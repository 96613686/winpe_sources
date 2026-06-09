# WriteToLogFile(ushort const *,ushort const *,ushort const *)

- ea: `0x180033a5c`
- end: `0x180033f27`
- name: `?WriteToLogFile@@YAJPEBG00@Z`
- size: `1227`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011690`
- `0x18002f734`
- `0x18002feec`
- `0x180032ea8`

## callees

- `0x1800039f0`
- `0x1800043a8`
- `0x18000ba94`
- `0x18000bab4`
- `0x18000c63c`
- `0x180010bd8`
- `0x180010f74`
- `0x180012314`
- `0x180025ae0`
- `0x180031a14`
- `0x180032d0c`
- `0x180033a5c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033d5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033ed4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033d5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033e6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033ed4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180033adc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180033adc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033bc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033c47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033d6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033d84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033e7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033e8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ee5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ef6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033bc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033c47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033d6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033d84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033e7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033e8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ee5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180033ef6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180033de2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180033de2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033c74`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180033c74`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180033bce`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180033bce`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180033db9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180033db9`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180033aed`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToTzSpecificLocalTime` at `0x180033aed`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180033c11`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180033c11`

## string_xrefs

- `0x180033e2a`: `WriteToLogFile: failed to write uri data to the file`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WriteToLogFile(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v5; // rdx
  unsigned int LastError; // edi
  int v8; // eax
  int StoragePath; // ebx
  __int64 v10; // rdx
  DWORD FileAttributesW; // eax
  HRESULT v12; // eax
  char *FileW; // rbx
  __int64 v14; // r8
  LPCVOID *v15; // rax
  __int64 v16; // rdx
  unsigned __int64 v17; // rcx
  bool v18; // cc
  DWORD v19; // edi
  LPCVOID *v20; // rdx
  const char *v21; // r9
  __int64 v22; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  PWSTR ppszPathOut; // [rsp+58h] [rbp-A8h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp-A0h] BYREF
  char *v30; // [rsp+68h] [rbp-98h]
  struct _SYSTEMTIME LocalTime; // [rsp+70h] [rbp-90h] BYREF
  LPCVOID lpBuffer[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v33; // [rsp+90h] [rbp-70h]
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v35[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  if ( !a1 )
  {
    v5 = 631;
LABEL_3:
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    return LastError;
  }
  if ( !a3 )
  {
    v5 = 633;
    goto LABEL_3;
  }
  SystemTime = 0;
  LocalTime = 0;
  GetSystemTime(&SystemTime);
  SystemTimeToTzSpecificLocalTime(0, &SystemTime, &LocalTime);
  memset_0(v35, 0, 0x208u);
  dwCreationDispositiona = LocalTime.wMonth;
  v8 = StringCchPrintfW(v35, 0x104u, L"%d-%02d-%02d %02d:%02d:%02d.%03d   ", LocalTime.wYear);
  StoragePath = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x289,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)v8,
      dwCreationDispositiona);
    return (unsigned int)StoragePath;
  }
  hMem = 0;
  StoragePath = GetStoragePath(a1, (PWSTR *)&hMem);
  if ( StoragePath < 0 )
  {
    v10 = 652;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)StoragePath,
      dwCreationDispositiona);
LABEL_13:
    if ( hMem )
      LocalFree(hMem);
    return (unsigned int)StoragePath;
  }
  FileAttributesW = GetFileAttributesW((LPCWSTR)hMem);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    StoragePath = CreateStoragePath(a1);
    if ( StoragePath < 0 )
    {
      v10 = 655;
      goto LABEL_12;
    }
  }
  ppszPathOut = 0;
  v12 = PathAllocCombine((PCWSTR)hMem, L"logs.txt", 0, &ppszPathOut);
  StoragePath = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x293,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)v12,
      dwCreationDispositiona);
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    goto LABEL_13;
  }
  FileW = (char *)CreateFileW(ppszPathOut, 4u, 1u, 0, 4u, 0x80u, 0);
  v30 = FileW;
  *(_OWORD *)lpBuffer = 0;
  v33 = 0;
  v14 = -1;
  do
    ++v14;
  while ( v35[v14] );
  std::wstring::_Construct<1,unsigned short const *>(lpBuffer, v35, v14);
  std::wstring::append(lpBuffer, a3);
  std::wstring::append(lpBuffer, (void *)L"\n");
  if ( *((_QWORD *)&v33 + 1) <= 7u )
  {
    v15 = lpBuffer;
  }
  else
  {
    v15 = (LPCVOID *)lpBuffer[0];
    if ( !lpBuffer[0] )
    {
      LastError = -2147024809;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A4,
        (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
        (const char *)LastError,
        dwCreationDispositionb);
LABEL_33:
      std::wstring::~wstring(lpBuffer);
      v18 = (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
LABEL_34:
      if ( v18 )
        CloseHandle(FileW);
      if ( ppszPathOut )
        LocalFree(ppszPathOut);
      if ( hMem )
        LocalFree(hMem);
      return LastError;
    }
  }
  v16 = 3145728;
  do
  {
    if ( !*(_WORD *)v15 )
      break;
    v15 = (LPCVOID *)((char *)v15 + 2);
    --v16;
  }
  while ( v16 );
  LastError = v16 == 0 ? 0x80070057 : 0;
  v17 = (3145728 - v16) & -(__int64)(v16 != 0);
  if ( !v16 )
    goto LABEL_32;
  if ( !v17 )
    goto LABEL_49;
  v19 = 2 * v17;
  if ( is_mul_ok(v17, 2u) )
  {
    if ( 2 * v17 <= 0xFFFFFFFF )
    {
      SetFilePointer(FileW, (v17 * (unsigned __int128)2uLL) >> 64, 0, 2u);
      NumberOfBytesWritten = 0;
      v20 = lpBuffer;
      if ( *((_QWORD *)&v33 + 1) > 7u )
        v20 = (LPCVOID *)lpBuffer[0];
      if ( !WriteFile(FileW, v20, v19, &NumberOfBytesWritten, 0) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x2B2,
                      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
                      v21);
        std::wstring::~wstring(lpBuffer);
        v18 = (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL;
        goto LABEL_34;
      }
      if ( NumberOfBytesWritten != v19 )
      {
        LastError = -2147467259;
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x2B5,
          (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
          (const char *)0x80004005LL,
          (int)"WriteToLogFile: failed to write uri data to the file",
          dwFlagsAndAttributes);
        goto LABEL_33;
      }
LABEL_49:
      std::wstring::~wstring(lpBuffer);
      if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(FileW);
      if ( ppszPathOut )
        LocalFree(ppszPathOut);
      if ( hMem )
        LocalFree(hMem);
      return 0;
    }
    v22 = 683;
  }
  else
  {
    v22 = 680;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v22,
    (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
    (const char *)0x80070216LL,
    dwCreationDispositionb);
  std::wstring::~wstring(lpBuffer);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  if ( hMem )
    LocalFree(hMem);
  return 2147942934LL;
}

```

