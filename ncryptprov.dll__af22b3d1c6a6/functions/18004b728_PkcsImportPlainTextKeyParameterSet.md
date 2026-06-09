# _PkcsImportPlainTextKeyParameterSet

- ea: `0x18004b728`
- end: `0x18004bb97`
- name: `_PkcsImportPlainTextKeyParameterSet`
- size: `1135`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, wchar_t *String1, STRSAFE_PCNZWCH psz)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180034c30`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x180017580`
- `0x18002015c`
- `0x1800398b0`
- `0x18004722c`
- `0x180049d50`
- `0x180049dec`
- `0x18004b728`
- `0x180050ad4`
- `0x180050cf8`
- `0x1800622e0`
- `0x180063010`

## import_xrefs

- `CRYPT32!CryptDecodeObjectEx` at `0x18004b883`
- `CRYPT32!CryptDecodeObjectEx` at `0x18004b8fb`
- `CRYPT32!CryptDecodeObjectEx` at `0x18004b883`
- `CRYPT32!CryptDecodeObjectEx` at `0x18004b8fb`

## string_xrefs

- `0x18004b7f8`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004b9aa`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004bac1`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`

## pseudocode

```c
__int64 __fastcall PkcsImportPlainTextKeyParameterSet(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        wchar_t *String1,
        STRSAFE_PCNZWCH psz)
{
  void *v7; // rdi
  unsigned int v8; // esi
  int v9; // ebx
  const wchar_t *v10; // r12
  int v11; // r14d
  const wchar_t *v12; // r15
  DWORD v13; // r9d
  __int64 v14; // r9
  unsigned int v15; // ebx
  __int64 v16; // rcx
  const BYTE *v17; // r8
  size_t v18; // rdx
  const void *v19; // r13
  __int64 v20; // r13
  HRESULT v21; // eax
  __int64 v22; // rcx
  size_t v23; // rbx
  unsigned int v24; // eax
  unsigned int v25; // r15d
  unsigned int *v26; // r14
  unsigned int v27; // esi
  int v28; // eax
  __int64 v29; // r9
  __int64 v30; // rcx
  __int64 v31; // rcx
  unsigned int *v32; // rax
  _BYTE *v33; // rax
  __int64 v34; // rcx
  _BYTE *v35; // rax
  __int64 v36; // rcx
  size_t pcchLength; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v39; // [rsp+48h] [rbp-30h]
  DWORD v40; // [rsp+4Ch] [rbp-2Ch] BYREF
  DWORD pcbStructInfo; // [rsp+50h] [rbp-28h] BYREF
  __int64 v42; // [rsp+58h] [rbp-20h] BYREF
  __int64 pvStructInfo; // [rsp+60h] [rbp-18h] BYREF
  void *v44; // [rsp+68h] [rbp-10h] BYREF
  unsigned int v47; // [rsp+D0h] [rbp+58h]

  v7 = 0;
  v44 = 0;
  pcchLength = 0;
  v42 = 0;
  v40 = 0;
  pvStructInfo = 0;
  pcbStructInfo = 0;
  if ( !wcscmp_0(String1, L"ML-DSA") )
  {
    v8 = 32;
    v39 = 196620;
    v9 = 1263752004;
    v10 = L"PQDSAPRIVATESEEDBLOB";
    v11 = 1397969732;
    v12 = L"PQDSAPRIVATEBLOB";
    goto LABEL_5;
  }
  if ( !wcscmp_0(String1, L"ML-KEM") )
  {
    v39 = 458753;
    v8 = 64;
    v11 = 1397443661;
    v10 = L"MLKEMPRIVATESEEDBLOB";
    v9 = 1380666445;
    v12 = L"MLKEMPRIVATEBLOB";
LABEL_5:
    v13 = *(_DWORD *)(a3 + 32);
    v47 = v11;
    if ( !v13 )
    {
      v14 = 3903;
LABEL_7:
      v15 = -2146893819;
      v16 = 2148073477LL;
LABEL_8:
      DebugTraceError(v16, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v14);
      goto LABEL_59;
    }
    v17 = *(const BYTE **)(a3 + 40);
    v18 = v8 + 2;
    switch ( *v17 )
    {
      case 4u:
        if ( !CryptDecodeObjectEx(1u, (LPCSTR)0x19, v17, v13, 0x8001u, &pDecodePara, &v42, &v40) )
        {
          v14 = 3949;
          goto LABEL_7;
        }
        v10 = v12;
        v47 = v9;
        v8 = *(_DWORD *)v42;
        v19 = *(const void **)(v42 + 8);
        break;
      case 0x30u:
        if ( !CryptDecodeObjectEx(1u, (LPCSTR)0x22, v17, v13, 0x8001u, &pDecodePara, &pvStructInfo, &pcbStructInfo) )
        {
          v14 = 3985;
          goto LABEL_7;
        }
        if ( *(_DWORD *)pvStructInfo != 2 || (v20 = *(_QWORD *)(pvStructInfo + 8), *(_DWORD *)v20 != v8 + 2) )
        {
          v14 = 3978;
          goto LABEL_7;
        }
        v19 = (const void *)(*(_QWORD *)(v20 + 8) + 2LL);
        v47 = v11;
        break;
      case 0x80u:
        if ( v13 != (_DWORD)v18 || v17[1] != v8 )
        {
          v14 = 3923;
          goto LABEL_7;
        }
        v19 = v17 + 2;
        break;
      default:
        v14 = 3993;
        goto LABEL_7;
    }
    v21 = StringCchLengthW(psz, v18, &pcchLength);
    v15 = v21;
    if ( v21 < 0 )
    {
      v14 = 4001;
LABEL_27:
      v16 = (unsigned int)v21;
      goto LABEL_8;
    }
    v22 = (unsigned int)(pcchLength + 1);
    if ( (unsigned int)v22 < (unsigned int)pcchLength )
    {
      v14 = 4009;
      goto LABEL_54;
    }
    LODWORD(pcchLength) = pcchLength + 1;
    v21 = RtlULongLongToULong(2 * v22, &pcchLength);
    v15 = v21;
    if ( v21 < 0 )
    {
      v14 = 4016;
      goto LABEL_27;
    }
    v23 = (unsigned int)pcchLength;
    v24 = pcchLength + 12;
    if ( (unsigned int)pcchLength >= 0xFFFFFFF4 )
    {
      v14 = 4023;
LABEL_54:
      v15 = -1073741675;
      v16 = 3221225621LL;
      goto LABEL_8;
    }
    v25 = v24 + v8;
    if ( v24 + v8 < v24 )
    {
      v14 = 4030;
      goto LABEL_54;
    }
    v26 = (unsigned int *)SafeAllocaAllocateFromHeap(v25);
    if ( !v26 )
    {
      v15 = -1073741801;
      DebugTraceError(3221225495LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 4038);
      goto LABEL_57;
    }
    *v26 = v47;
    v26[1] = v23;
    v26[2] = v8;
    memcpy_0(v26 + 3, psz, v23);
    memcpy_0((char *)v26 + v23 + 12, v19, v8);
    v27 = v39;
    v28 = PkcsCreateKeyObject(&v44, a4, a2, v39);
    v7 = v44;
    v15 = v28;
    if ( v28 < 0 )
    {
      v29 = 4058;
LABEL_48:
      v30 = (unsigned int)v28;
      goto LABEL_49;
    }
    if ( v27 == 196620 )
    {
      v28 = KspImportPqDsaPrivateKey((__int64)v44, v10, v26, v25, 2);
      v15 = v28;
      if ( v28 < 0 )
      {
        v29 = 4073;
        goto LABEL_48;
      }
      v28 = PkcsAddKeyUsageProperty(v7, 2);
      v15 = v28;
      if ( v28 < 0 )
      {
        v29 = 4081;
        goto LABEL_48;
      }
    }
    else
    {
      if ( v27 != 458753 )
      {
        v15 = -2146893783;
        v30 = 2148073513LL;
        v29 = 4102;
LABEL_49:
        DebugTraceError(v30, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v29);
        v31 = v25;
        v32 = v26;
        if ( v25 )
        {
          do
          {
            *(_BYTE *)v32 = 0;
            v32 = (unsigned int *)((char *)v32 + 1);
            --v31;
          }
          while ( v31 );
        }
        MSCryptFree(v26);
        goto LABEL_57;
      }
      v28 = KspImportMlKemBasedPrivateKey((__int64)v44, v10, v26, v25, 2);
      v15 = v28;
      if ( v28 < 0 )
      {
        v29 = 4095;
        goto LABEL_48;
      }
    }
    *a1 = v7;
    goto LABEL_59;
  }
  v15 = -2146893783;
LABEL_57:
  if ( v7 )
    DeleteKeyObject(v7);
LABEL_59:
  v33 = (_BYTE *)v42;
  if ( v42 )
  {
    v34 = v40;
    if ( v40 )
    {
      do
      {
        *v33++ = 0;
        --v34;
      }
      while ( v34 );
    }
    ((void (__fastcall *)(__int64))pDecodePara.pfnFree)(v42);
  }
  v35 = (_BYTE *)pvStructInfo;
  if ( pvStructInfo )
  {
    v36 = pcbStructInfo;
    if ( pcbStructInfo )
    {
      do
      {
        *v35++ = 0;
        --v36;
      }
      while ( v36 );
    }
    ((void (__fastcall *)(__int64))pDecodePara.pfnFree)(pvStructInfo);
  }
  return v15;
}

