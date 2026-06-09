# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x18000ae60`
- end: `0x18000afb4`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `340`
- prototype: `void __fastcall(unsigned __int64 this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000ae60`
- `0x18000b4a4`
- `0x18000b588`
- `0x18000eac8`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000af52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000af52`

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
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

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
      if ( ThreadLocalDataCache )
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, v5);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x18000ae60  push    rbx
0x18000ae62  push    rbp
0x18000ae63  push    rsi
0x18000ae64  push    rdi
0x18000ae65  push    r14
0x18000ae67  sub     rsp, 20h
0x18000ae6b  mov     r14, r8
0x18000ae6e  mov     rsi, rdx
0x18000ae71  mov     rdi, rcx
0x18000ae74  mov     byte ptr [rdx], 0
0x18000ae77  xor     bpl, bpl
0x18000ae7a  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000ae81  test    rbx, rbx
0x18000ae84  jz      loc_18000AF26
0x18000ae8a  call    cs:__imp_GetCurrentThreadId
0x18000ae91  nop     dword ptr [rax+rax+00h]
0x18000ae96  mov     r9d, eax
0x18000ae99  mov     r8d, eax
0x18000ae9c  shr     r8, 2
0x18000aea0  mov     rax, 0CCCCCCCCCCCCCCCDh
0x18000aeaa  mul     r8
0x18000aead  shr     rdx, 3
0x18000aeb1  lea     rcx, [rdx+rdx*4]
0x18000aeb5  add     rcx, rcx
0x18000aeb8  sub     r8, rcx
0x18000aebb  mov     rbx, [rbx+r8*8]
0x18000aebf  jmp     short loc_18000AECA
0x18000aec1  cmp     [rbx], r9d
0x18000aec4  jz      short loc_18000AF41
0x18000aec6  mov     rbx, [rbx+8]
0x18000aeca  test    rbx, rbx
0x18000aecd  jnz     short loc_18000AEC1
0x18000aecf  test    rbx, rbx
0x18000aed2  jz      short loc_18000AF26
0x18000aed4  cmp     qword ptr [rbx], 0
0x18000aed8  jz      short loc_18000AF26
0x18000aeda  mov     [rsi], bpl
0x18000aedd  mov     r9, r14; unsigned __int64
0x18000aee0  mov     r8, rsi; char *
0x18000aee3  mov     rdx, [rbx]; struct wil::details::ThreadFailureCallbackHolder *
0x18000aee6  mov     rcx, rdi; struct wil::FailureInfo *
0x18000aee9  call    ?GetThreadContext@ThreadFailureCallbackHolder@details@wil@@SA_NPEAUFailureInfo@3@PEAV123@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetThreadContext(wil::FailureInfo *,wil::details::ThreadFailureCallbackHolder *,char *,unsigned __int64)
0x18000aeee  test    al, al
0x18000aef0  jz      short loc_18000AEF6
0x18000aef2  mov     [rdi+48h], rsi
0x18000aef6  mov     rbx, [rbx]
0x18000aef9  mov     al, [rbx+28h]
0x18000aefc  mov     byte ptr [rbx+28h], 1
0x18000af00  test    al, al
0x18000af02  jnz     short loc_18000AF1D
0x18000af04  mov     rcx, [rbx+8]
0x18000af08  mov     rax, [rcx]
0x18000af0b  mov     rdx, rdi
0x18000af0e  mov     rax, [rax]
0x18000af11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af16  or      bpl, al
0x18000af19  mov     byte ptr [rbx+28h], 0
0x18000af1d  mov     rbx, [rbx+10h]
0x18000af21  test    rbx, rbx
0x18000af24  jnz     short loc_18000AEF9
0x18000af26  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x18000af2d  test    rax, rax
0x18000af30  jz      short loc_18000AF52
0x18000af32  test    bpl, bpl
0x18000af35  jnz     short loc_18000AF47
0x18000af37  test    byte ptr [rdi+4], 2
0x18000af3b  jnz     short loc_18000AF47
0x18000af3d  xor     ecx, ecx
0x18000af3f  jmp     short loc_18000AF49
0x18000af41  add     rbx, 10h
0x18000af45  jmp     short loc_18000AECF
0x18000af47  mov     cl, 1
0x18000af49  mov     rdx, rdi
0x18000af4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af51  nop
0x18000af52  call    cs:__imp_GetCurrentThreadId
0x18000af59  nop     dword ptr [rax+rax+00h]
0x18000af5e  mov     ecx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000af64  cmp     ecx, eax
0x18000af66  jz      short loc_18000AFA8
0x18000af68  mov     ecx, 1
0x18000af6d  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, ecx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000af75  inc     ecx; this
0x18000af77  cmp     ecx, 4
0x18000af7a  jge     short loc_18000AFA1
0x18000af7c  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000af82  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18000af87  test    rax, rax
0x18000af8a  jz      short loc_18000AF97
0x18000af8c  mov     rdx, rdi; struct wil::FailureInfo *
0x18000af8f  mov     rcx, rax; this
0x18000af92  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18000af97  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18000afa1  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000afa8  add     rsp, 20h
0x18000afac  pop     r14
0x18000afae  pop     rdi
0x18000afaf  pop     rsi
0x18000afb0  pop     rbp
0x18000afb1  pop     rbx
0x18000afb2  retn
```
