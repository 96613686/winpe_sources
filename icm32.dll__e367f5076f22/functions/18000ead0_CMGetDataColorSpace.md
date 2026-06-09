# CMGetDataColorSpace

- ea: `0x18000ead0`
- end: `0x18000ee12`
- name: `CMGetDataColorSpace`
- size: `834`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e930`
- `0x18001d4f0`

## callees

- `0x18000ead0`

## pseudocode

```c
__int64 __fastcall CMGetDataColorSpace(int a1, _DWORD *a2, _DWORD *a3)
{
  __int64 result; // rax
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx

  if ( a1 == 2 )
  {
    result = 8206;
LABEL_3:
    *a2 = 24;
LABEL_4:
    *a3 = 3;
    return result;
  }
  if ( a1 == 8 )
  {
    *a2 = 32;
    result = 2190;
    *a3 = 3;
    return result;
  }
  if ( a1 <= 513 )
  {
    if ( a1 == 513 )
    {
      result = 8198;
      goto LABEL_3;
    }
    if ( a1 > 16 )
    {
      v12 = a1 - 32;
      if ( !v12 )
      {
        *a2 = 32;
        result = 2077;
        *a3 = 4;
        return result;
      }
      v13 = v12 - 225;
      if ( !v13 )
      {
        *a2 = 16;
        result = 1286;
        goto LABEL_4;
      }
      v14 = v13 - 1;
      if ( !v14 )
      {
        *a2 = 16;
        result = 1285;
        goto LABEL_4;
      }
      v15 = v14 - 1;
      if ( !v15 )
      {
        *a2 = 16;
        result = 1288;
        goto LABEL_4;
      }
      if ( v15 == 1 )
      {
        *a2 = 16;
        result = 1293;
        goto LABEL_4;
      }
    }
    else
    {
      if ( a1 == 16 )
      {
        *a2 = 32;
        result = 8321;
        *a3 = 3;
        return result;
      }
      if ( !a1 )
      {
        *a2 = 16;
        result = 1281;
        goto LABEL_4;
      }
      v5 = a1 - 1;
      if ( !v5 )
      {
        *a2 = 16;
        result = 1537;
        *a3 = 3;
        return result;
      }
      v6 = v5 - 3;
      if ( !v6 )
      {
        result = 8193;
        *a2 = 24;
        *a3 = 3;
        return result;
      }
      v7 = v6 - 5;
      if ( !v7 )
      {
        *a2 = 32;
        result = 2561;
        goto LABEL_4;
      }
      if ( v7 == 1 )
      {
        *a2 = 48;
        result = 16398;
        *a3 = 3;
        return result;
      }
    }
    goto LABEL_64;
  }
  if ( a1 > 772 )
  {
    if ( a1 > 1029 )
    {
      v8 = a1 - 1281;
      if ( !v8 )
      {
        *a2 = 48;
        result = 16390;
        goto LABEL_4;
      }
      v9 = v8 - 1;
      if ( !v9 )
      {
        *a2 = 48;
        result = 16389;
        goto LABEL_4;
      }
      v10 = v9 - 1;
      if ( !v10 )
      {
        *a2 = 48;
        result = 16392;
        goto LABEL_4;
      }
      v11 = v10 - 1;
      if ( !v11 )
      {
        *a2 = 48;
        result = 16397;
        goto LABEL_4;
      }
      if ( v11 == 1 )
      {
        *a2 = 16;
        result = 10;
        *a3 = 1;
        return result;
      }
    }
    else
    {
      if ( a1 == 1029 )
      {
        *a2 = 32;
        result = 10000;
        goto LABEL_4;
      }
      v4 = a1 - 773;
      if ( !v4 )
      {
        *a2 = 32;
        result = 2050;
        *a3 = 4;
        return result;
      }
      v16 = v4 - 252;
      if ( !v16 )
      {
        *a2 = 32;
        result = 2566;
        goto LABEL_4;
      }
      v17 = v16 - 1;
      if ( !v17 )
      {
        *a2 = 32;
        result = 2565;
        goto LABEL_4;
      }
      v18 = v17 - 1;
      if ( !v18 )
      {
        *a2 = 32;
        result = 2568;
        goto LABEL_4;
      }
      if ( v18 == 1 )
      {
        *a2 = 32;
        result = 2573;
        goto LABEL_4;
      }
    }
LABEL_64:
    result = 0;
    *a2 = 0;
    *a3 = 0;
    return result;
  }
  if ( a1 == 772 )
  {
    *a2 = 32;
    result = 2061;
    goto LABEL_4;
  }
  switch ( a1 )
  {
    case 514:
      result = 8197;
      goto LABEL_3;
    case 515:
      result = 8200;
      goto LABEL_3;
    case 516:
      result = 8205;
      goto LABEL_3;
    case 517:
      *a2 = 40;
      result = 8209;
      *a3 = 5;
      break;
    case 518:
      *a2 = 48;
      result = 8210;
      *a3 = 6;
      break;
    case 519:
      *a2 = 56;
      result = 8211;
      *a3 = 7;
      break;
    case 520:
      *a2 = 64;
      result = 8212;
      *a3 = 8;
      break;
    case 521:
      *a2 = 8;
      result = 8202;
      *a3 = 1;
      break;
    default:
      goto LABEL_64;
  }
  return result;
}

