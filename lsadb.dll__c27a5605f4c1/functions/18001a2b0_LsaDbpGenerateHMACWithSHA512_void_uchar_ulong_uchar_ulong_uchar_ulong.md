# LsaDbpGenerateHMACWithSHA512(void *,uchar *,ulong,uchar *,ulong,uchar * *,ulong *)

- ea: `0x18001a2b0`
- end: `0x18001a467`
- name: `?LsaDbpGenerateHMACWithSHA512@@YAJPEAXPEAEK1KPEAPEAEPEAK@Z`
- size: `439`
- prototype: `__int64 __usercall@<rax>(BCRYPT_ALG_HANDLE hAlgorithm@<rcx>, unsigned __int8 *@<rdx>, unsigned int@<r8d>, unsigned __int8 *@<r9>, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017018`

## callees

- `0x18001a2b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a34a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a3a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a34a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a3a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a43e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a447`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a43e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001a447`
- `bcrypt!BCryptGetProperty` at `0x18001a32a`
- `bcrypt!BCryptGetProperty` at `0x18001a383`
- `bcrypt!BCryptGetProperty` at `0x18001a32a`
- `bcrypt!BCryptGetProperty` at `0x18001a383`
- `bcrypt!BCryptCreateHash` at `0x18001a3d7`
- `bcrypt!BCryptCreateHash` at `0x18001a3d7`
- `bcrypt!BCryptHashData` at `0x18001a3f2`
- `bcrypt!BCryptHashData` at `0x18001a3f2`
- `bcrypt!BCryptFinishHash` at `0x18001a40c`
- `bcrypt!BCryptFinishHash` at `0x18001a40c`
- `bcrypt!BCryptDestroyHash` at `0x18001a435`
- `bcrypt!BCryptDestroyHash` at `0x18001a435`

## pseudocode

```c
__int64 __fastcall LsaDbpGenerateHMACWithSHA512(
        BCRYPT_ALG_HANDLE hAlgorithm,
        unsigned __int8 *a2,
        ULONG a3,
        unsigned __int8 *a4,
        ULONG cbInput,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  UCHAR *v9; // rsi
  UCHAR *v10; // rdi
  NTSTATUS Property; // ebx
  unsigned int v12; // eax
  ULONG pcbResult; // [rsp+40h] [rbp-20h] BYREF
  UCHAR v15[4]; // [rsp+44h] [rbp-1Ch] BYREF
  UCHAR pbOutput[4]; // [rsp+48h] [rbp-18h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+50h] [rbp-10h] BYREF

  phHash = 0;
  v9 = 0;
  *(_DWORD *)pbOutput = 0;
  v10 = 0;
  *a6 = 0;
  *a7 = 0;
  *(_DWORD *)v15 = 0;
  pcbResult = 0;
  if ( !cbInput || !a3 )
    goto LABEL_14;
  Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_15;
  if ( pcbResult != 4 )
    goto LABEL_14;
  v9 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)pbOutput);
  if ( !v9 )
  {
LABEL_6:
    Property = -1073741670;
    goto LABEL_15;
  }
  Property = BCryptGetProperty(hAlgorithm, L"HashDigestLength", v15, 4u, &pcbResult, 0);
  if ( Property >= 0 )
  {
    if ( pcbResult == 4 )
    {
      v10 = (UCHAR *)LocalAlloc(0x40u, *(unsigned int *)v15);
      if ( !v10 )
        goto LABEL_6;
      Property = BCryptCreateHash(hAlgorithm, &phHash, v9, *(ULONG *)pbOutput, a2, a3, 0);
      if ( Property >= 0 )
      {
        Property = BCryptHashData(phHash, a4, cbInput, 0);
        if ( Property >= 0 )
        {
          Property = BCryptFinishHash(phHash, v10, *(ULONG *)v15, 0);
          if ( Property >= 0 )
          {
            v12 = *(_DWORD *)v15;
            *a6 = v10;
            v10 = 0;
            *a7 = v12;
          }
        }
      }
      goto LABEL_15;
    }
LABEL_14:
    Property = -1073741811;
  }
LABEL_15:
  if ( phHash )
    BCryptDestroyHash(phHash);
  LocalFree(v9);
  LocalFree(v10);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x18001a2b0  mov     rax, rsp
