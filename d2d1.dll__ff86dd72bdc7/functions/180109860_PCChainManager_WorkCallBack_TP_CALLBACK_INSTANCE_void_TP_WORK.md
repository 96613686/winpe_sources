# PCChainManager::WorkCallBack(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180109860`
- end: `0x180109a2e`
- name: `?WorkCallBack@PCChainManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `462`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180109860`
- `0x180109af4`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801099b7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1801099b7`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801099f6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180109a1c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801099f6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180109a1c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801099e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180109a08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801099e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180109a08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801098e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109975`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801098e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109975`

## pseudocode

```c
void __fastcall PCChainManager::WorkCallBack(
        PTP_CALLBACK_INSTANCE Instance,
        volatile signed __int32 *Context,
        PTP_WORK Work)
{
  int v4; // ebx
  unsigned __int32 v5; // ebp
  LPVOID v6; // rax
  volatile int v7; // ecx
  __int64 v8; // rdx
  _DWORD *v9; // rdi
  __int64 v10; // rsi
  __int64 v11; // rcx
  LPVOID v12; // rax
  volatile int v13; // ecx
  __int64 v14; // rdx
  _DWORD *v15; // rdi
  __int64 v16; // rsi
  void *v17; // rcx
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax

  v4 = _mm_getcsr();
  if ( (v4 & 0xFF80) != 0x1F80 )
    _mm_setcsr(0x1F80u);
  v5 = _InterlockedExchangeAdd(Context + 13, 1u);
  if ( _InterlockedCompareExchange(&dword_1805DBFBC, 1, 0) )
  {
    v6 = pvAddress;
  }
  else
  {
    ProcessHeap = GetProcessHeap();
    v6 = HeapAlloc(ProcessHeap, 8u, 0x1800u);
    pvAddress = v6;
  }
  if ( v6 )
  {
    EnsureThreadTraceRegisteredWithWER();
    do
    {
      v7 = g_nCurrentThreadTraceIndex;
      v8 = (unsigned __int8)(g_nCurrentThreadTraceIndex + 1);
    }
    while ( v7 != _InterlockedCompareExchange(&g_nCurrentThreadTraceIndex, v8, g_nCurrentThreadTraceIndex) );
    v9 = pvAddress;
    v10 = 3 * v8;
    v9[2 * v10] = GetCurrentThreadId();
    v9[2 * v10 + 1] = 0;
    v9[2 * v10 + 2] = v5;
    v9[2 * v10 + 3] = 0;
    *(_QWORD *)&v9[2 * v10 + 4] = Context;
  }
  v11 = *(_QWORD *)(*(_QWORD *)Context + 8LL * v5);
  (*(void (__fastcall **)(__int64, volatile signed __int32 *, PTP_WORK))(*(_QWORD *)v11 + 8LL))(v11, Context, Work);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)Context + 3) + 4LL * v5), 0xFFFFFFFF) == 1 )
  {
    v17 = (void *)*((_QWORD *)Context + 8);
    *((_DWORD *)Context + 14) = v5;
    SetEvent(v17);
  }
  if ( _InterlockedCompareExchange(&dword_1805DBFBC, 1, 0) )
  {
    v12 = pvAddress;
  }
  else
  {
    v19 = GetProcessHeap();
    v12 = HeapAlloc(v19, 8u, 0x1800u);
    pvAddress = v12;
  }
  if ( v12 )
  {
    EnsureThreadTraceRegisteredWithWER();
    do
    {
      v13 = g_nCurrentThreadTraceIndex;
      v14 = (unsigned __int8)(g_nCurrentThreadTraceIndex + 1);
    }
    while ( v13 != _InterlockedCompareExchange(&g_nCurrentThreadTraceIndex, v14, g_nCurrentThreadTraceIndex) );
    v15 = pvAddress;
    v16 = 3 * v14;
    v15[2 * v16] = GetCurrentThreadId();
    v15[2 * v16 + 1] = 1;
    v15[2 * v16 + 2] = v5;
    v15[2 * v16 + 3] = 0;
    *(_QWORD *)&v15[2 * v16 + 4] = Context;
  }
  if ( (v4 & 0xFF80) != 0x1F80 )
    _mm_setcsr(v4 & 0xFFFFFFC0);
}

