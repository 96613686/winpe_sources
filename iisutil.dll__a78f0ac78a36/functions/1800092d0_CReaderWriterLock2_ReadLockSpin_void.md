# CReaderWriterLock2::_ReadLockSpin(void)

- ea: `0x1800092d0`
- end: `0x1800093ce`
- name: `?_ReadLockSpin@CReaderWriterLock2@@AEAAXXZ`
- size: `254`
- prototype: `void __fastcall(CReaderWriterLock2 *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008e70`
- `0x1800092d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800092e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800092e8`

## pseudocode

```c
void __fastcall CReaderWriterLock2::_ReadLockSpin(CReaderWriterLock2 *this)
{
  unsigned int v2; // esi
  DWORD CurrentThreadId; // eax
  unsigned __int16 v4; // cx
  unsigned int v5; // edi
  int v6; // ebx
  int v7; // r8d
  signed __int32 v8; // edx

  v2 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v4 = CReaderWriterLock2::sm_wDefaultSpinCount;
  v5 = 0;
  v6 = (int)((double)CReaderWriterLock2::sm_wDefaultSpinCount * *(double *)&qword_180030E80[CurrentThreadId % 0xD]);
LABEL_2:
  v7 = v6;
  if ( g_cProcessors < 2 || !v4 )
    v7 = 1;
  while ( 1 )
  {
    if ( --v7 < 0 )
    {
      SwitchOrSleep(v2);
      if ( v5 < 4 )
        v2 = dword_180030D30[v5];
      else
        v2 = 100;
      v6 = (int)((double)v6 * CReaderWriterLock2::sm_dblDfltSpinAdjFctr);
      if ( v6 > 10000 )
      {
        v6 = 10000;
      }
      else if ( v6 <= 100 )
      {
        v6 = 100;
      }
      v4 = CReaderWriterLock2::sm_wDefaultSpinCount;
      ++v5;
      goto LABEL_2;
    }
    if ( (*(_DWORD *)this & 0xFFFF8000) == 0 )
    {
      v8 = *(_DWORD *)this;
      if ( v8 == _InterlockedCompareExchange((volatile signed __int32 *)this, v8 + 1, v8) )
        break;
    }
    _mm_pause();
  }
}

```

## disassembly

```asm
0x1800092d0  push    rbx
0x1800092d2  push    rbp
0x1800092d3  push    rsi
0x1800092d4  push    rdi
0x1800092d5  push    r12
0x1800092d7  push    r13
0x1800092d9  push    r14
0x1800092db  sub     rsp, 20h
0x1800092df  xor     r12d, r12d
0x1800092e2  mov     r14, rcx
0x1800092e5  mov     esi, r12d
0x1800092e8  call    cs:__imp_GetCurrentThreadId
0x1800092ee  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x1800092f5  lea     r13, __ImageBase
0x1800092fc  mov     r9d, eax
0x1800092ff  lea     ebp, [r12+64h]
0x180009304  mov     eax, 4EC4EC4Fh
0x180009309  mov     edi, r12d
0x18000930c  mul     r9d
0x18000930f  movd    xmm0, ecx
0x180009313  cvtdq2pd xmm0, xmm0
0x180009317  shr     edx, 2
0x18000931a  imul    r8d, edx, 0Dh
0x18000931e  sub     r9d, r8d
0x180009321  mulsd   xmm0, ds:rva qword_180030E80[r13+r9*8]
0x18000932b  cvttsd2si ebx, xmm0
0x18000932f  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180009336  mov     r8d, ebx
0x180009339  jb      loc_1800093C3
0x18000933f  test    cx, cx
0x180009342  jz      short loc_1800093C3
0x180009344  sub     r8d, 1
0x180009348  js      short loc_180009372
0x18000934a  mov     edx, [r14]
0x18000934d  test    edx, 0FFFF8000h
0x180009353  jnz     short loc_1800093AC
0x180009355  lea     ecx, [rdx+1]
0x180009358  mov     eax, edx
0x18000935a  lock cmpxchg [r14], ecx
0x18000935f  cmp     edx, eax
0x180009361  jnz     short loc_1800093AC
0x180009363  add     rsp, 20h
0x180009367  pop     r14
0x180009369  pop     r13
0x18000936b  pop     r12
0x18000936d  pop     rdi
0x18000936e  pop     rsi
0x18000936f  pop     rbp
0x180009370  pop     rbx
0x180009371  retn
0x180009372  mov     ecx, esi; unsigned int
0x180009374  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x180009379  cmp     edi, 4
0x18000937c  jb      short loc_1800093B0
0x18000937e  mov     esi, ebp
0x180009380  movd    xmm0, ebx
0x180009384  cvtdq2pd xmm0, xmm0
0x180009388  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock2@@1NA; double CReaderWriterLock2::sm_dblDfltSpinAdjFctr
0x180009390  cvttsd2si ebx, xmm0
0x180009394  cmp     ebx, 2710h
0x18000939a  jg      short loc_1800093BC
0x18000939c  cmp     ebx, ebp
0x18000939e  cmovle  ebx, ebp
0x1800093a1  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x1800093a8  inc     edi
0x1800093aa  jmp     short loc_18000932F
0x1800093ac  pause
0x1800093ae  jmp     short loc_180009344
0x1800093b0  mov     eax, edi
0x1800093b2  mov     esi, ds:rva dword_180030D30[r13+rax*4]
0x1800093ba  jmp     short loc_180009380
0x1800093bc  mov     ebx, 2710h
0x1800093c1  jmp     short loc_1800093A1
0x1800093c3  mov     r8d, 1
0x1800093c9  jmp     loc_180009344
```
