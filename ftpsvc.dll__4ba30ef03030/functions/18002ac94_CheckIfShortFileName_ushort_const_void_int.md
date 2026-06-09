# CheckIfShortFileName(ushort const *,void *,int *)

- ea: `0x18002ac94`
- end: `0x18002af53`
- name: `?CheckIfShortFileName@@YAJPEBGPEAXPEAH@Z`
- size: `703`
- prototype: `wchar_t *__fastcall(wchar_t *Str, HANDLE Token, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18000fdd8`

## callees

- `0x18002ac94`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18002ae1a`
- `msvcrt!wcsrchr` at `0x18002ae1a`
- `msvcrt!wcschr` at `0x18002ace6`
- `msvcrt!wcschr` at `0x18002ad72`
- `msvcrt!wcschr` at `0x18002ae5a`
- `msvcrt!wcschr` at `0x18002ace6`
- `msvcrt!wcschr` at `0x18002ad72`
- `msvcrt!wcschr` at `0x18002ae5a`
- `msvcrt!_wcsicmp` at `0x18002ae31`
- `msvcrt!_wcsicmp` at `0x18002ae31`
- `KERNEL32!FindFirstFileW` at `0x18002adeb`
- `KERNEL32!FindFirstFileW` at `0x18002adeb`
- `KERNEL32!FindClose` at `0x18002ae0c`
- `KERNEL32!FindClose` at `0x18002ae0c`
- `KERNEL32!GetLastError` at `0x18002ae93`
- `KERNEL32!GetLastError` at `0x18002aecb`
- `KERNEL32!GetLastError` at `0x18002ae93`
- `KERNEL32!GetLastError` at `0x18002aecb`
- `ADVAPI32!SetThreadToken` at `0x18002add6`
- `ADVAPI32!SetThreadToken` at `0x18002add6`
- `ADVAPI32!RevertToSelf` at `0x18002adf9`
- `ADVAPI32!RevertToSelf` at `0x18002adf9`
- `iisutil!MakePathCanonicalizationProof` at `0x18002adb9`
- `iisutil!MakePathCanonicalizationProof` at `0x18002adb9`
- `iisutil!PuDbgPrint` at `0x18002af0c`
- `iisutil!PuDbgPrint` at `0x18002af0c`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002ada0`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18002ada0`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002ad36`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002ad63`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002ad36`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002ad63`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002ae40`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002ae4c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002aea1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002aead`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002af3a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002af46`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002ae40`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002ae4c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002aea1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002aead`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002af3a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002af46`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
wchar_t *__fastcall CheckIfShortFileName(wchar_t *Str, HANDLE Token, int *a3)
{
  wchar_t *result; // rax
  const wchar_t *v7; // rbx
  wchar_t *v8; // rax
  __int64 v9; // rax
  int v10; // edi
  signed int PathCanonicalizationProof; // eax
  const WCHAR *v12; // rdi
  HANDLE FirstFileW; // rsi
  wchar_t *v14; // rax
  signed int v15; // ebx
  DWORD LastError; // eax
  _BYTE v17[32]; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpFileName; // [rsp+60h] [rbp-A0h]
  _BYTE v19[32]; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v20; // [rsp+98h] [rbp-68h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v22[264]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v23[264]; // [rsp+510h] [rbp+410h] BYREF

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
    memset_0(v22, 0, 0x208u);
    STRU::STRU((STRU *)v19, v22, 0x104u);
    memset_0(v23, 0, 0x208u);
    STRU::STRU((STRU *)v17, v23, 0x104u);
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
    PathCanonicalizationProof = MakePathCanonicalizationProof(v20, (struct STRU *)v17);
    if ( PathCanonicalizationProof < 0 )
      goto LABEL_22;
    v12 = lpFileName;
    if ( Token && !SetThreadToken(0, Token) )
    {
      PathCanonicalizationProof = GetLastError();
LABEL_22:
      v15 = PathCanonicalizationProof;
      goto LABEL_23;
    }
    FirstFileW = FindFirstFileW(v12, &FindFileData);
    if ( Token )
      RevertToSelf();
    if ( FirstFileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\iisrearc\\ftp\\server\\ftp_util\\ftp_util.cxx",
          1245,
          "CheckIfShortFileName",
          "FindFirst failed!! - \"%s\", error %d\n",
          (const char *)v12,
          LastError);
      if ( (unsigned int)(v15 - 2) > 1 && v15 != 123 )
      {
        if ( v15 > 0 )
          v15 = (unsigned __int16)v15 | 0x80070000;
        goto LABEL_23;
      }
LABEL_25:
      v15 = 0;
LABEL_23:
      STRU::~STRU(v17);
      STRU::~STRU(v19);
      return (wchar_t *)(unsigned int)v15;
    }
    FindClose(FirstFileW);
    v14 = wcsrchr(v12, 0x5Cu);
    if ( !v14 )
    {
      v15 = -2147467259;
      goto LABEL_23;
    }
    if ( _wcsicmp(FindFileData.cFileName, v14 + 1) )
    {
      *a3 = 1;
      goto LABEL_25;
    }
    STRU::~STRU(v17);
    STRU::~STRU(v19);
LABEL_18:
    result = wcschr(v7, 0x7Eu);
  }
  STRU::~STRU(v17);
  STRU::~STRU(v19);
  return (wchar_t *)(unsigned int)v10;
}

```

