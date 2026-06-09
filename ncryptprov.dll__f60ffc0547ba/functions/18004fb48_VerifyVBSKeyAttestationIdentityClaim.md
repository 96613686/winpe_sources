# VerifyVBSKeyAttestationIdentityClaim

- ea: `0x18004fb48`
- end: `0x18004feff`
- name: `VerifyVBSKeyAttestationIdentityClaim`
- size: `951`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18004f87c`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x1800398b0`
- `0x18004f254`
- `0x18004fb48`
- `0x18005f80c`
- `0x18005fd54`
- `0x18005fe50`

## import_xrefs

- `bcrypt!BCryptVerifySignature` at `0x18004fda0`
- `bcrypt!BCryptVerifySignature` at `0x18004fda0`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004feb1`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004feb1`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004fcf2`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004fcf2`

## string_xrefs

- `0x18004fbb2`: `onecore\ds\security\cryptoapi\ncrypt\storage\verifyclaim.c`
- `0x18004fc0c`: `onecore\ds\security\cryptoapi\ncrypt\storage\verifyclaim.c`
- `0x18004fcca`: `onecore\ds\security\cryptoapi\ncrypt\storage\verifyclaim.c`
- `0x18004fd53`: `onecore\ds\security\cryptoapi\ncrypt\storage\verifyclaim.c`
- `0x18004fc75`: `onecore\ds\security\cryptoapi\ncrypt\common\vbsattestation\serialization.cxx`

## pseudocode

```c
__int64 __fastcall VerifyVBSKeyAttestationIdentityClaim(UCHAR *pbInput, void *a2, void *a3, __int64 a4, int a5)
{
  PUCHAR v5; // r13
  bool v6; // zf
  int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // r14
  UCHAR *v14; // r14
  int IsRsaKey; // eax
  __int64 v16; // r9
  __int64 v17; // rcx
  NTSTATUS v18; // eax
  __int64 v19; // r9
  UCHAR *v20; // r14
  int v21; // eax
  NTSTATUS v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // ecx
  unsigned int v25; // eax
  __int64 v26; // rax
  __int64 v27; // r14
  void *v28; // rcx
  unsigned int v30; // [rsp+5Ch] [rbp-1Dh]
  unsigned int v31; // [rsp+60h] [rbp-19h]
  WCHAR *pszAlgId; // [rsp+78h] [rbp-1h]
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+80h] [rbp+7h] BYREF
  PUCHAR v34; // [rsp+88h] [rbp+Fh]

  v5 = pbInput + 32;
  v6 = (*((_DWORD *)pbInput + 9) & 0xFFFFFFE0) == 0;
  phAlgorithm = 0;
  if ( !v6 )
  {
    v9 = -1073739509;
    v10 = 1101;
    v11 = 3221227787LL;
LABEL_3:
    DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\verifyclaim.c", v10);
    goto LABEL_28;
  }
  v12 = *((unsigned int *)pbInput + 3);
  v13 = *((unsigned int *)pbInput + 4);
  v34 = &v5[*((unsigned int *)pbInput + 2)];
  v14 = &v34[v12 + v13];
  pszAlgId = (WCHAR *)&v34[v12];
  v30 = *((_DWORD *)pbInput + 5);
  v31 = *((_DWORD *)pbInput + 6);
  if ( v30 )
  {
    IsRsaKey = VBSAttestationIsRsaKey(a3);
    v9 = IsRsaKey;
    if ( IsRsaKey >= 0 )
    {
      v9 = -1073739509;
      v16 = 1119;
      v17 = 3221227787LL;
    }
    else
    {
      v16 = 1113;
      v17 = (unsigned int)IsRsaKey;
    }
    DebugTraceError(v17, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\verifyclaim.c", v16);
    goto LABEL_28;
  }
  v18 = VBSAttestationComparePublicKeys(a2, pbInput + 44);
  v9 = v18;
  if ( v18 < 0 )
  {
    v19 = 1152;
LABEL_11:
    DebugTraceError(
      (unsigned int)v18,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\verifyclaim.c",
      v19);
    goto LABEL_28;
  }
  v18 = BCryptOpenAlgorithmProvider(&phAlgorithm, pszAlgId, 0, 0);
  v9 = v18;
  if ( v18 < 0 )
  {
    v19 = 1164;
    goto LABEL_11;
  }
  v20 = &v14[v30];
  v21 = VBSAttestationBuildIdentityClaimHashBuffer(phAlgorithm, v34, (PUCHAR)pszAlgId, v20, 0, pbInput);
  v9 = v21;
  if ( v21 < 0 )
  {
    DebugTraceError(
      (unsigned int)v21,
      "Status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\verifyclaim.c",
      1181);
    goto LABEL_28;
  }
  v22 = BCryptVerifySignature(a3, 0, 0, 0, &v20[v31], *((_DWORD *)pbInput + 7), 0);
  v9 = v22;
  if ( v22 < 0 )
  {
    v10 = 1196;
    v11 = (unsigned int)v22;
    goto LABEL_3;
  }
  if ( a5 == 0x100000 && a4 )
  {
    v23 = *((_DWORD *)pbInput + 4);
    v24 = v23 + 40;
    if ( v23 + 40 < v23 )
    {
      v10 = 1208;
LABEL_22:
      v9 = -1073741675;
      v11 = 3221225621LL;
      goto LABEL_3;
    }
    v25 = *((_DWORD *)pbInput + 5);
    if ( v24 + v25 < v25 )
    {
      v10 = 1214;
      goto LABEL_22;
    }
    v26 = SafeAllocaAllocateFromHeap(v24 + v25);
    *(_QWORD *)(a4 + 8) = v26;
    if ( !v26 )
    {
      v9 = -1073741801;
      v10 = 1221;
      v11 = 3221225495LL;
      goto LABEL_3;
    }
    *(_OWORD *)v26 = 0;
    v9 = 0;
    *(_OWORD *)(v26 + 16) = 0;
    *(_QWORD *)(v26 + 32) = 0;
    v27 = *(_QWORD *)(a4 + 8);
    *(_DWORD *)a4 = 40;
    *(_DWORD *)(a4 + 4) = 95;
    *(_DWORD *)v27 = *((_DWORD *)v5 + 1);
    v28 = (void *)(*(_QWORD *)(a4 + 8) + 40LL);
    *(_QWORD *)(v27 + 8) = v28;
    memcpy_0(v28, pszAlgId, *((unsigned int *)pbInput + 4));
  }
LABEL_28:
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (v9 | 0x10000000) & (unsigned int)-(v9 != 0);
}

```

