# CloudExperienceHostAPI::BackupRestoreManager::_CopyToUserProfile(Windows::Internal::Storage::Cloud::Restore::RestoreAssetType,HSTRING__ *)

- ea: `0x18002c588`
- end: `0x18002c873`
- name: `?_CopyToUserProfile@BackupRestoreManager@CloudExperienceHostAPI@@CAJW4RestoreAssetType@Restore@Cloud@Storage@Internal@Windows@@PEAUHSTRING__@@@Z`
- size: `747`
- prototype: `__int64 __fastcall(int, HSTRING)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002ae20`
- `0x18002aeb0`

## callees

- `0x180002b60`
- `0x180006868`
- `0x1800076b4`
- `0x1800076d4`
- `0x180009100`
- `0x180009760`
- `0x1800117bc`
- `0x180011db0`
- `0x180019590`
- `0x1800266f8`
- `0x1800267a8`
- `0x18002c588`
- `0x18002dadc`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c5ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c761`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c5ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c753`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c761`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002c770`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18002c770`

## string_xrefs

- `0x18002c5e4`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002c670`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002c6e2`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002c782`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`
- `0x18002c7cb`: `shellcommon\shell\oobe\core\components\winrt\backuprestoremanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CloudExperienceHostAPI::BackupRestoreManager::_CopyToUserProfile(int a1, HSTRING a2)
{
  int v4; // eax
  unsigned int LastError; // ebx
  const WCHAR *StringRawBuffer; // rax
  const unsigned __int16 *v7; // rdx
  __int64 v8; // r14
  void *v9; // rdi
  __int64 (__fastcall *v10)(void *, __int64, bool, __int64); // rbx
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdx
  void **v15; // rcx
  void **p_last_path_segment; // rcx
  const WCHAR *v17; // rbx
  const WCHAR *v18; // rax
  const char *v19; // r9
  int v20; // eax
  __int64 v21; // rdx
  int v23; // [rsp+20h] [rbp-60h]
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  void *last_path_segment; // [rsp+38h] [rbp-48h] BYREF
  void *v26; // [rsp+40h] [rbp-40h] BYREF
  void *v27; // [rsp+48h] [rbp-38h] BYREF
  _BYTE v28[24]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v29; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v27 = 0;
  v4 = CloudExperienceHostCreateOOBEUserObject(
         &GUID_29a83fc7_d3a6_43a5_b3e3_ecffb558b4b2,
         &GUID_1d32528d_4cdb_404a_b580_b9e738429631,
         &v27);
  LastError = v4;
  if ( v4 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    last_path_segment = (void *)wil::find_last_path_segment(StringRawBuffer, v7);
    v8 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v28, &last_path_segment) + 24);
    v29 = 0;
    string = 0;
    v9 = v27;
    v10 = *(__int64 (__fastcall **)(void *, __int64, bool, __int64))(*(_QWORD *)v27 + 56LL);
    v11 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(&string);
    v12 = v10(v9, v8, a1 != 0, v11);
    LastError = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x118,
        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
        (const char *)(unsigned int)v12,
        v23);
LABEL_5:
      Windows::Internal::String::~String((Windows::Internal::String *)&string);
      goto LABEL_31;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59011689>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59011689>::GetImpl'::`2'::impl) )
    {
      if ( !IsUserOOBE() )
      {
        v17 = WindowsGetStringRawBuffer(string, 0);
        v18 = WindowsGetStringRawBuffer(a2, 0);
        if ( !CopyFileW(v18, v17, 0) )
        {
          LastError = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x12E,
                        (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
                        v19);
          goto LABEL_5;
        }
LABEL_30:
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        LastError = 0;
        goto LABEL_31;
      }
      v26 = 0;
      v13 = CloudExperienceHostCreateElevatedObject(
              &GUID_c54a88e2_d248_42aa_a147_70b66660ab43,
              &GUID_25ab4e55_0787_4fdf_8892_4cbfdf402a70,
              &v26);
      LastError = v13;
      if ( v13 < 0 )
      {
        v14 = 288;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
          (const char *)(unsigned int)v13,
          v23);
        v15 = &v26;
LABEL_11:
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(v15);
        goto LABEL_5;
      }
      v13 = (*(__int64 (__fastcall **)(void *, HSTRING, HSTRING))(*(_QWORD *)v26 + 56LL))(v26, a2, string);
      LastError = v13;
      if ( v13 < 0 )
      {
        v14 = 289;
        goto LABEL_10;
      }
      if ( !a1 )
      {
        v13 = (*(__int64 (__fastcall **)(void *, HSTRING))(*(_QWORD *)v26 + 64LL))(v26, string);
        LastError = v13;
        if ( v13 < 0 )
        {
          v14 = 297;
          goto LABEL_10;
        }
      }
      p_last_path_segment = &v26;
