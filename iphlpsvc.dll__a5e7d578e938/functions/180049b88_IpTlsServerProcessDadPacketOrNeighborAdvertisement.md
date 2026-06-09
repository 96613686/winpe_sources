# IpTlsServerProcessDadPacketOrNeighborAdvertisement

- ea: `0x180049b88`
- end: `0x18004a1bb`
- name: `IpTlsServerProcessDadPacketOrNeighborAdvertisement`
- size: `1587`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180049a30`

## callees

- `0x180004c64`
- `0x18000d7c0`
- `0x180030d34`
- `0x180047af8`
- `0x180049b88`
- `0x18004a1c4`
- `0x18004a3d8`
- `0x18004b5f0`
- `0x18004c188`
- `0x1800616b4`
- `0x1800639ac`
- `0x1800646d8`
- `0x180065094`
- `0x180066178`
- `0x1800663f8`
- `0x1800671c8`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringW` at `0x180049d58`
- `ntdll!RtlIpv6AddressToStringW` at `0x180049e11`
- `ntdll!RtlIpv6AddressToStringW` at `0x180049ee9`
- `ntdll!RtlIpv6AddressToStringW` at `0x180049f67`
- `ntdll!RtlIpv6AddressToStringW` at `0x180049d58`
- `ntdll!RtlIpv6AddressToStringW` at `0x180049e11`
- `ntdll!RtlIpv6AddressToStringW` at `0x180049ee9`
- `ntdll!RtlIpv6AddressToStringW` at `0x180049f67`
- `ntdll!RtlRemoveEntryHashTable` at `0x180049e8d`
- `ntdll!RtlRemoveEntryHashTable` at `0x180049f30`
- `ntdll!RtlRemoveEntryHashTable` at `0x180049e8d`
- `ntdll!RtlRemoveEntryHashTable` at `0x180049f30`
- `ntdll!RtlInsertEntryHashTable` at `0x180049eab`
- `ntdll!RtlInsertEntryHashTable` at `0x180049f51`
- `ntdll!RtlInsertEntryHashTable` at `0x180049eab`
- `ntdll!RtlInsertEntryHashTable` at `0x180049f51`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049bf7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180049bf7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a146`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004a146`

## string_xrefs

