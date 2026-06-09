# CSmallSpinLock::_LockSpin(void)

- ea: `0x180019110`
- end: `0x180019229`
- name: `?_LockSpin@CSmallSpinLock@@AEAAXXZ`
- size: `281`
- prototype: `void __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800190d0`

## callees

- `0x180009bd0`
- `0x180011c10`
- `0x180019110`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001912a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019165`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001918f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001912a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019165`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001918f`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180019177`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180019177`

## pseudocode

```c
void __fastcall CSmallSpinLock::_LockSpin(CSmallSpinLock *this)
{
  int v1; // r14d
  unsigned int v3; // ebp
  int v4; // ebx
  unsigned int v5; // edi
  int v6; // edx

  v1 = CSmallSpinLock::sm_wDefaultSpinCount;
  v3 = 0;
  v4 = (int)((double)v1 * *(double *)&qword_180032E80[GetCurrentThreadId() % 0xD]);
  if ( *(_DWORD *)this == GetCurrentThreadId() )
    DebugBreak();
  v5 = 0;
  while ( *(_DWORD *)this || _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId(), 0) )
  {
    if ( g_cProcessors > 1 && v1 )
    {
      v6 = v4;
      while ( *(_DWORD *)this )
      {
        if ( --v6 >= 0 )
        {
          _mm_pause();
        }
        else
        {
          SwitchOrSleep(v3);
          v4 = (int)((double)v4 * CSmallSpinLock::sm_dblDfltSpinAdjFctr);
          if ( v4 <= 10000 )
          {
            if ( v4 <= 100 )
              v4 = 100;
          }
          else
          {
            v4 = 10000;
          }
          v3 = SleepTime(v5);
        }
      }
    }
    else
    {
      SwitchOrSleep(v3);
      v3 = SleepTime(v5);
    }
    ++v5;
  }
}

```

## disassembly

```asm
0x180019110  push    rbx
0x180019112  push    rbp
0x180019113  push    rsi
0x180019114  push    rdi
0x180019115  push    r12
0x180019117  push    r14
0x180019119  sub     rsp, 28h
0x18001911d  movzx   r14d, cs:?sm_wDefaultSpinCount@CSmallSpinLock@@1GA; ushort CSmallSpinLock::sm_wDefaultSpinCount
0x180019125  mov     rsi, rcx
0x180019128  xor     ebp, ebp
0x18001912a  call    cs:__imp_GetCurrentThreadId
0x180019131  nop     dword ptr [rax+rax+00h]
0x180019136  movd    xmm0, r14d
0x18001913b  lea     rcx, qword_180032E80
0x180019142  mov     r9d, eax
0x180019145  mov     eax, 4EC4EC4Fh
0x18001914a  mul     r9d
0x18001914d  cvtdq2pd xmm0, xmm0
0x180019151  shr     edx, 2
0x180019154  imul    r8d, edx, 0Dh
0x180019158  sub     r9d, r8d
0x18001915b  mulsd   xmm0, qword ptr [rcx+r9*8]
0x180019161  cvttsd2si ebx, xmm0
0x180019165  call    cs:__imp_GetCurrentThreadId
0x18001916c  nop     dword ptr [rax+rax+00h]
0x180019171  mov     ecx, [rsi]
0x180019173  cmp     ecx, eax
0x180019175  jnz     short loc_180019183
0x180019177  call    cs:__imp_DebugBreak
0x18001917e  nop     dword ptr [rax+rax+00h]
0x180019183  xor     edi, edi
0x180019185  lea     r12d, [rdi+64h]
0x180019189  mov     eax, [rsi]
0x18001918b  test    eax, eax
0x18001918d  jnz     short loc_1800191A5
0x18001918f  call    cs:__imp_GetCurrentThreadId
0x180019196  nop     dword ptr [rax+rax+00h]
0x18001919b  mov     ecx, eax
0x18001919d  xor     eax, eax
0x18001919f  lock cmpxchg [rsi], ecx
0x1800191a3  jz      short loc_18001921B
0x1800191a5  cmp     cs:?g_cProcessors@@3KA, 1; ulong g_cProcessors
0x1800191ac  jbe     short loc_180019204
0x1800191ae  test    r14d, r14d
0x1800191b1  jz      short loc_180019204
0x1800191b3  mov     edx, ebx
0x1800191b5  jmp     short loc_1800191FC
0x1800191b7  sub     edx, 1
0x1800191ba  jns     short loc_1800191FA
0x1800191bc  mov     ecx, ebp; unsigned int
0x1800191be  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x1800191c3  movd    xmm0, ebx
0x1800191c7  cvtdq2pd xmm0, xmm0
0x1800191cb  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CSmallSpinLock@@1NA; double CSmallSpinLock::sm_dblDfltSpinAdjFctr
0x1800191d3  cvttsd2si ebx, xmm0
0x1800191d7  cmp     ebx, 2710h
0x1800191dd  jle     short loc_1800191E6
0x1800191df  mov     ebx, 2710h
0x1800191e4  jmp     short loc_1800191ED
0x1800191e6  cmp     ebx, r12d
0x1800191e9  cmovle  ebx, r12d
0x1800191ed  mov     ecx, edi; unsigned int
0x1800191ef  mov     edx, ebx
0x1800191f1  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x1800191f6  mov     ebp, eax
0x1800191f8  jmp     short loc_1800191FC
0x1800191fa  pause
0x1800191fc  mov     eax, [rsi]
0x1800191fe  test    eax, eax
0x180019200  jnz     short loc_1800191B7
0x180019202  jmp     short loc_180019214
0x180019204  mov     ecx, ebp; unsigned int
0x180019206  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18001920b  mov     ecx, edi; unsigned int
0x18001920d  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180019212  mov     ebp, eax
0x180019214  inc     edi
0x180019216  jmp     loc_180019189
0x18001921b  add     rsp, 28h
0x18001921f  pop     r14
0x180019221  pop     r12
0x180019223  pop     rdi
0x180019224  pop     rsi
0x180019225  pop     rbp
0x180019226  pop     rbx
0x180019227  retn
```
