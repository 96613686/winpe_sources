# OobeZdpElevatedManagerCore::BeginAsyncSearch(IUpdateSearcher *,void *,ISearchJob * *)

- ea: `0x18000dfb4`
- end: `0x18000e2b2`
- name: `?BeginAsyncSearch@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateSearcher@@PEAXPEAPEAUISearchJob@@@Z`
- size: `766`
- prototype: `__int64 __fastcall(OobeZdpElevatedManagerCore *__hidden this, struct IUpdateSearcher *, void *, struct ISearchJob **)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180010640`

## callees

- `0x180002b60`
- `0x1800041cd`
- `0x1800076d4`
- `0x180007d34`
- `0x180009760`
- `0x18000b098`
- `0x18000c554`
- `0x18000d684`
- `0x18000dfb4`
- `0x18000fae0`
- `0x18001122c`
- `0x18001125c`
- `0x18006e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000e0ae`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000e111`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000e0ae`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000e111`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000e183`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000e183`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000e075`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000e075`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e16a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e16a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e23b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e23b`
- `OLEAUT32!__imp_VariantInit` at `0x18000e1e1`
- `OLEAUT32!__imp_VariantInit` at `0x18000e1e1`
- `OLEAUT32!__imp_VariantClear` at `0x18000e232`
- `OLEAUT32!__imp_VariantClear` at `0x18000e232`

## string_xrefs

- `0x18000e141`: `IsInstalled = 0 AND DeploymentAction = 'Installation' AND CategoryIDs contains '%s'`
- `0x18000e020`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000e1b1`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`
- `0x18000e268`: `shellcommon\shell\oobe\core\components\com\oobezdpmanagercore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall OobeZdpElevatedManagerCore::BeginAsyncSearch(
        RTL_SRWLOCK *this,
        struct IUpdateSearcher *a2,
        RTL_SRWLOCK *a3,
        struct ISearchJob **a4)
{
  int v4; // r15d
  int v7; // eax
  unsigned int v8; // ebx
  HRESULT v9; // eax
  __int64 v10; // rdx
  unsigned __int64 v11; // rbx
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rbx
  OLECHAR *v14; // rdi
  int v15; // eax
  __int64 v16; // r9
  int v18; // [rsp+20h] [rbp-E0h]
  LPOLESTR lpsz; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v20; // [rsp+38h] [rbp-C8h]
  __int64 v21; // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  RTL_SRWLOCK *v23; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG v25; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR psz[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v4 = (int)a4;
  v23 = a3;
  *a4 = 0;
  OobeZdpElevatedManagerCore::OptInToSearchDriverSets((OobeZdpElevatedManagerCore *)this, a2);
  v22 = 0;
  v7 = Microsoft::WRL::Details::MakeAndInitialize<COOBEWUCompletionCallback,ISearchCompletedCallback,void * &>(
         &v22,
         &v23);
  v8 = v7;
  if ( v7 >= 0 )
  {
    lpsz = 0;
    v20 = 0;
    v21 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
    v20 = -1;
    v21 = -1;
    v9 = StringFromCLSID(&categoryWUZeroDayPriority, &lpsz);
    v8 = v9;
    if ( v9 >= 0 )
    {
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpsz);
      v11 = 0;
      if ( v20 )
      {
        do
        {
          if ( !wcschr(L"{", lpsz[v11]) )
            break;
          ++v11;
        }
        while ( v11 < v20 );
        if ( v11 )
        {
          memmove_0(lpsz, &lpsz[v11], 2 * (v20 - v11) + 2);
          v20 -= v11;
        }
      }
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&lpsz);
      v12 = v20;
      v13 = v20;
      if ( v20 )
      {
        do
        {
          if ( !wcschr(L"}", lpsz[v13 - 1]) )
            break;
          --v13;
        }
        while ( v13 );
        v12 = v20;
      }
      if ( v13 != v12 )
      {
        lpsz[v13] = 0;
        v20 = v13;
      }
      v9 = StringCchPrintfW(
             psz,
             0x104u,
             L"IsInstalled = 0 AND DeploymentAction = 'Installation' AND CategoryIDs contains '%s'",
             lpsz);
      v8 = v9;
      if ( v9 >= 0 )
      {
        v14 = SysAllocString(psz);
        if ( !v14 )
        {
          v8 = -2147024882;
          v16 = 2147942414LL;
          v10 = 409;
          goto LABEL_26;
        }
        AcquireSRWLockShared(this + 4);
        v23 = this + 4;
        v15 = (*(__int64 (__fastcall **)(PVOID, __int64))(*(_QWORD *)this[5].Ptr + 48LL))(this[5].Ptr, 1);
        if ( v15 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x19D,
            (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
            (const char *)(unsigned int)v15,
            v18);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v23);
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        v25 = pvarg;
        v18 = v4;
        v9 = ((__int64 (__fastcall *)(struct IUpdateSearcher *, OLECHAR *, __int64, VARIANTARG *))a2->lpVtbl->BeginSearch)(
               a2,
               v14,
               v22,
               &v25);
        v8 = v9;
        if ( v9 >= 0 )
        {
          VariantClear(&pvarg);
          SysFreeString(v14);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
          wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v22);
          return 0;
        }
        v10 = 418;
      }
      else
      {
        v10 = 406;
      }
    }
    else
    {
      v10 = 400;
    }
    v16 = (unsigned int)v9;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
      (const char *)v16,
      v18);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpsz);
    goto LABEL_27;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x18D,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\com\\oobezdpmanagercore.cpp",
    (const char *)(unsigned int)v7,
    v18);
LABEL_27:
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v22);
  return v8;
}

```

