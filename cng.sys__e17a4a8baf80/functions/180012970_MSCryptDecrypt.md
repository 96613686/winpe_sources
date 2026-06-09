# MSCryptDecrypt

- ea: `0x180012970`
- end: `0x1800133c3`
- name: `MSCryptDecrypt`
- size: `2643`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800210a0`
- `0x180089498`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x180012970`
- `0x1800133d0`
- `0x1800138e0`
- `0x180013ec8`
- `0x180014680`
- `0x180016b40`
- `0x180016b80`
- `0x18001cad0`
- `0x18004d080`
- `0x180052158`
- `0x180052e7c`
- `0x1800564d0`
- `0x180056a20`
- `0x1800a4260`
- `0x1800a4380`
- `0x1800a45c0`

## import_xrefs

- `ntoskrnl!KeRestoreExtendedProcessorState` at `0x180012c8d`
- `ntoskrnl!KeRestoreExtendedProcessorState` at `0x180012c8d`
- `ntoskrnl!KeSaveExtendedProcessorState` at `0x180012bc4`
- `ntoskrnl!KeSaveExtendedProcessorState` at `0x180012bc4`

## string_xrefs

- `0x180012acd`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180012dab`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180012e03`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180013062`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800130aa`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800130f2`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180013136`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180013274`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180013325`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18001336d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180013396`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptDecrypt(
        __int64 a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 *a5,
        int a6,
        unsigned __int64 a7,
        unsigned int a8,
        _DWORD *a9,
        unsigned int a10)
{
  __int64 v10; // r14
  unsigned __int64 v11; // r12
  unsigned int v13; // edx
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
            52);
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
                193);
          }
        }
        else if ( v14 == 65544 )
        {
          if ( (a10 & 0xFFFFFFBF) == 0
            && (v18 = *(_DWORD *)(a1 + 20)) != 0
            && (v13 = (unsigned int)a3 % v18) == 0
            && v11
            && a5
            && a6 == 8
            && (v19 = (unsigned int)a3, (unsigned int)a3 + v11 >= v11)
            && a7 + a8 >= a7 )
          {
            *a9 = a3;
            if ( a7 )
            {
              if ( (unsigned int)a3 > a8 )
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
                214);
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
              if ( (unsigned int)a3 > a8 )
                return (unsigned int)-1073741789;
              if ( !(_DWORD)a3 )
                return 0;
              if ( v11 && !a5 && (unsigned int)a3 + v11 >= v11 && (unsigned int)a3 + a7 >= a7 )
              {
                SymCryptRc4Crypt(a1 + 320, v11, a7);
                return 0;
              }
              v15 = -1073741811;
              DebugTraceError(
                3221225485LL,
                "Status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                1121);
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
              if ( (unsigned int)a3 > a8 )
                return (unsigned int)-1073741789;
              if ( a5 || a6 || a10 || (unsigned int)a3 + v11 < v11 || (unsigned int)a3 + a7 < a7 )
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
                    133);
                }
              }
              else
              {
                v42 = validateAuthCipherModeInfo(a4, a10, a3, a9);
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
                      166);
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
                      147);
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
                  244);
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
            59);
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
          41);
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
        31);
  }
  return v15;
}

```

## disassembly

