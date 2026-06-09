# MdmLogCollector::CollectStorageSnapshot(void)

- ea: `0x18010e480`
- end: `0x18010e97e`
- name: `?CollectStorageSnapshot@MdmLogCollector@@AEAAJXZ`
- size: `1278`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x18010ba4c`

## callees

- `0x180019080`
- `0x1800e6838`
- `0x1800e688c`
- `0x1800e68b0`
- `0x1800ed46c`
- `0x1800ef868`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00e4`
- `0x18010611c`
- `0x180106914`
- `0x180109198`
- `0x180109e70`
- `0x18010e480`
- `0x180110aa8`
- `0x180110d34`
- `0x180111ec4`
- `0x180112620`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010e5ba`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010e5ba`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010e52d`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010e930`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010e52d`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x18010e930`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010e596`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010e596`
- `ext-ms-win-storage-sense-l1-1-0!CloseFindStorageSearch` at `0x18010e545`
- `ext-ms-win-storage-sense-l1-1-0!CloseFindStorageSearch` at `0x18010e948`
- `ext-ms-win-storage-sense-l1-1-0!CloseFindStorageSearch` at `0x18010e545`
- `ext-ms-win-storage-sense-l1-1-0!CloseFindStorageSearch` at `0x18010e948`
- `ext-ms-win-storage-sense-l1-1-0!FindNextStorageTypeEx` at `0x18010e727`
- `ext-ms-win-storage-sense-l1-1-0!FindNextStorageTypeEx` at `0x18010e727`
- `ext-ms-win-storage-sense-l1-1-0!SelectStorageVolumeEx` at `0x18010e654`
- `ext-ms-win-storage-sense-l1-1-0!SelectStorageVolumeEx` at `0x18010e654`
- `ext-ms-win-storage-sense-l1-1-0!OpenStorageTypeSearch` at `0x18010e5e0`
- `ext-ms-win-storage-sense-l1-1-0!OpenStorageTypeSearch` at `0x18010e5e0`
- `ext-ms-win-storage-sense-l1-2-3!GetStorageDeviceLowDiskState2` at `0x18010e6ab`
- `ext-ms-win-storage-sense-l1-2-3!GetStorageDeviceLowDiskState2` at `0x18010e6ab`

## string_xrefs

