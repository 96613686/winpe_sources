# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180002b70`
- end: `0x180002d76`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180002b70`
- `0x180003268`
- `0x18000334c`
- `0x180003bb8`
- `0x180003f00`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c5b`

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
0x180002b70  push    rbx
0x180002b72  push    rbp
0x180002b73  push    rsi
0x180002b74  push    rdi
0x180002b75  push    r14
0x180002b77  sub     rsp, 20h
0x180002b7b  mov     byte ptr [rdx], 0
0x180002b7e  xor     bpl, bpl
0x180002b81  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180002b88  mov     r14, r8
0x180002b8b  mov     rsi, rdx
0x180002b8e  mov     rdi, rcx
0x180002b91  test    rbx, rbx
0x180002b94  jz      loc_180002C30
0x180002b9a  call    cs:__imp_GetCurrentThreadId
0x180002ba0  mov     r8d, eax
0x180002ba3  mov     r9d, eax
0x180002ba6  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180002bb0  shr     r8, 2
0x180002bb4  mul     r8
0x180002bb7  shr     rdx, 3
0x180002bbb  lea     rcx, [rdx+rdx*4]
0x180002bbf  add     rcx, rcx
0x180002bc2  sub     r8, rcx
0x180002bc5  mov     rbx, [rbx+r8*8]
0x180002bc9  jmp     short loc_180002BD4
0x180002bcb  cmp     [rbx], r9d
0x180002bce  jz      short loc_180002C4B
0x180002bd0  mov     rbx, [rbx+8]
0x180002bd4  test    rbx, rbx
0x180002bd7  jnz     short loc_180002BCB
0x180002bd9  test    rbx, rbx
0x180002bdc  jz      short loc_180002C30
0x180002bde  cmp     qword ptr [rbx], 0
0x180002be2  jz      short loc_180002C30
0x180002be4  mov     [rsi], bpl
0x180002be7  mov     r9, r14; unsigned __int64
0x180002bea  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180002bed  mov     r8, rsi; char *
0x180002bf0  mov     rcx, rdi; struct wil::FailureInfo *
0x180002bf3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180002bf8  test    al, al
0x180002bfa  jz      short loc_180002C00
0x180002bfc  mov     [rdi+48h], rsi
0x180002c00  mov     rbx, [rbx]
0x180002c03  mov     al, [rbx+28h]
0x180002c06  mov     byte ptr [rbx+28h], 1
0x180002c0a  test    al, al
0x180002c0c  jnz     short loc_180002C27
0x180002c0e  mov     rcx, [rbx+8]
0x180002c12  mov     rdx, rdi
0x180002c15  mov     rax, [rcx]
0x180002c18  mov     rax, [rax]
0x180002c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c20  or      bpl, al
0x180002c23  mov     byte ptr [rbx+28h], 0
0x180002c27  mov     rbx, [rbx+10h]
0x180002c2b  test    rbx, rbx
0x180002c2e  jnz     short loc_180002C03
0x180002c30  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180002c37  test    rax, rax
0x180002c3a  jz      short loc_180002C5B
0x180002c3c  test    bpl, bpl
0x180002c3f  jnz     short loc_180002C51
0x180002c41  test    byte ptr [rdi+4], 2
0x180002c45  jnz     short loc_180002C51
0x180002c47  xor     ecx, ecx
0x180002c49  jmp     short loc_180002C53
0x180002c4b  add     rbx, 10h
0x180002c4f  jmp     short loc_180002BD9
0x180002c51  mov     cl, 1
0x180002c53  mov     rdx, rdi
0x180002c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c5b  call    cs:__imp_GetCurrentThreadId
0x180002c61  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180002c67  cmp     ecx, eax
0x180002c69  jz      loc_180002D6B
0x180002c6f  mov     ecx, 1
0x180002c74  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180002c7c  inc     ecx; this
0x180002c7e  cmp     ecx, 4
0x180002c81  jge     loc_180002D64
0x180002c87  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180002c8d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180002c92  mov     rbx, rax
0x180002c95  test    rax, rax
0x180002c98  jz      loc_180002D5A
0x180002c9e  cmp     qword ptr [rax+18h], 0
0x180002ca3  mov     ebp, 50h ; 'P'
0x180002ca8  mov     esi, [rax+10h]
0x180002cab  jnz     short loc_180002CE2
0x180002cad  test    esi, esi
0x180002caf  jz      short loc_180002CE2
0x180002cb1  mov     edx, 190h; dwBytes
0x180002cb6  lea     ecx, [rbp-48h]; dwFlags
0x180002cb9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180002cbe  mov     [rbx+18h], rax
0x180002cc2  test    rax, rax
0x180002cc5  jz      short loc_180002CE2
0x180002cc7  mov     dword ptr [rbx+20h], 5
0x180002cce  lea     rcx, [rax+190h]
0x180002cd5  jmp     short loc_180002CDD
0x180002cd7  mov     [rax], bp
0x180002cda  add     rax, rbp
0x180002cdd  cmp     rax, rcx
0x180002ce0  jnz     short loc_180002CD7
0x180002ce2  mov     r9, [rbx+18h]
0x180002ce6  test    r9, r9
0x180002ce9  jz      short loc_180002D5A
0x180002ceb  test    esi, esi
0x180002ced  jz      short loc_180002D20
0x180002cef  movzx   eax, word ptr [rbx+20h]
0x180002cf3  mov     rcx, r9
0x180002cf6  lea     rdx, [rax+rax*4]
0x180002cfa  shl     rdx, 4
0x180002cfe  add     rdx, r9
0x180002d01  cmp     r9, rdx
0x180002d04  jz      short loc_180002D20
0x180002d06  mov     r8d, [rbx+10h]
0x180002d0a  cmp     [rcx+4], r8d
0x180002d0e  jbe     short loc_180002D18
0x180002d10  mov     eax, [rdi+8]
0x180002d13  cmp     [rcx+8], eax
0x180002d16  jz      short loc_180002D5A
0x180002d18  add     rcx, rbp
0x180002d1b  cmp     rcx, rdx
0x180002d1e  jnz     short loc_180002D0A
0x180002d20  movzx   eax, word ptr [rbx+22h]
0x180002d24  xor     edx, edx
0x180002d26  movzx   ecx, word ptr [rbx+20h]
0x180002d2a  inc     eax
0x180002d2c  div     ecx
0x180002d2e  mov     rax, [rbx+8]
0x180002d32  mov     r8d, 1
0x180002d38  mov     [rbx+22h], dx
0x180002d3c  lock xadd [rax], r8d
0x180002d41  movzx   eax, dx
0x180002d44  inc     r8d; unsigned int
0x180002d47  mov     rdx, rdi; struct wil::FailureInfo *
0x180002d4a  lea     rcx, [rax+rax*4]
0x180002d4e  shl     rcx, 4
0x180002d52  add     rcx, r9; this
0x180002d55  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180002d5a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180002d64  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180002d6b  add     rsp, 20h
0x180002d6f  pop     r14
0x180002d71  pop     rdi
0x180002d72  pop     rsi
0x180002d73  pop     rbp
0x180002d74  pop     rbx
0x180002d75  retn
```
