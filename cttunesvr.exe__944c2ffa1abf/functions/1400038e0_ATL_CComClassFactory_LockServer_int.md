# ATL::CComClassFactory::LockServer(int)

- ea: `0x1400038e0`
- end: `0x140003908`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400038e0`
- `0x140007010`

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
0x1400038e0  sub     rsp, 28h
0x1400038e4  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400038eb  mov     rax, [rcx]
0x1400038ee  test    edx, edx
0x1400038f0  jz      short loc_1400038F8
0x1400038f2  mov     rax, [rax+8]
0x1400038f6  jmp     short loc_1400038FC
0x1400038f8  mov     rax, [rax+10h]
0x1400038fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003901  xor     eax, eax
0x140003903  add     rsp, 28h
0x140003907  retn
```
