# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005560`
- end: `0x180005767`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005560`
- `0x180005c5c`
- `0x180005d40`
- `0x180006840`
- `0x180008364`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000558a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000564c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000558a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000564c`

## pseudocode

```c
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
0x180005560  push    rbx
0x180005562  push    rbp
0x180005563  push    rsi
0x180005564  push    rdi
0x180005565  push    r14
0x180005567  sub     rsp, 20h
0x18000556b  mov     r14, r8
0x18000556e  mov     rsi, rdx
0x180005571  mov     rdi, rcx
0x180005574  mov     byte ptr [rdx], 0
0x180005577  xor     bpl, bpl
0x18000557a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005581  test    rbx, rbx
0x180005584  jz      loc_180005620
0x18000558a  call    cs:__imp_GetCurrentThreadId
0x180005590  mov     r9d, eax
0x180005593  mov     r8d, eax
0x180005596  shr     r8, 2
0x18000559a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800055a4  mul     r8
0x1800055a7  shr     rdx, 3
0x1800055ab  lea     rcx, [rdx+rdx*4]
0x1800055af  add     rcx, rcx
0x1800055b2  sub     r8, rcx
0x1800055b5  mov     rbx, [rbx+r8*8]
0x1800055b9  jmp     short loc_1800055C4
0x1800055bb  cmp     [rbx], r9d
0x1800055be  jz      short loc_18000563B
0x1800055c0  mov     rbx, [rbx+8]
0x1800055c4  test    rbx, rbx
0x1800055c7  jnz     short loc_1800055BB
0x1800055c9  test    rbx, rbx
0x1800055cc  jz      short loc_180005620
0x1800055ce  cmp     qword ptr [rbx], 0
0x1800055d2  jz      short loc_180005620
0x1800055d4  mov     [rsi], bpl
0x1800055d7  mov     r9, r14; unsigned __int64
0x1800055da  mov     r8, rsi; char *
0x1800055dd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800055e0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800055e3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800055e8  test    al, al
0x1800055ea  jz      short loc_1800055F0
0x1800055ec  mov     [rdi+48h], rsi
0x1800055f0  mov     rbx, [rbx]
0x1800055f3  mov     al, [rbx+28h]
0x1800055f6  mov     byte ptr [rbx+28h], 1
0x1800055fa  test    al, al
0x1800055fc  jnz     short loc_180005617
0x1800055fe  mov     rcx, [rbx+8]
0x180005602  mov     rax, [rcx]
0x180005605  mov     rdx, rdi
0x180005608  mov     rax, [rax]
0x18000560b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005610  or      bpl, al
0x180005613  mov     byte ptr [rbx+28h], 0
0x180005617  mov     rbx, [rbx+10h]
0x18000561b  test    rbx, rbx
0x18000561e  jnz     short loc_1800055F3
0x180005620  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005627  test    rax, rax
0x18000562a  jz      short loc_18000564C
0x18000562c  test    bpl, bpl
0x18000562f  jnz     short loc_180005641
0x180005631  test    byte ptr [rdi+4], 2
0x180005635  jnz     short loc_180005641
0x180005637  xor     ecx, ecx
0x180005639  jmp     short loc_180005643
0x18000563b  add     rbx, 10h
0x18000563f  jmp     short loc_1800055C9
0x180005641  mov     cl, 1
0x180005643  mov     rdx, rdi
0x180005646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000564b  nop
0x18000564c  call    cs:__imp_GetCurrentThreadId
0x180005652  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005658  cmp     ecx, eax
0x18000565a  jz      loc_18000575C
0x180005660  mov     ecx, 1
0x180005665  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000566d  inc     ecx; this
0x18000566f  cmp     ecx, 4
0x180005672  jge     loc_180005755
0x180005678  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000567e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005683  mov     rbx, rax
0x180005686  test    rax, rax
0x180005689  jz      loc_18000574B
0x18000568f  mov     esi, [rax+10h]
0x180005692  mov     ebp, 50h ; 'P'
0x180005697  cmp     qword ptr [rax+18h], 0
0x18000569c  jnz     short loc_1800056D3
0x18000569e  test    esi, esi
0x1800056a0  jz      short loc_1800056D3
0x1800056a2  mov     edx, 190h; dwBytes
0x1800056a7  lea     ecx, [rbp-48h]; dwFlags
0x1800056aa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800056af  mov     [rbx+18h], rax
0x1800056b3  test    rax, rax
0x1800056b6  jz      short loc_1800056D3
0x1800056b8  mov     dword ptr [rbx+20h], 5
0x1800056bf  lea     rcx, [rax+190h]
0x1800056c6  jmp     short loc_1800056CE
0x1800056c8  mov     [rax], bp
0x1800056cb  add     rax, rbp
0x1800056ce  cmp     rax, rcx
0x1800056d1  jnz     short loc_1800056C8
0x1800056d3  mov     r9, [rbx+18h]
0x1800056d7  test    r9, r9
0x1800056da  jz      short loc_18000574B
0x1800056dc  test    esi, esi
0x1800056de  jz      short loc_180005711
0x1800056e0  mov     rcx, r9
0x1800056e3  movzx   eax, word ptr [rbx+20h]
0x1800056e7  lea     rdx, [rax+rax*4]
0x1800056eb  shl     rdx, 4
0x1800056ef  add     rdx, r9
0x1800056f2  cmp     r9, rdx
0x1800056f5  jz      short loc_180005711
0x1800056f7  mov     r8d, [rbx+10h]
0x1800056fb  cmp     [rcx+4], r8d
0x1800056ff  jbe     short loc_180005709
0x180005701  mov     eax, [rdi+8]
0x180005704  cmp     [rcx+8], eax
0x180005707  jz      short loc_18000574B
0x180005709  add     rcx, rbp
0x18000570c  cmp     rcx, rdx
0x18000570f  jnz     short loc_1800056FB
0x180005711  movzx   eax, word ptr [rbx+22h]
0x180005715  inc     eax
0x180005717  movzx   ecx, word ptr [rbx+20h]
0x18000571b  xor     edx, edx
0x18000571d  div     ecx
0x18000571f  mov     [rbx+22h], dx
0x180005723  mov     rax, [rbx+8]
0x180005727  mov     r8d, 1
0x18000572d  lock xadd [rax], r8d
0x180005732  inc     r8d; unsigned int
0x180005735  movzx   eax, dx
0x180005738  lea     rcx, [rax+rax*4]
0x18000573c  shl     rcx, 4
0x180005740  add     rcx, r9; this
0x180005743  mov     rdx, rdi; struct wil::FailureInfo *
0x180005746  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000574b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005755  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000575c  add     rsp, 20h
0x180005760  pop     r14
0x180005762  pop     rdi
0x180005763  pop     rsi
0x180005764  pop     rbp
0x180005765  pop     rbx
0x180005766  retn
```
