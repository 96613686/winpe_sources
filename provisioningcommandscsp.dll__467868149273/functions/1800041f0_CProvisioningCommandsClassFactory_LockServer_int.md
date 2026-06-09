# CProvisioningCommandsClassFactory::LockServer(int)

- ea: `0x1800041f0`
- end: `0x180004207`
- name: `?LockServer@CProvisioningCommandsClassFactory@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(CProvisioningCommandsClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800041f0`

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
0x1800041f0  test    edx, edx
0x1800041f2  jz      short loc_1800041FD
0x1800041f4  lock inc cs:dword_180014B04
0x1800041fb  jmp     short loc_180004204
0x1800041fd  lock dec cs:dword_180014B04
0x180004204  xor     eax, eax
0x180004206  retn
```
