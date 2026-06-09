# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006310`
- end: `0x180006517`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006310`
- `0x180006c9c`
- `0x180006d80`
- `0x180007e78`
- `0x18000a940`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000633a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800063fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000633a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800063fc`

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
0x180006310  push    rbx
0x180006312  push    rbp
0x180006313  push    rsi
0x180006314  push    rdi
0x180006315  push    r14
0x180006317  sub     rsp, 20h
0x18000631b  mov     r14, r8
0x18000631e  mov     rsi, rdx
0x180006321  mov     rdi, rcx
0x180006324  mov     byte ptr [rdx], 0
0x180006327  xor     bpl, bpl
0x18000632a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006331  test    rbx, rbx
0x180006334  jz      loc_1800063D0
0x18000633a  call    cs:__imp_GetCurrentThreadId
0x180006340  mov     r9d, eax
0x180006343  mov     r8d, eax
0x180006346  shr     r8, 2
0x18000634a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006354  mul     r8
0x180006357  shr     rdx, 3
0x18000635b  lea     rcx, [rdx+rdx*4]
0x18000635f  add     rcx, rcx
0x180006362  sub     r8, rcx
0x180006365  mov     rbx, [rbx+r8*8]
0x180006369  jmp     short loc_180006374
0x18000636b  cmp     [rbx], r9d
0x18000636e  jz      short loc_1800063EB
0x180006370  mov     rbx, [rbx+8]
0x180006374  test    rbx, rbx
0x180006377  jnz     short loc_18000636B
0x180006379  test    rbx, rbx
0x18000637c  jz      short loc_1800063D0
0x18000637e  cmp     qword ptr [rbx], 0
0x180006382  jz      short loc_1800063D0
0x180006384  mov     [rsi], bpl
0x180006387  mov     r9, r14; unsigned __int64
0x18000638a  mov     r8, rsi; char *
0x18000638d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180006390  mov     rcx, rdi; struct wil::FailureInfo *
0x180006393  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006398  test    al, al
0x18000639a  jz      short loc_1800063A0
0x18000639c  mov     [rdi+48h], rsi
0x1800063a0  mov     rbx, [rbx]
0x1800063a3  mov     al, [rbx+28h]
0x1800063a6  mov     byte ptr [rbx+28h], 1
0x1800063aa  test    al, al
0x1800063ac  jnz     short loc_1800063C7
0x1800063ae  mov     rcx, [rbx+8]
0x1800063b2  mov     rax, [rcx]
0x1800063b5  mov     rdx, rdi
0x1800063b8  mov     rax, [rax]
0x1800063bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063c0  or      bpl, al
0x1800063c3  mov     byte ptr [rbx+28h], 0
0x1800063c7  mov     rbx, [rbx+10h]
0x1800063cb  test    rbx, rbx
0x1800063ce  jnz     short loc_1800063A3
0x1800063d0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800063d7  test    rax, rax
0x1800063da  jz      short loc_1800063FC
0x1800063dc  test    bpl, bpl
0x1800063df  jnz     short loc_1800063F1
0x1800063e1  test    byte ptr [rdi+4], 2
0x1800063e5  jnz     short loc_1800063F1
0x1800063e7  xor     ecx, ecx
0x1800063e9  jmp     short loc_1800063F3
0x1800063eb  add     rbx, 10h
0x1800063ef  jmp     short loc_180006379
0x1800063f1  mov     cl, 1
0x1800063f3  mov     rdx, rdi
0x1800063f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063fb  nop
0x1800063fc  call    cs:__imp_GetCurrentThreadId
0x180006402  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006408  cmp     ecx, eax
0x18000640a  jz      loc_18000650C
0x180006410  mov     ecx, 1
0x180006415  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000641d  inc     ecx; this
0x18000641f  cmp     ecx, 4
0x180006422  jge     loc_180006505
0x180006428  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000642e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180006433  mov     rbx, rax
0x180006436  test    rax, rax
0x180006439  jz      loc_1800064FB
0x18000643f  mov     esi, [rax+10h]
0x180006442  mov     ebp, 50h ; 'P'
0x180006447  cmp     qword ptr [rax+18h], 0
0x18000644c  jnz     short loc_180006483
0x18000644e  test    esi, esi
0x180006450  jz      short loc_180006483
0x180006452  mov     edx, 190h; dwBytes
0x180006457  lea     ecx, [rbp-48h]; dwFlags
0x18000645a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000645f  mov     [rbx+18h], rax
0x180006463  test    rax, rax
0x180006466  jz      short loc_180006483
0x180006468  mov     dword ptr [rbx+20h], 5
0x18000646f  lea     rcx, [rax+190h]
0x180006476  jmp     short loc_18000647E
0x180006478  mov     [rax], bp
0x18000647b  add     rax, rbp
0x18000647e  cmp     rax, rcx
0x180006481  jnz     short loc_180006478
0x180006483  mov     r9, [rbx+18h]
0x180006487  test    r9, r9
0x18000648a  jz      short loc_1800064FB
0x18000648c  test    esi, esi
0x18000648e  jz      short loc_1800064C1
0x180006490  mov     rcx, r9
0x180006493  movzx   eax, word ptr [rbx+20h]
0x180006497  lea     rdx, [rax+rax*4]
0x18000649b  shl     rdx, 4
0x18000649f  add     rdx, r9
0x1800064a2  cmp     r9, rdx
0x1800064a5  jz      short loc_1800064C1
0x1800064a7  mov     r8d, [rbx+10h]
0x1800064ab  cmp     [rcx+4], r8d
0x1800064af  jbe     short loc_1800064B9
0x1800064b1  mov     eax, [rdi+8]
0x1800064b4  cmp     [rcx+8], eax
0x1800064b7  jz      short loc_1800064FB
0x1800064b9  add     rcx, rbp
0x1800064bc  cmp     rcx, rdx
0x1800064bf  jnz     short loc_1800064AB
0x1800064c1  movzx   eax, word ptr [rbx+22h]
0x1800064c5  inc     eax
0x1800064c7  movzx   ecx, word ptr [rbx+20h]
0x1800064cb  xor     edx, edx
0x1800064cd  div     ecx
0x1800064cf  mov     [rbx+22h], dx
0x1800064d3  mov     rax, [rbx+8]
0x1800064d7  mov     r8d, 1
0x1800064dd  lock xadd [rax], r8d
0x1800064e2  inc     r8d; unsigned int
0x1800064e5  movzx   eax, dx
0x1800064e8  lea     rcx, [rax+rax*4]
0x1800064ec  shl     rcx, 4
0x1800064f0  add     rcx, r9; this
0x1800064f3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800064f6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800064fb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006505  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000650c  add     rsp, 20h
0x180006510  pop     r14
0x180006512  pop     rdi
0x180006513  pop     rsi
0x180006514  pop     rbp
0x180006515  pop     rbx
0x180006516  retn
```
