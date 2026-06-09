# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003750`
- end: `0x180003957`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003750`
- `0x180003e4c`
- `0x180003f30`
- `0x1800047a8`
- `0x180004b10`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000377a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000383c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000377a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000383c`

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
0x180003750  push    rbx
0x180003752  push    rbp
0x180003753  push    rsi
0x180003754  push    rdi
0x180003755  push    r14
0x180003757  sub     rsp, 20h
0x18000375b  mov     r14, r8
0x18000375e  mov     rsi, rdx
0x180003761  mov     rdi, rcx
0x180003764  mov     byte ptr [rdx], 0
0x180003767  xor     bpl, bpl
0x18000376a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003771  test    rbx, rbx
0x180003774  jz      loc_180003810
0x18000377a  call    cs:__imp_GetCurrentThreadId
0x180003780  mov     r9d, eax
0x180003783  mov     r8d, eax
0x180003786  shr     r8, 2
0x18000378a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003794  mul     r8
0x180003797  shr     rdx, 3
0x18000379b  lea     rcx, [rdx+rdx*4]
0x18000379f  add     rcx, rcx
0x1800037a2  sub     r8, rcx
0x1800037a5  mov     rbx, [rbx+r8*8]
0x1800037a9  jmp     short loc_1800037B4
0x1800037ab  cmp     [rbx], r9d
0x1800037ae  jz      short loc_18000382B
0x1800037b0  mov     rbx, [rbx+8]
0x1800037b4  test    rbx, rbx
0x1800037b7  jnz     short loc_1800037AB
0x1800037b9  test    rbx, rbx
0x1800037bc  jz      short loc_180003810
0x1800037be  cmp     qword ptr [rbx], 0
0x1800037c2  jz      short loc_180003810
0x1800037c4  mov     [rsi], bpl
0x1800037c7  mov     r9, r14; unsigned __int64
0x1800037ca  mov     r8, rsi; char *
0x1800037cd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800037d0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800037d3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800037d8  test    al, al
0x1800037da  jz      short loc_1800037E0
0x1800037dc  mov     [rdi+48h], rsi
0x1800037e0  mov     rbx, [rbx]
0x1800037e3  mov     al, [rbx+28h]
0x1800037e6  mov     byte ptr [rbx+28h], 1
0x1800037ea  test    al, al
0x1800037ec  jnz     short loc_180003807
0x1800037ee  mov     rcx, [rbx+8]
0x1800037f2  mov     rax, [rcx]
0x1800037f5  mov     rdx, rdi
0x1800037f8  mov     rax, [rax]
0x1800037fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003800  or      bpl, al
0x180003803  mov     byte ptr [rbx+28h], 0
0x180003807  mov     rbx, [rbx+10h]
0x18000380b  test    rbx, rbx
0x18000380e  jnz     short loc_1800037E3
0x180003810  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003817  test    rax, rax
0x18000381a  jz      short loc_18000383C
0x18000381c  test    bpl, bpl
0x18000381f  jnz     short loc_180003831
0x180003821  test    byte ptr [rdi+4], 2
0x180003825  jnz     short loc_180003831
0x180003827  xor     ecx, ecx
0x180003829  jmp     short loc_180003833
0x18000382b  add     rbx, 10h
0x18000382f  jmp     short loc_1800037B9
0x180003831  mov     cl, 1
0x180003833  mov     rdx, rdi
0x180003836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000383b  nop
0x18000383c  call    cs:__imp_GetCurrentThreadId
0x180003842  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003848  cmp     ecx, eax
0x18000384a  jz      loc_18000394C
0x180003850  mov     ecx, 1
0x180003855  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000385d  inc     ecx; this
0x18000385f  cmp     ecx, 4
0x180003862  jge     loc_180003945
0x180003868  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000386e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180003873  mov     rbx, rax
0x180003876  test    rax, rax
0x180003879  jz      loc_18000393B
0x18000387f  mov     esi, [rax+10h]
0x180003882  mov     ebp, 50h ; 'P'
0x180003887  cmp     qword ptr [rax+18h], 0
0x18000388c  jnz     short loc_1800038C3
0x18000388e  test    esi, esi
0x180003890  jz      short loc_1800038C3
0x180003892  mov     edx, 190h; dwBytes
0x180003897  lea     ecx, [rbp-48h]; dwFlags
0x18000389a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000389f  mov     [rbx+18h], rax
0x1800038a3  test    rax, rax
0x1800038a6  jz      short loc_1800038C3
0x1800038a8  mov     dword ptr [rbx+20h], 5
0x1800038af  lea     rcx, [rax+190h]
0x1800038b6  jmp     short loc_1800038BE
0x1800038b8  mov     [rax], bp
0x1800038bb  add     rax, rbp
0x1800038be  cmp     rax, rcx
0x1800038c1  jnz     short loc_1800038B8
0x1800038c3  mov     r9, [rbx+18h]
0x1800038c7  test    r9, r9
0x1800038ca  jz      short loc_18000393B
0x1800038cc  test    esi, esi
0x1800038ce  jz      short loc_180003901
0x1800038d0  mov     rcx, r9
0x1800038d3  movzx   eax, word ptr [rbx+20h]
0x1800038d7  lea     rdx, [rax+rax*4]
0x1800038db  shl     rdx, 4
0x1800038df  add     rdx, r9
0x1800038e2  cmp     r9, rdx
0x1800038e5  jz      short loc_180003901
0x1800038e7  mov     r8d, [rbx+10h]
0x1800038eb  cmp     [rcx+4], r8d
0x1800038ef  jbe     short loc_1800038F9
0x1800038f1  mov     eax, [rdi+8]
0x1800038f4  cmp     [rcx+8], eax
0x1800038f7  jz      short loc_18000393B
0x1800038f9  add     rcx, rbp
0x1800038fc  cmp     rcx, rdx
0x1800038ff  jnz     short loc_1800038EB
0x180003901  movzx   eax, word ptr [rbx+22h]
0x180003905  inc     eax
0x180003907  movzx   ecx, word ptr [rbx+20h]
0x18000390b  xor     edx, edx
0x18000390d  div     ecx
0x18000390f  mov     [rbx+22h], dx
0x180003913  mov     rax, [rbx+8]
0x180003917  mov     r8d, 1
0x18000391d  lock xadd [rax], r8d
0x180003922  inc     r8d; unsigned int
0x180003925  movzx   eax, dx
0x180003928  lea     rcx, [rax+rax*4]
0x18000392c  shl     rcx, 4
0x180003930  add     rcx, r9; this
0x180003933  mov     rdx, rdi; struct wil::FailureInfo *
0x180003936  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000393b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003945  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000394c  add     rsp, 20h
0x180003950  pop     r14
0x180003952  pop     rdi
0x180003953  pop     rsi
0x180003954  pop     rbp
0x180003955  pop     rbx
0x180003956  retn
```
