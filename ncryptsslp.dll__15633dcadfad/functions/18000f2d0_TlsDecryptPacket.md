# TlsDecryptPacket

- ea: `0x18000f2d0`
- end: `0x18000fc02`
- name: `TlsDecryptPacket`
- size: `2354`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8 *, unsigned int, UCHAR *, ULONG, ULONG *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000ec00`

## callees

- `0x18000b594`
- `0x18000b654`
- `0x18000d6cc`
- `0x18000da9c`
- `0x18000f2d0`
- `0x18000fc08`
- `0x1800185e0`
- `0x180024ef0`
- `0x180024fb0`
- `0x180025660`

## import_xrefs

- `bcrypt!BCryptDecrypt` at `0x18000f58d`
- `bcrypt!BCryptDecrypt` at `0x18000f669`
- `bcrypt!BCryptDecrypt` at `0x18000f58d`
- `bcrypt!BCryptDecrypt` at `0x18000f669`

## string_xrefs

- `0x18000f6ec`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000f756`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000f79a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000f835`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000f895`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000f93c`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000f976`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000f9cc`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000fa80`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000fb8b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall TlsDecryptPacket(
        __int64 a1,
        __int64 a2,
        unsigned __int8 *a3,
        unsigned int a4,
        UCHAR *a5,
        ULONG a6,
        ULONG *a7,
        __int64 a8)
{
  __int64 v8; // r10
  ULONG cbIV; // esi
  PUCHAR v11; // r11
  __int64 v12; // r13
  unsigned int v13; // edi
  __int64 v14; // r14
  int v15; // r9d
  ULONG v16; // r8d
  int v17; // eax
  int v18; // r8d
  int v19; // eax
  int v20; // ecx
  int v21; // edi
  int v22; // eax
  unsigned int v23; // edi
  unsigned int v24; // edx
  unsigned int v25; // r8d
  unsigned int v26; // ecx
  ULONG v27; // edi
  int v28; // edx
  PUCHAR v29; // r12
  _QWORD *v30; // r15
  ULONG v31; // r8d
  int v32; // ecx
  int v33; // ebx
  int v34; // eax
  ULONG v35; // ebx
  int v36; // edx
  __int16 v37; // cx
  UCHAR *v38; // rdx
  char *v39; // rcx
  UCHAR *v40; // r15
  void *v41; // rcx
  ULONG v42; // esi
  unsigned int v43; // ebx
  UCHAR *pbIV; // rcx
  NTSTATUS v46; // eax
  int v47; // edx
  unsigned int v48; // edx
  int v49; // eax
  int v50; // edx
  int v51; // r8d
  unsigned int v52; // eax
  _QWORD *v53; // rcx
  __int64 v54; // r9
  __int64 v55; // rcx
  ULONG v56; // eax
  int v57; // ebx
  bool v58; // zf
  int v59; // eax
  __int64 v60; // r9
  char v61; // r8
  __int64 v62; // rdx
  UCHAR v63; // cl
  UCHAR v64; // al
  ULONG cbInput; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v66; // [rsp+54h] [rbp-ACh]
  int v67; // [rsp+58h] [rbp-A8h]
  int v68; // [rsp+5Ch] [rbp-A4h]
  ULONG cbOutput; // [rsp+60h] [rbp-A0h]
  ULONG v70; // [rsp+64h] [rbp-9Ch]
  PUCHAR pbOutput; // [rsp+68h] [rbp-98h]
  int v72[2]; // [rsp+70h] [rbp-90h]
  void *v73; // [rsp+78h] [rbp-88h]
  ULONG *v74; // [rsp+80h] [rbp-80h]
  _QWORD pPaddingInfo[12]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v76[16]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v77[2]; // [rsp+100h] [rbp+0h] BYREF
  UCHAR v78[48]; // [rsp+110h] [rbp+10h] BYREF

  v8 = *(_QWORD *)(a2 + 16);
  cbIV = 0;
  v11 = a5;
  v12 = a2;
  v13 = *(_DWORD *)(a2 + 8);
  v14 = a4;
  v15 = 0;
  cbOutput = a6;
  cbInput = 0;
  v16 = *(_DWORD *)(v8 + 68);
  v70 = v16;
  *(_QWORD *)v72 = a1;
  pbOutput = a5;
  v74 = a7;
  v67 = 0;
  v77[0] = v8;
  if ( v13 < 0x302 )
  {
LABEL_5:
    v19 = BYTE1(v13) == 0xFE && v13 <= 0xFEFF;
    if ( a3 )
    {
      if ( (unsigned int)v14 >= 5 )
      {
        v20 = a3[1];
        LODWORD(a2) = (_BYTE)v20 == 0xFE;
        if ( (_DWORD)a2 == v19 )
        {
          if ( !v19 )
          {
            v21 = a3[3];
            v22 = a3[4];
            goto LABEL_12;
          }
          if ( (unsigned int)v14 >= 0xD )
          {
            v21 = a3[11];
            v22 = a3[12];
LABEL_12:
            v23 = v22 | (v21 << 8);
            if ( v23 >= v16 + cbIV )
            {
              v24 = (v20 << 8) | a3[2];
              if ( (_BYTE)v20 == 0xFE && v24 <= 0xFEFF )
                v25 = 13;
              else
                v25 = 5;
              v26 = v25 + cbIV;
              if ( (unsigned int)v14 < v25 + cbIV )
              {
                v54 = 2169;
                goto LABEL_83;
              }
              if ( v24 - 768 > 3 && v24 != 65277 && v24 != 65279 )
              {
                v54 = 2181;
                goto LABEL_83;
              }
              v27 = v23 - cbIV;
              cbInput = v27;
              if ( v27 + v26 != (_DWORD)v14 )
              {
                v54 = 2192;
                goto LABEL_83;
              }
              v28 = 0;
              v29 = &a3[v26];
              v30 = &a3[v25];
              v68 = 0;
              if ( v29 == v11 )
              {
                v31 = cbOutput;
                v32 = 1;
LABEL_20:
                v33 = *a3;
                v34 = 0;
                v73 = v30;
                v67 = 0;
                v66 = v33;
                if ( v15 )
                {
                  v35 = v27 + cbIV;
                  memset(pPaddingInfo, 0, 0x58u);
                  if ( v27 + cbIV < 0x18 )
                  {
                    v43 = -2146893819;
                    v53 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_sDsd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v36,
                        v31,
                        (unsigned int)"Status",
                        5,
                        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                        178);
LABEL_51:
                      v53 = WPP_GLOBAL_Control;
                    }
                  }
                  else
                  {
                    v37 = *(_WORD *)(v12 + 8);
                    v76[10] = v37;
                    v38 = (UCHAR *)(v30 + 1);
                    v76[7] = a8;
                    v76[0] = HIBYTE(a8);
                    v76[11] = (unsigned __int16)(v35 - 24) >> 8;
                    v76[12] = v35 - 24;
                    v76[1] = BYTE6(a8);
                    v76[2] = BYTE5(a8);
                    v76[3] = BYTE4(a8);
                    v76[4] = BYTE3(a8);
                    v76[5] = BYTE2(a8);
                    v76[6] = BYTE1(a8);
                    v76[8] = v66;
                    v76[9] = HIBYTE(v37);
                    LODWORD(v77[0]) = *(_DWORD *)(v12 + 56);
                    *(_QWORD *)((char *)v77 + 4) = *v30;
                    pPaddingInfo[1] = v77;
                    pPaddingInfo[3] = v76;
                    pPaddingInfo[0] = 0x100000058LL;
                    v39 = (char *)v30 + v35 - 16;
                    v40 = pbOutput;
                    pPaddingInfo[5] = v39;
                    v41 = *(void **)(v12 + 32);
                    LODWORD(pPaddingInfo[2]) = 12;
                    LODWORD(pPaddingInfo[4]) = 13;
                    LODWORD(pPaddingInfo[6]) = 16;
                    if ( BCryptDecrypt(v41, v38, v35 - 24, pPaddingInfo, 0, 0, pbOutput, cbOutput, &cbInput, 0) >= 0 )
                    {
                      v27 = cbInput;
                      if ( cbInput == v35 - 24 )
                      {
LABEL_24:
                        v34 = v67;
                        v28 = v68;
                        goto LABEL_25;
                      }
                      v43 = -2146893780;
                      DebugTraceError(
                        2148073516LL,
                        "Status",
                        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                        768);
                      goto LABEL_51;
                    }
                    v43 = -2146893780;
                    v53 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_sDsd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v36,
                        v31,
                        (unsigned int)"Status",
                        44,
                        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                        249);
                      goto LABEL_51;
                    }
                  }
                  if ( v53 != &WPP_GLOBAL_Control && (*((_BYTE *)v53 + 28) & 1) != 0 )
                    WPP_SF_sDsd(
                      v53[2],
                      v36,
                      v31,
                      (unsigned int)"Status",
                      v43,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                      209);
                  return v43;
                }
                if ( !*(_DWORD *)(v8 + 40) )
                {
                  if ( v32 )
                  {
                    v40 = pbOutput;
                    goto LABEL_25;
                  }
                  if ( v27 > v31 )
                  {
                    v43 = -2146893784;
                    v54 = 2273;
                    v55 = 2148073512LL;
                    goto LABEL_84;
                  }
                  v40 = pbOutput;
                  memmove(pbOutput, v29, v27);
LABEL_104:
                  v27 = cbInput;
                  goto LABEL_24;
                }
                pbIV = 0;
                if ( cbIV )
                {
                  memmove(v76, v30, cbIV);
                  v8 = v77[0];
                  pbIV = v76;
                }
                if ( !(v27 % *(_DWORD *)(v8 + 36)) )
                {
                  v40 = pbOutput;
                  v46 = BCryptDecrypt(
                          *(BCRYPT_KEY_HANDLE *)(v12 + 32),
                          v29,
                          v27,
                          0,
                          pbIV,
                          cbIV,
                          pbOutput,
                          cbOutput,
                          &cbInput,
                          0);
                  if ( v46 < 0 )
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    {
                      WPP_SF_sDsd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        v47,
                        v31,
                        (unsigned int)"Status",
                        v46,
                        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                        12);
                    }
                    return (unsigned int)-2146893780;
                  }
                  v48 = *(_DWORD *)(v77[0] + 36LL);
                  if ( v48 > 1 )
                  {
                    if ( *(_DWORD *)(v12 + 8) >= 0x301u )
                    {
                      v49 = Tls1VerifyPaddingAndMac(v72[0], v12, v33, a8, v40, cbInput, (__int64)&cbInput);
                      if ( v49 < 0 )
                      {
                        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                        {
                          WPP_SF_sDsd(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            v50,
                            v51,
                            (unsigned int)"Status",
                            v49,
                            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                            37);
                        }
                        return (unsigned int)-2146893780;
                      }
                      goto LABEL_55;
                    }
                    v27 = cbInput;
                    if ( cbInput && (v56 = v40[cbInput - 1] + 1, v56 <= v48) && v56 <= cbInput )
                    {
                      v28 = v68;
                      v27 = cbInput - v56;
                      v34 = v67;
                      cbInput = v27;
                    }
                    else
                    {
                      v28 = v68;
                      v34 = 1;
                      v67 = 1;
                    }
LABEL_25:
                    v42 = v70;
                    if ( !v70 )
                    {
                      if ( !v34 )
                      {
LABEL_27:
                        *v74 = v27;
                        if ( v28 )
                          memmove(v73, v29, v27);
                        return 0;
                      }
                      goto LABEL_77;
                    }
                    if ( v27 >= v70 )
                    {
                      v57 = v67;
                      v27 -= v70;
                      cbInput = v27;
                    }
                    else
                    {
                      v57 = 1;
                    }
                    v58 = *(_DWORD *)(v12 + 8) == 768;
                    v77[0] = v27;
                    if ( v58 )
                    {
                      v59 = Ssl3ComputeMac(v72[0], v12, v66, a8, (__int64)v40, v27, (__int64)v78, v70);
                      if ( v59 < 0 )
                      {
                        v60 = 2423;
LABEL_117:
                        DebugTraceError(
                          (unsigned int)v59,
                          "Status",
                          "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                          v60);
                        return (unsigned int)-2146893780;
                      }
                    }
                    else
                    {
                      v59 = Tls1ComputeMac(v72[0], v12, v66, a8, v40, v27, v78, v70);
                      if ( v59 < 0 )
                      {
                        v60 = 2441;
                        goto LABEL_117;
                      }
                    }
                    if ( v57 )
                    {
LABEL_77:
                      v43 = -2146893780;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                      {
                        WPP_SF_sDsd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          v28,
                          v31,
                          (unsigned int)"Status",
                          44,
                          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                          162);
                      }
                      return v43;
                    }
                    v61 = 0;
                    v62 = 0;
                    if ( v42 )
                    {
                      do
                      {
                        v63 = v40[v77[0] + v62];
                        v64 = v78[v62];
                        v62 = (unsigned int)(v62 + 1);
                        v61 |= v64 ^ v63;
                      }
                      while ( (unsigned int)v62 < v42 );
                      if ( v61 )
                      {
                        v43 = -2146893780;
                        v54 = 2457;
                        v55 = 2148073516LL;
                        goto LABEL_84;
                      }
                    }
LABEL_55:
                    v27 = cbInput;
                    v28 = v68;
                    goto LABEL_27;
                  }
                  goto LABEL_104;
                }
                v54 = 2299;
LABEL_83:
                v43 = -2146893819;
                v55 = 2148073477LL;
LABEL_84:
                DebugTraceError(v55, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", v54);
                return v43;
              }
              if ( v30 == (_QWORD *)v11 )
              {
                if ( cbOutput < cbIV )
                {
                  v54 = 2219;
                  goto LABEL_83;
                }
                v32 = 1;
                v68 = 1;
                v31 = cbOutput - cbIV;
                pbOutput = &v11[cbIV];
                cbOutput -= cbIV;
                v28 = 1;
                goto LABEL_20;
              }
              if ( a3 <= v11 )
              {
                if ( v11 < &a3[v14] )
                  goto LABEL_99;
                if ( a3 < v11 )
                {
                  v31 = cbOutput;
LABEL_97:
                  v32 = 0;
                  goto LABEL_20;
                }
              }
              v31 = cbOutput;
              if ( a3 >= &v11[cbOutput] )
                goto LABEL_97;
LABEL_99:
              v43 = -2146893781;
              v54 = 2232;
              v55 = 2148073515LL;
              goto LABEL_84;
            }
          }
        }
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        v16,
        (unsigned int)"NTE_BAD_DATA",
        5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        105);
    return (unsigned int)-2146893819;
  }
  v17 = wcscmp(*(const wchar_t **)(v8 + 48), L"ChainingModeGCM");
  v8 = v77[0];
  if ( !v17 )
  {
    v16 = 0;
    cbIV = 8;
    v70 = 0;
    v15 = 1;
LABEL_4:
    v11 = pbOutput;
    goto LABEL_5;
  }
  v52 = *(_DWORD *)(v77[0] + 36LL);
  if ( v52 <= 1 )
  {
    v15 = 0;
LABEL_57:
    v16 = v70;
    goto LABEL_4;
  }
  if ( v52 <= 0x10 )
  {
    v15 = v67;
    cbIV = *(_DWORD *)(v77[0] + 36LL);
    goto LABEL_57;
  }
  v43 = -2146893779;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a2,
      v18,
      (unsigned int)"Status",
      45,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      89);
  return v43;
}

