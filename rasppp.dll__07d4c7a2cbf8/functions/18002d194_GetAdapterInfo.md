# GetAdapterInfo

- ea: `0x18002d194`
- end: `0x18002d87f`
- name: `GetAdapterInfo`
- size: `1771`
- prototype: `__int64 __fastcall(ULONG IfIndex)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003153c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002a138`
- `0x18002cbb4`
- `0x18002d194`
- `0x180030da4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d3b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d3be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d3b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d3be`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d31f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d642`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d31f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d331`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d331`
- `WS2_32!__imp_htonl` at `0x18002d4ea`
- `WS2_32!__imp_htonl` at `0x18002d56a`
- `WS2_32!__imp_htonl` at `0x18002d6ae`
- `WS2_32!__imp_htonl` at `0x18002d746`
- `WS2_32!__imp_htonl` at `0x18002d4ea`
- `WS2_32!__imp_htonl` at `0x18002d56a`
- `WS2_32!__imp_htonl` at `0x18002d6ae`
- `WS2_32!__imp_htonl` at `0x18002d746`
- `WS2_32!__imp_inet_addr` at `0x18002d4a8`
- `WS2_32!__imp_inet_addr` at `0x18002d4b7`
- `WS2_32!__imp_inet_addr` at `0x18002d4cd`
- `WS2_32!__imp_inet_addr` at `0x18002d4dc`
- `WS2_32!__imp_inet_addr` at `0x18002d69d`
- `WS2_32!__imp_inet_addr` at `0x18002d73b`
- `WS2_32!__imp_inet_addr` at `0x18002d4a8`
- `WS2_32!__imp_inet_addr` at `0x18002d4b7`
- `WS2_32!__imp_inet_addr` at `0x18002d4cd`
- `WS2_32!__imp_inet_addr` at `0x18002d4dc`
- `WS2_32!__imp_inet_addr` at `0x18002d69d`
- `WS2_32!__imp_inet_addr` at `0x18002d73b`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18002d2b7`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18002d3cf`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18002d2b7`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18002d3cf`
- `IPHLPAPI!GetPerAdapterInfo` at `0x18002d5fe`
- `IPHLPAPI!GetPerAdapterInfo` at `0x18002d65f`
- `IPHLPAPI!GetPerAdapterInfo` at `0x18002d5fe`
- `IPHLPAPI!GetPerAdapterInfo` at `0x18002d65f`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18002d2ab`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18002d2ab`
- `IPHLPAPI!GetAdaptersInfo` at `0x18002d2d7`
- `IPHLPAPI!GetAdaptersInfo` at `0x18002d419`
- `IPHLPAPI!GetAdaptersInfo` at `0x18002d2d7`
- `IPHLPAPI!GetAdaptersInfo` at `0x18002d419`

## string_xrefs

- `0x18002d817`: `GetAdapterInfo: SetCurrentThreadCompartmentId failed and returned %d`
- `0x18002d86c`: `GetAdapterInfo: SetCurrentThreadCompartmentId failed and returned %d`

## pseudocode

```c
__int64 __fastcall GetAdapterInfo(ULONG IfIndex, __int64 a2, unsigned int *a3)
{
  unsigned int v3; // r14d
  struct _IP_ADAPTER_INFO *v5; // r12
  IP_PER_ADAPTER_INFO_W2KSP1 *v6; // r13
  unsigned int v7; // esi
  __int64 v8; // rcx
  unsigned int RoutingDomainIdForCompartment; // edi
  ULONG AdaptersInfo; // eax
  const wchar_t *v11; // rdx
  const CHAR *v12; // rcx
  struct _IP_ADAPTER_INFO *v13; // rax
  DWORD PerAdapterInfo; // eax
  const wchar_t *v15; // rdx
  const CHAR *v17; // rcx
  struct _IP_ADAPTER_INFO *v18; // rbx
  __int64 v19; // rdx
  const wchar_t *v20; // r8
  const CHAR *v21; // rcx
  unsigned int v22; // edi
  IP_PER_ADAPTER_INFO_W2KSP1 *v23; // rax
  unsigned int v24; // ebx
  struct _IP_ADDR_STRING *Next; // rcx
  unsigned int v26; // ebx
  ULONG SizePointer; // [rsp+40h] [rbp-C0h] BYREF
  int v28; // [rsp+44h] [rbp-BCh]
  NET_IF_COMPARTMENT_ID CompartmentId; // [rsp+48h] [rbp-B8h]
  unsigned int *v30; // [rsp+50h] [rbp-B0h]
  _OWORD v31[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v32; // [rsp+78h] [rbp-88h] BYREF
  __int128 v33; // [rsp+7Ch] [rbp-84h]
  __int128 v34; // [rsp+8Ch] [rbp-74h]
  int v35; // [rsp+9Ch] [rbp-64h]
  int v36; // [rsp+A0h] [rbp-60h] BYREF
  char v37[2044]; // [rsp+A4h] [rbp-5Ch] BYREF

  v3 = 0;
  v30 = a3;
  SizePointer = 0;
  v28 = 0;
  v36 = 0;
  v5 = 0;
  memset(v31, 0, sizeof(v31));
  v6 = 0;
  v7 = 0;
  memset_0(v37, 0, sizeof(v37));
  v8 = qword_18004C658;
  v32 = 0;
  v33 = 0;
  v35 = 0;
  v34 = 0;
  if ( qword_18004C648 || qword_18004C650 || qword_18004C658 )
  {
    CompartmentId = 1;
    RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(qword_18004C658, v31);
    if ( RoutingDomainIdForCompartment )
      goto LABEL_21;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( v8 )
    {
      LOWORD(v32) = 0;
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        v8,
        L"GetAdapterInfo",
        v31,
        0,
        &v32);
    }
  }
  else
  {
    TraceHlp("GetAdapterInfo");
  }
  CompartmentId = GetCurrentThreadCompartmentId();
  AdaptersInfo = SetCurrentThreadCompartmentId(1u);
  RoutingDomainIdForCompartment = AdaptersInfo;
  if ( AdaptersInfo )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004C650 )
      {
        v11 = L"GetAdapterInfo: SetCurrentThreadCompartmentId failed and returned %d";
        goto LABEL_83;
      }
      goto LABEL_22;
    }
    v12 = "GetAdapterInfo: SetCurrentThreadCompartmentId failed and returned %d";
    goto LABEL_85;
  }
  v28 = 1;
  SizePointer = 0;
  AdaptersInfo = GetAdaptersInfo(0, &SizePointer);
  RoutingDomainIdForCompartment = AdaptersInfo;
  if ( AdaptersInfo != 111 && AdaptersInfo )
    goto LABEL_12;
  v13 = (struct _IP_ADAPTER_INFO *)LocalAlloc(0x40u, SizePointer);
  v5 = v13;
  if ( !v13 )
    goto LABEL_17;
  AdaptersInfo = GetAdaptersInfo(v13, &SizePointer);
  RoutingDomainIdForCompartment = AdaptersInfo;
  if ( AdaptersInfo )
  {
LABEL_12:
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004C650 )
      {
        v11 = L"GetAdaptersInfo failed and returned %d";
LABEL_83:
        LOWORD(v32) = 0;
        LOWORD(v36) = 0;
        FormatRRASErrorString(&v36, v11, AdaptersInfo);
        ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          qword_18004C650,
          &v36,
          v31,
          0,
          &v32);
        goto LABEL_22;
      }
      goto LABEL_22;
    }
    v12 = "GetAdaptersInfo failed and returned %d";
    goto LABEL_85;
  }
  v18 = v5;
  while ( v18->Index != IfIndex )
  {
    v18 = v18->Next;
    if ( !v18 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        v19 = qword_18004C650;
        if ( qword_18004C650 )
        {
          v20 = L"Couldn't get info for the adapter";
          goto LABEL_37;
        }
        goto LABEL_40;
      }
      v21 = "Couldn't get info for the adapter";
      goto LABEL_39;
    }
  }
  v22 = 0;
  v7 = inet_addr(v18->IpAddressList.IpAddress.String);
  inet_addr(v18->GatewayList.IpAddress.String);
  if ( v18->HaveWins )
  {
    v22 = inet_addr(v18->PrimaryWinsServer.IpAddress.String);
    v3 = inet_addr(v18->SecondaryWinsServer.IpAddress.String);
  }
  if ( v22 == htonl(0x7F000001u) )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004C658 )
      {
        LOWORD(v36) = 0;
        LOWORD(v32) = 0;
        FormatRRASErrorString(&v36, L"GetAdapterInfo: replacing WINS1 with 0x%x since its loopback", v7);
        ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          qword_18004C658,
          &v36,
          v31,
          0,
          &v32);
      }
    }
    else
    {
      TraceHlp("GetAdapterInfo: replacing WINS1 with 0x%x since its loopback");
    }
  }
  if ( v3 == htonl(0x7F000001u) )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004C650 )
      {
        LOWORD(v36) = 0;
        LOWORD(v32) = 0;
        FormatRRASErrorString(&v36, L"GetAdapterInfo: replacing WINS2 with 0x%x since its loopback", v7);
        ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          qword_18004C650,
          &v36,
          v31,
          0,
          &v32);
      }
    }
    else
    {
      TraceHlp("GetAdapterInfo: replacing WINS2 with 0x%x since its loopback");
    }
  }
  SizePointer = 0;
  PerAdapterInfo = GetPerAdapterInfo(IfIndex, 0, &SizePointer);
  RoutingDomainIdForCompartment = PerAdapterInfo;
  if ( PerAdapterInfo != 111 )
  {
    if ( !gIsIphlpEtwTracingAvailable )
    {
      v17 = "GetPerAdapterInfo failed and returned %d";
LABEL_29:
      TraceHlp(v17);
      goto LABEL_21;
    }
    if ( qword_18004C650 )
    {
      v15 = L"GetPerAdapterInfo failed and returned %d";
LABEL_20:
      LOWORD(v32) = 0;
      LOWORD(v36) = 0;
      FormatRRASErrorString(&v36, v15, PerAdapterInfo);
      ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        qword_18004C650,
        &v36,
        v31,
        0,
        &v32);
    }
