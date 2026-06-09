# TlsEncryptPacket

- ea: `0x18000c1c0`
- end: `0x18000cc36`
- name: `TlsEncryptPacket`
- size: `2678`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000bb90`

## callees

- `0x18000b594`
- `0x18000b654`
- `0x18000c1c0`
- `0x18000d6cc`
- `0x18000da9c`
- `0x1800185e0`
- `0x180020bc4`
- `0x180020c5c`
- `0x180024ef0`
- `0x180024fb0`
- `0x180025660`

## import_xrefs

- `bcrypt!BCryptEncrypt` at `0x18000c485`
- `bcrypt!BCryptEncrypt` at `0x18000c60b`
- `bcrypt!BCryptEncrypt` at `0x18000cae0`
- `bcrypt!BCryptEncrypt` at `0x18000cb68`
- `bcrypt!BCryptEncrypt` at `0x18000c485`
- `bcrypt!BCryptEncrypt` at `0x18000c60b`
- `bcrypt!BCryptEncrypt` at `0x18000cae0`
- `bcrypt!BCryptEncrypt` at `0x18000cb68`
- `bcrypt!BCryptGenRandom` at `0x18000c94a`
- `bcrypt!BCryptGenRandom` at `0x18000c94a`

## string_xrefs

- `0x18000c504`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000c644`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000c6d2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000c727`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000c7b8`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000c8a5`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000c926`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000cb7a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000cbae`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000cbf2`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000cc0b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsEncryptPacket(
        __int64 a1,
        __int64 a2,
        UCHAR *a3,
        unsigned int a4,
        PUCHAR a5,
        unsigned int a6,
        ULONG *a7,
        unsigned __int64 a8,
        int a9)
{
  size_t cbOutput; // rdi
  unsigned int v11; // eax
  __int64 v12; // rcx
  unsigned int v13; // ebx
  int v14; // esi
  ULONG v15; // r9d
  ULONG cbIV; // r13d
  ULONG v17; // r10d
  int v18; // edx
  unsigned int v19; // r12d
  int v20; // edx
  int v21; // r8d
  unsigned int v22; // esi
  __int16 v23; // cx
  __int64 v24; // r10
  BOOL v25; // r8d
  int v26; // r11d
  UCHAR *v27; // r8
  UCHAR *v28; // rbx
  __int64 v29; // rcx
  int v30; // edx
  __int16 v31; // cx
  int v32; // eax
  UCHAR *v33; // rdx
  void *v34; // rcx
  NTSTATUS v35; // eax
  int v36; // edx
  int v37; // r8d
  unsigned int v38; // ebx
  int v40; // r8d
  UCHAR *pbIV; // rcx
  UCHAR *v42; // rdx
  ULONG v43; // ecx
  unsigned int v44; // r8d
  PUCHAR v45; // rdx
  ULONG v46; // edi
  int v47; // eax
  int v48; // edx
  int v49; // r8d
  _QWORD *v50; // rcx
  int v51; // eax
  __int64 v52; // r9
  NTSTATUS v53; // eax
  __int64 v54; // r8
  __int64 v55; // rcx
  _QWORD *v56; // rcx
  ULONG v57; // edi
  NTSTATUS v58; // eax
  UCHAR *v59; // rbx
  __int64 v60; // rcx
  ULONG v61; // edi
  ULONG v62; // edi
  NTSTATUS v63; // eax
  char pbOutput; // [rsp+38h] [rbp-D0h]
  UCHAR *pbOutputa; // [rsp+38h] [rbp-D0h]
  ULONG v66; // [rsp+58h] [rbp-B0h]
  int Size; // [rsp+5Ch] [rbp-ACh]
  ULONG Size_4; // [rsp+60h] [rbp-A8h] BYREF
  ULONG pcbResult; // [rsp+64h] [rbp-A4h] BYREF
  PUCHAR v70; // [rsp+68h] [rbp-A0h]
  PUCHAR pbInput; // [rsp+70h] [rbp-98h]
  ULONG cbInput[2]; // [rsp+78h] [rbp-90h]
  UCHAR *v73; // [rsp+80h] [rbp-88h]
  ULONG v74; // [rsp+88h] [rbp-80h]
  int v75[2]; // [rsp+90h] [rbp-78h]
  ULONG *v76; // [rsp+98h] [rbp-70h]
  _QWORD pPaddingInfo[12]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v78; // [rsp+108h] [rbp+0h] BYREF
  char v79; // [rsp+110h] [rbp+8h]
  char v80; // [rsp+111h] [rbp+9h]
  char v81; // [rsp+112h] [rbp+Ah]
  char v82; // [rsp+113h] [rbp+Bh]
  char v83; // [rsp+114h] [rbp+Ch]
  _QWORD v84[2]; // [rsp+118h] [rbp+10h] BYREF

  v76 = a7;
  cbOutput = a4;
  pbInput = a3;
  *(_QWORD *)v75 = a1;
  Size_4 = 0;
  if ( a4 > 0x4000 )
  {
    v38 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        121);
    return v38;
  }
  v11 = *(_DWORD *)(a2 + 8);
  v12 = *(_QWORD *)(a2 + 16);
  v13 = v11 >> 8;
  LODWORD(v70) = 0;
  v84[0] = v12;
  if ( BYTE1(v11) == 0xFE && v11 <= 0xFEFF )
    v14 = 13;
  else
    v14 = 5;
  v15 = *(_DWORD *)(v12 + 68);
  cbIV = 0;
  v17 = *(_DWORD *)(v12 + 36);
  v18 = v14;
  v19 = v14;
  v66 = v15;
  pcbResult = v17;
  if ( v11 < 0x302 )
    goto LABEL_40;
  if ( !wcscmp(*(const wchar_t **)(v12 + 48), L"ChainingModeGCM") )
  {
    cbIV = 8;
    v22 = 16;
    v15 = 0;
    LODWORD(v70) = 1;
LABEL_7:
    v66 = v15;
    goto LABEL_8;
  }
  v17 = pcbResult;
  if ( pcbResult <= 1 )
  {
    v15 = v66;
    v18 = v14;
LABEL_40:
    LODWORD(v70) = 0;
    v19 = v18;
    v66 = v15;
    if ( v17 > 1 )
    {
      v22 = v17 - ((unsigned int)cbOutput + v15) % v17;
      goto LABEL_8;
    }
    v22 = 0;
    LODWORD(v70) = 0;
    goto LABEL_7;
  }
  if ( pcbResult > 0x10 )
  {
    v38 = -2146893779;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        v21,
        (unsigned int)"Status",
        45,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        189);
    return v38;
  }
  v15 = v66;
  cbIV = pcbResult;
  v22 = pcbResult - ((unsigned int)cbOutput + v66) % pcbResult;