```

## disassembly

```asm
0x18000ead0  cmp     ecx, 2
0x18000ead3  jnz     short loc_18000EAE8
0x18000ead5  mov     eax, 200Eh
0x18000eada  mov     dword ptr [rdx], 18h
0x18000eae0  mov     dword ptr [r8], 3
0x18000eae7  retn
0x18000eae8  cmp     ecx, 8
0x18000eaeb  jnz     short loc_18000EB00
0x18000eaed  mov     dword ptr [rdx], 20h ; ' '
0x18000eaf3  mov     eax, 88Eh
0x18000eaf8  mov     dword ptr [r8], 3
0x18000eaff  retn
0x18000eb00  cmp     ecx, 201h
0x18000eb06  jle     short loc_18000EB45
0x18000eb08  cmp     ecx, 304h
0x18000eb0e  jle     loc_18000EBE7
0x18000eb14  cmp     ecx, 405h
0x18000eb1a  jg      loc_18000EBA8
0x18000eb20  jz      loc_18000EDBA
0x18000eb26  sub     ecx, 305h
0x18000eb2c  jnz     loc_18000ED63
0x18000eb32  mov     dword ptr [rdx], 20h ; ' '
0x18000eb38  mov     eax, 802h
0x18000eb3d  mov     dword ptr [r8], 4
0x18000eb44  retn
0x18000eb45  jz      loc_18000ECDF
0x18000eb4b  cmp     ecx, 10h
0x18000eb4e  jg      loc_18000EC26
0x18000eb54  jz      loc_18000EC51
0x18000eb5a  test    ecx, ecx
0x18000eb5c  jz      loc_18000EC74
0x18000eb62  sub     ecx, 1
0x18000eb65  jnz     short loc_18000EB7A
0x18000eb67  mov     dword ptr [rdx], 10h
0x18000eb6d  mov     eax, 601h
0x18000eb72  mov     dword ptr [r8], 3
0x18000eb79  retn
0x18000eb7a  sub     ecx, 3
0x18000eb7d  jz      loc_18000EC3E
0x18000eb83  sub     ecx, 5
0x18000eb86  jz      loc_18000EC64
0x18000eb8c  cmp     ecx, 1
0x18000eb8f  jnz     def_18000EC11; jumptable 000000018000EC11 default case
0x18000eb95  mov     dword ptr [rdx], 30h ; '0'
0x18000eb9b  mov     eax, 400Eh
0x18000eba0  mov     dword ptr [r8], 3
0x18000eba7  retn
0x18000eba8  sub     ecx, 501h
0x18000ebae  jz      loc_18000EE02
0x18000ebb4  sub     ecx, 1
0x18000ebb7  jz      loc_18000EDF2
0x18000ebbd  sub     ecx, 1
0x18000ebc0  jz      loc_18000EDE2
0x18000ebc6  sub     ecx, 1
0x18000ebc9  jz      loc_18000EDD2
0x18000ebcf  cmp     ecx, 1
0x18000ebd2  jnz     def_18000EC11; jumptable 000000018000EC11 default case
0x18000ebd8  mov     dword ptr [rdx], 10h
0x18000ebde  mov     eax, 0Ah
0x18000ebe3  mov     [r8], ecx
0x18000ebe6  retn
0x18000ebe7  jz      loc_18000ED53
0x18000ebed  add     ecx, 0FFFFFDFEh; switch 8 cases
0x18000ebf3  cmp     ecx, 7
0x18000ebf6  ja      def_18000EC11; jumptable 000000018000EC11 default case
0x18000ebfc  movsxd  rax, ecx
0x18000ebff  lea     r9, cs:180000000h
0x18000ec06  mov     ecx, ds:(jpt_18000EC11 - 180000000h)[r9+rax*4]
0x18000ec0e  add     rcx, r9
0x18000ec11  jmp     rcx; switch jump
0x18000ec13  mov     dword ptr [rdx], 8; jumptable 000000018000EC11 case 521
0x18000ec19  mov     eax, 200Ah
0x18000ec1e  mov     dword ptr [r8], 1
0x18000ec25  retn
0x18000ec26  sub     ecx, 20h ; ' '
0x18000ec29  jnz     short loc_18000EC84
0x18000ec2b  mov     dword ptr [rdx], 20h ; ' '
0x18000ec31  mov     eax, 81Dh
0x18000ec36  mov     dword ptr [r8], 4
0x18000ec3d  retn
0x18000ec3e  mov     eax, 2001h
0x18000ec43  mov     dword ptr [rdx], 18h
0x18000ec49  mov     dword ptr [r8], 3
0x18000ec50  retn
0x18000ec51  mov     dword ptr [rdx], 20h ; ' '
0x18000ec57  mov     eax, 2081h
0x18000ec5c  mov     dword ptr [r8], 3
0x18000ec63  retn
0x18000ec64  mov     dword ptr [rdx], 20h ; ' '
0x18000ec6a  mov     eax, 0A01h
0x18000ec6f  jmp     loc_18000EAE0
0x18000ec74  mov     dword ptr [rdx], 10h
0x18000ec7a  mov     eax, 501h
0x18000ec7f  jmp     loc_18000EAE0
0x18000ec84  sub     ecx, 0E1h
0x18000ec8a  jz      short loc_18000ECCF
0x18000ec8c  sub     ecx, 1
0x18000ec8f  jz      short loc_18000ECBF
0x18000ec91  sub     ecx, 1
0x18000ec94  jz      short loc_18000ECAF
0x18000ec96  cmp     ecx, 1
0x18000ec99  jnz     def_18000EC11; jumptable 000000018000EC11 default case
0x18000ec9f  mov     dword ptr [rdx], 10h
0x18000eca5  mov     eax, 50Dh
0x18000ecaa  jmp     loc_18000EAE0
0x18000ecaf  mov     dword ptr [rdx], 10h
0x18000ecb5  mov     eax, 508h
0x18000ecba  jmp     loc_18000EAE0
0x18000ecbf  mov     dword ptr [rdx], 10h
0x18000ecc5  mov     eax, 505h
0x18000ecca  jmp     loc_18000EAE0
0x18000eccf  mov     dword ptr [rdx], 10h
0x18000ecd5  mov     eax, 506h
0x18000ecda  jmp     loc_18000EAE0
0x18000ecdf  mov     eax, 2006h
0x18000ece4  jmp     loc_18000EADA
0x18000ece9  mov     eax, 2005h; jumptable 000000018000EC11 case 514
0x18000ecee  jmp     loc_18000EADA
0x18000ecf3  mov     eax, 2008h; jumptable 000000018000EC11 case 515
0x18000ecf8  jmp     loc_18000EADA
0x18000ecfd  mov     eax, 200Dh; jumptable 000000018000EC11 case 516
0x18000ed02  jmp     loc_18000EADA
0x18000ed07  mov     dword ptr [rdx], 28h ; '('; jumptable 000000018000EC11 case 517
0x18000ed0d  mov     eax, 2011h
0x18000ed12  mov     dword ptr [r8], 5
0x18000ed19  retn
0x18000ed1a  mov     dword ptr [rdx], 30h ; '0'; jumptable 000000018000EC11 case 518
0x18000ed20  mov     eax, 2012h
0x18000ed25  mov     dword ptr [r8], 6
0x18000ed2c  retn
0x18000ed2d  mov     dword ptr [rdx], 38h ; '8'; jumptable 000000018000EC11 case 519
0x18000ed33  mov     eax, 2013h
0x18000ed38  mov     dword ptr [r8], 7
0x18000ed3f  retn
0x18000ed40  mov     dword ptr [rdx], 40h ; '@'; jumptable 000000018000EC11 case 520
0x18000ed46  mov     eax, 2014h
0x18000ed4b  mov     dword ptr [r8], 8
0x18000ed52  retn
0x18000ed53  mov     dword ptr [rdx], 20h ; ' '
0x18000ed59  mov     eax, 80Dh
0x18000ed5e  jmp     loc_18000EAE0
0x18000ed63  sub     ecx, 0FCh
0x18000ed69  jz      short loc_18000EDAA
0x18000ed6b  sub     ecx, 1
0x18000ed6e  jz      short loc_18000ED9A
0x18000ed70  sub     ecx, 1
0x18000ed73  jz      short loc_18000ED8A
0x18000ed75  cmp     ecx, 1
0x18000ed78  jnz     short def_18000EC11; jumptable 000000018000EC11 default case
0x18000ed7a  mov     dword ptr [rdx], 20h ; ' '
0x18000ed80  mov     eax, 0A0Dh
0x18000ed85  jmp     loc_18000EAE0
0x18000ed8a  mov     dword ptr [rdx], 20h ; ' '
0x18000ed90  mov     eax, 0A08h
0x18000ed95  jmp     loc_18000EAE0
0x18000ed9a  mov     dword ptr [rdx], 20h ; ' '
0x18000eda0  mov     eax, 0A05h
0x18000eda5  jmp     loc_18000EAE0
0x18000edaa  mov     dword ptr [rdx], 20h ; ' '
0x18000edb0  mov     eax, 0A06h
0x18000edb5  jmp     loc_18000EAE0
0x18000edba  mov     dword ptr [rdx], 20h ; ' '
0x18000edc0  mov     eax, 2710h
0x18000edc5  jmp     loc_18000EAE0
0x18000edca  xor     eax, eax; jumptable 000000018000EC11 default case
0x18000edcc  mov     [rdx], eax
0x18000edce  mov     [r8], eax
0x18000edd1  retn
0x18000edd2  mov     dword ptr [rdx], 30h ; '0'
0x18000edd8  mov     eax, 400Dh
0x18000eddd  jmp     loc_18000EAE0
0x18000ede2  mov     dword ptr [rdx], 30h ; '0'
0x18000ede8  mov     eax, 4008h
0x18000eded  jmp     loc_18000EAE0
0x18000edf2  mov     dword ptr [rdx], 30h ; '0'
0x18000edf8  mov     eax, 4005h
0x18000edfd  jmp     loc_18000EAE0
0x18000ee02  mov     dword ptr [rdx], 30h ; '0'
0x18000ee08  mov     eax, 4006h
0x18000ee0d  jmp     loc_18000EAE0
```
