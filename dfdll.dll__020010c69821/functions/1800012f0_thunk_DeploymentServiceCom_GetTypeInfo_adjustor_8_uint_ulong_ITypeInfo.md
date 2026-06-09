# [thunk]:DeploymentServiceCom::GetTypeInfo`adjustor{8}' (uint,ulong,ITypeInfo * *)

- ea: `0x1800012f0`
- end: `0x1800012f9`
- name: `?GetTypeInfo@DeploymentServiceCom@@W7EAAJIKPEAPEAUITypeInfo@@@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001280`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::GetTypeInfo(__int64 a1, int a2, __int64 a3, struct ITypeInfo **a4)
{
  return DeploymentServiceCom::GetTypeInfo((DeploymentServiceCom *)(a1 - 8), a2, a3, a4);
}

```

## disassembly

```asm
0x1800012f0  sub     rcx, 8; this
0x1800012f4  jmp     ?GetTypeInfo@DeploymentServiceCom@@UEAAJIKPEAPEAUITypeInfo@@@Z; DeploymentServiceCom::GetTypeInfo(uint,ulong,ITypeInfo * *)
```
