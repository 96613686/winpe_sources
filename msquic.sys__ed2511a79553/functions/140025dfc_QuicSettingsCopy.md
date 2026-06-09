# QuicSettingsCopy

- ea: `0x140025dfc`
- end: `0x1400262ab`
- name: `QuicSettingsCopy`
- size: `1199`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140007b30`
- `0x140025d70`

## callees

- `0x140025dfc`
- `0x14002c014`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140026034`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026034`

## pseudocode

```c
char __fastcall QuicSettingsCopy(__int64 *a1, __int64 a2)
{
  __int64 v2; // r8
  _BYTE *v3; // r9
  _BYTE *v4; // r10
  _BYTE *v7; // rdx
  _BYTE *v8; // r11
  void *v9; // rcx
  __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rax
  _BYTE *v13; // r8
  _BYTE *v14; // r9
  _BYTE *v15; // r11
  _BYTE *v16; // r10

  v2 = *a1;
  v3 = (char *)a1 + 139;
  v4 = (_BYTE *)(a2 + 139);
  if ( (*a1 & 0x2000000) == 0 )
    *v3 ^= (*v4 ^ *v3) & 1;
  v7 = (_BYTE *)(a2 + 139);
  v8 = (char *)a1 + 139;
  if ( (v2 & 0x4000000) == 0 )
    *v3 ^= (*v4 ^ *v3) & 2;
  if ( (v2 & 0x8000000) != 0 )
  {
    v7 = v4;
    v8 = (char *)a1 + 139;
  }
  else
  {
    *v3 ^= (*v4 ^ *v3) & 4;
  }
  if ( (v2 & 0x10000000) == 0 )
    *v8 = *v3 ^ (*v7 ^ *v3) & 8;
  if ( (v2 & 0x1000000) == 0 )
    *((_BYTE *)a1 + 138) = *(_BYTE *)(a2 + 138);
  if ( (v2 & 0x200000) == 0 )
    *((_WORD *)a1 + 62) = *(_WORD *)(a2 + 124);
  if ( (v2 & 0x400000) == 0 )
    *((_WORD *)a1 + 63) = *(_WORD *)(a2 + 126);
  if ( (v2 & 0x800000) == 0 )
    *((_DWORD *)a1 + 29) = *(_DWORD *)(a2 + 116);
  if ( (v2 & 0x800) == 0 )
    *((_DWORD *)a1 + 20) = *(_DWORD *)(a2 + 80);
  if ( (v2 & 0x1000) == 0 )
    *((_DWORD *)a1 + 21) = *(_DWORD *)(a2 + 84);
  if ( (v2 & 0x2000) == 0 )
    *((_DWORD *)a1 + 22) = *(_DWORD *)(a2 + 88);
  if ( (v2 & 0x4000) == 0 )
    *((_DWORD *)a1 + 23) = *(_DWORD *)(a2 + 92);
  if ( (v2 & 0x8000) == 0 )
    *((_DWORD *)a1 + 24) = *(_DWORD *)(a2 + 96);
  if ( (v2 & 0x10000) == 0 )
    *((_DWORD *)a1 + 25) = *(_DWORD *)(a2 + 100);
  if ( (v2 & 0x20000) == 0 )
    *((_DWORD *)a1 + 26) = *(_DWORD *)(a2 + 104);
  if ( (v2 & 0x40000) == 0 )
    *((_DWORD *)a1 + 27) = *(_DWORD *)(a2 + 108);
  if ( (v2 & 4) == 0 )
    a1[4] = *(_QWORD *)(a2 + 32);
  if ( (v2 & 2) == 0 )
    a1[3] = *(_QWORD *)(a2 + 24);
  if ( (v2 & 0x80000) == 0 )
    *((_WORD *)a1 + 60) = *(_WORD *)(a2 + 120);
  if ( (v2 & 0x100000) == 0 )
    *((_WORD *)a1 + 61) = *(_WORD *)(a2 + 122);
  if ( (v2 & 8) == 0 )
  {
    *((_DWORD *)a1 + 12) = *(_DWORD *)(a2 + 48);
    *((_DWORD *)a1 + 12) = *(_DWORD *)(a2 + 48);
  }
  if ( (v2 & 0x20) == 0 )
    *((_DWORD *)a1 + 14) = *(_DWORD *)(a2 + 56);
  if ( (v2 & 0x40) == 0 )
    *((_DWORD *)a1 + 15) = *(_DWORD *)(a2 + 60);
  if ( (v2 & 0x80u) == 0LL )
    *((_DWORD *)a1 + 16) = *(_DWORD *)(a2 + 64);
  if ( (v2 & 0x100) == 0 )
    *((_DWORD *)a1 + 17) = *(_DWORD *)(a2 + 68);
  if ( (v2 & 0x200) == 0 )
    *((_DWORD *)a1 + 18) = *(_DWORD *)(a2 + 72);
  if ( (v2 & 0x400) == 0 )
    *((_DWORD *)a1 + 19) = *(_DWORD *)(a2 + 76);
  if ( (v2 & 1) == 0 )
    a1[2] = *(_QWORD *)(a2 + 16);
  if ( (v2 & 0x20000000) == 0 )
    *((_BYTE *)a1 + 139) ^= (*(_BYTE *)(a2 + 139) ^ *((_BYTE *)a1 + 139)) & 0x30;
  if ( (v2 & 0x80000000) == 0 )
    *((_BYTE *)a1 + 139) ^= (*(_BYTE *)(a2 + 139) ^ *((_BYTE *)a1 + 139)) & 0x40;
  if ( (v2 & 0x40000000) == 0 )
  {
    v9 = (void *)a1[1];
    if ( v9 )
    {
      ExFreePoolWithTag(v9, 0x30346351u);
      a1[1] = 0;
    }
    v10 = *(_QWORD *)(a2 + 8);
    if ( v10 )
      a1[1] = QuicSettingsCopyVersionSettings(v10, 0);
  }
  v11 = *a1;
  if ( (*a1 & 0x300000000LL) == 0 )
  {
    *((_WORD *)a1 + 64) = *(_WORD *)(a2 + 128);
    LOWORD(v12) = *(_WORD *)(a2 + 130);
LABEL_72:
    *((_WORD *)a1 + 65) = v12;
    goto LABEL_77;
  }
  v12 = v11 >> 33;
  if ( (v11 & 0x100000000LL) != 0 )
  {
    if ( (v11 & 0x200000000LL) == 0 )
    {
      LOWORD(v12) = *(_WORD *)(a2 + 130);
      if ( (unsigned __int16)v12 <= *((_WORD *)a1 + 64) )
        goto LABEL_77;
      goto LABEL_72;
    }
  }
  else if ( (v11 & 0x200000000LL) == 0 )
  {
    goto LABEL_77;
  }
  if ( (v11 & 0x100000000LL) == 0 )
  {
    LOWORD(v12) = *(_WORD *)(a2 + 128);
    if ( (unsigned __int16)v12 < *((_WORD *)a1 + 65) )
      *((_WORD *)a1 + 64) = v12;
  }
LABEL_77:
  if ( (v11 & 0x800000000LL) == 0 )
  {
    LOBYTE(v12) = *(_BYTE *)(a2 + 142);
    *((_BYTE *)a1 + 142) = v12;
  }
  if ( (v11 & 0x400000000LL) == 0 )
  {
    v12 = *(_QWORD *)(a2 + 40);
    a1[5] = v12;
  }
  if ( (v11 & 0x1000000000LL) == 0 )
  {
    LOWORD(v12) = *(_WORD *)(a2 + 132);
    *((_WORD *)a1 + 66) = v12;
  }
  if ( (v11 & 0x2000000000LL) == 0 )
  {
    LOWORD(v12) = *(_WORD *)(a2 + 134);
    *((_WORD *)a1 + 67) = v12;
  }
  if ( (v11 & 0x4000000000LL) == 0 )
  {
    LOWORD(v12) = *(_WORD *)(a2 + 136);
    *((_WORD *)a1 + 68) = v12;
  }
  if ( (v11 & 0x8000000000LL) == 0 )
  {
    LODWORD(v12) = *(_DWORD *)(a2 + 112);
    *((_DWORD *)a1 + 28) = v12;
  }
  if ( (v11 & 0x10000000000LL) == 0 )
  {
    LOBYTE(v12) = *(_BYTE *)(a2 + 139);
    *((_BYTE *)a1 + 139) = v12 ^ (*((_BYTE *)a1 + 139) ^ v12) & 0x7F;
  }
  v13 = (char *)a1 + 140;
  v14 = (_BYTE *)(a2 + 140);
  if ( (v11 & 0x20000000000LL) == 0 )
  {
    LOBYTE(v12) = *v13 ^ (*v14 ^ *v13) & 1;
    *v13 = v12;
  }
  if ( (v11 & 0x40000000000LL) != 0 )
  {
    v15 = (_BYTE *)(a2 + 140);
    v16 = (char *)a1 + 140;
  }
  else
  {
    LOBYTE(v12) = *v13;
    v15 = (_BYTE *)(a2 + 140);
    v16 = (char *)a1 + 140;
    *v13 ^= (*v14 ^ *v13) & 2;
  }
  if ( (v11 & 0x80000000000LL) != 0 )
  {
    v15 = (_BYTE *)(a2 + 140);
    v16 = (char *)a1 + 140;
  }
  else
  {
    LOBYTE(v12) = *v13;
    *v13 ^= (*v14 ^ *v13) & 4;
  }
  if ( (v11 & 0x100000000000LL) == 0 )
  {
    LOBYTE(v12) = *v13;
    *v16 = *v13 ^ (*v15 ^ *v13) & 8;
  }
  if ( (v11 & 0x1000000000000LL) == 0 )
  {
    LOBYTE(v12) = *v15;
    *v16 = *v15 ^ (*v16 ^ *v15) & 0x7F;
  }
  if ( (v11 & 0x2000000000000LL) == 0 )
  {
    LOBYTE(v12) = *((_BYTE *)a1 + 141) ^ (*(_BYTE *)(a2 + 141) ^ *((_BYTE *)a1 + 141)) & 1;
    *((_BYTE *)a1 + 141) = v12;
  }
  if ( (v11 & 0x4000000000000LL) == 0 )
  {
    LOBYTE(v12) = *((_BYTE *)a1 + 141);
    *((_BYTE *)a1 + 141) = v12 ^ (*(_BYTE *)(a2 + 141) ^ v12) & 2;
  }
  if ( (v11 & 0x200000000000LL) == 0 )
  {
    LOBYTE(v12) = *((_BYTE *)a1 + 140) ^ (*(_BYTE *)(a2 + 140) ^ *((_BYTE *)a1 + 140)) & 0x10;
    *((_BYTE *)a1 + 140) = v12;
  }
  if ( (v11 & 0x400000000000LL) == 0 )
  {
    LOBYTE(v12) = *((_BYTE *)a1 + 140);
    *((_BYTE *)a1 + 140) = v12 ^ (*(_BYTE *)(a2 + 140) ^ v12) & 0x20;
  }
  if ( (v11 & 0x800000000000LL) == 0 )
  {
    LOBYTE(v12) = *((_BYTE *)a1 + 140);
    *((_BYTE *)a1 + 140) = v12 ^ (*(_BYTE *)(a2 + 140) ^ v12) & 0x40;
  }
  return v12;
}

