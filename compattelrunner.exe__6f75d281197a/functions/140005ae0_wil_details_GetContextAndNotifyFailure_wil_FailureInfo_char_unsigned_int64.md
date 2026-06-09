# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140005ae0`
- end: `0x140005ce7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140005ae0`
- `0x14000632c`
- `0x140006410`
- `0x140006e88`
- `0x1400089e4`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005b0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005bcc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005b0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005bcc`

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
0x140005ae0  push    rbx
0x140005ae2  push    rbp
0x140005ae3  push    rsi
0x140005ae4  push    rdi
0x140005ae5  push    r14
0x140005ae7  sub     rsp, 20h
0x140005aeb  mov     r14, r8
0x140005aee  mov     rsi, rdx
0x140005af1  mov     rdi, rcx
0x140005af4  mov     byte ptr [rdx], 0
0x140005af7  xor     bpl, bpl
0x140005afa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140005b01  test    rbx, rbx
0x140005b04  jz      loc_140005BA0
0x140005b0a  call    cs:__imp_GetCurrentThreadId
0x140005b10  mov     r9d, eax
0x140005b13  mov     r8d, eax
0x140005b16  shr     r8, 2
0x140005b1a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140005b24  mul     r8
0x140005b27  shr     rdx, 3
0x140005b2b  lea     rcx, [rdx+rdx*4]
0x140005b2f  add     rcx, rcx
0x140005b32  sub     r8, rcx
0x140005b35  mov     rbx, [rbx+r8*8]
0x140005b39  jmp     short loc_140005B44
0x140005b3b  cmp     [rbx], r9d
0x140005b3e  jz      short loc_140005BBB
0x140005b40  mov     rbx, [rbx+8]
0x140005b44  test    rbx, rbx
0x140005b47  jnz     short loc_140005B3B
0x140005b49  test    rbx, rbx
0x140005b4c  jz      short loc_140005BA0
0x140005b4e  cmp     qword ptr [rbx], 0
0x140005b52  jz      short loc_140005BA0
0x140005b54  mov     [rsi], bpl
0x140005b57  mov     r9, r14; unsigned __int64
0x140005b5a  mov     r8, rsi; char *
0x140005b5d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140005b60  mov     rcx, rdi; struct wil::FailureInfo *
0x140005b63  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140005b68  test    al, al
0x140005b6a  jz      short loc_140005B70
0x140005b6c  mov     [rdi+48h], rsi
0x140005b70  mov     rbx, [rbx]
0x140005b73  mov     al, [rbx+28h]
0x140005b76  mov     byte ptr [rbx+28h], 1
0x140005b7a  test    al, al
0x140005b7c  jnz     short loc_140005B97
0x140005b7e  mov     rcx, [rbx+8]
0x140005b82  mov     rax, [rcx]
0x140005b85  mov     rdx, rdi
0x140005b88  mov     rax, [rax]
0x140005b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b90  or      bpl, al
0x140005b93  mov     byte ptr [rbx+28h], 0
0x140005b97  mov     rbx, [rbx+10h]
0x140005b9b  test    rbx, rbx
0x140005b9e  jnz     short loc_140005B73
0x140005ba0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140005ba7  test    rax, rax
0x140005baa  jz      short loc_140005BCC
0x140005bac  test    bpl, bpl
0x140005baf  jnz     short loc_140005BC1
0x140005bb1  test    byte ptr [rdi+4], 2
0x140005bb5  jnz     short loc_140005BC1
0x140005bb7  xor     ecx, ecx
0x140005bb9  jmp     short loc_140005BC3
0x140005bbb  add     rbx, 10h
0x140005bbf  jmp     short loc_140005B49
0x140005bc1  mov     cl, 1
0x140005bc3  mov     rdx, rdi
0x140005bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bcb  nop
0x140005bcc  call    cs:__imp_GetCurrentThreadId
0x140005bd2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140005bd8  cmp     ecx, eax
0x140005bda  jz      loc_140005CDC
0x140005be0  mov     ecx, 1
0x140005be5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140005bed  inc     ecx; this
0x140005bef  cmp     ecx, 4
0x140005bf2  jge     loc_140005CD5
0x140005bf8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140005bfe  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140005c03  mov     rbx, rax
0x140005c06  test    rax, rax
0x140005c09  jz      loc_140005CCB
0x140005c0f  mov     esi, [rax+10h]
0x140005c12  mov     ebp, 50h ; 'P'
0x140005c17  cmp     qword ptr [rax+18h], 0
0x140005c1c  jnz     short loc_140005C53
0x140005c1e  test    esi, esi
0x140005c20  jz      short loc_140005C53
0x140005c22  mov     edx, 190h; dwBytes
0x140005c27  lea     ecx, [rbp-48h]; dwFlags
0x140005c2a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005c2f  mov     [rbx+18h], rax
0x140005c33  test    rax, rax
0x140005c36  jz      short loc_140005C53
0x140005c38  mov     dword ptr [rbx+20h], 5
0x140005c3f  lea     rcx, [rax+190h]
0x140005c46  jmp     short loc_140005C4E
0x140005c48  mov     [rax], bp
0x140005c4b  add     rax, rbp
0x140005c4e  cmp     rax, rcx
0x140005c51  jnz     short loc_140005C48
0x140005c53  mov     r9, [rbx+18h]
0x140005c57  test    r9, r9
0x140005c5a  jz      short loc_140005CCB
0x140005c5c  test    esi, esi
0x140005c5e  jz      short loc_140005C91
0x140005c60  mov     rcx, r9
0x140005c63  movzx   eax, word ptr [rbx+20h]
0x140005c67  lea     rdx, [rax+rax*4]
0x140005c6b  shl     rdx, 4
0x140005c6f  add     rdx, r9
0x140005c72  cmp     r9, rdx
0x140005c75  jz      short loc_140005C91
0x140005c77  mov     r8d, [rbx+10h]
0x140005c7b  cmp     [rcx+4], r8d
0x140005c7f  jbe     short loc_140005C89
0x140005c81  mov     eax, [rdi+8]
0x140005c84  cmp     [rcx+8], eax
0x140005c87  jz      short loc_140005CCB
0x140005c89  add     rcx, rbp
0x140005c8c  cmp     rcx, rdx
0x140005c8f  jnz     short loc_140005C7B
0x140005c91  movzx   eax, word ptr [rbx+22h]
0x140005c95  inc     eax
0x140005c97  movzx   ecx, word ptr [rbx+20h]
0x140005c9b  xor     edx, edx
0x140005c9d  div     ecx
0x140005c9f  mov     [rbx+22h], dx
0x140005ca3  mov     rax, [rbx+8]
0x140005ca7  mov     r8d, 1
0x140005cad  lock xadd [rax], r8d
0x140005cb2  inc     r8d; unsigned int
0x140005cb5  movzx   eax, dx
0x140005cb8  lea     rcx, [rax+rax*4]
0x140005cbc  shl     rcx, 4
0x140005cc0  add     rcx, r9; this
0x140005cc3  mov     rdx, rdi; struct wil::FailureInfo *
0x140005cc6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140005ccb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140005cd5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140005cdc  add     rsp, 20h
0x140005ce0  pop     r14
0x140005ce2  pop     rdi
0x140005ce3  pop     rsi
0x140005ce4  pop     rbp
0x140005ce5  pop     rbx
0x140005ce6  retn
```
