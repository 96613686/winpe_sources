# CReaderWriterLock3::_WriteLockSpin(void)

- ea: `0x180007e60`
- end: `0x180007feb`
- name: `?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ`
- size: `395`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `15`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002fd0`
- `0x180004320`
- `0x180004490`
- `0x180005c80`
- `0x180006730`
- `0x1800080f0`
- `0x180008470`
- `0x180009420`
- `0x18000a820`
- `0x18000b020`
- `0x18000b310`
- `0x18000e280`
- `0x18000eb30`
- `0x180010e80`
- `0x18001b160`

## callees

- `0x180004450`
- `0x180007e60`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f25`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007f60`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180007f60`

## pseudocode

```c
void __fastcall CReaderWriterLock3::_WriteLockSpin(CReaderWriterLock3 *this)
{
  signed __int32 i; // ecx
  DWORD v3; // ebp
  DWORD CurrentThreadId; // eax
  unsigned int v5; // r14d
  unsigned __int16 v6; // dx
  int v7; // edi
  int v8; // esi
  signed __int32 v9; // edx

  for ( i = *(_DWORD *)this;
        i != _InterlockedCompareExchange((volatile signed __int32 *)this, i + 0x10000, i);
        i = *(_DWORD *)this )
  {
    _mm_pause();
  }
  v3 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v5 = 0;
  v6 = CReaderWriterLock3::sm_wDefaultSpinCount;
  v7 = (int)((double)CReaderWriterLock3::sm_wDefaultSpinCount * *(double *)&qword_180032E80[CurrentThreadId % 0xD]);
LABEL_4:
  v8 = v7;
  if ( g_cProcessors < 2 || !v6 )
    v8 = 1;
  while ( 1 )
  {
    if ( --v8 < 0 )
    {
      if ( v3 || !g_pfnSwitchToThread() )
        Sleep(v3);
      if ( v5 < 4 )
        v3 = dword_180032D40[v5];
      else
        v3 = 100;
      v7 = (int)((double)v7 * CReaderWriterLock3::sm_dblDfltSpinAdjFctr);
      if ( v7 <= 10000 )
      {
        if ( v7 <= 100 )
          v7 = 100;
      }
      else
      {
        v7 = 10000;
      }
      v6 = CReaderWriterLock3::sm_wDefaultSpinCount;
      ++v5;
      goto LABEL_4;
    }
    if ( !*((_DWORD *)this + 1) && !(unsigned __int16)*(_DWORD *)this )
    {
      v9 = *(_DWORD *)this;
      if ( v9 == _InterlockedCompareExchange((volatile signed __int32 *)this, v9 | 0xFFFF, v9) )
        break;
    }
    if ( CReaderWriterLock3::_TryWriteLock2(this) )
      return;
    _mm_pause();
  }
  _InterlockedExchange((volatile __int32 *)this + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
}

```

## disassembly