## disassembly

```asm
0x18004fb48  mov     rax, rsp
0x18004fb4b  mov     [rax+20h], rbx
0x18004fb4f  mov     [rax+18h], r8
0x18004fb53  mov     [rax+10h], rdx
0x18004fb57  push    rbp
0x18004fb58  push    rsi
0x18004fb59  push    rdi
0x18004fb5a  push    r12
0x18004fb5c  push    r13
0x18004fb5e  push    r14
0x18004fb60  push    r15
0x18004fb62  lea     rbp, [rax-57h]
0x18004fb66  sub     rsp, 90h
0x18004fb6d  xor     edx, edx
0x18004fb6f  lea     r13, [rcx+20h]
0x18004fb73  test    dword ptr [r13+4], 0FFFFFFE0h
0x18004fb7b  mov     rsi, r9
0x18004fb7e  mov     rdi, rcx
0x18004fb81  mov     [rbp+4Fh+pbHash], rdx
0x18004fb85  mov     r12d, edx
0x18004fb88  mov     [rbp+4Fh+pPaddingInfo], rdx
0x18004fb8c  mov     r14d, edx
0x18004fb8f  mov     [rbp+4Fh+cbHash], edx
0x18004fb92  mov     byte ptr [rbp+4Fh+arg_0], dl
0x18004fb95  mov     [rbp+4Fh+phAlgorithm], rdx
0x18004fb99  jz      short loc_18004FBC3
0x18004fb9b  mov     ebx, 0C000090Bh
0x18004fba0  mov     r9d, 44Dh
0x18004fba6  mov     ecx, 0C000090Bh
0x18004fbab  lea     rdx, aStatus; "Status"
0x18004fbb2  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004fbb9  call    DebugTraceError
0x18004fbbe  jmp     loc_18004FEA6
0x18004fbc3  mov     ecx, [rcx+8]
0x18004fbc6  mov     eax, [rdi+0Ch]
0x18004fbc9  add     rcx, r13
0x18004fbcc  mov     r14d, [rdi+10h]
0x18004fbd0  mov     [rbp+4Fh+var_40], rcx
0x18004fbd4  add     rcx, rax
0x18004fbd7  mov     eax, [rdi+14h]
0x18004fbda  add     r14, rcx
0x18004fbdd  mov     [rbp+4Fh+pszAlgId], rcx
0x18004fbe1  mov     ecx, [rdi+18h]
0x18004fbe4  mov     [rbp+4Fh+var_6C], eax
0x18004fbe7  mov     [rbp+4Fh+var_68], ecx
0x18004fbea  test    eax, eax
0x18004fbec  jz      loc_18004FCA7
0x18004fbf2  lea     rdx, [rbp+4Fh+arg_0]
0x18004fbf6  mov     rcx, r8; hObject
0x18004fbf9  call    VBSAttestationIsRsaKey
0x18004fbfe  mov     ebx, eax
0x18004fc00  test    eax, eax
0x18004fc02  jns     short loc_18004FC27
0x18004fc04  mov     r9d, 459h
0x18004fc0a  mov     ecx, eax
0x18004fc0c  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004fc13  lea     rdx, aStatus; "Status"
0x18004fc1a  call    DebugTraceError
0x18004fc1f  mov     r14, r12
0x18004fc22  jmp     loc_18004FEA6
0x18004fc27  cmp     byte ptr [rbp+4Fh+arg_0], r12b
0x18004fc2b  jnz     short loc_18004FC3F
0x18004fc2d  mov     ebx, 0C000090Bh
0x18004fc32  mov     r9d, 45Fh
0x18004fc38  mov     ecx, 0C000090Bh
0x18004fc3d  jmp     short loc_18004FC0C
0x18004fc3f  mov     eax, [r14+4]
0x18004fc43  mov     [rbp+4Fh+arg_0], eax
0x18004fc46  cmp     eax, 8
0x18004fc49  jz      short loc_18004FC58
0x18004fc4b  mov     ebx, 0C00000E5h
0x18004fc50  mov     r8d, 5FCh
0x18004fc56  jmp     short loc_18004FC75
0x18004fc58  mov     ecx, 10h
0x18004fc5d  call    SafeAllocaAllocateFromHeap
0x18004fc62  mov     rcx, rax
0x18004fc65  test    rax, rax
0x18004fc68  jnz     short loc_18004FC90
0x18004fc6a  mov     ebx, 0C0000017h
0x18004fc6f  mov     r8d, 5EFh
0x18004fc75  lea     rdx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004fc7c  mov     ecx, ebx
0x18004fc7e  call    VBS_ATTEST_TRACE_ERROR_IN
0x18004fc83  mov     r9d, 46Ah
0x18004fc89  mov     ecx, ebx
0x18004fc8b  jmp     loc_18004FC0C
0x18004fc90  lea     rax, [r14+10h]
0x18004fc94  mov     [rbp+4Fh+pPaddingInfo], rcx
0x18004fc98  mov     [rcx], rax
0x18004fc9b  mov     r15, r14
0x18004fc9e  mov     eax, [r14+0Ch]
0x18004fca2  mov     [rcx+8], eax
0x18004fca5  jmp     short loc_18004FCAD
0x18004fca7  mov     [rbp+4Fh+arg_0], edx
0x18004fcaa  mov     r15, rdx
0x18004fcad  mov     r8d, [r13+8]
0x18004fcb1  lea     rdx, [r13+0Ch]; Source2
0x18004fcb5  mov     rcx, [rbp+4Fh+hBCryptKey]; hBCryptKey
0x18004fcb9  call    VBSAttestationComparePublicKeys
0x18004fcbe  mov     ebx, eax
0x18004fcc0  test    eax, eax
0x18004fcc2  jns     short loc_18004FCE4
0x18004fcc4  mov     r9d, 480h
0x18004fcca  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004fcd1  mov     ecx, eax
0x18004fcd3  lea     rdx, aStatus; "Status"
0x18004fcda  call    DebugTraceError
0x18004fcdf  jmp     loc_18004FEA2
0x18004fce4  mov     rdx, [rbp+4Fh+pszAlgId]; pszAlgId
0x18004fce8  lea     rcx, [rbp+4Fh+phAlgorithm]; phAlgorithm
0x18004fcec  xor     r9d, r9d; dwFlags
0x18004fcef  xor     r8d, r8d; pszImplementation
0x18004fcf2  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004fcf9  nop     dword ptr [rax+rax+00h]
0x18004fcfe  mov     ebx, eax
0x18004fd00  test    eax, eax
0x18004fd02  jns     short loc_18004FD0C
0x18004fd04  mov     r9d, 48Ch
0x18004fd0a  jmp     short loc_18004FCCA
0x18004fd0c  mov     eax, [rbp+4Fh+var_6C]
0x18004fd0f  lea     r8, [rbp+4Fh+cbHash]
0x18004fd13  mov     rcx, [rbp+4Fh+phAlgorithm]; hObject
0x18004fd17  lea     rdx, [rbp+4Fh+pbHash]
0x18004fd1b  add     r14, rax
0x18004fd1e  mov     [rsp+40h], rdi; pbInput
0x18004fd23  mov     rax, [rbp+4Fh+pszAlgId]
0x18004fd27  mov     r9, r13
0x18004fd2a  mov     [rsp+0C0h+var_88], r15; PUCHAR
0x18004fd2f  mov     qword ptr [rsp+0C0h+dwFlags], r14; PUCHAR
0x18004fd34  mov     qword ptr [rsp+0C0h+cbSignature], rax; PUCHAR
0x18004fd39  mov     rax, [rbp+4Fh+var_40]
0x18004fd3d  mov     [rsp+0C0h+pbSignature], rax; PUCHAR
0x18004fd42  call    VBSAttestationBuildIdentityClaimHashBuffer
0x18004fd47  mov     ebx, eax
0x18004fd49  test    eax, eax
0x18004fd4b  jns     short loc_18004FD71
0x18004fd4d  mov     r9d, 49Dh
0x18004fd53  lea     r8, aOnecoreDsSecur_32; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004fd5a  lea     rdx, aStatus; "Status"
0x18004fd61  mov     ecx, eax
0x18004fd63  call    DebugTraceError
0x18004fd68  mov     r12, [rbp+4Fh+pbHash]
0x18004fd6c  jmp     loc_18004FEA2
0x18004fd71  mov     eax, [rbp+4Fh+arg_0]
0x18004fd74  mov     ecx, [rbp+4Fh+var_68]
0x18004fd77  mov     r12, [rbp+4Fh+pbHash]
0x18004fd7b  add     rcx, r14
0x18004fd7e  mov     r14, [rbp+4Fh+pPaddingInfo]
0x18004fd82  mov     r8, r12; pbHash
0x18004fd85  mov     r9d, [rbp+4Fh+cbHash]; cbHash
0x18004fd89  mov     rdx, r14; pPaddingInfo
0x18004fd8c  mov     [rsp+0C0h+dwFlags], eax; dwFlags
0x18004fd90  mov     eax, [rdi+1Ch]
0x18004fd93  mov     [rsp+0C0h+cbSignature], eax; cbSignature
0x18004fd97  mov     [rsp+0C0h+pbSignature], rcx; pbSignature
0x18004fd9c  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004fda0  call    cs:__imp_BCryptVerifySignature
0x18004fda7  nop     dword ptr [rax+rax+00h]
0x18004fdac  mov     ebx, eax
0x18004fdae  test    eax, eax
0x18004fdb0  jns     short loc_18004FDBF
0x18004fdb2  mov     r9d, 4ACh
0x18004fdb8  mov     ecx, eax
0x18004fdba  jmp     loc_18004FBAB
0x18004fdbf  cmp     [rbp+4Fh+arg_20], 100000h
0x18004fdc6  jnz     loc_18004FEA6
0x18004fdcc  test    rsi, rsi
0x18004fdcf  jz      loc_18004FEA6
0x18004fdd5  mov     eax, [rdi+10h]
0x18004fdd8  lea     ecx, [rax+28h]
0x18004fddb  cmp     ecx, eax
0x18004fddd  jnb     short loc_18004FDF4
0x18004fddf  mov     r9d, 4B8h
0x18004fde5  mov     ebx, 0C0000095h
0x18004fdea  mov     ecx, 0C0000095h
0x18004fdef  jmp     loc_18004FBAB
0x18004fdf4  mov     eax, [rdi+14h]
0x18004fdf7  lea     edx, [rcx+rax]
0x18004fdfa  cmp     edx, eax
0x18004fdfc  jnb     short loc_18004FE06
0x18004fdfe  mov     r9d, 4BEh
0x18004fe04  jmp     short loc_18004FDE5
0x18004fe06  mov     ecx, edx
0x18004fe08  call    SafeAllocaAllocateFromHeap
0x18004fe0d  mov     [rsi+8], rax
0x18004fe11  test    rax, rax
0x18004fe14  jnz     short loc_18004FE2B
0x18004fe16  mov     ebx, 0C0000017h
0x18004fe1b  mov     r9d, 4C5h
0x18004fe21  mov     ecx, 0C0000017h
0x18004fe26  jmp     loc_18004FBAB
0x18004fe2b  xorps   xmm0, xmm0
0x18004fe2e  xor     ecx, ecx
0x18004fe30  movups  xmmword ptr [rax], xmm0
0x18004fe33  xor     ebx, ebx
0x18004fe35  movups  xmmword ptr [rax+10h], xmm0
0x18004fe39  mov     [rax+20h], rcx
0x18004fe3d  mov     r14, [rsi+8]
0x18004fe41  mov     dword ptr [rsi], 28h ; '('
0x18004fe47  mov     dword ptr [rsi+4], 5Fh ; '_'
0x18004fe4e  mov     eax, [r13+4]
0x18004fe52  mov     [r14], eax
0x18004fe55  test    r15, r15
0x18004fe58  jz      short loc_18004FE89
0x18004fe5a  mov     eax, [r15+4]
0x18004fe5e  lea     rdx, [r15+10h]; Src
0x18004fe62  mov     [r14+10h], eax
0x18004fe66  mov     eax, [r15+0Ch]
0x18004fe6a  mov     [r14+20h], eax
0x18004fe6e  mov     rax, [rsi+8]
0x18004fe72  mov     ecx, [rdi+10h]
0x18004fe75  add     rax, 28h ; '('
0x18004fe79  add     rcx, rax; void *
0x18004fe7c  mov     [r14+18h], rcx
0x18004fe80  mov     r8d, [r15+8]; Size
0x18004fe84  call    memcpy_0
0x18004fe89  mov     rcx, [rsi+8]
0x18004fe8d  mov     rdx, [rbp+4Fh+pszAlgId]; Src
0x18004fe91  add     rcx, 28h ; '('; void *
0x18004fe95  mov     [r14+8], rcx
0x18004fe99  mov     r8d, [rdi+10h]; Size
0x18004fe9d  call    memcpy_0
0x18004fea2  mov     r14, [rbp+4Fh+pPaddingInfo]
0x18004fea6  mov     rcx, [rbp+4Fh+phAlgorithm]; hAlgorithm
0x18004feaa  test    rcx, rcx
0x18004fead  jz      short loc_18004FEBD
0x18004feaf  xor     edx, edx; dwFlags
0x18004feb1  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18004feb8  nop     dword ptr [rax+rax+00h]
0x18004febd  test    r14, r14
0x18004fec0  jz      short loc_18004FECA
0x18004fec2  mov     rcx, r14
0x18004fec5  call    MSCryptFree
0x18004feca  test    r12, r12
0x18004fecd  jz      short loc_18004FED7
0x18004fecf  mov     rcx, r12
0x18004fed2  call    MSCryptFree
0x18004fed7  mov     ecx, ebx
0x18004fed9  bts     ecx, 1Ch
0x18004fedd  neg     ebx
0x18004fedf  mov     rbx, [rsp+0C0h+arg_18]
0x18004fee7  sbb     eax, eax
0x18004fee9  and     eax, ecx
0x18004feeb  add     rsp, 90h
0x18004fef2  pop     r15
0x18004fef4  pop     r14
0x18004fef6  pop     r13
0x18004fef8  pop     r12
0x18004fefa  pop     rdi
0x18004fefb  pop     rsi
0x18004fefc  pop     rbp
0x18004fefd  retn
```
