# Ssl3ComputeMac

- ea: `0x180084a2c`
- end: `0x180084d32`
- name: `Ssl3ComputeMac`
- size: `774`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, ULONG cbInput, __int64, ULONG cbOutput)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f080`
- `0x18003f56c`

## callees

- `0x180001930`
- `0x1800034b0`
- `0x1800064e0`
- `0x18000743c`
- `0x1800080f0`
- `0x180084a2c`
- `0x18009f650`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180084aa9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180084aa9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180084cfc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180084cfc`

## string_xrefs

- `0x180084ad4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\ssl3key.c`

## pseudocode

```c
__int64 __fastcall Ssl3ComputeMac(
        __int64 a1,
        __int64 a2,
        int a3,
        unsigned __int64 a4,
        UCHAR *a5,
        ULONG cbInput,
        UCHAR *a7,
        ULONG cbOutput)
{
  __int64 v9; // rsi
  __int64 v10; // rax
  ULONG v11; // r12d
  UCHAR *v13; // rax
  UCHAR *v14; // r14
  unsigned int v15; // ebx
  __int64 v16; // r9
  __int64 v17; // rcx
  NTSTATUS v18; // eax
  ULONG v19; // r9d
  void *v20; // rcx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-69h] BYREF
  int v23; // [rsp+48h] [rbp-61h]
  ULONG v24; // [rsp+4Ch] [rbp-5Dh]
  unsigned __int64 v25; // [rsp+50h] [rbp-59h]
  PUCHAR v26; // [rsp+58h] [rbp-51h]
  PUCHAR v27; // [rsp+60h] [rbp-49h]
  UCHAR pbInput[8]; // [rsp+68h] [rbp-41h] BYREF
  char v29; // [rsp+70h] [rbp-39h]
  char v30; // [rsp+71h] [rbp-38h]
  char v31; // [rsp+72h] [rbp-37h]
  UCHAR pbOutput[48]; // [rsp+78h] [rbp-31h] BYREF

  v26 = a5;
  v27 = a7;
  v9 = 312;
  v10 = *(_QWORD *)(a2 + 16);
  v11 = 48;
  v23 = a3;
  phHash = 0;
  v25 = a4;
  if ( *(_DWORD *)(v10 + 64) != 32771 )
  {
    v11 = 40;
    v9 = 352;
  }
  v24 = v11;
  v13 = (UCHAR *)ExAllocateFromPagedLookasideList(*(PPAGED_LOOKASIDE_LIST *)(v9 + a1 + 16));
  v14 = v13;
  if ( !v13 )
  {
    v15 = -2146893810;
    v16 = 419;
    v17 = 2148073486LL;
LABEL_5:
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\schannel\\ssl3key.c", v16);
    goto LABEL_30;
  }
  v18 = BCryptCreateHash(*(BCRYPT_ALG_HANDLE *)(v9 + a1), &phHash, v13, *(_DWORD *)(v9 + a1 + 24), 0, 0, 0);
  v15 = v18;
  if ( v18 < 0 )
  {
    v16 = 437;
LABEL_8:
    v17 = (unsigned int)v18;
    goto LABEL_5;
  }
  v18 = BCryptHashData(phHash, (PUCHAR)(a2 + 56), *(_DWORD *)(a2 + 104), 0);
  v15 = v18;
  if ( v18 < 0 )
  {
    v16 = 449;
    goto LABEL_8;
  }
  v18 = BCryptHashData(
          phHash,
          (PUCHAR)"666666666666666666666666666666666666666666666666E\x00n\x00a\x00b\x00l\x00e\x00T\x00l\x00s\x00E\x00x\x00"
                  "t\x00e\x00r\x00n\x00a\x00l\x00A\x00l\x00g\x00o\x00r\x00i\x00t\x00h\x00m\x00s",
          v11,
          0);
  v15 = v18;
  if ( v18 < 0 )
  {
    v16 = 461;
    goto LABEL_8;
  }
  *(_QWORD *)pbInput = _byteswap_uint64(v25);
  v29 = v23;
  v30 = BYTE1(cbInput);
  v31 = cbInput;
  v18 = BCryptHashData(phHash, pbInput, 0xBu, 0);
  v15 = v18;
  if ( v18 < 0 )
  {
    v16 = 490;
    goto LABEL_8;
  }
  v18 = BCryptHashData(phHash, v26, cbInput, 0);
  v15 = v18;
  if ( v18 < 0 )
  {
    v16 = 502;
    goto LABEL_8;
  }
  v18 = BCryptFinishHash(phHash, pbOutput, *(_DWORD *)(*(_QWORD *)(a2 + 16) + 68LL), 0);
  v15 = v18;
  if ( v18 < 0 )
  {
    v16 = 514;
    goto LABEL_8;
  }
  BCryptDestroyHash(phHash);
  v19 = *(_DWORD *)(v9 + a1 + 24);
  v20 = *(void **)(v9 + a1);
  phHash = 0;
  v18 = BCryptCreateHash(v20, &phHash, v14, v19, 0, 0, 0);
  v15 = v18;
  if ( v18 < 0 )
  {
    v16 = 535;
    goto LABEL_8;
  }
  v18 = BCryptHashData(phHash, (PUCHAR)(a2 + 56), *(_DWORD *)(a2 + 104), 0);
  v15 = v18;
  if ( v18 < 0 )
  {
    v16 = 547;
    goto LABEL_8;
  }
  v18 = BCryptHashData(phHash, (PUCHAR)&g_rgbPad2, v24, 0);
  v15 = v18;
  if ( v18 < 0 )
  {
    v16 = 559;
    goto LABEL_8;
  }
  v18 = BCryptHashData(phHash, pbOutput, *(_DWORD *)(*(_QWORD *)(a2 + 16) + 68LL), 0);
  v15 = v18;
  if ( v18 < 0 )
  {
    v16 = 570;
    goto LABEL_8;
  }
  v18 = BCryptFinishHash(phHash, v27, cbOutput, 0);
  v15 = v18;
  if ( v18 < 0 )
  {
    v16 = 582;
    goto LABEL_8;
  }
  BCryptDestroyHash(phHash);
  v15 = 0;
  phHash = 0;
LABEL_30:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v14 )
    ExFreeToPagedLookasideList(*(PPAGED_LOOKASIDE_LIST *)(v9 + a1 + 16), v14);
  return v15;
}

```

