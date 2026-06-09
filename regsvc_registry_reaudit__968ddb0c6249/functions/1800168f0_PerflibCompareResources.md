# PerflibCompareResources

- ea: `0x1800168f0`
- end: `0x180016920`
- name: `PerflibCompareResources`
- size: `48`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800168f0`
- `0x18001e425`

## pseudocode

```c
__int64 __fastcall PerflibCompareResources(struct _RTL_AVL_TABLE *Table, PVOID FirstStruct, PVOID SecondStruct)
{
  int v3; // ecx

  v3 = memcmp_0(FirstStruct, SecondStruct, 0x18u);
  if ( v3 >= 0 )
    return (unsigned int)(v3 <= 0) + 1;
  else
    return 0;
}

```

## disassembly

```asm
0x1800168f0  sub     rsp, 28h
0x1800168f4  mov     rax, r8
0x1800168f7  mov     rcx, rdx; Buf1
0x1800168fa  mov     rdx, rax; Buf2
0x1800168fd  mov     r8d, 18h; Size
0x180016903  call    memcmp_0
0x180016908  mov     ecx, eax
0x18001690a  test    eax, eax
0x18001690c  jns     short loc_180016912
0x18001690e  xor     eax, eax
0x180016910  jmp     short loc_18001691B
0x180016912  xor     eax, eax
0x180016914  test    ecx, ecx
0x180016916  setle   al
0x180016919  inc     eax
0x18001691b  add     rsp, 28h
0x18001691f  retn
```
