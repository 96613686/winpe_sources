# HsmiOsComputeAppIdentity

- ea: `0x140013bcc`
- end: `0x140013dbc`
- name: `HsmiOsComputeAppIdentity`
- size: `496`
- prototype: `__int64 __fastcall(PUCHAR *, unsigned __int16 *, unsigned __int16 *, UCHAR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140013dc4`

## callees

- `0x140013bcc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140013d85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013d85`
- `ntoskrnl!ExAllocatePool2` at `0x140013c6b`
- `ntoskrnl!ExAllocatePool2` at `0x140013c6b`
- `cng!BCryptCreateHash` at `0x140013ca7`
- `cng!BCryptCreateHash` at `0x140013ca7`
- `cng!BCryptOpenAlgorithmProvider` at `0x140013c1a`
- `cng!BCryptOpenAlgorithmProvider` at `0x140013c1a`
- `cng!BCryptFinishHash` at `0x140013d55`
- `cng!BCryptFinishHash` at `0x140013d55`
- `cng!BCryptCloseAlgorithmProvider` at `0x140013d9c`
- `cng!BCryptCloseAlgorithmProvider` at `0x140013d9c`
- `cng!BCryptDestroyHash` at `0x140013d6c`
- `cng!BCryptDestroyHash` at `0x140013d6c`
- `cng!BCryptHashData` at `0x140013ccc`
- `cng!BCryptHashData` at `0x140013d02`
- `cng!BCryptHashData` at `0x140013d35`
- `cng!BCryptHashData` at `0x140013ccc`
- `cng!BCryptHashData` at `0x140013d02`
- `cng!BCryptHashData` at `0x140013d35`
- `cng!BCryptGetProperty` at `0x140013c51`
- `cng!BCryptGetProperty` at `0x140013c51`

## pseudocode

