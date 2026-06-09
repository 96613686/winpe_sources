# CProvisioningCommandsClassFactory::AddRef(void)

- ea: `0x180003510`
- end: `0x18000351d`
- name: `?AddRef@CProvisioningCommandsClassFactory@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(CProvisioningCommandsClassFactory *this)`
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
0x180003510  mov     eax, 1
0x180003515  lock xadd [rcx+8], eax
0x18000351a  inc     eax
0x18000351c  retn
```
