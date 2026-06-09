# CClassFactory::LockServer(int)

- ea: `0x180001fa0`
- end: `0x180001fb7`
- name: `?LockServer@CClassFactory@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001fa0`

## pseudocode

```c
__int64 __fastcall CClassFactory::LockServer(CClassFactory *this, int a2)
{
  if ( a2 )
    _InterlockedIncrement(&dword_180006640);
  else
    _InterlockedDecrement(&dword_180006640);
  return 0;
}

```

## disassembly

```asm
0x180001fa0  test    edx, edx
0x180001fa2  jz      short loc_180001FAD
0x180001fa4  lock inc cs:dword_180006640
0x180001fab  jmp     short loc_180001FB4
0x180001fad  lock dec cs:dword_180006640
0x180001fb4  xor     eax, eax
0x180001fb6  retn
```
