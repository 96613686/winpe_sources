# LuafvSplitPathRight

- ea: `0x1400177e0`
- end: `0x14001784a`
- name: `LuafvSplitPathRight`
- size: `106`
- prototype: `char __fastcall(_WORD *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400175f8`

## callees

- `0x1400177e0`

## pseudocode

```c
char __fastcall LuafvSplitPathRight(_WORD *a1, unsigned __int16 *a2)
{
  unsigned int v2; // r9d
  unsigned int v4; // ecx
  char result; // al
  _WORD *v6; // r11
  unsigned __int16 v7; // r9

  v2 = *a2;
  v4 = 0;
  if ( !(_WORD)v2 )
    return 0;
  v6 = (_WORD *)*((_QWORD *)a2 + 1);
  LOBYTE(v4) = *v6 == 92;
  while ( v4 < v2 >> 1 && v6[v4] != 92 )
    ++v4;
  result = 1;
  *a1 += 2 * v4;
  v7 = v2 - 2 * v4;
  *a2 = v7;
  a2[1] = v7;
  *((_QWORD *)a2 + 1) = &v6[v4];
  return result;
}

```

## disassembly

```asm
0x1400177e0  mov     [rsp+arg_0], rbx
0x1400177e5  movzx   r9d, word ptr [rdx]
0x1400177e9  mov     rbx, rcx
0x1400177ec  xor     ecx, ecx
0x1400177ee  mov     r10, rdx
0x1400177f1  test    r9w, r9w
0x1400177f5  jnz     short loc_1400177FB
0x1400177f7  xor     al, al
0x1400177f9  jmp     short loc_140017843
0x1400177fb  mov     r11, [rdx+8]
0x1400177ff  mov     edx, r9d
0x140017802  cmp     word ptr [r11], 5Ch ; '\'
0x140017807  setz    cl
0x14001780a  shr     edx, 1
0x14001780c  jmp     short loc_14001781A
0x14001780e  mov     eax, ecx
0x140017810  cmp     word ptr [r11+rax*2], 5Ch ; '\'
0x140017816  jz      short loc_14001781E
0x140017818  inc     ecx
0x14001781a  cmp     ecx, edx
0x14001781c  jb      short loc_14001780E
0x14001781e  movzx   r8d, cx
0x140017822  mov     al, 1
0x140017824  add     r8w, r8w
0x140017828  mov     ecx, ecx
0x14001782a  add     [rbx], r8w
0x14001782e  sub     r9w, r8w
0x140017832  mov     [r10], r9w
0x140017836  lea     rdx, [r11+rcx*2]
0x14001783a  mov     [r10+2], r9w
0x14001783f  mov     [r10+8], rdx
0x140017843  mov     rbx, [rsp+arg_0]
0x140017848  retn
```
