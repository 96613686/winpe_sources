# CloudExperienceHostAPI::OobeSettingsStaticsCore::CommitSettingsAsyncForUser(Windows::System::IUser *,Windows::Foundation::Collections::IVectorView<CloudExperienceHostAPI::IOobeSetting *> *,uint,Windows::Foundation::IAsyncAction * *)

- ea: `0x18004f420`
- end: `0x18004f780`
- name: `?CommitSettingsAsyncForUser@OobeSettingsStaticsCore@CloudExperienceHostAPI@@UEAAJPEAUIUser@System@Windows@@PEAU?$IVectorView@PEAUIOobeSetting@CloudExperienceHostAPI@@@Collections@Foundation@5@IPEAPEAUIAsyncAction@85@@Z`
- size: `864`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800076d4`
- `0x180009760`
- `0x18001430c`
- `0x180015544`
- `0x18004cb78`
- `0x18004ce04`
- `0x18004f420`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f4e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f5a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f5f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f4e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f5a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004f5f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004f519`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004f519`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004f54e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004f54e`

## string_xrefs

- `0x18004f486`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`
- `0x18004f5e7`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`
- `0x18004f615`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`
- `0x18004f700`: `shellcommon\shell\oobe\core\components\winrt\oobesettingscore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CloudExperienceHostAPI::OobeSettingsStaticsCore::CommitSettingsAsyncForUser(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        unsigned int a4,
        _QWORD *a5)
{
  int v7; // eax
  unsigned int v8; // ebx
  __int64 result; // rax
  unsigned int v10; // r14d
  unsigned int v11; // r15d
  unsigned int i; // esi
  __int64 v13; // rax
  int v14; // eax
  _QWORD *v15; // rdi
  __int64 (__fastcall *v16)(_QWORD *, HSTRING *); // rbx
  int v17; // eax
  const WCHAR *StringRawBuffer; // rbx
  unsigned int j; // edi
  __int64 v20; // rdx
  __int64 v21; // r9
  HSTRING *v22; // rax
  char v23; // bl
  HSTRING v24; // rcx
  __int64 *v25; // rbx
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rax
  const char *v29; // r9
  int bIgnoreCase; // [rsp+20h] [rbp-68h]
  unsigned int v31; // [rsp+30h] [rbp-58h] BYREF
  HSTRING string; // [rsp+38h] [rbp-50h] BYREF
  _QWORD *v33; // [rsp+40h] [rbp-48h] BYREF
  char v34[8]; // [rsp+48h] [rbp-40h] BYREF
  _QWORD v35[2]; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  __int64 v37; // [rsp+A0h] [rbp+18h] BYREF
  unsigned int v38; // [rsp+A8h] [rbp+20h]

  v38 = a4;
  LODWORD(v37) = 0;
  *a5 = 0;
  v31 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*a3 + 56))(a3, &v31);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v10 = 0;
    v11 = 0;
    for ( i = 0; i < v31; ++i )
    {
      v13 = *a3;
      v33 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD **))(v13 + 48))(a3, i, &v33);
      v8 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17B,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
          (const char *)(unsigned int)v14,
          bIgnoreCase);
