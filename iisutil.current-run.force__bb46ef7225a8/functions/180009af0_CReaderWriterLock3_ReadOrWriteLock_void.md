# CReaderWriterLock3::ReadOrWriteLock(void)

- ea: `0x180009af0`
- end: `0x180009cc6`
- name: `?ReadOrWriteLock@CReaderWriterLock3@@QEAA_NXZ`
- size: `470`
- prototype: `bool __fastcall(CReaderWriterLock3 *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180009960`
- `0x180009cd0`
- `0x180009ed0`
- `0x180013d30`
- `0x180014880`

## callees

- `0x1800039d0`
- `0x180007180`
- `0x180009af0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009b00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009b3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009ca0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009b00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009b3e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009ca0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180009c36`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180009c36`

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
      v8 = (int)((double)CReaderWriterLock3::sm_wDefaultSpinCount * *(double *)&qword_180030E80[CurrentThreadId % 0xD]);
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
          v4 = dword_180030D30[v6];
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
0x180009af0  mov     [rsp+arg_18], rbx
0x180009af5  push    rdi
0x180009af6  sub     rsp, 20h
0x180009afa  mov     ebx, [rcx+4]
0x180009afd  mov     rdi, rcx
0x180009b00  call    cs:__imp_GetCurrentThreadId
0x180009b06  xor     eax, ebx
0x180009b08  test    eax, 0FFFFFFFCh
0x180009b0d  jz      loc_180009BD7
0x180009b13  mov     edx, [rdi]
0x180009b15  cmp     dx, 0FFFFh
0x180009b1a  jz      short loc_180009B2D
0x180009b1c  lea     ecx, [rdx+1]
0x180009b1f  mov     eax, edx
0x180009b21  lock cmpxchg [rdi], ecx
0x180009b25  cmp     edx, eax
0x180009b27  jz      loc_180009BD3
0x180009b2d  mov     [rsp+28h+arg_0], rbp
0x180009b32  mov     [rsp+28h+arg_8], rsi
0x180009b37  xor     esi, esi
0x180009b39  mov     [rsp+28h+arg_10], r14
0x180009b3e  call    cs:__imp_GetCurrentThreadId
0x180009b44  mov     r8d, eax
0x180009b47  lea     r14, __ImageBase
0x180009b4e  mov     eax, 4EC4EC4Fh
0x180009b53  mul     r8d
0x180009b56  shr     edx, 2
0x180009b59  imul    ecx, edx, 0Dh
0x180009b5c  sub     r8d, ecx
0x180009b5f  mov     ecx, r8d
0x180009b62  xor     ebp, ebp
0x180009b64  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180009b6c  movd    xmm0, r8d
0x180009b71  cvtdq2pd xmm0, xmm0
0x180009b75  mulsd   xmm0, ds:rva qword_180030E80[r14+rcx*8]
0x180009b7f  cvttsd2si ebx, xmm0
0x180009b83  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x180009b8a  mov     edx, ebx
0x180009b8c  jb      loc_180009CBC
0x180009b92  test    r8w, r8w
0x180009b96  jz      loc_180009CBC
0x180009b9c  sub     edx, 1
0x180009b9f  js      short loc_180009C20
0x180009ba1  mov     r8d, [rdi]
0x180009ba4  cmp     r8w, 0FFFFh
0x180009baa  jz      loc_180009C99
0x180009bb0  lea     ecx, [r8+1]
0x180009bb4  mov     eax, r8d
0x180009bb7  lock cmpxchg [rdi], ecx
0x180009bbb  cmp     r8d, eax
0x180009bbe  jnz     loc_180009C99
0x180009bc4  mov     rsi, [rsp+28h+arg_8]
0x180009bc9  mov     rbp, [rsp+28h+arg_0]
0x180009bce  mov     r14, [rsp+28h+arg_10]
0x180009bd3  mov     al, 1
0x180009bd5  jmp     short loc_180009C15
0x180009bd7  mov     eax, [rdi+4]
0x180009bda  test    eax, eax
0x180009bdc  jnz     short loc_180009BFF
0x180009bde  mov     edx, [rdi]
0x180009be0  test    dx, dx
0x180009be3  jnz     short loc_180009BFF
0x180009be5  lea     ecx, [rdx+10000h]
0x180009beb  mov     eax, edx
0x180009bed  or      ecx, 0FFFFh
0x180009bf3  lock cmpxchg [rdi], ecx
0x180009bf7  cmp     edx, eax
0x180009bf9  jz      loc_180009CA0
0x180009bff  mov     rcx, rdi; this
0x180009c02  call    ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
0x180009c07  test    al, al
0x180009c09  jnz     short loc_180009C13
0x180009c0b  mov     rcx, rdi; this
0x180009c0e  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x180009c13  xor     al, al
0x180009c15  mov     rbx, [rsp+28h+arg_18]
0x180009c1a  add     rsp, 20h
0x180009c1e  pop     rdi
0x180009c1f  retn
0x180009c20  test    esi, esi
0x180009c22  jnz     short loc_180009C34
0x180009c24  mov     rax, cs:?g_pfnSwitchToThread@@3P6AHXZEA; int (*g_pfnSwitchToThread)(void)
0x180009c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c30  test    eax, eax
0x180009c32  jnz     short loc_180009C3C
0x180009c34  mov     ecx, esi; dwMilliseconds
0x180009c36  call    cs:__imp_Sleep
0x180009c3c  cmp     ebp, 4
0x180009c3f  jb      short loc_180009C8F
0x180009c41  mov     esi, 64h ; 'd'
0x180009c46  movd    xmm0, ebx
0x180009c4a  cvtdq2pd xmm0, xmm0
0x180009c4e  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock3@@1NA; double CReaderWriterLock3::sm_dblDfltSpinAdjFctr
0x180009c56  cvttsd2si ebx, xmm0
0x180009c5a  cmp     ebx, 2710h
0x180009c60  jg      short loc_180009C7B
0x180009c62  cmp     ebx, 64h ; 'd'
0x180009c65  jg      short loc_180009C6C
0x180009c67  mov     ebx, 64h ; 'd'
0x180009c6c  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180009c74  inc     ebp
0x180009c76  jmp     loc_180009B83
0x180009c7b  movzx   r8d, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180009c83  mov     ebx, 2710h
0x180009c88  inc     ebp
0x180009c8a  jmp     loc_180009B83
0x180009c8f  mov     esi, ds:rva dword_180030D30[r14+rbp*4]
0x180009c97  jmp     short loc_180009C46
0x180009c99  pause
0x180009c9b  jmp     loc_180009B9C
0x180009ca0  call    cs:__imp_GetCurrentThreadId
0x180009ca6  mov     rbx, [rsp+28h+arg_18]
0x180009cab  and     eax, 0FFFFFFFCh
0x180009cae  or      eax, 1
0x180009cb1  xchg    eax, [rdi+4]
0x180009cb4  xor     al, al
0x180009cb6  add     rsp, 20h
0x180009cba  pop     rdi
0x180009cbb  retn
0x180009cbc  mov     edx, 1
0x180009cc1  jmp     loc_180009B9C
```
