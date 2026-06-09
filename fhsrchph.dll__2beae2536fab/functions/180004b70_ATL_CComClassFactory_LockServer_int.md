# ATL::CComClassFactory::LockServer(int)

- ea: `0x180004b70`
- end: `0x180004b98`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004b70`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::LockServer(ATL::CComClassFactory *this, int a2)
{
  __int64 v2; // rax
  void (*v3)(void); // rax

  v2 = *(_QWORD *)ATL::_pAtlModule;
  if ( a2 )
    v3 = *(void (**)(void))(v2 + 8);
  else
    v3 = *(void (**)(void))(v2 + 16);
  v3();
  return 0;
}

```

## disassembly

```asm
0x180004b70  sub     rsp, 28h
0x180004b74  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004b7b  mov     rax, [rcx]
0x180004b7e  test    edx, edx
0x180004b80  jz      short loc_180004B88
0x180004b82  mov     rax, [rax+8]
0x180004b86  jmp     short loc_180004B8C
0x180004b88  mov     rax, [rax+10h]
0x180004b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b91  xor     eax, eax
0x180004b93  add     rsp, 28h
0x180004b97  retn
```
