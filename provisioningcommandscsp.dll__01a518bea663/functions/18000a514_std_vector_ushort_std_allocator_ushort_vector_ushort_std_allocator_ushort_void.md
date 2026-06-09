# std::vector<ushort,std::allocator<ushort>>::~vector<ushort,std::allocator<ushort>>(void)

- ea: `0x18000a514`
- end: `0x18000a548`
- name: `??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000d326`
- `0x18000d4c5`
- `0x18000d57a`

## callees

- `0x18000a514`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a525`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a525`

## pseudocode

```c
void __fastcall std::vector<unsigned short>::~vector<unsigned short>(__int64 a1)
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
0x18000a514  push    rbx
0x18000a516  sub     rsp, 20h
0x18000a51a  mov     rbx, rcx
0x18000a51d  mov     rcx, [rcx]
0x18000a520  test    rcx, rcx
0x18000a523  jz      short loc_18000A542
0x18000a525  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a52b  mov     qword ptr [rbx], 0
0x18000a532  mov     qword ptr [rbx+8], 0
0x18000a53a  mov     qword ptr [rbx+10h], 0
0x18000a542  add     rsp, 20h
0x18000a546  pop     rbx
0x18000a547  retn
```
