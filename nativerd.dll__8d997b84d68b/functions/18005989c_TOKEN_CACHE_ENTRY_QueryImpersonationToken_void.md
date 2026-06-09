# TOKEN_CACHE_ENTRY::QueryImpersonationToken(void)

- ea: `0x18005989c`
- end: `0x180059952`
- name: `?QueryImpersonationToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ`
- size: `182`
- prototype: `void *__fastcall(TOKEN_CACHE_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004461c`
- `0x1800562fc`

## callees

- `0x18005989c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800598fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800598fe`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800598eb`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800598eb`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x1800598c3`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x1800598c3`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180059939`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x180059939`
- `iisutil!PuDbgPrint` at `0x18005992f`
- `iisutil!PuDbgPrint` at `0x18005992f`

## string_xrefs

- `0x180059916`: `servercommon\inetsrv\iis\iisrearc\core\nativereader\dll\tokencache.cxx`
- `0x18005991d`: `DuplicateTokenEx failed, GetLastError = %lx\n`
- `0x18005990b`: `TOKEN_CACHE_ENTRY::QueryImpersonationToken`

## pseudocode

```c
void *__fastcall TOKEN_CACHE_ENTRY::QueryImpersonationToken(HANDLE *this)
{
  void **phNewToken; // rbx
  DWORD LastError; // eax

  phNewToken = this + 44;
  if ( !this[44] )
  {
    CSmallSpinLock::WriteLock((CSmallSpinLock *)(this + 4));
    if ( !*phNewToken
      && !DuplicateTokenEx(this[45], 0, 0, SecurityImpersonation, TokenImpersonation, phNewToken)
      && (g_dwDebugFlags & 3) != 0 )
    {
      LastError = GetLastError();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\nativereader\\dll\\tokencache.cxx",
        409,
        "TOKEN_CACHE_ENTRY::QueryImpersonationToken",
        "DuplicateTokenEx failed, GetLastError = %lx\n",
        LastError);
    }
    CSmallSpinLock::WriteUnlock((CSmallSpinLock *)(this + 4));
  }
  return *phNewToken;
}

```

## disassembly

```asm
0x18005989c  mov     [rsp+arg_0], rbx
0x1800598a1  mov     [rsp+arg_8], rsi
0x1800598a6  push    rdi
0x1800598a7  sub     rsp, 30h
0x1800598ab  lea     rbx, [rcx+160h]
0x1800598b2  mov     rdi, rcx
0x1800598b5  cmp     qword ptr [rbx], 0
0x1800598b9  jnz     loc_18005993F
0x1800598bf  add     rcx, 20h ; ' '
0x1800598c3  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x1800598c9  cmp     qword ptr [rbx], 0
0x1800598cd  jnz     short loc_180059935
0x1800598cf  mov     rcx, [rdi+168h]; hExistingToken
0x1800598d6  mov     r9d, 2; ImpersonationLevel
0x1800598dc  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x1800598e1  xor     r8d, r8d; lpTokenAttributes
0x1800598e4  xor     edx, edx; dwDesiredAccess
0x1800598e6  mov     [rsp+38h+TokenType], r9d; TokenType
0x1800598eb  call    cs:__imp_DuplicateTokenEx
0x1800598f1  test    eax, eax
0x1800598f3  jnz     short loc_180059935
0x1800598f5  test    byte ptr cs:g_dwDebugFlags, 3
0x1800598fc  jz      short loc_180059935
0x1800598fe  call    cs:__imp_GetLastError
0x180059904  mov     rcx, cs:g_pDebug
0x18005990b  lea     r9, aTokenCacheEntr; "TOKEN_CACHE_ENTRY::QueryImpersonationTo"...
0x180059912  mov     dword ptr [rsp+38h+phNewToken], eax
0x180059916  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18005991d  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x180059924  mov     r8d, 199h
0x18005992a  mov     qword ptr [rsp+38h+TokenType], rax
0x18005992f  call    cs:__imp_PuDbgPrint
0x180059935  lea     rcx, [rdi+20h]
0x180059939  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x18005993f  mov     rax, [rbx]
0x180059942  mov     rbx, [rsp+38h+arg_0]
0x180059947  mov     rsi, [rsp+38h+arg_8]
0x18005994c  add     rsp, 30h
0x180059950  pop     rdi
0x180059951  retn
```
