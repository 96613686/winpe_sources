# ATL::CComObject<CPnpDiskCleanupHandler>::`scalar deleting destructor'(uint)

- ea: `0x180002ce0`
- end: `0x180002d2e`
- name: `??_G?$CComObject@VCPnpDiskCleanupHandler@@@ATL@@UEAAPEAXI@Z`
- size: `78`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001160`
- `0x180002ce0`
- `0x18000a010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CPnpDiskCleanupHandler>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CPnpDiskCleanupHandler>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180002ce0  mov     [rsp+arg_0], rbx
0x180002ce5  push    rdi
0x180002ce6  sub     rsp, 20h
0x180002cea  mov     dword ptr [rcx+8], 0C0000001h
0x180002cf1  lea     rax, ??_7?$CComObject@VCPnpDiskCleanupHandler@@@ATL@@6B@; const ATL::CComObject<CPnpDiskCleanupHandler>::`vftable'
0x180002cf8  mov     [rcx], rax
0x180002cfb  mov     rdi, rcx
0x180002cfe  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180002d05  mov     ebx, edx
0x180002d07  mov     rax, [rcx]
0x180002d0a  mov     rax, [rax+10h]
0x180002d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d13  test    bl, 1
0x180002d16  jz      short loc_180002D20
0x180002d18  mov     rcx, rdi; Block
0x180002d1b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002d20  mov     rbx, [rsp+28h+arg_0]
0x180002d25  mov     rax, rdi
0x180002d28  add     rsp, 20h
0x180002d2c  pop     rdi
0x180002d2d  retn
```
