# InputTraceLogging::Provider(void)

- ea: `0x18017c1a0`
- end: `0x18017c25e`
- name: `?Provider@InputTraceLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `190`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `35`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801339ec`
- `0x180133a50`
- `0x180135b80`
- `0x1801360e0`
- `0x180136328`
- `0x18018adf0`
- `0x18018d904`
- `0x1801a0d40`
- `0x1801da328`
- `0x1801dfe3c`
- `0x1801e15a0`
- `0x1801e1888`
- `0x1801e4fbc`
- `0x1801e4ffc`
- `0x1801f2b7c`
- `0x1801f3138`
- `0x1801f3718`
- `0x1801f3cf8`
- `0x1801f42d8`
- `0x1801f48b8`
- `0x1801f4e4c`
- `0x1801f5034`
- `0x1801f50dc`
- `0x1801f530c`
- `0x1801f55d8`
- `0x1801f5e90`
- `0x1801f7050`
- `0x1801f8378`
- `0x1801f83b8`
- `0x1801f8760`
- `0x180220320`
- `0x18022f320`
- `0x1802569b0`
- `0x18027af00`
- `0x18027b1b8`

## callees

- `0x18017c1a0`
- `0x18017c2a0`
- `0x180228860`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18017c1c8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18017c1c8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18017c253`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18017c253`

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
    qword_1803BB188 = 0;
    v3 = &qword_1803BB180;
    qword_1803BB180 = &wil::details::FeatureLogging::`vftable';
    byte_1803BB190 = 0;
    dword_1803BB194 = 0;
    CallbackContext = &`InputTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`InputTraceLogging::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register(
      (wil::TraceLoggingProvider *)&qword_1803BB180,
      (const struct _tlgProvider_t *const)CallbackContext,
      v1);
    InitOnceComplete(&`InputTraceLogging::Instance'::`2'::wrapper, 0, &qword_1803BB180);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x18017c1a0  mov     rax, rsp
0x18017c1a3  push    rbx
0x18017c1a4  sub     rsp, 20h
0x18017c1a8  lea     r9, [rax+10h]; lpContext
0x18017c1ac  mov     qword ptr [rax+10h], 0
0x18017c1b4  lea     r8, [rax+8]; fPending
0x18017c1b8  mov     dword ptr [rax+8], 0
0x18017c1bf  xor     edx, edx; dwFlags
0x18017c1c1  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x18017c1c8  call    cs:__imp_InitOnceBeginInitialize
0x18017c1ce  test    eax, eax
0x18017c1d0  jz      short loc_18017C1D9
0x18017c1d2  cmp     [rsp+28h+arg_0], 0
0x18017c1d7  jnz     short loc_18017C1E8
0x18017c1d9  mov     rax, [rsp+28h+arg_8]
0x18017c1de  mov     rax, [rax+8]
0x18017c1e2  add     rsp, 20h
0x18017c1e6  pop     rbx
0x18017c1e7  retn
0x18017c1e8  lea     rbx, qword_1803BB180
0x18017c1ef  mov     cs:qword_1803BB188, 0
0x18017c1fa  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x18017c201  mov     [rsp+28h+arg_8], rbx
0x18017c206  mov     cs:qword_1803BB180, rax
0x18017c20d  mov     cs:byte_1803BB190, 0
0x18017c214  mov     cs:dword_1803BB194, 0
0x18017c21e  lea     rax, ?__hInner@?1???0StaticHandle@InputTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `InputTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18017c225  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@InputTraceLogging@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18017c22c  mov     cs:CallbackContext, rax
0x18017c233  call    atexit
0x18017c238  mov     rdx, cs:CallbackContext; struct _tlgProvider_t *
0x18017c23f  mov     rcx, rbx; this
0x18017c242  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18017c247  mov     r8, rbx; lpContext
0x18017c24a  lea     rcx, ?wrapper@?1??Instance@InputTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VInputTraceLogging@@@details@wil@@A; lpInitOnce
0x18017c251  xor     edx, edx; dwFlags
0x18017c253  call    cs:__imp_InitOnceComplete
0x18017c259  jmp     loc_18017C1D9
```
