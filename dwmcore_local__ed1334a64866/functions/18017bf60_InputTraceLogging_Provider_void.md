# InputTraceLogging::Provider(void)

- ea: `0x18017bf60`
- end: `0x18017c01e`
- name: `?Provider@InputTraceLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `190`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `35`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801120ac`
- `0x180112110`
- `0x180114240`
- `0x1801147a0`
- `0x1801149e8`
- `0x1801555d0`
- `0x180155610`
- `0x180189670`
- `0x18018c184`
- `0x1801a03a0`
- `0x1801d90d8`
- `0x1801df6bc`
- `0x1801e1630`
- `0x1801e1918`
- `0x1801f2d0c`
- `0x1801f32c8`
- `0x1801f38a8`
- `0x1801f3e88`
- `0x1801f4468`
- `0x1801f4a48`
- `0x1801f4fdc`
- `0x1801f51c4`
- `0x1801f526c`
- `0x1801f549c`
- `0x1801f5768`
- `0x1801f6020`
- `0x1801f71e0`
- `0x1801f8508`
- `0x1801f8548`
- `0x1801f88f0`
- `0x180220300`
- `0x18022f300`
- `0x180256990`
- `0x18027aee0`
- `0x18027b198`

## callees

- `0x18017bf60`
- `0x18017c060`
- `0x180228840`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18017bf88`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18017bf88`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18017c013`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18017c013`

## pseudocode

```c
const struct _tlgProvider_t *InputTraceLogging::Provider(void)
{
  void (*v1)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`InputTraceLogging::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_1803BB198 = 0;
    v3 = &qword_1803BB190;
    qword_1803BB190 = &wil::details::FeatureLogging::`vftable';
    byte_1803BB1A0 = 0;
    dword_1803BB1A4 = 0;
    CallbackContext = &`InputTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`InputTraceLogging::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register(
      (wil::TraceLoggingProvider *)&qword_1803BB190,
      (const struct _tlgProvider_t *const)CallbackContext,
      v1);
    InitOnceComplete(&`InputTraceLogging::Instance'::`2'::wrapper, 0, &qword_1803BB190);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x18017bf60  mov     rax, rsp
0x18017bf63  push    rbx
0x18017bf64  sub     rsp, 20h
0x18017bf68  lea     r9, [rax+10h]; lpContext
0x18017bf6c  mov     qword ptr [rax+10h], 0
0x18017bf74  lea     r8, [rax+8]; fPending
0x18017bf78  mov     dword ptr [rax+8], 0
0x18017bf7f  xor     edx, edx; dwFlags
0x18017bf81  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x18017bf88  call    cs:__imp_InitOnceBeginInitialize
0x18017bf8e  test    eax, eax
0x18017bf90  jz      short loc_18017BF99
0x18017bf92  cmp     [rsp+28h+arg_0], 0
0x18017bf97  jnz     short loc_18017BFA8
0x18017bf99  mov     rax, [rsp+28h+arg_8]
0x18017bf9e  mov     rax, [rax+8]
0x18017bfa2  add     rsp, 20h
0x18017bfa6  pop     rbx
0x18017bfa7  retn
0x18017bfa8  lea     rbx, qword_1803BB190
0x18017bfaf  mov     cs:qword_1803BB198, 0
0x18017bfba  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18017bfc1  mov     [rsp+28h+arg_8], rbx
0x18017bfc6  mov     cs:qword_1803BB190, rax
0x18017bfcd  mov     cs:byte_1803BB1A0, 0
0x18017bfd4  mov     cs:dword_1803BB1A4, 0
0x18017bfde  lea     rax, ?__hInner@?1???0StaticHandle@InputTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `InputTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18017bfe5  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@InputTraceLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18017bfec  mov     cs:CallbackContext, rax
0x18017bff3  call    atexit
0x18017bff8  mov     rdx, cs:CallbackContext; struct _tlgProvider_t *
0x18017bfff  mov     rcx, rbx; this
0x18017c002  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18017c007  mov     r8, rbx; lpContext
0x18017c00a  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x18017c011  xor     edx, edx; dwFlags
0x18017c013  call    cs:__imp_InitOnceComplete
0x18017c019  jmp     loc_18017BF99
```
