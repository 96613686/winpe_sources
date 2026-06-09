# ATL::CComAggObject<CPortableWorkspaceLauncher>::`vector deleting destructor'(uint)

- ea: `0x18000ba30`
- end: `0x18000ba7f`
- name: `??_E?$CComAggObject@VCPortableWorkspaceLauncher@@@ATL@@UEAAPEAXI@Z`
- size: `79`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000ba30`
- `0x180011010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ba6b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ba6b`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CPortableWorkspaceLauncher>::`vector deleting destructor'(_DWORD *a1, char a2)
{
  a1[2] = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CPortableWorkspaceLauncher>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000ba30  mov     [rsp+arg_0], rbx
0x18000ba35  push    rdi
0x18000ba36  sub     rsp, 20h
0x18000ba3a  mov     dword ptr [rcx+8], 0C0000001h
0x18000ba41  lea     rax, ??_7?$CComAggObject@VCPortableWorkspaceLauncher@@@ATL@@6B@; const ATL::CComAggObject<CPortableWorkspaceLauncher>::`vftable'
0x18000ba48  mov     [rcx], rax
0x18000ba4b  mov     rdi, rcx
0x18000ba4e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000ba55  mov     ebx, edx
0x18000ba57  mov     rax, [rcx]
0x18000ba5a  mov     rax, [rax+10h]
0x18000ba5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba63  test    bl, 1
0x18000ba66  jz      short loc_18000BA71
0x18000ba68  mov     rcx, rdi
0x18000ba6b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ba71  mov     rbx, [rsp+28h+arg_0]
0x18000ba76  mov     rax, rdi
0x18000ba79  add     rsp, 20h
0x18000ba7d  pop     rdi
0x18000ba7e  retn
```
