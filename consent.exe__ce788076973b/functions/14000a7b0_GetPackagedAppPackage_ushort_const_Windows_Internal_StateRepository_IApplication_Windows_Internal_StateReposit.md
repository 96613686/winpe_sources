# GetPackagedAppPackage(ushort const *,Windows::Internal::StateRepository::IApplication * *,Windows::Internal::StateRepository::IPackage * *)

- ea: `0x14000a7b0`
- end: `0x14000aacf`
- name: `?GetPackagedAppPackage@@YAJPEBGPEAPEAUIApplication@StateRepository@Internal@Windows@@PEAPEAUIPackage@234@@Z`
- size: `799`
- prototype: `__int64 __fastcall(PCWSTR sourceString, struct Windows::Internal::StateRepository::IApplication **, struct Windows::Internal::StateRepository::IPackage **)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000eee4`

## callees

- `0x14000a7b0`
- `0x14000ddc4`
- `0x14000e884`
- `0x140010080`
- `0x140019514`
- `0x14001e050`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000a81c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000a8a9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000a9b0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000aaa3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000a81c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000a8a9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000a9b0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x14000aaa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a806`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a99a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a806`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000a99a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000a841`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000a8ce`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000a841`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x14000a8ce`
- `ntdll!RtlLengthSid` at `0x14000a91e`
- `ntdll!RtlLengthSid` at `0x14000a91e`

## string_xrefs

- `0x14000a856`: `ds\security\services\lua\consentui\context.cpp`
- `0x14000a8e3`: `ds\security\services\lua\consentui\context.cpp`
- `0x14000a948`: `ds\security\services\lua\consentui\context.cpp`
- `0x14000a9e2`: `ds\security\services\lua\consentui\context.cpp`
- `0x14000aa15`: `ds\security\services\lua\consentui\context.cpp`

## pseudocode

