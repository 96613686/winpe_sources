# NlInitializeDomains(void)

- ea: `0x180027fa4`
- end: `0x1800283e4`
- name: `?NlInitializeDomains@@YAKXZ`
- size: `1088`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800747cc`

## callees

- `0x180002cc0`
- `0x180003250`
- `0x180007e90`
- `0x18000dd00`
- `0x18000e910`
- `0x180025f54`
- `0x180026518`
- `0x1800267ec`
- `0x1800275e4`
- `0x180027748`
- `0x180027fa4`
- `0x180028f18`
- `0x180029858`
- `0x18002a6f4`
- `0x180041f80`
- `0x18006891c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028125`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028139`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002814d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028161`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028175`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028189`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028125`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028139`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002814d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028161`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028175`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028189`
- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x1800282e0`
- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x1800282e0`
- `ntdll!RtlLeaveCriticalSection` at `0x18002834f`
- `ntdll!RtlLeaveCriticalSection` at `0x180028372`
- `ntdll!RtlLeaveCriticalSection` at `0x18002834f`
- `ntdll!RtlLeaveCriticalSection` at `0x180028372`
- `ntdll!RtlInitializeCriticalSection` at `0x18002800a`
- `ntdll!RtlInitializeCriticalSection` at `0x18002800a`
- `ntdll!RtlEnterCriticalSection` at `0x18002828f`
- `ntdll!RtlEnterCriticalSection` at `0x18002828f`
- `ntdll!RtlEqualSid` at `0x180028220`
- `ntdll!RtlEqualSid` at `0x180028220`
- `ntdll!RtlLengthSid` at `0x180028257`
- `ntdll!RtlLengthSid` at `0x180028257`
- `netutils!NetApiBufferFree` at `0x180028111`
- `netutils!NetApiBufferFree` at `0x180028111`
- `SAMSRV!SamIQueryCapabilities` at `0x1800282bd`
- `SAMSRV!SamIQueryCapabilities` at `0x1800282bd`

## string_xrefs

- `0x1800282aa`: `onecore\ds\netapi\svcdlls\logonsrv\server\domain.cxx`

## pseudocode

