# ATL::CComClassFactory::LockServer(int)

- ea: `0x180002b20`
- end: `0x180002b37`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002b20`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::LockServer(ATL::CComClassFactory *this, int a2)
{
  if ( a2 )
    _InterlockedIncrement(&dword_180017A78);
  else
    _InterlockedDecrement(&dword_180017A78);
  return 0;
}

```

## disassembly

```asm
0x180002b20  test    edx, edx
0x180002b22  jz      short loc_180002B2D
0x180002b24  lock inc cs:dword_180017A78
0x180002b2b  jmp     short loc_180002B34
0x180002b2d  lock dec cs:dword_180017A78
0x180002b34  xor     eax, eax
0x180002b36  retn
```
