# wil::SetLastError(wil::FailureInfo const &)

- ea: `0x18001fc80`
- end: `0x18001fcdf`
- name: `?SetLastError@wil@@YAXAEBUFailureInfo@1@@Z`
- size: `95`
- prototype: `void __fastcall(wil *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001b7e0`

## callees

- `0x18001fc80`
- `0x180025dec`
- `0x1800268e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fc89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fc89`

## pseudocode

```c
void __fastcall wil::SetLastError(wil *this, const struct wil::FailureInfo *a2)
{
  DWORD CurrentThreadId; // eax
  wil::details_abi *v4; // rcx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  CurrentThreadId = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != CurrentThreadId )
  {
    if ( _InterlockedIncrement(&`wil::SetLastError'::`5'::depth) < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = CurrentThreadId;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v4);
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
0x18001fc80  push    rbx
0x18001fc82  sub     rsp, 20h
0x18001fc86  mov     rbx, rcx
0x18001fc89  call    cs:__imp_GetCurrentThreadId
0x18001fc8f  mov     edx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001fc95  cmp     edx, eax
0x18001fc97  jz      short loc_18001FCD9
0x18001fc99  mov     edx, 1
0x18001fc9e  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, edx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001fca6  inc     edx; bool
0x18001fca8  cmp     edx, 4
0x18001fcab  jge     short loc_18001FCD2
0x18001fcad  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001fcb3  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x18001fcb8  test    rax, rax
0x18001fcbb  jz      short loc_18001FCC8
0x18001fcbd  mov     rdx, rbx; struct wil::FailureInfo *
0x18001fcc0  mov     rcx, rax; this
0x18001fcc3  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x18001fcc8  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001fcd2  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x18001fcd9  add     rsp, 20h
0x18001fcdd  pop     rbx
0x18001fcde  retn
```
