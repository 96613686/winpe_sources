# CheckSize(DIRECTCOLORCONVFRM *)

- ea: `0x180008f30`
- end: `0x1800091bf`
- name: `?CheckSize@@YA?AW4tagColorConvertStatus@@PEAUDIRECTCOLORCONVFRM@@@Z`
- size: `655`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180009660`
- `0x18000fe84`
- `0x180019ea4`
- `0x18001f874`

## callees

- `0x180008f30`

## pseudocode

```c
__int64 __fastcall CheckSize(__int64 *a1)
{
  __int64 v1; // rdi
  int v3; // r10d
  _DWORD *v4; // rbx
  int v5; // r11d
  int v6; // r8d
  int v7; // r9d
  int v8; // eax
  int v9; // ecx
  bool v10; // zf
  int v11; // ecx
  int v12; // eax
  int v13; // eax
  unsigned int v14; // ecx
  int v15; // eax
  bool v16; // zf

  v1 = *a1;
  v3 = *(_DWORD *)(*a1 + 4);
  if ( v3 <= 0 )
    return 6;
  v4 = (_DWORD *)a1[1];
  v5 = v4[1];
  if ( v5 <= 0 )
    return 6;
  v6 = *(_DWORD *)(v1 + 16);
  if ( (!v6 || v6 == 3) && (!v4[4] || v4[4] == 3) )
    return 0;
  if ( *((_DWORD *)a1 + 3820) )
  {
    if ( v5 != *((_DWORD *)a1 + 3818) - *((_DWORD *)a1 + 3816) )
      return 6;
    v7 = v4[2];
    v8 = *((_DWORD *)a1 + 3819);
    v9 = -v7;
    if ( v7 > 0 )
      v9 = v4[2];
    v10 = v9 == v8 - *((_DWORD *)a1 + 3817);
  }
  else
  {
    if ( v3 != v5 )
      return 6;
    v7 = v4[2];
    v11 = -v7;
    if ( v7 > 0 )
      v11 = v4[2];
    v12 = -*(_DWORD *)(v1 + 8);
    if ( *(int *)(v1 + 8) > 0 )
      v12 = *(_DWORD *)(v1 + 8);
    v10 = v12 == v11;
  }
  if ( !v10 )
    return 6;
  if ( v6 == 961893977 )
  {
    if ( v3 % 4 )
      return 6;
    v13 = -*(_DWORD *)(v1 + 8);
    if ( *(int *)(v1 + 8) > 0 )
      v13 = *(_DWORD *)(v1 + 8);
    if ( v13 % 4 )
      return 6;
  }
  v14 = v4[4];
  if ( v14 == 961893977 )
  {
    if ( v5 % 4 )
      return 6;
    v15 = -v7;
    if ( v7 > 0 )
      v15 = v7;
    if ( v15 % 4 )
      return 6;
  }
  if ( (v6 == 825308240 || v6 == 825316942) && v3 % 4 || (v14 == 825308240 || v14 == 825316942) && v5 % 4 )
    return 6;
  if ( v6 == 1345401945 || v6 == 1412510809 )
  {
    v16 = v3 % 8 == 0;
  }
  else
  {
    if ( v6 != 844715353
      && v6 != 1498831189
      && v6 != 1431918169
      && v6 != 909193814
      && v6 != 808531030
      && v6 != 1448433993
      && v6 != 808596553
      && v6 != 842150992
      && v6 != 842094158
      && v6 != 842094169 )
    {
      goto LABEL_50;
    }
    v16 = (v3 & 1) == 0;
  }
  if ( !v16 )
    return 6;
LABEL_50:
  if ( (v14 == 844715353
     || v14 == 1498831189
     || v14 == 1431918169
     || v14 == 909193814
     || v14 == 808531030
     || v14 == 1448433993
     || v14 == 808596553
     || v14 == 842150992
     || v14 == 842094158
     || v14 == 842094169)
    && (v5 & 1) != 0 )
  {
    return 6;
  }
  if ( v6 == 1448433993 || v6 == 808596553 )
  {
    if ( v14 <= 3 || v14 == 844715353 || v14 == 1498831189 || v14 == 1431918169 || v14 == 825316942 )
      return 0;
LABEL_71:
    if ( (*(_BYTE *)(v1 + 8) & 1) != 0 )
      return 6;
    goto LABEL_72;
  }
  if ( v6 == 842094169 || v6 == 842094158 )
    goto LABEL_71;
LABEL_72:
  if ( v14 != 1448433993 && v14 != 808596553 && v14 != 842094169 && v14 != 842094158 || (v4[2] & 1) == 0 )
    return 0;
  return 6;
}

