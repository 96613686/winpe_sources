# ProcessUnreachablePathsByFamily<_IPV6_PATH_KEY,_IPV6_PATH_ROD>(_NLA_CONNECTIVITY_FAMILY,NCSI_INTERFACE_ATTRIBUTES *,ulong,Ncsi::Proxy::Info const &,TNcsiNsiTable<_IPV6_PATH_KEY,_IPV6_PATH_ROD> const &,NCSI_PASSIVE_POLL_DATA_IN const &,bool &)

- ea: `0x180033010`
- end: `0x180033e86`
- name: `??$ProcessUnreachablePathsByFamily@U_IPV6_PATH_KEY@@U_IPV6_PATH_ROD@@@@YAXW4_NLA_CONNECTIVITY_FAMILY@@PEAVNCSI_INTERFACE_ATTRIBUTES@@KAEBVInfo@Proxy@Ncsi@@AEBV?$TNcsiNsiTable@U_IPV6_PATH_KEY@@U_IPV6_PATH_ROD@@@@AEBUNCSI_PASSIVE_POLL_DATA_IN@@AEA_N@Z`
- size: `3702`
- prototype: `void __fastcall(int, NCSI_INTERFACE_ATTRIBUTES *, unsigned int, Ncsi::Proxy::Info *, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010870`

## callees

