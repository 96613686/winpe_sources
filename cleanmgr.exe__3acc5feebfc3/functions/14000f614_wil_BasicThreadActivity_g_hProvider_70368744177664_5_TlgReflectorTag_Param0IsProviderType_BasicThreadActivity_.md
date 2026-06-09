# wil::BasicThreadActivity<g_hProvider,70368744177664,5,_TlgReflectorTag_Param0IsProviderType>::~BasicThreadActivity<g_hProvider,70368744177664,5,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x14000f614`
- end: `0x14000f619`
- name: `??1?$BasicThreadActivity@Vg_hProvider@@$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140017819`

## callees

- `0x14000f660`

## pseudocode

```c
// attributes: thunk
void __fastcall wil::BasicThreadActivity<g_hProvider,70368744177664,5,_TlgReflectorTag_Param0IsProviderType>::~BasicThreadActivity<g_hProvider,70368744177664,5,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  _TlgActivityBase<wil::BasicThreadActivity<g_hProvider,70368744177664,5,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>::~_TlgActivityBase<wil::BasicThreadActivity<g_hProvider,70368744177664,5,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>(a1);
}

```

## disassembly

```asm
0x14000f614  jmp     ??1?$_TlgActivityBase@V?$BasicThreadActivity@Vg_hProvider@@$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsProviderType@@@wil@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<wil::BasicThreadActivity<g_hProvider,70368744177664,5,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>::~_TlgActivityBase<wil::BasicThreadActivity<g_hProvider,70368744177664,5,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>(void)
```
