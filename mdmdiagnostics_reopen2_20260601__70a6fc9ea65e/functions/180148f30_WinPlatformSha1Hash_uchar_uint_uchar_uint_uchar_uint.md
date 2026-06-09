# WinPlatformSha1Hash(uchar *,uint,uchar *,uint,uchar *,uint)

- ea: `0x180148f30`
- end: `0x1801490eb`
- name: `?WinPlatformSha1Hash@@YAJPEAEI0I0I@Z`
- size: `443`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbSecret, ULONG cbSecret, PUCHAR, ULONG)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180019064`
- `0x1800190a4`
- `0x18001a054`
- `0x180148f30`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x180148fcc`
- `bcrypt!BCryptGetProperty` at `0x180148fcc`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180148f96`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180148f96`
- `bcrypt!BCryptFinishHash` at `0x18014906a`
- `bcrypt!BCryptFinishHash` at `0x18014906a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801490c3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1801490c3`
- `bcrypt!BCryptDestroyHash` at `0x180149081`
- `bcrypt!BCryptDestroyHash` at `0x180149081`
- `bcrypt!BCryptHashData` at `0x180149049`
- `bcrypt!BCryptHashData` at `0x180149049`
- `bcrypt!BCryptCreateHash` at `0x18014902a`
- `bcrypt!BCryptCreateHash` at `0x18014902a`

## pseudocode

