# GetAdapterInfo

- ea: `0x18002e3cc`
- end: `0x18002eb3f`
- name: `GetAdapterInfo`
- size: `1907`
- prototype: `__int64 __fastcall(ULONG IfIndex, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180032b1c`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x18002b0dc`
- `0x18002dcfc`
- `0x18002e3cc`
- `0x18003230c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e60b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e61a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e60b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e61a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e569`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e8de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e569`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002e8de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e581`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e581`
- `WS2_32!__imp_htonl` at `0x18002e774`
- `WS2_32!__imp_htonl` at `0x18002e7fa`
- `WS2_32!__imp_htonl` at `0x18002e95c`
- `WS2_32!__imp_htonl` at `0x18002ea00`
- `WS2_32!__imp_htonl` at `0x18002e774`
- `WS2_32!__imp_htonl` at `0x18002e7fa`
- `WS2_32!__imp_htonl` at `0x18002e95c`
- `WS2_32!__imp_htonl` at `0x18002ea00`
- `WS2_32!__imp_inet_addr` at `0x18002e71a`
- `WS2_32!__imp_inet_addr` at `0x18002e72f`
- `WS2_32!__imp_inet_addr` at `0x18002e74b`
- `WS2_32!__imp_inet_addr` at `0x18002e760`
- `WS2_32!__imp_inet_addr` at `0x18002e945`
- `WS2_32!__imp_inet_addr` at `0x18002e9ef`
- `WS2_32!__imp_inet_addr` at `0x18002e71a`
- `WS2_32!__imp_inet_addr` at `0x18002e72f`
- `WS2_32!__imp_inet_addr` at `0x18002e74b`
- `WS2_32!__imp_inet_addr` at `0x18002e760`
- `WS2_32!__imp_inet_addr` at `0x18002e945`
- `WS2_32!__imp_inet_addr` at `0x18002e9ef`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18002e4f5`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18002e631`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18002e4f5`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x18002e631`
- `IPHLPAPI!GetPerAdapterInfo` at `0x18002e894`
- `IPHLPAPI!GetPerAdapterInfo` at `0x18002e901`
- `IPHLPAPI!GetPerAdapterInfo` at `0x18002e894`
- `IPHLPAPI!GetPerAdapterInfo` at `0x18002e901`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18002e4e3`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18002e4e3`
- `IPHLPAPI!GetAdaptersInfo` at `0x18002e51b`
- `IPHLPAPI!GetAdaptersInfo` at `0x18002e685`
- `IPHLPAPI!GetAdaptersInfo` at `0x18002e51b`
- `IPHLPAPI!GetAdaptersInfo` at `0x18002e685`

## string_xrefs

