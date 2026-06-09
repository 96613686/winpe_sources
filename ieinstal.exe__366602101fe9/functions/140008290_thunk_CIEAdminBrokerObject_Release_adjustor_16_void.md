# [thunk]:CIEAdminBrokerObject::Release`adjustor{16}' (void)

- ea: `0x140008290`
- end: `0x140008299`
- name: `?Release@CIEAdminBrokerObject@@WBA@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008230`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::Release(__int64 a1)
{
  return CIEAdminBrokerObject::Release((CIEAdminBrokerObject *)(a1 - 16));
}

```

## disassembly

```asm
0x140008290  sub     rcx, 10h; this
0x140008294  jmp     ?Release@CIEAdminBrokerObject@@UEAAKXZ; CIEAdminBrokerObject::Release(void)
```
