# CReaderWriterLock3::_ReadLockSpin(CReaderWriterLock3::SPIN_TYPE)

- ea: `0x180003700`
- end: `0x180003899`
- name: `?_ReadLockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z`
- size: `409`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003700`
- `0x1800039d0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003717`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000387c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003717`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000387c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800037b7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800037b7`

## pseudocode

```c
bool __fastcall CReaderWriterLock3::_ReadLockSpin(volatile __int32 *a1, int a2)
{
  DWORD v4; // ebp
  DWORD CurrentThreadId; // eax
  unsigned __int16 v6; // cx
  __int64 v7; // r14
  int v8; // edi
  int v9; // ebx
  signed __int32 v10; // edx
  bool result; // al
  signed __int32 v12; // edx

  v4 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v6 = CReaderWriterLock3::sm_wDefaultSpinCount;
  v7 = 0;
  v8 = (int)((double)CReaderWriterLock3::sm_wDefaultSpinCount * *(double *)&qword_180030E80[CurrentThreadId % 0xD]);
LABEL_2:
  v9 = v8;
  if ( g_cProcessors < 2 || !v6 )
    v9 = 1;
  while ( 1 )
  {
    if ( --v9 < 0 )
    {
      if ( v4 || !g_pfnSwitchToThread() )
        Sleep(v4);
      if ( (unsigned int)v7 < 4 )
        v4 = dword_180030D30[v7];
      else
        v4 = 100;
      v8 = (int)((double)v8 * CReaderWriterLock3::sm_dblDfltSpinAdjFctr);
      if ( v8 > 10000 )
      {
        v6 = CReaderWriterLock3::sm_wDefaultSpinCount;
        v8 = 10000;
        v7 = (unsigned int)(v7 + 1);
      }
      else
      {
        if ( v8 <= 100 )
          v8 = 100;
        v6 = CReaderWriterLock3::sm_wDefaultSpinCount;
        v7 = (unsigned int)(v7 + 1);
      }
      goto LABEL_2;
    }
    if ( a2 == 1 )
    {
      if ( *((_DWORD *)a1 + 1)
        || (unsigned __int16)*a1
        || (v12 = *a1, v12 != _InterlockedCompareExchange(a1, v12 | 0xFFFF, v12)) )
      {
        result = CReaderWriterLock3::_TryWriteLock2((CReaderWriterLock3 *)a1);
      }
      else
      {
        _InterlockedExchange(a1 + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
        result = 1;
      }
    }
    else
    {
      v10 = *a1;
      if ( a2 == 2 )
      {
        if ( (v10 & 0xFFFF8000) != 0 || v10 != _InterlockedCompareExchange(a1, v10 + 1, v10) )
          goto LABEL_9;
      }
      else if ( (_WORD)v10 == 0xFFFF || v10 != _InterlockedCompareExchange(a1, v10 + 1, v10) )
      {
LABEL_9:
        result = 0;
        goto LABEL_22;
      }
      result = 1;
    }
LABEL_22:
    if ( result )
      return result;
    _mm_pause();
  }
}

```

## disassembly

```asm
0x180003700  push    rbx; private: void CReaderWriterLock3::_LockSpin(enum CReaderWriterLock3::SPIN_TYPE)
0x180003702  push    rbp
0x180003703  push    rsi
0x180003704  push    rdi
0x180003705  push    r12
0x180003707  push    r14
0x180003709  push    r15
0x18000370b  sub     rsp, 20h
0x18000370f  mov     r15d, edx
0x180003712  mov     rsi, rcx
0x180003715  xor     ebp, ebp
0x180003717  call    cs:__imp_GetCurrentThreadId
0x18000371d  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180003724  lea     r12, __ImageBase
0x18000372b  mov     r9d, eax
0x18000372e  mov     eax, 4EC4EC4Fh
0x180003733  mul     r9d
0x180003736  movd    xmm0, ecx
0x18000373a  cvtdq2pd xmm0, xmm0
0x18000373e  shr     edx, 2
0x180003741  imul    r8d, edx, 0Dh
0x180003745  sub     r9d, r8d
0x180003748  xor     r14d, r14d
0x18000374b  mulsd   xmm0, ds:rva qword_180030E80[r12+r9*8]
0x180003755  cvttsd2si edi, xmm0
0x180003759  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180003760  mov     ebx, edi
0x180003762  jb      loc_18000388F
0x180003768  test    cx, cx
0x18000376b  jz      loc_18000388F
0x180003771  sub     ebx, 1
0x180003774  js      short loc_1800037A1
0x180003776  cmp     r15d, 1
0x18000377a  jz      loc_180003822
0x180003780  mov     edx, [rsi]
0x180003782  cmp     r15d, 2
0x180003786  jnz     short loc_180003801
0x180003788  test    edx, 0FFFF8000h
0x18000378e  jnz     short loc_18000379D
0x180003790  lea     ecx, [rdx+1]
0x180003793  mov     eax, edx
0x180003795  lock cmpxchg [rsi], ecx
0x180003799  cmp     edx, eax
0x18000379b  jz      short loc_180003815
0x18000379d  xor     al, al
0x18000379f  jmp     short loc_180003817
0x1800037a1  test    ebp, ebp
0x1800037a3  jnz     short loc_1800037B5
0x1800037a5  mov     rax, cs:?g_pfnSwitchToThread@@3P6AHXZEA; int (*g_pfnSwitchToThread)(void)
0x1800037ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b1  test    eax, eax
0x1800037b3  jnz     short loc_1800037BD
0x1800037b5  mov     ecx, ebp; dwMilliseconds
0x1800037b7  call    cs:__imp_Sleep
0x1800037bd  cmp     r14d, 4
0x1800037c1  jb      loc_180003860
0x1800037c7  mov     ebp, 64h ; 'd'
0x1800037cc  movd    xmm0, edi
0x1800037d0  cvtdq2pd xmm0, xmm0
0x1800037d4  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock3@@1NA; double CReaderWriterLock3::sm_dblDfltSpinAdjFctr
0x1800037dc  cvttsd2si edi, xmm0
0x1800037e0  cmp     edi, 2710h
0x1800037e6  jg      short loc_18000384C
0x1800037e8  cmp     edi, 64h ; 'd'
0x1800037eb  jg      short loc_1800037F2
0x1800037ed  mov     edi, 64h ; 'd'
0x1800037f2  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x1800037f9  inc     r14d
0x1800037fc  jmp     loc_180003759
0x180003801  cmp     dx, 0FFFFh
0x180003806  jz      short loc_18000379D
0x180003808  lea     ecx, [rdx+1]
0x18000380b  mov     eax, edx
0x18000380d  lock cmpxchg [rsi], ecx
0x180003811  cmp     edx, eax
0x180003813  jnz     short loc_18000379D
0x180003815  mov     al, 1
0x180003817  test    al, al
0x180003819  jnz     short loc_18000386D
0x18000381b  pause
0x18000381d  jmp     loc_180003771
0x180003822  mov     eax, [rsi+4]
0x180003825  test    eax, eax
0x180003827  jnz     short loc_180003842
0x180003829  mov     edx, [rsi]
0x18000382b  test    dx, dx
0x18000382e  jnz     short loc_180003842
0x180003830  mov     ecx, edx
0x180003832  mov     eax, edx
0x180003834  or      ecx, 0FFFFh
0x18000383a  lock cmpxchg [rsi], ecx
0x18000383e  cmp     edx, eax
0x180003840  jz      short loc_18000387C
0x180003842  mov     rcx, rsi; this
0x180003845  call    ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
0x18000384a  jmp     short loc_180003817
0x18000384c  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180003853  mov     edi, 2710h
0x180003858  inc     r14d
0x18000385b  jmp     loc_180003759
0x180003860  mov     ebp, ds:rva dword_180030D30[r12+r14*4]
0x180003868  jmp     loc_1800037CC
0x18000386d  add     rsp, 20h
0x180003871  pop     r15
0x180003873  pop     r14
0x180003875  pop     r12
0x180003877  pop     rdi
0x180003878  pop     rsi
0x180003879  pop     rbp
0x18000387a  pop     rbx
0x18000387b  retn
0x18000387c  call    cs:__imp_GetCurrentThreadId
0x180003882  and     eax, 0FFFFFFFCh
0x180003885  or      eax, 1
0x180003888  xchg    eax, [rsi+4]
0x18000388b  mov     al, 1
0x18000388d  jmp     short loc_180003817
0x18000388f  mov     ebx, 1
0x180003894  jmp     loc_180003771
```
