# FMyPrimitiveSHA

- ea: `0x18000c4a0`
- end: `0x18000c796`
- name: `FMyPrimitiveSHA`
- size: `758`
- prototype: `__int64 __usercall@<rax>(PUCHAR pbInput@<rcx>, ULONG cbInput@<edx>, PUCHAR)`
- caller_count: `14`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c1b4`
- `0x180012838`
- `0x180014c80`
- `0x180016370`
- `0x180019f40`
- `0x180024f38`
- `0x1800290c8`
- `0x18002a794`
- `0x18002ca70`
- `0x18002d330`
- `0x18003048c`
- `0x18003325c`
- `0x180033b04`
- `0x180036dc0`

## callees

- `0x18000c4a0`
- `0x18000c7a0`
- `0x18003e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c548`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c6fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c785`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c548`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c6fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c785`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c513`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c76c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c513`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c76c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c6e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c714`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c739`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c75a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c6e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c714`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c739`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c75a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c693`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c693`
- `bcrypt!BCryptFinishHash` at `0x18000c600`
- `bcrypt!BCryptFinishHash` at `0x18000c600`
- `bcrypt!BCryptDestroyHash` at `0x18000c61e`
- `bcrypt!BCryptDestroyHash` at `0x18000c61e`
- `bcrypt!BCryptHashData` at `0x18000c5a9`
- `bcrypt!BCryptHashData` at `0x18000c5a9`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000c65b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18000c65b`
- `bcrypt!BCryptCreateHash` at `0x18000c58c`
- `bcrypt!BCryptCreateHash` at `0x18000c58c`
- `bcrypt!BCryptGetProperty` at `0x18000c5db`
- `bcrypt!BCryptGetProperty` at `0x18000c5db`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c728`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c749`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c728`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18000c749`

## pseudocode

```c
_BOOL8 __fastcall FMyPrimitiveSHA(PUCHAR pbInput, ULONG cbInput, __int64 a3, __int64 a4, PUCHAR a5)
{
  char *v5; // rdi
  _QWORD *i; // rbx
  BCRYPT_ALG_HANDLE v9; // rbx
  BOOL v10; // edi
  NTSTATUS v12; // eax
  _QWORD *v13; // rax
  BCRYPT_ALG_HANDLE v14; // rcx
  _QWORD *v15; // rdi
  char *v16; // rsi
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+40h] [rbp-30h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-28h] BYREF
  __int64 v19; // [rsp+50h] [rbp-20h] BYREF
  int v20; // [rsp+58h] [rbp-18h]
  int v21; // [rsp+5Ch] [rbp-14h]
  __int64 v22; // [rsp+60h] [rbp-10h]
  int v23; // [rsp+68h] [rbp-8h]
  int v24; // [rsp+6Ch] [rbp-4h]
  __int64 pcbResult; // [rsp+B0h] [rbp+40h] BYREF
  ULONG pbOutput; // [rsp+B8h] [rbp+48h] BYREF

  pcbResult = a3;
  v5 = (char *)g_pBCProvList;
  v24 = 0;
  phAlgorithm = 0;
  pbOutput = -1;
  if ( !g_pBCProvList )
  {
    SetLastError(0x800C0001);
    return 0;
  }
  v19 = 0;
  v20 = 32772;
  v21 = -1;
  v22 = 0;
  v23 = 0;
  if ( *((_DWORD *)g_pBCProvList + 2) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)g_pBCProvList + 16));
    for ( i = *(_QWORD **)v5; i; i = (_QWORD *)*i )
    {
      if ( (*((unsigned int (__fastcall **)(_QWORD *, __int64 *))v5 + 7))(i, &v19) )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
        v9 = (BCRYPT_ALG_HANDLE)i[2];
        goto LABEL_8;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 16));
  }
  v12 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", L"Microsoft Primitive Provider", 0);
  if ( v12 < 0 )
  {
    SetLastError(v12 | 0x10000000);
    return 0;
  }
  if ( !(unsigned int)FBCryptProviderSupportsAlg(phAlgorithm) )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    SetLastError(0x32u);
    return 0;
  }
  v13 = LocalAlloc(0x40u, 0x20u);
  v14 = phAlgorithm;
  v15 = v13;
  if ( !v13 )
  {
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
    SetLastError(8u);
    return 0;
  }
  v16 = (char *)g_pBCProvList;
  *v13 = 0;
  *((_DWORD *)v13 + 2) = 32772;
  *((_DWORD *)v13 + 3) = pbOutput;
  v13[2] = v14;
  *((_DWORD *)v13 + 6) = 0;
  if ( *((_DWORD *)v16 + 2) )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v16 + 16));
    *v15 = *(_QWORD *)v16;
    *(_QWORD *)v16 = v15;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v16 + 16));
  }
  v9 = phAlgorithm;
