# CProvisioningCommandsClassFactory::AddRef(void)

- ea: `0x1800034c0`
- end: `0x1800034cd`
- name: `?AddRef@CProvisioningCommandsClassFactory@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CProvisioningCommandsClassFactory *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsClassFactory::AddRef(CProvisioningCommandsClassFactory *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x1800034c0  mov     eax, 1
0x1800034c5  lock xadd [rcx+8], eax
0x1800034ca  inc     eax
0x1800034cc  retn
```
