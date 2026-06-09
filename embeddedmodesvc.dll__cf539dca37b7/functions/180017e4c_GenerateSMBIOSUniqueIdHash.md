# GenerateSMBIOSUniqueIdHash

- ea: `0x180017e4c`
- end: `0x18001809b`
- name: `GenerateSMBIOSUniqueIdHash`
- size: `591`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR *, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001839c`

## callees

- `0x180002ee0`
- `0x180003940`
- `0x18001053c`
- `0x180017e4c`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x180017f92`
- `bcrypt!BCryptHashData` at `0x180017f92`
- `bcrypt!BCryptDestroyHash` at `0x180017fb4`
- `bcrypt!BCryptDestroyHash` at `0x180018030`
- `bcrypt!BCryptDestroyHash` at `0x18001806a`
- `bcrypt!BCryptDestroyHash` at `0x180017fb4`
- `bcrypt!BCryptDestroyHash` at `0x180018030`
- `bcrypt!BCryptDestroyHash` at `0x18001806a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180017f10`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180017f36`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180017faa`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180018026`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001807b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180017f10`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180017f36`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180017faa`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180018026`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001807b`
- `bcrypt!BCryptCreateHash` at `0x180017f73`
- `bcrypt!BCryptCreateHash` at `0x180017f73`
- `bcrypt!BCryptFinishHash` at `0x180018046`
- `bcrypt!BCryptFinishHash` at `0x180018046`
- `bcrypt!BCryptGetProperty` at `0x180017ef8`
- `bcrypt!BCryptGetProperty` at `0x180017fe9`
- `bcrypt!BCryptGetProperty` at `0x180017ef8`
- `bcrypt!BCryptGetProperty` at `0x180017fe9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180017ea8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180017ea8`

## pseudocode

```c
__int64 __fastcall GenerateSMBIOSUniqueIdHash(PUCHAR pbInput, ULONG cbInput, PUCHAR *a3, _DWORD *a4)
{
  NTSTATUS Property; // ebx
  UCHAR *v10; // rax
  UCHAR *v11; // rax
  unsigned __int64 v12; // rdx
  PUCHAR v13; // rcx
  BCRYPT_HASH_HANDLE v14; // rcx
  ULONG cbOutput; // [rsp+40h] [rbp-30h] BYREF
  UCHAR v16[4]; // [rsp+44h] [rbp-2Ch] BYREF
  UCHAR pbOutput[4]; // [rsp+48h] [rbp-28h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-20h] BYREF
  UCHAR *v19; // [rsp+58h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+60h] [rbp-10h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  v19 = 0;
  cbOutput = 4;
  *(_DWORD *)pbOutput = 0;
  *(_DWORD *)v16 = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( (Property & 0xC0000000) == 0xC0000000 )
    goto LABEL_2;
  Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, cbOutput, &cbOutput, 0);
  if ( (Property & 0xC0000000) == 0xC0000000 )
    goto LABEL_4;
  v10 = (UCHAR *)operator new[](*(unsigned int *)pbOutput, (const struct std::nothrow_t *)&std::nothrow);
  v19 = v10;
  if ( !v10 )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
LABEL_7:
    std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v19);
    return 2147942414LL;
  }
  Property = BCryptCreateHash(phAlgorithm, &phHash, v10, *(ULONG *)pbOutput, 0, 0, 0);
  if ( (Property & 0xC0000000) == 0xC0000000 )
  {
LABEL_4:
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
LABEL_2:
    std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v19);
    return Property | 0x10000000u;
  }
  Property = BCryptHashData(phHash, pbInput, cbInput, 0);
  if ( (Property & 0xC0000000) == 0xC0000000 )
    goto LABEL_10;
  cbOutput = 4;
  Property = BCryptGetProperty(phHash, L"HashDigestLength", v16, 4u, &cbOutput, 0);
  if ( (Property & 0xC0000000) == 0xC0000000 )
    goto LABEL_10;
  v11 = (UCHAR *)operator new[](*(unsigned int *)v16, (const struct std::nothrow_t *)&std::nothrow);
  v13 = *a3;
  *a3 = v11;
  if ( v13 )
    operator delete(v13, v12);
  if ( !*a3 )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    BCryptDestroyHash(phHash);
    goto LABEL_7;
  }
  Property = BCryptFinishHash(phHash, *a3, *(ULONG *)v16, 0);
  if ( (Property & 0xC0000000) == 0xC0000000 )
  {
LABEL_10:
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    BCryptDestroyHash(phHash);
    goto LABEL_2;
  }
  v14 = phHash;
  *a4 = *(_DWORD *)v16;
  if ( v14 )
    BCryptDestroyHash(v14);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&v19);
  return 0;
}

```

