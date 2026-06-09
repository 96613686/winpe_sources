# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1400049c0`
- end: `0x140004bc7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400049c0`
- `0x1400050bc`
- `0x1400051a0`
- `0x140005838`
- `0x140006dd4`
- `0x14001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400049ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004aac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400049ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004aac`

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
0x1400049c0  push    rbx
0x1400049c2  push    rbp
0x1400049c3  push    rsi
0x1400049c4  push    rdi
0x1400049c5  push    r14
0x1400049c7  sub     rsp, 20h
0x1400049cb  mov     r14, r8
0x1400049ce  mov     rsi, rdx
0x1400049d1  mov     rdi, rcx
0x1400049d4  mov     byte ptr [rdx], 0
0x1400049d7  xor     bpl, bpl
0x1400049da  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1400049e1  test    rbx, rbx
0x1400049e4  jz      loc_140004A80
0x1400049ea  call    cs:__imp_GetCurrentThreadId
0x1400049f0  mov     r9d, eax
0x1400049f3  mov     r8d, eax
0x1400049f6  shr     r8, 2
0x1400049fa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140004a04  mul     r8
0x140004a07  shr     rdx, 3
0x140004a0b  lea     rcx, [rdx+rdx*4]
0x140004a0f  add     rcx, rcx
0x140004a12  sub     r8, rcx
0x140004a15  mov     rbx, [rbx+r8*8]
0x140004a19  jmp     short loc_140004A24
0x140004a1b  cmp     [rbx], r9d
0x140004a1e  jz      short loc_140004A9B
0x140004a20  mov     rbx, [rbx+8]
0x140004a24  test    rbx, rbx
0x140004a27  jnz     short loc_140004A1B
0x140004a29  test    rbx, rbx
0x140004a2c  jz      short loc_140004A80
0x140004a2e  cmp     qword ptr [rbx], 0
0x140004a32  jz      short loc_140004A80
0x140004a34  mov     [rsi], bpl
0x140004a37  mov     r9, r14; unsigned __int64
0x140004a3a  mov     r8, rsi; char *
0x140004a3d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140004a40  mov     rcx, rdi; struct wil::FailureInfo *
0x140004a43  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140004a48  test    al, al
0x140004a4a  jz      short loc_140004A50
0x140004a4c  mov     [rdi+48h], rsi
0x140004a50  mov     rbx, [rbx]
0x140004a53  mov     al, [rbx+28h]
0x140004a56  mov     byte ptr [rbx+28h], 1
0x140004a5a  test    al, al
0x140004a5c  jnz     short loc_140004A77
0x140004a5e  mov     rcx, [rbx+8]
0x140004a62  mov     rax, [rcx]
0x140004a65  mov     rdx, rdi
0x140004a68  mov     rax, [rax]
0x140004a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004a70  or      bpl, al
0x140004a73  mov     byte ptr [rbx+28h], 0
0x140004a77  mov     rbx, [rbx+10h]
0x140004a7b  test    rbx, rbx
0x140004a7e  jnz     short loc_140004A53
0x140004a80  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140004a87  test    rax, rax
0x140004a8a  jz      short loc_140004AAC
0x140004a8c  test    bpl, bpl
0x140004a8f  jnz     short loc_140004AA1
0x140004a91  test    byte ptr [rdi+4], 2
0x140004a95  jnz     short loc_140004AA1
0x140004a97  xor     ecx, ecx
0x140004a99  jmp     short loc_140004AA3
0x140004a9b  add     rbx, 10h
0x140004a9f  jmp     short loc_140004A29
0x140004aa1  mov     cl, 1
0x140004aa3  mov     rdx, rdi
0x140004aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004aab  nop
0x140004aac  call    cs:__imp_GetCurrentThreadId
0x140004ab2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004ab8  cmp     ecx, eax
0x140004aba  jz      loc_140004BBC
0x140004ac0  mov     ecx, 1
0x140004ac5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140004acd  inc     ecx; this
0x140004acf  cmp     ecx, 4
0x140004ad2  jge     loc_140004BB5
0x140004ad8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004ade  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140004ae3  mov     rbx, rax
0x140004ae6  test    rax, rax
0x140004ae9  jz      loc_140004BAB
0x140004aef  mov     esi, [rax+10h]
0x140004af2  mov     ebp, 50h ; 'P'
0x140004af7  cmp     qword ptr [rax+18h], 0
0x140004afc  jnz     short loc_140004B33
0x140004afe  test    esi, esi
0x140004b00  jz      short loc_140004B33
0x140004b02  mov     edx, 190h; dwBytes
0x140004b07  lea     ecx, [rbp-48h]; dwFlags
0x140004b0a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004b0f  mov     [rbx+18h], rax
0x140004b13  test    rax, rax
0x140004b16  jz      short loc_140004B33
0x140004b18  mov     dword ptr [rbx+20h], 5
0x140004b1f  lea     rcx, [rax+190h]
0x140004b26  jmp     short loc_140004B2E
0x140004b28  mov     [rax], bp
0x140004b2b  add     rax, rbp
0x140004b2e  cmp     rax, rcx
0x140004b31  jnz     short loc_140004B28
0x140004b33  mov     r9, [rbx+18h]
0x140004b37  test    r9, r9
0x140004b3a  jz      short loc_140004BAB
0x140004b3c  test    esi, esi
0x140004b3e  jz      short loc_140004B71
0x140004b40  mov     rcx, r9
0x140004b43  movzx   eax, word ptr [rbx+20h]
0x140004b47  lea     rdx, [rax+rax*4]
0x140004b4b  shl     rdx, 4
0x140004b4f  add     rdx, r9
0x140004b52  cmp     r9, rdx
0x140004b55  jz      short loc_140004B71
0x140004b57  mov     r8d, [rbx+10h]
0x140004b5b  cmp     [rcx+4], r8d
0x140004b5f  jbe     short loc_140004B69
0x140004b61  mov     eax, [rdi+8]
0x140004b64  cmp     [rcx+8], eax
0x140004b67  jz      short loc_140004BAB
0x140004b69  add     rcx, rbp
0x140004b6c  cmp     rcx, rdx
0x140004b6f  jnz     short loc_140004B5B
0x140004b71  movzx   eax, word ptr [rbx+22h]
0x140004b75  inc     eax
0x140004b77  movzx   ecx, word ptr [rbx+20h]
0x140004b7b  xor     edx, edx
0x140004b7d  div     ecx
0x140004b7f  mov     [rbx+22h], dx
0x140004b83  mov     rax, [rbx+8]
0x140004b87  mov     r8d, 1
0x140004b8d  lock xadd [rax], r8d
0x140004b92  inc     r8d; unsigned int
0x140004b95  movzx   eax, dx
0x140004b98  lea     rcx, [rax+rax*4]
0x140004b9c  shl     rcx, 4
0x140004ba0  add     rcx, r9; this
0x140004ba3  mov     rdx, rdi; struct wil::FailureInfo *
0x140004ba6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140004bab  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140004bb5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140004bbc  add     rsp, 20h
0x140004bc0  pop     r14
0x140004bc2  pop     rdi
0x140004bc3  pop     rsi
0x140004bc4  pop     rbp
0x140004bc5  pop     rbx
0x140004bc6  retn
```
