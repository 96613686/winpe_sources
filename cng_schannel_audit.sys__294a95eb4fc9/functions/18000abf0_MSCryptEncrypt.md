# MSCryptEncrypt

- ea: `0x18000abf0`
- end: `0x18000b4e5`
- name: `MSCryptEncrypt`
- size: `2293`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800173a0`

## callees

- `0x18000743c`
- `0x1800082b0`
- `0x18000a560`
- `0x18000abf0`
- `0x18000b4f0`
- `0x18000ba00`
- `0x18000bfe8`
- `0x18000c7a0`
- `0x18000ca20`
- `0x18000ca60`
- `0x18000cae4`
- `0x180048d7c`
- `0x18004c3d0`
- `0x18009d820`
- `0x18009dd40`

## import_xrefs

- `ntoskrnl!KeRestoreExtendedProcessorState` at `0x18000af52`
- `ntoskrnl!KeRestoreExtendedProcessorState` at `0x18000af52`
- `ntoskrnl!KeSaveExtendedProcessorState` at `0x18000ae6f`
- `ntoskrnl!KeSaveExtendedProcessorState` at `0x18000ae6f`

## string_xrefs

- `0x18000b0b0`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000b136`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000b186`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000b2c4`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000b309`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000b3d7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000b430`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000b48d`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`
- `0x18000b4b7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\key.c`

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
          v40 = 48;
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
                  200);
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
                  871);
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
                    v40 = -34;
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
                      139);
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
                          172);
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
                        153);
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
                    253);
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
              65);
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
            57);
      }
    }
    else
    {
      v17 = -1073741811;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      {
        v40 = 37;
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
0x18000abf0  push    rbx
0x18000abf2  push    rbp
0x18000abf3  push    rsi
0x18000abf4  push    rdi
0x18000abf5  push    r12
0x18000abf7  push    r13
0x18000abf9  push    r14
0x18000abfb  push    r15
0x18000abfd  sub     rsp, 2D8h
0x18000ac04  mov     rax, cs:__security_cookie
0x18000ac0b  xor     rax, rsp
0x18000ac0e  mov     [rsp+318h+var_58], rax
0x18000ac16  mov     rbp, [rsp+318h+arg_20]
0x18000ac1e  mov     rdi, r9
0x18000ac21  mov     r9, [rsp+318h+arg_40]
0x18000ac29  mov     r15, rdx
0x18000ac2c  mov     r14, [rsp+318h+arg_30]
0x18000ac34  mov     r10, rcx
0x18000ac37  mov     ebx, [rsp+318h+arg_38]
0x18000ac3e  mov     r11d, r8d
0x18000ac41  test    rcx, rcx
0x18000ac44  jz      loc_18000B053
0x18000ac4a  cmp     dword ptr [rcx+4], 4D53534Bh
0x18000ac51  jnz     loc_18000B053
0x18000ac57  mov     r8d, [rcx+0Ch]
0x18000ac5b  lea     eax, [r8-4]
0x18000ac5f  cmp     eax, 1
0x18000ac62  ja      loc_18000AD1E
0x18000ac68  mov     edx, [rsp+318h+arg_48]
0x18000ac6f  test    edx, 0FFFFFF98h
0x18000ac75  jnz     loc_18000B0D9
0x18000ac7b  mov     rax, [rcx+20h]
0x18000ac7f  mov     ecx, [rax+24h]
0x18000ac82  not     ecx
0x18000ac84  and     ecx, edx
0x18000ac86  test    cl, 40h
0x18000ac89  jnz     loc_18000B0D9
0x18000ac8f  test    r9, r9
0x18000ac92  jz      loc_18000B2DD
0x18000ac98  test    dl, 20h
0x18000ac9b  jnz     loc_18000B14C
0x18000aca1  mov     eax, [r10+8]
0x18000aca5  cmp     eax, 10007h
0x18000acaa  jnz     loc_18000AD61
0x18000acb0  mov     dword ptr [rsp+318h+var_2C8], edx; jumptable 000000018000AD80 cases 65538-65542
0x18000acb4  mov     eax, edx
0x18000acb6  and     eax, 1
0x18000acb9  mov     r8, rbp
0x18000acbc  mov     dword ptr [rsp+318h+var_2D0], eax
0x18000acc0  mov     rdx, rdi
0x18000acc3  mov     [rsp+318h+var_2D8], r9
0x18000acc8  mov     rcx, r10
0x18000accb  mov     r9d, [rsp+318h+arg_28]
0x18000acd3  mov     dword ptr [rsp+318h+var_2E0], ebx
0x18000acd7  mov     [rsp+318h+var_2E8], r14
0x18000acdc  mov     dword ptr [rsp+318h+var_2F0], r11d
0x18000ace1  mov     [rsp+318h+var_2F8], r15
0x18000ace6  call    MSBlockEncrypt
0x18000aceb  mov     r13d, eax
0x18000acee  test    eax, eax
0x18000acf0  js      loc_18000B10B
0x18000acf6  mov     eax, r13d
0x18000acf9  mov     rcx, [rsp+318h+var_58]
0x18000ad01  xor     rcx, rsp; StackCookie
0x18000ad04  call    __security_check_cookie
0x18000ad09  add     rsp, 2D8h
0x18000ad10  pop     r15
0x18000ad12  pop     r14
0x18000ad14  pop     r13
0x18000ad16  pop     r12
0x18000ad18  pop     rdi
0x18000ad19  pop     rsi
0x18000ad1a  pop     rbp
0x18000ad1b  pop     rbx
0x18000ad1c  retn
0x18000ad1e  cmp     dword ptr [rcx+8], 10009h
0x18000ad25  jz      loc_18000AC68
0x18000ad2b  test    rdi, rdi
0x18000ad2e  jz      loc_18000AC68
0x18000ad34  mov     r13d, 0C000000Dh
0x18000ad3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad41  lea     rax, WPP_GLOBAL_Control
0x18000ad48  cmp     rcx, rax
0x18000ad4b  jz      short loc_18000ACF6
0x18000ad4d  mov     eax, [rcx+2Ch]
0x18000ad50  test    al, 1
0x18000ad52  jz      short loc_18000ACF6
0x18000ad54  mov     dword ptr [rsp+318h+var_2E8], 325h
0x18000ad5c  jmp     loc_18000B0B0
0x18000ad61  add     eax, 0FFFEFFFFh; switch 9 cases
0x18000ad66  cmp     eax, 8
0x18000ad69  ja      def_18000AD80; jumptable 000000018000AD80 default case, case 65543
0x18000ad6f  lea     rcx, cs:180000000h
0x18000ad76  mov     eax, ds:(jpt_18000AD80 - 180000000h)[rcx+rax*4]
0x18000ad7d  add     rax, rcx
0x18000ad80  jmp     rax; switch jump
0x18000ad86  test    edx, 0FFFFFFBFh; jumptable 000000018000AD80 case 65544
0x18000ad8c  jnz     loc_18000B080
0x18000ad92  mov     ecx, [r10+14h]
0x18000ad96  test    ecx, ecx
0x18000ad98  jz      loc_18000B080
0x18000ad9e  xor     edx, edx; Val
0x18000ada0  mov     eax, r11d
0x18000ada3  div     ecx
0x18000ada5  test    edx, edx
0x18000ada7  jnz     loc_18000B080
0x18000adad  test    r15, r15
0x18000adb0  jz      loc_18000B080
0x18000adb6  test    rbp, rbp
0x18000adb9  jz      loc_18000B080
0x18000adbf  cmp     [rsp+318h+arg_28], 8
0x18000adc7  jnz     loc_18000B080
0x18000adcd  lea     rax, [r11+r15]
0x18000add1  mov     rsi, r11
0x18000add4  cmp     rax, r15
0x18000add7  jb      loc_18000B080
0x18000addd  lea     rax, [r14+rbx]
0x18000ade1  cmp     rax, r14
0x18000ade4  jb      loc_18000B080
0x18000adea  mov     [r9], r11d
0x18000aded  test    r14, r14
0x18000adf0  jz      loc_18000B04B
0x18000adf6  cmp     r11d, ebx
0x18000adf9  ja      loc_18000B4A6
0x18000adff  mov     edi, [r10+14h]
0x18000ae03  xor     r13d, r13d
0x18000ae06  cmp     rdi, 10h
0x18000ae0a  jb      loc_18000ACF6
0x18000ae10  mov     rbp, [rbp+0]
0x18000ae14  lea     rbx, [r10+80h]
0x18000ae1b  mov     r8d, 40h ; '@'; Size
0x18000ae21  mov     [rsp+318h+var_2A8], rbx
0x18000ae26  lea     rcx, [rsp+318h+XStateSave]; void *
0x18000ae2e  mov     [rsp+318h+var_2B8], rbp
0x18000ae33  mov     [rsp+318h+var_2B0], r13
0x18000ae38  call    memset
0x18000ae3d  mov     eax, cs:g_SymCryptCpuFeaturesNotPresent
0x18000ae43  test    eax, 816h
0x18000ae48  jnz     loc_18000AF63
0x18000ae4e  test    al, 10h
0x18000ae50  jnz     loc_18000B4DA
0x18000ae56  mov     rax, cr8
0x18000ae5a  cmp     al, 2
0x18000ae5c  ja      loc_18000AF63
0x18000ae62  lea     rdx, [rsp+318h+XStateSave]; XStateSave
0x18000ae6a  mov     ecx, 4; Mask
0x18000ae6f  call    cs:__imp_KeSaveExtendedProcessorState
0x18000ae76  nop     dword ptr [rax+rax+00h]
0x18000ae7b  test    eax, eax
0x18000ae7d  js      loc_18000AF63
0x18000ae83  cmp     rsi, rdi
0x18000ae86  jb      loc_18000AF38
0x18000ae8c  lea     rax, [rbx+1F0h]
0x18000ae93  mov     [rsp+318h+var_2B8], rax
0x18000ae98  mov     rbx, r13
0x18000ae9b  nop     dword ptr [rax+rax+00h]
0x18000aea0  mov     [rsp+rbx+318h+var_258], rbp
0x18000aea8  sub     rsi, rdi
0x18000aeab  mov     [rsp+rbx+318h+var_250], r13
0x18000aeb3  inc     rbp
0x18000aeb6  add     rbx, 10h
0x18000aeba  cmp     rbx, 100h
0x18000aec1  jnb     short loc_18000AEC8
0x18000aec3  cmp     rsi, rdi
0x18000aec6  jnb     short loc_18000AEA0
0x18000aec8  mov     r9, rbx
0x18000aecb  lea     r8, [rsp+318h+var_258]
0x18000aed3  lea     rdx, [rsp+318h+var_258]
0x18000aedb  mov     rcx, rax
0x18000aede  call    SymCryptAesEcbEncryptXmm
0x18000aee3  mov     r12, r13
0x18000aee6  test    rbx, rbx
0x18000aee9  jz      short loc_18000AF2A
0x18000aeeb  mov     r13, [rsp+318h+var_2A8]
0x18000aef0  lea     rdx, [rsp+318h+var_258]
0x18000aef8  mov     [rsp+318h+var_2F0], rdi
0x18000aefd  add     rdx, r12
0x18000af00  mov     [rsp+318h+var_2F8], r14
0x18000af05  mov     r9, r15
0x18000af08  lea     r8, [rsp+318h+var_158]
0x18000af10  mov     rcx, r13
0x18000af13  call    SymCryptXtsAesEncryptDataUnitYmm_2048
0x18000af18  add     r15, rdi
0x18000af1b  add     r14, rdi
0x18000af1e  add     r12, 10h
0x18000af22  cmp     r12, rbx
0x18000af25  jb      short loc_18000AEF0
0x18000af27  xor     r13d, r13d
0x18000af2a  mov     rax, [rsp+318h+var_2B8]
0x18000af2f  cmp     rsi, rdi
0x18000af32  jnb     loc_18000AE98
0x18000af38  mov     edx, 200h
0x18000af3d  lea     rcx, [rsp+318h+var_258]
0x18000af45  call    SymCryptWipeAsm
0x18000af4a  lea     rcx, [rsp+318h+XStateSave]; XStateSave
0x18000af52  call    cs:__imp_KeRestoreExtendedProcessorState
0x18000af59  nop     dword ptr [rax+rax+00h]
0x18000af5e  jmp     loc_18000ACF6
0x18000af63  mov     eax, cs:g_SymCryptCpuFeaturesNotPresent
0x18000af69  test    al, 6
0x18000af6b  jnz     loc_18000B05E
0x18000af71  cmp     rsi, rdi
0x18000af74  jb      loc_18000B028
0x18000af7a  lea     rax, [rbx+1F0h]
0x18000af81  mov     [rsp+318h+var_2B8], rax
0x18000af86  mov     r12, r13
0x18000af89  nop     dword ptr [rax+00000000h]
0x18000af90  mov     [rsp+r12+318h+var_258], rbp
0x18000af98  sub     rsi, rdi
0x18000af9b  mov     [rsp+r12+318h+var_250], r13
0x18000afa3  inc     rbp
0x18000afa6  add     r12, 10h
0x18000afaa  cmp     r12, 100h
0x18000afb1  jnb     short loc_18000AFB8
0x18000afb3  cmp     rsi, rdi
0x18000afb6  jnb     short loc_18000AF90
0x18000afb8  mov     r9, r12
0x18000afbb  lea     r8, [rsp+318h+var_258]
0x18000afc3  lea     rdx, [rsp+318h+var_258]
0x18000afcb  mov     rcx, rax
0x18000afce  call    SymCryptAesEcbEncryptXmm
0x18000afd3  mov     rbx, r13
0x18000afd6  test    r12, r12
0x18000afd9  jz      short loc_18000B01A
0x18000afdb  mov     r13, [rsp+318h+var_2A8]
0x18000afe0  lea     rdx, [rsp+318h+var_258]
0x18000afe8  mov     [rsp+318h+var_2F0], rdi
0x18000afed  add     rdx, rbx
0x18000aff0  mov     [rsp+318h+var_2F8], r14
0x18000aff5  mov     r9, r15
0x18000aff8  lea     r8, [rsp+318h+var_158]
0x18000b000  mov     rcx, r13
0x18000b003  call    SymCryptXtsAesEncryptDataUnitXmm
0x18000b008  add     r15, rdi
0x18000b00b  add     r14, rdi
0x18000b00e  add     rbx, 10h
0x18000b012  cmp     rbx, r12
0x18000b015  jb      short loc_18000AFE0
0x18000b017  xor     r13d, r13d
0x18000b01a  mov     rax, [rsp+318h+var_2B8]
0x18000b01f  cmp     rsi, rdi
0x18000b022  jnb     loc_18000AF86
0x18000b028  mov     edx, 200h
0x18000b02d  lea     rcx, [rsp+318h+var_258]
0x18000b035  call    SymCryptWipeAsm
0x18000b03a  jmp     loc_18000ACF6
0x18000b03f  mov     [r9], r11d; jumptable 000000018000AD80 case 65537
0x18000b042  test    r14, r14
0x18000b045  jnz     loc_18000B345
0x18000b04b  xor     r13d, r13d
0x18000b04e  jmp     loc_18000ACF6
0x18000b053  mov     r13d, 0C0000008h
0x18000b059  jmp     loc_18000ACF6
0x18000b05e  mov     [rsp+318h+var_2F0], rsi
0x18000b063  lea     r8, [rsp+318h+var_2B8]
0x18000b068  mov     r9, r15
0x18000b06b  mov     [rsp+318h+var_2F8], r14
0x18000b070  mov     rdx, rdi
0x18000b073  mov     rcx, rbx
0x18000b076  call    SymCryptXtsAesEncryptInternalAsm
0x18000b07b  jmp     loc_18000ACF6
0x18000b080  mov     r13d, 0C000000Dh
0x18000b086  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b08d  lea     rax, WPP_GLOBAL_Control
0x18000b094  cmp     rcx, rax
0x18000b097  jz      loc_18000ACF6
0x18000b09d  mov     eax, [rcx+2Ch]
0x18000b0a0  test    al, 1
0x18000b0a2  jz      loc_18000ACF6
0x18000b0a8  mov     dword ptr [rsp+318h+var_2E8], 3DEh
0x18000b0b0  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b0b7  mov     [rsp+318h+var_2F0], rax
0x18000b0bc  mov     dword ptr [rsp+318h+var_2F8], 0C000000Dh
0x18000b0c4  mov     rcx, [rcx+18h]
0x18000b0c8  lea     r9, aStatus; "Status"
0x18000b0cf  call    WPP_SF_sDsd
0x18000b0d4  jmp     loc_18000ACF6
0x18000b0d9  mov     r13d, 0C000000Dh
0x18000b0df  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0e6  lea     rax, WPP_GLOBAL_Control
0x18000b0ed  cmp     rcx, rax
0x18000b0f0  jz      loc_18000ACF6
0x18000b0f6  mov     eax, [rcx+2Ch]
0x18000b0f9  test    al, 1
0x18000b0fb  jz      loc_18000ACF6
0x18000b101  mov     dword ptr [rsp+318h+var_2E8], 330h
0x18000b109  jmp     short loc_18000B0B0
0x18000b10b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b112  lea     rax, WPP_GLOBAL_Control
0x18000b119  cmp     rcx, rax
0x18000b11c  jz      loc_18000ACF6
0x18000b122  mov     edx, [rcx+2Ch]
0x18000b125  test    dl, 1
0x18000b128  jz      loc_18000ACF6
0x18000b12e  mov     dword ptr [rsp+318h+var_2E8], 3C8h
0x18000b136  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b13d  mov     [rsp+318h+var_2F0], rax
0x18000b142  mov     dword ptr [rsp+318h+var_2F8], r13d
0x18000b147  jmp     loc_18000B0C4
0x18000b14c  cmp     dword ptr [r10+8], 10002h
  ... truncated ...
```
