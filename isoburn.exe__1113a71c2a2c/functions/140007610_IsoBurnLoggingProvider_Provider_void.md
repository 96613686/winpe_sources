# IsoBurnLoggingProvider::Provider(void)

- ea: `0x140007610`
- end: `0x1400076c2`
- name: `?Provider@IsoBurnLoggingProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003798`
- `0x140007170`
- `0x1400086e4`
- `0x1400089a0`
- `0x140008b80`

## callees

- `0x140002220`
- `0x140003ae4`
- `0x140007610`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x14000763b`
- `KERNEL32!InitOnceBeginInitialize` at `0x14000763b`

## pseudocode

```c
const struct _tlgProvider_t *IsoBurnLoggingProvider::Provider(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`IsoBurnLoggingProvider::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`IsoBurnLoggingProvider::Instance'::`2'::wrapper;
    v4 = &qword_140016798;
    qword_140016798 = (__int64)&IsoBurnLoggingProvider::`vftable';
    qword_1400167A0 = 0;
    byte_1400167A8 = 0;
    dword_1400167AC = 0;
    qword_1400167B0 = (__int64)&`IsoBurnLoggingProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_e45a734b8097d77559c54153451e4bfa_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<IsoBurnLoggingProvider>::Completer::~Completer(&v1);
  }
  return (const struct _tlgProvider_t *)v4[1];
}

```

## disassembly

```asm
0x140007610  mov     rax, rsp
0x140007613  push    rdi
0x140007614  sub     rsp, 30h
0x140007618  lea     rdi, ?wrapper@?1??Instance@IsoBurnLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VIsoBurnLoggingProvider@@@details@wil@@A; wil::details::static_lazy<IsoBurnLoggingProvider> `IsoBurnLoggingProvider::Instance(void)'::`2'::wrapper
0x14000761f  mov     qword ptr [rax+10h], 0
0x140007627  mov     rcx, rdi; lpInitOnce
0x14000762a  mov     dword ptr [rax+8], 0
0x140007631  lea     r9, [rax+10h]; lpContext
0x140007635  xor     edx, edx; dwFlags
0x140007637  lea     r8, [rax+8]; fPending
0x14000763b  call    cs:__imp_InitOnceBeginInitialize
0x140007641  test    eax, eax
0x140007643  jz      short loc_1400076B3
0x140007645  cmp     [rsp+38h+arg_0], 0
0x14000764a  jz      short loc_1400076B3
0x14000764c  lea     rax, qword_140016798
0x140007653  mov     [rsp+38h+var_18], rdi
0x140007658  mov     [rsp+38h+arg_8], rax
0x14000765d  lea     rax, ??_7IsoBurnLoggingProvider@@6B@; const IsoBurnLoggingProvider::`vftable'
0x140007664  mov     cs:qword_140016798, rax
0x14000766b  mov     cs:qword_1400167A0, 0
0x140007676  mov     cs:byte_1400167A8, 0
0x14000767d  mov     cs:dword_1400167AC, 0
0x140007687  lea     rax, ?__hInner@?1???0StaticHandle@IsoBurnLoggingProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `IsoBurnLoggingProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14000768e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_e45a734b8097d77559c54153451e4bfa_@@CA@XZ; void (__cdecl *)()
0x140007695  mov     cs:qword_1400167B0, rax
0x14000769c  call    atexit
0x1400076a1  lea     rcx, [rsp+38h+var_18]
0x1400076a6  mov     [rsp+38h+var_10], 0
0x1400076ae  call    ??1Completer@?$static_lazy@VIsoBurnLoggingProvider@@@details@wil@@QEAA@XZ; wil::details::static_lazy<IsoBurnLoggingProvider>::Completer::~Completer(void)
0x1400076b3  mov     rax, [rsp+38h+arg_8]
0x1400076b8  mov     rax, [rax+8]
0x1400076bc  add     rsp, 30h
0x1400076c0  pop     rdi
0x1400076c1  retn
```
