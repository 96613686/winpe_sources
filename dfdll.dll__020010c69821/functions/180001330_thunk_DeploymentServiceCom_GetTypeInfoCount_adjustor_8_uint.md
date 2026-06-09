# [thunk]:DeploymentServiceCom::GetTypeInfoCount`adjustor{8}' (uint *)

- ea: `0x180001330`
- end: `0x180001339`
- name: `?GetTypeInfoCount@DeploymentServiceCom@@W7EAAJPEAI@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001300`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::GetTypeInfoCount(__int64 a1, unsigned int *a2)
{
  return DeploymentServiceCom::GetTypeInfoCount((DeploymentServiceCom *)(a1 - 8), a2);
}

```

## disassembly

```asm
0x180001330  sub     rcx, 8; this
0x180001334  jmp     ?GetTypeInfoCount@DeploymentServiceCom@@UEAAJPEAI@Z; DeploymentServiceCom::GetTypeInfoCount(uint *)
```