LABEL_21:
    if ( !RoutingDomainIdForCompartment )
      goto LABEL_23;
    goto LABEL_22;
  }
  v23 = (IP_PER_ADAPTER_INFO_W2KSP1 *)LocalAlloc(0x40u, SizePointer);
  v6 = v23;
  if ( !v23 )
  {
LABEL_17:
    PerAdapterInfo = GetLastError();
    RoutingDomainIdForCompartment = PerAdapterInfo;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004C650 )
        goto LABEL_21;
      v15 = L"LocalAlloc failed and returned %d";
      goto LABEL_20;
    }
    v17 = "LocalAlloc failed and returned %d";
    goto LABEL_29;
  }
  AdaptersInfo = GetPerAdapterInfo(IfIndex, v23, &SizePointer);
  RoutingDomainIdForCompartment = AdaptersInfo;
  if ( AdaptersInfo )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004C650 )
      {
        v11 = L"GetPerAdapterInfo failed and returned %d";
        goto LABEL_83;
      }
LABEL_22:
      v7 = 0;
      goto LABEL_23;
    }
    v12 = "GetPerAdapterInfo failed and returned %d";
LABEL_85:
    TraceHlp(v12);
    goto LABEL_22;
  }
  v24 = inet_addr(v6->DnsServerList.IpAddress.String);
  if ( v24 == htonl(0x7F000001u) )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( qword_18004C650 )
      {
        LOWORD(v36) = 0;
        LOWORD(v32) = 0;
        FormatRRASErrorString(&v36, L"GetAdapterInfo: replacing DNS1 with 0x%x since its loopback", v7);
        ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          qword_18004C650,
          &v36,
          v31,
          0,
          &v32);
      }
    }
    else
    {
      TraceHlp("GetAdapterInfo: replacing DNS1 with 0x%x since its loopback");
    }
  }
  Next = v6->DnsServerList.Next;
  if ( Next )
  {
    v26 = inet_addr(Next->IpAddress.String);
    if ( v26 == htonl(0x7F000001u) )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( qword_18004C650 )
        {
          LOWORD(v36) = 0;
          LOWORD(v32) = 0;
          FormatRRASErrorString(&v36, L"GetAdapterInfo: replacing DNS2 with 0x%x since its loopback", v7);
          ((void (__fastcall *)(__int64, __int64, int *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
            gIphlpEtwContext,
            qword_18004C650,
            &v36,
            v31,
            0,
            &v32);
        }
      }
      else
      {
        TraceHlp("GetAdapterInfo: replacing DNS2 with 0x%x since its loopback");
      }
    }
  }
  if ( ((v7 + 1) & 0xFFFFFFFE) == 0 )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      v19 = qword_18004C650;
      if ( qword_18004C650 )
      {
        v20 = L"Couldn't get IpAddress for the adapter";
LABEL_37:
        LOWORD(v32) = 0;
        ((void (__fastcall *)(__int64, __int64, const wchar_t *, _OWORD *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          v19,
          v20,
          v31,
          0,
          &v32);
      }
LABEL_40:
      RoutingDomainIdForCompartment = 1168;
      goto LABEL_22;
    }
    v21 = "Couldn't get IpAddress for the adapter";
LABEL_39:
    TraceHlp(v21);
    goto LABEL_40;
  }
