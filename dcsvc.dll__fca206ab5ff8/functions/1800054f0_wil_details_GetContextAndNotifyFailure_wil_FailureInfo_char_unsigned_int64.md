# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800054f0`
- end: `0x1800056f7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800054f0`
- `0x180005bec`
- `0x180005cd0`
- `0x1800068b8`
- `0x1800085d0`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000551a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000551a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055dc`

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
0x1800054f0  push    rbx
0x1800054f2  push    rbp
0x1800054f3  push    rsi
0x1800054f4  push    rdi
0x1800054f5  push    r14
0x1800054f7  sub     rsp, 20h
0x1800054fb  mov     r14, r8
0x1800054fe  mov     rsi, rdx
0x180005501  mov     rdi, rcx
0x180005504  mov     byte ptr [rdx], 0
0x180005507  xor     bpl, bpl
0x18000550a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005511  test    rbx, rbx
0x180005514  jz      loc_1800055B0
0x18000551a  call    cs:__imp_GetCurrentThreadId
0x180005520  mov     r9d, eax
0x180005523  mov     r8d, eax
0x180005526  shr     r8, 2
0x18000552a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005534  mul     r8
0x180005537  shr     rdx, 3
0x18000553b  lea     rcx, [rdx+rdx*4]
0x18000553f  add     rcx, rcx
0x180005542  sub     r8, rcx
0x180005545  mov     rbx, [rbx+r8*8]
0x180005549  jmp     short loc_180005554
0x18000554b  cmp     [rbx], r9d
0x18000554e  jz      short loc_1800055CB
0x180005550  mov     rbx, [rbx+8]
0x180005554  test    rbx, rbx
0x180005557  jnz     short loc_18000554B
0x180005559  test    rbx, rbx
0x18000555c  jz      short loc_1800055B0
0x18000555e  cmp     qword ptr [rbx], 0
0x180005562  jz      short loc_1800055B0
0x180005564  mov     [rsi], bpl
0x180005567  mov     r9, r14; unsigned __int64
0x18000556a  mov     r8, rsi; char *
0x18000556d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005570  mov     rcx, rdi; struct wil::FailureInfo *
0x180005573  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005578  test    al, al
0x18000557a  jz      short loc_180005580
0x18000557c  mov     [rdi+48h], rsi
0x180005580  mov     rbx, [rbx]
0x180005583  mov     al, [rbx+28h]
0x180005586  mov     byte ptr [rbx+28h], 1
0x18000558a  test    al, al
0x18000558c  jnz     short loc_1800055A7
0x18000558e  mov     rcx, [rbx+8]
0x180005592  mov     rax, [rcx]
0x180005595  mov     rdx, rdi
0x180005598  mov     rax, [rax]
0x18000559b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055a0  or      bpl, al
0x1800055a3  mov     byte ptr [rbx+28h], 0
0x1800055a7  mov     rbx, [rbx+10h]
0x1800055ab  test    rbx, rbx
0x1800055ae  jnz     short loc_180005583
0x1800055b0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800055b7  test    rax, rax
0x1800055ba  jz      short loc_1800055DC
0x1800055bc  test    bpl, bpl
0x1800055bf  jnz     short loc_1800055D1
0x1800055c1  test    byte ptr [rdi+4], 2
0x1800055c5  jnz     short loc_1800055D1
0x1800055c7  xor     ecx, ecx
0x1800055c9  jmp     short loc_1800055D3
0x1800055cb  add     rbx, 10h
0x1800055cf  jmp     short loc_180005559
0x1800055d1  mov     cl, 1
0x1800055d3  mov     rdx, rdi
0x1800055d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055db  nop
0x1800055dc  call    cs:__imp_GetCurrentThreadId
0x1800055e2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800055e8  cmp     ecx, eax
0x1800055ea  jz      loc_1800056EC
0x1800055f0  mov     ecx, 1
0x1800055f5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800055fd  inc     ecx; this
0x1800055ff  cmp     ecx, 4
0x180005602  jge     loc_1800056E5
0x180005608  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000560e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005613  mov     rbx, rax
0x180005616  test    rax, rax
0x180005619  jz      loc_1800056DB
0x18000561f  mov     esi, [rax+10h]
0x180005622  mov     ebp, 50h ; 'P'
0x180005627  cmp     qword ptr [rax+18h], 0
0x18000562c  jnz     short loc_180005663
0x18000562e  test    esi, esi
0x180005630  jz      short loc_180005663
0x180005632  mov     edx, 190h; dwBytes
0x180005637  lea     ecx, [rbp-48h]; dwFlags
0x18000563a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000563f  mov     [rbx+18h], rax
0x180005643  test    rax, rax
0x180005646  jz      short loc_180005663
0x180005648  mov     dword ptr [rbx+20h], 5
0x18000564f  lea     rcx, [rax+190h]
0x180005656  jmp     short loc_18000565E
0x180005658  mov     [rax], bp
0x18000565b  add     rax, rbp
0x18000565e  cmp     rax, rcx
0x180005661  jnz     short loc_180005658
0x180005663  mov     r9, [rbx+18h]
0x180005667  test    r9, r9
0x18000566a  jz      short loc_1800056DB
0x18000566c  test    esi, esi
0x18000566e  jz      short loc_1800056A1
0x180005670  mov     rcx, r9
0x180005673  movzx   eax, word ptr [rbx+20h]
0x180005677  lea     rdx, [rax+rax*4]
0x18000567b  shl     rdx, 4
0x18000567f  add     rdx, r9
0x180005682  cmp     r9, rdx
0x180005685  jz      short loc_1800056A1
0x180005687  mov     r8d, [rbx+10h]
0x18000568b  cmp     [rcx+4], r8d
0x18000568f  jbe     short loc_180005699
0x180005691  mov     eax, [rdi+8]
0x180005694  cmp     [rcx+8], eax
0x180005697  jz      short loc_1800056DB
0x180005699  add     rcx, rbp
0x18000569c  cmp     rcx, rdx
0x18000569f  jnz     short loc_18000568B
0x1800056a1  movzx   eax, word ptr [rbx+22h]
0x1800056a5  inc     eax
0x1800056a7  movzx   ecx, word ptr [rbx+20h]
0x1800056ab  xor     edx, edx
0x1800056ad  div     ecx
0x1800056af  mov     [rbx+22h], dx
0x1800056b3  mov     rax, [rbx+8]
0x1800056b7  mov     r8d, 1
0x1800056bd  lock xadd [rax], r8d
0x1800056c2  inc     r8d; unsigned int
0x1800056c5  movzx   eax, dx
0x1800056c8  lea     rcx, [rax+rax*4]
0x1800056cc  shl     rcx, 4
0x1800056d0  add     rcx, r9; this
0x1800056d3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800056d6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800056db  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800056e5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800056ec  add     rsp, 20h
0x1800056f0  pop     r14
0x1800056f2  pop     rdi
0x1800056f3  pop     rsi
0x1800056f4  pop     rbp
0x1800056f5  pop     rbx
0x1800056f6  retn
```
