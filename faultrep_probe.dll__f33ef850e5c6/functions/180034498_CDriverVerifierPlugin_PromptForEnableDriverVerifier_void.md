# CDriverVerifierPlugin::PromptForEnableDriverVerifier(void *)

- ea: `0x180034498`
- end: `0x180034840`
- name: `?PromptForEnableDriverVerifier@CDriverVerifierPlugin@@AEAAHPEAX@Z`
- size: `936`
- prototype: `__int64 __fastcall(CDriverVerifierPlugin *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033aec`

## callees

- `0x1800028b4`
- `0x180009f00`
- `0x1800160a4`
- `0x18001e95c`
- `0x180026ed4`
- `0x180034498`
- `0x18003c178`

## import_xrefs

- `wer!WerpGetReportFlags` at `0x18003453b`
- `wer!WerpGetReportFlags` at `0x18003453b`
- `wer!WerpPromptUser` at `0x18003476a`
- `wer!WerpPromptUser` at `0x18003476a`

## string_xrefs

- `0x1800347b5`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\DriverVerifier`

## pseudocode

```c

```
