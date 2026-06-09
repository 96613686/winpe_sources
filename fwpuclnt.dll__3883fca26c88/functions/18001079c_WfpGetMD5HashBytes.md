# WfpGetMD5HashBytes

- ea: `0x18001079c`
- end: `0x180010a26`
- name: `WfpGetMD5HashBytes`
- size: `650`
- prototype: `__int64 __fastcall(ULONG cbInput, PUCHAR pbInput)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018fc0`
- `0x18001c02c`

## callees

- `0x18000438c`
- `0x180006e40`
- `0x180007e38`
- `0x18001079c`
- `0x180011500`
- `0x180012bd0`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x180010955`
- `bcrypt!BCryptHashData` at `0x180010955`
- `bcrypt!BCryptFinishHash` at `0x18001097c`
- `bcrypt!BCryptFinishHash` at `0x18001097c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180010804`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180010804`
- `bcrypt!BCryptDestroyHash` at `0x1800109c0`
- `bcrypt!BCryptDestroyHash` at `0x1800109c0`
- `bcrypt!BCryptCreateHash` at `0x180010924`
- `bcrypt!BCryptCreateHash` at `0x180010924`
- `bcrypt!BCryptGetProperty` at `0x18001084f`
- `bcrypt!BCryptGetProperty` at `0x1800108ab`
- `bcrypt!BCryptGetProperty` at `0x18001084f`
- `bcrypt!BCryptGetProperty` at `0x1800108ab`

## string_xrefs

- `0x180010814`: `BCryptOpenAlgorithmProvider(L"MD5")`
- `0x1800108fd`: `SecurityRealmPolicyHmacKey`
- `0x180010934`: `BCryptCreateHash`

## pseudocode

```c
__int64 __fastcall WfpGetMD5HashBytes(ULONG cbInput, PUCHAR pbInput, _DWORD *a3, _QWORD *a4)
{
  unsigned int Property; // eax
  __int64 v5; // rcx
  const char *v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rbx
  PUCHAR v10; // [rsp+40h] [rbp-29h]
  PUCHAR pbHashObject; // [rsp+48h] [rbp-21h]
  UCHAR v12[4]; // [rsp+50h] [rbp-19h]
  UCHAR pbOutput[4]; // [rsp+54h] [rbp-15h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-11h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+60h] [rbp-9h]
  ULONG pcbResult; // [rsp+68h] [rbp-1h] BYREF

  *a3 = 0;
  *a4 = 0;
  phAlgorithm = 0;
  phHash = 0;
  *(_DWORD *)pbOutput = 0;
  pbHashObject = 0;
  *(_DWORD *)v12 = 0;
  v10 = 0;
  pcbResult = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"MD5", 0, 8u);
  if ( Property )
  {
    v6 = "BCryptOpenAlgorithmProvider(L\"MD5\")";
  }
  else
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( !Property )
    {
      WfpPoolAllocNonPaged(*(unsigned int *)pbOutput);
      v7 = 3221225495LL;
      v6 = "WfpMemAlloc";
      goto LABEL_4;
    }
    v6 = "BCryptGetProperty(L\"ObjectLength\")";
  }
  v7 = Property;
LABEL_4:
  v8 = WfpReportSysErrorAsNtStatus(v5, v6, v7);
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v8 )
    WfpReportError(v8, "WfpGetMD5HashBytes");
  return v8;
}

```

## disassembly

