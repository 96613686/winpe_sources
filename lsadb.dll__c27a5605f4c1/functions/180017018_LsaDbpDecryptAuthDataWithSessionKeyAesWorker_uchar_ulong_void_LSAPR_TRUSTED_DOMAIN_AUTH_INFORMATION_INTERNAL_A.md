# LsaDbpDecryptAuthDataWithSessionKeyAesWorker(uchar *,ulong,void *,_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES *,uchar * *,ulong *)

- ea: `0x180017018`
- end: `0x18001758c`
- name: `?LsaDbpDecryptAuthDataWithSessionKeyAesWorker@@YAJPEAEKPEAXPEAU_LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES@@PEAPEAEPEAK@Z`
- size: `1396`
- prototype: `int(unsigned __int8 *, unsigned int, void *, struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180016e14`

## callees

- `0x180001670`
- `0x18000fd18`
- `0x18000fd40`
- `0x180017018`
- `0x180017800`
- `0x18001a2b0`
- `0x18001a470`
- `0x18003ad24`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800171a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017201`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800173a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017404`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800171a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017201`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800173a9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180017404`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017297`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800172a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017497`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800174a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017519`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017522`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001752c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017536`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001753f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017297`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800172a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017497`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800174a0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017519`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017522`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001752c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017536`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001753f`
- `bcrypt!BCryptGetProperty` at `0x18001717a`
- `bcrypt!BCryptGetProperty` at `0x1800171e1`
- `bcrypt!BCryptGetProperty` at `0x180017382`
- `bcrypt!BCryptGetProperty` at `0x1800173e4`
- `bcrypt!BCryptGetProperty` at `0x18001717a`
- `bcrypt!BCryptGetProperty` at `0x1800171e1`
- `bcrypt!BCryptGetProperty` at `0x180017382`
- `bcrypt!BCryptGetProperty` at `0x1800173e4`
- `bcrypt!BCryptCreateHash` at `0x180017235`
- `bcrypt!BCryptCreateHash` at `0x180017437`
- `bcrypt!BCryptCreateHash` at `0x180017235`
- `bcrypt!BCryptCreateHash` at `0x180017437`
- `bcrypt!BCryptHashData` at `0x180017251`
- `bcrypt!BCryptHashData` at `0x180017452`
- `bcrypt!BCryptHashData` at `0x180017251`
- `bcrypt!BCryptHashData` at `0x180017452`
- `bcrypt!BCryptFinishHash` at `0x18001726d`
- `bcrypt!BCryptFinishHash` at `0x18001746d`
- `bcrypt!BCryptFinishHash` at `0x18001726d`
- `bcrypt!BCryptFinishHash` at `0x18001746d`
- `bcrypt!BCryptDestroyHash` at `0x18001728e`
- `bcrypt!BCryptDestroyHash` at `0x18001748e`
- `bcrypt!BCryptDestroyHash` at `0x18001728e`
- `bcrypt!BCryptDestroyHash` at `0x18001748e`

## pseudocode

```c
__int64 __fastcall LsaDbpDecryptAuthDataWithSessionKeyAesWorker(
        unsigned __int8 *a1,
        ULONG a2,
        void *a3,
        struct _LSAPR_TRUSTED_DOMAIN_AUTH_INFORMATION_INTERNAL_AES *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  unsigned int *v7; // r8
  ULONG v8; // eax
  unsigned __int8 **v10; // rdx
  UCHAR *v11; // r14
  UCHAR *v12; // rsi
  unsigned int v13; // r12d
  NTSTATUS Property; // ebx
  unsigned int v15; // edx
  HLOCAL v16; // rdi
  UCHAR *v17; // r14
  UCHAR *v18; // rsi
  ULONG v19; // r12d
  unsigned int v20; // r9d
  unsigned __int8 *v21; // rsi
  size_t Size; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pcbResult; // [rsp+48h] [rbp-B8h] BYREF
  UCHAR v25[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  ULONG v26; // [rsp+50h] [rbp-B0h] BYREF
  ULONG cbSecret; // [rsp+54h] [rbp-ACh]
  HLOCAL v28; // [rsp+58h] [rbp-A8h]
  UCHAR pbOutput[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 *v30; // [rsp+68h] [rbp-98h]
  unsigned int v31; // [rsp+70h] [rbp-90h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+78h] [rbp-88h] BYREF
  BCRYPT_HASH_HANDLE hHash; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h]
  unsigned __int8 *v35; // [rsp+90h] [rbp-70h] BYREF
  void *Buf1; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL v37; // [rsp+A0h] [rbp-60h] BYREF
  PUCHAR pbSecret; // [rsp+A8h] [rbp-58h]
  unsigned int *v39; // [rsp+B0h] [rbp-50h]
  unsigned __int8 **v40; // [rsp+B8h] [rbp-48h]
  UCHAR pbInput[56]; // [rsp+C0h] [rbp-40h] BYREF
  char v42[64]; // [rsp+F8h] [rbp-8h] BYREF

  v7 = a6;
  v8 = a2;
  strcpy(v42, "Microsoft LSAD encryption key AEAD-AES-256-CBC-HMAC-SHA512 16");
  cbSecret = a2;
  v10 = a5;
  pbSecret = a1;
  v40 = a5;
  v39 = a6;
  v28 = 0;
  Buf1 = 0;
  Size = 0;
  strcpy((char *)pbInput, "Microsoft LSAD MAC key AEAD-AES-256-CBC-HMAC-SHA512 16");
  v37 = 0;
  v31 = 0;
  v30 = 0;
  v35 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids);
    v8 = cbSecret;
    v10 = v40;
    v7 = v39;
  }
  if ( !*((_DWORD *)a4 + 20) || !*((_QWORD *)a4 + 11) )
  {
    hMem = 0;
    Property = -1073741811;
LABEL_47:
    v16 = v28;
    goto LABEL_48;
  }
  *v10 = 0;
  v11 = 0;
  *v7 = 0;
  v12 = 0;
  phHash = 0;
  v13 = 0;
  *(_DWORD *)pbOutput = 0;
  *(_DWORD *)v25 = 0;
  pcbResult = 0;
  hMem = 0;
  if ( !v8 )
  {
    Property = -1073741811;
    goto LABEL_21;
  }
  Property = BCryptGetProperty(a3, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property >= 0 )
  {
    if ( pcbResult != 4 )
    {
LABEL_9:
      Property = -1073741811;
      goto LABEL_19;
    }
    v11 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)pbOutput);
    if ( !v11 )
      goto LABEL_11;
    Property = BCryptGetProperty(a3, L"HashDigestLength", v25, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      if ( pcbResult != 4 )
        goto LABEL_9;
      v12 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)v25);
      if ( v12 )
      {
        Property = BCryptCreateHash(a3, &phHash, v11, *(ULONG *)pbOutput, pbSecret, cbSecret, 0);
        if ( Property >= 0 )
        {
          Property = BCryptHashData(phHash, pbInput, 0x37u, 0);
          if ( Property >= 0 )
          {
            Property = BCryptFinishHash(phHash, v12, *(ULONG *)v25, 0);
            if ( Property >= 0 )
            {
              v13 = *(_DWORD *)v25;
              hMem = v12;
              v12 = 0;
            }
          }
        }
        goto LABEL_19;
      }
