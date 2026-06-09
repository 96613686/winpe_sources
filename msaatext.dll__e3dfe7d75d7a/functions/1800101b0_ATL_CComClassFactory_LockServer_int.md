# ATL::CComClassFactory::LockServer(int)

- ea: `0x1800101b0`
- end: `0x1800101c7`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800101b0`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::LockServer(ATL::CComClassFactory *this, int a2)
{
  if ( a2 )
    _InterlockedIncrement(&dword_180024B28);
  else
    _InterlockedDecrement(&dword_180024B28);
  return 0;
}

```

## disassembly

```asm
0x1800101b0  test    edx, edx
0x1800101b2  jz      short loc_1800101BD
0x1800101b4  lock inc cs:dword_180024B28
0x1800101bb  jmp     short loc_1800101C4
0x1800101bd  lock dec cs:dword_180024B28
0x1800101c4  xor     eax, eax
0x1800101c6  retn
```
