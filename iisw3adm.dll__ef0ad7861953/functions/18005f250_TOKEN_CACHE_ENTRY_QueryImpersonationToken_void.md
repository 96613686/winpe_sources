# TOKEN_CACHE_ENTRY::QueryImpersonationToken(void)

- ea: `0x18005f250`
- end: `0x18005f326`
- name: `?QueryImpersonationToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ`
- size: `214`
- prototype: `void *__fastcall(TOKEN_CACHE_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018eb4`

## callees

- `0x18005f250`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f2b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f2b2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18005f29f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18005f29f`
- `iisutil!PuDbgPrint` at `0x18005f2e3`
- `iisutil!PuDbgPrint` at `0x18005f2e3`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x18005f2ec`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x18005f2ec`
- `iisutil!DisableTokenBackupPrivilege` at `0x18005f30d`
- `iisutil!DisableTokenBackupPrivilege` at `0x18005f30d`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x18005f27a`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x18005f27a`

## string_xrefs

- `0x18005f2ca`: `servercommon\inetsrv\iis\iisrearc\iisplus\tokencache\tokencache.cxx`
- `0x18005f2d1`: `DuplicateTokenEx failed, GetLastError = %lx\n`
- `0x18005f2bf`: `TOKEN_CACHE_ENTRY::QueryImpersonationToken`

## pseudocode

```c
void *__fastcall TOKEN_CACHE_ENTRY::QueryImpersonationToken(TOKEN_CACHE_ENTRY *this)
{
  void **phNewToken; // rbx
  CSmallSpinLock *v3; // rsi
  DWORD LastError; // eax

  phNewToken = (void **)((char *)this + 24);
  if ( *((_QWORD *)this + 3) )
    goto LABEL_13;
  v3 = (TOKEN_CACHE_ENTRY *)((char *)this + 320);
  CSmallSpinLock::WriteLock((TOKEN_CACHE_ENTRY *)((char *)this + 320));
  if ( !*phNewToken
    && !DuplicateTokenEx(*((HANDLE *)this + 4), 0, 0, SecurityImpersonation, TokenImpersonation, phNewToken)
    && (g_dwDebugFlags & 3) != 0 )
  {
    LastError = GetLastError();
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\tokencache\\tokencache.cxx",
      711,
      "TOKEN_CACHE_ENTRY::QueryImpersonationToken",
      "DuplicateTokenEx failed, GetLastError = %lx\n",
      LastError);
  }
  CSmallSpinLock::WriteUnlock(v3);
  if ( *phNewToken )
  {
LABEL_13:
    if ( !*((_DWORD *)this + 11) && !_InterlockedExchange((volatile __int32 *)this + 11, 1) )
      DisableTokenBackupPrivilege(*phNewToken);
  }
  return *phNewToken;
}

```

## disassembly

```asm
0x18005f250  mov     [rsp+arg_0], rbx
0x18005f255  mov     [rsp+arg_8], rsi
0x18005f25a  push    rdi
0x18005f25b  sub     rsp, 30h
0x18005f25f  lea     rbx, [rcx+18h]
0x18005f263  mov     rdi, rcx
0x18005f266  cmp     qword ptr [rbx], 0
0x18005f26a  jnz     loc_18005F2F8
0x18005f270  lea     rsi, [rcx+140h]
0x18005f277  mov     rcx, rsi
0x18005f27a  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x18005f280  cmp     qword ptr [rbx], 0
0x18005f284  jnz     short loc_18005F2E9
0x18005f286  mov     rcx, [rdi+20h]; hExistingToken
0x18005f28a  mov     r9d, 2; ImpersonationLevel
0x18005f290  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x18005f295  xor     r8d, r8d; lpTokenAttributes
0x18005f298  xor     edx, edx; dwDesiredAccess
0x18005f29a  mov     [rsp+38h+TokenType], r9d; TokenType
0x18005f29f  call    cs:__imp_DuplicateTokenEx
0x18005f2a5  test    eax, eax
0x18005f2a7  jnz     short loc_18005F2E9
0x18005f2a9  test    byte ptr cs:g_dwDebugFlags, 3
0x18005f2b0  jz      short loc_18005F2E9
0x18005f2b2  call    cs:__imp_GetLastError
0x18005f2b8  mov     rcx, cs:g_pDebug
0x18005f2bf  lea     r9, aTokenCacheEntr; "TOKEN_CACHE_ENTRY::QueryImpersonationTo"...
0x18005f2c6  mov     dword ptr [rsp+38h+phNewToken], eax
0x18005f2ca  lea     rdx, aServercommonIn_45; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18005f2d1  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x18005f2d8  mov     r8d, 2C7h
0x18005f2de  mov     qword ptr [rsp+38h+TokenType], rax
0x18005f2e3  call    cs:__imp_PuDbgPrint
0x18005f2e9  mov     rcx, rsi
0x18005f2ec  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x18005f2f2  cmp     qword ptr [rbx], 0
0x18005f2f6  jz      short loc_18005F313
0x18005f2f8  cmp     dword ptr [rdi+2Ch], 0
0x18005f2fc  jnz     short loc_18005F313
0x18005f2fe  mov     ecx, 1
0x18005f303  xchg    ecx, [rdi+2Ch]
0x18005f306  test    ecx, ecx
0x18005f308  jnz     short loc_18005F313
0x18005f30a  mov     rcx, [rbx]
0x18005f30d  call    cs:__imp_?DisableTokenBackupPrivilege@@YAXPEAX@Z; DisableTokenBackupPrivilege(void *)
0x18005f313  mov     rax, [rbx]
0x18005f316  mov     rbx, [rsp+38h+arg_0]
0x18005f31b  mov     rsi, [rsp+38h+arg_8]
0x18005f320  add     rsp, 30h
0x18005f324  pop     rdi
0x18005f325  retn
```
