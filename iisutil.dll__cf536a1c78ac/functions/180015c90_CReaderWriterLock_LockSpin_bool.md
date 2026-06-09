# CReaderWriterLock::_LockSpin(bool)

- ea: `0x180015c90`
- end: `0x180015db4`
- name: `?_LockSpin@CReaderWriterLock@@AEAAX_N@Z`
- size: `292`
- prototype: `void __fastcall(CReaderWriterLock *__hidden this, bool)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015be0`
- `0x180015c10`
- `0x180015c50`
- `0x18001c9a0`
- `0x18001ca00`

## callees

- `0x180009bd0`
- `0x180011c10`
- `0x180015c90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015cb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015cb2`

## pseudocode

```c
void __fastcall CReaderWriterLock::_LockSpin(CReaderWriterLock *this, char a2)
{
  unsigned int v3; // ebp
  DWORD CurrentThreadId; // eax
  unsigned __int16 v6; // cx
  unsigned int v7; // esi
  int v8; // ebx
  int v9; // r8d
  bool v10; // zf
  signed __int32 v11; // edx
  char v12; // al

  v3 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v6 = CReaderWriterLock::sm_wDefaultSpinCount;
  v7 = 0;
  v8 = (int)((double)CReaderWriterLock::sm_wDefaultSpinCount * *(double *)&qword_180032E80[CurrentThreadId % 0xD]);
LABEL_2:
  v9 = v8;
  if ( g_cProcessors < 2 || !v6 )
    v9 = 1;
  while ( 1 )
  {
    if ( --v9 < 0 )
    {
      SwitchOrSleep(v3);
      v3 = SleepTime(v7);
      v8 = (int)((double)v8 * CReaderWriterLock::sm_dblDfltSpinAdjFctr);
      if ( v8 <= 10000 )
      {
        if ( v8 <= 100 )
          v8 = 100;
      }
      else
      {
        v8 = 10000;
      }
      v6 = CReaderWriterLock::sm_wDefaultSpinCount;
      ++v7;
      goto LABEL_2;
    }
    if ( a2 )
    {
      if ( !*(_DWORD *)this )
      {
        v10 = _InterlockedCompareExchange((volatile signed __int32 *)this, -1, 0) == 0;
        goto LABEL_12;
      }
    }
    else if ( *(_DWORD *)this != -1 && !*((_DWORD *)this + 1) )
    {
      v11 = *(_DWORD *)this;
      v10 = v11 == _InterlockedCompareExchange((volatile signed __int32 *)this, v11 + 1, v11);
LABEL_12:
      v12 = 1;
      if ( v10 )
        goto LABEL_14;
    }
    v12 = 0;
LABEL_14:
    if ( v12 )
      break;
    _mm_pause();
  }
}

```

## disassembly

```asm
0x180015c90  mov     [rsp+arg_0], rbx
0x180015c95  mov     [rsp+arg_10], rbp
0x180015c9a  push    rsi
0x180015c9b  push    rdi
0x180015c9c  push    r13
0x180015c9e  push    r14
0x180015ca0  push    r15
0x180015ca2  sub     rsp, 20h
0x180015ca6  xor     r15d, r15d
0x180015ca9  mov     r14b, dl
0x180015cac  mov     ebp, r15d
0x180015caf  mov     rdi, rcx
0x180015cb2  call    cs:__imp_GetCurrentThreadId
0x180015cb9  nop     dword ptr [rax+rax+00h]
0x180015cbe  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock@@1GA; ushort CReaderWriterLock::sm_wDefaultSpinCount
0x180015cc5  mov     esi, r15d
0x180015cc8  mov     r9d, eax
0x180015ccb  mov     eax, 4EC4EC4Fh
0x180015cd0  mul     r9d
0x180015cd3  movd    xmm0, ecx
0x180015cd7  cvtdq2pd xmm0, xmm0
0x180015cdb  shr     edx, 2
0x180015cde  imul    r8d, edx, 0Dh
0x180015ce2  lea     rdx, qword_180032E80
0x180015ce9  sub     r9d, r8d
0x180015cec  or      r13d, 0FFFFFFFFh
0x180015cf0  mulsd   xmm0, qword ptr [rdx+r9*8]
0x180015cf6  cvttsd2si ebx, xmm0
0x180015cfa  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180015d01  mov     r8d, ebx
0x180015d04  jb      short loc_180015D0B
0x180015d06  test    cx, cx
0x180015d09  jnz     short loc_180015D11
0x180015d0b  mov     r8d, 1
0x180015d11  sub     r8d, 1
0x180015d15  js      short loc_180015D51
0x180015d17  test    r14b, r14b
0x180015d1a  jz      short loc_180015D29
0x180015d1c  mov     eax, [rdi]
0x180015d1e  test    eax, eax
0x180015d20  jnz     short loc_180015D46
0x180015d22  lock cmpxchg [rdi], r13d
0x180015d27  jmp     short loc_180015D42
0x180015d29  mov     edx, [rdi]
0x180015d2b  cmp     edx, r13d
0x180015d2e  jz      short loc_180015D46
0x180015d30  mov     eax, [rdi+4]
0x180015d33  test    eax, eax
0x180015d35  jnz     short loc_180015D46
0x180015d37  lea     ecx, [rdx+1]
0x180015d3a  mov     eax, edx
0x180015d3c  lock cmpxchg [rdi], ecx
0x180015d40  cmp     edx, eax
0x180015d42  mov     al, 1
0x180015d44  jz      short loc_180015D49
0x180015d46  mov     al, r15b
0x180015d49  test    al, al
0x180015d4b  jnz     short loc_180015D9C
0x180015d4d  pause
0x180015d4f  jmp     short loc_180015D11
0x180015d51  mov     ecx, ebp; unsigned int
0x180015d53  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x180015d58  mov     ecx, esi; unsigned int
0x180015d5a  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x180015d5f  movd    xmm0, ebx
0x180015d63  mov     ebp, eax
0x180015d65  cvtdq2pd xmm0, xmm0
0x180015d69  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock@@1NA; double CReaderWriterLock::sm_dblDfltSpinAdjFctr
0x180015d71  cvttsd2si ebx, xmm0
0x180015d75  cmp     ebx, 2710h
0x180015d7b  jle     short loc_180015D84
0x180015d7d  mov     ebx, 2710h
0x180015d82  jmp     short loc_180015D8E
0x180015d84  mov     eax, 64h ; 'd'
0x180015d89  cmp     ebx, eax
0x180015d8b  cmovle  ebx, eax
0x180015d8e  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock@@1GA; ushort CReaderWriterLock::sm_wDefaultSpinCount
0x180015d95  inc     esi
0x180015d97  jmp     loc_180015CFA
0x180015d9c  mov     rbx, [rsp+48h+arg_0]
0x180015da1  mov     rbp, [rsp+48h+arg_10]
0x180015da6  add     rsp, 20h
0x180015daa  pop     r15
0x180015dac  pop     r14
0x180015dae  pop     r13
0x180015db0  pop     rdi
0x180015db1  pop     rsi
0x180015db2  retn
```
