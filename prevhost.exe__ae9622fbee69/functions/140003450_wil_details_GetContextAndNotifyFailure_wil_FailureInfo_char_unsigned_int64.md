# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140003450`
- end: `0x140003656`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140003450`
- `0x140003b48`
- `0x140003c2c`
- `0x1400047f8`
- `0x140004de0`
- `0x140006010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000347a`
- `KERNEL32!GetCurrentThreadId` at `0x14000353b`
- `KERNEL32!GetCurrentThreadId` at `0x14000347a`
- `KERNEL32!GetCurrentThreadId` at `0x14000353b`

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
0x140003450  push    rbx
0x140003452  push    rbp
0x140003453  push    rsi
0x140003454  push    rdi
0x140003455  push    r14
0x140003457  sub     rsp, 20h
0x14000345b  mov     byte ptr [rdx], 0
0x14000345e  xor     bpl, bpl
0x140003461  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140003468  mov     r14, r8
0x14000346b  mov     rsi, rdx
0x14000346e  mov     rdi, rcx
0x140003471  test    rbx, rbx
0x140003474  jz      loc_140003510
0x14000347a  call    cs:__imp_GetCurrentThreadId
0x140003480  mov     r8d, eax
0x140003483  mov     r9d, eax
0x140003486  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003490  shr     r8, 2
0x140003494  mul     r8
0x140003497  shr     rdx, 3
0x14000349b  lea     rcx, [rdx+rdx*4]
0x14000349f  add     rcx, rcx
0x1400034a2  sub     r8, rcx
0x1400034a5  mov     rbx, [rbx+r8*8]
0x1400034a9  jmp     short loc_1400034B4
0x1400034ab  cmp     [rbx], r9d
0x1400034ae  jz      short loc_14000352B
0x1400034b0  mov     rbx, [rbx+8]
0x1400034b4  test    rbx, rbx
0x1400034b7  jnz     short loc_1400034AB
0x1400034b9  test    rbx, rbx
0x1400034bc  jz      short loc_140003510
0x1400034be  cmp     qword ptr [rbx], 0
0x1400034c2  jz      short loc_140003510
0x1400034c4  mov     [rsi], bpl
0x1400034c7  mov     r9, r14; unsigned __int64
0x1400034ca  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1400034cd  mov     r8, rsi; char *
0x1400034d0  mov     rcx, rdi; struct wil::FailureInfo *
0x1400034d3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400034d8  test    al, al
0x1400034da  jz      short loc_1400034E0
0x1400034dc  mov     [rdi+48h], rsi
0x1400034e0  mov     rbx, [rbx]
0x1400034e3  mov     al, [rbx+28h]
0x1400034e6  mov     byte ptr [rbx+28h], 1
0x1400034ea  test    al, al
0x1400034ec  jnz     short loc_140003507
0x1400034ee  mov     rcx, [rbx+8]
0x1400034f2  mov     rdx, rdi
0x1400034f5  mov     rax, [rcx]
0x1400034f8  mov     rax, [rax]
0x1400034fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003500  or      bpl, al
0x140003503  mov     byte ptr [rbx+28h], 0
0x140003507  mov     rbx, [rbx+10h]
0x14000350b  test    rbx, rbx
0x14000350e  jnz     short loc_1400034E3
0x140003510  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140003517  test    rax, rax
0x14000351a  jz      short loc_14000353B
0x14000351c  test    bpl, bpl
0x14000351f  jnz     short loc_140003531
0x140003521  test    byte ptr [rdi+4], 2
0x140003525  jnz     short loc_140003531
0x140003527  xor     ecx, ecx
0x140003529  jmp     short loc_140003533
0x14000352b  add     rbx, 10h
0x14000352f  jmp     short loc_1400034B9
0x140003531  mov     cl, 1
0x140003533  mov     rdx, rdi
0x140003536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000353b  call    cs:__imp_GetCurrentThreadId
0x140003541  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003547  cmp     ecx, eax
0x140003549  jz      loc_14000364B
0x14000354f  mov     ecx, 1
0x140003554  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000355c  inc     ecx; this
0x14000355e  cmp     ecx, 4
0x140003561  jge     loc_140003644
0x140003567  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000356d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140003572  mov     rbx, rax
0x140003575  test    rax, rax
0x140003578  jz      loc_14000363A
0x14000357e  cmp     qword ptr [rax+18h], 0
0x140003583  mov     ebp, 50h ; 'P'
0x140003588  mov     esi, [rax+10h]
0x14000358b  jnz     short loc_1400035C2
0x14000358d  test    esi, esi
0x14000358f  jz      short loc_1400035C2
0x140003591  mov     edx, 190h; dwBytes
0x140003596  lea     ecx, [rbp-48h]; dwFlags
0x140003599  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000359e  mov     [rbx+18h], rax
0x1400035a2  test    rax, rax
0x1400035a5  jz      short loc_1400035C2
0x1400035a7  mov     dword ptr [rbx+20h], 5
0x1400035ae  lea     rcx, [rax+190h]
0x1400035b5  jmp     short loc_1400035BD
0x1400035b7  mov     [rax], bp
0x1400035ba  add     rax, rbp
0x1400035bd  cmp     rax, rcx
0x1400035c0  jnz     short loc_1400035B7
0x1400035c2  mov     r9, [rbx+18h]
0x1400035c6  test    r9, r9
0x1400035c9  jz      short loc_14000363A
0x1400035cb  test    esi, esi
0x1400035cd  jz      short loc_140003600
0x1400035cf  movzx   eax, word ptr [rbx+20h]
0x1400035d3  mov     rcx, r9
0x1400035d6  lea     rdx, [rax+rax*4]
0x1400035da  shl     rdx, 4
0x1400035de  add     rdx, r9
0x1400035e1  cmp     r9, rdx
0x1400035e4  jz      short loc_140003600
0x1400035e6  mov     r8d, [rbx+10h]
0x1400035ea  cmp     [rcx+4], r8d
0x1400035ee  jbe     short loc_1400035F8
0x1400035f0  mov     eax, [rdi+8]
0x1400035f3  cmp     [rcx+8], eax
0x1400035f6  jz      short loc_14000363A
0x1400035f8  add     rcx, rbp
0x1400035fb  cmp     rcx, rdx
0x1400035fe  jnz     short loc_1400035EA
0x140003600  movzx   eax, word ptr [rbx+22h]
0x140003604  xor     edx, edx
0x140003606  movzx   ecx, word ptr [rbx+20h]
0x14000360a  inc     eax
0x14000360c  div     ecx
0x14000360e  mov     rax, [rbx+8]
0x140003612  mov     r8d, 1
0x140003618  mov     [rbx+22h], dx
0x14000361c  lock xadd [rax], r8d
0x140003621  movzx   eax, dx
0x140003624  inc     r8d; unsigned int
0x140003627  mov     rdx, rdi; struct wil::FailureInfo *
0x14000362a  lea     rcx, [rax+rax*4]
0x14000362e  shl     rcx, 4
0x140003632  add     rcx, r9; this
0x140003635  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000363a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003644  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000364b  add     rsp, 20h
0x14000364f  pop     r14
0x140003651  pop     rdi
0x140003652  pop     rsi
0x140003653  pop     rbp
0x140003654  pop     rbx
0x140003655  retn
```
