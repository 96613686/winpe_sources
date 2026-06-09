# CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *)

- ea: `0x1800147e8`
- end: `0x18001480d`
- name: `?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@@Z`
- size: `37`
- prototype: `__int64 __fastcall(CEventLogger *__hidden this, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180011b8c`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x1800147f9`
- `ADVAPI32!EventWrite` at `0x1800147f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEventLogger::LogEvent(CEventLogger *this, const struct _EVENT_DESCRIPTOR *a2)
{
  return EventWrite(g_Logger, a2, 0, 0) != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x1800147e8  sub     rsp, 28h
0x1800147ec  mov     rcx, cs:?g_Logger@@3VCEventLogger@@A; RegHandle
0x1800147f3  xor     r9d, r9d; UserData
0x1800147f6  xor     r8d, r8d; UserDataCount
0x1800147f9  call    cs:__imp_EventWrite
0x1800147ff  neg     eax
0x180014801  sbb     eax, eax
0x180014803  and     eax, 80004005h
0x180014808  add     rsp, 28h
0x18001480c  retn
```
