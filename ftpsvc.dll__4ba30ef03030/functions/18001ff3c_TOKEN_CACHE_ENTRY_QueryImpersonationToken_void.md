# TOKEN_CACHE_ENTRY::QueryImpersonationToken(void)

- ea: `0x18001ff3c`
- end: `0x180020012`
- name: `?QueryImpersonationToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ`
- size: `214`
- prototype: `void *__fastcall(TOKEN_CACHE_ENTRY *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fdd8`
- `0x1800116a4`
- `0x180015890`
- `0x1800158d0`
- `0x18001b3ac`
- `0x18001b90c`

## callees

- `0x18001ff3c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001ff9e`
- `KERNEL32!GetLastError` at `0x18001ff9e`
- `ADVAPI32!DuplicateTokenEx` at `0x18001ff8b`
- `ADVAPI32!DuplicateTokenEx` at `0x18001ff8b`
- `iisutil!PuDbgPrint` at `0x18001ffcf`
- `iisutil!PuDbgPrint` at `0x18001ffcf`
- `iisutil!DisableTokenBackupPrivilege` at `0x18001fff9`
- `iisutil!DisableTokenBackupPrivilege` at `0x18001fff9`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x18001ffd8`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x18001ffd8`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x18001ff66`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x18001ff66`

## string_xrefs

- `0x18001ffbd`: `DuplicateTokenEx failed, GetLastError = %lx\n`
- `0x18001ffb6`: `servercommon\inetsrv\iis\iisrearc\iisplus\tokencache\tokencache.cxx`
- `0x18001ffab`: `TOKEN_CACHE_ENTRY::QueryImpersonationToken`

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
0x18001ff3c  mov     [rsp+arg_0], rbx
0x18001ff41  mov     [rsp+arg_8], rsi
0x18001ff46  push    rdi
0x18001ff47  sub     rsp, 30h
0x18001ff4b  lea     rbx, [rcx+18h]
0x18001ff4f  mov     rdi, rcx
0x18001ff52  cmp     qword ptr [rbx], 0
0x18001ff56  jnz     loc_18001FFE4
0x18001ff5c  lea     rsi, [rcx+140h]
0x18001ff63  mov     rcx, rsi
0x18001ff66  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x18001ff6c  cmp     qword ptr [rbx], 0
0x18001ff70  jnz     short loc_18001FFD5
0x18001ff72  mov     rcx, [rdi+20h]; hExistingToken
0x18001ff76  mov     r9d, 2; ImpersonationLevel
0x18001ff7c  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x18001ff81  xor     r8d, r8d; lpTokenAttributes
0x18001ff84  xor     edx, edx; dwDesiredAccess
0x18001ff86  mov     [rsp+38h+TokenType], r9d; TokenType
0x18001ff8b  call    cs:__imp_DuplicateTokenEx
0x18001ff91  test    eax, eax
0x18001ff93  jnz     short loc_18001FFD5
0x18001ff95  test    byte ptr cs:g_dwDebugFlags, 3
0x18001ff9c  jz      short loc_18001FFD5
0x18001ff9e  call    cs:__imp_GetLastError
0x18001ffa4  mov     rcx, cs:g_pDebug
0x18001ffab  lea     r9, aTokenCacheEntr; "TOKEN_CACHE_ENTRY::QueryImpersonationTo"...
0x18001ffb2  mov     dword ptr [rsp+38h+phNewToken], eax
0x18001ffb6  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001ffbd  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x18001ffc4  mov     r8d, 2C7h
0x18001ffca  mov     qword ptr [rsp+38h+TokenType], rax
0x18001ffcf  call    cs:__imp_PuDbgPrint
0x18001ffd5  mov     rcx, rsi
0x18001ffd8  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x18001ffde  cmp     qword ptr [rbx], 0
0x18001ffe2  jz      short loc_18001FFFF
0x18001ffe4  cmp     dword ptr [rdi+2Ch], 0
0x18001ffe8  jnz     short loc_18001FFFF
0x18001ffea  mov     ecx, 1
0x18001ffef  xchg    ecx, [rdi+2Ch]
0x18001fff2  test    ecx, ecx
0x18001fff4  jnz     short loc_18001FFFF
0x18001fff6  mov     rcx, [rbx]
0x18001fff9  call    cs:__imp_?DisableTokenBackupPrivilege@@YAXPEAX@Z; DisableTokenBackupPrivilege(void *)
0x18001ffff  mov     rax, [rbx]
0x180020002  mov     rbx, [rsp+38h+arg_0]
0x180020007  mov     rsi, [rsp+38h+arg_8]
0x18002000c  add     rsp, 30h
0x180020010  pop     rdi
0x180020011  retn
```
