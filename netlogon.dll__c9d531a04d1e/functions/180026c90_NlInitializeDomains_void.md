# NlInitializeDomains(void)

- ea: `0x180026c90`
- end: `0x180027075`
- name: `?NlInitializeDomains@@YAKXZ`
- size: `997`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006f490`

## callees

- `0x180002c00`
- `0x180003170`
- `0x180007b50`
- `0x18000d710`
- `0x18000e270`
- `0x180024f08`
- `0x18002545c`
- `0x180025708`
- `0x1800263c4`
- `0x180026508`
- `0x180026c90`
- `0x180027ab4`
- `0x180028384`
- `0x180029020`
- `0x18003f648`
- `0x180063f6c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e05`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e21`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e4b`
- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x180026f83`
- `LSASRV!LsaIIsInEmulatedDomainJoinMode` at `0x180026f83`
- `ntdll!RtlLeaveCriticalSection` at `0x180026fec`
- `ntdll!RtlLeaveCriticalSection` at `0x180027009`
- `ntdll!RtlLeaveCriticalSection` at `0x180026fec`
- `ntdll!RtlLeaveCriticalSection` at `0x180027009`
- `ntdll!RtlInitializeCriticalSection` at `0x180026cf6`
- `ntdll!RtlInitializeCriticalSection` at `0x180026cf6`
- `ntdll!RtlEnterCriticalSection` at `0x180026f3e`
- `ntdll!RtlEnterCriticalSection` at `0x180026f3e`
- `ntdll!RtlEqualSid` at `0x180026edb`
- `ntdll!RtlEqualSid` at `0x180026edb`
- `ntdll!RtlLengthSid` at `0x180026f0c`
- `ntdll!RtlLengthSid` at `0x180026f0c`
- `netutils!NetApiBufferFree` at `0x180026df7`
- `netutils!NetApiBufferFree` at `0x180026df7`
- `SAMSRV!SamIQueryCapabilities` at `0x180026f66`
- `SAMSRV!SamIQueryCapabilities` at `0x180026f66`

## string_xrefs