```c
__int64 __fastcall GetPackagedAppPackage(
        PCWSTR sourceString,
        struct Windows::Internal::StateRepository::IApplication **a2,
        struct Windows::Internal::StateRepository::IPackage **a3)
{
  HRESULT v6; // eax
  HSTRING v7; // rbx
  int ActivationFactory; // eax
  HRESULT v9; // eax
  HSTRING v10; // rbx
  int v11; // eax
  __int64 v12; // rsi
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64, __int64 *); // rdi
  __int64 v14; // rbx
  ULONG v15; // eax
  int v16; // eax
  _QWORD *v17; // rbx
  __int64 v18; // rdi
  unsigned __int64 v19; // rdx
  HRESULT v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // rcx
  void *v25; // rcx
  _QWORD *v26; // rcx
  int v28; // [rsp+20h] [rbp-98h]
  __int64 v29; // [rsp+30h] [rbp-88h] BYREF
  __int64 v30; // [rsp+38h] [rbp-80h] BYREF
  _QWORD *v31; // [rsp+40h] [rbp-78h] BYREF
  void *Block[2]; // [rsp+48h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-60h] BYREF
  HSTRING string; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  Block[1] = (void *)sourceString;
  *a2 = 0;
  *a3 = 0;
  v31 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &hstringHeader, &string);
  if ( v6 < 0 )
    RaiseException(v6, 1u, 0, 0);
  v7 = string;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(&v31);
  ActivationFactory = RoGetActivationFactory(v7, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v31);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x235,
      (unsigned int)"ds\\security\\services\\lua\\consentui\\context.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v28);
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(Block);
  v30 = 0;
  string = 0;
  v9 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.User", 0x25u, &hstringHeader, &string);
  if ( v9 < 0 )
    RaiseException(v9, 1u, 0, 0);
  v10 = string;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(&v30);
  v11 = RoGetActivationFactory(v10, &GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720, &v30);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x23A,
      (unsigned int)"ds\\security\\services\\lua\\consentui\\context.cpp",
      (const char *)(unsigned int)v11,
      v28);
  v29 = 0;
  v12 = v30;
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v30 + 144LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(&v29);
  v14 = *(_QWORD *)Block[0];
  v15 = RtlLengthSid(*(PSID *)Block[0]);
  v16 = v13(v12, v15, v14, &v29);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x23D,
      (unsigned int)"ds\\security\\services\\lua\\consentui\\context.cpp",
      (const char *)(unsigned int)v16,
      v28);
  v17 = v31;
  v18 = *v31;
  string = 0;
  v19 = -1;
  do
    ++v19;
  while ( sourceString[v19] );
  if ( v19 > 0xFFFFFFFF || (int)v19 + 1 < (unsigned int)v19 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    return (unsigned int)v29;
  }
  else
  {
    v20 = WindowsCreateStringReference(sourceString, v19, &hstringHeader, &string);
    if ( v20 < 0 )
      RaiseException(v20, 1u, 0, 0);
    v21 = (*(__int64 (__fastcall **)(_QWORD *, __int64, HSTRING, struct Windows::Internal::StateRepository::IApplication **))(v18 + 240))(
            v17,
            v29,
            string,
            a2);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x23F,
        (unsigned int)"ds\\security\\services\\lua\\consentui\\context.cpp",
        (const char *)(unsigned int)v21,
        v28);
    v22 = (*(__int64 (__fastcall **)(_QWORD, struct Windows::Internal::StateRepository::IPackage **))(*(_QWORD *)*a2 + 72LL))(
            *a2,
            a3);
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x241,
        (unsigned int)"ds\\security\\services\\lua\\consentui\\context.cpp",
        (const char *)(unsigned int)v22,
        v28);
    v23 = v29;
    if ( v29 )
    {
      v29 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = Block[0];
    Block[0] = 0;
    if ( v25 )
      operator delete(v25);
    v26 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x14000a7b0  mov     r11, rsp
0x14000a7b3  push    rbx
0x14000a7b4  push    rsi
0x14000a7b5  push    rdi
0x14000a7b6  push    r12
0x14000a7b8  push    r13
0x14000a7ba  push    r14
0x14000a7bc  push    r15
0x14000a7be  sub     rsp, 80h
0x14000a7c5  mov     rax, cs:__security_cookie
0x14000a7cc  xor     rax, rsp
0x14000a7cf  mov     [rsp+0B8h+var_40], rax
0x14000a7d4  mov     r12, r8
0x14000a7d7  mov     r15, rdx
0x14000a7da  mov     r14, rcx
0x14000a7dd  mov     [rsp+0B8h+var_68], rcx
0x14000a7e2  xor     r13d, r13d
0x14000a7e5  mov     [rdx], r13
0x14000a7e8  mov     [r8], r13
0x14000a7eb  mov     [r11-78h], r13
0x14000a7ef  mov     [r11-48h], r13
0x14000a7f3  lea     r9, [r11-48h]; string
0x14000a7f7  lea     r8, [r11-60h]; hstringHeader
0x14000a7fb  lea     edx, [r13+2Ch]; length
0x14000a7ff  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x14000a806  call    cs:__imp_WindowsCreateStringReference
0x14000a80c  test    eax, eax
0x14000a80e  jns     short loc_14000A823
0x14000a810  xor     r9d, r9d; lpArguments
0x14000a813  xor     r8d, r8d; nNumberOfArguments
0x14000a816  lea     edx, [r13+1]; dwExceptionFlags
0x14000a81a  mov     ecx, eax; dwExceptionCode
0x14000a81c  call    cs:__imp_RaiseException
0x14000a822  nop
0x14000a823  mov     rbx, [rsp+0B8h+string]
0x14000a828  lea     rcx, [rsp+0B8h+var_78]
0x14000a82d  call    ?InternalRelease@?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(void)
0x14000a832  lea     r8, [rsp+0B8h+var_78]
0x14000a837  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x14000a83e  mov     rcx, rbx
0x14000a841  call    cs:__imp_RoGetActivationFactory
0x14000a847  mov     rcx, [rsp+0B8h]; this
0x14000a84f  test    eax, eax
0x14000a851  jns     short loc_14000A868
0x14000a853  mov     r9d, eax; char *
0x14000a856  lea     r8, aDsSecurityServ; "ds\\security\\services\\lua\\consentui"...
0x14000a85d  mov     edx, 235h; void *
0x14000a862  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000a868  lea     rcx, [rsp+0B8h+Block]
0x14000a86d  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x14000a872  nop
0x14000a873  mov     [rsp+0B8h+var_80], r13
0x14000a878  mov     [rsp+0B8h+string], r13
0x14000a87d  lea     r9, [rsp+0B8h+string]; string
0x14000a882  lea     r8, [rsp+0B8h+hstringHeader]; hstringHeader
0x14000a887  mov     edx, 25h ; '%'; length
0x14000a88c  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_User@@3QBGB; "Windows.Internal.StateRepository.User"
0x14000a893  call    cs:__imp_WindowsCreateStringReference
0x14000a899  test    eax, eax
0x14000a89b  jns     short loc_14000A8B0
0x14000a89d  xor     r9d, r9d; lpArguments
0x14000a8a0  xor     r8d, r8d; nNumberOfArguments
0x14000a8a3  lea     edx, [r9+1]; dwExceptionFlags
0x14000a8a7  mov     ecx, eax; dwExceptionCode
0x14000a8a9  call    cs:__imp_RaiseException
0x14000a8af  nop
0x14000a8b0  mov     rbx, [rsp+0B8h+string]
0x14000a8b5  lea     rcx, [rsp+0B8h+var_80]
0x14000a8ba  call    ?InternalRelease@?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(void)
0x14000a8bf  lea     r8, [rsp+0B8h+var_80]
0x14000a8c4  lea     rdx, _GUID_84103ccb_2fd7_4d6c_962e_5d8582b4c720
0x14000a8cb  mov     rcx, rbx
0x14000a8ce  call    cs:__imp_RoGetActivationFactory
0x14000a8d4  mov     rcx, [rsp+0B8h]; this
0x14000a8dc  test    eax, eax
0x14000a8de  jns     short loc_14000A8F5
0x14000a8e0  mov     r9d, eax; char *
0x14000a8e3  lea     r8, aDsSecurityServ; "ds\\security\\services\\lua\\consentui"...
0x14000a8ea  mov     edx, 23Ah; void *
0x14000a8ef  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000a8f5  mov     [rsp+0B8h+var_88], r13
0x14000a8fa  mov     rsi, [rsp+0B8h+var_80]
0x14000a8ff  mov     rax, [rsi]
0x14000a902  mov     rdi, [rax+90h]
0x14000a909  lea     rcx, [rsp+0B8h+var_88]
0x14000a90e  call    ?InternalRelease@?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>::InternalRelease(void)
0x14000a913  mov     rcx, [rsp+0B8h+Block]
0x14000a918  mov     rbx, [rcx]
0x14000a91b  mov     rcx, rbx; Sid
0x14000a91e  call    cs:__imp_RtlLengthSid
0x14000a924  lea     r9, [rsp+0B8h+var_88]
0x14000a929  mov     r8, rbx
0x14000a92c  mov     edx, eax
0x14000a92e  mov     rcx, rsi
0x14000a931  mov     rax, rdi
0x14000a934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a939  mov     rcx, [rsp+0B8h]; this
0x14000a941  test    eax, eax
0x14000a943  jns     short loc_14000A959
0x14000a945  mov     r9d, eax; char *
0x14000a948  lea     r8, aDsSecurityServ; "ds\\security\\services\\lua\\consentui"...
0x14000a94f  mov     edx, 23Dh; void *
0x14000a954  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000a959  mov     rbx, [rsp+0B8h+var_78]
0x14000a95e  mov     rdi, [rbx]
0x14000a961  mov     [rsp+0B8h+string], r13
0x14000a966  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000a96a  inc     rdx; length
0x14000a96d  cmp     [r14+rdx*2], r13w
0x14000a972  jnz     short loc_14000A96A
0x14000a974  mov     eax, 0FFFFFFFFh
0x14000a979  cmp     rdx, rax
0x14000a97c  ja      loc_14000AA94
0x14000a982  lea     eax, [rdx+1]
0x14000a985  cmp     eax, edx
0x14000a987  jb      loc_14000AA94
0x14000a98d  lea     r9, [rsp+0B8h+string]; string
0x14000a992  lea     r8, [rsp+0B8h+hstringHeader]; hstringHeader
0x14000a997  mov     rcx, r14; sourceString
0x14000a99a  call    cs:__imp_WindowsCreateStringReference
0x14000a9a0  test    eax, eax
0x14000a9a2  jns     short loc_14000A9B7
0x14000a9a4  xor     r9d, r9d; lpArguments
0x14000a9a7  xor     r8d, r8d; nNumberOfArguments
0x14000a9aa  lea     edx, [r9+1]; dwExceptionFlags
0x14000a9ae  mov     ecx, eax; dwExceptionCode
0x14000a9b0  call    cs:__imp_RaiseException
0x14000a9b6  nop
0x14000a9b7  mov     r9, r15
0x14000a9ba  mov     r8, [rsp+0B8h+string]
0x14000a9bf  mov     rdx, [rsp+0B8h+var_88]
0x14000a9c4  mov     rcx, rbx
0x14000a9c7  mov     rax, [rdi+0F0h]
0x14000a9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a9d3  mov     rcx, [rsp+0B8h]; this
0x14000a9db  test    eax, eax
0x14000a9dd  jns     short loc_14000A9F4
0x14000a9df  mov     r9d, eax; char *
0x14000a9e2  lea     r8, aDsSecurityServ; "ds\\security\\services\\lua\\consentui"...
0x14000a9e9  mov     edx, 23Fh; void *
0x14000a9ee  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000a9f4  mov     rcx, [r15]
0x14000a9f7  mov     rax, [rcx]
0x14000a9fa  mov     rdx, r12
0x14000a9fd  mov     rax, [rax+48h]
0x14000aa01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa06  mov     rcx, [rsp+0B8h]; this
0x14000aa0e  test    eax, eax
0x14000aa10  jns     short loc_14000AA27
0x14000aa12  mov     r9d, eax; char *
0x14000aa15  lea     r8, aDsSecurityServ; "ds\\security\\services\\lua\\consentui"...
0x14000aa1c  mov     edx, 241h; void *
0x14000aa21  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000aa27  mov     rcx, [rsp+0B8h+var_88]
0x14000aa2c  test    rcx, rcx
0x14000aa2f  jz      short loc_14000AA43
0x14000aa31  mov     [rsp+0B8h+var_88], r13
0x14000aa36  mov     rax, [rcx]
0x14000aa39  mov     rax, [rax+10h]
0x14000aa3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa42  nop
0x14000aa43  mov     rcx, [rsp+0B8h+var_80]
0x14000aa48  test    rcx, rcx
0x14000aa4b  jz      short loc_14000AA5F
0x14000aa4d  mov     [rsp+0B8h+var_80], r13
0x14000aa52  mov     rax, [rcx]
0x14000aa55  mov     rax, [rax+10h]
0x14000aa59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa5e  nop
0x14000aa5f  mov     rcx, [rsp+0B8h+Block]; Block
0x14000aa64  mov     [rsp+0B8h+Block], r13
0x14000aa69  test    rcx, rcx
0x14000aa6c  jz      short loc_14000AA74
0x14000aa6e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000aa73  nop
0x14000aa74  mov     rcx, [rsp+0B8h+var_78]
0x14000aa79  test    rcx, rcx
0x14000aa7c  jz      short loc_14000AA90
0x14000aa7e  mov     [rsp+0B8h+var_78], r13
0x14000aa83  mov     rax, [rcx]
0x14000aa86  mov     rax, [rax+10h]
0x14000aa8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa8f  nop
0x14000aa90  xor     eax, eax
0x14000aa92  jmp     short loc_14000AAAE
0x14000aa94  xor     r9d, r9d; lpArguments
0x14000aa97  xor     r8d, r8d; nNumberOfArguments
0x14000aa9a  lea     edx, [r9+1]; dwExceptionFlags
0x14000aa9e  mov     ecx, 80070216h; dwExceptionCode
0x14000aaa3  call    cs:__imp_RaiseException
0x14000aaa9  nop
0x14000aaaa  mov     eax, dword ptr [rsp+0B8h+var_88]
0x14000aaae  mov     rcx, [rsp+0B8h+var_40]
0x14000aab3  xor     rcx, rsp; StackCookie
0x14000aab6  call    __security_check_cookie
0x14000aabb  add     rsp, 80h
0x14000aac2  pop     r15
0x14000aac4  pop     r14
0x14000aac6  pop     r13
0x14000aac8  pop     r12
0x14000aaca  pop     rdi
0x14000aacb  pop     rsi
0x14000aacc  pop     rbx
0x14000aacd  retn
```