```

## disassembly

```asm
0x180008f30  push    rbx
0x180008f32  push    rbp
0x180008f33  push    rsi
0x180008f34  push    rdi
0x180008f35  push    r14
0x180008f37  push    r15
0x180008f39  mov     rdi, [rcx]
0x180008f3c  mov     rdx, rcx
0x180008f3f  mov     r10d, [rdi+4]
0x180008f43  test    r10d, r10d
0x180008f46  jle     loc_1800091B1
0x180008f4c  mov     rbx, [rcx+8]
0x180008f50  mov     r11d, [rbx+4]
0x180008f54  test    r11d, r11d
0x180008f57  jle     loc_1800091B1
0x180008f5d  mov     r8d, [rdi+10h]
0x180008f61  test    r8d, r8d
0x180008f64  jz      short loc_180008F6C
0x180008f66  cmp     r8d, 3
0x180008f6a  jnz     short loc_180008F80
0x180008f6c  cmp     dword ptr [rbx+10h], 0
0x180008f70  jz      loc_1800091AD
0x180008f76  cmp     dword ptr [rbx+10h], 3
0x180008f7a  jz      loc_1800091AD
0x180008f80  cmp     dword ptr [rcx+3BB0h], 0
0x180008f87  jz      short loc_180008FBB
0x180008f89  mov     eax, [rcx+3BA8h]
0x180008f8f  sub     eax, [rcx+3BA0h]
0x180008f95  cmp     r11d, eax
0x180008f98  jnz     loc_1800091B1
0x180008f9e  mov     r9d, [rbx+8]
0x180008fa2  mov     ecx, r9d
0x180008fa5  mov     eax, [rdx+3BACh]
0x180008fab  neg     ecx
0x180008fad  cmovs   ecx, r9d
0x180008fb1  sub     eax, [rdx+3BA4h]
0x180008fb7  cmp     ecx, eax
0x180008fb9  jmp     short loc_180008FDC
0x180008fbb  cmp     r10d, r11d
0x180008fbe  jnz     loc_1800091B1
0x180008fc4  mov     r9d, [rbx+8]
0x180008fc8  mov     ecx, r9d
0x180008fcb  mov     eax, [rdi+8]
0x180008fce  neg     ecx
0x180008fd0  cmovs   ecx, r9d
0x180008fd4  neg     eax
0x180008fd6  cmovs   eax, [rdi+8]
0x180008fda  cmp     eax, ecx
0x180008fdc  jnz     loc_1800091B1
0x180008fe2  mov     ebp, 39555659h
0x180008fe7  mov     esi, 4
0x180008fec  cmp     r8d, ebp
0x180008fef  jnz     short loc_180009013
0x180008ff1  mov     eax, r10d
0x180008ff4  cdq
0x180008ff5  idiv    esi
0x180008ff7  test    edx, edx
0x180008ff9  jnz     loc_1800091B1
0x180008fff  mov     eax, [rdi+8]
0x180009002  neg     eax
0x180009004  cmovs   eax, [rdi+8]
0x180009008  cdq
0x180009009  idiv    esi
0x18000900b  test    edx, edx
0x18000900d  jnz     loc_1800091B1
0x180009013  mov     ecx, [rbx+10h]
0x180009016  cmp     ecx, ebp
0x180009018  jnz     short loc_18000903C
0x18000901a  mov     eax, r11d
0x18000901d  cdq
0x18000901e  idiv    esi
0x180009020  test    edx, edx
0x180009022  jnz     loc_1800091B1
0x180009028  mov     eax, r9d
0x18000902b  neg     eax
0x18000902d  cmovs   eax, r9d
0x180009031  cdq
0x180009032  idiv    esi
0x180009034  test    edx, edx
0x180009036  jnz     loc_1800091B1
0x18000903c  mov     r9d, 31313450h
0x180009042  cmp     r8d, r9d
0x180009045  jz      short loc_180009050
0x180009047  cmp     r8d, 3131564Eh
0x18000904e  jnz     short loc_18000905E
0x180009050  mov     eax, r10d
0x180009053  cdq
0x180009054  idiv    esi
0x180009056  test    edx, edx
0x180009058  jnz     loc_1800091B1
0x18000905e  cmp     ecx, r9d
0x180009061  jz      short loc_18000906B
0x180009063  cmp     ecx, 3131564Eh
0x180009069  jnz     short loc_180009079
0x18000906b  mov     eax, r11d
0x18000906e  cdq
0x18000906f  idiv    esi
0x180009071  test    edx, edx
0x180009073  jnz     loc_1800091B1
0x180009079  mov     r14d, 3231564Eh
0x18000907f  mov     ebp, 56555949h
0x180009084  mov     esi, 30323449h
0x180009089  lea     r15d, [r14+0Bh]
0x18000908d  cmp     r8d, 50313459h
0x180009094  jnz     short loc_1800090A7
0x180009096  mov     eax, r10d
0x180009099  mov     r9d, 8
0x18000909f  cdq
0x1800090a0  idiv    r9d
0x1800090a3  test    edx, edx
0x1800090a5  jmp     short loc_1800090FE
0x1800090a7  cmp     r8d, 54313459h
0x1800090ae  jz      short loc_180009096
0x1800090b0  cmp     r8d, 32595559h
0x1800090b7  jz      short loc_1800090FA
0x1800090b9  cmp     r8d, 59565955h
0x1800090c0  jz      short loc_1800090FA
0x1800090c2  cmp     r8d, 55595659h
0x1800090c9  jz      short loc_1800090FA
0x1800090cb  cmp     r8d, 36313256h
0x1800090d2  jz      short loc_1800090FA
0x1800090d4  cmp     r8d, 30313456h
0x1800090db  jz      short loc_1800090FA
0x1800090dd  cmp     r8d, ebp
0x1800090e0  jz      short loc_1800090FA
0x1800090e2  cmp     r8d, esi
0x1800090e5  jz      short loc_1800090FA
0x1800090e7  cmp     r8d, 32323450h
0x1800090ee  jz      short loc_1800090FA
0x1800090f0  cmp     r8d, r14d
0x1800090f3  jz      short loc_1800090FA
0x1800090f5  cmp     r8d, r15d
0x1800090f8  jnz     short loc_180009104
0x1800090fa  test    r10b, 1
0x1800090fe  jnz     loc_1800091B1
0x180009104  cmp     ecx, 32595559h
0x18000910a  jz      short loc_180009146
0x18000910c  cmp     ecx, 59565955h
0x180009112  jz      short loc_180009146
0x180009114  cmp     ecx, 55595659h
0x18000911a  jz      short loc_180009146
0x18000911c  cmp     ecx, 36313256h
0x180009122  jz      short loc_180009146
0x180009124  cmp     ecx, 30313456h
0x18000912a  jz      short loc_180009146
0x18000912c  cmp     ecx, ebp
0x18000912e  jz      short loc_180009146
0x180009130  cmp     ecx, esi
0x180009132  jz      short loc_180009146
0x180009134  cmp     ecx, 32323450h
0x18000913a  jz      short loc_180009146
0x18000913c  cmp     ecx, r14d
0x18000913f  jz      short loc_180009146
0x180009141  cmp     ecx, r15d
0x180009144  jnz     short loc_18000914C
0x180009146  test    r11b, 1
0x18000914a  jnz     short loc_1800091B1
0x18000914c  cmp     r8d, ebp
0x18000914f  jz      short loc_180009156
0x180009151  cmp     r8d, esi
0x180009154  jnz     short loc_180009185
0x180009156  cmp     ecx, 3
0x180009159  jbe     short loc_1800091AD
0x18000915b  cmp     ecx, 32595559h
0x180009161  jz      short loc_1800091AD
0x180009163  cmp     ecx, 59565955h
0x180009169  jz      short loc_1800091AD
0x18000916b  cmp     ecx, 55595659h
0x180009171  jz      short loc_1800091AD
0x180009173  cmp     ecx, 3131564Eh
0x180009179  jz      short loc_1800091AD
0x18000917b  cmp     r8d, ebp
0x18000917e  jz      short loc_18000918F
0x180009180  cmp     r8d, esi
0x180009183  jz      short loc_18000918F
0x180009185  cmp     r8d, r15d
0x180009188  jz      short loc_18000918F
0x18000918a  cmp     r8d, r14d
0x18000918d  jnz     short loc_180009195
0x18000918f  test    byte ptr [rdi+8], 1
0x180009193  jnz     short loc_1800091B1
0x180009195  cmp     ecx, ebp
0x180009197  jz      short loc_1800091A7
0x180009199  cmp     ecx, esi
0x18000919b  jz      short loc_1800091A7
0x18000919d  cmp     ecx, r15d
0x1800091a0  jz      short loc_1800091A7
0x1800091a2  cmp     ecx, r14d
0x1800091a5  jnz     short loc_1800091AD
0x1800091a7  test    byte ptr [rbx+8], 1
0x1800091ab  jnz     short loc_1800091B1
0x1800091ad  xor     eax, eax
0x1800091af  jmp     short loc_1800091B6
0x1800091b1  mov     eax, 6
0x1800091b6  pop     r15
0x1800091b8  pop     r14
0x1800091ba  pop     rdi
0x1800091bb  pop     rsi
0x1800091bc  pop     rbp
0x1800091bd  pop     rbx
0x1800091be  retn
```