## disassembly

```asm
0x180084a2c  mov     [rsp-8+arg_10], rbx
0x180084a31  push    rbp
0x180084a32  push    rsi
0x180084a33  push    rdi
0x180084a34  push    r12
0x180084a36  push    r13
0x180084a38  push    r14
0x180084a3a  push    r15
0x180084a3c  lea     rbp, [rsp-7]
0x180084a41  sub     rsp, 0B0h
0x180084a48  mov     rax, cs:__security_cookie
0x180084a4f  xor     rax, rsp
0x180084a52  mov     [rbp+37h+var_38], rax
0x180084a56  mov     rax, [rbp+37h+arg_20]
0x180084a5a  xor     ebx, ebx
0x180084a5c  mov     [rbp+37h+var_88], rax
0x180084a60  mov     r15, rcx
0x180084a63  mov     rax, [rbp+37h+arg_30]
0x180084a67  mov     ecx, 8003h
0x180084a6c  mov     [rbp+37h+var_80], rax
0x180084a70  mov     esi, 138h
0x180084a75  mov     rax, [rdx+10h]
0x180084a79  lea     r12d, [rbx+30h]
0x180084a7d  mov     [rbp+37h+var_98], r8d
0x180084a81  mov     rdi, rdx
0x180084a84  mov     [rbp+37h+phHash], rbx
0x180084a88  mov     [rbp+37h+var_90], r9
0x180084a8c  mov     r8d, [rax+40h]
0x180084a90  cmp     r8d, ecx
0x180084a93  lea     eax, [rbx+28h]
0x180084a96  cmovnz  r12d, eax
0x180084a9a  lea     eax, [rsi+28h]
0x180084a9d  cmovnz  esi, eax
0x180084aa0  mov     [rbp+37h+var_94], r12d
0x180084aa4  mov     rcx, [rsi+r15+10h]; Lookaside
0x180084aa9  call    cs:__imp_ExAllocateFromPagedLookasideList
0x180084ab0  nop     dword ptr [rax+rax+00h]
0x180084ab5  mov     r14, rax
0x180084ab8  test    rax, rax
0x180084abb  jnz     short loc_180084AE5
0x180084abd  mov     ebx, 8009000Eh
0x180084ac2  mov     r9d, 1A3h
0x180084ac8  mov     ecx, 8009000Eh
0x180084acd  lea     rdx, aStatus; "Status"
0x180084ad4  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180084adb  call    DebugTraceError
0x180084ae0  jmp     loc_180084CE1
0x180084ae5  mov     r9d, [rsi+r15+18h]; cbHashObject
0x180084aea  lea     rdx, [rbp+37h+phHash]; phHash
0x180084aee  mov     rcx, [rsi+r15]; hAlgorithm
0x180084af2  mov     r8, r14; pbHashObject
0x180084af5  mov     [rsp+0E0h+dwFlags], ebx; dwFlags
0x180084af9  mov     [rsp+0E0h+cbSecret], ebx; cbSecret
0x180084afd  mov     [rsp+0E0h+pbSecret], rbx; pbSecret
0x180084b02  call    BCryptCreateHash
0x180084b07  mov     ebx, eax
0x180084b09  test    eax, eax
0x180084b0b  jns     short loc_180084B17
0x180084b0d  mov     r9d, 1B5h
0x180084b13  mov     ecx, eax
0x180084b15  jmp     short loc_180084ACD
0x180084b17  mov     r8d, [rdi+68h]; cbInput
0x180084b1b  lea     rdx, [rdi+38h]; pbInput
0x180084b1f  mov     rcx, [rbp+37h+phHash]; hHash
0x180084b23  xor     r9d, r9d; dwFlags
0x180084b26  call    BCryptHashData
0x180084b2b  mov     ebx, eax
0x180084b2d  test    eax, eax
0x180084b2f  jns     short loc_180084B39
0x180084b31  mov     r9d, 1C1h
0x180084b37  jmp     short loc_180084B13
0x180084b39  mov     rcx, [rbp+37h+phHash]; hHash
0x180084b3d  lea     rdx, g_rgbPad1; "666666666666666666666666666666666666666"...
0x180084b44  xor     r9d, r9d; dwFlags
0x180084b47  mov     r8d, r12d; cbInput
0x180084b4a  call    BCryptHashData
0x180084b4f  mov     ebx, eax
0x180084b51  test    eax, eax
0x180084b53  jns     short loc_180084B5D
0x180084b55  mov     r9d, 1CDh
0x180084b5b  jmp     short loc_180084B13
0x180084b5d  mov     r12d, [rbp+37h+cbInput]
0x180084b61  lea     rdx, [rbp+37h+pbInput]; pbInput
0x180084b65  mov     rax, [rbp+37h+var_90]
0x180084b69  xor     r9d, r9d; dwFlags
0x180084b6c  mov     rcx, [rbp+37h+phHash]; hHash
0x180084b70  bswap   rax
0x180084b73  mov     qword ptr [rbp+37h+pbInput], rax
0x180084b77  mov     eax, [rbp+37h+var_98]
0x180084b7a  lea     r8d, [r9+0Bh]; cbInput
0x180084b7e  mov     [rbp+37h+var_70], al
0x180084b81  mov     eax, r12d
0x180084b84  shr     eax, 8
0x180084b87  mov     [rbp+37h+var_6F], al
0x180084b8a  mov     [rbp+37h+var_6E], r12b
0x180084b8e  call    BCryptHashData
0x180084b93  mov     ebx, eax
0x180084b95  test    eax, eax
0x180084b97  jns     short loc_180084BA4
0x180084b99  mov     r9d, 1EAh
0x180084b9f  jmp     loc_180084B13
0x180084ba4  mov     rdx, [rbp+37h+var_88]; pbInput
0x180084ba8  xor     r9d, r9d; dwFlags
0x180084bab  mov     rcx, [rbp+37h+phHash]; hHash
0x180084baf  mov     r8d, r12d; cbInput
0x180084bb2  call    BCryptHashData
0x180084bb7  mov     ebx, eax
0x180084bb9  test    eax, eax
0x180084bbb  jns     short loc_180084BC8
0x180084bbd  mov     r9d, 1F6h
0x180084bc3  jmp     loc_180084B13
0x180084bc8  mov     r8, [rdi+10h]
0x180084bcc  lea     rdx, [rbp+37h+pbOutput]; pbOutput
0x180084bd0  mov     rcx, [rbp+37h+phHash]; hHash
0x180084bd4  xor     r9d, r9d; dwFlags
0x180084bd7  mov     r8d, [r8+44h]; cbOutput
0x180084bdb  call    BCryptFinishHash
0x180084be0  mov     ebx, eax
0x180084be2  test    eax, eax
0x180084be4  jns     short loc_180084BF1
0x180084be6  mov     r9d, 202h
0x180084bec  jmp     loc_180084B13
0x180084bf1  mov     rcx, [rbp+37h+phHash]; hHash
0x180084bf5  call    BCryptDestroyHash
0x180084bfa  mov     r9d, [rsi+r15+18h]; cbHashObject
0x180084bff  lea     rdx, [rbp+37h+phHash]; phHash
0x180084c03  mov     rcx, [rsi+r15]; hAlgorithm
0x180084c07  xor     eax, eax
0x180084c09  mov     [rsp+0E0h+dwFlags], eax; dwFlags
0x180084c0d  mov     r8, r14; pbHashObject
0x180084c10  mov     [rsp+0E0h+cbSecret], eax; cbSecret
0x180084c14  mov     [rsp+0E0h+pbSecret], rax; pbSecret
0x180084c19  mov     [rbp+37h+phHash], rax
0x180084c1d  call    BCryptCreateHash
0x180084c22  mov     ebx, eax
0x180084c24  test    eax, eax
0x180084c26  jns     short loc_180084C33
0x180084c28  mov     r9d, 217h
0x180084c2e  jmp     loc_180084B13
0x180084c33  mov     r8d, [rdi+68h]; cbInput
0x180084c37  lea     rdx, [rdi+38h]; pbInput
0x180084c3b  mov     rcx, [rbp+37h+phHash]; hHash
0x180084c3f  xor     r9d, r9d; dwFlags
0x180084c42  call    BCryptHashData
0x180084c47  mov     ebx, eax
0x180084c49  test    eax, eax
0x180084c4b  jns     short loc_180084C58
0x180084c4d  mov     r9d, 223h
0x180084c53  jmp     loc_180084B13
0x180084c58  mov     r8d, [rbp+37h+var_94]; cbInput
0x180084c5c  lea     rdx, g_rgbPad2; pbInput
0x180084c63  mov     rcx, [rbp+37h+phHash]; hHash
0x180084c67  xor     r9d, r9d; dwFlags
0x180084c6a  call    BCryptHashData
0x180084c6f  mov     ebx, eax
0x180084c71  test    eax, eax
0x180084c73  jns     short loc_180084C80
0x180084c75  mov     r9d, 22Fh
0x180084c7b  jmp     loc_180084B13
0x180084c80  mov     r8, [rdi+10h]
0x180084c84  lea     rdx, [rbp+37h+pbOutput]; pbInput
0x180084c88  mov     rcx, [rbp+37h+phHash]; hHash
0x180084c8c  xor     r9d, r9d; dwFlags
0x180084c8f  mov     r8d, [r8+44h]; cbInput
0x180084c93  call    BCryptHashData
0x180084c98  mov     ebx, eax
0x180084c9a  test    eax, eax
0x180084c9c  jns     short loc_180084CA9
0x180084c9e  mov     r9d, 23Ah
0x180084ca4  jmp     loc_180084B13
0x180084ca9  mov     r8d, [rbp+37h+cbOutput]; cbOutput
0x180084cad  xor     r9d, r9d; dwFlags
0x180084cb0  mov     rdx, [rbp+37h+var_80]; pbOutput
0x180084cb4  mov     rcx, [rbp+37h+phHash]; hHash
0x180084cb8  call    BCryptFinishHash
0x180084cbd  mov     ebx, eax
0x180084cbf  test    eax, eax
0x180084cc1  jns     short loc_180084CCE
0x180084cc3  mov     r9d, 246h
0x180084cc9  jmp     loc_180084B13
0x180084cce  mov     rcx, [rbp+37h+phHash]; hHash
0x180084cd2  call    BCryptDestroyHash
0x180084cd7  xor     ebx, ebx
0x180084cd9  mov     [rbp+37h+phHash], 0
0x180084ce1  mov     rcx, [rbp+37h+phHash]; hHash
0x180084ce5  test    rcx, rcx
0x180084ce8  jz      short loc_180084CEF
0x180084cea  call    BCryptDestroyHash
0x180084cef  test    r14, r14
0x180084cf2  jz      short loc_180084D08
0x180084cf4  mov     rcx, [rsi+r15+10h]; Lookaside
0x180084cf9  mov     rdx, r14; Entry
0x180084cfc  call    cs:__imp_ExFreeToPagedLookasideList
0x180084d03  nop     dword ptr [rax+rax+00h]
0x180084d08  mov     eax, ebx
0x180084d0a  mov     rcx, [rbp+37h+var_38]
0x180084d0e  xor     rcx, rsp; StackCookie
0x180084d11  call    __security_check_cookie
0x180084d16  mov     rbx, [rsp+0E0h+arg_10]
0x180084d1e  add     rsp, 0B0h
0x180084d25  pop     r15
0x180084d27  pop     r14
0x180084d29  pop     r13
0x180084d2b  pop     r12
0x180084d2d  pop     rdi
0x180084d2e  pop     rsi
0x180084d2f  pop     rbp
0x180084d30  retn
```
