# LsaDbpLookupNamesInTrustedForestsWorker(ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_REFERENCED_DOMAIN_LIST * *,_LSAPR_TRANSLATED_SIDS_EX2 *,uchar *,ulong *,ulong,long *)

- ea: `0x18001d7f4`
- end: `0x18001da8d`
- name: `?LsaDbpLookupNamesInTrustedForestsWorker@@YAJKPEAU_LSAPR_UNICODE_STRING@@00PEAPEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@PEAEPEAKKPEAJ@Z`
- size: `665`
- prototype: `__int64 __fastcall(unsigned int, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_UNICODE_STRING *, struct _LSAPR_REFERENCED_DOMAIN_LIST **, struct _LSAPR_TRANSLATED_SIDS_EX2 *, unsigned __int8 *, unsigned int *, unsigned int, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18001d334`
- `0x18001daa0`

## callees

- `0x180001fb8`
- `0x18001b214`
- `0x18001b8dc`
- `0x18001bbd4`
- `0x18001d7f4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d94c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001d94c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001d921`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001da36`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001d921`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001da36`
- `LSASRV!LsapDbLookupCreateListReferencedDomains` at `0x18001d9ad`
- `LSASRV!LsapDbLookupCreateListReferencedDomains` at `0x18001d9ad`
- `LSASRV!LsapDbLookupNameChainRequest` at `0x18001d8cf`
- `LSASRV!LsapDbLookupNameChainRequest` at `0x18001d8cf`
- `LSASRV!LsapDbLookupGetDomainInfo` at `0x18001d873`
- `LSASRV!LsapDbLookupGetDomainInfo` at `0x18001d873`
- `LSASRV!LsaLookupPerfCounterAddLargeAmount` at `0x18001da4d`
- `LSASRV!LsaLookupPerfCounterAddLargeAmount` at `0x18001da4d`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001da18`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001da5b`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001da18`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001da5b`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupNamesInTrustedForestsWorker(
        unsigned int a1,
        struct _LSAPR_UNICODE_STRING *a2,
        struct _LSAPR_UNICODE_STRING *a3,
        struct _LSAPR_UNICODE_STRING *a4,
        struct _LSAPR_REFERENCED_DOMAIN_LIST **a5,
        struct _LSAPR_TRANSLATED_SIDS_EX2 *a6,
        unsigned __int8 *a7,
        unsigned int *a8,
        unsigned int a9,
        int *a10)
{
  int *v10; // r12
  bool v11; // zf
  __int64 v13; // r14
  int DomainInfo; // edi
  unsigned int v15; // eax
  void *v16; // rcx
  HLOCAL v17; // rax
  __int64 i; // rdx
  __int64 v19; // rcx
  int v20; // eax
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp-41h] BYREF
  LARGE_INTEGER v23; // [rsp+68h] [rbp-39h] BYREF
  __int128 v24; // [rsp+70h] [rbp-31h] BYREF
  __int128 v25; // [rsp+80h] [rbp-21h]
  __int128 v26; // [rsp+90h] [rbp-11h]

  v10 = a10;
  v11 = DcInRootDomain == 0;
  v13 = a1;
  *a10 = 0;
  *a7 = 0;
  PerformanceCount.QuadPart = 0;
  v23.QuadPart = 0;
  if ( v11 )
  {
    a10 = 0;
    v24 = 0;
    v25 = 0;
    v26 = 0;
    DomainInfo = LsapDbLookupGetDomainInfo(0, &a10, 0);
    if ( DomainInfo >= 0 )
    {
      v24 = 0;
      v25 = 0;
      v26 = 0;
      v24 = *((_OWORD *)a10 + 2);
      DomainInfo = LsapDbLookupNameChainRequest(&v24, (unsigned int)v13, a2, a5, (char *)a6 + 8, 5, a8);
      if ( *((_QWORD *)a6 + 1) )
      {
        *a7 = 1;
        v15 = *a8;
      }
      else
      {
        v15 = 0;
      }
      *(_DWORD *)a6 = v15;
      if ( DomainInfo < 0 )
      {
        if ( (unsigned int)(DomainInfo + 1073741428) <= 1 || DomainInfo == -1073741136 )
          *v10 = DomainInfo;
        return 0;
      }
    }
  }
  else
  {
    if ( !QueryPerformanceCounter(&PerformanceCount) )
      PerformanceCount.QuadPart = 0;
    v16 = (void *)*((_QWORD *)a6 + 1);
    if ( !v16 )
    {
      v17 = LocalAlloc(0x40u, 24 * v13);
      *((_QWORD *)a6 + 1) = v17;
      v16 = v17;
      if ( !v17 )
        return (unsigned int)-1073741670;
      *(_DWORD *)a6 = v13;
    }
    memset_0(v16, 0, 24 * v13);
    for ( i = 0; (unsigned int)i < (unsigned int)v13; *(_DWORD *)(*((_QWORD *)a6 + 1) + 8 * v19 + 16) = -1 )
    {
      v19 = 3 * i;
      i = (unsigned int)(i + 1);
      *(_DWORD *)(*((_QWORD *)a6 + 1) + 8 * v19) = 8;
    }
    if ( *a5 || (DomainInfo = LsapDbLookupCreateListReferencedDomains(a5, 0), DomainInfo >= 0) )
    {
      v20 = LsaDbpLookupXForestNamesBuildWorkList(v13, (__int64)a2, (__int64)a3, (__int64)a4, (__int64)*a5, (__int64)a6);
      DomainInfo = v20;
      if ( v20 >= 0 )
      {
        LsaLookupPerfCounterAddAmount(0x10u, MEMORY[0x38]);
        DomainInfo = LsaDbpLookupProcessWorkList(0, v10);
        if ( PerformanceCount.QuadPart && QueryPerformanceCounter(&v23) )
        {
          LsaLookupPerfCounterAddLargeAmount(0x11u, v23.QuadPart - PerformanceCount.QuadPart);
          LsaLookupPerfCounterAddAmount(0x12u, MEMORY[0x38]);
        }
      }
      else if ( v20 == -1073741709 )
      {
        return 0;
      }
    }
  }
  return (unsigned int)DomainInfo;
}

```

