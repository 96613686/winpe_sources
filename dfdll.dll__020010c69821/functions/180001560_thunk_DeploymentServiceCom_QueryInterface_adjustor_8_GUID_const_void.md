# [thunk]:DeploymentServiceCom::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x180001560`
- end: `0x180001569`
- name: `?QueryInterface@DeploymentServiceCom@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800014d0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::QueryInterface(__int64 a1, const struct _GUID *a2, void **a3)
{
  return DeploymentServiceCom::QueryInterface((DeploymentServiceCom *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x180001560  sub     rcx, 8; this
0x180001564  jmp     ?QueryInterface@DeploymentServiceCom@@UEAAJAEBU_GUID@@PEAPEAX@Z; DeploymentServiceCom::QueryInterface(_GUID const &,void * *)
```
