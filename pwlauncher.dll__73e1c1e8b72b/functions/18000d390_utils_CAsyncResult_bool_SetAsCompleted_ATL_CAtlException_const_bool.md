# utils::CAsyncResult<bool>::SetAsCompleted(ATL::CAtlException const &,bool)

- ea: `0x18000d390`
- end: `0x18000d395`
- name: `?SetAsCompleted@?$CAsyncResult@_N@utils@@UEAAXAEBVCAtlException@ATL@@_N@Z`
- size: `5`
- prototype: `void __fastcall(utils::CAsyncResultNoResult *, const struct ATL::CAtlException *, bool)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000f880`

## pseudocode

```c
// attributes: thunk
void __fastcall utils::CAsyncResult<bool>::SetAsCompleted(
        utils::CAsyncResultNoResult *a1,
        const struct ATL::CAtlException *a2,
        bool a3)
{
  utils::CAsyncResultNoResult::SetAsCompleted(a1, a2, a3);
}

```

## disassembly

```asm
0x18000d390  jmp     ?SetAsCompleted@CAsyncResultNoResult@utils@@UEAAXAEBVCAtlException@ATL@@_N@Z; utils::CAsyncResultNoResult::SetAsCompleted(ATL::CAtlException const &,bool)
```
