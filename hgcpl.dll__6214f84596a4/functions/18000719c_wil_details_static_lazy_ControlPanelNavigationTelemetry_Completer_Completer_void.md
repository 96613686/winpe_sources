# wil::details::static_lazy<ControlPanelNavigationTelemetry>::Completer::~Completer(void)

- ea: `0x18000719c`
- end: `0x1800071d1`
- name: `??1Completer@?$static_lazy@VControlPanelNavigationTelemetry@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000adf8`
- `0x18000aeb8`
- `0x1800124b0`
- `0x180018644`

## callees

- `0x18000719c`
- `0x1800084f4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800071ca`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<ControlPanelNavigationTelemetry>::Completer::~Completer(
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
0x18000719c  push    rbx
0x18000719e  sub     rsp, 20h
0x1800071a2  cmp     dword ptr [rcx+8], 0
0x1800071a6  mov     rbx, rcx
0x1800071a9  jnz     short loc_1800071BB
0x1800071ab  mov     rcx, [rcx]
0x1800071ae  add     rcx, 8; this
0x1800071b2  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x1800071b6  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800071bb  mov     rcx, [rbx]
0x1800071be  mov     edx, [rbx+8]
0x1800071c1  lea     r8, [rcx+8]
0x1800071c5  add     rsp, 20h
0x1800071c9  pop     rbx
0x1800071ca  jmp     cs:__imp_InitOnceComplete
```
