# wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)

- ea: `0x14000fc6c`
- end: `0x14000fc8b`
- name: `?IgnoreCurrentThread@?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ`
- size: `31`
- prototype: `void __fastcall(__int64)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x140010e00`
- `0x140011030`
- `0x140011260`
- `0x140011490`
- `0x1400116c0`
- `0x1400118f0`
- `0x140011b20`

## callees

- `0x14000fc6c`
- `0x14000fcd0`
- `0x140011d48`

## pseudocode

```c
void __fastcall wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
        __int64 a1)
{
  wil::details::ThreadFailureCallbackHolder *v1; // rcx

  if ( wil::details::ThreadFailureCallbackHolder::IsWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288)) )
    wil::details::ThreadFailureCallbackHolder::StopWatching(v1);
}

```

## disassembly

```asm
0x14000fc6c  sub     rsp, 28h
0x14000fc70  add     rcx, 120h; this
0x14000fc77  call    ?IsWatching@ThreadFailureCallbackHolder@details@wil@@QEBA_NXZ; wil::details::ThreadFailureCallbackHolder::IsWatching(void)
0x14000fc7c  test    al, al
0x14000fc7e  jz      short loc_14000FC86
0x14000fc80  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x14000fc85  nop
0x14000fc86  add     rsp, 28h
0x14000fc8a  retn
```
