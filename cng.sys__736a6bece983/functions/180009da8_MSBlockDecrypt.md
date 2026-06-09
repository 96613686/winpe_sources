# MSBlockDecrypt

- ea: `0x180009da8`
- end: `0x18000a559`
- name: `MSBlockDecrypt`
- size: `1969`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180008850`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x180009da8`
- `0x18000ca20`
- `0x18003eea4`
- `0x180040e5c`
- `0x18009f650`
- `0x18009f6d0`
- `0x18009f780`

## string_xrefs

- `0x180009eaa`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x180009eda`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x180009f9f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18000a1ad`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`
- `0x18000a4f4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\block.c`

## pseudocode

```c
__int64 __fastcall MSBlockDecrypt(
        _DWORD *a1,
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
  _DWORD *v11; // r10
  int v14; // r9d
  int v15; // ebx
  __int64 v16; // r9
  int v17; // ebx
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  __int64 v20; // r9
  __int64 v21; // rcx
  size_t v22; // rsi
  _BYTE *v23; // r15
  _DWORD *v24; // r11
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
  _DWORD *v39; // rdi
  size_t v40; // rax
  int v41; // eax
  size_t v42; // rdi
  unsigned int v43; // eax
  __int64 v44; // rcx
  _BYTE *v45; // rax
  unsigned int v47; // [rsp+70h] [rbp-90h]
  _DWORD *v48; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v49; // [rsp+80h] [rbp-80h]
  unsigned __int64 v50; // [rsp+88h] [rbp-78h]
  unsigned int v51; // [rsp+90h] [rbp-70h]
  __int64 v52; // [rsp+98h] [rbp-68h]
  void *Src; // [rsp+A0h] [rbp-60h]
  __int128 v54; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v55; // [rsp+B8h] [rbp-48h]
  __int128 v56; // [rsp+C8h] [rbp-38h]
  __int64 v57; // [rsp+D8h] [rbp-28h]
  _DWORD *v58; // [rsp+E0h] [rbp-20h]
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
  v22 = (unsigned int)a1[4];
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
      if ( v14 == 2 )
      {
        v16 = 987;
        goto LABEL_89;
      }
      v24 = a3;
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
      v25 = validateAuthCipherModeInfo(a2);
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
            ((void (__fastcall *)(char *, _QWORD, _QWORD, _DWORD *, unsigned __int64, unsigned int, unsigned __int64, _DWORD))rgSymmAlgorithmDefaults[v29 + 11])(
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
              (*(void (__fastcall **)(char *, _QWORD, _QWORD, _DWORD *, unsigned __int64, _DWORD, _QWORD *, _DWORD))((char *)&rgSymmAlgorithmDefaults[11] + v52))(
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
          ((void (__fastcall *)(char *, _QWORD, _DWORD *, unsigned __int64, unsigned int, unsigned __int64, _DWORD))rgSymmAlgorithmDefaults[v29 + 10])(
            v30,
            (unsigned int)v22,
            v24,
            a5,
            v47,
            v19,
            0);
          if ( v63 )
          {
            (*(void (__fastcall **)(char *, _QWORD, _DWORD *, unsigned __int64, _DWORD, _QWORD *, _DWORD))((char *)&rgSymmAlgorithmDefaults[10] + v52))(
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
          if ( Src && ((unsigned int)(v58[3] - 4) > 1 || v28) )
            memmove(v23, Src, v22);
          if ( (unsigned int)(v39[3] - 4) <= 1 && !v28 )
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
0x180009da8  mov     [rsp-8+arg_18], rbx
0x180009dad  push    rbp
0x180009dae  push    rsi
0x180009daf  push    rdi
0x180009db0  push    r12
0x180009db2  push    r13
0x180009db4  push    r14
0x180009db6  push    r15
0x180009db8  lea     rbp, [rsp-30h]
0x180009dbd  sub     rsp, 130h
0x180009dc4  mov     rax, cs:__security_cookie
0x180009dcb  xor     rax, rsp
0x180009dce  mov     [rbp+60h+var_40], rax
0x180009dd2  mov     esi, [rcx+14h]
0x180009dd5  mov     r10, rcx
0x180009dd8  mov     r13d, [rbp+60h+arg_28]
0x180009ddf  mov     rdi, rdx
0x180009de2  mov     rax, [rbp+60h+arg_30]
0x180009de9  mov     r11d, r9d
0x180009dec  mov     r9d, [rcx+0Ch]
0x180009df0  xorps   xmm0, xmm0
0x180009df3  mov     ebx, [rbp+60h+arg_48]
0x180009df9  mov     r12, [rbp+60h+arg_20]
0x180009e00  mov     [rbp+60h+var_D8], rax
0x180009e04  mov     rax, [rbp+60h+arg_40]
0x180009e0b  mov     [rbp+60h+var_78], rax
0x180009e0f  lea     eax, [r9-4]
0x180009e13  mov     [rbp+60h+var_80], rcx
0x180009e17  xor     ecx, ecx
0x180009e19  cmp     eax, 1
0x180009e1c  mov     [rbp+60h+Src], r8
0x180009e20  mov     eax, r13d
0x180009e23  mov     [rbp+60h+var_70], r12
0x180009e27  setbe   cl
0x180009e2a  mov     [rbp+60h+var_D0], r13d
0x180009e2e  xor     edx, edx
0x180009e30  mov     [rsp+160h+var_F0], r13d
0x180009e35  div     esi
0x180009e37  and     ebx, 1
0x180009e3a  mov     [rbp+60h+var_E0], esi
0x180009e3d  mov     [rbp+60h+arg_48], ebx
0x180009e43  movups  [rbp+60h+var_B8], xmm0
0x180009e47  movups  [rbp+60h+var_A8], xmm0
0x180009e4b  movups  [rbp+60h+var_98], xmm0
0x180009e4f  test    edx, edx
0x180009e51  jz      short loc_180009E68
0x180009e53  mov     r9d, 393h
0x180009e59  mov     ebx, 0C0000206h
0x180009e5e  mov     ecx, 0C0000206h
0x180009e63  jmp     loc_18000A4F4
0x180009e68  mov     rdx, [rbp+60h+var_D8]
0x180009e6c  test    rdx, rdx
0x180009e6f  jnz     short loc_180009E81
0x180009e71  test    ecx, ecx
0x180009e73  jz      short loc_180009E7A
0x180009e75  test    r12, r12
0x180009e78  jz      short loc_180009E81
0x180009e7a  xor     ebx, ebx
0x180009e7c  jmp     loc_18000A507
0x180009e81  test    r13d, r13d
0x180009e84  jnz     short loc_180009E8A
0x180009e86  test    ecx, ecx
0x180009e88  jz      short loc_180009E7A
0x180009e8a  mov     r14d, [rbp+60h+arg_38]
0x180009e91  test    ebx, ebx
0x180009e93  jnz     short loc_180009EC2
0x180009e95  cmp     r13d, r14d
0x180009e98  jbe     short loc_180009EC2
0x180009e9a  mov     ebx, 0C0000023h
0x180009e9f  mov     r9d, 3AFh
0x180009ea5  mov     ecx, 0C0000023h
0x180009eaa  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009eb1  lea     rdx, aStatus; "Status"
0x180009eb8  call    DebugTraceError
0x180009ebd  jmp     loc_18000A525
0x180009ec2  mov     esi, [r10+10h]
0x180009ec6  test    ebx, ebx
0x180009ec8  jz      short loc_180009F00
0x180009eca  mov     eax, r13d
0x180009ecd  sub     eax, esi
0x180009ecf  cmp     eax, r14d
0x180009ed2  jbe     short loc_180009EFC
0x180009ed4  mov     r9d, 3B5h
0x180009eda  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009ee1  lea     rdx, aStatus; "Status"
0x180009ee8  mov     ecx, 0C0000023h
0x180009eed  mov     ebx, 0C0000023h
0x180009ef2  call    DebugTraceError
0x180009ef7  jmp     loc_18000A510
0x180009efc  mov     [rsp+160h+var_F0], eax
0x180009f00  test    r12, r12
0x180009f03  jnz     short loc_180009F0D
0x180009f05  test    ecx, ecx
0x180009f07  jz      loc_18000A4E4
0x180009f0d  mov     rax, r13
0x180009f10  mov     [rbp+60h+var_88], rax
0x180009f14  add     rax, r12
0x180009f17  cmp     rax, r12
0x180009f1a  jb      loc_18000A4E4
0x180009f20  lea     rax, [rdx+r14]
0x180009f24  cmp     rax, rdx
0x180009f27  jb      loc_18000A4E4
0x180009f2d  lea     r15, [r10+28h]
0x180009f31  test    r8, r8
0x180009f34  jnz     short loc_180009F3B
0x180009f36  mov     r11, r15
0x180009f39  jmp     short loc_180009F63
0x180009f3b  cmp     r11d, esi
0x180009f3e  jnb     short loc_180009F4F
0x180009f40  test    ecx, ecx
0x180009f42  jnz     short loc_180009F4F
0x180009f44  mov     r9d, 3D4h
0x180009f4a  jmp     loc_180009E59
0x180009f4f  cmp     r9d, 2
0x180009f53  jnz     short loc_180009F60
0x180009f55  mov     r9d, 3DBh
0x180009f5b  jmp     loc_18000A4EA
0x180009f60  mov     r11, r8
0x180009f63  mov     [rsp+160h+var_E8], r11
0x180009f68  test    ecx, ecx
0x180009f6a  jz      loc_18000A02B
0x180009f70  test    ebx, ebx
0x180009f72  jz      short loc_180009FCC
0x180009f74  mov     ebx, 0C000000Dh
0x180009f79  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f80  lea     rax, WPP_GLOBAL_Control
0x180009f87  cmp     rcx, rax
0x180009f8a  jz      loc_18000A510
0x180009f90  mov     eax, [rcx+2Ch]
0x180009f93  test    al, 1
0x180009f95  jz      loc_18000A510
0x180009f9b  mov     rcx, [rcx+18h]
0x180009f9f  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009fa6  mov     dword ptr [rsp+160h+var_130], 3E8h
0x180009fae  lea     r9, aStatus; "Status"
0x180009fb5  mov     [rsp+160h+var_138], r8
0x180009fba  mov     dword ptr [rsp+160h+var_140], 0C000000Dh
0x180009fc2  call    WPP_SF_sDsd
0x180009fc7  jmp     loc_18000A510
0x180009fcc  mov     rcx, rdi
0x180009fcf  call    validateAuthCipherModeInfo
0x180009fd4  mov     rdi, rax
0x180009fd7  test    rax, rax
0x180009fda  jnz     short loc_180009FF1
0x180009fdc  mov     ebx, 0C000000Dh
0x180009fe1  mov     r9d, 3F0h
0x180009fe7  mov     ecx, 0C000000Dh
0x180009fec  jmp     loc_180009EAA
0x180009ff1  mov     r8d, [rax+50h]
0x180009ff5  mov     r14d, r8d
0x180009ff8  shr     r8d, 1
0x180009ffb  and     r8d, 1
0x180009fff  and     r14d, 1
0x18000a003  jz      short loc_18000A030
0x18000a005  xor     edx, edx
0x18000a007  mov     eax, r13d
0x18000a00a  div     esi
0x18000a00c  test    edx, edx
0x18000a00e  jz      short loc_18000A025
0x18000a010  mov     ebx, 0C0000206h
0x18000a015  mov     r9d, 3FCh
0x18000a01b  mov     ecx, 0C0000206h
0x18000a020  jmp     loc_180009EAA
0x18000a025  mov     rdx, [rbp+60h+var_D8]
0x18000a029  jmp     short loc_18000A033
0x18000a02b  xor     edi, edi
0x18000a02d  xor     r8d, r8d
0x18000a030  xor     r14d, r14d
0x18000a033  mov     eax, [r10+8]
0x18000a037  xor     ebx, ebx
0x18000a039  movzx   eax, ax
0x18000a03c  dec     eax
0x18000a03e  imul    rcx, rax, 70h ; 'p'
0x18000a042  lea     rax, rgSymmAlgorithmDefaults
0x18000a049  mov     [rbp+60h+var_C8], rcx
0x18000a04d  mov     r13d, [rcx+rax+44h]
0x18000a052  add     r13, r10
0x18000a055  sub     r9d, 1
0x18000a059  jz      loc_18000A402
0x18000a05f  sub     r9d, 1
0x18000a063  jz      loc_18000A39D
0x18000a069  sub     r9d, 1
0x18000a06d  jz      loc_18000A31C
0x18000a073  sub     r9d, 1
0x18000a077  jz      loc_18000A28E
0x18000a07d  cmp     r9d, 1
0x18000a081  jz      short loc_18000A098
0x18000a083  mov     ebx, 0C0000008h
0x18000a088  mov     r9d, 4B1h
0x18000a08e  mov     ecx, 0C0000008h
0x18000a093  jmp     loc_18000A4F4
0x18000a098  xor     r9d, r9d
0x18000a09b  mov     qword ptr [rbp+60h+var_B8], r10
0x18000a09f  test    r14d, r14d
0x18000a0a2  jnz     short loc_18000A0D2
0x18000a0a4  test    r8d, r8d
0x18000a0a7  jnz     short loc_18000A0D2
0x18000a0a9  lea     rax, [rbp+60h+var_60]
0x18000a0ad  mov     qword ptr [rbp+60h+var_A8+8], r9
0x18000a0b1  mov     qword ptr [rbp+60h+var_B8+8], rax
0x18000a0b5  lea     r12, [rdi+44h]
0x18000a0b9  lea     rax, [rbp+60h+var_50]
0x18000a0bd  mov     qword ptr [rbp+60h+var_98], r9
0x18000a0c1  mov     qword ptr [rbp+60h+var_A8], rax
0x18000a0c5  lea     r13, [rdi+48h]
0x18000a0c9  mov     dword ptr [rbp+60h+var_98+8], 1
0x18000a0d0  jmp     short loc_18000A11D
0x18000a0d2  cmp     [rdi+38h], r9
0x18000a0d6  jz      loc_18000A283
0x18000a0dc  cmp     [rdi+40h], esi
0x18000a0df  jb      loc_18000A283
0x18000a0e5  mov     rax, [rbp+60h+Src]
0x18000a0e9  lea     r12, [rdi+44h]
0x18000a0ed  mov     qword ptr [rbp+60h+var_B8+8], rax
0x18000a0f1  lea     r13, [rdi+48h]
0x18000a0f5  mov     rax, [rdi+38h]
0x18000a0f9  mov     qword ptr [rbp+60h+var_A8], rax
0x18000a0fd  mov     eax, [r12]
0x18000a101  mov     qword ptr [rbp+60h+var_A8+8], rax
0x18000a105  mov     rax, [r13+0]
0x18000a109  mov     qword ptr [rbp+60h+var_98], rax
0x18000a10d  mov     dword ptr [rbp+60h+var_98+8], 1
0x18000a114  test    r14d, r14d
0x18000a117  jz      short loc_18000A11D
0x18000a119  mov     dword ptr [rbp+60h+var_98+8], r9d
0x18000a11d  mov     eax, [rdi+30h]
0x18000a120  lea     r10, rgSymmAlgorithmDefaults
0x18000a127  mov     r10, [rcx+r10+68h]
0x18000a12c  mov     r8d, esi
0x18000a12f  mov     [rsp+160h+var_100], r9d
0x18000a134  xor     ecx, ecx
0x18000a136  mov     r9, [rdi+8]
0x18000a13a  mov     [rsp+160h+var_108], eax
0x18000a13e  mov     rax, [rdi+28h]
0x18000a142  mov     [rsp+160h+var_110], rax
0x18000a147  mov     eax, [rdi+20h]
0x18000a14a  mov     [rsp+160h+var_118], eax
0x18000a14e  mov     rax, [rdi+18h]
0x18000a152  mov     [rsp+160h+var_120], rax
0x18000a157  mov     eax, [rsp+160h+var_F0]
0x18000a15b  mov     [rsp+160h+var_128], rdx
0x18000a160  lea     rdx, [rbp+60h+var_B8]
0x18000a164  mov     dword ptr [rsp+160h+var_130], eax
0x18000a168  mov     rax, [rbp+60h+var_70]
0x18000a16c  mov     [rsp+160h+var_138], rax
0x18000a171  mov     eax, [rdi+10h]
0x18000a174  mov     dword ptr [rsp+160h+var_140], eax
0x18000a178  mov     rax, r10
0x18000a17b  call    _guard_dispatch_icall
0x18000a180  mov     ebx, eax
0x18000a182  test    eax, eax
0x18000a184  jns     short loc_18000A1D6
0x18000a186  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a18d  lea     rax, WPP_GLOBAL_Control
0x18000a194  cmp     rcx, rax
0x18000a197  jz      loc_18000A507
0x18000a19d  mov     edx, [rcx+2Ch]
0x18000a1a0  test    dl, 1
0x18000a1a3  jz      loc_18000A507
0x18000a1a9  mov     rcx, [rcx+18h]
0x18000a1ad  lea     r8, aOnecoreDsSecur_31; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a1b4  mov     dword ptr [rsp+160h+var_130], 499h
0x18000a1bc  lea     r9, aStatus; "Status"
0x18000a1c3  mov     [rsp+160h+var_138], r8
0x18000a1c8  mov     dword ptr [rsp+160h+var_140], ebx
0x18000a1cc  call    WPP_SF_sDsd
0x18000a1d1  jmp     loc_18000A507
0x18000a1d6  test    r14d, r14d
0x18000a1d9  jz      loc_18000A26A
0x18000a1df  mov     eax, dword ptr [rbp+60h+var_A8+8]
0x18000a1e2  mov     [r12], eax
0x18000a1e6  mov     rax, qword ptr [rbp+60h+var_98]
0x18000a1ea  or      dword ptr [rdi+50h], 2
0x18000a1ee  mov     [r13+0], rax
0x18000a1f2  cmp     [rbp+60h+arg_48], 0
0x18000a1f9  jnz     loc_18000A46F
0x18000a1ff  mov     rdi, [rbp+60h+var_80]
0x18000a203  mov     eax, [rdi+1Ch]
0x18000a206  test    al, 2
0x18000a208  jnz     loc_18000A507
0x18000a20e  mov     rcx, [rbp+60h+Src]
0x18000a212  test    rcx, rcx
0x18000a215  jz      short loc_18000A235
0x18000a217  mov     eax, [rdi+0Ch]
0x18000a21a  sub     eax, 4
0x18000a21d  cmp     eax, 1
0x18000a220  ja      short loc_18000A227
0x18000a222  test    r14d, r14d
0x18000a225  jz      short loc_18000A235
0x18000a227  mov     rdx, rcx; Src
0x18000a22a  mov     r8, rsi; Size
0x18000a22d  mov     rcx, r15; void *
0x18000a230  call    memmove
0x18000a235  mov     eax, [rdi+0Ch]
0x18000a238  sub     eax, 4
0x18000a23b  cmp     eax, 1
0x18000a23e  ja      loc_18000A507
0x18000a244  test    r14d, r14d
0x18000a247  jnz     loc_18000A507
0x18000a24d  mov     rax, rsi
  ... truncated ...
```
