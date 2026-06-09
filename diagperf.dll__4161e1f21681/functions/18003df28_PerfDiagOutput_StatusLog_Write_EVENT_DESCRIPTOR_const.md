# PerfDiagOutput::StatusLog::Write(_EVENT_DESCRIPTOR const &)

- ea: `0x18003df28`
- end: `0x18003df66`
- name: `?Write@StatusLog@PerfDiagOutput@@YAXAEBU_EVENT_DESCRIPTOR@@@Z`
- size: `62`
- prototype: `void __fastcall(PerfDiagOutput::StatusLog *__hidden this, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `16`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180016dec`
- `0x1800279d8`
- `0x1800286b8`
- `0x18002b580`
- `0x18002f06c`
- `0x180030840`
- `0x180031aec`
- `0x1800375cc`
- `0x18003f1b8`
- `0x1800b24c4`
- `0x1800b4f00`
- `0x1800b67d8`
- `0x1800b736c`
- `0x1800b9ae0`
- `0x1800ba5f0`
- `0x1800c49c4`

## callees

- `0x18003df28`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18003df5a`
- `ntdll!EtwEventWrite` at `0x18003df5a`
- `ntdll!EtwEventEnabled` at `0x18003df40`
- `ntdll!EtwEventEnabled` at `0x18003df40`

## pseudocode

```c
void __fastcall PerfDiagOutput::StatusLog::Write(PerfDiagOutput::StatusLog *this, const struct _EVENT_DESCRIPTOR *a2)
{
  if ( PerfDiagOutput::StatusLog::g_RegHandle )
  {
    if ( (unsigned __int8)EtwEventEnabled(PerfDiagOutput::StatusLog::g_RegHandle, this) )
      EtwEventWrite(PerfDiagOutput::StatusLog::g_RegHandle, this, 0, 0);
  }
}

```

## disassembly

```asm
0x18003df28  push    rbx
0x18003df2a  sub     rsp, 20h
0x18003df2e  mov     rbx, rcx
0x18003df31  mov     rcx, cs:?g_RegHandle@StatusLog@PerfDiagOutput@@3_KA; unsigned __int64 PerfDiagOutput::StatusLog::g_RegHandle
0x18003df38  test    rcx, rcx
0x18003df3b  jz      short loc_18003DF60
0x18003df3d  mov     rdx, rbx
0x18003df40  call    cs:__imp_EtwEventEnabled
0x18003df46  test    al, al
0x18003df48  jz      short loc_18003DF60
0x18003df4a  mov     rcx, cs:?g_RegHandle@StatusLog@PerfDiagOutput@@3_KA; unsigned __int64 PerfDiagOutput::StatusLog::g_RegHandle
0x18003df51  xor     r9d, r9d
0x18003df54  xor     r8d, r8d
0x18003df57  mov     rdx, rbx
0x18003df5a  call    cs:__imp_EtwEventWrite
0x18003df60  add     rsp, 20h
0x18003df64  pop     rbx
0x18003df65  retn
```
