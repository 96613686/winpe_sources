# IkeValidateChainAgainstIkePolicy

- ea: `0x180004310`
- end: `0x180004500`
- name: `IkeValidateChainAgainstIkePolicy`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800302f8`

## callees

- `0x180004034`
- `0x18000413c`
- `0x180004310`
- `0x1800061ec`
- `0x18004aa3c`
- `0x18004ca68`
- `0x18008b274`

## import_xrefs

- `CRYPT32!CertFreeCertificateChain` at `0x1800044d4`
- `CRYPT32!CertFreeCertificateChain` at `0x1800044d4`
- `CRYPT32!CertDuplicateCertificateChain` at `0x1800044cb`
- `CRYPT32!CertDuplicateCertificateChain` at `0x1800044cb`

## string_xrefs

- `0x180004365`: `IkeCompareChainWithTrustCAAndCRP`
- `0x1800043bc`: `IkeCompareChainWithTrustCAAndCRP`
- `0x1800043ed`: `IkeCompareChainWithTrustCAAndCRP`
- `0x180004404`: `IkeCompareChainWithTrustCAAndCRP`
- `0x1800044df`: `IkeCompareChainWithTrustCAAndCRP`

## pseudocode

```c
__int64 __fastcall IkeValidateChainAgainstIkePolicy(
        __int64 a1,
        PCCERT_CHAIN_CONTEXT *a2,
        __int64 a3,
        unsigned int a4,
        _DWORD *a5,
        __int64 a6)
{
  _DWORD *v10; // r10
  __int64 rgpChain; // rbp
  unsigned int cChain; // ebx
  __int64 v13; // rcx
  __int64 v14; // rbx
  PCERT_SIMPLE_CHAIN v15; // rdx
  PCCERT_CONTEXT pCertContext; // r8
  DWORD i; // ebp
  PCCERT_CHAIN_CONTEXT v19; // r12

  TraceLogHelper("IkeValidateChainAgainstIkePolicy", 1);
  v10 = a5;
  if ( !*(_DWORD *)(a6 + 16) )
    v10 = a5 + 6;
  if ( *v10 )
  {
    TraceLogHelper("IkeCompareChainWithTrustCAAndCRP", 1);
    rgpChain = (__int64)(*a2)->rgpChain;
    cChain = (*a2)->cChain;
    if ( (unsigned int)IkeCompareSimpleChainArrayWithPolicyRoot(0, rgpChain, cChain, a6)
      && (unsigned int)IkeCompareSimpleChainArrayWithCRPRootList(*(unsigned int *)(a6 + 8), a3, a4, rgpChain, cChain) )
    {
      TraceLogHelper("IkeCompareChainWithTrustCAAndCRP", 0);
      v14 = 0;
    }
    else
    {
      v14 = 0;
      for ( i = 0; i < (*a2)->cLowerQualityChainContext; ++i )
      {
        v13 = i;
        v19 = (*a2)->rgpLowerQualityChainContext[i];
        if ( (v19->TrustStatus.dwErrorStatus & 8) == 0
          && IkeCompareSimpleChainArrayWithTrustCAAndCRP(0, a3, a4, (__int64)v19->rgpChain, v19->cChain, a6) )
        {
          CertDuplicateCertificateChain(v19);
          CertFreeCertificateChain(*a2);
          *a2 = v19;
          TraceLogHelper("IkeCompareChainWithTrustCAAndCRP", 0);
          goto LABEL_9;
        }
      }
      v14 = WfpReportSysErrorAsWinError(v13, "IkeCompareChainWithTrustCAAndCRP", 13887, 1);
      TraceLogHelper("IkeCompareChainWithTrustCAAndCRP", 0);
      if ( v14 )
        goto LABEL_11;
    }
LABEL_9:
    v15 = (*a2)->rgpChain[(*a2)->cChain - 1];
    pCertContext = v15->rgpElement[v15->cElement - 1]->pCertContext;
    *(_QWORD *)(a6 + 64) = pCertContext->pCertInfo->Issuer.pbData;
    *(_DWORD *)(a6 + 56) = pCertContext->pCertInfo->Issuer.cbData;
    if ( a1 )
      *(_DWORD *)(a6 + 72) = *(_DWORD *)(a1 + 48);
  }
  else
  {
    v14 = IkeCompareChainWithTrustCAAndCRP(a1, a3, a4, a2, a6);
  }
LABEL_11:
  TraceLogHelper("IkeValidateChainAgainstIkePolicy", 0);
  return v14;
}