```asm
0x180012970  push    rbp
0x180012972  push    rbx
0x180012973  push    rsi
0x180012974  push    rdi
0x180012975  push    r12
0x180012977  push    r13
0x180012979  push    r14
0x18001297b  push    r15
0x18001297d  lea     rbp, [rsp-328h]
0x180012985  sub     rsp, 428h
0x18001298c  mov     rax, cs:__security_cookie
0x180012993  xor     rax, rsp
0x180012996  mov     [rbp+360h+var_50], rax
0x18001299d  mov     r14, [rbp+360h+arg_30]
0x1800129a4  mov     rbx, r9
0x1800129a7  mov     rsi, [rbp+360h+arg_20]
0x1800129ae  mov     r12, rdx
0x1800129b1  mov     r11d, [rbp+360h+arg_38]
0x1800129b8  mov     r10, rcx
0x1800129bb  mov     r9, [rbp+360h+arg_40]
0x1800129c2  mov     [rsp+460h+var_3E8], r14
0x1800129c7  mov     [rbp+360h+var_3E0], rdx
0x1800129cb  test    rcx, rcx
0x1800129ce  jz      loc_180012DD4
0x1800129d4  cmp     dword ptr [rcx+4], 4D53534Bh
0x1800129db  jnz     loc_180012DD4
0x1800129e1  mov     eax, [rcx+0Ch]
0x1800129e4  sub     eax, 4
0x1800129e7  cmp     eax, 1
0x1800129ea  ja      loc_180012A90
0x1800129f0  mov     edx, [rbp+360h+arg_48]
0x1800129f6  test    edx, 0FFFFFEB8h
0x1800129fc  jnz     loc_18001307B
0x180012a02  mov     rax, [rcx+20h]
0x180012a06  mov     ecx, [rax+24h]
0x180012a09  not     ecx
0x180012a0b  and     ecx, edx
0x180012a0d  test    cl, 40h
0x180012a10  jnz     loc_18001307B
0x180012a16  test    r9, r9
0x180012a19  jz      loc_1800130C3
0x180012a1f  mov     eax, [r10+8]
0x180012a23  cmp     eax, 10007h
0x180012a28  jnz     loc_180012AE6
0x180012a2e  mov     dword ptr [rsp+460h+var_418], edx; jumptable 000000018001315C cases 65538-65542
0x180012a32  mov     rcx, r10
0x180012a35  mov     [rsp+460h+var_420], r9
0x180012a3a  mov     rdx, rbx
0x180012a3d  mov     r9d, [rbp+360h+arg_28]
0x180012a44  mov     dword ptr [rsp+460h+var_428], r11d
0x180012a49  mov     [rsp+460h+var_430], r14
0x180012a4e  mov     dword ptr [rsp+460h+var_438], r8d
0x180012a53  mov     r8, rsi
0x180012a56  mov     [rsp+460h+var_440], r12
0x180012a5b  call    MSBlockDecrypt
0x180012a60  mov     ebx, eax
0x180012a62  test    eax, eax
0x180012a64  js      loc_18001310B
0x180012a6a  mov     eax, ebx
0x180012a6c  mov     rcx, [rbp+360h+var_50]
0x180012a73  xor     rcx, rsp; StackCookie
0x180012a76  call    __security_check_cookie
0x180012a7b  add     rsp, 428h
0x180012a82  pop     r15
0x180012a84  pop     r14
0x180012a86  pop     r13
0x180012a88  pop     r12
0x180012a8a  pop     rdi
0x180012a8b  pop     rsi
0x180012a8c  pop     rbx
0x180012a8d  pop     rbp
0x180012a8e  retn
0x180012a90  cmp     dword ptr [rcx+8], 10009h
0x180012a97  jz      loc_1800129F0
0x180012a9d  test    rbx, rbx
0x180012aa0  jz      loc_1800129F0
0x180012aa6  mov     ebx, 0C000000Dh
0x180012aab  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ab2  lea     rax, WPP_GLOBAL_Control
0x180012ab9  cmp     rcx, rax
0x180012abc  jz      short loc_180012A6A
0x180012abe  mov     eax, [rcx+2Ch]
0x180012ac1  test    al, 1
0x180012ac3  jz      short loc_180012A6A
0x180012ac5  mov     dword ptr [rsp+460h+var_430], 429h
0x180012acd  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012ad4  mov     [rsp+460h+var_438], rax
0x180012ad9  mov     dword ptr [rsp+460h+var_440], 0C000000Dh
0x180012ae1  jmp     loc_180012DBF
0x180012ae6  cmp     eax, 10008h
0x180012aeb  jnz     loc_180012D6E
0x180012af1  test    edx, 0FFFFFFBFh
0x180012af7  jnz     loc_180013033
0x180012afd  mov     ecx, [r10+14h]
0x180012b01  test    ecx, ecx
0x180012b03  jz      loc_180013033
0x180012b09  xor     edx, edx; Val
0x180012b0b  mov     eax, r8d
0x180012b0e  div     ecx
0x180012b10  test    edx, edx
0x180012b12  jnz     loc_180013033
0x180012b18  test    r12, r12
0x180012b1b  jz      loc_180013033
0x180012b21  test    rsi, rsi
0x180012b24  jz      loc_180013033
0x180012b2a  cmp     [rbp+360h+arg_28], 8
0x180012b31  jnz     loc_180013033
0x180012b37  mov     edi, r8d
0x180012b3a  lea     rax, [rdi+r12]
0x180012b3e  cmp     rax, r12
0x180012b41  jb      loc_180013033
0x180012b47  lea     rax, [r14+r11]
0x180012b4b  cmp     rax, r14
0x180012b4e  jb      loc_180013033
0x180012b54  mov     [r9], r8d
0x180012b57  test    r14, r14
0x180012b5a  jz      loc_1800132E4
0x180012b60  cmp     r8d, r11d
0x180012b63  ja      loc_180013386
0x180012b69  mov     r15d, [r10+14h]
0x180012b6d  xor     ebx, ebx
0x180012b6f  mov     [rbp+360h+var_3D8], r15
0x180012b73  cmp     r15, 10h
0x180012b77  jb      loc_180012A6A
0x180012b7d  mov     rsi, [rsi]
0x180012b80  lea     rcx, [rbp+360h+XStateSave]; void *
0x180012b84  mov     r8d, 40h ; '@'; Size
0x180012b8a  lea     r13, [r10+80h]
0x180012b91  call    memset
0x180012b96  mov     eax, cs:g_SymCryptCpuFeaturesNotPresent
0x180012b9c  test    eax, 816h
0x180012ba1  jnz     loc_180012C9E
0x180012ba7  test    al, 10h
0x180012ba9  jnz     loc_1800133B8
0x180012baf  mov     rax, cr8
0x180012bb3  cmp     al, 2
0x180012bb5  ja      loc_180012C9E
0x180012bbb  lea     rdx, [rbp+360h+XStateSave]; XStateSave
0x180012bbf  mov     ecx, 4; Mask
0x180012bc4  call    cs:__imp_KeSaveExtendedProcessorState
0x180012bcb  nop     dword ptr [rax+rax+00h]
0x180012bd0  test    eax, eax
0x180012bd2  js      loc_180012C9E
0x180012bd8  cmp     rdi, r15
0x180012bdb  jb      loc_180012C7B
0x180012be1  lea     rcx, [r13+1F0h]
0x180012be8  xor     eax, eax
0x180012bea  mov     rbx, rax
0x180012bed  nop     dword ptr [rax]
0x180012bf0  mov     [rbp+rbx+360h+var_380], rsi
0x180012bf5  sub     rdi, r15
0x180012bf8  mov     [rbp+rbx+360h+var_378], rax
0x180012bfd  inc     rsi
0x180012c00  add     rbx, 10h
0x180012c04  cmp     rbx, 100h
0x180012c0b  jnb     short loc_180012C12
0x180012c0d  cmp     rdi, r15
0x180012c10  jnb     short loc_180012BF0
0x180012c12  mov     r9, rbx
0x180012c15  mov     [rsp+460h+var_3F8], rsi
0x180012c1a  lea     r8, [rbp+360h+var_380]
0x180012c1e  lea     rdx, [rbp+360h+var_380]
0x180012c22  call    SymCryptAesEcbEncryptXmm
0x180012c27  xor     eax, eax
0x180012c29  test    rbx, rbx
0x180012c2c  jz      short loc_180012C69
0x180012c2e  mov     esi, eax
0x180012c30  lea     rdx, [rbp+360h+var_380]
0x180012c34  mov     [rsp+460h+var_438], r15
0x180012c39  add     rdx, rsi
0x180012c3c  mov     [rsp+460h+var_440], r14
0x180012c41  mov     r9, r12
0x180012c44  lea     r8, [rbp+360h+var_280]
0x180012c4b  mov     rcx, r13
0x180012c4e  call    SymCryptXtsAesDecryptDataUnitYmm_2048
0x180012c53  add     r12, r15
0x180012c56  add     r14, r15
0x180012c59  add     rsi, 10h
0x180012c5d  cmp     rsi, rbx
0x180012c60  jb      short loc_180012C30
0x180012c62  mov     rsi, [rsp+460h+var_3F8]
0x180012c67  xor     eax, eax
0x180012c69  lea     rcx, [r13+1F0h]
0x180012c70  cmp     rdi, r15
0x180012c73  jnb     loc_180012BEA
0x180012c79  xor     ebx, ebx
0x180012c7b  mov     edx, 200h
0x180012c80  lea     rcx, [rbp+360h+var_380]
0x180012c84  call    SymCryptWipeAsm
0x180012c89  lea     rcx, [rbp+360h+XStateSave]; XStateSave
0x180012c8d  call    cs:__imp_KeRestoreExtendedProcessorState
0x180012c94  nop     dword ptr [rax+rax+00h]
0x180012c99  jmp     loc_180012A6A
0x180012c9e  mov     eax, cs:g_SymCryptCpuFeaturesNotPresent
0x180012ca4  test    al, 6
0x180012ca6  jnz     loc_180012E19
0x180012cac  cmp     rdi, r15
0x180012caf  jb      loc_180012D5B
0x180012cb5  lea     rcx, [r13+1F0h]
0x180012cbc  xor     eax, eax
0x180012cbe  mov     rbx, rax
0x180012cc1  nop     dword ptr [rax+00h]
0x180012cc5  nop     word ptr [rax+rax+00000000h]
0x180012cd0  mov     [rbp+rbx+360h+var_380], rsi
0x180012cd5  sub     rdi, r15
0x180012cd8  mov     [rbp+rbx+360h+var_378], rax
0x180012cdd  inc     rsi
0x180012ce0  add     rbx, 10h
0x180012ce4  cmp     rbx, 100h
0x180012ceb  jnb     short loc_180012CF2
0x180012ced  cmp     rdi, r15
0x180012cf0  jnb     short loc_180012CD0
0x180012cf2  mov     r9, rbx
0x180012cf5  mov     [rsp+460h+var_3F8], rsi
0x180012cfa  lea     r8, [rbp+360h+var_380]
0x180012cfe  lea     rdx, [rbp+360h+var_380]
0x180012d02  call    SymCryptAesEcbEncryptXmm
0x180012d07  xor     eax, eax
0x180012d09  test    rbx, rbx
0x180012d0c  jz      short loc_180012D49
0x180012d0e  mov     esi, eax
0x180012d10  lea     rdx, [rbp+360h+var_380]
0x180012d14  mov     [rsp+460h+var_438], r15
0x180012d19  add     rdx, rsi
0x180012d1c  mov     [rsp+460h+var_440], r14
0x180012d21  mov     r9, r12
0x180012d24  lea     r8, [rbp+360h+var_280]
0x180012d2b  mov     rcx, r13
0x180012d2e  call    SymCryptXtsAesDecryptDataUnitXmm
0x180012d33  add     r12, r15
0x180012d36  add     r14, r15
0x180012d39  add     rsi, 10h
0x180012d3d  cmp     rsi, rbx
0x180012d40  jb      short loc_180012D10
0x180012d42  mov     rsi, [rsp+460h+var_3F8]
0x180012d47  xor     eax, eax
0x180012d49  lea     rcx, [r13+1F0h]
0x180012d50  cmp     rdi, r15
0x180012d53  jnb     loc_180012CBE
0x180012d59  xor     ebx, ebx
0x180012d5b  mov     edx, 200h
0x180012d60  lea     rcx, [rbp+360h+var_380]
0x180012d64  call    SymCryptWipeAsm
0x180012d69  jmp     loc_180012A6A
0x180012d6e  add     eax, 0FFFEFFFFh; switch 9 cases
0x180012d73  cmp     eax, 8
0x180012d76  jbe     loc_18001314B
0x180012d7c  mov     ebx, 0C00000BBh; jumptable 000000018001315C default case, cases 65543,65544
0x180012d81  mov     rcx, cs:WPP_GLOBAL_Control
0x180012d88  lea     rax, WPP_GLOBAL_Control
0x180012d8f  cmp     rcx, rax
0x180012d92  jz      loc_180012A6A
0x180012d98  mov     eax, [rcx+2Ch]
0x180012d9b  test    al, 1
0x180012d9d  jz      loc_180012A6A
0x180012da3  mov     dword ptr [rsp+460h+var_430], 4F4h
0x180012dab  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012db2  mov     [rsp+460h+var_438], rax
0x180012db7  mov     dword ptr [rsp+460h+var_440], 0C00000BBh
0x180012dbf  mov     rcx, [rcx+18h]
0x180012dc3  lea     r9, aStatus; "Status"
0x180012dca  call    WPP_SF_sDsd
0x180012dcf  jmp     loc_180012A6A
0x180012dd4  mov     ebx, 0C0000008h
0x180012dd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180012de0  lea     rax, WPP_GLOBAL_Control
0x180012de7  cmp     rcx, rax
0x180012dea  jz      loc_180012A6A
0x180012df0  mov     eax, [rcx+2Ch]
0x180012df3  test    al, 1
0x180012df5  jz      loc_180012A6A
0x180012dfb  mov     dword ptr [rsp+460h+var_430], 41Fh
0x180012e03  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012e0a  mov     [rsp+460h+var_438], rax
0x180012e0f  mov     dword ptr [rsp+460h+var_440], 0C0000008h
0x180012e17  jmp     short loc_180012DBF
0x180012e19  cmp     rdi, r15
0x180012e1c  jb      loc_180013022
0x180012e22  lea     rax, [r13+1F0h]
0x180012e29  xor     ecx, ecx
0x180012e2b  mov     rbx, rcx
0x180012e2e  xchg    ax, ax
0x180012e30  mov     [rbp+rbx+360h+var_150], rsi
0x180012e38  sub     rdi, r15
0x180012e3b  mov     [rbp+rbx+360h+var_148], rcx
0x180012e43  inc     rsi
0x180012e46  add     rbx, 10h
0x180012e4a  cmp     rbx, 100h
0x180012e51  jnb     short loc_180012E58
0x180012e53  cmp     rdi, r15
0x180012e56  jnb     short loc_180012E30
0x180012e58  mov     r9, rbx
0x180012e5b  mov     [rbp+360h+var_3D0], rbx
0x180012e5f  lea     r8, [rbp+360h+var_150]
0x180012e66  mov     [rsp+460h+var_3F8], rsi
0x180012e6b  lea     rdx, [rbp+360h+var_150]
0x180012e72  mov     [rbp+360h+var_3C8], rdi
0x180012e76  mov     rcx, rax
0x180012e79  call    SymCryptAesEcbEncryptAsm
0x180012e7e  xor     ecx, ecx
  ... truncated ...
```
