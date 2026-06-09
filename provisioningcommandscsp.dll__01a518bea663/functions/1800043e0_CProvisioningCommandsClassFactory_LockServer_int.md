# CProvisioningCommandsClassFactory::LockServer(int)

- ea: `0x1800043e0`
- end: `0x1800043f7`
- name: `?LockServer@CProvisioningCommandsClassFactory@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(CProvisioningCommandsClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800043e0`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsClassFactory::LockServer(CProvisioningCommandsClassFactory *this, int a2)
{
  if ( a2 )
    _InterlockedIncrement(&dword_180014B04);
  else
    _InterlockedDecrement(&dword_180014B04);
  return 0;
}

```

## disassembly

```asm
0x1800043e0  test    edx, edx
0x1800043e2  jz      short loc_1800043ED
0x1800043e4  lock inc cs:dword_180014B04
0x1800043eb  jmp     short loc_1800043F4
0x1800043ed  lock dec cs:dword_180014B04
0x1800043f4  xor     eax, eax
0x1800043f6  retn
```
