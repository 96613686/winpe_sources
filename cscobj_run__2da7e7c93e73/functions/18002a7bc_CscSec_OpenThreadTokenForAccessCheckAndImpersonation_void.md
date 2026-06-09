# CscSec_OpenThreadTokenForAccessCheckAndImpersonation(void * *)

- ea: `0x18002a7bc`
- end: `0x18002a7ff`
- name: `?CscSec_OpenThreadTokenForAccessCheckAndImpersonation@@YAJPEAPEAX@Z`
- size: `67`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180026980`

## callees

- `0x180009864`
- `0x18002a7bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002a7ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002a7ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002a7e1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002a7e1`

## pseudocode

```c
__int64 __fastcall CscSec_OpenThreadTokenForAccessCheckAndImpersonation(PHANDLE TokenHandle)
{
  unsigned int v1; // edi
  HANDLE CurrentThread; // rax
  UstVarLib *v4; // rcx

  v1 = 0;
  *TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, TokenHandle) )
    return (unsigned int)UstVarLib::ResultFromLastError(v4);
  return v1;
}

```

## disassembly

```asm
0x18002a7bc  mov     [rsp+arg_0], rbx
0x18002a7c1  push    rdi
0x18002a7c2  sub     rsp, 20h
0x18002a7c6  xor     edi, edi
0x18002a7c8  mov     rbx, rcx
0x18002a7cb  mov     [rcx], rdi
0x18002a7ce  call    cs:__imp_GetCurrentThread
0x18002a7d4  mov     r9, rbx; TokenHandle
0x18002a7d7  lea     edx, [rdi+0Eh]; DesiredAccess
0x18002a7da  mov     rcx, rax; ThreadHandle
0x18002a7dd  lea     r8d, [rdi+1]; OpenAsSelf
0x18002a7e1  call    cs:__imp_OpenThreadToken
0x18002a7e7  test    eax, eax
0x18002a7e9  jnz     short loc_18002A7F2
0x18002a7eb  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x18002a7f0  mov     edi, eax
0x18002a7f2  mov     rbx, [rsp+28h+arg_0]
0x18002a7f7  mov     eax, edi
0x18002a7f9  add     rsp, 20h
0x18002a7fd  pop     rdi
0x18002a7fe  retn
```
