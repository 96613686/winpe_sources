# GPOScripts::LaunchProcessInSession(ushort const *,ulong,_STARTUPINFOW *,_PROCESS_INFORMATION *,ulong,void *)

- ea: `0x1800950d0`
- end: `0x1800952df`
- name: `?LaunchProcessInSession@GPOScripts@@AEAAKPEBGKPEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@KPEAX@Z`
- size: `527`
- prototype: `__int64 __fastcall(GPOScripts *this, const unsigned __int16 *, int, struct _STARTUPINFOW *, struct _PROCESS_INFORMATION *lpProcessInformation, unsigned int, HANDLE hExistingToken)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180094498`
- `0x18009479c`

## callees

- `0x18000a504`
- `0x18000a52c`
- `0x18001ee6c`
- `0x18002c690`
- `0x180039148`
- `0x1800950d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009524f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009524f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009516a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18009516a`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180095293`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x180095293`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009517c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18009517c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180095129`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180095129`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800951f1`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800951f1`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800951bf`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180095245`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800951bf`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180095245`
- `profapi!__imp_CreateEnvBlock` at `0x18009520c`
- `profapi!__imp_CreateEnvBlock` at `0x18009520c`
- `profapi!__imp_DestroyEnvBlock` at `0x1800952a9`
- `profapi!__imp_DestroyEnvBlock` at `0x1800952a9`

## pseudocode

```c
__int64 __fastcall GPOScripts::LaunchProcessInSession(
        GPOScripts *this,
        const unsigned __int16 *a2,
        int a3,
        struct _STARTUPINFOW *a4,
        struct _PROCESS_INFORMATION *lpProcessInformation,
        unsigned int a6,
        HANDLE hExistingToken)
{
  __int64 v8; // rax
  unsigned __int64 v11; // r14
  HLOCAL v12; // rax
  WCHAR *v13; // rbx
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  int v16; // eax
  HANDLE hToken; // [rsp+68h] [rbp-11h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-9h] BYREF
  LPVOID lpEnvironment; // [rsp+78h] [rbp-1h] BYREF
  LPWSTR lpCommandLine; // [rsp+80h] [rbp+7h] BYREF
  _QWORD v22[2]; // [rsp+88h] [rbp+Fh] BYREF
  int TokenInformation; // [rsp+D8h] [rbp+5Fh] BYREF

  TokenInformation = a3;
  hToken = 0;
  v8 = -1;
  lpCommandLine = 0;
  v22[0] = 0;
  lpEnvironment = 0;
  do
    ++v8;
  while ( a2[v8] );
  v11 = v8 + 1;
  v12 = LocalAlloc(0x40u, 2 * (v8 + 1));
  XPtrLF<unsigned short>::operator=(&lpCommandLine, v12);
  v13 = lpCommandLine;
  if ( !lpCommandLine )
  {
    LastError = 14;
    goto LABEL_18;
  }
  StringCchCopyW(lpCommandLine, v11, a2);
  if ( *((_DWORD *)this + 4) )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x1ABu, &TokenHandle)
      || !DuplicateTokenEx(TokenHandle, 0x1ABu, 0, SecurityImpersonation, TokenPrimary, &hToken) )
    {
      LastError = GetLastError();
      XHandle::~XHandle((XHandle *)&TokenHandle);
      goto LABEL_18;
    }
    XHandle::~XHandle((XHandle *)&TokenHandle);
  }
  else if ( !DuplicateTokenEx(hExistingToken, 0x1ABu, 0, SecurityImpersonation, TokenPrimary, &hToken) )
  {
LABEL_15:
    LastError = GetLastError();
    goto LABEL_18;
  }
  XHandle::operator=(v22, hToken);
  if ( !SetTokenInformation(hToken, TokenSessionId, &TokenInformation, 4u) )
    goto LABEL_15;
  if ( !*((_DWORD *)this + 4) )
  {
    v16 = CreateEnvBlock(&lpEnvironment, hToken, 0);
    if ( v16 < 0 )
    {
      lpEnvironment = 0;
      LastError = (unsigned __int16)v16;
      goto LABEL_20;
    }
  }
  if ( !CreateProcessAsUserW(hToken, 0, v13, 0, 0, 0, 0x404u, lpEnvironment, 0, a4, lpProcessInformation) )
    goto LABEL_15;
  LastError = 0;
LABEL_18:
  if ( lpEnvironment )
    DestroyEnvBlock();
LABEL_20:
  XHandle::~XHandle((XHandle *)v22);
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&lpCommandLine);
  return LastError;
}

```

