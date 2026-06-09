# wil::details::static_lazy<AccessibilitySettingsTraceLogging>::Completer::~Completer(void)

- ea: `0x14001d7d4`
- end: `0x14001d809`
- name: `??1Completer@?$static_lazy@VAccessibilitySettingsTraceLogging@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002120c`
- `0x14002485c`

## callees

- `0x14001d7d4`
- `0x14001fd8c`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x14001d802`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<AccessibilitySettingsTraceLogging>::Completer::~Completer(
        _DWORD *a1,
        __int64 a2,
        void (*a3)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))
{
  if ( !a1[2] )
    wil::TraceLoggingProvider::Register(
      (wil::TraceLoggingProvider *)(*(_QWORD *)a1 + 8LL),
      *(const struct _tlgProvider_t *const *)(*(_QWORD *)a1 + 32LL),
      a3);
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x14001d7d4  push    rbx
0x14001d7d6  sub     rsp, 20h
0x14001d7da  cmp     dword ptr [rcx+8], 0
0x14001d7de  mov     rbx, rcx
0x14001d7e1  jnz     short loc_14001D7F3
0x14001d7e3  mov     rcx, [rcx]
0x14001d7e6  add     rcx, 8; this
0x14001d7ea  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x14001d7ee  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x14001d7f3  mov     rcx, [rbx]
0x14001d7f6  mov     edx, [rbx+8]
0x14001d7f9  lea     r8, [rcx+8]
0x14001d7fd  add     rsp, 20h
0x14001d801  pop     rbx
0x14001d802  jmp     cs:__imp_InitOnceComplete
```
