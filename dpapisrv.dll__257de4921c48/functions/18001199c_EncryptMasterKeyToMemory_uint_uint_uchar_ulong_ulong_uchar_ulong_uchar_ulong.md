# EncryptMasterKeyToMemory(uint,uint,uchar *,ulong,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18001199c`
- end: `0x180012252`
- name: `?EncryptMasterKeyToMemory@@YAKIIPEAEKK0KPEAPEAEPEAK@Z`
- size: `2230`
- prototype: `ULONG __fastcall(int, int, unsigned __int8 *, ULONG, unsigned int, unsigned __int8 *, size_t Size, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180012258`
- `0x18002a794`
- `0x18002d330`

## callees

- `0x180002310`
- `0x180002480`
- `0x1800029d0`
- `0x180007f10`
- `0x180008300`
- `0x18001199c`
- `0x18001d810`
- `0x18001eb8c`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011c1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011c1a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011b23`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180011b23`
- `bcrypt!BCryptEncrypt` at `0x18001211b`
- `bcrypt!BCryptEncrypt` at `0x180012220`
- `bcrypt!BCryptEncrypt` at `0x18001211b`
- `bcrypt!BCryptEncrypt` at `0x180012220`
- `bcrypt!BCryptGenRandom` at `0x180011bcf`
- `bcrypt!BCryptGenRandom` at `0x180011c8b`
- `bcrypt!BCryptGenRandom` at `0x180011bcf`
- `bcrypt!BCryptGenRandom` at `0x180011c8b`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180011f47`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180012099`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800121c0`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180011f47`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180012099`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800121c0`
- `bcrypt!BCryptDecrypt` at `0x180011f9c`
- `bcrypt!BCryptDecrypt` at `0x180011f9c`
- `bcrypt!BCryptDestroyKey` at `0x180011fcc`
- `bcrypt!BCryptDestroyKey` at `0x180011fe2`
- `bcrypt!BCryptDestroyKey` at `0x18001212e`
- `bcrypt!BCryptDestroyKey` at `0x180012233`
- `bcrypt!BCryptDestroyKey` at `0x180011fcc`
- `bcrypt!BCryptDestroyKey` at `0x180011fe2`
- `bcrypt!BCryptDestroyKey` at `0x18001212e`
- `bcrypt!BCryptDestroyKey` at `0x180012233`
- `ntdll!RtlNtStatusToDosError` at `0x1800120c8`
- `ntdll!RtlNtStatusToDosError` at `0x1800120c8`

## string_xrefs

- `0x180011a8a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x180011b65`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x180011bf2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x180011cc8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x180011dad`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x180011fb2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x180012050`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`
- `0x1800120b1`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keyman.cpp`

## pseudocode

