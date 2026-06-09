# TlsEncryptPacket

- ea: `0x18003e9dc`
- end: `0x18003ed6a`
- name: `TlsEncryptPacket`
- size: `910`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180006a10`

## callees

- `0x1800071b0`
- `0x18000743c`
- `0x1800082b0`
- `0x18001b0a0`
- `0x18003e9dc`
- `0x18003ed70`
- `0x180082888`
- `0x1800838f8`
- `0x180083a3c`
- `0x18009d746`
- `0x18009da40`
- `0x18009dd40`

## string_xrefs

- `0x18003eaa3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800a18f3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsEncryptPacket(
        __int64 a1,
        __int64 a2,
        UCHAR *a3,
        unsigned int a4,
        UCHAR *a5,
        unsigned int a6,
        _DWORD *a7,
        unsigned __int64 a8,
        int a9)
{
  size_t v9; // r13
  unsigned int v12; // edi
  __int64 v13; // r8
  ULONG cbIV; // r15d
  unsigned int v15; // ecx
  unsigned int v16; // ebx
  __int64 v17; // rax
  size_t v18; // rbx
  int v19; // eax
  ULONG cbOutput; // r9d
  unsigned int v22; // r12d
  __int64 v23; // r8
  int v24; // edx
  BOOL v25; // ecx
  int v26; // r11d
  __int64 v27; // r9
  __int64 v28; // rcx
  UCHAR *pbIV; // rbx
  char *v30; // rcx
  unsigned __int64 v31; // rdx
  unsigned int v32; // r8d
  UCHAR *v33; // rcx
  int v34; // edi
  __int64 v35; // rsi
  UCHAR *v36; // rbx
  ULONG v37; // edi
  UCHAR *pbOutput; // [rsp+30h] [rbp-98h]
  ULONG pcbResult; // [rsp+50h] [rbp-78h] BYREF
  int v40; // [rsp+54h] [rbp-74h]
  unsigned int v41; // [rsp+58h] [rbp-70h]
  PUCHAR v42; // [rsp+60h] [rbp-68h]
  unsigned int Size; // [rsp+68h] [rbp-60h]
  unsigned int Size_4; // [rsp+6Ch] [rbp-5Ch]
  __int64 v45; // [rsp+70h] [rbp-58h]
  PUCHAR v46; // [rsp+78h] [rbp-50h]
  int v47; // [rsp+80h] [rbp-48h]
  __int64 v48; // [rsp+88h] [rbp-40h]
  ULONG v50; // [rsp+E8h] [rbp+20h]

  v9 = a4;
  pcbResult = 0;
  if ( a4 <= 0x4000 )
  {
    v12 = *(_DWORD *)(a2 + 8);
    v13 = *(_QWORD *)(a2 + 16);
    LODWORD(v42) = 0;
    v48 = v13;
    if ( BYTE1(v12) != 0xFE || (v41 = 13, v12 > 0xFEFF) )
      v41 = 5;
    cbIV = 0;
    v15 = *(_DWORD *)(v13 + 36);
    v50 = *(_DWORD *)(v13 + 68);
    Size_4 = v15;
    if ( v12 >= 0x302 )
    {
      if ( !wcscmp_0(*(const wchar_t **)(v13 + 48), L"ChainingModeGCM") )
      {
        cbOutput = 0;
        LODWORD(v42) = 1;
        v50 = 0;
        v22 = 16;
        cbIV = 8;
        goto LABEL_20;
      }
      v15 = Size_4;
      if ( Size_4 <= 1 )
        goto LABEL_46;
      if ( Size_4 > 0x10 )
      {
        v27 = 1725;
        goto LABEL_41;
      }
      cbIV = Size_4;
    }
    else if ( v15 <= 1 )
    {
LABEL_46:
      cbOutput = v50;
      v22 = 0;
LABEL_20:
      v23 = v41;
      v24 = v9 + cbIV + v22 + cbOutput;
      Size = v22 + cbOutput;
      v47 = v24 + v41;
      if ( a6 < v24 + v41 || a6 < v41 )
        return (unsigned int)-2146893784;
      v25 = BYTE1(v12) == 0xFE && v12 <= 0xFEFF;
      v26 = a9;
      *a5 = a9;
      a5[1] = *(_BYTE *)(a2 + 9);
      a5[2] = *(_BYTE *)(a2 + 8);
      if ( v25 )
      {
        a5[10] = a8;
        a5[3] = HIBYTE(a8);
        a5[4] = BYTE6(a8);
        a5[5] = BYTE5(a8);
        a5[6] = BYTE4(a8);
        a5[7] = BYTE3(a8);
        a5[8] = BYTE2(a8);
        a5[9] = BYTE1(a8);
        a5[11] = BYTE1(v24);
        a5[12] = v24;
      }
      else
      {
        a5[4] = v24;
        a5[3] = BYTE1(v24);
      }
      v17 = (unsigned int)v23 + cbIV;
      v18 = v9;
      v45 = v17;
      v46 = &a5[v17];
      if ( &a5[v17] == a3 )
      {
        v40 = 1;
LABEL_13:
        if ( cbOutput )
        {
          pbOutput = &a5[v17 + v9];
          if ( *(_DWORD *)(a2 + 8) == 768 )
          {
            v19 = Ssl3ComputeMac(a1, a2, v26, a8, a3, v9, pbOutput, cbOutput);
            v16 = v19;
            if ( v19 < 0 )
            {
              v27 = 1856;
              goto LABEL_55;
            }
          }
          else
          {
            v19 = Tls1ComputeMac(a1, a2, v26, a8, a3, v9, pbOutput, cbOutput);
            v16 = v19;
            if ( v19 < 0 )
            {
              v27 = 1873;
              goto LABEL_55;
            }
          }
          cbOutput = v50;
          v18 = v9;
        }
        if ( (_DWORD)v42 )
        {
          v19 = Tls1AeadEncrypt(a2, a9, a8, a3, v9, (__int64)&a5[v41], (unsigned int)v9 + v22 + cbIV);
          v16 = v19;
          if ( v19 >= 0 )
          {
LABEL_16:
            v16 = 0;
            *a7 = v47;
            return v16;
          }
          v27 = 1904;
          goto LABEL_55;
        }
        memset(&a5[v45 + v18 + cbOutput], (unsigned __int8)(v22 - 1), v22);
        if ( !*(_DWORD *)(v48 + 40) )
        {
          if ( !v40 )
            memmove(v46, a3, v18);
          goto LABEL_16;
        }
        pbIV = 0;
        v42 = 0;
        if ( !cbIV )
        {
LABEL_71:
          if ( v40 )
          {
            v34 = v9 + Size;
            v19 = BCryptEncrypt(
                    *(BCRYPT_KEY_HANDLE *)(a2 + 32),
                    a3,
                    v9 + Size,
                    0,
                    pbIV,
                    cbIV,
                    v46,
                    v9 + Size,
                    &pcbResult,
                    0);
            v16 = v19;
            if ( v19 < 0 )
            {
              v27 = 1965;
              goto LABEL_55;
            }
            if ( pcbResult == v34 )
              goto LABEL_16;
            v27 = 1972;
            goto LABEL_42;
          }
          Size = (unsigned int)v9 % Size_4;
          v35 = (unsigned int)v9 - (unsigned int)v9 % Size_4;
          if ( (_DWORD)v9 != (unsigned int)v9 % Size_4 )
          {
            v19 = BCryptEncrypt(
                    *(BCRYPT_KEY_HANDLE *)(a2 + 32),
                    a3,
                    v35,
                    0,
                    pbIV,
                    cbIV,
                    v46,
                    v9 - (unsigned int)v9 % Size_4,
                    &pcbResult,
                    0);
            v16 = v19;
            if ( v19 < 0 )
            {
              v27 = 1997;
              goto LABEL_55;
            }
            if ( pcbResult != (_DWORD)v35 )
            {
              v27 = 2004;
LABEL_42:
              v16 = -2146893792;
              v28 = 2148073504LL;
              goto LABEL_43;
            }
          }
          v36 = &a5[(unsigned int)v35 + v45];
          memmove(v36, &a3[v35], Size);
          v37 = v9 + v22 - v35 + v50;
          v19 = BCryptEncrypt(*(BCRYPT_KEY_HANDLE *)(a2 + 32), v36, v37, 0, v42, cbIV, v36, v37, &pcbResult, 0);
          v16 = v19;
          if ( v19 >= 0 )
          {
            if ( pcbResult == v37 )
              goto LABEL_16;
            v27 = 2038;
            goto LABEL_42;
          }
          v27 = 2031;
LABEL_55:
          v28 = (unsigned int)v19;
          goto LABEL_43;
        }
        v30 = *(char **)(a2 + 40);
        if ( v30 )
        {
          v31 = *(unsigned int *)(a2 + 48);
          if ( (unsigned int)v31 >= cbIV )
          {
            v32 = *(_DWORD *)(a2 + 52);
            if ( v32 + cbIV > (unsigned int)v31 )
            {
              if ( !SystemPrng(v30, v31) )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                {
                  WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 3));
                }
                return (unsigned int)-2146893779;
              }
              v32 = 0;
            }
            v33 = &a5[v41];
            v42 = (PUCHAR)(*(_QWORD *)(a2 + 40) + v32);
            pbIV = v42;
            *(_DWORD *)(a2 + 52) = v32 + cbIV;
            memmove(v33, pbIV, cbIV);
            goto LABEL_71;
          }
        }
        v27 = 1919;
LABEL_41:
        v16 = -2146893779;
        v28 = 2148073517LL;
LABEL_43:
        DebugTraceError(v28, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v27);
        return v16;
      }
      if ( &a5[v23] == a3 )
      {
        memmove(&a5[v17], a3, v9);
        cbOutput = v50;
        v26 = a9;
        a3 = v46;
        v40 = 1;
LABEL_53:
        v17 = v45;
        goto LABEL_13;
      }
      if ( a3 > a5 )
        goto LABEL_50;
      if ( a5 < &a3[v9] )
      {
LABEL_51:
        v16 = -2146893781;
        v27 = 1829;
        v28 = 2148073515LL;
        goto LABEL_43;
      }
      if ( a3 >= a5 )
      {
LABEL_50:
        if ( a3 < &a5[a6] )
          goto LABEL_51;
      }
      v40 = 0;
      goto LABEL_53;
    }
    cbOutput = v50;
    v22 = v15 - (v50 + (unsigned int)v9) % v15;
    goto LABEL_20;
  }
  v16 = -2146893785;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      121);
  return v16;
}

