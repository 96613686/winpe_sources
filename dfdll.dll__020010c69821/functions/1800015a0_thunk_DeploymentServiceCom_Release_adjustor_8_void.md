# [thunk]:DeploymentServiceCom::Release`adjustor{8}' (void)

- ea: `0x1800015a0`
- end: `0x1800015a9`
- name: `?Release@DeploymentServiceCom@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001570`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::Release(__int64 a1)
{
  return DeploymentServiceCom::Release((DeploymentServiceCom *)(a1 - 8));
}

```

## disassembly

```asm
0x1800015a0  sub     rcx, 8; this
0x1800015a4  jmp     ?Release@DeploymentServiceCom@@UEAAKXZ; DeploymentServiceCom::Release(void)
```