LABEL_23:
  if ( v30 )
    *v30 = v7;
  LocalFree(v5);
  LocalFree(v6);
  if ( v28 )
    SetCurrentThreadCompartmentId(CompartmentId);
  return RoutingDomainIdForCompartment;
}

```

## disassembly

```asm
0x18002d194  mov     [rsp-8+arg_8], rbx
0x18002d199  push    rbp
0x18002d19a  push    rsi
0x18002d19b  push    rdi
0x18002d19c  push    r12
0x18002d19e  push    r13
0x18002d1a0  push    r14
0x18002d1a2  push    r15
0x18002d1a4  lea     rbp, [rsp-7B0h]
0x18002d1ac  sub     rsp, 8B0h
0x18002d1b3  mov     rax, cs:__security_cookie
0x18002d1ba  xor     rax, rsp
0x18002d1bd  mov     [rbp+7E0h+var_40], rax
0x18002d1c4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002d1cb  xor     r14d, r14d
0x18002d1ce  mov     [rsp+8E0h+var_890], r8
0x18002d1d3  mov     r15d, ecx
0x18002d1d6  mov     [rsp+8E0h+SizePointer], r14d
0x18002d1db  xor     edx, edx; Val
0x18002d1dd  mov     [rsp+8E0h+var_89C], r14d
0x18002d1e2  mov     r8d, 7FCh; Size
0x18002d1e8  mov     [rbp+7E0h+var_840], r14d
0x18002d1ec  lea     rcx, [rbp+7E0h+var_83C]; void *
0x18002d1f0  mov     r12d, r14d
0x18002d1f3  movdqu  [rsp+8E0h+var_888], xmm0
0x18002d1f9  mov     r13d, r14d
0x18002d1fc  mov     esi, r14d
0x18002d1ff  call    memset_0
0x18002d204  mov     rcx, cs:qword_18004C658
0x18002d20b  xor     eax, eax
0x18002d20d  cmp     cs:qword_18004C648, r14
0x18002d214  xorps   xmm0, xmm0
0x18002d217  mov     [rsp+8E0h+var_868], r14d
0x18002d21c  movups  [rsp+8E0h+var_864], xmm0
0x18002d221  lea     ebx, [rax+1]
0x18002d224  mov     [rbp+7E0h+var_844], eax
0x18002d227  movups  [rbp+7E0h+var_854], xmm0
0x18002d22b  movups  [rsp+8E0h+var_878], xmm0
0x18002d230  jnz     short loc_18002D240
0x18002d232  cmp     cs:qword_18004C650, r14
0x18002d239  jnz     short loc_18002D240
0x18002d23b  test    rcx, rcx
0x18002d23e  jz      short loc_18002D258
0x18002d240  lea     rdx, [rsp+8E0h+var_888]
0x18002d245  mov     [rsp+8E0h+CompartmentId], ebx
0x18002d249  call    NsiGetRoutingDomainIdForCompartment
0x18002d24e  mov     edi, eax
0x18002d250  test    eax, eax
0x18002d252  jnz     loc_18002D39F
0x18002d258  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18002d25f  jz      short loc_18002D29F
0x18002d261  test    rcx, rcx
0x18002d264  jz      short loc_18002D2AB
0x18002d266  lea     rax, [rsp+8E0h+var_868]
0x18002d26b  mov     word ptr [rsp+8E0h+var_868], r14w
0x18002d271  mov     [rsp+8E0h+var_8B8], rax
0x18002d276  lea     r9, [rsp+8E0h+var_888]
0x18002d27b  mov     rax, cs:gIphlpParamTemplateFunc
0x18002d282  lea     r8, aGetadapterinfo; "GetAdapterInfo"
0x18002d289  mov     rdx, rcx
0x18002d28c  mov     [rsp+8E0h+var_8C0], r14
0x18002d291  mov     rcx, cs:gIphlpEtwContext
0x18002d298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d29d  jmp     short loc_18002D2AB
0x18002d29f  lea     rcx, aGetadapterinfo_6; "GetAdapterInfo"
0x18002d2a6  call    TraceHlp
0x18002d2ab  call    cs:__imp_GetCurrentThreadCompartmentId
0x18002d2b1  mov     ecx, ebx; CompartmentId
0x18002d2b3  mov     [rsp+8E0h+CompartmentId], eax
0x18002d2b7  call    cs:__imp_SetCurrentThreadCompartmentId
0x18002d2bd  mov     edi, eax
0x18002d2bf  test    eax, eax
0x18002d2c1  jnz     loc_18002D801
0x18002d2c7  lea     rdx, [rsp+8E0h+SizePointer]; SizePointer
0x18002d2cc  mov     [rsp+8E0h+var_89C], ebx
0x18002d2d0  xor     ecx, ecx; AdapterInfo
0x18002d2d2  mov     [rsp+8E0h+SizePointer], r14d
0x18002d2d7  call    cs:__imp_GetAdaptersInfo
0x18002d2dd  mov     edi, eax
0x18002d2df  cmp     eax, 6Fh ; 'o'
0x18002d2e2  jz      short loc_18002D316
0x18002d2e4  test    eax, eax
0x18002d2e6  jz      short loc_18002D316
0x18002d2e8  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18002d2ef  jz      short loc_18002D30A
0x18002d2f1  cmp     cs:qword_18004C650, r14
0x18002d2f8  jz      loc_18002D3A3
0x18002d2fe  lea     rdx, aGetadaptersinf; "GetAdaptersInfo failed and returned %d"
0x18002d305  jmp     loc_18002D81E
0x18002d30a  lea     rcx, aGetadaptersinf_0; "GetAdaptersInfo failed and returned %d"
0x18002d311  jmp     loc_18002D873
0x18002d316  mov     edx, [rsp+8E0h+SizePointer]; uBytes
0x18002d31a  mov     ecx, 40h ; '@'; uFlags
0x18002d31f  call    cs:__imp_LocalAlloc
0x18002d325  mov     r12, rax
0x18002d328  test    rax, rax
0x18002d32b  jnz     loc_18002D411
0x18002d331  call    cs:__imp_GetLastError
0x18002d337  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18002d33e  mov     edi, eax
0x18002d340  jz      loc_18002D401
0x18002d346  cmp     cs:qword_18004C650, r14
0x18002d34d  jz      short loc_18002D39F
0x18002d34f  lea     rdx, aLocalallocFail_1; "LocalAlloc failed and returned %d"
0x18002d356  mov     r8d, eax
0x18002d359  mov     word ptr [rsp+8E0h+var_868], r14w
0x18002d35f  lea     rcx, [rbp+7E0h+var_840]
0x18002d363  mov     word ptr [rbp+7E0h+var_840], r14w
0x18002d368  call    FormatRRASErrorString
0x18002d36d  mov     rdx, cs:qword_18004C650
0x18002d374  lea     rax, [rsp+8E0h+var_868]
0x18002d379  mov     rcx, cs:gIphlpEtwContext
0x18002d380  lea     r9, [rsp+8E0h+var_888]
0x18002d385  mov     [rsp+8E0h+var_8B8], rax
0x18002d38a  lea     r8, [rbp+7E0h+var_840]
0x18002d38e  mov     rax, cs:gIphlpParamTemplateFunc
0x18002d395  mov     [rsp+8E0h+var_8C0], r14
0x18002d39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d39f  test    edi, edi
0x18002d3a1  jz      short loc_18002D3A6
0x18002d3a3  mov     esi, r14d
0x18002d3a6  mov     rax, [rsp+8E0h+var_890]
0x18002d3ab  test    rax, rax
0x18002d3ae  jz      short loc_18002D3B2
0x18002d3b0  mov     [rax], esi
0x18002d3b2  mov     rcx, r12; hMem
0x18002d3b5  call    cs:__imp_LocalFree
0x18002d3bb  mov     rcx, r13; hMem
0x18002d3be  call    cs:__imp_LocalFree
0x18002d3c4  cmp     [rsp+8E0h+var_89C], r14d
0x18002d3c9  jz      short loc_18002D3D5
0x18002d3cb  mov     ecx, [rsp+8E0h+CompartmentId]; CompartmentId
0x18002d3cf  call    cs:__imp_SetCurrentThreadCompartmentId
0x18002d3d5  mov     eax, edi
0x18002d3d7  mov     rcx, [rbp+7E0h+var_40]
0x18002d3de  xor     rcx, rsp; StackCookie
0x18002d3e1  call    __security_check_cookie
0x18002d3e6  mov     rbx, [rsp+8E0h+arg_8]
0x18002d3ee  add     rsp, 8B0h
0x18002d3f5  pop     r15
0x18002d3f7  pop     r14
0x18002d3f9  pop     r13
0x18002d3fb  pop     r12
0x18002d3fd  pop     rdi
0x18002d3fe  pop     rsi
0x18002d3ff  pop     rbp
0x18002d400  retn
0x18002d401  lea     rcx, aLocalallocFail; "LocalAlloc failed and returned %d"
0x18002d408  mov     edx, eax
0x18002d40a  call    TraceHlp
0x18002d40f  jmp     short loc_18002D39F
0x18002d411  lea     rdx, [rsp+8E0h+SizePointer]; SizePointer
0x18002d416  mov     rcx, r12; AdapterInfo
0x18002d419  call    cs:__imp_GetAdaptersInfo
0x18002d41f  mov     edi, eax
0x18002d421  test    eax, eax
0x18002d423  jnz     loc_18002D2E8
0x18002d429  mov     rbx, r12
0x18002d42c  cmp     [rbx+1A0h], r15d
0x18002d433  jz      short loc_18002D49E
0x18002d435  mov     rbx, [rbx]
0x18002d438  test    rbx, rbx
0x18002d43b  jnz     short loc_18002D42C
0x18002d43d  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18002d444  jz      short loc_18002D488
0x18002d446  mov     rdx, cs:qword_18004C650
0x18002d44d  test    rdx, rdx
0x18002d450  jz      short loc_18002D494
0x18002d452  lea     r8, aCouldnTGetInfo_0; "Couldn't get info for the adapter"
0x18002d459  mov     rcx, cs:gIphlpEtwContext
0x18002d460  lea     rax, [rsp+8E0h+var_868]
0x18002d465  mov     [rsp+8E0h+var_8B8], rax
0x18002d46a  lea     r9, [rsp+8E0h+var_888]
0x18002d46f  mov     rax, cs:gIphlpParamTemplateFunc
0x18002d476  mov     [rsp+8E0h+var_8C0], r14
0x18002d47b  mov     word ptr [rsp+8E0h+var_868], r14w
0x18002d481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d486  jmp     short loc_18002D494
0x18002d488  lea     rcx, aCouldnTGetInfo; "Couldn't get info for the adapter"
0x18002d48f  call    TraceHlp
0x18002d494  mov     edi, 490h
0x18002d499  jmp     loc_18002D3A3
0x18002d49e  lea     rcx, [rbx+1C0h]; cp
0x18002d4a5  mov     edi, r14d
0x18002d4a8  call    cs:__imp_inet_addr
0x18002d4ae  lea     rcx, [rbx+1F0h]; cp
0x18002d4b5  mov     esi, eax
0x18002d4b7  call    cs:__imp_inet_addr
0x18002d4bd  cmp     [rbx+248h], r14d
0x18002d4c4  jz      short loc_18002D4E5
0x18002d4c6  lea     rcx, [rbx+258h]; cp
0x18002d4cd  call    cs:__imp_inet_addr
0x18002d4d3  lea     rcx, [rbx+288h]; cp
0x18002d4da  mov     edi, eax
0x18002d4dc  call    cs:__imp_inet_addr
0x18002d4e2  mov     r14d, eax
0x18002d4e5  mov     ecx, 7F000001h; hostlong
0x18002d4ea  call    cs:__imp_htonl
0x18002d4f0  cmp     edi, eax
0x18002d4f2  jnz     short loc_18002D565
0x18002d4f4  xor     ebx, ebx
0x18002d4f6  cmp     cs:gIsIphlpEtwTracingAvailable, ebx
0x18002d4fc  jz      short loc_18002D557
0x18002d4fe  cmp     cs:qword_18004C658, rbx
0x18002d505  jz      short loc_18002D565
0x18002d507  mov     r8d, esi
0x18002d50a  mov     word ptr [rbp+7E0h+var_840], bx
0x18002d50e  lea     rdx, aGetadapterinfo_7; "GetAdapterInfo: replacing WINS1 with 0x"...
0x18002d515  mov     word ptr [rsp+8E0h+var_868], bx
0x18002d51a  lea     rcx, [rbp+7E0h+var_840]
0x18002d51e  call    FormatRRASErrorString
0x18002d523  mov     rdx, cs:qword_18004C658
0x18002d52a  lea     rax, [rsp+8E0h+var_868]
0x18002d52f  mov     rcx, cs:gIphlpEtwContext
0x18002d536  lea     r9, [rsp+8E0h+var_888]
0x18002d53b  mov     [rsp+8E0h+var_8B8], rax
0x18002d540  lea     r8, [rbp+7E0h+var_840]
0x18002d544  mov     rax, cs:gIphlpParamTemplateFunc
0x18002d54b  mov     [rsp+8E0h+var_8C0], rbx
0x18002d550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d555  jmp     short loc_18002D565
0x18002d557  mov     edx, esi
0x18002d559  lea     rcx, aGetadapterinfo_5; "GetAdapterInfo: replacing WINS1 with 0x"...
0x18002d560  call    TraceHlp
0x18002d565  mov     ecx, 7F000001h; hostlong
0x18002d56a  call    cs:__imp_htonl
0x18002d570  cmp     r14d, eax
0x18002d573  jnz     short loc_18002D5EC
0x18002d575  xor     r14d, r14d
0x18002d578  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18002d57f  jz      short loc_18002D5DC
0x18002d581  cmp     cs:qword_18004C650, r14
0x18002d588  jz      short loc_18002D5EF
0x18002d58a  mov     r8d, esi
0x18002d58d  mov     word ptr [rbp+7E0h+var_840], r14w
0x18002d592  lea     rdx, aGetadapterinfo_8; "GetAdapterInfo: replacing WINS2 with 0x"...
0x18002d599  mov     word ptr [rsp+8E0h+var_868], r14w
0x18002d59f  lea     rcx, [rbp+7E0h+var_840]
0x18002d5a3  call    FormatRRASErrorString
0x18002d5a8  mov     rdx, cs:qword_18004C650
0x18002d5af  lea     rax, [rsp+8E0h+var_868]
0x18002d5b4  mov     rcx, cs:gIphlpEtwContext
0x18002d5bb  lea     r9, [rsp+8E0h+var_888]
0x18002d5c0  mov     [rsp+8E0h+var_8B8], rax
0x18002d5c5  lea     r8, [rbp+7E0h+var_840]
0x18002d5c9  mov     rax, cs:gIphlpParamTemplateFunc
0x18002d5d0  mov     [rsp+8E0h+var_8C0], r14
0x18002d5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d5da  jmp     short loc_18002D5EF
0x18002d5dc  mov     edx, esi
0x18002d5de  lea     rcx, aGetadapterinfo_4; "GetAdapterInfo: replacing WINS2 with 0x"...
0x18002d5e5  call    TraceHlp
0x18002d5ea  jmp     short loc_18002D5EF
0x18002d5ec  xor     r14d, r14d
0x18002d5ef  lea     r8, [rsp+8E0h+SizePointer]; pOutBufLen
0x18002d5f4  mov     [rsp+8E0h+SizePointer], r14d
0x18002d5f9  xor     edx, edx; pPerAdapterInfo
0x18002d5fb  mov     ecx, r15d; IfIndex
0x18002d5fe  call    cs:__imp_GetPerAdapterInfo
0x18002d604  mov     edi, eax
0x18002d606  cmp     eax, 6Fh ; 'o'
0x18002d609  jz      short loc_18002D639
0x18002d60b  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18002d612  jz      short loc_18002D62D
0x18002d614  cmp     cs:qword_18004C650, r14
0x18002d61b  jz      loc_18002D39F
0x18002d621  lea     rdx, aGetperadapteri_0; "GetPerAdapterInfo failed and returned %"...
0x18002d628  jmp     loc_18002D356
0x18002d62d  lea     rcx, aGetperadapteri; "GetPerAdapterInfo failed and returned %"...
0x18002d634  jmp     loc_18002D408
0x18002d639  mov     edx, [rsp+8E0h+SizePointer]; uBytes
0x18002d63d  mov     ecx, 40h ; '@'; uFlags
0x18002d642  call    cs:__imp_LocalAlloc
0x18002d648  mov     r13, rax
0x18002d64b  test    rax, rax
0x18002d64e  jz      loc_18002D331
0x18002d654  lea     r8, [rsp+8E0h+SizePointer]; pOutBufLen
0x18002d659  mov     rdx, rax; pPerAdapterInfo
0x18002d65c  mov     ecx, r15d; IfIndex
0x18002d65f  call    cs:__imp_GetPerAdapterInfo
0x18002d665  mov     edi, eax
0x18002d667  test    eax, eax
0x18002d669  jz      short loc_18002D699
0x18002d66b  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18002d672  jz      short loc_18002D68D
0x18002d674  cmp     cs:qword_18004C650, r14
0x18002d67b  jz      loc_18002D3A3
0x18002d681  lea     rdx, aGetperadapteri_0; "GetPerAdapterInfo failed and returned %"...
0x18002d688  jmp     loc_18002D81E
0x18002d68d  lea     rcx, aGetperadapteri; "GetPerAdapterInfo failed and returned %"...
0x18002d694  jmp     loc_18002D873
0x18002d699  lea     rcx, [r13+18h]; cp
0x18002d69d  call    cs:__imp_inet_addr
0x18002d6a3  mov     r15d, 7F000001h
0x18002d6a9  mov     ebx, eax
0x18002d6ab  mov     ecx, r15d; hostlong
0x18002d6ae  call    cs:__imp_htonl
0x18002d6b4  cmp     ebx, eax
0x18002d6b6  jnz     short loc_18002D72A
0x18002d6b8  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
  ... truncated ...
```
