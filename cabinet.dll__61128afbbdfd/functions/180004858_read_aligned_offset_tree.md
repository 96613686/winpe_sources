# read_aligned_offset_tree

- ea: `0x180004858`
- end: `0x1800048c4`
- name: `read_aligned_offset_tree`
- size: `108`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000548c`

## callees

- `0x180002b44`
- `0x180004858`
- `0x180006270`

## pseudocode

```c
_BOOL8 __fastcall read_aligned_offset_tree(__int64 a1)
{
  __int64 i; // rdi
  __int64 v3; // rcx
  char v4; // r11

  for ( i = 0; i != 8; ++i )
  {
    fillbuf(a1, 3);
    *(_BYTE *)(a1 + i + 3640) = v4;
  }
  return !*(_DWORD *)(a1 + 11980) && (unsigned int)make_table_8bit(v3, a1 + 3640, (char *)(a1 + 3512)) != 0;
}

```

## disassembly

```asm
0x180004858  mov     [rsp+arg_0], rbx
0x18000485d  push    rdi
0x18000485e  sub     rsp, 20h
0x180004862  mov     rbx, rcx
0x180004865  xor     edi, edi
0x180004867  mov     r11d, [rbx+2EC0h]
0x18000486e  mov     edx, 3
0x180004873  mov     rcx, rbx
0x180004876  shr     r11d, 1Dh
0x18000487a  call    fillbuf
0x18000487f  mov     [rbx+rdi+0E38h], r11b
0x180004887  inc     rdi
0x18000488a  cmp     rdi, 8
0x18000488e  jnz     short loc_180004867
0x180004890  cmp     dword ptr [rbx+2ECCh], 0
0x180004897  jnz     short loc_1800048C0
0x180004899  lea     r8, [rbx+0DB8h]
0x1800048a0  lea     rdx, [rbx+0E38h]
0x1800048a7  call    make_table_8bit
0x1800048ac  xor     ecx, ecx
0x1800048ae  test    eax, eax
0x1800048b0  setnz   cl
0x1800048b3  mov     eax, ecx
0x1800048b5  mov     rbx, [rsp+28h+arg_0]
0x1800048ba  add     rsp, 20h
0x1800048be  pop     rdi
0x1800048bf  retn
0x1800048c0  xor     eax, eax
0x1800048c2  jmp     short loc_1800048B5
```