- `0x180026f53`: `onecore\ds\netapi\svcdlls\logonsrv\server\domain.cxx`

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
  qword_1800F1EF8 = (__int64)&NlGlobalServicedDomains;
  NlGlobalServicedDomains.Flink = &NlGlobalServicedDomains;
  qword_1800F1EE8 = (__int64)&NlGlobalServicedNdncs;
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
          1384,
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
      DomainPhase2 = NlCreateDomainPhase2(v34, 1);
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
0x180026c90  push    rbp
0x180026c92  push    rbx
0x180026c93  push    rsi
0x180026c94  push    rdi
0x180026c95  push    r12
0x180026c97  push    r13
0x180026c99  push    r14
0x180026c9b  push    r15
0x180026c9d  lea     rbp, [rsp-1Fh]
0x180026ca2  sub     rsp, 0B8h
0x180026ca9  mov     rax, cs:__security_cookie
0x180026cb0  xor     rax, rsp
0x180026cb3  mov     [rbp+57h+var_48], rax
0x180026cb7  xor     r12d, r12d
0x180026cba  mov     [rbp+57h+var_68], 0
0x180026cc2  xor     edi, edi
0x180026cc4  mov     [rbp+57h+var_78], r12
0x180026cc8  xor     r14d, r14d
0x180026ccb  mov     [rbp+57h+SourceString], rdi
0x180026ccf  xor     esi, esi
0x180026cd1  mov     [rbp+57h+lpWideCharStr], r14
0x180026cd5  xor     r15d, r15d
0x180026cd8  mov     [rbp+57h+Sid2], rsi
0x180026cdc  xor     r13d, r13d
0x180026cdf  mov     [rbp+57h+Sid1], r15
0x180026ce3  lea     rcx, ?NlGlobalDomainCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180026cea  mov     [rbp+57h+Buf1], r13
0x180026cee  mov     [rbp+57h+Buffer], 0
0x180026cf6  call    cs:__imp_RtlInitializeCriticalSection
0x180026cfc  lea     rax, ?NlGlobalServicedDomains@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalServicedDomains
0x180026d03  mov     cs:?NlGlobalDomainsInitialized@@3HA, 1; int NlGlobalDomainsInitialized
0x180026d0d  mov     cs:qword_1800F1EF8, rax
0x180026d14  lea     rcx, [rbp+57h+Buffer]
0x180026d18  mov     cs:?NlGlobalServicedDomains@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalServicedDomains
0x180026d1f  xor     edx, edx
0x180026d21  lea     rax, ?NlGlobalServicedNdncs@@3U_LIST_ENTRY@@A; _LIST_ENTRY NlGlobalServicedNdncs
0x180026d28  mov     cs:qword_1800F1EE8, rax
0x180026d2f  mov     cs:?NlGlobalServicedNdncs@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY NlGlobalServicedNdncs
0x180026d36  call    NetpGetComputerNameEx2
0x180026d3b  mov     ebx, eax
0x180026d3d  test    eax, eax
0x180026d3f  jz      short loc_180026D57
0x180026d41  lea     r8d, [r12+3]
0x180026d46  mov     edx, eax
0x180026d48  mov     ecx, 1669h
0x180026d4d  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x180026d52  jmp     loc_180026DEB
0x180026d57  mov     rcx, [rbp+57h+Buffer]; Src
0x180026d5b  call    NetpAllocWStrFromWStr
0x180026d60  mov     cs:?NlGlobalUnicodeComputerName@@3PEAGEA, rax; ushort * NlGlobalUnicodeComputerName
0x180026d67  test    rax, rax
0x180026d6a  jnz     short loc_180026D7C
0x180026d6c  lea     ebx, [rax+8]
0x180026d6f  mov     ecx, 0BEEh
0x180026d74  mov     edx, ebx
0x180026d76  lea     r8d, [rax+1]
0x180026d7a  jmp     short loc_180026D4D
0x180026d7c  lea     rax, [rbp+57h+Buf1]
0x180026d80  mov     [rsp+0F0h+var_C8], rsi; unsigned __int8 *
0x180026d85  lea     r9, [rbp+57h+Sid1]; void **
0x180026d89  mov     [rsp+0F0h+var_D0], rax; struct _GUID **
0x180026d8e  lea     r8, [rbp+57h+Sid2]; void **
0x180026d92  lea     rdx, [rbp+57h+lpWideCharStr]; unsigned __int16 **
0x180026d96  lea     rcx, [rbp+57h+SourceString]; unsigned __int16 **
0x180026d9a  call    ?NlGetDomainName@@YAKPEAPEAG0PEAPEAX1PEAPEAU_GUID@@PEAE@Z; NlGetDomainName(ushort * *,ushort * *,void * *,void * *,_GUID * *,uchar *)
0x180026d9f  mov     r14, [rbp+57h+lpWideCharStr]
0x180026da3  mov     ebx, eax
0x180026da5  test    eax, eax
0x180026da7  jnz     short loc_180026DDB
0x180026da9  test    r14, r14
0x180026dac  jz      loc_180026E77
0x180026db2  lea     rcx, [rbp+57h+var_78]; unsigned __int16 **
0x180026db6  call    ?NlGetDnsHostName@@YAKPEAPEAG@Z; NlGetDnsHostName(ushort * *)
0x180026dbb  mov     ebx, eax
0x180026dbd  test    eax, eax
0x180026dbf  jz      loc_180026E73
0x180026dc5  mov     r8d, 3
0x180026dcb  mov     edx, eax
0x180026dcd  mov     ecx, 1669h
0x180026dd2  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x180026dd7  mov     r12, [rbp+57h+var_78]
0x180026ddb  mov     r13, [rbp+57h+Buf1]
0x180026ddf  mov     r15, [rbp+57h+Sid1]
0x180026de3  mov     rsi, [rbp+57h+Sid2]
0x180026de7  mov     rdi, [rbp+57h+SourceString]
0x180026deb  mov     rax, [rbp+57h+Buffer]
0x180026def  test    rax, rax
0x180026df2  jz      short loc_180026DFD
0x180026df4  mov     rcx, rax; Buffer
0x180026df7  call    cs:__imp_NetApiBufferFree
0x180026dfd  test    r12, r12
0x180026e00  jz      short loc_180026E0B
0x180026e02  mov     rcx, r12; hMem
0x180026e05  call    cs:__imp_LocalFree
0x180026e0b  test    rdi, rdi
0x180026e0e  jz      short loc_180026E19
0x180026e10  mov     rcx, rdi; hMem
0x180026e13  call    cs:__imp_LocalFree
0x180026e19  test    r14, r14
0x180026e1c  jz      short loc_180026E27
0x180026e1e  mov     rcx, r14; hMem
0x180026e21  call    cs:__imp_LocalFree
0x180026e27  test    rsi, rsi
0x180026e2a  jz      short loc_180026E35
0x180026e2c  mov     rcx, rsi; hMem
0x180026e2f  call    cs:__imp_LocalFree
0x180026e35  test    r15, r15
0x180026e38  jz      short loc_180026E43
0x180026e3a  mov     rcx, r15; hMem
0x180026e3d  call    cs:__imp_LocalFree
0x180026e43  test    r13, r13
0x180026e46  jz      short loc_180026E51
0x180026e48  mov     rcx, r13; hMem
0x180026e4b  call    cs:__imp_LocalFree
0x180026e51  mov     eax, ebx
0x180026e53  mov     rcx, [rbp+57h+var_48]
0x180026e57  xor     rcx, rsp; StackCookie
0x180026e5a  call    __security_check_cookie
0x180026e5f  add     rsp, 0B8h
0x180026e66  pop     r15
0x180026e68  pop     r14
0x180026e6a  pop     r13
0x180026e6c  pop     r12
0x180026e6e  pop     rdi
0x180026e6f  pop     rsi
0x180026e70  pop     rbx
0x180026e71  pop     rbp
0x180026e72  retn
0x180026e73  mov     r12, [rbp+57h+var_78]
0x180026e77  mov     r13, [rbp+57h+Buf1]
0x180026e7b  lea     rax, [rbp+57h+var_68]
0x180026e7f  mov     rsi, [rbp+57h+Sid2]
0x180026e83  mov     r9, r13; Buf1
0x180026e86  mov     rcx, [rbp+57h+SourceString]; SourceString
0x180026e8a  mov     r8, rsi; Src
0x180026e8d  mov     [rsp+0F0h+var_B0], rax; struct _DOMAIN_INFO **
0x180026e92  mov     rdx, r14; lpWideCharStr
0x180026e95  mov     rax, [rbp+57h+Buffer]
0x180026e99  mov     [rsp+0F0h+var_B8], 3000h; unsigned int
0x180026ea1  mov     [rsp+0F0h+var_C0], 1; char
0x180026ea6  mov     [rsp+0F0h+var_C8], r12; unsigned __int16 *
0x180026eab  mov     [rsp+0F0h+var_D0], rax; unsigned __int16 *
0x180026eb0  call    ?NlCreateDomainPhase1@@YAKPEAG0PEAXPEAU_GUID@@00EKPEAPEAU_DOMAIN_INFO@@@Z; NlCreateDomainPhase1(ushort *,ushort *,void *,_GUID *,ushort *,ushort *,uchar,ulong,_DOMAIN_INFO * *)
0x180026eb5  mov     r15, [rbp+57h+Sid1]
0x180026eb9  mov     ebx, eax
0x180026ebb  mov     rdi, [rbp+57h+var_68]
0x180026ebf  test    eax, eax
0x180026ec1  jnz     loc_180027011
0x180026ec7  xor     ebx, ebx
0x180026ec9  cmp     cs:?NlGlobalMemberWorkstation@@3HA, ebx; int NlGlobalMemberWorkstation
0x180026ecf  jz      loc_180027027
0x180026ed5  mov     rdx, rsi; Sid2
0x180026ed8  mov     rcx, r15; Sid1
0x180026edb  call    cs:__imp_RtlEqualSid
0x180026ee1  test    al, al
0x180026ee3  jz      short loc_180026F37
0x180026ee5  xor     eax, eax
0x180026ee7  xorps   xmm0, xmm0
0x180026eea  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180026eee  mov     [rbp+57h+var_50], rax
0x180026ef2  mov     rcx, rsi; Sid
0x180026ef5  mov     rax, [rdi+108h]
0x180026efc  mov     [rbp+57h+var_60], rax
0x180026f00  lea     rax, [rdi+48h]
0x180026f04  mov     [rbp+57h+var_60+8], rax
0x180026f08  mov     [rbp+57h+var_50], rbx
0x180026f0c  call    cs:__imp_RtlLengthSid
0x180026f12  mov     dword ptr [rsp+0F0h+var_C0], eax; unsigned int
0x180026f16  lea     r9, [rbp+57h+var_60]; unsigned __int16 **
0x180026f1a  mov     [rsp+0F0h+var_C8], rsi; unsigned __int8 *
0x180026f1f  xor     r8d, r8d; unsigned int
0x180026f22  lea     edx, [rbx+1]; unsigned int
0x180026f25  mov     dword ptr [rsp+0F0h+var_D0], 2; unsigned int
0x180026f2d  mov     ecx, 158Ch; unsigned int
0x180026f32  call    ?NlpWriteEventlog@@YAXKKKPEAPEAGKPEAEK@Z; NlpWriteEventlog(ulong,ulong,ulong,ushort * *,ulong,uchar *,ulong)
0x180026f37  lea     rcx, [rdi+190h]; CriticalSection
0x180026f3e  call    cs:__imp_RtlEnterCriticalSection
0x180026f44  cmp     [rdi+1E8h], rbx
0x180026f4b  jz      short loc_180026F66
0x180026f4d  mov     r8d, 568h; unsigned int
0x180026f53  lea     rdx, aOnecoreDsNetap_23; "onecore\\ds\\netapi\\svcdlls\\logonsrv"...
0x180026f5a  lea     rcx, aDomaininfoDomc; "DomainInfo->DomClientSession == NULL"
0x180026f61  call    ?NlAssertFailed@@YAXPEAX0KPEAD@Z; NlAssertFailed(void *,void *,ulong,char *)
0x180026f66  call    cs:__imp_SamIQueryCapabilities
0x180026f6c  test    al, 2
0x180026f6e  jz      short loc_180026F77
0x180026f70  mov     ebx, 6
0x180026f75  jmp     short loc_180026F83
0x180026f77  and     al, 1
0x180026f79  neg     al
0x180026f7b  sbb     ebx, ebx
0x180026f7d  and     ebx, 5
0x180026f80  add     ebx, 2
0x180026f83  call    cs:__imp_LsaIIsInEmulatedDomainJoinMode
0x180026f89  mov     [rsp+0F0h+var_B8], 0
0x180026f91  lea     r8, [rdi+80h]
0x180026f98  movzx   ecx, word ptr [r8]
0x180026f9c  lea     rdx, [rdi+38h]
0x180026fa0  neg     cx
0x180026fa3  mov     dword ptr [rsp+0F0h+var_C0], ebx
0x180026fa7  mov     rcx, rdi
0x180026faa  sbb     r9d, r9d
0x180026fad  and     r9d, 4
0x180026fb1  neg     al
0x180026fb3  sbb     eax, eax
0x180026fb5  and     eax, 40000h
0x180026fba  add     eax, 10h
0x180026fbd  or      r9d, eax
0x180026fc0  mov     rax, [rdi+0D0h]
0x180026fc7  mov     dword ptr [rsp+0F0h+var_C8], r9d
0x180026fcc  mov     r9, r15
0x180026fcf  mov     [rsp+0F0h+var_D0], rax
0x180026fd4  call    ?NlAllocateClientSession@@YAPEAU_CLIENT_SESSION@@PEAU_DOMAIN_INFO@@PEAU_UNICODE_STRING@@1PEAXPEAU_GUID@@KW4_NETLOGON_SECURE_CHANNEL_TYPE@@K@Z; NlAllocateClientSession(_DOMAIN_INFO *,_UNICODE_STRING *,_UNICODE_STRING *,void *,_GUID *,ulong,_NETLOGON_SECURE_CHANNEL_TYPE,ulong)
0x180026fd9  mov     [rdi+1E8h], rax
0x180026fe0  lea     rcx, [rdi+190h]; CriticalSection
0x180026fe7  test    rax, rax
0x180026fea  jnz     short loc_180027009
0x180026fec  call    cs:__imp_RtlLeaveCriticalSection
0x180026ff2  mov     ebx, 8
0x180026ff7  mov     ecx, 0BEEh
0x180026ffc  mov     edx, ebx
0x180026ffe  lea     r8d, [rbx-7]
0x180027002  call    ?NlExit@@YAXKKW4NL_EXIT_CODE@@PEAG@Z; NlExit(ulong,ulong,NL_EXIT_CODE,ushort *)
0x180027007  jmp     short loc_180027011
0x180027009  call    cs:__imp_RtlLeaveCriticalSection
0x18002700f  xor     ebx, ebx
0x180027011  test    rdi, rdi
0x180027014  jz      loc_180026DE7
0x18002701a  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18002701d  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x180027022  jmp     loc_180026DE7
0x180027027  mov     dl, 1; unsigned __int8
0x180027029  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18002702c  call    ?NlCreateDomainPhase2@@YAKPEAU_DOMAIN_INFO@@E@Z; NlCreateDomainPhase2(_DOMAIN_INFO *,uchar)
0x180027031  mov     ebx, eax
0x180027033  test    eax, eax
0x180027035  jnz     short loc_180027011
0x180027037  mov     rcx, [rbp+57h+Buffer]; unsigned __int16 *
0x18002703b  xor     r9d, r9d; unsigned __int8 *
0x18002703e  mov     r8b, 1; unsigned __int8
0x180027041  mov     rdx, r12; unsigned __int16 *
0x180027044  call    ?NlUpdateServicedNdncs@@YAKPEAG0EPEAE@Z; NlUpdateServicedNdncs(ushort *,ushort *,uchar,uchar *)
0x180027049  mov     ebx, eax
0x18002704b  test    eax, eax
0x18002704d  jnz     short loc_180027011
0x18002704f  xor     edx, edx; int *
0x180027051  mov     rcx, rdi; struct _DOMAIN_INFO *
0x180027054  call    ?NlUpdateDnsRootAlias@@YAJPEAU_DOMAIN_INFO@@PEAH@Z; NlUpdateDnsRootAlias(_DOMAIN_INFO *,int *)
0x180027059  test    eax, eax
0x18002705b  jns     short loc_18002700F
0x18002705d  mov     ecx, eax; Status
0x18002705f  call    NetpNtStatusToApiStatus
0x180027064  mov     ebx, eax
0x180027066  mov     r8d, 3
0x18002706c  mov     edx, eax
0x18002706e  mov     ecx, 15E2h
0x180027073  jmp     short loc_180027002
```
