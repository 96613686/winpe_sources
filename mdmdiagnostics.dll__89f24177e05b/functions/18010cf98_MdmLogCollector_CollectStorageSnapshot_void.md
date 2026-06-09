# MdmLogCollector::CollectStorageSnapshot(void)

- ea: `0x18010cf98`
- end: `0x18010d455`
- name: `?CollectStorageSnapshot@MdmLogCollector@@AEAAJXZ`
- size: `1213`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18010a670`

## callees

- `0x180019000`
- `0x1800e6664`
- `0x1800e66b8`
- `0x1800e66dc`
- `0x1800ece5c`
- `0x1800ef134`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef900`
- `0x180104e60`
- `0x18010566c`
- `0x180107ecc`
- `0x180108ae0`
- `0x18010cf98`
- `0x18010f490`
- `0x18010f704`
- `0x1801109fc`
- `0x180111188`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010d0c0`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010d0c0`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010d045`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010d414`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010d045`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010d414`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010d0a2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010d0a2`
- `ext-ms-win-storage-sense-l1-1-0!CloseFindStorageSearch` at `0x18010d057`
- `ext-ms-win-storage-sense-l1-1-0!CloseFindStorageSearch` at `0x18010d426`
- `ext-ms-win-storage-sense-l1-1-0!CloseFindStorageSearch` at `0x18010d057`
- `ext-ms-win-storage-sense-l1-1-0!CloseFindStorageSearch` at `0x18010d426`
- `ext-ms-win-storage-sense-l1-1-0!FindNextStorageTypeEx` at `0x18010d215`
- `ext-ms-win-storage-sense-l1-1-0!FindNextStorageTypeEx` at `0x18010d215`
- `ext-ms-win-storage-sense-l1-1-0!SelectStorageVolumeEx` at `0x18010d14e`
- `ext-ms-win-storage-sense-l1-1-0!SelectStorageVolumeEx` at `0x18010d14e`
- `ext-ms-win-storage-sense-l1-1-0!OpenStorageTypeSearch` at `0x18010d0e0`
- `ext-ms-win-storage-sense-l1-1-0!OpenStorageTypeSearch` at `0x18010d0e0`
- `ext-ms-win-storage-sense-l1-2-3!GetStorageDeviceLowDiskState2` at `0x18010d19f`
- `ext-ms-win-storage-sense-l1-2-3!GetStorageDeviceLowDiskState2` at `0x18010d19f`

## string_xrefs

- `0x18010d291`: `%PROGRAMDATA%`
- `0x18010d01d`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010d0fb`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010d229`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010d374`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall MdmLogCollector::CollectStorageSnapshot(MdmLogCollector *this)
{
  __int64 v2; // rcx
  int TemporaryOutputPath; // eax
  int StorageDeviceLowDiskState2; // ebx
  const unsigned __int16 *v6; // rax
  const WCHAR *v7; // rax
  const wchar_t *v8; // rax
  __int64 v9; // rdx
  int i; // ebx
  int NextStorageType; // eax
  _QWORD *j; // rbx
  _QWORD *v13; // rsi
  int v14; // eax
  __int64 v15; // rdi
  int v16; // [rsp+20h] [rbp-E0h]
  int *v17; // [rsp+20h] [rbp-E0h]
  errno_t v18; // [rsp+40h] [rbp-C0h] BYREF
  FILE *Stream; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v22; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE *v23; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v24; // [rsp+70h] [rbp-90h]
  unsigned __int64 v25; // [rsp+78h] [rbp-88h]
  __int128 v26; // [rsp+80h] [rbp-80h] BYREF
  __int64 v27; // [rsp+90h] [rbp-70h]
  errno_t *v28; // [rsp+98h] [rbp-68h]
  FILE **p_Stream; // [rsp+A0h] [rbp-60h]
  __int64 *v30; // [rsp+A8h] [rbp-58h]
  char v31; // [rsp+B0h] [rbp-50h]
  _BYTE v32[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v33[40]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v34[14]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v35[32]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  Stream = 0;
  v20 = 0;
  v18 = 0;
  v28 = &v18;
  p_Stream = &Stream;
  v30 = &v20;
  v31 = 1;
  std::wstring::wstring(v33);
  TemporaryOutputPath = MdmLogCollector::GetTemporaryOutputPath(v2, v33);
  StorageDeviceLowDiskState2 = TemporaryOutputPath;
  if ( TemporaryOutputPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x925,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)(unsigned int)TemporaryOutputPath,
      v16);
LABEL_3:
    std::wstring::_Tidy_deallocate(v33);
    if ( !v18 )
      fclose(Stream);
    if ( v20 )
      CloseFindStorageSearch(&v20);
    return (unsigned int)StorageDeviceLowDiskState2;
  }
  std::wstring::wstring(v32, v33);
  std::wstring::append(v32, L"StorageSnapshot.txt");
  v6 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
  MdmLogCollector::AddFileEntry(this, v6);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
  DeleteFileW(v7);
  v8 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v32);
  v18 = _wfopen_s(&Stream, v8, L"a+");
  MdmLogCollector::WriteToFile(Stream, L"Storage snapshot (In MB)\n\n");
  StorageDeviceLowDiskState2 = OpenStorageTypeSearch(&v20);
  if ( StorageDeviceLowDiskState2 < 0 )
  {
    v9 = 2357;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)(unsigned int)StorageDeviceLowDiskState2,
      v16);
    std::wstring::_Tidy_deallocate(v32);
    goto LABEL_3;
  }
  v25 = 0;
  v24 = 0;
  v16 = 0;
  StorageDeviceLowDiskState2 = SelectStorageVolumeEx(v20, 0, 0, 0);
  if ( StorageDeviceLowDiskState2 < 0 )
  {
    v9 = 2369;
    goto LABEL_10;
  }
  MdmLogCollector::WriteToFile(Stream, L"Total Space: %llu Free Space: %llu\n\n", v25 >> 20, v24 >> 20);
  v22 = 0;
  v16 = 0;
  StorageDeviceLowDiskState2 = GetStorageDeviceLowDiskState2(0, 0, 0, &v22);
  if ( StorageDeviceLowDiskState2 < 0 )
  {
    v9 = 2374;
    goto LABEL_10;
  }
  MdmLogCollector::WriteToFile(Stream, L"In low disk state: %d\n", v22 != 0);
  MdmLogCollector::WriteToFile(Stream, L"\nStorage Node Key: Size \n");
  for ( i = 0; i < 34; ++i )
  {
    *(_QWORD *)v21 = 0;
    v23 = 0;
    v17 = v21;
    NextStorageType = FindNextStorageTypeEx(v20, (unsigned int)i, &Name, 0);
    if ( NextStorageType >= 0 )
    {
      if ( *(_QWORD *)v21 )
        MdmLogCollector::WriteToFile(Stream, L"%d: %llu\n", (unsigned int)i, *(_QWORD *)v21 >> 20);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x954,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
        (const char *)(unsigned int)NextStorageType,
        (int)v21);
    }
  }
  v34[0] = L"%DATADRIVE%\\crashdump";
  v34[1] = L"Data Crashdump";
  v34[2] = L"%DATADRIVE%\\systemdata\\etw";
  v34[3] = L"Data Diagnostics";
  v34[4] = L"%PROGRAMDATA%";
  v34[5] = L"Data Programs";
  v34[6] = L"%OSDATADRIVE%\\systemdata\\etw";
  v34[7] = L"OS Data Diagnostics";
  v34[8] = L"%OSDATADRIVE%\\logfiles";
  v34[9] = L"OS Data LogFiles";
  v34[10] = L"%OSDATADRIVE%\\shareddata";
  v34[11] = L"OS Data Shared";
  v34[12] = L"%SYSTEMDRIVE%\\data\\users";
  v34[13] = L"System Users";
  v26 = 0;
  v27 = 0;
  v23 = v35;
  *(_QWORD *)v21 = v34;
  std::vector<std::tuple<unsigned short const *,unsigned short const *>>::_Construct_n<std::tuple<unsigned short const *,unsigned short const *> const *,std::tuple<unsigned short const *,unsigned short const *> const *>(
    &v26,
    7,
    v21,
    &v23);
  MdmLogCollector::WriteToFile(Stream, L"\nFolder Key: Size\n");
  v13 = (_QWORD *)*((_QWORD *)&v26 + 1);
  for ( j = (_QWORD *)v26; j != v13; j += 2 )
  {
    *(_QWORD *)v21 = 0;
    v14 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
            *j,
            v21);
    if ( v14 >= 0 )
    {
      std::wstring::wstring(v35, *(_QWORD *)v21);
      v15 = GetFolderSizeInBytes(v35) / 0x100000;
      std::wstring::_Tidy_deallocate(v35);
      if ( v15 > 0 )
        MdmLogCollector::WriteToFile(Stream, L"%ws: %lld\n", j[1], v15);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x970,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
        (const char *)(unsigned int)v14,
        (int)v17);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v21);
  }
  std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(&v26);
  std::wstring::_Tidy_deallocate(v32);
  std::wstring::_Tidy_deallocate(v33);
  if ( !v18 )
    fclose(Stream);
  if ( v20 )
    CloseFindStorageSearch(&v20);
  return 0;
}

