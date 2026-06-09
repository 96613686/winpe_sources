# ATL::CComClassFactory::LockServer(int)

- ea: `0x18000c160`
- end: `0x18000c188`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000c160`
- `0x180011010`

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
0x18000c160  sub     rsp, 28h
0x18000c164  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c16b  mov     rax, [rcx]
0x18000c16e  test    edx, edx
0x18000c170  jz      short loc_18000C178
0x18000c172  mov     rax, [rax+8]
0x18000c176  jmp     short loc_18000C17C
0x18000c178  mov     rax, [rax+10h]
0x18000c17c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c181  xor     eax, eax
0x18000c183  add     rsp, 28h
0x18000c187  retn
```