## disassembly

```asm
0x18000dfb4  push    rbp
0x18000dfb6  push    rbx
0x18000dfb7  push    rsi
0x18000dfb8  push    rdi
0x18000dfb9  push    r14
0x18000dfbb  push    r15
0x18000dfbd  lea     rbp, [rsp-1B8h]
0x18000dfc5  sub     rsp, 2B8h
0x18000dfcc  mov     rax, cs:__security_cookie
0x18000dfd3  xor     rax, rsp
0x18000dfd6  mov     [rbp+1E0h+var_40], rax
0x18000dfdd  mov     r15, r9
0x18000dfe0  mov     r14, rdx
0x18000dfe3  mov     rsi, rcx
0x18000dfe6  mov     [rsp+2E0h+var_290], r8
0x18000dfeb  mov     qword ptr [r9], 0
0x18000dff2  call    ?OptInToSearchDriverSets@OobeZdpElevatedManagerCore@@AEAAJPEAUIUpdateSearcher@@@Z; OobeZdpElevatedManagerCore::OptInToSearchDriverSets(IUpdateSearcher *)
0x18000dff7  nop
0x18000dff8  mov     [rsp+2E0h+var_298], 0
0x18000e001  lea     rdx, [rsp+2E0h+var_290]
0x18000e006  lea     rcx, [rsp+2E0h+var_298]
0x18000e00b  call    ??$MakeAndInitialize@VCOOBEWUCompletionCallback@@UISearchCompletedCallback@@AEAPEAX@Details@WRL@Microsoft@@YAJPEAPEAUISearchCompletedCallback@@AEAPEAX@Z; Microsoft::WRL::Details::MakeAndInitialize<COOBEWUCompletionCallback,ISearchCompletedCallback,void * &>(ISearchCompletedCallback * *,void * &)
0x18000e010  mov     ebx, eax
0x18000e012  test    eax, eax
0x18000e014  jns     short loc_18000E036
0x18000e016  mov     rcx, [rbp+1E8h]; this
0x18000e01d  mov     r9d, eax; char *
0x18000e020  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000e027  mov     edx, 18Dh; void *
0x18000e02c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e031  jmp     loc_18000E287
0x18000e036  mov     [rsp+2E0h+lpsz], 0
0x18000e03f  mov     [rsp+2E0h+var_2A8], 0
0x18000e048  mov     [rsp+2E0h+var_2A0], 0
0x18000e051  lea     rcx, [rsp+2E0h+lpsz]
0x18000e056  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000e05b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e05f  mov     [rsp+2E0h+var_2A8], rax
0x18000e064  mov     [rsp+2E0h+var_2A0], rax
0x18000e069  lea     rdx, [rsp+2E0h+lpsz]; lplpsz
0x18000e06e  lea     rcx, categoryWUZeroDayPriority; rclsid
0x18000e075  call    cs:__imp_StringFromCLSID
0x18000e07b  mov     ebx, eax
0x18000e07d  test    eax, eax
0x18000e07f  jns     short loc_18000E08B
0x18000e081  mov     edx, 190h
0x18000e086  jmp     loc_18000E228
0x18000e08b  lea     rcx, [rsp+2E0h+lpsz]
0x18000e090  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18000e095  xor     ebx, ebx
0x18000e097  cmp     [rsp+2E0h+var_2A8], rbx
0x18000e09c  jbe     short loc_18000E0E9
0x18000e09e  mov     rdx, [rsp+2E0h+lpsz]
0x18000e0a3  movzx   edx, word ptr [rdx+rbx*2]; Ch
0x18000e0a7  lea     rcx, Str; "{"
0x18000e0ae  call    cs:__imp_wcschr
0x18000e0b4  mov     r8, [rsp+2E0h+var_2A8]
0x18000e0b9  test    rax, rax
0x18000e0bc  jz      short loc_18000E0C6
0x18000e0be  inc     rbx
0x18000e0c1  cmp     rbx, r8
0x18000e0c4  jb      short loc_18000E09E
0x18000e0c6  test    rbx, rbx
0x18000e0c9  jz      short loc_18000E0E9
0x18000e0cb  sub     r8, rbx
0x18000e0ce  lea     r8, ds:2[r8*2]; Size
0x18000e0d6  mov     rcx, [rsp+2E0h+lpsz]; void *
0x18000e0db  lea     rdx, [rcx+rbx*2]; Src
0x18000e0df  call    memmove_0
0x18000e0e4  sub     [rsp+2E0h+var_2A8], rbx
0x18000e0e9  lea     rcx, [rsp+2E0h+lpsz]
0x18000e0ee  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18000e0f3  mov     rcx, [rsp+2E0h+var_2A8]
0x18000e0f8  mov     rbx, rcx
0x18000e0fb  test    rcx, rcx
0x18000e0fe  jz      short loc_18000E127
0x18000e100  mov     rdx, [rsp+2E0h+lpsz]
0x18000e105  movzx   edx, word ptr [rdx+rbx*2-2]; Ch
0x18000e10a  lea     rcx, asc_18008C218; "}"
0x18000e111  call    cs:__imp_wcschr
0x18000e117  test    rax, rax
0x18000e11a  jz      short loc_18000E122
0x18000e11c  sub     rbx, 1
0x18000e120  jnz     short loc_18000E100
0x18000e122  mov     rcx, [rsp+2E0h+var_2A8]
0x18000e127  cmp     rbx, rcx
0x18000e12a  jz      short loc_18000E13C
0x18000e12c  xor     ecx, ecx
0x18000e12e  mov     rax, [rsp+2E0h+lpsz]
0x18000e133  mov     [rax+rbx*2], cx
0x18000e137  mov     [rsp+2E0h+var_2A8], rbx
0x18000e13c  mov     r9, [rsp+2E0h+lpsz]
0x18000e141  lea     r8, aIsinstalled0An; "IsInstalled = 0 AND DeploymentAction = "...
0x18000e148  mov     edx, 104h; unsigned __int64
0x18000e14d  lea     rcx, [rbp+1E0h+psz]; unsigned __int16 *
0x18000e151  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e156  mov     ebx, eax
0x18000e158  test    eax, eax
0x18000e15a  jns     short loc_18000E166
0x18000e15c  mov     edx, 196h
0x18000e161  jmp     loc_18000E228
0x18000e166  lea     rcx, [rbp+1E0h+psz]; psz
0x18000e16a  call    cs:__imp_SysAllocString
0x18000e170  mov     rdi, rax
0x18000e173  test    rax, rax
0x18000e176  jz      loc_18000E25B
0x18000e17c  lea     rbx, [rsi+20h]
0x18000e180  mov     rcx, rbx; SRWLock
0x18000e183  call    cs:__imp_AcquireSRWLockShared
0x18000e189  mov     [rsp+2E0h+var_290], rbx
0x18000e18e  mov     rcx, [rsi+28h]
0x18000e192  mov     r8, [rcx]
0x18000e195  mov     edx, 1
0x18000e19a  mov     rax, [r8+30h]
0x18000e19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1a3  mov     rcx, [rbp+1E8h]; this
0x18000e1aa  test    eax, eax
0x18000e1ac  jns     short loc_18000E1C3
0x18000e1ae  mov     r9d, eax; char *
0x18000e1b1  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000e1b8  mov     edx, 19Dh; void *
0x18000e1bd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e1c2  nop
0x18000e1c3  lea     rcx, [rsp+2E0h+var_290]
0x18000e1c8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e1cd  xorps   xmm0, xmm0
0x18000e1d0  xor     eax, eax
0x18000e1d2  movups  xmmword ptr [rsp+2E0h+pvarg], xmm0
0x18000e1d7  mov     qword ptr [rsp+2E0h+pvarg+10h], rax
0x18000e1dc  lea     rcx, [rsp+2E0h+pvarg]; pvarg
0x18000e1e1  call    cs:__imp_VariantInit
0x18000e1e7  movups  xmm0, xmmword ptr [rsp+2E0h+pvarg]
0x18000e1ec  movsd   xmm1, qword ptr [rsp+2E0h+pvarg+10h]
0x18000e1f2  movaps  [rsp+2E0h+var_270], xmm0
0x18000e1f7  movsd   [rbp+1E0h+var_260], xmm1
0x18000e1fc  mov     rax, [r14]
0x18000e1ff  mov     qword ptr [rsp+2E0h+var_2C0], r15
0x18000e204  lea     r9, [rsp+2E0h+var_270]
0x18000e209  mov     r8, [rsp+2E0h+var_298]
0x18000e20e  mov     rdx, rdi
0x18000e211  mov     rcx, r14
0x18000e214  mov     rax, [rax+78h]
0x18000e218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e21d  mov     ebx, eax
0x18000e21f  test    eax, eax
0x18000e221  jns     short loc_18000E22D
0x18000e223  mov     edx, 1A2h
0x18000e228  mov     r9d, eax
0x18000e22b  jmp     short loc_18000E268
0x18000e22d  lea     rcx, [rsp+2E0h+pvarg]; pvarg
0x18000e232  call    cs:__imp_VariantClear
0x18000e238  mov     rcx, rdi; bstrString
0x18000e23b  call    cs:__imp_SysFreeString
0x18000e241  nop
0x18000e242  lea     rcx, [rsp+2E0h+lpsz]
0x18000e247  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000e24c  nop
0x18000e24d  lea     rcx, [rsp+2E0h+var_298]
0x18000e252  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000e257  xor     eax, eax
0x18000e259  jmp     short loc_18000E293
0x18000e25b  mov     ebx, 8007000Eh
0x18000e260  mov     r9d, ebx; char *
0x18000e263  mov     edx, 199h; void *
0x18000e268  lea     r8, aShellcommonShe_13; "shellcommon\\shell\\oobe\\core\\compone"...
0x18000e26f  mov     rcx, [rbp+1E8h]; this
0x18000e276  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e27b  nop
0x18000e27c  lea     rcx, [rsp+2E0h+lpsz]
0x18000e281  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000e286  nop
0x18000e287  lea     rcx, [rsp+2E0h+var_298]
0x18000e28c  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18000e291  mov     eax, ebx
0x18000e293  mov     rcx, [rbp+1E0h+var_40]
0x18000e29a  xor     rcx, rsp; StackCookie
0x18000e29d  call    __security_check_cookie
0x18000e2a2  add     rsp, 2B8h
0x18000e2a9  pop     r15
0x18000e2ab  pop     r14
0x18000e2ad  pop     rdi
0x18000e2ae  pop     rsi
0x18000e2af  pop     rbx
0x18000e2b0  pop     rbp
0x18000e2b1  retn
```