```

## disassembly

```asm
0x18004b728  mov     [rsp-40h+arg_18], r9
0x18004b72d  mov     [rsp-40h+arg_8], rdx
0x18004b732  mov     [rsp-40h+arg_0], rcx
0x18004b737  push    rbp
0x18004b738  push    rbx
0x18004b739  push    rsi
0x18004b73a  push    rdi
0x18004b73b  push    r12
0x18004b73d  push    r13
0x18004b73f  push    r14
0x18004b741  push    r15
0x18004b743  mov     rbp, rsp
0x18004b746  sub     rsp, 78h
0x18004b74a  mov     rcx, [rbp+String1]; String1
0x18004b74e  lea     rdx, aMlDsa; "ML-DSA"
0x18004b755  xor     ebx, ebx
0x18004b757  mov     r13, r8
0x18004b75a  mov     edi, ebx
0x18004b75c  mov     [rbp+var_10], rbx
0x18004b760  mov     [rbp+pcchLength], rbx
0x18004b764  mov     [rbp+var_20], rbx
0x18004b768  mov     [rbp+var_2C], ebx
0x18004b76b  mov     [rbp+var_18], rbx
0x18004b76f  mov     [rbp+var_28], ebx
0x18004b772  call    wcscmp_0
0x18004b777  test    eax, eax
0x18004b779  jnz     short loc_18004B7A0
0x18004b77b  lea     esi, [rbx+20h]
0x18004b77e  mov     [rbp+var_30], 3000Ch
0x18004b785  mov     ebx, 4B535344h
0x18004b78a  lea     r12, aPqdsaprivatese; "PQDSAPRIVATESEEDBLOB"
0x18004b791  mov     r14d, 53535344h
0x18004b797  lea     r15, aPqdsaprivatebl; "PQDSAPRIVATEBLOB"
0x18004b79e  jmp     short loc_18004B7DB
0x18004b7a0  mov     rcx, [rbp+String1]; String1
0x18004b7a4  lea     rdx, aMlKem; "ML-KEM"
0x18004b7ab  call    wcscmp_0
0x18004b7b0  test    eax, eax
0x18004b7b2  jnz     loc_18004BB17
0x18004b7b8  mov     [rbp+var_30], 70001h
0x18004b7bf  lea     esi, [rax+40h]
0x18004b7c2  mov     r14d, 534B4C4Dh
0x18004b7c8  lea     r12, aMlkemprivatese; "MLKEMPRIVATESEEDBLOB"
0x18004b7cf  mov     ebx, 524B4C4Dh
0x18004b7d4  lea     r15, aMlkemprivatebl; "MLKEMPRIVATEBLOB"
0x18004b7db  mov     r9d, [r13+20h]; cbEncoded
0x18004b7df  mov     [rbp+arg_10], r14d
0x18004b7e3  test    r9d, r9d
0x18004b7e6  jnz     short loc_18004B810
0x18004b7e8  mov     r9d, 0F3Fh
0x18004b7ee  mov     ebx, 80090005h
0x18004b7f3  mov     ecx, 80090005h
0x18004b7f8  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004b7ff  lea     rdx, aStatus_0; "status"
0x18004b806  call    DebugTraceError
0x18004b80b  jmp     loc_18004BB29
0x18004b810  mov     r8, [r13+28h]; pbEncoded
0x18004b814  lea     edx, [rsi+2]
0x18004b817  movzx   ecx, byte ptr [r8]
0x18004b81b  sub     ecx, 4
0x18004b81e  jz      loc_18004B8CD
0x18004b824  sub     ecx, 2Ch ; ','
0x18004b827  jz      short loc_18004B855
0x18004b829  cmp     ecx, 50h ; 'P'
0x18004b82c  jz      short loc_18004B836
0x18004b82e  mov     r9d, 0F99h
0x18004b834  jmp     short loc_18004B7EE
0x18004b836  cmp     r9d, edx
0x18004b839  jnz     short loc_18004B84D
0x18004b83b  movzx   eax, byte ptr [r8+1]
0x18004b840  cmp     eax, esi
0x18004b842  jnz     short loc_18004B84D
0x18004b844  lea     r13, [r8+2]
0x18004b848  jmp     loc_18004B91F
0x18004b84d  mov     r9d, 0F53h
0x18004b853  jmp     short loc_18004B7EE
0x18004b855  lea     rax, [rbp+var_28]
0x18004b859  mov     edx, 22h ; '"'; lpszStructType
0x18004b85e  mov     [rsp+78h+pcbStructInfo], rax; pcbStructInfo
0x18004b863  lea     rax, [rbp+var_18]
0x18004b867  mov     [rsp+78h+pvStructInfo], rax; pvStructInfo
0x18004b86c  lea     rax, pDecodePara
0x18004b873  mov     [rsp+78h+pDecodePara], rax; pDecodePara
0x18004b878  lea     ecx, [rdx-21h]; dwCertEncodingType
0x18004b87b  mov     [rsp+78h+dwFlags], 8001h; dwFlags
0x18004b883  call    cs:__imp_CryptDecodeObjectEx
0x18004b88a  nop     dword ptr [rax+rax+00h]
0x18004b88f  test    eax, eax
0x18004b891  jz      short loc_18004B8C2
0x18004b893  mov     rax, [rbp+var_18]
0x18004b897  cmp     dword ptr [rax], 2
0x18004b89a  jnz     short loc_18004B8B7
0x18004b89c  mov     r13, [rax+8]
0x18004b8a0  lea     eax, [rsi+2]
0x18004b8a3  cmp     [r13+0], eax
0x18004b8a7  jnz     short loc_18004B8B7
0x18004b8a9  mov     r13, [r13+8]
0x18004b8ad  add     r13, 2
0x18004b8b1  mov     [rbp+arg_10], r14d
0x18004b8b5  jmp     short loc_18004B91F
0x18004b8b7  mov     r9d, 0F8Ah
0x18004b8bd  jmp     loc_18004B7EE
0x18004b8c2  mov     r9d, 0F91h
0x18004b8c8  jmp     loc_18004B7EE
0x18004b8cd  lea     rax, [rbp+var_2C]
0x18004b8d1  mov     edx, 19h; lpszStructType
0x18004b8d6  mov     [rsp+78h+pcbStructInfo], rax; pcbStructInfo
0x18004b8db  lea     rax, [rbp+var_20]
0x18004b8df  mov     [rsp+78h+pvStructInfo], rax; pvStructInfo
0x18004b8e4  lea     rax, pDecodePara
0x18004b8eb  mov     [rsp+78h+pDecodePara], rax; pDecodePara
0x18004b8f0  lea     ecx, [rdx-18h]; dwCertEncodingType
0x18004b8f3  mov     [rsp+78h+dwFlags], 8001h; dwFlags
0x18004b8fb  call    cs:__imp_CryptDecodeObjectEx
0x18004b902  nop     dword ptr [rax+rax+00h]
0x18004b907  test    eax, eax
0x18004b909  jz      loc_18004BB0C
0x18004b90f  mov     rax, [rbp+var_20]
0x18004b913  mov     r12, r15
0x18004b916  mov     [rbp+arg_10], ebx
0x18004b919  mov     esi, [rax]
0x18004b91b  mov     r13, [rax+8]
0x18004b91f  mov     rcx, [rbp+psz]; psz
0x18004b923  lea     r8, [rbp+pcchLength]; pcchLength
0x18004b927  call    StringCchLengthW
0x18004b92c  mov     ebx, eax
0x18004b92e  test    eax, eax
0x18004b930  jns     short loc_18004B93F
0x18004b932  mov     r9d, 0FA1h
0x18004b938  mov     ecx, eax
0x18004b93a  jmp     loc_18004B7F8
0x18004b93f  mov     eax, dword ptr [rbp+pcchLength]
0x18004b942  lea     ecx, [rax+1]
0x18004b945  cmp     ecx, eax
0x18004b947  jb      loc_18004BAF7
0x18004b94d  mov     dword ptr [rbp+pcchLength], ecx
0x18004b950  lea     rdx, [rbp+pcchLength]
0x18004b954  add     rcx, rcx
0x18004b957  call    RtlULongLongToULong
0x18004b95c  mov     ebx, eax
0x18004b95e  test    eax, eax
0x18004b960  jns     short loc_18004B96A
0x18004b962  mov     r9d, 0FB0h
0x18004b968  jmp     short loc_18004B938
0x18004b96a  mov     ebx, dword ptr [rbp+pcchLength]
0x18004b96d  lea     eax, [rbx+0Ch]
0x18004b970  cmp     eax, 0Ch
0x18004b973  jnb     short loc_18004B980
0x18004b975  mov     r9d, 0FB7h
0x18004b97b  jmp     loc_18004BAFD
0x18004b980  lea     r15d, [rax+rsi]
0x18004b984  cmp     r15d, eax
0x18004b987  jnb     short loc_18004B994
0x18004b989  mov     r9d, 0FBEh
0x18004b98f  jmp     loc_18004BAFD
0x18004b994  mov     ecx, r15d
0x18004b997  call    SafeAllocaAllocateFromHeap
0x18004b99c  mov     r14, rax
0x18004b99f  test    rax, rax
0x18004b9a2  jnz     short loc_18004B9CC
0x18004b9a4  mov     r9d, 0FC6h
0x18004b9aa  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004b9b1  lea     rdx, aStatus_0; "status"
0x18004b9b8  mov     ecx, 0C0000017h
0x18004b9bd  mov     ebx, 0C0000017h
0x18004b9c2  call    DebugTraceError
0x18004b9c7  jmp     loc_18004BB1C
0x18004b9cc  mov     eax, [rbp+arg_10]
0x18004b9cf  lea     rcx, [r14+0Ch]; void *
0x18004b9d3  mov     rdx, [rbp+psz]; Src
0x18004b9d7  mov     r8, rbx; Size
0x18004b9da  mov     [r14], eax
0x18004b9dd  mov     [r14+4], ebx
0x18004b9e1  mov     [r14+8], esi
0x18004b9e5  call    memcpy_0
0x18004b9ea  lea     rcx, [rbx+0Ch]
0x18004b9ee  mov     r8d, esi; Size
0x18004b9f1  add     rcx, r14; void *
0x18004b9f4  mov     rdx, r13; Src
0x18004b9f7  call    memcpy_0
0x18004b9fc  mov     eax, [rbp+arg_30]
0x18004b9ff  lea     rcx, [rbp+var_10]
0x18004ba03  mov     esi, [rbp+var_30]
0x18004ba06  mov     r9d, esi
0x18004ba09  mov     r8, [rbp+arg_8]
0x18004ba0d  mov     rdx, [rbp+arg_18]
0x18004ba11  mov     dword ptr [rsp+78h+pDecodePara], eax
0x18004ba15  call    _PkcsCreateKeyObject
0x18004ba1a  mov     rdi, [rbp+var_10]
0x18004ba1e  mov     ebx, eax
0x18004ba20  test    eax, eax
0x18004ba22  jns     short loc_18004BA2F
0x18004ba24  mov     r9d, 0FDAh
0x18004ba2a  jmp     loc_18004BAB8
0x18004ba2f  cmp     esi, 3000Ch
0x18004ba35  jz      short loc_18004BA78
0x18004ba37  cmp     esi, 70001h
0x18004ba3d  jz      short loc_18004BA51
0x18004ba3f  mov     ebx, 80090029h
0x18004ba44  mov     ecx, 80090029h
0x18004ba49  mov     r9d, 1006h
0x18004ba4f  jmp     short loc_18004BABA
0x18004ba51  mov     r9d, r15d
0x18004ba54  mov     [rsp+78h+dwFlags], 2
0x18004ba5c  mov     r8, r14
0x18004ba5f  mov     rdx, r12
0x18004ba62  mov     rcx, rdi
0x18004ba65  call    KspImportMlKemBasedPrivateKey
0x18004ba6a  mov     ebx, eax
0x18004ba6c  test    eax, eax
0x18004ba6e  jns     short loc_18004BAEE
0x18004ba70  mov     r9d, 0FFFh
0x18004ba76  jmp     short loc_18004BAB8
0x18004ba78  mov     r9d, r15d
0x18004ba7b  mov     [rsp+78h+dwFlags], 2
0x18004ba83  mov     r8, r14
0x18004ba86  mov     rdx, r12
0x18004ba89  mov     rcx, rdi
0x18004ba8c  call    KspImportPqDsaPrivateKey
0x18004ba91  mov     ebx, eax
0x18004ba93  test    eax, eax
0x18004ba95  jns     short loc_18004BA9F
0x18004ba97  mov     r9d, 0FE9h
0x18004ba9d  jmp     short loc_18004BAB8
0x18004ba9f  mov     edx, 2
0x18004baa4  mov     rcx, rdi
0x18004baa7  call    _PkcsAddKeyUsageProperty
0x18004baac  mov     ebx, eax
0x18004baae  test    eax, eax
0x18004bab0  jns     short loc_18004BAEE
0x18004bab2  mov     r9d, 0FF1h
0x18004bab8  mov     ecx, eax
0x18004baba  lea     rdx, aStatus_0; "status"
0x18004bac1  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004bac8  call    DebugTraceError
0x18004bacd  mov     ecx, r15d
0x18004bad0  mov     rax, r14
0x18004bad3  test    r15d, r15d
0x18004bad6  jz      short loc_18004BAE4
0x18004bad8  mov     byte ptr [rax], 0
0x18004badb  inc     rax
0x18004bade  sub     rcx, 1
0x18004bae2  jnz     short loc_18004BAD8
0x18004bae4  mov     rcx, r14
0x18004bae7  call    MSCryptFree
0x18004baec  jmp     short loc_18004BB1C
0x18004baee  mov     rax, [rbp+arg_0]
0x18004baf2  mov     [rax], rdi
0x18004baf5  jmp     short loc_18004BB29
0x18004baf7  mov     r9d, 0FA9h
0x18004bafd  mov     ebx, 0C0000095h
0x18004bb02  mov     ecx, 0C0000095h
0x18004bb07  jmp     loc_18004B7F8
0x18004bb0c  mov     r9d, 0F6Dh
0x18004bb12  jmp     loc_18004B7EE
0x18004bb17  mov     ebx, 80090029h
0x18004bb1c  test    rdi, rdi
0x18004bb1f  jz      short loc_18004BB29
0x18004bb21  mov     rcx, rdi; void *
0x18004bb24  call    DeleteKeyObject
0x18004bb29  mov     rax, [rbp+var_20]
0x18004bb2d  test    rax, rax
0x18004bb30  jz      short loc_18004BB56
0x18004bb32  mov     ecx, [rbp+var_2C]
0x18004bb35  test    rcx, rcx
0x18004bb38  jz      short loc_18004BB46
0x18004bb3a  mov     byte ptr [rax], 0
0x18004bb3d  inc     rax
0x18004bb40  sub     rcx, 1
0x18004bb44  jnz     short loc_18004BB3A
0x18004bb46  mov     rcx, [rbp+var_20]
0x18004bb4a  mov     rax, cs:pDecodePara.pfnFree
0x18004bb51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bb56  mov     rax, [rbp+var_18]
0x18004bb5a  test    rax, rax
0x18004bb5d  jz      short loc_18004BB83
0x18004bb5f  mov     ecx, [rbp+var_28]
0x18004bb62  test    rcx, rcx
0x18004bb65  jz      short loc_18004BB73
0x18004bb67  mov     byte ptr [rax], 0
0x18004bb6a  inc     rax
0x18004bb6d  sub     rcx, 1
0x18004bb71  jnz     short loc_18004BB67
0x18004bb73  mov     rcx, [rbp+var_18]
0x18004bb77  mov     rax, cs:pDecodePara.pfnFree
0x18004bb7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bb83  mov     eax, ebx
0x18004bb85  add     rsp, 78h
0x18004bb89  pop     r15
0x18004bb8b  pop     r14
0x18004bb8d  pop     r13
0x18004bb8f  pop     r12
0x18004bb91  pop     rdi
0x18004bb92  pop     rsi
0x18004bb93  pop     rbx
0x18004bb94  pop     rbp
0x18004bb95  retn
```
