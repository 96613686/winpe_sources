# ScHelperEncryptCredentials

- ea: `0x18007de50`
- end: `0x18007e5be`
- name: `ScHelperEncryptCredentials`
- size: `1902`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int64, __int64, __int64, __int64, size_t, __int64, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180062ddc`

## callees

- `0x18000a810`
- `0x18002b260`
- `0x18002fdc0`
- `0x180042410`
- `0x18004317c`
- `0x180066594`
- `0x180067154`
- `0x180067518`
- `0x18006814c`
- `0x18007d1a8`
- `0x18007d358`
- `0x18007d49c`
- `0x18007de50`
- `0x18007f534`
- `0x18007f990`
- `0x18007f9fc`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e388`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e551`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007e551`
- `ncrypt!NCryptFreeObject` at `0x18007e587`
- `ncrypt!NCryptFreeObject` at `0x18007e587`
- `ncrypt!NCryptOpenKey` at `0x18007e180`
- `ncrypt!NCryptOpenKey` at `0x18007e180`
- `ncrypt!NCryptGetProperty` at `0x18007dfb8`
- `ncrypt!NCryptGetProperty` at `0x18007dfb8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x18007e569`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x18007e578`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x18007e569`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyKey` at `0x18007e578`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptEncrypt` at `0x18007e37a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptEncrypt` at `0x18007e4c8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptEncrypt` at `0x18007e37a`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptEncrypt` at `0x18007e4c8`

## pseudocode

```c
__int64 __fastcall ScHelperEncryptCredentials(
        void *a1,
        DWORD a2,
        NCRYPT_PROV_HANDLE a3,
        void *a4,
        struct _CRYPTOAPI_BLOB *a5,
        __int64 a6,
        unsigned __int8 *a7,
        unsigned __int8 *a8,
        size_t a9,
        __int64 a10,
        unsigned int *a11)
{
  int v14; // esi
  int IsNcryptRsaKey; // ebx
  struct Kerb3961::EncryptionAlgorithm *v16; // r15
  KerberosCryptoPolicy *v17; // rcx
  unsigned __int64 v18; // rcx
  size_t v19; // r14
  unsigned int v20; // ecx
  unsigned int v21; // edx
  __int64 v22; // r10
  unsigned int v23; // r8d
  unsigned int v24; // ecx
  __int64 v25; // rbx
  __int64 v26; // rsi
  int v27; // eax
  struct _CRYPTOAPI_BLOB *v28; // rdi
  __int64 v29; // rbx
  __int64 cbData; // rdi
  void *v31; // rdx
  char *v32; // rbx
  int v33; // eax
  NCRYPT_PROV_HANDLE v34; // rdi
  unsigned __int8 *v35; // r15
  unsigned int v36; // eax
  unsigned __int8 *v37; // rsi
  int v38; // eax
  HLOCAL v39; // r15
  unsigned int v40; // ecx
  unsigned int v41; // eax
  unsigned __int64 v42; // rbx
  BYTE *p_cbOutput; // rdi
  __int64 v44; // rcx
  unsigned __int64 v45; // rcx
  void *v46; // rsp
  void *v47; // rsp
  BYTE *v48; // rax
  BOOL v49; // eax
  __int64 v50; // rdx
  BOOL v51; // ebx
  unsigned int *v52; // rsi
  unsigned __int64 v53; // rbx
  unsigned __int64 v54; // rcx
  __int64 v55; // rcx
  unsigned __int64 v56; // rcx
  void *v57; // rsp
  void *v58; // rsp
  BYTE *v59; // rax
  size_t v60; // r8
  _BYTE v62[32]; // [rsp+0h] [rbp-60h] BYREF
  DWORD *pcbResult; // [rsp+20h] [rbp-40h]
  DWORD dwBufLen[2]; // [rsp+30h] [rbp-30h]
  DWORD cbOutput; // [rsp+60h] [rbp+0h] BYREF
  size_t Size; // [rsp+64h] [rbp+4h] BYREF
  unsigned int v67; // [rsp+6Ch] [rbp+Ch] BYREF
  DWORD pdwDataLen; // [rsp+70h] [rbp+10h] BYREF
  int v69; // [rsp+74h] [rbp+14h] BYREF
  unsigned int *v70; // [rsp+78h] [rbp+18h]
  HCRYPTKEY hKey; // [rsp+80h] [rbp+20h] BYREF
  DWORD dwKeySpec; // [rsp+88h] [rbp+28h]
  __int64 v73; // [rsp+90h] [rbp+30h]
  void *Src; // [rsp+98h] [rbp+38h]
  struct _CRYPTOAPI_BLOB *v75; // [rsp+A0h] [rbp+40h]
  unsigned __int8 *v76; // [rsp+A8h] [rbp+48h]
  HCRYPTKEY v77; // [rsp+B0h] [rbp+50h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+B8h] [rbp+58h] BYREF
  __int64 v79; // [rsp+C0h] [rbp+60h]
  NCRYPT_PROV_HANDLE hProvider; // [rsp+C8h] [rbp+68h]
  __int64 v81; // [rsp+D0h] [rbp+70h] BYREF
  HLOCAL hMem; // [rsp+D8h] [rbp+78h] BYREF
  __int64 *v83[2]; // [rsp+E0h] [rbp+80h] BYREF
  BYTE pbOutput[528]; // [rsp+F0h] [rbp+90h] BYREF

  v75 = a5;
  v73 = a6;
  v76 = a8;
  hProvider = a3;
  dwKeySpec = a2;
  v70 = a11;
  Src = a4;
  v77 = 0;
  hKey = 0;
  hMem = 0;
  Size = 0;
  pdwDataLen = 0;
  v81 = 0;
  v67 = 0;
  memset_0(pbOutput, 0, 0x20Au);
  phKey = 0;
  v14 = 1;
  cbOutput = 520;
  v69 = 1;
  KerberosCryptoPolicy::Create(v83);
  if ( !v83[0] )
  {
    IsNcryptRsaKey = -1073741670;
    goto LABEL_82;
  }
  v79 = KerberosCryptoPolicy::SelectEncryptionAlgorithm();
  v16 = (struct Kerb3961::EncryptionAlgorithm *)v79;
  if ( !v79 )
  {
    IsNcryptRsaKey = -1073741059;
    goto LABEL_82;
  }
  if ( !a1 )
    goto LABEL_6;
  if ( ((a2 + 1) & 0xFFFFFFFE) != 0 )
    goto LABEL_27;
  IsNcryptRsaKey = ScHelperIsNcryptRsaKey(1, a1, &v69);
  if ( IsNcryptRsaKey < 0 )
    goto LABEL_82;
  v14 = v69;
  if ( v69 )
  {
LABEL_27:
    v19 = (unsigned int)a9;
    v22 = v73;
    v24 = a9 + 88;
    goto LABEL_28;
  }
  if ( !hProvider )
  {
LABEL_6:
    IsNcryptRsaKey = -1073741023;
    goto LABEL_82;
  }
  if ( !a4 )
  {
    IsNcryptRsaKey = NCryptGetProperty(
                       (NCRYPT_HANDLE)a1,
                       L"SmartCardAssociatedECDHKey",
                       pbOutput,
                       cbOutput,
                       &cbOutput,
                       0);
    if ( IsNcryptRsaKey < 0 )
      goto LABEL_82;
    Src = pbOutput;
LABEL_19:
    v19 = (unsigned int)a9;
    if ( (unsigned int)a9 > 0xFFFF || !KerberosCryptoPolicy::GetEncryptedSize(v17, v16, a9, &v67) )
    {
      IsNcryptRsaKey = -1073741637;
      goto LABEL_82;
    }
    v20 = v67 + 84;
    if ( v67 + 84 < v67
      || (v21 = v20 + v75->cbData, v21 < v20)
      || (v22 = v73, v23 = v21 + *(_DWORD *)(v73 + 16), v23 < v21)
      || (v24 = v23 + cbOutput, v23 + cbOutput < v23) )
    {
LABEL_17:
      IsNcryptRsaKey = -1073741675;
      goto LABEL_82;
    }
LABEL_28:
    v69 = v24;
    if ( !a10 || *v70 < v24 )
    {
      *v70 = v24;
      IsNcryptRsaKey = -1073741789;
      goto LABEL_82;
    }
    if ( !v14 )
    {
      *(_DWORD *)a10 = 0;
      v25 = a10 + 8;
      *(_DWORD *)(a10 + 4) = *(_DWORD *)(v22 + 16);
      memcpy_0((void *)(a10 + 8), *(const void **)(v22 + 8), *(unsigned int *)(v22 + 16));
      v26 = *(unsigned int *)(v73 + 16);
      *(_OWORD *)(v26 + v25) = *(_OWORD *)a7;
      *(_OWORD *)(v26 + v25 + 16) = *((_OWORD *)a7 + 1);
      *(_OWORD *)(v26 + v25 + 32) = *((_OWORD *)a7 + 2);
      *(_OWORD *)(v26 + v25 + 48) = *((_OWORD *)a7 + 3);
      v27 = (*(__int64 (__fastcall **)(struct Kerb3961::EncryptionAlgorithm *))(*(_QWORD *)v16 + 216LL))(v16);
      v28 = v75;
      *(_DWORD *)(v26 + v25 + 64) = v27;
      *(_DWORD *)(v26 + v25 + 68) = v28->cbData;
      v29 = v26 + a10 + 8;
      memcpy_0((void *)(v29 + 72), v28->pbData, v28->cbData);
      cbData = v28->cbData;
      v31 = Src;
      *(_DWORD *)(cbData + v29 + 72) = cbOutput;
      v32 = (char *)(cbData + v29 + 76);
      memcpy_0(v32, v31, cbOutput);
      v33 = v69 - cbData;
      v34 = hProvider;
      v67 = v33 - v26 - cbOutput - 84;
      v35 = (unsigned __int8 *)&v32[cbOutput];
      IsNcryptRsaKey = NCryptOpenKey(hProvider, &phKey, (LPCWSTR)Src, 0, 0x40u);
      if ( IsNcryptRsaKey >= 0 )
      {
        v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v79 + 216LL))(v79);
        IsNcryptRsaKey = KerbEncryptCreds(
                           v34,
                           phKey,
                           v75,
                           v36,
                           (unsigned int)pcbResult,
                           a7,
                           dwBufLen[0],
                           a7 + 32,
                           v19,
                           v76,
                           &v67,
                           v35);
        if ( IsNcryptRsaKey >= 0 )
          *v70 = v67 + (_DWORD)v35 - a10;
      }
      goto LABEL_82;
    }
    IsNcryptRsaKey = ScHelperCreateCredKeys(a1, dwKeySpec, v22, a7, 0, &v77, &hKey, (HCRYPTPROV *)&v81);
    if ( IsNcryptRsaKey < 0 )
      goto LABEL_82;
    v37 = v76;
    v38 = ScHelperCreateCredHMAC(v81, v77, v76, (unsigned int)v19, &hMem, &Size);
    v39 = hMem;
    IsNcryptRsaKey = v38;
    if ( v38 < 0 )
      goto LABEL_79;
    v40 = Size + v19;
    if ( (int)Size + (int)v19 < (unsigned int)Size || (v41 = v40 + 4, v40 + 4 < v40) )
    {
      IsNcryptRsaKey = -1073741675;
      HIDWORD(Size) = -1;
LABEL_79:
      if ( v39 )
        LocalFree(v39);
      goto LABEL_82;
    }
    HIDWORD(Size) = v40 + 4;
    v42 = v41;
    p_cbOutput = 0;
    if ( v40 == -4
      || v41 > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)v41 + g_ulAdditionalProbeSize + 8 < v41
      || !(unsigned int)((__int64 (*)(void))VerifyStackAvailable)() )
    {
      goto LABEL_91;
    }
    v44 = v42 + 23;
    if ( v42 + 23 <= v42 + 8 )
      v44 = 0xFFFFFFFFFFFFFF0LL;
    v45 = v44 & 0xFFFFFFFFFFFFFFF0uLL;
    v46 = alloca(v45);
    v47 = alloca(v45);
    p_cbOutput = (BYTE *)&cbOutput;
    if ( v62 == (_BYTE *)-96LL || (cbOutput = 1801679955, p_cbOutput = (BYTE *)&Size + 4, &Size == (size_t *)-4LL) )
    {
LABEL_91:
      if ( v42 + 8 >= v42 )
      {
        v48 = (BYTE *)((__int64 (*)(void))g_pfnAllocate)();
        p_cbOutput = v48;
        if ( v48 )
        {
          *(_DWORD *)v48 = 1885431112;
          p_cbOutput = v48 + 8;
        }
      }
    }
    if ( !p_cbOutput )
    {
LABEL_50:
      IsNcryptRsaKey = -1073741670;
      goto LABEL_79;
    }
    *(_DWORD *)p_cbOutput = Size;
    memcpy_0(p_cbOutput + 4, v39, (unsigned int)Size);
    memcpy_0(&p_cbOutput[(unsigned int)Size + 4], v37, v19);
    pdwDataLen = HIDWORD(Size);
    v49 = CryptEncrypt(hKey, 0, 1, 0, p_cbOutput, &pdwDataLen, HIDWORD(Size));
    v50 = 0;
    v51 = v49;
    if ( !v49 )
    {
      if ( GetLastError() != 234 )
      {
LABEL_53:
        IsNcryptRsaKey = -1073741023;
        goto LABEL_76;
      }
      v50 = 0;
    }
    v52 = v70;
    if ( *v70 && *v70 >= (unsigned __int64)pdwDataLen + 64 )
    {
      if ( !v51 )
      {
        if ( *((_DWORD *)p_cbOutput - 2) == 1885431112 )
          ((void (__fastcall *)(BYTE *, _QWORD))g_pfnFree)(p_cbOutput - 8, 0);
        v53 = HIDWORD(Size);
        p_cbOutput = 0;
        if ( !HIDWORD(Size) )
          goto LABEL_92;
        if ( HIDWORD(Size) > (unsigned __int64)g_ulMaxStackAllocSize )
          goto LABEL_92;
        v54 = HIDWORD(Size) + g_ulAdditionalProbeSize + 8;
        if ( v54 < HIDWORD(Size) || !(unsigned int)VerifyStackAvailable(v54, v50) )
          goto LABEL_92;
        v55 = v53 + 23;
        if ( v53 + 23 <= v53 + 8 )
          v55 = 0xFFFFFFFFFFFFFF0LL;
        v56 = v55 & 0xFFFFFFFFFFFFFFF0uLL;
        v57 = alloca(v56);
        v58 = alloca(v56);
        p_cbOutput = (BYTE *)&cbOutput;
        if ( v62 == (_BYTE *)-96LL || (cbOutput = 1801679955, p_cbOutput = (BYTE *)&Size + 4, &Size == (size_t *)-4LL) )
        {
LABEL_92:
          if ( v53 + 8 >= v53 )
          {
            v59 = (BYTE *)((__int64 (__fastcall *)(unsigned __int64, __int64))g_pfnAllocate)(v53 + 8, v50);
            p_cbOutput = v59;
            if ( v59 )
            {
              *(_DWORD *)v59 = 1885431112;
              p_cbOutput = v59 + 8;
            }
          }
        }
        if ( !p_cbOutput )
          goto LABEL_50;
        *(_DWORD *)p_cbOutput = Size;
        memcpy_0(p_cbOutput + 4, v39, (unsigned int)Size);
        memcpy_0(&p_cbOutput[(unsigned int)Size + 4], v76, v19);
        if ( !CryptEncrypt(hKey, 0, 1, 0, p_cbOutput, (DWORD *)&Size + 1, pdwDataLen) )
          goto LABEL_53;
      }
      v60 = HIDWORD(Size);
      *(_OWORD *)a10 = *(_OWORD *)a7;
      *(_OWORD *)(a10 + 16) = *((_OWORD *)a7 + 1);
      *(_OWORD *)(a10 + 32) = *((_OWORD *)a7 + 2);
      *(_OWORD *)(a10 + 48) = *((_OWORD *)a7 + 3);
      memcpy_0((void *)(a10 + 64), p_cbOutput, v60);
      IsNcryptRsaKey = 0;
    }
    else
    {
      IsNcryptRsaKey = -1073741789;
    }
    *v52 = pdwDataLen + 64;
