# ImportRegFileWorker

- ea: `0x14000ae58`
- end: `0x14000b1cb`
- name: `ImportRegFileWorker`
- size: `883`
- prototype: `void __fastcall(LPCWSTR lpFileName, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x14000998c`

## callees

- `0x140001340`
- `0x140001cc6`
- `0x14000ac00`
- `0x14000ad40`
- `0x14000ae58`
- `0x14000b1d4`
- `0x14000b480`
- `0x14000c560`
- `0x14000c5a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b158`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14000af29`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x14000af29`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000af68`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x14000af68`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14000afb3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x14000afb3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000af04`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000af04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b1a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000b1a3`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14000aecb`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x14000aecb`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x14000b024`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x14000b072`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x14000b024`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x14000b072`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000afe2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000b0db`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000afe2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x14000b0db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000b180`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000b180`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x14000b037`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x14000b085`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x14000b037`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x14000b085`

## string_xrefs

- `0x14000b15e`: `REGEDIT:  CreateFile failed, GetLastError() = %d\n`
- `0x14000afcf`: `Windows Registry Editor Version`

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
    *(__int64 *)((char *)&qword_140054254 + 4) = 0;
    dword_140054250 = 0;
    qword_140054254 = FileSize / 0x64;
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
    LODWORD(qword_140054248) = 0;
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
0x14000ae58  mov     [rsp-8+arg_10], rbx
0x14000ae5d  push    rbp
0x14000ae5e  push    rsi
0x14000ae5f  push    rdi
0x14000ae60  lea     rbp, [rsp-380h]
0x14000ae68  sub     rsp, 480h
0x14000ae6f  mov     rax, cs:__security_cookie
0x14000ae76  xor     rax, rsp
0x14000ae79  mov     [rbp+390h+var_20], rax
0x14000ae80  mov     edi, edx
0x14000ae82  mov     rbx, rcx
0x14000ae85  xor     esi, esi
0x14000ae87  lea     rcx, [rsp+490h+Buffer]; void *
0x14000ae8c  xor     edx, edx; Val
0x14000ae8e  mov     [rsp+490h+var_450], si
0x14000ae93  mov     r8d, 208h; Size
0x14000ae99  call    memset_0
0x14000ae9e  lea     rax, [rsp+490h+FilePart]
0x14000aea3  mov     [rsp+490h+FilePart], rsi
0x14000aea8  mov     [rsp+490h+lpFilePart], rax; lpFilePart
0x14000aead  mov     r9d, 104h; nBufferLength
0x14000aeb3  lea     rax, [rsp+490h+Buffer]
0x14000aeb8  mov     cs:g_FileErrorStringID, esi
0x14000aebe  xor     r8d, r8d; lpExtension
0x14000aec1  mov     [rsp+490h+lpBuffer], rax; lpBuffer
0x14000aec6  mov     rdx, rbx; lpFileName
0x14000aec9  xor     ecx, ecx; lpPath
0x14000aecb  call    cs:__imp_SearchPathW
0x14000aed1  dec     eax
0x14000aed3  cmp     eax, 103h
0x14000aed8  ja      loc_14000B158
0x14000aede  mov     [rsp+490h+hTemplateFile], rsi; hTemplateFile
0x14000aee3  lea     r8d, [rsi+1]; dwShareMode
0x14000aee7  mov     dword ptr [rsp+490h+lpFilePart], 80h; dwFlagsAndAttributes
0x14000aeef  lea     rcx, [rsp+490h+Buffer]; lpFileName
0x14000aef4  xor     r9d, r9d; lpSecurityAttributes
0x14000aef7  mov     dword ptr [rsp+490h+lpBuffer], 3; dwCreationDisposition
0x14000aeff  mov     edx, 80000000h; dwDesiredAccess
0x14000af04  call    cs:__imp_CreateFileW
0x14000af0a  mov     cs:hObject, rax
0x14000af11  mov     rcx, rax; hFile
0x14000af14  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000af18  jz      loc_14000B158
0x14000af1e  xor     edx, edx; lpFileSizeHigh
0x14000af20  mov     [rsp+490h+var_448], si
0x14000af25  mov     [rsp+490h+NumberOfBytesRead], esi
0x14000af29  call    cs:__imp_GetFileSize
0x14000af2f  lea     r9, [rsp+490h+NumberOfBytesRead]; lpNumberOfBytesRead
0x14000af34  mov     cs:qword_140054254+4, rsi
0x14000af3b  mov     ecx, eax
0x14000af3d  mov     cs:dword_140054250, esi
0x14000af43  mov     eax, 51EB851Fh
0x14000af48  mov     [rsp+490h+lpBuffer], rsi; lpOverlapped
0x14000af4d  mul     ecx
0x14000af4f  mov     rcx, cs:hObject; hFile
0x14000af56  lea     r8d, [rsi+2]; nNumberOfBytesToRead
0x14000af5a  shr     edx, 5
0x14000af5d  mov     dword ptr cs:qword_140054254, edx
0x14000af63  lea     rdx, [rsp+490h+var_448]; lpBuffer
0x14000af68  call    cs:__imp_ReadFile
0x14000af6e  test    eax, eax
0x14000af70  jnz     short loc_14000AF81
0x14000af72  mov     cs:g_FileErrorStringID, 2BFh
0x14000af7c  jmp     loc_14000B197
0x14000af81  mov     eax, 0FEFFh
0x14000af86  cmp     [rsp+490h+var_448], ax
0x14000af8b  jnz     short loc_14000AF99
0x14000af8d  mov     cs:s_fTreatFileAsUnicode, 1
0x14000af97  jmp     short loc_14000AFB9
0x14000af99  mov     rcx, cs:hObject; hFile
0x14000afa0  mov     r9d, 1; dwMoveMethod
0x14000afa6  xor     r8d, r8d; lpDistanceToMoveHigh
0x14000afa9  mov     cs:s_fTreatFileAsUnicode, esi
0x14000afaf  lea     edx, [r9-3]; lDistanceToMove
0x14000afb3  call    cs:__imp_SetFilePointer
0x14000afb9  mov     dword ptr cs:qword_140054248, esi
0x14000afbf  call    SkipWhitespace
0x14000afc4  mov     ecx, 57h ; 'W'
0x14000afc9  mov     cs:g_ImportFileVersion, esi
0x14000afcf  lea     rbx, s_WinNT50RegFileHeader; "Windows Registry Editor Version"
0x14000afd6  call    MatchChar
0x14000afdb  test    eax, eax
0x14000afdd  jz      short loc_14000AFF3
0x14000afdf  mov     rcx, rbx; lpsz
0x14000afe2  call    cs:__imp_CharNextW
0x14000afe8  mov     rbx, rax
0x14000afeb  movzx   ecx, word ptr [rax]
0x14000afee  test    cx, cx
0x14000aff1  jnz     short loc_14000AFD6
0x14000aff3  cmp     si, [rbx]
0x14000aff6  jnz     loc_14000B0C3
0x14000affc  call    SkipWhitespace
0x14000b001  mov     [rsp+490h+var_44A], si
0x14000b006  mov     ebx, 2Eh ; '.'
0x14000b00b  jmp     short loc_14000B04E
0x14000b00d  lea     rcx, [rsp+490h+pszSrc]
0x14000b012  call    GetChar
0x14000b017  test    eax, eax
0x14000b019  jz      loc_14000B14C
0x14000b01f  movzx   ecx, [rsp+490h+pszSrc]; ch
0x14000b024  call    cs:__imp_IsCharAlphaNumericW
0x14000b02a  test    eax, eax
0x14000b02c  jz      loc_14000B14C
0x14000b032  lea     rcx, [rsp+490h+pszSrc]; pszSrc
0x14000b037  call    cs:__imp_StrToIntW
0x14000b03d  mov     ecx, cs:g_ImportFileVersion
0x14000b043  shl     ecx, 4
0x14000b046  add     ecx, eax
0x14000b048  mov     cs:g_ImportFileVersion, ecx
0x14000b04e  mov     ecx, ebx
0x14000b050  call    MatchChar
0x14000b055  test    eax, eax
0x14000b057  jz      short loc_14000B00D
0x14000b059  mov     ebx, esi
0x14000b05b  lea     rcx, [rsp+490h+pszSrc]
0x14000b060  call    GetChar
0x14000b065  test    eax, eax
0x14000b067  jz      loc_14000B14C
0x14000b06d  movzx   ecx, [rsp+490h+pszSrc]; ch
0x14000b072  call    cs:__imp_IsCharAlphaNumericW
0x14000b078  test    eax, eax
0x14000b07a  jz      loc_14000B14C
0x14000b080  lea     rcx, [rsp+490h+pszSrc]; pszSrc
0x14000b085  call    cs:__imp_StrToIntW
0x14000b08b  mov     edx, cs:g_ImportFileVersion
0x14000b091  inc     ebx
0x14000b093  shl     edx, 4
0x14000b096  add     edx, eax
0x14000b098  mov     cs:g_ImportFileVersion, edx
0x14000b09e  cmp     ebx, 2
0x14000b0a1  jb      short loc_14000B05B
0x14000b0a3  cmp     edx, 500h
0x14000b0a9  jz      short loc_14000B0BA
0x14000b0ab  mov     cs:g_FileErrorStringID, 2C3h
0x14000b0b5  jmp     loc_14000B197
0x14000b0ba  call    SkipWhitespace
0x14000b0bf  mov     ecx, edi
0x14000b0c1  jmp     short loc_14000B134
0x14000b0c3  lea     rbx, s_RegistryHeader; "REGEDIT"
0x14000b0ca  mov     ecx, 52h ; 'R'
0x14000b0cf  call    MatchChar
0x14000b0d4  test    eax, eax
0x14000b0d6  jz      short loc_14000B0EC
0x14000b0d8  mov     rcx, rbx; lpsz
0x14000b0db  call    cs:__imp_CharNextW
0x14000b0e1  mov     rbx, rax
0x14000b0e4  movzx   ecx, word ptr [rax]
0x14000b0e7  test    cx, cx
0x14000b0ea  jnz     short loc_14000B0CF
0x14000b0ec  cmp     [rbx], si
0x14000b0ef  jnz     short loc_14000B14C
0x14000b0f1  mov     ecx, 34h ; '4'
0x14000b0f6  call    MatchChar
0x14000b0fb  mov     ebx, eax
0x14000b0fd  call    SkipWhitespace
0x14000b102  lea     rcx, [rsp+490h+var_450]
0x14000b107  call    GetChar
0x14000b10c  test    eax, eax
0x14000b10e  jz      loc_14000B197
0x14000b114  cmp     [rsp+490h+var_450], 0Ah
0x14000b11a  jz      short loc_14000B124
0x14000b11c  cmp     [rsp+490h+var_450], 0Dh
0x14000b122  jnz     short loc_14000B197
0x14000b124  mov     ecx, edi
0x14000b126  test    ebx, ebx
0x14000b128  jz      short loc_14000B13B
0x14000b12a  mov     cs:g_ImportFileVersion, 400h
0x14000b134  call    ImportNewerRegFile
0x14000b139  jmp     short loc_14000B197
0x14000b13b  mov     cs:g_ImportFileVersion, 310h
0x14000b145  call    ImportWin31RegFile
0x14000b14a  jmp     short loc_14000B197
0x14000b14c  mov     cs:g_FileErrorStringID, 2C2h
0x14000b156  jmp     short loc_14000B197
0x14000b158  call    cs:__imp_GetLastError
0x14000b15e  lea     r8, aRegeditCreatef; "REGEDIT:  CreateFile failed, GetLastErr"...
0x14000b165  mov     edx, 0FAh; cchDest
0x14000b16a  mov     r9d, eax
0x14000b16d  lea     rcx, [rbp+390h+pszDest]; pszDest
0x14000b174  call    StringCchPrintfW
0x14000b179  lea     rcx, [rbp+390h+pszDest]; lpOutputString
0x14000b180  call    cs:__imp_OutputDebugStringW
0x14000b186  mov     cs:hObject, rsi
0x14000b18d  mov     cs:g_FileErrorStringID, 2BEh
0x14000b197  mov     rcx, cs:hObject; hObject
0x14000b19e  test    rcx, rcx
0x14000b1a1  jz      short loc_14000B1A9
0x14000b1a3  call    cs:__imp_CloseHandle
0x14000b1a9  mov     rcx, [rbp+390h+var_20]
0x14000b1b0  xor     rcx, rsp; StackCookie
0x14000b1b3  call    __security_check_cookie
0x14000b1b8  mov     rbx, [rsp+490h+arg_10]
0x14000b1c0  add     rsp, 480h
0x14000b1c7  pop     rdi
0x14000b1c8  pop     rsi
0x14000b1c9  pop     rbp
0x14000b1ca  retn
```
