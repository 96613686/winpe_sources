# SPRecoverQueryStatus

- ea: `0x180038874`
- end: `0x1800389f2`
- name: `SPRecoverQueryStatus`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180039190`

## callees

- `0x180007f10`
- `0x180013f2c`
- `0x18001c340`
- `0x18001c9c0`
- `0x1800373ac`
- `0x180037ba8`
- `0x180038874`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800389d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800389d4`
- `CRYPT32!CertFreeCertificateContext` at `0x1800389bb`
- `CRYPT32!CertFreeCertificateContext` at `0x1800389bb`

## string_xrefs

- `0x180038907`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x18003894a`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c
__int64 __fastcall SPRecoverQueryStatus(__int64 a1, const WCHAR *a2, unsigned int *a3)
{
  struct _CERT_CONTEXT *v3; // rdi
  __int64 v6; // rcx
  unsigned int v7; // eax
  unsigned int v8; // ebx
  unsigned int RecoveryPublic; // eax
  unsigned int v10; // edi
  HLOCAL hMem; // [rsp+50h] [rbp+8h] BYREF
  struct _CERT_CONTEXT *v13; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  v13 = 0;
  hMem = 0;
  v6 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN *)v6 != &WPP_GLOBAL_Control && (*(_BYTE *)(v6 + 28) & 4) != 0 )
      WPP_SF_S(*(_QWORD *)(v6 + 16), 18, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids, a2);
  }
  v7 = MyLookupLocalAccountName(a2, &hMem);
  v8 = v7;
  if ( v7 )
  {
    DebugTraceError(v7, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", 820);
    goto LABEL_22;
  }
  RecoveryPublic = RecoverFindRecoveryPublic(0, hMem, (const struct _CERT_CONTEXT **)&v13, 0, 0);
  v10 = 2;
  v8 = RecoveryPublic;
  switch ( RecoveryPublic )
  {
    case 2u:
      DebugTraceError(2, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", 839);
LABEL_11:
      v8 = 0;
      goto LABEL_17;
    case 0x80092004:
      v10 = 1;
      goto LABEL_11;
    case 0xCu:
      v10 = 4;
      goto LABEL_11;
  }
  v10 = 0;
  if ( !RecoveryPublic )
  {
LABEL_17:
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids, v10);
    *a3 = v10;
  }
  v3 = v13;
LABEL_22:
  if ( v3 )
    CertFreeCertificateContext(v3);
  if ( hMem )
    LocalFree(hMem);
  return v8;
}

```

## disassembly

