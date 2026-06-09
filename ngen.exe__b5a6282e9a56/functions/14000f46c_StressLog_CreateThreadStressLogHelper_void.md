# StressLog::CreateThreadStressLogHelper(void)

- ea: `0x14000f46c`
- end: `0x14000f6de`
- name: `?CreateThreadStressLogHelper@StressLog@@SAPEAVThreadStressLog@@XZ`
- size: `626`
- prototype: `struct ThreadStressLog *(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x14000f2a4`

## callees

- `0x14000a0a0`
- `0x14000a148`
- `0x14000a23c`
- `0x14000f038`
- `0x14000f46c`
- `0x14000f6e0`
- `0x140011df4`
- `0x14001374c`
- `0x140013f30`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x14000f4a2`
- `KERNEL32!QueryPerformanceCounter` at `0x14000f4a2`
- `KERNEL32!SetLastError` at `0x14000f693`
- `KERNEL32!SetLastError` at `0x14000f693`
- `KERNEL32!GetCurrentThreadId` at `0x14000f62b`
- `KERNEL32!GetCurrentThreadId` at `0x14000f62b`
- `KERNEL32!GetLastError` at `0x14000f66c`
- `KERNEL32!GetLastError` at `0x14000f66c`

## pseudocode

```c
struct ThreadStressLog *StressLog::CreateThreadStressLogHelper(void)
{
  int v0; // esi
  __int64 v1; // rdi
  __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // rax
  const struct NoThrow *v5; // rdx
  unsigned __int64 v6; // rcx
  _QWORD *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rbp
  _QWORD *Block; // rax
  DWORD LastError; // ebx
  struct IExecutionEngine *ExecutionEngine; // rax
  __int64 v16; // [rsp+20h] [rbp-28h] BYREF
  char v17; // [rsp+28h] [rbp-20h]
  LARGE_INTEGER v18; // [rsp+50h] [rbp+8h] BYREF
  __int64 v19; // [rsp+58h] [rbp+10h]

