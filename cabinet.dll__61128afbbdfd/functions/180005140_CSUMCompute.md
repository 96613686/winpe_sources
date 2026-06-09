# CSUMCompute

- ea: `0x180005140`
- end: `0x1800051c8`
- name: `CSUMCompute`
- size: `136`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800039b8`
- `0x180004f94`

## callees

- `0x180005140`

## pseudocode

```c
__int64 __fastcall CSUMCompute(unsigned __int8 *a1, unsigned int a2, int a3)
{
  int v4; // r9d
  char v5; // r11
  int v6; // r8d
  int v7; // edx
  int v8; // eax
  int v9; // r11d
  int v10; // r11d

  v4 = a2 >> 2;
  v5 = a2;
  if ( a2 >> 2 )
  {
    do
    {
      --v4;
      v6 = *(unsigned __int16 *)a1 | (a1[2] << 16);
      v7 = a1[3] << 24;
      a1 += 4;
      a3 ^= v6 | v7;
    }
    while ( v4 > 0 );
  }
  v8 = 0;
  v9 = (v5 & 3) - 1;
  if ( !v9 )
    goto LABEL_9;
  v10 = v9 - 1;
  if ( !v10 )
  {
LABEL_8:
    v8 |= *a1++ << 8;
LABEL_9:
    v8 |= *a1;
    return a3 ^ (unsigned int)v8;
  }
  if ( v10 == 1 )
  {
    v8 = *a1++ << 16;
    goto LABEL_8;
  }
  return a3 ^ (unsigned int)v8;
}

```

## disassembly

```asm
0x180005140  mov     r9d, edx
0x180005143  mov     r10d, r8d
0x180005146  shr     r9d, 2
0x18000514a  mov     r11d, edx
0x18000514d  test    r9d, r9d
0x180005150  jz      short loc_180005191
0x180005152  nop     dword ptr [rax+00h]
0x180005156  nop     word ptr [rax+rax+00000000h]
0x180005160  movzx   edx, byte ptr [rcx+1]
0x180005164  dec     r9d
0x180005167  movzx   eax, byte ptr [rcx]
0x18000516a  movzx   r8d, byte ptr [rcx+2]
0x18000516f  shl     edx, 8
0x180005172  or      edx, eax
0x180005174  shl     r8d, 10h
0x180005178  or      r8d, edx
0x18000517b  movzx   edx, byte ptr [rcx+3]
0x18000517f  shl     edx, 18h
0x180005182  add     rcx, 4
0x180005186  or      edx, r8d
0x180005189  xor     r10d, edx
0x18000518c  test    r9d, r9d
0x18000518f  jg      short loc_180005160
0x180005191  xor     eax, eax
0x180005193  and     r11d, 3
0x180005197  sub     r11d, 1
0x18000519b  jz      short loc_1800051C1
0x18000519d  sub     r11d, 1
0x1800051a1  jz      short loc_1800051B6
0x1800051a3  cmp     r11d, 1
0x1800051a7  jz      short loc_1800051AD
0x1800051a9  xor     eax, r10d
0x1800051ac  retn
0x1800051ad  movzx   eax, byte ptr [rcx]
0x1800051b0  shl     eax, 10h
0x1800051b3  inc     rcx
0x1800051b6  movzx   edx, byte ptr [rcx]
0x1800051b9  shl     edx, 8
0x1800051bc  or      eax, edx
0x1800051be  inc     rcx
0x1800051c1  movzx   edx, byte ptr [rcx]
0x1800051c4  or      eax, edx
0x1800051c6  jmp     short loc_1800051A9
```