```c
ULONG __fastcall EncryptMasterKeyToMemory(
        int a1,
        int a2,
        unsigned __int8 *a3,
        ULONG a4,
        unsigned int a5,
        unsigned __int8 *a6,
        size_t Size,
        unsigned __int8 **a8,
        unsigned int *a9)
{
  int v9; // esi
  unsigned int v10; // r15d
  unsigned int v11; // ebx
  unsigned int v12; // r13d
  __int64 v13; // r12
  ULONG cbOutput; // edi
  SIZE_T v15; // rax
  __int64 v16; // r9
  int v17; // ebx
  int v18; // r14d
  UCHAR *v20; // rax
  int v21; // edx
  NTSTATUS v22; // eax
  __int64 v23; // r9
  const char *v24; // rdx
  __int64 v25; // rcx
  SIZE_T v26; // rdx
  HLOCAL v27; // rcx
  _BYTE *i; // rax
  int v29; // ecx
  int v30; // r8d
  UCHAR *v31; // r14
  NTSTATUS v32; // eax
  __int64 v33; // r9
  unsigned int v34; // r8d
  int v35; // edx
  _DWORD *v36; // rax
  UCHAR *v37; // r12
  void *BCryptProviderHandle; // rax
  NTSTATUS v39; // eax
  void *v40; // rax
  __int64 v41; // r9
  int v42; // ebx
  __int64 v43; // r9
  void *v44; // rax
  ULONG pcbResult; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v46; // [rsp+64h] [rbp-9Ch]
  unsigned int v47; // [rsp+68h] [rbp-98h]
  BCRYPT_KEY_HANDLE hKey; // [rsp+70h] [rbp-90h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v50; // [rsp+80h] [rbp-80h]
  HLOCAL hMem; // [rsp+88h] [rbp-78h]
  PUCHAR pbInput; // [rsp+90h] [rbp-70h]
  void *Src; // [rsp+98h] [rbp-68h]
  unsigned __int8 **v54; // [rsp+A0h] [rbp-60h]
  unsigned int *v55; // [rsp+A8h] [rbp-58h]
  SIZE_T v56[2]; // [rsp+B0h] [rbp-50h] BYREF
  UCHAR pbIV[16]; // [rsp+C0h] [rbp-40h] BYREF
  UCHAR pbOutput[24]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v59; // [rsp+E8h] [rbp-18h]
  __int128 v60; // [rsp+F0h] [rbp-10h]
  UCHAR v61[64]; // [rsp+110h] [rbp+10h] BYREF

  v9 = a1;
  Src = a6;
  v54 = a8;
  pcbResult = a4;
  hKey = a3;
  v55 = a9;
  if ( !a5 || a1 == 26625 )
  {
    v18 = 1;
    cbOutput = Size + 36;
    v46 = 1;
    v10 = 20;
    v13 = 4;
    v12 = 32777;
    v47 = 40;
    v9 = 26625;
    v15 = (unsigned int)(Size + 56);
LABEL_21:
    v50 = v15;
    LODWORD(phKey) = 1;
    goto LABEL_22;
  }
  v10 = 64;
  v11 = 64;
  v12 = 32782;
  if ( a2 != 32782 )
    v11 = 40;
  v47 = v11;
  if ( a2 != 32782 )
  {
    v12 = 32777;
    v10 = 20;
  }
  if ( a1 == 26115 )
  {
    v13 = 4;
  }
  else
  {
    if ( a1 != 26128 )
      return -2146893821;
    v13 = 0;
  }
  cbOutput = v10 + v13 + Size + 16;
  v15 = cbOutput + 32;
  v50 = cbOutput + 32;
  if ( a1 != 26115 )
  {
    if ( (cbOutput & 0xF) != 0 )
    {
      v16 = 5068;
      goto LABEL_14;
    }
    v18 = 0;
    v47 = v11;
    v46 = 0;
    goto LABEL_21;
  }
  if ( (cbOutput & 7) != 0 )
  {
    v16 = 5058;
LABEL_14:
    v17 = -2146893821;
    DebugTraceError(2148073475LL, "NTE_BAD_KEY", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v16);
    return v17;
  }
  v18 = 0;
  LODWORD(phKey) = 2;
  v46 = 0;
LABEL_22:
  v56[0] = v15;
  v20 = (UCHAR *)LocalAlloc(0, v15);
  hMem = v20;
  if ( !v20 )
  {
    v17 = 1130;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v21,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"ERROR_NOT_ENOUGH_SERVER_MEMORY",
        106,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
        212);
    return v17;
  }
  v17 = -2146893821;
  *(_QWORD *)pbIV = (-(__int64)(v18 != 0) & 0xFFFFFFFFFFFFFFF4uLL) + 32;
  *(_DWORD *)v20 = (v18 ^ 1) + 1;
  pbInput = v20 + 4;
  v22 = BCryptGenRandom(0, v20 + 4, 0x10u, 2u);
  if ( v22 < 0 )
  {
    v23 = 5103;
LABEL_28:
    v24 = "ntStatus";
    v25 = (unsigned int)v22;
LABEL_29:
    DebugTraceError(v25, v24, "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v23);
LABEL_30:
    v26 = v56[0];
    v27 = hMem;
    for ( i = hMem; v26; --v26 )
      *i++ = 0;
    LocalFree(v27);
    if ( (Microsoft_Windows_Crypto_DPAPIEnableBits & 0x10) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        v29,
        (unsigned int)ETW_LOG_MASTERKEY_ENCRYPTION_FAILED,
        v30,
        1,
        (__int64)v56);
    return v17;
  }
  v31 = (UCHAR *)hMem + *(_QWORD *)pbIV;
  v32 = BCryptGenRandom(0, (PUCHAR)hMem + *(_QWORD *)pbIV, 0x10u, 2u);
  if ( v32 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v32,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"ntStatus",
        v32,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
        253);
    goto LABEL_30;
  }
  if ( !v46 )
  {
    v34 = 0;
    while ( 1 )
    {
      v46 = v34 + 1;
      if ( !PKCS5DerivePBKDF2(
              (UCHAR *)hKey,
              pcbResult,
              (__int128 *)pbInput,
              v33,
              v12,
              a5,
              (unsigned __int8)v34 + 1,
              &pbOutput[v10 * v34],
              v47 - v10 * v34) )
        break;
      v34 = v46;
      if ( v46 >= (unsigned int)phKey )
      {
        v36 = hMem;
        *((_DWORD *)hMem + 5) = a5;
        v37 = &v31[v13 + 16 + v10];
        v36[7] = v9;
        v36[6] = v12;
        goto LABEL_51;
      }
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_sDsd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        v35,
        (unsigned int)WPP_677ac012138b306f90e36e17286bb8c1_Traceguids,
        (unsigned int)"NTE_FAIL",
        32,
        (__int64)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
        23);
    goto LABEL_30;
  }
  if ( !(unsigned int)ReusableHMAC(0, 0, v12, (PUCHAR)hKey, pcbResult, pbInput, 0x10u, 0, 0, pbOutput, v47) )
  {
    v23 = 5172;
LABEL_49:
    v24 = "NTE_FAIL";
    v25 = 2148073504LL;
    goto LABEL_29;
  }
  v37 = v31 + 36;
LABEL_51:
  if ( !(unsigned int)ReusableHMAC(0, 0, v12, (PUCHAR)hKey, pcbResult, v31, 0x10u, 0, 0, v61, v10) )
  {
    v23 = 5196;
    goto LABEL_49;
  }
  memcpy_0(v37, Src, (unsigned int)Size);
  if ( !(unsigned int)ReusableHMAC(0, 0, v12, v61, v10, (PUCHAR)Src, Size, 0, 0, v31 + 16, v10) )
  {
    v23 = 5223;
    goto LABEL_49;
  }
  if ( v9 == 26625 )
  {
    BCryptProviderHandle = (void *)GetBCryptProviderHandle(0x6801u);
    phKey = 0;
    pcbResult = 0;
    if ( !BCryptProviderHandle )
    {
      v23 = 5237;
      goto LABEL_49;
    }
    v22 = BCryptGenerateSymmetricKey(BCryptProviderHandle, &phKey, 0, 0, pbOutput, 0x14u, 0);
    if ( v22 < 0 )
    {
      v23 = 5255;
      goto LABEL_28;
    }
    v39 = BCryptDecrypt(phKey, v31, cbOutput, 0, 0, 0, v31, cbOutput, &pcbResult, 1u);
    if ( v39 < 0 )
    {
      DebugTraceError(
        (unsigned int)v39,
        "ntStatus",
        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp",
        5272);
      BCryptDestroyKey(phKey);
      goto LABEL_30;
    }
    BCryptDestroyKey(phKey);
LABEL_63:
    v17 = 0;
    *v54 = (unsigned __int8 *)hMem;
    *v55 = v50;
    return v17;
  }
  if ( v9 == 26115 )
  {
    hKey = 0;
    pcbResult = 0;
    if ( (cbOutput & 0xFFFFFFF8) != cbOutput )
    {
      v23 = 5294;
      goto LABEL_49;
    }
    v40 = (void *)GetBCryptProviderHandle(0x6603u);
    if ( !v40 )
    {
      v41 = 5304;
LABEL_69:
      DebugTraceError(2148073504LL, "NTE_FAIL", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v41);
      return 13;
    }
    v42 = BCryptGenerateSymmetricKey(v40, &hKey, 0, 0, pbOutput, 0x18u, 0);
    if ( v42 >= 0 )
    {
      *(_QWORD *)pbIV = v59;
      v42 = BCryptEncrypt(hKey, v31, cbOutput & 0xFFFFFFF8, 0, pbIV, 8u, v31, cbOutput & 0xFFFFFFF8, &pcbResult, 0);
      BCryptDestroyKey(hKey);
      if ( v42 >= 0 )
        goto LABEL_63;
      v43 = 5342;
    }
    else
    {
      v43 = 5318;
    }
  }
  else
  {
    hKey = 0;
    pcbResult = 0;
    if ( (cbOutput & 0xFFFFFFF0) != cbOutput )
    {
      v23 = 5357;
      goto LABEL_49;
    }
    v44 = (void *)GetBCryptProviderHandle(0x6610u);
    if ( !v44 )
    {
      v41 = 5366;
      goto LABEL_69;
    }
    v42 = BCryptGenerateSymmetricKey(v44, &hKey, 0, 0, pbOutput, 0x20u, 0);
    if ( v42 >= 0 )
    {
      *(_OWORD *)pbIV = v60;
      v42 = BCryptEncrypt(hKey, v31, cbOutput & 0xFFFFFFF0, 0, pbIV, 0x10u, v31, cbOutput & 0xFFFFFFF0, &pcbResult, 0);
      BCryptDestroyKey(hKey);
      if ( v42 >= 0 )
        goto LABEL_63;
      v43 = 5403;
    }
    else
    {
      v43 = 5380;
    }
  }
  DebugTraceError((unsigned int)v42, "ntStatus", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keyman.cpp", v43);
  return RtlNtStatusToDosError(v42);
}

```

