# wil::details::FeatureLogging::Instance(void)

- ea: `0x18001d30c`
- end: `0x18001d47a`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `366`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012c20`

## callees

- `0x18001d30c`
- `0x18002a3d0`
- `0x18002a85c`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001d452`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001d452`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001d34c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001d34c`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001d40b`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18001d40b`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001d423`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18001d423`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  _QWORD *v0; // rbx
  _QWORD *v1; // rdi
  bool v2; // zf
  ULONGLONG *v3; // r9
  WINBOOL v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 *v6; // [rsp+28h] [rbp-30h] BYREF
  GUID ProviderId; // [rsp+30h] [rbp-28h] BYREF

  v6 = 0;
  v5 = 0;
  if ( InitOnceBeginInitialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &v5, (LPVOID *)&v6) && v5 )
  {
    qword_1800AD600 = 0;
    v6 = &qword_1800AD5F8;
    qword_1800AD5F8 = (__int64)&DesktopShellHostExtensionsLogging::`vftable';
    byte_1800AD608 = 0;
    dword_1800AD60C = 0;
    CallbackContext = &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    v0 = CallbackContext;
    qword_1800AD600 = (__int64)CallbackContext;
    byte_1800AD608 = 1;
    v1 = (char *)CallbackContext + 32;
    v2 = *((_QWORD *)CallbackContext + 4) == 0;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( !v2 )
      __fastfail(5u);
    v3 = (ULONGLONG *)((char *)CallbackContext + 32);
    *((_QWORD *)CallbackContext + 5) = 0;
    v0[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v0, v3) )
      EventSetInformation(*v1, 2, v0[1], *(unsigned __int16 *)v0[1]);
    dword_1800AD60C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800AD5F8 + 8))(&qword_1800AD5F8);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_1800AD5F8);
  }
  return (struct wil::details::FeatureLogging *)v6;
}

```

## disassembly

```asm
0x18001d30c  mov     r11, rsp
0x18001d30f  mov     [r11+8], rbx
0x18001d313  mov     [r11+10h], rbp
0x18001d317  push    rdi
0x18001d318  sub     rsp, 50h
0x18001d31c  mov     rax, cs:__security_cookie
0x18001d323  xor     rax, rsp
0x18001d326  mov     [rsp+58h+var_18], rax
0x18001d32b  lea     r9, [r11-30h]; lpContext
0x18001d32f  mov     qword ptr [r11-30h], 0
0x18001d337  lea     r8, [r11-38h]; fPending
0x18001d33b  mov     [rsp+58h+var_38], 0
0x18001d343  xor     edx, edx; dwFlags
0x18001d345  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18001d34c  call    cs:__imp_InitOnceBeginInitialize
0x18001d352  test    eax, eax
0x18001d354  jz      loc_18001D458
0x18001d35a  cmp     [rsp+58h+var_38], 0
0x18001d35f  jz      loc_18001D458
0x18001d365  lea     rbp, qword_1800AD5F8
0x18001d36c  mov     cs:qword_1800AD600, 0
0x18001d377  lea     rax, ??_7DesktopShellHostExtensionsLogging@@6B@; const DesktopShellHostExtensionsLogging::`vftable'
0x18001d37e  mov     [rsp+58h+var_30], rbp
0x18001d383  mov     cs:qword_1800AD5F8, rax
0x18001d38a  mov     cs:byte_1800AD608, 0
0x18001d391  mov     cs:dword_1800AD60C, 0
0x18001d39b  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001d3a2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x18001d3a9  mov     cs:CallbackContext, rax
0x18001d3b0  call    atexit
0x18001d3b5  mov     rbx, cs:CallbackContext
0x18001d3bc  mov     cs:qword_1800AD600, rbx
0x18001d3c3  mov     cs:byte_1800AD608, 1
0x18001d3ca  mov     rax, [rbx+8]
0x18001d3ce  lea     rdi, [rbx+20h]
0x18001d3d2  cmp     qword ptr [rdi], 0
0x18001d3d6  movups  xmm0, xmmword ptr [rax-10h]
0x18001d3da  movdqu  xmmword ptr [rsp+58h+ProviderId.Data1], xmm0
0x18001d3e0  jz      short loc_18001D3E9
0x18001d3e2  mov     ecx, 5
0x18001d3e7  int     29h; Win8: RtlFailFast(ecx)
0x18001d3e9  mov     r9, rdi; RegHandle
0x18001d3ec  mov     qword ptr [rbx+28h], 0
0x18001d3f4  mov     r8, rbx; CallbackContext
0x18001d3f7  mov     qword ptr [rbx+30h], 0
0x18001d3ff  lea     rdx, _tlgEnableCallback; EnableCallback
0x18001d406  lea     rcx, [rsp+58h+ProviderId]; ProviderId
0x18001d40b  call    cs:__imp_EventRegister
0x18001d411  test    eax, eax
0x18001d413  jnz     short loc_18001D429
0x18001d415  mov     r8, [rbx+8]
0x18001d419  lea     edx, [rax+2]
0x18001d41c  mov     rcx, [rdi]
0x18001d41f  movzx   r9d, word ptr [r8]
0x18001d423  call    cs:__imp_EventSetInformation
0x18001d429  mov     rax, cs:qword_1800AD5F8
0x18001d430  mov     rcx, rbp
0x18001d433  mov     cs:dword_1800AD60C, 1
0x18001d43d  mov     rax, [rax+8]
0x18001d441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d446  mov     r8, rbp; lpContext
0x18001d449  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18001d450  xor     edx, edx; dwFlags
0x18001d452  call    cs:__imp_InitOnceComplete
0x18001d458  mov     rax, [rsp+58h+var_30]
0x18001d45d  mov     rcx, [rsp+58h+var_18]
0x18001d462  xor     rcx, rsp; StackCookie
0x18001d465  call    __security_check_cookie
0x18001d46a  mov     rbx, [rsp+58h+arg_0]
0x18001d46f  mov     rbp, [rsp+58h+arg_8]
0x18001d474  add     rsp, 50h
0x18001d478  pop     rdi
0x18001d479  retn
```
