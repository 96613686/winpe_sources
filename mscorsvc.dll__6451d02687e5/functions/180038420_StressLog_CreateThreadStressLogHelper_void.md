# StressLog::CreateThreadStressLogHelper(void)

- ea: `0x180038420`
- end: `0x180038695`
- name: `?CreateThreadStressLogHelper@StressLog@@SAPEAVThreadStressLog@@XZ`
- size: `629`
- prototype: `struct ThreadStressLog *(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x180038258`

## callees

- `0x180030530`
- `0x1800305a4`
- `0x1800306c8`
- `0x180037fec`
- `0x180038420`
- `0x180038698`
- `0x180038cc4`
- `0x18003dc50`
- `0x18003f280`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18003864c`
- `KERNEL32!SetLastError` at `0x18003864c`
- `KERNEL32!GetCurrentThreadId` at `0x1800385e4`
- `KERNEL32!GetCurrentThreadId` at `0x1800385e4`
- `KERNEL32!QueryPerformanceCounter` at `0x180038456`
- `KERNEL32!QueryPerformanceCounter` at `0x180038456`
- `KERNEL32!GetLastError` at `0x180038625`
- `KERNEL32!GetLastError` at `0x180038625`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
struct ThreadStressLog *StressLog::CreateThreadStressLogHelper(void)
{
  int v0; // esi
  __int64 v1; // rdi
  __int64 v2; // rbx
  __int64 v3; // rcx
  __int64 v4; // rax
  const struct NoThrow *v5; // rdx
  _QWORD *v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rbp
  _QWORD *Block; // rax
  DWORD LastError; // ebx
  struct IExecutionEngine *ExecutionEngine; // rax
  __int64 v15; // [rsp+20h] [rbp-28h] BYREF
  char v16; // [rsp+28h] [rbp-20h]
  LARGE_INTEGER v17; // [rsp+50h] [rbp+8h] BYREF
  __int64 v18; // [rsp+58h] [rbp+10h]

  v0 = 0;
  v1 = 0;
  if ( dword_18006F314 <= 0 )
  {
LABEL_18:
    if ( (unsigned int)IsInCantAllocStressLogRegion() )
      return (struct ThreadStressLog *)v1;
    v6 = operator new(0x50u, v5);
    v1 = (__int64)v6;
    if ( v6 )
    {
      v6[8] = 0;
      v6[6] = 0;
      v6[5] = 0;
      if ( (unsigned int)IsInCantAllocStressLogRegion() )
      {
        v7 = 0;
      }
      else
      {
        v15 = 32792;
        v16 = 0;
        v7 = ClrHeapAlloc(StressLogChunk::s_LogChunkHeap, 0, &v15);
      }
      v18 = v7;
      if ( v7 )
      {
        *(_QWORD *)v7 = 0;
        *(_QWORD *)(v7 + 8) = 0;
        *(_DWORD *)(v7 + 32784) = -808464433;
        *(_DWORD *)(v7 + 32788) = -808464433;
      }
      else
      {
        v7 = 0;
      }
      if ( v7 )
      {
        _InterlockedAdd(&dword_18006F300, 1u);
        *(_QWORD *)v7 = v7;
        *(_QWORD *)(v7 + 8) = v7;
        *(_QWORD *)(v1 + 48) = v7;
        *(_QWORD *)(v1 + 40) = v7;
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
        v8 = *(_QWORD *)(v1 + 64);
        if ( !v8 || *(_DWORD *)(v8 + 32784) == -808464433 && *(_DWORD *)(v8 + 32788) == -808464433 )
          goto LABEL_32;
      }
      ThreadStressLog::~ThreadStressLog((ThreadStressLog *)v1);
      operator delete((void *)v1);
    }
    return 0;
  }
  v17.QuadPart = 0;
  QueryPerformanceCounter(&v17);
  v1 = qword_18006F308;
  v2 = 0;
  while ( v1 )
  {
    if ( *(_DWORD *)(v1 + 12) )
    {
      v3 = *(_QWORD *)(v1 + 48) + 32784LL;
      v4 = *(_QWORD *)(v1 + 16);
      if ( v4 != v3 && *(_QWORD *)(v4 + 16) < (unsigned __int64)(v17.QuadPart - 0x40000000) )
      {
        v0 = 1;
        _InterlockedDecrement(&dword_18006F314);
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
    _InterlockedDecrement(&dword_18006F314);
  }
  if ( !v1 )
    goto LABEL_18;
LABEL_32:
  *(_DWORD *)(v1 + 8) = GetCurrentThreadId();
  *(_DWORD *)(v1 + 12) = 0;
  v9 = *(_QWORD *)(v1 + 48);
  *(_QWORD *)(v1 + 64) = v9;
  *(_QWORD *)(v1 + 16) = v9 + 32784;
  *(_DWORD *)(v1 + 36) = 0;
  v10 = dword_18006F310;
  Block = (_QWORD *)__ClrFlsGetBlock();
  if ( Block )
  {
    Block[v10] = v1;
  }
  else
  {
    LastError = GetLastError();
    ExecutionEngine = GetExecutionEngine();
    (*(void (__fastcall **)(struct IExecutionEngine *, _QWORD, __int64))(*(_QWORD *)ExecutionEngine + 56LL))(
      ExecutionEngine,
      (unsigned int)v10,
      v1);
    SetLastError(LastError);
  }
  if ( !v0 )
  {
    *(_QWORD *)v1 = qword_18006F308;
    qword_18006F308 = v1;
  }
  return (struct ThreadStressLog *)v1;
}

```

