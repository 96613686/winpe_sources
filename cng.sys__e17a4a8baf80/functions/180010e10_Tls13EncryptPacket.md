# Tls13EncryptPacket

- ea: `0x180010e10`
- end: `0x180011154`
- name: `Tls13EncryptPacket`
- size: `836`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010b30`

## callees

- `0x180010e10`
- `0x1800112d0`
- `0x18001155c`
- `0x1800123d0`

## string_xrefs

- `0x180010fed`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18001103b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180011085`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800110d6`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180011132`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800a5bf9`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
0x180010e10  mov     r11, rsp
0x180010e13  mov     [r11+10h], rbx
0x180010e17  mov     [r11+18h], rsi
0x180010e1b  push    rdi
0x180010e1c  sub     rsp, 0C0h
0x180010e23  mov     [rsp+0C8h+pPaddingInfo], 58h ; 'X'
0x180010e2b  xorps   xmm0, xmm0
0x180010e2e  mov     [rsp+0C8h+var_64], 1
0x180010e36  mov     rax, rdx
0x180010e39  lea     rdx, [r11-74h]
0x180010e3d  mov     ebx, r9d
0x180010e40  xor     esi, esi
0x180010e42  mov     [r11-60h], rdx
0x180010e46  xor     edx, edx
0x180010e48  mov     [r11+20h], esi
0x180010e4c  mov     qword ptr [r11-58h], 0Ch
0x180010e54  mov     r10, r8
0x180010e57  mov     [r11-44h], edx
0x180010e5b  movups  [rsp+0C8h+var_78], xmm0
0x180010e60  movups  xmmword ptr [r11-40h], xmm0
0x180010e65  movups  xmmword ptr [r11-30h], xmm0
0x180010e6a  movups  xmmword ptr [r11-20h], xmm0
0x180010e6f  test    rcx, rcx
0x180010e72  jz      loc_180010FCE
0x180010e78  test    rax, rax
0x180010e7b  jz      loc_180010FCE
0x180010e81  test    r8, r8
0x180010e84  jz      loc_180010FCE
0x180010e8a  lea     ecx, [rbx-1]
0x180010e8d  cmp     ecx, 4000h
0x180010e93  ja      loc_180010FCE
0x180010e99  mov     r8, [rsp+0C8h+arg_20]
0x180010ea1  test    r8, r8
0x180010ea4  jz      loc_180010FCE
0x180010eaa  mov     rdi, [rsp+0C8h+arg_30]
0x180010eb2  test    rdi, rdi
0x180010eb5  jz      loc_180010FCE
0x180010ebb  cmp     dword ptr [rax+8], 304h
0x180010ec2  jnz     loc_180011066
0x180010ec8  cmp     dword ptr [rax+6Ch], 5
0x180010ecc  jnz     loc_180011066
0x180010ed2  mov     edx, [rsp+0C8h+arg_28]
0x180010ed9  lea     ecx, [rbx+10h]
0x180010edc  movzx   r9d, cx
0x180010ee0  mov     [r11+8], rbp
0x180010ee4  lea     ebp, [r9+5]
0x180010ee8  cmp     edx, ebp
0x180010eea  jb      loc_1800110B7
0x180010ef0  lea     r11, [r8+5]
0x180010ef4  cmp     r11, r10
0x180010ef7  jnz     loc_180011108
0x180010efd  movzx   ecx, [rsp+0C8h+arg_40]
0x180010f05  lea     rdx, [r8+5]
0x180010f09  mov     [r8], cl
0x180010f0c  add     rdx, rbx
0x180010f0f  mov     [r8+4], r9b
0x180010f13  movzx   ecx, r9w
0x180010f17  shr     cx, 8
0x180010f1b  lea     r9, [rsp+0C8h+pPaddingInfo]; pPaddingInfo
0x180010f20  mov     [r8+3], cl
0x180010f24  mov     word ptr [r8+1], 303h
0x180010f2b  mov     ecx, [rax+38h]
0x180010f2e  mov     dword ptr [rsp+0C8h+var_78+4], ecx
0x180010f32  mov     rcx, [rsp+0C8h+arg_38]
0x180010f3a  mov     [rsp+0C8h+dwFlags], esi; dwFlags
0x180010f3e  bswap   rcx
0x180010f41  xor     rcx, [rax+3Ch]
0x180010f45  mov     qword ptr [rsp+0C8h+var_78+8], rcx
0x180010f4a  lea     rcx, [rsp+0C8h+arg_18]
0x180010f52  mov     [rsp+0C8h+pcbResult], rcx; pcbResult
0x180010f57  mov     rcx, [rax+20h]; hKey
0x180010f5b  mov     [rsp+0C8h+cbOutput], ebx; cbOutput
0x180010f5f  mov     [rsp+0C8h+pbOutput], r11; pbOutput
0x180010f64  mov     [rsp+0C8h+var_50], r8
0x180010f69  mov     r8d, ebx; cbInput
0x180010f6c  mov     [rsp+0C8h+var_40], rdx
0x180010f74  mov     rdx, r10; pbInput
0x180010f77  mov     [rsp+0C8h+cbIV], esi; cbIV
0x180010f7b  mov     [rsp+0C8h+pbIV], rsi; pbIV
0x180010f80  mov     [rsp+0C8h+var_48], 5
0x180010f8b  mov     [rsp+0C8h+var_38], 10h
0x180010f96  call    BCryptEncrypt
0x180010f9b  mov     esi, eax
0x180010f9d  test    eax, eax
0x180010f9f  js      short loc_18001101C
0x180010fa1  cmp     [rsp+0C8h+arg_18], ebx
0x180010fa8  jnz     loc_18001112C
0x180010fae  mov     [rdi], ebp
0x180010fb0  mov     rbp, [rsp+0C8h+arg_0]
0x180010fb8  lea     r11, [rsp+0C8h+var_8]
0x180010fc0  mov     rbx, [r11+18h]
0x180010fc4  mov     rsi, [r11+20h]
0x180010fc8  mov     rsp, r11
0x180010fcb  pop     rdi
0x180010fcc  retn
0x180010fce  mov     rcx, cs:WPP_GLOBAL_Control
0x180010fd5  lea     rax, WPP_GLOBAL_Control
0x180010fdc  cmp     rcx, rax
0x180010fdf  jz      short loc_180011015
0x180010fe1  mov     edx, [rcx+2Ch]
0x180010fe4  test    dl, 1
0x180010fe7  jz      short loc_180011015
0x180010fe9  mov     rcx, [rcx+18h]
0x180010fed  lea     rdx, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010ff4  mov     dword ptr [rsp+0C8h+pbOutput], 12B5h
0x180010ffc  lea     r9, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x180011003  mov     qword ptr [rsp+0C8h+cbIV], rdx
0x180011008  mov     dword ptr [rsp+0C8h+pbIV], 80090027h
0x180011010  call    WPP_SF_sDsd
0x180011015  mov     eax, 80090027h
0x18001101a  jmp     short loc_180010FB8
0x18001101c  mov     rcx, cs:WPP_GLOBAL_Control
0x180011023  lea     rax, WPP_GLOBAL_Control
0x18001102a  cmp     rcx, rax
0x18001102d  jz      short loc_18001105F
0x18001102f  mov     edx, [rcx+2Ch]
0x180011032  test    dl, 1
0x180011035  jz      short loc_18001105F
0x180011037  mov     rcx, [rcx+18h]
0x18001103b  lea     rdx, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011042  mov     dword ptr [rsp+0C8h+pbOutput], 1300h
0x18001104a  lea     r9, aStatus; "Status"
0x180011051  mov     qword ptr [rsp+0C8h+cbIV], rdx
0x180011056  mov     dword ptr [rsp+0C8h+pbIV], esi
0x18001105a  call    WPP_SF_sDsd
0x18001105f  mov     eax, esi
0x180011061  jmp     loc_180010FB0
0x180011066  mov     rcx, cs:WPP_GLOBAL_Control
0x18001106d  lea     rax, WPP_GLOBAL_Control
0x180011074  cmp     rcx, rax
0x180011077  jz      short loc_1800110AD
0x180011079  mov     edx, [rcx+2Ch]
0x18001107c  test    dl, 1
0x18001107f  jz      short loc_1800110AD
0x180011081  mov     rcx, [rcx+18h]
0x180011085  lea     rdx, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001108c  mov     dword ptr [rsp+0C8h+pbOutput], 12BCh
0x180011094  lea     r9, aNteNotSupporte; "NTE_NOT_SUPPORTED"
0x18001109b  mov     qword ptr [rsp+0C8h+cbIV], rdx
0x1800110a0  mov     dword ptr [rsp+0C8h+pbIV], 80090029h
0x1800110a8  call    WPP_SF_sDsd
0x1800110ad  mov     eax, 80090029h
0x1800110b2  jmp     loc_180010FB8
0x1800110b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110be  lea     rax, WPP_GLOBAL_Control
0x1800110c5  cmp     rcx, rax
0x1800110c8  jz      short loc_1800110FE
0x1800110ca  mov     edx, [rcx+2Ch]
0x1800110cd  test    dl, 1
0x1800110d0  jz      short loc_1800110FE
0x1800110d2  mov     rcx, [rcx+18h]
0x1800110d6  lea     rdx, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800110dd  mov     dword ptr [rsp+0C8h+pbOutput], 12C4h
0x1800110e5  lea     r9, aNteBufferTooSm; "NTE_BUFFER_TOO_SMALL"
0x1800110ec  mov     qword ptr [rsp+0C8h+cbIV], rdx
0x1800110f1  mov     dword ptr [rsp+0C8h+pbIV], 80090028h
0x1800110f9  call    WPP_SF_sDsd
0x1800110fe  mov     eax, 80090028h
0x180011103  jmp     loc_180010FB0
0x180011108  cmp     r10, r8
0x18001110b  ja      loc_1800A5BE6
0x180011111  lea     rcx, [r10+rbx]
0x180011115  cmp     r8, rcx
0x180011118  jb      loc_1800A5BF3
0x18001111e  cmp     r10, r8
0x180011121  jb      loc_180010EFD
0x180011127  jmp     loc_1800A5BE6
0x18001112c  mov     r9d, 1305h
0x180011132  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011139  lea     rdx, aNteFail; "NTE_FAIL"
0x180011140  mov     ecx, 80090020h
0x180011145  call    DebugTraceError
0x18001114a  mov     eax, 80090020h
0x18001114f  jmp     loc_180010FB0
0x1800a5be6  lea     rcx, [r8+rdx]
0x1800a5bea  cmp     r10, rcx
0x1800a5bed  jnb     loc_180010EFD
0x1800a5bf3  mov     r9d, 12CDh
0x1800a5bf9  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800a5c00  lea     rdx, aNteBuffersOver; "NTE_BUFFERS_OVERLAP"
0x1800a5c07  mov     ecx, 8009002Bh
0x1800a5c0c  call    DebugTraceError
0x1800a5c11  mov     eax, 8009002Bh
0x1800a5c16  jmp     loc_180010FB0
```
