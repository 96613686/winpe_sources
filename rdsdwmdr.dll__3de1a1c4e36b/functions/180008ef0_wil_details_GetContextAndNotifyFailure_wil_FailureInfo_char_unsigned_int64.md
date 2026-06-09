# wil::details::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)

- ea: `0x180008ef0`
- end: `0x180008f54`
- name: `?GetContextAndNotifyFailure@details@wil@@YAXPEAUFailureInfo@2@PEAD_K@Z`
- size: `100`
- prototype: `void __fastcall(wil::details *this, struct wil::FailureInfo *, char *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180008e24`
- `0x180008ef0`
- `0x180009cd0`
- `0x18000c3ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008efe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008efe`

## pseudocode

```c
void __fastcall wil::details::GetContextAndNotifyFailure(wil::details *this, struct wil::FailureInfo *a2, char *a3)
{
  DWORD CurrentThreadId; // eax
  wil::details_abi *v5; // rcx
  int v6; // edx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(this, (char *)a2, (unsigned __int64)a3);
  CurrentThreadId = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != CurrentThreadId )
  {
    v6 = _InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( v6 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = CurrentThreadId;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v5, v6);
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
0x180008ef0  push    rbx
0x180008ef2  sub     rsp, 20h
0x180008ef6  mov     rbx, rcx
0x180008ef9  call    ?GetContextAndNotifyFailure@ThreadFailureCallbackHolder@details@wil@@SAXPEAUFailureInfo@3@PEAD_K@Z; wil::details::ThreadFailureCallbackHolder::GetContextAndNotifyFailure(wil::FailureInfo *,char *,unsigned __int64)
0x180008efe  call    cs:__imp_GetCurrentThreadId
0x180008f04  mov     edx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008f0a  cmp     edx, eax
0x180008f0c  jz      short loc_180008F4E
0x180008f0e  mov     edx, 1
0x180008f13  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, edx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180008f1b  inc     edx; bool
0x180008f1d  cmp     edx, 4
0x180008f20  jge     short loc_180008F47
0x180008f22  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008f28  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180008f2d  test    rax, rax
0x180008f30  jz      short loc_180008F3D
0x180008f32  mov     rdx, rbx; struct wil::FailureInfo *
0x180008f35  mov     rcx, rax; this
0x180008f38  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180008f3d  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x180008f47  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180008f4e  add     rsp, 20h
0x180008f52  pop     rbx
0x180008f53  retn
```
