# MSCryptEncrypt

- ea: `0x180014d10`
- end: `0x180015605`
- name: `MSCryptEncrypt`
- size: `2293`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180021480`

## callees

- `0x18001155c`
- `0x1800123d0`
- `0x180014680`
- `0x180014d10`
- `0x180015610`
- `0x180015b20`
- `0x180016108`
- `0x1800168c0`
- `0x180016b40`
- `0x180016b80`
- `0x180016c04`
- `0x180052e7c`
- `0x1800564d0`
- `0x1800a4260`
- `0x1800a4380`

## import_xrefs

- `ntoskrnl!KeRestoreExtendedProcessorState` at `0x180015072`
- `ntoskrnl!KeRestoreExtendedProcessorState` at `0x180015072`
- `ntoskrnl!KeSaveExtendedProcessorState` at `0x180014f8f`
- `ntoskrnl!KeSaveExtendedProcessorState` at `0x180014f8f`

## string_xrefs

- `0x1800151d0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180015256`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800152a6`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800153e4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180015429`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800154f7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x180015550`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800155ad`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x1800155d7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

## pseudocode

```c
__int64 __fastcall MSCryptEncrypt(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 *a5,
        int a6,
        unsigned __int64 a7,
        unsigned int a8,
        _DWORD *a9,
        unsigned int a10)
{
  unsigned __int64 v10; // r15
  __int64 v11; // r14
  unsigned __int64 v13; // r11
  __int64 v14; // r8
  int v15; // eax
  int v16; // r8d
  unsigned int v17; // r13d
  _QWORD *v19; // rcx
  unsigned int v20; // ecx
  unsigned __int64 v21; // rsi
  unsigned __int64 v22; // rdi
  __int64 v23; // rbp
  __int64 v24; // rbx
  __int64 v25; // rax
  unsigned __int64 v26; // rbx
  unsigned __int64 v27; // r12
  __int64 v28; // rax
  unsigned __int64 v29; // r12
  unsigned __int64 v30; // rbx
  int v31; // edx
  __int64 v32; // rax
  int v33; // edx
  __int64 v34; // r8
  __int64 v35; // r10
  __int64 v36; // r11
  __int64 v37; // rbx
  int v38; // edx
  int v39; // r8d
  char v40; // [rsp+30h] [rbp-2E8h]
  _QWORD v41[2]; // [rsp+60h] [rbp-2B8h] BYREF
  __int64 v42; // [rsp+70h] [rbp-2A8h]
  _BYTE XStateSave[64]; // [rsp+80h] [rbp-298h] BYREF
  _QWORD v44[32]; // [rsp+C0h] [rbp-258h] BYREF
  _BYTE v45[256]; // [rsp+1C0h] [rbp-158h] BYREF

  v10 = a2;
  v11 = a7;
  v13 = a3;
  if ( a1 && *(_DWORD *)(a1 + 4) == 1297306443 )
  {
    v14 = *(unsigned int *)(a1 + 12);
    if ( (unsigned int)(v14 - 4) <= 1 || *(_DWORD *)(a1 + 8) == 65545 || !a4 )
    {
      LODWORD(a2) = a10;
      if ( (a10 & 0xFFFFFF98) != 0
        || ((unsigned __int8)a10 & (unsigned __int8)~*(_BYTE *)(*(_QWORD *)(a1 + 32) + 36LL) & 0x40) != 0 )
      {
        v17 = -1073741811;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        {
          v40 = 49;
          goto LABEL_60;
        }
      }
      else if ( a9 )
      {
        if ( (a10 & 0x20) == 0 || *(_DWORD *)(a1 + 8) == 65538 && (_DWORD)v14 == 5 )
        {
          v15 = *(_DWORD *)(a1 + 8);
          if ( v15 == 65543 )
          {
LABEL_9:
            v17 = MSBlockEncrypt(a1, a4, (_DWORD)a5, a6, v10, v13, a7, a8, (__int64)a9, a10 & 1, a10);
            if ( (v17 & 0x80000000) != 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
            {
              v31 = *((_DWORD *)WPP_GLOBAL_Control + 11);
              if ( (v31 & 1) != 0 )
                WPP_SF_sDsd(
                  *((_QWORD *)WPP_GLOBAL_Control + 3),
                  v31,
                  v16,
                  (unsigned int)"Status",
                  v17,
                  (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                  201);
            }
          }
          else
          {
            switch ( v15 )
            {
              case 65537:
                *a9 = v13;
                if ( !a7 )
                  return 0;
                if ( (unsigned int)v13 > a8 )
                  goto LABEL_111;
                if ( !(_DWORD)v13 )
                  return 0;
                if ( v10 && !a5 && v13 + v10 >= v10 && v13 + a7 >= a7 )
                {
                  SymCryptRc4Crypt(a1 + 320, v10, a7);
                  return 0;
                }
                v17 = -1073741811;
                DebugTraceError(
                  3221225485LL,
                  "Status",
                  "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                  872);
                return v17;
              case 65538:
              case 65539:
              case 65540:
              case 65541:
              case 65542:
                goto LABEL_9;
              case 65544:
                if ( (a10 & 0xFFFFFFBF) == 0
                  && (v20 = *(_DWORD *)(a1 + 20)) != 0
                  && (LODWORD(a2) = (unsigned int)v13 % v20) == 0
                  && v10
                  && a5
                  && a6 == 8
                  && (v21 = v13, v13 + v10 >= v10)
                  && a7 + a8 >= a7 )
                {
                  *a9 = v13;
                  if ( !a7 )
                    return 0;
                  if ( (unsigned int)v13 > a8 )
                  {
LABEL_111:
                    v17 = -1073741789;
                  }
                  else
                  {
                    v22 = *(unsigned int *)(a1 + 20);
                    v17 = 0;
                    if ( v22 >= 0x10 )
                    {
                      v23 = *a5;
                      v24 = a1 + 128;
                      v42 = a1 + 128;
                      v41[0] = v23;
                      v41[1] = 0;
                      memset(XStateSave, 0, sizeof(XStateSave));
                      if ( (g_SymCryptCpuFeaturesNotPresent & 0x816) != 0 )
                        goto LABEL_42;
                      if ( (g_SymCryptCpuFeaturesNotPresent & 0x10) != 0 )
                        SymCryptFatal(0x206D6D79u);
                      if ( KeGetCurrentIrql() > 2u || KeSaveExtendedProcessorState(4u, (PXSTATE_SAVE)XStateSave) < 0 )
                      {
LABEL_42:
                        if ( (g_SymCryptCpuFeaturesNotPresent & 6) != 0 )
                        {
                          SymCryptXtsAesEncryptInternalAsm(v24, v22, (unsigned int)v41, v10, a7, v21);
                        }
                        else
                        {
                          if ( v21 >= v22 )
                          {
                            v28 = v24 + 496;
                            v41[0] = v24 + 496;
                            do
                            {
                              v29 = 0;
                              do
                              {
                                v44[v29 / 8] = v23;
                                v21 -= v22;
                                v44[v29 / 8 + 1] = 0;
                                ++v23;
                                v29 += 16LL;
                              }
                              while ( v29 < 0x100 && v21 >= v22 );
                              SymCryptAesEcbEncryptXmm(v28, v44, v44, v29);
                              v30 = 0;
                              if ( v29 )
                              {
                                do
                                {
                                  SymCryptXtsAesEncryptDataUnitXmm(v42, &v44[v30 / 8], v45, v10, v11, v22);
                                  v10 += v22;
                                  v11 += v22;
                                  v30 += 16LL;
                                }
                                while ( v30 < v29 );
                                v17 = 0;
                              }
                              v28 = v41[0];
                            }
                            while ( v21 >= v22 );
                          }
                          SymCryptWipeAsm(v44, 512);
                        }
                      }
                      else
                      {
                        if ( v21 >= v22 )
                        {
                          v25 = v24 + 496;
                          v41[0] = v24 + 496;
                          do
                          {
                            v26 = 0;
                            do
                            {
                              v44[v26 / 8] = v23;
                              v21 -= v22;
                              v44[v26 / 8 + 1] = 0;
                              ++v23;
                              v26 += 16LL;
                            }
                            while ( v26 < 0x100 && v21 >= v22 );
                            SymCryptAesEcbEncryptXmm(v25, v44, v44, v26);
                            v27 = 0;
                            if ( v26 )
                            {
                              do
                              {
                                SymCryptXtsAesEncryptDataUnitYmm_2048(
                                  v42,
                                  (unsigned int)&v44[v27 / 8],
                                  (unsigned int)v45,
                                  v10,
                                  v11,
                                  v22);
                                LODWORD(v10) = v22 + v10;
                                v11 += v22;
                                v27 += 16LL;
                              }
                              while ( v27 < v26 );
                              v17 = 0;
                            }
                            v25 = v41[0];
                          }
                          while ( v21 >= v22 );
                        }
                        SymCryptWipeAsm(v44, 512);
                        KeRestoreExtendedProcessorState((PXSTATE_SAVE)XStateSave);
                      }
                    }
                  }
                }
                else
                {
                  v17 = -1073741811;
                  v19 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                  {
                    v40 = -33;
                    goto LABEL_60;
                  }
                }
                break;
              case 65545:
                *a9 = v13;
                if ( v10 && !a7 )
                  return 0;
                if ( (unsigned int)v13 > a8 )
                  goto LABEL_111;
                if ( a5 || a6 || a10 || v13 + v10 < v10 || v13 + a7 < a7 )
                {
                  v17 = -1073741811;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                  {
                    WPP_SF_sDsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 3),
                      a10,
                      v14,
                      (unsigned int)"Status",
                      13,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                      140);
                  }
                }
                else
                {
                  v32 = validateAuthCipherModeInfo(a4, a10, v14, a9);
                  if ( v32
                    && (v34 = *(_QWORD *)(v32 + 8)) != 0
                    && *(_DWORD *)(v32 + 16) == 12
                    && (v37 = *(_QWORD *)(v32 + 40)) != 0
                    && *(_DWORD *)(v32 + 48) == 16
                    && *(_DWORD *)(v32 + 80) == v33 )
                  {
                    if ( (unsigned int)SymCryptChaCha20Poly1305Encrypt(
                                         (int)v35 + 60,
                                         *(_DWORD *)(v35 + 56),
                                         v34,
                                         12,
                                         *(_QWORD *)(v32 + 24),
                                         *(unsigned int *)(v32 + 32),
                                         v10,
                                         a7,
                                         v36,
                                         v37,
                                         16) )
                    {
                      v17 = -1073741174;
                      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                      {
                        WPP_SF_sDsd(
                          *((_QWORD *)WPP_GLOBAL_Control + 3),
                          v38,
                          v39,
                          (unsigned int)"Status",
                          138,
                          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                          173);
                      }
                    }
                    else
                    {
                      return 0;
                    }
                  }
                  else
                  {
                    v17 = -1073741811;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                    {
                      WPP_SF_sDsd(
                        *((_QWORD *)WPP_GLOBAL_Control + 3),
                        v33,
                        v34,
                        (unsigned int)"Status",
                        13,
                        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                        154);
                    }
                  }
                }
                return v17;
              default:
                v17 = -1073741637;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
                {
                  WPP_SF_sDsd(
                    *((_QWORD *)WPP_GLOBAL_Control + 3),
                    a10,
                    v14,
                    (unsigned int)"Status",
                    187,
                    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
                    254);
                }
                return v17;
            }
          }
        }
        else
        {
          v17 = -1073741811;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              a10,
              v14,
              (unsigned int)"Status",
              13,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
              66);
        }
      }
      else
      {
        v17 = -1073741811;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            a10,
            v14,
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
            58);
      }
    }
    else
    {
      v17 = -1073741811;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      {
        v40 = 38;
LABEL_60:
        WPP_SF_sDsd(
          v19[3],
          a2,
          v14,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\key.c",
          v40);
      }
    }
  }
  else
  {
    return (unsigned int)-1073741816;
  }
  return v17;
}

