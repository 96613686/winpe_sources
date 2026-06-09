# CMDCOM::ComMDEnumBackupsD(char *,ulong *,_FILETIME *,ulong,int)

- ea: `0x180017384`
- end: `0x1800177b1`
- name: `?ComMDEnumBackupsD@CMDCOM@@QEAAJPEADPEAKPEAU_FILETIME@@KH@Z`
- size: `1069`
- prototype: `int(CMDCOM *__hidden this, char *, unsigned int *, struct _FILETIME *, unsigned int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017360`
- `0x1800177c0`

## callees

- `0x180017384`
- `0x18001b2f0`
- `0x18001dbe0`
- `0x18001dc74`
- `0x18001deb8`
- `0x18003098e`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `msvcrt!atol` at `0x180017729`
- `msvcrt!atol` at `0x180017729`
- `KERNEL32!FindFirstFileA` at `0x180017514`
- `KERNEL32!FindFirstFileA` at `0x180017514`
- `KERNEL32!WaitForSingleObject` at `0x1800173e7`
- `KERNEL32!WaitForSingleObject` at `0x1800173e7`
- `KERNEL32!FindClose` at `0x180017660`
- `KERNEL32!FindClose` at `0x180017660`
- `KERNEL32!ReleaseSemaphore` at `0x18001776d`
- `KERNEL32!ReleaseSemaphore` at `0x18001776d`
- `KERNEL32!GetLastError` at `0x180017523`
- `KERNEL32!GetLastError` at `0x180017523`
- `KERNEL32!FindNextFileA` at `0x1800175cb`
- `KERNEL32!FindNextFileA` at `0x1800175cb`
- `IisRTL!?SetLen@STRAU@@QEAAHK@Z` at `0x1800176b3`
- `IisRTL!?SetLen@STRAU@@QEAAHK@Z` at `0x1800176b3`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x180017456`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x180017461`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x180017456`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x180017461`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001742d`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001747b`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x180017496`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x1800174b0`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x1800174ca`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001742d`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001747b`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x180017496`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x1800174b0`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x1800174ca`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x18001740d`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x180017565`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x1800175f9`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x180017677`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x18001740d`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x180017565`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x1800175f9`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x180017677`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x1800173ff`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x1800173ff`
- `IisRTL!?QueryCBA@STRAU@@QEAAIXZ` at `0x1800176cb`
- `IisRTL!?QueryCBA@STRAU@@QEAAIXZ` at `0x18001771a`
- `IisRTL!?QueryCBA@STRAU@@QEAAIXZ` at `0x1800176cb`
- `IisRTL!?QueryCBA@STRAU@@QEAAIXZ` at `0x18001771a`
- `IisRTL!?QueryCCH@STRAU@@QEAAIXZ` at `0x1800176c3`
- `IisRTL!?QueryCCH@STRAU@@QEAAIXZ` at `0x1800176c3`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x180017578`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x180017591`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x180017608`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x18001761d`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x18001768a`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x18001769e`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x180017578`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x180017591`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x180017608`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x18001761d`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x18001768a`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x18001769e`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x1800174dd`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x180017507`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x1800175a1`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x180017631`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x1800174dd`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x180017507`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x1800175a1`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x180017631`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x1800173f2`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x1800173f2`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180017778`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x180017778`
- `IisRTL!?QueryCB@STRAU@@QEAAIH@Z` at `0x1800176e0`
- `IisRTL!?QueryCB@STRAU@@QEAAIH@Z` at `0x1800176e0`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180017701`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x180017701`

## pseudocode

