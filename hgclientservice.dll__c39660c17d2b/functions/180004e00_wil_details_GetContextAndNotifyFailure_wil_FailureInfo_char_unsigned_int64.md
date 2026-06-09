# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004e00`
- end: `0x180005007`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004e00`
- `0x1800054fc`
- `0x1800055e0`
- `0x180005ec8`
- `0x1800065a4`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004eec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004eec`

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
0x180004e00  push    rbx
0x180004e02  push    rbp
0x180004e03  push    rsi
0x180004e04  push    rdi
0x180004e05  push    r14
0x180004e07  sub     rsp, 20h
0x180004e0b  mov     r14, r8
0x180004e0e  mov     rsi, rdx
0x180004e11  mov     rdi, rcx
0x180004e14  mov     byte ptr [rdx], 0
0x180004e17  xor     bpl, bpl
0x180004e1a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004e21  test    rbx, rbx
0x180004e24  jz      loc_180004EC0
0x180004e2a  call    cs:__imp_GetCurrentThreadId
0x180004e30  mov     r9d, eax
0x180004e33  mov     r8d, eax
0x180004e36  shr     r8, 2
0x180004e3a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004e44  mul     r8
0x180004e47  shr     rdx, 3
0x180004e4b  lea     rcx, [rdx+rdx*4]
0x180004e4f  add     rcx, rcx
0x180004e52  sub     r8, rcx
0x180004e55  mov     rbx, [rbx+r8*8]
0x180004e59  jmp     short loc_180004E64
0x180004e5b  cmp     [rbx], r9d
0x180004e5e  jz      short loc_180004EDB
0x180004e60  mov     rbx, [rbx+8]
0x180004e64  test    rbx, rbx
0x180004e67  jnz     short loc_180004E5B
0x180004e69  test    rbx, rbx
0x180004e6c  jz      short loc_180004EC0
0x180004e6e  cmp     qword ptr [rbx], 0
0x180004e72  jz      short loc_180004EC0
0x180004e74  mov     [rsi], bpl
0x180004e77  mov     r9, r14; unsigned __int64
0x180004e7a  mov     r8, rsi; char *
0x180004e7d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004e80  mov     rcx, rdi; struct wil::FailureInfo *
0x180004e83  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004e88  test    al, al
0x180004e8a  jz      short loc_180004E90
0x180004e8c  mov     [rdi+48h], rsi
0x180004e90  mov     rbx, [rbx]
0x180004e93  mov     al, [rbx+28h]
0x180004e96  mov     byte ptr [rbx+28h], 1
0x180004e9a  test    al, al
0x180004e9c  jnz     short loc_180004EB7
0x180004e9e  mov     rcx, [rbx+8]
0x180004ea2  mov     rax, [rcx]
0x180004ea5  mov     rdx, rdi
0x180004ea8  mov     rax, [rax]
0x180004eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eb0  or      bpl, al
0x180004eb3  mov     byte ptr [rbx+28h], 0
0x180004eb7  mov     rbx, [rbx+10h]
0x180004ebb  test    rbx, rbx
0x180004ebe  jnz     short loc_180004E93
0x180004ec0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004ec7  test    rax, rax
0x180004eca  jz      short loc_180004EEC
0x180004ecc  test    bpl, bpl
0x180004ecf  jnz     short loc_180004EE1
0x180004ed1  test    byte ptr [rdi+4], 2
0x180004ed5  jnz     short loc_180004EE1
0x180004ed7  xor     ecx, ecx
0x180004ed9  jmp     short loc_180004EE3
0x180004edb  add     rbx, 10h
0x180004edf  jmp     short loc_180004E69
0x180004ee1  mov     cl, 1
0x180004ee3  mov     rdx, rdi
0x180004ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eeb  nop
0x180004eec  call    cs:__imp_GetCurrentThreadId
0x180004ef2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004ef8  cmp     ecx, eax
0x180004efa  jz      loc_180004FFC
0x180004f00  mov     ecx, 1
0x180004f05  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004f0d  inc     ecx; this
0x180004f0f  cmp     ecx, 4
0x180004f12  jge     loc_180004FF5
0x180004f18  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004f1e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004f23  mov     rbx, rax
0x180004f26  test    rax, rax
0x180004f29  jz      loc_180004FEB
0x180004f2f  mov     esi, [rax+10h]
0x180004f32  mov     ebp, 50h ; 'P'
0x180004f37  cmp     qword ptr [rax+18h], 0
0x180004f3c  jnz     short loc_180004F73
0x180004f3e  test    esi, esi
0x180004f40  jz      short loc_180004F73
0x180004f42  mov     edx, 190h; dwBytes
0x180004f47  lea     ecx, [rbp-48h]; dwFlags
0x180004f4a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004f4f  mov     [rbx+18h], rax
0x180004f53  test    rax, rax
0x180004f56  jz      short loc_180004F73
0x180004f58  mov     dword ptr [rbx+20h], 5
0x180004f5f  lea     rcx, [rax+190h]
0x180004f66  jmp     short loc_180004F6E
0x180004f68  mov     [rax], bp
0x180004f6b  add     rax, rbp
0x180004f6e  cmp     rax, rcx
0x180004f71  jnz     short loc_180004F68
0x180004f73  mov     r9, [rbx+18h]
0x180004f77  test    r9, r9
0x180004f7a  jz      short loc_180004FEB
0x180004f7c  test    esi, esi
0x180004f7e  jz      short loc_180004FB1
0x180004f80  mov     rcx, r9
0x180004f83  movzx   eax, word ptr [rbx+20h]
0x180004f87  lea     rdx, [rax+rax*4]
0x180004f8b  shl     rdx, 4
0x180004f8f  add     rdx, r9
0x180004f92  cmp     r9, rdx
0x180004f95  jz      short loc_180004FB1
0x180004f97  mov     r8d, [rbx+10h]
0x180004f9b  cmp     [rcx+4], r8d
0x180004f9f  jbe     short loc_180004FA9
0x180004fa1  mov     eax, [rdi+8]
0x180004fa4  cmp     [rcx+8], eax
0x180004fa7  jz      short loc_180004FEB
0x180004fa9  add     rcx, rbp
0x180004fac  cmp     rcx, rdx
0x180004faf  jnz     short loc_180004F9B
0x180004fb1  movzx   eax, word ptr [rbx+22h]
0x180004fb5  inc     eax
0x180004fb7  movzx   ecx, word ptr [rbx+20h]
0x180004fbb  xor     edx, edx
0x180004fbd  div     ecx
0x180004fbf  mov     [rbx+22h], dx
0x180004fc3  mov     rax, [rbx+8]
0x180004fc7  mov     r8d, 1
0x180004fcd  lock xadd [rax], r8d
0x180004fd2  inc     r8d; unsigned int
0x180004fd5  movzx   eax, dx
0x180004fd8  lea     rcx, [rax+rax*4]
0x180004fdc  shl     rcx, 4
0x180004fe0  add     rcx, r9; this
0x180004fe3  mov     rdx, rdi; struct wil::FailureInfo *
0x180004fe6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004feb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004ff5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004ffc  add     rsp, 20h
0x180005000  pop     r14
0x180005002  pop     rdi
0x180005003  pop     rsi
0x180005004  pop     rbp
0x180005005  pop     rbx
0x180005006  retn
```
