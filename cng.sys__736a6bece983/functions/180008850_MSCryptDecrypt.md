# MSCryptDecrypt

- ea: `0x180008850`
- end: `0x1800092a3`
- name: `MSCryptDecrypt`
- size: `2643`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180014070`
- `0x180080288`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x180008850`
- `0x1800092b0`
- `0x1800097c0`
- `0x180009da8`
- `0x18000a560`
- `0x18000ca20`
- `0x18000ca60`
- `0x18002c630`
- `0x180043b30`
- `0x180048af8`
- `0x18004980c`
- `0x18004cc10`
- `0x18004d160`
- `0x18009f650`
- `0x18009f780`
- `0x18009fa80`

## import_xrefs

- `ntoskrnl!KeRestoreExtendedProcessorState` at `0x180008b6d`
- `ntoskrnl!KeRestoreExtendedProcessorState` at `0x180008b6d`
- `ntoskrnl!KeSaveExtendedProcessorState` at `0x180008aa4`
- `ntoskrnl!KeSaveExtendedProcessorState` at `0x180008aa4`

## string_xrefs

- `0x1800089ad`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180008c8b`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180008ce3`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180008f42`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180008f8a`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180008fd2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180009016`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180009154`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180009205`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000924d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180009276`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptDecrypt(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 *a5,
        int a6,
        unsigned __int64 a7,
        unsigned int a8,
        unsigned int *a9,
        int a10)
{
  __int64 v10; // r14
  unsigned __int64 v11; // r12
  int v13; // edx
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // r8d
  unsigned int v18; // ecx
  unsigned __int64 v19; // rdi
  unsigned __int64 v20; // r15
  __int64 v21; // rsi
  __int64 v22; // r13
  __int64 v23; // rcx
  unsigned __int64 v24; // rbx
  unsigned __int64 j; // rsi
  __int64 v26; // rcx
  unsigned __int64 v27; // rbx
  unsigned __int64 i; // rsi
  __int64 v29; // rdx
  _QWORD *v30; // rcx
  __int64 v31; // rax
  unsigned __int64 v32; // rbx
  unsigned __int64 *v33; // rax
  __m128i *v34; // r14
  unsigned __int64 v35; // rdi
  unsigned __int64 *v36; // rbx
  const __m128i *v37; // rsi
  unsigned __int64 v38; // r8
  __int64 v39; // rdx
  __int64 *v40; // rdi
  int v41; // edx
  __int64 v42; // rax
  int v43; // edx
  __int64 v44; // r8
  __int64 v45; // r10
  __int64 v46; // r11
  __int64 v47; // rbx
  int v48; // edx
  int v49; // r8d
  __m128i v50; // xmm0
  __int64 v51; // rax
  unsigned __int64 v52; // [rsp+60h] [rbp-A0h]
  __int64 v53; // [rsp+68h] [rbp-98h]
  __int64 v54; // [rsp+68h] [rbp-98h]
  __int64 v55; // [rsp+68h] [rbp-98h]
  unsigned __int64 v56; // [rsp+78h] [rbp-88h]
  unsigned __int64 v57; // [rsp+80h] [rbp-80h]
  unsigned __int64 v58; // [rsp+88h] [rbp-78h]
  unsigned __int64 v59; // [rsp+90h] [rbp-70h]
  unsigned __int64 v60; // [rsp+98h] [rbp-68h]
  _BYTE XStateSave[64]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v62[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v63[256]; // [rsp+1E0h] [rbp+E0h] BYREF
  __m128 v64; // [rsp+2E0h] [rbp+1E0h] BYREF
  __m128 Src; // [rsp+2F0h] [rbp+1F0h] BYREF
  __m128i v66; // [rsp+300h] [rbp+200h] BYREF
  _QWORD v67[32]; // [rsp+310h] [rbp+210h] BYREF

  v10 = a7;
  v11 = a2;
  v56 = a7;
  v57 = a2;
  if ( a1 && *(_DWORD *)(a1 + 4) == 1297306443 )
  {
    if ( (unsigned int)(*(_DWORD *)(a1 + 12) - 4) <= 1 || *(_DWORD *)(a1 + 8) == 65545 || !a4 )
    {
      v13 = a10;
      if ( (a10 & 0xFFFFFEB8) != 0
        || ((unsigned __int8)a10 & (unsigned __int8)~*(_BYTE *)(*(_QWORD *)(a1 + 32) + 36LL) & 0x40) != 0 )
      {
        v15 = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            a10,
            a3,
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
            51);
      }
      else if ( a9 )
      {
        v14 = *(_DWORD *)(a1 + 8);
        if ( v14 == 65543 )
        {
LABEL_8:
          v15 = MSBlockDecrypt(a1, a4, (_DWORD)a5, a6, v11, a3, a7, a8, (__int64)a9, a10);
          if ( (v15 & 0x80000000) != 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            v41 = *((_DWORD *)WPP_GLOBAL_Control + 11);
            if ( (v41 & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v41,
                v16,
                (unsigned int)"Status",
                v15,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                192);
          }
        }
        else if ( v14 == 65544 )
        {
          if ( (a10 & 0xFFFFFFBF) == 0
            && (v18 = *(_DWORD *)(a1 + 20)) != 0
            && (v13 = a3 % v18) == 0
            && v11
            && a5
            && a6 == 8
            && (v19 = a3, a3 + v11 >= v11)
            && a7 + a8 >= a7 )
          {
            *a9 = a3;
            if ( a7 )
            {
              if ( a3 > a8 )
              {
                return (unsigned int)-1073741789;
              }
              else
              {
                v20 = *(unsigned int *)(a1 + 20);
                v15 = 0;
                v58 = v20;
                if ( v20 >= 0x10 )
                {
                  v21 = *a5;
                  v22 = a1 + 128;
                  memset(XStateSave, 0, sizeof(XStateSave));
                  if ( (g_SymCryptCpuFeaturesNotPresent & 0x816) != 0 )
                    goto LABEL_43;
                  if ( (g_SymCryptCpuFeaturesNotPresent & 0x10) != 0 )
                    SymCryptFatal(0x206D6D79u);
                  if ( KeGetCurrentIrql() > 2u || KeSaveExtendedProcessorState(4u, (PXSTATE_SAVE)XStateSave) < 0 )
                  {
LABEL_43:
                    if ( (g_SymCryptCpuFeaturesNotPresent & 6) != 0 )
                    {
                      if ( v19 >= v20 )
                      {
                        v31 = v22 + 496;
                        do
                        {
                          v32 = 0;
                          do
                          {
                            v67[v32] = v21;
                            v19 -= v20;
                            v67[v32 + 1] = 0;
                            ++v21;
                            v32 += 2LL;
                          }
                          while ( v32 < 32 && v19 >= v20 );
                          v59 = v32 * 8;
                          v55 = v21;
                          v60 = v19;
                          SymCryptAesEcbEncryptAsm(v31, v67, v67, v32 * 8);
                          v52 = 0;
                          if ( v32 * 8 )
                          {
                            v33 = (unsigned __int64 *)v56;
                            v34 = (__m128i *)v67;
                            do
                            {
                              v35 = v20;
                              v36 = v33;
                              v37 = (const __m128i *)v11;
                              if ( v20 >= 0x20 )
                              {
                                do
                                {
                                  v64 = _mm_xor_ps((__m128)_mm_loadu_si128(v37), (__m128)_mm_loadu_si128(v34));
                                  SymCryptAesDecryptAsm(v22, &v64, &v64);
                                  v38 = v34->m128i_i64[0];
                                  ++v37;
                                  v39 = v34->m128i_i64[1];
                                  *v36 = v64.m128_u64[0] ^ v34->m128i_i64[0];
                                  v35 -= 16LL;
                                  v36[1] = v64.m128_u64[1] ^ v39;
                                  v34->m128i_i64[0] = (2 * v38) ^ (v39 >> 63) & 0x87;
                                  v36 += 2;
                                  v34->m128i_i64[1] = (v38 >> 63) | (2 * v39);
                                }
                                while ( v35 >= 0x20 );
                                v20 = v58;
                              }
                              if ( v35 > 0x10 )
                              {
                                v50 = *v34;
                                v51 = *(__int128 *)v34 >> 63;
                                v34->m128i_i64[0] = (2 * v34->m128i_i64[0]) ^ (v34->m128i_i64[1] >> 63) & 0x87;
                                v34->m128i_i64[1] = v51;
                                v66 = v50;
                                SymCryptXorBytes(v34, v37, &v64, 16);
                                SymCryptAesDecryptAsm(v22, &v64, &v64);
                                SymCryptXorBytes(v34, &v64, &v64, 16);
                                Src = v64;
                                memmove(&v64, &v37[1], v35 - 16);
                                memmove(v36 + 2, &Src, v35 - 16);
                                v37 = (const __m128i *)&v64;
                                v40 = (__int64 *)&v66;
                              }
                              else
                              {
                                v40 = (__int64 *)v34;
                              }
                              v64.m128_u64[0] = *v40 ^ v37->m128i_i64[0];
                              v64.m128_u64[1] = v40[1] ^ v37->m128i_i64[1];
                              SymCryptAesDecryptAsm(v22, &v64, &v64);
                              ++v34;
                              v11 = v20 + v57;
                              *(_OWORD *)v36 = *(_OWORD *)v40 ^ *(_OWORD *)&v64;
                              v64 = 0u;
                              v33 = (unsigned __int64 *)(v20 + v56);
                              Src = 0u;
                              v66 = 0u;
                              v57 += v20;
                              v56 += v20;
                              v52 += 16LL;
                            }
                            while ( v52 < v59 );
                            v19 = v60;
                            v21 = v55;
                          }
                          v31 = v22 + 496;
                        }
                        while ( v19 >= v20 );
                        v15 = 0;
                      }
                      v29 = 256;
                      v30 = v67;
                    }
                    else
                    {
                      if ( v19 >= v20 )
                      {
                        v26 = v22 + 496;
                        do
                        {
                          v27 = 0;
                          do
                          {
                            v62[v27 / 8] = v21;
                            v19 -= v20;
                            v62[v27 / 8 + 1] = 0;
                            ++v21;
                            v27 += 16LL;
                          }
                          while ( v27 < 0x100 && v19 >= v20 );
                          v54 = v21;
                          SymCryptAesEcbEncryptXmm(v26, v62, v62, v27);
                          if ( v27 )
                          {
                            for ( i = 0; i < v27; i += 16LL )
                            {
                              SymCryptXtsAesDecryptDataUnitXmm(v22, &v62[i / 8], v63, v11, v10, v20);
                              v11 += v20;
                              v10 += v20;
                            }
                            v21 = v54;
                          }
                          v26 = v22 + 496;
                        }
                        while ( v19 >= v20 );
                        v15 = 0;
                      }
                      v29 = 512;
                      v30 = v62;
                    }
                    SymCryptWipeAsm(v30, v29);
                  }
                  else
                  {
                    if ( v19 >= v20 )
                    {
                      v23 = v22 + 496;
                      do
                      {
                        v24 = 0;
                        do
                        {
                          v62[v24 / 8] = v21;
                          v19 -= v20;
                          v62[v24 / 8 + 1] = 0;
                          ++v21;
                          v24 += 16LL;
                        }
                        while ( v24 < 0x100 && v19 >= v20 );
                        v53 = v21;
                        SymCryptAesEcbEncryptXmm(v23, v62, v62, v24);
                        if ( v24 )
                        {
                          for ( j = 0; j < v24; j += 16LL )
                          {
                            SymCryptXtsAesDecryptDataUnitYmm_2048(
                              v22,
                              (unsigned int)&v62[j / 8],
                              (unsigned int)v63,
                              v11,
                              v10,
                              v20);
                            v11 += v20;
                            v10 += v20;
                          }
                          v21 = v53;
                        }
                        v23 = v22 + 496;
                      }
                      while ( v19 >= v20 );
                      v15 = 0;
                    }
                    SymCryptWipeAsm(v62, 512);
                    KeRestoreExtendedProcessorState((PXSTATE_SAVE)XStateSave);
                  }
                }
              }
            }
            else
            {
              return 0;
            }
          }
          else
          {
            v15 = -1073741811;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            {
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v13,
                a3,
                (unsigned int)"Status",
                13,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                213);
            }
          }
        }
        else
        {
          switch ( v14 )
          {
            case 65537:
              *a9 = a3;
              if ( !a7 )
                return 0;
              if ( a3 > a8 )
                return (unsigned int)-1073741789;
              if ( !a3 )
                return 0;
              if ( v11 && !a5 && a3 + v11 >= v11 && a3 + a7 >= a7 )
              {
                SymCryptRc4Crypt(a1 + 320, v11, a7);
                return 0;
              }
              v15 = -1073741811;
              DebugTraceError(
                3221225485LL,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                1120);
              return v15;
            case 65538:
            case 65539:
            case 65540:
            case 65541:
            case 65542:
              goto LABEL_8;
            case 65545:
              *a9 = a3;
              if ( v11 && !a7 )
                return 0;
              if ( a3 > a8 )
                return (unsigned int)-1073741789;
              if ( a5 || a6 || a10 || a3 + v11 < v11 || a3 + a7 < a7 )
              {
                v15 = -1073741811;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                {
                  WPP_SF_sDsd(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    a10,
                    a3,
                    (unsigned int)"Status",
                    13,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                    132);
                }
              }
              else
              {
                v42 = validateAuthCipherModeInfo(a4);
                if ( v42
                  && (v44 = *(_QWORD *)(v42 + 8)) != 0
                  && *(_DWORD *)(v42 + 16) == 12
                  && (v47 = *(_QWORD *)(v42 + 40)) != 0
                  && *(_DWORD *)(v42 + 48) == 16
                  && *(_DWORD *)(v42 + 80) == v43 )
                {
                  if ( !(unsigned int)SymCryptChaCha20Poly1305Decrypt(
                                        (int)v45 + 60,
                                        *(_DWORD *)(v45 + 56),
                                        v44,
                                        12,
                                        *(_QWORD *)(v42 + 24),
                                        *(unsigned int *)(v42 + 32),
                                        v11,
                                        a7,
                                        v46,
                                        v47,
                                        16) )
                    return 0;
                  v15 = -1073700862;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                  {
                    WPP_SF_sDsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 3),
                      v48,
                      v49,
                      (unsigned int)"Status",
                      2,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                      165);
                  }
                }
                else
                {
                  v15 = -1073741811;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                  {
                    WPP_SF_sDsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 3),
                      v43,
                      v44,
                      (unsigned int)"Status",
                      13,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                      146);
                  }
                }
              }
              break;
            default:
              v15 = -1073741637;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
              {
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  a10,
                  a3,
                  (unsigned int)"Status",
                  187,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                  243);
              }
              return v15;
          }
        }
      }
      else
      {
        v15 = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            a10,
            a3,
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
            58);
      }
    }
    else
    {
      v15 = -1073741811;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          a2,
          a3,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
          40);
    }
  }
  else
  {
    v15 = -1073741816;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        a2,
        a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
        30);
  }
  return v15;
}

