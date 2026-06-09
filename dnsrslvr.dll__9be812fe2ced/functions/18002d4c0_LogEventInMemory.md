# LogEventInMemory

- ea: `0x18002d4c0`
- end: `0x18002d5aa`
- name: `LogEventInMemory`
- size: `234`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002d290`
- `0x18002d6f8`
- `0x18003cfc0`
- `0x18003d4b0`
- `0x1800495c0`

## callees

- `0x18002d4c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d561`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d591`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d561`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d591`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d59f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d59f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d572`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002d572`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d515`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d515`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d4f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002d4f6`

## pseudocode

```c
LPVOID __fastcall LogEventInMemory(int a1, int a2)
{
  __int64 v4; // rbx
  LPVOID result; // rax
  int v6; // eax
  SIZE_T v7; // rbx
  HANDLE ProcessHeap; // rax
  void *v9; // rbx
  HANDLE v10; // rax

  if ( g_pEventArray )
    goto LABEL_2;
  v6 = g_EventArrayLength;
  if ( g_EventArrayLength > 0x10000 )
  {
    v6 = 0x10000;
    g_EventArrayLength = 0x10000;
  }
  v7 = 16LL * v6;
  ProcessHeap = GetProcessHeap();
  result = HeapAlloc(ProcessHeap, 8u, v7);
  v9 = result;
  if ( result )
  {
    if ( _InterlockedCompareExchange64(&g_pEventArray, (signed __int64)result, 0) )
    {
      v10 = GetProcessHeap();
      HeapFree(v10, 0, v9);
    }
LABEL_2:
    v4 = 2LL * (_InterlockedIncrement(&g_EventIndex) % (unsigned int)g_EventArrayLength);
    *(_DWORD *)(g_pEventArray + 8 * v4 + 4) = GetTickCount();
    *(_DWORD *)(g_pEventArray + 8 * v4 + 8) = a1;
    *(_DWORD *)(g_pEventArray + 8 * v4) = (__int16)GetCurrentThreadId();
    result = (LPVOID)g_pEventArray;
    *(_DWORD *)(g_pEventArray + 8 * v4 + 12) = a2;
  }
  return result;
}

```

## disassembly

```asm
0x18002d4c0  mov     [rsp+arg_0], rbx
0x18002d4c5  mov     [rsp+arg_8], rsi
0x18002d4ca  push    rdi
0x18002d4cb  sub     rsp, 20h
0x18002d4cf  cmp     cs:g_pEventArray, 0
0x18002d4d7  mov     edi, edx
0x18002d4d9  mov     esi, ecx
0x18002d4db  jz      short loc_18002D543
0x18002d4dd  mov     eax, 1
0x18002d4e2  lock xadd cs:g_EventIndex, eax
0x18002d4ea  inc     eax
0x18002d4ec  xor     edx, edx
0x18002d4ee  div     cs:g_EventArrayLength
0x18002d4f4  mov     ebx, edx
0x18002d4f6  call    cs:__imp_GetTickCount
0x18002d4fc  mov     rcx, cs:g_pEventArray
0x18002d503  add     rbx, rbx
0x18002d506  mov     [rcx+rbx*8+4], eax
0x18002d50a  mov     rax, cs:g_pEventArray
0x18002d511  mov     [rax+rbx*8+8], esi
0x18002d515  call    cs:__imp_GetCurrentThreadId
0x18002d51b  movsx   ecx, ax
0x18002d51e  mov     rax, cs:g_pEventArray
0x18002d525  mov     [rax+rbx*8], ecx
0x18002d528  mov     rax, cs:g_pEventArray
0x18002d52f  mov     [rax+rbx*8+0Ch], edi
0x18002d533  mov     rbx, [rsp+28h+arg_0]
0x18002d538  mov     rsi, [rsp+28h+arg_8]
0x18002d53d  add     rsp, 20h
0x18002d541  pop     rdi
0x18002d542  retn
0x18002d543  mov     eax, cs:g_EventArrayLength
0x18002d549  mov     ecx, 10000h
0x18002d54e  cmp     eax, ecx
0x18002d550  jle     short loc_18002D55A
0x18002d552  mov     eax, ecx
0x18002d554  mov     cs:g_EventArrayLength, ecx
0x18002d55a  movsxd  rbx, eax
0x18002d55d  shl     rbx, 4
0x18002d561  call    cs:__imp_GetProcessHeap
0x18002d567  mov     r8, rbx; dwBytes
0x18002d56a  mov     edx, 8; dwFlags
0x18002d56f  mov     rcx, rax; hHeap
0x18002d572  call    cs:__imp_HeapAlloc
0x18002d578  mov     rbx, rax
0x18002d57b  test    rax, rax
0x18002d57e  jz      short loc_18002D533
0x18002d580  xor     eax, eax
0x18002d582  lock cmpxchg cs:g_pEventArray, rbx
0x18002d58b  jz      loc_18002D4DD
0x18002d591  call    cs:__imp_GetProcessHeap
0x18002d597  mov     r8, rbx; lpMem
0x18002d59a  xor     edx, edx; dwFlags
0x18002d59c  mov     rcx, rax; hHeap
0x18002d59f  call    cs:__imp_HeapFree
0x18002d5a5  jmp     loc_18002D4DD
```