## disassembly

```asm
0x18001d7f4  mov     rax, rsp
0x18001d7f7  mov     [rax+8], rbx
0x18001d7fb  mov     [rax+20h], r9
0x18001d7ff  mov     [rax+18h], r8
0x18001d803  mov     [rax+10h], rdx
0x18001d807  push    rbp
0x18001d808  push    rsi
0x18001d809  push    rdi
0x18001d80a  push    r12
0x18001d80c  push    r13
0x18001d80e  push    r14
0x18001d810  push    r15
0x18001d812  lea     rbp, [rax-3Fh]
0x18001d816  sub     rsp, 0A0h
0x18001d81d  mov     r12, [rbp+37h+arg_48]
0x18001d824  xor     ebx, ebx
0x18001d826  cmp     cs:?DcInRootDomain@@3EA, bl; uchar DcInRootDomain
0x18001d82c  mov     r13, rdx
0x18001d82f  mov     r15, [rbp+37h+arg_30]
0x18001d833  mov     esi, ebx
0x18001d835  mov     r14d, ecx
0x18001d838  mov     [r12], ebx
0x18001d83c  mov     [rbp+37h+var_80], rbx
0x18001d840  mov     [r15], bl
0x18001d843  mov     qword ptr [rbp+37h+PerformanceCount], rbx
0x18001d847  mov     qword ptr [rbp+37h+var_70], rbx
0x18001d84b  jnz     loc_18001D916
0x18001d851  xorps   xmm0, xmm0
0x18001d854  mov     [rbp+37h+arg_48], rbx
0x18001d85b  xor     r8d, r8d
0x18001d85e  lea     rdx, [rbp+37h+arg_48]
0x18001d865  xor     ecx, ecx
0x18001d867  movups  [rbp+37h+var_68], xmm0
0x18001d86b  movups  [rbp+37h+var_58], xmm0
0x18001d86f  movups  [rbp+37h+var_48], xmm0
0x18001d873  call    cs:__imp_LsapDbLookupGetDomainInfo
0x18001d879  mov     edi, eax
0x18001d87b  test    eax, eax
0x18001d87d  js      loc_18001DA70
0x18001d883  mov     rax, [rbp+37h+arg_48]
0x18001d88a  lea     rcx, [rbp+37h+var_68]
0x18001d88e  mov     r13, [rbp+37h+arg_28]
0x18001d892  xorps   xmm0, xmm0
0x18001d895  mov     r9, [rbp+37h+arg_20]
0x18001d899  mov     edx, r14d
0x18001d89c  mov     r8, [rbp+37h+arg_8]
0x18001d8a0  movups  [rbp+37h+var_68], xmm0
0x18001d8a4  lea     rbx, [r13+8]
0x18001d8a8  movups  [rbp+37h+var_58], xmm0
0x18001d8ac  movups  [rbp+37h+var_48], xmm0
0x18001d8b0  movups  xmm0, xmmword ptr [rax+20h]
0x18001d8b4  mov     rax, [rbp+37h+arg_38]
0x18001d8b8  mov     [rsp+0D0h+var_A0], rax
0x18001d8bd  mov     dword ptr [rsp+0D0h+var_A8], 5
0x18001d8c5  mov     [rsp+0D0h+var_B0], rbx
0x18001d8ca  movdqu  [rbp+37h+var_68], xmm0
0x18001d8cf  call    cs:__imp_LsapDbLookupNameChainRequest
0x18001d8d5  mov     edi, eax
0x18001d8d7  cmp     [rbx], rsi
0x18001d8da  jz      short loc_18001D8E8
0x18001d8dc  mov     rax, [rbp+37h+arg_38]
0x18001d8e0  mov     byte ptr [r15], 1
0x18001d8e4  mov     eax, [rax]
0x18001d8e6  jmp     short loc_18001D8EA
0x18001d8e8  xor     eax, eax
0x18001d8ea  mov     [r13+0], eax
0x18001d8ee  test    edi, edi
0x18001d8f0  jns     loc_18001DA61
0x18001d8f6  lea     eax, [rdi+3FFFFE74h]
0x18001d8fc  cmp     eax, 1
0x18001d8ff  jbe     short loc_18001D90D
0x18001d901  cmp     edi, 0C00002B0h
0x18001d907  jnz     loc_18001DA0C
0x18001d90d  mov     [r12], edi
0x18001d911  jmp     loc_18001DA0C
0x18001d916  lea     rcx, [rbp+37h+PerformanceCount]; lpPerformanceCount
0x18001d91a  mov     [rbp+37h+arg_40], r14d
0x18001d921  call    cs:__imp_QueryPerformanceCounter
0x18001d927  test    eax, eax
0x18001d929  jnz     short loc_18001D92F
0x18001d92b  mov     qword ptr [rbp+37h+PerformanceCount], rbx
0x18001d92f  mov     rbx, [rbp+37h+arg_28]
0x18001d933  lea     rdi, [r14+r14*2]
0x18001d937  shl     rdi, 3
0x18001d93b  mov     rcx, [rbx+8]
0x18001d93f  test    rcx, rcx
0x18001d942  jnz     short loc_18001D96B
0x18001d944  mov     rdx, rdi; uBytes
0x18001d947  mov     ecx, 40h ; '@'; uFlags
0x18001d94c  call    cs:__imp_LocalAlloc
0x18001d952  mov     [rbx+8], rax
0x18001d956  mov     rcx, rax; void *
0x18001d959  test    rax, rax
0x18001d95c  jnz     short loc_18001D968
0x18001d95e  mov     edi, 0C000009Ah
0x18001d963  jmp     loc_18001DA70
0x18001d968  mov     [rbx], r14d
0x18001d96b  mov     r8, rdi; Size
0x18001d96e  xor     edx, edx; Val
0x18001d970  call    memset_0
0x18001d975  xor     edx, edx
0x18001d977  test    r14d, r14d
0x18001d97a  jz      short loc_18001D99E
0x18001d97c  mov     rax, [rbx+8]
0x18001d980  lea     rcx, [rdx+rdx*2]
0x18001d984  inc     edx
0x18001d986  mov     dword ptr [rax+rcx*8], 8
0x18001d98d  mov     rax, [rbx+8]
0x18001d991  mov     dword ptr [rax+rcx*8+10h], 0FFFFFFFFh
0x18001d999  cmp     edx, r14d
0x18001d99c  jb      short loc_18001D97C
0x18001d99e  mov     rsi, [rbp+37h+arg_20]
0x18001d9a2  cmp     qword ptr [rsi], 0
0x18001d9a6  jnz     short loc_18001D9BD
0x18001d9a8  xor     edx, edx
0x18001d9aa  mov     rcx, rsi
0x18001d9ad  call    cs:__imp_LsapDbLookupCreateListReferencedDomains
0x18001d9b3  mov     edi, eax
0x18001d9b5  test    eax, eax
0x18001d9b7  js      loc_18001DA70
0x18001d9bd  mov     r9, [rbp+37h+arg_18]
0x18001d9c1  lea     rax, [rbp+37h+var_80]
0x18001d9c5  mov     r8, [rbp+37h+arg_10]
0x18001d9c9  mov     rdx, r13
0x18001d9cc  mov     [rsp+48h], rax
0x18001d9d1  mov     ecx, r14d
0x18001d9d4  lea     rax, [rbp+37h+arg_40]
0x18001d9db  mov     [rsp+0D0h+var_90], rax
0x18001d9e0  mov     rax, [rbp+37h+arg_38]
0x18001d9e4  mov     [rsp+0D0h+var_98], rax
0x18001d9e9  mov     rax, [rsi]
0x18001d9ec  mov     [rsp+0D0h+var_A8], rbx
0x18001d9f1  mov     [rsp+0D0h+var_B0], rax
0x18001d9f6  call    ?LsaDbpLookupXForestNamesBuildWorkList@@YAJKPEAU_LSAPR_UNICODE_STRING@@00PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_SIDS_EX2@@W4_LSAP_LOOKUP_LEVEL@@PEAK4PEAPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupXForestNamesBuildWorkList(ulong,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_UNICODE_STRING *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_SIDS_EX2 *,_LSAP_LOOKUP_LEVEL,ulong *,ulong *,_LSAP_DB_LOOKUP_WORK_LIST * *)
0x18001d9fb  mov     rsi, [rbp+37h+var_80]
0x18001d9ff  mov     edi, eax
0x18001da01  test    eax, eax
0x18001da03  jns     short loc_18001DA10
0x18001da05  cmp     eax, 0C0000073h
0x18001da0a  jnz     short loc_18001DA61
0x18001da0c  xor     edi, edi
0x18001da0e  jmp     short loc_18001DA61
0x18001da10  mov     edx, [rsi+38h]
0x18001da13  mov     ecx, 10h
0x18001da18  call    cs:__imp_?LsaLookupPerfCounterAddAmount@@YAXKK@Z; LsaLookupPerfCounterAddAmount(ulong,ulong)
0x18001da1e  mov     rdx, r12; int *
0x18001da21  mov     rcx, rsi; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x18001da24  call    ?LsaDbpLookupProcessWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@PEAJ@Z; LsaDbpLookupProcessWorkList(_LSAP_DB_LOOKUP_WORK_LIST *,long *)
0x18001da29  cmp     qword ptr [rbp+37h+PerformanceCount], 0
0x18001da2e  mov     edi, eax
0x18001da30  jz      short loc_18001DA61
0x18001da32  lea     rcx, [rbp+37h+var_70]; lpPerformanceCount
0x18001da36  call    cs:__imp_QueryPerformanceCounter
0x18001da3c  test    eax, eax
0x18001da3e  jz      short loc_18001DA61
0x18001da40  mov     rdx, qword ptr [rbp+37h+var_70]
0x18001da44  mov     ecx, 11h
0x18001da49  sub     rdx, qword ptr [rbp+37h+PerformanceCount]
0x18001da4d  call    cs:__imp_?LsaLookupPerfCounterAddLargeAmount@@YAXK_K@Z; LsaLookupPerfCounterAddLargeAmount(ulong,unsigned __int64)
0x18001da53  mov     edx, [rsi+38h]
0x18001da56  mov     ecx, 12h
0x18001da5b  call    cs:__imp_?LsaLookupPerfCounterAddAmount@@YAXKK@Z; LsaLookupPerfCounterAddAmount(ulong,ulong)
0x18001da61  test    rsi, rsi
0x18001da64  jz      short loc_18001DA70
0x18001da66  mov     rcx, rsi; hMem
0x18001da69  call    ?LsaDbpLookupDeleteWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupDeleteWorkList(_LSAP_DB_LOOKUP_WORK_LIST *)
0x18001da6e  mov     edi, eax
0x18001da70  mov     rbx, [rsp+0D0h+arg_0]
0x18001da78  mov     eax, edi
0x18001da7a  add     rsp, 0A0h
0x18001da81  pop     r15
0x18001da83  pop     r14
0x18001da85  pop     r13
0x18001da87  pop     r12
0x18001da89  pop     rdi
0x18001da8a  pop     rsi
0x18001da8b  pop     rbp
0x18001da8c  retn
```
