# NlGetLocalPingResponse(ushort const *,ushort const *,char const *,_GUID *,void *,int,ushort const *,ushort const *,ushort const *,ulong,ulong,ulong,sockaddr *,void * *,ulong *)

- ea: `0x18006ef9c`
- end: `0x18006f488`
- name: `?NlGetLocalPingResponse@@YAKPEBG0PEBDPEAU_GUID@@PEAXH000KKKPEAUsockaddr@@PEAPEAXPEAK@Z`
- size: `1260`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, PCWSTR SourceString, const char *, struct _GUID *Buf1, void *, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, struct sockaddr *, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d910`
- `0x180078f00`

## callees

- `0x180003200`
- `0x180007278`
- `0x18000e270`
- `0x18000ed34`
- `0x180025708`
- `0x180025e34`
- `0x180026180`
- `0x18006da7c`
- `0x18006ef9c`
- `0x180073e34`
- `0x180083250`
- `0x180089ab4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18006f15b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18006f15b`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18006f100`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18006f100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f10f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f1a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f10f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f1a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f167`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006f167`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006f079`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006f0ad`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006f079`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006f0ad`
- `ntdll!RtlLeaveCriticalSection` at `0x18006f2a3`
- `ntdll!RtlLeaveCriticalSection` at `0x18006f356`
- `ntdll!RtlLeaveCriticalSection` at `0x18006f2a3`
- `ntdll!RtlLeaveCriticalSection` at `0x18006f356`
- `ntdll!RtlEnterCriticalSection` at `0x18006f257`
- `ntdll!RtlEnterCriticalSection` at `0x18006f316`
- `ntdll!RtlEnterCriticalSection` at `0x18006f257`
- `ntdll!RtlEnterCriticalSection` at `0x18006f316`
- `netutils!NetApiBufferFree` at `0x18006f45d`
- `netutils!NetApiBufferFree` at `0x18006f45d`
- `netutils!NetApiBufferAllocate` at `0x18006f088`
- `netutils!NetApiBufferAllocate` at `0x18006f088`
- `WS2_32!__imp_htonl` at `0x18006f307`
- `WS2_32!__imp_htonl` at `0x18006f307`

## string_xrefs

- `0x18006f0ee`: `NtdsDelayedStartupCompletedEvent`
- `0x18006f115`: `NtdsDelayedStartupCompletedEvent`
- `0x18006f124`: `NlGetLocalPingResponse: Cannot OpenEvent %ws %ld\n`

## pseudocode

