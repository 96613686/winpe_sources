# LsaDbpLookupSidsBuildWorkList(ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_NAMES_EX *,_LSAP_LOOKUP_LEVEL,ulong *,ulong *,_LSAP_DB_LOOKUP_WORK_LIST * *)

- ea: `0x18001b94c`
- end: `0x18001bbcd`
- name: `?LsaDbpLookupSidsBuildWorkList@@YAJKPEAPEAU_LSAPR_SID@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@W4_LSAP_LOOKUP_LEVEL@@PEAK4PEAPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z`
- size: `641`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18001e860`

## callees

- `0x18001a658`
- `0x18001a6d8`
- `0x18001b020`
- `0x18001b0dc`
- `0x18001b214`
- `0x18001b94c`
- `0x18001c088`
- `0x180032de4`
- `0x18003ad30`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ba19`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ba19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ba8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001baa7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bb77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ba8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001baa7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bb77`
- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x18001bad2`
- `LSASRV!LsapDbLookupAddListReferencedDomains` at `0x18001bad2`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18001bb83`
- `LSASRV!LsapDbExpReleaseLockTrustedDomainList` at `0x18001bb83`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001ba3c`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001ba3c`
- `ntdll!RtlLengthSid` at `0x18001ba08`
- `ntdll!RtlLengthSid` at `0x18001ba08`
- `ntdll!RtlEqualSid` at `0x18001ba5c`
- `ntdll!RtlEqualSid` at `0x18001ba5c`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupSidsBuildWorkList(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int8 a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8)
{
  int WorkList; // eax
  __int64 v13; // rcx
  HLOCAL v14; // rdi
  int HasDomainTrust; // ebx
  __int64 v16; // rcx
  unsigned int v17; // r15d
  unsigned int v18; // eax
  unsigned int i; // edx
  void *v20; // rbx
  SIZE_T v21; // r14
  HLOCAL v22; // rax
  void *v23; // rsi
  PUCHAR v24; // rax
  struct _LSAP_DB_LOOKUP_WORK_ITEM **v25; // rbx
  struct _LSAP_DB_LOOKUP_WORK_ITEM *j; // r14
  const UNICODE_STRING *v27; // r14
  __int64 v28; // r8
  HLOCAL hMem; // [rsp+30h] [rbp-20h] BYREF
  int v31; // [rsp+38h] [rbp-18h] BYREF
  struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *v32; // [rsp+40h] [rbp-10h] BYREF
  struct _LSAP_DB_LOOKUP_WORK_ITEM *v33; // [rsp+48h] [rbp-8h] BYREF

  hMem = 0;
  v32 = 0;
  v31 = 0;
  a5 = 0;
  WorkList = LsaDbpLookupCreateWorkList((struct _LSAP_DB_LOOKUP_WORK_LIST **)&hMem);
  v14 = hMem;
  HasDomainTrust = WorkList;
  if ( WorkList < 0 )
    goto LABEL_23;
  v16 = a6;
  *((_DWORD *)hMem + 10) = 1;
  *((_DWORD *)v14 + 16) = a1;
  *((_DWORD *)v14 + 17) = 3;
  *((_QWORD *)v14 + 9) = a3;
  *((_QWORD *)v14 + 10) = v16;
  v13 = a7;
  *((_QWORD *)v14 + 11) = a7;
  *((_QWORD *)v14 + 14) = a2;
  v17 = 0;
  *((_QWORD *)v14 + 15) = a4;
  LODWORD(hMem) = 0;
  if ( a1 )
  {
    v18 = 0;
    for ( i = 0; ; i = v17 )
    {
      v13 = 32LL * v18;
      if ( *(_DWORD *)(v13 + *(_QWORD *)(a4 + 8) + 24) == -1 )
      {
        v20 = *(void **)(a2 + 8LL * i);
        v21 = RtlLengthSid(v20) - 4;
        v22 = LocalAlloc(0x40u, v21);
        v23 = v22;
        if ( !v22 )
        {
          HasDomainTrust = -1073741670;
          goto LABEL_23;
        }
        memcpy_0(v22, v20, (unsigned int)v21);
        v24 = RtlSubAuthorityCountSid(v23);
        v33 = 0;
        --*v24;
        v25 = (struct _LSAP_DB_LOOKUP_WORK_ITEM **)*((_QWORD *)v14 + 2);
        for ( j = *v25; j != (struct _LSAP_DB_LOOKUP_WORK_ITEM *)v25; j = *(struct _LSAP_DB_LOOKUP_WORK_ITEM **)j )
        {
          if ( RtlEqualSid(*((PSID *)j + 5), v23) )
          {
            LocalFree(v23);
            goto LABEL_18;
          }
        }
        HasDomainTrust = LsaDbpDomainHasDomainTrust(1u, 0, v23, &a5, &v32);
        LocalFree(v23);
        if ( HasDomainTrust == -1073741601 )
          goto LABEL_11;
        if ( HasDomainTrust < 0 )
          goto LABEL_23;
        if ( (*((_BYTE *)v32 + 56) & 2) == 0 )
        {
LABEL_11:
          HasDomainTrust = 0;
          goto LABEL_20;
        }
        v27 = (const UNICODE_STRING *)((char *)v32 + 72);
        HasDomainTrust = LsapDbLookupAddListReferencedDomains(a3, (char *)v32 + 72, &v31);
        if ( HasDomainTrust < 0 )
          goto LABEL_23;
        HasDomainTrust = LsaDbpLookupCreateWorkItem(v27, v31, v28, &v33);
        if ( HasDomainTrust < 0 )
          goto LABEL_23;
        j = v33;
        HasDomainTrust = LsaDbpAddWorkItemToWorkList((struct _LSAP_DB_LOOKUP_WORK_LIST *)v14, v33);
        if ( HasDomainTrust < 0 )
          goto LABEL_23;
LABEL_18:
        HasDomainTrust = LsaDbpLookupAddIndicesToWorkItem(j, 1u, (unsigned int *)&hMem);
        if ( HasDomainTrust < 0 )
          goto LABEL_23;
        v17 = (unsigned int)hMem;
        v13 = *(_QWORD *)(*((_QWORD *)v14 + 15) + 8LL);
        *(_DWORD *)(32LL * (unsigned int)hMem + v13 + 24) = *((_DWORD *)j + 12);
      }
LABEL_20:
      LODWORD(hMem) = ++v17;
      v18 = v17;
      if ( v17 >= a1 )
        break;
    }
    if ( HasDomainTrust < 0 )
      goto LABEL_23;
  }
  HasDomainTrust = -1073741709;
  if ( !*((_DWORD *)v14 + 14) )
  {
LABEL_23:
    if ( v14 )
      LsaDbpLookupDeleteWorkList(v14);
    *a8 = 0;
  }
  else
  {
    HasDomainTrust = 0;
    *((_DWORD *)v14 + 24) = *((_DWORD *)v14 + 14) - 1;
    LsaDbpUpdateMappedCountsWorkList((struct _LSAP_DB_LOOKUP_WORK_LIST *)v14);
    *a8 = v14;
  }
  if ( a5 )
    LsapDbExpReleaseLockTrustedDomainList(v13);
  return (unsigned int)HasDomainTrust;
}

```