- `0x180009804`
- `0x1800099b8`
- `0x18000a6f8`
- `0x18000e350`
- `0x180013eb0`
- `0x18001a5fc`
- `0x18001e004`
- `0x18001f7b0`
- `0x180025638`
- `0x180029b5c`
- `0x18002b174`
- `0x18002cdfc`
- `0x180031fac`
- `0x180033010`
- `0x180047240`
- `0x180057264`
- `0x18005aae4`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x180033496`
- `ntdll!EtwEventWriteTransfer` at `0x180033732`
- `ntdll!EtwEventWriteTransfer` at `0x180033834`
- `ntdll!EtwEventWriteTransfer` at `0x180033960`
- `ntdll!EtwEventWriteTransfer` at `0x180033a61`
- `ntdll!EtwEventWriteTransfer` at `0x180033c76`
- `ntdll!EtwEventWriteTransfer` at `0x180033e4e`
- `ntdll!EtwEventWriteTransfer` at `0x180033496`
- `ntdll!EtwEventWriteTransfer` at `0x180033732`
- `ntdll!EtwEventWriteTransfer` at `0x180033834`
- `ntdll!EtwEventWriteTransfer` at `0x180033960`
- `ntdll!EtwEventWriteTransfer` at `0x180033a61`
- `ntdll!EtwEventWriteTransfer` at `0x180033c76`
- `ntdll!EtwEventWriteTransfer` at `0x180033e4e`

## string_xrefs

- `0x180033b2c`: `Found unreachable paths, network may be down`

## pseudocode

```c
void __fastcall ProcessUnreachablePathsByFamily<_IPV6_PATH_KEY,_IPV6_PATH_ROD>(
        int a1,
        NCSI_INTERFACE_ATTRIBUTES *a2,
        unsigned int a3,
        Ncsi::Proxy::Info *a4,
        __int64 a5,
        __int64 a6,
        _BYTE *a7)
{
  int v7; // edi
  int v8; // r15d
  unsigned int v9; // esi
  __int64 v10; // r10
  unsigned int v11; // r13d
  __int64 v12; // r9
  unsigned int v13; // r12d
  __int64 v14; // rbx
  int v16; // edx
  __int64 v17; // r15
  __int64 v18; // r13
  __int64 v19; // r12
  char v20; // si
  int v21; // edx
  int v22; // r8d
  bool v23; // al
  __int64 v24; // rbx
  __int64 v25; // rdi
  unsigned __int8 v26; // r8
  unsigned __int8 v27; // r9
  unsigned __int8 v28; // r10
  char v29; // r11
  __int128 v30; // xmm1
  const char *v31; // rcx
  const char *v32; // r9
  const struct _TraceLoggingMetadata_t *v33; // r8
  int v34; // edx
  int v35; // r8d
  bool IsProxyAddress; // al
  __int64 v37; // rbx
  __int64 v38; // rdi
  unsigned __int8 v39; // al
  unsigned __int8 v40; // r9
  unsigned __int8 v41; // r10
  unsigned __int8 v42; // al
  char v43; // r11
  __int128 v44; // xmm1
  const char *v45; // rcx
  _BYTE *v46; // rdi
  int v47; // eax
  int v48; // ecx
  char v49; // [rsp+50h] [rbp-B0h]
  char v50; // [rsp+51h] [rbp-AFh]
  const char *v51; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v52; // [rsp+60h] [rbp-A0h]
  int v53; // [rsp+64h] [rbp-9Ch]
  unsigned int v54; // [rsp+68h] [rbp-98h]
  char v55; // [rsp+6Ch] [rbp-94h] BYREF
  char v56; // [rsp+6Dh] [rbp-93h] BYREF
  int v57; // [rsp+70h] [rbp-90h]
  int v58; // [rsp+74h] [rbp-8Ch]
  unsigned int v59; // [rsp+78h] [rbp-88h] BYREF
  const char *v60; // [rsp+80h] [rbp-80h] BYREF
  __int64 v61; // [rsp+88h] [rbp-78h] BYREF
  const char *v62; // [rsp+90h] [rbp-70h] BYREF
  _BYTE *v63; // [rsp+98h] [rbp-68h]
  __int128 v64; // [rsp+A0h] [rbp-60h] BYREF
  Ncsi::Proxy::Info *v65[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v66; // [rsp+C0h] [rbp-40h] BYREF
  char *v67; // [rsp+D0h] [rbp-30h] BYREF
  int v68; // [rsp+D8h] [rbp-28h]
  int v69; // [rsp+DCh] [rbp-24h]
  char *v70; // [rsp+E0h] [rbp-20h]
  __int64 v71; // [rsp+E8h] [rbp-18h]
  const char *v72; // [rsp+F0h] [rbp-10h]
  __int64 v73; // [rsp+F8h] [rbp-8h]
  const char *v74; // [rsp+100h] [rbp+0h]
  __int64 v75; // [rsp+108h] [rbp+8h]
  Ncsi::Proxy::Info **v76; // [rsp+110h] [rbp+10h]
  __int64 v77; // [rsp+118h] [rbp+18h]
  const char *v78; // [rsp+120h] [rbp+20h]
  __int64 v79; // [rsp+128h] [rbp+28h]
  unsigned int *v80; // [rsp+130h] [rbp+30h]
  __int64 v81; // [rsp+138h] [rbp+38h]
  char *v82; // [rsp+140h] [rbp+40h]
  __int64 v83; // [rsp+148h] [rbp+48h]
  const char **v84; // [rsp+150h] [rbp+50h]
  __int64 v85; // [rsp+158h] [rbp+58h]
  char *v86; // [rsp+160h] [rbp+60h]
  __int64 v87; // [rsp+168h] [rbp+68h]
  Ncsi::Proxy::Info **v88; // [rsp+170h] [rbp+70h]
  __int64 v89; // [rsp+178h] [rbp+78h]

  v9 = 0;
  v10 = qword_18009DD80;
  v11 = 0;
  LOBYTE(v8) = 0;
  v65[0] = a4;
  v12 = qword_18009DD70;
  v13 = 0;
  LOBYTE(v7) = 0;
  v60 = (const char *)qword_18009DD70;
  v14 = 0;
  v52 = a3;
  v16 = *((_DWORD *)a2 + 2092);
  v63 = a7;
  v54 = 0;
  LODWORD(v51) = 0;
  LODWORD(v62) = v8;
  v59 = 0;
  v49 = 0;
  v50 = 0;
  v57 = v7;
  v53 = v16;
  v61 = qword_18009DD80;
  v58 = 0;
  if ( g_nsiPathTablev6 )
  {
    v17 = WPP_GLOBAL_Control;
    while ( 1 )
    {
      a1 = v14;
      v18 = v12 + 48 * v14;
      if ( *(_QWORD *)a2 == *(_QWORD *)(v18 + 8) )
      {
        v19 = v10 + 112LL * (unsigned int)v14;
        if ( !*(_BYTE *)(v19 + 20) || *(_BYTE *)(v19 + 21) )
        {
          if ( *(_DWORD *)(v19 + 16) > a3 )
            goto LABEL_41;
          if ( v16 < 2
            || !PathIsOnlink<_IPV6_PATH_KEY,_IPV6_PATH_ROD>(
                  (unsigned int)v14,
                  (__int64)a2,
                  (_QWORD *)v18,
                  v10 + 112LL * (unsigned int)v14) )
          {
            v54 = ++v9;
          }
          if ( !(unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(a2, 1)
            || (unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot() )
          {
            IsProxyAddress = Ncsi::Proxy::Info::IsProxyAddress(v65[0], (const struct in6_addr *)(v18 + 16));
            v17 = WPP_GLOBAL_Control;
            if ( IsProxyAddress )
              ++v59;
          }
          if ( !v50 )
          {
            v37 = *(_QWORD *)(a6 + 8);
            v38 = *(_QWORD *)(a6 + 16);
            v64 = *(_OWORD *)(v18 + 16);
            if ( v37 != v38 )
            {
              while ( 1 )
              {
                v39 = 0;
                while ( 1 )
                {
                  a1 = v39;
                  v40 = *(_BYTE *)(v37 + v39);
                  v41 = *((_BYTE *)&v65[-2] + v39);
                  if ( v40 != v41 )
                    break;
                  if ( ++v39 == 16 )
                  {
                    v42 = 0x80;
                    goto LABEL_65;
                  }
                }
                v43 = 0;
                a1 = v41;
                LOBYTE(a1) = v40 ^ v41;
                if ( ((v40 ^ v41) & 0x80u) == 0 )
                {
                  do
                  {
                    ++v43;
                    v35 = 1;
                    v34 = v41;
                    LOBYTE(v35) = 1 << (7 - v43);
                    a1 = v40;
                    LOBYTE(a1) = v35 & v40;
                    LOBYTE(v34) = v35 & v41;
                  }
                  while ( ((unsigned __int8)v35 & v40) == ((unsigned __int8)v35 & v41) );
                  v9 = v54;
                }
                v42 = v43 + 8 * v39;
LABEL_65:
                if ( v42 >= *(_BYTE *)(v37 + 16) )
                  break;
                v37 += 18;
                if ( v37 == v38 )
                  goto LABEL_69;
              }
              v50 = 1;
            }
LABEL_69:
            LODWORD(v14) = v58;
            LOBYTE(v7) = v57;
          }
          if ( *(_BYTE *)(v17 + 25) >= 5u )
          {
            v44 = *(_OWORD *)(v18 + 32);
            v64 = *(_OWORD *)(v18 + 16);
            v66 = v44;
            if ( (_UNKNOWN *)v17 != &WPP_GLOBAL_Control && (*(_BYTE *)(v17 + 28) & 2) != 0 )
            {
              v45 = "Can't connect ";
              if ( !*(_BYTE *)(v19 + 21) )
                v45 = "Unreachable";
              WPP_SF_sss_IPV6__IPV6_d(
                *(_QWORD *)(v17 + 16),
                v34,
                v35,
                (unsigned int)"Remote ",
                (__int64)"path",
                (__int64)v45,
                (__int64)&v66,
                (__int64)&v64,
                *(_DWORD *)(v19 + 16));
              v17 = WPP_GLOBAL_Control;
            }
          }
          goto LABEL_40;
        }
        if ( *(_DWORD *)(v19 + 16) <= a3 )
        {
          v20 = PathIsOnlink<_IPV6_PATH_KEY,_IPV6_PATH_ROD>(
                  (unsigned int)v14,
                  (__int64)a2,
                  (_QWORD *)v18,
                  v10 + 112LL * (unsigned int)v14);
          if ( !v20 )
            LODWORD(v51) = (_DWORD)v51 + 1;
          if ( !(unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(a2, 1)
            || (unsigned __int8)NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot() )
          {
            v23 = Ncsi::Proxy::Info::IsProxyAddress(v65[0], (const struct in6_addr *)(v18 + 16));
            v17 = WPP_GLOBAL_Control;
            a1 = (unsigned __int8)v62;
            if ( v23 )
              a1 = 1;
            LODWORD(v62) = a1;
          }
          if ( !v49 )
          {
            v24 = *(_QWORD *)(a6 + 8);
            v25 = *(_QWORD *)(a6 + 16);
            v66 = *(_OWORD *)(v18 + 16);
            if ( v24 != v25 )
            {
              while ( 1 )
              {
                v26 = 0;
                while ( 1 )
                {
                  v27 = *(_BYTE *)(v24 + v26);
                  v28 = *((_BYTE *)&v66 + v26);
                  if ( v27 != v28 )
                    break;
                  if ( ++v26 == 16 )
                  {
                    LOBYTE(v22) = 0x80;
                    goto LABEL_24;
                  }
                }
                v29 = 0;
                if ( ((v27 ^ v28) & 0x80u) == 0 )
                {
                  do
                  {
                    ++v29;
                    v21 = 1;
                    LOBYTE(v21) = 1 << (7 - v29);
                    a1 = v28;
                    LOBYTE(a1) = v21 & v28;
                  }
                  while ( ((unsigned __int8)v21 & v27) == ((unsigned __int8)v21 & v28) );
                  v17 = WPP_GLOBAL_Control;
                }
                LOBYTE(v22) = v29 + 8 * v26;
LABEL_24:
                if ( (unsigned __int8)v22 >= *(_BYTE *)(v24 + 16) )
                  break;
                v24 += 18;
                if ( v24 == v25 )
                  goto LABEL_28;
              }
              v49 = 1;
            }
LABEL_28:
            LODWORD(v14) = v58;
            LOBYTE(v7) = v57;
          }
          if ( !v20 )
          {
            v7 = (unsigned __int8)v7;
            if ( !*((_WORD *)a2 + 4152) )
              v7 = 1;
            v57 = v7;
          }
          if ( *(_BYTE *)(v17 + 25) >= 5u )
          {
            v30 = *(_OWORD *)(v18 + 32);
            v66 = *(_OWORD *)(v18 + 16);
            v64 = v30;
            if ( (_UNKNOWN *)v17 != &WPP_GLOBAL_Control && (*(_BYTE *)(v17 + 28) & 2) != 0 )
            {
              v31 = "Can't connect ";
              if ( !*(_BYTE *)(v19 + 21) )
                v31 = "reachable";
              WPP_SF_sss_IPV6__IPV6_d(
                *(_QWORD *)(v17 + 16),
                v21,
                v22,
                (unsigned int)"Remote ",
                (__int64)"path",
                (__int64)v31,
                (__int64)&v64,
                (__int64)&v66,
                *(_DWORD *)(v19 + 16));
              v17 = WPP_GLOBAL_Control;
            }
          }
          v9 = v54;
LABEL_40:
          v10 = v61;
          v12 = (__int64)v60;
          v16 = v53;
          a3 = v52;
        }
      }
LABEL_41:
      v14 = (unsigned int)(v14 + 1);
      v58 = v14;
      if ( (unsigned int)v14 >= g_nsiPathTablev6 )
      {
        LOBYTE(v8) = (_BYTE)v62;
        v13 = v59;
        v11 = (unsigned int)v51;
        break;
      }
    }
  }
  v32 = "IPv6";
  v33 = &TraceLoggingMetadata;
  if ( (unsigned int)dword_18009A080 > 5 )
  {
    a1 = qword_18009A098;
    if ( (qword_18009A090 & 0x400000000000LL) != 0 && (qword_18009A098 & 0x400000000000LL) == qword_18009A098 )
    {
      v61 = *((unsigned __int16 *)a2 + 3);
      v60 = *(const char **)a2;
      v88 = v65;
      v86 = &v55;
      v84 = &v51;
      v82 = &v56;
      v80 = &v59;
      v78 = (const char *)&v62;
      v76 = (Ncsi::Proxy::Info **)&v61;
      v72 = (const char *)&v60;
      v67 = (char *)off_18009A088;
      v55 = v7;
      v74 = "IPv6";
      *((_QWORD *)&v66 + 1) = 0x400000000000LL;
      v65[0] = (Ncsi::Proxy::Info *)2048;
      LODWORD(v51) = v13;
      v56 = v8;
      v59 = v11;
      LODWORD(v62) = v9;
      v89 = 8;
      v87 = 1;
      v85 = 4;
      v83 = 1;
      v81 = 4;
      v79 = 4;
      v77 = 8;
      v75 = 5;
      v73 = 8;
      *(_QWORD *)&v66 = 0x50B000000LL;
      v68 = *(unsigned __int16 *)off_18009A088;
      v70 = &byte_180088657;
      v69 = 2;
      v71 = 0x1000000B6LL;
      v54 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(qword_18009A0A0, &v66, 0, 0, 11, &v67);
      v33 = &TraceLoggingMetadata;
      v32 = "IPv6";
    }
  }
  if ( (_BYTE)v8 )
  {
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      v65[0] = *(Ncsi::Proxy::Info **)a2;
      v78 = "IPv6";
      v76 = v65;
      v79 = 5;
      v74 = "Successfully reached a proxy";
      v72 = "SetProxiedInternetCapability to true";
      v67 = (char *)off_18009A088;
      v77 = 8;
      v75 = 29;
      v73 = 37;
      v66 = 0x50B000000uLL;
      v68 = *(unsigned __int16 *)off_18009A088;
      v70 = (char *)&unk_1800885A8;
      v69 = 2;
      v71 = 0x100000049LL;
      LODWORD(v51) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(qword_18009A0A0, &v66, 0, 0, 6, &v67);
    }
    LOBYTE(v33) = 1;
    NCSI_INTERFACE_ATTRIBUTES::SetProxiedInternetCapability(a2, 1, v33, 13);
    if ( *((_BYTE *)a2 + 4499) )
    {
      if ( (unsigned int)dword_18009A080 > 5 )
      {
        v65[0] = *(Ncsi::Proxy::Info **)a2;
        v78 = "IPv4";
        v79 = 5;
        v76 = v65;
        v77 = 8;
        v74 = "Active probe over previous family was successful through a proxy";
        v72 = "SetProxiedInternetCapability to true on the other family";
        v67 = (char *)off_18009A088;
        v75 = 65;
        v73 = 57;
        v66 = 0x50B000000uLL;
        v68 = *(unsigned __int16 *)off_18009A088;
        v70 = byte_1800885FD;
        v69 = 2;
        v71 = 0x10000004ELL;
        LODWORD(v51) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(qword_18009A0A0, &v66, 0, 0, 6, &v67);
      }
      LOBYTE(v33) = 1;
      NCSI_INTERFACE_ATTRIBUTES::SetProxiedInternetCapability(a2, 0, v33, 13);
      v46 = v63;
      *v63 = 1;
    }
    else
    {
      v46 = v63;
      *v63 = 1;
    }
    goto LABEL_103;
  }
  if ( v11 )
  {
    v47 = *((_DWORD *)a2 + 2108);
    if ( v47 == 1 || v47 == 4 )
    {
      if ( (unsigned int)dword_18009A080 > 5 )
      {
        v65[0] = *(Ncsi::Proxy::Info **)a2;
        v78 = "IPv6";
        v76 = v65;
        v79 = 5;
        v74 = "Reached an host in a suspect state";
        v72 = "CancelSuspectState";
        v67 = (char *)off_18009A088;
        v77 = 8;
        v75 = 35;
        v73 = 19;
        v66 = 0x50B000000uLL;
        v68 = *(unsigned __int16 *)off_18009A088;
        v70 = (char *)&word_1800884FE;
        v69 = 2;
        v71 = 0x100000049LL;
        LODWORD(v51) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(qword_18009A0A0, &v66, 0, 0, 6, &v67);
      }
      NCSI_INTERFACE_ATTRIBUTES::CancelSuspectState(a2, 1, 4);
      v46 = v63;
      goto LABEL_103;
    }
LABEL_102:
    v46 = v63;
    goto LABEL_103;
  }
  if ( !v13 )
  {
    if ( v9 )
    {
      if ( (unsigned int)dword_18009A080 > 5 )
      {
        v61 = *(_QWORD *)a2;
        v60 = "Found unreachable paths, network may be down";
        v62 = "EnterSuspectState";
        LODWORD(v51) = 0;
        v59 = v9;
        v65[0] = (Ncsi::Proxy::Info *)"IPv6";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          a1,
          (unsigned int)&dword_180088484,
          (unsigned int)&TraceLoggingMetadata,
          (unsigned int)"IPv6",
          (__int64)&v62,
          (__int64)&v60,
          (__int64)&v61,
          (__int64)v65,
          (__int64)&v59,
          (__int64)&v51);
      }
      NCSI_INTERFACE_ATTRIBUTES::EnterSuspectState(a2, 1, 1);
    }
    goto LABEL_102;
  }
  if ( (unsigned int)dword_18009A080 > 5 )
  {
    v65[0] = *(Ncsi::Proxy::Info **)a2;
    v78 = "IPv6";
    v76 = v65;
    v79 = 5;
    v74 = "Unreachable proxies";
    v72 = "EnterSuspectState";
    v67 = (char *)off_18009A088;
    v77 = 8;
    v75 = 20;
    v73 = 18;
    v66 = 0x50B000000uLL;
    v68 = *(unsigned __int16 *)off_18009A088;
    v70 = byte_180088553;
    v69 = 2;
    v71 = 0x100000049LL;
    LODWORD(v51) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(qword_18009A0A0, &v66, 0, 0, 6, &v67);
  }
  NCSI_INTERFACE_ATTRIBUTES::EnterSuspectState(a2, 1, 2);
  if ( *((_BYTE *)a2 + 4499) )
  {
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      v65[0] = (Ncsi::Proxy::Info *)"IPv4";
      v61 = *(_QWORD *)a2;
      v60 = "Previous active probe was successful through a proxy but now fails";
      v51 = "EnterSuspectState on other family";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        a1,
        (unsigned int)&byte_18008842F,
        (_DWORD)v33,
        (_DWORD)v32,
        (__int64)&v51,
        (__int64)&v60,
        (__int64)&v61,
        (__int64)v65);
    }
    NCSI_INTERFACE_ATTRIBUTES::EnterSuspectState(a2, 0, 2);
  }
  v46 = v63;
LABEL_103:
  if ( v49 )
  {
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      v65[0] = *(Ncsi::Proxy::Info **)a2;
      v77 = 8;
      v76 = v65;
      v75 = 71;
      v74 = "Reached a host with a corporate prefix, assuming has corp connectivity";
      v73 = 30;
      v72 = "SetCorporateConnectivity true";
      v67 = (char *)off_18009A088;
      v66 = 0x50B000000uLL;
      v68 = *(unsigned __int16 *)off_18009A088;
      v70 = (char *)&unk_1800883A0;
      v69 = 2;
      v71 = 0x100000041LL;
      LODWORD(v51) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(qword_18009A0A0, &v66, 0, 0, 5, &v67);
    }
    if ( *((_BYTE *)a2 + 11660) != 1 )
    {
      if ( (Microsoft_Windows_NCSIEnableBits & 4) != 0 )
      {
        LOBYTE(v32) = 6;
        McTemplateU0jux_EtwEventWriteTransfer(
          a1,
          (unsigned int)StopWaitForCorporate,
          (_DWORD)a2 + 8,
          (_DWORD)v32,
          *(_QWORD *)a2);
      }
      *((_BYTE *)a2 + 11660) = 1;
      if ( (Microsoft_Windows_NCSIEnableBits & 0x1000) != 0 )
        McTemplateU0jxqq_EtwEventWriteTransfer(
          a1,
          (unsigned int)CorporateConnectivityChanged,
          (_DWORD)a2 + 8,
          *(_QWORD *)a2,
          1,
          1);
    }
    if ( *((_DWORD *)a2 + 2914) )
    {
      *((_DWORD *)a2 + 2914) = 0;
      v48 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
      {
        WPP_SF_i(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          26,
          WPP_d2174b9e5b313c7131b16cc52be830be_Traceguids,
          *(_QWORD *)a2);
      }
      if ( (Microsoft_Windows_NCSIEnableBits & 4) != 0 )
      {
        v65[0] = *(Ncsi::Proxy::Info **)a2;
        v71 = 16;
        v70 = (char *)a2 + 8;
        v72 = (const char *)v65;
        v73 = 8;
        McGenEventWrite_EtwEventWriteTransfer(
          v48,
          (unsigned int)EndCorporateSuspectStateEvent,
          (_DWORD)v33,
          3,
          (__int64)&v67);
      }
    }
    *v46 = 1;
  }
  else if ( v50 )
  {
    if ( (unsigned int)dword_18009A080 > 5 )
    {
      v65[0] = *(Ncsi::Proxy::Info **)a2;
      v77 = 8;
      v76 = v65;
      v75 = 59;
      v74 = "Corp sites were unreachable, corp connectivity may be down";
      v73 = 27;
      v72 = "EnterSuspectCorporateState";
      v67 = (char *)off_18009A088;
      v66 = 0x50B000000uLL;
      v68 = *(unsigned __int16 *)off_18009A088;
      v70 = byte_1800883ED;
      v69 = 2;
      v71 = 0x100000041LL;
      LODWORD(v51) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwEventWriteTransfer(qword_18009A0A0, &v66, 0, 0, 5, &v67);
    }
    NCSI_INTERFACE_ATTRIBUTES::EnterSuspectCorporateState(a2);
  }
}

