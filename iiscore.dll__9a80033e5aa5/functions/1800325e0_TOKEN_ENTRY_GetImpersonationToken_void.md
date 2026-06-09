# TOKEN_ENTRY::GetImpersonationToken(void)

- ea: `0x1800325e0`
- end: `0x180032810`
- name: `?GetImpersonationToken@TOKEN_ENTRY@@UEAAPEAXXZ`
- size: `560`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800325e0`
- `0x1800343f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003277f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800326e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003277f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003274b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003276c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003274b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003276c`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18003267a`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800326cc`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18003267a`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800326cc`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180032623`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180032623`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x1800327cf`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x1800327cf`
- `iisutil!DisableTokenBackupPrivilege` at `0x1800327eb`
- `iisutil!DisableTokenBackupPrivilege` at `0x1800327eb`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800327c6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800327c6`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180032637`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180032637`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180032641`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800326ac`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180032641`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800326ac`
- `iisutil!PuDbgPrint` at `0x180032714`
- `iisutil!PuDbgPrint` at `0x1800327b0`
- `iisutil!PuDbgPrint` at `0x180032714`
- `iisutil!PuDbgPrint` at `0x1800327b0`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18003264e`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18003264e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18003269a`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18003269a`

## string_xrefs

- `0x1800326fb`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180032797`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180032702`: `Failed to get primary token security descriptor, GetLastError = %lx\n`
- `0x1800326f0`: `TOKEN_ENTRY::GetImpersonationToken`
- `0x18003278c`: `TOKEN_ENTRY::GetImpersonationToken`
- `0x18003279e`: `DuplicateTokenEx failed, GetLastError = %lx\n`

## pseudocode

```c
void *__fastcall TOKEN_ENTRY::GetImpersonationToken(TOKEN_ENTRY *this)
{
  void **phNewToken; // rdi
  CSmallSpinLock *v3; // r14
  void *Ptr; // r15
  void *v5; // rcx
  DWORD LastError; // eax
  void *v7; // rcx
  DWORD v8; // eax
  DWORD nLengthNeeded; // [rsp+30h] [rbp-39h] BYREF
  _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v12[48]; // [rsp+50h] [rbp-19h] BYREF

  phNewToken = (void **)((char *)this + 16);
  if ( !*((_QWORD *)this + 2) )
  {
    v3 = (TOKEN_ENTRY *)((char *)this + 248);
    CSmallSpinLock::WriteLock((TOKEN_ENTRY *)((char *)this + 248));
    if ( *phNewToken )
      goto LABEL_16;
    BUFFER::BUFFER((BUFFER *)v12);
    Ptr = BUFFER::QueryPtr((BUFFER *)v12);
    nLengthNeeded = BUFFER::QuerySize((BUFFER *)v12);
    v5 = (void *)*((_QWORD *)this + 3);
    memset(&TokenAttributes, 0, sizeof(TokenAttributes));
    if ( !GetKernelObjectSecurity(v5, 4u, Ptr, nLengthNeeded, &nLengthNeeded) )
    {
      if ( GetLastError() != 122 )
        goto LABEL_7;
      if ( !BUFFER::Resize((BUFFER *)v12, nLengthNeeded) )
      {
LABEL_15:
        BUFFER::~BUFFER((BUFFER *)v12);
LABEL_16:
        CSmallSpinLock::WriteUnlock(v3);
        if ( !*phNewToken )
          return *phNewToken;
        goto LABEL_17;
      }
      Ptr = BUFFER::QueryPtr((BUFFER *)v12);
      if ( !GetKernelObjectSecurity(*((HANDLE *)this + 3), 4u, Ptr, nLengthNeeded, &nLengthNeeded) )
      {
LABEL_7:
        if ( (g_dwDebugFlags & 3) != 0 )
        {
          LastError = GetLastError();
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
            1095,
            "TOKEN_ENTRY::GetImpersonationToken",
            "Failed to get primary token security descriptor, GetLastError = %lx\n",
            LastError);
        }
        goto LABEL_15;
      }
    }
    v7 = (void *)*((_QWORD *)this + 3);
    TokenAttributes.lpSecurityDescriptor = Ptr;
    TokenAttributes.nLength = 24;
    TokenAttributes.bInheritHandle = 1;
    if ( !DuplicateTokenEx(v7, 0, &TokenAttributes, SecurityDelegation, TokenImpersonation, phNewToken)
      && !DuplicateTokenEx(
            *((HANDLE *)this + 3),
            0,
            &TokenAttributes,
            SecurityImpersonation,
            TokenImpersonation,
            phNewToken)
      && (g_dwDebugFlags & 3) != 0 )
    {
      v8 = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
        1124,
        "TOKEN_ENTRY::GetImpersonationToken",
        "DuplicateTokenEx failed, GetLastError = %lx\n",
        v8);
    }
    if ( *phNewToken )
      *((_DWORD *)this + 65) |= 1u;
    goto LABEL_15;
  }
