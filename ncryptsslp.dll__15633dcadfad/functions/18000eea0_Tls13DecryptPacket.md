# Tls13DecryptPacket

- ea: `0x18000eea0`
- end: `0x18000f2bb`
- name: `Tls13DecryptPacket`
- size: `1051`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int64, unsigned int, PUCHAR pbOutput, ULONG cbOutput, ULONG *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ec00`

## callees

- `0x18000b594`
- `0x18000b654`
- `0x18000eea0`

## import_xrefs

- `bcrypt!BCryptDecrypt` at `0x18000f036`
- `bcrypt!BCryptDecrypt` at `0x18000f036`

## string_xrefs

- `0x18000f097`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000f0fa`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000f140`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000f19b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000f1d3`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000f221`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000f249`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000f271`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`
- `0x18000f299`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

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
  ULONG *v8; // rdi
  unsigned __int16 v9; // ax
  unsigned __int16 v10; // ax
  int v11; // ebx
  void *v12; // rcx
  NTSTATUS v13; // esi
  int v14; // r8d
  __int128 v16; // [rsp+50h] [rbp-78h] BYREF
  _DWORD pPaddingInfo[2]; // [rsp+60h] [rbp-68h] BYREF
  char *v18; // [rsp+68h] [rbp-60h]
  __int64 v19; // [rsp+70h] [rbp-58h]
  unsigned __int64 v20; // [rsp+78h] [rbp-50h]
  int v21; // [rsp+80h] [rbp-48h]
  int v22; // [rsp+84h] [rbp-44h]
  __int128 v23; // [rsp+88h] [rbp-40h]
  __int128 v24; // [rsp+98h] [rbp-30h]
  __int128 v25; // [rsp+A8h] [rbp-20h]
  ULONG pcbResult; // [rsp+D0h] [rbp+8h] BYREF

  pPaddingInfo[0] = 88;
  pPaddingInfo[1] = 1;
  v18 = (char *)&v16 + 4;
  pcbResult = 0;
  v19 = 12;
  v22 = 0;
  v16 = 0;
  v23 = 0;
  v24 = 0;
  v25 = 0;
  if ( !a1 || !a2 || !a3 || !pbOutput || (v8 = a7) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        a3,
        (unsigned int)"NTE_INVALID_PARAMETER",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        48);
    return 2148073511LL;
  }
  if ( *(_DWORD *)(a2 + 8) != 772 || *(_DWORD *)(a2 + 108) != 5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        a3,
        (unsigned int)"NTE_NOT_SUPPORTED",
        41,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        55);
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
        goto LABEL_39;
      if ( a3 < (unsigned __int64)pbOutput )
        goto LABEL_10;
    }
    if ( a3 >= (unsigned __int64)&pbOutput[cbOutput] )
      goto LABEL_10;
LABEL_39:
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
  v9 = _byteswap_ushort(*(_WORD *)(a3 + 3));
  if ( v9 > 0x10u && v9 + 5 == a4 )
  {
    v10 = v9 - 16;
    v11 = v10;
    if ( cbOutput < v10 )
    {
      DebugTraceError(
        2148073512LL,
        "NTE_BUFFER_TOO_SMALL",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        4969);
      return 2148073512LL;
    }
    DWORD1(v16) = *(_DWORD *)(a2 + 56);
    *((_QWORD *)&v16 + 1) = *(_QWORD *)(a2 + 60) ^ _byteswap_uint64(a8);
    v20 = a3;
    *(_QWORD *)&v23 = v10 + a3 + 5;
    v12 = *(void **)(a2 + 32);
    v21 = 5;
    DWORD2(v23) = 16;
    v13 = BCryptDecrypt(v12, (PUCHAR)(a3 + 5), v10, pPaddingInfo, 0, 0, pbOutput, cbOutput, &pcbResult, 0);
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)&WPP_GLOBAL_Control,
          v14,
          (unsigned int)"Status",
          v13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
          137);
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
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        a3,
        (unsigned int)"NTE_BAD_DATA",
        5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\tls1key.c",
        98);
    return 2148073477LL;
  }
}

