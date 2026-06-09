# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140003150`
- end: `0x140003356`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140003150`
- `0x140003848`
- `0x14000392c`
- `0x140004198`
- `0x1400044e0`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000317a`
- `KERNEL32!GetCurrentThreadId` at `0x14000323b`
- `KERNEL32!GetCurrentThreadId` at `0x14000317a`
- `KERNEL32!GetCurrentThreadId` at `0x14000323b`

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
0x140003150  push    rbx
0x140003152  push    rbp
0x140003153  push    rsi
0x140003154  push    rdi
0x140003155  push    r14
0x140003157  sub     rsp, 20h
0x14000315b  mov     byte ptr [rdx], 0
0x14000315e  xor     bpl, bpl
0x140003161  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140003168  mov     r14, r8
0x14000316b  mov     rsi, rdx
0x14000316e  mov     rdi, rcx
0x140003171  test    rbx, rbx
0x140003174  jz      loc_140003210
0x14000317a  call    cs:__imp_GetCurrentThreadId
0x140003180  mov     r8d, eax
0x140003183  mov     r9d, eax
0x140003186  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003190  shr     r8, 2
0x140003194  mul     r8
0x140003197  shr     rdx, 3
0x14000319b  lea     rcx, [rdx+rdx*4]
0x14000319f  add     rcx, rcx
0x1400031a2  sub     r8, rcx
0x1400031a5  mov     rbx, [rbx+r8*8]
0x1400031a9  jmp     short loc_1400031B4
0x1400031ab  cmp     [rbx], r9d
0x1400031ae  jz      short loc_14000322B
0x1400031b0  mov     rbx, [rbx+8]
0x1400031b4  test    rbx, rbx
0x1400031b7  jnz     short loc_1400031AB
0x1400031b9  test    rbx, rbx
0x1400031bc  jz      short loc_140003210
0x1400031be  cmp     qword ptr [rbx], 0
0x1400031c2  jz      short loc_140003210
0x1400031c4  mov     [rsi], bpl
0x1400031c7  mov     r9, r14; unsigned __int64
0x1400031ca  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1400031cd  mov     r8, rsi; char *
0x1400031d0  mov     rcx, rdi; struct wil::FailureInfo *
0x1400031d3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400031d8  test    al, al
0x1400031da  jz      short loc_1400031E0
0x1400031dc  mov     [rdi+48h], rsi
0x1400031e0  mov     rbx, [rbx]
0x1400031e3  mov     al, [rbx+28h]
0x1400031e6  mov     byte ptr [rbx+28h], 1
0x1400031ea  test    al, al
0x1400031ec  jnz     short loc_140003207
0x1400031ee  mov     rcx, [rbx+8]
0x1400031f2  mov     rdx, rdi
0x1400031f5  mov     rax, [rcx]
0x1400031f8  mov     rax, [rax]
0x1400031fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003200  or      bpl, al
0x140003203  mov     byte ptr [rbx+28h], 0
0x140003207  mov     rbx, [rbx+10h]
0x14000320b  test    rbx, rbx
0x14000320e  jnz     short loc_1400031E3
0x140003210  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140003217  test    rax, rax
0x14000321a  jz      short loc_14000323B
0x14000321c  test    bpl, bpl
0x14000321f  jnz     short loc_140003231
0x140003221  test    byte ptr [rdi+4], 2
0x140003225  jnz     short loc_140003231
0x140003227  xor     ecx, ecx
0x140003229  jmp     short loc_140003233
0x14000322b  add     rbx, 10h
0x14000322f  jmp     short loc_1400031B9
0x140003231  mov     cl, 1
0x140003233  mov     rdx, rdi
0x140003236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000323b  call    cs:__imp_GetCurrentThreadId
0x140003241  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003247  cmp     ecx, eax
0x140003249  jz      loc_14000334B
0x14000324f  mov     ecx, 1
0x140003254  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000325c  inc     ecx; this
0x14000325e  cmp     ecx, 4
0x140003261  jge     loc_140003344
0x140003267  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000326d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140003272  mov     rbx, rax
0x140003275  test    rax, rax
0x140003278  jz      loc_14000333A
0x14000327e  cmp     qword ptr [rax+18h], 0
0x140003283  mov     ebp, 50h ; 'P'
0x140003288  mov     esi, [rax+10h]
0x14000328b  jnz     short loc_1400032C2
0x14000328d  test    esi, esi
0x14000328f  jz      short loc_1400032C2
0x140003291  mov     edx, 190h; dwBytes
0x140003296  lea     ecx, [rbp-48h]; dwFlags
0x140003299  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000329e  mov     [rbx+18h], rax
0x1400032a2  test    rax, rax
0x1400032a5  jz      short loc_1400032C2
0x1400032a7  mov     dword ptr [rbx+20h], 5
0x1400032ae  lea     rcx, [rax+190h]
0x1400032b5  jmp     short loc_1400032BD
0x1400032b7  mov     [rax], bp
0x1400032ba  add     rax, rbp
0x1400032bd  cmp     rax, rcx
0x1400032c0  jnz     short loc_1400032B7
0x1400032c2  mov     r9, [rbx+18h]
0x1400032c6  test    r9, r9
0x1400032c9  jz      short loc_14000333A
0x1400032cb  test    esi, esi
0x1400032cd  jz      short loc_140003300
0x1400032cf  movzx   eax, word ptr [rbx+20h]
0x1400032d3  mov     rcx, r9
0x1400032d6  lea     rdx, [rax+rax*4]
0x1400032da  shl     rdx, 4
0x1400032de  add     rdx, r9
0x1400032e1  cmp     r9, rdx
0x1400032e4  jz      short loc_140003300
0x1400032e6  mov     r8d, [rbx+10h]
0x1400032ea  cmp     [rcx+4], r8d
0x1400032ee  jbe     short loc_1400032F8
0x1400032f0  mov     eax, [rdi+8]
0x1400032f3  cmp     [rcx+8], eax
0x1400032f6  jz      short loc_14000333A
0x1400032f8  add     rcx, rbp
0x1400032fb  cmp     rcx, rdx
0x1400032fe  jnz     short loc_1400032EA
0x140003300  movzx   eax, word ptr [rbx+22h]
0x140003304  xor     edx, edx
0x140003306  movzx   ecx, word ptr [rbx+20h]
0x14000330a  inc     eax
0x14000330c  div     ecx
0x14000330e  mov     rax, [rbx+8]
0x140003312  mov     r8d, 1
0x140003318  mov     [rbx+22h], dx
0x14000331c  lock xadd [rax], r8d
0x140003321  movzx   eax, dx
0x140003324  inc     r8d; unsigned int
0x140003327  mov     rdx, rdi; struct wil::FailureInfo *
0x14000332a  lea     rcx, [rax+rax*4]
0x14000332e  shl     rcx, 4
0x140003332  add     rcx, r9; this
0x140003335  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000333a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003344  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000334b  add     rsp, 20h
0x14000334f  pop     r14
0x140003351  pop     rdi
0x140003352  pop     rsi
0x140003353  pop     rbp
0x140003354  pop     rbx
0x140003355  retn
```
