# wil::details::static_lazy<NetworkingTriageScenario::GetConnected>::Completer::~Completer(void)

- ea: `0x180022d34`
- end: `0x180022d69`
- name: `??1Completer@?$static_lazy@VGetConnected@NetworkingTriageScenario@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: `BOOL __fastcall(_DWORD *, __int64, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002c024`
- `0x18002c0e4`

## callees

- `0x180022d34`
- `0x1800287a4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180022d62`

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
0x180022d34  push    rbx
0x180022d36  sub     rsp, 20h
0x180022d3a  cmp     dword ptr [rcx+8], 0
0x180022d3e  mov     rbx, rcx
0x180022d41  jnz     short loc_180022D53
0x180022d43  mov     rcx, [rcx]
0x180022d46  add     rcx, 8; this
0x180022d4a  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x180022d4e  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180022d53  mov     rcx, [rbx]
0x180022d56  mov     edx, [rbx+8]
0x180022d59  lea     r8, [rcx+8]
0x180022d5d  add     rsp, 20h
0x180022d61  pop     rbx
0x180022d62  jmp     cs:__imp_InitOnceComplete
```
