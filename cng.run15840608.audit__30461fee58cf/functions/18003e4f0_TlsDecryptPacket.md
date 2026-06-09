# TlsDecryptPacket

- ea: `0x18003e4f0`
- end: `0x18003e9d4`
- name: `TlsDecryptPacket`
- size: `1252`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8 *, unsigned int, PUCHAR, ULONG, ULONG *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180007490`

## callees

- `0x18000743c`
- `0x180007b60`
- `0x1800082b0`
- `0x18003e4f0`
- `0x18003ef90`
- `0x180082888`
- `0x180082a40`
- `0x180083a3c`
- `0x18009d746`
- `0x18009d820`
- `0x18009da40`

## string_xrefs

- `0x18003e7dd`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18003e851`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800a1753`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800a17dc`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsDecryptPacket(
        __int64 a1,
        __int64 a2,
        unsigned __int8 *a3,
        unsigned int a4,
        PUCHAR a5,
        ULONG a6,
        ULONG *a7,
        int a8)
{
  unsigned int v8; // ebx
  unsigned __int8 *v9; // rdi
  UCHAR *pbOutput; // r14
  int v11; // r10d
  __int64 v12; // rsi
  ULONG cbIV; // r15d
  __int64 v14; // r9
  ULONG v15; // r12d
  int v16; // ecx
  int v17; // ebx
  int v18; // eax
  unsigned int v19; // ebx
  unsigned int v20; // ecx
  ULONG v21; // edx
  ULONG v22; // ebx
  PUCHAR v23; // r13
  PUCHAR v24; // r11
  ULONG cbOutput; // esi
  int v26; // ecx
  int v27; // edx
  int v28; // r12d
  int v29; // eax
  unsigned int v30; // ebx
  __int64 v31; // rcx
  ULONG v32; // esi
  bool v33; // zf
  UCHAR *pbIV; // rdi
  NTSTATUS v36; // eax
  __int64 v37; // rcx
  unsigned int v38; // r9d
  int v39; // eax
  __int64 v40; // r9
  int v41; // eax
  __int64 v42; // r9
  __int64 v43; // rcx
  unsigned int v44; // eax
  ULONG v45; // eax
  int v46; // eax
  int v47; // eax
  char v48; // r8
  __int64 v49; // rdx
  UCHAR v50; // cl
  UCHAR v51; // al
  ULONG cbInput; // [rsp+50h] [rbp-89h] BYREF
  int v53; // [rsp+54h] [rbp-85h]
  int v54[2]; // [rsp+58h] [rbp-81h]
  int v55; // [rsp+60h] [rbp-79h]
  ULONG v56; // [rsp+64h] [rbp-75h]
  int v57; // [rsp+68h] [rbp-71h]
  __int64 v58; // [rsp+70h] [rbp-69h]
  int v59[2]; // [rsp+78h] [rbp-61h]
  void *Src; // [rsp+80h] [rbp-59h]
  ULONG *v61; // [rsp+88h] [rbp-51h]
  UCHAR v62[16]; // [rsp+90h] [rbp-49h] BYREF
  UCHAR v63[48]; // [rsp+A0h] [rbp-39h] BYREF

  v8 = *(_DWORD *)(a2 + 8);
  v9 = a3;
  pbOutput = a5;
  v11 = a2;
  v12 = a4;
  cbIV = 0;
  v14 = *(_QWORD *)(a2 + 16);
  cbInput = 0;
  *(_QWORD *)v54 = a2;
  *(_QWORD *)v59 = a1;
  v15 = *(_DWORD *)(v14 + 68);
  v56 = v15;
  v61 = a7;
  v55 = 0;
  v58 = v14;
  if ( v8 >= 0x302 )
  {
    v41 = wcscmp_0(*(const wchar_t **)(v14 + 48), L"ChainingModeGCM");
    v14 = v58;
    if ( v41 )
    {
      v44 = *(_DWORD *)(v58 + 36);
      if ( v44 > 1 )
      {
        if ( v44 > 0x10 )
        {
          v30 = -2146893779;
          v42 = 2137;
          v43 = 2148073517LL;
          goto LABEL_75;
        }
        cbIV = *(_DWORD *)(v58 + 36);
      }
    }
    else
    {
      v15 = 0;
      v56 = 0;
      cbIV = 8;
      v55 = 1;
    }
    v11 = v54[0];
  }
  if ( BYTE1(v8) != 0xFE || (v16 = 1, v8 > 0xFEFF) )
    v16 = 0;
  if ( !v9 )
    goto LABEL_42;
  if ( (unsigned int)v12 < 5 )
    goto LABEL_42;
  LODWORD(a2) = v9[1];
  if ( ((_BYTE)a2 == 0xFE) != v16 )
    goto LABEL_42;
  LODWORD(a3) = 13;
  if ( v16 )
  {
    if ( (unsigned int)v12 < 0xD )
    {
LABEL_42:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          a2,
          (_DWORD)a3,
          (unsigned int)"NTE_BAD_DATA",
          5,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          105);
      return (unsigned int)-2146893819;
    }
    v17 = v9[11];
    v18 = v9[12];
  }
  else
  {
    v17 = v9[3];
    v18 = v9[4];
  }
  v19 = v18 | (v17 << 8);
  if ( v19 < v15 + cbIV )
    goto LABEL_42;
  v20 = v9[2] | ((_DWORD)a2 << 8);
  if ( (_BYTE)a2 != 0xFE || v20 > 0xFEFF )
    LODWORD(a3) = 5;
  v21 = (_DWORD)a3 + cbIV;
  if ( (unsigned int)v12 < (unsigned int)a3 + cbIV )
  {
    v30 = -2146893819;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v21,
        (_DWORD)a3,
        (unsigned int)"Status",
        5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        121);
  }
  else
  {
    if ( v20 - 768 > 3 && v20 != 65277 && v20 != 65279 )
    {
      v42 = 2181;
LABEL_58:
      v30 = -2146893819;
      v43 = 2148073477LL;
LABEL_75:
      DebugTraceError(v43, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v42);
      return v30;
    }
    v22 = v19 - cbIV;
    cbInput = v22;
    if ( v22 + v21 == (_DWORD)v12 )
    {
      v57 = 0;
      v23 = &v9[(unsigned int)a3];
      v24 = &v9[v21];
      Src = v24;
      if ( v24 == a5 )
      {
        cbOutput = a6;
        v26 = 1;
      }
      else if ( v23 == a5 )
      {
        if ( a6 < cbIV )
        {
          v42 = 2219;
          goto LABEL_58;
        }
        v26 = 1;
        v57 = 1;
        pbOutput = &a5[cbIV];
        cbOutput = a6 - cbIV;
      }
      else
      {
        if ( a5 >= v9 && a5 < &v9[v12] || (cbOutput = a6, v9 >= a5) && v9 < &a5[a6] )
        {
          v30 = -2146893781;
          v42 = 2232;
          v43 = 2148073515LL;
          goto LABEL_75;
        }
        v26 = 0;
      }
      v27 = *v9;
      v28 = 0;
      v53 = v27;
      if ( v55 )
      {
        v29 = Tls1AeadDecrypt(v11, v27, a8, (int)v23, v22 + cbIV, (__int64)pbOutput, cbOutput, &cbInput);
        v30 = v29;
        if ( v29 < 0 )
        {
          v42 = 2257;
          v43 = (unsigned int)v29;
          goto LABEL_75;
        }
      }
      else if ( *(_DWORD *)(v14 + 40) )
      {
        pbIV = 0;
        if ( cbIV )
        {
          pbIV = v62;
          memmove(v62, v23, cbIV);
          v14 = v58;
          v24 = (PUCHAR)Src;
        }
        if ( v22 % *(_DWORD *)(v14 + 36) )
        {
          v42 = 2299;
          goto LABEL_58;
        }
        v36 = BCryptDecrypt(
                *(BCRYPT_KEY_HANDLE *)(*(_QWORD *)v54 + 32LL),
                v24,
                v22,
                0,
                pbIV,
                cbIV,
                pbOutput,
                cbOutput,
                &cbInput,
                0);
        v37 = (unsigned int)v36;
        if ( v36 < 0 )
        {
          v40 = 2316;
          goto LABEL_87;
        }
        v38 = *(_DWORD *)(v58 + 36);
        if ( v38 > 1 )
        {
          v31 = *(_QWORD *)v54;
          if ( *(_DWORD *)(*(_QWORD *)v54 + 8LL) >= 0x301u )
          {
            v39 = Tls1VerifyPaddingAndMac(v59[0], v54[0], v53, a8, pbOutput, cbInput, (__int64)&cbInput);
            v37 = (unsigned int)v39;
            if ( v39 >= 0 )
              goto LABEL_104;
            v40 = 2341;
            goto LABEL_87;
          }
          v22 = cbInput;
          if ( cbInput )
          {
            v45 = pbOutput[cbInput - 1] + 1;
            if ( v45 > v38 || v45 > cbInput )
            {
              v28 = 1;
            }
            else
            {
              v22 = cbInput - v45;
              cbInput -= v45;
            }
            v27 = v53;
          }
          else
          {
            v28 = 1;
            v27 = v53;
          }
LABEL_21:
          v32 = v56;
          if ( !v56 )
          {
            if ( !v28 )
            {
LABEL_23:
              v33 = v57 == 0;
              *v61 = v22;
              if ( !v33 )
                memmove(v23, Src, v22);
              return 0;
            }
            goto LABEL_69;
          }
          if ( v22 >= v56 )
          {
            v22 -= v56;
            cbInput = v22;
          }
          else
          {
            v28 = 1;
          }
          if ( *(_DWORD *)(v31 + 8) == 768 )
          {
            v46 = Ssl3ComputeMac(v59[0], v31, v27, a8, (__int64)pbOutput, v22, (__int64)v63, v56);
            v37 = (unsigned int)v46;
            if ( v46 < 0 )
            {
              v40 = 2423;
              goto LABEL_87;
            }
            goto LABEL_100;
          }
          v47 = Tls1ComputeMac(v59[0], v31, v27, a8, pbOutput, v22, v63, v56);
          v37 = (unsigned int)v47;
          if ( v47 >= 0 )
          {
LABEL_100:
            if ( v28 )
            {
LABEL_69:
              v42 = 2466;
LABEL_74:
              v30 = -2146893780;
              v43 = 2148073516LL;
              goto LABEL_75;
            }
            v48 = 0;
            v49 = 0;
            if ( v32 )
            {
              do
              {
                v50 = v63[v49];
                v51 = pbOutput[v22 + v49];
                v49 = (unsigned int)(v49 + 1);
                v48 |= v51 ^ v50;
              }
              while ( (unsigned int)v49 < v32 );
              if ( v48 )
              {
                v42 = 2457;
                goto LABEL_74;
              }
            }
LABEL_104:
            v22 = cbInput;
            goto LABEL_23;
          }
          v40 = 2441;
LABEL_87:
          DebugTraceError(v37, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v40);
          return (unsigned int)-2146893780;
        }
      }
      else
      {
        if ( v26 )
          goto LABEL_20;
        if ( v22 > cbOutput )
        {
          v30 = -2146893784;
          v42 = 2273;
          v43 = 2148073512LL;
          goto LABEL_75;
        }
        memmove(pbOutput, v24, v22);
      }
      v27 = v53;
      v22 = cbInput;
LABEL_20:
      v31 = *(_QWORD *)v54;
      goto LABEL_21;
    }
    v30 = -2146893819;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v21,
        (_DWORD)a3,
        (unsigned int)"Status",
        5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        144);
  }
  return v30;
}

