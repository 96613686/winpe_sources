# NlCreateDomainPhase1(ushort *,ushort *,void *,_GUID *,ushort *,ushort *,uchar,ulong,_DOMAIN_INFO * *)

- ea: `0x180024f08`
- end: `0x180025455`
- name: `?NlCreateDomainPhase1@@YAKPEAG0PEAXPEAU_GUID@@00EKPEAPEAU_DOMAIN_INFO@@@Z`
- size: `1357`
- prototype: `__int64 __fastcall(WCHAR *SourceString, WCHAR *lpWideCharStr, void *Src, struct _GUID *Buf1, unsigned __int16 *lpWideCharStra, unsigned __int16 *lpSrcStr, char, unsigned int, struct _DOMAIN_INFO **)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180026c90`
- `0x180028384`

## callees

- `0x180003670`
- `0x180007278`
- `0x180007b50`
- `0x18000ba1c`
- `0x18001606c`
- `0x1800160a0`
- `0x180024adc`
- `0x180024f08`
- `0x180025698`
- `0x180025708`
- `0x180025e34`
- `0x180026180`
- `0x180027114`
- `0x180027498`
- `0x180029020`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18002512f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18002512f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025020`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025020`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025012`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025012`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18002527c`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18002527c`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x1800252bb`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x1800252bb`
- `ntdll!RtlLeaveCriticalSection` at `0x1800251ae`
- `ntdll!RtlLeaveCriticalSection` at `0x18002543c`
- `ntdll!RtlLeaveCriticalSection` at `0x1800251ae`
- `ntdll!RtlLeaveCriticalSection` at `0x18002543c`
- `ntdll!RtlAcquireResourceExclusive` at `0x180025256`
- `ntdll!RtlAcquireResourceExclusive` at `0x180025256`
- `ntdll!RtlInitializeCriticalSection` at `0x180025105`
- `ntdll!RtlInitializeCriticalSection` at `0x180025112`
- `ntdll!RtlInitializeCriticalSection` at `0x180025105`
- `ntdll!RtlInitializeCriticalSection` at `0x180025112`
- `ntdll!RtlEnterCriticalSection` at `0x180024f4a`
- `ntdll!RtlEnterCriticalSection` at `0x1800251dd`
- `ntdll!RtlEnterCriticalSection` at `0x180024f4a`
- `ntdll!RtlEnterCriticalSection` at `0x1800251dd`
- `ntdll!RtlInitUnicodeString` at `0x1800250b4`
- `ntdll!RtlInitUnicodeString` at `0x1800250b4`
- `ntdll!RtlLengthSid` at `0x180024f73`
- `ntdll!RtlLengthSid` at `0x180024f73`
- `ntdll!RtlReleaseResource` at `0x180025290`
- `ntdll!RtlReleaseResource` at `0x180025290`
- `SAMSRV!SamIConnect` at `0x1800252f5`
- `SAMSRV!SamIConnect` at `0x1800252f5`
- `SAMSRV!SamrOpenDomain` at `0x180025327`
- `SAMSRV!SamrOpenDomain` at `0x180025353`
- `SAMSRV!SamrOpenDomain` at `0x180025327`
- `SAMSRV!SamrOpenDomain` at `0x180025353`

## string_xrefs

- `0x180025158`: `%ws: Cannot set ComputerName\n`
- `0x1800252c7`: `%ws: Can't LsaIOpenPolicyTrusted: 0x%lx.\n`
- `0x180025333`: `%ws: ACCOUNT: Cannot SamrOpenDomain: %lx\n`
- `0x18002535f`: `%ws: BUILTIN: Cannot SamrOpenDomain: %lx\n`

## pseudocode

