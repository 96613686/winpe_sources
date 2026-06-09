# CReaderWriterLock2::_LockSpin(bool)

- ea: `0x180019624`
- end: `0x180019713`
- name: `?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z`
- size: `239`
- prototype: `void __fastcall(CReaderWriterLock2 *__hidden this, bool)`
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800015e0`
- `0x180001940`
- `0x180001c00`
- `0x1800026c0`
- `0x1800029d0`
- `0x180002d60`
- `0x180003890`
- `0x180003cf0`
- `0x180003ed0`
- `0x180003f40`

## callees

- `0x1800195d4`
- `0x1800195f4`
- `0x180019624`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001963b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001963b`

## pseudocode

```c
void __fastcall CReaderWriterLock2::_LockSpin(CReaderWriterLock2 *this, char a2)
{
  DWORD v4; // ebp
  unsigned int v5; // esi
  int v6; // ebx
  int v7; // r8d
  signed __int32 v8; // edx
  signed __int32 v9; // ecx
  char v10; // al

  v4 = 0;
  v5 = 0;
  v6 = (int)(*(double *)&qword_1800230D0[GetCurrentThreadId() % 0xD] * 4000.0);
LABEL_2:
  v7 = v6;
  if ( g_cProcessors < 2 )
    v7 = 1;
  do
  {
    if ( --v7 < 0 )
    {
      SwitchOrSleep(v4);
      v4 = SleepTime(v5);
      v6 = (int)((double)v6 * 0.5);
      if ( v6 <= 10000 )
      {
        if ( v6 <= 100 )
          v6 = 100;
      }
      else
      {
        v6 = 10000;
      }
      ++v5;
      goto LABEL_2;
    }
    v8 = *(_DWORD *)this;
    if ( a2 )
    {
      if ( (_WORD)v8 )
        goto LABEL_12;
      v9 = v8 | 0xFFFF;
    }
    else
    {
      if ( (v8 & 0xFFFF8000) != 0 )
        goto LABEL_12;
      v9 = v8 + 1;
    }
    if ( v8 == _InterlockedCompareExchange((volatile signed __int32 *)this, v9, v8) )
    {
      v10 = 1;
      continue;
    }
LABEL_12:
    v10 = 0;
  }
  while ( !v10 );
}

```

## disassembly

```asm
0x180019624  push    rbx
0x180019626  push    rbp
0x180019627  push    rsi
0x180019628  push    rdi
0x180019629  push    r13
0x18001962b  push    r14
0x18001962d  push    r15
0x18001962f  sub     rsp, 20h
0x180019633  mov     r14b, dl
0x180019636  mov     rdi, rcx
0x180019639  xor     ebp, ebp
0x18001963b  call    cs:__imp_GetCurrentThreadId
0x180019641  mov     r9d, eax
0x180019644  lea     rcx, qword_1800230D0
0x18001964b  mov     eax, 4EC4EC4Fh
0x180019650  lea     r15d, [rbp+1]
0x180019654  mul     r9d
0x180019657  lea     r13d, [rbp+64h]
0x18001965b  shr     edx, 2
0x18001965e  imul    r8d, edx, 0Dh
0x180019662  sub     r9d, r8d
0x180019665  xor     esi, esi
0x180019667  movsd   xmm0, qword ptr [rcx+r9*8]
0x18001966d  mulsd   xmm0, cs:__real@40af400000000000
0x180019675  cvttsd2si ebx, xmm0
0x180019679  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180019680  mov     r8d, ebx
0x180019683  cmovb   r8d, r15d
0x180019687  sub     r8d, r15d
0x18001968a  js      short loc_1800196D1
0x18001968c  mov     edx, [rdi]
0x18001968e  test    r14b, r14b
0x180019691  jz      short loc_1800196A2
0x180019693  test    dx, dx
0x180019696  jnz     short loc_1800196BC
0x180019698  mov     ecx, edx
0x18001969a  or      ecx, 0FFFFh
0x1800196a0  jmp     short loc_1800196AD
0x1800196a2  test    edx, 0FFFF8000h
0x1800196a8  jnz     short loc_1800196BC
0x1800196aa  lea     ecx, [rdx+1]
0x1800196ad  mov     eax, edx
0x1800196af  lock cmpxchg [rdi], ecx
0x1800196b3  cmp     edx, eax
0x1800196b5  jnz     short loc_1800196BC
0x1800196b7  mov     al, r15b
0x1800196ba  jmp     short loc_1800196BE
0x1800196bc  xor     al, al
0x1800196be  test    al, al
0x1800196c0  jz      short loc_180019687
0x1800196c2  add     rsp, 20h
0x1800196c6  pop     r15
0x1800196c8  pop     r14
0x1800196ca  pop     r13
0x1800196cc  pop     rdi
0x1800196cd  pop     rsi
0x1800196ce  pop     rbp
0x1800196cf  pop     rbx
0x1800196d0  retn
0x1800196d1  mov     ecx, ebp; dwMilliseconds
0x1800196d3  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x1800196d8  mov     ecx, esi; unsigned int
0x1800196da  call    ?SleepTime@@YAKK@Z; SleepTime(ulong)
0x1800196df  movd    xmm0, ebx
0x1800196e3  mov     ebp, eax
0x1800196e5  cvtdq2pd xmm0, xmm0
0x1800196e9  mulsd   xmm0, cs:__real@3fe0000000000000
0x1800196f1  cvttsd2si ebx, xmm0
0x1800196f5  cmp     ebx, 2710h
0x1800196fb  jle     short loc_180019704
0x1800196fd  mov     ebx, 2710h
0x180019702  jmp     short loc_18001970B
0x180019704  cmp     ebx, r13d
0x180019707  cmovle  ebx, r13d
0x18001970b  add     esi, r15d
0x18001970e  jmp     loc_180019679
```
