# TlsDecryptPacket

- ea: `0x1800484b0`
- end: `0x180048994`
- name: `TlsDecryptPacket`
- size: `1252`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800115b0`

## callees

- `0x18001155c`
- `0x180011c80`
- `0x1800123d0`
- `0x1800484b0`
- `0x180048f50`
- `0x18008ca78`
- `0x18008cc30`
- `0x18008dc2c`
- `0x1800a4232`
- `0x1800a4260`
- `0x1800a45c0`

## string_xrefs

- `0x18004879d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180048811`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800a84f1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800a857a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
        unsigned __int64 a8)
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
            v46 = Ssl3ComputeMac(*(__int64 *)v59, v31, v27, a8, pbOutput, v22, v63, v56);
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
0x1800484b0  mov     [rsp-8+arg_18], rbx
0x1800484b5  push    rbp
0x1800484b6  push    rsi
0x1800484b7  push    rdi
0x1800484b8  push    r12
0x1800484ba  push    r13
0x1800484bc  push    r14
0x1800484be  push    r15
0x1800484c0  lea     rbp, [rsp-7]
0x1800484c5  sub     rsp, 0E0h
0x1800484cc  mov     rax, cs:__security_cookie
0x1800484d3  xor     rax, rsp
0x1800484d6  mov     [rbp+37h+var_40], rax
0x1800484da  mov     rax, [rbp+37h+arg_30]
0x1800484de  xor     r13d, r13d
0x1800484e1  mov     ebx, [rdx+8]
0x1800484e4  mov     rdi, r8
0x1800484e7  mov     r14, [rbp+37h+arg_20]
0x1800484eb  mov     r10, rdx
0x1800484ee  mov     esi, r9d
0x1800484f1  mov     r15d, r13d
0x1800484f4  mov     r9, [rdx+10h]
0x1800484f8  mov     [rsp+110h+cbInput], r13d
0x1800484fd  mov     qword ptr [rsp+110h+var_B8], rdx
0x180048502  mov     qword ptr [rbp+37h+var_98], rcx
0x180048506  mov     r12d, [r9+44h]
0x18004850a  mov     [rbp+37h+var_AC], r12d
0x18004850e  mov     [rbp+37h+var_88], rax
0x180048512  mov     [rbp+37h+var_B0], r13d
0x180048516  mov     [rbp+37h+var_A0], r9
0x18004851a  cmp     ebx, 302h
0x180048520  jnb     loc_180048843
0x180048526  mov     eax, ebx
0x180048528  mov     r11b, 0FEh
0x18004852b  shr     eax, 8
0x18004852e  cmp     al, r11b
0x180048531  jz      loc_180048876
0x180048537  mov     ecx, r13d
0x18004853a  test    rdi, rdi
0x18004853d  jz      loc_1800487F3
0x180048543  cmp     esi, 5
0x180048546  jb      loc_1800487F3
0x18004854c  movzx   edx, byte ptr [rdi+1]
0x180048550  mov     eax, r13d
0x180048553  cmp     dl, r11b
0x180048556  setz    al
0x180048559  cmp     eax, ecx
0x18004855b  jnz     loc_1800487F3
0x180048561  mov     r8d, 0Dh
0x180048567  test    ecx, ecx
0x180048569  jnz     loc_18004888C
0x18004856f  movzx   ebx, byte ptr [rdi+3]
0x180048573  movzx   eax, byte ptr [rdi+4]
0x180048577  shl     ebx, 8
0x18004857a  or      ebx, eax
0x18004857c  lea     eax, [r12+r15]
0x180048580  cmp     ebx, eax
0x180048582  jb      loc_1800487F3
0x180048588  movzx   eax, byte ptr [rdi+2]
0x18004858c  mov     ecx, edx
0x18004858e  shl     ecx, 8
0x180048591  or      ecx, eax
0x180048593  cmp     dl, r11b
0x180048596  jz      loc_1800488A2
0x18004859c  mov     r8d, 5
0x1800485a2  lea     edx, [r8+r15]
0x1800485a6  cmp     esi, edx
0x1800485a8  jb      loc_1800487C2
0x1800485ae  lea     eax, [rcx-300h]
0x1800485b4  cmp     eax, 3
0x1800485b7  ja      loc_1800488B3
0x1800485bd  sub     ebx, r15d
0x1800485c0  mov     [rsp+110h+cbInput], ebx
0x1800485c4  lea     eax, [rbx+rdx]
0x1800485c7  cmp     eax, esi
0x1800485c9  jnz     loc_18004876A
0x1800485cf  mov     [rbp+37h+var_A8], r13d
0x1800485d3  mov     r13d, r8d
0x1800485d6  mov     r11d, edx
0x1800485d9  add     r13, rdi
0x1800485dc  add     r11, rdi
0x1800485df  mov     [rbp+37h+Src], r11
0x1800485e3  cmp     r11, r14
0x1800485e6  jnz     loc_1800488E8
0x1800485ec  mov     esi, [rbp+37h+arg_28]
0x1800485ef  mov     ecx, 1
0x1800485f4  movzx   edx, byte ptr [rdi]; int
0x1800485f7  xor     r12d, r12d
0x1800485fa  mov     [rsp+110h+var_BC], edx
0x1800485fe  cmp     [rbp+37h+var_B0], r12d
0x180048602  jz      loc_180048699
0x180048608  mov     r8, qword ptr [rbp+37h+arg_38]; int
0x18004860c  lea     rcx, [rsp+110h+cbInput]
0x180048611  mov     qword ptr [rsp+110h+cbOutput], rcx; ULONG *
0x180048616  lea     eax, [rbx+r15]
0x18004861a  mov     dword ptr [rsp+110h+pbOutput], esi; ULONG
0x18004861e  mov     r9, r13; int
0x180048621  mov     qword ptr [rsp+110h+cbIV], r14; __int64
0x180048626  mov     rcx, r10; int
0x180048629  mov     dword ptr [rsp+110h+pbIV], eax; int
0x18004862d  call    Tls1AeadDecrypt
0x180048632  mov     ebx, eax
0x180048634  test    eax, eax
0x180048636  js      loc_180048905
0x18004863c  mov     edx, [rsp+110h+var_BC]
0x180048640  mov     ebx, [rsp+110h+cbInput]
0x180048644  mov     rcx, qword ptr [rsp+110h+var_B8]
0x180048649  mov     esi, [rbp+37h+var_AC]
0x18004864c  test    esi, esi
0x18004864e  jnz     loc_180048962
0x180048654  test    r12d, r12d
0x180048657  jnz     loc_180048975
0x18004865d  cmp     [rbp+37h+var_A8], 0
0x180048661  mov     rax, [rbp+37h+var_88]
0x180048665  mov     [rax], ebx
0x180048667  jnz     loc_180048980
0x18004866d  xor     ebx, ebx
0x18004866f  mov     eax, ebx
0x180048671  mov     rcx, [rbp+37h+var_40]
0x180048675  xor     rcx, rsp; StackCookie
0x180048678  call    __security_check_cookie
0x18004867d  mov     rbx, [rsp+110h+arg_18]
0x180048685  add     rsp, 0E0h
0x18004868c  pop     r15
0x18004868e  pop     r14
0x180048690  pop     r13
0x180048692  pop     r12
0x180048694  pop     rdi
0x180048695  pop     rsi
0x180048696  pop     rbp
0x180048697  retn
0x180048699  cmp     [r9+28h], r12d
0x18004869d  jz      loc_180048912
0x1800486a3  xor     edi, edi
0x1800486a5  test    r15d, r15d
0x1800486a8  jnz     loc_180048937
0x1800486ae  xor     edx, edx
0x1800486b0  mov     eax, ebx
0x1800486b2  div     dword ptr [r9+24h]
0x1800486b6  test    edx, edx
0x1800486b8  jnz     loc_1800488D3
0x1800486be  mov     rcx, qword ptr [rsp+110h+var_B8]
0x1800486c3  lea     rax, [rsp+110h+cbInput]
0x1800486c8  mov     [rsp+110h+dwFlags], r12d; dwFlags
0x1800486cd  xor     r9d, r9d; pPaddingInfo
0x1800486d0  mov     [rsp+110h+pcbResult], rax; pcbResult
0x1800486d5  mov     r8d, ebx; cbInput
0x1800486d8  mov     [rsp+110h+cbOutput], esi; cbOutput
0x1800486dc  mov     rdx, r11; pbInput
0x1800486df  mov     rcx, [rcx+20h]; hKey
0x1800486e3  mov     [rsp+110h+pbOutput], r14; pbOutput
0x1800486e8  mov     [rsp+110h+cbIV], r15d; cbIV
0x1800486ed  mov     [rsp+110h+pbIV], rdi; pbIV
0x1800486f2  call    BCryptDecrypt
0x1800486f7  mov     ecx, eax
0x1800486f9  test    eax, eax
0x1800486fb  js      loc_180048957
0x180048701  mov     r9, [rbp+37h+var_A0]
0x180048705  mov     edx, 1
0x18004870a  mov     r9d, [r9+24h]
0x18004870e  cmp     r9d, edx
0x180048711  jbe     loc_18004863C
0x180048717  mov     rcx, qword ptr [rsp+110h+var_B8]
0x18004871c  cmp     dword ptr [rcx+8], 301h
0x180048723  jb      loc_1800A8597
0x180048729  mov     r9, qword ptr [rbp+37h+arg_38]; int
0x18004872d  lea     rax, [rsp+110h+cbInput]
0x180048732  mov     r8d, [rsp+110h+var_BC]; int
0x180048737  mov     rdx, rcx; int
0x18004873a  mov     rcx, qword ptr [rbp+37h+var_98]; int
0x18004873e  mov     [rsp+110h+pbOutput], rax; __int64
0x180048743  mov     eax, [rsp+110h+cbInput]
0x180048747  mov     [rsp+110h+cbIV], eax; cbInput
0x18004874b  mov     [rsp+110h+pbIV], r14; PUCHAR
0x180048750  call    Tls1VerifyPaddingAndMac
0x180048755  mov     ecx, eax
0x180048757  test    eax, eax
0x180048759  jns     loc_1800A865E
0x18004875f  mov     r9d, 925h
0x180048765  jmp     loc_1800A857A
0x18004876a  mov     ebx, 80090005h
0x18004876f  mov     rcx, cs:WPP_GLOBAL_Control
0x180048776  lea     rax, WPP_GLOBAL_Control
0x18004877d  cmp     rcx, rax
0x180048780  jz      loc_18004866F
0x180048786  mov     eax, [rcx+2Ch]
0x180048789  test    al, 1
0x18004878b  jz      loc_18004866F
0x180048791  mov     dword ptr [rsp+110h+pbOutput], 890h
0x180048799  mov     rcx, [rcx+18h]
0x18004879d  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800487a4  mov     qword ptr [rsp+110h+cbIV], rax
0x1800487a9  lea     r9, aStatus; "Status"
0x1800487b0  mov     dword ptr [rsp+110h+pbIV], 80090005h
0x1800487b8  call    WPP_SF_sDsd
0x1800487bd  jmp     loc_18004866F
0x1800487c2  mov     ebx, 80090005h
0x1800487c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800487ce  lea     rax, WPP_GLOBAL_Control
0x1800487d5  cmp     rcx, rax
0x1800487d8  jz      loc_18004866F
0x1800487de  mov     eax, [rcx+2Ch]
0x1800487e1  test    al, 1
0x1800487e3  jz      loc_18004866F
0x1800487e9  mov     dword ptr [rsp+110h+pbOutput], 879h
0x1800487f1  jmp     short loc_180048799
0x1800487f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800487fa  lea     rax, WPP_GLOBAL_Control
0x180048801  cmp     rcx, rax
0x180048804  jz      short loc_180048839
0x180048806  mov     eax, [rcx+2Ch]
0x180048809  test    al, 1
0x18004880b  jz      short loc_180048839
0x18004880d  mov     rcx, [rcx+18h]
0x180048811  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180048818  mov     dword ptr [rsp+110h+pbOutput], 869h
0x180048820  lea     r9, aNteBadData; "NTE_BAD_DATA"
0x180048827  mov     qword ptr [rsp+110h+cbIV], rax
0x18004882c  mov     dword ptr [rsp+110h+pbIV], 80090005h
0x180048834  call    WPP_SF_sDsd
0x180048839  mov     ebx, 80090005h
0x18004883e  jmp     loc_18004866F
0x180048843  mov     rcx, [r9+30h]; Str1
0x180048847  lea     rdx, aChainingmodegc; "ChainingModeGCM"
0x18004884e  call    wcscmp_0
0x180048853  mov     r9, [rbp+37h+var_A0]
0x180048857  test    eax, eax
0x180048859  jnz     loc_1800A84BA
0x18004885f  mov     r12d, r13d
0x180048862  mov     [rbp+37h+var_AC], r13d
0x180048866  lea     r15d, [rax+8]
0x18004886a  mov     [rbp+37h+var_B0], 1
0x180048871  jmp     loc_1800A8506
0x180048876  mov     ecx, 1
0x18004887b  cmp     ebx, 0FEFFh
0x180048881  jbe     loc_18004853A
0x180048887  jmp     loc_180048537
0x18004888c  cmp     esi, r8d
0x18004888f  jb      loc_1800487F3
0x180048895  movzx   ebx, byte ptr [rdi+0Bh]
0x180048899  movzx   eax, byte ptr [rdi+0Ch]
0x18004889d  jmp     loc_180048577
0x1800488a2  cmp     ecx, 0FEFFh
0x1800488a8  jbe     loc_1800485A2
0x1800488ae  jmp     loc_18004859C
0x1800488b3  cmp     ecx, 0FEFDh
0x1800488b9  jz      loc_1800485BD
0x1800488bf  cmp     ecx, 0FEFFh
0x1800488c5  jz      loc_1800485BD
0x1800488cb  mov     r9d, 885h
0x1800488d1  jmp     short loc_1800488D9
0x1800488d3  mov     r9d, 8FBh
0x1800488d9  mov     ebx, 80090005h
0x1800488de  mov     ecx, 80090005h
0x1800488e3  jmp     loc_1800A84EA
0x1800488e8  cmp     r13, r14
0x1800488eb  jnz     loc_1800A8528
0x1800488f1  mov     esi, [rbp+37h+arg_28]
0x1800488f4  cmp     esi, r15d
0x1800488f7  jnb     loc_1800A8510
0x1800488fd  mov     r9d, 8ABh
0x180048903  jmp     short loc_1800488D9
0x180048905  mov     r9d, 8D1h
0x18004890b  mov     ecx, eax
0x18004890d  jmp     loc_1800A84EA
0x180048912  test    ecx, ecx
0x180048914  jnz     loc_180048644
0x18004891a  cmp     ebx, esi
0x18004891c  jbe     loc_1800A8560
0x180048922  mov     ebx, 80090028h
0x180048927  mov     r9d, 8E1h
0x18004892d  mov     ecx, 80090028h
0x180048932  jmp     loc_1800A84EA
0x180048937  mov     r8d, r15d; Size
0x18004893a  lea     rcx, [rbp+37h+var_80]; void *
0x18004893e  mov     rdx, r13; Src
0x180048941  lea     rdi, [rbp+37h+var_80]
0x180048945  call    memmove
0x18004894a  mov     r9, [rbp+37h+var_A0]
0x18004894e  mov     r11, [rbp+37h+Src]
0x180048952  jmp     loc_1800486AE
0x180048957  mov     r9d, 90Ch
0x18004895d  jmp     loc_1800A857A
0x180048962  cmp     ebx, esi
0x180048964  jnb     loc_1800A85D2
0x18004896a  mov     r12d, 1
0x180048970  jmp     loc_1800A85D8
0x180048975  mov     r9d, 9A2h
0x18004897b  jmp     loc_1800A84E0
0x180048980  mov     rdx, [rbp+37h+Src]; Src
0x180048984  mov     rcx, r13; void *
0x180048987  mov     r8d, ebx; Size
0x18004898a  call    memmove
0x18004898f  jmp     loc_18004866D
0x1800a84ba  mov     eax, [r9+24h]
0x1800a84be  cmp     eax, 1
0x1800a84c1  jbe     short loc_1800A8506
0x1800a84c3  cmp     eax, 10h
0x1800a84c6  jbe     short loc_1800A8503
0x1800a84c8  mov     ebx, 8009002Dh
  ... truncated ...
```
