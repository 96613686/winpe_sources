# Tls13EncryptPacket

- ea: `0x180006cf0`
- end: `0x180007034`
- name: `Tls13EncryptPacket`
- size: `836`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006a10`

## callees

- `0x180006cf0`
- `0x1800071b0`
- `0x18000743c`
- `0x1800082b0`

## string_xrefs

- `0x180006ecd`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180006f1b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180006f65`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180006fb6`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180007012`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18009ee5b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
  _DWORD *v11; // rdi
  int v12; // r9d
  int v13; // ebp
  void *v14; // rcx
  NTSTATUS result; // eax
  int v16; // r8d
  NTSTATUS v17; // esi
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
          goto LABEL_36;
        if ( a5 < &v10[cbOutput] )
        {
LABEL_37:
          DebugTraceError(
            2148073515LL,
            "NTE_BUFFERS_OVERLAP",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            4813);
          return -2146893781;
        }
        if ( v10 >= a5 )
        {
LABEL_36:
          if ( v10 < &a5[a6] )
            goto LABEL_37;
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
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
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
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
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
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
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
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
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
0x180006cf0  mov     r11, rsp
0x180006cf3  mov     [r11+10h], rbx
0x180006cf7  mov     [r11+18h], rsi
0x180006cfb  push    rdi
0x180006cfc  sub     rsp, 0C0h
0x180006d03  mov     [rsp+0C8h+pPaddingInfo], 58h ; 'X'
0x180006d0b  xorps   xmm0, xmm0
0x180006d0e  mov     [rsp+0C8h+var_64], 1
0x180006d16  mov     rax, rdx
0x180006d19  lea     rdx, [r11-74h]
0x180006d1d  mov     ebx, r9d
0x180006d20  xor     esi, esi
0x180006d22  mov     [r11-60h], rdx
0x180006d26  xor     edx, edx
0x180006d28  mov     [r11+20h], esi
0x180006d2c  mov     qword ptr [r11-58h], 0Ch
0x180006d34  mov     r10, r8
0x180006d37  mov     [r11-44h], edx
0x180006d3b  movups  [rsp+0C8h+var_78], xmm0
0x180006d40  movups  xmmword ptr [r11-40h], xmm0
0x180006d45  movups  xmmword ptr [r11-30h], xmm0
0x180006d4a  movups  xmmword ptr [r11-20h], xmm0
0x180006d4f  test    rcx, rcx
0x180006d52  jz      loc_180006EAE
0x180006d58  test    rax, rax
0x180006d5b  jz      loc_180006EAE
0x180006d61  test    r8, r8
0x180006d64  jz      loc_180006EAE
0x180006d6a  lea     ecx, [rbx-1]
0x180006d6d  cmp     ecx, 4000h
0x180006d73  ja      loc_180006EAE
0x180006d79  mov     r8, [rsp+0C8h+arg_20]
0x180006d81  test    r8, r8
0x180006d84  jz      loc_180006EAE
0x180006d8a  mov     rdi, [rsp+0C8h+arg_30]
0x180006d92  test    rdi, rdi
0x180006d95  jz      loc_180006EAE
0x180006d9b  cmp     dword ptr [rax+8], 304h
0x180006da2  jnz     loc_180006F46
0x180006da8  cmp     dword ptr [rax+6Ch], 5
0x180006dac  jnz     loc_180006F46
0x180006db2  mov     edx, [rsp+0C8h+arg_28]
0x180006db9  lea     ecx, [rbx+10h]
0x180006dbc  movzx   r9d, cx
0x180006dc0  mov     [r11+8], rbp
0x180006dc4  lea     ebp, [r9+5]
0x180006dc8  cmp     edx, ebp
0x180006dca  jb      loc_180006F97
0x180006dd0  lea     r11, [r8+5]
0x180006dd4  cmp     r11, r10
0x180006dd7  jnz     loc_180006FE8
0x180006ddd  movzx   ecx, [rsp+0C8h+arg_40]
0x180006de5  lea     rdx, [r8+5]
0x180006de9  mov     [r8], cl
0x180006dec  add     rdx, rbx
0x180006def  mov     [r8+4], r9b
0x180006df3  movzx   ecx, r9w
0x180006df7  shr     cx, 8
0x180006dfb  lea     r9, [rsp+0C8h+pPaddingInfo]; pPaddingInfo
0x180006e00  mov     [r8+3], cl
0x180006e04  mov     word ptr [r8+1], 303h
0x180006e0b  mov     ecx, [rax+38h]
0x180006e0e  mov     dword ptr [rsp+0C8h+var_78+4], ecx
0x180006e12  mov     rcx, [rsp+0C8h+arg_38]
0x180006e1a  mov     [rsp+0C8h+dwFlags], esi; dwFlags
0x180006e1e  bswap   rcx
0x180006e21  xor     rcx, [rax+3Ch]
0x180006e25  mov     qword ptr [rsp+0C8h+var_78+8], rcx
0x180006e2a  lea     rcx, [rsp+0C8h+arg_18]
0x180006e32  mov     [rsp+0C8h+pcbResult], rcx; pcbResult
0x180006e37  mov     rcx, [rax+20h]; hKey
0x180006e3b  mov     [rsp+0C8h+cbOutput], ebx; cbOutput
0x180006e3f  mov     [rsp+0C8h+pbOutput], r11; pbOutput
0x180006e44  mov     [rsp+0C8h+var_50], r8
0x180006e49  mov     r8d, ebx; cbInput
0x180006e4c  mov     [rsp+0C8h+var_40], rdx
0x180006e54  mov     rdx, r10; pbInput
0x180006e57  mov     [rsp+0C8h+cbIV], esi; cbIV
0x180006e5b  mov     [rsp+0C8h+pbIV], rsi; pbIV
0x180006e60  mov     [rsp+0C8h+var_48], 5
0x180006e6b  mov     [rsp+0C8h+var_38], 10h
0x180006e76  call    BCryptEncrypt
0x180006e7b  mov     esi, eax
0x180006e7d  test    eax, eax
0x180006e7f  js      short loc_180006EFC
0x180006e81  cmp     [rsp+0C8h+arg_18], ebx
0x180006e88  jnz     loc_18000700C
0x180006e8e  mov     [rdi], ebp
0x180006e90  mov     rbp, [rsp+0C8h+arg_0]
0x180006e98  lea     r11, [rsp+0C8h+var_8]
0x180006ea0  mov     rbx, [r11+18h]
0x180006ea4  mov     rsi, [r11+20h]
0x180006ea8  mov     rsp, r11
0x180006eab  pop     rdi
0x180006eac  retn
0x180006eae  mov     rcx, cs:WPP_GLOBAL_Control
0x180006eb5  lea     rax, WPP_GLOBAL_Control
0x180006ebc  cmp     rcx, rax
0x180006ebf  jz      short loc_180006EF5
0x180006ec1  mov     edx, [rcx+2Ch]
0x180006ec4  test    dl, 1
0x180006ec7  jz      short loc_180006EF5
0x180006ec9  mov     rcx, [rcx+18h]
0x180006ecd  lea     rdx, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006ed4  mov     dword ptr [rsp+0C8h+pbOutput], 12B5h
0x180006edc  lea     r9, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x180006ee3  mov     qword ptr [rsp+0C8h+cbIV], rdx
0x180006ee8  mov     dword ptr [rsp+0C8h+pbIV], 80090027h
0x180006ef0  call    WPP_SF_sDsd
0x180006ef5  mov     eax, 80090027h
0x180006efa  jmp     short loc_180006E98
0x180006efc  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f03  lea     rax, WPP_GLOBAL_Control
0x180006f0a  cmp     rcx, rax
0x180006f0d  jz      short loc_180006F3F
0x180006f0f  mov     edx, [rcx+2Ch]
0x180006f12  test    dl, 1
0x180006f15  jz      short loc_180006F3F
0x180006f17  mov     rcx, [rcx+18h]
0x180006f1b  lea     rdx, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006f22  mov     dword ptr [rsp+0C8h+pbOutput], 1300h
0x180006f2a  lea     r9, aStatus; "Status"
0x180006f31  mov     qword ptr [rsp+0C8h+cbIV], rdx
0x180006f36  mov     dword ptr [rsp+0C8h+pbIV], esi
0x180006f3a  call    WPP_SF_sDsd
0x180006f3f  mov     eax, esi
0x180006f41  jmp     loc_180006E90
0x180006f46  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f4d  lea     rax, WPP_GLOBAL_Control
0x180006f54  cmp     rcx, rax
0x180006f57  jz      short loc_180006F8D
0x180006f59  mov     edx, [rcx+2Ch]
0x180006f5c  test    dl, 1
0x180006f5f  jz      short loc_180006F8D
0x180006f61  mov     rcx, [rcx+18h]
0x180006f65  lea     rdx, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006f6c  mov     dword ptr [rsp+0C8h+pbOutput], 12BCh
0x180006f74  lea     r9, aNteNotSupporte; "NTE_NOT_SUPPORTED"
0x180006f7b  mov     qword ptr [rsp+0C8h+cbIV], rdx
0x180006f80  mov     dword ptr [rsp+0C8h+pbIV], 80090029h
0x180006f88  call    WPP_SF_sDsd
0x180006f8d  mov     eax, 80090029h
0x180006f92  jmp     loc_180006E98
0x180006f97  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f9e  lea     rax, WPP_GLOBAL_Control
0x180006fa5  cmp     rcx, rax
0x180006fa8  jz      short loc_180006FDE
0x180006faa  mov     edx, [rcx+2Ch]
0x180006fad  test    dl, 1
0x180006fb0  jz      short loc_180006FDE
0x180006fb2  mov     rcx, [rcx+18h]
0x180006fb6  lea     rdx, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006fbd  mov     dword ptr [rsp+0C8h+pbOutput], 12C4h
0x180006fc5  lea     r9, aNteBufferTooSm; "NTE_BUFFER_TOO_SMALL"
0x180006fcc  mov     qword ptr [rsp+0C8h+cbIV], rdx
0x180006fd1  mov     dword ptr [rsp+0C8h+pbIV], 80090028h
0x180006fd9  call    WPP_SF_sDsd
0x180006fde  mov     eax, 80090028h
0x180006fe3  jmp     loc_180006E90
0x180006fe8  cmp     r10, r8
0x180006feb  ja      loc_18009EE48
0x180006ff1  lea     rcx, [r10+rbx]
0x180006ff5  cmp     r8, rcx
0x180006ff8  jb      loc_18009EE55
0x180006ffe  cmp     r10, r8
0x180007001  jb      loc_180006DDD
0x180007007  jmp     loc_18009EE48
0x18000700c  mov     r9d, 1305h
0x180007012  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007019  lea     rdx, aNteFail; "NTE_FAIL"
0x180007020  mov     ecx, 80090020h
0x180007025  call    DebugTraceError
0x18000702a  mov     eax, 80090020h
0x18000702f  jmp     loc_180006E90
0x18009ee48  lea     rcx, [r8+rdx]
0x18009ee4c  cmp     r10, rcx
0x18009ee4f  jnb     loc_180006DDD
0x18009ee55  mov     r9d, 12CDh
0x18009ee5b  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18009ee62  lea     rdx, aNteBuffersOver; "NTE_BUFFERS_OVERLAP"
0x18009ee69  mov     ecx, 8009002Bh
0x18009ee6e  call    DebugTraceError
0x18009ee73  mov     eax, 8009002Bh
0x18009ee78  jmp     loc_180006E90
```
