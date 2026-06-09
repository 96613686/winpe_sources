# _Windows::Internal::ServiceModuleBase::Initialize_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor__::_1_::dtor$1

- ea: `0x1800108fa`
- end: `0x180010906`
- name: `_Windows::Internal::ServiceModuleBase::Initialize_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor__::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004118`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModuleBase::Initialize_Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal_2_Windows::Internal::DefaultServerDescriptor__::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  return Microsoft::WRL::ComPtr<IGlobalOptions>::~ComPtr<IGlobalOptions>(a2 + 144);
}

```

## disassembly

```asm
0x1800108fa  lea     rcx, [rdx+90h]
0x180010901  jmp     ??1?$ComPtr@UIGlobalOptions@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IGlobalOptions>::~ComPtr<IGlobalOptions>(void)
```