```c
__int64 __fastcall HsmiOsComputeAppIdentity(PUCHAR *a1, unsigned __int16 *a2, unsigned __int16 *a3, UCHAR *a4)
{
  UCHAR *v8; // rdi
  NTSTATUS v9; // ebx
  UCHAR *Pool2; // rax
  UCHAR *v11; // rdx
  UCHAR *v12; // rdx
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-28h] BYREF
  ULONG cbOutput; // [rsp+44h] [rbp-24h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-18h] BYREF

  cbOutput = 4;
  phAlgorithm = 0;
  *(_DWORD *)pbOutput = 0;
  phHash = 0;
  v8 = 0;
  v9 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", L"Microsoft Primitive Provider", 0);
  if ( v9 >= 0 )
  {
    BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, cbOutput, &cbOutput, 0);
    Pool2 = (UCHAR *)ExAllocatePool2(256, *(unsigned int *)pbOutput, 1869103944);
    v8 = Pool2;
    if ( Pool2 )
    {
      v9 = BCryptCreateHash(phAlgorithm, &phHash, Pool2, *(ULONG *)pbOutput, 0, 0, 0);
      if ( v9 >= 0 )
      {
        v9 = BCryptHashData(phHash, a1[1], *(unsigned __int16 *)a1, 0);
        if ( v9 >= 0 )
        {
          if ( !a2
            || (v11 = (UCHAR *)*((_QWORD *)a2 + 1)) == 0
            || !*a2
            || (v9 = BCryptHashData(phHash, v11, *a2, 0), v9 >= 0) )
          {
            if ( !a3
              || (v12 = (UCHAR *)*((_QWORD *)a3 + 1)) == 0
              || !*a3
              || (v9 = BCryptHashData(phHash, v12, *a3, 0), v9 >= 0) )
            {
              v9 = BCryptFinishHash(phHash, a4, 0x20u, 0);
            }
          }
        }
      }
    }
    else
    {
      v9 = -1073741670;
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x6F684348u);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140013bcc  push    rbp
0x140013bce  push    rbx
0x140013bcf  push    rsi
0x140013bd0  push    rdi
0x140013bd1  push    r12
0x140013bd3  push    r13
0x140013bd5  push    r14
0x140013bd7  push    r15
0x140013bd9  mov     rbp, rsp
0x140013bdc  sub     rsp, 68h
0x140013be0  xor     r13d, r13d
0x140013be3  mov     [rbp+cbOutput], 4
0x140013bea  mov     r12, r9
0x140013bed  mov     [rbp+phAlgorithm], r13
0x140013bf1  mov     r14, r8
0x140013bf4  mov     dword ptr [rbp+pbOutput], r13d
0x140013bf8  mov     rsi, rdx
0x140013bfb  mov     [rbp+phHash], r13
0x140013bff  mov     r15, rcx
0x140013c02  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140013c09  xor     r9d, r9d; dwFlags
0x140013c0c  lea     rdx, pszAlgId; "SHA256"
0x140013c13  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140013c17  mov     edi, r13d
0x140013c1a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140013c21  nop     dword ptr [rax+rax+00h]
0x140013c26  mov     ebx, eax
0x140013c28  test    eax, eax
0x140013c2a  js      loc_140013D63
0x140013c30  mov     r9d, [rbp+cbOutput]; cbOutput
0x140013c34  lea     rax, [rbp+cbOutput]
0x140013c38  mov     rcx, [rbp+phAlgorithm]; hObject
0x140013c3c  lea     r8, [rbp+pbOutput]; pbOutput
0x140013c40  mov     [rsp+68h+dwFlags], r13d; dwFlags
0x140013c45  lea     rdx, pszProperty; "ObjectLength"
0x140013c4c  mov     [rsp+68h+pcbResult], rax; pcbResult
0x140013c51  call    cs:__imp_BCryptGetProperty
0x140013c58  nop     dword ptr [rax+rax+00h]
0x140013c5d  mov     edx, dword ptr [rbp+pbOutput]
0x140013c60  mov     ecx, 100h
0x140013c65  mov     r8d, 6F684348h
0x140013c6b  call    cs:__imp_ExAllocatePool2
0x140013c72  nop     dword ptr [rax+rax+00h]
0x140013c77  mov     rdi, rax
0x140013c7a  test    rax, rax
0x140013c7d  jnz     short loc_140013C89
0x140013c7f  mov     ebx, 0C000009Ah
0x140013c84  jmp     loc_140013D63
0x140013c89  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x140013c8d  lea     rdx, [rbp+phHash]; phHash
0x140013c91  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140013c95  mov     r8, rax; pbHashObject
0x140013c98  mov     [rsp+68h+var_38], r13d; dwFlags
0x140013c9d  mov     [rsp+68h+dwFlags], r13d; cbSecret
0x140013ca2  mov     [rsp+68h+pcbResult], r13; pbSecret
0x140013ca7  call    cs:__imp_BCryptCreateHash
0x140013cae  nop     dword ptr [rax+rax+00h]
0x140013cb3  mov     ebx, eax
0x140013cb5  test    eax, eax
0x140013cb7  js      loc_140013D63
0x140013cbd  movzx   r8d, word ptr [r15]; cbInput
0x140013cc1  xor     r9d, r9d; dwFlags
0x140013cc4  mov     rdx, [r15+8]; pbInput
0x140013cc8  mov     rcx, [rbp+phHash]; hHash
0x140013ccc  call    cs:__imp_BCryptHashData
0x140013cd3  nop     dword ptr [rax+rax+00h]
0x140013cd8  mov     ebx, eax
0x140013cda  test    eax, eax
0x140013cdc  js      loc_140013D63
0x140013ce2  test    rsi, rsi
0x140013ce5  jz      short loc_140013D14
0x140013ce7  mov     rdx, [rsi+8]; pbInput
0x140013ceb  test    rdx, rdx
0x140013cee  jz      short loc_140013D14
0x140013cf0  movzx   eax, word ptr [rsi]
0x140013cf3  test    ax, ax
0x140013cf6  jz      short loc_140013D14
0x140013cf8  mov     rcx, [rbp+phHash]; hHash
0x140013cfc  mov     r8d, eax; cbInput
0x140013cff  xor     r9d, r9d; dwFlags
0x140013d02  call    cs:__imp_BCryptHashData
0x140013d09  nop     dword ptr [rax+rax+00h]
0x140013d0e  mov     ebx, eax
0x140013d10  test    eax, eax
0x140013d12  js      short loc_140013D63
0x140013d14  test    r14, r14
0x140013d17  jz      short loc_140013D47
0x140013d19  mov     rdx, [r14+8]; pbInput
0x140013d1d  test    rdx, rdx
0x140013d20  jz      short loc_140013D47
0x140013d22  movzx   eax, word ptr [r14]
0x140013d26  test    ax, ax
0x140013d29  jz      short loc_140013D47
0x140013d2b  mov     rcx, [rbp+phHash]; hHash
0x140013d2f  mov     r8d, eax; cbInput
0x140013d32  xor     r9d, r9d; dwFlags
0x140013d35  call    cs:__imp_BCryptHashData
0x140013d3c  nop     dword ptr [rax+rax+00h]
0x140013d41  mov     ebx, eax
0x140013d43  test    eax, eax
0x140013d45  js      short loc_140013D63
0x140013d47  mov     rcx, [rbp+phHash]; hHash
0x140013d4b  xor     r9d, r9d; dwFlags
0x140013d4e  mov     rdx, r12; pbOutput
0x140013d51  lea     r8d, [r9+20h]; cbOutput
0x140013d55  call    cs:__imp_BCryptFinishHash
0x140013d5c  nop     dword ptr [rax+rax+00h]
0x140013d61  mov     ebx, eax
0x140013d63  mov     rcx, [rbp+phHash]; hHash
0x140013d67  test    rcx, rcx
0x140013d6a  jz      short loc_140013D78
0x140013d6c  call    cs:__imp_BCryptDestroyHash
0x140013d73  nop     dword ptr [rax+rax+00h]
0x140013d78  test    rdi, rdi
0x140013d7b  jz      short loc_140013D91
0x140013d7d  mov     edx, 6F684348h; Tag
0x140013d82  mov     rcx, rdi; P
0x140013d85  call    cs:__imp_ExFreePoolWithTag
0x140013d8c  nop     dword ptr [rax+rax+00h]
0x140013d91  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140013d95  test    rcx, rcx
0x140013d98  jz      short loc_140013DA8
0x140013d9a  xor     edx, edx; dwFlags
0x140013d9c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140013da3  nop     dword ptr [rax+rax+00h]
0x140013da8  mov     eax, ebx
0x140013daa  add     rsp, 68h
0x140013dae  pop     r15
0x140013db0  pop     r14
0x140013db2  pop     r13
0x140013db4  pop     r12
0x140013db6  pop     rdi
0x140013db7  pop     rsi
0x140013db8  pop     rbx
0x140013db9  pop     rbp
0x140013dba  retn
```