## disassembly

```asm
0x18001b94c  mov     [rsp-38h+arg_0], rbx
0x18001b951  mov     [rsp-38h+arg_10], r8
0x18001b956  mov     [rsp-38h+arg_8], rdx
0x18001b95b  push    rbp
0x18001b95c  push    rsi
0x18001b95d  push    rdi
0x18001b95e  push    r12
0x18001b960  push    r13
0x18001b962  push    r14
0x18001b964  push    r15
0x18001b966  mov     rbp, rsp
0x18001b969  sub     rsp, 50h
0x18001b96d  xor     eax, eax
0x18001b96f  mov     r12d, ecx
0x18001b972  lea     rcx, [rbp+hMem]; struct _LSAP_DB_LOOKUP_WORK_LIST **
0x18001b976  mov     [rbp+hMem], rax
0x18001b97a  mov     esi, eax
0x18001b97c  mov     [rbp+var_10], rax
0x18001b980  mov     [rbp+var_18], eax
0x18001b983  mov     r13, r9
0x18001b986  mov     [rbp+arg_20], al
0x18001b989  mov     r14, r8
0x18001b98c  mov     r15, rdx
0x18001b98f  call    ?LsaDbpLookupCreateWorkList@@YAJPEAPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupCreateWorkList(_LSAP_DB_LOOKUP_WORK_LIST * *)
0x18001b994  mov     rdi, [rbp+hMem]
0x18001b998  mov     ebx, eax
0x18001b99a  test    eax, eax
0x18001b99c  js      loc_18001BB57
0x18001b9a2  mov     rcx, [rbp+arg_28]
0x18001b9a6  mov     dword ptr [rdi+28h], 1
0x18001b9ad  mov     [rdi+40h], r12d
0x18001b9b1  mov     dword ptr [rdi+44h], 3
0x18001b9b8  mov     [rdi+48h], r14
0x18001b9bc  mov     [rdi+50h], rcx
0x18001b9c0  mov     rcx, [rbp+arg_30]
0x18001b9c4  mov     [rdi+58h], rcx
0x18001b9c8  mov     [rdi+70h], r15
0x18001b9cc  xor     r15d, r15d
0x18001b9cf  mov     [rdi+78h], r13
0x18001b9d3  mov     dword ptr [rbp+hMem], r15d
0x18001b9d7  test    r12d, r12d
0x18001b9da  jz      loc_18001BBA7
0x18001b9e0  xor     eax, eax
0x18001b9e2  xor     edx, edx
0x18001b9e4  mov     ecx, eax
0x18001b9e6  xor     esi, esi
0x18001b9e8  mov     rax, [r13+8]
0x18001b9ec  shl     rcx, 5
0x18001b9f0  cmp     dword ptr [rcx+rax+18h], 0FFFFFFFFh
0x18001b9f5  jnz     loc_18001BB3A
0x18001b9fb  mov     rcx, [rbp+arg_8]
0x18001b9ff  mov     eax, edx
0x18001ba01  mov     rbx, [rcx+rax*8]
0x18001ba05  mov     rcx, rbx; Sid
0x18001ba08  call    cs:__imp_RtlLengthSid
0x18001ba0e  sub     eax, 4
0x18001ba11  lea     ecx, [rsi+40h]; uFlags
0x18001ba14  mov     edx, eax; uBytes
0x18001ba16  mov     r14d, eax
0x18001ba19  call    cs:__imp_LocalAlloc
0x18001ba1f  mov     rsi, rax
0x18001ba22  test    rax, rax
0x18001ba25  jz      loc_18001BB50
0x18001ba2b  mov     r8d, r14d; Size
0x18001ba2e  mov     rdx, rbx; Src
0x18001ba31  mov     rcx, rax; void *
0x18001ba34  call    memcpy_0
0x18001ba39  mov     rcx, rsi; Sid
0x18001ba3c  call    cs:__imp_RtlSubAuthorityCountSid
0x18001ba42  mov     [rbp+var_8], 0
0x18001ba4a  dec     byte ptr [rax]
0x18001ba4c  mov     rbx, [rdi+10h]
0x18001ba50  mov     r14, [rbx]
0x18001ba53  jmp     short loc_18001BA69
0x18001ba55  mov     rcx, [r14+28h]; Sid1
0x18001ba59  mov     rdx, rsi; Sid2
0x18001ba5c  call    cs:__imp_RtlEqualSid
0x18001ba62  test    al, al
0x18001ba64  jnz     short loc_18001BAA4
0x18001ba66  mov     r14, [r14]
0x18001ba69  cmp     r14, rbx
0x18001ba6c  jnz     short loc_18001BA55
0x18001ba6e  xor     edx, edx; struct _UNICODE_STRING *
0x18001ba70  lea     rax, [rbp+var_10]
0x18001ba74  lea     r9, [rbp+arg_20]; unsigned __int8 *
0x18001ba78  mov     [rsp+50h+var_30], rax; struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY **
0x18001ba7d  mov     r8, rsi; void *
0x18001ba80  lea     ecx, [rdx+1]; unsigned int
0x18001ba83  call    ?LsaDbpDomainHasDomainTrust@@YAJKPEAU_UNICODE_STRING@@PEAXPEAEPEAPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@@Z; LsaDbpDomainHasDomainTrust(ulong,_UNICODE_STRING *,void *,uchar *,_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY * *)
0x18001ba88  mov     rcx, rsi; hMem
0x18001ba8b  mov     ebx, eax
0x18001ba8d  call    cs:__imp_LocalFree
0x18001ba93  xor     esi, esi
0x18001ba95  cmp     ebx, 0C00000DFh
0x18001ba9b  jnz     short loc_18001BAB1
0x18001ba9d  xor     ebx, ebx
0x18001ba9f  jmp     loc_18001BB3A
0x18001baa4  mov     rcx, rsi; hMem
0x18001baa7  call    cs:__imp_LocalFree
0x18001baad  xor     esi, esi
0x18001baaf  jmp     short loc_18001BB08
0x18001bab1  test    ebx, ebx
0x18001bab3  js      loc_18001BB57
0x18001bab9  mov     rax, [rbp+var_10]
0x18001babd  test    byte ptr [rax+38h], 2
0x18001bac1  jz      short loc_18001BA9D
0x18001bac3  mov     rcx, [rbp+arg_10]
0x18001bac7  lea     r14, [rax+48h]
0x18001bacb  mov     rdx, r14
0x18001bace  lea     r8, [rbp+var_18]
0x18001bad2  call    cs:__imp_LsapDbLookupAddListReferencedDomains
0x18001bad8  mov     ebx, eax
0x18001bada  test    eax, eax
0x18001badc  js      short loc_18001BB57
0x18001bade  mov     edx, [rbp+var_18]; int
0x18001bae1  lea     r9, [rbp+var_8]; struct _LSAP_DB_LOOKUP_WORK_ITEM **
0x18001bae5  mov     rcx, r14; SourceString
0x18001bae8  call    ?LsaDbpLookupCreateWorkItem@@YAJPEAU_LSAPR_TRUST_INFORMATION@@JKPEAPEAU_LSAP_DB_LOOKUP_WORK_ITEM@@@Z; LsaDbpLookupCreateWorkItem(_LSAPR_TRUST_INFORMATION *,long,ulong,_LSAP_DB_LOOKUP_WORK_ITEM * *)
0x18001baed  mov     ebx, eax
0x18001baef  test    eax, eax
0x18001baf1  js      short loc_18001BB57
0x18001baf3  mov     r14, [rbp+var_8]
0x18001baf7  mov     rcx, rdi; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x18001bafa  mov     rdx, r14; struct _LSAP_DB_LOOKUP_WORK_ITEM *
0x18001bafd  call    ?LsaDbpAddWorkItemToWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@PEAU_LSAP_DB_LOOKUP_WORK_ITEM@@@Z; LsaDbpAddWorkItemToWorkList(_LSAP_DB_LOOKUP_WORK_LIST *,_LSAP_DB_LOOKUP_WORK_ITEM *)
0x18001bb02  mov     ebx, eax
0x18001bb04  test    eax, eax
0x18001bb06  js      short loc_18001BB57
0x18001bb08  lea     r8, [rbp+hMem]; unsigned int *
0x18001bb0c  mov     edx, 1; unsigned int
0x18001bb11  mov     rcx, r14; struct _LSAP_DB_LOOKUP_WORK_ITEM *
0x18001bb14  call    ?LsaDbpLookupAddIndicesToWorkItem@@YAJPEAU_LSAP_DB_LOOKUP_WORK_ITEM@@KPEAK@Z; LsaDbpLookupAddIndicesToWorkItem(_LSAP_DB_LOOKUP_WORK_ITEM *,ulong,ulong *)
0x18001bb19  mov     ebx, eax
0x18001bb1b  test    eax, eax
0x18001bb1d  js      short loc_18001BB57
0x18001bb1f  mov     rax, [rdi+78h]
0x18001bb23  mov     r15d, dword ptr [rbp+hMem]
0x18001bb27  mov     edx, r15d
0x18001bb2a  shl     rdx, 5
0x18001bb2e  mov     rcx, [rax+8]
0x18001bb32  mov     eax, [r14+30h]
0x18001bb36  mov     [rdx+rcx+18h], eax
0x18001bb3a  inc     r15d
0x18001bb3d  mov     dword ptr [rbp+hMem], r15d
0x18001bb41  mov     eax, r15d
0x18001bb44  cmp     r15d, r12d
0x18001bb47  jnb     short loc_18001BBA3
0x18001bb49  mov     edx, eax
0x18001bb4b  jmp     loc_18001B9E4
0x18001bb50  mov     ebx, 0C000009Ah
0x18001bb55  xor     esi, esi
0x18001bb57  test    rdi, rdi
0x18001bb5a  jz      short loc_18001BB64
0x18001bb5c  mov     rcx, rdi; hMem
0x18001bb5f  call    ?LsaDbpLookupDeleteWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupDeleteWorkList(_LSAP_DB_LOOKUP_WORK_LIST *)
0x18001bb64  mov     rax, [rbp+arg_38]
0x18001bb68  mov     qword ptr [rax], 0
0x18001bb6f  test    rsi, rsi
0x18001bb72  jz      short loc_18001BB7D
0x18001bb74  mov     rcx, rsi; hMem
0x18001bb77  call    cs:__imp_LocalFree
0x18001bb7d  cmp     [rbp+arg_20], 0
0x18001bb81  jz      short loc_18001BB89
0x18001bb83  call    cs:__imp_LsapDbExpReleaseLockTrustedDomainList
0x18001bb89  mov     eax, ebx
0x18001bb8b  mov     rbx, [rsp+50h+arg_0]
0x18001bb93  add     rsp, 50h
0x18001bb97  pop     r15
0x18001bb99  pop     r14
0x18001bb9b  pop     r13
0x18001bb9d  pop     r12
0x18001bb9f  pop     rdi
0x18001bba0  pop     rsi
0x18001bba1  pop     rbp
0x18001bba2  retn
0x18001bba3  test    ebx, ebx
0x18001bba5  js      short loc_18001BB57
0x18001bba7  cmp     dword ptr [rdi+38h], 0
0x18001bbab  mov     ebx, 0C0000073h
0x18001bbb0  jz      short loc_18001BB57
0x18001bbb2  mov     eax, [rdi+38h]
0x18001bbb5  xor     ebx, ebx
0x18001bbb7  dec     eax
0x18001bbb9  mov     rcx, rdi; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x18001bbbc  mov     [rdi+60h], eax
0x18001bbbf  call    ?LsaDbpUpdateMappedCountsWorkList@@YAXPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpUpdateMappedCountsWorkList(_LSAP_DB_LOOKUP_WORK_LIST *)
0x18001bbc4  mov     rax, [rbp+arg_38]
0x18001bbc8  mov     [rax], rdi
0x18001bbcb  jmp     short loc_18001BB6F
```