## disassembly

```asm
0x18001199c  mov     [rsp-8+arg_0], rbx
0x1800119a1  push    rbp
0x1800119a2  push    rsi
0x1800119a3  push    rdi
0x1800119a4  push    r12
0x1800119a6  push    r13
0x1800119a8  push    r14
0x1800119aa  push    r15
0x1800119ac  lea     rbp, [rsp-60h]
0x1800119b1  sub     rsp, 160h
0x1800119b8  mov     rax, cs:__security_cookie
0x1800119bf  xor     rax, rsp
0x1800119c2  mov     [rbp+90h+var_40], rax
0x1800119c6  cmp     [rbp+90h+arg_20], 0
0x1800119cd  mov     r11d, 6603h
0x1800119d3  mov     rax, [rbp+90h+arg_28]
0x1800119da  mov     esi, ecx
0x1800119dc  mov     [rbp+90h+Src], rax
0x1800119e0  mov     r10d, 6801h
0x1800119e6  mov     rax, [rbp+90h+arg_38]
0x1800119ed  mov     [rbp+90h+var_F0], rax
0x1800119f1  mov     rax, [rbp+90h+arg_40]
0x1800119f8  mov     [rsp+190h+var_130], r9d
0x1800119fd  lea     r9d, [r11+0Dh]
0x180011a01  mov     [rsp+190h+hKey], r8
0x180011a06  mov     r8d, 1
0x180011a0c  mov     [rbp+90h+var_E8], rax
0x180011a10  jz      loc_180011AE1
0x180011a16  cmp     ecx, r10d
0x180011a19  jz      loc_180011AE1
0x180011a1f  mov     ecx, 800Eh
0x180011a24  lea     r15d, [r8+3Fh]
0x180011a28  cmp     edx, ecx
0x180011a2a  lea     eax, [r8+27h]
0x180011a2e  mov     ebx, r15d
0x180011a31  mov     r13d, ecx
0x180011a34  cmovnz  ebx, eax
0x180011a37  lea     eax, [rcx-5]
0x180011a3a  mov     [rsp+190h+var_128], ebx
0x180011a3e  cmovnz  r13d, eax
0x180011a42  lea     eax, [r8+13h]
0x180011a46  cmovnz  r15d, eax
0x180011a4a  cmp     esi, r11d
0x180011a4d  jnz     short loc_180011A57
0x180011a4f  mov     r12d, 4
0x180011a55  jmp     short loc_180011A5F
0x180011a57  cmp     esi, r9d
0x180011a5a  jnz     short loc_180011AD7
0x180011a5c  xor     r12d, r12d
0x180011a5f  mov     edi, dword ptr [rbp+90h+Size]
0x180011a65  lea     eax, [r15+r12]
0x180011a69  add     edi, 10h
0x180011a6c  add     edi, eax
0x180011a6e  lea     eax, [rdi+20h]
0x180011a71  mov     [rbp+90h+var_110], eax
0x180011a74  cmp     esi, r11d
0x180011a77  jnz     short loc_180011AB6
0x180011a79  test    dil, 7
0x180011a7d  jz      short loc_180011AA4
0x180011a7f  mov     r9d, 13C2h
0x180011a85  mov     ebx, 80090003h
0x180011a8a  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180011a91  mov     ecx, ebx
0x180011a93  lea     rdx, aNteBadKey; "NTE_BAD_KEY"
0x180011a9a  call    DebugTraceError
0x180011a9f  jmp     loc_180011C4A
0x180011aa4  xor     r14d, r14d
0x180011aa7  mov     dword ptr [rsp+190h+phKey], 2
0x180011aaf  mov     [rsp+190h+var_12C], r14d
0x180011ab4  jmp     short loc_180011B1A
0x180011ab6  cmp     esi, r9d
0x180011ab9  jnz     short loc_180011AC9
0x180011abb  test    dil, 0Fh
0x180011abf  jz      short loc_180011AC9
0x180011ac1  mov     r9d, 13CCh
0x180011ac7  jmp     short loc_180011A85
0x180011ac9  xor     r14d, r14d
0x180011acc  mov     [rsp+190h+var_128], ebx
0x180011ad0  mov     [rsp+190h+var_12C], r14d
0x180011ad5  jmp     short loc_180011B12
0x180011ad7  mov     eax, 80090003h
0x180011adc  jmp     loc_180011C4C
0x180011ae1  mov     edi, dword ptr [rbp+90h+Size]
0x180011ae7  mov     r14d, r8d
0x180011aea  add     edi, 24h ; '$'
0x180011aed  mov     [rsp+190h+var_12C], r8d
0x180011af2  mov     r15d, 14h
0x180011af8  mov     r12d, 4
0x180011afe  mov     r13d, 8009h
0x180011b04  mov     [rsp+190h+var_128], 28h ; '('
0x180011b0c  mov     esi, r10d
0x180011b0f  lea     eax, [rdi+14h]
0x180011b12  mov     [rbp+90h+var_110], eax
0x180011b15  mov     dword ptr [rsp+190h+phKey], r8d
0x180011b1a  mov     rdx, rax; uBytes
0x180011b1d  mov     [rbp+90h+var_E0], rax
0x180011b21  xor     ecx, ecx; uFlags
0x180011b23  call    cs:__imp_LocalAlloc
0x180011b2a  nop     dword ptr [rax+rax+00h]
0x180011b2f  mov     [rbp+90h+hMem], rax
0x180011b33  mov     rcx, rax
0x180011b36  test    rax, rax
0x180011b39  jnz     short loc_180011B95
0x180011b3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011b42  lea     rax, WPP_GLOBAL_Control
0x180011b49  mov     ebx, 46Ah
0x180011b4e  cmp     rcx, rax
0x180011b51  jz      loc_180011C4A
0x180011b57  test    byte ptr [rcx+1Ch], 1
0x180011b5b  jz      loc_180011C4A
0x180011b61  mov     rcx, [rcx+10h]
0x180011b65  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180011b6c  mov     [rsp+190h+dwFlags], 13D4h
0x180011b74  lea     r9, aErrorNotEnough_0; "ERROR_NOT_ENOUGH_SERVER_MEMORY"
0x180011b7b  mov     qword ptr [rsp+190h+cbSecret], r8
0x180011b80  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180011b87  mov     dword ptr [rsp+190h+pbSecret], ebx
0x180011b8b  call    WPP_SF_sDsd
0x180011b90  jmp     loc_180011C4A
0x180011b95  mov     eax, r14d
0x180011b98  mov     r9d, 2; dwFlags
0x180011b9e  neg     eax
0x180011ba0  mov     ebx, 80090003h
0x180011ba5  sbb     rax, rax
0x180011ba8  and     rax, 0FFFFFFFFFFFFFFF4h
0x180011bac  lea     r8d, [r9+0Eh]; cbBuffer
0x180011bb0  add     rax, 20h ; ' '
0x180011bb4  mov     qword ptr [rbp+90h+pbIV], rax
0x180011bb8  mov     eax, r14d
0x180011bbb  xor     eax, 1
0x180011bbe  inc     eax
0x180011bc0  mov     [rcx], eax
0x180011bc2  lea     rax, [rcx+4]
0x180011bc6  mov     rdx, rax; pbBuffer
0x180011bc9  mov     [rbp+90h+pbInput], rax
0x180011bcd  xor     ecx, ecx; hAlgorithm
0x180011bcf  call    cs:__imp_BCryptGenRandom
0x180011bd6  nop     dword ptr [rax+rax+00h]
0x180011bdb  test    eax, eax
0x180011bdd  jns     loc_180011C74
0x180011be3  mov     r9d, 13EFh
0x180011be9  lea     rdx, aNtstatus; "ntStatus"
0x180011bf0  mov     ecx, eax
0x180011bf2  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180011bf9  call    DebugTraceError
0x180011bfe  mov     rdx, [rbp+90h+var_E0]
0x180011c02  mov     rcx, [rbp+90h+hMem]; hMem
0x180011c06  mov     rax, rcx
0x180011c09  test    rdx, rdx
0x180011c0c  jz      short loc_180011C1A
0x180011c0e  mov     byte ptr [rax], 0
0x180011c11  inc     rax
0x180011c14  sub     rdx, 1
0x180011c18  jnz     short loc_180011C0E
0x180011c1a  call    cs:__imp_LocalFree
0x180011c21  nop     dword ptr [rax+rax+00h]
0x180011c26  test    cs:Microsoft_Windows_Crypto_DPAPIEnableBits, 10h
0x180011c2d  jz      short loc_180011C4A
0x180011c2f  lea     rax, [rbp+90h+var_E0]
0x180011c33  mov     r9d, 1
0x180011c39  lea     rdx, ETW_LOG_MASTERKEY_ENCRYPTION_FAILED
0x180011c40  mov     [rsp+190h+pbSecret], rax
0x180011c45  call    McGenEventWrite_EtwEventWriteTransfer
0x180011c4a  mov     eax, ebx
0x180011c4c  mov     rcx, [rbp+90h+var_40]
0x180011c50  xor     rcx, rsp; StackCookie
0x180011c53  call    __security_check_cookie
0x180011c58  mov     rbx, [rsp+190h+arg_0]
0x180011c60  add     rsp, 160h
0x180011c67  pop     r15
0x180011c69  pop     r14
0x180011c6b  pop     r13
0x180011c6d  pop     r12
0x180011c6f  pop     rdi
0x180011c70  pop     rsi
0x180011c71  pop     rbp
0x180011c72  retn
0x180011c74  mov     r14, qword ptr [rbp+90h+pbIV]
0x180011c78  mov     r9d, 2; dwFlags
0x180011c7e  add     r14, [rbp+90h+hMem]
0x180011c82  xor     ecx, ecx; hAlgorithm
0x180011c84  mov     rdx, r14; pbBuffer
0x180011c87  lea     r8d, [r9+0Eh]; cbBuffer
0x180011c8b  call    cs:__imp_BCryptGenRandom
0x180011c92  nop     dword ptr [rax+rax+00h]
0x180011c97  xor     ecx, ecx; hAlgorithm
0x180011c99  mov     edx, eax
0x180011c9b  test    eax, eax
0x180011c9d  jns     short loc_180011CF4
0x180011c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ca6  lea     rax, WPP_GLOBAL_Control
0x180011cad  cmp     rcx, rax
0x180011cb0  jz      loc_180011BFE
0x180011cb6  test    byte ptr [rcx+1Ch], 1
0x180011cba  jz      loc_180011BFE
0x180011cc0  mov     [rsp+190h+dwFlags], 13FDh
0x180011cc8  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180011ccf  mov     qword ptr [rsp+190h+cbSecret], r8
0x180011cd4  lea     r9, aNtstatus; "ntStatus"
0x180011cdb  mov     dword ptr [rsp+190h+pbSecret], edx
0x180011cdf  mov     rcx, [rcx+10h]
0x180011ce3  lea     r8, WPP_677ac012138b306f90e36e17286bb8c1_Traceguids
0x180011cea  call    WPP_SF_sDsd
0x180011cef  jmp     loc_180011BFE
0x180011cf4  cmp     [rsp+190h+var_12C], ecx
0x180011cf8  jnz     loc_180011DCD
0x180011cfe  mov     r8d, ecx
0x180011d01  mov     ecx, [rsp+190h+var_128]
0x180011d05  mov     eax, r8d
0x180011d08  imul    eax, r15d
0x180011d0c  inc     r8d
0x180011d0f  mov     [rsp+190h+var_12C], r8d
0x180011d14  sub     ecx, eax
0x180011d16  mov     edx, eax
0x180011d18  mov     dword ptr [rsp+190h+pcbResult], ecx; int
0x180011d1c  lea     rax, [rbp+90h+pbOutput]
0x180011d20  mov     rcx, [rsp+190h+hKey]; int
0x180011d25  add     rax, rdx
0x180011d28  mov     edx, [rsp+190h+var_130]; int
0x180011d2c  mov     qword ptr [rsp+190h+cbOutput], rax; PUCHAR
0x180011d31  mov     eax, [rbp+90h+arg_20]
0x180011d37  mov     [rsp+190h+dwFlags], r8d; char
0x180011d3c  mov     r8, [rbp+90h+pbInput]; int
0x180011d40  mov     [rsp+190h+cbSecret], eax; int
0x180011d44  mov     dword ptr [rsp+190h+pbSecret], r13d; unsigned int
0x180011d49  call    PKCS5DerivePBKDF2
0x180011d4e  test    eax, eax
0x180011d50  jz      short loc_180011D84
0x180011d52  mov     r8d, [rsp+190h+var_12C]
0x180011d57  cmp     r8d, dword ptr [rsp+190h+phKey]
0x180011d5c  jb      short loc_180011D01
0x180011d5e  mov     rax, [rbp+90h+hMem]
0x180011d62  add     r12, 10h
0x180011d66  mov     ecx, [rbp+90h+arg_20]
0x180011d6c  add     r12, r14
0x180011d6f  mov     [rax+14h], ecx
0x180011d72  mov     ecx, r15d
0x180011d75  add     r12, rcx
0x180011d78  mov     [rax+1Ch], esi
0x180011d7b  mov     [rax+18h], r13d
0x180011d7f  jmp     loc_180011E2E
0x180011d84  mov     rcx, cs:WPP_GLOBAL_Control
0x180011d8b  lea     rax, WPP_GLOBAL_Control
0x180011d92  cmp     rcx, rax
0x180011d95  jz      loc_180011BFE
0x180011d9b  test    byte ptr [rcx+1Ch], 1
0x180011d9f  jz      loc_180011BFE
0x180011da5  mov     [rsp+190h+dwFlags], 1417h
0x180011dad  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180011db4  mov     qword ptr [rsp+190h+cbSecret], r8
0x180011db9  lea     r9, aNteFail; "NTE_FAIL"
0x180011dc0  mov     dword ptr [rsp+190h+pbSecret], 80090020h
0x180011dc8  jmp     loc_180011CDF
0x180011dcd  mov     eax, [rsp+190h+var_128]
0x180011dd1  mov     r8d, r13d; unsigned int
0x180011dd4  mov     r9, [rsp+190h+hKey]; pbSecret
0x180011dd9  xor     edx, edx; hHash
0x180011ddb  mov     [rsp+190h+var_140], eax; unsigned int
0x180011ddf  lea     rax, [rbp+90h+pbOutput]
0x180011de3  mov     qword ptr [rsp+190h+var_148], rax; pbOutput
0x180011de8  mov     rax, [rbp+90h+pbInput]
0x180011dec  mov     dword ptr [rsp+190h+pcbResult], ecx; cbHashObject
0x180011df0  mov     qword ptr [rsp+190h+cbOutput], rcx; pbHashObject
0x180011df5  mov     [rsp+190h+dwFlags], 10h; cbInput
0x180011dfd  mov     qword ptr [rsp+190h+cbSecret], rax; pbInput
0x180011e02  mov     eax, [rsp+190h+var_130]
0x180011e06  mov     dword ptr [rsp+190h+pbSecret], eax; ULONG
0x180011e0a  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x180011e0f  test    eax, eax
0x180011e11  jnz     short loc_180011E2A
0x180011e13  mov     r9d, 1434h
0x180011e19  lea     rdx, aNteFail; "NTE_FAIL"
0x180011e20  mov     ecx, 80090020h
0x180011e25  jmp     loc_180011BF2
0x180011e2a  lea     r12, [r14+24h]
0x180011e2e  mov     r9, [rsp+190h+hKey]; pbSecret
0x180011e33  lea     rax, [rbp+90h+var_80]
0x180011e37  mov     [rsp+190h+var_140], r15d; unsigned int
0x180011e3c  mov     r8d, r13d; unsigned int
0x180011e3f  mov     qword ptr [rsp+190h+var_148], rax; pbOutput
0x180011e44  xor     edx, edx; hHash
0x180011e46  mov     eax, [rsp+190h+var_130]
0x180011e4a  xor     ecx, ecx; hAlgorithm
0x180011e4c  mov     dword ptr [rsp+190h+pcbResult], 0; cbHashObject
0x180011e54  mov     qword ptr [rsp+190h+cbOutput], 0; pbHashObject
0x180011e5d  mov     [rsp+190h+dwFlags], 10h; cbInput
0x180011e65  mov     qword ptr [rsp+190h+cbSecret], r14; pbInput
0x180011e6a  mov     dword ptr [rsp+190h+pbSecret], eax; ULONG
0x180011e6e  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x180011e73  test    eax, eax
0x180011e75  jnz     short loc_180011E7F
0x180011e77  mov     r9d, 144Ch
0x180011e7d  jmp     short loc_180011E19
0x180011e7f  mov     r8d, dword ptr [rbp+90h+Size]; Size
0x180011e86  mov     rcx, r12; void *
0x180011e89  mov     rdx, [rbp+90h+Src]; Src
0x180011e8d  call    memcpy_0
0x180011e92  mov     [rsp+190h+var_140], r15d; unsigned int
0x180011e97  lea     rax, [r14+10h]
0x180011e9b  mov     qword ptr [rsp+190h+var_148], rax; pbOutput
  ... truncated ...
```