```

## disassembly

```asm
0x180014d10  push    rbx
0x180014d12  push    rbp
0x180014d13  push    rsi
0x180014d14  push    rdi
0x180014d15  push    r12
0x180014d17  push    r13
0x180014d19  push    r14
0x180014d1b  push    r15
0x180014d1d  sub     rsp, 2D8h
0x180014d24  mov     rax, cs:__security_cookie
0x180014d2b  xor     rax, rsp
0x180014d2e  mov     [rsp+318h+var_58], rax
0x180014d36  mov     rbp, [rsp+318h+arg_20]
0x180014d3e  mov     rdi, r9
0x180014d41  mov     r9, [rsp+318h+arg_40]
0x180014d49  mov     r15, rdx
0x180014d4c  mov     r14, [rsp+318h+arg_30]
0x180014d54  mov     r10, rcx
0x180014d57  mov     ebx, [rsp+318h+arg_38]
0x180014d5e  mov     r11d, r8d
0x180014d61  test    rcx, rcx
0x180014d64  jz      loc_180015173
0x180014d6a  cmp     dword ptr [rcx+4], 4D53534Bh
0x180014d71  jnz     loc_180015173
0x180014d77  mov     r8d, [rcx+0Ch]
0x180014d7b  lea     eax, [r8-4]
0x180014d7f  cmp     eax, 1
0x180014d82  ja      loc_180014E3E
0x180014d88  mov     edx, [rsp+318h+arg_48]
0x180014d8f  test    edx, 0FFFFFF98h
0x180014d95  jnz     loc_1800151F9
0x180014d9b  mov     rax, [rcx+20h]
0x180014d9f  mov     ecx, [rax+24h]
0x180014da2  not     ecx
0x180014da4  and     ecx, edx
0x180014da6  test    cl, 40h
0x180014da9  jnz     loc_1800151F9
0x180014daf  test    r9, r9
0x180014db2  jz      loc_1800153FD
0x180014db8  test    dl, 20h
0x180014dbb  jnz     loc_18001526C
0x180014dc1  mov     eax, [r10+8]
0x180014dc5  cmp     eax, 10007h
0x180014dca  jnz     loc_180014E81
0x180014dd0  mov     dword ptr [rsp+318h+var_2C8], edx; jumptable 0000000180014EA0 cases 65538-65542
0x180014dd4  mov     eax, edx
0x180014dd6  and     eax, 1
0x180014dd9  mov     r8, rbp
0x180014ddc  mov     dword ptr [rsp+318h+var_2D0], eax
0x180014de0  mov     rdx, rdi
0x180014de3  mov     [rsp+318h+var_2D8], r9
0x180014de8  mov     rcx, r10
0x180014deb  mov     r9d, [rsp+318h+arg_28]
0x180014df3  mov     dword ptr [rsp+318h+var_2E0], ebx
0x180014df7  mov     [rsp+318h+var_2E8], r14
0x180014dfc  mov     dword ptr [rsp+318h+var_2F0], r11d
0x180014e01  mov     [rsp+318h+var_2F8], r15
0x180014e06  call    MSBlockEncrypt
0x180014e0b  mov     r13d, eax
0x180014e0e  test    eax, eax
0x180014e10  js      loc_18001522B
0x180014e16  mov     eax, r13d
0x180014e19  mov     rcx, [rsp+318h+var_58]
0x180014e21  xor     rcx, rsp; StackCookie
0x180014e24  call    __security_check_cookie
0x180014e29  add     rsp, 2D8h
0x180014e30  pop     r15
0x180014e32  pop     r14
0x180014e34  pop     r13
0x180014e36  pop     r12
0x180014e38  pop     rdi
0x180014e39  pop     rsi
0x180014e3a  pop     rbp
0x180014e3b  pop     rbx
0x180014e3c  retn
0x180014e3e  cmp     dword ptr [rcx+8], 10009h
0x180014e45  jz      loc_180014D88
0x180014e4b  test    rdi, rdi
0x180014e4e  jz      loc_180014D88
0x180014e54  mov     r13d, 0C000000Dh
0x180014e5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e61  lea     rax, WPP_GLOBAL_Control
0x180014e68  cmp     rcx, rax
0x180014e6b  jz      short loc_180014E16
0x180014e6d  mov     eax, [rcx+2Ch]
0x180014e70  test    al, 1
0x180014e72  jz      short loc_180014E16
0x180014e74  mov     dword ptr [rsp+318h+var_2E8], 326h
0x180014e7c  jmp     loc_1800151D0
0x180014e81  add     eax, 0FFFEFFFFh; switch 9 cases
0x180014e86  cmp     eax, 8
0x180014e89  ja      def_180014EA0; jumptable 0000000180014EA0 default case, case 65543
0x180014e8f  lea     rcx, cs:180000000h
0x180014e96  mov     eax, ds:(jpt_180014EA0 - 180000000h)[rcx+rax*4]
0x180014e9d  add     rax, rcx
0x180014ea0  jmp     rax; switch jump
0x180014ea6  test    edx, 0FFFFFFBFh; jumptable 0000000180014EA0 case 65544
0x180014eac  jnz     loc_1800151A0
0x180014eb2  mov     ecx, [r10+14h]
0x180014eb6  test    ecx, ecx
0x180014eb8  jz      loc_1800151A0
0x180014ebe  xor     edx, edx; Val
0x180014ec0  mov     eax, r11d
0x180014ec3  div     ecx
0x180014ec5  test    edx, edx
0x180014ec7  jnz     loc_1800151A0
0x180014ecd  test    r15, r15
0x180014ed0  jz      loc_1800151A0
0x180014ed6  test    rbp, rbp
0x180014ed9  jz      loc_1800151A0
0x180014edf  cmp     [rsp+318h+arg_28], 8
0x180014ee7  jnz     loc_1800151A0
0x180014eed  lea     rax, [r11+r15]
0x180014ef1  mov     rsi, r11
0x180014ef4  cmp     rax, r15
0x180014ef7  jb      loc_1800151A0
0x180014efd  lea     rax, [r14+rbx]
0x180014f01  cmp     rax, r14
0x180014f04  jb      loc_1800151A0
0x180014f0a  mov     [r9], r11d
0x180014f0d  test    r14, r14
0x180014f10  jz      loc_18001516B
0x180014f16  cmp     r11d, ebx
0x180014f19  ja      loc_1800155C6
0x180014f1f  mov     edi, [r10+14h]
0x180014f23  xor     r13d, r13d
0x180014f26  cmp     rdi, 10h
0x180014f2a  jb      loc_180014E16
0x180014f30  mov     rbp, [rbp+0]
0x180014f34  lea     rbx, [r10+80h]
0x180014f3b  mov     r8d, 40h ; '@'; Size
0x180014f41  mov     [rsp+318h+var_2A8], rbx
0x180014f46  lea     rcx, [rsp+318h+XStateSave]; void *
0x180014f4e  mov     [rsp+318h+var_2B8], rbp
0x180014f53  mov     [rsp+318h+var_2B0], r13
0x180014f58  call    memset
0x180014f5d  mov     eax, cs:g_SymCryptCpuFeaturesNotPresent
0x180014f63  test    eax, 816h
0x180014f68  jnz     loc_180015083
0x180014f6e  test    al, 10h
0x180014f70  jnz     loc_1800155FA
0x180014f76  mov     rax, cr8
0x180014f7a  cmp     al, 2
0x180014f7c  ja      loc_180015083
0x180014f82  lea     rdx, [rsp+318h+XStateSave]; XStateSave
0x180014f8a  mov     ecx, 4; Mask
0x180014f8f  call    cs:__imp_KeSaveExtendedProcessorState
0x180014f96  nop     dword ptr [rax+rax+00h]
0x180014f9b  test    eax, eax
0x180014f9d  js      loc_180015083
0x180014fa3  cmp     rsi, rdi
0x180014fa6  jb      loc_180015058
0x180014fac  lea     rax, [rbx+1F0h]
0x180014fb3  mov     [rsp+318h+var_2B8], rax
0x180014fb8  mov     rbx, r13
0x180014fbb  nop     dword ptr [rax+rax+00h]
0x180014fc0  mov     [rsp+rbx+318h+var_258], rbp
0x180014fc8  sub     rsi, rdi
0x180014fcb  mov     [rsp+rbx+318h+var_250], r13
0x180014fd3  inc     rbp
0x180014fd6  add     rbx, 10h
0x180014fda  cmp     rbx, 100h
0x180014fe1  jnb     short loc_180014FE8
0x180014fe3  cmp     rsi, rdi
0x180014fe6  jnb     short loc_180014FC0
0x180014fe8  mov     r9, rbx
0x180014feb  lea     r8, [rsp+318h+var_258]
0x180014ff3  lea     rdx, [rsp+318h+var_258]
0x180014ffb  mov     rcx, rax
0x180014ffe  call    SymCryptAesEcbEncryptXmm
0x180015003  mov     r12, r13
0x180015006  test    rbx, rbx
0x180015009  jz      short loc_18001504A
0x18001500b  mov     r13, [rsp+318h+var_2A8]
0x180015010  lea     rdx, [rsp+318h+var_258]
0x180015018  mov     [rsp+318h+var_2F0], rdi
0x18001501d  add     rdx, r12
0x180015020  mov     [rsp+318h+var_2F8], r14
0x180015025  mov     r9, r15
0x180015028  lea     r8, [rsp+318h+var_158]
0x180015030  mov     rcx, r13
0x180015033  call    SymCryptXtsAesEncryptDataUnitYmm_2048
0x180015038  add     r15, rdi
0x18001503b  add     r14, rdi
0x18001503e  add     r12, 10h
0x180015042  cmp     r12, rbx
0x180015045  jb      short loc_180015010
0x180015047  xor     r13d, r13d
0x18001504a  mov     rax, [rsp+318h+var_2B8]
0x18001504f  cmp     rsi, rdi
0x180015052  jnb     loc_180014FB8
0x180015058  mov     edx, 200h
0x18001505d  lea     rcx, [rsp+318h+var_258]
0x180015065  call    SymCryptWipeAsm
0x18001506a  lea     rcx, [rsp+318h+XStateSave]; XStateSave
0x180015072  call    cs:__imp_KeRestoreExtendedProcessorState
0x180015079  nop     dword ptr [rax+rax+00h]
0x18001507e  jmp     loc_180014E16
0x180015083  mov     eax, cs:g_SymCryptCpuFeaturesNotPresent
0x180015089  test    al, 6
0x18001508b  jnz     loc_18001517E
0x180015091  cmp     rsi, rdi
0x180015094  jb      loc_180015148
0x18001509a  lea     rax, [rbx+1F0h]
0x1800150a1  mov     [rsp+318h+var_2B8], rax
0x1800150a6  mov     r12, r13
0x1800150a9  nop     dword ptr [rax+00000000h]
0x1800150b0  mov     [rsp+r12+318h+var_258], rbp
0x1800150b8  sub     rsi, rdi
0x1800150bb  mov     [rsp+r12+318h+var_250], r13
0x1800150c3  inc     rbp
0x1800150c6  add     r12, 10h
0x1800150ca  cmp     r12, 100h
0x1800150d1  jnb     short loc_1800150D8
0x1800150d3  cmp     rsi, rdi
0x1800150d6  jnb     short loc_1800150B0
0x1800150d8  mov     r9, r12
0x1800150db  lea     r8, [rsp+318h+var_258]
0x1800150e3  lea     rdx, [rsp+318h+var_258]
0x1800150eb  mov     rcx, rax
0x1800150ee  call    SymCryptAesEcbEncryptXmm
0x1800150f3  mov     rbx, r13
0x1800150f6  test    r12, r12
0x1800150f9  jz      short loc_18001513A
0x1800150fb  mov     r13, [rsp+318h+var_2A8]
0x180015100  lea     rdx, [rsp+318h+var_258]
0x180015108  mov     [rsp+318h+var_2F0], rdi
0x18001510d  add     rdx, rbx
0x180015110  mov     [rsp+318h+var_2F8], r14
0x180015115  mov     r9, r15
0x180015118  lea     r8, [rsp+318h+var_158]
0x180015120  mov     rcx, r13
0x180015123  call    SymCryptXtsAesEncryptDataUnitXmm
0x180015128  add     r15, rdi
0x18001512b  add     r14, rdi
0x18001512e  add     rbx, 10h
0x180015132  cmp     rbx, r12
0x180015135  jb      short loc_180015100
0x180015137  xor     r13d, r13d
0x18001513a  mov     rax, [rsp+318h+var_2B8]
0x18001513f  cmp     rsi, rdi
0x180015142  jnb     loc_1800150A6
0x180015148  mov     edx, 200h
0x18001514d  lea     rcx, [rsp+318h+var_258]
0x180015155  call    SymCryptWipeAsm
0x18001515a  jmp     loc_180014E16
0x18001515f  mov     [r9], r11d; jumptable 0000000180014EA0 case 65537
0x180015162  test    r14, r14
0x180015165  jnz     loc_180015465
0x18001516b  xor     r13d, r13d
0x18001516e  jmp     loc_180014E16
0x180015173  mov     r13d, 0C0000008h
0x180015179  jmp     loc_180014E16
0x18001517e  mov     [rsp+318h+var_2F0], rsi
0x180015183  lea     r8, [rsp+318h+var_2B8]
0x180015188  mov     r9, r15
0x18001518b  mov     [rsp+318h+var_2F8], r14
0x180015190  mov     rdx, rdi
0x180015193  mov     rcx, rbx
0x180015196  call    SymCryptXtsAesEncryptInternalAsm
0x18001519b  jmp     loc_180014E16
0x1800151a0  mov     r13d, 0C000000Dh
0x1800151a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800151ad  lea     rax, WPP_GLOBAL_Control
0x1800151b4  cmp     rcx, rax
0x1800151b7  jz      loc_180014E16
0x1800151bd  mov     eax, [rcx+2Ch]
0x1800151c0  test    al, 1
0x1800151c2  jz      loc_180014E16
0x1800151c8  mov     dword ptr [rsp+318h+var_2E8], 3DFh
0x1800151d0  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800151d7  mov     [rsp+318h+var_2F0], rax
0x1800151dc  mov     dword ptr [rsp+318h+var_2F8], 0C000000Dh
0x1800151e4  mov     rcx, [rcx+18h]
0x1800151e8  lea     r9, aStatus; "Status"
0x1800151ef  call    WPP_SF_sDsd
0x1800151f4  jmp     loc_180014E16
0x1800151f9  mov     r13d, 0C000000Dh
0x1800151ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180015206  lea     rax, WPP_GLOBAL_Control
0x18001520d  cmp     rcx, rax
0x180015210  jz      loc_180014E16
0x180015216  mov     eax, [rcx+2Ch]
0x180015219  test    al, 1
0x18001521b  jz      loc_180014E16
0x180015221  mov     dword ptr [rsp+318h+var_2E8], 331h
0x180015229  jmp     short loc_1800151D0
0x18001522b  mov     rcx, cs:WPP_GLOBAL_Control
0x180015232  lea     rax, WPP_GLOBAL_Control
0x180015239  cmp     rcx, rax
0x18001523c  jz      loc_180014E16
0x180015242  mov     edx, [rcx+2Ch]
0x180015245  test    dl, 1
0x180015248  jz      loc_180014E16
0x18001524e  mov     dword ptr [rsp+318h+var_2E8], 3C9h
0x180015256  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001525d  mov     [rsp+318h+var_2F0], rax
0x180015262  mov     dword ptr [rsp+318h+var_2F8], r13d
0x180015267  jmp     loc_1800151E4
0x18001526c  cmp     dword ptr [r10+8], 10002h
  ... truncated ...
```