## disassembly

```asm
0x18002ac94  mov     [rsp-8+arg_18], rbx
0x18002ac99  push    rbp
0x18002ac9a  push    rsi
0x18002ac9b  push    rdi
0x18002ac9c  push    r12
0x18002ac9e  push    r13
0x18002aca0  push    r14
0x18002aca2  push    r15
0x18002aca4  lea     rbp, [rsp-630h]
0x18002acac  sub     rsp, 730h
0x18002acb3  mov     rax, cs:__security_cookie
0x18002acba  xor     rax, rsp
0x18002acbd  mov     [rbp+660h+var_40], rax
0x18002acc4  mov     r12, r8
0x18002acc7  mov     r14, rdx
0x18002acca  mov     r15, rcx
0x18002accd  xor     edx, edx; Val
0x18002accf  mov     r8d, 250h; Size
0x18002acd5  lea     rcx, [rbp+660h+FindFileData]; void *
0x18002acd9  call    memset_0
0x18002acde  mov     edx, 7Eh ; '~'; Ch
0x18002ace3  mov     rcx, r15; Str
0x18002ace6  call    cs:__imp_wcschr
0x18002acec  xor     r13d, r13d
0x18002acef  mov     [r12], r13d
0x18002acf3  jmp     loc_18002AE60
0x18002acf8  lea     rbx, [rax+2]
0x18002acfc  cmp     word ptr [rbx], 30h ; '0'
0x18002ad00  jb      loc_18002AE52
0x18002ad06  cmp     word ptr [rbx], 39h ; '9'
0x18002ad0a  ja      loc_18002AE52
0x18002ad10  xor     edx, edx; Val
0x18002ad12  mov     r8d, 208h; Size
0x18002ad18  lea     rcx, [rbp+660h+var_460]; void *
0x18002ad1f  call    memset_0
0x18002ad24  mov     r8d, 104h
0x18002ad2a  lea     rdx, [rbp+660h+var_460]
0x18002ad31  lea     rcx, [rsp+760h+var_6E8]
0x18002ad36  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002ad3c  nop
0x18002ad3d  xor     edx, edx; Val
0x18002ad3f  mov     r8d, 208h; Size
0x18002ad45  lea     rcx, [rbp+660h+var_250]; void *
0x18002ad4c  call    memset_0
0x18002ad51  mov     r8d, 104h
0x18002ad57  lea     rdx, [rbp+660h+var_250]
0x18002ad5e  lea     rcx, [rsp+760h+var_720]
0x18002ad63  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002ad69  nop
0x18002ad6a  mov     edx, 5Ch ; '\'; Ch
0x18002ad6f  mov     rcx, rbx; Str
0x18002ad72  call    cs:__imp_wcschr
0x18002ad78  test    rax, rax
0x18002ad7b  jnz     short loc_18002AD8F
0x18002ad7d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ad81  inc     rax
0x18002ad84  cmp     [rbx+rax*2], r13w
0x18002ad89  jnz     short loc_18002AD81
0x18002ad8b  lea     rax, [rbx+rax*2]
0x18002ad8f  sub     rax, r15
0x18002ad92  sar     rax, 1
0x18002ad95  mov     r8d, eax
0x18002ad98  mov     rdx, r15
0x18002ad9b  lea     rcx, [rsp+760h+var_6E8]
0x18002ada0  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18002ada6  mov     edi, eax
0x18002ada8  test    eax, eax
0x18002adaa  js      loc_18002AF35
0x18002adb0  lea     rdx, [rsp+760h+var_720]
0x18002adb5  mov     rcx, [rbp+660h+var_6C8]
0x18002adb9  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x18002adbf  test    eax, eax
0x18002adc1  js      loc_18002AE9A
0x18002adc7  mov     rdi, [rsp+760h+lpFileName]
0x18002adcc  test    r14, r14
0x18002adcf  jz      short loc_18002ADE4
0x18002add1  mov     rdx, r14; Token
0x18002add4  xor     ecx, ecx; Thread
0x18002add6  call    cs:__imp_SetThreadToken
0x18002addc  test    eax, eax
0x18002adde  jz      loc_18002AE93
0x18002ade4  lea     rdx, [rbp+660h+FindFileData]; lpFindFileData
0x18002ade8  mov     rcx, rdi; lpFileName
0x18002adeb  call    cs:__imp_FindFirstFileW
0x18002adf1  mov     rsi, rax
0x18002adf4  test    r14, r14
0x18002adf7  jz      short loc_18002ADFF
0x18002adf9  call    cs:__imp_RevertToSelf
0x18002adff  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18002ae03  jz      loc_18002AECB
0x18002ae09  mov     rcx, rsi; hFindFile
0x18002ae0c  call    cs:__imp_FindClose
0x18002ae12  mov     edx, 5Ch ; '\'; Ch
0x18002ae17  mov     rcx, rdi; Str
0x18002ae1a  call    cs:__imp_wcsrchr
0x18002ae20  test    rax, rax
0x18002ae23  jz      loc_18002AEC4
0x18002ae29  lea     rdx, [rax+2]; String2
0x18002ae2d  lea     rcx, [rbp+660h+FindFileData.cFileName]; String1
0x18002ae31  call    cs:__imp__wcsicmp
0x18002ae37  test    eax, eax
0x18002ae39  jnz     short loc_18002AEB7
0x18002ae3b  lea     rcx, [rsp+760h+var_720]
0x18002ae40  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002ae46  nop
0x18002ae47  lea     rcx, [rsp+760h+var_6E8]
0x18002ae4c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002ae52  mov     edx, 7Eh ; '~'; Ch
0x18002ae57  mov     rcx, rbx; Str
0x18002ae5a  call    cs:__imp_wcschr
0x18002ae60  test    rax, rax
0x18002ae63  jnz     loc_18002ACF8
0x18002ae69  mov     rcx, [rbp+660h+var_40]
0x18002ae70  xor     rcx, rsp; StackCookie
0x18002ae73  call    __security_check_cookie
0x18002ae78  mov     rbx, [rsp+760h+arg_18]
0x18002ae80  add     rsp, 730h
0x18002ae87  pop     r15
0x18002ae89  pop     r14
0x18002ae8b  pop     r13
0x18002ae8d  pop     r12
0x18002ae8f  pop     rdi
0x18002ae90  pop     rsi
0x18002ae91  pop     rbp
0x18002ae92  retn
0x18002ae93  call    cs:__imp_GetLastError
0x18002ae99  nop
0x18002ae9a  mov     ebx, eax
0x18002ae9c  lea     rcx, [rsp+760h+var_720]
0x18002aea1  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002aea7  nop
0x18002aea8  lea     rcx, [rsp+760h+var_6E8]
0x18002aead  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002aeb3  mov     eax, ebx
0x18002aeb5  jmp     short loc_18002AE69
0x18002aeb7  mov     dword ptr [r12], 1
0x18002aebf  mov     ebx, r13d
0x18002aec2  jmp     short loc_18002AE9C
0x18002aec4  mov     ebx, 80004005h
0x18002aec9  jmp     short loc_18002AE9C
0x18002aecb  call    cs:__imp_GetLastError
0x18002aed1  mov     ebx, eax
0x18002aed3  test    byte ptr cs:g_dwDebugFlags, 3
0x18002aeda  jz      short loc_18002AF12
0x18002aedc  mov     [rsp+760h+var_730], eax
0x18002aee0  mov     [rsp+760h+var_738], rdi
0x18002aee5  lea     rax, aFindfirstFaile; "FindFirst failed!! - \"%s\", error %d\n"
0x18002aeec  mov     [rsp+760h+var_740], rax
0x18002aef1  lea     r9, aCheckifshortfi; "CheckIfShortFileName"
0x18002aef8  mov     r8d, 4DDh
0x18002aefe  lea     rdx, aInetsrvIisIisr_12; "inetsrv\\iis\\iisrearc\\ftp\\server\\ft"...
0x18002af05  mov     rcx, cs:g_pDebug
0x18002af0c  call    cs:__imp_PuDbgPrint
0x18002af12  lea     eax, [rbx-2]
0x18002af15  cmp     eax, 1
0x18002af18  jbe     short loc_18002AEBF
0x18002af1a  cmp     ebx, 7Bh ; '{'
0x18002af1d  jz      short loc_18002AEBF
0x18002af1f  test    ebx, ebx
0x18002af21  jle     loc_18002AE9C
0x18002af27  movzx   ebx, bx
0x18002af2a  or      ebx, 80070000h
0x18002af30  jmp     loc_18002AE9C
0x18002af35  lea     rcx, [rsp+760h+var_720]
0x18002af3a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002af40  nop
0x18002af41  lea     rcx, [rsp+760h+var_6E8]
0x18002af46  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18002af4c  mov     eax, edi
0x18002af4e  jmp     loc_18002AE69
```
