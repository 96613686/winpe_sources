# TlsEncryptPacket

- ea: `0x18004899c`
- end: `0x180048d2a`
- name: `TlsEncryptPacket`
- size: `910`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180010b30`

## callees

- `0x1800112d0`
- `0x18001155c`
- `0x1800123d0`
- `0x1800251d0`
- `0x18004899c`
- `0x180048d30`
- `0x18008ca78`
- `0x18008dae8`
- `0x18008dc2c`
- `0x1800a4232`
- `0x1800a4380`
- `0x1800a45c0`

## string_xrefs

- `0x180048a63`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800a8691`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
  void *v30; // rcx
  unsigned int v31; // edx
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
        v30 = *(void **)(a2 + 40);
        if ( v30 )
        {
          v31 = *(_DWORD *)(a2 + 48);
          if ( v31 >= cbIV )
          {
            v32 = *(_DWORD *)(a2 + 52);
            if ( v32 + cbIV > v31 )
            {
              if ( !(unsigned int)SystemPrng(v30) )
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
0x18004899c  mov     [rsp+arg_8], rbx
0x1800489a1  mov     qword ptr [rsp+arg_0], rcx
0x1800489a6  push    rbp
0x1800489a7  push    rsi
0x1800489a8  push    rdi
0x1800489a9  push    r12
0x1800489ab  push    r13
0x1800489ad  push    r14
0x1800489af  push    r15
0x1800489b1  sub     rsp, 90h
0x1800489b8  mov     r13d, r9d
0x1800489bb  mov     r14, r8
0x1800489be  mov     [rsp+0C8h+var_78], 0
0x1800489c6  mov     rbp, rdx
0x1800489c9  cmp     r9d, 4000h
0x1800489d0  ja      short loc_180048A32
0x1800489d2  mov     edi, [rdx+8]
0x1800489d5  mov     ebx, edi
0x1800489d7  mov     r8, [rdx+10h]
0x1800489db  shr     ebx, 8
0x1800489de  mov     dword ptr [rsp+0C8h+var_68], 0
0x1800489e6  mov     [rsp+0C8h+var_40], r8
0x1800489ee  cmp     bl, 0FEh
0x1800489f1  jz      loc_180048C39
0x1800489f7  mov     [rsp+0C8h+var_70], 5
0x1800489ff  mov     eax, [r8+44h]
0x180048a03  xor     r15d, r15d
0x180048a06  mov     ecx, [r8+24h]
0x180048a0a  mov     [rsp+0C8h+arg_18], eax
0x180048a11  mov     dword ptr [rsp+0C8h+Size+4], ecx
0x180048a15  lea     esi, [r15+1]
0x180048a19  cmp     edi, 302h
0x180048a1f  jnb     loc_180048B93
0x180048a25  cmp     ecx, esi
0x180048a27  ja      loc_1800A86A6
0x180048a2d  jmp     loc_1800A86C1
0x180048a32  mov     ebx, 80090027h
0x180048a37  mov     rcx, cs:WPP_GLOBAL_Control
0x180048a3e  lea     rax, WPP_GLOBAL_Control
0x180048a45  cmp     rcx, rax
0x180048a48  jz      loc_180048B75
0x180048a4e  mov     eax, [rcx+2Ch]
0x180048a51  mov     esi, 1
0x180048a56  test    sil, al
0x180048a59  jz      loc_180048B75
0x180048a5f  mov     rcx, [rcx+18h]
0x180048a63  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180048a6a  mov     dword ptr [rsp+0C8h+pbOutput], 679h
0x180048a72  lea     r9, aStatus; "Status"
0x180048a79  mov     qword ptr [rsp+0C8h+cbIV], r8
0x180048a7e  mov     dword ptr [rsp+0C8h+pbIV], 80090027h
0x180048a86  call    WPP_SF_sDsd
0x180048a8b  jmp     loc_180048B75
0x180048a90  mov     rcx, qword ptr [rsp+0C8h+arg_38]
0x180048a98  mov     rax, rcx
0x180048a9b  mov     [rdi+0Ah], cl
0x180048a9e  shr     rax, 38h
0x180048aa2  mov     [rdi+3], al
0x180048aa5  mov     rax, rcx
0x180048aa8  shr     rax, 30h
0x180048aac  mov     [rdi+4], al
0x180048aaf  mov     rax, rcx
0x180048ab2  shr     rax, 28h
0x180048ab6  mov     [rdi+5], al
0x180048ab9  mov     rax, rcx
0x180048abc  shr     rax, 20h
0x180048ac0  mov     [rdi+6], al
0x180048ac3  mov     rax, rcx
0x180048ac6  shr     rax, 18h
0x180048aca  mov     [rdi+7], al
0x180048acd  mov     rax, rcx
0x180048ad0  shr     rax, 10h
0x180048ad4  mov     [rdi+8], al
0x180048ad7  mov     rax, rcx
0x180048ada  shr     rax, 8
0x180048ade  mov     [rdi+9], al
0x180048ae1  mov     eax, edx
0x180048ae3  shr     eax, 8
0x180048ae6  mov     [rdi+0Bh], al
0x180048ae9  mov     [rdi+0Ch], dl
0x180048aec  lea     eax, [r8+r15]
0x180048af0  mov     rbx, r13
0x180048af3  lea     rcx, [rax+rdi]; void *
0x180048af7  mov     [rsp+0C8h+var_58], rax
0x180048afc  mov     [rsp+0C8h+var_50], rcx
0x180048b01  cmp     rcx, r14
0x180048b04  jnz     loc_180048C87
0x180048b0a  mov     [rsp+0C8h+var_74], esi
0x180048b0e  test    r9d, r9d
0x180048b11  jnz     loc_180048CBD
0x180048b17  cmp     dword ptr [rsp+0C8h+var_68], 0
0x180048b1c  jz      loc_1800A8741
0x180048b22  mov     eax, [rsp+0C8h+var_70]
0x180048b26  lea     ecx, [r12+r15]
0x180048b2a  mov     r8, qword ptr [rsp+0C8h+arg_38]
0x180048b32  add     ecx, r13d
0x180048b35  mov     edx, [rsp+0C8h+arg_40]
0x180048b3c  add     rax, rdi
0x180048b3f  mov     dword ptr [rsp+0C8h+pbOutput], ecx
0x180048b43  mov     r9, r14
0x180048b46  mov     qword ptr [rsp+0C8h+cbIV], rax
0x180048b4b  mov     rcx, rbp
0x180048b4e  mov     dword ptr [rsp+0C8h+pbIV], r13d
0x180048b53  call    Tls1AeadEncrypt
0x180048b58  mov     ebx, eax
0x180048b5a  test    eax, eax
0x180048b5c  js      loc_180048D15
0x180048b62  mov     rax, [rsp+0C8h+arg_30]
0x180048b6a  xor     ebx, ebx
0x180048b6c  mov     ecx, [rsp+0C8h+var_48]
0x180048b73  mov     [rax], ecx
0x180048b75  mov     eax, ebx
0x180048b77  mov     rbx, [rsp+0C8h+arg_8]
0x180048b7f  add     rsp, 90h
0x180048b86  pop     r15
0x180048b88  pop     r14
0x180048b8a  pop     r13
0x180048b8c  pop     r12
0x180048b8e  pop     rdi
0x180048b8f  pop     rsi
0x180048b90  pop     rbp
0x180048b91  retn
0x180048b93  mov     rcx, [r8+30h]; Str1
0x180048b97  lea     rdx, aChainingmodegc; "ChainingModeGCM"
0x180048b9e  call    wcscmp_0
0x180048ba3  test    eax, eax
0x180048ba5  jnz     loc_180048C52
0x180048bab  xor     r9d, r9d
0x180048bae  mov     dword ptr [rsp+0C8h+var_68], esi
0x180048bb2  mov     [rsp+0C8h+arg_18], r9d
0x180048bba  lea     r12d, [rax+10h]
0x180048bbe  lea     r15d, [rax+8]
0x180048bc2  mov     r8d, [rsp+0C8h+var_70]
0x180048bc7  lea     eax, [r12+r9]
0x180048bcb  mov     r10d, [rsp+0C8h+arg_28]
0x180048bd3  lea     edx, [r15+rax]
0x180048bd7  add     edx, r13d
0x180048bda  mov     dword ptr [rsp+0C8h+Size], eax
0x180048bde  lea     eax, [rdx+r8]
0x180048be2  mov     [rsp+0C8h+var_48], eax
0x180048be9  cmp     r10d, eax
0x180048bec  jb      loc_180048D20
0x180048bf2  cmp     r10d, r8d
0x180048bf5  jb      loc_180048D20
0x180048bfb  cmp     bl, 0FEh
0x180048bfe  jz      short loc_180048C78
0x180048c00  xor     ecx, ecx
0x180048c02  mov     rdi, [rsp+0C8h+arg_20]
0x180048c0a  mov     r11d, [rsp+0C8h+arg_40]
0x180048c12  mov     [rdi], r11b
0x180048c15  mov     al, [rbp+9]
0x180048c18  mov     [rdi+1], al
0x180048c1b  mov     al, [rbp+8]
0x180048c1e  mov     [rdi+2], al
0x180048c21  test    ecx, ecx
0x180048c23  jnz     loc_180048A90
0x180048c29  mov     eax, edx
0x180048c2b  mov     [rdi+4], dl
0x180048c2e  shr     eax, 8
0x180048c31  mov     [rdi+3], al
0x180048c34  jmp     loc_180048AEC
0x180048c39  mov     [rsp+0C8h+var_70], 0Dh
0x180048c41  cmp     edi, 0FEFFh
0x180048c47  jbe     loc_1800489FF
0x180048c4d  jmp     loc_1800489F7
0x180048c52  mov     ecx, dword ptr [rsp+0C8h+Size+4]
0x180048c56  cmp     ecx, esi
0x180048c58  jbe     loc_1800A86C1
0x180048c5e  mov     r12d, 10h
0x180048c64  cmp     ecx, r12d
0x180048c67  jbe     loc_1800A86A3
0x180048c6d  mov     r9d, 6BDh
0x180048c73  jmp     loc_1800A866E
0x180048c78  cmp     edi, 0FEFFh
0x180048c7e  ja      short loc_180048C00
0x180048c80  mov     ecx, esi
0x180048c82  jmp     loc_180048C02
0x180048c87  lea     rax, [rdi+r8]
0x180048c8b  cmp     rax, r14
0x180048c8e  jnz     loc_1800A86D1
0x180048c94  mov     r8, rbx; Size
0x180048c97  mov     rdx, r14; Src
0x180048c9a  call    memmove
0x180048c9f  mov     r9d, [rsp+0C8h+arg_18]
0x180048ca7  mov     r11d, [rsp+0C8h+arg_40]
0x180048caf  mov     r14, [rsp+0C8h+var_50]
0x180048cb4  mov     [rsp+0C8h+var_74], esi
0x180048cb8  jmp     loc_1800A8707
0x180048cbd  mov     [rsp+0C8h+cbOutput], r9d; cbOutput
0x180048cc2  lea     rcx, [rax+r13]
0x180048cc6  mov     r9, qword ptr [rsp+0C8h+arg_38]; int
0x180048cce  add     rcx, rdi
0x180048cd1  cmp     dword ptr [rbp+8], 300h
0x180048cd8  mov     r8d, r11d; int
0x180048cdb  mov     [rsp+0C8h+pbOutput], rcx; pbOutput
0x180048ce0  mov     rdx, rbp; int
0x180048ce3  mov     rcx, qword ptr [rsp+0C8h+arg_0]; int
0x180048ceb  mov     [rsp+0C8h+cbIV], r13d; cbInput
0x180048cf0  mov     [rsp+0C8h+pbIV], r14; PUCHAR
0x180048cf5  jnz     loc_1800A871E
0x180048cfb  call    Ssl3ComputeMac
0x180048d00  mov     ebx, eax
0x180048d02  test    eax, eax
0x180048d04  jns     loc_1800A8731
0x180048d0a  mov     r9d, 740h
0x180048d10  jmp     loc_1800A8717
0x180048d15  mov     r9d, 770h
0x180048d1b  jmp     loc_1800A8717
0x180048d20  mov     ebx, 80090028h
0x180048d25  jmp     loc_180048B75
0x1800a8668  mov     r9d, 77Fh
0x1800a866e  mov     ebx, 8009002Dh
0x1800a8673  mov     ecx, 8009002Dh
0x1800a8678  jmp     short loc_1800A868A
0x1800a867a  mov     r9d, 7B4h
0x1800a8680  mov     ebx, 80090020h
0x1800a8685  mov     ecx, 80090020h
0x1800a868a  lea     rdx, aStatus; "Status"
0x1800a8691  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a8698  call    DebugTraceError
0x1800a869d  nop
0x1800a869e  jmp     loc_180048B75
0x1800a86a3  mov     r15d, ecx
0x1800a86a6  mov     r9d, [rsp+0C8h+arg_18]
0x1800a86ae  xor     edx, edx
0x1800a86b0  mov     r12d, ecx
0x1800a86b3  lea     eax, [r9+r13]
0x1800a86b7  div     ecx
0x1800a86b9  sub     r12d, edx
0x1800a86bc  jmp     loc_180048BC2
0x1800a86c1  mov     r9d, [rsp+0C8h+arg_18]
0x1800a86c9  xor     r12d, r12d
0x1800a86cc  jmp     loc_180048BC2
0x1800a86d1  cmp     r14, rdi
0x1800a86d4  ja      short loc_1800A86E4
0x1800a86d6  lea     rax, [r14+r13]
0x1800a86da  cmp     rdi, rax
0x1800a86dd  jb      short loc_1800A86ED
0x1800a86df  cmp     r14, rdi
0x1800a86e2  jb      short loc_1800A86FF
0x1800a86e4  lea     rax, [rdi+r10]
0x1800a86e8  cmp     r14, rax
0x1800a86eb  jnb     short loc_1800A86FF
0x1800a86ed  mov     ebx, 8009002Bh
0x1800a86f2  mov     r9d, 725h
0x1800a86f8  mov     ecx, 8009002Bh
0x1800a86fd  jmp     short loc_1800A868A
0x1800a86ff  mov     [rsp+0C8h+var_74], 0
0x1800a8707  mov     rax, [rsp+0C8h+var_58]
0x1800a870c  jmp     loc_180048B0E
0x1800a8711  mov     r9d, 7EFh
0x1800a8717  mov     ecx, eax
0x1800a8719  jmp     loc_1800A868A
0x1800a871e  call    Tls1ComputeMac
0x1800a8723  mov     ebx, eax
0x1800a8725  test    eax, eax
0x1800a8727  jns     short loc_1800A8731
0x1800a8729  mov     r9d, 751h
0x1800a872f  jmp     short loc_1800A8717
0x1800a8731  mov     r9d, [rsp+0C8h+arg_18]
0x1800a8739  mov     rbx, r13
0x1800a873c  jmp     loc_180048B17
0x1800a8741  mov     ecx, r9d
0x1800a8744  mov     al, r12b
0x1800a8747  add     rcx, rbx
0x1800a874a  mov     r8d, r12d; Size
0x1800a874d  add     rcx, [rsp+0C8h+var_58]
0x1800a8752  sub     al, sil
0x1800a8755  add     rcx, rdi; void *
0x1800a8758  movzx   edx, al; Val
0x1800a875b  call    memset
0x1800a8760  mov     rax, [rsp+0C8h+var_40]
0x1800a8768  cmp     dword ptr [rax+28h], 0
0x1800a876c  jz      loc_1800A896B
0x1800a8772  xor     ebx, ebx
0x1800a8774  mov     [rsp+0C8h+var_68], rbx
0x1800a8779  test    r15d, r15d
0x1800a877c  jz      loc_1800A8806
0x1800a8782  mov     rcx, [rbp+28h]; void *
0x1800a8786  test    rcx, rcx
0x1800a8789  jz      loc_1800A8668
0x1800a878f  mov     edx, [rbp+30h]
0x1800a8792  cmp     edx, r15d
0x1800a8795  jb      loc_1800A8668
0x1800a879b  mov     r8d, [rbp+34h]
0x1800a879f  lea     eax, [r8+r15]
0x1800a87a3  cmp     eax, edx
0x1800a87a5  jbe     short loc_1800A87E1
0x1800a87a7  call    SystemPrng
0x1800a87ac  test    eax, eax
0x1800a87ae  jnz     short loc_1800A87DE
0x1800a87b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a87b7  lea     rax, WPP_GLOBAL_Control
0x1800a87be  cmp     rcx, rax
0x1800a87c1  jz      short loc_1800A87D4
0x1800a87c3  mov     eax, [rcx+2Ch]
0x1800a87c6  test    sil, al
0x1800a87c9  jz      short loc_1800A87D4
0x1800a87cb  mov     rcx, [rcx+18h]
0x1800a87cf  call    WPP_SF_ss
  ... truncated ...
```