```

## disassembly

```asm
0x18003e4f0  mov     [rsp-8+arg_18], rbx
0x18003e4f5  push    rbp
0x18003e4f6  push    rsi
0x18003e4f7  push    rdi
0x18003e4f8  push    r12
0x18003e4fa  push    r13
0x18003e4fc  push    r14
0x18003e4fe  push    r15
0x18003e500  lea     rbp, [rsp-7]
0x18003e505  sub     rsp, 0E0h
0x18003e50c  mov     rax, cs:__security_cookie
0x18003e513  xor     rax, rsp
0x18003e516  mov     [rbp+37h+var_40], rax
0x18003e51a  mov     rax, [rbp+37h+arg_30]
0x18003e51e  xor     r13d, r13d
0x18003e521  mov     ebx, [rdx+8]
0x18003e524  mov     rdi, r8
0x18003e527  mov     r14, [rbp+37h+arg_20]
0x18003e52b  mov     r10, rdx
0x18003e52e  mov     esi, r9d
0x18003e531  mov     r15d, r13d
0x18003e534  mov     r9, [rdx+10h]
0x18003e538  mov     [rsp+110h+cbInput], r13d
0x18003e53d  mov     qword ptr [rsp+110h+var_B8], rdx
0x18003e542  mov     qword ptr [rbp+37h+var_98], rcx
0x18003e546  mov     r12d, [r9+44h]
0x18003e54a  mov     [rbp+37h+var_AC], r12d
0x18003e54e  mov     [rbp+37h+var_88], rax
0x18003e552  mov     [rbp+37h+var_B0], r13d
0x18003e556  mov     [rbp+37h+var_A0], r9
0x18003e55a  cmp     ebx, 302h
0x18003e560  jnb     loc_18003E883
0x18003e566  mov     eax, ebx
0x18003e568  mov     r11b, 0FEh
0x18003e56b  shr     eax, 8
0x18003e56e  cmp     al, r11b
0x18003e571  jz      loc_18003E8B6
0x18003e577  mov     ecx, r13d
0x18003e57a  test    rdi, rdi
0x18003e57d  jz      loc_18003E833
0x18003e583  cmp     esi, 5
0x18003e586  jb      loc_18003E833
0x18003e58c  movzx   edx, byte ptr [rdi+1]
0x18003e590  mov     eax, r13d
0x18003e593  cmp     dl, r11b
0x18003e596  setz    al
0x18003e599  cmp     eax, ecx
0x18003e59b  jnz     loc_18003E833
0x18003e5a1  mov     r8d, 0Dh
0x18003e5a7  test    ecx, ecx
0x18003e5a9  jnz     loc_18003E8CC
0x18003e5af  movzx   ebx, byte ptr [rdi+3]
0x18003e5b3  movzx   eax, byte ptr [rdi+4]
0x18003e5b7  shl     ebx, 8
0x18003e5ba  or      ebx, eax
0x18003e5bc  lea     eax, [r12+r15]
0x18003e5c0  cmp     ebx, eax
0x18003e5c2  jb      loc_18003E833
0x18003e5c8  movzx   eax, byte ptr [rdi+2]
0x18003e5cc  mov     ecx, edx
0x18003e5ce  shl     ecx, 8
0x18003e5d1  or      ecx, eax
0x18003e5d3  cmp     dl, r11b
0x18003e5d6  jz      loc_18003E8E2
0x18003e5dc  mov     r8d, 5
0x18003e5e2  lea     edx, [r8+r15]
0x18003e5e6  cmp     esi, edx
0x18003e5e8  jb      loc_18003E802
0x18003e5ee  lea     eax, [rcx-300h]
0x18003e5f4  cmp     eax, 3
0x18003e5f7  ja      loc_18003E8F3
0x18003e5fd  sub     ebx, r15d
0x18003e600  mov     [rsp+110h+cbInput], ebx
0x18003e604  lea     eax, [rbx+rdx]
0x18003e607  cmp     eax, esi
0x18003e609  jnz     loc_18003E7AA
0x18003e60f  mov     [rbp+37h+var_A8], r13d
0x18003e613  mov     r13d, r8d
0x18003e616  mov     r11d, edx
0x18003e619  add     r13, rdi
0x18003e61c  add     r11, rdi
0x18003e61f  mov     [rbp+37h+Src], r11
0x18003e623  cmp     r11, r14
0x18003e626  jnz     loc_18003E928
0x18003e62c  mov     esi, [rbp+37h+arg_28]
0x18003e62f  mov     ecx, 1
0x18003e634  movzx   edx, byte ptr [rdi]; int
0x18003e637  xor     r12d, r12d
0x18003e63a  mov     [rsp+110h+var_BC], edx
0x18003e63e  cmp     [rbp+37h+var_B0], r12d
0x18003e642  jz      loc_18003E6D9
0x18003e648  mov     r8, qword ptr [rbp+37h+arg_38]; int
0x18003e64c  lea     rcx, [rsp+110h+cbInput]
0x18003e651  mov     qword ptr [rsp+110h+cbOutput], rcx; ULONG *
0x18003e656  lea     eax, [rbx+r15]
0x18003e65a  mov     dword ptr [rsp+110h+pbOutput], esi; ULONG
0x18003e65e  mov     r9, r13; int
0x18003e661  mov     qword ptr [rsp+110h+cbIV], r14; __int64
0x18003e666  mov     rcx, r10; int
0x18003e669  mov     dword ptr [rsp+110h+pbIV], eax; int
0x18003e66d  call    Tls1AeadDecrypt
0x18003e672  mov     ebx, eax
0x18003e674  test    eax, eax
0x18003e676  js      loc_18003E945
0x18003e67c  mov     edx, [rsp+110h+var_BC]
0x18003e680  mov     ebx, [rsp+110h+cbInput]
0x18003e684  mov     rcx, qword ptr [rsp+110h+var_B8]
0x18003e689  mov     esi, [rbp+37h+var_AC]
0x18003e68c  test    esi, esi
0x18003e68e  jnz     loc_18003E9A2
0x18003e694  test    r12d, r12d
0x18003e697  jnz     loc_18003E9B5
0x18003e69d  cmp     [rbp+37h+var_A8], 0
0x18003e6a1  mov     rax, [rbp+37h+var_88]
0x18003e6a5  mov     [rax], ebx
0x18003e6a7  jnz     loc_18003E9C0
0x18003e6ad  xor     ebx, ebx
0x18003e6af  mov     eax, ebx
0x18003e6b1  mov     rcx, [rbp+37h+var_40]
0x18003e6b5  xor     rcx, rsp; StackCookie
0x18003e6b8  call    __security_check_cookie
0x18003e6bd  mov     rbx, [rsp+110h+arg_18]
0x18003e6c5  add     rsp, 0E0h
0x18003e6cc  pop     r15
0x18003e6ce  pop     r14
0x18003e6d0  pop     r13
0x18003e6d2  pop     r12
0x18003e6d4  pop     rdi
0x18003e6d5  pop     rsi
0x18003e6d6  pop     rbp
0x18003e6d7  retn
0x18003e6d9  cmp     [r9+28h], r12d
0x18003e6dd  jz      loc_18003E952
0x18003e6e3  xor     edi, edi
0x18003e6e5  test    r15d, r15d
0x18003e6e8  jnz     loc_18003E977
0x18003e6ee  xor     edx, edx
0x18003e6f0  mov     eax, ebx
0x18003e6f2  div     dword ptr [r9+24h]
0x18003e6f6  test    edx, edx
0x18003e6f8  jnz     loc_18003E913
0x18003e6fe  mov     rcx, qword ptr [rsp+110h+var_B8]
0x18003e703  lea     rax, [rsp+110h+cbInput]
0x18003e708  mov     [rsp+110h+dwFlags], r12d; dwFlags
0x18003e70d  xor     r9d, r9d; pPaddingInfo
0x18003e710  mov     [rsp+110h+pcbResult], rax; pcbResult
0x18003e715  mov     r8d, ebx; cbInput
0x18003e718  mov     [rsp+110h+cbOutput], esi; cbOutput
0x18003e71c  mov     rdx, r11; pbInput
0x18003e71f  mov     rcx, [rcx+20h]; hKey
0x18003e723  mov     [rsp+110h+pbOutput], r14; pbOutput
0x18003e728  mov     [rsp+110h+cbIV], r15d; cbIV
0x18003e72d  mov     [rsp+110h+pbIV], rdi; pbIV
0x18003e732  call    BCryptDecrypt
0x18003e737  mov     ecx, eax
0x18003e739  test    eax, eax
0x18003e73b  js      loc_18003E997
0x18003e741  mov     r9, [rbp+37h+var_A0]
0x18003e745  mov     edx, 1
0x18003e74a  mov     r9d, [r9+24h]
0x18003e74e  cmp     r9d, edx
0x18003e751  jbe     loc_18003E67C
0x18003e757  mov     rcx, qword ptr [rsp+110h+var_B8]
0x18003e75c  cmp     dword ptr [rcx+8], 301h
0x18003e763  jb      loc_1800A17F9
0x18003e769  mov     r9, qword ptr [rbp+37h+arg_38]; int
0x18003e76d  lea     rax, [rsp+110h+cbInput]
0x18003e772  mov     r8d, [rsp+110h+var_BC]; int
0x18003e777  mov     rdx, rcx; int
0x18003e77a  mov     rcx, qword ptr [rbp+37h+var_98]; int
0x18003e77e  mov     [rsp+110h+pbOutput], rax; __int64
0x18003e783  mov     eax, [rsp+110h+cbInput]
0x18003e787  mov     [rsp+110h+cbIV], eax; cbInput
0x18003e78b  mov     [rsp+110h+pbIV], r14; PUCHAR
0x18003e790  call    Tls1VerifyPaddingAndMac
0x18003e795  mov     ecx, eax
0x18003e797  test    eax, eax
0x18003e799  jns     loc_1800A18C0
0x18003e79f  mov     r9d, 925h
0x18003e7a5  jmp     loc_1800A17DC
0x18003e7aa  mov     ebx, 80090005h
0x18003e7af  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e7b6  lea     rax, WPP_GLOBAL_Control
0x18003e7bd  cmp     rcx, rax
0x18003e7c0  jz      loc_18003E6AF
0x18003e7c6  mov     eax, [rcx+2Ch]
0x18003e7c9  test    al, 1
0x18003e7cb  jz      loc_18003E6AF
0x18003e7d1  mov     dword ptr [rsp+110h+pbOutput], 890h
0x18003e7d9  mov     rcx, [rcx+18h]
0x18003e7dd  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003e7e4  mov     qword ptr [rsp+110h+cbIV], rax
0x18003e7e9  lea     r9, aStatus; "Status"
0x18003e7f0  mov     dword ptr [rsp+110h+pbIV], 80090005h
0x18003e7f8  call    WPP_SF_sDsd
0x18003e7fd  jmp     loc_18003E6AF
0x18003e802  mov     ebx, 80090005h
0x18003e807  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e80e  lea     rax, WPP_GLOBAL_Control
0x18003e815  cmp     rcx, rax
0x18003e818  jz      loc_18003E6AF
0x18003e81e  mov     eax, [rcx+2Ch]
0x18003e821  test    al, 1
0x18003e823  jz      loc_18003E6AF
0x18003e829  mov     dword ptr [rsp+110h+pbOutput], 879h
0x18003e831  jmp     short loc_18003E7D9
0x18003e833  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e83a  lea     rax, WPP_GLOBAL_Control
0x18003e841  cmp     rcx, rax
0x18003e844  jz      short loc_18003E879
0x18003e846  mov     eax, [rcx+2Ch]
0x18003e849  test    al, 1
0x18003e84b  jz      short loc_18003E879
0x18003e84d  mov     rcx, [rcx+18h]
0x18003e851  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003e858  mov     dword ptr [rsp+110h+pbOutput], 869h
0x18003e860  lea     r9, aNteBadData; "NTE_BAD_DATA"
0x18003e867  mov     qword ptr [rsp+110h+cbIV], rax
0x18003e86c  mov     dword ptr [rsp+110h+pbIV], 80090005h
0x18003e874  call    WPP_SF_sDsd
0x18003e879  mov     ebx, 80090005h
0x18003e87e  jmp     loc_18003E6AF
0x18003e883  mov     rcx, [r9+30h]; Str1
0x18003e887  lea     rdx, aChainingmodegc; "ChainingModeGCM"
0x18003e88e  call    wcscmp_0
0x18003e893  mov     r9, [rbp+37h+var_A0]
0x18003e897  test    eax, eax
0x18003e899  jnz     loc_1800A171C
0x18003e89f  mov     r12d, r13d
0x18003e8a2  mov     [rbp+37h+var_AC], r13d
0x18003e8a6  lea     r15d, [rax+8]
0x18003e8aa  mov     [rbp+37h+var_B0], 1
0x18003e8b1  jmp     loc_1800A1768
0x18003e8b6  mov     ecx, 1
0x18003e8bb  cmp     ebx, 0FEFFh
0x18003e8c1  jbe     loc_18003E57A
0x18003e8c7  jmp     loc_18003E577
0x18003e8cc  cmp     esi, r8d
0x18003e8cf  jb      loc_18003E833
0x18003e8d5  movzx   ebx, byte ptr [rdi+0Bh]
0x18003e8d9  movzx   eax, byte ptr [rdi+0Ch]
0x18003e8dd  jmp     loc_18003E5B7
0x18003e8e2  cmp     ecx, 0FEFFh
0x18003e8e8  jbe     loc_18003E5E2
0x18003e8ee  jmp     loc_18003E5DC
0x18003e8f3  cmp     ecx, 0FEFDh
0x18003e8f9  jz      loc_18003E5FD
0x18003e8ff  cmp     ecx, 0FEFFh
0x18003e905  jz      loc_18003E5FD
0x18003e90b  mov     r9d, 885h
0x18003e911  jmp     short loc_18003E919
0x18003e913  mov     r9d, 8FBh
0x18003e919  mov     ebx, 80090005h
0x18003e91e  mov     ecx, 80090005h
0x18003e923  jmp     loc_1800A174C
0x18003e928  cmp     r13, r14
0x18003e92b  jnz     loc_1800A178A
0x18003e931  mov     esi, [rbp+37h+arg_28]
0x18003e934  cmp     esi, r15d
0x18003e937  jnb     loc_1800A1772
0x18003e93d  mov     r9d, 8ABh
0x18003e943  jmp     short loc_18003E919
0x18003e945  mov     r9d, 8D1h
0x18003e94b  mov     ecx, eax
0x18003e94d  jmp     loc_1800A174C
0x18003e952  test    ecx, ecx
0x18003e954  jnz     loc_18003E684
0x18003e95a  cmp     ebx, esi
0x18003e95c  jbe     loc_1800A17C2
0x18003e962  mov     ebx, 80090028h
0x18003e967  mov     r9d, 8E1h
0x18003e96d  mov     ecx, 80090028h
0x18003e972  jmp     loc_1800A174C
0x18003e977  mov     r8d, r15d; Size
0x18003e97a  lea     rcx, [rbp+37h+var_80]; void *
0x18003e97e  mov     rdx, r13; Src
0x18003e981  lea     rdi, [rbp+37h+var_80]
0x18003e985  call    memmove
0x18003e98a  mov     r9, [rbp+37h+var_A0]
0x18003e98e  mov     r11, [rbp+37h+Src]
0x18003e992  jmp     loc_18003E6EE
0x18003e997  mov     r9d, 90Ch
0x18003e99d  jmp     loc_1800A17DC
0x18003e9a2  cmp     ebx, esi
0x18003e9a4  jnb     loc_1800A1834
0x18003e9aa  mov     r12d, 1
0x18003e9b0  jmp     loc_1800A183A
0x18003e9b5  mov     r9d, 9A2h
0x18003e9bb  jmp     loc_1800A1742
0x18003e9c0  mov     rdx, [rbp+37h+Src]; Src
0x18003e9c4  mov     rcx, r13; void *
0x18003e9c7  mov     r8d, ebx; Size
0x18003e9ca  call    memmove
0x18003e9cf  jmp     loc_18003E6AD
0x1800a171c  mov     eax, [r9+24h]
0x1800a1720  cmp     eax, 1
0x1800a1723  jbe     short loc_1800A1768
0x1800a1725  cmp     eax, 10h
0x1800a1728  jbe     short loc_1800A1765
0x1800a172a  mov     ebx, 8009002Dh
  ... truncated ...
```
