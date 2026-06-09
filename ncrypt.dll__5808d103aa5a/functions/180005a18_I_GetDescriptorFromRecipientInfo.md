# I_GetDescriptorFromRecipientInfo

- ea: `0x180005a18`
- end: `0x180005f7e`
- name: `I_GetDescriptorFromRecipientInfo`
- size: `1382`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800058b0`

## callees

- `0x180005a18`
- `0x180005f90`
- `0x1800090e0`
- `0x18000d02c`
- `0x18000e120`
- `0x180019de4`
- `0x18001d7b8`
- `0x18001f151`
- `0x18001f175`
- `0x18001f1b0`

## import_xrefs

- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x180005b52`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x180005b95`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x180005eb8`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x180005b52`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x180005b95`
- `NTASN1!__imp_RtlAsn1DecodeAndAllocate` at `0x180005eb8`

## string_xrefs

- `0x180005bfc`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x180005c50`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x180005d17`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x180005e4c`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`
- `0x180005f2c`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\descriptor.c`

## pseudocode

```c
__int64 __fastcall I_GetDescriptorFromRecipientInfo(int *a1, _QWORD *a2)
{
  __int64 v4; // rdx
  int v5; // r8d
  void *v6; // rdi
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rcx
  unsigned int v13; // ebx
  int v14; // edx
  int v15; // r8d
  _QWORD *v16; // rcx
  _QWORD *v18; // rcx
  int *v19; // rcx
  unsigned int RecipientIdString; // eax
  const wchar_t *v21; // rdx
  __int64 v22; // rax
  size_t v23; // rdi
  __int64 v24; // rdx
  unsigned int DescriptorFromAndCombiner; // eax
  __int64 v26; // r9
  __int64 v27; // rcx
  __int64 v28; // rdx
  char *v29; // rcx
  __int64 v30; // r9
  char v31; // [rsp+30h] [rbp-D0h]
  char v32; // [rsp+30h] [rbp-D0h]
  void *v33; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v34; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL v36; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v38; // [rsp+68h] [rbp-98h]
  _QWORD v39[3]; // [rsp+70h] [rbp-90h] BYREF
  int v40; // [rsp+88h] [rbp-78h]
  _QWORD v41[32]; // [rsp+90h] [rbp-70h] BYREF

  v37 = 1;
  v34 = 0;
  hMem = 0;
  v39[0] = 0;
  v39[2] = 0;
  v40 = 0;
  memset_0(v41, 0, sizeof(v41));
  *a2 = 0;
  v38 = v39;
  v33 = 0;
  v39[1] = v41;
  v6 = 0;
  v7 = *a1;
  v36 = 0;
  v8 = v7 - 1;
  if ( !v8 || (v9 = v8 - 1) == 0 )
  {
    if ( *a1 == 1 )
    {
      v19 = a1 + 4;
    }
    else
    {
      if ( a1[36] != 1 )
      {
        v26 = 1616;
        goto LABEL_68;
      }
      v19 = (int *)*((_QWORD *)a1 + 19);
    }
    RecipientIdString = I_GetRecipientIdString(v19, v4, &v33);
    v13 = RecipientIdString;
    if ( RecipientIdString )
    {
      v30 = 1630;
      goto LABEL_73;
    }
    v21 = L"CERTIFICATE";
LABEL_51:
    v6 = v33;
    v22 = 4LL * LODWORD(v39[0]);
    ++LODWORD(v39[0]);
    v41[v22] = v21;
    v41[v22 + 1] = v6;
LABEL_15:
    v13 = CNG_DuplicateDescriptor(&v37, a2, 0);
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          v15,
          (unsigned int)"Status",
          v13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
          181);
    }
    else
    {
      v13 = 0;
    }
    goto LABEL_19;
  }
  v10 = v9 - 1;
  if ( v10 )
  {
    if ( v10 != 2 )
    {
      v13 = -2146893783;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return v13;
      v32 = -88;
      goto LABEL_38;
    }
    if ( a1[2] != 12 )
      goto LABEL_75;
    v23 = (unsigned int)a1[2];
    if ( !memcmp_0(*((const void **)a1 + 2), &qword_180023328, v23) )
    {
      DescriptorFromAndCombiner = I_GetDescriptorFromAndCombiner(a1, v24, a2);
      v13 = DescriptorFromAndCombiner;
      if ( !DescriptorFromAndCombiner )
        goto LABEL_25;
      v26 = 1528;
      goto LABEL_57;
    }
    if ( !memcmp_0(*((const void **)a1 + 2), g_rgbObjDraCert, v23) )
    {
      DescriptorFromAndCombiner = RtlAsn1DecodeAndAllocate(
                                    ASN1_NCRYPT_MODULE_HANDLE,
                                    22,
                                    0x200000,
                                    *((_QWORD *)a1 + 4),
                                    (unsigned int)a1[6],
                                    0,
                                    &NCryptDefaultAllocPara,
                                    &v36);
      v13 = DescriptorFromAndCombiner;
      if ( DescriptorFromAndCombiner )
      {
        v26 = 1553;
LABEL_57:
        v27 = DescriptorFromAndCombiner;
LABEL_59:
        DebugTraceError(
          v27,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
          v26);
        goto LABEL_25;
      }
      if ( *(_DWORD *)v36 == 1 )
      {
        v29 = (char *)v36 + 16;
LABEL_70:
        RecipientIdString = I_GetRecipientIdString(v29, v28, &v33);
        v13 = RecipientIdString;
        if ( RecipientIdString )
        {
          v30 = 1586;
LABEL_73:
          DebugTraceError(
            RecipientIdString,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
            v30);
          v6 = v33;
LABEL_19:
          if ( v6 )
            I_DefaultExtrenalFree(v6);
          goto LABEL_25;
        }
        v21 = L"DRACERTIFICATE";
        goto LABEL_51;
      }
      if ( *(_DWORD *)v36 != 2 )
      {
        v13 = -2146893819;
        v26 = 1575;
        v27 = 2148073477LL;
        goto LABEL_59;
      }
      if ( *((_DWORD *)v36 + 36) == 1 )
      {
        v29 = (char *)*((_QWORD *)v36 + 19);
        goto LABEL_70;
      }
      v26 = 1566;
    }
    else
    {
LABEL_75:
      v26 = 1597;
    }
LABEL_68:
    v13 = -2146893783;
    v27 = 2148073513LL;
    goto LABEL_59;
  }
  v11 = *((_QWORD *)a1 + 5);
  if ( !v11 || *(_DWORD *)v11 != 11 )
    goto LABEL_35;
  v4 = *(_QWORD *)(v11 + 8);
  v12 = *(_QWORD *)v4 + 0x7DFEFBFEF9D4F6FALL;
  if ( *(_QWORD *)v4 == 0x82010401062B0906uLL )
  {
    v12 = *(unsigned __int16 *)(v4 + 8) - 18999LL;
    if ( *(_WORD *)(v4 + 8) == 18999 )
      v12 = *(unsigned __int8 *)(v4 + 10) - 1LL;
  }
  if ( v12 )
  {
LABEL_35:
    v13 = -2146893783;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v13;
    v32 = 112;
    goto LABEL_38;
  }
  v13 = RtlAsn1DecodeAndAllocate(
          ASN1_NCRYPT_MODULE_HANDLE,
          1,
          2097153,
          *(_QWORD *)(v11 + 24),
          *(unsigned int *)(v11 + 16),
          0,
          &NCryptDefaultAllocPara,
          &v34);
  if ( v13 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_25;
    v31 = -124;
LABEL_24:
    WPP_SF_sDsd(
      v16[2],
      v4,
      v5,
      (unsigned int)"Status",
      v13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
      v31);
    goto LABEL_25;
  }
  v13 = RtlAsn1DecodeAndAllocate(
          ASN1_NCRYPT_MODULE_HANDLE,
          28,
          1,
          *((_QWORD *)v34 + 3),
          *((unsigned int *)v34 + 4),
          0,
          &NCryptDefaultAllocPara,
          &hMem);
  if ( v13 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_25;
    v31 = -108;
    goto LABEL_24;
  }
  if ( *(_DWORD *)hMem == 1 && **((_DWORD **)hMem + 1) == 1 )
  {
    v38 = (_QWORD *)*((_QWORD *)hMem + 1);
    goto LABEL_15;
  }
  v13 = -2146893783;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v32 = -100;
