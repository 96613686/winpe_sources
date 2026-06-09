# CReaderWriterLock3::ReadLock(void)

- ea: `0x180005aa0`
- end: `0x180005c17`
- name: `?ReadLock@CReaderWriterLock3@@QEAAXXZ`
- size: `375`
- prototype: `void __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004490`
- `0x180004d50`
- `0x180005520`
- `0x180005f60`
- `0x180006730`
- `0x18000bdd0`
- `0x180011210`
- `0x180013410`
- `0x180016620`
- `0x18001ad60`
- `0x18002a430`
- `0x18002aad0`
- `0x18002af70`
- `0x18002dcd0`
- `0x18002ddc0`

## callees

- `0x180005aa0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005adf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005adf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005b9d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180005b9d`

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
    v7 = (int)((double)CReaderWriterLock3::sm_wDefaultSpinCount * *(double *)&qword_180032E80[CurrentThreadId % 0xD]);
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
        v3 = dword_180032D40[v5];
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
0x180005aa0  push    rbx
0x180005aa2  sub     rsp, 20h
0x180005aa6  mov     r8d, [rcx]
0x180005aa9  mov     rbx, rcx
0x180005aac  test    r8d, 0FFFF8000h
0x180005ab3  jnz     short loc_180005AC9
0x180005ab5  lea     edx, [r8+1]
0x180005ab9  mov     eax, r8d
0x180005abc  lock cmpxchg [rcx], edx
0x180005ac0  cmp     r8d, eax
0x180005ac3  jz      loc_180005B80
0x180005ac9  mov     [rsp+28h+arg_0], rbp
0x180005ace  mov     [rsp+28h+arg_8], rsi
0x180005ad3  xor     esi, esi
0x180005ad5  mov     [rsp+28h+arg_10], rdi
0x180005ada  mov     [rsp+28h+arg_18], r14
0x180005adf  call    cs:__imp_GetCurrentThreadId
0x180005ae6  nop     dword ptr [rax+rax+00h]
0x180005aeb  mov     r8d, eax
0x180005aee  lea     r14, __ImageBase
0x180005af5  mov     eax, 4EC4EC4Fh
0x180005afa  mul     r8d
0x180005afd  shr     edx, 2
0x180005b00  imul    ecx, edx, 0Dh
0x180005b03  sub     r8d, ecx
0x180005b06  mov     ecx, r8d
0x180005b09  xor     ebp, ebp
0x180005b0b  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180005b13  movd    xmm0, r8d
0x180005b18  cvtdq2pd xmm0, xmm0
0x180005b1c  mulsd   xmm0, ds:rva qword_180032E80[r14+rcx*8]
0x180005b26  cvttsd2si edi, xmm0
0x180005b2a  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180005b31  mov     edx, edi
0x180005b33  jb      loc_180005C0D
0x180005b39  test    r8w, r8w
0x180005b3d  jz      loc_180005C0D
0x180005b43  sub     edx, 1
0x180005b46  js      short loc_180005B87
0x180005b48  mov     r8d, [rbx]
0x180005b4b  test    r8d, 0FFFF8000h
0x180005b52  jnz     loc_180005C06
0x180005b58  lea     ecx, [r8+1]
0x180005b5c  mov     eax, r8d
0x180005b5f  lock cmpxchg [rbx], ecx
0x180005b63  cmp     r8d, eax
0x180005b66  jnz     loc_180005C06
0x180005b6c  mov     rdi, [rsp+28h+arg_10]
0x180005b71  mov     rsi, [rsp+28h+arg_8]
0x180005b76  mov     rbp, [rsp+28h+arg_0]
0x180005b7b  mov     r14, [rsp+28h+arg_18]
0x180005b80  add     rsp, 20h
0x180005b84  pop     rbx
0x180005b85  retn
0x180005b87  test    esi, esi
0x180005b89  jnz     short loc_180005B9B
0x180005b8b  mov     rax, cs:?g_pfnSwitchToThread@@3P6AHXZEA; int (*g_pfnSwitchToThread)(void)
0x180005b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b97  test    eax, eax
0x180005b99  jnz     short loc_180005BA9
0x180005b9b  mov     ecx, esi; dwMilliseconds
0x180005b9d  call    cs:__imp_Sleep
0x180005ba4  nop     dword ptr [rax+rax+00h]
0x180005ba9  cmp     ebp, 4
0x180005bac  jb      short loc_180005BFC
0x180005bae  mov     esi, 64h ; 'd'
0x180005bb3  movd    xmm0, edi
0x180005bb7  cvtdq2pd xmm0, xmm0
0x180005bbb  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock3@@1NA; double CReaderWriterLock3::sm_dblDfltSpinAdjFctr
0x180005bc3  cvttsd2si edi, xmm0
0x180005bc7  cmp     edi, 2710h
0x180005bcd  jg      short loc_180005BE8
0x180005bcf  cmp     edi, 64h ; 'd'
0x180005bd2  jg      short loc_180005BD9
0x180005bd4  mov     edi, 64h ; 'd'
0x180005bd9  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180005be1  inc     ebp
0x180005be3  jmp     loc_180005B2A
0x180005be8  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180005bf0  mov     edi, 2710h
0x180005bf5  inc     ebp
0x180005bf7  jmp     loc_180005B2A
0x180005bfc  mov     esi, ds:rva dword_180032D40[r14+rbp*4]
0x180005c04  jmp     short loc_180005BB3
0x180005c06  pause
0x180005c08  jmp     loc_180005B43
0x180005c0d  mov     edx, 1
0x180005c12  jmp     loc_180005B43
```
