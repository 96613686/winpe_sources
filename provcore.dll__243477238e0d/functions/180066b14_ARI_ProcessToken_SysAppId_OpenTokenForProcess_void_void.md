# ARI::ProcessToken::SysAppId::OpenTokenForProcess(void *,void * *)

- ea: `0x180066b14`
- end: `0x180066b60`
- name: `?OpenTokenForProcess@SysAppId@ProcessToken@ARI@@YAJPEAXPEAPEAX@Z`
- size: `76`
- prototype: `int __fastcall(void *process, void **token)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18006675c`
- `0x180066904`
- `0x180067270`

## callees

- `0x180066b14`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066b44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180066b44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180066b24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180066b24`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180066b3a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180066b3a`

## pseudocode

```c
DWORD __fastcall ARI::ProcessToken::SysAppId::OpenTokenForProcess(HANDLE process, void **token)
{
  if ( process == GetCurrentProcess() )
  {
    *token = (void *)-4LL;
  }
  else if ( !OpenProcessToken(process, 8u, token) )
  {
    return GetLastError();
  }
  return 0;
}

```

## disassembly

```asm
0x180066b14  mov     [rsp+arg_0], rbx
0x180066b19  push    rdi
0x180066b1a  sub     rsp, 20h
0x180066b1e  mov     rbx, token
0x180066b21  mov     rdi, process
0x180066b24  call    cs:__imp_GetCurrentProcess
0x180066b2a  cmp     rdi, rax
0x180066b2d  jz      short loc_180066B4C
0x180066b2f  mov     r8, rbx; TokenHandle
0x180066b32  mov     edx, 8; DesiredAccess
0x180066b37  mov     process, rdi; ProcessHandle
0x180066b3a  call    cs:__imp_OpenProcessToken
0x180066b40  test    eax, eax
0x180066b42  jnz     short loc_180066B53
0x180066b44  call    cs:__imp_GetLastError
0x180066b4a  jmp     short loc_180066B55
0x180066b4c  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFCh
0x180066b53  xor     eax, eax
0x180066b55  mov     rbx, [rsp+28h+arg_0]
0x180066b5a  add     rsp, 20h
0x180066b5e  pop     rdi
0x180066b5f  retn
```
