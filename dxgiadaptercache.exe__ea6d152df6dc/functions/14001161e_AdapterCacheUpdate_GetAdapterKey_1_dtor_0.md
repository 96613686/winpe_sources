# _AdapterCacheUpdate::GetAdapterKey_::_1_::dtor$0

- ea: `0x14001161e`
- end: `0x14001162a`
- name: `_AdapterCacheUpdate::GetAdapterKey_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140006198`

## pseudocode

```c
__int64 __fastcall AdapterCacheUpdate::GetAdapterKey_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFn<_lambda_7cc52a65bce916bca787c1c779c224e9_>::~ScopeExitFn<_lambda_7cc52a65bce916bca787c1c779c224e9_>(a2 + 160);
}

```

## disassembly

```asm
0x14001161e  lea     rcx, [rdx+0A0h]
0x140011625  jmp     ??1?$ScopeExitFn@V_lambda_7cc52a65bce916bca787c1c779c224e9_@@@details@wil@@QEAA@XZ; wil::details::ScopeExitFn<_lambda_7cc52a65bce916bca787c1c779c224e9_>::~ScopeExitFn<_lambda_7cc52a65bce916bca787c1c779c224e9_>(void)
```
