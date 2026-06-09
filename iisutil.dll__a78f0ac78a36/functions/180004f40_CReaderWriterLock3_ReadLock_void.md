# CReaderWriterLock3::ReadLock(void)

- ea: `0x180004f40`
- end: `0x1800050aa`
- name: `?ReadLock@CReaderWriterLock3@@QEAAXXZ`
- size: `362`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003a10`
- `0x180004250`
- `0x1800049c0`
- `0x1800053d0`
- `0x180005b40`
- `0x18000a990`
- `0x180010080`
- `0x180012810`
- `0x180015990`
- `0x180019ea0`
- `0x180028630`
- `0x180028ca0`
- `0x180029130`
- `0x18002bcc0`
- `0x18002bda0`

## callees

- `0x180004f40`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f7f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005036`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005036`

## pseudocode

```c
void __fastcall CReaderWriterLock3::ReadLock(CReaderWriterLock3 *this)
{
  signed __int32 v1; // r8d
  DWORD v3; // esi
  DWORD CurrentThreadId; // eax
  __int64 v5; // rbp
  unsigned __int16 v6; // r8
  int v7; // edi
  int v8; // edx
  signed __int32 v9; // r8d

  if ( (*(_DWORD *)this & 0xFFFF8000) != 0
    || (v1 = *(_DWORD *)this, v1 != _InterlockedCompareExchange((volatile signed __int32 *)this, v1 + 1, v1)) )
  {
    v3 = 0;
    CurrentThreadId = GetCurrentThreadId();
    v5 = 0;
    v6 = CReaderWriterLock3::sm_wDefaultSpinCount;
    v7 = (int)((double)CReaderWriterLock3::sm_wDefaultSpinCount * *(double *)&qword_180030E80[CurrentThreadId % 0xD]);
    while ( 1 )
    {
      v8 = v7;
      if ( g_cProcessors < 2 || !v6 )
        v8 = 1;
      while ( --v8 >= 0 )
      {
        if ( (*(_DWORD *)this & 0xFFFF8000) == 0 )
        {
          v9 = *(_DWORD *)this;
          if ( v9 == _InterlockedCompareExchange((volatile signed __int32 *)this, v9 + 1, v9) )
            return;
        }
        _mm_pause();
      }
      if ( v3 || !g_pfnSwitchToThread() )
        Sleep(v3);
      if ( (unsigned int)v5 < 4 )
        v3 = dword_180030D30[v5];
      else
        v3 = 100;
      v7 = (int)((double)v7 * CReaderWriterLock3::sm_dblDfltSpinAdjFctr);
      if ( v7 > 10000 )
      {
        v6 = CReaderWriterLock3::sm_wDefaultSpinCount;
        v7 = 10000;
        v5 = (unsigned int)(v5 + 1);
      }
      else
      {
        if ( v7 <= 100 )
          v7 = 100;
        v6 = CReaderWriterLock3::sm_wDefaultSpinCount;
        v5 = (unsigned int)(v5 + 1);
      }
    }
  }
}

```

## disassembly

```asm
0x180004f40  push    rbx
0x180004f42  sub     rsp, 20h
0x180004f46  mov     r8d, [rcx]
0x180004f49  mov     rbx, rcx
0x180004f4c  test    r8d, 0FFFF8000h
0x180004f53  jnz     short loc_180004F69
0x180004f55  lea     edx, [r8+1]
0x180004f59  mov     eax, r8d
0x180004f5c  lock cmpxchg [rcx], edx
0x180004f60  cmp     r8d, eax
0x180004f63  jz      loc_18000501A
0x180004f69  mov     [rsp+28h+arg_0], rbp
0x180004f6e  mov     [rsp+28h+arg_8], rsi
0x180004f73  xor     esi, esi
0x180004f75  mov     [rsp+28h+arg_10], rdi
0x180004f7a  mov     [rsp+28h+arg_18], r14
0x180004f7f  call    cs:__imp_GetCurrentThreadId
0x180004f85  mov     r8d, eax
0x180004f88  lea     r14, __ImageBase
0x180004f8f  mov     eax, 4EC4EC4Fh
0x180004f94  mul     r8d
0x180004f97  shr     edx, 2
0x180004f9a  imul    ecx, edx, 0Dh
0x180004f9d  sub     r8d, ecx
0x180004fa0  mov     ecx, r8d
0x180004fa3  xor     ebp, ebp
0x180004fa5  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180004fad  movd    xmm0, r8d
0x180004fb2  cvtdq2pd xmm0, xmm0
0x180004fb6  mulsd   xmm0, ds:rva qword_180030E80[r14+rcx*8]
0x180004fc0  cvttsd2si edi, xmm0
0x180004fc4  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180004fcb  mov     edx, edi
0x180004fcd  jb      loc_1800050A0
0x180004fd3  test    r8w, r8w
0x180004fd7  jz      loc_1800050A0
0x180004fdd  sub     edx, 1
0x180004fe0  js      short loc_180005020
0x180004fe2  mov     r8d, [rbx]
0x180004fe5  test    r8d, 0FFFF8000h
0x180004fec  jnz     loc_180005099
0x180004ff2  lea     ecx, [r8+1]
0x180004ff6  mov     eax, r8d
0x180004ff9  lock cmpxchg [rbx], ecx
0x180004ffd  cmp     r8d, eax
0x180005000  jnz     loc_180005099
0x180005006  mov     rdi, [rsp+28h+arg_10]
0x18000500b  mov     rsi, [rsp+28h+arg_8]
0x180005010  mov     rbp, [rsp+28h+arg_0]
0x180005015  mov     r14, [rsp+28h+arg_18]
0x18000501a  add     rsp, 20h
0x18000501e  pop     rbx
0x18000501f  retn
0x180005020  test    esi, esi
0x180005022  jnz     short loc_180005034
0x180005024  mov     rax, cs:?g_pfnSwitchToThread@@3P6AHXZEA; int (*g_pfnSwitchToThread)(void)
0x18000502b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005030  test    eax, eax
0x180005032  jnz     short loc_18000503C
0x180005034  mov     ecx, esi; dwMilliseconds
0x180005036  call    cs:__imp_Sleep
0x18000503c  cmp     ebp, 4
0x18000503f  jb      short loc_18000508F
0x180005041  mov     esi, 64h ; 'd'
0x180005046  movd    xmm0, edi
0x18000504a  cvtdq2pd xmm0, xmm0
0x18000504e  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock3@@1NA; double CReaderWriterLock3::sm_dblDfltSpinAdjFctr
0x180005056  cvttsd2si edi, xmm0
0x18000505a  cmp     edi, 2710h
0x180005060  jg      short loc_18000507B
0x180005062  cmp     edi, 64h ; 'd'
0x180005065  jg      short loc_18000506C
0x180005067  mov     edi, 64h ; 'd'
0x18000506c  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180005074  inc     ebp
0x180005076  jmp     loc_180004FC4
0x18000507b  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180005083  mov     edi, 2710h
0x180005088  inc     ebp
0x18000508a  jmp     loc_180004FC4
0x18000508f  mov     esi, ds:rva dword_180030D30[r14+rbp*4]
0x180005097  jmp     short loc_180005046
0x180005099  pause
0x18000509b  jmp     loc_180004FDD
0x1800050a0  mov     edx, 1
0x1800050a5  jmp     loc_180004FDD
```
