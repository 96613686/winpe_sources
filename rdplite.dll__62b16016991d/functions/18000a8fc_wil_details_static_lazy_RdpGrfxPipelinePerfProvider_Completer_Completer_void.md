# wil::details::static_lazy<RdpGrfxPipelinePerfProvider>::Completer::~Completer(void)

- ea: `0x18000a8fc`
- end: `0x18000a931`
- name: `??1Completer@?$static_lazy@VRdpGrfxPipelinePerfProvider@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d6cc`
- `0x180012728`

## callees

- `0x18000a8fc`
- `0x18000bb60`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a92a`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<RdpGrfxPipelinePerfProvider>::Completer::~Completer(
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
0x18000a8fc  push    rbx
0x18000a8fe  sub     rsp, 20h
0x18000a902  cmp     dword ptr [rcx+8], 0
0x18000a906  mov     rbx, rcx
0x18000a909  jnz     short loc_18000A91B
0x18000a90b  mov     rcx, [rcx]
0x18000a90e  add     rcx, 8; this
0x18000a912  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x18000a916  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000a91b  mov     rcx, [rbx]
0x18000a91e  mov     edx, [rbx+8]
0x18000a921  lea     r8, [rcx+8]
0x18000a925  add     rsp, 20h
0x18000a929  pop     rbx
0x18000a92a  jmp     cs:__imp_InitOnceComplete
```
