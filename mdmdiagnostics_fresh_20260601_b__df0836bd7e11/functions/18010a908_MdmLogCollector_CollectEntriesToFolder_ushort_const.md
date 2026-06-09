# MdmLogCollector::CollectEntriesToFolder(ushort const *)

- ea: `0x18010a908`
- end: `0x18010ac96`
- name: `?CollectEntriesToFolder@MdmLogCollector@@AEAAJPEBG@Z`
- size: `910`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this, LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config`

## callers

- `0x18010b6d4`

## callees

- `0x180019000`
- `0x1800e6664`
- `0x1800e66dc`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1800ef8c8`
- `0x1800ef900`
- `0x18010589c`
- `0x1801058cc`
- `0x180105b28`
- `0x180105c40`
- `0x18010830c`
- `0x180109340`
- `0x18010a908`
- `0x18010ac9c`
- `0x18010ae30`
- `0x18010b364`
- `0x18010c120`
- `0x18010d978`
- `0x18010ec58`
- `0x180110974`
- `0x1801109fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010a9e0`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18010a9e0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010a9b5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010a9b5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18010a937`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18010a937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010a941`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010a941`

## string_xrefs

- `0x18010ab97`: `Failed to CollectRegistryEntries. HResult:0x%08x\n`

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
0x18010a908  mov     [rsp+arg_10], rbx
0x18010a90d  mov     [rsp+arg_18], rsi
0x18010a912  push    rdi
0x18010a913  sub     rsp, 0D0h
0x18010a91a  mov     rax, cs:__security_cookie
0x18010a921  xor     rax, rsp
0x18010a924  mov     [rsp+0D8h+var_10], rax
0x18010a92c  mov     rdi, rdx
0x18010a92f  mov     rbx, rcx
0x18010a932  xor     edx, edx; lpSecurityAttributes
0x18010a934  mov     rcx, rdi; lpPathName
0x18010a937  call    cs:__imp_CreateDirectoryW
0x18010a93d  test    eax, eax
0x18010a93f  jnz     short loc_18010A95F
0x18010a941  call    cs:__imp_GetLastError
0x18010a947  cmp     eax, 0B7h
0x18010a94c  jz      short loc_18010A95F
0x18010a94e  test    eax, eax
0x18010a950  jle     short loc_18010A95A
0x18010a952  movzx   eax, ax
0x18010a955  or      eax, 80070000h
0x18010a95a  jmp     loc_18010AC70
0x18010a95f  mov     rdx, rdi
0x18010a962  lea     rcx, [rsp+0D8h+var_90]
0x18010a967  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010a96c  nop
0x18010a96d  lea     rdx, psz; "\\"
0x18010a974  lea     rcx, [rsp+0D8h+var_90]
0x18010a979  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010a97e  lea     rdx, [rsp+0D8h+var_90]
0x18010a983  lea     rcx, [rsp+0D8h+var_50]
0x18010a98b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18010a990  nop
0x18010a991  lea     rdx, aMdmlogcollecto_0; "MdmLogCollectorFootPrint.txt"
0x18010a998  lea     rcx, [rsp+0D8h+var_50]
0x18010a9a0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010a9a5  lea     rcx, [rsp+0D8h+var_50]
0x18010a9ad  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010a9b2  mov     rcx, rax; lpFileName
0x18010a9b5  call    cs:__imp_DeleteFileW
0x18010a9bb  mov     [rsp+0D8h+Stream], 0
0x18010a9c4  lea     rcx, [rsp+0D8h+var_50]
0x18010a9cc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010a9d1  mov     rdx, rax; FileName
0x18010a9d4  lea     r8, aA; "a+"
0x18010a9db  lea     rcx, [rsp+0D8h+Stream]; Stream
0x18010a9e0  call    cs:__imp__wfopen_s
0x18010a9e6  mov     [rsp+0D8h+var_B0], eax
0x18010a9ea  lea     rax, [rsp+0D8h+var_B0]
0x18010a9ef  mov     [rsp+0D8h+var_A8], rax
0x18010a9f4  lea     rax, [rsp+0D8h+Stream]
0x18010a9f9  mov     [rsp+0D8h+var_A0], rax
0x18010a9fe  mov     [rsp+0D8h+var_98], 1
0x18010aa03  lea     rdx, aStartAt; "--- Start at:"
0x18010aa0a  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010aa0f  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010aa14  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010aa19  call    ?WriteSystemTime@MdmLogCollector@@CAXPEAU_iobuf@@@Z; MdmLogCollector::WriteSystemTime(_iobuf *)
0x18010aa1e  lea     rdx, asc_1801B9CF8; "\n"
0x18010aa25  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010aa2a  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010aa2f  lea     rdx, aAreaname_0; "\"AreaName\" : \""
0x18010aa36  lea     rcx, [rsp+0D8h+var_70]
0x18010aa3b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010aa40  nop
0x18010aa41  mov     rdi, [rbx+68h]
0x18010aa45  mov     rsi, [rbx+70h]
0x18010aa49  lea     rcx, [rsp+0D8h+var_70]
0x18010aa4e  cmp     rdi, rsi
0x18010aa51  jz      short loc_18010AA72
0x18010aa53  mov     rdx, rdi
0x18010aa56  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18010aa5b  lea     rdx, asc_1801D12D8; ";"
0x18010aa62  lea     rcx, [rsp+0D8h+var_70]
0x18010aa67  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010aa6c  add     rdi, 20h ; ' '
0x18010aa70  jmp     short loc_18010AA49
0x18010aa72  lea     rdx, asc_1801D12D4; "\""
0x18010aa79  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010aa7e  lea     rcx, [rsp+0D8h+var_70]
0x18010aa83  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010aa88  mov     r8, rax
0x18010aa8b  lea     rdx, aS_5; "%s\n"
0x18010aa92  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010aa97  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010aa9c  lea     rdi, [rbx+80h]
0x18010aaa3  lea     rdx, aMdmdiagversion; "\"MdmDiagVersion\":\"1.0\""
0x18010aaaa  lea     rcx, [rsp+0D8h+var_30]
0x18010aab2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010aab7  nop
0x18010aab8  mov     rdx, [rdi+8]
0x18010aabc  mov     rcx, rdi
0x18010aabf  cmp     rdx, [rdi+10h]
0x18010aac3  jz      short loc_18010AAD4
0x18010aac5  lea     rdx, [rsp+0D8h+var_30]
0x18010aacd  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18010aad2  jmp     short loc_18010AAE2
0x18010aad4  lea     r8, [rsp+0D8h+var_30]
0x18010aadc  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18010aae1  nop
0x18010aae2  lea     rcx, [rsp+0D8h+var_30]
0x18010aaea  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010aaef  mov     rdx, [rdi+8]
0x18010aaf3  mov     rcx, rdi
0x18010aaf6  cmp     rdx, [rdi+10h]
0x18010aafa  jz      short loc_18010AB08
0x18010aafc  lea     rdx, [rsp+0D8h+var_70]
0x18010ab01  call    ??$_Emplace_back_with_unused_capacity@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring const &>(std::wstring const &)
0x18010ab06  jmp     short loc_18010AB12
0x18010ab08  lea     r8, [rsp+0D8h+var_70]
0x18010ab0d  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x18010ab12  lea     rcx, [rsp+0D8h+var_90]
0x18010ab17  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ab1c  mov     r8, rax; unsigned __int16 *
0x18010ab1f  mov     rdx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010ab24  mov     rcx, rbx; this
0x18010ab27  call    ?CollectEventViewerEntries@MdmLogCollector@@AEAAJPEAU_iobuf@@PEBG@Z; MdmLogCollector::CollectEventViewerEntries(_iobuf *,ushort const *)
0x18010ab2c  test    eax, eax
0x18010ab2e  jns     short loc_18010AB44
0x18010ab30  mov     r8d, eax
0x18010ab33  lea     rdx, aFailedToCollec_6; "Failed to CollectEventViewerEntries. HR"...
0x18010ab3a  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010ab3f  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ab44  lea     rcx, [rsp+0D8h+var_90]
0x18010ab49  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ab4e  mov     r8, rax; unsigned __int16 *
0x18010ab51  mov     rdx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010ab56  mov     rcx, rbx; this
0x18010ab59  call    ?CollectFileEntries@MdmLogCollector@@AEAAJPEAU_iobuf@@PEBG@Z; MdmLogCollector::CollectFileEntries(_iobuf *,ushort const *)
0x18010ab5e  test    eax, eax
0x18010ab60  jns     short loc_18010AB76
0x18010ab62  mov     r8d, eax
0x18010ab65  lea     rdx, aFailedToCollec_0; "Failed to CollectFileEntries. HResult:0"...
0x18010ab6c  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010ab71  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ab76  lea     rcx, [rsp+0D8h+var_90]
0x18010ab7b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ab80  mov     r8, rax; unsigned __int16 *
0x18010ab83  mov     rdx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010ab88  mov     rcx, rbx; this
0x18010ab8b  call    ?CollectRegistryEntries@MdmLogCollector@@AEAAJPEAU_iobuf@@PEBG@Z; MdmLogCollector::CollectRegistryEntries(_iobuf *,ushort const *)
0x18010ab90  test    eax, eax
0x18010ab92  jns     short loc_18010ABA8
0x18010ab94  mov     r8d, eax
0x18010ab97  lea     rdx, aFailedToCollec_2; "Failed to CollectRegistryEntries. HResu"...
0x18010ab9e  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010aba3  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010aba8  lea     rcx, [rsp+0D8h+var_90]
0x18010abad  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010abb2  mov     r8, rax; unsigned __int16 *
0x18010abb5  mov     rdx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010abba  mov     rcx, rbx; this
0x18010abbd  call    ?CollectTracingSessionEntries@MdmLogCollector@@AEAAJPEAU_iobuf@@PEBG@Z; MdmLogCollector::CollectTracingSessionEntries(_iobuf *,ushort const *)
0x18010abc2  test    eax, eax
0x18010abc4  jns     short loc_18010ABDA
0x18010abc6  mov     r8d, eax
0x18010abc9  lea     rdx, aFailedToCollec_3; "Failed to CollectTracingSessionEntries."...
0x18010abd0  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010abd5  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010abda  mov     rcx, rbx; this
0x18010abdd  call    ?CollectFullVersionInfo@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectFullVersionInfo(void)
0x18010abe2  test    eax, eax
0x18010abe4  jns     short loc_18010ABFA
0x18010abe6  mov     r8d, eax
0x18010abe9  lea     rdx, aFailedToCollec_1; "Failed to CollectFullVersionInfo. HResu"...
0x18010abf0  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010abf5  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010abfa  mov     rcx, rbx; this
0x18010abfd  call    ?CollectAutologonInfo@MdmLogCollector@@AEAAJXZ; MdmLogCollector::CollectAutologonInfo(void)
0x18010ac02  test    eax, eax
0x18010ac04  jns     short loc_18010AC1A
0x18010ac06  mov     r8d, eax
0x18010ac09  lea     rdx, aFailedToCollec_5; "Failed to CollectAutologonInfo. HResult"...
0x18010ac10  mov     rcx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010ac15  call    ?WriteToFile@MdmLogCollector@@CAXPEAU_iobuf@@PEBGZZ; MdmLogCollector::WriteToFile(_iobuf *,ushort const *,...)
0x18010ac1a  lea     rcx, [rsp+0D8h+var_90]
0x18010ac1f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010ac24  mov     r8, rax; unsigned __int16 *
0x18010ac27  mov     rdx, [rsp+0D8h+Stream]; struct _iobuf *
0x18010ac2c  mov     rcx, rbx; this
0x18010ac2f  call    ?GenerateMetadataFile@MdmLogCollector@@AEAAJPEAU_iobuf@@PEBG@Z; MdmLogCollector::GenerateMetadataFile(_iobuf *,ushort const *)
0x18010ac34  nop
0x18010ac35  lea     rcx, [rsp+0D8h+var_70]
0x18010ac3a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ac3f  nop
0x18010ac40  mov     [rsp+0D8h+var_98], 0
0x18010ac45  lea     rcx, [rsp+0D8h+var_A8]
0x18010ac4a  call    _lambda_5b3d6c233d4eae6053aaad5e34b7a9fd___operator__
0x18010ac4f  nop
0x18010ac50  lea     rcx, [rsp+0D8h+var_50]
0x18010ac58  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ac5d  nop
0x18010ac5e  lea     rcx, [rsp+0D8h+var_90]
0x18010ac63  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ac68  xor     eax, eax
0x18010ac6a  jmp     short loc_18010AC70
0x18010ac6c  mov     eax, [rsp+0D8h+var_B0]
0x18010ac70  mov     rcx, [rsp+0D8h+var_10]
0x18010ac78  xor     rcx, rsp; StackCookie
0x18010ac7b  call    __security_check_cookie
0x18010ac80  lea     r11, [rsp+0D8h+var_8]
0x18010ac88  mov     rbx, [r11+20h]
0x18010ac8c  mov     rsi, [r11+28h]
0x18010ac90  mov     rsp, r11
0x18010ac93  pop     rdi
0x18010ac94  retn
```