```

## disassembly

```asm
0x180008850  push    rbp
0x180008852  push    rbx
0x180008853  push    rsi
0x180008854  push    rdi
0x180008855  push    r12
0x180008857  push    r13
0x180008859  push    r14
0x18000885b  push    r15
0x18000885d  lea     rbp, [rsp-328h]
0x180008865  sub     rsp, 428h
0x18000886c  mov     rax, cs:__security_cookie
0x180008873  xor     rax, rsp
0x180008876  mov     [rbp+360h+var_50], rax
0x18000887d  mov     r14, [rbp+360h+arg_30]
0x180008884  mov     rbx, r9
0x180008887  mov     rsi, [rbp+360h+arg_20]
0x18000888e  mov     r12, rdx
0x180008891  mov     r11d, [rbp+360h+arg_38]
0x180008898  mov     r10, rcx
0x18000889b  mov     r9, [rbp+360h+arg_40]
0x1800088a2  mov     [rsp+460h+var_3E8], r14
0x1800088a7  mov     [rbp+360h+var_3E0], rdx
0x1800088ab  test    rcx, rcx
0x1800088ae  jz      loc_180008CB4
0x1800088b4  cmp     dword ptr [rcx+4], 4D53534Bh
0x1800088bb  jnz     loc_180008CB4
0x1800088c1  mov     eax, [rcx+0Ch]
0x1800088c4  sub     eax, 4
0x1800088c7  cmp     eax, 1
0x1800088ca  ja      loc_180008970
0x1800088d0  mov     edx, [rbp+360h+arg_48]
0x1800088d6  test    edx, 0FFFFFEB8h
0x1800088dc  jnz     loc_180008F5B
0x1800088e2  mov     rax, [rcx+20h]
0x1800088e6  mov     ecx, [rax+24h]
0x1800088e9  not     ecx
0x1800088eb  and     ecx, edx
0x1800088ed  test    cl, 40h
0x1800088f0  jnz     loc_180008F5B
0x1800088f6  test    r9, r9
0x1800088f9  jz      loc_180008FA3
0x1800088ff  mov     eax, [r10+8]
0x180008903  cmp     eax, 10007h
0x180008908  jnz     loc_1800089C6
0x18000890e  mov     dword ptr [rsp+460h+var_418], edx; jumptable 000000018000903C cases 65538-65542
0x180008912  mov     rcx, r10
0x180008915  mov     [rsp+460h+var_420], r9
0x18000891a  mov     rdx, rbx
0x18000891d  mov     r9d, [rbp+360h+arg_28]
0x180008924  mov     dword ptr [rsp+460h+var_428], r11d
0x180008929  mov     [rsp+460h+var_430], r14
0x18000892e  mov     dword ptr [rsp+460h+var_438], r8d
0x180008933  mov     r8, rsi
0x180008936  mov     [rsp+460h+var_440], r12
0x18000893b  call    MSBlockDecrypt
0x180008940  mov     ebx, eax
0x180008942  test    eax, eax
0x180008944  js      loc_180008FEB
0x18000894a  mov     eax, ebx
0x18000894c  mov     rcx, [rbp+360h+var_50]
0x180008953  xor     rcx, rsp; StackCookie
0x180008956  call    __security_check_cookie
0x18000895b  add     rsp, 428h
0x180008962  pop     r15
0x180008964  pop     r14
0x180008966  pop     r13
0x180008968  pop     r12
0x18000896a  pop     rdi
0x18000896b  pop     rsi
0x18000896c  pop     rbx
0x18000896d  pop     rbp
0x18000896e  retn
0x180008970  cmp     dword ptr [rcx+8], 10009h
0x180008977  jz      loc_1800088D0
0x18000897d  test    rbx, rbx
0x180008980  jz      loc_1800088D0
0x180008986  mov     ebx, 0C000000Dh
0x18000898b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008992  lea     rax, WPP_GLOBAL_Control
0x180008999  cmp     rcx, rax
0x18000899c  jz      short loc_18000894A
0x18000899e  mov     eax, [rcx+2Ch]
0x1800089a1  test    al, 1
0x1800089a3  jz      short loc_18000894A
0x1800089a5  mov     dword ptr [rsp+460h+var_430], 428h
0x1800089ad  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800089b4  mov     [rsp+460h+var_438], rax
0x1800089b9  mov     dword ptr [rsp+460h+var_440], 0C000000Dh
0x1800089c1  jmp     loc_180008C9F
0x1800089c6  cmp     eax, 10008h
0x1800089cb  jnz     loc_180008C4E
0x1800089d1  test    edx, 0FFFFFFBFh
0x1800089d7  jnz     loc_180008F13
0x1800089dd  mov     ecx, [r10+14h]
0x1800089e1  test    ecx, ecx
0x1800089e3  jz      loc_180008F13
0x1800089e9  xor     edx, edx; Val
0x1800089eb  mov     eax, r8d
0x1800089ee  div     ecx
0x1800089f0  test    edx, edx
0x1800089f2  jnz     loc_180008F13
0x1800089f8  test    r12, r12
0x1800089fb  jz      loc_180008F13
0x180008a01  test    rsi, rsi
0x180008a04  jz      loc_180008F13
0x180008a0a  cmp     [rbp+360h+arg_28], 8
0x180008a11  jnz     loc_180008F13
0x180008a17  mov     edi, r8d
0x180008a1a  lea     rax, [rdi+r12]
0x180008a1e  cmp     rax, r12
0x180008a21  jb      loc_180008F13
0x180008a27  lea     rax, [r14+r11]
0x180008a2b  cmp     rax, r14
0x180008a2e  jb      loc_180008F13
0x180008a34  mov     [r9], r8d
0x180008a37  test    r14, r14
0x180008a3a  jz      loc_1800091C4
0x180008a40  cmp     r8d, r11d
0x180008a43  ja      loc_180009266
0x180008a49  mov     r15d, [r10+14h]
0x180008a4d  xor     ebx, ebx
0x180008a4f  mov     [rbp+360h+var_3D8], r15
0x180008a53  cmp     r15, 10h
0x180008a57  jb      loc_18000894A
0x180008a5d  mov     rsi, [rsi]
0x180008a60  lea     rcx, [rbp+360h+XStateSave]; void *
0x180008a64  mov     r8d, 40h ; '@'; Size
0x180008a6a  lea     r13, [r10+80h]
0x180008a71  call    memset
0x180008a76  mov     eax, cs:g_SymCryptCpuFeaturesNotPresent
0x180008a7c  test    eax, 816h
0x180008a81  jnz     loc_180008B7E
0x180008a87  test    al, 10h
0x180008a89  jnz     loc_180009298
0x180008a8f  mov     rax, cr8
0x180008a93  cmp     al, 2
0x180008a95  ja      loc_180008B7E
0x180008a9b  lea     rdx, [rbp+360h+XStateSave]; XStateSave
0x180008a9f  mov     ecx, 4; Mask
0x180008aa4  call    cs:__imp_KeSaveExtendedProcessorState
0x180008aab  nop     dword ptr [rax+rax+00h]
0x180008ab0  test    eax, eax
0x180008ab2  js      loc_180008B7E
0x180008ab8  cmp     rdi, r15
0x180008abb  jb      loc_180008B5B
0x180008ac1  lea     rcx, [r13+1F0h]
0x180008ac8  xor     eax, eax
0x180008aca  mov     rbx, rax
0x180008acd  nop     dword ptr [rax]
0x180008ad0  mov     [rbp+rbx+360h+var_380], rsi
0x180008ad5  sub     rdi, r15
0x180008ad8  mov     [rbp+rbx+360h+var_378], rax
0x180008add  inc     rsi
0x180008ae0  add     rbx, 10h
0x180008ae4  cmp     rbx, 100h
0x180008aeb  jnb     short loc_180008AF2
0x180008aed  cmp     rdi, r15
0x180008af0  jnb     short loc_180008AD0
0x180008af2  mov     r9, rbx
0x180008af5  mov     [rsp+460h+var_3F8], rsi
0x180008afa  lea     r8, [rbp+360h+var_380]
0x180008afe  lea     rdx, [rbp+360h+var_380]
0x180008b02  call    SymCryptAesEcbEncryptXmm
0x180008b07  xor     eax, eax
0x180008b09  test    rbx, rbx
0x180008b0c  jz      short loc_180008B49
0x180008b0e  mov     esi, eax
0x180008b10  lea     rdx, [rbp+360h+var_380]
0x180008b14  mov     [rsp+460h+var_438], r15
0x180008b19  add     rdx, rsi
0x180008b1c  mov     [rsp+460h+var_440], r14
0x180008b21  mov     r9, r12
0x180008b24  lea     r8, [rbp+360h+var_280]
0x180008b2b  mov     rcx, r13
0x180008b2e  call    SymCryptXtsAesDecryptDataUnitYmm_2048
0x180008b33  add     r12, r15
0x180008b36  add     r14, r15
0x180008b39  add     rsi, 10h
0x180008b3d  cmp     rsi, rbx
0x180008b40  jb      short loc_180008B10
0x180008b42  mov     rsi, [rsp+460h+var_3F8]
0x180008b47  xor     eax, eax
0x180008b49  lea     rcx, [r13+1F0h]
0x180008b50  cmp     rdi, r15
0x180008b53  jnb     loc_180008ACA
0x180008b59  xor     ebx, ebx
0x180008b5b  mov     edx, 200h
0x180008b60  lea     rcx, [rbp+360h+var_380]
0x180008b64  call    SymCryptWipeAsm
0x180008b69  lea     rcx, [rbp+360h+XStateSave]; XStateSave
0x180008b6d  call    cs:__imp_KeRestoreExtendedProcessorState
0x180008b74  nop     dword ptr [rax+rax+00h]
0x180008b79  jmp     loc_18000894A
0x180008b7e  mov     eax, cs:g_SymCryptCpuFeaturesNotPresent
0x180008b84  test    al, 6
0x180008b86  jnz     loc_180008CF9
0x180008b8c  cmp     rdi, r15
0x180008b8f  jb      loc_180008C3B
0x180008b95  lea     rcx, [r13+1F0h]
0x180008b9c  xor     eax, eax
0x180008b9e  mov     rbx, rax
0x180008ba1  nop     dword ptr [rax+00h]
0x180008ba5  nop     word ptr [rax+rax+00000000h]
0x180008bb0  mov     [rbp+rbx+360h+var_380], rsi
0x180008bb5  sub     rdi, r15
0x180008bb8  mov     [rbp+rbx+360h+var_378], rax
0x180008bbd  inc     rsi
0x180008bc0  add     rbx, 10h
0x180008bc4  cmp     rbx, 100h
0x180008bcb  jnb     short loc_180008BD2
0x180008bcd  cmp     rdi, r15
0x180008bd0  jnb     short loc_180008BB0
0x180008bd2  mov     r9, rbx
0x180008bd5  mov     [rsp+460h+var_3F8], rsi
0x180008bda  lea     r8, [rbp+360h+var_380]
0x180008bde  lea     rdx, [rbp+360h+var_380]
0x180008be2  call    SymCryptAesEcbEncryptXmm
0x180008be7  xor     eax, eax
0x180008be9  test    rbx, rbx
0x180008bec  jz      short loc_180008C29
0x180008bee  mov     esi, eax
0x180008bf0  lea     rdx, [rbp+360h+var_380]
0x180008bf4  mov     [rsp+460h+var_438], r15
0x180008bf9  add     rdx, rsi
0x180008bfc  mov     [rsp+460h+var_440], r14
0x180008c01  mov     r9, r12
0x180008c04  lea     r8, [rbp+360h+var_280]
0x180008c0b  mov     rcx, r13
0x180008c0e  call    SymCryptXtsAesDecryptDataUnitXmm
0x180008c13  add     r12, r15
0x180008c16  add     r14, r15
0x180008c19  add     rsi, 10h
0x180008c1d  cmp     rsi, rbx
0x180008c20  jb      short loc_180008BF0
0x180008c22  mov     rsi, [rsp+460h+var_3F8]
0x180008c27  xor     eax, eax
0x180008c29  lea     rcx, [r13+1F0h]
0x180008c30  cmp     rdi, r15
0x180008c33  jnb     loc_180008B9E
0x180008c39  xor     ebx, ebx
0x180008c3b  mov     edx, 200h
0x180008c40  lea     rcx, [rbp+360h+var_380]
0x180008c44  call    SymCryptWipeAsm
0x180008c49  jmp     loc_18000894A
0x180008c4e  add     eax, 0FFFEFFFFh; switch 9 cases
0x180008c53  cmp     eax, 8
0x180008c56  jbe     loc_18000902B
0x180008c5c  mov     ebx, 0C00000BBh; jumptable 000000018000903C default case, cases 65543,65544
0x180008c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c68  lea     rax, WPP_GLOBAL_Control
0x180008c6f  cmp     rcx, rax
0x180008c72  jz      loc_18000894A
0x180008c78  mov     eax, [rcx+2Ch]
0x180008c7b  test    al, 1
0x180008c7d  jz      loc_18000894A
0x180008c83  mov     dword ptr [rsp+460h+var_430], 4F3h
0x180008c8b  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008c92  mov     [rsp+460h+var_438], rax
0x180008c97  mov     dword ptr [rsp+460h+var_440], 0C00000BBh
0x180008c9f  mov     rcx, [rcx+18h]
0x180008ca3  lea     r9, aStatus; "Status"
0x180008caa  call    WPP_SF_sDsd
0x180008caf  jmp     loc_18000894A
0x180008cb4  mov     ebx, 0C0000008h
0x180008cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cc0  lea     rax, WPP_GLOBAL_Control
0x180008cc7  cmp     rcx, rax
0x180008cca  jz      loc_18000894A
0x180008cd0  mov     eax, [rcx+2Ch]
0x180008cd3  test    al, 1
0x180008cd5  jz      loc_18000894A
0x180008cdb  mov     dword ptr [rsp+460h+var_430], 41Eh
0x180008ce3  lea     rax, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008cea  mov     [rsp+460h+var_438], rax
0x180008cef  mov     dword ptr [rsp+460h+var_440], 0C0000008h
0x180008cf7  jmp     short loc_180008C9F
0x180008cf9  cmp     rdi, r15
0x180008cfc  jb      loc_180008F02
0x180008d02  lea     rax, [r13+1F0h]
0x180008d09  xor     ecx, ecx
0x180008d0b  mov     rbx, rcx
0x180008d0e  xchg    ax, ax
0x180008d10  mov     [rbp+rbx+360h+var_150], rsi
0x180008d18  sub     rdi, r15
0x180008d1b  mov     [rbp+rbx+360h+var_148], rcx
0x180008d23  inc     rsi
0x180008d26  add     rbx, 10h
0x180008d2a  cmp     rbx, 100h
0x180008d31  jnb     short loc_180008D38
0x180008d33  cmp     rdi, r15
0x180008d36  jnb     short loc_180008D10
0x180008d38  mov     r9, rbx
0x180008d3b  mov     [rbp+360h+var_3D0], rbx
0x180008d3f  lea     r8, [rbp+360h+var_150]
0x180008d46  mov     [rsp+460h+var_3F8], rsi
0x180008d4b  lea     rdx, [rbp+360h+var_150]
0x180008d52  mov     [rbp+360h+var_3C8], rdi
0x180008d56  mov     rcx, rax
0x180008d59  call    SymCryptAesEcbEncryptAsm
0x180008d5e  xor     ecx, ecx
  ... truncated ...
```
