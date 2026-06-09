# CProvisioningCommandsCSP::~CProvisioningCommandsCSP(void)

- ea: `0x180006130`
- end: `0x180006151`
- name: `??1CProvisioningCommandsCSP@@MEAA@XZ`
- size: `33`
- prototype: `void __fastcall(CProvisioningCommandsCSP *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006160`

## callees

- `0x180007f04`

## pseudocode

```c
void __fastcall CProvisioningCommandsCSP::~CProvisioningCommandsCSP(CProvisioningCommandsCSP *this)
{
  *(_QWORD *)this = &CProvisioningCommandsCSP::`vftable'{for `IConfigServiceProvider2'};
  *((_QWORD *)this + 1) = &CProvisioningCommandsCSP::`vftable'{for `ICSPValidate'};
  _InterlockedDecrement(&dword_180014AB8);
  CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(this);
}

```

## disassembly

```asm
0x180006130  lea     rax, ??_7CProvisioningCommandsCSP@@6BIConfigServiceProvider2@@@; const CProvisioningCommandsCSP::`vftable'{for `IConfigServiceProvider2'}
0x180006137  mov     [rcx], rax
0x18000613a  lea     rax, ??_7CProvisioningCommandsCSP@@6BICSPValidate@@@; const CProvisioningCommandsCSP::`vftable'{for `ICSPValidate'}
0x180006141  mov     [rcx+8], rax
0x180006145  lock dec cs:dword_180014AB8
0x18000614c  jmp     ??1CConfigServiceProvider2Impl@@UEAA@XZ; CConfigServiceProvider2Impl::~CConfigServiceProvider2Impl(void)
```