LABEL_22:
        wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v33);
        return v8;
      }
      string = 0;
      v15 = v33;
      v16 = *(__int64 (__fastcall **)(_QWORD *, HSTRING *))(*v33 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v17 = v16(v15, &string);
      v8 = v17;
      if ( v17 < 0 )
      {
        v20 = 381;
LABEL_19:
        v21 = (unsigned int)v17;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
          (const char *)v21,
          bIgnoreCase);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_22;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      for ( j = 0; ; ++j )
      {
        if ( j >= 8 )
        {
          v8 = -2147024809;
          v21 = 2147942487LL;
          v20 = 383;
          goto LABEL_20;
        }
        if ( CompareStringOrdinal(StringRawBuffer, -1, `CanonicalNameFromProtectPcId'::`2'::canonicalNames[j], -1, 0) == 2 )
          break;
      }
      LOBYTE(v37) = 0;
      v17 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v33 + 152LL))(v33, &v37);
      v8 = v17;
      if ( v17 < 0 )
      {
        v20 = 386;
        goto LABEL_19;
      }
      if ( (_BYTE)v37 )
        v10 |= 1 << j;
      v11 |= 1 << j;
      WindowsDeleteString(string);
      string = 0;
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v33);
    }
    try
    {
      if ( a2 )
      {
        v22 = (HSTRING *)convert_from_abi<winrt::Windows::System::User>(v35, a2);
        v23 = 1;
        v24 = *v22;
      }
      else
      {
        v22 = (HSTRING *)v34;
        v23 = 2;
        v24 = 0;
      }
      *v22 = 0;
      string = v24;
      if ( (v23 & 2) != 0 )
      {
        v23 &= ~2u;
        winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)v34);
      }
      if ( (v23 & 1) != 0 )
        winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)v35);
      winrt::get_partial_trust_activation_factory_for_user<winrt::CloudExperienceHostAPI::OobeSettingsManagerStaticsCore,winrt::CloudExperienceHostAPI::IOobeSettingsManager>(
        (winrt *)&v33,
        (struct winrt::Windows::System::User *)&string);
      v25 = v33;
      v35[0] = v33;
      if ( v33 )
        (*(void (__fastcall **)(_QWORD *))(*v33 + 8LL))(v33);
      v37 = 0;
      v26 = *v25;
      v37 = 0;
      v27 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD))(v26 + 56))(v25, v10, v11, v38);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x193,
          (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
          (const char *)(unsigned int)v27,
          (int)&v37);
      v28 = v37;
      v37 = 0;
      *a5 = v28;
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(&v37);
      wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(v35);
      winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)&v33);
      winrt::Windows::Storage::IStorageFolder::~IStorageFolder((winrt::Windows::Storage::IStorageFolder *)&string);
      result = 0;
    }
    catch ( ... )
    {
      LODWORD(a5) = wil::details::in1diag3::Return_CaughtException(
                      retaddr,
                      (void *)0x196,
                      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
                      v29);
      return (unsigned int)a5;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x173,
      (unsigned int)"shellcommon\\shell\\oobe\\core\\components\\winrt\\oobesettingscore.cpp",
      (const char *)(unsigned int)v7,
      bIgnoreCase);
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x18004f420  mov     rax, rsp
0x18004f423  mov     [rax+8], rbx
0x18004f427  mov     [rax+10h], rsi
0x18004f42b  mov     [rax+20h], r9d
0x18004f42f  push    rdi
0x18004f430  push    r12
0x18004f432  push    r13
0x18004f434  push    r14
0x18004f436  push    r15
0x18004f438  sub     rsp, 60h
0x18004f43c  mov     r13, r8
0x18004f43f  mov     r12, rdx
0x18004f442  mov     dword ptr [rsp+88h+arg_10], 0
0x18004f44d  mov     rdi, [rsp+88h+arg_20]
0x18004f455  mov     qword ptr [rdi], 0
0x18004f45c  xor     edi, edi
0x18004f45e  mov     [rax-58h], edi
0x18004f461  mov     rax, [r8]
0x18004f464  lea     rdx, [rsp+88h+var_58]
0x18004f469  mov     rcx, r8
0x18004f46c  mov     rax, [rax+38h]
0x18004f470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f475  mov     ebx, eax
0x18004f477  test    eax, eax
0x18004f479  jns     short loc_18004F49E
0x18004f47b  mov     rcx, [rsp+88h]; this
0x18004f483  mov     r9d, eax; char *
0x18004f486  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004f48d  mov     edx, 173h; void *
0x18004f492  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f497  mov     eax, ebx
0x18004f499  jmp     loc_18004F766
0x18004f49e  mov     r14d, edi
0x18004f4a1  mov     r15d, edi
0x18004f4a4  mov     esi, edi
0x18004f4a6  cmp     esi, [rsp+88h+var_58]
0x18004f4aa  jnb     loc_18004F636
0x18004f4b0  mov     rax, [r13+0]
0x18004f4b4  mov     [rsp+88h+var_48], rdi
0x18004f4b9  lea     r8, [rsp+88h+var_48]
0x18004f4be  mov     edx, esi
0x18004f4c0  mov     rcx, r13
0x18004f4c3  mov     rax, [rax+30h]
0x18004f4c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f4cc  mov     ebx, eax
0x18004f4ce  test    eax, eax
0x18004f4d0  js      loc_18004F60A
0x18004f4d6  mov     [rsp+88h+string], rdi
0x18004f4db  mov     rdi, [rsp+88h+var_48]
0x18004f4e0  mov     rax, [rdi]
0x18004f4e3  mov     rbx, [rax+30h]
0x18004f4e7  xor     ecx, ecx; string
0x18004f4e9  call    cs:__imp_WindowsDeleteString
0x18004f4ef  mov     [rsp+88h+string], 0
0x18004f4f8  lea     rdx, [rsp+88h+string]
0x18004f4fd  mov     rcx, rdi
0x18004f500  mov     rax, rbx
0x18004f503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f508  mov     ebx, eax
0x18004f50a  test    eax, eax
0x18004f50c  js      loc_18004F5D7
0x18004f512  xor     edx, edx; length
0x18004f514  mov     rcx, [rsp+88h+string]; string
0x18004f519  call    cs:__imp_WindowsGetStringRawBuffer
0x18004f51f  mov     rbx, rax
0x18004f522  xor     edi, edi
0x18004f524  cmp     edi, 8
0x18004f527  jnb     loc_18004F5C8
0x18004f52d  movsxd  r8, edi
0x18004f530  lea     rax, ?canonicalNames@?1??CanonicalNameFromProtectPcId@@YAQEBGW4OOBE_PROTECTPC_BOOLEAN_SETTING@@@Z@4QBQEBGB; ushort const * const near * const `CanonicalNameFromProtectPcId(OOBE_PROTECTPC_BOOLEAN_SETTING)'::`2'::canonicalNames
0x18004f537  mov     [rsp+88h+bIgnoreCase], 0; bIgnoreCase
0x18004f53f  or      ecx, 0FFFFFFFFh
0x18004f542  mov     r9d, ecx; cchCount2
0x18004f545  mov     r8, [rax+r8*8]; lpString2
0x18004f549  mov     edx, ecx; cchCount1
0x18004f54b  mov     rcx, rbx; lpString1
0x18004f54e  call    cs:__imp_CompareStringOrdinal
0x18004f554  cmp     eax, 2
0x18004f557  jz      short loc_18004F55D
0x18004f559  inc     edi
0x18004f55b  jmp     short loc_18004F524
0x18004f55d  cmp     edi, 8
0x18004f560  jge     short loc_18004F5C8
0x18004f562  mov     byte ptr [rsp+88h+arg_10], 0
0x18004f56a  mov     rcx, [rsp+88h+var_48]
0x18004f56f  mov     rax, [rcx]
0x18004f572  lea     rdx, [rsp+88h+arg_10]
0x18004f57a  mov     rax, [rax+98h]
0x18004f581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f586  mov     ebx, eax
0x18004f588  test    eax, eax
0x18004f58a  js      short loc_18004F5C1
0x18004f58c  cmp     byte ptr [rsp+88h+arg_10], 0
0x18004f594  jz      short loc_18004F59A
0x18004f596  bts     r14d, edi
0x18004f59a  bts     r15d, edi
0x18004f59e  mov     rcx, [rsp+88h+string]; string
0x18004f5a3  call    cs:__imp_WindowsDeleteString
0x18004f5a9  xor     edi, edi
0x18004f5ab  mov     [rsp+88h+string], rdi
0x18004f5b0  lea     rcx, [rsp+88h+var_48]
0x18004f5b5  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004f5ba  inc     esi
0x18004f5bc  jmp     loc_18004F4A6
0x18004f5c1  mov     edx, 182h
0x18004f5c6  jmp     short loc_18004F5DC
0x18004f5c8  mov     ebx, 80070057h
0x18004f5cd  mov     r9d, ebx
0x18004f5d0  mov     edx, 17Fh
0x18004f5d5  jmp     short loc_18004F5DF
0x18004f5d7  mov     edx, 17Dh; void *
0x18004f5dc  mov     r9d, eax; char *
0x18004f5df  mov     rcx, [rsp+88h]; this
0x18004f5e7  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004f5ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f5f3  nop
0x18004f5f4  mov     rcx, [rsp+88h+string]; string
0x18004f5f9  call    cs:__imp_WindowsDeleteString
0x18004f5ff  mov     [rsp+88h+string], 0
0x18004f608  jmp     short loc_18004F627
0x18004f60a  mov     rcx, [rsp+88h]; this
0x18004f612  mov     r9d, eax; char *
0x18004f615  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004f61c  mov     edx, 17Bh; void *
0x18004f621  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f626  nop
0x18004f627  lea     rcx, [rsp+88h+var_48]
0x18004f62c  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004f631  jmp     loc_18004F497
0x18004f636  test    r12, r12
0x18004f639  jz      short loc_18004F652
0x18004f63b  mov     rdx, r12
0x18004f63e  lea     rcx, [rsp+88h+var_38]
0x18004f643  call    ??$convert_from_abi@UUser@System@Windows@winrt@@@@YA?AUUser@System@Windows@winrt@@PEAUIUnknown@@@Z; convert_from_abi<winrt::Windows::System::User>(IUnknown *)
0x18004f648  mov     ebx, 1
0x18004f64d  mov     rcx, [rax]
0x18004f650  jmp     short loc_18004F65F
0x18004f652  lea     rax, [rsp+88h+var_40]
0x18004f657  mov     ebx, 2
0x18004f65c  mov     rcx, rdi
0x18004f65f  mov     [rax], rdi
0x18004f662  mov     [rsp+88h+string], rcx
0x18004f667  test    bl, 2
0x18004f66a  jz      short loc_18004F679
0x18004f66c  and     ebx, 0FFFFFFFDh
0x18004f66f  lea     rcx, [rsp+88h+var_40]; this
0x18004f674  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x18004f679  test    bl, 1
0x18004f67c  jz      short loc_18004F688
0x18004f67e  lea     rcx, [rsp+88h+var_38]; this
0x18004f683  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x18004f688  lea     rdx, [rsp+88h+string]; struct winrt::Windows::System::User *
0x18004f68d  lea     rcx, [rsp+88h+var_48]; this
0x18004f692  call    ??$get_partial_trust_activation_factory_for_user@UOobeSettingsManagerStaticsCore@CloudExperienceHostAPI@winrt@@UIOobeSettingsManager@23@@winrt@@YA?A_PAEBUUser@System@Windows@0@@Z
0x18004f697  nop
0x18004f698  mov     rbx, [rsp+88h+var_48]
0x18004f69d  mov     [rsp+88h+var_38], rbx
0x18004f6a2  test    rbx, rbx
0x18004f6a5  jz      short loc_18004F6B7
0x18004f6a7  mov     rax, [rbx]
0x18004f6aa  mov     rcx, rbx
0x18004f6ad  mov     rax, [rax+8]
0x18004f6b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6b6  nop
0x18004f6b7  mov     [rsp+88h+arg_10], rdi
0x18004f6bf  mov     rax, [rbx]
0x18004f6c2  mov     [rsp+88h+arg_10], rdi
0x18004f6ca  lea     rcx, [rsp+88h+arg_10]
0x18004f6d2  mov     qword ptr [rsp+88h+bIgnoreCase], rcx; int
0x18004f6d7  mov     r9d, [rsp+88h+arg_18]
0x18004f6df  mov     r8d, r15d
0x18004f6e2  mov     edx, r14d
0x18004f6e5  mov     rcx, rbx
0x18004f6e8  mov     rax, [rax+38h]
0x18004f6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f6f1  mov     rcx, [rsp+88h]; this
0x18004f6f9  test    eax, eax
0x18004f6fb  jns     short loc_18004F711
0x18004f6fd  mov     r9d, eax; char *
0x18004f700  lea     r8, aShellcommonShe_19; "shellcommon\\shell\\oobe\\core\\compone"...
0x18004f707  mov     edx, 193h; void *
0x18004f70c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004f711  mov     rax, [rsp+88h+arg_10]
0x18004f719  mov     [rsp+88h+arg_10], rdi
0x18004f721  mov     rcx, [rsp+88h+arg_20]
0x18004f729  mov     [rcx], rax
0x18004f72c  lea     rcx, [rsp+88h+arg_10]
0x18004f734  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004f739  nop
0x18004f73a  lea     rcx, [rsp+88h+var_38]
0x18004f73f  call    ??1?$com_ptr_t@UIOobeUpdateSettingsElevatedManagerCore@CloudExperienceHostAPI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>::~com_ptr_t<CloudExperienceHostAPI::IOobeUpdateSettingsElevatedManagerCore,wil::err_exception_policy>(void)
0x18004f744  nop
0x18004f745  lea     rcx, [rsp+88h+var_48]; this
0x18004f74a  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x18004f74f  nop
0x18004f750  lea     rcx, [rsp+88h+string]; this
0x18004f755  call    ??1IStorageFolder@Storage@Windows@winrt@@QEAA@XZ; winrt::Windows::Storage::IStorageFolder::~IStorageFolder(void)
0x18004f75a  nop
0x18004f75b  xor     eax, eax
0x18004f75d  jmp     short loc_18004F766
0x18004f75f  mov     eax, dword ptr [rsp+88h+arg_20]
0x18004f766  lea     r11, [rsp+88h+var_28]
0x18004f76b  mov     rbx, [r11+30h]
0x18004f76f  mov     rsi, [r11+38h]
0x18004f773  mov     rsp, r11
0x18004f776  pop     r15
0x18004f778  pop     r14
0x18004f77a  pop     r13
0x18004f77c  pop     r12
0x18004f77e  pop     rdi
0x18004f77f  retn
```
