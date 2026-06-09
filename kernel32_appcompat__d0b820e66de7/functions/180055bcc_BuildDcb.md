# BuildDcb

- ea: `0x180055bcc`
- end: `0x180056334`
- name: `BuildDcb`
- size: `1896`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180067cb0`
- `0x180067d10`

## callees

- `0x180049b8c`
- `0x180055bcc`
- `0x18005633c`
- `0x18005d52c`
- `0x180067dd4`
- `0x180067df0`
- `0x180067ee4`
- `0x180067f44`
- `0x180068070`
- `0x18008275d`

## import_xrefs

- `ntdll!atol` at `0x180055cb3`
- `ntdll!atol` at `0x180055d96`
- `ntdll!atol` at `0x180055e1a`
- `ntdll!atol` at `0x180055f2e`
- `ntdll!atol` at `0x180055fa5`
- `ntdll!atol` at `0x18005600a`
- `ntdll!atol` at `0x180055cb3`
- `ntdll!atol` at `0x180055d96`
- `ntdll!atol` at `0x180055e1a`
- `ntdll!atol` at `0x180055f2e`
- `ntdll!atol` at `0x180055fa5`
- `ntdll!atol` at `0x18005600a`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180055c7c`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180055c7c`

## string_xrefs

- `0x180055c6d`: `SERIALCOMM`

## pseudocode

```c
__int64 __fastcall BuildDcb(_BYTE *a1, __int64 a2, _QWORD *a3)
{
  unsigned __int8 v4; // si
  unsigned __int8 v5; // r14
  unsigned int v6; // eax
  int v7; // r12d
  _BYTE *i; // rax
  char *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // eax
  int v12; // eax
  int v13; // r9d
  int v14; // edx
  int v15; // r15d
  int v16; // r10d
  int v17; // r13d
  int v18; // r11d
  int v19; // r8d
  unsigned int v20; // eax
  char *v21; // rcx
  unsigned int v22; // eax
  unsigned int v23; // eax
  int v25; // ecx
  int v26; // eax
  unsigned int v27; // eax
  int v28; // eax
  unsigned int v29; // eax
  int v30; // eax
  unsigned int v31; // eax
  int v32; // eax
  unsigned int v33; // eax
  _QWORD *v34; // rax
  bool v35; // cf
  unsigned __int8 v36; // [rsp+34h] [rbp-A5h] BYREF
  unsigned __int8 v37; // [rsp+35h] [rbp-A4h] BYREF
  char v38; // [rsp+36h] [rbp-A3h] BYREF
  char v39; // [rsp+37h] [rbp-A2h] BYREF
  int v40; // [rsp+38h] [rbp-A1h]
  int v41; // [rsp+3Ch] [rbp-9Dh]
  _BYTE *v42; // [rsp+40h] [rbp-99h] BYREF
  _BYTE *v43; // [rsp+48h] [rbp-91h]
  char *String[2]; // [rsp+50h] [rbp-89h]
  int v45; // [rsp+60h] [rbp-79h]
  int v46; // [rsp+64h] [rbp-75h] BYREF
  int v47; // [rsp+68h] [rbp-71h]
  int v48; // [rsp+6Ch] [rbp-6Dh]
  int v49; // [rsp+70h] [rbp-69h]
  int v50; // [rsp+74h] [rbp-65h]
  int v51; // [rsp+78h] [rbp-61h]
  int v52; // [rsp+7Ch] [rbp-5Dh]
  int v53; // [rsp+80h] [rbp-59h]
  int v54; // [rsp+84h] [rbp-55h]
  int v55; // [rsp+88h] [rbp-51h]
  _QWORD v56[20]; // [rsp+90h] [rbp-49h] BYREF
  char v57; // [rsp+140h] [rbp+67h] BYREF
  _QWORD *v58; // [rsp+150h] [rbp+77h]
  char v59; // [rsp+158h] [rbp+7Fh]

  v58 = a3;
  v43 = a1;
  v42 = a1;
  v50 = 0;
  v45 = 0;
  v51 = 0;
  v55 = 0;
  v52 = 0;
  v46 = 0;
  v38 = 0;
  v59 = 0;
  v57 = 0;
  v39 = 0;
  v49 = 0;
  v53 = 0;
  v36 = 0;
  v37 = 0;
  *(_OWORD *)String = 0;
  memset_0(v56, 0, 0x70u);
  v56[0] = &DeviceNameCompare;
  v56[3] = &v42;
  RtlQueryRegistryValuesEx(4, L"SERIALCOMM", v56, 0, 0);
  if ( (unsigned int)Match(&v42, "#") )
  {
    v4 = 1;
    v5 = 1;
    v6 = atol(String[0]);
    if ( !(unsigned int)ConvertBaudRate(v6, &v46) )
      return 0;
    v7 = 1;
    v40 = 0;
    for ( i = v43; ; ++i )
    {
      v42 = i;
      if ( *i != 32 )
        break;
    }
    if ( !(unsigned int)Match(&v42, ",") )
      goto LABEL_27;
    Advance(&v42);
    if ( !(unsigned int)Match(&v42, ",") && (unsigned int)Match(&v42, "@") )
    {
      v9 = String[0];
      LOBYTE(v9) = *String[0];
      if ( !(unsigned int)ConvertParity(v9, &v39) )
        return 0;
      v51 = 1;
      Advance(&v42);
    }
    if ( !(unsigned int)Match(&v42, ",") )
      goto LABEL_27;
    Advance(&v42);
    if ( (unsigned int)Match(&v42, "#") )
    {
      v10 = atol(String[0]);
      if ( !(unsigned int)ConvertDataBits(v10, &v38) )
        return 0;
      v50 = 1;
      Advance(&v42);
    }
    if ( !(unsigned int)Match(&v42, ",") )
      goto LABEL_27;
    Advance(&v42);
    if ( (unsigned int)Match(&v42, "1.5") )
    {
      v59 = 1;
      v45 = 1;
      Advance(&v42);
    }
    else if ( (unsigned int)Match(&v42, "#") )
    {
      v11 = atol(String[0]);
      if ( !(unsigned int)ConvertStopBits(v11, &v57) )
        return 0;
      v45 = 1;
      Advance(&v42);
      v59 = v57;
    }
    if ( (unsigned int)Match(&v42, ",") )
    {
      Advance(&v42);
      if ( (unsigned int)Match(&v42, "x") )
      {
LABEL_25:
        Advance(&v42);
        goto LABEL_28;
      }
      v12 = Match(&v42, "p");
      v13 = 0;
      if ( v12 )
      {
        v4 = 2;
        v5 = 2;
        goto LABEL_25;
      }
      v14 = 0;
    }
    else
    {
LABEL_27:
      v14 = v40;
      v13 = v40;
    }
LABEL_28:
    if ( !*v42 )
    {
      v15 = 1;
      v54 = 1;
      v16 = 1;
      v17 = 1;
      v18 = 1;
      v19 = v14;
      goto LABEL_74;
    }
    return 0;
  }
  v15 = 0;
  v48 = 0;
  v7 = 0;
  v54 = 0;
  v17 = 0;
  v18 = 0;
  v41 = 0;
  v40 = 0;
  v47 = 0;
  while ( *v42 )
  {
    if ( (unsigned int)Match(&v42, "BAUD=#") )
    {
      v20 = atol(String[0]);
      if ( !(unsigned int)ConvertBaudRate(v20, &v46) )
        return 0;
      v15 = 1;
    }
    else if ( (unsigned int)Match(&v42, "PARITY=@") )
    {
      v21 = String[0];
      LOBYTE(v21) = *String[0];
      if ( !(unsigned int)ConvertParity(v21, &v39) )
        return 0;
      v51 = 1;
    }
    else if ( (unsigned int)Match(&v42, "DATA=#") )
    {
      v22 = atol(String[0]);
      if ( !(unsigned int)ConvertDataBits(v22, &v38) )
        return 0;
      v50 = 1;
    }
    else if ( (unsigned int)Match(&v42, "STOP=1.5") )
    {
      v59 = 1;
      v57 = 1;
      v45 = 1;
    }
    else if ( (unsigned int)Match(&v42, "STOP=#") )
    {
      v23 = atol(String[0]);
      if ( !(unsigned int)ConvertStopBits(v23, &v57) )
        return 0;
      v59 = v57;
      v45 = 1;
    }
    else if ( (unsigned int)Match(&v42, "TO=ON") )
    {
      v55 = 1;
      v49 = 1;
    }
    else if ( (unsigned int)Match(&v42, "TO=OFF") )
    {
      v55 = 1;
      v49 = 0;
    }
    else if ( (unsigned int)Match(&v42, "XON=ON") )
    {
      v7 = 1;
      v41 = 1;
    }
    else if ( (unsigned int)Match(&v42, "XON=OFF") )
    {
      v7 = 1;
      v41 = 0;
    }
    else if ( (unsigned int)Match(&v42, "ODSR=ON") )
    {
      v48 = 1;
      v40 = 1;
    }
    else if ( (unsigned int)Match(&v42, "ODSR=OFF") )
    {
      v48 = 1;
      v40 = 0;
    }
    else if ( (unsigned int)Match(&v42, "IDSR=ON") )
    {
      v52 = 1;
      v53 = 1;
    }
    else if ( (unsigned int)Match(&v42, "IDSR=OFF") )
    {
      v52 = 1;
      v53 = 0;
    }
    else if ( (unsigned int)Match(&v42, "OCTS=ON") )
    {
      v17 = 1;
      v47 = 1;
    }
    else if ( (unsigned int)Match(&v42, "OCTS=OFF") )
    {
      v17 = 1;
      v47 = 0;
    }
    else if ( (unsigned int)Match(&v42, "DTR=*") )
    {
      if ( !(unsigned int)ConvertDtrControl(String[0], String[1], &v36) )
        return 0;
      v54 = 1;
    }
    else if ( !(unsigned int)Match(&v42, "RTS=*") || !(unsigned int)ConvertRtsControl(String[0], String[1], &v37) )
    {
      return 0;
    }
    Advance(&v42);
  }
  v4 = v36;
  v5 = v37;
  v14 = v40;
  v19 = v47;
  v13 = v41;
  v16 = v48;
  if ( !v15 )
  {
    v25 = v46;
    goto LABEL_76;
  }
LABEL_74:
  v25 = v46;
  *(_DWORD *)(a2 + 4) = v46;
LABEL_76:
  if ( v50 )
    *(_BYTE *)(a2 + 18) = v38;
  if ( v45 )
  {
    *(_BYTE *)(a2 + 20) = v59;
  }
  else if ( v15 && v25 == 110 )
  {
    *(_BYTE *)(a2 + 20) = 2;
  }
  else
  {
    *(_BYTE *)(a2 + 20) = 0;
  }
  if ( v51 )
    *(_BYTE *)(a2 + 19) = v39;
  if ( v7 )
  {
    v26 = *(_DWORD *)(a2 + 8);
    if ( v13 )
      v27 = v26 | 0x300;
    else
      v27 = v26 & 0xFFFFFCFF;
    *(_DWORD *)(a2 + 8) = v27;
  }
  if ( v17 )
  {
    v28 = *(_DWORD *)(a2 + 8);
    if ( v19 )
      v29 = v28 | 4;
    else
      v29 = v28 & 0xFFFFFFFB;
    *(_DWORD *)(a2 + 8) = v29;
  }
  if ( v16 )
  {
    v30 = *(_DWORD *)(a2 + 8);
    if ( v14 )
      v31 = v30 | 8;
    else
      v31 = v30 & 0xFFFFFFF7;
    *(_DWORD *)(a2 + 8) = v31;
  }
  if ( v52 )
  {
    v32 = *(_DWORD *)(a2 + 8);
    if ( v53 )
      v33 = v32 | 0x40;
    else
      v33 = v32 & 0xFFFFFFBF;
    *(_DWORD *)(a2 + 8) = v33;
  }
  if ( v54 )
    *(_DWORD *)(a2 + 8) ^= (*(_DWORD *)(a2 + 8) ^ (16 * v4)) & 0x30;
  if ( v18 )
    *(_DWORD *)(a2 + 8) ^= (*(_DWORD *)(a2 + 8) ^ (v5 << 12)) & 0x3000;
  if ( v55 )
  {
    v34 = v58;
    v35 = v49 != 0;
    v49 = -v49;
    *v58 = 0;
    v34[1] = 0;
    *((_DWORD *)v34 + 4) = v35 ? 0xEA60 : 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180055bcc  mov     [rsp-8+arg_8], rbx
0x180055bd1  mov     [rsp-8+arg_10], r8
0x180055bd6  push    rbp
0x180055bd7  push    rsi
0x180055bd8  push    rdi
0x180055bd9  push    r12
0x180055bdb  push    r13
0x180055bdd  push    r14
0x180055bdf  push    r15
0x180055be1  lea     rbp, [rsp-27h]
0x180055be6  sub     rsp, 100h
0x180055bed  xor     r14d, r14d
0x180055bf0  mov     [rsp+130h+var_E8], rcx
0x180055bf5  mov     rdi, rdx
0x180055bf8  mov     [rsp+130h+var_F0], rcx
0x180055bfd  xorps   xmm0, xmm0
0x180055c00  mov     [rbp+57h+var_BC], r14d
0x180055c04  xor     edx, edx; Val
0x180055c06  mov     [rbp+57h+var_D0], r14d
0x180055c0a  lea     r8d, [r14+70h]; Size
0x180055c0e  mov     [rbp+57h+var_B8], r14d
0x180055c12  lea     rcx, [rbp+57h+var_A0]; void *
0x180055c16  mov     [rbp+57h+var_A8], r14d
0x180055c1a  mov     [rbp+57h+var_B4], r14d
0x180055c1e  mov     [rbp+57h+var_CC], r14d
0x180055c22  mov     [rsp+130h+var_FA], r14b
0x180055c27  mov     [rbp+57h+arg_18], r14b
0x180055c2b  mov     [rbp+57h+arg_0], r14b
0x180055c2f  mov     [rsp+130h+var_F9], r14b
0x180055c34  mov     [rbp+57h+var_C0], r14d
0x180055c38  mov     [rbp+57h+var_B0], r14d
0x180055c3c  mov     [rsp+130h+var_FC], r14b
0x180055c41  mov     [rsp+130h+var_FB], r14b
0x180055c46  movdqu  xmmword ptr [rsp+130h+String], xmm0
0x180055c4c  call    memset_0
0x180055c51  lea     rax, DeviceNameCompare
0x180055c58  mov     [rsp+130h+var_110], r14
0x180055c5d  mov     [rbp+57h+var_A0], rax
0x180055c61  lea     r8, [rbp+57h+var_A0]
0x180055c65  lea     rax, [rsp+130h+var_F0]
0x180055c6a  xor     r9d, r9d
0x180055c6d  lea     rdx, aSerialcomm; "SERIALCOMM"
0x180055c74  mov     [rbp+57h+var_88], rax
0x180055c78  lea     ecx, [r14+4]
0x180055c7c  call    cs:__imp_RtlQueryRegistryValuesEx
0x180055c83  nop     dword ptr [rax+rax+00h]
0x180055c88  lea     r13, asc_18009178C; "#"
0x180055c8f  mov     rdx, r13
0x180055c92  lea     rcx, [rsp+130h+var_F0]
0x180055c97  call    Match
0x180055c9c  lea     ebx, [r14+1]
0x180055ca0  test    eax, eax
0x180055ca2  jz      loc_180055EDF
0x180055ca8  mov     rcx, [rsp+130h+String]; String
0x180055cad  mov     sil, bl
0x180055cb0  mov     r14b, bl
0x180055cb3  call    cs:__imp_atol
0x180055cba  nop     dword ptr [rax+rax+00h]
0x180055cbf  mov     ecx, eax
0x180055cc1  lea     rdx, [rbp+57h+var_CC]
0x180055cc5  call    ConvertBaudRate
0x180055cca  test    eax, eax
0x180055ccc  jz      loc_1800561F1
0x180055cd2  xor     eax, eax
0x180055cd4  mov     r12d, ebx
0x180055cd7  mov     [rsp+130h+var_F8], eax
0x180055cdb  mov     rax, [rsp+130h+var_E8]
0x180055ce0  jmp     short loc_180055CE5
0x180055ce2  add     rax, rbx
0x180055ce5  mov     [rsp+130h+var_F0], rax
0x180055cea  cmp     byte ptr [rax], 20h ; ' '
0x180055ced  jz      short loc_180055CE2
0x180055cef  lea     r15, asc_180091788; ","
0x180055cf6  mov     rdx, r15
0x180055cf9  lea     rcx, [rsp+130h+var_F0]
0x180055cfe  call    Match
0x180055d03  test    eax, eax
0x180055d05  jz      loc_180055EB3
0x180055d0b  lea     rcx, [rsp+130h+var_F0]
0x180055d10  call    Advance
0x180055d15  mov     rdx, r15
0x180055d18  lea     rcx, [rsp+130h+var_F0]
0x180055d1d  call    Match
0x180055d22  test    eax, eax
0x180055d24  jnz     short loc_180055D61
0x180055d26  lea     rdx, asc_1800928B0; "@"
0x180055d2d  lea     rcx, [rsp+130h+var_F0]
0x180055d32  call    Match
0x180055d37  test    eax, eax
0x180055d39  jz      short loc_180055D61
0x180055d3b  mov     rcx, [rsp+130h+String]
0x180055d40  lea     rdx, [rsp+130h+var_F9]
0x180055d45  mov     cl, [rcx]
0x180055d47  call    ConvertParity
0x180055d4c  test    eax, eax
0x180055d4e  jz      loc_1800561F1
0x180055d54  lea     rcx, [rsp+130h+var_F0]
0x180055d59  mov     [rbp+57h+var_B8], ebx
0x180055d5c  call    Advance
0x180055d61  mov     rdx, r15
0x180055d64  lea     rcx, [rsp+130h+var_F0]
0x180055d69  call    Match
0x180055d6e  test    eax, eax
0x180055d70  jz      loc_180055EB3
0x180055d76  lea     rcx, [rsp+130h+var_F0]
0x180055d7b  call    Advance
0x180055d80  mov     rdx, r13
0x180055d83  lea     rcx, [rsp+130h+var_F0]
0x180055d88  call    Match
0x180055d8d  test    eax, eax
0x180055d8f  jz      short loc_180055DC3
0x180055d91  mov     rcx, [rsp+130h+String]; String
0x180055d96  call    cs:__imp_atol
0x180055d9d  nop     dword ptr [rax+rax+00h]
0x180055da2  mov     ecx, eax
0x180055da4  lea     rdx, [rsp+130h+var_FA]
0x180055da9  call    ConvertDataBits
0x180055dae  test    eax, eax
0x180055db0  jz      loc_1800561F1
0x180055db6  lea     rcx, [rsp+130h+var_F0]
0x180055dbb  mov     [rbp+57h+var_BC], ebx
0x180055dbe  call    Advance
0x180055dc3  mov     rdx, r15
0x180055dc6  lea     rcx, [rsp+130h+var_F0]
0x180055dcb  call    Match
0x180055dd0  test    eax, eax
0x180055dd2  jz      loc_180055EB3
0x180055dd8  lea     rcx, [rsp+130h+var_F0]
0x180055ddd  call    Advance
0x180055de2  lea     rdx, a15; "1.5"
0x180055de9  lea     rcx, [rsp+130h+var_F0]
0x180055dee  call    Match
0x180055df3  lea     rcx, [rsp+130h+var_F0]
0x180055df8  test    eax, eax
0x180055dfa  jz      short loc_180055E09
0x180055dfc  mov     [rbp+57h+arg_18], bl
0x180055dff  mov     [rbp+57h+var_D0], ebx
0x180055e02  call    Advance
0x180055e07  jmp     short loc_180055E4C
0x180055e09  mov     rdx, r13
0x180055e0c  call    Match
0x180055e11  test    eax, eax
0x180055e13  jz      short loc_180055E4C
0x180055e15  mov     rcx, [rsp+130h+String]; String
0x180055e1a  call    cs:__imp_atol
0x180055e21  nop     dword ptr [rax+rax+00h]
0x180055e26  mov     ecx, eax
0x180055e28  lea     rdx, [rbp+57h+arg_0]
0x180055e2c  call    ConvertStopBits
0x180055e31  test    eax, eax
0x180055e33  jz      loc_1800561F1
0x180055e39  lea     rcx, [rsp+130h+var_F0]
0x180055e3e  mov     [rbp+57h+var_D0], ebx
0x180055e41  call    Advance
0x180055e46  mov     al, [rbp+57h+arg_0]
0x180055e49  mov     [rbp+57h+arg_18], al
0x180055e4c  mov     rdx, r15
0x180055e4f  lea     rcx, [rsp+130h+var_F0]
0x180055e54  call    Match
0x180055e59  test    eax, eax
0x180055e5b  jz      short loc_180055EB3
0x180055e5d  lea     rcx, [rsp+130h+var_F0]
0x180055e62  call    Advance
0x180055e67  lea     rdx, asc_1800928B8; "x"
0x180055e6e  lea     rcx, [rsp+130h+var_F0]
0x180055e73  call    Match
0x180055e78  lea     rcx, [rsp+130h+var_F0]
0x180055e7d  test    eax, eax
0x180055e7f  jz      short loc_180055E88
0x180055e81  mov     r9d, ebx
0x180055e84  xor     edx, edx
0x180055e86  jmp     short loc_180055EA8
0x180055e88  lea     rdx, aP; "p"
0x180055e8f  call    Match
0x180055e94  xor     r9d, r9d
0x180055e97  test    eax, eax
0x180055e99  jz      short loc_180055EAF
0x180055e9b  mov     sil, 2
0x180055e9e  lea     rcx, [rsp+130h+var_F0]
0x180055ea3  mov     r14b, sil
0x180055ea6  mov     edx, ebx
0x180055ea8  call    Advance
0x180055ead  jmp     short loc_180055EBA
0x180055eaf  xor     edx, edx
0x180055eb1  jmp     short loc_180055EBA
0x180055eb3  mov     edx, [rsp+130h+var_F8]
0x180055eb7  mov     r9d, edx
0x180055eba  mov     rax, [rsp+130h+var_F0]
0x180055ebf  cmp     byte ptr [rax], 0
0x180055ec2  jnz     loc_1800561F1
0x180055ec8  mov     r15d, ebx
0x180055ecb  mov     [rbp+57h+var_AC], ebx
0x180055ece  mov     r10d, ebx
0x180055ed1  mov     r13d, ebx
0x180055ed4  mov     r11d, ebx
0x180055ed7  mov     r8d, edx
0x180055eda  jmp     loc_180056218
0x180055edf  mov     r15d, r14d
0x180055ee2  mov     [rbp+57h+var_C4], r14d
0x180055ee6  mov     r12d, r14d
0x180055ee9  mov     [rbp+57h+var_AC], r14d
0x180055eed  mov     r13d, r14d
0x180055ef0  mov     [rsp+130h+var_100], r14d
0x180055ef5  mov     r11d, r14d
0x180055ef8  mov     [rsp+130h+var_F4], r14d
0x180055efd  mov     [rsp+130h+var_F8], r14d
0x180055f02  mov     [rbp+57h+var_C8], r14d
0x180055f06  mov     rax, [rsp+130h+var_F0]
0x180055f0b  cmp     [rax], r14b
0x180055f0e  jz      loc_1800561F8
0x180055f14  lea     rdx, aBaud; "BAUD=#"
0x180055f1b  lea     rcx, [rsp+130h+var_F0]
0x180055f20  call    Match
0x180055f25  test    eax, eax
0x180055f27  jz      short loc_180055F55
0x180055f29  mov     rcx, [rsp+130h+String]; String
0x180055f2e  call    cs:__imp_atol
0x180055f35  nop     dword ptr [rax+rax+00h]
0x180055f3a  mov     ecx, eax
0x180055f3c  lea     rdx, [rbp+57h+var_CC]
0x180055f40  call    ConvertBaudRate
0x180055f45  test    eax, eax
0x180055f47  jz      loc_1800561F1
0x180055f4d  mov     r15d, ebx
0x180055f50  jmp     loc_1800561A7
0x180055f55  lea     rdx, aParity; "PARITY=@"
0x180055f5c  lea     rcx, [rsp+130h+var_F0]
0x180055f61  call    Match
0x180055f66  test    eax, eax
0x180055f68  jz      short loc_180055F8B
0x180055f6a  mov     rcx, [rsp+130h+String]
0x180055f6f  lea     rdx, [rsp+130h+var_F9]
0x180055f74  mov     cl, [rcx]
0x180055f76  call    ConvertParity
0x180055f7b  test    eax, eax
0x180055f7d  jz      loc_1800561F1
0x180055f83  mov     [rbp+57h+var_B8], ebx
0x180055f86  jmp     loc_1800561A7
0x180055f8b  lea     rdx, aData; "DATA=#"
0x180055f92  lea     rcx, [rsp+130h+var_F0]
0x180055f97  call    Match
0x180055f9c  test    eax, eax
0x180055f9e  jz      short loc_180055FCD
0x180055fa0  mov     rcx, [rsp+130h+String]; String
0x180055fa5  call    cs:__imp_atol
0x180055fac  nop     dword ptr [rax+rax+00h]
0x180055fb1  mov     ecx, eax
0x180055fb3  lea     rdx, [rsp+130h+var_FA]
0x180055fb8  call    ConvertDataBits
0x180055fbd  test    eax, eax
0x180055fbf  jz      loc_1800561F1
0x180055fc5  mov     [rbp+57h+var_BC], ebx
0x180055fc8  jmp     loc_1800561A7
0x180055fcd  lea     rdx, aStop15; "STOP=1.5"
0x180055fd4  lea     rcx, [rsp+130h+var_F0]
0x180055fd9  call    Match
0x180055fde  test    eax, eax
0x180055fe0  jz      short loc_180055FF0
0x180055fe2  mov     [rbp+57h+arg_18], bl
0x180055fe5  mov     [rbp+57h+arg_0], bl
0x180055fe8  mov     [rbp+57h+var_D0], ebx
0x180055feb  jmp     loc_1800561A7
0x180055ff0  lea     rdx, aStop; "STOP=#"
0x180055ff7  lea     rcx, [rsp+130h+var_F0]
0x180055ffc  call    Match
0x180056001  test    eax, eax
0x180056003  jz      short loc_180056037
0x180056005  mov     rcx, [rsp+130h+String]; String
0x18005600a  call    cs:__imp_atol
0x180056011  nop     dword ptr [rax+rax+00h]
0x180056016  mov     ecx, eax
0x180056018  lea     rdx, [rbp+57h+arg_0]
0x18005601c  call    ConvertStopBits
0x180056021  test    eax, eax
0x180056023  jz      loc_1800561F1
0x180056029  mov     al, [rbp+57h+arg_0]
0x18005602c  mov     [rbp+57h+arg_18], al
0x18005602f  mov     [rbp+57h+var_D0], ebx
0x180056032  jmp     loc_1800561A7
0x180056037  lea     rdx, aToOn; "TO=ON"
0x18005603e  lea     rcx, [rsp+130h+var_F0]
0x180056043  call    Match
0x180056048  test    eax, eax
0x18005604a  jz      short loc_180056057
0x18005604c  mov     [rbp+57h+var_A8], ebx
0x18005604f  mov     [rbp+57h+var_C0], ebx
0x180056052  jmp     loc_1800561A7
0x180056057  lea     rdx, aToOff; "TO=OFF"
0x18005605e  lea     rcx, [rsp+130h+var_F0]
0x180056063  call    Match
0x180056068  test    eax, eax
0x18005606a  jz      short loc_180056078
0x18005606c  mov     [rbp+57h+var_A8], ebx
0x18005606f  mov     [rbp+57h+var_C0], r14d
0x180056073  jmp     loc_1800561A7
0x180056078  lea     rdx, aXonOn; "XON=ON"
0x18005607f  lea     rcx, [rsp+130h+var_F0]
0x180056084  call    Match
0x180056089  test    eax, eax
0x18005608b  jz      short loc_180056099
  ... truncated ...
```
