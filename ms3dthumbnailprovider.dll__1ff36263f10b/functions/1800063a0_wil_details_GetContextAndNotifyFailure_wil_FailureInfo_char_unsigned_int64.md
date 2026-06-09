# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800063a0`
- end: `0x1800065a7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800063a0`
- `0x180006b68`
- `0x180006c4c`
- `0x180007b60`
- `0x180008410`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800063ca`
- `KERNEL32!GetCurrentThreadId` at `0x18000648c`
- `KERNEL32!GetCurrentThreadId` at `0x1800063ca`
- `KERNEL32!GetCurrentThreadId` at `0x18000648c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  wil::details *v5; // rdi
  char v6; // bp
  __int64 v7; // rbx
  unsigned __int64 CurrentThreadId; // r9
  __int64 i; // rbx
  struct wil::details::ThreadFailureCallbackHolder *v10; // rbx
  char v11; // al
  DWORD v12; // eax
  bool v13; // dl
  wil::details_abi *v14; // rcx
  struct wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax
  unsigned __int64 v16; // r8
  struct wil::details_abi::ThreadLocalData *v17; // rbx
  int v18; // esi
  _WORD *v19; // rax
  _WORD *v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rcx
  __int64 v23; // rdx
  unsigned __int16 v24; // dx

  v5 = (wil::details *)this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v7 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
    {
      if ( *(_DWORD *)i == (_DWORD)CurrentThreadId )
      {
        i += 16;
        break;
      }
    }
    if ( i && *(_QWORD *)i )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(
             v5,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v5 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v6 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v5);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v6 || (*((_BYTE *)v5 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v5);
  }
  v12 = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != v12 )
  {
    v14 = (wil::details_abi *)(unsigned int)_InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( (int)v14 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = v12;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v14, v13);
      v17 = ThreadLocalDataCache;
      if ( ThreadLocalDataCache )
      {
        v18 = *((_DWORD *)ThreadLocalDataCache + 4);
        if ( !*((_QWORD *)ThreadLocalDataCache + 3) )
        {
          if ( v18 )
          {
            v19 = wil::details::ProcessHeapAlloc(8u, 0x190u, v16);
            *((_QWORD *)v17 + 3) = v19;
            if ( v19 )
            {
              *((_DWORD *)v17 + 8) = 5;
              v20 = v19 + 200;
              while ( v19 != v20 )
              {
                *v19 = 80;
                v19 += 40;
              }
            }
          }
        }
        v21 = *((_QWORD *)v17 + 3);
        if ( v21 )
        {
          if ( !v18 || (v22 = *((_QWORD *)v17 + 3), v23 = v21 + 80LL * *((unsigned __int16 *)v17 + 16), v21 == v23) )
          {
LABEL_36:
            v24 = ((unsigned int)*((unsigned __int16 *)v17 + 17) + 1) % *((unsigned __int16 *)v17 + 16);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v5,
              _InterlockedIncrement(*((volatile signed __int32 **)v17 + 1)));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v5 + 2) )
            {
              v22 += 80;
              if ( v22 == v23 )
                goto LABEL_36;
            }
          }
        }
      }
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x1800063a0  push    rbx
0x1800063a2  push    rbp
0x1800063a3  push    rsi
0x1800063a4  push    rdi
0x1800063a5  push    r14
0x1800063a7  sub     rsp, 20h
0x1800063ab  mov     r14, r8
0x1800063ae  mov     rsi, rdx
0x1800063b1  mov     rdi, rcx
0x1800063b4  mov     byte ptr [rdx], 0
0x1800063b7  xor     bpl, bpl
0x1800063ba  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800063c1  test    rbx, rbx
0x1800063c4  jz      loc_180006460
0x1800063ca  call    cs:__imp_GetCurrentThreadId
0x1800063d0  mov     r9d, eax
0x1800063d3  mov     r8d, eax
0x1800063d6  shr     r8, 2
0x1800063da  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800063e4  mul     r8
0x1800063e7  shr     rdx, 3
0x1800063eb  lea     rcx, [rdx+rdx*4]
0x1800063ef  add     rcx, rcx
0x1800063f2  sub     r8, rcx
0x1800063f5  mov     rbx, [rbx+r8*8]
0x1800063f9  jmp     short loc_180006404
0x1800063fb  cmp     [rbx], r9d
0x1800063fe  jz      short loc_18000647B
0x180006400  mov     rbx, [rbx+8]
0x180006404  test    rbx, rbx
0x180006407  jnz     short loc_1800063FB
0x180006409  test    rbx, rbx
0x18000640c  jz      short loc_180006460
0x18000640e  cmp     qword ptr [rbx], 0
0x180006412  jz      short loc_180006460
0x180006414  mov     [rsi], bpl
0x180006417  mov     r9, r14; unsigned __int64
0x18000641a  mov     r8, rsi; char *
0x18000641d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180006420  mov     rcx, rdi; struct wil::FailureInfo *
0x180006423  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006428  test    al, al
0x18000642a  jz      short loc_180006430
0x18000642c  mov     [rdi+48h], rsi
0x180006430  mov     rbx, [rbx]
0x180006433  mov     al, [rbx+28h]
0x180006436  mov     byte ptr [rbx+28h], 1
0x18000643a  test    al, al
0x18000643c  jnz     short loc_180006457
0x18000643e  mov     rcx, [rbx+8]
0x180006442  mov     rax, [rcx]
0x180006445  mov     rdx, rdi
0x180006448  mov     rax, [rax]
0x18000644b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006450  or      bpl, al
0x180006453  mov     byte ptr [rbx+28h], 0
0x180006457  mov     rbx, [rbx+10h]
0x18000645b  test    rbx, rbx
0x18000645e  jnz     short loc_180006433
0x180006460  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006467  test    rax, rax
0x18000646a  jz      short loc_18000648C
0x18000646c  test    bpl, bpl
0x18000646f  jnz     short loc_180006481
0x180006471  test    byte ptr [rdi+4], 2
0x180006475  jnz     short loc_180006481
0x180006477  xor     ecx, ecx
0x180006479  jmp     short loc_180006483
0x18000647b  add     rbx, 10h
0x18000647f  jmp     short loc_180006409
0x180006481  mov     cl, 1
0x180006483  mov     rdx, rdi
0x180006486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000648b  nop
0x18000648c  call    cs:__imp_GetCurrentThreadId
0x180006492  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006498  cmp     ecx, eax
0x18000649a  jz      loc_18000659C
0x1800064a0  mov     ecx, 1
0x1800064a5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800064ad  inc     ecx; this
0x1800064af  cmp     ecx, 4
0x1800064b2  jge     loc_180006595
0x1800064b8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800064be  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800064c3  mov     rbx, rax
0x1800064c6  test    rax, rax
0x1800064c9  jz      loc_18000658B
0x1800064cf  mov     esi, [rax+10h]
0x1800064d2  mov     ebp, 50h ; 'P'
0x1800064d7  cmp     qword ptr [rax+18h], 0
0x1800064dc  jnz     short loc_180006513
0x1800064de  test    esi, esi
0x1800064e0  jz      short loc_180006513
0x1800064e2  mov     edx, 190h; dwBytes
0x1800064e7  lea     ecx, [rbp-48h]; dwFlags
0x1800064ea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800064ef  mov     [rbx+18h], rax
0x1800064f3  test    rax, rax
0x1800064f6  jz      short loc_180006513
0x1800064f8  mov     dword ptr [rbx+20h], 5
0x1800064ff  lea     rcx, [rax+190h]
0x180006506  jmp     short loc_18000650E
0x180006508  mov     [rax], bp
0x18000650b  add     rax, rbp
0x18000650e  cmp     rax, rcx
0x180006511  jnz     short loc_180006508
0x180006513  mov     r9, [rbx+18h]
0x180006517  test    r9, r9
0x18000651a  jz      short loc_18000658B
0x18000651c  test    esi, esi
0x18000651e  jz      short loc_180006551
0x180006520  mov     rcx, r9
0x180006523  movzx   eax, word ptr [rbx+20h]
0x180006527  lea     rdx, [rax+rax*4]
0x18000652b  shl     rdx, 4
0x18000652f  add     rdx, r9
0x180006532  cmp     r9, rdx
0x180006535  jz      short loc_180006551
0x180006537  mov     r8d, [rbx+10h]
0x18000653b  cmp     [rcx+4], r8d
0x18000653f  jbe     short loc_180006549
0x180006541  mov     eax, [rdi+8]
0x180006544  cmp     [rcx+8], eax
0x180006547  jz      short loc_18000658B
0x180006549  add     rcx, rbp
0x18000654c  cmp     rcx, rdx
0x18000654f  jnz     short loc_18000653B
0x180006551  movzx   eax, word ptr [rbx+22h]
0x180006555  inc     eax
0x180006557  movzx   ecx, word ptr [rbx+20h]
0x18000655b  xor     edx, edx
0x18000655d  div     ecx
0x18000655f  mov     [rbx+22h], dx
0x180006563  mov     rax, [rbx+8]
0x180006567  mov     r8d, 1
0x18000656d  lock xadd [rax], r8d
0x180006572  inc     r8d; unsigned int
0x180006575  movzx   eax, dx
0x180006578  lea     rcx, [rax+rax*4]
0x18000657c  shl     rcx, 4
0x180006580  add     rcx, r9; this
0x180006583  mov     rdx, rdi; struct wil::FailureInfo *
0x180006586  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000658b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006595  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000659c  add     rsp, 20h
0x1800065a0  pop     r14
0x1800065a2  pop     rdi
0x1800065a3  pop     rsi
0x1800065a4  pop     rbp
0x1800065a5  pop     rbx
0x1800065a6  retn
```
