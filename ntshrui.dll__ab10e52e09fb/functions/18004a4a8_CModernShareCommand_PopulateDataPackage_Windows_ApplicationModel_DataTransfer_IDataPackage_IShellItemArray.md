# CModernShareCommand::PopulateDataPackage(Windows::ApplicationModel::DataTransfer::IDataPackage *,IShellItemArray *)

- ea: `0x18004a4a8`
- end: `0x18004aad2`
- name: `?PopulateDataPackage@CModernShareCommand@@QEAAJPEAUIDataPackage@DataTransfer@ApplicationModel@Windows@@PEAUIShellItemArray@@@Z`
- size: `1578`
- prototype: `int(CModernShareCommand *__hidden this, struct Windows::ApplicationModel::DataTransfer::IDataPackage *, struct IShellItemArray *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003b3f4`

## callees

- `0x180008900`
- `0x1800214cc`
- `0x1800223bc`
- `0x1800232c4`
- `0x180023990`
- `0x180024e44`
- `0x1800254e0`
- `0x18003d508`
- `0x180046870`
- `0x180047a28`
- `0x180047a58`
- `0x18004a4a8`
- `0x180050d90`
- `0x180050fc8`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004a92a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18004a92a`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18004a60d`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18004a60d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18004a5fb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18004a5fb`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18004a5e2`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18004a5e2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004aacb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004aacb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a76e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a7b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a7e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a76e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a7b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004a7e5`

## string_xrefs

- `0x18004a519`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004a556`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004a66c`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004a73a`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004a794`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004a83c`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004a899`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004a941`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`
- `0x18004aa21`: `shell\osshell\lmui\ntshrui\dll\shareverb.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CModernShareCommand::PopulateDataPackage(
        CModernShareCommand *this,
        struct Windows::ApplicationModel::DataTransfer::IDataPackage *a2,
        struct IShellItemArray *a3)
{
  __int64 (__fastcall *v5)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // ebx
  int StorageItemVectorFromShellItemArray; // eax
  __int64 v11; // rdx
  __int64 v12; // r9
  HRSRC Resource; // rax
  HGLOBAL v14; // rax
  _WORD *v15; // rax
  const WCHAR *v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  unsigned __int64 v19; // r9
  void *p_hstringHeader; // rcx
  __int64 (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v22)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v23; // rax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, __int64 *); // rbx
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, HSTRING *); // rbx
  int v29; // eax
  __int64 v30; // rdx
  unsigned __int64 v31; // rsi
  int EnterpriseId; // eax
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v34)(_QWORD, GUID *, __int64 *); // rdi
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, _QWORD); // rbx
  __int64 v39; // rax
  __int64 v40; // r9
  __int64 v41; // rdx
  __int64 (__fastcall ***v42)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v43)(_QWORD, GUID *, __int64 *); // rbx
  unsigned int v44; // eax
  int v45; // eax
  __int64 v46; // rbx
  __int64 (__fastcall *v47)(__int64, GUID *, __int64 *); // rdi
  int v48; // eax
  __int64 v49; // r8
  __int64 v50; // rdx
  int v52[2]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v53; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v55)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-C8h] BYREF
  __int64 v56; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v57; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v58; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v59; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v60; // [rsp+60h] [rbp-A0h]
  __int64 v61; // [rsp+68h] [rbp-98h]
  _QWORD v62[3]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v63; // [rsp+88h] [rbp-78h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-70h] BYREF
  __int64 v65; // [rsp+A8h] [rbp-58h]
  _BYTE v66[32]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR Buffer[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v55 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a2 + 56LL);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v55);
  v6 = v5(a2, &v55);
  v9 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6A2,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)v6,
      v52[0]);
LABEL_59:
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v55);
    return (unsigned int)v9;
  }
  *(_QWORD *)v52 = 0;
  StorageItemVectorFromShellItemArray = CreateStorageItemVectorFromShellItemArray(a3, v7, v8, v52);
  v9 = StorageItemVectorFromShellItemArray;
  if ( StorageItemVectorFromShellItemArray < 0 )
  {
    v11 = 1701;
LABEL_5:
    v12 = (unsigned int)StorageItemVectorFromShellItemArray;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)v12,
      v52[0]);
