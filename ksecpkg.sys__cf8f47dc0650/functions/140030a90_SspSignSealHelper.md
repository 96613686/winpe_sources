# SspSignSealHelper

- ea: `0x140030a90`
- end: `0x1400310fa`
- name: `SspSignSealHelper`
- size: `1642`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140026220`
- `0x140028320`
- `0x1400283e0`
- `0x1400284d0`

## callees

- `0x14000879c`
- `0x140010160`
- `0x1400262d0`
- `0x140030020`
- `0x140030a90`

## import_xrefs

- `cng!BCryptEncrypt` at `0x14003100d`
- `cng!BCryptEncrypt` at `0x14003100d`
- `cng!BCryptDuplicateKey` at `0x140030fc1`
- `cng!BCryptDuplicateKey` at `0x140030fc1`
- `cng!BCryptDestroyKey` at `0x140031024`
- `cng!BCryptDestroyKey` at `0x140031024`
- `cng!BCryptCreateHash` at `0x140030c2d`
- `cng!BCryptCreateHash` at `0x140030c95`
- `cng!BCryptCreateHash` at `0x140030c2d`
- `cng!BCryptCreateHash` at `0x140030c95`
- `cng!BCryptHashData` at `0x140030cbf`
- `cng!BCryptHashData` at `0x140030cea`
- `cng!BCryptHashData` at `0x140030d75`
- `cng!BCryptHashData` at `0x140030e09`
- `cng!BCryptHashData` at `0x140030cbf`
- `cng!BCryptHashData` at `0x140030cea`
- `cng!BCryptHashData` at `0x140030d75`
- `cng!BCryptHashData` at `0x140030e09`
- `cng!BCryptDestroyHash` at `0x140030d33`
- `cng!BCryptDestroyHash` at `0x1400310a3`
- `cng!BCryptDestroyHash` at `0x1400310b8`
- `cng!BCryptDestroyHash` at `0x140030d33`
- `cng!BCryptDestroyHash` at `0x1400310a3`
- `cng!BCryptDestroyHash` at `0x1400310b8`
- `cng!BCryptFinishHash` at `0x140030d15`
- `cng!BCryptFinishHash` at `0x140030e6b`
- `cng!BCryptFinishHash` at `0x140030d15`
- `cng!BCryptFinishHash` at `0x140030e6b`

## pseudocode

```c
__int64 __fastcall SspSignSealHelper(__int64 a1, unsigned int a2, __int64 a3, int a4, _OWORD *a5, _QWORD *a6)
{
  unsigned int v7; // r8d
  __int64 v10; // rdx
  unsigned int v11; // ecx
  __int64 result; // rax
  __int64 v13; // rax
  __int64 v14; // r8
  int v15; // edx
  _DWORD *v16; // r12
  UCHAR *v17; // rbx
  BCRYPT_KEY_HANDLE *v18; // r13
  UCHAR *pbSecret; // rsi
  int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // rcx
  unsigned int v23; // esi
  __int64 v24; // r9
  int v25; // eax
  __int64 v26; // r8
  unsigned int v27; // eax
  __int64 v28; // r8
  bool v29; // zf
  unsigned int i; // esi
  __int64 v31; // r9
  int v32; // ecx
  __int64 v33; // r8
  __int64 v34; // r8
  int v35; // eax
  BCRYPT_KEY_HANDLE v36; // rcx
  NTSTATUS v37; // ebx
  NTSTATUS v38; // eax
  BCRYPT_HASH_HANDLE hHash; // [rsp+50h] [rbp-69h] BYREF
  int v40; // [rsp+58h] [rbp-61h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+60h] [rbp-59h] BYREF
  ULONG pcbResult; // [rsp+68h] [rbp-51h] BYREF
  int v43; // [rsp+6Ch] [rbp-4Dh]
  int v44; // [rsp+70h] [rbp-49h]
  BCRYPT_KEY_HANDLE phNewKey; // [rsp+78h] [rbp-41h] BYREF
  __int64 v46; // [rsp+80h] [rbp-39h]
  _OWORD *v47; // [rsp+88h] [rbp-31h]
  UCHAR pbInput[16]; // [rsp+90h] [rbp-29h] BYREF
  UCHAR pbOutput[16]; // [rsp+A0h] [rbp-19h] BYREF
  UCHAR v50[16]; // [rsp+B0h] [rbp-9h] BYREF

  v7 = *(_DWORD *)(a3 + 4);
  v40 = a4;
  v47 = a5;
  hHash = 0;
  phHash = 0;
  *(_OWORD *)pbInput = 0;
  *(_OWORD *)pbOutput = 0;
  if ( !v7 )
    return 2148074248LL;
  v10 = *(_QWORD *)(a3 + 8);
  v11 = 0;
  while ( (unsigned __int8)*(_DWORD *)(v10 + 16LL * v11 + 4) != 2 )
  {
    if ( ++v11 >= v7 )
      return 2148074248LL;
  }
  if ( v11 == -1 )
    return 2148074248LL;
  v13 = 16LL * (int)v11;
  v46 = v13;
  if ( *(_DWORD *)(v10 + v13) < 0x10u )
    return 2148074248LL;
  v14 = *(_QWORD *)(v10 + v13 + 8);
  *a6 = v14;
  v15 = *(_DWORD *)(a1 + 48);
  if ( (v15 & 0x10) == 0 && a2 <= 1 )
  {
    result = 0;
    *a5 = 0;
    *(_DWORD *)a5 = 1;
    return result;
  }
  if ( (v15 & 0x20) == 0 && a2 - 2 <= 1 )
    return 2148074242LL;
  if ( a2 )
  {
    if ( a2 == 1 )
    {
LABEL_20:
      v16 = *(_DWORD **)(a1 + 80);
      v17 = (UCHAR *)(a1 + 244);
      v18 = *(BCRYPT_KEY_HANDLE **)(a1 + 96);
      pbSecret = (UCHAR *)(a1 + 212);
      goto LABEL_22;
    }
    if ( a2 != 2 )
    {
      if ( a2 != 3 )
        return 3221225800LL;
      goto LABEL_20;
    }
  }
  v16 = *(_DWORD **)(a1 + 72);
  v17 = (UCHAR *)(a1 + 228);
  v18 = *(BCRYPT_KEY_HANDLE **)(a1 + 88);
  pbSecret = (UCHAR *)(a1 + 196);
LABEL_22:
  v44 = *(_DWORD *)(v14 + 4);
  v20 = *(_DWORD *)(v14 + 12);
  v43 = v20;
  *(_DWORD *)pbInput = 1;
  if ( (v15 & 0x80000) == 0 )
  {
    *(_DWORD *)&pbInput[8] = -1;
    for ( i = 0; i < *(_DWORD *)(a3 + 4); ++i )
    {
      v31 = *(_QWORD *)(a3 + 8);
      v32 = *(_DWORD *)(v31 + 16LL * i + 4);
      if ( (_BYTE)v32 == 1 )
      {
        v33 = *(unsigned int *)(v31 + 16LL * i);
        if ( (_DWORD)v33 )
        {
          if ( (v32 & 0x90000000) == 0x90000000 )
          {
LABEL_59:
            v21 = -2146893048;
            goto LABEL_92;
          }
          if ( v32 >= 0 )
          {
            if ( a2 == 3
              && (v32 & 0x10000000) == 0
              && (int)SspEncryptBuffer(a1, v18, v33, *(_QWORD *)(v31 + 16LL * i + 8)) < 0 )
            {
              goto LABEL_34;
            }
            Crc32(
              *(unsigned int *)&pbInput[8],
              *(unsigned int *)(*(_QWORD *)(a3 + 8) + 16LL * i),
              *(_QWORD *)(*(_QWORD *)(a3 + 8) + 16LL * i + 8),
              &pbInput[8]);
            if ( a2 == 2 )
            {
              v34 = *(_QWORD *)(a3 + 8);
              if ( (*(_DWORD *)(v34 + 16LL * i + 4) & 0x10000000) == 0
                && (int)SspEncryptBuffer(a1, v18, *(unsigned int *)(v34 + 16LL * i), *(_QWORD *)(v34 + 16LL * i + 8)) < 0 )
              {
                goto LABEL_34;
              }
            }
          }
        }
      }
    }
    v35 = *(_DWORD *)(a1 + 48);
    *(_DWORD *)&pbInput[8] = ~*(_DWORD *)&pbInput[8];
    *(_DWORD *)&pbInput[12] = 0;
    v36 = *v18;
    phNewKey = 0;
    pcbResult = 0;
    if ( (v35 & 0x80040) == 0x40 )
    {
      v37 = BCryptDuplicateKey(v36, &phNewKey, 0, 0, 0);
      if ( v37 < 0 )
        goto LABEL_79;
      v36 = phNewKey;
    }
    v37 = BCryptEncrypt(v36, &pbInput[4], 0xCu, 0, 0, 0, &pbInput[4], 0xCu, &pcbResult, 0);
LABEL_79:
    if ( phNewKey )
    {
      v38 = BCryptDestroyKey(phNewKey);
      if ( v37 < 0 )
        goto LABEL_34;
      v37 = v38;
    }
    if ( v37 < 0 )
    {
      v21 = -2146893052;
      goto LABEL_92;
    }
    if ( (*(_DWORD *)(a1 + 48) & 0x40) != 0 )
    {
      if ( (a2 & 0xFFFFFFFD) == 0 || v40 )
        *(_DWORD *)&pbInput[12] ^= v40;
      else
        *(_DWORD *)&pbInput[12] = v43;
    }
    else
    {
      *(_DWORD *)&pbInput[12] ^= (*v16)++;
    }
    *(_DWORD *)&pbInput[4] = v44;
LABEL_91:
    v21 = 0;
    *(_DWORD *)(v46 + *(_QWORD *)(a3 + 8)) = 16;
    *v47 = *(_OWORD *)pbInput;
    goto LABEL_92;
  }
  if ( (v15 & 0x40) == 0 )
  {
    *(_DWORD *)&pbInput[12] = (*v16)++;
    goto LABEL_25;
  }
  if ( (a2 & 0xFFFFFFFD) != 0 && !a4 )
  {
    *(_DWORD *)&pbInput[12] = v20;
LABEL_31:
    if ( a2 != 3 && (v15 & 0x40000000) == 0 )
      goto LABEL_25;
    goto LABEL_33;
  }
  *(_DWORD *)&pbInput[12] = a4;
  if ( a2 != 2 )
    goto LABEL_31;
LABEL_33:
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, &hHash, 0, 0, 0, 0, 0) < 0 )
  {
LABEL_34:
    v21 = -2146893052;
    goto LABEL_92;
  }
  if ( BCryptHashData(hHash, v17, 0x10u, 0) < 0 )
  {
    v21 = -2146893052;
    goto LABEL_92;
  }
  if ( BCryptHashData(hHash, &pbInput[12], 4u, 0) < 0 )
  {
    v21 = -2146893052;
    goto LABEL_92;
  }
  if ( BCryptFinishHash(hHash, pbOutput, 0x10u, 0) < 0 )
  {
    v21 = -2146893052;
    goto LABEL_92;
  }
  BCryptDestroyHash(hHash);
  v22 = *(unsigned int *)(a1 + 48);
  hHash = 0;
  if ( (int)SspRc4Key(v22, v18, pbOutput) < 0 )
  {
    v21 = -2146893052;
    goto LABEL_92;
  }
