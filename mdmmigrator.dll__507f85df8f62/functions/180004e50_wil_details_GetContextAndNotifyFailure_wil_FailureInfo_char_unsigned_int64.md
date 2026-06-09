# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004e50`
- end: `0x180005057`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004e50`
- `0x18000554c`
- `0x180005630`
- `0x180005ea8`
- `0x180006384`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f3c`

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
0x180004e50  push    rbx
0x180004e52  push    rbp
0x180004e53  push    rsi
0x180004e54  push    rdi
0x180004e55  push    r14
0x180004e57  sub     rsp, 20h
0x180004e5b  mov     r14, r8
0x180004e5e  mov     rsi, rdx
0x180004e61  mov     rdi, rcx
0x180004e64  mov     byte ptr [rdx], 0
0x180004e67  xor     bpl, bpl
0x180004e6a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004e71  test    rbx, rbx
0x180004e74  jz      loc_180004F10
0x180004e7a  call    cs:__imp_GetCurrentThreadId
0x180004e80  mov     r9d, eax
0x180004e83  mov     r8d, eax
0x180004e86  shr     r8, 2
0x180004e8a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004e94  mul     r8
0x180004e97  shr     rdx, 3
0x180004e9b  lea     rcx, [rdx+rdx*4]
0x180004e9f  add     rcx, rcx
0x180004ea2  sub     r8, rcx
0x180004ea5  mov     rbx, [rbx+r8*8]
0x180004ea9  jmp     short loc_180004EB4
0x180004eab  cmp     [rbx], r9d
0x180004eae  jz      short loc_180004F2B
0x180004eb0  mov     rbx, [rbx+8]
0x180004eb4  test    rbx, rbx
0x180004eb7  jnz     short loc_180004EAB
0x180004eb9  test    rbx, rbx
0x180004ebc  jz      short loc_180004F10
0x180004ebe  cmp     qword ptr [rbx], 0
0x180004ec2  jz      short loc_180004F10
0x180004ec4  mov     [rsi], bpl
0x180004ec7  mov     r9, r14; unsigned __int64
0x180004eca  mov     r8, rsi; char *
0x180004ecd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004ed0  mov     rcx, rdi; struct wil::FailureInfo *
0x180004ed3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004ed8  test    al, al
0x180004eda  jz      short loc_180004EE0
0x180004edc  mov     [rdi+48h], rsi
0x180004ee0  mov     rbx, [rbx]
0x180004ee3  mov     al, [rbx+28h]
0x180004ee6  mov     byte ptr [rbx+28h], 1
0x180004eea  test    al, al
0x180004eec  jnz     short loc_180004F07
0x180004eee  mov     rcx, [rbx+8]
0x180004ef2  mov     rax, [rcx]
0x180004ef5  mov     rdx, rdi
0x180004ef8  mov     rax, [rax]
0x180004efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f00  or      bpl, al
0x180004f03  mov     byte ptr [rbx+28h], 0
0x180004f07  mov     rbx, [rbx+10h]
0x180004f0b  test    rbx, rbx
0x180004f0e  jnz     short loc_180004EE3
0x180004f10  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004f17  test    rax, rax
0x180004f1a  jz      short loc_180004F3C
0x180004f1c  test    bpl, bpl
0x180004f1f  jnz     short loc_180004F31
0x180004f21  test    byte ptr [rdi+4], 2
0x180004f25  jnz     short loc_180004F31
0x180004f27  xor     ecx, ecx
0x180004f29  jmp     short loc_180004F33
0x180004f2b  add     rbx, 10h
0x180004f2f  jmp     short loc_180004EB9
0x180004f31  mov     cl, 1
0x180004f33  mov     rdx, rdi
0x180004f36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f3b  nop
0x180004f3c  call    cs:__imp_GetCurrentThreadId
0x180004f42  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004f48  cmp     ecx, eax
0x180004f4a  jz      loc_18000504C
0x180004f50  mov     ecx, 1
0x180004f55  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004f5d  inc     ecx; this
0x180004f5f  cmp     ecx, 4
0x180004f62  jge     loc_180005045
0x180004f68  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004f6e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004f73  mov     rbx, rax
0x180004f76  test    rax, rax
0x180004f79  jz      loc_18000503B
0x180004f7f  mov     esi, [rax+10h]
0x180004f82  mov     ebp, 50h ; 'P'
0x180004f87  cmp     qword ptr [rax+18h], 0
0x180004f8c  jnz     short loc_180004FC3
0x180004f8e  test    esi, esi
0x180004f90  jz      short loc_180004FC3
0x180004f92  mov     edx, 190h; dwBytes
0x180004f97  lea     ecx, [rbp-48h]; dwFlags
0x180004f9a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004f9f  mov     [rbx+18h], rax
0x180004fa3  test    rax, rax
0x180004fa6  jz      short loc_180004FC3
0x180004fa8  mov     dword ptr [rbx+20h], 5
0x180004faf  lea     rcx, [rax+190h]
0x180004fb6  jmp     short loc_180004FBE
0x180004fb8  mov     [rax], bp
0x180004fbb  add     rax, rbp
0x180004fbe  cmp     rax, rcx
0x180004fc1  jnz     short loc_180004FB8
0x180004fc3  mov     r9, [rbx+18h]
0x180004fc7  test    r9, r9
0x180004fca  jz      short loc_18000503B
0x180004fcc  test    esi, esi
0x180004fce  jz      short loc_180005001
0x180004fd0  mov     rcx, r9
0x180004fd3  movzx   eax, word ptr [rbx+20h]
0x180004fd7  lea     rdx, [rax+rax*4]
0x180004fdb  shl     rdx, 4
0x180004fdf  add     rdx, r9
0x180004fe2  cmp     r9, rdx
0x180004fe5  jz      short loc_180005001
0x180004fe7  mov     r8d, [rbx+10h]
0x180004feb  cmp     [rcx+4], r8d
0x180004fef  jbe     short loc_180004FF9
0x180004ff1  mov     eax, [rdi+8]
0x180004ff4  cmp     [rcx+8], eax
0x180004ff7  jz      short loc_18000503B
0x180004ff9  add     rcx, rbp
0x180004ffc  cmp     rcx, rdx
0x180004fff  jnz     short loc_180004FEB
0x180005001  movzx   eax, word ptr [rbx+22h]
0x180005005  inc     eax
0x180005007  movzx   ecx, word ptr [rbx+20h]
0x18000500b  xor     edx, edx
0x18000500d  div     ecx
0x18000500f  mov     [rbx+22h], dx
0x180005013  mov     rax, [rbx+8]
0x180005017  mov     r8d, 1
0x18000501d  lock xadd [rax], r8d
0x180005022  inc     r8d; unsigned int
0x180005025  movzx   eax, dx
0x180005028  lea     rcx, [rax+rax*4]
0x18000502c  shl     rcx, 4
0x180005030  add     rcx, r9; this
0x180005033  mov     rdx, rdi; struct wil::FailureInfo *
0x180005036  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000503b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005045  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000504c  add     rsp, 20h
0x180005050  pop     r14
0x180005052  pop     rdi
0x180005053  pop     rsi
0x180005054  pop     rbp
0x180005055  pop     rbx
0x180005056  retn
```
