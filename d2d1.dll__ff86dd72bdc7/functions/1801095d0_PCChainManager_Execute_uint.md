# PCChainManager::Execute(uint)

- ea: `0x1801095d0`
- end: `0x18010982c`
- name: `?Execute@PCChainManager@@QEAAXI@Z`
- size: `604`
- prototype: `void __fastcall(PCChainManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180108870`

## callees

- `0x1801095d0`
- `0x180109834`
- `0x180109a40`
- `0x180109af4`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180109668`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180109668`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801097f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18010981a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801097f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18010981a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801097e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180109806`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801097e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180109806`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801097b3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1801097b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801096c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109776`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801096c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109776`

## pseudocode

```c
void __fastcall PCChainManager::Execute(PCChainManager *this, unsigned int a2)
{
  unsigned int i; // ebp
  __int64 v4; // rcx
  unsigned int v5; // ebx
  char v6; // r13
  __int64 v7; // r12
  LPVOID v8; // rax
  volatile int v9; // ecx
  __int64 v10; // rdx
  _DWORD *v11; // rbx
  __int64 v12; // rdi
  __int64 v13; // rcx
  int v14; // eax
  bool v15; // r15
  LPVOID v16; // rax
  volatile int v17; // ecx
  __int64 v18; // rdx
  _DWORD *v19; // rbx
  __int64 v20; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v22; // rax

  if ( a2 > 1 )
  {
    RecordThreadTraceEvent(4, 0, 0, this);
    if ( (unsigned int)(*((_DWORD *)this + 2) + *((_DWORD *)this + 12)) < *((_DWORD *)this + 2) )
      __int2c();
    v5 = 0;
    *((_DWORD *)this + 13) = 0;
    for ( *((_DWORD *)this + 14) = 0; v5 < *((_DWORD *)this + 12); ++v5 )
      PCChainManager::EnqueueNextProducerTask(this);
    v6 = 1;
    do
    {
      WaitForSingleObject(*((HANDLE *)this + 8), 0xFFFFFFFF);
      if ( *((_DWORD *)this + 14) >= *((_DWORD *)this + 2) )
        break;
      LODWORD(v7) = *((_DWORD *)this + 14);
      do
      {
        if ( _InterlockedCompareExchange(&dword_1805DBFBC, 1, 0) )
        {
          v8 = pvAddress;
        }
        else
        {
          ProcessHeap = GetProcessHeap();
          v8 = HeapAlloc(ProcessHeap, 8u, 0x1800u);
          pvAddress = v8;
        }
        if ( v8 )
        {
          EnsureThreadTraceRegisteredWithWER();
          do
          {
            v9 = g_nCurrentThreadTraceIndex;
            v10 = (unsigned __int8)(g_nCurrentThreadTraceIndex + 1);
          }
          while ( v9 != _InterlockedCompareExchange(&g_nCurrentThreadTraceIndex, v10, g_nCurrentThreadTraceIndex) );
          v11 = pvAddress;
          v12 = 3 * v10;
          v11[2 * v12] = GetCurrentThreadId();
          v11[2 * v12 + 1] = 2;
          v11[2 * v12 + 2] = v7;
          v11[2 * v12 + 3] = 0;
          *(_QWORD *)&v11[2 * v12 + 4] = this;
        }
        v13 = *(_QWORD *)(*(_QWORD *)this + 8LL * (unsigned int)v7);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        PCChainManager::EnqueueNextProducerTask(this);
        v14 = v7;
        v7 = (unsigned int)(v7 + 1);
        if ( v14 >= *((_DWORD *)this + 2) - 1 )
        {
          v15 = 0;
          v6 = 0;
        }
        else
        {
          v15 = _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)this + 3) + 4 * v7), 0xFFFFFFFF) == 0;
        }
        if ( _InterlockedCompareExchange(&dword_1805DBFBC, 1, 0) )
        {
          v16 = pvAddress;
        }
        else
        {
          v22 = GetProcessHeap();
          v16 = HeapAlloc(v22, 8u, 0x1800u);
          pvAddress = v16;
        }
        if ( v16 )
        {
          EnsureThreadTraceRegisteredWithWER();
          do
          {
            v17 = g_nCurrentThreadTraceIndex;
            v18 = (unsigned __int8)(g_nCurrentThreadTraceIndex + 1);
          }
          while ( v17 != _InterlockedCompareExchange(&g_nCurrentThreadTraceIndex, v18, g_nCurrentThreadTraceIndex) );
          v19 = pvAddress;
          v20 = 3 * v18;
          v19[2 * v20] = GetCurrentThreadId();
          v19[2 * v20 + 1] = 3;
          v19[2 * v20 + 2] = v7;
          v19[2 * v20 + 3] = !v15;
          *(_QWORD *)&v19[2 * v20 + 4] = this;
        }
      }
      while ( v15 );
    }
    while ( v6 );
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 9), 0);
    RecordThreadTraceEvent(5, 0, 0, this);
  }
  else
  {
    for ( i = 0; i < *((_DWORD *)this + 2); ++i )
    {
      v4 = *(_QWORD *)(*(_QWORD *)this + 8LL * i);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
}

```