- `0x180049f7c`: `%s: IpTlsServerProcessDadPacketOrNeighborAdvertisement: failed to move %s to conflict, discarding existing mapping`
- `0x180049c37`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180049c8d`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180049cb0`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x180049d07`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004a022`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004a05e`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004a0ae`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004a0cc`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`
- `0x18004a16d`: `onecoreuap\net\netio\iphlpsvc\service\iptlsserver.c`

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
  const struct in6_addr *v12; // rsi
  int ClientAddressState; // eax
  __int64 v14; // r14
  int v15; // edi
  __int64 v16; // r9
  int v17; // ecx
  _QWORD *v18; // rbx
  __int64 v19; // r9
  int v20; // ecx
  __int64 v21; // rdx
  _QWORD *v22; // rax
  __int64 v23; // rdx
  _QWORD *v24; // rcx
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  _QWORD *v27; // rcx
  __int64 v28; // rsi
  __int64 v29; // rdi
  __int64 v30; // rbx
  char v31; // al
  const struct in6_addr *v32; // rcx
  __int64 v33; // rsi
  __int64 v34; // rdi
  __int64 v35; // rbx
  __int64 v36; // rdx
  _QWORD *v37; // rax
  __int64 v38; // rdi
  int v39; // esi
  int v40; // r14d
  char v41; // bl
  int v42; // ecx
  int v43; // ecx
  __int64 v44; // rax
  __int64 v45; // rbx
  __int64 v47; // [rsp+20h] [rbp-E0h]
  __int64 v48; // [rsp+28h] [rbp-D8h]
  char v49; // [rsp+40h] [rbp-C0h]
  char v50; // [rsp+41h] [rbp-BFh]
  int v51; // [rsp+44h] [rbp-BCh]
  __int64 v54; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v55; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v56; // [rsp+68h] [rbp-98h]
  const struct in6_addr *v57; // [rsp+70h] [rbp-90h]
  WCHAR S[72]; // [rsp+80h] [rbp-80h] BYREF

  v6 = a4;
  v56 = a3;
  v54 = 0;
  v55 = 0;
  v49 = 0;
  v10 = 0;
  v11 = 0;
  memset_0(S, 0, 0x82u);
  EnterCriticalSection(a1 + 6);
  v12 = (const struct in6_addr *)(v6 + a3 + 200);
  v57 = v12;
  ClientAddressState = IpTlsGetClientAddressState((_DWORD)a1, a2, (_DWORD)v12, (unsigned int)&v54, (__int64)&v55);
  v14 = v54;
  v51 = ClientAddressState;
  v15 = ClientAddressState;
  if ( v54 )
  {
    v16 = *(_QWORD *)(v54 + 40);
    if ( v16 )
    {
      EventWrite0(
        0x20000000,
        L"(%s: Reference client context (%p)%S:%d",
        *(_QWORD *)(*(_QWORD *)(v16 + 40) + 288LL) + 56LL);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
        McTemplateU0psq_EventWriteTransfer(
          v17,
          (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE,
          *(_QWORD *)(v14 + 40),
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
          108);
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v14 + 40) + 56LL));
      v10 = *(_QWORD *)(v14 + 40);
    }
  }
  v18 = v55;
  if ( v55 )
  {
    v19 = v55[5];
    if ( v19 )
    {
      EventWrite0(
        0x20000000,
        L"(%s: Reference client context (%p)%S:%d",
        *(_QWORD *)(*(_QWORD *)(v19 + 40) + 288LL) + 56LL);
      if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
        McTemplateU0psq_EventWriteTransfer(
          v20,
          (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE,
          v18[5],
          (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
          113);
      _InterlockedIncrement((volatile signed __int32 *)(v18[5] + 56LL));
      v11 = v18[5];
    }
  }
  if ( v15 )
  {
    if ( v15 == 2 )
    {
      if ( !*(_QWORD *)(v14 + 40) )
        goto LABEL_37;
      v31 = AddClientAddressMapping(a2, v12, 1u);
      v32 = (const struct in6_addr *)(v14 + 24);
      if ( v31 )
      {
        RtlIpv6AddressToStringW(v32, S);
        EventWrite0(
          0x10000000,
          L"%s: IpTlsServerProcessDadPacketOrNeighborAdvertisement: entering conflict for address %s",
          *(_QWORD *)(*(_QWORD *)(a2 + 40) + 288LL) + 56LL,
          S);
        v33 = *(_QWORD *)(v14 + 40);
        v34 = *(_QWORD *)(v14 + 16);
        v35 = *(_QWORD *)(v33 + 40);
        RtlRemoveEntryHashTable(v35 + 104, v14, 0);
        RtlInsertEntryHashTable(v35 + 184, v14, v34 | 0x40000000, 0);
        IpTlsUpdatePerfCountersForClient(v33);
        goto LABEL_37;
      }
      RtlIpv6AddressToStringW(v32, S);
      EventWrite0(
        0x10000000,
        L"%s: IpTlsServerProcessDadPacketOrNeighborAdvertisement: failed to move %s to conflict, discarding existing mapping",
        *(_QWORD *)(*(_QWORD *)(a2 + 40) + 288LL) + 56LL,
        S);
      v36 = *(_QWORD *)(v14 + 48);
      if ( *(_QWORD *)(v36 + 8) == v14 + 48 )
      {
        v37 = *(_QWORD **)(v14 + 56);
        if ( *v37 == v14 + 48 )
        {
          *v37 = v36;
          v25 = (_QWORD *)v14;
          *(_QWORD *)(v36 + 8) = v37;
          goto LABEL_33;
        }
      }
LABEL_34:
      __fastfail(3u);
    }
    if ( v15 != 3 )
    {
      if ( v15 != 4 )
        goto LABEL_37;
      RtlIpv6AddressToStringW((const struct in6_addr *)(v14 + 24), S);
      EventWrite0(
        0x10000000,
        L"%s: IpTlsServerProcessDadPacketOrNeighborAdvertisement: received DAD/NA for %s from conflict non-owner",
        *(_QWORD *)(*(_QWORD *)(a2 + 40) + 288LL) + 56LL,
        S);
      v21 = *(_QWORD *)(v14 + 48);
      if ( *(_QWORD *)(v21 + 8) == v14 + 48 )
      {
        v22 = *(_QWORD **)(v14 + 56);
        if ( *v22 == v14 + 48 )
        {
          *v22 = v21;
          *(_QWORD *)(v21 + 8) = v22;
          *(_BYTE *)(*(_QWORD *)(v14 + 40) + 32LL) = 1;
          RemoveClientAddressMapping(v14);
          if ( !v18 )
            goto LABEL_37;
          v23 = v18[6];
          if ( *(_QWORD **)(v23 + 8) == v18 + 6 )
          {
            v24 = (_QWORD *)v18[7];
            if ( (_QWORD *)*v24 == v18 + 6 )
            {
              *v24 = v23;
              *(_QWORD *)(v23 + 8) = v24;
              v25 = v18;
              *(_BYTE *)(v18[5] + 32LL) = 1;
LABEL_33:
              RemoveClientAddressMapping(v25);
              goto LABEL_37;
            }
          }
        }
      }
      goto LABEL_34;
    }
    if ( a6 )
      goto LABEL_37;
    RtlIpv6AddressToStringW((const struct in6_addr *)(v14 + 24), S);
    EventWrite0(
      0x10000000,
      L"%s: IpTlsServerProcessDadPacketOrNeighborAdvertisement: received NA for %s from conflict owner",
      *(_QWORD *)(*(_QWORD *)(a2 + 40) + 288LL) + 56LL,
      S);
    if ( v18 )
    {
      v26 = v18[6];
      if ( *(_QWORD **)(v26 + 8) != v18 + 6 )
        goto LABEL_34;
      v27 = (_QWORD *)v18[7];
      if ( (_QWORD *)*v27 != v18 + 6 )
        goto LABEL_34;
      *v27 = v26;
      *(_QWORD *)(v26 + 8) = v27;
      RemoveClientAddressMapping(v18);
    }
    v28 = *(_QWORD *)(v14 + 40);
    v29 = *(_QWORD *)(v14 + 16);
    v30 = *(_QWORD *)(v28 + 40);
    RtlRemoveEntryHashTable(v30 + 184, v14, 0);
    RtlInsertEntryHashTable(v30 + 104, v14, v29 & 0xFFFFFFFFBFFFFFFFuLL, 0);
    IpTlsUpdatePerfCountersForClient(v28);
  }
  else
  {
    AddClientAddressMapping(a2, v12, 0);
  }
  v49 = 1;
LABEL_37:
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v50 = IpTlsServerForwardDadOrNAPacket((_DWORD)a1, a2, v56, a4, a5, v51, v10, v11);
  v41 = v50;
  if ( v10 )
  {
    LODWORD(v48) = 3825;
    EventWrite0(
      0x20000000,
      L"(%s: Dereference client context (%p) %S:%d",
      *(_QWORD *)(*(_QWORD *)(v10 + 40) + 288LL) + 56LL,
      v10,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      v48);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v42,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE,
        v10,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        241);
    DereferenceClientContextEx(v10);
  }
  if ( v11 )
  {
    LODWORD(v48) = 3829;
    EventWrite0(
      0x20000000,
      L"(%s: Dereference client context (%p) %S:%d",
      *(_QWORD *)(*(_QWORD *)(v11 + 40) + 288LL) + 56LL,
      v11,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      v48);
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x2000) != 0 )
      McTemplateU0psq_EventWriteTransfer(
        v43,
        (unsigned int)EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE,
        v11,
        (unsigned int)"onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
        245);
    DereferenceClientContextEx(v11);
  }
  if ( v49 )
  {
    v44 = IpTlsServerLookupNDEntry(a1, v57);
    v45 = v44;
    if ( v44 )
    {
      v38 = *(_QWORD *)(v44 + 56);
      v39 = *(_DWORD *)(v44 + 64);
      v40 = *(_DWORD *)(v44 + 68);
      *(_QWORD *)(v44 + 56) = 0;
      if ( *(_BYTE *)(v44 + 74) )
      {
        IpTlsServerRemoveNDEntry(a1, v44);
        FREE(v45);
      }
    }
    v41 = v50;
  }
  LeaveCriticalSection(a1 + 6);
  if ( v38 )
  {
    SendBufferOnContext((_DWORD)a1, a2, v38, v39, v40);
    LODWORD(v47) = 3873;
    EventWrite0(
      0x20000000,
      L"(Dereference IPTLS Buffer(%p)%S:%d",
      v38,
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\iptlsserver.c",
      v47);
    IpTlsDereferenceBufferEx(v38);
  }
  return v41;
}

