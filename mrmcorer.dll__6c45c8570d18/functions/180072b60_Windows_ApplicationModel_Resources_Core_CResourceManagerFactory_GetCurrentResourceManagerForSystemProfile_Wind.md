# Windows::ApplicationModel::Resources::Core::CResourceManagerFactory::GetCurrentResourceManagerForSystemProfile(Windows::ApplicationModel::Resources::Core::IResourceManager * *)

- ea: `0x180072b60`
- end: `0x180072fe0`
- name: `?GetCurrentResourceManagerForSystemProfile@CResourceManagerFactory@Core@Resources@ApplicationModel@Windows@@UEAAJPEAPEAUIResourceManager@2345@@Z`
- size: `1152`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Resources::Core::CResourceManagerFactory *__hidden this, struct IResourceManager **)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000892c`
- `0x18000a070`
- `0x18000a0d0`
- `0x18000af60`
- `0x18000b46c`
- `0x18002c8d0`
- `0x180034d84`
- `0x1800364a8`
- `0x1800371a8`
- `0x180052d2c`
- `0x180072b08`
- `0x180072b60`
- `0x1800731d8`
- `0x180083ad4`
- `0x1800862f0`
- `0x1800867dc`
- `0x1800c5010`

## import_xrefs

- `KERNELBASE!GetCurrentPackageFullName` at `0x180072c9a`
- `KERNELBASE!GetCurrentPackageFullName` at `0x180072c9a`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180072b9e`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180072b9e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180072c5c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180072c5c`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180072dc8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateErrorW` at `0x180072dc8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180072e4f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180072e95`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180072e4f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180072e95`

## string_xrefs

- `0x180072d4e`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x180072dd5`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x180072df7`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x180072e5c`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x180072ea2`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x180072f00`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`
- `0x180072fac`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceManagerFactory::GetCurrentResourceManagerForSystemProfile(
        Windows::ApplicationModel::Resources::Core::CResourceManagerFactory *this,
        struct IResourceManager **a2)
{
  char MrtSharedObjectState; // bl
  struct IResourceManager *v4; // rbx
  struct IResourceManager *v5; // rcx
  struct IResourceManager *v6; // rax
  struct Windows::ApplicationModel::Resources::Core::CResourceManager *v7; // rcx
  unsigned int v8; // ebx
  Windows::ApplicationModel::Resources::Core::CResourceManagerFactory *v11; // rcx
  Microsoft::Resources::Runtime::CResourceManagerInternal *v12; // rax
  Microsoft::Resources::Runtime::CResourceManagerInternal *v13; // rdi
  int v14; // eax
  int v15; // eax
  Windows::ApplicationModel::Resources::Core::CResourceManagerFactory *v16; // rcx
  int v17; // eax
  struct IResourceManager *v18; // rcx
  struct Windows::ApplicationModel::Resources::Core::CResourceManager *v19; // rcx
  struct IResourceManager *v20; // rcx
  struct Windows::ApplicationModel::Resources::Core::CResourceManager *v21; // rcx
  struct IResourceManager *v22; // rcx
  struct IResourceManager *v23; // rcx
  struct Windows::ApplicationModel::Resources::Core::CResourceManager *v24; // rcx
  unsigned int v25; // edx
  struct IResourceManager *v26; // rcx
  struct Windows::ApplicationModel::Resources::Core::CResourceManager *v27; // rcx
  struct Windows::ApplicationModel::Resources::Core::CResourceManager *v28; // [rsp+20h] [rbp-E0h] BYREF
  struct IResourceManager *v29; // [rsp+28h] [rbp-D8h] BYREF
  UINT32 packageFullNameLength; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v31; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h]
  WCHAR packageFullName[128]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  if ( !a2 )
  {
    v31 = *(_OWORD *)L"returnValue";
    v32 = *(_QWORD *)L"lue";
    v8 = -2147024809;
    RoOriginateErrorW(2147942487LL, 11, &v31);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28C,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
      (const char *)0x80070057LL,
      (int)v28);
    return v8;
  }
  RtlAcquireSRWLockExclusive(&Windows::ApplicationModel::Resources::Core::CResourceManager::s_srwlockMrtResourceManagerSingleton);
  *a2 = 0;
  v28 = 0;
  v29 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v28);
  if ( (int)Windows::ApplicationModel::Resources::Core::CResourceManager::GetSingletonResourceManager(&v28) >= 0 )
  {
    MrtSharedObjectState = Windows::ApplicationModel::Resources::Core::CResourceManager::GetMrtSharedObjectState(v28);
    if ( (MrtSharedObjectState & 2) == 0 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( (MrtSharedObjectState & 0x14) != 0 )
    {
      v8 = -2147009752;
      RoOriginateError(2147957544LL);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29F,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
        (const char *)0x80073B28LL,
        (int)v28);
      v23 = v29;
      if ( v29 )
      {
        v29 = 0;
        ((void (__fastcall *)(struct IResourceManager *))v23->lpVtbl->Release)(v23);
      }
    }
    else
    {
      if ( (MrtSharedObjectState & 8) != 0 )
      {
        v4 = (struct IResourceManager *)v28;
        if ( v28 )
          (*(void (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::CResourceManager *))(*(_QWORD *)v28 + 8LL))(v28);
        v5 = v29;
        v29 = v4;
        if ( v5 )
          ((void (__fastcall *)(struct IResourceManager *))v5->lpVtbl->Release)(v5);
LABEL_11:
        v6 = v29;
        v29 = 0;
        *a2 = v6;
        v7 = v28;
        if ( v28 )
        {
          v28 = 0;
          (*(void (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::CResourceManager *))(*(_QWORD *)v7 + 16LL))(v7);
        }
        v8 = 0;
        goto LABEL_14;
      }
      v8 = -2147009752;
      RoOriginateError(2147957544LL);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2AA,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
        (const char *)0x80073B28LL,
        (int)v28);
      v22 = v29;
      if ( v29 )
      {
        v29 = 0;
        ((void (__fastcall *)(struct IResourceManager *))v22->lpVtbl->Release)(v22);
      }
    }
    v24 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::CResourceManager *))(*(_QWORD *)v24 + 16LL))(v24);
    }
    goto LABEL_14;
  }
  packageFullNameLength = 128;
  if ( !GetCurrentPackageFullName(&packageFullNameLength, packageFullName)
    && (int)Windows::ApplicationModel::Resources::Core::CResourceManagerFactory::_CreateCurrentResourceManagerForSystemProfileWithPackageName(
              v11,
              packageFullName) >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v28);
    if ( (int)Windows::ApplicationModel::Resources::Core::CResourceManager::GetSingletonResourceManager(&v28) >= 0 )
    {
      if ( !v28 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      Microsoft::WRL::ComPtr<Windows::ApplicationModel::Resources::Core::IResourceManager>::operator=<Windows::ApplicationModel::Resources::Core::CResourceManager>(
        &v29,
        &v28);
      goto LABEL_11;
    }
  }
  v12 = (Microsoft::Resources::Runtime::CResourceManagerInternal *)operator new(
                                                                     0xC8u,
                                                                     (const struct std::nothrow_t *)&std::nothrow);
  if ( v12 )
    v13 = (Microsoft::Resources::Runtime::CResourceManagerInternal *)Microsoft::Resources::Runtime::CResourceManagerInternal::CResourceManagerInternal(v12);
  else
    v13 = 0;
  *(_QWORD *)&v31 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable';
  *((_QWORD *)&v31 + 1) = v13;
  if ( !v13 )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C9,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
      (const char *)0x8007000ELL,
      (int)v28);
    v20 = v29;
    if ( v29 )
    {
      v29 = 0;
      ((void (__fastcall *)(struct IResourceManager *))v20->lpVtbl->Release)(v20);
    }
    v21 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::CResourceManager *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    goto LABEL_14;
  }
  v14 = Microsoft::Resources::Runtime::CResourceManagerInternal::InitializeWithProfileSimple(v13, 8);
  v8 = v14;
  if ( v14 >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v29);
    v15 = Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Resources::Core::CResourceManager,Windows::ApplicationModel::Resources::Core::IResourceManager,Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal> &>(
            &v29,
            &v31);
    v8 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CD,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
        (const char *)(unsigned int)v15,
        (int)v28);
      Microsoft::Resources::Runtime::CResourceManagerInternal::`scalar deleting destructor'(v13, v25);
      v26 = v29;
      if ( v29 )
      {
        v29 = 0;
        ((void (__fastcall *)(struct IResourceManager *))v26->lpVtbl->Release)(v26);
      }
      v27 = v28;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::CResourceManager *))(*(_QWORD *)v27 + 16LL))(v27);
      }
      goto LABEL_14;
    }
    v17 = Windows::ApplicationModel::Resources::Core::CResourceManagerFactory::_WriteToLifetimeStore(v16, v29);
    v8 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D2,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
        (const char *)(unsigned int)v17,
        (int)v28);
      v18 = v29;
      if ( v29 )
      {
        v29 = 0;
        ((void (__fastcall *)(struct IResourceManager *))v18->lpVtbl->Release)(v18);
      }
      v19 = v28;
      if ( v28 )
      {
        v28 = 0;
        (*(void (__fastcall **)(struct Windows::ApplicationModel::Resources::Core::CResourceManager *))(*(_QWORD *)v19 + 16LL))(v19);
      }
      goto LABEL_14;
    }
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2CB,
    (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcemanager.cpp",
    (const char *)(unsigned int)v14,
    (int)v28);
  Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(&v31);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v28);
