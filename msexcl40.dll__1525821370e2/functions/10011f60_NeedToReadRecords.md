# NeedToReadRecords

- ea: `0x10011f60`
- end: `0x1001225b`
- name: `NeedToReadRecords`
- size: `763`
- prototype: `int __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x10012270`

## callees

- `0x10011f60`
- `0x10035f40`

## pseudocode

```c
_DWORD *__fastcall NeedToReadRecords(int a1, _BYTE *a2, int a3, _DWORD *a4)
{
  _DWORD *result; // eax
  bool v7; // zf

  if ( a4[1] )
    return memset(a2, 1, 0x100u);
  memset(a2, 0, 0x100u);
  a2[9] = 1;
  if ( *(int *)(a1 + 4) >= 5 )
  {
    if ( a4[6] )
      a2[133] = 1;
    result = a4 + 4;
    goto LABEL_9;
  }
  result = a4 + 4;
  if ( a4[4] )
  {
    a2[133] = 1;
LABEL_9:
    if ( *result )
      a2[143] = 1;
  }
  if ( a4[5] )
    a2[163] = 1;
  v7 = a4[7] == 0;
  a2[47] = 1;
  if ( !v7 )
    a2[96] = 1;
  if ( a4[8] )
    a2[135] = 1;
  if ( a4[16] )
  {
    a2[134] = 1;
    a2[91] = 1;
    *((_WORD *)a2 + 9) = 257;
    a2[25] = 1;
    a2[99] = 1;
    a2[165] = 1;
  }
  if ( a4[19] )
    a2[85] = 1;
  if ( a4[17] )
    a2[125] = 1;
  if ( a4[18] )
    a2[153] = 1;
  if ( a4[21] )
  {
    a2[171] = 1;
    a2[154] = 1;
  }
  if ( a4[20] )
    a2[37] = 1;
  if ( a4[22] )
    a2[49] = 1;
  if ( a4[23] )
    a2[30] = 1;
  if ( a4[24] )
  {
    a2[67] = 1;
    a2[224] = 1;
  }
  if ( a4[9] )
    a2[97] = 1;
  if ( a4[10] )
    a2[193] = 1;
  if ( a4[11] )
    a2[195] = 1;
  if ( a4[12] )
    a2[194] = 1;
  if ( a4[13] )
    a2[166] = 1;
  if ( a4[14] )
    a2[34] = 1;
  if ( a4[15] )
    a2[66] = 1;
  if ( a4[25] )
    a2[92] = 1;
  if ( a4[26] )
    a2[184] = 1;
  if ( a4[27] )
    a2[185] = 1;
  if ( a4[28] )
    a2[15] = 1;
  if ( a4[29] )
    a2[156] = 1;
  if ( a4[30] )
    a2[154] = 1;
  if ( a4[31] )
    a2[22] = 1;
  if ( a4[32] )
    a2[23] = 1;
  if ( a4[33] )
    a2[35] = 1;
  if ( a4[34] )
    a2[24] = 1;
  if ( a4[35] )
    *a2 = 1;
  if ( a4[37] )
  {
    a2[126] = 1;
    a2[189] = 1;
    a2[3] = 1;
  }
  if ( a4[38] )
  {
    a2[1] = 1;
    a2[190] = 1;
  }
  if ( a4[36] )
  {
    a2[4] = 1;
    a2[214] = 1;
    a2[253] = 1;
  }
  if ( a4[40] || a4[39] )
    a2[5] = 1;
  if ( a4[41] )
    a2[6] = 1;
  if ( a4[42] )
    a2[33] = 1;
  if ( a4[43] )
    a2[1212] = 1;
  if ( a4[44] )
    a2[7] = 1;
  if ( a4[45] )
  {
    a2[28] = 1;
    a2[52] = 1;
  }
  if ( a4[46] )
    a2[93] = 1;
  if ( a4[47] )
    a2[127] = 1;
  if ( a4[48] )
    a2[175] = 1;
  if ( a4[49] )
    a2[252] = 1;
  if ( a4[50] )
    a2[10] = 1;
  if ( a4[51] )
    a2[140] = 1;
  return result;
}

```

## disassembly

