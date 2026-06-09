# _PackageSecurity::CreateCatalog_::_1_::dtor$1

- ea: `0x1800187b1`
- end: `0x1800187bd`
- name: `_PackageSecurity::CreateCatalog_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a4b8`

## pseudocode

```c
__int64 __fastcall PackageSecurity::CreateCatalog_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFn__lambda_611af3f9743d8e1948488c0440ea24e3___::_ScopeExitFn__lambda_611af3f9743d8e1948488c0440ea24e3___(a2 + 160);
}

```

## disassembly

```asm
0x1800187b1  lea     rcx, [rdx+0A0h]
0x1800187b8  jmp     wil__details__ScopeExitFn__lambda_611af3f9743d8e1948488c0440ea24e3______ScopeExitFn__lambda_611af3f9743d8e1948488c0440ea24e3___
```
