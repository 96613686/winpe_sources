# AeComputeMultiHashes

- ea: `0x180064654`
- end: `0x180064f76`
- name: `AeComputeMultiHashes`
- size: `2338`
- prototype: `__int64 __fastcall(BYTE *pbData)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800771c8`

## callees

- `0x180005e40`
- `0x180006e88`
- `0x180064654`
- `0x180065d34`
- `0x180065d5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800647c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006482d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006488f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800649b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064e94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064747`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800647c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006482d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006488f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800649b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064ae5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064e01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064e94`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18006473d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180064823`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18006473d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x180064823`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180064f3a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180064f4f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180064f3a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180064f4f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180064f12`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180064f25`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180064f12`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180064f25`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800647b7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180064885`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x1800647b7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180064885`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180064936`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180064952`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180064936`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180064952`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180064a38`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180064adb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180064df7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180064e8a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180064a38`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180064adb`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180064df7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180064e8a`

## pseudocode

```c
__int64 __fastcall AeComputeMultiHashes(BYTE *pbData, unsigned __int64 a2, __int64 a3, wchar_t *a4)
{
  unsigned __int64 v6; // r14
  unsigned int v8; // ebx
  signed int LastError; // eax
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  BYTE *v15; // r12
  const BYTE *v16; // rbx
  DWORD v17; // r14d
  DWORD v18; // r8d
  signed int v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  signed int v24; // eax
  BYTE v25; // cl
  unsigned __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  signed int v30; // eax
  signed int v31; // eax
  unsigned __int64 v32; // r8
  unsigned __int64 i; // rdx
  __int64 v34; // rcx
  DWORD pdwDataLen; // [rsp+30h] [rbp-50h] BYREF
  HCRYPTHASH phHash; // [rsp+38h] [rbp-48h] BYREF
  HCRYPTHASH hHash; // [rsp+40h] [rbp-40h] BYREF
  HCRYPTPROV hProv; // [rsp+48h] [rbp-38h] BYREF
  HCRYPTPROV phProv; // [rsp+50h] [rbp-30h] BYREF
  BYTE pbDataa[16]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v42; // [rsp+68h] [rbp-18h]

  pdwDataLen = 0;
  phProv = 0;
  hProv = 0;
  phHash = 0;
  v6 = a2;
  hHash = 0;
  *(_OWORD *)pbDataa = 0;
  v42 = 0;
  if ( dwDataLen )
  {
    if ( dwDataLen > 0x40000000 )
      dwDataLen = 0x40000000;
  }
  else
  {
    dwDataLen = 0x2000000;
  }
  if ( !a3 && !a4 )
    return 1;
  if ( !a2 )
  {
    v8 = -2147467259;
    if ( a3 )
      wcscpy_s((wchar_t *)a3, 0x2Du, L"0000da39a3ee5e6b4b0d3255bfef95601890afd80709");
    if ( a4 )
      wcscpy_s(a4, 0x41u, L"e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855");
    goto LABEL_105;
  }
  if ( !CryptAcquireContextW(&phProv, 0, L"Microsoft Base Cryptographic Provider v1.0", 1u, 0xF0000000) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_105;
    v11 = 23;
    goto LABEL_19;
  }
  if ( a3 && !CryptCreateHash(phProv, 0x8004u, 0, 0, &phHash) )
  {
    v12 = GetLastError();
    v8 = v12;
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_105;
    v11 = 24;
    goto LABEL_19;
  }
  if ( a4 )
  {
    if ( !CryptAcquireContextW(&hProv, 0, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000000) )
    {
      v13 = GetLastError();
      v8 = v13;
      if ( v13 > 0 )
        v8 = (unsigned __int16)v13 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_105;
      v11 = 26;
      goto LABEL_19;
    }
    if ( !CryptCreateHash(hProv, 0x800Cu, 0, 0, &hHash) )
    {
      v14 = GetLastError();
      v8 = v14;
      if ( v14 > 0 )
        v8 = (unsigned __int16)v14 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_105;
      v11 = 27;
      goto LABEL_19;
    }
  }
  else if ( v6 > 0x1E00000 )
  {
    v6 = 31457280;
  }
  v15 = &pbData[v6];
  v16 = pbData;
  if ( pbData < &pbData[v6] )
  {
    while ( 1 )
    {
      v17 = (_DWORD)v15 - (_DWORD)v16;
      if ( (int)v15 - (int)v16 > dwDataLen )
        v17 = dwDataLen;
      if ( a3 && v16 < pbData + 31457280 )
      {
        v18 = &v16[v17] <= pbData + 31457280 ? v17 : (_DWORD)pbData - (_DWORD)v16 + 31457280;
        if ( !CryptHashData(phHash, v16, v18, 0) )
        {
          v19 = GetLastError();
          v8 = v19;
          if ( v19 > 0 )
            v8 = (unsigned __int16)v19 | 0x80070000;
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 28;
            goto LABEL_19;
          }
          goto LABEL_105;
        }
      }
      if ( a4 && !CryptHashData(hHash, v16, v17, 0) )
        break;
      v16 += v17;
      if ( v16 >= v15 )
        goto LABEL_65;
    }
    v20 = GetLastError();
    v8 = v20;
    if ( v20 > 0 )
      v8 = (unsigned __int16)v20 | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 30;
      goto LABEL_19;
    }
    goto LABEL_105;
  }
