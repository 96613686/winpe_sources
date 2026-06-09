# [thunk]:DeploymentServiceCom::AddRef`adjustor{8}' (void)

- ea: `0x1800011b0`
- end: `0x1800011b9`
- name: `?AddRef@DeploymentServiceCom@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800011a0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::AddRef(__int64 a1)
{
  return DeploymentServiceCom::AddRef((DeploymentServiceCom *)(a1 - 8));
}

```

## disassembly

```asm
0x1800011b0  sub     rcx, 8; this
0x1800011b4  jmp     ?AddRef@DeploymentServiceCom@@UEAAKXZ; DeploymentServiceCom::AddRef(void)
```
