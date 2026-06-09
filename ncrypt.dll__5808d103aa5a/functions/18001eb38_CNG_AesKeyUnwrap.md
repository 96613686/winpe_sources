# CNG_AesKeyUnwrap

- ea: `0x18001eb38`
- end: `0x18001ee17`
- name: `CNG_AesKeyUnwrap`
- size: `735`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180016e90`

## callees

- `0x180005fa0`
- `0x18000e120`
- `0x180015c4c`
- `0x18001eb38`
- `0x18001f145`
- `0x18001f15d`
- `0x18001f1b0`
- `0x180020010`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x18001edaf`
- `bcrypt!BCryptDestroyKey` at `0x18001edbe`
- `bcrypt!BCryptDestroyKey` at `0x18001edaf`
- `bcrypt!BCryptDestroyKey` at `0x18001edbe`
- `bcrypt!BCryptImportKey` at `0x18001ec1c`
- `bcrypt!BCryptImportKey` at `0x18001ec1c`
- `bcrypt!BCryptExportKey` at `0x18001ec56`
- `bcrypt!BCryptExportKey` at `0x18001ed4c`
- `bcrypt!BCryptExportKey` at `0x18001ec56`
- `bcrypt!BCryptExportKey` at `0x18001ed4c`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001ebdd`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18001ebdd`

## string_xrefs

- `0x18001eb9d`: `onecore\ds\security\cryptoapi\ncrypt\protect\common\keywrap.c`
- `0x18001ed08`: `onecore\ds\security\cryptoapi\ncrypt\protect\common\keywrap.c`

## pseudocode

```c
__int64 __fastcall CNG_AesKeyUnwrap(__int64 a1, UCHAR *a2, ULONG a3, UCHAR *a4, ULONG cbSecret, _QWORD *a6, _DWORD *a7)
{
  UCHAR *p_pcbResult; // rdi
  NTSTATUS BCryptHandle; // ebx
  __int64 v13; // r9
  unsigned int v14; // ebx
  unsigned __int64 v15; // rbx
  __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  UCHAR *v20; // rax
  __int64 v21; // r9
  size_t v22; // rsi
  void *v23; // rax
  void *v24; // r14
  __int64 v25; // rax
  UCHAR *v26; // rcx
  __int64 v28; // [rsp+0h] [rbp-50h] BYREF
  ULONG pcbResult; // [rsp+50h] [rbp+0h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+58h] [rbp+8h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+60h] [rbp+10h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+68h] [rbp+18h] BYREF

  hAlgorithm = 0;
  phKey = 0;
  hKey = 0;
  p_pcbResult = 0;
  pcbResult = 0;
  BCryptHandle = CNG_GetBCryptHandle(L"AES", &hAlgorithm);
  if ( BCryptHandle < 0 )
  {
    v13 = 210;
LABEL_3:
    DebugTraceError(
      (unsigned int)BCryptHandle,
      "status",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\common\\keywrap.c",
      v13);
    v14 = BCryptHandle | 0x10000000;
    goto LABEL_29;
  }
  BCryptHandle = BCryptGenerateSymmetricKey(hAlgorithm, &phKey, 0, 0, a4, cbSecret, 0);
  if ( BCryptHandle < 0 )
  {
    v13 = 225;
    goto LABEL_3;
  }
  BCryptHandle = BCryptImportKey(hAlgorithm, phKey, L"Rfc3565KeyWrapBlob", &hKey, 0, 0, a2, a3, 0);
  if ( BCryptHandle < 0 )
  {
    v13 = 245;
    goto LABEL_3;
  }
  BCryptHandle = BCryptExportKey(hKey, 0, L"KeyDataBlob", 0, 0, &pcbResult, 0);
  if ( BCryptHandle < 0 )
  {
    v13 = 261;
    goto LABEL_3;
  }
  v15 = pcbResult;
  if ( !pcbResult
    || pcbResult > (unsigned __int64)g_ulMaxStackAllocSize
    || (unsigned __int64)pcbResult + g_ulAdditionalProbeSize + 8 < pcbResult
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_41;
  }
  v16 = v15 + 23;
  if ( v15 + 23 <= v15 + 8 )
    v16 = 0xFFFFFFFFFFFFFF0LL;
  v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
  v18 = alloca(v17);
  v19 = alloca(v17);
  p_pcbResult = (UCHAR *)&pcbResult;
  if ( &v28 == (__int64 *)-80LL || (pcbResult = 1801679955, (p_pcbResult = (UCHAR *)&hKey) == 0) )
  {
LABEL_41:
    if ( v15 + 8 >= v15 )
    {
      v20 = (UCHAR *)((__int64 (*)(void))g_pfnAllocate)();
      p_pcbResult = v20;
      if ( v20 )
      {
        *(_DWORD *)v20 = 1885431112;
        p_pcbResult = v20 + 8;
      }
    }
  }
  if ( !p_pcbResult )
  {
    v21 = 270;
LABEL_23:
    v14 = -2146893810;
    DebugTraceError(2148073486LL, "hr", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\common\\keywrap.c", v21);
    goto LABEL_29;
  }
  BCryptHandle = BCryptExportKey(hKey, 0, L"KeyDataBlob", p_pcbResult, pcbResult, &pcbResult, 0);
  if ( BCryptHandle < 0 )
  {
    v13 = 284;
    goto LABEL_3;
  }
  v22 = *((unsigned int *)p_pcbResult + 2);
  v23 = (void *)(*(__int64 (__fastcall **)(size_t))(a1 + 8))(v22);
  v24 = v23;
  if ( !v23 )
  {
    v21 = 295;
    goto LABEL_23;
  }
  v14 = 0;
  memcpy_0(v23, p_pcbResult + 12, v22);
  *a6 = v24;
  *a7 = v22;
LABEL_29:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( p_pcbResult )
  {
    v25 = pcbResult;
    v26 = p_pcbResult;
    if ( pcbResult )
    {
      do
      {
        *v26++ = 0;
        --v25;
      }
      while ( v25 );
    }
    if ( *((_DWORD *)p_pcbResult - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  return v14;
}

```

