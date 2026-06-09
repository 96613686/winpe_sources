# TimeoutManager::StartNewThread(void)

- ea: `0x18004105c`
- end: `0x180041150`
- name: `?StartNewThread@TimeoutManager@@AEAAHXZ`
- size: `244`
- prototype: `__int64 __fastcall(TimeoutManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800411ec`

## callees

- `0x18004105c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800410b7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180041127`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800410b7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180041127`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180041095`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180041095`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800410a9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800410a9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800410e3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800410e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800410fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800410fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800410f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004113d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800410f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004113d`

## pseudocode

```c
__int64 __fastcall TimeoutManager::StartNewThread(TimeoutManager *this)
{
  unsigned int v1; // ebx
  HANDLE CurrentThread; // rax
  BOOL v3; // edi
  HANDLE Thread; // rax
  TimeoutManager *ThreadId; // [rsp+40h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  ThreadId = this;
  v1 = 1;
  if ( _InterlockedIncrement((_DWORD *)&qword_180064218 + 1) == 1 )
  {
    LODWORD(ThreadId) = 0;
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      v3 = SetThreadToken(0, 0);
    }
    else
    {
      v3 = 0;
      if ( GetLastError() != 1008 )
      {
        _InterlockedDecrement((_DWORD *)&qword_180064218 + 1);
        return 0;
      }
    }
    Thread = CreateThread(0, 0, TimeoutManager::ThreadLoop, &g_TimeoutManager, 0, (LPDWORD)&ThreadId);
    if ( Thread )
    {
      CloseHandle(Thread);
    }
    else
    {
      v1 = 0;
      _InterlockedDecrement((_DWORD *)&qword_180064218 + 1);
    }
    if ( v3 )
      v1 &= -SetThreadToken(0, TokenHandle);
    if ( TokenHandle )
      CloseHandle(TokenHandle);
  }
  return v1;
}

```

## disassembly

```asm
0x18004105c  mov     [rsp+arg_10], rbx
0x180041061  mov     [rsp+ThreadId], rcx
0x180041066  push    rdi
0x180041067  sub     rsp, 30h
0x18004106b  mov     ebx, 1
0x180041070  mov     eax, ebx
0x180041072  lock xadd dword ptr cs:qword_180064218+4, eax
0x18004107a  add     eax, ebx
0x18004107c  cmp     eax, ebx
0x18004107e  jnz     loc_180041143
0x180041084  mov     dword ptr [rsp+38h+ThreadId], 0
0x18004108c  mov     [rsp+38h+TokenHandle], 0
0x180041095  call    cs:__imp_GetCurrentThread
0x18004109b  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800410a0  mov     r8d, ebx; OpenAsSelf
0x1800410a3  mov     rcx, rax; ThreadHandle
0x1800410a6  lea     edx, [rbx+3]; DesiredAccess
0x1800410a9  call    cs:__imp_OpenThreadToken
0x1800410af  test    eax, eax
0x1800410b1  jz      short loc_1800410F9
0x1800410b3  xor     edx, edx; Token
0x1800410b5  xor     ecx, ecx; Thread
0x1800410b7  call    cs:__imp_SetThreadToken
0x1800410bd  mov     edi, eax
0x1800410bf  lea     rax, [rsp+38h+ThreadId]
0x1800410c4  xor     edx, edx; dwStackSize
0x1800410c6  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800410cb  lea     r9, ?g_TimeoutManager@@3VTimeoutManager@@A; lpParameter
0x1800410d2  lea     r8, ?ThreadLoop@TimeoutManager@@CAKPEAX@Z; lpStartAddress
0x1800410d9  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800410e1  xor     ecx, ecx; lpThreadAttributes
0x1800410e3  call    cs:__imp_CreateThread
0x1800410e9  test    rax, rax
0x1800410ec  jz      short loc_180041113
0x1800410ee  mov     rcx, rax; hObject
0x1800410f1  call    cs:__imp_CloseHandle
0x1800410f7  jmp     short loc_18004111C
0x1800410f9  xor     edi, edi
0x1800410fb  call    cs:__imp_GetLastError
0x180041101  cmp     eax, 3F0h
0x180041106  jz      short loc_1800410BF
0x180041108  lock dec dword ptr cs:qword_180064218+4
0x18004110f  xor     eax, eax
0x180041111  jmp     short loc_180041145
0x180041113  xor     ebx, ebx
0x180041115  lock dec dword ptr cs:qword_180064218+4
0x18004111c  test    edi, edi
0x18004111e  jz      short loc_180041133
0x180041120  mov     rdx, [rsp+38h+TokenHandle]; Token
0x180041125  xor     ecx, ecx; Thread
0x180041127  call    cs:__imp_SetThreadToken
0x18004112d  neg     eax
0x18004112f  sbb     ecx, ecx
0x180041131  and     ebx, ecx
0x180041133  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180041138  test    rcx, rcx
0x18004113b  jz      short loc_180041143
0x18004113d  call    cs:__imp_CloseHandle
0x180041143  mov     eax, ebx
0x180041145  mov     rbx, [rsp+38h+arg_10]
0x18004114a  add     rsp, 30h
0x18004114e  pop     rdi
0x18004114f  retn
```