LABEL_58:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *>>::InternalRelease(v52);
    goto LABEL_59;
  }
  v53 = 0;
  StorageItemVectorFromShellItemArray = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v52 + 56LL))(
                                          *(_QWORD *)v52,
                                          &v53);
  v9 = StorageItemVectorFromShellItemArray;
  if ( StorageItemVectorFromShellItemArray < 0 )
  {
    v11 = 1704;
    goto LABEL_5;
  }
  if ( !v53 )
  {
    v9 = -2147024809;
    v12 = 2147942487LL;
    v11 = 1705;
    goto LABEL_6;
  }
  if ( v53 < 2 )
  {
    v57 = 0;
    v24 = *(_QWORD *)v52;
    v25 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v52 + 48LL);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v57);
    v26 = v25(v24, 0, &v57);
    v9 = v26;
    if ( v26 >= 0 )
    {
      string = 0;
      v27 = v57;
      v28 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v57 + 88LL);
      WindowsDeleteString(0);
      string = 0;
      v29 = v28(v27, &string);
      v9 = v29;
      if ( v29 >= 0 )
      {
        v29 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING))(*v55)[7])(
                v55,
                string);
        v9 = v29;
        if ( v29 >= 0 )
        {
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v57);
          goto LABEL_35;
        }
        v30 = 1727;
      }
      else
      {
        v30 = 1726;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
        (const char *)(unsigned int)v29,
        v52[0]);
      WindowsDeleteString(string);
      string = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6BC,
        (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
        (const char *)(unsigned int)v26,
        v52[0]);
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v57);
    goto LABEL_58;
  }
  memset(&hstringHeader, 0, sizeof(hstringHeader));
  memset(v62, 0, sizeof(v62));
  v9 = -2147467259;
  Resource = FindResourceExW(&_ImageBase, (LPCWSTR)6, (LPCWSTR)0x143, 0);
  if ( !Resource )
    goto LABEL_25;
  v14 = LoadResource(&_ImageBase, Resource);
  if ( !v14 )
    goto LABEL_25;
  v15 = LockResource(v14);
  if ( !v15 )
    goto LABEL_25;
  v16 = v15 + 1;
  if ( !*v15 )
    v16 = &WindowName;
  v9 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         &hstringHeader,
         v16,
         (unsigned __int16)*v15);
  if ( v9 < 0 )
  {
LABEL_25:
    v19 = (unsigned int)v9;
    v18 = 1714;
    goto LABEL_21;
  }
  v17 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          v62,
          hstringHeader.Reserved.Reserved1,
          v53);
  v9 = v17;
  if ( v17 < 0 )
  {
    v18 = 1715;
LABEL_20:
    v19 = (unsigned int)v17;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)v19,
      v52[0]);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v62);
    p_hstringHeader = &hstringHeader;
LABEL_57:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(p_hstringHeader);
    goto LABEL_58;
  }
  v21 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v55;
  v22 = (*v55)[7];
  v56 = v62[0];
  v23 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v66, &v56);
  v17 = ((__int64 (__fastcall *)(_QWORD, _QWORD))v22)(v21, *(_QWORD *)(v23 + 24));
  v9 = v17;
  if ( v17 < 0 )
  {
    v18 = 1717;
    goto LABEL_20;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v62);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&hstringHeader);
LABEL_35:
  v59 = 0;
  v60 = 0;
  v61 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v59);
  v31 = -1;
  v60 = -1;
  v61 = -1;
  EnterpriseId = IShellItemArray_GetEnterpriseId(a3, &v59);
  if ( EnterpriseId < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x6C3,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)EnterpriseId,
      v52[0]);
    goto LABEL_44;
  }
  if ( v59 )
  {
    v56 = 0;
    v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v55;
    v34 = **v55;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v56);
    v35 = v34(v33, &GUID_9e87fd9b_5205_401b_874a_455653bd39e8, &v56);
    v9 = v35;
    if ( v35 < 0 )
    {
      v36 = 1734;
LABEL_40:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
        (const char *)(unsigned int)v35,
        v52[0]);
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v56);
LABEL_56:
      p_hstringHeader = &v59;
      goto LABEL_57;
    }
    v37 = v56;
    v38 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v56 + 56LL);
    v63 = v59;
    v39 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v66, &v63);
    v35 = v38(v37, *(_QWORD *)(v39 + 24));
    v9 = v35;
    if ( v35 < 0 )
    {
      v36 = 1735;
      goto LABEL_40;
    }
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v56);
  }
