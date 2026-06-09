# LPA::Lpd::DownloadInstance::EncryptConfirmationCode(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800ae32c`
- end: `0x1800ae529`
- name: `?EncryptConfirmationCode@DownloadInstance@Lpd@LPA@@CAJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@5@AEAV65@@Z`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800adc8c`

## callees

- `0x18005e224`
- `0x180071320`
- `0x18007516c`
- `0x18009972c`
- `0x1800a2ddc`
- `0x1800a7f30`
- `0x1800ae32c`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x1800ae452`
- `bcrypt!BCryptHashData` at `0x1800ae4a7`
- `bcrypt!BCryptHashData` at `0x1800ae452`
- `bcrypt!BCryptHashData` at `0x1800ae4a7`
- `bcrypt!BCryptGetProperty` at `0x1800ae3ca`
- `bcrypt!BCryptGetProperty` at `0x1800ae3ca`
- `bcrypt!BCryptCreateHash` at `0x1800ae3ff`
- `bcrypt!BCryptCreateHash` at `0x1800ae3ff`
- `bcrypt!BCryptDestroyHash` at `0x1800ae4e5`
- `bcrypt!BCryptDestroyHash` at `0x1800ae4e5`
- `bcrypt!BCryptFinishHash` at `0x1800ae471`
- `bcrypt!BCryptFinishHash` at `0x1800ae4d1`
- `bcrypt!BCryptFinishHash` at `0x1800ae471`
- `bcrypt!BCryptFinishHash` at `0x1800ae4d1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800ae388`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800ae388`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800ae4fe`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800ae4fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LPA::Lpd::DownloadInstance::EncryptConfirmationCode(__int64 a1, __int64 a2, PUCHAR *a3)
{
  NTSTATUS v6; // eax
  unsigned int v7; // edi
  NTSTATUS Property; // eax
  NTSTATUS v9; // eax
  __int64 v10; // r15
  const struct std::nothrow_t *v11; // rax
  UCHAR *v12; // rax
  NTSTATUS v13; // eax
  UCHAR *v14; // rbx
  NTSTATUS v15; // eax
  NTSTATUS v16; // eax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-20h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-10h] BYREF
  PUCHAR pbInput; // [rsp+58h] [rbp-8h] BYREF
  ULONG pcbResult; // [rsp+A8h] [rbp+48h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  *(_DWORD *)pbOutput = 0;
  pbInput = 0;
  v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", L"Microsoft Primitive Provider", 0x20u);
  v7 = v6 | 0x10000000;
  if ( v6 >= 0 )
  {
    pcbResult = 0;
    Property = BCryptGetProperty(phAlgorithm, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
    v7 = Property | 0x10000000;
    if ( Property >= 0 )
    {
      v9 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0x20u);
      v7 = v9 | 0x10000000;
      if ( v9 >= 0 )
      {
        v10 = *(_QWORD *)(a2 + 8) + *(unsigned int *)pbOutput - *(_QWORD *)a2;
        v11 = (const struct std::nothrow_t *)std::make_unique<unsigned char [0],0>(&pcbResult, v10);
        std::unique_ptr<unsigned char [0]>::operator=<std::default_delete<unsigned char [0]>,0>((void **)&pbInput, v11);
        std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&pcbResult);
        v12 = (UCHAR *)std::_String_val<std::_Simple_types<char>>::_Myptr(a1);
        v13 = BCryptHashData(phHash, v12, *(_DWORD *)(a1 + 16), 0);
        v7 = v13 | 0x10000000;
        if ( v13 >= 0 )
        {
          v14 = pbInput;
          v15 = BCryptFinishHash(phHash, pbInput, *(ULONG *)pbOutput, 0);
          v7 = v15 | 0x10000000;
          if ( v15 >= 0 )
          {
            memcpy_s(
              &v14[*(unsigned int *)pbOutput],
              v10 - *(unsigned int *)pbOutput,
              *(const void *const *)a2,
              *(_QWORD *)(a2 + 8) - *(_QWORD *)a2);
            v16 = BCryptHashData(phHash, v14, v10, 0);
            v7 = v16 | 0x10000000;
            if ( v16 >= 0 )
            {
              std::vector<unsigned char>::_Resize<std::_Value_init_tag>(a3, *(unsigned int *)pbOutput, &pcbResult);
              v7 = BCryptFinishHash(phHash, *a3, *(ULONG *)pbOutput, 0) | 0x10000000;
            }
          }
        }
      }
    }
  }
  if ( phHash )
  {
    BCryptDestroyHash(phHash);
    phHash = 0;
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&pbInput);
  return v7;
}