```c
__int64 __fastcall CMDCOM::ComMDEnumBackupsD(
        CMDCOM *this,
        char *a2,
        unsigned int *a3,
        struct _FILETIME *a4,
        unsigned int a5,
        int a6)
{
  int v8; // esi
  const char *Str; // rax
  signed int LastHResult; // edi
  int v11; // eax
  const CHAR *StrA; // rax
  HANDLE FirstFileA; // r12
  signed int LastError; // eax
  unsigned int v15; // eax
  unsigned __int16 *v16; // rax
  unsigned int v17; // eax
  char *v18; // rax
  unsigned int v19; // eax
  unsigned __int16 *v20; // rax
  unsigned int v21; // eax
  char *v22; // rax
  unsigned __int16 *StrW; // rax
  unsigned int BackupNameLen; // eax
  unsigned int CCH; // eax
  size_t v26; // rbx
  char *v27; // rax
  unsigned int CBA; // eax
  _BYTE v31[128]; // [rsp+30h] [rbp-D0h] BYREF
  _WIN32_FIND_DATAA FindFileData; // [rsp+B0h] [rbp-50h] BYREF

  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v8 = -1;
  WaitForSingleObject(g_hReadSaveSemaphore, 0xFFFFFFFF);
  STRAU::STRAU((STRAU *)v31);
  Str = STR::QueryStr(g_pstrBackupFilePath);
  if ( !STRAU::Copy((STRAU *)v31, Str) || !STRAU::Append((STRAU *)v31, "\\") )
  {
    LastHResult = -2147024882;
    goto LABEL_60;
  }
  LastHResult = 0;
  if ( a6 )
  {
    if ( *(_WORD *)a2 )
    {
      if ( STRAU::Append((STRAU *)v31, (const unsigned __int16 *)a2) )
      {
LABEL_17:
        if ( STRAU::Append((STRAU *)v31, ".MD") && STRAU::Append((STRAU *)v31, "*") )
        {
          if ( !STRAU::QueryStrA((STRAU *)v31) )
            LastHResult = -2147024882;
          if ( LastHResult < 0 )
            goto LABEL_60;
          memset_0(&FindFileData, 0, sizeof(FindFileData));
          StrA = STRAU::QueryStrA((STRAU *)v31);
          FirstFileA = FindFirstFileA(StrA, &FindFileData);
          if ( FirstFileA == (HANDLE)-1LL )
          {
            LastError = GetLastError();
            LastHResult = LastError;
            if ( LastError > 0 )
              LastHResult = (unsigned __int16)LastError | 0x80070000;
LABEL_48:
            if ( LastHResult < 0 )
            {
              if ( ((LastHResult + 2147024894) & 0xFFFFFFEF) == 0 )
                LastHResult = -2147024637;
              goto LABEL_60;
            }
            if ( STRAU::Copy((STRAU *)v31, FindFileData.cFileName) && STRAU::QueryStrW((STRAU *)v31) )
            {
              StrW = STRAU::QueryStrW((STRAU *)v31);
              BackupNameLen = GetBackupNameLen(StrW);
              STRAU::SetLen((STRAU *)v31, BackupNameLen);
              if ( a6 )
                CCH = STRAU::QueryCCH((STRAU *)v31);
              else
                CCH = STRAU::QueryCBA((STRAU *)v31);
              if ( CCH - 1 > 0x63 )
              {
                LastHResult = -2147024773;
              }
              else
              {
                v26 = (a6 != 0) + 1LL + STRAU::QueryCB((STRAU *)v31, a6);
                v27 = STRAU::QueryStr((STRAU *)v31, a6);
                memcpy_0(a2, v27, v26);
                CBA = STRAU::QueryCBA((STRAU *)v31);
                *a3 = atol(&FindFileData.cAlternateFileName[CBA - 257]);
                *a4 = FindFileData.ftLastWriteTime;
              }
              goto LABEL_60;
            }
            goto LABEL_57;
          }
          v15 = GetBackupNameLen(FindFileData.cFileName);
          if ( (unsigned int)CheckDigits(&FindFileData.cAlternateFileName[v15 - 257]) )
          {
            if ( !STRAU::Copy((STRAU *)v31, FindFileData.cFileName) || !STRAU::QueryStrW((STRAU *)v31) )
            {
              LastHResult = -2147024882;
LABEL_47:
              FindClose(FirstFileA);
              goto LABEL_48;
            }
            if ( a6 )
            {
              v16 = STRAU::QueryStrW((STRAU *)v31);
              v17 = GetBackupNameLen(v16);
            }
            else
            {
              v18 = STRAU::QueryStrA((STRAU *)v31);
              v17 = GetBackupNameLen(v18);
            }
            if ( v17 - 1 <= 0x63 )
              v8 = 0;
          }
          do
          {
            if ( v8 == a5 )
              break;
            if ( FindNextFileA(FirstFileA, &FindFileData) )
            {
              v19 = GetBackupNameLen(FindFileData.cFileName);
              if ( (unsigned int)CheckDigits(&FindFileData.cAlternateFileName[v19 - 257]) )
              {
                if ( STRAU::Copy((STRAU *)v31, FindFileData.cFileName) && STRAU::QueryStrW((STRAU *)v31) )
                {
                  if ( a6 )
                  {
                    v20 = STRAU::QueryStrW((STRAU *)v31);
                    v21 = GetBackupNameLen(v20);
                  }
                  else
                  {
                    v22 = STRAU::QueryStrA((STRAU *)v31);
                    v21 = GetBackupNameLen(v22);
                  }
                  if ( v21 - 1 <= 0x63 )
                    ++v8;
                }
                else
                {
                  LastHResult = -2147024882;
                }
              }
            }
            else
            {
              LastHResult = GetLastHResult();
            }
          }
          while ( LastHResult >= 0 );
          goto LABEL_47;
        }
LABEL_57:
        LastHResult = -2147024882;
        goto LABEL_60;
      }
      LastHResult = -2147024882;
      goto LABEL_14;
    }
    v11 = STRAU::Append((STRAU *)v31, L"*");
  }
  else
  {
    if ( *a2 )
    {
      if ( !STRAU::Append((STRAU *)v31, a2) )
        goto LABEL_57;
      goto LABEL_17;
    }
    v11 = STRAU::Append((STRAU *)v31, "*");
  }
  LastHResult = v11 == 0 ? 0x8007000E : 0;
LABEL_14:
  if ( LastHResult >= 0 )
    goto LABEL_17;
LABEL_60:
  ReleaseSemaphore(g_hReadSaveSemaphore, 1, 0);
  STRAU::~STRAU((STRAU *)v31);
  return (unsigned int)LastHResult;
}

```

