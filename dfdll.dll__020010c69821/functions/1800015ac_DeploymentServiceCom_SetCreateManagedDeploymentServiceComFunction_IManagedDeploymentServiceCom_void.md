# DeploymentServiceCom::SetCreateManagedDeploymentServiceComFunction(IManagedDeploymentServiceCom * (*)(void))

- ea: `0x1800015ac`
- end: `0x1800015b4`
- name: `?SetCreateManagedDeploymentServiceComFunction@DeploymentServiceCom@@SAXP6APEAUIManagedDeploymentServiceCom@@XZ@Z`
- size: `8`
- prototype: `void __fastcall(struct IManagedDeploymentServiceCom *(*)(void))`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001770`
- `0x180001830`

## pseudocode

```c
void __fastcall DeploymentServiceCom::SetCreateManagedDeploymentServiceComFunction(
        struct IManagedDeploymentServiceCom *(*a1)(void))
{
  DeploymentServiceCom::s_pCreateManagedDeploymentServiceComFunction = a1;
}

```

## disassembly

```asm
0x1800015ac  mov     cs:?s_pCreateManagedDeploymentServiceComFunction@DeploymentServiceCom@@0P6APEAUIManagedDeploymentServiceCom@@XZEA, rcx; IManagedDeploymentServiceCom * (*DeploymentServiceCom::s_pCreateManagedDeploymentServiceComFunction)(void)
0x1800015b3  retn
```
