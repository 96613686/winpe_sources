# CADMCOMW::CImpIConnectionPointContainer::`scalar deleting destructor'(uint)

- ea: `0x18000c140`
- end: `0x18000c166`
- name: `??_GCImpIConnectionPointContainer@CADMCOMW@@UEAAPEAXI@Z`
- size: `38`
- prototype: `void *__fastcall(CADMCOMW::CImpIConnectionPointContainer *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800010a4`
- `0x18000c140`

## pseudocode

```c
CADMCOMW::CImpIConnectionPointContainer *__fastcall CADMCOMW::CImpIConnectionPointContainer::`scalar deleting destructor'(
        CADMCOMW::CImpIConnectionPointContainer *this,
        char a2)
{
  *(_QWORD *)this = &CADMCOMW::CImpIConnectionPointContainer::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000c140  push    rbx
0x18000c142  sub     rsp, 20h
0x18000c146  lea     rax, ??_7CImpIConnectionPointContainer@CADMCOMW@@6B@; const CADMCOMW::CImpIConnectionPointContainer::`vftable'
0x18000c14d  mov     rbx, rcx
0x18000c150  mov     [rcx], rax
0x18000c153  test    dl, 1
0x18000c156  jz      short loc_18000C15D
0x18000c158  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c15d  mov     rax, rbx
0x18000c160  add     rsp, 20h
0x18000c164  pop     rbx
0x18000c165  retn
```
