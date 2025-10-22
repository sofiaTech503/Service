# ⚙️ MÓDULO 3: SERVIÇOS

📂 Estrutura de pastas:

frontend/

└── src/

    └── pages/

        └── Servicos/

            ├── index.js

            ├── Contratos.jsx

            ├── FaturamentoServicos.jsx
            
            └── Recibos.jsx

🔹 index.js
import React from "react";
import FaturamentoServicos from "./FaturamentoServicos";
import Contratos from "./Contratos";
import Recibos from "./Recibos";

export default function Servicos() {
  return (
    <div className="page-container">
      <h1>⚙️ Serviços e NFs</h1>
      <p>
        Gerencie seus contratos de prestação de serviços, notas fiscais
        eletrônicas e recibos de forma simples e prática.
      </p>

      <FaturamentoServicos />
      <hr style={{ margin: "20px 0" }} />
      <Contratos />
      <hr style={{ margin: "20px 0" }} />
      <Recibos />
    </div>
  );
}

🔹 FaturamentoServicos.jsx
import React from "react";

export default function FaturamentoServicos() {
  const servicos = [
    { id: 1, descricao: "Consultoria de sistemas", valor: 1200, status: "Emitida", data: "2025-10-15" },
    { id: 2, descricao: "Treinamento de equipe", valor: 800, status: "Pendente", data: "2025-10-20" },
  ];

  return (
    <section>
      <h2>🧾 Faturamento de Serviços</h2>
      <table style={{ width: "100%", marginTop: 10, borderCollapse: "collapse" }}>
        <thead>
          <tr style={{ background: "#eee" }}>
            <th>Serviço</th>
            <th>Data</th>
            <th>Valor (R$)</th>
            <th>Status</th>
          </tr>
        </thead>
        <tbody>
          {servicos.map((s) => (
            <tr key={s.id} style={{ textAlign: "center", borderBottom: "1px solid #ddd" }}>
              <td>{s.descricao}</td>
              <td>{s.data}</td>
              <td>{s.valor.toFixed(2)}</td>
              <td>{s.status}</td>
            </tr>
          ))}
        </tbody>
      </table>
    </section>
  );
}

🔹 Contratos.jsx
import React from "react";

export default function Contratos() {
  const contratos = [
    { id: 1, cliente: "TechSolutions", servico: "Suporte Mensal", inicio: "2025-01-01", fim: "2025-12-31" },
    { id: 2, cliente: "SuperMercado Real", servico: "Consultoria ERP", inicio: "2025-08-01", fim: "2026-07-31" },
  ];

  return (
    <section>
      <h2>📄 Contratos Ativos</h2>
      <table style={{ width: "100%", marginTop: 10, borderCollapse: "collapse" }}>
        <thead>
          <tr style={{ background: "#eee" }}>
            <th>Cliente</th>
            <th>Serviço</th>
            <th>Início</th>
            <th>Fim</th>
          </tr>
        </thead>
        <tbody>
          {contratos.map((c) => (
            <tr key={c.id} style={{ textAlign: "center", borderBottom: "1px solid #ddd" }}>
              <td>{c.cliente}</td>
              <td>{c.servico}</td>
              <td>{c.inicio}</td>
              <td>{c.fim}</td>
            </tr>
          ))}
        </tbody>
      </table>
    </section>
  );
}

🔹 Recibos.jsx
import React from "react";

export default function Recibos() {
  const recibos = [
    { id: 1, cliente: "TechSolutions", valor: 1200, data: "2025-10-15" },
    { id: 2, cliente: "SuperMercado Real", valor: 800, data: "2025-10-18" },
  ];

  return (
    <section>
      <h2>🧾 Recibos Emitidos</h2>
      <table style={{ width: "100%", marginTop: 10, borderCollapse: "collapse" }}>
        <thead>
          <tr style={{ background: "#eee" }}>
            <th>Cliente</th>
            <th>Valor (R$)</th>
            <th>Data</th>
          </tr>
        </thead>
        <tbody>
          {recibos.map((r) => (
            <tr key={r.id} style={{ textAlign: "center", borderBottom: "1px solid #ddd" }}>
              <td>{r.cliente}</td>
              <td>{r.valor.toFixed(2)}</td>
              <td>{r.data}</td>
            </tr>
          ))}
        </tbody>
      </table>
    </section>
  );
}

🔹 Atualize seu Sidebar.js

Verifique se existe o item:

<li><Link to="/servicos">⚙️ Serviços</Link></li>


Se não tiver, adicione.

🔹 Atualize suas rotas (App.js)

Adicione o import:

import Servicos from "./pages/Servicos";


E no bloco <Routes>:

<Route path="/servicos" element={<Servicos />} />


✅ Resultado esperado no ERP:

No menu lateral (sidebar), o item Serviços abrirá uma página com:

🧾 Faturamento de Serviços

📄 Contratos Ativos

🧾 Recibos Emitidos

Tudo organizado e pronto para integrar futuramente com o backend.