## disassembly

```asm
0x180033a5c  mov     [rsp-8+arg_8], rbx
0x180033a61  push    rbp
0x180033a62  push    rsi
0x180033a63  push    rdi
0x180033a64  push    r14
0x180033a66  push    r15
0x180033a68  lea     rbp, [rsp-1D0h]
0x180033a70  sub     rsp, 2D0h
0x180033a77  mov     rax, cs:__security_cookie
0x180033a7e  xor     rax, rsp
0x180033a81  mov     [rbp+1F0h+var_30], rax
0x180033a88  mov     rsi, r8
0x180033a8b  mov     rdi, rcx
0x180033a8e  xor     r14d, r14d
0x180033a91  test    rcx, rcx
0x180033a94  jnz     short loc_180033ABD
0x180033a96  mov     edx, 277h; void *
0x180033a9b  mov     edi, 80070057h
0x180033aa0  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033aa7  mov     r9d, edi; char *
0x180033aaa  mov     rcx, [rbp+1F8h]; this
0x180033ab1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033ab6  mov     eax, edi
0x180033ab8  jmp     loc_180033F01
0x180033abd  test    rsi, rsi
0x180033ac0  jnz     short loc_180033AC9
0x180033ac2  mov     edx, 279h
0x180033ac7  jmp     short loc_180033A9B
0x180033ac9  xorps   xmm0, xmm0
0x180033acc  movups  xmmword ptr [rbp+1F0h+SystemTime.wYear], xmm0
0x180033ad0  xorps   xmm1, xmm1
0x180033ad3  movups  xmmword ptr [rsp+2F0h+LocalTime.wYear], xmm1
0x180033ad8  lea     rcx, [rbp+1F0h+SystemTime]; lpSystemTime
0x180033adc  call    cs:__imp_GetSystemTime
0x180033ae2  lea     r8, [rsp+2F0h+LocalTime]; lpLocalTime
0x180033ae7  lea     rdx, [rbp+1F0h+SystemTime]; lpUniversalTime
0x180033aeb  xor     ecx, ecx; lpTimeZoneInformation
0x180033aed  call    cs:__imp_SystemTimeToTzSpecificLocalTime
0x180033af3  xor     edx, edx; Val
0x180033af5  mov     r8d, 208h; Size
0x180033afb  lea     rcx, [rbp+1F0h+var_240]; void *
0x180033aff  call    memset_0
0x180033b04  movzx   eax, [rsp+2F0h+LocalTime.wMilliseconds]
0x180033b09  movzx   ecx, [rsp+2F0h+LocalTime.wSecond]
0x180033b0e  movzx   edx, [rsp+2F0h+LocalTime.wMinute]
0x180033b13  movzx   r8d, [rsp+2F0h+LocalTime.wHour]
0x180033b19  movzx   r10d, [rsp+2F0h+LocalTime.wDay]
0x180033b1f  movzx   r11d, [rsp+2F0h+LocalTime.wMonth]
0x180033b25  movzx   r9d, [rsp+2F0h+LocalTime.wYear]
0x180033b2b  mov     [rsp+2F0h+var_2A8], eax
0x180033b2f  mov     [rsp+2F0h+var_2B0], ecx
0x180033b33  mov     [rsp+2F0h+var_2B8], edx
0x180033b37  mov     dword ptr [rsp+2F0h+hTemplateFile], r8d
0x180033b3c  mov     dword ptr [rsp+2F0h+dwFlagsAndAttributes], r10d
0x180033b41  mov     [rsp+2F0h+dwCreationDisposition], r11d; int
0x180033b46  lea     r8, aD02d02d02d02d0_0; "%d-%02d-%02d %02d:%02d:%02d.%03d   "
0x180033b4d  mov     edx, 104h; unsigned __int64
0x180033b52  lea     rcx, [rbp+1F0h+var_240]; unsigned __int16 *
0x180033b56  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180033b5b  mov     ebx, eax
0x180033b5d  test    eax, eax
0x180033b5f  jns     short loc_180033B83
0x180033b61  mov     rcx, [rbp+1F8h]; this
0x180033b68  mov     r9d, eax; char *
0x180033b6b  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033b72  mov     edx, 289h; void *
0x180033b77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033b7c  mov     eax, ebx
0x180033b7e  jmp     loc_180033F01
0x180033b83  mov     [rsp+2F0h+hMem], r14
0x180033b88  lea     rdx, [rsp+2F0h+hMem]; ppszPathOut
0x180033b8d  mov     rcx, rdi; pszMore
0x180033b90  call    ?GetStoragePath@@YAJPEBGPEAPEAG@Z; GetStoragePath(ushort const *,ushort * *)
0x180033b95  mov     ebx, eax
0x180033b97  test    eax, eax
0x180033b99  jns     short loc_180033BC9
0x180033b9b  mov     edx, 28Ch; void *
0x180033ba0  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033ba7  mov     r9d, ebx; char *
0x180033baa  mov     rcx, [rbp+1F8h]; this
0x180033bb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033bb6  nop
0x180033bb7  mov     rcx, [rsp+2F0h+hMem]; hMem
0x180033bbc  test    rcx, rcx
0x180033bbf  jz      short loc_180033B7C
0x180033bc1  call    cs:__imp_LocalFree
0x180033bc7  jmp     short loc_180033B7C
0x180033bc9  mov     rcx, [rsp+2F0h+hMem]; lpFileName
0x180033bce  call    cs:__imp_GetFileAttributesW
0x180033bd4  mov     r15d, 0FFFFFFFFh
0x180033bda  cmp     eax, r15d
0x180033bdd  jz      short loc_180033BE3
0x180033bdf  test    al, 10h
0x180033be1  jnz     short loc_180033BF8
0x180033be3  mov     rcx, rdi; unsigned __int16 *
0x180033be6  call    ?CreateStoragePath@@YAJPEBG@Z; CreateStoragePath(ushort const *)
0x180033beb  mov     ebx, eax
0x180033bed  test    eax, eax
0x180033bef  jns     short loc_180033BF8
0x180033bf1  mov     edx, 28Fh
0x180033bf6  jmp     short loc_180033BA0
0x180033bf8  mov     [rsp+2F0h+ppszPathOut], r14
0x180033bfd  lea     r9, [rsp+2F0h+ppszPathOut]; ppszPathOut
0x180033c02  xor     r8d, r8d; dwFlags
0x180033c05  lea     rdx, aLogsTxt; "logs.txt"
0x180033c0c  mov     rcx, [rsp+2F0h+hMem]; pszPathIn
0x180033c11  call    cs:__imp_PathAllocCombine
0x180033c17  mov     ebx, eax
0x180033c19  test    eax, eax
0x180033c1b  jns     short loc_180033C52
0x180033c1d  mov     rcx, [rbp+1F8h]; this
0x180033c24  mov     r9d, eax; char *
0x180033c27  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033c2e  mov     edx, 293h; void *
0x180033c33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033c38  nop
0x180033c39  mov     rcx, [rsp+2F0h+ppszPathOut]; hMem
0x180033c3e  test    rcx, rcx
0x180033c41  jz      loc_180033BB7
0x180033c47  call    cs:__imp_LocalFree
0x180033c4d  jmp     loc_180033BB7
0x180033c52  mov     [rsp+2F0h+hTemplateFile], r14; hTemplateFile
0x180033c57  mov     dword ptr [rsp+2F0h+dwFlagsAndAttributes], 80h; char *
0x180033c5f  mov     edx, 4; dwDesiredAccess
0x180033c64  mov     [rsp+2F0h+dwCreationDisposition], edx; int
0x180033c68  xor     r9d, r9d; lpSecurityAttributes
0x180033c6b  lea     r8d, [rdx-3]; dwShareMode
0x180033c6f  mov     rcx, [rsp+2F0h+ppszPathOut]; lpFileName
0x180033c74  call    cs:__imp_CreateFileW
0x180033c7a  mov     rbx, rax
0x180033c7d  mov     [rsp+2F0h+var_288], rax
0x180033c82  xorps   xmm0, xmm0
0x180033c85  movups  xmmword ptr [rbp+1F0h+lpBuffer], xmm0
0x180033c89  xorps   xmm1, xmm1
0x180033c8c  movdqu  [rbp+1F0h+var_260], xmm1
0x180033c91  lea     rax, [rbp+1F0h+var_240]
0x180033c95  or      r8, 0FFFFFFFFFFFFFFFFh
0x180033c99  inc     r8
0x180033c9c  cmp     [rax+r8*2], r14w
0x180033ca1  jnz     short loc_180033C99
0x180033ca3  lea     rdx, [rbp+1F0h+var_240]
0x180033ca7  lea     rcx, [rbp+1F0h+lpBuffer]
0x180033cab  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180033cb0  nop
0x180033cb1  mov     rdx, rsi; void *
0x180033cb4  lea     rcx, [rbp+1F0h+lpBuffer]; Src
0x180033cb8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180033cbd  lea     rdx, asc_18003E4E8; "\n"
0x180033cc4  lea     rcx, [rbp+1F0h+lpBuffer]; Src
0x180033cc8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180033ccd  cmp     qword ptr [rbp+1F0h+var_260+8], 7
0x180033cd2  jbe     short loc_180033CE4
0x180033cd4  mov     rax, [rbp+1F0h+lpBuffer]
0x180033cd8  test    rax, rax
0x180033cdb  jnz     short loc_180033CE8
0x180033cdd  mov     edi, 80070057h
0x180033ce2  jmp     short loc_180033D2B
0x180033ce4  lea     rax, [rbp+1F0h+lpBuffer]
0x180033ce8  mov     r8d, 300000h
0x180033cee  mov     edx, r8d
0x180033cf1  mov     r9d, 2; dwMoveMethod
0x180033cf7  cmp     [rax], r14w
0x180033cfb  jz      short loc_180033D06
0x180033cfd  add     rax, r9
0x180033d00  sub     rdx, 1; lDistanceToMove
0x180033d04  jnz     short loc_180033CF7
0x180033d06  mov     rax, rdx
0x180033d09  neg     rax
0x180033d0c  sbb     ecx, ecx
0x180033d0e  not     ecx
0x180033d10  mov     edi, 80070057h
0x180033d15  and     edi, ecx
0x180033d17  mov     rax, rdx
0x180033d1a  sub     r8, rdx
0x180033d1d  neg     rax
0x180033d20  sbb     rcx, rcx
0x180033d23  and     rcx, r8
0x180033d26  test    rdx, rdx
0x180033d29  jnz     short loc_180033D8F
0x180033d2b  mov     rcx, [rbp+1F8h]; this
0x180033d32  mov     r9d, edi; char *
0x180033d35  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033d3c  mov     edx, 2A4h; void *
0x180033d41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033d46  nop
0x180033d47  lea     rcx, [rbp+1F0h+lpBuffer]
0x180033d4b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033d50  nop
0x180033d51  lea     rax, [rbx-1]
0x180033d55  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180033d59  ja      short loc_180033D65
0x180033d5b  mov     rcx, rbx; hObject
0x180033d5e  call    cs:__imp_CloseHandle
0x180033d64  nop
0x180033d65  mov     rcx, [rsp+2F0h+ppszPathOut]; hMem
0x180033d6a  test    rcx, rcx
0x180033d6d  jz      short loc_180033D76
0x180033d6f  call    cs:__imp_LocalFree
0x180033d75  nop
0x180033d76  mov     rcx, [rsp+2F0h+hMem]; hMem
0x180033d7b  test    rcx, rcx
0x180033d7e  jz      loc_180033AB6
0x180033d84  call    cs:__imp_LocalFree
0x180033d8a  jmp     loc_180033AB6
0x180033d8f  test    rcx, rcx
0x180033d92  jz      loc_180033E54
0x180033d98  mov     rax, r9
0x180033d9b  mul     rcx
0x180033d9e  mov     rdi, rax
0x180033da1  test    rdx, rdx
0x180033da4  jnz     loc_180033E9E
0x180033daa  cmp     rax, r15
0x180033dad  ja      loc_180033E97
0x180033db3  xor     r8d, r8d; lpDistanceToMoveHigh
0x180033db6  mov     rcx, rbx; hFile
0x180033db9  call    cs:__imp_SetFilePointer
0x180033dbf  mov     [rsp+2F0h+NumberOfBytesWritten], r14d
0x180033dc4  lea     rdx, [rbp+1F0h+lpBuffer]
0x180033dc8  cmp     qword ptr [rbp+1F0h+var_260+8], 7
0x180033dcd  cmova   rdx, [rbp+1F0h+lpBuffer]; lpBuffer
0x180033dd2  mov     qword ptr [rsp+2F0h+dwCreationDisposition], r14; lpOverlapped
0x180033dd7  lea     r9, [rsp+2F0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180033ddc  mov     r8d, edi; nNumberOfBytesToWrite
0x180033ddf  mov     rcx, rbx; hFile
0x180033de2  call    cs:__imp_WriteFile
0x180033de8  test    eax, eax
0x180033dea  jnz     short loc_180033E1D
0x180033dec  mov     rcx, [rbp+1F8h]; this
0x180033df3  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033dfa  mov     edx, 2B2h; void *
0x180033dff  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180033e04  mov     edi, eax
0x180033e06  lea     rcx, [rbp+1F0h+lpBuffer]
0x180033e0a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033e0f  nop
0x180033e10  lea     rcx, [rbx-1]
0x180033e14  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180033e18  jmp     loc_180033D59
0x180033e1d  cmp     [rsp+2F0h+NumberOfBytesWritten], edi
0x180033e21  jz      short loc_180033E54
0x180033e23  mov     rcx, [rbp+1F8h]; this
0x180033e2a  lea     rax, aWritetologfile; "WriteToLogFile: failed to write uri dat"...
0x180033e31  mov     qword ptr [rsp+2F0h+dwCreationDisposition], rax; int
0x180033e36  mov     edi, 80004005h
0x180033e3b  mov     r9d, edi; char *
0x180033e3e  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033e45  mov     edx, 2B5h; void *
0x180033e4a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180033e4f  jmp     loc_180033D47
0x180033e54  lea     rcx, [rbp+1F0h+lpBuffer]
0x180033e58  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033e5d  nop
0x180033e5e  lea     rax, [rbx-1]
0x180033e62  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180033e66  ja      short loc_180033E72
0x180033e68  mov     rcx, rbx; hObject
0x180033e6b  call    cs:__imp_CloseHandle
0x180033e71  nop
0x180033e72  mov     rcx, [rsp+2F0h+ppszPathOut]; hMem
0x180033e77  test    rcx, rcx
0x180033e7a  jz      short loc_180033E83
0x180033e7c  call    cs:__imp_LocalFree
0x180033e82  nop
0x180033e83  mov     rcx, [rsp+2F0h+hMem]; hMem
0x180033e88  test    rcx, rcx
0x180033e8b  jz      short loc_180033E93
0x180033e8d  call    cs:__imp_LocalFree
0x180033e93  xor     eax, eax
0x180033e95  jmp     short loc_180033F01
0x180033e97  mov     edx, 2ABh
0x180033e9c  jmp     short loc_180033EA3
0x180033e9e  mov     edx, 2A8h; void *
0x180033ea3  mov     r9d, 80070216h; char *
0x180033ea9  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180033eb0  mov     rcx, [rbp+1F8h]; this
0x180033eb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033ebc  nop
0x180033ebd  lea     rcx, [rbp+1F0h+lpBuffer]
0x180033ec1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033ec6  nop
0x180033ec7  lea     rax, [rbx-1]
0x180033ecb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180033ecf  ja      short loc_180033EDB
0x180033ed1  mov     rcx, rbx; hObject
0x180033ed4  call    cs:__imp_CloseHandle
0x180033eda  nop
0x180033edb  mov     rcx, [rsp+2F0h+ppszPathOut]; hMem
0x180033ee0  test    rcx, rcx
0x180033ee3  jz      short loc_180033EEC
0x180033ee5  call    cs:__imp_LocalFree
0x180033eeb  nop
0x180033eec  mov     rcx, [rsp+2F0h+hMem]; hMem
0x180033ef1  test    rcx, rcx
0x180033ef4  jz      short loc_180033EFC
0x180033ef6  call    cs:__imp_LocalFree
0x180033efc  mov     eax, 80070216h
0x180033f01  mov     rcx, [rbp+1F0h+var_30]
0x180033f08  xor     rcx, rsp; StackCookie
0x180033f0b  call    __security_check_cookie
0x180033f10  mov     rbx, [rsp+2F0h+arg_8]
  ... truncated ...
```
