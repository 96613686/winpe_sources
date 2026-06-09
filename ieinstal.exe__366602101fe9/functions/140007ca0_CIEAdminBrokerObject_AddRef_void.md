# CIEAdminBrokerObject::AddRef(void)

- ea: `0x140007ca0`
- end: `0x140007ca8`
- name: `?AddRef@CIEAdminBrokerObject@@UEAAKXZ`
- size: `8`
- prototype: `unsigned int __fastcall(CIEAdminBrokerObject *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140007cb0`
- `0x140007cc0`

## pseudocode

```c
__int64 __fastcall CIEAdminBrokerObject::AddRef(CIEAdminBrokerObject *this)
{
  _InterlockedIncrement((volatile signed __int32 *)this + 6);
  return *((unsigned int *)this + 6);
}

```

## disassembly

```asm
0x140007ca0  lock inc dword ptr [rcx+18h]
0x140007ca4  mov     eax, [rcx+18h]
0x140007ca7  retn
```
