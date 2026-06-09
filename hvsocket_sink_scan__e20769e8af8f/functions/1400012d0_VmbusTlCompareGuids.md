# VmbusTlCompareGuids

- ea: `0x1400012d0`
- end: `0x140001309`
- name: `VmbusTlCompareGuids`
- size: `57`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400012d0`
- `0x14000c0a0`

## pseudocode

```c
__int64 __fastcall VmbusTlCompareGuids(struct _RTL_AVL_TABLE *Table, PVOID FirstStruct, PVOID SecondStruct)
{
  int v3; // eax
  __int64 v4; // rdx
  __int64 result; // rax

  v3 = memcmp(FirstStruct, SecondStruct, 0x10u);
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
0x1400012d0  sub     rsp, 28h
0x1400012d4  mov     rax, r8
0x1400012d7  mov     rcx, rdx; Buf1
0x1400012da  mov     rdx, rax; Buf2
0x1400012dd  mov     r8d, 10h; Size
0x1400012e3  call    memcmp
0x1400012e8  movsxd  rdx, eax
0x1400012eb  test    eax, eax
0x1400012ed  jle     short loc_1400012F6
0x1400012ef  mov     eax, 1
0x1400012f4  jmp     short loc_140001303
0x1400012f6  xor     ecx, ecx
0x1400012f8  mov     eax, 2
0x1400012fd  test    rdx, rdx
0x140001300  cmovs   eax, ecx
0x140001303  add     rsp, 28h
0x140001307  retn
```
