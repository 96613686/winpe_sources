# IpTlsServerProcessDadPacketOrNeighborAdvertisement

- ea: `0x180049bc8`
- end: `0x18004a1fb`
- name: `IpTlsServerProcessDadPacketOrNeighborAdvertisement`
- size: `1587`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180049a70`

## callees

- `0x180004c54`
- `0x18000d7b0`
- `0x180030d24`
- `0x180047b38`
- `0x180049bc8`
- `0x18004a204`
- `0x18004a418`
- `0x18004b630`
- `0x18004c1c8`
- `0x180061694`
- `0x18006398c`
- `0x1800646b8`
- `0x180065074`
- `0x180066158`
- `0x1800663d8`
- `0x1800671a8`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringW` at `0x180049d98`
- `ntdll!RtlIpv6AddressToStringW` at `0x180049e51`
- `ntdll!RtlIpv6AddressToStringW` at `0x180049f29`
- `ntdll!RtlIpv6AddressToStringW` at `0x180049fa7`
- `ntdll!RtlIpv6AddressToStringW` at `0x180049d98`
- `ntdll!RtlIpv6AddressToStringW` at `0x180049e51`
- `ntdll!RtlIpv6AddressToStringW` at `0x180049f29`
- `ntdll!RtlIpv6AddressToStringW` at `0x180049fa7`
- `ntdll!RtlRemoveEntryHashTable` at `0x180049ecd`
- `ntdll!RtlRemoveEntryHashTable` at `0x180049f70`
- `ntdll!RtlRemoveEntryHashTable` at `0x180049ecd`
- `ntdll!RtlRemoveEntryHashTable` at `0x180049f70`
- `ntdll!RtlInsertEntryHashTable` at `0x180049eeb`
- `ntdll!RtlInsertEntryHashTable` at `0x180049f91`
- `ntdll!RtlInsertEntryHashTable` at `0x180049eeb`
- `ntdll!RtlInsertEntryHashTable` at `0x180049f91`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049c37`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049c37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a186`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a186`

## string_xrefs

- `0x180049fbc`: `%s: IpTlsServerProcessDadPacketOrNeighborAdvertisement: failed to move %s to conflict, discarding existing mapping`
- `0x180049c77`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180049ccd`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180049cf0`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180049d47`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004a062`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004a09e`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004a0ee`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004a10c`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004a1ad`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

## pseudocode

```c
char __fastcall IpTlsServerProcessDadPacketOrNeighborAdvertisement(
        struct _RTL_CRITICAL_SECTION *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        char a6)
{
  __int64 v6; // rsi
  __int64 v10; // r13
  __int64 v11; // r15
  __int64 v12; // rsi
  int ClientAddressState; // eax
  __int64 v14; // r8
  __int64 v15; // r14
  int v16; // edi
  __int64 v17; // r9
  int v18; // ecx
  _QWORD *v19; // rbx
  __int64 v20; // r9
  int v21; // ecx
  __int64 v22; // rdx
  _QWORD *v23; // rax
  __int64 v24; // rdx
  _QWORD *v25; // rcx
  _QWORD *v26; // rcx
  __int64 v27; // rdx
  _QWORD *v28; // rcx
  __int64 v29; // rsi
  __int64 v30; // rdi
  __int64 v31; // rbx
  char v32; // al
  const struct in6_addr *v33; // rcx
  __int64 v34; // rsi
  __int64 v35; // rdi
  __int64 v36; // rbx
  __int64 v37; // rdx
  _QWORD *v38; // rax
  __int64 v39; // rdi
  int v40; // esi
  int v41; // r14d
  char v42; // bl
  int v43; // ecx
  int v44; // ecx
  __int64 v45; // rax
  __int64 v46; // rbx
  __int64 v48; // [rsp+20h] [rbp-E0h]
  __int64 v49; // [rsp+28h] [rbp-D8h]
  char v50; // [rsp+40h] [rbp-C0h]
  char v51; // [rsp+41h] [rbp-BFh]
  int v52; // [rsp+44h] [rbp-BCh]
  __int64 v55; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v56; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+68h] [rbp-98h]
  __int64 v58; // [rsp+70h] [rbp-90h]
  WCHAR S[72]; // [rsp+80h] [rbp-80h] BYREF

  v6 = a4;
  v57 = a3;
  v55 = 0;
  v56 = 0;
  v50 = 0;
  v10 = 0;
  v11 = 0;
  memset_0(S, 0, 0x82u);
  EnterCriticalSection(a1 + 6);
  v12 = v6 + a3 + 200;
  v58 = v12;
  ClientAddressState = IpTlsGetClientAddressState((_DWORD)a1, a2, v12, (unsigned int)&v55, (__int64)&v56);
  v15 = v55;
  v52 = ClientAddressState;
  v16 = ClientAddressState;
  if ( v55 )
  {
    v17 = *(_QWORD *)(v55 + 40);
    if ( v17 )
    {
      EventWrite0(
        0x20000000,
        L"(%s: Reference client context (%p)%S:%d",
        *(_QWORD *)(*(_QWORD *)(v17 + 40) + 288LL) + 56LL);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
        McTemplateU0psq_EventWriteTransfer(
          v18,
          (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE,
          *(_QWORD *)(v15 + 40),
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
          108);
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v15 + 40) + 56LL));
      v10 = *(_QWORD *)(v15 + 40);
    }
  }
  v19 = v56;
  if ( v56 )
  {
    v20 = v56[5];
    if ( v20 )
    {
      EventWrite0(
        0x20000000,
        L"(%s: Reference client context (%p)%S:%d",
        *(_QWORD *)(*(_QWORD *)(v20 + 40) + 288LL) + 56LL);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
        McTemplateU0psq_EventWriteTransfer(
          v21,
          (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE,
          v19[5],
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
          113);
      _InterlockedIncrement((volatile signed __int32 *)(v19[5] + 56LL));
      v11 = v19[5];
    }
  }
  if ( v16 )
  {
    if ( v16 == 2 )
    {
      if ( !*(_QWORD *)(v15 + 40) )
        goto LABEL_37;
      LOBYTE(v14) = 1;
      v32 = AddClientAddressMapping(a2, v12, v14);
      v33 = (const struct in6_addr *)(v15 + 24);
      if ( v32 )
      {
        RtlIpv6AddressToStringW(v33, S);
        EventWrite0(
          0x10000000,
          L"%s: IpTlsServerProcessDadPacketOrNeighborAdvertisement: entering conflict for address %s",
          *(_QWORD *)(*(_QWORD *)(a2 + 40) + 288LL) + 56LL,
          S);
        v34 = *(_QWORD *)(v15 + 40);
        v35 = *(_QWORD *)(v15 + 16);
        v36 = *(_QWORD *)(v34 + 40);
        RtlRemoveEntryHashTable(v36 + 104, v15, 0);
        RtlInsertEntryHashTable(v36 + 184, v15, v35 | 0x40000000, 0);
        IpTlsUpdatePerfCountersForClient(v34);
        goto LABEL_37;
      }
      RtlIpv6AddressToStringW(v33, S);
      EventWrite0(
        0x10000000,
        L"%s: IpTlsServerProcessDadPacketOrNeighborAdvertisement: failed to move %s to conflict, discarding existing mapping",
        *(_QWORD *)(*(_QWORD *)(a2 + 40) + 288LL) + 56LL,
        S);
      v37 = *(_QWORD *)(v15 + 48);
      if ( *(_QWORD *)(v37 + 8) == v15 + 48 )
      {
        v38 = *(_QWORD **)(v15 + 56);
        if ( *v38 == v15 + 48 )
        {
          *v38 = v37;
          v26 = (_QWORD *)v15;
          *(_QWORD *)(v37 + 8) = v38;
          goto LABEL_33;
        }
      }
LABEL_34:
      __fastfail(3u);
    }
    if ( v16 != 3 )
    {
      if ( v16 != 4 )
        goto LABEL_37;
      RtlIpv6AddressToStringW((const struct in6_addr *)(v15 + 24), S);
      EventWrite0(
        0x10000000,
        L"%s: IpTlsServerProcessDadPacketOrNeighborAdvertisement: received DAD/NA for %s from conflict non-owner",
        *(_QWORD *)(*(_QWORD *)(a2 + 40) + 288LL) + 56LL,
        S);
      v22 = *(_QWORD *)(v15 + 48);
      if ( *(_QWORD *)(v22 + 8) == v15 + 48 )
      {
        v23 = *(_QWORD **)(v15 + 56);
        if ( *v23 == v15 + 48 )
        {
          *v23 = v22;
          *(_QWORD *)(v22 + 8) = v23;
          *(_BYTE *)(*(_QWORD *)(v15 + 40) + 32LL) = 1;
          RemoveClientAddressMapping(v15);
          if ( !v19 )
            goto LABEL_37;
          v24 = v19[6];
          if ( *(_QWORD **)(v24 + 8) == v19 + 6 )
          {
            v25 = (_QWORD *)v19[7];
            if ( (_QWORD *)*v25 == v19 + 6 )
            {
              *v25 = v24;
              *(_QWORD *)(v24 + 8) = v25;
              v26 = v19;
              *(_BYTE *)(v19[5] + 32LL) = 1;
LABEL_33:
              RemoveClientAddressMapping(v26);
              goto LABEL_37;
            }
          }
        }
      }
      goto LABEL_34;
    }
    if ( a6 )
      goto LABEL_37;
    RtlIpv6AddressToStringW((const struct in6_addr *)(v15 + 24), S);
    EventWrite0(
      0x10000000,
      L"%s: IpTlsServerProcessDadPacketOrNeighborAdvertisement: received NA for %s from conflict owner",
      *(_QWORD *)(*(_QWORD *)(a2 + 40) + 288LL) + 56LL,
      S);
    if ( v19 )
    {
      v27 = v19[6];
      if ( *(_QWORD **)(v27 + 8) != v19 + 6 )
        goto LABEL_34;
      v28 = (_QWORD *)v19[7];
      if ( (_QWORD *)*v28 != v19 + 6 )
        goto LABEL_34;
      *v28 = v27;
      *(_QWORD *)(v27 + 8) = v28;
      RemoveClientAddressMapping(v19);
    }
    v29 = *(_QWORD *)(v15 + 40);
    v30 = *(_QWORD *)(v15 + 16);
    v31 = *(_QWORD *)(v29 + 40);
    RtlRemoveEntryHashTable(v31 + 184, v15, 0);
    RtlInsertEntryHashTable(v31 + 104, v15, v30 & 0xFFFFFFFFBFFFFFFFuLL, 0);
    IpTlsUpdatePerfCountersForClient(v29);
  }
  else
  {
    AddClientAddressMapping(a2, v12, 0);
  }
  v50 = 1;
LABEL_37:
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v51 = IpTlsServerForwardDadOrNAPacket((_DWORD)a1, a2, v57, a4, a5, v52, v10, v11);
  v42 = v51;
  if ( v10 )
  {
    LODWORD(v49) = 3825;
    EventWrite0(
      0x20000000,
      L"(%s: Dereference client context (%p) %S:%d",
      *(_QWORD *)(*(_QWORD *)(v10 + 40) + 288LL) + 56LL,
      v10,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      v49);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v43,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE,
        v10,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        241);
    DereferenceClientContextEx(v10);
  }
  if ( v11 )
  {
    LODWORD(v49) = 3829;
    EventWrite0(
      0x20000000,
      L"(%s: Dereference client context (%p) %S:%d",
      *(_QWORD *)(*(_QWORD *)(v11 + 40) + 288LL) + 56LL,
      v11,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      v49);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v44,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE,
        v11,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        245);
    DereferenceClientContextEx(v11);
  }
  if ( v50 )
  {
    v45 = IpTlsServerLookupNDEntry(a1, v58);
    v46 = v45;
    if ( v45 )
    {
      v39 = *(_QWORD *)(v45 + 56);
      v40 = *(_DWORD *)(v45 + 64);
      v41 = *(_DWORD *)(v45 + 68);
      *(_QWORD *)(v45 + 56) = 0;
      if ( *(_BYTE *)(v45 + 74) )
      {
        IpTlsServerRemoveNDEntry(a1, v45);
        FREE(v46);
      }
    }
    v42 = v51;
  }
  LeaveCriticalSection(a1 + 6);
  if ( v39 )
  {
    SendBufferOnContext((_DWORD)a1, a2, v39, v40, v41);
    LODWORD(v48) = 3873;
    EventWrite0(
      0x20000000,
      L"(Dereference IPTLS Buffer(%p)%S:%d",
      v39,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      v48);
    IpTlsDereferenceBufferEx(v39);
  }
  return v42;
}

