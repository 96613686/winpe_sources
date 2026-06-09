# std::vector<ushort,std::allocator<ushort>>::~vector<ushort,std::allocator<ushort>>(void)

- ea: `0x18000aa6c`
- end: `0x18000aaa7`
- name: `??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ`
- size: `59`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000d9f2`
- `0x18000db93`
- `0x18000dc4a`

## callees

- `0x18000aa6c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000aa7d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000aa7d`

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
0x18000aa6c  push    rbx
0x18000aa6e  sub     rsp, 20h
0x18000aa72  mov     rbx, rcx
0x18000aa75  mov     rcx, [rcx]
0x18000aa78  test    rcx, rcx
0x18000aa7b  jz      short loc_18000AAA0
0x18000aa7d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000aa84  nop     dword ptr [rax+rax+00h]
0x18000aa89  mov     qword ptr [rbx], 0
0x18000aa90  mov     qword ptr [rbx+8], 0
0x18000aa98  mov     qword ptr [rbx+10h], 0
0x18000aaa0  add     rsp, 20h
0x18000aaa4  pop     rbx
0x18000aaa5  retn
```
