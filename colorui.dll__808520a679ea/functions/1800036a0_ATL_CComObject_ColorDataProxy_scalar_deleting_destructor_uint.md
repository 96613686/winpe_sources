# ATL::CComObject<ColorDataProxy>::`scalar deleting destructor'(uint)

- ea: `0x1800036a0`
- end: `0x1800036f4`
- name: `??_G?$CComObject@VColorDataProxy@@@ATL@@UEAAPEAXI@Z`
- size: `84`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001334`
- `0x1800036a0`
- `0x180019010`

## import_xrefs

- `mscms!ColorCplUninitialize` at `0x1800036d3`
- `mscms!ColorCplUninitialize` at `0x1800036d3`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<ColorDataProxy>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<ColorDataProxy>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  ColorCplUninitialize();
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800036a0  mov     [rsp+arg_0], rbx
0x1800036a5  push    rdi
0x1800036a6  sub     rsp, 20h
0x1800036aa  mov     dword ptr [rcx+8], 0C0000001h
0x1800036b1  lea     rax, ??_7?$CComObject@VColorDataProxy@@@ATL@@6B@; const ATL::CComObject<ColorDataProxy>::`vftable'
0x1800036b8  mov     [rcx], rax
0x1800036bb  mov     rdi, rcx
0x1800036be  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800036c5  mov     ebx, edx
0x1800036c7  mov     rax, [rcx]
0x1800036ca  mov     rax, [rax+10h]
0x1800036ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036d3  call    cs:__imp_ColorCplUninitialize
0x1800036d9  test    bl, 1
0x1800036dc  jz      short loc_1800036E6
0x1800036de  mov     rcx, rdi; Block
0x1800036e1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800036e6  mov     rbx, [rsp+28h+arg_0]
0x1800036eb  mov     rax, rdi
0x1800036ee  add     rsp, 20h
0x1800036f2  pop     rdi
0x1800036f3  retn
```
