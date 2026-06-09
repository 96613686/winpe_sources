# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800242b0`
- end: `0x1800244cd`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `541`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800242b0`
- `0x180024a20`
- `0x180024b20`
- `0x180025d20`
- `0x180027b60`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800242da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800243aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800242da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800243aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::GetContextAndNotifyFailure(wil::details *this, struct wil::FailureInfo *a2, char *a3)
{
  wil::details *v5; // rdi
  char v6; // si
  __int64 v7; // rbx
  unsigned __int64 CurrentThreadId; // r9
  struct wil::details::ThreadFailureCallbackHolder **v9; // rbx
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

  v5 = this;
  *(_BYTE *)a2 = 0;
  v6 = 0;
  v7 = wil::details::g_pThreadFailureCallbacks;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = *(wil::details **)(v7 + 8 * ((CurrentThreadId >> 2) % 0xA));
    if ( this )
    {
      while ( *(_DWORD *)this != (_DWORD)CurrentThreadId )
      {
        this = (wil::details *)*((_QWORD *)this + 1);
        if ( !this )
          goto LABEL_5;
      }
      v9 = (struct wil::details::ThreadFailureCallbackHolder **)((char *)this + 16);
    }
    else
    {
LABEL_5:
      v9 = 0;
    }
    if ( v9 && *v9 )
    {
      *(_BYTE *)a2 = 0;
      if ( wil::details::ThreadFailureCallbackHolder::GetThreadContext(v5, *v9, (char *)a2, (unsigned __int64)a3) )
        *((_QWORD *)v5 + 9) = a2;
      v10 = *v9;
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
              do
              {
                *v19 = 80;
                v19 += 40;
              }
              while ( v19 != v20 );
            }
          }
        }
        v21 = *((_QWORD *)v17 + 3);
        if ( v21 )
        {
          if ( !v18 || (v22 = *((_QWORD *)v17 + 3), v23 = v21 + 80LL * *((unsigned __int16 *)v17 + 16), v21 == v23) )
          {
LABEL_35:
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
                goto LABEL_35;
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
0x1800242b0  push    rbx
0x1800242b2  push    rbp
0x1800242b3  push    rsi
0x1800242b4  push    rdi
0x1800242b5  push    r14
0x1800242b7  sub     rsp, 20h
0x1800242bb  mov     rbp, r8
0x1800242be  mov     r14, rdx
0x1800242c1  mov     rdi, rcx
0x1800242c4  mov     byte ptr [rdx], 0
0x1800242c7  xor     sil, sil
0x1800242ca  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800242d1  test    rbx, rbx
0x1800242d4  jz      loc_18002437E
0x1800242da  call    cs:__imp_GetCurrentThreadId
0x1800242e0  mov     r9d, eax
0x1800242e3  mov     r8d, eax
0x1800242e6  shr     r8, 2
0x1800242ea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800242f4  mul     r8
0x1800242f7  shr     rdx, 3
0x1800242fb  lea     rcx, [rdx+rdx*4]
0x1800242ff  add     rcx, rcx
0x180024302  sub     r8, rcx
0x180024305  mov     rcx, [rbx+r8*8]
0x180024309  test    rcx, rcx
0x18002430c  jz      short loc_180024322
0x18002430e  xchg    ax, ax
0x180024310  cmp     [rcx], r9d
0x180024313  jz      loc_180024399
0x180024319  mov     rcx, [rcx+8]
0x18002431d  test    rcx, rcx
0x180024320  jnz     short loc_180024310
0x180024322  xor     ebx, ebx
0x180024324  test    rbx, rbx
0x180024327  jz      short loc_18002437E
0x180024329  cmp     qword ptr [rbx], 0
0x18002432d  jz      short loc_18002437E
0x18002432f  mov     [r14], sil
0x180024332  mov     r9, rbp; unsigned __int64
0x180024335  mov     r8, r14; char *
0x180024338  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18002433b  mov     rcx, rdi; struct wil::FailureInfo *
0x18002433e  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180024343  test    al, al
0x180024345  jz      short loc_18002434B
0x180024347  mov     [rdi+48h], r14
0x18002434b  mov     rbx, [rbx]
0x18002434e  xchg    ax, ax
0x180024350  movzx   eax, byte ptr [rbx+28h]
0x180024354  mov     byte ptr [rbx+28h], 1
0x180024358  test    al, al
0x18002435a  jnz     short loc_180024375
0x18002435c  mov     rcx, [rbx+8]
0x180024360  mov     rax, [rcx]
0x180024363  mov     rdx, rdi
0x180024366  mov     rax, [rax]
0x180024369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002436e  or      sil, al
0x180024371  mov     byte ptr [rbx+28h], 0
0x180024375  mov     rbx, [rbx+10h]
0x180024379  test    rbx, rbx
0x18002437c  jnz     short loc_180024350
0x18002437e  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180024385  test    rax, rax
0x180024388  jz      short loc_1800243AA
0x18002438a  test    sil, sil
0x18002438d  jnz     short loc_18002439F
0x18002438f  test    byte ptr [rdi+4], 2
0x180024393  jnz     short loc_18002439F
0x180024395  xor     ecx, ecx
0x180024397  jmp     short loc_1800243A1
0x180024399  lea     rbx, [rcx+10h]
0x18002439d  jmp     short loc_180024324
0x18002439f  mov     cl, 1
0x1800243a1  mov     rdx, rdi
0x1800243a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243a9  nop
0x1800243aa  call    cs:__imp_GetCurrentThreadId
0x1800243b0  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800243b6  cmp     ecx, eax
0x1800243b8  jz      loc_1800244C2
0x1800243be  mov     ebp, 1
0x1800243c3  mov     ecx, ebp
0x1800243c5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800243cd  inc     ecx; this
0x1800243cf  cmp     ecx, 4
0x1800243d2  jge     loc_1800244BB
0x1800243d8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800243de  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800243e3  mov     rbx, rax
0x1800243e6  test    rax, rax
0x1800243e9  jz      loc_1800244B1
0x1800243ef  mov     esi, [rax+10h]
0x1800243f2  cmp     qword ptr [rax+18h], 0
0x1800243f7  jnz     short loc_18002443E
0x1800243f9  test    esi, esi
0x1800243fb  jz      short loc_18002443E
0x1800243fd  mov     edx, 190h; dwBytes
0x180024402  mov     ecx, 8; dwFlags
0x180024407  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18002440c  mov     [rbx+18h], rax
0x180024410  test    rax, rax
0x180024413  jz      short loc_18002443E
0x180024415  mov     dword ptr [rbx+20h], 5
0x18002441c  lea     rcx, [rax+190h]
0x180024423  cmp     rax, rcx
0x180024426  jz      short loc_18002443E
0x180024428  nop     dword ptr [rax+rax+00000000h]
0x180024430  mov     word ptr [rax], 50h ; 'P'
0x180024435  add     rax, 50h ; 'P'
0x180024439  cmp     rax, rcx
0x18002443c  jnz     short loc_180024430
0x18002443e  mov     r9, [rbx+18h]
0x180024442  test    r9, r9
0x180024445  jz      short loc_1800244B1
0x180024447  test    esi, esi
0x180024449  jz      short loc_18002447D
0x18002444b  mov     rcx, r9
0x18002444e  movzx   eax, word ptr [rbx+20h]
0x180024452  lea     rdx, [rax+rax*4]
0x180024456  shl     rdx, 4
0x18002445a  add     rdx, r9
0x18002445d  cmp     r9, rdx
0x180024460  jz      short loc_18002447D
0x180024462  mov     r8d, [rbx+10h]
0x180024466  cmp     [rcx+4], r8d
0x18002446a  jbe     short loc_180024474
0x18002446c  mov     eax, [rdi+8]
0x18002446f  cmp     [rcx+8], eax
0x180024472  jz      short loc_1800244B1
0x180024474  add     rcx, 50h ; 'P'
0x180024478  cmp     rcx, rdx
0x18002447b  jnz     short loc_180024466
0x18002447d  movzx   eax, word ptr [rbx+22h]
0x180024481  inc     eax
0x180024483  movzx   ecx, word ptr [rbx+20h]
0x180024487  xor     edx, edx
0x180024489  div     ecx
0x18002448b  mov     [rbx+22h], dx
0x18002448f  mov     rax, [rbx+8]
0x180024493  lock xadd [rax], ebp
0x180024497  lea     r8d, [rbp+1]; unsigned int
0x18002449b  movzx   eax, dx
0x18002449e  lea     rcx, [rax+rax*4]
0x1800244a2  shl     rcx, 4
0x1800244a6  add     rcx, r9; this
0x1800244a9  mov     rdx, rdi; struct wil::FailureInfo *
0x1800244ac  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800244b1  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800244bb  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800244c2  add     rsp, 20h
0x1800244c6  pop     r14
0x1800244c8  pop     rdi
0x1800244c9  pop     rsi
0x1800244ca  pop     rbp
0x1800244cb  pop     rbx
0x1800244cc  retn
```
