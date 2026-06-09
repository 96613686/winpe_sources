# wil::details::static_lazy<NetworkingTriageScenario::GetConnected>::Completer::~Completer(void)

- ea: `0x180023974`
- end: `0x1800239ae`
- name: `??1Completer@?$static_lazy@VGetConnected@NetworkingTriageScenario@@@details@wil@@QEAA@XZ`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002cfb8`
- `0x18002d080`

## callees

- `0x180023974`
- `0x180029588`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800239a2`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<NetworkingTriageScenario::GetConnected>::Completer::~Completer(
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
0x180023974  push    rbx
0x180023976  sub     rsp, 20h
0x18002397a  cmp     dword ptr [rcx+8], 0
0x18002397e  mov     rbx, rcx
0x180023981  jnz     short loc_180023993
0x180023983  mov     rcx, [rcx]
0x180023986  add     rcx, 8; this
0x18002398a  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x18002398e  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180023993  mov     rcx, [rbx]
0x180023996  mov     edx, [rbx+8]
0x180023999  lea     r8, [rcx+8]
0x18002399d  add     rsp, 20h
0x1800239a1  pop     rbx
0x1800239a2  jmp     cs:__imp_InitOnceComplete
```
