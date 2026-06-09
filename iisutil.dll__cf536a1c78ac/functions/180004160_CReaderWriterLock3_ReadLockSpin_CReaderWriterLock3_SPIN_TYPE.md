# CReaderWriterLock3::_ReadLockSpin(CReaderWriterLock3::SPIN_TYPE)

- ea: `0x180004160`
- end: `0x18000430c`
- name: `?_ReadLockSpin@CReaderWriterLock3@@AEAAXW4SPIN_TYPE@1@@Z`
- size: `428`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180004160`
- `0x180004450`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004177`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800042e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004177`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800042e9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000421d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000421d`

## pseudocode

```c
bool __fastcall CReaderWriterLock3::_ReadLockSpin(volatile __int32 *a1, int a2)
{
  DWORD v4; // ebp
  DWORD CurrentThreadId; // eax
  unsigned __int16 v6; // cx
  __int64 v7; // r14
  int v8; // edi
  int v9; // ebx
  signed __int32 v10; // edx
  bool result; // al
  signed __int32 v12; // edx

  v4 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v6 = CReaderWriterLock3::sm_wDefaultSpinCount;
  v7 = 0;
  v8 = (int)((double)CReaderWriterLock3::sm_wDefaultSpinCount * *(double *)&qword_180032E80[CurrentThreadId % 0xD]);
LABEL_2:
  v9 = v8;
  if ( g_cProcessors < 2 || !v6 )
    v9 = 1;
  while ( 1 )
  {
    if ( --v9 < 0 )
    {
      if ( v4 || !g_pfnSwitchToThread() )
        Sleep(v4);
      if ( (unsigned int)v7 < 4 )
        v4 = dword_180032D40[v7];
      else
        v4 = 100;
      v8 = (int)((double)v8 * CReaderWriterLock3::sm_dblDfltSpinAdjFctr);
      if ( v8 > 10000 )
      {
        v6 = CReaderWriterLock3::sm_wDefaultSpinCount;
        v8 = 10000;
        v7 = (unsigned int)(v7 + 1);
      }
      else
      {
        if ( v8 <= 100 )
          v8 = 100;
        v6 = CReaderWriterLock3::sm_wDefaultSpinCount;
        v7 = (unsigned int)(v7 + 1);
      }
      goto LABEL_2;
    }
    if ( a2 == 1 )
    {
      if ( *((_DWORD *)a1 + 1)
        || (unsigned __int16)*a1
        || (v12 = *a1, v12 != _InterlockedCompareExchange(a1, v12 | 0xFFFF, v12)) )
      {
        result = CReaderWriterLock3::_TryWriteLock2((CReaderWriterLock3 *)a1);
      }
      else
      {
        _InterlockedExchange(a1 + 1, GetCurrentThreadId() & 0xFFFFFFFC | 1);
        result = 1;
      }
    }
    else
    {
      v10 = *a1;
      if ( a2 == 2 )
      {
        if ( (v10 & 0xFFFF8000) != 0 || v10 != _InterlockedCompareExchange(a1, v10 + 1, v10) )
          goto LABEL_9;
      }
      else if ( (_WORD)v10 == 0xFFFF || v10 != _InterlockedCompareExchange(a1, v10 + 1, v10) )
      {
LABEL_9:
        result = 0;
        goto LABEL_22;
      }
      result = 1;
    }
LABEL_22:
    if ( result )
      return result;
    _mm_pause();
  }
}

```

## disassembly

