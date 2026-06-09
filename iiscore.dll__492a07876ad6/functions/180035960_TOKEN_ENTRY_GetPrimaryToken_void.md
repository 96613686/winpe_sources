# TOKEN_ENTRY::GetPrimaryToken(void)

- ea: `0x180035960`
- end: `0x180035a72`
- name: `?GetPrimaryToken@TOKEN_ENTRY@@UEAAPEAXXZ`
- size: `274`
- prototype: `void *__fastcall(HANDLE *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180035960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359ff`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800359bc`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800359e6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800359bc`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800359e6`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x18003598a`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x18003598a`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180035a52`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180035a52`
- `iisutil!PuDbgPrint` at `0x180035a36`
- `iisutil!PuDbgPrint` at `0x180035a36`

## string_xrefs

- `0x180035a1d`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x180035a24`: `DuplicateTokenEx failed, GetLastError = %lx\n`
- `0x180035a12`: `TOKEN_ENTRY::GetPrimaryToken`

## pseudocode

```c
void *__fastcall TOKEN_ENTRY::GetPrimaryToken(HANDLE *this)
{
  void **phNewToken; // rbx
  CSmallSpinLock *v3; // rsi
  DWORD LastError; // eax

  phNewToken = this + 3;
  if ( !this[3] )
  {
    v3 = (CSmallSpinLock *)(this + 31);
    CSmallSpinLock::WriteLock((CSmallSpinLock *)(this + 31));
    if ( !*phNewToken )
    {
      if ( !DuplicateTokenEx(this[2], 0, 0, SecurityDelegation, TokenPrimary, phNewToken)
        && !DuplicateTokenEx(this[2], 0, 0, SecurityImpersonation, TokenPrimary, phNewToken)
        && (g_dwDebugFlags & 3) != 0 )
      {
        LastError = GetLastError();
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\common\\iislogon_lib\\iislogon.cxx",
          1199,
          "TOKEN_ENTRY::GetPrimaryToken",
          "DuplicateTokenEx failed, GetLastError = %lx\n",
          LastError);
      }
      if ( *phNewToken )
        *((_DWORD *)this + 65) |= 2u;
    }
    CSmallSpinLock::WriteUnlock(v3);
  }
  return *phNewToken;
}

```

## disassembly

```asm
0x180035960  mov     [rsp+arg_0], rbx
0x180035965  mov     [rsp+arg_8], rsi
0x18003596a  push    rdi
0x18003596b  sub     rsp, 30h
0x18003596f  lea     rbx, [rcx+18h]
0x180035973  mov     rdi, rcx
0x180035976  cmp     qword ptr [rbx], 0
0x18003597a  jnz     loc_180035A5E
0x180035980  lea     rsi, [rcx+0F8h]
0x180035987  mov     rcx, rsi
0x18003598a  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x180035991  nop     dword ptr [rax+rax+00h]
0x180035996  cmp     qword ptr [rbx], 0
0x18003599a  jnz     loc_180035A4F
0x1800359a0  mov     rcx, [rdi+10h]; hExistingToken
0x1800359a4  mov     r9d, 3; ImpersonationLevel
0x1800359aa  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x1800359af  xor     r8d, r8d; lpTokenAttributes
0x1800359b2  xor     edx, edx; dwDesiredAccess
0x1800359b4  mov     [rsp+38h+TokenType], 1; TokenType
0x1800359bc  call    cs:__imp_DuplicateTokenEx
0x1800359c3  nop     dword ptr [rax+rax+00h]
0x1800359c8  test    eax, eax
0x1800359ca  jnz     short loc_180035A42
0x1800359cc  mov     rcx, [rdi+10h]; hExistingToken
0x1800359d0  lea     r9d, [rax+2]; ImpersonationLevel
0x1800359d4  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x1800359d9  xor     r8d, r8d; lpTokenAttributes
0x1800359dc  xor     edx, edx; dwDesiredAccess
0x1800359de  mov     [rsp+38h+TokenType], 1; TokenType
0x1800359e6  call    cs:__imp_DuplicateTokenEx
0x1800359ed  nop     dword ptr [rax+rax+00h]
0x1800359f2  test    eax, eax
0x1800359f4  jnz     short loc_180035A42
0x1800359f6  test    byte ptr cs:g_dwDebugFlags, 3
0x1800359fd  jz      short loc_180035A42
0x1800359ff  call    cs:__imp_GetLastError
0x180035a06  nop     dword ptr [rax+rax+00h]
0x180035a0b  mov     rcx, cs:g_pDebug
0x180035a12  lea     r9, aTokenEntryGetp; "TOKEN_ENTRY::GetPrimaryToken"
0x180035a19  mov     dword ptr [rsp+38h+phNewToken], eax
0x180035a1d  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180035a24  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x180035a2b  mov     r8d, 4AFh
0x180035a31  mov     qword ptr [rsp+38h+TokenType], rax
0x180035a36  call    cs:__imp_PuDbgPrint
0x180035a3d  nop     dword ptr [rax+rax+00h]
0x180035a42  cmp     qword ptr [rbx], 0
0x180035a46  jz      short loc_180035A4F
0x180035a48  or      dword ptr [rdi+104h], 2
0x180035a4f  mov     rcx, rsi
0x180035a52  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x180035a59  nop     dword ptr [rax+rax+00h]
0x180035a5e  mov     rax, [rbx]
0x180035a61  mov     rbx, [rsp+38h+arg_0]
0x180035a66  mov     rsi, [rsp+38h+arg_8]
0x180035a6b  add     rsp, 30h
0x180035a6f  pop     rdi
0x180035a70  retn
```
