# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800061f0`
- end: `0x1800063f6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800061f0`
- `0x180006b0c`
- `0x180006bf0`
- `0x180008038`
- `0x180009648`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000621a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800062db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000621a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800062db`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(unsigned __int64 this, struct wil::FailureInfo *a2, char *a3)
{
  char v3; // bp
  __int64 v4; // rbx
  wil::details *v7; // rdi
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
  volatile signed __int32 *v25; // rax

  *(_BYTE *)a2 = 0;
  v3 = 0;
  v4 = wil::details::g_pThreadFailureCallbacks;
  v7 = (wil::details *)this;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    CurrentThreadId = GetCurrentThreadId();
    this = 10 * ((CurrentThreadId >> 2) / 0xA);
    for ( i = *(_QWORD *)(v4 + 8 * ((CurrentThreadId >> 2) % 0xA)); i; i = *(_QWORD *)(i + 8) )
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
             v7,
             *(struct wil::details::ThreadFailureCallbackHolder **)i,
             (char *)a2,
             (unsigned __int64)a3) )
      {
        *((_QWORD *)v7 + 9) = a2;
      }
      v10 = *(struct wil::details::ThreadFailureCallbackHolder **)i;
      do
      {
        v11 = *((_BYTE *)v10 + 40);
        *((_BYTE *)v10 + 40) = 1;
        if ( !v11 )
        {
          v3 |= (***((__int64 (__fastcall ****)(_QWORD, wil::details *))v10 + 1))(*((_QWORD *)v10 + 1), v7);
          *((_BYTE *)v10 + 40) = 0;
        }
        v10 = (struct wil::details::ThreadFailureCallbackHolder *)*((_QWORD *)v10 + 2);
      }
      while ( v10 );
    }
  }
  if ( wil::details::g_pfnTelemetryCallback )
  {
    if ( v3 || (*((_BYTE *)v7 + 4) & 2) != 0 )
      LOBYTE(this) = 1;
    else
      this = 0;
    wil::details::g_pfnTelemetryCallback(this, v7);
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
            v25 = (volatile signed __int32 *)*((_QWORD *)v17 + 1);
            *((_WORD *)v17 + 17) = v24;
            wil::details_abi::ThreadLocalFailureInfo::Set(
              (wil::details_abi::ThreadLocalFailureInfo *)(v21 + 80LL * v24),
              v7,
              _InterlockedIncrement(v25));
          }
          else
          {
            while ( *(_DWORD *)(v22 + 4) <= *((_DWORD *)v17 + 4) || *(_DWORD *)(v22 + 8) != *((_DWORD *)v7 + 2) )
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
0x1800061f0  push    rbx
0x1800061f2  push    rbp
0x1800061f3  push    rsi
0x1800061f4  push    rdi
0x1800061f5  push    r14
0x1800061f7  sub     rsp, 20h
0x1800061fb  mov     byte ptr [rdx], 0
0x1800061fe  xor     bpl, bpl
0x180006201  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006208  mov     r14, r8
0x18000620b  mov     rsi, rdx
0x18000620e  mov     rdi, rcx
0x180006211  test    rbx, rbx
0x180006214  jz      loc_1800062B0
0x18000621a  call    cs:__imp_GetCurrentThreadId
0x180006220  mov     r8d, eax
0x180006223  mov     r9d, eax
0x180006226  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006230  shr     r8, 2
0x180006234  mul     r8
0x180006237  shr     rdx, 3
0x18000623b  lea     rcx, [rdx+rdx*4]
0x18000623f  add     rcx, rcx
0x180006242  sub     r8, rcx
0x180006245  mov     rbx, [rbx+r8*8]
0x180006249  jmp     short loc_180006254
0x18000624b  cmp     [rbx], r9d
0x18000624e  jz      short loc_1800062CB
0x180006250  mov     rbx, [rbx+8]
0x180006254  test    rbx, rbx
0x180006257  jnz     short loc_18000624B
0x180006259  test    rbx, rbx
0x18000625c  jz      short loc_1800062B0
0x18000625e  cmp     qword ptr [rbx], 0
0x180006262  jz      short loc_1800062B0
0x180006264  mov     [rsi], bpl
0x180006267  mov     r9, r14; unsigned __int64
0x18000626a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000626d  mov     r8, rsi; char *
0x180006270  mov     rcx, rdi; struct wil::FailureInfo *
0x180006273  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006278  test    al, al
0x18000627a  jz      short loc_180006280
0x18000627c  mov     [rdi+48h], rsi
0x180006280  mov     rbx, [rbx]
0x180006283  mov     al, [rbx+28h]
0x180006286  mov     byte ptr [rbx+28h], 1
0x18000628a  test    al, al
0x18000628c  jnz     short loc_1800062A7
0x18000628e  mov     rcx, [rbx+8]
0x180006292  mov     rdx, rdi
0x180006295  mov     rax, [rcx]
0x180006298  mov     rax, [rax]
0x18000629b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062a0  or      bpl, al
0x1800062a3  mov     byte ptr [rbx+28h], 0
0x1800062a7  mov     rbx, [rbx+10h]
0x1800062ab  test    rbx, rbx
0x1800062ae  jnz     short loc_180006283
0x1800062b0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800062b7  test    rax, rax
0x1800062ba  jz      short loc_1800062DB
0x1800062bc  test    bpl, bpl
0x1800062bf  jnz     short loc_1800062D1
0x1800062c1  test    byte ptr [rdi+4], 2
0x1800062c5  jnz     short loc_1800062D1
0x1800062c7  xor     ecx, ecx
0x1800062c9  jmp     short loc_1800062D3
0x1800062cb  add     rbx, 10h
0x1800062cf  jmp     short loc_180006259
0x1800062d1  mov     cl, 1
0x1800062d3  mov     rdx, rdi
0x1800062d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062db  call    cs:__imp_GetCurrentThreadId
0x1800062e1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800062e7  cmp     ecx, eax
0x1800062e9  jz      loc_1800063EB
0x1800062ef  mov     ecx, 1
0x1800062f4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800062fc  inc     ecx; this
0x1800062fe  cmp     ecx, 4
0x180006301  jge     loc_1800063E4
0x180006307  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000630d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180006312  mov     rbx, rax
0x180006315  test    rax, rax
0x180006318  jz      loc_1800063DA
0x18000631e  cmp     qword ptr [rax+18h], 0
0x180006323  mov     ebp, 50h ; 'P'
0x180006328  mov     esi, [rax+10h]
0x18000632b  jnz     short loc_180006362
0x18000632d  test    esi, esi
0x18000632f  jz      short loc_180006362
0x180006331  mov     edx, 190h; dwBytes
0x180006336  lea     ecx, [rbp-48h]; dwFlags
0x180006339  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000633e  mov     [rbx+18h], rax
0x180006342  test    rax, rax
0x180006345  jz      short loc_180006362
0x180006347  mov     dword ptr [rbx+20h], 5
0x18000634e  lea     rcx, [rax+190h]
0x180006355  jmp     short loc_18000635D
0x180006357  mov     [rax], bp
0x18000635a  add     rax, rbp
0x18000635d  cmp     rax, rcx
0x180006360  jnz     short loc_180006357
0x180006362  mov     r9, [rbx+18h]
0x180006366  test    r9, r9
0x180006369  jz      short loc_1800063DA
0x18000636b  test    esi, esi
0x18000636d  jz      short loc_1800063A0
0x18000636f  movzx   eax, word ptr [rbx+20h]
0x180006373  mov     rcx, r9
0x180006376  lea     rdx, [rax+rax*4]
0x18000637a  shl     rdx, 4
0x18000637e  add     rdx, r9
0x180006381  cmp     r9, rdx
0x180006384  jz      short loc_1800063A0
0x180006386  mov     r8d, [rbx+10h]
0x18000638a  cmp     [rcx+4], r8d
0x18000638e  jbe     short loc_180006398
0x180006390  mov     eax, [rdi+8]
0x180006393  cmp     [rcx+8], eax
0x180006396  jz      short loc_1800063DA
0x180006398  add     rcx, rbp
0x18000639b  cmp     rcx, rdx
0x18000639e  jnz     short loc_18000638A
0x1800063a0  movzx   eax, word ptr [rbx+22h]
0x1800063a4  xor     edx, edx
0x1800063a6  movzx   ecx, word ptr [rbx+20h]
0x1800063aa  inc     eax
0x1800063ac  div     ecx
0x1800063ae  mov     rax, [rbx+8]
0x1800063b2  mov     r8d, 1
0x1800063b8  mov     [rbx+22h], dx
0x1800063bc  lock xadd [rax], r8d
0x1800063c1  movzx   eax, dx
0x1800063c4  inc     r8d; unsigned int
0x1800063c7  mov     rdx, rdi; struct wil::FailureInfo *
0x1800063ca  lea     rcx, [rax+rax*4]
0x1800063ce  shl     rcx, 4
0x1800063d2  add     rcx, r9; this
0x1800063d5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800063da  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800063e4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800063eb  add     rsp, 20h
0x1800063ef  pop     r14
0x1800063f1  pop     rdi
0x1800063f2  pop     rsi
0x1800063f3  pop     rbp
0x1800063f4  pop     rbx
0x1800063f5  retn
```
