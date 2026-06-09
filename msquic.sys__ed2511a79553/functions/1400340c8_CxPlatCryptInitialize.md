# CxPlatCryptInitialize

- ea: `0x1400340c8`
- end: `0x140034473`
- name: `CxPlatCryptInitialize`
- size: `939`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140063008`

## callees

- `0x1400340c8`
- `0x14003e928`

## import_xrefs

- `cng!BCryptSetProperty` at `0x140034204`
- `cng!BCryptSetProperty` at `0x140034279`
- `cng!BCryptSetProperty` at `0x140034444`
- `cng!BCryptSetProperty` at `0x140034204`
- `cng!BCryptSetProperty` at `0x140034279`
- `cng!BCryptSetProperty` at `0x140034444`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400340f7`
- `cng!BCryptOpenAlgorithmProvider` at `0x140034136`
- `cng!BCryptOpenAlgorithmProvider` at `0x140034175`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400341b9`
- `cng!BCryptOpenAlgorithmProvider` at `0x140034243`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400342b5`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400342f5`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400340f7`
- `cng!BCryptOpenAlgorithmProvider` at `0x140034136`
- `cng!BCryptOpenAlgorithmProvider` at `0x140034175`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400341b9`
- `cng!BCryptOpenAlgorithmProvider` at `0x140034243`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400342b5`
- `cng!BCryptOpenAlgorithmProvider` at `0x1400342f5`
- `cng!BCryptCloseAlgorithmProvider` at `0x140034331`
- `cng!BCryptCloseAlgorithmProvider` at `0x140034353`
- `cng!BCryptCloseAlgorithmProvider` at `0x140034375`
- `cng!BCryptCloseAlgorithmProvider` at `0x140034397`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400343b9`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400343db`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400343fd`
- `cng!BCryptCloseAlgorithmProvider` at `0x140034331`
- `cng!BCryptCloseAlgorithmProvider` at `0x140034353`
- `cng!BCryptCloseAlgorithmProvider` at `0x140034375`
- `cng!BCryptCloseAlgorithmProvider` at `0x140034397`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400343b9`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400343db`
- `cng!BCryptCloseAlgorithmProvider` at `0x1400343fd`

## string_xrefs

- `0x140034116`: `Open HMAC_SHA256 algorithm`
- `0x140034155`: `Open HMAC_SHA384 algorithm`
- `0x140034194`: `Open HMAC_SHA512 algorithm`
- `0x1400341d8`: `Open AES algorithm`
- `0x1400342d2`: `Open ChaCha20-Poly1305 algorithm`
- `0x140034314`: `Open SP800-108 CTR HMAC KDF algorithm`

## pseudocode

```c
__int64 CxPlatCryptInitialize()
{
  NTSTATUS v0; // eax
  __int64 v1; // rdx
  __int64 v2; // rcx
  unsigned int v3; // ebx
  const char *v4; // r9
  NTSTATUS v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx

  v0 = BCryptOpenAlgorithmProvider(&CXPLAT_HMAC_SHA256_ALG_HANDLE, L"SHA256", L"Microsoft Primitive Provider", 9u);
  v3 = v0;
  if ( v0 >= 0 )
  {
    v0 = BCryptOpenAlgorithmProvider(&CXPLAT_HMAC_SHA384_ALG_HANDLE, L"SHA384", L"Microsoft Primitive Provider", 9u);
    v3 = v0;
    if ( v0 >= 0 )
    {
      v0 = BCryptOpenAlgorithmProvider(&CXPLAT_HMAC_SHA512_ALG_HANDLE, L"SHA512", L"Microsoft Primitive Provider", 9u);
      v3 = v0;
      if ( v0 >= 0 )
      {
        v0 = BCryptOpenAlgorithmProvider(&CXPLAT_AES_ECB_ALG_HANDLE, L"AES", L"Microsoft Primitive Provider", 1u);
        v3 = v0;
        if ( v0 >= 0 )
        {
          v0 = BCryptSetProperty(CXPLAT_AES_ECB_ALG_HANDLE, L"ChainingMode", (PUCHAR)L"ChainingModeECB", 0x20u, 0);
          v3 = v0;
          if ( v0 < 0 )
          {
            if ( (Microsoft_QuicEnableBits & 4) != 0 )
            {
              v4 = "Set ECB chaining mode";
              goto LABEL_26;
            }
            goto LABEL_27;
          }
          v0 = BCryptOpenAlgorithmProvider(&CXPLAT_AES_GCM_ALG_HANDLE, L"AES", L"Microsoft Primitive Provider", 1u);
          v3 = v0;
          if ( v0 >= 0 )
          {
            v0 = BCryptSetProperty(CXPLAT_AES_GCM_ALG_HANDLE, L"ChainingMode", (PUCHAR)L"ChainingModeGCM", 0x20u, 0);
            v3 = v0;
            if ( v0 >= 0 )
            {
              v5 = BCryptOpenAlgorithmProvider(
                     &CXPLAT_CHACHA20_POLY1305_ALG_HANDLE,
                     L"CHACHA20_POLY1305",
                     L"Microsoft Primitive Provider",
                     1u);
              if ( v5 >= 0 )
              {
                v0 = BCryptSetProperty(
                       CXPLAT_CHACHA20_POLY1305_ALG_HANDLE,
                       L"ChainingMode",
                       (PUCHAR)L"ChainingModeN/A",
                       0x20u,
                       0);
                v3 = v0;
                if ( v0 < 0 )
                {
                  if ( (Microsoft_QuicEnableBits & 4) == 0 )
                    goto LABEL_27;
                  v4 = "Set ChaCha20-Poly1305 chaining mode";
                  goto LABEL_26;
                }
              }
              else if ( (Microsoft_QuicEnableBits & 4) != 0 )
              {
                McTemplateU0qs_EtwWriteTransfer(v7, v6, (unsigned int)v5, "Open ChaCha20-Poly1305 algorithm");
              }
              v0 = BCryptOpenAlgorithmProvider(
                     &CXPLAT_SP800108_CTR_HMAC_ALG_HANDLE,
                     L"SP800_108_CTR_HMAC",
                     L"Microsoft Primitive Provider",
                     1u);
              v3 = v0;
              if ( v0 >= 0 )
                return v3;
              if ( (Microsoft_QuicEnableBits & 4) != 0 )
              {
                v4 = "Open SP800-108 CTR HMAC KDF algorithm";
                goto LABEL_26;
              }
            }
            else if ( (Microsoft_QuicEnableBits & 4) != 0 )
            {
              v4 = "Set GCM chaining mode";
              goto LABEL_26;
            }
            goto LABEL_27;
          }
        }
        if ( (Microsoft_QuicEnableBits & 4) != 0 )
        {
          v4 = "Open AES algorithm";
          goto LABEL_26;
        }
      }
      else if ( (Microsoft_QuicEnableBits & 4) != 0 )
      {
        v4 = "Open HMAC_SHA512 algorithm";
        goto LABEL_26;
      }
    }
    else if ( (Microsoft_QuicEnableBits & 4) != 0 )
    {
      v4 = "Open HMAC_SHA384 algorithm";
      goto LABEL_26;
    }
  }
  else if ( (Microsoft_QuicEnableBits & 4) != 0 )
  {
    v4 = "Open HMAC_SHA256 algorithm";
LABEL_26:
    McTemplateU0qs_EtwWriteTransfer(v2, v1, (unsigned int)v0, v4);
  }
LABEL_27:
  if ( CXPLAT_HMAC_SHA256_ALG_HANDLE )
  {
    BCryptCloseAlgorithmProvider(CXPLAT_HMAC_SHA256_ALG_HANDLE, 0);
    CXPLAT_HMAC_SHA256_ALG_HANDLE = 0;
  }
  if ( CXPLAT_HMAC_SHA384_ALG_HANDLE )
  {
    BCryptCloseAlgorithmProvider(CXPLAT_HMAC_SHA384_ALG_HANDLE, 0);
    CXPLAT_HMAC_SHA384_ALG_HANDLE = 0;
  }
  if ( CXPLAT_HMAC_SHA512_ALG_HANDLE )
  {
    BCryptCloseAlgorithmProvider(CXPLAT_HMAC_SHA512_ALG_HANDLE, 0);
    CXPLAT_HMAC_SHA512_ALG_HANDLE = 0;
  }
  if ( CXPLAT_AES_ECB_ALG_HANDLE )
  {
    BCryptCloseAlgorithmProvider(CXPLAT_AES_ECB_ALG_HANDLE, 0);
    CXPLAT_AES_ECB_ALG_HANDLE = 0;
  }
  if ( CXPLAT_AES_GCM_ALG_HANDLE )
  {
    BCryptCloseAlgorithmProvider(CXPLAT_AES_GCM_ALG_HANDLE, 0);
    CXPLAT_AES_GCM_ALG_HANDLE = 0;
  }
  if ( CXPLAT_CHACHA20_POLY1305_ALG_HANDLE )
  {
    BCryptCloseAlgorithmProvider(CXPLAT_CHACHA20_POLY1305_ALG_HANDLE, 0);
    CXPLAT_CHACHA20_POLY1305_ALG_HANDLE = 0;
  }
  if ( CXPLAT_SP800108_CTR_HMAC_ALG_HANDLE )
  {
    BCryptCloseAlgorithmProvider(CXPLAT_SP800108_CTR_HMAC_ALG_HANDLE, 0);
    CXPLAT_SP800108_CTR_HMAC_ALG_HANDLE = 0;
  }
  return v3;
}