  v0 = 0;
  v1 = 0;
  if ( dword_140027134 <= 0 )
  {
LABEL_18:
    if ( (unsigned int)IsInCantAllocStressLogRegion() )
      return (struct ThreadStressLog *)v1;
    v7 = operator new(v6, v5);
    v1 = (__int64)v7;
    if ( v7 )
    {
      v7[8] = 0;
      v7[6] = 0;
      v7[5] = 0;
      if ( (unsigned int)IsInCantAllocStressLogRegion() )
      {
        v8 = 0;
      }
      else
      {
        v16 = 32792;
        v17 = 0;
        v8 = ClrHeapAlloc(StressLogChunk::s_LogChunkHeap, 0, &v16);
      }
      v19 = v8;
      if ( v8 )
      {
        *(_QWORD *)v8 = 0;
        *(_QWORD *)(v8 + 8) = 0;
        *(_DWORD *)(v8 + 32784) = -808464433;
        *(_DWORD *)(v8 + 32788) = -808464433;
      }
      else
      {
        v8 = 0;
      }
      if ( v8 )
      {
        _InterlockedAdd(&dword_140027120, 1u);
        *(_QWORD *)v8 = v8;
        *(_QWORD *)(v8 + 8) = v8;
        *(_QWORD *)(v1 + 48) = v8;
        *(_QWORD *)(v1 + 40) = v8;
        *(_QWORD *)v1 = 0;
        *(_DWORD *)(v1 + 8) = 0;
        *(_DWORD *)(v1 + 12) = 1;
        *(_QWORD *)(v1 + 16) = 0;
        *(_QWORD *)(v1 + 24) = 0;
        *(_DWORD *)(v1 + 36) = 0;
        *(_QWORD *)(v1 + 56) = 0;
        *(_QWORD *)(v1 + 64) = 0;
        *(_DWORD *)(v1 + 72) = 1;
      }
      if ( *(_QWORD *)(v1 + 40) )
      {
        v9 = *(_QWORD *)(v1 + 64);
        if ( !v9 || *(_DWORD *)(v9 + 32784) == -808464433 && *(_DWORD *)(v9 + 32788) == -808464433 )
          goto LABEL_32;
      }
      ThreadStressLog::~ThreadStressLog((ThreadStressLog *)v1);
      operator delete((void *)v1);
    }
    return 0;
  }
  v18.QuadPart = 0;
  QueryPerformanceCounter(&v18);
  v1 = qword_140027128;
  v2 = 0;
  while ( v1 )
  {
    if ( *(_DWORD *)(v1 + 12) )
    {
      v3 = *(_QWORD *)(v1 + 48) + 32784LL;
      v4 = *(_QWORD *)(v1 + 16);
      if ( v4 != v3 && *(_QWORD *)(v4 + 16) < (unsigned __int64)(v18.QuadPart - 0x40000000) )
      {
        v0 = 1;
        _InterlockedDecrement(&dword_140027134);
        break;
      }
      if ( v2 )
      {
        if ( v4 != v3 && *(_QWORD *)(*(_QWORD *)(v2 + 16) + 16LL) > *(_QWORD *)(v4 + 16) )
          v2 = v1;
      }
      else
      {
        v2 = v1;
      }
    }
    v1 = *(_QWORD *)v1;
  }
  if ( !(unsigned int)StressLog::AllowNewChunk(0) )
  {
    if ( v1 )
      goto LABEL_32;
    v1 = v2;
    v0 = 1;
    _InterlockedDecrement(&dword_140027134);
  }
  if ( !v1 )
    goto LABEL_18;
LABEL_32:
  *(_DWORD *)(v1 + 8) = GetCurrentThreadId();
  *(_DWORD *)(v1 + 12) = 0;
  v10 = *(_QWORD *)(v1 + 48);
  *(_QWORD *)(v1 + 64) = v10;
  *(_QWORD *)(v1 + 16) = v10 + 32784;
  *(_DWORD *)(v1 + 36) = 0;
  v11 = dword_140027130;
  Block = (_QWORD *)__ClrFlsGetBlock();
  if ( Block )
  {
    Block[v11] = v1;
  }
  else
  {
    LastError = GetLastError();
    ExecutionEngine = GetExecutionEngine();
    (*(void (__fastcall **)(struct IExecutionEngine *, _QWORD, __int64))(*(_QWORD *)ExecutionEngine + 56LL))(
      ExecutionEngine,
      (unsigned int)v11,
      v1);
    SetLastError(LastError);
  }
  if ( !v0 )
  {
    *(_QWORD *)v1 = qword_140027128;
    qword_140027128 = v1;
  }
  return (struct ThreadStressLog *)v1;
}