```

## disassembly

```asm
0x180109860  push    rbx
0x180109862  push    rbp
0x180109863  push    rsi
0x180109864  push    rdi
0x180109865  push    r12
0x180109867  push    r14
0x180109869  sub     rsp, 28h
0x18010986d  mov     r14, rdx
0x180109870  stmxcsr [rsp+58h+arg_8]
0x180109875  mov     ebx, [rsp+58h+arg_8]
0x180109879  mov     eax, ebx
0x18010987b  and     eax, 0FF80h
0x180109880  cmp     eax, 1F80h
0x180109885  jnz     loc_1801099C2
0x18010988b  mov     r12d, 1
0x180109891  mov     ebp, r12d
0x180109894  lock xadd [rdx+34h], ebp
0x180109899  xor     eax, eax
0x18010989b  lock cmpxchg cs:dword_1805DBFBC, r12d
0x1801098a4  jz      loc_1801099E2
0x1801098aa  mov     rax, cs:pvAddress
0x1801098b1  test    rax, rax
0x1801098b4  jz      short loc_180109902
0x1801098b6  call    ?EnsureThreadTraceRegisteredWithWER@@YAXXZ; EnsureThreadTraceRegisteredWithWER(void)
0x1801098bb  mov     ecx, cs:?g_nCurrentThreadTraceIndex@@3JC; long volatile g_nCurrentThreadTraceIndex
0x1801098c1  lea     eax, [rcx+1]
0x1801098c4  movzx   edx, al
0x1801098c7  mov     eax, ecx
0x1801098c9  lock cmpxchg cs:?g_nCurrentThreadTraceIndex@@3JC, edx; long volatile g_nCurrentThreadTraceIndex
0x1801098d1  cmp     ecx, eax
0x1801098d3  jnz     short loc_1801098BB
0x1801098d5  mov     rdi, cs:pvAddress
0x1801098dc  lea     rsi, [rdx+rdx*2]
0x1801098e0  call    cs:__imp_GetCurrentThreadId
0x1801098e6  mov     [rdi+rsi*8], eax
0x1801098e9  mov     dword ptr [rdi+rsi*8+4], 0
0x1801098f1  mov     [rdi+rsi*8+8], ebp
0x1801098f5  mov     dword ptr [rdi+rsi*8+0Ch], 0
0x1801098fd  mov     [rdi+rsi*8+10h], r14
0x180109902  mov     rax, [r14]
0x180109905  mov     ecx, ebp
0x180109907  mov     rcx, [rax+rcx*8]
0x18010990b  mov     rax, [rcx]
0x18010990e  mov     rax, [rax+8]
0x180109912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109917  mov     rcx, [r14+18h]
0x18010991b  or      eax, 0FFFFFFFFh
0x18010991e  mov     edx, ebp
0x180109920  lock xadd [rcx+rdx*4], eax
0x180109925  cmp     eax, r12d
0x180109928  jz      loc_1801099AF
0x18010992e  xor     eax, eax
0x180109930  lock cmpxchg cs:dword_1805DBFBC, r12d
0x180109939  jz      loc_180109A08
0x18010993f  mov     rax, cs:pvAddress
0x180109946  test    rax, rax
0x180109949  jz      short loc_180109994
0x18010994b  call    ?EnsureThreadTraceRegisteredWithWER@@YAXXZ; EnsureThreadTraceRegisteredWithWER(void)
0x180109950  mov     ecx, cs:?g_nCurrentThreadTraceIndex@@3JC; long volatile g_nCurrentThreadTraceIndex
0x180109956  lea     eax, [rcx+1]
0x180109959  movzx   edx, al
0x18010995c  mov     eax, ecx
0x18010995e  lock cmpxchg cs:?g_nCurrentThreadTraceIndex@@3JC, edx; long volatile g_nCurrentThreadTraceIndex
0x180109966  cmp     ecx, eax
0x180109968  jnz     short loc_180109950
0x18010996a  mov     rdi, cs:pvAddress
0x180109971  lea     rsi, [rdx+rdx*2]
0x180109975  call    cs:__imp_GetCurrentThreadId
0x18010997b  mov     [rdi+rsi*8], eax
0x18010997e  mov     [rdi+rsi*8+4], r12d
0x180109983  mov     [rdi+rsi*8+8], ebp
0x180109987  mov     dword ptr [rdi+rsi*8+0Ch], 0
0x18010998f  mov     [rdi+rsi*8+10h], r14
0x180109994  mov     eax, ebx
0x180109996  and     eax, 0FF80h
0x18010999b  cmp     eax, 1F80h
0x1801099a0  jnz     short loc_1801099D4
0x1801099a2  add     rsp, 28h
0x1801099a6  pop     r14
0x1801099a8  pop     r12
0x1801099aa  pop     rdi
0x1801099ab  pop     rsi
0x1801099ac  pop     rbp
0x1801099ad  pop     rbx
0x1801099ae  retn
0x1801099af  mov     rcx, [r14+40h]; hEvent
0x1801099b3  mov     [r14+38h], ebp
0x1801099b7  call    cs:__imp_SetEvent
0x1801099bd  jmp     loc_18010992E
0x1801099c2  mov     [rsp+58h+arg_8], 1F80h
0x1801099ca  ldmxcsr [rsp+58h+arg_8]
0x1801099cf  jmp     loc_18010988B
0x1801099d4  and     ebx, 0FFFFFFC0h
0x1801099d7  mov     [rsp+58h+arg_8], ebx
0x1801099db  ldmxcsr [rsp+58h+arg_8]
0x1801099e0  jmp     short loc_1801099A2
0x1801099e2  call    cs:__imp_GetProcessHeap
0x1801099e8  mov     edx, 8; dwFlags
0x1801099ed  mov     r8d, 1800h; dwBytes
0x1801099f3  mov     rcx, rax; hHeap
0x1801099f6  call    cs:__imp_HeapAlloc
0x1801099fc  mov     cs:pvAddress, rax
0x180109a03  jmp     loc_1801098B1
0x180109a08  call    cs:__imp_GetProcessHeap
0x180109a0e  mov     edx, 8; dwFlags
0x180109a13  mov     r8d, 1800h; dwBytes
0x180109a19  mov     rcx, rax; hHeap
0x180109a1c  call    cs:__imp_HeapAlloc
0x180109a22  mov     cs:pvAddress, rax
0x180109a29  jmp     loc_180109946
```
