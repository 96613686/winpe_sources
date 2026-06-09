# LsaDbIIsDomainWithinForest(_UNICODE_STRING *,int *,int *,void * *,ulong *,ulong *,ulong *)

- ea: `0x180009670`
- end: `0x18000986c`
- name: `?LsaDbIIsDomainWithinForest@@YAJPEAU_UNICODE_STRING@@PEAH1PEAPEAXPEAK33@Z`
- size: `508`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, int *, int *, void **, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180009670`
- `0x180026674`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009835`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009835`
- `LSASRV!LsapDuplicateSid` at `0x180009801`
- `LSASRV!LsapDuplicateSid` at `0x180009801`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x180009798`
- `LSASRV!LsarQueryTrustedDomainInfoByName` at `0x180009798`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180009853`
- `LSASRV!LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO` at `0x180009853`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180009844`
- `LSASRV!LsaIFree_LSAPR_POLICY_INFORMATION` at `0x180009844`
- `LSASRV!LsapCompareDomainNames` at `0x1800096ed`
- `LSASRV!LsapCompareDomainNames` at `0x1800096ed`
- `LSASRV!LsapDbQueryInformationPolicy` at `0x1800096c2`
- `LSASRV!LsapDbQueryInformationPolicy` at `0x1800096c2`

## pseudocode

```c
__int64 __fastcall LsaDbIIsDomainWithinForest(
        struct _UNICODE_STRING *a1,
        int *a2,
        int *a3,
        void **a4,
        unsigned int *a5,
        unsigned int *a6,
        unsigned int *a7)
{
  void **v7; // rsi
  int Match; // ebx
  __int64 v11; // r8
  int v12; // esi
  void **v13; // rdi
  void *v14; // rax
  int v15; // eax
  unsigned int v16; // edx
  unsigned int v17; // ecx
  __int64 v18; // r8
  __int64 v20; // [rsp+38h] [rbp-30h] BYREF
  void *v21; // [rsp+40h] [rbp-28h] BYREF
  _DWORD *v22; // [rsp+48h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-18h]

  v7 = a4;
  v20 = 0;
  v22 = 0;
  hMem = 0;
  v21 = 0;
  *a2 = 0;
  if ( a3 )
    *a3 = 0;
  Match = LsapDbQueryInformationPolicy(LsaDbpPolicyHandle, 12, &v20);
  if ( Match < 0 )
    goto LABEL_31;
  v12 = 1;
  if ( (unsigned __int8)LsapCompareDomainNames(a1, v20 + 16, v20) )
  {
    *a2 = 1;
    if ( a3 )
      *a3 = 1;
    v13 = a4;
    v14 = *(void **)(v20 + 64);
    goto LABEL_19;
  }
  v13 = a4;
  LOBYTE(v11) = 1;
  Match = LsaDbpForestTrustFindMatch(1, a1, v11, 0, (unsigned __int64)&v21 & -(__int64)(a4 != 0));
  v14 = v21;
  hMem = v21;
  if ( Match < 0 )
  {
    if ( Match != -1073741198 )
      goto LABEL_30;
    v14 = 0;
    Match = 0;
    v12 = 0;
  }
  v21 = v14;
  *a2 = v12;
  if ( !*a2 || !a5 && !a6 && !a7 )
    goto LABEL_19;
  v15 = LsarQueryTrustedDomainInfoByName(LsaDbpPolicyHandle, a1, 6, &v22);
  Match = v15;
  if ( v15 >= 0 )
  {
    v16 = v22[11];
    v17 = v22[10];
    v18 = (unsigned int)v22[12];
    v14 = v21;
    goto LABEL_20;
  }
  if ( v15 == -1073741772 )
  {
    v14 = v21;
    Match = 0;
LABEL_19:
    v18 = 0;
    v16 = 0;
    v17 = 0;
LABEL_20:
    if ( *a2 )
    {
      if ( a5 )
        *a5 = v17;
      if ( a6 )
        *a6 = v16;
      if ( a7 )
        *a7 = v18;
      if ( v13 && v14 )
        Match = LsapDuplicateSid(v13, v14, v18, 0);
      goto LABEL_39;
    }
  }
LABEL_30:
  v7 = a4;
LABEL_31:
  if ( v7 )
    *v7 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a7 )
    *a7 = 0;
LABEL_39:
  LocalFree(hMem);
  LsaIFree_LSAPR_POLICY_INFORMATION(12);
  LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO(6, v22);
  return (unsigned int)Match;
}

```