```

## disassembly

```asm
0x18003e9dc  mov     [rsp+arg_8], rbx
0x18003e9e1  mov     qword ptr [rsp+arg_0], rcx
0x18003e9e6  push    rbp
0x18003e9e7  push    rsi
0x18003e9e8  push    rdi
0x18003e9e9  push    r12
0x18003e9eb  push    r13
0x18003e9ed  push    r14
0x18003e9ef  push    r15
0x18003e9f1  sub     rsp, 90h
0x18003e9f8  mov     r13d, r9d
0x18003e9fb  mov     r14, r8
0x18003e9fe  mov     [rsp+0C8h+var_78], 0
0x18003ea06  mov     rbp, rdx
0x18003ea09  cmp     r9d, 4000h
0x18003ea10  ja      short loc_18003EA72
0x18003ea12  mov     edi, [rdx+8]
0x18003ea15  mov     ebx, edi
0x18003ea17  mov     r8, [rdx+10h]
0x18003ea1b  shr     ebx, 8
0x18003ea1e  mov     dword ptr [rsp+0C8h+var_68], 0
0x18003ea26  mov     [rsp+0C8h+var_40], r8
0x18003ea2e  cmp     bl, 0FEh
0x18003ea31  jz      loc_18003EC79
0x18003ea37  mov     [rsp+0C8h+var_70], 5
0x18003ea3f  mov     eax, [r8+44h]
0x18003ea43  xor     r15d, r15d
0x18003ea46  mov     ecx, [r8+24h]
0x18003ea4a  mov     [rsp+0C8h+arg_18], eax
0x18003ea51  mov     dword ptr [rsp+0C8h+Size+4], ecx
0x18003ea55  lea     esi, [r15+1]
0x18003ea59  cmp     edi, 302h
0x18003ea5f  jnb     loc_18003EBD3
0x18003ea65  cmp     ecx, esi
0x18003ea67  ja      loc_1800A1908
0x18003ea6d  jmp     loc_1800A1923
0x18003ea72  mov     ebx, 80090027h
0x18003ea77  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ea7e  lea     rax, WPP_GLOBAL_Control
0x18003ea85  cmp     rcx, rax
0x18003ea88  jz      loc_18003EBB5
0x18003ea8e  mov     eax, [rcx+2Ch]
0x18003ea91  mov     esi, 1
0x18003ea96  test    sil, al
0x18003ea99  jz      loc_18003EBB5
0x18003ea9f  mov     rcx, [rcx+18h]
0x18003eaa3  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003eaaa  mov     dword ptr [rsp+0C8h+pbOutput], 679h
0x18003eab2  lea     r9, aStatus; "Status"
0x18003eab9  mov     qword ptr [rsp+0C8h+cbIV], r8
0x18003eabe  mov     dword ptr [rsp+0C8h+pbIV], 80090027h
0x18003eac6  call    WPP_SF_sDsd
0x18003eacb  jmp     loc_18003EBB5
0x18003ead0  mov     rcx, qword ptr [rsp+0C8h+arg_38]
0x18003ead8  mov     rax, rcx
0x18003eadb  mov     [rdi+0Ah], cl
0x18003eade  shr     rax, 38h
0x18003eae2  mov     [rdi+3], al
0x18003eae5  mov     rax, rcx
0x18003eae8  shr     rax, 30h
0x18003eaec  mov     [rdi+4], al
0x18003eaef  mov     rax, rcx
0x18003eaf2  shr     rax, 28h
0x18003eaf6  mov     [rdi+5], al
0x18003eaf9  mov     rax, rcx
0x18003eafc  shr     rax, 20h
0x18003eb00  mov     [rdi+6], al
0x18003eb03  mov     rax, rcx
0x18003eb06  shr     rax, 18h
0x18003eb0a  mov     [rdi+7], al
0x18003eb0d  mov     rax, rcx
0x18003eb10  shr     rax, 10h
0x18003eb14  mov     [rdi+8], al
0x18003eb17  mov     rax, rcx
0x18003eb1a  shr     rax, 8
0x18003eb1e  mov     [rdi+9], al
0x18003eb21  mov     eax, edx
0x18003eb23  shr     eax, 8
0x18003eb26  mov     [rdi+0Bh], al
0x18003eb29  mov     [rdi+0Ch], dl
0x18003eb2c  lea     eax, [r8+r15]
0x18003eb30  mov     rbx, r13
0x18003eb33  lea     rcx, [rax+rdi]; void *
0x18003eb37  mov     [rsp+0C8h+var_58], rax
0x18003eb3c  mov     [rsp+0C8h+var_50], rcx
0x18003eb41  cmp     rcx, r14
0x18003eb44  jnz     loc_18003ECC7
0x18003eb4a  mov     [rsp+0C8h+var_74], esi
0x18003eb4e  test    r9d, r9d
0x18003eb51  jnz     loc_18003ECFD
0x18003eb57  cmp     dword ptr [rsp+0C8h+var_68], 0
0x18003eb5c  jz      loc_1800A19A3
0x18003eb62  mov     eax, [rsp+0C8h+var_70]
0x18003eb66  lea     ecx, [r12+r15]
0x18003eb6a  mov     r8, qword ptr [rsp+0C8h+arg_38]
0x18003eb72  add     ecx, r13d
0x18003eb75  mov     edx, [rsp+0C8h+arg_40]
0x18003eb7c  add     rax, rdi
0x18003eb7f  mov     dword ptr [rsp+0C8h+pbOutput], ecx
0x18003eb83  mov     r9, r14
0x18003eb86  mov     qword ptr [rsp+0C8h+cbIV], rax
0x18003eb8b  mov     rcx, rbp
0x18003eb8e  mov     dword ptr [rsp+0C8h+pbIV], r13d
0x18003eb93  call    Tls1AeadEncrypt
0x18003eb98  mov     ebx, eax
0x18003eb9a  test    eax, eax
0x18003eb9c  js      loc_18003ED55
0x18003eba2  mov     rax, [rsp+0C8h+arg_30]
0x18003ebaa  xor     ebx, ebx
0x18003ebac  mov     ecx, [rsp+0C8h+var_48]
0x18003ebb3  mov     [rax], ecx
0x18003ebb5  mov     eax, ebx
0x18003ebb7  mov     rbx, [rsp+0C8h+arg_8]
0x18003ebbf  add     rsp, 90h
0x18003ebc6  pop     r15
0x18003ebc8  pop     r14
0x18003ebca  pop     r13
0x18003ebcc  pop     r12
0x18003ebce  pop     rdi
0x18003ebcf  pop     rsi
0x18003ebd0  pop     rbp
0x18003ebd1  retn
0x18003ebd3  mov     rcx, [r8+30h]; Str1
0x18003ebd7  lea     rdx, aChainingmodegc; "ChainingModeGCM"
0x18003ebde  call    wcscmp_0
0x18003ebe3  test    eax, eax
0x18003ebe5  jnz     loc_18003EC92
0x18003ebeb  xor     r9d, r9d
0x18003ebee  mov     dword ptr [rsp+0C8h+var_68], esi
0x18003ebf2  mov     [rsp+0C8h+arg_18], r9d
0x18003ebfa  lea     r12d, [rax+10h]
0x18003ebfe  lea     r15d, [rax+8]
0x18003ec02  mov     r8d, [rsp+0C8h+var_70]
0x18003ec07  lea     eax, [r12+r9]
0x18003ec0b  mov     r10d, [rsp+0C8h+arg_28]
0x18003ec13  lea     edx, [r15+rax]
0x18003ec17  add     edx, r13d
0x18003ec1a  mov     dword ptr [rsp+0C8h+Size], eax
0x18003ec1e  lea     eax, [rdx+r8]
0x18003ec22  mov     [rsp+0C8h+var_48], eax
0x18003ec29  cmp     r10d, eax
0x18003ec2c  jb      loc_18003ED60
0x18003ec32  cmp     r10d, r8d
0x18003ec35  jb      loc_18003ED60
0x18003ec3b  cmp     bl, 0FEh
0x18003ec3e  jz      short loc_18003ECB8
0x18003ec40  xor     ecx, ecx
0x18003ec42  mov     rdi, [rsp+0C8h+arg_20]
0x18003ec4a  mov     r11d, [rsp+0C8h+arg_40]
0x18003ec52  mov     [rdi], r11b
0x18003ec55  mov     al, [rbp+9]
0x18003ec58  mov     [rdi+1], al
0x18003ec5b  mov     al, [rbp+8]
0x18003ec5e  mov     [rdi+2], al
0x18003ec61  test    ecx, ecx
0x18003ec63  jnz     loc_18003EAD0
0x18003ec69  mov     eax, edx
0x18003ec6b  mov     [rdi+4], dl
0x18003ec6e  shr     eax, 8
0x18003ec71  mov     [rdi+3], al
0x18003ec74  jmp     loc_18003EB2C
0x18003ec79  mov     [rsp+0C8h+var_70], 0Dh
0x18003ec81  cmp     edi, 0FEFFh
0x18003ec87  jbe     loc_18003EA3F
0x18003ec8d  jmp     loc_18003EA37
0x18003ec92  mov     ecx, dword ptr [rsp+0C8h+Size+4]
0x18003ec96  cmp     ecx, esi
0x18003ec98  jbe     loc_1800A1923
0x18003ec9e  mov     r12d, 10h
0x18003eca4  cmp     ecx, r12d
0x18003eca7  jbe     loc_1800A1905
0x18003ecad  mov     r9d, 6BDh
0x18003ecb3  jmp     loc_1800A18D0
0x18003ecb8  cmp     edi, 0FEFFh
0x18003ecbe  ja      short loc_18003EC40
0x18003ecc0  mov     ecx, esi
0x18003ecc2  jmp     loc_18003EC42
0x18003ecc7  lea     rax, [rdi+r8]
0x18003eccb  cmp     rax, r14
0x18003ecce  jnz     loc_1800A1933
0x18003ecd4  mov     r8, rbx; Size
0x18003ecd7  mov     rdx, r14; Src
0x18003ecda  call    memmove
0x18003ecdf  mov     r9d, [rsp+0C8h+arg_18]
0x18003ece7  mov     r11d, [rsp+0C8h+arg_40]
0x18003ecef  mov     r14, [rsp+0C8h+var_50]
0x18003ecf4  mov     [rsp+0C8h+var_74], esi
0x18003ecf8  jmp     loc_1800A1969
0x18003ecfd  mov     [rsp+0C8h+cbOutput], r9d; cbOutput
0x18003ed02  lea     rcx, [rax+r13]
0x18003ed06  mov     r9, qword ptr [rsp+0C8h+arg_38]; int
0x18003ed0e  add     rcx, rdi
0x18003ed11  cmp     dword ptr [rbp+8], 300h
0x18003ed18  mov     r8d, r11d; int
0x18003ed1b  mov     [rsp+0C8h+pbOutput], rcx; pbOutput
0x18003ed20  mov     rdx, rbp; int
0x18003ed23  mov     rcx, qword ptr [rsp+0C8h+arg_0]; int
0x18003ed2b  mov     [rsp+0C8h+cbIV], r13d; cbInput
0x18003ed30  mov     [rsp+0C8h+pbIV], r14; PUCHAR
0x18003ed35  jnz     loc_1800A1980
0x18003ed3b  call    Ssl3ComputeMac
0x18003ed40  mov     ebx, eax
0x18003ed42  test    eax, eax
0x18003ed44  jns     loc_1800A1993
0x18003ed4a  mov     r9d, 740h
0x18003ed50  jmp     loc_1800A1979
0x18003ed55  mov     r9d, 770h
0x18003ed5b  jmp     loc_1800A1979
0x18003ed60  mov     ebx, 80090028h
0x18003ed65  jmp     loc_18003EBB5
0x1800a18ca  mov     r9d, 77Fh
0x1800a18d0  mov     ebx, 8009002Dh
0x1800a18d5  mov     ecx, 8009002Dh
0x1800a18da  jmp     short loc_1800A18EC
0x1800a18dc  mov     r9d, 7B4h
0x1800a18e2  mov     ebx, 80090020h
0x1800a18e7  mov     ecx, 80090020h
0x1800a18ec  lea     rdx, aStatus; "Status"
0x1800a18f3  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a18fa  call    DebugTraceError
0x1800a18ff  nop
0x1800a1900  jmp     loc_18003EBB5
0x1800a1905  mov     r15d, ecx
0x1800a1908  mov     r9d, [rsp+0C8h+arg_18]
0x1800a1910  xor     edx, edx
0x1800a1912  mov     r12d, ecx
0x1800a1915  lea     eax, [r9+r13]
0x1800a1919  div     ecx
0x1800a191b  sub     r12d, edx
0x1800a191e  jmp     loc_18003EC02
0x1800a1923  mov     r9d, [rsp+0C8h+arg_18]
0x1800a192b  xor     r12d, r12d
0x1800a192e  jmp     loc_18003EC02
0x1800a1933  cmp     r14, rdi
0x1800a1936  ja      short loc_1800A1946
0x1800a1938  lea     rax, [r14+r13]
0x1800a193c  cmp     rdi, rax
0x1800a193f  jb      short loc_1800A194F
0x1800a1941  cmp     r14, rdi
0x1800a1944  jb      short loc_1800A1961
0x1800a1946  lea     rax, [rdi+r10]
0x1800a194a  cmp     r14, rax
0x1800a194d  jnb     short loc_1800A1961
0x1800a194f  mov     ebx, 8009002Bh
0x1800a1954  mov     r9d, 725h
0x1800a195a  mov     ecx, 8009002Bh
0x1800a195f  jmp     short loc_1800A18EC
0x1800a1961  mov     [rsp+0C8h+var_74], 0
0x1800a1969  mov     rax, [rsp+0C8h+var_58]
0x1800a196e  jmp     loc_18003EB4E
0x1800a1973  mov     r9d, 7EFh
0x1800a1979  mov     ecx, eax
0x1800a197b  jmp     loc_1800A18EC
0x1800a1980  call    Tls1ComputeMac
0x1800a1985  mov     ebx, eax
0x1800a1987  test    eax, eax
0x1800a1989  jns     short loc_1800A1993
0x1800a198b  mov     r9d, 751h
0x1800a1991  jmp     short loc_1800A1979
0x1800a1993  mov     r9d, [rsp+0C8h+arg_18]
0x1800a199b  mov     rbx, r13
0x1800a199e  jmp     loc_18003EB57
0x1800a19a3  mov     ecx, r9d
0x1800a19a6  mov     al, r12b
0x1800a19a9  add     rcx, rbx
0x1800a19ac  mov     r8d, r12d; Size
0x1800a19af  add     rcx, [rsp+0C8h+var_58]
0x1800a19b4  sub     al, sil
0x1800a19b7  add     rcx, rdi; void *
0x1800a19ba  movzx   edx, al; Val
0x1800a19bd  call    memset
0x1800a19c2  mov     rax, [rsp+0C8h+var_40]
0x1800a19ca  cmp     dword ptr [rax+28h], 0
0x1800a19ce  jz      loc_1800A1BCD
0x1800a19d4  xor     ebx, ebx
0x1800a19d6  mov     [rsp+0C8h+var_68], rbx
0x1800a19db  test    r15d, r15d
0x1800a19de  jz      loc_1800A1A68
0x1800a19e4  mov     rcx, [rbp+28h]; void *
0x1800a19e8  test    rcx, rcx
0x1800a19eb  jz      loc_1800A18CA
0x1800a19f1  mov     edx, [rbp+30h]
0x1800a19f4  cmp     edx, r15d
0x1800a19f7  jb      loc_1800A18CA
0x1800a19fd  mov     r8d, [rbp+34h]
0x1800a1a01  lea     eax, [r8+r15]
0x1800a1a05  cmp     eax, edx
0x1800a1a07  jbe     short loc_1800A1A43
0x1800a1a09  call    SystemPrng
0x1800a1a0e  test    eax, eax
0x1800a1a10  jnz     short loc_1800A1A40
0x1800a1a12  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a1a19  lea     rax, WPP_GLOBAL_Control
0x1800a1a20  cmp     rcx, rax
0x1800a1a23  jz      short loc_1800A1A36
0x1800a1a25  mov     eax, [rcx+2Ch]
0x1800a1a28  test    sil, al
0x1800a1a2b  jz      short loc_1800A1A36
0x1800a1a2d  mov     rcx, [rcx+18h]
0x1800a1a31  call    WPP_SF_ss
  ... truncated ...
```