LABEL_25:
  if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x91, &phHash, 0, 0, pbSecret, 0x10u, 0) < 0 )
  {
    v21 = -2146893052;
    goto LABEL_92;
  }
  if ( BCryptHashData(phHash, &pbInput[12], 4u, 0) < 0 )
  {
    v21 = -2146893052;
    goto LABEL_92;
  }
  v23 = 0;
  if ( *(_DWORD *)(a3 + 4) )
  {
    do
    {
      v24 = *(_QWORD *)(a3 + 8);
      v25 = *(_DWORD *)(v24 + 16LL * v23 + 4);
      if ( (_BYTE)v25 == 1 )
      {
        v26 = *(unsigned int *)(v24 + 16LL * v23);
        if ( (_DWORD)v26 )
        {
          v27 = v25 & 0x90000000;
          if ( v27 == -1879048192 )
            goto LABEL_59;
          if ( a2 == 3 && !v27 && (int)SspEncryptBuffer(a1, v18, v26, *(_QWORD *)(v24 + 16LL * v23 + 8)) < 0 )
            goto LABEL_34;
          if ( BCryptHashData(
                 phHash,
                 *(PUCHAR *)(*(_QWORD *)(a3 + 8) + 16LL * v23 + 8),
                 *(_DWORD *)(*(_QWORD *)(a3 + 8) + 16LL * v23),
                 0) < 0 )
            goto LABEL_34;
          if ( a2 == 2 )
          {
            v28 = *(_QWORD *)(a3 + 8);
            if ( (*(_DWORD *)(v28 + 16LL * v23 + 4) & 0x90000000) == 0
              && (int)SspEncryptBuffer(a1, v18, *(unsigned int *)(v28 + 16LL * v23), *(_QWORD *)(v28 + 16LL * v23 + 8)) < 0 )
            {
              goto LABEL_34;
            }
          }
        }
      }
    }
    while ( ++v23 < *(_DWORD *)(a3 + 4) );
  }
  if ( BCryptFinishHash(phHash, v50, 0x10u, 0) < 0 )
  {
    v21 = -2146893052;
    goto LABEL_92;
  }
  v29 = (*(_DWORD *)(a1 + 48) & 0x40000000) == 0;
  *(_QWORD *)&pbInput[4] = *(_QWORD *)v50;
  if ( v29 || (int)SspEncryptBuffer(a1, v18, 8, &pbInput[4]) >= 0 )
    goto LABEL_91;
  v21 = -2146893052;
