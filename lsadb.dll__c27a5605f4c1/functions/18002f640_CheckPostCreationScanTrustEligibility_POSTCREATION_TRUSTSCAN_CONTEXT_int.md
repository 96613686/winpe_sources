# CheckPostCreationScanTrustEligibility(_POSTCREATION_TRUSTSCAN_CONTEXT *,int *)

- ea: `0x18002f640`
- end: `0x18002f8ed`
- name: `?CheckPostCreationScanTrustEligibility@@YAJPEAU_POSTCREATION_TRUSTSCAN_CONTEXT@@PEAH@Z`
- size: `685`
- prototype: `__int64 __fastcall(struct _POSTCREATION_TRUSTSCAN_CONTEXT *, int *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800316b0`
- `0x1800318d0`

## callees

- `0x18000bf70`
- `0x18000fd18`
- `0x18000fd40`
- `0x18000fd80`
- `0x18000fde0`
- `0x180026940`
- `0x180027f28`
- `0x18002b6f0`
- `0x18002f640`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f877`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f877`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18002f6af`
- `LSASRV!LsapDbExpAcquireReadLockTrustedDomainList` at `0x18002f6af`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18002f769`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18002f774`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18002f769`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18002f774`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x18002f77e`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x18002f77e`
- `LSASRV!LsarClose` at `0x18002f890`
- `LSASRV!LsarClose` at `0x18002f890`
- `ntdll!RtlInitUnicodeString` at `0x18002f6a9`
- `ntdll!RtlInitUnicodeString` at `0x18002f6a9`

## pseudocode

```c
__int64 __fastcall CheckPostCreationScanTrustEligibility(struct _POSTCREATION_TRUSTSCAN_CONTEXT *a1, int *a2)
{
  PCWSTR *v3; // rsi
  __int64 v4; // rcx
  int LockTrustedDomainList; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rcx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  HLOCAL hMem; // [rsp+70h] [rbp+30h] BYREF
  void *v20; // [rsp+78h] [rbp+38h] BYREF
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v21; // [rsp+80h] [rbp+40h] BYREF

  v21 = 0;
  DestinationString = 0;
  v20 = 0;
  hMem = 0;
  *a2 = 0;
  v3 = (PCWSTR *)((char *)a1 + 8);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids, *v3);
  RtlInitUnicodeString(&DestinationString, *v3);
  LockTrustedDomainList = LsapDbExpAcquireReadLockTrustedDomainList(v4);
  v6 = LockTrustedDomainList;
  if ( LockTrustedDomainList < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_36;
    v8 = 77;
    goto LABEL_6;
  }
  v9 = LsaDbpLookupNameTrustedDomainListEx((struct _LSAPR_UNICODE_STRING *)&DestinationString, &v21);
  v6 = v9;
  if ( v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        78,
        &WPP_844d483327f83d00fc717282eb3891a9_Traceguids,
        (unsigned int)v9);
    goto LABEL_17;
  }
  if ( (*((_BYTE *)v21 + 64) & 8) == 0 )
  {
    *a2 = 0;
    v11 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v12 = 79;
LABEL_16:
      WPP_SF_(v11[2], v12, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids);
      goto LABEL_17;
    }
    goto LABEL_17;
  }
  if ( (*((_BYTE *)v21 + 56) & 1) == 0 )
  {
    *a2 = 0;
    v11 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v12 = 80;
      goto LABEL_16;
    }
