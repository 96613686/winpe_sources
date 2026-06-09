# EduPrintProvLogging::Provider(void)

- ea: `0x14000cfac`
- end: `0x14000d05e`
- name: `?Provider@EduPrintProvLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000d20c`
- `0x14000ddb8`
- `0x14001191c`
- `0x140011f3c`
- `0x1400120b4`
- `0x1400122f0`
- `0x1400123e0`
- `0x140012754`
- `0x1400128fc`
- `0x140012ae0`

## callees

- `0x1400028c4`
- `0x14000cd88`
- `0x14000cfac`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000cfd7`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000cfd7`

## pseudocode

```c
const struct _tlgProvider_t *EduPrintProvLogging::Provider(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  WINBOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`EduPrintProvLogging::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`EduPrintProvLogging::Instance'::`2'::wrapper;
    v4 = &qword_14001D6B8;
    qword_14001D6B8 = (__int64)&EduPrintProvLogging::`vftable';
    qword_14001D6C0 = 0;
    byte_14001D6C8 = 0;
    dword_14001D6CC = 0;
    qword_14001D6D0 = (__int64)&`EduPrintProvLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_3fcc860ff4de8c9a475fe632501dcbf8_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<EduPrintProvLogging>::Completer::~Completer(&v1);
  }
  return (const struct _tlgProvider_t *)v4[1];
}

```

## disassembly

```asm
0x14000cfac  mov     rax, rsp
0x14000cfaf  push    rdi
0x14000cfb0  sub     rsp, 30h
0x14000cfb4  lea     rdi, ?wrapper@?1??Instance@EduPrintProvLogging@@KAPEAV2@XZ@4V?$static_lazy@VEduPrintProvLogging@@@details@wil@@A; wil::details::static_lazy<EduPrintProvLogging> `EduPrintProvLogging::Instance(void)'::`2'::wrapper
0x14000cfbb  mov     qword ptr [rax+10h], 0
0x14000cfc3  mov     rcx, rdi; lpInitOnce
0x14000cfc6  mov     dword ptr [rax+8], 0
0x14000cfcd  lea     r9, [rax+10h]; lpContext
0x14000cfd1  xor     edx, edx; dwFlags
0x14000cfd3  lea     r8, [rax+8]; fPending
0x14000cfd7  call    cs:__imp_InitOnceBeginInitialize
0x14000cfdd  test    eax, eax
0x14000cfdf  jz      short loc_14000D04F
0x14000cfe1  cmp     [rsp+38h+arg_0], 0
0x14000cfe6  jz      short loc_14000D04F
0x14000cfe8  lea     rax, qword_14001D6B8
0x14000cfef  mov     [rsp+38h+var_18], rdi
0x14000cff4  mov     [rsp+38h+arg_8], rax
0x14000cff9  lea     rax, ??_7EduPrintProvLogging@@6B@; const EduPrintProvLogging::`vftable'
0x14000d000  mov     cs:qword_14001D6B8, rax
0x14000d007  mov     cs:qword_14001D6C0, 0
0x14000d012  mov     cs:byte_14001D6C8, 0
0x14000d019  mov     cs:dword_14001D6CC, 0
0x14000d023  lea     rax, ?__hInner@?1???0StaticHandle@EduPrintProvLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `EduPrintProvLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14000d02a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_3fcc860ff4de8c9a475fe632501dcbf8_@@CA@XZ; void (__cdecl *)()
0x14000d031  mov     cs:qword_14001D6D0, rax
0x14000d038  call    atexit
0x14000d03d  lea     rcx, [rsp+38h+var_18]
0x14000d042  mov     [rsp+38h+var_10], 0
0x14000d04a  call    ??1Completer@?$static_lazy@VEduPrintProvLogging@@@details@wil@@QEAA@XZ; wil::details::static_lazy<EduPrintProvLogging>::Completer::~Completer(void)
0x14000d04f  mov     rax, [rsp+38h+arg_8]
0x14000d054  mov     rax, [rax+8]
0x14000d058  add     rsp, 30h
0x14000d05c  pop     rdi
0x14000d05d  retn
```
