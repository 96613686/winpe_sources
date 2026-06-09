# CCrashReport::SetReportSignature(void *,WER_PLUGIN_SIG_ELEMENT *,ulong)

- ea: `0x180015830`
- end: `0x180015bf7`
- name: `?SetReportSignature@CCrashReport@@AEAAJPEAXPEAUWER_PLUGIN_SIG_ELEMENT@@K@Z`
- size: `967`
- prototype: `int(CCrashReport *__hidden this, void *, struct WER_PLUGIN_SIG_ELEMENT *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000ff8c`

## callees

- `0x1800028b4`
- `0x180006b50`
- `0x180009e04`
- `0x180009f00`
- `0x180015830`
- `0x180016414`
- `0x18001b448`
- `0x180026210`
- `0x18003e5a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800158eb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800158eb`
- `wer!WerpSetReportNamespaceParameter` at `0x180015b76`
- `wer!WerpSetReportNamespaceParameter` at `0x180015b76`
- `wer!WerReportSetParameter` at `0x180015909`
- `wer!WerReportSetParameter` at `0x1800159fd`
- `wer!WerReportSetParameter` at `0x180015aab`
- `wer!WerReportSetParameter` at `0x180015909`
- `wer!WerReportSetParameter` at `0x1800159fd`
- `wer!WerReportSetParameter` at `0x180015aab`

## pseudocode

```c

```
