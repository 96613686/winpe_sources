# shared::BasicFile::MoveFiles(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180144af0`
- end: `0x180144e70`
- name: `?MoveFiles@BasicFile@shared@@UEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@00@Z`
- size: `896`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops`

## callees

- `0x18000b724`
- `0x18000d02c`
- `0x18000d098`
- `0x180030190`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800a11bc`
- `0x18011d5d0`
- `0x18011d808`
- `0x180143248`
- `0x180144af0`
- `0x1801f6fb0`
- `0x1801f7974`
- `0x1801fcb36`
- `0x18023a62c`
- `0x18023a664`
- `0x18023aa04`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180144db0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180144db0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144d85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180144d85`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180144cc0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180144cc0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180144c26`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180144c26`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180144cb3`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180144cb3`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180144d5f`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180144d5f`

## string_xrefs

- `0x180144dd9`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall shared::BasicFile::MoveFiles(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  const WCHAR *v11; // rcx
  HANDLE FirstFileW; // rbx
  int v13; // edx
  int v14; // edx
  __int64 i; // rbx
  __int64 v16; // r14
  __int64 v17; // rax
  __int64 v18; // rax
  const WCHAR *v19; // rdx
  const WCHAR *v20; // rcx
  signed int LastError; // eax
  unsigned int v22; // ebx
  int v23; // ecx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rax
  __int64 result; // rax
  __int128 v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h]
  unsigned int v31; // [rsp+48h] [rbp-B8h] BYREF
  __int64 CurrentThreadId; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+58h] [rbp-A8h] BYREF
  const char *v34; // [rsp+90h] [rbp-70h] BYREF
  int v35[6]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v36[32]; // [rsp+B0h] [rbp-50h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+D0h] [rbp-30h] BYREF
  LPCWSTR lpNewFileName[4]; // [rsp+F0h] [rbp-10h] BYREF
  LPCWSTR lpExistingFileName[4]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v40[32]; // [rsp+130h] [rbp+30h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+150h] [rbp+50h] BYREF

  if ( !*(_QWORD *)(a2 + 16) )
  {
    v34 = ".\\basicfile.cpp";
    v35[0] = 202;
    v7 = cdp::MakeException<std::invalid_argument,>(v36, a2, "Source folder can't be empty");
    cdp::CdpThrow<std::invalid_argument>(&v34, v7);
  }
  if ( !*(_QWORD *)(a3 + 16) )
  {
    v34 = ".\\basicfile.cpp";
    v35[0] = 203;
    v8 = cdp::MakeException<std::invalid_argument,>(v36, a2, "Target folder can't be empty");
    cdp::CdpThrow<std::invalid_argument>(&v34, v8);
  }
  if ( !*(_QWORD *)(a4 + 16) )
  {
    v34 = ".\\basicfile.cpp";
    v35[0] = 204;
    v9 = cdp::MakeException<std::invalid_argument,>(v36, a2, "Name pattern can't be empty");
    cdp::CdpThrow<std::invalid_argument>(&v34, v9);
  }
  v29 = 0;
  v30 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 72LL))(a1, v36, a2);
  cdp::ToWstring(lpFileName, v10);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v36);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v11 = (const WCHAR *)lpFileName;
  if ( lpFileName[3] > (LPCWSTR)7 )
    v11 = lpFileName[0];
  FirstFileW = FindFirstFileW(v11, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    do
    {
      v13 = FindFileData.cFileName[0] - 46;
      if ( FindFileData.cFileName[0] == 46 )
        v13 = FindFileData.cFileName[1];
      if ( v13 )
      {
        v14 = FindFileData.cFileName[0] - 46;
        if ( FindFileData.cFileName[0] == 46 )
        {
          v14 = FindFileData.cFileName[1] - 46;
          if ( FindFileData.cFileName[1] == 46 )
            v14 = FindFileData.cFileName[2];
        }
        if ( v14 )
        {
          if ( *((_QWORD *)&v29 + 1) == v30 )
          {
            std::vector<std::wstring>::_Emplace_reallocate<unsigned short (&)[260]>(
              &v29,
              *((_QWORD *)&v29 + 1),
              FindFileData.cFileName);
          }
          else
          {
            std::wstring::wstring(*((_QWORD *)&v29 + 1), FindFileData.cFileName);
            *((_QWORD *)&v29 + 1) += 32LL;
          }
        }
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    FindClose(FirstFileW);
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 88LL))(a1, a3);
    v16 = *((_QWORD *)&v29 + 1);
    for ( i = v29; i != v16; i += 32 )
    {
      v17 = cdp::ToWstring(&v34, a2);
      shared::BasicFile::ConcatPath(a1, lpExistingFileName, v17, i);
      std::wstring::_Tidy_deallocate(&v34);
      v18 = cdp::ToWstring(v40, a3);
      shared::BasicFile::ConcatPath(a1, lpNewFileName, v18, i);
      std::wstring::_Tidy_deallocate(v40);
      v19 = (const WCHAR *)lpNewFileName;
      if ( lpNewFileName[3] > (LPCWSTR)7 )
        v19 = lpNewFileName[0];
      v20 = (const WCHAR *)lpExistingFileName;
      if ( lpExistingFileName[3] > (LPCWSTR)7 )
        v20 = lpExistingFileName[0];
      if ( !MoveFileExW(v20, v19, 2u) )
      {
        LastError = GetLastError();
        v22 = LastError;
        if ( LastError > 0 )
          v22 = (unsigned __int16)LastError | 0x80070000;
        v34 = ".\\basicfile.cpp";
        v35[0] = 235;
        v31 = v22;
        CurrentThreadId = GetCurrentThreadId();
        Log<long &,char const * &,int &,unsigned __int64>(
          v23,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v31,
          (unsigned int)&v34,
          (__int64)v35,
          (__int64)&CurrentThreadId);
        v24 = cdp::ExceptionStackFromSourceLocationInfo(v36, &v34);
        v27 = cdp::ErrorCodeToString(v22, v25, v26, v24);
        ConnectedDevices::Exception::Exception(pExceptionObject, v22, v27);
        throw (ConnectedDevices::Exception *)pExceptionObject;
      }
      std::wstring::_Tidy_deallocate(lpNewFileName);
      std::wstring::_Tidy_deallocate(lpExistingFileName);
    }
  }
  result = std::wstring::_Tidy_deallocate(lpFileName);
  if ( (_QWORD)v29 )
  {
    std::_Destroy_range<std::allocator<std::wstring>>(v29, *((_QWORD *)&v29 + 1));
    return std::_Deallocate<16>(v29, (v30 - v29) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  return result;
}

```