```

## disassembly

```asm
0x140025dfc  mov     [rsp+arg_0], rbx
0x140025e01  push    rdi
0x140025e02  sub     rsp, 20h
0x140025e06  mov     r8, [rcx]
0x140025e09  lea     r9, [rcx+8Bh]
0x140025e10  lea     r10, [rdx+8Bh]
0x140025e17  mov     rdi, rdx
0x140025e1a  mov     rbx, rcx
0x140025e1d  bt      r8, 19h
0x140025e22  jb      short loc_140025E34
0x140025e24  mov     al, [r9]
0x140025e27  mov     dl, al
0x140025e29  xor     dl, [r10]
0x140025e2c  and     dl, 1
0x140025e2f  xor     dl, al
0x140025e31  mov     [r9], dl
0x140025e34  bt      r8, 1Ah
0x140025e39  jb      short loc_140025E5B
0x140025e3b  mov     al, [r9]
0x140025e3e  lea     rdx, [rdi+8Bh]
0x140025e45  mov     cl, al
0x140025e47  lea     r11, [rbx+8Bh]
0x140025e4e  xor     cl, [r10]
0x140025e51  and     cl, 2
0x140025e54  xor     cl, al
0x140025e56  mov     [r9], cl
0x140025e59  jmp     short loc_140025E61
0x140025e5b  mov     rdx, r10
0x140025e5e  mov     r11, r9
0x140025e61  bt      r8, 1Bh
0x140025e66  jb      short loc_140025E7A
0x140025e68  mov     al, [r9]
0x140025e6b  mov     cl, al
0x140025e6d  xor     cl, [r10]
0x140025e70  and     cl, 4
0x140025e73  xor     cl, al
0x140025e75  mov     [r9], cl
0x140025e78  jmp     short loc_140025E80
0x140025e7a  mov     rdx, r10
0x140025e7d  mov     r11, r9
0x140025e80  bt      r8, 1Ch
0x140025e85  jb      short loc_140025E96
0x140025e87  mov     al, [r9]
0x140025e8a  mov     cl, al
0x140025e8c  xor     cl, [rdx]
0x140025e8e  and     cl, 8
0x140025e91  xor     cl, al
0x140025e93  mov     [r11], cl
0x140025e96  bt      r8, 18h
0x140025e9b  jb      short loc_140025EA9
0x140025e9d  mov     al, [rdi+8Ah]
0x140025ea3  mov     [rbx+8Ah], al
0x140025ea9  bt      r8, 15h
0x140025eae  jb      short loc_140025EB8
0x140025eb0  movzx   eax, word ptr [rdi+7Ch]
0x140025eb4  mov     [rbx+7Ch], ax
0x140025eb8  bt      r8, 16h
0x140025ebd  jb      short loc_140025EC7
0x140025ebf  movzx   eax, word ptr [rdi+7Eh]
0x140025ec3  mov     [rbx+7Eh], ax
0x140025ec7  bt      r8, 17h
0x140025ecc  jb      short loc_140025ED4
0x140025ece  mov     eax, [rdi+74h]
0x140025ed1  mov     [rbx+74h], eax
0x140025ed4  bt      r8, 0Bh
0x140025ed9  jb      short loc_140025EE1
0x140025edb  mov     eax, [rdi+50h]
0x140025ede  mov     [rbx+50h], eax
0x140025ee1  bt      r8, 0Ch
0x140025ee6  jb      short loc_140025EEE
0x140025ee8  mov     eax, [rdi+54h]
0x140025eeb  mov     [rbx+54h], eax
0x140025eee  bt      r8, 0Dh
0x140025ef3  jb      short loc_140025EFB
0x140025ef5  mov     eax, [rdi+58h]
0x140025ef8  mov     [rbx+58h], eax
0x140025efb  bt      r8, 0Eh
0x140025f00  jb      short loc_140025F08
0x140025f02  mov     eax, [rdi+5Ch]
0x140025f05  mov     [rbx+5Ch], eax
0x140025f08  bt      r8, 0Fh
0x140025f0d  jb      short loc_140025F15
0x140025f0f  mov     eax, [rdi+60h]
0x140025f12  mov     [rbx+60h], eax
0x140025f15  bt      r8, 10h
0x140025f1a  jb      short loc_140025F22
0x140025f1c  mov     eax, [rdi+64h]
0x140025f1f  mov     [rbx+64h], eax
0x140025f22  bt      r8, 11h
0x140025f27  jb      short loc_140025F2F
0x140025f29  mov     eax, [rdi+68h]
0x140025f2c  mov     [rbx+68h], eax
0x140025f2f  bt      r8, 12h
0x140025f34  jb      short loc_140025F3C
0x140025f36  mov     eax, [rdi+6Ch]
0x140025f39  mov     [rbx+6Ch], eax
0x140025f3c  test    r8b, 4
0x140025f40  jnz     short loc_140025F4A
0x140025f42  mov     rax, [rdi+20h]
0x140025f46  mov     [rbx+20h], rax
0x140025f4a  test    r8b, 2
0x140025f4e  jnz     short loc_140025F58
0x140025f50  mov     rax, [rdi+18h]
0x140025f54  mov     [rbx+18h], rax
0x140025f58  bt      r8, 13h
0x140025f5d  jb      short loc_140025F67
0x140025f5f  movzx   eax, word ptr [rdi+78h]
0x140025f63  mov     [rbx+78h], ax
0x140025f67  bt      r8, 14h
0x140025f6c  jb      short loc_140025F76
0x140025f6e  movzx   eax, word ptr [rdi+7Ah]
0x140025f72  mov     [rbx+7Ah], ax
0x140025f76  test    r8b, 8
0x140025f7a  jnz     short loc_140025F88
0x140025f7c  mov     eax, [rdi+30h]
0x140025f7f  mov     [rbx+30h], eax
0x140025f82  mov     eax, [rdi+30h]
0x140025f85  mov     [rbx+30h], eax
0x140025f88  test    r8b, 20h
0x140025f8c  jnz     short loc_140025F94
0x140025f8e  mov     eax, [rdi+38h]
0x140025f91  mov     [rbx+38h], eax
0x140025f94  test    r8b, 40h
0x140025f98  jnz     short loc_140025FA0
0x140025f9a  mov     eax, [rdi+3Ch]
0x140025f9d  mov     [rbx+3Ch], eax
0x140025fa0  test    r8b, r8b
0x140025fa3  js      short loc_140025FAB
0x140025fa5  mov     eax, [rdi+40h]
0x140025fa8  mov     [rbx+40h], eax
0x140025fab  bt      r8, 8
0x140025fb0  jb      short loc_140025FB8
0x140025fb2  mov     eax, [rdi+44h]
0x140025fb5  mov     [rbx+44h], eax
0x140025fb8  bt      r8, 9
0x140025fbd  jb      short loc_140025FC5
0x140025fbf  mov     eax, [rdi+48h]
0x140025fc2  mov     [rbx+48h], eax
0x140025fc5  bt      r8, 0Ah
0x140025fca  jb      short loc_140025FD2
0x140025fcc  mov     eax, [rdi+4Ch]
0x140025fcf  mov     [rbx+4Ch], eax
0x140025fd2  test    r8b, 1
0x140025fd6  jnz     short loc_140025FE0
0x140025fd8  mov     rax, [rdi+10h]
0x140025fdc  mov     [rbx+10h], rax
0x140025fe0  bt      r8, 1Dh
0x140025fe5  jb      short loc_140025FFF
0x140025fe7  mov     cl, [rbx+8Bh]
0x140025fed  mov     al, cl
0x140025fef  xor     al, [rdi+8Bh]
0x140025ff5  and     al, 30h
0x140025ff7  xor     al, cl
0x140025ff9  mov     [rbx+8Bh], al
0x140025fff  bt      r8, 1Fh
0x140026004  jb      short loc_14002601F
0x140026006  mov     al, [rbx+8Bh]
0x14002600c  mov     cl, al
0x14002600e  xor     cl, [rdi+8Bh]
0x140026014  and     cl, 40h
0x140026017  xor     cl, al
0x140026019  mov     [rbx+8Bh], cl
0x14002601f  bt      r8, 1Eh
0x140026024  jb      short loc_140026059
0x140026026  mov     rcx, [rbx+8]; P
0x14002602a  test    rcx, rcx
0x14002602d  jz      short loc_140026045
0x14002602f  mov     edx, 30346351h; Tag
0x140026034  call    cs:__imp_ExFreePoolWithTag
0x14002603b  nop     dword ptr [rax+rax+00h]
0x140026040  and     qword ptr [rbx+8], 0
0x140026045  mov     rcx, [rdi+8]
0x140026049  test    rcx, rcx
0x14002604c  jz      short loc_140026059
0x14002604e  xor     edx, edx
0x140026050  call    QuicSettingsCopyVersionSettings
0x140026055  mov     [rbx+8], rax
0x140026059  mov     rdx, [rbx]
0x14002605c  mov     rax, 300000000h
0x140026066  test    rax, rdx
0x140026069  jnz     short loc_140026082
0x14002606b  movzx   eax, word ptr [rdi+80h]
0x140026072  mov     [rbx+80h], ax
0x140026079  movzx   eax, word ptr [rdi+82h]
0x140026080  jmp     short loc_1400260AC
0x140026082  mov     rcx, rdx
0x140026085  mov     rax, rdx
0x140026088  shr     rcx, 20h
0x14002608c  and     ecx, 1
0x14002608f  shr     rax, 21h
0x140026093  test    rcx, rcx
0x140026096  jz      short loc_1400260B5
0x140026098  test    al, 1
0x14002609a  jnz     short loc_1400260B9
0x14002609c  movzx   eax, word ptr [rdi+82h]
0x1400260a3  cmp     ax, [rbx+80h]
0x1400260aa  jbe     short loc_1400260D5
0x1400260ac  mov     [rbx+82h], ax
0x1400260b3  jmp     short loc_1400260D5
0x1400260b5  test    al, 1
0x1400260b7  jz      short loc_1400260D5
0x1400260b9  test    rcx, rcx
0x1400260bc  jnz     short loc_1400260D5
0x1400260be  movzx   eax, word ptr [rdi+80h]
0x1400260c5  cmp     ax, [rbx+82h]
0x1400260cc  jnb     short loc_1400260D5
0x1400260ce  mov     [rbx+80h], ax
0x1400260d5  bt      rdx, 23h ; '#'
0x1400260da  jb      short loc_1400260E8
0x1400260dc  mov     al, [rdi+8Eh]
0x1400260e2  mov     [rbx+8Eh], al
0x1400260e8  bt      rdx, 22h ; '"'
0x1400260ed  jb      short loc_1400260F7
0x1400260ef  mov     rax, [rdi+28h]
0x1400260f3  mov     [rbx+28h], rax
0x1400260f7  bt      rdx, 24h ; '$'
0x1400260fc  jb      short loc_14002610C
0x1400260fe  movzx   eax, word ptr [rdi+84h]
0x140026105  mov     [rbx+84h], ax
0x14002610c  bt      rdx, 25h ; '%'
0x140026111  jb      short loc_140026121
0x140026113  movzx   eax, word ptr [rdi+86h]
0x14002611a  mov     [rbx+86h], ax
0x140026121  bt      rdx, 26h ; '&'
0x140026126  jb      short loc_140026136
0x140026128  movzx   eax, word ptr [rdi+88h]
0x14002612f  mov     [rbx+88h], ax
0x140026136  bt      rdx, 27h ; '''
0x14002613b  jb      short loc_140026143
0x14002613d  mov     eax, [rdi+70h]
0x140026140  mov     [rbx+70h], eax
0x140026143  bt      rdx, 28h ; '('
0x140026148  jb      short loc_140026163
0x14002614a  mov     al, [rdi+8Bh]
0x140026150  mov     cl, al
0x140026152  xor     cl, [rbx+8Bh]
0x140026158  and     cl, 7Fh
0x14002615b  xor     cl, al
0x14002615d  mov     [rbx+8Bh], cl
0x140026163  bt      rdx, 29h ; ')'
0x140026168  lea     r8, [rbx+8Ch]
0x14002616f  lea     r9, [rdi+8Ch]
0x140026176  jb      short loc_140026187
0x140026178  mov     cl, [r8]
0x14002617b  mov     al, cl
0x14002617d  xor     al, [r9]
0x140026180  and     al, 1
0x140026182  xor     al, cl
0x140026184  mov     [r8], al
0x140026187  bt      rdx, 2Ah ; '*'
0x14002618c  jb      short loc_1400261AE
0x14002618e  mov     al, [r8]
0x140026191  lea     r11, [rdi+8Ch]
0x140026198  mov     cl, al
0x14002619a  lea     r10, [rbx+8Ch]
0x1400261a1  xor     cl, [r9]
0x1400261a4  and     cl, 2
0x1400261a7  xor     cl, al
0x1400261a9  mov     [r8], cl
0x1400261ac  jmp     short loc_1400261B4
0x1400261ae  mov     r11, r9
0x1400261b1  mov     r10, r8
0x1400261b4  bt      rdx, 2Bh ; '+'
0x1400261b9  jb      short loc_1400261CD
0x1400261bb  mov     al, [r8]
0x1400261be  mov     cl, al
0x1400261c0  xor     cl, [r9]
0x1400261c3  and     cl, 4
0x1400261c6  xor     cl, al
0x1400261c8  mov     [r8], cl
0x1400261cb  jmp     short loc_1400261D3
0x1400261cd  mov     r11, r9
0x1400261d0  mov     r10, r8
0x1400261d3  bt      rdx, 2Ch ; ','
0x1400261d8  jb      short loc_1400261EA
0x1400261da  mov     al, [r8]
0x1400261dd  mov     cl, al
0x1400261df  xor     cl, [r11]
0x1400261e2  and     cl, 8
0x1400261e5  xor     cl, al
0x1400261e7  mov     [r10], cl
0x1400261ea  bt      rdx, 30h ; '0'
0x1400261ef  jb      short loc_140026201
0x1400261f1  mov     al, [r11]
0x1400261f4  mov     cl, al
0x1400261f6  xor     cl, [r10]
0x1400261f9  and     cl, 7Fh
0x1400261fc  xor     cl, al
0x1400261fe  mov     [r10], cl
0x140026201  bt      rdx, 31h ; '1'
0x140026206  jb      short loc_140026220
0x140026208  mov     cl, [rbx+8Dh]
0x14002620e  mov     al, cl
0x140026210  xor     al, [rdi+8Dh]
0x140026216  and     al, 1
0x140026218  xor     al, cl
0x14002621a  mov     [rbx+8Dh], al
0x140026220  bt      rdx, 32h ; '2'
0x140026225  jb      short loc_140026240
0x140026227  mov     al, [rbx+8Dh]
  ... truncated ...
```
