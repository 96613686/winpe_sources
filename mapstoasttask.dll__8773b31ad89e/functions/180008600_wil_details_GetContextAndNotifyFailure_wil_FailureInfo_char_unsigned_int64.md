# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180008600`
- end: `0x180008807`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180008600`
- `0x1800088d0`
- `0x1800089fc`
- `0x180008c0c`
- `0x180008e7c`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000862a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800086ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000862a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800086ec`

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
0x180008600  push    rbx
0x180008602  push    rbp
0x180008603  push    rsi
0x180008604  push    rdi
0x180008605  push    r14
0x180008607  sub     rsp, 20h
0x18000860b  mov     r14, r8
0x18000860e  mov     rsi, rdx
0x180008611  mov     rdi, rcx
0x180008614  mov     byte ptr [rdx], 0
0x180008617  xor     bpl, bpl
0x18000861a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180008621  test    rbx, rbx
0x180008624  jz      loc_1800086C0
0x18000862a  call    cs:__imp_GetCurrentThreadId
0x180008630  mov     r9d, eax
0x180008633  mov     r8d, eax
0x180008636  shr     r8, 2
0x18000863a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180008644  mul     r8
0x180008647  shr     rdx, 3
0x18000864b  lea     rcx, [rdx+rdx*4]
0x18000864f  add     rcx, rcx
0x180008652  sub     r8, rcx
0x180008655  mov     rbx, [rbx+r8*8]
0x180008659  jmp     short loc_180008664
0x18000865b  cmp     [rbx], r9d
0x18000865e  jz      short loc_1800086DB
0x180008660  mov     rbx, [rbx+8]
0x180008664  test    rbx, rbx
0x180008667  jnz     short loc_18000865B
0x180008669  test    rbx, rbx
0x18000866c  jz      short loc_1800086C0
0x18000866e  cmp     qword ptr [rbx], 0
0x180008672  jz      short loc_1800086C0
0x180008674  mov     [rsi], bpl
0x180008677  mov     r9, r14; unsigned __int64
0x18000867a  mov     r8, rsi; char *
0x18000867d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180008680  mov     rcx, rdi; struct wil::FailureInfo *
0x180008683  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180008688  test    al, al
0x18000868a  jz      short loc_180008690
0x18000868c  mov     [rdi+48h], rsi
0x180008690  mov     rbx, [rbx]
0x180008693  mov     al, [rbx+28h]
0x180008696  mov     byte ptr [rbx+28h], 1
0x18000869a  test    al, al
0x18000869c  jnz     short loc_1800086B7
0x18000869e  mov     rcx, [rbx+8]
0x1800086a2  mov     rax, [rcx]
0x1800086a5  mov     rdx, rdi
0x1800086a8  mov     rax, [rax]
0x1800086ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086b0  or      bpl, al
0x1800086b3  mov     byte ptr [rbx+28h], 0
0x1800086b7  mov     rbx, [rbx+10h]
0x1800086bb  test    rbx, rbx
0x1800086be  jnz     short loc_180008693
0x1800086c0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800086c7  test    rax, rax
0x1800086ca  jz      short loc_1800086EC
0x1800086cc  test    bpl, bpl
0x1800086cf  jnz     short loc_1800086E1
0x1800086d1  test    byte ptr [rdi+4], 2
0x1800086d5  jnz     short loc_1800086E1
0x1800086d7  xor     ecx, ecx
0x1800086d9  jmp     short loc_1800086E3
0x1800086db  add     rbx, 10h
0x1800086df  jmp     short loc_180008669
0x1800086e1  mov     cl, 1
0x1800086e3  mov     rdx, rdi
0x1800086e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086eb  nop
0x1800086ec  call    cs:__imp_GetCurrentThreadId
0x1800086f2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800086f8  cmp     ecx, eax
0x1800086fa  jz      loc_1800087FC
0x180008700  mov     ecx, 1
0x180008705  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000870d  inc     ecx; this
0x18000870f  cmp     ecx, 4
0x180008712  jge     loc_1800087F5
0x180008718  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000871e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180008723  mov     rbx, rax
0x180008726  test    rax, rax
0x180008729  jz      loc_1800087EB
0x18000872f  mov     esi, [rax+10h]
0x180008732  mov     ebp, 50h ; 'P'
0x180008737  cmp     qword ptr [rax+18h], 0
0x18000873c  jnz     short loc_180008773
0x18000873e  test    esi, esi
0x180008740  jz      short loc_180008773
0x180008742  mov     edx, 190h; dwBytes
0x180008747  lea     ecx, [rbp-48h]; dwFlags
0x18000874a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000874f  mov     [rbx+18h], rax
0x180008753  test    rax, rax
0x180008756  jz      short loc_180008773
0x180008758  mov     dword ptr [rbx+20h], 5
0x18000875f  lea     rcx, [rax+190h]
0x180008766  jmp     short loc_18000876E
0x180008768  mov     [rax], bp
0x18000876b  add     rax, rbp
0x18000876e  cmp     rax, rcx
0x180008771  jnz     short loc_180008768
0x180008773  mov     r9, [rbx+18h]
0x180008777  test    r9, r9
0x18000877a  jz      short loc_1800087EB
0x18000877c  test    esi, esi
0x18000877e  jz      short loc_1800087B1
0x180008780  mov     rcx, r9
0x180008783  movzx   eax, word ptr [rbx+20h]
0x180008787  lea     rdx, [rax+rax*4]
0x18000878b  shl     rdx, 4
0x18000878f  add     rdx, r9
0x180008792  cmp     r9, rdx
0x180008795  jz      short loc_1800087B1
0x180008797  mov     r8d, [rbx+10h]
0x18000879b  cmp     [rcx+4], r8d
0x18000879f  jbe     short loc_1800087A9
0x1800087a1  mov     eax, [rdi+8]
0x1800087a4  cmp     [rcx+8], eax
0x1800087a7  jz      short loc_1800087EB
0x1800087a9  add     rcx, rbp
0x1800087ac  cmp     rcx, rdx
0x1800087af  jnz     short loc_18000879B
0x1800087b1  movzx   eax, word ptr [rbx+22h]
0x1800087b5  inc     eax
0x1800087b7  movzx   ecx, word ptr [rbx+20h]
0x1800087bb  xor     edx, edx
0x1800087bd  div     ecx
0x1800087bf  mov     [rbx+22h], dx
0x1800087c3  mov     rax, [rbx+8]
0x1800087c7  mov     r8d, 1
0x1800087cd  lock xadd [rax], r8d
0x1800087d2  inc     r8d; unsigned int
0x1800087d5  movzx   eax, dx
0x1800087d8  lea     rcx, [rax+rax*4]
0x1800087dc  shl     rcx, 4
0x1800087e0  add     rcx, r9; this
0x1800087e3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800087e6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800087eb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800087f5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800087fc  add     rsp, 20h
0x180008800  pop     r14
0x180008802  pop     rdi
0x180008803  pop     rsi
0x180008804  pop     rbp
0x180008805  pop     rbx
0x180008806  retn
```
