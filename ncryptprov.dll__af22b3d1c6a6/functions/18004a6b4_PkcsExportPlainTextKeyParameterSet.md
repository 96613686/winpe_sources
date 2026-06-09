# _PkcsExportPlainTextKeyParameterSet

- ea: `0x18004a6b4`
- end: `0x18004aa2e`
- name: `_PkcsExportPlainTextKeyParameterSet`
- size: `890`
- prototype: `__int64 __fastcall(__int64, int, __int64, DWORD, DWORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180034e80`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x1800231f8`
- `0x180025018`
- `0x1800398b0`
- `0x18004a6b4`
- `0x18005f338`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a80d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a80d`
- `CRYPT32!CryptEncodeObjectEx` at `0x18004a7fd`
- `CRYPT32!CryptEncodeObjectEx` at `0x18004a7fd`
- `CRYPT32!CryptFindOIDInfo` at `0x18004a89d`
- `CRYPT32!CryptFindOIDInfo` at `0x18004a89d`

## string_xrefs

- `0x18004a794`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004a830`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004a8c1`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`

## pseudocode

```c
__int64 __fastcall PkcsExportPlainTextKeyParameterSet(__int64 a1, int a2, __int64 a3, DWORD a4, DWORD *a5)
{
  unsigned int v7; // ebx
  unsigned int v8; // r13d
  unsigned __int16 *v9; // r14
  const wchar_t *v10; // r8
  const wchar_t *v11; // rdi
  __int64 v12; // rcx
  unsigned int v13; // r12d
  int v14; // eax
  unsigned __int16 *v15; // rsi
  signed int LastError; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  DWORD v19; // edi
  void *ParameterSetAlgorithmName; // rax
  PCCRYPT_OID_INFO OIDInfo; // rdx
  __int64 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // rcx
  _BYTE *v25; // rax
  __int64 v26; // r14
  _BYTE *v27; // rax
  _BYTE *v28; // rdi
  const void *v29; // r12
  size_t v30; // r8
  _BYTE *v31; // rax
  _BYTE *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rax
  unsigned __int16 *v35; // rcx
  unsigned int pvEncoded; // [rsp+28h] [rbp-48h]
  unsigned int pvEncodeda; // [rsp+28h] [rbp-48h]
  unsigned int v39; // [rsp+40h] [rbp-30h] BYREF
  int v40; // [rsp+44h] [rbp-2Ch]
  HLOCAL hMem; // [rsp+48h] [rbp-28h] BYREF
  const void *v42; // [rsp+50h] [rbp-20h] BYREF
  __int128 pvStructInfo; // [rsp+58h] [rbp-18h] BYREF
  DWORD pcbEncoded; // [rsp+B8h] [rbp+48h] BYREF
  DWORD v45; // [rsp+C8h] [rbp+58h]

  v45 = a4;
  hMem = 0;
  v39 = 0;
  v42 = 0;
  pvStructInfo = 0;
  if ( a2 == 196620 )
  {
    v8 = 32;
    v9 = L"ML-DSA";
    v10 = L"PQDSAPRIVATESEEDBLOB";
    v11 = L"PQDSAPRIVATEBLOB";
  }
  else
  {
    if ( a2 != 458753 )
      return (unsigned int)-2146893783;
    v8 = 64;
    v9 = L"ML-KEM";
    v10 = L"MLKEMPRIVATESEEDBLOB";
    v11 = L"MLKEMPRIVATEBLOB";
  }
  v12 = *(_QWORD *)(a1 + 112);
  v13 = v8 + 2;
  pcbEncoded = v8 + 2;
  v40 = 1;
  if ( (int)PkcsAllocAndExportKeyBlob(v12, a1, (__int64)v10, (__int64 *)&hMem, &v39, pvEncoded) >= 0 )
  {
    v15 = (unsigned __int16 *)hMem;
    goto LABEL_15;
  }
  v14 = PkcsAllocAndExportKeyBlob(*(_QWORD *)(a1 + 112), a1, (__int64)v11, (__int64 *)&hMem, &v39, pvEncodeda);
  v7 = v14;
  if ( v14 >= 0 )
  {
    v40 = 0;
    v15 = (unsigned __int16 *)hMem;
    LODWORD(pvStructInfo) = *((_DWORD *)hMem + 2);
    *((_QWORD *)&pvStructInfo + 1) = (char *)hMem + *((unsigned int *)hMem + 1) + 12;
    if ( !CryptEncodeObjectEx(1u, (LPCSTR)0x19, &pvStructInfo, 0x8000u, &pEncodePara, &v42, &pcbEncoded) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      v17 = 3715;
      v18 = v7;
      goto LABEL_13;
    }
LABEL_15:
    v19 = pcbEncoded + 56;
    if ( pcbEncoded >= 0xFFFFFFC8 )
    {
      v7 = -1073741675;
      v17 = 3723;
      v18 = 3221225621LL;
LABEL_13:
      DebugTraceError(v18, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v17);
      goto LABEL_40;
    }
    ParameterSetAlgorithmName = (void *)I_CryptMakeParameterSetAlgorithmName(v9, v15 + 6);
    hMem = ParameterSetAlgorithmName;
    if ( !ParameterSetAlgorithmName )
    {
      v7 = -1073739509;
      v17 = 3734;
      v18 = 3221227787LL;
      goto LABEL_13;
    }
    OIDInfo = CryptFindOIDInfo(5u, ParameterSetAlgorithmName, 3u);
    if ( !OIDInfo )
    {
      v22 = 3746;
LABEL_21:
      v7 = -2146893819;
      v23 = 2148073477LL;
LABEL_22:
      DebugTraceError(v23, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v22);
LABEL_39:
      PkiFree(hMem);
      goto LABEL_40;
    }
    v7 = 0;
    *a5 = v19;
    if ( !a3 )
      goto LABEL_39;
    if ( v45 < v19 )
    {
      v7 = -2146893784;
      v22 = 3757;
      v23 = 2148073512LL;
      goto LABEL_22;
    }
    v24 = v19;
    v25 = (_BYTE *)a3;
    if ( v19 )
    {
      do
      {
        *v25++ = 0;
        --v24;
      }
      while ( v24 );
    }
    *(_QWORD *)(a3 + 8) = OIDInfo->pszOID;
    if ( v40 )
    {
      if ( *((_DWORD *)v15 + 2) != v8 )
      {
        v22 = 3770;
        goto LABEL_21;
      }
      v26 = v13;
      v27 = (_BYTE *)SafeAllocaAllocateFromHeap(v13);
      v28 = v27;
      if ( !v27 )
      {
        v7 = -2146893810;
        v22 = 3779;
        v23 = 2148073486LL;
        goto LABEL_22;
      }
      *v27 = 0x80;
      v27[1] = v8;
      v29 = v27;
      memcpy_0(v27 + 2, (char *)v15 + *((unsigned int *)v15 + 1) + 12, v8);
    }
    else
    {
      v29 = v42;
      v26 = v8 + 2;
      v28 = 0;
    }
    v30 = pcbEncoded;
    *(_DWORD *)(a3 + 32) = pcbEncoded;
    *(_QWORD *)(a3 + 40) = a3 + 56;
    memcpy_0((void *)(a3 + 56), v29, v30);
    if ( v28 )
    {
      v31 = v28;
      do
      {
        *v31++ = 0;
        --v26;
      }
      while ( v26 );
      MSCryptFree(v28);
    }
    goto LABEL_39;
  }
  DebugTraceError((unsigned int)v14, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 3697);
  v15 = (unsigned __int16 *)hMem;
LABEL_40:
  v32 = v42;
  if ( v42 )
  {
    v33 = pcbEncoded;
    if ( pcbEncoded )
    {
      do
      {
        *v32++ = 0;
        --v33;
      }
      while ( v33 );
    }
    ((void (*)(void))pEncodePara.pfnFree)();
  }
  if ( v15 )
  {
    v34 = v39;
    v35 = v15;
    if ( v39 )
    {
      do
      {
        *(_BYTE *)v35 = 0;
        v35 = (unsigned __int16 *)((char *)v35 + 1);
        --v34;
      }
      while ( v34 );
    }
    MSCryptFree(v15);
  }
  return v7;
}

