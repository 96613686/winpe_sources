# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180004980`
- end: `0x180004b87`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180004980`
- `0x18000507c`
- `0x180005160`
- `0x1800062a4`
- `0x180006814`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800049aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800049aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a6c`

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
0x180004980  push    rbx
0x180004982  push    rbp
0x180004983  push    rsi
0x180004984  push    rdi
0x180004985  push    r14
0x180004987  sub     rsp, 20h
0x18000498b  mov     r14, r8
0x18000498e  mov     rsi, rdx
0x180004991  mov     rdi, rcx
0x180004994  mov     byte ptr [rdx], 0
0x180004997  xor     bpl, bpl
0x18000499a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800049a1  test    rbx, rbx
0x1800049a4  jz      loc_180004A40
0x1800049aa  call    cs:__imp_GetCurrentThreadId
0x1800049b0  mov     r9d, eax
0x1800049b3  mov     r8d, eax
0x1800049b6  shr     r8, 2
0x1800049ba  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800049c4  mul     r8
0x1800049c7  shr     rdx, 3
0x1800049cb  lea     rcx, [rdx+rdx*4]
0x1800049cf  add     rcx, rcx
0x1800049d2  sub     r8, rcx
0x1800049d5  mov     rbx, [rbx+r8*8]
0x1800049d9  jmp     short loc_1800049E4
0x1800049db  cmp     [rbx], r9d
0x1800049de  jz      short loc_180004A5B
0x1800049e0  mov     rbx, [rbx+8]
0x1800049e4  test    rbx, rbx
0x1800049e7  jnz     short loc_1800049DB
0x1800049e9  test    rbx, rbx
0x1800049ec  jz      short loc_180004A40
0x1800049ee  cmp     qword ptr [rbx], 0
0x1800049f2  jz      short loc_180004A40
0x1800049f4  mov     [rsi], bpl
0x1800049f7  mov     r9, r14; unsigned __int64
0x1800049fa  mov     r8, rsi; char *
0x1800049fd  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180004a00  mov     rcx, rdi; struct wil::FailureInfo *
0x180004a03  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180004a08  test    al, al
0x180004a0a  jz      short loc_180004A10
0x180004a0c  mov     [rdi+48h], rsi
0x180004a10  mov     rbx, [rbx]
0x180004a13  mov     al, [rbx+28h]
0x180004a16  mov     byte ptr [rbx+28h], 1
0x180004a1a  test    al, al
0x180004a1c  jnz     short loc_180004A37
0x180004a1e  mov     rcx, [rbx+8]
0x180004a22  mov     rax, [rcx]
0x180004a25  mov     rdx, rdi
0x180004a28  mov     rax, [rax]
0x180004a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a30  or      bpl, al
0x180004a33  mov     byte ptr [rbx+28h], 0
0x180004a37  mov     rbx, [rbx+10h]
0x180004a3b  test    rbx, rbx
0x180004a3e  jnz     short loc_180004A13
0x180004a40  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180004a47  test    rax, rax
0x180004a4a  jz      short loc_180004A6C
0x180004a4c  test    bpl, bpl
0x180004a4f  jnz     short loc_180004A61
0x180004a51  test    byte ptr [rdi+4], 2
0x180004a55  jnz     short loc_180004A61
0x180004a57  xor     ecx, ecx
0x180004a59  jmp     short loc_180004A63
0x180004a5b  add     rbx, 10h
0x180004a5f  jmp     short loc_1800049E9
0x180004a61  mov     cl, 1
0x180004a63  mov     rdx, rdi
0x180004a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a6b  nop
0x180004a6c  call    cs:__imp_GetCurrentThreadId
0x180004a72  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004a78  cmp     ecx, eax
0x180004a7a  jz      loc_180004B7C
0x180004a80  mov     ecx, 1
0x180004a85  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004a8d  inc     ecx; this
0x180004a8f  cmp     ecx, 4
0x180004a92  jge     loc_180004B75
0x180004a98  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004a9e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180004aa3  mov     rbx, rax
0x180004aa6  test    rax, rax
0x180004aa9  jz      loc_180004B6B
0x180004aaf  mov     esi, [rax+10h]
0x180004ab2  mov     ebp, 50h ; 'P'
0x180004ab7  cmp     qword ptr [rax+18h], 0
0x180004abc  jnz     short loc_180004AF3
0x180004abe  test    esi, esi
0x180004ac0  jz      short loc_180004AF3
0x180004ac2  mov     edx, 190h; dwBytes
0x180004ac7  lea     ecx, [rbp-48h]; dwFlags
0x180004aca  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180004acf  mov     [rbx+18h], rax
0x180004ad3  test    rax, rax
0x180004ad6  jz      short loc_180004AF3
0x180004ad8  mov     dword ptr [rbx+20h], 5
0x180004adf  lea     rcx, [rax+190h]
0x180004ae6  jmp     short loc_180004AEE
0x180004ae8  mov     [rax], bp
0x180004aeb  add     rax, rbp
0x180004aee  cmp     rax, rcx
0x180004af1  jnz     short loc_180004AE8
0x180004af3  mov     r9, [rbx+18h]
0x180004af7  test    r9, r9
0x180004afa  jz      short loc_180004B6B
0x180004afc  test    esi, esi
0x180004afe  jz      short loc_180004B31
0x180004b00  mov     rcx, r9
0x180004b03  movzx   eax, word ptr [rbx+20h]
0x180004b07  lea     rdx, [rax+rax*4]
0x180004b0b  shl     rdx, 4
0x180004b0f  add     rdx, r9
0x180004b12  cmp     r9, rdx
0x180004b15  jz      short loc_180004B31
0x180004b17  mov     r8d, [rbx+10h]
0x180004b1b  cmp     [rcx+4], r8d
0x180004b1f  jbe     short loc_180004B29
0x180004b21  mov     eax, [rdi+8]
0x180004b24  cmp     [rcx+8], eax
0x180004b27  jz      short loc_180004B6B
0x180004b29  add     rcx, rbp
0x180004b2c  cmp     rcx, rdx
0x180004b2f  jnz     short loc_180004B1B
0x180004b31  movzx   eax, word ptr [rbx+22h]
0x180004b35  inc     eax
0x180004b37  movzx   ecx, word ptr [rbx+20h]
0x180004b3b  xor     edx, edx
0x180004b3d  div     ecx
0x180004b3f  mov     [rbx+22h], dx
0x180004b43  mov     rax, [rbx+8]
0x180004b47  mov     r8d, 1
0x180004b4d  lock xadd [rax], r8d
0x180004b52  inc     r8d; unsigned int
0x180004b55  movzx   eax, dx
0x180004b58  lea     rcx, [rax+rax*4]
0x180004b5c  shl     rcx, 4
0x180004b60  add     rcx, r9; this
0x180004b63  mov     rdx, rdi; struct wil::FailureInfo *
0x180004b66  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180004b6b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180004b75  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180004b7c  add     rsp, 20h
0x180004b80  pop     r14
0x180004b82  pop     rdi
0x180004b83  pop     rsi
0x180004b84  pop     rbp
0x180004b85  pop     rbx
0x180004b86  retn
```