LABEL_65:
  if ( a3 )
  {
    pdwDataLen = 0;
    *(_OWORD *)pbDataa = 0;
    v42 = 0;
    if ( !CryptGetHashParam(phHash, 2u, 0, &pdwDataLen, 0) )
    {
      v21 = GetLastError();
      v8 = v21;
      if ( v21 > 0 )
        v8 = (unsigned __int16)v21 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_105;
      v11 = 31;
      goto LABEL_19;
    }
    if ( pdwDataLen != 20 )
    {
      v8 = -2147418113;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_105;
      v23 = 32;
      goto LABEL_76;
    }
    if ( !CryptGetHashParam(phHash, 2u, pbDataa, &pdwDataLen, 0) )
    {
      v24 = GetLastError();
      v8 = v24;
      if ( v24 > 0 )
        v8 = (unsigned __int16)v24 | 0x80070000;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_105;
      v11 = 33;
      goto LABEL_19;
    }
    v25 = pbDataa[0];
    v26 = pbDataa[0];
    *(_DWORD *)a3 = 3145776;
    *(_DWORD *)(a3 + 4) = 3145776;
    *(_WORD *)(a3 + 8) = a0123456789abcd_0[v26 >> 4];
    *(_WORD *)(a3 + 10) = a0123456789abcd_0[v25 & 0xF];
    v27 = pbDataa[1] & 0xF;
    *(_WORD *)(a3 + 12) = a0123456789abcd_0[(unsigned __int64)pbDataa[1] >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27];
    LODWORD(v27) = pbDataa[2];
    *(_WORD *)(a3 + 14) = v26;
    *(_WORD *)(a3 + 16) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27 & 0xF];
    LODWORD(v27) = pbDataa[3];
    *(_WORD *)(a3 + 18) = v26;
    *(_WORD *)(a3 + 20) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27 & 0xF];
    LODWORD(v27) = pbDataa[4];
    *(_WORD *)(a3 + 22) = v26;
    *(_WORD *)(a3 + 24) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27 & 0xF];
    LODWORD(v27) = pbDataa[5];
    *(_WORD *)(a3 + 26) = v26;
    *(_WORD *)(a3 + 28) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27 & 0xF];
    LODWORD(v27) = pbDataa[6];
    *(_WORD *)(a3 + 30) = v26;
    *(_WORD *)(a3 + 32) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27 & 0xF];
    LODWORD(v27) = pbDataa[7];
    *(_WORD *)(a3 + 34) = v26;
    *(_WORD *)(a3 + 36) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27 & 0xF];
    LODWORD(v27) = pbDataa[8];
    *(_WORD *)(a3 + 38) = v26;
    *(_WORD *)(a3 + 40) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v27 & 0xF];
    LODWORD(v27) = pbDataa[9];
    *(_WORD *)(a3 + 42) = v26;
    *(_WORD *)(a3 + 44) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v27 >> 4];
    *(_WORD *)(a3 + 46) = a0123456789abcd_0[v27 & 0xF];
    v28 = pbDataa[10] & 0xF;
    *(_WORD *)(a3 + 48) = a0123456789abcd_0[(unsigned __int64)pbDataa[10] >> 4];
    *(_WORD *)(a3 + 50) = a0123456789abcd_0[v28];
    v29 = pbDataa[11] & 0xF;
    *(_WORD *)(a3 + 52) = a0123456789abcd_0[(unsigned __int64)pbDataa[11] >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29];
    LODWORD(v29) = pbDataa[12];
    *(_WORD *)(a3 + 54) = v26;
    *(_WORD *)(a3 + 56) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29 & 0xF];
    LODWORD(v29) = pbDataa[13];
    *(_WORD *)(a3 + 58) = v26;
    *(_WORD *)(a3 + 60) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29 & 0xF];
    LODWORD(v29) = pbDataa[14];
    *(_WORD *)(a3 + 62) = v26;
    *(_WORD *)(a3 + 64) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29 & 0xF];
    LODWORD(v29) = pbDataa[15];
    *(_WORD *)(a3 + 66) = v26;
    *(_WORD *)(a3 + 68) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29 & 0xF];
    LODWORD(v29) = (unsigned __int8)v42;
    *(_WORD *)(a3 + 70) = v26;
    *(_WORD *)(a3 + 72) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29 & 0xF];
    LODWORD(v29) = BYTE1(v42);
    *(_WORD *)(a3 + 74) = v26;
    *(_WORD *)(a3 + 76) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29 & 0xF];
    LODWORD(v29) = BYTE2(v42);
    *(_WORD *)(a3 + 78) = v26;
    *(_WORD *)(a3 + 80) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    LOWORD(v26) = a0123456789abcd_0[v29 & 0xF];
    LODWORD(v29) = BYTE3(v42);
    *(_WORD *)(a3 + 82) = v26;
    *(_WORD *)(a3 + 84) = a0123456789abcd_0[(unsigned __int64)(unsigned int)v29 >> 4];
    *(_DWORD *)(a3 + 86) = a0123456789abcd_0[v29 & 0xF];
  }
  if ( !a4 )
  {
LABEL_104:
    v8 = 0;
    goto LABEL_105;
  }
  pdwDataLen = 0;
  *(_OWORD *)pbDataa = 0;
  v42 = 0;
  if ( !CryptGetHashParam(hHash, 2u, 0, &pdwDataLen, 0) )
  {
    v30 = GetLastError();
    v8 = v30;
    if ( v30 > 0 )
      v8 = (unsigned __int16)v30 | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_105;
    v11 = 39;
    goto LABEL_19;
  }
  if ( pdwDataLen != 32 )
  {
    v8 = -2147418113;
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_105;
    v23 = 40;
LABEL_76:
    WPP_SF_(v22[2], v23, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids);
    goto LABEL_105;
  }
  if ( CryptGetHashParam(hHash, 2u, pbDataa, &pdwDataLen, 0) )
  {
    v32 = pdwDataLen;
    for ( i = 0; i < v32; a4[2 * i++ + 1] = a0123456789abcd_0[v34] )
    {
      v34 = pbDataa[i] & 0xF;
      a4[2 * i] = a0123456789abcd_0[(unsigned __int64)pbDataa[i] >> 4];
    }
    a4[2 * i] = 0;
    goto LABEL_104;
  }
  v31 = GetLastError();
  v8 = v31;
  if ( v31 > 0 )
    v8 = (unsigned __int16)v31 | 0x80070000;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_105;
  v11 = 41;
