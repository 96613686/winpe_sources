# ToString(ulong const &,TUNNEL_TYPE const &)

- ea: `0x18003a79c`
- end: `0x18003b3ef`
- name: `?ToString@@YAPEB_WAEBKAEBW4TUNNEL_TYPE@@@Z`
- size: `3155`
- prototype: `const wchar_t *__fastcall(const unsigned int *, const enum TUNNEL_TYPE *)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180038b08`
- `0x180039b84`
- `0x18003e3bc`

## callees

- `0x18003a79c`

## string_xrefs

- `0x18003a88b`: `IF_TYPE_ISO88024_TOKENBUS`
- `0x18003a883`: `IF_TYPE_ISO88025_TOKENRING`
- `0x18003aa45`: `IF_TYPE_FRAMERELAY_SERVICE`
- `0x18003aa92`: `IF_TYPE_SONET_PATH`
- `0x18003ae34`: `IF_TYPE_PPPMULTILINKBUNDLE`
- `0x18003afb1`: `IF_TYPE_DOCSCABLE_MACLAYER`
- `0x18003b0a9`: `IF_TYPE_DVBRCC_MACLAYER`
- `0x18003b11e`: `IF_TYPE_COMPOSITELINK`
- `0x18003b116`: `IF_TYPE_SS7_SIGLINK`
- `0x18003b1cf`: `IF_TYPE_MF_SIGLINK`
- `0x18003b296`: `IF_TYPE_PROP_DOCS_WIRELESS_MACLAYER`

## pseudocode

