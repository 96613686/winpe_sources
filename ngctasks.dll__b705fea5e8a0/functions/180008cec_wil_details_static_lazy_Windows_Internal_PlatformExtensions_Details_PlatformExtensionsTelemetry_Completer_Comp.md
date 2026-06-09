# wil::details::static_lazy<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry>::Completer::~Completer(void)

- ea: `0x180008cec`
- end: `0x180008d22`
- name: `??1Completer@?$static_lazy@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@@details@wil@@QEAA@XZ`
- size: `54`
- prototype: `BOOL __fastcall(_DWORD *, __int64, void (*)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ed50`
- `0x18001f985`

## callees

- `0x180008cec`
- `0x18000c54c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008d15`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180008d15`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry>::Completer::~Completer(
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
0x180008cec  push    rbx
0x180008cee  sub     rsp, 20h
0x180008cf2  mov     rbx, rcx
0x180008cf5  cmp     dword ptr [rcx+8], 0
0x180008cf9  jnz     short loc_180008D0B
0x180008cfb  mov     rcx, [rcx]
0x180008cfe  add     rcx, 8; this
0x180008d02  mov     rdx, [rcx+18h]; struct _tlgProvider_t *
0x180008d06  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180008d0b  mov     rcx, [rbx]; lpInitOnce
0x180008d0e  lea     r8, [rcx+8]; lpContext
0x180008d12  mov     edx, [rbx+8]; dwFlags
0x180008d15  call    cs:__imp_InitOnceComplete
0x180008d1b  nop
0x180008d1c  add     rsp, 20h
0x180008d20  pop     rbx
0x180008d21  retn
```
