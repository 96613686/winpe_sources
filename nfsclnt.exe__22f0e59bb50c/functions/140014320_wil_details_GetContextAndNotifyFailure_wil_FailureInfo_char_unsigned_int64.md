# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140014320`
- end: `0x140014526`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140014320`
- `0x140014a18`
- `0x140014afc`
- `0x140015488`
- `0x140016818`
- `0x140019010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14001434a`
- `KERNEL32!GetCurrentThreadId` at `0x14001440b`
- `KERNEL32!GetCurrentThreadId` at `0x14001434a`
- `KERNEL32!GetCurrentThreadId` at `0x14001440b`

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
0x140014320  push    rbx
0x140014322  push    rbp
0x140014323  push    rsi
0x140014324  push    rdi
0x140014325  push    r14
0x140014327  sub     rsp, 20h
0x14001432b  mov     byte ptr [rdx], 0
0x14001432e  xor     bpl, bpl
0x140014331  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140014338  mov     r14, r8
0x14001433b  mov     rsi, rdx
0x14001433e  mov     rdi, rcx
0x140014341  test    rbx, rbx
0x140014344  jz      loc_1400143E0
0x14001434a  call    cs:__imp_GetCurrentThreadId
0x140014350  mov     r8d, eax
0x140014353  mov     r9d, eax
0x140014356  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140014360  shr     r8, 2
0x140014364  mul     r8
0x140014367  shr     rdx, 3
0x14001436b  lea     rcx, [rdx+rdx*4]
0x14001436f  add     rcx, rcx
0x140014372  sub     r8, rcx
0x140014375  mov     rbx, [rbx+r8*8]
0x140014379  jmp     short loc_140014384
0x14001437b  cmp     [rbx], r9d
0x14001437e  jz      short loc_1400143FB
0x140014380  mov     rbx, [rbx+8]
0x140014384  test    rbx, rbx
0x140014387  jnz     short loc_14001437B
0x140014389  test    rbx, rbx
0x14001438c  jz      short loc_1400143E0
0x14001438e  cmp     qword ptr [rbx], 0
0x140014392  jz      short loc_1400143E0
0x140014394  mov     [rsi], bpl
0x140014397  mov     r9, r14; unsigned __int64
0x14001439a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x14001439d  mov     r8, rsi; char *
0x1400143a0  mov     rcx, rdi; struct wil::FailureInfo *
0x1400143a3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400143a8  test    al, al
0x1400143aa  jz      short loc_1400143B0
0x1400143ac  mov     [rdi+48h], rsi
0x1400143b0  mov     rbx, [rbx]
0x1400143b3  mov     al, [rbx+28h]
0x1400143b6  mov     byte ptr [rbx+28h], 1
0x1400143ba  test    al, al
0x1400143bc  jnz     short loc_1400143D7
0x1400143be  mov     rcx, [rbx+8]
0x1400143c2  mov     rdx, rdi
0x1400143c5  mov     rax, [rcx]
0x1400143c8  mov     rax, [rax]
0x1400143cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400143d0  or      bpl, al
0x1400143d3  mov     byte ptr [rbx+28h], 0
0x1400143d7  mov     rbx, [rbx+10h]
0x1400143db  test    rbx, rbx
0x1400143de  jnz     short loc_1400143B3
0x1400143e0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400143e7  test    rax, rax
0x1400143ea  jz      short loc_14001440B
0x1400143ec  test    bpl, bpl
0x1400143ef  jnz     short loc_140014401
0x1400143f1  test    byte ptr [rdi+4], 2
0x1400143f5  jnz     short loc_140014401
0x1400143f7  xor     ecx, ecx
0x1400143f9  jmp     short loc_140014403
0x1400143fb  add     rbx, 10h
0x1400143ff  jmp     short loc_140014389
0x140014401  mov     cl, 1
0x140014403  mov     rdx, rdi
0x140014406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001440b  call    cs:__imp_GetCurrentThreadId
0x140014411  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140014417  cmp     ecx, eax
0x140014419  jz      loc_14001451B
0x14001441f  mov     ecx, 1
0x140014424  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14001442c  inc     ecx; this
0x14001442e  cmp     ecx, 4
0x140014431  jge     loc_140014514
0x140014437  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14001443d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140014442  mov     rbx, rax
0x140014445  test    rax, rax
0x140014448  jz      loc_14001450A
0x14001444e  cmp     qword ptr [rax+18h], 0
0x140014453  mov     ebp, 50h ; 'P'
0x140014458  mov     esi, [rax+10h]
0x14001445b  jnz     short loc_140014492
0x14001445d  test    esi, esi
0x14001445f  jz      short loc_140014492
0x140014461  mov     edx, 190h; dwBytes
0x140014466  lea     ecx, [rbp-48h]; dwFlags
0x140014469  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14001446e  mov     [rbx+18h], rax
0x140014472  test    rax, rax
0x140014475  jz      short loc_140014492
0x140014477  mov     dword ptr [rbx+20h], 5
0x14001447e  lea     rcx, [rax+190h]
0x140014485  jmp     short loc_14001448D
0x140014487  mov     [rax], bp
0x14001448a  add     rax, rbp
0x14001448d  cmp     rax, rcx
0x140014490  jnz     short loc_140014487
0x140014492  mov     r9, [rbx+18h]
0x140014496  test    r9, r9
0x140014499  jz      short loc_14001450A
0x14001449b  test    esi, esi
0x14001449d  jz      short loc_1400144D0
0x14001449f  movzx   eax, word ptr [rbx+20h]
0x1400144a3  mov     rcx, r9
0x1400144a6  lea     rdx, [rax+rax*4]
0x1400144aa  shl     rdx, 4
0x1400144ae  add     rdx, r9
0x1400144b1  cmp     r9, rdx
0x1400144b4  jz      short loc_1400144D0
0x1400144b6  mov     r8d, [rbx+10h]
0x1400144ba  cmp     [rcx+4], r8d
0x1400144be  jbe     short loc_1400144C8
0x1400144c0  mov     eax, [rdi+8]
0x1400144c3  cmp     [rcx+8], eax
0x1400144c6  jz      short loc_14001450A
0x1400144c8  add     rcx, rbp
0x1400144cb  cmp     rcx, rdx
0x1400144ce  jnz     short loc_1400144BA
0x1400144d0  movzx   eax, word ptr [rbx+22h]
0x1400144d4  xor     edx, edx
0x1400144d6  movzx   ecx, word ptr [rbx+20h]
0x1400144da  inc     eax
0x1400144dc  div     ecx
0x1400144de  mov     rax, [rbx+8]
0x1400144e2  mov     r8d, 1
0x1400144e8  mov     [rbx+22h], dx
0x1400144ec  lock xadd [rax], r8d
0x1400144f1  movzx   eax, dx
0x1400144f4  inc     r8d; unsigned int
0x1400144f7  mov     rdx, rdi; struct wil::FailureInfo *
0x1400144fa  lea     rcx, [rax+rax*4]
0x1400144fe  shl     rcx, 4
0x140014502  add     rcx, r9; this
0x140014505  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14001450a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140014514  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14001451b  add     rsp, 20h
0x14001451f  pop     r14
0x140014521  pop     rdi
0x140014522  pop     rsi
0x140014523  pop     rbp
0x140014524  pop     rbx
0x140014525  retn
```
