# NlCreateDomainPhase1(ushort *,ushort *,void *,_GUID *,ushort *,ushort *,uchar,ulong,_DOMAIN_INFO * *)

- ea: `0x180025f54`
- end: `0x180026512`
- name: `?NlCreateDomainPhase1@@YAKPEAG0PEAXPEAU_GUID@@00EKPEAPEAU_DOMAIN_INFO@@@Z`
- size: `1470`
- prototype: `unsigned int __fastcall(PCWSTR SourceString, LPCWCH lpWideCharStr, void *Src, struct _GUID *Buf1, unsigned __int16 *, unsigned __int16 *, char, unsigned int, struct _DOMAIN_INFO **)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180027fa4`
- `0x180029858`

## callees

- `0x1800037f0`
- `0x180007518`
- `0x180007e90`
- `0x18000c130`
- `0x180016a70`
- `0x180016aa4`
- `0x180025a74`
- `0x180025f54`
- `0x180026774`
- `0x1800267ec`
- `0x180026fdc`
- `0x180027350`
- `0x1800284a4`
- `0x180028860`
- `0x18002a6f4`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800261a5`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800261a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002607e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002607e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002606a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002606a`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18002630e`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x18002630e`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x180026359`
- `LSASRV!LsaIOpenPolicyTrusted` at `0x180026359`
- `ntdll!RtlLeaveCriticalSection` at `0x18002622a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800264f2`
- `ntdll!RtlLeaveCriticalSection` at `0x18002622a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800264f2`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800262e2`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800262e2`
- `ntdll!RtlInitializeCriticalSection` at `0x18002616f`
- `ntdll!RtlInitializeCriticalSection` at `0x180026182`
- `ntdll!RtlInitializeCriticalSection` at `0x18002616f`
- `ntdll!RtlInitializeCriticalSection` at `0x180026182`
- `ntdll!RtlEnterCriticalSection` at `0x180025f96`
- `ntdll!RtlEnterCriticalSection` at `0x18002625f`
- `ntdll!RtlEnterCriticalSection` at `0x180025f96`
- `ntdll!RtlEnterCriticalSection` at `0x18002625f`
- `ntdll!RtlInitUnicodeString` at `0x180026118`
- `ntdll!RtlInitUnicodeString` at `0x180026118`
- `ntdll!RtlLengthSid` at `0x180025fc5`
- `ntdll!RtlLengthSid` at `0x180025fc5`
- `ntdll!RtlReleaseResource` at `0x180026328`
- `ntdll!RtlReleaseResource` at `0x180026328`
- `SAMSRV!SamIConnect` at `0x180026399`
- `SAMSRV!SamIConnect` at `0x180026399`
- `SAMSRV!SamrOpenDomain` at `0x1800263d1`
- `SAMSRV!SamrOpenDomain` at `0x180026403`
- `SAMSRV!SamrOpenDomain` at `0x1800263d1`
- `SAMSRV!SamrOpenDomain` at `0x180026403`

## string_xrefs

- `0x1800261d4`: `%ws: Cannot set ComputerName\n`
- `0x18002636b`: `%ws: Can't LsaIOpenPolicyTrusted: 0x%lx.\n`
- `0x1800263e3`: `%ws: ACCOUNT: Cannot SamrOpenDomain: %lx\n`
- `0x180026415`: `%ws: BUILTIN: Cannot SamrOpenDomain: %lx\n`

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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl'::`2'::impl) )
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
  NetpULongPtrRoundUp((unsigned __int64)NetbiosDomain + 656, 4u, (unsigned __int64 *)&v34);
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
      v31 = (struct _DOMAIN_INFO **)qword_1800F8EB0;
      if ( *(struct _LIST_ENTRY **)qword_1800F8EB0 == &NlGlobalServicedDomains )
      {
        *(_QWORD *)NetbiosDomain = &NlGlobalServicedDomains;
        *((_QWORD *)NetbiosDomain + 1) = v31;
        *v31 = NetbiosDomain;
        qword_1800F8EB0 = (__int64)NetbiosDomain;
        goto LABEL_67;
      }
    }
    else
    {
      if ( (v30 & 0x4000) == 0 )
        goto LABEL_67;
      v32 = (struct _DOMAIN_INFO **)qword_1800F8EA0;
      if ( *(struct _DOMAIN_INFO ***)qword_1800F8EA0 == &NlGlobalServicedNdncs )
      {
        *(_QWORD *)NetbiosDomain = &NlGlobalServicedNdncs;
        *((_QWORD *)NetbiosDomain + 1) = v32;
        *v32 = NetbiosDomain;
        qword_1800F8EA0 = (__int64)NetbiosDomain;
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
0x180025f54  mov     rax, rsp
0x180025f57  push    rbx
0x180025f58  push    rbp
0x180025f59  push    rsi
0x180025f5a  push    rdi
0x180025f5b  push    r12
0x180025f5d  push    r13
0x180025f5f  push    r14
0x180025f61  push    r15
0x180025f63  sub     rsp, 48h
0x180025f67  xor     r13d, r13d
0x180025f6a  mov     rbp, rdx
0x180025f6d  mov     rsi, rcx
0x180025f70  mov     [rax+8], r13d
0x180025f74  mov     r14, r8
0x180025f77  mov     ecx, 290h; unsigned int
0x180025f7c  lea     r8, [rax+8]; unsigned int *
0x180025f80  mov     r12, r9
0x180025f83  lea     edx, [r13+4]; unsigned int
0x180025f87  mov     r15d, r13d
0x180025f8a  call    ?NetpULongRoundUp@@YAJKKPEAK@Z; NetpULongRoundUp(ulong,ulong,ulong *)
0x180025f8f  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180025f96  call    cs:__imp_RtlEnterCriticalSection
0x180025f9d  nop     dword ptr [rax+rax+00h]
0x180025fa2  test    rsi, rsi
0x180025fa5  lea     rdx, aWsAddingNewDom; "%ws: Adding new domain\n"
0x180025fac  mov     r8, rsi
0x180025faf  mov     ecx, 400h; unsigned int
0x180025fb4  cmovz   r8, rbp
0x180025fb8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180025fbd  test    r14, r14
0x180025fc0  jz      short loc_180025FD4
0x180025fc2  mov     rcx, r14; Sid
0x180025fc5  call    cs:__imp_RtlLengthSid
0x180025fcc  nop     dword ptr [rax+rax+00h]
0x180025fd1  mov     r15d, eax
0x180025fd4  test    rsi, rsi
0x180025fd7  jz      short loc_180025FE8
0x180025fd9  xor     edx, edx; unsigned __int8
0x180025fdb  mov     rcx, rsi; SourceString
0x180025fde  call    ?NlFindNetbiosDomain@@YAPEAU_DOMAIN_INFO@@PEBGE@Z; NlFindNetbiosDomain(ushort const *,uchar)
0x180025fe3  mov     rdi, rax
0x180025fe6  jmp     short loc_180026049
0x180025fe8  test    rbp, rbp
0x180025feb  jz      short loc_18002605B
0x180025fed  xor     r8d, r8d; int
0x180025ff0  xor     edx, edx; lpMultiByteStr
0x180025ff2  mov     rcx, rbp; lpWideCharStr
0x180025ff5  call    ?NetpCreateUtf8StrFromWStr@@YAPEADPEBGPEADH@Z; NetpCreateUtf8StrFromWStr(ushort const *,char *,int)
0x180025ffa  mov     rbx, rax
0x180025ffd  test    rax, rax
0x180026000  jnz     short loc_180026028
0x180026002  lea     edx, [rax+8]
0x180026005  mov     ebx, edx
0x180026007  cmp     [rsp+88h+arg_30], r13b
0x18002600f  jz      loc_1800264EB
0x180026015  mov     ecx, 0BEEh
0x18002601a  lea     r8d, [rax+1]
0x18002601e  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x180026023  jmp     loc_1800264EB
0x180026028  xor     r9d, r9d; unsigned __int8
0x18002602b  mov     [rsp+88h+var_68], r13; unsigned __int8 *
0x180026030  mov     r8b, 1; unsigned __int8
0x180026033  mov     rdx, r12; Buf1
0x180026036  mov     rcx, rbx; char *
0x180026039  call    ?NlFindDnsDomain@@YAPEAU_DOMAIN_INFO@@PEBDPEAU_GUID@@EEPEAE@Z; NlFindDnsDomain(char const *,_GUID *,uchar,uchar,uchar *)
0x18002603e  mov     rcx, rbx
0x180026041  mov     rdi, rax
0x180026044  call    NetpMemoryFree
0x180026049  test    rdi, rdi
0x18002604c  jz      short loc_18002605B
0x18002604e  btr     dword ptr [rdi+250h], 0Bh
0x180026056  jmp     loc_1800264DD
0x18002605b  mov     edx, dword ptr [rsp+88h+arg_0]
0x180026062  mov     ecx, 40h ; '@'; uFlags
0x180026067  add     edx, r15d; uBytes
0x18002606a  call    cs:__imp_LocalAlloc
0x180026071  nop     dword ptr [rax+rax+00h]
0x180026076  mov     rdi, rax
0x180026079  test    rax, rax
0x18002607c  jnz     short loc_1800260AB
0x18002607e  call    cs:__imp_GetLastError
0x180026085  nop     dword ptr [rax+rax+00h]
0x18002608a  mov     ebx, eax
0x18002608c  cmp     [rsp+88h+arg_30], r13b
0x180026094  jz      loc_180026451
0x18002609a  lea     edx, [rdi+8]
0x18002609d  mov     ecx, 0BEEh
0x1800260a2  lea     r8d, [rdi+1]
0x1800260a6  jmp     loc_18002644C
0x1800260ab  inc     cs:?NlGlobalServicedDomainCount@@3KA; ulong NlGlobalServicedDomainCount
0x1800260b1  mov     dword ptr [rax+248h], 1
0x1800260bb  mov     eax, [rsp+88h+arg_38]
0x1800260c2  or      [rdi+250h], eax
0x1800260c8  mov     eax, [rdi+250h]
0x1800260ce  bt      eax, 0Ch
0x1800260d2  jnb     short loc_1800260DB
0x1800260d4  mov     cs:?NlGlobalDomainInfo@@3PEAU_DOMAIN_INFO@@EA, rdi; _DOMAIN_INFO * NlGlobalDomainInfo
0x1800260db  cmp     cs:?NlGlobalMemberWorkstation@@3HA, r13d; int NlGlobalMemberWorkstation
0x1800260e2  jz      short loc_1800260F0
0x1800260e4  mov     dword ptr [rdi+24Ch], 3
0x1800260ee  jmp     short loc_18002610F
0x1800260f0  bt      eax, 0Eh
0x1800260f4  jnb     short loc_180026102
0x1800260f6  mov     dword ptr [rdi+24Ch], 4
0x180026100  jmp     short loc_18002610F
0x180026102  bt      eax, 0Dh
0x180026106  jnb     short loc_18002610F
0x180026108  mov     [rdi+24Ch], r13d
0x18002610f  lea     rcx, [rdi+100h]; DestinationString
0x180026116  xor     edx, edx; SourceString
0x180026118  call    cs:__imp_RtlInitUnicodeString
0x18002611f  nop     dword ptr [rax+rax+00h]
0x180026124  lea     rax, [rdi+1C0h]
0x18002612b  mov     [rdi+8], rdi
0x18002612f  mov     [rax+8], rax
0x180026133  lea     rcx, [rdi+190h]; CriticalSection
0x18002613a  mov     [rax], rax
0x18002613d  lea     rax, [rdi+238h]
0x180026144  mov     [rax+8], rax
0x180026148  mov     [rax], rax
0x18002614b  lea     rax, [rdi+280h]
0x180026152  mov     [rax+8], rax
0x180026156  mov     [rax], rax
0x180026159  lea     rax, ?NlDomainThread@@YAXPEAX@Z; NlDomainThread(void *)
0x180026160  mov     [rdi+20h], rax
0x180026164  mov     [rdi], rdi
0x180026167  mov     [rdi+28h], rdi
0x18002616b  mov     [rdi+30h], r13b
0x18002616f  call    cs:__imp_RtlInitializeCriticalSection
0x180026176  nop     dword ptr [rax+rax+00h]
0x18002617b  lea     rcx, [rdi+1F8h]; CriticalSection
0x180026182  call    cs:__imp_RtlInitializeCriticalSection
0x180026189  nop     dword ptr [rax+rax+00h]
0x18002618e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::GetImpl(void)'::`2'::impl
0x180026195  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SiteSubnet_Improvements>::__private_IsEnabled(void)
0x18002619a  test    al, al
0x18002619c  jz      short loc_1800261B1
0x18002619e  lea     rcx, [rdi+258h]; SRWLock
0x1800261a5  call    cs:__imp_InitializeSRWLock
0x1800261ac  nop     dword ptr [rax+rax+00h]
0x1800261b1  mov     rdx, [rsp+88h+lpWideCharStr]; lpWideCharStr
0x1800261b9  test    rdx, rdx
0x1800261bc  jz      short loc_1800261E0
0x1800261be  mov     r8, [rsp+88h+lpSrcStr]; lpSrcStr
0x1800261c6  mov     rcx, rdi; struct _DOMAIN_INFO *
0x1800261c9  call    ?NlSetComputerName@@YAKPEAU_DOMAIN_INFO@@PEAG1@Z; NlSetComputerName(_DOMAIN_INFO *,ushort *,ushort *)
0x1800261ce  mov     ebx, eax
0x1800261d0  test    eax, eax
0x1800261d2  jz      short loc_1800261E0
0x1800261d4  lea     rdx, aWsCannotSetCom; "%ws: Cannot set ComputerName\n"
0x1800261db  jmp     loc_180026276
0x1800261e0  lea     rcx, [rdi+290h]; unsigned __int64
0x1800261e7  mov     edx, 4; unsigned __int64
0x1800261ec  lea     r8, [rsp+88h+arg_0]; unsigned __int64 *
0x1800261f4  mov     [rsp+88h+arg_0], rcx
0x1800261fc  call    ?NetpULongPtrRoundUp@@YAJ_K0PEA_K@Z; NetpULongPtrRoundUp(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180026201  test    r14, r14
0x180026204  jz      short loc_180026223
0x180026206  mov     rbx, [rsp+88h+arg_0]
0x18002620e  mov     rdx, r14; Src
0x180026211  mov     rcx, rbx; void *
0x180026214  mov     r8d, r15d; Size
0x180026217  call    memcpy_0
0x18002621c  mov     [rdi+0B8h], rbx
0x180026223  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18002622a  call    cs:__imp_RtlLeaveCriticalSection
0x180026231  nop     dword ptr [rax+rax+00h]
0x180026236  mov     [rsp+88h+var_58], r13; unsigned __int8 *
0x18002623b  mov     r9, r12; struct _GUID *
0x18002623e  mov     [rsp+88h+var_60], r13; unsigned __int8 *
0x180026243  mov     r8, rsi; unsigned __int16 *
0x180026246  mov     rdx, rbp; unsigned __int16 *
0x180026249  mov     [rsp+88h+var_68], r13; unsigned __int8 *
0x18002624e  mov     rcx, rdi; struct _DOMAIN_INFO *
0x180026251  call    ?NlSetDomainNameInDomainInfo@@YAKPEAU_DOMAIN_INFO@@PEAG1PEAU_GUID@@PEAE33@Z; NlSetDomainNameInDomainInfo(_DOMAIN_INFO *,ushort *,ushort *,_GUID *,uchar *,uchar *,uchar *)
0x180026256  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18002625d  mov     ebx, eax
0x18002625f  call    cs:__imp_RtlEnterCriticalSection
0x180026266  nop     dword ptr [rax+rax+00h]
0x18002626b  test    ebx, ebx
0x18002626d  jz      short loc_1800262A8
0x18002626f  lea     rdx, aWsCannotSetDns; "%ws: Cannot set DnsDomainName\n"
0x180026276  mov     r8, rsi
0x180026279  mov     ecx, 100h; unsigned int
0x18002627e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180026283  cmp     [rsp+88h+arg_30], r13b
0x18002628b  jz      loc_180026462
0x180026291  mov     r8d, 3
0x180026297  mov     edx, ebx
0x180026299  mov     ecx, 1669h
0x18002629e  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x1800262a3  jmp     loc_180026462
0x1800262a8  cmp     cs:hDataSource_PerfCntr_1, r13
0x1800262af  jz      loc_180026336
0x1800262b5  test    rbp, rbp
0x1800262b8  jz      short loc_1800262C3
0x1800262ba  mov     rbx, [rdi+90h]
0x1800262c1  jmp     short loc_1800262D3
0x1800262c3  lea     rbx, [rdi+48h]
0x1800262c7  test    rsi, rsi
0x1800262ca  jnz     short loc_1800262D3
0x1800262cc  lea     rbx, aUnknownDomain; "Unknown Domain"
0x1800262d3  mov     ebp, 1
0x1800262d8  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x1800262df  mov     dl, bpl; Wait
0x1800262e2  call    cs:__imp_RtlAcquireResourceExclusive
0x1800262e9  nop     dword ptr [rax+rax+00h]
0x1800262ee  mov     r9d, ebp
0x1800262f1  lock xadd cs:?NlPcGlobalInstanceNumber@@3KA, r9d; ulong NlPcGlobalInstanceNumber
0x1800262fa  mov     rcx, cs:hDataSource_PerfCntr_1; ProviderHandle
0x180026301  lea     rdx, CtrSet_PerfCntr_1_1Guid; CounterSetGuid
0x180026308  add     r9d, ebp; Id
0x18002630b  mov     r8, rbx; Name
0x18002630e  call    cs:__imp_PerfCreateInstance
0x180026315  nop     dword ptr [rax+rax+00h]
0x18002631a  lea     rcx, ?NlPcGlobalLock@@3U_SAFE_RESOURCE@@A; Resource
0x180026321  mov     [rdi+160h], rax
0x180026328  call    cs:__imp_RtlReleaseResource
0x18002632f  nop     dword ptr [rax+rax+00h]
0x180026334  jmp     short loc_180026342
0x180026336  mov     [rdi+160h], r13
0x18002633d  mov     ebp, 1
0x180026342  test    dword ptr [rdi+250h], 2000h
0x18002634c  jz      loc_180026474
0x180026352  lea     rcx, [rdi+188h]
0x180026359  call    cs:__imp_LsaIOpenPolicyTrusted
0x180026360  nop     dword ptr [rax+rax+00h]
0x180026365  mov     ebx, eax
0x180026367  test    eax, eax
0x180026369  jns     short loc_180026387
0x18002636b  lea     rdx, aWsCanTLsaiopen; "%ws: Can't LsaIOpenPolicyTrusted: 0x%lx"...
0x180026372  mov     r8, rsi
0x180026375  mov     r9d, ebx
0x180026378  mov     ecx, 100h; unsigned int
0x18002637d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180026382  jmp     loc_18002642F
0x180026387  lea     r14, [rdi+170h]
0x18002638e  mov     r9b, bpl
0x180026391  mov     rdx, r14
0x180026394  xor     r8d, r8d
0x180026397  xor     ecx, ecx
0x180026399  call    cs:__imp_SamIConnect
0x1800263a0  nop     dword ptr [rax+rax+00h]
0x1800263a5  mov     ebx, eax
0x1800263a7  test    eax, eax
0x1800263a9  jns     short loc_1800263B4
0x1800263ab  lea     rdx, aWsCanTSamiconn; "%ws: Can't SamIConnect: 0x%lx.\n"
0x1800263b2  jmp     short loc_180026372
0x1800263b4  mov     r8, [rdi+0B8h]
0x1800263bb  lea     r15, [rdi+178h]
0x1800263c2  mov     rcx, [r14]
0x1800263c5  mov     r12d, 0F07FFh
0x1800263cb  mov     r9, r15
0x1800263ce  mov     edx, r12d
0x1800263d1  call    cs:__imp_SamrOpenDomain
0x1800263d8  nop     dword ptr [rax+rax+00h]
0x1800263dd  mov     ebx, eax
0x1800263df  test    eax, eax
0x1800263e1  jns     short loc_1800263EC
0x1800263e3  lea     rdx, aWsAccountCanno; "%ws: ACCOUNT: Cannot SamrOpenDomain: %l"...
0x1800263ea  jmp     short loc_18002641C
0x1800263ec  mov     r8, cs:BuiltinDomainSid
0x1800263f3  lea     r15, [rdi+180h]
0x1800263fa  mov     rcx, [r14]
0x1800263fd  mov     r9, r15
0x180026400  mov     edx, r12d
0x180026403  call    cs:__imp_SamrOpenDomain
0x18002640a  nop     dword ptr [rax+rax+00h]
0x18002640f  mov     ebx, eax
0x180026411  test    eax, eax
0x180026413  jns     short loc_180026474
0x180026415  lea     rdx, aWsBuiltinCanno; "%ws: BUILTIN: Cannot SamrOpenDomain: %l"...
0x18002641c  mov     r9d, ebx
0x18002641f  mov     r8, rsi
0x180026422  mov     ecx, 100h; unsigned int
0x180026427  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002642c  mov     [r15], r13
0x18002642f  mov     ecx, ebx; Status
0x180026431  call    NetpNtStatusToApiStatus
0x180026436  mov     ebx, eax
0x180026438  cmp     [rsp+88h+arg_30], r13b
0x180026440  jz      short loc_180026451
0x180026442  mov     ecx, 15E2h
0x180026447  mov     edx, eax
0x180026449  mov     r8d, ebp
0x18002644c  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x180026451  test    ebx, ebx
0x180026453  jz      loc_1800264E0
0x180026459  test    rdi, rdi
0x18002645c  jz      loc_1800264EB
0x180026462  mov     rcx, rdi; struct _DOMAIN_INFO *
0x180026465  call    ?NlDeleteDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDeleteDomain(_DOMAIN_INFO *)
0x18002646a  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18002646d  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x180026472  jmp     short loc_1800264EB
0x180026474  add     [rdi+248h], ebp
0x18002647a  mov     eax, [rdi+250h]
0x180026480  bt      eax, 0Dh
0x180026484  jnb     short loc_1800264AC
  ... truncated ...
```
