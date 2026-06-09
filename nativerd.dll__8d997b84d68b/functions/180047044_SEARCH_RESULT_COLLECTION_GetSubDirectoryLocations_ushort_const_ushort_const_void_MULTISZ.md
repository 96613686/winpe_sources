# SEARCH_RESULT_COLLECTION::GetSubDirectoryLocations(ushort const *,ushort const *,void *,MULTISZ *)

- ea: `0x180047044`
- end: `0x18004738c`
- name: `?GetSubDirectoryLocations@SEARCH_RESULT_COLLECTION@@AEAAJPEBG0PEAXPEAVMULTISZ@@@Z`
- size: `840`
- prototype: `int(SEARCH_RESULT_COLLECTION *__hidden this, const unsigned __int16 *, const unsigned __int16 *, void *, struct MULTISZ *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800469e8`

## callees

- `0x180047044`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004713e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800472d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800472e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004713e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800472d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800472e5`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800472fd`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800472fd`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800471f1`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800471f1`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800472c6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800472c6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004733f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004733f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180047127`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180047127`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180047112`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180047112`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180047313`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180047313`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180047328`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180047328`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004715f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18004715f`
- `iisutil!?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z` at `0x1800472b5`
- `iisutil!?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z` at `0x1800472b5`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004734f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004735a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004734f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18004735a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180047189`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800471e4`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180047189`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800471e4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800470b7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800470dd`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800470b7`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800470dd`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180047197`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x180047197`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180047174`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180047274`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180047174`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180047274`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800471b3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800471cf`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004728c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800472a1`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800471b3`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800471cf`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18004728c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800472a1`

## pseudocode

```c
__int64 __fastcall SEARCH_RESULT_COLLECTION::GetSubDirectoryLocations(
        SEARCH_RESULT_COLLECTION *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void *a4,
        struct MULTISZ *a5)
{
  int v8; // esi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v11; // ebx
  unsigned __int16 *Str; // rbx
  const WCHAR *v13; // rax
  HANDLE FirstFileW; // rdi
  DWORD v15; // eax
  int v16; // edx
  int v17; // edx
  signed int v18; // eax
  void *TokenHandle; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v21[56]; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v22[64]; // [rsp+60h] [rbp-A0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v24[264]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int16 v25[264]; // [rsp+500h] [rbp+400h] BYREF

  TokenHandle = 0;
  memset_0(v24, 0, 0x208u);
  STRU::STRU((STRU *)v21, v24, 0x104u);
  memset_0(v25, 0, 0x208u);
  STRU::STRU((STRU *)v22, v25, 0x104u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( !a3 || !*a3 )
  {
    v11 = -2147024883;
    goto LABEL_45;
  }
  v8 = 0;
  if ( a4 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) && GetLastError() != 1008 || !ImpersonateLoggedOnUser(a4) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_45;
    }
    v8 = 1;
  }
  v11 = STRU::Copy((STRU *)v21, a3);
  if ( v11 >= 0 )
  {
    Str = STRU::QueryStr((STRU *)v21);
    if ( Str[STRU::QueryCCH((STRU *)v21) - 1] == 92 || (v11 = STRU::Append((STRU *)v21, L"\\"), v11 >= 0) )
    {
      v11 = STRU::Append((STRU *)v21, L"*");
      if ( v11 >= 0 )
      {
        v13 = STRU::QueryStr((STRU *)v21);
        FirstFileW = FindFirstFileW(v13, &FindFileData);
        if ( FirstFileW == (HANDLE)-1LL )
        {
          v15 = GetLastError();
          v11 = 0;
          if ( v15 != 5 )
            v11 = v15;
          if ( v11 > 0 )
            v11 = (unsigned __int16)v11 | 0x80070000;
        }
        else
        {
          do
          {
            if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
            {
              v16 = FindFileData.cFileName[0] - 46;
              if ( FindFileData.cFileName[0] == 46 )
                v16 = FindFileData.cFileName[1];
              if ( v16 )
              {
                v17 = FindFileData.cFileName[0] - 46;
                if ( FindFileData.cFileName[0] == 46 )
                {
                  v17 = FindFileData.cFileName[1] - 46;
                  if ( FindFileData.cFileName[1] == 46 )
                    v17 = FindFileData.cFileName[2];
                }
                if ( v17 )
                {
                  v11 = STRU::Copy((STRU *)v22, a2);
                  if ( v11 < 0 )
                    goto LABEL_36;
                  v11 = STRU::Append((STRU *)v22, L"/");
                  if ( v11 < 0 )
                    goto LABEL_36;
                  v11 = STRU::Append((STRU *)v22, FindFileData.cFileName);
                  if ( v11 < 0 )
                    goto LABEL_36;
                  if ( !MULTISZ::Append(a5, (struct STRU *)v22) )
                  {
                    v18 = GetLastError();
                    v11 = v18;
                    if ( v18 <= 0 )
                      goto LABEL_36;
                    goto LABEL_35;
                  }
                }
              }
            }
          }
          while ( FindNextFileW(FirstFileW, &FindFileData) );
          v18 = GetLastError();
          if ( !v18 )
          {
            v11 = -2147024883;
            goto LABEL_36;
          }
          if ( v18 != 18 )
          {
            if ( v18 <= 0 )
            {
              v11 = v18;
              goto LABEL_36;
            }
LABEL_35:
            v11 = (unsigned __int16)v18 | 0x80070000;
          }
LABEL_36:
          FindClose(FirstFileW);
        }
      }
    }
  }
  if ( v8 )
  {
    if ( TokenHandle )
      SetThreadToken(0, TokenHandle);
    else
      RevertToSelf();
  }
