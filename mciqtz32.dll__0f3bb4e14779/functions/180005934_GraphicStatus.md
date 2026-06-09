# GraphicStatus

- ea: `0x180005934`
- end: `0x180006080`
- name: `GraphicStatus`
- size: `1868`
- prototype: `__int64 __fastcall(struct _MCIGRAPHIC *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000485c`

## callees

- `0x180001d48`
- `0x180001e7c`
- `0x180001ef4`
- `0x180002254`
- `0x18000238c`
- `0x180003b5c`
- `0x1800043d0`
- `0x180005934`
- `0x180007010`

## import_xrefs

- `KERNEL32!MulDiv` at `0x180005c49`
- `KERNEL32!MulDiv` at `0x180005c49`
- `USER32!IsIconic` at `0x180005e0f`
- `USER32!IsIconic` at `0x180005e0f`
- `USER32!IsZoomed` at `0x180005e23`
- `USER32!IsZoomed` at `0x180005e23`
- `USER32!IsWindowVisible` at `0x180005de6`
- `USER32!IsWindowVisible` at `0x180005de6`

## pseudocode

```c
__int64 __fastcall GraphicStatus(struct _MCIGRAPHIC *a1, int a2, _DWORD *a3)
{
  int *v6; // r14
  unsigned int v7; // edi
  int v8; // edx
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  unsigned int v18; // ebx
  unsigned int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int Palette; // eax
  unsigned __int64 v26; // rcx
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  __int64 v33; // rbx
  double v34; // xmm1_8
  int Speed; // eax
  unsigned __int64 v36; // rax
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  BOOL v42; // eax
  int v43; // eax
  unsigned __int64 v44; // r8
  int v45; // eax
  HWND v46; // rcx
  BOOL v47; // eax
  bool v48; // zf
  HWND v49; // rcx
  HWND v50; // rcx
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  unsigned int v54; // eax
  unsigned int v55; // eax
  unsigned int v56; // eax
  __int64 v57; // rcx
  __int64 v58; // rcx
  int v59; // [rsp+40h] [rbp-10h] BYREF
  int v60; // [rsp+44h] [rbp-Ch] BYREF
  int v61; // [rsp+48h] [rbp-8h] BYREF
  int v62; // [rsp+4Ch] [rbp-4h] BYREF
  unsigned int v63; // [rsp+88h] [rbp+38h] BYREF
  unsigned __int64 v64; // [rsp+98h] [rbp+48h] BYREF

  if ( (a2 & 0x200000) != 0 )
    return 274;
  v6 = a3 + 2;
  v7 = 0;
  if ( (a2 & 0x100) == 0 )
  {
    if ( (a2 & 0x40000) != 0 )
      *(_QWORD *)v6 = 0;
    else
      v7 = 273;
    goto LABEL_156;
  }
  *(_QWORD *)v6 = 0;
  if ( (a2 & 0x10) != 0 && (unsigned int)(a3[4] - 1) > 1 )
    return 284;
  v8 = a2 & 0x200;
  if ( v8 )
  {
    if ( a3[4] != 2 )
      return 284;
  }
  if ( (a2 & 0x40000) != 0 )
    return 284;
  v9 = a3[4];
  if ( v9 > 0x4019 )
  {
    if ( v9 > 0x4100 )
    {
      v51 = v9 - 16641;
      if ( v51 )
      {
        v52 = v51 - 1;
        if ( v52 )
        {
          v53 = v52 - 1;
          if ( !v53 )
          {
            v20 = *((int *)a1 + 21);
            goto LABEL_152;
          }
          v54 = v53 - 1;
          if ( v54 )
          {
            v55 = v54 - 1;
            if ( !v55 )
              goto LABEL_49;
            v56 = v55 - 16124;
            if ( !v56 )
            {
              if ( *((_QWORD *)a1 + 41) )
              {
                (*(void (__fastcall **)(_QWORD, _DWORD *))(**((_QWORD **)a1 + 41) + 24LL))(*((_QWORD *)a1 + 41), a3 + 2);
              }
              else if ( !*((_QWORD *)a1 + 42) )
              {
                goto LABEL_49;
              }
              v57 = *((_QWORD *)a1 + 42);
              if ( v57 )
              {
                v62 = 0;
                v61 = 0;
                v60 = 0;
                v59 = 0;
                v63 = 0;
                LODWORD(v64) = 0;
                (*(void (__fastcall **)(__int64, int *, int *, int *, int *, unsigned int *, unsigned __int64 *))(*(_QWORD *)v57 + 104LL))(
                  v57,
                  &v62,
                  &v61,
                  &v60,
                  &v59,
                  &v63,
                  &v64);
                *(_QWORD *)v6 += v59 + v63 + (unsigned int)v64;
              }
              goto LABEL_156;
            }
            v32 = v56 - 1;
            if ( !v32 )
            {
              *(_QWORD *)v6 = 100;
              goto LABEL_156;
            }
            goto LABEL_136;
          }
          if ( !*((_QWORD *)a1 + 67) )
            goto LABEL_49;
          v20 = *((unsigned int *)a1 + 141);
        }
        else
        {
          v58 = *((_QWORD *)a1 + 42);
          if ( !v58 )
            goto LABEL_49;
          v63 = 0;
          (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v58 + 152LL))(v58, &v63);
          v20 = v63;
        }
      }
      else
      {
        if ( !*((_QWORD *)a1 + 42) )
          goto LABEL_49;
        v20 = *((int *)a1 + 94);
      }
    }
    else
    {
      if ( v9 != 16640 )
      {
        switch ( v9 )
        {
          case 0x4021u:
            v46 = (HWND)*((_QWORD *)a1 + 37);
            if ( !v46 )
              goto LABEL_113;
            v47 = IsWindowVisible(v46);
            goto LABEL_112;
          case 0x4022u:
            v49 = (HWND)*((_QWORD *)a1 + 37);
            if ( !v49 )
              goto LABEL_113;
            v47 = IsIconic(v49);
            goto LABEL_112;
          case 0x4023u:
            v50 = (HWND)*((_QWORD *)a1 + 37);
            if ( !v50 )
              goto LABEL_113;
            v47 = IsZoomed(v50);
LABEL_112:
            v48 = !v47;
            v16 = 34865153;
            if ( v48 )
LABEL_113:
              v16 = 34799616;
            goto LABEL_25;
          case 0x4026u:
            if ( *((_DWORD *)a1 + 72) != 529 )
            {
              v7 = 302;
              goto LABEL_156;
            }
            *(_QWORD *)v6 = 34472462;
            break;
          case 0x4027u:
            if ( !*((_QWORD *)a1 + 67) )
              goto LABEL_49;
            v20 = *((unsigned int *)a1 + 137);
            goto LABEL_152;
          case 0x4028u:
            if ( !*((_QWORD *)a1 + 67) )
              goto LABEL_49;
            v20 = *((unsigned int *)a1 + 138);
            goto LABEL_152;
          case 0x4029u:
            if ( !*((_QWORD *)a1 + 67) )
              goto LABEL_49;
            v20 = *((unsigned __int16 *)a1 + 278);
            goto LABEL_152;
          case 0x402Au:
            if ( !*((_QWORD *)a1 + 67) )
              goto LABEL_49;
            v20 = *((unsigned __int16 *)a1 + 279);
            goto LABEL_152;
          case 0x402Cu:
            goto LABEL_28;
          case 0x402Du:
            v20 = *((int *)a1 + 25);
            goto LABEL_152;
          case 0x402Eu:
            v20 = *((int *)a1 + 26);
            goto LABEL_152;
          default:
            goto LABEL_49;
        }
        goto LABEL_26;
      }
      v20 = *((int *)a1 + 22);
    }
LABEL_152:
    *(_QWORD *)v6 = v20;
    goto LABEL_156;
  }
  if ( v9 == 16409 )
  {
    ActuallyGetVolume(a1);
    v43 = a2 & 0x180000;
    if ( (a2 & 0x180000) != 0 )
    {
      if ( v43 == 0x80000 )
      {
        v45 = *((_DWORD *)a1 + 56);
      }
      else
      {
        if ( v43 != 0x100000 )
        {
          v7 = CheckResult(-2147467259);
LABEL_103:
          *(_QWORD *)v6 = v44;
          goto LABEL_156;
        }
        v45 = *((_DWORD *)a1 + 59);
      }
    }
    else
    {
      v45 = (*((_DWORD *)a1 + 56) + *((_DWORD *)a1 + 59)) / 2;
    }
    v44 = (unsigned __int64)(1000 * (v45 + 1LL)) >> 16;
    goto LABEL_103;
  }
  if ( v9 > 0x4008 )
  {
    if ( v9 > 0x4012 )
    {
      v37 = v9 - 16403;
      if ( !v37 )
        goto LABEL_49;
      v38 = v37 - 1;
      if ( v38 )
      {
        v39 = v38 - 1;
        if ( !v39 )
          goto LABEL_49;
        v40 = v39 - 1;
        if ( !v40 )
          goto LABEL_49;
        v41 = v40 - 1;
        if ( !v41 )
        {
          v17 = 34799616;
          goto LABEL_30;
        }
        if ( v41 != 1 )
          goto LABEL_49;
        *(_QWORD *)v6 = (unsigned __int16)-(*((_DWORD *)a1 + 62) != 0) + 2147483649LL;
LABEL_94:
        v7 = 1114112;
        goto LABEL_156;
      }
      v42 = 0;
      if ( (a2 & 0x80000) == 0 && *((_QWORD *)a1 + 23) && !*((_DWORD *)a1 + 58) )
        v42 = *((_DWORD *)a1 + 59) != 0;
      if ( (a2 & 0x100000) == 0 && *((_QWORD *)a1 + 23) && !*((_DWORD *)a1 + 55) && *((_DWORD *)a1 + 56) )
        v42 = 1;
      v36 = (-(__int64)v42 & 0xFFFFFFFFFFFF0001uLL) + 2147549184u;
    }
    else
    {
      if ( v9 == 16402 )
        goto LABEL_49;
      v27 = v9 - 16393;
      if ( !v27 )
        goto LABEL_49;
      v28 = v27 - 1;
      if ( !v28 )
        goto LABEL_49;
      v29 = v28 - 1;
      if ( v29 )
      {
        v30 = v29 - 1;
        if ( !v30 )
          goto LABEL_49;
        v31 = v30 - 2;
        if ( !v31 )
        {
          if ( *((_QWORD *)a1 + 42) )
          {
            v33 = *((_QWORD *)a1 + 45) / 10LL;
            if ( (a2 & 0x20000) == 0 )
              v33 = 1000 * v33 / DeviceGetSpeed(a1);
            if ( v33 )
              v20 = 1000000000 / v33;
            else
              v20 = 1000;
            goto LABEL_152;
          }
          v34 = *((double *)a1 + 73);
          if ( v34 == 0.0 )
            goto LABEL_49;
          *(_QWORD *)v6 = (int)(1000.0 / v34);
          if ( (a2 & 0x20000) != 0 )
            goto LABEL_156;
          Speed = DeviceGetSpeed(a1);
          v26 = MulDiv(*v6, 1000, Speed);
          goto LABEL_51;
        }
        v32 = v31 - 1;
        if ( !v32 )
          goto LABEL_49;
LABEL_136:
        if ( v32 == 1 )
          goto LABEL_156;
        goto LABEL_49;
      }
      v36 = 2147631105LL;
    }
    *(_QWORD *)v6 = v36;
    goto LABEL_94;
  }
  if ( v9 == 16392 )
    goto LABEL_49;
  if ( v9 > 8 )
  {
    v22 = v9 - 0x4000;
    if ( !v22 )
      goto LABEL_49;
    v23 = v22 - 1;
    if ( !v23 )
    {
      *(_QWORD *)v6 = *((_QWORD *)a1 + 37);
      v7 = *((_QWORD *)a1 + 37) == 0 ? 0x112 : 0;
      goto LABEL_156;
    }
    v24 = v23 - 2;
    if ( !v24 )
    {
      if ( *((_DWORD *)a1 + 53) )
      {
        v20 = 0;
        goto LABEL_152;
      }
      LODWORD(v20) = DeviceGetSpeed(a1);
      goto LABEL_43;
    }
    if ( v24 != 1 )
      goto LABEL_49;
    v64 = 0;
    Palette = DeviceGetPalette(a1, &v64);
    v26 = v64;
    v7 = Palette;
LABEL_51:
    *(_QWORD *)v6 = v26;
    goto LABEL_156;
  }
  if ( v9 == 8 )
    goto LABEL_44;
  v10 = v9 - 1;
  if ( !v10 )
  {
    if ( (a2 & 0x10) != 0 )
    {
      v21 = 0;
      if ( a3[5] != 1 )
        v21 = 282;
      v7 = v21;
    }
    LODWORD(v20) = Duration(a1);
LABEL_43:
    v20 = (unsigned int)v20;
    goto LABEL_152;
  }
  v11 = v10 - 1;
  if ( v11 )
  {
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( !v14 )
        {
LABEL_28:
          v16 = 34865153;
LABEL_25:
          *(_QWORD *)v6 = v16;
LABEL_26:
          v7 = 0x10000;
          goto LABEL_156;
        }
        v15 = v14 - 1;
        if ( v15 )
        {
          if ( v15 == 1 )
          {
            v16 = 34865153;
            if ( *((_DWORD *)a1 + 72) == 524 )
              v16 = 34799616;
            goto LABEL_25;
          }
LABEL_49:
          v7 = 274;
          goto LABEL_156;
        }
        v17 = *((unsigned __int16 *)a1 + 30) | ((unsigned __int64)(unsigned __int16)(*((_WORD *)a1 + 30) + 533) << 16);
      }
      else
      {
        v17 = *((unsigned __int16 *)a1 + 144) | ((unsigned __int64)*((unsigned __int16 *)a1 + 144) << 16);
      }
LABEL_30:
      *(_QWORD *)v6 = v17;
      goto LABEL_26;
    }
LABEL_44:
    *(_QWORD *)v6 = 1;
    goto LABEL_156;
  }
  if ( (a2 & 0x10) != 0 )
  {
    if ( a3[5] != 1 )
      v7 = 282;
    goto LABEL_156;
  }
  if ( !v8 )
  {
    v18 = CurrentPosition(a1);
    v19 = StopPosition(a1);
    if ( v18 > v19 )
      v18 = v19;
    v20 = v18;
    goto LABEL_152;
  }
LABEL_156:
  if ( (a2 & 0x20) != 0 && !(_WORD)v7 )
  {
    v7 = 0;
    *(_QWORD *)v6 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x180005934  mov     [rsp-28h+arg_0], rbx
0x180005939  mov     [rsp-28h+arg_10], rsi
0x18000593e  push    rbp
0x18000593f  push    rdi
0x180005940  push    r12
0x180005942  push    r14
0x180005944  push    r15
0x180005946  mov     rbp, rsp
0x180005949  sub     rsp, 50h
0x18000594d  mov     r15d, edx
0x180005950  mov     rsi, rcx
0x180005953  bt      edx, 15h
0x180005957  jnb     short loc_180005963
0x180005959  mov     eax, 112h
0x18000595e  jmp     loc_180006011
0x180005963  xor     r12d, r12d
0x180005966  lea     r14, [r8+8]
0x18000596a  mov     edi, r12d
0x18000596d  bt      r15d, 8
0x180005972  jnb     loc_180005FED
0x180005978  mov     ecx, r15d
0x18000597b  mov     [r14], r12
0x18000597e  lea     ebx, [r12+1]
0x180005983  and     ecx, 10h
0x180005986  jz      short loc_180005992
0x180005988  mov     eax, [r8+10h]
0x18000598c  sub     eax, ebx
0x18000598e  cmp     eax, ebx
0x180005990  ja      short loc_1800059A8
0x180005992  and     edx, 200h
0x180005998  jz      short loc_1800059A1
0x18000599a  cmp     dword ptr [r8+10h], 2
0x18000599f  jnz     short loc_1800059A8
0x1800059a1  bt      r15d, 12h
0x1800059a6  jnb     short loc_1800059B2
0x1800059a8  mov     eax, 11Ch
0x1800059ad  jmp     loc_180006011
0x1800059b2  mov     eax, [r8+10h]
0x1800059b6  mov     r9d, 4019h
0x1800059bc  cmp     eax, r9d
0x1800059bf  ja      loc_180005D84
0x1800059c5  jz      loc_180005D1A
0x1800059cb  mov     r9d, 4008h
0x1800059d1  cmp     eax, r9d
0x1800059d4  ja      loc_180005B58
0x1800059da  jz      def_180005DB6; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x1800059e0  cmp     eax, 8
0x1800059e3  ja      loc_180005AD8
0x1800059e9  jz      loc_180005AD0
0x1800059ef  sub     eax, ebx
0x1800059f1  jz      loc_180005AAC
0x1800059f7  sub     eax, ebx
0x1800059f9  jz      short loc_180005A6E
0x1800059fb  sub     eax, ebx
0x1800059fd  jz      loc_180005AD0
0x180005a03  sub     eax, ebx
0x180005a05  jz      short loc_180005A59
0x180005a07  sub     eax, ebx
0x180005a09  jz      short loc_180005A52; jumptable 0000000180005DB6 case 16428
0x180005a0b  sub     eax, ebx
0x180005a0d  jz      short loc_180005A3B
0x180005a0f  cmp     eax, ebx
0x180005a11  jnz     def_180005DB6; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x180005a17  cmp     dword ptr [rsi+120h], 20Ch
0x180005a21  mov     eax, 2140001h
0x180005a26  mov     ecx, 2130000h
0x180005a2b  cmovz   eax, ecx
0x180005a2e  mov     [r14], rax
0x180005a31  mov     edi, 10000h
0x180005a36  jmp     loc_180005FFE
0x180005a3b  movzx   edx, word ptr [rsi+3Ch]
0x180005a3f  mov     eax, 215h
0x180005a44  add     eax, edx
0x180005a46  movzx   ecx, ax
0x180005a49  shl     rcx, 10h
0x180005a4d  or      rcx, rdx
0x180005a50  jmp     short loc_180005A69
0x180005a52  mov     eax, 2140001h; jumptable 0000000180005DB6 case 16428
0x180005a57  jmp     short loc_180005A2E
0x180005a59  movzx   eax, word ptr [rsi+120h]
0x180005a60  mov     ecx, eax
0x180005a62  shl     rcx, 10h
0x180005a66  or      rcx, rax
0x180005a69  mov     [r14], rcx
0x180005a6c  jmp     short loc_180005A31
0x180005a6e  test    ecx, ecx
0x180005a70  jz      short loc_180005A86
0x180005a72  cmp     [r8+14h], ebx
0x180005a76  jz      loc_180005FFE
0x180005a7c  mov     edi, 11Ah
0x180005a81  jmp     loc_180005FFE
0x180005a86  test    edx, edx
0x180005a88  jnz     loc_180005FFE
0x180005a8e  mov     rcx, rsi; struct _MCIGRAPHIC *
0x180005a91  call    ?CurrentPosition@@YAKPEAU_MCIGRAPHIC@@@Z; CurrentPosition(_MCIGRAPHIC *)
0x180005a96  mov     rcx, rsi; struct _MCIGRAPHIC *
0x180005a99  mov     ebx, eax
0x180005a9b  call    ?StopPosition@@YAKPEAU_MCIGRAPHIC@@@Z; StopPosition(_MCIGRAPHIC *)
0x180005aa0  cmp     ebx, eax
0x180005aa2  cmova   ebx, eax
0x180005aa5  mov     eax, ebx
0x180005aa7  jmp     loc_180005FE8
0x180005aac  test    ecx, ecx
0x180005aae  jz      short loc_180005AC1
0x180005ab0  cmp     [r8+14h], ebx
0x180005ab4  mov     edi, 11Ah
0x180005ab9  mov     eax, r12d
0x180005abc  cmovnz  eax, edi
0x180005abf  mov     edi, eax
0x180005ac1  mov     rcx, rsi; struct _MCIGRAPHIC *
0x180005ac4  call    ?Duration@@YAKPEAU_MCIGRAPHIC@@@Z; Duration(_MCIGRAPHIC *)
0x180005ac9  mov     eax, eax
0x180005acb  jmp     loc_180005FE8
0x180005ad0  mov     [r14], rbx
0x180005ad3  jmp     loc_180005FFE
0x180005ad8  sub     eax, 4000h
0x180005add  jz      short def_180005DB6; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x180005adf  sub     eax, ebx
0x180005ae1  jz      short loc_180005B35
0x180005ae3  sub     eax, 2
0x180005ae6  jz      short loc_180005B1A
0x180005ae8  sub     eax, ebx
0x180005aea  jz      short loc_180005AFC
0x180005aec  sub     eax, ebx
0x180005aee  jz      short def_180005DB6; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x180005af0  sub     eax, ebx
0x180005af2  mov     edi, 112h; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x180005af7  jmp     loc_180005FFE
0x180005afc  lea     rdx, [rbp+arg_18]; unsigned __int64 *
0x180005b00  mov     [rbp+arg_18], r12
0x180005b04  mov     rcx, rsi; struct _MCIGRAPHIC *
0x180005b07  call    ?DeviceGetPalette@@YAKPEAU_MCIGRAPHIC@@PEA_K@Z; DeviceGetPalette(_MCIGRAPHIC *,unsigned __int64 *)
0x180005b0c  mov     rcx, [rbp+arg_18]
0x180005b10  mov     edi, eax
0x180005b12  mov     [r14], rcx
0x180005b15  jmp     loc_180005FFE
0x180005b1a  cmp     [rsi+0D4h], r12d
0x180005b21  jz      short loc_180005B2B
0x180005b23  mov     rax, r12
0x180005b26  jmp     loc_180005FE8
0x180005b2b  mov     rcx, rsi; struct _MCIGRAPHIC *
0x180005b2e  call    ?DeviceGetSpeed@@YAKPEAU_MCIGRAPHIC@@@Z; DeviceGetSpeed(_MCIGRAPHIC *)
0x180005b33  jmp     short loc_180005AC9
0x180005b35  mov     rax, [rsi+128h]
0x180005b3c  mov     [r14], rax
0x180005b3f  mov     rax, [rsi+128h]
0x180005b46  neg     rax
0x180005b49  sbb     edi, edi
0x180005b4b  not     edi
0x180005b4d  and     edi, 112h
0x180005b53  jmp     loc_180005FFE
0x180005b58  mov     ecx, 4012h
0x180005b5d  cmp     eax, ecx
0x180005b5f  ja      loc_180005C61
0x180005b65  jz      short def_180005DB6; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x180005b67  sub     eax, 4009h
0x180005b6c  jz      short def_180005DB6; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x180005b6e  sub     eax, ebx
0x180005b70  jz      short def_180005DB6; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x180005b72  sub     eax, ebx
0x180005b74  jz      loc_180005C57
0x180005b7a  sub     eax, ebx
0x180005b7c  jz      def_180005DB6; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x180005b82  sub     eax, 2
0x180005b85  jz      short loc_180005B94
0x180005b87  sub     eax, ebx
0x180005b89  jz      def_180005DB6; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x180005b8f  jmp     loc_180005EDE
0x180005b94  cmp     [rsi+150h], r12
0x180005b9b  jz      short loc_180005BFD
0x180005b9d  mov     rax, 6666666666666667h
0x180005ba7  imul    qword ptr [rsi+168h]
0x180005bae  mov     rbx, rdx
0x180005bb1  sar     rbx, 2
0x180005bb5  mov     rax, rbx
0x180005bb8  shr     rax, 3Fh
0x180005bbc  add     rbx, rax
0x180005bbf  bt      r15d, 11h
0x180005bc4  jb      short loc_180005BDF
0x180005bc6  mov     rcx, rsi; struct _MCIGRAPHIC *
0x180005bc9  call    ?DeviceGetSpeed@@YAKPEAU_MCIGRAPHIC@@@Z; DeviceGetSpeed(_MCIGRAPHIC *)
0x180005bce  mov     ecx, eax
0x180005bd0  imul    rax, rbx, 3E8h
0x180005bd7  cqo
0x180005bd9  idiv    rcx
0x180005bdc  mov     rbx, rax
0x180005bdf  test    rbx, rbx
0x180005be2  jnz     short loc_180005BEE
0x180005be4  mov     eax, 3E8h
0x180005be9  jmp     loc_180005FE8
0x180005bee  mov     eax, 3B9ACA00h
0x180005bf3  cqo
0x180005bf5  idiv    rbx
0x180005bf8  jmp     loc_180005FE8
0x180005bfd  movsd   xmm1, qword ptr [rsi+248h]
0x180005c05  ucomisd xmm1, cs:__real@0000000000000000
0x180005c0d  jp      short loc_180005C15
0x180005c0f  jz      def_180005DB6; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x180005c15  movsd   xmm0, cs:__real@408f400000000000
0x180005c1d  divsd   xmm0, xmm1
0x180005c21  cvttsd2si eax, xmm0
0x180005c25  movsxd  rcx, eax
0x180005c28  mov     [r14], rcx
0x180005c2b  bt      r15d, 11h
0x180005c30  jb      loc_180005FFE
0x180005c36  mov     rcx, rsi; struct _MCIGRAPHIC *
0x180005c39  call    ?DeviceGetSpeed@@YAKPEAU_MCIGRAPHIC@@@Z; DeviceGetSpeed(_MCIGRAPHIC *)
0x180005c3e  mov     ecx, [r14]; nNumber
0x180005c41  mov     r8d, eax; nDenominator
0x180005c44  mov     edx, 3E8h; nNumerator
0x180005c49  call    cs:__imp_MulDiv
0x180005c4f  movsxd  rcx, eax
0x180005c52  jmp     loc_180005B12
0x180005c57  mov     eax, 80024001h
0x180005c5c  jmp     loc_180005D0D
0x180005c61  sub     eax, 4013h
0x180005c66  jz      def_180005DB6; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x180005c6c  sub     eax, ebx
0x180005c6e  jz      short loc_180005CB1
0x180005c70  sub     eax, ebx
0x180005c72  jz      def_180005DB6; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x180005c78  sub     eax, ebx
0x180005c7a  jz      def_180005DB6; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x180005c80  sub     eax, ebx
0x180005c82  jz      short loc_180005CA7
0x180005c84  cmp     eax, ebx
0x180005c86  jnz     def_180005DB6; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x180005c8c  mov     eax, [rsi+0F8h]
0x180005c92  neg     eax
0x180005c94  mov     eax, 80000001h
0x180005c99  sbb     rcx, rcx
0x180005c9c  movzx   ecx, cx
0x180005c9f  add     rcx, rax
0x180005ca2  mov     [r14], rcx
0x180005ca5  jmp     short loc_180005D10
0x180005ca7  mov     ecx, 2130000h
0x180005cac  jmp     loc_180005A69
0x180005cb1  mov     eax, r12d
0x180005cb4  bt      r15d, 13h
0x180005cb9  jb      short loc_180005CD7
0x180005cbb  cmp     [rsi+0B8h], r12
0x180005cc2  jz      short loc_180005CD7
0x180005cc4  cmp     [rsi+0E8h], r12d
0x180005ccb  jnz     short loc_180005CD7
0x180005ccd  cmp     [rsi+0ECh], r12d
0x180005cd4  cmovnz  eax, ebx
0x180005cd7  bt      r15d, 14h
0x180005cdc  jb      short loc_180005CFA
0x180005cde  cmp     [rsi+0B8h], r12
0x180005ce5  jz      short loc_180005CFA
0x180005ce7  cmp     [rsi+0DCh], r12d
0x180005cee  jnz     short loc_180005CFA
0x180005cf0  cmp     [rsi+0E0h], r12d
0x180005cf7  cmovnz  eax, ebx
0x180005cfa  neg     eax
0x180005cfc  mov     ecx, 80010000h
0x180005d01  sbb     rax, rax
0x180005d04  and     rax, 0FFFFFFFFFFFF0001h
0x180005d0a  add     rax, rcx
0x180005d0d  mov     [r14], rax
0x180005d10  mov     edi, 110000h
0x180005d15  jmp     loc_180005FFE
0x180005d1a  mov     rcx, rsi; struct _MCIGRAPHIC *
0x180005d1d  call    ?ActuallyGetVolume@@YAJPEAU_MCIGRAPHIC@@@Z; ActuallyGetVolume(_MCIGRAPHIC *)
0x180005d22  mov     eax, r15d
0x180005d25  and     eax, 180000h
0x180005d2a  jz      short loc_180005D5B
0x180005d2c  cmp     eax, 80000h
0x180005d31  jz      short loc_180005D53
0x180005d33  cmp     eax, 100000h
0x180005d38  jz      short loc_180005D4B
0x180005d3a  mov     ecx, 80004005h; int
0x180005d3f  mov     r8, r12
0x180005d42  call    ?CheckResult@@YAKJ@Z; CheckResult(long)
0x180005d47  mov     edi, eax
0x180005d49  jmp     short loc_180005D7C
0x180005d4b  mov     eax, [rsi+0ECh]
0x180005d51  jmp     short loc_180005D6C
0x180005d53  mov     eax, [rsi+0E0h]
0x180005d59  jmp     short loc_180005D6C
0x180005d5b  mov     eax, [rsi+0ECh]
0x180005d61  add     eax, [rsi+0E0h]
0x180005d67  cdq
0x180005d68  sub     eax, edx
0x180005d6a  sar     eax, 1
0x180005d6c  cdqe
0x180005d6e  add     rax, rbx
0x180005d71  imul    r8, rax, 3E8h
0x180005d78  shr     r8, 10h
0x180005d7c  mov     [r14], r8
0x180005d7f  jmp     loc_180005FFE
0x180005d84  mov     ecx, 4100h
0x180005d89  cmp     eax, ecx
0x180005d8b  ja      loc_180005EA8
0x180005d91  jz      loc_180005E9F
0x180005d97  add     eax, 0FFFFBFE6h; switch 21 cases
0x180005d9c  cmp     eax, 14h
0x180005d9f  ja      def_180005DB6; jumptable 0000000180005DB6 default case, cases 16410-16416,16420,16421,16427
0x180005da5  lea     rcx, cs:180000000h
0x180005dac  mov     eax, ds:(jpt_180005DB6 - 180000000h)[rcx+rax*4]
  ... truncated ...
```
