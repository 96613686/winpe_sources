# NlGetLocalPingResponse(ushort const *,ushort const *,char const *,_GUID *,void *,int,ushort const *,ushort const *,ushort const *,ulong,ulong,ulong,sockaddr *,void * *,ulong *)

- ea: `0x180074294`
- end: `0x1800747c5`
- name: `?NlGetLocalPingResponse@@YAKPEBG0PEBDPEAU_GUID@@PEAXH000KKKPEAUsockaddr@@PEAPEAXPEAK@Z`
- size: `1329`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, PCWSTR SourceString, const char *, struct _GUID *Buf1, void *, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int, unsigned int, struct sockaddr *, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003ffd0`
- `0x18007ea48`

## callees

- `0x180003320`
- `0x180007518`
- `0x18000e910`
- `0x1800267ec`
- `0x180026fdc`
- `0x180027350`
- `0x180072cb4`
- `0x180074294`
- `0x1800795c4`
- `0x180089414`
- `0x180090204`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18007445d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18007445d`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800743f6`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x1800743f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007440b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800744af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007440b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800744af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007446f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007446f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007435d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007439d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007435d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007439d`
- `ntdll!RtlLeaveCriticalSection` at `0x1800745c1`
- `ntdll!RtlLeaveCriticalSection` at `0x180074686`
- `ntdll!RtlLeaveCriticalSection` at `0x1800745c1`
- `ntdll!RtlLeaveCriticalSection` at `0x180074686`
- `ntdll!RtlEnterCriticalSection` at `0x18007456f`
- `ntdll!RtlEnterCriticalSection` at `0x180074640`
- `ntdll!RtlEnterCriticalSection` at `0x18007456f`
- `ntdll!RtlEnterCriticalSection` at `0x180074640`
- `netutils!NetApiBufferFree` at `0x180074793`
- `netutils!NetApiBufferFree` at `0x180074793`
- `netutils!NetApiBufferAllocate` at `0x180074372`
- `netutils!NetApiBufferAllocate` at `0x180074372`
- `WS2_32!__imp_htonl` at `0x18007462b`
- `WS2_32!__imp_htonl` at `0x18007462b`

## string_xrefs