LABEL_17:
    LsapDbExpReleaseLockTrustedDomainList(v11);
    goto LABEL_36;
  }
  LsapDbExpReleaseLockTrustedDomainList(v10);
  LockTrustedDomainList = LsaIOpenPolicyTrusted(&v20);
  v6 = LockTrustedDomainList;
  if ( LockTrustedDomainList < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v8 = 81;
LABEL_6:
      WPP_SF_d(v7[2], v8, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids, (unsigned int)LockTrustedDomainList);
      goto LABEL_36;
    }
    goto LABEL_36;
  }
  hMem = 0;
  LockTrustedDomainList = LsaDbrQueryForestTrustInformationWorker(
                            v20,
                            &DestinationString,
                            4u,
                            (struct _LSA_FOREST_TRUST_INFORMATION2 **)&hMem);
  v6 = LockTrustedDomainList;
  if ( LockTrustedDomainList == -1073741275 )
  {
    *a2 = 1;
    v6 = 0;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_Z(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        82,
        &WPP_844d483327f83d00fc717282eb3891a9_Traceguids,
        &DestinationString);
    goto LABEL_36;
  }
  if ( LockTrustedDomainList >= 0 )
  {
    if ( *(_DWORD *)hMem )
    {
      v13 = 0;
      while ( 1 )
      {
        v14 = *(_QWORD *)(*((_QWORD *)hMem + 1) + 8 * v13);
        if ( v14 )
        {
          if ( *(_DWORD *)(v14 + 4) == 4 )
            break;
        }
        v13 = (unsigned int)(v13 + 1);
        if ( (unsigned int)v13 >= *(_DWORD *)hMem )
          goto LABEL_32;
      }
      *a2 = 0;
      v15 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
        goto LABEL_35;
      v16 = 84;
    }
    else
    {
LABEL_32:
      *a2 = 1;
      v15 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      {
LABEL_35:
        v6 = 0;
        goto LABEL_36;
      }
      v16 = 85;
    }
    WPP_SF_Z(v15[2], v16, &WPP_844d483327f83d00fc717282eb3891a9_Traceguids, &DestinationString);
    goto LABEL_35;
  }
  v7 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v8 = 83;
    goto LABEL_6;
  }
LABEL_36:
  LsaDbpFreeForestTrustInfo2((struct _LSA_FOREST_TRUST_INFORMATION2 *)hMem);
  LocalFree(hMem);
  hMem = 0;
  if ( v20 )
    v6 = LsarClose(&v20);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_SDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      86,
      (unsigned int)&WPP_844d483327f83d00fc717282eb3891a9_Traceguids,
      (unsigned int)*v3,
      v6,
      *a2,
      *(_QWORD *)&DestinationString.Length,
      DestinationString.Buffer);
  return v6;
}

