# StressLog::CreateThreadStressLog(void)

- ea: `0x14000f2a4`
- end: `0x14000f460`
- name: `?CreateThreadStressLog@StressLog@@SAPEAVThreadStressLog@@XZ`
- size: `444`
- prototype: `struct ThreadStressLog *(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x14000f8e0`

## callees

- `0x14000a148`
- `0x14000a1f4`
- `0x14000a218`
- `0x14000ef8c`
- `0x14000f2a4`
- `0x14000f46c`
- `0x14000f6e0`
- `0x1400101f4`
- `0x140010250`
- `0x140011bbc`
- `0x140011cf0`
- `0x140011df4`
- `0x140013f30`

## pseudocode

```c
struct ThreadStressLog *StressLog::CreateThreadStressLog(void)
{
  __int64 v0; // rdi
  _QWORD *Block; // rax
  struct ThreadStressLog *ThreadStressLogHelper; // rdi
  struct IExecutionEngine *ExecutionEngine; // rax
  int v5; // [rsp+28h] [rbp-30h]
  _BYTE v6[16]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v7; // [rsp+40h] [rbp-18h] BYREF

  v0 = dword_140027130;
  Block = (_QWORD *)__ClrFlsGetBlock();
  if ( Block )
  {
    ThreadStressLogHelper = (struct ThreadStressLog *)Block[v0];
  }
  else
  {
    ExecutionEngine = GetExecutionEngine();
    ThreadStressLogHelper = (struct ThreadStressLog *)(*(__int64 (__fastcall **)(struct IExecutionEngine *, _QWORD))(*(_QWORD *)ExecutionEngine + 40LL))(
                                                        ExecutionEngine,
                                                        (unsigned int)v0);
  }
  if ( ThreadStressLogHelper )
    return ThreadStressLogHelper;
  if ( (PVOID)qword_140028148 != NtCurrentTeb()->NtTib.StackBase
    && StressLogChunk::s_LogChunkHeap
    && (PVOID)ForbidCallsIntoHostOnThisThread::s_pvOwningFiber != NtCurrentTeb()->NtTib.StackBase
    && !(unsigned int)IsInCantAllocStressLogRegion()
    && (dword_140027134 || (unsigned int)StressLog::AllowNewChunk(0)) )
  {
    if ( !g_StackProbingEnabled )
      goto LABEL_16;
    if ( (unsigned int)((__int64 (__fastcall *)(__int64))g_fpDoProbe)(24) )
    {
      if ( g_StackProbingEnabled )
        SOIntolerantTransitionHandler::CtorImpl((SOIntolerantTransitionHandler *)v6);
LABEL_16:
      v5 = 0;
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        if ( qword_140027138 )
        {
          IncCantAllocCount();
          ClrEnterCriticalSection(qword_140027138);
          DecCantAllocCount();
          v5 = 1;
        }
        qword_140028148 = (__int64)NtCurrentTeb()->NtTib.StackBase;
        ClrFlsSetValue(dword_140027130, 0);
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &OutOfMemoryException * `RTTI Type Descriptor', (OutOfMemoryException **)&v7) )
        {
          ThreadStressLogHelper = 0;
          __eh34_try_continuation(0, &OutOfMemoryException * `RTTI Type Descriptor', &loc_14000F408);
LABEL_22:
          qword_140028148 = 0;
          if ( v5 )
          {
            IncCantAllocCount();
            ClrLeaveCriticalSection(qword_140027138);
            DecCantAllocCount();
          }
          v6[0] = 0;
          if ( g_StackProbingEnabled )
            SOIntolerantTransitionHandler::DtorImpl((SOIntolerantTransitionHandler *)v6);
          return ThreadStressLogHelper;
        }
      }
      if ( StressLog::theLog )
        ThreadStressLogHelper = StressLog::CreateThreadStressLogHelper();
      goto LABEL_22;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000f2a4  push    rdi
0x14000f2a6  sub     rsp, 50h
0x14000f2aa  mov     edi, cs:dword_140027130
0x14000f2b0  mov     rax, cs:?__ClrFlsGetBlock@@3P6APEAXXZEA; void * (*__ClrFlsGetBlock)(void)
0x14000f2b7  call    cs:__guard_dispatch_icall_fptr
0x14000f2bd  test    rax, rax
0x14000f2c0  jz      short loc_14000F2C8
0x14000f2c2  mov     rdi, [rax+rdi*8]
0x14000f2c6  jmp     short loc_14000F2E5
0x14000f2c8  call    ?GetExecutionEngine@@YAPEAUIExecutionEngine@@XZ; GetExecutionEngine(void)
0x14000f2cd  mov     r8, rax
0x14000f2d0  mov     rcx, [rax]
0x14000f2d3  mov     rax, [rcx+28h]
0x14000f2d7  mov     edx, edi
0x14000f2d9  mov     rcx, r8
0x14000f2dc  call    cs:__guard_dispatch_icall_fptr
0x14000f2e2  mov     rdi, rax
0x14000f2e5  mov     [rsp+58h+arg_8], rdi
0x14000f2ea  test    rdi, rdi
0x14000f2ed  jz      short loc_14000F2F7
0x14000f2ef  mov     rax, rdi
0x14000f2f2  jmp     loc_14000F45A
0x14000f2f7  mov     rax, gs:30h
0x14000f300  mov     rcx, [rax+8]
0x14000f304  cmp     cs:qword_140028148, rcx
0x14000f30b  jz      loc_14000F458
0x14000f311  cmp     cs:?s_LogChunkHeap@StressLogChunk@@2PEAXEA, 0; void * StressLogChunk::s_LogChunkHeap
0x14000f319  jz      loc_14000F458
0x14000f31f  mov     rax, gs:30h
0x14000f328  mov     rcx, [rax+8]
0x14000f32c  mov     rax, cs:?s_pvOwningFiber@ForbidCallsIntoHostOnThisThread@@0V?$Volatile@PEAX@@A; Volatile<void *> ForbidCallsIntoHostOnThisThread::s_pvOwningFiber
0x14000f333  cmp     rax, rcx
0x14000f336  jz      loc_14000F458
0x14000f33c  call    ?IsInCantAllocStressLogRegion@@YAHXZ; IsInCantAllocStressLogRegion(void)
0x14000f341  test    eax, eax
0x14000f343  jnz     loc_14000F458
0x14000f349  mov     eax, cs:dword_140027134
0x14000f34f  test    eax, eax
0x14000f351  jnz     short loc_14000F362
0x14000f353  xor     ecx, ecx; int
0x14000f355  call    ?AllowNewChunk@StressLog@@SAHJ@Z; StressLog::AllowNewChunk(long)
0x14000f35a  test    eax, eax
0x14000f35c  jz      loc_14000F458
0x14000f362  cmp     cs:?g_StackProbingEnabled@@3_NA, 0; bool g_StackProbingEnabled
0x14000f369  jz      short loc_14000F399
0x14000f36b  mov     ecx, 18h
0x14000f370  mov     rax, cs:?g_fpDoProbe@@3P6AHI@ZEA; int (*g_fpDoProbe)(uint)
0x14000f377  call    cs:__guard_dispatch_icall_fptr
0x14000f37d  test    eax, eax
0x14000f37f  jz      loc_14000F458
0x14000f385  cmp     cs:?g_StackProbingEnabled@@3_NA, 0; bool g_StackProbingEnabled
0x14000f38c  jz      short loc_14000F399
0x14000f38e  lea     rcx, [rsp+58h+var_28]; this
0x14000f393  call    ?CtorImpl@SOIntolerantTransitionHandler@@QEAAXXZ; SOIntolerantTransitionHandler::CtorImpl(void)
0x14000f398  nop
0x14000f399  mov     rax, cs:qword_140027138
0x14000f3a0  mov     [rsp+58h+var_38], rax
0x14000f3a5  and     [rsp+58h+var_30], 0
0x14000f3aa  test    rax, rax
0x14000f3ad  jz      short loc_14000F3CD
0x14000f3af  call    ?IncCantAllocCount@@YAXXZ; IncCantAllocCount(void)
0x14000f3b4  mov     rcx, cs:qword_140027138; void *
0x14000f3bb  call    ?ClrEnterCriticalSection@@YAXPEAX@Z; ClrEnterCriticalSection(void *)
0x14000f3c0  call    ?DecCantAllocCount@@YAXXZ; DecCantAllocCount(void)
0x14000f3c5  mov     [rsp+58h+var_30], 1
0x14000f3cd  mov     rax, gs:30h
0x14000f3d6  mov     rcx, [rax+8]
0x14000f3da  mov     cs:qword_140028148, rcx
0x14000f3e1  mov     eax, cs:dword_140027130
0x14000f3e7  mov     [rsp+58h+arg_0], eax
0x14000f3eb  xor     edx, edx; void *
0x14000f3ed  mov     ecx, eax; unsigned int
0x14000f3ef  call    ?ClrFlsSetValue@@YAXKPEAX@Z; ClrFlsSetValue(ulong,void *)
0x14000f3f4  nop
0x14000f3f5  cmp     cs:?theLog@StressLog@@2V1@A, 0; StressLog StressLog::theLog
0x14000f3fc  jz      short loc_14000F40D
0x14000f3fe  call    ?CreateThreadStressLogHelper@StressLog@@SAPEAVThreadStressLog@@XZ; StressLog::CreateThreadStressLogHelper(void)
0x14000f403  mov     rdi, rax
0x14000f406  jmp     short loc_14000F40D
0x14000f408  mov     rdi, [rsp+58h+arg_8]
0x14000f40d  and     cs:qword_140028148, 0
0x14000f415  cmp     [rsp+58h+var_30], 0
0x14000f41a  jz      short loc_14000F437
0x14000f41c  call    ?IncCantAllocCount@@YAXXZ; IncCantAllocCount(void)
0x14000f421  mov     rcx, cs:qword_140027138; void *
0x14000f428  call    ?ClrLeaveCriticalSection@@YAXPEAX@Z; ClrLeaveCriticalSection(void *)
0x14000f42d  call    ?DecCantAllocCount@@YAXXZ; DecCantAllocCount(void)
0x14000f432  and     [rsp+58h+var_30], 0
0x14000f437  mov     [rsp+58h+var_28], 0
0x14000f43c  cmp     cs:?g_StackProbingEnabled@@3_NA, 0; bool g_StackProbingEnabled
0x14000f443  jz      loc_14000F2EF
0x14000f449  lea     rcx, [rsp+58h+var_28]; this
0x14000f44e  call    ?DtorImpl@SOIntolerantTransitionHandler@@QEAAXXZ; SOIntolerantTransitionHandler::DtorImpl(void)
0x14000f453  jmp     loc_14000F2EF
0x14000f458  xor     eax, eax
0x14000f45a  add     rsp, 50h
0x14000f45e  pop     rdi
0x14000f45f  retn
```