```

## disassembly

```asm
0x180049b88  push    rbp
0x180049b8a  push    rbx
0x180049b8b  push    rsi
0x180049b8c  push    rdi
0x180049b8d  push    r12
0x180049b8f  push    r13
0x180049b91  push    r14
0x180049b93  push    r15
0x180049b95  lea     rbp, [rsp-28h]
0x180049b9a  sub     rsp, 128h
0x180049ba1  mov     rax, cs:__security_cookie
0x180049ba8  xor     rax, rsp
0x180049bab  mov     [rbp+60h+var_50], rax
0x180049baf  xor     eax, eax
0x180049bb1  movsxd  rsi, r9d
0x180049bb4  mov     rdi, r8
0x180049bb7  mov     [rsp+160h+var_F8], r8
0x180049bbc  mov     r12, rdx
0x180049bbf  mov     [rsp+160h+var_110], rcx
0x180049bc4  mov     rbx, rcx
0x180049bc7  mov     [rsp+160h+var_118], esi
0x180049bcb  xor     edx, edx; Val
0x180049bcd  mov     [rsp+160h+var_108], rax
0x180049bd2  mov     r8d, 82h; Size
0x180049bd8  mov     [rsp+160h+var_100], rax
0x180049bdd  lea     rcx, [rbp+60h+S]; void *
0x180049be1  mov     [rsp+160h+var_120], al
0x180049be5  mov     r13d, eax
0x180049be8  mov     r15d, eax
0x180049beb  call    memset_0
0x180049bf0  lea     rcx, [rbx+0F0h]; lpCriticalSection
0x180049bf7  call    cs:__imp_EnterCriticalSection
0x180049bfe  nop     dword ptr [rax+rax+00h]
0x180049c03  mov     rax, rsi
0x180049c06  lea     r9, [rsp+160h+var_108]
0x180049c0b  lea     rsi, [rdi+0C8h]
0x180049c12  mov     rdx, r12
0x180049c15  add     rsi, rax
0x180049c18  mov     rcx, rbx
0x180049c1b  lea     rax, [rsp+160h+var_100]
0x180049c20  mov     [rsp+160h+var_F0], rsi
0x180049c25  mov     r8, rsi
0x180049c28  mov     [rsp+160h+var_140], rax
0x180049c2d  call    IpTlsGetClientAddressState
0x180049c32  mov     r14, [rsp+160h+var_108]
0x180049c37  lea     rcx, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180049c3e  mov     [rsp+160h+var_11C], eax
0x180049c42  mov     edi, eax
0x180049c44  test    r14, r14
0x180049c47  jz      short loc_180049CB7
0x180049c49  mov     r9, [r14+28h]
0x180049c4d  test    r9, r9
0x180049c50  jz      short loc_180049CB7
0x180049c52  mov     rax, [r9+28h]
0x180049c56  lea     rdx, aSReferenceClie; "(%s: Reference client context (%p)%S:%d"
0x180049c5d  mov     ebx, 0E6Ch
0x180049c62  mov     dword ptr [rsp+160h+var_138], ebx
0x180049c66  mov     [rsp+160h+var_140], rcx
0x180049c6b  mov     ecx, 20000000h
0x180049c70  mov     r8, [rax+120h]
0x180049c77  add     r8, 38h ; '8'
0x180049c7b  call    EventWrite0
0x180049c80  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180049c87  jz      short loc_180049CA4
0x180049c89  mov     r8, [r14+28h]
0x180049c8d  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180049c94  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE
0x180049c9b  mov     dword ptr [rsp+160h+var_140], ebx
0x180049c9f  call    McTemplateU0psq_EventWriteTransfer
0x180049ca4  mov     rax, [r14+28h]
0x180049ca8  lock inc dword ptr [rax+38h]
0x180049cac  mov     r13, [r14+28h]
0x180049cb0  lea     rcx, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180049cb7  mov     rbx, [rsp+160h+var_100]
0x180049cbc  test    rbx, rbx
0x180049cbf  jz      short loc_180049D2B
0x180049cc1  mov     r9, [rbx+28h]
0x180049cc5  test    r9, r9
0x180049cc8  jz      short loc_180049D2B
0x180049cca  mov     rax, [r9+28h]
0x180049cce  lea     rdx, aSReferenceClie; "(%s: Reference client context (%p)%S:%d"
0x180049cd5  mov     r15d, 0E71h
0x180049cdb  mov     dword ptr [rsp+160h+var_138], r15d
0x180049ce0  mov     [rsp+160h+var_140], rcx
0x180049ce5  mov     ecx, 20000000h
0x180049cea  mov     r8, [rax+120h]
0x180049cf1  add     r8, 38h ; '8'
0x180049cf5  call    EventWrite0
0x180049cfa  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x180049d01  jz      short loc_180049D1F
0x180049d03  mov     r8, [rbx+28h]
0x180049d07  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x180049d0e  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_REFERENCE
0x180049d15  mov     dword ptr [rsp+160h+var_140], r15d
0x180049d1a  call    McTemplateU0psq_EventWriteTransfer
0x180049d1f  mov     rax, [rbx+28h]
0x180049d23  lock inc dword ptr [rax+38h]
0x180049d27  mov     r15, [rbx+28h]
0x180049d2b  mov     ecx, edi
0x180049d2d  test    edi, edi
0x180049d2f  jz      loc_180049FC6
0x180049d35  sub     ecx, 2
0x180049d38  jz      loc_180049EC4
0x180049d3e  sub     ecx, 1
0x180049d41  jz      loc_180049DFC
0x180049d47  cmp     ecx, 1
0x180049d4a  jnz     loc_180049FD9
0x180049d50  lea     rcx, [r14+18h]; Addr
0x180049d54  lea     rdx, [rbp+60h+S]; S
0x180049d58  call    cs:__imp_RtlIpv6AddressToStringW
0x180049d5f  nop     dword ptr [rax+rax+00h]
0x180049d64  mov     rax, [r12+28h]
0x180049d69  lea     r9, [rbp+60h+S]
0x180049d6d  lea     rdx, aSIptlsserverpr_2; "%s: IpTlsServerProcessDadPacketOrNeighb"...
0x180049d74  mov     ecx, 10000000h
0x180049d79  mov     r8, [rax+120h]
0x180049d80  add     r8, 38h ; '8'
0x180049d84  call    EventWrite0
0x180049d89  lea     rcx, [r14+30h]
0x180049d8d  mov     rdx, [rcx]
0x180049d90  cmp     [rdx+8], rcx
0x180049d94  jnz     loc_180049FBF
0x180049d9a  mov     rax, [rcx+8]
0x180049d9e  cmp     [rax], rcx
0x180049da1  jnz     loc_180049FBF
0x180049da7  mov     [rax], rdx
0x180049daa  mov     rcx, r14
0x180049dad  mov     [rdx+8], rax
0x180049db1  mov     rax, [r14+28h]
0x180049db5  mov     byte ptr [rax+20h], 1
0x180049db9  call    RemoveClientAddressMapping
0x180049dbe  test    rbx, rbx
0x180049dc1  jz      loc_180049FD9
0x180049dc7  lea     rax, [rbx+30h]
0x180049dcb  mov     rdx, [rax]
0x180049dce  cmp     [rdx+8], rax
0x180049dd2  jnz     loc_180049FBF
0x180049dd8  mov     rcx, [rax+8]
0x180049ddc  cmp     [rcx], rax
0x180049ddf  jnz     loc_180049FBF
0x180049de5  mov     [rcx], rdx
0x180049de8  mov     [rdx+8], rcx
0x180049dec  mov     rcx, rbx
0x180049def  mov     rax, [rbx+28h]
0x180049df3  mov     byte ptr [rax+20h], 1
0x180049df7  jmp     loc_180049FB8
0x180049dfc  cmp     [rbp+60h+arg_28], 0
0x180049e03  jnz     loc_180049FD9
0x180049e09  lea     rcx, [r14+18h]; Addr
0x180049e0d  lea     rdx, [rbp+60h+S]; S
0x180049e11  call    cs:__imp_RtlIpv6AddressToStringW
0x180049e18  nop     dword ptr [rax+rax+00h]
0x180049e1d  mov     rax, [r12+28h]
0x180049e22  lea     r9, [rbp+60h+S]
0x180049e26  lea     rdx, aSIptlsserverpr_1; "%s: IpTlsServerProcessDadPacketOrNeighb"...
0x180049e2d  mov     ecx, 10000000h
0x180049e32  mov     r8, [rax+120h]
0x180049e39  add     r8, 38h ; '8'
0x180049e3d  call    EventWrite0
0x180049e42  test    rbx, rbx
0x180049e45  jz      short loc_180049E74
0x180049e47  lea     rax, [rbx+30h]
0x180049e4b  mov     rdx, [rax]
0x180049e4e  cmp     [rdx+8], rax
0x180049e52  jnz     loc_180049FBF
0x180049e58  mov     rcx, [rax+8]
0x180049e5c  cmp     [rcx], rax
0x180049e5f  jnz     loc_180049FBF
0x180049e65  mov     [rcx], rdx
0x180049e68  mov     [rdx+8], rcx
0x180049e6c  mov     rcx, rbx
0x180049e6f  call    RemoveClientAddressMapping
0x180049e74  mov     rsi, [r14+28h]
0x180049e78  xor     r8d, r8d
0x180049e7b  mov     rdi, [r14+10h]
0x180049e7f  mov     rdx, r14
0x180049e82  mov     rbx, [rsi+28h]
0x180049e86  lea     rcx, [rbx+0B8h]
0x180049e8d  call    cs:__imp_RtlRemoveEntryHashTable
0x180049e94  nop     dword ptr [rax+rax+00h]
0x180049e99  btr     rdi, 1Eh
0x180049e9e  lea     rcx, [rbx+68h]
0x180049ea2  mov     r8, rdi
0x180049ea5  xor     r9d, r9d
0x180049ea8  mov     rdx, r14
0x180049eab  call    cs:__imp_RtlInsertEntryHashTable
0x180049eb2  nop     dword ptr [rax+rax+00h]
0x180049eb7  mov     rcx, rsi
0x180049eba  call    IpTlsUpdatePerfCountersForClient
0x180049ebf  jmp     loc_180049FD4
0x180049ec4  cmp     qword ptr [r14+28h], 0
0x180049ec9  jz      loc_180049FD9
0x180049ecf  mov     r8b, 1
0x180049ed2  mov     rdx, rsi
0x180049ed5  mov     rcx, r12
0x180049ed8  call    AddClientAddressMapping
0x180049edd  lea     rcx, [r14+18h]; Addr
0x180049ee1  lea     rdx, [rbp+60h+S]; S
0x180049ee5  test    al, al
0x180049ee7  jz      short loc_180049F67
0x180049ee9  call    cs:__imp_RtlIpv6AddressToStringW
0x180049ef0  nop     dword ptr [rax+rax+00h]
0x180049ef5  mov     rax, [r12+28h]
0x180049efa  lea     r9, [rbp+60h+S]
0x180049efe  lea     rdx, aSIptlsserverpr_0; "%s: IpTlsServerProcessDadPacketOrNeighb"...
0x180049f05  mov     ecx, 10000000h
0x180049f0a  mov     r8, [rax+120h]
0x180049f11  add     r8, 38h ; '8'
0x180049f15  call    EventWrite0
0x180049f1a  mov     rsi, [r14+28h]
0x180049f1e  xor     r8d, r8d
0x180049f21  mov     rdi, [r14+10h]
0x180049f25  mov     rdx, r14
0x180049f28  mov     rbx, [rsi+28h]
0x180049f2c  lea     rcx, [rbx+68h]
0x180049f30  call    cs:__imp_RtlRemoveEntryHashTable
0x180049f37  nop     dword ptr [rax+rax+00h]
0x180049f3c  bts     rdi, 1Eh
0x180049f41  lea     rcx, [rbx+0B8h]
0x180049f48  mov     r8, rdi
0x180049f4b  xor     r9d, r9d
0x180049f4e  mov     rdx, r14
0x180049f51  call    cs:__imp_RtlInsertEntryHashTable
0x180049f58  nop     dword ptr [rax+rax+00h]
0x180049f5d  mov     rcx, rsi
0x180049f60  call    IpTlsUpdatePerfCountersForClient
0x180049f65  jmp     short loc_180049FD9
0x180049f67  call    cs:__imp_RtlIpv6AddressToStringW
0x180049f6e  nop     dword ptr [rax+rax+00h]
0x180049f73  mov     rax, [r12+28h]
0x180049f78  lea     r9, [rbp+60h+S]
0x180049f7c  lea     rdx, aSIptlsserverpr; "%s: IpTlsServerProcessDadPacketOrNeighb"...
0x180049f83  mov     ecx, 10000000h
0x180049f88  mov     r8, [rax+120h]
0x180049f8f  add     r8, 38h ; '8'
0x180049f93  call    EventWrite0
0x180049f98  lea     rcx, [r14+30h]
0x180049f9c  mov     rdx, [rcx]
0x180049f9f  cmp     [rdx+8], rcx
0x180049fa3  jnz     short loc_180049FBF
0x180049fa5  mov     rax, [rcx+8]
0x180049fa9  cmp     [rax], rcx
0x180049fac  jnz     short loc_180049FBF
0x180049fae  mov     [rax], rdx
0x180049fb1  mov     rcx, r14
0x180049fb4  mov     [rdx+8], rax
0x180049fb8  call    RemoveClientAddressMapping
0x180049fbd  jmp     short loc_180049FD9
0x180049fbf  mov     ecx, 3
0x180049fc4  int     29h; Win8: RtlFailFast(ecx)
0x180049fc6  xor     r8d, r8d
0x180049fc9  mov     rdx, rsi
0x180049fcc  mov     rcx, r12
0x180049fcf  call    AddClientAddressMapping
0x180049fd4  mov     [rsp+160h+var_120], 1
0x180049fd9  mov     eax, [rsp+160h+var_11C]
0x180049fdd  mov     rdx, r12
0x180049fe0  mov     r9d, [rsp+160h+var_118]
0x180049fe5  xor     edi, edi
0x180049fe7  mov     r8, [rsp+160h+var_F8]
0x180049fec  xor     esi, esi
0x180049fee  mov     rcx, [rsp+160h+var_110]
0x180049ff3  xor     r14d, r14d
0x180049ff6  mov     [rsp+160h+var_128], r15
0x180049ffb  mov     [rsp+160h+var_130], r13
0x18004a000  mov     dword ptr [rsp+160h+var_138], eax
0x18004a004  mov     eax, [rbp+60h+arg_20]
0x18004a00a  mov     dword ptr [rsp+160h+var_140], eax
0x18004a00e  call    IpTlsServerForwardDadOrNAPacket
0x18004a013  mov     [rsp+160h+var_11F], al
0x18004a017  mov     bl, al
0x18004a019  test    r13, r13
0x18004a01c  jz      short loc_18004A084
0x18004a01e  mov     rcx, [r13+28h]
0x18004a022  lea     rax, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18004a029  mov     dword ptr [rsp+160h+var_138], 0EF1h
0x18004a031  lea     rdx, aSDereferenceCl; "(%s: Dereference client context (%p) %S"...
0x18004a038  mov     r9, r13
0x18004a03b  mov     [rsp+160h+var_140], rax
0x18004a040  mov     r8, [rcx+120h]
0x18004a047  mov     ecx, 20000000h
0x18004a04c  add     r8, 38h ; '8'
0x18004a050  call    EventWrite0
0x18004a055  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+1, 20h
0x18004a05c  jz      short loc_18004A07C
0x18004a05e  lea     r9, aOnecoreuapNetN_11; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18004a065  mov     dword ptr [rsp+160h+var_140], 0EF1h
0x18004a06d  mov     r8, r13
0x18004a070  lea     rdx, EVENT_IPHLPSVC_ETW_IPHTTPS_SERVER_CLIENT_CONTEXT_DEREFERENCE
0x18004a077  call    McTemplateU0psq_EventWriteTransfer
0x18004a07c  mov     rcx, r13
0x18004a07f  call    DereferenceClientContextEx
0x18004a084  xor     r13d, r13d
0x18004a087  test    r15, r15
0x18004a08a  jz      short loc_18004A0F2
0x18004a08c  mov     rax, [r15+28h]
0x18004a090  lea     rdx, aSDereferenceCl; "(%s: Dereference client context (%p) %S"...
0x18004a097  mov     dword ptr [rsp+160h+var_138], 0EF5h
0x18004a09f  mov     r9, r15
0x18004a0a2  mov     ecx, 20000000h
  ... truncated ...
```
