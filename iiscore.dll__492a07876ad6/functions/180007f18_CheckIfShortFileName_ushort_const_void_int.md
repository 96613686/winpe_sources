# CheckIfShortFileName(ushort const *,void *,int *)

- ea: `0x180007f18`
- end: `0x180008263`
- name: `?CheckIfShortFileName@@YAJPEBGPEAXPEAH@Z`
- size: `843`
- prototype: `wchar_t *__fastcall(wchar_t *Str, HANDLE Token, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180007550`

## callees

- `0x180007f18`
- `0x18003773a`
- `0x180037790`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000810f`
- `msvcrt!_wcsicmp` at `0x18000810f`
- `msvcrt!wcsrchr` at `0x1800080fb`
- `msvcrt!wcsrchr` at `0x1800080fb`
- `msvcrt!wcschr` at `0x180007f6a`
- `msvcrt!wcschr` at `0x18000800a`
- `msvcrt!wcschr` at `0x180008149`
- `msvcrt!wcschr` at `0x180007f6a`
- `msvcrt!wcschr` at `0x18000800a`
- `msvcrt!wcschr` at `0x180008149`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000809f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000809f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000815a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000819e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000815a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000819e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800080ba`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800080ba`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800080e7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800080e7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800080ce`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800080ce`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008124`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008135`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000816d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000817e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008219`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000822a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008124`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008135`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000816d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000817e`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180008219`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000822a`
- `iisutil!PuDbgPrint` at `0x1800081e5`
- `iisutil!PuDbgPrint` at `0x1800081e5`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008059`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008086`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008059`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180008086`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007fc4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007ff6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007fc4`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007ff6`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000803e`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000803e`
- `iisutil!MakePathCanonicalizationProof` at `0x18000806d`
- `iisutil!MakePathCanonicalizationProof` at `0x18000806d`

## string_xrefs

- `0x1800081c7`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3context.cxx`

## pseudocode

```c
wchar_t *__fastcall CheckIfShortFileName(wchar_t *Str, HANDLE Token, int *a3)
{
  wchar_t *result; // rax
  const wchar_t *v7; // rbx
  wchar_t *v8; // rax
  __int64 v9; // rax
  int v10; // edi
  const unsigned __int16 *v11; // rax
  signed int PathCanonicalizationProof; // eax
  const WCHAR *v13; // rdi
  HANDLE FirstFileW; // rsi
  wchar_t *v15; // rax
  signed int v16; // ebx
  DWORD LastError; // eax
  _BYTE v18[56]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v19[56]; // [rsp+78h] [rbp-88h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v21[264]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v22[264]; // [rsp+510h] [rbp+410h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  result = wcschr(Str, 0x7Eu);
  *a3 = 0;
  while ( 1 )
  {
    if ( !result )
      return result;
    v7 = result + 1;
    if ( result[1] < 0x30u || *v7 > 0x39u )
      goto LABEL_18;
    memset_0(v21, 0, 0x208u);
    STRU::STRU((STRU *)v19, v21, 0x104u);
    memset_0(v22, 0, 0x208u);
    STRU::STRU((STRU *)v18, v22, 0x104u);
    v8 = wcschr(v7, 0x5Cu);
    if ( !v8 )
    {
      v9 = -1;
      do
        ++v9;
      while ( v7[v9] );
      v8 = (wchar_t *)&v7[v9];
    }
    v10 = STRU::Copy((STRU *)v19, Str, v8 - Str);
    if ( v10 < 0 )
      break;
    v11 = STRU::QueryStr((STRU *)v19);
    PathCanonicalizationProof = MakePathCanonicalizationProof(v11, (struct STRU *)v18);
    if ( PathCanonicalizationProof < 0 )
      goto LABEL_20;
    v13 = STRU::QueryStr((STRU *)v18);
    if ( Token && !SetThreadToken(0, Token) )
    {
      PathCanonicalizationProof = GetLastError();
LABEL_20:
      v16 = PathCanonicalizationProof;
LABEL_21:
      STRU::~STRU((STRU *)v18);
      STRU::~STRU((STRU *)v19);
      return (wchar_t *)(unsigned int)v16;
    }
    FirstFileW = FindFirstFileW(v13, &FindFileData);
    if ( Token )
      RevertToSelf();
    if ( FirstFileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v16 = LastError;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\w3context.cxx",
          209,
          "CheckIfShortFileName",
          "FindFirst failed!! - \"%s\", error %d\n",
          (const char *)v13,
          LastError);
      if ( (unsigned int)(v16 - 2) > 1 && v16 != 123 )
      {
        if ( v16 > 0 )
          v16 = (unsigned __int16)v16 | 0x80070000;
        goto LABEL_21;
      }
      goto LABEL_23;
    }
    FindClose(FirstFileW);
    v15 = wcsrchr(v13, 0x5Cu);
    if ( _wcsicmp(FindFileData.cFileName, v15 + 1) )
    {
      *a3 = 1;
LABEL_23:
      v16 = 0;
      goto LABEL_21;
    }
    STRU::~STRU((STRU *)v18);
    STRU::~STRU((STRU *)v19);
LABEL_18:
    result = wcschr(v7, 0x7Eu);
  }
  STRU::~STRU((STRU *)v18);
  STRU::~STRU((STRU *)v19);
  return (wchar_t *)(unsigned int)v10;
}

```

