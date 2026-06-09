# TOKEN_ENTRY::GetImpersonationToken(void)

- ea: `0x180035620`
- end: `0x1800358bd`
- name: `?GetImpersonationToken@TOKEN_ENTRY@@UEAAPEAXXZ`
- size: `669`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180035620`
- `0x180037790`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003580d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800356e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035759`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003580d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800357cd`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800357f4`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800357cd`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800357f4`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800356d2`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18003573c`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800356d2`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x18003573c`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180035663`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180035663`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x18003586f`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x18003586f`
- `iisutil!DisableTokenBackupPrivilege` at `0x180035891`
- `iisutil!DisableTokenBackupPrivilege` at `0x180035891`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180035860`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180035860`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18003567d`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18003567d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18003568d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180035716`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18003568d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180035716`
- `iisutil!PuDbgPrint` at `0x180035790`
- `iisutil!PuDbgPrint` at `0x180035844`
- `iisutil!PuDbgPrint` at `0x180035790`
- `iisutil!PuDbgPrint` at `0x180035844`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800356a0`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800356a0`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800356fe`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800356fe`

## string_xrefs

- `0x180035777`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x18003582b`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x18003577e`: `Failed to get primary token security descriptor, GetLastError = %lx\n`
- `0x18003576c`: `TOKEN_ENTRY::GetImpersonationToken`
- `0x180035820`: `TOKEN_ENTRY::GetImpersonationToken`
- `0x180035832`: `DuplicateTokenEx failed, GetLastError = %lx\n`

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
0x180035620  push    rbp
0x180035622  push    rbx
0x180035623  push    rsi
0x180035624  push    rdi
0x180035625  push    r14
0x180035627  push    r15
0x180035629  lea     rbp, [rsp-2Fh]
0x18003562e  sub     rsp, 98h
0x180035635  mov     rax, cs:__security_cookie
0x18003563c  xor     rax, rsp
0x18003563f  mov     [rbp+57h+var_40], rax
0x180035643  lea     rdi, [rcx+10h]
0x180035647  mov     rbx, rcx
0x18003564a  cmp     qword ptr [rdi], 0
0x18003564e  mov     esi, 1
0x180035653  jnz     loc_180035881
0x180035659  lea     r14, [rcx+0F8h]
0x180035660  mov     rcx, r14
0x180035663  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x18003566a  nop     dword ptr [rax+rax+00h]
0x18003566f  cmp     qword ptr [rdi], 0
0x180035673  jnz     loc_18003586C
0x180035679  lea     rcx, [rbp+57h+var_70]
0x18003567d  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180035684  nop     dword ptr [rax+rax+00h]
0x180035689  lea     rcx, [rbp+57h+var_70]
0x18003568d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180035694  nop     dword ptr [rax+rax+00h]
0x180035699  lea     rcx, [rbp+57h+var_70]
0x18003569d  mov     r15, rax
0x1800356a0  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800356a7  nop     dword ptr [rax+rax+00h]
0x1800356ac  xor     ecx, ecx
0x1800356ae  lea     edx, [rsi+3]; RequestedInformation
0x1800356b1  xorps   xmm0, xmm0
0x1800356b4  mov     [rbp+57h+nLengthNeeded], eax
0x1800356b7  mov     qword ptr [rbp+57h+TokenAttributes.bInheritHandle], rcx
0x1800356bb  mov     r9d, eax; nLength
0x1800356be  lea     rcx, [rbp+57h+nLengthNeeded]
0x1800356c2  mov     r8, r15; pSecurityDescriptor
0x1800356c5  mov     [rsp+0C0h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x1800356ca  mov     rcx, [rbx+18h]; Handle
0x1800356ce  movups  xmmword ptr [rbp+57h+TokenAttributes.nLength], xmm0
0x1800356d2  call    cs:__imp_GetKernelObjectSecurity
0x1800356d9  nop     dword ptr [rax+rax+00h]
0x1800356de  test    eax, eax
0x1800356e0  jnz     loc_1800357A1
0x1800356e6  call    cs:__imp_GetLastError
0x1800356ed  nop     dword ptr [rax+rax+00h]
0x1800356f2  cmp     eax, 7Ah ; 'z'
0x1800356f5  jnz     short loc_18003574C
0x1800356f7  mov     edx, [rbp+57h+nLengthNeeded]
0x1800356fa  lea     rcx, [rbp+57h+var_70]
0x1800356fe  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180035705  nop     dword ptr [rax+rax+00h]
0x18003570a  test    al, al
0x18003570c  jz      loc_18003585C
0x180035712  lea     rcx, [rbp+57h+var_70]
0x180035716  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18003571d  nop     dword ptr [rax+rax+00h]
0x180035722  mov     r9d, [rbp+57h+nLengthNeeded]; nLength
0x180035726  lea     edx, [rsi+3]; RequestedInformation
0x180035729  mov     rcx, [rbx+18h]; Handle
0x18003572d  mov     r15, rax
0x180035730  lea     rax, [rbp+57h+nLengthNeeded]
0x180035734  mov     r8, r15; pSecurityDescriptor
0x180035737  mov     [rsp+0C0h+lpnLengthNeeded], rax; lpnLengthNeeded
0x18003573c  call    cs:__imp_GetKernelObjectSecurity
0x180035743  nop     dword ptr [rax+rax+00h]
0x180035748  test    eax, eax
0x18003574a  jnz     short loc_1800357A1
0x18003574c  test    byte ptr cs:g_dwDebugFlags, 3
0x180035753  jz      loc_18003585C
0x180035759  call    cs:__imp_GetLastError
0x180035760  nop     dword ptr [rax+rax+00h]
0x180035765  mov     rcx, cs:g_pDebug
0x18003576c  lea     r9, aTokenEntryGeti; "TOKEN_ENTRY::GetImpersonationToken"
0x180035773  mov     dword ptr [rsp+0C0h+phNewToken], eax
0x180035777  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18003577e  lea     rax, aFailedToGetPri; "Failed to get primary token security de"...
0x180035785  mov     r8d, 447h
0x18003578b  mov     [rsp+0C0h+lpnLengthNeeded], rax
0x180035790  call    cs:__imp_PuDbgPrint
0x180035797  nop     dword ptr [rax+rax+00h]
0x18003579c  jmp     loc_18003585C
0x1800357a1  mov     rcx, [rbx+18h]; hExistingToken
0x1800357a5  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x1800357a9  mov     [rbp+57h+TokenAttributes.lpSecurityDescriptor], r15
0x1800357ad  xor     edx, edx; dwDesiredAccess
0x1800357af  mov     r15d, 2
0x1800357b5  mov     [rsp+0C0h+phNewToken], rdi; phNewToken
0x1800357ba  mov     [rbp+57h+TokenAttributes.nLength], 18h
0x1800357c1  mov     [rbp+57h+TokenAttributes.bInheritHandle], esi
0x1800357c4  mov     dword ptr [rsp+0C0h+lpnLengthNeeded], r15d; TokenType
0x1800357c9  lea     r9d, [r15+1]; ImpersonationLevel
0x1800357cd  call    cs:__imp_DuplicateTokenEx
0x1800357d4  nop     dword ptr [rax+rax+00h]
0x1800357d9  test    eax, eax
0x1800357db  jnz     short loc_180035850
0x1800357dd  mov     rcx, [rbx+18h]; hExistingToken
0x1800357e1  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x1800357e5  mov     [rsp+0C0h+phNewToken], rdi; phNewToken
0x1800357ea  mov     r9d, r15d; ImpersonationLevel
0x1800357ed  xor     edx, edx; dwDesiredAccess
0x1800357ef  mov     dword ptr [rsp+0C0h+lpnLengthNeeded], r15d; TokenType
0x1800357f4  call    cs:__imp_DuplicateTokenEx
0x1800357fb  nop     dword ptr [rax+rax+00h]
0x180035800  test    eax, eax
0x180035802  jnz     short loc_180035850
0x180035804  test    byte ptr cs:g_dwDebugFlags, 3
0x18003580b  jz      short loc_180035850
0x18003580d  call    cs:__imp_GetLastError
0x180035814  nop     dword ptr [rax+rax+00h]
0x180035819  mov     rcx, cs:g_pDebug
0x180035820  lea     r9, aTokenEntryGeti; "TOKEN_ENTRY::GetImpersonationToken"
0x180035827  mov     dword ptr [rsp+0C0h+phNewToken], eax
0x18003582b  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180035832  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x180035839  mov     r8d, 464h
0x18003583f  mov     [rsp+0C0h+lpnLengthNeeded], rax
0x180035844  call    cs:__imp_PuDbgPrint
0x18003584b  nop     dword ptr [rax+rax+00h]
0x180035850  cmp     qword ptr [rdi], 0
0x180035854  jz      short loc_18003585C
0x180035856  or      [rbx+104h], esi
0x18003585c  lea     rcx, [rbp+57h+var_70]
0x180035860  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180035867  nop     dword ptr [rax+rax+00h]
0x18003586c  mov     rcx, r14
0x18003586f  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x180035876  nop     dword ptr [rax+rax+00h]
0x18003587b  cmp     qword ptr [rdi], 0
0x18003587f  jz      short loc_18003589D
0x180035881  cmp     dword ptr [rbx+74h], 0
0x180035885  jnz     short loc_18003589D
0x180035887  xchg    esi, [rbx+74h]
0x18003588a  test    esi, esi
0x18003588c  jnz     short loc_18003589D
0x18003588e  mov     rcx, [rdi]
0x180035891  call    cs:__imp_?DisableTokenBackupPrivilege@@YAXPEAX@Z; DisableTokenBackupPrivilege(void *)
0x180035898  nop     dword ptr [rax+rax+00h]
0x18003589d  mov     rax, [rdi]
0x1800358a0  mov     rcx, [rbp+57h+var_40]
0x1800358a4  xor     rcx, rsp; StackCookie
0x1800358a7  call    __security_check_cookie
0x1800358ac  add     rsp, 98h
0x1800358b3  pop     r15
0x1800358b5  pop     r14
0x1800358b7  pop     rdi
0x1800358b8  pop     rsi
0x1800358b9  pop     rbx
0x1800358ba  pop     rbp
0x1800358bb  retn
```
