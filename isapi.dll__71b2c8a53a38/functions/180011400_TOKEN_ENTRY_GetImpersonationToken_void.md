# TOKEN_ENTRY::GetImpersonationToken(void)

- ea: `0x180011400`
- end: `0x180011630`
- name: `?GetImpersonationToken@TOKEN_ENTRY@@UEAAPEAXXZ`
- size: `560`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180011400`
- `0x1800124c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800114a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001159f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800114a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001159f`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18001149a`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800114ec`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18001149a`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800114ec`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001156b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001158c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001156b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001158c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011461`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800114cc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011461`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800114cc`
- `iisutil!PuDbgPrint` at `0x180011534`
- `iisutil!PuDbgPrint` at `0x1800115d0`
- `iisutil!PuDbgPrint` at `0x180011534`
- `iisutil!PuDbgPrint` at `0x1800115d0`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800115e6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800115e6`
- `iisutil!DisableTokenBackupPrivilege` at `0x18001160b`
- `iisutil!DisableTokenBackupPrivilege` at `0x18001160b`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18001146e`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18001146e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800114ba`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800114ba`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180011457`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180011457`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180011443`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180011443`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x1800115ef`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x1800115ef`

## string_xrefs

- `0x18001151b`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x1800115b7`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180011522`: `Failed to get primary token security descriptor, GetLastError = %lx\n`
- `0x180011510`: `TOKEN_ENTRY::GetImpersonationToken`
- `0x1800115ac`: `TOKEN_ENTRY::GetImpersonationToken`
- `0x1800115be`: `DuplicateTokenEx failed, GetLastError = %lx\n`

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
0x180011400  push    rbp
0x180011402  push    rbx
0x180011403  push    rsi
0x180011404  push    rdi
0x180011405  push    r14
0x180011407  push    r15
0x180011409  lea     rbp, [rsp-2Fh]
0x18001140e  sub     rsp, 98h
0x180011415  mov     rax, cs:__security_cookie
0x18001141c  xor     rax, rsp
0x18001141f  mov     [rbp+57h+var_40], rax
0x180011423  lea     rdi, [rcx+10h]
0x180011427  mov     rbx, rcx
0x18001142a  cmp     qword ptr [rdi], 0
0x18001142e  mov     esi, 1
0x180011433  jnz     loc_1800115FB
0x180011439  lea     r14, [rcx+0F8h]
0x180011440  mov     rcx, r14
0x180011443  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x180011449  cmp     qword ptr [rdi], 0
0x18001144d  jnz     loc_1800115EC
0x180011453  lea     rcx, [rbp+57h+var_70]
0x180011457  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18001145d  lea     rcx, [rbp+57h+var_70]
0x180011461  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180011467  lea     rcx, [rbp+57h+var_70]
0x18001146b  mov     r15, rax
0x18001146e  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180011474  xor     ecx, ecx
0x180011476  lea     edx, [rsi+3]; RequestedInformation
0x180011479  xorps   xmm0, xmm0
0x18001147c  mov     [rbp+57h+nLengthNeeded], eax
0x18001147f  mov     qword ptr [rbp+57h+TokenAttributes.bInheritHandle], rcx
0x180011483  mov     r9d, eax; nLength
0x180011486  lea     rcx, [rbp+57h+nLengthNeeded]
0x18001148a  mov     r8, r15; pSecurityDescriptor
0x18001148d  mov     [rsp+0C0h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x180011492  mov     rcx, [rbx+18h]; Handle
0x180011496  movups  xmmword ptr [rbp+57h+TokenAttributes.nLength], xmm0
0x18001149a  call    cs:__imp_GetKernelObjectSecurity
0x1800114a0  test    eax, eax
0x1800114a2  jnz     loc_18001153F
0x1800114a8  call    cs:__imp_GetLastError
0x1800114ae  cmp     eax, 7Ah ; 'z'
0x1800114b1  jnz     short loc_1800114F6
0x1800114b3  mov     edx, [rbp+57h+nLengthNeeded]
0x1800114b6  lea     rcx, [rbp+57h+var_70]
0x1800114ba  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800114c0  test    al, al
0x1800114c2  jz      loc_1800115E2
0x1800114c8  lea     rcx, [rbp+57h+var_70]
0x1800114cc  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800114d2  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x1800114d6  lea     edx, [rsi+3]; RequestedInformation
0x1800114d9  mov     rcx, [rbx+18h]; Handle
0x1800114dd  mov     r15, rax
0x1800114e0  lea     rax, [rbp+57h+nLengthNeeded]
0x1800114e4  mov     r8, r15; pSecurityDescriptor
0x1800114e7  mov     [rsp+0C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x1800114ec  call    cs:__imp_GetKernelObjectSecurity
0x1800114f2  test    eax, eax
0x1800114f4  jnz     short loc_18001153F
0x1800114f6  test    byte ptr cs:g_dwDebugFlags, 3
0x1800114fd  jz      loc_1800115E2
0x180011503  call    cs:__imp_GetLastError
0x180011509  mov     rcx, cs:g_pDebug
0x180011510  lea     r9, aTokenEntryGeti; "TOKEN_ENTRY::GetImpersonationToken"
0x180011517  mov     dword ptr [rsp+0C0h+phNewToken], eax
0x18001151b  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180011522  lea     rax, aFailedToGetPri; "Failed to get primary token security de"...
0x180011529  mov     r8d, 447h
0x18001152f  mov     [rsp+0C0h+lpnLengthNeeded], rax
0x180011534  call    cs:__imp_PuDbgPrint
0x18001153a  jmp     loc_1800115E2
0x18001153f  mov     rcx, [rbx+18h]; hExistingToken
0x180011543  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x180011547  mov     [rbp+57h+TokenAttributes.lpSecurityDescriptor], r15
0x18001154b  xor     edx, edx; dwDesiredAccess
0x18001154d  mov     r15d, 2
0x180011553  mov     [rsp+0C0h+phNewToken], rdi; phNewToken
0x180011558  mov     [rbp+57h+TokenAttributes.nLength], 18h
0x18001155f  mov     [rbp+57h+TokenAttributes.bInheritHandle], esi
0x180011562  mov     dword ptr [rsp+0C0h+lpnLengthNeeded], r15d; TokenType
0x180011567  lea     r9d, [r15+1]; ImpersonationLevel
0x18001156b  call    cs:__imp_DuplicateTokenEx
0x180011571  test    eax, eax
0x180011573  jnz     short loc_1800115D6
0x180011575  mov     rcx, [rbx+18h]; hExistingToken
0x180011579  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x18001157d  mov     [rsp+0C0h+phNewToken], rdi; phNewToken
0x180011582  mov     r9d, r15d; ImpersonationLevel
0x180011585  xor     edx, edx; dwDesiredAccess
0x180011587  mov     dword ptr [rsp+0C0h+lpnLengthNeeded], r15d; TokenType
0x18001158c  call    cs:__imp_DuplicateTokenEx
0x180011592  test    eax, eax
0x180011594  jnz     short loc_1800115D6
0x180011596  test    byte ptr cs:g_dwDebugFlags, 3
0x18001159d  jz      short loc_1800115D6
0x18001159f  call    cs:__imp_GetLastError
0x1800115a5  mov     rcx, cs:g_pDebug
0x1800115ac  lea     r9, aTokenEntryGeti; "TOKEN_ENTRY::GetImpersonationToken"
0x1800115b3  mov     dword ptr [rsp+0C0h+phNewToken], eax
0x1800115b7  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800115be  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x1800115c5  mov     r8d, 464h
0x1800115cb  mov     [rsp+0C0h+lpnLengthNeeded], rax
0x1800115d0  call    cs:__imp_PuDbgPrint
0x1800115d6  cmp     qword ptr [rdi], 0
0x1800115da  jz      short loc_1800115E2
0x1800115dc  or      [rbx+104h], esi
0x1800115e2  lea     rcx, [rbp+57h+var_70]
0x1800115e6  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800115ec  mov     rcx, r14
0x1800115ef  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x1800115f5  cmp     qword ptr [rdi], 0
0x1800115f9  jz      short loc_180011611
0x1800115fb  cmp     dword ptr [rbx+74h], 0
0x1800115ff  jnz     short loc_180011611
0x180011601  xchg    esi, [rbx+74h]
0x180011604  test    esi, esi
0x180011606  jnz     short loc_180011611
0x180011608  mov     rcx, [rdi]
0x18001160b  call    cs:__imp_?DisableTokenBackupPrivilege@@YAXPEAX@Z; DisableTokenBackupPrivilege(void *)
0x180011611  mov     rax, [rdi]
0x180011614  mov     rcx, [rbp+57h+var_40]
0x180011618  xor     rcx, rsp; StackCookie
0x18001161b  call    __security_check_cookie
0x180011620  add     rsp, 98h
0x180011627  pop     r15
0x180011629  pop     r14
0x18001162b  pop     rdi
0x18001162c  pop     rsi
0x18001162d  pop     rbx
0x18001162e  pop     rbp
0x18001162f  retn
```