## disassembly

```asm
0x180038420  mov     r11, rsp
0x180038423  mov     [r11+18h], rbx
0x180038427  mov     [r11+20h], rbp
0x18003842b  push    rsi
0x18003842c  push    rdi
0x18003842d  push    r14
0x18003842f  sub     rsp, 30h
0x180038433  xor     r14d, r14d
0x180038436  mov     esi, r14d
0x180038439  mov     edi, r14d
0x18003843c  mov     eax, cs:dword_18006F314
0x180038442  lea     ebp, [r14+1]
0x180038446  test    eax, eax
0x180038448  jle     loc_1800384ED
0x18003844e  mov     [r11+8], r14
0x180038452  lea     rcx, [r11+8]; lpPerformanceCount
0x180038456  call    cs:__imp_QueryPerformanceCounter
0x18003845c  mov     rdx, [rsp+48h+arg_0]
0x180038461  add     rdx, 0FFFFFFFFC0000000h
0x180038468  mov     rdi, cs:qword_18006F308
0x18003846f  mov     ebx, r14d
0x180038472  test    rdi, rdi
0x180038475  jz      short loc_1800384C4
0x180038477  cmp     [rdi+0Ch], r14d
0x18003847b  jz      short loc_1800384B6
0x18003847d  mov     rcx, [rdi+30h]
0x180038481  add     rcx, 8010h
0x180038488  mov     rax, [rdi+10h]
0x18003848c  cmp     rax, rcx
0x18003848f  jz      short loc_180038497
0x180038491  cmp     [rax+10h], rdx
0x180038495  jb      short loc_1800384BB
0x180038497  test    rbx, rbx
0x18003849a  jnz     short loc_1800384A1
0x18003849c  mov     rbx, rdi
0x18003849f  jmp     short loc_1800384B6
0x1800384a1  cmp     rax, rcx
0x1800384a4  jz      short loc_1800384B6
0x1800384a6  mov     rcx, [rbx+10h]
0x1800384aa  mov     rax, [rax+10h]
0x1800384ae  cmp     [rcx+10h], rax
0x1800384b2  cmova   rbx, rdi
0x1800384b6  mov     rdi, [rdi]
0x1800384b9  jmp     short loc_180038472
0x1800384bb  mov     esi, ebp
0x1800384bd  lock dec cs:dword_18006F314
0x1800384c4  xor     ecx, ecx; int
0x1800384c6  call    ?AllowNewChunk@StressLog@@SAHJ@Z; StressLog::AllowNewChunk(long)
0x1800384cb  test    eax, eax
0x1800384cd  jnz     short loc_1800384E4
0x1800384cf  test    rdi, rdi
0x1800384d2  jnz     loc_1800385E4
0x1800384d8  mov     rdi, rbx
0x1800384db  mov     esi, ebp
0x1800384dd  lock dec cs:dword_18006F314
0x1800384e4  test    rdi, rdi
0x1800384e7  jnz     loc_1800385E4
0x1800384ed  call    ?IsInCantAllocStressLogRegion@@YAHXZ; IsInCantAllocStressLogRegion(void)
0x1800384f2  test    eax, eax
0x1800384f4  jnz     loc_18003867F
0x1800384fa  lea     ebx, [rax+50h]
0x1800384fd  mov     ecx, ebx; dwBytes
0x1800384ff  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x180038504  mov     rdi, rax
0x180038507  test    rax, rax
0x18003850a  jz      loc_18003867C
0x180038510  mov     [rax+40h], r14
0x180038514  mov     [rax+30h], r14
0x180038518  mov     [rax+28h], r14
0x18003851c  call    ?IsInCantAllocStressLogRegion@@YAHXZ; IsInCantAllocStressLogRegion(void)
0x180038521  test    eax, eax
0x180038523  jz      short loc_18003852A
0x180038525  mov     rax, r14
0x180038528  jmp     short loc_180038556
0x18003852a  mov     qword ptr [rsp+48h+var_28], 8018h
0x180038533  mov     byte ptr [rsp+48h+var_28+8], r14b
0x180038538  movaps  xmm0, [rsp+48h+var_28]
0x18003853d  movdqa  [rsp+48h+var_28], xmm0
0x180038543  lea     r8, [rsp+48h+var_28]
0x180038548  xor     edx, edx
0x18003854a  mov     rcx, cs:?s_LogChunkHeap@StressLogChunk@@2PEAXEA; void * StressLogChunk::s_LogChunkHeap
0x180038551  call    ?ClrHeapAlloc@@YAPEAXPEAXKV?$ClrSafeInt@_K@@@Z; ClrHeapAlloc(void *,ulong,ClrSafeInt<unsigned __int64>)
0x180038556  mov     [rsp+48h+arg_8], rax
0x18003855b  mov     ecx, 0CFCFCFCFh
0x180038560  test    rax, rax
0x180038563  jz      short loc_18003857A
0x180038565  mov     [rax], r14
0x180038568  mov     [rax+8], r14
0x18003856c  mov     [rax+8010h], ecx
0x180038572  mov     [rax+8014h], ecx
0x180038578  jmp     short loc_18003857D
0x18003857a  mov     rax, r14
0x18003857d  test    rax, rax
0x180038580  jz      short loc_1800385B9
0x180038582  lock add cs:dword_18006F300, ebp
0x180038589  mov     [rax], rax
0x18003858c  mov     [rax+8], rax
0x180038590  mov     [rdi+30h], rax
0x180038594  mov     [rdi+28h], rax
0x180038598  mov     [rdi], r14
0x18003859b  mov     [rdi+8], r14d
0x18003859f  mov     [rdi+0Ch], ebp
0x1800385a2  mov     [rdi+10h], r14
0x1800385a6  mov     [rdi+18h], r14
0x1800385aa  mov     [rdi+24h], r14d
0x1800385ae  mov     [rdi+38h], r14
0x1800385b2  mov     [rdi+40h], r14
0x1800385b6  mov     [rdi+48h], ebp
0x1800385b9  cmp     [rdi+28h], r14
0x1800385bd  jz      loc_180038669
0x1800385c3  mov     rax, [rdi+40h]
0x1800385c7  test    rax, rax
0x1800385ca  jz      short loc_1800385E4
0x1800385cc  cmp     [rax+8010h], ecx
0x1800385d2  jnz     loc_180038669
0x1800385d8  cmp     [rax+8014h], ecx
0x1800385de  jnz     loc_180038669
0x1800385e4  call    cs:__imp_GetCurrentThreadId
0x1800385ea  mov     [rdi+8], eax
0x1800385ed  mov     [rdi+0Ch], r14d
0x1800385f1  mov     rax, [rdi+30h]
0x1800385f5  mov     [rdi+40h], rax
0x1800385f9  add     rax, 8010h
0x1800385ff  mov     [rdi+10h], rax
0x180038603  mov     [rdi+24h], r14d
0x180038607  mov     ebp, cs:dword_18006F310
0x18003860d  mov     rax, cs:?__ClrFlsGetBlock@@3P6APEAXXZEA; void * (*__ClrFlsGetBlock)(void)
0x180038614  call    cs:__guard_dispatch_icall_fptr
0x18003861a  test    rax, rax
0x18003861d  jz      short loc_180038625
0x18003861f  mov     [rax+rbp*8], rdi
0x180038623  jmp     short loc_180038652
0x180038625  call    cs:__imp_GetLastError
0x18003862b  mov     ebx, eax
0x18003862d  call    ?GetExecutionEngine@@YAPEAUIExecutionEngine@@XZ; GetExecutionEngine(void)
0x180038632  mov     r9, rax
0x180038635  mov     rcx, [rax]
0x180038638  mov     rax, [rcx+38h]
0x18003863c  mov     r8, rdi
0x18003863f  mov     edx, ebp
0x180038641  mov     rcx, r9
0x180038644  call    cs:__guard_dispatch_icall_fptr
0x18003864a  mov     ecx, ebx; dwErrCode
0x18003864c  call    cs:__imp_SetLastError
0x180038652  test    esi, esi
0x180038654  jnz     short loc_18003867F
0x180038656  mov     rax, cs:qword_18006F308
0x18003865d  mov     [rdi], rax
0x180038660  mov     cs:qword_18006F308, rdi
0x180038667  jmp     short loc_18003867F
0x180038669  mov     rcx, rdi; this
0x18003866c  call    ??1ThreadStressLog@@QEAA@XZ; ThreadStressLog::~ThreadStressLog(void)
0x180038671  mov     rdx, rbx; unsigned __int64
0x180038674  mov     rcx, rdi; void *
0x180038677  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003867c  mov     rdi, r14
0x18003867f  mov     rax, rdi
0x180038682  mov     rbx, [rsp+48h+arg_10]
0x180038687  mov     rbp, [rsp+48h+arg_18]
0x18003868c  add     rsp, 30h
0x180038690  pop     r14
0x180038692  pop     rdi
0x180038693  pop     rsi
0x180038694  retn
```