## disassembly

```asm
0x180009670  mov     [rsp-40h+arg_18], r9
0x180009675  mov     [rsp-40h+arg_0], rcx
0x18000967a  push    rbp
0x18000967b  push    rbx
0x18000967c  push    rsi
0x18000967d  push    rdi
0x18000967e  push    r12
0x180009680  push    r13
0x180009682  push    r14
0x180009684  push    r15
0x180009686  mov     rbp, rsp
0x180009689  sub     rsp, 68h
0x18000968d  xor     ecx, ecx
0x18000968f  mov     rsi, r9
0x180009692  mov     [rbp+var_30], rcx
0x180009696  mov     rdi, r8
0x180009699  mov     [rbp+var_20], rcx
0x18000969d  mov     r14, rdx
0x1800096a0  mov     [rbp+hMem], rcx
0x1800096a4  mov     [rbp+var_28], rcx
0x1800096a8  mov     [rdx], ecx
0x1800096aa  test    r8, r8
0x1800096ad  jz      short loc_1800096B2
0x1800096af  mov     [r8], ecx
0x1800096b2  mov     rcx, cs:?LsaDbpPolicyHandle@@3PEAXEA; void * LsaDbpPolicyHandle
0x1800096b9  lea     r8, [rbp+var_30]
0x1800096bd  mov     edx, 0Ch
0x1800096c2  call    cs:__imp_LsapDbQueryInformationPolicy
0x1800096c8  mov     r15, [rbp+arg_30]
0x1800096cc  xor     r9d, r9d
0x1800096cf  mov     r12, [rbp+arg_28]
0x1800096d3  mov     ebx, eax
0x1800096d5  mov     r13, [rbp+arg_20]
0x1800096d9  test    eax, eax
0x1800096db  js      loc_18000980F
0x1800096e1  mov     r8, [rbp+var_30]
0x1800096e5  mov     rcx, [rbp+arg_0]
0x1800096e9  lea     rdx, [r8+10h]
0x1800096ed  call    cs:__imp_LsapCompareDomainNames
0x1800096f3  xor     r9d, r9d
0x1800096f6  lea     esi, [r9+1]
0x1800096fa  test    al, al
0x1800096fc  jz      short loc_180009719
0x1800096fe  mov     [r14], esi
0x180009701  test    rdi, rdi
0x180009704  jz      short loc_180009708
0x180009706  mov     [rdi], esi
0x180009708  mov     rax, [rbp+var_30]
0x18000970c  mov     rdi, [rbp+arg_18]
0x180009710  mov     rax, [rax+40h]
0x180009714  jmp     loc_1800097C9
0x180009719  mov     rdi, [rbp+arg_18]
0x18000971d  mov     r8b, sil
0x180009720  mov     rdx, [rbp+arg_0]
0x180009724  mov     rax, rdi
0x180009727  neg     rax
0x18000972a  lea     rax, [rbp+var_28]
0x18000972e  sbb     rcx, rcx
0x180009731  and     rcx, rax
0x180009734  mov     [rsp+68h+var_48], rcx
0x180009739  mov     ecx, esi
0x18000973b  call    ?LsaDbpForestTrustFindMatch@@YAJW4LSA_ROUTING_MATCH_TYPE@@PEAXEPEAU_UNICODE_STRING@@PEAPEAX@Z; LsaDbpForestTrustFindMatch(LSA_ROUTING_MATCH_TYPE,void *,uchar,_UNICODE_STRING *,void * *)
0x180009740  mov     ebx, eax
0x180009742  xor     r9d, r9d
0x180009745  mov     rax, [rbp+var_28]
0x180009749  mov     [rbp+hMem], rax
0x18000974d  test    ebx, ebx
0x18000974f  jns     short loc_180009766
0x180009751  cmp     ebx, 0C0000272h
0x180009757  jnz     loc_18000980B
0x18000975d  mov     eax, r9d
0x180009760  mov     ebx, r9d
0x180009763  mov     esi, r9d
0x180009766  mov     rcx, r14
0x180009769  mov     [rbp+var_28], rax
0x18000976d  mov     [rcx], esi
0x18000976f  cmp     [r14], r9d
0x180009772  jz      short loc_1800097C9
0x180009774  test    r13, r13
0x180009777  jnz     short loc_180009783
0x180009779  test    r12, r12
0x18000977c  jnz     short loc_180009783
0x18000977e  test    r15, r15
0x180009781  jz      short loc_1800097C9
0x180009783  mov     rdx, [rbp+arg_0]
0x180009787  lea     r9, [rbp+var_20]
0x18000978b  mov     rcx, cs:?LsaDbpPolicyHandle@@3PEAXEA; void * LsaDbpPolicyHandle
0x180009792  mov     r8d, 6
0x180009798  call    cs:__imp_LsarQueryTrustedDomainInfoByName
0x18000979e  xor     r9d, r9d
0x1800097a1  mov     ebx, eax
0x1800097a3  test    eax, eax
0x1800097a5  js      short loc_1800097BB
0x1800097a7  mov     rax, [rbp+var_20]
0x1800097ab  mov     edx, [rax+2Ch]
0x1800097ae  mov     ecx, [rax+28h]
0x1800097b1  mov     r8d, [rax+30h]
0x1800097b5  mov     rax, [rbp+var_28]
0x1800097b9  jmp     short loc_1800097D2
0x1800097bb  cmp     eax, 0C0000034h
0x1800097c0  jnz     short loc_18000980B
0x1800097c2  mov     rax, [rbp+var_28]
0x1800097c6  mov     ebx, r9d
0x1800097c9  mov     r8d, r9d
0x1800097cc  mov     edx, r9d
0x1800097cf  mov     ecx, r9d
0x1800097d2  cmp     [r14], r9d
0x1800097d5  jz      short loc_18000980B
0x1800097d7  test    r13, r13
0x1800097da  jz      short loc_1800097E0
0x1800097dc  mov     [r13+0], ecx
0x1800097e0  test    r12, r12
0x1800097e3  jz      short loc_1800097E9
0x1800097e5  mov     [r12], edx
0x1800097e9  test    r15, r15
0x1800097ec  jz      short loc_1800097F1
0x1800097ee  mov     [r15], r8d
0x1800097f1  test    rdi, rdi
0x1800097f4  jz      short loc_180009831
0x1800097f6  test    rax, rax
0x1800097f9  jz      short loc_180009831
0x1800097fb  mov     rdx, rax
0x1800097fe  mov     rcx, rdi
0x180009801  call    cs:__imp_LsapDuplicateSid
0x180009807  mov     ebx, eax
0x180009809  jmp     short loc_180009831
0x18000980b  mov     rsi, [rbp+arg_18]
0x18000980f  test    rsi, rsi
0x180009812  jz      short loc_180009817
0x180009814  mov     [rsi], r9
0x180009817  test    r13, r13
0x18000981a  jz      short loc_180009820
0x18000981c  mov     [r13+0], r9d
0x180009820  test    r12, r12
0x180009823  jz      short loc_180009829
0x180009825  mov     [r12], r9d
0x180009829  test    r15, r15
0x18000982c  jz      short loc_180009831
0x18000982e  mov     [r15], r9d
0x180009831  mov     rcx, [rbp+hMem]; hMem
0x180009835  call    cs:__imp_LocalFree
0x18000983b  mov     rdx, [rbp+var_30]
0x18000983f  mov     ecx, 0Ch
0x180009844  call    cs:__imp_LsaIFree_LSAPR_POLICY_INFORMATION
0x18000984a  mov     rdx, [rbp+var_20]
0x18000984e  mov     ecx, 6
0x180009853  call    cs:__imp_LsaIFree_LSAPR_TRUSTED_DOMAIN_INFO
0x180009859  mov     eax, ebx
0x18000985b  add     rsp, 68h
0x18000985f  pop     r15
0x180009861  pop     r14
0x180009863  pop     r13
0x180009865  pop     r12
0x180009867  pop     rdi
0x180009868  pop     rsi
0x180009869  pop     rbx
0x18000986a  pop     rbp
0x18000986b  retn
```
