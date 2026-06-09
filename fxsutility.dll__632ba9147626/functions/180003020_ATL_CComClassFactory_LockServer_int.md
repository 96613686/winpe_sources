# ATL::CComClassFactory::LockServer(int)

- ea: `0x180003020`
- end: `0x180003037`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003020`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::LockServer(ATL::CComClassFactory *this, int a2)
{
  if ( a2 )
    _InterlockedIncrement(&dword_18001EB58);
  else
    _InterlockedDecrement(&dword_18001EB58);
  return 0;
}

```

## disassembly

```asm
0x180003020  test    edx, edx
0x180003022  jz      short loc_18000302D
0x180003024  lock inc cs:dword_18001EB58
0x18000302b  jmp     short loc_180003034
0x18000302d  lock dec cs:dword_18001EB58
0x180003034  xor     eax, eax
0x180003036  retn
```
