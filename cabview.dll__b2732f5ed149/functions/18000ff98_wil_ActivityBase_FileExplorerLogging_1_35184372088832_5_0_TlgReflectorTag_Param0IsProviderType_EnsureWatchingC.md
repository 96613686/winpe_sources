# wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)

- ea: `0x18000ff98`
- end: `0x18000ffb3`
- name: `?EnsureWatchingCurrentThread@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `27`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180011308`
- `0x1800113c8`

## callees

- `0x18000ff98`
- `0x180011488`

## pseudocode

```c
void __fastcall wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  v1 = (wil::details::ThreadFailureCallbackHolder *)(a1 + 288);
  if ( !*((_DWORD *)v1 + 6) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(v1);
}

```

## disassembly

```asm
0x18000ff98  sub     rsp, 28h
0x18000ff9c  add     rcx, 120h; this
0x18000ffa3  cmp     dword ptr [rcx+18h], 0
0x18000ffa7  jnz     short loc_18000FFAE
0x18000ffa9  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18000ffae  add     rsp, 28h
0x18000ffb2  retn
```
