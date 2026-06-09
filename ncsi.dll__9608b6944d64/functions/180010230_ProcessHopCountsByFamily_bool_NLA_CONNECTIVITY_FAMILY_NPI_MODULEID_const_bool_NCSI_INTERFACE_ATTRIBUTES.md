# ProcessHopCountsByFamily(bool,_NLA_CONNECTIVITY_FAMILY,_NPI_MODULEID const *,bool &,NCSI_INTERFACE_ATTRIBUTES *)

- ea: `0x180010230`
- end: `0x18001085b`
- name: `?ProcessHopCountsByFamily@@YAX_NW4_NLA_CONNECTIVITY_FAMILY@@PEBU_NPI_MODULEID@@AEA_NPEAVNCSI_INTERFACE_ATTRIBUTES@@@Z`
- size: `1579`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update`

## callers

- `0x180010060`

## callees

- `0x180009804`
- `0x18000e350`
- `0x180010230`
- `0x18001e004`
- `0x1800249f0`
- `0x180033e90`
- `0x1800343d0`
- `0x180047240`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800103ca`
- `ntdll!EtwEventWriteTransfer` at `0x18001072b`
- `ntdll!EtwEventWriteTransfer` at `0x1800103ca`
- `ntdll!EtwEventWriteTransfer` at `0x18001072b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001082e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001082e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010271`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010271`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800104c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800104c3`

## string_xrefs

