# _utils::CAsyncResultNoResult::SetAsCompleted_::_1_::dtor$0

- ea: `0x180010789`
- end: `0x180010795`
- name: `_utils::CAsyncResultNoResult::SetAsCompleted_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009920`

## pseudocode

```c
__int64 __fastcall utils::CAsyncResultNoResult::SetAsCompleted_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::tr1::shared_ptr<utils::CAsyncResultNoResult>::~shared_ptr<utils::CAsyncResultNoResult>(a2 + 64);
}

```

## disassembly

```asm
0x180010789  lea     rcx, [rdx+40h]
0x180010790  jmp     ??1?$shared_ptr@VCAsyncResultNoResult@utils@@@tr1@std@@QEAA@XZ; std::tr1::shared_ptr<utils::CAsyncResultNoResult>::~shared_ptr<utils::CAsyncResultNoResult>(void)
```
