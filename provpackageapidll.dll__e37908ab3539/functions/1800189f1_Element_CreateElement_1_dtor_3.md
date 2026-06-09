# _Element::CreateElement_::_1_::dtor$3

- ea: `0x1800189f1`
- end: `0x1800189fd`
- name: `_Element::CreateElement_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180014784`

## pseudocode

```c
__int64 __fastcall Element::CreateElement_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFn__lambda_fb9e59e85ad4a735f045440e2f3c470a___::_ScopeExitFn__lambda_fb9e59e85ad4a735f045440e2f3c470a___(a2 + 64);
}

```

## disassembly

```asm
0x1800189f1  lea     rcx, [rdx+40h]
0x1800189f8  jmp     wil__details__ScopeExitFn__lambda_fb9e59e85ad4a735f045440e2f3c470a______ScopeExitFn__lambda_fb9e59e85ad4a735f045440e2f3c470a___
```
