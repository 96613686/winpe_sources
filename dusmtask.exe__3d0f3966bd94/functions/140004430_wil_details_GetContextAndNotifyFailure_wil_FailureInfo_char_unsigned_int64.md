# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140004430`
- end: `0x140004637`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140004430`
- `0x140004b2c`
- `0x140004c10`
- `0x140005530`
- `0x140005ab4`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000445a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000451c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000445a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000451c`

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
0x140004430  push    rbx
0x140004432  push    rbp
0x140004433  push    rsi
0x140004434  push    rdi
0x140004435  push    r14
0x140004437  sub     rsp, 20h
0x14000443b  mov     r14, r8
0x14000443e  mov     rsi, rdx
0x140004441  mov     rdi, rcx
0x140004444  mov     byte ptr [rdx], 0
0x140004447  xor     bpl, bpl
0x14000444a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140004451  test    rbx, rbx
0x140004454  jz      loc_1400044F0
0x14000445a  call    cs:__imp_GetCurrentThreadId
0x140004460  mov     r9d, eax
0x140004463  mov     r8d, eax
0x140004466  shr     r8, 2
0x14000446a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004474  mul     r8
0x140004477  shr     rdx, 3
0x14000447b  lea     rcx, [rdx+rdx*4]
0x14000447f  add     rcx, rcx
0x140004482  sub     r8, rcx
0x140004485  mov     rbx, [rbx+r8*8]
0x140004489  jmp     short loc_140004494
0x14000448b  cmp     [rbx], r9d
0x14000448e  jz      short loc_14000450B
0x140004490  mov     rbx, [rbx+8]
0x140004494  test    rbx, rbx
0x140004497  jnz     short loc_14000448B
0x140004499  test    rbx, rbx
0x14000449c  jz      short loc_1400044F0
0x14000449e  cmp     qword ptr [rbx], 0
0x1400044a2  jz      short loc_1400044F0
0x1400044a4  mov     [rsi], bpl
0x1400044a7  mov     r9, r14; unsigned __int64
0x1400044aa  mov     r8, rsi; char *
0x1400044ad  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x1400044b0  mov     rcx, rdi; struct wil::FailureInfo *
0x1400044b3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x1400044b8  test    al, al
0x1400044ba  jz      short loc_1400044C0
0x1400044bc  mov     [rdi+48h], rsi
0x1400044c0  mov     rbx, [rbx]
0x1400044c3  mov     al, [rbx+28h]
0x1400044c6  mov     byte ptr [rbx+28h], 1
0x1400044ca  test    al, al
0x1400044cc  jnz     short loc_1400044E7
0x1400044ce  mov     rcx, [rbx+8]
0x1400044d2  mov     rax, [rcx]
0x1400044d5  mov     rdx, rdi
0x1400044d8  mov     rax, [rax]
0x1400044db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044e0  or      bpl, al
0x1400044e3  mov     byte ptr [rbx+28h], 0
0x1400044e7  mov     rbx, [rbx+10h]
0x1400044eb  test    rbx, rbx
0x1400044ee  jnz     short loc_1400044C3
0x1400044f0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1400044f7  test    rax, rax
0x1400044fa  jz      short loc_14000451C
0x1400044fc  test    bpl, bpl
0x1400044ff  jnz     short loc_140004511
0x140004501  test    byte ptr [rdi+4], 2
0x140004505  jnz     short loc_140004511
0x140004507  xor     ecx, ecx
0x140004509  jmp     short loc_140004513
0x14000450b  add     rbx, 10h
0x14000450f  jmp     short loc_140004499
0x140004511  mov     cl, 1
0x140004513  mov     rdx, rdi
0x140004516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000451b  nop
0x14000451c  call    cs:__imp_GetCurrentThreadId
0x140004522  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004528  cmp     ecx, eax
0x14000452a  jz      loc_14000462C
0x140004530  mov     ecx, 1
0x140004535  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000453d  inc     ecx; this
0x14000453f  cmp     ecx, 4
0x140004542  jge     loc_140004625
0x140004548  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000454e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140004553  mov     rbx, rax
0x140004556  test    rax, rax
0x140004559  jz      loc_14000461B
0x14000455f  mov     esi, [rax+10h]
0x140004562  mov     ebp, 50h ; 'P'
0x140004567  cmp     qword ptr [rax+18h], 0
0x14000456c  jnz     short loc_1400045A3
0x14000456e  test    esi, esi
0x140004570  jz      short loc_1400045A3
0x140004572  mov     edx, 190h; dwBytes
0x140004577  lea     ecx, [rbp-48h]; dwFlags
0x14000457a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000457f  mov     [rbx+18h], rax
0x140004583  test    rax, rax
0x140004586  jz      short loc_1400045A3
0x140004588  mov     dword ptr [rbx+20h], 5
0x14000458f  lea     rcx, [rax+190h]
0x140004596  jmp     short loc_14000459E
0x140004598  mov     [rax], bp
0x14000459b  add     rax, rbp
0x14000459e  cmp     rax, rcx
0x1400045a1  jnz     short loc_140004598
0x1400045a3  mov     r9, [rbx+18h]
0x1400045a7  test    r9, r9
0x1400045aa  jz      short loc_14000461B
0x1400045ac  test    esi, esi
0x1400045ae  jz      short loc_1400045E1
0x1400045b0  mov     rcx, r9
0x1400045b3  movzx   eax, word ptr [rbx+20h]
0x1400045b7  lea     rdx, [rax+rax*4]
0x1400045bb  shl     rdx, 4
0x1400045bf  add     rdx, r9
0x1400045c2  cmp     r9, rdx
0x1400045c5  jz      short loc_1400045E1
0x1400045c7  mov     r8d, [rbx+10h]
0x1400045cb  cmp     [rcx+4], r8d
0x1400045cf  jbe     short loc_1400045D9
0x1400045d1  mov     eax, [rdi+8]
0x1400045d4  cmp     [rcx+8], eax
0x1400045d7  jz      short loc_14000461B
0x1400045d9  add     rcx, rbp
0x1400045dc  cmp     rcx, rdx
0x1400045df  jnz     short loc_1400045CB
0x1400045e1  movzx   eax, word ptr [rbx+22h]
0x1400045e5  inc     eax
0x1400045e7  movzx   ecx, word ptr [rbx+20h]
0x1400045eb  xor     edx, edx
0x1400045ed  div     ecx
0x1400045ef  mov     [rbx+22h], dx
0x1400045f3  mov     rax, [rbx+8]
0x1400045f7  mov     r8d, 1
0x1400045fd  lock xadd [rax], r8d
0x140004602  inc     r8d; unsigned int
0x140004605  movzx   eax, dx
0x140004608  lea     rcx, [rax+rax*4]
0x14000460c  shl     rcx, 4
0x140004610  add     rcx, r9; this
0x140004613  mov     rdx, rdi; struct wil::FailureInfo *
0x140004616  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000461b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004625  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000462c  add     rsp, 20h
0x140004630  pop     r14
0x140004632  pop     rdi
0x140004633  pop     rsi
0x140004634  pop     rbp
0x140004635  pop     rbx
0x140004636  retn
```