```

## disassembly

```asm
0x180033010  mov     [rsp-8+arg_0], rbx
0x180033015  push    rbp
0x180033016  push    rsi
0x180033017  push    rdi
0x180033018  push    r12
0x18003301a  push    r13
0x18003301c  push    r14
0x18003301e  push    r15
0x180033020  lea     rbp, [rsp-90h]
0x180033028  sub     rsp, 190h
0x18003302f  mov     rax, cs:__security_cookie
0x180033036  xor     rax, rsp
0x180033039  mov     [rbp+0C0h+var_40], rax
0x180033040  mov     rax, [rbp+0C0h+arg_30]
0x180033047  xor     esi, esi
0x180033049  mov     r10, cs:qword_18009DD80
0x180033050  xor     r13d, r13d
0x180033053  xor     r15b, r15b
0x180033056  mov     [rbp+0C0h+var_110], r9
0x18003305a  mov     r9, cs:qword_18009DD70
0x180033061  xor     r12d, r12d
0x180033064  xor     dil, dil
0x180033067  mov     [rbp+0C0h+var_140], r9
0x18003306b  xor     ebx, ebx
0x18003306d  mov     [rsp+1C0h+var_160], r8d
0x180033072  cmp     cs:?g_nsiPathTablev6@@3V?$TNcsiNsiTable@U_IPV6_PATH_KEY@@U_IPV6_PATH_ROD@@@@A, ebx; TNcsiNsiTable<_IPV6_PATH_KEY,_IPV6_PATH_ROD> g_nsiPathTablev6
0x180033078  mov     r14, rdx
0x18003307b  mov     edx, [rdx+20B0h]
0x180033081  mov     [rbp+0C0h+var_128], rax
0x180033085  mov     [rsp+1C0h+var_158], esi
0x180033089  mov     dword ptr [rsp+1C0h+var_168], r13d
0x18003308e  mov     dword ptr [rbp+0C0h+var_130], r15d
0x180033092  mov     [rsp+1C0h+var_148], r12d
0x180033097  mov     [rsp+1C0h+var_170], sil
0x18003309c  mov     [rsp+1C0h+var_16F], sil
0x1800330a1  mov     [rsp+1C0h+var_150], edi
0x1800330a5  mov     [rsp+1C0h+var_15C], edx
0x1800330a9  mov     [rbp+0C0h+var_138], r10
0x1800330ad  mov     [rsp+1C0h+var_14C], ebx
0x1800330b1  jbe     loc_180033314
0x1800330b7  mov     r15, cs:WPP_GLOBAL_Control
0x1800330be  xchg    ax, ax
0x1800330c0  lea     r13, [rbx+rbx*2]
0x1800330c4  mov     ecx, ebx
0x1800330c6  shl     r13, 4
0x1800330ca  add     r13, r9
0x1800330cd  mov     rax, [r13+8]
0x1800330d1  cmp     [r14], rax
0x1800330d4  jnz     loc_1800332F4
0x1800330da  imul    r12, rcx, 70h ; 'p'
0x1800330de  add     r12, r10
0x1800330e1  cmp     byte ptr [r12+14h], 0
0x1800330e7  jz      loc_1800334AF
0x1800330ed  cmp     byte ptr [r12+15h], 0
0x1800330f3  jnz     loc_1800334AF
0x1800330f9  cmp     [r12+10h], r8d
0x1800330fe  ja      loc_1800332F4
0x180033104  mov     r9, r12
0x180033107  mov     r8, r13
0x18003310a  mov     rdx, r14
0x18003310d  call    ??$PathIsOnlink@U_IPV6_PATH_KEY@@U_IPV6_PATH_ROD@@@@YA_NW4_NLA_CONNECTIVITY_FAMILY@@PEAVNCSI_INTERFACE_ATTRIBUTES@@PEAU_IPV6_PATH_KEY@@PEAU_IPV6_PATH_ROD@@@Z; PathIsOnlink<_IPV6_PATH_KEY,_IPV6_PATH_ROD>(_NLA_CONNECTIVITY_FAMILY,NCSI_INTERFACE_ATTRIBUTES *,_IPV6_PATH_KEY *,_IPV6_PATH_ROD *)
0x180033112  movzx   esi, al
0x180033115  test    al, al
0x180033117  jnz     short loc_18003311D
0x180033119  inc     dword ptr [rsp+1C0h+var_168]
0x18003311d  mov     edx, 1
0x180033122  mov     rcx, r14
0x180033125  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x18003312a  test    al, al
0x18003312c  jz      short loc_180033137
0x18003312e  call    ?HasInternetBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x180033133  test    al, al
0x180033135  jz      short loc_180033162
0x180033137  mov     rcx, [rbp+0C0h+var_110]; this
0x18003313b  lea     rdx, [r13+10h]; struct in6_addr *
0x18003313f  call    ?IsProxyAddress@Info@Proxy@Ncsi@@QEBA_NAEBUin6_addr@@@Z; Ncsi::Proxy::Info::IsProxyAddress(in6_addr const &)
0x180033144  mov     ecx, dword ptr [rbp+0C0h+var_130]
0x180033147  test    al, al
0x180033149  mov     r15, cs:WPP_GLOBAL_Control
0x180033150  mov     r11d, 1
0x180033156  movzx   ecx, cl
0x180033159  cmovnz  ecx, r11d
0x18003315d  mov     dword ptr [rbp+0C0h+var_130], ecx
0x180033160  jmp     short loc_180033168
0x180033162  mov     r11d, 1
0x180033168  cmp     [rsp+1C0h+var_170], 0
0x18003316d  jnz     loc_180033239
0x180033173  mov     rax, [rbp+0C0h+arg_28]
0x18003317a  movups  xmm0, xmmword ptr [r13+10h]
0x18003317f  mov     rbx, [rax+8]
0x180033183  mov     rdi, [rax+10h]
0x180033187  movaps  [rbp+0C0h+var_100], xmm0
0x18003318b  cmp     rbx, rdi
0x18003318e  jz      loc_180033231
0x180033194  xor     r8b, r8b
0x180033197  nop     word ptr [rax+rax+00000000h]
0x1800331a0  movzx   eax, r8b
0x1800331a4  movzx   r9d, byte ptr [rbx+rax]
0x1800331a9  movzx   r10d, byte ptr [rbp+rax+0C0h+var_100]
0x1800331af  cmp     r9b, r10b
0x1800331b2  jnz     short loc_1800331C2
0x1800331b4  inc     r8b
0x1800331b7  cmp     r8b, 10h
0x1800331bb  jnz     short loc_1800331A0
0x1800331bd  mov     r8b, 80h
0x1800331c0  jmp     short loc_180033211
0x1800331c2  xor     r11b, r11b
0x1800331c5  movzx   eax, r10b
0x1800331c9  xor     al, r9b
0x1800331cc  js      short loc_18003320A
0x1800331ce  mov     r15d, 1
0x1800331d4  nop     dword ptr [rax+00h]
0x1800331d8  nop     dword ptr [rax+rax+00000000h]
0x1800331e0  inc     r11b
0x1800331e3  mov     ecx, 7
0x1800331e8  movzx   eax, r11b
0x1800331ec  mov     edx, r15d
0x1800331ef  sub     ecx, eax
0x1800331f1  movzx   eax, r9b
0x1800331f5  shl     dl, cl
0x1800331f7  movzx   ecx, r10b
0x1800331fb  and     cl, dl
0x1800331fd  and     al, dl
0x1800331ff  cmp     al, cl
0x180033201  jz      short loc_1800331E0
0x180033203  mov     r15, cs:WPP_GLOBAL_Control
0x18003320a  shl     r8b, 3
0x18003320e  add     r8b, r11b
0x180033211  cmp     r8b, [rbx+10h]
0x180033215  jnb     short loc_180033226
0x180033217  add     rbx, 12h
0x18003321b  cmp     rbx, rdi
0x18003321e  jnz     loc_180033194
0x180033224  jmp     short loc_18003322B
0x180033226  mov     [rsp+1C0h+var_170], 1
0x18003322b  mov     r11d, 1
0x180033231  mov     ebx, [rsp+1C0h+var_14C]
0x180033235  mov     edi, [rsp+1C0h+var_150]
0x180033239  test    sil, sil
0x18003323c  jnz     short loc_180033254
0x18003323e  xor     eax, eax
0x180033240  movzx   edi, dil
0x180033244  cmp     ax, [r14+2070h]
0x18003324c  cmovz   edi, r11d
0x180033250  mov     [rsp+1C0h+var_150], edi
0x180033254  cmp     byte ptr [r15+19h], 5
0x180033259  jb      loc_1800332DF
0x18003325f  movups  xmm0, xmmword ptr [r13+10h]
0x180033264  movups  xmm1, xmmword ptr [r13+20h]
0x180033269  movaps  [rbp+0C0h+var_100], xmm0
0x18003326d  movaps  [rbp+0C0h+var_120], xmm1
0x180033271  lea     rax, WPP_GLOBAL_Control
0x180033278  cmp     r15, rax
0x18003327b  jz      short loc_1800332DF
0x18003327d  test    byte ptr [r15+1Ch], 2
0x180033282  jz      short loc_1800332DF
0x180033284  cmp     byte ptr [r12+15h], 0
0x18003328a  lea     rax, aReachable; "reachable"
0x180033291  lea     rcx, aCanTConnect; "Can't connect "
0x180033298  cmovz   rcx, rax
0x18003329c  lea     r9, aRemote; "Remote "
0x1800332a3  mov     eax, [r12+10h]
0x1800332a8  mov     dword ptr [rsp+1C0h+var_180], eax
0x1800332ac  lea     rax, [rbp+0C0h+var_100]
0x1800332b0  mov     [rsp+1C0h+var_188], rax
0x1800332b5  lea     rax, [rbp+0C0h+var_120]
0x1800332b9  mov     [rsp+1C0h+var_190], rax
0x1800332be  lea     rax, aPath; "path"
0x1800332c5  mov     [rsp+1C0h+var_198], rcx
0x1800332ca  mov     rcx, [r15+10h]
0x1800332ce  mov     [rsp+1C0h+var_1A0], rax
0x1800332d3  call    WPP_SF_sss_IPV6__IPV6_d
0x1800332d8  mov     r15, cs:WPP_GLOBAL_Control
0x1800332df  mov     esi, [rsp+1C0h+var_158]
0x1800332e3  mov     r10, [rbp+0C0h+var_138]
0x1800332e7  mov     r9, [rbp+0C0h+var_140]
0x1800332eb  mov     edx, [rsp+1C0h+var_15C]
0x1800332ef  mov     r8d, [rsp+1C0h+var_160]
0x1800332f4  inc     ebx
0x1800332f6  cmp     ebx, cs:?g_nsiPathTablev6@@3V?$TNcsiNsiTable@U_IPV6_PATH_KEY@@U_IPV6_PATH_ROD@@@@A; TNcsiNsiTable<_IPV6_PATH_KEY,_IPV6_PATH_ROD> g_nsiPathTablev6
0x1800332fc  mov     [rsp+1C0h+var_14C], ebx
0x180033300  jb      loc_1800330C0
0x180033306  mov     r15d, dword ptr [rbp+0C0h+var_130]
0x18003330a  mov     r12d, [rsp+1C0h+var_148]
0x18003330f  mov     r13d, dword ptr [rsp+1C0h+var_168]
0x180033314  mov     eax, cs:dword_18009A080
0x18003331a  lea     r9, aIpv6; "IPv6"
0x180033321  lea     rbx, _TraceLoggingMetadataEnd
0x180033328  lea     r8, _TraceLoggingMetadata
0x18003332f  cmp     eax, 5
0x180033332  jbe     loc_180033658
0x180033338  mov     rcx, cs:qword_18009A098
0x18003333f  mov     rdx, 400000000000h
0x180033349  mov     rax, cs:qword_18009A090
0x180033350  test    rdx, rax
0x180033353  jz      loc_180033658
0x180033359  mov     rax, rcx
0x18003335c  and     rax, rdx
0x18003335f  cmp     rax, rcx
0x180033362  jnz     loc_180033658
0x180033368  movzx   eax, word ptr [r14+6]
0x18003336d  mov     [rbp+0C0h+var_138], rax
0x180033371  mov     rax, [r14]
0x180033374  mov     [rbp+0C0h+var_140], rax
0x180033378  lea     rax, [rbp+0C0h+var_110]
0x18003337c  mov     [rbp+0C0h+var_50], rax
0x180033380  lea     rax, [rsp+1C0h+var_154]
0x180033385  mov     [rbp+0C0h+var_60], rax
0x180033389  lea     rax, [rsp+1C0h+var_168]
0x18003338e  mov     [rbp+0C0h+var_70], rax
0x180033392  lea     rax, [rsp+1C0h+var_153]
0x180033397  mov     [rbp+0C0h+var_80], rax
0x18003339b  lea     rax, [rsp+1C0h+var_148]
0x1800333a0  mov     [rbp+0C0h+var_90], rax
0x1800333a4  lea     rax, [rbp+0C0h+var_130]
0x1800333a8  mov     [rbp+0C0h+var_A0], rax
0x1800333ac  lea     rax, [rbp+0C0h+var_138]
0x1800333b0  mov     [rbp+0C0h+var_B0], rax
0x1800333b4  lea     rax, [rbp+0C0h+var_140]
0x1800333b8  mov     [rbp+0C0h+var_D0], rax
0x1800333bc  movzx   eax, cs:word_18008864D
0x1800333c3  mov     dword ptr [rbp+0C0h+var_100+4], eax
0x1800333c6  mov     rax, cs:off_18009A088
0x1800333cd  mov     [rbp+0C0h+var_F0], rax
0x1800333d1  mov     [rsp+1C0h+var_154], dil
0x1800333d6  mov     edi, 1
0x1800333db  mov     [rbp+0C0h+var_C0], r9
0x1800333df  xor     r9d, r9d
0x1800333e2  mov     qword ptr [rbp+0C0h+var_100+8], rdx
0x1800333e6  lea     rdx, [rbp+0C0h+var_100]
0x1800333ea  mov     [rbp+0C0h+var_110], 800h
0x1800333f2  mov     dword ptr [rsp+1C0h+var_168], r12d
0x1800333f7  mov     [rsp+1C0h+var_153], r15b
0x1800333fc  mov     [rsp+1C0h+var_148], r13d
0x180033401  mov     dword ptr [rbp+0C0h+var_130], esi
0x180033404  mov     [rbp+0C0h+var_48], 8
0x18003340c  mov     [rbp+0C0h+var_58], rdi
0x180033410  mov     [rbp+0C0h+var_68], 4
0x180033418  mov     [rbp+0C0h+var_78], rdi
0x18003341c  mov     [rbp+0C0h+var_88], 4
0x180033424  mov     [rbp+0C0h+var_98], 4
0x18003342c  mov     [rbp+0C0h+var_A8], 8
0x180033434  mov     [rbp+0C0h+var_B8], 5
0x18003343c  mov     [rbp+0C0h+var_C8], 8
0x180033444  mov     dword ptr [rbp+0C0h+var_100], 0B000000h
0x18003344b  movzx   eax, word ptr [rax]
0x18003344e  mov     [rbp+0C0h+var_E8], eax
0x180033451  lea     rax, byte_180088657
0x180033458  mov     [rbp+0C0h+var_E0], rax
0x18003345c  mov     rax, rbx
0x18003345f  sub     eax, r8d
0x180033462  mov     [rbp+0C0h+var_E4], 2
0x180033469  mov     dword ptr [rbp+0C0h+var_D8], 0B6h
0x180033470  xor     r8d, r8d
0x180033473  mov     dword ptr [rbp+0C0h+var_D8+4], edi
0x180033476  mov     [rsp+1C0h+var_158], eax
0x18003347a  mov     eax, [rsp+1C0h+var_158]
0x18003347e  mov     rcx, cs:qword_18009A0A0
0x180033485  lea     rax, [rbp+0C0h+var_F0]
0x180033489  mov     [rsp+1C0h+var_198], rax
0x18003348e  mov     dword ptr [rsp+1C0h+var_1A0], 0Bh
0x180033496  call    cs:__imp_EtwEventWriteTransfer
0x18003349c  lea     r8, _TraceLoggingMetadata
0x1800334a3  lea     r9, aIpv6; "IPv6"
0x1800334aa  jmp     loc_18003365D
0x1800334af  cmp     [r12+10h], r8d
0x1800334b4  ja      loc_1800332F4
0x1800334ba  cmp     edx, 2
0x1800334bd  jl      short loc_1800334D1
0x1800334bf  mov     r9, r12
0x1800334c2  mov     r8, r13
0x1800334c5  mov     rdx, r14
0x1800334c8  call    ??$PathIsOnlink@U_IPV6_PATH_KEY@@U_IPV6_PATH_ROD@@@@YA_NW4_NLA_CONNECTIVITY_FAMILY@@PEAVNCSI_INTERFACE_ATTRIBUTES@@PEAU_IPV6_PATH_KEY@@PEAU_IPV6_PATH_ROD@@@Z; PathIsOnlink<_IPV6_PATH_KEY,_IPV6_PATH_ROD>(_NLA_CONNECTIVITY_FAMILY,NCSI_INTERFACE_ATTRIBUTES *,_IPV6_PATH_KEY *,_IPV6_PATH_ROD *)
0x1800334cd  test    al, al
0x1800334cf  jnz     short loc_1800334D7
0x1800334d1  inc     esi
0x1800334d3  mov     [rsp+1C0h+var_158], esi
0x1800334d7  mov     edx, 1
0x1800334dc  mov     rcx, r14
0x1800334df  call    ?IsBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::IsBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x1800334e4  test    al, al
0x1800334e6  jz      short loc_1800334F1
0x1800334e8  call    ?HasInternetBehindHotspot@NCSI_INTERFACE_ATTRIBUTES@@QEBA_NW4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::HasInternetBehindHotspot(_NLA_CONNECTIVITY_FAMILY)
0x1800334ed  test    al, al
0x1800334ef  jz      short loc_18003350D
0x1800334f1  mov     rcx, [rbp+0C0h+var_110]; this
0x1800334f5  lea     rdx, [r13+10h]; struct in6_addr *
0x1800334f9  call    ?IsProxyAddress@Info@Proxy@Ncsi@@QEBA_NAEBUin6_addr@@@Z; Ncsi::Proxy::Info::IsProxyAddress(in6_addr const &)
0x1800334fe  mov     r15, cs:WPP_GLOBAL_Control
0x180033505  test    al, al
0x180033507  jz      short loc_18003350D
0x180033509  inc     [rsp+1C0h+var_148]
0x18003350d  cmp     [rsp+1C0h+var_16F], 0
0x180033512  jnz     loc_1800335C0
0x180033518  mov     rax, [rbp+0C0h+arg_28]
0x18003351f  movups  xmm0, xmmword ptr [r13+10h]
0x180033524  mov     rbx, [rax+8]
0x180033528  mov     rdi, [rax+10h]
0x18003352c  movaps  [rbp+0C0h+var_120], xmm0
0x180033530  cmp     rbx, rdi
  ... truncated ...
```