## disassembly

```asm
0x180017e4c  push    rbp
0x180017e4e  push    rbx
0x180017e4f  push    rsi
0x180017e50  push    rdi
0x180017e51  push    r13
0x180017e53  push    r14
0x180017e55  push    r15
0x180017e57  mov     rbp, rsp
0x180017e5a  sub     rsp, 70h
0x180017e5e  mov     rsi, r9
0x180017e61  mov     [rbp+phAlgorithm], 0
0x180017e69  mov     rdi, r8
0x180017e6c  mov     [rbp+phHash], 0
0x180017e74  mov     r14d, edx
0x180017e77  mov     [rbp+var_18], 0
0x180017e7f  mov     r15, rcx
0x180017e82  mov     [rbp+cbOutput], 4
0x180017e89  xor     r9d, r9d; dwFlags
0x180017e8c  mov     dword ptr [rbp+pbOutput], 0
0x180017e93  xor     r8d, r8d; pszImplementation
0x180017e96  mov     dword ptr [rbp+var_2C], 0
0x180017e9d  lea     rdx, pszAlgId; "SHA256"
0x180017ea4  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180017ea8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180017eae  mov     r13d, 0C0000000h
0x180017eb4  mov     ecx, eax
0x180017eb6  and     ecx, r13d
0x180017eb9  mov     ebx, eax
0x180017ebb  cmp     ecx, r13d
0x180017ebe  jnz     short loc_180017ED4
0x180017ec0  lea     rcx, [rbp+var_18]
0x180017ec4  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180017ec9  bts     ebx, 1Ch
0x180017ecd  mov     eax, ebx
0x180017ecf  jmp     loc_18001808C
0x180017ed4  mov     r9d, [rbp+cbOutput]; cbOutput
0x180017ed8  lea     rax, [rbp+cbOutput]
0x180017edc  mov     rcx, [rbp+phAlgorithm]; hObject
0x180017ee0  lea     r8, [rbp+pbOutput]; pbOutput
0x180017ee4  mov     [rsp+70h+dwFlags], 0; dwFlags
0x180017eec  lea     rdx, pszProperty; "ObjectLength"
0x180017ef3  mov     [rsp+70h+pcbResult], rax; pcbResult
0x180017ef8  call    cs:__imp_BCryptGetProperty
0x180017efe  mov     ecx, eax
0x180017f00  mov     ebx, eax
0x180017f02  and     ecx, r13d
0x180017f05  cmp     ecx, r13d
0x180017f08  jnz     short loc_180017F18
0x180017f0a  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180017f0e  xor     edx, edx; dwFlags
0x180017f10  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180017f16  jmp     short loc_180017EC0
0x180017f18  mov     ecx, dword ptr [rbp+pbOutput]; unsigned __int64
0x180017f1b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017f22  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180017f27  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180017f2b  mov     [rbp+var_18], rax
0x180017f2f  test    rax, rax
0x180017f32  jnz     short loc_180017F4F
0x180017f34  xor     edx, edx; dwFlags
0x180017f36  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180017f3c  lea     rcx, [rbp+var_18]
0x180017f40  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180017f45  mov     eax, 8007000Eh
0x180017f4a  jmp     loc_18001808C
0x180017f4f  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x180017f53  lea     rdx, [rbp+phHash]; phHash
0x180017f57  mov     [rsp+70h+var_40], 0; dwFlags
0x180017f5f  mov     r8, rax; pbHashObject
0x180017f62  mov     [rsp+70h+dwFlags], 0; cbSecret
0x180017f6a  mov     [rsp+70h+pcbResult], 0; pbSecret
0x180017f73  call    cs:__imp_BCryptCreateHash
0x180017f79  mov     ecx, eax
0x180017f7b  mov     ebx, eax
0x180017f7d  and     ecx, r13d
0x180017f80  cmp     ecx, r13d
0x180017f83  jz      short loc_180017F0A
0x180017f85  mov     rcx, [rbp+phHash]; hHash
0x180017f89  xor     r9d, r9d; dwFlags
0x180017f8c  mov     r8d, r14d; cbInput
0x180017f8f  mov     rdx, r15; pbInput
0x180017f92  call    cs:__imp_BCryptHashData
0x180017f98  mov     ecx, eax
0x180017f9a  mov     ebx, eax
0x180017f9c  and     ecx, r13d
0x180017f9f  cmp     ecx, r13d
0x180017fa2  jnz     short loc_180017FBF
0x180017fa4  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180017fa8  xor     edx, edx; dwFlags
0x180017faa  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180017fb0  mov     rcx, [rbp+phHash]; hHash
0x180017fb4  call    cs:__imp_BCryptDestroyHash
0x180017fba  jmp     loc_180017EC0
0x180017fbf  mov     rcx, [rbp+phHash]; hObject
0x180017fc3  lea     rax, [rbp+cbOutput]
0x180017fc7  mov     r9d, 4; cbOutput
0x180017fcd  mov     [rsp+70h+dwFlags], 0; dwFlags
0x180017fd5  lea     r8, [rbp+var_2C]; pbOutput
0x180017fd9  mov     [rbp+cbOutput], r9d
0x180017fdd  lea     rdx, aHashdigestleng; "HashDigestLength"
0x180017fe4  mov     [rsp+70h+pcbResult], rax; pcbResult
0x180017fe9  call    cs:__imp_BCryptGetProperty
0x180017fef  mov     ecx, eax
0x180017ff1  mov     ebx, eax
0x180017ff3  and     ecx, r13d
0x180017ff6  cmp     ecx, r13d
0x180017ff9  jz      short loc_180017FA4
0x180017ffb  mov     ecx, dword ptr [rbp+var_2C]; unsigned __int64
0x180017ffe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018005  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001800a  mov     rcx, [rdi]; void *
0x18001800d  mov     [rdi], rax
0x180018010  test    rcx, rcx
0x180018013  jz      short loc_18001801A
0x180018015  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001801a  mov     rdx, [rdi]; pbOutput
0x18001801d  test    rdx, rdx
0x180018020  jnz     short loc_18001803B
0x180018022  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180018026  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001802c  mov     rcx, [rbp+phHash]; hHash
0x180018030  call    cs:__imp_BCryptDestroyHash
0x180018036  jmp     loc_180017F3C
0x18001803b  mov     r8d, dword ptr [rbp+var_2C]; cbOutput
0x18001803f  xor     r9d, r9d; dwFlags
0x180018042  mov     rcx, [rbp+phHash]; hHash
0x180018046  call    cs:__imp_BCryptFinishHash
0x18001804c  mov     ecx, eax
0x18001804e  mov     ebx, eax
0x180018050  and     ecx, r13d
0x180018053  cmp     ecx, r13d
0x180018056  jz      loc_180017FA4
0x18001805c  mov     rcx, [rbp+phHash]; hHash
0x180018060  mov     eax, dword ptr [rbp+var_2C]
0x180018063  mov     [rsi], eax
0x180018065  test    rcx, rcx
0x180018068  jz      short loc_180018070
0x18001806a  call    cs:__imp_BCryptDestroyHash
0x180018070  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180018074  test    rcx, rcx
0x180018077  jz      short loc_180018081
0x180018079  xor     edx, edx; dwFlags
0x18001807b  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180018081  lea     rcx, [rbp+var_18]
0x180018085  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x18001808a  xor     eax, eax
0x18001808c  add     rsp, 70h
0x180018090  pop     r15
0x180018092  pop     r14
0x180018094  pop     r13
0x180018096  pop     rdi
0x180018097  pop     rsi
0x180018098  pop     rbx
0x180018099  pop     rbp
0x18001809a  retn
```