LABEL_14:
  RtlReleaseSRWLockExclusive(&Windows::ApplicationModel::Resources::Core::CResourceManager::s_srwlockMrtResourceManagerSingleton);
  return v8;
}

```

## disassembly

```asm
0x180072b60  mov     [rsp-8+arg_0], rbx
0x180072b65  mov     [rsp-8+arg_10], rsi
0x180072b6a  push    rbp
0x180072b6b  push    rdi
0x180072b6c  push    r14
0x180072b6e  lea     rbp, [rsp-60h]
0x180072b73  sub     rsp, 160h
0x180072b7a  mov     rax, cs:__security_cookie
0x180072b81  xor     rax, rsp
0x180072b84  mov     [rbp+70h+var_20], rax
0x180072b88  mov     rsi, rdx
0x180072b8b  xor     r14d, r14d
0x180072b8e  test    rdx, rdx
0x180072b91  jz      loc_180072D9D
0x180072b97  lea     rcx, ?s_srwlockMrtResourceManagerSingleton@CResourceManager@Core@Resources@ApplicationModel@Windows@@2U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::ApplicationModel::Resources::Core::CResourceManager::s_srwlockMrtResourceManagerSingleton
0x180072b9e  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180072ba4  mov     [rsi], r14
0x180072ba7  mov     [rsp+170h+var_150], r14; int
0x180072bac  mov     [rsp+170h+var_148], r14
0x180072bb1  lea     rcx, [rsp+170h+var_150]
0x180072bb6  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180072bbb  lea     rcx, [rsp+170h+var_150]; struct Windows::ApplicationModel::Resources::Core::CResourceManager **
0x180072bc0  call    ?GetSingletonResourceManager@CResourceManager@Core@Resources@ApplicationModel@Windows@@SAJPEAPEAV12345@@Z; Windows::ApplicationModel::Resources::Core::CResourceManager::GetSingletonResourceManager(Windows::ApplicationModel::Resources::Core::CResourceManager * *)
0x180072bc5  test    eax, eax
0x180072bc7  js      loc_180072C88
0x180072bcd  mov     rcx, [rsp+170h+var_150]
0x180072bd2  call    ?GetMrtSharedObjectState@CResourceManager@Core@Resources@ApplicationModel@Windows@@QEAA?AW4_MrtSharedObjectState@3Microsoft@@XZ; Windows::ApplicationModel::Resources::Core::CResourceManager::GetMrtSharedObjectState(void)
0x180072bd7  mov     ebx, eax
0x180072bd9  test    al, 2
0x180072bdb  jz      loc_180072F57
0x180072be1  test    bl, 14h
0x180072be4  jnz     loc_180072E8C
0x180072bea  test    bl, 8
0x180072bed  jz      loc_180072E46
0x180072bf3  mov     rbx, [rsp+170h+var_150]
0x180072bf8  test    rbx, rbx
0x180072bfb  jz      short loc_180072C0D
0x180072bfd  mov     rax, [rbx]
0x180072c00  mov     rcx, rbx
0x180072c03  mov     rax, [rax+8]
0x180072c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c0c  nop
0x180072c0d  mov     rcx, [rsp+170h+var_148]
0x180072c12  mov     [rsp+170h+var_148], rbx
0x180072c17  test    rcx, rcx
0x180072c1a  jz      short loc_180072C29
0x180072c1c  mov     rax, [rcx]
0x180072c1f  mov     rax, [rax+10h]
0x180072c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c28  nop
0x180072c29  mov     rax, [rsp+170h+var_148]
0x180072c2e  mov     [rsp+170h+var_148], r14
0x180072c33  mov     [rsi], rax
0x180072c36  mov     rcx, [rsp+170h+var_150]
0x180072c3b  test    rcx, rcx
0x180072c3e  jz      short loc_180072C52
0x180072c40  mov     [rsp+170h+var_150], r14
0x180072c45  mov     rax, [rcx]
0x180072c48  mov     rax, [rax+10h]
0x180072c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072c51  nop
0x180072c52  mov     ebx, r14d
0x180072c55  lea     rcx, ?s_srwlockMrtResourceManagerSingleton@CResourceManager@Core@Resources@ApplicationModel@Windows@@2U_RTL_SRWLOCK@@A; _RTL_SRWLOCK Windows::ApplicationModel::Resources::Core::CResourceManager::s_srwlockMrtResourceManagerSingleton
0x180072c5c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180072c62  mov     eax, ebx
0x180072c64  mov     rcx, [rbp+70h+var_20]
0x180072c68  xor     rcx, rsp; StackCookie
0x180072c6b  call    __security_check_cookie
0x180072c70  lea     r11, [rsp+170h+var_10]
0x180072c78  mov     rbx, [r11+20h]
0x180072c7c  mov     rsi, [r11+30h]
0x180072c80  mov     rsp, r11
0x180072c83  pop     r14
0x180072c85  pop     rdi
0x180072c86  pop     rbp
0x180072c87  retn
0x180072c88  mov     [rsp+170h+packageFullNameLength], 80h
0x180072c90  lea     rdx, [rsp+170h+packageFullName]; packageFullName
0x180072c95  lea     rcx, [rsp+170h+packageFullNameLength]; packageFullNameLength
0x180072c9a  call    cs:__imp_GetCurrentPackageFullName
0x180072ca0  test    eax, eax
0x180072ca2  jz      loc_180072F61
0x180072ca8  jle     short loc_180072CB2
0x180072caa  movzx   eax, ax
0x180072cad  or      eax, 80070000h
0x180072cb2  test    eax, eax
0x180072cb4  jns     loc_180072C29
0x180072cba  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180072cc1  mov     ecx, 0C8h; unsigned __int64
0x180072cc6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180072ccb  test    rax, rax
0x180072cce  jz      loc_180072EF1
0x180072cd4  mov     rcx, rax; this
0x180072cd7  call    ??0CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::Runtime::CResourceManagerInternal::CResourceManagerInternal(void)
0x180072cdc  mov     rdi, rax
0x180072cdf  lea     rax, ??_7?$AutoDeletePtr@VCResourceManagerInternal@Runtime@Resources@Microsoft@@@Resources@Microsoft@@6B@; const Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::`vftable'
0x180072ce6  mov     qword ptr [rsp+170h+var_138], rax
0x180072ceb  mov     qword ptr [rsp+170h+var_138+8], rdi
0x180072cf0  test    rdi, rdi
0x180072cf3  jz      loc_180072DEB
0x180072cf9  mov     edx, 8
0x180072cfe  mov     rcx, rdi
0x180072d01  call    ?InitializeWithProfileSimple@CResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAJW4ProfileType@MrmProfile@34@@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::InitializeWithProfileSimple(Microsoft::Resources::MrmProfile::ProfileType)
0x180072d06  mov     ebx, eax
0x180072d08  test    eax, eax
0x180072d0a  js      loc_180072FA5
0x180072d10  lea     rcx, [rsp+170h+var_148]
0x180072d15  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180072d1a  lea     rdx, [rsp+170h+var_138]
0x180072d1f  lea     rcx, [rsp+170h+var_148]
0x180072d24  call    ??$MakeAndInitialize@VCResourceManager@Core@Resources@ApplicationModel@Windows@@UIResourceManager@2345@AEAV?$AutoDeletePtr@VCResourceManagerInternal@Runtime@Resources@Microsoft@@@3Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAUIResourceManager@Core@Resources@ApplicationModel@Windows@@AEAV?$AutoDeletePtr@VCResourceManagerInternal@Runtime@Resources@Microsoft@@@52@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::ApplicationModel::Resources::Core::CResourceManager,Windows::ApplicationModel::Resources::Core::IResourceManager,Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal> &>(Windows::ApplicationModel::Resources::Core::IResourceManager * *,Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal> &)
0x180072d29  mov     ebx, eax
0x180072d2b  test    eax, eax
0x180072d2d  js      loc_180072EF9
0x180072d33  mov     rdx, [rsp+170h+var_148]; struct IResourceManager *
0x180072d38  call    ?_WriteToLifetimeStore@CResourceManagerFactory@Core@Resources@ApplicationModel@Windows@@AEAAJPEAUIResourceManager@2345@@Z; Windows::ApplicationModel::Resources::Core::CResourceManagerFactory::_WriteToLifetimeStore(Windows::ApplicationModel::Resources::Core::IResourceManager *)
0x180072d3d  mov     ebx, eax
0x180072d3f  test    eax, eax
0x180072d41  jns     loc_180072C29
0x180072d47  mov     rcx, [rbp+78h]; this
0x180072d4b  mov     r9d, eax; char *
0x180072d4e  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180072d55  mov     edx, 2D2h; void *
0x180072d5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072d5f  nop
0x180072d60  mov     rcx, [rsp+170h+var_148]
0x180072d65  test    rcx, rcx
0x180072d68  jz      short loc_180072D7C
0x180072d6a  mov     [rsp+170h+var_148], r14
0x180072d6f  mov     rax, [rcx]
0x180072d72  mov     rax, [rax+10h]
0x180072d76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072d7b  nop
0x180072d7c  mov     rcx, [rsp+170h+var_150]
0x180072d81  test    rcx, rcx
0x180072d84  jz      short loc_180072D98
0x180072d86  mov     [rsp+170h+var_150], r14
0x180072d8b  mov     rax, [rcx]
0x180072d8e  mov     rax, [rax+10h]
0x180072d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072d97  nop
0x180072d98  jmp     loc_180072C55
0x180072d9d  movups  xmm0, xmmword ptr cs:aReturnvalue; "returnValue"
0x180072da4  movups  [rsp+170h+var_138], xmm0
0x180072da9  movsd   xmm1, qword ptr cs:aReturnvalue+10h; "lue"
0x180072db1  movsd   [rsp+170h+var_128], xmm1
0x180072db7  lea     r8, [rsp+170h+var_138]
0x180072dbc  mov     edx, 0Bh
0x180072dc1  mov     ebx, 80070057h
0x180072dc6  mov     ecx, ebx
0x180072dc8  call    cs:__imp_RoOriginateErrorW
0x180072dce  mov     rcx, [rbp+78h]; this
0x180072dd2  mov     r9d, ebx; char *
0x180072dd5  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180072ddc  mov     edx, 28Ch; void *
0x180072de1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072de6  jmp     loc_180072C62
0x180072deb  mov     rcx, [rbp+78h]; this
0x180072def  mov     ebx, 8007000Eh
0x180072df4  mov     r9d, ebx; char *
0x180072df7  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180072dfe  mov     edx, 2C9h; void *
0x180072e03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072e08  nop
0x180072e09  mov     rcx, [rsp+170h+var_148]
0x180072e0e  test    rcx, rcx
0x180072e11  jz      short loc_180072E25
0x180072e13  mov     [rsp+170h+var_148], r14
0x180072e18  mov     rax, [rcx]
0x180072e1b  mov     rax, [rax+10h]
0x180072e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072e24  nop
0x180072e25  mov     rcx, [rsp+170h+var_150]
0x180072e2a  test    rcx, rcx
0x180072e2d  jz      short loc_180072E41
0x180072e2f  mov     [rsp+170h+var_150], r14
0x180072e34  mov     rax, [rcx]
0x180072e37  mov     rax, [rax+10h]
0x180072e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072e40  nop
0x180072e41  jmp     loc_180072C55
0x180072e46  xor     edx, edx
0x180072e48  mov     ebx, 80073B28h
0x180072e4d  mov     ecx, ebx
0x180072e4f  call    cs:__imp_RoOriginateError
0x180072e55  mov     rcx, [rbp+78h]; this
0x180072e59  mov     r9d, ebx; char *
0x180072e5c  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180072e63  mov     edx, 2AAh; void *
0x180072e68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072e6d  nop
0x180072e6e  mov     rcx, [rsp+170h+var_148]
0x180072e73  test    rcx, rcx
0x180072e76  jz      short loc_180072E8A
0x180072e78  mov     [rsp+170h+var_148], r14
0x180072e7d  mov     rax, [rcx]
0x180072e80  mov     rax, [rax+10h]
0x180072e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072e89  nop
0x180072e8a  jmp     short loc_180072ED0
0x180072e8c  xor     edx, edx
0x180072e8e  mov     ebx, 80073B28h
0x180072e93  mov     ecx, ebx
0x180072e95  call    cs:__imp_RoOriginateError
0x180072e9b  mov     rcx, [rbp+78h]; this
0x180072e9f  mov     r9d, ebx; char *
0x180072ea2  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180072ea9  mov     edx, 29Fh; void *
0x180072eae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072eb3  nop
0x180072eb4  mov     rcx, [rsp+170h+var_148]
0x180072eb9  test    rcx, rcx
0x180072ebc  jz      short loc_180072ED0
0x180072ebe  mov     [rsp+170h+var_148], r14
0x180072ec3  mov     rax, [rcx]
0x180072ec6  mov     rax, [rax+10h]
0x180072eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072ecf  nop
0x180072ed0  mov     rcx, [rsp+170h+var_150]
0x180072ed5  test    rcx, rcx
0x180072ed8  jz      short loc_180072EEC
0x180072eda  mov     [rsp+170h+var_150], r14
0x180072edf  mov     rax, [rcx]
0x180072ee2  mov     rax, [rax+10h]
0x180072ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072eeb  nop
0x180072eec  jmp     loc_180072C55
0x180072ef1  mov     rdi, r14
0x180072ef4  jmp     loc_180072CDF
0x180072ef9  mov     rcx, [rbp+78h]; this
0x180072efd  mov     r9d, eax; char *
0x180072f00  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180072f07  mov     edx, 2CDh; void *
0x180072f0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072f11  mov     rcx, rdi; this
0x180072f14  call    ??_GCResourceManagerInternal@Runtime@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::Runtime::CResourceManagerInternal::`scalar deleting destructor'(uint)
0x180072f19  nop
0x180072f1a  mov     rcx, [rsp+170h+var_148]
0x180072f1f  test    rcx, rcx
0x180072f22  jz      short loc_180072F36
0x180072f24  mov     [rsp+170h+var_148], r14
0x180072f29  mov     rax, [rcx]
0x180072f2c  mov     rax, [rax+10h]
0x180072f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072f35  nop
0x180072f36  mov     rcx, [rsp+170h+var_150]
0x180072f3b  test    rcx, rcx
0x180072f3e  jz      short loc_180072F52
0x180072f40  mov     [rsp+170h+var_150], r14
0x180072f45  mov     rax, [rcx]
0x180072f48  mov     rax, [rax+10h]
0x180072f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072f51  nop
0x180072f52  jmp     loc_180072C55
0x180072f57  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180072f5c  jmp     loc_180072BE1
0x180072f61  lea     rdx, [rsp+170h+packageFullName]; unsigned __int16 *
0x180072f66  call    ?_CreateCurrentResourceManagerForSystemProfileWithPackageName@CResourceManagerFactory@Core@Resources@ApplicationModel@Windows@@AEAAJPEBG@Z; Windows::ApplicationModel::Resources::Core::CResourceManagerFactory::_CreateCurrentResourceManagerForSystemProfileWithPackageName(ushort const *)
0x180072f6b  test    eax, eax
0x180072f6d  js      loc_180072CBA
0x180072f73  lea     rcx, [rsp+170h+var_150]
0x180072f78  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180072f7d  lea     rcx, [rsp+170h+var_150]; struct Windows::ApplicationModel::Resources::Core::CResourceManager **
0x180072f82  call    ?GetSingletonResourceManager@CResourceManager@Core@Resources@ApplicationModel@Windows@@SAJPEAPEAV12345@@Z; Windows::ApplicationModel::Resources::Core::CResourceManager::GetSingletonResourceManager(Windows::ApplicationModel::Resources::Core::CResourceManager * *)
0x180072f87  test    eax, eax
0x180072f89  js      loc_180072CBA
0x180072f8f  cmp     [rsp+170h+var_150], r14
0x180072f94  jnz     loc_1800C4702
0x180072f9a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180072f9f  nop
0x180072fa0  jmp     loc_1800C4702
0x180072fa5  mov     rcx, [rbp+78h]; this
0x180072fa9  mov     r9d, eax; char *
0x180072fac  lea     r8, aOnecoreuapBase_25; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x180072fb3  mov     edx, 2CBh; void *
0x180072fb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072fbd  lea     rcx, [rsp+170h+var_138]
0x180072fc2  call    ?Release@?$AutoDeletePtr@VCResourceManagerInternal@Runtime@Resources@Microsoft@@@Resources@Microsoft@@QEAAXXZ; Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Runtime::CResourceManagerInternal>::Release(void)
0x180072fc7  lea     rcx, [rsp+170h+var_148]
0x180072fcc  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180072fd1  lea     rcx, [rsp+170h+var_150]
0x180072fd6  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x180072fdb  jmp     loc_180072C55
0x1800c4702  lea     rdx, [rsp+170h+var_150]
0x1800c4707  lea     rcx, [rsp+170h+var_148]
0x1800c470c  call    ??$?4VCResourceManager@Core@Resources@ApplicationModel@Windows@@@?$ComPtr@UIResourceManager@Core@Resources@ApplicationModel@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV?$ComPtr@VCResourceManager@Core@Resources@ApplicationModel@Windows@@@12@@Z; Microsoft::WRL::ComPtr<Windows::ApplicationModel::Resources::Core::IResourceManager>::operator=<Windows::ApplicationModel::Resources::Core::CResourceManager>(Microsoft::WRL::ComPtr<Windows::ApplicationModel::Resources::Core::CResourceManager> const &)
0x1800c4711  nop
0x1800c4712  jmp     loc_180072C29
```
