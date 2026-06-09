# CloudExperienceHostAPI::OobeDisplayLanguages::GetDisplayLanguages(Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::IOobeDisplayLanguage *> * *)

- ea: `0x180089e60`
- end: `0x18008a25d`
- name: `?GetDisplayLanguages@OobeDisplayLanguages@CloudExperienceHostAPI@@UEAAJPEAPEAU?$IVectorView@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@@Collections@Foundation@Windows@@@Z`
- size: `1021`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180003470`
- `0x180008544`
- `0x180008b54`
- `0x18001ad08`
- `0x18001e9a4`
- `0x1800203d0`
- `0x1800230b0`
- `0x1800599d0`
- `0x180059b90`
- `0x180059cc0`
- `0x18005d1b8`
- `0x1800887ac`
- `0x180088a0c`
- `0x180089e60`
- `0x18008a464`
- `0x18008a5b4`
- `0x1800b82d4`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180089fa8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180089fa8`
- `ntdll!RtlGetUILanguageInfo` at `0x18008a090`
- `ntdll!RtlGetUILanguageInfo` at `0x18008a090`

## string_xrefs

- `0x180089ee6`: `shell\oobe\machine\plugins\adapters\winrt\oobedisplaylanguage.cpp`
- `0x180089f46`: `shell\oobe\machine\plugins\adapters\winrt\oobedisplaylanguage.cpp`
- `0x18008a210`: `shell\oobe\machine\plugins\adapters\winrt\oobedisplaylanguage.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CloudExperienceHostAPI::OobeDisplayLanguages::GetDisplayLanguages(__int64 a1, _QWORD *a2)
{
  __int64 v4; // rcx
  char v5; // r8
  CloudExperienceHostCoreTelemetry *v6; // rcx
  int v7; // eax
  unsigned int v8; // ebx
  unsigned int (__fastcall *v9)(unsigned int, unsigned __int16 *, unsigned int, const unsigned __int16 *); // r12
  unsigned int v10; // r14d
  unsigned int v11; // r15d
  __int64 v12; // rbx
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  int v16; // r14d
  unsigned __int16 *v17; // rax
  int v18; // ecx
  int v19; // edx
  __int64 v20; // rdx
  int v21; // eax
  int v22; // eax
  int *bIgnoreCase; // [rsp+20h] [rbp-E0h]
  char *v25; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  int v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v30; // [rsp+50h] [rbp-B0h]
  WCHAR String1[88]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String2[88]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR v33[176]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  if ( CloudExperienceHostCoreTelemetry::IsEnabled(a1, (unsigned __int64)a2) )
  {
    wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(
      v4,
      _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_);
    CloudExperienceHostCoreTelemetry::GlobalizationState_(
      v6,
      "CloudExperienceHostAPI::OobeDisplayLanguages::GetDisplayLanguages");
  }
  *a2 = 0;
  v29 = 0;
  v7 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<CloudExperienceHostAPI::IOobeDisplayLanguage,Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeDisplayLanguage *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeDisplayLanguage *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeDisplayLanguage *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeDisplayLanguage *>>>(
         v4,
         &v29,
         v5);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6B,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
      (const char *)(unsigned int)v7,
      (int)bIgnoreCase);
LABEL_40:
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v29);
    return v8;
  }
  v9 = *(unsigned int (__fastcall **)(unsigned int, unsigned __int16 *, unsigned int, const unsigned __int16 *))(a1 + 56);
  if ( !v9 )
    v9 = GetSupportedUILanguages;
  v10 = v9(0, 0, 0, (const unsigned __int16 *)1);
  v30 = v10;
  if ( v10 )
  {
    String2[0] = 0;
    GetSystemPreferredUILanguage(&v25);
    v11 = 0;
    v12 = v29;
    while ( v11 < v10 )
    {
      if ( ((unsigned int (__fastcall *)(_QWORD, WCHAR *, __int64))v9)(v11, String1, 85) )
      {
        if ( CompareStringOrdinal(String1, -1, String2, -1, 1) != 2 )
        {
          v15 = StringCchCopyW(String2, 0x55u, String1);
          if ( v15 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x8E,
              (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
              (const char *)(unsigned int)v15,
              (int)bIgnoreCase);
          if ( (unsigned int)GetNativeDisplayNameEx(String1, v33, 0xAEu) )
          {
            v26 = 0;
            v16 = Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostAPI::OobeDisplayLanguage,CloudExperienceHostAPI::OobeDisplayLanguage,unsigned short (&)[85],unsigned short (&)[174]>(
                    &v26,
                    String1,
                    v33);
            if ( v16 < 0 )
            {
              v20 = 154;
LABEL_31:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v20,
                (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
                (const char *)(unsigned int)v16,
                (int)bIgnoreCase);
              wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::~com_ptr_t<OobeZdpManager,wil::err_exception_policy>(&v26);
LABEL_32:
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v25);
              v8 = v16;
              goto LABEL_40;
            }
            v17 = (unsigned __int16 *)v25;
            if ( !v25 )
              goto LABEL_26;
            do
            {
              v18 = *(unsigned __int16 *)((char *)v17 + (char *)String1 - v25);
              v19 = *v17 - v18;
              if ( v19 )
                break;
              ++v17;
            }
            while ( v18 );
            if ( v19 || (v27 = 0, bIgnoreCase = &v27, (int)RtlGetUILanguageInfo(8, String1, 0) < 0) || (v27 & 4) != 0 )
            {
LABEL_26:
              v16 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 104LL))(v12, v26);
              if ( v16 < 0 )
              {
                v20 = 163;
                goto LABEL_31;
              }
            }
            else
            {
              v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v12 + 88LL))(v12, 0, v26);
              if ( v16 < 0 )
              {
                v20 = 159;
                goto LABEL_31;
              }
            }
            wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::~com_ptr_t<OobeZdpManager,wil::err_exception_policy>(&v26);
            v10 = v30;
          }
          else
          {
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x95,
              (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
              (const char *)0x8000FFFFLL,
              (int)bIgnoreCase);
          }
        }
      }
      else
      {
        wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x83, v13, v14);
      }
      ++v11;
    }
    v28 = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 56LL))(v12, &v28);
    v16 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
        (const char *)(unsigned int)v21,
        (int)bIgnoreCase);
      goto LABEL_32;
    }
    if ( v28 )
    {
      v22 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v12 + 64LL))(v12, a2);
      v8 = v22;
      if ( v22 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v25);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v29);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
        (const char *)(unsigned int)v22,
        (int)bIgnoreCase);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v25);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAA,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
        (const char *)0x8000FFFFLL,
        (int)bIgnoreCase);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v25);
      v8 = -2147418113;
    }
    goto LABEL_40;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x75,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\winrt\\oobedisplaylanguage.cpp",
    (const char *)0x8000FFFFLL,
    (int)bIgnoreCase);
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v29);
  return 2147549183LL;
}

```

