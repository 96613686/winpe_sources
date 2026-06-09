# ASCLOG_DATETIME_CACHE::`scalar deleting destructor'(uint)

- ea: `0x180003b00`
- end: `0x180003b26`
- name: `??_GASCLOG_DATETIME_CACHE@@UEAAPEAXI@Z`
- size: `38`
- prototype: `void *__fastcall(ASCLOG_DATETIME_CACHE *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180003b00`

## import_xrefs

- `IisRTL!??_7CACHED_DATETIME_FORMATS@@6B@` at `0x180003b06`

## pseudocode

```c
ASCLOG_DATETIME_CACHE *__fastcall ASCLOG_DATETIME_CACHE::`scalar deleting destructor'(
        ASCLOG_DATETIME_CACHE *this,
        char a2)
{
  *(_QWORD *)this = CACHED_DATETIME_FORMATS::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180003b00  push    rbx
0x180003b02  sub     rsp, 20h
0x180003b06  mov     rax, cs:__imp_??_7CACHED_DATETIME_FORMATS@@6B@; const CACHED_DATETIME_FORMATS::`vftable'
0x180003b0d  mov     rbx, rcx
0x180003b10  mov     [rcx], rax
0x180003b13  test    dl, 1
0x180003b16  jz      short loc_180003B1D
0x180003b18  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003b1d  mov     rax, rbx
0x180003b20  add     rsp, 20h
0x180003b24  pop     rbx
0x180003b25  retn
```