```

## disassembly

```asm
0x18010cf98  mov     [rsp-8+arg_8], rbx
0x18010cf9d  mov     [rsp-8+arg_10], rsi
0x18010cfa2  push    rbp
0x18010cfa3  push    rdi
0x18010cfa4  push    r14
0x18010cfa6  lea     rbp, [rsp-0A0h]
0x18010cfae  sub     rsp, 1A0h
0x18010cfb5  mov     rax, cs:__security_cookie
0x18010cfbc  xor     rax, rsp
0x18010cfbf  mov     [rbp+0B0h+var_20], rax
0x18010cfc6  mov     rdi, rcx
0x18010cfc9  xor     r14d, r14d
0x18010cfcc  mov     [rsp+1B0h+Stream], r14
0x18010cfd1  mov     [rsp+1B0h+var_160], r14
0x18010cfd6  mov     [rsp+1B0h+var_170], r14d
0x18010cfdb  lea     rax, [rsp+1B0h+var_170]
0x18010cfe0  mov     [rbp+0B0h+var_118], rax
0x18010cfe4  lea     rax, [rsp+1B0h+Stream]
0x18010cfe9  mov     [rbp+0B0h+var_110], rax
0x18010cfed  lea     rax, [rsp+1B0h+var_160]
0x18010cff2  mov     [rbp+0B0h+var_108], rax
0x18010cff6  mov     [rbp+0B0h+var_100], 1
0x18010cffa  lea     rcx, [rbp+0B0h+var_D8]
0x18010cffe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010d003  nop
0x18010d004  lea     rdx, [rbp+0B0h+var_D8]
0x18010d008  call    ?GetTemporaryOutputPath@MdmLogCollector@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetTemporaryOutputPath(std::wstring &)
0x18010d00d  mov     ebx, eax
0x18010d00f  test    eax, eax
0x18010d011  jns     short loc_18010D064
0x18010d013  mov     rcx, [rbp+0B8h]; this
0x18010d01a  mov     r9d, eax; char *
0x18010d01d  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010d024  mov     edx, 925h; void *
0x18010d029  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d02e  nop
0x18010d02f  lea     rcx, [rbp+0B0h+var_D8]
0x18010d033  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010d038  nop
0x18010d039  cmp     [rsp+1B0h+var_170], r14d
0x18010d03e  jnz     short loc_18010D04B
0x18010d040  mov     rcx, [rsp+1B0h+Stream]; Stream
0x18010d045  call    cs:__imp_fclose
0x18010d04b  cmp     [rsp+1B0h+var_160], r14
0x18010d050  jz      short loc_18010D05D
0x18010d052  lea     rcx, [rsp+1B0h+var_160]
0x18010d057  call    cs:__imp_CloseFindStorageSearch
0x18010d05d  mov     eax, ebx
0x18010d05f  jmp     loc_18010D42E
0x18010d064  lea     rdx, [rbp+0B0h+var_D8]
0x18010d068  lea     rcx, [rbp+0B0h+var_F8]
0x18010d06c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18010d071  nop
0x18010d072  lea     rdx, aStoragesnapsho; "StorageSnapshot.txt"
0x18010d079  lea     rcx, [rbp+0B0h+var_F8]
0x18010d07d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010d082  lea     rcx, [rbp+0B0h+var_F8]
0x18010d086  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d08b  mov     rdx, rax; unsigned __int16 *
0x18010d08e  mov     rcx, rdi; this
0x18010d091  call    ?AddFileEntry@MdmLogCollector@@QEAAJPEBG@Z; MdmLogCollector::AddFileEntry(ushort const *)
0x18010d096  lea     rcx, [rbp+0B0h+var_F8]
0x18010d09a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d09f  mov     rcx, rax; lpFileName
0x18010d0a2  call    cs:__imp_DeleteFileW
0x18010d0a8  lea     rcx, [rbp+0B0h+var_F8]
0x18010d0ac  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010d0b1  mov     rdx, rax; FileName
0x18010d0b4  lea     r8, aA; "a+"
0x18010d0bb  lea     rcx, [rsp+1B0h+Stream]; Stream
0x18010d0c0  call    cs:__imp__wfopen_s
0x18010d0c6  mov     [rsp+1B0h+var_170], eax
0x18010d0ca  lea     rdx, aStorageSnapsho; "Storage snapshot (In MB)\n\n"
0x18010d0d1  mov     rcx, [rsp+1B0h+Stream]; struct _iobuf *
0x18010d0d6  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d0db  lea     rcx, [rsp+1B0h+var_160]
0x18010d0e0  call    cs:__imp_OpenStorageTypeSearch
0x18010d0e6  mov     ebx, eax
0x18010d0e8  test    eax, eax
0x18010d0ea  jns     short loc_18010D116
0x18010d0ec  mov     edx, 935h; void *
0x18010d0f1  mov     rcx, [rbp+0B8h]; this
0x18010d0f8  mov     r9d, ebx; char *
0x18010d0fb  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010d102  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d107  nop
0x18010d108  lea     rcx, [rbp+0B0h+var_F8]
0x18010d10c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010d111  jmp     loc_18010D02F
0x18010d116  mov     [rsp+1B0h+var_138], r14
0x18010d11b  mov     [rsp+1B0h+var_140], r14
0x18010d120  lea     rax, [rsp+1B0h+var_140]
0x18010d125  mov     [rsp+1B0h+var_178], rax
0x18010d12a  lea     rax, [rsp+1B0h+var_138]
0x18010d12f  mov     [rsp+1B0h+var_180], rax
0x18010d134  mov     dword ptr [rsp+1B0h+var_188], 1
0x18010d13c  mov     qword ptr [rsp+1B0h+var_190], r14
0x18010d141  xor     r9d, r9d
0x18010d144  xor     r8d, r8d
0x18010d147  xor     edx, edx
0x18010d149  mov     rcx, [rsp+1B0h+var_160]
0x18010d14e  call    cs:__imp_SelectStorageVolumeEx
0x18010d154  mov     ebx, eax
0x18010d156  test    eax, eax
0x18010d158  jns     short loc_18010D161
0x18010d15a  mov     edx, 941h
0x18010d15f  jmp     short loc_18010D0F1
0x18010d161  mov     r9, [rsp+1B0h+var_140]
0x18010d166  shr     r9, 14h
0x18010d16a  mov     r8, [rsp+1B0h+var_138]
0x18010d16f  shr     r8, 14h
0x18010d173  lea     rdx, aTotalSpaceLluF; "Total Space: %llu Free Space: %llu\n\n"
0x18010d17a  mov     rcx, [rsp+1B0h+Stream]; struct _iobuf *
0x18010d17f  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d184  mov     [rsp+1B0h+var_150], r14d
0x18010d189  mov     [rsp+1B0h+var_188], r14
0x18010d18e  mov     qword ptr [rsp+1B0h+var_190], r14
0x18010d193  lea     r9, [rsp+1B0h+var_150]
0x18010d198  xor     r8d, r8d
0x18010d19b  xor     edx, edx
0x18010d19d  xor     ecx, ecx
0x18010d19f  call    cs:__imp_GetStorageDeviceLowDiskState2
0x18010d1a5  mov     ebx, eax
0x18010d1a7  test    eax, eax
0x18010d1a9  jns     short loc_18010D1B5
0x18010d1ab  mov     edx, 946h
0x18010d1b0  jmp     loc_18010D0F1
0x18010d1b5  mov     r8d, r14d
0x18010d1b8  cmp     [rsp+1B0h+var_150], r14d
0x18010d1bd  setnz   r8b
0x18010d1c1  lea     rdx, aInLowDiskState; "In low disk state: %d\n"
0x18010d1c8  mov     rcx, [rsp+1B0h+Stream]; struct _iobuf *
0x18010d1cd  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d1d2  lea     rdx, aStorageNodeKey; "\nStorage Node Key: Size \n"
0x18010d1d9  mov     rcx, [rsp+1B0h+Stream]; struct _iobuf *
0x18010d1de  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d1e3  mov     ebx, r14d
0x18010d1e6  mov     qword ptr [rsp+1B0h+var_158], r14
0x18010d1eb  mov     [rsp+1B0h+var_148], r14
0x18010d1f0  lea     rax, [rsp+1B0h+var_148]
0x18010d1f5  mov     [rsp+1B0h+var_188], rax
0x18010d1fa  lea     rax, [rsp+1B0h+var_158]
0x18010d1ff  mov     qword ptr [rsp+1B0h+var_190], rax; int
0x18010d204  xor     r9d, r9d
0x18010d207  lea     r8, Name
0x18010d20e  mov     edx, ebx
0x18010d210  mov     rcx, [rsp+1B0h+var_160]
0x18010d215  call    cs:__imp_FindNextStorageTypeEx
0x18010d21b  mov     rcx, [rbp+0B8h]; this
0x18010d222  test    eax, eax
0x18010d224  jns     short loc_18010D23C
0x18010d226  mov     r9d, eax; char *
0x18010d229  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010d230  mov     edx, 954h; void *
0x18010d235  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010d23a  jmp     short loc_18010D25E
0x18010d23c  mov     r9, qword ptr [rsp+1B0h+var_158]
0x18010d241  test    r9, r9
0x18010d244  jz      short loc_18010D25E
0x18010d246  shr     r9, 14h
0x18010d24a  mov     r8d, ebx
0x18010d24d  lea     rdx, aDLlu; "%d: %llu\n"
0x18010d254  mov     rcx, [rsp+1B0h+Stream]; struct _iobuf *
0x18010d259  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d25e  inc     ebx
0x18010d260  cmp     ebx, 22h ; '"'
0x18010d263  jl      short loc_18010D1E6
0x18010d265  lea     rax, aDatadriveCrash; "%DATADRIVE%\\crashdump"
0x18010d26c  mov     [rbp+0B0h+var_B0], rax
0x18010d270  lea     rax, aDataCrashdump; "Data Crashdump"
0x18010d277  mov     [rbp+0B0h+var_A8], rax
0x18010d27b  lea     rax, aDatadriveSyste; "%DATADRIVE%\\systemdata\\etw"
0x18010d282  mov     [rbp+0B0h+var_A0], rax
0x18010d286  lea     rax, aDataDiagnostic; "Data Diagnostics"
0x18010d28d  mov     [rbp+0B0h+var_98], rax
0x18010d291  lea     rax, aProgramdata; "%PROGRAMDATA%"
0x18010d298  mov     [rbp+0B0h+var_90], rax
0x18010d29c  lea     rax, aDataPrograms; "Data Programs"
0x18010d2a3  mov     [rbp+0B0h+var_88], rax
0x18010d2a7  lea     rax, aOsdatadriveSys_0; "%OSDATADRIVE%\\systemdata\\etw"
0x18010d2ae  mov     [rbp+0B0h+var_80], rax
0x18010d2b2  lea     rax, aOsDataDiagnost; "OS Data Diagnostics"
0x18010d2b9  mov     [rbp+0B0h+var_78], rax
0x18010d2bd  lea     rax, aOsdatadriveLog; "%OSDATADRIVE%\\logfiles"
0x18010d2c4  mov     [rbp+0B0h+var_70], rax
0x18010d2c8  lea     rax, aOsDataLogfiles; "OS Data LogFiles"
0x18010d2cf  mov     [rbp+0B0h+var_68], rax
0x18010d2d3  lea     rax, aOsdatadriveSha; "%OSDATADRIVE%\\shareddata"
0x18010d2da  mov     [rbp+0B0h+var_60], rax
0x18010d2de  lea     rax, aOsDataShared; "OS Data Shared"
0x18010d2e5  mov     [rbp+0B0h+var_58], rax
0x18010d2e9  lea     rax, aSystemdriveDat; "%SYSTEMDRIVE%\\data\\users"
0x18010d2f0  mov     [rbp+0B0h+var_50], rax
0x18010d2f4  lea     rax, aSystemUsers; "System Users"
0x18010d2fb  mov     [rbp+0B0h+var_48], rax
0x18010d2ff  xorps   xmm0, xmm0
0x18010d302  movdqu  [rbp+0B0h+var_130], xmm0
0x18010d307  mov     [rbp+0B0h+var_120], r14
0x18010d30b  lea     rax, [rbp+0B0h+var_40]
0x18010d30f  mov     [rsp+1B0h+var_148], rax
0x18010d314  lea     rax, [rbp+0B0h+var_B0]
0x18010d318  mov     qword ptr [rsp+1B0h+var_158], rax
0x18010d31d  lea     r9, [rsp+1B0h+var_148]
0x18010d322  lea     r8, [rsp+1B0h+var_158]
0x18010d327  mov     edx, 7
0x18010d32c  lea     rcx, [rbp+0B0h+var_130]
0x18010d330  call    ??$_Construct_n@PEBV?$tuple@PEBGPEBG@std@@PEBV12@@?$vector@V?$tuple@PEBGPEBG@std@@V?$allocator@V?$tuple@PEBGPEBG@std@@@2@@std@@AEAAX_K$$QEAPEBV?$tuple@PEBGPEBG@1@1@Z; std::vector<std::tuple<ushort const *,ushort const *>>::_Construct_n<std::tuple<ushort const *,ushort const *> const *,std::tuple<ushort const *,ushort const *> const *>(unsigned __int64,std::tuple<ushort const *,ushort const *> const * &&,std::tuple<ushort const *,ushort const *> const * &&)
0x18010d335  nop
0x18010d336  lea     rdx, aFolderKeySize; "\nFolder Key: Size\n"
0x18010d33d  mov     rcx, [rsp+1B0h+Stream]; struct _iobuf *
0x18010d342  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d347  mov     rbx, qword ptr [rbp+0B0h+var_130]
0x18010d34b  mov     rsi, qword ptr [rbp+0B0h+var_130+8]
0x18010d34f  jmp     loc_18010D3E1
0x18010d354  mov     qword ptr [rsp+1B0h+var_158], r14
0x18010d359  lea     rdx, [rsp+1B0h+var_158]
0x18010d35e  mov     rcx, [rbx]
0x18010d361  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18010d366  mov     rcx, [rbp+0B8h]; this
0x18010d36d  test    eax, eax
0x18010d36f  jns     short loc_18010D387
0x18010d371  mov     r9d, eax; char *
0x18010d374  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010d37b  mov     edx, 970h; void *
0x18010d380  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010d385  jmp     short loc_18010D3D3
0x18010d387  mov     rdx, qword ptr [rsp+1B0h+var_158]
0x18010d38c  lea     rcx, [rbp+0B0h+var_40]
0x18010d390  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010d395  nop
0x18010d396  lea     rcx, [rbp+0B0h+var_40]
0x18010d39a  call    ?GetFolderSizeInBytes@@YA_JAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetFolderSizeInBytes(std::wstring const &)
0x18010d39f  cqo
0x18010d3a1  mov     ecx, 100000h
0x18010d3a6  idiv    rcx
0x18010d3a9  mov     rdi, rax
0x18010d3ac  lea     rcx, [rbp+0B0h+var_40]
0x18010d3b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010d3b5  test    rdi, rdi
0x18010d3b8  jle     short loc_18010D3D3
0x18010d3ba  mov     r9, rdi
0x18010d3bd  mov     r8, [rbx+8]
0x18010d3c1  lea     rdx, aWsLld; "%ws: %lld\n"
0x18010d3c8  mov     rcx, [rsp+1B0h+Stream]; struct _iobuf *
0x18010d3cd  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010d3d2  nop
0x18010d3d3  lea     rcx, [rsp+1B0h+var_158]
0x18010d3d8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010d3dd  add     rbx, 10h
0x18010d3e1  cmp     rbx, rsi
0x18010d3e4  jnz     loc_18010D354
0x18010d3ea  lea     rcx, [rbp+0B0h+var_130]
0x18010d3ee  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x18010d3f3  nop
0x18010d3f4  lea     rcx, [rbp+0B0h+var_F8]
0x18010d3f8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010d3fd  nop
0x18010d3fe  lea     rcx, [rbp+0B0h+var_D8]
0x18010d402  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010d407  nop
0x18010d408  cmp     [rsp+1B0h+var_170], r14d
0x18010d40d  jnz     short loc_18010D41A
0x18010d40f  mov     rcx, [rsp+1B0h+Stream]; Stream
0x18010d414  call    cs:__imp_fclose
0x18010d41a  cmp     [rsp+1B0h+var_160], r14
0x18010d41f  jz      short loc_18010D42C
0x18010d421  lea     rcx, [rsp+1B0h+var_160]
0x18010d426  call    cs:__imp_CloseFindStorageSearch
0x18010d42c  xor     eax, eax
0x18010d42e  mov     rcx, [rbp+0B0h+var_20]
0x18010d435  xor     rcx, rsp; StackCookie
0x18010d438  call    __security_check_cookie
0x18010d43d  lea     r11, [rsp+1B0h+var_10]
0x18010d445  mov     rbx, [r11+28h]
0x18010d449  mov     rsi, [r11+30h]
0x18010d44d  mov     rsp, r11
0x18010d450  pop     r14
0x18010d452  pop     rdi
0x18010d453  pop     rbp
0x18010d454  retn
```