LABEL_11:
      Property = -1073741670;
    }
  }
LABEL_19:
  if ( phHash )
    BCryptDestroyHash(phHash);
LABEL_21:
  LocalFree(v11);
  LocalFree(v12);
  if ( Property < 0 )
    goto LABEL_47;
  Property = LsaDbpWriteAuthInfoDataToHMAC(
               (unsigned __int8 *)a4 + 64,
               v15,
               *((unsigned __int8 **)a4 + 11),
               *((_DWORD *)a4 + 20),
               (unsigned __int8 **)&v37,
               (unsigned int *)&Size + 1);
  if ( Property < 0 )
    goto LABEL_47;
  Property = LsaDbpGenerateHMACWithSHA512(
               a3,
               (unsigned __int8 *)hMem,
               v13,
               (unsigned __int8 *)v37,
               HIDWORD(Size),
               (unsigned __int8 **)&Buf1,
               (unsigned int *)&Size);
  if ( Property < 0 )
    goto LABEL_47;
  if ( memcmp_0(Buf1, a4, (unsigned int)Size) )
  {
    Property = -1073741811;
    v16 = 0;
LABEL_48:
    v21 = v30;
    goto LABEL_49;
  }
  v17 = 0;
  hHash = 0;
  v18 = 0;
  v19 = 0;
  Size = 0;
  v26 = 0;
  v28 = 0;
  if ( !cbSecret )
  {
    Property = -1073741811;
    goto LABEL_42;
  }
  Property = BCryptGetProperty(a3, L"ObjectLength", (PUCHAR)&Size + 4, 4u, &v26, 0);
  if ( Property >= 0 )
  {
    if ( v26 != 4 )
    {
LABEL_30:
      Property = -1073741811;
      goto LABEL_40;
    }
    v17 = (UCHAR *)LocalAlloc(0x40u, HIDWORD(Size));
    if ( !v17 )
      goto LABEL_32;
    Property = BCryptGetProperty(a3, L"HashDigestLength", (PUCHAR)&Size, 4u, &v26, 0);
    if ( Property >= 0 )
    {
      if ( v26 != 4 )
        goto LABEL_30;
      v18 = (UCHAR *)LocalAlloc(0x40u, (unsigned int)Size);
      if ( v18 )
      {
        Property = BCryptCreateHash(a3, &hHash, v17, HIDWORD(Size), pbSecret, cbSecret, 0);
        if ( Property >= 0 )
        {
          Property = BCryptHashData(hHash, (PUCHAR)v42, 0x3Eu, 0);
          if ( Property >= 0 )
          {
            Property = BCryptFinishHash(hHash, v18, Size, 0);
            if ( Property >= 0 )
            {
              v19 = Size;
              v28 = v18;
              v18 = 0;
            }
          }
        }
        goto LABEL_40;
      }
LABEL_32:
      Property = -1073741670;
    }
  }
