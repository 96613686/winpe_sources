# ATL::CComAggObject<CCtTuner>::`scalar deleting destructor'(uint)

- ea: `0x140002210`
- end: `0x14000225e`
- name: `??_G?$CComAggObject@VCCtTuner@@@ATL@@UEAAPEAXI@Z`
- size: `78`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400011e0`
- `0x140002210`
- `0x140007010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CCtTuner>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<CCtTuner>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x140002210  mov     [rsp+arg_0], rbx
0x140002215  push    rdi
0x140002216  sub     rsp, 20h
0x14000221a  mov     dword ptr [rcx+8], 0C0000001h
0x140002221  lea     rax, ??_7?$CComAggObject@VCCtTuner@@@ATL@@6B@; const ATL::CComAggObject<CCtTuner>::`vftable'
0x140002228  mov     [rcx], rax
0x14000222b  mov     rdi, rcx
0x14000222e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140002235  mov     ebx, edx
0x140002237  mov     rax, [rcx]
0x14000223a  mov     rax, [rax+10h]
0x14000223e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002243  test    bl, 1
0x140002246  jz      short loc_140002250
0x140002248  mov     rcx, rdi; Block
0x14000224b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002250  mov     rbx, [rsp+28h+arg_0]
0x140002255  mov     rax, rdi
0x140002258  add     rsp, 20h
0x14000225c  pop     rdi
0x14000225d  retn
```
