# Tls13EncryptPacket

- ea: `0x18000be50`
- end: `0x18000c1b4`
- name: `Tls13EncryptPacket`
- size: `868`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000bb90`

## callees

- `0x18000b594`
- `0x18000b654`
- `0x18000be50`

## import_xrefs

- `bcrypt!BCryptEncrypt` at `0x18000bfd6`
- `bcrypt!BCryptEncrypt` at `0x18000bfd6`

## string_xrefs

- `0x18000c02b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000c077`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000c0bf`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000c10e`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000c16a`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000c192`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
NTSTATUS __fastcall Tls13EncryptPacket(
        __int64 a1,
        __int64 a2,
        UCHAR *a3,
        unsigned int a4,
        UCHAR *a5,
        unsigned int a6,
        _DWORD *a7,
        unsigned __int64 a8,
        UCHAR a9)
{
  __int64 cbOutput; // rbx
  UCHAR *v10; // r10
  _DWORD *v11; // rsi
  int v12; // r9d
  int v13; // ebp
  void *v14; // rcx
  NTSTATUS result; // eax
  int v16; // r8d
  NTSTATUS v17; // edi
  __int128 v18; // [rsp+50h] [rbp-78h] BYREF
  _DWORD pPaddingInfo[2]; // [rsp+60h] [rbp-68h] BYREF
  char *v20; // [rsp+68h] [rbp-60h]
  __int64 v21; // [rsp+70h] [rbp-58h]
  UCHAR *v22; // [rsp+78h] [rbp-50h]
  int v23; // [rsp+80h] [rbp-48h]
  int v24; // [rsp+84h] [rbp-44h]
  __int128 v25; // [rsp+88h] [rbp-40h]
  __int128 v26; // [rsp+98h] [rbp-30h]
  __int128 v27; // [rsp+A8h] [rbp-20h]
  ULONG pcbResult; // [rsp+E8h] [rbp+20h] BYREF

  pPaddingInfo[0] = 88;
  pPaddingInfo[1] = 1;
  cbOutput = a4;
  v20 = (char *)&v18 + 4;
  pcbResult = 0;
  v21 = 12;
  v10 = a3;
  v24 = 0;
  v18 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  if ( a1 && a2 && a3 && a4 - 1 <= 0x4000 && (a3 = a5) != 0 && (v11 = a7) != 0 )
  {
    if ( *(_DWORD *)(a2 + 8) == 772 && *(_DWORD *)(a2 + 108) == 5 )
    {
      v12 = (unsigned __int16)(a4 + 16);
      v13 = v12 + 5;
      if ( a6 >= v12 + 5 )
      {
        if ( a5 + 5 == v10 )
          goto LABEL_11;
        if ( v10 > a5 )
          goto LABEL_34;
        if ( a5 < &v10[cbOutput] )
        {
LABEL_35:
          DebugTraceError(
            2148073515LL,
            "NTE_BUFFERS_OVERLAP",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            4813);
          return -2146893781;
        }
        if ( v10 >= a5 )
        {
LABEL_34:
          if ( v10 < &a5[a6] )
            goto LABEL_35;
        }
LABEL_11:
        *a5 = a9;
        a3[4] = cbOutput + 16;
        a3[3] = BYTE1(v12);
        *(_WORD *)(a3 + 1) = 771;
        DWORD1(v18) = *(_DWORD *)(a2 + 56);
        *((_QWORD *)&v18 + 1) = *(_QWORD *)(a2 + 60) ^ _byteswap_uint64(a8);
        v14 = *(void **)(a2 + 32);
        v22 = a3;
        *(_QWORD *)&v25 = &a3[cbOutput + 5];
        v23 = 5;
        DWORD2(v25) = 16;
        result = BCryptEncrypt(v14, v10, cbOutput, pPaddingInfo, 0, 0, a3 + 5, cbOutput, &pcbResult, 0);
        v17 = result;
        if ( result < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              v16,
              (unsigned int)"Status",
              result,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              0);
          return v17;
        }
        else if ( pcbResult == (_DWORD)cbOutput )
        {
          *v11 = v13;
        }
        else
        {
          DebugTraceError(
            2148073504LL,
            "NTE_FAIL",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            4869);
          return -2146893792;
        }
        return result;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          (_DWORD)a5,
          (unsigned int)"NTE_BUFFER_TOO_SMALL",
          40,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          196);
      return -2146893784;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          (_DWORD)a5,
          (unsigned int)"NTE_NOT_SUPPORTED",
          41,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          188);
      return -2146893783;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        (_DWORD)a3,
        (unsigned int)"NTE_INVALID_PARAMETER",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        181);
    return -2146893785;
  }
}

```

## disassembly

