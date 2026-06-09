# TOKEN_CACHE_ENTRY::QueryPrimaryToken(void)

- ea: `0x18005f32c`
- end: `0x18005f3e4`
- name: `?QueryPrimaryToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ`
- size: `184`
- prototype: `void *__fastcall(TOKEN_CACHE_ENTRY *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019cb8`
- `0x180019e7c`
- `0x180021e30`
- `0x180023c8c`
- `0x180025dec`
- `0x180027008`
- `0x1800362d8`
- `0x180037234`

## callees

- `0x18005f32c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f391`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f391`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18005f37e`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18005f37e`
- `iisutil!PuDbgPrint` at `0x18005f3c2`
- `iisutil!PuDbgPrint` at `0x18005f3c2`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x18005f3cb`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x18005f3cb`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x18005f356`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x18005f356`

## string_xrefs

- `0x18005f3a9`: `servercommon\inetsrv\iis\iisrearc\iisplus\tokencache\tokencache.cxx`
- `0x18005f3b0`: `DuplicateTokenEx failed, GetLastError = %lx\n`
- `0x18005f39e`: `TOKEN_CACHE_ENTRY::QueryPrimaryToken`

## pseudocode

```c
void *__fastcall TOKEN_CACHE_ENTRY::QueryPrimaryToken(HANDLE *this)
{
  void **phNewToken; // rbx
  CSmallSpinLock *v3; // rsi
  DWORD LastError; // eax

  phNewToken = this + 4;
  if ( !this[4] )
  {
    v3 = (CSmallSpinLock *)(this + 40);
    CSmallSpinLock::WriteLock((CSmallSpinLock *)(this + 40));
    if ( !*phNewToken
      && !DuplicateTokenEx(this[3], 0, 0, SecurityImpersonation, TokenPrimary, phNewToken)
      && (g_dwDebugFlags & 3) != 0 )
    {
      LastError = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\tokencache\\tokencache.cxx",
        771,
        "TOKEN_CACHE_ENTRY::QueryPrimaryToken",
        "DuplicateTokenEx failed, GetLastError = %lx\n",
        LastError);
    }
    CSmallSpinLock::WriteUnlock(v3);
  }
  return *phNewToken;
}

```

## disassembly

```asm
0x18005f32c  mov     [rsp+arg_0], rbx
0x18005f331  mov     [rsp+arg_8], rsi
0x18005f336  push    rdi
0x18005f337  sub     rsp, 30h
0x18005f33b  lea     rbx, [rcx+20h]
0x18005f33f  mov     rdi, rcx
0x18005f342  cmp     qword ptr [rbx], 0
0x18005f346  jnz     loc_18005F3D1
0x18005f34c  lea     rsi, [rcx+140h]
0x18005f353  mov     rcx, rsi
0x18005f356  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x18005f35c  cmp     qword ptr [rbx], 0
0x18005f360  jnz     short loc_18005F3C8
0x18005f362  mov     rcx, [rdi+18h]; hExistingToken
0x18005f366  mov     r9d, 2; ImpersonationLevel
0x18005f36c  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x18005f371  xor     r8d, r8d; lpTokenAttributes
0x18005f374  xor     edx, edx; dwDesiredAccess
0x18005f376  mov     [rsp+38h+TokenType], 1; TokenType
0x18005f37e  call    cs:__imp_DuplicateTokenEx
0x18005f384  test    eax, eax
0x18005f386  jnz     short loc_18005F3C8
0x18005f388  test    byte ptr cs:g_dwDebugFlags, 3
0x18005f38f  jz      short loc_18005F3C8
0x18005f391  call    cs:__imp_GetLastError
0x18005f397  mov     rcx, cs:g_pDebug
0x18005f39e  lea     r9, aTokenCacheEntr_4; "TOKEN_CACHE_ENTRY::QueryPrimaryToken"
0x18005f3a5  mov     dword ptr [rsp+38h+phNewToken], eax
0x18005f3a9  lea     rdx, aServercommonIn_45; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18005f3b0  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x18005f3b7  mov     r8d, 303h
0x18005f3bd  mov     qword ptr [rsp+38h+TokenType], rax
0x18005f3c2  call    cs:__imp_PuDbgPrint
0x18005f3c8  mov     rcx, rsi
0x18005f3cb  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x18005f3d1  mov     rax, [rbx]
0x18005f3d4  mov     rbx, [rsp+38h+arg_0]
0x18005f3d9  mov     rsi, [rsp+38h+arg_8]
0x18005f3de  add     rsp, 30h
0x18005f3e2  pop     rdi
0x18005f3e3  retn
```