## disassembly

```asm
0x180017384  mov     [rsp-8+arg_0], rbx
0x180017389  push    rbp
0x18001738a  push    rsi
0x18001738b  push    rdi
0x18001738c  push    r12
0x18001738e  push    r13
0x180017390  push    r14
0x180017392  push    r15
0x180017394  lea     rbp, [rsp-100h]
0x18001739c  sub     rsp, 200h
0x1800173a3  mov     rax, cs:__security_cookie
0x1800173aa  xor     rax, rsp
0x1800173ad  mov     [rbp+130h+var_40], rax
0x1800173b4  mov     r15d, [rbp+130h+arg_28]
0x1800173bb  xor     r12d, r12d
0x1800173be  mov     [rsp+230h+var_210], r9
0x1800173c3  mov     r13, r8
0x1800173c6  mov     r14, rdx
0x1800173c9  test    rdx, rdx
0x1800173cc  jz      loc_180017780
0x1800173d2  test    r8, r8
0x1800173d5  jz      loc_180017780
0x1800173db  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hHandle
0x1800173e2  or      esi, 0FFFFFFFFh
0x1800173e5  mov     edx, esi; dwMilliseconds
0x1800173e7  call    cs:__imp_WaitForSingleObject
0x1800173ed  lea     rcx, [rsp+230h+var_200]
0x1800173f2  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x1800173f8  mov     rcx, cs:?g_pstrBackupFilePath@@3PEAVSTR@@EA; STR * g_pstrBackupFilePath
0x1800173ff  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x180017405  mov     rdx, rax
0x180017408  lea     rcx, [rsp+230h+var_200]
0x18001740d  call    cs:__imp_?Copy@STRAU@@QEAAHPEBD@Z; STRAU::Copy(char const *)
0x180017413  test    eax, eax
0x180017415  jnz     short loc_180017421
0x180017417  mov     edi, 8007000Eh
0x18001741c  jmp     loc_18001775F
0x180017421  lea     rdx, asc_18003A528; "\\"
0x180017428  lea     rcx, [rsp+230h+var_200]
0x18001742d  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x180017433  test    eax, eax
0x180017435  jz      short loc_180017417
0x180017437  lea     rcx, [rsp+230h+var_200]
0x18001743c  mov     edi, r12d
0x18001743f  mov     ebx, 8007000Eh
0x180017444  test    r15d, r15d
0x180017447  jz      short loc_18001746F
0x180017449  cmp     [r14], r12w
0x18001744d  jnz     short loc_18001745E
0x18001744f  lea     rdx, asc_18003A52C; "*"
0x180017456  call    cs:__imp_?Append@STRAU@@QEAAHPEBG@Z; STRAU::Append(ushort const *)
0x18001745c  jmp     short loc_180017481
0x18001745e  mov     rdx, r14
0x180017461  call    cs:__imp_?Append@STRAU@@QEAAHPEBG@Z; STRAU::Append(ushort const *)
0x180017467  test    eax, eax
0x180017469  jnz     short loc_1800174A4
0x18001746b  mov     edi, ebx
0x18001746d  jmp     short loc_180017489
0x18001746f  cmp     [r14], r12b
0x180017472  jnz     short loc_180017493
0x180017474  lea     rdx, asc_18003A530; "*"
0x18001747b  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x180017481  neg     eax
0x180017483  sbb     edi, edi
0x180017485  not     edi
0x180017487  and     edi, ebx
0x180017489  test    edi, edi
0x18001748b  js      loc_18001775F
0x180017491  jmp     short loc_1800174A4
0x180017493  mov     rdx, r14
0x180017496  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x18001749c  test    eax, eax
0x18001749e  jz      loc_180017748
0x1800174a4  lea     rdx, aMd; ".MD"
0x1800174ab  lea     rcx, [rsp+230h+var_200]
0x1800174b0  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x1800174b6  test    eax, eax
0x1800174b8  jz      loc_180017748
0x1800174be  lea     rdx, asc_18003A530; "*"
0x1800174c5  lea     rcx, [rsp+230h+var_200]
0x1800174ca  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x1800174d0  test    eax, eax
0x1800174d2  jz      loc_180017748
0x1800174d8  lea     rcx, [rsp+230h+var_200]
0x1800174dd  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x1800174e3  test    rax, rax
0x1800174e6  cmovz   edi, ebx
0x1800174e9  test    edi, edi
0x1800174eb  js      loc_18001775F
0x1800174f1  xor     edx, edx; Val
0x1800174f3  lea     rcx, [rbp+130h+FindFileData]; void *
0x1800174f7  mov     r8d, 140h; Size
0x1800174fd  call    memset_0
0x180017502  lea     rcx, [rsp+230h+var_200]
0x180017507  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x18001750d  mov     rcx, rax; lpFileName
0x180017510  lea     rdx, [rbp+130h+FindFileData]; lpFindFileData
0x180017514  call    cs:__imp_FindFirstFileA
0x18001751a  mov     r12, rax
0x18001751d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180017521  jnz     short loc_180017541
0x180017523  call    cs:__imp_GetLastError
0x180017529  mov     edi, eax
0x18001752b  test    eax, eax
0x18001752d  jle     loc_180017666
0x180017533  movzx   edi, ax
0x180017536  or      edi, 80070000h
0x18001753c  jmp     loc_180017666
0x180017541  lea     rcx, [rbp+130h+FindFileData.cFileName]; char *
0x180017545  call    ?GetBackupNameLen@@YAKPEAD@Z; GetBackupNameLen(char *)
0x18001754a  mov     eax, eax
0x18001754c  lea     rcx, [rbp+130h+FindFileData.cFileName+3]
0x180017550  add     rcx, rax; char *
0x180017553  call    ?CheckDigits@@YAHPEAD@Z; CheckDigits(char *)
0x180017558  test    eax, eax
0x18001755a  jz      short loc_1800175B8
0x18001755c  lea     rdx, [rbp+130h+FindFileData.cFileName]
0x180017560  lea     rcx, [rsp+230h+var_200]
0x180017565  call    cs:__imp_?Copy@STRAU@@QEAAHPEBD@Z; STRAU::Copy(char const *)
0x18001756b  test    eax, eax
0x18001756d  jz      loc_18001762D
0x180017573  lea     rcx, [rsp+230h+var_200]
0x180017578  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x18001757e  test    rax, rax
0x180017581  jz      loc_18001762D
0x180017587  lea     rcx, [rsp+230h+var_200]
0x18001758c  test    r15d, r15d
0x18001758f  jz      short loc_1800175A1
0x180017591  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x180017597  mov     rcx, rax; unsigned __int16 *
0x18001759a  call    ?GetBackupNameLen@@YAKPEAG@Z; GetBackupNameLen(ushort *)
0x18001759f  jmp     short loc_1800175AF
0x1800175a1  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x1800175a7  mov     rcx, rax; char *
0x1800175aa  call    ?GetBackupNameLen@@YAKPEAD@Z; GetBackupNameLen(char *)
0x1800175af  dec     eax
0x1800175b1  cmp     eax, 63h ; 'c'
0x1800175b4  ja      short loc_1800175B8
0x1800175b6  xor     esi, esi
0x1800175b8  cmp     esi, [rbp+130h+arg_20]
0x1800175be  jz      loc_18001765D
0x1800175c4  lea     rdx, [rbp+130h+FindFileData]; lpFindFileData
0x1800175c8  mov     rcx, r12; hFindFile
0x1800175cb  call    cs:__imp_FindNextFileA
0x1800175d1  test    eax, eax
0x1800175d3  jz      short loc_18001764E
0x1800175d5  lea     rcx, [rbp+130h+FindFileData.cFileName]; char *
0x1800175d9  call    ?GetBackupNameLen@@YAKPEAD@Z; GetBackupNameLen(char *)
0x1800175de  mov     eax, eax
0x1800175e0  lea     rcx, [rbp+130h+FindFileData.cFileName+3]
0x1800175e4  add     rcx, rax; char *
0x1800175e7  call    ?CheckDigits@@YAHPEAD@Z; CheckDigits(char *)
0x1800175ec  test    eax, eax
0x1800175ee  jz      short loc_180017655
0x1800175f0  lea     rdx, [rbp+130h+FindFileData.cFileName]
0x1800175f4  lea     rcx, [rsp+230h+var_200]
0x1800175f9  call    cs:__imp_?Copy@STRAU@@QEAAHPEBD@Z; STRAU::Copy(char const *)
0x1800175ff  test    eax, eax
0x180017601  jz      short loc_18001764A
0x180017603  lea     rcx, [rsp+230h+var_200]
0x180017608  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x18001760e  test    rax, rax
0x180017611  jz      short loc_18001764A
0x180017613  lea     rcx, [rsp+230h+var_200]
0x180017618  test    r15d, r15d
0x18001761b  jz      short loc_180017631
0x18001761d  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x180017623  mov     rcx, rax; unsigned __int16 *
0x180017626  call    ?GetBackupNameLen@@YAKPEAG@Z; GetBackupNameLen(ushort *)
0x18001762b  jmp     short loc_18001763F
0x18001762d  mov     edi, ebx
0x18001762f  jmp     short loc_18001765D
0x180017631  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x180017637  mov     rcx, rax; char *
0x18001763a  call    ?GetBackupNameLen@@YAKPEAD@Z; GetBackupNameLen(char *)
0x18001763f  dec     eax
0x180017641  cmp     eax, 63h ; 'c'
0x180017644  ja      short loc_180017655
0x180017646  inc     esi
0x180017648  jmp     short loc_180017655
0x18001764a  mov     edi, ebx
0x18001764c  jmp     short loc_180017655
0x18001764e  call    ?GetLastHResult@@YAJXZ; GetLastHResult(void)
0x180017653  mov     edi, eax
0x180017655  test    edi, edi
0x180017657  jns     loc_1800175B8
0x18001765d  mov     rcx, r12; hFindFile
0x180017660  call    cs:__imp_FindClose
0x180017666  test    edi, edi
0x180017668  js      loc_18001774C
0x18001766e  lea     rdx, [rbp+130h+FindFileData.cFileName]
0x180017672  lea     rcx, [rsp+230h+var_200]
0x180017677  call    cs:__imp_?Copy@STRAU@@QEAAHPEBD@Z; STRAU::Copy(char const *)
0x18001767d  test    eax, eax
0x18001767f  jz      loc_180017748
0x180017685  lea     rcx, [rsp+230h+var_200]
0x18001768a  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x180017690  test    rax, rax
0x180017693  jz      loc_180017748
0x180017699  lea     rcx, [rsp+230h+var_200]
0x18001769e  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x1800176a4  mov     rcx, rax; unsigned __int16 *
0x1800176a7  call    ?GetBackupNameLen@@YAKPEAG@Z; GetBackupNameLen(ushort *)
0x1800176ac  mov     edx, eax
0x1800176ae  lea     rcx, [rsp+230h+var_200]
0x1800176b3  call    cs:__imp_?SetLen@STRAU@@QEAAHK@Z; STRAU::SetLen(ulong)
0x1800176b9  lea     rcx, [rsp+230h+var_200]
0x1800176be  test    r15d, r15d
0x1800176c1  jz      short loc_1800176CB
0x1800176c3  call    cs:__imp_?QueryCCH@STRAU@@QEAAIXZ; STRAU::QueryCCH(void)
0x1800176c9  jmp     short loc_1800176D1
0x1800176cb  call    cs:__imp_?QueryCBA@STRAU@@QEAAIXZ; STRAU::QueryCBA(void)
0x1800176d1  dec     eax
0x1800176d3  cmp     eax, 63h ; 'c'
0x1800176d6  ja      short loc_180017741
0x1800176d8  mov     edx, r15d
0x1800176db  lea     rcx, [rsp+230h+var_200]
0x1800176e0  call    cs:__imp_?QueryCB@STRAU@@QEAAIH@Z; STRAU::QueryCB(int)
0x1800176e6  mov     ebx, eax
0x1800176e8  mov     edx, r15d
0x1800176eb  mov     eax, r15d
0x1800176ee  lea     rcx, [rsp+230h+var_200]
0x1800176f3  neg     eax
0x1800176f5  sbb     r8, r8
0x1800176f8  neg     r8
0x1800176fb  inc     r8
0x1800176fe  add     rbx, r8
0x180017701  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x180017707  mov     r8, rbx; Size
0x18001770a  mov     rcx, r14; void *
0x18001770d  mov     rdx, rax; Src
0x180017710  call    memcpy_0
0x180017715  lea     rcx, [rsp+230h+var_200]
0x18001771a  call    cs:__imp_?QueryCBA@STRAU@@QEAAIXZ; STRAU::QueryCBA(void)
0x180017720  mov     eax, eax
0x180017722  lea     rcx, [rbp+130h+FindFileData.cFileName+3]
0x180017726  add     rcx, rax; String
0x180017729  call    cs:__imp_atol
0x18001772f  mov     rcx, [rsp+230h+var_210]
0x180017734  mov     [r13+0], eax
0x180017738  mov     rax, qword ptr [rbp+130h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x18001773c  mov     [rcx], rax
0x18001773f  jmp     short loc_18001775F
0x180017741  mov     edi, 8007007Bh
0x180017746  jmp     short loc_18001775F
0x180017748  mov     edi, ebx
0x18001774a  jmp     short loc_18001775F
0x18001774c  lea     eax, [rdi+7FF8FFFEh]
0x180017752  test    eax, 0FFFFFFEFh
0x180017757  mov     eax, 80070103h
0x18001775c  cmovz   edi, eax
0x18001775f  mov     rcx, cs:?g_hReadSaveSemaphore@@3PEAXEA; hSemaphore
0x180017766  xor     r8d, r8d; lpPreviousCount
0x180017769  lea     edx, [r8+1]; lReleaseCount
0x18001776d  call    cs:__imp_ReleaseSemaphore
0x180017773  lea     rcx, [rsp+230h+var_200]
0x180017778  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x18001777e  jmp     short loc_180017785
0x180017780  mov     edi, 80070057h
0x180017785  mov     eax, edi
0x180017787  mov     rcx, [rbp+130h+var_40]
0x18001778e  xor     rcx, rsp; StackCookie
0x180017791  call    __security_check_cookie
0x180017796  mov     rbx, [rsp+230h+arg_0]
0x18001779e  add     rsp, 200h
0x1800177a5  pop     r15
0x1800177a7  pop     r14
0x1800177a9  pop     r13
0x1800177ab  pop     r12
0x1800177ad  pop     rdi
0x1800177ae  pop     rsi
0x1800177af  pop     rbp
0x1800177b0  retn
```
