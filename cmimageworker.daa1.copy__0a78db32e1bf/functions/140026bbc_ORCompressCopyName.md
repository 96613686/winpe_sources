# ORCompressCopyName

- ea: `0x140026bbc`
- end: `0x140026c65`
- name: `ORCompressCopyName`
- size: `169`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002307c`
- `0x140023cb0`
- `0x140025028`
- `0x140025f20`

## callees

- `0x140026bbc`
- `0x14002e8cc`

## pseudocode

```c
__int64 __fastcall ORCompressCopyName(_WORD *a1, unsigned __int64 a2, __int64 a3, unsigned __int16 *a4)
{
  _WORD *v5; // r10
  unsigned __int64 v6; // rbx
  int v8; // edx
  unsigned __int64 v9; // r8
  __int64 v10; // rax

  v5 = (_WORD *)*((_QWORD *)a4 + 1);
  v6 = *a4;
  if ( *(_DWORD *)(a3 + 24) + (*(_DWORD *)(a3 + 20) << 12) == 4097 )
  {
    if ( a1 == v5 )
      return (unsigned __int16)v6;
    if ( a2 >= v6 )
    {
LABEL_4:
      memcpy_0(a1, *((const void **)a4 + 1), *a4);
      return (unsigned __int16)v6;
    }
    return 0;
  }
  v8 = 0;
  v9 = v6 >> 1;
  if ( v6 >> 1 )
  {
    while ( (unsigned __int8)v5[v8] == v5[v8] )
    {
      if ( ++v8 == v9 )
        goto LABEL_9;
    }
    if ( a1 == v5 )
      return (unsigned __int16)v6;
    if ( a2 >= v6 )
      goto LABEL_4;
    return 0;
  }
LABEL_9:
  if ( a2 < v9 )
    return 0;
  v10 = 0;
  if ( v9 )
  {
    do
    {
      *((_BYTE *)a1 + v10) = v5[v10];
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (unsigned int)v10 != v9 );
  }
  return (unsigned __int16)v9;
}

```

## disassembly

```asm
0x140026bbc  mov     [rsp+arg_0], rbx
0x140026bc1  push    rdi
0x140026bc2  sub     rsp, 20h
0x140026bc6  mov     eax, [r8+14h]
0x140026bca  mov     rdi, rdx
0x140026bcd  mov     r10, [r9+8]
0x140026bd1  mov     r11, rcx
0x140026bd4  movzx   ebx, word ptr [r9]
0x140026bd8  shl     eax, 0Ch
0x140026bdb  add     eax, [r8+18h]
0x140026bdf  cmp     eax, 1001h
0x140026be4  jnz     short loc_140026C00
0x140026be6  cmp     rcx, r10
0x140026be9  jz      short loc_140026BFB
0x140026beb  cmp     rdx, rbx
0x140026bee  jb      short loc_140026C2A
0x140026bf0  mov     rdx, r10; Src
0x140026bf3  mov     r8, rbx; Size
0x140026bf6  call    memcpy_0
0x140026bfb  movzx   eax, bx
0x140026bfe  jmp     short loc_140026C59
0x140026c00  mov     r8, rbx
0x140026c03  mov     edx, 0
0x140026c08  shr     r8, 1
0x140026c0b  jz      short loc_140026C25
0x140026c0d  mov     eax, edx
0x140026c0f  movzx   ecx, word ptr [r10+rax*2]
0x140026c14  movzx   eax, cl
0x140026c17  cmp     ax, cx
0x140026c1a  jnz     short loc_140026C2E
0x140026c1c  inc     edx
0x140026c1e  mov     eax, edx
0x140026c20  cmp     rax, r8
0x140026c23  jnz     short loc_140026C0D
0x140026c25  cmp     rdi, r8
0x140026c28  jnb     short loc_140026C3D
0x140026c2a  xor     eax, eax
0x140026c2c  jmp     short loc_140026C59
0x140026c2e  cmp     r11, r10
0x140026c31  jz      short loc_140026BFB
0x140026c33  cmp     rdi, rbx
0x140026c36  jb      short loc_140026C2A
0x140026c38  mov     rcx, r11
0x140026c3b  jmp     short loc_140026BF0
0x140026c3d  xor     eax, eax
0x140026c3f  test    r8, r8
0x140026c42  jz      short loc_140026C55
0x140026c44  mov     cl, [r10+rax*2]
0x140026c48  mov     [rax+r11], cl
0x140026c4c  inc     eax
0x140026c4e  mov     ecx, eax
0x140026c50  cmp     rcx, r8
0x140026c53  jnz     short loc_140026C44
0x140026c55  movzx   eax, r8w
0x140026c59  mov     rbx, [rsp+28h+arg_0]
0x140026c5e  add     rsp, 20h
0x140026c62  pop     rdi
0x140026c63  retn
```
