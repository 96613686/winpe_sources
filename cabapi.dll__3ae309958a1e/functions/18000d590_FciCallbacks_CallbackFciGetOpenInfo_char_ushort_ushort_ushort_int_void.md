# FciCallbacks::CallbackFciGetOpenInfo(char *,ushort *,ushort *,ushort *,int *,void *)

- ea: `0x18000d590`
- end: `0x18000d7e8`
- name: `?CallbackFciGetOpenInfo@FciCallbacks@@SA_JPEADPEAG11PEAHPEAX@Z`
- size: `600`
- prototype: `INT_PTR __fastcall(LPSTR pszName, USHORT *pdate, USHORT *ptime, USHORT *pattribs, int *err)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callees

- `0x180001540`
- `0x180003648`
- `0x1800082b8`
- `0x18000b34c`
- `0x18000c7a4`
- `0x18000d590`
- `0x1800104d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d75e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d6c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d75e`
- `ntdll!NtClose` at `0x18000d788`
- `ntdll!NtClose` at `0x18000d788`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000d705`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18000d705`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d6b0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000d6b0`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18000d740`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x18000d740`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x18000d754`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x18000d754`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000d717`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x18000d717`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000d72e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000d72e`

## pseudocode

```c
INT_PTR __fastcall FciCallbacks::CallbackFciGetOpenInfo(
        LPSTR pszName,
        USHORT *pdate,
        USHORT *ptime,
        USHORT *pattribs,
        int *err)
{
  __int64 FileW; // rbx
  size_t v9; // r8
  __int128 *v10; // rax
  const WCHAR *v11; // rcx
  _QWORD v13[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v14; // [rsp+60h] [rbp-A0h] BYREF
  __m128i si128; // [rsp+70h] [rbp-90h]
  struct _FILETIME LocalFileTime; // [rsp+80h] [rbp-80h] BYREF
  CHAR MultiByteStr[16]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v18; // [rsp+98h] [rbp-68h]
  LPCWSTR lpFileName[4]; // [rsp+A8h] [rbp-58h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+C8h] [rbp-38h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+D8h] [rbp-28h] BYREF

  v13[2] = -2;
  memset(&FileInformation, 0, sizeof(FileInformation));
  SystemTime = 0;
  LocalFileTime = 0;
  v13[3] = 0;
  *(_OWORD *)MultiByteStr = 0;
  v18 = 0;
  FileW = -1;
  v9 = -1;
  do
    ++v9;
  while ( pszName[v9] );
  std::string::_Construct<1,char const *>(MultiByteStr, pszName, v9);
  v14 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v14) = 0;
  if ( (int)Utils::ConvertMultiByteToUnicode(MultiByteStr) >= 0 )
  {
    v10 = &v14;
    if ( si128.m128i_i64[1] > 7uLL )
      v10 = (__int128 *)v14;
    v13[0] = v10;
    v13[1] = si128.m128i_i64[0];
    GetCanonicalUNCPath(lpFileName, v13);
    v11 = (const WCHAR *)lpFileName;
    if ( lpFileName[3] > (LPCWSTR)7 )
      v11 = lpFileName[0];
    FileW = (__int64)CreateFileW(v11, 0x80000000, 7u, 0, 3u, 0xA000080u, 0);
    if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      *err = GetLastError();
      std::wstring::~wstring((char **)lpFileName);
      std::wstring::~wstring((char **)&v14);
      std::string::~string((char **)MultiByteStr);
      if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
        return -1;
LABEL_17:
      if ( NtClose((HANDLE)FileW) < 0 )
        __fastfail(7u);
      return -1;
    }
    if ( !GetFileInformationByHandle((HANDLE)FileW, &FileInformation)
      || !FileTimeToSystemTime(&FileInformation.ftLastWriteTime, &SystemTime)
      || (*(_DWORD *)&SystemTime.wSecond = 0, !SystemTimeToFileTime(&SystemTime, &FileInformation.ftLastWriteTime))
      || !FileTimeToLocalFileTime(&FileInformation.ftLastWriteTime, &LocalFileTime)
      || !FileTimeToDosDateTime(&LocalFileTime, pdate, ptime) )
    {
      *err = GetLastError();
      std::wstring::~wstring((char **)lpFileName);
      std::wstring::~wstring((char **)&v14);
      std::string::~string((char **)MultiByteStr);
      goto LABEL_17;
    }
    *pattribs = FileInformation.dwFileAttributes & 0x27;
    std::wstring::~wstring((char **)lpFileName);
  }
  std::wstring::~wstring((char **)&v14);
  std::string::~string((char **)MultiByteStr);
  return FileW;
}

