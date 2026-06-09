# acmdStreamSize

- ea: `0x18000297c`
- end: `0x180002ae4`
- name: `acmdStreamSize`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800020d0`

## callees

- `0x18000297c`

## pseudocode

```c
__int64 __fastcall acmdStreamSize(__int64 a1, _DWORD *a2)
{
  _WORD *v3; // r11
  _WORD *v4; // r10
  unsigned int v6; // edx
  unsigned int v7; // r8d
  int v8; // r8d
  unsigned int v9; // ecx
  unsigned int v10; // edx
  unsigned int v11; // r8d
  int v12; // r8d
  unsigned int v13; // r10d
  unsigned int v14; // edx
  __int64 v15; // rax

  v3 = *(_WORD **)(a1 + 4);
  v4 = *(_WORD **)(a1 + 12);
  if ( (a2[1] & 0xF) == 0 )
  {
    if ( *v3 == 49 )
    {
      v10 = a2[2] / 0x41u;
      if ( v10 - 1 > 0xCCCCCB )
        return 512;
      v11 = (unsigned __int16)v4[7] >> 3 << ((unsigned __int16)v4[1] >> 1);
      if ( 0xFFFFFFFF / v11 < 320 * v10 )
        return 512;
      v12 = 320 * v10 * v11;
    }
    else
    {
      v13 = a2[2] / ((unsigned __int16)v3[7] >> 3 << ((unsigned __int16)v3[1] >> 1));
      v14 = v13 / 0x140;
      if ( !(v13 / 0x140) )
        return 512;
      v15 = v14 + 1;
      if ( v13 == 320 * v14 )
        v15 = v14;
      v12 = 65 * v15;
      if ( (unsigned __int64)(65 * v15) > 0xFFFFFFFF )
        return 512;
    }
    a2[3] = v12;
    return 0;
  }
  if ( (a2[1] & 0xF) != 1 )
    return 8;
  if ( *v4 == 49 )
  {
    v6 = a2[3] / 0x41u;
    if ( v6 - 1 <= 0xCCCCCB )
    {
      v7 = (unsigned __int16)v3[7] >> 3 << ((unsigned __int16)v3[1] >> 1);
      if ( 0xFFFFFFFF / v7 >= 320 * v6 )
      {
        v8 = 320 * v6 * v7;
LABEL_10:
        a2[2] = v8;
        return 0;
      }
    }
  }
  else
  {
    v9 = a2[3] / ((unsigned __int16)v4[7] >> 3 << ((unsigned __int16)v4[1] >> 1));
    if ( v9 >= 0x140 )
    {
      v8 = 65 * (v9 / 0x140);
      goto LABEL_10;
    }
  }
  return 512;
}

