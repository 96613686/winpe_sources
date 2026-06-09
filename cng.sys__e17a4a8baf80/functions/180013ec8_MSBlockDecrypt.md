# MSBlockDecrypt

- ea: `0x180013ec8`
- end: `0x180014679`
- name: `MSBlockDecrypt`
- size: `1969`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180012970`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x180013ec8`
- `0x180016b40`
- `0x1800482d4`
- `0x18004a28c`
- `0x1800a4260`
- `0x1800a4300`
- `0x1800a45c0`

## string_xrefs

- `0x180013fca`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x180013ffa`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x1800140bf`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x1800142cd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x180014614`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`

## pseudocode

```c
__int64 __fastcall MSBlockDecrypt(
        unsigned int *a1,
        __int64 a2,
        void *a3,
        unsigned int a4,
        unsigned __int64 a5,
        unsigned int a6,
        unsigned __int64 a7,
        unsigned int a8,
        unsigned int *a9,
        char a10)
{
  unsigned int v10; // esi
  unsigned int *v11; // r10
  __int64 v14; // r9
  int v15; // ebx
  __int64 v16; // r9
  int v17; // ebx
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rcx
  size_t v22; // rsi
  _BYTE *v23; // r15
  unsigned int *v24; // r11
  __int64 v25; // rax
  __int64 v26; // rdi
  int v27; // r8d
  int v28; // r14d
  __int64 v29; // rcx
  char *v30; // r13
  int v31; // r9d
  int v32; // r9d
  int v33; // r9d
  int v34; // r9d
  _DWORD *v35; // r12
  _QWORD *v36; // r13
  int v37; // edx
  __int64 v38; // rax
  unsigned int *v39; // rdi
  size_t v40; // rax
  int v41; // eax
  size_t v42; // rdi
  unsigned int v43; // eax
  __int64 v44; // rcx
  _BYTE *v45; // rax
  unsigned int v47; // [rsp+70h] [rbp-90h]
  unsigned int *v48; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v49; // [rsp+80h] [rbp-80h]
  unsigned __int64 v50; // [rsp+88h] [rbp-78h]
  unsigned int v51; // [rsp+90h] [rbp-70h]
  __int64 v52; // [rsp+98h] [rbp-68h]
  void *Src; // [rsp+A0h] [rbp-60h]
  __int128 v54; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v55; // [rsp+B8h] [rbp-48h]
  __int128 v56; // [rsp+C8h] [rbp-38h]
  __int64 v57; // [rsp+D8h] [rbp-28h]
  unsigned int *v58; // [rsp+E0h] [rbp-20h]
  unsigned int *v59; // [rsp+E8h] [rbp-18h]
  _QWORD v60[2]; // [rsp+F0h] [rbp-10h] BYREF
  char v61; // [rsp+100h] [rbp+0h] BYREF
  char v62; // [rsp+110h] [rbp+10h] BYREF
  int v63; // [rsp+1B8h] [rbp+B8h]

  v10 = a1[5];
  v11 = a1;
  v14 = a1[3];
  v50 = a7;
  v59 = a9;
  v58 = a1;
  Src = a3;
  v60[0] = a5;
  v51 = a6;
  v47 = a6;
  v15 = a10 & 1;
  v49 = v10;
  v63 = v15;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  if ( a6 % v10 )
  {
    v16 = 915;
LABEL_3:
    v17 = -1073741306;
    v18 = 3221225990LL;
LABEL_90:
    DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c", v16);
    goto LABEL_91;
  }
  v19 = v50;
  if ( !v50 && ((unsigned int)(v14 - 4) > 1 || a5) || !a6 && (unsigned int)(v14 - 4) > 1 )
  {
    v17 = 0;
    goto LABEL_91;
  }
  if ( !v15 && a6 > a8 )
  {
    v17 = -1073741789;
    v20 = 943;
    v21 = 3221225507LL;
LABEL_13:
    DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c", v20);
    goto LABEL_94;
  }
  v22 = a1[4];
  if ( !v15 )
  {
LABEL_18:
    if ( !a5 && (unsigned int)(v14 - 4) > 1 || (v57 = a6, a5 + a6 < a5) || v50 + a8 < v50 )
    {
      v16 = 963;
      goto LABEL_89;
    }
    v23 = a1 + 10;
    if ( a3 )
    {
      if ( a4 < (unsigned int)v22 && (unsigned int)(v14 - 4) > 1 )
      {
        v16 = 980;
        goto LABEL_3;
      }
      if ( (_DWORD)v14 == 2 )
      {
        v16 = 987;
        goto LABEL_89;
      }
      v24 = (unsigned int *)a3;
    }
    else
    {
      v24 = a1 + 10;
    }
    v48 = v24;
    if ( (unsigned int)(v14 - 4) > 1 )
    {
      v26 = 0;
      v27 = 0;
    }
    else
    {
      if ( v15 )
      {
        v17 = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v50,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
            232);
        goto LABEL_92;
      }
      v25 = validateAuthCipherModeInfo(a2, v50, a3, v14);
      v26 = v25;
      if ( !v25 )
      {
        v17 = -1073741811;
        v20 = 1008;
        v21 = 3221225485LL;
        goto LABEL_13;
      }
      v27 = (*(_DWORD *)(v25 + 80) >> 1) & 1;
      v28 = *(_DWORD *)(v25 + 80) & 1;
      if ( v28 )
      {
        if ( a6 % (unsigned int)v22 )
        {
          v17 = -1073741306;
          v20 = 1020;
          v21 = 3221225990LL;
          goto LABEL_13;
        }
        v19 = v50;
LABEL_43:
        v17 = 0;
        v29 = 14LL * ((unsigned int)(unsigned __int16)v11[2] - 1);
        v52 = v29 * 8;
        v30 = (char *)v11 + HIDWORD(rgSymmAlgorithmDefaults[v29 + 8]);
        v31 = v14 - 1;
        if ( v31 )
        {
          v32 = v31 - 1;
          if ( v32 )
          {
            v33 = v32 - 1;
            if ( v33 )
            {
              v34 = v33 - 1;
              if ( v34 )
              {
                if ( v34 != 1 )
                {
                  v17 = -1073741816;
                  v16 = 1201;
                  v18 = 3221225480LL;
                  goto LABEL_90;
                }
                *(_QWORD *)&v54 = v11;
                if ( !v28 && !v27 )
                {
                  *((_QWORD *)&v55 + 1) = 0;
                  *((_QWORD *)&v54 + 1) = &v61;
                  v35 = (_DWORD *)(v26 + 68);
                  *(_QWORD *)&v56 = 0;
                  *(_QWORD *)&v55 = &v62;
                  v36 = (_QWORD *)(v26 + 72);
                  DWORD2(v56) = 1;
LABEL_55:
                  v17 = ((__int64 (__fastcall *)(_QWORD, __int128 *, _QWORD, _QWORD, _DWORD, _QWORD, unsigned int, unsigned __int64, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD))rgSymmAlgorithmDefaults[v29 + 13])(
                          0,
                          &v54,
                          (unsigned int)v22,
                          *(_QWORD *)(v26 + 8),
                          *(_DWORD *)(v26 + 16),
                          v60[0],
                          v47,
                          v19,
                          *(_QWORD *)(v26 + 24),
                          *(_DWORD *)(v26 + 32),
                          *(_QWORD *)(v26 + 40),
                          *(_DWORD *)(v26 + 48),
                          0);
                  if ( v17 < 0 )
                  {
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
                    {
                      v37 = *((_DWORD *)WPP_GLOBAL_Control + 11);
                      if ( (v37 & 1) != 0 )
                        WPP_SF_sDsd(
                          *((_QWORD *)WPP_GLOBAL_Control + 3),
                          v37,
                          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
                          (unsigned int)"Status",
                          v17,
                          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c",
                          153);
                    }
                    goto LABEL_91;
                  }
                  if ( v28 )
                  {
                    *v35 = DWORD2(v55);
                    v38 = v56;
                    *(_DWORD *)(v26 + 80) |= 2u;
                    *v36 = v38;
                  }
                  else
                  {
                    *(_DWORD *)(v26 + 80) &= ~2u;
                    *v35 = 0;
                    *v36 = 0;
                  }
LABEL_61:
                  if ( !v63 )
                    goto LABEL_62;
LABEL_85:
                  v42 = v22;
                  v48 = 0;
                  v43 = SymCryptPaddingPkcs7Remove(v42, v60, v42, v50 + v57 - v42, a8 + (_DWORD)v22 - v51, &v48);
                  v47 += (unsigned int)v48;
                  v17 = SymCryptMapUint32(v43, 3221225473LL, &BlockDecryptErrorMap);
                  if ( v22 )
                  {
                    do
                    {
                      *v23++ = 0;
                      --v42;
                    }
                    while ( v42 );
                  }
                  goto LABEL_92;
                }
                if ( *(_QWORD *)(v26 + 56) && *(_DWORD *)(v26 + 64) >= (unsigned int)v22 )
                {
                  v35 = (_DWORD *)(v26 + 68);
                  *((_QWORD *)&v54 + 1) = Src;
                  v36 = (_QWORD *)(v26 + 72);
                  *(_QWORD *)&v55 = *(_QWORD *)(v26 + 56);
                  *((_QWORD *)&v55 + 1) = *(unsigned int *)(v26 + 68);
                  *(_QWORD *)&v56 = *(_QWORD *)(v26 + 72);
                  DWORD2(v56) = v28 == 0;
                  goto LABEL_55;
                }
                v16 = 1142;
              }
              else
              {
                if ( !v28 && !*(_QWORD *)(v26 + 56) )
                {
                  v41 = ((__int64 (__fastcall *)(char *, _QWORD, _QWORD, _QWORD, _DWORD, unsigned __int64, unsigned int, unsigned __int64, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD))rgSymmAlgorithmDefaults[v29 + 12])(
                          v30,
                          0,
                          (unsigned int)v22,
                          *(_QWORD *)(v26 + 8),
                          *(_DWORD *)(v26 + 16),
                          a5,
                          v47,
                          v50,
                          *(_QWORD *)(v26 + 24),
                          *(_DWORD *)(v26 + 32),
                          *(_QWORD *)(v26 + 40),
                          *(_DWORD *)(v26 + 48),
                          0);
                  v17 = v41;
                  if ( v41 < 0 )
                  {
                    v16 = 1128;
                    v18 = (unsigned int)v41;
                    goto LABEL_90;
                  }
                  goto LABEL_61;
                }
                v16 = 1108;
              }
LABEL_89:
              v18 = 3221225485LL;
              v17 = -1073741811;
              goto LABEL_90;
            }
            ((void (__fastcall *)(char *, _QWORD, _QWORD, unsigned int *, unsigned __int64, unsigned int, unsigned __int64, _DWORD))rgSymmAlgorithmDefaults[v29 + 11])(
              (char *)v11 + HIDWORD(rgSymmAlgorithmDefaults[v29 + 8]),
              (unsigned int)v22,
              v49,
              v24,
              a5,
              v47,
              v19,
              0);
            if ( v63 )
            {
              (*(void (__fastcall **)(char *, _QWORD, _QWORD, unsigned int *, unsigned __int64, _DWORD, _QWORD *, _DWORD))((char *)&rgSymmAlgorithmDefaults[11] + v52))(
                v30,
                (unsigned int)v22,
                v49,
                v48,
                a5 + v47,
                v22,
                v60,
                0);
              goto LABEL_85;
            }
          }
          else
          {
            ((void (__fastcall *)(char *, _QWORD, unsigned __int64, _QWORD, unsigned __int64, _DWORD))rgSymmAlgorithmDefaults[v29 + 9])(
              v30,
              (unsigned int)v22,
              a5,
              v47,
              v19,
              0);
            if ( v63 )
            {
              (*(void (__fastcall **)(char *, _QWORD, unsigned __int64, _QWORD, _QWORD *, _DWORD))((char *)&rgSymmAlgorithmDefaults[9]
                                                                                                 + v52))(
                v30,
                (unsigned int)v22,
                a5 + v47,
                (unsigned int)v22,
                v60,
                0);
              goto LABEL_85;
            }
          }
        }
        else
        {
          ((void (__fastcall *)(char *, _QWORD, unsigned int *, unsigned __int64, unsigned int, unsigned __int64, _DWORD))rgSymmAlgorithmDefaults[v29 + 10])(
            v30,
            (unsigned int)v22,
            v24,
            a5,
            v47,
            v19,
            0);
          if ( v63 )
          {
            (*(void (__fastcall **)(char *, _QWORD, unsigned int *, unsigned __int64, _DWORD, _QWORD *, _DWORD))((char *)&rgSymmAlgorithmDefaults[10] + v52))(
              v30,
              (unsigned int)v22,
              v48,
              a5 + v47,
              v22,
              v60,
              0);
            goto LABEL_85;
          }
        }
LABEL_62:
        v39 = v58;
        if ( (v58[7] & 2) == 0 )
        {
          if ( Src && (v58[3] - 4 > 1 || v28) )
            memmove(v23, Src, v22);
          if ( v39[3] - 4 <= 1 && !v28 )
          {
            v40 = v22;
            if ( (_DWORD)v22 )
            {
              do
              {
                *v23++ = 0;
                --v40;
              }
              while ( v40 );
            }
          }
        }
LABEL_91:
        if ( !v63 )
          goto LABEL_94;
        goto LABEL_92;
      }
    }
    v28 = 0;
    goto LABEL_43;
  }
  if ( a6 - (unsigned int)v22 <= a8 )
  {
    v47 = a6 - v22;
    goto LABEL_18;
  }
  v17 = -1073741789;
  DebugTraceError(3221225507LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\block.c", 949);
LABEL_92:
  v44 = 16;
  v45 = v60;
  do
  {
    *v45++ = 0;
    --v44;
  }
  while ( v44 );
LABEL_94:
  *v59 = v47;
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180013ec8  mov     [rsp-8+arg_18], rbx
0x180013ecd  push    rbp
0x180013ece  push    rsi
0x180013ecf  push    rdi
0x180013ed0  push    r12
0x180013ed2  push    r13
0x180013ed4  push    r14
0x180013ed6  push    r15
0x180013ed8  lea     rbp, [rsp-30h]
0x180013edd  sub     rsp, 130h
0x180013ee4  mov     rax, cs:__security_cookie
0x180013eeb  xor     rax, rsp
0x180013eee  mov     [rbp+60h+var_40], rax
0x180013ef2  mov     esi, [rcx+14h]
0x180013ef5  mov     r10, rcx
0x180013ef8  mov     r13d, [rbp+60h+arg_28]
0x180013eff  mov     rdi, rdx
0x180013f02  mov     rax, [rbp+60h+arg_30]
0x180013f09  mov     r11d, r9d
0x180013f0c  mov     r9d, [rcx+0Ch]
0x180013f10  xorps   xmm0, xmm0
0x180013f13  mov     ebx, [rbp+60h+arg_48]
0x180013f19  mov     r12, [rbp+60h+arg_20]
0x180013f20  mov     [rbp+60h+var_D8], rax
0x180013f24  mov     rax, [rbp+60h+arg_40]
0x180013f2b  mov     [rbp+60h+var_78], rax
0x180013f2f  lea     eax, [r9-4]
0x180013f33  mov     [rbp+60h+var_80], rcx
0x180013f37  xor     ecx, ecx
0x180013f39  cmp     eax, 1
0x180013f3c  mov     [rbp+60h+Src], r8
0x180013f40  mov     eax, r13d
0x180013f43  mov     [rbp+60h+var_70], r12
0x180013f47  setbe   cl
0x180013f4a  mov     [rbp+60h+var_D0], r13d
0x180013f4e  xor     edx, edx
0x180013f50  mov     [rsp+160h+var_F0], r13d
0x180013f55  div     esi
0x180013f57  and     ebx, 1
0x180013f5a  mov     [rbp+60h+var_E0], esi
0x180013f5d  mov     [rbp+60h+arg_48], ebx
0x180013f63  movups  [rbp+60h+var_B8], xmm0
0x180013f67  movups  [rbp+60h+var_A8], xmm0
0x180013f6b  movups  [rbp+60h+var_98], xmm0
0x180013f6f  test    edx, edx
0x180013f71  jz      short loc_180013F88
0x180013f73  mov     r9d, 393h
0x180013f79  mov     ebx, 0C0000206h
0x180013f7e  mov     ecx, 0C0000206h
0x180013f83  jmp     loc_180014614
0x180013f88  mov     rdx, [rbp+60h+var_D8]
0x180013f8c  test    rdx, rdx
0x180013f8f  jnz     short loc_180013FA1
0x180013f91  test    ecx, ecx
0x180013f93  jz      short loc_180013F9A
0x180013f95  test    r12, r12
0x180013f98  jz      short loc_180013FA1
0x180013f9a  xor     ebx, ebx
0x180013f9c  jmp     loc_180014627
0x180013fa1  test    r13d, r13d
0x180013fa4  jnz     short loc_180013FAA
0x180013fa6  test    ecx, ecx
0x180013fa8  jz      short loc_180013F9A
0x180013faa  mov     r14d, [rbp+60h+arg_38]
0x180013fb1  test    ebx, ebx
0x180013fb3  jnz     short loc_180013FE2
0x180013fb5  cmp     r13d, r14d
0x180013fb8  jbe     short loc_180013FE2
0x180013fba  mov     ebx, 0C0000023h
0x180013fbf  mov     r9d, 3AFh
0x180013fc5  mov     ecx, 0C0000023h
0x180013fca  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180013fd1  lea     rdx, aStatus; "Status"
0x180013fd8  call    DebugTraceError
0x180013fdd  jmp     loc_180014645
0x180013fe2  mov     esi, [r10+10h]
0x180013fe6  test    ebx, ebx
0x180013fe8  jz      short loc_180014020
0x180013fea  mov     eax, r13d
0x180013fed  sub     eax, esi
0x180013fef  cmp     eax, r14d
0x180013ff2  jbe     short loc_18001401C
0x180013ff4  mov     r9d, 3B5h
0x180013ffa  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180014001  lea     rdx, aStatus; "Status"
0x180014008  mov     ecx, 0C0000023h
0x18001400d  mov     ebx, 0C0000023h
0x180014012  call    DebugTraceError
0x180014017  jmp     loc_180014630
0x18001401c  mov     [rsp+160h+var_F0], eax
0x180014020  test    r12, r12
0x180014023  jnz     short loc_18001402D
0x180014025  test    ecx, ecx
0x180014027  jz      loc_180014604
0x18001402d  mov     rax, r13
0x180014030  mov     [rbp+60h+var_88], rax
0x180014034  add     rax, r12
0x180014037  cmp     rax, r12
0x18001403a  jb      loc_180014604
0x180014040  lea     rax, [rdx+r14]
0x180014044  cmp     rax, rdx
0x180014047  jb      loc_180014604
0x18001404d  lea     r15, [r10+28h]
0x180014051  test    r8, r8
0x180014054  jnz     short loc_18001405B
0x180014056  mov     r11, r15
0x180014059  jmp     short loc_180014083
0x18001405b  cmp     r11d, esi
0x18001405e  jnb     short loc_18001406F
0x180014060  test    ecx, ecx
0x180014062  jnz     short loc_18001406F
0x180014064  mov     r9d, 3D4h
0x18001406a  jmp     loc_180013F79
0x18001406f  cmp     r9d, 2
0x180014073  jnz     short loc_180014080
0x180014075  mov     r9d, 3DBh
0x18001407b  jmp     loc_18001460A
0x180014080  mov     r11, r8
0x180014083  mov     [rsp+160h+var_E8], r11
0x180014088  test    ecx, ecx
0x18001408a  jz      loc_18001414B
0x180014090  test    ebx, ebx
0x180014092  jz      short loc_1800140EC
0x180014094  mov     ebx, 0C000000Dh
0x180014099  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140a0  lea     rax, WPP_GLOBAL_Control
0x1800140a7  cmp     rcx, rax
0x1800140aa  jz      loc_180014630
0x1800140b0  mov     eax, [rcx+2Ch]
0x1800140b3  test    al, 1
0x1800140b5  jz      loc_180014630
0x1800140bb  mov     rcx, [rcx+18h]
0x1800140bf  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800140c6  mov     dword ptr [rsp+160h+var_130], 3E8h
0x1800140ce  lea     r9, aStatus; "Status"
0x1800140d5  mov     [rsp+160h+var_138], r8
0x1800140da  mov     dword ptr [rsp+160h+var_140], 0C000000Dh
0x1800140e2  call    WPP_SF_sDsd
0x1800140e7  jmp     loc_180014630
0x1800140ec  mov     rcx, rdi
0x1800140ef  call    validateAuthCipherModeInfo
0x1800140f4  mov     rdi, rax
0x1800140f7  test    rax, rax
0x1800140fa  jnz     short loc_180014111
0x1800140fc  mov     ebx, 0C000000Dh
0x180014101  mov     r9d, 3F0h
0x180014107  mov     ecx, 0C000000Dh
0x18001410c  jmp     loc_180013FCA
0x180014111  mov     r8d, [rax+50h]
0x180014115  mov     r14d, r8d
0x180014118  shr     r8d, 1
0x18001411b  and     r8d, 1
0x18001411f  and     r14d, 1
0x180014123  jz      short loc_180014150
0x180014125  xor     edx, edx
0x180014127  mov     eax, r13d
0x18001412a  div     esi
0x18001412c  test    edx, edx
0x18001412e  jz      short loc_180014145
0x180014130  mov     ebx, 0C0000206h
0x180014135  mov     r9d, 3FCh
0x18001413b  mov     ecx, 0C0000206h
0x180014140  jmp     loc_180013FCA
0x180014145  mov     rdx, [rbp+60h+var_D8]
0x180014149  jmp     short loc_180014153
0x18001414b  xor     edi, edi
0x18001414d  xor     r8d, r8d
0x180014150  xor     r14d, r14d
0x180014153  mov     eax, [r10+8]
0x180014157  xor     ebx, ebx
0x180014159  movzx   eax, ax
0x18001415c  dec     eax
0x18001415e  imul    rcx, rax, 70h ; 'p'
0x180014162  lea     rax, rgSymmAlgorithmDefaults
0x180014169  mov     [rbp+60h+var_C8], rcx
0x18001416d  mov     r13d, [rcx+rax+44h]
0x180014172  add     r13, r10
0x180014175  sub     r9d, 1
0x180014179  jz      loc_180014522
0x18001417f  sub     r9d, 1
0x180014183  jz      loc_1800144BD
0x180014189  sub     r9d, 1
0x18001418d  jz      loc_18001443C
0x180014193  sub     r9d, 1
0x180014197  jz      loc_1800143AE
0x18001419d  cmp     r9d, 1
0x1800141a1  jz      short loc_1800141B8
0x1800141a3  mov     ebx, 0C0000008h
0x1800141a8  mov     r9d, 4B1h
0x1800141ae  mov     ecx, 0C0000008h
0x1800141b3  jmp     loc_180014614
0x1800141b8  xor     r9d, r9d
0x1800141bb  mov     qword ptr [rbp+60h+var_B8], r10
0x1800141bf  test    r14d, r14d
0x1800141c2  jnz     short loc_1800141F2
0x1800141c4  test    r8d, r8d
0x1800141c7  jnz     short loc_1800141F2
0x1800141c9  lea     rax, [rbp+60h+var_60]
0x1800141cd  mov     qword ptr [rbp+60h+var_A8+8], r9
0x1800141d1  mov     qword ptr [rbp+60h+var_B8+8], rax
0x1800141d5  lea     r12, [rdi+44h]
0x1800141d9  lea     rax, [rbp+60h+var_50]
0x1800141dd  mov     qword ptr [rbp+60h+var_98], r9
0x1800141e1  mov     qword ptr [rbp+60h+var_A8], rax
0x1800141e5  lea     r13, [rdi+48h]
0x1800141e9  mov     dword ptr [rbp+60h+var_98+8], 1
0x1800141f0  jmp     short loc_18001423D
0x1800141f2  cmp     [rdi+38h], r9
0x1800141f6  jz      loc_1800143A3
0x1800141fc  cmp     [rdi+40h], esi
0x1800141ff  jb      loc_1800143A3
0x180014205  mov     rax, [rbp+60h+Src]
0x180014209  lea     r12, [rdi+44h]
0x18001420d  mov     qword ptr [rbp+60h+var_B8+8], rax
0x180014211  lea     r13, [rdi+48h]
0x180014215  mov     rax, [rdi+38h]
0x180014219  mov     qword ptr [rbp+60h+var_A8], rax
0x18001421d  mov     eax, [r12]
0x180014221  mov     qword ptr [rbp+60h+var_A8+8], rax
0x180014225  mov     rax, [r13+0]
0x180014229  mov     qword ptr [rbp+60h+var_98], rax
0x18001422d  mov     dword ptr [rbp+60h+var_98+8], 1
0x180014234  test    r14d, r14d
0x180014237  jz      short loc_18001423D
0x180014239  mov     dword ptr [rbp+60h+var_98+8], r9d
0x18001423d  mov     eax, [rdi+30h]
0x180014240  lea     r10, rgSymmAlgorithmDefaults
0x180014247  mov     r10, [rcx+r10+68h]
0x18001424c  mov     r8d, esi
0x18001424f  mov     [rsp+160h+var_100], r9d
0x180014254  xor     ecx, ecx
0x180014256  mov     r9, [rdi+8]
0x18001425a  mov     [rsp+160h+var_108], eax
0x18001425e  mov     rax, [rdi+28h]
0x180014262  mov     [rsp+160h+var_110], rax
0x180014267  mov     eax, [rdi+20h]
0x18001426a  mov     [rsp+160h+var_118], eax
0x18001426e  mov     rax, [rdi+18h]
0x180014272  mov     [rsp+160h+var_120], rax
0x180014277  mov     eax, [rsp+160h+var_F0]
0x18001427b  mov     [rsp+160h+var_128], rdx
0x180014280  lea     rdx, [rbp+60h+var_B8]
0x180014284  mov     dword ptr [rsp+160h+var_130], eax
0x180014288  mov     rax, [rbp+60h+var_70]
0x18001428c  mov     [rsp+160h+var_138], rax
0x180014291  mov     eax, [rdi+10h]
0x180014294  mov     dword ptr [rsp+160h+var_140], eax
0x180014298  mov     rax, r10
0x18001429b  call    _guard_dispatch_icall
0x1800142a0  mov     ebx, eax
0x1800142a2  test    eax, eax
0x1800142a4  jns     short loc_1800142F6
0x1800142a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142ad  lea     rax, WPP_GLOBAL_Control
0x1800142b4  cmp     rcx, rax
0x1800142b7  jz      loc_180014627
0x1800142bd  mov     edx, [rcx+2Ch]
0x1800142c0  test    dl, 1
0x1800142c3  jz      loc_180014627
0x1800142c9  mov     rcx, [rcx+18h]
0x1800142cd  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800142d4  mov     dword ptr [rsp+160h+var_130], 499h
0x1800142dc  lea     r9, aStatus; "Status"
0x1800142e3  mov     [rsp+160h+var_138], r8
0x1800142e8  mov     dword ptr [rsp+160h+var_140], ebx
0x1800142ec  call    WPP_SF_sDsd
0x1800142f1  jmp     loc_180014627
0x1800142f6  test    r14d, r14d
0x1800142f9  jz      loc_18001438A
0x1800142ff  mov     eax, dword ptr [rbp+60h+var_A8+8]
0x180014302  mov     [r12], eax
0x180014306  mov     rax, qword ptr [rbp+60h+var_98]
0x18001430a  or      dword ptr [rdi+50h], 2
0x18001430e  mov     [r13+0], rax
0x180014312  cmp     [rbp+60h+arg_48], 0
0x180014319  jnz     loc_18001458F
0x18001431f  mov     rdi, [rbp+60h+var_80]
0x180014323  mov     eax, [rdi+1Ch]
0x180014326  test    al, 2
0x180014328  jnz     loc_180014627
0x18001432e  mov     rcx, [rbp+60h+Src]
0x180014332  test    rcx, rcx
0x180014335  jz      short loc_180014355
0x180014337  mov     eax, [rdi+0Ch]
0x18001433a  sub     eax, 4
0x18001433d  cmp     eax, 1
0x180014340  ja      short loc_180014347
0x180014342  test    r14d, r14d
0x180014345  jz      short loc_180014355
0x180014347  mov     rdx, rcx; Src
0x18001434a  mov     r8, rsi; Size
0x18001434d  mov     rcx, r15; void *
0x180014350  call    memmove
0x180014355  mov     eax, [rdi+0Ch]
0x180014358  sub     eax, 4
0x18001435b  cmp     eax, 1
0x18001435e  ja      loc_180014627
0x180014364  test    r14d, r14d
0x180014367  jnz     loc_180014627
0x18001436d  mov     rax, rsi
  ... truncated ...
```