- `0x18002ead7`: `GetAdapterInfo: SetCurrentThreadCompartmentId failed and returned %d`
- `0x18002eb2c`: `GetAdapterInfo: SetCurrentThreadCompartmentId failed and returned %d`

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
  GUID v31[2]; // [rsp+58h] [rbp-A8h] BYREF
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
  v8 = qword_18004D658;
  v32 = 0;
  v33 = 0;
  v35 = 0;
  v34 = 0;
  if ( xmmword_18004D648 != 0 || qword_18004D658 )
  {
    CompartmentId = 1;
    RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(qword_18004D658, v31);
    if ( RoutingDomainIdForCompartment )
      goto LABEL_20;
  }
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( v8 )
    {
      LOWORD(v32) = 0;
      ((void (__fastcall *)(__int64, __int64, const wchar_t *, GUID *, _QWORD, int *))gIphlpParamTemplateFunc)(
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
      if ( *((_QWORD *)&xmmword_18004D648 + 1) )
      {
        v11 = L"GetAdapterInfo: SetCurrentThreadCompartmentId failed and returned %d";
        goto LABEL_82;
      }
      goto LABEL_21;
    }
    v12 = "GetAdapterInfo: SetCurrentThreadCompartmentId failed and returned %d";
    goto LABEL_84;
  }
  v28 = 1;
  SizePointer = 0;
  AdaptersInfo = GetAdaptersInfo(0, &SizePointer);
  RoutingDomainIdForCompartment = AdaptersInfo;
  if ( AdaptersInfo != 111 && AdaptersInfo )
    goto LABEL_11;
  v13 = (struct _IP_ADAPTER_INFO *)LocalAlloc(0x40u, SizePointer);
  v5 = v13;
  if ( !v13 )
    goto LABEL_16;
  AdaptersInfo = GetAdaptersInfo(v13, &SizePointer);
  RoutingDomainIdForCompartment = AdaptersInfo;
  if ( AdaptersInfo )
  {
LABEL_11:
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_18004D648 + 1) )
      {
        v11 = L"GetAdaptersInfo failed and returned %d";
LABEL_82:
        LOWORD(v32) = 0;
        LOWORD(v36) = 0;
        FormatRRASErrorString((wchar_t *)&v36, v11, AdaptersInfo);
        ((void (__fastcall *)(__int64, _QWORD, int *, GUID *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_18004D648 + 1),
          &v36,
          v31,
          0,
          &v32);
        goto LABEL_21;
      }
      goto LABEL_21;
    }
    v12 = "GetAdaptersInfo failed and returned %d";
    goto LABEL_84;
  }
  v18 = v5;
  while ( v18->Index != IfIndex )
  {
    v18 = v18->Next;
    if ( !v18 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        v19 = *((_QWORD *)&xmmword_18004D648 + 1);
        if ( *((_QWORD *)&xmmword_18004D648 + 1) )
        {
          v20 = L"Couldn't get info for the adapter";
          goto LABEL_36;
        }
        goto LABEL_39;
      }
      v21 = "Couldn't get info for the adapter";
      goto LABEL_38;
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
      if ( qword_18004D658 )
      {
        LOWORD(v36) = 0;
        LOWORD(v32) = 0;
        FormatRRASErrorString((wchar_t *)&v36, L"GetAdapterInfo: replacing WINS1 with 0x%x since its loopback", v7);
        ((void (__fastcall *)(__int64, __int64, int *, GUID *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          qword_18004D658,
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
      if ( *((_QWORD *)&xmmword_18004D648 + 1) )
      {
        LOWORD(v36) = 0;
        LOWORD(v32) = 0;
        FormatRRASErrorString((wchar_t *)&v36, L"GetAdapterInfo: replacing WINS2 with 0x%x since its loopback", v7);
        ((void (__fastcall *)(__int64, _QWORD, int *, GUID *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_18004D648 + 1),
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
LABEL_28:
      TraceHlp(v17);
      goto LABEL_20;
    }
    if ( *((_QWORD *)&xmmword_18004D648 + 1) )
    {
      v15 = L"GetPerAdapterInfo failed and returned %d";
LABEL_19:
      LOWORD(v32) = 0;
      LOWORD(v36) = 0;
      FormatRRASErrorString((wchar_t *)&v36, v15, PerAdapterInfo);
      ((void (__fastcall *)(__int64, _QWORD, int *, GUID *, _QWORD, int *))gIphlpParamTemplateFunc)(
        gIphlpEtwContext,
        *((_QWORD *)&xmmword_18004D648 + 1),
        &v36,
        v31,
        0,
        &v32);
    }
LABEL_20:
    if ( !RoutingDomainIdForCompartment )
      goto LABEL_22;
    goto LABEL_21;
  }
  v23 = (IP_PER_ADAPTER_INFO_W2KSP1 *)LocalAlloc(0x40u, SizePointer);
  v6 = v23;
  if ( !v23 )
  {
LABEL_16:
    PerAdapterInfo = GetLastError();
    RoutingDomainIdForCompartment = PerAdapterInfo;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !*((_QWORD *)&xmmword_18004D648 + 1) )
        goto LABEL_20;
      v15 = L"LocalAlloc failed and returned %d";
      goto LABEL_19;
    }
    v17 = "LocalAlloc failed and returned %d";
    goto LABEL_28;
  }
  AdaptersInfo = GetPerAdapterInfo(IfIndex, v23, &SizePointer);
  RoutingDomainIdForCompartment = AdaptersInfo;
  if ( AdaptersInfo )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_18004D648 + 1) )
      {
        v11 = L"GetPerAdapterInfo failed and returned %d";
        goto LABEL_82;
      }
LABEL_21:
      v7 = 0;
      goto LABEL_22;
    }
    v12 = "GetPerAdapterInfo failed and returned %d";
LABEL_84:
    TraceHlp(v12);
    goto LABEL_21;
  }
  v24 = inet_addr(v6->DnsServerList.IpAddress.String);
  if ( v24 == htonl(0x7F000001u) )
  {
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( *((_QWORD *)&xmmword_18004D648 + 1) )
      {
        LOWORD(v36) = 0;
        LOWORD(v32) = 0;
        FormatRRASErrorString((wchar_t *)&v36, L"GetAdapterInfo: replacing DNS1 with 0x%x since its loopback", v7);
        ((void (__fastcall *)(__int64, _QWORD, int *, GUID *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          *((_QWORD *)&xmmword_18004D648 + 1),
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
        if ( *((_QWORD *)&xmmword_18004D648 + 1) )
        {
          LOWORD(v36) = 0;
          LOWORD(v32) = 0;
          FormatRRASErrorString((wchar_t *)&v36, L"GetAdapterInfo: replacing DNS2 with 0x%x since its loopback", v7);
          ((void (__fastcall *)(__int64, _QWORD, int *, GUID *, _QWORD, int *))gIphlpParamTemplateFunc)(
            gIphlpEtwContext,
            *((_QWORD *)&xmmword_18004D648 + 1),
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
      v19 = *((_QWORD *)&xmmword_18004D648 + 1);
      if ( *((_QWORD *)&xmmword_18004D648 + 1) )
      {
        v20 = L"Couldn't get IpAddress for the adapter";
LABEL_36:
        LOWORD(v32) = 0;
        ((void (__fastcall *)(__int64, __int64, const wchar_t *, GUID *, _QWORD, int *))gIphlpParamTemplateFunc)(
          gIphlpEtwContext,
          v19,
          v20,
          v31,
          0,
          &v32);
      }
LABEL_39:
      RoutingDomainIdForCompartment = 1168;
      goto LABEL_21;
    }
    v21 = "Couldn't get IpAddress for the adapter";
LABEL_38:
    TraceHlp(v21);
    goto LABEL_39;
  }
LABEL_22:
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
0x18002e3cc  mov     [rsp-8+arg_8], rbx
0x18002e3d1  push    rbp
0x18002e3d2  push    rsi
0x18002e3d3  push    rdi
0x18002e3d4  push    r12
0x18002e3d6  push    r13
0x18002e3d8  push    r14
0x18002e3da  push    r15
0x18002e3dc  lea     rbp, [rsp-7B0h]
0x18002e3e4  sub     rsp, 8B0h
0x18002e3eb  mov     rax, cs:__security_cookie
0x18002e3f2  xor     rax, rsp
0x18002e3f5  mov     [rbp+7E0h+var_40], rax
0x18002e3fc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18002e403  xor     r14d, r14d
0x18002e406  mov     [rsp+8E0h+var_890], r8
0x18002e40b  mov     r15d, ecx
0x18002e40e  mov     [rsp+8E0h+SizePointer], r14d
0x18002e413  xor     edx, edx; Val
0x18002e415  mov     [rsp+8E0h+var_89C], r14d
0x18002e41a  mov     r8d, 7FCh; Size
0x18002e420  mov     [rbp+7E0h+var_840], r14d
0x18002e424  lea     rcx, [rbp+7E0h+var_83C]; void *
0x18002e428  mov     r12d, r14d
0x18002e42b  movdqu  [rsp+8E0h+var_888], xmm0
0x18002e431  mov     r13d, r14d
0x18002e434  mov     esi, r14d
0x18002e437  call    memset_0
0x18002e43c  mov     rcx, cs:qword_18004D658
0x18002e443  xor     eax, eax
0x18002e445  cmp     qword ptr cs:xmmword_18004D648, r14
0x18002e44c  xorps   xmm0, xmm0
0x18002e44f  mov     [rsp+8E0h+var_868], r14d
0x18002e454  movups  [rsp+8E0h+var_864], xmm0
0x18002e459  lea     ebx, [rax+1]
0x18002e45c  mov     [rbp+7E0h+var_844], eax
0x18002e45f  movups  [rbp+7E0h+var_854], xmm0
0x18002e463  movups  [rsp+8E0h+var_878], xmm0
0x18002e468  jnz     short loc_18002E478
0x18002e46a  cmp     qword ptr cs:xmmword_18004D648+8, r14
0x18002e471  jnz     short loc_18002E478
0x18002e473  test    rcx, rcx
0x18002e476  jz      short loc_18002E490
0x18002e478  lea     rdx, [rsp+8E0h+var_888]
0x18002e47d  mov     [rsp+8E0h+CompartmentId], ebx
0x18002e481  call    NsiGetRoutingDomainIdForCompartment
0x18002e486  mov     edi, eax
0x18002e488  test    eax, eax
0x18002e48a  jnz     loc_18002E5F5
0x18002e490  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18002e497  jz      short loc_18002E4D7
0x18002e499  test    rcx, rcx
0x18002e49c  jz      short loc_18002E4E3
0x18002e49e  lea     rax, [rsp+8E0h+var_868]
0x18002e4a3  mov     word ptr [rsp+8E0h+var_868], r14w
0x18002e4a9  mov     [rsp+8E0h+var_8B8], rax
0x18002e4ae  lea     r9, [rsp+8E0h+var_888]
0x18002e4b3  mov     rax, cs:gIphlpParamTemplateFunc
0x18002e4ba  lea     r8, aGetadapterinfo; "GetAdapterInfo"
0x18002e4c1  mov     rdx, rcx
0x18002e4c4  mov     [rsp+8E0h+var_8C0], r14
0x18002e4c9  mov     rcx, cs:gIphlpEtwContext
0x18002e4d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e4d5  jmp     short loc_18002E4E3
0x18002e4d7  lea     rcx, aGetadapterinfo_6; "GetAdapterInfo"
0x18002e4de  call    TraceHlp
0x18002e4e3  call    cs:__imp_GetCurrentThreadCompartmentId
0x18002e4ea  nop     dword ptr [rax+rax+00h]
0x18002e4ef  mov     ecx, ebx; CompartmentId
0x18002e4f1  mov     [rsp+8E0h+CompartmentId], eax
0x18002e4f5  call    cs:__imp_SetCurrentThreadCompartmentId
0x18002e4fc  nop     dword ptr [rax+rax+00h]
0x18002e501  mov     edi, eax
0x18002e503  test    eax, eax
0x18002e505  jnz     loc_18002EAC1
0x18002e50b  lea     rdx, [rsp+8E0h+SizePointer]; SizePointer
0x18002e510  mov     [rsp+8E0h+var_89C], ebx
0x18002e514  xor     ecx, ecx; AdapterInfo
0x18002e516  mov     [rsp+8E0h+SizePointer], r14d
0x18002e51b  call    cs:__imp_GetAdaptersInfo
0x18002e522  nop     dword ptr [rax+rax+00h]
0x18002e527  mov     edi, eax
0x18002e529  cmp     eax, 6Fh ; 'o'
0x18002e52c  jz      short loc_18002E560
0x18002e52e  test    eax, eax
0x18002e530  jz      short loc_18002E560
0x18002e532  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18002e539  jz      short loc_18002E554
0x18002e53b  cmp     qword ptr cs:xmmword_18004D648+8, r14
0x18002e542  jz      loc_18002E5F9
0x18002e548  lea     rdx, aGetadaptersinf; "GetAdaptersInfo failed and returned %d"
0x18002e54f  jmp     loc_18002EADE
0x18002e554  lea     rcx, aGetadaptersinf_0; "GetAdaptersInfo failed and returned %d"
0x18002e55b  jmp     loc_18002EB33
0x18002e560  mov     edx, [rsp+8E0h+SizePointer]; uBytes
0x18002e564  mov     ecx, 40h ; '@'; uFlags
0x18002e569  call    cs:__imp_LocalAlloc
0x18002e570  nop     dword ptr [rax+rax+00h]
0x18002e575  mov     r12, rax
0x18002e578  test    rax, rax
0x18002e57b  jnz     loc_18002E67D
0x18002e581  call    cs:__imp_GetLastError
0x18002e588  nop     dword ptr [rax+rax+00h]
0x18002e58d  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18002e594  mov     edi, eax
0x18002e596  jz      loc_18002E66A
0x18002e59c  cmp     qword ptr cs:xmmword_18004D648+8, r14
0x18002e5a3  jz      short loc_18002E5F5
0x18002e5a5  lea     rdx, aLocalallocFail_1; "LocalAlloc failed and returned %d"
0x18002e5ac  mov     r8d, eax
0x18002e5af  mov     word ptr [rsp+8E0h+var_868], r14w
0x18002e5b5  lea     rcx, [rbp+7E0h+var_840]
0x18002e5b9  mov     word ptr [rbp+7E0h+var_840], r14w
0x18002e5be  call    FormatRRASErrorString
0x18002e5c3  mov     rdx, qword ptr cs:xmmword_18004D648+8
0x18002e5ca  lea     rax, [rsp+8E0h+var_868]
0x18002e5cf  mov     rcx, cs:gIphlpEtwContext
0x18002e5d6  lea     r9, [rsp+8E0h+var_888]
0x18002e5db  mov     [rsp+8E0h+var_8B8], rax
0x18002e5e0  lea     r8, [rbp+7E0h+var_840]
0x18002e5e4  mov     rax, cs:gIphlpParamTemplateFunc
0x18002e5eb  mov     [rsp+8E0h+var_8C0], r14
0x18002e5f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e5f5  test    edi, edi
0x18002e5f7  jz      short loc_18002E5FC
0x18002e5f9  mov     esi, r14d
0x18002e5fc  mov     rax, [rsp+8E0h+var_890]
0x18002e601  test    rax, rax
0x18002e604  jz      short loc_18002E608
0x18002e606  mov     [rax], esi
0x18002e608  mov     rcx, r12; hMem
0x18002e60b  call    cs:__imp_LocalFree
0x18002e612  nop     dword ptr [rax+rax+00h]
0x18002e617  mov     rcx, r13; hMem
0x18002e61a  call    cs:__imp_LocalFree
0x18002e621  nop     dword ptr [rax+rax+00h]
0x18002e626  cmp     [rsp+8E0h+var_89C], r14d
0x18002e62b  jz      short loc_18002E63D
0x18002e62d  mov     ecx, [rsp+8E0h+CompartmentId]; CompartmentId
0x18002e631  call    cs:__imp_SetCurrentThreadCompartmentId
0x18002e638  nop     dword ptr [rax+rax+00h]
0x18002e63d  mov     eax, edi
0x18002e63f  mov     rcx, [rbp+7E0h+var_40]
0x18002e646  xor     rcx, rsp; StackCookie
0x18002e649  call    __security_check_cookie
0x18002e64e  mov     rbx, [rsp+8E0h+arg_8]
0x18002e656  add     rsp, 8B0h
0x18002e65d  pop     r15
0x18002e65f  pop     r14
0x18002e661  pop     r13
0x18002e663  pop     r12
0x18002e665  pop     rdi
0x18002e666  pop     rsi
0x18002e667  pop     rbp
0x18002e668  retn
0x18002e66a  lea     rcx, aLocalallocFail; "LocalAlloc failed and returned %d"
0x18002e671  mov     edx, eax
0x18002e673  call    TraceHlp
0x18002e678  jmp     loc_18002E5F5
0x18002e67d  lea     rdx, [rsp+8E0h+SizePointer]; SizePointer
0x18002e682  mov     rcx, r12; AdapterInfo
0x18002e685  call    cs:__imp_GetAdaptersInfo
0x18002e68c  nop     dword ptr [rax+rax+00h]
0x18002e691  mov     edi, eax
0x18002e693  test    eax, eax
0x18002e695  jnz     loc_18002E532
0x18002e69b  mov     rbx, r12
0x18002e69e  cmp     [rbx+1A0h], r15d
0x18002e6a5  jz      short loc_18002E710
0x18002e6a7  mov     rbx, [rbx]
0x18002e6aa  test    rbx, rbx
0x18002e6ad  jnz     short loc_18002E69E
0x18002e6af  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18002e6b6  jz      short loc_18002E6FA
0x18002e6b8  mov     rdx, qword ptr cs:xmmword_18004D648+8
0x18002e6bf  test    rdx, rdx
0x18002e6c2  jz      short loc_18002E706
0x18002e6c4  lea     r8, aCouldnTGetInfo_0; "Couldn't get info for the adapter"
0x18002e6cb  mov     rcx, cs:gIphlpEtwContext
0x18002e6d2  lea     rax, [rsp+8E0h+var_868]
0x18002e6d7  mov     [rsp+8E0h+var_8B8], rax
0x18002e6dc  lea     r9, [rsp+8E0h+var_888]
0x18002e6e1  mov     rax, cs:gIphlpParamTemplateFunc
0x18002e6e8  mov     [rsp+8E0h+var_8C0], r14
0x18002e6ed  mov     word ptr [rsp+8E0h+var_868], r14w
0x18002e6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6f8  jmp     short loc_18002E706
0x18002e6fa  lea     rcx, aCouldnTGetInfo; "Couldn't get info for the adapter"
0x18002e701  call    TraceHlp
0x18002e706  mov     edi, 490h
0x18002e70b  jmp     loc_18002E5F9
0x18002e710  lea     rcx, [rbx+1C0h]; cp
0x18002e717  mov     edi, r14d
0x18002e71a  call    cs:__imp_inet_addr
0x18002e721  nop     dword ptr [rax+rax+00h]
0x18002e726  lea     rcx, [rbx+1F0h]; cp
0x18002e72d  mov     esi, eax
0x18002e72f  call    cs:__imp_inet_addr
0x18002e736  nop     dword ptr [rax+rax+00h]
0x18002e73b  cmp     [rbx+248h], r14d
0x18002e742  jz      short loc_18002E76F
0x18002e744  lea     rcx, [rbx+258h]; cp
0x18002e74b  call    cs:__imp_inet_addr
0x18002e752  nop     dword ptr [rax+rax+00h]
0x18002e757  lea     rcx, [rbx+288h]; cp
0x18002e75e  mov     edi, eax
0x18002e760  call    cs:__imp_inet_addr
0x18002e767  nop     dword ptr [rax+rax+00h]
0x18002e76c  mov     r14d, eax
0x18002e76f  mov     ecx, 7F000001h; hostlong
0x18002e774  call    cs:__imp_htonl
0x18002e77b  nop     dword ptr [rax+rax+00h]
0x18002e780  cmp     edi, eax
0x18002e782  jnz     short loc_18002E7F5
0x18002e784  xor     ebx, ebx
0x18002e786  cmp     cs:gIsIphlpEtwTracingAvailable, ebx
0x18002e78c  jz      short loc_18002E7E7
0x18002e78e  cmp     cs:qword_18004D658, rbx
0x18002e795  jz      short loc_18002E7F5
0x18002e797  mov     r8d, esi
0x18002e79a  mov     word ptr [rbp+7E0h+var_840], bx
0x18002e79e  lea     rdx, aGetadapterinfo_7; "GetAdapterInfo: replacing WINS1 with 0x"...
0x18002e7a5  mov     word ptr [rsp+8E0h+var_868], bx
0x18002e7aa  lea     rcx, [rbp+7E0h+var_840]
0x18002e7ae  call    FormatRRASErrorString
0x18002e7b3  mov     rdx, cs:qword_18004D658
0x18002e7ba  lea     rax, [rsp+8E0h+var_868]
0x18002e7bf  mov     rcx, cs:gIphlpEtwContext
0x18002e7c6  lea     r9, [rsp+8E0h+var_888]
0x18002e7cb  mov     [rsp+8E0h+var_8B8], rax
0x18002e7d0  lea     r8, [rbp+7E0h+var_840]
0x18002e7d4  mov     rax, cs:gIphlpParamTemplateFunc
0x18002e7db  mov     [rsp+8E0h+var_8C0], rbx
0x18002e7e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e7e5  jmp     short loc_18002E7F5
0x18002e7e7  mov     edx, esi
0x18002e7e9  lea     rcx, aGetadapterinfo_5; "GetAdapterInfo: replacing WINS1 with 0x"...
0x18002e7f0  call    TraceHlp
0x18002e7f5  mov     ecx, 7F000001h; hostlong
0x18002e7fa  call    cs:__imp_htonl
0x18002e801  nop     dword ptr [rax+rax+00h]
0x18002e806  cmp     r14d, eax
0x18002e809  jnz     short loc_18002E882
0x18002e80b  xor     r14d, r14d
0x18002e80e  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18002e815  jz      short loc_18002E872
0x18002e817  cmp     qword ptr cs:xmmword_18004D648+8, r14
0x18002e81e  jz      short loc_18002E885
0x18002e820  mov     r8d, esi
0x18002e823  mov     word ptr [rbp+7E0h+var_840], r14w
0x18002e828  lea     rdx, aGetadapterinfo_8; "GetAdapterInfo: replacing WINS2 with 0x"...
0x18002e82f  mov     word ptr [rsp+8E0h+var_868], r14w
0x18002e835  lea     rcx, [rbp+7E0h+var_840]
0x18002e839  call    FormatRRASErrorString
0x18002e83e  mov     rdx, qword ptr cs:xmmword_18004D648+8
0x18002e845  lea     rax, [rsp+8E0h+var_868]
0x18002e84a  mov     rcx, cs:gIphlpEtwContext
0x18002e851  lea     r9, [rsp+8E0h+var_888]
0x18002e856  mov     [rsp+8E0h+var_8B8], rax
0x18002e85b  lea     r8, [rbp+7E0h+var_840]
0x18002e85f  mov     rax, cs:gIphlpParamTemplateFunc
0x18002e866  mov     [rsp+8E0h+var_8C0], r14
0x18002e86b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e870  jmp     short loc_18002E885
0x18002e872  mov     edx, esi
0x18002e874  lea     rcx, aGetadapterinfo_4; "GetAdapterInfo: replacing WINS2 with 0x"...
0x18002e87b  call    TraceHlp
0x18002e880  jmp     short loc_18002E885
0x18002e882  xor     r14d, r14d
0x18002e885  lea     r8, [rsp+8E0h+SizePointer]; pOutBufLen
0x18002e88a  mov     [rsp+8E0h+SizePointer], r14d
0x18002e88f  xor     edx, edx; pPerAdapterInfo
0x18002e891  mov     ecx, r15d; IfIndex
0x18002e894  call    cs:__imp_GetPerAdapterInfo
0x18002e89b  nop     dword ptr [rax+rax+00h]
0x18002e8a0  mov     edi, eax
0x18002e8a2  cmp     eax, 6Fh ; 'o'
0x18002e8a5  jz      short loc_18002E8D5
0x18002e8a7  cmp     cs:gIsIphlpEtwTracingAvailable, r14d
0x18002e8ae  jz      short loc_18002E8C9
0x18002e8b0  cmp     qword ptr cs:xmmword_18004D648+8, r14
0x18002e8b7  jz      loc_18002E5F5
0x18002e8bd  lea     rdx, aGetperadapteri_0; "GetPerAdapterInfo failed and returned %"...
0x18002e8c4  jmp     loc_18002E5AC
0x18002e8c9  lea     rcx, aGetperadapteri; "GetPerAdapterInfo failed and returned %"...
0x18002e8d0  jmp     loc_18002E671
0x18002e8d5  mov     edx, [rsp+8E0h+SizePointer]; uBytes
0x18002e8d9  mov     ecx, 40h ; '@'; uFlags
0x18002e8de  call    cs:__imp_LocalAlloc
0x18002e8e5  nop     dword ptr [rax+rax+00h]
0x18002e8ea  mov     r13, rax
0x18002e8ed  test    rax, rax
0x18002e8f0  jz      loc_18002E581
0x18002e8f6  lea     r8, [rsp+8E0h+SizePointer]; pOutBufLen
0x18002e8fb  mov     rdx, rax; pPerAdapterInfo
0x18002e8fe  mov     ecx, r15d; IfIndex
0x18002e901  call    cs:__imp_GetPerAdapterInfo
0x18002e908  nop     dword ptr [rax+rax+00h]
0x18002e90d  mov     edi, eax
0x18002e90f  test    eax, eax
  ... truncated ...
```
