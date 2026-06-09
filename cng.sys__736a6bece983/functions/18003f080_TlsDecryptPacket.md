# TlsDecryptPacket

- ea: `0x18003f080`
- end: `0x18003f564`
- name: `TlsDecryptPacket`
- size: `1252`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180007490`

## callees

- `0x18000743c`
- `0x180007b60`
- `0x1800082b0`
- `0x18003f080`
- `0x18003fb20`
- `0x180083878`
- `0x180083a30`
- `0x180084a2c`
- `0x18009f616`
- `0x18009f650`
- `0x18009f780`

## string_xrefs

- `0x18003f36d`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18003f3e1`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800a3583`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800a360c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
0x18003f080  mov     [rsp-8+arg_18], rbx
0x18003f085  push    rbp
0x18003f086  push    rsi
0x18003f087  push    rdi
0x18003f088  push    r12
0x18003f08a  push    r13
0x18003f08c  push    r14
0x18003f08e  push    r15
0x18003f090  lea     rbp, [rsp-7]
0x18003f095  sub     rsp, 0E0h
0x18003f09c  mov     rax, cs:__security_cookie
0x18003f0a3  xor     rax, rsp
0x18003f0a6  mov     [rbp+37h+var_40], rax
0x18003f0aa  mov     rax, [rbp+37h+arg_30]
0x18003f0ae  xor     r13d, r13d
0x18003f0b1  mov     ebx, [rdx+8]
0x18003f0b4  mov     rdi, r8
0x18003f0b7  mov     r14, [rbp+37h+arg_20]
0x18003f0bb  mov     r10, rdx
0x18003f0be  mov     esi, r9d
0x18003f0c1  mov     r15d, r13d
0x18003f0c4  mov     r9, [rdx+10h]
0x18003f0c8  mov     [rsp+110h+cbInput], r13d
0x18003f0cd  mov     qword ptr [rsp+110h+var_B8], rdx
0x18003f0d2  mov     qword ptr [rbp+37h+var_98], rcx
0x18003f0d6  mov     r12d, [r9+44h]
0x18003f0da  mov     [rbp+37h+var_AC], r12d
0x18003f0de  mov     [rbp+37h+var_88], rax
0x18003f0e2  mov     [rbp+37h+var_B0], r13d
0x18003f0e6  mov     [rbp+37h+var_A0], r9
0x18003f0ea  cmp     ebx, 302h
0x18003f0f0  jnb     loc_18003F413
0x18003f0f6  mov     eax, ebx
0x18003f0f8  mov     r11b, 0FEh
0x18003f0fb  shr     eax, 8
0x18003f0fe  cmp     al, r11b
0x18003f101  jz      loc_18003F446
0x18003f107  mov     ecx, r13d
0x18003f10a  test    rdi, rdi
0x18003f10d  jz      loc_18003F3C3
0x18003f113  cmp     esi, 5
0x18003f116  jb      loc_18003F3C3
0x18003f11c  movzx   edx, byte ptr [rdi+1]
0x18003f120  mov     eax, r13d
0x18003f123  cmp     dl, r11b
0x18003f126  setz    al
0x18003f129  cmp     eax, ecx
0x18003f12b  jnz     loc_18003F3C3
0x18003f131  mov     r8d, 0Dh
0x18003f137  test    ecx, ecx
0x18003f139  jnz     loc_18003F45C
0x18003f13f  movzx   ebx, byte ptr [rdi+3]
0x18003f143  movzx   eax, byte ptr [rdi+4]
0x18003f147  shl     ebx, 8
0x18003f14a  or      ebx, eax
0x18003f14c  lea     eax, [r12+r15]
0x18003f150  cmp     ebx, eax
0x18003f152  jb      loc_18003F3C3
0x18003f158  movzx   eax, byte ptr [rdi+2]
0x18003f15c  mov     ecx, edx
0x18003f15e  shl     ecx, 8
0x18003f161  or      ecx, eax
0x18003f163  cmp     dl, r11b
0x18003f166  jz      loc_18003F472
0x18003f16c  mov     r8d, 5
0x18003f172  lea     edx, [r8+r15]
0x18003f176  cmp     esi, edx
0x18003f178  jb      loc_18003F392
0x18003f17e  lea     eax, [rcx-300h]
0x18003f184  cmp     eax, 3
0x18003f187  ja      loc_18003F483
0x18003f18d  sub     ebx, r15d
0x18003f190  mov     [rsp+110h+cbInput], ebx
0x18003f194  lea     eax, [rbx+rdx]
0x18003f197  cmp     eax, esi
0x18003f199  jnz     loc_18003F33A
0x18003f19f  mov     [rbp+37h+var_A8], r13d
0x18003f1a3  mov     r13d, r8d
0x18003f1a6  mov     r11d, edx
0x18003f1a9  add     r13, rdi
0x18003f1ac  add     r11, rdi
0x18003f1af  mov     [rbp+37h+Src], r11
0x18003f1b3  cmp     r11, r14
0x18003f1b6  jnz     loc_18003F4B8
0x18003f1bc  mov     esi, [rbp+37h+arg_28]
0x18003f1bf  mov     ecx, 1
0x18003f1c4  movzx   edx, byte ptr [rdi]; int
0x18003f1c7  xor     r12d, r12d
0x18003f1ca  mov     [rsp+110h+var_BC], edx
0x18003f1ce  cmp     [rbp+37h+var_B0], r12d
0x18003f1d2  jz      loc_18003F269
0x18003f1d8  mov     r8, qword ptr [rbp+37h+arg_38]; int
0x18003f1dc  lea     rcx, [rsp+110h+cbInput]
0x18003f1e1  mov     qword ptr [rsp+110h+cbOutput], rcx; ULONG *
0x18003f1e6  lea     eax, [rbx+r15]
0x18003f1ea  mov     dword ptr [rsp+110h+pbOutput], esi; ULONG
0x18003f1ee  mov     r9, r13; int
0x18003f1f1  mov     qword ptr [rsp+110h+cbIV], r14; __int64
0x18003f1f6  mov     rcx, r10; int
0x18003f1f9  mov     dword ptr [rsp+110h+pbIV], eax; int
0x18003f1fd  call    Tls1AeadDecrypt
0x18003f202  mov     ebx, eax
0x18003f204  test    eax, eax
0x18003f206  js      loc_18003F4D5
0x18003f20c  mov     edx, [rsp+110h+var_BC]
0x18003f210  mov     ebx, [rsp+110h+cbInput]
0x18003f214  mov     rcx, qword ptr [rsp+110h+var_B8]
0x18003f219  mov     esi, [rbp+37h+var_AC]
0x18003f21c  test    esi, esi
0x18003f21e  jnz     loc_18003F532
0x18003f224  test    r12d, r12d
0x18003f227  jnz     loc_18003F545
0x18003f22d  cmp     [rbp+37h+var_A8], 0
0x18003f231  mov     rax, [rbp+37h+var_88]
0x18003f235  mov     [rax], ebx
0x18003f237  jnz     loc_18003F550
0x18003f23d  xor     ebx, ebx
0x18003f23f  mov     eax, ebx
0x18003f241  mov     rcx, [rbp+37h+var_40]
0x18003f245  xor     rcx, rsp; StackCookie
0x18003f248  call    __security_check_cookie
0x18003f24d  mov     rbx, [rsp+110h+arg_18]
0x18003f255  add     rsp, 0E0h
0x18003f25c  pop     r15
0x18003f25e  pop     r14
0x18003f260  pop     r13
0x18003f262  pop     r12
0x18003f264  pop     rdi
0x18003f265  pop     rsi
0x18003f266  pop     rbp
0x18003f267  retn
0x18003f269  cmp     [r9+28h], r12d
0x18003f26d  jz      loc_18003F4E2
0x18003f273  xor     edi, edi
0x18003f275  test    r15d, r15d
0x18003f278  jnz     loc_18003F507
0x18003f27e  xor     edx, edx
0x18003f280  mov     eax, ebx
0x18003f282  div     dword ptr [r9+24h]
0x18003f286  test    edx, edx
0x18003f288  jnz     loc_18003F4A3
0x18003f28e  mov     rcx, qword ptr [rsp+110h+var_B8]
0x18003f293  lea     rax, [rsp+110h+cbInput]
0x18003f298  mov     [rsp+110h+dwFlags], r12d; dwFlags
0x18003f29d  xor     r9d, r9d; pPaddingInfo
0x18003f2a0  mov     [rsp+110h+pcbResult], rax; pcbResult
0x18003f2a5  mov     r8d, ebx; cbInput
0x18003f2a8  mov     [rsp+110h+cbOutput], esi; cbOutput
0x18003f2ac  mov     rdx, r11; pbInput
0x18003f2af  mov     rcx, [rcx+20h]; hKey
0x18003f2b3  mov     [rsp+110h+pbOutput], r14; pbOutput
0x18003f2b8  mov     [rsp+110h+cbIV], r15d; cbIV
0x18003f2bd  mov     [rsp+110h+pbIV], rdi; pbIV
0x18003f2c2  call    BCryptDecrypt
0x18003f2c7  mov     ecx, eax
0x18003f2c9  test    eax, eax
0x18003f2cb  js      loc_18003F527
0x18003f2d1  mov     r9, [rbp+37h+var_A0]
0x18003f2d5  mov     edx, 1
0x18003f2da  mov     r9d, [r9+24h]
0x18003f2de  cmp     r9d, edx
0x18003f2e1  jbe     loc_18003F20C
0x18003f2e7  mov     rcx, qword ptr [rsp+110h+var_B8]
0x18003f2ec  cmp     dword ptr [rcx+8], 301h
0x18003f2f3  jb      loc_1800A3629
0x18003f2f9  mov     r9, qword ptr [rbp+37h+arg_38]; int
0x18003f2fd  lea     rax, [rsp+110h+cbInput]
0x18003f302  mov     r8d, [rsp+110h+var_BC]; int
0x18003f307  mov     rdx, rcx; int
0x18003f30a  mov     rcx, qword ptr [rbp+37h+var_98]; int
0x18003f30e  mov     [rsp+110h+pbOutput], rax; __int64
0x18003f313  mov     eax, [rsp+110h+cbInput]
0x18003f317  mov     [rsp+110h+cbIV], eax; cbInput
0x18003f31b  mov     [rsp+110h+pbIV], r14; PUCHAR
0x18003f320  call    Tls1VerifyPaddingAndMac
0x18003f325  mov     ecx, eax
0x18003f327  test    eax, eax
0x18003f329  jns     loc_1800A36F0
0x18003f32f  mov     r9d, 925h
0x18003f335  jmp     loc_1800A360C
0x18003f33a  mov     ebx, 80090005h
0x18003f33f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f346  lea     rax, WPP_GLOBAL_Control
0x18003f34d  cmp     rcx, rax
0x18003f350  jz      loc_18003F23F
0x18003f356  mov     eax, [rcx+2Ch]
0x18003f359  test    al, 1
0x18003f35b  jz      loc_18003F23F
0x18003f361  mov     dword ptr [rsp+110h+pbOutput], 890h
0x18003f369  mov     rcx, [rcx+18h]
0x18003f36d  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f374  mov     qword ptr [rsp+110h+cbIV], rax
0x18003f379  lea     r9, aStatus; "Status"
0x18003f380  mov     dword ptr [rsp+110h+pbIV], 80090005h
0x18003f388  call    WPP_SF_sDsd
0x18003f38d  jmp     loc_18003F23F
0x18003f392  mov     ebx, 80090005h
0x18003f397  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f39e  lea     rax, WPP_GLOBAL_Control
0x18003f3a5  cmp     rcx, rax
0x18003f3a8  jz      loc_18003F23F
0x18003f3ae  mov     eax, [rcx+2Ch]
0x18003f3b1  test    al, 1
0x18003f3b3  jz      loc_18003F23F
0x18003f3b9  mov     dword ptr [rsp+110h+pbOutput], 879h
0x18003f3c1  jmp     short loc_18003F369
0x18003f3c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f3ca  lea     rax, WPP_GLOBAL_Control
0x18003f3d1  cmp     rcx, rax
0x18003f3d4  jz      short loc_18003F409
0x18003f3d6  mov     eax, [rcx+2Ch]
0x18003f3d9  test    al, 1
0x18003f3db  jz      short loc_18003F409
0x18003f3dd  mov     rcx, [rcx+18h]
0x18003f3e1  lea     rax, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18003f3e8  mov     dword ptr [rsp+110h+pbOutput], 869h
0x18003f3f0  lea     r9, aNteBadData; "NTE_BAD_DATA"
0x18003f3f7  mov     qword ptr [rsp+110h+cbIV], rax
0x18003f3fc  mov     dword ptr [rsp+110h+pbIV], 80090005h
0x18003f404  call    WPP_SF_sDsd
0x18003f409  mov     ebx, 80090005h
0x18003f40e  jmp     loc_18003F23F
0x18003f413  mov     rcx, [r9+30h]; Str1
0x18003f417  lea     rdx, aChainingmodegc; "ChainingModeGCM"
0x18003f41e  call    wcscmp_0
0x18003f423  mov     r9, [rbp+37h+var_A0]
0x18003f427  test    eax, eax
0x18003f429  jnz     loc_1800A354C
0x18003f42f  mov     r12d, r13d
0x18003f432  mov     [rbp+37h+var_AC], r13d
0x18003f436  lea     r15d, [rax+8]
0x18003f43a  mov     [rbp+37h+var_B0], 1
0x18003f441  jmp     loc_1800A3598
0x18003f446  mov     ecx, 1
0x18003f44b  cmp     ebx, 0FEFFh
0x18003f451  jbe     loc_18003F10A
0x18003f457  jmp     loc_18003F107
0x18003f45c  cmp     esi, r8d
0x18003f45f  jb      loc_18003F3C3
0x18003f465  movzx   ebx, byte ptr [rdi+0Bh]
0x18003f469  movzx   eax, byte ptr [rdi+0Ch]
0x18003f46d  jmp     loc_18003F147
0x18003f472  cmp     ecx, 0FEFFh
0x18003f478  jbe     loc_18003F172
0x18003f47e  jmp     loc_18003F16C
0x18003f483  cmp     ecx, 0FEFDh
0x18003f489  jz      loc_18003F18D
0x18003f48f  cmp     ecx, 0FEFFh
0x18003f495  jz      loc_18003F18D
0x18003f49b  mov     r9d, 885h
0x18003f4a1  jmp     short loc_18003F4A9
0x18003f4a3  mov     r9d, 8FBh
0x18003f4a9  mov     ebx, 80090005h
0x18003f4ae  mov     ecx, 80090005h
0x18003f4b3  jmp     loc_1800A357C
0x18003f4b8  cmp     r13, r14
0x18003f4bb  jnz     loc_1800A35BA
0x18003f4c1  mov     esi, [rbp+37h+arg_28]
0x18003f4c4  cmp     esi, r15d
0x18003f4c7  jnb     loc_1800A35A2
0x18003f4cd  mov     r9d, 8ABh
0x18003f4d3  jmp     short loc_18003F4A9
0x18003f4d5  mov     r9d, 8D1h
0x18003f4db  mov     ecx, eax
0x18003f4dd  jmp     loc_1800A357C
0x18003f4e2  test    ecx, ecx
0x18003f4e4  jnz     loc_18003F214
0x18003f4ea  cmp     ebx, esi
0x18003f4ec  jbe     loc_1800A35F2
0x18003f4f2  mov     ebx, 80090028h
0x18003f4f7  mov     r9d, 8E1h
0x18003f4fd  mov     ecx, 80090028h
0x18003f502  jmp     loc_1800A357C
0x18003f507  mov     r8d, r15d; Size
0x18003f50a  lea     rcx, [rbp+37h+var_80]; void *
0x18003f50e  mov     rdx, r13; Src
0x18003f511  lea     rdi, [rbp+37h+var_80]
0x18003f515  call    memmove
0x18003f51a  mov     r9, [rbp+37h+var_A0]
0x18003f51e  mov     r11, [rbp+37h+Src]
0x18003f522  jmp     loc_18003F27E
0x18003f527  mov     r9d, 90Ch
0x18003f52d  jmp     loc_1800A360C
0x18003f532  cmp     ebx, esi
0x18003f534  jnb     loc_1800A3664
0x18003f53a  mov     r12d, 1
0x18003f540  jmp     loc_1800A366A
0x18003f545  mov     r9d, 9A2h
0x18003f54b  jmp     loc_1800A3572
0x18003f550  mov     rdx, [rbp+37h+Src]; Src
0x18003f554  mov     rcx, r13; void *
0x18003f557  mov     r8d, ebx; Size
0x18003f55a  call    memmove
0x18003f55f  jmp     loc_18003F23D
0x1800a354c  mov     eax, [r9+24h]
0x1800a3550  cmp     eax, 1
0x1800a3553  jbe     short loc_1800A3598
0x1800a3555  cmp     eax, 10h
0x1800a3558  jbe     short loc_1800A3595
0x1800a355a  mov     ebx, 8009002Dh
  ... truncated ...
```