```asm
0x10011f60  mov     edi, edi
0x10011f62  push    ebp
0x10011f63  mov     ebp, esp
0x10011f65  push    ebx
0x10011f66  push    esi
0x10011f67  push    edi
0x10011f68  mov     edi, [ebp+arg_4]
0x10011f6b  mov     esi, edx
0x10011f6d  mov     ebx, ecx
0x10011f6f  push    100h; Size
0x10011f74  cmp     dword ptr [edi+4], 0
0x10011f78  jz      short loc_10011F8C
0x10011f7a  push    1; Val
0x10011f7c  push    esi; void *
0x10011f7d  call    _memset
0x10011f82  add     esp, 0Ch
0x10011f85  pop     edi
0x10011f86  pop     esi
0x10011f87  pop     ebx
0x10011f88  pop     ebp
0x10011f89  retn    8
0x10011f8c  push    0; Val
0x10011f8e  push    esi; void *
0x10011f8f  call    _memset
0x10011f94  add     esp, 0Ch
0x10011f97  mov     byte ptr [esi+9], 1
0x10011f9b  cmp     dword ptr [ebx+4], 5
0x10011f9f  jl      short loc_10011FB3
0x10011fa1  cmp     dword ptr [edi+18h], 0
0x10011fa5  jz      short loc_10011FAE
0x10011fa7  mov     byte ptr [esi+85h], 1
0x10011fae  lea     eax, [edi+10h]
0x10011fb1  jmp     short loc_10011FC3
0x10011fb3  cmp     dword ptr [edi+10h], 0
0x10011fb7  lea     eax, [edi+10h]
0x10011fba  jz      short loc_10011FCF
0x10011fbc  mov     byte ptr [esi+85h], 1
0x10011fc3  cmp     dword ptr [eax], 0
0x10011fc6  jz      short loc_10011FCF
0x10011fc8  mov     byte ptr [esi+8Fh], 1
0x10011fcf  cmp     dword ptr [edi+14h], 0
0x10011fd3  jz      short loc_10011FDC
0x10011fd5  mov     byte ptr [esi+0A3h], 1
0x10011fdc  cmp     dword ptr [edi+1Ch], 0
0x10011fe0  mov     byte ptr [esi+2Fh], 1
0x10011fe4  jz      short loc_10011FEA
0x10011fe6  mov     byte ptr [esi+60h], 1
0x10011fea  cmp     dword ptr [edi+20h], 0
0x10011fee  jz      short loc_10011FF7
0x10011ff0  mov     byte ptr [esi+87h], 1
0x10011ff7  cmp     dword ptr [edi+40h], 0
0x10011ffb  jz      short loc_1001201D
0x10011ffd  mov     byte ptr [esi+86h], 1
0x10012004  mov     byte ptr [esi+5Bh], 1
0x10012008  mov     word ptr [esi+12h], 101h
0x1001200e  mov     byte ptr [esi+19h], 1
0x10012012  mov     byte ptr [esi+63h], 1
0x10012016  mov     byte ptr [esi+0A5h], 1
0x1001201d  cmp     dword ptr [edi+4Ch], 0
0x10012021  jz      short loc_10012027
0x10012023  mov     byte ptr [esi+55h], 1
0x10012027  cmp     dword ptr [edi+44h], 0
0x1001202b  jz      short loc_10012031
0x1001202d  mov     byte ptr [esi+7Dh], 1
0x10012031  cmp     dword ptr [edi+48h], 0
0x10012035  jz      short loc_1001203E
0x10012037  mov     byte ptr [esi+99h], 1
0x1001203e  cmp     dword ptr [edi+54h], 0
0x10012042  jz      short loc_10012052
0x10012044  mov     byte ptr [esi+0ABh], 1
0x1001204b  mov     byte ptr [esi+9Ah], 1
0x10012052  cmp     dword ptr [edi+50h], 0
0x10012056  jz      short loc_1001205C
0x10012058  mov     byte ptr [esi+25h], 1
0x1001205c  cmp     dword ptr [edi+58h], 0
0x10012060  jz      short loc_10012066
0x10012062  mov     byte ptr [esi+31h], 1
0x10012066  cmp     dword ptr [edi+5Ch], 0
0x1001206a  jz      short loc_10012070
0x1001206c  mov     byte ptr [esi+1Eh], 1
0x10012070  cmp     dword ptr [edi+60h], 0
0x10012074  jz      short loc_10012081
0x10012076  mov     byte ptr [esi+43h], 1
0x1001207a  mov     byte ptr [esi+0E0h], 1
0x10012081  cmp     dword ptr [edi+24h], 0
0x10012085  jz      short loc_1001208B
0x10012087  mov     byte ptr [esi+61h], 1
0x1001208b  cmp     dword ptr [edi+28h], 0
0x1001208f  jz      short loc_10012098
0x10012091  mov     byte ptr [esi+0C1h], 1
0x10012098  cmp     dword ptr [edi+2Ch], 0
0x1001209c  jz      short loc_100120A5
0x1001209e  mov     byte ptr [esi+0C3h], 1
0x100120a5  cmp     dword ptr [edi+30h], 0
0x100120a9  jz      short loc_100120B2
0x100120ab  mov     byte ptr [esi+0C2h], 1
0x100120b2  cmp     dword ptr [edi+34h], 0
0x100120b6  jz      short loc_100120BF
0x100120b8  mov     byte ptr [esi+0A6h], 1
0x100120bf  cmp     dword ptr [edi+38h], 0
0x100120c3  jz      short loc_100120C9
0x100120c5  mov     byte ptr [esi+22h], 1
0x100120c9  cmp     dword ptr [edi+3Ch], 0
0x100120cd  jz      short loc_100120D3
0x100120cf  mov     byte ptr [esi+42h], 1
0x100120d3  cmp     dword ptr [edi+64h], 0
0x100120d7  jz      short loc_100120DD
0x100120d9  mov     byte ptr [esi+5Ch], 1
0x100120dd  cmp     dword ptr [edi+68h], 0
0x100120e1  jz      short loc_100120EA
0x100120e3  mov     byte ptr [esi+0B8h], 1
0x100120ea  cmp     dword ptr [edi+6Ch], 0
0x100120ee  jz      short loc_100120F7
0x100120f0  mov     byte ptr [esi+0B9h], 1
0x100120f7  cmp     dword ptr [edi+70h], 0
0x100120fb  jz      short loc_10012101
0x100120fd  mov     byte ptr [esi+0Fh], 1
0x10012101  cmp     dword ptr [edi+74h], 0
0x10012105  jz      short loc_1001210E
0x10012107  mov     byte ptr [esi+9Ch], 1
0x1001210e  cmp     dword ptr [edi+78h], 0
0x10012112  jz      short loc_1001211B
0x10012114  mov     byte ptr [esi+9Ah], 1
0x1001211b  cmp     dword ptr [edi+7Ch], 0
0x1001211f  jz      short loc_10012125
0x10012121  mov     byte ptr [esi+16h], 1
0x10012125  cmp     dword ptr [edi+80h], 0
0x1001212c  jz      short loc_10012132
0x1001212e  mov     byte ptr [esi+17h], 1
0x10012132  cmp     dword ptr [edi+84h], 0
0x10012139  jz      short loc_1001213F
0x1001213b  mov     byte ptr [esi+23h], 1
0x1001213f  cmp     dword ptr [edi+88h], 0
0x10012146  jz      short loc_1001214C
0x10012148  mov     byte ptr [esi+18h], 1
0x1001214c  cmp     dword ptr [edi+8Ch], 0
0x10012153  jz      short loc_10012158
0x10012155  mov     byte ptr [esi], 1
0x10012158  cmp     dword ptr [edi+94h], 0
0x1001215f  jz      short loc_10012170
0x10012161  mov     byte ptr [esi+7Eh], 1
0x10012165  mov     byte ptr [esi+0BDh], 1
0x1001216c  mov     byte ptr [esi+3], 1
0x10012170  cmp     dword ptr [edi+98h], 0
0x10012177  jz      short loc_10012184
0x10012179  mov     byte ptr [esi+1], 1
0x1001217d  mov     byte ptr [esi+0BEh], 1
0x10012184  cmp     dword ptr [edi+90h], 0
0x1001218b  jz      short loc_1001219F
0x1001218d  mov     byte ptr [esi+4], 1
0x10012191  mov     byte ptr [esi+0D6h], 1
0x10012198  mov     byte ptr [esi+0FDh], 1
0x1001219f  cmp     dword ptr [edi+0A0h], 0
0x100121a6  jnz     short loc_100121B1
0x100121a8  cmp     dword ptr [edi+9Ch], 0
0x100121af  jz      short loc_100121B5
0x100121b1  mov     byte ptr [esi+5], 1
0x100121b5  cmp     dword ptr [edi+0A4h], 0
0x100121bc  jz      short loc_100121C2
0x100121be  mov     byte ptr [esi+6], 1
0x100121c2  cmp     dword ptr [edi+0A8h], 0
0x100121c9  jz      short loc_100121CF
0x100121cb  mov     byte ptr [esi+21h], 1
0x100121cf  cmp     dword ptr [edi+0ACh], 0
0x100121d6  jz      short loc_100121DF
0x100121d8  mov     byte ptr [esi+4BCh], 1
0x100121df  cmp     dword ptr [edi+0B0h], 0
0x100121e6  jz      short loc_100121EC
0x100121e8  mov     byte ptr [esi+7], 1
0x100121ec  cmp     dword ptr [edi+0B4h], 0
0x100121f3  jz      short loc_100121FD
0x100121f5  mov     byte ptr [esi+1Ch], 1
0x100121f9  mov     byte ptr [esi+34h], 1
0x100121fd  cmp     dword ptr [edi+0B8h], 0
0x10012204  jz      short loc_1001220A
0x10012206  mov     byte ptr [esi+5Dh], 1
0x1001220a  cmp     dword ptr [edi+0BCh], 0
0x10012211  jz      short loc_10012217
0x10012213  mov     byte ptr [esi+7Fh], 1
0x10012217  cmp     dword ptr [edi+0C0h], 0
0x1001221e  jz      short loc_10012227
0x10012220  mov     byte ptr [esi+0AFh], 1
0x10012227  cmp     dword ptr [edi+0C4h], 0
0x1001222e  jz      short loc_10012237
0x10012230  mov     byte ptr [esi+0FCh], 1
0x10012237  cmp     dword ptr [edi+0C8h], 0
0x1001223e  jz      short loc_10012244
0x10012240  mov     byte ptr [esi+0Ah], 1
0x10012244  cmp     dword ptr [edi+0CCh], 0
0x1001224b  jz      short loc_10012254
0x1001224d  mov     byte ptr [esi+8Ch], 1
0x10012254  pop     edi
0x10012255  pop     esi
0x10012256  pop     ebx
0x10012257  pop     ebp
0x10012258  retn    8
```