## disassembly

```asm
0x180007f18  mov     [rsp-8+arg_18], rbx
0x180007f1d  push    rbp
0x180007f1e  push    rsi
0x180007f1f  push    rdi
0x180007f20  push    r12
0x180007f22  push    r13
0x180007f24  push    r14
0x180007f26  push    r15
0x180007f28  lea     rbp, [rsp-630h]
0x180007f30  sub     rsp, 730h
0x180007f37  mov     rax, cs:__security_cookie
0x180007f3e  xor     rax, rsp
0x180007f41  mov     [rbp+660h+var_40], rax
0x180007f48  mov     r12, r8
0x180007f4b  mov     r14, rdx
0x180007f4e  mov     r15, rcx
0x180007f51  xor     edx, edx; Val
0x180007f53  mov     r8d, 250h; Size
0x180007f59  lea     rcx, [rbp+660h+FindFileData]; void *
0x180007f5d  call    memset_0
0x180007f62  mov     edx, 7Eh ; '~'; Ch
0x180007f67  mov     rcx, r15; Str
0x180007f6a  call    cs:__imp_wcschr
0x180007f71  nop     dword ptr [rax+rax+00h]
0x180007f76  xor     r13d, r13d
0x180007f79  mov     [r12], r13d
0x180007f7d  test    rax, rax
0x180007f80  jz      loc_180008238
0x180007f86  lea     rbx, [rax+2]
0x180007f8a  cmp     word ptr [rbx], 30h ; '0'
0x180007f8e  jb      loc_180008141
0x180007f94  cmp     word ptr [rbx], 39h ; '9'
0x180007f98  ja      loc_180008141
0x180007f9e  xor     edx, edx; Val
0x180007fa0  lea     rcx, [rbp+660h+var_460]; void *
0x180007fa7  mov     r8d, 208h; Size
0x180007fad  call    memset_0
0x180007fb2  mov     r8d, 104h
0x180007fb8  lea     rdx, [rbp+660h+var_460]
0x180007fbf  lea     rcx, [rsp+760h+var_6E8]
0x180007fc4  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180007fcb  nop     dword ptr [rax+rax+00h]
0x180007fd0  xor     edx, edx; Val
0x180007fd2  lea     rcx, [rbp+660h+var_250]; void *
0x180007fd9  mov     r8d, 208h; Size
0x180007fdf  call    memset_0
0x180007fe4  mov     r8d, 104h
0x180007fea  lea     rdx, [rbp+660h+var_250]
0x180007ff1  lea     rcx, [rsp+760h+var_720]
0x180007ff6  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180007ffd  nop     dword ptr [rax+rax+00h]
0x180008002  mov     edx, 5Ch ; '\'; Ch
0x180008007  mov     rcx, rbx; Str
0x18000800a  call    cs:__imp_wcschr
0x180008011  nop     dword ptr [rax+rax+00h]
0x180008016  test    rax, rax
0x180008019  jnz     short loc_18000802D
0x18000801b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000801f  inc     rax
0x180008022  cmp     [rbx+rax*2], r13w
0x180008027  jnz     short loc_18000801F
0x180008029  lea     rax, [rbx+rax*2]
0x18000802d  sub     rax, r15
0x180008030  lea     rcx, [rsp+760h+var_6E8]
0x180008035  sar     rax, 1
0x180008038  mov     rdx, r15
0x18000803b  mov     r8d, eax
0x18000803e  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180008045  nop     dword ptr [rax+rax+00h]
0x18000804a  mov     edi, eax
0x18000804c  test    eax, eax
0x18000804e  js      loc_180008214
0x180008054  lea     rcx, [rsp+760h+var_6E8]
0x180008059  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180008060  nop     dword ptr [rax+rax+00h]
0x180008065  mov     rcx, rax
0x180008068  lea     rdx, [rsp+760h+var_720]
0x18000806d  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180008074  nop     dword ptr [rax+rax+00h]
0x180008079  test    eax, eax
0x18000807b  js      loc_180008166
0x180008081  lea     rcx, [rsp+760h+var_720]
0x180008086  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000808d  nop     dword ptr [rax+rax+00h]
0x180008092  mov     rdi, rax
0x180008095  test    r14, r14
0x180008098  jz      short loc_1800080B3
0x18000809a  mov     rdx, r14; Token
0x18000809d  xor     ecx, ecx; Thread
0x18000809f  call    cs:__imp_SetThreadToken
0x1800080a6  nop     dword ptr [rax+rax+00h]
0x1800080ab  test    eax, eax
0x1800080ad  jz      loc_18000815A
0x1800080b3  lea     rdx, [rbp+660h+FindFileData]; lpFindFileData
0x1800080b7  mov     rcx, rdi; lpFileName
0x1800080ba  call    cs:__imp_FindFirstFileW
0x1800080c1  nop     dword ptr [rax+rax+00h]
0x1800080c6  mov     rsi, rax
0x1800080c9  test    r14, r14
0x1800080cc  jz      short loc_1800080DA
0x1800080ce  call    cs:__imp_RevertToSelf
0x1800080d5  nop     dword ptr [rax+rax+00h]
0x1800080da  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800080de  jz      loc_18000819E
0x1800080e4  mov     rcx, rsi; hFindFile
0x1800080e7  call    cs:__imp_FindClose
0x1800080ee  nop     dword ptr [rax+rax+00h]
0x1800080f3  mov     edx, 5Ch ; '\'; Ch
0x1800080f8  mov     rcx, rdi; Str
0x1800080fb  call    cs:__imp_wcsrchr
0x180008102  nop     dword ptr [rax+rax+00h]
0x180008107  lea     rcx, [rbp+660h+FindFileData.cFileName]; String1
0x18000810b  lea     rdx, [rax+2]; String2
0x18000810f  call    cs:__imp__wcsicmp
0x180008116  nop     dword ptr [rax+rax+00h]
0x18000811b  test    eax, eax
0x18000811d  jnz     short loc_180008191
0x18000811f  lea     rcx, [rsp+760h+var_720]
0x180008124  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000812b  nop     dword ptr [rax+rax+00h]
0x180008130  lea     rcx, [rsp+760h+var_6E8]
0x180008135  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000813c  nop     dword ptr [rax+rax+00h]
0x180008141  mov     edx, 7Eh ; '~'; Ch
0x180008146  mov     rcx, rbx; Str
0x180008149  call    cs:__imp_wcschr
0x180008150  nop     dword ptr [rax+rax+00h]
0x180008155  jmp     loc_180007F7D
0x18000815a  call    cs:__imp_GetLastError
0x180008161  nop     dword ptr [rax+rax+00h]
0x180008166  mov     ebx, eax
0x180008168  lea     rcx, [rsp+760h+var_720]
0x18000816d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008174  nop     dword ptr [rax+rax+00h]
0x180008179  lea     rcx, [rsp+760h+var_6E8]
0x18000817e  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008185  nop     dword ptr [rax+rax+00h]
0x18000818a  mov     eax, ebx
0x18000818c  jmp     loc_180008238
0x180008191  mov     dword ptr [r12], 1
0x180008199  mov     ebx, r13d
0x18000819c  jmp     short loc_180008168
0x18000819e  call    cs:__imp_GetLastError
0x1800081a5  nop     dword ptr [rax+rax+00h]
0x1800081aa  test    byte ptr cs:g_dwDebugFlags, 3
0x1800081b1  mov     ebx, eax
0x1800081b3  jz      short loc_1800081F1
0x1800081b5  mov     rcx, cs:g_pDebug
0x1800081bc  lea     r9, aCheckifshortfi; "CheckIfShortFileName"
0x1800081c3  mov     [rsp+760h+var_730], eax
0x1800081c7  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800081ce  lea     rax, aFindfirstFaile; "FindFirst failed!! - \"%s\", error %d\n"
0x1800081d5  mov     [rsp+760h+var_738], rdi
0x1800081da  mov     r8d, 0D1h
0x1800081e0  mov     [rsp+760h+var_740], rax
0x1800081e5  call    cs:__imp_PuDbgPrint
0x1800081ec  nop     dword ptr [rax+rax+00h]
0x1800081f1  lea     eax, [rbx-2]
0x1800081f4  cmp     eax, 1
0x1800081f7  jbe     short loc_180008199
0x1800081f9  cmp     ebx, 7Bh ; '{'
0x1800081fc  jz      short loc_180008199
0x1800081fe  test    ebx, ebx
0x180008200  jle     loc_180008168
0x180008206  movzx   ebx, bx
0x180008209  or      ebx, 80070000h
0x18000820f  jmp     loc_180008168
0x180008214  lea     rcx, [rsp+760h+var_720]
0x180008219  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008220  nop     dword ptr [rax+rax+00h]
0x180008225  lea     rcx, [rsp+760h+var_6E8]
0x18000822a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180008231  nop     dword ptr [rax+rax+00h]
0x180008236  mov     eax, edi
0x180008238  mov     rcx, [rbp+660h+var_40]
0x18000823f  xor     rcx, rsp; StackCookie
0x180008242  call    __security_check_cookie
0x180008247  mov     rbx, [rsp+760h+arg_18]
0x18000824f  add     rsp, 730h
0x180008256  pop     r15
0x180008258  pop     r14
0x18000825a  pop     r13
0x18000825c  pop     r12
0x18000825e  pop     rdi
0x18000825f  pop     rsi
0x180008260  pop     rbp
0x180008261  retn
```
