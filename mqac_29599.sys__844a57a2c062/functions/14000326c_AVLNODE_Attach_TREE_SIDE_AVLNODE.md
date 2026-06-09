# AVLNODE::Attach(TREE_SIDE,AVLNODE *)

- ea: `0x14000326c`
- end: `0x1400032a5`
- name: `?Attach@AVLNODE@@QEAAXW4TREE_SIDE@@PEAU1@@Z`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400032ac`

## callees

- `0x14000326c`

## pseudocode

```c
void __fastcall AVLNODE::Attach(__int64 a1, int a2, __int64 a3)
{
  unsigned __int8 v3; // al
  unsigned __int8 v4; // r9
  char v5; // r9

  if ( a3 )
  {
    v3 = *(_BYTE *)(a3 + 33);
    v4 = *(_BYTE *)(a3 + 32);
    *(_QWORD *)a3 = a1;
    if ( v4 <= v3 )
      v4 = v3;
    v5 = v4 + 1;
  }
  else
  {
    v5 = 0;
  }
  if ( a2 == 2 )
  {
    *(_QWORD *)(a1 + 16) = a3;
    *(_BYTE *)(a1 + 33) = v5;
  }
  else
  {
    *(_QWORD *)(a1 + 8) = a3;
    *(_BYTE *)(a1 + 32) = v5;
  }
}

```

## disassembly

```asm
0x14000326c  test    r8, r8
0x14000326f  jz      short loc_14000328A
0x140003271  movzx   eax, byte ptr [r8+21h]
0x140003276  movzx   r9d, byte ptr [r8+20h]
0x14000327b  cmp     r9b, al
0x14000327e  mov     [r8], rcx
0x140003281  cmovbe  r9d, eax
0x140003285  inc     r9b
0x140003288  jmp     short loc_14000328D
0x14000328a  xor     r9b, r9b
0x14000328d  cmp     edx, 2
0x140003290  jnz     short loc_14000329C
0x140003292  mov     [rcx+10h], r8
0x140003296  mov     [rcx+21h], r9b
0x14000329a  retn
0x14000329c  mov     [rcx+8], r8
0x1400032a0  mov     [rcx+20h], r9b
0x1400032a4  retn
```
