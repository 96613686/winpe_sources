# aesInitializeCommon

- ea: `0x1800017c0`
- end: `0x180001b86`
- name: `aesInitializeCommon`
- size: `966`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005fc0`

## callees

- `0x1800017c0`
- `0x180002240`
- `0x1800022c0`
- `0x180004c40`
- `0x1800054be`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800019ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001aed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800019ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180001aed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800018aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800019f2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800018aa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800019f2`
- `bcrypt!BCryptEncrypt` at `0x180001970`
- `bcrypt!BCryptEncrypt` at `0x180001ab3`
- `bcrypt!BCryptEncrypt` at `0x180001970`
- `bcrypt!BCryptEncrypt` at `0x180001ab3`
- `bcrypt!BCryptDestroyKey` at `0x1800019a0`
- `bcrypt!BCryptDestroyKey` at `0x180001adf`
- `bcrypt!BCryptDestroyKey` at `0x1800019a0`
- `bcrypt!BCryptDestroyKey` at `0x180001adf`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800018df`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180001a27`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180001b26`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1800018df`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180001a27`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x180001b26`

## pseudocode

```c
NTSTATUS __fastcall aesInitializeCommon(unsigned int a1, UCHAR *a2, unsigned int a3, int a4, int a5, __int64 a6)
{
  __int64 v6; // r15
  size_t cbSecret; // rbx
  UCHAR *pbSecret; // r14
  __int64 v9; // r12
  int v10; // eax
  __int64 *v11; // rdx
  UCHAR *v12; // rdi
  NTSTATUS v13; // esi
  UCHAR *v14; // rax
  UCHAR *v15; // r12
  int v16; // r14d
  __int128 v17; // xmm0
  BCRYPT_KEY_HANDLE v18; // rcx
  UCHAR *v19; // r13
  char *v20; // r12
  UCHAR *v21; // rdi
  UCHAR *v22; // rax
  int v23; // r14d
  UCHAR *v24; // r15
  __int128 v25; // xmm0
  BCRYPT_KEY_HANDLE v26; // rcx
  UCHAR *v27; // r13
  UCHAR *v28; // r8
  _BYTE v30[4]; // [rsp+50h] [rbp-69h] BYREF
  char v31; // [rsp+54h] [rbp-65h]
  ULONG pcbResult; // [rsp+58h] [rbp-61h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v34; // [rsp+68h] [rbp-51h]
  UCHAR *v35; // [rsp+70h] [rbp-49h]
  __int64 v36; // [rsp+78h] [rbp-41h]
  UCHAR v37[16]; // [rsp+80h] [rbp-39h] BYREF
  UCHAR pbIV[16]; // [rsp+90h] [rbp-29h] BYREF
  UCHAR v39[32]; // [rsp+A0h] [rbp-19h] BYREF

  v6 = a6;
  cbSecret = a3;
  pbSecret = a2;
  v9 = a1;
  *(_DWORD *)(a6 + 20) = a3;
  *(_DWORD *)(a6 + 16) = a4;
  v35 = a2;
  v34 = a1;
  v36 = a6;
  *(_OWORD *)(a6 + 40) = 0;
  if ( !a5 )
    return -1073741811;
  v10 = cCheckSums;
  do
  {
    if ( !v10 )
      return -2146958526;
    v11 = &CheckSumFns[8 * (unsigned __int64)(unsigned int)--v10];
  }
  while ( *(_DWORD *)v11 != a5 );
  v30[0] = HIBYTE(a4);
  v30[1] = BYTE2(a4);
  *(_QWORD *)a6 = v11;
  v30[2] = BYTE1(a4);
  v30[3] = a4;
  v31 = -86;
  fold_40_to_128(v30, v37);
  phKey = 0;
  v12 = 0;
  v13 = CheckCNG();
  if ( v13 >= 0 )
  {
    v14 = (UCHAR *)LocalAlloc(0, (unsigned int)cshAesKeyObjectSize);
    v12 = v14;
    if ( v14 )
    {
      v13 = BCryptGenerateSymmetricKey(cshAesAlgHandle, &phKey, v14, cshAesKeyObjectSize, pbSecret, cbSecret, 0);
      if ( v13 >= 0 )
      {
        v15 = v37;
        memset_0(v39, 0, cbSecret);
        v16 = 0;
        if ( (_DWORD)cbSecret )
        {
          do
          {
            v17 = *(_OWORD *)v15;
            v18 = phKey;
            v19 = &v39[16 * v16];
            pcbResult = 16;
            *(_OWORD *)v19 = v17;
            *(_OWORD *)pbIV = 0;
            v13 = BCryptEncrypt(v18, v19, 0x10u, 0, pbIV, 0x10u, v19, 0x10u, &pcbResult, 0);
            if ( v13 < 0 )
              break;
            ++v16;
            v15 = v19;
          }
          while ( 16 * v16 < (unsigned int)cbSecret );
        }
        v9 = v34;
        pbSecret = v35;
      }
    }
    else
    {
      v13 = -1073741801;
    }
  }
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( v12 )
    LocalFree(v12);
  if ( v13 < 0 )
    return v13;
  v31 = 85;
  fold_40_to_128(v30, v37);
  v20 = (char *)(a6 + v9);
  phKey = 0;
  *(_QWORD *)(a6 + 24) = v20;
  v21 = 0;
  v13 = CheckCNG();
  if ( v13 >= 0 )
  {
    v22 = (UCHAR *)LocalAlloc(0, (unsigned int)cshAesKeyObjectSize);
    v21 = v22;
    if ( v22 )
    {
      v13 = BCryptGenerateSymmetricKey(cshAesAlgHandle, &phKey, v22, cshAesKeyObjectSize, pbSecret, cbSecret, 0);
      if ( v13 >= 0 )
      {
        memset_0(v20, 0, cbSecret);
        v23 = 0;
        if ( (_DWORD)cbSecret )
        {
          v24 = v37;
          do
          {
            v25 = *(_OWORD *)v24;
            v26 = phKey;
            v27 = (UCHAR *)&v20[16 * v23];
            pcbResult = 16;
            *(_OWORD *)pbIV = 0;
            *(_OWORD *)v27 = v25;
            v13 = BCryptEncrypt(v26, v27, 0x10u, 0, pbIV, 0x10u, v27, 0x10u, &pcbResult, 0);
            if ( v13 < 0 )
              break;
            ++v23;
            v24 = v27;
          }
          while ( 16 * v23 < (unsigned int)cbSecret );
          v6 = v36;
        }
      }
    }
    else
    {
      v13 = -1073741801;
    }
  }
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( v21 )
    LocalFree(v21);
  if ( v13 < 0 )
    return v13;
  v28 = (UCHAR *)(*(_QWORD *)(v6 + 24) + cbSecret);
  *(_QWORD *)(v6 + 32) = v28;
  return BCryptGenerateSymmetricKey(
           cshAesAlgHandle,
           (BCRYPT_KEY_HANDLE *)(v6 + 8),
           v28,
           cshAesKeyObjectSize,
           v39,
           cbSecret,
           0);
}

```

