# Utils::GetSHA256CngHash(std::vector<uchar,std::allocator<uchar>> const &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x1800d331c`
- end: `0x1800d346d`
- name: `?GetSHA256CngHash@Utils@@SAJAEBV?$vector@EV?$allocator@E@std@@@std@@AEAV23@@Z`
- size: `337`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180017fa0`
- `0x18003a060`
- `0x1800990a0`
- `0x1800af510`
- `0x1800d30d8`

## callees

- `0x180019640`
- `0x1800d331c`

## import_xrefs

- `bcrypt!BCryptFinishHash` at `0x1800d342a`
- `bcrypt!BCryptFinishHash` at `0x1800d342a`
- `bcrypt!BCryptHashData` at `0x1800d340c`
- `bcrypt!BCryptHashData` at `0x1800d340c`
- `bcrypt!BCryptCreateHash` at `0x1800d33ee`
- `bcrypt!BCryptCreateHash` at `0x1800d33ee`
- `bcrypt!BCryptGetProperty` at `0x1800d33a1`
- `bcrypt!BCryptGetProperty` at `0x1800d33a1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800d3454`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800d3454`
- `bcrypt!BCryptDestroyHash` at `0x1800d3442`
- `bcrypt!BCryptDestroyHash` at `0x1800d3442`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800d3362`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800d3362`

## pseudocode

```c
__int64 __fastcall Utils::GetSHA256CngHash(__int64 a1, __int64 a2)
{
  NTSTATUS Property; // edi
  NTSTATUS v6; // [rsp+40h] [rbp-28h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_HANDLE hObject; // [rsp+50h] [rbp-18h] BYREF
  unsigned int pbOutput; // [rsp+80h] [rbp+18h] BYREF
  ULONG pcbResult; // [rsp+88h] [rbp+20h] BYREF

  hObject = 0;
  phHash = 0;
  pbOutput = 0;
  pcbResult = 0;
  Property = BCryptOpenAlgorithmProvider(&hObject, L"SHA256", 0, 0);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(hObject, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
    v6 = Property;
    if ( Property >= 0 )
    {
      try
      {
        std::vector<unsigned char>::resize(a2, pbOutput);
        Property = BCryptCreateHash(hObject, &phHash, 0, 0, 0, 0, 0);
        if ( Property >= 0 )
        {
          Property = BCryptHashData(phHash, *(PUCHAR *)a1, *(_DWORD *)(a1 + 8) - *(_DWORD *)a1, 0);
          if ( Property >= 0 )
            Property = BCryptFinishHash(phHash, *(PUCHAR *)a2, *(_DWORD *)(a2 + 8) - *(_DWORD *)a2, 0);
        }
      }
      catch ( std::exception )
      {
        Property = v6;
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( hObject )
    BCryptCloseAlgorithmProvider(hObject, 0);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1800d331c  mov     rax, rsp
0x1800d331f  mov     [rax+8], rsi
0x1800d3323  mov     [rax+10h], rdi
0x1800d3327  push    r14
0x1800d3329  sub     rsp, 60h
0x1800d332d  mov     rsi, rdx
0x1800d3330  mov     r14, rcx
0x1800d3333  mov     qword ptr [rax-18h], 0
0x1800d333b  mov     qword ptr [rax-20h], 0
0x1800d3343  mov     dword ptr [rax+18h], 0
0x1800d334a  mov     dword ptr [rax+20h], 0
0x1800d3351  xor     r9d, r9d; dwFlags
0x1800d3354  xor     r8d, r8d; pszImplementation
0x1800d3357  lea     rdx, pszAlgId; "SHA256"
0x1800d335e  lea     rcx, [rax-18h]; phAlgorithm
0x1800d3362  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800d3368  mov     edi, eax
0x1800d336a  test    eax, eax
0x1800d336c  js      loc_1800D3438
0x1800d3372  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1800d337a  lea     rax, [rsp+68h+arg_18]
0x1800d3382  mov     [rsp+68h+pcbResult], rax; pcbResult
0x1800d3387  mov     r9d, 4; cbOutput
0x1800d338d  lea     r8, [rsp+68h+pbOutput]; pbOutput
0x1800d3395  lea     rdx, pszProperty; "HashDigestLength"
0x1800d339c  mov     rcx, [rsp+68h+hObject]; hObject
0x1800d33a1  call    cs:__imp_BCryptGetProperty
0x1800d33a7  mov     edi, eax
0x1800d33a9  mov     [rsp+68h+var_28], eax
0x1800d33ad  test    eax, eax
0x1800d33af  js      loc_1800D3438
0x1800d33b5  mov     edx, [rsp+68h+pbOutput]
0x1800d33bc  mov     rcx, rsi
0x1800d33bf  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x1800d33c4  nop
0x1800d33c5  mov     [rsp+68h+var_38], 0; dwFlags
0x1800d33cd  mov     [rsp+68h+dwFlags], 0; cbSecret
0x1800d33d5  mov     [rsp+68h+pcbResult], 0; pbSecret
0x1800d33de  xor     r9d, r9d; cbHashObject
0x1800d33e1  xor     r8d, r8d; pbHashObject
0x1800d33e4  lea     rdx, [rsp+68h+phHash]; phHash
0x1800d33e9  mov     rcx, [rsp+68h+hObject]; hAlgorithm
0x1800d33ee  call    cs:__imp_BCryptCreateHash
0x1800d33f4  mov     edi, eax
0x1800d33f6  test    eax, eax
0x1800d33f8  js      short loc_1800D3438
0x1800d33fa  mov     r8d, [r14+8]
0x1800d33fe  sub     r8d, [r14]; cbInput
0x1800d3401  xor     r9d, r9d; dwFlags
0x1800d3404  mov     rdx, [r14]; pbInput
0x1800d3407  mov     rcx, [rsp+68h+phHash]; hHash
0x1800d340c  call    cs:__imp_BCryptHashData
0x1800d3412  mov     edi, eax
0x1800d3414  test    eax, eax
0x1800d3416  js      short loc_1800D3438
0x1800d3418  mov     r8d, [rsi+8]
0x1800d341c  sub     r8d, [rsi]; cbOutput
0x1800d341f  xor     r9d, r9d; dwFlags
0x1800d3422  mov     rdx, [rsi]; pbOutput
0x1800d3425  mov     rcx, [rsp+68h+phHash]; hHash
0x1800d342a  call    cs:__imp_BCryptFinishHash
0x1800d3430  mov     edi, eax
0x1800d3432  jmp     short loc_1800D3438
0x1800d3434  mov     edi, [rsp+68h+var_28]
0x1800d3438  mov     rcx, [rsp+68h+phHash]; hHash
0x1800d343d  test    rcx, rcx
0x1800d3440  jz      short loc_1800D3448
0x1800d3442  call    cs:__imp_BCryptDestroyHash
0x1800d3448  mov     rcx, [rsp+68h+hObject]; hAlgorithm
0x1800d344d  test    rcx, rcx
0x1800d3450  jz      short loc_1800D345A
0x1800d3452  xor     edx, edx; dwFlags
0x1800d3454  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800d345a  mov     eax, edi
0x1800d345c  mov     rsi, [rsp+68h+arg_0]
0x1800d3461  mov     rdi, [rsp+68h+arg_8]
0x1800d3466  add     rsp, 60h
0x1800d346a  pop     r14
0x1800d346c  retn
```
