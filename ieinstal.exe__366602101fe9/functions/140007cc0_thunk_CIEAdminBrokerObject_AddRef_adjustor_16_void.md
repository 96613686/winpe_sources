# [thunk]:CIEAdminBrokerObject::AddRef`adjustor{16}' (void)

- ea: `0x140007cc0`
- end: `0x140007cc9`
- name: `?AddRef@CIEAdminBrokerObject@@WBA@EAAKXZ`
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
  return CIEAdminBrokerObject::AddRef((CIEAdminBrokerObject *)(a1 - 16));
}

```

## disassembly

```asm
0x140007cc0  sub     rcx, 10h; this
0x140007cc4  jmp     ?AddRef@CIEAdminBrokerObject@@UEAAKXZ; CIEAdminBrokerObject::AddRef(void)
```
