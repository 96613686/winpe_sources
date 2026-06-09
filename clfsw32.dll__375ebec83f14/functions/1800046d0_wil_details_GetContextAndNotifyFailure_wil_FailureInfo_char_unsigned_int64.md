# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800046d0`
- end: `0x1800048e3`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `531`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800046d0`
- `0x180004e04`
- `0x180004ef0`
- `0x180005910`
- `0x180006db8`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800046fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047c1`

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
0x1800046d0  push    rbx
0x1800046d2  push    rbp
0x1800046d3  push    rsi
0x1800046d4  push    rdi
0x1800046d5  push    r14
0x1800046d7  sub     rsp, 20h
0x1800046db  mov     byte ptr [rdx], 0
0x1800046de  xor     bpl, bpl
0x1800046e1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800046e8  mov     r14, r8
0x1800046eb  mov     rsi, rdx
0x1800046ee  mov     rdi, rcx
0x1800046f1  test    rbx, rbx
0x1800046f4  jz      loc_180004796
0x1800046fa  call    cs:__imp_GetCurrentThreadId
0x180004701  nop     dword ptr [rax+rax+00h]
0x180004706  mov     r8d, eax
0x180004709  mov     r9d, eax
0x18000470c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004716  shr     r8, 2
0x18000471a  mul     r8
0x18000471d  shr     rdx, 3
0x180004721  lea     rcx, [rdx+rdx*4]
0x180004725  add     rcx, rcx
0x180004728  sub     r8, rcx
0x18000472b  mov     rbx, [rbx+r8*8]
0x18000472f  jmp     short loc_18000473A
0x180004731  cmp     [rbx], r9d
0x180004734  jz      short loc_1800047B1
0x180004736  mov     rbx, [rbx+8]
0x18000473a  test    rbx, rbx
0x18000473d  jnz     short loc_180004731
0x18000473f  test    rbx, rbx
0x180004742  jz      short loc_180004796
0x180004744  cmp     qword ptr [rbx], 0
0x180004748  jz      short loc_180004796
0x18000474a  mov     [rsi], bpl
0x18000474d  mov     r9, r14; unsigned __int64
0x180004750  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004753  mov     r8, rsi; char *
0x180004756  mov     rcx, rdi; struct wil::FailureInfo *
0x180004759  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000475e  test    al, al
0x180004760  jz      short loc_180004766
0x180004762  mov     [rdi+48h], rsi
0x180004766  mov     rbx, [rbx]
0x180004769  mov     al, [rbx+28h]
0x18000476c  mov     byte ptr [rbx+28h], 1
0x180004770  test    al, al
0x180004772  jnz     short loc_18000478D
0x180004774  mov     rcx, [rbx+8]
0x180004778  mov     rdx, rdi
0x18000477b  mov     rax, [rcx]
0x18000477e  mov     rax, [rax]
0x180004781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004786  or      bpl, al
0x180004789  mov     byte ptr [rbx+28h], 0
0x18000478d  mov     rbx, [rbx+10h]
0x180004791  test    rbx, rbx
0x180004794  jnz     short loc_180004769
0x180004796  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000479d  test    rax, rax
0x1800047a0  jz      short loc_1800047C1
0x1800047a2  test    bpl, bpl
0x1800047a5  jnz     short loc_1800047B7
0x1800047a7  test    byte ptr [rdi+4], 2
0x1800047ab  jnz     short loc_1800047B7
0x1800047ad  xor     ecx, ecx
0x1800047af  jmp     short loc_1800047B9
0x1800047b1  add     rbx, 10h
0x1800047b5  jmp     short loc_18000473F
0x1800047b7  mov     cl, 1
0x1800047b9  mov     rdx, rdi
0x1800047bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047c1  call    cs:__imp_GetCurrentThreadId
0x1800047c8  nop     dword ptr [rax+rax+00h]
0x1800047cd  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800047d3  cmp     ecx, eax
0x1800047d5  jz      loc_1800048D7
0x1800047db  mov     ecx, 1
0x1800047e0  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800047e8  inc     ecx; this
0x1800047ea  cmp     ecx, 4
0x1800047ed  jge     loc_1800048D0
0x1800047f3  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800047f9  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800047fe  mov     rbx, rax
0x180004801  test    rax, rax
0x180004804  jz      loc_1800048C6
0x18000480a  cmp     qword ptr [rax+18h], 0
0x18000480f  mov     ebp, 50h ; 'P'
0x180004814  mov     esi, [rax+10h]
0x180004817  jnz     short loc_18000484E
0x180004819  test    esi, esi
0x18000481b  jz      short loc_18000484E
0x18000481d  mov     edx, 190h; dwBytes
0x180004822  lea     ecx, [rbp-48h]; dwFlags
0x180004825  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000482a  mov     [rbx+18h], rax
0x18000482e  test    rax, rax
0x180004831  jz      short loc_18000484E
0x180004833  mov     dword ptr [rbx+20h], 5
0x18000483a  lea     rcx, [rax+190h]
0x180004841  jmp     short loc_180004849
0x180004843  mov     [rax], bp
0x180004846  add     rax, rbp
0x180004849  cmp     rax, rcx
0x18000484c  jnz     short loc_180004843
0x18000484e  mov     r9, [rbx+18h]
0x180004852  test    r9, r9
0x180004855  jz      short loc_1800048C6
0x180004857  test    esi, esi
0x180004859  jz      short loc_18000488C
0x18000485b  movzx   eax, word ptr [rbx+20h]
0x18000485f  mov     rcx, r9
0x180004862  lea     rdx, [rax+rax*4]
0x180004866  shl     rdx, 4
0x18000486a  add     rdx, r9
0x18000486d  cmp     r9, rdx
0x180004870  jz      short loc_18000488C
0x180004872  mov     r8d, [rbx+10h]
0x180004876  cmp     [rcx+4], r8d
0x18000487a  jbe     short loc_180004884
0x18000487c  mov     eax, [rdi+8]
0x18000487f  cmp     [rcx+8], eax
0x180004882  jz      short loc_1800048C6
0x180004884  add     rcx, rbp
0x180004887  cmp     rcx, rdx
0x18000488a  jnz     short loc_180004876
0x18000488c  movzx   eax, word ptr [rbx+22h]
0x180004890  xor     edx, edx
0x180004892  movzx   ecx, word ptr [rbx+20h]
0x180004896  inc     eax
0x180004898  div     ecx
0x18000489a  mov     rax, [rbx+8]
0x18000489e  mov     r8d, 1
0x1800048a4  mov     [rbx+22h], dx
0x1800048a8  lock xadd [rax], r8d
0x1800048ad  movzx   eax, dx
0x1800048b0  inc     r8d; unsigned int
0x1800048b3  mov     rdx, rdi; struct wil::FailureInfo *
0x1800048b6  lea     rcx, [rax+rax*4]
0x1800048ba  shl     rcx, 4
0x1800048be  add     rcx, r9; this
0x1800048c1  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800048c6  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800048d0  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800048d7  add     rsp, 20h
0x1800048db  pop     r14
0x1800048dd  pop     rdi
0x1800048de  pop     rsi
0x1800048df  pop     rbp
0x1800048e0  pop     rbx
0x1800048e1  retn
```
