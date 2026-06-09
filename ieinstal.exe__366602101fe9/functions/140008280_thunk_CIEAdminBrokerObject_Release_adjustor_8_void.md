# [thunk]:CIEAdminBrokerObject::Release`adjustor{8}' (void)

- ea: `0x140008280`
- end: `0x140008289`
- name: `?Release@CIEAdminBrokerObject@@W7EAAKXZ`
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
  return CIEAdminBrokerObject::Release((CIEAdminBrokerObject *)(a1 - 8));
}

```

## disassembly

```asm
0x140008280  sub     rcx, 8; this
0x140008284  jmp     ?Release@CIEAdminBrokerObject@@UEAAKXZ; CIEAdminBrokerObject::Release(void)
```