```

## disassembly

```asm
0x18000297c  mov     eax, [rdx+4]
0x18000297f  mov     r9, rdx
0x180002982  mov     r11, [rcx+4]
0x180002986  mov     r10, [rcx+0Ch]
0x18000298a  and     eax, 0Fh
0x18000298d  jz      loc_180002A34
0x180002993  cmp     eax, 1
0x180002996  jz      short loc_18000299E
0x180002998  mov     eax, 8
0x18000299d  retn
0x18000299e  mov     eax, 31h ; '1'
0x1800029a3  cmp     ax, [r10]
0x1800029a7  jnz     short loc_1800029F6
0x1800029a9  mov     eax, 0FC0FC0FDh
0x1800029ae  mul     dword ptr [rdx+0Ch]
0x1800029b1  shr     edx, 6
0x1800029b4  lea     eax, [rdx-1]
0x1800029b7  cmp     eax, 0CCCCCBh
0x1800029bc  ja      loc_180002ADE
0x1800029c2  movzx   r8d, word ptr [r11+0Eh]
0x1800029c7  lea     r10d, [rdx+rdx*4]
0x1800029cb  movzx   ecx, word ptr [r11+2]
0x1800029d0  xor     edx, edx
0x1800029d2  shr     r8d, 3
0x1800029d6  mov     eax, 0FFFFFFFFh
0x1800029db  shr     ecx, 1
0x1800029dd  shl     r8d, cl
0x1800029e0  div     r8d
0x1800029e3  shl     r10d, 6
0x1800029e7  cmp     eax, r10d
0x1800029ea  jb      loc_180002ADE
0x1800029f0  imul    r8d, r10d
0x1800029f4  jmp     short loc_180002A2D
0x1800029f6  movzx   r8d, word ptr [r10+0Eh]
0x1800029fb  xor     edx, edx
0x1800029fd  movzx   ecx, word ptr [r10+2]
0x180002a02  mov     eax, [r9+0Ch]
0x180002a06  shr     ecx, 1
0x180002a08  shr     r8d, 3
0x180002a0c  shl     r8d, cl
0x180002a0f  div     r8d
0x180002a12  mov     ecx, eax
0x180002a14  cmp     eax, 140h
0x180002a19  jb      loc_180002ADE
0x180002a1f  mov     eax, 0CCCCCCCDh
0x180002a24  mul     ecx
0x180002a26  shr     edx, 8
0x180002a29  imul    r8d, edx, 41h ; 'A'
0x180002a2d  mov     [r9+8], r8d
0x180002a31  xor     eax, eax
0x180002a33  retn
0x180002a34  mov     eax, 31h ; '1'
0x180002a39  cmp     ax, [r11]
0x180002a3d  jnz     short loc_180002A88
0x180002a3f  mov     eax, 0FC0FC0FDh
0x180002a44  mul     dword ptr [rdx+8]
0x180002a47  shr     edx, 6
0x180002a4a  lea     eax, [rdx-1]
0x180002a4d  cmp     eax, 0CCCCCBh
0x180002a52  ja      loc_180002ADE
0x180002a58  movzx   r8d, word ptr [r10+0Eh]
0x180002a5d  lea     r11d, [rdx+rdx*4]
0x180002a61  movzx   ecx, word ptr [r10+2]
0x180002a66  xor     edx, edx
0x180002a68  shr     r8d, 3
0x180002a6c  mov     eax, 0FFFFFFFFh
0x180002a71  shr     ecx, 1
0x180002a73  shl     r8d, cl
0x180002a76  div     r8d
0x180002a79  shl     r11d, 6
0x180002a7d  cmp     eax, r11d
0x180002a80  jb      short loc_180002ADE
0x180002a82  imul    r8d, r11d
0x180002a86  jmp     short loc_180002AD5
0x180002a88  movzx   r8d, word ptr [r11+0Eh]
0x180002a8d  xor     edx, edx
0x180002a8f  movzx   ecx, word ptr [r11+2]
0x180002a94  mov     eax, [r9+8]
0x180002a98  shr     r8d, 3
0x180002a9c  shr     ecx, 1
0x180002a9e  shl     r8d, cl
0x180002aa1  div     r8d
0x180002aa4  mov     r10d, eax
0x180002aa7  mov     eax, 0CCCCCCCDh
0x180002aac  mul     r10d
0x180002aaf  shr     edx, 8
0x180002ab2  test    edx, edx
0x180002ab4  jz      short loc_180002ADE
0x180002ab6  lea     eax, [rdx+1]
0x180002ab9  lea     r8d, [rdx+rdx*4]
0x180002abd  shl     r8d, 6
0x180002ac1  cmp     r10d, r8d
0x180002ac4  cmovz   eax, edx
0x180002ac7  imul    r8, rax, 41h ; 'A'
0x180002acb  mov     eax, 0FFFFFFFFh
0x180002ad0  cmp     r8, rax
0x180002ad3  ja      short loc_180002ADE
0x180002ad5  mov     [r9+0Ch], r8d
0x180002ad9  jmp     loc_180002A31
0x180002ade  mov     eax, 200h
0x180002ae3  retn
```