## disassembly

```asm
0x1800950d0  mov     rax, rsp
0x1800950d3  mov     [rax+8], rbx
0x1800950d7  mov     [rax+10h], rsi
0x1800950db  mov     [rax+18h], r8d
0x1800950df  push    rbp
0x1800950e0  push    rdi
0x1800950e1  push    r12
0x1800950e3  push    r14
0x1800950e5  push    r15
0x1800950e7  lea     rbp, [rax-47h]
0x1800950eb  sub     rsp, 90h
0x1800950f2  xor     r12d, r12d
0x1800950f5  mov     r15, r9
0x1800950f8  mov     [rbp+3Fh+hToken], r12
0x1800950fc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180095100  mov     [rbp+3Fh+lpCommandLine], r12
0x180095104  mov     rdi, rdx
0x180095107  mov     [rbp+3Fh+var_30], r12
0x18009510b  mov     rsi, rcx
0x18009510e  mov     [rbp+3Fh+var_40], r12
0x180095112  inc     rax
0x180095115  cmp     [rdx+rax*2], r12w
0x18009511a  jnz     short loc_180095112
0x18009511c  lea     r14, [rax+1]
0x180095120  mov     ecx, 40h ; '@'; uFlags
0x180095125  lea     rdx, [r14+r14]; uBytes
0x180095129  call    cs:__imp_LocalAlloc
0x18009512f  mov     rdx, rax
0x180095132  lea     rcx, [rbp+3Fh+lpCommandLine]
0x180095136  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x18009513b  mov     rbx, [rbp+3Fh+lpCommandLine]
0x18009513f  test    rbx, rbx
0x180095142  jnz     short loc_18009514E
0x180095144  mov     ebx, 0Eh
0x180095149  jmp     loc_1800952A0
0x18009514e  mov     r8, rdi; unsigned __int16 *
0x180095151  mov     rdx, r14; unsigned __int64
0x180095154  mov     rcx, rbx; unsigned __int16 *
0x180095157  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009515c  cmp     [rsi+10h], r12d
0x180095160  jz      loc_180095222
0x180095166  mov     [rbp+3Fh+TokenHandle], r12
0x18009516a  call    cs:__imp_GetCurrentProcess
0x180095170  lea     r8, [rbp+3Fh+TokenHandle]; TokenHandle
0x180095174  mov     edx, 1ABh; DesiredAccess
0x180095179  mov     rcx, rax; ProcessHandle
0x18009517c  call    cs:__imp_OpenProcessToken
0x180095182  test    eax, eax
0x180095184  jnz     short loc_18009519C
0x180095186  call    cs:__imp_GetLastError
0x18009518c  lea     rcx, [rbp+3Fh+TokenHandle]; this
0x180095190  mov     ebx, eax
0x180095192  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x180095197  jmp     loc_1800952A0
0x18009519c  mov     rcx, [rbp+3Fh+TokenHandle]; hExistingToken
0x1800951a0  lea     rax, [rbp+3Fh+hToken]
0x1800951a4  mov     [rsp+0B0h+phNewToken], rax; phNewToken
0x1800951a9  mov     r9d, 2; ImpersonationLevel
0x1800951af  xor     r8d, r8d; lpTokenAttributes
0x1800951b2  mov     [rsp+0B0h+TokenType], 1; TokenType
0x1800951ba  mov     edx, 1ABh; dwDesiredAccess
0x1800951bf  call    cs:__imp_DuplicateTokenEx
0x1800951c5  test    eax, eax
0x1800951c7  jz      short loc_180095186
0x1800951c9  lea     rcx, [rbp+3Fh+TokenHandle]; this
0x1800951cd  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x1800951d2  mov     rdx, [rbp+3Fh+hToken]
0x1800951d6  lea     rcx, [rbp+3Fh+var_30]
0x1800951da  call    ??4XHandle@@QEAAXPEAX@Z; XHandle::operator=(void *)
0x1800951df  mov     rcx, [rbp+3Fh+hToken]; TokenHandle
0x1800951e3  lea     r8, [rbp+3Fh+TokenInformation]; TokenInformation
0x1800951e7  mov     r9d, 4; TokenInformationLength
0x1800951ed  lea     edx, [r9+8]; TokenInformationClass
0x1800951f1  call    cs:__imp_SetTokenInformation
0x1800951f7  test    eax, eax
0x1800951f9  jz      short loc_18009524F
0x1800951fb  cmp     [rsi+10h], r12d
0x1800951ff  jnz     short loc_180095259
0x180095201  mov     rdx, [rbp+3Fh+hToken]
0x180095205  lea     rcx, [rbp+3Fh+var_40]
0x180095209  xor     r8d, r8d
0x18009520c  call    cs:__imp_CreateEnvBlock
0x180095212  test    eax, eax
0x180095214  jns     short loc_180095259
0x180095216  mov     [rbp+3Fh+var_40], r12
0x18009521a  movzx   ebx, ax
0x18009521d  jmp     loc_1800952AF
0x180095222  mov     rcx, [rbp+3Fh+hExistingToken]; hExistingToken
0x180095226  lea     rax, [rbp+3Fh+hToken]
0x18009522a  mov     [rsp+0B0h+phNewToken], rax; phNewToken
0x18009522f  mov     r9d, 2; ImpersonationLevel
0x180095235  xor     r8d, r8d; lpTokenAttributes
0x180095238  mov     [rsp+0B0h+TokenType], 1; TokenType
0x180095240  mov     edx, 1ABh; dwDesiredAccess
0x180095245  call    cs:__imp_DuplicateTokenEx
0x18009524b  test    eax, eax
0x18009524d  jnz     short loc_1800951D2
0x18009524f  call    cs:__imp_GetLastError
0x180095255  mov     ebx, eax
0x180095257  jmp     short loc_1800952A0
0x180095259  mov     rdx, [rbp+3Fh+var_40]
0x18009525d  xor     r9d, r9d; lpProcessAttributes
0x180095260  mov     rax, [rbp+3Fh+arg_20]
0x180095264  mov     r8, rbx; lpCommandLine
0x180095267  mov     rcx, [rbp+3Fh+hToken]; hToken
0x18009526b  mov     [rsp+0B0h+lpProcessInformation], rax; lpProcessInformation
0x180095270  mov     [rsp+0B0h+lpStartupInfo], r15; lpStartupInfo
0x180095275  mov     [rsp+0B0h+lpCurrentDirectory], r12; lpCurrentDirectory
0x18009527a  mov     [rsp+0B0h+lpEnvironment], rdx; lpEnvironment
0x18009527f  xor     edx, edx; lpApplicationName
0x180095281  mov     [rsp+0B0h+dwCreationFlags], 404h; dwCreationFlags
0x180095289  mov     dword ptr [rsp+0B0h+phNewToken], r12d; bInheritHandles
0x18009528e  mov     qword ptr [rsp+0B0h+TokenType], r12; lpThreadAttributes
0x180095293  call    cs:__imp_CreateProcessAsUserW
0x180095299  test    eax, eax
0x18009529b  jz      short loc_18009524F
0x18009529d  mov     ebx, r12d
0x1800952a0  mov     rcx, [rbp+3Fh+var_40]
0x1800952a4  test    rcx, rcx
0x1800952a7  jz      short loc_1800952AF
0x1800952a9  call    cs:__imp_DestroyEnvBlock
0x1800952af  lea     rcx, [rbp+3Fh+var_30]; this
0x1800952b3  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x1800952b8  lea     rcx, [rbp+3Fh+lpCommandLine]
0x1800952bc  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800952c1  lea     r11, [rsp+0B0h+var_20]
0x1800952c9  mov     eax, ebx
0x1800952cb  mov     rbx, [r11+30h]
0x1800952cf  mov     rsi, [r11+38h]
0x1800952d3  mov     rsp, r11
0x1800952d6  pop     r15
0x1800952d8  pop     r14
0x1800952da  pop     r12
0x1800952dc  pop     rdi
0x1800952dd  pop     rbp
0x1800952de  retn
```
