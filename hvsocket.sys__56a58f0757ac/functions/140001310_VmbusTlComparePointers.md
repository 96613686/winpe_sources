# VmbusTlComparePointers

- ea: `0x140001310`
- end: `0x140001349`
- name: `VmbusTlComparePointers`
- size: `57`
- prototype: `__int64 __fastcall(struct _RTL_AVL_TABLE *Table, PVOID FirstStruct, PVOID SecondStruct)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140001310`
- `0x14000c0a0`

## pseudocode

```c
__int64 __fastcall VmbusTlComparePointers(struct _RTL_AVL_TABLE *Table, PVOID FirstStruct, PVOID SecondStruct)
{
  int v3; // eax
  __int64 v4; // rdx
  __int64 result; // rax

  v3 = memcmp(FirstStruct, SecondStruct, 8u);
  v4 = v3;
  if ( v3 > 0 )
    return 1;
  result = 2;
  if ( v4 < 0 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x140001310  sub     rsp, 28h
0x140001314  mov     rax, r8
0x140001317  mov     rcx, rdx; Buf1
0x14000131a  mov     rdx, rax; Buf2
0x14000131d  mov     r8d, 8; Size
0x140001323  call    memcmp
0x140001328  movsxd  rdx, eax
0x14000132b  test    eax, eax
0x14000132d  jle     short loc_140001336
0x14000132f  mov     eax, 1
0x140001334  jmp     short loc_140001343
0x140001336  xor     ecx, ecx
0x140001338  mov     eax, 2
0x14000133d  test    rdx, rdx
0x140001340  cmovs   eax, ecx
0x140001343  add     rsp, 28h
0x140001347  retn
```
