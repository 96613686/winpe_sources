# wil::SetLastError(wil::FailureInfo const &)

- ea: `0x1800114c4`
- end: `0x18001152a`
- name: `?SetLastError@wil@@YAXAEBUFailureInfo@1@@Z`
- size: `102`
- prototype: `void __fastcall(struct wil::FailureInfo *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800113e0`

## callees

- `0x1800114c4`
- `0x180011530`
- `0x180011608`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800114cd`
- `KERNEL32!GetCurrentThreadId` at `0x1800114cd`

## pseudocode

```c
void __fastcall wil::SetLastError(struct wil::FailureInfo *this, const struct wil::FailureInfo *a2)
{
  DWORD CurrentThreadId; // eax
  wil::details_abi *v4; // rcx
  int v5; // edx
  wil::details_abi::ThreadLocalData *ThreadLocalDataCache; // rax

  CurrentThreadId = GetCurrentThreadId();
  if ( `wil::SetLastError'::`2'::lastThread != CurrentThreadId )
  {
    v5 = _InterlockedIncrement(&`wil::SetLastError'::`5'::depth);
    if ( v5 < 4 )
    {
      `wil::SetLastError'::`2'::lastThread = CurrentThreadId;
      ThreadLocalDataCache = wil::details_abi::GetThreadLocalDataCache(v4, v5);
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
0x1800114c4  push    rbx
0x1800114c6  sub     rsp, 20h
0x1800114ca  mov     rbx, rcx
0x1800114cd  call    cs:__imp_GetCurrentThreadId
0x1800114d4  nop     dword ptr [rax+rax+00h]
0x1800114d9  mov     edx, cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800114df  cmp     edx, eax
0x1800114e1  jz      short loc_180011523
0x1800114e3  mov     edx, 1
0x1800114e8  lock xadd cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC, edx; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x1800114f0  inc     edx; bool
0x1800114f2  cmp     edx, 4
0x1800114f5  jge     short loc_18001151C
0x1800114f7  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, eax; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x1800114fd  call    ?GetThreadLocalDataCache@details_abi@wil@@YAPEAUThreadLocalData@12@_N@Z; wil::details_abi::GetThreadLocalDataCache(bool)
0x180011502  test    rax, rax
0x180011505  jz      short loc_180011512
0x180011507  mov     rdx, rbx; struct wil::FailureInfo *
0x18001150a  mov     rcx, rax; this
0x18001150d  call    ?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z; wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)
0x180011512  mov     cs:?lastThread@?1??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4IC, 0; uint volatile `wil::SetLastError(wil::FailureInfo const &)'::`2'::lastThread
0x18001151c  lock dec cs:?depth@?4??SetLastError@wil@@YAXAEBUFailureInfo@2@@Z@4JC; long volatile `wil::SetLastError(wil::FailureInfo const &)'::`5'::depth
0x180011523  add     rsp, 20h
0x180011527  pop     rbx
0x180011528  retn
```
