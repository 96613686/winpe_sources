# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003530`
- end: `0x180003737`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003530`
- `0x180003c2c`
- `0x180003d10`
- `0x180004588`
- `0x180004a80`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000355a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000361c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000355a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000361c`

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
0x180003530  push    rbx
0x180003532  push    rbp
0x180003533  push    rsi
0x180003534  push    rdi
0x180003535  push    r14
0x180003537  sub     rsp, 20h
0x18000353b  mov     r14, r8
0x18000353e  mov     rsi, rdx
0x180003541  mov     rdi, rcx
0x180003544  mov     byte ptr [rdx], 0
0x180003547  xor     bpl, bpl
0x18000354a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003551  test    rbx, rbx
0x180003554  jz      loc_1800035F0
0x18000355a  call    cs:__imp_GetCurrentThreadId
0x180003560  mov     r9d, eax
0x180003563  mov     r8d, eax
0x180003566  shr     r8, 2
0x18000356a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003574  mul     r8
0x180003577  shr     rdx, 3
0x18000357b  lea     rcx, [rdx+rdx*4]
0x18000357f  add     rcx, rcx
0x180003582  sub     r8, rcx
0x180003585  mov     rbx, [rbx+r8*8]
0x180003589  jmp     short loc_180003594
0x18000358b  cmp     [rbx], r9d
0x18000358e  jz      short loc_18000360B
0x180003590  mov     rbx, [rbx+8]
0x180003594  test    rbx, rbx
0x180003597  jnz     short loc_18000358B
0x180003599  test    rbx, rbx
0x18000359c  jz      short loc_1800035F0
0x18000359e  cmp     qword ptr [rbx], 0
0x1800035a2  jz      short loc_1800035F0
0x1800035a4  mov     [rsi], bpl
0x1800035a7  mov     r9, r14; unsigned __int64
0x1800035aa  mov     r8, rsi; char *
0x1800035ad  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1800035b0  mov     rcx, rdi; struct wil::FailureInfo *
0x1800035b3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1800035b8  test    al, al
0x1800035ba  jz      short loc_1800035C0
0x1800035bc  mov     [rdi+48h], rsi
0x1800035c0  mov     rbx, [rbx]
0x1800035c3  mov     al, [rbx+28h]
0x1800035c6  mov     byte ptr [rbx+28h], 1
0x1800035ca  test    al, al
0x1800035cc  jnz     short loc_1800035E7
0x1800035ce  mov     rcx, [rbx+8]
0x1800035d2  mov     rax, [rcx]
0x1800035d5  mov     rdx, rdi
0x1800035d8  mov     rax, [rax]
0x1800035db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035e0  or      bpl, al
0x1800035e3  mov     byte ptr [rbx+28h], 0
0x1800035e7  mov     rbx, [rbx+10h]
0x1800035eb  test    rbx, rbx
0x1800035ee  jnz     short loc_1800035C3
0x1800035f0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800035f7  test    rax, rax
0x1800035fa  jz      short loc_18000361C
0x1800035fc  test    bpl, bpl
0x1800035ff  jnz     short loc_180003611
0x180003601  test    byte ptr [rdi+4], 2
0x180003605  jnz     short loc_180003611
0x180003607  xor     ecx, ecx
0x180003609  jmp     short loc_180003613
0x18000360b  add     rbx, 10h
0x18000360f  jmp     short loc_180003599
0x180003611  mov     cl, 1
0x180003613  mov     rdx, rdi
0x180003616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000361b  nop
0x18000361c  call    cs:__imp_GetCurrentThreadId
0x180003622  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003628  cmp     ecx, eax
0x18000362a  jz      loc_18000372C
0x180003630  mov     ecx, 1
0x180003635  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000363d  inc     ecx; this
0x18000363f  cmp     ecx, 4
0x180003642  jge     loc_180003725
0x180003648  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000364e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180003653  mov     rbx, rax
0x180003656  test    rax, rax
0x180003659  jz      loc_18000371B
0x18000365f  mov     esi, [rax+10h]
0x180003662  mov     ebp, 50h ; 'P'
0x180003667  cmp     qword ptr [rax+18h], 0
0x18000366c  jnz     short loc_1800036A3
0x18000366e  test    esi, esi
0x180003670  jz      short loc_1800036A3
0x180003672  mov     edx, 190h; dwBytes
0x180003677  lea     ecx, [rbp-48h]; dwFlags
0x18000367a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000367f  mov     [rbx+18h], rax
0x180003683  test    rax, rax
0x180003686  jz      short loc_1800036A3
0x180003688  mov     dword ptr [rbx+20h], 5
0x18000368f  lea     rcx, [rax+190h]
0x180003696  jmp     short loc_18000369E
0x180003698  mov     [rax], bp
0x18000369b  add     rax, rbp
0x18000369e  cmp     rax, rcx
0x1800036a1  jnz     short loc_180003698
0x1800036a3  mov     r9, [rbx+18h]
0x1800036a7  test    r9, r9
0x1800036aa  jz      short loc_18000371B
0x1800036ac  test    esi, esi
0x1800036ae  jz      short loc_1800036E1
0x1800036b0  mov     rcx, r9
0x1800036b3  movzx   eax, word ptr [rbx+20h]
0x1800036b7  lea     rdx, [rax+rax*4]
0x1800036bb  shl     rdx, 4
0x1800036bf  add     rdx, r9
0x1800036c2  cmp     r9, rdx
0x1800036c5  jz      short loc_1800036E1
0x1800036c7  mov     r8d, [rbx+10h]
0x1800036cb  cmp     [rcx+4], r8d
0x1800036cf  jbe     short loc_1800036D9
0x1800036d1  mov     eax, [rdi+8]
0x1800036d4  cmp     [rcx+8], eax
0x1800036d7  jz      short loc_18000371B
0x1800036d9  add     rcx, rbp
0x1800036dc  cmp     rcx, rdx
0x1800036df  jnz     short loc_1800036CB
0x1800036e1  movzx   eax, word ptr [rbx+22h]
0x1800036e5  inc     eax
0x1800036e7  movzx   ecx, word ptr [rbx+20h]
0x1800036eb  xor     edx, edx
0x1800036ed  div     ecx
0x1800036ef  mov     [rbx+22h], dx
0x1800036f3  mov     rax, [rbx+8]
0x1800036f7  mov     r8d, 1
0x1800036fd  lock xadd [rax], r8d
0x180003702  inc     r8d; unsigned int
0x180003705  movzx   eax, dx
0x180003708  lea     rcx, [rax+rax*4]
0x18000370c  shl     rcx, 4
0x180003710  add     rcx, r9; this
0x180003713  mov     rdx, rdi; struct wil::FailureInfo *
0x180003716  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000371b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003725  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000372c  add     rsp, 20h
0x180003730  pop     r14
0x180003732  pop     rdi
0x180003733  pop     rsi
0x180003734  pop     rbp
0x180003735  pop     rbx
0x180003736  retn
```