- `0x18001032a`: `Caller indicated 0 off-link routes`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ProcessHopCountsByFamily(char a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rdi
  int v8; // eax
  _QWORD *v9; // r12
  const char *v10; // r15
  __int64 v11; // r14
  const char *v12; // rcx
  __int64 v13; // rax
  int v14; // ebx
  __int64 v15; // r9
  unsigned int v16; // r10d
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  const char *v20; // rax
  unsigned int v21; // r8d
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 v25; // r11
  const unsigned __int16 *v26; // [rsp+40h] [rbp-91h] BYREF
  const unsigned __int16 *v27; // [rsp+48h] [rbp-89h] BYREF
  const unsigned __int16 *v28; // [rsp+50h] [rbp-81h] BYREF
  const unsigned __int16 *v29; // [rsp+58h] [rbp-79h] BYREF
  __int64 v30; // [rsp+60h] [rbp-71h]
  char *v31; // [rsp+70h] [rbp-61h] BYREF
  int v32; // [rsp+78h] [rbp-59h]
  int v33; // [rsp+7Ch] [rbp-55h]
  char *v34; // [rsp+80h] [rbp-51h]
  int v35; // [rsp+88h] [rbp-49h]
  int v36; // [rsp+8Ch] [rbp-45h]
  const char *v37; // [rsp+90h] [rbp-41h]
  __int64 v38; // [rsp+98h] [rbp-39h]
  const char *v39; // [rsp+A0h] [rbp-31h]
  __int64 v40; // [rsp+A8h] [rbp-29h]
  const unsigned __int16 **v41; // [rsp+B0h] [rbp-21h]
  __int64 v42; // [rsp+B8h] [rbp-19h]
  const char *v43; // [rsp+C0h] [rbp-11h]
  int v44; // [rsp+C8h] [rbp-9h]
  int v45; // [rsp+CCh] [rbp-5h]
  __int64 v46; // [rsp+D0h] [rbp-1h] BYREF
  __int64 v47; // [rsp+D8h] [rbp+7h]

  v6 = a2;
  EnterCriticalSection(&g_ncsiLock);
  v46 = (__int64)&g_ncsiLock;
  v8 = g_nsiIpv6IfaceTableForHops;
  if ( !(_DWORD)v6 )
    v8 = g_nsiIpv4IfaceTableForHops;
  v9 = &g_nsiIpv4IfaceTableForHops;
  if ( (_DWORD)v6 )
    v9 = &g_nsiIpv6IfaceTableForHops;
  v10 = "UnknownConnectivityFamily";
  v11 = -1;
  if ( !a1 )
  {
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      if ( (_DWORD)v6 )
      {
        if ( (_DWORD)v6 == 1 )
          v12 = "IPv6";
        else
          v12 = "UnknownConnectivityFamily";
      }
      else
      {
        v12 = "IPv4";
      }
      v27 = *(const unsigned __int16 **)a5;
      v13 = -1;
      do
        ++v13;
      while ( v12[v13] );
      v43 = v12;
      v44 = v13 + 1;
      v45 = 0;
      v41 = &v27;
      v42 = 8;
      v39 = "Caller indicated 0 off-link routes";
      v40 = 35;
      v37 = "Clearing NsiIfaceTableForHops";
      v38 = 30;
      v29 = (const unsigned __int16 *)0x50B000000LL;
      v30 = 0;
      v31 = (char *)off_18009A088;
      v32 = *(unsigned __int16 *)off_18009A088;
      v33 = 2;
      v34 = (char *)&unk_180088CA0;
      v35 = 66;
      v36 = 1;
      LODWORD(v26) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(qword_18009A0A0, &v29, 0, 0, 6, &v31);
    }
LABEL_15:
    if ( *(_DWORD *)(a5 + 24) )
    {
      if ( (unsigned int)dword_18009A080 > 5 )
      {
        if ( (_DWORD)v6 )
        {
          if ( (_DWORD)v6 == 1 )
            v10 = "IPv6";
        }
        else
        {
          v10 = "IPv4";
        }
        v29 = *(const unsigned __int16 **)a5;
        do
          ++v11;
        while ( v10[v11] );
        v43 = v10;
        v44 = v11 + 1;
        v45 = 0;
        v41 = &v29;
        v42 = 8;
        v39 = "pInterface is disconnected";
        v40 = 27;
        v37 = "Skipping";
        v38 = 9;
        v46 = 0x50B000000LL;
        v47 = 0;
        v31 = (char *)off_18009A088;
        v32 = *(unsigned __int16 *)off_18009A088;
        v34 = byte_180088B25;
        v21 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        goto LABEL_54;
      }
    }
    else if ( !(unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(a5, (unsigned int)v6)
           || (unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot() )
    {
      if ( *(_QWORD *)(3944 * v6 + a5 + 4448) )
      {
        if ( *(_DWORD *)v9 )
        {
          v25 = 0;
          while ( *(_QWORD *)a5 != *(_QWORD *)(v9[1] + 8 * v25) )
          {
            v25 = (unsigned int)(v25 + 1);
            if ( (unsigned int)v25 >= *(_DWORD *)v9 )
              goto LABEL_68;
          }
        }
        else
        {
LABEL_68:
          UpdateConnectivityFromPassivePolling((unsigned int)v6, a5, 2, a4);
        }
      }
    }
    else if ( (unsigned int)dword_18009A080 > 5 )
    {
      if ( (_DWORD)v6 )
      {
        if ( (_DWORD)v6 == 1 )
          v10 = "IPv6";
      }
      else
      {
        v10 = "IPv4";
      }
      v29 = (const unsigned __int16 *)v10;
      v28 = *(const unsigned __int16 **)a5;
      v27 = (const unsigned __int16 *)"pInterface is behind hotspot";
      v26 = (const unsigned __int16 *)"Skipping";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        v22,
        (unsigned __int8 *)&unk_180088B68,
        v23,
        v24,
        &v26,
        &v27,
        (__int64)&v28,
        &v29);
    }
    goto LABEL_69;
  }
  v14 = 0;
  if ( !v8 )
    goto LABEL_15;
  if ( !*(_DWORD *)v9 )
    HIDWORD(v30) = 0;
  while ( (unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(a5, (unsigned int)v6)
       && !(unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot()
       || *(_QWORD *)a5 != v15 )
  {
LABEL_40:
    if ( (unsigned int)++v14 >= *(_DWORD *)v9 )
      goto LABEL_15;
  }
  if ( g_ncsiClientPresent == 1 )
  {
    LODWORD(v26) = 2;
    if ( !(unsigned int)NcsiClassifyPacket((unsigned int)v6, v16, *(_QWORD *)(3944 * v6 + a5 + 4448)) )
    {
      if ( *(_DWORD *)(a5 + 24) )
      {
        if ( GetTickCount() - *(_DWORD *)(a5 + 11688) > 0x3A98 )
        {
          if ( (unsigned int)dword_18009A080 > 5 )
          {
            if ( (_DWORD)v6 )
            {
              if ( (_DWORD)v6 == 1 )
                v20 = "IPv6";
              else
                v20 = "UnknownConnectivityFamily";
            }
            else
            {
              v20 = "IPv4";
            }
            v27 = (const unsigned __int16 *)v20;
            v26 = *(const unsigned __int16 **)a5;
            v28 = (const unsigned __int16 *)"pInterface has been getting packets more than 15s after disconnect";
            v29 = (const unsigned __int16 *)"Re-Evaluating adapter state";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
              v17,
              (unsigned __int8 *)&dword_180088C04,
              v18,
              v19,
              &v29,
              &v28,
              (__int64)&v26,
              &v27);
          }
          NHM::NhmNetReadyMonitor::ReevaluateAdapterState((NHM::NhmNetReadyMonitor *)&g_ncsiNetReadyMonitor);
        }
      }
      else
      {
        UpdateConnectivityFromPassivePolling((unsigned int)v6, a5, (unsigned int)v26, a4);
      }
    }
    goto LABEL_40;
  }
  if ( (unsigned int)dword_18009A080 > 5 )
  {
    if ( (_DWORD)v6 )
    {
      if ( (_DWORD)v6 == 1 )
        v10 = "IPv6";
    }
    else
    {
      v10 = "IPv4";
    }
    v29 = *(const unsigned __int16 **)a5;
    do
      ++v11;
    while ( v10[v11] );
    v43 = v10;
    v44 = v11 + 1;
    v45 = 0;
    v41 = &v29;
    v42 = 8;
    v39 = "Client is absent";
    v40 = 17;
    v37 = "Skipping";
    v38 = 9;
    v46 = 0x50B000000LL;
    v47 = 0;
    v31 = (char *)off_18009A088;
    v32 = *(unsigned __int16 *)off_18009A088;
    v34 = byte_180088BC1;
    v21 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
LABEL_54:
    v36 = 1;
    v35 = 66;
    v33 = 2;
    LODWORD(v26) = v21;
    EtwEventWriteTransfer(qword_18009A0A0, &v46, 0, 0, 6, &v31);
  }
LABEL_69:
  LeaveCriticalSection(&g_ncsiLock);
}

```

## disassembly

```asm
0x180010230  mov     [rsp-8+arg_0], rbx
0x180010235  push    rbp
0x180010236  push    rsi
0x180010237  push    rdi
0x180010238  push    r12
0x18001023a  push    r13
0x18001023c  push    r14
0x18001023e  push    r15
0x180010240  lea     rbp, [rsp-1Fh]
0x180010245  sub     rsp, 0F0h
0x18001024c  mov     rax, cs:__security_cookie
0x180010253  xor     rax, rsp
0x180010256  mov     [rbp+4Fh+var_40], rax
0x18001025a  mov     r13, r9
0x18001025d  movsxd  rdi, edx
0x180010260  movzx   ebx, cl
0x180010263  mov     rsi, [rbp+4Fh+arg_20]
0x180010267  lea     r14, ?g_ncsiLock@@3Vcritical_section@wil@@A; wil::critical_section g_ncsiLock
0x18001026e  mov     rcx, r14; lpCriticalSection
0x180010271  call    cs:__imp_EnterCriticalSection
0x180010277  mov     [rbp+4Fh+var_50], r14
0x18001027b  mov     eax, cs:?g_nsiIpv6IfaceTableForHops@@3V?$TNcsiNsiTable@U_NL_INTERFACE_KEY@@U_NL_INTERFACE_HOP_ROD@@@@A; TNcsiNsiTable<_NL_INTERFACE_KEY,_NL_INTERFACE_HOP_ROD> g_nsiIpv6IfaceTableForHops
0x180010281  test    edi, edi
0x180010283  cmovz   eax, cs:?g_nsiIpv4IfaceTableForHops@@3V?$TNcsiNsiTable@U_NL_INTERFACE_KEY@@U_NL_INTERFACE_HOP_ROD@@@@A; TNcsiNsiTable<_NL_INTERFACE_KEY,_NL_INTERFACE_HOP_ROD> g_nsiIpv4IfaceTableForHops
0x18001028a  lea     rcx, ?g_nsiIpv6IfaceTableForHops@@3V?$TNcsiNsiTable@U_NL_INTERFACE_KEY@@U_NL_INTERFACE_HOP_ROD@@@@A; TNcsiNsiTable<_NL_INTERFACE_KEY,_NL_INTERFACE_HOP_ROD> g_nsiIpv6IfaceTableForHops
0x180010291  lea     r12, ?g_nsiIpv4IfaceTableForHops@@3V?$TNcsiNsiTable@U_NL_INTERFACE_KEY@@U_NL_INTERFACE_HOP_ROD@@@@A; TNcsiNsiTable<_NL_INTERFACE_KEY,_NL_INTERFACE_HOP_ROD> g_nsiIpv4IfaceTableForHops
0x180010298  cmovnz  r12, rcx
0x18001029c  lea     r15, aUnknownconnect; "UnknownConnectivityFamily"
0x1800102a3  mov     r14, 0FFFFFFFFFFFFFFFFh
0x1800102aa  lea     r8, _TraceLoggingMetadataEnd
0x1800102b1  lea     r11, _TraceLoggingMetadata
0x1800102b8  test    bl, bl
0x1800102ba  jnz     loc_180010414
0x1800102c0  mov     eax, cs:dword_18009A080
0x1800102c6  cmp     eax, 5
0x1800102c9  jbe     loc_1800103DE
0x1800102cf  test    edi, edi
0x1800102d1  jz      short loc_1800102E6
0x1800102d3  cmp     edi, 1
0x1800102d6  jz      short loc_1800102DD
0x1800102d8  mov     rcx, r15
0x1800102db  jmp     short loc_1800102ED
0x1800102dd  lea     rcx, aIpv6; "IPv6"
0x1800102e4  jmp     short loc_1800102ED
0x1800102e6  lea     rcx, aIpv4; "IPv4"
0x1800102ed  mov     rax, [rsi]
0x1800102f0  mov     [rsp+120h+var_D8], rax
0x1800102f5  mov     rax, r14
0x1800102f8  nop     dword ptr [rax+rax+00000000h]
0x180010300  inc     rax
0x180010303  cmp     byte ptr [rcx+rax], 0
0x180010307  jnz     short loc_180010300
0x180010309  mov     [rbp+4Fh+var_60], rcx
0x18001030d  inc     eax
0x18001030f  mov     [rbp+4Fh+var_58], eax
0x180010312  mov     [rbp+4Fh+var_54], 0
0x180010319  lea     rax, [rsp+120h+var_D8]
0x18001031e  mov     [rbp+4Fh+var_70], rax
0x180010322  mov     [rbp+4Fh+var_68], 8
0x18001032a  lea     rax, aCallerIndicate; "Caller indicated 0 off-link routes"
0x180010331  mov     [rbp+4Fh+var_80], rax
0x180010335  mov     [rbp+4Fh+var_78], 23h ; '#'
0x18001033d  lea     rax, aClearingNsiifa; "Clearing NsiIfaceTableForHops"
0x180010344  mov     [rbp+4Fh+var_90], rax
0x180010348  mov     [rbp+4Fh+var_88], 1Eh
0x180010350  mov     dword ptr [rbp+4Fh+var_C8], 0B000000h
0x180010357  movzx   eax, cs:word_180088C96
0x18001035e  mov     dword ptr [rbp+4Fh+var_C8+4], eax
0x180010361  mov     [rbp+4Fh+var_C0], 0
0x180010369  mov     rax, cs:off_18009A088
0x180010370  mov     [rbp+4Fh+var_B0], rax
0x180010374  movzx   eax, word ptr [rax]
0x180010377  mov     [rbp+4Fh+var_A8], eax
0x18001037a  mov     [rbp+4Fh+var_A4], 2
0x180010381  lea     rax, unk_180088CA0
0x180010388  mov     [rbp+4Fh+var_A0], rax
0x18001038c  mov     [rbp+4Fh+var_98], 42h ; 'B'
0x180010393  mov     [rbp+4Fh+var_94], 1
0x18001039a  mov     rax, r8
0x18001039d  sub     eax, r11d
0x1800103a0  mov     dword ptr [rsp+120h+var_E0], eax
0x1800103a4  mov     eax, dword ptr [rsp+120h+var_E0]
0x1800103a8  lea     rax, [rbp+4Fh+var_B0]
0x1800103ac  mov     [rsp+120h+var_F8], rax
0x1800103b1  mov     dword ptr [rsp+120h+var_100], 6
0x1800103b9  xor     r9d, r9d
0x1800103bc  xor     r8d, r8d
0x1800103bf  lea     rdx, [rbp+4Fh+var_C8]
0x1800103c3  mov     rcx, cs:qword_18009A0A0
0x1800103ca  call    cs:__imp_EtwEventWriteTransfer
0x1800103d0  lea     r11, _TraceLoggingMetadata
0x1800103d7  lea     r8, _TraceLoggingMetadataEnd
0x1800103de  cmp     dword ptr [rsi+18h], 0
0x1800103e2  jz      loc_180010736
0x1800103e8  mov     eax, cs:dword_18009A080
0x1800103ee  cmp     eax, 5
0x1800103f1  jbe     loc_180010827
0x1800103f7  test    edi, edi
0x1800103f9  jz      loc_180010648
0x1800103ff  cmp     edi, 1
0x180010402  jnz     loc_18001064F
0x180010408  lea     r15, aIpv6; "IPv6"
0x18001040f  jmp     loc_18001064F
0x180010414  xor     ebx, ebx
0x180010416  test    eax, eax
0x180010418  jz      short loc_1800103DE
0x18001041a  cmp     ebx, [r12]
0x18001041e  jnb     short loc_180010435
0x180010420  mov     rax, [r12+8]
0x180010425  mov     r9, [rax+rbx*8]
0x180010429  mov     rax, [r12+18h]
0x18001042e  movzx   r10d, byte ptr [rax+rbx]
0x180010433  jmp     short loc_180010440
0x180010435  xor     r9d, r9d
0x180010438  xor     r10d, r10d
0x18001043b  xor     eax, eax
0x18001043d  mov     dword ptr [rbp+4Fh+var_C0+4], eax
0x180010440  mov     edx, edi
0x180010442  mov     rcx, rsi
0x180010445  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x18001044a  test    al, al
0x18001044c  jz      short loc_18001045B
0x18001044e  call    ?HasInternetBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x180010453  test    al, al
0x180010455  jz      loc_180010566
0x18001045b  cmp     [rsi], r9
0x18001045e  jnz     loc_180010566
0x180010464  mov     eax, cs:?g_ncsiClientPresent@@3U?$atomic@W4_NCSI_CLIENT_PRESENCE@@@std@@A; std::atomic<_NCSI_CLIENT_PRESENCE> g_ncsiClientPresent
0x18001046a  nop
0x18001046b  cmp     eax, 1
0x18001046e  jnz     loc_180010577
0x180010474  mov     dword ptr [rsp+120h+var_E0], 2
0x18001047c  imul    r8, rdi, 0F68h
0x180010483  lea     rax, [rsp+120h+var_E0]
0x180010488  mov     [rsp+120h+var_100], rax
0x18001048d  mov     r8, [r8+rsi+1160h]
0x180010495  mov     edx, r10d
0x180010498  mov     ecx, edi
0x18001049a  call    ?NcsiClassifyPacket@@YAKW4_NLA_CONNECTIVITY_FAMILY@@K_KT_NET_LUID_LH@@AEAW4NcsiPacketType@@@Z; NcsiClassifyPacket(_NLA_CONNECTIVITY_FAMILY,ulong,unsigned __int64,_NET_LUID_LH,NcsiPacketType &)
0x18001049f  test    eax, eax
0x1800104a1  jnz     loc_180010566
0x1800104a7  cmp     [rsi+18h], eax
0x1800104aa  jnz     short loc_1800104C3
0x1800104ac  mov     r9, r13
0x1800104af  mov     r8d, dword ptr [rsp+120h+var_E0]
0x1800104b4  mov     rdx, rsi
0x1800104b7  mov     ecx, edi
0x1800104b9  call    ?UpdateConnectivityFromPassivePolling@@YAXW4_NLA_CONNECTIVITY_FAMILY@@PEAVNCSI_INTERFACE_ATTRIBUTES@@W4NcsiPacketType@@AEA_N@Z; UpdateConnectivityFromPassivePolling(_NLA_CONNECTIVITY_FAMILY,NCSI_INTERFACE_ATTRIBUTES *,NcsiPacketType,bool &)
0x1800104be  jmp     loc_180010566
0x1800104c3  call    cs:__imp_GetTickCount
0x1800104c9  sub     eax, [rsi+2DA8h]
0x1800104cf  cmp     eax, 3A98h
0x1800104d4  jbe     loc_180010566
0x1800104da  mov     eax, cs:dword_18009A080
0x1800104e0  cmp     eax, 5
0x1800104e3  jbe     short loc_18001055A
0x1800104e5  test    edi, edi
0x1800104e7  jz      short loc_1800104FC
0x1800104e9  cmp     edi, 1
0x1800104ec  jz      short loc_1800104F3
0x1800104ee  mov     rax, r15
0x1800104f1  jmp     short loc_180010503
0x1800104f3  lea     rax, aIpv6; "IPv6"
0x1800104fa  jmp     short loc_180010503
0x1800104fc  lea     rax, aIpv4; "IPv4"
0x180010503  mov     [rsp+120h+var_D8], rax
0x180010508  mov     rax, [rsi]
0x18001050b  mov     [rsp+120h+var_E0], rax
0x180010510  lea     rax, aPinterfaceHasB; "pInterface has been getting packets mor"...
0x180010517  mov     [rsp+120h+var_D0], rax
0x18001051c  lea     rax, aReEvaluatingAd; "Re-Evaluating adapter state"
0x180010523  mov     [rbp+4Fh+var_C8], rax
0x180010527  lea     rax, [rsp+120h+var_D8]
0x18001052c  mov     [rsp+120h+var_E8], rax
0x180010531  lea     rax, [rsp+120h+var_E0]
0x180010536  mov     [rsp+120h+var_F0], rax
0x18001053b  lea     rax, [rsp+120h+var_D0]
0x180010540  mov     [rsp+120h+var_F8], rax
0x180010545  lea     rax, [rbp+4Fh+var_C8]
0x180010549  mov     [rsp+120h+var_100], rax
0x18001054e  lea     rdx, dword_180088C04
0x180010555  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x18001055a  lea     rcx, ?g_ncsiNetReadyMonitor@@3VNhmNetReadyMonitor@NHM@@A; this
0x180010561  call    ?ReevaluateAdapterState@NhmNetReadyMonitor@NHM@@QEBAXXZ; NHM::NhmNetReadyMonitor::ReevaluateAdapterState(void)
0x180010566  inc     ebx
0x180010568  cmp     ebx, [r12]
0x18001056c  jb      loc_180010420
0x180010572  jmp     loc_1800103D0
0x180010577  mov     eax, cs:dword_18009A080
0x18001057d  cmp     eax, 5
0x180010580  jbe     loc_180010827
0x180010586  test    edi, edi
0x180010588  jz      short loc_180010598
0x18001058a  cmp     edi, 1
0x18001058d  jnz     short loc_18001059F
0x18001058f  lea     r15, aIpv6; "IPv6"
0x180010596  jmp     short loc_18001059F
0x180010598  lea     r15, aIpv4; "IPv4"
0x18001059f  mov     rax, [rsi]
0x1800105a2  mov     [rbp+4Fh+var_C8], rax
0x1800105a6  nop     word ptr [rax+rax+00000000h]
0x1800105b0  lea     r14, [r14+1]
0x1800105b4  cmp     byte ptr [r15+r14], 0
0x1800105b9  jnz     short loc_1800105B0
0x1800105bb  mov     [rbp+4Fh+var_60], r15
0x1800105bf  lea     eax, [r14+1]
0x1800105c3  mov     [rbp+4Fh+var_58], eax
0x1800105c6  xor     ecx, ecx
0x1800105c8  mov     [rbp+4Fh+var_54], ecx
0x1800105cb  lea     rax, [rbp+4Fh+var_C8]
0x1800105cf  mov     [rbp+4Fh+var_70], rax
0x1800105d3  mov     [rbp+4Fh+var_68], 8
0x1800105db  lea     rax, aClientIsAbsent; "Client is absent"
0x1800105e2  mov     [rbp+4Fh+var_80], rax
0x1800105e6  mov     [rbp+4Fh+var_78], 11h
0x1800105ee  lea     rax, aSkipping; "Skipping"
0x1800105f5  mov     [rbp+4Fh+var_90], rax
0x1800105f9  mov     [rbp+4Fh+var_88], 9
0x180010601  mov     dword ptr [rbp+4Fh+var_50], 0B000000h
0x180010608  movzx   eax, cs:word_180088BB7
0x18001060f  mov     dword ptr [rbp+4Fh+var_50+4], eax
0x180010612  mov     [rbp+4Fh+var_48], rcx
0x180010616  mov     rax, cs:off_18009A088
0x18001061d  mov     [rbp+4Fh+var_B0], rax
0x180010621  movzx   eax, word ptr [rax]
0x180010624  mov     [rbp+4Fh+var_A8], eax
0x180010627  lea     rax, byte_180088BC1
0x18001062e  mov     [rbp+4Fh+var_A0], rax
0x180010632  lea     r8, _TraceLoggingMetadataEnd
0x180010639  lea     rax, _TraceLoggingMetadata
0x180010640  sub     r8d, eax
0x180010643  jmp     loc_1800106EB
0x180010648  lea     r15, aIpv4; "IPv4"
0x18001064f  mov     rax, [rsi]
0x180010652  mov     [rbp+4Fh+var_C8], rax
0x180010656  nop     word ptr [rax+rax+00000000h]
0x180010660  lea     r14, [r14+1]
0x180010664  cmp     byte ptr [r15+r14], 0
0x180010669  jnz     short loc_180010660
0x18001066b  mov     [rbp+4Fh+var_60], r15
0x18001066f  lea     eax, [r14+1]
0x180010673  mov     [rbp+4Fh+var_58], eax
0x180010676  mov     [rbp+4Fh+var_54], 0
0x18001067d  lea     rax, [rbp+4Fh+var_C8]
0x180010681  mov     [rbp+4Fh+var_70], rax
0x180010685  mov     [rbp+4Fh+var_68], 8
0x18001068d  lea     rax, aPinterfaceIsDi; "pInterface is disconnected"
0x180010694  mov     [rbp+4Fh+var_80], rax
0x180010698  mov     [rbp+4Fh+var_78], 1Bh
0x1800106a0  lea     rax, aSkipping; "Skipping"
0x1800106a7  mov     [rbp+4Fh+var_90], rax
0x1800106ab  mov     [rbp+4Fh+var_88], 9
0x1800106b3  mov     dword ptr [rbp+4Fh+var_50], 0B000000h
0x1800106ba  movzx   eax, cs:word_180088B1B
0x1800106c1  mov     dword ptr [rbp+4Fh+var_50+4], eax
0x1800106c4  mov     [rbp+4Fh+var_48], 0
0x1800106cc  mov     rax, cs:off_18009A088
0x1800106d3  mov     [rbp+4Fh+var_B0], rax
0x1800106d7  movzx   eax, word ptr [rax]
0x1800106da  mov     [rbp+4Fh+var_A8], eax
0x1800106dd  lea     rax, byte_180088B25
0x1800106e4  mov     [rbp+4Fh+var_A0], rax
0x1800106e8  sub     r8d, r11d
0x1800106eb  mov     [rbp+4Fh+var_94], 1
0x1800106f2  mov     [rbp+4Fh+var_98], 42h ; 'B'
0x1800106f9  mov     [rbp+4Fh+var_A4], 2
0x180010700  mov     dword ptr [rsp+120h+var_E0], r8d
0x180010705  mov     eax, dword ptr [rsp+120h+var_E0]
0x180010709  lea     rax, [rbp+4Fh+var_B0]
0x18001070d  mov     [rsp+120h+var_F8], rax
0x180010712  mov     dword ptr [rsp+120h+var_100], 6
0x18001071a  xor     r9d, r9d
0x18001071d  xor     r8d, r8d
0x180010720  lea     rdx, [rbp+4Fh+var_50]
0x180010724  mov     rcx, cs:qword_18009A0A0
0x18001072b  call    cs:__imp_EtwEventWriteTransfer
0x180010731  jmp     loc_180010827
0x180010736  mov     edx, edi
0x180010738  mov     rcx, rsi
0x18001073b  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x180010740  test    al, al
0x180010742  jz      loc_1800107D6
0x180010748  call    ?HasInternetBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x18001074d  test    al, al
0x18001074f  jnz     loc_1800107D6
0x180010755  mov     eax, cs:dword_18009A080
0x18001075b  cmp     eax, 5
0x18001075e  jbe     loc_180010827
0x180010764  test    edi, edi
0x180010766  jz      short loc_180010776
0x180010768  cmp     edi, 1
0x18001076b  jnz     short loc_18001077D
0x18001076d  lea     r15, aIpv6; "IPv6"
0x180010774  jmp     short loc_18001077D
0x180010776  lea     r15, aIpv4; "IPv4"
0x18001077d  mov     [rbp+4Fh+var_C8], r15
0x180010781  mov     rax, [rsi]
0x180010784  mov     [rsp+120h+var_D0], rax
0x180010789  lea     rax, aPinterfaceIsBe; "pInterface is behind hotspot"
0x180010790  mov     [rsp+120h+var_D8], rax
  ... truncated ...
```
