# I_GetHashEntry

- ea: `0x180001acc`
- end: `0x180001de2`
- name: `I_GetHashEntry`
- size: `790`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001930`
- `0x180003f10`
- `0x180004570`
- `0x180006b60`
- `0x1800097f0`
- `0x180009ca0`
- `0x18000a120`
- `0x18000ae00`

## callees

- `0x180001acc`
- `0x180001de8`
- `0x18000b594`
- `0x18000b654`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x180001d1e`
- `bcrypt!BCryptGetProperty` at `0x180001d6a`
- `bcrypt!BCryptGetProperty` at `0x180001d1e`
- `bcrypt!BCryptGetProperty` at `0x180001d6a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180001cf3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180001d3f`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180001cf3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180001d3f`

## string_xrefs

- `0x180001c47`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`
- `0x180001d80`: `onecore\ds\security\cryptoapi\ncrypt\schannel\provider.c`

## pseudocode

```c
__int64 __fastcall I_GetHashEntry(unsigned int a1, ULONG a2, __int64 a3)
{
  __int64 *v4; // rsi
  int v5; // eax
  __int64 v8; // rcx
  int v9; // edx
  __int64 v10; // rdi
  int v11; // edx
  int AlgorithmHandle; // ebx
  int v13; // r8d
  BCRYPT_ALG_HANDLE v14; // rcx
  void *v15; // rbx
  __int64 *v16; // r12
  int v17; // r9d
  int v18; // edx
  int v19; // r8d
  BCRYPT_ALG_HANDLE v20; // rcx
  volatile signed __int64 *v21; // r15
  void *v22; // rbx
  int v23; // eax
  int *v24; // rcx
  char *v26; // r12
  __int64 *v27; // r15
  int *v28; // rcx
  NTSTATUS Property; // eax
  __int64 v30; // r9
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+40h] [rbp-10h] BYREF
  LPCWSTR pszAlgId; // [rsp+48h] [rbp-8h]
  int pbOutput; // [rsp+90h] [rbp+40h] BYREF
  ULONG pcbResult; // [rsp+98h] [rbp+48h] BYREF
  int v35; // [rsp+A8h] [rbp+58h]

  v4 = &l_PagedHashEntryCache;
  hAlgorithm = 0;
  v5 = a2 & 1;
  pbOutput = 0;
  if ( (a2 & 1) != 0 )
    v4 = &l_NonPagedHashEntryCache;
  if ( a1 < g_dwHashInfoTotalCount && (_mm_lfence(), (v8 = g_pHashInfo[a1]) != 0) )
  {
    v9 = *(_DWORD *)(v8 + 8);
    v10 = 32LL * a1;
    v35 = v9;
    if ( HIDWORD(v4[(unsigned __int64)v10 / 8 + 3]) )
    {
      v26 = byte_18003EAA0;
      if ( v5 )
        v26 = byte_18003EDA0;
      v27 = &qword_18003EA98;
      v16 = (__int64 *)&v26[v10];
      if ( v5 )
        v27 = &qword_18003ED98;
      v28 = &dword_18003EAA4;
      v21 = &v27[(unsigned __int64)v10 / 8];
      if ( v5 )
        v28 = &dword_18003EDA4;
      v24 = &v28[(unsigned __int64)v10 / 4];
LABEL_13:
      AlgorithmHandle = 0;
      *(_QWORD *)a3 = v4[(unsigned __int64)v10 / 8];
      *(_DWORD *)(a3 + 16) = *(_DWORD *)v16;
      *(_QWORD *)(a3 + 8) = *v21;
      *(_DWORD *)(a3 + 20) = *v24;
      *(_DWORD *)(a3 + 24) = v9;
      *(_DWORD *)(a3 + 28) = 1;
      return (unsigned int)AlgorithmHandle;
    }
    pszAlgId = *(LPCWSTR *)v8;
    AlgorithmHandle = GetAlgorithmHandle(pszAlgId, &hAlgorithm, (UCHAR *)&pbOutput, a2);
    if ( AlgorithmHandle < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          v13,
          (unsigned int)"Status",
          AlgorithmHandle,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          3);
    }
    else
    {
      v14 = hAlgorithm;
      v15 = (void *)_InterlockedCompareExchange64(&v4[(unsigned __int64)v10 / 8], (signed __int64)hAlgorithm, 0);
      if ( v15 )
      {
        pcbResult = 0;
        BCryptCloseAlgorithmProvider(v14, 0);
        Property = BCryptGetProperty(v15, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
        AlgorithmHandle = Property;
        if ( Property < 0 )
        {
          v30 = 4889;
LABEL_32:
          DebugTraceError(
            (unsigned int)Property,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
            v30);
          return (unsigned int)AlgorithmHandle;
        }
      }
      v16 = &v4[(unsigned __int64)v10 / 8 + 2];
      *(_DWORD *)v16 = pbOutput;
      if ( ((a1 - 2) & 0xFFFFFFFD) == 0 || (v17 = 8, a1 == 5) )
        v17 = 12;
      AlgorithmHandle = GetAlgorithmHandle(pszAlgId, &hAlgorithm, (UCHAR *)&pbOutput, a2 | v17);
      if ( AlgorithmHandle >= 0 )
      {
        v20 = hAlgorithm;
        v21 = &v4[(unsigned __int64)v10 / 8 + 1];
        v22 = (void *)_InterlockedCompareExchange64(v21, (signed __int64)hAlgorithm, 0);
        if ( v22 )
        {
          pcbResult = 0;
          BCryptCloseAlgorithmProvider(v20, 0);
          Property = BCryptGetProperty(v22, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
          AlgorithmHandle = Property;
          if ( Property < 0 )
          {
            v30 = 4953;
            goto LABEL_32;
          }
        }
        v23 = pbOutput;
        v9 = v35;
        v24 = (int *)&v4[(unsigned __int64)v10 / 8 + 2] + 1;
        HIDWORD(v4[(unsigned __int64)v10 / 8 + 3]) = 1;
        *v24 = v23;
        goto LABEL_13;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v18,
          v19,
          (unsigned int)"Status",
          AlgorithmHandle,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
          67);
    }
  }
  else
  {
    AlgorithmHandle = 1168;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        a3,
        (unsigned int)"Status",
        144,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\provider.c",
        243);
  }
  return (unsigned int)AlgorithmHandle;
}

```