```

## disassembly

```asm
0x180004310  mov     [rsp+arg_10], rbx
0x180004315  push    rsi
0x180004316  push    rdi
0x180004317  push    r13
0x180004319  push    r14
0x18000431b  push    r15
0x18000431d  sub     rsp, 30h
0x180004321  mov     rsi, rdx
0x180004324  mov     r13, rcx
0x180004327  mov     edx, 1
0x18000432c  lea     rcx, aIkevalidatecha; "IkeValidateChainAgainstIkePolicy"
0x180004333  mov     r14d, r9d
0x180004336  mov     r15, r8
0x180004339  call    TraceLogHelper
0x18000433e  mov     r10, [rsp+58h+arg_20]
0x180004346  mov     rdi, [rsp+58h+arg_28]
0x18000434e  lea     rax, [r10+18h]
0x180004352  cmp     dword ptr [rdi+10h], 0
0x180004356  cmovz   r10, rax
0x18000435a  cmp     dword ptr [r10], 0
0x18000435e  jz      short loc_1800043CC
0x180004360  mov     [rsp+58h+arg_0], rbp
0x180004365  lea     rcx, aIkecomparechai; "IkeCompareChainWithTrustCAAndCRP"
0x18000436c  mov     edx, 1
0x180004371  mov     [rsp+58h+arg_8], r12
0x180004376  call    TraceLogHelper
0x18000437b  mov     rax, [rsi]
0x18000437e  mov     r9, rdi
0x180004381  xor     ecx, ecx
0x180004383  mov     rbp, [rax+10h]
0x180004387  mov     ebx, [rax+0Ch]
0x18000438a  mov     rdx, rbp
0x18000438d  mov     r8d, ebx
0x180004390  call    IkeCompareSimpleChainArrayWithPolicyRoot
0x180004395  test    eax, eax
0x180004397  jz      loc_180004482
0x18000439d  mov     ecx, [rdi+8]
0x1800043a0  mov     r9, rbp
0x1800043a3  mov     r8d, r14d
0x1800043a6  mov     dword ptr [rsp+58h+var_38], ebx
0x1800043aa  mov     rdx, r15
0x1800043ad  call    IkeCompareSimpleChainArrayWithCRPRootList
0x1800043b2  test    eax, eax
0x1800043b4  jz      loc_180004482
0x1800043ba  xor     edx, edx
0x1800043bc  lea     rcx, aIkecomparechai; "IkeCompareChainWithTrustCAAndCRP"
0x1800043c3  call    TraceLogHelper
0x1800043c8  xor     ebx, ebx
0x1800043ca  jmp     short loc_180004415
0x1800043cc  mov     r9, rsi
0x1800043cf  mov     [rsp+58h+var_38], rdi
0x1800043d4  mov     r8d, r14d
0x1800043d7  mov     rdx, r15
0x1800043da  mov     rcx, r13
0x1800043dd  call    IkeCompareChainWithTrustCAAndCRP
0x1800043e2  mov     rbx, rax
0x1800043e5  jmp     short loc_18000445F
0x1800043e7  mov     r9d, 1
0x1800043ed  lea     rdx, aIkecomparechai; "IkeCompareChainWithTrustCAAndCRP"
0x1800043f4  mov     r8d, 363Fh
0x1800043fa  call    WfpReportSysErrorAsWinError
0x1800043ff  mov     rbx, rax
0x180004402  xor     edx, edx
0x180004404  lea     rcx, aIkecomparechai; "IkeCompareChainWithTrustCAAndCRP"
0x18000440b  call    TraceLogHelper
0x180004410  test    rbx, rbx
0x180004413  jnz     short loc_180004455
0x180004415  mov     rdx, [rsi]
0x180004418  mov     ecx, [rdx+0Ch]
0x18000441b  mov     rax, [rdx+10h]
0x18000441f  dec     ecx
0x180004421  mov     rdx, [rax+rcx*8]
0x180004425  mov     ecx, [rdx+0Ch]
0x180004428  mov     rax, [rdx+10h]
0x18000442c  dec     ecx
0x18000442e  mov     rcx, [rax+rcx*8]
0x180004432  mov     r8, [rcx+8]
0x180004436  mov     rax, [r8+18h]
0x18000443a  mov     rdx, [rax+38h]
0x18000443e  mov     [rdi+40h], rdx
0x180004442  mov     rax, [r8+18h]
0x180004446  mov     edx, [rax+30h]
0x180004449  mov     [rdi+38h], edx
0x18000444c  test    r13, r13
0x18000444f  jnz     loc_1800044F4
0x180004455  mov     rbp, [rsp+58h+arg_0]
0x18000445a  mov     r12, [rsp+58h+arg_8]
0x18000445f  xor     edx, edx
0x180004461  lea     rcx, aIkevalidatecha; "IkeValidateChainAgainstIkePolicy"
0x180004468  call    TraceLogHelper
0x18000446d  mov     rax, rbx
0x180004470  mov     rbx, [rsp+58h+arg_10]
0x180004475  add     rsp, 30h
0x180004479  pop     r15
0x18000447b  pop     r14
0x18000447d  pop     r13
0x18000447f  pop     rdi
0x180004480  pop     rsi
0x180004481  retn
0x180004482  xor     ebx, ebx
0x180004484  mov     ebp, ebx
0x180004486  mov     rax, [rsi]
0x180004489  cmp     ebp, [rax+18h]
0x18000448c  jnb     loc_1800043E7
0x180004492  mov     rax, [rax+20h]
0x180004496  mov     ecx, ebp
0x180004498  mov     r12, [rax+rcx*8]
0x18000449c  test    byte ptr [r12+4], 8
0x1800044a2  jnz     short loc_1800044F0
0x1800044a4  mov     eax, [r12+0Ch]
0x1800044a9  mov     r8d, r14d
0x1800044ac  mov     r9, [r12+10h]
0x1800044b1  mov     rdx, r15
0x1800044b4  mov     [rsp+58h+var_30], rdi
0x1800044b9  xor     ecx, ecx
0x1800044bb  mov     dword ptr [rsp+58h+var_38], eax
0x1800044bf  call    IkeCompareSimpleChainArrayWithTrustCAAndCRP
0x1800044c4  test    eax, eax
0x1800044c6  jz      short loc_1800044F0
0x1800044c8  mov     rcx, r12; pChainContext
0x1800044cb  call    cs:__imp_CertDuplicateCertificateChain
0x1800044d1  mov     rcx, [rsi]; pChainContext
0x1800044d4  call    cs:__imp_CertFreeCertificateChain
0x1800044da  xor     edx, edx
0x1800044dc  mov     [rsi], r12
0x1800044df  lea     rcx, aIkecomparechai; "IkeCompareChainWithTrustCAAndCRP"
0x1800044e6  call    TraceLogHelper
0x1800044eb  jmp     loc_180004415
0x1800044f0  inc     ebp
0x1800044f2  jmp     short loc_180004486
0x1800044f4  mov     eax, [r13+30h]
0x1800044f8  mov     [rdi+48h], eax
0x1800044fb  jmp     loc_180004455
```
