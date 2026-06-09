# CSpinLock::_LockSpin(void)

- ea: `0x180010d10`
- end: `0x180010e12`
- name: `?_LockSpin@CSpinLock@@AEAAXXZ`
- size: `258`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010cd0`

## callees

- `0x180009bd0`
- `0x180010d10`
- `0x180011c10`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010d2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010d97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010d2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010d97`

## pseudocode

```c
void __fastcall CSpinLock::_LockSpin(CSpinLock *this)
{
  int v1; // ebx
  unsigned int v2; // ebp
  unsigned int v4; // esi
  int v5; // ebx
  int v6; // edx

  v1 = CSpinLock::sm_wDefaultSpinCount;
  v2 = 0;
  v4 = 0;
  v5 = (int)((double)v1 * *(double *)&qword_180032E80[GetCurrentThreadId() % 0xD]);
  while ( 1 )
  {
    if ( g_cProcessors > 1 && CSpinLock::sm_wDefaultSpinCount )
    {
LABEL_13:
      v6 = v5;
      while ( *(_DWORD *)this )
      {
        if ( --v6 < 0 )
        {
          SwitchOrSleep(v2);
          v2 = SleepTime(v4);
          v5 = (int)((double)v5 * CSpinLock::sm_dblDfltSpinAdjFctr);
          if ( v5 <= 10000 )
          {
            if ( v5 <= 100 )
              v5 = 100;
          }
          else
          {
            v5 = 10000;
          }
          goto LABEL_13;
        }
        _mm_pause();
      }
    }
    else
    {
      SwitchOrSleep(v2);
      v2 = SleepTime(v4);
    }
    if ( !*(_DWORD *)this
      && !_InterlockedCompareExchange((volatile signed __int32 *)this, GetCurrentThreadId() & 0xFFFFFFFC | 1, 0) )
    {
      break;
    }
    ++v4;
  }
}

```

## disassembly

```asm
0x180010d10  push    rbx
0x180010d12  push    rbp
0x180010d13  push    rsi
0x180010d14  push    rdi
0x180010d15  push    r12
0x180010d17  push    r14
0x180010d19  sub     rsp, 28h
0x180010d1d  movzx   ebx, cs:?sm_wDefaultSpinCount@CSpinLock@@1GA; ushort CSpinLock::sm_wDefaultSpinCount
0x180010d24  xor     r14d, r14d
0x180010d27  mov     ebp, r14d
0x180010d2a  mov     rdi, rcx
0x180010d2d  call    cs:__imp_GetCurrentThreadId
0x180010d34  nop     dword ptr [rax+rax+00h]
0x180010d39  movd    xmm0, ebx
0x180010d3d  lea     rcx, qword_180032E80
0x180010d44  mov     r9d, eax
0x180010d47  lea     r12d, [r14+64h]
0x180010d4b  mov     eax, 4EC4EC4Fh
0x180010d50  mov     esi, r14d
0x180010d53  mul     r9d
0x180010d56  cvtdq2pd xmm0, xmm0
0x180010d5a  shr     edx, 2
0x180010d5d  imul    r8d, edx, 0Dh
0x180010d61  sub     r9d, r8d
0x180010d64  mulsd   xmm0, qword ptr [rcx+r9*8]
0x180010d6a  cvttsd2si ebx, xmm0
0x180010d6e  cmp     cs:?g_cProcessors@@3KA, 1; ulong g_cProcessors
0x180010d75  jbe     short loc_180010D81
0x180010d77  cmp     cs:?sm_wDefaultSpinCount@CSpinLock@@1GA, r14w; ushort CSpinLock::sm_wDefaultSpinCount
0x180010d7f  jnz     short loc_180010DF6
0x180010d81  mov     ecx, ebp; unsigned int
0x180010d83  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x180010d88  mov     ecx, esi; unsigned int
0x180010d8a  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180010d8f  mov     ebp, eax
0x180010d91  mov     eax, [rdi]
0x180010d93  test    eax, eax
0x180010d95  jnz     short loc_180010DB3
0x180010d97  call    cs:__imp_GetCurrentThreadId
0x180010d9e  nop     dword ptr [rax+rax+00h]
0x180010da3  mov     ecx, eax
0x180010da5  and     ecx, 0FFFFFFFDh
0x180010da8  or      ecx, 1
0x180010dab  xor     eax, eax
0x180010dad  lock cmpxchg [rdi], ecx
0x180010db1  jz      short loc_180010E04
0x180010db3  inc     esi
0x180010db5  jmp     short loc_180010D6E
0x180010db7  sub     edx, 1
0x180010dba  jns     short loc_180010DFA
0x180010dbc  mov     ecx, ebp; unsigned int
0x180010dbe  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x180010dc3  mov     ecx, esi; unsigned int
0x180010dc5  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180010dca  movd    xmm0, ebx
0x180010dce  mov     ebp, eax
0x180010dd0  cvtdq2pd xmm0, xmm0
0x180010dd4  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CSpinLock@@1NA; double CSpinLock::sm_dblDfltSpinAdjFctr
0x180010ddc  cvttsd2si ebx, xmm0
0x180010de0  cmp     ebx, 2710h
0x180010de6  jle     short loc_180010DEF
0x180010de8  mov     ebx, 2710h
0x180010ded  jmp     short loc_180010DF6
0x180010def  cmp     ebx, r12d
0x180010df2  cmovle  ebx, r12d
0x180010df6  mov     edx, ebx
0x180010df8  jmp     short loc_180010DFC
0x180010dfa  pause
0x180010dfc  mov     eax, [rdi]
0x180010dfe  test    eax, eax
0x180010e00  jnz     short loc_180010DB7
0x180010e02  jmp     short loc_180010D91
0x180010e04  add     rsp, 28h
0x180010e08  pop     r14
0x180010e0a  pop     r12
0x180010e0c  pop     rdi
0x180010e0d  pop     rsi
0x180010e0e  pop     rbp
0x180010e0f  pop     rbx
0x180010e10  retn
```