LABEL_29:
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(p_last_path_segment);
      goto LABEL_30;
    }
    last_path_segment = 0;
    v20 = CloudExperienceHostCreateElevatedObject(
            &GUID_c54a88e2_d248_42aa_a147_70b66660ab43,
            &GUID_25ab4e55_0787_4fdf_8892_4cbfdf402a70,
            &last_path_segment);
    LastError = v20;
    if ( v20 >= 0 )
    {
      v20 = (*(__int64 (__fastcall **)(void *, HSTRING, HSTRING))(*(_QWORD *)last_path_segment + 56LL))(
              last_path_segment,
              a2,
              string);
      LastError = v20;
      if ( v20 >= 0 )
      {
        if ( a1
          || (v20 = (*(__int64 (__fastcall **)(void *, HSTRING))(*(_QWORD *)last_path_segment + 64LL))(
                      last_path_segment,
                      string),
              LastError = v20,
              v20 >= 0) )
        {
          p_last_path_segment = &last_path_segment;
          goto LABEL_29;
        }
        v21 = 317;
      }
      else
      {
        v21 = 309;
      }
    }
    else
    {
      v21 = 308;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
      (const char *)(unsigned int)v20,
      v23);
    v15 = &last_path_segment;
    goto LABEL_11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x113,
    (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\backuprestoremanager.cpp",
    (const char *)(unsigned int)v4,
    v23);
LABEL_31:
  wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v27);
  return LastError;
}