```

## disassembly

```asm
0x1800ae32c  mov     [rsp-28h+arg_0], rbx
0x1800ae331  mov     [rsp-28h+arg_8], rsi
0x1800ae336  push    rbp
0x1800ae337  push    rdi
0x1800ae338  push    r13
0x1800ae33a  push    r14
0x1800ae33c  push    r15
0x1800ae33e  mov     rbp, rsp
0x1800ae341  sub     rsp, 60h
0x1800ae345  mov     rsi, r8
0x1800ae348  mov     r14, rdx
0x1800ae34b  mov     rbx, rcx
0x1800ae34e  mov     [rbp+phAlgorithm], 0
0x1800ae356  mov     [rbp+phHash], 0
0x1800ae35e  mov     dword ptr [rbp+pbOutput], 0
0x1800ae365  mov     [rbp+pbInput], 0
0x1800ae36d  mov     r15d, 20h ; ' '
0x1800ae373  mov     r9d, r15d; dwFlags
0x1800ae376  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800ae37d  lea     rdx, aSha256; "SHA256"
0x1800ae384  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800ae388  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800ae38e  mov     edi, eax
0x1800ae390  mov     r13d, 10000000h
0x1800ae396  or      edi, r13d
0x1800ae399  jl      loc_1800AE4DC
0x1800ae39f  mov     [rbp+arg_18], 0
0x1800ae3a6  mov     [rsp+60h+dwFlags], 0; dwFlags
0x1800ae3ae  lea     rax, [rbp+arg_18]
0x1800ae3b2  mov     [rsp+60h+pcbResult], rax; pcbResult
0x1800ae3b7  lea     r9d, [r15-1Ch]; cbOutput
0x1800ae3bb  lea     r8, [rbp+pbOutput]; pbOutput
0x1800ae3bf  lea     rdx, pszProperty; "HashDigestLength"
0x1800ae3c6  mov     rcx, [rbp+phAlgorithm]; hObject
0x1800ae3ca  call    cs:__imp_BCryptGetProperty
0x1800ae3d0  mov     edi, eax
0x1800ae3d2  or      edi, r13d
0x1800ae3d5  jl      loc_1800AE4DC
0x1800ae3db  mov     [rsp+60h+var_30], r15d; dwFlags
0x1800ae3e0  mov     [rsp+60h+dwFlags], 0; cbSecret
0x1800ae3e8  mov     [rsp+60h+pcbResult], 0; pbSecret
0x1800ae3f1  xor     r9d, r9d; cbHashObject
0x1800ae3f4  xor     r8d, r8d; pbHashObject
0x1800ae3f7  lea     rdx, [rbp+phHash]; phHash
0x1800ae3fb  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800ae3ff  call    cs:__imp_BCryptCreateHash
0x1800ae405  mov     edi, eax
0x1800ae407  or      edi, r13d
0x1800ae40a  jl      loc_1800AE4DC
0x1800ae410  mov     r15d, dword ptr [rbp+pbOutput]
0x1800ae414  sub     r15, [r14]
0x1800ae417  add     r15, [r14+8]
0x1800ae41b  mov     rdx, r15
0x1800ae41e  lea     rcx, [rbp+arg_18]
0x1800ae422  call    ??$make_unique@$$BY0A@E$0A@@std@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@0@_K@Z; std::make_unique<uchar [0],0>(unsigned __int64)
0x1800ae427  mov     rdx, rax
0x1800ae42a  lea     rcx, [rbp+pbInput]
0x1800ae42e  call    ??$?4U?$default_delete@$$BY0A@E@std@@$0A@@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<uchar [0]>::operator=<std::default_delete<uchar [0]>,0>(std::unique_ptr<uchar [0]> &&)
0x1800ae433  lea     rcx, [rbp+arg_18]
0x1800ae437  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x1800ae43c  mov     rcx, rbx
0x1800ae43f  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800ae444  xor     r9d, r9d; dwFlags
0x1800ae447  mov     r8d, [rbx+10h]; cbInput
0x1800ae44b  mov     rdx, rax; pbInput
0x1800ae44e  mov     rcx, [rbp+phHash]; hHash
0x1800ae452  call    cs:__imp_BCryptHashData
0x1800ae458  mov     edi, eax
0x1800ae45a  or      edi, r13d
0x1800ae45d  jl      short loc_1800AE4DC
0x1800ae45f  xor     r9d, r9d; dwFlags
0x1800ae462  mov     r8d, dword ptr [rbp+pbOutput]; cbOutput
0x1800ae466  mov     rbx, [rbp+pbInput]
0x1800ae46a  mov     rdx, rbx; pbOutput
0x1800ae46d  mov     rcx, [rbp+phHash]; hHash
0x1800ae471  call    cs:__imp_BCryptFinishHash
0x1800ae477  mov     edi, eax
0x1800ae479  or      edi, r13d
0x1800ae47c  jl      short loc_1800AE4DC
0x1800ae47e  mov     eax, dword ptr [rbp+pbOutput]
0x1800ae481  mov     r9, [r14+8]
0x1800ae485  sub     r9, [r14]; SourceSize
0x1800ae488  mov     rdx, r15
0x1800ae48b  sub     rdx, rax; DestinationSize
0x1800ae48e  lea     rcx, [rax+rbx]; Destination
0x1800ae492  mov     r8, [r14]; Source
0x1800ae495  call    memcpy_s
0x1800ae49a  mov     r8d, r15d; cbInput
0x1800ae49d  xor     r9d, r9d; dwFlags
0x1800ae4a0  mov     rdx, rbx; pbInput
0x1800ae4a3  mov     rcx, [rbp+phHash]; hHash
0x1800ae4a7  call    cs:__imp_BCryptHashData
0x1800ae4ad  mov     edi, eax
0x1800ae4af  or      edi, r13d
0x1800ae4b2  jl      short loc_1800AE4DC
0x1800ae4b4  mov     edx, dword ptr [rbp+pbOutput]
0x1800ae4b7  lea     r8, [rbp+arg_18]
0x1800ae4bb  mov     rcx, rsi
0x1800ae4be  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800ae4c3  xor     r9d, r9d; dwFlags
0x1800ae4c6  mov     r8d, dword ptr [rbp+pbOutput]; cbOutput
0x1800ae4ca  mov     rdx, [rsi]; pbOutput
0x1800ae4cd  mov     rcx, [rbp+phHash]; hHash
0x1800ae4d1  call    cs:__imp_BCryptFinishHash
0x1800ae4d7  mov     edi, eax
0x1800ae4d9  or      edi, r13d
0x1800ae4dc  mov     rcx, [rbp+phHash]; hHash
0x1800ae4e0  test    rcx, rcx
0x1800ae4e3  jz      short loc_1800AE4F3
0x1800ae4e5  call    cs:__imp_BCryptDestroyHash
0x1800ae4eb  mov     [rbp+phHash], 0
0x1800ae4f3  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800ae4f7  test    rcx, rcx
0x1800ae4fa  jz      short loc_1800AE505
0x1800ae4fc  xor     edx, edx; dwFlags
0x1800ae4fe  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800ae504  nop
0x1800ae505  lea     rcx, [rbp+pbInput]
0x1800ae509  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x1800ae50e  mov     eax, edi
0x1800ae510  lea     r11, [rsp+60h+var_s0]
0x1800ae515  mov     rbx, [r11+30h]
0x1800ae519  mov     rsi, [r11+38h]
0x1800ae51d  mov     rsp, r11
0x1800ae520  pop     r15
0x1800ae522  pop     r14
0x1800ae524  pop     r13
0x1800ae526  pop     rdi
0x1800ae527  pop     rbp
0x1800ae528  retn
```
