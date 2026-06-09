# LsaDbpLookupSidsInTrustedForestsWorker(ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST * *,_LSAPR_TRANSLATED_NAMES_EX *,uchar *,ulong *,long *)

- ea: `0x18001edf4`
- end: `0x18001f052`
- name: `?LsaDbpLookupSidsInTrustedForestsWorker@@YAJKPEAPEAU_LSAPR_SID@@PEAPEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@PEAEPEAKPEAJ@Z`
- size: `606`
- prototype: `__int64 __fastcall(unsigned int, struct _LSAPR_SID **, struct _LSAPR_REFERENCED_DOMAIN_LIST **, struct _LSAPR_TRANSLATED_NAMES_EX *, unsigned __int8 *, unsigned int *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x18001e968`
- `0x18001f060`

## callees

- `0x180001fb8`
- `0x18001b214`
- `0x18001b8dc`
- `0x18001be28`
- `0x18001edf4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ef27`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ef27`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ef03`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f002`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ef03`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f002`
- `LSASRV!LsaDbLookupSidChainRequest` at `0x18001eeb4`
- `LSASRV!LsaDbLookupSidChainRequest` at `0x18001eeb4`
- `LSASRV!LsapDbLookupCreateListReferencedDomains` at `0x18001ef86`
- `LSASRV!LsapDbLookupCreateListReferencedDomains` at `0x18001ef86`
- `LSASRV!LsapDbLookupGetDomainInfo` at `0x18001ee60`
- `LSASRV!LsapDbLookupGetDomainInfo` at `0x18001ee60`
- `LSASRV!LsaLookupPerfCounterAddLargeAmount` at `0x18001f019`
- `LSASRV!LsaLookupPerfCounterAddLargeAmount` at `0x18001f019`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001efe4`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001f027`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001efe4`
- `LSASRV!LsaLookupPerfCounterAddAmount` at `0x18001f027`

## pseudocode

```c
__int64 __fastcall LsaDbpLookupSidsInTrustedForestsWorker(
        unsigned int a1,
        struct _LSAPR_SID **a2,
        struct _LSAPR_REFERENCED_DOMAIN_LIST **a3,
        struct _LSAPR_TRANSLATED_NAMES_EX *a4,
        unsigned __int8 *a5,
        unsigned int *a6,
        int *a7)
{
  int *v7; // rdi
  bool v8; // zf
  unsigned __int8 *v10; // r13
  __int64 v12; // r15
  struct _LSAP_DB_LOOKUP_WORK_LIST *v13; // rsi
  int DomainInfo; // edi
  unsigned int *v15; // rax
  unsigned int v16; // eax
  HLOCAL v17; // rax
  unsigned int i; // edx
  __int64 v19; // rcx
  int v20; // eax
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-51h] BYREF
  struct _LSAP_DB_LOOKUP_WORK_LIST *v23; // [rsp+48h] [rbp-49h]
  LARGE_INTEGER v24; // [rsp+50h] [rbp-41h] BYREF
  __int128 v25; // [rsp+58h] [rbp-39h] BYREF
  __int128 v26; // [rsp+68h] [rbp-29h]
  __int128 v27; // [rsp+78h] [rbp-19h]

  v7 = a7;
  v8 = DcInRootDomain == 0;
  v10 = a5;
  v12 = a1;
  v13 = 0;
  *a7 = 0;
  v23 = 0;
  *v10 = 0;
  PerformanceCount.QuadPart = 0;
  v24.QuadPart = 0;
  if ( v8 )
  {
    a5 = 0;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    DomainInfo = LsapDbLookupGetDomainInfo(0, &a5, 0);
    if ( DomainInfo < 0 )
      return (unsigned int)DomainInfo;
    v25 = 0;
    v26 = 0;
    v27 = 0;
    v25 = *((_OWORD *)a5 + 2);
    DomainInfo = LsaDbLookupSidChainRequest(&v25, (unsigned int)v12, a2, a3, (char *)a4 + 8, 5, a6);
    if ( *((_QWORD *)a4 + 1) )
    {
      v15 = a6;
      *v10 = 1;
      v16 = *v15;
    }
    else
    {
      v16 = 0;
    }
    *(_DWORD *)a4 = v16;
    if ( DomainInfo < 0 )
    {
      if ( (unsigned int)(DomainInfo + 1073741428) <= 1 || DomainInfo == -1073741136 )
        *a7 = DomainInfo;
      DomainInfo = 0;
    }
  }
  else
  {
    LODWORD(a5) = a1;
    if ( !QueryPerformanceCounter(&PerformanceCount) )
      PerformanceCount.QuadPart = 0;
    v17 = (HLOCAL)*((_QWORD *)a4 + 1);
    if ( !v17 )
    {
      v17 = LocalAlloc(0x40u, 32 * v12);
      *((_QWORD *)a4 + 1) = v17;
      if ( !v17 )
        return (unsigned int)-1073741670;
      *(_DWORD *)a4 = v12;
    }
    memset_0(v17, 0, 32 * v12);
    for ( i = 0; i < (unsigned int)v12; *(_DWORD *)(*((_QWORD *)a4 + 1) + v19 + 24) = -1 )
    {
      v19 = i++;
      v19 *= 32;
      *(_DWORD *)(v19 + *((_QWORD *)a4 + 1)) = 8;
    }
    if ( !*a3 )
    {
      DomainInfo = LsapDbLookupCreateListReferencedDomains(a3, 0);
      if ( DomainInfo < 0 )
        return (unsigned int)DomainInfo;
      v7 = a7;
    }
    v20 = LsaDbpLookupXForestSidsBuildWorkList((unsigned int)v12, a2, *a3, a4);
    v13 = v23;
    if ( v20 >= 0 )
    {
      LsaLookupPerfCounterAddAmount(0x25u, *((_DWORD *)v23 + 14));
      DomainInfo = LsaDbpLookupProcessWorkList(v13, v7);
      if ( PerformanceCount.QuadPart && QueryPerformanceCounter(&v24) )
      {
        LsaLookupPerfCounterAddLargeAmount(0x26u, v24.QuadPart - PerformanceCount.QuadPart);
        LsaLookupPerfCounterAddAmount(0x27u, *((_DWORD *)v13 + 14));
      }
    }
    else
    {
      DomainInfo = 0;
      if ( v20 != -1073741709 )
        DomainInfo = v20;
    }
  }
  if ( v13 )
    return (unsigned int)LsaDbpLookupDeleteWorkList(v13);
  return (unsigned int)DomainInfo;
}

```

