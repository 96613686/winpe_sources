# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140006e70`
- end: `0x140007077`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140006e70`
- `0x140007610`
- `0x1400076f4`
- `0x1400083f8`
- `0x140009854`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006e9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006f5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006e9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006f5c`

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
0x140006e70  push    rbx
0x140006e72  push    rbp
0x140006e73  push    rsi
0x140006e74  push    rdi
0x140006e75  push    r14
0x140006e77  sub     rsp, 20h
0x140006e7b  mov     r14, r8
0x140006e7e  mov     rsi, rdx
0x140006e81  mov     rdi, rcx
0x140006e84  mov     byte ptr [rdx], 0
0x140006e87  xor     bpl, bpl
0x140006e8a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140006e91  test    rbx, rbx
0x140006e94  jz      loc_140006F30
0x140006e9a  call    cs:__imp_GetCurrentThreadId
0x140006ea0  mov     r9d, eax
0x140006ea3  mov     r8d, eax
0x140006ea6  shr     r8, 2
0x140006eaa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140006eb4  mul     r8
0x140006eb7  shr     rdx, 3
0x140006ebb  lea     rcx, [rdx+rdx*4]
0x140006ebf  add     rcx, rcx
0x140006ec2  sub     r8, rcx
0x140006ec5  mov     rbx, [rbx+r8*8]
0x140006ec9  jmp     short loc_140006ED4
0x140006ecb  cmp     [rbx], r9d
0x140006ece  jz      short loc_140006F4B
0x140006ed0  mov     rbx, [rbx+8]
0x140006ed4  test    rbx, rbx
0x140006ed7  jnz     short loc_140006ECB
0x140006ed9  test    rbx, rbx
0x140006edc  jz      short loc_140006F30
0x140006ede  cmp     qword ptr [rbx], 0
0x140006ee2  jz      short loc_140006F30
0x140006ee4  mov     [rsi], bpl
0x140006ee7  mov     r9, r14; unsigned __int64
0x140006eea  mov     r8, rsi; char *
0x140006eed  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140006ef0  mov     rcx, rdi; struct wil::FailureInfo *
0x140006ef3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140006ef8  test    al, al
0x140006efa  jz      short loc_140006F00
0x140006efc  mov     [rdi+48h], rsi
0x140006f00  mov     rbx, [rbx]
0x140006f03  mov     al, [rbx+28h]
0x140006f06  mov     byte ptr [rbx+28h], 1
0x140006f0a  test    al, al
0x140006f0c  jnz     short loc_140006F27
0x140006f0e  mov     rcx, [rbx+8]
0x140006f12  mov     rax, [rcx]
0x140006f15  mov     rdx, rdi
0x140006f18  mov     rax, [rax]
0x140006f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f20  or      bpl, al
0x140006f23  mov     byte ptr [rbx+28h], 0
0x140006f27  mov     rbx, [rbx+10h]
0x140006f2b  test    rbx, rbx
0x140006f2e  jnz     short loc_140006F03
0x140006f30  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140006f37  test    rax, rax
0x140006f3a  jz      short loc_140006F5C
0x140006f3c  test    bpl, bpl
0x140006f3f  jnz     short loc_140006F51
0x140006f41  test    byte ptr [rdi+4], 2
0x140006f45  jnz     short loc_140006F51
0x140006f47  xor     ecx, ecx
0x140006f49  jmp     short loc_140006F53
0x140006f4b  add     rbx, 10h
0x140006f4f  jmp     short loc_140006ED9
0x140006f51  mov     cl, 1
0x140006f53  mov     rdx, rdi
0x140006f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f5b  nop
0x140006f5c  call    cs:__imp_GetCurrentThreadId
0x140006f62  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140006f68  cmp     ecx, eax
0x140006f6a  jz      loc_14000706C
0x140006f70  mov     ecx, 1
0x140006f75  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140006f7d  inc     ecx; this
0x140006f7f  cmp     ecx, 4
0x140006f82  jge     loc_140007065
0x140006f88  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140006f8e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140006f93  mov     rbx, rax
0x140006f96  test    rax, rax
0x140006f99  jz      loc_14000705B
0x140006f9f  mov     esi, [rax+10h]
0x140006fa2  mov     ebp, 50h ; 'P'
0x140006fa7  cmp     qword ptr [rax+18h], 0
0x140006fac  jnz     short loc_140006FE3
0x140006fae  test    esi, esi
0x140006fb0  jz      short loc_140006FE3
0x140006fb2  mov     edx, 190h; dwBytes
0x140006fb7  lea     ecx, [rbp-48h]; dwFlags
0x140006fba  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140006fbf  mov     [rbx+18h], rax
0x140006fc3  test    rax, rax
0x140006fc6  jz      short loc_140006FE3
0x140006fc8  mov     dword ptr [rbx+20h], 5
0x140006fcf  lea     rcx, [rax+190h]
0x140006fd6  jmp     short loc_140006FDE
0x140006fd8  mov     [rax], bp
0x140006fdb  add     rax, rbp
0x140006fde  cmp     rax, rcx
0x140006fe1  jnz     short loc_140006FD8
0x140006fe3  mov     r9, [rbx+18h]
0x140006fe7  test    r9, r9
0x140006fea  jz      short loc_14000705B
0x140006fec  test    esi, esi
0x140006fee  jz      short loc_140007021
0x140006ff0  mov     rcx, r9
0x140006ff3  movzx   eax, word ptr [rbx+20h]
0x140006ff7  lea     rdx, [rax+rax*4]
0x140006ffb  shl     rdx, 4
0x140006fff  add     rdx, r9
0x140007002  cmp     r9, rdx
0x140007005  jz      short loc_140007021
0x140007007  mov     r8d, [rbx+10h]
0x14000700b  cmp     [rcx+4], r8d
0x14000700f  jbe     short loc_140007019
0x140007011  mov     eax, [rdi+8]
0x140007014  cmp     [rcx+8], eax
0x140007017  jz      short loc_14000705B
0x140007019  add     rcx, rbp
0x14000701c  cmp     rcx, rdx
0x14000701f  jnz     short loc_14000700B
0x140007021  movzx   eax, word ptr [rbx+22h]
0x140007025  inc     eax
0x140007027  movzx   ecx, word ptr [rbx+20h]
0x14000702b  xor     edx, edx
0x14000702d  div     ecx
0x14000702f  mov     [rbx+22h], dx
0x140007033  mov     rax, [rbx+8]
0x140007037  mov     r8d, 1
0x14000703d  lock xadd [rax], r8d
0x140007042  inc     r8d; unsigned int
0x140007045  movzx   eax, dx
0x140007048  lea     rcx, [rax+rax*4]
0x14000704c  shl     rcx, 4
0x140007050  add     rcx, r9; this
0x140007053  mov     rdx, rdi; struct wil::FailureInfo *
0x140007056  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000705b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140007065  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000706c  add     rsp, 20h
0x140007070  pop     r14
0x140007072  pop     rdi
0x140007073  pop     rsi
0x140007074  pop     rbp
0x140007075  pop     rbx
0x140007076  retn
```