```

## disassembly

```asm
0x18002f640  push    rbp
0x18002f642  push    rbx
0x18002f643  push    rsi
0x18002f644  push    rdi
0x18002f645  push    r12
0x18002f647  mov     rbp, rsp
0x18002f64a  sub     rsp, 40h
0x18002f64e  xorps   xmm0, xmm0
0x18002f651  mov     [rbp+arg_10], 0
0x18002f659  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002f65d  mov     rdi, rdx
0x18002f660  mov     [rbp+arg_8], 0
0x18002f668  mov     [rbp+hMem], 0
0x18002f670  mov     dword ptr [rdx], 0
0x18002f676  lea     rsi, [rcx+8]
0x18002f67a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f681  lea     r12, WPP_844d483327f83d00fc717282eb3891a9_Traceguids
0x18002f688  test    byte ptr [rcx+1Ch], 10h
0x18002f68c  jz      short loc_18002F6A2
0x18002f68e  mov     r9, [rsi]
0x18002f691  mov     edx, 4Ch ; 'L'
0x18002f696  mov     rcx, [rcx+10h]
0x18002f69a  mov     r8, r12
0x18002f69d  call    WPP_SF_S
0x18002f6a2  mov     rdx, [rsi]; SourceString
0x18002f6a5  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002f6a9  call    cs:__imp_RtlInitUnicodeString
0x18002f6af  call    cs:__imp_LsapDbExpAcquireReadLockTrustedDomainList
0x18002f6b5  mov     ebx, eax
0x18002f6b7  test    eax, eax
0x18002f6b9  jns     short loc_18002F6E5
0x18002f6bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6c2  test    byte ptr [rcx+1Ch], 10h
0x18002f6c6  jz      loc_18002F86A
0x18002f6cc  mov     edx, 4Dh ; 'M'
0x18002f6d1  mov     rcx, [rcx+10h]
0x18002f6d5  mov     r9d, eax
0x18002f6d8  mov     r8, r12
0x18002f6db  call    WPP_SF_d
0x18002f6e0  jmp     loc_18002F86A
0x18002f6e5  lea     rdx, [rbp+arg_10]; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18002f6e9  lea     rcx, [rbp+DestinationString]; struct _LSAPR_UNICODE_STRING *
0x18002f6ed  call    ?LsaDbpLookupNameTrustedDomainListEx@@YAJPEAU_LSAPR_UNICODE_STRING@@PEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpLookupNameTrustedDomainListEx(_LSAPR_UNICODE_STRING *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18002f6f2  mov     ebx, eax
0x18002f6f4  test    eax, eax
0x18002f6f6  jns     short loc_18002F71B
0x18002f6f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f6ff  test    byte ptr [rcx+1Ch], 10h
0x18002f703  jz      short loc_18002F769
0x18002f705  mov     rcx, [rcx+10h]
0x18002f709  mov     edx, 4Eh ; 'N'
0x18002f70e  mov     r9d, eax
0x18002f711  mov     r8, r12
0x18002f714  call    WPP_SF_d
0x18002f719  jmp     short loc_18002F769
0x18002f71b  mov     rax, [rbp+arg_10]
0x18002f71f  test    byte ptr [rax+40h], 8
0x18002f723  jnz     short loc_18002F73F
0x18002f725  mov     dword ptr [rdi], 0
0x18002f72b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f732  test    byte ptr [rcx+1Ch], 10h
0x18002f736  jz      short loc_18002F769
0x18002f738  mov     edx, 4Fh ; 'O'
0x18002f73d  jmp     short loc_18002F75D
0x18002f73f  test    byte ptr [rax+38h], 1
0x18002f743  jnz     short loc_18002F774
0x18002f745  mov     dword ptr [rdi], 0
0x18002f74b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f752  test    byte ptr [rcx+1Ch], 10h
0x18002f756  jz      short loc_18002F769
0x18002f758  mov     edx, 50h ; 'P'
0x18002f75d  mov     rcx, [rcx+10h]
0x18002f761  mov     r8, r12
0x18002f764  call    WPP_SF_
0x18002f769  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18002f76f  jmp     loc_18002F86A
0x18002f774  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18002f77a  lea     rcx, [rbp+arg_8]
0x18002f77e  call    cs:__imp_LsaIOpenPolicyTrusted
0x18002f784  mov     ebx, eax
0x18002f786  test    eax, eax
0x18002f788  jns     short loc_18002F7A5
0x18002f78a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f791  test    byte ptr [rcx+1Ch], 10h
0x18002f795  jz      loc_18002F86A
0x18002f79b  mov     edx, 51h ; 'Q'
0x18002f7a0  jmp     loc_18002F6D1
0x18002f7a5  mov     rcx, [rbp+arg_8]; void *
0x18002f7a9  lea     r9, [rbp+hMem]; struct _LSA_FOREST_TRUST_INFORMATION2 **
0x18002f7ad  mov     r8d, 4; enum LSA_FOREST_TRUST_RECORD_TYPE
0x18002f7b3  mov     [rbp+hMem], 0
0x18002f7bb  lea     rdx, [rbp+DestinationString]; struct _UNICODE_STRING *
0x18002f7bf  call    ?LsaDbrQueryForestTrustInformationWorker@@YAJPEAXPEAU_UNICODE_STRING@@W4LSA_FOREST_TRUST_RECORD_TYPE@@PEAPEAU_LSA_FOREST_TRUST_INFORMATION2@@@Z; LsaDbrQueryForestTrustInformationWorker(void *,_UNICODE_STRING *,LSA_FOREST_TRUST_RECORD_TYPE,_LSA_FOREST_TRUST_INFORMATION2 * *)
0x18002f7c4  mov     ebx, eax
0x18002f7c6  cmp     eax, 0C0000225h
0x18002f7cb  jnz     short loc_18002F7FB
0x18002f7cd  mov     dword ptr [rdi], 1
0x18002f7d3  xor     ebx, ebx
0x18002f7d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f7dc  test    byte ptr [rcx+1Ch], 10h
0x18002f7e0  jz      loc_18002F86A
0x18002f7e6  mov     rcx, [rcx+10h]
0x18002f7ea  lea     edx, [rbx+52h]
0x18002f7ed  lea     r9, [rbp+DestinationString]
0x18002f7f1  mov     r8, r12
0x18002f7f4  call    WPP_SF_Z
0x18002f7f9  jmp     short loc_18002F86A
0x18002f7fb  test    eax, eax
0x18002f7fd  jns     short loc_18002F816
0x18002f7ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f806  test    byte ptr [rcx+1Ch], 10h
0x18002f80a  jz      short loc_18002F86A
0x18002f80c  mov     edx, 53h ; 'S'
0x18002f811  jmp     loc_18002F6D1
0x18002f816  mov     rax, [rbp+hMem]
0x18002f81a  mov     edx, [rax]
0x18002f81c  test    edx, edx
0x18002f81e  jz      short loc_18002F840
0x18002f820  mov     r9, [rax+8]
0x18002f824  xor     ecx, ecx
0x18002f826  mov     r8, [r9+rcx*8]
0x18002f82a  test    r8, r8
0x18002f82d  jz      short loc_18002F83A
0x18002f82f  cmp     dword ptr [r8+4], 4
0x18002f834  jz      loc_18002F8D0
0x18002f83a  inc     ecx
0x18002f83c  cmp     ecx, edx
0x18002f83e  jb      short loc_18002F826
0x18002f840  mov     dword ptr [rdi], 1
0x18002f846  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f84d  test    byte ptr [rcx+1Ch], 10h
0x18002f851  jz      short loc_18002F868
0x18002f853  mov     edx, 55h ; 'U'
0x18002f858  mov     rcx, [rcx+10h]
0x18002f85c  lea     r9, [rbp+DestinationString]
0x18002f860  mov     r8, r12
0x18002f863  call    WPP_SF_Z
0x18002f868  xor     ebx, ebx
0x18002f86a  mov     rcx, [rbp+hMem]; struct _LSA_FOREST_TRUST_INFORMATION2 *
0x18002f86e  call    ?LsaDbpFreeForestTrustInfo2@@YAXPEAU_LSA_FOREST_TRUST_INFORMATION2@@@Z; LsaDbpFreeForestTrustInfo2(_LSA_FOREST_TRUST_INFORMATION2 *)
0x18002f873  mov     rcx, [rbp+hMem]; hMem
0x18002f877  call    cs:__imp_LocalFree
0x18002f87d  cmp     [rbp+arg_8], 0
0x18002f882  mov     [rbp+hMem], 0
0x18002f88a  jz      short loc_18002F898
0x18002f88c  lea     rcx, [rbp+arg_8]
0x18002f890  call    cs:__imp_LsarClose
0x18002f896  mov     ebx, eax
0x18002f898  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f89f  test    byte ptr [rcx+1Ch], 10h
0x18002f8a3  jz      short loc_18002F8C3
0x18002f8a5  mov     eax, [rdi]
0x18002f8a7  mov     edx, 56h ; 'V'
0x18002f8ac  mov     r9, [rsi]
0x18002f8af  mov     r8, r12
0x18002f8b2  mov     rcx, [rcx+10h]
0x18002f8b6  mov     [rsp+40h+var_18], eax
0x18002f8ba  mov     [rsp+40h+var_20], ebx
0x18002f8be  call    WPP_SF_SDD
0x18002f8c3  mov     eax, ebx
0x18002f8c5  add     rsp, 40h
0x18002f8c9  pop     r12
0x18002f8cb  pop     rdi
0x18002f8cc  pop     rsi
0x18002f8cd  pop     rbx
0x18002f8ce  pop     rbp
0x18002f8cf  retn
0x18002f8d0  mov     dword ptr [rdi], 0
0x18002f8d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f8dd  test    byte ptr [rcx+1Ch], 10h
0x18002f8e1  jz      short loc_18002F868
0x18002f8e3  mov     edx, 54h ; 'T'
0x18002f8e8  jmp     loc_18002F858
```