```

## disassembly

```asm
0x18002c588  mov     [rsp-28h+arg_0], rbx
0x18002c58d  mov     [rsp-28h+arg_10], rsi
0x18002c592  push    rbp
0x18002c593  push    rdi
0x18002c594  push    r12
0x18002c596  push    r14
0x18002c598  push    r15
0x18002c59a  mov     rbp, rsp
0x18002c59d  sub     rsp, 80h
0x18002c5a4  mov     rax, cs:__security_cookie
0x18002c5ab  xor     rax, rsp
0x18002c5ae  mov     [rbp+var_10], rax
0x18002c5b2  mov     r12, rdx
0x18002c5b5  mov     r15d, ecx
0x18002c5b8  mov     [rbp+var_38], 0
0x18002c5c0  lea     r8, [rbp+var_38]; void **
0x18002c5c4  lea     rdx, _GUID_1d32528d_4cdb_404a_b580_b9e738429631; struct _GUID *
0x18002c5cb  lea     rcx, _GUID_29a83fc7_d3a6_43a5_b3e3_ecffb558b4b2; struct _GUID *
0x18002c5d2  call    ?CloudExperienceHostCreateOOBEUserObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateOOBEUserObject(_GUID const &,_GUID const &,void * *)
0x18002c5d7  mov     ebx, eax
0x18002c5d9  test    eax, eax
0x18002c5db  jns     short loc_18002C5FA
0x18002c5dd  mov     rcx, [rbp+28h]; this
0x18002c5e1  mov     r9d, eax; char *
0x18002c5e4  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002c5eb  mov     edx, 113h; void *
0x18002c5f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c5f5  jmp     loc_18002C840
0x18002c5fa  xor     edx, edx; length
0x18002c5fc  mov     rcx, r12; string
0x18002c5ff  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c605  mov     rcx, rax; lpStringSource
0x18002c608  call    ?find_last_path_segment@wil@@YAPEBGPEBG@Z; wil::find_last_path_segment(ushort const *)
0x18002c60d  mov     [rbp+var_48], rax
0x18002c611  lea     rdx, [rbp+var_48]
0x18002c615  lea     rcx, [rbp+var_30]
0x18002c619  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002c61e  mov     r14, [rax+18h]
0x18002c622  mov     [rbp+var_18], 0
0x18002c62a  xor     esi, esi
0x18002c62c  test    r15d, r15d
0x18002c62f  setnz   sil
0x18002c633  mov     [rbp+string], 0
0x18002c63b  mov     rdi, [rbp+var_38]
0x18002c63f  mov     rax, [rdi]
0x18002c642  mov     rbx, [rax+38h]
0x18002c646  lea     rcx, [rbp+string]
0x18002c64a  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHSTRING__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::put(void)
0x18002c64f  mov     r9, rax
0x18002c652  mov     r8d, esi
0x18002c655  mov     rdx, r14
0x18002c658  mov     rcx, rdi
0x18002c65b  mov     rax, rbx
0x18002c65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c663  mov     ebx, eax
0x18002c665  test    eax, eax
0x18002c667  jns     short loc_18002C690
0x18002c669  mov     rcx, [rbp+28h]; this
0x18002c66d  mov     r9d, eax; char *
0x18002c670  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002c677  mov     edx, 118h; void *
0x18002c67c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c681  nop
0x18002c682  lea     rcx, [rbp+string]; this
0x18002c686  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002c68b  jmp     loc_18002C840
0x18002c690  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_59011689@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_59011689@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59011689> `wil::Feature<__WilFeatureTraits_Feature_59011689>::GetImpl(void)'::`2'::impl
0x18002c697  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_59011689@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_59011689>::__private_IsEnabled(void)
0x18002c69c  test    al, al
0x18002c69e  jz      loc_18002C79A
0x18002c6a4  call    ?IsUserOOBE@@YA_NXZ; IsUserOOBE(void)
0x18002c6a9  test    al, al
0x18002c6ab  jz      loc_18002C74D
0x18002c6b1  mov     [rbp+var_40], 0
0x18002c6b9  lea     r8, [rbp+var_40]; void **
0x18002c6bd  lea     rdx, _GUID_25ab4e55_0787_4fdf_8892_4cbfdf402a70; struct _GUID *
0x18002c6c4  lea     rcx, _GUID_c54a88e2_d248_42aa_a147_70b66660ab43; struct _GUID *
0x18002c6cb  call    ?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)
0x18002c6d0  mov     ebx, eax
0x18002c6d2  test    eax, eax
0x18002c6d4  jns     short loc_18002C6FA
0x18002c6d6  mov     edx, 120h; void *
0x18002c6db  mov     rcx, [rbp+28h]; this
0x18002c6df  mov     r9d, eax; char *
0x18002c6e2  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002c6e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c6ee  nop
0x18002c6ef  lea     rcx, [rbp+var_40]
0x18002c6f3  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18002c6f8  jmp     short loc_18002C682
0x18002c6fa  mov     rcx, [rbp+var_40]
0x18002c6fe  mov     rax, [rcx]
0x18002c701  mov     r8, [rbp+string]
0x18002c705  mov     rdx, r12
0x18002c708  mov     rax, [rax+38h]
0x18002c70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c711  mov     ebx, eax
0x18002c713  test    eax, eax
0x18002c715  jns     short loc_18002C71E
0x18002c717  mov     edx, 121h
0x18002c71c  jmp     short loc_18002C6DB
0x18002c71e  test    r15d, r15d
0x18002c721  jnz     short loc_18002C744
0x18002c723  mov     rcx, [rbp+var_40]
0x18002c727  mov     rax, [rcx]
0x18002c72a  mov     rdx, [rbp+string]
0x18002c72e  mov     rax, [rax+40h]
0x18002c732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c737  mov     ebx, eax
0x18002c739  test    eax, eax
0x18002c73b  jns     short loc_18002C744
0x18002c73d  mov     edx, 129h
0x18002c742  jmp     short loc_18002C6DB
0x18002c744  lea     rcx, [rbp+var_40]
0x18002c748  jmp     loc_18002C82F
0x18002c74d  xor     edx, edx; length
0x18002c74f  mov     rcx, [rbp+string]; string
0x18002c753  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c759  mov     rbx, rax
0x18002c75c  xor     edx, edx; length
0x18002c75e  mov     rcx, r12; string
0x18002c761  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c767  xor     r8d, r8d; bFailIfExists
0x18002c76a  mov     rdx, rbx; lpNewFileName
0x18002c76d  mov     rcx, rax; lpExistingFileName
0x18002c770  call    cs:__imp_CopyFileW
0x18002c776  test    eax, eax
0x18002c778  jnz     loc_18002C835
0x18002c77e  mov     rcx, [rbp+28h]; this
0x18002c782  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002c789  mov     edx, 12Eh; void *
0x18002c78e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c793  mov     ebx, eax
0x18002c795  jmp     loc_18002C682
0x18002c79a  mov     [rbp+var_48], 0
0x18002c7a2  lea     r8, [rbp+var_48]; void **
0x18002c7a6  lea     rdx, _GUID_25ab4e55_0787_4fdf_8892_4cbfdf402a70; struct _GUID *
0x18002c7ad  lea     rcx, _GUID_c54a88e2_d248_42aa_a147_70b66660ab43; struct _GUID *
0x18002c7b4  call    ?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)
0x18002c7b9  mov     ebx, eax
0x18002c7bb  test    eax, eax
0x18002c7bd  jns     short loc_18002C7E1
0x18002c7bf  mov     edx, 134h; void *
0x18002c7c4  mov     rcx, [rbp+28h]; this
0x18002c7c8  mov     r9d, eax; char *
0x18002c7cb  lea     r8, aShellcommonShe_12; "shellcommon\\shell\\oobe\\core\\compone"...
0x18002c7d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c7d7  nop
0x18002c7d8  lea     rcx, [rbp+var_48]
0x18002c7dc  jmp     loc_18002C6F3
0x18002c7e1  mov     rcx, [rbp+var_48]
0x18002c7e5  mov     rax, [rcx]
0x18002c7e8  mov     r8, [rbp+string]
0x18002c7ec  mov     rdx, r12
0x18002c7ef  mov     rax, [rax+38h]
0x18002c7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7f8  mov     ebx, eax
0x18002c7fa  test    eax, eax
0x18002c7fc  jns     short loc_18002C805
0x18002c7fe  mov     edx, 135h
0x18002c803  jmp     short loc_18002C7C4
0x18002c805  test    r15d, r15d
0x18002c808  jnz     short loc_18002C82B
0x18002c80a  mov     rcx, [rbp+var_48]
0x18002c80e  mov     rax, [rcx]
0x18002c811  mov     rdx, [rbp+string]
0x18002c815  mov     rax, [rax+40h]
0x18002c819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c81e  mov     ebx, eax
0x18002c820  test    eax, eax
0x18002c822  jns     short loc_18002C82B
0x18002c824  mov     edx, 13Dh
0x18002c829  jmp     short loc_18002C7C4
0x18002c82b  lea     rcx, [rbp+var_48]
0x18002c82f  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18002c834  nop
0x18002c835  lea     rcx, [rbp+string]; this
0x18002c839  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002c83e  xor     ebx, ebx
0x18002c840  lea     rcx, [rbp+var_38]
0x18002c844  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18002c849  mov     eax, ebx
0x18002c84b  mov     rcx, [rbp+var_10]
0x18002c84f  xor     rcx, rsp; StackCookie
0x18002c852  call    __security_check_cookie
0x18002c857  lea     r11, [rsp+80h+var_s0]
0x18002c85f  mov     rbx, [r11+30h]
0x18002c863  mov     rsi, [r11+40h]
0x18002c867  mov     rsp, r11
0x18002c86a  pop     r15
0x18002c86c  pop     r14
0x18002c86e  pop     r12
0x18002c870  pop     rdi
0x18002c871  pop     rbp
0x18002c872  retn
```