LABEL_92:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( hHash )
    BCryptDestroyHash(hHash);
  return v21;
}

```

## disassembly

```asm
0x140030a90  push    rbp
0x140030a92  push    rbx
0x140030a93  push    rdi
0x140030a94  push    r14
0x140030a96  push    r15
0x140030a98  lea     rbp, [rsp-27h]
0x140030a9d  sub     rsp, 0E0h
0x140030aa4  mov     rax, cs:__security_cookie
0x140030aab  xor     rax, rsp
0x140030aae  mov     [rbp+47h+var_40], rax
0x140030ab2  mov     r11, [rbp+47h+arg_20]
0x140030ab6  xor     ebx, ebx
0x140030ab8  mov     r10, [rbp+47h+arg_28]
0x140030abc  mov     r14, r8
0x140030abf  mov     r8d, [r8+4]
0x140030ac3  xorps   xmm0, xmm0
0x140030ac6  mov     [rbp+47h+var_A8], r9d
0x140030aca  xorps   xmm1, xmm1
0x140030acd  mov     [rbp+47h+var_78], r11
0x140030ad1  mov     r15d, edx
0x140030ad4  mov     [rbp+47h+hHash], rbx
0x140030ad8  mov     rdi, rcx
0x140030adb  mov     [rbp+47h+phHash], rbx
0x140030adf  movups  xmmword ptr [rbp+47h+pbInput], xmm0
0x140030ae3  movups  xmmword ptr [rbp+47h+pbOutput], xmm1
0x140030ae7  test    r8d, r8d
0x140030aea  jz      short loc_140030B26
0x140030aec  mov     rdx, [r14+8]
0x140030af0  mov     ecx, ebx
0x140030af2  mov     eax, ecx
0x140030af4  add     rax, rax
0x140030af7  mov     eax, [rdx+rax*8+4]
0x140030afb  cmp     al, 2
0x140030afd  jz      short loc_140030B10
0x140030aff  inc     ecx
0x140030b01  cmp     ecx, r8d
0x140030b04  jb      short loc_140030AF2
0x140030b06  mov     eax, 80090308h
0x140030b0b  jmp     loc_1400310DE
0x140030b10  cmp     ecx, 0FFFFFFFFh
0x140030b13  jz      short loc_140030B26
0x140030b15  movsxd  rax, ecx
0x140030b18  shl     rax, 4
0x140030b1c  mov     [rbp+47h+var_80], rax
0x140030b20  cmp     dword ptr [rdx+rax], 10h
0x140030b24  jnb     short loc_140030B30
0x140030b26  mov     eax, 80090308h
0x140030b2b  jmp     loc_1400310DE
0x140030b30  mov     r8, [rdx+rax+8]
0x140030b35  mov     [r10], r8
0x140030b38  mov     edx, [rdi+30h]
0x140030b3b  test    dl, 10h
0x140030b3e  jnz     short loc_140030B5B
0x140030b40  cmp     r15d, 1
0x140030b44  ja      short loc_140030B5B
0x140030b46  xorps   xmm0, xmm0
0x140030b49  mov     eax, ebx
0x140030b4b  movups  xmmword ptr [r11], xmm0
0x140030b4f  mov     dword ptr [r11], 1
0x140030b56  jmp     loc_1400310DE
0x140030b5b  test    dl, 20h
0x140030b5e  jnz     short loc_140030B73
0x140030b60  lea     eax, [r15-2]
0x140030b64  cmp     eax, 1
0x140030b67  ja      short loc_140030B73
0x140030b69  mov     eax, 80090302h
0x140030b6e  jmp     loc_1400310DE
0x140030b73  mov     [rsp+100h+arg_8], rsi
0x140030b7b  mov     ecx, r15d
0x140030b7e  mov     [rsp+100h+var_28], r12
0x140030b86  mov     [rsp+100h+var_30], r13
0x140030b8e  test    r15d, r15d
0x140030b91  jz      short loc_140030BC4
0x140030b93  sub     ecx, 1
0x140030b96  jz      short loc_140030BAC
0x140030b98  sub     ecx, 1
0x140030b9b  jz      short loc_140030BC4
0x140030b9d  cmp     ecx, 1
0x140030ba0  jz      short loc_140030BAC
0x140030ba2  mov     eax, 0C0000148h
0x140030ba7  jmp     loc_1400310C6
0x140030bac  mov     r12, [rdi+50h]
0x140030bb0  lea     rbx, [rdi+0F4h]
0x140030bb7  mov     r13, [rdi+60h]
0x140030bbb  lea     rsi, [rdi+0D4h]
0x140030bc2  jmp     short loc_140030BDA
0x140030bc4  mov     r12, [rdi+48h]
0x140030bc8  lea     rbx, [rdi+0E4h]
0x140030bcf  mov     r13, [rdi+58h]
0x140030bd3  lea     rsi, [rdi+0C4h]
0x140030bda  mov     eax, [r8+4]
0x140030bde  mov     [rbp+47h+var_90], eax
0x140030be1  mov     eax, [r8+0Ch]
0x140030be5  mov     [rbp+47h+var_94], eax
0x140030be8  mov     dword ptr [rbp+47h+pbInput], 1
0x140030bef  bt      edx, 13h
0x140030bf3  jnb     loc_140030ECB
0x140030bf9  test    dl, 40h
0x140030bfc  jnz     short loc_140030C4B
0x140030bfe  mov     eax, [r12]
0x140030c02  mov     dword ptr [rbp+47h+pbInput+0Ch], eax
0x140030c05  inc     dword ptr [r12]
0x140030c09  xor     r12d, r12d
0x140030c0c  mov     [rsp+100h+dwFlags], r12d; dwFlags
0x140030c11  lea     rdx, [rbp+47h+phHash]; phHash
0x140030c15  mov     [rsp+100h+cbSecret], 10h; cbSecret
0x140030c1d  xor     r9d, r9d; cbHashObject
0x140030c20  xor     r8d, r8d; pbHashObject
0x140030c23  mov     [rsp+100h+pbSecret], rsi; pbSecret
0x140030c28  mov     ecx, 91h; hAlgorithm
0x140030c2d  call    cs:__imp_BCryptCreateHash
0x140030c34  nop     dword ptr [rax+rax+00h]
0x140030c39  test    eax, eax
0x140030c3b  jns     loc_140030D64
0x140030c41  mov     ebx, 80090304h
0x140030c46  jmp     loc_14003109A
0x140030c4b  test    r15d, 0FFFFFFFDh
0x140030c52  jz      short loc_140030C5E
0x140030c54  test    r9d, r9d
0x140030c57  jnz     short loc_140030C5E
0x140030c59  mov     dword ptr [rbp+47h+pbInput+0Ch], eax
0x140030c5c  jmp     short loc_140030C68
0x140030c5e  mov     dword ptr [rbp+47h+pbInput+0Ch], r9d
0x140030c62  cmp     r15d, 2
0x140030c66  jz      short loc_140030C74
0x140030c68  cmp     r15d, 3
0x140030c6c  jz      short loc_140030C74
0x140030c6e  bt      edx, 1Eh
0x140030c72  jnb     short loc_140030C09
0x140030c74  xor     r12d, r12d
0x140030c77  lea     rdx, [rbp+47h+hHash]; phHash
0x140030c7b  mov     [rsp+100h+dwFlags], r12d; dwFlags
0x140030c80  xor     r9d, r9d; cbHashObject
0x140030c83  mov     [rsp+100h+cbSecret], r12d; cbSecret
0x140030c88  xor     r8d, r8d; pbHashObject
0x140030c8b  mov     ecx, 21h ; '!'; hAlgorithm
0x140030c90  mov     [rsp+100h+pbSecret], r12; pbSecret
0x140030c95  call    cs:__imp_BCryptCreateHash
0x140030c9c  nop     dword ptr [rax+rax+00h]
0x140030ca1  test    eax, eax
0x140030ca3  jns     short loc_140030CAF
0x140030ca5  mov     ebx, 80090304h
0x140030caa  jmp     loc_14003109A
0x140030caf  mov     rcx, [rbp+47h+hHash]; hHash
0x140030cb3  xor     r9d, r9d; dwFlags
0x140030cb6  mov     r8d, 10h; cbInput
0x140030cbc  mov     rdx, rbx; pbInput
0x140030cbf  call    cs:__imp_BCryptHashData
0x140030cc6  nop     dword ptr [rax+rax+00h]
0x140030ccb  test    eax, eax
0x140030ccd  jns     short loc_140030CD9
0x140030ccf  mov     ebx, 80090304h
0x140030cd4  jmp     loc_14003109A
0x140030cd9  mov     rcx, [rbp+47h+hHash]; hHash
0x140030cdd  lea     rdx, [rbp+47h+pbInput+0Ch]; pbInput
0x140030ce1  xor     r9d, r9d; dwFlags
0x140030ce4  mov     r8d, 4; cbInput
0x140030cea  call    cs:__imp_BCryptHashData
0x140030cf1  nop     dword ptr [rax+rax+00h]
0x140030cf6  test    eax, eax
0x140030cf8  jns     short loc_140030D04
0x140030cfa  mov     ebx, 80090304h
0x140030cff  jmp     loc_14003109A
0x140030d04  mov     rcx, [rbp+47h+hHash]; hHash
0x140030d08  lea     rdx, [rbp+47h+pbOutput]; pbOutput
0x140030d0c  xor     r9d, r9d; dwFlags
0x140030d0f  mov     r8d, 10h; cbOutput
0x140030d15  call    cs:__imp_BCryptFinishHash
0x140030d1c  nop     dword ptr [rax+rax+00h]
0x140030d21  test    eax, eax
0x140030d23  jns     short loc_140030D2F
0x140030d25  mov     ebx, 80090304h
0x140030d2a  jmp     loc_14003109A
0x140030d2f  mov     rcx, [rbp+47h+hHash]; hHash
0x140030d33  call    cs:__imp_BCryptDestroyHash
0x140030d3a  nop     dword ptr [rax+rax+00h]
0x140030d3f  mov     ecx, [rdi+30h]
0x140030d42  lea     r8, [rbp+47h+pbOutput]
0x140030d46  mov     rdx, r13
0x140030d49  mov     [rbp+47h+hHash], r12
0x140030d4d  call    SspRc4Key
0x140030d52  test    eax, eax
0x140030d54  jns     loc_140030C0C
0x140030d5a  mov     ebx, 80090304h
0x140030d5f  jmp     loc_14003109A
0x140030d64  mov     rcx, [rbp+47h+phHash]; hHash
0x140030d68  lea     rdx, [rbp+47h+pbInput+0Ch]; pbInput
0x140030d6c  xor     r9d, r9d; dwFlags
0x140030d6f  mov     r8d, 4; cbInput
0x140030d75  call    cs:__imp_BCryptHashData
0x140030d7c  nop     dword ptr [rax+rax+00h]
0x140030d81  test    eax, eax
0x140030d83  jns     short loc_140030D8F
0x140030d85  mov     ebx, 80090304h
0x140030d8a  jmp     loc_14003109A
0x140030d8f  cmp     dword ptr [r14+4], 0
0x140030d94  mov     esi, r12d
0x140030d97  jbe     loc_140030E5A
0x140030d9d  nop     dword ptr [rax]
0x140030da0  mov     r9, [r14+8]
0x140030da4  mov     ebx, esi
0x140030da6  add     rbx, rbx
0x140030da9  mov     eax, [r9+rbx*8+4]
0x140030dae  cmp     al, 1
0x140030db0  jnz     loc_140030E4E
0x140030db6  mov     r8d, [r9+rbx*8]
0x140030dba  test    r8d, r8d
0x140030dbd  jz      loc_140030E4E
0x140030dc3  and     eax, 90000000h
0x140030dc8  cmp     eax, 90000000h
0x140030dcd  jz      loc_140030E85
0x140030dd3  cmp     r15d, 3
0x140030dd7  jnz     short loc_140030DF5
0x140030dd9  test    eax, eax
0x140030ddb  jnz     short loc_140030DF5
0x140030ddd  mov     r9, [r9+rbx*8+8]
0x140030de2  mov     rdx, r13
0x140030de5  mov     rcx, rdi
0x140030de8  call    SspEncryptBuffer
0x140030ded  test    eax, eax
0x140030def  js      loc_140030CA5
0x140030df5  mov     rax, [r14+8]
0x140030df9  xor     r9d, r9d; dwFlags
0x140030dfc  mov     rcx, [rbp+47h+phHash]; hHash
0x140030e00  mov     r8d, [rax+rbx*8]; cbInput
0x140030e04  mov     rdx, [rax+rbx*8+8]; pbInput
0x140030e09  call    cs:__imp_BCryptHashData
0x140030e10  nop     dword ptr [rax+rax+00h]
0x140030e15  test    eax, eax
0x140030e17  js      loc_140030CA5
0x140030e1d  cmp     r15d, 2
0x140030e21  jnz     short loc_140030E4E
0x140030e23  mov     r8, [r14+8]
0x140030e27  test    dword ptr [r8+rbx*8+4], 90000000h
0x140030e30  jnz     short loc_140030E4E
0x140030e32  mov     r9, [r8+rbx*8+8]
0x140030e37  mov     rdx, r13
0x140030e3a  mov     r8d, [r8+rbx*8]
0x140030e3e  mov     rcx, rdi
0x140030e41  call    SspEncryptBuffer
0x140030e46  test    eax, eax
0x140030e48  js      loc_140030CA5
0x140030e4e  inc     esi
0x140030e50  cmp     esi, [r14+4]
0x140030e54  jb      loc_140030DA0
0x140030e5a  mov     rcx, [rbp+47h+phHash]; hHash
0x140030e5e  lea     rdx, [rbp+47h+var_50]; pbOutput
0x140030e62  xor     r9d, r9d; dwFlags
0x140030e65  mov     r8d, 10h; cbOutput
0x140030e6b  call    cs:__imp_BCryptFinishHash
0x140030e72  nop     dword ptr [rax+rax+00h]
0x140030e77  test    eax, eax
0x140030e79  jns     short loc_140030E8F
0x140030e7b  mov     ebx, 80090304h
0x140030e80  jmp     loc_14003109A
0x140030e85  mov     ebx, 80090308h
0x140030e8a  jmp     loc_14003109A
0x140030e8f  test    dword ptr [rdi+30h], 40000000h
0x140030e96  mov     rax, qword ptr [rbp+47h+var_50]
0x140030e9a  mov     qword ptr [rbp+47h+pbInput+4], rax
0x140030e9e  jz      loc_14003107D
0x140030ea4  lea     r9, [rbp+47h+pbInput+4]
0x140030ea8  mov     r8d, 8
0x140030eae  mov     rdx, r13
0x140030eb1  mov     rcx, rdi
0x140030eb4  call    SspEncryptBuffer
0x140030eb9  test    eax, eax
0x140030ebb  jns     loc_14003107D
0x140030ec1  mov     ebx, 80090304h
0x140030ec6  jmp     loc_14003109A
0x140030ecb  xor     edx, edx
0x140030ecd  mov     dword ptr [rbp+47h+pbInput+8], 0FFFFFFFFh
0x140030ed4  mov     esi, edx
0x140030ed6  cmp     [r14+4], edx
0x140030eda  jbe     loc_140030F95
0x140030ee0  mov     r9, [r14+8]
0x140030ee4  mov     ebx, esi
0x140030ee6  add     rbx, rbx
0x140030ee9  mov     ecx, [r9+rbx*8+4]
0x140030eee  cmp     cl, 1
0x140030ef1  jnz     loc_140030F87
0x140030ef7  mov     r8d, [r9+rbx*8]
0x140030efb  test    r8d, r8d
0x140030efe  jz      loc_140030F87
0x140030f04  mov     eax, ecx
0x140030f06  and     eax, 90000000h
0x140030f0b  cmp     eax, 90000000h
0x140030f10  jz      loc_140030E85
0x140030f16  test    ecx, ecx
0x140030f18  js      short loc_140030F87
0x140030f1a  cmp     r15d, 3
0x140030f1e  jnz     short loc_140030F3E
0x140030f20  bt      ecx, 1Ch
0x140030f24  jb      short loc_140030F3E
0x140030f26  mov     r9, [r9+rbx*8+8]
0x140030f2b  mov     rdx, r13
0x140030f2e  mov     rcx, rdi
0x140030f31  call    SspEncryptBuffer
0x140030f36  test    eax, eax
0x140030f38  js      loc_140030CA5
  ... truncated ...
```
