# TOKEN_ENTRY::GetPrimaryToken(void)

- ea: `0x1800116c0`
- end: `0x1800117ad`
- name: `?GetPrimaryToken@TOKEN_ENTRY@@UEAAPEAXXZ`
- size: `237`
- prototype: `void *__fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800116c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001174d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001174d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180011716`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001173a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180011716`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18001173a`
- `iisutil!PuDbgPrint` at `0x18001177e`
- `iisutil!PuDbgPrint` at `0x18001177e`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x1800116ea`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x1800116ea`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180011794`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180011794`

## string_xrefs

- `0x180011765`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x18001176c`: `DuplicateTokenEx failed, GetLastError = %lx\n`
- `0x18001175a`: `TOKEN_ENTRY::GetPrimaryToken`

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
0x1800116c0  mov     [rsp+arg_0], rbx
0x1800116c5  mov     [rsp+arg_8], rsi
0x1800116ca  push    rdi
0x1800116cb  sub     rsp, 30h
0x1800116cf  lea     rbx, [rcx+18h]
0x1800116d3  mov     rdi, rcx
0x1800116d6  cmp     qword ptr [rbx], 0
0x1800116da  jnz     loc_18001179A
0x1800116e0  lea     rsi, [rcx+0F8h]
0x1800116e7  mov     rcx, rsi
0x1800116ea  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x1800116f0  cmp     qword ptr [rbx], 0
0x1800116f4  jnz     loc_180011791
0x1800116fa  mov     rcx, [rdi+10h]; hExistingToken
0x1800116fe  mov     r9d, 3; ImpersonationLevel
0x180011704  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x180011709  xor     r8d, r8d; lpTokenAttributes
0x18001170c  xor     edx, edx; dwDesiredAccess
0x18001170e  mov     [rsp+38h+TokenType], 1; TokenType
0x180011716  call    cs:__imp_DuplicateTokenEx
0x18001171c  test    eax, eax
0x18001171e  jnz     short loc_180011784
0x180011720  mov     rcx, [rdi+10h]; hExistingToken
0x180011724  lea     r9d, [rax+2]; ImpersonationLevel
0x180011728  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x18001172d  xor     r8d, r8d; lpTokenAttributes
0x180011730  xor     edx, edx; dwDesiredAccess
0x180011732  mov     [rsp+38h+TokenType], 1; TokenType
0x18001173a  call    cs:__imp_DuplicateTokenEx
0x180011740  test    eax, eax
0x180011742  jnz     short loc_180011784
0x180011744  test    byte ptr cs:g_dwDebugFlags, 3
0x18001174b  jz      short loc_180011784
0x18001174d  call    cs:__imp_GetLastError
0x180011753  mov     rcx, cs:g_pDebug
0x18001175a  lea     r9, aTokenEntryGetp; "TOKEN_ENTRY::GetPrimaryToken"
0x180011761  mov     dword ptr [rsp+38h+phNewToken], eax
0x180011765  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001176c  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x180011773  mov     r8d, 4AFh
0x180011779  mov     qword ptr [rsp+38h+TokenType], rax
0x18001177e  call    cs:__imp_PuDbgPrint
0x180011784  cmp     qword ptr [rbx], 0
0x180011788  jz      short loc_180011791
0x18001178a  or      dword ptr [rdi+104h], 2
0x180011791  mov     rcx, rsi
0x180011794  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x18001179a  mov     rax, [rbx]
0x18001179d  mov     rbx, [rsp+38h+arg_0]
0x1800117a2  mov     rsi, [rsp+38h+arg_8]
0x1800117a7  add     rsp, 30h
0x1800117ab  pop     rdi
0x1800117ac  retn
```
