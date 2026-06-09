# OUTPUT_CACHE::`scalar deleting destructor'(uint)

- ea: `0x1800052b4`
- end: `0x1800052d4`
- name: `??_GOUTPUT_CACHE@@QEAAPEAXI@Z`
- size: `32`
- prototype: `void *__fastcall(OUTPUT_CACHE *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800039d0`
- `0x1800072b0`

## callees

- `0x180005a4c`

## import_xrefs

- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x1800052bd`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x1800052bd`

## pseudocode

```c
OUTPUT_CACHE *__fastcall OUTPUT_CACHE::`scalar deleting destructor'(OUTPUT_CACHE *this)
{
  CLKRHashTable::~CLKRHashTable(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800052b4  push    rbx
0x1800052b6  sub     rsp, 20h
0x1800052ba  mov     rbx, rcx
0x1800052bd  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x1800052c3  mov     rcx, rbx; Block
0x1800052c6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800052cb  mov     rax, rbx
0x1800052ce  add     rsp, 20h
0x1800052d2  pop     rbx
0x1800052d3  retn
```
