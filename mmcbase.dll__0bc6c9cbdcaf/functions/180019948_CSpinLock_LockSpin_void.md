# CSpinLock::_LockSpin(void)

- ea: `0x180019948`
- end: `0x180019a2c`
- name: `?_LockSpin@CSpinLock@@AEAAXXZ`
- size: `228`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180019cfc`

## callees

- `0x1800195d4`
- `0x1800195f4`
- `0x180019948`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019954`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019a01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019954`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019a01`

## pseudocode

```c
void __fastcall CSpinLock::_LockSpin(CSpinLock *this)
{
  DWORD v1; // esi
  unsigned int v2; // edi
  int v3; // ebx
  int v4; // edx

  v1 = 0;
  v2 = 0;
  v3 = (int)(*(double *)&qword_1800230D0[GetCurrentThreadId() % 0xD] * 4000.0);
  while ( 1 )
  {
    if ( g_cProcessors <= 1 )
    {
      SwitchOrSleep(v1);
      v1 = SleepTime(v2);
    }
    else
    {
      v4 = v3;
      while ( LKRhash::CLKRLinearHashTable::sm_llGlobalList )
      {
        if ( --v4 < 0 )
        {
          SwitchOrSleep(v1);
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
          v1 = SleepTime(v2);
        }
      }
    }
    if ( !LKRhash::CLKRLinearHashTable::sm_llGlobalList
      && !_InterlockedCompareExchange(
            (volatile signed __int32 *)&LKRhash::CLKRLinearHashTable::sm_llGlobalList,
            GetCurrentThreadId() & 0xFFFFFFFC | 1,
            0) )
    {
      break;
    }
    ++v2;
  }
}

```

## disassembly

```asm
0x180019948  push    rbx
0x18001994a  push    rsi
0x18001994b  push    rdi
0x18001994c  push    r14
0x18001994e  sub     rsp, 28h
0x180019952  xor     esi, esi
0x180019954  call    cs:__imp_GetCurrentThreadId
0x18001995a  mov     r8d, eax
0x18001995d  lea     r14d, [rsi+64h]
0x180019961  mov     eax, 4EC4EC4Fh
0x180019966  mul     r8d
0x180019969  shr     edx, 2
0x18001996c  imul    ecx, edx, 0Dh
0x18001996f  sub     r8d, ecx
0x180019972  lea     rcx, qword_1800230D0
0x180019979  xor     edi, edi
0x18001997b  movsd   xmm0, qword ptr [rcx+r8*8]
0x180019981  mulsd   xmm0, cs:__real@40af400000000000
0x180019989  cvttsd2si ebx, xmm0
0x18001998d  cmp     cs:?g_cProcessors@@3KA, 1; ulong g_cProcessors
0x180019994  jbe     short loc_1800199E7
0x180019996  mov     edx, ebx
0x180019998  jmp     short loc_1800199DB
0x18001999a  sub     edx, 1
0x18001999d  jns     short loc_1800199DB
0x18001999f  mov     ecx, esi; dwMilliseconds
0x1800199a1  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x1800199a6  movd    xmm0, ebx
0x1800199aa  cvtdq2pd xmm0, xmm0
0x1800199ae  mulsd   xmm0, cs:__real@3fe0000000000000
0x1800199b6  cvttsd2si ebx, xmm0
0x1800199ba  cmp     ebx, 2710h
0x1800199c0  jle     short loc_1800199C9
0x1800199c2  mov     ebx, 2710h
0x1800199c7  jmp     short loc_1800199D0
0x1800199c9  cmp     ebx, r14d
0x1800199cc  cmovle  ebx, r14d
0x1800199d0  mov     ecx, edi; unsigned int
0x1800199d2  mov     edx, ebx
0x1800199d4  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x1800199d9  mov     esi, eax
0x1800199db  mov     eax, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x1800199e1  test    eax, eax
0x1800199e3  jnz     short loc_18001999A
0x1800199e5  jmp     short loc_1800199F7
0x1800199e7  mov     ecx, esi; dwMilliseconds
0x1800199e9  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x1800199ee  mov     ecx, edi; unsigned int
0x1800199f0  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x1800199f5  mov     esi, eax
0x1800199f7  mov     eax, cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x1800199fd  test    eax, eax
0x1800199ff  jnz     short loc_180019A1B
0x180019a01  call    cs:__imp_GetCurrentThreadId
0x180019a07  mov     ecx, eax
0x180019a09  and     ecx, 0FFFFFFFDh
0x180019a0c  or      ecx, 1
0x180019a0f  xor     eax, eax
0x180019a11  lock cmpxchg cs:?sm_llGlobalList@CLKRLinearHashTable@LKRhash@@0VCLockedDoubleList@@A, ecx; CLockedDoubleList LKRhash::CLKRLinearHashTable::sm_llGlobalList
0x180019a19  jz      short loc_180019A22
0x180019a1b  inc     edi
0x180019a1d  jmp     loc_18001998D
0x180019a22  add     rsp, 28h
0x180019a26  pop     r14
0x180019a28  pop     rdi
0x180019a29  pop     rsi
0x180019a2a  pop     rbx
0x180019a2b  retn
```