## disassembly

```asm
0x180144af0  push    rbp
0x180144af2  push    rbx
0x180144af3  push    rsi
0x180144af4  push    rdi
0x180144af5  push    r14
0x180144af7  push    r15
0x180144af9  lea     rbp, [rsp-2B8h]
0x180144b01  sub     rsp, 3B8h
0x180144b08  mov     rax, cs:__security_cookie
0x180144b0f  xor     rax, rsp
0x180144b12  mov     [rbp+2E0h+var_40], rax
0x180144b19  mov     rsi, r8
0x180144b1c  mov     r15, rdx
0x180144b1f  mov     rdi, rcx
0x180144b22  cmp     qword ptr [rdx+10h], 0
0x180144b27  jnz     short loc_180144B59
0x180144b29  lea     rax, aBasicfileCpp; ".\\basicfile.cpp"
0x180144b30  mov     [rbp+2E0h+var_350], rax
0x180144b34  mov     [rbp+2E0h+var_348], 0CAh
0x180144b3b  lea     r8, aSourceFolderCa; "Source folder can't be empty"
0x180144b42  lea     rcx, [rbp+2E0h+var_330]
0x180144b46  call    ??$MakeException@Vinvalid_argument@std@@$$V@cdp@@YA?AVinvalid_argument@std@@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<std::invalid_argument,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180144b4b  nop
0x180144b4c  mov     rdx, rax
0x180144b4f  lea     rcx, [rbp+2E0h+var_350]
0x180144b53  call    ??$CdpThrow@Vinvalid_argument@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVinvalid_argument@std@@@Z; cdp::CdpThrow<std::invalid_argument>(cdp::CDPSourceLocationInfo const &,std::invalid_argument &&)
0x180144b59  cmp     qword ptr [r8+10h], 0
0x180144b5e  jnz     short loc_180144B90
0x180144b60  lea     rax, aBasicfileCpp; ".\\basicfile.cpp"
0x180144b67  mov     [rbp+2E0h+var_350], rax
0x180144b6b  mov     [rbp+2E0h+var_348], 0CBh
0x180144b72  lea     r8, aTargetFolderCa; "Target folder can't be empty"
0x180144b79  lea     rcx, [rbp+2E0h+var_330]
0x180144b7d  call    ??$MakeException@Vinvalid_argument@std@@$$V@cdp@@YA?AVinvalid_argument@std@@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<std::invalid_argument,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180144b82  nop
0x180144b83  mov     rdx, rax
0x180144b86  lea     rcx, [rbp+2E0h+var_350]
0x180144b8a  call    ??$CdpThrow@Vinvalid_argument@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVinvalid_argument@std@@@Z; cdp::CdpThrow<std::invalid_argument>(cdp::CDPSourceLocationInfo const &,std::invalid_argument &&)
0x180144b90  cmp     qword ptr [r9+10h], 0
0x180144b95  jnz     short loc_180144BC7
0x180144b97  lea     rax, aBasicfileCpp; ".\\basicfile.cpp"
0x180144b9e  mov     [rbp+2E0h+var_350], rax
0x180144ba2  mov     [rbp+2E0h+var_348], 0CCh
0x180144ba9  lea     r8, aNamePatternCan; "Name pattern can't be empty"
0x180144bb0  lea     rcx, [rbp+2E0h+var_330]
0x180144bb4  call    ??$MakeException@Vinvalid_argument@std@@$$V@cdp@@YA?AVinvalid_argument@std@@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<std::invalid_argument,>(cdp::CDPSourceLocationInfo const &,char const *)
0x180144bb9  nop
0x180144bba  mov     rdx, rax
0x180144bbd  lea     rcx, [rbp+2E0h+var_350]
0x180144bc1  call    ??$CdpThrow@Vinvalid_argument@std@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVinvalid_argument@std@@@Z; cdp::CdpThrow<std::invalid_argument>(cdp::CDPSourceLocationInfo const &,std::invalid_argument &&)
0x180144bc7  xorps   xmm0, xmm0
0x180144bca  movdqu  [rsp+3E0h+var_3B0], xmm0
0x180144bd0  mov     [rsp+3E0h+var_3A0], 0
0x180144bd9  mov     rax, [rcx]
0x180144bdc  mov     r8, r15
0x180144bdf  lea     rdx, [rbp+2E0h+var_330]
0x180144be3  mov     rax, [rax+48h]
0x180144be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144bec  nop
0x180144bed  mov     rdx, rax
0x180144bf0  lea     rcx, [rbp+2E0h+lpFileName]
0x180144bf4  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x180144bf9  nop
0x180144bfa  lea     rcx, [rbp+2E0h+var_330]; void *
0x180144bfe  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180144c03  xor     edx, edx; Val
0x180144c05  mov     r8d, 250h; Size
0x180144c0b  lea     rcx, [rbp+2E0h+FindFileData]; void *
0x180144c0f  call    memset_0
0x180144c14  lea     rcx, [rbp+2E0h+lpFileName]
0x180144c18  cmp     [rbp+2E0h+var_2F8], 7
0x180144c1d  cmova   rcx, [rbp+2E0h+lpFileName]; lpFileName
0x180144c22  lea     rdx, [rbp+2E0h+FindFileData]; lpFindFileData
0x180144c26  call    cs:__imp_FindFirstFileW
0x180144c2c  mov     rbx, rax
0x180144c2f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180144c33  jz      loc_180144E1D
0x180144c39  mov     r14d, 2Eh ; '.'
0x180144c3f  movzx   edx, [rbp+2E0h+FindFileData.cFileName]
0x180144c43  sub     edx, r14d
0x180144c46  jnz     short loc_180144C53
0x180144c48  movzx   edx, [rbp+2E0h+FindFileData.cFileName+2]
0x180144c4c  xor     eax, eax
0x180144c4e  movzx   ecx, ax
0x180144c51  sub     edx, ecx
0x180144c53  test    edx, edx
0x180144c55  jz      short loc_180144CAC
0x180144c57  movzx   edx, [rbp+2E0h+FindFileData.cFileName]
0x180144c5b  sub     edx, r14d
0x180144c5e  jnz     short loc_180144C77
0x180144c60  movzx   edx, [rbp+2E0h+FindFileData.cFileName+2]
0x180144c64  sub     edx, r14d
0x180144c67  jnz     short loc_180144C77
0x180144c69  movzx   edx, [rbp+2E0h+FindFileData.cFileName+4]
0x180144c70  xor     eax, eax
0x180144c72  movzx   ecx, ax
0x180144c75  sub     edx, ecx
0x180144c77  test    edx, edx
0x180144c79  jz      short loc_180144CAC
0x180144c7b  mov     rax, qword ptr [rsp+3E0h+var_3B0+8]
0x180144c80  cmp     rax, [rsp+3E0h+var_3A0]
0x180144c85  jz      short loc_180144C9B
0x180144c87  lea     rdx, [rbp+2E0h+FindFileData.cFileName]
0x180144c8b  mov     rcx, rax
0x180144c8e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180144c93  add     qword ptr [rsp+3E0h+var_3B0+8], 20h ; ' '
0x180144c99  jmp     short loc_180144CAC
0x180144c9b  lea     r8, [rbp+2E0h+FindFileData.cFileName]
0x180144c9f  mov     rdx, rax
0x180144ca2  lea     rcx, [rsp+3E0h+var_3B0]
0x180144ca7  call    ??$_Emplace_reallocate@AEAY0BAE@G@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEAY0BAE@G@Z; std::vector<std::wstring>::_Emplace_reallocate<ushort (&)[260]>(std::wstring * const,ushort (&)[260])
0x180144cac  lea     rdx, [rbp+2E0h+FindFileData]; lpFindFileData
0x180144cb0  mov     rcx, rbx; hFindFile
0x180144cb3  call    cs:__imp_FindNextFileW
0x180144cb9  test    eax, eax
0x180144cbb  jnz     short loc_180144C3F
0x180144cbd  mov     rcx, rbx; hFindFile
0x180144cc0  call    cs:__imp_FindClose
0x180144cc6  mov     rax, [rdi]
0x180144cc9  mov     rdx, rsi
0x180144ccc  mov     rcx, rdi
0x180144ccf  mov     rax, [rax+58h]
0x180144cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144cd8  mov     rbx, qword ptr [rsp+3E0h+var_3B0]
0x180144cdd  mov     r14, qword ptr [rsp+3E0h+var_3B0+8]
0x180144ce2  cmp     rbx, r14
0x180144ce5  jz      loc_180144E1D
0x180144ceb  mov     rdx, r15
0x180144cee  lea     rcx, [rbp+2E0h+var_350]
0x180144cf2  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x180144cf7  nop
0x180144cf8  mov     r9, rbx
0x180144cfb  mov     r8, rax
0x180144cfe  lea     rdx, [rbp+2E0h+lpExistingFileName]
0x180144d02  mov     rcx, rdi
0x180144d05  call    ?ConcatPath@BasicFile@shared@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@0@Z; shared::BasicFile::ConcatPath(std::wstring const &,std::wstring const &)
0x180144d0a  nop
0x180144d0b  lea     rcx, [rbp+2E0h+var_350]
0x180144d0f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180144d14  mov     rdx, rsi
0x180144d17  lea     rcx, [rbp+2E0h+var_2B0]
0x180144d1b  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x180144d20  nop
0x180144d21  mov     r9, rbx
0x180144d24  mov     r8, rax
0x180144d27  lea     rdx, [rbp+2E0h+lpNewFileName]
0x180144d2b  mov     rcx, rdi
0x180144d2e  call    ?ConcatPath@BasicFile@shared@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@0@Z; shared::BasicFile::ConcatPath(std::wstring const &,std::wstring const &)
0x180144d33  nop
0x180144d34  lea     rcx, [rbp+2E0h+var_2B0]
0x180144d38  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180144d3d  lea     rdx, [rbp+2E0h+lpNewFileName]
0x180144d41  cmp     [rbp+2E0h+var_2D8], 7
0x180144d46  cmova   rdx, [rbp+2E0h+lpNewFileName]; lpNewFileName
0x180144d4b  lea     rcx, [rbp+2E0h+lpExistingFileName]
0x180144d4f  cmp     [rbp+2E0h+var_2B8], 7
0x180144d54  cmova   rcx, [rbp+2E0h+lpExistingFileName]; lpExistingFileName
0x180144d59  mov     r8d, 2; dwFlags
0x180144d5f  call    cs:__imp_MoveFileExW
0x180144d65  test    eax, eax
0x180144d67  jz      short loc_180144D85
0x180144d69  lea     rcx, [rbp+2E0h+lpNewFileName]
0x180144d6d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180144d72  nop
0x180144d73  lea     rcx, [rbp+2E0h+lpExistingFileName]
0x180144d77  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180144d7c  add     rbx, 20h ; ' '
0x180144d80  jmp     loc_180144CE2
0x180144d85  call    cs:__imp_GetLastError
0x180144d8b  mov     ebx, eax
0x180144d8d  test    eax, eax
0x180144d8f  jle     short loc_180144D9A
0x180144d91  movzx   ebx, ax
0x180144d94  or      ebx, 80070000h
0x180144d9a  lea     rax, aBasicfileCpp; ".\\basicfile.cpp"
0x180144da1  mov     [rbp+2E0h+var_350], rax
0x180144da5  mov     [rbp+2E0h+var_348], 0EBh
0x180144dac  mov     [rsp+3E0h+var_398], ebx
0x180144db0  call    cs:__imp_GetCurrentThreadId
0x180144db6  mov     eax, eax
0x180144db8  mov     [rsp+3E0h+var_390], rax
0x180144dbd  lea     rax, [rsp+3E0h+var_390]
0x180144dc2  mov     [rsp+3E0h+var_3B8], rax
0x180144dc7  lea     rax, [rbp+2E0h+var_348]
0x180144dcb  mov     [rsp+3E0h+var_3C0], rax
0x180144dd0  lea     r9, [rbp+2E0h+var_350]
0x180144dd4  lea     r8, [rsp+3E0h+var_398]
0x180144dd9  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180144de0  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x180144de5  lea     rdx, [rbp+2E0h+var_350]
0x180144de9  lea     rcx, [rbp+2E0h+var_330]
0x180144ded  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x180144df2  mov     r9, rax
0x180144df5  mov     ecx, ebx
0x180144df7  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x180144dfc  mov     r8, rax
0x180144dff  mov     edx, ebx
0x180144e01  lea     rcx, [rsp+3E0h+pExceptionObject]
0x180144e06  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x180144e0b  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x180144e12  lea     rcx, [rsp+3E0h+pExceptionObject]; pExceptionObject
0x180144e17  call    _CxxThrowException_0
0x180144e1d  lea     rcx, [rbp+2E0h+lpFileName]
0x180144e21  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180144e26  nop
0x180144e27  mov     rcx, qword ptr [rsp+3E0h+var_3B0]
0x180144e2c  test    rcx, rcx
0x180144e2f  jz      short loc_180144E51
0x180144e31  mov     rdx, qword ptr [rsp+3E0h+var_3B0+8]
0x180144e36  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x180144e3b  mov     rcx, qword ptr [rsp+3E0h+var_3B0]
0x180144e40  mov     rdx, [rsp+3E0h+var_3A0]
0x180144e45  sub     rdx, rcx
0x180144e48  and     rdx, 0FFFFFFFFFFFFFFE0h
0x180144e4c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180144e51  mov     rcx, [rbp+2E0h+var_40]
0x180144e58  xor     rcx, rsp; StackCookie
0x180144e5b  call    __security_check_cookie
0x180144e60  add     rsp, 3B8h
0x180144e67  pop     r15
0x180144e69  pop     r14
0x180144e6b  pop     rdi
0x180144e6c  pop     rsi
0x180144e6d  pop     rbx
0x180144e6e  pop     rbp
0x180144e6f  retn
```
