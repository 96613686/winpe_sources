# ImportRegFileWorker

- ea: `0x14000b54c`
- end: `0x14000b914`
- name: `ImportRegFileWorker`
- size: `968`
- prototype: `void __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x140009f80`

## callees

- `0x140001340`
- `0x140001cc6`
- `0x14000b2c4`
- `0x14000b418`
- `0x14000b54c`
- `0x14000b91c`
- `0x14000bbf0`
- `0x14000cd84`
- `0x14000cdc4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b88e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b88e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14000b629`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14000b629`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000b66e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000b66e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14000b6bf`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14000b6bf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000b5fe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000b5fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b8e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b8e5`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14000b5bf`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14000b5bf`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x14000b73c`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x14000b796`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x14000b73c`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x14000b796`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000b6f4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000b80b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000b6f4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000b80b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000b8bc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000b8bc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x14000b755`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x14000b7af`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x14000b755`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x14000b7af`

## string_xrefs

- `0x14000b89a`: `REGEDIT:  CreateFile failed, GetLastError() = %d\n`
- `0x14000b6e1`: `Windows Registry Editor Version`

## pseudocode

```c
void __fastcall ImportRegFileWorker(LPCWSTR lpFileName, unsigned int a2)
{
  DWORD FileSize; // eax
  __int64 v5; // rcx
  const WCHAR *v6; // rbx
  unsigned int v7; // ebx
  int v8; // edx
  __int64 v9; // rcx
  const WCHAR *v10; // rbx
  __int64 v11; // rcx
  int matched; // ebx
  DWORD LastError; // eax
  _WORD v14[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszSrc[2]; // [rsp+44h] [rbp-BCh] BYREF
  _WORD v16[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD NumberOfBytesRead; // [rsp+4Ch] [rbp-B4h] BYREF
  LPWSTR FilePart; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[256]; // [rsp+270h] [rbp+170h] BYREF

  v14[0] = 0;
  memset_0(Buffer, 0, 0x208u);
  FilePart = 0;
  g_FileErrorStringID = 0;
  if ( SearchPathW(0, lpFileName, 0, 0x104u, Buffer, &FilePart) - 1 > 0x103
    || (hObject = CreateFileW(Buffer, 0x80000000, 1u, 0, 3u, 0x80u, 0), hObject == (HANDLE)-1LL) )
  {
    LastError = GetLastError();
    StringCchPrintfW(pszDest, 0xFAu, L"REGEDIT:  CreateFile failed, GetLastError() = %d\n", LastError);
    OutputDebugStringW(pszDest);
    hObject = 0;
    g_FileErrorStringID = 702;
  }
  else
  {
    v16[0] = 0;
    NumberOfBytesRead = 0;
    FileSize = GetFileSize(hObject, 0);
    *(__int64 *)((char *)&qword_140055254 + 4) = 0;
    dword_140055250 = 0;
    qword_140055254 = FileSize / 0x64;
    if ( !ReadFile(hObject, v16, 2u, &NumberOfBytesRead, 0) )
    {
      g_FileErrorStringID = 703;
      goto LABEL_37;
    }
    if ( v16[0] == 0xFEFF )
    {
      s_fTreatFileAsUnicode = 1;
    }
    else
    {
      s_fTreatFileAsUnicode = 0;
      SetFilePointer(hObject, -2, 0, 1u);
    }
    LODWORD(qword_140055248) = 0;
    SkipWhitespace();
    v5 = 87;
    g_ImportFileVersion = 0;
    v6 = L"Windows Registry Editor Version";
    do
    {
      if ( !(unsigned int)MatchChar(v5) )
        break;
      v6 = CharNextW(v6);
      v5 = *v6;
    }
    while ( (_WORD)v5 );
    if ( !*v6 )
    {
      SkipWhitespace();
      pszSrc[1] = 0;
      while ( !(unsigned int)MatchChar(46) )
      {
        if ( !(unsigned int)GetChar(pszSrc) || !IsCharAlphaNumericW(pszSrc[0]) )
          goto LABEL_35;
        g_ImportFileVersion = StrToIntW(pszSrc) + 16 * g_ImportFileVersion;
      }
      v7 = 0;
      while ( (unsigned int)GetChar(pszSrc) && IsCharAlphaNumericW(pszSrc[0]) )
      {
        ++v7;
        v8 = StrToIntW(pszSrc) + 16 * g_ImportFileVersion;
        g_ImportFileVersion = v8;
        if ( v7 >= 2 )
        {
          if ( v8 != 1280 )
          {
            g_FileErrorStringID = 707;
            goto LABEL_37;
          }
          SkipWhitespace();
          v9 = a2;
          goto LABEL_33;
        }
      }
      goto LABEL_35;
    }
    v10 = L"REGEDIT";
    v11 = 82;
    do
    {
      if ( !(unsigned int)MatchChar(v11) )
        break;
      v10 = CharNextW(v10);
      v11 = *v10;
    }
    while ( (_WORD)v11 );
    if ( *v10 )
    {
LABEL_35:
      g_FileErrorStringID = 706;
      goto LABEL_37;
    }
    matched = MatchChar(52);
    SkipWhitespace();
    if ( (unsigned int)GetChar(v14) && (v14[0] == 10 || v14[0] == 13) )
    {
      v9 = a2;
      if ( matched )
      {
        g_ImportFileVersion = 1024;
LABEL_33:
        ImportNewerRegFile(v9);
      }
      else
      {
        g_ImportFileVersion = 784;
        ImportWin31RegFile(a2);
      }
    }
  }
LABEL_37:
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x14000b54c  mov     [rsp-8+arg_10], rbx
0x14000b551  push    rbp
0x14000b552  push    rsi
0x14000b553  push    rdi
0x14000b554  lea     rbp, [rsp-380h]
0x14000b55c  sub     rsp, 480h
0x14000b563  mov     rax, cs:__security_cookie
0x14000b56a  xor     rax, rsp
0x14000b56d  mov     [rbp+390h+var_20], rax
0x14000b574  mov     edi, edx
0x14000b576  mov     rbx, rcx
0x14000b579  xor     esi, esi
0x14000b57b  lea     rcx, [rsp+490h+Buffer]; void *
0x14000b580  xor     edx, edx; Val
0x14000b582  mov     [rsp+490h+var_450], si
0x14000b587  mov     r8d, 208h; Size
0x14000b58d  call    memset_0
0x14000b592  lea     rax, [rsp+490h+FilePart]
0x14000b597  mov     [rsp+490h+FilePart], rsi
0x14000b59c  mov     [rsp+490h+lpFilePart], rax; lpFilePart
0x14000b5a1  mov     r9d, 104h; nBufferLength
0x14000b5a7  lea     rax, [rsp+490h+Buffer]
0x14000b5ac  mov     cs:g_FileErrorStringID, esi
0x14000b5b2  xor     r8d, r8d; lpExtension
0x14000b5b5  mov     [rsp+490h+lpBuffer], rax; lpBuffer
0x14000b5ba  mov     rdx, rbx; lpFileName
0x14000b5bd  xor     ecx, ecx; lpPath
0x14000b5bf  call    cs:__imp_SearchPathW
0x14000b5c6  nop     dword ptr [rax+rax+00h]
0x14000b5cb  dec     eax
0x14000b5cd  cmp     eax, 103h
0x14000b5d2  ja      loc_14000B88E
0x14000b5d8  mov     [rsp+490h+hTemplateFile], rsi; hTemplateFile
0x14000b5dd  lea     r8d, [rsi+1]; dwShareMode
0x14000b5e1  mov     dword ptr [rsp+490h+lpFilePart], 80h; dwFlagsAndAttributes
0x14000b5e9  lea     rcx, [rsp+490h+Buffer]; lpFileName
0x14000b5ee  xor     r9d, r9d; lpSecurityAttributes
0x14000b5f1  mov     dword ptr [rsp+490h+lpBuffer], 3; dwCreationDisposition
0x14000b5f9  mov     edx, 80000000h; dwDesiredAccess
0x14000b5fe  call    cs:__imp_CreateFileW
0x14000b605  nop     dword ptr [rax+rax+00h]
0x14000b60a  mov     cs:hObject, rax
0x14000b611  mov     rcx, rax; hFile
0x14000b614  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000b618  jz      loc_14000B88E
0x14000b61e  xor     edx, edx; lpFileSizeHigh
0x14000b620  mov     [rsp+490h+var_448], si
0x14000b625  mov     [rsp+490h+NumberOfBytesRead], esi
0x14000b629  call    cs:__imp_GetFileSize
0x14000b630  nop     dword ptr [rax+rax+00h]
0x14000b635  lea     r9, [rsp+490h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14000b63a  mov     cs:qword_140055254+4, rsi
0x14000b641  mov     ecx, eax
0x14000b643  mov     cs:dword_140055250, esi
0x14000b649  mov     eax, 51EB851Fh
0x14000b64e  mov     [rsp+490h+lpBuffer], rsi; lpOverlapped
0x14000b653  mul     ecx
0x14000b655  mov     rcx, cs:hObject; hFile
0x14000b65c  lea     r8d, [rsi+2]; nNumberOfBytesToRead
0x14000b660  shr     edx, 5
0x14000b663  mov     dword ptr cs:qword_140055254, edx
0x14000b669  lea     rdx, [rsp+490h+var_448]; lpBuffer
0x14000b66e  call    cs:__imp_ReadFile
0x14000b675  nop     dword ptr [rax+rax+00h]
0x14000b67a  test    eax, eax
0x14000b67c  jnz     short loc_14000B68D
0x14000b67e  mov     cs:g_FileErrorStringID, 2BFh
0x14000b688  jmp     loc_14000B8D9
0x14000b68d  mov     eax, 0FEFFh
0x14000b692  cmp     [rsp+490h+var_448], ax
0x14000b697  jnz     short loc_14000B6A5
0x14000b699  mov     cs:s_fTreatFileAsUnicode, 1
0x14000b6a3  jmp     short loc_14000B6CB
0x14000b6a5  mov     rcx, cs:hObject; hFile
0x14000b6ac  mov     r9d, 1; dwMoveMethod
0x14000b6b2  xor     r8d, r8d; lpDistanceToMoveHigh
0x14000b6b5  mov     cs:s_fTreatFileAsUnicode, esi
0x14000b6bb  lea     edx, [r9-3]; lDistanceToMove
0x14000b6bf  call    cs:__imp_SetFilePointer
0x14000b6c6  nop     dword ptr [rax+rax+00h]
0x14000b6cb  mov     dword ptr cs:qword_140055248, esi
0x14000b6d1  call    SkipWhitespace
0x14000b6d6  mov     ecx, 57h ; 'W'
0x14000b6db  mov     cs:g_ImportFileVersion, esi
0x14000b6e1  lea     rbx, s_WinNT50RegFileHeader; "Windows Registry Editor Version"
0x14000b6e8  call    MatchChar
0x14000b6ed  test    eax, eax
0x14000b6ef  jz      short loc_14000B70B
0x14000b6f1  mov     rcx, rbx; lpsz
0x14000b6f4  call    cs:__imp_CharNextW
0x14000b6fb  nop     dword ptr [rax+rax+00h]
0x14000b700  mov     rbx, rax
0x14000b703  movzx   ecx, word ptr [rax]
0x14000b706  test    cx, cx
0x14000b709  jnz     short loc_14000B6E8
0x14000b70b  cmp     si, [rbx]
0x14000b70e  jnz     loc_14000B7F3
0x14000b714  call    SkipWhitespace
0x14000b719  mov     [rsp+490h+var_44A], si
0x14000b71e  mov     ebx, 2Eh ; '.'
0x14000b723  jmp     short loc_14000B772
0x14000b725  lea     rcx, [rsp+490h+pszSrc]
0x14000b72a  call    GetChar
0x14000b72f  test    eax, eax
0x14000b731  jz      loc_14000B882
0x14000b737  movzx   ecx, [rsp+490h+pszSrc]; ch
0x14000b73c  call    cs:__imp_IsCharAlphaNumericW
0x14000b743  nop     dword ptr [rax+rax+00h]
0x14000b748  test    eax, eax
0x14000b74a  jz      loc_14000B882
0x14000b750  lea     rcx, [rsp+490h+pszSrc]; pszSrc
0x14000b755  call    cs:__imp_StrToIntW
0x14000b75c  nop     dword ptr [rax+rax+00h]
0x14000b761  mov     ecx, cs:g_ImportFileVersion
0x14000b767  shl     ecx, 4
0x14000b76a  add     ecx, eax
0x14000b76c  mov     cs:g_ImportFileVersion, ecx
0x14000b772  mov     ecx, ebx
0x14000b774  call    MatchChar
0x14000b779  test    eax, eax
0x14000b77b  jz      short loc_14000B725
0x14000b77d  mov     ebx, esi
0x14000b77f  lea     rcx, [rsp+490h+pszSrc]
0x14000b784  call    GetChar
0x14000b789  test    eax, eax
0x14000b78b  jz      loc_14000B882
0x14000b791  movzx   ecx, [rsp+490h+pszSrc]; ch
0x14000b796  call    cs:__imp_IsCharAlphaNumericW
0x14000b79d  nop     dword ptr [rax+rax+00h]
0x14000b7a2  test    eax, eax
0x14000b7a4  jz      loc_14000B882
0x14000b7aa  lea     rcx, [rsp+490h+pszSrc]; pszSrc
0x14000b7af  call    cs:__imp_StrToIntW
0x14000b7b6  nop     dword ptr [rax+rax+00h]
0x14000b7bb  mov     edx, cs:g_ImportFileVersion
0x14000b7c1  inc     ebx
0x14000b7c3  shl     edx, 4
0x14000b7c6  add     edx, eax
0x14000b7c8  mov     cs:g_ImportFileVersion, edx
0x14000b7ce  cmp     ebx, 2
0x14000b7d1  jb      short loc_14000B77F
0x14000b7d3  cmp     edx, 500h
0x14000b7d9  jz      short loc_14000B7EA
0x14000b7db  mov     cs:g_FileErrorStringID, 2C3h
0x14000b7e5  jmp     loc_14000B8D9
0x14000b7ea  call    SkipWhitespace
0x14000b7ef  mov     ecx, edi
0x14000b7f1  jmp     short loc_14000B86A
0x14000b7f3  lea     rbx, s_RegistryHeader; "REGEDIT"
0x14000b7fa  mov     ecx, 52h ; 'R'
0x14000b7ff  call    MatchChar
0x14000b804  test    eax, eax
0x14000b806  jz      short loc_14000B822
0x14000b808  mov     rcx, rbx; lpsz
0x14000b80b  call    cs:__imp_CharNextW
0x14000b812  nop     dword ptr [rax+rax+00h]
0x14000b817  mov     rbx, rax
0x14000b81a  movzx   ecx, word ptr [rax]
0x14000b81d  test    cx, cx
0x14000b820  jnz     short loc_14000B7FF
0x14000b822  cmp     [rbx], si
0x14000b825  jnz     short loc_14000B882
0x14000b827  mov     ecx, 34h ; '4'
0x14000b82c  call    MatchChar
0x14000b831  mov     ebx, eax
0x14000b833  call    SkipWhitespace
0x14000b838  lea     rcx, [rsp+490h+var_450]
0x14000b83d  call    GetChar
0x14000b842  test    eax, eax
0x14000b844  jz      loc_14000B8D9
0x14000b84a  cmp     [rsp+490h+var_450], 0Ah
0x14000b850  jz      short loc_14000B85A
0x14000b852  cmp     [rsp+490h+var_450], 0Dh
0x14000b858  jnz     short loc_14000B8D9
0x14000b85a  mov     ecx, edi
0x14000b85c  test    ebx, ebx
0x14000b85e  jz      short loc_14000B871
0x14000b860  mov     cs:g_ImportFileVersion, 400h
0x14000b86a  call    ImportNewerRegFile
0x14000b86f  jmp     short loc_14000B8D9
0x14000b871  mov     cs:g_ImportFileVersion, 310h
0x14000b87b  call    ImportWin31RegFile
0x14000b880  jmp     short loc_14000B8D9
0x14000b882  mov     cs:g_FileErrorStringID, 2C2h
0x14000b88c  jmp     short loc_14000B8D9
0x14000b88e  call    cs:__imp_GetLastError
0x14000b895  nop     dword ptr [rax+rax+00h]
0x14000b89a  lea     r8, aRegeditCreatef; "REGEDIT:  CreateFile failed, GetLastErr"...
0x14000b8a1  mov     edx, 0FAh; cchDest
0x14000b8a6  mov     r9d, eax
0x14000b8a9  lea     rcx, [rbp+390h+pszDest]; pszDest
0x14000b8b0  call    StringCchPrintfW
0x14000b8b5  lea     rcx, [rbp+390h+pszDest]; lpOutputString
0x14000b8bc  call    cs:__imp_OutputDebugStringW
0x14000b8c3  nop     dword ptr [rax+rax+00h]
0x14000b8c8  mov     cs:hObject, rsi
0x14000b8cf  mov     cs:g_FileErrorStringID, 2BEh
0x14000b8d9  mov     rcx, cs:hObject; hObject
0x14000b8e0  test    rcx, rcx
0x14000b8e3  jz      short loc_14000B8F1
0x14000b8e5  call    cs:__imp_CloseHandle
0x14000b8ec  nop     dword ptr [rax+rax+00h]
0x14000b8f1  mov     rcx, [rbp+390h+var_20]
0x14000b8f8  xor     rcx, rsp; StackCookie
0x14000b8fb  call    __security_check_cookie
0x14000b900  mov     rbx, [rsp+490h+arg_10]
0x14000b908  add     rsp, 480h
0x14000b90f  pop     rdi
0x14000b910  pop     rsi
0x14000b911  pop     rbp
0x14000b912  retn
```
