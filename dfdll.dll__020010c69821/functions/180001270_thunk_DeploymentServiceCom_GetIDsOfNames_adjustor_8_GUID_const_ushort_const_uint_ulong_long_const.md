# [thunk]:DeploymentServiceCom::GetIDsOfNames`adjustor{8}' (_GUID const &,ushort * * const,uint,ulong,long * const)

- ea: `0x180001270`
- end: `0x180001279`
- name: `?GetIDsOfNames@DeploymentServiceCom@@W7EAAJAEBU_GUID@@QEAPEAGIKQEAJ@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001220`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::GetIDsOfNames(
        __int64 a1,
        const struct _GUID *a2,
        unsigned __int16 **a3,
        unsigned int a4,
        unsigned int a5,
        int *a6)
{
  return DeploymentServiceCom::GetIDsOfNames((DeploymentServiceCom *)(a1 - 8), a2, a3, a4, a5, a6);
}

```

## disassembly

```asm
0x180001270  sub     rcx, 8; this
0x180001274  jmp     ?GetIDsOfNames@DeploymentServiceCom@@UEAAJAEBU_GUID@@QEAPEAGIKQEAJ@Z; DeploymentServiceCom::GetIDsOfNames(_GUID const &,ushort * * const,uint,ulong,long * const)
```