```

## disassembly

```asm
0x180049bc8  push    rbp
0x180049bca  push    rbx
0x180049bcb  push    rsi
0x180049bcc  push    rdi
0x180049bcd  push    r12
0x180049bcf  push    r13
0x180049bd1  push    r14
0x180049bd3  push    r15
0x180049bd5  lea     rbp, [rsp-28h]
0x180049bda  sub     rsp, 128h
0x180049be1  mov     rax, cs:__security_cookie
0x180049be8  xor     rax, rsp
0x180049beb  mov     [rbp+60h+var_50], rax
0x180049bef  xor     eax, eax
0x180049bf1  movsxd  rsi, r9d
0x180049bf4  mov     rdi, r8
0x180049bf7  mov     [rsp+160h+var_F8], r8
0x180049bfc  mov     r12, rdx
0x180049bff  mov     [rsp+160h+var_110], rcx
0x180049c04  mov     rbx, rcx
0x180049c07  mov     [rsp+160h+var_118], esi
0x180049c0b  xor     edx, edx; Val
0x180049c0d  mov     [rsp+160h+var_108], rax
0x180049c12  mov     r8d, 82h; Size
0x180049c18  mov     [rsp+160h+var_100], rax
0x180049c1d  lea     rcx, [rbp+60h+S]; void *
0x180049c21  mov     [rsp+160h+var_120], al
0x180049c25  mov     r13d, eax
0x180049c28  mov     r15d, eax
0x180049c2b  call    memset_0
0x180049c30  lea     rcx, [rbx+0F0h]; lpCriticalSection
0x180049c37  call    cs:__imp_EnterCriticalSection
0x180049c3e  nop     dword ptr [rax+rax+00h]
0x180049c43  mov     rax, rsi
0x180049c46  lea     r9, [rsp+160h+var_108]
0x180049c4b  lea     rsi, [rdi+0C8h]
0x180049c52  mov     rdx, r12
0x180049c55  add     rsi, rax
0x180049c58  mov     rcx, rbx
0x180049c5b  lea     rax, [rsp+160h+var_100]
0x180049c60  mov     [rsp+160h+var_F0], rsi
0x180049c65  mov     r8, rsi
0x180049c68  mov     [rsp+160h+var_140], rax
0x180049c6d  call    IpTlsGetClientAddressState
0x180049c72  mov     r14, [rsp+160h+var_108]
0x180049c77  lea     rcx, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180049c7e  mov     [rsp+160h+var_11C], eax
0x180049c82  mov     edi, eax
0x180049c84  test    r14, r14
0x180049c87  jz      short loc_180049CF7
0x180049c89  mov     r9, [r14+28h]
0x180049c8d  test    r9, r9
0x180049c90  jz      short loc_180049CF7
0x180049c92  mov     rax, [r9+28h]
0x180049c96  lea     rdx, aSReferenceClie; "(%s: Reference client context (%p)%S:%d"
0x180049c9d  mov     ebx, 0E6Ch
0x180049ca2  mov     dword ptr [rsp+160h+var_138], ebx
0x180049ca6  mov     [rsp+160h+var_140], rcx
0x180049cab  mov     ecx, 20000000h
0x180049cb0  mov     r8, [rax+120h]
0x180049cb7  add     r8, 38h ; '8'
0x180049cbb  call    EventWrite0
0x180049cc0  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180049cc7  jz      short loc_180049CE4
0x180049cc9  mov     r8, [r14+28h]
0x180049ccd  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180049cd4  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE
0x180049cdb  mov     dword ptr [rsp+160h+var_140], ebx
0x180049cdf  call    McTemplateU0psq_EventWriteTransfer
0x180049ce4  mov     rax, [r14+28h]
0x180049ce8  lock inc dword ptr [rax+38h]
0x180049cec  mov     r13, [r14+28h]
0x180049cf0  lea     rcx, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180049cf7  mov     rbx, [rsp+160h+var_100]
0x180049cfc  test    rbx, rbx
0x180049cff  jz      short loc_180049D6B
0x180049d01  mov     r9, [rbx+28h]
0x180049d05  test    r9, r9
0x180049d08  jz      short loc_180049D6B
0x180049d0a  mov     rax, [r9+28h]
0x180049d0e  lea     rdx, aSReferenceClie; "(%s: Reference client context (%p)%S:%d"
0x180049d15  mov     r15d, 0E71h
0x180049d1b  mov     dword ptr [rsp+160h+var_138], r15d
0x180049d20  mov     [rsp+160h+var_140], rcx
0x180049d25  mov     ecx, 20000000h
0x180049d2a  mov     r8, [rax+120h]
0x180049d31  add     r8, 38h ; '8'
0x180049d35  call    EventWrite0
0x180049d3a  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180049d41  jz      short loc_180049D5F
0x180049d43  mov     r8, [rbx+28h]
0x180049d47  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180049d4e  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE
0x180049d55  mov     dword ptr [rsp+160h+var_140], r15d
0x180049d5a  call    McTemplateU0psq_EventWriteTransfer
0x180049d5f  mov     rax, [rbx+28h]
0x180049d63  lock inc dword ptr [rax+38h]
0x180049d67  mov     r15, [rbx+28h]
0x180049d6b  mov     ecx, edi
0x180049d6d  test    edi, edi
0x180049d6f  jz      loc_18004A006
0x180049d75  sub     ecx, 2
0x180049d78  jz      loc_180049F04
0x180049d7e  sub     ecx, 1
0x180049d81  jz      loc_180049E3C
0x180049d87  cmp     ecx, 1
0x180049d8a  jnz     loc_18004A019
0x180049d90  lea     rcx, [r14+18h]; Addr
0x180049d94  lea     rdx, [rbp+60h+S]; S
0x180049d98  call    cs:__imp_RtlIpv6AddressToStringW
0x180049d9f  nop     dword ptr [rax+rax+00h]
0x180049da4  mov     rax, [r12+28h]
0x180049da9  lea     r9, [rbp+60h+S]
0x180049dad  lea     rdx, aSIptlsserverpr_2; "%s: IpTlsServerProcessDadPacketOrNeighb"...
0x180049db4  mov     ecx, 10000000h
0x180049db9  mov     r8, [rax+120h]
0x180049dc0  add     r8, 38h ; '8'
0x180049dc4  call    EventWrite0
0x180049dc9  lea     rcx, [r14+30h]
0x180049dcd  mov     rdx, [rcx]
0x180049dd0  cmp     [rdx+8], rcx
0x180049dd4  jnz     loc_180049FFF
0x180049dda  mov     rax, [rcx+8]
0x180049dde  cmp     [rax], rcx
0x180049de1  jnz     loc_180049FFF
0x180049de7  mov     [rax], rdx
0x180049dea  mov     rcx, r14
0x180049ded  mov     [rdx+8], rax
0x180049df1  mov     rax, [r14+28h]
0x180049df5  mov     byte ptr [rax+20h], 1
0x180049df9  call    RemoveClientAddressMapping
0x180049dfe  test    rbx, rbx
0x180049e01  jz      loc_18004A019
0x180049e07  lea     rax, [rbx+30h]
0x180049e0b  mov     rdx, [rax]
0x180049e0e  cmp     [rdx+8], rax
0x180049e12  jnz     loc_180049FFF
0x180049e18  mov     rcx, [rax+8]
0x180049e1c  cmp     [rcx], rax
0x180049e1f  jnz     loc_180049FFF
0x180049e25  mov     [rcx], rdx
0x180049e28  mov     [rdx+8], rcx
0x180049e2c  mov     rcx, rbx
0x180049e2f  mov     rax, [rbx+28h]
0x180049e33  mov     byte ptr [rax+20h], 1
0x180049e37  jmp     loc_180049FF8
0x180049e3c  cmp     [rbp+60h+arg_28], 0
0x180049e43  jnz     loc_18004A019
0x180049e49  lea     rcx, [r14+18h]; Addr
0x180049e4d  lea     rdx, [rbp+60h+S]; S
0x180049e51  call    cs:__imp_RtlIpv6AddressToStringW
0x180049e58  nop     dword ptr [rax+rax+00h]
0x180049e5d  mov     rax, [r12+28h]
0x180049e62  lea     r9, [rbp+60h+S]
0x180049e66  lea     rdx, aSIptlsserverpr_1; "%s: IpTlsServerProcessDadPacketOrNeighb"...
0x180049e6d  mov     ecx, 10000000h
0x180049e72  mov     r8, [rax+120h]
0x180049e79  add     r8, 38h ; '8'
0x180049e7d  call    EventWrite0
0x180049e82  test    rbx, rbx
0x180049e85  jz      short loc_180049EB4
0x180049e87  lea     rax, [rbx+30h]
0x180049e8b  mov     rdx, [rax]
0x180049e8e  cmp     [rdx+8], rax
0x180049e92  jnz     loc_180049FFF
0x180049e98  mov     rcx, [rax+8]
0x180049e9c  cmp     [rcx], rax
0x180049e9f  jnz     loc_180049FFF
0x180049ea5  mov     [rcx], rdx
0x180049ea8  mov     [rdx+8], rcx
0x180049eac  mov     rcx, rbx
0x180049eaf  call    RemoveClientAddressMapping
0x180049eb4  mov     rsi, [r14+28h]
0x180049eb8  xor     r8d, r8d
0x180049ebb  mov     rdi, [r14+10h]
0x180049ebf  mov     rdx, r14
0x180049ec2  mov     rbx, [rsi+28h]
0x180049ec6  lea     rcx, [rbx+0B8h]
0x180049ecd  call    cs:__imp_RtlRemoveEntryHashTable
0x180049ed4  nop     dword ptr [rax+rax+00h]
0x180049ed9  btr     rdi, 1Eh
0x180049ede  lea     rcx, [rbx+68h]
0x180049ee2  mov     r8, rdi
0x180049ee5  xor     r9d, r9d
0x180049ee8  mov     rdx, r14
0x180049eeb  call    cs:__imp_RtlInsertEntryHashTable
0x180049ef2  nop     dword ptr [rax+rax+00h]
0x180049ef7  mov     rcx, rsi
0x180049efa  call    IpTlsUpdatePerfCountersForClient
0x180049eff  jmp     loc_18004A014
0x180049f04  cmp     qword ptr [r14+28h], 0
0x180049f09  jz      loc_18004A019
0x180049f0f  mov     r8b, 1
0x180049f12  mov     rdx, rsi
0x180049f15  mov     rcx, r12
0x180049f18  call    AddClientAddressMapping
0x180049f1d  lea     rcx, [r14+18h]; Addr
0x180049f21  lea     rdx, [rbp+60h+S]; S
0x180049f25  test    al, al
0x180049f27  jz      short loc_180049FA7
0x180049f29  call    cs:__imp_RtlIpv6AddressToStringW
0x180049f30  nop     dword ptr [rax+rax+00h]
0x180049f35  mov     rax, [r12+28h]
0x180049f3a  lea     r9, [rbp+60h+S]
0x180049f3e  lea     rdx, aSIptlsserverpr_0; "%s: IpTlsServerProcessDadPacketOrNeighb"...
0x180049f45  mov     ecx, 10000000h
0x180049f4a  mov     r8, [rax+120h]
0x180049f51  add     r8, 38h ; '8'
0x180049f55  call    EventWrite0
0x180049f5a  mov     rsi, [r14+28h]
0x180049f5e  xor     r8d, r8d
0x180049f61  mov     rdi, [r14+10h]
0x180049f65  mov     rdx, r14
0x180049f68  mov     rbx, [rsi+28h]
0x180049f6c  lea     rcx, [rbx+68h]
0x180049f70  call    cs:__imp_RtlRemoveEntryHashTable
0x180049f77  nop     dword ptr [rax+rax+00h]
0x180049f7c  bts     rdi, 1Eh
0x180049f81  lea     rcx, [rbx+0B8h]
0x180049f88  mov     r8, rdi
0x180049f8b  xor     r9d, r9d
0x180049f8e  mov     rdx, r14
0x180049f91  call    cs:__imp_RtlInsertEntryHashTable
0x180049f98  nop     dword ptr [rax+rax+00h]
0x180049f9d  mov     rcx, rsi
0x180049fa0  call    IpTlsUpdatePerfCountersForClient
0x180049fa5  jmp     short loc_18004A019
0x180049fa7  call    cs:__imp_RtlIpv6AddressToStringW
0x180049fae  nop     dword ptr [rax+rax+00h]
0x180049fb3  mov     rax, [r12+28h]
0x180049fb8  lea     r9, [rbp+60h+S]
0x180049fbc  lea     rdx, aSIptlsserverpr; "%s: IpTlsServerProcessDadPacketOrNeighb"...
0x180049fc3  mov     ecx, 10000000h
0x180049fc8  mov     r8, [rax+120h]
0x180049fcf  add     r8, 38h ; '8'
0x180049fd3  call    EventWrite0
0x180049fd8  lea     rcx, [r14+30h]
0x180049fdc  mov     rdx, [rcx]
0x180049fdf  cmp     [rdx+8], rcx
0x180049fe3  jnz     short loc_180049FFF
0x180049fe5  mov     rax, [rcx+8]
0x180049fe9  cmp     [rax], rcx
0x180049fec  jnz     short loc_180049FFF
0x180049fee  mov     [rax], rdx
0x180049ff1  mov     rcx, r14
0x180049ff4  mov     [rdx+8], rax
0x180049ff8  call    RemoveClientAddressMapping
0x180049ffd  jmp     short loc_18004A019
0x180049fff  mov     ecx, 3
0x18004a004  int     29h; Win8: RtlFailFast(ecx)
0x18004a006  xor     r8d, r8d
0x18004a009  mov     rdx, rsi
0x18004a00c  mov     rcx, r12
0x18004a00f  call    AddClientAddressMapping
0x18004a014  mov     [rsp+160h+var_120], 1
0x18004a019  mov     eax, [rsp+160h+var_11C]
0x18004a01d  mov     rdx, r12
0x18004a020  mov     r9d, [rsp+160h+var_118]
0x18004a025  xor     edi, edi
0x18004a027  mov     r8, [rsp+160h+var_F8]
0x18004a02c  xor     esi, esi
0x18004a02e  mov     rcx, [rsp+160h+var_110]
0x18004a033  xor     r14d, r14d
0x18004a036  mov     [rsp+160h+var_128], r15
0x18004a03b  mov     [rsp+160h+var_130], r13
0x18004a040  mov     dword ptr [rsp+160h+var_138], eax
0x18004a044  mov     eax, [rbp+60h+arg_20]
0x18004a04a  mov     dword ptr [rsp+160h+var_140], eax
0x18004a04e  call    IpTlsServerForwardDadOrNAPacket
0x18004a053  mov     [rsp+160h+var_11F], al
0x18004a057  mov     bl, al
0x18004a059  test    r13, r13
0x18004a05c  jz      short loc_18004A0C4
0x18004a05e  mov     rcx, [r13+28h]
0x18004a062  lea     rax, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18004a069  mov     dword ptr [rsp+160h+var_138], 0EF1h
0x18004a071  lea     rdx, aSDereferenceCl; "(%s: Dereference client context (%p) %S"...
0x18004a078  mov     r9, r13
0x18004a07b  mov     [rsp+160h+var_140], rax
0x18004a080  mov     r8, [rcx+120h]
0x18004a087  mov     ecx, 20000000h
0x18004a08c  add     r8, 38h ; '8'
0x18004a090  call    EventWrite0
0x18004a095  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18004a09c  jz      short loc_18004A0BC
0x18004a09e  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18004a0a5  mov     dword ptr [rsp+160h+var_140], 0EF1h
0x18004a0ad  mov     r8, r13
0x18004a0b0  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE
0x18004a0b7  call    McTemplateU0psq_EventWriteTransfer
0x18004a0bc  mov     rcx, r13
0x18004a0bf  call    DereferenceClientContextEx
0x18004a0c4  xor     r13d, r13d
0x18004a0c7  test    r15, r15
0x18004a0ca  jz      short loc_18004A132
0x18004a0cc  mov     rax, [r15+28h]
0x18004a0d0  lea     rdx, aSDereferenceCl; "(%s: Dereference client context (%p) %S"...
0x18004a0d7  mov     dword ptr [rsp+160h+var_138], 0EF5h
0x18004a0df  mov     r9, r15
0x18004a0e2  mov     ecx, 20000000h
  ... truncated ...
```