LABEL_44:
  if ( !LoadStringW(g_hInstance, (v53 != 1) + 5153, Buffer, 260) )
  {
    v9 = -2147418113;
    v40 = 2147549183LL;
    v41 = 1741;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)v40,
      v52[0]);
    goto LABEL_56;
  }
  do
    ++v31;
  while ( Buffer[v31] );
  if ( v31 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x18004AAD1LL);
  }
  v42 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v55;
  v43 = (*v55)[9];
  v44 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v31);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, Buffer, v44, v31);
  v45 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64))v43)(v42, v65);
  v9 = v45;
  if ( v45 < 0 )
  {
    v40 = (unsigned int)v45;
    v41 = 1742;
    goto LABEL_46;
  }
  v58 = 0;
  v46 = *(_QWORD *)v52;
  v47 = ***(__int64 (__fastcall ****)(__int64, GUID *, __int64 *))v52;
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v58);
  v48 = v47(v46, &GUID_bb8b8418_65d1_544b_b083_6d172f568c73, &v58);
  v9 = v48;
  if ( v48 < 0 )
  {
    v50 = 1745;
LABEL_55:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v50,
      (unsigned int)"shell\\osshell\\lmui\\ntshrui\\dll\\shareverb.cpp",
      (const char *)(unsigned int)v48,
      v52[0]);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v58);
    goto LABEL_56;
  }
  LOBYTE(v49) = 1;
  v48 = (*(__int64 (__fastcall **)(struct Windows::ApplicationModel::DataTransfer::IDataPackage *, __int64, __int64))(*(_QWORD *)a2 + 184LL))(
          a2,
          v58,
          v49);
  v9 = v48;
  if ( v48 < 0 )
  {
    v50 = 1746;
    goto LABEL_55;
  }
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v58);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v59);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *>>::InternalRelease(v52);
  Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v55);
  return 0;
}

