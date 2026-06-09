# _DevhlprGetReaderImageNameInternal_::_1_::dtor$19

- ea: `0x1800247c0`
- end: `0x1800247cc`
- name: `_DevhlprGetReaderImageNameInternal_::_1_::dtor$19`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180014090`

## pseudocode

```c
__int64 __fastcall DevhlprGetReaderImageNameInternal_::_1_::dtor_19(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFnGuard__lambda_650b069bedae799f787ef4ee3bedeed8___::_ScopeExitFnGuard__lambda_650b069bedae799f787ef4ee3bedeed8___(a2 + 176);
}

```

## disassembly

```asm
0x1800247c0  lea     rcx, [rdx+0B0h]
0x1800247c7  jmp     wil__details__ScopeExitFnGuard__lambda_650b069bedae799f787ef4ee3bedeed8______ScopeExitFnGuard__lambda_650b069bedae799f787ef4ee3bedeed8___
```
