# GetPackagedResourceResolvers(Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplication>,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>,Windows::Internal::StateRepository::IApplicationResourceResolver * *,Windows::Internal::StateRepository::IPackageResourceResolver * *)

- ea: `0x14000e5e4`
- end: `0x14000e827`
- name: `?GetPackagedResourceResolvers@@YAJV?$ComPtr@UIApplication@StateRepository@Internal@Windows@@@WRL@Microsoft@@V?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@23@PEAPEAUIApplicationResourceResolver@StateRepository@Internal@Windows@@PEAPEAUIPackageResourceResolver@678@@Z`
- size: `579`
- prototype: `__int64 __fastcall(__int64 *, __int64 *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000eee4`

## callees

- `0x14000e5e4`
- `0x14000e830`
- `0x14000e884`
- `0x140019514`
- `0x14001e050`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000e675`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000e6df`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000e675`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000e6df`

## string_xrefs

- `0x14000e68a`: `ds\security\services\lua\consentui\context.cpp`
- `0x14000e6f4`: `ds\security\services\lua\consentui\context.cpp`
- `0x14000e72c`: `ds\security\services\lua\consentui\context.cpp`
- `0x14000e763`: `ds\security\services\lua\consentui\context.cpp`

## pseudocode

```c
__int64 __fastcall GetPackagedResourceResolvers(__int64 *a1, __int64 *a2, _QWORD *a3, _QWORD *a4)
{
  __int64 v8; // rbx
  int ActivationFactory; // eax
  __int64 v10; // rbx
  int v11; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  wil *v19; // rcx
  unsigned int v20; // eax
  __int64 v21; // [rsp+20h] [rbp-78h] BYREF
  __int64 v22; // [rsp+28h] [rbp-70h] BYREF
  __int64 *v23; // [rsp+30h] [rbp-68h]
  __int64 *v24; // [rsp+38h] [rbp-60h]
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-58h] BYREF
  __int64 v26; // [rsp+58h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v23 = a1;
  v24 = a2;
  *a3 = 0;
  *a4 = 0;
  v22 = 0;
  v21 = 0;
  v26 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.ApplicationResourceResolver",
    0x3Du,
    0x3Cu);
  v8 = v26;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(&v22);
  ActivationFactory = RoGetActivationFactory(v8, &GUID_84463b2a_c88e_4597_b41f_17d3bf6486e9, &v22);
  try
  {
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x25D,
        (unsigned int)"ds\\security\\services\\lua\\consentui\\context.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v21);
    v26 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.PackageResourceResolver",
      0x39u,
      0x38u);
    v10 = v26;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(&v21);
    v11 = RoGetActivationFactory(v10, &GUID_cb4720b3_052a_4478_b348_29a7cf0d828e, &v21);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x25E,
        (unsigned int)"ds\\security\\services\\lua\\consentui\\context.cpp",
        (const char *)(unsigned int)v11,
        v21);
    v12 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v22 + 48LL))(v22, *a1, a3);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x260,
        (unsigned int)"ds\\security\\services\\lua\\consentui\\context.cpp",
        (const char *)(unsigned int)v12,
        v21);
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v21 + 48LL))(v21, *a2, a4);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x261,
        (unsigned int)"ds\\security\\services\\lua\\consentui\\context.cpp",
        (const char *)(unsigned int)v13,
        v21);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(&v21);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(&v22);
  }
  catch ( ... )
  {
    v19 = (wil *)&WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      v20 = wil::ResultFromCaughtException((wil *)&WPP_GLOBAL_Control);
      WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 23, WPP_bed9811735e730a365d52877ff824444_Traceguids, v20);
    }
    LODWORD(v21) = wil::ResultFromCaughtException(v19);
    v17 = *v23;
    if ( *v23 )
    {
      *v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = *v24;
    if ( *v24 )
    {
      *v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return (unsigned int)v21;
  }
  v14 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  v15 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x14000e5e4  mov     r11, rsp
0x14000e5e7  push    rbx
0x14000e5e8  push    rsi
0x14000e5e9  push    r12
0x14000e5eb  push    r14
0x14000e5ed  push    r15
0x14000e5ef  sub     rsp, 70h
0x14000e5f3  mov     rax, cs:__security_cookie
0x14000e5fa  xor     rax, rsp
0x14000e5fd  mov     [rsp+98h+var_38], rax
0x14000e602  mov     r12, r9
0x14000e605  mov     r15, r8
0x14000e608  mov     rsi, rdx
0x14000e60b  mov     r14, rcx
0x14000e60e  mov     [r11-68h], rcx
0x14000e612  mov     [r11-60h], rdx
0x14000e616  mov     qword ptr [r8], 0
0x14000e61d  mov     qword ptr [r9], 0
0x14000e624  mov     qword ptr [r11-70h], 0
0x14000e62c  mov     qword ptr [r11-78h], 0
0x14000e634  mov     qword ptr [r11-40h], 0
0x14000e63c  mov     r9d, 3Ch ; '<'; unsigned int
0x14000e642  lea     r8d, [r9+1]; unsigned int
0x14000e646  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_ApplicationResourceResolver@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x14000e64d  lea     rcx, [r11-58h]; hstringHeader
0x14000e651  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14000e656  nop
0x14000e657  mov     rbx, [rsp+98h+var_40]
0x14000e65c  lea     rcx, [rsp+98h+var_70]
0x14000e661  call    ?InternalRelease@?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(void)
0x14000e666  lea     r8, [rsp+98h+var_70]
0x14000e66b  lea     rdx, _GUID_84463b2a_c88e_4597_b41f_17d3bf6486e9
0x14000e672  mov     rcx, rbx
0x14000e675  call    cs:__imp_RoGetActivationFactory
0x14000e67b  mov     rcx, [rsp+98h]; this
0x14000e683  test    eax, eax
0x14000e685  jns     short loc_14000E69C
0x14000e687  mov     r9d, eax; char *
0x14000e68a  lea     r8, aDsSecurityServ; "ds\\security\\services\\lua\\consentui"...
0x14000e691  mov     edx, 25Dh; void *
0x14000e696  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000e69c  mov     [rsp+98h+var_40], 0
0x14000e6a5  mov     r9d, 38h ; '8'; unsigned int
0x14000e6ab  lea     r8d, [r9+1]; unsigned int
0x14000e6af  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageResourceResolver@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x14000e6b6  lea     rcx, [rsp+98h+hstringHeader]; hstringHeader
0x14000e6bb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14000e6c0  nop
0x14000e6c1  mov     rbx, [rsp+98h+var_40]
0x14000e6c6  lea     rcx, [rsp+98h+var_78]
0x14000e6cb  call    ?InternalRelease@?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(void)
0x14000e6d0  lea     r8, [rsp+98h+var_78]
0x14000e6d5  lea     rdx, _GUID_cb4720b3_052a_4478_b348_29a7cf0d828e
0x14000e6dc  mov     rcx, rbx
0x14000e6df  call    cs:__imp_RoGetActivationFactory
0x14000e6e5  mov     rcx, [rsp+98h]; this
0x14000e6ed  test    eax, eax
0x14000e6ef  jns     short loc_14000E706
0x14000e6f1  mov     r9d, eax; char *
0x14000e6f4  lea     r8, aDsSecurityServ; "ds\\security\\services\\lua\\consentui"...
0x14000e6fb  mov     edx, 25Eh; void *
0x14000e700  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000e706  mov     rcx, [rsp+98h+var_70]
0x14000e70b  mov     rax, [rcx]
0x14000e70e  mov     r8, r15
0x14000e711  mov     rdx, [r14]
0x14000e714  mov     rax, [rax+30h]
0x14000e718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e71d  mov     rcx, [rsp+98h]; this
0x14000e725  test    eax, eax
0x14000e727  jns     short loc_14000E73D
0x14000e729  mov     r9d, eax; char *
0x14000e72c  lea     r8, aDsSecurityServ; "ds\\security\\services\\lua\\consentui"...
0x14000e733  mov     edx, 260h; void *
0x14000e738  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000e73d  mov     rcx, [rsp+98h+var_78]
0x14000e742  mov     rax, [rcx]
0x14000e745  mov     r8, r12
0x14000e748  mov     rdx, [rsi]
0x14000e74b  mov     rax, [rax+30h]
0x14000e74f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e754  mov     rcx, [rsp+98h]; this
0x14000e75c  test    eax, eax
0x14000e75e  jns     short loc_14000E775
0x14000e760  mov     r9d, eax; char *
0x14000e763  lea     r8, aDsSecurityServ; "ds\\security\\services\\lua\\consentui"...
0x14000e76a  mov     edx, 261h; void *
0x14000e76f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000e775  lea     rcx, [rsp+98h+var_78]
0x14000e77a  call    ?InternalRelease@?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(void)
0x14000e77f  nop
0x14000e780  lea     rcx, [rsp+98h+var_70]
0x14000e785  call    ?InternalRelease@?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(void)
0x14000e78a  nop
0x14000e78b  mov     rcx, [r14]
0x14000e78e  test    rcx, rcx
0x14000e791  jz      short loc_14000E7A7
0x14000e793  mov     qword ptr [r14], 0
0x14000e79a  mov     rax, [rcx]
0x14000e79d  mov     rax, [rax+10h]
0x14000e7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e7a6  nop
0x14000e7a7  mov     rcx, [rsi]
0x14000e7aa  test    rcx, rcx
0x14000e7ad  jz      short loc_14000E7C3
0x14000e7af  mov     qword ptr [rsi], 0
0x14000e7b6  mov     rax, [rcx]
0x14000e7b9  mov     rax, [rax+10h]
0x14000e7bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e7c2  nop
0x14000e7c3  xor     eax, eax
0x14000e7c5  jmp     short loc_14000E80D
0x14000e7c7  mov     rax, [rsp+98h+var_68]
0x14000e7cc  mov     rcx, [rax]
0x14000e7cf  test    rcx, rcx
0x14000e7d2  jz      short loc_14000E7E8
0x14000e7d4  mov     qword ptr [rax], 0
0x14000e7db  mov     rax, [rcx]
0x14000e7de  mov     rax, [rax+10h]
0x14000e7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e7e7  nop
0x14000e7e8  mov     rax, [rsp+98h+var_60]
0x14000e7ed  mov     rcx, [rax]
0x14000e7f0  test    rcx, rcx
0x14000e7f3  jz      short loc_14000E809
0x14000e7f5  mov     qword ptr [rax], 0
0x14000e7fc  mov     rax, [rcx]
0x14000e7ff  mov     rax, [rax+10h]
0x14000e803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e808  nop
0x14000e809  mov     eax, dword ptr [rsp+98h+var_78]
0x14000e80d  mov     rcx, [rsp+98h+var_38]
0x14000e812  xor     rcx, rsp; StackCookie
0x14000e815  call    __security_check_cookie
0x14000e81a  add     rsp, 70h
0x14000e81e  pop     r15
0x14000e820  pop     r14
0x14000e822  pop     r12
0x14000e824  pop     rsi
0x14000e825  pop     rbx
0x14000e826  retn
```
