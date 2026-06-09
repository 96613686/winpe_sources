# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003760`
- end: `0x180003967`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003760`
- `0x180003e5c`
- `0x180003f40`
- `0x1800047a8`
- `0x180004b10`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000378a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000384c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000378a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000384c`

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
0x180003760  push    rbx
0x180003762  push    rbp
0x180003763  push    rsi
0x180003764  push    rdi
0x180003765  push    r14
0x180003767  sub     rsp, 20h
0x18000376b  mov     r14, r8
0x18000376e  mov     rsi, rdx
0x180003771  mov     rdi, rcx
0x180003774  mov     byte ptr [rdx], 0
0x180003777  xor     bpl, bpl
0x18000377a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003781  test    rbx, rbx
0x180003784  jz      loc_180003820
0x18000378a  call    cs:__imp_GetCurrentThreadId
0x180003790  mov     r9d, eax
0x180003793  mov     r8d, eax
0x180003796  shr     r8, 2
0x18000379a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800037a4  mul     r8
0x1800037a7  shr     rdx, 3
0x1800037ab  lea     rcx, [rdx+rdx*4]
0x1800037af  add     rcx, rcx
0x1800037b2  sub     r8, rcx
0x1800037b5  mov     rbx, [rbx+r8*8]
0x1800037b9  jmp     short loc_1800037C4
0x1800037bb  cmp     [rbx], r9d
0x1800037be  jz      short loc_18000383B
0x1800037c0  mov     rbx, [rbx+8]
0x1800037c4  test    rbx, rbx
0x1800037c7  jnz     short loc_1800037BB
0x1800037c9  test    rbx, rbx
0x1800037cc  jz      short loc_180003820
0x1800037ce  cmp     qword ptr [rbx], 0
0x1800037d2  jz      short loc_180003820
0x1800037d4  mov     [rsi], bpl
0x1800037d7  mov     r9, r14; unsigned __int64
0x1800037da  mov     r8, rsi; char *
0x1800037dd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800037e0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800037e3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800037e8  test    al, al
0x1800037ea  jz      short loc_1800037F0
0x1800037ec  mov     [rdi+48h], rsi
0x1800037f0  mov     rbx, [rbx]
0x1800037f3  mov     al, [rbx+28h]
0x1800037f6  mov     byte ptr [rbx+28h], 1
0x1800037fa  test    al, al
0x1800037fc  jnz     short loc_180003817
0x1800037fe  mov     rcx, [rbx+8]
0x180003802  mov     rax, [rcx]
0x180003805  mov     rdx, rdi
0x180003808  mov     rax, [rax]
0x18000380b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003810  or      bpl, al
0x180003813  mov     byte ptr [rbx+28h], 0
0x180003817  mov     rbx, [rbx+10h]
0x18000381b  test    rbx, rbx
0x18000381e  jnz     short loc_1800037F3
0x180003820  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003827  test    rax, rax
0x18000382a  jz      short loc_18000384C
0x18000382c  test    bpl, bpl
0x18000382f  jnz     short loc_180003841
0x180003831  test    byte ptr [rdi+4], 2
0x180003835  jnz     short loc_180003841
0x180003837  xor     ecx, ecx
0x180003839  jmp     short loc_180003843
0x18000383b  add     rbx, 10h
0x18000383f  jmp     short loc_1800037C9
0x180003841  mov     cl, 1
0x180003843  mov     rdx, rdi
0x180003846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000384b  nop
0x18000384c  call    cs:__imp_GetCurrentThreadId
0x180003852  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003858  cmp     ecx, eax
0x18000385a  jz      loc_18000395C
0x180003860  mov     ecx, 1
0x180003865  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000386d  inc     ecx; this
0x18000386f  cmp     ecx, 4
0x180003872  jge     loc_180003955
0x180003878  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000387e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180003883  mov     rbx, rax
0x180003886  test    rax, rax
0x180003889  jz      loc_18000394B
0x18000388f  mov     esi, [rax+10h]
0x180003892  mov     ebp, 50h ; 'P'
0x180003897  cmp     qword ptr [rax+18h], 0
0x18000389c  jnz     short loc_1800038D3
0x18000389e  test    esi, esi
0x1800038a0  jz      short loc_1800038D3
0x1800038a2  mov     edx, 190h; dwBytes
0x1800038a7  lea     ecx, [rbp-48h]; dwFlags
0x1800038aa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800038af  mov     [rbx+18h], rax
0x1800038b3  test    rax, rax
0x1800038b6  jz      short loc_1800038D3
0x1800038b8  mov     dword ptr [rbx+20h], 5
0x1800038bf  lea     rcx, [rax+190h]
0x1800038c6  jmp     short loc_1800038CE
0x1800038c8  mov     [rax], bp
0x1800038cb  add     rax, rbp
0x1800038ce  cmp     rax, rcx
0x1800038d1  jnz     short loc_1800038C8
0x1800038d3  mov     r9, [rbx+18h]
0x1800038d7  test    r9, r9
0x1800038da  jz      short loc_18000394B
0x1800038dc  test    esi, esi
0x1800038de  jz      short loc_180003911
0x1800038e0  mov     rcx, r9
0x1800038e3  movzx   eax, word ptr [rbx+20h]
0x1800038e7  lea     rdx, [rax+rax*4]
0x1800038eb  shl     rdx, 4
0x1800038ef  add     rdx, r9
0x1800038f2  cmp     r9, rdx
0x1800038f5  jz      short loc_180003911
0x1800038f7  mov     r8d, [rbx+10h]
0x1800038fb  cmp     [rcx+4], r8d
0x1800038ff  jbe     short loc_180003909
0x180003901  mov     eax, [rdi+8]
0x180003904  cmp     [rcx+8], eax
0x180003907  jz      short loc_18000394B
0x180003909  add     rcx, rbp
0x18000390c  cmp     rcx, rdx
0x18000390f  jnz     short loc_1800038FB
0x180003911  movzx   eax, word ptr [rbx+22h]
0x180003915  inc     eax
0x180003917  movzx   ecx, word ptr [rbx+20h]
0x18000391b  xor     edx, edx
0x18000391d  div     ecx
0x18000391f  mov     [rbx+22h], dx
0x180003923  mov     rax, [rbx+8]
0x180003927  mov     r8d, 1
0x18000392d  lock xadd [rax], r8d
0x180003932  inc     r8d; unsigned int
0x180003935  movzx   eax, dx
0x180003938  lea     rcx, [rax+rax*4]
0x18000393c  shl     rcx, 4
0x180003940  add     rcx, r9; this
0x180003943  mov     rdx, rdi; struct wil::FailureInfo *
0x180003946  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000394b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003955  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000395c  add     rsp, 20h
0x180003960  pop     r14
0x180003962  pop     rdi
0x180003963  pop     rsi
0x180003964  pop     rbp
0x180003965  pop     rbx
0x180003966  retn
```
