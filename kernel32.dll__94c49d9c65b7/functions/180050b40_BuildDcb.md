# BuildDcb

- ea: `0x180050b40`
- end: `0x18005127d`
- name: `BuildDcb`
- size: `1853`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180061380`
- `0x1800613e0`

## callees

- `0x1800453e0`
- `0x180050b40`
- `0x180051284`
- `0x1800588d8`
- `0x180061484`
- `0x1800614a0`
- `0x180061560`
- `0x1800615b8`
- `0x1800616ac`
- `0x18007a7dd`

## import_xrefs

- `ntdll!atol` at `0x180050c21`
- `ntdll!atol` at `0x180050cfe`
- `ntdll!atol` at `0x180050d7c`
- `ntdll!atol` at `0x180050e8a`
- `ntdll!atol` at `0x180050efb`
- `ntdll!atol` at `0x180050f5a`
- `ntdll!atol` at `0x180050c21`
- `ntdll!atol` at `0x180050cfe`
- `ntdll!atol` at `0x180050d7c`
- `ntdll!atol` at `0x180050e8a`
- `ntdll!atol` at `0x180050efb`
- `ntdll!atol` at `0x180050f5a`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180050bf0`
- `ntdll!RtlQueryRegistryValuesEx` at `0x180050bf0`

## string_xrefs