- `0x1800743e4`: `NtdsDelayedStartupCompletedEvent`
- `0x180074417`: `NtdsDelayedStartupCompletedEvent`
- `0x180074426`: `NlGetLocalPingResponse: Cannot OpenEvent %ws %ld\n`

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
  char Handler; // al
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
0x180074294  push    rbp
0x180074296  push    rbx
0x180074297  push    rsi
0x180074298  push    rdi
0x180074299  push    r12
0x18007429b  push    r13
0x18007429d  push    r14
0x18007429f  push    r15
0x1800742a1  lea     rbp, [rsp-1F8h]
0x1800742a9  sub     rsp, 2F8h
0x1800742b0  mov     rax, cs:__security_cookie
0x1800742b7  xor     rax, rsp
0x1800742ba  mov     [rbp+230h+var_50], rax
0x1800742c1  cmp     cs:?NlGlobalMemberWorkstation@@3HA, 0; int NlGlobalMemberWorkstation
0x1800742c8  mov     rdi, r9
0x1800742cb  mov     rax, [rbp+230h+arg_20]
0x1800742d2  mov     rsi, r8
0x1800742d5  mov     r15, [rbp+230h+arg_30]
0x1800742dc  mov     r14, rdx
0x1800742df  mov     r12, [rbp+230h+arg_40]
0x1800742e6  mov     r13, rcx
0x1800742e9  mov     [rbp+230h+var_288], rax
0x1800742ed  mov     rax, [rbp+230h+arg_38]
0x1800742f4  mov     [rbp+230h+var_2A0], rax
0x1800742f8  mov     rax, [rbp+230h+arg_60]
0x1800742ff  mov     [rbp+230h+var_290], rax
0x180074303  mov     rax, [rbp+230h+arg_68]
0x18007430a  mov     [rbp+230h+var_270], rax
0x18007430e  mov     rax, [rbp+230h+arg_70]
0x180074315  mov     [rbp+230h+var_268], rax
0x180074319  mov     [rbp+230h+var_298], r15
0x18007431d  mov     dword ptr [rbp+230h+Size], 0
0x180074324  mov     [rbp+230h+var_2B0], 0
0x180074328  mov     qword ptr [rbp+230h+Size+4], 0
0x180074330  jz      short loc_18007433C
0x180074332  mov     eax, 54Bh
0x180074337  jmp     loc_1800747A1
0x18007433c  test    rsi, rsi
0x18007433f  jz      short loc_1800743A9
0x180074341  mov     [rsp+330h+cchWideChar], 0; cchWideChar
0x180074349  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18007434d  xor     edx, edx; dwFlags
0x18007434f  mov     [rsp+330h+lpWideCharStr], 0; lpWideCharStr
0x180074358  mov     ecx, 0FDE9h; CodePage
0x18007435d  call    cs:__imp_MultiByteToWideChar
0x180074364  nop     dword ptr [rax+rax+00h]
0x180074369  lea     rdx, [rbp+230h+Size+4]; Buffer
0x18007436d  mov     ebx, eax
0x18007436f  lea     ecx, [rax+rax]; ByteCount
0x180074372  call    cs:__imp_NetApiBufferAllocate
0x180074379  nop     dword ptr [rax+rax+00h]
0x18007437e  test    eax, eax
0x180074380  jnz     short loc_1800743A9
0x180074382  mov     rax, qword ptr [rbp+230h+Size+4]
0x180074386  or      r9d, 0FFFFFFFFh; cbMultiByte
0x18007438a  mov     [rsp+330h+cchWideChar], ebx; cchWideChar
0x18007438e  mov     r8, rsi; lpMultiByteStr
0x180074391  xor     edx, edx; dwFlags
0x180074393  mov     [rsp+330h+lpWideCharStr], rax; lpWideCharStr
0x180074398  mov     ecx, 0FDE9h; CodePage
0x18007439d  call    cs:__imp_MultiByteToWideChar
0x1800743a4  nop     dword ptr [rax+rax+00h]
0x1800743a9  mov     rax, qword ptr [rbp+230h+Size+4]
0x1800743ad  lea     rdx, aReceivedPingFr; "Received ping from %ws(%ws) %ws %ws on "...
0x1800743b4  mov     r9, [rbp+230h+var_2A0]
0x1800743b8  mov     r8, r15
0x1800743bb  mov     [rsp+330h+var_300], r13
0x1800743c0  mov     ecx, 10h; unsigned int
0x1800743c5  mov     qword ptr [rsp+330h+cchWideChar], r12
0x1800743ca  mov     [rsp+330h+lpWideCharStr], rax
0x1800743cf  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800743d4  cmp     cs:?NlGlobalDsRunningUnknown@@3EA, 0; uchar NlGlobalDsRunningUnknown
0x1800743db  jz      loc_1800744F9
0x1800743e1  xorps   xmm0, xmm0
0x1800743e4  lea     r8, Name; "NtdsDelayedStartupCompletedEvent"
0x1800743eb  xor     edx, edx; bInheritHandle
0x1800743ed  mov     ecx, 100000h; dwDesiredAccess
0x1800743f2  movups  xmmword ptr [rbp+230h+Handles], xmm0
0x1800743f6  call    cs:__imp_OpenEventW
0x1800743fd  nop     dword ptr [rax+rax+00h]
0x180074402  mov     [rbp+230h+Handles], rax
0x180074406  test    rax, rax
0x180074409  jnz     short loc_180074439
0x18007440b  call    cs:__imp_GetLastError
0x180074412  nop     dword ptr [rax+rax+00h]
0x180074417  lea     r8, Name; "NtdsDelayedStartupCompletedEvent"
0x18007441e  mov     ecx, 100h; unsigned int
0x180074423  mov     r9d, eax
0x180074426  lea     rdx, aNlgetlocalping; "NlGetLocalPingResponse: Cannot OpenEven"...
0x18007442d  mov     ebx, eax
0x18007442f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180074434  jmp     loc_18007478A
0x180074439  mov     rax, cs:?NlGlobalTerminateEvent@@3PEAXEA; void * NlGlobalTerminateEvent
0x180074440  lea     rdx, [rbp+230h+Handles]; lpHandles
0x180074444  xor     r8d, r8d; bWaitAll
0x180074447  mov     [rbp+230h+Handles+8], rax
0x18007444b  mov     r9d, 124F80h; dwMilliseconds
0x180074451  mov     dword ptr [rsp+330h+lpWideCharStr], 0; bAlertable
0x180074459  lea     ecx, [r8+2]; nCount
0x18007445d  call    cs:__imp_WaitForMultipleObjectsEx
0x180074464  nop     dword ptr [rax+rax+00h]
0x180074469  mov     rcx, [rbp+230h+Handles]; hObject
0x18007446d  mov     ebx, eax
0x18007446f  call    cs:__imp_CloseHandle
0x180074476  nop     dword ptr [rax+rax+00h]
0x18007447b  test    ebx, ebx
0x18007447d  jz      short loc_1800744F2
0x18007447f  cmp     ebx, 1
0x180074482  jz      short loc_1800744E9
0x180074484  cmp     ebx, 102h
0x18007448a  jz      short loc_1800744D6
0x18007448c  cmp     ebx, 0FFFFFFFFh
0x18007448f  jz      short loc_1800744AF
0x180074491  mov     r8d, ebx
0x180074494  lea     rdx, aNlgetlocalping_0; "NlGetLocalPingResponse: Unknown status "...
0x18007449b  mov     ecx, 100h; unsigned int
0x1800744a0  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800744a5  mov     ebx, 54Bh
0x1800744aa  jmp     loc_18007478A
0x1800744af  call    cs:__imp_GetLastError
0x1800744b6  nop     dword ptr [rax+rax+00h]
0x1800744bb  lea     rdx, aNlgetlocalping_3; "NlGetLocalPingResponse: Wait for DS fai"...
0x1800744c2  mov     ecx, 100h; unsigned int
0x1800744c7  mov     r8d, eax
0x1800744ca  mov     ebx, eax
0x1800744cc  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800744d1  jmp     loc_18007478A
0x1800744d6  lea     rdx, aNlgetlocalping_1; "NlGetLocalPingResponse: DS took too lon"...
0x1800744dd  mov     ecx, 100h; unsigned int
0x1800744e2  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800744e7  jmp     short loc_1800744A5
0x1800744e9  lea     rdx, aNlgetlocalping_2; "NlGetLocalPingResponse: Netlogon shut d"...
0x1800744f0  jmp     short loc_1800744DD
0x1800744f2  mov     cs:?NlGlobalDsRunningUnknown@@3EA, 0; uchar NlGlobalDsRunningUnknown
0x1800744f9  mov     r15d, [rbp+230h+arg_58]
0x180074500  test    rsi, rsi
0x180074503  jnz     short loc_180074518
0x180074505  test    rdi, rdi
0x180074508  jnz     short loc_180074518
0x18007450a  test    r14, r14
0x18007450d  jnz     loc_1800745E7
0x180074513  jmp     loc_1800745D1
0x180074518  mov     r9b, 1; unsigned __int8
0x18007451b  lea     rax, [rbp+230h+var_2B0]
0x18007451f  mov     r8b, r9b; unsigned __int8
0x180074522  mov     [rsp+330h+lpWideCharStr], rax; unsigned __int8 *
0x180074527  mov     rdx, rdi; Buf1
0x18007452a  mov     rcx, rsi; char *
0x18007452d  call    ?NlFindDnsDomain@@YAPEAU_DOMAIN_INFO@@PEBDPEAU_GUID@@EEPEAE@Z; NlFindDnsDomain(char const *,_GUID *,uchar,uchar,uchar *)
0x180074532  mov     rdi, rax
0x180074535  test    rax, rax
0x180074538  jnz     loc_180074626
0x18007453e  test    r15d, r15d
0x180074541  jns     loc_1800745E2
0x180074547  cmp     [rbp+230h+var_288], rax
0x18007454b  jnz     loc_1800745E2
0x180074551  test    r12, r12
0x180074554  jnz     loc_1800745E2
0x18007455a  cmp     [rbp+230h+arg_48], r12d
0x180074561  jnz     short loc_1800745E2
0x180074563  test    rsi, rsi
0x180074566  jz      short loc_1800745E2
0x180074568  lea     rcx, ?NlGlobalDnsForestNameCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18007456f  call    cs:__imp_RtlEnterCriticalSection
0x180074576  nop     dword ptr [rax+rax+00h]
0x18007457b  mov     rdx, cs:?NlGlobalUtf8DnsForestName@@3PEADEA; char *
0x180074582  test    rdx, rdx
0x180074585  jz      short loc_180074598
0x180074587  mov     rcx, rsi; char *
0x18007458a  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x18007458f  test    eax, eax
0x180074591  jz      short loc_180074598
0x180074593  lea     ebx, [rdi+1]
0x180074596  jmp     short loc_1800745BA
0x180074598  mov     rdx, cs:?NlGlobalUtf8DnsForestNameAlias@@3PEADEA; char *
0x18007459f  xor     ebx, ebx
0x1800745a1  test    rdx, rdx
0x1800745a4  jz      short loc_1800745BA
0x1800745a6  mov     rcx, rsi; char *
0x1800745a9  call    ?NlEqualDnsNameUtf8@@YAHPEBD0@Z; NlEqualDnsNameUtf8(char const *,char const *)
0x1800745ae  test    eax, eax
0x1800745b0  jz      short loc_1800745BA
0x1800745b2  mov     ebx, 1
0x1800745b7  mov     [rbp+230h+var_2B0], bl
0x1800745ba  lea     rcx, ?NlGlobalDnsForestNameCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800745c1  call    cs:__imp_RtlLeaveCriticalSection
0x1800745c8  nop     dword ptr [rax+rax+00h]
0x1800745cd  test    ebx, ebx
0x1800745cf  jz      short loc_1800745E2
0x1800745d1  xor     ecx, ecx; SourceString
0x1800745d3  mov     dl, 1; unsigned __int8
0x1800745d5  call    ?NlFindNetbiosDomain@@YAPEAU_DOMAIN_INFO@@PEBGE@Z; NlFindNetbiosDomain(ushort const *,uchar)
0x1800745da  mov     rdi, rax
0x1800745dd  test    rax, rax
0x1800745e0  jnz     short loc_180074626
0x1800745e2  test    r14, r14
0x1800745e5  jz      short loc_1800745F9
0x1800745e7  xor     edx, edx; unsigned __int8
0x1800745e9  mov     rcx, r14; SourceString
0x1800745ec  call    ?NlFindNetbiosDomain@@YAPEAU_DOMAIN_INFO@@PEBGE@Z; NlFindNetbiosDomain(ushort const *,uchar)
0x1800745f1  mov     rdi, rax
0x1800745f4  test    rax, rax
0x1800745f7  jnz     short loc_180074626
0x1800745f9  mov     r9, qword ptr [rbp+230h+Size+4]
0x1800745fd  lea     rdx, aPingFromWsForD; "Ping from %ws for domain %ws %ws for %w"...
0x180074604  mov     r8, [rbp+230h+var_298]
0x180074608  mov     ecx, 100h; unsigned int
0x18007460d  mov     [rsp+330h+var_300], r13
0x180074612  mov     qword ptr [rsp+330h+cchWideChar], r12
0x180074617  mov     [rsp+330h+lpWideCharStr], r14
0x18007461c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180074621  jmp     loc_1800744A5
0x180074626  mov     ecx, 7F000001h; hostlong
0x18007462b  call    cs:__imp_htonl
0x180074632  nop     dword ptr [rax+rax+00h]
0x180074637  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18007463e  mov     ebx, eax
0x180074640  call    cs:__imp_RtlEnterCriticalSection
0x180074647  nop     dword ptr [rax+rax+00h]
0x18007464c  mov     rdx, cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x180074653  mov     esi, 2
0x180074658  test    rdx, rdx
0x18007465b  jz      short loc_18007467F
0x18007465d  xor     ecx, ecx
0x18007465f  cmp     [rdx], ecx
0x180074661  jle     short loc_18007467F
0x180074663  mov     eax, ecx
0x180074665  add     rax, rax
0x180074668  mov     r8, [rdx+rax*8+8]
0x18007466d  cmp     [r8], si
0x180074671  jz      short loc_18007467B
0x180074673  inc     ecx
0x180074675  cmp     ecx, [rdx]
0x180074677  jl      short loc_180074663
0x180074679  jmp     short loc_18007467F
0x18007467b  mov     ebx, [r8+4]
0x18007467f  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180074686  call    cs:__imp_RtlLeaveCriticalSection
0x18007468d  nop     dword ptr [rax+rax+00h]
0x180074692  cmp     [rbp+230h+arg_28], 0
0x180074699  lea     rax, [rbp+230h+Size]
0x18007469d  mov     r8b, [rbp+230h+var_2B0]; unsigned __int8
0x1800746a1  mov     rdx, rdi; struct _DOMAIN_INFO *
0x1800746a4  mov     rcx, r13; unsigned __int16 *
0x1800746a7  jz      short loc_1800746F1
0x1800746a9  mov     [rsp+330h+var_2E0], rax; unsigned int *
0x1800746ae  mov     r9d, esi; unsigned int
0x1800746b1  lea     rax, [rbp+230h+Src]
0x1800746b5  mov     [rsp+330h+var_2E8], rax; unsigned __int8 *
0x1800746ba  mov     rax, [rbp+230h+var_290]
0x1800746be  mov     [rsp+330h+var_2F0], rax; struct sockaddr *
0x1800746c3  mov     rax, [rbp+230h+var_2A0]
0x1800746c7  mov     [rsp+330h+var_2F8], ebx; unsigned int
0x1800746cb  mov     [rsp+330h+var_300], rax; unsigned __int16 *
0x1800746d0  mov     rax, [rbp+230h+var_298]
0x1800746d4  mov     qword ptr [rsp+330h+cchWideChar], rax; unsigned __int16 *
0x1800746d9  mov     dword ptr [rsp+330h+lpWideCharStr], r15d; unsigned int
0x1800746de  call    ?PrimaryQueryHandler@@YAEPEBGPEAU_DOMAIN_INFO@@EKK00KPEAUsockaddr@@QEAEPEAK@Z; PrimaryQueryHandler(ushort const *,_DOMAIN_INFO *,uchar,ulong,ulong,ushort const *,ushort const *,ulong,sockaddr *,uchar * const,ulong *)
0x1800746e3  test    al, al
0x1800746e5  jnz     short loc_180074749
0x1800746e7  mov     ebx, 54Bh
0x1800746ec  jmp     loc_18007477D
0x1800746f1  mov     r9, [rbp+230h+var_288]; void *
0x1800746f5  mov     [rsp+330h+var_2C0], rax; unsigned int *
0x1800746fa  lea     rax, [rbp+230h+Src]
0x1800746fe  mov     [rsp+330h+var_2C8], rax; unsigned __int8 *
0x180074703  mov     rax, [rbp+230h+var_290]
0x180074707  mov     [rsp+330h+var_2D0], rax; struct sockaddr *
0x18007470c  mov     eax, [rbp+230h+arg_48]
0x180074712  mov     [rsp+330h+var_2D8], ebx; unsigned int
0x180074716  mov     dword ptr [rsp+330h+var_2E0], eax; unsigned int
0x18007471a  mov     rax, [rbp+230h+var_2A0]
0x18007471e  mov     [rsp+330h+var_2E8], rax; unsigned __int16 *
0x180074723  mov     rax, [rbp+230h+var_298]
0x180074727  mov     [rsp+330h+var_2F0], rax; unsigned __int16 *
0x18007472c  mov     [rsp+330h+var_2F8], 0; unsigned int
0x180074734  mov     [rsp+330h+var_300], r12; unsigned __int16 *
0x180074739  mov     [rsp+330h+cchWideChar], r15d; unsigned int
0x18007473e  mov     dword ptr [rsp+330h+lpWideCharStr], esi; unsigned int
0x180074742  call    ?LogonRequestHandler@@YAEPEBGPEAU_DOMAIN_INFO@@EPEAXKK0K00KKPEAUsockaddr@@QEAEPEAK@Z; LogonRequestHandler(ushort const *,_DOMAIN_INFO *,uchar,void *,ulong,ulong,ushort const *,ulong,ushort const *,ushort const *,ulong,ulong,sockaddr *,uchar * const,ulong *)
0x180074747  jmp     short loc_1800746E3
0x180074749  mov     ecx, dword ptr [rbp+230h+Size]
0x18007474c  call    NetpMemoryAllocate
0x180074751  mov     rcx, [rbp+230h+var_270]
0x180074755  mov     [rcx], rax
0x180074758  test    rax, rax
0x18007475b  jnz     short loc_180074762
0x18007475d  lea     ebx, [rax+8]
0x180074760  jmp     short loc_18007477D
0x180074762  mov     r8d, dword ptr [rbp+230h+Size]; Size
0x180074766  lea     rdx, [rbp+230h+Src]; Src
0x18007476a  mov     rcx, rax; void *
0x18007476d  call    memcpy_0
0x180074772  mov     rcx, [rbp+230h+var_268]
0x180074776  xor     ebx, ebx
0x180074778  mov     eax, dword ptr [rbp+230h+Size]
0x18007477b  mov     [rcx], eax
0x18007477d  test    rdi, rdi
0x180074780  jz      short loc_18007478A
0x180074782  mov     rcx, rdi; struct _DOMAIN_INFO *
  ... truncated ...
```
