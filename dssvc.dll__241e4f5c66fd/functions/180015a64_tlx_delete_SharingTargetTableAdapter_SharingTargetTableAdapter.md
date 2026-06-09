# tlx::_delete<SharingTargetTableAdapter>(SharingTargetTableAdapter *)

- ea: `0x180015a64`
- end: `0x180015a93`
- name: `??$_delete@VSharingTargetTableAdapter@@@tlx@@YAXPEAVSharingTargetTableAdapter@@@Z`
- size: `47`
- prototype: `void __fastcall(_QWORD *P)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015b28`
- `0x180016198`
- `0x1800162bc`
- `0x180016dec`
- `0x180017518`
- `0x180017e80`

## callees

- `0x180006cb0`
- `0x18000be3c`
- `0x180015a64`

## pseudocode

```c
void __fastcall tlx::_delete<SharingTargetTableAdapter>(_QWORD *P)
{
  if ( P )
  {
    P[2] = &SharingTarget::`vftable';
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(P + 3);
    Common::GlobalHeap::Free(P);
  }
}

```

## disassembly

```asm
0x180015a64  test    rcx, rcx
0x180015a67  jz      short locret_180015A92
0x180015a69  push    rbx
0x180015a6a  sub     rsp, 20h
0x180015a6e  lea     rax, ??_7SharingTarget@@6B@; const SharingTarget::`vftable'
0x180015a75  mov     rbx, rcx
0x180015a78  mov     [rcx+10h], rax
0x180015a7c  add     rcx, 18h
0x180015a80  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180015a85  mov     rcx, rbx; P
0x180015a88  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180015a8d  add     rsp, 20h
0x180015a91  pop     rbx
0x180015a92  retn
```
