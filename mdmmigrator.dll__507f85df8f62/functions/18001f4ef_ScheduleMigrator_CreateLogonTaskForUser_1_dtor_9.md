# _ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$9

- ea: `0x18001f4ef`
- end: `0x18001f4fb`
- name: `_ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor$9`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000aadc`

## pseudocode

```c
__int64 __fastcall ScheduleMigrator::CreateLogonTaskForUser_::_1_::dtor_9(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFn__lambda_9e8d37036f3268db243611ba3d1003f8___::_ScopeExitFn__lambda_9e8d37036f3268db243611ba3d1003f8___(a2 + 184);
}

```

## disassembly

```asm
0x18001f4ef  lea     rcx, [rdx+0B8h]
0x18001f4f6  jmp     wil__details__ScopeExitFn__lambda_9e8d37036f3268db243611ba3d1003f8______ScopeExitFn__lambda_9e8d37036f3268db243611ba3d1003f8___
```
