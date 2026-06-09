# SuspendImpersonate(void * *)

- ea: `0x180011fb4`
- end: `0x180012017`
- name: `?SuspendImpersonate@@YAJPEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180011cd4`
- `0x180011d30`
- `0x180014840`
- `0x1800161e0`
- `0x180058ce8`

## callees

- `0x180011fb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011fe9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011fe9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011fd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011fd4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011ff7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011ff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fff`

## pseudocode

```c
signed int __fastcall SuspendImpersonate(PHANDLE TokenHandle)
{
  signed int result; // eax
  HANDLE CurrentThread; // rax

  *TokenHandle = 0;
  if ( !NtCurrentTeb()->IsImpersonating )
    return 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, TokenHandle) )
  {
    SetThreadToken(0, 0);
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180011fb4  push    rbx
0x180011fb6  sub     rsp, 20h
0x180011fba  mov     qword ptr [rcx], 0
0x180011fc1  mov     rbx, rcx
0x180011fc4  mov     eax, gs:179Ch
0x180011fcc  test    eax, eax
0x180011fce  jnz     short loc_180011FD4
0x180011fd0  xor     eax, eax
0x180011fd2  jmp     short loc_180012011
0x180011fd4  call    cs:__imp_GetCurrentThread
0x180011fda  mov     edx, 4; DesiredAccess
0x180011fdf  mov     r9, rbx; TokenHandle
0x180011fe2  mov     rcx, rax; ThreadHandle
0x180011fe5  lea     r8d, [rdx-3]; OpenAsSelf
0x180011fe9  call    cs:__imp_OpenThreadToken
0x180011fef  test    eax, eax
0x180011ff1  jz      short loc_180011FFF
0x180011ff3  xor     edx, edx; Token
0x180011ff5  xor     ecx, ecx; Thread
0x180011ff7  call    cs:__imp_SetThreadToken
0x180011ffd  jmp     short loc_180011FD0
0x180011fff  call    cs:__imp_GetLastError
0x180012005  test    eax, eax
0x180012007  jle     short loc_180012011
0x180012009  movzx   eax, ax
0x18001200c  or      eax, 80070000h
0x180012011  add     rsp, 20h
0x180012015  pop     rbx
0x180012016  retn
```