```c
__int64 NlInitializeDomains(void)
{
  unsigned __int16 *v0; // r12
  WCHAR *v1; // rdi
  WCHAR *v2; // r14
  PSID v3; // rsi
  PSID v4; // r15
  struct _GUID *v5; // r13
  unsigned int ComputerNameEx2; // eax
  unsigned int DomainPhase2; // ebx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned int DomainName; // eax
  unsigned int DnsHostName; // eax
  unsigned int v14; // eax
  struct _DOMAIN_INFO *v15; // rdi
  ULONG v16; // eax
  char *v17; // r9
  char v18; // al
  int v19; // ebx
  char v20; // al
  HLOCAL ClientSession; // rax
  struct _RTL_CRITICAL_SECTION *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r8
  NTSTATUS updated; // eax
  PCWSTR SourceString; // [rsp+50h] [rbp-49h] BYREF
  LPVOID Buffer; // [rsp+58h] [rbp-41h] BYREF
  PSID Sid2; // [rsp+60h] [rbp-39h] BYREF
  PSID Sid1; // [rsp+68h] [rbp-31h] BYREF
  struct _GUID *Buf1; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int16 *v32; // [rsp+78h] [rbp-21h] BYREF
  LPCWCH lpWideCharStr; // [rsp+80h] [rbp-19h] BYREF
  struct _DOMAIN_INFO *v34; // [rsp+88h] [rbp-11h] BYREF
  unsigned __int16 *v35[2]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v36; // [rsp+A0h] [rbp+7h]

  v0 = 0;
  v34 = 0;
  v1 = 0;
  v32 = 0;
  v2 = 0;
  SourceString = 0;
  v3 = 0;
  lpWideCharStr = 0;
  v4 = 0;
  Sid2 = 0;
  v5 = 0;
  Sid1 = 0;
  Buf1 = 0;
  Buffer = 0;
  RtlInitializeCriticalSection(&NlGlobalDomainCritSect);
  NlGlobalDomainsInitialized = 1;
  qword_1800F8EB0 = (__int64)&NlGlobalServicedDomains;
  NlGlobalServicedDomains.Flink = &NlGlobalServicedDomains;
  qword_1800F8EA0 = (__int64)&NlGlobalServicedNdncs;
  NlGlobalServicedNdncs = (struct _DOMAIN_INFO *)&NlGlobalServicedNdncs;
  ComputerNameEx2 = NetpGetComputerNameEx2(&Buffer, 0);
  DomainPhase2 = ComputerNameEx2;
  if ( ComputerNameEx2 )
  {
    v8 = 3;
    v9 = ComputerNameEx2;
    v10 = 5737;
LABEL_3:
    NlExit(v10, v9, v8);
    goto LABEL_12;
  }
  NlGlobalUnicodeComputerName = (unsigned __int16 *)NetpAllocWStrFromWStr(Buffer);
  if ( !NlGlobalUnicodeComputerName )
  {
    DomainPhase2 = 8;
    v10 = 3054;
    v9 = 8;
    v8 = 1;
    goto LABEL_3;
  }
  DomainName = NlGetDomainName((HLOCAL *)&SourceString, (LPVOID *)&lpWideCharStr, &Sid2, &Sid1, &Buf1, 0);
  v2 = (WCHAR *)lpWideCharStr;
  DomainPhase2 = DomainName;
  if ( DomainName )
    goto LABEL_10;
  if ( !lpWideCharStr )
  {
LABEL_28:
    v5 = Buf1;
    v3 = Sid2;
    v14 = NlCreateDomainPhase1((WCHAR *)SourceString, v2, Sid2, Buf1, (unsigned __int16 *)Buffer, v0, 1, 0x3000u, &v34);
    v4 = Sid1;
    DomainPhase2 = v14;
    v15 = v34;
    if ( v14 )
      goto LABEL_42;
    if ( NlGlobalMemberWorkstation )
    {
      if ( RtlEqualSid(Sid1, v3) )
      {
        *(_OWORD *)v35 = 0;
        v36 = 0;
        v35[0] = *((unsigned __int16 **)v15 + 33);
        v35[1] = (unsigned __int16 *)((char *)v15 + 72);
        v36 = 0;
        v16 = RtlLengthSid(v3);
        NlpWriteEventlog(0x158Cu, 1u, 0, v35, 2u, (unsigned __int8 *)v3, v16);
      }
      RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)v15 + 10);
      if ( *((_QWORD *)v15 + 61) )
        NlAssertFailed(
          "DomainInfo->DomClientSession == NULL",
          "onecore\\ds\\netapi\\svcdlls\\logonsrv\\server\\domain.cxx",
          0x568u,
          v17);
      v18 = SamIQueryCapabilities();
      if ( (v18 & 2) != 0 )
        v19 = 6;
      else
        v19 = (v18 & 1) != 0 ? 7 : 2;
      v20 = LsaIIsInEmulatedDomainJoinMode();
      ClientSession = NlAllocateClientSession(
                        v15,
                        (struct _UNICODE_STRING *)((char *)v15 + 56),
                        (struct _UNICODE_STRING *)v15 + 8,
                        v4,
                        *((struct _GUID **)v15 + 26),
                        (v20 != 0 ? 262160 : 16) | (*((_WORD *)v15 + 64) != 0 ? 4 : 0),
                        v19,
                        0);
      *((_QWORD *)v15 + 61) = ClientSession;
      v22 = (struct _RTL_CRITICAL_SECTION *)((char *)v15 + 400);
      if ( !ClientSession )
      {
        RtlLeaveCriticalSection(v22);
        DomainPhase2 = 8;
        v23 = 3054;
        v24 = 8;
        v25 = 1;
LABEL_39:
        NlExit(v23, v24, v25);
        goto LABEL_42;
      }
      RtlLeaveCriticalSection(v22);
    }
    else
    {
      DomainPhase2 = NlCreateDomainPhase2(v34, 1u);
      if ( DomainPhase2 || (DomainPhase2 = NlUpdateServicedNdncs((unsigned __int16 *)Buffer, v0, 1u, 0)) != 0 )
      {
LABEL_42:
        if ( v15 )
          NlDereferenceDomain(v15);
        goto LABEL_11;
      }
      updated = NlUpdateDnsRootAlias(v15, 0);
      if ( updated < 0 )
      {
        DomainPhase2 = NetpNtStatusToApiStatus(updated);
        v25 = 3;
        v24 = DomainPhase2;
        v23 = 5602;
        goto LABEL_39;
      }
    }
    DomainPhase2 = 0;
    goto LABEL_42;
  }
  DnsHostName = NlGetDnsHostName(&v32);
  DomainPhase2 = DnsHostName;
  if ( !DnsHostName )
  {
    v0 = v32;
    goto LABEL_28;
  }
  NlExit(5737, DnsHostName, 3);
  v0 = v32;
LABEL_10:
  v5 = Buf1;
  v4 = Sid1;
  v3 = Sid2;
LABEL_11:
  v1 = (WCHAR *)SourceString;
LABEL_12:
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( v0 )
    LocalFree(v0);
  if ( v1 )
    LocalFree(v1);
  if ( v2 )
    LocalFree(v2);
  if ( v3 )
    LocalFree(v3);
  if ( v4 )
    LocalFree(v4);
  if ( v5 )
    LocalFree(v5);
  return DomainPhase2;
}

```

