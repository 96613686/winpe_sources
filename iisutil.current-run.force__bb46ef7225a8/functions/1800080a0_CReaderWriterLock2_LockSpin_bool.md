# CReaderWriterLock2::_LockSpin(bool)

- ea: `0x1800080a0`
- end: `0x1800081cb`
- name: `?_LockSpin@CReaderWriterLock2@@AEAAX_N@Z`
- size: `299`
- prototype: `void __fastcall(CReaderWriterLock2 *__hidden this, bool)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800073e0`
- `0x180007750`
- `0x180008980`
- `0x180008f40`
- `0x1800093e0`
- `0x1800098c0`
- `0x18000a110`
- `0x18000a8f0`
- `0x18000a9d0`
- `0x18000d1a0`
- `0x180015550`

## callees

- `0x1800080a0`
- `0x180008e70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080bb`

## pseudocode

```c
void __fastcall CReaderWriterLock2::_LockSpin(CReaderWriterLock2 *this, char a2)
{
  unsigned int v3; // ebp
  DWORD CurrentThreadId; // eax
  unsigned __int16 v6; // cx
  unsigned int v7; // esi
  int v8; // ebx
  int v9; // r8d
  signed __int32 v10; // edx
  signed __int32 v11; // ecx
  char v12; // al

  v3 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v6 = CReaderWriterLock2::sm_wDefaultSpinCount;
  v7 = 0;
  v8 = (int)((double)CReaderWriterLock2::sm_wDefaultSpinCount * *(double *)&qword_180030E80[CurrentThreadId % 0xD]);
LABEL_2:
  v9 = v8;
  if ( g_cProcessors < 2 || !v6 )
    v9 = 1;
  while ( 1 )
  {
    if ( --v9 < 0 )
    {
      SwitchOrSleep(v3);
      if ( v7 < 4 )
        v3 = dword_180030D30[v7];
      else
        v3 = 100;
      v8 = (int)((double)v8 * CReaderWriterLock2::sm_dblDfltSpinAdjFctr);
      if ( v8 > 10000 )
      {
        v8 = 10000;
      }
      else if ( v8 <= 100 )
      {
        v8 = 100;
      }
      v6 = CReaderWriterLock2::sm_wDefaultSpinCount;
      ++v7;
      goto LABEL_2;
    }
    v10 = *(_DWORD *)this;
    if ( a2 )
    {
      if ( !(_WORD)v10 )
      {
        v11 = v10 | 0xFFFF;
LABEL_8:
        v12 = 1;
        if ( v10 == _InterlockedCompareExchange((volatile signed __int32 *)this, v11, v10) )
          goto LABEL_10;
      }
    }
    else if ( (v10 & 0xFFFF8000) == 0 )
    {
      v11 = v10 + 1;
      goto LABEL_8;
    }
    v12 = 0;
LABEL_10:
    if ( v12 )
      break;
    _mm_pause();
  }
}

```

## disassembly

```asm
0x1800080a0  push    rbx
0x1800080a2  push    rbp
0x1800080a3  push    rsi
0x1800080a4  push    rdi
0x1800080a5  push    r12
0x1800080a7  push    r14
0x1800080a9  push    r15
0x1800080ab  sub     rsp, 20h
0x1800080af  xor     r15d, r15d
0x1800080b2  mov     r14b, dl
0x1800080b5  mov     ebp, r15d
0x1800080b8  mov     rdi, rcx
0x1800080bb  call    cs:__imp_GetCurrentThreadId
0x1800080c1  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x1800080c8  lea     r12d, [r15+64h]
0x1800080cc  mov     r9d, eax
0x1800080cf  mov     esi, r15d
0x1800080d2  mov     eax, 4EC4EC4Fh
0x1800080d7  mul     r9d
0x1800080da  movd    xmm0, ecx
0x1800080de  cvtdq2pd xmm0, xmm0
0x1800080e2  shr     edx, 2
0x1800080e5  imul    r8d, edx, 0Dh
0x1800080e9  lea     rdx, __ImageBase
0x1800080f0  sub     r9d, r8d
0x1800080f3  mulsd   xmm0, ds:rva qword_180030E80[rdx+r9*8]
0x1800080fd  cvttsd2si ebx, xmm0
0x180008101  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180008108  mov     r8d, ebx
0x18000810b  jb      loc_1800081C0
0x180008111  test    cx, cx
0x180008114  jz      loc_1800081C0
0x18000811a  sub     r8d, 1
0x18000811e  js      short loc_180008149
0x180008120  mov     edx, [rdi]
0x180008122  test    r14b, r14b
0x180008125  jnz     short loc_180008189
0x180008127  test    edx, 0FFFF8000h
0x18000812d  jnz     short loc_18000813E
0x18000812f  lea     ecx, [rdx+1]
0x180008132  mov     eax, edx
0x180008134  lock cmpxchg [rdi], ecx
0x180008138  cmp     edx, eax
0x18000813a  mov     al, 1
0x18000813c  jz      short loc_180008141
0x18000813e  mov     al, r15b
0x180008141  test    al, al
0x180008143  jnz     short loc_180008198
0x180008145  pause
0x180008147  jmp     short loc_18000811A
0x180008149  mov     ecx, ebp; unsigned int
0x18000814b  call    ?SwitchOrSleep@@YAXK@Z; SwitchOrSleep(ulong)
0x180008150  cmp     esi, 4
0x180008153  jb      short loc_1800081A7
0x180008155  mov     ebp, r12d
0x180008158  movd    xmm0, ebx
0x18000815c  cvtdq2pd xmm0, xmm0
0x180008160  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock2@@1NA; double CReaderWriterLock2::sm_dblDfltSpinAdjFctr
0x180008168  cvttsd2si ebx, xmm0
0x18000816c  cmp     ebx, 2710h
0x180008172  jg      short loc_1800081B9
0x180008174  cmp     ebx, r12d
0x180008177  cmovle  ebx, r12d
0x18000817b  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock2@@1GA; ushort CReaderWriterLock2::sm_wDefaultSpinCount
0x180008182  inc     esi
0x180008184  jmp     loc_180008101
0x180008189  test    dx, dx
0x18000818c  jnz     short loc_18000813E
0x18000818e  mov     ecx, edx
0x180008190  or      ecx, 0FFFFh
0x180008196  jmp     short loc_180008132
0x180008198  add     rsp, 20h
0x18000819c  pop     r15
0x18000819e  pop     r14
0x1800081a0  pop     r12
0x1800081a2  pop     rdi
0x1800081a3  pop     rsi
0x1800081a4  pop     rbp
0x1800081a5  pop     rbx
0x1800081a6  retn
0x1800081a7  mov     eax, esi
0x1800081a9  lea     rcx, __ImageBase
0x1800081b0  mov     ebp, ds:rva dword_180030D30[rcx+rax*4]
0x1800081b7  jmp     short loc_180008158
0x1800081b9  mov     ebx, 2710h
0x1800081be  jmp     short loc_18000817B
0x1800081c0  mov     r8d, 1
0x1800081c6  jmp     loc_18000811A
```