## disassembly

```asm
0x180001acc  mov     [rsp-38h+arg_10], rbx
0x180001ad1  push    rbp
0x180001ad2  push    rsi
0x180001ad3  push    rdi
0x180001ad4  push    r12
0x180001ad6  push    r13
0x180001ad8  push    r14
0x180001ada  push    r15
0x180001adc  mov     rbp, rsp
0x180001adf  sub     rsp, 50h
0x180001ae3  mov     r15d, ecx
0x180001ae6  lea     rsi, l_PagedHashEntryCache
0x180001aed  mov     eax, edx
0x180001aef  mov     [rbp+hAlgorithm], 0
0x180001af7  and     eax, 1
0x180001afa  mov     [rbp+pbOutput], 0
0x180001b01  lea     rcx, l_NonPagedHashEntryCache
0x180001b08  mov     r14, r8
0x180001b0b  cmovnz  rsi, rcx
0x180001b0f  mov     r13d, edx
0x180001b12  cmp     r15d, cs:g_dwHashInfoTotalCount
0x180001b19  jnb     loc_180001D9A
0x180001b1f  mov     edi, r15d
0x180001b22  lfence
0x180001b25  lea     rcx, g_pHashInfo
0x180001b2c  mov     rcx, [rcx+r15*8]
0x180001b30  test    rcx, rcx
0x180001b33  jz      loc_180001D9A
0x180001b39  mov     edx, [rcx+8]
0x180001b3c  shl     rdi, 5
0x180001b40  mov     [rbp+arg_18], edx
0x180001b43  cmp     dword ptr [rdi+rsi+1Ch], 0
0x180001b48  jnz     loc_180001CA0
0x180001b4e  mov     rax, [rcx]
0x180001b51  lea     r8, [rbp+pbOutput]
0x180001b55  mov     rcx, rax; pszAlgId
0x180001b58  mov     [rbp+pszAlgId], rax
0x180001b5c  mov     r9d, r13d
0x180001b5f  lea     rdx, [rbp+hAlgorithm]
0x180001b63  call    GetAlgorithmHandle
0x180001b68  mov     ebx, eax
0x180001b6a  test    eax, eax
0x180001b6c  js      loc_180001C7D
0x180001b72  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x180001b76  xor     eax, eax
0x180001b78  lock cmpxchg [rdi+rsi], rcx
0x180001b7e  mov     rbx, rax
0x180001b81  jnz     loc_180001CEA
0x180001b87  mov     eax, [rbp+pbOutput]
0x180001b8a  lea     r12, [rdi+10h]
0x180001b8e  add     r12, rsi
0x180001b91  mov     [r12], eax
0x180001b95  lea     eax, [r15-2]
0x180001b99  test    eax, 0FFFFFFFDh
0x180001b9e  jnz     loc_180001DCD
0x180001ba4  mov     r9d, 0Ch
0x180001baa  mov     rcx, [rbp+pszAlgId]; pszAlgId
0x180001bae  lea     r8, [rbp+pbOutput]
0x180001bb2  or      r9d, r13d
0x180001bb5  lea     rdx, [rbp+hAlgorithm]
0x180001bb9  call    GetAlgorithmHandle
0x180001bbe  mov     ebx, eax
0x180001bc0  test    eax, eax
0x180001bc2  js      short loc_180001C22
0x180001bc4  mov     rcx, [rbp+hAlgorithm]; hAlgorithm
0x180001bc8  lea     r15, [rdi+8]
0x180001bcc  add     r15, rsi
0x180001bcf  xor     eax, eax
0x180001bd1  lock cmpxchg [r15], rcx
0x180001bd6  mov     rbx, rax
0x180001bd9  jnz     loc_180001D36
0x180001bdf  mov     eax, [rbp+pbOutput]
0x180001be2  lea     rcx, [rdi+14h]
0x180001be6  mov     edx, [rbp+arg_18]
0x180001be9  add     rcx, rsi
0x180001bec  mov     dword ptr [rdi+rsi+1Ch], 1
0x180001bf4  mov     [rcx], eax
0x180001bf6  mov     rax, [rdi+rsi]
0x180001bfa  xor     ebx, ebx
0x180001bfc  mov     [r14], rax
0x180001bff  mov     eax, [r12]
0x180001c03  mov     [r14+10h], eax
0x180001c07  mov     rax, [r15]
0x180001c0a  mov     [r14+8], rax
0x180001c0e  mov     eax, [rcx]
0x180001c10  mov     [r14+14h], eax
0x180001c14  mov     [r14+18h], edx
0x180001c18  mov     dword ptr [r14+1Ch], 1
0x180001c20  jmp     short loc_180001C63
0x180001c22  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c29  lea     rax, WPP_GLOBAL_Control
0x180001c30  cmp     rcx, rax
0x180001c33  jz      short loc_180001C63
0x180001c35  test    byte ptr [rcx+1Ch], 1
0x180001c39  jz      short loc_180001C63
0x180001c3b  mov     [rsp+50h+var_20], 1343h
0x180001c43  mov     rcx, [rcx+10h]
0x180001c47  lea     rax, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001c4e  mov     qword ptr [rsp+50h+dwFlags], rax
0x180001c53  lea     r9, aStatus; "Status"
0x180001c5a  mov     dword ptr [rsp+50h+pcbResult], ebx
0x180001c5e  call    WPP_SF_sDsd
0x180001c63  mov     eax, ebx
0x180001c65  mov     rbx, [rsp+50h+arg_10]
0x180001c6d  add     rsp, 50h
0x180001c71  pop     r15
0x180001c73  pop     r14
0x180001c75  pop     r13
0x180001c77  pop     r12
0x180001c79  pop     rdi
0x180001c7a  pop     rsi
0x180001c7b  pop     rbp
0x180001c7c  retn
0x180001c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c84  lea     rax, WPP_GLOBAL_Control
0x180001c8b  cmp     rcx, rax
0x180001c8e  jz      short loc_180001C63
0x180001c90  test    byte ptr [rcx+1Ch], 1
0x180001c94  jz      short loc_180001C63
0x180001c96  mov     [rsp+50h+var_20], 1303h
0x180001c9e  jmp     short loc_180001C43
0x180001ca0  test    eax, eax
0x180001ca2  lea     rcx, byte_18003EDA0
0x180001ca9  lea     r12, byte_18003EAA0
0x180001cb0  cmovnz  r12, rcx
0x180001cb4  lea     r15, qword_18003EA98
0x180001cbb  add     r12, rdi
0x180001cbe  lea     rcx, qword_18003ED98
0x180001cc5  test    eax, eax
0x180001cc7  lea     r8, dword_18003EDA4
0x180001cce  cmovnz  r15, rcx
0x180001cd2  lea     rcx, dword_18003EAA4
0x180001cd9  add     r15, rdi
0x180001cdc  test    eax, eax
0x180001cde  cmovnz  rcx, r8
0x180001ce2  add     rcx, rdi
0x180001ce5  jmp     loc_180001BF6
0x180001cea  xor     edx, edx; dwFlags
0x180001cec  mov     [rbp+arg_8], 0
0x180001cf3  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180001cf9  lea     rax, [rbp+arg_8]
0x180001cfd  mov     [rsp+50h+dwFlags], 0; dwFlags
0x180001d05  mov     r9d, 4; cbOutput
0x180001d0b  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180001d10  lea     r8, [rbp+pbOutput]; pbOutput
0x180001d14  mov     rcx, rbx; hObject
0x180001d17  lea     rdx, aObjectlength; "ObjectLength"
0x180001d1e  call    cs:__imp_BCryptGetProperty
0x180001d24  mov     ebx, eax
0x180001d26  test    eax, eax
0x180001d28  jns     loc_180001B87
0x180001d2e  mov     r9d, 1319h
0x180001d34  jmp     short loc_180001D80
0x180001d36  xor     edx, edx; dwFlags
0x180001d38  mov     [rbp+arg_8], 0
0x180001d3f  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180001d45  lea     rax, [rbp+arg_8]
0x180001d49  mov     [rsp+50h+dwFlags], 0; dwFlags
0x180001d51  mov     r9d, 4; cbOutput
0x180001d57  mov     [rsp+50h+pcbResult], rax; pcbResult
0x180001d5c  lea     r8, [rbp+pbOutput]; pbOutput
0x180001d60  mov     rcx, rbx; hObject
0x180001d63  lea     rdx, aObjectlength; "ObjectLength"
0x180001d6a  call    cs:__imp_BCryptGetProperty
0x180001d70  mov     ebx, eax
0x180001d72  test    eax, eax
0x180001d74  jns     loc_180001BDF
0x180001d7a  mov     r9d, 1359h
0x180001d80  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001d87  mov     ecx, eax
0x180001d89  lea     rdx, aStatus; "Status"
0x180001d90  call    DebugTraceError
0x180001d95  jmp     loc_180001C63
0x180001d9a  mov     ebx, 490h
0x180001d9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180001da6  lea     rax, WPP_GLOBAL_Control
0x180001dad  cmp     rcx, rax
0x180001db0  jz      loc_180001C63
0x180001db6  test    byte ptr [rcx+1Ch], 1
0x180001dba  jz      loc_180001C63
0x180001dc0  mov     [rsp+50h+var_20], 12F3h
0x180001dc8  jmp     loc_180001C43
0x180001dcd  mov     r9d, 8
0x180001dd3  cmp     r15d, 5
0x180001dd7  jnz     loc_180001BAA
0x180001ddd  jmp     loc_180001BA4
```
