# TlgHelper::Provider(void)

- ea: `0x18000f144`
- end: `0x18000f234`
- name: `?Provider@TlgHelper@@SAPEBU_tlgProvider_t@@XZ`
- size: `240`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `42`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003ca8`
- `0x180003e4c`
- `0x180003ebc`
- `0x180003f2c`
- `0x180003fbc`
- `0x18000404c`
- `0x1800040c0`
- `0x180004134`
- `0x1800041a8`
- `0x180004238`
- `0x1800042c8`
- `0x18000433c`
- `0x1800043b0`
- `0x180004424`
- `0x180004498`
- `0x18000450c`
- `0x180004580`
- `0x1800045f4`
- `0x180004668`
- `0x1800046dc`
- `0x180004750`
- `0x180008be0`
- `0x180009504`
- `0x180009f8c`
- `0x18000a1a8`
- `0x18000a7e4`
- `0x18000b014`
- `0x18000b3e0`
- `0x18000df2c`
- `0x18000e790`
- `0x18000e964`
- `0x1800114d0`
- `0x180012024`
- `0x1800121a0`
- `0x180013df0`
- `0x1800145d0`
- `0x180014cd0`
- `0x1800157f8`
- `0x18001e7fc`
- `0x18001e900`
- `0x18001f1f0`
- `0x18001f3c8`

## callees

- `0x180001950`
- `0x180002aec`
- `0x18000f144`
- `0x180024010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x18000f219`
- `KERNEL32!InitOnceComplete` at `0x18000f219`
- `KERNEL32!InitOnceBeginInitialize` at `0x18000f165`
- `KERNEL32!InitOnceBeginInitialize` at `0x18000f165`

## pseudocode

```c
const struct _tlgProvider_t *TlgHelper::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`TlgHelper::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_180030D30 = 0;
    dword_180030D3C = 0;
    v2 = &qword_180030D28;
    qword_180030D28 = (__int64)&TlgHelper::`vftable';
    byte_180030D38 = 0;
    CallbackContext = &`TlgHelper::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_27248ce03d41213a4b11ef93405cd787_::_lambda_invoker_cdecl_);
    qword_180030D30 = (__int64)CallbackContext;
    byte_180030D38 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_180030D3C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180030D28 + 8))(&qword_180030D28);
    InitOnceComplete(&`TlgHelper::Instance'::`2'::wrapper, 0, &qword_180030D28);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x18000f144  mov     rax, rsp
0x18000f147  sub     rsp, 28h
0x18000f14b  and     qword ptr [rax+10h], 0
0x18000f150  lea     r9, [rax+10h]; lpContext
0x18000f154  and     dword ptr [rax+8], 0
0x18000f158  lea     r8, [rax+8]; fPending
0x18000f15c  xor     edx, edx; dwFlags
0x18000f15e  lea     rcx, ?wrapper@?1??Instance@TlgHelper@@KAPEAV2@XZ@4V?$static_lazy@VTlgHelper@@@details@wil@@A; lpInitOnce
0x18000f165  call    cs:__imp_InitOnceBeginInitialize
0x18000f16c  nop     dword ptr [rax+rax+00h]
0x18000f171  test    eax, eax
0x18000f173  jz      loc_18000F225
0x18000f179  cmp     [rsp+28h+arg_0], 0
0x18000f17e  jz      loc_18000F225
0x18000f184  and     cs:qword_180030D30, 0
0x18000f18c  lea     rax, qword_180030D28
0x18000f193  and     cs:dword_180030D3C, 0
0x18000f19a  mov     [rsp+28h+arg_8], rax
0x18000f19f  lea     rax, ??_7TlgHelper@@6B@; const TlgHelper::`vftable'
0x18000f1a6  mov     cs:qword_180030D28, rax
0x18000f1ad  mov     cs:byte_180030D38, 0
0x18000f1b4  lea     rax, ?__hInner@?1???0StaticHandle@TlgHelper@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `TlgHelper::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000f1bb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_27248ce03d41213a4b11ef93405cd787_@@CA@XZ; void (__cdecl *)()
0x18000f1c2  mov     cs:CallbackContext, rax
0x18000f1c9  call    atexit
0x18000f1ce  mov     rcx, cs:CallbackContext; CallbackContext
0x18000f1d5  mov     cs:qword_180030D30, rcx
0x18000f1dc  mov     cs:byte_180030D38, 1
0x18000f1e3  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000f1e8  mov     rax, cs:qword_180030D28
0x18000f1ef  lea     rcx, qword_180030D28
0x18000f1f6  mov     cs:dword_180030D3C, 1
0x18000f200  mov     rax, [rax+8]
0x18000f204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f209  lea     r8, qword_180030D28; lpContext
0x18000f210  xor     edx, edx; dwFlags
0x18000f212  lea     rcx, ?wrapper@?1??Instance@TlgHelper@@KAPEAV2@XZ@4V?$static_lazy@VTlgHelper@@@details@wil@@A; lpInitOnce
0x18000f219  call    cs:__imp_InitOnceComplete
0x18000f220  nop     dword ptr [rax+rax+00h]
0x18000f225  mov     rax, [rsp+28h+arg_8]
0x18000f22a  mov     rax, [rax+8]
0x18000f22e  add     rsp, 28h
0x18000f232  retn
```