LABEL_38:
    WPP_SF_sDsd(
      v18[2],
      v4,
      v5,
      (unsigned int)"Status",
      41,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\descriptor.c",
      v32);
  }
LABEL_25:
  if ( v34 )
    I_DefaultExtrenalFree(v34);
  if ( hMem )
    I_DefaultExtrenalFree(hMem);
  if ( v36 )
    I_DefaultExtrenalFree(v36);
  return v13;
}

```

## disassembly

```asm
0x180005a18  mov     [rsp-8+arg_10], rbx
0x180005a1d  mov     [rsp-8+arg_18], rsi
0x180005a22  push    rbp
0x180005a23  push    rdi
0x180005a24  push    r12
0x180005a26  push    r14
0x180005a28  push    r15
0x180005a2a  lea     rbp, [rsp-0A0h]
0x180005a32  sub     rsp, 1A0h
0x180005a39  mov     rax, cs:__security_cookie
0x180005a40  xor     rax, rsp
0x180005a43  mov     [rbp+0C0h+var_30], rax
0x180005a4a  xor     r15d, r15d
0x180005a4d  mov     [rsp+1C0h+var_160], 1
0x180005a56  mov     r14, rdx
0x180005a59  mov     [rsp+1C0h+var_178], r15
0x180005a5e  mov     rbx, rcx
0x180005a61  mov     [rsp+1C0h+hMem], r15
0x180005a66  xor     edx, edx; Val
0x180005a68  mov     [rsp+1C0h+var_150], r15
0x180005a6d  lea     rcx, [rbp+0C0h+var_130]; void *
0x180005a71  mov     [rbp+0C0h+var_140], r15
0x180005a75  mov     r8d, 100h; Size
0x180005a7b  mov     [rbp+0C0h+var_138], r15d
0x180005a7f  call    memset_0
0x180005a84  lea     rax, [rsp+1C0h+var_150]
0x180005a89  mov     [r14], r15
0x180005a8c  mov     [rsp+1C0h+var_158], rax
0x180005a91  lea     r12d, [r15+1]
0x180005a95  lea     rax, [rbp+0C0h+var_130]
0x180005a99  mov     [rsp+1C0h+var_180], r15
0x180005a9e  mov     [rsp+1C0h+var_148], rax
0x180005aa3  mov     edi, r15d
0x180005aa6  mov     eax, [rbx]
0x180005aa8  mov     [rsp+1C0h+var_168], r15
0x180005aad  sub     eax, r12d
0x180005ab0  jz      loc_180005DA4
0x180005ab6  sub     eax, r12d
0x180005ab9  jz      loc_180005DA4
0x180005abf  sub     eax, r12d
0x180005ac2  jnz     loc_180005D30
0x180005ac8  mov     r9, [rbx+28h]
0x180005acc  test    r9, r9
0x180005acf  jz      loc_180005CF1
0x180005ad5  cmp     dword ptr [r9], 0Bh
0x180005ad9  jnz     loc_180005CF1
0x180005adf  mov     rdx, [r9+8]
0x180005ae3  mov     rax, 82010401062B0906h
0x180005aed  mov     rcx, [rdx]
0x180005af0  sub     rcx, rax
0x180005af3  jnz     short loc_180005B11
0x180005af5  movzx   ecx, word ptr [rdx+8]
0x180005af9  mov     eax, 4A37h
0x180005afe  movzx   eax, ax
0x180005b01  sub     rcx, rax
0x180005b04  jnz     short loc_180005B11
0x180005b06  movzx   ecx, byte ptr [rdx+0Ah]
0x180005b0a  movzx   eax, r12b
0x180005b0e  sub     rcx, rax
0x180005b11  test    rcx, rcx
0x180005b14  jnz     loc_180005CF1
0x180005b1a  mov     eax, [r9+10h]
0x180005b1e  lea     rcx, [rsp+1C0h+var_178]
0x180005b23  mov     r9, [r9+18h]
0x180005b27  lea     rsi, NCryptDefaultAllocPara
0x180005b2e  mov     [rsp+1C0h+var_188], rcx
0x180005b33  mov     r8d, 200001h
0x180005b39  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x180005b40  mov     edx, r12d
0x180005b43  mov     [rsp+1C0h+var_190], rsi
0x180005b48  mov     [rsp+1C0h+var_198], r15
0x180005b4d  mov     [rsp+1C0h+var_1A0], rax
0x180005b52  call    cs:__imp_RtlAsn1DecodeAndAllocate
0x180005b58  mov     ebx, eax
0x180005b5a  test    eax, eax
0x180005b5c  jnz     loc_180005C2F
0x180005b62  mov     r9, [rsp+1C0h+var_178]
0x180005b67  lea     rcx, [rsp+1C0h+hMem]
0x180005b6c  mov     [rsp+1C0h+var_188], rcx
0x180005b71  lea     edx, [rbx+1Ch]
0x180005b74  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x180005b7b  mov     r8d, r12d
0x180005b7e  mov     [rsp+1C0h+var_190], rsi
0x180005b83  mov     eax, [r9+10h]
0x180005b87  mov     r9, [r9+18h]
0x180005b8b  mov     [rsp+1C0h+var_198], r15
0x180005b90  mov     [rsp+1C0h+var_1A0], rax
0x180005b95  call    cs:__imp_RtlAsn1DecodeAndAllocate
0x180005b9b  mov     ebx, eax
0x180005b9d  test    eax, eax
0x180005b9f  jnz     loc_180005CCB
0x180005ba5  mov     rcx, [rsp+1C0h+hMem]
0x180005baa  cmp     [rcx], r12d
0x180005bad  jnz     loc_180005D71
0x180005bb3  mov     rax, [rcx+8]
0x180005bb7  cmp     [rax], r12d
0x180005bba  jnz     loc_180005D71
0x180005bc0  mov     [rsp+1C0h+var_158], rax
0x180005bc5  xor     r8d, r8d
0x180005bc8  lea     rcx, [rsp+1C0h+var_160]
0x180005bcd  mov     rdx, r14
0x180005bd0  call    CNG_DuplicateDescriptor
0x180005bd5  mov     ebx, eax
0x180005bd7  test    eax, eax
0x180005bd9  jz      loc_180005D69
0x180005bdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180005be6  lea     rax, WPP_GLOBAL_Control
0x180005bed  cmp     rcx, rax
0x180005bf0  jz      short loc_180005C20
0x180005bf2  test    [rcx+1Ch], r12b
0x180005bf6  jz      short loc_180005C20
0x180005bf8  mov     rcx, [rcx+10h]
0x180005bfc  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005c03  mov     dword ptr [rsp+1C0h+var_190], 6B5h
0x180005c0b  lea     r9, aStatus; "Status"
0x180005c12  mov     [rsp+1C0h+var_198], rax
0x180005c17  mov     dword ptr [rsp+1C0h+var_1A0], ebx
0x180005c1b  call    WPP_SF_sDsd
0x180005c20  test    rdi, rdi
0x180005c23  jz      short loc_180005C70
0x180005c25  mov     rcx, rdi; hMem
0x180005c28  call    I_DefaultExtrenalFree
0x180005c2d  jmp     short loc_180005C70
0x180005c2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c36  lea     rax, WPP_GLOBAL_Control
0x180005c3d  cmp     rcx, rax
0x180005c40  jz      short loc_180005C70
0x180005c42  test    [rcx+1Ch], r12b
0x180005c46  jz      short loc_180005C70
0x180005c48  mov     dword ptr [rsp+1C0h+var_190], 684h
0x180005c50  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005c57  mov     [rsp+1C0h+var_198], rax
0x180005c5c  mov     dword ptr [rsp+1C0h+var_1A0], ebx
0x180005c60  mov     rcx, [rcx+10h]
0x180005c64  lea     r9, aStatus; "Status"
0x180005c6b  call    WPP_SF_sDsd
0x180005c70  mov     rcx, [rsp+1C0h+var_178]; hMem
0x180005c75  test    rcx, rcx
0x180005c78  jnz     short loc_180005CC4
0x180005c7a  mov     rcx, [rsp+1C0h+hMem]; hMem
0x180005c7f  test    rcx, rcx
0x180005c82  jz      short loc_180005C89
0x180005c84  call    I_DefaultExtrenalFree
0x180005c89  mov     rcx, [rsp+1C0h+var_168]; hMem
0x180005c8e  test    rcx, rcx
0x180005c91  jnz     loc_180005F74
0x180005c97  mov     eax, ebx
0x180005c99  mov     rcx, [rbp+0C0h+var_30]
0x180005ca0  xor     rcx, rsp; StackCookie
0x180005ca3  call    __security_check_cookie
0x180005ca8  lea     r11, [rsp+1C0h+var_20]
0x180005cb0  mov     rbx, [r11+40h]
0x180005cb4  mov     rsi, [r11+48h]
0x180005cb8  mov     rsp, r11
0x180005cbb  pop     r15
0x180005cbd  pop     r14
0x180005cbf  pop     r12
0x180005cc1  pop     rdi
0x180005cc2  pop     rbp
0x180005cc3  retn
0x180005cc4  call    I_DefaultExtrenalFree
0x180005cc9  jmp     short loc_180005C7A
0x180005ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cd2  lea     rax, WPP_GLOBAL_Control
0x180005cd9  cmp     rcx, rax
0x180005cdc  jz      short loc_180005C70
0x180005cde  test    [rcx+1Ch], r12b
0x180005ce2  jz      short loc_180005C70
0x180005ce4  mov     dword ptr [rsp+1C0h+var_190], 694h
0x180005cec  jmp     loc_180005C50
0x180005cf1  mov     ebx, 80090029h
0x180005cf6  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cfd  lea     rax, WPP_GLOBAL_Control
0x180005d04  cmp     rcx, rax
0x180005d07  jz      short loc_180005C97
0x180005d09  test    [rcx+1Ch], r12b
0x180005d0d  jz      short loc_180005C97
0x180005d0f  mov     dword ptr [rsp+1C0h+var_190], 670h
0x180005d17  lea     rax, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005d1e  mov     [rsp+1C0h+var_198], rax
0x180005d23  mov     dword ptr [rsp+1C0h+var_1A0], 80090029h
0x180005d2b  jmp     loc_180005C60
0x180005d30  cmp     eax, 2
0x180005d33  jz      loc_180005DF1
0x180005d39  mov     ebx, 80090029h
0x180005d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d45  lea     rax, WPP_GLOBAL_Control
0x180005d4c  cmp     rcx, rax
0x180005d4f  jz      loc_180005C97
0x180005d55  test    [rcx+1Ch], r12b
0x180005d59  jz      loc_180005C97
0x180005d5f  mov     dword ptr [rsp+1C0h+var_190], 6A8h
0x180005d67  jmp     short loc_180005D17
0x180005d69  mov     ebx, r15d
0x180005d6c  jmp     loc_180005C20
0x180005d71  mov     ebx, 80090029h
0x180005d76  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d7d  lea     rax, WPP_GLOBAL_Control
0x180005d84  cmp     rcx, rax
0x180005d87  jz      loc_180005C70
0x180005d8d  test    [rcx+1Ch], r12b
0x180005d91  jz      loc_180005C70
0x180005d97  mov     dword ptr [rsp+1C0h+var_190], 69Ch
0x180005d9f  jmp     loc_180005D17
0x180005da4  cmp     [rbx], r12d
0x180005da7  jnz     loc_180005F5F
0x180005dad  lea     rcx, [rbx+10h]
0x180005db1  lea     r8, [rsp+1C0h+var_180]
0x180005db6  call    I_GetRecipientIdString
0x180005dbb  mov     ebx, eax
0x180005dbd  test    eax, eax
0x180005dbf  jnz     loc_180005F26
0x180005dc5  lea     rdx, aCertificate; "CERTIFICATE"
0x180005dcc  mov     ecx, dword ptr [rsp+1C0h+var_150]
0x180005dd0  mov     rdi, [rsp+1C0h+var_180]
0x180005dd5  mov     eax, ecx
0x180005dd7  shl     rax, 5
0x180005ddb  add     ecx, r12d
0x180005dde  mov     dword ptr [rsp+1C0h+var_150], ecx
0x180005de2  mov     [rbp+rax+0C0h+var_130], rdx
0x180005de7  mov     [rbp+rax+0C0h+var_128], rdi
0x180005dec  jmp     loc_180005BC5
0x180005df1  cmp     dword ptr [rbx+8], 0Ch
0x180005df5  jnz     loc_180005F57
0x180005dfb  mov     edi, [rbx+8]
0x180005dfe  lea     rdx, qword_180023328; Buf2
0x180005e05  mov     rcx, [rbx+10h]; Buf1
0x180005e09  mov     r8d, edi; Size
0x180005e0c  call    memcmp_0
0x180005e11  test    eax, eax
0x180005e13  jnz     short loc_180005E64
0x180005e15  mov     r8, r14
0x180005e18  mov     rcx, rbx
0x180005e1b  call    I_GetDescriptorFromAndCombiner
0x180005e20  mov     ebx, eax
0x180005e22  test    eax, eax
0x180005e24  jz      loc_180005C70
0x180005e2a  mov     r9d, 5F8h
0x180005e30  jmp     short loc_180005E38
0x180005e32  mov     r9d, 611h
0x180005e38  mov     ecx, eax
0x180005e3a  jmp     short loc_180005E4C
0x180005e3c  mov     ebx, 80090005h
0x180005e41  mov     r9d, 627h
0x180005e47  mov     ecx, 80090005h
0x180005e4c  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005e53  lea     rdx, aStatus; "Status"
0x180005e5a  call    DebugTraceError
0x180005e5f  jmp     loc_180005C70
0x180005e64  mov     rcx, [rbx+10h]; Buf1
0x180005e68  lea     rdx, g_rgbObjDraCert; Buf2
0x180005e6f  mov     r8, rdi; Size
0x180005e72  call    memcmp_0
0x180005e77  test    eax, eax
0x180005e79  jnz     loc_180005F57
0x180005e7f  mov     eax, [rbx+18h]
0x180005e82  lea     rcx, [rsp+1C0h+var_168]
0x180005e87  mov     r9, [rbx+20h]
0x180005e8b  lea     rsi, NCryptDefaultAllocPara
0x180005e92  mov     [rsp+1C0h+var_188], rcx
0x180005e97  mov     edx, 16h
0x180005e9c  mov     rcx, cs:ASN1_NCRYPT_MODULE_HANDLE
0x180005ea3  mov     r8d, 200000h
0x180005ea9  mov     [rsp+1C0h+var_190], rsi
0x180005eae  mov     [rsp+1C0h+var_198], r15
0x180005eb3  mov     [rsp+1C0h+var_1A0], rax
0x180005eb8  call    cs:__imp_RtlAsn1DecodeAndAllocate
0x180005ebe  mov     ebx, eax
0x180005ec0  test    eax, eax
0x180005ec2  jnz     loc_180005E32
0x180005ec8  mov     rax, [rsp+1C0h+var_168]
0x180005ecd  cmp     [rax], r12d
0x180005ed0  jnz     short loc_180005ED8
0x180005ed2  lea     rcx, [rax+10h]
0x180005ed6  jmp     short loc_180005F0E
0x180005ed8  cmp     dword ptr [rax], 2
0x180005edb  jnz     loc_180005E3C
0x180005ee1  cmp     [rax+90h], r12d
0x180005ee8  jz      short loc_180005F07
0x180005eea  mov     r9d, 61Eh
0x180005ef0  jmp     short loc_180005EF8
0x180005ef2  mov     r9d, 650h
0x180005ef8  mov     ebx, 80090029h
0x180005efd  mov     ecx, 80090029h
0x180005f02  jmp     loc_180005E4C
0x180005f07  mov     rcx, [rax+98h]
0x180005f0e  lea     r8, [rsp+1C0h+var_180]
0x180005f13  call    I_GetRecipientIdString
0x180005f18  mov     ebx, eax
0x180005f1a  test    eax, eax
0x180005f1c  jz      short loc_180005F4B
0x180005f1e  mov     r9d, 632h
0x180005f24  jmp     short loc_180005F2C
0x180005f26  mov     r9d, 65Eh
0x180005f2c  lea     r8, aOnecoreDsSecur_11; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180005f33  mov     ecx, eax
0x180005f35  lea     rdx, aStatus; "Status"
0x180005f3c  call    DebugTraceError
0x180005f41  mov     rdi, [rsp+1C0h+var_180]
0x180005f46  jmp     loc_180005C20
  ... truncated ...
```
