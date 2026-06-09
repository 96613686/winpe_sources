# GetCompressionAndBitCount

- ea: `0x180005024`
- end: `0x1800051f3`
- name: `GetCompressionAndBitCount`
- size: `463`
- prototype: `__int64 __fastcall(unsigned int, int *, _DWORD *, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004e18`

## callees

- `0x180005024`

## pseudocode

```c
__int64 __fastcall GetCompressionAndBitCount(unsigned int a1, int *a2, _DWORD *a3, _DWORD *a4, _DWORD *a5)
{
  __int64 result; // rax
  int v7; // edx
  bool v8; // zf

  result = 844715353;
  *a5 = 0;
  if ( a1 <= 0x32595559 )
  {
    if ( a1 == 844715353 )
      goto LABEL_49;
    result = 808596553;
    if ( a1 > 0x30323449 )
    {
      v7 = 825307737;
      result = a1 - 825307737;
      if ( a1 == 825307737 )
      {
        *a3 = 8;
        goto LABEL_6;
      }
      result = a1 - 825308249;
      if ( a1 == 825308249 )
        goto LABEL_49;
      result = a1 - 825316942;
      if ( a1 != 825316942 )
      {
        result = a1 - 826494281;
        if ( a1 == 826494281 )
          goto LABEL_49;
        result = a1 - 842094158;
        if ( a1 != 842094158 )
        {
          result = a1 - 842094169;
          if ( a1 != 842094169 && a1 != 843271497 )
            goto LABEL_46;
        }
      }
    }
    else if ( a1 != 808596553 )
    {
      result = a1 - 20;
      if ( a1 == 20 )
        goto LABEL_23;
      result = a1 - 22;
      if ( a1 == 22 )
        goto LABEL_47;
      result = a1 - 23;
      if ( a1 == 23 )
        goto LABEL_48;
      result = a1 - 24;
      if ( a1 == 24 )
        goto LABEL_22;
      result = a1 - 41;
      if ( a1 == 41 )
        goto LABEL_4;
      result = a1 - 808530550;
      if ( a1 == 808530550 )
      {
LABEL_49:
        *a3 = 16;
        goto LABEL_21;
      }
      v8 = (_DWORD)result == 480;
      goto LABEL_38;
    }
LABEL_20:
    *a3 = 12;
LABEL_21:
    v7 = a1;
    goto LABEL_6;
  }
  result = 1448433993;
  if ( a1 <= 0x56555949 )
  {
    if ( a1 != 1448433993 )
    {
      if ( a1 == 860048713 )
        goto LABEL_49;
      if ( a1 != 876825929 )
      {
        if ( a1 == 909193814 )
        {
LABEL_39:
          *a3 = 32;
          goto LABEL_21;
        }
        v7 = 961893977;
        if ( a1 == 961893977 )
        {
          *a3 = 9;
          goto LABEL_6;
        }
        if ( a1 != 1345401945 )
        {
          if ( a1 == 1431918169 )
            goto LABEL_49;
          v8 = a1 == 1448433985;
LABEL_38:
          if ( !v8 )
          {
LABEL_46:
            *a3 = 0;
            goto LABEL_21;
          }
          goto LABEL_39;
        }
      }
    }
    goto LABEL_20;
  }
  if ( a1 != -466162822 )
  {
    if ( a1 != 1498831189 )
    {
      if ( a1 != -466162821 )
      {
        if ( a1 != -466162820 )
        {
          if ( a1 != -466162819 )
          {
            if ( a1 != -466162818 )
              goto LABEL_46;
LABEL_47:
            *a3 = 32;
            goto LABEL_5;
          }
LABEL_23:
          *a3 = 24;
          goto LABEL_5;
        }
LABEL_22:
        *a3 = 16;
        goto LABEL_5;
      }
LABEL_48:
      *a3 = 16;
      v7 = 3;
      *a5 = 1;
      goto LABEL_6;
    }
    goto LABEL_49;
  }
LABEL_4:
  *a3 = 8;
LABEL_5:
  *a5 = 1;
  v7 = 0;
LABEL_6:
  *a4 = 1;
  *a2 = v7;
  return result;
}

```

## disassembly

