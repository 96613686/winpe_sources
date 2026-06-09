# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140003530`
- end: `0x140003737`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140003530`
- `0x140003c2c`
- `0x140003d10`
- `0x140004624`
- `0x140004a04`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000355a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000361c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000355a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000361c`

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
0x140003530  push    rbx
0x140003532  push    rbp
0x140003533  push    rsi
0x140003534  push    rdi
0x140003535  push    r14
0x140003537  sub     rsp, 20h
0x14000353b  mov     r14, r8
0x14000353e  mov     rsi, rdx
0x140003541  mov     rdi, rcx
0x140003544  mov     byte ptr [rdx], 0
0x140003547  xor     bpl, bpl
0x14000354a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140003551  test    rbx, rbx
0x140003554  jz      loc_1400035F0
0x14000355a  call    cs:__imp_GetCurrentThreadId
0x140003560  mov     r9d, eax
0x140003563  mov     r8d, eax
0x140003566  shr     r8, 2
0x14000356a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140003574  mul     r8
0x140003577  shr     rdx, 3
0x14000357b  lea     rcx, [rdx+rdx*4]
0x14000357f  add     rcx, rcx
0x140003582  sub     r8, rcx
0x140003585  mov     rbx, [rbx+r8*8]
0x140003589  jmp     short loc_140003594
0x14000358b  cmp     [rbx], r9d
0x14000358e  jz      short loc_14000360B
0x140003590  mov     rbx, [rbx+8]
0x140003594  test    rbx, rbx
0x140003597  jnz     short loc_14000358B
0x140003599  test    rbx, rbx
0x14000359c  jz      short loc_1400035F0
0x14000359e  cmp     qword ptr [rbx], 0
0x1400035a2  jz      short loc_1400035F0
0x1400035a4  mov     [rsi], bpl
0x1400035a7  mov     r9, r14; unsigned __int64
0x1400035aa  mov     r8, rsi; char *
0x1400035ad  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1400035b0  mov     rcx, rdi; struct wil::FailureInfo *
0x1400035b3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400035b8  test    al, al
0x1400035ba  jz      short loc_1400035C0
0x1400035bc  mov     [rdi+48h], rsi
0x1400035c0  mov     rbx, [rbx]
0x1400035c3  mov     al, [rbx+28h]
0x1400035c6  mov     byte ptr [rbx+28h], 1
0x1400035ca  test    al, al
0x1400035cc  jnz     short loc_1400035E7
0x1400035ce  mov     rcx, [rbx+8]
0x1400035d2  mov     rax, [rcx]
0x1400035d5  mov     rdx, rdi
0x1400035d8  mov     rax, [rax]
0x1400035db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400035e0  or      bpl, al
0x1400035e3  mov     byte ptr [rbx+28h], 0
0x1400035e7  mov     rbx, [rbx+10h]
0x1400035eb  test    rbx, rbx
0x1400035ee  jnz     short loc_1400035C3
0x1400035f0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400035f7  test    rax, rax
0x1400035fa  jz      short loc_14000361C
0x1400035fc  test    bpl, bpl
0x1400035ff  jnz     short loc_140003611
0x140003601  test    byte ptr [rdi+4], 2
0x140003605  jnz     short loc_140003611
0x140003607  xor     ecx, ecx
0x140003609  jmp     short loc_140003613
0x14000360b  add     rbx, 10h
0x14000360f  jmp     short loc_140003599
0x140003611  mov     cl, 1
0x140003613  mov     rdx, rdi
0x140003616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000361b  nop
0x14000361c  call    cs:__imp_GetCurrentThreadId
0x140003622  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003628  cmp     ecx, eax
0x14000362a  jz      loc_14000372C
0x140003630  mov     ecx, 1
0x140003635  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000363d  inc     ecx; this
0x14000363f  cmp     ecx, 4
0x140003642  jge     loc_140003725
0x140003648  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000364e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140003653  mov     rbx, rax
0x140003656  test    rax, rax
0x140003659  jz      loc_14000371B
0x14000365f  mov     esi, [rax+10h]
0x140003662  mov     ebp, 50h ; 'P'
0x140003667  cmp     qword ptr [rax+18h], 0
0x14000366c  jnz     short loc_1400036A3
0x14000366e  test    esi, esi
0x140003670  jz      short loc_1400036A3
0x140003672  mov     edx, 190h; dwBytes
0x140003677  lea     ecx, [rbp-48h]; dwFlags
0x14000367a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000367f  mov     [rbx+18h], rax
0x140003683  test    rax, rax
0x140003686  jz      short loc_1400036A3
0x140003688  mov     dword ptr [rbx+20h], 5
0x14000368f  lea     rcx, [rax+190h]
0x140003696  jmp     short loc_14000369E
0x140003698  mov     [rax], bp
0x14000369b  add     rax, rbp
0x14000369e  cmp     rax, rcx
0x1400036a1  jnz     short loc_140003698
0x1400036a3  mov     r9, [rbx+18h]
0x1400036a7  test    r9, r9
0x1400036aa  jz      short loc_14000371B
0x1400036ac  test    esi, esi
0x1400036ae  jz      short loc_1400036E1
0x1400036b0  mov     rcx, r9
0x1400036b3  movzx   eax, word ptr [rbx+20h]
0x1400036b7  lea     rdx, [rax+rax*4]
0x1400036bb  shl     rdx, 4
0x1400036bf  add     rdx, r9
0x1400036c2  cmp     r9, rdx
0x1400036c5  jz      short loc_1400036E1
0x1400036c7  mov     r8d, [rbx+10h]
0x1400036cb  cmp     [rcx+4], r8d
0x1400036cf  jbe     short loc_1400036D9
0x1400036d1  mov     eax, [rdi+8]
0x1400036d4  cmp     [rcx+8], eax
0x1400036d7  jz      short loc_14000371B
0x1400036d9  add     rcx, rbp
0x1400036dc  cmp     rcx, rdx
0x1400036df  jnz     short loc_1400036CB
0x1400036e1  movzx   eax, word ptr [rbx+22h]
0x1400036e5  inc     eax
0x1400036e7  movzx   ecx, word ptr [rbx+20h]
0x1400036eb  xor     edx, edx
0x1400036ed  div     ecx
0x1400036ef  mov     [rbx+22h], dx
0x1400036f3  mov     rax, [rbx+8]
0x1400036f7  mov     r8d, 1
0x1400036fd  lock xadd [rax], r8d
0x140003702  inc     r8d; unsigned int
0x140003705  movzx   eax, dx
0x140003708  lea     rcx, [rax+rax*4]
0x14000370c  shl     rcx, 4
0x140003710  add     rcx, r9; this
0x140003713  mov     rdx, rdi; struct wil::FailureInfo *
0x140003716  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000371b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140003725  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000372c  add     rsp, 20h
0x140003730  pop     r14
0x140003732  pop     rdi
0x140003733  pop     rsi
0x140003734  pop     rbp
0x140003735  pop     rbx
0x140003736  retn
```