LABEL_8:
  if ( !v9 )
    return 0;
  pbOutput = 0;
  v10 = 0;
  LODWORD(pcbResult) = 0;
  phHash = 0;
  if ( BCryptCreateHash(v9, &phHash, 0, 0, 0, 0, 0) >= 0
    && BCryptHashData(phHash, pbInput, cbInput, 0) >= 0
    && BCryptGetProperty(v9, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, (ULONG *)&pcbResult, 0) >= 0
    && pbOutput <= 0x14 )
  {
    v10 = BCryptFinishHash(phHash, a5, pbOutput, 0) >= 0;
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  return v10;
}

```

## disassembly

```asm
0x18000c4a0  mov     [rsp-28h+arg_0], rbx
0x18000c4a5  mov     [rsp-28h+arg_8], rsi
0x18000c4aa  mov     [rsp-28h+pbOutput], r9d
0x18000c4af  mov     [rsp-28h+pcbResult], r8
0x18000c4b4  push    rbp
0x18000c4b5  push    rdi
0x18000c4b6  push    r12
0x18000c4b8  push    r14
0x18000c4ba  push    r15
0x18000c4bc  mov     rbp, rsp
0x18000c4bf  sub     rsp, 70h
0x18000c4c3  mov     rdi, cs:?g_pBCProvList@@3PEAVCBCryptProvList@@EA; CBCryptProvList * g_pBCProvList
0x18000c4ca  xor     r12d, r12d
0x18000c4cd  mov     [rbp+var_4], r12d
0x18000c4d1  mov     r14d, edx
0x18000c4d4  mov     [rbp+phAlgorithm], r12
0x18000c4d8  mov     r15, rcx
0x18000c4db  mov     [rbp+pbOutput], 0FFFFFFFFh
0x18000c4e2  test    rdi, rdi
0x18000c4e5  jz      loc_18000C6E1
0x18000c4eb  mov     [rbp+var_20], r12
0x18000c4ef  mov     [rbp+var_18], 8004h
0x18000c4f6  mov     [rbp+var_14], 0FFFFFFFFh
0x18000c4fd  mov     [rbp+var_10], r12
0x18000c501  mov     [rbp+var_8], r12d
0x18000c505  cmp     [rdi+8], r12d
0x18000c509  jz      loc_18000C646
0x18000c50f  lea     rcx, [rdi+10h]; lpCriticalSection
0x18000c513  call    cs:__imp_EnterCriticalSection
0x18000c51a  nop     dword ptr [rax+rax+00h]
0x18000c51f  mov     rbx, [rdi]
0x18000c522  test    rbx, rbx
0x18000c525  jz      loc_18000C6F9
0x18000c52b  mov     rax, [rdi+38h]
0x18000c52f  lea     rdx, [rbp+var_20]
0x18000c533  mov     rcx, rbx
0x18000c536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c53b  test    eax, eax
0x18000c53d  jnz     short loc_18000C544
0x18000c53f  mov     rbx, [rbx]
0x18000c542  jmp     short loc_18000C522
0x18000c544  lea     rcx, [rdi+10h]; lpCriticalSection
0x18000c548  call    cs:__imp_LeaveCriticalSection
0x18000c54f  nop     dword ptr [rax+rax+00h]
0x18000c554  mov     rbx, [rbx+10h]
0x18000c558  test    rbx, rbx
0x18000c55b  jz      loc_18000C6F2
0x18000c561  mov     [rsp+70h+dwFlags], r12d; dwFlags
0x18000c566  lea     rdx, [rbp+phHash]; phHash
0x18000c56a  mov     [rsp+70h+cbSecret], r12d; cbSecret
0x18000c56f  xor     r9d, r9d; cbHashObject
0x18000c572  xor     r8d, r8d; pbHashObject
0x18000c575  mov     [rsp+70h+pbSecret], r12; pbSecret
0x18000c57a  mov     rcx, rbx; hAlgorithm
0x18000c57d  mov     [rbp+pbOutput], r12d
0x18000c581  mov     edi, r12d
0x18000c584  mov     dword ptr [rbp+pcbResult], r12d
0x18000c588  mov     [rbp+phHash], r12
0x18000c58c  call    cs:__imp_BCryptCreateHash
0x18000c593  nop     dword ptr [rax+rax+00h]
0x18000c598  test    eax, eax
0x18000c59a  js      short loc_18000C615
0x18000c59c  mov     rcx, [rbp+phHash]; hHash
0x18000c5a0  xor     r9d, r9d; dwFlags
0x18000c5a3  mov     r8d, r14d; cbInput
0x18000c5a6  mov     rdx, r15; pbInput
0x18000c5a9  call    cs:__imp_BCryptHashData
0x18000c5b0  nop     dword ptr [rax+rax+00h]
0x18000c5b5  test    eax, eax
0x18000c5b7  js      short loc_18000C615
0x18000c5b9  lea     rax, [rbp+pcbResult]
0x18000c5bd  mov     [rsp+70h+cbSecret], r12d; dwFlags
0x18000c5c2  mov     r9d, 4; cbOutput
0x18000c5c8  mov     [rsp+70h+pbSecret], rax; pcbResult
0x18000c5cd  lea     r8, [rbp+pbOutput]; pbOutput
0x18000c5d1  mov     rcx, rbx; hObject
0x18000c5d4  lea     rdx, aHashdigestleng; "HashDigestLength"
0x18000c5db  call    cs:__imp_BCryptGetProperty
0x18000c5e2  nop     dword ptr [rax+rax+00h]
0x18000c5e7  test    eax, eax
0x18000c5e9  js      short loc_18000C615
0x18000c5eb  mov     r8d, [rbp+pbOutput]; cbOutput
0x18000c5ef  cmp     r8d, 14h
0x18000c5f3  ja      short loc_18000C615
0x18000c5f5  mov     rdx, [rbp+arg_20]; pbOutput
0x18000c5f9  xor     r9d, r9d; dwFlags
0x18000c5fc  mov     rcx, [rbp+phHash]; hHash
0x18000c600  call    cs:__imp_BCryptFinishHash
0x18000c607  nop     dword ptr [rax+rax+00h]
0x18000c60c  test    eax, eax
0x18000c60e  js      short loc_18000C615
0x18000c610  mov     edi, 1
0x18000c615  mov     rcx, [rbp+phHash]; hHash
0x18000c619  test    rcx, rcx
0x18000c61c  jz      short loc_18000C62A
0x18000c61e  call    cs:__imp_BCryptDestroyHash
0x18000c625  nop     dword ptr [rax+rax+00h]
0x18000c62a  mov     eax, edi
0x18000c62c  lea     r11, [rsp+70h+var_s0]
0x18000c631  mov     rbx, [r11+30h]
0x18000c635  mov     rsi, [r11+38h]
0x18000c639  mov     rsp, r11
0x18000c63c  pop     r15
0x18000c63e  pop     r14
0x18000c640  pop     r12
0x18000c642  pop     rdi
0x18000c643  pop     rbp
0x18000c644  retn
0x18000c646  xor     r9d, r9d; dwFlags
0x18000c649  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18000c650  lea     rdx, pszAlgId; "SHA1"
0x18000c657  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18000c65b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000c662  nop     dword ptr [rax+rax+00h]
0x18000c667  test    eax, eax
0x18000c669  js      loc_18000C70E
0x18000c66f  mov     rcx, [rbp+phAlgorithm]; hObject
0x18000c673  lea     r8, [rbp+pbOutput]
0x18000c677  mov     edx, 8004h
0x18000c67c  call    FBCryptProviderSupportsAlg
0x18000c681  test    eax, eax
0x18000c683  jz      loc_18000C722
0x18000c689  mov     edx, 20h ; ' '; uBytes
0x18000c68e  mov     ecx, 40h ; '@'; uFlags
0x18000c693  call    cs:__imp_LocalAlloc
0x18000c69a  nop     dword ptr [rax+rax+00h]
0x18000c69f  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18000c6a3  mov     rdi, rax
0x18000c6a6  test    rax, rax
0x18000c6a9  jz      loc_18000C747
0x18000c6af  mov     rsi, cs:?g_pBCProvList@@3PEAVCBCryptProvList@@EA; CBCryptProvList * g_pBCProvList
0x18000c6b6  mov     [rax], r12
0x18000c6b9  mov     dword ptr [rax+8], 8004h
0x18000c6c0  mov     eax, [rbp+pbOutput]
0x18000c6c3  mov     [rdi+0Ch], eax
0x18000c6c6  mov     [rdi+10h], rcx
0x18000c6ca  mov     [rdi+18h], r12d
0x18000c6ce  cmp     [rsi+8], r12d
0x18000c6d2  jnz     loc_18000C768
0x18000c6d8  mov     rbx, [rbp+phAlgorithm]
0x18000c6dc  jmp     loc_18000C558
0x18000c6e1  mov     ecx, 800C0001h; dwErrCode
0x18000c6e6  call    cs:__imp_SetLastError
0x18000c6ed  nop     dword ptr [rax+rax+00h]
0x18000c6f2  xor     eax, eax
0x18000c6f4  jmp     loc_18000C62C
0x18000c6f9  lea     rcx, [rdi+10h]; lpCriticalSection
0x18000c6fd  call    cs:__imp_LeaveCriticalSection
0x18000c704  nop     dword ptr [rax+rax+00h]
0x18000c709  jmp     loc_18000C646
0x18000c70e  bts     eax, 1Ch
0x18000c712  mov     ecx, eax; dwErrCode
0x18000c714  call    cs:__imp_SetLastError
0x18000c71b  nop     dword ptr [rax+rax+00h]
0x18000c720  jmp     short loc_18000C6F2
0x18000c722  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18000c726  xor     edx, edx; dwFlags
0x18000c728  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000c72f  nop     dword ptr [rax+rax+00h]
0x18000c734  mov     ecx, 32h ; '2'; dwErrCode
0x18000c739  call    cs:__imp_SetLastError
0x18000c740  nop     dword ptr [rax+rax+00h]
0x18000c745  jmp     short loc_18000C6F2
0x18000c747  xor     edx, edx; dwFlags
0x18000c749  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18000c750  nop     dword ptr [rax+rax+00h]
0x18000c755  mov     ecx, 8; dwErrCode
0x18000c75a  call    cs:__imp_SetLastError
0x18000c761  nop     dword ptr [rax+rax+00h]
0x18000c766  jmp     short loc_18000C6F2
0x18000c768  lea     rcx, [rsi+10h]; lpCriticalSection
0x18000c76c  call    cs:__imp_EnterCriticalSection
0x18000c773  nop     dword ptr [rax+rax+00h]
0x18000c778  mov     rax, [rsi]
0x18000c77b  lea     rcx, [rsi+10h]; lpCriticalSection
0x18000c77f  mov     [rdi], rax
0x18000c782  mov     [rsi], rdi
0x18000c785  call    cs:__imp_LeaveCriticalSection
0x18000c78c  nop     dword ptr [rax+rax+00h]
0x18000c791  jmp     loc_18000C6D8
```
