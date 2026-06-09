# std::vector<ushort const *,std::allocator<ushort const *>>::~vector<ushort const *,std::allocator<ushort const *>>(void)

- ea: `0x1400039d0`
- end: `0x140003a04`
- name: `??1?$vector@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ`
- size: `52`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14000e0b5`
- `0x14000e0c7`
- `0x14000e113`
- `0x14000eaac`
- `0x14000eafd`
- `0x14000ebeb`
- `0x14000ec88`

## callees

- `0x1400039d0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1400039e1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400039e1`

## pseudocode

```c
void __fastcall std::vector<unsigned short const *>::~vector<unsigned short const *>(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x1400039d0  push    rbx
0x1400039d2  sub     rsp, 20h
0x1400039d6  mov     rbx, rcx
0x1400039d9  mov     rcx, [rcx]
0x1400039dc  test    rcx, rcx
0x1400039df  jz      short loc_1400039FE
0x1400039e1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400039e7  mov     qword ptr [rbx], 0
0x1400039ee  mov     qword ptr [rbx+8], 0
0x1400039f6  mov     qword ptr [rbx+10h], 0
0x1400039fe  add     rsp, 20h
0x140003a02  pop     rbx
0x140003a03  retn
```
