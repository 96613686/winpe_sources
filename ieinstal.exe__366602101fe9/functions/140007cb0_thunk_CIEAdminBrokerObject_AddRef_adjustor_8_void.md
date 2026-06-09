# [thunk]:CIEAdminBrokerObject::AddRef`adjustor{8}' (void)

- ea: `0x140007cb0`
- end: `0x140007cb9`
- name: `?AddRef@CIEAdminBrokerObject@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140007ca0`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::AddRef(__int64 a1)
{
  return CIEAdminBrokerObject::AddRef((CIEAdminBrokerObject *)(a1 - 8));
}

```

## disassembly

```asm
0x140007cb0  sub     rcx, 8; this
0x140007cb4  jmp     ?AddRef@CIEAdminBrokerObject@@UEAAKXZ; CIEAdminBrokerObject::AddRef(void)
```
