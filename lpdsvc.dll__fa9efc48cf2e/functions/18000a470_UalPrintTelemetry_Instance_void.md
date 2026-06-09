# UalPrintTelemetry::Instance(void)

- ea: `0x18000a470`
- end: `0x18000a544`
- name: `?Instance@UalPrintTelemetry@@KAPEAV1@XZ`
- size: `212`
- prototype: `struct UalPrintTelemetry *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a89c`
- `0x18000a9a4`

## callees

- `0x1800021c4`
- `0x18000a3bc`
- `0x18000a470`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a498`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000a498`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a533`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000a533`

## pseudocode

```c
struct UalPrintTelemetry *UalPrintTelemetry::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`UalPrintTelemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_1800132C0 = 0;
    qword_1800132B8 = (__int64)&wil::TraceLoggingProvider::`vftable';
    v2 = &qword_1800132B8;
    byte_1800132C8 = 0;
    dword_1800132CC = 0;
    atexit(_lambda_7bee68cf4190d4b9aabe7a3df845d730_::_lambda_invoker_cdecl_);
    qword_1800132C0 = *((_QWORD *)UalPrintLogging::Instance() + 1);
    byte_1800132C8 = 0;
    dword_1800132CC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800132B8 + 8))(&qword_1800132B8);
    InitOnceComplete(&`UalPrintTelemetry::Instance'::`2'::wrapper, 0, &qword_1800132B8);
  }
  return (struct UalPrintTelemetry *)v2;
}

```

## disassembly

```asm
0x18000a470  mov     rax, rsp
0x18000a473  push    rbx
0x18000a474  sub     rsp, 20h
0x18000a478  lea     r9, [rax+10h]; lpContext
0x18000a47c  mov     qword ptr [rax+10h], 0
0x18000a484  lea     r8, [rax+8]; fPending
0x18000a488  mov     dword ptr [rax+8], 0
0x18000a48f  xor     edx, edx; dwFlags
0x18000a491  lea     rcx, ?wrapper@?1??Instance@UalPrintTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUalPrintTelemetry@@@details@wil@@A; lpInitOnce
0x18000a498  call    cs:__imp_InitOnceBeginInitialize
0x18000a49e  test    eax, eax
0x18000a4a0  jz      loc_18000A539
0x18000a4a6  cmp     [rsp+28h+arg_0], 0
0x18000a4ab  jz      loc_18000A539
0x18000a4b1  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x18000a4b8  mov     cs:qword_1800132C0, 0
0x18000a4c3  lea     rbx, qword_1800132B8
0x18000a4ca  mov     cs:qword_1800132B8, rax
0x18000a4d1  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_7bee68cf4190d4b9aabe7a3df845d730_@@CA@XZ; void (__cdecl *)()
0x18000a4d8  mov     [rsp+28h+arg_8], rbx
0x18000a4dd  mov     cs:byte_1800132C8, 0
0x18000a4e4  mov     cs:dword_1800132CC, 0
0x18000a4ee  call    atexit
0x18000a4f3  call    ?Instance@UalPrintLogging@@KAPEAV1@XZ; UalPrintLogging::Instance(void)
0x18000a4f8  mov     rcx, rbx
0x18000a4fb  mov     rdx, [rax+8]
0x18000a4ff  mov     rax, cs:qword_1800132B8
0x18000a506  mov     cs:qword_1800132C0, rdx
0x18000a50d  mov     cs:byte_1800132C8, 0
0x18000a514  mov     cs:dword_1800132CC, 1
0x18000a51e  mov     rax, [rax+8]
0x18000a522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a527  mov     r8, rbx; lpContext
0x18000a52a  lea     rcx, ?wrapper@?1??Instance@UalPrintTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUalPrintTelemetry@@@details@wil@@A; lpInitOnce
0x18000a531  xor     edx, edx; dwFlags
0x18000a533  call    cs:__imp_InitOnceComplete
0x18000a539  mov     rax, [rsp+28h+arg_8]
0x18000a53e  add     rsp, 20h
0x18000a542  pop     rbx
0x18000a543  retn
```