```c
__int64 __fastcall WinPlatformSha1Hash(
        PUCHAR pbInput,
        ULONG cbInput,
        PUCHAR pbSecret,
        ULONG cbSecret,
        PUCHAR a5,
        ULONG a6)
{
  void *v6; // rdi
  ULONG v11; // r9d
  NTSTATUS Property; // ebx
  __int64 v13; // rax
  _BYTE *v14; // rcx
  ULONG cbOutput; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-10h] BYREF
  ULONG pbOutput; // [rsp+A8h] [rbp+48h] BYREF

  v6 = 0;
  phAlgorithm = 0;
  phHash = 0;
  pbOutput = 0;
  cbOutput = 4;
  if ( cbSecret && pbSecret )
    v11 = 8;
  else
    v11 = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", v11);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", (PUCHAR)&pbOutput, cbOutput, &cbOutput, 0);
    if ( Property >= 0 )
    {
      v6 = operator new(pbOutput);
      memset_0(v6, 0, pbOutput);
      memset_0(v6, 0, pbOutput);
      Property = BCryptCreateHash(phAlgorithm, &phHash, (PUCHAR)v6, pbOutput, pbSecret, cbSecret, 0);
      if ( Property >= 0 )
      {
        Property = BCryptHashData(phHash, pbInput, cbInput, 0);
        if ( Property >= 0 )
          Property = BCryptFinishHash(phHash, a5, a6, 0);
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v6 )
  {
    v13 = pbOutput;
    v14 = v6;
    if ( pbOutput )
    {
      do
      {
        *v14++ = 0;
        --v13;
      }
      while ( v13 );
    }
    operator delete(v6);
  }
  pbOutput = 0;
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x180148f30  mov     [rsp-28h+arg_0], rbx
0x180148f35  mov     [rsp-28h+arg_8], rsi
0x180148f3a  push    rbp
0x180148f3b  push    rdi
0x180148f3c  push    r12
0x180148f3e  push    r14
0x180148f40  push    r15
0x180148f42  mov     rbp, rsp
0x180148f45  sub     rsp, 60h
0x180148f49  xor     edi, edi
0x180148f4b  mov     [rbp+phAlgorithm], 0
0x180148f53  mov     [rbp+phHash], 0
0x180148f5b  mov     r14d, r9d
0x180148f5e  mov     [rbp+pbOutput], edi
0x180148f61  mov     rsi, r8
0x180148f64  mov     [rbp+cbOutput], 4
0x180148f6b  mov     r15d, edx
0x180148f6e  mov     r12, rcx
0x180148f71  test    r9d, r9d
0x180148f74  jz      short loc_180148F81
0x180148f76  test    r8, r8
0x180148f79  jz      short loc_180148F81
0x180148f7b  lea     r9d, [rdi+8]
0x180148f7f  jmp     short loc_180148F84
0x180148f81  xor     r9d, r9d; dwFlags
0x180148f84  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x180148f8b  lea     rdx, aSha1_0; "SHA1"
0x180148f92  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180148f96  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180148f9d  nop     dword ptr [rax+rax+00h]
0x180148fa2  mov     ebx, eax
0x180148fa4  test    eax, eax
0x180148fa6  js      loc_180149078
0x180148fac  mov     r9d, [rbp+cbOutput]; cbOutput
0x180148fb0  lea     rax, [rbp+cbOutput]
0x180148fb4  mov     rcx, [rbp+phAlgorithm]; hObject
0x180148fb8  lea     r8, [rbp+pbOutput]; pbOutput
0x180148fbc  mov     [rsp+60h+dwFlags], edi; dwFlags
0x180148fc0  lea     rdx, pszProperty; "ObjectLength"
0x180148fc7  mov     [rsp+60h+pcbResult], rax; pcbResult
0x180148fcc  call    cs:__imp_BCryptGetProperty
0x180148fd3  nop     dword ptr [rax+rax+00h]
0x180148fd8  mov     ebx, eax
0x180148fda  test    eax, eax
0x180148fdc  js      loc_180149078
0x180148fe2  mov     ecx, [rbp+pbOutput]; Size
0x180148fe5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180148fea  mov     r8d, [rbp+pbOutput]; Size
0x180148fee  xor     edx, edx; Val
0x180148ff0  mov     rcx, rax; void *
0x180148ff3  mov     rdi, rax
0x180148ff6  call    memset_0
0x180148ffb  mov     r8d, [rbp+pbOutput]; Size
0x180148fff  xor     edx, edx; Val
0x180149001  mov     rcx, rdi; void *
0x180149004  call    memset_0
0x180149009  mov     r9d, [rbp+pbOutput]; cbHashObject
0x18014900d  lea     rdx, [rbp+phHash]; phHash
0x180149011  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180149015  mov     r8, rdi; pbHashObject
0x180149018  mov     [rsp+60h+var_30], 0; dwFlags
0x180149020  mov     [rsp+60h+dwFlags], r14d; cbSecret
0x180149025  mov     [rsp+60h+pcbResult], rsi; pbSecret
0x18014902a  call    cs:__imp_BCryptCreateHash
0x180149031  nop     dword ptr [rax+rax+00h]
0x180149036  mov     ebx, eax
0x180149038  test    eax, eax
0x18014903a  js      short loc_180149078
0x18014903c  mov     rcx, [rbp+phHash]; hHash
0x180149040  xor     r9d, r9d; dwFlags
0x180149043  mov     r8d, r15d; cbInput
0x180149046  mov     rdx, r12; pbInput
0x180149049  call    cs:__imp_BCryptHashData
0x180149050  nop     dword ptr [rax+rax+00h]
0x180149055  mov     ebx, eax
0x180149057  test    eax, eax
0x180149059  js      short loc_180149078
0x18014905b  mov     r8d, [rbp+arg_28]; cbOutput
0x18014905f  xor     r9d, r9d; dwFlags
0x180149062  mov     rdx, [rbp+arg_20]; pbOutput
0x180149066  mov     rcx, [rbp+phHash]; hHash
0x18014906a  call    cs:__imp_BCryptFinishHash
0x180149071  nop     dword ptr [rax+rax+00h]
0x180149076  mov     ebx, eax
0x180149078  mov     rcx, [rbp+phHash]; hHash
0x18014907c  test    rcx, rcx
0x18014907f  jz      short loc_18014908D
0x180149081  call    cs:__imp_BCryptDestroyHash
0x180149088  nop     dword ptr [rax+rax+00h]
0x18014908d  test    rdi, rdi
0x180149090  jz      short loc_1801490B1
0x180149092  mov     eax, [rbp+pbOutput]
0x180149095  mov     rcx, rdi
0x180149098  test    rax, rax
0x18014909b  jz      short loc_1801490A9
0x18014909d  mov     byte ptr [rcx], 0
0x1801490a0  inc     rcx
0x1801490a3  sub     rax, 1
0x1801490a7  jnz     short loc_18014909D
0x1801490a9  mov     rcx, rdi; Block
0x1801490ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801490b1  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1801490b5  mov     [rbp+pbOutput], 0
0x1801490bc  test    rcx, rcx
0x1801490bf  jz      short loc_1801490CF
0x1801490c1  xor     edx, edx; dwFlags
0x1801490c3  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1801490ca  nop     dword ptr [rax+rax+00h]
0x1801490cf  lea     r11, [rsp+60h+var_s0]
0x1801490d4  mov     eax, ebx
0x1801490d6  mov     rbx, [r11+30h]
0x1801490da  mov     rsi, [r11+38h]
0x1801490de  mov     rsp, r11
0x1801490e1  pop     r15
0x1801490e3  pop     r14
0x1801490e5  pop     r12
0x1801490e7  pop     rdi
0x1801490e8  pop     rbp
0x1801490e9  retn
```
