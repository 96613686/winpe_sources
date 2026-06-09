# wil::details::static_lazy<NetworkingTriageScenario::GetConnected>::Completer::~Completer(void)

- ea: `0x18000f1d8`
- end: `0x18000f20d`
- name: `??1Completer@?$static_lazy@VGetConnected@NetworkingTriageScenario@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013444`
- `0x180013558`
- `0x18001dc2c`

## callees

- `0x18000f1d8`
- `0x1800119c0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000f206`

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
0x18000f1d8  push    rbx
0x18000f1da  sub     rsp, 20h
0x18000f1de  cmp     dword ptr [rcx+8], 0
0x18000f1e2  mov     rbx, rcx
0x18000f1e5  jnz     short loc_18000F1F7
0x18000f1e7  mov     rcx, [rcx]
0x18000f1ea  add     rcx, 8; this
0x18000f1ee  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x18000f1f2  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000f1f7  mov     rcx, [rbx]
0x18000f1fa  mov     edx, [rbx+8]
0x18000f1fd  lea     r8, [rcx+8]
0x18000f201  add     rsp, 20h
0x18000f205  pop     rbx
0x18000f206  jmp     cs:__imp_InitOnceComplete
```
