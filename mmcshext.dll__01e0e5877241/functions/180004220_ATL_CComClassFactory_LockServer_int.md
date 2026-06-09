# ATL::CComClassFactory::LockServer(int)

- ea: `0x180004220`
- end: `0x180004237`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180004220`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::LockServer(ATL::CComClassFactory *this, int a2)
{
  if ( a2 )
    _InterlockedIncrement(&dword_180012EE8);
  else
    _InterlockedDecrement(&dword_180012EE8);
  return 0;
}

```

## disassembly

```asm
0x180004220  test    edx, edx
0x180004222  jz      short loc_18000422D
0x180004224  lock inc cs:dword_180012EE8
0x18000422b  jmp     short loc_180004234
0x18000422d  lock dec cs:dword_180012EE8
0x180004234  xor     eax, eax
0x180004236  retn
```