- `0x18010e7ad`: `%PROGRAMDATA%`
- `0x18010e505`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010e601`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010e741`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010e890`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`

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
      (void *)0x8FC,
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
    v9 = 2316;
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
    v9 = 2328;
    goto LABEL_10;
  }
  MdmLogCollector::WriteToFile(Stream, L"Total Space: %llu Free Space: %llu\n\n", v25 >> 20, v24 >> 20);
  v22 = 0;
  v16 = 0;
  StorageDeviceLowDiskState2 = GetStorageDeviceLowDiskState2(0, 0, 0, &v22);
  if ( StorageDeviceLowDiskState2 < 0 )
  {
    v9 = 2333;
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
        (void *)0x92B,
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
        (void *)0x947,
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
0x18010e480  mov     [rsp-8+arg_8], rbx
0x18010e485  mov     [rsp-8+arg_10], rsi
0x18010e48a  push    rbp
0x18010e48b  push    rdi
0x18010e48c  push    r14
0x18010e48e  lea     rbp, [rsp-0A0h]
0x18010e496  sub     rsp, 1A0h
0x18010e49d  mov     rax, cs:__security_cookie
0x18010e4a4  xor     rax, rsp
0x18010e4a7  mov     [rbp+0B0h+var_20], rax
0x18010e4ae  mov     rdi, rcx
0x18010e4b1  xor     r14d, r14d
0x18010e4b4  mov     [rsp+1B0h+Stream], r14
0x18010e4b9  mov     [rsp+1B0h+var_160], r14
0x18010e4be  mov     [rsp+1B0h+var_170], r14d
0x18010e4c3  lea     rax, [rsp+1B0h+var_170]
0x18010e4c8  mov     [rbp+0B0h+var_118], rax
0x18010e4cc  lea     rax, [rsp+1B0h+Stream]
0x18010e4d1  mov     [rbp+0B0h+var_110], rax
0x18010e4d5  lea     rax, [rsp+1B0h+var_160]
0x18010e4da  mov     [rbp+0B0h+var_108], rax
0x18010e4de  mov     [rbp+0B0h+var_100], 1
0x18010e4e2  lea     rcx, [rbp+0B0h+var_D8]
0x18010e4e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010e4eb  nop
0x18010e4ec  lea     rdx, [rbp+0B0h+var_D8]
0x18010e4f0  call    ?GetTemporaryOutputPath@MdmLogCollector@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetTemporaryOutputPath(std::wstring &)
0x18010e4f5  mov     ebx, eax
0x18010e4f7  test    eax, eax
0x18010e4f9  jns     short loc_18010E558
0x18010e4fb  mov     rcx, [rbp+0B8h]; this
0x18010e502  mov     r9d, eax; char *
0x18010e505  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010e50c  mov     edx, 8FCh; void *
0x18010e511  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e516  nop
0x18010e517  lea     rcx, [rbp+0B0h+var_D8]
0x18010e51b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e520  nop
0x18010e521  cmp     [rsp+1B0h+var_170], r14d
0x18010e526  jnz     short loc_18010E539
0x18010e528  mov     rcx, [rsp+1B0h+Stream]; Stream
0x18010e52d  call    cs:__imp_fclose
0x18010e534  nop     dword ptr [rax+rax+00h]
0x18010e539  cmp     [rsp+1B0h+var_160], r14
0x18010e53e  jz      short loc_18010E551
0x18010e540  lea     rcx, [rsp+1B0h+var_160]
0x18010e545  call    cs:__imp_CloseFindStorageSearch
0x18010e54c  nop     dword ptr [rax+rax+00h]
0x18010e551  mov     eax, ebx
0x18010e553  jmp     loc_18010E956
0x18010e558  lea     rdx, [rbp+0B0h+var_D8]
0x18010e55c  lea     rcx, [rbp+0B0h+var_F8]
0x18010e560  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18010e565  nop
0x18010e566  lea     rdx, aStoragesnapsho; "StorageSnapshot.txt"
0x18010e56d  lea     rcx, [rbp+0B0h+var_F8]
0x18010e571  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010e576  lea     rcx, [rbp+0B0h+var_F8]
0x18010e57a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010e57f  mov     rdx, rax; unsigned __int16 *
0x18010e582  mov     rcx, rdi; this
0x18010e585  call    ?AddFileEntry@MdmLogCollector@@QEAAJPEBG@Z; MdmLogCollector::AddFileEntry(ushort const *)
0x18010e58a  lea     rcx, [rbp+0B0h+var_F8]
0x18010e58e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010e593  mov     rcx, rax; lpFileName
0x18010e596  call    cs:__imp_DeleteFileW
0x18010e59d  nop     dword ptr [rax+rax+00h]
0x18010e5a2  lea     rcx, [rbp+0B0h+var_F8]
0x18010e5a6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010e5ab  mov     rdx, rax; FileName
0x18010e5ae  lea     r8, aA; "a+"
0x18010e5b5  lea     rcx, [rsp+1B0h+Stream]; Stream
0x18010e5ba  call    cs:__imp__wfopen_s
0x18010e5c1  nop     dword ptr [rax+rax+00h]
0x18010e5c6  mov     [rsp+1B0h+var_170], eax
0x18010e5ca  lea     rdx, aStorageSnapsho; "Storage snapshot (In MB)\n\n"
0x18010e5d1  mov     rcx, [rsp+1B0h+Stream]; struct _iobuf *
0x18010e5d6  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010e5db  lea     rcx, [rsp+1B0h+var_160]
0x18010e5e0  call    cs:__imp_OpenStorageTypeSearch
0x18010e5e7  nop     dword ptr [rax+rax+00h]
0x18010e5ec  mov     ebx, eax
0x18010e5ee  test    eax, eax
0x18010e5f0  jns     short loc_18010E61C
0x18010e5f2  mov     edx, 90Ch; void *
0x18010e5f7  mov     rcx, [rbp+0B8h]; this
0x18010e5fe  mov     r9d, ebx; char *
0x18010e601  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010e608  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e60d  nop
0x18010e60e  lea     rcx, [rbp+0B0h+var_F8]
0x18010e612  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e617  jmp     loc_18010E517
0x18010e61c  mov     [rsp+1B0h+var_138], r14
0x18010e621  mov     [rsp+1B0h+var_140], r14
0x18010e626  lea     rax, [rsp+1B0h+var_140]
0x18010e62b  mov     [rsp+1B0h+var_178], rax
0x18010e630  lea     rax, [rsp+1B0h+var_138]
0x18010e635  mov     [rsp+1B0h+var_180], rax
0x18010e63a  mov     dword ptr [rsp+1B0h+var_188], 1
0x18010e642  mov     qword ptr [rsp+1B0h+var_190], r14
0x18010e647  xor     r9d, r9d
0x18010e64a  xor     r8d, r8d
0x18010e64d  xor     edx, edx
0x18010e64f  mov     rcx, [rsp+1B0h+var_160]
0x18010e654  call    cs:__imp_SelectStorageVolumeEx
0x18010e65b  nop     dword ptr [rax+rax+00h]
0x18010e660  mov     ebx, eax
0x18010e662  test    eax, eax
0x18010e664  jns     short loc_18010E66D
0x18010e666  mov     edx, 918h
0x18010e66b  jmp     short loc_18010E5F7
0x18010e66d  mov     r9, [rsp+1B0h+var_140]
0x18010e672  shr     r9, 14h
0x18010e676  mov     r8, [rsp+1B0h+var_138]
0x18010e67b  shr     r8, 14h
0x18010e67f  lea     rdx, aTotalSpaceLluF; "Total Space: %llu Free Space: %llu\n\n"
0x18010e686  mov     rcx, [rsp+1B0h+Stream]; struct _iobuf *
0x18010e68b  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010e690  mov     [rsp+1B0h+var_150], r14d
0x18010e695  mov     [rsp+1B0h+var_188], r14
0x18010e69a  mov     qword ptr [rsp+1B0h+var_190], r14
0x18010e69f  lea     r9, [rsp+1B0h+var_150]
0x18010e6a4  xor     r8d, r8d
0x18010e6a7  xor     edx, edx
0x18010e6a9  xor     ecx, ecx
0x18010e6ab  call    cs:__imp_GetStorageDeviceLowDiskState2
0x18010e6b2  nop     dword ptr [rax+rax+00h]
0x18010e6b7  mov     ebx, eax
0x18010e6b9  test    eax, eax
0x18010e6bb  jns     short loc_18010E6C7
0x18010e6bd  mov     edx, 91Dh
0x18010e6c2  jmp     loc_18010E5F7
0x18010e6c7  mov     r8d, r14d
0x18010e6ca  cmp     [rsp+1B0h+var_150], r14d
0x18010e6cf  setnz   r8b
0x18010e6d3  lea     rdx, aInLowDiskState; "In low disk state: %d\n"
0x18010e6da  mov     rcx, [rsp+1B0h+Stream]; struct _iobuf *
0x18010e6df  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010e6e4  lea     rdx, aStorageNodeKey; "\nStorage Node Key: Size \n"
0x18010e6eb  mov     rcx, [rsp+1B0h+Stream]; struct _iobuf *
0x18010e6f0  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010e6f5  mov     ebx, r14d
0x18010e6f8  mov     qword ptr [rsp+1B0h+var_158], r14
0x18010e6fd  mov     [rsp+1B0h+var_148], r14
0x18010e702  lea     rax, [rsp+1B0h+var_148]
0x18010e707  mov     [rsp+1B0h+var_188], rax
0x18010e70c  lea     rax, [rsp+1B0h+var_158]
0x18010e711  mov     qword ptr [rsp+1B0h+var_190], rax; int
0x18010e716  xor     r9d, r9d
0x18010e719  lea     r8, Name
0x18010e720  mov     edx, ebx
0x18010e722  mov     rcx, [rsp+1B0h+var_160]
0x18010e727  call    cs:__imp_FindNextStorageTypeEx
0x18010e72e  nop     dword ptr [rax+rax+00h]
0x18010e733  mov     rcx, [rbp+0B8h]; this
0x18010e73a  test    eax, eax
0x18010e73c  jns     short loc_18010E754
0x18010e73e  mov     r9d, eax; char *
0x18010e741  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010e748  mov     edx, 92Bh; void *
0x18010e74d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010e752  jmp     short loc_18010E776
0x18010e754  mov     r9, qword ptr [rsp+1B0h+var_158]
0x18010e759  test    r9, r9
0x18010e75c  jz      short loc_18010E776
0x18010e75e  shr     r9, 14h
0x18010e762  mov     r8d, ebx
0x18010e765  lea     rdx, aDLlu; "%d: %llu\n"
0x18010e76c  mov     rcx, [rsp+1B0h+Stream]; struct _iobuf *
0x18010e771  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010e776  inc     ebx
0x18010e778  cmp     ebx, 22h ; '"'
0x18010e77b  jl      loc_18010E6F8
0x18010e781  lea     rax, aDatadriveCrash; "%DATADRIVE%\\crashdump"
0x18010e788  mov     [rbp+0B0h+var_B0], rax
0x18010e78c  lea     rax, aDataCrashdump; "Data Crashdump"
0x18010e793  mov     [rbp+0B0h+var_A8], rax
0x18010e797  lea     rax, aDatadriveSyste; "%DATADRIVE%\\systemdata\\etw"
0x18010e79e  mov     [rbp+0B0h+var_A0], rax
0x18010e7a2  lea     rax, aDataDiagnostic; "Data Diagnostics"
0x18010e7a9  mov     [rbp+0B0h+var_98], rax
0x18010e7ad  lea     rax, aProgramdata; "%PROGRAMDATA%"
0x18010e7b4  mov     [rbp+0B0h+var_90], rax
0x18010e7b8  lea     rax, aDataPrograms; "Data Programs"
0x18010e7bf  mov     [rbp+0B0h+var_88], rax
0x18010e7c3  lea     rax, aOsdatadriveSys_0; "%OSDATADRIVE%\\systemdata\\etw"
0x18010e7ca  mov     [rbp+0B0h+var_80], rax
0x18010e7ce  lea     rax, aOsDataDiagnost; "OS Data Diagnostics"
0x18010e7d5  mov     [rbp+0B0h+var_78], rax
0x18010e7d9  lea     rax, aOsdatadriveLog; "%OSDATADRIVE%\\logfiles"
0x18010e7e0  mov     [rbp+0B0h+var_70], rax
0x18010e7e4  lea     rax, aOsDataLogfiles; "OS Data LogFiles"
0x18010e7eb  mov     [rbp+0B0h+var_68], rax
0x18010e7ef  lea     rax, aOsdatadriveSha; "%OSDATADRIVE%\\shareddata"
0x18010e7f6  mov     [rbp+0B0h+var_60], rax
0x18010e7fa  lea     rax, aOsDataShared; "OS Data Shared"
0x18010e801  mov     [rbp+0B0h+var_58], rax
0x18010e805  lea     rax, aSystemdriveDat; "%SYSTEMDRIVE%\\data\\users"
0x18010e80c  mov     [rbp+0B0h+var_50], rax
0x18010e810  lea     rax, aSystemUsers; "System Users"
0x18010e817  mov     [rbp+0B0h+var_48], rax
0x18010e81b  xorps   xmm0, xmm0
0x18010e81e  movdqu  [rbp+0B0h+var_130], xmm0
0x18010e823  mov     [rbp+0B0h+var_120], r14
0x18010e827  lea     rax, [rbp+0B0h+var_40]
0x18010e82b  mov     [rsp+1B0h+var_148], rax
0x18010e830  lea     rax, [rbp+0B0h+var_B0]
0x18010e834  mov     qword ptr [rsp+1B0h+var_158], rax
0x18010e839  lea     r9, [rsp+1B0h+var_148]
0x18010e83e  lea     r8, [rsp+1B0h+var_158]
0x18010e843  mov     edx, 7
0x18010e848  lea     rcx, [rbp+0B0h+var_130]
0x18010e84c  call    ??$_Construct_n@PEBV?$tuple@PEBGPEBG@std@@PEBV12@@?$vector@V?$tuple@PEBGPEBG@std@@V?$allocator@V?$tuple@PEBGPEBG@std@@@2@@std@@AEAAX_K$$QEAPEBV?$tuple@PEBGPEBG@1@1@Z; std::vector<std::tuple<ushort const *,ushort const *>>::_Construct_n<std::tuple<ushort const *,ushort const *> const *,std::tuple<ushort const *,ushort const *> const *>(unsigned __int64,std::tuple<ushort const *,ushort const *> const * &&,std::tuple<ushort const *,ushort const *> const * &&)
0x18010e851  nop
0x18010e852  lea     rdx, aFolderKeySize; "\nFolder Key: Size\n"
0x18010e859  mov     rcx, [rsp+1B0h+Stream]; struct _iobuf *
0x18010e85e  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010e863  mov     rbx, qword ptr [rbp+0B0h+var_130]
0x18010e867  mov     rsi, qword ptr [rbp+0B0h+var_130+8]
0x18010e86b  jmp     loc_18010E8FD
0x18010e870  mov     qword ptr [rsp+1B0h+var_158], r14
0x18010e875  lea     rdx, [rsp+1B0h+var_158]
0x18010e87a  mov     rcx, [rbx]
0x18010e87d  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18010e882  mov     rcx, [rbp+0B8h]; this
0x18010e889  test    eax, eax
0x18010e88b  jns     short loc_18010E8A3
0x18010e88d  mov     r9d, eax; char *
0x18010e890  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010e897  mov     edx, 947h; void *
0x18010e89c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010e8a1  jmp     short loc_18010E8EF
0x18010e8a3  mov     rdx, qword ptr [rsp+1B0h+var_158]
0x18010e8a8  lea     rcx, [rbp+0B0h+var_40]
0x18010e8ac  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010e8b1  nop
0x18010e8b2  lea     rcx, [rbp+0B0h+var_40]
0x18010e8b6  call    ?GetFolderSizeInBytes@@YA_JAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetFolderSizeInBytes(std::wstring const &)
0x18010e8bb  cqo
0x18010e8bd  mov     ecx, 100000h
0x18010e8c2  idiv    rcx
0x18010e8c5  mov     rdi, rax
0x18010e8c8  lea     rcx, [rbp+0B0h+var_40]
0x18010e8cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e8d1  test    rdi, rdi
0x18010e8d4  jle     short loc_18010E8EF
0x18010e8d6  mov     r9, rdi
0x18010e8d9  mov     r8, [rbx+8]
0x18010e8dd  lea     rdx, aWsLld; "%ws: %lld\n"
0x18010e8e4  mov     rcx, [rsp+1B0h+Stream]; struct _iobuf *
0x18010e8e9  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010e8ee  nop
0x18010e8ef  lea     rcx, [rsp+1B0h+var_158]
0x18010e8f4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18010e8f9  add     rbx, 10h
0x18010e8fd  cmp     rbx, rsi
0x18010e900  jnz     loc_18010E870
0x18010e906  lea     rcx, [rbp+0B0h+var_130]
0x18010e90a  call    ??1?$vector@U_Loop_vals_v2_t@std@@V?$allocator@U_Loop_vals_v2_t@std@@@2@@std@@QEAA@XZ; std::vector<std::_Loop_vals_v2_t>::~vector<std::_Loop_vals_v2_t>(void)
0x18010e90f  nop
0x18010e910  lea     rcx, [rbp+0B0h+var_F8]
0x18010e914  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e919  nop
0x18010e91a  lea     rcx, [rbp+0B0h+var_D8]
0x18010e91e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010e923  nop
0x18010e924  cmp     [rsp+1B0h+var_170], r14d
0x18010e929  jnz     short loc_18010E93C
0x18010e92b  mov     rcx, [rsp+1B0h+Stream]; Stream
0x18010e930  call    cs:__imp_fclose
0x18010e937  nop     dword ptr [rax+rax+00h]
0x18010e93c  cmp     [rsp+1B0h+var_160], r14
0x18010e941  jz      short loc_18010E954
0x18010e943  lea     rcx, [rsp+1B0h+var_160]
0x18010e948  call    cs:__imp_CloseFindStorageSearch
0x18010e94f  nop     dword ptr [rax+rax+00h]
0x18010e954  xor     eax, eax
0x18010e956  mov     rcx, [rbp+0B0h+var_20]
0x18010e95d  xor     rcx, rsp; StackCookie
0x18010e960  call    __security_check_cookie
0x18010e965  lea     r11, [rsp+1B0h+var_10]
0x18010e96d  mov     rbx, [r11+28h]
0x18010e971  mov     rsi, [r11+30h]
0x18010e975  mov     rsp, r11
0x18010e978  pop     r14
0x18010e97a  pop     rdi
0x18010e97b  pop     rbp
0x18010e97c  retn
```