```

## disassembly

```asm
0x18004a6b4  mov     [rsp-38h+arg_0], rbx
0x18004a6b9  mov     [rsp-38h+arg_18], r9d
0x18004a6be  push    rbp
0x18004a6bf  push    rsi
0x18004a6c0  push    rdi
0x18004a6c1  push    r12
0x18004a6c3  push    r13
0x18004a6c5  push    r14
0x18004a6c7  push    r15
0x18004a6c9  mov     rbp, rsp
0x18004a6cc  sub     rsp, 70h
0x18004a6d0  xor     esi, esi
0x18004a6d2  xorps   xmm0, xmm0
0x18004a6d5  mov     [rbp+hMem], rsi
0x18004a6d9  mov     r15, r8
0x18004a6dc  mov     [rbp+var_30], esi
0x18004a6df  mov     rbx, rcx
0x18004a6e2  mov     [rbp+var_20], rsi
0x18004a6e6  movups  [rbp+pvStructInfo], xmm0
0x18004a6ea  cmp     edx, 3000Ch
0x18004a6f0  jz      short loc_18004A721
0x18004a6f2  cmp     edx, 70001h
0x18004a6f8  jz      short loc_18004A704
0x18004a6fa  mov     ebx, 80090029h
0x18004a6ff  jmp     loc_18004AA13
0x18004a704  mov     r13d, 40h ; '@'
0x18004a70a  lea     r14, aMlKem; "ML-KEM"
0x18004a711  lea     r8, aMlkemprivatese; "MLKEMPRIVATESEEDBLOB"
0x18004a718  lea     rdi, aMlkemprivatebl; "MLKEMPRIVATEBLOB"
0x18004a71f  jmp     short loc_18004A73C
0x18004a721  mov     r13d, 20h ; ' '
0x18004a727  lea     r14, aMlDsa; "ML-DSA"
0x18004a72e  lea     r8, aPqdsaprivatese; "PQDSAPRIVATESEEDBLOB"
0x18004a735  lea     rdi, aPqdsaprivatebl; "PQDSAPRIVATEBLOB"
0x18004a73c  mov     rcx, [rcx+70h]
0x18004a740  lea     rax, [rbp+var_30]
0x18004a744  lea     r12d, [r13+2]
0x18004a748  mov     [rsp+70h+pEncodePara], rax
0x18004a74d  lea     r9, [rbp+hMem]
0x18004a751  mov     [rbp+arg_8], r12d
0x18004a755  mov     rdx, rbx
0x18004a758  mov     [rbp+var_2C], 1
0x18004a75f  call    _PkcsAllocAndExportKeyBlob
0x18004a764  test    eax, eax
0x18004a766  jns     loc_18004A848
0x18004a76c  mov     rcx, [rbx+70h]
0x18004a770  lea     rax, [rbp+var_30]
0x18004a774  lea     r9, [rbp+hMem]
0x18004a778  mov     [rsp+70h+pEncodePara], rax
0x18004a77d  mov     r8, rdi
0x18004a780  mov     rdx, rbx
0x18004a783  call    _PkcsAllocAndExportKeyBlob
0x18004a788  mov     ebx, eax
0x18004a78a  test    eax, eax
0x18004a78c  jns     short loc_18004A7B2
0x18004a78e  mov     r9d, 0E71h
0x18004a794  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a79b  lea     rdx, aStatus_0; "status"
0x18004a7a2  mov     ecx, eax
0x18004a7a4  call    DebugTraceError
0x18004a7a9  mov     rsi, [rbp+hMem]
0x18004a7ad  jmp     loc_18004A9C2
0x18004a7b2  mov     edx, 19h; lpszStructType
0x18004a7b7  mov     [rbp+var_2C], esi
0x18004a7ba  mov     rsi, [rbp+hMem]
0x18004a7be  lea     r8, [rbp+pvStructInfo]; pvStructInfo
0x18004a7c2  mov     r9d, 8000h; dwFlags
0x18004a7c8  mov     eax, [rsi+8]
0x18004a7cb  lea     rcx, [rsi+0Ch]
0x18004a7cf  mov     dword ptr [rbp+pvStructInfo], eax
0x18004a7d2  mov     eax, [rsi+4]
0x18004a7d5  add     rcx, rax
0x18004a7d8  lea     rax, [rbp+arg_8]
0x18004a7dc  mov     [rsp+70h+pcbEncoded], rax; pcbEncoded
0x18004a7e1  lea     rax, [rbp+var_20]
0x18004a7e5  mov     [rsp+70h+pvEncoded], rax; pvEncoded
0x18004a7ea  lea     rax, pEncodePara
0x18004a7f1  mov     qword ptr [rbp+pvStructInfo+8], rcx
0x18004a7f5  lea     ecx, [rdx-18h]; dwCertEncodingType
0x18004a7f8  mov     [rsp+70h+pEncodePara], rax; pEncodePara
0x18004a7fd  call    cs:__imp_CryptEncodeObjectEx
0x18004a804  nop     dword ptr [rax+rax+00h]
0x18004a809  test    eax, eax
0x18004a80b  jnz     short loc_18004A84C
0x18004a80d  call    cs:__imp_GetLastError
0x18004a814  nop     dword ptr [rax+rax+00h]
0x18004a819  mov     ebx, eax
0x18004a81b  test    eax, eax
0x18004a81d  jle     short loc_18004A828
0x18004a81f  movzx   ebx, ax
0x18004a822  or      ebx, 80070000h
0x18004a828  mov     r9d, 0E83h
0x18004a82e  mov     ecx, ebx
0x18004a830  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a837  lea     rdx, aStatus_0; "status"
0x18004a83e  call    DebugTraceError
0x18004a843  jmp     loc_18004A9C2
0x18004a848  mov     rsi, [rbp+hMem]
0x18004a84c  mov     edi, [rbp+arg_8]
0x18004a84f  add     edi, 38h ; '8'
0x18004a852  cmp     edi, 38h ; '8'
0x18004a855  jnb     short loc_18004A869
0x18004a857  mov     ebx, 0C0000095h
0x18004a85c  mov     r9d, 0E8Bh
0x18004a862  mov     ecx, 0C0000095h
0x18004a867  jmp     short loc_18004A830
0x18004a869  lea     rdx, [rsi+0Ch]; unsigned __int16 *
0x18004a86d  mov     rcx, r14; unsigned __int16 *
0x18004a870  call    I_CryptMakeParameterSetAlgorithmName
0x18004a875  mov     [rbp+hMem], rax
0x18004a879  test    rax, rax
0x18004a87c  jnz     short loc_18004A890
0x18004a87e  mov     ebx, 0C000090Bh
0x18004a883  mov     r9d, 0E96h
0x18004a889  mov     ecx, 0C000090Bh
0x18004a88e  jmp     short loc_18004A830
0x18004a890  mov     r8d, 3; dwGroupId
0x18004a896  mov     rdx, rax; pvKey
0x18004a899  lea     ecx, [r8+2]; dwKeyType
0x18004a89d  call    cs:__imp_CryptFindOIDInfo
0x18004a8a4  nop     dword ptr [rax+rax+00h]
0x18004a8a9  mov     rdx, rax
0x18004a8ac  test    rax, rax
0x18004a8af  jnz     short loc_18004A8D9
0x18004a8b1  mov     r9d, 0EA2h
0x18004a8b7  mov     ebx, 80090005h
0x18004a8bc  mov     ecx, 80090005h
0x18004a8c1  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004a8c8  lea     rdx, aStatus_0; "status"
0x18004a8cf  call    DebugTraceError
0x18004a8d4  jmp     loc_18004A9B9
0x18004a8d9  mov     rax, [rbp+arg_20]
0x18004a8dd  xor     ebx, ebx
0x18004a8df  mov     [rax], edi
0x18004a8e1  test    r15, r15
0x18004a8e4  jz      loc_18004A9B9
0x18004a8ea  cmp     [rbp+arg_18], edi
0x18004a8ed  jnb     short loc_18004A901
0x18004a8ef  mov     ebx, 80090028h
0x18004a8f4  mov     r9d, 0EADh
0x18004a8fa  mov     ecx, 80090028h
0x18004a8ff  jmp     short loc_18004A8C1
0x18004a901  mov     ecx, edi
0x18004a903  mov     rax, r15
0x18004a906  test    edi, edi
0x18004a908  jz      short loc_18004A915
0x18004a90a  mov     [rax], bl
0x18004a90c  inc     rax
0x18004a90f  sub     rcx, 1
0x18004a913  jnz     short loc_18004A90A
0x18004a915  mov     rax, [rdx+8]
0x18004a919  mov     [r15+8], rax
0x18004a91d  cmp     [rbp+var_2C], ebx
0x18004a920  jz      short loc_18004A97A
0x18004a922  cmp     [rsi+8], r13d
0x18004a926  jz      short loc_18004A930
0x18004a928  mov     r9d, 0EBAh
0x18004a92e  jmp     short loc_18004A8B7
0x18004a930  mov     ecx, r12d
0x18004a933  mov     r14d, r12d
0x18004a936  call    SafeAllocaAllocateFromHeap
0x18004a93b  mov     rdi, rax
0x18004a93e  test    rax, rax
0x18004a941  jnz     short loc_18004A958
0x18004a943  mov     ebx, 8009000Eh
0x18004a948  mov     r9d, 0EC3h
0x18004a94e  mov     ecx, 8009000Eh
0x18004a953  jmp     loc_18004A8C1
0x18004a958  mov     byte ptr [rax], 80h
0x18004a95b  lea     rcx, [rax+2]; void *
0x18004a95f  mov     [rax+1], r13b
0x18004a963  mov     r12, rax
0x18004a966  mov     edx, [rsi+4]
0x18004a969  add     rdx, 0Ch
0x18004a96d  mov     r8d, r13d; Size
0x18004a970  add     rdx, rsi; Src
0x18004a973  call    memcpy_0
0x18004a978  jmp     short loc_18004A984
0x18004a97a  mov     r12, [rbp+var_20]
0x18004a97e  lea     r14d, [r13+2]
0x18004a982  xor     edi, edi
0x18004a984  mov     eax, [rbp+arg_8]
0x18004a987  lea     rcx, [r15+38h]; void *
0x18004a98b  mov     r8d, eax; Size
0x18004a98e  mov     [r15+20h], eax
0x18004a992  mov     rdx, r12; Src
0x18004a995  mov     [r15+28h], rcx
0x18004a999  call    memcpy_0
0x18004a99e  test    rdi, rdi
0x18004a9a1  jz      short loc_18004A9B9
0x18004a9a3  mov     rax, rdi
0x18004a9a6  mov     [rax], bl
0x18004a9a8  inc     rax
0x18004a9ab  sub     r14, 1
0x18004a9af  jnz     short loc_18004A9A6
0x18004a9b1  mov     rcx, rdi
0x18004a9b4  call    MSCryptFree
0x18004a9b9  mov     rcx, [rbp+hMem]; hMem
0x18004a9bd  call    PkiFree
0x18004a9c2  mov     rcx, [rbp+var_20]
0x18004a9c6  test    rcx, rcx
0x18004a9c9  jz      short loc_18004A9EF
0x18004a9cb  mov     eax, [rbp+arg_8]
0x18004a9ce  test    rax, rax
0x18004a9d1  jz      short loc_18004A9E3
0x18004a9d3  mov     byte ptr [rcx], 0
0x18004a9d6  inc     rcx
0x18004a9d9  sub     rax, 1
0x18004a9dd  jnz     short loc_18004A9D3
0x18004a9df  mov     rcx, [rbp+var_20]
0x18004a9e3  mov     rax, cs:pEncodePara.pfnFree
0x18004a9ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9ef  test    rsi, rsi
0x18004a9f2  jz      short loc_18004AA13
0x18004a9f4  mov     eax, [rbp+var_30]
0x18004a9f7  mov     rcx, rsi
0x18004a9fa  test    rax, rax
0x18004a9fd  jz      short loc_18004AA0B
0x18004a9ff  mov     byte ptr [rcx], 0
0x18004aa02  inc     rcx
0x18004aa05  sub     rax, 1
0x18004aa09  jnz     short loc_18004A9FF
0x18004aa0b  mov     rcx, rsi
0x18004aa0e  call    MSCryptFree
0x18004aa13  mov     eax, ebx
0x18004aa15  mov     rbx, [rsp+70h+arg_0]
0x18004aa1d  add     rsp, 70h
0x18004aa21  pop     r15
0x18004aa23  pop     r14
0x18004aa25  pop     r13
0x18004aa27  pop     r12
0x18004aa29  pop     rdi
0x18004aa2a  pop     rsi
0x18004aa2b  pop     rbp
0x18004aa2c  retn
```
