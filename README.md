# NexusMali

NexusMali está migrando da base experimental PanVK/Mesa v0.2 para o **MaliSX2 oficial v0.3.3**, mantendo esta identidade de projeto e o histórico da versão anterior.

## Base técnica da migração

- Projeto upstream: https://github.com/bmdhacks/malisx2
- Versão: `v0.3.3`
- Commit MaliSX2: `d0422ed5eb5d8971f118f14d2550ce04aa1a0a5a`
- Mesa derivado de `bmdhacks/armsx2-turnip`
- Commit Mesa fixado: `81113fce01b0e3974cdbb2683449e8619d0639e0`
- Saída Android ARM64: `libvulkan_malisx2.so`
- Compilação: Meson + Ninja, NDK r28c, API 29.

O workflow em `.github/workflows/build.yml` baixa exatamente essas revisões, compila para Android ARM64, verifica o ELF e gera um pacote ZIP com biblioteca, metadados, licença e hashes SHA-256. A execução é manual por `workflow_dispatch`.

## Compatibilidade

O alvo de teste deste projeto inclui o Galaxy S10 com Exynos 9820 e Mali-G76 MP12. **A Mali-G76 não consta entre as GPUs oficialmente testadas pelo upstream MaliSX2 v0.3.3**; portanto, o pacote para esse aparelho é experimental e precisa ser validado no dispositivo. Não há garantia de funcionamento apenas por compilar para ARM64.

## Histórico

O arquivo `NexusMali-v0.2-source.zip` foi mantido como referência histórica. Ele contém a base anterior e não é mais usado pelo novo workflow.

## Licenças

O driver MaliSX2 é distribuído sob MIT. O código Mesa utilizado na compilação mantém suas próprias licenças. Consulte os avisos e licenças presentes no repositório upstream e no pacote gerado.
