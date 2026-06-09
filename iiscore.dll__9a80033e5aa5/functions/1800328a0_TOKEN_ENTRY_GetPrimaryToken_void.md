# TOKEN_ENTRY::GetPrimaryToken(void)

- ea: `0x1800328a0`
- end: `0x18003298d`
- name: `?GetPrimaryToken@TOKEN_ENTRY@@UEAAPEAXXZ`
- size: `237`
- prototype: `void *__fastcall(HANDLE *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800328a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003292d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003292d`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800328f6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003291a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800328f6`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003291a`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x1800328ca`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x1800328ca`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180032974`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180032974`
- `iisutil!PuDbgPrint` at `0x18003295e`
- `iisutil!PuDbgPrint` at `0x18003295e`

## string_xrefs

- `0x180032945`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\common\iislogon_lib\iislogon.cxx`
- `0x18003294c`: `DuplicateTokenEx failed, GetLastError = %lx\n`
- `0x18003293a`: `TOKEN_ENTRY::GetPrimaryToken`

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
0x1800328a0  mov     [rsp+arg_0], rbx
0x1800328a5  mov     [rsp+arg_8], rsi
0x1800328aa  push    rdi
0x1800328ab  sub     rsp, 30h
0x1800328af  lea     rbx, [rcx+18h]
0x1800328b3  mov     rdi, rcx
0x1800328b6  cmp     qword ptr [rbx], 0
0x1800328ba  jnz     loc_18003297A
0x1800328c0  lea     rsi, [rcx+0F8h]
0x1800328c7  mov     rcx, rsi
0x1800328ca  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x1800328d0  cmp     qword ptr [rbx], 0
0x1800328d4  jnz     loc_180032971
0x1800328da  mov     rcx, [rdi+10h]; hExistingToken
0x1800328de  mov     r9d, 3; ImpersonationLevel
0x1800328e4  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x1800328e9  xor     r8d, r8d; lpTokenAttributes
0x1800328ec  xor     edx, edx; dwDesiredAccess
0x1800328ee  mov     [rsp+38h+TokenType], 1; TokenType
0x1800328f6  call    cs:__imp_DuplicateTokenEx
0x1800328fc  test    eax, eax
0x1800328fe  jnz     short loc_180032964
0x180032900  mov     rcx, [rdi+10h]; hExistingToken
0x180032904  lea     r9d, [rax+2]; ImpersonationLevel
0x180032908  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x18003290d  xor     r8d, r8d; lpTokenAttributes
0x180032910  xor     edx, edx; dwDesiredAccess
0x180032912  mov     [rsp+38h+TokenType], 1; TokenType
0x18003291a  call    cs:__imp_DuplicateTokenEx
0x180032920  test    eax, eax
0x180032922  jnz     short loc_180032964
0x180032924  test    byte ptr cs:g_dwDebugFlags, 3
0x18003292b  jz      short loc_180032964
0x18003292d  call    cs:__imp_GetLastError
0x180032933  mov     rcx, cs:g_pDebug
0x18003293a  lea     r9, aTokenEntryGetp; "TOKEN_ENTRY::GetPrimaryToken"
0x180032941  mov     dword ptr [rsp+38h+phNewToken], eax
0x180032945  lea     rdx, aServercommonIn_1; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18003294c  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x180032953  mov     r8d, 4AFh
0x180032959  mov     qword ptr [rsp+38h+TokenType], rax
0x18003295e  call    cs:__imp_PuDbgPrint
0x180032964  cmp     qword ptr [rbx], 0
0x180032968  jz      short loc_180032971
0x18003296a  or      dword ptr [rdi+104h], 2
0x180032971  mov     rcx, rsi
0x180032974  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x18003297a  mov     rax, [rbx]
0x18003297d  mov     rbx, [rsp+38h+arg_0]
0x180032982  mov     rsi, [rsp+38h+arg_8]
0x180032987  add     rsp, 30h
0x18003298b  pop     rdi
0x18003298c  retn
```
