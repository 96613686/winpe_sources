# RestoreCertificates(ushort const *,char *,char *)

- ea: `0x1800232cc`
- end: `0x180023542`
- name: `?RestoreCertificates@@YAJPEBGPEAD1@Z`
- size: `630`
- prototype: `__int64 __fastcall(const unsigned __int16 *, char *, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001a584`

## callees

- `0x1800091b8`
- `0x1800232cc`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `msvcrt!strncpy_s` at `0x180023395`
- `msvcrt!strncpy_s` at `0x1800233ca`
- `msvcrt!strncpy_s` at `0x180023395`
- `msvcrt!strncpy_s` at `0x1800233ca`
- `msvcrt!strrchr` at `0x180023342`
- `msvcrt!strrchr` at `0x180023350`
- `msvcrt!strrchr` at `0x180023342`
- `msvcrt!strrchr` at `0x180023350`
- `KERNEL32!CopyFileW` at `0x1800234ca`
- `KERNEL32!CopyFileW` at `0x1800234ca`
- `KERNEL32!FindClose` at `0x1800234eb`
- `KERNEL32!FindClose` at `0x1800234eb`
- `KERNEL32!FindNextFileW` at `0x1800234da`
- `KERNEL32!FindNextFileW` at `0x1800234da`
- `KERNEL32!FindFirstFileW` at `0x180023431`
- `KERNEL32!FindFirstFileW` at `0x180023431`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x1800233fb`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x18002340d`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x180023476`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x1800234a0`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x1800233fb`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x18002340d`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x180023476`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x1800234a0`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x1800233ed`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x18002344f`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x18002348b`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x1800233ed`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x18002344f`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x18002348b`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x180023418`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x1800234ae`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x1800234bb`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x180023418`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x1800234ae`
- `IisRTL!?QueryStrW@STRAU@@QEAAPEAGXZ` at `0x1800234bb`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x18002330a`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180023314`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x18002331e`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x18002330a`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x180023314`
- `IisRTL!??0STRAU@@QEAA@XZ` at `0x18002331e`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x1800234f5`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x1800234ff`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x18002350a`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x1800234f5`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x1800234ff`
- `IisRTL!??1STRAU@@QEAA@XZ` at `0x18002350a`

## pseudocode

```c
__int64 __fastcall RestoreCertificates(const unsigned __int16 *a1, char *a2, char *a3)
{
  char *v6; // rdi
  char *v7; // rax
  int v8; // ebx
  unsigned int v9; // ecx
  __int64 v10; // rdi
  unsigned int v11; // eax
  __int64 v12; // rbx
  const WCHAR *StrW; // rax
  HANDLE FirstFileW; // rdi
  __int64 v15; // rax
  const WCHAR *v16; // rbx
  const WCHAR *v17; // rax
  _BYTE v19[128]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v20[128]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v21[128]; // [rsp+120h] [rbp+20h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+1A0h] [rbp+A0h] BYREF
  char v23[272]; // [rsp+3F0h] [rbp+2F0h] BYREF
  char Destination[272]; // [rsp+500h] [rbp+400h] BYREF

  STRAU::STRAU((STRAU *)v19);
  STRAU::STRAU((STRAU *)v21);
  STRAU::STRAU((STRAU *)v20);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v6 = strrchr(a3, 92);
  v7 = strrchr(a2, 92);
  v8 = (int)v7;
  if ( v6 && v7 )
  {
    v9 = (_DWORD)v6 - (_DWORD)a3 + 1;
    if ( v9 > 0x103 )
      v9 = 259;
    v10 = v9;
    strncpy_s(Destination, 0x104u, a3, v9);
    Destination[v10] = 0;
    v11 = v8 - (_DWORD)a2 + 1;
    if ( v11 > 0x103 )
      v11 = 259;
    v12 = v11;
    strncpy_s(v23, 0x104u, a2, v11);
    v23[v12] = 0;
    STRAU::Copy((STRAU *)v19, v23);
    STRAU::Append((STRAU *)v19, a1);
    STRAU::Append((STRAU *)v19, L".*.mp");
    StrW = STRAU::QueryStrW((STRAU *)v19);
    if ( StrW )
    {
      FirstFileW = FindFirstFileW(StrW, &FindFileData);
      if ( FirstFileW != (HANDLE)-1LL )
      {
        do
        {
          if ( STRAU::Copy((STRAU *)v21, Destination) )
          {
            v15 = -1;
            do
              ++v15;
            while ( a1[v15] );
            if ( STRAU::Append((STRAU *)v21, &FindFileData.cAlternateFileName[v15 - 259])
              && STRAU::Copy((STRAU *)v20, v23)
              && STRAU::Append((STRAU *)v20, FindFileData.cFileName) )
            {
              v16 = STRAU::QueryStrW((STRAU *)v21);
              v17 = STRAU::QueryStrW((STRAU *)v20);
              CopyFileW(v17, v16, 0);
            }
          }
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        FindClose(FirstFileW);
      }
    }
  }
  STRAU::~STRAU((STRAU *)v20);
  STRAU::~STRAU((STRAU *)v21);
  STRAU::~STRAU((STRAU *)v19);
  return 0;
}

```

## disassembly

```asm
0x1800232cc  mov     [rsp-8+arg_18], rbx
0x1800232d1  push    rbp
0x1800232d2  push    rsi
0x1800232d3  push    rdi
0x1800232d4  push    r12
0x1800232d6  push    r13
0x1800232d8  push    r14
0x1800232da  push    r15
0x1800232dc  lea     rbp, [rsp-520h]
0x1800232e4  sub     rsp, 620h
0x1800232eb  mov     rax, cs:__security_cookie
0x1800232f2  xor     rax, rsp
0x1800232f5  mov     [rbp+550h+var_40], rax
0x1800232fc  mov     r15, rcx
0x1800232ff  mov     rsi, r8
0x180023302  lea     rcx, [rsp+650h+var_630]
0x180023307  mov     r14, rdx
0x18002330a  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x180023310  lea     rcx, [rbp+550h+var_530]
0x180023314  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x18002331a  lea     rcx, [rbp+550h+var_5B0]
0x18002331e  call    cs:__imp_??0STRAU@@QEAA@XZ; STRAU::STRAU(void)
0x180023324  xor     edx, edx; Val
0x180023326  lea     rcx, [rbp+550h+FindFileData]; void *
0x18002332d  mov     r8d, 250h; Size
0x180023333  call    memset_0
0x180023338  mov     ebx, 5Ch ; '\'
0x18002333d  mov     rcx, rsi; Str
0x180023340  mov     edx, ebx; Ch
0x180023342  call    cs:__imp_strrchr
0x180023348  mov     edx, ebx; Ch
0x18002334a  mov     rcx, r14; Str
0x18002334d  mov     rdi, rax
0x180023350  call    cs:__imp_strrchr
0x180023356  xor     r12d, r12d
0x180023359  mov     rbx, rax
0x18002335c  test    rdi, rdi
0x18002335f  jz      loc_1800234F1
0x180023365  test    rax, rax
0x180023368  jz      loc_1800234F1
0x18002336e  sub     edi, esi
0x180023370  mov     r13d, 103h
0x180023376  mov     r8, rsi; Source
0x180023379  lea     ecx, [rdi+1]
0x18002337c  cmp     ecx, r13d
0x18002337f  lea     esi, [r13+1]
0x180023383  mov     edx, esi; SizeInBytes
0x180023385  cmova   ecx, r13d
0x180023389  mov     edi, ecx
0x18002338b  mov     r9d, ecx; MaxCount
0x18002338e  lea     rcx, [rbp+550h+Destination]; Destination
0x180023395  call    cs:__imp_strncpy_s
0x18002339b  cmp     rdi, rsi
0x18002339e  jnb     loc_18002353C
0x1800233a4  sub     ebx, r14d
0x1800233a7  mov     [rbp+rdi+550h+Destination], r12b
0x1800233af  mov     r8, r14; Source
0x1800233b2  lea     rcx, [rbp+550h+var_260]; Destination
0x1800233b9  mov     edx, esi; SizeInBytes
0x1800233bb  lea     eax, [rbx+1]
0x1800233be  cmp     eax, r13d
0x1800233c1  cmova   eax, r13d
0x1800233c5  mov     r9d, eax; MaxCount
0x1800233c8  mov     ebx, eax
0x1800233ca  call    cs:__imp_strncpy_s
0x1800233d0  cmp     rbx, rsi
0x1800233d3  jnb     loc_18002353C
0x1800233d9  lea     rdx, [rbp+550h+var_260]
0x1800233e0  mov     [rbp+rbx+550h+var_260], r12b
0x1800233e8  lea     rcx, [rsp+650h+var_630]
0x1800233ed  call    cs:__imp_?Copy@STRAU@@QEAAHPEBD@Z; STRAU::Copy(char const *)
0x1800233f3  mov     rdx, r15
0x1800233f6  lea     rcx, [rsp+650h+var_630]
0x1800233fb  call    cs:__imp_?Append@STRAU@@QEAAHPEBG@Z; STRAU::Append(ushort const *)
0x180023401  lea     rdx, aMp_0; ".*.mp"
0x180023408  lea     rcx, [rsp+650h+var_630]
0x18002340d  call    cs:__imp_?Append@STRAU@@QEAAHPEBG@Z; STRAU::Append(ushort const *)
0x180023413  lea     rcx, [rsp+650h+var_630]
0x180023418  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x18002341e  test    rax, rax
0x180023421  jz      loc_1800234F1
0x180023427  lea     rdx, [rbp+550h+FindFileData]; lpFindFileData
0x18002342e  mov     rcx, rax; lpFileName
0x180023431  call    cs:__imp_FindFirstFileW
0x180023437  mov     rdi, rax
0x18002343a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002343e  jz      loc_1800234F1
0x180023444  lea     rdx, [rbp+550h+Destination]
0x18002344b  lea     rcx, [rbp+550h+var_530]
0x18002344f  call    cs:__imp_?Copy@STRAU@@QEAAHPEBD@Z; STRAU::Copy(char const *)
0x180023455  test    eax, eax
0x180023457  jz      short loc_1800234D0
0x180023459  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002345d  inc     rax
0x180023460  cmp     [r15+rax*2], r12w
0x180023465  jnz     short loc_18002345D
0x180023467  lea     rdx, [rbp+550h+FindFileData.cFileName+2]
0x18002346e  lea     rdx, [rdx+rax*2]
0x180023472  lea     rcx, [rbp+550h+var_530]
0x180023476  call    cs:__imp_?Append@STRAU@@QEAAHPEBG@Z; STRAU::Append(ushort const *)
0x18002347c  test    eax, eax
0x18002347e  jz      short loc_1800234D0
0x180023480  lea     rdx, [rbp+550h+var_260]
0x180023487  lea     rcx, [rbp+550h+var_5B0]
0x18002348b  call    cs:__imp_?Copy@STRAU@@QEAAHPEBD@Z; STRAU::Copy(char const *)
0x180023491  test    eax, eax
0x180023493  jz      short loc_1800234D0
0x180023495  lea     rdx, [rbp+550h+FindFileData.cFileName]
0x18002349c  lea     rcx, [rbp+550h+var_5B0]
0x1800234a0  call    cs:__imp_?Append@STRAU@@QEAAHPEBG@Z; STRAU::Append(ushort const *)
0x1800234a6  test    eax, eax
0x1800234a8  jz      short loc_1800234D0
0x1800234aa  lea     rcx, [rbp+550h+var_530]
0x1800234ae  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x1800234b4  lea     rcx, [rbp+550h+var_5B0]
0x1800234b8  mov     rbx, rax
0x1800234bb  call    cs:__imp_?QueryStrW@STRAU@@QEAAPEAGXZ; STRAU::QueryStrW(void)
0x1800234c1  xor     r8d, r8d; bFailIfExists
0x1800234c4  mov     rdx, rbx; lpNewFileName
0x1800234c7  mov     rcx, rax; lpExistingFileName
0x1800234ca  call    cs:__imp_CopyFileW
0x1800234d0  lea     rdx, [rbp+550h+FindFileData]; lpFindFileData
0x1800234d7  mov     rcx, rdi; hFindFile
0x1800234da  call    cs:__imp_FindNextFileW
0x1800234e0  test    eax, eax
0x1800234e2  jnz     loc_180023444
0x1800234e8  mov     rcx, rdi; hFindFile
0x1800234eb  call    cs:__imp_FindClose
0x1800234f1  lea     rcx, [rbp+550h+var_5B0]
0x1800234f5  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x1800234fb  lea     rcx, [rbp+550h+var_530]
0x1800234ff  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180023505  lea     rcx, [rsp+650h+var_630]
0x18002350a  call    cs:__imp_??1STRAU@@QEAA@XZ; STRAU::~STRAU(void)
0x180023510  xor     eax, eax
0x180023512  mov     rcx, [rbp+550h+var_40]
0x180023519  xor     rcx, rsp; StackCookie
0x18002351c  call    __security_check_cookie
0x180023521  mov     rbx, [rsp+650h+arg_18]
0x180023529  add     rsp, 620h
0x180023530  pop     r15
0x180023532  pop     r14
0x180023534  pop     r13
0x180023536  pop     r12
0x180023538  pop     rdi
0x180023539  pop     rsi
0x18002353a  pop     rbp
0x18002353b  retn
0x18002353c  call    __report_rangecheckfailure
```
