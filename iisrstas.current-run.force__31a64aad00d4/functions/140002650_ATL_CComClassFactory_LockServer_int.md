# ATL::CComClassFactory::LockServer(int)

- ea: `0x140002650`
- end: `0x14000266d`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `29`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002650`
- `0x1400029d8`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::LockServer(ATL::CComClassFactory *this, int a2)
{
  if ( a2 )
    _InterlockedIncrement(&dword_14000A798);
  else
    CExeModule::Unlock(this);
  return 0;
}

```

## disassembly

```asm
0x140002650  sub     rsp, 28h
0x140002654  test    edx, edx
0x140002656  jz      short loc_140002661
0x140002658  lock inc cs:dword_14000A798
0x14000265f  jmp     short loc_140002666
0x140002661  call    ?Unlock@CExeModule@@QEAAJXZ; CExeModule::Unlock(void)
0x140002666  xor     eax, eax
0x140002668  add     rsp, 28h
0x14000266c  retn
```
