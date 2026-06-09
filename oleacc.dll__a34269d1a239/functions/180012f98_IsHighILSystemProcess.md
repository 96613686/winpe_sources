# IsHighILSystemProcess

- ea: `0x180012f98`
- end: `0x180012ff9`
- name: `IsHighILSystemProcess`
- size: `97`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800127b0`

## callees

- `0x180012f98`
- `0x180013000`
- `0x180045ad8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012fe6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012fe6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012fb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180012fb8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180012fcb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180012fcb`

## pseudocode

```c
_BOOL8 IsHighILSystemProcess()
{
  HANDLE CurrentProcess; // rax
  unsigned int TokenIl; // ebx
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  if ( !(unsigned int)IsSystem() )
    return 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    return 0;
  TokenIl = GetTokenIl(TokenHandle);
  CloseHandle(TokenHandle);
  return TokenIl >= 0x3000;
}

```

## disassembly

```asm
0x180012f98  push    rbx
0x180012f9a  sub     rsp, 20h
0x180012f9e  call    ?IsSystem@@YAHXZ; IsSystem(void)
0x180012fa3  test    eax, eax
0x180012fa5  jnz     short loc_180012FAF
0x180012fa7  xor     eax, eax
0x180012fa9  add     rsp, 20h
0x180012fad  pop     rbx
0x180012fae  retn
0x180012faf  mov     [rsp+28h+TokenHandle], 0
0x180012fb8  call    cs:__imp_GetCurrentProcess
0x180012fbe  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180012fc3  mov     edx, 8; DesiredAccess
0x180012fc8  mov     rcx, rax; ProcessHandle
0x180012fcb  call    cs:__imp_OpenProcessToken
0x180012fd1  test    eax, eax
0x180012fd3  jz      short loc_180012FA7
0x180012fd5  mov     rcx, [rsp+28h+TokenHandle]; void *
0x180012fda  call    ?GetTokenIl@@YAKPEAX@Z; GetTokenIl(void *)
0x180012fdf  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180012fe4  mov     ebx, eax
0x180012fe6  call    cs:__imp_CloseHandle
0x180012fec  xor     eax, eax
0x180012fee  cmp     ebx, 3000h
0x180012ff4  setnb   al
0x180012ff7  jmp     short loc_180012FA9
```