- `0x180050be1`: `SERIALCOMM`

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
0x180050b40  mov     [rsp-8+arg_8], rbx
0x180050b45  mov     [rsp-8+arg_10], r8
0x180050b4a  push    rbp
0x180050b4b  push    rsi
0x180050b4c  push    rdi
0x180050b4d  push    r12
0x180050b4f  push    r13
0x180050b51  push    r14
0x180050b53  push    r15
0x180050b55  lea     rbp, [rsp-27h]
0x180050b5a  sub     rsp, 100h
0x180050b61  xor     r14d, r14d
0x180050b64  mov     [rsp+130h+var_E8], rcx
0x180050b69  mov     rdi, rdx
0x180050b6c  mov     [rsp+130h+var_F0], rcx
0x180050b71  xorps   xmm0, xmm0
0x180050b74  mov     [rbp+57h+var_BC], r14d
0x180050b78  xor     edx, edx; Val
0x180050b7a  mov     [rbp+57h+var_D0], r14d
0x180050b7e  lea     r8d, [r14+70h]; Size
0x180050b82  mov     [rbp+57h+var_B8], r14d
0x180050b86  lea     rcx, [rbp+57h+var_A0]; void *
0x180050b8a  mov     [rbp+57h+var_A8], r14d
0x180050b8e  mov     [rbp+57h+var_B4], r14d
0x180050b92  mov     [rbp+57h+var_CC], r14d
0x180050b96  mov     [rsp+130h+var_FA], r14b
0x180050b9b  mov     [rbp+57h+arg_18], r14b
0x180050b9f  mov     [rbp+57h+arg_0], r14b
0x180050ba3  mov     [rsp+130h+var_F9], r14b
0x180050ba8  mov     [rbp+57h+var_C0], r14d
0x180050bac  mov     [rbp+57h+var_B0], r14d
0x180050bb0  mov     [rsp+130h+var_FC], r14b
0x180050bb5  mov     [rsp+130h+var_FB], r14b
0x180050bba  movdqu  xmmword ptr [rsp+130h+String], xmm0
0x180050bc0  call    memset_0
0x180050bc5  lea     rax, DeviceNameCompare
0x180050bcc  mov     [rsp+130h+var_110], r14
0x180050bd1  mov     [rbp+57h+var_A0], rax
0x180050bd5  lea     r8, [rbp+57h+var_A0]
0x180050bd9  lea     rax, [rsp+130h+var_F0]
0x180050bde  xor     r9d, r9d
0x180050be1  lea     rdx, aSerialcomm; "SERIALCOMM"
0x180050be8  mov     [rbp+57h+var_88], rax
0x180050bec  lea     ecx, [r14+4]
0x180050bf0  call    cs:__imp_RtlQueryRegistryValuesEx
0x180050bf6  lea     r13, asc_1800897B8; "#"
0x180050bfd  mov     rdx, r13
0x180050c00  lea     rcx, [rsp+130h+var_F0]
0x180050c05  call    Match
0x180050c0a  lea     ebx, [r14+1]
0x180050c0e  test    eax, eax
0x180050c10  jz      loc_180050E3B
0x180050c16  mov     rcx, [rsp+130h+String]; String
0x180050c1b  mov     sil, bl
0x180050c1e  mov     r14b, bl
0x180050c21  call    cs:__imp_atol
0x180050c27  mov     ecx, eax
0x180050c29  lea     rdx, [rbp+57h+var_CC]
0x180050c2d  call    ConvertBaudRate
0x180050c32  test    eax, eax
0x180050c34  jz      loc_18005113B
0x180050c3a  xor     eax, eax
0x180050c3c  mov     r12d, ebx
0x180050c3f  mov     [rsp+130h+var_F8], eax
0x180050c43  mov     rax, [rsp+130h+var_E8]
0x180050c48  jmp     short loc_180050C4D
0x180050c4a  add     rax, rbx
0x180050c4d  mov     [rsp+130h+var_F0], rax
0x180050c52  cmp     byte ptr [rax], 20h ; ' '
0x180050c55  jz      short loc_180050C4A
0x180050c57  lea     r15, asc_1800897B4; ","
0x180050c5e  mov     rdx, r15
0x180050c61  lea     rcx, [rsp+130h+var_F0]
0x180050c66  call    Match
0x180050c6b  test    eax, eax
0x180050c6d  jz      loc_180050E0F
0x180050c73  lea     rcx, [rsp+130h+var_F0]
0x180050c78  call    Advance
0x180050c7d  mov     rdx, r15
0x180050c80  lea     rcx, [rsp+130h+var_F0]
0x180050c85  call    Match
0x180050c8a  test    eax, eax
0x180050c8c  jnz     short loc_180050CC9
0x180050c8e  lea     rdx, asc_18008A8D8; "@"
0x180050c95  lea     rcx, [rsp+130h+var_F0]
0x180050c9a  call    Match
0x180050c9f  test    eax, eax
0x180050ca1  jz      short loc_180050CC9
0x180050ca3  mov     rcx, [rsp+130h+String]
0x180050ca8  lea     rdx, [rsp+130h+var_F9]
0x180050cad  mov     cl, [rcx]
0x180050caf  call    ConvertParity
0x180050cb4  test    eax, eax
0x180050cb6  jz      loc_18005113B
0x180050cbc  lea     rcx, [rsp+130h+var_F0]
0x180050cc1  mov     [rbp+57h+var_B8], ebx
0x180050cc4  call    Advance
0x180050cc9  mov     rdx, r15
0x180050ccc  lea     rcx, [rsp+130h+var_F0]
0x180050cd1  call    Match
0x180050cd6  test    eax, eax
0x180050cd8  jz      loc_180050E0F
0x180050cde  lea     rcx, [rsp+130h+var_F0]
0x180050ce3  call    Advance
0x180050ce8  mov     rdx, r13
0x180050ceb  lea     rcx, [rsp+130h+var_F0]
0x180050cf0  call    Match
0x180050cf5  test    eax, eax
0x180050cf7  jz      short loc_180050D25
0x180050cf9  mov     rcx, [rsp+130h+String]; String
0x180050cfe  call    cs:__imp_atol
0x180050d04  mov     ecx, eax
0x180050d06  lea     rdx, [rsp+130h+var_FA]
0x180050d0b  call    ConvertDataBits
0x180050d10  test    eax, eax
0x180050d12  jz      loc_18005113B
0x180050d18  lea     rcx, [rsp+130h+var_F0]
0x180050d1d  mov     [rbp+57h+var_BC], ebx
0x180050d20  call    Advance
0x180050d25  mov     rdx, r15
0x180050d28  lea     rcx, [rsp+130h+var_F0]
0x180050d2d  call    Match
0x180050d32  test    eax, eax
0x180050d34  jz      loc_180050E0F
0x180050d3a  lea     rcx, [rsp+130h+var_F0]
0x180050d3f  call    Advance
0x180050d44  lea     rdx, a15; "1.5"
0x180050d4b  lea     rcx, [rsp+130h+var_F0]
0x180050d50  call    Match
0x180050d55  lea     rcx, [rsp+130h+var_F0]
0x180050d5a  test    eax, eax
0x180050d5c  jz      short loc_180050D6B
0x180050d5e  mov     [rbp+57h+arg_18], bl
0x180050d61  mov     [rbp+57h+var_D0], ebx
0x180050d64  call    Advance
0x180050d69  jmp     short loc_180050DA8
0x180050d6b  mov     rdx, r13
0x180050d6e  call    Match
0x180050d73  test    eax, eax
0x180050d75  jz      short loc_180050DA8
0x180050d77  mov     rcx, [rsp+130h+String]; String
0x180050d7c  call    cs:__imp_atol
0x180050d82  mov     ecx, eax
0x180050d84  lea     rdx, [rbp+57h+arg_0]
0x180050d88  call    ConvertStopBits
0x180050d8d  test    eax, eax
0x180050d8f  jz      loc_18005113B
0x180050d95  lea     rcx, [rsp+130h+var_F0]
0x180050d9a  mov     [rbp+57h+var_D0], ebx
0x180050d9d  call    Advance
0x180050da2  mov     al, [rbp+57h+arg_0]
0x180050da5  mov     [rbp+57h+arg_18], al
0x180050da8  mov     rdx, r15
0x180050dab  lea     rcx, [rsp+130h+var_F0]
0x180050db0  call    Match
0x180050db5  test    eax, eax
0x180050db7  jz      short loc_180050E0F
0x180050db9  lea     rcx, [rsp+130h+var_F0]
0x180050dbe  call    Advance
0x180050dc3  lea     rdx, asc_18008A8E0; "x"
0x180050dca  lea     rcx, [rsp+130h+var_F0]
0x180050dcf  call    Match
0x180050dd4  lea     rcx, [rsp+130h+var_F0]
0x180050dd9  test    eax, eax
0x180050ddb  jz      short loc_180050DE4
0x180050ddd  mov     r9d, ebx
0x180050de0  xor     edx, edx
0x180050de2  jmp     short loc_180050E04
0x180050de4  lea     rdx, aP; "p"
0x180050deb  call    Match
0x180050df0  xor     r9d, r9d
0x180050df3  test    eax, eax
0x180050df5  jz      short loc_180050E0B
0x180050df7  mov     sil, 2
0x180050dfa  lea     rcx, [rsp+130h+var_F0]
0x180050dff  mov     r14b, sil
0x180050e02  mov     edx, ebx
0x180050e04  call    Advance
0x180050e09  jmp     short loc_180050E16
0x180050e0b  xor     edx, edx
0x180050e0d  jmp     short loc_180050E16
0x180050e0f  mov     edx, [rsp+130h+var_F8]
0x180050e13  mov     r9d, edx
0x180050e16  mov     rax, [rsp+130h+var_F0]
0x180050e1b  cmp     byte ptr [rax], 0
0x180050e1e  jnz     loc_18005113B
0x180050e24  mov     r15d, ebx
0x180050e27  mov     [rbp+57h+var_AC], ebx
0x180050e2a  mov     r10d, ebx
0x180050e2d  mov     r13d, ebx
0x180050e30  mov     r11d, ebx
0x180050e33  mov     r8d, edx
0x180050e36  jmp     loc_180051162
0x180050e3b  mov     r15d, r14d
0x180050e3e  mov     [rbp+57h+var_C4], r14d
0x180050e42  mov     r12d, r14d
0x180050e45  mov     [rbp+57h+var_AC], r14d
0x180050e49  mov     r13d, r14d
0x180050e4c  mov     [rsp+130h+var_100], r14d
0x180050e51  mov     r11d, r14d
0x180050e54  mov     [rsp+130h+var_F4], r14d
0x180050e59  mov     [rsp+130h+var_F8], r14d
0x180050e5e  mov     [rbp+57h+var_C8], r14d
0x180050e62  mov     rax, [rsp+130h+var_F0]
0x180050e67  cmp     [rax], r14b
0x180050e6a  jz      loc_180051142
0x180050e70  lea     rdx, aBaud; "BAUD=#"
0x180050e77  lea     rcx, [rsp+130h+var_F0]
0x180050e7c  call    Match
0x180050e81  test    eax, eax
0x180050e83  jz      short loc_180050EAB
0x180050e85  mov     rcx, [rsp+130h+String]; String
0x180050e8a  call    cs:__imp_atol
0x180050e90  mov     ecx, eax
0x180050e92  lea     rdx, [rbp+57h+var_CC]
0x180050e96  call    ConvertBaudRate
0x180050e9b  test    eax, eax
0x180050e9d  jz      loc_18005113B
0x180050ea3  mov     r15d, ebx
0x180050ea6  jmp     loc_1800510F1
0x180050eab  lea     rdx, aParity; "PARITY=@"
0x180050eb2  lea     rcx, [rsp+130h+var_F0]
0x180050eb7  call    Match
0x180050ebc  test    eax, eax
0x180050ebe  jz      short loc_180050EE1
0x180050ec0  mov     rcx, [rsp+130h+String]
0x180050ec5  lea     rdx, [rsp+130h+var_F9]
0x180050eca  mov     cl, [rcx]
0x180050ecc  call    ConvertParity
0x180050ed1  test    eax, eax
0x180050ed3  jz      loc_18005113B
0x180050ed9  mov     [rbp+57h+var_B8], ebx
0x180050edc  jmp     loc_1800510F1
0x180050ee1  lea     rdx, aData; "DATA=#"
0x180050ee8  lea     rcx, [rsp+130h+var_F0]
0x180050eed  call    Match
0x180050ef2  test    eax, eax
0x180050ef4  jz      short loc_180050F1D
0x180050ef6  mov     rcx, [rsp+130h+String]; String
0x180050efb  call    cs:__imp_atol
0x180050f01  mov     ecx, eax
0x180050f03  lea     rdx, [rsp+130h+var_FA]
0x180050f08  call    ConvertDataBits
0x180050f0d  test    eax, eax
0x180050f0f  jz      loc_18005113B
0x180050f15  mov     [rbp+57h+var_BC], ebx
0x180050f18  jmp     loc_1800510F1
0x180050f1d  lea     rdx, aStop15; "STOP=1.5"
0x180050f24  lea     rcx, [rsp+130h+var_F0]
0x180050f29  call    Match
0x180050f2e  test    eax, eax
0x180050f30  jz      short loc_180050F40
0x180050f32  mov     [rbp+57h+arg_18], bl
0x180050f35  mov     [rbp+57h+arg_0], bl
0x180050f38  mov     [rbp+57h+var_D0], ebx
0x180050f3b  jmp     loc_1800510F1
0x180050f40  lea     rdx, aStop; "STOP=#"
0x180050f47  lea     rcx, [rsp+130h+var_F0]
0x180050f4c  call    Match
0x180050f51  test    eax, eax
0x180050f53  jz      short loc_180050F81
0x180050f55  mov     rcx, [rsp+130h+String]; String
0x180050f5a  call    cs:__imp_atol
0x180050f60  mov     ecx, eax
0x180050f62  lea     rdx, [rbp+57h+arg_0]
0x180050f66  call    ConvertStopBits
0x180050f6b  test    eax, eax
0x180050f6d  jz      loc_18005113B
0x180050f73  mov     al, [rbp+57h+arg_0]
0x180050f76  mov     [rbp+57h+arg_18], al
0x180050f79  mov     [rbp+57h+var_D0], ebx
0x180050f7c  jmp     loc_1800510F1
0x180050f81  lea     rdx, aToOn; "TO=ON"
0x180050f88  lea     rcx, [rsp+130h+var_F0]
0x180050f8d  call    Match
0x180050f92  test    eax, eax
0x180050f94  jz      short loc_180050FA1
0x180050f96  mov     [rbp+57h+var_A8], ebx
0x180050f99  mov     [rbp+57h+var_C0], ebx
0x180050f9c  jmp     loc_1800510F1
0x180050fa1  lea     rdx, aToOff; "TO=OFF"
0x180050fa8  lea     rcx, [rsp+130h+var_F0]
0x180050fad  call    Match
0x180050fb2  test    eax, eax
0x180050fb4  jz      short loc_180050FC2
0x180050fb6  mov     [rbp+57h+var_A8], ebx
0x180050fb9  mov     [rbp+57h+var_C0], r14d
0x180050fbd  jmp     loc_1800510F1
0x180050fc2  lea     rdx, aXonOn; "XON=ON"
0x180050fc9  lea     rcx, [rsp+130h+var_F0]
0x180050fce  call    Match
0x180050fd3  test    eax, eax
0x180050fd5  jz      short loc_180050FE3
0x180050fd7  mov     r12d, ebx
0x180050fda  mov     [rsp+130h+var_F4], ebx
0x180050fde  jmp     loc_1800510F1
0x180050fe3  lea     rdx, aXonOff; "XON=OFF"
0x180050fea  lea     rcx, [rsp+130h+var_F0]
0x180050fef  call    Match
0x180050ff4  test    eax, eax
  ... truncated ...
```
