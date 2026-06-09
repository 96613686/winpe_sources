# ISAPI_CONTEXT::QueryToken(void)

- ea: `0x180005f08`
- end: `0x180005f89`
- name: `?QueryToken@ISAPI_CONTEXT@@QEAAPEAXXZ`
- size: `129`
- prototype: `void *__fastcall(ISAPI_CONTEXT *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003744`
- `0x1800038ec`
- `0x180007b7c`

## callees

- `0x180005f08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005f45`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180005f45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005f32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180005f32`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180005f6f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180005f6f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005f7a`

## pseudocode

```c
void *__fastcall ISAPI_CONTEXT::QueryToken(ISAPI_CONTEXT *this)
{
  void *result; // rax
  void **phNewToken; // rbx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+40h] [rbp+8h] BYREF

  result = *(void **)(*((_QWORD *)this + 25) + 16LL);
  if ( !result )
  {
    phNewToken = (void **)((char *)this + 208);
    result = (void *)*((_QWORD *)this + 26);
    if ( !result )
    {
      TokenHandle = 0;
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 0xF01FFu, &TokenHandle) )
      {
        DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityDelegation, TokenImpersonation, phNewToken);
        CloseHandle(TokenHandle);
      }
      return *phNewToken;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180005f08  push    rbx
0x180005f0a  sub     rsp, 30h
0x180005f0e  mov     rax, [rcx+0C8h]
0x180005f15  mov     rax, [rax+10h]
0x180005f19  test    rax, rax
0x180005f1c  jnz     short loc_180005F83
0x180005f1e  lea     rbx, [rcx+0D0h]
0x180005f25  mov     rax, [rbx]
0x180005f28  test    rax, rax
0x180005f2b  jnz     short loc_180005F83
0x180005f2d  mov     [rsp+38h+TokenHandle], rax
0x180005f32  call    cs:__imp_GetCurrentProcess
0x180005f38  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180005f3d  mov     edx, 0F01FFh; DesiredAccess
0x180005f42  mov     rcx, rax; ProcessHandle
0x180005f45  call    cs:__imp_OpenProcessToken
0x180005f4b  test    eax, eax
0x180005f4d  jz      short loc_180005F80
0x180005f4f  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x180005f54  mov     r9d, 3; ImpersonationLevel
0x180005f5a  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x180005f5f  xor     r8d, r8d; lpTokenAttributes
0x180005f62  mov     edx, 2000000h; dwDesiredAccess
0x180005f67  mov     [rsp+38h+TokenType], 2; TokenType
0x180005f6f  call    cs:__imp_DuplicateTokenEx
0x180005f75  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180005f7a  call    cs:__imp_CloseHandle
0x180005f80  mov     rax, [rbx]
0x180005f83  add     rsp, 30h
0x180005f87  pop     rbx
0x180005f88  retn
```