```asm
0x180007e60  push    rbx
0x180007e62  push    rbp
0x180007e63  push    rsi
0x180007e64  push    rdi
0x180007e65  push    r13
0x180007e67  push    r14
0x180007e69  push    r15
0x180007e6b  sub     rsp, 20h
0x180007e6f  mov     rbx, rcx
0x180007e72  mov     ecx, [rcx]
0x180007e74  lea     edx, [rcx+10000h]
0x180007e7a  mov     eax, ecx
0x180007e7c  lock cmpxchg [rbx], edx
0x180007e80  cmp     ecx, eax
0x180007e82  jnz     loc_180007FB8
0x180007e88  xor     r15d, r15d
0x180007e8b  mov     ebp, r15d
0x180007e8e  call    cs:__imp_GetCurrentThreadId
0x180007e95  nop     dword ptr [rax+rax+00h]
0x180007e9a  mov     r14d, r15d
0x180007e9d  lea     r13d, [r15+64h]
0x180007ea1  mov     r8d, eax
0x180007ea4  mov     eax, 4EC4EC4Fh
0x180007ea9  mul     r8d
0x180007eac  shr     edx, 2
0x180007eaf  imul    ecx, edx, 0Dh
0x180007eb2  movzx   edx, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180007eb9  sub     r8d, ecx
0x180007ebc  movd    xmm0, edx
0x180007ec0  mov     ecx, r8d
0x180007ec3  lea     r8, __ImageBase
0x180007eca  cvtdq2pd xmm0, xmm0
0x180007ece  mulsd   xmm0, ds:rva qword_180032E80[r8+rcx*8]
0x180007ed8  cvttsd2si edi, xmm0
0x180007edc  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180007ee3  mov     esi, edi
0x180007ee5  jb      loc_180007FD8
0x180007eeb  test    dx, dx
0x180007eee  jz      loc_180007FD8
0x180007ef4  sub     esi, 1
0x180007ef7  js      short loc_180007F4A
0x180007ef9  mov     eax, [rbx+4]
0x180007efc  test    eax, eax
0x180007efe  jnz     loc_180007FC1
0x180007f04  mov     edx, [rbx]
0x180007f06  test    dx, dx
0x180007f09  jnz     loc_180007FC1
0x180007f0f  mov     ecx, edx
0x180007f11  mov     eax, edx
0x180007f13  or      ecx, 0FFFFh
0x180007f19  lock cmpxchg [rbx], ecx
0x180007f1d  cmp     edx, eax
0x180007f1f  jnz     loc_180007FC1
0x180007f25  call    cs:__imp_GetCurrentThreadId
0x180007f2c  nop     dword ptr [rax+rax+00h]
0x180007f31  and     eax, 0FFFFFFFCh
0x180007f34  or      eax, 1
0x180007f37  xchg    eax, [rbx+4]
0x180007f3a  add     rsp, 20h
0x180007f3e  pop     r15
0x180007f40  pop     r14
0x180007f42  pop     r13
0x180007f44  pop     rdi
0x180007f45  pop     rsi
0x180007f46  pop     rbp
0x180007f47  pop     rbx
0x180007f48  retn
0x180007f4a  test    ebp, ebp
0x180007f4c  jnz     short loc_180007F5E
0x180007f4e  mov     rax, cs:?g_pfnSwitchToThread@@3P6AHXZEA; int (*g_pfnSwitchToThread)(void)
0x180007f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f5a  test    eax, eax
0x180007f5c  jnz     short loc_180007F6C
0x180007f5e  mov     ecx, ebp; dwMilliseconds
0x180007f60  call    cs:__imp_Sleep
0x180007f67  nop     dword ptr [rax+rax+00h]
0x180007f6c  cmp     r14d, 4
0x180007f70  jb      short loc_180007FA5
0x180007f72  mov     ebp, r13d
0x180007f75  movd    xmm0, edi
0x180007f79  cvtdq2pd xmm0, xmm0
0x180007f7d  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock3@@1NA; double CReaderWriterLock3::sm_dblDfltSpinAdjFctr
0x180007f85  cvttsd2si edi, xmm0
0x180007f89  cmp     edi, 2710h
0x180007f8f  jle     short loc_180007FE2
0x180007f91  mov     edi, 2710h
0x180007f96  movzx   edx, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180007f9d  inc     r14d
0x180007fa0  jmp     loc_180007EDC
0x180007fa5  mov     eax, r14d
0x180007fa8  lea     rcx, __ImageBase
0x180007faf  mov     ebp, ds:rva dword_180032D40[rcx+rax*4]
0x180007fb6  jmp     short loc_180007F75
0x180007fb8  pause
0x180007fba  mov     ecx, [rbx]
0x180007fbc  jmp     loc_180007E74
0x180007fc1  mov     rcx, rbx; this
0x180007fc4  call    ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
0x180007fc9  test    al, al
0x180007fcb  jnz     loc_180007F3A
0x180007fd1  pause
0x180007fd3  jmp     loc_180007EF4
0x180007fd8  mov     esi, 1
0x180007fdd  jmp     loc_180007EF4
0x180007fe2  cmp     edi, r13d
0x180007fe5  cmovle  edi, r13d
0x180007fe9  jmp     short loc_180007F96
```
