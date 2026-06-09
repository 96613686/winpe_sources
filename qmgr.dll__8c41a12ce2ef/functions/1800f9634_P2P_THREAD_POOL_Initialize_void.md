# P2P_THREAD_POOL::Initialize(void)

- ea: `0x1800f9634`
- end: `0x1800f970f`
- name: `?Initialize@P2P_THREAD_POOL@@QEAAKXZ`
- size: `219`
- prototype: `unsigned int __fastcall(P2P_THREAD_POOL *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800f95a8`

## callees

- `0x18009c7c0`
- `0x1800f9634`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800f9697`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800f9697`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800f96ea`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800f96ea`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800f96ca`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800f96ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f966c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f966c`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800f965e`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800f965e`

## pseudocode

```c
DWORD __fastcall P2P_THREAD_POOL::Initialize(P2P_THREAD_POOL *this)
{
  HANDLE IoCompletionPort; // rax
  __int64 i; // rdi
  HANDLE v5; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF
  HMODULE phModule; // [rsp+48h] [rbp+10h] BYREF

  phModule = 0;
  ThreadId = 0;
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
  *(_QWORD *)this = IoCompletionPort;
  if ( !IoCompletionPort )
    return GetLastError();
  for ( i = 0; !(_DWORD)i; i = 1 )
  {
    _InterlockedIncrement((volatile signed __int32 *)this + 14);
    if ( !GetModuleHandleExW(4u, (LPCWSTR)P2P_THREAD_POOL::WorkerThreadRoutine, &phModule) )
    {
      P2P_THREAD_POOL::Dereference(this);
      return GetLastError();
    }
    *((_QWORD *)this + 6) = phModule;
    v5 = CreateThread(0, 0, P2P_THREAD_POOL::WorkerThreadRoutine, this, 0, &ThreadId);
    *((_QWORD *)this + i + 1) = v5;
    if ( !v5 )
    {
      P2P_THREAD_POOL::Dereference(this);
      FreeLibrary(*((HMODULE *)this + 6));
      return GetLastError();
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800f9634  mov     [rsp+arg_10], rbx
0x1800f9639  push    rdi
0x1800f963a  sub     rsp, 30h
0x1800f963e  mov     rbx, rcx
0x1800f9641  mov     [rsp+38h+phModule], 0
0x1800f964a  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x1800f964e  mov     [rsp+38h+ThreadId], 0
0x1800f9656  xor     r9d, r9d; NumberOfConcurrentThreads
0x1800f9659  xor     r8d, r8d; CompletionKey
0x1800f965c  xor     edx, edx; ExistingCompletionPort
0x1800f965e  call    cs:__imp_CreateIoCompletionPort
0x1800f9664  mov     [rbx], rax
0x1800f9667  test    rax, rax
0x1800f966a  jnz     short loc_1800F9677
0x1800f966c  call    cs:__imp_GetLastError
0x1800f9672  jmp     loc_1800F9704
0x1800f9677  xor     edi, edi
0x1800f9679  cmp     edi, 1
0x1800f967c  jnb     loc_1800F9702
0x1800f9682  lock inc dword ptr [rbx+38h]
0x1800f9686  lea     r8, [rsp+38h+phModule]; phModule
0x1800f968b  mov     ecx, 4; dwFlags
0x1800f9690  lea     rdx, ?WorkerThreadRoutine@P2P_THREAD_POOL@@CAKPEAX@Z; lpModuleName
0x1800f9697  call    cs:__imp_GetModuleHandleExW
0x1800f969d  test    eax, eax
0x1800f969f  jz      short loc_1800F96F5
0x1800f96a1  mov     rax, [rsp+38h+phModule]
0x1800f96a6  lea     r8, ?WorkerThreadRoutine@P2P_THREAD_POOL@@CAKPEAX@Z; lpStartAddress
0x1800f96ad  mov     [rbx+30h], rax
0x1800f96b1  mov     r9, rbx; lpParameter
0x1800f96b4  lea     rax, [rsp+38h+ThreadId]
0x1800f96b9  xor     edx, edx; dwStackSize
0x1800f96bb  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800f96c0  xor     ecx, ecx; lpThreadAttributes
0x1800f96c2  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800f96ca  call    cs:__imp_CreateThread
0x1800f96d0  mov     [rbx+rdi*8+8], rax
0x1800f96d5  test    rax, rax
0x1800f96d8  jz      short loc_1800F96DE
0x1800f96da  inc     edi
0x1800f96dc  jmp     short loc_1800F9679
0x1800f96de  mov     rcx, rbx; this
0x1800f96e1  call    ?Dereference@P2P_THREAD_POOL@@AEAAXXZ; P2P_THREAD_POOL::Dereference(void)
0x1800f96e6  mov     rcx, [rbx+30h]; hLibModule
0x1800f96ea  call    cs:__imp_FreeLibrary
0x1800f96f0  jmp     loc_1800F966C
0x1800f96f5  mov     rcx, rbx; this
0x1800f96f8  call    ?Dereference@P2P_THREAD_POOL@@AEAAXXZ; P2P_THREAD_POOL::Dereference(void)
0x1800f96fd  jmp     loc_1800F966C
0x1800f9702  xor     eax, eax
0x1800f9704  mov     rbx, [rsp+38h+arg_10]
0x1800f9709  add     rsp, 30h
0x1800f970d  pop     rdi
0x1800f970e  retn
```
