# CReaderWriterLock2::_ReadLockSpin(void)

- ea: `0x18000a060`
- end: `0x18000a16c`
- name: `?_ReadLockSpin@CReaderWriterLock2@@AEAAXXZ`
- size: `268`
- prototype: `void __fastcall(CReaderWriterLock2 *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180009bd0`
- `0x18000a060`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a078`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a078`

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
  v6 = (int)((double)CReaderWriterLock2::sm_wDefaultSpinCount * *(double *)&qword_180032E80[CurrentThreadId % 0xD]);
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
        v2 = dword_180032D40[v5];
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
0x18000a060  push    rbx
0x18000a062  push    rbp
0x18000a063  push    rsi
0x18000a064  push    rdi
0x18000a065  push    r12
0x18000a067  push    r13
0x18000a069  push    r14
0x18000a06b  sub     rsp, 20h
0x18000a06f  xor     r12d, r12d
0x18000a072  mov     r14, rcx
0x18000a075  mov     esi, r12d
0x18000a078  call    cs:__imp_GetCurrentThreadId
0x18000a07f  nop     dword ptr [rax+rax+00h]
0x18000a084  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x18000a08b  lea     r13, __ImageBase
0x18000a092  mov     r9d, eax
0x18000a095  lea     ebp, [r12+64h]
0x18000a09a  mov     eax, 4EC4EC4Fh
0x18000a09f  mov     edi, r12d
0x18000a0a2  mul     r9d
0x18000a0a5  movd    xmm0, ecx
0x18000a0a9  cvtdq2pd xmm0, xmm0
0x18000a0ad  shr     edx, 2
0x18000a0b0  imul    r8d, edx, 0Dh
0x18000a0b4  sub     r9d, r8d
0x18000a0b7  mulsd   xmm0, ds:rva qword_180032E80[r13+r9*8]
0x18000a0c1  cvttsd2si ebx, xmm0
0x18000a0c5  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x18000a0cc  mov     r8d, ebx
0x18000a0cf  jb      loc_18000A161
0x18000a0d5  test    cx, cx
0x18000a0d8  jz      loc_18000A161
0x18000a0de  sub     r8d, 1
0x18000a0e2  js      short loc_18000A10D
0x18000a0e4  mov     edx, [r14]
0x18000a0e7  test    edx, 0FFFF8000h
0x18000a0ed  jnz     short loc_18000A14A
0x18000a0ef  lea     ecx, [rdx+1]
0x18000a0f2  mov     eax, edx
0x18000a0f4  lock cmpxchg [r14], ecx
0x18000a0f9  cmp     edx, eax
0x18000a0fb  jnz     short loc_18000A14A
0x18000a0fd  add     rsp, 20h
0x18000a101  pop     r14
0x18000a103  pop     r13
0x18000a105  pop     r12
0x18000a107  pop     rdi
0x18000a108  pop     rsi
0x18000a109  pop     rbp
0x18000a10a  pop     rbx
0x18000a10b  retn
0x18000a10d  mov     ecx, esi; unsigned int
0x18000a10f  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x18000a114  cmp     edi, 4
0x18000a117  jb      short loc_18000A14E
0x18000a119  mov     esi, ebp
0x18000a11b  movd    xmm0, ebx
0x18000a11f  cvtdq2pd xmm0, xmm0
0x18000a123  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock2@@1NA; double CReaderWriterLock2::sm_dblDfltSpinAdjFctr
0x18000a12b  cvttsd2si ebx, xmm0
0x18000a12f  cmp     ebx, 2710h
0x18000a135  jg      short loc_18000A15A
0x18000a137  cmp     ebx, ebp
0x18000a139  cmovle  ebx, ebp
0x18000a13c  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x18000a143  inc     edi
0x18000a145  jmp     loc_18000A0C5
0x18000a14a  pause
0x18000a14c  jmp     short loc_18000A0DE
0x18000a14e  mov     eax, edi
0x18000a150  mov     esi, ds:rva dword_180032D40[r13+rax*4]
0x18000a158  jmp     short loc_18000A11B
0x18000a15a  mov     ebx, 2710h
0x18000a15f  jmp     short loc_18000A13C
0x18000a161  mov     r8d, 1
0x18000a167  jmp     loc_18000A0DE
```
