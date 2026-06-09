# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004bf0`
- end: `0x180004df7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004bf0`
- `0x1800052ec`
- `0x1800053d0`
- `0x180006588`
- `0x180006ae0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004c1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cdc`

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
0x180004bf0  push    rbx
0x180004bf2  push    rbp
0x180004bf3  push    rsi
0x180004bf4  push    rdi
0x180004bf5  push    r14
0x180004bf7  sub     rsp, 20h
0x180004bfb  mov     r14, r8
0x180004bfe  mov     rsi, rdx
0x180004c01  mov     rdi, rcx
0x180004c04  mov     byte ptr [rdx], 0
0x180004c07  xor     bpl, bpl
0x180004c0a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180004c11  test    rbx, rbx
0x180004c14  jz      loc_180004CB0
0x180004c1a  call    cs:__imp_GetCurrentThreadId
0x180004c20  mov     r9d, eax
0x180004c23  mov     r8d, eax
0x180004c26  shr     r8, 2
0x180004c2a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180004c34  mul     r8
0x180004c37  shr     rdx, 3
0x180004c3b  lea     rcx, [rdx+rdx*4]
0x180004c3f  add     rcx, rcx
0x180004c42  sub     r8, rcx
0x180004c45  mov     rbx, [rbx+r8*8]
0x180004c49  jmp     short loc_180004C54
0x180004c4b  cmp     [rbx], r9d
0x180004c4e  jz      short loc_180004CCB
0x180004c50  mov     rbx, [rbx+8]
0x180004c54  test    rbx, rbx
0x180004c57  jnz     short loc_180004C4B
0x180004c59  test    rbx, rbx
0x180004c5c  jz      short loc_180004CB0
0x180004c5e  cmp     qword ptr [rbx], 0
0x180004c62  jz      short loc_180004CB0
0x180004c64  mov     [rsi], bpl
0x180004c67  mov     r9, r14; unsigned __int64
0x180004c6a  mov     r8, rsi; char *
0x180004c6d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004c70  mov     rcx, rdi; struct wil::FailureInfo *
0x180004c73  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004c78  test    al, al
0x180004c7a  jz      short loc_180004C80
0x180004c7c  mov     [rdi+48h], rsi
0x180004c80  mov     rbx, [rbx]
0x180004c83  mov     al, [rbx+28h]
0x180004c86  mov     byte ptr [rbx+28h], 1
0x180004c8a  test    al, al
0x180004c8c  jnz     short loc_180004CA7
0x180004c8e  mov     rcx, [rbx+8]
0x180004c92  mov     rax, [rcx]
0x180004c95  mov     rdx, rdi
0x180004c98  mov     rax, [rax]
0x180004c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ca0  or      bpl, al
0x180004ca3  mov     byte ptr [rbx+28h], 0
0x180004ca7  mov     rbx, [rbx+10h]
0x180004cab  test    rbx, rbx
0x180004cae  jnz     short loc_180004C83
0x180004cb0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004cb7  test    rax, rax
0x180004cba  jz      short loc_180004CDC
0x180004cbc  test    bpl, bpl
0x180004cbf  jnz     short loc_180004CD1
0x180004cc1  test    byte ptr [rdi+4], 2
0x180004cc5  jnz     short loc_180004CD1
0x180004cc7  xor     ecx, ecx
0x180004cc9  jmp     short loc_180004CD3
0x180004ccb  add     rbx, 10h
0x180004ccf  jmp     short loc_180004C59
0x180004cd1  mov     cl, 1
0x180004cd3  mov     rdx, rdi
0x180004cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cdb  nop
0x180004cdc  call    cs:__imp_GetCurrentThreadId
0x180004ce2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004ce8  cmp     ecx, eax
0x180004cea  jz      loc_180004DEC
0x180004cf0  mov     ecx, 1
0x180004cf5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004cfd  inc     ecx; this
0x180004cff  cmp     ecx, 4
0x180004d02  jge     loc_180004DE5
0x180004d08  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004d0e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004d13  mov     rbx, rax
0x180004d16  test    rax, rax
0x180004d19  jz      loc_180004DDB
0x180004d1f  mov     esi, [rax+10h]
0x180004d22  mov     ebp, 50h ; 'P'
0x180004d27  cmp     qword ptr [rax+18h], 0
0x180004d2c  jnz     short loc_180004D63
0x180004d2e  test    esi, esi
0x180004d30  jz      short loc_180004D63
0x180004d32  mov     edx, 190h; dwBytes
0x180004d37  lea     ecx, [rbp-48h]; dwFlags
0x180004d3a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004d3f  mov     [rbx+18h], rax
0x180004d43  test    rax, rax
0x180004d46  jz      short loc_180004D63
0x180004d48  mov     dword ptr [rbx+20h], 5
0x180004d4f  lea     rcx, [rax+190h]
0x180004d56  jmp     short loc_180004D5E
0x180004d58  mov     [rax], bp
0x180004d5b  add     rax, rbp
0x180004d5e  cmp     rax, rcx
0x180004d61  jnz     short loc_180004D58
0x180004d63  mov     r9, [rbx+18h]
0x180004d67  test    r9, r9
0x180004d6a  jz      short loc_180004DDB
0x180004d6c  test    esi, esi
0x180004d6e  jz      short loc_180004DA1
0x180004d70  mov     rcx, r9
0x180004d73  movzx   eax, word ptr [rbx+20h]
0x180004d77  lea     rdx, [rax+rax*4]
0x180004d7b  shl     rdx, 4
0x180004d7f  add     rdx, r9
0x180004d82  cmp     r9, rdx
0x180004d85  jz      short loc_180004DA1
0x180004d87  mov     r8d, [rbx+10h]
0x180004d8b  cmp     [rcx+4], r8d
0x180004d8f  jbe     short loc_180004D99
0x180004d91  mov     eax, [rdi+8]
0x180004d94  cmp     [rcx+8], eax
0x180004d97  jz      short loc_180004DDB
0x180004d99  add     rcx, rbp
0x180004d9c  cmp     rcx, rdx
0x180004d9f  jnz     short loc_180004D8B
0x180004da1  movzx   eax, word ptr [rbx+22h]
0x180004da5  inc     eax
0x180004da7  movzx   ecx, word ptr [rbx+20h]
0x180004dab  xor     edx, edx
0x180004dad  div     ecx
0x180004daf  mov     [rbx+22h], dx
0x180004db3  mov     rax, [rbx+8]
0x180004db7  mov     r8d, 1
0x180004dbd  lock xadd [rax], r8d
0x180004dc2  inc     r8d; unsigned int
0x180004dc5  movzx   eax, dx
0x180004dc8  lea     rcx, [rax+rax*4]
0x180004dcc  shl     rcx, 4
0x180004dd0  add     rcx, r9; this
0x180004dd3  mov     rdx, rdi; struct wil::FailureInfo *
0x180004dd6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004ddb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004de5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004dec  add     rsp, 20h
0x180004df0  pop     r14
0x180004df2  pop     rdi
0x180004df3  pop     rsi
0x180004df4  pop     rbp
0x180004df5  pop     rbx
0x180004df6  retn
```
