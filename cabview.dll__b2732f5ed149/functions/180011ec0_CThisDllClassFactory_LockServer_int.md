# CThisDllClassFactory::LockServer(int)

- ea: `0x180011ec0`
- end: `0x180011ed7`
- name: `?LockServer@CThisDllClassFactory@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(CThisDllClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180011ec0`

## pseudocode

```c
__int64 __fastcall CThisDllClassFactory::LockServer(CThisDllClassFactory *this, int a2)
{
  if ( a2 )
    _InterlockedIncrement(&g_cRefThisDll);
  else
    _InterlockedDecrement(&g_cRefThisDll);
  return 0;
}

```

## disassembly

```asm
0x180011ec0  test    edx, edx
0x180011ec2  jz      short loc_180011ECD
0x180011ec4  lock inc cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180011ecb  jmp     short loc_180011ED4
0x180011ecd  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x180011ed4  xor     eax, eax
0x180011ed6  retn
```