LABEL_8:
  cbInput[0] = v15 + cbOutput + v22;
  v23 = LOWORD(cbInput[0]) + cbIV;
  v74 = cbInput[0] + cbIV + v19;
  if ( a6 < v74 || a6 < v19 )
    return (unsigned int)-2146893784;
  v24 = v19 + cbIV;
  v25 = (_BYTE)v13 == 0xFE && *(_DWORD *)(a2 + 8) <= 0xFEFFu;
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
    a5[11] = HIBYTE(v23);
    a5[12] = v23;
  }
  else
  {
    a5[4] = v23;
    a5[3] = HIBYTE(v23);
  }
  v27 = pbInput;
  v28 = &a5[v24];
  v29 = (unsigned int)v24;
  v78 = (unsigned int)v24;
  v73 = &a5[v24];
  if ( &a5[v24] == pbInput )
  {
    Size = 1;
    goto LABEL_16;
  }
  if ( &a5[v19] == pbInput )
  {
    memmove(&a5[v24], pbInput, cbOutput);
    v15 = v66;
    LODWORD(v24) = v19 + cbIV;
    v29 = v78;
    v27 = v28;
    v26 = a9;
    pbInput = v28;
    Size = 1;
  }
  else
  {
    if ( pbInput > a5 )
      goto LABEL_67;
    if ( a5 < &pbInput[cbOutput] )
      goto LABEL_68;
    if ( pbInput >= a5 )
    {
LABEL_67:
      if ( pbInput < &a5[a6] )
      {
LABEL_68:
        v38 = -2146893781;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            a6,
            (_DWORD)pbInput,
            (unsigned int)"Status",
            43,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            37);
        return v38;
      }
    }
    Size = 0;
  }
