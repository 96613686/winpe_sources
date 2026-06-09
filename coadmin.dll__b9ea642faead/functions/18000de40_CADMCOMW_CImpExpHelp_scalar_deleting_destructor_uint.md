# CADMCOMW::CImpExpHelp::`scalar deleting destructor'(uint)

- ea: `0x18000de40`
- end: `0x18000de66`
- name: `??_GCImpExpHelp@CADMCOMW@@UEAAPEAXI@Z`
- size: `38`
- prototype: `void *__fastcall(CADMCOMW::CImpExpHelp *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800010a4`
- `0x18000de40`

## pseudocode

```c
CADMCOMW::CImpExpHelp *__fastcall CADMCOMW::CImpExpHelp::`scalar deleting destructor'(
        CADMCOMW::CImpExpHelp *this,
        char a2)
{
  *(_QWORD *)this = &CADMCOMW::CImpExpHelp::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000de40  push    rbx
0x18000de42  sub     rsp, 20h
0x18000de46  lea     rax, ??_7CImpExpHelp@CADMCOMW@@6B@; const CADMCOMW::CImpExpHelp::`vftable'
0x18000de4d  mov     rbx, rcx
0x18000de50  mov     [rcx], rax
0x18000de53  test    dl, 1
0x18000de56  jz      short loc_18000DE5D
0x18000de58  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000de5d  mov     rax, rbx
0x18000de60  add     rsp, 20h
0x18000de64  pop     rbx
0x18000de65  retn
```