```asm
0x180005024  mov     r10, [rsp+arg_20]
0x180005029  mov     eax, 32595559h
0x18000502e  mov     r11, rdx
0x180005031  mov     dword ptr [r10], 0
0x180005038  cmp     ecx, eax
0x18000503a  jbe     short loc_180005070
0x18000503c  mov     eax, 56555949h
0x180005041  cmp     ecx, eax
0x180005043  jbe     loc_180005128
0x180005049  cmp     ecx, 0E436EB7Ah
0x18000504f  jnz     loc_180005187
0x180005055  mov     dword ptr [r8], 8
0x18000505c  mov     dword ptr [r10], 1
0x180005063  xor     edx, edx
0x180005065  mov     dword ptr [r9], 1
0x18000506c  mov     [r11], edx
0x18000506f  retn
0x180005070  jz      loc_1800051E7
0x180005076  mov     eax, 30323449h
0x18000507b  cmp     ecx, eax
0x18000507d  ja      short loc_1800050B9
0x18000507f  jz      short loc_1800050D6
0x180005081  mov     eax, ecx
0x180005083  sub     eax, 14h
0x180005086  jz      short loc_1800050ED
0x180005088  sub     eax, 2
0x18000508b  jz      loc_1800051C3
0x180005091  sub     eax, 1
0x180005094  jz      loc_1800051CF
0x18000509a  sub     eax, 1
0x18000509d  jz      short loc_1800050E1
0x18000509f  sub     eax, 11h
0x1800050a2  jz      short loc_180005055
0x1800050a4  sub     eax, 3031324Dh
0x1800050a9  jz      loc_1800051E7
0x1800050af  cmp     eax, 1E0h
0x1800050b4  jmp     loc_18000516D
0x1800050b9  mov     eax, ecx
0x1800050bb  mov     edx, 31313259h
0x1800050c0  sub     eax, edx
0x1800050c2  jz      short loc_18000511C
0x1800050c4  sub     eax, 200h
0x1800050c9  jz      loc_1800051E7
0x1800050cf  sub     eax, 21F5h
0x1800050d4  jnz     short loc_1800050F9
0x1800050d6  mov     dword ptr [r8], 0Ch
0x1800050dd  mov     edx, ecx
0x1800050df  jmp     short loc_180005065
0x1800050e1  mov     dword ptr [r8], 10h
0x1800050e8  jmp     loc_18000505C
0x1800050ed  mov     dword ptr [r8], 18h
0x1800050f4  jmp     loc_18000505C
0x1800050f9  sub     eax, 11F6FBh
0x1800050fe  jz      loc_1800051E7
0x180005104  sub     eax, 0EE0905h
0x180005109  jz      short loc_1800050D6
0x18000510b  sub     eax, 0Bh
0x18000510e  jz      short loc_1800050D6
0x180005110  cmp     eax, 11F6F0h
0x180005115  jz      short loc_1800050D6
0x180005117  jmp     loc_1800051B7
0x18000511c  mov     dword ptr [r8], 8
0x180005123  jmp     loc_180005065
0x180005128  jz      short loc_1800050D6
0x18000512a  cmp     ecx, 33434D49h
0x180005130  jz      loc_1800051E7
0x180005136  cmp     ecx, 34434D49h
0x18000513c  jz      short loc_1800050D6
0x18000513e  cmp     ecx, 36313256h
0x180005144  jz      short loc_18000516F
0x180005146  mov     edx, 39555659h
0x18000514b  cmp     ecx, edx
0x18000514d  jz      short loc_18000517B
0x18000514f  cmp     ecx, 50313459h
0x180005155  jz      loc_1800050D6
0x18000515b  cmp     ecx, 55595659h
0x180005161  jz      loc_1800051E7
0x180005167  cmp     ecx, 56555941h
0x18000516d  jnz     short loc_1800051B7
0x18000516f  mov     dword ptr [r8], 20h ; ' '
0x180005176  jmp     loc_1800050DD
0x18000517b  mov     dword ptr [r8], 9
0x180005182  jmp     loc_180005065
0x180005187  cmp     ecx, 59565955h
0x18000518d  jz      short loc_1800051E7
0x18000518f  cmp     ecx, 0E436EB7Bh
0x180005195  jz      short loc_1800051CF
0x180005197  cmp     ecx, 0E436EB7Ch
0x18000519d  jz      loc_1800050E1
0x1800051a3  cmp     ecx, 0E436EB7Dh
0x1800051a9  jz      loc_1800050ED
0x1800051af  cmp     ecx, 0E436EB7Eh
0x1800051b5  jz      short loc_1800051C3
0x1800051b7  mov     dword ptr [r8], 0
0x1800051be  jmp     loc_1800050DD
0x1800051c3  mov     dword ptr [r8], 20h ; ' '
0x1800051ca  jmp     loc_18000505C
0x1800051cf  mov     dword ptr [r8], 10h
0x1800051d6  mov     edx, 3
0x1800051db  mov     dword ptr [r10], 1
0x1800051e2  jmp     loc_180005065
0x1800051e7  mov     dword ptr [r8], 10h
0x1800051ee  jmp     loc_1800050DD
```