LABEL_16:
  if ( !v15 )
  {
LABEL_17:
    if ( (_DWORD)v70 )
    {
      memset(pPaddingInfo, 0, 0x58u);
      pcbResult = 0;
      if ( cbIV + (_DWORD)cbOutput + v22 == (_DWORD)cbOutput + 24 )
      {
        v31 = *(_WORD *)(a2 + 8);
        LOBYTE(v78) = HIBYTE(a8);
        BYTE1(v78) = BYTE6(a8);
        BYTE2(v78) = BYTE5(a8);
        BYTE3(v78) = BYTE4(a8);
        BYTE4(v78) = BYTE3(a8);
        BYTE5(v78) = BYTE2(a8);
        BYTE6(v78) = BYTE1(a8);
        v79 = a9;
        v80 = HIBYTE(v31);
        v82 = BYTE1(cbOutput);
        v32 = *(_DWORD *)(a2 + 56);
        HIBYTE(v78) = a8;
        LODWORD(v84[0]) = v32;
        v81 = v31;
        *(_QWORD *)((char *)v84 + 4) = v78;
        v33 = &a5[v19];
        v83 = cbOutput;
        LODWORD(pPaddingInfo[0]) = 88;
        pPaddingInfo[5] = &v33[cbOutput + 8];
        *(_QWORD *)v33 = v78;
        v34 = *(void **)(a2 + 32);
        pPaddingInfo[1] = v84;
        pPaddingInfo[3] = &v78;
        HIDWORD(pPaddingInfo[0]) = 1;
        LODWORD(pPaddingInfo[2]) = 12;
        LODWORD(pPaddingInfo[4]) = 13;
        LODWORD(pPaddingInfo[6]) = 16;
        v35 = BCryptEncrypt(v34, pbInput, cbOutput, pPaddingInfo, 0, 0, v33 + 8, cbOutput, &pcbResult, 0);
        v38 = v35;
        if ( v35 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v36,
              v37,
              (unsigned int)"Status",
              v35,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              128);
        }
        else
        {
          if ( pcbResult == (_DWORD)cbOutput )
          {
LABEL_21:
            v38 = 0;
            *v76 = v74;
            return v38;
          }
          v38 = -2146893792;
          DebugTraceError(2148073504LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 647);
        }
      }
      else
      {
        v38 = -2146893779;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v30,
            0,
            (unsigned int)"Status",
            45,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            52);
      }
      DebugTraceError(v38, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 1904);
      return v38;
    }
    memset(&a5[(unsigned int)v24 + v15 + cbOutput], (unsigned __int8)(v22 - 1), v22);
    if ( !*(_DWORD *)(v84[0] + 40LL) )
    {
      if ( !Size )
        memmove(&a5[v19 + cbIV], pbInput, cbOutput);
      goto LABEL_21;
    }
    pbIV = 0;
    v70 = 0;
    if ( cbIV )
    {
      v42 = *(UCHAR **)(a2 + 40);
      if ( !v42 || (v43 = *(_DWORD *)(a2 + 48), v43 < cbIV) )
      {
        v38 = -2146893779;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v42,
            v40,
            (unsigned int)"Status",
            45,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            127);
        return v38;
      }
      v44 = *(_DWORD *)(a2 + 52);
      if ( v44 + cbIV > v43 )
      {
        v53 = BCryptGenRandom(0, v42, v43, 2u);
        if ( v53 < 0 )
        {
          v56 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v54, (unsigned int)v53);
              v56 = WPP_GLOBAL_Control;
            }
            if ( v56 != &WPP_GLOBAL_Control && (*((_BYTE *)v56 + 28) & 1) != 0 )
              WPP_SF_ss(v56[2]);
          }
          return (unsigned int)-2146893779;
        }
        v44 = 0;
      }
      v70 = (PUCHAR)(*(_QWORD *)(a2 + 40) + v44);
      v45 = v70;
      *(_DWORD *)(a2 + 52) = v44 + cbIV;
      memmove(&a5[v19], v45, cbIV);
      pbIV = v70;
    }
    if ( Size )
    {
      v46 = cbInput[0];
      v47 = BCryptEncrypt(
              *(BCRYPT_KEY_HANDLE *)(a2 + 32),
              pbInput,
              cbInput[0],
              0,
              pbIV,
              cbIV,
              v28,
              cbInput[0],
              &Size_4,
              0);
      v38 = v47;
      if ( v47 < 0 )
      {
        v50 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          pbOutput = -83;
LABEL_38:
          WPP_SF_sDsd(
            v50[2],
            v48,
            v49,
            (unsigned int)"Status",
            v47,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            pbOutput);
          return v38;
        }
        return v38;
      }
      if ( Size_4 == v46 )
        goto LABEL_21;
      v52 = 1972;
      goto LABEL_103;
    }
    cbInput[0] = (unsigned int)cbOutput % pcbResult;
    v57 = cbOutput - (unsigned int)cbOutput % pcbResult;
    if ( !v57 )
      goto LABEL_99;
    v58 = BCryptEncrypt(*(BCRYPT_KEY_HANDLE *)(a2 + 32), pbInput, v57, 0, pbIV, cbIV, v28, v57, &Size_4, 0);
    v38 = v58;
    if ( v58 < 0 )
    {
      v52 = 1997;
      v55 = (unsigned int)v58;
      goto LABEL_104;
    }
    if ( Size_4 == v57 )
    {
LABEL_99:
      v59 = &a5[v57 + v78];
      v60 = v57;
      v61 = cbInput[0];
      memmove(v59, &pbInput[v60], cbInput[0]);
      v62 = v66 + v22 + v61;
      v63 = BCryptEncrypt(*(BCRYPT_KEY_HANDLE *)(a2 + 32), v59, v62, 0, v70, cbIV, v59, v62, &Size_4, 0);
      v38 = v63;
      if ( v63 < 0 )
      {
        DebugTraceError(
          (unsigned int)v63,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          2031);
        return v38;
      }
      if ( Size_4 == v62 )
        goto LABEL_21;
      v52 = 2038;
    }
    else
    {
      v52 = 2004;
    }