## disassembly

```asm
0x18001edf4  mov     [rsp-8+arg_8], rdx
0x18001edf9  push    rbp
0x18001edfa  push    rbx
0x18001edfb  push    rsi
0x18001edfc  push    rdi
0x18001edfd  push    r12
0x18001edff  push    r13
0x18001ee01  push    r14
0x18001ee03  push    r15
0x18001ee05  lea     rbp, [rsp-7]
0x18001ee0a  sub     rsp, 98h
0x18001ee11  mov     rdi, [rbp+3Fh+arg_30]
0x18001ee15  xor     ebx, ebx
0x18001ee17  cmp     cs:?DcInRootDomain@@3EA, bl; uchar DcInRootDomain
0x18001ee1d  mov     r14, r9
0x18001ee20  mov     r13, [rbp+3Fh+arg_20]
0x18001ee24  mov     r12, r8
0x18001ee27  mov     r15d, ecx
0x18001ee2a  mov     esi, ebx
0x18001ee2c  mov     [rdi], ebx
0x18001ee2e  mov     [rbp+3Fh+var_88], rbx
0x18001ee32  mov     [r13+0], bl
0x18001ee36  mov     qword ptr [rbp+3Fh+PerformanceCount], rbx
0x18001ee3a  mov     qword ptr [rbp+3Fh+var_80], rbx
0x18001ee3e  jnz     loc_18001EEFB
0x18001ee44  xorps   xmm0, xmm0
0x18001ee47  mov     [rbp+3Fh+arg_20], rbx
0x18001ee4b  xor     r8d, r8d
0x18001ee4e  lea     rdx, [rbp+3Fh+arg_20]
0x18001ee52  xor     ecx, ecx
0x18001ee54  movups  [rbp+3Fh+var_78], xmm0
0x18001ee58  movups  [rbp+3Fh+var_68], xmm0
0x18001ee5c  movups  [rbp+3Fh+var_58], xmm0
0x18001ee60  call    cs:__imp_LsapDbLookupGetDomainInfo
0x18001ee66  mov     edi, eax
0x18001ee68  test    eax, eax
0x18001ee6a  js      loc_18001F03C
0x18001ee70  mov     rax, [rbp+3Fh+arg_20]
0x18001ee74  lea     rbx, [r14+8]
0x18001ee78  mov     r8, [rbp+3Fh+arg_8]
0x18001ee7c  lea     rcx, [rbp+3Fh+var_78]
0x18001ee80  xorps   xmm0, xmm0
0x18001ee83  mov     r9, r12
0x18001ee86  movups  [rbp+3Fh+var_78], xmm0
0x18001ee8a  mov     edx, r15d
0x18001ee8d  movups  [rbp+3Fh+var_68], xmm0
0x18001ee91  movups  [rbp+3Fh+var_58], xmm0
0x18001ee95  movups  xmm0, xmmword ptr [rax+20h]
0x18001ee99  mov     rax, [rbp+3Fh+arg_28]
0x18001ee9d  mov     [rsp+0D0h+var_A0], rax
0x18001eea2  mov     dword ptr [rsp+0D0h+var_A8], 5
0x18001eeaa  mov     [rsp+0D0h+var_B0], rbx
0x18001eeaf  movdqu  [rbp+3Fh+var_78], xmm0
0x18001eeb4  call    cs:__imp_LsaDbLookupSidChainRequest
0x18001eeba  mov     edi, eax
0x18001eebc  cmp     [rbx], rsi
0x18001eebf  jz      short loc_18001EECE
0x18001eec1  mov     rax, [rbp+3Fh+arg_28]
0x18001eec5  mov     byte ptr [r13+0], 1
0x18001eeca  mov     eax, [rax]
0x18001eecc  jmp     short loc_18001EED0
0x18001eece  xor     eax, eax
0x18001eed0  mov     [r14], eax
0x18001eed3  test    edi, edi
0x18001eed5  jns     loc_18001F02D
0x18001eedb  lea     eax, [rdi+3FFFFE74h]
0x18001eee1  cmp     eax, 1
0x18001eee4  jbe     short loc_18001EEEE
0x18001eee6  cmp     edi, 0C00002B0h
0x18001eeec  jnz     short loc_18001EEF4
0x18001eeee  mov     rax, [rbp+3Fh+arg_30]
0x18001eef2  mov     [rax], edi
0x18001eef4  xor     edi, edi
0x18001eef6  jmp     loc_18001F02D
0x18001eefb  lea     rcx, [rbp+3Fh+PerformanceCount]; lpPerformanceCount
0x18001eeff  mov     dword ptr [rbp+3Fh+arg_20], r15d
0x18001ef03  call    cs:__imp_QueryPerformanceCounter
0x18001ef09  test    eax, eax
0x18001ef0b  jnz     short loc_18001EF11
0x18001ef0d  mov     qword ptr [rbp+3Fh+PerformanceCount], rbx
0x18001ef11  mov     rax, [r14+8]
0x18001ef15  mov     rbx, r15
0x18001ef18  shl     rbx, 5
0x18001ef1c  test    rax, rax
0x18001ef1f  jnz     short loc_18001EF43
0x18001ef21  mov     rdx, rbx; uBytes
0x18001ef24  lea     ecx, [rax+40h]; uFlags
0x18001ef27  call    cs:__imp_LocalAlloc
0x18001ef2d  mov     [r14+8], rax
0x18001ef31  test    rax, rax
0x18001ef34  jnz     short loc_18001EF40
0x18001ef36  mov     edi, 0C000009Ah
0x18001ef3b  jmp     loc_18001F03C
0x18001ef40  mov     [r14], r15d
0x18001ef43  mov     r8, rbx; Size
0x18001ef46  xor     edx, edx; Val
0x18001ef48  mov     rcx, rax; void *
0x18001ef4b  call    memset_0
0x18001ef50  xor     edx, edx
0x18001ef52  test    r15d, r15d
0x18001ef55  jz      short loc_18001EF7B
0x18001ef57  mov     rax, [r14+8]
0x18001ef5b  mov     ecx, edx
0x18001ef5d  inc     edx
0x18001ef5f  shl     rcx, 5
0x18001ef63  mov     dword ptr [rcx+rax], 8
0x18001ef6a  mov     rax, [r14+8]
0x18001ef6e  mov     dword ptr [rax+rcx+18h], 0FFFFFFFFh
0x18001ef76  cmp     edx, r15d
0x18001ef79  jb      short loc_18001EF57
0x18001ef7b  cmp     [r12], rsi
0x18001ef7f  jnz     short loc_18001EF9A
0x18001ef81  xor     edx, edx
0x18001ef83  mov     rcx, r12
0x18001ef86  call    cs:__imp_LsapDbLookupCreateListReferencedDomains
0x18001ef8c  mov     edi, eax
0x18001ef8e  test    eax, eax
0x18001ef90  js      loc_18001F03C
0x18001ef96  mov     rdi, [rbp+3Fh+arg_30]
0x18001ef9a  mov     r8, [r12]
0x18001ef9e  lea     rax, [rbp+3Fh+var_88]
0x18001efa2  mov     rdx, [rbp+3Fh+arg_8]
0x18001efa6  mov     r9, r14
0x18001efa9  mov     [rsp+0D0h+var_98], rax
0x18001efae  mov     ecx, r15d
0x18001efb1  lea     rax, [rbp+3Fh+arg_20]
0x18001efb5  mov     [rsp+0D0h+var_A0], rax
0x18001efba  mov     rax, [rbp+3Fh+arg_28]
0x18001efbe  mov     [rsp+0D0h+var_A8], rax
0x18001efc3  call    ?LsaDbpLookupXForestSidsBuildWorkList@@YAJKPEAPEAU_LSAPR_SID@@PEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@W4_LSAP_LOOKUP_LEVEL@@PEAK4PEAPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupXForestSidsBuildWorkList(ulong,_LSAPR_SID * *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_NAMES_EX *,_LSAP_LOOKUP_LEVEL,ulong *,ulong *,_LSAP_DB_LOOKUP_WORK_LIST * *)
0x18001efc8  mov     rsi, [rbp+3Fh+var_88]
0x18001efcc  test    eax, eax
0x18001efce  jns     short loc_18001EFDC
0x18001efd0  xor     edi, edi
0x18001efd2  cmp     eax, 0C0000073h
0x18001efd7  cmovnz  edi, eax
0x18001efda  jmp     short loc_18001F02D
0x18001efdc  mov     edx, [rsi+38h]
0x18001efdf  mov     ecx, 25h ; '%'
0x18001efe4  call    cs:__imp_?LsaLookupPerfCounterAddAmount@@YAXKK@Z; LsaLookupPerfCounterAddAmount(ulong,ulong)
0x18001efea  mov     rdx, rdi; int *
0x18001efed  mov     rcx, rsi; struct _LSAP_DB_LOOKUP_WORK_LIST *
0x18001eff0  call    ?LsaDbpLookupProcessWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@PEAJ@Z; LsaDbpLookupProcessWorkList(_LSAP_DB_LOOKUP_WORK_LIST *,long *)
0x18001eff5  cmp     qword ptr [rbp+3Fh+PerformanceCount], 0
0x18001effa  mov     edi, eax
0x18001effc  jz      short loc_18001F02D
0x18001effe  lea     rcx, [rbp+3Fh+var_80]; lpPerformanceCount
0x18001f002  call    cs:__imp_QueryPerformanceCounter
0x18001f008  test    eax, eax
0x18001f00a  jz      short loc_18001F02D
0x18001f00c  mov     rdx, qword ptr [rbp+3Fh+var_80]
0x18001f010  mov     ecx, 26h ; '&'
0x18001f015  sub     rdx, qword ptr [rbp+3Fh+PerformanceCount]
0x18001f019  call    cs:__imp_?LsaLookupPerfCounterAddLargeAmount@@YAXK_K@Z; LsaLookupPerfCounterAddLargeAmount(ulong,unsigned __int64)
0x18001f01f  mov     edx, [rsi+38h]
0x18001f022  mov     ecx, 27h ; '''
0x18001f027  call    cs:__imp_?LsaLookupPerfCounterAddAmount@@YAXKK@Z; LsaLookupPerfCounterAddAmount(ulong,ulong)
0x18001f02d  test    rsi, rsi
0x18001f030  jz      short loc_18001F03C
0x18001f032  mov     rcx, rsi; hMem
0x18001f035  call    ?LsaDbpLookupDeleteWorkList@@YAJPEAU_LSAP_DB_LOOKUP_WORK_LIST@@@Z; LsaDbpLookupDeleteWorkList(_LSAP_DB_LOOKUP_WORK_LIST *)
0x18001f03a  mov     edi, eax
0x18001f03c  mov     eax, edi
0x18001f03e  add     rsp, 98h
0x18001f045  pop     r15
0x18001f047  pop     r14
0x18001f049  pop     r13
0x18001f04b  pop     r12
0x18001f04d  pop     rdi
0x18001f04e  pop     rsi
0x18001f04f  pop     rbx
0x18001f050  pop     rbp
0x18001f051  retn
```
