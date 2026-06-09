# CReaderWriterLock3::_WriteLockSpin(void)

- ea: `0x180007180`
- end: `0x1800072f8`
- name: `?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ`
- size: `376`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `15`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002680`
- `0x1800038a0`
- `0x180003a10`
- `0x180005110`
- `0x180005b40`
- `0x1800073e0`
- `0x180007750`
- `0x1800086e0`
- `0x180009af0`
- `0x18000a110`
- `0x18000a9d0`
- `0x18000d1a0`
- `0x18000d970`
- `0x18000fab0`
- `0x18001a2a0`

## callees

- `0x1800039d0`
- `0x180007180`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800071ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000723f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800071ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000723f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007273`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007273`

## pseudocode

```c
void __fastcall CReaderWriterLock3::_WriteLockSpin(CReaderWriterLock3 *this)
{
  signed __int32 i; // ecx
  DWORD v3; // ebp
  DWORD CurrentThreadId; // eax
  unsigned int v5; // r14d
  unsigned __int16 v6; // dx
  int v7; // edi
  int v8; // esi
  signed __int32 v9; // edx

  for ( i = *(_DWORD *)this;
        i != _InterlockedCompareExchange((volatile signed __int32 *)this, i + 0x10000, i);
        i = *(_DWORD *)this )
  {
    _mm_pause();
  }
  v3 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v5 = 0;
  v6 = CReaderWriterLock3::sm_wDefaultSpinCount;
  v7 = (int)((double)CReaderWriterLock3::sm_wDefaultSpinCount * *(double *)&qword_180030E80[CurrentThreadId % 0xD]);
LABEL_4:
  v8 = v7;
  if ( g_cProcessors < 2 || !v6 )
    v8 = 1;
  while ( 1 )
  {
    if ( --v8 < 0 )
    {
      if ( v3 || !g_pfnSwitchToThread() )
        Sleep(v3);
      if ( v5 < 4 )
        v3 = dword_180030D30[v5];
      else
        v3 = 100;
      v7 = (int)((double)v7 * CReaderWriterLock3::sm_dblDfltSpinAdjFctr);
      if ( v7 <= 10000 )
      {
        if ( v7 <= 100 )
          v7 = 100;
      }
      else
      {
        v7 = 10000;
      }
      v6 = CReaderWriterLock3::sm_wDefaultSpinCount;
      ++v5;
      goto LABEL_4;
    }
    if ( !*((_DWORD *)this + 1) && !(unsigned __int16)*(_DWORD *)this )
    {
      v9 = *(_DWORD *)this;
      if ( v9 == _InterlockedCompareExchange((volatile signed __int32 *)this, v9 | 0xFFFF, v9) )
        break;
    }
    if ( CReaderWriterLock3::_TryWriteLock2(this) )
      return;
    _mm_pause();
  }
  _InterlockedExchange((volatile __int32 *)this + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
}

```

## disassembly

```asm
0x180007180  push    rbx
0x180007182  push    rbp
0x180007183  push    rsi
0x180007184  push    rdi
0x180007185  push    r13
0x180007187  push    r14
0x180007189  push    r15
0x18000718b  sub     rsp, 20h
0x18000718f  mov     rbx, rcx
0x180007192  mov     ecx, [rcx]
0x180007194  lea     edx, [rcx+10000h]
0x18000719a  mov     eax, ecx
0x18000719c  lock cmpxchg [rbx], edx
0x1800071a0  cmp     ecx, eax
0x1800071a2  jnz     loc_1800072C5
0x1800071a8  xor     r15d, r15d
0x1800071ab  mov     ebp, r15d
0x1800071ae  call    cs:__imp_GetCurrentThreadId
0x1800071b4  mov     r14d, r15d
0x1800071b7  lea     r13d, [r15+64h]
0x1800071bb  mov     r8d, eax
0x1800071be  mov     eax, 4EC4EC4Fh
0x1800071c3  mul     r8d
0x1800071c6  shr     edx, 2
0x1800071c9  imul    ecx, edx, 0Dh
0x1800071cc  movzx   edx, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x1800071d3  sub     r8d, ecx
0x1800071d6  movd    xmm0, edx
0x1800071da  mov     ecx, r8d
0x1800071dd  lea     r8, __ImageBase
0x1800071e4  cvtdq2pd xmm0, xmm0
0x1800071e8  mulsd   xmm0, ds:rva qword_180030E80[r8+rcx*8]
0x1800071f2  cvttsd2si edi, xmm0
0x1800071f6  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x1800071fd  mov     esi, edi
0x1800071ff  jb      loc_1800072E5
0x180007205  test    dx, dx
0x180007208  jz      loc_1800072E5
0x18000720e  sub     esi, 1
0x180007211  js      short loc_18000725D
0x180007213  mov     eax, [rbx+4]
0x180007216  test    eax, eax
0x180007218  jnz     loc_1800072CE
0x18000721e  mov     edx, [rbx]
0x180007220  test    dx, dx
0x180007223  jnz     loc_1800072CE
0x180007229  mov     ecx, edx
0x18000722b  mov     eax, edx
0x18000722d  or      ecx, 0FFFFh
0x180007233  lock cmpxchg [rbx], ecx
0x180007237  cmp     edx, eax
0x180007239  jnz     loc_1800072CE
0x18000723f  call    cs:__imp_GetCurrentThreadId
0x180007245  and     eax, 0FFFFFFFCh
0x180007248  or      eax, 1
0x18000724b  xchg    eax, [rbx+4]
0x18000724e  add     rsp, 20h
0x180007252  pop     r15
0x180007254  pop     r14
0x180007256  pop     r13
0x180007258  pop     rdi
0x180007259  pop     rsi
0x18000725a  pop     rbp
0x18000725b  pop     rbx
0x18000725c  retn
0x18000725d  test    ebp, ebp
0x18000725f  jnz     short loc_180007271
0x180007261  mov     rax, cs:?g_pfnSwitchToThread@@3P6AHXZEA; int (*g_pfnSwitchToThread)(void)
0x180007268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000726d  test    eax, eax
0x18000726f  jnz     short loc_180007279
0x180007271  mov     ecx, ebp; dwMilliseconds
0x180007273  call    cs:__imp_Sleep
0x180007279  cmp     r14d, 4
0x18000727d  jb      short loc_1800072B2
0x18000727f  mov     ebp, r13d
0x180007282  movd    xmm0, edi
0x180007286  cvtdq2pd xmm0, xmm0
0x18000728a  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock3@@1NA; double CReaderWriterLock3::sm_dblDfltSpinAdjFctr
0x180007292  cvttsd2si edi, xmm0
0x180007296  cmp     edi, 2710h
0x18000729c  jle     short loc_1800072EF
0x18000729e  mov     edi, 2710h
0x1800072a3  movzx   edx, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x1800072aa  inc     r14d
0x1800072ad  jmp     loc_1800071F6
0x1800072b2  mov     eax, r14d
0x1800072b5  lea     rcx, __ImageBase
0x1800072bc  mov     ebp, ds:rva dword_180030D30[rcx+rax*4]
0x1800072c3  jmp     short loc_180007282
0x1800072c5  pause
0x1800072c7  mov     ecx, [rbx]
0x1800072c9  jmp     loc_180007194
0x1800072ce  mov     rcx, rbx; this
0x1800072d1  call    ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
0x1800072d6  test    al, al
0x1800072d8  jnz     loc_18000724E
0x1800072de  pause
0x1800072e0  jmp     loc_18000720E
0x1800072e5  mov     esi, 1
0x1800072ea  jmp     loc_18000720E
0x1800072ef  cmp     edi, r13d
0x1800072f2  cmovle  edi, r13d
0x1800072f6  jmp     short loc_1800072A3
```
