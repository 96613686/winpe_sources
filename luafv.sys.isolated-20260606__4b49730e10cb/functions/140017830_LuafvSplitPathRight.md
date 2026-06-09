# LuafvSplitPathRight

- ea: `0x140017830`
- end: `0x14001789a`
- name: `LuafvSplitPathRight`
- size: `106`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140017648`

## callees

- `0x140017830`

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
0x140017830  mov     [rsp+arg_0], rbx
0x140017835  movzx   r9d, word ptr [rdx]
0x140017839  mov     rbx, rcx
0x14001783c  xor     ecx, ecx
0x14001783e  mov     r10, rdx
0x140017841  test    r9w, r9w
0x140017845  jnz     short loc_14001784B
0x140017847  xor     al, al
0x140017849  jmp     short loc_140017893
0x14001784b  mov     r11, [rdx+8]
0x14001784f  mov     edx, r9d
0x140017852  cmp     word ptr [r11], 5Ch ; '\'
0x140017857  setz    cl
0x14001785a  shr     edx, 1
0x14001785c  jmp     short loc_14001786A
0x14001785e  mov     eax, ecx
0x140017860  cmp     word ptr [r11+rax*2], 5Ch ; '\'
0x140017866  jz      short loc_14001786E
0x140017868  inc     ecx
0x14001786a  cmp     ecx, edx
0x14001786c  jb      short loc_14001785E
0x14001786e  movzx   r8d, cx
0x140017872  mov     al, 1
0x140017874  add     r8w, r8w
0x140017878  mov     ecx, ecx
0x14001787a  add     [rbx], r8w
0x14001787e  sub     r9w, r8w
0x140017882  mov     [r10], r9w
0x140017886  lea     rdx, [r11+rcx*2]
0x14001788a  mov     [r10+2], r9w
0x14001788f  mov     [r10+8], rdx
0x140017893  mov     rbx, [rsp+arg_0]
0x140017898  retn
```
