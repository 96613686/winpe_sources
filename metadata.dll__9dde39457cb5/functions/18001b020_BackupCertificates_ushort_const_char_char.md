# BackupCertificates(ushort const *,char *,char *)

- ea: `0x18001b020`
- end: `0x18001b2e8`
- name: `?BackupCertificates@@YAJPEBGPEAD1@Z`
- size: `712`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180015e30`

## callees

- `0x1800091b8`
- `0x18001b020`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `msvcrt!strncpy_s` at `0x18001b0e9`
- `msvcrt!strncpy_s` at `0x18001b138`
- `msvcrt!strncpy_s` at `0x18001b0e9`
- `msvcrt!strncpy_s` at `0x18001b138`
- `msvcrt!strcat_s` at `0x18001b186`
- `msvcrt!strcat_s` at `0x18001b186`
- `msvcrt!strrchr` at `0x18001b09a`
- `msvcrt!strrchr` at `0x18001b0a8`
- `msvcrt!strrchr` at `0x18001b09a`
- `msvcrt!strrchr` at `0x18001b0a8`
- `msvcrt!strcpy_s` at `0x18001b111`
- `msvcrt!strcpy_s` at `0x18001b111`
- `KERNEL32!FindFirstFileA` at `0x18001b197`
- `KERNEL32!FindFirstFileA` at `0x18001b197`
- `KERNEL32!CopyFileW` at `0x18001b27d`
- `KERNEL32!CopyFileW` at `0x18001b27d`
- `KERNEL32!FindClose` at `0x18001b29b`
- `KERNEL32!FindClose` at `0x18001b29b`
- `KERNEL32!FindNextFileA` at `0x18001b28a`
- `KERNEL32!FindNextFileA` at `0x18001b28a`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x18001b229`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x18001b229`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001b201`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001b23f`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001b252`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001b201`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001b23f`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001b252`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x18001b1eb`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x18001b217`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x18001b1eb`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x18001b217`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x18001b261`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x18001b26e`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x18001b261`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x18001b26e`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x18001b06e`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x18001b079`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x18001b06e`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x18001b079`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x18001b2a6`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x18001b2b0`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x18001b2a6`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x18001b2b0`

## pseudocode

```c
__int64 __fastcall BackupCertificates(const unsigned __int16 *a1, char *a2, char *a3)
{
  __int64 v6; // rbx
  char *v7; // rsi
  char *v8; // rax
  int v9; // edi
  unsigned int v10; // ecx
  __int64 v11; // rsi
  unsigned int v12; // eax
  __int64 v13; // rdi
  __int64 v14; // rax
  unsigned int v15; // ebx
  HANDLE FirstFileA; // rdi
  __int64 v17; // rsi
  __int64 v18; // rcx
  __int64 v19; // rax
  const WCHAR *StrW; // rbx
  const WCHAR *v21; // rax
  _BYTE v23[128]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v24[128]; // [rsp+A0h] [rbp-60h] BYREF
  struct _WIN32_FIND_DATAA FindFileData; // [rsp+120h] [rbp+20h] BYREF
  char Destination[272]; // [rsp+260h] [rbp+160h] BYREF
  char v27[272]; // [rsp+370h] [rbp+270h] BYREF
  CHAR FileName[272]; // [rsp+480h] [rbp+380h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  STRAU::STRAU((STRAU *)v24);
  STRAU::STRAU((STRAU *)v23);
  v6 = -1;
  do
    ++v6;
  while ( a1[v6] );
  v7 = strrchr(a3, 92);
  v8 = strrchr(a2, 92);
  v9 = (int)v8;
  if ( v7 && v8 )
  {
    v10 = (_DWORD)v7 - (_DWORD)a3 + 1;
    if ( v10 > 0x103 )
      v10 = 259;
    v11 = v10;
    strncpy_s(Destination, 0x104u, a3, v10);
    Destination[v11] = 0;
    strcpy_s(FileName, 0x104u, Destination);
    v12 = v9 - (_DWORD)a2 + 1;
    if ( v12 > 0x103 )
      v12 = 259;
    v13 = v12;
    strncpy_s(v27, 0x104u, a2, v12);
    v27[v13] = 0;
    v14 = -1;
    do
      ++v14;
    while ( Destination[v14] );
    if ( (unsigned __int64)(v14 + 4) < 0x104 )
    {
      v15 = 2 * v6;
      strcat_s(FileName, 0x104u, "*.mp");
      FirstFileA = FindFirstFileA(FileName, &FindFileData);
      if ( FirstFileA != (HANDLE)-1LL )
      {
        v17 = v15;
        do
        {
          v18 = -1;
          do
            ++v18;
          while ( v27[v18] );
          v19 = -1;
          do
            ++v19;
          while ( FindFileData.cFileName[v19] );
          if ( (unsigned __int64)(v17 + v19 + v18 + 1) < 0x104
            && STRAU::Copy((STRAU *)v24, Destination)
            && STRAU::Append((STRAU *)v24, FindFileData.cFileName)
            && STRAU::Copy((STRAU *)v23, v27)
            && STRAU::Append((STRAU *)v23, a1)
            && STRAU::Append((STRAU *)v23, ".")
            && STRAU::Append((STRAU *)v23, FindFileData.cFileName) )
          {
            StrW = STRAU::QueryStrW((STRAU *)v23);
            v21 = STRAU::QueryStrW((STRAU *)v24);
            CopyFileW(v21, StrW, 0);
          }
        }
        while ( FindNextFileA(FirstFileA, &FindFileData) );
        FindClose(FirstFileA);
      }
    }
  }
  STRAU::~STRAU((STRAU *)v23);
  STRAU::~STRAU((STRAU *)v24);
  return 0;
}