```c
const wchar_t *__fastcall ToString(unsigned int *a1, const enum TUNNEL_TYPE *a2)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // eax
  unsigned int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  unsigned int v54; // eax
  unsigned int v55; // eax
  unsigned int v56; // eax
  unsigned int v57; // eax
  unsigned int v58; // eax
  unsigned int v59; // eax
  unsigned int v60; // eax
  unsigned int v61; // eax
  unsigned int v62; // eax
  unsigned int v63; // eax
  unsigned int v64; // eax
  unsigned int v65; // eax
  unsigned int v66; // eax
  unsigned int v67; // eax
  unsigned int v68; // eax
  unsigned int v69; // eax
  unsigned int v70; // eax
  unsigned int v71; // eax
  unsigned int v72; // eax
  unsigned int v73; // eax
  unsigned int v74; // eax
  unsigned int v75; // eax
  unsigned int v76; // eax
  unsigned int v77; // eax
  unsigned int v78; // eax
  unsigned int v79; // eax
  unsigned int v80; // eax
  unsigned int v81; // eax
  unsigned int v82; // eax
  unsigned int v83; // eax
  unsigned int v84; // eax
  unsigned int v85; // eax
  unsigned int v86; // eax
  unsigned int v87; // eax
  unsigned int v88; // eax
  unsigned int v89; // eax
  unsigned int v90; // eax
  unsigned int v91; // eax
  unsigned int v92; // eax
  unsigned int v93; // eax
  unsigned int v94; // eax
  unsigned int v95; // eax
  unsigned int v96; // eax
  unsigned int v97; // eax
  unsigned int v98; // eax
  unsigned int v99; // eax
  unsigned int v100; // eax
  unsigned int v101; // eax
  unsigned int v102; // eax
  unsigned int v103; // eax
  unsigned int v104; // eax
  unsigned int v105; // eax
  unsigned int v106; // eax
  unsigned int v107; // eax
  unsigned int v108; // eax
  unsigned int v109; // eax
  unsigned int v110; // eax
  unsigned int v111; // eax
  unsigned int v112; // eax
  unsigned int v113; // eax
  unsigned int v114; // eax
  unsigned int v115; // eax
  unsigned int v116; // eax
  unsigned int v117; // eax
  unsigned int v118; // eax
  unsigned int v119; // eax
  unsigned int v120; // eax
  unsigned int v121; // eax
  unsigned int v122; // eax
  unsigned int v123; // eax
  unsigned int v124; // eax
  unsigned int v125; // eax
  unsigned int v126; // eax
  unsigned int v127; // eax
  unsigned int v128; // eax
  unsigned int v129; // eax
  unsigned int v130; // eax
  unsigned int v131; // eax
  unsigned int v132; // eax
  unsigned int v133; // eax
  unsigned int v134; // eax
  unsigned int v135; // eax
  unsigned int v136; // eax
  unsigned int v137; // eax
  const wchar_t *v138; // rcx
  const wchar_t *v139; // rdx

  v2 = *a1;
  if ( *a1 > 0x103 )
  {
    v139 = L"XBOX Wireless";
    if ( v2 != 281 )
      return L"(unknown IFTYPE)";
    return v139;
  }
  else
  {
    if ( v2 == 259 )
      return L"IF_TYPE_IEEE802154";
    if ( v2 <= 0x64 )
    {
      if ( v2 == 100 )
        return L"IF_TYPE_VOICE_EM";
      if ( v2 > 0x32 )
      {
        if ( v2 > 0x4B )
        {
          if ( v2 > 0x58 )
          {
            if ( v2 > 0x5E )
            {
              v68 = v2 - 95;
              if ( !v68 )
                return L"IF_TYPE_RADSL";
              v69 = v68 - 1;
              if ( !v69 )
                return L"IF_TYPE_SDSL";
              v70 = v69 - 1;
              if ( !v70 )
                return L"IF_TYPE_VDSL";
              v71 = v70 - 1;
              if ( !v71 )
                return L"IF_TYPE_ISO88025_CRFPRINT";
              if ( v71 == 1 )
                return L"IF_TYPE_MYRINET";
            }
            else
            {
              if ( v2 == 94 )
                return L"IF_TYPE_ADSL";
              v64 = v2 - 89;
              if ( !v64 )
                return L"IF_TYPE_PROP_CNLS";
              v65 = v64 - 1;
              if ( !v65 )
                return L"IF_TYPE_HOSTPAD";
              v66 = v65 - 1;
              if ( !v66 )
                return L"IF_TYPE_TERMPAD";
              v67 = v66 - 1;
              if ( !v67 )
                return L"IF_TYPE_FRAMERELAY_MPI";
              if ( v67 == 1 )
                return L"IF_TYPE_X213";
            }
          }
          else
          {
            if ( v2 == 88 )
              return L"IF_TYPE_ARAP";
            if ( v2 > 0x52 )
            {
              v60 = v2 - 83;
              if ( !v60 )
                return L"IF_TYPE_BSC";
              v61 = v60 - 1;
              if ( !v61 )
                return L"IF_TYPE_ASYNC";
              v62 = v61 - 1;
              if ( !v62 )
                return L"IF_TYPE_CNR";
              v63 = v62 - 1;
              if ( !v63 )
                return L"IF_TYPE_ISO88025R_DTR";
              if ( v63 == 1 )
                return L"IF_TYPE_EPLRS";
            }
            else
            {
              if ( v2 == 82 )
                return L"IF_TYPE_DS0_BUNDLE";
              v55 = v2 - 76;
              if ( !v55 )
                return L"IF_TYPE_ISDN_U";
              v56 = v55 - 1;
              if ( !v56 )
                return L"IF_TYPE_LAP_D";
              v57 = v56 - 1;
              if ( !v57 )
                return L"IF_TYPE_IPSWITCH";
              v58 = v57 - 1;
              if ( !v58 )
                return L"IF_TYPE_RSRB";
              v59 = v58 - 1;
              if ( !v59 )
                return L"IF_TYPE_ATM_LOGICAL";
              if ( v59 == 1 )
                return L"IF_TYPE_DS0";
            }
          }
        }
        else
        {
          if ( v2 == 75 )
            return L"IF_TYPE_ISDN_S";
          if ( v2 > 0x3F )
          {
            if ( v2 > 0x45 )
            {
              v51 = v2 - 70;
              if ( !v51 )
                return L"IF_TYPE_CHANNEL";
              v52 = v51 - 1;
              if ( !v52 )
                return L"Wi-Fi (IEEE80211)";
              v53 = v52 - 1;
              if ( !v53 )
                return L"IF_TYPE_IBM370PARCHAN";
              v54 = v53 - 1;
              if ( !v54 )
                return L"IF_TYPE_ESCON";
              if ( v54 == 1 )
                return L"IF_TYPE_DLSW";
            }
            else
            {
              if ( v2 == 69 )
                return L"IF_TYPE_FASTETHER_FX";
              v47 = v2 - 64;
              if ( !v47 )
                return L"IF_TYPE_V11";
              v48 = v47 - 1;
              if ( !v48 )
                return L"IF_TYPE_V36";
              v49 = v48 - 1;
              if ( !v49 )
                return L"IF_TYPE_G703_64K";
              v50 = v49 - 1;
              if ( !v50 )
                return L"IF_TYPE_G703_2MB";
              if ( v50 == 1 )
                return L"IF_TYPE_QLLC";
            }
          }
          else
          {
            if ( v2 == 63 )
              return L"IF_TYPE_ISDN";
            if ( v2 > 0x39 )
            {
              v43 = v2 - 58;
              if ( !v43 )
                return L"IF_TYPE_FRAMERELAY_INTERCONNECT";
              v44 = v43 - 1;
              if ( !v44 )
                return L"IF_TYPE_AFLANE_8023";
              v45 = v44 - 1;
              if ( !v45 )
                return L"IF_TYPE_AFLANE_8025";
              v46 = v45 - 1;
              if ( !v46 )
                return L"IF_TYPE_CCTEMUL";
              if ( v46 == 1 )
                return L"IF_TYPE_FASTETHER";
            }
            else
            {
              if ( v2 == 57 )
                return L"IF_TYPE_HIPPIINTERFACE";
              v38 = v2 - 51;
              if ( !v38 )
                return L"IF_TYPE_SONET_VT";
              v39 = v38 - 1;
              if ( !v39 )
                return L"IF_TYPE_SMDS_ICIP";
              v40 = v39 - 1;
              if ( !v40 )
                return L"IF_TYPE_PROP_VIRTUAL";
              v41 = v40 - 1;
              if ( !v41 )
                return L"IF_TYPE_PROP_MULTIPLEXOR";
              v42 = v41 - 1;
              if ( !v42 )
                return L"IF_TYPE_IEEE80212";
              if ( v42 == 1 )
                return L"IF_TYPE_FIBRECHANNEL";
            }
          }
        }
      }
      else
      {
        if ( v2 == 50 )
          return L"IF_TYPE_SONET_PATH";
        if ( v2 > 0x19 )
        {
          if ( v2 > 0x26 )
          {
            if ( v2 > 0x2C )
            {
              v34 = v2 - 45;
              if ( !v34 )
                return L"IF_TYPE_V35";
              v35 = v34 - 1;
              if ( !v35 )
                return L"IF_TYPE_HSSI";
              v36 = v35 - 1;
              if ( !v36 )
                return L"IF_TYPE_HIPPI";
              v37 = v36 - 1;
              if ( !v37 )
                return L"IF_TYPE_MODEM";
              if ( v37 == 1 )
                return L"IF_TYPE_AAL5";
            }
            else
            {
              if ( v2 == 44 )
                return L"IF_TYPE_FRAMERELAY_SERVICE";
              v30 = v2 - 39;
              if ( !v30 )
                return L"IF_TYPE_SONET";
              v31 = v30 - 1;
              if ( !v31 )
                return L"IF_TYPE_X25_PLE";
              v32 = v31 - 1;
              if ( !v32 )
                return L"IF_TYPE_ISO88022_LLC";
              v33 = v32 - 1;
              if ( !v33 )
                return L"IF_TYPE_LOCALTALK";
              if ( v33 == 1 )
                return L"IF_TYPE_SMDS_DXI";
            }
          }
          else
          {
            if ( v2 == 38 )
              return L"IF_TYPE_MIO_X25";
            if ( v2 > 0x20 )
            {
              v26 = v2 - 33;
              if ( !v26 )
                return L"IF_TYPE_RS232";
              v27 = v26 - 1;
              if ( !v27 )
                return L"IF_TYPE_PARA";
              v28 = v27 - 1;
              if ( !v28 )
                return L"IF_TYPE_ARCNET";
              v29 = v28 - 1;
              if ( !v29 )
                return L"IF_TYPE_ARCNET_PLUS";
              if ( v29 == 1 )
                return L"IF_TYPE_ATM";
            }
            else
            {
              if ( v2 == 32 )
                return L"IF_TYPE_FRAMERELAY";
              v21 = v2 - 26;
              if ( !v21 )
                return L"IF_TYPE_ETHERNET_3MBIT";
              v22 = v21 - 1;
              if ( !v22 )
                return L"IF_TYPE_NSIP";
              v23 = v22 - 1;
              if ( !v23 )
                return L"IF_TYPE_SLIP";
              v24 = v23 - 1;
              if ( !v24 )
                return L"IF_TYPE_ULTRA";
              v25 = v24 - 1;
              if ( !v25 )
                return L"IF_TYPE_DS3";
              if ( v25 == 1 )
                return L"IF_TYPE_SIP";
            }
          }
        }
        else
        {
          if ( v2 == 25 )
            return L"IF_TYPE_EON";
          if ( v2 > 0xD )
          {
            if ( v2 > 0x13 )
            {
              v17 = v2 - 20;
              if ( !v17 )
                return L"IF_TYPE_BASIC_ISDN";
              v18 = v17 - 1;
              if ( !v18 )
                return L"IF_TYPE_PRIMARY_ISDN";
              v19 = v18 - 1;
              if ( !v19 )
                return L"IF_TYPE_PROP_POINT2POINT_SERIAL";
              v20 = v19 - 1;
              if ( !v20 )
                return L"IF_TYPE_PPP";
              if ( v20 == 1 )
                return L"IF_TYPE_SOFTWARE_LOOPBACK";
            }
            else
            {
              if ( v2 == 19 )
                return L"IF_TYPE_E1";
              v13 = v2 - 14;
              if ( !v13 )
                return L"IF_TYPE_HYPERCHANNEL";
              v14 = v13 - 1;
              if ( !v14 )
                return L"IF_TYPE_FDDI";
              v15 = v14 - 1;
              if ( !v15 )
                return L"IF_TYPE_LAP_B";
              v16 = v15 - 1;
              if ( !v16 )
                return L"IF_TYPE_SDLC";
              if ( v16 == 1 )
                return L"IF_TYPE_DS1";
            }
          }
          else
          {
            if ( v2 == 13 )
              return L"IF_TYPE_PROTEON_80MBIT";
            if ( v2 > 7 )
            {
              v9 = v2 - 8;
              if ( !v9 )
                return L"IF_TYPE_ISO88024_TOKENBUS";
              v10 = v9 - 1;
              if ( !v10 )
                return L"IF_TYPE_ISO88025_TOKENRING";
              v11 = v10 - 1;
              if ( !v11 )
                return L"IF_TYPE_ISO88026_MAN";
              v12 = v11 - 1;
              if ( !v12 )
                return L"IF_TYPE_STARLAN";
              if ( v12 == 1 )
                return L"IF_TYPE_PROTEON_10MBIT";
            }
            else
            {
              if ( v2 == 7 )
                return L"IF_TYPE_IS088023_CSMACD";
              v3 = v2 - 1;
              if ( !v3 )
                return L"IF_TYPE_OTHER";
              v4 = v3 - 1;
              if ( !v4 )
                return L"IF_TYPE_REGULAR_1822";
              v5 = v4 - 1;
              if ( !v5 )
                return L"IF_TYPE_HDH_1822";
              v6 = v5 - 1;
              if ( !v6 )
                return L"IF_TYPE_DDN_X25";
              v7 = v6 - 1;
              if ( !v7 )
                return L"IF_TYPE_RFC877_X25";
              if ( v7 == 1 )
                return L"Ethernet (ETHERNET_CSMACD)";
            }
          }
        }
      }
      return L"(unknown IFTYPE)";
    }
    if ( v2 <= 0x96 )
    {
      if ( v2 == 150 )
        return L"IF_TYPE_MPLS_TUNNEL";
      if ( v2 <= 0x7D )
      {
        if ( v2 == 125 )
          return L"IF_TYPE_FAST";
        if ( v2 > 0x71 )
        {
          if ( v2 > 0x77 )
          {
            v85 = v2 - 120;
            if ( !v85 )
              return L"IF_TYPE_V37";
            v86 = v85 - 1;
            if ( !v86 )
              return L"IF_TYPE_X25_MLP";
            v87 = v86 - 1;
            if ( !v87 )
              return L"IF_TYPE_X25_HUNTGROUP";
            v88 = v87 - 1;
            if ( !v88 )
              return L"IF_TYPE_TRANSPHDLC";
            if ( v88 == 1 )
              return L"IF_TYPE_INTERLEAVE";
          }
          else
          {
            if ( v2 == 119 )
              return L"IF_TYPE_LAP_F";
            v81 = v2 - 114;
            if ( !v81 )
              return L"IF_TYPE_IPOVER_ATM";
            v82 = v81 - 1;
            if ( !v82 )
              return L"IF_TYPE_ISO88025_FIBER";
            v83 = v82 - 1;
            if ( !v83 )
              return L"IF_TYPE_TDLC";
            v84 = v83 - 1;
            if ( !v84 )
              return L"IF_TYPE_GIGABITETHERNET";
            if ( v84 == 1 )
              return L"IF_TYPE_HDLC";
          }
        }
        else
        {
          if ( v2 == 113 )
            return L"IF_TYPE_MPC";
          if ( v2 > 0x6B )
          {
            v77 = v2 - 108;
            if ( !v77 )
              return L"IF_TYPE_PPPMULTILINKBUNDLE";
            v78 = v77 - 1;
            if ( !v78 )
              return L"IF_TYPE_IPOVER_CDLC";
            v79 = v78 - 1;
            if ( !v79 )
              return L"IF_TYPE_IPOVER_CLAW";
            v80 = v79 - 1;
            if ( !v80 )
              return L"IF_TYPE_STACKTOSTACK";
            if ( v80 == 1 )
              return L"IF_TYPE_VIRTUALIPADDRESS";
          }
          else
          {
            if ( v2 == 107 )
              return L"IF_TYPE_ATM_IMA";
            v72 = v2 - 101;
            if ( !v72 )
              return L"IF_TYPE_VOICE_FXO";
            v73 = v72 - 1;
            if ( !v73 )
              return L"IF_TYPE_VOICE_FXS";
            v74 = v73 - 1;
            if ( !v74 )
              return L"IF_TYPE_VOICE_ENCAP";
            v75 = v74 - 1;
            if ( !v75 )
              return L"IF_TYPE_VOICE_OVERIP";
            v76 = v75 - 1;
            if ( !v76 )
              return L"IF_TYPE_ATM_DXI";
            if ( v76 == 1 )
              return L"IF_TYPE_ATM_FUNI";
          }
        }
        return L"(unknown IFTYPE)";
      }
      if ( v2 > 0x8A )
      {
        if ( v2 > 0x90 )
        {
          v102 = v2 - 145;
          if ( !v102 )
            return L"IF_TYPE_IF_GSN";
          v103 = v102 - 1;
          if ( !v103 )
            return L"IF_TYPE_DVBRCC_MACLAYER";
          v104 = v103 - 1;
          if ( !v104 )
            return L"IF_TYPE_DVBRCC_DOWNSTREAM";
          v105 = v104 - 1;
          if ( !v105 )
            return L"IF_TYPE_DVBRCC_UPSTREAM";
          if ( v105 == 1 )
            return L"IF_TYPE_ATM_VIRTUAL";
        }
        else
        {
          if ( v2 == 144 )
            return L"IF_TYPE_IEEE1394";
          v98 = v2 - 139;
          if ( !v98 )
            return L"IF_TYPE_MEDIAMAILOVERIP";
          v99 = v98 - 1;
          if ( !v99 )
            return L"IF_TYPE_DTM";
          v100 = v99 - 1;
          if ( !v100 )
            return L"IF_TYPE_DCN";
          v101 = v100 - 1;
          if ( !v101 )
            return L"IF_TYPE_IPFORWARD";
          if ( v101 == 1 )
            return L"IF_TYPE_MSDSL";
        }
        return L"(unknown IFTYPE)";
      }
      if ( v2 == 138 )
        return L"IF_TYPE_DIGITALPOWERLINE";
      if ( v2 > 0x84 )
      {
        v94 = v2 - 133;
        if ( !v94 )
          return L"IF_TYPE_CES";
        v95 = v94 - 1;
        if ( !v95 )
          return L"IF_TYPE_ATM_SUBINTERFACE";
        v96 = v95 - 1;
        if ( !v96 )
          return L"IF_TYPE_L2_VLAN";
        v97 = v96 - 1;
        if ( !v97 )
          return L"IF_TYPE_L3_IPVLAN";
        if ( v97 == 1 )
          return L"IF_TYPE_L3_IPXVLAN";
        return L"(unknown IFTYPE)";
      }
      if ( v2 == 132 )
        return L"IF_TYPE_COFFEE";
      v89 = v2 - 126;
      if ( !v89 )
        return L"IF_TYPE_IP";
      v90 = v89 - 1;
      if ( !v90 )
        return L"IF_TYPE_DOCSCABLE_MACLAYER";
      v91 = v90 - 1;
      if ( !v91 )
        return L"IF_TYPE_DOCSCABLE_DOWNSTREAM";
      v92 = v91 - 1;
      if ( !v92 )
        return L"IF_TYPE_DOCSCABLE_UPSTREAM";
      v93 = v92 - 1;
      if ( !v93 )
        return L"IF_TYPE_A12MPPSWITCH";
      if ( v93 == 1 )
      {
        switch ( *a2 )
        {
          case TUNNEL_TYPE_NONE:
            return L"Tunnel (NONE)";
          case TUNNEL_TYPE_OTHER:
            return L"Tunnel (OTHER)";
          case TUNNEL_TYPE_DIRECT:
            return L"Tunnel (DIRECT)";
          case TUNNEL_TYPE_6TO4:
            return L"Tunnel (6TO4)";
          case TUNNEL_TYPE_ISATAP:
            return L"Tunnel (ISATAP)";
          case TUNNEL_TYPE_TEREDO:
            return L"Tunnel (TEREDO)";
          case TUNNEL_TYPE_IPHTTPS:
            return L"Tunnel (IPHTTPS)";
        }
        return L"XBOX Wireless";
      }
      return L"(unknown IFTYPE)";
    }
    if ( v2 <= 0xAF )
    {
      if ( v2 == 175 )
        return L"IF_TYPE_NFAS";
      if ( v2 > 0xA3 )
      {
        if ( v2 > 0xA9 )
        {
          v119 = v2 - 170;
          if ( !v119 )
            return L"IF_TYPE_DS1_FDL";
          v120 = v119 - 1;
          if ( !v120 )
            return L"IF_TYPE_POS";
          v121 = v120 - 1;
          if ( !v121 )
            return L"IF_TYPE_DVB_ASI_IN";
          v122 = v121 - 1;
          if ( !v122 )
            return L"IF_TYPE_DVB_ASI_OUT";
          if ( v122 == 1 )
            return L"IF_TYPE_PLC";
        }
        else
        {
          if ( v2 == 169 )
            return L"IF_TYPE_SHDSL";
          v115 = v2 - 164;
          if ( !v115 )
            return L"IF_TYPE_H323_GATEKEEPER";
          v116 = v115 - 1;
          if ( !v116 )
            return L"IF_TYPE_H323_PROXY";
          v117 = v116 - 1;
          if ( !v117 )
            return L"IF_TYPE_MPLS";
          v118 = v117 - 1;
          if ( !v118 )
            return L"IF_TYPE_MF_SIGLINK";
          if ( v118 == 1 )
            return L"IF_TYPE_HDSL2";
        }
      }
      else
      {
        if ( v2 == 163 )
          return L"IF_TYPE_FRF16_MFR_BUNDLE";
        if ( v2 > 0x9D )
        {
          v111 = v2 - 158;
          if ( !v111 )
            return L"IF_TYPE_FR_FORWARD";
          v112 = v111 - 1;
          if ( !v112 )
            return L"IF_TYPE_RFC1483";
          v113 = v112 - 1;
          if ( !v113 )
            return L"IF_TYPE_USB";
          v114 = v113 - 1;
          if ( !v114 )
            return L"IF_TYPE_IEEE8023AD_LAG";
          if ( v114 == 1 )
            return L"IF_TYPE_BGP_POLICY_ACCOUNTING";
        }
        else
        {
          if ( v2 == 157 )
            return L"IF_TYPE_PROP_WIRELESS_P2P";
          v106 = v2 - 151;
          if ( !v106 )
            return L"IF_TYPE_SRP";
          v107 = v106 - 1;
          if ( !v107 )
            return L"IF_TYPE_VOICEOVERATM";
          v108 = v107 - 1;
          if ( !v108 )
            return L"IF_TYPE_VOICEOVERFRAMERELAY";
          v109 = v108 - 1;
          if ( !v109 )
            return L"IF_TYPE_IDSL";
          v110 = v109 - 1;
          if ( !v110 )
            return L"IF_TYPE_COMPOSITELINK";
          if ( v110 == 1 )
            return L"IF_TYPE_SS7_SIGLINK";
        }
      }
      return L"(unknown IFTYPE)";
    }
    if ( v2 <= 0xF3 )
    {
      if ( v2 == 243 )
        return L"Cellular (WWANPP)";
      if ( v2 <= 0xBB )
      {
        if ( v2 == 187 )
          return L"IF_TYPE_AAL2";
        if ( v2 > 0xB5 )
        {
          v127 = v2 - 182;
          if ( !v127 )
            return L"IF_TYPE_PROP_DOCS_WIRELESS_UPSTREAM";
          v128 = v127 - 1;
          if ( !v128 )
            return L"IF_TYPE_HIPERLAN2";
          v129 = v128 - 1;
          if ( !v129 )
            return L"IF_TYPE_PROP_BWA_P2MP";
          v130 = v129 - 1;
          if ( !v130 )
            return L"IF_TYPE_SONET_OVERHEAD_CHANNEL";
          if ( v130 == 1 )
            return L"IF_TYPE_DIGITAL_WRAPPER_OVERHEAD_CHANNEL";
        }
        else
        {
          if ( v2 == 181 )
            return L"IF_TYPE_PROP_DOCS_WIRELESS_DOWNSTREAM";
          v123 = v2 - 176;
          if ( !v123 )
            return L"IF_TYPE_TR008";
          v124 = v123 - 1;
          if ( !v124 )
            return L"IF_TYPE_GR303_RDT";
          v125 = v124 - 1;
          if ( !v125 )
            return L"IF_TYPE_GR303_IDT";
          v126 = v125 - 1;
          if ( !v126 )
            return L"IF_TYPE_ISUP";
          if ( v126 == 1 )
            return L"IF_TYPE_PROP_DOCS_WIRELESS_MACLAYER";
        }
        return L"(unknown IFTYPE)";
      }
      if ( v2 <= 0xC1 )
      {
        if ( v2 == 193 )
          return L"IF_TYPE_FR_DLCI_ENDPT";
        v131 = v2 - 188;
        if ( !v131 )
          return L"IF_TYPE_RADIO_MAC";
        v132 = v131 - 1;
        if ( !v132 )
          return L"IF_TYPE_ATM_RADIO";
        v133 = v132 - 1;
        if ( !v133 )
          return L"IF_TYPE_IMT";
        v134 = v133 - 1;
        if ( !v134 )
          return L"IF_TYPE_MVL";
        if ( v134 == 1 )
          return L"IF_TYPE_REACH_DSL";
        return L"(unknown IFTYPE)";
      }
      v135 = v2 - 194;
      if ( !v135 )
        return L"IF_TYPE_ATM_VCI_ENDPT";
      v136 = v135 - 1;
      if ( !v136 )
        return L"IF_TYPE_OPTICAL_CHANNEL";
      v137 = v136 - 1;
      if ( !v137 )
        return L"IF_TYPE_OPTICAL_TRANSPORT";
      if ( v137 == 41 )
        return L"IF_TYPE_IEEE80216_WMAN";
      return L"(unknown IFTYPE)";
    }
    v138 = L"(unknown IFTYPE)";
    if ( v2 == 244 )
      return L"IF_TYPE_WWANPP2";
    return v138;
  }
}

```