LABEL_40:
  if ( hHash )
    BCryptDestroyHash(hHash);
LABEL_42:
  LocalFree(v17);
  LocalFree(v18);
  v16 = v28;
  if ( Property < 0 )
    goto LABEL_48;
  Property = LsaDbpDecryptDataWithAES(
               *((PUCHAR *)a4 + 11),
               *((_DWORD *)a4 + 20),
               (PUCHAR)a4 + 64,
               v20,
               (unsigned __int8 *)v28,
               v19,
               &v35,
               &v31);
  if ( Property < 0 )
  {
    v21 = v35;
  }
  else
  {
    v21 = 0;
    *v39 = v31;
    *v40 = v35;
  }
LABEL_49:
  LocalFree(hMem);
  LocalFree(v16);
  LocalFree(Buf1);
  LocalFree(v37);
  LocalFree(v21);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      65,
      &WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids,
      (unsigned int)Property);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180017018  push    rbp
0x18001701a  push    rbx
0x18001701b  push    rsi
0x18001701c  push    rdi
0x18001701d  push    r12
0x18001701f  push    r13
0x180017021  push    r14
0x180017023  push    r15
0x180017025  lea     rbp, [rsp-48h]
0x18001702a  sub     rsp, 148h
0x180017031  mov     rax, cs:__security_cookie
0x180017038  xor     rax, rsp
0x18001703b  mov     [rbp+80h+var_48], rax
0x18001703f  movups  xmm0, xmmword ptr cs:aMicrosoftLsadE; "Microsoft LSAD encryption key AEAD-AES-"...
0x180017046  xor     ebx, ebx
0x180017048  mov     r13, r8
0x18001704b  movups  xmm1, xmmword ptr cs:aMicrosoftLsadE+10h; "ncryption key AEAD-AES-256-CBC-HMAC-SHA"...
0x180017052  mov     r8, [rbp+80h+arg_28]
0x180017059  mov     eax, edx
0x18001705b  movups  xmmword ptr [rbp+80h+var_88], xmm0
0x18001705f  mov     [rsp+180h+cbSecret], edx
0x180017063  mov     r15, r9
0x180017066  movups  xmm0, xmmword ptr cs:aMicrosoftLsadE+20h; "AD-AES-256-CBC-HMAC-SHA512 16"
0x18001706d  mov     rdx, [rbp+80h+arg_20]
0x180017074  movups  xmmword ptr [rbp+80h+var_88+10h], xmm1
0x180017078  mov     [rbp+80h+pbSecret], rcx
0x18001707c  movups  xmm1, xmmword ptr cs:aMicrosoftLsadE+2Eh; "-HMAC-SHA512 16"
0x180017083  mov     [rbp+80h+var_C8], rdx
0x180017087  movups  xmmword ptr [rbp+80h+var_88+20h], xmm0
0x18001708b  mov     [rbp+80h+var_D0], r8
0x18001708f  movups  xmm0, xmmword ptr cs:aMicrosoftLsadM; "Microsoft LSAD MAC key AEAD-AES-256-CBC"...
0x180017096  mov     [rsp+180h+var_128], rbx
0x18001709b  movups  xmmword ptr [rbp+80h+var_88+2Eh], xmm1
0x18001709f  mov     [rbp+80h+Buf1], rbx
0x1800170a3  movups  xmm1, xmmword ptr cs:aMicrosoftLsadM+10h; "AC key AEAD-AES-256-CBC-HMAC-SHA512 16"
0x1800170aa  mov     dword ptr [rsp+180h+Size], ebx
0x1800170ae  movups  xmmword ptr [rbp+80h+pbInput], xmm0
0x1800170b2  mov     [rbp+80h+var_E0], rbx
0x1800170b6  movups  xmm0, xmmword ptr cs:aMicrosoftLsadM+20h; "256-CBC-HMAC-SHA512 16"
0x1800170bd  mov     dword ptr [rsp+180h+Size+4], ebx
0x1800170c1  movups  [rbp+80h+var_B0], xmm1
0x1800170c5  mov     [rsp+180h+var_110], ebx
0x1800170c9  movsd   xmm1, qword ptr cs:aMicrosoftLsadM+2Fh; "A512 16"
0x1800170d1  movups  [rbp+80h+var_A0], xmm0
0x1800170d5  mov     [rsp+180h+var_118], rbx
0x1800170da  movsd   qword ptr [rbp+80h+var_A0+0Fh], xmm1
0x1800170df  mov     [rbp+80h+var_F0], rbx
0x1800170e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170ea  test    byte ptr [rcx+1Ch], 2
0x1800170ee  jz      short loc_18001710F
0x1800170f0  mov     rcx, [rcx+10h]
0x1800170f4  lea     edx, [rbx+40h]
0x1800170f7  lea     r8, WPP_589af85ad85e3e7fd8e73207de81c7d4_Traceguids
0x1800170fe  call    WPP_SF_
0x180017103  mov     eax, [rsp+180h+cbSecret]
0x180017107  mov     rdx, [rbp+80h+var_C8]
0x18001710b  mov     r8, [rbp+80h+var_D0]
0x18001710f  cmp     [r15+50h], ebx
0x180017113  jz      loc_180017502
0x180017119  cmp     [r15+58h], rbx
0x18001711d  jz      loc_180017502
0x180017123  mov     [rdx], rbx
0x180017126  mov     r14, rbx
0x180017129  mov     [r8], ebx
0x18001712c  mov     rsi, rbx
0x18001712f  mov     [rsp+180h+phHash], rbx
0x180017134  mov     r12d, ebx
0x180017137  mov     dword ptr [rsp+180h+pbOutput], ebx
0x18001713b  mov     dword ptr [rsp+180h+var_134], ebx
0x18001713f  mov     [rsp+180h+var_138], ebx
0x180017143  mov     [rbp+80h+hMem], rbx
0x180017147  test    eax, eax
0x180017149  jnz     short loc_180017157
0x18001714b  mov     edi, 0C000000Dh
0x180017150  mov     ebx, edi
0x180017152  jmp     loc_180017294
0x180017157  lea     rax, [rsp+180h+var_138]
0x18001715c  mov     [rsp+180h+dwFlags], ebx; dwFlags
0x180017160  mov     r9d, 4; cbOutput
0x180017166  mov     [rsp+180h+pcbResult], rax; pcbResult
0x18001716b  lea     r8, [rsp+180h+pbOutput]; pbOutput
0x180017170  mov     rcx, r13; hObject
0x180017173  lea     rdx, pszProperty; "ObjectLength"
0x18001717a  call    cs:__imp_BCryptGetProperty
0x180017180  mov     ebx, eax
0x180017182  mov     edi, 0C000000Dh
0x180017187  test    eax, eax
0x180017189  js      loc_180017284
0x18001718f  cmp     [rsp+180h+var_138], 4
0x180017194  jz      short loc_18001719D
0x180017196  mov     ebx, edi
0x180017198  jmp     loc_180017284
0x18001719d  mov     edx, dword ptr [rsp+180h+pbOutput]; uBytes
0x1800171a1  mov     ecx, 40h ; '@'; uFlags
0x1800171a6  call    cs:__imp_LocalAlloc
0x1800171ac  mov     r14, rax
0x1800171af  test    rax, rax
0x1800171b2  jnz     short loc_1800171BE
0x1800171b4  mov     ebx, 0C000009Ah
0x1800171b9  jmp     loc_180017284
0x1800171be  lea     rax, [rsp+180h+var_138]
0x1800171c3  mov     [rsp+180h+dwFlags], esi; dwFlags
0x1800171c7  mov     r9d, 4; cbOutput
0x1800171cd  mov     [rsp+180h+pcbResult], rax; pcbResult
0x1800171d2  lea     r8, [rsp+180h+var_134]; pbOutput
0x1800171d7  mov     rcx, r13; hObject
0x1800171da  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800171e1  call    cs:__imp_BCryptGetProperty
0x1800171e7  mov     ebx, eax
0x1800171e9  test    eax, eax
0x1800171eb  js      loc_180017284
0x1800171f1  cmp     [rsp+180h+var_138], 4
0x1800171f6  jnz     short loc_180017196
0x1800171f8  mov     edx, dword ptr [rsp+180h+var_134]; uBytes
0x1800171fc  mov     ecx, 40h ; '@'; uFlags
0x180017201  call    cs:__imp_LocalAlloc
0x180017207  mov     rsi, rax
0x18001720a  test    rax, rax
0x18001720d  jz      short loc_1800171B4
0x18001720f  mov     eax, [rsp+180h+cbSecret]
0x180017213  lea     rdx, [rsp+180h+phHash]; phHash
0x180017218  mov     r9d, dword ptr [rsp+180h+pbOutput]; cbHashObject
0x18001721d  mov     r8, r14; pbHashObject
0x180017220  mov     [rsp+180h+var_150], r12d; dwFlags
0x180017225  mov     rcx, r13; hAlgorithm
0x180017228  mov     [rsp+180h+dwFlags], eax; cbSecret
0x18001722c  mov     rax, [rbp+80h+pbSecret]
0x180017230  mov     [rsp+180h+pcbResult], rax; pbSecret
0x180017235  call    cs:__imp_BCryptCreateHash
0x18001723b  mov     ebx, eax
0x18001723d  test    eax, eax
0x18001723f  js      short loc_180017284
0x180017241  mov     rcx, [rsp+180h+phHash]; hHash
0x180017246  lea     rdx, [rbp+80h+pbInput]; pbInput
0x18001724a  xor     r9d, r9d; dwFlags
0x18001724d  lea     r8d, [r9+37h]; cbInput
0x180017251  call    cs:__imp_BCryptHashData
0x180017257  mov     ebx, eax
0x180017259  test    eax, eax
0x18001725b  js      short loc_180017284
0x18001725d  mov     r8d, dword ptr [rsp+180h+var_134]; cbOutput
0x180017262  xor     r9d, r9d; dwFlags
0x180017265  mov     rcx, [rsp+180h+phHash]; hHash
0x18001726a  mov     rdx, rsi; pbOutput
0x18001726d  call    cs:__imp_BCryptFinishHash
0x180017273  mov     ebx, eax
0x180017275  test    eax, eax
0x180017277  js      short loc_180017284
0x180017279  mov     r12d, dword ptr [rsp+180h+var_134]
0x18001727e  mov     [rbp+80h+hMem], rsi
0x180017282  xor     esi, esi
0x180017284  mov     rcx, [rsp+180h+phHash]; hHash
0x180017289  test    rcx, rcx
0x18001728c  jz      short loc_180017294
0x18001728e  call    cs:__imp_BCryptDestroyHash
0x180017294  mov     rcx, r14; hMem
0x180017297  call    cs:__imp_LocalFree
0x18001729d  mov     rcx, rsi; hMem
0x1800172a0  call    cs:__imp_LocalFree
0x1800172a6  test    ebx, ebx
0x1800172a8  js      loc_18001750B
0x1800172ae  mov     r9d, [r15+50h]; unsigned int
0x1800172b2  lea     rcx, [rsp+180h+Size+4]
0x1800172b7  mov     r8, [r15+58h]; unsigned __int8 *
0x1800172bb  mov     qword ptr [rsp+180h+dwFlags], rcx; unsigned int *
0x1800172c0  lea     rcx, [rbp+80h+var_E0]
0x1800172c4  mov     [rsp+180h+pcbResult], rcx; unsigned __int8 **
0x1800172c9  lea     rcx, [r15+40h]; unsigned __int8 *
0x1800172cd  call    ?LsaDbpWriteAuthInfoDataToHMAC@@YAJPEAEK0KPEAPEAEPEAK@Z; LsaDbpWriteAuthInfoDataToHMAC(uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x1800172d2  mov     ebx, eax
0x1800172d4  test    eax, eax
0x1800172d6  js      loc_18001750B
0x1800172dc  mov     r9, [rbp+80h+var_E0]; unsigned __int8 *
0x1800172e0  lea     rax, [rsp+180h+Size]
0x1800172e5  mov     rdx, [rbp+80h+hMem]; unsigned __int8 *
0x1800172e9  mov     r8d, r12d; unsigned int
0x1800172ec  mov     qword ptr [rsp+180h+var_150], rax; unsigned int *
0x1800172f1  mov     rcx, r13; hAlgorithm
0x1800172f4  lea     rax, [rbp+80h+Buf1]
0x1800172f8  mov     qword ptr [rsp+180h+dwFlags], rax; unsigned __int8 **
0x1800172fd  mov     eax, dword ptr [rsp+180h+Size+4]
0x180017301  mov     dword ptr [rsp+180h+pcbResult], eax; unsigned int
0x180017305  call    ?LsaDbpGenerateHMACWithSHA512@@YAJPEAXPEAEK1KPEAPEAEPEAK@Z; LsaDbpGenerateHMACWithSHA512(void *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)
0x18001730a  mov     ebx, eax
0x18001730c  test    eax, eax
0x18001730e  js      loc_18001750B
0x180017314  mov     r8d, dword ptr [rsp+180h+Size]; Size
0x180017319  mov     rdx, r15; Buf2
0x18001731c  mov     rcx, [rbp+80h+Buf1]; Buf1
0x180017320  call    memcmp_0
0x180017325  xor     ecx, ecx
0x180017327  test    eax, eax
0x180017329  jz      short loc_180017334
0x18001732b  mov     ebx, edi
0x18001732d  mov     edi, ecx
0x18001732f  jmp     loc_180017510
0x180017334  mov     r14, rcx
0x180017337  mov     [rbp+80h+hHash], rcx
0x18001733b  mov     rsi, rcx
0x18001733e  mov     dword ptr [rsp+180h+Size+4], ecx
0x180017342  mov     r12d, ecx
0x180017345  mov     dword ptr [rsp+180h+Size], ecx
0x180017349  mov     [rsp+180h+var_130], ecx
0x18001734d  mov     [rsp+180h+var_128], rcx
0x180017352  cmp     [rsp+180h+cbSecret], ecx
0x180017356  jnz     short loc_18001735F
0x180017358  mov     ebx, edi
0x18001735a  jmp     loc_180017494
0x18001735f  mov     [rsp+180h+dwFlags], ecx; dwFlags
0x180017363  lea     rax, [rsp+180h+var_130]
0x180017368  mov     rcx, r13; hObject
0x18001736b  mov     [rsp+180h+pcbResult], rax; pcbResult
0x180017370  mov     r9d, 4; cbOutput
0x180017376  lea     r8, [rsp+180h+Size+4]; pbOutput
0x18001737b  lea     rdx, pszProperty; "ObjectLength"
0x180017382  call    cs:__imp_BCryptGetProperty
0x180017388  mov     ebx, eax
0x18001738a  test    eax, eax
0x18001738c  js      loc_180017485
0x180017392  cmp     [rsp+180h+var_130], 4
0x180017397  jz      short loc_1800173A0
0x180017399  mov     ebx, edi
0x18001739b  jmp     loc_180017485
0x1800173a0  mov     edx, dword ptr [rsp+180h+Size+4]; uBytes
0x1800173a4  mov     ecx, 40h ; '@'; uFlags
0x1800173a9  call    cs:__imp_LocalAlloc
0x1800173af  mov     r14, rax
0x1800173b2  test    rax, rax
0x1800173b5  jnz     short loc_1800173C1
0x1800173b7  mov     ebx, 0C000009Ah
0x1800173bc  jmp     loc_180017485
0x1800173c1  lea     rax, [rsp+180h+var_130]
0x1800173c6  mov     [rsp+180h+dwFlags], esi; dwFlags
0x1800173ca  mov     r9d, 4; cbOutput
0x1800173d0  mov     [rsp+180h+pcbResult], rax; pcbResult
0x1800173d5  lea     r8, [rsp+180h+Size]; pbOutput
0x1800173da  mov     rcx, r13; hObject
0x1800173dd  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800173e4  call    cs:__imp_BCryptGetProperty
0x1800173ea  mov     ebx, eax
0x1800173ec  test    eax, eax
0x1800173ee  js      loc_180017485
0x1800173f4  cmp     [rsp+180h+var_130], 4
0x1800173f9  jnz     short loc_180017399
0x1800173fb  mov     edx, dword ptr [rsp+180h+Size]; uBytes
0x1800173ff  mov     ecx, 40h ; '@'; uFlags
0x180017404  call    cs:__imp_LocalAlloc
0x18001740a  mov     rsi, rax
0x18001740d  test    rax, rax
0x180017410  jz      short loc_1800173B7
0x180017412  mov     eax, [rsp+180h+cbSecret]
0x180017416  lea     rdx, [rbp+80h+hHash]; phHash
0x18001741a  mov     r9d, dword ptr [rsp+180h+Size+4]; cbHashObject
0x18001741f  mov     r8, r14; pbHashObject
0x180017422  mov     [rsp+180h+var_150], r12d; dwFlags
0x180017427  mov     rcx, r13; hAlgorithm
0x18001742a  mov     [rsp+180h+dwFlags], eax; cbSecret
0x18001742e  mov     rax, [rbp+80h+pbSecret]
0x180017432  mov     [rsp+180h+pcbResult], rax; pbSecret
0x180017437  call    cs:__imp_BCryptCreateHash
0x18001743d  mov     ebx, eax
0x18001743f  test    eax, eax
0x180017441  js      short loc_180017485
0x180017443  mov     rcx, [rbp+80h+hHash]; hHash
0x180017447  lea     rdx, [rbp+80h+var_88]; pbInput
0x18001744b  xor     r9d, r9d; dwFlags
0x18001744e  lea     r8d, [r9+3Eh]; cbInput
0x180017452  call    cs:__imp_BCryptHashData
0x180017458  mov     ebx, eax
0x18001745a  test    eax, eax
0x18001745c  js      short loc_180017485
0x18001745e  mov     r8d, dword ptr [rsp+180h+Size]; cbOutput
0x180017463  xor     r9d, r9d; dwFlags
0x180017466  mov     rcx, [rbp+80h+hHash]; hHash
0x18001746a  mov     rdx, rsi; pbOutput
0x18001746d  call    cs:__imp_BCryptFinishHash
0x180017473  mov     ebx, eax
0x180017475  test    eax, eax
0x180017477  js      short loc_180017485
0x180017479  mov     r12d, dword ptr [rsp+180h+Size]
0x18001747e  mov     [rsp+180h+var_128], rsi
0x180017483  xor     esi, esi
0x180017485  mov     rcx, [rbp+80h+hHash]; hHash
0x180017489  test    rcx, rcx
0x18001748c  jz      short loc_180017494
0x18001748e  call    cs:__imp_BCryptDestroyHash
0x180017494  mov     rcx, r14; hMem
0x180017497  call    cs:__imp_LocalFree
0x18001749d  mov     rcx, rsi; hMem
0x1800174a0  call    cs:__imp_LocalFree
0x1800174a6  mov     rdi, [rsp+180h+var_128]
0x1800174ab  test    ebx, ebx
0x1800174ad  js      short loc_180017510
0x1800174af  mov     edx, [r15+50h]; cbInput
0x1800174b3  lea     rax, [rsp+180h+var_110]
0x1800174b8  mov     rcx, [r15+58h]; pbInput
0x1800174bc  lea     r8, [r15+40h]; pbIV
0x1800174c0  mov     [rsp+180h+var_148], rax; unsigned int *
0x1800174c5  lea     rax, [rbp+80h+var_F0]
0x1800174c9  mov     qword ptr [rsp+180h+var_150], rax; unsigned __int8 **
  ... truncated ...
```
