# ATL::CComObject<CCtTuner>::`scalar deleting destructor'(uint)

- ea: `0x140002270`
- end: `0x1400022be`
- name: `??_G?$CComObject@VCCtTuner@@@ATL@@UEAAPEAXI@Z`
- size: `78`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1400011e0`
- `0x140002270`
- `0x140007010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CCtTuner>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CCtTuner>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x140002270  mov     [rsp+arg_0], rbx
0x140002275  push    rdi
0x140002276  sub     rsp, 20h
0x14000227a  mov     dword ptr [rcx+8], 0C0000001h
0x140002281  lea     rax, ??_7?$CComObject@VCCtTuner@@@ATL@@6B@; const ATL::CComObject<CCtTuner>::`vftable'
0x140002288  mov     [rcx], rax
0x14000228b  mov     rdi, rcx
0x14000228e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140002295  mov     ebx, edx
0x140002297  mov     rax, [rcx]
0x14000229a  mov     rax, [rax+10h]
0x14000229e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400022a3  test    bl, 1
0x1400022a6  jz      short loc_1400022B0
0x1400022a8  mov     rcx, rdi; Block
0x1400022ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400022b0  mov     rbx, [rsp+28h+arg_0]
0x1400022b5  mov     rax, rdi
0x1400022b8  add     rsp, 20h
0x1400022bc  pop     rdi
0x1400022bd  retn
```
