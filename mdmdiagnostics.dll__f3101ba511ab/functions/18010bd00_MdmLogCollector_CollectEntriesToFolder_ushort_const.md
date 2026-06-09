# MdmLogCollector::CollectEntriesToFolder(ushort const *)

- ea: `0x18010bd00`
- end: `0x18010c0a6`
- name: `?CollectEntriesToFolder@MdmLogCollector@@AEAAJPEBG@Z`
- size: `934`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this, LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config`

## callers

- `0x18010cb20`

## callees

- `0x180019080`
- `0x1800e6838`
- `0x1800e68b0`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1800f00ac`
- `0x1800f00e4`
- `0x180106b3c`
- `0x180106b6c`
- `0x180106dc8`
- `0x180106ee0`
- `0x18010964c`
- `0x18010a6dc`
- `0x18010bd00`
- `0x18010c0ac`
- `0x18010c24c`
- `0x18010c7b0`
- `0x18010d5a0`
- `0x18010eeb8`
- `0x180110218`
- `0x180111e34`
- `0x180111ec4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010bdea`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010bdea`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010bdb9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010bdb9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18010bd2f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18010bd2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010bd3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010bd3f`

## string_xrefs

- `0x18010bfa7`: `Failed to CollectRegistryEntries. HResult:0x%08x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
signed int __fastcall MdmLogCollector::CollectEntriesToFolder(MdmLogCollector *this, LPCWSTR lpPathName)
{
  signed int result; // eax
  const WCHAR *v5; // rax
  const wchar_t *v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rdx
  char *v11; // rcx
  __int64 v12; // rdx
  char *v13; // rcx
  const unsigned __int16 *v14; // rax
  int v15; // eax
  const unsigned __int16 *v16; // rax
  int v17; // eax
  const unsigned __int16 *v18; // rax
  int v19; // eax
  const unsigned __int16 *v20; // rax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  const unsigned __int16 *v24; // rax
  FILE *Stream; // [rsp+20h] [rbp-B8h] BYREF
  errno_t v26; // [rsp+28h] [rbp-B0h] BYREF
  _QWORD v27[2]; // [rsp+30h] [rbp-A8h] BYREF
  char v28; // [rsp+40h] [rbp-98h]
  _BYTE v29[32]; // [rsp+48h] [rbp-90h] BYREF
  _BYTE v30[32]; // [rsp+68h] [rbp-70h] BYREF
  _BYTE v31[32]; // [rsp+88h] [rbp-50h] BYREF
  _BYTE v32[32]; // [rsp+A8h] [rbp-30h] BYREF

  if ( CreateDirectoryW(lpPathName, 0) || (result = GetLastError(), result == 183) )
  {
    std::wstring::wstring(v29, lpPathName);
    std::wstring::append(v29, L"\\");
    std::wstring::wstring(v31, v29);
    std::wstring::append(v31, L"MdmLogCollectorFootPrint.txt");
    v5 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
    DeleteFileW(v5);
    Stream = 0;
    v6 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
    v26 = _wfopen_s(&Stream, v6, L"a+");
    v27[0] = &v26;
    v27[1] = &Stream;
    v28 = 1;
    MdmLogCollector::WriteToFile(Stream, L"--- Start at:");
    MdmLogCollector::WriteSystemTime(Stream);
    MdmLogCollector::WriteToFile(Stream, L"\n");
    std::wstring::wstring(v30, L"\"AreaName\" : \"");
    v7 = *((_QWORD *)this + 13);
    v8 = *((_QWORD *)this + 14);
    while ( v7 != v8 )
    {
      std::wstring::append(v30, v7);
      std::wstring::append(v30, L";");
      v7 += 32;
    }
    std::wstring::append(v30, L"\"");
    v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
    MdmLogCollector::WriteToFile(Stream, L"%s\n", v9);
    std::wstring::wstring(v32, L"\"MdmDiagVersion\":\"1.0\"");
    v10 = *((_QWORD *)this + 17);
    v11 = (char *)this + 128;
    if ( v10 == *((_QWORD *)this + 18) )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v11, v10, v32);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(v11, v32);
    std::wstring::_Tidy_deallocate(v32);
    v12 = *((_QWORD *)this + 17);
    v13 = (char *)this + 128;
    if ( v12 == *((_QWORD *)this + 18) )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(v13, v12, v30);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(v13, v30);
    v14 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    v15 = MdmLogCollector::CollectEventViewerEntries(this, Stream, v14);
    if ( v15 < 0 )
      MdmLogCollector::WriteToFile(Stream, L"Failed to CollectEventViewerEntries. HResult:0x%08x\n", (unsigned int)v15);
    v16 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    v17 = MdmLogCollector::CollectFileEntries(this, Stream, v16);
    if ( v17 < 0 )
      MdmLogCollector::WriteToFile(Stream, L"Failed to CollectFileEntries. HResult:0x%08x\n", (unsigned int)v17);
    v18 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    v19 = MdmLogCollector::CollectRegistryEntries(this, Stream, v18);
    if ( v19 < 0 )
      MdmLogCollector::WriteToFile(Stream, L"Failed to CollectRegistryEntries. HResult:0x%08x\n", (unsigned int)v19);
    v20 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    v21 = MdmLogCollector::CollectTracingSessionEntries(this, Stream, v20);
    if ( v21 < 0 )
      MdmLogCollector::WriteToFile(
        Stream,
        L"Failed to CollectTracingSessionEntries. HResult:0x%08x\n",
        (unsigned int)v21);
    v22 = MdmLogCollector::CollectFullVersionInfo(this);
    if ( v22 < 0 )
      MdmLogCollector::WriteToFile(Stream, L"Failed to CollectFullVersionInfo. HResult:0x%08x\n", (unsigned int)v22);
    v23 = MdmLogCollector::CollectAutologonInfo(this);
    if ( v23 < 0 )
      MdmLogCollector::WriteToFile(Stream, L"Failed to CollectAutologonInfo. HResult:0x%08x\n", (unsigned int)v23);
    v24 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    MdmLogCollector::GenerateMetadataFile(this, Stream, v24);
    std::wstring::_Tidy_deallocate(v30);
    v28 = 0;
    lambda_5b3d6c233d4eae6053aaad5e34b7a9fd_::operator()(v27);
    std::wstring::_Tidy_deallocate(v31);
    std::wstring::_Tidy_deallocate(v29);
    return 0;
  }
  else if ( result > 0 )
  {
    return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18010bd00  mov     [rsp+arg_10], rbx
0x18010bd05  mov     [rsp+arg_18], rsi
0x18010bd0a  push    rdi
0x18010bd0b  sub     rsp, 0D0h
0x18010bd12  mov     rax, cs:__security_cookie
0x18010bd19  xor     rax, rsp
0x18010bd1c  mov     [rsp+0D8h+var_10], rax
0x18010bd24  mov     rdi, rdx
0x18010bd27  mov     rbx, rcx
0x18010bd2a  xor     edx, edx; lpSecurityAttributes
0x18010bd2c  mov     rcx, rdi; lpPathName
0x18010bd2f  call    cs:__imp_CreateDirectoryW
0x18010bd36  nop     dword ptr [rax+rax+00h]
0x18010bd3b  test    eax, eax
0x18010bd3d  jnz     short loc_18010BD63
0x18010bd3f  call    cs:__imp_GetLastError
0x18010bd46  nop     dword ptr [rax+rax+00h]
0x18010bd4b  cmp     eax, 0B7h
0x18010bd50  jz      short loc_18010BD63
0x18010bd52  test    eax, eax
0x18010bd54  jle     short loc_18010BD5E
0x18010bd56  movzx   eax, ax
0x18010bd59  or      eax, 80070000h
0x18010bd5e  jmp     loc_18010C080
0x18010bd63  mov     rdx, rdi
0x18010bd66  lea     rcx, [rsp+0D8h+var_90]
0x18010bd6b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010bd70  nop
0x18010bd71  lea     rdx, psz; "\\"
0x18010bd78  lea     rcx, [rsp+0D8h+var_90]
0x18010bd7d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010bd82  lea     rdx, [rsp+0D8h+var_90]
0x18010bd87  lea     rcx, [rsp+0D8h+var_50]
0x18010bd8f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18010bd94  nop
0x18010bd95  lea     rdx, aMdmlogcollecto_0; "MdmLogCollectorFootPrint.txt"
0x18010bd9c  lea     rcx, [rsp+0D8h+var_50]
0x18010bda4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010bda9  lea     rcx, [rsp+0D8h+var_50]
0x18010bdb1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010bdb6  mov     rcx, rax; lpFileName
0x18010bdb9  call    cs:__imp_DeleteFileW
0x18010bdc0  nop     dword ptr [rax+rax+00h]
0x18010bdc5  mov     [rsp+0D8h+Stream], 0
0x18010bdce  lea     rcx, [rsp+0D8h+var_50]
0x18010bdd6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010bddb  mov     rdx, rax; FileName
0x18010bdde  lea     r8, aA; "a+"
0x18010bde5  lea     rcx, [rsp+0D8h+Stream]; Stream
0x18010bdea  call    cs:__imp__wfopen_s
0x18010bdf1  nop     dword ptr [rax+rax+00h]
0x18010bdf6  mov     [rsp+0D8h+var_B0], eax
0x18010bdfa  lea     rax, [rsp+0D8h+var_B0]
0x18010bdff  mov     [rsp+0D8h+var_A8], rax
0x18010be04  lea     rax, [rsp+0D8h+Stream]
0x18010be09  mov     [rsp+0D8h+var_A0], rax
0x18010be0e  mov     [rsp+0D8h+var_98], 1
0x18010be13  lea     rdx, aStartAt; "--- Start at:"
0x18010be1a  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010be1f  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010be24  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010be29  call    ?WriteSystemTime@MdmLogCollector@@CAXPEAU_iobuf@@@Z; MdmLogCollector::WriteSystemTime(_iobuf *)
0x18010be2e  lea     rdx, asc_1801BBCF8; "\n"
0x18010be35  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010be3a  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010be3f  lea     rdx, aAreaname_0; "\"AreaName\" : \""
0x18010be46  lea     rcx, [rsp+0D8h+var_70]
0x18010be4b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010be50  nop
0x18010be51  mov     rdi, [rbx+68h]
0x18010be55  mov     rsi, [rbx+70h]
0x18010be59  lea     rcx, [rsp+0D8h+var_70]
0x18010be5e  cmp     rdi, rsi
0x18010be61  jz      short loc_18010BE82
0x18010be63  mov     rdx, rdi
0x18010be66  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18010be6b  lea     rdx, asc_1801D32C8; ";"
0x18010be72  lea     rcx, [rsp+0D8h+var_70]
0x18010be77  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010be7c  add     rdi, 20h ; ' '
0x18010be80  jmp     short loc_18010BE59
0x18010be82  lea     rdx, asc_1801D32C4; "\""
0x18010be89  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010be8e  lea     rcx, [rsp+0D8h+var_70]
0x18010be93  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010be98  mov     r8, rax
0x18010be9b  lea     rdx, aS_5; "%s\n"
0x18010bea2  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010bea7  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010beac  lea     rdi, [rbx+80h]
0x18010beb3  lea     rdx, aMdmdiagversion; "\"MdmDiagVersion\":\"1.0\""
0x18010beba  lea     rcx, [rsp+0D8h+var_30]
0x18010bec2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010bec7  nop
0x18010bec8  mov     rdx, [rdi+8]
0x18010becc  mov     rcx, rdi
0x18010becf  cmp     rdx, [rdi+10h]
0x18010bed3  jz      short loc_18010BEE4
0x18010bed5  lea     rdx, [rsp+0D8h+var_30]
0x18010bedd  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18010bee2  jmp     short loc_18010BEF2
0x18010bee4  lea     r8, [rsp+0D8h+var_30]
0x18010beec  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18010bef1  nop
0x18010bef2  lea     rcx, [rsp+0D8h+var_30]
0x18010befa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010beff  mov     rdx, [rdi+8]
0x18010bf03  mov     rcx, rdi
0x18010bf06  cmp     rdx, [rdi+10h]
0x18010bf0a  jz      short loc_18010BF18
0x18010bf0c  lea     rdx, [rsp+0D8h+var_70]
0x18010bf11  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x18010bf16  jmp     short loc_18010BF22
0x18010bf18  lea     r8, [rsp+0D8h+var_70]
0x18010bf1d  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18010bf22  lea     rcx, [rsp+0D8h+var_90]
0x18010bf27  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010bf2c  mov     r8, rax; unsigned __int16 *
0x18010bf2f  mov     rdx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010bf34  mov     rcx, rbx; this
0x18010bf37  call    ?CollectEventViewerEntries@MdmLogCollector@@AEAAJPEAU_iobuf@@PEBG@Z; MdmLogCollector::CollectEventViewerEntries(_iobuf *,ushort const *)
0x18010bf3c  test    eax, eax
0x18010bf3e  jns     short loc_18010BF54
0x18010bf40  mov     r8d, eax
0x18010bf43  lea     rdx, aFailedToCollec_6; "Failed to CollectEventViewerEntries. HR"...
0x18010bf4a  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010bf4f  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010bf54  lea     rcx, [rsp+0D8h+var_90]
0x18010bf59  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010bf5e  mov     r8, rax; unsigned __int16 *
0x18010bf61  mov     rdx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010bf66  mov     rcx, rbx; this
0x18010bf69  call    ?CollectFileEntries@MdmLogCollector@@AEAAJPEAU_iobuf@@PEBG@Z; MdmLogCollector::CollectFileEntries(_iobuf *,ushort const *)
0x18010bf6e  test    eax, eax
0x18010bf70  jns     short loc_18010BF86
0x18010bf72  mov     r8d, eax
0x18010bf75  lea     rdx, aFailedToCollec_0; "Failed to CollectFileEntries. HResult:0"...
0x18010bf7c  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010bf81  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010bf86  lea     rcx, [rsp+0D8h+var_90]
0x18010bf8b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010bf90  mov     r8, rax; unsigned __int16 *
0x18010bf93  mov     rdx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010bf98  mov     rcx, rbx; this
0x18010bf9b  call    ?CollectRegistryEntries@MdmLogCollector@@AEAAJPEAU_iobuf@@PEBG@Z; MdmLogCollector::CollectRegistryEntries(_iobuf *,ushort const *)
0x18010bfa0  test    eax, eax
0x18010bfa2  jns     short loc_18010BFB8
0x18010bfa4  mov     r8d, eax
0x18010bfa7  lea     rdx, aFailedToCollec_2; "Failed to CollectRegistryEntries. HResu"...
0x18010bfae  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010bfb3  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010bfb8  lea     rcx, [rsp+0D8h+var_90]
0x18010bfbd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010bfc2  mov     r8, rax; unsigned __int16 *
0x18010bfc5  mov     rdx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010bfca  mov     rcx, rbx; this
0x18010bfcd  call    ?CollectTracingSessionEntries@MdmLogCollector@@AEAAJPEAU_iobuf@@PEBG@Z; MdmLogCollector::CollectTracingSessionEntries(_iobuf *,ushort const *)
0x18010bfd2  test    eax, eax
0x18010bfd4  jns     short loc_18010BFEA
0x18010bfd6  mov     r8d, eax
0x18010bfd9  lea     rdx, aFailedToCollec_3; "Failed to CollectTracingSessionEntries."...
0x18010bfe0  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010bfe5  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010bfea  mov     rcx, rbx; this
0x18010bfed  call    ?CollectFullVersionInfo@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectFullVersionInfo(void)
0x18010bff2  test    eax, eax
0x18010bff4  jns     short loc_18010C00A
0x18010bff6  mov     r8d, eax
0x18010bff9  lea     rdx, aFailedToCollec_1; "Failed to CollectFullVersionInfo. HResu"...
0x18010c000  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010c005  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010c00a  mov     rcx, rbx; this
0x18010c00d  call    ?CollectAutologonInfo@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectAutologonInfo(void)
0x18010c012  test    eax, eax
0x18010c014  jns     short loc_18010C02A
0x18010c016  mov     r8d, eax
0x18010c019  lea     rdx, aFailedToCollec_5; "Failed to CollectAutologonInfo. HResult"...
0x18010c020  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010c025  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010c02a  lea     rcx, [rsp+0D8h+var_90]
0x18010c02f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010c034  mov     r8, rax; unsigned __int16 *
0x18010c037  mov     rdx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010c03c  mov     rcx, rbx; this
0x18010c03f  call    ?GenerateMetadataFile@MdmLogCollector@@AEAAJPEAU_iobuf@@PEBG@Z; MdmLogCollector::GenerateMetadataFile(_iobuf *,ushort const *)
0x18010c044  nop
0x18010c045  lea     rcx, [rsp+0D8h+var_70]
0x18010c04a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010c04f  nop
0x18010c050  mov     [rsp+0D8h+var_98], 0
0x18010c055  lea     rcx, [rsp+0D8h+var_A8]
0x18010c05a  call    _lambda_5b3d6c233d4eae6053aaad5e34b7a9fd___operator__
0x18010c05f  nop
0x18010c060  lea     rcx, [rsp+0D8h+var_50]
0x18010c068  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010c06d  nop
0x18010c06e  lea     rcx, [rsp+0D8h+var_90]
0x18010c073  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010c078  xor     eax, eax
0x18010c07a  jmp     short loc_18010C080
0x18010c07c  mov     eax, [rsp+0D8h+var_B0]
0x18010c080  mov     rcx, [rsp+0D8h+var_10]
0x18010c088  xor     rcx, rsp; StackCookie
0x18010c08b  call    __security_check_cookie
0x18010c090  lea     r11, [rsp+0D8h+var_8]
0x18010c098  mov     rbx, [r11+20h]
0x18010c09c  mov     rsi, [r11+28h]
0x18010c0a0  mov     rsp, r11
0x18010c0a3  pop     rdi
0x18010c0a4  retn
```