```c
__int64 __fastcall NlGetLocalPingResponse(
        unsigned __int16 *a1,
        PCWSTR SourceString,
        const char *a3,
        struct _GUID *Buf1,
        void *a5,
        int a6,
        unsigned __int16 *a7,
        unsigned __int16 *a8,
        unsigned __int16 *a9,
        unsigned int a10,
        unsigned int a11,
        int a12,
        struct sockaddr *a13,
        void **a14,
        unsigned int *a15)
{
  int cchWideChar; // ebx
  __int64 LastError; // rbx
  DWORD v22; // ebx
  struct _DOMAIN_INFO *DnsDomain; // rdi
  int v24; // ebx
  u_long v25; // ebx
  unsigned int v26; // ecx
  __int64 v27; // r8
  unsigned __int8 Handler; // al
  void *v29; // rax
  unsigned __int8 v30[4]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int Size[3]; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned __int16 *v32; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v33; // [rsp+98h] [rbp-68h]
  struct sockaddr *v34; // [rsp+A0h] [rbp-60h]
  void *v35; // [rsp+A8h] [rbp-58h]
  HANDLE Handles[2]; // [rsp+B0h] [rbp-50h] BYREF
  void **v37; // [rsp+C0h] [rbp-40h]
  unsigned int *v38; // [rsp+C8h] [rbp-38h]
  unsigned __int8 Src[528]; // [rsp+D0h] [rbp-30h] BYREF

  v35 = a5;
  v32 = a8;
  v34 = a13;
  v37 = a14;
  v38 = a15;
  v33 = a7;
  memset(Size, 0, sizeof(Size));
  v30[0] = 0;
  if ( NlGlobalMemberWorkstation )
    return 1355;
  memset_0(Src, 0, 0x208u);
  if ( a3 )
  {
    cchWideChar = MultiByteToWideChar(0xFDE9u, 0, a3, -1, 0, 0);
    if ( !NetApiBufferAllocate(2 * cchWideChar, (LPVOID *)&Size[1]) )
      MultiByteToWideChar(0xFDE9u, 0, a3, -1, *(LPWSTR *)&Size[1], cchWideChar);
  }
  NlPrintRoutine(0x10u, L"Received ping from %ws(%ws) %ws %ws on %ws\n", a7, v32, *(_QWORD *)&Size[1], a9, a1);
  if ( !NlGlobalDsRunningUnknown )
    goto LABEL_19;
  *(_OWORD *)Handles = 0;
  Handles[0] = OpenEventW(0x100000u, 0, L"NtdsDelayedStartupCompletedEvent");
  if ( Handles[0] )
  {
    Handles[1] = NlGlobalTerminateEvent;
    v22 = WaitForMultipleObjectsEx(2u, Handles, 0, 0x124F80u, 0);
    CloseHandle(Handles[0]);
    if ( v22 )
    {
      switch ( v22 )
      {
        case 1u:
          NlPrintRoutine(0x100u, L"NlGetLocalPingResponse: Netlogon shut down.\n");
          break;
        case 0x102u:
          NlPrintRoutine(0x100u, L"NlGetLocalPingResponse: DS took too long to start.\n");
          break;
        case 0xFFFFFFFF:
          LastError = GetLastError();
          NlPrintRoutine(0x100u, L"NlGetLocalPingResponse: Wait for DS failed %ld.\n", LastError);
          goto LABEL_55;
        default:
          NlPrintRoutine(0x100u, L"NlGetLocalPingResponse: Unknown status from Wait %ld.\n", v22);
          break;
      }
      goto LABEL_14;
    }
    NlGlobalDsRunningUnknown = 0;
LABEL_19:
    if ( a3 || Buf1 )
    {
      DnsDomain = NlFindDnsDomain(a3, Buf1, 1u, 1u, v30);
      if ( DnsDomain )
        goto LABEL_40;
      if ( a12 >= 0 || v35 || a9 || a10 || !a3 )
        goto LABEL_37;
      RtlEnterCriticalSection(&NlGlobalDnsForestNameCritSect);
      if ( NlGlobalUtf8DnsForestName && (unsigned int)NlEqualDnsNameUtf8(a3, NlGlobalUtf8DnsForestName) )
      {
        v24 = 1;
      }
      else
      {
        v24 = 0;
        if ( NlGlobalUtf8DnsForestNameAlias && (unsigned int)NlEqualDnsNameUtf8(a3, NlGlobalUtf8DnsForestNameAlias) )
        {
          v24 = 1;
          v30[0] = 1;
        }
      }
      RtlLeaveCriticalSection(&NlGlobalDnsForestNameCritSect);
      if ( !v24 )
      {
LABEL_37:
        if ( !SourceString )
        {
LABEL_39:
          NlPrintRoutine(
            0x100u,
            L"Ping from %ws for domain %ws %ws for %ws on %ws is invalid since we don't host the named domain.\n",
            v33,
            *(_QWORD *)&Size[1],
            SourceString,
            a9,
            a1);
LABEL_14:
          LODWORD(LastError) = 1355;
          goto LABEL_55;
        }
        goto LABEL_38;
      }
    }
    else if ( SourceString )
    {
LABEL_38:
      DnsDomain = NlFindNetbiosDomain(SourceString, 0);
      if ( !DnsDomain )
        goto LABEL_39;
LABEL_40:
      v25 = htonl(0x7F000001u);
      RtlEnterCriticalSection(&NlGlobalTransportCritSect);
      if ( NlGlobalWinsockPnpAddresses )
      {
        v26 = 0;
        if ( *(int *)NlGlobalWinsockPnpAddresses > 0 )
        {
          while ( 1 )
          {
            v27 = *((_QWORD *)NlGlobalWinsockPnpAddresses + 2 * v26 + 1);
            if ( *(_WORD *)v27 == 2 )
              break;
            if ( (signed int)++v26 >= *(_DWORD *)NlGlobalWinsockPnpAddresses )
              goto LABEL_46;
          }
          v25 = *(_DWORD *)(v27 + 4);
        }
      }
LABEL_46:
      RtlLeaveCriticalSection(&NlGlobalTransportCritSect);
      if ( a6 )
        Handler = PrimaryQueryHandler(a1, DnsDomain, v30[0], 2u, a12, v33, v32, v25, v34, Src, Size);
      else
        Handler = LogonRequestHandler(a1, DnsDomain, v30[0], v35, 2u, a12, a9, 0, v33, v32, a10, v25, v34, Src, Size);
      if ( Handler )
      {
        v29 = (void *)NetpMemoryAllocate(Size[0]);
        *v37 = v29;
        if ( v29 )
        {
          memcpy_0(v29, Src, Size[0]);
          LODWORD(LastError) = 0;
          *v38 = Size[0];
        }
        else
        {
          LODWORD(LastError) = 8;
        }
      }
      else
      {
        LODWORD(LastError) = 1355;
      }
      NlDereferenceDomain(DnsDomain);
      goto LABEL_55;
    }
    DnsDomain = NlFindNetbiosDomain(0, 1u);
    if ( DnsDomain )
      goto LABEL_40;
    goto LABEL_37;
  }
  LastError = GetLastError();
  NlPrintRoutine(
    0x100u,
    L"NlGetLocalPingResponse: Cannot OpenEvent %ws %ld\n",
    L"NtdsDelayedStartupCompletedEvent",
    LastError);
LABEL_55:
  if ( *(_QWORD *)&Size[1] )
    NetApiBufferFree(*(LPVOID *)&Size[1]);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18006ef9c  push    rbp
0x18006ef9e  push    rbx
0x18006ef9f  push    rsi
0x18006efa0  push    rdi
0x18006efa1  push    r12
0x18006efa3  push    r13
0x18006efa5  push    r14
0x18006efa7  push    r15
0x18006efa9  lea     rbp, [rsp-1F8h]
0x18006efb1  sub     rsp, 2F8h
0x18006efb8  mov     rax, cs:__security_cookie
0x18006efbf  xor     rax, rsp
0x18006efc2  mov     [rbp+230h+var_50], rax
0x18006efc9  cmp     cs:?NlGlobalMemberWorkstation@@3HA, 0; int NlGlobalMemberWorkstation
0x18006efd0  mov     rdi, r9
0x18006efd3  mov     rax, [rbp+230h+arg_20]
0x18006efda  mov     rsi, r8
0x18006efdd  mov     r15, [rbp+230h+arg_30]
0x18006efe4  mov     r14, rdx
0x18006efe7  mov     r12, [rbp+230h+arg_40]
0x18006efee  mov     r13, rcx
0x18006eff1  mov     [rbp+230h+var_288], rax
0x18006eff5  mov     rax, [rbp+230h+arg_38]
0x18006effc  mov     [rbp+230h+var_2A0], rax
0x18006f000  mov     rax, [rbp+230h+arg_60]
0x18006f007  mov     [rbp+230h+var_290], rax
0x18006f00b  mov     rax, [rbp+230h+arg_68]
0x18006f012  mov     [rbp+230h+var_270], rax
0x18006f016  mov     rax, [rbp+230h+arg_70]
0x18006f01d  mov     [rbp+230h+var_268], rax
0x18006f021  mov     [rbp+230h+var_298], r15
0x18006f025  mov     dword ptr [rbp+230h+Size], 0
0x18006f02c  mov     [rbp+230h+var_2B0], 0
0x18006f030  mov     qword ptr [rbp+230h+Size+4], 0
0x18006f038  jz      short loc_18006F044
0x18006f03a  mov     eax, 54Bh
0x18006f03f  jmp     loc_18006F465
0x18006f044  xor     edx, edx; Val
0x18006f046  lea     rcx, [rbp+230h+Src]; void *
0x18006f04a  mov     r8d, 208h; Size
0x18006f050  call    memset_0
0x18006f055  test    rsi, rsi
0x18006f058  jz      short loc_18006F0B3
0x18006f05a  mov     [rsp+330h+cchWideChar], 0; cchWideChar
0x18006f062  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18006f066  mov     r8, rsi; lpMultiByteStr
0x18006f069  mov     [rsp+330h+lpWideCharStr], 0; lpWideCharStr
0x18006f072  xor     edx, edx; dwFlags
0x18006f074  mov     ecx, 0FDE9h; CodePage
0x18006f079  call    cs:__imp_MultiByteToWideChar
0x18006f07f  lea     rdx, [rbp+230h+Size+4]; Buffer
0x18006f083  mov     ebx, eax
0x18006f085  lea     ecx, [rax+rax]; ByteCount
0x18006f088  call    cs:__imp_NetApiBufferAllocate
0x18006f08e  test    eax, eax
0x18006f090  jnz     short loc_18006F0B3
0x18006f092  mov     rax, qword ptr [rbp+230h+Size+4]
0x18006f096  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18006f09a  mov     [rsp+330h+cchWideChar], ebx; cchWideChar
0x18006f09e  mov     r8, rsi; lpMultiByteStr
0x18006f0a1  xor     edx, edx; dwFlags
0x18006f0a3  mov     [rsp+330h+lpWideCharStr], rax; lpWideCharStr
0x18006f0a8  mov     ecx, 0FDE9h; CodePage
0x18006f0ad  call    cs:__imp_MultiByteToWideChar
0x18006f0b3  mov     rax, qword ptr [rbp+230h+Size+4]
0x18006f0b7  lea     rdx, aReceivedPingFr; "Received ping from %ws(%ws) %ws %ws on "...
0x18006f0be  mov     r9, [rbp+230h+var_2A0]
0x18006f0c2  mov     r8, r15
0x18006f0c5  mov     [rsp+330h+var_300], r13
0x18006f0ca  mov     ecx, 10h; unsigned int
0x18006f0cf  mov     qword ptr [rsp+330h+cchWideChar], r12
0x18006f0d4  mov     [rsp+330h+lpWideCharStr], rax
0x18006f0d9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006f0de  cmp     cs:?NlGlobalDsRunningUnknown@@3EA, 0; uchar NlGlobalDsRunningUnknown
0x18006f0e5  jz      loc_18006F1E5
0x18006f0eb  xorps   xmm0, xmm0
0x18006f0ee  lea     r8, Name; "NtdsDelayedStartupCompletedEvent"
0x18006f0f5  xor     edx, edx; bInheritHandle
0x18006f0f7  mov     ecx, 100000h; dwDesiredAccess
0x18006f0fc  movups  xmmword ptr [rbp+230h+Handles], xmm0
0x18006f100  call    cs:__imp_OpenEventW
0x18006f106  mov     [rbp+230h+Handles], rax
0x18006f10a  test    rax, rax
0x18006f10d  jnz     short loc_18006F137
0x18006f10f  call    cs:__imp_GetLastError
0x18006f115  lea     r8, Name; "NtdsDelayedStartupCompletedEvent"
0x18006f11c  mov     ecx, 100h; unsigned int
0x18006f121  mov     r9d, eax
0x18006f124  lea     rdx, aNlgetlocalping; "NlGetLocalPingResponse: Cannot OpenEven"...
0x18006f12b  mov     ebx, eax
0x18006f12d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006f132  jmp     loc_18006F454
0x18006f137  mov     rax, cs:?NlGlobalTerminateEvent@@3PEAXEA; void * NlGlobalTerminateEvent
0x18006f13e  lea     rdx, [rbp+230h+Handles]; lpHandles
0x18006f142  xor     r8d, r8d; bWaitAll
0x18006f145  mov     [rbp+230h+Handles+8], rax
0x18006f149  mov     r9d, 124F80h; dwMilliseconds
0x18006f14f  mov     dword ptr [rsp+330h+lpWideCharStr], 0; bAlertable
0x18006f157  lea     ecx, [r8+2]; nCount
0x18006f15b  call    cs:__imp_WaitForMultipleObjectsEx
0x18006f161  mov     rcx, [rbp+230h+Handles]; hObject
0x18006f165  mov     ebx, eax
0x18006f167  call    cs:__imp_CloseHandle
0x18006f16d  test    ebx, ebx
0x18006f16f  jz      short loc_18006F1DE
0x18006f171  cmp     ebx, 1
0x18006f174  jz      short loc_18006F1D5
0x18006f176  cmp     ebx, 102h
0x18006f17c  jz      short loc_18006F1C2
0x18006f17e  cmp     ebx, 0FFFFFFFFh
0x18006f181  jz      short loc_18006F1A1
0x18006f183  mov     r8d, ebx
0x18006f186  lea     rdx, aNlgetlocalping_0; "NlGetLocalPingResponse: Unknown status "...
0x18006f18d  mov     ecx, 100h; unsigned int
0x18006f192  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006f197  mov     ebx, 54Bh
0x18006f19c  jmp     loc_18006F454
0x18006f1a1  call    cs:__imp_GetLastError
0x18006f1a7  lea     rdx, aNlgetlocalping_3; "NlGetLocalPingResponse: Wait for DS fai"...
0x18006f1ae  mov     ecx, 100h; unsigned int
0x18006f1b3  mov     r8d, eax
0x18006f1b6  mov     ebx, eax
0x18006f1b8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006f1bd  jmp     loc_18006F454
0x18006f1c2  lea     rdx, aNlgetlocalping_1; "NlGetLocalPingResponse: DS took too lon"...
0x18006f1c9  mov     ecx, 100h; unsigned int
0x18006f1ce  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006f1d3  jmp     short loc_18006F197
0x18006f1d5  lea     rdx, aNlgetlocalping_2; "NlGetLocalPingResponse: Netlogon shut d"...
0x18006f1dc  jmp     short loc_18006F1C9
0x18006f1de  mov     cs:?NlGlobalDsRunningUnknown@@3EA, 0; uchar NlGlobalDsRunningUnknown
0x18006f1e5  mov     r15d, [rbp+230h+arg_58]
0x18006f1ec  test    rsi, rsi
0x18006f1ef  jnz     short loc_18006F204
0x18006f1f1  test    rdi, rdi
0x18006f1f4  jnz     short loc_18006F204
0x18006f1f6  test    r14, r14
0x18006f1f9  jnz     loc_18006F2C3
0x18006f1ff  jmp     loc_18006F2AD
0x18006f204  mov     r9b, 1; unsigned __int8
0x18006f207  lea     rax, [rbp+230h+var_2B0]
0x18006f20b  mov     r8b, r9b; unsigned __int8
0x18006f20e  mov     [rsp+330h+lpWideCharStr], rax; unsigned __int8 *
0x18006f213  mov     rdx, rdi; Buf1
0x18006f216  mov     rcx, rsi; char *
0x18006f219  call    ?NlFindDnsDomain@@YAPEAU_DOMAIN_INFO@@PEBDPEAU_GUID@@EEPEAE@Z; NlFindDnsDomain(char const *,_GUID *,uchar,uchar,uchar *)
0x18006f21e  mov     rdi, rax
0x18006f221  test    rax, rax
0x18006f224  jnz     loc_18006F302
0x18006f22a  test    r15d, r15d
0x18006f22d  jns     loc_18006F2BE
0x18006f233  cmp     [rbp+230h+var_288], rax
0x18006f237  jnz     loc_18006F2BE
0x18006f23d  test    r12, r12
0x18006f240  jnz     short loc_18006F2BE
0x18006f242  cmp     [rbp+230h+arg_48], r12d
0x18006f249  jnz     short loc_18006F2BE
0x18006f24b  test    rsi, rsi
0x18006f24e  jz      short loc_18006F2BE
0x18006f250  lea     rcx, ?NlGlobalDnsForestNameCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18006f257  call    cs:__imp_RtlEnterCriticalSection
0x18006f25d  mov     rdx, cs:?NlGlobalUtf8DnsForestName@@3PEADEA; char *
0x18006f264  test    rdx, rdx
0x18006f267  jz      short loc_18006F27A
0x18006f269  mov     rcx, rsi; char *
0x18006f26c  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x18006f271  test    eax, eax
0x18006f273  jz      short loc_18006F27A
0x18006f275  lea     ebx, [rdi+1]
0x18006f278  jmp     short loc_18006F29C
0x18006f27a  mov     rdx, cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA; char *
0x18006f281  xor     ebx, ebx
0x18006f283  test    rdx, rdx
0x18006f286  jz      short loc_18006F29C
0x18006f288  mov     rcx, rsi; char *
0x18006f28b  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x18006f290  test    eax, eax
0x18006f292  jz      short loc_18006F29C
0x18006f294  mov     ebx, 1
0x18006f299  mov     [rbp+230h+var_2B0], bl
0x18006f29c  lea     rcx, ?NlGlobalDnsForestNameCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18006f2a3  call    cs:__imp_RtlLeaveCriticalSection
0x18006f2a9  test    ebx, ebx
0x18006f2ab  jz      short loc_18006F2BE
0x18006f2ad  xor     ecx, ecx; SourceString
0x18006f2af  mov     dl, 1; unsigned __int8
0x18006f2b1  call    ?NlFindNetbiosDomain@@YAPEAU_DOMAIN_INFO@@PEBGE@Z; NlFindNetbiosDomain(ushort const *,uchar)
0x18006f2b6  mov     rdi, rax
0x18006f2b9  test    rax, rax
0x18006f2bc  jnz     short loc_18006F302
0x18006f2be  test    r14, r14
0x18006f2c1  jz      short loc_18006F2D5
0x18006f2c3  xor     edx, edx; unsigned __int8
0x18006f2c5  mov     rcx, r14; SourceString
0x18006f2c8  call    ?NlFindNetbiosDomain@@YAPEAU_DOMAIN_INFO@@PEBGE@Z; NlFindNetbiosDomain(ushort const *,uchar)
0x18006f2cd  mov     rdi, rax
0x18006f2d0  test    rax, rax
0x18006f2d3  jnz     short loc_18006F302
0x18006f2d5  mov     r9, qword ptr [rbp+230h+Size+4]
0x18006f2d9  lea     rdx, aPingFromWsForD; "Ping from %ws for domain %ws %ws for %w"...
0x18006f2e0  mov     r8, [rbp+230h+var_298]
0x18006f2e4  mov     ecx, 100h; unsigned int
0x18006f2e9  mov     [rsp+330h+var_300], r13
0x18006f2ee  mov     qword ptr [rsp+330h+cchWideChar], r12
0x18006f2f3  mov     [rsp+330h+lpWideCharStr], r14
0x18006f2f8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18006f2fd  jmp     loc_18006F197
0x18006f302  mov     ecx, 7F000001h; hostlong
0x18006f307  call    cs:__imp_htonl
0x18006f30d  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18006f314  mov     ebx, eax
0x18006f316  call    cs:__imp_RtlEnterCriticalSection
0x18006f31c  mov     rdx, cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x18006f323  mov     esi, 2
0x18006f328  test    rdx, rdx
0x18006f32b  jz      short loc_18006F34F
0x18006f32d  xor     ecx, ecx
0x18006f32f  cmp     [rdx], ecx
0x18006f331  jle     short loc_18006F34F
0x18006f333  mov     eax, ecx
0x18006f335  add     rax, rax
0x18006f338  mov     r8, [rdx+rax*8+8]
0x18006f33d  cmp     [r8], si
0x18006f341  jz      short loc_18006F34B
0x18006f343  inc     ecx
0x18006f345  cmp     ecx, [rdx]
0x18006f347  jl      short loc_18006F333
0x18006f349  jmp     short loc_18006F34F
0x18006f34b  mov     ebx, [r8+4]
0x18006f34f  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18006f356  call    cs:__imp_RtlLeaveCriticalSection
0x18006f35c  cmp     [rbp+230h+arg_28], 0
0x18006f363  lea     rax, [rbp+230h+Size]
0x18006f367  mov     r8b, [rbp+230h+var_2B0]; unsigned __int8
0x18006f36b  mov     rdx, rdi; struct _DOMAIN_INFO *
0x18006f36e  mov     rcx, r13; unsigned __int16 *
0x18006f371  jz      short loc_18006F3BB
0x18006f373  mov     [rsp+330h+var_2E0], rax; unsigned int *
0x18006f378  mov     r9d, esi; unsigned int
0x18006f37b  lea     rax, [rbp+230h+Src]
0x18006f37f  mov     [rsp+330h+var_2E8], rax; unsigned __int8 *
0x18006f384  mov     rax, [rbp+230h+var_290]
0x18006f388  mov     [rsp+330h+var_2F0], rax; struct sockaddr *
0x18006f38d  mov     rax, [rbp+230h+var_2A0]
0x18006f391  mov     [rsp+330h+var_2F8], ebx; unsigned int
0x18006f395  mov     [rsp+330h+var_300], rax; unsigned __int16 *
0x18006f39a  mov     rax, [rbp+230h+var_298]
0x18006f39e  mov     qword ptr [rsp+330h+cchWideChar], rax; unsigned __int16 *
0x18006f3a3  mov     dword ptr [rsp+330h+lpWideCharStr], r15d; unsigned int
0x18006f3a8  call    ?PrimaryQueryHandler@@YAEPEBGPEAU_DOMAIN_INFO@@EKK00KPEAUsockaddr@@QEAEPEAK@Z; PrimaryQueryHandler(ushort const *,_DOMAIN_INFO *,uchar,ulong,ulong,ushort const *,ushort const *,ulong,sockaddr *,uchar * const,ulong *)
0x18006f3ad  test    al, al
0x18006f3af  jnz     short loc_18006F413
0x18006f3b1  mov     ebx, 54Bh
0x18006f3b6  jmp     loc_18006F447
0x18006f3bb  mov     r9, [rbp+230h+var_288]; void *
0x18006f3bf  mov     [rsp+330h+var_2C0], rax; unsigned int *
0x18006f3c4  lea     rax, [rbp+230h+Src]
0x18006f3c8  mov     [rsp+330h+var_2C8], rax; unsigned __int8 *
0x18006f3cd  mov     rax, [rbp+230h+var_290]
0x18006f3d1  mov     [rsp+330h+var_2D0], rax; struct sockaddr *
0x18006f3d6  mov     eax, [rbp+230h+arg_48]
0x18006f3dc  mov     [rsp+330h+var_2D8], ebx; unsigned int
0x18006f3e0  mov     dword ptr [rsp+330h+var_2E0], eax; unsigned int
0x18006f3e4  mov     rax, [rbp+230h+var_2A0]
0x18006f3e8  mov     [rsp+330h+var_2E8], rax; unsigned __int16 *
0x18006f3ed  mov     rax, [rbp+230h+var_298]
0x18006f3f1  mov     [rsp+330h+var_2F0], rax; unsigned __int16 *
0x18006f3f6  mov     [rsp+330h+var_2F8], 0; unsigned int
0x18006f3fe  mov     [rsp+330h+var_300], r12; unsigned __int16 *
0x18006f403  mov     [rsp+330h+cchWideChar], r15d; unsigned int
0x18006f408  mov     dword ptr [rsp+330h+lpWideCharStr], esi; unsigned int
0x18006f40c  call    ?LogonRequestHandler@@YAEPEBGPEAU_DOMAIN_INFO@@EPEAXKK0K00KKPEAUsockaddr@@QEAEPEAK@Z; LogonRequestHandler(ushort const *,_DOMAIN_INFO *,uchar,void *,ulong,ulong,ushort const *,ulong,ushort const *,ushort const *,ulong,ulong,sockaddr *,uchar * const,ulong *)
0x18006f411  jmp     short loc_18006F3AD
0x18006f413  mov     ecx, dword ptr [rbp+230h+Size]
0x18006f416  call    NetpMemoryAllocate
0x18006f41b  mov     rcx, [rbp+230h+var_270]
0x18006f41f  mov     [rcx], rax
0x18006f422  test    rax, rax
0x18006f425  jnz     short loc_18006F42C
0x18006f427  lea     ebx, [rax+8]
0x18006f42a  jmp     short loc_18006F447
0x18006f42c  mov     r8d, dword ptr [rbp+230h+Size]; Size
0x18006f430  lea     rdx, [rbp+230h+Src]; Src
0x18006f434  mov     rcx, rax; void *
0x18006f437  call    memcpy_0
0x18006f43c  mov     rcx, [rbp+230h+var_268]
0x18006f440  xor     ebx, ebx
0x18006f442  mov     eax, dword ptr [rbp+230h+Size]
0x18006f445  mov     [rcx], eax
0x18006f447  test    rdi, rdi
0x18006f44a  jz      short loc_18006F454
0x18006f44c  mov     rcx, rdi; struct _DOMAIN_INFO *
0x18006f44f  call    ?NlDereferenceDomain@@YAXPEAU_DOMAIN_INFO@@@Z; NlDereferenceDomain(_DOMAIN_INFO *)
0x18006f454  mov     rcx, qword ptr [rbp+230h+Size+4]; Buffer
0x18006f458  test    rcx, rcx
0x18006f45b  jz      short loc_18006F463
0x18006f45d  call    cs:__imp_NetApiBufferFree
0x18006f463  mov     eax, ebx
0x18006f465  mov     rcx, [rbp+230h+var_50]
0x18006f46c  xor     rcx, rsp; StackCookie
  ... truncated ...
```