```

## disassembly

```asm
0x18000eea0  mov     r11, rsp
0x18000eea3  mov     [r11+20h], rbp
0x18000eea7  push    rdi
0x18000eea8  sub     rsp, 0C0h
0x18000eeaf  mov     [rsp+0C8h+pPaddingInfo], 58h ; 'X'
0x18000eeb7  lea     rax, [r11-74h]
0x18000eebb  mov     [rsp+0C8h+var_64], 1
0x18000eec3  xorps   xmm0, xmm0
0x18000eec6  xor     ebp, ebp
0x18000eec8  mov     [r11-60h], rax
0x18000eecc  xor     eax, eax
0x18000eece  mov     [r11+8], ebp
0x18000eed2  mov     qword ptr [r11-58h], 0Ch
0x18000eeda  mov     r10, rdx
0x18000eedd  mov     [r11-44h], eax
0x18000eee1  movups  [rsp+0C8h+var_78], xmm0
0x18000eee6  movups  xmmword ptr [r11-40h], xmm0
0x18000eeeb  movups  xmmword ptr [r11-30h], xmm0
0x18000eef0  movups  xmmword ptr [r11-20h], xmm0
0x18000eef5  test    rcx, rcx
0x18000eef8  jz      loc_18000F07A
0x18000eefe  test    rdx, rdx
0x18000ef01  jz      loc_18000F07A
0x18000ef07  test    r8, r8
0x18000ef0a  jz      loc_18000F07A
0x18000ef10  mov     rdx, [rsp+0C8h+arg_20]
0x18000ef18  test    rdx, rdx
0x18000ef1b  jz      loc_18000F07A
0x18000ef21  mov     rdi, [rsp+0C8h+arg_30]
0x18000ef29  test    rdi, rdi
0x18000ef2c  jz      loc_18000F07A
0x18000ef32  cmp     dword ptr [r10+8], 304h
0x18000ef3a  jnz     loc_18000F123
0x18000ef40  cmp     dword ptr [r10+6Ch], 5
0x18000ef45  jnz     loc_18000F123
0x18000ef4b  lea     eax, [r9-16h]
0x18000ef4f  cmp     eax, 40EAh
0x18000ef54  ja      loc_18000F293
0x18000ef5a  mov     [r11+18h], rsi
0x18000ef5e  lea     r11, [r8+5]
0x18000ef62  mov     esi, [rsp+0C8h+arg_28]
0x18000ef69  cmp     r11, rdx
0x18000ef6c  jnz     loc_18000F1F5
0x18000ef72  cmp     byte ptr [r8+1], 0FEh
0x18000ef77  jz      loc_18000F1CD
0x18000ef7d  movzx   eax, byte ptr [r8+3]
0x18000ef82  movzx   ecx, byte ptr [r8+4]
0x18000ef87  shl     ax, 8
0x18000ef8b  or      ax, cx
0x18000ef8e  cmp     ax, 10h
0x18000ef92  jbe     loc_18000F17E
0x18000ef98  movzx   ecx, ax
0x18000ef9b  add     ecx, 5
0x18000ef9e  cmp     ecx, r9d
0x18000efa1  jnz     loc_18000F17E
0x18000efa7  sub     ax, 10h
0x18000efab  mov     [rsp+0C8h+arg_8], rbx
0x18000efb3  movzx   ebx, ax
0x18000efb6  cmp     esi, ebx
0x18000efb8  jb      loc_18000F243
0x18000efbe  mov     eax, [r10+38h]
0x18000efc2  lea     rcx, [r8+5]
0x18000efc6  mov     dword ptr [rsp+0C8h+var_78+4], eax
0x18000efca  lea     r9, [rsp+0C8h+pPaddingInfo]; pPaddingInfo
0x18000efcf  mov     rax, [rsp+0C8h+arg_38]
0x18000efd7  add     rcx, rbx
0x18000efda  mov     [rsp+0C8h+dwFlags], ebp; dwFlags
0x18000efde  bswap   rax
0x18000efe1  xor     rax, [r10+3Ch]
0x18000efe5  mov     qword ptr [rsp+0C8h+var_78+8], rax
0x18000efea  lea     rax, [rsp+0C8h+arg_0]
0x18000eff2  mov     [rsp+0C8h+pcbResult], rax; pcbResult
0x18000eff7  mov     [rsp+0C8h+cbOutput], esi; cbOutput
0x18000effb  mov     [rsp+0C8h+pbOutput], rdx; pbOutput
0x18000f000  mov     rdx, r11; pbInput
0x18000f003  mov     [rsp+0C8h+var_50], r8
0x18000f008  mov     r8d, ebx; cbInput
0x18000f00b  mov     [rsp+0C8h+var_40], rcx
0x18000f013  mov     rcx, [r10+20h]; hKey
0x18000f017  mov     [rsp+0C8h+cbIV], ebp; cbIV
0x18000f01b  mov     [rsp+0C8h+pbIV], rbp; pbIV
0x18000f020  mov     [rsp+0C8h+var_48], 5
0x18000f02b  mov     [rsp+0C8h+var_38], 10h
0x18000f036  call    cs:__imp_BCryptDecrypt
0x18000f03c  mov     esi, eax
0x18000f03e  test    eax, eax
0x18000f040  js      loc_18000F0D5
0x18000f046  mov     eax, [rsp+0C8h+arg_0]
0x18000f04d  cmp     eax, ebx
0x18000f04f  jnz     loc_18000F26B
0x18000f055  mov     [rdi], eax
0x18000f057  mov     eax, esi
0x18000f059  mov     rbx, [rsp+0C8h+arg_8]
0x18000f061  mov     rsi, [rsp+0C8h+arg_10]
0x18000f069  mov     rbp, [rsp+0C8h+arg_18]
0x18000f071  add     rsp, 0C0h
0x18000f078  pop     rdi
0x18000f079  retn
0x18000f07a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f081  lea     rdx, WPP_GLOBAL_Control
0x18000f088  cmp     rcx, rdx
0x18000f08b  jz      short loc_18000F0BF
0x18000f08d  test    byte ptr [rcx+1Ch], 1
0x18000f091  jz      short loc_18000F0BF
0x18000f093  mov     rcx, [rcx+10h]
0x18000f097  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f09e  mov     dword ptr [rsp+0C8h+pbOutput], 1330h
0x18000f0a6  lea     r9, aNteInvalidPara; "NTE_INVALID_PARAMETER"
0x18000f0ad  mov     qword ptr [rsp+0C8h+cbIV], rax
0x18000f0b2  mov     dword ptr [rsp+0C8h+pbIV], 80090027h
0x18000f0ba  call    WPP_SF_sDsd
0x18000f0bf  mov     eax, 80090027h
0x18000f0c4  mov     rbp, [rsp+0C8h+arg_18]
0x18000f0cc  add     rsp, 0C0h
0x18000f0d3  pop     rdi
0x18000f0d4  retn
0x18000f0d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f0dc  lea     rdx, WPP_GLOBAL_Control
0x18000f0e3  cmp     rcx, rdx
0x18000f0e6  jz      loc_18000F057
0x18000f0ec  test    byte ptr [rcx+1Ch], 1
0x18000f0f0  jz      loc_18000F057
0x18000f0f6  mov     rcx, [rcx+10h]
0x18000f0fa  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f101  mov     dword ptr [rsp+0C8h+pbOutput], 1389h
0x18000f109  lea     r9, aStatus; "Status"
0x18000f110  mov     qword ptr [rsp+0C8h+cbIV], rax
0x18000f115  mov     dword ptr [rsp+0C8h+pbIV], esi
0x18000f119  call    WPP_SF_sDsd
0x18000f11e  jmp     loc_18000F057
0x18000f123  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f12a  lea     rdx, WPP_GLOBAL_Control
0x18000f131  cmp     rcx, rdx
0x18000f134  jz      short loc_18000F168
0x18000f136  test    byte ptr [rcx+1Ch], 1
0x18000f13a  jz      short loc_18000F168
0x18000f13c  mov     rcx, [rcx+10h]
0x18000f140  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f147  mov     dword ptr [rsp+0C8h+pbOutput], 1337h
0x18000f14f  lea     r9, aNteNotSupporte; "NTE_NOT_SUPPORTED"
0x18000f156  mov     qword ptr [rsp+0C8h+cbIV], rax
0x18000f15b  mov     dword ptr [rsp+0C8h+pbIV], 80090029h
0x18000f163  call    WPP_SF_sDsd
0x18000f168  mov     rbp, [rsp+0C8h+arg_18]
0x18000f170  mov     eax, 80090029h
0x18000f175  add     rsp, 0C0h
0x18000f17c  pop     rdi
0x18000f17d  retn
0x18000f17e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f185  lea     rdx, WPP_GLOBAL_Control
0x18000f18c  cmp     rcx, rdx
0x18000f18f  jz      short loc_18000F1C3
0x18000f191  test    byte ptr [rcx+1Ch], 1
0x18000f195  jz      short loc_18000F1C3
0x18000f197  mov     rcx, [rcx+10h]
0x18000f19b  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f1a2  mov     dword ptr [rsp+0C8h+pbOutput], 1362h
0x18000f1aa  lea     r9, aNteBadData; "NTE_BAD_DATA"
0x18000f1b1  mov     qword ptr [rsp+0C8h+cbIV], rax
0x18000f1b6  mov     dword ptr [rsp+0C8h+pbIV], 80090005h
0x18000f1be  call    WPP_SF_sDsd
0x18000f1c3  mov     eax, 80090005h
0x18000f1c8  jmp     loc_18000F061
0x18000f1cd  mov     r9d, 135Ch
0x18000f1d3  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f1da  lea     rdx, aNteBadData; "NTE_BAD_DATA"
0x18000f1e1  mov     ecx, 80090005h
0x18000f1e6  call    DebugTraceError
0x18000f1eb  mov     eax, 80090005h
0x18000f1f0  jmp     loc_18000F061
0x18000f1f5  cmp     r8, rdx
0x18000f1f8  ja      short loc_18000F20E
0x18000f1fa  mov     eax, r9d
0x18000f1fd  add     rax, r8
0x18000f200  cmp     rdx, rax
0x18000f203  jb      short loc_18000F21B
0x18000f205  cmp     r8, rdx
0x18000f208  jb      loc_18000EF72
0x18000f20e  lea     rax, [rdx+rsi]
0x18000f212  cmp     r8, rax
0x18000f215  jnb     loc_18000EF72
0x18000f21b  mov     r9d, 1348h
0x18000f221  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f228  lea     rdx, aNteBuffersOver; "NTE_BUFFERS_OVERLAP"
0x18000f22f  mov     ecx, 8009002Bh
0x18000f234  call    DebugTraceError
0x18000f239  mov     eax, 8009002Bh
0x18000f23e  jmp     loc_18000F061
0x18000f243  mov     r9d, 1369h
0x18000f249  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f250  lea     rdx, aNteBufferTooSm; "NTE_BUFFER_TOO_SMALL"
0x18000f257  mov     ecx, 80090028h
0x18000f25c  call    DebugTraceError
0x18000f261  mov     eax, 80090028h
0x18000f266  jmp     loc_18000F059
0x18000f26b  mov     r9d, 138Eh
0x18000f271  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f278  lea     rdx, aNteDecryptionF; "NTE_DECRYPTION_FAILURE"
0x18000f27f  mov     ecx, 8009002Ch
0x18000f284  call    DebugTraceError
0x18000f289  mov     eax, 8009002Ch
0x18000f28e  jmp     loc_18000F059
0x18000f293  mov     r9d, 133Fh
0x18000f299  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f2a0  lea     rdx, aNteBadData; "NTE_BAD_DATA"
0x18000f2a7  mov     ecx, 80090005h
0x18000f2ac  call    DebugTraceError
0x18000f2b1  mov     eax, 80090005h
0x18000f2b6  jmp     loc_18000F069
```
