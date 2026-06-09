# ATL::_dynamic_atexit_destructor_for___AtlBaseModule__

- ea: `0x1800126c0`
- end: `0x1800126fe`
- name: `ATL::_dynamic_atexit_destructor_for___AtlBaseModule__`
- size: `62`
- prototype: `void()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800126c0`

## import_xrefs

- `msvcrt!free` at `0x1800126dd`
- `msvcrt!free` at `0x1800126dd`
- `KERNEL32!DeleteCriticalSection` at `0x1800126cb`
- `KERNEL32!DeleteCriticalSection` at `0x1800126cb`

## pseudocode

```c
void ATL::_dynamic_atexit_destructor_for___AtlBaseModule__()
{
  DeleteCriticalSection(&stru_180019AD8);
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  qword_180019B08 = 0;
}

```

## disassembly

```asm
0x1800126c0  sub     rsp, 28h
0x1800126c4  lea     rcx, stru_180019AD8; lpCriticalSection
0x1800126cb  call    cs:__imp_DeleteCriticalSection
0x1800126d1  mov     rcx, cs:Block; Block
0x1800126d8  test    rcx, rcx
0x1800126db  jz      short loc_1800126EE
0x1800126dd  call    cs:__imp_free
0x1800126e3  mov     cs:Block, 0
0x1800126ee  mov     cs:qword_180019B08, 0
0x1800126f9  add     rsp, 28h
0x1800126fd  retn
```