```

## disassembly

```asm
0x18004a4a8  mov     [rsp-8+arg_0], rbx
0x18004a4ad  mov     [rsp-8+arg_18], rsi
0x18004a4b2  push    rbp
0x18004a4b3  push    rdi
0x18004a4b4  push    r12
0x18004a4b6  push    r14
0x18004a4b8  push    r15
0x18004a4ba  lea     rbp, [rsp-1F0h]
0x18004a4c2  sub     rsp, 2F0h
0x18004a4c9  mov     rax, cs:__security_cookie
0x18004a4d0  xor     rax, rsp
0x18004a4d3  mov     [rbp+210h+var_30], rax
0x18004a4da  mov     r14, r8
0x18004a4dd  mov     r15, rdx
0x18004a4e0  xor     r12d, r12d
0x18004a4e3  mov     [rsp+310h+var_2D8], r12
0x18004a4e8  mov     rax, [rdx]
0x18004a4eb  mov     rbx, [rax+38h]
0x18004a4ef  lea     rcx, [rsp+310h+var_2D8]
0x18004a4f4  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004a4f9  lea     rdx, [rsp+310h+var_2D8]
0x18004a4fe  mov     rcx, r15
0x18004a501  mov     rax, rbx
0x18004a504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a509  mov     ebx, eax
0x18004a50b  test    eax, eax
0x18004a50d  jns     short loc_18004A52F
0x18004a50f  mov     rcx, [rbp+218h]; this
0x18004a516  mov     r9d, eax; char *
0x18004a519  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004a520  mov     edx, 6A2h; void *
0x18004a525  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a52a  jmp     loc_18004AA56
0x18004a52f  mov     qword ptr [rsp+310h+var_2F0], r12; int
0x18004a534  lea     r9, [rsp+310h+var_2F0]
0x18004a539  mov     rcx, r14
0x18004a53c  call    ?CreateStorageItemVectorFromShellItemArray@@YAJPEAUIShellItemArray@@PEBGKPEAPEAU?$IVector@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Z; CreateStorageItemVectorFromShellItemArray(IShellItemArray *,ushort const *,ulong,Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *> * *)
0x18004a541  mov     ebx, eax
0x18004a543  test    eax, eax
0x18004a545  jns     short loc_18004A567
0x18004a547  mov     edx, 6A5h; void *
0x18004a54c  mov     r9d, eax; char *
0x18004a54f  mov     rcx, [rbp+218h]; this
0x18004a556  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004a55d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a562  jmp     loc_18004AA4B
0x18004a567  mov     [rsp+310h+var_2E8], r12d
0x18004a56c  mov     rcx, qword ptr [rsp+310h+var_2F0]
0x18004a571  mov     rax, [rcx]
0x18004a574  lea     rdx, [rsp+310h+var_2E8]
0x18004a579  mov     rax, [rax+38h]
0x18004a57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a582  mov     ebx, eax
0x18004a584  test    eax, eax
0x18004a586  jns     short loc_18004A58F
0x18004a588  mov     edx, 6A8h
0x18004a58d  jmp     short loc_18004A54C
0x18004a58f  mov     eax, [rsp+310h+var_2E8]
0x18004a593  test    eax, eax
0x18004a595  jnz     short loc_18004A5A6
0x18004a597  mov     ebx, 80070057h
0x18004a59c  mov     r9d, ebx
0x18004a59f  mov     edx, 6A9h
0x18004a5a4  jmp     short loc_18004A54F
0x18004a5a6  cmp     eax, 2
0x18004a5a9  jb      loc_18004A6F4
0x18004a5af  mov     qword ptr [rbp+210h+hstringHeader.Reserved], r12
0x18004a5b3  mov     qword ptr [rbp+210h+hstringHeader.Reserved+8], r12
0x18004a5b7  mov     qword ptr [rbp+210h+hstringHeader.Reserved+10h], r12
0x18004a5bb  mov     [rsp+310h+var_2A0], r12
0x18004a5c0  mov     [rsp+310h+var_298], r12
0x18004a5c5  mov     [rbp+210h+var_290], r12
0x18004a5c9  mov     ebx, 80004005h
0x18004a5ce  xor     r9d, r9d; wLanguage
0x18004a5d1  lea     edx, [r9+6]; lpType
0x18004a5d5  mov     r8d, 143h; lpName
0x18004a5db  lea     rcx, __ImageBase; hModule
0x18004a5e2  call    cs:__imp_FindResourceExW
0x18004a5e8  test    rax, rax
0x18004a5eb  jz      loc_18004A6E7
0x18004a5f1  mov     rdx, rax; hResInfo
0x18004a5f4  lea     rcx, __ImageBase; hModule
0x18004a5fb  call    cs:__imp_LoadResource
0x18004a601  test    rax, rax
0x18004a604  jz      loc_18004A6E7
0x18004a60a  mov     rcx, rax; hResData
0x18004a60d  call    cs:__imp_LockResource
0x18004a613  test    rax, rax
0x18004a616  jz      loc_18004A6E7
0x18004a61c  cmp     [rax], r12w
0x18004a620  lea     rdx, [rax+2]
0x18004a624  jnz     short loc_18004A62D
0x18004a626  lea     rdx, WindowName
0x18004a62d  movzx   r8d, word ptr [rax]
0x18004a631  lea     rcx, [rbp+210h+hstringHeader]
0x18004a635  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18004a63a  mov     ebx, eax
0x18004a63c  test    eax, eax
0x18004a63e  js      loc_18004A6E7
0x18004a644  mov     r8d, [rsp+310h+var_2E8]
0x18004a649  mov     rdx, qword ptr [rbp+210h+hstringHeader.Reserved]
0x18004a64d  lea     rcx, [rsp+310h+var_2A0]
0x18004a652  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18004a657  mov     ebx, eax
0x18004a659  test    eax, eax
0x18004a65b  jns     short loc_18004A68D
0x18004a65d  mov     edx, 6B3h; void *
0x18004a662  mov     r9d, eax; char *
0x18004a665  mov     rcx, [rbp+218h]; this
0x18004a66c  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004a673  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a678  nop
0x18004a679  lea     rcx, [rsp+310h+var_2A0]
0x18004a67e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004a683  nop
0x18004a684  lea     rcx, [rbp+210h+hstringHeader]
0x18004a688  jmp     loc_18004AA45
0x18004a68d  mov     rdi, [rsp+310h+var_2D8]
0x18004a692  mov     rax, [rdi]
0x18004a695  mov     rbx, [rax+38h]
0x18004a699  mov     rcx, [rsp+310h+var_2A0]
0x18004a69e  mov     [rsp+310h+var_2D0], rcx
0x18004a6a3  lea     rdx, [rsp+310h+var_2D0]
0x18004a6a8  lea     rcx, [rbp+210h+var_260]
0x18004a6ac  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004a6b1  nop
0x18004a6b2  mov     rdx, [rax+18h]
0x18004a6b6  mov     rcx, rdi
0x18004a6b9  mov     rax, rbx
0x18004a6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6c1  mov     ebx, eax
0x18004a6c3  test    eax, eax
0x18004a6c5  jns     short loc_18004A6CE
0x18004a6c7  mov     edx, 6B5h
0x18004a6cc  jmp     short loc_18004A662
0x18004a6ce  lea     rcx, [rsp+310h+var_2A0]
0x18004a6d3  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004a6d8  nop
0x18004a6d9  lea     rcx, [rbp+210h+hstringHeader]
0x18004a6dd  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004a6e2  jmp     loc_18004A7FA
0x18004a6e7  mov     r9d, ebx
0x18004a6ea  mov     edx, 6B2h
0x18004a6ef  jmp     loc_18004A665
0x18004a6f4  cmp     eax, 1
0x18004a6f7  jnz     loc_18004A7FA
0x18004a6fd  mov     [rsp+310h+var_2C8], r12
0x18004a702  mov     rdi, qword ptr [rsp+310h+var_2F0]
0x18004a707  mov     rax, [rdi]
0x18004a70a  mov     rbx, [rax+30h]
0x18004a70e  lea     rcx, [rsp+310h+var_2C8]
0x18004a713  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004a718  lea     r8, [rsp+310h+var_2C8]
0x18004a71d  xor     edx, edx
0x18004a71f  mov     rcx, rdi
0x18004a722  mov     rax, rbx
0x18004a725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a72a  mov     ebx, eax
0x18004a72c  test    eax, eax
0x18004a72e  jns     short loc_18004A75B
0x18004a730  mov     rcx, [rbp+218h]; this
0x18004a737  mov     r9d, eax; char *
0x18004a73a  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004a741  mov     edx, 6BCh; void *
0x18004a746  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a74b  nop
0x18004a74c  lea     rcx, [rsp+310h+var_2C8]
0x18004a751  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004a756  jmp     loc_18004AA4B
0x18004a75b  mov     [rsp+310h+string], r12
0x18004a760  mov     rdi, [rsp+310h+var_2C8]
0x18004a765  mov     rax, [rdi]
0x18004a768  mov     rbx, [rax+58h]
0x18004a76c  xor     ecx, ecx; string
0x18004a76e  call    cs:__imp_WindowsDeleteString
0x18004a774  mov     [rsp+310h+string], r12
0x18004a779  lea     rdx, [rsp+310h+string]
0x18004a77e  mov     rcx, rdi
0x18004a781  mov     rax, rbx
0x18004a784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a789  mov     ebx, eax
0x18004a78b  test    eax, eax
0x18004a78d  jns     short loc_18004A7BD
0x18004a78f  mov     edx, 6BEh; void *
0x18004a794  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004a79b  mov     r9d, eax; char *
0x18004a79e  mov     rcx, [rbp+218h]; this
0x18004a7a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a7aa  nop
0x18004a7ab  mov     rcx, [rsp+310h+string]; string
0x18004a7b0  call    cs:__imp_WindowsDeleteString
0x18004a7b6  mov     [rsp+310h+string], r12
0x18004a7bb  jmp     short loc_18004A74C
0x18004a7bd  mov     rcx, [rsp+310h+var_2D8]
0x18004a7c2  mov     rax, [rcx]
0x18004a7c5  mov     rdx, [rsp+310h+string]
0x18004a7ca  mov     rax, [rax+38h]
0x18004a7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7d3  mov     ebx, eax
0x18004a7d5  test    eax, eax
0x18004a7d7  jns     short loc_18004A7E0
0x18004a7d9  mov     edx, 6BFh
0x18004a7de  jmp     short loc_18004A794
0x18004a7e0  mov     rcx, [rsp+310h+string]; string
0x18004a7e5  call    cs:__imp_WindowsDeleteString
0x18004a7eb  mov     [rsp+310h+string], r12
0x18004a7f0  lea     rcx, [rsp+310h+var_2C8]
0x18004a7f5  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004a7fa  mov     [rsp+310h+var_2B8], r12
0x18004a7ff  mov     [rsp+310h+var_2B0], r12
0x18004a804  mov     [rsp+310h+var_2A8], r12
0x18004a809  lea     rcx, [rsp+310h+var_2B8]
0x18004a80e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004a813  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004a817  mov     [rsp+310h+var_2B0], rsi
0x18004a81c  mov     [rsp+310h+var_2A8], rsi
0x18004a821  lea     rdx, [rsp+310h+var_2B8]; unsigned __int16 **
0x18004a826  mov     rcx, r14; struct IShellItemArray *
0x18004a829  call    ?IShellItemArray_GetEnterpriseId@@YAJPEAUIShellItemArray@@PEAPEAG@Z; IShellItemArray_GetEnterpriseId(IShellItemArray *,ushort * *)
0x18004a82e  mov     rcx, [rbp+218h]; this
0x18004a835  test    eax, eax
0x18004a837  jns     short loc_18004A852
0x18004a839  mov     r9d, eax; char *
0x18004a83c  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004a843  mov     edx, 6C3h; void *
0x18004a848  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a84d  jmp     loc_18004A908
0x18004a852  cmp     [rsp+310h+var_2B8], r12
0x18004a857  jz      loc_18004A908
0x18004a85d  mov     [rsp+310h+var_2D0], r12
0x18004a862  mov     rbx, [rsp+310h+var_2D8]
0x18004a867  mov     rax, [rbx]
0x18004a86a  mov     rdi, [rax]
0x18004a86d  lea     rcx, [rsp+310h+var_2D0]
0x18004a872  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004a877  lea     r8, [rsp+310h+var_2D0]
0x18004a87c  lea     rdx, _GUID_9e87fd9b_5205_401b_874a_455653bd39e8
0x18004a883  mov     rcx, rbx
0x18004a886  mov     rax, rdi
0x18004a889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a88e  mov     ebx, eax
0x18004a890  test    eax, eax
0x18004a892  jns     short loc_18004A8BF
0x18004a894  mov     edx, 6C6h; void *
0x18004a899  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004a8a0  mov     r9d, eax; char *
0x18004a8a3  mov     rcx, [rbp+218h]; this
0x18004a8aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a8af  nop
0x18004a8b0  lea     rcx, [rsp+310h+var_2D0]
0x18004a8b5  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004a8ba  jmp     loc_18004AA40
0x18004a8bf  mov     rdi, [rsp+310h+var_2D0]
0x18004a8c4  mov     rax, [rdi]
0x18004a8c7  mov     rbx, [rax+38h]
0x18004a8cb  mov     rcx, [rsp+310h+var_2B8]
0x18004a8d0  mov     [rbp+210h+var_288], rcx
0x18004a8d4  lea     rdx, [rbp+210h+var_288]
0x18004a8d8  lea     rcx, [rbp+210h+var_260]
0x18004a8dc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004a8e1  nop
0x18004a8e2  mov     rdx, [rax+18h]
0x18004a8e6  mov     rcx, rdi
0x18004a8e9  mov     rax, rbx
0x18004a8ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8f1  mov     ebx, eax
0x18004a8f3  test    eax, eax
0x18004a8f5  jns     short loc_18004A8FE
0x18004a8f7  mov     edx, 6C7h
0x18004a8fc  jmp     short loc_18004A899
0x18004a8fe  lea     rcx, [rsp+310h+var_2D0]
0x18004a903  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x18004a908  mov     edx, r12d
0x18004a90b  cmp     [rsp+310h+var_2E8], 1
0x18004a910  setnz   dl
0x18004a913  add     edx, 1421h; uID
0x18004a919  mov     r9d, 104h; cchBufferMax
0x18004a91f  lea     r8, [rbp+210h+Buffer]; lpBuffer
0x18004a923  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18004a92a  call    cs:__imp_LoadStringW
0x18004a930  test    eax, eax
0x18004a932  jnz     short loc_18004A959
0x18004a934  mov     ebx, 8000FFFFh
0x18004a939  mov     r9d, ebx; char *
0x18004a93c  mov     edx, 6CDh; void *
0x18004a941  lea     r8, aShellOsshellLm_0; "shell\\osshell\\lmui\\ntshrui\\dll\\sha"...
0x18004a948  mov     rcx, [rbp+218h]; this
0x18004a94f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a954  jmp     loc_18004AA40
0x18004a959  lea     rax, [rbp+210h+Buffer]
0x18004a95d  inc     rsi
0x18004a960  cmp     [rax+rsi*2], r12w
0x18004a965  jnz     short loc_18004A95D
0x18004a967  mov     eax, 0FFFFFFFFh
0x18004a96c  cmp     rsi, rax
0x18004a96f  ja      loc_18004AABC
0x18004a975  mov     rdi, [rsp+310h+var_2D8]
0x18004a97a  mov     rax, [rdi]
0x18004a97d  mov     rbx, [rax+48h]
0x18004a981  mov     ecx, esi; unsigned int
  ... truncated ...
```
