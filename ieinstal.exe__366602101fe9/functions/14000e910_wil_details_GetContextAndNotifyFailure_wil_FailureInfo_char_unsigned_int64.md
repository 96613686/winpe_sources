# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x14000e910`
- end: `0x14000eb23`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `531`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000e910`
- `0x14000eec4`
- `0x14000efb0`
- `0x14000fafc`
- `0x14000fe74`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000e93a`
- `KERNEL32!GetCurrentThreadId` at `0x14000ea01`
- `KERNEL32!GetCurrentThreadId` at `0x14000e93a`
- `KERNEL32!GetCurrentThreadId` at `0x14000ea01`

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
0x14000e910  push    rbx
0x14000e912  push    rbp
0x14000e913  push    rsi
0x14000e914  push    rdi
0x14000e915  push    r14
0x14000e917  sub     rsp, 20h
0x14000e91b  mov     byte ptr [rdx], 0
0x14000e91e  xor     bpl, bpl
0x14000e921  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x14000e928  mov     r14, r8
0x14000e92b  mov     rsi, rdx
0x14000e92e  mov     rdi, rcx
0x14000e931  test    rbx, rbx
0x14000e934  jz      loc_14000E9D6
0x14000e93a  call    cs:__imp_GetCurrentThreadId
0x14000e941  nop     dword ptr [rax+rax+00h]
0x14000e946  mov     r8d, eax
0x14000e949  mov     r9d, eax
0x14000e94c  mov     rax, 0CCCCCCCCCCCCCCCDh
0x14000e956  shr     r8, 2
0x14000e95a  mul     r8
0x14000e95d  shr     rdx, 3
0x14000e961  lea     rcx, [rdx+rdx*4]
0x14000e965  add     rcx, rcx
0x14000e968  sub     r8, rcx
0x14000e96b  mov     rbx, [rbx+r8*8]
0x14000e96f  jmp     short loc_14000E97A
0x14000e971  cmp     [rbx], r9d
0x14000e974  jz      short loc_14000E9F1
0x14000e976  mov     rbx, [rbx+8]
0x14000e97a  test    rbx, rbx
0x14000e97d  jnz     short loc_14000E971
0x14000e97f  test    rbx, rbx
0x14000e982  jz      short loc_14000E9D6
0x14000e984  cmp     qword ptr [rbx], 0
0x14000e988  jz      short loc_14000E9D6
0x14000e98a  mov     [rsi], bpl
0x14000e98d  mov     r9, r14; unsigned __int64
0x14000e990  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x14000e993  mov     r8, rsi; char *
0x14000e996  mov     rcx, rdi; struct wil::FailureInfo *
0x14000e999  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x14000e99e  test    al, al
0x14000e9a0  jz      short loc_14000E9A6
0x14000e9a2  mov     [rdi+48h], rsi
0x14000e9a6  mov     rbx, [rbx]
0x14000e9a9  mov     al, [rbx+28h]
0x14000e9ac  mov     byte ptr [rbx+28h], 1
0x14000e9b0  test    al, al
0x14000e9b2  jnz     short loc_14000E9CD
0x14000e9b4  mov     rcx, [rbx+8]
0x14000e9b8  mov     rdx, rdi
0x14000e9bb  mov     rax, [rcx]
0x14000e9be  mov     rax, [rax]
0x14000e9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e9c6  or      bpl, al
0x14000e9c9  mov     byte ptr [rbx+28h], 0
0x14000e9cd  mov     rbx, [rbx+10h]
0x14000e9d1  test    rbx, rbx
0x14000e9d4  jnz     short loc_14000E9A9
0x14000e9d6  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x14000e9dd  test    rax, rax
0x14000e9e0  jz      short loc_14000EA01
0x14000e9e2  test    bpl, bpl
0x14000e9e5  jnz     short loc_14000E9F7
0x14000e9e7  test    byte ptr [rdi+4], 2
0x14000e9eb  jnz     short loc_14000E9F7
0x14000e9ed  xor     ecx, ecx
0x14000e9ef  jmp     short loc_14000E9F9
0x14000e9f1  add     rbx, 10h
0x14000e9f5  jmp     short loc_14000E97F
0x14000e9f7  mov     cl, 1
0x14000e9f9  mov     rdx, rdi
0x14000e9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ea01  call    cs:__imp_GetCurrentThreadId
0x14000ea08  nop     dword ptr [rax+rax+00h]
0x14000ea0d  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000ea13  cmp     ecx, eax
0x14000ea15  jz      loc_14000EB17
0x14000ea1b  mov     ecx, 1
0x14000ea20  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000ea28  inc     ecx; this
0x14000ea2a  cmp     ecx, 4
0x14000ea2d  jge     loc_14000EB10
0x14000ea33  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000ea39  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x14000ea3e  mov     rbx, rax
0x14000ea41  test    rax, rax
0x14000ea44  jz      loc_14000EB06
0x14000ea4a  cmp     qword ptr [rax+18h], 0
0x14000ea4f  mov     ebp, 50h ; 'P'
0x14000ea54  mov     esi, [rax+10h]
0x14000ea57  jnz     short loc_14000EA8E
0x14000ea59  test    esi, esi
0x14000ea5b  jz      short loc_14000EA8E
0x14000ea5d  mov     edx, 190h; dwBytes
0x14000ea62  lea     ecx, [rbp-48h]; dwFlags
0x14000ea65  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000ea6a  mov     [rbx+18h], rax
0x14000ea6e  test    rax, rax
0x14000ea71  jz      short loc_14000EA8E
0x14000ea73  mov     dword ptr [rbx+20h], 5
0x14000ea7a  lea     rcx, [rax+190h]
0x14000ea81  jmp     short loc_14000EA89
0x14000ea83  mov     [rax], bp
0x14000ea86  add     rax, rbp
0x14000ea89  cmp     rax, rcx
0x14000ea8c  jnz     short loc_14000EA83
0x14000ea8e  mov     r9, [rbx+18h]
0x14000ea92  test    r9, r9
0x14000ea95  jz      short loc_14000EB06
0x14000ea97  test    esi, esi
0x14000ea99  jz      short loc_14000EACC
0x14000ea9b  movzx   eax, word ptr [rbx+20h]
0x14000ea9f  mov     rcx, r9
0x14000eaa2  lea     rdx, [rax+rax*4]
0x14000eaa6  shl     rdx, 4
0x14000eaaa  add     rdx, r9
0x14000eaad  cmp     r9, rdx
0x14000eab0  jz      short loc_14000EACC
0x14000eab2  mov     r8d, [rbx+10h]
0x14000eab6  cmp     [rcx+4], r8d
0x14000eaba  jbe     short loc_14000EAC4
0x14000eabc  mov     eax, [rdi+8]
0x14000eabf  cmp     [rcx+8], eax
0x14000eac2  jz      short loc_14000EB06
0x14000eac4  add     rcx, rbp
0x14000eac7  cmp     rcx, rdx
0x14000eaca  jnz     short loc_14000EAB6
0x14000eacc  movzx   eax, word ptr [rbx+22h]
0x14000ead0  xor     edx, edx
0x14000ead2  movzx   ecx, word ptr [rbx+20h]
0x14000ead6  inc     eax
0x14000ead8  div     ecx
0x14000eada  mov     rax, [rbx+8]
0x14000eade  mov     r8d, 1
0x14000eae4  mov     [rbx+22h], dx
0x14000eae8  lock xadd [rax], r8d
0x14000eaed  movzx   eax, dx
0x14000eaf0  inc     r8d; unsigned int
0x14000eaf3  mov     rdx, rdi; struct wil::FailureInfo *
0x14000eaf6  lea     rcx, [rax+rax*4]
0x14000eafa  shl     rcx, 4
0x14000eafe  add     rcx, r9; this
0x14000eb01  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000eb06  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x14000eb10  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000eb17  add     rsp, 20h
0x14000eb1b  pop     r14
0x14000eb1d  pop     rdi
0x14000eb1e  pop     rsi
0x14000eb1f  pop     rbp
0x14000eb20  pop     rbx
0x14000eb21  retn
```