## disassembly

```asm
0x180089e60  mov     [rsp-8+arg_10], rbx
0x180089e65  mov     [rsp-8+arg_18], rdi
0x180089e6a  push    rbp
0x180089e6b  push    r12
0x180089e6d  push    r13
0x180089e6f  push    r14
0x180089e71  push    r15
0x180089e73  lea     rbp, [rsp-230h]
0x180089e7b  sub     rsp, 330h
0x180089e82  mov     rax, cs:__security_cookie
0x180089e89  xor     rax, rsp
0x180089e8c  mov     [rbp+250h+var_30], rax
0x180089e93  mov     r13, rdx
0x180089e96  mov     rdi, rcx
0x180089e99  call    ?IsEnabled@CloudExperienceHostCoreTelemetry@@SA_NE_K@Z; CloudExperienceHostCoreTelemetry::IsEnabled(uchar,unsigned __int64)
0x180089e9e  test    al, al
0x180089ea0  jz      short loc_180089EBB
0x180089ea2  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5eb5719585a1dfff1c0403c1b5c6f80a_@@CA@XZ; _lambda_5eb5719585a1dfff1c0403c1b5c6f80a_::_lambda_invoker_cdecl_(void)
0x180089ea9  call    ?get@?$static_lazy@VCloudExperienceHostCoreTelemetry@@@details@wil@@QEAAPEAVCloudExperienceHostCoreTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CloudExperienceHostCoreTelemetry>::get(void (*)(void))
0x180089eae  lea     rdx, aCloudexperienc_1; "CloudExperienceHostAPI::OobeDisplayLang"...
0x180089eb5  call    ?GlobalizationState_@CloudExperienceHostCoreTelemetry@@QEAAXPEBD@Z; CloudExperienceHostCoreTelemetry::GlobalizationState_(char const *)
0x180089eba  nop
0x180089ebb  mov     qword ptr [r13+0], 0
0x180089ec3  mov     [rsp+350h+var_308], 0
0x180089ecc  lea     rdx, [rsp+350h+var_308]
0x180089ed1  call    ??$CreateExternalObjectVector@UIOobeDisplayLanguage@CloudExperienceHostAPI@@V?$Vector@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@U?$DefaultEqualityPredicate@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@@4567@U?$DefaultVectorOptions@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@@4567@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@U?$DefaultEqualityPredicate@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@@4567@U?$DefaultVectorOptions@PEAUIOobeDisplayLanguage@CloudExperienceHostAPI@@@4567@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<CloudExperienceHostAPI::IOobeDisplayLanguage,Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeDisplayLanguage *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeDisplayLanguage *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeDisplayLanguage *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeDisplayLanguage *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeDisplayLanguage *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeDisplayLanguage *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeDisplayLanguage *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeDisplayLanguage *>> * *)
0x180089ed6  mov     ebx, eax
0x180089ed8  test    eax, eax
0x180089eda  jns     short loc_180089EFC
0x180089edc  mov     rcx, [rbp+258h]; this
0x180089ee3  mov     r9d, eax; char *
0x180089ee6  lea     r8, aShellOobeMachi_7; "shell\\oobe\\machine\\plugins\\adapters"...
0x180089eed  mov     edx, 6Bh ; 'k'; void *
0x180089ef2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089ef7  jmp     loc_18008A1F5
0x180089efc  mov     r12, [rdi+38h]
0x180089f00  lea     rax, GetSupportedUILanguages
0x180089f07  test    r12, r12
0x180089f0a  cmovz   r12, rax
0x180089f0e  mov     r9d, 1
0x180089f14  xor     r8d, r8d
0x180089f17  xor     edx, edx
0x180089f19  xor     ecx, ecx
0x180089f1b  mov     rax, r12
0x180089f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089f23  mov     r14d, eax
0x180089f26  mov     [rsp+350h+var_300], eax
0x180089f2a  test    eax, eax
0x180089f2c  jz      loc_18008A203
0x180089f32  xor     ecx, ecx
0x180089f34  mov     [rbp+250h+String2], cx
0x180089f38  lea     rcx, [rsp+350h+var_320]
0x180089f3d  call    ?GetSystemPreferredUILanguage@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; GetSystemPreferredUILanguage(void)
0x180089f42  nop
0x180089f43  xor     r15d, r15d
0x180089f46  lea     rdi, aShellOobeMachi_7; "shell\\oobe\\machine\\plugins\\adapters"...
0x180089f4d  mov     rbx, [rsp+350h+var_308]
0x180089f52  cmp     r15d, r14d
0x180089f55  jnb     loc_18008A133
0x180089f5b  mov     r9d, 1
0x180089f61  lea     r8d, [r9+54h]
0x180089f65  lea     rdx, [rsp+350h+String1]
0x180089f6a  mov     ecx, r15d
0x180089f6d  mov     rax, r12
0x180089f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089f75  test    eax, eax
0x180089f77  jnz     short loc_180089F8F
0x180089f79  mov     rcx, [rbp+258h]; this
0x180089f80  mov     edx, 83h; void *
0x180089f85  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180089f8a  jmp     loc_18008A0EF
0x180089f8f  mov     [rsp+350h+bIgnoreCase], 1; int
0x180089f97  or      eax, 0FFFFFFFFh
0x180089f9a  mov     r9d, eax; cchCount2
0x180089f9d  lea     r8, [rbp+250h+String2]; lpString2
0x180089fa1  mov     edx, eax; cchCount1
0x180089fa3  lea     rcx, [rsp+350h+String1]; lpString1
0x180089fa8  call    cs:__imp_CompareStringOrdinal
0x180089fae  cmp     eax, 2
0x180089fb1  jz      loc_18008A0EF
0x180089fb7  lea     r8, [rsp+350h+String1]; unsigned __int16 *
0x180089fbc  mov     edx, 55h ; 'U'; unsigned __int64
0x180089fc1  lea     rcx, [rbp+250h+String2]; unsigned __int16 *
0x180089fc5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180089fca  mov     rcx, [rbp+258h]; this
0x180089fd1  test    eax, eax
0x180089fd3  jns     short loc_180089FE5
0x180089fd5  mov     r9d, eax; char *
0x180089fd8  mov     r8, rdi; unsigned int
0x180089fdb  mov     edx, 8Eh; void *
0x180089fe0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180089fe5  mov     r8d, 0AEh
0x180089feb  lea     rdx, [rbp+250h+var_190]
0x180089ff2  lea     rcx, [rsp+350h+String1]
0x180089ff7  call    GetNativeDisplayNameEx
0x180089ffc  test    eax, eax
0x180089ffe  jnz     short loc_18008A01F
0x18008a000  mov     rcx, [rbp+258h]; this
0x18008a007  mov     r9d, 8000FFFFh; char *
0x18008a00d  mov     r8, rdi; unsigned int
0x18008a010  mov     edx, 95h; void *
0x18008a015  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18008a01a  jmp     loc_18008A0EF
0x18008a01f  mov     [rsp+350h+var_318], 0
0x18008a028  lea     r8, [rbp+250h+var_190]
0x18008a02f  lea     rdx, [rsp+350h+String1]
0x18008a034  lea     rcx, [rsp+350h+var_318]
0x18008a039  call    ??$MakeAndInitialize@VOobeDisplayLanguage@CloudExperienceHostAPI@@V12@AEAY0FF@GAEAY0KO@G@Details@WRL@Microsoft@@YAJPEAPEAVOobeDisplayLanguage@CloudExperienceHostAPI@@AEAY0FF@GAEAY0KO@G@Z; Microsoft::WRL::Details::MakeAndInitialize<CloudExperienceHostAPI::OobeDisplayLanguage,CloudExperienceHostAPI::OobeDisplayLanguage,ushort (&)[85],ushort (&)[174]>(CloudExperienceHostAPI::OobeDisplayLanguage * *,ushort (&)[85],ushort (&)[174])
0x18008a03e  mov     r14d, eax
0x18008a041  test    eax, eax
0x18008a043  js      loc_18008A0FE
0x18008a049  mov     rax, [rsp+350h+var_320]
0x18008a04e  test    rax, rax
0x18008a051  jz      short loc_18008A0C5
0x18008a053  lea     r8, [rsp+350h+String1]
0x18008a058  sub     r8, rax
0x18008a05b  movzx   edx, word ptr [rax]
0x18008a05e  movzx   ecx, word ptr [rax+r8]
0x18008a063  sub     edx, ecx
0x18008a065  jnz     short loc_18008A06F
0x18008a067  add     rax, 2
0x18008a06b  test    ecx, ecx
0x18008a06d  jnz     short loc_18008A05B
0x18008a06f  test    edx, edx
0x18008a071  jnz     short loc_18008A0C5
0x18008a073  mov     [rsp+350h+var_310], edx
0x18008a077  lea     rax, [rsp+350h+var_310]
0x18008a07c  mov     qword ptr [rsp+350h+bIgnoreCase], rax
0x18008a081  xor     r9d, r9d
0x18008a084  xor     r8d, r8d
0x18008a087  lea     rdx, [rsp+350h+String1]
0x18008a08c  lea     ecx, [r9+8]
0x18008a090  call    cs:__imp_RtlGetUILanguageInfo
0x18008a096  test    eax, eax
0x18008a098  js      short loc_18008A0C5
0x18008a09a  test    byte ptr [rsp+350h+var_310], 4
0x18008a09f  jnz     short loc_18008A0C5
0x18008a0a1  mov     rax, [rbx]
0x18008a0a4  mov     r8, [rsp+350h+var_318]
0x18008a0a9  xor     edx, edx
0x18008a0ab  mov     rcx, rbx
0x18008a0ae  mov     rax, [rax+58h]
0x18008a0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a0b7  mov     r14d, eax
0x18008a0ba  test    eax, eax
0x18008a0bc  jns     short loc_18008A0E0
0x18008a0be  mov     edx, 9Fh
0x18008a0c3  jmp     short loc_18008A103
0x18008a0c5  mov     rax, [rbx]
0x18008a0c8  mov     rdx, [rsp+350h+var_318]
0x18008a0cd  mov     rcx, rbx
0x18008a0d0  mov     rax, [rax+68h]
0x18008a0d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a0d9  mov     r14d, eax
0x18008a0dc  test    eax, eax
0x18008a0de  js      short loc_18008A0F7
0x18008a0e0  lea     rcx, [rsp+350h+var_318]
0x18008a0e5  call    ??1?$com_ptr_t@VOobeZdpManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::~com_ptr_t<OobeZdpManager,wil::err_exception_policy>(void)
0x18008a0ea  mov     r14d, [rsp+350h+var_300]
0x18008a0ef  inc     r15d
0x18008a0f2  jmp     loc_180089F52
0x18008a0f7  mov     edx, 0A3h
0x18008a0fc  jmp     short loc_18008A103
0x18008a0fe  mov     edx, 9Ah; void *
0x18008a103  mov     rcx, [rbp+258h]; this
0x18008a10a  mov     r9d, r14d; char *
0x18008a10d  mov     r8, rdi; unsigned int
0x18008a110  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a115  nop
0x18008a116  lea     rcx, [rsp+350h+var_318]
0x18008a11b  call    ??1?$com_ptr_t@VOobeZdpManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<OobeZdpManager,wil::err_exception_policy>::~com_ptr_t<OobeZdpManager,wil::err_exception_policy>(void)
0x18008a120  nop
0x18008a121  lea     rcx, [rsp+350h+var_320]
0x18008a126  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008a12b  mov     ebx, r14d
0x18008a12e  jmp     loc_18008A1F5
0x18008a133  mov     [rsp+350h+var_30C], 0
0x18008a13b  mov     rax, [rbx]
0x18008a13e  lea     rdx, [rsp+350h+var_30C]
0x18008a143  mov     rcx, rbx
0x18008a146  mov     rax, [rax+38h]
0x18008a14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a14f  mov     r14d, eax
0x18008a152  test    eax, eax
0x18008a154  jns     short loc_18008A16F
0x18008a156  mov     rcx, [rbp+258h]; this
0x18008a15d  mov     r9d, eax; char *
0x18008a160  mov     r8, rdi; unsigned int
0x18008a163  mov     edx, 0A9h; void *
0x18008a168  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a16d  jmp     short loc_18008A121
0x18008a16f  cmp     [rsp+350h+var_30C], 0
0x18008a174  jbe     short loc_18008A1CB
0x18008a176  mov     rax, [rbx]
0x18008a179  mov     rdx, r13
0x18008a17c  mov     rcx, rbx
0x18008a17f  mov     rax, [rax+40h]
0x18008a183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008a188  mov     ebx, eax
0x18008a18a  test    eax, eax
0x18008a18c  jns     short loc_18008A1B2
0x18008a18e  mov     rcx, [rbp+258h]; this
0x18008a195  mov     r9d, eax; char *
0x18008a198  mov     r8, rdi; unsigned int
0x18008a19b  mov     edx, 0ACh; void *
0x18008a1a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a1a5  nop
0x18008a1a6  lea     rcx, [rsp+350h+var_320]
0x18008a1ab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008a1b0  jmp     short loc_18008A1F5
0x18008a1b2  lea     rcx, [rsp+350h+var_320]
0x18008a1b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008a1bc  nop
0x18008a1bd  lea     rcx, [rsp+350h+var_308]
0x18008a1c2  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18008a1c7  xor     eax, eax
0x18008a1c9  jmp     short loc_18008A231
0x18008a1cb  mov     rcx, [rbp+258h]; this
0x18008a1d2  mov     r9d, 8000FFFFh; char *
0x18008a1d8  mov     r8, rdi; unsigned int
0x18008a1db  mov     edx, 0AAh; void *
0x18008a1e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a1e5  nop
0x18008a1e6  lea     rcx, [rsp+350h+var_320]
0x18008a1eb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008a1f0  mov     ebx, 8000FFFFh
0x18008a1f5  lea     rcx, [rsp+350h+var_308]
0x18008a1fa  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18008a1ff  mov     eax, ebx
0x18008a201  jmp     short loc_18008A231
0x18008a203  mov     rcx, [rbp+258h]; this
0x18008a20a  mov     r9d, 8000FFFFh; char *
0x18008a210  lea     r8, aShellOobeMachi_7; "shell\\oobe\\machine\\plugins\\adapters"...
0x18008a217  mov     edx, 75h ; 'u'; void *
0x18008a21c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a221  nop
0x18008a222  lea     rcx, [rsp+350h+var_308]
0x18008a227  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18008a22c  mov     eax, 8000FFFFh
0x18008a231  mov     rcx, [rbp+250h+var_30]
0x18008a238  xor     rcx, rsp; StackCookie
0x18008a23b  call    __security_check_cookie
0x18008a240  lea     r11, [rsp+350h+var_20]
0x18008a248  mov     rbx, [r11+40h]
0x18008a24c  mov     rdi, [r11+48h]
0x18008a250  mov     rsp, r11
0x18008a253  pop     r15
0x18008a255  pop     r14
0x18008a257  pop     r13
0x18008a259  pop     r12
0x18008a25b  pop     rbp
0x18008a25c  retn
```