```asm
0x18000be50  mov     r11, rsp
0x18000be53  mov     [r11+10h], rbx
0x18000be57  mov     [r11+18h], rsi
0x18000be5b  push    rdi
0x18000be5c  sub     rsp, 0C0h
0x18000be63  mov     [rsp+0C8h+pPaddingInfo], 58h ; 'X'
0x18000be6b  xorps   xmm0, xmm0
0x18000be6e  mov     [rsp+0C8h+var_64], 1
0x18000be76  mov     rax, rdx
0x18000be79  lea     rdx, [r11-74h]
0x18000be7d  mov     ebx, r9d
0x18000be80  xor     edi, edi
0x18000be82  mov     [r11-60h], rdx
0x18000be86  xor     edx, edx
0x18000be88  mov     [r11+20h], edi
0x18000be8c  mov     qword ptr [r11-58h], 0Ch
0x18000be94  mov     r10, r8
0x18000be97  mov     [r11-44h], edx
0x18000be9b  movups  [rsp+0C8h+var_78], xmm0
0x18000bea0  movups  xmmword ptr [r11-40h], xmm0
0x18000bea5  movups  xmmword ptr [r11-30h], xmm0
0x18000beaa  movups  xmmword ptr [r11-20h], xmm0
0x18000beaf  test    rcx, rcx
0x18000beb2  jz      loc_18000C00E
0x18000beb8  test    rax, rax
0x18000bebb  jz      loc_18000C00E
0x18000bec1  test    r8, r8
0x18000bec4  jz      loc_18000C00E
0x18000beca  lea     ecx, [rbx-1]
0x18000becd  cmp     ecx, 4000h
0x18000bed3  ja      loc_18000C00E
0x18000bed9  mov     r8, [rsp+0C8h+arg_20]
0x18000bee1  test    r8, r8
0x18000bee4  jz      loc_18000C00E
0x18000beea  mov     rsi, [rsp+0C8h+arg_30]
0x18000bef2  test    rsi, rsi
0x18000bef5  jz      loc_18000C00E
0x18000befb  cmp     dword ptr [rax+8], 304h
0x18000bf02  jnz     loc_18000C0A2
0x18000bf08  cmp     dword ptr [rax+6Ch], 5
0x18000bf0c  jnz     loc_18000C0A2
0x18000bf12  mov     edx, [rsp+0C8h+arg_28]
0x18000bf19  lea     ecx, [rbx+10h]
0x18000bf1c  movzx   r9d, cx
0x18000bf20  mov     [r11+8], rbp
0x18000bf24  lea     ebp, [r9+5]
0x18000bf28  cmp     edx, ebp
0x18000bf2a  jb      loc_18000C0F1
0x18000bf30  lea     r11, [r8+5]
0x18000bf34  cmp     r11, r10
0x18000bf37  jnz     loc_18000C140
0x18000bf3d  movzx   ecx, [rsp+0C8h+arg_40]
0x18000bf45  lea     rdx, [r8+5]
0x18000bf49  mov     [r8], cl
0x18000bf4c  add     rdx, rbx
0x18000bf4f  mov     [r8+4], r9b
0x18000bf53  movzx   ecx, r9w
0x18000bf57  shr     cx, 8
0x18000bf5b  lea     r9, [rsp+0C8h+pPaddingInfo]; pPaddingInfo
0x18000bf60  mov     [r8+3], cl
0x18000bf64  mov     word ptr [r8+1], 303h
0x18000bf6b  mov     ecx, [rax+38h]
0x18000bf6e  mov     dword ptr [rsp+0C8h+var_78+4], ecx
0x18000bf72  mov     rcx, [rsp+0C8h+arg_38]
0x18000bf7a  mov     [rsp+0C8h+dwFlags], edi; dwFlags
0x18000bf7e  bswap   rcx
0x18000bf81  xor     rcx, [rax+3Ch]
0x18000bf85  mov     qword ptr [rsp+0C8h+var_78+8], rcx
0x18000bf8a  lea     rcx, [rsp+0C8h+arg_18]
0x18000bf92  mov     [rsp+0C8h+pcbResult], rcx; pcbResult
0x18000bf97  mov     rcx, [rax+20h]; hKey
0x18000bf9b  mov     [rsp+0C8h+cbOutput], ebx; cbOutput
0x18000bf9f  mov     [rsp+0C8h+pbOutput], r11; pbOutput
0x18000bfa4  mov     [rsp+0C8h+var_50], r8
0x18000bfa9  mov     r8d, ebx; cbInput
0x18000bfac  mov     [rsp+0C8h+var_40], rdx
0x18000bfb4  mov     rdx, r10; pbInput
0x18000bfb7  mov     [rsp+0C8h+cbIV], edi; cbIV
0x18000bfbb  mov     [rsp+0C8h+pbIV], rdi; pbIV
0x18000bfc0  mov     [rsp+0C8h+var_48], 5
0x18000bfcb  mov     [rsp+0C8h+var_38], 10h
0x18000bfd6  call    cs:__imp_BCryptEncrypt
0x18000bfdc  mov     edi, eax
0x18000bfde  test    eax, eax
0x18000bfe0  js      short loc_18000C05A
0x18000bfe2  cmp     [rsp+0C8h+arg_18], ebx
0x18000bfe9  jnz     loc_18000C18C
0x18000bfef  mov     [rsi], ebp
0x18000bff1  mov     rbp, [rsp+0C8h+arg_0]
0x18000bff9  lea     r11, [rsp+0C8h+var_8]
0x18000c001  mov     rbx, [r11+18h]
0x18000c005  mov     rsi, [r11+20h]
0x18000c009  mov     rsp, r11
0x18000c00c  pop     rdi
0x18000c00d  retn
0x18000c00e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c015  lea     rax, WPP_GLOBAL_Control
0x18000c01c  cmp     rcx, rax
0x18000c01f  jz      short loc_18000C053
0x18000c021  test    byte ptr [rcx+1Ch], 1
0x18000c025  jz      short loc_18000C053
0x18000c027  mov     rcx, [rcx+10h]
0x18000c02b  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c032  mov     dword ptr [rsp+0C8h+pbOutput], 12B5h
0x18000c03a  lea     r9, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x18000c041  mov     qword ptr [rsp+0C8h+cbIV], rdx
0x18000c046  mov     dword ptr [rsp+0C8h+pbIV], 80090027h
0x18000c04e  call    WPP_SF_sDsd
0x18000c053  mov     eax, 80090027h
0x18000c058  jmp     short loc_18000BFF9
0x18000c05a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c061  lea     rax, WPP_GLOBAL_Control
0x18000c068  cmp     rcx, rax
0x18000c06b  jz      short loc_18000C09B
0x18000c06d  test    byte ptr [rcx+1Ch], 1
0x18000c071  jz      short loc_18000C09B
0x18000c073  mov     rcx, [rcx+10h]
0x18000c077  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c07e  mov     dword ptr [rsp+0C8h+pbOutput], 1300h
0x18000c086  lea     r9, aStatus; "Status"
0x18000c08d  mov     qword ptr [rsp+0C8h+cbIV], rdx
0x18000c092  mov     dword ptr [rsp+0C8h+pbIV], edi
0x18000c096  call    WPP_SF_sDsd
0x18000c09b  mov     eax, edi
0x18000c09d  jmp     loc_18000BFF1
0x18000c0a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0a9  lea     rax, WPP_GLOBAL_Control
0x18000c0b0  cmp     rcx, rax
0x18000c0b3  jz      short loc_18000C0E7
0x18000c0b5  test    byte ptr [rcx+1Ch], 1
0x18000c0b9  jz      short loc_18000C0E7
0x18000c0bb  mov     rcx, [rcx+10h]
0x18000c0bf  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c0c6  mov     dword ptr [rsp+0C8h+pbOutput], 12BCh
0x18000c0ce  lea     r9, aNteNotSupporte; "NTE_NOT_SUPPORTED"
0x18000c0d5  mov     qword ptr [rsp+0C8h+cbIV], rdx
0x18000c0da  mov     dword ptr [rsp+0C8h+pbIV], 80090029h
0x18000c0e2  call    WPP_SF_sDsd
0x18000c0e7  mov     eax, 80090029h
0x18000c0ec  jmp     loc_18000BFF9
0x18000c0f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c0f8  lea     rax, WPP_GLOBAL_Control
0x18000c0ff  cmp     rcx, rax
0x18000c102  jz      short loc_18000C136
0x18000c104  test    byte ptr [rcx+1Ch], 1
0x18000c108  jz      short loc_18000C136
0x18000c10a  mov     rcx, [rcx+10h]
0x18000c10e  lea     rdx, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c115  mov     dword ptr [rsp+0C8h+pbOutput], 12C4h
0x18000c11d  lea     r9, aNteBufferTooSm; "NTE_BUFFER_TOO_SMALL"
0x18000c124  mov     qword ptr [rsp+0C8h+cbIV], rdx
0x18000c129  mov     dword ptr [rsp+0C8h+pbIV], 80090028h
0x18000c131  call    WPP_SF_sDsd
0x18000c136  mov     eax, 80090028h
0x18000c13b  jmp     loc_18000BFF1
0x18000c140  cmp     r10, r8
0x18000c143  ja      short loc_18000C157
0x18000c145  lea     rcx, [r10+rbx]
0x18000c149  cmp     r8, rcx
0x18000c14c  jb      short loc_18000C164
0x18000c14e  cmp     r10, r8
0x18000c151  jb      loc_18000BF3D
0x18000c157  lea     rcx, [r8+rdx]
0x18000c15b  cmp     r10, rcx
0x18000c15e  jnb     loc_18000BF3D
0x18000c164  mov     r9d, 12CDh
0x18000c16a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c171  lea     rdx, aNteBuffersOver; "NTE_BUFFERS_OVERLAP"
0x18000c178  mov     ecx, 8009002Bh
0x18000c17d  call    DebugTraceError
0x18000c182  mov     eax, 8009002Bh
0x18000c187  jmp     loc_18000BFF1
0x18000c18c  mov     r9d, 1305h
0x18000c192  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000c199  lea     rdx, aNteFail; "NTE_FAIL"
0x18000c1a0  mov     ecx, 80090020h
0x18000c1a5  call    DebugTraceError
0x18000c1aa  mov     eax, 80090020h
0x18000c1af  jmp     loc_18000BFF1
```
