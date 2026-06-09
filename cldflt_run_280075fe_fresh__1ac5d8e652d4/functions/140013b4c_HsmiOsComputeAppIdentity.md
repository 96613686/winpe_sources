# HsmiOsComputeAppIdentity

- ea: `0x140013b4c`
- end: `0x140013d3c`
- name: `HsmiOsComputeAppIdentity`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140013d44`

## callees

- `0x140013b4c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140013d05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013d05`
- `ntoskrnl!ExAllocatePool2` at `0x140013beb`
- `ntoskrnl!ExAllocatePool2` at `0x140013beb`
- `cng!BCryptCreateHash` at `0x140013c27`
- `cng!BCryptCreateHash` at `0x140013c27`
- `cng!BCryptOpenAlgorithmProvider` at `0x140013b9a`
- `cng!BCryptOpenAlgorithmProvider` at `0x140013b9a`
- `cng!BCryptFinishHash` at `0x140013cd5`
- `cng!BCryptFinishHash` at `0x140013cd5`
- `cng!BCryptCloseAlgorithmProvider` at `0x140013d1c`
- `cng!BCryptCloseAlgorithmProvider` at `0x140013d1c`
- `cng!BCryptDestroyHash` at `0x140013cec`
- `cng!BCryptDestroyHash` at `0x140013cec`
- `cng!BCryptHashData` at `0x140013c4c`
- `cng!BCryptHashData` at `0x140013c82`
- `cng!BCryptHashData` at `0x140013cb5`
- `cng!BCryptHashData` at `0x140013c4c`
- `cng!BCryptHashData` at `0x140013c82`
- `cng!BCryptHashData` at `0x140013cb5`
- `cng!BCryptGetProperty` at `0x140013bd1`
- `cng!BCryptGetProperty` at `0x140013bd1`

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
0x140013b4c  push    rbp
0x140013b4e  push    rbx
0x140013b4f  push    rsi
0x140013b50  push    rdi
0x140013b51  push    r12
0x140013b53  push    r13
0x140013b55  push    r14
0x140013b57  push    r15
0x140013b59  mov     rbp, rsp
0x140013b5c  sub     rsp, 68h
0x140013b60  xor     r13d, r13d
0x140013b63  mov     [rbp+cbOutput], 4
0x140013b6a  mov     r12, r9
0x140013b6d  mov     [rbp+phAlgorithm], r13
0x140013b71  mov     r14, r8
0x140013b74  mov     dword ptr [rbp+pbOutput], r13d
0x140013b78  mov     rsi, rdx
0x140013b7b  mov     [rbp+phHash], r13
0x140013b7f  mov     r15, rcx
0x140013b82  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140013b89  xor     r9d, r9d; dwFlags
0x140013b8c  lea     rdx, pszAlgId; "SHA256"
0x140013b93  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140013b97  mov     edi, r13d
0x140013b9a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140013ba1  nop     dword ptr [rax+rax+00h]
0x140013ba6  mov     ebx, eax
0x140013ba8  test    eax, eax
0x140013baa  js      loc_140013CE3
0x140013bb0  mov     r9d, [rbp+cbOutput]; cbOutput
0x140013bb4  lea     rax, [rbp+cbOutput]
0x140013bb8  mov     rcx, [rbp+phAlgorithm]; hObject
0x140013bbc  lea     r8, [rbp+pbOutput]; pbOutput
0x140013bc0  mov     [rsp+68h+dwFlags], r13d; dwFlags
0x140013bc5  lea     rdx, pszProperty; "ObjectLength"
0x140013bcc  mov     [rsp+68h+pcbResult], rax; pcbResult
0x140013bd1  call    cs:__imp_BCryptGetProperty
0x140013bd8  nop     dword ptr [rax+rax+00h]
0x140013bdd  mov     edx, dword ptr [rbp+pbOutput]
0x140013be0  mov     ecx, 100h
0x140013be5  mov     r8d, 6F684348h
0x140013beb  call    cs:__imp_ExAllocatePool2
0x140013bf2  nop     dword ptr [rax+rax+00h]
0x140013bf7  mov     rdi, rax
0x140013bfa  test    rax, rax
0x140013bfd  jnz     short loc_140013C09
0x140013bff  mov     ebx, 0C000009Ah
0x140013c04  jmp     loc_140013CE3
0x140013c09  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x140013c0d  lea     rdx, [rbp+phHash]; phHash
0x140013c11  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140013c15  mov     r8, rax; pbHashObject
0x140013c18  mov     [rsp+68h+var_38], r13d; dwFlags
0x140013c1d  mov     [rsp+68h+dwFlags], r13d; cbSecret
0x140013c22  mov     [rsp+68h+pcbResult], r13; pbSecret
0x140013c27  call    cs:__imp_BCryptCreateHash
0x140013c2e  nop     dword ptr [rax+rax+00h]
0x140013c33  mov     ebx, eax
0x140013c35  test    eax, eax
0x140013c37  js      loc_140013CE3
0x140013c3d  movzx   r8d, word ptr [r15]; cbInput
0x140013c41  xor     r9d, r9d; dwFlags
0x140013c44  mov     rdx, [r15+8]; pbInput
0x140013c48  mov     rcx, [rbp+phHash]; hHash
0x140013c4c  call    cs:__imp_BCryptHashData
0x140013c53  nop     dword ptr [rax+rax+00h]
0x140013c58  mov     ebx, eax
0x140013c5a  test    eax, eax
0x140013c5c  js      loc_140013CE3
0x140013c62  test    rsi, rsi
0x140013c65  jz      short loc_140013C94
0x140013c67  mov     rdx, [rsi+8]; pbInput
0x140013c6b  test    rdx, rdx
0x140013c6e  jz      short loc_140013C94
0x140013c70  movzx   eax, word ptr [rsi]
0x140013c73  test    ax, ax
0x140013c76  jz      short loc_140013C94
0x140013c78  mov     rcx, [rbp+phHash]; hHash
0x140013c7c  mov     r8d, eax; cbInput
0x140013c7f  xor     r9d, r9d; dwFlags
0x140013c82  call    cs:__imp_BCryptHashData
0x140013c89  nop     dword ptr [rax+rax+00h]
0x140013c8e  mov     ebx, eax
0x140013c90  test    eax, eax
0x140013c92  js      short loc_140013CE3
0x140013c94  test    r14, r14
0x140013c97  jz      short loc_140013CC7
0x140013c99  mov     rdx, [r14+8]; pbInput
0x140013c9d  test    rdx, rdx
0x140013ca0  jz      short loc_140013CC7
0x140013ca2  movzx   eax, word ptr [r14]
0x140013ca6  test    ax, ax
0x140013ca9  jz      short loc_140013CC7
0x140013cab  mov     rcx, [rbp+phHash]; hHash
0x140013caf  mov     r8d, eax; cbInput
0x140013cb2  xor     r9d, r9d; dwFlags
0x140013cb5  call    cs:__imp_BCryptHashData
0x140013cbc  nop     dword ptr [rax+rax+00h]
0x140013cc1  mov     ebx, eax
0x140013cc3  test    eax, eax
0x140013cc5  js      short loc_140013CE3
0x140013cc7  mov     rcx, [rbp+phHash]; hHash
0x140013ccb  xor     r9d, r9d; dwFlags
0x140013cce  mov     rdx, r12; pbOutput
0x140013cd1  lea     r8d, [r9+20h]; cbOutput
0x140013cd5  call    cs:__imp_BCryptFinishHash
0x140013cdc  nop     dword ptr [rax+rax+00h]
0x140013ce1  mov     ebx, eax
0x140013ce3  mov     rcx, [rbp+phHash]; hHash
0x140013ce7  test    rcx, rcx
0x140013cea  jz      short loc_140013CF8
0x140013cec  call    cs:__imp_BCryptDestroyHash
0x140013cf3  nop     dword ptr [rax+rax+00h]
0x140013cf8  test    rdi, rdi
0x140013cfb  jz      short loc_140013D11
0x140013cfd  mov     edx, 6F684348h; Tag
0x140013d02  mov     rcx, rdi; P
0x140013d05  call    cs:__imp_ExFreePoolWithTag
0x140013d0c  nop     dword ptr [rax+rax+00h]
0x140013d11  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x140013d15  test    rcx, rcx
0x140013d18  jz      short loc_140013D28
0x140013d1a  xor     edx, edx; dwFlags
0x140013d1c  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140013d23  nop     dword ptr [rax+rax+00h]
0x140013d28  mov     eax, ebx
0x140013d2a  add     rsp, 68h
0x140013d2e  pop     r15
0x140013d30  pop     r14
0x140013d32  pop     r13
0x140013d34  pop     r12
0x140013d36  pop     rdi
0x140013d37  pop     rsi
0x140013d38  pop     rbx
0x140013d39  pop     rbp
0x140013d3a  retn
```
