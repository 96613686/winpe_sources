# OfflineMapsTraceLogging::Provider(void)

- ea: `0x18000689c`
- end: `0x18000694e`
- name: `?Provider@OfflineMapsTraceLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800065ac`
- `0x18000668c`
- `0x180006750`
- `0x180009660`

## callees

- `0x1800020bc`
- `0x18000642c`
- `0x18000689c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800068c7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800068c7`

## pseudocode

```c
const struct _tlgProvider_t *OfflineMapsTraceLogging::Provider(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`OfflineMapsTraceLogging::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`OfflineMapsTraceLogging::Instance'::`2'::wrapper;
    v4 = &qword_180018598;
    qword_180018598 = (__int64)&wil::TraceLoggingProvider::`vftable';
    qword_1800185A0 = 0;
    byte_1800185A8 = 0;
    dword_1800185AC = 0;
    qword_1800185B0 = (__int64)&`OfflineMapsTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_b1920e3fd6e26929e52072737012d5c8_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(&v1);
  }
  return (const struct _tlgProvider_t *)v4[1];
}

```

## disassembly

```asm
0x18000689c  mov     rax, rsp
0x18000689f  push    rdi
0x1800068a0  sub     rsp, 30h
0x1800068a4  lea     rdi, ?wrapper@?1??Instance@OfflineMapsTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VOfflineMapsTraceLogging@@@details@wil@@A; wil::details::static_lazy<OfflineMapsTraceLogging> `OfflineMapsTraceLogging::Instance(void)'::`2'::wrapper
0x1800068ab  mov     qword ptr [rax+10h], 0
0x1800068b3  mov     rcx, rdi; lpInitOnce
0x1800068b6  mov     dword ptr [rax+8], 0
0x1800068bd  lea     r9, [rax+10h]; lpContext
0x1800068c1  xor     edx, edx; dwFlags
0x1800068c3  lea     r8, [rax+8]; fPending
0x1800068c7  call    cs:__imp_InitOnceBeginInitialize
0x1800068cd  test    eax, eax
0x1800068cf  jz      short loc_18000693F
0x1800068d1  cmp     [rsp+38h+arg_0], 0
0x1800068d6  jz      short loc_18000693F
0x1800068d8  lea     rax, qword_180018598
0x1800068df  mov     [rsp+38h+var_18], rdi
0x1800068e4  mov     [rsp+38h+arg_8], rax
0x1800068e9  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x1800068f0  mov     cs:qword_180018598, rax
0x1800068f7  mov     cs:qword_1800185A0, 0
0x180006902  mov     cs:byte_1800185A8, 0
0x180006909  mov     cs:dword_1800185AC, 0
0x180006913  lea     rax, ?__hInner@?1???0StaticHandle@OfflineMapsTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `OfflineMapsTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000691a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b1920e3fd6e26929e52072737012d5c8_@@CA@XZ; void (__cdecl *)()
0x180006921  mov     cs:qword_1800185B0, rax
0x180006928  call    atexit
0x18000692d  lea     rcx, [rsp+38h+var_18]
0x180006932  mov     [rsp+38h+var_10], 0
0x18000693a  call    ??1Completer@?$static_lazy@VOfflineMapsTraceLogging@@@details@wil@@QEAA@XZ; wil::details::static_lazy<OfflineMapsTraceLogging>::Completer::~Completer(void)
0x18000693f  mov     rax, [rsp+38h+arg_8]
0x180006944  mov     rax, [rax+8]
0x180006948  add     rsp, 30h
0x18000694c  pop     rdi
0x18000694d  retn
```
