# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004ce0`
- end: `0x180004ee6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004ce0`
- `0x1800053d8`
- `0x1800054bc`
- `0x1800061a8`
- `0x180007cc8`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004dcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004dcb`

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
0x180004ce0  push    rbx
0x180004ce2  push    rbp
0x180004ce3  push    rsi
0x180004ce4  push    rdi
0x180004ce5  push    r14
0x180004ce7  sub     rsp, 20h
0x180004ceb  mov     byte ptr [rdx], 0
0x180004cee  xor     bpl, bpl
0x180004cf1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004cf8  mov     r14, r8
0x180004cfb  mov     rsi, rdx
0x180004cfe  mov     rdi, rcx
0x180004d01  test    rbx, rbx
0x180004d04  jz      loc_180004DA0
0x180004d0a  call    cs:__imp_GetCurrentThreadId
0x180004d10  mov     r8d, eax
0x180004d13  mov     r9d, eax
0x180004d16  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004d20  shr     r8, 2
0x180004d24  mul     r8
0x180004d27  shr     rdx, 3
0x180004d2b  lea     rcx, [rdx+rdx*4]
0x180004d2f  add     rcx, rcx
0x180004d32  sub     r8, rcx
0x180004d35  mov     rbx, [rbx+r8*8]
0x180004d39  jmp     short loc_180004D44
0x180004d3b  cmp     [rbx], r9d
0x180004d3e  jz      short loc_180004DBB
0x180004d40  mov     rbx, [rbx+8]
0x180004d44  test    rbx, rbx
0x180004d47  jnz     short loc_180004D3B
0x180004d49  test    rbx, rbx
0x180004d4c  jz      short loc_180004DA0
0x180004d4e  cmp     qword ptr [rbx], 0
0x180004d52  jz      short loc_180004DA0
0x180004d54  mov     [rsi], bpl
0x180004d57  mov     r9, r14; unsigned __int64
0x180004d5a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004d5d  mov     r8, rsi; char *
0x180004d60  mov     rcx, rdi; struct wil::FailureInfo *
0x180004d63  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004d68  test    al, al
0x180004d6a  jz      short loc_180004D70
0x180004d6c  mov     [rdi+48h], rsi
0x180004d70  mov     rbx, [rbx]
0x180004d73  mov     al, [rbx+28h]
0x180004d76  mov     byte ptr [rbx+28h], 1
0x180004d7a  test    al, al
0x180004d7c  jnz     short loc_180004D97
0x180004d7e  mov     rcx, [rbx+8]
0x180004d82  mov     rdx, rdi
0x180004d85  mov     rax, [rcx]
0x180004d88  mov     rax, [rax]
0x180004d8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d90  or      bpl, al
0x180004d93  mov     byte ptr [rbx+28h], 0
0x180004d97  mov     rbx, [rbx+10h]
0x180004d9b  test    rbx, rbx
0x180004d9e  jnz     short loc_180004D73
0x180004da0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004da7  test    rax, rax
0x180004daa  jz      short loc_180004DCB
0x180004dac  test    bpl, bpl
0x180004daf  jnz     short loc_180004DC1
0x180004db1  test    byte ptr [rdi+4], 2
0x180004db5  jnz     short loc_180004DC1
0x180004db7  xor     ecx, ecx
0x180004db9  jmp     short loc_180004DC3
0x180004dbb  add     rbx, 10h
0x180004dbf  jmp     short loc_180004D49
0x180004dc1  mov     cl, 1
0x180004dc3  mov     rdx, rdi
0x180004dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dcb  call    cs:__imp_GetCurrentThreadId
0x180004dd1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004dd7  cmp     ecx, eax
0x180004dd9  jz      loc_180004EDB
0x180004ddf  mov     ecx, 1
0x180004de4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004dec  inc     ecx; this
0x180004dee  cmp     ecx, 4
0x180004df1  jge     loc_180004ED4
0x180004df7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004dfd  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004e02  mov     rbx, rax
0x180004e05  test    rax, rax
0x180004e08  jz      loc_180004ECA
0x180004e0e  cmp     qword ptr [rax+18h], 0
0x180004e13  mov     ebp, 50h ; 'P'
0x180004e18  mov     esi, [rax+10h]
0x180004e1b  jnz     short loc_180004E52
0x180004e1d  test    esi, esi
0x180004e1f  jz      short loc_180004E52
0x180004e21  mov     edx, 190h; dwBytes
0x180004e26  lea     ecx, [rbp-48h]; dwFlags
0x180004e29  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004e2e  mov     [rbx+18h], rax
0x180004e32  test    rax, rax
0x180004e35  jz      short loc_180004E52
0x180004e37  mov     dword ptr [rbx+20h], 5
0x180004e3e  lea     rcx, [rax+190h]
0x180004e45  jmp     short loc_180004E4D
0x180004e47  mov     [rax], bp
0x180004e4a  add     rax, rbp
0x180004e4d  cmp     rax, rcx
0x180004e50  jnz     short loc_180004E47
0x180004e52  mov     r9, [rbx+18h]
0x180004e56  test    r9, r9
0x180004e59  jz      short loc_180004ECA
0x180004e5b  test    esi, esi
0x180004e5d  jz      short loc_180004E90
0x180004e5f  movzx   eax, word ptr [rbx+20h]
0x180004e63  mov     rcx, r9
0x180004e66  lea     rdx, [rax+rax*4]
0x180004e6a  shl     rdx, 4
0x180004e6e  add     rdx, r9
0x180004e71  cmp     r9, rdx
0x180004e74  jz      short loc_180004E90
0x180004e76  mov     r8d, [rbx+10h]
0x180004e7a  cmp     [rcx+4], r8d
0x180004e7e  jbe     short loc_180004E88
0x180004e80  mov     eax, [rdi+8]
0x180004e83  cmp     [rcx+8], eax
0x180004e86  jz      short loc_180004ECA
0x180004e88  add     rcx, rbp
0x180004e8b  cmp     rcx, rdx
0x180004e8e  jnz     short loc_180004E7A
0x180004e90  movzx   eax, word ptr [rbx+22h]
0x180004e94  xor     edx, edx
0x180004e96  movzx   ecx, word ptr [rbx+20h]
0x180004e9a  inc     eax
0x180004e9c  div     ecx
0x180004e9e  mov     rax, [rbx+8]
0x180004ea2  mov     r8d, 1
0x180004ea8  mov     [rbx+22h], dx
0x180004eac  lock xadd [rax], r8d
0x180004eb1  movzx   eax, dx
0x180004eb4  inc     r8d; unsigned int
0x180004eb7  mov     rdx, rdi; struct wil::FailureInfo *
0x180004eba  lea     rcx, [rax+rax*4]
0x180004ebe  shl     rcx, 4
0x180004ec2  add     rcx, r9; this
0x180004ec5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004eca  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004ed4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004edb  add     rsp, 20h
0x180004edf  pop     r14
0x180004ee1  pop     rdi
0x180004ee2  pop     rsi
0x180004ee3  pop     rbp
0x180004ee4  pop     rbx
0x180004ee5  retn
```
