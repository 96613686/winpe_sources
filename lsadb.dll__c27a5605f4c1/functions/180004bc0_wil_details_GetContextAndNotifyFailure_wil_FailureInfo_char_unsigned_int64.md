# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004bc0`
- end: `0x180004dc6`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004bc0`
- `0x1800052b8`
- `0x18000539c`
- `0x180006538`
- `0x180007bb8`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004bea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004bea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cab`

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
0x180004bc0  push    rbx
0x180004bc2  push    rbp
0x180004bc3  push    rsi
0x180004bc4  push    rdi
0x180004bc5  push    r14
0x180004bc7  sub     rsp, 20h
0x180004bcb  mov     byte ptr [rdx], 0
0x180004bce  xor     bpl, bpl
0x180004bd1  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004bd8  mov     r14, r8
0x180004bdb  mov     rsi, rdx
0x180004bde  mov     rdi, rcx
0x180004be1  test    rbx, rbx
0x180004be4  jz      loc_180004C80
0x180004bea  call    cs:__imp_GetCurrentThreadId
0x180004bf0  mov     r8d, eax
0x180004bf3  mov     r9d, eax
0x180004bf6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004c00  shr     r8, 2
0x180004c04  mul     r8
0x180004c07  shr     rdx, 3
0x180004c0b  lea     rcx, [rdx+rdx*4]
0x180004c0f  add     rcx, rcx
0x180004c12  sub     r8, rcx
0x180004c15  mov     rbx, [rbx+r8*8]
0x180004c19  jmp     short loc_180004C24
0x180004c1b  cmp     [rbx], r9d
0x180004c1e  jz      short loc_180004C9B
0x180004c20  mov     rbx, [rbx+8]
0x180004c24  test    rbx, rbx
0x180004c27  jnz     short loc_180004C1B
0x180004c29  test    rbx, rbx
0x180004c2c  jz      short loc_180004C80
0x180004c2e  cmp     qword ptr [rbx], 0
0x180004c32  jz      short loc_180004C80
0x180004c34  mov     [rsi], bpl
0x180004c37  mov     r9, r14; unsigned __int64
0x180004c3a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004c3d  mov     r8, rsi; char *
0x180004c40  mov     rcx, rdi; struct wil::FailureInfo *
0x180004c43  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004c48  test    al, al
0x180004c4a  jz      short loc_180004C50
0x180004c4c  mov     [rdi+48h], rsi
0x180004c50  mov     rbx, [rbx]
0x180004c53  mov     al, [rbx+28h]
0x180004c56  mov     byte ptr [rbx+28h], 1
0x180004c5a  test    al, al
0x180004c5c  jnz     short loc_180004C77
0x180004c5e  mov     rcx, [rbx+8]
0x180004c62  mov     rdx, rdi
0x180004c65  mov     rax, [rcx]
0x180004c68  mov     rax, [rax]
0x180004c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c70  or      bpl, al
0x180004c73  mov     byte ptr [rbx+28h], 0
0x180004c77  mov     rbx, [rbx+10h]
0x180004c7b  test    rbx, rbx
0x180004c7e  jnz     short loc_180004C53
0x180004c80  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004c87  test    rax, rax
0x180004c8a  jz      short loc_180004CAB
0x180004c8c  test    bpl, bpl
0x180004c8f  jnz     short loc_180004CA1
0x180004c91  test    byte ptr [rdi+4], 2
0x180004c95  jnz     short loc_180004CA1
0x180004c97  xor     ecx, ecx
0x180004c99  jmp     short loc_180004CA3
0x180004c9b  add     rbx, 10h
0x180004c9f  jmp     short loc_180004C29
0x180004ca1  mov     cl, 1
0x180004ca3  mov     rdx, rdi
0x180004ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cab  call    cs:__imp_GetCurrentThreadId
0x180004cb1  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004cb7  cmp     ecx, eax
0x180004cb9  jz      loc_180004DBB
0x180004cbf  mov     ecx, 1
0x180004cc4  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004ccc  inc     ecx; this
0x180004cce  cmp     ecx, 4
0x180004cd1  jge     loc_180004DB4
0x180004cd7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004cdd  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004ce2  mov     rbx, rax
0x180004ce5  test    rax, rax
0x180004ce8  jz      loc_180004DAA
0x180004cee  cmp     qword ptr [rax+18h], 0
0x180004cf3  mov     ebp, 50h ; 'P'
0x180004cf8  mov     esi, [rax+10h]
0x180004cfb  jnz     short loc_180004D32
0x180004cfd  test    esi, esi
0x180004cff  jz      short loc_180004D32
0x180004d01  mov     edx, 190h; dwBytes
0x180004d06  lea     ecx, [rbp-48h]; dwFlags
0x180004d09  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004d0e  mov     [rbx+18h], rax
0x180004d12  test    rax, rax
0x180004d15  jz      short loc_180004D32
0x180004d17  mov     dword ptr [rbx+20h], 5
0x180004d1e  lea     rcx, [rax+190h]
0x180004d25  jmp     short loc_180004D2D
0x180004d27  mov     [rax], bp
0x180004d2a  add     rax, rbp
0x180004d2d  cmp     rax, rcx
0x180004d30  jnz     short loc_180004D27
0x180004d32  mov     r9, [rbx+18h]
0x180004d36  test    r9, r9
0x180004d39  jz      short loc_180004DAA
0x180004d3b  test    esi, esi
0x180004d3d  jz      short loc_180004D70
0x180004d3f  movzx   eax, word ptr [rbx+20h]
0x180004d43  mov     rcx, r9
0x180004d46  lea     rdx, [rax+rax*4]
0x180004d4a  shl     rdx, 4
0x180004d4e  add     rdx, r9
0x180004d51  cmp     r9, rdx
0x180004d54  jz      short loc_180004D70
0x180004d56  mov     r8d, [rbx+10h]
0x180004d5a  cmp     [rcx+4], r8d
0x180004d5e  jbe     short loc_180004D68
0x180004d60  mov     eax, [rdi+8]
0x180004d63  cmp     [rcx+8], eax
0x180004d66  jz      short loc_180004DAA
0x180004d68  add     rcx, rbp
0x180004d6b  cmp     rcx, rdx
0x180004d6e  jnz     short loc_180004D5A
0x180004d70  movzx   eax, word ptr [rbx+22h]
0x180004d74  xor     edx, edx
0x180004d76  movzx   ecx, word ptr [rbx+20h]
0x180004d7a  inc     eax
0x180004d7c  div     ecx
0x180004d7e  mov     rax, [rbx+8]
0x180004d82  mov     r8d, 1
0x180004d88  mov     [rbx+22h], dx
0x180004d8c  lock xadd [rax], r8d
0x180004d91  movzx   eax, dx
0x180004d94  inc     r8d; unsigned int
0x180004d97  mov     rdx, rdi; struct wil::FailureInfo *
0x180004d9a  lea     rcx, [rax+rax*4]
0x180004d9e  shl     rcx, 4
0x180004da2  add     rcx, r9; this
0x180004da5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004daa  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004db4  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004dbb  add     rsp, 20h
0x180004dbf  pop     r14
0x180004dc1  pop     rdi
0x180004dc2  pop     rsi
0x180004dc3  pop     rbp
0x180004dc4  pop     rbx
0x180004dc5  retn
```
