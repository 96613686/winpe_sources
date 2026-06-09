# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x1800271d0`
- end: `0x18002721c`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `__int64 __fastcall(HANDLE ProcessHandle, PHANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180027154`

## callees

- `0x1800271d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800271e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800271e0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800271f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800271f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027200`

## pseudocode

```c
DWORD __fastcall ARI::ProcessToken::SysAppId::OpenTokenForProcess(HANDLE ProcessHandle, PHANDLE TokenHandle, void **a3)
{
  if ( ProcessHandle == GetCurrentProcess() )
  {
    *TokenHandle = (void *)-4LL;
  }
  else if ( !OpenProcessToken(ProcessHandle, 8u, TokenHandle) )
  {
    return GetLastError();
  }
  return 0;
}

```

## disassembly

```asm
0x1800271d0  mov     [rsp+arg_0], rbx
0x1800271d5  push    rdi
0x1800271d6  sub     rsp, 20h
0x1800271da  mov     rbx, rdx
0x1800271dd  mov     rdi, rcx
0x1800271e0  call    cs:__imp_GetCurrentProcess
0x1800271e6  cmp     rdi, rax
0x1800271e9  jz      short loc_180027208
0x1800271eb  mov     r8, rbx; TokenHandle
0x1800271ee  mov     edx, 8; DesiredAccess
0x1800271f3  mov     rcx, rdi; ProcessHandle
0x1800271f6  call    cs:__imp_OpenProcessToken
0x1800271fc  test    eax, eax
0x1800271fe  jnz     short loc_18002720F
0x180027200  call    cs:__imp_GetLastError
0x180027206  jmp     short loc_180027211
0x180027208  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x18002720f  xor     eax, eax
0x180027211  mov     rbx, [rsp+28h+arg_0]
0x180027216  add     rsp, 20h
0x18002721a  pop     rdi
0x18002721b  retn
```
