# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000c7b0`
- end: `0x18000c9b7`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `519`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000c7b0`
- `0x18000d2a0`
- `0x18000d384`
- `0x18000e6ac`
- `0x180010c4c`
- `0x180023010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000c7da`
- `KERNEL32!GetCurrentThreadId` at `0x18000c89c`
- `KERNEL32!GetCurrentThreadId` at `0x18000c7da`
- `KERNEL32!GetCurrentThreadId` at `0x18000c89c`

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
0x18000c7b0  push    rbx
0x18000c7b2  push    rbp
0x18000c7b3  push    rsi
0x18000c7b4  push    rdi
0x18000c7b5  push    r14
0x18000c7b7  sub     rsp, 20h
0x18000c7bb  mov     r14, r8
0x18000c7be  mov     rsi, rdx
0x18000c7c1  mov     rdi, rcx
0x18000c7c4  mov     byte ptr [rdx], 0
0x18000c7c7  xor     bpl, bpl
0x18000c7ca  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000c7d1  test    rbx, rbx
0x18000c7d4  jz      loc_18000C870
0x18000c7da  call    cs:__imp_GetCurrentThreadId
0x18000c7e0  mov     r9d, eax
0x18000c7e3  mov     r8d, eax
0x18000c7e6  shr     r8, 2
0x18000c7ea  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000c7f4  mul     r8
0x18000c7f7  shr     rdx, 3
0x18000c7fb  lea     rcx, [rdx+rdx*4]
0x18000c7ff  add     rcx, rcx
0x18000c802  sub     r8, rcx
0x18000c805  mov     rbx, [rbx+r8*8]
0x18000c809  jmp     short loc_18000C814
0x18000c80b  cmp     [rbx], r9d
0x18000c80e  jz      short loc_18000C88B
0x18000c810  mov     rbx, [rbx+8]
0x18000c814  test    rbx, rbx
0x18000c817  jnz     short loc_18000C80B
0x18000c819  test    rbx, rbx
0x18000c81c  jz      short loc_18000C870
0x18000c81e  cmp     qword ptr [rbx], 0
0x18000c822  jz      short loc_18000C870
0x18000c824  mov     [rsi], bpl
0x18000c827  mov     r9, r14; unsigned __int64
0x18000c82a  mov     r8, rsi; char *
0x18000c82d  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000c830  mov     rcx, rdi; struct wil::FailureInfo *
0x18000c833  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000c838  test    al, al
0x18000c83a  jz      short loc_18000C840
0x18000c83c  mov     [rdi+48h], rsi
0x18000c840  mov     rbx, [rbx]
0x18000c843  mov     al, [rbx+28h]
0x18000c846  mov     byte ptr [rbx+28h], 1
0x18000c84a  test    al, al
0x18000c84c  jnz     short loc_18000C867
0x18000c84e  mov     rcx, [rbx+8]
0x18000c852  mov     rax, [rcx]
0x18000c855  mov     rdx, rdi
0x18000c858  mov     rax, [rax]
0x18000c85b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c860  or      bpl, al
0x18000c863  mov     byte ptr [rbx+28h], 0
0x18000c867  mov     rbx, [rbx+10h]
0x18000c86b  test    rbx, rbx
0x18000c86e  jnz     short loc_18000C843
0x18000c870  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000c877  test    rax, rax
0x18000c87a  jz      short loc_18000C89C
0x18000c87c  test    bpl, bpl
0x18000c87f  jnz     short loc_18000C891
0x18000c881  test    byte ptr [rdi+4], 2
0x18000c885  jnz     short loc_18000C891
0x18000c887  xor     ecx, ecx
0x18000c889  jmp     short loc_18000C893
0x18000c88b  add     rbx, 10h
0x18000c88f  jmp     short loc_18000C819
0x18000c891  mov     cl, 1
0x18000c893  mov     rdx, rdi
0x18000c896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c89b  nop
0x18000c89c  call    cs:__imp_GetCurrentThreadId
0x18000c8a2  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000c8a8  cmp     ecx, eax
0x18000c8aa  jz      loc_18000C9AC
0x18000c8b0  mov     ecx, 1
0x18000c8b5  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000c8bd  inc     ecx; this
0x18000c8bf  cmp     ecx, 4
0x18000c8c2  jge     loc_18000C9A5
0x18000c8c8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000c8ce  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000c8d3  mov     rbx, rax
0x18000c8d6  test    rax, rax
0x18000c8d9  jz      loc_18000C99B
0x18000c8df  mov     esi, [rax+10h]
0x18000c8e2  mov     ebp, 50h ; 'P'
0x18000c8e7  cmp     qword ptr [rax+18h], 0
0x18000c8ec  jnz     short loc_18000C923
0x18000c8ee  test    esi, esi
0x18000c8f0  jz      short loc_18000C923
0x18000c8f2  mov     edx, 190h; dwBytes
0x18000c8f7  lea     ecx, [rbp-48h]; dwFlags
0x18000c8fa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000c8ff  mov     [rbx+18h], rax
0x18000c903  test    rax, rax
0x18000c906  jz      short loc_18000C923
0x18000c908  mov     dword ptr [rbx+20h], 5
0x18000c90f  lea     rcx, [rax+190h]
0x18000c916  jmp     short loc_18000C91E
0x18000c918  mov     [rax], bp
0x18000c91b  add     rax, rbp
0x18000c91e  cmp     rax, rcx
0x18000c921  jnz     short loc_18000C918
0x18000c923  mov     r9, [rbx+18h]
0x18000c927  test    r9, r9
0x18000c92a  jz      short loc_18000C99B
0x18000c92c  test    esi, esi
0x18000c92e  jz      short loc_18000C961
0x18000c930  mov     rcx, r9
0x18000c933  movzx   eax, word ptr [rbx+20h]
0x18000c937  lea     rdx, [rax+rax*4]
0x18000c93b  shl     rdx, 4
0x18000c93f  add     rdx, r9
0x18000c942  cmp     r9, rdx
0x18000c945  jz      short loc_18000C961
0x18000c947  mov     r8d, [rbx+10h]
0x18000c94b  cmp     [rcx+4], r8d
0x18000c94f  jbe     short loc_18000C959
0x18000c951  mov     eax, [rdi+8]
0x18000c954  cmp     [rcx+8], eax
0x18000c957  jz      short loc_18000C99B
0x18000c959  add     rcx, rbp
0x18000c95c  cmp     rcx, rdx
0x18000c95f  jnz     short loc_18000C94B
0x18000c961  movzx   eax, word ptr [rbx+22h]
0x18000c965  inc     eax
0x18000c967  movzx   ecx, word ptr [rbx+20h]
0x18000c96b  xor     edx, edx
0x18000c96d  div     ecx
0x18000c96f  mov     [rbx+22h], dx
0x18000c973  mov     rax, [rbx+8]
0x18000c977  mov     r8d, 1
0x18000c97d  lock xadd [rax], r8d
0x18000c982  inc     r8d; unsigned int
0x18000c985  movzx   eax, dx
0x18000c988  lea     rcx, [rax+rax*4]
0x18000c98c  shl     rcx, 4
0x18000c990  add     rcx, r9; this
0x18000c993  mov     rdx, rdi; struct wil::FailureInfo *
0x18000c996  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000c99b  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000c9a5  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000c9ac  add     rsp, 20h
0x18000c9b0  pop     r14
0x18000c9b2  pop     rdi
0x18000c9b3  pop     rsi
0x18000c9b4  pop     rbp
0x18000c9b5  pop     rbx
0x18000c9b6  retn
```