```c
__int64 __fastcall NlCreateDomainPhase1(
        WCHAR *SourceString,
        WCHAR *lpWideCharStr,
        void *Src,
        struct _GUID *Buf1,
        unsigned __int16 *lpWideCharStra,
        unsigned __int16 *lpSrcStr,
        char a7,
        unsigned int a8,
        struct _DOMAIN_INFO **a9)
{
  ULONG v13; // r15d
  WCHAR *v14; // r8
  struct _DOMAIN_INFO *NetbiosDomain; // rdi
  const char *Utf8StrFromWStr; // rax
  const char *v17; // rbx
  DWORD LastError; // ebx
  struct _DOMAIN_INFO *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  void *v23; // rbx
  const WCHAR *v24; // rbx
  NTSTATUS v25; // ebx
  __int64 v26; // r9
  _QWORD *v27; // r14
  _QWORD *v28; // r15
  DWORD v29; // eax
  int v30; // eax
  struct _DOMAIN_INFO **v31; // rax
  struct _DOMAIN_INFO **v32; // rax
  void *v34; // [rsp+90h] [rbp+8h] BYREF

  LODWORD(v34) = 0;
  v13 = 0;
  NetpULongRoundUp(0x290u, 4u, (unsigned int *)&v34);
  RtlEnterCriticalSection(&NlGlobalDomainCritSect);
  v14 = SourceString;
  if ( !SourceString )
    v14 = lpWideCharStr;
  NlPrintRoutine(0x400u, L"%ws: Adding new domain\n", v14);
  if ( Src )
    v13 = RtlLengthSid(Src);
  if ( SourceString )
  {
    NetbiosDomain = NlFindNetbiosDomain(SourceString, 0);
  }
  else
  {
    if ( !lpWideCharStr )
      goto LABEL_14;
    Utf8StrFromWStr = NetpCreateUtf8StrFromWStr(lpWideCharStr, 0, 0);
    v17 = Utf8StrFromWStr;
    if ( !Utf8StrFromWStr )
    {
      LastError = 8;
      if ( a7 )
        NlExit(3054, 8, 1);
      goto LABEL_69;
    }
    NetbiosDomain = NlFindDnsDomain(Utf8StrFromWStr, Buf1, 1u, 0, 0);
    NetpMemoryFree(v17);
  }
  if ( NetbiosDomain )
  {
    *((_DWORD *)NetbiosDomain + 148) &= ~0x800u;
LABEL_67:
    LastError = 0;
    goto LABEL_68;
  }
LABEL_14:
  v19 = (struct _DOMAIN_INFO *)LocalAlloc(0x40u, v13 + (unsigned int)v34);
  NetbiosDomain = v19;
  if ( !v19 )
  {
    LastError = GetLastError();
    if ( !a7 )
      goto LABEL_57;
    v20 = 8;
    v21 = 3054;
    goto LABEL_56;
  }
  ++NlGlobalServicedDomainCount;
  *((_DWORD *)v19 + 146) = 1;
  *((_DWORD *)v19 + 148) |= a8;
  v22 = *((_DWORD *)v19 + 148);
  if ( (v22 & 0x1000) != 0 )
    NlGlobalDomainInfo = NetbiosDomain;
  if ( NlGlobalMemberWorkstation )
  {
    *((_DWORD *)NetbiosDomain + 147) = 3;
  }
  else if ( (v22 & 0x4000) != 0 )
  {
    *((_DWORD *)NetbiosDomain + 147) = 4;
  }
  else if ( (v22 & 0x2000) != 0 )
  {
    *((_DWORD *)NetbiosDomain + 147) = 0;
  }
  RtlInitUnicodeString((PUNICODE_STRING)NetbiosDomain + 16, 0);
  *((_QWORD *)NetbiosDomain + 1) = NetbiosDomain;
  *((_QWORD *)NetbiosDomain + 57) = (char *)NetbiosDomain + 448;
  *((_QWORD *)NetbiosDomain + 56) = (char *)NetbiosDomain + 448;
  *((_QWORD *)NetbiosDomain + 72) = (char *)NetbiosDomain + 568;
  *((_QWORD *)NetbiosDomain + 71) = (char *)NetbiosDomain + 568;
  *((_QWORD *)NetbiosDomain + 81) = (char *)NetbiosDomain + 640;
  *((_QWORD *)NetbiosDomain + 80) = (char *)NetbiosDomain + 640;
  *((_QWORD *)NetbiosDomain + 4) = NlDomainThread;
  *(_QWORD *)NetbiosDomain = NetbiosDomain;
  *((_QWORD *)NetbiosDomain + 5) = NetbiosDomain;
  *((_BYTE *)NetbiosDomain + 48) = 0;
  RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)NetbiosDomain + 10);
  RtlInitializeCriticalSection((PRTL_CRITICAL_SECTION)((char *)NetbiosDomain + 504));
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl) )
    InitializeSRWLock((PSRWLOCK)NetbiosDomain + 75);
  if ( lpWideCharStra )
  {
    LastError = NlSetComputerName(NetbiosDomain, lpWideCharStra, lpSrcStr);
    if ( LastError )
    {
      NlPrintRoutine(0x100u, L"%ws: Cannot set ComputerName\n", SourceString);
      goto LABEL_34;
    }
  }
  v34 = (char *)NetbiosDomain + 656;
  NetpULongPtrRoundUp((unsigned __int64)NetbiosDomain + 656, 4, (unsigned __int64 *)&v34);
  if ( Src )
  {
    v23 = v34;
    memcpy_0(v34, Src, v13);
    *((_QWORD *)NetbiosDomain + 23) = v23;
  }
  RtlLeaveCriticalSection(&NlGlobalDomainCritSect);
  LastError = NlSetDomainNameInDomainInfo(NetbiosDomain, lpWideCharStr, SourceString, Buf1, 0, 0, 0);
  RtlEnterCriticalSection(&NlGlobalDomainCritSect);
  if ( LastError )
  {
    NlPrintRoutine(0x100u, L"%ws: Cannot set DnsDomainName\n", SourceString);
LABEL_34:
    if ( a7 )
      NlExit(5737, LastError, 3);
LABEL_59:
    NlDeleteDomain(NetbiosDomain);
    NlDereferenceDomain(NetbiosDomain);
    goto LABEL_69;
  }
  if ( hDataSource_PerfCntr_1 )
  {
    if ( lpWideCharStr )
    {
      v24 = (const WCHAR *)*((_QWORD *)NetbiosDomain + 18);
    }
    else
    {
      v24 = (const WCHAR *)((char *)NetbiosDomain + 72);
      if ( !SourceString )
        v24 = L"Unknown Domain";
    }
    RtlAcquireResourceExclusive(&NlPcGlobalLock, 1u);
    *((_QWORD *)NetbiosDomain + 44) = PerfCreateInstance(
                                        hDataSource_PerfCntr_1,
                                        &CtrSet_PerfCntr_1_1Guid,
                                        v24,
                                        _InterlockedIncrement((volatile signed __int32 *)&NlPcGlobalInstanceNumber));
    RtlReleaseResource(&NlPcGlobalLock);
  }
  else
  {
    *((_QWORD *)NetbiosDomain + 44) = 0;
  }
  if ( (*((_DWORD *)NetbiosDomain + 148) & 0x2000) == 0 )
    goto LABEL_60;
  v25 = LsaIOpenPolicyTrusted((char *)NetbiosDomain + 392);
  if ( v25 < 0 )
  {
    NlPrintRoutine(0x100u, L"%ws: Can't LsaIOpenPolicyTrusted: 0x%lx.\n", SourceString, (unsigned int)v25);
    goto LABEL_54;
  }
  v27 = (_QWORD *)((char *)NetbiosDomain + 368);
  LOBYTE(v26) = 1;
  v25 = SamIConnect(0, (char *)NetbiosDomain + 368, 0, v26);
  if ( v25 >= 0 )
  {
    v28 = (_QWORD *)((char *)NetbiosDomain + 376);
    v25 = SamrOpenDomain(*v27, 985087, *((_QWORD *)NetbiosDomain + 23), (char *)NetbiosDomain + 376);
    if ( v25 < 0 )
    {
      NlPrintRoutine(0x100u, L"%ws: ACCOUNT: Cannot SamrOpenDomain: %lx\n", SourceString, (unsigned int)v25);
LABEL_53:
      *v28 = 0;
      goto LABEL_54;
    }
    v28 = (_QWORD *)((char *)NetbiosDomain + 384);
    v25 = SamrOpenDomain(*v27, 985087, BuiltinDomainSid, (char *)NetbiosDomain + 384);
    if ( v25 < 0 )
    {
      NlPrintRoutine(0x100u, L"%ws: BUILTIN: Cannot SamrOpenDomain: %lx\n", SourceString, (unsigned int)v25);
      goto LABEL_53;
    }
LABEL_60:
    ++*((_DWORD *)NetbiosDomain + 146);
    v30 = *((_DWORD *)NetbiosDomain + 148);
    if ( (v30 & 0x2000) != 0 )
    {
      v31 = (struct _DOMAIN_INFO **)qword_1800F1EF8;
      if ( *(struct _LIST_ENTRY **)qword_1800F1EF8 == &NlGlobalServicedDomains )
      {
        *(_QWORD *)NetbiosDomain = &NlGlobalServicedDomains;
        *((_QWORD *)NetbiosDomain + 1) = v31;
        *v31 = NetbiosDomain;
        qword_1800F1EF8 = (__int64)NetbiosDomain;
        goto LABEL_67;
      }
    }
    else
    {
      if ( (v30 & 0x4000) == 0 )
        goto LABEL_67;
      v32 = (struct _DOMAIN_INFO **)qword_1800F1EE8;
      if ( *(struct _DOMAIN_INFO ***)qword_1800F1EE8 == &NlGlobalServicedNdncs )
      {
        *(_QWORD *)NetbiosDomain = &NlGlobalServicedNdncs;
        *((_QWORD *)NetbiosDomain + 1) = v32;
        *v32 = NetbiosDomain;
        qword_1800F1EE8 = (__int64)NetbiosDomain;
        goto LABEL_67;
      }
    }
    __fastfail(3u);
  }
  NlPrintRoutine(0x100u, L"%ws: Can't SamIConnect: 0x%lx.\n", SourceString, (unsigned int)v25);
LABEL_54:
  v29 = NetpNtStatusToApiStatus(v25);
  LastError = v29;
  if ( !a7 )
    goto LABEL_57;
  v21 = 5602;
  v20 = v29;
LABEL_56:
  NlExit(v21, v20, 1);
LABEL_57:
  if ( !LastError )
  {
LABEL_68:
    *a9 = NetbiosDomain;
    goto LABEL_69;
  }
  if ( NetbiosDomain )
    goto LABEL_59;
LABEL_69:
  RtlLeaveCriticalSection(&NlGlobalDomainCritSect);
  return LastError;
}

```