```asm
0x180038874  mov     rax, rsp
0x180038877  mov     [rax+10h], rbx
0x18003887b  mov     [rax+8], rcx
0x18003887f  push    rdi
0x180038880  push    r14
0x180038882  push    r15
0x180038884  sub     rsp, 30h
0x180038888  xor     edi, edi
0x18003888a  mov     r14, r8
0x18003888d  mov     [rax+20h], rdi
0x180038891  mov     rbx, rdx
0x180038894  mov     [rax+8], rdi
0x180038898  mov     rcx, cs:WPP_GLOBAL_Control
0x18003889f  lea     r15, WPP_GLOBAL_Control
0x1800388a6  cmp     rcx, r15
0x1800388a9  jz      short loc_1800388EE
0x1800388ab  test    byte ptr [rcx+1Ch], 4
0x1800388af  jz      short loc_1800388CB
0x1800388b1  mov     rcx, [rcx+10h]
0x1800388b5  lea     edx, [rdi+11h]
0x1800388b8  lea     r8, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids
0x1800388bf  call    WPP_SF_
0x1800388c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800388cb  cmp     rcx, r15
0x1800388ce  jz      short loc_1800388EE
0x1800388d0  test    byte ptr [rcx+1Ch], 4
0x1800388d4  jz      short loc_1800388EE
0x1800388d6  mov     rcx, [rcx+10h]
0x1800388da  lea     r8, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids
0x1800388e1  mov     edx, 12h
0x1800388e6  mov     r9, rbx
0x1800388e9  call    WPP_SF_S
0x1800388ee  lea     rdx, [rsp+48h+hMem]; void **
0x1800388f3  mov     rcx, rbx; SourceString
0x1800388f6  call    ?MyLookupLocalAccountName@@YAKPEBGPEAPEAX@Z; MyLookupLocalAccountName(ushort const *,void * *)
0x1800388fb  mov     ebx, eax
0x1800388fd  test    eax, eax
0x1800388ff  jz      short loc_180038921
0x180038901  mov     r9d, 334h
0x180038907  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18003890e  lea     rdx, aDwerror; "dwError"
0x180038915  mov     ecx, eax
0x180038917  call    DebugTraceError
0x18003891c  jmp     loc_1800389B3
0x180038921  mov     rdx, [rsp+48h+hMem]; void *
0x180038926  lea     r8, [rsp+48h+arg_18]; struct _CERT_CONTEXT **
0x18003892b  xor     r9d, r9d; unsigned __int8 *
0x18003892e  mov     [rsp+48h+var_28], edi; int
0x180038932  xor     ecx, ecx; void *
0x180038934  call    ?RecoverFindRecoveryPublic@@YAKPEAX0PEAPEBU_CERT_CONTEXT@@PEAEH@Z; RecoverFindRecoveryPublic(void *,void *,_CERT_CONTEXT const * *,uchar *,int)
0x180038939  mov     edi, 2
0x18003893e  mov     ebx, eax
0x180038940  cmp     eax, edi
0x180038942  jnz     short loc_180038963
0x180038944  mov     r9d, 347h
0x18003894a  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180038951  lea     rdx, aDwerror; "dwError"
0x180038958  mov     ecx, edi
0x18003895a  call    DebugTraceError
0x18003895f  xor     ebx, ebx
0x180038961  jmp     short loc_180038981
0x180038963  cmp     eax, 80092004h
0x180038968  jnz     short loc_180038971
0x18003896a  mov     edi, 1
0x18003896f  jmp     short loc_18003895F
0x180038971  cmp     eax, 0Ch
0x180038974  jnz     short loc_18003897B
0x180038976  lea     edi, [rax-8]
0x180038979  jmp     short loc_18003895F
0x18003897b  xor     edi, edi
0x18003897d  test    eax, eax
0x18003897f  jnz     short loc_1800389AE
0x180038981  mov     rcx, cs:WPP_GLOBAL_Control
0x180038988  cmp     rcx, r15
0x18003898b  jz      short loc_1800389AB
0x18003898d  test    byte ptr [rcx+1Ch], 4
0x180038991  jz      short loc_1800389AB
0x180038993  mov     rcx, [rcx+10h]
0x180038997  lea     r8, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids
0x18003899e  mov     edx, 13h
0x1800389a3  mov     r9d, edi
0x1800389a6  call    WPP_SF_d
0x1800389ab  mov     [r14], edi
0x1800389ae  mov     rdi, [rsp+48h+arg_18]
0x1800389b3  test    rdi, rdi
0x1800389b6  jz      short loc_1800389C7
0x1800389b8  mov     rcx, rdi; pCertContext
0x1800389bb  call    cs:__imp_CertFreeCertificateContext
0x1800389c2  nop     dword ptr [rax+rax+00h]
0x1800389c7  cmp     [rsp+48h+hMem], 0
0x1800389cd  jz      short loc_1800389E0
0x1800389cf  mov     rcx, [rsp+48h+hMem]; hMem
0x1800389d4  call    cs:__imp_LocalFree
0x1800389db  nop     dword ptr [rax+rax+00h]
0x1800389e0  mov     eax, ebx
0x1800389e2  mov     rbx, [rsp+48h+arg_8]
0x1800389e7  add     rsp, 30h
0x1800389eb  pop     r15
0x1800389ed  pop     r14
0x1800389ef  pop     rdi
0x1800389f0  retn
```