LABEL_17:
  if ( !*((_DWORD *)this + 29) && !_InterlockedExchange((volatile __int32 *)this + 29, 1) )
    DisableTokenBackupPrivilege(*phNewToken);
  return *phNewToken;
}

```

## disassembly

```asm
0x1800325e0  push    rbp
0x1800325e2  push    rbx
0x1800325e3  push    rsi
0x1800325e4  push    rdi
0x1800325e5  push    r14
0x1800325e7  push    r15
0x1800325e9  lea     rbp, [rsp-2Fh]
0x1800325ee  sub     rsp, 98h
0x1800325f5  mov     rax, cs:__security_cookie
0x1800325fc  xor     rax, rsp
0x1800325ff  mov     [rbp+57h+var_40], rax
0x180032603  lea     rdi, [rcx+10h]
0x180032607  mov     rbx, rcx
0x18003260a  cmp     qword ptr [rdi], 0
0x18003260e  mov     esi, 1
0x180032613  jnz     loc_1800327DB
0x180032619  lea     r14, [rcx+0F8h]
0x180032620  mov     rcx, r14
0x180032623  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x180032629  cmp     qword ptr [rdi], 0
0x18003262d  jnz     loc_1800327CC
0x180032633  lea     rcx, [rbp+57h+var_70]
0x180032637  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18003263d  lea     rcx, [rbp+57h+var_70]
0x180032641  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180032647  lea     rcx, [rbp+57h+var_70]
0x18003264b  mov     r15, rax
0x18003264e  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180032654  xor     ecx, ecx
0x180032656  lea     edx, [rsi+3]; RequestedInformation
0x180032659  xorps   xmm0, xmm0
0x18003265c  mov     [rbp+57h+nLengthNeeded], eax
0x18003265f  mov     qword ptr [rbp+57h+TokenAttributes.bInheritHandle], rcx
0x180032663  mov     r9d, eax; nLength
0x180032666  lea     rcx, [rbp+57h+nLengthNeeded]
0x18003266a  mov     r8, r15; pSecurityDescriptor
0x18003266d  mov     [rsp+0C0h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x180032672  mov     rcx, [rbx+18h]; Handle
0x180032676  movups  xmmword ptr [rbp+57h+TokenAttributes.nLength], xmm0
0x18003267a  call    cs:__imp_GetKernelObjectSecurity
0x180032680  test    eax, eax
0x180032682  jnz     loc_18003271F
0x180032688  call    cs:__imp_GetLastError
0x18003268e  cmp     eax, 7Ah ; 'z'
0x180032691  jnz     short loc_1800326D6
0x180032693  mov     edx, [rbp+57h+nLengthNeeded]
0x180032696  lea     rcx, [rbp+57h+var_70]
0x18003269a  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800326a0  test    al, al
0x1800326a2  jz      loc_1800327C2
0x1800326a8  lea     rcx, [rbp+57h+var_70]
0x1800326ac  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800326b2  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x1800326b6  lea     edx, [rsi+3]; RequestedInformation
0x1800326b9  mov     rcx, [rbx+18h]; Handle
0x1800326bd  mov     r15, rax
0x1800326c0  lea     rax, [rbp+57h+nLengthNeeded]
0x1800326c4  mov     r8, r15; pSecurityDescriptor
0x1800326c7  mov     [rsp+0C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800326cc  call    cs:__imp_GetKernelObjectSecurity
0x1800326d2  test    eax, eax
0x1800326d4  jnz     short loc_18003271F
0x1800326d6  test    byte ptr cs:g_dwDebugFlags, 3
0x1800326dd  jz      loc_1800327C2
0x1800326e3  call    cs:__imp_GetLastError
0x1800326e9  mov     rcx, cs:g_pDebug
0x1800326f0  lea     r9, aTokenEntryGeti; "TOKEN_ENTRY::GetImpersonationToken"
0x1800326f7  mov     dword ptr [rsp+0C0h+phNewToken], eax
0x1800326fb  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180032702  lea     rax, aFailedToGetPri; "Failed to get primary token security de"...
0x180032709  mov     r8d, 447h
0x18003270f  mov     [rsp+0C0h+lpnLengthNeeded], rax
0x180032714  call    cs:__imp_PuDbgPrint
0x18003271a  jmp     loc_1800327C2
0x18003271f  mov     rcx, [rbx+18h]; hExistingToken
0x180032723  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x180032727  mov     [rbp+57h+TokenAttributes.lpSecurityDescriptor], r15
0x18003272b  xor     edx, edx; dwDesiredAccess
0x18003272d  mov     r15d, 2
0x180032733  mov     [rsp+0C0h+phNewToken], rdi; phNewToken
0x180032738  mov     [rbp+57h+TokenAttributes.nLength], 18h
0x18003273f  mov     [rbp+57h+TokenAttributes.bInheritHandle], esi
0x180032742  mov     dword ptr [rsp+0C0h+lpnLengthNeeded], r15d; TokenType
0x180032747  lea     r9d, [r15+1]; ImpersonationLevel
0x18003274b  call    cs:__imp_DuplicateTokenEx
0x180032751  test    eax, eax
0x180032753  jnz     short loc_1800327B6
0x180032755  mov     rcx, [rbx+18h]; hExistingToken
0x180032759  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x18003275d  mov     [rsp+0C0h+phNewToken], rdi; phNewToken
0x180032762  mov     r9d, r15d; ImpersonationLevel
0x180032765  xor     edx, edx; dwDesiredAccess
0x180032767  mov     dword ptr [rsp+0C0h+lpnLengthNeeded], r15d; TokenType
0x18003276c  call    cs:__imp_DuplicateTokenEx
0x180032772  test    eax, eax
0x180032774  jnz     short loc_1800327B6
0x180032776  test    byte ptr cs:g_dwDebugFlags, 3
0x18003277d  jz      short loc_1800327B6
0x18003277f  call    cs:__imp_GetLastError
0x180032785  mov     rcx, cs:g_pDebug
0x18003278c  lea     r9, aTokenEntryGeti; "TOKEN_ENTRY::GetImpersonationToken"
0x180032793  mov     dword ptr [rsp+0C0h+phNewToken], eax
0x180032797  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18003279e  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x1800327a5  mov     r8d, 464h
0x1800327ab  mov     [rsp+0C0h+lpnLengthNeeded], rax
0x1800327b0  call    cs:__imp_PuDbgPrint
0x1800327b6  cmp     qword ptr [rdi], 0
0x1800327ba  jz      short loc_1800327C2
0x1800327bc  or      [rbx+104h], esi
0x1800327c2  lea     rcx, [rbp+57h+var_70]
0x1800327c6  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800327cc  mov     rcx, r14
0x1800327cf  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x1800327d5  cmp     qword ptr [rdi], 0
0x1800327d9  jz      short loc_1800327F1
0x1800327db  cmp     dword ptr [rbx+74h], 0
0x1800327df  jnz     short loc_1800327F1
0x1800327e1  xchg    esi, [rbx+74h]
0x1800327e4  test    esi, esi
0x1800327e6  jnz     short loc_1800327F1
0x1800327e8  mov     rcx, [rdi]
0x1800327eb  call    cs:__imp_?DisableTokenBackupPrivilege@@YAXPEAX@Z; DisableTokenBackupPrivilege(void *)
0x1800327f1  mov     rax, [rdi]
0x1800327f4  mov     rcx, [rbp+57h+var_40]
0x1800327f8  xor     rcx, rsp; StackCookie
0x1800327fb  call    __security_check_cookie
0x180032800  add     rsp, 98h
0x180032807  pop     r15
0x180032809  pop     r14
0x18003280b  pop     rdi
0x18003280c  pop     rsi
0x18003280d  pop     rbx
0x18003280e  pop     rbp
0x18003280f  retn
```
