# TlsEncryptPacket

- ea: `0x18003f56c`
- end: `0x18003f8fa`
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
- `0x180018150`
- `0x18003f56c`
- `0x18003f900`
- `0x180083878`
- `0x1800848e8`
- `0x180084a2c`
- `0x18009f616`
- `0x18009f780`
- `0x18009fa80`

## string_xrefs

- `0x18003f633`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800a3723`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
0x18003f56c  mov     [rsp+arg_8], rbx
0x18003f571  mov     qword ptr [rsp+arg_0], rcx
0x18003f576  push    rbp
0x18003f577  push    rsi
0x18003f578  push    rdi
0x18003f579  push    r12
0x18003f57b  push    r13
0x18003f57d  push    r14
0x18003f57f  push    r15
0x18003f581  sub     rsp, 90h
0x18003f588  mov     r13d, r9d
0x18003f58b  mov     r14, r8
0x18003f58e  mov     [rsp+0C8h+var_78], 0
0x18003f596  mov     rbp, rdx
0x18003f599  cmp     r9d, 4000h
0x18003f5a0  ja      short loc_18003F602
0x18003f5a2  mov     edi, [rdx+8]
0x18003f5a5  mov     ebx, edi
0x18003f5a7  mov     r8, [rdx+10h]
0x18003f5ab  shr     ebx, 8
0x18003f5ae  mov     dword ptr [rsp+0C8h+var_68], 0
0x18003f5b6  mov     [rsp+0C8h+var_40], r8
0x18003f5be  cmp     bl, 0FEh
0x18003f5c1  jz      loc_18003F809
0x18003f5c7  mov     [rsp+0C8h+var_70], 5
0x18003f5cf  mov     eax, [r8+44h]
0x18003f5d3  xor     r15d, r15d
0x18003f5d6  mov     ecx, [r8+24h]
0x18003f5da  mov     [rsp+0C8h+arg_18], eax
0x18003f5e1  mov     dword ptr [rsp+0C8h+Size+4], ecx
0x18003f5e5  lea     esi, [r15+1]
0x18003f5e9  cmp     edi, 302h
0x18003f5ef  jnb     loc_18003F763
0x18003f5f5  cmp     ecx, esi
0x18003f5f7  ja      loc_1800A3738
0x18003f5fd  jmp     loc_1800A3753
0x18003f602  mov     ebx, 80090027h
0x18003f607  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f60e  lea     rax, WPP_GLOBAL_Control
0x18003f615  cmp     rcx, rax
0x18003f618  jz      loc_18003F745
0x18003f61e  mov     eax, [rcx+2Ch]
0x18003f621  mov     esi, 1
0x18003f626  test    sil, al
0x18003f629  jz      loc_18003F745
0x18003f62f  mov     rcx, [rcx+18h]
0x18003f633  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f63a  mov     dword ptr [rsp+0C8h+pbOutput], 679h
0x18003f642  lea     r9, aStatus; "Status"
0x18003f649  mov     qword ptr [rsp+0C8h+cbIV], r8
0x18003f64e  mov     dword ptr [rsp+0C8h+pbIV], 80090027h
0x18003f656  call    WPP_SF_sDsd
0x18003f65b  jmp     loc_18003F745
0x18003f660  mov     rcx, qword ptr [rsp+0C8h+arg_38]
0x18003f668  mov     rax, rcx
0x18003f66b  mov     [rdi+0Ah], cl
0x18003f66e  shr     rax, 38h
0x18003f672  mov     [rdi+3], al
0x18003f675  mov     rax, rcx
0x18003f678  shr     rax, 30h
0x18003f67c  mov     [rdi+4], al
0x18003f67f  mov     rax, rcx
0x18003f682  shr     rax, 28h
0x18003f686  mov     [rdi+5], al
0x18003f689  mov     rax, rcx
0x18003f68c  shr     rax, 20h
0x18003f690  mov     [rdi+6], al
0x18003f693  mov     rax, rcx
0x18003f696  shr     rax, 18h
0x18003f69a  mov     [rdi+7], al
0x18003f69d  mov     rax, rcx
0x18003f6a0  shr     rax, 10h
0x18003f6a4  mov     [rdi+8], al
0x18003f6a7  mov     rax, rcx
0x18003f6aa  shr     rax, 8
0x18003f6ae  mov     [rdi+9], al
0x18003f6b1  mov     eax, edx
0x18003f6b3  shr     eax, 8
0x18003f6b6  mov     [rdi+0Bh], al
0x18003f6b9  mov     [rdi+0Ch], dl
0x18003f6bc  lea     eax, [r8+r15]
0x18003f6c0  mov     rbx, r13
0x18003f6c3  lea     rcx, [rax+rdi]; void *
0x18003f6c7  mov     [rsp+0C8h+var_58], rax
0x18003f6cc  mov     [rsp+0C8h+var_50], rcx
0x18003f6d1  cmp     rcx, r14
0x18003f6d4  jnz     loc_18003F857
0x18003f6da  mov     [rsp+0C8h+var_74], esi
0x18003f6de  test    r9d, r9d
0x18003f6e1  jnz     loc_18003F88D
0x18003f6e7  cmp     dword ptr [rsp+0C8h+var_68], 0
0x18003f6ec  jz      loc_1800A37D3
0x18003f6f2  mov     eax, [rsp+0C8h+var_70]
0x18003f6f6  lea     ecx, [r12+r15]
0x18003f6fa  mov     r8, qword ptr [rsp+0C8h+arg_38]
0x18003f702  add     ecx, r13d
0x18003f705  mov     edx, [rsp+0C8h+arg_40]
0x18003f70c  add     rax, rdi
0x18003f70f  mov     dword ptr [rsp+0C8h+pbOutput], ecx
0x18003f713  mov     r9, r14
0x18003f716  mov     qword ptr [rsp+0C8h+cbIV], rax
0x18003f71b  mov     rcx, rbp
0x18003f71e  mov     dword ptr [rsp+0C8h+pbIV], r13d
0x18003f723  call    Tls1AeadEncrypt
0x18003f728  mov     ebx, eax
0x18003f72a  test    eax, eax
0x18003f72c  js      loc_18003F8E5
0x18003f732  mov     rax, [rsp+0C8h+arg_30]
0x18003f73a  xor     ebx, ebx
0x18003f73c  mov     ecx, [rsp+0C8h+var_48]
0x18003f743  mov     [rax], ecx
0x18003f745  mov     eax, ebx
0x18003f747  mov     rbx, [rsp+0C8h+arg_8]
0x18003f74f  add     rsp, 90h
0x18003f756  pop     r15
0x18003f758  pop     r14
0x18003f75a  pop     r13
0x18003f75c  pop     r12
0x18003f75e  pop     rdi
0x18003f75f  pop     rsi
0x18003f760  pop     rbp
0x18003f761  retn
0x18003f763  mov     rcx, [r8+30h]; Str1
0x18003f767  lea     rdx, aChainingmodegc; "ChainingModeGCM"
0x18003f76e  call    wcscmp_0
0x18003f773  test    eax, eax
0x18003f775  jnz     loc_18003F822
0x18003f77b  xor     r9d, r9d
0x18003f77e  mov     dword ptr [rsp+0C8h+var_68], esi
0x18003f782  mov     [rsp+0C8h+arg_18], r9d
0x18003f78a  lea     r12d, [rax+10h]
0x18003f78e  lea     r15d, [rax+8]
0x18003f792  mov     r8d, [rsp+0C8h+var_70]
0x18003f797  lea     eax, [r12+r9]
0x18003f79b  mov     r10d, [rsp+0C8h+arg_28]
0x18003f7a3  lea     edx, [r15+rax]
0x18003f7a7  add     edx, r13d
0x18003f7aa  mov     dword ptr [rsp+0C8h+Size], eax
0x18003f7ae  lea     eax, [rdx+r8]
0x18003f7b2  mov     [rsp+0C8h+var_48], eax
0x18003f7b9  cmp     r10d, eax
0x18003f7bc  jb      loc_18003F8F0
0x18003f7c2  cmp     r10d, r8d
0x18003f7c5  jb      loc_18003F8F0
0x18003f7cb  cmp     bl, 0FEh
0x18003f7ce  jz      short loc_18003F848
0x18003f7d0  xor     ecx, ecx
0x18003f7d2  mov     rdi, [rsp+0C8h+arg_20]
0x18003f7da  mov     r11d, [rsp+0C8h+arg_40]
0x18003f7e2  mov     [rdi], r11b
0x18003f7e5  mov     al, [rbp+9]
0x18003f7e8  mov     [rdi+1], al
0x18003f7eb  mov     al, [rbp+8]
0x18003f7ee  mov     [rdi+2], al
0x18003f7f1  test    ecx, ecx
0x18003f7f3  jnz     loc_18003F660
0x18003f7f9  mov     eax, edx
0x18003f7fb  mov     [rdi+4], dl
0x18003f7fe  shr     eax, 8
0x18003f801  mov     [rdi+3], al
0x18003f804  jmp     loc_18003F6BC
0x18003f809  mov     [rsp+0C8h+var_70], 0Dh
0x18003f811  cmp     edi, 0FEFFh
0x18003f817  jbe     loc_18003F5CF
0x18003f81d  jmp     loc_18003F5C7
0x18003f822  mov     ecx, dword ptr [rsp+0C8h+Size+4]
0x18003f826  cmp     ecx, esi
0x18003f828  jbe     loc_1800A3753
0x18003f82e  mov     r12d, 10h
0x18003f834  cmp     ecx, r12d
0x18003f837  jbe     loc_1800A3735
0x18003f83d  mov     r9d, 6BDh
0x18003f843  jmp     loc_1800A3700
0x18003f848  cmp     edi, 0FEFFh
0x18003f84e  ja      short loc_18003F7D0
0x18003f850  mov     ecx, esi
0x18003f852  jmp     loc_18003F7D2
0x18003f857  lea     rax, [rdi+r8]
0x18003f85b  cmp     rax, r14
0x18003f85e  jnz     loc_1800A3763
0x18003f864  mov     r8, rbx; Size
0x18003f867  mov     rdx, r14; Src
0x18003f86a  call    memmove
0x18003f86f  mov     r9d, [rsp+0C8h+arg_18]
0x18003f877  mov     r11d, [rsp+0C8h+arg_40]
0x18003f87f  mov     r14, [rsp+0C8h+var_50]
0x18003f884  mov     [rsp+0C8h+var_74], esi
0x18003f888  jmp     loc_1800A3799
0x18003f88d  mov     [rsp+0C8h+cbOutput], r9d; cbOutput
0x18003f892  lea     rcx, [rax+r13]
0x18003f896  mov     r9, qword ptr [rsp+0C8h+arg_38]; int
0x18003f89e  add     rcx, rdi
0x18003f8a1  cmp     dword ptr [rbp+8], 300h
0x18003f8a8  mov     r8d, r11d; int
0x18003f8ab  mov     [rsp+0C8h+pbOutput], rcx; pbOutput
0x18003f8b0  mov     rdx, rbp; int
0x18003f8b3  mov     rcx, qword ptr [rsp+0C8h+arg_0]; int
0x18003f8bb  mov     [rsp+0C8h+cbIV], r13d; cbInput
0x18003f8c0  mov     [rsp+0C8h+pbIV], r14; PUCHAR
0x18003f8c5  jnz     loc_1800A37B0
0x18003f8cb  call    Ssl3ComputeMac
0x18003f8d0  mov     ebx, eax
0x18003f8d2  test    eax, eax
0x18003f8d4  jns     loc_1800A37C3
0x18003f8da  mov     r9d, 740h
0x18003f8e0  jmp     loc_1800A37A9
0x18003f8e5  mov     r9d, 770h
0x18003f8eb  jmp     loc_1800A37A9
0x18003f8f0  mov     ebx, 80090028h
0x18003f8f5  jmp     loc_18003F745
0x1800a36fa  mov     r9d, 77Fh
0x1800a3700  mov     ebx, 8009002Dh
0x1800a3705  mov     ecx, 8009002Dh
0x1800a370a  jmp     short loc_1800A371C
0x1800a370c  mov     r9d, 7B4h
0x1800a3712  mov     ebx, 80090020h
0x1800a3717  mov     ecx, 80090020h
0x1800a371c  lea     rdx, aStatus; "Status"
0x1800a3723  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a372a  call    DebugTraceError
0x1800a372f  nop
0x1800a3730  jmp     loc_18003F745
0x1800a3735  mov     r15d, ecx
0x1800a3738  mov     r9d, [rsp+0C8h+arg_18]
0x1800a3740  xor     edx, edx
0x1800a3742  mov     r12d, ecx
0x1800a3745  lea     eax, [r9+r13]
0x1800a3749  div     ecx
0x1800a374b  sub     r12d, edx
0x1800a374e  jmp     loc_18003F792
0x1800a3753  mov     r9d, [rsp+0C8h+arg_18]
0x1800a375b  xor     r12d, r12d
0x1800a375e  jmp     loc_18003F792
0x1800a3763  cmp     r14, rdi
0x1800a3766  ja      short loc_1800A3776
0x1800a3768  lea     rax, [r14+r13]
0x1800a376c  cmp     rdi, rax
0x1800a376f  jb      short loc_1800A377F
0x1800a3771  cmp     r14, rdi
0x1800a3774  jb      short loc_1800A3791
0x1800a3776  lea     rax, [rdi+r10]
0x1800a377a  cmp     r14, rax
0x1800a377d  jnb     short loc_1800A3791
0x1800a377f  mov     ebx, 8009002Bh
0x1800a3784  mov     r9d, 725h
0x1800a378a  mov     ecx, 8009002Bh
0x1800a378f  jmp     short loc_1800A371C
0x1800a3791  mov     [rsp+0C8h+var_74], 0
0x1800a3799  mov     rax, [rsp+0C8h+var_58]
0x1800a379e  jmp     loc_18003F6DE
0x1800a37a3  mov     r9d, 7EFh
0x1800a37a9  mov     ecx, eax
0x1800a37ab  jmp     loc_1800A371C
0x1800a37b0  call    Tls1ComputeMac
0x1800a37b5  mov     ebx, eax
0x1800a37b7  test    eax, eax
0x1800a37b9  jns     short loc_1800A37C3
0x1800a37bb  mov     r9d, 751h
0x1800a37c1  jmp     short loc_1800A37A9
0x1800a37c3  mov     r9d, [rsp+0C8h+arg_18]
0x1800a37cb  mov     rbx, r13
0x1800a37ce  jmp     loc_18003F6E7
0x1800a37d3  mov     ecx, r9d
0x1800a37d6  mov     al, r12b
0x1800a37d9  add     rcx, rbx
0x1800a37dc  mov     r8d, r12d; Size
0x1800a37df  add     rcx, [rsp+0C8h+var_58]
0x1800a37e4  sub     al, sil
0x1800a37e7  add     rcx, rdi; void *
0x1800a37ea  movzx   edx, al; Val
0x1800a37ed  call    memset
0x1800a37f2  mov     rax, [rsp+0C8h+var_40]
0x1800a37fa  cmp     dword ptr [rax+28h], 0
0x1800a37fe  jz      loc_1800A39FD
0x1800a3804  xor     ebx, ebx
0x1800a3806  mov     [rsp+0C8h+var_68], rbx
0x1800a380b  test    r15d, r15d
0x1800a380e  jz      loc_1800A3898
0x1800a3814  mov     rcx, [rbp+28h]; void *
0x1800a3818  test    rcx, rcx
0x1800a381b  jz      loc_1800A36FA
0x1800a3821  mov     edx, [rbp+30h]
0x1800a3824  cmp     edx, r15d
0x1800a3827  jb      loc_1800A36FA
0x1800a382d  mov     r8d, [rbp+34h]
0x1800a3831  lea     eax, [r8+r15]
0x1800a3835  cmp     eax, edx
0x1800a3837  jbe     short loc_1800A3873
0x1800a3839  call    SystemPrng
0x1800a383e  test    eax, eax
0x1800a3840  jnz     short loc_1800A3870
0x1800a3842  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a3849  lea     rax, WPP_GLOBAL_Control
0x1800a3850  cmp     rcx, rax
0x1800a3853  jz      short loc_1800A3866
0x1800a3855  mov     eax, [rcx+2Ch]
0x1800a3858  test    sil, al
0x1800a385b  jz      short loc_1800A3866
0x1800a385d  mov     rcx, [rcx+18h]
0x1800a3861  call    WPP_SF_ss
  ... truncated ...
```
