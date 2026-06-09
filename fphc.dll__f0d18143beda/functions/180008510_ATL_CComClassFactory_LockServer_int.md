# ATL::CComClassFactory::LockServer(int)

- ea: `0x180008510`
- end: `0x180008538`
- name: `?LockServer@CComClassFactory@ATL@@UEAAJH@Z`
- size: `40`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008510`
- `0x180012010`

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
0x180008510  sub     rsp, 28h
0x180008514  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000851b  mov     rax, [rcx]
0x18000851e  test    edx, edx
0x180008520  jz      short loc_180008528
0x180008522  mov     rax, [rax+8]
0x180008526  jmp     short loc_18000852C
0x180008528  mov     rax, [rax+10h]
0x18000852c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008531  xor     eax, eax
0x180008533  add     rsp, 28h
0x180008537  retn
```
