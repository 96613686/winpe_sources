# wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x180010410`
- end: `0x18001042b`
- name: `?IgnoreCurrentThread@?$ActivityBase@VFileExplorerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `27`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800114fc`
- `0x1800115e0`
- `0x180011810`

## callees

- `0x180010410`
- `0x180011a3c`

## pseudocode

```c
void __fastcall wil::ActivityBase<FileExplorerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  v1 = (wil::details::ThreadFailureCallbackHolder *)(a1 + 288);
  if ( *((_DWORD *)v1 + 6) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(v1);
}

```

## disassembly

```asm
0x180010410  sub     rsp, 28h
0x180010414  add     rcx, 120h; this
0x18001041b  cmp     dword ptr [rcx+18h], 0
0x18001041f  jz      short loc_180010426
0x180010421  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180010426  add     rsp, 28h
0x18001042a  retn
```