## disassembly

```asm
0x1801095d0  push    rbx
0x1801095d2  push    rbp
0x1801095d3  push    rsi
0x1801095d4  push    rdi
0x1801095d5  push    r12
0x1801095d7  push    r13
0x1801095d9  push    r14
0x1801095db  push    r15
0x1801095dd  sub     rsp, 28h
0x1801095e1  mov     edi, 1
0x1801095e6  mov     rsi, rcx
0x1801095e9  cmp     edx, edi
0x1801095eb  ja      short loc_180109621
0x1801095ed  xor     ebp, ebp
0x1801095ef  cmp     [rcx+8], ebp
0x1801095f2  jbe     short loc_180109610
0x1801095f4  mov     rax, [rsi]
0x1801095f7  mov     ecx, ebp
0x1801095f9  mov     rcx, [rax+rcx*8]
0x1801095fd  mov     rax, [rcx]
0x180109600  mov     rax, [rax+10h]
0x180109604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109609  add     ebp, edi
0x18010960b  cmp     ebp, [rsi+8]
0x18010960e  jb      short loc_1801095F4
0x180109610  add     rsp, 28h
0x180109614  pop     r15
0x180109616  pop     r14
0x180109618  pop     r13
0x18010961a  pop     r12
0x18010961c  pop     rdi
0x18010961d  pop     rsi
0x18010961e  pop     rbp
0x18010961f  pop     rbx
0x180109620  retn
0x180109621  xor     edx, edx
0x180109623  mov     r9, rsi
0x180109626  xor     r8d, r8d
0x180109629  lea     ecx, [rdx+4]
0x18010962c  call    ?RecordThreadTraceEvent@@YAXW4Enum@ThreadTraceEvent@@KHPEAVPCChainManager@@@Z; RecordThreadTraceEvent(ThreadTraceEvent::Enum,ulong,int,PCChainManager *)
0x180109631  mov     ecx, [rsi+30h]
0x180109634  add     ecx, [rsi+8]
0x180109637  cmp     ecx, [rsi+8]
0x18010963a  jb      loc_1801097D9
0x180109640  xor     ebp, ebp
0x180109642  mov     ebx, ebp
0x180109644  mov     [rsi+34h], ebp
0x180109647  mov     [rsi+38h], ebp
0x18010964a  cmp     [rsi+30h], ebp
0x18010964d  jbe     short loc_18010965E
0x18010964f  mov     rcx, rsi; this
0x180109652  call    ?EnqueueNextProducerTask@PCChainManager@@AEAAXXZ; PCChainManager::EnqueueNextProducerTask(void)
0x180109657  add     ebx, edi
0x180109659  cmp     ebx, [rsi+30h]
0x18010965c  jb      short loc_18010964F
0x18010965e  mov     r13b, dil
0x180109661  mov     rcx, [rsi+40h]; hHandle
0x180109665  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180109668  call    cs:__imp_WaitForSingleObject
0x18010966e  mov     ecx, [rsi+8]
0x180109671  mov     eax, [rsi+38h]
0x180109674  cmp     eax, ecx
0x180109676  jge     loc_1801097AD
0x18010967c  mov     r12d, [rsi+38h]
0x180109680  xor     eax, eax
0x180109682  lock cmpxchg cs:dword_1805DBFBC, edi
0x18010968a  jz      loc_1801097E0
0x180109690  mov     rax, cs:pvAddress
0x180109697  test    rax, rax
0x18010969a  jz      short loc_1801096EA
0x18010969c  call    ?EnsureThreadTraceRegisteredWithWER@@YAXXZ; EnsureThreadTraceRegisteredWithWER(void)
0x1801096a1  mov     ecx, cs:?g_nCurrentThreadTraceIndex@@3JC; long volatile g_nCurrentThreadTraceIndex
0x1801096a7  lea     eax, [rcx+1]
0x1801096aa  movzx   edx, al
0x1801096ad  mov     eax, ecx
0x1801096af  lock cmpxchg cs:?g_nCurrentThreadTraceIndex@@3JC, edx; long volatile g_nCurrentThreadTraceIndex
0x1801096b7  cmp     ecx, eax
0x1801096b9  jnz     short loc_1801096A1
0x1801096bb  mov     rbx, cs:pvAddress
0x1801096c2  lea     rdi, [rdx+rdx*2]
0x1801096c6  call    cs:__imp_GetCurrentThreadId
0x1801096cc  mov     [rbx+rdi*8], eax
0x1801096cf  mov     dword ptr [rbx+rdi*8+4], 2
0x1801096d7  mov     [rbx+rdi*8+8], r12d
0x1801096dc  mov     [rbx+rdi*8+0Ch], ebp
0x1801096e0  mov     [rbx+rdi*8+10h], rsi
0x1801096e5  mov     edi, 1
0x1801096ea  mov     rax, [rsi]
0x1801096ed  mov     ecx, r12d
0x1801096f0  mov     rcx, [rax+rcx*8]
0x1801096f4  mov     rax, [rcx]
0x1801096f7  mov     rax, [rax+10h]
0x1801096fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109700  mov     rcx, rsi; this
0x180109703  call    ?EnqueueNextProducerTask@PCChainManager@@AEAAXXZ; PCChainManager::EnqueueNextProducerTask(void)
0x180109708  mov     ecx, [rsi+8]
0x18010970b  mov     eax, r12d
0x18010970e  sub     ecx, edi
0x180109710  add     r12d, edi
0x180109713  cmp     eax, ecx
0x180109715  jge     loc_1801097CE
0x18010971b  mov     rax, [rsi+18h]
0x18010971f  lock add dword ptr [rax+r12*4], 0FFFFFFFFh
0x180109725  setz    r15b
0x180109729  xor     eax, eax
0x18010972b  lock cmpxchg cs:dword_1805DBFBC, edi
0x180109733  jz      loc_180109806
0x180109739  mov     rax, cs:pvAddress
0x180109740  test    rax, rax
0x180109743  jz      short loc_18010979B
0x180109745  movzx   r14d, r15b
0x180109749  xor     r14d, edi
0x18010974c  call    ?EnsureThreadTraceRegisteredWithWER@@YAXXZ; EnsureThreadTraceRegisteredWithWER(void)
0x180109751  mov     ecx, cs:?g_nCurrentThreadTraceIndex@@3JC; long volatile g_nCurrentThreadTraceIndex
0x180109757  lea     eax, [rcx+1]
0x18010975a  movzx   edx, al
0x18010975d  mov     eax, ecx
0x18010975f  lock cmpxchg cs:?g_nCurrentThreadTraceIndex@@3JC, edx; long volatile g_nCurrentThreadTraceIndex
0x180109767  cmp     ecx, eax
0x180109769  jnz     short loc_180109751
0x18010976b  mov     rbx, cs:pvAddress
0x180109772  lea     rdi, [rdx+rdx*2]
0x180109776  call    cs:__imp_GetCurrentThreadId
0x18010977c  mov     [rbx+rdi*8], eax
0x18010977f  mov     dword ptr [rbx+rdi*8+4], 3
0x180109787  mov     [rbx+rdi*8+8], r12d
0x18010978c  mov     [rbx+rdi*8+0Ch], r14d
0x180109791  mov     [rbx+rdi*8+10h], rsi
0x180109796  mov     edi, 1
0x18010979b  test    r15b, r15b
0x18010979e  jnz     loc_180109680
0x1801097a4  test    r13b, r13b
0x1801097a7  jnz     loc_180109661
0x1801097ad  mov     rcx, [rsi+48h]; pwk
0x1801097b1  xor     edx, edx; fCancelPendingCallbacks
0x1801097b3  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1801097b9  xor     edx, edx
0x1801097bb  mov     r9, rsi
0x1801097be  xor     r8d, r8d
0x1801097c1  lea     ecx, [rdx+5]
0x1801097c4  call    ?RecordThreadTraceEvent@@YAXW4Enum@ThreadTraceEvent@@KHPEAVPCChainManager@@@Z; RecordThreadTraceEvent(ThreadTraceEvent::Enum,ulong,int,PCChainManager *)
0x1801097c9  jmp     loc_180109610
0x1801097ce  mov     r15b, bpl
0x1801097d1  mov     r13b, bpl
0x1801097d4  jmp     loc_180109729
0x1801097d9  int     2Ch; Windows NT - assertion failure
0x1801097db  jmp     loc_180109640
0x1801097e0  call    cs:__imp_GetProcessHeap
0x1801097e6  mov     edx, 8; dwFlags
0x1801097eb  mov     r8d, 1800h; dwBytes
0x1801097f1  mov     rcx, rax; hHeap
0x1801097f4  call    cs:__imp_HeapAlloc
0x1801097fa  mov     cs:pvAddress, rax
0x180109801  jmp     loc_180109697
0x180109806  call    cs:__imp_GetProcessHeap
0x18010980c  mov     edx, 8; dwFlags
0x180109811  mov     r8d, 1800h; dwBytes
0x180109817  mov     rcx, rax; hHeap
0x18010981a  call    cs:__imp_HeapAlloc
0x180109820  mov     cs:pvAddress, rax
0x180109827  jmp     loc_180109740
```