## disassembly

```asm
0x18001eb38  push    rbp
0x18001eb3a  push    rbx
0x18001eb3b  push    rsi
0x18001eb3c  push    rdi
0x18001eb3d  push    r12
0x18001eb3f  push    r13
0x18001eb41  push    r14
0x18001eb43  push    r15
0x18001eb45  sub     rsp, 88h
0x18001eb4c  lea     rbp, [rsp+50h]
0x18001eb51  mov     rax, cs:__security_cookie
0x18001eb58  xor     rax, rbp
0x18001eb5b  mov     [rbp+70h+var_50], rax
0x18001eb5f  xor     r12d, r12d
0x18001eb62  mov     r14, rdx
0x18001eb65  mov     r13, rcx
0x18001eb68  mov     [rbp+70h+hAlgorithm], r12
0x18001eb6c  lea     rdx, [rbp+70h+hAlgorithm]
0x18001eb70  mov     [rbp+70h+phKey], r12
0x18001eb74  lea     rcx, aAes; "AES"
0x18001eb7b  mov     [rbp+70h+hKey], r12
0x18001eb7f  mov     edi, r12d
0x18001eb82  mov     [rbp+70h+pcbResult], r12d
0x18001eb86  mov     r15, r9
0x18001eb89  mov     esi, r8d
0x18001eb8c  call    CNG_GetBCryptHandle
0x18001eb91  mov     ebx, eax
0x18001eb93  test    eax, eax
0x18001eb95  jns     short loc_18001EBBB
0x18001eb97  mov     r9d, 0D2h
0x18001eb9d  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001eba4  mov     ecx, ebx
0x18001eba6  lea     rdx, aStatus_0; "status"
0x18001ebad  call    DebugTraceError
0x18001ebb2  bts     ebx, 1Ch
0x18001ebb6  jmp     loc_18001EDA6
0x18001ebbb  mov     eax, [rbp+70h+arg_20]
0x18001ebc1  lea     rdx, [rbp+70h+phKey]; phKey
0x18001ebc5  mov     rcx, [rbp+70h+hAlgorithm]; hAlgorithm
0x18001ebc9  xor     r9d, r9d; cbKeyObject
0x18001ebcc  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x18001ebd1  xor     r8d, r8d; pbKeyObject
0x18001ebd4  mov     [rsp+0C0h+cbSecret], eax; cbSecret
0x18001ebd8  mov     [rsp+0C0h+pbSecret], r15; pbSecret
0x18001ebdd  call    cs:__imp_BCryptGenerateSymmetricKey
0x18001ebe3  mov     ebx, eax
0x18001ebe5  test    eax, eax
0x18001ebe7  jns     short loc_18001EBF1
0x18001ebe9  mov     r9d, 0E1h
0x18001ebef  jmp     short loc_18001EB9D
0x18001ebf1  mov     rdx, [rbp+70h+phKey]; hImportKey
0x18001ebf5  lea     r9, [rbp+70h+hKey]; phKey
0x18001ebf9  mov     rcx, [rbp+70h+hAlgorithm]; hAlgorithm
0x18001ebfd  lea     r8, aRfc3565keywrap; "Rfc3565KeyWrapBlob"
0x18001ec04  mov     [rsp+0C0h+var_80], r12d; dwFlags
0x18001ec09  mov     [rsp+0C0h+cbInput], esi; cbInput
0x18001ec0d  mov     qword ptr [rsp+0C0h+dwFlags], r14; pbInput
0x18001ec12  mov     [rsp+0C0h+cbSecret], r12d; cbKeyObject
0x18001ec17  mov     [rsp+0C0h+pbSecret], r12; pbKeyObject
0x18001ec1c  call    cs:__imp_BCryptImportKey
0x18001ec22  mov     ebx, eax
0x18001ec24  test    eax, eax
0x18001ec26  jns     short loc_18001EC33
0x18001ec28  mov     r9d, 0F5h
0x18001ec2e  jmp     loc_18001EB9D
0x18001ec33  mov     rcx, [rbp+70h+hKey]; hKey
0x18001ec37  lea     rax, [rbp+70h+pcbResult]
0x18001ec3b  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x18001ec40  lea     r8, aKeydatablob; "KeyDataBlob"
0x18001ec47  mov     qword ptr [rsp+0C0h+cbSecret], rax; pcbResult
0x18001ec4c  xor     r9d, r9d; pbOutput
0x18001ec4f  xor     edx, edx; hExportKey
0x18001ec51  mov     dword ptr [rsp+0C0h+pbSecret], r12d; cbOutput
0x18001ec56  call    cs:__imp_BCryptExportKey
0x18001ec5c  mov     ebx, eax
0x18001ec5e  test    eax, eax
0x18001ec60  jns     short loc_18001EC6D
0x18001ec62  mov     r9d, 105h
0x18001ec68  jmp     loc_18001EB9D
0x18001ec6d  mov     ebx, [rbp+70h+pcbResult]
0x18001ec70  test    rbx, rbx
0x18001ec73  jz      short loc_18001ECD6
0x18001ec75  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18001ec7c  ja      short loc_18001ECD6
0x18001ec7e  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001ec85  add     rcx, 8
0x18001ec89  add     rcx, rbx
0x18001ec8c  cmp     rcx, rbx
0x18001ec8f  jb      short loc_18001ECD6
0x18001ec91  call    VerifyStackAvailable
0x18001ec96  test    eax, eax
0x18001ec98  jz      short loc_18001ECD6
0x18001ec9a  lea     rax, [rbx+8]
0x18001ec9e  lea     rcx, [rax+0Fh]
0x18001eca2  cmp     rcx, rax
0x18001eca5  ja      short loc_18001ECB1
0x18001eca7  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001ecb1  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001ecb5  mov     rax, rcx
0x18001ecb8  call    __chkstk_0
0x18001ecbd  sub     rsp, rcx
0x18001ecc0  lea     rdi, [rsp+0C0h+pcbResult]
0x18001ecc5  test    rdi, rdi
0x18001ecc8  jz      short loc_18001ECD6
0x18001ecca  mov     dword ptr [rdi], 6B637453h
0x18001ecd0  add     rdi, 8
0x18001ecd4  jnz     short loc_18001ECFD
0x18001ecd6  lea     rcx, [rbx+8]
0x18001ecda  cmp     rcx, rbx
0x18001ecdd  jb      short loc_18001ECFD
0x18001ecdf  mov     rax, cs:g_pfnAllocate
0x18001ece6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eceb  mov     rdi, rax
0x18001ecee  test    rax, rax
0x18001ecf1  jz      short loc_18001ECFD
0x18001ecf3  mov     dword ptr [rax], 70616548h
0x18001ecf9  add     rdi, 8
0x18001ecfd  test    rdi, rdi
0x18001ed00  jnz     short loc_18001ED27
0x18001ed02  mov     r9d, 10Eh
0x18001ed08  lea     r8, aOnecoreDsSecur_3; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ed0f  mov     ecx, 8009000Eh
0x18001ed14  lea     rdx, aHr; "hr"
0x18001ed1b  mov     ebx, 8009000Eh
0x18001ed20  call    DebugTraceError
0x18001ed25  jmp     short loc_18001EDA6
0x18001ed27  mov     rcx, [rbp+70h+hKey]; hKey
0x18001ed2b  lea     rax, [rbp+70h+pcbResult]
0x18001ed2f  mov     [rsp+0C0h+dwFlags], r12d; dwFlags
0x18001ed34  lea     r8, aKeydatablob; "KeyDataBlob"
0x18001ed3b  mov     qword ptr [rsp+0C0h+cbSecret], rax; pcbResult
0x18001ed40  mov     r9, rdi; pbOutput
0x18001ed43  mov     eax, [rbp+70h+pcbResult]
0x18001ed46  xor     edx, edx; hExportKey
0x18001ed48  mov     dword ptr [rsp+0C0h+pbSecret], eax; cbOutput
0x18001ed4c  call    cs:__imp_BCryptExportKey
0x18001ed52  mov     ebx, eax
0x18001ed54  test    eax, eax
0x18001ed56  jns     short loc_18001ED63
0x18001ed58  mov     r9d, 11Ch
0x18001ed5e  jmp     loc_18001EB9D
0x18001ed63  mov     esi, [rdi+8]
0x18001ed66  mov     rax, [r13+8]
0x18001ed6a  mov     ecx, esi
0x18001ed6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed71  mov     r14, rax
0x18001ed74  test    rax, rax
0x18001ed77  jnz     short loc_18001ED81
0x18001ed79  mov     r9d, 127h
0x18001ed7f  jmp     short loc_18001ED08
0x18001ed81  lea     rdx, [rdi+0Ch]; Src
0x18001ed85  mov     r8, rsi; Size
0x18001ed88  mov     rcx, r14; void *
0x18001ed8b  mov     ebx, r12d
0x18001ed8e  call    memcpy_0
0x18001ed93  mov     rax, [rbp+70h+arg_28]
0x18001ed9a  mov     [rax], r14
0x18001ed9d  mov     rax, [rbp+70h+arg_30]
0x18001eda4  mov     [rax], esi
0x18001eda6  mov     rcx, [rbp+70h+phKey]; hKey
0x18001edaa  test    rcx, rcx
0x18001edad  jz      short loc_18001EDB5
0x18001edaf  call    cs:__imp_BCryptDestroyKey
0x18001edb5  mov     rcx, [rbp+70h+hKey]; hKey
0x18001edb9  test    rcx, rcx
0x18001edbc  jz      short loc_18001EDC4
0x18001edbe  call    cs:__imp_BCryptDestroyKey
0x18001edc4  test    rdi, rdi
0x18001edc7  jz      short loc_18001EDF8
0x18001edc9  mov     eax, [rbp+70h+pcbResult]
0x18001edcc  mov     rcx, rdi
0x18001edcf  test    rax, rax
0x18001edd2  jz      short loc_18001EDE0
0x18001edd4  mov     [rcx], r12b
0x18001edd7  inc     rcx
0x18001edda  sub     rax, 1
0x18001edde  jnz     short loc_18001EDD4
0x18001ede0  lea     rcx, [rdi-8]
0x18001ede4  cmp     dword ptr [rcx], 70616548h
0x18001edea  jnz     short loc_18001EDF8
0x18001edec  mov     rax, cs:g_pfnFree
0x18001edf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edf8  mov     eax, ebx
0x18001edfa  mov     rcx, [rbp+70h+var_50]
0x18001edfe  xor     rcx, rbp; StackCookie
0x18001ee01  call    __security_check_cookie
0x18001ee06  lea     rsp, [rbp+38h]
0x18001ee0a  pop     r15
0x18001ee0c  pop     r14
0x18001ee0e  pop     r13
0x18001ee10  pop     r12
0x18001ee12  pop     rdi
0x18001ee13  pop     rsi
0x18001ee14  pop     rbx
0x18001ee15  pop     rbp
0x18001ee16  retn
```
