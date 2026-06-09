# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180005a20`
- end: `0x180005c26`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `518`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180005a20`
- `0x1800061a8`
- `0x18000628c`
- `0x1800075e4`
- `0x180009ae8`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180005a4a`
- `KERNEL32!GetCurrentThreadId` at `0x180005b0b`
- `KERNEL32!GetCurrentThreadId` at `0x180005a4a`
- `KERNEL32!GetCurrentThreadId` at `0x180005b0b`

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
0x180005a20  push    rbx
0x180005a22  push    rbp
0x180005a23  push    rsi
0x180005a24  push    rdi
0x180005a25  push    r14
0x180005a27  sub     rsp, 20h
0x180005a2b  mov     byte ptr [rdx], 0
0x180005a2e  xor     bpl, bpl
0x180005a31  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180005a38  mov     r14, r8
0x180005a3b  mov     rsi, rdx
0x180005a3e  mov     rdi, rcx
0x180005a41  test    rbx, rbx
0x180005a44  jz      loc_180005AE0
0x180005a4a  call    cs:__imp_GetCurrentThreadId
0x180005a50  mov     r8d, eax
0x180005a53  mov     r9d, eax
0x180005a56  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180005a60  shr     r8, 2
0x180005a64  mul     r8
0x180005a67  shr     rdx, 3
0x180005a6b  lea     rcx, [rdx+rdx*4]
0x180005a6f  add     rcx, rcx
0x180005a72  sub     r8, rcx
0x180005a75  mov     rbx, [rbx+r8*8]
0x180005a79  jmp     short loc_180005A84
0x180005a7b  cmp     [rbx], r9d
0x180005a7e  jz      short loc_180005AFB
0x180005a80  mov     rbx, [rbx+8]
0x180005a84  test    rbx, rbx
0x180005a87  jnz     short loc_180005A7B
0x180005a89  test    rbx, rbx
0x180005a8c  jz      short loc_180005AE0
0x180005a8e  cmp     qword ptr [rbx], 0
0x180005a92  jz      short loc_180005AE0
0x180005a94  mov     [rsi], bpl
0x180005a97  mov     r9, r14; unsigned __int64
0x180005a9a  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180005a9d  mov     r8, rsi; char *
0x180005aa0  mov     rcx, rdi; struct wil::FailureInfo *
0x180005aa3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180005aa8  test    al, al
0x180005aaa  jz      short loc_180005AB0
0x180005aac  mov     [rdi+48h], rsi
0x180005ab0  mov     rbx, [rbx]
0x180005ab3  mov     al, [rbx+28h]
0x180005ab6  mov     byte ptr [rbx+28h], 1
0x180005aba  test    al, al
0x180005abc  jnz     short loc_180005AD7
0x180005abe  mov     rcx, [rbx+8]
0x180005ac2  mov     rdx, rdi
0x180005ac5  mov     rax, [rcx]
0x180005ac8  mov     rax, [rax]
0x180005acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad0  or      bpl, al
0x180005ad3  mov     byte ptr [rbx+28h], 0
0x180005ad7  mov     rbx, [rbx+10h]
0x180005adb  test    rbx, rbx
0x180005ade  jnz     short loc_180005AB3
0x180005ae0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180005ae7  test    rax, rax
0x180005aea  jz      short loc_180005B0B
0x180005aec  test    bpl, bpl
0x180005aef  jnz     short loc_180005B01
0x180005af1  test    byte ptr [rdi+4], 2
0x180005af5  jnz     short loc_180005B01
0x180005af7  xor     ecx, ecx
0x180005af9  jmp     short loc_180005B03
0x180005afb  add     rbx, 10h
0x180005aff  jmp     short loc_180005A89
0x180005b01  mov     cl, 1
0x180005b03  mov     rdx, rdi
0x180005b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b0b  call    cs:__imp_GetCurrentThreadId
0x180005b11  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005b17  cmp     ecx, eax
0x180005b19  jz      loc_180005C1B
0x180005b1f  mov     ecx, 1
0x180005b24  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005b2c  inc     ecx; this
0x180005b2e  cmp     ecx, 4
0x180005b31  jge     loc_180005C14
0x180005b37  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005b3d  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180005b42  mov     rbx, rax
0x180005b45  test    rax, rax
0x180005b48  jz      loc_180005C0A
0x180005b4e  cmp     qword ptr [rax+18h], 0
0x180005b53  mov     ebp, 50h ; 'P'
0x180005b58  mov     esi, [rax+10h]
0x180005b5b  jnz     short loc_180005B92
0x180005b5d  test    esi, esi
0x180005b5f  jz      short loc_180005B92
0x180005b61  mov     edx, 190h; dwBytes
0x180005b66  lea     ecx, [rbp-48h]; dwFlags
0x180005b69  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005b6e  mov     [rbx+18h], rax
0x180005b72  test    rax, rax
0x180005b75  jz      short loc_180005B92
0x180005b77  mov     dword ptr [rbx+20h], 5
0x180005b7e  lea     rcx, [rax+190h]
0x180005b85  jmp     short loc_180005B8D
0x180005b87  mov     [rax], bp
0x180005b8a  add     rax, rbp
0x180005b8d  cmp     rax, rcx
0x180005b90  jnz     short loc_180005B87
0x180005b92  mov     r9, [rbx+18h]
0x180005b96  test    r9, r9
0x180005b99  jz      short loc_180005C0A
0x180005b9b  test    esi, esi
0x180005b9d  jz      short loc_180005BD0
0x180005b9f  movzx   eax, word ptr [rbx+20h]
0x180005ba3  mov     rcx, r9
0x180005ba6  lea     rdx, [rax+rax*4]
0x180005baa  shl     rdx, 4
0x180005bae  add     rdx, r9
0x180005bb1  cmp     r9, rdx
0x180005bb4  jz      short loc_180005BD0
0x180005bb6  mov     r8d, [rbx+10h]
0x180005bba  cmp     [rcx+4], r8d
0x180005bbe  jbe     short loc_180005BC8
0x180005bc0  mov     eax, [rdi+8]
0x180005bc3  cmp     [rcx+8], eax
0x180005bc6  jz      short loc_180005C0A
0x180005bc8  add     rcx, rbp
0x180005bcb  cmp     rcx, rdx
0x180005bce  jnz     short loc_180005BBA
0x180005bd0  movzx   eax, word ptr [rbx+22h]
0x180005bd4  xor     edx, edx
0x180005bd6  movzx   ecx, word ptr [rbx+20h]
0x180005bda  inc     eax
0x180005bdc  div     ecx
0x180005bde  mov     rax, [rbx+8]
0x180005be2  mov     r8d, 1
0x180005be8  mov     [rbx+22h], dx
0x180005bec  lock xadd [rax], r8d
0x180005bf1  movzx   eax, dx
0x180005bf4  inc     r8d; unsigned int
0x180005bf7  mov     rdx, rdi; struct wil::FailureInfo *
0x180005bfa  lea     rcx, [rax+rax*4]
0x180005bfe  shl     rcx, 4
0x180005c02  add     rcx, r9; this
0x180005c05  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180005c0a  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005c14  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180005c1b  add     rsp, 20h
0x180005c1f  pop     r14
0x180005c21  pop     rdi
0x180005c22  pop     rsi
0x180005c23  pop     rbp
0x180005c24  pop     rbx
0x180005c25  retn
```
