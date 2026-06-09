# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180003de0`
- end: `0x180003fe7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180003de0`
- `0x1800044dc`
- `0x1800045c0`
- `0x180004e28`
- `0x180005320`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ecc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ecc`

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
0x180003de0  push    rbx
0x180003de2  push    rbp
0x180003de3  push    rsi
0x180003de4  push    rdi
0x180003de5  push    r14
0x180003de7  sub     rsp, 20h
0x180003deb  mov     r14, r8
0x180003dee  mov     rsi, rdx
0x180003df1  mov     rdi, rcx
0x180003df4  mov     byte ptr [rdx], 0
0x180003df7  xor     bpl, bpl
0x180003dfa  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180003e01  test    rbx, rbx
0x180003e04  jz      loc_180003EA0
0x180003e0a  call    cs:__imp_GetCurrentThreadId
0x180003e10  mov     r9d, eax
0x180003e13  mov     r8d, eax
0x180003e16  shr     r8, 2
0x180003e1a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180003e24  mul     r8
0x180003e27  shr     rdx, 3
0x180003e2b  lea     rcx, [rdx+rdx*4]
0x180003e2f  add     rcx, rcx
0x180003e32  sub     r8, rcx
0x180003e35  mov     rbx, [rbx+r8*8]
0x180003e39  jmp     short loc_180003E44
0x180003e3b  cmp     [rbx], r9d
0x180003e3e  jz      short loc_180003EBB
0x180003e40  mov     rbx, [rbx+8]
0x180003e44  test    rbx, rbx
0x180003e47  jnz     short loc_180003E3B
0x180003e49  test    rbx, rbx
0x180003e4c  jz      short loc_180003EA0
0x180003e4e  cmp     qword ptr [rbx], 0
0x180003e52  jz      short loc_180003EA0
0x180003e54  mov     [rsi], bpl
0x180003e57  mov     r9, r14; unsigned __int64
0x180003e5a  mov     r8, rsi; char *
0x180003e5d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180003e60  mov     rcx, rdi; struct wil::FailureInfo *
0x180003e63  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180003e68  test    al, al
0x180003e6a  jz      short loc_180003E70
0x180003e6c  mov     [rdi+48h], rsi
0x180003e70  mov     rbx, [rbx]
0x180003e73  mov     al, [rbx+28h]
0x180003e76  mov     byte ptr [rbx+28h], 1
0x180003e7a  test    al, al
0x180003e7c  jnz     short loc_180003E97
0x180003e7e  mov     rcx, [rbx+8]
0x180003e82  mov     rax, [rcx]
0x180003e85  mov     rdx, rdi
0x180003e88  mov     rax, [rax]
0x180003e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e90  or      bpl, al
0x180003e93  mov     byte ptr [rbx+28h], 0
0x180003e97  mov     rbx, [rbx+10h]
0x180003e9b  test    rbx, rbx
0x180003e9e  jnz     short loc_180003E73
0x180003ea0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180003ea7  test    rax, rax
0x180003eaa  jz      short loc_180003ECC
0x180003eac  test    bpl, bpl
0x180003eaf  jnz     short loc_180003EC1
0x180003eb1  test    byte ptr [rdi+4], 2
0x180003eb5  jnz     short loc_180003EC1
0x180003eb7  xor     ecx, ecx
0x180003eb9  jmp     short loc_180003EC3
0x180003ebb  add     rbx, 10h
0x180003ebf  jmp     short loc_180003E49
0x180003ec1  mov     cl, 1
0x180003ec3  mov     rdx, rdi
0x180003ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ecb  nop
0x180003ecc  call    cs:__imp_GetCurrentThreadId
0x180003ed2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003ed8  cmp     ecx, eax
0x180003eda  jz      loc_180003FDC
0x180003ee0  mov     ecx, 1
0x180003ee5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003eed  inc     ecx; this
0x180003eef  cmp     ecx, 4
0x180003ef2  jge     loc_180003FD5
0x180003ef8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003efe  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180003f03  mov     rbx, rax
0x180003f06  test    rax, rax
0x180003f09  jz      loc_180003FCB
0x180003f0f  mov     esi, [rax+10h]
0x180003f12  mov     ebp, 50h ; 'P'
0x180003f17  cmp     qword ptr [rax+18h], 0
0x180003f1c  jnz     short loc_180003F53
0x180003f1e  test    esi, esi
0x180003f20  jz      short loc_180003F53
0x180003f22  mov     edx, 190h; dwBytes
0x180003f27  lea     ecx, [rbp-48h]; dwFlags
0x180003f2a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180003f2f  mov     [rbx+18h], rax
0x180003f33  test    rax, rax
0x180003f36  jz      short loc_180003F53
0x180003f38  mov     dword ptr [rbx+20h], 5
0x180003f3f  lea     rcx, [rax+190h]
0x180003f46  jmp     short loc_180003F4E
0x180003f48  mov     [rax], bp
0x180003f4b  add     rax, rbp
0x180003f4e  cmp     rax, rcx
0x180003f51  jnz     short loc_180003F48
0x180003f53  mov     r9, [rbx+18h]
0x180003f57  test    r9, r9
0x180003f5a  jz      short loc_180003FCB
0x180003f5c  test    esi, esi
0x180003f5e  jz      short loc_180003F91
0x180003f60  mov     rcx, r9
0x180003f63  movzx   eax, word ptr [rbx+20h]
0x180003f67  lea     rdx, [rax+rax*4]
0x180003f6b  shl     rdx, 4
0x180003f6f  add     rdx, r9
0x180003f72  cmp     r9, rdx
0x180003f75  jz      short loc_180003F91
0x180003f77  mov     r8d, [rbx+10h]
0x180003f7b  cmp     [rcx+4], r8d
0x180003f7f  jbe     short loc_180003F89
0x180003f81  mov     eax, [rdi+8]
0x180003f84  cmp     [rcx+8], eax
0x180003f87  jz      short loc_180003FCB
0x180003f89  add     rcx, rbp
0x180003f8c  cmp     rcx, rdx
0x180003f8f  jnz     short loc_180003F7B
0x180003f91  movzx   eax, word ptr [rbx+22h]
0x180003f95  inc     eax
0x180003f97  movzx   ecx, word ptr [rbx+20h]
0x180003f9b  xor     edx, edx
0x180003f9d  div     ecx
0x180003f9f  mov     [rbx+22h], dx
0x180003fa3  mov     rax, [rbx+8]
0x180003fa7  mov     r8d, 1
0x180003fad  lock xadd [rax], r8d
0x180003fb2  inc     r8d; unsigned int
0x180003fb5  movzx   eax, dx
0x180003fb8  lea     rcx, [rax+rax*4]
0x180003fbc  shl     rcx, 4
0x180003fc0  add     rcx, r9; this
0x180003fc3  mov     rdx, rdi; struct wil::FailureInfo *
0x180003fc6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180003fcb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180003fd5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180003fdc  add     rsp, 20h
0x180003fe0  pop     r14
0x180003fe2  pop     rdi
0x180003fe3  pop     rsi
0x180003fe4  pop     rbp
0x180003fe5  pop     rbx
0x180003fe6  retn
```
