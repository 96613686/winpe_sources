# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x1800057b0`
- end: `0x180005814`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `100`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::FailureInfo *, char *, unsigned __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800056a0`
- `0x1800057b0`
- `0x180005d88`
- `0x180006eb8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057be`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(wil::details *this, struct wil::FailureInfo *a2, char *a3)
{
  DWORD CurrentThreadId; // eax
  wil::details_abi *v5; // rcx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(
    (unsigned __int64)this,
    (char *)a2,
    (unsigned __int64)a3);
  CurrentThreadId = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != CurrentThreadId )
  {
    if ( _InterlockedIncrement(&`wil::SetLastError'::`5'::depth) < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = CurrentThreadId;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v5);
      if ( ThreadLocalDataCache )
        wil::details_abi::ThreadLocalData::SetLastError(ThreadLocalDataCache, this);
      `wil::SetLastError'::`2'::lastThread = 0;
    }
    _InterlockedDecrement(&`wil::SetLastError'::`5'::depth);
  }
}

```

## disassembly

```asm
0x1800057b0  push    rbx
0x1800057b2  sub     rsp, 20h
0x1800057b6  mov     rbx, rcx
0x1800057b9  call    ?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)
0x1800057be  call    cs:__imp_GetCurrentThreadId
0x1800057c4  mov     edx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800057ca  cmp     edx, eax
0x1800057cc  jz      short loc_18000580E
0x1800057ce  mov     edx, 1
0x1800057d3  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, edx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800057db  inc     edx; bool
0x1800057dd  cmp     edx, 4
0x1800057e0  jge     short loc_180005807
0x1800057e2  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800057e8  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x1800057ed  test    rax, rax
0x1800057f0  jz      short loc_1800057FD
0x1800057f2  mov     rdx, rbx; struct wil::FailureInfo *
0x1800057f5  mov     rcx, rax; this
0x1800057f8  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x1800057fd  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180005807  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18000580e  add     rsp, 20h
0x180005812  pop     rbx
0x180005813  retn
```
