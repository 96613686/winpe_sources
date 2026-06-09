# DIRLIST_CONFIG::`vector deleting destructor'(uint)

- ea: `0x180002410`
- end: `0x180002436`
- name: `??_EDIRLIST_CONFIG@@EEAAPEAXI@Z`
- size: `38`
- prototype: `void *__fastcall(DIRLIST_CONFIG *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x180001048`
- `0x180002410`

## pseudocode

```c
DIRLIST_CONFIG *__fastcall DIRLIST_CONFIG::`vector deleting destructor'(DIRLIST_CONFIG *this, char a2)
{
  *(_QWORD *)this = &DIRLIST_CONFIG::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002410  push    rbx
0x180002412  sub     rsp, 20h
0x180002416  lea     rax, ??_7DIRLIST_CONFIG@@6B@; const DIRLIST_CONFIG::`vftable'
0x18000241d  mov     rbx, rcx
0x180002420  mov     [rcx], rax
0x180002423  test    dl, 1
0x180002426  jz      short loc_18000242D
0x180002428  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000242d  mov     rax, rbx
0x180002430  add     rsp, 20h
0x180002434  pop     rbx
0x180002435  retn
```
