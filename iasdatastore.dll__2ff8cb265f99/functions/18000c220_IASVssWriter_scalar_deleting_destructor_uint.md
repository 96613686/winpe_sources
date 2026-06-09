# IASVssWriter::`scalar deleting destructor'(uint)

- ea: `0x18000c220`
- end: `0x18000c250`
- name: `??_GIASVssWriter@@UEAAPEAXI@Z`
- size: `48`
- prototype: `void *__fastcall(IASVssWriter *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c1a0`

## callees

- `0x18000c110`
- `0x18000c220`

## import_xrefs

- `msvcrt!free` at `0x18000c23c`
- `msvcrt!free` at `0x18000c23c`

## pseudocode

```c
IASVssWriter *__fastcall IASVssWriter::`scalar deleting destructor'(IASVssWriter *this, char a2)
{
  IASVssWriter::~IASVssWriter(this);
  if ( (a2 & 1) != 0 )
    free(this);
  return this;
}

```

## disassembly

```asm
0x18000c220  mov     [rsp+arg_0], rbx
0x18000c225  push    rdi
0x18000c226  sub     rsp, 20h
0x18000c22a  mov     ebx, edx
0x18000c22c  mov     rdi, rcx
0x18000c22f  call    ??1IASVssWriter@@UEAA@XZ; IASVssWriter::~IASVssWriter(void)
0x18000c234  test    bl, 1
0x18000c237  jz      short loc_18000C242
0x18000c239  mov     rcx, rdi; Block
0x18000c23c  call    cs:__imp_free
0x18000c242  mov     rbx, [rsp+28h+arg_0]
0x18000c247  mov     rax, rdi
0x18000c24a  add     rsp, 20h
0x18000c24e  pop     rdi
0x18000c24f  retn
```