```

## disassembly

```asm
0x14000f46c  mov     r11, rsp
0x14000f46f  mov     [r11+18h], rbx
0x14000f473  mov     [r11+20h], rbp
0x14000f477  push    rsi
0x14000f478  push    rdi
0x14000f479  push    r14
0x14000f47b  sub     rsp, 30h
0x14000f47f  xor     r14d, r14d
0x14000f482  mov     esi, r14d
0x14000f485  mov     edi, r14d
0x14000f488  mov     eax, cs:dword_140027134
0x14000f48e  lea     ebp, [r14+1]
0x14000f492  test    eax, eax
0x14000f494  jle     loc_14000F539
0x14000f49a  mov     [r11+8], r14
0x14000f49e  lea     rcx, [r11+8]; lpPerformanceCount
0x14000f4a2  call    cs:__imp_QueryPerformanceCounter
0x14000f4a8  mov     rdx, [rsp+48h+arg_0]
0x14000f4ad  add     rdx, 0FFFFFFFFC0000000h
0x14000f4b4  mov     rdi, cs:qword_140027128
0x14000f4bb  mov     ebx, r14d
0x14000f4be  test    rdi, rdi
0x14000f4c1  jz      short loc_14000F510
0x14000f4c3  cmp     [rdi+0Ch], r14d
0x14000f4c7  jz      short loc_14000F502
0x14000f4c9  mov     rcx, [rdi+30h]
0x14000f4cd  add     rcx, 8010h
0x14000f4d4  mov     rax, [rdi+10h]
0x14000f4d8  cmp     rax, rcx
0x14000f4db  jz      short loc_14000F4E3
0x14000f4dd  cmp     [rax+10h], rdx
0x14000f4e1  jb      short loc_14000F507
0x14000f4e3  test    rbx, rbx
0x14000f4e6  jnz     short loc_14000F4ED
0x14000f4e8  mov     rbx, rdi
0x14000f4eb  jmp     short loc_14000F502
0x14000f4ed  cmp     rax, rcx
0x14000f4f0  jz      short loc_14000F502
0x14000f4f2  mov     rcx, [rbx+10h]
0x14000f4f6  mov     rax, [rax+10h]
0x14000f4fa  cmp     [rcx+10h], rax
0x14000f4fe  cmova   rbx, rdi
0x14000f502  mov     rdi, [rdi]
0x14000f505  jmp     short loc_14000F4BE
0x14000f507  mov     esi, ebp
0x14000f509  lock dec cs:dword_140027134
0x14000f510  xor     ecx, ecx; int
0x14000f512  call    ?AllowNewChunk@StressLog@@SAHJ@Z; StressLog::AllowNewChunk(long)
0x14000f517  test    eax, eax
0x14000f519  jnz     short loc_14000F530
0x14000f51b  test    rdi, rdi
0x14000f51e  jnz     loc_14000F62B
0x14000f524  mov     rdi, rbx
0x14000f527  mov     esi, ebp
0x14000f529  lock dec cs:dword_140027134
0x14000f530  test    rdi, rdi
0x14000f533  jnz     loc_14000F62B
0x14000f539  call    ?IsInCantAllocStressLogRegion@@YAHXZ; IsInCantAllocStressLogRegion(void)
0x14000f53e  test    eax, eax
0x14000f540  jnz     loc_14000F6C8
0x14000f546  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x14000f54b  mov     rdi, rax
0x14000f54e  test    rax, rax
0x14000f551  jz      loc_14000F6C5
0x14000f557  mov     [rax+40h], r14
0x14000f55b  mov     [rax+30h], r14
0x14000f55f  mov     [rax+28h], r14
0x14000f563  call    ?IsInCantAllocStressLogRegion@@YAHXZ; IsInCantAllocStressLogRegion(void)
0x14000f568  test    eax, eax
0x14000f56a  jz      short loc_14000F571
0x14000f56c  mov     rax, r14
0x14000f56f  jmp     short loc_14000F59D
0x14000f571  mov     qword ptr [rsp+48h+var_28], 8018h
0x14000f57a  mov     byte ptr [rsp+48h+var_28+8], r14b
0x14000f57f  movaps  xmm0, [rsp+48h+var_28]
0x14000f584  movdqa  [rsp+48h+var_28], xmm0
0x14000f58a  lea     r8, [rsp+48h+var_28]
0x14000f58f  xor     edx, edx
0x14000f591  mov     rcx, cs:?s_LogChunkHeap@StressLogChunk@@2PEAXEA; void * StressLogChunk::s_LogChunkHeap
0x14000f598  call    ?ClrHeapAlloc@@YAPEAXPEAXKV?$ClrSafeInt@_K@@@Z; ClrHeapAlloc(void *,ulong,ClrSafeInt<unsigned __int64>)
0x14000f59d  mov     [rsp+48h+arg_8], rax
0x14000f5a2  mov     ecx, 0CFCFCFCFh
0x14000f5a7  test    rax, rax
0x14000f5aa  jz      short loc_14000F5C1
0x14000f5ac  mov     [rax], r14
0x14000f5af  mov     [rax+8], r14
0x14000f5b3  mov     [rax+8010h], ecx
0x14000f5b9  mov     [rax+8014h], ecx
0x14000f5bf  jmp     short loc_14000F5C4
0x14000f5c1  mov     rax, r14
0x14000f5c4  test    rax, rax
0x14000f5c7  jz      short loc_14000F600
0x14000f5c9  lock add cs:dword_140027120, ebp
0x14000f5d0  mov     [rax], rax
0x14000f5d3  mov     [rax+8], rax
0x14000f5d7  mov     [rdi+30h], rax
0x14000f5db  mov     [rdi+28h], rax
0x14000f5df  mov     [rdi], r14
0x14000f5e2  mov     [rdi+8], r14d
0x14000f5e6  mov     [rdi+0Ch], ebp
0x14000f5e9  mov     [rdi+10h], r14
0x14000f5ed  mov     [rdi+18h], r14
0x14000f5f1  mov     [rdi+24h], r14d
0x14000f5f5  mov     [rdi+38h], r14
0x14000f5f9  mov     [rdi+40h], r14
0x14000f5fd  mov     [rdi+48h], ebp
0x14000f600  cmp     [rdi+28h], r14
0x14000f604  jz      loc_14000F6B0
0x14000f60a  mov     rax, [rdi+40h]
0x14000f60e  test    rax, rax
0x14000f611  jz      short loc_14000F62B
0x14000f613  cmp     [rax+8010h], ecx
0x14000f619  jnz     loc_14000F6B0
0x14000f61f  cmp     [rax+8014h], ecx
0x14000f625  jnz     loc_14000F6B0
0x14000f62b  call    cs:__imp_GetCurrentThreadId
0x14000f631  mov     [rdi+8], eax
0x14000f634  mov     [rdi+0Ch], r14d
0x14000f638  mov     rax, [rdi+30h]
0x14000f63c  mov     [rdi+40h], rax
0x14000f640  add     rax, 8010h
0x14000f646  mov     [rdi+10h], rax
0x14000f64a  mov     [rdi+24h], r14d
0x14000f64e  mov     ebp, cs:dword_140027130
0x14000f654  mov     rax, cs:?__ClrFlsGetBlock@@3P6APEAXXZEA; void * (*__ClrFlsGetBlock)(void)
0x14000f65b  call    cs:__guard_dispatch_icall_fptr
0x14000f661  test    rax, rax
0x14000f664  jz      short loc_14000F66C
0x14000f666  mov     [rax+rbp*8], rdi
0x14000f66a  jmp     short loc_14000F699
0x14000f66c  call    cs:__imp_GetLastError
0x14000f672  mov     ebx, eax
0x14000f674  call    ?GetExecutionEngine@@YAPEAUIExecutionEngine@@XZ; GetExecutionEngine(void)
0x14000f679  mov     r9, rax
0x14000f67c  mov     rcx, [rax]
0x14000f67f  mov     rax, [rcx+38h]
0x14000f683  mov     r8, rdi
0x14000f686  mov     edx, ebp
0x14000f688  mov     rcx, r9
0x14000f68b  call    cs:__guard_dispatch_icall_fptr
0x14000f691  mov     ecx, ebx; dwErrCode
0x14000f693  call    cs:__imp_SetLastError
0x14000f699  test    esi, esi
0x14000f69b  jnz     short loc_14000F6C8
0x14000f69d  mov     rax, cs:qword_140027128
0x14000f6a4  mov     [rdi], rax
0x14000f6a7  mov     cs:qword_140027128, rdi
0x14000f6ae  jmp     short loc_14000F6C8
0x14000f6b0  mov     rcx, rdi; this
0x14000f6b3  call    ??1ThreadStressLog@@QEAA@XZ; ThreadStressLog::~ThreadStressLog(void)
0x14000f6b8  mov     edx, 50h ; 'P'; unsigned __int64
0x14000f6bd  mov     rcx, rdi; void *
0x14000f6c0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000f6c5  mov     rdi, r14
0x14000f6c8  mov     rax, rdi
0x14000f6cb  mov     rbx, [rsp+48h+arg_10]
0x14000f6d0  mov     rbp, [rsp+48h+arg_18]
0x14000f6d5  add     rsp, 30h
0x14000f6d9  pop     r14
0x14000f6db  pop     rdi
0x14000f6dc  pop     rsi
0x14000f6dd  retn
```