LABEL_45:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  STRU::~STRU((STRU *)v22);
  STRU::~STRU((STRU *)v21);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180047044  mov     [rsp-8+arg_0], rbx
0x180047049  push    rbp
0x18004704a  push    rsi
0x18004704b  push    rdi
0x18004704c  push    r12
0x18004704e  push    r13
0x180047050  push    r14
0x180047052  push    r15
0x180047054  lea     rbp, [rsp-620h]
0x18004705c  sub     rsp, 720h
0x180047063  mov     rax, cs:__security_cookie
0x18004706a  xor     rax, rsp
0x18004706d  mov     [rbp+650h+var_40], rax
0x180047074  mov     r15, [rbp+650h+arg_20]
0x18004707b  lea     rcx, [rbp+650h+var_460]; void *
0x180047082  mov     rbx, r8
0x180047085  mov     r14, rdx
0x180047088  mov     r12d, 208h
0x18004708e  xor     r13d, r13d
0x180047091  mov     r8d, r12d; Size
0x180047094  mov     [rsp+750h+TokenHandle], r13
0x180047099  xor     edx, edx; Val
0x18004709b  mov     rdi, r9
0x18004709e  call    memset_0
0x1800470a3  mov     esi, 104h
0x1800470a8  lea     rdx, [rbp+650h+var_460]
0x1800470af  mov     r8d, esi
0x1800470b2  lea     rcx, [rsp+750h+var_728]
0x1800470b7  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800470bd  mov     r8d, r12d; Size
0x1800470c0  lea     rcx, [rbp+650h+var_250]; void *
0x1800470c7  xor     edx, edx; Val
0x1800470c9  call    memset_0
0x1800470ce  mov     r8d, esi
0x1800470d1  lea     rdx, [rbp+650h+var_250]
0x1800470d8  lea     rcx, [rsp+750h+var_6F0]
0x1800470dd  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800470e3  xor     edx, edx; Val
0x1800470e5  lea     r8d, [r12+48h]; Size
0x1800470ea  lea     rcx, [rbp+650h+FindFileData]; void *
0x1800470ee  call    memset_0
0x1800470f3  test    rbx, rbx
0x1800470f6  jz      loc_180047330
0x1800470fc  cmp     [rbx], r13w
0x180047100  jz      loc_180047330
0x180047106  lea     r12d, [r13+1]
0x18004710a  mov     esi, r13d
0x18004710d  test    rdi, rdi
0x180047110  jz      short loc_18004716C
0x180047112  call    cs:__imp_GetCurrentThread
0x180047118  lea     r9, [rsp+750h+TokenHandle]; TokenHandle
0x18004711d  mov     r8d, r12d; OpenAsSelf
0x180047120  mov     rcx, rax; ThreadHandle
0x180047123  lea     edx, [r13+4]; DesiredAccess
0x180047127  call    cs:__imp_OpenThreadToken
0x18004712d  test    eax, eax
0x18004712f  jnz     short loc_18004715C
0x180047131  call    cs:__imp_GetLastError
0x180047137  cmp     eax, 3F0h
0x18004713c  jz      short loc_18004715C
0x18004713e  call    cs:__imp_GetLastError
0x180047144  mov     ebx, eax
0x180047146  test    eax, eax
0x180047148  jle     loc_180047335
0x18004714e  movzx   ebx, ax
0x180047151  or      ebx, 80070000h
0x180047157  jmp     loc_180047335
0x18004715c  mov     rcx, rdi; hToken
0x18004715f  call    cs:__imp_ImpersonateLoggedOnUser
0x180047165  test    eax, eax
0x180047167  jz      short loc_18004713E
0x180047169  mov     esi, r12d
0x18004716c  mov     rdx, rbx
0x18004716f  lea     rcx, [rsp+750h+var_728]
0x180047174  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004717a  mov     ebx, eax
0x18004717c  test    eax, eax
0x18004717e  js      loc_180047303
0x180047184  lea     rcx, [rsp+750h+var_728]
0x180047189  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18004718f  lea     rcx, [rsp+750h+var_728]
0x180047194  mov     rbx, rax
0x180047197  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18004719d  sub     eax, r12d
0x1800471a0  cmp     word ptr [rbx+rax*2], 5Ch ; '\'
0x1800471a5  jz      short loc_1800471C3
0x1800471a7  lea     rdx, asc_18005F940; "\\"
0x1800471ae  lea     rcx, [rsp+750h+var_728]
0x1800471b3  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800471b9  mov     ebx, eax
0x1800471bb  test    eax, eax
0x1800471bd  js      loc_180047303
0x1800471c3  lea     rdx, asc_180060FF4; "*"
0x1800471ca  lea     rcx, [rsp+750h+var_728]
0x1800471cf  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800471d5  mov     ebx, eax
0x1800471d7  test    eax, eax
0x1800471d9  js      loc_180047303
0x1800471df  lea     rcx, [rsp+750h+var_728]
0x1800471e4  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800471ea  mov     rcx, rax; lpFileName
0x1800471ed  lea     rdx, [rbp+650h+FindFileData]; lpFindFileData
0x1800471f1  call    cs:__imp_FindFirstFileW
0x1800471f7  mov     rdi, rax
0x1800471fa  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800471fe  jnz     short loc_180047225
0x180047200  call    cs:__imp_GetLastError
0x180047206  cmp     eax, 5
0x180047209  mov     ebx, r13d
0x18004720c  cmovnz  ebx, eax
0x18004720f  test    ebx, ebx
0x180047211  jle     loc_180047303
0x180047217  movzx   ebx, bx
0x18004721a  or      ebx, 80070000h
0x180047220  jmp     loc_180047303
0x180047225  mov     r12d, 2Eh ; '.'
0x18004722b  test    byte ptr [rbp+650h+FindFileData.dwFileAttributes], 10h
0x18004722f  jz      loc_1800472BF
0x180047235  movzx   edx, [rbp+650h+FindFileData.cFileName]
0x180047239  sub     edx, r12d
0x18004723c  jnz     short loc_180047248
0x18004723e  movzx   edx, [rbp+650h+FindFileData.cFileName+2]
0x180047242  movzx   ecx, r13w
0x180047246  sub     edx, ecx
0x180047248  test    edx, edx
0x18004724a  jz      short loc_1800472BF
0x18004724c  movzx   edx, [rbp+650h+FindFileData.cFileName]
0x180047250  sub     edx, r12d
0x180047253  jnz     short loc_180047268
0x180047255  movzx   edx, [rbp+650h+FindFileData.cFileName+2]
0x180047259  sub     edx, r12d
0x18004725c  jnz     short loc_180047268
0x18004725e  movzx   edx, [rbp+650h+FindFileData.cFileName+4]
0x180047262  movzx   ecx, r13w
0x180047266  sub     edx, ecx
0x180047268  test    edx, edx
0x18004726a  jz      short loc_1800472BF
0x18004726c  mov     rdx, r14
0x18004726f  lea     rcx, [rsp+750h+var_6F0]
0x180047274  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18004727a  mov     ebx, eax
0x18004727c  test    eax, eax
0x18004727e  js      short loc_1800472FA
0x180047280  lea     rdx, asc_18005F044; "/"
0x180047287  lea     rcx, [rsp+750h+var_6F0]
0x18004728c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180047292  mov     ebx, eax
0x180047294  test    eax, eax
0x180047296  js      short loc_1800472FA
0x180047298  lea     rdx, [rbp+650h+FindFileData.cFileName]
0x18004729c  lea     rcx, [rsp+750h+var_6F0]
0x1800472a1  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800472a7  mov     ebx, eax
0x1800472a9  test    eax, eax
0x1800472ab  js      short loc_1800472FA
0x1800472ad  lea     rdx, [rsp+750h+var_6F0]
0x1800472b2  mov     rcx, r15
0x1800472b5  call    cs:__imp_?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z; MULTISZ::Append(STRU &)
0x1800472bb  test    eax, eax
0x1800472bd  jz      short loc_1800472E5
0x1800472bf  lea     rdx, [rbp+650h+FindFileData]; lpFindFileData
0x1800472c3  mov     rcx, rdi; hFindFile
0x1800472c6  call    cs:__imp_FindNextFileW
0x1800472cc  test    eax, eax
0x1800472ce  jnz     loc_18004722B
0x1800472d4  call    cs:__imp_GetLastError
0x1800472da  test    eax, eax
0x1800472dc  jnz     short loc_18004731B
0x1800472de  mov     ebx, 8007000Dh
0x1800472e3  jmp     short loc_1800472FA
0x1800472e5  call    cs:__imp_GetLastError
0x1800472eb  mov     ebx, eax
0x1800472ed  test    eax, eax
0x1800472ef  jle     short loc_1800472FA
0x1800472f1  movzx   ebx, ax
0x1800472f4  or      ebx, 80070000h
0x1800472fa  mov     rcx, rdi; hFindFile
0x1800472fd  call    cs:__imp_FindClose
0x180047303  test    esi, esi
0x180047305  jz      short loc_180047335
0x180047307  mov     rdx, [rsp+750h+TokenHandle]; Token
0x18004730c  test    rdx, rdx
0x18004730f  jz      short loc_180047328
0x180047311  xor     ecx, ecx; Thread
0x180047313  call    cs:__imp_SetThreadToken
0x180047319  jmp     short loc_180047335
0x18004731b  cmp     eax, 12h
0x18004731e  jz      short loc_1800472FA
0x180047320  test    eax, eax
0x180047322  jg      short loc_1800472F1
0x180047324  mov     ebx, eax
0x180047326  jmp     short loc_1800472FA
0x180047328  call    cs:__imp_RevertToSelf
0x18004732e  jmp     short loc_180047335
0x180047330  mov     ebx, 8007000Dh
0x180047335  mov     rcx, [rsp+750h+TokenHandle]; hObject
0x18004733a  test    rcx, rcx
0x18004733d  jz      short loc_18004734A
0x18004733f  call    cs:__imp_CloseHandle
0x180047345  mov     [rsp+750h+TokenHandle], r13
0x18004734a  lea     rcx, [rsp+750h+var_6F0]
0x18004734f  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180047355  lea     rcx, [rsp+750h+var_728]
0x18004735a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180047360  mov     eax, ebx
0x180047362  mov     rcx, [rbp+650h+var_40]
0x180047369  xor     rcx, rsp; StackCookie
0x18004736c  call    __security_check_cookie
0x180047371  mov     rbx, [rsp+750h+arg_0]
0x180047379  add     rsp, 720h
0x180047380  pop     r15
0x180047382  pop     r14
0x180047384  pop     r13
0x180047386  pop     r12
0x180047388  pop     rdi
0x180047389  pop     rsi
0x18004738a  pop     rbp
0x18004738b  retn
```
