# BookKeepingXml::`vector deleting destructor'(uint)

- ea: `0x18000bd80`
- end: `0x18000bdaf`
- name: `??_EBookKeepingXml@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(BookKeepingXml *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x18000bd80`
- `0x18000c68c`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18000bda0`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18000bda0`

## pseudocode

```c
BookKeepingXml *__fastcall BookKeepingXml::`vector deleting destructor'(BookKeepingXml *this)
{
  char v2; // dl

  *(_QWORD *)this = &BookKeepingXml::`vftable';
  BookKeepingXml::Empty(this);
  if ( (v2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000bd80  push    rbx
0x18000bd82  sub     rsp, 20h
0x18000bd86  lea     rax, ??_7BookKeepingXml@@6B@; const BookKeepingXml::`vftable'
0x18000bd8d  mov     rbx, rcx
0x18000bd90  mov     [rcx], rax
0x18000bd93  call    ?Empty@BookKeepingXml@@QEAAXXZ; BookKeepingXml::Empty(void)
0x18000bd98  test    dl, 1
0x18000bd9b  jz      short loc_18000BDA6
0x18000bd9d  mov     rcx, rbx
0x18000bda0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bda6  mov     rax, rbx
0x18000bda9  add     rsp, 20h
0x18000bdad  pop     rbx
0x18000bdae  retn
```
