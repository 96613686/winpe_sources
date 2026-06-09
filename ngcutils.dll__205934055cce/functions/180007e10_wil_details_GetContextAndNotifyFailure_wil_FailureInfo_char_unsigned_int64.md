# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180007e10`
- end: `0x180008017`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180007e10`
- `0x18000850c`
- `0x1800085f0`
- `0x180008e04`
- `0x18000a6a4`
- `0x180061010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007efc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007efc`

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
0x180007e10  push    rbx
0x180007e12  push    rbp
0x180007e13  push    rsi
0x180007e14  push    rdi
0x180007e15  push    r14
0x180007e17  sub     rsp, 20h
0x180007e1b  mov     r14, r8
0x180007e1e  mov     rsi, rdx
0x180007e21  mov     rdi, rcx
0x180007e24  mov     byte ptr [rdx], 0
0x180007e27  xor     bpl, bpl
0x180007e2a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x180007e31  test    rbx, rbx
0x180007e34  jz      loc_180007ED0
0x180007e3a  call    cs:__imp_GetCurrentThreadId
0x180007e40  mov     r9d, eax
0x180007e43  mov     r8d, eax
0x180007e46  shr     r8, 2
0x180007e4a  mov     rax, 0CCCCCCCCCCCCCCCDh
0x180007e54  mul     r8
0x180007e57  shr     rdx, 3
0x180007e5b  lea     rcx, [rdx+rdx*4]
0x180007e5f  add     rcx, rcx
0x180007e62  sub     r8, rcx
0x180007e65  mov     rbx, [rbx+r8*8]
0x180007e69  jmp     short loc_180007E74
0x180007e6b  cmp     [rbx], r9d
0x180007e6e  jz      short loc_180007EEB
0x180007e70  mov     rbx, [rbx+8]
0x180007e74  test    rbx, rbx
0x180007e77  jnz     short loc_180007E6B
0x180007e79  test    rbx, rbx
0x180007e7c  jz      short loc_180007ED0
0x180007e7e  cmp     qword ptr [rbx], 0
0x180007e82  jz      short loc_180007ED0
0x180007e84  mov     [rsi], bpl
0x180007e87  mov     r9, r14; unsigned __int64
0x180007e8a  mov     r8, rsi; char *
0x180007e8d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x180007e90  mov     rcx, rdi; struct wil::FailureInfo *
0x180007e93  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x180007e98  test    al, al
0x180007e9a  jz      short loc_180007EA0
0x180007e9c  mov     [rdi+48h], rsi
0x180007ea0  mov     rbx, [rbx]
0x180007ea3  mov     al, [rbx+28h]
0x180007ea6  mov     byte ptr [rbx+28h], 1
0x180007eaa  test    al, al
0x180007eac  jnz     short loc_180007EC7
0x180007eae  mov     rcx, [rbx+8]
0x180007eb2  mov     rax, [rcx]
0x180007eb5  mov     rdx, rdi
0x180007eb8  mov     rax, [rax]
0x180007ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ec0  or      bpl, al
0x180007ec3  mov     byte ptr [rbx+28h], 0
0x180007ec7  mov     rbx, [rbx+10h]
0x180007ecb  test    rbx, rbx
0x180007ece  jnz     short loc_180007EA3
0x180007ed0  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x180007ed7  test    rax, rax
0x180007eda  jz      short loc_180007EFC
0x180007edc  test    bpl, bpl
0x180007edf  jnz     short loc_180007EF1
0x180007ee1  test    byte ptr [rdi+4], 2
0x180007ee5  jnz     short loc_180007EF1
0x180007ee7  xor     ecx, ecx
0x180007ee9  jmp     short loc_180007EF3
0x180007eeb  add     rbx, 10h
0x180007eef  jmp     short loc_180007E79
0x180007ef1  mov     cl, 1
0x180007ef3  mov     rdx, rdi
0x180007ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007efb  nop
0x180007efc  call    cs:__imp_GetCurrentThreadId
0x180007f02  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007f08  cmp     ecx, eax
0x180007f0a  jz      loc_18000800C
0x180007f10  mov     ecx, 1
0x180007f15  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180007f1d  inc     ecx; this
0x180007f1f  cmp     ecx, 4
0x180007f22  jge     loc_180008005
0x180007f28  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180007f2e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180007f33  mov     rbx, rax
0x180007f36  test    rax, rax
0x180007f39  jz      loc_180007FFB
0x180007f3f  mov     esi, [rax+10h]
0x180007f42  mov     ebp, 50h ; 'P'
0x180007f47  cmp     qword ptr [rax+18h], 0
0x180007f4c  jnz     short loc_180007F83
0x180007f4e  test    esi, esi
0x180007f50  jz      short loc_180007F83
0x180007f52  mov     edx, 190h; dwBytes
0x180007f57  lea     ecx, [rbp-48h]; dwFlags
0x180007f5a  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007f5f  mov     [rbx+18h], rax
0x180007f63  test    rax, rax
0x180007f66  jz      short loc_180007F83
0x180007f68  mov     dword ptr [rbx+20h], 5
0x180007f6f  lea     rcx, [rax+190h]
0x180007f76  jmp     short loc_180007F7E
0x180007f78  mov     [rax], bp
0x180007f7b  add     rax, rbp
0x180007f7e  cmp     rax, rcx
0x180007f81  jnz     short loc_180007F78
0x180007f83  mov     r9, [rbx+18h]
0x180007f87  test    r9, r9
0x180007f8a  jz      short loc_180007FFB
0x180007f8c  test    esi, esi
0x180007f8e  jz      short loc_180007FC1
0x180007f90  mov     rcx, r9
0x180007f93  movzx   eax, word ptr [rbx+20h]
0x180007f97  lea     rdx, [rax+rax*4]
0x180007f9b  shl     rdx, 4
0x180007f9f  add     rdx, r9
0x180007fa2  cmp     r9, rdx
0x180007fa5  jz      short loc_180007FC1
0x180007fa7  mov     r8d, [rbx+10h]
0x180007fab  cmp     [rcx+4], r8d
0x180007faf  jbe     short loc_180007FB9
0x180007fb1  mov     eax, [rdi+8]
0x180007fb4  cmp     [rcx+8], eax
0x180007fb7  jz      short loc_180007FFB
0x180007fb9  add     rcx, rbp
0x180007fbc  cmp     rcx, rdx
0x180007fbf  jnz     short loc_180007FAB
0x180007fc1  movzx   eax, word ptr [rbx+22h]
0x180007fc5  inc     eax
0x180007fc7  movzx   ecx, word ptr [rbx+20h]
0x180007fcb  xor     edx, edx
0x180007fcd  div     ecx
0x180007fcf  mov     [rbx+22h], dx
0x180007fd3  mov     rax, [rbx+8]
0x180007fd7  mov     r8d, 1
0x180007fdd  lock xadd [rax], r8d
0x180007fe2  inc     r8d; unsigned int
0x180007fe5  movzx   eax, dx
0x180007fe8  lea     rcx, [rax+rax*4]
0x180007fec  shl     rcx, 4
0x180007ff0  add     rcx, r9; this
0x180007ff3  mov     rdx, rdi; struct wil::FailureInfo *
0x180007ff6  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180007ffb  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008005  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000800c  add     rsp, 20h
0x180008010  pop     r14
0x180008012  pop     rdi
0x180008013  pop     rsi
0x180008014  pop     rbp
0x180008015  pop     rbx
0x180008016  retn
```
