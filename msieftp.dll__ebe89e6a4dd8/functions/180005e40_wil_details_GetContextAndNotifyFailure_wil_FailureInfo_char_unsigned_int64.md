# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005e40`
- end: `0x180006046`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005e40`
- `0x180006688`
- `0x18000676c`
- `0x180007470`
- `0x180009268`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f2b`

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
0x180005e40  push    rbx
0x180005e42  push    rbp
0x180005e43  push    rsi
0x180005e44  push    rdi
0x180005e45  push    r14
0x180005e47  sub     rsp, 20h
0x180005e4b  mov     byte ptr [rdx], 0
0x180005e4e  xor     bpl, bpl
0x180005e51  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005e58  mov     r14, r8
0x180005e5b  mov     rsi, rdx
0x180005e5e  mov     rdi, rcx
0x180005e61  test    rbx, rbx
0x180005e64  jz      loc_180005F00
0x180005e6a  call    cs:__imp_GetCurrentThreadId
0x180005e70  mov     r8d, eax
0x180005e73  mov     r9d, eax
0x180005e76  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005e80  shr     r8, 2
0x180005e84  mul     r8
0x180005e87  shr     rdx, 3
0x180005e8b  lea     rcx, [rdx+rdx*4]
0x180005e8f  add     rcx, rcx
0x180005e92  sub     r8, rcx
0x180005e95  mov     rbx, [rbx+r8*8]
0x180005e99  jmp     short loc_180005EA4
0x180005e9b  cmp     [rbx], r9d
0x180005e9e  jz      short loc_180005F1B
0x180005ea0  mov     rbx, [rbx+8]
0x180005ea4  test    rbx, rbx
0x180005ea7  jnz     short loc_180005E9B
0x180005ea9  test    rbx, rbx
0x180005eac  jz      short loc_180005F00
0x180005eae  cmp     qword ptr [rbx], 0
0x180005eb2  jz      short loc_180005F00
0x180005eb4  mov     [rsi], bpl
0x180005eb7  mov     r9, r14; unsigned __int64
0x180005eba  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005ebd  mov     r8, rsi; char *
0x180005ec0  mov     rcx, rdi; struct wil::FailureInfo *
0x180005ec3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005ec8  test    al, al
0x180005eca  jz      short loc_180005ED0
0x180005ecc  mov     [rdi+48h], rsi
0x180005ed0  mov     rbx, [rbx]
0x180005ed3  mov     al, [rbx+28h]
0x180005ed6  mov     byte ptr [rbx+28h], 1
0x180005eda  test    al, al
0x180005edc  jnz     short loc_180005EF7
0x180005ede  mov     rcx, [rbx+8]
0x180005ee2  mov     rdx, rdi
0x180005ee5  mov     rax, [rcx]
0x180005ee8  mov     rax, [rax]
0x180005eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef0  or      bpl, al
0x180005ef3  mov     byte ptr [rbx+28h], 0
0x180005ef7  mov     rbx, [rbx+10h]
0x180005efb  test    rbx, rbx
0x180005efe  jnz     short loc_180005ED3
0x180005f00  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005f07  test    rax, rax
0x180005f0a  jz      short loc_180005F2B
0x180005f0c  test    bpl, bpl
0x180005f0f  jnz     short loc_180005F21
0x180005f11  test    byte ptr [rdi+4], 2
0x180005f15  jnz     short loc_180005F21
0x180005f17  xor     ecx, ecx
0x180005f19  jmp     short loc_180005F23
0x180005f1b  add     rbx, 10h
0x180005f1f  jmp     short loc_180005EA9
0x180005f21  mov     cl, 1
0x180005f23  mov     rdx, rdi
0x180005f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f2b  call    cs:__imp_GetCurrentThreadId
0x180005f31  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005f37  cmp     ecx, eax
0x180005f39  jz      loc_18000603B
0x180005f3f  mov     ecx, 1
0x180005f44  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005f4c  inc     ecx; this
0x180005f4e  cmp     ecx, 4
0x180005f51  jge     loc_180006034
0x180005f57  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005f5d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005f62  mov     rbx, rax
0x180005f65  test    rax, rax
0x180005f68  jz      loc_18000602A
0x180005f6e  cmp     qword ptr [rax+18h], 0
0x180005f73  mov     ebp, 50h ; 'P'
0x180005f78  mov     esi, [rax+10h]
0x180005f7b  jnz     short loc_180005FB2
0x180005f7d  test    esi, esi
0x180005f7f  jz      short loc_180005FB2
0x180005f81  mov     edx, 190h; dwBytes
0x180005f86  lea     ecx, [rbp-48h]; dwFlags
0x180005f89  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005f8e  mov     [rbx+18h], rax
0x180005f92  test    rax, rax
0x180005f95  jz      short loc_180005FB2
0x180005f97  mov     dword ptr [rbx+20h], 5
0x180005f9e  lea     rcx, [rax+190h]
0x180005fa5  jmp     short loc_180005FAD
0x180005fa7  mov     [rax], bp
0x180005faa  add     rax, rbp
0x180005fad  cmp     rax, rcx
0x180005fb0  jnz     short loc_180005FA7
0x180005fb2  mov     r9, [rbx+18h]
0x180005fb6  test    r9, r9
0x180005fb9  jz      short loc_18000602A
0x180005fbb  test    esi, esi
0x180005fbd  jz      short loc_180005FF0
0x180005fbf  movzx   eax, word ptr [rbx+20h]
0x180005fc3  mov     rcx, r9
0x180005fc6  lea     rdx, [rax+rax*4]
0x180005fca  shl     rdx, 4
0x180005fce  add     rdx, r9
0x180005fd1  cmp     r9, rdx
0x180005fd4  jz      short loc_180005FF0
0x180005fd6  mov     r8d, [rbx+10h]
0x180005fda  cmp     [rcx+4], r8d
0x180005fde  jbe     short loc_180005FE8
0x180005fe0  mov     eax, [rdi+8]
0x180005fe3  cmp     [rcx+8], eax
0x180005fe6  jz      short loc_18000602A
0x180005fe8  add     rcx, rbp
0x180005feb  cmp     rcx, rdx
0x180005fee  jnz     short loc_180005FDA
0x180005ff0  movzx   eax, word ptr [rbx+22h]
0x180005ff4  xor     edx, edx
0x180005ff6  movzx   ecx, word ptr [rbx+20h]
0x180005ffa  inc     eax
0x180005ffc  div     ecx
0x180005ffe  mov     rax, [rbx+8]
0x180006002  mov     r8d, 1
0x180006008  mov     [rbx+22h], dx
0x18000600c  lock xadd [rax], r8d
0x180006011  movzx   eax, dx
0x180006014  inc     r8d; unsigned int
0x180006017  mov     rdx, rdi; struct wil::FailureInfo *
0x18000601a  lea     rcx, [rax+rax*4]
0x18000601e  shl     rcx, 4
0x180006022  add     rcx, r9; this
0x180006025  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000602a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180006034  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000603b  add     rsp, 20h
0x18000603f  pop     r14
0x180006041  pop     rdi
0x180006042  pop     rsi
0x180006043  pop     rbp
0x180006044  pop     rbx
0x180006045  retn
```
