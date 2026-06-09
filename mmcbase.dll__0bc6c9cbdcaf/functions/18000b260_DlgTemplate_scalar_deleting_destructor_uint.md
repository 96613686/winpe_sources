# DlgTemplate::`scalar deleting destructor'(uint)

- ea: `0x18000b260`
- end: `0x18000b287`
- name: `??_GDlgTemplate@@UEAAPEAXI@Z`
- size: `39`
- prototype: `void *__fastcall(DlgTemplate *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000b260`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18000b278`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18000b278`

## pseudocode

```c
DlgTemplate *__fastcall DlgTemplate::`scalar deleting destructor'(DlgTemplate *this, char a2)
{
  *(_QWORD *)this = &DlgTemplate::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000b260  push    rbx
0x18000b262  sub     rsp, 20h
0x18000b266  lea     rax, ??_7DlgTemplate@@6B@; const DlgTemplate::`vftable'
0x18000b26d  mov     rbx, rcx
0x18000b270  mov     [rcx], rax
0x18000b273  test    dl, 1
0x18000b276  jz      short loc_18000B27E
0x18000b278  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b27e  mov     rax, rbx
0x18000b281  add     rsp, 20h
0x18000b285  pop     rbx
0x18000b286  retn
```