LABEL_103:
    v38 = -2146893792;
    v55 = 2148073504LL;
    goto LABEL_104;
  }
  pbOutputa = &a5[v29 + cbOutput];
  if ( *(_DWORD *)(a2 + 8) != 768 )
  {
    v51 = Tls1ComputeMac(v75[0], a2, v26, a8, v27, cbOutput, pbOutputa, v15);
    v38 = v51;
    if ( v51 < 0 )
    {
      v52 = 1873;
      v55 = (unsigned int)v51;
LABEL_104:
      DebugTraceError(v55, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v52);
      return v38;
    }
    goto LABEL_54;
  }
  v47 = Ssl3ComputeMac(*(__int64 *)v75, a2, v26, a8, v27, cbOutput, pbOutputa, v15);
  v38 = v47;
  if ( v47 >= 0 )
  {
LABEL_54:
    v28 = v73;
    LODWORD(v24) = v19 + cbIV;
    v15 = v66;
    goto LABEL_17;
  }
  v50 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    pbOutput = 64;
    goto LABEL_38;
  }
  return v38;
}

```

## disassembly

```asm
0x18000c1c0  mov     r11, rsp
0x18000c1c3  push    rbp
0x18000c1c4  push    rbx
0x18000c1c5  push    rdi
0x18000c1c6  push    r14
0x18000c1c8  push    r15
0x18000c1ca  lea     rbp, [r11-78h]
0x18000c1ce  sub     rsp, 150h
0x18000c1d5  mov     rax, cs:__security_cookie
0x18000c1dc  xor     rax, rsp
0x18000c1df  mov     [rbp+70h+var_50], rax
0x18000c1e3  mov     rax, [rbp+70h+arg_30]
0x18000c1ea  mov     r15, rdx
0x18000c1ed  mov     r14, [rbp+70h+arg_20]
0x18000c1f4  mov     [rbp+70h+var_E0], rax
0x18000c1f8  mov     edi, r9d
0x18000c1fb  mov     [rsp+170h+pbInput], r8
0x18000c200  mov     qword ptr [rbp+70h+var_E8], rcx
0x18000c204  mov     dword ptr [rsp+170h+Size+4], 0
0x18000c20c  cmp     r9d, 4000h
0x18000c213  ja      loc_18000C78E
0x18000c219  mov     eax, [rdx+8]
0x18000c21c  xor     r8d, r8d
0x18000c21f  mov     rcx, [rdx+10h]
0x18000c223  mov     ebx, eax
0x18000c225  mov     [r11-30h], rsi
0x18000c229  shr     ebx, 8
0x18000c22c  mov     [r11-38h], r12
0x18000c230  mov     [r11-40h], r13
0x18000c234  mov     dword ptr [rsp+170h+var_110], r8d
0x18000c239  mov     qword ptr [rbp+70h+var_60], rcx
0x18000c23d  cmp     bl, 0FEh
0x18000c240  jz      loc_18000C8CA
0x18000c246  mov     esi, 5
0x18000c24b  mov     r9d, [rcx+44h]
0x18000c24f  xor     r13d, r13d
0x18000c252  mov     r10d, [rcx+24h]
0x18000c256  mov     edx, esi
0x18000c258  mov     dword ptr [rsp+170h+Size], edx
0x18000c25c  mov     r12d, esi
0x18000c25f  mov     [rsp+170h+var_120], r9d
0x18000c264  mov     [rsp+170h+var_114], r10d
0x18000c269  cmp     eax, 302h
0x18000c26e  jb      loc_18000C665
0x18000c274  mov     rcx, [rcx+30h]; String1
0x18000c278  lea     rdx, aChainingmodegc; "ChainingModeGCM"
0x18000c27f  call    wcscmp
0x18000c284  test    eax, eax
0x18000c286  jnz     loc_18000C68F
0x18000c28c  mov     dword ptr [rsp+170h+Size], 10h
0x18000c294  mov     r13d, 8
0x18000c29a  mov     esi, dword ptr [rsp+170h+Size]
0x18000c29e  xor     r9d, r9d
0x18000c2a1  mov     dword ptr [rsp+170h+var_110], 1
0x18000c2a9  mov     [rsp+170h+var_120], r9d
0x18000c2ae  mov     edx, [rbp+70h+arg_28]
0x18000c2b4  lea     eax, [rdi+rsi]
0x18000c2b7  add     eax, r9d
0x18000c2ba  mov     [rsp+170h+cbInput], eax
0x18000c2be  lea     ecx, [rax+r13]
0x18000c2c2  lea     eax, [rcx+r12]
0x18000c2c6  mov     [rbp+70h+var_F0], eax
0x18000c2c9  cmp     edx, eax
0x18000c2cb  jb      loc_18000C6FB
0x18000c2d1  cmp     edx, r12d
0x18000c2d4  jb      loc_18000C6FB
0x18000c2da  lea     r10d, [r12+r13]
0x18000c2de  cmp     bl, 0FEh
0x18000c2e1  jz      loc_18000C8DF
0x18000c2e7  xor     r8d, r8d
0x18000c2ea  mov     r11d, [rbp+70h+arg_40]
0x18000c2f1  mov     [r14], r11b
0x18000c2f4  movzx   eax, byte ptr [r15+9]
0x18000c2f9  mov     [r14+1], al
0x18000c2fd  movzx   eax, byte ptr [r15+8]
0x18000c302  mov     [r14+2], al
0x18000c306  test    r8d, r8d
0x18000c309  jnz     loc_18000C973
0x18000c30f  mov     eax, ecx
0x18000c311  mov     [r14+4], cl
0x18000c315  shr     eax, 8
0x18000c318  mov     [r14+3], al
0x18000c31c  mov     r8, [rsp+170h+pbInput]
0x18000c321  lea     rbx, [r10+r14]
0x18000c325  mov     ecx, r10d
0x18000c328  mov     [rbp+70h+var_70], rcx
0x18000c32c  mov     [rsp+170h+var_F8], rbx
0x18000c331  cmp     rbx, r8
0x18000c334  jnz     loc_18000C852
0x18000c33a  mov     dword ptr [rsp+170h+Size], 1
0x18000c342  test    r9d, r9d
0x18000c345  jnz     loc_18000C733
0x18000c34b  cmp     dword ptr [rsp+170h+var_110], 0
0x18000c350  jz      loc_18000C540
0x18000c356  xor     edx, edx; Val
0x18000c358  lea     rcx, [rbp+70h+pPaddingInfo]; void *
0x18000c35c  mov     r8d, 58h ; 'X'; Size
0x18000c362  call    memset
0x18000c367  xor     r8d, r8d
0x18000c36a  lea     ecx, [rdi+rsi]
0x18000c36d  add     ecx, r13d
0x18000c370  mov     [rsp+170h+var_114], r8d
0x18000c375  lea     eax, [rdi+18h]
0x18000c378  cmp     ecx, eax
0x18000c37a  jnz     loc_18000C705
0x18000c380  mov     rdx, qword ptr [rbp+70h+arg_38]
0x18000c387  lea     r9, [rbp+70h+pPaddingInfo]; pPaddingInfo
0x18000c38b  movzx   ecx, word ptr [r15+8]
0x18000c390  mov     rax, rdx
0x18000c393  shr     rax, 38h
0x18000c397  mov     byte ptr [rbp+70h+var_70], al
0x18000c39a  mov     rax, rdx
0x18000c39d  shr     rax, 30h
0x18000c3a1  mov     byte ptr [rbp+70h+var_70+1], al
0x18000c3a4  mov     rax, rdx
0x18000c3a7  shr     rax, 28h
0x18000c3ab  mov     byte ptr [rbp+70h+var_70+2], al
0x18000c3ae  mov     rax, rdx
0x18000c3b1  shr     rax, 20h
0x18000c3b5  mov     byte ptr [rbp+70h+var_70+3], al
0x18000c3b8  mov     rax, rdx
0x18000c3bb  shr     rax, 18h
0x18000c3bf  mov     byte ptr [rbp+70h+var_70+4], al
0x18000c3c2  mov     rax, rdx
0x18000c3c5  shr     rax, 10h
0x18000c3c9  mov     byte ptr [rbp+70h+var_70+5], al
0x18000c3cc  mov     rax, rdx
0x18000c3cf  shr     rax, 8
0x18000c3d3  mov     byte ptr [rbp+70h+var_70+6], al
0x18000c3d6  mov     eax, [rbp+70h+arg_40]
0x18000c3dc  mov     [rbp+70h+var_68], al
0x18000c3df  movzx   eax, cx
0x18000c3e2  shr     ax, 8
0x18000c3e6  mov     [rbp+70h+var_67], al
0x18000c3e9  movzx   eax, di
0x18000c3ec  shr     ax, 8
0x18000c3f0  mov     [rsp+170h+dwFlags], r8d; dwFlags
0x18000c3f5  mov     [rbp+70h+var_65], al
0x18000c3f8  mov     eax, [r15+38h]
0x18000c3fc  mov     byte ptr [rbp+70h+var_70+7], dl
0x18000c3ff  mov     dword ptr [rbp+70h+var_60], eax
0x18000c402  mov     rax, [rbp+70h+var_70]
0x18000c406  mov     [rbp+70h+var_66], cl
0x18000c409  lea     rcx, [rdi+8]
0x18000c40d  mov     qword ptr [rbp+70h+var_60+4], rax
0x18000c411  mov     edx, r12d
0x18000c414  add     rdx, r14
0x18000c417  mov     [rbp+70h+var_64], dil
0x18000c41b  add     rcx, rdx
0x18000c41e  mov     [rbp+70h+pPaddingInfo], 58h ; 'X'
0x18000c425  mov     [rbp+70h+var_A8], rcx
0x18000c429  lea     rcx, [rsp+170h+var_114]
0x18000c42e  mov     [rsp+170h+pcbResult], rcx; pcbResult
0x18000c433  mov     [rdx], rax
0x18000c436  lea     rax, [rbp+70h+var_60]
0x18000c43a  mov     rcx, [r15+20h]; hKey
0x18000c43e  mov     [rbp+70h+var_C8], rax
0x18000c442  lea     rax, [rbp+70h+var_70]
0x18000c446  mov     [rsp+170h+cbOutput], edi; cbOutput
0x18000c44a  mov     [rbp+70h+var_B8], rax
0x18000c44e  lea     rax, [rdx+8]
0x18000c452  mov     rdx, [rsp+170h+pbInput]; pbInput
0x18000c457  mov     [rsp+170h+pbOutput], rax; pbOutput
0x18000c45c  mov     [rsp+170h+cbIV], r8d; cbIV
0x18000c461  mov     [rsp+170h+pbIV], r8; pbIV
0x18000c466  mov     r8d, edi; cbInput
0x18000c469  mov     [rbp+70h+var_CC], 1
0x18000c470  mov     [rbp+70h+var_C0], 0Ch
0x18000c477  mov     [rbp+70h+var_B0], 0Dh
0x18000c47e  mov     [rbp+70h+var_A0], 10h
0x18000c485  call    cs:__imp_BCryptEncrypt
0x18000c48b  mov     ebx, eax
0x18000c48d  test    eax, eax
0x18000c48f  js      short loc_18000C4DB
0x18000c491  cmp     [rsp+170h+var_114], edi
0x18000c495  jnz     loc_18000CC0B
0x18000c49b  mov     rcx, [rbp+70h+var_E0]
0x18000c49f  xor     ebx, ebx
0x18000c4a1  mov     eax, [rbp+70h+var_F0]
0x18000c4a4  mov     [rcx], eax
0x18000c4a6  mov     r12, [rsp+170h+var_30]
0x18000c4ae  mov     rsi, [rsp+148h]
0x18000c4b6  mov     r13, [rsp+170h+var_38]
0x18000c4be  mov     eax, ebx
0x18000c4c0  mov     rcx, [rbp+70h+var_50]
0x18000c4c4  xor     rcx, rsp; StackCookie
0x18000c4c7  call    __security_check_cookie
0x18000c4cc  add     rsp, 150h
0x18000c4d3  pop     r15
0x18000c4d5  pop     r14
0x18000c4d7  pop     rdi
0x18000c4d8  pop     rbx
0x18000c4d9  pop     rbp
0x18000c4da  retn
0x18000c4db  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4e2  lea     rdi, WPP_GLOBAL_Control
0x18000c4e9  cmp     rcx, rdi
0x18000c4ec  jz      loc_18000C727
0x18000c4f2  test    byte ptr [rcx+1Ch], 1
0x18000c4f6  jz      loc_18000C727
0x18000c4fc  mov     dword ptr [rsp+170h+pbOutput], 280h
0x18000c504  lea     rdi, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c50b  mov     qword ptr [rsp+170h+cbIV], rdi
0x18000c510  mov     dword ptr [rsp+170h+pbIV], eax
0x18000c514  mov     rcx, [rcx+10h]
0x18000c518  lea     r9, aStatus; "Status"
0x18000c51f  call    WPP_SF_sDsd
0x18000c524  mov     r9d, 770h
0x18000c52a  lea     rdx, aStatus; "Status"
0x18000c531  mov     r8, rdi
0x18000c534  mov     ecx, ebx
0x18000c536  call    DebugTraceError
0x18000c53b  jmp     loc_18000C4A6
0x18000c540  lea     eax, [rsi-1]
0x18000c543  mov     ecx, r9d
0x18000c546  movzx   edx, al; Val
0x18000c549  mov     eax, r10d
0x18000c54c  add     rax, r14
0x18000c54f  mov     r8d, esi; Size
0x18000c552  add     rcx, rax
0x18000c555  add     rcx, rdi; void *
0x18000c558  call    memset
0x18000c55d  mov     rax, qword ptr [rbp+70h+var_60]
0x18000c561  cmp     dword ptr [rax+28h], 0
0x18000c565  jz      loc_18000CBC6
0x18000c56b  xor     ecx, ecx
0x18000c56d  mov     [rsp+170h+var_110], rcx
0x18000c572  test    r13d, r13d
0x18000c575  jz      short loc_18000C5C8
0x18000c577  mov     rdx, [r15+28h]; pbBuffer
0x18000c57b  test    rdx, rdx
0x18000c57e  jz      loc_18000C8F8
0x18000c584  mov     ecx, [r15+30h]
0x18000c588  cmp     ecx, r13d
0x18000c58b  jb      loc_18000C8F8
0x18000c591  mov     r8d, [r15+34h]
0x18000c595  lea     eax, [r8+r13]
0x18000c599  cmp     eax, ecx
0x18000c59b  ja      loc_18000C93F
0x18000c5a1  mov     edx, r8d
0x18000c5a4  lea     eax, [r8+r13]
0x18000c5a8  add     rdx, [r15+28h]; Src
0x18000c5ac  mov     ecx, r12d
0x18000c5af  mov     r8d, r13d; Size
0x18000c5b2  add     rcx, r14; void *
0x18000c5b5  mov     [rsp+170h+var_110], rdx
0x18000c5ba  mov     [r15+34h], eax
0x18000c5be  call    memmove
0x18000c5c3  mov     rcx, [rsp+170h+var_110]
0x18000c5c8  cmp     dword ptr [rsp+170h+Size], 0
0x18000c5cd  jz      loc_18000CA9C
0x18000c5d3  mov     edi, [rsp+170h+cbInput]
0x18000c5d7  lea     rax, [rsp+170h+Size+4]
0x18000c5dc  mov     rdx, [rsp+170h+pbInput]; pbInput
0x18000c5e1  xor     r9d, r9d; pPaddingInfo
0x18000c5e4  mov     [rsp+170h+dwFlags], 0; dwFlags
0x18000c5ec  mov     r8d, edi; cbInput
0x18000c5ef  mov     [rsp+170h+pcbResult], rax; pcbResult
0x18000c5f4  mov     [rsp+170h+cbOutput], edi; cbOutput
0x18000c5f8  mov     [rsp+170h+pbOutput], rbx; pbOutput
0x18000c5fd  mov     [rsp+170h+cbIV], r13d; cbIV
0x18000c602  mov     [rsp+170h+pbIV], rcx; pbIV
0x18000c607  mov     rcx, [r15+20h]; hKey
0x18000c60b  call    cs:__imp_BCryptEncrypt
0x18000c611  mov     ebx, eax
0x18000c613  test    eax, eax
0x18000c615  jns     loc_18000C7E5
0x18000c61b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c622  lea     rdi, WPP_GLOBAL_Control
0x18000c629  cmp     rcx, rdi
0x18000c62c  jz      loc_18000C4A6
0x18000c632  test    byte ptr [rcx+1Ch], 1
0x18000c636  jz      loc_18000C4A6
0x18000c63c  mov     dword ptr [rsp+170h+pbOutput], 7ADh
0x18000c644  lea     rdi, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c64b  mov     qword ptr [rsp+170h+cbIV], rdi
0x18000c650  mov     dword ptr [rsp+170h+pbIV], eax
0x18000c654  jmp     loc_18000C6E6
0x18000c659  mov     r9d, [rsp+170h+var_120]
0x18000c65e  mov     r8d, r13d
0x18000c661  mov     edx, dword ptr [rsp+170h+Size]
0x18000c665  mov     dword ptr [rsp+170h+var_110], r8d
0x18000c66a  mov     r12d, edx
0x18000c66d  mov     [rsp+170h+var_120], r9d
0x18000c672  cmp     r10d, 1
0x18000c676  jbe     loc_18000C8BE
0x18000c67c  xor     edx, edx
0x18000c67e  lea     eax, [rdi+r9]
0x18000c682  div     r10d
0x18000c685  mov     esi, r10d
0x18000c688  sub     esi, edx
0x18000c68a  jmp     loc_18000C2AE
0x18000c68f  mov     r10d, [rsp+170h+var_114]
0x18000c694  cmp     r10d, 1
0x18000c698  jbe     short loc_18000C659
0x18000c69a  cmp     r10d, 10h
0x18000c69e  jbe     loc_18000C7FA
0x18000c6a4  mov     ebx, 8009002Dh
0x18000c6a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c6b0  lea     rdi, WPP_GLOBAL_Control
  ... truncated ...
```
