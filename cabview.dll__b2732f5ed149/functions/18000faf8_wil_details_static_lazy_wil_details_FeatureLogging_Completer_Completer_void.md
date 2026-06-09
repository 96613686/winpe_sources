# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x18000faf8`
- end: `0x18000fb2d`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011ac4`
- `0x180011ba0`

## callees

- `0x18000faf8`
- `0x180010cc8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000fb26`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(
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
0x18000faf8  push    rbx
0x18000fafa  sub     rsp, 20h
0x18000fafe  cmp     dword ptr [rcx+8], 0
0x18000fb02  mov     rbx, rcx
0x18000fb05  jnz     short loc_18000FB17
0x18000fb07  mov     rcx, [rcx]
0x18000fb0a  add     rcx, 8; this
0x18000fb0e  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x18000fb12  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000fb17  mov     rcx, [rbx]
0x18000fb1a  mov     edx, [rbx+8]
0x18000fb1d  lea     r8, [rcx+8]
0x18000fb21  add     rsp, 20h
0x18000fb25  pop     rbx
0x18000fb26  jmp     cs:__imp_InitOnceComplete
```
