# CheckIfShortFileName(ushort const *,void *,int *)

- ea: `0x180007a38`
- end: `0x180007cee`
- name: `?CheckIfShortFileName@@YAJPEBGPEAXPEAH@Z`
- size: `694`
- prototype: `wchar_t *__fastcall(wchar_t *Str, HANDLE Token, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800070a0`

## callees

- `0x180007a38`
- `0x18003439a`
- `0x1800343f0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180007bdd`
- `msvcrt!_wcsicmp` at `0x180007bdd`
- `msvcrt!wcsrchr` at `0x180007bcf`
- `msvcrt!wcsrchr` at `0x180007bcf`
- `msvcrt!wcschr` at `0x180007a8a`
- `msvcrt!wcschr` at `0x180007b18`
- `msvcrt!wcschr` at `0x180007c05`
- `msvcrt!wcschr` at `0x180007a8a`
- `msvcrt!wcschr` at `0x180007b18`
- `msvcrt!wcschr` at `0x180007c05`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180007b8f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180007b8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c42`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180007ba0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180007ba0`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180007bc1`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180007bc1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007bae`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180007bae`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007bec`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007bf7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007c1d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007c28`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007cb1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007cbc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007bec`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007bf7`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007c1d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007c28`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007cb1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007cbc`
- `iisutil!PuDbgPrint` at `0x180007c83`
- `iisutil!PuDbgPrint` at `0x180007c83`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007b5b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007b7c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007b5b`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180007b7c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007ade`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007b0a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007ade`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180007b0a`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180007b46`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180007b46`
- `iisutil!MakePathCanonicalizationProof` at `0x180007b69`
- `iisutil!MakePathCanonicalizationProof` at `0x180007b69`

## string_xrefs

- `0x180007c65`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3context.cxx`

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
0x180007a38  mov     [rsp-8+arg_18], rbx
0x180007a3d  push    rbp
0x180007a3e  push    rsi
0x180007a3f  push    rdi
0x180007a40  push    r12
0x180007a42  push    r13
0x180007a44  push    r14
0x180007a46  push    r15
0x180007a48  lea     rbp, [rsp-630h]
0x180007a50  sub     rsp, 730h
0x180007a57  mov     rax, cs:__security_cookie
0x180007a5e  xor     rax, rsp
0x180007a61  mov     [rbp+660h+var_40], rax
0x180007a68  mov     r12, r8
0x180007a6b  mov     r14, rdx
0x180007a6e  mov     r15, rcx
0x180007a71  xor     edx, edx; Val
0x180007a73  mov     r8d, 250h; Size
0x180007a79  lea     rcx, [rbp+660h+FindFileData]; void *
0x180007a7d  call    memset_0
0x180007a82  mov     edx, 7Eh ; '~'; Ch
0x180007a87  mov     rcx, r15; Str
0x180007a8a  call    cs:__imp_wcschr
0x180007a90  xor     r13d, r13d
0x180007a93  mov     [r12], r13d
0x180007a97  test    rax, rax
0x180007a9a  jz      loc_180007CC4
0x180007aa0  lea     rbx, [rax+2]
0x180007aa4  cmp     word ptr [rbx], 30h ; '0'
0x180007aa8  jb      loc_180007BFD
0x180007aae  cmp     word ptr [rbx], 39h ; '9'
0x180007ab2  ja      loc_180007BFD
0x180007ab8  xor     edx, edx; Val
0x180007aba  lea     rcx, [rbp+660h+var_460]; void *
0x180007ac1  mov     r8d, 208h; Size
0x180007ac7  call    memset_0
0x180007acc  mov     r8d, 104h
0x180007ad2  lea     rdx, [rbp+660h+var_460]
0x180007ad9  lea     rcx, [rsp+760h+var_6E8]
0x180007ade  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180007ae4  xor     edx, edx; Val
0x180007ae6  lea     rcx, [rbp+660h+var_250]; void *
0x180007aed  mov     r8d, 208h; Size
0x180007af3  call    memset_0
0x180007af8  mov     r8d, 104h
0x180007afe  lea     rdx, [rbp+660h+var_250]
0x180007b05  lea     rcx, [rsp+760h+var_720]
0x180007b0a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180007b10  mov     edx, 5Ch ; '\'; Ch
0x180007b15  mov     rcx, rbx; Str
0x180007b18  call    cs:__imp_wcschr
0x180007b1e  test    rax, rax
0x180007b21  jnz     short loc_180007B35
0x180007b23  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007b27  inc     rax
0x180007b2a  cmp     [rbx+rax*2], r13w
0x180007b2f  jnz     short loc_180007B27
0x180007b31  lea     rax, [rbx+rax*2]
0x180007b35  sub     rax, r15
0x180007b38  lea     rcx, [rsp+760h+var_6E8]
0x180007b3d  sar     rax, 1
0x180007b40  mov     rdx, r15
0x180007b43  mov     r8d, eax
0x180007b46  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180007b4c  mov     edi, eax
0x180007b4e  test    eax, eax
0x180007b50  js      loc_180007CAC
0x180007b56  lea     rcx, [rsp+760h+var_6E8]
0x180007b5b  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180007b61  mov     rcx, rax
0x180007b64  lea     rdx, [rsp+760h+var_720]
0x180007b69  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180007b6f  test    eax, eax
0x180007b71  js      loc_180007C16
0x180007b77  lea     rcx, [rsp+760h+var_720]
0x180007b7c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180007b82  mov     rdi, rax
0x180007b85  test    r14, r14
0x180007b88  jz      short loc_180007B99
0x180007b8a  mov     rdx, r14; Token
0x180007b8d  xor     ecx, ecx; Thread
0x180007b8f  call    cs:__imp_SetThreadToken
0x180007b95  test    eax, eax
0x180007b97  jz      short loc_180007C10
0x180007b99  lea     rdx, [rbp+660h+FindFileData]; lpFindFileData
0x180007b9d  mov     rcx, rdi; lpFileName
0x180007ba0  call    cs:__imp_FindFirstFileW
0x180007ba6  mov     rsi, rax
0x180007ba9  test    r14, r14
0x180007bac  jz      short loc_180007BB4
0x180007bae  call    cs:__imp_RevertToSelf
0x180007bb4  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180007bb8  jz      loc_180007C42
0x180007bbe  mov     rcx, rsi; hFindFile
0x180007bc1  call    cs:__imp_FindClose
0x180007bc7  mov     edx, 5Ch ; '\'; Ch
0x180007bcc  mov     rcx, rdi; Str
0x180007bcf  call    cs:__imp_wcsrchr
0x180007bd5  lea     rcx, [rbp+660h+FindFileData.cFileName]; String1
0x180007bd9  lea     rdx, [rax+2]; String2
0x180007bdd  call    cs:__imp__wcsicmp
0x180007be3  test    eax, eax
0x180007be5  jnz     short loc_180007C35
0x180007be7  lea     rcx, [rsp+760h+var_720]
0x180007bec  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007bf2  lea     rcx, [rsp+760h+var_6E8]
0x180007bf7  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007bfd  mov     edx, 7Eh ; '~'; Ch
0x180007c02  mov     rcx, rbx; Str
0x180007c05  call    cs:__imp_wcschr
0x180007c0b  jmp     loc_180007A97
0x180007c10  call    cs:__imp_GetLastError
0x180007c16  mov     ebx, eax
0x180007c18  lea     rcx, [rsp+760h+var_720]
0x180007c1d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007c23  lea     rcx, [rsp+760h+var_6E8]
0x180007c28  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007c2e  mov     eax, ebx
0x180007c30  jmp     loc_180007CC4
0x180007c35  mov     dword ptr [r12], 1
0x180007c3d  mov     ebx, r13d
0x180007c40  jmp     short loc_180007C18
0x180007c42  call    cs:__imp_GetLastError
0x180007c48  test    byte ptr cs:g_dwDebugFlags, 3
0x180007c4f  mov     ebx, eax
0x180007c51  jz      short loc_180007C89
0x180007c53  mov     rcx, cs:g_pDebug
0x180007c5a  lea     r9, aCheckifshortfi; "CheckIfShortFileName"
0x180007c61  mov     [rsp+760h+var_730], eax
0x180007c65  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180007c6c  lea     rax, aFindfirstFaile; "FindFirst failed!! - \"%s\", error %d\n"
0x180007c73  mov     [rsp+760h+var_738], rdi
0x180007c78  mov     r8d, 0D1h
0x180007c7e  mov     [rsp+760h+var_740], rax
0x180007c83  call    cs:__imp_PuDbgPrint
0x180007c89  lea     eax, [rbx-2]
0x180007c8c  cmp     eax, 1
0x180007c8f  jbe     short loc_180007C3D
0x180007c91  cmp     ebx, 7Bh ; '{'
0x180007c94  jz      short loc_180007C3D
0x180007c96  test    ebx, ebx
0x180007c98  jle     loc_180007C18
0x180007c9e  movzx   ebx, bx
0x180007ca1  or      ebx, 80070000h
0x180007ca7  jmp     loc_180007C18
0x180007cac  lea     rcx, [rsp+760h+var_720]
0x180007cb1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007cb7  lea     rcx, [rsp+760h+var_6E8]
0x180007cbc  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007cc2  mov     eax, edi
0x180007cc4  mov     rcx, [rbp+660h+var_40]
0x180007ccb  xor     rcx, rsp; StackCookie
0x180007cce  call    __security_check_cookie
0x180007cd3  mov     rbx, [rsp+760h+arg_18]
0x180007cdb  add     rsp, 730h
0x180007ce2  pop     r15
0x180007ce4  pop     r14
0x180007ce6  pop     r13
0x180007ce8  pop     r12
0x180007cea  pop     rdi
0x180007ceb  pop     rsi
0x180007cec  pop     rbp
0x180007ced  retn
```
