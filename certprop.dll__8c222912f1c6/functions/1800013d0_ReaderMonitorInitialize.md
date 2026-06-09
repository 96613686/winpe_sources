# ReaderMonitorInitialize

- ea: `0x1800013d0`
- end: `0x180001562`
- name: `ReaderMonitorInitialize`
- size: `402`
- prototype: `DWORD __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180002690`
- `0x18000ec48`

## callees

- `0x1800013d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000152c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18000152c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000142e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000145d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001476`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000148f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000142e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000145d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001476`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000148f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800014c7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800014c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800014ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800014ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800014d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000144c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800014d6`
- `ntdll!RtlInitializeCriticalSection` at `0x1800013e8`
- `ntdll!RtlInitializeCriticalSection` at `0x1800013e8`

## pseudocode

```c
DWORD __fastcall ReaderMonitorInitialize(__int64 a1)
{
  HANDLE EventW; // rax
  HANDLE v4; // rax
  HANDLE v5; // rax
  HANDLE v6; // rax
  DWORD LastError; // esi
  HANDLE CurrentThread; // rax
  PTP_CLEANUP_GROUP ThreadpoolCleanupGroup; // rax

  hHeap = *(HANDLE *)(a1 + 32);
  if ( RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)(a1 + 48)) )
    return 8;
  *(_QWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  *(_DWORD *)(a1 + 216) = 1;
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 88) = EventW;
  if ( !EventW )
    return GetLastError();
  v4 = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 96) = v4;
  if ( !v4 )
    return GetLastError();
  v5 = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 104) = v5;
  if ( !v5 )
    return GetLastError();
  v6 = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 240) = v6;
  if ( !v6 )
    return GetLastError();
  LastError = 0;
  if ( *(_DWORD *)a1 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 4u, 1, (PHANDLE)(a1 + 248)) )
      LastError = GetLastError();
  }
  *(_DWORD *)(a1 + 136) = 3;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_DWORD *)(a1 + 192) = 0;
  *(_DWORD *)(a1 + 196) = 1;
  *(_DWORD *)(a1 + 200) = 72;
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  *(_QWORD *)(a1 + 208) = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
    return GetLastError();
  *(_QWORD *)(a1 + 152) = ThreadpoolCleanupGroup;
  *(_QWORD *)(a1 + 160) = 0;
  return LastError;
}

```

## disassembly

```asm
0x1800013d0  push    rbx
0x1800013d2  sub     rsp, 20h
0x1800013d6  mov     rax, [rcx+20h]
0x1800013da  mov     rbx, rcx
0x1800013dd  add     rcx, 30h ; '0'; CriticalSection
0x1800013e1  mov     cs:hHeap, rax
0x1800013e8  call    cs:__imp_RtlInitializeCriticalSection
0x1800013ee  test    eax, eax
0x1800013f0  jz      short loc_1800013FC
0x1800013f2  mov     eax, 8
0x1800013f7  jmp     loc_18000155C
0x1800013fc  mov     [rsp+28h+arg_0], rbp
0x180001401  xor     r9d, r9d; lpName
0x180001404  xor     ebp, ebp
0x180001406  mov     [rsp+28h+arg_8], rsi
0x18000140b  xor     r8d, r8d; bInitialState
0x18000140e  mov     [rbx+108h], rbp
0x180001415  xor     edx, edx; bManualReset
0x180001417  mov     [rbx+78h], rbp
0x18000141b  xor     ecx, ecx; lpEventAttributes
0x18000141d  mov     [rbx+80h], rbp
0x180001424  mov     dword ptr [rbx+0D8h], 1
0x18000142e  call    cs:__imp_CreateEventW
0x180001434  mov     [rbx+58h], rax
0x180001438  test    rax, rax
0x18000143b  jnz     short loc_180001453
0x18000143d  mov     rsi, [rsp+28h+arg_8]
0x180001442  mov     rbp, [rsp+28h+arg_0]
0x180001447  add     rsp, 20h
0x18000144b  pop     rbx
0x18000144c  jmp     cs:__imp_GetLastError
0x180001453  xor     r9d, r9d; lpName
0x180001456  xor     r8d, r8d; bInitialState
0x180001459  xor     edx, edx; bManualReset
0x18000145b  xor     ecx, ecx; lpEventAttributes
0x18000145d  call    cs:__imp_CreateEventW
0x180001463  mov     [rbx+60h], rax
0x180001467  test    rax, rax
0x18000146a  jz      short loc_18000143D
0x18000146c  xor     r9d, r9d; lpName
0x18000146f  xor     r8d, r8d; bInitialState
0x180001472  xor     edx, edx; bManualReset
0x180001474  xor     ecx, ecx; lpEventAttributes
0x180001476  call    cs:__imp_CreateEventW
0x18000147c  mov     [rbx+68h], rax
0x180001480  test    rax, rax
0x180001483  jz      short loc_18000143D
0x180001485  xor     r9d, r9d; lpName
0x180001488  xor     r8d, r8d; bInitialState
0x18000148b  xor     edx, edx; bManualReset
0x18000148d  xor     ecx, ecx; lpEventAttributes
0x18000148f  call    cs:__imp_CreateEventW
0x180001495  mov     [rbx+0F0h], rax
0x18000149c  test    rax, rax
0x18000149f  jz      short loc_18000143D
0x1800014a1  mov     esi, ebp
0x1800014a3  cmp     [rbx], ebp
0x1800014a5  jz      short loc_1800014DE
0x1800014a7  mov     [rsp+28h+arg_10], rdi
0x1800014ac  call    cs:__imp_GetCurrentThread
0x1800014b2  lea     r9, [rbx+0F8h]; TokenHandle
0x1800014b9  mov     edx, 4; DesiredAccess
0x1800014be  mov     rcx, rax; ThreadHandle
0x1800014c1  mov     r8d, 1; OpenAsSelf
0x1800014c7  call    cs:__imp_OpenThreadToken
0x1800014cd  mov     rdi, [rsp+28h+arg_10]
0x1800014d2  test    eax, eax
0x1800014d4  jnz     short loc_1800014DE
0x1800014d6  call    cs:__imp_GetLastError
0x1800014dc  mov     esi, eax
0x1800014de  mov     dword ptr [rbx+88h], 3
0x1800014e8  mov     [rbx+90h], rbp
0x1800014ef  mov     [rbx+98h], rbp
0x1800014f6  mov     [rbx+0A0h], rbp
0x1800014fd  mov     [rbx+0A8h], rbp
0x180001504  mov     [rbx+0B0h], rbp
0x18000150b  mov     [rbx+0B8h], rbp
0x180001512  mov     [rbx+0C0h], ebp
0x180001518  mov     dword ptr [rbx+0C4h], 1
0x180001522  mov     dword ptr [rbx+0C8h], 48h ; 'H'
0x18000152c  call    cs:__imp_CreateThreadpoolCleanupGroup
0x180001532  mov     [rbx+0D0h], rax
0x180001539  test    rax, rax
0x18000153c  jz      loc_18000143D
0x180001542  mov     [rbx+98h], rax
0x180001549  mov     [rbx+0A0h], rbp
0x180001550  mov     rbp, [rsp+28h+arg_0]
0x180001555  mov     eax, esi
0x180001557  mov     rsi, [rsp+28h+arg_8]
0x18000155c  add     rsp, 20h
0x180001560  pop     rbx
0x180001561  retn
```
