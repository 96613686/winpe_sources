# wil::details::static_lazy<SearchIndexerTraceProvider>::Completer::~Completer(void)

- ea: `0x18001684c`
- end: `0x180016881`
- name: `??1Completer@?$static_lazy@USearchIndexerTraceProvider@@@details@wil@@QEAA@XZ`
- size: `53`
- prototype: `BOOL __fastcall(_DWORD *, __int64, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002f80`
- `0x180005c00`
- `0x18000a480`
- `0x18001c398`
- `0x180022224`
- `0x1800222e4`

## callees

- `0x18000a9a0`
- `0x18001684c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001687a`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<SearchIndexerTraceProvider>::Completer::~Completer(
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
0x18001684c  push    rbx
0x18001684e  sub     rsp, 20h
0x180016852  cmp     dword ptr [rcx+8], 0
0x180016856  mov     rbx, rcx
0x180016859  jnz     short loc_18001686B
0x18001685b  mov     rcx, [rcx]
0x18001685e  add     rcx, 8; this
0x180016862  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x180016866  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18001686b  mov     rcx, [rbx]
0x18001686e  mov     edx, [rbx+8]
0x180016871  lea     r8, [rcx+8]
0x180016875  add     rsp, 20h
0x180016879  pop     rbx
0x18001687a  jmp     cs:__imp_InitOnceComplete
```
