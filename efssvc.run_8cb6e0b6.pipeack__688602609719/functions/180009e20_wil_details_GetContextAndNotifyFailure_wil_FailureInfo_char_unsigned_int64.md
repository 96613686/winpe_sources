# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180009e20`
- end: `0x18000a033`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `531`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180009e20`
- `0x18000a3d4`
- `0x18000a4c0`
- `0x18000af2c`
- `0x18000b648`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009e4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009f11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009e4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009f11`

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
0x180009e20  push    rbx
0x180009e22  push    rbp
0x180009e23  push    rsi
0x180009e24  push    rdi
0x180009e25  push    r14
0x180009e27  sub     rsp, 20h
0x180009e2b  mov     byte ptr [rdx], 0
0x180009e2e  xor     bpl, bpl
0x180009e31  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180009e38  mov     r14, r8
0x180009e3b  mov     rsi, rdx
0x180009e3e  mov     rdi, rcx
0x180009e41  test    rbx, rbx
0x180009e44  jz      loc_180009EE6
0x180009e4a  call    cs:__imp_GetCurrentThreadId
0x180009e51  nop     dword ptr [rax+rax+00h]
0x180009e56  mov     r8d, eax
0x180009e59  mov     r9d, eax
0x180009e5c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180009e66  shr     r8, 2
0x180009e6a  mul     r8
0x180009e6d  shr     rdx, 3
0x180009e71  lea     rcx, [rdx+rdx*4]
0x180009e75  add     rcx, rcx
0x180009e78  sub     r8, rcx
0x180009e7b  mov     rbx, [rbx+r8*8]
0x180009e7f  jmp     short loc_180009E8A
0x180009e81  cmp     [rbx], r9d
0x180009e84  jz      short loc_180009F01
0x180009e86  mov     rbx, [rbx+8]
0x180009e8a  test    rbx, rbx
0x180009e8d  jnz     short loc_180009E81
0x180009e8f  test    rbx, rbx
0x180009e92  jz      short loc_180009EE6
0x180009e94  cmp     qword ptr [rbx], 0
0x180009e98  jz      short loc_180009EE6
0x180009e9a  mov     [rsi], bpl
0x180009e9d  mov     r9, r14; unsigned __int64
0x180009ea0  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180009ea3  mov     r8, rsi; char *
0x180009ea6  mov     rcx, rdi; struct wil::FailureInfo *
0x180009ea9  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180009eae  test    al, al
0x180009eb0  jz      short loc_180009EB6
0x180009eb2  mov     [rdi+48h], rsi
0x180009eb6  mov     rbx, [rbx]
0x180009eb9  mov     al, [rbx+28h]
0x180009ebc  mov     byte ptr [rbx+28h], 1
0x180009ec0  test    al, al
0x180009ec2  jnz     short loc_180009EDD
0x180009ec4  mov     rcx, [rbx+8]
0x180009ec8  mov     rdx, rdi
0x180009ecb  mov     rax, [rcx]
0x180009ece  mov     rax, [rax]
0x180009ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ed6  or      bpl, al
0x180009ed9  mov     byte ptr [rbx+28h], 0
0x180009edd  mov     rbx, [rbx+10h]
0x180009ee1  test    rbx, rbx
0x180009ee4  jnz     short loc_180009EB9
0x180009ee6  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180009eed  test    rax, rax
0x180009ef0  jz      short loc_180009F11
0x180009ef2  test    bpl, bpl
0x180009ef5  jnz     short loc_180009F07
0x180009ef7  test    byte ptr [rdi+4], 2
0x180009efb  jnz     short loc_180009F07
0x180009efd  xor     ecx, ecx
0x180009eff  jmp     short loc_180009F09
0x180009f01  add     rbx, 10h
0x180009f05  jmp     short loc_180009E8F
0x180009f07  mov     cl, 1
0x180009f09  mov     rdx, rdi
0x180009f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f11  call    cs:__imp_GetCurrentThreadId
0x180009f18  nop     dword ptr [rax+rax+00h]
0x180009f1d  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009f23  cmp     ecx, eax
0x180009f25  jz      loc_18000A027
0x180009f2b  mov     ecx, 1
0x180009f30  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180009f38  inc     ecx; this
0x180009f3a  cmp     ecx, 4
0x180009f3d  jge     loc_18000A020
0x180009f43  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180009f49  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180009f4e  mov     rbx, rax
0x180009f51  test    rax, rax
0x180009f54  jz      loc_18000A016
0x180009f5a  cmp     qword ptr [rax+18h], 0
0x180009f5f  mov     ebp, 50h ; 'P'
0x180009f64  mov     esi, [rax+10h]
0x180009f67  jnz     short loc_180009F9E
0x180009f69  test    esi, esi
0x180009f6b  jz      short loc_180009F9E
0x180009f6d  mov     edx, 190h; dwBytes
0x180009f72  lea     ecx, [rbp-48h]; dwFlags
0x180009f75  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009f7a  mov     [rbx+18h], rax
0x180009f7e  test    rax, rax
0x180009f81  jz      short loc_180009F9E
0x180009f83  mov     dword ptr [rbx+20h], 5
0x180009f8a  lea     rcx, [rax+190h]
0x180009f91  jmp     short loc_180009F99
0x180009f93  mov     [rax], bp
0x180009f96  add     rax, rbp
0x180009f99  cmp     rax, rcx
0x180009f9c  jnz     short loc_180009F93
0x180009f9e  mov     r9, [rbx+18h]
0x180009fa2  test    r9, r9
0x180009fa5  jz      short loc_18000A016
0x180009fa7  test    esi, esi
0x180009fa9  jz      short loc_180009FDC
0x180009fab  movzx   eax, word ptr [rbx+20h]
0x180009faf  mov     rcx, r9
0x180009fb2  lea     rdx, [rax+rax*4]
0x180009fb6  shl     rdx, 4
0x180009fba  add     rdx, r9
0x180009fbd  cmp     r9, rdx
0x180009fc0  jz      short loc_180009FDC
0x180009fc2  mov     r8d, [rbx+10h]
0x180009fc6  cmp     [rcx+4], r8d
0x180009fca  jbe     short loc_180009FD4
0x180009fcc  mov     eax, [rdi+8]
0x180009fcf  cmp     [rcx+8], eax
0x180009fd2  jz      short loc_18000A016
0x180009fd4  add     rcx, rbp
0x180009fd7  cmp     rcx, rdx
0x180009fda  jnz     short loc_180009FC6
0x180009fdc  movzx   eax, word ptr [rbx+22h]
0x180009fe0  xor     edx, edx
0x180009fe2  movzx   ecx, word ptr [rbx+20h]
0x180009fe6  inc     eax
0x180009fe8  div     ecx
0x180009fea  mov     rax, [rbx+8]
0x180009fee  mov     r8d, 1
0x180009ff4  mov     [rbx+22h], dx
0x180009ff8  lock xadd [rax], r8d
0x180009ffd  movzx   eax, dx
0x18000a000  inc     r8d; unsigned int
0x18000a003  mov     rdx, rdi; struct wil::FailureInfo *
0x18000a006  lea     rcx, [rax+rax*4]
0x18000a00a  shl     rcx, 4
0x18000a00e  add     rcx, r9; this
0x18000a011  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000a016  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000a020  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000a027  add     rsp, 20h
0x18000a02b  pop     r14
0x18000a02d  pop     rdi
0x18000a02e  pop     rsi
0x18000a02f  pop     rbp
0x18000a030  pop     rbx
0x18000a031  retn
```
