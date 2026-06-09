# TRelationMeta::`scalar deleting destructor'(uint)

- ea: `0x180020da0`
- end: `0x180020dc7`
- name: `??_GTRelationMeta@@UEAAPEAXI@Z`
- size: `39`
- prototype: `void *__fastcall(TRelationMeta *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180020da0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180020db8`
- `ole32!CoTaskMemFree` at `0x180020db8`

## pseudocode

```c
TRelationMeta *__fastcall TRelationMeta::`scalar deleting destructor'(TRelationMeta *this, char a2)
{
  *(_QWORD *)this = &TMetaTableBase::`vftable';
  if ( (a2 & 1) != 0 )
    CoTaskMemFree(this);
  return this;
}

```

## disassembly

```asm
0x180020da0  push    rbx
0x180020da2  sub     rsp, 20h
0x180020da6  mov     rbx, rcx
0x180020da9  lea     rax, ??_7TMetaTableBase@@6B@; const TMetaTableBase::`vftable'
0x180020db0  mov     [rcx], rax
0x180020db3  test    dl, 1
0x180020db6  jz      short loc_180020DBE
0x180020db8  call    cs:__imp_CoTaskMemFree
0x180020dbe  mov     rax, rbx
0x180020dc1  add     rsp, 20h
0x180020dc5  pop     rbx
0x180020dc6  retn
```