## disassembly

```asm
0x18003a79c  mov     eax, [rcx]
0x18003a79e  mov     ecx, 103h
0x18003a7a3  cmp     eax, ecx
0x18003a7a5  ja      loc_18003B3D4
0x18003a7ab  jz      loc_18003B3CC
0x18003a7b1  cmp     eax, 64h ; 'd'
0x18003a7b4  ja      loc_18003AD65
0x18003a7ba  jz      loc_18003AD5D
0x18003a7c0  cmp     eax, 32h ; '2'
0x18003a7c3  ja      loc_18003AA9A
0x18003a7c9  jz      loc_18003AA92
0x18003a7cf  cmp     eax, 19h
0x18003a7d2  ja      loc_18003A93C
0x18003a7d8  jz      loc_18003A934
0x18003a7de  cmp     eax, 0Dh
0x18003a7e1  ja      loc_18003A89B
0x18003a7e7  jz      loc_18003A893
0x18003a7ed  cmp     eax, 7
0x18003a7f0  ja      short loc_18003A84E
0x18003a7f2  jz      short loc_18003A846
0x18003a7f4  sub     eax, 1
0x18003a7f7  jz      short loc_18003A83E
0x18003a7f9  sub     eax, 1
0x18003a7fc  jz      short loc_18003A836
0x18003a7fe  sub     eax, 1
0x18003a801  jz      short loc_18003A82E
0x18003a803  sub     eax, 1
0x18003a806  jz      short loc_18003A826
0x18003a808  sub     eax, 1
0x18003a80b  jz      short loc_18003A81E
0x18003a80d  cmp     eax, 1
0x18003a810  jnz     loc_18003B381
0x18003a816  lea     rax, aEthernetEthern; "Ethernet (ETHERNET_CSMACD)"
0x18003a81d  retn
0x18003a81e  lea     rax, aIfTypeRfc877X2; "IF_TYPE_RFC877_X25"
0x18003a825  retn
0x18003a826  lea     rax, aIfTypeDdnX25; "IF_TYPE_DDN_X25"
0x18003a82d  retn
0x18003a82e  lea     rax, aIfTypeHdh1822; "IF_TYPE_HDH_1822"
0x18003a835  retn
0x18003a836  lea     rax, aIfTypeRegular1; "IF_TYPE_REGULAR_1822"
0x18003a83d  retn
0x18003a83e  lea     rax, aIfTypeOther; "IF_TYPE_OTHER"
0x18003a845  retn
0x18003a846  lea     rax, aIfTypeIs088023; "IF_TYPE_IS088023_CSMACD"
0x18003a84d  retn
0x18003a84e  sub     eax, 8
0x18003a851  jz      short loc_18003A88B
0x18003a853  sub     eax, 1
0x18003a856  jz      short loc_18003A883
0x18003a858  sub     eax, 1
0x18003a85b  jz      short loc_18003A87B
0x18003a85d  sub     eax, 1
0x18003a860  jz      short loc_18003A873
0x18003a862  cmp     eax, 1
0x18003a865  jnz     loc_18003B381
0x18003a86b  lea     rax, aIfTypeProteon1; "IF_TYPE_PROTEON_10MBIT"
0x18003a872  retn
0x18003a873  lea     rax, aIfTypeStarlan; "IF_TYPE_STARLAN"
0x18003a87a  retn
0x18003a87b  lea     rax, aIfTypeIso88026; "IF_TYPE_ISO88026_MAN"
0x18003a882  retn
0x18003a883  lea     rax, aIfTypeIso88025_0; "IF_TYPE_ISO88025_TOKENRING"
0x18003a88a  retn
0x18003a88b  lea     rax, aIfTypeIso88024; "IF_TYPE_ISO88024_TOKENBUS"
0x18003a892  retn
0x18003a893  lea     rax, aIfTypeProteon8; "IF_TYPE_PROTEON_80MBIT"
0x18003a89a  retn
0x18003a89b  cmp     eax, 13h
0x18003a89e  ja      short loc_18003A8EF
0x18003a8a0  jz      short loc_18003A8E7
0x18003a8a2  sub     eax, 0Eh
0x18003a8a5  jz      short loc_18003A8DF
0x18003a8a7  sub     eax, 1
0x18003a8aa  jz      short loc_18003A8D7
0x18003a8ac  sub     eax, 1
0x18003a8af  jz      short loc_18003A8CF
0x18003a8b1  sub     eax, 1
0x18003a8b4  jz      short loc_18003A8C7
0x18003a8b6  cmp     eax, 1
0x18003a8b9  jnz     loc_18003B381
0x18003a8bf  lea     rax, aIfTypeDs1; "IF_TYPE_DS1"
0x18003a8c6  retn
0x18003a8c7  lea     rax, aIfTypeSdlc; "IF_TYPE_SDLC"
0x18003a8ce  retn
0x18003a8cf  lea     rax, aIfTypeLapB; "IF_TYPE_LAP_B"
0x18003a8d6  retn
0x18003a8d7  lea     rax, aIfTypeFddi; "IF_TYPE_FDDI"
0x18003a8de  retn
0x18003a8df  lea     rax, aIfTypeHypercha; "IF_TYPE_HYPERCHANNEL"
0x18003a8e6  retn
0x18003a8e7  lea     rax, aIfTypeE1; "IF_TYPE_E1"
0x18003a8ee  retn
0x18003a8ef  sub     eax, 14h
0x18003a8f2  jz      short loc_18003A92C
0x18003a8f4  sub     eax, 1
0x18003a8f7  jz      short loc_18003A924
0x18003a8f9  sub     eax, 1
0x18003a8fc  jz      short loc_18003A91C
0x18003a8fe  sub     eax, 1
0x18003a901  jz      short loc_18003A914
0x18003a903  cmp     eax, 1
0x18003a906  jnz     loc_18003B381
0x18003a90c  lea     rax, aIfTypeSoftware; "IF_TYPE_SOFTWARE_LOOPBACK"
0x18003a913  retn
0x18003a914  lea     rax, aIfTypePpp; "IF_TYPE_PPP"
0x18003a91b  retn
0x18003a91c  lea     rax, aIfTypePropPoin; "IF_TYPE_PROP_POINT2POINT_SERIAL"
0x18003a923  retn
0x18003a924  lea     rax, aIfTypePrimaryI; "IF_TYPE_PRIMARY_ISDN"
0x18003a92b  retn
0x18003a92c  lea     rax, aIfTypeBasicIsd; "IF_TYPE_BASIC_ISDN"
0x18003a933  retn
0x18003a934  lea     rax, aIfTypeEon; "IF_TYPE_EON"
0x18003a93b  retn
0x18003a93c  cmp     eax, 26h ; '&'
0x18003a93f  ja      loc_18003A9F9
0x18003a945  jz      loc_18003A9F1
0x18003a94b  cmp     eax, 20h ; ' '
0x18003a94e  ja      short loc_18003A9AC
0x18003a950  jz      short loc_18003A9A4
0x18003a952  sub     eax, 1Ah
0x18003a955  jz      short loc_18003A99C
0x18003a957  sub     eax, 1
0x18003a95a  jz      short loc_18003A994
0x18003a95c  sub     eax, 1
0x18003a95f  jz      short loc_18003A98C
0x18003a961  sub     eax, 1
0x18003a964  jz      short loc_18003A984
0x18003a966  sub     eax, 1
0x18003a969  jz      short loc_18003A97C
0x18003a96b  cmp     eax, 1
0x18003a96e  jnz     loc_18003B381
0x18003a974  lea     rax, aIfTypeSip; "IF_TYPE_SIP"
0x18003a97b  retn
0x18003a97c  lea     rax, aIfTypeDs3; "IF_TYPE_DS3"
0x18003a983  retn
0x18003a984  lea     rax, aIfTypeUltra; "IF_TYPE_ULTRA"
0x18003a98b  retn
0x18003a98c  lea     rax, aIfTypeSlip; "IF_TYPE_SLIP"
0x18003a993  retn
0x18003a994  lea     rax, aIfTypeNsip; "IF_TYPE_NSIP"
0x18003a99b  retn
0x18003a99c  lea     rax, aIfTypeEthernet; "IF_TYPE_ETHERNET_3MBIT"
0x18003a9a3  retn
0x18003a9a4  lea     rax, aIfTypeFramerel_1; "IF_TYPE_FRAMERELAY"
0x18003a9ab  retn
0x18003a9ac  sub     eax, 21h ; '!'
0x18003a9af  jz      short loc_18003A9E9
0x18003a9b1  sub     eax, 1
0x18003a9b4  jz      short loc_18003A9E1
0x18003a9b6  sub     eax, 1
0x18003a9b9  jz      short loc_18003A9D9
0x18003a9bb  sub     eax, 1
0x18003a9be  jz      short loc_18003A9D1
0x18003a9c0  cmp     eax, 1
0x18003a9c3  jnz     loc_18003B381
0x18003a9c9  lea     rax, aIfTypeAtm; "IF_TYPE_ATM"
0x18003a9d0  retn
0x18003a9d1  lea     rax, aIfTypeArcnetPl; "IF_TYPE_ARCNET_PLUS"
0x18003a9d8  retn
0x18003a9d9  lea     rax, aIfTypeArcnet; "IF_TYPE_ARCNET"
0x18003a9e0  retn
0x18003a9e1  lea     rax, aIfTypePara; "IF_TYPE_PARA"
0x18003a9e8  retn
0x18003a9e9  lea     rax, aIfTypeRs232; "IF_TYPE_RS232"
0x18003a9f0  retn
0x18003a9f1  lea     rax, aIfTypeMioX25; "IF_TYPE_MIO_X25"
0x18003a9f8  retn
0x18003a9f9  cmp     eax, 2Ch ; ','
0x18003a9fc  ja      short loc_18003AA4D
0x18003a9fe  jz      short loc_18003AA45
0x18003aa00  sub     eax, 27h ; '''
0x18003aa03  jz      short loc_18003AA3D
0x18003aa05  sub     eax, 1
0x18003aa08  jz      short loc_18003AA35
0x18003aa0a  sub     eax, 1
0x18003aa0d  jz      short loc_18003AA2D
0x18003aa0f  sub     eax, 1
0x18003aa12  jz      short loc_18003AA25
0x18003aa14  cmp     eax, 1
0x18003aa17  jnz     loc_18003B381
0x18003aa1d  lea     rax, aIfTypeSmdsDxi; "IF_TYPE_SMDS_DXI"
0x18003aa24  retn
0x18003aa25  lea     rax, aIfTypeLocaltal; "IF_TYPE_LOCALTALK"
0x18003aa2c  retn
0x18003aa2d  lea     rax, aIfTypeIso88022; "IF_TYPE_ISO88022_LLC"
0x18003aa34  retn
0x18003aa35  lea     rax, aIfTypeX25Ple; "IF_TYPE_X25_PLE"
0x18003aa3c  retn
0x18003aa3d  lea     rax, aIfTypeSonet; "IF_TYPE_SONET"
0x18003aa44  retn
0x18003aa45  lea     rax, aIfTypeFramerel_2; "IF_TYPE_FRAMERELAY_SERVICE"
0x18003aa4c  retn
0x18003aa4d  sub     eax, 2Dh ; '-'
0x18003aa50  jz      short loc_18003AA8A
0x18003aa52  sub     eax, 1
0x18003aa55  jz      short loc_18003AA82
0x18003aa57  sub     eax, 1
0x18003aa5a  jz      short loc_18003AA7A
0x18003aa5c  sub     eax, 1
0x18003aa5f  jz      short loc_18003AA72
0x18003aa61  cmp     eax, 1
0x18003aa64  jnz     loc_18003B381
0x18003aa6a  lea     rax, aIfTypeAal5; "IF_TYPE_AAL5"
0x18003aa71  retn
0x18003aa72  lea     rax, aIfTypeModem; "IF_TYPE_MODEM"
0x18003aa79  retn
0x18003aa7a  lea     rax, aIfTypeHippi; "IF_TYPE_HIPPI"
0x18003aa81  retn
0x18003aa82  lea     rax, aIfTypeHssi; "IF_TYPE_HSSI"
0x18003aa89  retn
0x18003aa8a  lea     rax, aIfTypeV35; "IF_TYPE_V35"
0x18003aa91  retn
0x18003aa92  lea     rax, aIfTypeSonetPat; "IF_TYPE_SONET_PATH"
0x18003aa99  retn
0x18003aa9a  cmp     eax, 4Bh ; 'K'
0x18003aa9d  ja      loc_18003AC07
0x18003aaa3  jz      loc_18003ABFF
0x18003aaa9  cmp     eax, 3Fh ; '?'
0x18003aaac  ja      loc_18003AB66
0x18003aab2  jz      loc_18003AB5E
0x18003aab8  cmp     eax, 39h ; '9'
0x18003aabb  ja      short loc_18003AB19
0x18003aabd  jz      short loc_18003AB11
0x18003aabf  sub     eax, 33h ; '3'
0x18003aac2  jz      short loc_18003AB09
0x18003aac4  sub     eax, 1
0x18003aac7  jz      short loc_18003AB01
0x18003aac9  sub     eax, 1
0x18003aacc  jz      short loc_18003AAF9
0x18003aace  sub     eax, 1
0x18003aad1  jz      short loc_18003AAF1
0x18003aad3  sub     eax, 1
0x18003aad6  jz      short loc_18003AAE9
0x18003aad8  cmp     eax, 1
0x18003aadb  jnz     loc_18003B381
0x18003aae1  lea     rax, aIfTypeFibrecha; "IF_TYPE_FIBRECHANNEL"
0x18003aae8  retn
0x18003aae9  lea     rax, aIfTypeIeee8021_0; "IF_TYPE_IEEE80212"
0x18003aaf0  retn
0x18003aaf1  lea     rax, aIfTypePropMult; "IF_TYPE_PROP_MULTIPLEXOR"
0x18003aaf8  retn
0x18003aaf9  lea     rax, aIfTypePropVirt; "IF_TYPE_PROP_VIRTUAL"
0x18003ab00  retn
0x18003ab01  lea     rax, aIfTypeSmdsIcip; "IF_TYPE_SMDS_ICIP"
0x18003ab08  retn
0x18003ab09  lea     rax, aIfTypeSonetVt; "IF_TYPE_SONET_VT"
0x18003ab10  retn
0x18003ab11  lea     rax, aIfTypeHippiint; "IF_TYPE_HIPPIINTERFACE"
0x18003ab18  retn
0x18003ab19  sub     eax, 3Ah ; ':'
0x18003ab1c  jz      short loc_18003AB56
0x18003ab1e  sub     eax, 1
0x18003ab21  jz      short loc_18003AB4E
0x18003ab23  sub     eax, 1
0x18003ab26  jz      short loc_18003AB46
0x18003ab28  sub     eax, 1
0x18003ab2b  jz      short loc_18003AB3E
0x18003ab2d  cmp     eax, 1
0x18003ab30  jnz     loc_18003B381
0x18003ab36  lea     rax, aIfTypeFastethe_0; "IF_TYPE_FASTETHER"
0x18003ab3d  retn
0x18003ab3e  lea     rax, aIfTypeCctemul; "IF_TYPE_CCTEMUL"
0x18003ab45  retn
0x18003ab46  lea     rax, aIfTypeAflane80_0; "IF_TYPE_AFLANE_8025"
0x18003ab4d  retn
0x18003ab4e  lea     rax, aIfTypeAflane80; "IF_TYPE_AFLANE_8023"
0x18003ab55  retn
0x18003ab56  lea     rax, aIfTypeFramerel; "IF_TYPE_FRAMERELAY_INTERCONNECT"
0x18003ab5d  retn
0x18003ab5e  lea     rax, aIfTypeIsdn; "IF_TYPE_ISDN"
0x18003ab65  retn
0x18003ab66  cmp     eax, 45h ; 'E'
0x18003ab69  ja      short loc_18003ABBA
0x18003ab6b  jz      short loc_18003ABB2
0x18003ab6d  sub     eax, 40h ; '@'
0x18003ab70  jz      short loc_18003ABAA
0x18003ab72  sub     eax, 1
0x18003ab75  jz      short loc_18003ABA2
0x18003ab77  sub     eax, 1
0x18003ab7a  jz      short loc_18003AB9A
0x18003ab7c  sub     eax, 1
0x18003ab7f  jz      short loc_18003AB92
0x18003ab81  cmp     eax, 1
0x18003ab84  jnz     loc_18003B381
0x18003ab8a  lea     rax, aIfTypeQllc; "IF_TYPE_QLLC"
0x18003ab91  retn
0x18003ab92  lea     rax, aIfTypeG7032mb; "IF_TYPE_G703_2MB"
0x18003ab99  retn
0x18003ab9a  lea     rax, aIfTypeG70364k; "IF_TYPE_G703_64K"
0x18003aba1  retn
0x18003aba2  lea     rax, aIfTypeV36; "IF_TYPE_V36"
0x18003aba9  retn
0x18003abaa  lea     rax, aIfTypeV11; "IF_TYPE_V11"
0x18003abb1  retn
0x18003abb2  lea     rax, aIfTypeFastethe; "IF_TYPE_FASTETHER_FX"
0x18003abb9  retn
0x18003abba  sub     eax, 46h ; 'F'
0x18003abbd  jz      short loc_18003ABF7
  ... truncated ...
```
