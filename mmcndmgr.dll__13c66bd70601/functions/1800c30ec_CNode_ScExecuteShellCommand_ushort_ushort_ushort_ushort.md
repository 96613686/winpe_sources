# CNode::ScExecuteShellCommand(ushort *,ushort *,ushort *,ushort *)

- ea: `0x1800c30ec`
- end: `0x1800c35da`
- name: `?ScExecuteShellCommand@CNode@@QEAA?AVSC@mmcerror@@PEAG000@Z`
- size: `1262`
- prototype: `__int64 __fastcall(__int64, __int64, const unsigned __int16 *, const WCHAR *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800e8ee0`

## callees

- `0x180004998`
- `0x1800063c0`
- `0x1800074d0`
- `0x180013dac`
- `0x18002a710`
- `0x18003b6dc`
- `0x180057074`
- `0x180086d68`
- `0x1800c30ec`
- `0x1801076c4`
- `0x180134502`
- `0x18013450e`
- `0x180134540`

## import_xrefs

- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800c31a3`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800c3222`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800c33dc`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800c3437`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800c3517`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800c31a3`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800c3222`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800c33dc`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800c3437`
- `mmcbase!?ToHr@SC@mmcerror@@QEBAJXZ` at `0x1800c3517`
- `mmcbase!GetStringModule` at `0x1800c32ea`
- `mmcbase!GetStringModule` at `0x1800c332e`
- `mmcbase!GetStringModule` at `0x1800c32ea`
- `mmcbase!GetStringModule` at `0x1800c332e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1800c318e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1800c3502`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1800c318e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x1800c3502`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1800c3169`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x1800c3169`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800c319a`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800c350e`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800c319a`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1800c350e`
- `mmcbase!?s_CallDepth@SC@mmcerror@@0IA` at `0x1800c3147`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c34e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c34e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c34e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c34e1`
- `USER32!MessageBoxW` at `0x1800c336f`
- `USER32!MessageBoxW` at `0x1800c336f`
- `USER32!GetActiveWindow` at `0x1800c3303`
- `USER32!GetActiveWindow` at `0x1800c3303`
- `SHELL32!ShellExecuteExW` at `0x1800c34d3`
- `SHELL32!ShellExecuteExW` at `0x1800c34d3`

## string_xrefs

- `0x1800c315f`: `CNode::ScExecuteShellCommand`

## pseudocode

```c

```