0x18001a2b3  mov     [rax+8], rbx
0x18001a2b7  mov     [rax+20h], r9
0x18001a2bb  mov     [rax+10h], rdx
0x18001a2bf  push    rbp
0x18001a2c0  push    rsi
0x18001a2c1  push    rdi
0x18001a2c2  push    r12
0x18001a2c4  push    r13
0x18001a2c6  push    r14
0x18001a2c8  push    r15
0x18001a2ca  mov     rbp, rsp
0x18001a2cd  sub     rsp, 60h
0x18001a2d1  mov     r12, [rbp+arg_28]
0x18001a2d5  mov     r15, rcx
0x18001a2d8  mov     r13, [rbp+arg_30]
0x18001a2dc  xor     ecx, ecx
0x18001a2de  mov     r14d, r8d
0x18001a2e1  mov     [rbp+phHash], rcx
0x18001a2e5  mov     esi, ecx
0x18001a2e7  mov     dword ptr [rbp+pbOutput], ecx
0x18001a2ea  mov     edi, ecx
0x18001a2ec  mov     [r12], rcx
0x18001a2f0  mov     [r13+0], ecx
0x18001a2f4  mov     dword ptr [rbp+var_1C], ecx
0x18001a2f7  mov     [rbp+var_20], ecx
0x18001a2fa  cmp     [rbp+cbInput], ecx
0x18001a2fd  jz      loc_18001A427
0x18001a303  test    r8d, r8d
0x18001a306  jz      loc_18001A427
0x18001a30c  mov     [rax-70h], ecx
0x18001a30f  lea     r9d, [rcx+4]; cbOutput
0x18001a313  lea     rax, [rbp+var_20]
0x18001a317  mov     rcx, r15; hObject
0x18001a31a  lea     r8, [rbp+pbOutput]; pbOutput
0x18001a31e  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18001a323  lea     rdx, pszProperty; "ObjectLength"
0x18001a32a  call    cs:__imp_BCryptGetProperty
0x18001a330  mov     ebx, eax
0x18001a332  test    eax, eax
0x18001a334  js      loc_18001A42C
0x18001a33a  cmp     [rbp+var_20], 4
0x18001a33e  jnz     loc_18001A427
0x18001a344  mov     edx, dword ptr [rbp+pbOutput]; uBytes
0x18001a347  lea     ecx, [rdi+40h]; uFlags
0x18001a34a  call    cs:__imp_LocalAlloc
0x18001a350  mov     rsi, rax
0x18001a353  test    rax, rax
0x18001a356  jnz     short loc_18001A362
0x18001a358  mov     ebx, 0C000009Ah
0x18001a35d  jmp     loc_18001A42C
0x18001a362  lea     rax, [rbp+var_20]
0x18001a366  mov     [rsp+60h+dwFlags], edi; dwFlags
0x18001a36a  mov     r9d, 4; cbOutput
0x18001a370  mov     [rsp+60h+pcbResult], rax; pcbResult
0x18001a375  lea     r8, [rbp+var_1C]; pbOutput
0x18001a379  mov     rcx, r15; hObject
0x18001a37c  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18001a383  call    cs:__imp_BCryptGetProperty
0x18001a389  mov     ebx, eax
0x18001a38b  test    eax, eax
0x18001a38d  js      loc_18001A42C
0x18001a393  cmp     [rbp+var_20], 4
0x18001a397  jnz     loc_18001A427
0x18001a39d  mov     edx, dword ptr [rbp+var_1C]; uBytes
0x18001a3a0  mov     ecx, 40h ; '@'; uFlags
0x18001a3a5  call    cs:__imp_LocalAlloc
0x18001a3ab  mov     rdi, rax
0x18001a3ae  test    rax, rax
0x18001a3b1  jz      short loc_18001A358
0x18001a3b3  mov     rax, [rbp+pbSecret]
0x18001a3b7  lea     rdx, [rbp+phHash]; phHash
0x18001a3bb  mov     r9d, dword ptr [rbp+pbOutput]; cbHashObject
0x18001a3bf  mov     r8, rsi; pbHashObject
0x18001a3c2  mov     [rsp+60h+var_30], 0; dwFlags
0x18001a3ca  mov     rcx, r15; hAlgorithm
0x18001a3cd  mov     [rsp+60h+dwFlags], r14d; cbSecret
0x18001a3d2  mov     [rsp+60h+pcbResult], rax; pbSecret
0x18001a3d7  call    cs:__imp_BCryptCreateHash
0x18001a3dd  mov     ebx, eax
0x18001a3df  test    eax, eax
0x18001a3e1  js      short loc_18001A42C
0x18001a3e3  mov     r8d, [rbp+cbInput]; cbInput
0x18001a3e7  xor     r9d, r9d; dwFlags
0x18001a3ea  mov     rdx, [rbp+pbInput]; pbInput
0x18001a3ee  mov     rcx, [rbp+phHash]; hHash
0x18001a3f2  call    cs:__imp_BCryptHashData
0x18001a3f8  mov     ebx, eax
0x18001a3fa  test    eax, eax
0x18001a3fc  js      short loc_18001A42C
0x18001a3fe  mov     r8d, dword ptr [rbp+var_1C]; cbOutput
0x18001a402  xor     r9d, r9d; dwFlags
0x18001a405  mov     rcx, [rbp+phHash]; hHash
0x18001a409  mov     rdx, rdi; pbOutput
0x18001a40c  call    cs:__imp_BCryptFinishHash
0x18001a412  mov     ebx, eax
0x18001a414  test    eax, eax
0x18001a416  js      short loc_18001A42C
0x18001a418  mov     eax, dword ptr [rbp+var_1C]
0x18001a41b  mov     [r12], rdi
0x18001a41f  xor     edi, edi
0x18001a421  mov     [r13+0], eax
0x18001a425  jmp     short loc_18001A42C
0x18001a427  mov     ebx, 0C000000Dh
0x18001a42c  mov     rcx, [rbp+phHash]; hHash
0x18001a430  test    rcx, rcx
0x18001a433  jz      short loc_18001A43B
0x18001a435  call    cs:__imp_BCryptDestroyHash
0x18001a43b  mov     rcx, rsi; hMem
0x18001a43e  call    cs:__imp_LocalFree
0x18001a444  mov     rcx, rdi; hMem
0x18001a447  call    cs:__imp_LocalFree
0x18001a44d  mov     eax, ebx
0x18001a44f  mov     rbx, [rsp+60h+arg_0]
0x18001a457  add     rsp, 60h
0x18001a45b  pop     r15
0x18001a45d  pop     r14
0x18001a45f  pop     r13
0x18001a461  pop     r12
0x18001a463  pop     rdi
0x18001a464  pop     rsi
0x18001a465  pop     rbp
0x18001a466  retn
```
