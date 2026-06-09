# MS3DPrintShellExtension::Provider(void)

- ea: `0x180007c04`
- end: `0x180007cb6`
- name: `?Provider@MS3DPrintShellExtension@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800052b8`
- `0x1800075a0`
- `0x180008cf0`
- `0x180008e98`
- `0x180009070`

## callees

- `0x1800022dc`
- `0x1800054c4`
- `0x180007c04`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x180007c2f`
- `KERNEL32!InitOnceBeginInitialize` at `0x180007c2f`

## pseudocode

```c
const struct _tlgProvider_t *MS3DPrintShellExtension::Provider(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`MS3DPrintShellExtension::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`MS3DPrintShellExtension::Instance'::`2'::wrapper;
    v4 = &qword_180010448;
    qword_180010448 = (__int64)&MS3DPrintShellExtension::`vftable';
    qword_180010450 = 0;
    byte_180010458 = 0;
    dword_18001045C = 0;
    qword_180010460 = (__int64)&`MS3DPrintShellExtension::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_7b28c4f55a532f5dcff12964be203562_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<MS3DPrintShellExtension>::Completer::~Completer(&v1);
  }
  return (const struct _tlgProvider_t *)v4[1];
}

```

## disassembly

```asm
0x180007c04  mov     rax, rsp
0x180007c07  push    rdi
0x180007c08  sub     rsp, 30h
0x180007c0c  lea     rdi, ?wrapper@?1??Instance@MS3DPrintShellExtension@@KAPEAV2@XZ@4V?$static_lazy@VMS3DPrintShellExtension@@@details@wil@@A; wil::details::static_lazy<MS3DPrintShellExtension> `MS3DPrintShellExtension::Instance(void)'::`2'::wrapper
0x180007c13  mov     qword ptr [rax+10h], 0
0x180007c1b  mov     rcx, rdi; lpInitOnce
0x180007c1e  mov     dword ptr [rax+8], 0
0x180007c25  lea     r9, [rax+10h]; lpContext
0x180007c29  xor     edx, edx; dwFlags
0x180007c2b  lea     r8, [rax+8]; fPending
0x180007c2f  call    cs:__imp_InitOnceBeginInitialize
0x180007c35  test    eax, eax
0x180007c37  jz      short loc_180007CA7
0x180007c39  cmp     [rsp+38h+arg_0], 0
0x180007c3e  jz      short loc_180007CA7
0x180007c40  lea     rax, qword_180010448
0x180007c47  mov     [rsp+38h+var_18], rdi
0x180007c4c  mov     [rsp+38h+arg_8], rax
0x180007c51  lea     rax, ??_7MS3DPrintShellExtension@@6B@; const MS3DPrintShellExtension::`vftable'
0x180007c58  mov     cs:qword_180010448, rax
0x180007c5f  mov     cs:qword_180010450, 0
0x180007c6a  mov     cs:byte_180010458, 0
0x180007c71  mov     cs:dword_18001045C, 0
0x180007c7b  lea     rax, ?__hInner@?1???0StaticHandle@MS3DPrintShellExtension@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MS3DPrintShellExtension::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180007c82  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_7b28c4f55a532f5dcff12964be203562_@@CA@XZ; void (__cdecl *)()
0x180007c89  mov     cs:qword_180010460, rax
0x180007c90  call    atexit
0x180007c95  lea     rcx, [rsp+38h+var_18]
0x180007c9a  mov     [rsp+38h+var_10], 0
0x180007ca2  call    ??1Completer@?$static_lazy@VMS3DPrintShellExtension@@@details@wil@@QEAA@XZ; wil::details::static_lazy<MS3DPrintShellExtension>::Completer::~Completer(void)
0x180007ca7  mov     rax, [rsp+38h+arg_8]
0x180007cac  mov     rax, [rax+8]
0x180007cb0  add     rsp, 30h
0x180007cb4  pop     rdi
0x180007cb5  retn
```
