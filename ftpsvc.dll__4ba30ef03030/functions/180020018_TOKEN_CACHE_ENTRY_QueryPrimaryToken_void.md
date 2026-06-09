# TOKEN_CACHE_ENTRY::QueryPrimaryToken(void)

- ea: `0x180020018`
- end: `0x1800200d0`
- name: `?QueryPrimaryToken@TOKEN_CACHE_ENTRY@@QEAAPEAXXZ`
- size: `184`
- prototype: `void *__fastcall(TOKEN_CACHE_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800158b0`

## callees

- `0x180020018`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002007d`
- `KERNEL32!GetLastError` at `0x18002007d`
- `ADVAPI32!DuplicateTokenEx` at `0x18002006a`
- `ADVAPI32!DuplicateTokenEx` at `0x18002006a`
- `iisutil!PuDbgPrint` at `0x1800200ae`
- `iisutil!PuDbgPrint` at `0x1800200ae`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x1800200b7`
- `iisutil!?WriteUnlock@CSmallSpinLock@@QEAAXXZ` at `0x1800200b7`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180020042`
- `iisutil!?WriteLock@CSmallSpinLock@@QEAAXXZ` at `0x180020042`

## string_xrefs

- `0x18002009c`: `DuplicateTokenEx failed, GetLastError = %lx\n`
- `0x180020095`: `servercommon\inetsrv\iis\iisrearc\iisplus\tokencache\tokencache.cxx`
- `0x18002008a`: `TOKEN_CACHE_ENTRY::QueryPrimaryToken`

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
0x180020018  mov     [rsp+arg_0], rbx
0x18002001d  mov     [rsp+arg_8], rsi
0x180020022  push    rdi
0x180020023  sub     rsp, 30h
0x180020027  lea     rbx, [rcx+20h]
0x18002002b  mov     rdi, rcx
0x18002002e  cmp     qword ptr [rbx], 0
0x180020032  jnz     loc_1800200BD
0x180020038  lea     rsi, [rcx+140h]
0x18002003f  mov     rcx, rsi
0x180020042  call    cs:__imp_?WriteLock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteLock(void)
0x180020048  cmp     qword ptr [rbx], 0
0x18002004c  jnz     short loc_1800200B4
0x18002004e  mov     rcx, [rdi+18h]; hExistingToken
0x180020052  mov     r9d, 2; ImpersonationLevel
0x180020058  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x18002005d  xor     r8d, r8d; lpTokenAttributes
0x180020060  xor     edx, edx; dwDesiredAccess
0x180020062  mov     [rsp+38h+TokenType], 1; TokenType
0x18002006a  call    cs:__imp_DuplicateTokenEx
0x180020070  test    eax, eax
0x180020072  jnz     short loc_1800200B4
0x180020074  test    byte ptr cs:g_dwDebugFlags, 3
0x18002007b  jz      short loc_1800200B4
0x18002007d  call    cs:__imp_GetLastError
0x180020083  mov     rcx, cs:g_pDebug
0x18002008a  lea     r9, aTokenCacheEntr_4; "TOKEN_CACHE_ENTRY::QueryPrimaryToken"
0x180020091  mov     dword ptr [rsp+38h+phNewToken], eax
0x180020095  lea     rdx, aServercommonIn_2; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18002009c  lea     rax, aDuplicatetoken; "DuplicateTokenEx failed, GetLastError ="...
0x1800200a3  mov     r8d, 303h
0x1800200a9  mov     qword ptr [rsp+38h+TokenType], rax
0x1800200ae  call    cs:__imp_PuDbgPrint
0x1800200b4  mov     rcx, rsi
0x1800200b7  call    cs:__imp_?WriteUnlock@CSmallSpinLock@@QEAAXXZ; CSmallSpinLock::WriteUnlock(void)
0x1800200bd  mov     rax, [rbx]
0x1800200c0  mov     rbx, [rsp+38h+arg_0]
0x1800200c5  mov     rsi, [rsp+38h+arg_8]
0x1800200ca  add     rsp, 30h
0x1800200ce  pop     rdi
0x1800200cf  retn
```
