# Tls13DecryptPacket

- ea: `0x180007760`
- end: `0x180007b4d`
- name: `Tls13DecryptPacket`
- size: `1005`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int64, unsigned int, PUCHAR pbOutput, ULONG cbOutput, ULONG *, unsigned __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007490`

## callees

- `0x18000743c`
- `0x180007760`
- `0x180007b60`
- `0x1800082b0`

## string_xrefs

- `0x180007959`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800079af`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x1800079f7`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180007a55`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180007ab3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180007adb`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180007b03`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x180007b2b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18009f05b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall Tls13DecryptPacket(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned int a4,
        PUCHAR pbOutput,
        ULONG cbOutput,
        ULONG *a7,
        unsigned __int64 a8)
{
  ULONG *v8; // rbx
  unsigned __int16 v9; // ax
  unsigned __int16 v10; // ax
  int v11; // esi
  void *v12; // rcx
  NTSTATUS v13; // edi
  int v15; // edx
  int v16; // edx
  int v17; // edx
  int v18; // edx
  __int128 v19; // [rsp+50h] [rbp-78h] BYREF
  _DWORD pPaddingInfo[2]; // [rsp+60h] [rbp-68h] BYREF
  char *v21; // [rsp+68h] [rbp-60h]
  __int64 v22; // [rsp+70h] [rbp-58h]
  unsigned __int64 v23; // [rsp+78h] [rbp-50h]
  int v24; // [rsp+80h] [rbp-48h]
  int v25; // [rsp+84h] [rbp-44h]
  __int128 v26; // [rsp+88h] [rbp-40h]
  __int128 v27; // [rsp+98h] [rbp-30h]
  __int128 v28; // [rsp+A8h] [rbp-20h]
  ULONG pcbResult; // [rsp+D0h] [rbp+8h] BYREF

  pPaddingInfo[0] = 88;
  pPaddingInfo[1] = 1;
  v21 = (char *)&v19 + 4;
  pcbResult = 0;
  v22 = 12;
  v25 = 0;
  v19 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  if ( !a1 || !a2 || !a3 || !pbOutput || (v8 = a7) == 0 )
  {
    DebugTraceError(
      2148073511LL,
      "NTE_INVALID_PARAMETER",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      4912);
    return 2148073511LL;
  }
  if ( *(_DWORD *)(a2 + 8) != 772 || *(_DWORD *)(a2 + 108) != 5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v17 = *((_DWORD *)WPP_GLOBAL_Control + 11);
      if ( (v17 & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v17,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          (unsigned int)"NTE_NOT_SUPPORTED",
          41,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          55);
    }
    return 2148073513LL;
  }
  if ( a4 - 22 > 0x40EA )
  {
    DebugTraceError(2148073477LL, "NTE_BAD_DATA", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 4927);
    return 2148073477LL;
  }
  if ( (PUCHAR)(a3 + 5) != pbOutput )
  {
    if ( a3 <= (unsigned __int64)pbOutput )
    {
      if ( (unsigned __int64)pbOutput < a3 + a4 )
        goto LABEL_43;
      if ( a3 < (unsigned __int64)pbOutput )
        goto LABEL_10;
    }
    if ( a3 >= (unsigned __int64)&pbOutput[cbOutput] )
      goto LABEL_10;
LABEL_43:
    DebugTraceError(
      2148073515LL,
      "NTE_BUFFERS_OVERLAP",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
      4936);
    return 2148073515LL;
  }
LABEL_10:
  if ( *(_BYTE *)(a3 + 1) == 0xFE )
  {
    DebugTraceError(2148073477LL, "NTE_BAD_DATA", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c", 4956);
    return 2148073477LL;
  }
  else
  {
    v9 = _byteswap_ushort(*(_WORD *)(a3 + 3));
    if ( v9 > 0x10u && v9 + 5 == a4 )
    {
      v10 = v9 - 16;
      v11 = v10;
      if ( cbOutput < v10 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v18 = *((_DWORD *)WPP_GLOBAL_Control + 11);
          if ( (v18 & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 3),
              v18,
              (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              (unsigned int)"NTE_BUFFER_TOO_SMALL",
              40,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              105);
        }
        return 2148073512LL;
      }
      else
      {
        DWORD1(v19) = *(_DWORD *)(a2 + 56);
        *((_QWORD *)&v19 + 1) = *(_QWORD *)(a2 + 60) ^ _byteswap_uint64(a8);
        v23 = a3;
        *(_QWORD *)&v26 = v10 + a3 + 5;
        v12 = *(void **)(a2 + 32);
        v24 = 5;
        DWORD2(v26) = 16;
        v13 = BCryptDecrypt(v12, (PUCHAR)(a3 + 5), v10, pPaddingInfo, 0, 0, pbOutput, cbOutput, &pcbResult, 0);
        if ( v13 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            v16 = *((_DWORD *)WPP_GLOBAL_Control + 11);
            if ( (v16 & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 3),
                v16,
                (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                (unsigned int)"Status",
                v13,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
                137);
          }
        }
        else
        {
          if ( pcbResult != v11 )
          {
            DebugTraceError(
              2148073516LL,
              "NTE_DECRYPTION_FAILURE",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
              5006);
            return 2148073516LL;
          }
          *v8 = pcbResult;
        }
        return (unsigned int)v13;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        v15 = *((_DWORD *)WPP_GLOBAL_Control + 11);
        if ( (v15 & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v15,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            (unsigned int)"NTE_BAD_DATA",
            5,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
            98);
      }
      return 2148073477LL;
    }
  }
}

```

## disassembly

```asm
0x180007760  mov     r11, rsp
0x180007763  mov     [r11+20h], rbx
0x180007767  push    rbp
0x180007768  sub     rsp, 0C0h
0x18000776f  mov     [rsp+0C8h+pPaddingInfo], 58h ; 'X'
0x180007777  lea     rax, [r11-74h]
0x18000777b  mov     [rsp+0C8h+var_64], 1
0x180007783  xorps   xmm0, xmm0
0x180007786  xor     ebp, ebp
0x180007788  mov     [r11-60h], rax
0x18000778c  xor     eax, eax
0x18000778e  mov     [r11+8], ebp
0x180007792  mov     qword ptr [r11-58h], 0Ch
0x18000779a  mov     r10, rdx
0x18000779d  mov     [r11-44h], eax
0x1800077a1  movups  [rsp+0C8h+var_78], xmm0
0x1800077a6  movups  xmmword ptr [r11-40h], xmm0
0x1800077ab  movups  xmmword ptr [r11-30h], xmm0
0x1800077b0  movups  xmmword ptr [r11-20h], xmm0
0x1800077b5  test    rcx, rcx
0x1800077b8  jz      loc_180007B25
0x1800077be  test    rdx, rdx
0x1800077c1  jz      loc_180007B25
0x1800077c7  test    r8, r8
0x1800077ca  jz      loc_180007B25
0x1800077d0  mov     rdx, [rsp+0C8h+arg_20]
0x1800077d8  test    rdx, rdx
0x1800077db  jz      loc_180007B25
0x1800077e1  mov     rbx, [rsp+0C8h+arg_30]
0x1800077e9  test    rbx, rbx
0x1800077ec  jz      loc_180007B25
0x1800077f2  cmp     dword ptr [r10+8], 304h
0x1800077fa  jnz     loc_1800079D8
0x180007800  cmp     dword ptr [r10+6Ch], 5
0x180007805  jnz     loc_1800079D8
0x18000780b  lea     eax, [r9-16h]
0x18000780f  cmp     eax, 40EAh
0x180007814  ja      loc_180007AFD
0x18000781a  mov     [r11+18h], rdi
0x18000781e  lea     r11, [r8+5]
0x180007822  mov     edi, [rsp+0C8h+arg_28]
0x180007829  cmp     r11, rdx
0x18000782c  jnz     loc_180007A87
0x180007832  cmp     byte ptr [r8+1], 0FEh
0x180007837  jz      loc_180007AD5
0x18000783d  movzx   eax, byte ptr [r8+3]
0x180007842  movzx   ecx, byte ptr [r8+4]
0x180007847  shl     ax, 8
0x18000784b  or      ax, cx
0x18000784e  cmp     ax, 10h
0x180007852  jbe     loc_18000793A
0x180007858  movzx   ecx, ax
0x18000785b  add     ecx, 5
0x18000785e  cmp     ecx, r9d
0x180007861  jnz     loc_18000793A
0x180007867  sub     ax, 10h
0x18000786b  mov     [rsp+0C8h+arg_8], rsi
0x180007873  movzx   esi, ax
0x180007876  cmp     edi, esi
0x180007878  jb      loc_180007A36
0x18000787e  mov     eax, [r10+38h]
0x180007882  lea     rcx, [r8+5]
0x180007886  mov     dword ptr [rsp+0C8h+var_78+4], eax
0x18000788a  lea     r9, [rsp+0C8h+pPaddingInfo]; pPaddingInfo
0x18000788f  mov     rax, [rsp+0C8h+arg_38]
0x180007897  add     rcx, rsi
0x18000789a  mov     [rsp+0C8h+dwFlags], ebp; dwFlags
0x18000789e  bswap   rax
0x1800078a1  xor     rax, [r10+3Ch]
0x1800078a5  mov     qword ptr [rsp+0C8h+var_78+8], rax
0x1800078aa  lea     rax, [rsp+0C8h+arg_0]
0x1800078b2  mov     [rsp+0C8h+pcbResult], rax; pcbResult
0x1800078b7  mov     [rsp+0C8h+cbOutput], edi; cbOutput
0x1800078bb  mov     [rsp+0C8h+pbOutput], rdx; pbOutput
0x1800078c0  mov     rdx, r11; pbInput
0x1800078c3  mov     [rsp+0C8h+var_50], r8
0x1800078c8  mov     r8d, esi; cbInput
0x1800078cb  mov     [rsp+0C8h+var_40], rcx
0x1800078d3  mov     rcx, [r10+20h]; hKey
0x1800078d7  mov     [rsp+0C8h+cbIV], ebp; cbIV
0x1800078db  mov     [rsp+0C8h+pbIV], rbp; pbIV
0x1800078e0  mov     [rsp+0C8h+var_48], 5
0x1800078eb  mov     [rsp+0C8h+var_38], 10h
0x1800078f6  call    BCryptDecrypt
0x1800078fb  mov     edi, eax
0x1800078fd  test    eax, eax
0x1800078ff  js      loc_180007988
0x180007905  mov     eax, [rsp+0C8h+arg_0]
0x18000790c  cmp     eax, esi
0x18000790e  jnz     loc_180007AAD
0x180007914  mov     [rbx], eax
0x180007916  mov     eax, edi
0x180007918  mov     rsi, [rsp+0C8h+arg_8]
0x180007920  mov     rdi, [rsp+0C8h+arg_10]
0x180007928  mov     rbx, [rsp+0C8h+arg_18]
0x180007930  add     rsp, 0C0h
0x180007937  pop     rbp
0x180007938  retn
0x18000793a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007941  lea     rax, WPP_GLOBAL_Control
0x180007948  cmp     rcx, rax
0x18000794b  jz      short loc_180007981
0x18000794d  mov     edx, [rcx+2Ch]
0x180007950  test    dl, 1
0x180007953  jz      short loc_180007981
0x180007955  mov     rcx, [rcx+18h]
0x180007959  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007960  mov     dword ptr [rsp+0C8h+pbOutput], 1362h
0x180007968  lea     r9, aNteBadData; "NTE_BAD_DATA"
0x18000796f  mov     qword ptr [rsp+0C8h+cbIV], r8
0x180007974  mov     dword ptr [rsp+0C8h+pbIV], 80090005h
0x18000797c  call    WPP_SF_sDsd
0x180007981  mov     eax, 80090005h
0x180007986  jmp     short loc_180007920
0x180007988  mov     rcx, cs:WPP_GLOBAL_Control
0x18000798f  lea     rax, WPP_GLOBAL_Control
0x180007996  cmp     rcx, rax
0x180007999  jz      loc_180007916
0x18000799f  mov     edx, [rcx+2Ch]
0x1800079a2  test    dl, 1
0x1800079a5  jz      loc_180007916
0x1800079ab  mov     rcx, [rcx+18h]
0x1800079af  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800079b6  mov     dword ptr [rsp+0C8h+pbOutput], 1389h
0x1800079be  lea     r9, aStatus; "Status"
0x1800079c5  mov     qword ptr [rsp+0C8h+cbIV], r8
0x1800079ca  mov     dword ptr [rsp+0C8h+pbIV], edi
0x1800079ce  call    WPP_SF_sDsd
0x1800079d3  jmp     loc_180007916
0x1800079d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079df  lea     rax, WPP_GLOBAL_Control
0x1800079e6  cmp     rcx, rax
0x1800079e9  jz      short loc_180007A1F
0x1800079eb  mov     edx, [rcx+2Ch]
0x1800079ee  test    dl, 1
0x1800079f1  jz      short loc_180007A1F
0x1800079f3  mov     rcx, [rcx+18h]
0x1800079f7  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800079fe  mov     dword ptr [rsp+0C8h+pbOutput], 1337h
0x180007a06  lea     r9, aNteNotSupporte; "NTE_NOT_SUPPORTED"
0x180007a0d  mov     qword ptr [rsp+0C8h+cbIV], r8
0x180007a12  mov     dword ptr [rsp+0C8h+pbIV], 80090029h
0x180007a1a  call    WPP_SF_sDsd
0x180007a1f  mov     rbx, [rsp+0C8h+arg_18]
0x180007a27  mov     eax, 80090029h
0x180007a2c  add     rsp, 0C0h
0x180007a33  pop     rbp
0x180007a34  retn
0x180007a36  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a3d  lea     rax, WPP_GLOBAL_Control
0x180007a44  cmp     rcx, rax
0x180007a47  jz      short loc_180007A7D
0x180007a49  mov     edx, [rcx+2Ch]
0x180007a4c  test    dl, 1
0x180007a4f  jz      short loc_180007A7D
0x180007a51  mov     rcx, [rcx+18h]
0x180007a55  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007a5c  mov     dword ptr [rsp+0C8h+pbOutput], 1369h
0x180007a64  lea     r9, aNteBufferTooSm; "NTE_BUFFER_TOO_SMALL"
0x180007a6b  mov     qword ptr [rsp+0C8h+cbIV], r8
0x180007a70  mov     dword ptr [rsp+0C8h+pbIV], 80090028h
0x180007a78  call    WPP_SF_sDsd
0x180007a7d  mov     eax, 80090028h
0x180007a82  jmp     loc_180007918
0x180007a87  cmp     r8, rdx
0x180007a8a  ja      loc_18009F048
0x180007a90  mov     eax, r9d
0x180007a93  add     rax, r8
0x180007a96  cmp     rdx, rax
0x180007a99  jb      loc_18009F055
0x180007a9f  cmp     r8, rdx
0x180007aa2  jb      loc_180007832
0x180007aa8  jmp     loc_18009F048
0x180007aad  mov     r9d, 138Eh
0x180007ab3  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007aba  lea     rdx, aNteDecryptionF; "NTE_DECRYPTION_FAILURE"
0x180007ac1  mov     ecx, 8009002Ch
0x180007ac6  call    DebugTraceError
0x180007acb  mov     eax, 8009002Ch
0x180007ad0  jmp     loc_180007918
0x180007ad5  mov     r9d, 135Ch
0x180007adb  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007ae2  lea     rdx, aNteBadData; "NTE_BAD_DATA"
0x180007ae9  mov     ecx, 80090005h
0x180007aee  call    DebugTraceError
0x180007af3  mov     eax, 80090005h
0x180007af8  jmp     loc_180007920
0x180007afd  mov     r9d, 133Fh
0x180007b03  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007b0a  lea     rdx, aNteBadData; "NTE_BAD_DATA"
0x180007b11  mov     ecx, 80090005h
0x180007b16  call    DebugTraceError
0x180007b1b  mov     eax, 80090005h
0x180007b20  jmp     loc_180007928
0x180007b25  mov     r9d, 1330h
0x180007b2b  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007b32  lea     rdx, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x180007b39  mov     ecx, 80090027h
0x180007b3e  call    DebugTraceError
0x180007b43  mov     eax, 80090027h
0x180007b48  jmp     loc_180007928
0x18009f048  lea     rax, [rdx+rdi]
0x18009f04c  cmp     r8, rax
0x18009f04f  jnb     loc_180007832
0x18009f055  mov     r9d, 1348h
0x18009f05b  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18009f062  lea     rdx, aNteBuffersOver; "NTE_BUFFERS_OVERLAP"
0x18009f069  mov     ecx, 8009002Bh
0x18009f06e  call    DebugTraceError
0x18009f073  mov     eax, 8009002Bh
0x18009f078  jmp     loc_180007920
```
