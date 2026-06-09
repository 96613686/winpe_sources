# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800044a0`
- end: `0x1800046a7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800044a0`
- `0x180004b9c`
- `0x180004c80`
- `0x1800054f8`
- `0x1800059f0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800044ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000458c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800044ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000458c`

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
0x1800044a0  push    rbx
0x1800044a2  push    rbp
0x1800044a3  push    rsi
0x1800044a4  push    rdi
0x1800044a5  push    r14
0x1800044a7  sub     rsp, 20h
0x1800044ab  mov     r14, r8
0x1800044ae  mov     rsi, rdx
0x1800044b1  mov     rdi, rcx
0x1800044b4  mov     byte ptr [rdx], 0
0x1800044b7  xor     bpl, bpl
0x1800044ba  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800044c1  test    rbx, rbx
0x1800044c4  jz      loc_180004560
0x1800044ca  call    cs:__imp_GetCurrentThreadId
0x1800044d0  mov     r9d, eax
0x1800044d3  mov     r8d, eax
0x1800044d6  shr     r8, 2
0x1800044da  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800044e4  mul     r8
0x1800044e7  shr     rdx, 3
0x1800044eb  lea     rcx, [rdx+rdx*4]
0x1800044ef  add     rcx, rcx
0x1800044f2  sub     r8, rcx
0x1800044f5  mov     rbx, [rbx+r8*8]
0x1800044f9  jmp     short loc_180004504
0x1800044fb  cmp     [rbx], r9d
0x1800044fe  jz      short loc_18000457B
0x180004500  mov     rbx, [rbx+8]
0x180004504  test    rbx, rbx
0x180004507  jnz     short loc_1800044FB
0x180004509  test    rbx, rbx
0x18000450c  jz      short loc_180004560
0x18000450e  cmp     qword ptr [rbx], 0
0x180004512  jz      short loc_180004560
0x180004514  mov     [rsi], bpl
0x180004517  mov     r9, r14; unsigned __int64
0x18000451a  mov     r8, rsi; char *
0x18000451d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004520  mov     rcx, rdi; struct wil::FailureInfo *
0x180004523  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004528  test    al, al
0x18000452a  jz      short loc_180004530
0x18000452c  mov     [rdi+48h], rsi
0x180004530  mov     rbx, [rbx]
0x180004533  mov     al, [rbx+28h]
0x180004536  mov     byte ptr [rbx+28h], 1
0x18000453a  test    al, al
0x18000453c  jnz     short loc_180004557
0x18000453e  mov     rcx, [rbx+8]
0x180004542  mov     rax, [rcx]
0x180004545  mov     rdx, rdi
0x180004548  mov     rax, [rax]
0x18000454b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004550  or      bpl, al
0x180004553  mov     byte ptr [rbx+28h], 0
0x180004557  mov     rbx, [rbx+10h]
0x18000455b  test    rbx, rbx
0x18000455e  jnz     short loc_180004533
0x180004560  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004567  test    rax, rax
0x18000456a  jz      short loc_18000458C
0x18000456c  test    bpl, bpl
0x18000456f  jnz     short loc_180004581
0x180004571  test    byte ptr [rdi+4], 2
0x180004575  jnz     short loc_180004581
0x180004577  xor     ecx, ecx
0x180004579  jmp     short loc_180004583
0x18000457b  add     rbx, 10h
0x18000457f  jmp     short loc_180004509
0x180004581  mov     cl, 1
0x180004583  mov     rdx, rdi
0x180004586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000458b  nop
0x18000458c  call    cs:__imp_GetCurrentThreadId
0x180004592  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004598  cmp     ecx, eax
0x18000459a  jz      loc_18000469C
0x1800045a0  mov     ecx, 1
0x1800045a5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800045ad  inc     ecx; this
0x1800045af  cmp     ecx, 4
0x1800045b2  jge     loc_180004695
0x1800045b8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800045be  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800045c3  mov     rbx, rax
0x1800045c6  test    rax, rax
0x1800045c9  jz      loc_18000468B
0x1800045cf  mov     esi, [rax+10h]
0x1800045d2  mov     ebp, 50h ; 'P'
0x1800045d7  cmp     qword ptr [rax+18h], 0
0x1800045dc  jnz     short loc_180004613
0x1800045de  test    esi, esi
0x1800045e0  jz      short loc_180004613
0x1800045e2  mov     edx, 190h; dwBytes
0x1800045e7  lea     ecx, [rbp-48h]; dwFlags
0x1800045ea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800045ef  mov     [rbx+18h], rax
0x1800045f3  test    rax, rax
0x1800045f6  jz      short loc_180004613
0x1800045f8  mov     dword ptr [rbx+20h], 5
0x1800045ff  lea     rcx, [rax+190h]
0x180004606  jmp     short loc_18000460E
0x180004608  mov     [rax], bp
0x18000460b  add     rax, rbp
0x18000460e  cmp     rax, rcx
0x180004611  jnz     short loc_180004608
0x180004613  mov     r9, [rbx+18h]
0x180004617  test    r9, r9
0x18000461a  jz      short loc_18000468B
0x18000461c  test    esi, esi
0x18000461e  jz      short loc_180004651
0x180004620  mov     rcx, r9
0x180004623  movzx   eax, word ptr [rbx+20h]
0x180004627  lea     rdx, [rax+rax*4]
0x18000462b  shl     rdx, 4
0x18000462f  add     rdx, r9
0x180004632  cmp     r9, rdx
0x180004635  jz      short loc_180004651
0x180004637  mov     r8d, [rbx+10h]
0x18000463b  cmp     [rcx+4], r8d
0x18000463f  jbe     short loc_180004649
0x180004641  mov     eax, [rdi+8]
0x180004644  cmp     [rcx+8], eax
0x180004647  jz      short loc_18000468B
0x180004649  add     rcx, rbp
0x18000464c  cmp     rcx, rdx
0x18000464f  jnz     short loc_18000463B
0x180004651  movzx   eax, word ptr [rbx+22h]
0x180004655  inc     eax
0x180004657  movzx   ecx, word ptr [rbx+20h]
0x18000465b  xor     edx, edx
0x18000465d  div     ecx
0x18000465f  mov     [rbx+22h], dx
0x180004663  mov     rax, [rbx+8]
0x180004667  mov     r8d, 1
0x18000466d  lock xadd [rax], r8d
0x180004672  inc     r8d; unsigned int
0x180004675  movzx   eax, dx
0x180004678  lea     rcx, [rax+rax*4]
0x18000467c  shl     rcx, 4
0x180004680  add     rcx, r9; this
0x180004683  mov     rdx, rdi; struct wil::FailureInfo *
0x180004686  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000468b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004695  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000469c  add     rsp, 20h
0x1800046a0  pop     r14
0x1800046a2  pop     rdi
0x1800046a3  pop     rsi
0x1800046a4  pop     rbp
0x1800046a5  pop     rbx
0x1800046a6  retn
```
