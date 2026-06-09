# WebRuntimeDiagnostics::DiagnosticsTargetData::~DiagnosticsTargetData(void)

- ea: `0x18006ad94`
- end: `0x18006add9`
- name: `??1DiagnosticsTargetData@WebRuntimeDiagnostics@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(WebRuntimeDiagnostics::DiagnosticsTargetData *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18006b060`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ada1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006adb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006adc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ada1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006adb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006adc5`

## pseudocode

```c
void __fastcall WebRuntimeDiagnostics::DiagnosticsTargetData::~DiagnosticsTargetData(HSTRING *this)
{
  WindowsDeleteString(this[8]);
  this[8] = 0;
  WindowsDeleteString(this[6]);
  this[6] = 0;
  WindowsDeleteString(this[5]);
  this[5] = 0;
}

```

## disassembly

```asm
0x18006ad94  push    rbx
0x18006ad96  sub     rsp, 20h
0x18006ad9a  mov     rbx, rcx
0x18006ad9d  mov     rcx, [rcx+40h]; string
0x18006ada1  call    cs:__imp_WindowsDeleteString
0x18006ada7  mov     qword ptr [rbx+40h], 0
0x18006adaf  mov     rcx, [rbx+30h]; string
0x18006adb3  call    cs:__imp_WindowsDeleteString
0x18006adb9  mov     qword ptr [rbx+30h], 0
0x18006adc1  mov     rcx, [rbx+28h]; string
0x18006adc5  call    cs:__imp_WindowsDeleteString
0x18006adcb  mov     qword ptr [rbx+28h], 0
0x18006add3  add     rsp, 20h
0x18006add7  pop     rbx
0x18006add8  retn
```
