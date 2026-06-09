# CAutoImpersonate::IsImpersonating(int *)

- ea: `0x18004052c`
- end: `0x1800405af`
- name: `?IsImpersonating@CAutoImpersonate@@QEAAJPEAH@Z`
- size: `131`
- prototype: `__int64 __fastcall(CAutoImpersonate *__hidden this, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800404c8`
- `0x1800405b8`

## callees

- `0x18004052c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040584`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040584`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180040567`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180040567`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180040553`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180040553`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004057c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004057c`

## pseudocode

```c
__int64 __fastcall CAutoImpersonate::IsImpersonating(CAutoImpersonate *this, int *a2)
{
  unsigned int v4; // ebx
  HANDLE CurrentThread; // rax
  void *v6; // rcx
  signed int LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = this;
  if ( !a2 )
    return 2147500035LL;
  v4 = 0;
  *a2 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    v6 = TokenHandle;
    *a2 = 1;
    CloseHandle(v6);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      else
        return (unsigned int)LastError;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18004052c  mov     [rsp+arg_8], rbx
0x180040531  mov     [rsp+TokenHandle], rcx
0x180040536  push    rdi
0x180040537  sub     rsp, 20h
0x18004053b  mov     rdi, rdx
0x18004053e  test    rdx, rdx
0x180040541  jnz     short loc_18004054A
0x180040543  mov     eax, 80004003h
0x180040548  jmp     short loc_1800405A4
0x18004054a  xor     ebx, ebx
0x18004054c  mov     [rdx], ebx
0x18004054e  mov     [rsp+28h+TokenHandle], rbx
0x180040553  call    cs:__imp_GetCurrentThread
0x180040559  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18004055e  xor     r8d, r8d; OpenAsSelf
0x180040561  mov     rcx, rax; ThreadHandle
0x180040564  lea     edx, [rbx+8]; DesiredAccess
0x180040567  call    cs:__imp_OpenThreadToken
0x18004056d  test    eax, eax
0x18004056f  jz      short loc_180040584
0x180040571  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180040576  mov     dword ptr [rdi], 1
0x18004057c  call    cs:__imp_CloseHandle
0x180040582  jmp     short loc_1800405A2
0x180040584  call    cs:__imp_GetLastError
0x18004058a  cmp     eax, 3F0h
0x18004058f  jz      short loc_1800405A2
0x180040591  test    eax, eax
0x180040593  jg      short loc_180040599
0x180040595  mov     ebx, eax
0x180040597  jmp     short loc_1800405A2
0x180040599  movzx   ebx, ax
0x18004059c  or      ebx, 80070000h
0x1800405a2  mov     eax, ebx
0x1800405a4  mov     rbx, [rsp+28h+arg_8]
0x1800405a9  add     rsp, 20h
0x1800405ad  pop     rdi
0x1800405ae  retn
```
