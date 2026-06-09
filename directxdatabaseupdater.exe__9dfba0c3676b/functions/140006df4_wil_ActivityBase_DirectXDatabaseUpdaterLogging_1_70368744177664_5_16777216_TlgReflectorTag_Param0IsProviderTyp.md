# wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)

- ea: `0x140006df4`
- end: `0x140006e12`
- name: `?EnsureWatchingCurrentThread@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ`
- size: `30`
- prototype: `void __fastcall(__int64)`
- caller_count: `6`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14000ac0c`
- `0x14000ad00`
- `0x14000adcc`
- `0x14000ae8c`
- `0x14000af4c`
- `0x14000b00c`

## callees

- `0x140006df4`
- `0x14000839c`
- `0x14000b588`

## pseudocode

```c
void __fastcall wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( !wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(v1);
}

```

## disassembly

```asm
0x140006df4  sub     rsp, 28h
0x140006df8  add     rcx, 120h; this
0x140006dff  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x140006e04  test    al, al
0x140006e06  jnz     short loc_140006E0D
0x140006e08  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140006e0d  add     rsp, 28h
0x140006e11  retn
```