```

## disassembly

```asm
0x18000d590  push    rbp
0x18000d592  push    rbx
0x18000d593  push    rsi
0x18000d594  push    rdi
0x18000d595  push    r13
0x18000d597  push    r14
0x18000d599  push    r15
0x18000d59b  lea     rbp, [rsp-20h]
0x18000d5a0  sub     rsp, 120h
0x18000d5a7  mov     [rsp+150h+var_100], 0FFFFFFFFFFFFFFFEh
0x18000d5b0  mov     rax, cs:__security_cookie
0x18000d5b7  xor     rax, rsp
0x18000d5ba  mov     [rbp+50h+var_40], rax
0x18000d5be  mov     rsi, r9
0x18000d5c1  mov     r15, r8
0x18000d5c4  mov     r14, rdx
0x18000d5c7  mov     rdi, [rbp+50h+err]
0x18000d5ce  xorps   xmm0, xmm0
0x18000d5d1  xor     eax, eax
0x18000d5d3  movups  xmmword ptr [rbp+50h+FileInformation.dwFileAttributes], xmm0
0x18000d5d7  movups  xmmword ptr [rbp+50h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18000d5db  movups  xmmword ptr [rbp+50h+FileInformation.nFileSizeHigh], xmm0
0x18000d5df  mov     [rbp+50h+FileInformation.nFileIndexLow], eax
0x18000d5e2  movups  xmmword ptr [rbp+50h+SystemTime.wYear], xmm0
0x18000d5e6  mov     qword ptr [rbp+50h+LocalFileTime.dwLowDateTime], rax
0x18000d5ea  mov     [rsp+150h+var_F8], rax
0x18000d5ef  movups  xmmword ptr [rbp+50h+MultiByteStr], xmm0
0x18000d5f3  xorps   xmm1, xmm1
0x18000d5f6  movdqu  [rbp+50h+var_B8], xmm1
0x18000d5fb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000d5ff  mov     r8, rbx
0x18000d602  inc     r8
0x18000d605  cmp     byte ptr [rcx+r8], 0
0x18000d60a  jnz     short loc_18000D602
0x18000d60c  mov     rdx, rcx
0x18000d60f  lea     rcx, [rbp+50h+MultiByteStr]
0x18000d613  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000d618  nop
0x18000d619  xorps   xmm0, xmm0
0x18000d61c  movups  [rsp+150h+var_F0], xmm0
0x18000d621  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000d629  movdqu  [rsp+150h+var_E0], xmm1
0x18000d62f  xor     eax, eax
0x18000d631  mov     word ptr [rsp+150h+var_F0], ax
0x18000d636  lea     rdx, [rsp+150h+var_F0]
0x18000d63b  lea     rcx, [rbp+50h+MultiByteStr]; lpMultiByteStr
0x18000d63f  call    ?ConvertMultiByteToUnicode@Utils@@SAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z; Utils::ConvertMultiByteToUnicode(std::string const &,std::wstring *)
0x18000d644  test    eax, eax
0x18000d646  js      loc_18000D7B2
0x18000d64c  mov     rcx, qword ptr [rsp+150h+var_E0]
0x18000d651  lea     rax, [rsp+150h+var_F0]
0x18000d656  mov     r13d, 7
0x18000d65c  cmp     qword ptr [rsp+150h+var_E0+8], r13
0x18000d661  cmova   rax, qword ptr [rsp+150h+var_F0]
0x18000d667  mov     [rsp+150h+var_110], rax
0x18000d66c  mov     [rsp+150h+var_108], rcx
0x18000d671  lea     rdx, [rsp+150h+var_110]
0x18000d676  lea     rcx, [rbp+50h+lpFileName]
0x18000d67a  call    ?GetCanonicalUNCPath@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_zstring_view@_W@wil@@@Z; GetCanonicalUNCPath(wil::basic_zstring_view<wchar_t> const &)
0x18000d67f  lea     rcx, [rbp+50h+lpFileName]
0x18000d683  cmp     [rbp+50h+var_90], r13
0x18000d687  cmova   rcx, [rbp+50h+lpFileName]; lpFileName
0x18000d68c  mov     [rsp+150h+hTemplateFile], 0; hTemplateFile
0x18000d695  mov     [rsp+150h+dwFlagsAndAttributes], 0A000080h; dwFlagsAndAttributes
0x18000d69d  mov     [rsp+150h+dwCreationDisposition], 3; dwCreationDisposition
0x18000d6a5  xor     r9d, r9d; lpSecurityAttributes
0x18000d6a8  mov     r8d, r13d; dwShareMode
0x18000d6ab  mov     edx, 80000000h; dwDesiredAccess
0x18000d6b0  call    cs:__imp_CreateFileW
0x18000d6b6  mov     rbx, rax
0x18000d6b9  inc     rax
0x18000d6bc  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000d6c2  jnz     short loc_18000D6FE
0x18000d6c4  call    cs:__imp_GetLastError
0x18000d6ca  mov     [rdi], eax
0x18000d6cc  lea     rcx, [rbp+50h+lpFileName]
0x18000d6d0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d6d5  nop
0x18000d6d6  lea     rcx, [rsp+150h+var_F0]
0x18000d6db  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d6e0  nop
0x18000d6e1  lea     rcx, [rbp+50h+MultiByteStr]
0x18000d6e5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000d6ea  nop
0x18000d6eb  lea     rax, [rbx-1]
0x18000d6ef  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000d6f3  ja      loc_18000D797
0x18000d6f9  jmp     loc_18000D785
0x18000d6fe  lea     rdx, [rbp+50h+FileInformation]; lpFileInformation
0x18000d702  mov     rcx, rbx; hFile
0x18000d705  call    cs:__imp_GetFileInformationByHandle
0x18000d70b  test    eax, eax
0x18000d70d  jz      short loc_18000D75E
0x18000d70f  lea     rdx, [rbp+50h+SystemTime]; lpSystemTime
0x18000d713  lea     rcx, [rbp+50h+FileInformation.ftLastWriteTime]; lpFileTime
0x18000d717  call    cs:__imp_FileTimeToSystemTime
0x18000d71d  test    eax, eax
0x18000d71f  jz      short loc_18000D75E
0x18000d721  xor     eax, eax
0x18000d723  mov     dword ptr [rbp+50h+SystemTime.wSecond], eax
0x18000d726  lea     rdx, [rbp+50h+FileInformation.ftLastWriteTime]; lpFileTime
0x18000d72a  lea     rcx, [rbp+50h+SystemTime]; lpSystemTime
0x18000d72e  call    cs:__imp_SystemTimeToFileTime
0x18000d734  test    eax, eax
0x18000d736  jz      short loc_18000D75E
0x18000d738  lea     rdx, [rbp+50h+LocalFileTime]; lpLocalFileTime
0x18000d73c  lea     rcx, [rbp+50h+FileInformation.ftLastWriteTime]; lpFileTime
0x18000d740  call    cs:__imp_FileTimeToLocalFileTime
0x18000d746  test    eax, eax
0x18000d748  jz      short loc_18000D75E
0x18000d74a  mov     r8, r15; lpFatTime
0x18000d74d  mov     rdx, r14; lpFatDate
0x18000d750  lea     rcx, [rbp+50h+LocalFileTime]; lpFileTime
0x18000d754  call    cs:__imp_FileTimeToDosDateTime
0x18000d75a  test    eax, eax
0x18000d75c  jnz     short loc_18000D79D
0x18000d75e  call    cs:__imp_GetLastError
0x18000d764  mov     [rdi], eax
0x18000d766  lea     rcx, [rbp+50h+lpFileName]
0x18000d76a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d76f  nop
0x18000d770  lea     rcx, [rsp+150h+var_F0]
0x18000d775  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d77a  nop
0x18000d77b  lea     rcx, [rbp+50h+MultiByteStr]
0x18000d77f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000d784  nop
0x18000d785  mov     rcx, rbx; Handle
0x18000d788  call    cs:__imp_NtClose
0x18000d78e  test    eax, eax
0x18000d790  jns     short loc_18000D797
0x18000d792  mov     rcx, r13
0x18000d795  int     29h; Win8: RtlFailFast(ecx)
0x18000d797  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d79b  jmp     short loc_18000D7CA
0x18000d79d  movzx   eax, word ptr [rbp+50h+FileInformation.dwFileAttributes]
0x18000d7a1  and     ax, 27h
0x18000d7a5  mov     [rsi], ax
0x18000d7a8  lea     rcx, [rbp+50h+lpFileName]
0x18000d7ac  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d7b1  nop
0x18000d7b2  lea     rcx, [rsp+150h+var_F0]
0x18000d7b7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d7bc  nop
0x18000d7bd  lea     rcx, [rbp+50h+MultiByteStr]
0x18000d7c1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18000d7c6  nop
0x18000d7c7  mov     rax, rbx
0x18000d7ca  mov     rcx, [rbp+50h+var_40]
0x18000d7ce  xor     rcx, rsp; StackCookie
0x18000d7d1  call    __security_check_cookie
0x18000d7d6  add     rsp, 120h
0x18000d7dd  pop     r15
0x18000d7df  pop     r14
0x18000d7e1  pop     r13
0x18000d7e3  pop     rdi
0x18000d7e4  pop     rsi
0x18000d7e5  pop     rbx
0x18000d7e6  pop     rbp
0x18000d7e7  retn
```