LABEL_76:
    if ( *((_DWORD *)p_cbOutput - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    goto LABEL_79;
  }
  v18 = -1;
  do
    ++v18;
  while ( *((_WORD *)a4 + v18) );
  if ( (int)ULongLongToULong(v18, &cbOutput) < 0 )
    goto LABEL_17;
  IsNcryptRsaKey = RtlULongLongToULong(2LL * cbOutput, &cbOutput);
  if ( IsNcryptRsaKey >= 0 )
    goto LABEL_19;
LABEL_82:
  if ( hKey )
    CryptDestroyKey(hKey);
  if ( v77 )
    CryptDestroyKey(v77);
  if ( phKey )
    NCryptFreeObject(phKey);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(v83);
  return (unsigned int)IsNcryptRsaKey;
}

```

## disassembly

```asm
0x18007de50  push    rbp
0x18007de52  push    rbx
0x18007de53  push    rsi
0x18007de54  push    rdi
0x18007de55  push    r12
0x18007de57  push    r13
0x18007de59  push    r14
0x18007de5b  push    r15
0x18007de5d  sub     rsp, 318h
0x18007de64  lea     rbp, [rsp+60h]
0x18007de69  mov     rax, cs:__security_cookie
0x18007de70  xor     rax, rbp
0x18007de73  mov     [rbp+2F0h+var_50], rax
0x18007de7a  mov     rax, [rbp+2F0h+arg_20]
0x18007de81  xor     esi, esi
0x18007de83  mov     r13, [rbp+2F0h+arg_30]
0x18007de8a  mov     ebx, edx
0x18007de8c  mov     r12, [rbp+2F0h+arg_48]
0x18007de93  mov     rdi, rcx
0x18007de96  mov     [rbp+2F0h+var_2B0], rax
0x18007de9a  lea     rcx, [rbp+2F0h+pbOutput]; void *
0x18007dea1  mov     rax, [rbp+2F0h+arg_28]
0x18007dea8  mov     r14, r9
0x18007deab  mov     [rbp+2F0h+var_2C0], rax
0x18007deaf  mov     rax, [rbp+2F0h+arg_38]
0x18007deb6  mov     [rbp+2F0h+var_2A8], rax
0x18007deba  mov     rax, [rbp+2F0h+arg_50]
0x18007dec1  mov     [rbp+2F0h+hProvider], r8
0x18007dec5  mov     r8d, 20Ah; Size
0x18007decb  mov     [rbp+2F0h+dwKeySpec], edx
0x18007dece  xor     edx, edx; Val
0x18007ded0  mov     [rbp+2F0h+var_2D8], rax
0x18007ded4  mov     [rbp+2F0h+Src], r9
0x18007ded8  mov     [rbp+2F0h+var_2A0], rsi
0x18007dedc  mov     [rbp+2F0h+hKey], rsi
0x18007dee0  mov     [rbp+2F0h+hMem], rsi
0x18007dee4  mov     dword ptr [rbp+2F0h+Size], esi
0x18007dee7  mov     dword ptr [rbp+2F0h+Size+4], esi
0x18007deea  mov     [rbp+2F0h+pdwDataLen], esi
0x18007deed  mov     [rbp+2F0h+var_280], rsi
0x18007def1  mov     [rbp+2F0h+var_2E4], esi
0x18007def4  call    memset_0
0x18007def9  mov     [rbp+2F0h+phKey], rsi
0x18007defd  lea     rcx, [rbp+2F0h+var_270]
0x18007df04  mov     esi, 1
0x18007df09  mov     [rbp+2F0h+cbOutput], 208h
0x18007df10  mov     [rbp+2F0h+var_2DC], esi
0x18007df13  call    ?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z; KerberosCryptoPolicy::Create(Kerb3961PolicyType)
0x18007df18  mov     rcx, [rbp+2F0h+var_270]
0x18007df1f  test    rcx, rcx
0x18007df22  jnz     short loc_18007DF2E
0x18007df24  mov     ebx, 0C000009Ah
0x18007df29  jmp     loc_18007E560
0x18007df2e  call    ?SelectEncryptionAlgorithm@KerberosCryptoPolicy@@QEAAPEAUEncryptionAlgorithm@Kerb3961@@W4KeyUsage@3@W4KdcPrincipalKeyState@@@Z; KerberosCryptoPolicy::SelectEncryptionAlgorithm(Kerb3961::KeyUsage,KdcPrincipalKeyState)
0x18007df33  mov     [rbp+2F0h+var_290], rax
0x18007df37  mov     r15, rax
0x18007df3a  test    rax, rax
0x18007df3d  jnz     short loc_18007DF49
0x18007df3f  mov     ebx, 0C00002FDh
0x18007df44  jmp     loc_18007E560
0x18007df49  test    rdi, rdi
0x18007df4c  jnz     short loc_18007DF58
0x18007df4e  mov     ebx, 0C0000321h
0x18007df53  jmp     loc_18007E560
0x18007df58  lea     eax, [rbx+1]
0x18007df5b  test    eax, 0FFFFFFFEh
0x18007df60  jnz     loc_18007E079
0x18007df66  lea     r8, [rbp+2F0h+var_2DC]; int *
0x18007df6a  mov     rdx, rdi; void *
0x18007df6d  mov     ecx, esi; int
0x18007df6f  call    ?ScHelperIsNcryptRsaKey@@YAJHPEAXPEAH@Z; ScHelperIsNcryptRsaKey(int,void *,int *)
0x18007df74  mov     ebx, eax
0x18007df76  test    eax, eax
0x18007df78  js      loc_18007E560
0x18007df7e  mov     esi, [rbp+2F0h+var_2DC]
0x18007df81  xor     ebx, ebx
0x18007df83  test    esi, esi
0x18007df85  jnz     loc_18007E07B
0x18007df8b  cmp     [rbp+2F0h+hProvider], rbx
0x18007df8f  jz      short loc_18007DF4E
0x18007df91  test    r14, r14
0x18007df94  jnz     short loc_18007DFD5
0x18007df96  mov     r9d, [rbp+2F0h+cbOutput]; cbOutput
0x18007df9a  lea     rax, [rbp+2F0h+cbOutput]
0x18007df9e  mov     [rsp+350h+dwFlags], ebx; dwFlags
0x18007dfa2  lea     r8, [rbp+2F0h+pbOutput]; pbOutput
0x18007dfa9  lea     rdx, aSmartcardassoc; "SmartCardAssociatedECDHKey"
0x18007dfb0  mov     [rsp+350h+pcbResult], rax; pcbResult
0x18007dfb5  mov     rcx, rdi; hObject
0x18007dfb8  call    cs:__imp_NCryptGetProperty
0x18007dfbe  mov     ebx, eax
0x18007dfc0  test    eax, eax
0x18007dfc2  js      loc_18007E560
0x18007dfc8  lea     rax, [rbp+2F0h+pbOutput]
0x18007dfcf  mov     [rbp+2F0h+Src], rax
0x18007dfd3  jmp     short loc_18007E013
0x18007dfd5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007dfd9  inc     rcx; unsigned __int64
0x18007dfdc  cmp     [r14+rcx*2], bx
0x18007dfe1  jnz     short loc_18007DFD9
0x18007dfe3  lea     rdx, [rbp+2F0h+cbOutput]; unsigned int *
0x18007dfe7  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18007dfec  test    eax, eax
0x18007dfee  jns     short loc_18007DFFA
0x18007dff0  mov     ebx, 0C0000095h
0x18007dff5  jmp     loc_18007E560
0x18007dffa  mov     ecx, [rbp+2F0h+cbOutput]
0x18007dffd  lea     rdx, [rbp+2F0h+cbOutput]; unsigned int *
0x18007e001  add     rcx, rcx; unsigned __int64
0x18007e004  call    ?RtlULongLongToULong@@YAJ_KPEAK@Z; RtlULongLongToULong(unsigned __int64,ulong *)
0x18007e009  mov     ebx, eax
0x18007e00b  test    eax, eax
0x18007e00d  js      loc_18007E560
0x18007e013  mov     r14d, dword ptr [rbp+2F0h+arg_40]
0x18007e01a  cmp     r14d, 0FFFFh
0x18007e021  jbe     short loc_18007E02D
0x18007e023  mov     ebx, 0C00000BBh
0x18007e028  jmp     loc_18007E560
0x18007e02d  lea     r9, [rbp+2F0h+var_2E4]; unsigned int *
0x18007e031  mov     r8d, r14d; unsigned int
0x18007e034  mov     rdx, r15; struct Kerb3961::EncryptionAlgorithm *
0x18007e037  call    ?GetEncryptedSize@KerberosCryptoPolicy@@QEAA_NPEAUEncryptionAlgorithm@Kerb3961@@KPEAK@Z; KerberosCryptoPolicy::GetEncryptedSize(Kerb3961::EncryptionAlgorithm *,ulong,ulong *)
0x18007e03c  xor     ebx, ebx
0x18007e03e  test    al, al
0x18007e040  jz      short loc_18007E023
0x18007e042  mov     eax, [rbp+2F0h+var_2E4]
0x18007e045  lea     ecx, [rax+54h]
0x18007e048  cmp     ecx, eax
0x18007e04a  jb      short loc_18007DFF0
0x18007e04c  mov     r8, [rbp+2F0h+var_2B0]
0x18007e050  mov     edx, [r8]
0x18007e053  add     edx, ecx
0x18007e055  cmp     edx, ecx
0x18007e057  jb      short loc_18007DFF0
0x18007e059  mov     r10, [rbp+2F0h+var_2C0]
0x18007e05d  mov     r8d, [r10+10h]
0x18007e061  add     r8d, edx
0x18007e064  cmp     r8d, edx
0x18007e067  jb      short loc_18007DFF0
0x18007e069  mov     ecx, [rbp+2F0h+cbOutput]
0x18007e06c  add     ecx, r8d
0x18007e06f  cmp     ecx, r8d
0x18007e072  jnb     short loc_18007E08A
0x18007e074  jmp     loc_18007DFF0
0x18007e079  xor     ebx, ebx
0x18007e07b  mov     r14d, dword ptr [rbp+2F0h+arg_40]
0x18007e082  mov     r10, [rbp+2F0h+var_2C0]
0x18007e086  lea     ecx, [r14+58h]
0x18007e08a  mov     rax, [rbp+2F0h+var_2D8]
0x18007e08e  mov     edx, ecx
0x18007e090  mov     [rbp+2F0h+var_2DC], ecx
0x18007e093  test    r12, r12
0x18007e096  jz      loc_18007E559
0x18007e09c  cmp     [rax], ecx
0x18007e09e  jb      loc_18007E559
0x18007e0a4  test    esi, esi
0x18007e0a6  jnz     loc_18007E1FD
0x18007e0ac  mov     [r12], ebx
0x18007e0b0  lea     rbx, [r12+8]
0x18007e0b5  mov     eax, [r10+10h]
0x18007e0b9  mov     rcx, rbx; void *
0x18007e0bc  mov     [r12+4], eax
0x18007e0c1  mov     r8d, [r10+10h]; Size
0x18007e0c5  mov     rdx, [r10+8]; Src
0x18007e0c9  call    memcpy_0
0x18007e0ce  movaps  xmm0, xmmword ptr [r13+0]
0x18007e0d3  mov     rcx, r15
0x18007e0d6  mov     rax, [rbp+2F0h+var_2C0]
0x18007e0da  mov     esi, [rax+10h]
0x18007e0dd  movups  xmmword ptr [rsi+rbx], xmm0
0x18007e0e1  movaps  xmm1, xmmword ptr [r13+10h]
0x18007e0e6  movups  xmmword ptr [rsi+rbx+10h], xmm1
0x18007e0eb  movaps  xmm0, xmmword ptr [r13+20h]
0x18007e0f0  movups  xmmword ptr [rsi+rbx+20h], xmm0
0x18007e0f5  movaps  xmm1, xmmword ptr [r13+30h]
0x18007e0fa  movups  xmmword ptr [rsi+rbx+30h], xmm1
0x18007e0ff  mov     rax, [r15]
0x18007e102  mov     rax, [rax+0D8h]
0x18007e109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e10e  mov     rdi, [rbp+2F0h+var_2B0]
0x18007e112  mov     [rsi+rbx+40h], eax
0x18007e116  mov     eax, [rdi]
0x18007e118  mov     [rsi+rbx+44h], eax
0x18007e11c  add     rbx, rsi
0x18007e11f  mov     r8d, [rdi]; Size
0x18007e122  mov     rdx, [rdi+8]; Src
0x18007e126  lea     rcx, [rbx+48h]; void *
0x18007e12a  call    memcpy_0
0x18007e12f  mov     edi, [rdi]
0x18007e131  mov     eax, [rbp+2F0h+cbOutput]
0x18007e134  mov     rdx, [rbp+2F0h+Src]; Src
0x18007e138  mov     [rdi+rbx+48h], eax
0x18007e13c  add     rbx, 4Ch ; 'L'
0x18007e140  mov     r8d, [rbp+2F0h+cbOutput]; Size
0x18007e144  add     rbx, rdi
0x18007e147  mov     rcx, rbx; void *
0x18007e14a  call    memcpy_0
0x18007e14f  mov     eax, [rbp+2F0h+var_2DC]
0x18007e152  lea     rdx, [rbp+2F0h+phKey]; phKey
0x18007e156  mov     r15d, [rbp+2F0h+cbOutput]
0x18007e15a  sub     eax, edi
0x18007e15c  mov     rdi, [rbp+2F0h+hProvider]
0x18007e160  sub     eax, esi
0x18007e162  sub     eax, [rbp+2F0h+cbOutput]
0x18007e165  xor     r9d, r9d; dwLegacyKeySpec
0x18007e168  mov     r8, [rbp+2F0h+Src]; pszKeyName
0x18007e16c  sub     eax, 54h ; 'T'
0x18007e16f  mov     rcx, rdi; hProvider
0x18007e172  mov     [rbp+2F0h+var_2E4], eax
0x18007e175  add     r15, rbx
0x18007e178  mov     dword ptr [rsp+350h+pcbResult], 40h ; '@'; unsigned int
0x18007e180  call    cs:__imp_NCryptOpenKey
0x18007e186  mov     ebx, eax
0x18007e188  test    eax, eax
0x18007e18a  js      loc_18007E560
0x18007e190  mov     rcx, [rbp+2F0h+var_290]
0x18007e194  mov     rax, [rcx]
0x18007e197  mov     rax, [rax+0D8h]
0x18007e19e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e1a3  mov     r8, [rbp+2F0h+var_2B0]; struct _CRYPTOAPI_BLOB *
0x18007e1a7  lea     rdx, [rbp+2F0h+var_2E4]
0x18007e1ab  mov     [rsp+350h+var_2F8], r15; unsigned __int8 *
0x18007e1b0  lea     rcx, [r13+20h]
0x18007e1b4  mov     [rsp+350h+var_300], rdx; unsigned int *
0x18007e1b9  mov     r9d, eax; unsigned int
0x18007e1bc  mov     rdx, [rbp+2F0h+var_2A8]
0x18007e1c0  mov     [rsp+350h+var_308], rdx; unsigned __int8 *
0x18007e1c5  mov     rdx, [rbp+2F0h+phKey]; unsigned __int64
0x18007e1c9  mov     [rsp+350h+var_310], r14d; unsigned int
0x18007e1ce  mov     [rsp+350h+var_318], rcx; unsigned __int8 *
0x18007e1d3  mov     rcx, rdi; unsigned __int64
0x18007e1d6  mov     qword ptr [rsp+350h+dwFlags], r13; unsigned __int8 *
0x18007e1db  call    ?KerbEncryptCreds@@YAJ_K0PEAU_CRYPTOAPI_BLOB@@KKPEAEK2K2PEAK2@Z; KerbEncryptCreds(unsigned __int64,unsigned __int64,_CRYPTOAPI_BLOB *,ulong,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong *,uchar *)
0x18007e1e0  mov     ebx, eax
0x18007e1e2  test    eax, eax
0x18007e1e4  js      loc_18007E560
0x18007e1ea  mov     rax, [rbp+2F0h+var_2D8]
0x18007e1ee  sub     r15d, r12d
0x18007e1f1  add     r15d, [rbp+2F0h+var_2E4]
0x18007e1f5  mov     [rax], r15d
0x18007e1f8  jmp     loc_18007E560
0x18007e1fd  mov     edx, [rbp+2F0h+dwKeySpec]; dwKeySpec
0x18007e200  lea     rax, [rbp+2F0h+var_280]
0x18007e204  mov     [rsp+350h+var_318], rax; __int64
0x18007e209  mov     r9, r13
0x18007e20c  lea     rax, [rbp+2F0h+hKey]
0x18007e210  mov     r8, r10
0x18007e213  mov     qword ptr [rsp+350h+dwBufLen], rax; __int64
0x18007e218  mov     rcx, rdi; void *
0x18007e21b  lea     rax, [rbp+2F0h+var_2A0]
0x18007e21f  mov     qword ptr [rsp+350h+dwFlags], rax; __int64
0x18007e224  mov     dword ptr [rsp+350h+pcbResult], ebx; int
0x18007e228  call    ScHelperCreateCredKeys
0x18007e22d  mov     ebx, eax
0x18007e22f  test    eax, eax
0x18007e231  js      loc_18007E560
0x18007e237  mov     rsi, [rbp+2F0h+var_2A8]
0x18007e23b  lea     rax, [rbp+2F0h+Size]
0x18007e23f  mov     rdx, [rbp+2F0h+var_2A0]
0x18007e243  mov     r9d, r14d
0x18007e246  mov     rcx, [rbp+2F0h+var_280]
0x18007e24a  mov     r8, rsi
0x18007e24d  mov     qword ptr [rsp+350h+dwFlags], rax
0x18007e252  lea     rax, [rbp+2F0h+hMem]
0x18007e256  mov     [rsp+350h+pcbResult], rax
0x18007e25b  call    ScHelperCreateCredHMAC
0x18007e260  mov     r15, [rbp+2F0h+hMem]
0x18007e264  mov     ebx, eax
0x18007e266  test    eax, eax
0x18007e268  js      loc_18007E549
0x18007e26e  mov     eax, dword ptr [rbp+2F0h+Size]
0x18007e271  lea     ecx, [rax+r14]
0x18007e275  cmp     ecx, eax
0x18007e277  jb      loc_18007E53D
0x18007e27d  lea     eax, [rcx+4]
0x18007e280  cmp     eax, ecx
0x18007e282  jb      loc_18007E53D
0x18007e288  xor     ecx, ecx
0x18007e28a  mov     dword ptr [rbp+2F0h+Size+4], eax
0x18007e28d  mov     ebx, eax
0x18007e28f  mov     edi, ecx
0x18007e291  test    eax, eax
0x18007e293  jz      short loc_18007E2F6
0x18007e295  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18007e29c  ja      short loc_18007E2F6
0x18007e29e  mov     rcx, cs:g_ulAdditionalProbeSize
0x18007e2a5  add     rcx, 8
0x18007e2a9  add     rcx, rbx
0x18007e2ac  cmp     rcx, rbx
0x18007e2af  jb      short loc_18007E2F6
0x18007e2b1  call    VerifyStackAvailable
0x18007e2b6  test    eax, eax
0x18007e2b8  jz      short loc_18007E2F6
0x18007e2ba  lea     rax, [rbx+8]
0x18007e2be  lea     rcx, [rax+0Fh]
0x18007e2c2  cmp     rcx, rax
0x18007e2c5  ja      short loc_18007E2D1
0x18007e2c7  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18007e2d1  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18007e2d5  mov     rax, rcx
  ... truncated ...
```
