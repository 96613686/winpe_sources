# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180006d90`
- end: `0x180006f97`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180006d90`
- `0x18000748c`
- `0x180007570`
- `0x180007cf8`
- `0x180009564`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006dba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006dba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e7c`

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
0x180006d90  push    rbx
0x180006d92  push    rbp
0x180006d93  push    rsi
0x180006d94  push    rdi
0x180006d95  push    r14
0x180006d97  sub     rsp, 20h
0x180006d9b  mov     r14, r8
0x180006d9e  mov     rsi, rdx
0x180006da1  mov     rdi, rcx
0x180006da4  mov     byte ptr [rdx], 0
0x180006da7  xor     bpl, bpl
0x180006daa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180006db1  test    rbx, rbx
0x180006db4  jz      loc_180006E50
0x180006dba  call    cs:__imp_GetCurrentThreadId
0x180006dc0  mov     r9d, eax
0x180006dc3  mov     r8d, eax
0x180006dc6  shr     r8, 2
0x180006dca  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180006dd4  mul     r8
0x180006dd7  shr     rdx, 3
0x180006ddb  lea     rcx, [rdx+rdx*4]
0x180006ddf  add     rcx, rcx
0x180006de2  sub     r8, rcx
0x180006de5  mov     rbx, [rbx+r8*8]
0x180006de9  jmp     short loc_180006DF4
0x180006deb  cmp     [rbx], r9d
0x180006dee  jz      short loc_180006E6B
0x180006df0  mov     rbx, [rbx+8]
0x180006df4  test    rbx, rbx
0x180006df7  jnz     short loc_180006DEB
0x180006df9  test    rbx, rbx
0x180006dfc  jz      short loc_180006E50
0x180006dfe  cmp     qword ptr [rbx], 0
0x180006e02  jz      short loc_180006E50
0x180006e04  mov     [rsi], bpl
0x180006e07  mov     r9, r14; unsigned __int64
0x180006e0a  mov     r8, rsi; char *
0x180006e0d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180006e10  mov     rcx, rdi; struct wil::FailureInfo *
0x180006e13  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180006e18  test    al, al
0x180006e1a  jz      short loc_180006E20
0x180006e1c  mov     [rdi+48h], rsi
0x180006e20  mov     rbx, [rbx]
0x180006e23  mov     al, [rbx+28h]
0x180006e26  mov     byte ptr [rbx+28h], 1
0x180006e2a  test    al, al
0x180006e2c  jnz     short loc_180006E47
0x180006e2e  mov     rcx, [rbx+8]
0x180006e32  mov     rax, [rcx]
0x180006e35  mov     rdx, rdi
0x180006e38  mov     rax, [rax]
0x180006e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e40  or      bpl, al
0x180006e43  mov     byte ptr [rbx+28h], 0
0x180006e47  mov     rbx, [rbx+10h]
0x180006e4b  test    rbx, rbx
0x180006e4e  jnz     short loc_180006E23
0x180006e50  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180006e57  test    rax, rax
0x180006e5a  jz      short loc_180006E7C
0x180006e5c  test    bpl, bpl
0x180006e5f  jnz     short loc_180006E71
0x180006e61  test    byte ptr [rdi+4], 2
0x180006e65  jnz     short loc_180006E71
0x180006e67  xor     ecx, ecx
0x180006e69  jmp     short loc_180006E73
0x180006e6b  add     rbx, 10h
0x180006e6f  jmp     short loc_180006DF9
0x180006e71  mov     cl, 1
0x180006e73  mov     rdx, rdi
0x180006e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e7b  nop
0x180006e7c  call    cs:__imp_GetCurrentThreadId
0x180006e82  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006e88  cmp     ecx, eax
0x180006e8a  jz      loc_180006F8C
0x180006e90  mov     ecx, 1
0x180006e95  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180006e9d  inc     ecx; this
0x180006e9f  cmp     ecx, 4
0x180006ea2  jge     loc_180006F85
0x180006ea8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006eae  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180006eb3  mov     rbx, rax
0x180006eb6  test    rax, rax
0x180006eb9  jz      loc_180006F7B
0x180006ebf  mov     esi, [rax+10h]
0x180006ec2  mov     ebp, 50h ; 'P'
0x180006ec7  cmp     qword ptr [rax+18h], 0
0x180006ecc  jnz     short loc_180006F03
0x180006ece  test    esi, esi
0x180006ed0  jz      short loc_180006F03
0x180006ed2  mov     edx, 190h; dwBytes
0x180006ed7  lea     ecx, [rbp-48h]; dwFlags
0x180006eda  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180006edf  mov     [rbx+18h], rax
0x180006ee3  test    rax, rax
0x180006ee6  jz      short loc_180006F03
0x180006ee8  mov     dword ptr [rbx+20h], 5
0x180006eef  lea     rcx, [rax+190h]
0x180006ef6  jmp     short loc_180006EFE
0x180006ef8  mov     [rax], bp
0x180006efb  add     rax, rbp
0x180006efe  cmp     rax, rcx
0x180006f01  jnz     short loc_180006EF8
0x180006f03  mov     r9, [rbx+18h]
0x180006f07  test    r9, r9
0x180006f0a  jz      short loc_180006F7B
0x180006f0c  test    esi, esi
0x180006f0e  jz      short loc_180006F41
0x180006f10  mov     rcx, r9
0x180006f13  movzx   eax, word ptr [rbx+20h]
0x180006f17  lea     rdx, [rax+rax*4]
0x180006f1b  shl     rdx, 4
0x180006f1f  add     rdx, r9
0x180006f22  cmp     r9, rdx
0x180006f25  jz      short loc_180006F41
0x180006f27  mov     r8d, [rbx+10h]
0x180006f2b  cmp     [rcx+4], r8d
0x180006f2f  jbe     short loc_180006F39
0x180006f31  mov     eax, [rdi+8]
0x180006f34  cmp     [rcx+8], eax
0x180006f37  jz      short loc_180006F7B
0x180006f39  add     rcx, rbp
0x180006f3c  cmp     rcx, rdx
0x180006f3f  jnz     short loc_180006F2B
0x180006f41  movzx   eax, word ptr [rbx+22h]
0x180006f45  inc     eax
0x180006f47  movzx   ecx, word ptr [rbx+20h]
0x180006f4b  xor     edx, edx
0x180006f4d  div     ecx
0x180006f4f  mov     [rbx+22h], dx
0x180006f53  mov     rax, [rbx+8]
0x180006f57  mov     r8d, 1
0x180006f5d  lock xadd [rax], r8d
0x180006f62  inc     r8d; unsigned int
0x180006f65  movzx   eax, dx
0x180006f68  lea     rcx, [rax+rax*4]
0x180006f6c  shl     rcx, 4
0x180006f70  add     rcx, r9; this
0x180006f73  mov     rdx, rdi; struct wil::FailureInfo *
0x180006f76  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180006f7b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006f85  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180006f8c  add     rsp, 20h
0x180006f90  pop     r14
0x180006f92  pop     rdi
0x180006f93  pop     rsi
0x180006f94  pop     rbp
0x180006f95  pop     rbx
0x180006f96  retn
```
