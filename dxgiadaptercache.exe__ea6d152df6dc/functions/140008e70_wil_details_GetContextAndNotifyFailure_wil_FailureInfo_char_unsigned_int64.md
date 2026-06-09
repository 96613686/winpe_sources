# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x140008e70`
- end: `0x140009077`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140008e70`
- `0x14000989c`
- `0x140009980`
- `0x14000a910`
- `0x14000ca04`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008e9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008f5c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008e9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008f5c`

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
0x140008e70  push    rbx
0x140008e72  push    rbp
0x140008e73  push    rsi
0x140008e74  push    rdi
0x140008e75  push    r14
0x140008e77  sub     rsp, 20h
0x140008e7b  mov     r14, r8
0x140008e7e  mov     rsi, rdx
0x140008e81  mov     rdi, rcx
0x140008e84  mov     byte ptr [rdx], 0
0x140008e87  xor     bpl, bpl
0x140008e8a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x140008e91  test    rbx, rbx
0x140008e94  jz      loc_140008F30
0x140008e9a  call    cs:__imp_GetCurrentThreadId
0x140008ea0  mov     r9d, eax
0x140008ea3  mov     r8d, eax
0x140008ea6  shr     r8, 2
0x140008eaa  mov     rax, 0CCCCCCCCCCCCCCCDh
0x140008eb4  mul     r8
0x140008eb7  shr     rdx, 3
0x140008ebb  lea     rcx, [rdx+rdx*4]
0x140008ebf  add     rcx, rcx
0x140008ec2  sub     r8, rcx
0x140008ec5  mov     rbx, [rbx+r8*8]
0x140008ec9  jmp     short loc_140008ED4
0x140008ecb  cmp     [rbx], r9d
0x140008ece  jz      short loc_140008F4B
0x140008ed0  mov     rbx, [rbx+8]
0x140008ed4  test    rbx, rbx
0x140008ed7  jnz     short loc_140008ECB
0x140008ed9  test    rbx, rbx
0x140008edc  jz      short loc_140008F30
0x140008ede  cmp     qword ptr [rbx], 0
0x140008ee2  jz      short loc_140008F30
0x140008ee4  mov     [rsi], bpl
0x140008ee7  mov     r9, r14; unsigned __int64
0x140008eea  mov     r8, rsi; char *
0x140008eed  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x140008ef0  mov     rcx, rdi; struct wil::FailureInfo *
0x140008ef3  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x140008ef8  test    al, al
0x140008efa  jz      short loc_140008F00
0x140008efc  mov     [rdi+48h], rsi
0x140008f00  mov     rbx, [rbx]
0x140008f03  mov     al, [rbx+28h]
0x140008f06  mov     byte ptr [rbx+28h], 1
0x140008f0a  test    al, al
0x140008f0c  jnz     short loc_140008F27
0x140008f0e  mov     rcx, [rbx+8]
0x140008f12  mov     rax, [rcx]
0x140008f15  mov     rdx, rdi
0x140008f18  mov     rax, [rax]
0x140008f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f20  or      bpl, al
0x140008f23  mov     byte ptr [rbx+28h], 0
0x140008f27  mov     rbx, [rbx+10h]
0x140008f2b  test    rbx, rbx
0x140008f2e  jnz     short loc_140008F03
0x140008f30  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140008f37  test    rax, rax
0x140008f3a  jz      short loc_140008F5C
0x140008f3c  test    bpl, bpl
0x140008f3f  jnz     short loc_140008F51
0x140008f41  test    byte ptr [rdi+4], 2
0x140008f45  jnz     short loc_140008F51
0x140008f47  xor     ecx, ecx
0x140008f49  jmp     short loc_140008F53
0x140008f4b  add     rbx, 10h
0x140008f4f  jmp     short loc_140008ED9
0x140008f51  mov     cl, 1
0x140008f53  mov     rdx, rdi
0x140008f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f5b  nop
0x140008f5c  call    cs:__imp_GetCurrentThreadId
0x140008f62  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140008f68  cmp     ecx, eax
0x140008f6a  jz      loc_14000906C
0x140008f70  mov     ecx, 1
0x140008f75  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x140008f7d  inc     ecx; this
0x140008f7f  cmp     ecx, 4
0x140008f82  jge     loc_140009065
0x140008f88  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140008f8e  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x140008f93  mov     rbx, rax
0x140008f96  test    rax, rax
0x140008f99  jz      loc_14000905B
0x140008f9f  mov     esi, [rax+10h]
0x140008fa2  mov     ebp, 50h ; 'P'
0x140008fa7  cmp     qword ptr [rax+18h], 0
0x140008fac  jnz     short loc_140008FE3
0x140008fae  test    esi, esi
0x140008fb0  jz      short loc_140008FE3
0x140008fb2  mov     edx, 190h; dwBytes
0x140008fb7  lea     ecx, [rbp-48h]; dwFlags
0x140008fba  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140008fbf  mov     [rbx+18h], rax
0x140008fc3  test    rax, rax
0x140008fc6  jz      short loc_140008FE3
0x140008fc8  mov     dword ptr [rbx+20h], 5
0x140008fcf  lea     rcx, [rax+190h]
0x140008fd6  jmp     short loc_140008FDE
0x140008fd8  mov     [rax], bp
0x140008fdb  add     rax, rbp
0x140008fde  cmp     rax, rcx
0x140008fe1  jnz     short loc_140008FD8
0x140008fe3  mov     r9, [rbx+18h]
0x140008fe7  test    r9, r9
0x140008fea  jz      short loc_14000905B
0x140008fec  test    esi, esi
0x140008fee  jz      short loc_140009021
0x140008ff0  mov     rcx, r9
0x140008ff3  movzx   eax, word ptr [rbx+20h]
0x140008ff7  lea     rdx, [rax+rax*4]
0x140008ffb  shl     rdx, 4
0x140008fff  add     rdx, r9
0x140009002  cmp     r9, rdx
0x140009005  jz      short loc_140009021
0x140009007  mov     r8d, [rbx+10h]
0x14000900b  cmp     [rcx+4], r8d
0x14000900f  jbe     short loc_140009019
0x140009011  mov     eax, [rdi+8]
0x140009014  cmp     [rcx+8], eax
0x140009017  jz      short loc_14000905B
0x140009019  add     rcx, rbp
0x14000901c  cmp     rcx, rdx
0x14000901f  jnz     short loc_14000900B
0x140009021  movzx   eax, word ptr [rbx+22h]
0x140009025  inc     eax
0x140009027  movzx   ecx, word ptr [rbx+20h]
0x14000902b  xor     edx, edx
0x14000902d  div     ecx
0x14000902f  mov     [rbx+22h], dx
0x140009033  mov     rax, [rbx+8]
0x140009037  mov     r8d, 1
0x14000903d  lock xadd [rax], r8d
0x140009042  inc     r8d; unsigned int
0x140009045  movzx   eax, dx
0x140009048  lea     rcx, [rax+rax*4]
0x14000904c  shl     rcx, 4
0x140009050  add     rcx, r9; this
0x140009053  mov     rdx, rdi; struct wil::FailureInfo *
0x140009056  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000905b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x140009065  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x14000906c  add     rsp, 20h
0x140009070  pop     r14
0x140009072  pop     rdi
0x140009073  pop     rsi
0x140009074  pop     rbp
0x140009075  pop     rbx
0x140009076  retn
```
