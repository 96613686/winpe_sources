# wil::details::FeatureLogging::IsEnabled(uchar,unsigned __int64)

- ea: `0x18000e1f0`
- end: `0x18000e37f`
- name: `?IsEnabled@FeatureLogging@details@wil@@SA_NE_K@Z`
- size: `399`
- prototype: `bool __fastcall(unsigned __int8, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012c20`

## callees

- `0x18000e1f0`
- `0x18002a3d0`
- `0x18002a85c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e329`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e329`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e226`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e226`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000e2df`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000e2df`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000e2fa`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000e2fa`

## pseudocode

```c
bool __fastcall wil::details::FeatureLogging::IsEnabled()
{
  _QWORD *v0; // rbx
  ULONGLONG *v1; // r9
  _DWORD *v2; // rax
  WINBOOL fPending; // [rsp+20h] [rbp-38h] BYREF
  LPVOID Context; // [rsp+28h] [rbp-30h] BYREF
  GUID ProviderId; // [rsp+30h] [rbp-28h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &fPending, &Context)
    && fPending )
  {
    Context = &qword_1800AD5F8;
    qword_1800AD600 = 0;
    byte_1800AD608 = 0;
    dword_1800AD60C = 0;
    qword_1800AD5F8 = (__int64)&DesktopShellHostExtensionsLogging::`vftable';
    CallbackContext = &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    v0 = CallbackContext;
    qword_1800AD600 = (__int64)CallbackContext;
    byte_1800AD608 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    v1 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v0[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v0, v1) )
      EventSetInformation(v0[4], 2, v0[1], *(unsigned __int16 *)v0[1]);
    dword_1800AD60C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800AD5F8 + 8))(&qword_1800AD5F8);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_1800AD5F8);
  }
  v2 = (_DWORD *)*((_QWORD *)Context + 1);
  return v2 && *v2;
}

```

## disassembly

```asm
0x18000e1f0  sub     rsp, 58h
0x18000e1f4  mov     rax, cs:__security_cookie
0x18000e1fb  xor     rax, rsp
0x18000e1fe  mov     [rsp+58h+var_18], rax
0x18000e203  mov     [rsp+58h+arg_10], rsi
0x18000e208  lea     r9, [rsp+58h+Context]; lpContext
0x18000e20d  xor     esi, esi
0x18000e20f  lea     r8, [rsp+58h+fPending]; fPending
0x18000e214  xor     edx, edx; dwFlags
0x18000e216  mov     [rsp+58h+Context], rsi
0x18000e21b  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18000e222  mov     [rsp+58h+fPending], esi
0x18000e226  call    cs:__imp_InitOnceBeginInitialize
0x18000e22c  test    eax, eax
0x18000e22e  jz      loc_18000E33E
0x18000e234  cmp     [rsp+58h+fPending], esi
0x18000e238  jz      loc_18000E33E
0x18000e23e  mov     [rsp+58h+arg_0], rbx
0x18000e243  lea     rax, ??_7DesktopShellHostExtensionsLogging@@6B@; const DesktopShellHostExtensionsLogging::`vftable'
0x18000e24a  mov     [rsp+58h+arg_8], rbp
0x18000e24f  lea     rbp, qword_1800AD5F8
0x18000e256  mov     [rsp+58h+Context], rbp
0x18000e25b  mov     [rsp+58h+var_8], rdi
0x18000e260  mov     cs:qword_1800AD600, rsi
0x18000e267  mov     cs:byte_1800AD608, sil
0x18000e26e  mov     cs:dword_1800AD60C, esi
0x18000e274  mov     cs:qword_1800AD5F8, rax
0x18000e27b  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000e282  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x18000e289  mov     cs:CallbackContext, rax
0x18000e290  call    atexit
0x18000e295  mov     rbx, cs:CallbackContext
0x18000e29c  mov     cs:qword_1800AD600, rbx
0x18000e2a3  mov     cs:byte_1800AD608, 1
0x18000e2aa  mov     rax, [rbx+8]
0x18000e2ae  movups  xmm0, xmmword ptr [rax-10h]
0x18000e2b2  movups  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x18000e2b7  cmp     [rbx+20h], rsi
0x18000e2bb  jz      short loc_18000E2C4
0x18000e2bd  mov     ecx, 5
0x18000e2c2  int     29h; Win8: RtlFailFast(ecx)
0x18000e2c4  lea     r9, [rbx+20h]; RegHandle
0x18000e2c8  mov     [rbx+28h], rsi
0x18000e2cc  mov     r8, rbx; CallbackContext
0x18000e2cf  mov     [rbx+30h], rsi
0x18000e2d3  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000e2da  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x18000e2df  call    cs:__imp_EventRegister
0x18000e2e5  test    eax, eax
0x18000e2e7  jnz     short loc_18000E300
0x18000e2e9  mov     r8, [rbx+8]
0x18000e2ed  mov     edx, 2
0x18000e2f2  mov     rcx, [rbx+20h]
0x18000e2f6  movzx   r9d, word ptr [r8]
0x18000e2fa  call    cs:__imp_EventSetInformation
0x18000e300  mov     rax, cs:qword_1800AD5F8
0x18000e307  mov     rcx, rbp
0x18000e30a  mov     cs:dword_1800AD60C, 1
0x18000e314  mov     rax, [rax+8]
0x18000e318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e31d  mov     r8, rbp; lpContext
0x18000e320  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18000e327  xor     edx, edx; dwFlags
0x18000e329  call    cs:__imp_InitOnceComplete
0x18000e32f  mov     rdi, [rsp+58h+var_8]
0x18000e334  mov     rbp, [rsp+58h+arg_8]
0x18000e339  mov     rbx, [rsp+58h+arg_0]
0x18000e33e  mov     rax, [rsp+58h+Context]
0x18000e343  mov     rsi, [rsp+58h+arg_10]
0x18000e348  mov     rax, [rax+8]
0x18000e34c  test    rax, rax
0x18000e34f  jz      short loc_18000E36B
0x18000e351  mov     eax, [rax]
0x18000e353  test    eax, eax
0x18000e355  jz      short loc_18000E36B
0x18000e357  mov     al, 1
0x18000e359  mov     rcx, [rsp+58h+var_18]
0x18000e35e  xor     rcx, rsp; StackCookie
0x18000e361  call    __security_check_cookie
0x18000e366  add     rsp, 58h
0x18000e36a  retn
0x18000e36b  xor     al, al
0x18000e36d  mov     rcx, [rsp+58h+var_18]
0x18000e372  xor     rcx, rsp; StackCookie
0x18000e375  call    __security_check_cookie
0x18000e37a  add     rsp, 58h
0x18000e37e  retn
```
