# ATL::CComClassFactory::LockServer(int)

- ea: `0x180004550`
- end: `0x180004567`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004550`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::LockServer(ATL::CComClassFactory *this, int a2)
{
  if ( a2 )
    _InterlockedIncrement(&dword_18000F8D8);
  else
    _InterlockedDecrement(&dword_18000F8D8);
  return 0;
}

```

## disassembly

```asm
0x180004550  test    edx, edx
0x180004552  jz      short loc_18000455D
0x180004554  lock inc cs:dword_18000F8D8
0x18000455b  jmp     short loc_180004564
0x18000455d  lock dec cs:dword_18000F8D8
0x180004564  xor     eax, eax
0x180004566  retn
```
