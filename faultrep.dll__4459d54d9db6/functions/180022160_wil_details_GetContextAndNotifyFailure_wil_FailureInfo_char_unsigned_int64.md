# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180022160`
- end: `0x180022367`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180022160`
- `0x180022430`
- `0x180022514`
- `0x180022850`
- `0x180023af8`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002218a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002224c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002218a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002224c`

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
0x180022160  push    rbx
0x180022162  push    rbp
0x180022163  push    rsi
0x180022164  push    rdi
0x180022165  push    r14
0x180022167  sub     rsp, 20h
0x18002216b  mov     r14, r8
0x18002216e  mov     rsi, rdx
0x180022171  mov     rdi, rcx
0x180022174  mov     byte ptr [rdx], 0
0x180022177  xor     bpl, bpl
0x18002217a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180022181  test    rbx, rbx
0x180022184  jz      loc_180022220
0x18002218a  call    cs:__imp_GetCurrentThreadId
0x180022190  mov     r9d, eax
0x180022193  mov     r8d, eax
0x180022196  shr     r8, 2
0x18002219a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800221a4  mul     r8
0x1800221a7  shr     rdx, 3
0x1800221ab  lea     rcx, [rdx+rdx*4]
0x1800221af  add     rcx, rcx
0x1800221b2  sub     r8, rcx
0x1800221b5  mov     rbx, [rbx+r8*8]
0x1800221b9  jmp     short loc_1800221C4
0x1800221bb  cmp     [rbx], r9d
0x1800221be  jz      short loc_18002223B
0x1800221c0  mov     rbx, [rbx+8]
0x1800221c4  test    rbx, rbx
0x1800221c7  jnz     short loc_1800221BB
0x1800221c9  test    rbx, rbx
0x1800221cc  jz      short loc_180022220
0x1800221ce  cmp     qword ptr [rbx], 0
0x1800221d2  jz      short loc_180022220
0x1800221d4  mov     [rsi], bpl
0x1800221d7  mov     r9, r14; unsigned __int64
0x1800221da  mov     r8, rsi; char *
0x1800221dd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800221e0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800221e3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800221e8  test    al, al
0x1800221ea  jz      short loc_1800221F0
0x1800221ec  mov     [rdi+48h], rsi
0x1800221f0  mov     rbx, [rbx]
0x1800221f3  mov     al, [rbx+28h]
0x1800221f6  mov     byte ptr [rbx+28h], 1
0x1800221fa  test    al, al
0x1800221fc  jnz     short loc_180022217
0x1800221fe  mov     rcx, [rbx+8]
0x180022202  mov     rax, [rcx]
0x180022205  mov     rdx, rdi
0x180022208  mov     rax, [rax]
0x18002220b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022210  or      bpl, al
0x180022213  mov     byte ptr [rbx+28h], 0
0x180022217  mov     rbx, [rbx+10h]
0x18002221b  test    rbx, rbx
0x18002221e  jnz     short loc_1800221F3
0x180022220  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180022227  test    rax, rax
0x18002222a  jz      short loc_18002224C
0x18002222c  test    bpl, bpl
0x18002222f  jnz     short loc_180022241
0x180022231  test    byte ptr [rdi+4], 2
0x180022235  jnz     short loc_180022241
0x180022237  xor     ecx, ecx
0x180022239  jmp     short loc_180022243
0x18002223b  add     rbx, 10h
0x18002223f  jmp     short loc_1800221C9
0x180022241  mov     cl, 1
0x180022243  mov     rdx, rdi
0x180022246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002224b  nop
0x18002224c  call    cs:__imp_GetCurrentThreadId
0x180022252  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180022258  cmp     ecx, eax
0x18002225a  jz      loc_18002235C
0x180022260  mov     ecx, 1
0x180022265  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18002226d  inc     ecx; this
0x18002226f  cmp     ecx, 4
0x180022272  jge     loc_180022355
0x180022278  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18002227e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180022283  mov     rbx, rax
0x180022286  test    rax, rax
0x180022289  jz      loc_18002234B
0x18002228f  mov     esi, [rax+10h]
0x180022292  mov     ebp, 50h ; 'P'
0x180022297  cmp     qword ptr [rax+18h], 0
0x18002229c  jnz     short loc_1800222D3
0x18002229e  test    esi, esi
0x1800222a0  jz      short loc_1800222D3
0x1800222a2  mov     edx, 190h; dwBytes
0x1800222a7  lea     ecx, [rbp-48h]; dwFlags
0x1800222aa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800222af  mov     [rbx+18h], rax
0x1800222b3  test    rax, rax
0x1800222b6  jz      short loc_1800222D3
0x1800222b8  mov     dword ptr [rbx+20h], 5
0x1800222bf  lea     rcx, [rax+190h]
0x1800222c6  jmp     short loc_1800222CE
0x1800222c8  mov     [rax], bp
0x1800222cb  add     rax, rbp
0x1800222ce  cmp     rax, rcx
0x1800222d1  jnz     short loc_1800222C8
0x1800222d3  mov     r9, [rbx+18h]
0x1800222d7  test    r9, r9
0x1800222da  jz      short loc_18002234B
0x1800222dc  test    esi, esi
0x1800222de  jz      short loc_180022311
0x1800222e0  mov     rcx, r9
0x1800222e3  movzx   eax, word ptr [rbx+20h]
0x1800222e7  lea     rdx, [rax+rax*4]
0x1800222eb  shl     rdx, 4
0x1800222ef  add     rdx, r9
0x1800222f2  cmp     r9, rdx
0x1800222f5  jz      short loc_180022311
0x1800222f7  mov     r8d, [rbx+10h]
0x1800222fb  cmp     [rcx+4], r8d
0x1800222ff  jbe     short loc_180022309
0x180022301  mov     eax, [rdi+8]
0x180022304  cmp     [rcx+8], eax
0x180022307  jz      short loc_18002234B
0x180022309  add     rcx, rbp
0x18002230c  cmp     rcx, rdx
0x18002230f  jnz     short loc_1800222FB
0x180022311  movzx   eax, word ptr [rbx+22h]
0x180022315  inc     eax
0x180022317  movzx   ecx, word ptr [rbx+20h]
0x18002231b  xor     edx, edx
0x18002231d  div     ecx
0x18002231f  mov     [rbx+22h], dx
0x180022323  mov     rax, [rbx+8]
0x180022327  mov     r8d, 1
0x18002232d  lock xadd [rax], r8d
0x180022332  inc     r8d; unsigned int
0x180022335  movzx   eax, dx
0x180022338  lea     rcx, [rax+rax*4]
0x18002233c  shl     rcx, 4
0x180022340  add     rcx, r9; this
0x180022343  mov     rdx, rdi; struct wil::FailureInfo *
0x180022346  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18002234b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180022355  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18002235c  add     rsp, 20h
0x180022360  pop     r14
0x180022362  pop     rdi
0x180022363  pop     rsi
0x180022364  pop     rbp
0x180022365  pop     rbx
0x180022366  retn
```
