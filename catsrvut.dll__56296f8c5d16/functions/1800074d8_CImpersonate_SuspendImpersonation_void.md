# CImpersonate::SuspendImpersonation(void)

- ea: `0x1800074d8`
- end: `0x180007576`
- name: `?SuspendImpersonation@CImpersonate@@QEAAJXZ`
- size: `158`
- prototype: `__int64 __fastcall(CImpersonate *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180003150`
- `0x180009574`
- `0x180009f84`
- `0x1800300d0`
- `0x1800304d0`

## callees

- `0x1800074d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000755b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000755b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000752b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000752b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007510`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180007510`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800074fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800074fd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000751e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000751e`

## pseudocode

```c
__int64 __fastcall CImpersonate::SuspendImpersonation(CImpersonate *this)
{
  unsigned int v3; // ebx
  void **v4; // rsi
  HANDLE CurrentThread; // rax
  signed int LastError; // eax

  if ( (*((_BYTE *)this + 8) & 1) != 0 )
    return 2147549183LL;
  v3 = 0;
  v4 = (void **)((char *)this + 16);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 1, v4) )
  {
    LastError = GetLastError();
    if ( LastError != 1008 )
    {
      if ( LastError <= 0 )
        return (unsigned int)LastError;
      return (unsigned __int16)LastError | 0x80070000;
    }
LABEL_9:
    *((_DWORD *)this + 2) |= 1u;
    return v3;
  }
  if ( SetThreadToken(0, 0) )
    goto LABEL_9;
  CloseHandle(*v4);
  *v4 = 0;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return v3;
}

```

## disassembly

```asm
0x1800074d8  mov     [rsp+arg_0], rbx
0x1800074dd  mov     [rsp+arg_8], rsi
0x1800074e2  push    rdi
0x1800074e3  sub     rsp, 20h
0x1800074e7  test    byte ptr [rcx+8], 1
0x1800074eb  mov     rdi, rcx
0x1800074ee  jz      short loc_1800074F7
0x1800074f0  mov     eax, 8000FFFFh
0x1800074f5  jmp     short loc_18000754B
0x1800074f7  xor     ebx, ebx
0x1800074f9  lea     rsi, [rcx+10h]
0x1800074fd  call    cs:__imp_GetCurrentThread
0x180007503  mov     r9, rsi; TokenHandle
0x180007506  lea     edx, [rbx+4]; DesiredAccess
0x180007509  mov     rcx, rax; ThreadHandle
0x18000750c  lea     r8d, [rbx+1]; OpenAsSelf
0x180007510  call    cs:__imp_OpenThreadToken
0x180007516  test    eax, eax
0x180007518  jz      short loc_18000755B
0x18000751a  xor     edx, edx; Token
0x18000751c  xor     ecx, ecx; Thread
0x18000751e  call    cs:__imp_SetThreadToken
0x180007524  test    eax, eax
0x180007526  jnz     short loc_180007568
0x180007528  mov     rcx, [rsi]; hObject
0x18000752b  call    cs:__imp_CloseHandle
0x180007531  mov     [rsi], rbx
0x180007534  call    cs:__imp_GetLastError
0x18000753a  mov     ebx, eax
0x18000753c  test    eax, eax
0x18000753e  jle     short loc_180007549
0x180007540  movzx   ebx, ax
0x180007543  or      ebx, 80070000h
0x180007549  mov     eax, ebx
0x18000754b  mov     rbx, [rsp+28h+arg_0]
0x180007550  mov     rsi, [rsp+28h+arg_8]
0x180007555  add     rsp, 20h
0x180007559  pop     rdi
0x18000755a  retn
0x18000755b  call    cs:__imp_GetLastError
0x180007561  cmp     eax, 3F0h
0x180007566  jnz     short loc_18000756E
0x180007568  or      dword ptr [rdi+8], 1
0x18000756c  jmp     short loc_180007549
0x18000756e  test    eax, eax
0x180007570  jg      short loc_180007540
0x180007572  mov     ebx, eax
0x180007574  jmp     short loc_180007549
```