```asm
0x18001079c  push    rbp
0x18001079e  push    rbx
0x18001079f  push    rsi
0x1800107a0  push    rdi
0x1800107a1  push    r12
0x1800107a3  push    r13
0x1800107a5  push    r14
0x1800107a7  push    r15
0x1800107a9  lea     rbp, [rsp-1Fh]
0x1800107ae  sub     rsp, 88h
0x1800107b5  mov     rax, cs:__security_cookie
0x1800107bc  xor     rax, rsp
0x1800107bf  mov     [rbp+57h+var_50], rax
0x1800107c3  xor     esi, esi
0x1800107c5  mov     r15, r9
0x1800107c8  mov     [r8], esi
0x1800107cb  mov     r14, r8
0x1800107ce  mov     r13, rdx
0x1800107d1  mov     [r9], rsi
0x1800107d4  mov     r12d, ecx
0x1800107d7  mov     [rbp+57h+phAlgorithm], rsi
0x1800107db  lea     r9d, [rsi+8]; dwFlags
0x1800107df  mov     [rbp+57h+phHash], rsi
0x1800107e3  xor     r8d, r8d; pszImplementation
0x1800107e6  mov     dword ptr [rbp+57h+pbOutput], esi
0x1800107e9  lea     rdx, pszAlgId; "MD5"
0x1800107f0  mov     [rbp+57h+pbHashObject], rsi
0x1800107f4  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x1800107f8  mov     dword ptr [rbp+57h+var_70], esi
0x1800107fb  mov     edi, esi
0x1800107fd  mov     [rbp+57h+var_80], rsi
0x180010801  mov     [rbp+57h+var_58], esi
0x180010804  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001080b  nop     dword ptr [rax+rax+00h]
0x180010810  test    eax, eax
0x180010812  jz      short loc_18001082B
0x180010814  lea     rdx, aBcryptopenalgo_0; "BCryptOpenAlgorithmProvider(L\"MD5\")"
0x18001081b  mov     r8d, eax
0x18001081e  call    WfpReportSysErrorAsNtStatus
0x180010823  mov     rbx, rax
0x180010826  jmp     loc_1800109B7
0x18001082b  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x18001082f  lea     rax, [rbp+57h+var_58]
0x180010833  mov     ebx, 4
0x180010838  mov     [rsp+0C0h+dwFlags], esi; dwFlags
0x18001083c  mov     r9d, ebx; cbOutput
0x18001083f  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x180010844  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x180010848  lea     rdx, pszProperty; "ObjectLength"
0x18001084f  call    cs:__imp_BCryptGetProperty
0x180010856  nop     dword ptr [rax+rax+00h]
0x18001085b  test    eax, eax
0x18001085d  jz      short loc_180010868
0x18001085f  lea     rdx, aBcryptgetprope_0; "BCryptGetProperty(L\"ObjectLength\")"
0x180010866  jmp     short loc_18001081B
0x180010868  mov     ecx, dword ptr [rbp+57h+pbOutput]; dwBytes
0x18001086b  lea     r8, [rbp+57h+pbHashObject]
0x18001086f  call    WfpPoolAllocNonPaged
0x180010874  mov     rdi, [rbp+57h+pbHashObject]
0x180010878  test    rdi, rdi
0x18001087b  jnz     short loc_18001088C
0x18001087d  mov     r8d, 0C0000017h
0x180010883  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x18001088a  jmp     short loc_18001081E
0x18001088c  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x180010890  lea     rax, [rbp+57h+var_58]
0x180010894  mov     [rsp+0C0h+dwFlags], esi; dwFlags
0x180010898  lea     r8, [rbp+57h+var_70]; pbOutput
0x18001089c  mov     r9d, ebx; cbOutput
0x18001089f  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x1800108a4  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800108ab  call    cs:__imp_BCryptGetProperty
0x1800108b2  nop     dword ptr [rax+rax+00h]
0x1800108b7  test    eax, eax
0x1800108b9  jz      short loc_1800108C7
0x1800108bb  lea     rdx, aBcryptgetprope_1; "BCryptGetProperty(L\"HashDigestLength\""...
0x1800108c2  jmp     loc_18001081B
0x1800108c7  mov     ecx, dword ptr [rbp+57h+var_70]; dwBytes
0x1800108ca  lea     r8, [rbp+57h+var_80]
0x1800108ce  call    WfpPoolAllocNonPaged
0x1800108d3  mov     rsi, [rbp+57h+var_80]
0x1800108d7  mov     rbx, rax
0x1800108da  test    rsi, rsi
0x1800108dd  jnz     short loc_1800108F9
0x1800108df  mov     r8d, 0C0000017h
0x1800108e5  lea     rdx, aWfpmemalloc; "WfpMemAlloc"
0x1800108ec  call    WfpReportSysErrorAsNtStatus
0x1800108f1  mov     rbx, rax
0x1800108f4  jmp     loc_1800109B5
0x1800108f9  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x1800108fd  lea     rax, pbSecret; "SecurityRealmPolicyHmacKey"
0x180010904  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180010908  lea     rdx, [rbp+57h+phHash]; phHash
0x18001090c  mov     [rsp+0C0h+var_90], 0; dwFlags
0x180010914  mov     r8, rdi; pbHashObject
0x180010917  mov     [rsp+0C0h+dwFlags], 1Ah; cbSecret
0x18001091f  mov     [rsp+0C0h+pcbResult], rax; pbSecret
0x180010924  call    cs:__imp_BCryptCreateHash
0x18001092b  nop     dword ptr [rax+rax+00h]
0x180010930  test    eax, eax
0x180010932  jz      short loc_180010948
0x180010934  lea     rdx, aBcryptcreateha_0; "BCryptCreateHash"
0x18001093b  mov     r8d, eax
0x18001093e  call    WfpReportSysErrorAsNtStatus
0x180010943  mov     rbx, rax
0x180010946  jmp     short loc_1800109A7
0x180010948  mov     rcx, [rbp+57h+phHash]; hHash
0x18001094c  xor     r9d, r9d; dwFlags
0x18001094f  mov     r8d, r12d; cbInput
0x180010952  mov     rdx, r13; pbInput
0x180010955  call    cs:__imp_BCryptHashData
0x18001095c  nop     dword ptr [rax+rax+00h]
0x180010961  test    eax, eax
0x180010963  jz      short loc_18001096E
0x180010965  lea     rdx, aBcrypthashdata_0; "BCryptHashData"
0x18001096c  jmp     short loc_18001093B
0x18001096e  mov     r8d, dword ptr [rbp+57h+var_70]; cbOutput
0x180010972  xor     r9d, r9d; dwFlags
0x180010975  mov     rcx, [rbp+57h+phHash]; hHash
0x180010979  mov     rdx, rsi; pbOutput
0x18001097c  call    cs:__imp_BCryptFinishHash
0x180010983  nop     dword ptr [rax+rax+00h]
0x180010988  test    eax, eax
0x18001098a  jz      short loc_180010995
0x18001098c  lea     rdx, aBcryptfinishha_0; "BCryptFinishHash"
0x180010993  jmp     short loc_18001093B
0x180010995  mov     eax, dword ptr [rbp+57h+var_70]
0x180010998  mov     [r15], rsi
0x18001099b  xor     esi, esi
0x18001099d  mov     [rbp+57h+var_80], rsi
0x1800109a1  mov     dword ptr [rbp+57h+var_70], esi
0x1800109a4  mov     [r14], eax
0x1800109a7  test    rsi, rsi
0x1800109aa  jz      short loc_1800109B5
0x1800109ac  lea     rcx, [rbp+57h+var_80]
0x1800109b0  call    WfpMemFree
0x1800109b5  xor     esi, esi
0x1800109b7  mov     rcx, [rbp+57h+phHash]; hHash
0x1800109bb  test    rcx, rcx
0x1800109be  jz      short loc_1800109CC
0x1800109c0  call    cs:__imp_BCryptDestroyHash
0x1800109c7  nop     dword ptr [rax+rax+00h]
0x1800109cc  test    rdi, rdi
0x1800109cf  jz      short loc_1800109EE
0x1800109d1  mov     eax, dword ptr [rbp+57h+pbOutput]
0x1800109d4  test    rax, rax
0x1800109d7  jz      short loc_1800109E5
0x1800109d9  mov     [rdi], sil
0x1800109dc  inc     rdi
0x1800109df  sub     rax, 1
0x1800109e3  jnz     short loc_1800109D9
0x1800109e5  lea     rcx, [rbp+57h+pbHashObject]
0x1800109e9  call    WfpMemFree
0x1800109ee  test    rbx, rbx
0x1800109f1  jz      short loc_180010A02
0x1800109f3  lea     rdx, aWfpgetmd5hashb; "WfpGetMD5HashBytes"
0x1800109fa  mov     rcx, rbx
0x1800109fd  call    WfpReportError
0x180010a02  mov     rax, rbx
0x180010a05  mov     rcx, [rbp+57h+var_50]
0x180010a09  xor     rcx, rsp; StackCookie
0x180010a0c  call    __security_check_cookie
0x180010a11  add     rsp, 88h
0x180010a18  pop     r15
0x180010a1a  pop     r14
0x180010a1c  pop     r13
0x180010a1e  pop     r12
0x180010a20  pop     rdi
0x180010a21  pop     rsi
0x180010a22  pop     rbx
0x180010a23  pop     rbp
0x180010a24  retn
```
