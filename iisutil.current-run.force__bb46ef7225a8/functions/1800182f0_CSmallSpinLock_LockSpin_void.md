# CSmallSpinLock::_LockSpin(void)

- ea: `0x1800182f0`
- end: `0x1800183f0`
- name: `?_LockSpin@CSmallSpinLock@@AEAAXXZ`
- size: `256`
- prototype: `void __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800182b0`

## callees

- `0x180008e70`
- `0x180010b30`
- `0x1800182f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001830a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001833f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001835d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001830a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001833f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001835d`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001834b`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001834b`

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
  v4 = (int)((double)v1 * *(double *)&qword_180030E80[GetCurrentThreadId() % 0xD]);
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
0x1800182f0  push    rbx
0x1800182f2  push    rbp
0x1800182f3  push    rsi
0x1800182f4  push    rdi
0x1800182f5  push    r12
0x1800182f7  push    r14
0x1800182f9  sub     rsp, 28h
0x1800182fd  movzx   r14d, cs:?sm_wDefaultSpinCount@CSmallSpinLock@@1GA; ushort CSmallSpinLock::sm_wDefaultSpinCount
0x180018305  mov     rsi, rcx
0x180018308  xor     ebp, ebp
0x18001830a  call    cs:__imp_GetCurrentThreadId
0x180018310  movd    xmm0, r14d
0x180018315  lea     rcx, qword_180030E80
0x18001831c  mov     r9d, eax
0x18001831f  mov     eax, 4EC4EC4Fh
0x180018324  mul     r9d
0x180018327  cvtdq2pd xmm0, xmm0
0x18001832b  shr     edx, 2
0x18001832e  imul    r8d, edx, 0Dh
0x180018332  sub     r9d, r8d
0x180018335  mulsd   xmm0, qword ptr [rcx+r9*8]
0x18001833b  cvttsd2si ebx, xmm0
0x18001833f  call    cs:__imp_GetCurrentThreadId
0x180018345  mov     ecx, [rsi]
0x180018347  cmp     ecx, eax
0x180018349  jnz     short loc_180018351
0x18001834b  call    cs:__imp_DebugBreak
0x180018351  xor     edi, edi
0x180018353  lea     r12d, [rdi+64h]
0x180018357  mov     eax, [rsi]
0x180018359  test    eax, eax
0x18001835b  jnz     short loc_18001836D
0x18001835d  call    cs:__imp_GetCurrentThreadId
0x180018363  mov     ecx, eax
0x180018365  xor     eax, eax
0x180018367  lock cmpxchg [rsi], ecx
0x18001836b  jz      short loc_1800183E3
0x18001836d  cmp     cs:?g_cProcessors@@3KA, 1; ulong g_cProcessors
0x180018374  jbe     short loc_1800183CC
0x180018376  test    r14d, r14d
0x180018379  jz      short loc_1800183CC
0x18001837b  mov     edx, ebx
0x18001837d  jmp     short loc_1800183C4
0x18001837f  sub     edx, 1
0x180018382  jns     short loc_1800183C2
0x180018384  mov     ecx, ebp; unsigned int
0x180018386  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18001838b  movd    xmm0, ebx
0x18001838f  cvtdq2pd xmm0, xmm0
0x180018393  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CSmallSpinLock@@1NA; double CSmallSpinLock::sm_dblDfltSpinAdjFctr
0x18001839b  cvttsd2si ebx, xmm0
0x18001839f  cmp     ebx, 2710h
0x1800183a5  jle     short loc_1800183AE
0x1800183a7  mov     ebx, 2710h
0x1800183ac  jmp     short loc_1800183B5
0x1800183ae  cmp     ebx, r12d
0x1800183b1  cmovle  ebx, r12d
0x1800183b5  mov     ecx, edi; unsigned int
0x1800183b7  mov     edx, ebx
0x1800183b9  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x1800183be  mov     ebp, eax
0x1800183c0  jmp     short loc_1800183C4
0x1800183c2  pause
0x1800183c4  mov     eax, [rsi]
0x1800183c6  test    eax, eax
0x1800183c8  jnz     short loc_18001837F
0x1800183ca  jmp     short loc_1800183DC
0x1800183cc  mov     ecx, ebp; unsigned int
0x1800183ce  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x1800183d3  mov     ecx, edi; unsigned int
0x1800183d5  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x1800183da  mov     ebp, eax
0x1800183dc  inc     edi
0x1800183de  jmp     loc_180018357
0x1800183e3  add     rsp, 28h
0x1800183e7  pop     r14
0x1800183e9  pop     r12
0x1800183eb  pop     rdi
0x1800183ec  pop     rsi
0x1800183ed  pop     rbp
0x1800183ee  pop     rbx
0x1800183ef  retn
```