```

## disassembly

```asm
0x18001b020  mov     [rsp-8+arg_18], rbx
0x18001b025  push    rbp
0x18001b026  push    rsi
0x18001b027  push    rdi
0x18001b028  push    r12
0x18001b02a  push    r13
0x18001b02c  push    r14
0x18001b02e  push    r15
0x18001b030  lea     rbp, [rsp-4A0h]
0x18001b038  sub     rsp, 5A0h
0x18001b03f  mov     rax, cs:__security_cookie
0x18001b046  xor     rax, rsp
0x18001b049  mov     [rbp+4D0h+var_40], rax
0x18001b050  mov     r14, r8
0x18001b053  mov     r15, rdx
0x18001b056  mov     r12, rcx
0x18001b059  xor     edx, edx; Val
0x18001b05b  mov     r8d, 140h; Size
0x18001b061  lea     rcx, [rbp+4D0h+FindFileData]; void *
0x18001b065  call    memset_0
0x18001b06a  lea     rcx, [rbp+4D0h+var_530]
0x18001b06e  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x18001b074  lea     rcx, [rsp+5D0h+var_5B0]
0x18001b079  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x18001b07f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001b083  xor     r13d, r13d
0x18001b086  inc     rbx
0x18001b089  cmp     [r12+rbx*2], r13w
0x18001b08e  jnz     short loc_18001B086
0x18001b090  mov     edi, 5Ch ; '\'
0x18001b095  mov     rcx, r14; Str
0x18001b098  mov     edx, edi; Ch
0x18001b09a  call    cs:__imp_strrchr
0x18001b0a0  mov     edx, edi; Ch
0x18001b0a2  mov     rcx, r15; Str
0x18001b0a5  mov     rsi, rax
0x18001b0a8  call    cs:__imp_strrchr
0x18001b0ae  mov     rdi, rax
0x18001b0b1  test    rsi, rsi
0x18001b0b4  jz      loc_18001B2A1
0x18001b0ba  test    rax, rax
0x18001b0bd  jz      loc_18001B2A1
0x18001b0c3  sub     esi, r14d
0x18001b0c6  mov     eax, 103h
0x18001b0cb  mov     r8, r14; Source
0x18001b0ce  lea     ecx, [rsi+1]
0x18001b0d1  cmp     ecx, eax
0x18001b0d3  lea     r14d, [rax+1]
0x18001b0d7  mov     edx, r14d; SizeInBytes
0x18001b0da  cmova   ecx, eax
0x18001b0dd  mov     esi, ecx
0x18001b0df  mov     r9d, ecx; MaxCount
0x18001b0e2  lea     rcx, [rbp+4D0h+Destination]; Destination
0x18001b0e9  call    cs:__imp_strncpy_s
0x18001b0ef  cmp     rsi, r14
0x18001b0f2  jnb     loc_18001B2E2
0x18001b0f8  lea     r8, [rbp+4D0h+Destination]; Source
0x18001b0ff  mov     [rbp+rsi+4D0h+Destination], r13b
0x18001b107  mov     edx, r14d; SizeInBytes
0x18001b10a  lea     rcx, [rbp+4D0h+FileName]; Destination
0x18001b111  call    cs:__imp_strcpy_s
0x18001b117  sub     edi, r15d
0x18001b11a  lea     ecx, [r14-1]
0x18001b11e  mov     r8, r15; Source
0x18001b121  mov     edx, r14d; SizeInBytes
0x18001b124  lea     eax, [rdi+1]
0x18001b127  cmp     eax, ecx
0x18001b129  cmova   eax, ecx
0x18001b12c  lea     rcx, [rbp+4D0h+var_260]; Destination
0x18001b133  mov     r9d, eax; MaxCount
0x18001b136  mov     edi, eax
0x18001b138  call    cs:__imp_strncpy_s
0x18001b13e  cmp     rdi, r14
0x18001b141  jnb     loc_18001B2E2
0x18001b147  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001b14b  mov     [rbp+rdi+4D0h+var_260], r13b
0x18001b153  mov     rax, r15
0x18001b156  lea     rcx, [rbp+4D0h+Destination]
0x18001b15d  inc     rax
0x18001b160  cmp     [rcx+rax], r13b
0x18001b164  jnz     short loc_18001B15D
0x18001b166  add     rax, 4
0x18001b16a  cmp     rax, r14
0x18001b16d  jnb     loc_18001B2A1
0x18001b173  lea     r8, Source; "*.mp"
0x18001b17a  mov     rdx, r14; SizeInBytes
0x18001b17d  lea     rcx, [rbp+4D0h+FileName]; Destination
0x18001b184  add     ebx, ebx
0x18001b186  call    cs:__imp_strcat_s
0x18001b18c  lea     rdx, [rbp+4D0h+FindFileData]; lpFindFileData
0x18001b190  lea     rcx, [rbp+4D0h+FileName]; lpFileName
0x18001b197  call    cs:__imp_FindFirstFileA
0x18001b19d  mov     rdi, rax
0x18001b1a0  cmp     rax, r15
0x18001b1a3  jz      loc_18001B2A1
0x18001b1a9  mov     esi, ebx
0x18001b1ab  lea     rax, [rbp+4D0h+var_260]
0x18001b1b2  mov     rcx, r15
0x18001b1b5  inc     rcx
0x18001b1b8  cmp     [rax+rcx], r13b
0x18001b1bc  jnz     short loc_18001B1B5
0x18001b1be  lea     rdx, [rbp+4D0h+FindFileData.cFileName]
0x18001b1c2  mov     rax, r15
0x18001b1c5  inc     rax
0x18001b1c8  cmp     [rdx+rax], r13b
0x18001b1cc  jnz     short loc_18001B1C5
0x18001b1ce  inc     rcx
0x18001b1d1  add     rcx, rax
0x18001b1d4  add     rcx, rsi
0x18001b1d7  cmp     rcx, r14
0x18001b1da  jnb     loc_18001B283
0x18001b1e0  lea     rdx, [rbp+4D0h+Destination]
0x18001b1e7  lea     rcx, [rbp+4D0h+var_530]
0x18001b1eb  call    cs:__imp_?Copy@STRAU@@QEAAHPEBD@Z; STRAU::Copy(char const *)
0x18001b1f1  test    eax, eax
0x18001b1f3  jz      loc_18001B283
0x18001b1f9  lea     rdx, [rbp+4D0h+FindFileData.cFileName]
0x18001b1fd  lea     rcx, [rbp+4D0h+var_530]
0x18001b201  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x18001b207  test    eax, eax
0x18001b209  jz      short loc_18001B283
0x18001b20b  lea     rdx, [rbp+4D0h+var_260]
0x18001b212  lea     rcx, [rsp+5D0h+var_5B0]
0x18001b217  call    cs:__imp_?Copy@STRAU@@QEAAHPEBD@Z; STRAU::Copy(char const *)
0x18001b21d  test    eax, eax
0x18001b21f  jz      short loc_18001B283
0x18001b221  mov     rdx, r12
0x18001b224  lea     rcx, [rsp+5D0h+var_5B0]
0x18001b229  call    cs:__imp_?Append@STRAU@@QEAAHPEBG@Z; STRAU::Append(ushort const *)
0x18001b22f  test    eax, eax
0x18001b231  jz      short loc_18001B283
0x18001b233  lea     rdx, asc_18003BDAC; "."
0x18001b23a  lea     rcx, [rsp+5D0h+var_5B0]
0x18001b23f  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x18001b245  test    eax, eax
0x18001b247  jz      short loc_18001B283
0x18001b249  lea     rdx, [rbp+4D0h+FindFileData.cFileName]
0x18001b24d  lea     rcx, [rsp+5D0h+var_5B0]
0x18001b252  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x18001b258  test    eax, eax
0x18001b25a  jz      short loc_18001B283
0x18001b25c  lea     rcx, [rsp+5D0h+var_5B0]
0x18001b261  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x18001b267  lea     rcx, [rbp+4D0h+var_530]
0x18001b26b  mov     rbx, rax
0x18001b26e  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x18001b274  xor     r8d, r8d; bFailIfExists
0x18001b277  mov     rdx, rbx; lpNewFileName
0x18001b27a  mov     rcx, rax; lpExistingFileName
0x18001b27d  call    cs:__imp_CopyFileW
0x18001b283  lea     rdx, [rbp+4D0h+FindFileData]; lpFindFileData
0x18001b287  mov     rcx, rdi; hFindFile
0x18001b28a  call    cs:__imp_FindNextFileA
0x18001b290  test    eax, eax
0x18001b292  jnz     loc_18001B1AB
0x18001b298  mov     rcx, rdi; hFindFile
0x18001b29b  call    cs:__imp_FindClose
0x18001b2a1  lea     rcx, [rsp+5D0h+var_5B0]
0x18001b2a6  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x18001b2ac  lea     rcx, [rbp+4D0h+var_530]
0x18001b2b0  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x18001b2b6  xor     eax, eax
0x18001b2b8  mov     rcx, [rbp+4D0h+var_40]
0x18001b2bf  xor     rcx, rsp; StackCookie
0x18001b2c2  call    __security_check_cookie
0x18001b2c7  mov     rbx, [rsp+5D0h+arg_18]
0x18001b2cf  add     rsp, 5A0h
0x18001b2d6  pop     r15
0x18001b2d8  pop     r14
0x18001b2da  pop     r13
0x18001b2dc  pop     r12
0x18001b2de  pop     rdi
0x18001b2df  pop     rsi
0x18001b2e0  pop     rbp
0x18001b2e1  retn
0x18001b2e2  call    __report_rangecheckfailure
```