```

## disassembly

```asm
0x18000f2d0  mov     [rsp-8+arg_18], rbx
0x18000f2d5  push    rbp
0x18000f2d6  push    rsi
0x18000f2d7  push    rdi
0x18000f2d8  push    r12
0x18000f2da  push    r13
0x18000f2dc  push    r14
0x18000f2de  push    r15
0x18000f2e0  lea     rbp, [rsp-50h]
0x18000f2e5  sub     rsp, 150h
0x18000f2ec  mov     rax, cs:__security_cookie
0x18000f2f3  xor     rax, rsp
0x18000f2f6  mov     [rbp+80h+var_40], rax
0x18000f2fa  mov     r10, [rdx+10h]
0x18000f2fe  xor     esi, esi
0x18000f300  mov     eax, [rbp+80h+arg_28]
0x18000f306  mov     rbx, r8
0x18000f309  mov     r11, [rbp+80h+arg_20]
0x18000f310  mov     r13, rdx
0x18000f313  mov     edi, [rdx+8]
0x18000f316  mov     r14d, r9d
0x18000f319  xor     r9d, r9d
0x18000f31c  mov     [rsp+180h+var_120], eax
0x18000f320  mov     rax, [rbp+80h+arg_30]
0x18000f327  mov     [rsp+180h+cbInput], esi
0x18000f32b  mov     r8d, [r10+44h]
0x18000f32f  mov     [rsp+180h+var_11C], r8d
0x18000f334  mov     qword ptr [rsp+180h+var_110], rcx
0x18000f339  mov     [rsp+180h+var_118], r11
0x18000f33e  mov     [rbp+80h+var_100], rax
0x18000f342  mov     [rsp+180h+var_128], r9d
0x18000f347  mov     qword ptr [rbp+80h+var_80], r10
0x18000f34b  cmp     edi, 302h
0x18000f351  jb      short loc_18000F387
0x18000f353  mov     rcx, [r10+30h]; String1
0x18000f357  lea     rdx, aChainingmodegc; "ChainingModeGCM"
0x18000f35e  call    wcscmp
0x18000f363  mov     r10, qword ptr [rbp+80h+var_80]
0x18000f367  test    eax, eax
0x18000f369  jnz     loc_18000F712
0x18000f36f  xor     r8d, r8d
0x18000f372  mov     esi, 8
0x18000f377  mov     [rsp+180h+var_11C], r8d
0x18000f37c  mov     r9d, 1
0x18000f382  mov     r11, [rsp+180h+var_118]
0x18000f387  mov     eax, edi
0x18000f389  shr     eax, 8
0x18000f38c  cmp     al, 0FEh
0x18000f38e  jz      loc_18000F905
0x18000f394  xor     eax, eax
0x18000f396  test    rbx, rbx
0x18000f399  jz      loc_18000F818
0x18000f39f  cmp     r14d, 5
0x18000f3a3  jb      loc_18000F818
0x18000f3a9  movzx   ecx, byte ptr [rbx+1]
0x18000f3ad  cmp     cl, 0FEh
0x18000f3b0  jz      loc_18000F91B
0x18000f3b6  xor     edx, edx
0x18000f3b8  cmp     edx, eax
0x18000f3ba  jnz     loc_18000F818
0x18000f3c0  test    eax, eax
0x18000f3c2  jnz     loc_18000F8EE
0x18000f3c8  movzx   edi, byte ptr [rbx+3]
0x18000f3cc  movzx   eax, byte ptr [rbx+4]
0x18000f3d0  shl     edi, 8
0x18000f3d3  or      edi, eax
0x18000f3d5  lea     eax, [r8+rsi]
0x18000f3d9  cmp     edi, eax
0x18000f3db  jb      loc_18000F818
0x18000f3e1  movzx   edx, byte ptr [rbx+2]
0x18000f3e5  mov     eax, ecx
0x18000f3e7  shl     eax, 8
0x18000f3ea  or      edx, eax
0x18000f3ec  cmp     cl, 0FEh
0x18000f3ef  jz      loc_18000F925
0x18000f3f5  mov     r8d, 5
0x18000f3fb  lea     ecx, [r8+rsi]
0x18000f3ff  cmp     r14d, ecx
0x18000f402  jb      loc_18000F99B
0x18000f408  lea     eax, [rdx-300h]
0x18000f40e  cmp     eax, 3
0x18000f411  ja      loc_18000F9DD
0x18000f417  sub     edi, esi
0x18000f419  mov     [rsp+180h+cbInput], edi
0x18000f41d  lea     eax, [rdi+rcx]
0x18000f420  cmp     eax, r14d
0x18000f423  jnz     loc_18000F9FD
0x18000f429  xor     edx, edx
0x18000f42b  mov     r12d, ecx
0x18000f42e  mov     r15d, r8d
0x18000f431  add     r12, rbx
0x18000f434  add     r15, rbx
0x18000f437  mov     [rsp+180h+var_124], edx
0x18000f43b  cmp     r12, r11
0x18000f43e  jnz     loc_18000FA05
0x18000f444  mov     r8d, [rsp+180h+var_120]
0x18000f449  mov     ecx, 1
0x18000f44e  movzx   ebx, byte ptr [rbx]
0x18000f451  xor     eax, eax
0x18000f453  mov     r14, qword ptr [rbp+80h+arg_38]
0x18000f45a  mov     r11, r15
0x18000f45d  mov     [rsp+180h+var_108], r15
0x18000f462  mov     [rsp+180h+var_128], eax
0x18000f466  mov     [rsp+180h+var_12C], bl
0x18000f46a  test    r9d, r9d
0x18000f46d  jz      loc_18000F5FC
0x18000f473  xor     edx, edx; Val
0x18000f475  lea     rcx, [rbp+80h+pPaddingInfo]; void *
0x18000f479  mov     r8d, 58h ; 'X'; Size
0x18000f47f  lea     ebx, [rdi+rsi]
0x18000f482  call    memset
0x18000f487  cmp     ebx, 18h
0x18000f48a  jb      loc_18000F76C
0x18000f490  movzx   ecx, word ptr [r13+8]
0x18000f495  lea     esi, [rbx-18h]
0x18000f498  mov     [rbp+80h+var_86], cl
0x18000f49b  lea     rdx, [r15+8]; pbInput
0x18000f49f  mov     rax, r14
0x18000f4a2  mov     [rbp+80h+var_89], r14b
0x18000f4a6  shr     rax, 38h
0x18000f4aa  lea     r9, [rbp+80h+pPaddingInfo]; pPaddingInfo
0x18000f4ae  mov     [rbp+80h+var_90], al
0x18000f4b1  mov     r8d, esi; cbInput
0x18000f4b4  mov     rax, r14
0x18000f4b7  mov     [rbp+80h+var_84], sil
0x18000f4bb  shr     rax, 30h
0x18000f4bf  mov     [rbp+80h+var_8F], al
0x18000f4c2  mov     rax, r14
0x18000f4c5  shr     rax, 28h
0x18000f4c9  mov     [rbp+80h+var_8E], al
0x18000f4cc  mov     rax, r14
0x18000f4cf  shr     rax, 20h
0x18000f4d3  mov     [rbp+80h+var_8D], al
0x18000f4d6  mov     rax, r14
0x18000f4d9  shr     rax, 18h
0x18000f4dd  mov     [rbp+80h+var_8C], al
0x18000f4e0  mov     rax, r14
0x18000f4e3  shr     rax, 10h
0x18000f4e7  mov     [rbp+80h+var_8B], al
0x18000f4ea  mov     rax, r14
0x18000f4ed  shr     rax, 8
0x18000f4f1  mov     [rbp+80h+var_8A], al
0x18000f4f4  movzx   eax, [rsp+180h+var_12C]
0x18000f4f9  mov     [rbp+80h+var_88], al
0x18000f4fc  movzx   eax, cx
0x18000f4ff  shr     ax, 8
0x18000f503  mov     [rbp+80h+var_87], al
0x18000f506  movzx   eax, si
0x18000f509  shr     ax, 8
0x18000f50d  mov     [rbp+80h+var_85], al
0x18000f510  mov     eax, [r13+38h]
0x18000f514  mov     dword ptr [rbp+80h+var_80], eax
0x18000f517  mov     rax, [r15]
0x18000f51a  mov     qword ptr [rbp+80h+var_80+4], rax
0x18000f51e  lea     rax, [rbp+80h+var_80]
0x18000f522  mov     [rbp+80h+var_E8], rax
0x18000f526  lea     rax, [rbp+80h+var_90]
0x18000f52a  mov     [rbp+80h+var_D8], rax
0x18000f52e  lea     rax, [rsp+180h+cbInput]
0x18000f533  mov     ecx, ebx
0x18000f535  add     rcx, 0FFFFFFFFFFFFFFF0h
0x18000f539  mov     [rbp+80h+pPaddingInfo], 58h ; 'X'
0x18000f540  add     rcx, r15
0x18000f543  mov     [rbp+80h+var_EC], 1
0x18000f54a  mov     r15, [rsp+180h+var_118]
0x18000f54f  mov     [rbp+80h+var_C8], rcx
0x18000f553  xor     ecx, ecx
0x18000f555  mov     [rsp+180h+dwFlags], ecx; dwFlags
0x18000f559  mov     [rsp+180h+pcbResult], rax; pcbResult
0x18000f55e  mov     eax, [rsp+180h+var_120]
0x18000f562  mov     [rsp+180h+cbOutput], eax; cbOutput
0x18000f566  mov     [rsp+180h+pbOutput], r15; pbOutput
0x18000f56b  mov     [rsp+180h+cbIV], ecx; cbIV
0x18000f56f  mov     [rsp+180h+pbIV], rcx; pbIV
0x18000f574  mov     rcx, [r13+20h]; hKey
0x18000f578  mov     [rbp+80h+var_E0], 0Ch
0x18000f57f  mov     [rbp+80h+var_D0], 0Dh
0x18000f586  mov     [rbp+80h+var_C0], 10h
0x18000f58d  call    cs:__imp_BCryptDecrypt
0x18000f593  test    eax, eax
0x18000f595  js      loc_18000F867
0x18000f59b  mov     edi, [rsp+180h+cbInput]
0x18000f59f  cmp     edi, esi
0x18000f5a1  jnz     loc_18000FA80
0x18000f5a7  mov     eax, [rsp+180h+var_128]
0x18000f5ab  mov     edx, [rsp+180h+var_124]
0x18000f5af  mov     esi, [rsp+180h+var_11C]
0x18000f5b3  test    esi, esi
0x18000f5b5  jnz     loc_18000FB28
0x18000f5bb  test    eax, eax
0x18000f5bd  jnz     loc_18000F948
0x18000f5c3  mov     rax, [rbp+80h+var_100]
0x18000f5c7  mov     [rax], edi
0x18000f5c9  test    edx, edx
0x18000f5cb  jnz     loc_18000FBED
0x18000f5d1  xor     ebx, ebx
0x18000f5d3  mov     eax, ebx
0x18000f5d5  mov     rcx, [rbp+80h+var_40]
0x18000f5d9  xor     rcx, rsp; StackCookie
0x18000f5dc  call    __security_check_cookie
0x18000f5e1  mov     rbx, [rsp+180h+arg_18]
0x18000f5e9  add     rsp, 150h
0x18000f5f0  pop     r15
0x18000f5f2  pop     r14
0x18000f5f4  pop     r13
0x18000f5f6  pop     r12
0x18000f5f8  pop     rdi
0x18000f5f9  pop     rsi
0x18000f5fa  pop     rbp
0x18000f5fb  retn
0x18000f5fc  cmp     [r10+28h], eax
0x18000f600  jz      loc_18000F8DC
0x18000f606  xor     ecx, ecx
0x18000f608  test    esi, esi
0x18000f60a  jz      short loc_18000F623
0x18000f60c  mov     r8d, esi; Size
0x18000f60f  lea     rcx, [rbp+80h+var_90]; void *
0x18000f613  mov     rdx, r11; Src
0x18000f616  call    memmove
0x18000f61b  mov     r10, qword ptr [rbp+80h+var_80]
0x18000f61f  lea     rcx, [rbp+80h+var_90]
0x18000f623  xor     edx, edx
0x18000f625  mov     eax, edi
0x18000f627  div     dword ptr [r10+24h]
0x18000f62b  test    edx, edx
0x18000f62d  jnz     loc_18000F9A3
0x18000f633  mov     r15, [rsp+180h+var_118]
0x18000f638  lea     rax, [rsp+180h+cbInput]
0x18000f63d  mov     [rsp+180h+dwFlags], edx; dwFlags
0x18000f641  xor     r9d, r9d; pPaddingInfo
0x18000f644  mov     [rsp+180h+pcbResult], rax; pcbResult
0x18000f649  mov     r8d, edi; cbInput
0x18000f64c  mov     eax, [rsp+180h+var_120]
0x18000f650  mov     rdx, r12; pbInput
0x18000f653  mov     [rsp+180h+cbOutput], eax; cbOutput
0x18000f657  mov     [rsp+180h+pbOutput], r15; pbOutput
0x18000f65c  mov     [rsp+180h+cbIV], esi; cbIV
0x18000f660  mov     [rsp+180h+pbIV], rcx; pbIV
0x18000f665  mov     rcx, [r13+20h]; hKey
0x18000f669  call    cs:__imp_BCryptDecrypt
0x18000f66f  test    eax, eax
0x18000f671  js      loc_18000F8AE
0x18000f677  mov     rax, qword ptr [rbp+80h+var_80]
0x18000f67b  mov     edx, [rax+24h]
0x18000f67e  cmp     edx, 1
0x18000f681  jbe     loc_18000FADF
0x18000f687  cmp     dword ptr [r13+8], 301h
0x18000f68f  jb      loc_18000FAE8
0x18000f695  mov     rcx, qword ptr [rsp+180h+var_110]; int
0x18000f69a  lea     rax, [rsp+180h+cbInput]
0x18000f69f  mov     [rsp+180h+pbOutput], rax; __int64
0x18000f6a4  mov     r8d, ebx; int
0x18000f6a7  mov     eax, [rsp+180h+cbInput]
0x18000f6ab  mov     r9, r14; int
0x18000f6ae  mov     [rsp+180h+cbIV], eax; cbInput
0x18000f6b2  mov     rdx, r13; int
0x18000f6b5  mov     [rsp+180h+pbIV], r15; PUCHAR
0x18000f6ba  call    Tls1VerifyPaddingAndMac
0x18000f6bf  test    eax, eax
0x18000f6c1  jns     loc_18000F7FE
0x18000f6c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6ce  lea     rdi, WPP_GLOBAL_Control
0x18000f6d5  cmp     rcx, rdi
0x18000f6d8  jz      short loc_18000F708
0x18000f6da  test    byte ptr [rcx+1Ch], 1
0x18000f6de  jz      short loc_18000F708
0x18000f6e0  mov     dword ptr [rsp+180h+pbOutput], 925h
0x18000f6e8  mov     rcx, [rcx+10h]
0x18000f6ec  lea     rsi, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f6f3  mov     qword ptr [rsp+180h+cbIV], rsi
0x18000f6f8  lea     r9, aStatus; "Status"
0x18000f6ff  mov     dword ptr [rsp+180h+pbIV], eax
0x18000f703  call    WPP_SF_sDsd
0x18000f708  mov     ebx, 8009002Ch
0x18000f70d  jmp     loc_18000F5D3
0x18000f712  mov     eax, [r10+24h]
0x18000f716  cmp     eax, 1
0x18000f719  jbe     loc_18000F80B
0x18000f71f  cmp     eax, 10h
0x18000f722  jbe     loc_18000F98F
0x18000f728  mov     ebx, 8009002Dh
0x18000f72d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f734  lea     rdi, WPP_GLOBAL_Control
0x18000f73b  cmp     rcx, rdi
0x18000f73e  jz      loc_18000F5D3
0x18000f744  test    byte ptr [rcx+1Ch], 1
0x18000f748  jz      loc_18000F5D3
0x18000f74e  mov     dword ptr [rsp+180h+pbOutput], 859h
0x18000f756  lea     rsi, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f75d  mov     qword ptr [rsp+180h+cbIV], rsi
0x18000f762  mov     dword ptr [rsp+180h+pbIV], 8009002Dh
0x18000f76a  jmp     short loc_18000F7E9
0x18000f76c  mov     ebx, 80090005h
0x18000f771  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f778  lea     rdi, WPP_GLOBAL_Control
0x18000f77f  cmp     rcx, rdi
0x18000f782  jz      loc_18000F93C
0x18000f788  test    byte ptr [rcx+1Ch], 1
0x18000f78c  jz      loc_18000F93C
0x18000f792  mov     dword ptr [rsp+180h+pbOutput], 2B2h
  ... truncated ...
```
