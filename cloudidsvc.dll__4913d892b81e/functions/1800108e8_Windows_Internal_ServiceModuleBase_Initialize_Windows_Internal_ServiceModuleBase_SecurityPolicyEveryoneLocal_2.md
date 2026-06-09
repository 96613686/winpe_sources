# _Windows::Internal::ServiceModuleBase::Initialize_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor__::_1_::dtor$0

- ea: `0x1800108e8`
- end: `0x1800108f4`
- name: `_Windows::Internal::ServiceModuleBase::Initialize_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004474`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModuleBase::Initialize_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return wil::details::lambda_call<_lambda_0844bed45d04fee2db371e67ed993d11_>::~lambda_call<_lambda_0844bed45d04fee2db371e67ed993d11_>(a2 + 64);
}

```

## disassembly

```asm
0x1800108e8  lea     rcx, [rdx+40h]
0x1800108ef  jmp     ??1?$lambda_call@V_lambda_0844bed45d04fee2db371e67ed993d11_@@@details@wil@@QEAA@XZ; wil::details::lambda_call<_lambda_0844bed45d04fee2db371e67ed993d11_>::~lambda_call<_lambda_0844bed45d04fee2db371e67ed993d11_>(void)
```