```asm
0x180004160  push    rbx; private: void CReaderWriterLock3::_LockSpin(enum CReaderWriterLock3::SPIN_TYPE)
0x180004162  push    rbp
0x180004163  push    rsi
0x180004164  push    rdi
0x180004165  push    r12
0x180004167  push    r14
0x180004169  push    r15
0x18000416b  sub     rsp, 20h
0x18000416f  mov     r15d, edx
0x180004172  mov     rsi, rcx
0x180004175  xor     ebp, ebp
0x180004177  call    cs:__imp_GetCurrentThreadId
0x18000417e  nop     dword ptr [rax+rax+00h]
0x180004183  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x18000418a  lea     r12, __ImageBase
0x180004191  mov     r9d, eax
0x180004194  mov     eax, 4EC4EC4Fh
0x180004199  mul     r9d
0x18000419c  movd    xmm0, ecx
0x1800041a0  cvtdq2pd xmm0, xmm0
0x1800041a4  shr     edx, 2
0x1800041a7  imul    r8d, edx, 0Dh
0x1800041ab  sub     r9d, r8d
0x1800041ae  xor     r14d, r14d
0x1800041b1  mulsd   xmm0, ds:rva qword_180032E80[r12+r9*8]
0x1800041bb  cvttsd2si edi, xmm0
0x1800041bf  cmp     cs:?g_cProcessors@@3KA, 2; ulong g_cProcessors
0x1800041c6  mov     ebx, edi
0x1800041c8  jb      loc_180004302
0x1800041ce  test    cx, cx
0x1800041d1  jz      loc_180004302
0x1800041d7  sub     ebx, 1
0x1800041da  js      short loc_180004207
0x1800041dc  cmp     r15d, 1
0x1800041e0  jz      loc_18000428E
0x1800041e6  mov     edx, [rsi]
0x1800041e8  cmp     r15d, 2
0x1800041ec  jnz     short loc_18000426D
0x1800041ee  test    edx, 0FFFF8000h
0x1800041f4  jnz     short loc_180004203
0x1800041f6  lea     ecx, [rdx+1]
0x1800041f9  mov     eax, edx
0x1800041fb  lock cmpxchg [rsi], ecx
0x1800041ff  cmp     edx, eax
0x180004201  jz      short loc_180004281
0x180004203  xor     al, al
0x180004205  jmp     short loc_180004283
0x180004207  test    ebp, ebp
0x180004209  jnz     short loc_18000421B
0x18000420b  mov     rax, cs:?g_pfnSwitchToThread@@3P6AHXZEA; int (*g_pfnSwitchToThread)(void)
0x180004212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004217  test    eax, eax
0x180004219  jnz     short loc_180004229
0x18000421b  mov     ecx, ebp; dwMilliseconds
0x18000421d  call    cs:__imp_Sleep
0x180004224  nop     dword ptr [rax+rax+00h]
0x180004229  cmp     r14d, 4
0x18000422d  jb      loc_1800042CC
0x180004233  mov     ebp, 64h ; 'd'
0x180004238  movd    xmm0, edi
0x18000423c  cvtdq2pd xmm0, xmm0
0x180004240  mulsd   xmm0, cs:?sm_dblDfltSpinAdjFctr@CReaderWriterLock3@@1NA; double CReaderWriterLock3::sm_dblDfltSpinAdjFctr
0x180004248  cvttsd2si edi, xmm0
0x18000424c  cmp     edi, 2710h
0x180004252  jg      short loc_1800042B8
0x180004254  cmp     edi, 64h ; 'd'
0x180004257  jg      short loc_18000425E
0x180004259  mov     edi, 64h ; 'd'
0x18000425e  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x180004265  inc     r14d
0x180004268  jmp     loc_1800041BF
0x18000426d  cmp     dx, 0FFFFh
0x180004272  jz      short loc_180004203
0x180004274  lea     ecx, [rdx+1]
0x180004277  mov     eax, edx
0x180004279  lock cmpxchg [rsi], ecx
0x18000427d  cmp     edx, eax
0x18000427f  jnz     short loc_180004203
0x180004281  mov     al, 1
0x180004283  test    al, al
0x180004285  jnz     short loc_1800042D9
0x180004287  pause
0x180004289  jmp     loc_1800041D7
0x18000428e  mov     eax, [rsi+4]
0x180004291  test    eax, eax
0x180004293  jnz     short loc_1800042AE
0x180004295  mov     edx, [rsi]
0x180004297  test    dx, dx
0x18000429a  jnz     short loc_1800042AE
0x18000429c  mov     ecx, edx
0x18000429e  mov     eax, edx
0x1800042a0  or      ecx, 0FFFFh
0x1800042a6  lock cmpxchg [rsi], ecx
0x1800042aa  cmp     edx, eax
0x1800042ac  jz      short loc_1800042E9
0x1800042ae  mov     rcx, rsi; this
0x1800042b1  call    ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
0x1800042b6  jmp     short loc_180004283
0x1800042b8  movzx   ecx, cs:?sm_wDefaultSpinCount@CReaderWriterLock3@@1GA; ushort CReaderWriterLock3::sm_wDefaultSpinCount
0x1800042bf  mov     edi, 2710h
0x1800042c4  inc     r14d
0x1800042c7  jmp     loc_1800041BF
0x1800042cc  mov     ebp, ds:rva dword_180032D40[r12+r14*4]
0x1800042d4  jmp     loc_180004238
0x1800042d9  add     rsp, 20h
0x1800042dd  pop     r15
0x1800042df  pop     r14
0x1800042e1  pop     r12
0x1800042e3  pop     rdi
0x1800042e4  pop     rsi
0x1800042e5  pop     rbp
0x1800042e6  pop     rbx
0x1800042e7  retn
0x1800042e9  call    cs:__imp_GetCurrentThreadId
0x1800042f0  nop     dword ptr [rax+rax+00h]
0x1800042f5  and     eax, 0FFFFFFFCh
0x1800042f8  or      eax, 1
0x1800042fb  xchg    eax, [rsi+4]
0x1800042fe  mov     al, 1
0x180004300  jmp     short loc_180004283
0x180004302  mov     ebx, 1
0x180004307  jmp     loc_1800041D7
```
