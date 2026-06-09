# UalPrintLogging::Instance(void)

- ea: `0x18000a3bc`
- end: `0x18000a46a`
- name: `?Instance@UalPrintLogging@@KAPEAV1@XZ`
- size: `174`
- prototype: `struct UalPrintLogging *(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a470`
- `0x18000a89c`
- `0x18000a9a4`
- `0x18000bb90`

## callees

- `0x1800021c4`
- `0x18000a26c`
- `0x18000a3bc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a3e7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a3e7`

## pseudocode

```c
struct UalPrintLogging *UalPrintLogging::Instance(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  WINBOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`UalPrintLogging::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`UalPrintLogging::Instance'::`2'::wrapper;
    v4 = &qword_180013290;
    qword_180013290 = (__int64)&wil::TraceLoggingProvider::`vftable';
    qword_180013298 = 0;
    byte_1800132A0 = 0;
    dword_1800132A4 = 0;
    qword_1800132A8 = (__int64)&`UalPrintLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_5b247de46c1b9b2de92b67fa654160e8_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<UalPrintLogging>::Completer::~Completer(&v1);
  }
  return (struct UalPrintLogging *)v4;
}

```

## disassembly

```asm
0x18000a3bc  mov     rax, rsp
0x18000a3bf  push    rdi
0x18000a3c0  sub     rsp, 30h
0x18000a3c4  lea     rdi, ?wrapper@?1??Instance@UalPrintLogging@@KAPEAV2@XZ@4V?$static_lazy@VUalPrintLogging@@@details@wil@@A; wil::details::static_lazy<UalPrintLogging> `UalPrintLogging::Instance(void)'::`2'::wrapper
0x18000a3cb  mov     qword ptr [rax+10h], 0
0x18000a3d3  mov     rcx, rdi; lpInitOnce
0x18000a3d6  mov     dword ptr [rax+8], 0
0x18000a3dd  lea     r9, [rax+10h]; lpContext
0x18000a3e1  xor     edx, edx; dwFlags
0x18000a3e3  lea     r8, [rax+8]; fPending
0x18000a3e7  call    cs:__imp_InitOnceBeginInitialize
0x18000a3ed  test    eax, eax
0x18000a3ef  jz      short loc_18000A45F
0x18000a3f1  cmp     [rsp+38h+arg_0], 0
0x18000a3f6  jz      short loc_18000A45F
0x18000a3f8  lea     rax, qword_180013290
0x18000a3ff  mov     [rsp+38h+var_18], rdi
0x18000a404  mov     [rsp+38h+arg_8], rax
0x18000a409  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x18000a410  mov     cs:qword_180013290, rax
0x18000a417  mov     cs:qword_180013298, 0
0x18000a422  mov     cs:byte_1800132A0, 0
0x18000a429  mov     cs:dword_1800132A4, 0
0x18000a433  lea     rax, ?__hInner@?1???0StaticHandle@UalPrintLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UalPrintLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000a43a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_5b247de46c1b9b2de92b67fa654160e8_@@CA@XZ; void (__cdecl *)()
0x18000a441  mov     cs:qword_1800132A8, rax
0x18000a448  call    atexit
0x18000a44d  lea     rcx, [rsp+38h+var_18]
0x18000a452  mov     [rsp+38h+var_10], 0
0x18000a45a  call    ??1Completer@?$static_lazy@VUalPrintLogging@@@details@wil@@QEAA@XZ; wil::details::static_lazy<UalPrintLogging>::Completer::~Completer(void)
0x18000a45f  mov     rax, [rsp+38h+arg_8]
0x18000a464  add     rsp, 30h
0x18000a468  pop     rdi
0x18000a469  retn
```