LABEL_19:
  WPP_SF_D(v10[2], v11, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids, v8);
LABEL_105:
  if ( phHash )
  {
    CryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( hHash )
  {
    CryptDestroyHash(hHash);
    hHash = 0;
  }
  if ( hProv )
  {
    CryptReleaseContext(hProv, 0);
    hProv = 0;
  }
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return v8;
}

```

## disassembly

```asm
0x180064654  push    rbp
0x180064656  push    rbx
0x180064657  push    rsi
0x180064658  push    r12
0x18006465a  push    r13
0x18006465c  push    r14
0x18006465e  push    r15
0x180064660  mov     rbp, rsp
0x180064663  sub     rsp, 80h
0x18006466a  mov     rax, cs:__security_cookie
0x180064671  xor     rax, rsp
0x180064674  mov     [rbp+var_8], rax
0x180064678  mov     eax, cs:dwDataLen
0x18006467e  xor     r12d, r12d
0x180064681  mov     [rbp+pdwDataLen], r12d
0x180064685  xorps   xmm0, xmm0
0x180064688  mov     [rbp+phProv], r12
0x18006468c  mov     rsi, r9
0x18006468f  mov     [rbp+hProv], r12
0x180064693  mov     r15, r8
0x180064696  mov     [rbp+phHash], r12
0x18006469a  mov     r14, rdx
0x18006469d  mov     [rbp+hHash], r12
0x1800646a1  mov     r13, rcx
0x1800646a4  movups  xmmword ptr [rbp+pbData], xmm0
0x1800646a8  movups  [rbp+var_18], xmm0
0x1800646ac  test    eax, eax
0x1800646ae  jnz     short loc_1800646BC
0x1800646b0  mov     cs:dwDataLen, 2000000h
0x1800646ba  jmp     short loc_1800646CB
0x1800646bc  mov     ecx, 40000000h
0x1800646c1  cmp     eax, ecx
0x1800646c3  jbe     short loc_1800646CB
0x1800646c5  mov     cs:dwDataLen, ecx
0x1800646cb  test    r15, r15
0x1800646ce  jnz     short loc_1800646DD
0x1800646d0  test    rsi, rsi
0x1800646d3  jnz     short loc_1800646DD
0x1800646d5  lea     ebx, [rsi+1]
0x1800646d8  jmp     loc_180064F55
0x1800646dd  test    r14, r14
0x1800646e0  jnz     short loc_180064721
0x1800646e2  mov     ebx, 80004005h
0x1800646e7  test    r15, r15
0x1800646ea  jz      short loc_1800646FF
0x1800646ec  lea     r8, a0000da39a3ee5e; "0000da39a3ee5e6b4b0d3255bfef95601890afd"...
0x1800646f3  mov     rcx, r15; Destination
0x1800646f6  lea     edx, [r14+2Dh]; SizeInWords
0x1800646fa  call    wcscpy_s
0x1800646ff  test    rsi, rsi
0x180064702  jz      loc_180064F09
0x180064708  lea     r8, aE3b0c44298fc1c; "e3b0c44298fc1c149afbf4c8996fb92427ae41e"...
0x18006470f  mov     edx, 41h ; 'A'; SizeInWords
0x180064714  mov     rcx, rsi; Destination
0x180064717  call    wcscpy_s
0x18006471c  jmp     loc_180064F09
0x180064721  mov     ebx, 0F0000000h
0x180064726  lea     r8, szProvider; "Microsoft Base Cryptographic Provider v"...
0x18006472d  mov     r9d, 1; dwProvType
0x180064733  mov     [rsp+80h+dwFlags], ebx; dwFlags
0x180064737  xor     edx, edx; szContainer
0x180064739  lea     rcx, [rbp+phProv]; phProv
0x18006473d  call    cs:__imp_CryptAcquireContextW
0x180064743  test    eax, eax
0x180064745  jnz     short loc_18006479A
0x180064747  call    cs:__imp_GetLastError
0x18006474d  mov     ebx, eax
0x18006474f  test    eax, eax
0x180064751  jle     short loc_18006475C
0x180064753  movzx   ebx, ax
0x180064756  or      ebx, 80070000h
0x18006475c  mov     rcx, cs:WPP_GLOBAL_Control
0x180064763  lea     rax, WPP_GLOBAL_Control
0x18006476a  cmp     rcx, rax
0x18006476d  jz      loc_180064F09
0x180064773  test    byte ptr [rcx+1Ch], 1
0x180064777  jz      loc_180064F09
0x18006477d  mov     edx, 17h
0x180064782  mov     rcx, [rcx+10h]
0x180064786  lea     r8, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids
0x18006478d  mov     r9d, ebx
0x180064790  call    WPP_SF_D
0x180064795  jmp     loc_180064F09
0x18006479a  test    r15, r15
0x18006479d  jz      short loc_1800647FE
0x18006479f  mov     rcx, [rbp+phProv]; hProv
0x1800647a3  lea     rax, [rbp+phHash]
0x1800647a7  xor     r9d, r9d; dwFlags
0x1800647aa  mov     qword ptr [rsp+80h+dwFlags], rax; phHash
0x1800647af  xor     r8d, r8d; hKey
0x1800647b2  mov     edx, 8004h; Algid
0x1800647b7  call    cs:__imp_CryptCreateHash
0x1800647bd  test    eax, eax
0x1800647bf  jnz     short loc_1800647FE
0x1800647c1  call    cs:__imp_GetLastError
0x1800647c7  mov     ebx, eax
0x1800647c9  test    eax, eax
0x1800647cb  jle     short loc_1800647D6
0x1800647cd  movzx   ebx, ax
0x1800647d0  or      ebx, 80070000h
0x1800647d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800647dd  lea     rax, WPP_GLOBAL_Control
0x1800647e4  cmp     rcx, rax
0x1800647e7  jz      loc_180064F09
0x1800647ed  test    byte ptr [rcx+1Ch], 1
0x1800647f1  jz      loc_180064F09
0x1800647f7  mov     edx, 18h
0x1800647fc  jmp     short loc_180064782
0x1800647fe  mov     edx, 1E00000h
0x180064803  test    rsi, rsi
0x180064806  jz      loc_1800648CF
0x18006480c  mov     r9d, 18h; dwProvType
0x180064812  mov     [rsp+80h+dwFlags], ebx; dwFlags
0x180064816  lea     r8, aMicrosoftEnhan; "Microsoft Enhanced RSA and AES Cryptogr"...
0x18006481d  xor     edx, edx; szContainer
0x18006481f  lea     rcx, [rbp+hProv]; phProv
0x180064823  call    cs:__imp_CryptAcquireContextW
0x180064829  test    eax, eax
0x18006482b  jnz     short loc_18006486D
0x18006482d  call    cs:__imp_GetLastError
0x180064833  mov     ebx, eax
0x180064835  test    eax, eax
0x180064837  jle     short loc_180064842
0x180064839  movzx   ebx, ax
0x18006483c  or      ebx, 80070000h
0x180064842  mov     rcx, cs:WPP_GLOBAL_Control
0x180064849  lea     rax, WPP_GLOBAL_Control
0x180064850  cmp     rcx, rax
0x180064853  jz      loc_180064F09
0x180064859  test    byte ptr [rcx+1Ch], 1
0x18006485d  jz      loc_180064F09
0x180064863  mov     edx, 1Ah
0x180064868  jmp     loc_180064782
0x18006486d  mov     rcx, [rbp+hProv]; hProv
0x180064871  lea     rax, [rbp+hHash]
0x180064875  xor     r9d, r9d; dwFlags
0x180064878  mov     qword ptr [rsp+80h+dwFlags], rax; phHash
0x18006487d  xor     r8d, r8d; hKey
0x180064880  mov     edx, 800Ch; Algid
0x180064885  call    cs:__imp_CryptCreateHash
0x18006488b  test    eax, eax
0x18006488d  jnz     short loc_1800648D8
0x18006488f  call    cs:__imp_GetLastError
0x180064895  mov     ebx, eax
0x180064897  test    eax, eax
0x180064899  jle     short loc_1800648A4
0x18006489b  movzx   ebx, ax
0x18006489e  or      ebx, 80070000h
0x1800648a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800648ab  lea     rax, WPP_GLOBAL_Control
0x1800648b2  cmp     rcx, rax
0x1800648b5  jz      loc_180064F09
0x1800648bb  test    byte ptr [rcx+1Ch], 1
0x1800648bf  jz      loc_180064F09
0x1800648c5  mov     edx, 1Bh
0x1800648ca  jmp     loc_180064782
0x1800648cf  cmp     r14, rdx
0x1800648d2  cmova   r14, rdx
0x1800648d6  jmp     short loc_1800648DD
0x1800648d8  mov     edx, 1E00000h
0x1800648dd  lea     r12, [r14+r13]
0x1800648e1  mov     rbx, r13
0x1800648e4  cmp     r13, r12
0x1800648e7  jnb     loc_1800649FB
0x1800648ed  mov     r14d, r12d
0x1800648f0  sub     r14d, ebx
0x1800648f3  cmp     r14d, cs:dwDataLen
0x1800648fa  cmova   r14d, cs:dwDataLen
0x180064902  test    r15, r15
0x180064905  jz      short loc_180064940
0x180064907  lea     rcx, [r13+1E00000h]
0x18006490e  cmp     rbx, rcx
0x180064911  jnb     short loc_180064940
0x180064913  mov     eax, r14d
0x180064916  add     rax, rbx
0x180064919  cmp     rax, rcx
0x18006491c  jbe     short loc_180064929
0x18006491e  mov     r8d, r13d
0x180064921  sub     r8d, ebx
0x180064924  add     r8d, edx
0x180064927  jmp     short loc_18006492C
0x180064929  mov     r8d, r14d; dwDataLen
0x18006492c  mov     rcx, [rbp+phHash]; hHash
0x180064930  xor     r9d, r9d; dwFlags
0x180064933  mov     rdx, rbx; pbData
0x180064936  call    cs:__imp_CryptHashData
0x18006493c  test    eax, eax
0x18006493e  jz      short loc_180064975
0x180064940  test    rsi, rsi
0x180064943  jz      short loc_18006495C
0x180064945  mov     rcx, [rbp+hHash]; hHash
0x180064949  xor     r9d, r9d; dwFlags
0x18006494c  mov     r8d, r14d; dwDataLen
0x18006494f  mov     rdx, rbx; pbData
0x180064952  call    cs:__imp_CryptHashData
0x180064958  test    eax, eax
0x18006495a  jz      short loc_1800649B8
0x18006495c  mov     eax, r14d
0x18006495f  add     rbx, rax
0x180064962  cmp     rbx, r12
0x180064965  jnb     loc_1800649FB
0x18006496b  mov     edx, 1E00000h
0x180064970  jmp     loc_1800648ED
0x180064975  call    cs:__imp_GetLastError
0x18006497b  xor     r12d, r12d
0x18006497e  mov     ebx, eax
0x180064980  test    eax, eax
0x180064982  jle     short loc_18006498D
0x180064984  movzx   ebx, ax
0x180064987  or      ebx, 80070000h
0x18006498d  mov     rcx, cs:WPP_GLOBAL_Control
0x180064994  lea     rax, WPP_GLOBAL_Control
0x18006499b  cmp     rcx, rax
0x18006499e  jz      loc_180064F09
0x1800649a4  test    byte ptr [rcx+1Ch], 1
0x1800649a8  jz      loc_180064F09
0x1800649ae  mov     edx, 1Ch
0x1800649b3  jmp     loc_180064782
0x1800649b8  call    cs:__imp_GetLastError
0x1800649be  xor     r12d, r12d
0x1800649c1  mov     ebx, eax
0x1800649c3  test    eax, eax
0x1800649c5  jle     short loc_1800649D0
0x1800649c7  movzx   ebx, ax
0x1800649ca  or      ebx, 80070000h
0x1800649d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800649d7  lea     rax, WPP_GLOBAL_Control
0x1800649de  cmp     rcx, rax
0x1800649e1  jz      loc_180064F09
0x1800649e7  test    byte ptr [rcx+1Ch], 1
0x1800649eb  jz      loc_180064F09
0x1800649f1  mov     edx, 1Eh
0x1800649f6  jmp     loc_180064782
0x1800649fb  mov     ebx, 2
0x180064a00  lea     r14, a0123456789abcd_0; "0123456789abcdef"
0x180064a07  xor     r12d, r12d
0x180064a0a  lea     r13d, [rbx+0Dh]
0x180064a0e  test    r15, r15
0x180064a11  jz      loc_180064DCD
0x180064a17  mov     rcx, [rbp+phHash]; hHash
0x180064a1b  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180064a1f  xorps   xmm0, xmm0
0x180064a22  mov     [rbp+pdwDataLen], r12d
0x180064a26  xor     r8d, r8d; pbData
0x180064a29  mov     [rsp+80h+dwFlags], r12d; dwFlags
0x180064a2e  mov     edx, ebx; dwParam
0x180064a30  movups  xmmword ptr [rbp+pbData], xmm0
0x180064a34  movups  [rbp+var_18], xmm0
0x180064a38  call    cs:__imp_CryptGetHashParam
0x180064a3e  test    eax, eax
0x180064a40  jnz     short loc_180064A82
0x180064a42  call    cs:__imp_GetLastError
0x180064a48  mov     ebx, eax
0x180064a4a  test    eax, eax
0x180064a4c  jle     short loc_180064A57
0x180064a4e  movzx   ebx, ax
0x180064a51  or      ebx, 80070000h
0x180064a57  mov     rcx, cs:WPP_GLOBAL_Control
0x180064a5e  lea     rax, WPP_GLOBAL_Control
0x180064a65  cmp     rcx, rax
0x180064a68  jz      loc_180064F09
0x180064a6e  test    byte ptr [rcx+1Ch], 1
0x180064a72  jz      loc_180064F09
0x180064a78  mov     edx, 1Fh
0x180064a7d  jmp     loc_180064782
0x180064a82  cmp     [rbp+pdwDataLen], 14h
0x180064a86  jz      short loc_180064AC8
0x180064a88  mov     ebx, 8000FFFFh
0x180064a8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180064a94  lea     rax, WPP_GLOBAL_Control
0x180064a9b  cmp     rcx, rax
0x180064a9e  jz      loc_180064F09
0x180064aa4  test    byte ptr [rcx+1Ch], 1
0x180064aa8  jz      loc_180064F09
0x180064aae  mov     edx, 20h ; ' '
0x180064ab3  mov     rcx, [rcx+10h]
0x180064ab7  lea     r8, WPP_ff13ec65e0c03369507e3b373b281b2e_Traceguids
0x180064abe  call    WPP_SF_
0x180064ac3  jmp     loc_180064F09
0x180064ac8  mov     rcx, [rbp+phHash]; hHash
0x180064acc  lea     r9, [rbp+pdwDataLen]; pdwDataLen
0x180064ad0  lea     r8, [rbp+pbData]; pbData
0x180064ad4  mov     [rsp+80h+dwFlags], r12d; dwFlags
0x180064ad9  mov     edx, ebx; dwParam
0x180064adb  call    cs:__imp_CryptGetHashParam
0x180064ae1  test    eax, eax
0x180064ae3  jnz     short loc_180064B25
0x180064ae5  call    cs:__imp_GetLastError
0x180064aeb  mov     ebx, eax
0x180064aed  test    eax, eax
0x180064aef  jle     short loc_180064AFA
0x180064af1  movzx   ebx, ax
0x180064af4  or      ebx, 80070000h
0x180064afa  mov     rcx, cs:WPP_GLOBAL_Control
0x180064b01  lea     rax, WPP_GLOBAL_Control
0x180064b08  cmp     rcx, rax
0x180064b0b  jz      loc_180064F09
0x180064b11  test    byte ptr [rcx+1Ch], 1
0x180064b15  jz      loc_180064F09
0x180064b1b  mov     edx, 21h ; '!'
  ... truncated ...
```
