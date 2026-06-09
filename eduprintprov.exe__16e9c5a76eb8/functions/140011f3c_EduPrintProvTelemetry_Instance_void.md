# EduPrintProvTelemetry::Instance(void)

- ea: `0x140011f3c`
- end: `0x14001200c`
- name: `?Instance@EduPrintProvTelemetry@@KAPEAV1@XZ`
- size: `208`
- prototype: `struct EduPrintProvTelemetry *(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140011470`
- `0x140011bb0`

## callees

- `0x1400028c4`
- `0x14000cfac`
- `0x140011f3c`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140011f64`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140011f64`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140011ffb`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140011ffb`

## pseudocode

```c
struct EduPrintProvTelemetry *EduPrintProvTelemetry::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`EduPrintProvTelemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_14001D6F0 = 0;
    qword_14001D6E8 = (__int64)&EduPrintProvTelemetry::`vftable';
    v2 = &qword_14001D6E8;
    byte_14001D6F8 = 0;
    dword_14001D6FC = 0;
    atexit(_lambda_e3c54e0f5933bb501bcd21460935fb3a_::_lambda_invoker_cdecl_);
    qword_14001D6F0 = (__int64)EduPrintProvLogging::Provider();
    byte_14001D6F8 = 0;
    dword_14001D6FC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_14001D6E8 + 8))(&qword_14001D6E8);
    InitOnceComplete(&`EduPrintProvTelemetry::Instance'::`2'::wrapper, 0, &qword_14001D6E8);
  }
  return (struct EduPrintProvTelemetry *)v2;
}

```

## disassembly

```asm
0x140011f3c  mov     rax, rsp
0x140011f3f  push    rbx
0x140011f40  sub     rsp, 20h
0x140011f44  lea     r9, [rax+10h]; lpContext
0x140011f48  mov     qword ptr [rax+10h], 0
0x140011f50  lea     r8, [rax+8]; fPending
0x140011f54  mov     dword ptr [rax+8], 0
0x140011f5b  xor     edx, edx; dwFlags
0x140011f5d  lea     rcx, ?wrapper@?1??Instance@EduPrintProvTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VEduPrintProvTelemetry@@@details@wil@@A; lpInitOnce
0x140011f64  call    cs:__imp_InitOnceBeginInitialize
0x140011f6a  test    eax, eax
0x140011f6c  jz      loc_140012001
0x140011f72  cmp     [rsp+28h+arg_0], 0
0x140011f77  jz      loc_140012001
0x140011f7d  lea     rax, ??_7EduPrintProvTelemetry@@6B@; const EduPrintProvTelemetry::`vftable'
0x140011f84  mov     cs:qword_14001D6F0, 0
0x140011f8f  lea     rbx, qword_14001D6E8
0x140011f96  mov     cs:qword_14001D6E8, rax
0x140011f9d  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_e3c54e0f5933bb501bcd21460935fb3a_@@CA@XZ; void (__cdecl *)()
0x140011fa4  mov     [rsp+28h+arg_8], rbx
0x140011fa9  mov     cs:byte_14001D6F8, 0
0x140011fb0  mov     cs:dword_14001D6FC, 0
0x140011fba  call    atexit
0x140011fbf  call    ?Provider@EduPrintProvLogging@@SAPEBU_tlgProvider_t@@XZ; EduPrintProvLogging::Provider(void)
0x140011fc4  mov     cs:qword_14001D6F0, rax
0x140011fcb  mov     rcx, rbx
0x140011fce  mov     rax, cs:qword_14001D6E8
0x140011fd5  mov     cs:byte_14001D6F8, 0
0x140011fdc  mov     cs:dword_14001D6FC, 1
0x140011fe6  mov     rax, [rax+8]
0x140011fea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011fef  mov     r8, rbx; lpContext
0x140011ff2  lea     rcx, ?wrapper@?1??Instance@EduPrintProvTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VEduPrintProvTelemetry@@@details@wil@@A; lpInitOnce
0x140011ff9  xor     edx, edx; dwFlags
0x140011ffb  call    cs:__imp_InitOnceComplete
0x140012001  mov     rax, [rsp+28h+arg_8]
0x140012006  add     rsp, 20h
0x14001200a  pop     rbx
0x14001200b  retn
```
