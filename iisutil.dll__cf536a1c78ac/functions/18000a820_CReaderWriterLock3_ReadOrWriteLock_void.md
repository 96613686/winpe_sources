# CReaderWriterLock3::ReadOrWriteLock(void)

- ea: `0x18000a820`
- end: `0x18000aa14`
- name: `?ReadOrWriteLock@CReaderWriterLock3@@QEAA_NXZ`
- size: `500`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a690`
- `0x18000aa20`
- `0x18000ac20`
- `0x180014780`
- `0x180015470`

## callees

- `0x180004450`
- `0x180007e60`
- `0x18000a820`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a830`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a874`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a9e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a830`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a874`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a9e7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000a977`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000a977`

## pseudocode

```c
char __fastcall CReaderWriterLock3::ReadOrWriteLock(CReaderWriterLock3 *this)
{
  int v1; // ebx
  signed __int32 v3; // edx
  DWORD v4; // esi
  DWORD CurrentThreadId; // eax
  __int64 v6; // rbp
  unsigned __int16 v7; // r8
  int v8; // ebx
  int v9; // edx
  signed __int32 v10; // r8d
  signed __int32 v12; // edx

  v1 = *((_DWORD *)this + 1);
  if ( ((v1 ^ GetCurrentThreadId()) & 0xFFFFFFFC) != 0 )
  {
    if ( (unsigned __int16)*(_DWORD *)this == 0xFFFF
      || (v3 = *(_DWORD *)this, v3 != _InterlockedCompareExchange((volatile signed __int32 *)this, v3 + 1, v3)) )
    {
      v4 = 0;
      CurrentThreadId = GetCurrentThreadId();
      v6 = 0;
      v7 = CReaderWriterLock3::sm_wDefaultSpinCount;
      v8 = (int)((double)CReaderWriterLock3::sm_wDefaultSpinCount * *(double *)&qword_180032E80[CurrentThreadId % 0xD]);
      while ( 1 )
      {
        v9 = v8;
        if ( g_cProcessors < 2 || !v7 )
          v9 = 1;
        while ( --v9 >= 0 )
        {
          if ( (unsigned __int16)*(_DWORD *)this != 0xFFFF )
          {
            v10 = *(_DWORD *)this;
            if ( v10 == _InterlockedCompareExchange((volatile signed __int32 *)this, v10 + 1, v10) )
              return 1;
          }
          _mm_pause();
        }
        if ( v4 || !g_pfnSwitchToThread() )
          Sleep(v4);
        if ( (unsigned int)v6 < 4 )
          v4 = dword_180032D40[v6];
        else
          v4 = 100;
        v8 = (int)((double)v8 * CReaderWriterLock3::sm_dblDfltSpinAdjFctr);
        if ( v8 > 10000 )
        {
          v7 = CReaderWriterLock3::sm_wDefaultSpinCount;
          v8 = 10000;
          v6 = (unsigned int)(v6 + 1);
        }
        else
        {
          if ( v8 <= 100 )
            v8 = 100;
          v7 = CReaderWriterLock3::sm_wDefaultSpinCount;
          v6 = (unsigned int)(v6 + 1);
        }
      }
    }
    return 1;
  }
  else if ( *((_DWORD *)this + 1)
         || (unsigned __int16)*(_DWORD *)this
         || (v12 = *(_DWORD *)this,
             v12 != _InterlockedCompareExchange((volatile signed __int32 *)this, (v12 + 0x10000) | 0xFFFF, v12)) )
  {
    if ( !CReaderWriterLock3::_TryWriteLock2(this) )
      CReaderWriterLock3::_WriteLockSpin(this);
    return 0;
  }
  else
  {
    _InterlockedExchange((volatile __int32 *)this + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
    return 0;
  }
}

```

## disassembly

```asm
0x18000a820  mov     [rsp+arg_18], rbx
0x18000a825  push    rdi
0x18000a826  sub     rsp, 20h
0x18000a82a  mov     ebx, [rcx+4]
0x18000a82d  mov     rdi, rcx
0x18000a830  call    cs:__imp_GetCurrentThreadId
0x18000a837  nop     dword ptr [rax+rax+00h]
0x18000a83c  xor     eax, ebx
0x18000a83e  test    eax, 0FFFFFFFCh
0x18000a843  jz      loc_18000A917
0x18000a849  mov     edx, [rdi]
0x18000a84b  cmp     dx, 0FFFFh
0x18000a850  jz      short loc_18000A863
0x18000a852  lea     ecx, [rdx+1]
0x18000a855  mov     eax, edx
0x18000a857  lock cmpxchg [rdi], ecx
0x18000a85b  cmp     edx, eax
0x18000a85d  jz      loc_18000A913
0x18000a863  mov     [rsp+28h+arg_0], rbp
0x18000a868  mov     [rsp+28h+arg_8], rsi
0x18000a86d  xor     esi, esi
0x18000a86f  mov     [rsp+28h+arg_10], r14
0x18000a874  call    cs:__imp_GetCurrentThreadId
0x18000a87b  nop     dword ptr [rax+rax+00h]
0x18000a880  mov     r8d, eax
0x18000a883  lea     r14, __ImageBase
0x18000a88a  mov     eax, 4EC4EC4Fh
0x18000a88f  mul     r8d
0x18000a892  shr     edx, 2
0x18000a895  imul    ecx, edx, 0Dh
0x18000a898  sub     r8d, ecx
0x18000a89b  mov     ecx, r8d
0x18000a89e  xor     ebp, ebp
0x18000a8a0  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x18000a8a8  movd    xmm0, r8d
0x18000a8ad  cvtdq2pd xmm0, xmm0
0x18000a8b1  mulsd   xmm0, ds:rva qword_180032E80[r14+rcx*8]
0x18000a8bb  cvttsd2si ebx, xmm0
0x18000a8bf  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x18000a8c6  mov     edx, ebx
0x18000a8c8  jb      loc_18000AA0A
0x18000a8ce  test    r8w, r8w
0x18000a8d2  jz      loc_18000AA0A
0x18000a8d8  sub     edx, 1
0x18000a8db  js      loc_18000A961
0x18000a8e1  mov     r8d, [rdi]
0x18000a8e4  cmp     r8w, 0FFFFh
0x18000a8ea  jz      loc_18000A9E0
0x18000a8f0  lea     ecx, [r8+1]
0x18000a8f4  mov     eax, r8d
0x18000a8f7  lock cmpxchg [rdi], ecx
0x18000a8fb  cmp     r8d, eax
0x18000a8fe  jnz     loc_18000A9E0
0x18000a904  mov     rsi, [rsp+28h+arg_8]
0x18000a909  mov     rbp, [rsp+28h+arg_0]
0x18000a90e  mov     r14, [rsp+28h+arg_10]
0x18000a913  mov     al, 1
0x18000a915  jmp     short loc_18000A955
0x18000a917  mov     eax, [rdi+4]
0x18000a91a  test    eax, eax
0x18000a91c  jnz     short loc_18000A93F
0x18000a91e  mov     edx, [rdi]
0x18000a920  test    dx, dx
0x18000a923  jnz     short loc_18000A93F
0x18000a925  lea     ecx, [rdx+10000h]
0x18000a92b  mov     eax, edx
0x18000a92d  or      ecx, 0FFFFh
0x18000a933  lock cmpxchg [rdi], ecx
0x18000a937  cmp     edx, eax
0x18000a939  jz      loc_18000A9E7
0x18000a93f  mov     rcx, rdi; this
0x18000a942  call    ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
0x18000a947  test    al, al
0x18000a949  jnz     short loc_18000A953
0x18000a94b  mov     rcx, rdi; this
0x18000a94e  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000a953  xor     al, al
0x18000a955  mov     rbx, [rsp+28h+arg_18]
0x18000a95a  add     rsp, 20h
0x18000a95e  pop     rdi
0x18000a95f  retn
0x18000a961  test    esi, esi
0x18000a963  jnz     short loc_18000A975
0x18000a965  mov     rax, cs:?g_pfnSwitchToThread@@3P6AHXZEA; int (*g_pfnSwitchToThread)(void)
0x18000a96c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a971  test    eax, eax
0x18000a973  jnz     short loc_18000A983
0x18000a975  mov     ecx, esi; dwMilliseconds
0x18000a977  call    cs:__imp_Sleep
0x18000a97e  nop     dword ptr [rax+rax+00h]
0x18000a983  cmp     ebp, 4
0x18000a986  jb      short loc_18000A9D6
0x18000a988  mov     esi, 64h ; 'd'
0x18000a98d  movd    xmm0, ebx
0x18000a991  cvtdq2pd xmm0, xmm0
0x18000a995  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock3@@1NA; double CReaderWriterLock3::sm_dblDfltSpinAdjFctr
0x18000a99d  cvttsd2si ebx, xmm0
0x18000a9a1  cmp     ebx, 2710h
0x18000a9a7  jg      short loc_18000A9C2
0x18000a9a9  cmp     ebx, 64h ; 'd'
0x18000a9ac  jg      short loc_18000A9B3
0x18000a9ae  mov     ebx, 64h ; 'd'
0x18000a9b3  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x18000a9bb  inc     ebp
0x18000a9bd  jmp     loc_18000A8BF
0x18000a9c2  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x18000a9ca  mov     ebx, 2710h
0x18000a9cf  inc     ebp
0x18000a9d1  jmp     loc_18000A8BF
0x18000a9d6  mov     esi, ds:rva dword_180032D40[r14+rbp*4]
0x18000a9de  jmp     short loc_18000A98D
0x18000a9e0  pause
0x18000a9e2  jmp     loc_18000A8D8
0x18000a9e7  call    cs:__imp_GetCurrentThreadId
0x18000a9ee  nop     dword ptr [rax+rax+00h]
0x18000a9f3  mov     rbx, [rsp+28h+arg_18]
0x18000a9f8  and     eax, 0FFFFFFFCh
0x18000a9fb  or      eax, 1
0x18000a9fe  xchg    eax, [rdi+4]
0x18000aa01  xor     al, al
0x18000aa03  add     rsp, 20h
0x18000aa07  pop     rdi
0x18000aa08  retn
0x18000aa0a  mov     edx, 1
0x18000aa0f  jmp     loc_18000A8D8
```
