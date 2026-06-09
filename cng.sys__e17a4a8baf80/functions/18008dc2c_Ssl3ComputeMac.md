# Ssl3ComputeMac

- ea: `0x18008dc2c`
- end: `0x18008df32`
- name: `Ssl3ComputeMac`
- size: `774`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, ULONG cbInput, __int64, ULONG cbOutput)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800484b0`
- `0x18004899c`

## callees

- `0x18000ba50`
- `0x18000d5d0`
- `0x180010600`
- `0x18001155c`
- `0x180012210`
- `0x18008dc2c`
- `0x1800a4260`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18008dca9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x18008dca9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18008defc`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x18008defc`

## string_xrefs

- `0x18008dcd4`: `onecore\ds\security\cryptoapi\ncrypt\schannel\ssl3key.c`
- `0x18008dd3d`: `666666666666666666666666666666666666666666666666\Registry\MACHINE\System\CurrentControlSet\Control\Cryptography\Providers\Microsoft SSL Protocol Provider`

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
          (PUCHAR)"666666666666666666666666666666666666666666666666\\\x00R\x00e\x00g\x00i\x00s\x00t\x00r\x00y\x00\\\x00M\x00"
                  "A\x00C\x00H\x00I\x00N\x00E\x00\\\x00S\x00y\x00s\x00t\x00e\x00m\x00\\\x00C\x00u\x00r\x00r\x00e\x00n\x00"
                  "t\x00C\x00o\x00n\x00t\x00r\x00o\x00l\x00S\x00e\x00t\x00\\\x00C\x00o\x00n\x00t\x00r\x00o\x00l\x00\\\x00"
                  "C\x00r\x00y\x00p\x00t\x00o\x00g\x00r\x00a\x00p\x00h\x00y\x00\\\x00P\x00r\x00o\x00v\x00i\x00d\x00e\x00r"
                  "\x00s\x00\\\x00M\x00i\x00c\x00r\x00o\x00s\x00o\x00f\x00t\x00 \x00S\x00S\x00L\x00 \x00P\x00r\x00o\x00t\x00"
                  "o\x00c\x00o\x00l\x00 \x00P\x00r\x00o\x00v\x00i\x00d\x00e\x00r",
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
0x18008dc2c  mov     [rsp-8+arg_10], rbx
0x18008dc31  push    rbp
0x18008dc32  push    rsi
0x18008dc33  push    rdi
0x18008dc34  push    r12
0x18008dc36  push    r13
0x18008dc38  push    r14
0x18008dc3a  push    r15
0x18008dc3c  lea     rbp, [rsp-7]
0x18008dc41  sub     rsp, 0B0h
0x18008dc48  mov     rax, cs:__security_cookie
0x18008dc4f  xor     rax, rsp
0x18008dc52  mov     [rbp+37h+var_38], rax
0x18008dc56  mov     rax, [rbp+37h+arg_20]
0x18008dc5a  xor     ebx, ebx
0x18008dc5c  mov     [rbp+37h+var_88], rax
0x18008dc60  mov     r15, rcx
0x18008dc63  mov     rax, [rbp+37h+arg_30]
0x18008dc67  mov     ecx, 8003h
0x18008dc6c  mov     [rbp+37h+var_80], rax
0x18008dc70  mov     esi, 138h
0x18008dc75  mov     rax, [rdx+10h]
0x18008dc79  lea     r12d, [rbx+30h]
0x18008dc7d  mov     [rbp+37h+var_98], r8d
0x18008dc81  mov     rdi, rdx
0x18008dc84  mov     [rbp+37h+phHash], rbx
0x18008dc88  mov     [rbp+37h+var_90], r9
0x18008dc8c  mov     r8d, [rax+40h]
0x18008dc90  cmp     r8d, ecx
0x18008dc93  lea     eax, [rbx+28h]
0x18008dc96  cmovnz  r12d, eax
0x18008dc9a  lea     eax, [rsi+28h]
0x18008dc9d  cmovnz  esi, eax
0x18008dca0  mov     [rbp+37h+var_94], r12d
0x18008dca4  mov     rcx, [rsi+r15+10h]; Lookaside
0x18008dca9  call    cs:__imp_ExAllocateFromPagedLookasideList
0x18008dcb0  nop     dword ptr [rax+rax+00h]
0x18008dcb5  mov     r14, rax
0x18008dcb8  test    rax, rax
0x18008dcbb  jnz     short loc_18008DCE5
0x18008dcbd  mov     ebx, 8009000Eh
0x18008dcc2  mov     r9d, 1A3h
0x18008dcc8  mov     ecx, 8009000Eh
0x18008dccd  lea     rdx, aStatus; "Status"
0x18008dcd4  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008dcdb  call    DebugTraceError
0x18008dce0  jmp     loc_18008DEE1
0x18008dce5  mov     r9d, [rsi+r15+18h]; cbHashObject
0x18008dcea  lea     rdx, [rbp+37h+phHash]; phHash
0x18008dcee  mov     rcx, [rsi+r15]; hAlgorithm
0x18008dcf2  mov     r8, r14; pbHashObject
0x18008dcf5  mov     [rsp+0E0h+dwFlags], ebx; dwFlags
0x18008dcf9  mov     [rsp+0E0h+cbSecret], ebx; cbSecret
0x18008dcfd  mov     [rsp+0E0h+pbSecret], rbx; pbSecret
0x18008dd02  call    BCryptCreateHash
0x18008dd07  mov     ebx, eax
0x18008dd09  test    eax, eax
0x18008dd0b  jns     short loc_18008DD17
0x18008dd0d  mov     r9d, 1B5h
0x18008dd13  mov     ecx, eax
0x18008dd15  jmp     short loc_18008DCCD
0x18008dd17  mov     r8d, [rdi+68h]; cbInput
0x18008dd1b  lea     rdx, [rdi+38h]; pbInput
0x18008dd1f  mov     rcx, [rbp+37h+phHash]; hHash
0x18008dd23  xor     r9d, r9d; dwFlags
0x18008dd26  call    BCryptHashData
0x18008dd2b  mov     ebx, eax
0x18008dd2d  test    eax, eax
0x18008dd2f  jns     short loc_18008DD39
0x18008dd31  mov     r9d, 1C1h
0x18008dd37  jmp     short loc_18008DD13
0x18008dd39  mov     rcx, [rbp+37h+phHash]; hHash
0x18008dd3d  lea     rdx, g_rgbPad1; "666666666666666666666666666666666666666"...
0x18008dd44  xor     r9d, r9d; dwFlags
0x18008dd47  mov     r8d, r12d; cbInput
0x18008dd4a  call    BCryptHashData
0x18008dd4f  mov     ebx, eax
0x18008dd51  test    eax, eax
0x18008dd53  jns     short loc_18008DD5D
0x18008dd55  mov     r9d, 1CDh
0x18008dd5b  jmp     short loc_18008DD13
0x18008dd5d  mov     r12d, [rbp+37h+cbInput]
0x18008dd61  lea     rdx, [rbp+37h+pbInput]; pbInput
0x18008dd65  mov     rax, [rbp+37h+var_90]
0x18008dd69  xor     r9d, r9d; dwFlags
0x18008dd6c  mov     rcx, [rbp+37h+phHash]; hHash
0x18008dd70  bswap   rax
0x18008dd73  mov     qword ptr [rbp+37h+pbInput], rax
0x18008dd77  mov     eax, [rbp+37h+var_98]
0x18008dd7a  lea     r8d, [r9+0Bh]; cbInput
0x18008dd7e  mov     [rbp+37h+var_70], al
0x18008dd81  mov     eax, r12d
0x18008dd84  shr     eax, 8
0x18008dd87  mov     [rbp+37h+var_6F], al
0x18008dd8a  mov     [rbp+37h+var_6E], r12b
0x18008dd8e  call    BCryptHashData
0x18008dd93  mov     ebx, eax
0x18008dd95  test    eax, eax
0x18008dd97  jns     short loc_18008DDA4
0x18008dd99  mov     r9d, 1EAh
0x18008dd9f  jmp     loc_18008DD13
0x18008dda4  mov     rdx, [rbp+37h+var_88]; pbInput
0x18008dda8  xor     r9d, r9d; dwFlags
0x18008ddab  mov     rcx, [rbp+37h+phHash]; hHash
0x18008ddaf  mov     r8d, r12d; cbInput
0x18008ddb2  call    BCryptHashData
0x18008ddb7  mov     ebx, eax
0x18008ddb9  test    eax, eax
0x18008ddbb  jns     short loc_18008DDC8
0x18008ddbd  mov     r9d, 1F6h
0x18008ddc3  jmp     loc_18008DD13
0x18008ddc8  mov     r8, [rdi+10h]
0x18008ddcc  lea     rdx, [rbp+37h+pbOutput]; pbOutput
0x18008ddd0  mov     rcx, [rbp+37h+phHash]; hHash
0x18008ddd4  xor     r9d, r9d; dwFlags
0x18008ddd7  mov     r8d, [r8+44h]; cbOutput
0x18008dddb  call    BCryptFinishHash
0x18008dde0  mov     ebx, eax
0x18008dde2  test    eax, eax
0x18008dde4  jns     short loc_18008DDF1
0x18008dde6  mov     r9d, 202h
0x18008ddec  jmp     loc_18008DD13
0x18008ddf1  mov     rcx, [rbp+37h+phHash]; hHash
0x18008ddf5  call    BCryptDestroyHash
0x18008ddfa  mov     r9d, [rsi+r15+18h]; cbHashObject
0x18008ddff  lea     rdx, [rbp+37h+phHash]; phHash
0x18008de03  mov     rcx, [rsi+r15]; hAlgorithm
0x18008de07  xor     eax, eax
0x18008de09  mov     [rsp+0E0h+dwFlags], eax; dwFlags
0x18008de0d  mov     r8, r14; pbHashObject
0x18008de10  mov     [rsp+0E0h+cbSecret], eax; cbSecret
0x18008de14  mov     [rsp+0E0h+pbSecret], rax; pbSecret
0x18008de19  mov     [rbp+37h+phHash], rax
0x18008de1d  call    BCryptCreateHash
0x18008de22  mov     ebx, eax
0x18008de24  test    eax, eax
0x18008de26  jns     short loc_18008DE33
0x18008de28  mov     r9d, 217h
0x18008de2e  jmp     loc_18008DD13
0x18008de33  mov     r8d, [rdi+68h]; cbInput
0x18008de37  lea     rdx, [rdi+38h]; pbInput
0x18008de3b  mov     rcx, [rbp+37h+phHash]; hHash
0x18008de3f  xor     r9d, r9d; dwFlags
0x18008de42  call    BCryptHashData
0x18008de47  mov     ebx, eax
0x18008de49  test    eax, eax
0x18008de4b  jns     short loc_18008DE58
0x18008de4d  mov     r9d, 223h
0x18008de53  jmp     loc_18008DD13
0x18008de58  mov     r8d, [rbp+37h+var_94]; cbInput
0x18008de5c  lea     rdx, g_rgbPad2; pbInput
0x18008de63  mov     rcx, [rbp+37h+phHash]; hHash
0x18008de67  xor     r9d, r9d; dwFlags
0x18008de6a  call    BCryptHashData
0x18008de6f  mov     ebx, eax
0x18008de71  test    eax, eax
0x18008de73  jns     short loc_18008DE80
0x18008de75  mov     r9d, 22Fh
0x18008de7b  jmp     loc_18008DD13
0x18008de80  mov     r8, [rdi+10h]
0x18008de84  lea     rdx, [rbp+37h+pbOutput]; pbInput
0x18008de88  mov     rcx, [rbp+37h+phHash]; hHash
0x18008de8c  xor     r9d, r9d; dwFlags
0x18008de8f  mov     r8d, [r8+44h]; cbInput
0x18008de93  call    BCryptHashData
0x18008de98  mov     ebx, eax
0x18008de9a  test    eax, eax
0x18008de9c  jns     short loc_18008DEA9
0x18008de9e  mov     r9d, 23Ah
0x18008dea4  jmp     loc_18008DD13
0x18008dea9  mov     r8d, [rbp+37h+cbOutput]; cbOutput
0x18008dead  xor     r9d, r9d; dwFlags
0x18008deb0  mov     rdx, [rbp+37h+var_80]; pbOutput
0x18008deb4  mov     rcx, [rbp+37h+phHash]; hHash
0x18008deb8  call    BCryptFinishHash
0x18008debd  mov     ebx, eax
0x18008debf  test    eax, eax
0x18008dec1  jns     short loc_18008DECE
0x18008dec3  mov     r9d, 246h
0x18008dec9  jmp     loc_18008DD13
0x18008dece  mov     rcx, [rbp+37h+phHash]; hHash
0x18008ded2  call    BCryptDestroyHash
0x18008ded7  xor     ebx, ebx
0x18008ded9  mov     [rbp+37h+phHash], 0
0x18008dee1  mov     rcx, [rbp+37h+phHash]; hHash
0x18008dee5  test    rcx, rcx
0x18008dee8  jz      short loc_18008DEEF
0x18008deea  call    BCryptDestroyHash
0x18008deef  test    r14, r14
0x18008def2  jz      short loc_18008DF08
0x18008def4  mov     rcx, [rsi+r15+10h]; Lookaside
0x18008def9  mov     rdx, r14; Entry
0x18008defc  call    cs:__imp_ExFreeToPagedLookasideList
0x18008df03  nop     dword ptr [rax+rax+00h]
0x18008df08  mov     eax, ebx
0x18008df0a  mov     rcx, [rbp+37h+var_38]
0x18008df0e  xor     rcx, rsp; StackCookie
0x18008df11  call    __security_check_cookie
0x18008df16  mov     rbx, [rsp+0E0h+arg_10]
0x18008df1e  add     rsp, 0B0h
0x18008df25  pop     r15
0x18008df27  pop     r14
0x18008df29  pop     r13
0x18008df2b  pop     r12
0x18008df2d  pop     rdi
0x18008df2e  pop     rsi
0x18008df2f  pop     rbp
0x18008df30  retn
```