## disassembly

```asm
0x180024f08  mov     rax, rsp
0x180024f0b  push    rbx
0x180024f0c  push    rbp
0x180024f0d  push    rsi
0x180024f0e  push    rdi
0x180024f0f  push    r12
0x180024f11  push    r13
0x180024f13  push    r14
0x180024f15  push    r15
0x180024f17  sub     rsp, 48h
0x180024f1b  xor     r13d, r13d
0x180024f1e  mov     rbp, rdx
0x180024f21  mov     rsi, rcx
0x180024f24  mov     [rax+8], r13d
0x180024f28  mov     r14, r8
0x180024f2b  mov     ecx, 290h; unsigned int
0x180024f30  lea     r8, [rax+8]; unsigned int *
0x180024f34  mov     r12, r9
0x180024f37  lea     edx, [r13+4]; unsigned int
0x180024f3b  mov     r15d, r13d
0x180024f3e  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x180024f43  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180024f4a  call    cs:__imp_RtlEnterCriticalSection
0x180024f50  test    rsi, rsi
0x180024f53  lea     rdx, aWsAddingNewDom; "%ws: Adding new domain\n"
0x180024f5a  mov     r8, rsi
0x180024f5d  mov     ecx, 400h; unsigned int
0x180024f62  cmovz   r8, rbp
0x180024f66  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180024f6b  test    r14, r14
0x180024f6e  jz      short loc_180024F7C
0x180024f70  mov     rcx, r14; Sid
0x180024f73  call    cs:__imp_RtlLengthSid
0x180024f79  mov     r15d, eax
0x180024f7c  test    rsi, rsi
0x180024f7f  jz      short loc_180024F90
0x180024f81  xor     edx, edx; unsigned __int8
0x180024f83  mov     rcx, rsi; SourceString
0x180024f86  call    ?NlFindNetbiosDomain@@YAPEAU_DOMAIN_INFO@@PEBGE@Z; NlFindNetbiosDomain(ushort const *,uchar)
0x180024f8b  mov     rdi, rax
0x180024f8e  jmp     short loc_180024FF1
0x180024f90  test    rbp, rbp
0x180024f93  jz      short loc_180025003
0x180024f95  xor     r8d, r8d; int
0x180024f98  xor     edx, edx; lpMultiByteStr
0x180024f9a  mov     rcx, rbp; lpWideCharStr
0x180024f9d  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x180024fa2  mov     rbx, rax
0x180024fa5  test    rax, rax
0x180024fa8  jnz     short loc_180024FD0
0x180024faa  lea     edx, [rax+8]
0x180024fad  mov     ebx, edx
0x180024faf  cmp     [rsp+88h+arg_30], r13b
0x180024fb7  jz      loc_180025435
0x180024fbd  mov     ecx, 0BEEh
0x180024fc2  lea     r8d, [rax+1]
0x180024fc6  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x180024fcb  jmp     loc_180025435
0x180024fd0  xor     r9d, r9d; unsigned __int8
0x180024fd3  mov     [rsp+88h+var_68], r13; unsigned __int8 *
0x180024fd8  mov     r8b, 1; unsigned __int8
0x180024fdb  mov     rdx, r12; Buf1
0x180024fde  mov     rcx, rbx; char *
0x180024fe1  call    ?NlFindDnsDomain@@YAPEAU_DOMAIN_INFO@@PEBDPEAU_GUID@@EEPEAE@Z; NlFindDnsDomain(char const *,_GUID *,uchar,uchar,uchar *)
0x180024fe6  mov     rcx, rbx
0x180024fe9  mov     rdi, rax
0x180024fec  call    NetpMemoryFree
0x180024ff1  test    rdi, rdi
0x180024ff4  jz      short loc_180025003
0x180024ff6  btr     dword ptr [rdi+250h], 0Bh
0x180024ffe  jmp     loc_180025427
0x180025003  mov     edx, dword ptr [rsp+88h+arg_0]
0x18002500a  mov     ecx, 40h ; '@'; uFlags
0x18002500f  add     edx, r15d; uBytes
0x180025012  call    cs:__imp_LocalAlloc
0x180025018  mov     rdi, rax
0x18002501b  test    rax, rax
0x18002501e  jnz     short loc_180025047
0x180025020  call    cs:__imp_GetLastError
0x180025026  mov     ebx, eax
0x180025028  cmp     [rsp+88h+arg_30], r13b
0x180025030  jz      loc_18002539B
0x180025036  lea     edx, [rdi+8]
0x180025039  mov     ecx, 0BEEh
0x18002503e  lea     r8d, [rdi+1]
0x180025042  jmp     loc_180025396
0x180025047  inc     cs:?NlGlobalServicedDomainCount@@3KA; ulong NlGlobalServicedDomainCount
0x18002504d  mov     dword ptr [rax+248h], 1
0x180025057  mov     eax, [rsp+88h+arg_38]
0x18002505e  or      [rdi+250h], eax
0x180025064  mov     eax, [rdi+250h]
0x18002506a  bt      eax, 0Ch
0x18002506e  jnb     short loc_180025077
0x180025070  mov     cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA, rdi; _DOMAIN_INFO * NlGlobalDomainInfo
0x180025077  cmp     cs:?NlGlobalMemberWorkstation@@3HA, r13d; int NlGlobalMemberWorkstation
0x18002507e  jz      short loc_18002508C
0x180025080  mov     dword ptr [rdi+24Ch], 3
0x18002508a  jmp     short loc_1800250AB
0x18002508c  bt      eax, 0Eh
0x180025090  jnb     short loc_18002509E
0x180025092  mov     dword ptr [rdi+24Ch], 4
0x18002509c  jmp     short loc_1800250AB
0x18002509e  bt      eax, 0Dh
0x1800250a2  jnb     short loc_1800250AB
0x1800250a4  mov     [rdi+24Ch], r13d
0x1800250ab  lea     rcx, [rdi+100h]; DestinationString
0x1800250b2  xor     edx, edx; SourceString
0x1800250b4  call    cs:__imp_RtlInitUnicodeString
0x1800250ba  lea     rax, [rdi+1C0h]
0x1800250c1  mov     [rdi+8], rdi
0x1800250c5  mov     [rax+8], rax
0x1800250c9  lea     rcx, [rdi+190h]; CriticalSection
0x1800250d0  mov     [rax], rax
0x1800250d3  lea     rax, [rdi+238h]
0x1800250da  mov     [rax+8], rax
0x1800250de  mov     [rax], rax
0x1800250e1  lea     rax, [rdi+280h]
0x1800250e8  mov     [rax+8], rax
0x1800250ec  mov     [rax], rax
0x1800250ef  lea     rax, ?NlDomainThread@@YAXPEAX@Z; NlDomainThread(void *)
0x1800250f6  mov     [rdi+20h], rax
0x1800250fa  mov     [rdi], rdi
0x1800250fd  mov     [rdi+28h], rdi
0x180025101  mov     [rdi+30h], r13b
0x180025105  call    cs:__imp_RtlInitializeCriticalSection
0x18002510b  lea     rcx, [rdi+1F8h]; CriticalSection
0x180025112  call    cs:__imp_RtlInitializeCriticalSection
0x180025118  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl(void)'::`2'::impl
0x18002511f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(void)
0x180025124  test    al, al
0x180025126  jz      short loc_180025135
0x180025128  lea     rcx, [rdi+258h]; SRWLock
0x18002512f  call    cs:__imp_InitializeSRWLock
0x180025135  mov     rdx, [rsp+88h+lpWideCharStr]; lpWideCharStr
0x18002513d  test    rdx, rdx
0x180025140  jz      short loc_180025164
0x180025142  mov     r8, [rsp+88h+lpSrcStr]; lpSrcStr
0x18002514a  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18002514d  call    ?NlSetComputerName@@YAKPEAU_DOMAIN_INFO@@PEAG1@Z; NlSetComputerName(_DOMAIN_INFO *,ushort *,ushort *)
0x180025152  mov     ebx, eax
0x180025154  test    eax, eax
0x180025156  jz      short loc_180025164
0x180025158  lea     rdx, aWsCannotSetCom; "%ws: Cannot set ComputerName\n"
0x18002515f  jmp     loc_1800251EE
0x180025164  lea     rcx, [rdi+290h]; unsigned __int64
0x18002516b  mov     edx, 4; unsigned __int64
0x180025170  lea     r8, [rsp+88h+arg_0]; unsigned __int64 *
0x180025178  mov     [rsp+88h+arg_0], rcx
0x180025180  call    ?NetpULongPtrRoundUp@@YAJ_K0PEA_K@Z; NetpULongPtrRoundUp(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180025185  test    r14, r14
0x180025188  jz      short loc_1800251A7
0x18002518a  mov     rbx, [rsp+88h+arg_0]
0x180025192  mov     rdx, r14; Src
0x180025195  mov     rcx, rbx; void *
0x180025198  mov     r8d, r15d; Size
0x18002519b  call    memcpy_0
0x1800251a0  mov     [rdi+0B8h], rbx
0x1800251a7  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800251ae  call    cs:__imp_RtlLeaveCriticalSection
0x1800251b4  mov     [rsp+88h+var_58], r13; unsigned __int8 *
0x1800251b9  mov     r9, r12; struct _GUID *
0x1800251bc  mov     [rsp+88h+var_60], r13; unsigned __int8 *
0x1800251c1  mov     r8, rsi; unsigned __int16 *
0x1800251c4  mov     rdx, rbp; unsigned __int16 *
0x1800251c7  mov     [rsp+88h+var_68], r13; unsigned __int8 *
0x1800251cc  mov     rcx, rdi; struct _DOMAIN_INFO *
0x1800251cf  call    ?NlSetDomainNameInDomainInfo@@YAKPEAU_DOMAIN_INFO@@PEAG1PEAU_GUID@@PEAE33@Z; NlSetDomainNameInDomainInfo(_DOMAIN_INFO *,ushort *,ushort *,_GUID *,uchar *,uchar *,uchar *)
0x1800251d4  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800251db  mov     ebx, eax
0x1800251dd  call    cs:__imp_RtlEnterCriticalSection
0x1800251e3  test    ebx, ebx
0x1800251e5  jz      short loc_180025220
0x1800251e7  lea     rdx, aWsCannotSetDns; "%ws: Cannot set DnsDomainName\n"
0x1800251ee  mov     r8, rsi
0x1800251f1  mov     ecx, 100h; unsigned int
0x1800251f6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800251fb  cmp     [rsp+88h+arg_30], r13b
0x180025203  jz      loc_1800253AC
0x180025209  mov     r8d, 3
0x18002520f  mov     edx, ebx
0x180025211  mov     ecx, 1669h
0x180025216  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x18002521b  jmp     loc_1800253AC
0x180025220  cmp     cs:hDataSource_PerfCntr_1, r13
0x180025227  jz      short loc_180025298
0x180025229  test    rbp, rbp
0x18002522c  jz      short loc_180025237
0x18002522e  mov     rbx, [rdi+90h]
0x180025235  jmp     short loc_180025247
0x180025237  lea     rbx, [rdi+48h]
0x18002523b  test    rsi, rsi
0x18002523e  jnz     short loc_180025247
0x180025240  lea     rbx, aUnknownDomain; "Unknown Domain"
0x180025247  mov     ebp, 1
0x18002524c  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x180025253  mov     dl, bpl; Wait
0x180025256  call    cs:__imp_RtlAcquireResourceExclusive
0x18002525c  mov     r9d, ebp
0x18002525f  lock xadd cs:?NlPcGlobalInstanceNumber@@3KA, r9d; ulong NlPcGlobalInstanceNumber
0x180025268  mov     rcx, cs:hDataSource_PerfCntr_1; ProviderHandle
0x18002526f  lea     rdx, CtrSet_PerfCntr_1_1Guid; CounterSetGuid
0x180025276  add     r9d, ebp; Id
0x180025279  mov     r8, rbx; Name
0x18002527c  call    cs:__imp_PerfCreateInstance
0x180025282  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x180025289  mov     [rdi+160h], rax
0x180025290  call    cs:__imp_RtlReleaseResource
0x180025296  jmp     short loc_1800252A4
0x180025298  mov     [rdi+160h], r13
0x18002529f  mov     ebp, 1
0x1800252a4  test    dword ptr [rdi+250h], 2000h
0x1800252ae  jz      loc_1800253BE
0x1800252b4  lea     rcx, [rdi+188h]
0x1800252bb  call    cs:__imp_LsaIOpenPolicyTrusted
0x1800252c1  mov     ebx, eax
0x1800252c3  test    eax, eax
0x1800252c5  jns     short loc_1800252E3
0x1800252c7  lea     rdx, aWsCanTLsaiopen; "%ws: Can't LsaIOpenPolicyTrusted: 0x%lx"...
0x1800252ce  mov     r8, rsi
0x1800252d1  mov     r9d, ebx
0x1800252d4  mov     ecx, 100h; unsigned int
0x1800252d9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800252de  jmp     loc_180025379
0x1800252e3  lea     r14, [rdi+170h]
0x1800252ea  mov     r9b, bpl
0x1800252ed  mov     rdx, r14
0x1800252f0  xor     r8d, r8d
0x1800252f3  xor     ecx, ecx
0x1800252f5  call    cs:__imp_SamIConnect
0x1800252fb  mov     ebx, eax
0x1800252fd  test    eax, eax
0x1800252ff  jns     short loc_18002530A
0x180025301  lea     rdx, aWsCanTSamiconn; "%ws: Can't SamIConnect: 0x%lx.\n"
0x180025308  jmp     short loc_1800252CE
0x18002530a  mov     r8, [rdi+0B8h]
0x180025311  lea     r15, [rdi+178h]
0x180025318  mov     rcx, [r14]
0x18002531b  mov     r12d, 0F07FFh
0x180025321  mov     r9, r15
0x180025324  mov     edx, r12d
0x180025327  call    cs:__imp_SamrOpenDomain
0x18002532d  mov     ebx, eax
0x18002532f  test    eax, eax
0x180025331  jns     short loc_18002533C
0x180025333  lea     rdx, aWsAccountCanno; "%ws: ACCOUNT: Cannot SamrOpenDomain: %l"...
0x18002533a  jmp     short loc_180025366
0x18002533c  mov     r8, cs:BuiltinDomainSid
0x180025343  lea     r15, [rdi+180h]
0x18002534a  mov     rcx, [r14]
0x18002534d  mov     r9, r15
0x180025350  mov     edx, r12d
0x180025353  call    cs:__imp_SamrOpenDomain
0x180025359  mov     ebx, eax
0x18002535b  test    eax, eax
0x18002535d  jns     short loc_1800253BE
0x18002535f  lea     rdx, aWsBuiltinCanno; "%ws: BUILTIN: Cannot SamrOpenDomain: %l"...
0x180025366  mov     r9d, ebx
0x180025369  mov     r8, rsi
0x18002536c  mov     ecx, 100h; unsigned int
0x180025371  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180025376  mov     [r15], r13
0x180025379  mov     ecx, ebx; Status
0x18002537b  call    NetpNtStatusToApiStatus
0x180025380  mov     ebx, eax
0x180025382  cmp     [rsp+88h+arg_30], r13b
0x18002538a  jz      short loc_18002539B
0x18002538c  mov     ecx, 15E2h
0x180025391  mov     edx, eax
0x180025393  mov     r8d, ebp
0x180025396  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x18002539b  test    ebx, ebx
0x18002539d  jz      loc_18002542A
0x1800253a3  test    rdi, rdi
0x1800253a6  jz      loc_180025435
0x1800253ac  mov     rcx, rdi; struct _DOMAIN_INFO *
0x1800253af  call    ?NlDeleteDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDeleteDomain(_DOMAIN_INFO *)
0x1800253b4  mov     rcx, rdi; struct _DOMAIN_INFO *
0x1800253b7  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x1800253bc  jmp     short loc_180025435
0x1800253be  add     [rdi+248h], ebp
0x1800253c4  mov     eax, [rdi+250h]
0x1800253ca  bt      eax, 0Dh
0x1800253ce  jnb     short loc_1800253F6
0x1800253d0  mov     rax, cs:qword_1800F1EF8
0x1800253d7  lea     rcx, ?NlGlobalServicedDomains@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalServicedDomains
0x1800253de  cmp     [rax], rcx
0x1800253e1  jnz     short loc_18002540F
0x1800253e3  mov     [rdi], rcx
0x1800253e6  mov     [rdi+8], rax
0x1800253ea  mov     [rax], rdi
0x1800253ed  mov     cs:qword_1800F1EF8, rdi
0x1800253f4  jmp     short loc_180025427
0x1800253f6  bt      eax, 0Eh
0x1800253fa  jnb     short loc_180025427
0x1800253fc  mov     rax, cs:qword_1800F1EE8
0x180025403  lea     rcx, ?NlGlobalServicedNdncs@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalServicedNdncs
0x18002540a  cmp     [rax], rcx
0x18002540d  jz      short loc_180025416
0x18002540f  mov     ecx, 3
0x180025414  int     29h; Win8: RtlFailFast(ecx)
  ... truncated ...
```
