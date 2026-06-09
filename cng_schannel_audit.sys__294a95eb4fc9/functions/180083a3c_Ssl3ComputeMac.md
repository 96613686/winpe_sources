# Ssl3ComputeMac

- ea: `0x180083a3c`
- end: `0x180083d42`
- name: `Ssl3ComputeMac`
- size: `774`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, ULONG cbInput, __int64, ULONG cbOutput)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003e4f0`
- `0x18003e9dc`

## callees

- `0x180001930`
- `0x1800034b0`
- `0x1800064e0`
- `0x18000743c`
- `0x1800080f0`
- `0x180083a3c`
- `0x18009d820`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180083ab9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x180083ab9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180083d0c`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x180083d0c`

## string_xrefs

- `0x180083ae4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\ssl3key.c`

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
0x180083a3c  mov     [rsp-8+arg_10], rbx
0x180083a41  push    rbp
0x180083a42  push    rsi
0x180083a43  push    rdi
0x180083a44  push    r12
0x180083a46  push    r13
0x180083a48  push    r14
0x180083a4a  push    r15
0x180083a4c  lea     rbp, [rsp-7]
0x180083a51  sub     rsp, 0B0h
0x180083a58  mov     rax, cs:__security_cookie
0x180083a5f  xor     rax, rsp
0x180083a62  mov     [rbp+37h+var_38], rax
0x180083a66  mov     rax, [rbp+37h+arg_20]
0x180083a6a  xor     ebx, ebx
0x180083a6c  mov     [rbp+37h+var_88], rax
0x180083a70  mov     r15, rcx
0x180083a73  mov     rax, [rbp+37h+arg_30]
0x180083a77  mov     ecx, 8003h
0x180083a7c  mov     [rbp+37h+var_80], rax
0x180083a80  mov     esi, 138h
0x180083a85  mov     rax, [rdx+10h]
0x180083a89  lea     r12d, [rbx+30h]
0x180083a8d  mov     [rbp+37h+var_98], r8d
0x180083a91  mov     rdi, rdx
0x180083a94  mov     [rbp+37h+phHash], rbx
0x180083a98  mov     [rbp+37h+var_90], r9
0x180083a9c  mov     r8d, [rax+40h]
0x180083aa0  cmp     r8d, ecx
0x180083aa3  lea     eax, [rbx+28h]
0x180083aa6  cmovnz  r12d, eax
0x180083aaa  lea     eax, [rsi+28h]
0x180083aad  cmovnz  esi, eax
0x180083ab0  mov     [rbp+37h+var_94], r12d
0x180083ab4  mov     rcx, [rsi+r15+10h]; Lookaside
0x180083ab9  call    cs:__imp_ExAllocateFromPagedLookasideList
0x180083ac0  nop     dword ptr [rax+rax+00h]
0x180083ac5  mov     r14, rax
0x180083ac8  test    rax, rax
0x180083acb  jnz     short loc_180083AF5
0x180083acd  mov     ebx, 8009000Eh
0x180083ad2  mov     r9d, 1A3h
0x180083ad8  mov     ecx, 8009000Eh
0x180083add  lea     rdx, aStatus; "Status"
0x180083ae4  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180083aeb  call    DebugTraceError
0x180083af0  jmp     loc_180083CF1
0x180083af5  mov     r9d, [rsi+r15+18h]; cbHashObject
0x180083afa  lea     rdx, [rbp+37h+phHash]; phHash
0x180083afe  mov     rcx, [rsi+r15]; hAlgorithm
0x180083b02  mov     r8, r14; pbHashObject
0x180083b05  mov     [rsp+0E0h+dwFlags], ebx; dwFlags
0x180083b09  mov     [rsp+0E0h+cbSecret], ebx; cbSecret
0x180083b0d  mov     [rsp+0E0h+pbSecret], rbx; pbSecret
0x180083b12  call    BCryptCreateHash
0x180083b17  mov     ebx, eax
0x180083b19  test    eax, eax
0x180083b1b  jns     short loc_180083B27
0x180083b1d  mov     r9d, 1B5h
0x180083b23  mov     ecx, eax
0x180083b25  jmp     short loc_180083ADD
0x180083b27  mov     r8d, [rdi+68h]; cbInput
0x180083b2b  lea     rdx, [rdi+38h]; pbInput
0x180083b2f  mov     rcx, [rbp+37h+phHash]; hHash
0x180083b33  xor     r9d, r9d; dwFlags
0x180083b36  call    BCryptHashData
0x180083b3b  mov     ebx, eax
0x180083b3d  test    eax, eax
0x180083b3f  jns     short loc_180083B49
0x180083b41  mov     r9d, 1C1h
0x180083b47  jmp     short loc_180083B23
0x180083b49  mov     rcx, [rbp+37h+phHash]; hHash
0x180083b4d  lea     rdx, g_rgbPad1; "666666666666666666666666666666666666666"...
0x180083b54  xor     r9d, r9d; dwFlags
0x180083b57  mov     r8d, r12d; cbInput
0x180083b5a  call    BCryptHashData
0x180083b5f  mov     ebx, eax
0x180083b61  test    eax, eax
0x180083b63  jns     short loc_180083B6D
0x180083b65  mov     r9d, 1CDh
0x180083b6b  jmp     short loc_180083B23
0x180083b6d  mov     r12d, [rbp+37h+cbInput]
0x180083b71  lea     rdx, [rbp+37h+pbInput]; pbInput
0x180083b75  mov     rax, [rbp+37h+var_90]
0x180083b79  xor     r9d, r9d; dwFlags
0x180083b7c  mov     rcx, [rbp+37h+phHash]; hHash
0x180083b80  bswap   rax
0x180083b83  mov     qword ptr [rbp+37h+pbInput], rax
0x180083b87  mov     eax, [rbp+37h+var_98]
0x180083b8a  lea     r8d, [r9+0Bh]; cbInput
0x180083b8e  mov     [rbp+37h+var_70], al
0x180083b91  mov     eax, r12d
0x180083b94  shr     eax, 8
0x180083b97  mov     [rbp+37h+var_6F], al
0x180083b9a  mov     [rbp+37h+var_6E], r12b
0x180083b9e  call    BCryptHashData
0x180083ba3  mov     ebx, eax
0x180083ba5  test    eax, eax
0x180083ba7  jns     short loc_180083BB4
0x180083ba9  mov     r9d, 1EAh
0x180083baf  jmp     loc_180083B23
0x180083bb4  mov     rdx, [rbp+37h+var_88]; pbInput
0x180083bb8  xor     r9d, r9d; dwFlags
0x180083bbb  mov     rcx, [rbp+37h+phHash]; hHash
0x180083bbf  mov     r8d, r12d; cbInput
0x180083bc2  call    BCryptHashData
0x180083bc7  mov     ebx, eax
0x180083bc9  test    eax, eax
0x180083bcb  jns     short loc_180083BD8
0x180083bcd  mov     r9d, 1F6h
0x180083bd3  jmp     loc_180083B23
0x180083bd8  mov     r8, [rdi+10h]
0x180083bdc  lea     rdx, [rbp+37h+pbOutput]; pbOutput
0x180083be0  mov     rcx, [rbp+37h+phHash]; hHash
0x180083be4  xor     r9d, r9d; dwFlags
0x180083be7  mov     r8d, [r8+44h]; cbOutput
0x180083beb  call    BCryptFinishHash
0x180083bf0  mov     ebx, eax
0x180083bf2  test    eax, eax
0x180083bf4  jns     short loc_180083C01
0x180083bf6  mov     r9d, 202h
0x180083bfc  jmp     loc_180083B23
0x180083c01  mov     rcx, [rbp+37h+phHash]; hHash
0x180083c05  call    BCryptDestroyHash
0x180083c0a  mov     r9d, [rsi+r15+18h]; cbHashObject
0x180083c0f  lea     rdx, [rbp+37h+phHash]; phHash
0x180083c13  mov     rcx, [rsi+r15]; hAlgorithm
0x180083c17  xor     eax, eax
0x180083c19  mov     [rsp+0E0h+dwFlags], eax; dwFlags
0x180083c1d  mov     r8, r14; pbHashObject
0x180083c20  mov     [rsp+0E0h+cbSecret], eax; cbSecret
0x180083c24  mov     [rsp+0E0h+pbSecret], rax; pbSecret
0x180083c29  mov     [rbp+37h+phHash], rax
0x180083c2d  call    BCryptCreateHash
0x180083c32  mov     ebx, eax
0x180083c34  test    eax, eax
0x180083c36  jns     short loc_180083C43
0x180083c38  mov     r9d, 217h
0x180083c3e  jmp     loc_180083B23
0x180083c43  mov     r8d, [rdi+68h]; cbInput
0x180083c47  lea     rdx, [rdi+38h]; pbInput
0x180083c4b  mov     rcx, [rbp+37h+phHash]; hHash
0x180083c4f  xor     r9d, r9d; dwFlags
0x180083c52  call    BCryptHashData
0x180083c57  mov     ebx, eax
0x180083c59  test    eax, eax
0x180083c5b  jns     short loc_180083C68
0x180083c5d  mov     r9d, 223h
0x180083c63  jmp     loc_180083B23
0x180083c68  mov     r8d, [rbp+37h+var_94]; cbInput
0x180083c6c  lea     rdx, g_rgbPad2; pbInput
0x180083c73  mov     rcx, [rbp+37h+phHash]; hHash
0x180083c77  xor     r9d, r9d; dwFlags
0x180083c7a  call    BCryptHashData
0x180083c7f  mov     ebx, eax
0x180083c81  test    eax, eax
0x180083c83  jns     short loc_180083C90
0x180083c85  mov     r9d, 22Fh
0x180083c8b  jmp     loc_180083B23
0x180083c90  mov     r8, [rdi+10h]
0x180083c94  lea     rdx, [rbp+37h+pbOutput]; pbInput
0x180083c98  mov     rcx, [rbp+37h+phHash]; hHash
0x180083c9c  xor     r9d, r9d; dwFlags
0x180083c9f  mov     r8d, [r8+44h]; cbInput
0x180083ca3  call    BCryptHashData
0x180083ca8  mov     ebx, eax
0x180083caa  test    eax, eax
0x180083cac  jns     short loc_180083CB9
0x180083cae  mov     r9d, 23Ah
0x180083cb4  jmp     loc_180083B23
0x180083cb9  mov     r8d, [rbp+37h+cbOutput]; cbOutput
0x180083cbd  xor     r9d, r9d; dwFlags
0x180083cc0  mov     rdx, [rbp+37h+var_80]; pbOutput
0x180083cc4  mov     rcx, [rbp+37h+phHash]; hHash
0x180083cc8  call    BCryptFinishHash
0x180083ccd  mov     ebx, eax
0x180083ccf  test    eax, eax
0x180083cd1  jns     short loc_180083CDE
0x180083cd3  mov     r9d, 246h
0x180083cd9  jmp     loc_180083B23
0x180083cde  mov     rcx, [rbp+37h+phHash]; hHash
0x180083ce2  call    BCryptDestroyHash
0x180083ce7  xor     ebx, ebx
0x180083ce9  mov     [rbp+37h+phHash], 0
0x180083cf1  mov     rcx, [rbp+37h+phHash]; hHash
0x180083cf5  test    rcx, rcx
0x180083cf8  jz      short loc_180083CFF
0x180083cfa  call    BCryptDestroyHash
0x180083cff  test    r14, r14
0x180083d02  jz      short loc_180083D18
0x180083d04  mov     rcx, [rsi+r15+10h]; Lookaside
0x180083d09  mov     rdx, r14; Entry
0x180083d0c  call    cs:__imp_ExFreeToPagedLookasideList
0x180083d13  nop     dword ptr [rax+rax+00h]
0x180083d18  mov     eax, ebx
0x180083d1a  mov     rcx, [rbp+37h+var_38]
0x180083d1e  xor     rcx, rsp; StackCookie
0x180083d21  call    __security_check_cookie
0x180083d26  mov     rbx, [rsp+0E0h+arg_10]
0x180083d2e  add     rsp, 0B0h
0x180083d35  pop     r15
0x180083d37  pop     r14
0x180083d39  pop     r13
0x180083d3b  pop     r12
0x180083d3d  pop     rdi
0x180083d3e  pop     rsi
0x180083d3f  pop     rbp
0x180083d40  retn
```
