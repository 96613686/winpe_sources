# wil::details::static_lazy<ControlPanelNavigationTelemetry>::Completer::~Completer(void)

- ea: `0x1800084c8`
- end: `0x1800084fd`
- name: `??1Completer@?$static_lazy@VControlPanelNavigationTelemetry@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013e4c`
- `0x18001ca0c`

## callees

- `0x1800084c8`
- `0x18001014c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800084f6`

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
0x1800084c8  push    rbx
0x1800084ca  sub     rsp, 20h
0x1800084ce  cmp     dword ptr [rcx+8], 0
0x1800084d2  mov     rbx, rcx
0x1800084d5  jnz     short loc_1800084E7
0x1800084d7  mov     rcx, [rcx]
0x1800084da  add     rcx, 8; this
0x1800084de  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x1800084e2  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800084e7  mov     rcx, [rbx]
0x1800084ea  mov     edx, [rbx+8]
0x1800084ed  lea     r8, [rcx+8]
0x1800084f1  add     rsp, 20h
0x1800084f5  pop     rbx
0x1800084f6  jmp     cs:__imp_InitOnceComplete
```