## disassembly

```asm
0x180027fa4  push    rbp
0x180027fa6  push    rbx
0x180027fa7  push    rsi
0x180027fa8  push    rdi
0x180027fa9  push    r12
0x180027fab  push    r13
0x180027fad  push    r14
0x180027faf  push    r15
0x180027fb1  lea     rbp, [rsp-1Fh]
0x180027fb6  sub     rsp, 0B8h
0x180027fbd  mov     rax, cs:__security_cookie
0x180027fc4  xor     rax, rsp
0x180027fc7  mov     [rbp+57h+var_48], rax
0x180027fcb  xor     r12d, r12d
0x180027fce  mov     [rbp+57h+var_68], 0
0x180027fd6  xor     edi, edi
0x180027fd8  mov     [rbp+57h+var_78], r12
0x180027fdc  xor     r14d, r14d
0x180027fdf  mov     [rbp+57h+SourceString], rdi
0x180027fe3  xor     esi, esi
0x180027fe5  mov     [rbp+57h+lpWideCharStr], r14
0x180027fe9  xor     r15d, r15d
0x180027fec  mov     [rbp+57h+Sid2], rsi
0x180027ff0  xor     r13d, r13d
0x180027ff3  mov     [rbp+57h+Sid1], r15
0x180027ff7  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180027ffe  mov     [rbp+57h+Buf1], r13
0x180028002  mov     [rbp+57h+Buffer], 0
0x18002800a  call    cs:__imp_RtlInitializeCriticalSection
0x180028011  nop     dword ptr [rax+rax+00h]
0x180028016  lea     rax, ?NlGlobalServicedDomains@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalServicedDomains
0x18002801d  mov     cs:?NlGlobalDomainsInitialized@@3HA, 1; int NlGlobalDomainsInitialized
0x180028027  mov     cs:qword_1800F8EB0, rax
0x18002802e  lea     rcx, [rbp+57h+Buffer]
0x180028032  mov     cs:?NlGlobalServicedDomains@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalServicedDomains
0x180028039  xor     edx, edx
0x18002803b  lea     rax, ?NlGlobalServicedNdncs@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalServicedNdncs
0x180028042  mov     cs:qword_1800F8EA0, rax
0x180028049  mov     cs:?NlGlobalServicedNdncs@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalServicedNdncs
0x180028050  call    NetpGetComputerNameEx2
0x180028055  mov     ebx, eax
0x180028057  test    eax, eax
0x180028059  jz      short loc_180028071
0x18002805b  lea     r8d, [r12+3]
0x180028060  mov     edx, eax
0x180028062  mov     ecx, 1669h
0x180028067  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x18002806c  jmp     loc_180028105
0x180028071  mov     rcx, [rbp+57h+Buffer]; Src
0x180028075  call    NetpAllocWStrFromWStr
0x18002807a  mov     cs:?NlGlobalUnicodeComputerName@@3PEAGEA, rax; ushort * NlGlobalUnicodeComputerName
0x180028081  test    rax, rax
0x180028084  jnz     short loc_180028096
0x180028086  lea     ebx, [rax+8]
0x180028089  mov     ecx, 0BEEh
0x18002808e  mov     edx, ebx
0x180028090  lea     r8d, [rax+1]
0x180028094  jmp     short loc_180028067
0x180028096  lea     rax, [rbp+57h+Buf1]
0x18002809a  mov     [rsp+0F0h+var_C8], rsi; unsigned __int8 *
0x18002809f  lea     r9, [rbp+57h+Sid1]; void **
0x1800280a3  mov     [rsp+0F0h+var_D0], rax; struct _GUID **
0x1800280a8  lea     r8, [rbp+57h+Sid2]; void **
0x1800280ac  lea     rdx, [rbp+57h+lpWideCharStr]; unsigned __int16 **
0x1800280b0  lea     rcx, [rbp+57h+SourceString]; unsigned __int16 **
0x1800280b4  call    ?NlGetDomainName@@YAKPEAPEAG0PEAPEAX1PEAPEAU_GUID@@PEAE@Z; NlGetDomainName(ushort * *,ushort * *,void * *,void * *,_GUID * *,uchar *)
0x1800280b9  mov     r14, [rbp+57h+lpWideCharStr]
0x1800280bd  mov     ebx, eax
0x1800280bf  test    eax, eax
0x1800280c1  jnz     short loc_1800280F5
0x1800280c3  test    r14, r14
0x1800280c6  jz      loc_1800281BC
0x1800280cc  lea     rcx, [rbp+57h+var_78]; unsigned __int16 **
0x1800280d0  call    ?NlGetDnsHostName@@YAKPEAPEAG@Z; NlGetDnsHostName(ushort * *)
0x1800280d5  mov     ebx, eax
0x1800280d7  test    eax, eax
0x1800280d9  jz      loc_1800281B8
0x1800280df  mov     r8d, 3
0x1800280e5  mov     edx, eax
0x1800280e7  mov     ecx, 1669h
0x1800280ec  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x1800280f1  mov     r12, [rbp+57h+var_78]
0x1800280f5  mov     r13, [rbp+57h+Buf1]
0x1800280f9  mov     r15, [rbp+57h+Sid1]
0x1800280fd  mov     rsi, [rbp+57h+Sid2]
0x180028101  mov     rdi, [rbp+57h+SourceString]
0x180028105  mov     rax, [rbp+57h+Buffer]
0x180028109  test    rax, rax
0x18002810c  jz      short loc_18002811D
0x18002810e  mov     rcx, rax; Buffer
0x180028111  call    cs:__imp_NetApiBufferFree
0x180028118  nop     dword ptr [rax+rax+00h]
0x18002811d  test    r12, r12
0x180028120  jz      short loc_180028131
0x180028122  mov     rcx, r12; hMem
0x180028125  call    cs:__imp_LocalFree
0x18002812c  nop     dword ptr [rax+rax+00h]
0x180028131  test    rdi, rdi
0x180028134  jz      short loc_180028145
0x180028136  mov     rcx, rdi; hMem
0x180028139  call    cs:__imp_LocalFree
0x180028140  nop     dword ptr [rax+rax+00h]
0x180028145  test    r14, r14
0x180028148  jz      short loc_180028159
0x18002814a  mov     rcx, r14; hMem
0x18002814d  call    cs:__imp_LocalFree
0x180028154  nop     dword ptr [rax+rax+00h]
0x180028159  test    rsi, rsi
0x18002815c  jz      short loc_18002816D
0x18002815e  mov     rcx, rsi; hMem
0x180028161  call    cs:__imp_LocalFree
0x180028168  nop     dword ptr [rax+rax+00h]
0x18002816d  test    r15, r15
0x180028170  jz      short loc_180028181
0x180028172  mov     rcx, r15; hMem
0x180028175  call    cs:__imp_LocalFree
0x18002817c  nop     dword ptr [rax+rax+00h]
0x180028181  test    r13, r13
0x180028184  jz      short loc_180028195
0x180028186  mov     rcx, r13; hMem
0x180028189  call    cs:__imp_LocalFree
0x180028190  nop     dword ptr [rax+rax+00h]
0x180028195  mov     eax, ebx
0x180028197  mov     rcx, [rbp+57h+var_48]
0x18002819b  xor     rcx, rsp; StackCookie
0x18002819e  call    __security_check_cookie
0x1800281a3  add     rsp, 0B8h
0x1800281aa  pop     r15
0x1800281ac  pop     r14
0x1800281ae  pop     r13
0x1800281b0  pop     r12
0x1800281b2  pop     rdi
0x1800281b3  pop     rsi
0x1800281b4  pop     rbx
0x1800281b5  pop     rbp
0x1800281b6  retn
0x1800281b8  mov     r12, [rbp+57h+var_78]
0x1800281bc  mov     r13, [rbp+57h+Buf1]
0x1800281c0  lea     rax, [rbp+57h+var_68]
0x1800281c4  mov     rsi, [rbp+57h+Sid2]
0x1800281c8  mov     r9, r13; Buf1
0x1800281cb  mov     rcx, [rbp+57h+SourceString]; SourceString
0x1800281cf  mov     r8, rsi; Src
0x1800281d2  mov     [rsp+0F0h+var_B0], rax; struct _DOMAIN_INFO **
0x1800281d7  mov     rdx, r14; lpWideCharStr
0x1800281da  mov     rax, [rbp+57h+Buffer]
0x1800281de  mov     [rsp+0F0h+var_B8], 3000h; unsigned int
0x1800281e6  mov     [rsp+0F0h+var_C0], 1; char
0x1800281eb  mov     [rsp+0F0h+var_C8], r12; unsigned __int16 *
0x1800281f0  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x1800281f5  call    ?NlCreateDomainPhase1@@YAKPEAG0PEAXPEAU_GUID@@00EKPEAPEAU_DOMAIN_INFO@@@Z; NlCreateDomainPhase1(ushort *,ushort *,void *,_GUID *,ushort *,ushort *,uchar,ulong,_DOMAIN_INFO * *)
0x1800281fa  mov     r15, [rbp+57h+Sid1]
0x1800281fe  mov     ebx, eax
0x180028200  mov     rdi, [rbp+57h+var_68]
0x180028204  test    eax, eax
0x180028206  jnz     loc_180028380
0x18002820c  xor     ebx, ebx
0x18002820e  cmp     cs:?NlGlobalMemberWorkstation@@3HA, ebx; int NlGlobalMemberWorkstation
0x180028214  jz      loc_180028396
0x18002821a  mov     rdx, rsi; Sid2
0x18002821d  mov     rcx, r15; Sid1
0x180028220  call    cs:__imp_RtlEqualSid
0x180028227  nop     dword ptr [rax+rax+00h]
0x18002822c  test    al, al
0x18002822e  jz      short loc_180028288
0x180028230  xor     eax, eax
0x180028232  xorps   xmm0, xmm0
0x180028235  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180028239  mov     [rbp+57h+var_50], rax
0x18002823d  mov     rcx, rsi; Sid
0x180028240  mov     rax, [rdi+108h]
0x180028247  mov     [rbp+57h+var_60], rax
0x18002824b  lea     rax, [rdi+48h]
0x18002824f  mov     [rbp+57h+var_60+8], rax
0x180028253  mov     [rbp+57h+var_50], rbx
0x180028257  call    cs:__imp_RtlLengthSid
0x18002825e  nop     dword ptr [rax+rax+00h]
0x180028263  mov     dword ptr [rsp+0F0h+var_C0], eax; unsigned int
0x180028267  lea     r9, [rbp+57h+var_60]; unsigned __int16 **
0x18002826b  mov     [rsp+0F0h+var_C8], rsi; unsigned __int8 *
0x180028270  xor     r8d, r8d; unsigned int
0x180028273  lea     edx, [rbx+1]; unsigned int
0x180028276  mov     dword ptr [rsp+0F0h+var_D0], 2; unsigned int
0x18002827e  mov     ecx, 158Ch; unsigned int
0x180028283  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x180028288  lea     rcx, [rdi+190h]; CriticalSection
0x18002828f  call    cs:__imp_RtlEnterCriticalSection
0x180028296  nop     dword ptr [rax+rax+00h]
0x18002829b  cmp     [rdi+1E8h], rbx
0x1800282a2  jz      short loc_1800282BD
0x1800282a4  mov     r8d, 568h; unsigned int
0x1800282aa  lea     rdx, aOnecoreDsNetap_23; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x1800282b1  lea     rcx, aDomaininfoDomc; "DomainInfo->DomClientSession == NULL"
0x1800282b8  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x1800282bd  call    cs:__imp_SamIQueryCapabilities
0x1800282c4  nop     dword ptr [rax+rax+00h]
0x1800282c9  test    al, 2
0x1800282cb  jz      short loc_1800282D4
0x1800282cd  mov     ebx, 6
0x1800282d2  jmp     short loc_1800282E0
0x1800282d4  and     al, 1
0x1800282d6  neg     al
0x1800282d8  sbb     ebx, ebx
0x1800282da  and     ebx, 5
0x1800282dd  add     ebx, 2
0x1800282e0  call    cs:__imp_LsaIIsInEmulatedDomainJoinMode
0x1800282e7  nop     dword ptr [rax+rax+00h]
0x1800282ec  mov     [rsp+0F0h+var_B8], 0
0x1800282f4  lea     r8, [rdi+80h]
0x1800282fb  movzx   ecx, word ptr [r8]
0x1800282ff  lea     rdx, [rdi+38h]
0x180028303  neg     cx
0x180028306  mov     dword ptr [rsp+0F0h+var_C0], ebx
0x18002830a  mov     rcx, rdi
0x18002830d  sbb     r9d, r9d
0x180028310  and     r9d, 4
0x180028314  neg     al
0x180028316  sbb     eax, eax
0x180028318  and     eax, 40000h
0x18002831d  add     eax, 10h
0x180028320  or      r9d, eax
0x180028323  mov     rax, [rdi+0D0h]
0x18002832a  mov     dword ptr [rsp+0F0h+var_C8], r9d
0x18002832f  mov     r9, r15
0x180028332  mov     [rsp+0F0h+var_D0], rax
0x180028337  call    ?NlAllocateClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@1PEAXPEAU_GUID@@KW4_NETLOGON_SECURE_CHANNEL_TYPE@@K@Z; NlAllocateClientSession(_DOMAIN_INFO *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID *,ulong,_NETLOGON_SECURE_CHANNEL_TYPE,ulong)
0x18002833c  mov     [rdi+1E8h], rax
0x180028343  lea     rcx, [rdi+190h]; CriticalSection
0x18002834a  test    rax, rax
0x18002834d  jnz     short loc_180028372
0x18002834f  call    cs:__imp_RtlLeaveCriticalSection
0x180028356  nop     dword ptr [rax+rax+00h]
0x18002835b  mov     ebx, 8
0x180028360  mov     ecx, 0BEEh
0x180028365  mov     edx, ebx
0x180028367  lea     r8d, [rbx-7]
0x18002836b  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x180028370  jmp     short loc_180028380
0x180028372  call    cs:__imp_RtlLeaveCriticalSection
0x180028379  nop     dword ptr [rax+rax+00h]
0x18002837e  xor     ebx, ebx
0x180028380  test    rdi, rdi
0x180028383  jz      loc_180028101
0x180028389  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18002838c  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x180028391  jmp     loc_180028101
0x180028396  mov     dl, 1; unsigned __int8
0x180028398  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18002839b  call    ?NlCreateDomainPhase2@@YAKPEAU_DOMAIN_INFO@@E@Z; NlCreateDomainPhase2(_DOMAIN_INFO *,uchar)
0x1800283a0  mov     ebx, eax
0x1800283a2  test    eax, eax
0x1800283a4  jnz     short loc_180028380
0x1800283a6  mov     rcx, [rbp+57h+Buffer]; unsigned __int16 *
0x1800283aa  xor     r9d, r9d; unsigned __int8 *
0x1800283ad  mov     r8b, 1; unsigned __int8
0x1800283b0  mov     rdx, r12; unsigned __int16 *
0x1800283b3  call    ?NlUpdateServicedNdncs@@YAKPEAG0EPEAE@Z; NlUpdateServicedNdncs(ushort *,ushort *,uchar,uchar *)
0x1800283b8  mov     ebx, eax
0x1800283ba  test    eax, eax
0x1800283bc  jnz     short loc_180028380
0x1800283be  xor     edx, edx; int *
0x1800283c0  mov     rcx, rdi; struct _DOMAIN_INFO *
0x1800283c3  call    ?NlUpdateDnsRootAlias@@YAJPEAU_DOMAIN_INFO@@PEAH@Z; NlUpdateDnsRootAlias(_DOMAIN_INFO *,int *)
0x1800283c8  test    eax, eax
0x1800283ca  jns     short loc_18002837E
0x1800283cc  mov     ecx, eax; Status
0x1800283ce  call    NetpNtStatusToApiStatus
0x1800283d3  mov     ebx, eax
0x1800283d5  mov     r8d, 3
0x1800283db  mov     edx, eax
0x1800283dd  mov     ecx, 15E2h
0x1800283e2  jmp     short loc_18002836B
```
