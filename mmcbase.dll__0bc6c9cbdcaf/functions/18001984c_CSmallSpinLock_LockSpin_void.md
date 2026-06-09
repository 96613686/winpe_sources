# CSmallSpinLock::_LockSpin(void)

- ea: `0x18001984c`
- end: `0x180019942`
- name: `?_LockSpin@CSmallSpinLock@@AEAAXXZ`
- size: `246`
- prototype: `void __fastcall(CSmallSpinLock *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800013a0`
- `0x180001c00`
- `0x180001f90`
- `0x180003fa0`
- `0x1800040b0`
- `0x18000585c`

## callees

- `0x1800195d4`
- `0x1800195f4`
- `0x18001984c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800198a3`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800198a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019863`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019897`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800198b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019863`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019897`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800198b5`

## pseudocode

```c
void __fastcall CSmallSpinLock::_LockSpin(CSmallSpinLock *this)
{
  DWORD v2; // ebp
  int v3; // ebx
  unsigned int v4; // edi
  int v5; // edx

  v2 = 0;
  v3 = (int)(*(double *)&qword_1800230D0[GetCurrentThreadId() % 0xD] * 4000.0);
  if ( *(_DWORD *)this == GetCurrentThreadId() )
    DebugBreak();
  v4 = 0;
  while ( *(_DWORD *)this || _InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId(), 0) )
  {
    if ( g_cProcessors <= 1 )
    {
      SwitchOrSleep(v2);
      v2 = SleepTime(v4);
    }
    else
    {
      v5 = v3;
      while ( *(_DWORD *)this )
      {
        if ( --v5 < 0 )
        {
          SwitchOrSleep(v2);
          v3 = (int)((double)v3 * 0.5);
          if ( v3 <= 10000 )
          {
            if ( v3 <= 100 )
              v3 = 100;
          }
          else
          {
            v3 = 10000;
          }
          v2 = SleepTime(v4);
        }
      }
    }
    ++v4;
  }
}

```

## disassembly

```asm
0x18001984c  mov     [rsp+arg_8], rbx
0x180019851  mov     [rsp+arg_10], rbp
0x180019856  push    rsi
0x180019857  push    rdi
0x180019858  push    r15
0x18001985a  sub     rsp, 20h
0x18001985e  mov     rsi, rcx
0x180019861  xor     ebp, ebp
0x180019863  call    cs:__imp_GetCurrentThreadId
0x180019869  mov     r9d, eax
0x18001986c  lea     rcx, qword_1800230D0
0x180019873  mov     eax, 4EC4EC4Fh
0x180019878  mul     r9d
0x18001987b  shr     edx, 2
0x18001987e  imul    r8d, edx, 0Dh
0x180019882  sub     r9d, r8d
0x180019885  movsd   xmm0, qword ptr [rcx+r9*8]
0x18001988b  mulsd   xmm0, cs:__real@40af400000000000
0x180019893  cvttsd2si ebx, xmm0
0x180019897  call    cs:__imp_GetCurrentThreadId
0x18001989d  mov     ecx, [rsi]
0x18001989f  cmp     ecx, eax
0x1800198a1  jnz     short loc_1800198A9
0x1800198a3  call    cs:__imp_DebugBreak
0x1800198a9  xor     edi, edi
0x1800198ab  lea     r15d, [rdi+64h]
0x1800198af  mov     eax, [rsi]
0x1800198b1  test    eax, eax
0x1800198b3  jnz     short loc_1800198C5
0x1800198b5  call    cs:__imp_GetCurrentThreadId
0x1800198bb  mov     ecx, eax
0x1800198bd  xor     eax, eax
0x1800198bf  lock cmpxchg [rsi], ecx
0x1800198c3  jz      short loc_18001992F
0x1800198c5  cmp     cs:?g_cProcessors@@3KA, 1; ulong g_cProcessors
0x1800198cc  jbe     short loc_18001991B
0x1800198ce  mov     edx, ebx
0x1800198d0  jmp     short loc_180019913
0x1800198d2  sub     edx, 1
0x1800198d5  jns     short loc_180019913
0x1800198d7  mov     ecx, ebp; dwMilliseconds
0x1800198d9  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x1800198de  movd    xmm0, ebx
0x1800198e2  cvtdq2pd xmm0, xmm0
0x1800198e6  mulsd   xmm0, cs:__real@3fe0000000000000
0x1800198ee  cvttsd2si ebx, xmm0
0x1800198f2  cmp     ebx, 2710h
0x1800198f8  jle     short loc_180019901
0x1800198fa  mov     ebx, 2710h
0x1800198ff  jmp     short loc_180019908
0x180019901  cmp     ebx, r15d
0x180019904  cmovle  ebx, r15d
0x180019908  mov     ecx, edi; unsigned int
0x18001990a  mov     edx, ebx
0x18001990c  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180019911  mov     ebp, eax
0x180019913  mov     eax, [rsi]
0x180019915  test    eax, eax
0x180019917  jnz     short loc_1800198D2
0x180019919  jmp     short loc_18001992B
0x18001991b  mov     ecx, ebp; dwMilliseconds
0x18001991d  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x180019922  mov     ecx, edi; unsigned int
0x180019924  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180019929  mov     ebp, eax
0x18001992b  inc     edi
0x18001992d  jmp     short loc_1800198AF
0x18001992f  mov     rbx, [rsp+38h+arg_8]
0x180019934  mov     rbp, [rsp+38h+arg_10]
0x180019939  add     rsp, 20h
0x18001993d  pop     r15
0x18001993f  pop     rdi
0x180019940  pop     rsi
0x180019941  retn
```