```

## disassembly

```asm
0x1400340c8  mov     [rsp+arg_0], rbx
0x1400340cd  mov     [rsp+arg_8], rbp
0x1400340d2  push    rsi
0x1400340d3  sub     rsp, 30h
0x1400340d7  mov     ebp, 9
0x1400340dc  lea     rsi, pszImplementation; "Microsoft Primitive Provider"
0x1400340e3  mov     r9d, ebp; dwFlags
0x1400340e6  lea     rdx, pszAlgId; "SHA256"
0x1400340ed  mov     r8, rsi; pszImplementation
0x1400340f0  lea     rcx, CXPLAT_HMAC_SHA256_ALG_HANDLE; phAlgorithm
0x1400340f7  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400340fe  nop     dword ptr [rax+rax+00h]
0x140034103  mov     ebx, eax
0x140034105  test    eax, eax
0x140034107  jns     short loc_140034122
0x140034109  test    cs:Microsoft_QuicEnableBits, 4
0x140034110  jz      loc_140034323
0x140034116  lea     r9, aOpenHmacSha256; "Open HMAC_SHA256 algorithm"
0x14003411d  jmp     loc_14003431B
0x140034122  mov     r9d, ebp; dwFlags
0x140034125  lea     rdx, aSha384; "SHA384"
0x14003412c  mov     r8, rsi; pszImplementation
0x14003412f  lea     rcx, CXPLAT_HMAC_SHA384_ALG_HANDLE; phAlgorithm
0x140034136  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14003413d  nop     dword ptr [rax+rax+00h]
0x140034142  mov     ebx, eax
0x140034144  test    eax, eax
0x140034146  jns     short loc_140034161
0x140034148  test    cs:Microsoft_QuicEnableBits, 4
0x14003414f  jz      loc_140034323
0x140034155  lea     r9, aOpenHmacSha384; "Open HMAC_SHA384 algorithm"
0x14003415c  jmp     loc_14003431B
0x140034161  mov     r9d, ebp; dwFlags
0x140034164  lea     rdx, aSha512; "SHA512"
0x14003416b  mov     r8, rsi; pszImplementation
0x14003416e  lea     rcx, CXPLAT_HMAC_SHA512_ALG_HANDLE; phAlgorithm
0x140034175  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14003417c  nop     dword ptr [rax+rax+00h]
0x140034181  mov     ebx, eax
0x140034183  test    eax, eax
0x140034185  jns     short loc_1400341A0
0x140034187  test    cs:Microsoft_QuicEnableBits, 4
0x14003418e  jz      loc_140034323
0x140034194  lea     r9, aOpenHmacSha512; "Open HMAC_SHA512 algorithm"
0x14003419b  jmp     loc_14003431B
0x1400341a0  mov     ebp, 1
0x1400341a5  lea     rdx, Str2; "AES"
0x1400341ac  mov     r9d, ebp; dwFlags
0x1400341af  lea     rcx, CXPLAT_AES_ECB_ALG_HANDLE; phAlgorithm
0x1400341b6  mov     r8, rsi; pszImplementation
0x1400341b9  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400341c0  nop     dword ptr [rax+rax+00h]
0x1400341c5  mov     ebx, eax
0x1400341c7  test    eax, eax
0x1400341c9  jns     short loc_1400341E4
0x1400341cb  test    cs:Microsoft_QuicEnableBits, 4
0x1400341d2  jz      loc_140034323
0x1400341d8  lea     r9, aOpenAesAlgorit; "Open AES algorithm"
0x1400341df  jmp     loc_14003431B
0x1400341e4  mov     rcx, cs:CXPLAT_AES_ECB_ALG_HANDLE; hObject
0x1400341eb  lea     r8, pbInput; "ChainingModeECB"
0x1400341f2  and     [rsp+38h+var_18], 0
0x1400341f7  lea     rdx, pszProperty; "ChainingMode"
0x1400341fe  mov     r9d, 20h ; ' '; cbInput
0x140034204  call    cs:__imp_BCryptSetProperty
0x14003420b  nop     dword ptr [rax+rax+00h]
0x140034210  mov     ebx, eax
0x140034212  test    eax, eax
0x140034214  jns     short loc_14003422F
0x140034216  test    cs:Microsoft_QuicEnableBits, 4
0x14003421d  jz      loc_140034323
0x140034223  lea     r9, aSetEcbChaining; "Set ECB chaining mode"
0x14003422a  jmp     loc_14003431B
0x14003422f  mov     r9d, ebp; dwFlags
0x140034232  lea     rdx, Str2; "AES"
0x140034239  mov     r8, rsi; pszImplementation
0x14003423c  lea     rcx, CXPLAT_AES_GCM_ALG_HANDLE; phAlgorithm
0x140034243  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14003424a  nop     dword ptr [rax+rax+00h]
0x14003424f  mov     ebx, eax
0x140034251  test    eax, eax
0x140034253  js      loc_1400341CB
0x140034259  mov     rcx, cs:CXPLAT_AES_GCM_ALG_HANDLE; hObject
0x140034260  lea     r8, aChainingmodegc; "ChainingModeGCM"
0x140034267  and     [rsp+38h+var_18], 0
0x14003426c  lea     rdx, pszProperty; "ChainingMode"
0x140034273  mov     r9d, 20h ; ' '; cbInput
0x140034279  call    cs:__imp_BCryptSetProperty
0x140034280  nop     dword ptr [rax+rax+00h]
0x140034285  mov     ebx, eax
0x140034287  test    eax, eax
0x140034289  jns     short loc_1400342A1
0x14003428b  test    cs:Microsoft_QuicEnableBits, 4
0x140034292  jz      loc_140034323
0x140034298  lea     r9, aSetGcmChaining; "Set GCM chaining mode"
0x14003429f  jmp     short loc_14003431B
0x1400342a1  mov     r9d, ebp; dwFlags
0x1400342a4  lea     rdx, aChacha20Poly13; "CHACHA20_POLY1305"
0x1400342ab  mov     r8, rsi; pszImplementation
0x1400342ae  lea     rcx, CXPLAT_CHACHA20_POLY1305_ALG_HANDLE; phAlgorithm
0x1400342b5  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400342bc  nop     dword ptr [rax+rax+00h]
0x1400342c1  test    eax, eax
0x1400342c3  jns     loc_140034424
0x1400342c9  test    cs:Microsoft_QuicEnableBits, 4
0x1400342d0  jz      short loc_1400342E1
0x1400342d2  lea     r9, aOpenChacha20Po; "Open ChaCha20-Poly1305 algorithm"
0x1400342d9  mov     r8d, eax
0x1400342dc  call    McTemplateU0qs_EtwWriteTransfer
0x1400342e1  mov     r9d, ebp; dwFlags
0x1400342e4  lea     rdx, aSp800108CtrHma; "SP800_108_CTR_HMAC"
0x1400342eb  mov     r8, rsi; pszImplementation
0x1400342ee  lea     rcx, CXPLAT_SP800108_CTR_HMAC_ALG_HANDLE; phAlgorithm
0x1400342f5  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1400342fc  nop     dword ptr [rax+rax+00h]
0x140034301  mov     ebx, eax
0x140034303  test    eax, eax
0x140034305  jns     loc_140034411
0x14003430b  test    cs:Microsoft_QuicEnableBits, 4
0x140034312  jz      short loc_140034323
0x140034314  lea     r9, aOpenSp800108Ct; "Open SP800-108 CTR HMAC KDF algorithm"
0x14003431b  mov     r8d, eax
0x14003431e  call    McTemplateU0qs_EtwWriteTransfer
0x140034323  mov     rcx, cs:CXPLAT_HMAC_SHA256_ALG_HANDLE; hAlgorithm
0x14003432a  test    rcx, rcx
0x14003432d  jz      short loc_140034345
0x14003432f  xor     edx, edx; dwFlags
0x140034331  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140034338  nop     dword ptr [rax+rax+00h]
0x14003433d  and     cs:CXPLAT_HMAC_SHA256_ALG_HANDLE, 0
0x140034345  mov     rcx, cs:CXPLAT_HMAC_SHA384_ALG_HANDLE; hAlgorithm
0x14003434c  test    rcx, rcx
0x14003434f  jz      short loc_140034367
0x140034351  xor     edx, edx; dwFlags
0x140034353  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14003435a  nop     dword ptr [rax+rax+00h]
0x14003435f  and     cs:CXPLAT_HMAC_SHA384_ALG_HANDLE, 0
0x140034367  mov     rcx, cs:CXPLAT_HMAC_SHA512_ALG_HANDLE; hAlgorithm
0x14003436e  test    rcx, rcx
0x140034371  jz      short loc_140034389
0x140034373  xor     edx, edx; dwFlags
0x140034375  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14003437c  nop     dword ptr [rax+rax+00h]
0x140034381  and     cs:CXPLAT_HMAC_SHA512_ALG_HANDLE, 0
0x140034389  mov     rcx, cs:CXPLAT_AES_ECB_ALG_HANDLE; hAlgorithm
0x140034390  test    rcx, rcx
0x140034393  jz      short loc_1400343AB
0x140034395  xor     edx, edx; dwFlags
0x140034397  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14003439e  nop     dword ptr [rax+rax+00h]
0x1400343a3  and     cs:CXPLAT_AES_ECB_ALG_HANDLE, 0
0x1400343ab  mov     rcx, cs:CXPLAT_AES_GCM_ALG_HANDLE; hAlgorithm
0x1400343b2  test    rcx, rcx
0x1400343b5  jz      short loc_1400343CD
0x1400343b7  xor     edx, edx; dwFlags
0x1400343b9  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400343c0  nop     dword ptr [rax+rax+00h]
0x1400343c5  and     cs:CXPLAT_AES_GCM_ALG_HANDLE, 0
0x1400343cd  mov     rcx, cs:CXPLAT_CHACHA20_POLY1305_ALG_HANDLE; hAlgorithm
0x1400343d4  test    rcx, rcx
0x1400343d7  jz      short loc_1400343EF
0x1400343d9  xor     edx, edx; dwFlags
0x1400343db  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400343e2  nop     dword ptr [rax+rax+00h]
0x1400343e7  and     cs:CXPLAT_CHACHA20_POLY1305_ALG_HANDLE, 0
0x1400343ef  mov     rcx, cs:CXPLAT_SP800108_CTR_HMAC_ALG_HANDLE; hAlgorithm
0x1400343f6  test    rcx, rcx
0x1400343f9  jz      short loc_140034411
0x1400343fb  xor     edx, edx; dwFlags
0x1400343fd  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140034404  nop     dword ptr [rax+rax+00h]
0x140034409  and     cs:CXPLAT_SP800108_CTR_HMAC_ALG_HANDLE, 0
0x140034411  mov     rbp, [rsp+38h+arg_8]
0x140034416  mov     eax, ebx
0x140034418  mov     rbx, [rsp+38h+arg_0]
0x14003441d  add     rsp, 30h
0x140034421  pop     rsi
0x140034422  retn
0x140034424  mov     rcx, cs:CXPLAT_CHACHA20_POLY1305_ALG_HANDLE; hObject
0x14003442b  lea     r8, aChainingmodenA; "ChainingModeN/A"
0x140034432  and     [rsp+38h+var_18], 0
0x140034437  lea     rdx, pszProperty; "ChainingMode"
0x14003443e  mov     r9d, 20h ; ' '; cbInput
0x140034444  call    cs:__imp_BCryptSetProperty
0x14003444b  nop     dword ptr [rax+rax+00h]
0x140034450  mov     ebx, eax
0x140034452  test    eax, eax
0x140034454  jns     loc_1400342E1
0x14003445a  test    cs:Microsoft_QuicEnableBits, 4
0x140034461  jz      loc_140034323
0x140034467  lea     r9, aSetChacha20Pol; "Set ChaCha20-Poly1305 chaining mode"
0x14003446e  jmp     loc_14003431B
```
