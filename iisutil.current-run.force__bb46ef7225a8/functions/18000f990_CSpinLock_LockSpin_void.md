# CSpinLock::_LockSpin(void)

- ea: `0x18000f990`
- end: `0x18000fa85`
- name: `?_LockSpin@CSpinLock@@AEAAXXZ`
- size: `245`
- prototype: `void __fastcall(CSpinLock *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f950`

## callees

- `0x180008e70`
- `0x18000f990`
- `0x180010b30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f9ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fa11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f9ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fa11`

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
  v5 = (int)((double)v1 * *(double *)&qword_180030E80[GetCurrentThreadId() % 0xD]);
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
0x18000f990  push    rbx
0x18000f992  push    rbp
0x18000f993  push    rsi
0x18000f994  push    rdi
0x18000f995  push    r12
0x18000f997  push    r14
0x18000f999  sub     rsp, 28h
0x18000f99d  movzx   ebx, cs:?sm_wDefaultSpinCount@CSpinLock@@1GA; ushort CSpinLock::sm_wDefaultSpinCount
0x18000f9a4  xor     r14d, r14d
0x18000f9a7  mov     ebp, r14d
0x18000f9aa  mov     rdi, rcx
0x18000f9ad  call    cs:__imp_GetCurrentThreadId
0x18000f9b3  movd    xmm0, ebx
0x18000f9b7  lea     rcx, qword_180030E80
0x18000f9be  mov     r9d, eax
0x18000f9c1  lea     r12d, [r14+64h]
0x18000f9c5  mov     eax, 4EC4EC4Fh
0x18000f9ca  mov     esi, r14d
0x18000f9cd  mul     r9d
0x18000f9d0  cvtdq2pd xmm0, xmm0
0x18000f9d4  shr     edx, 2
0x18000f9d7  imul    r8d, edx, 0Dh
0x18000f9db  sub     r9d, r8d
0x18000f9de  mulsd   xmm0, qword ptr [rcx+r9*8]
0x18000f9e4  cvttsd2si ebx, xmm0
0x18000f9e8  cmp     cs:?g_cProcessors@@3KA, 1; ulong g_cProcessors
0x18000f9ef  jbe     short loc_18000F9FB
0x18000f9f1  cmp     cs:?sm_wDefaultSpinCount@CSpinLock@@1GA, r14w; ushort CSpinLock::sm_wDefaultSpinCount
0x18000f9f9  jnz     short loc_18000FA6A
0x18000f9fb  mov     ecx, ebp; unsigned int
0x18000f9fd  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18000fa02  mov     ecx, esi; unsigned int
0x18000fa04  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x18000fa09  mov     ebp, eax
0x18000fa0b  mov     eax, [rdi]
0x18000fa0d  test    eax, eax
0x18000fa0f  jnz     short loc_18000FA27
0x18000fa11  call    cs:__imp_GetCurrentThreadId
0x18000fa17  mov     ecx, eax
0x18000fa19  and     ecx, 0FFFFFFFDh
0x18000fa1c  or      ecx, 1
0x18000fa1f  xor     eax, eax
0x18000fa21  lock cmpxchg [rdi], ecx
0x18000fa25  jz      short loc_18000FA78
0x18000fa27  inc     esi
0x18000fa29  jmp     short loc_18000F9E8
0x18000fa2b  sub     edx, 1
0x18000fa2e  jns     short loc_18000FA6E
0x18000fa30  mov     ecx, ebp; unsigned int
0x18000fa32  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18000fa37  mov     ecx, esi; unsigned int
0x18000fa39  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x18000fa3e  movd    xmm0, ebx
0x18000fa42  mov     ebp, eax
0x18000fa44  cvtdq2pd xmm0, xmm0
0x18000fa48  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CSpinLock@@1NA; double CSpinLock::sm_dblDfltSpinAdjFctr
0x18000fa50  cvttsd2si ebx, xmm0
0x18000fa54  cmp     ebx, 2710h
0x18000fa5a  jle     short loc_18000FA63
0x18000fa5c  mov     ebx, 2710h
0x18000fa61  jmp     short loc_18000FA6A
0x18000fa63  cmp     ebx, r12d
0x18000fa66  cmovle  ebx, r12d
0x18000fa6a  mov     edx, ebx
0x18000fa6c  jmp     short loc_18000FA70
0x18000fa6e  pause
0x18000fa70  mov     eax, [rdi]
0x18000fa72  test    eax, eax
0x18000fa74  jnz     short loc_18000FA2B
0x18000fa76  jmp     short loc_18000FA0B
0x18000fa78  add     rsp, 28h
0x18000fa7c  pop     r14
0x18000fa7e  pop     r12
0x18000fa80  pop     rdi
0x18000fa81  pop     rsi
0x18000fa82  pop     rbp
0x18000fa83  pop     rbx
0x18000fa84  retn
```