## disassembly

```asm
0x1800017c0  push    rbp
0x1800017c2  push    rbx
0x1800017c3  push    r12
0x1800017c5  push    r14
0x1800017c7  push    r15
0x1800017c9  lea     rbp, [rsp-27h]
0x1800017ce  sub     rsp, 0E0h
0x1800017d5  mov     rax, cs:__security_cookie
0x1800017dc  xor     rax, rsp
0x1800017df  mov     [rbp+47h+var_40], rax
0x1800017e3  mov     r15, [rbp+47h+arg_28]
0x1800017e7  xorps   xmm0, xmm0
0x1800017ea  mov     ebx, r8d
0x1800017ed  mov     r14, rdx
0x1800017f0  mov     r8d, [rbp+47h+arg_20]
0x1800017f4  mov     r12d, ecx
0x1800017f7  mov     [r15+14h], ebx
0x1800017fb  mov     [r15+10h], r9d
0x1800017ff  mov     [rbp+47h+var_90], rdx
0x180001803  mov     [rbp+47h+var_98], r12d
0x180001807  mov     [rbp+47h+var_88], r15
0x18000180b  movups  xmmword ptr [r15+28h], xmm0
0x180001810  test    r8d, r8d
0x180001813  jz      loc_180001B6B
0x180001819  mov     eax, cs:cCheckSums
0x18000181f  lea     r10, CheckSumFns
0x180001826  test    eax, eax
0x180001828  jz      loc_180001B60
0x18000182e  dec     eax
0x180001830  mov     edx, eax
0x180001832  shl     rdx, 6
0x180001836  add     rdx, r10
0x180001839  cmp     [rdx], r8d
0x18000183c  jnz     short loc_180001826
0x18000183e  mov     eax, r9d
0x180001841  mov     [rsp+100h+arg_0], rsi
0x180001849  shr     eax, 18h
0x18000184c  lea     rcx, [rbp+47h+var_B0]
0x180001850  mov     [rbp+47h+var_B0], al
0x180001853  mov     eax, r9d
0x180001856  shr     eax, 10h
0x180001859  mov     [rbp+47h+var_AF], al
0x18000185c  mov     eax, r9d
0x18000185f  shr     eax, 8
0x180001862  mov     [r15], rdx
0x180001865  lea     rdx, [rbp+47h+var_80]
0x180001869  mov     [rsp+100h+var_28], rdi
0x180001871  mov     [rbp+47h+var_AE], al
0x180001874  mov     [rsp+100h+var_30], r13
0x18000187c  mov     [rbp+47h+var_AD], r9b
0x180001880  mov     [rbp+47h+var_AC], 0AAh
0x180001884  call    fold_40_to_128
0x180001889  xor     r13d, r13d
0x18000188c  mov     [rbp+47h+phKey], r13
0x180001890  mov     edi, r13d
0x180001893  call    CheckCNG
0x180001898  mov     esi, eax
0x18000189a  test    eax, eax
0x18000189c  js      loc_180001997
0x1800018a2  mov     edx, cs:cshAesKeyObjectSize; uBytes
0x1800018a8  xor     ecx, ecx; uFlags
0x1800018aa  call    cs:__imp_LocalAlloc
0x1800018b0  mov     rdi, rax
0x1800018b3  test    rax, rax
0x1800018b6  jz      loc_180001B72
0x1800018bc  mov     r9d, cs:cshAesKeyObjectSize; cbKeyObject
0x1800018c3  lea     rdx, [rbp+47h+phKey]; phKey
0x1800018c7  mov     rcx, cs:cshAesAlgHandle; hAlgorithm
0x1800018ce  mov     r8, rax; pbKeyObject
0x1800018d1  mov     [rsp+100h+dwFlags], r13d; dwFlags
0x1800018d6  mov     [rsp+100h+cbSecret], ebx; cbSecret
0x1800018da  mov     [rsp+100h+pbSecret], r14; pbSecret
0x1800018df  call    cs:__imp_BCryptGenerateSymmetricKey
0x1800018e5  mov     esi, eax
0x1800018e7  test    eax, eax
0x1800018e9  js      loc_180001997
0x1800018ef  mov     r8, rbx; Size
0x1800018f2  lea     rcx, [rbp+47h+var_60]; void *
0x1800018f6  xor     edx, edx; Val
0x1800018f8  lea     r12, [rbp+47h+var_80]
0x1800018fc  call    memset_0
0x180001901  mov     r14d, r13d
0x180001904  test    ebx, ebx
0x180001906  jz      loc_18000198F
0x18000190c  movups  xmm0, xmmword ptr [r12]
0x180001911  mov     rcx, [rbp+47h+phKey]; hKey
0x180001915  lea     r13, [rbp+47h+var_60]
0x180001919  mov     [rsp+100h+var_B8], 0; dwFlags
0x180001921  mov     eax, r14d
0x180001924  shl     eax, 4
0x180001927  xorps   xmm1, xmm1
0x18000192a  add     r13, rax
0x18000192d  mov     [rbp+47h+var_A8], 10h
0x180001934  lea     rax, [rbp+47h+var_A8]
0x180001938  xor     r9d, r9d; pPaddingInfo
0x18000193b  mov     [rsp+100h+pcbResult], rax; pcbResult
0x180001940  mov     r8d, 10h; cbInput
0x180001946  mov     [rsp+100h+cbOutput], 10h; cbOutput
0x18000194e  lea     rax, [rbp+47h+pbIV]
0x180001952  mov     qword ptr [rsp+100h+dwFlags], r13; pbOutput
0x180001957  mov     rdx, r13; pbInput
0x18000195a  mov     [rsp+100h+cbSecret], 10h; cbIV
0x180001962  mov     [rsp+100h+pbSecret], rax; pbIV
0x180001967  movups  xmmword ptr [r13+0], xmm0
0x18000196c  movups  xmmword ptr [rbp+47h+pbIV], xmm1
0x180001970  call    cs:__imp_BCryptEncrypt
0x180001976  mov     esi, eax
0x180001978  test    eax, eax
0x18000197a  js      short loc_18000198C
0x18000197c  inc     r14d
0x18000197f  mov     r12, r13
0x180001982  mov     eax, r14d
0x180001985  shl     eax, 4
0x180001988  cmp     eax, ebx
0x18000198a  jb      short loc_18000190C
0x18000198c  xor     r13d, r13d
0x18000198f  mov     r12d, [rbp+47h+var_98]
0x180001993  mov     r14, [rbp+47h+var_90]
0x180001997  mov     rcx, [rbp+47h+phKey]; hKey
0x18000199b  test    rcx, rcx
0x18000199e  jz      short loc_1800019A6
0x1800019a0  call    cs:__imp_BCryptDestroyKey
0x1800019a6  test    rdi, rdi
0x1800019a9  jz      short loc_1800019B4
0x1800019ab  mov     rcx, rdi; hMem
0x1800019ae  call    cs:__imp_LocalFree
0x1800019b4  test    esi, esi
0x1800019b6  js      loc_180001B67
0x1800019bc  lea     rdx, [rbp+47h+var_80]
0x1800019c0  mov     [rbp+47h+var_AC], 55h ; 'U'
0x1800019c4  lea     rcx, [rbp+47h+var_B0]
0x1800019c8  call    fold_40_to_128
0x1800019cd  add     r12, r15
0x1800019d0  mov     [rbp+47h+phKey], r13
0x1800019d4  mov     [r15+18h], r12
0x1800019d8  mov     rdi, r13
0x1800019db  call    CheckCNG
0x1800019e0  mov     esi, eax
0x1800019e2  test    eax, eax
0x1800019e4  js      loc_180001AD6
0x1800019ea  mov     edx, cs:cshAesKeyObjectSize; uBytes
0x1800019f0  xor     ecx, ecx; uFlags
0x1800019f2  call    cs:__imp_LocalAlloc
0x1800019f8  mov     rdi, rax
0x1800019fb  test    rax, rax
0x1800019fe  jz      loc_180001B7C
0x180001a04  mov     r9d, cs:cshAesKeyObjectSize; cbKeyObject
0x180001a0b  lea     rdx, [rbp+47h+phKey]; phKey
0x180001a0f  mov     rcx, cs:cshAesAlgHandle; hAlgorithm
0x180001a16  mov     r8, rax; pbKeyObject
0x180001a19  mov     [rsp+100h+dwFlags], r13d; dwFlags
0x180001a1e  mov     [rsp+100h+cbSecret], ebx; cbSecret
0x180001a22  mov     [rsp+100h+pbSecret], r14; pbSecret
0x180001a27  call    cs:__imp_BCryptGenerateSymmetricKey
0x180001a2d  mov     esi, eax
0x180001a2f  test    eax, eax
0x180001a31  js      loc_180001AD6
0x180001a37  mov     r8, rbx; Size
0x180001a3a  xor     edx, edx; Val
0x180001a3c  mov     rcx, r12; void *
0x180001a3f  call    memset_0
0x180001a44  mov     r14d, r13d
0x180001a47  test    ebx, ebx
0x180001a49  jz      loc_180001AD6
0x180001a4f  lea     r15, [rbp+47h+var_80]
0x180001a53  movups  xmm0, xmmword ptr [r15]
0x180001a57  mov     rcx, [rbp+47h+phKey]; hKey
0x180001a5b  lea     rax, [rbp+47h+var_A8]
0x180001a5f  mov     [rsp+100h+var_B8], 0; dwFlags
0x180001a67  mov     r13d, r14d
0x180001a6a  mov     [rsp+100h+pcbResult], rax; pcbResult
0x180001a6f  xorps   xmm1, xmm1
0x180001a72  mov     [rsp+100h+cbOutput], 10h; cbOutput
0x180001a7a  lea     rax, [rbp+47h+pbIV]
0x180001a7e  shl     r13d, 4
0x180001a82  xor     r9d, r9d; pPaddingInfo
0x180001a85  add     r13, r12
0x180001a88  mov     [rbp+47h+var_A8], 10h
0x180001a8f  mov     qword ptr [rsp+100h+dwFlags], r13; pbOutput
0x180001a94  mov     r8d, 10h; cbInput
0x180001a9a  mov     [rsp+100h+cbSecret], 10h; cbIV
0x180001aa2  mov     rdx, r13; pbInput
0x180001aa5  movups  xmmword ptr [rbp+47h+pbIV], xmm1
0x180001aa9  mov     [rsp+100h+pbSecret], rax; pbIV
0x180001aae  movups  xmmword ptr [r13+0], xmm0
0x180001ab3  call    cs:__imp_BCryptEncrypt
0x180001ab9  mov     esi, eax
0x180001abb  test    eax, eax
0x180001abd  js      short loc_180001ACF
0x180001abf  inc     r14d
0x180001ac2  mov     r15, r13
0x180001ac5  mov     eax, r14d
0x180001ac8  shl     eax, 4
0x180001acb  cmp     eax, ebx
0x180001acd  jb      short loc_180001A53
0x180001acf  mov     r15, [rbp+47h+var_88]
0x180001ad3  xor     r13d, r13d
0x180001ad6  mov     rcx, [rbp+47h+phKey]; hKey
0x180001ada  test    rcx, rcx
0x180001add  jz      short loc_180001AE5
0x180001adf  call    cs:__imp_BCryptDestroyKey
0x180001ae5  test    rdi, rdi
0x180001ae8  jz      short loc_180001AF3
0x180001aea  mov     rcx, rdi; hMem
0x180001aed  call    cs:__imp_LocalFree
0x180001af3  test    esi, esi
0x180001af5  js      short loc_180001B67
0x180001af7  mov     [rsp+100h+dwFlags], r13d; dwFlags
0x180001afc  lea     rax, [rbp+47h+var_60]
0x180001b00  mov     r8, rbx
0x180001b03  mov     [rsp+100h+cbSecret], ebx; cbSecret
0x180001b07  add     r8, [r15+18h]; pbKeyObject
0x180001b0b  lea     rdx, [r15+8]; phKey
0x180001b0f  mov     [r15+20h], r8
0x180001b13  mov     r9d, cs:cshAesKeyObjectSize; cbKeyObject
0x180001b1a  mov     rcx, cs:cshAesAlgHandle; hAlgorithm
0x180001b21  mov     [rsp+100h+pbSecret], rax; pbSecret
0x180001b26  call    cs:__imp_BCryptGenerateSymmetricKey
0x180001b2c  mov     rdi, [rsp+100h+var_28]
0x180001b34  mov     rsi, [rsp+100h+arg_0]
0x180001b3c  mov     r13, [rsp+100h+var_30]
0x180001b44  mov     rcx, [rbp+47h+var_40]
0x180001b48  xor     rcx, rsp; StackCookie
0x180001b4b  call    __security_check_cookie
0x180001b50  add     rsp, 0E0h
0x180001b57  pop     r15
0x180001b59  pop     r14
0x180001b5b  pop     r12
0x180001b5d  pop     rbx
0x180001b5e  pop     rbp
0x180001b5f  retn
0x180001b60  mov     eax, 80080342h
0x180001b65  jmp     short loc_180001B44
0x180001b67  mov     eax, esi
0x180001b69  jmp     short loc_180001B2C
0x180001b6b  mov     eax, 0C000000Dh
0x180001b70  jmp     short loc_180001B44
0x180001b72  mov     esi, 0C0000017h
0x180001b77  jmp     loc_180001997
0x180001b7c  mov     esi, 0C0000017h
0x180001b81  jmp     loc_180001AD6
```
