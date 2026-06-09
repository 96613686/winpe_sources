# CCO::OnServerRedirectionPacket(RDP_SERVER_REDIRECTION_PACKET *,uint,int *)

- ea: `0x1801803dc`
- end: `0x180181db1`
- name: `?OnServerRedirectionPacket@CCO@@QEAAJPEFAURDP_SERVER_REDIRECTION_PACKET@@IPEAH@Z`
- size: `6613`
- prototype: `__int64 __fastcall(CCO *__hidden this, struct RDP_SERVER_REDIRECTION_PACKET *, unsigned int, int *)`
- caller_count: `2`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800a8a60`
- `0x18017e5e0`

## callees

- `0x18002a334`
- `0x18002a374`
- `0x180039c98`
- `0x180045338`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x1800ebae0`
- `0x1800ee040`
- `0x1800f31f0`
- `0x18010215c`
- `0x18015f3a8`
- `0x18015f468`
- `0x18015f5f8`
- `0x180175230`
- `0x1801803dc`
- `0x180182658`
- `0x180182a34`
- `0x180688f26`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1801810d4`
- `KERNEL32!LocalAlloc` at `0x180181143`
- `KERNEL32!LocalAlloc` at `0x180181312`
- `KERNEL32!LocalAlloc` at `0x180181459`
- `KERNEL32!LocalAlloc` at `0x180181516`
- `KERNEL32!LocalAlloc` at `0x1801817ba`
- `KERNEL32!LocalAlloc` at `0x180181872`
- `KERNEL32!LocalAlloc` at `0x1801819a0`
- `KERNEL32!LocalAlloc` at `0x180181a91`
- `KERNEL32!LocalAlloc` at `0x180181b89`
- `KERNEL32!LocalAlloc` at `0x1801810d4`
- `KERNEL32!LocalAlloc` at `0x180181143`
- `KERNEL32!LocalAlloc` at `0x180181312`
- `KERNEL32!LocalAlloc` at `0x180181459`
- `KERNEL32!LocalAlloc` at `0x180181516`
- `KERNEL32!LocalAlloc` at `0x1801817ba`
- `KERNEL32!LocalAlloc` at `0x180181872`
- `KERNEL32!LocalAlloc` at `0x1801819a0`
- `KERNEL32!LocalAlloc` at `0x180181a91`
- `KERNEL32!LocalAlloc` at `0x180181b89`
- `KERNEL32!LocalFree` at `0x18018056c`
- `KERNEL32!LocalFree` at `0x18018057f`
- `KERNEL32!LocalFree` at `0x1801813f7`
- `KERNEL32!LocalFree` at `0x1801814a7`
- `KERNEL32!LocalFree` at `0x180181571`
- `KERNEL32!LocalFree` at `0x180181634`
- `KERNEL32!LocalFree` at `0x180181803`
- `KERNEL32!LocalFree` at `0x1801818b7`
- `KERNEL32!LocalFree` at `0x180181a2f`
- `KERNEL32!LocalFree` at `0x180181b20`
- `KERNEL32!LocalFree` at `0x180181da6`
- `KERNEL32!LocalFree` at `0x18018056c`
- `KERNEL32!LocalFree` at `0x18018057f`
- `KERNEL32!LocalFree` at `0x1801813f7`
- `KERNEL32!LocalFree` at `0x1801814a7`
- `KERNEL32!LocalFree` at `0x180181571`
- `KERNEL32!LocalFree` at `0x180181634`
- `KERNEL32!LocalFree` at `0x180181803`
- `KERNEL32!LocalFree` at `0x1801818b7`
- `KERNEL32!LocalFree` at `0x180181a2f`
- `KERNEL32!LocalFree` at `0x180181b20`
- `KERNEL32!LocalFree` at `0x180181da6`

## string_xrefs

- `0x1801806f7`: `can not read TARGET_NET_ADDRESSsize`
- `0x180180867`: `can not read TARGET_NET_ADDRESSsize`
- `0x180180727`: `can not read TARGET_NET_ADDRESS`
- `0x1801808a2`: `can not read TARGET_NET_ADDRESS`
- `0x180180763`: `can not read LOAD_BALANCE_INFOsize`
- `0x1801808ef`: `can not read LOAD_BALANCE_INFOsize`
- `0x180180789`: `can not read LOAD_BALANCE_INFO`
- `0x180180929`: `can not read LOAD_BALANCE_INFO`
- `0x18018095e`: `can not read LB_USERNAMEsize`
- `0x18018099a`: `can not read LB_USERNAME`
- `0x180180a3f`: `can not read LB_DOMAINsize`
- `0x180180a79`: `can not read LB_DOMAIN`
- `0x180180b0d`: `can not read LB_PASSWORDsize`
- `0x180180b48`: `can not read LB_PASSWORD`
- `0x180180bd8`: `can not read TARGET_FQDNsize`
- `0x180180c12`: `can not read TARGET_FQDN`
- `0x180180ca7`: `can not read TARGET_NETBIOS_NAMEsize`
- `0x180180ce1`: `can not read TARGET_NETBIOS_NAME`
- `0x180180d76`: `can not read LB_CLIENT_TSV_URLsize`
- `0x180180da5`: `can not read LB_CLIENT_TSV_URL`
- `0x180180e8f`: `can not read LB_REDIRECTION_GUIDsize`
- `0x180180eca`: `can not read LB_REDIRECTION_GUID`
- `0x180180f18`: `can not read LB_TARGET_CERTIFICATEsize`
- `0x180180f53`: `can not read LB_TARGET_CERTIFICATE`
- `0x1801811bf`: `can not read TARGET_NET_ADDRESS_IPV6V4_LIST Addressessize`
- `0x1801811ea`: `can not read TARGET_NET_ADDRESS_IPV6V4_LIST Addresses`

## pseudocode

```c
__int64 __fastcall CCO::OnServerRedirectionPacket(
        CTSConnectionHandler **this,
        struct RDP_SERVER_REDIRECTION_PACKET *a2,
        __int64 a3,
        int *a4)
{
  __int64 v4; // rsi
  unsigned int v5; // edi
  CCO *v7; // r12
  unsigned int ActivityIdPrefix; // eax
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // ebx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // eax
  int v16; // edx
  const char *v17; // rcx
  unsigned int v18; // eax
  HLOCAL v19; // rcx
  unsigned int v21; // eax
  __int64 v22; // rax
  unsigned int v23; // ecx
  unsigned __int8 *v24; // rsi
  int v25; // r15d
  unsigned __int8 *v26; // rdi
  unsigned __int64 v27; // r14
  char *v28; // r12
  unsigned int v29; // r15d
  unsigned __int8 *v30; // rdi
  unsigned int v31; // r12d
  unsigned __int8 *v32; // rdi
  size_t v33; // rbx
  unsigned __int64 v34; // rbx
  size_t v35; // r15
  __int64 v36; // rbx
  int v37; // eax
  size_t v38; // rbx
  __int64 v39; // r15
  int v40; // eax
  size_t v41; // rbx
  unsigned int v42; // eax
  size_t v43; // rbx
  __int64 v44; // r15
  int v45; // eax
  size_t v46; // rbx
  __int64 v47; // r15
  int v48; // eax
  unsigned __int64 v49; // rbx
  unsigned __int8 *v50; // r15
  int v51; // eax
  __int64 v52; // rcx
  size_t v53; // r15
  size_t v54; // r15
  unsigned int *v55; // r15
  __int64 v56; // rdi
  unsigned int v57; // eax
  unsigned int v58; // eax
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // r8
  __int64 v62; // r9
  int v63; // eax
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // r9
  _DWORD *v67; // rdi
  int v68; // eax
  int v69; // edx
  const char *v70; // rcx
  unsigned __int8 *v71; // r15
  __int64 v72; // r13
  __int64 v73; // rdx
  __int64 v74; // rdi
  __int64 v75; // r8
  HKEY v76; // rax
  __int64 v77; // rdx
  __int64 v78; // rcx
  unsigned int v79; // r15d
  BOOL v80; // r13d
  unsigned int v81; // esi
  unsigned __int16 *v82; // rax
  unsigned __int16 *v83; // rdi
  unsigned int v84; // eax
  __int64 v85; // rdx
  __int64 v86; // rcx
  unsigned int v87; // ebx
  HLOCAL v88; // rax
  void *v89; // rdi
  __int64 v90; // rcx
  size_t v91; // rdi
  SIZE_T v92; // rdx
  HLOCAL v93; // rax
  void *v94; // rsi
  __int64 v95; // rcx
  _BYTE *v96; // rax
  _BYTE *v97; // rax
  __int64 v98; // rcx
  __int64 v99; // rcx
  __int64 v100; // rcx
  __int64 v101; // rcx
  void *v102; // rsi
  unsigned int v103; // ebx
  HLOCAL v104; // rax
  void *v105; // rdi
  __int64 v106; // rcx
  void *v107; // rsi
  unsigned int v108; // ebx
  HLOCAL v109; // rax
  void *v110; // rdi
  __int64 v111; // rcx
  __int64 v112; // rcx
  unsigned int v113; // esi
  HLOCAL v114; // rax
  void *v115; // rdi
  __int64 v116; // rdx
  __int64 v117; // rcx
  __int64 v118; // r8
  __int64 v119; // r9
  int v120; // eax
  __int64 v121; // rcx
  unsigned int v122; // esi
  HLOCAL v123; // rax
  void *v124; // rdi
  __int64 v125; // rdx
  __int64 v126; // rcx
  __int64 v127; // r8
  __int64 v128; // r9
  int v129; // eax
  __int64 v130; // rcx
  char *v131; // rax
  __int64 v132; // rdx
  __int64 v133; // rcx
  __int64 v134; // r8
  __int64 v135; // r9
  char *v136; // rdi
  __int64 v137; // rsi
  unsigned int *v138; // r12
  const void **v139; // r14
  unsigned int v140; // r8d
  __int64 v141; // rax
  HLOCAL v142; // rdi
  __int64 v143; // rdx
  __int64 v144; // rcx
  __int64 v145; // r8
  __int64 v146; // r9
  int v147; // eax
  __int64 v148; // rcx
  unsigned int v149; // eax
  __int64 v150; // [rsp+28h] [rbp-D8h]
  SIZE_T uBytes; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h]
  unsigned int v154; // [rsp+48h] [rbp-B8h]
  unsigned int v155; // [rsp+4Ch] [rbp-B4h] BYREF
  int v156; // [rsp+50h] [rbp-B0h]
  HLOCAL v157; // [rsp+58h] [rbp-A8h]
  HLOCAL v158; // [rsp+60h] [rbp-A0h]
  size_t Size; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v160; // [rsp+70h] [rbp-90h] BYREF
  void *v161; // [rsp+78h] [rbp-88h]
  size_t v162; // [rsp+80h] [rbp-80h]
  void *Src; // [rsp+88h] [rbp-78h]
  size_t v164; // [rsp+90h] [rbp-70h]
  void *v165; // [rsp+98h] [rbp-68h]
  void *v166; // [rsp+A0h] [rbp-60h]
  size_t v167; // [rsp+A8h] [rbp-58h]
  void *v168; // [rsp+B0h] [rbp-50h]
  size_t v169; // [rsp+B8h] [rbp-48h]
  size_t v170; // [rsp+C0h] [rbp-40h]
  void *v171; // [rsp+C8h] [rbp-38h]
  size_t v172; // [rsp+D0h] [rbp-30h]
  void *v173; // [rsp+D8h] [rbp-28h]
  size_t v174; // [rsp+E0h] [rbp-20h]
  unsigned int v175[2]; // [rsp+E8h] [rbp-18h]
  unsigned __int8 *v176; // [rsp+F0h] [rbp-10h]
  struct RDP_SERVER_REDIRECTION_PACKET *v177; // [rsp+F8h] [rbp-8h]
  __int64 v178; // [rsp+100h] [rbp+0h]
  int *v179; // [rsp+108h] [rbp+8h]
  unsigned __int16 v180[64]; // [rsp+110h] [rbp+10h] BYREF

  v4 = *((unsigned __int16 *)a2 + 1);
  v5 = a3;
  v179 = a4;
  v177 = a2;
  v7 = (CCO *)this;
  hMem = 0;
  v158 = 0;
  v155 = 0;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(this, a2, a3, a4);
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      186,
      &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
      ActivityIdPrefix);
  }
  v9 = *((_QWORD *)v7 + 50);
  LODWORD(uBytes) = 1;
  v12 = (*(__int64 (__fastcall **)(__int64, const char *, SIZE_T *))(*(_QWORD *)v9 + 120LL))(
          v9,
          "EnableServerRedirectionPduProcessing",
          &uBytes);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpX_GetActivityIdPrefix(v11, v10, v13, v14);
      v16 = 187;
      v17 = "Failed to get TS_PROP_CORE_ENABLE_SERVER_REDIRECTION_PDU_PROCESSING!";
LABEL_10:
      LODWORD(v150) = v12;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
        v15,
        (__int64)v17,
        v150);
      goto LABEL_11;
    }
    goto LABEL_11;
  }
  if ( !(_DWORD)uBytes )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = RdpX_GetActivityIdPrefix(v11, v10, v13, v14);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 188, &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids, v21);
    }
    v12 = -1626191425;
    goto LABEL_13;
  }
  v11 = *((_QWORD *)v7 + 35);
  if ( v11 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v11 + 24LL))(v11) )
    (*(void (__fastcall **)(_QWORD, struct RDP_SERVER_REDIRECTION_PACKET *, _QWORD))(**((_QWORD **)v7 + 35) + 112LL))(
      *((_QWORD *)v7 + 35),
      a2,
      v5);
  v22 = *((unsigned __int16 *)a2 + 1);
  if ( v5 < (unsigned int)v22 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 189, &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids);
    }
    v12 = -1626322483;
    goto LABEL_13;
  }
  v157 = 0;
  if ( (*(_WORD *)a2 & 0x100) != 0 )
  {
    v23 = v22 - 10;
    if ( (unsigned __int64)(v22 - 10) >= 0x80 )
    {
      v23 = 128;
LABEL_43:
      memcpy_0(v180, (char *)a2 + 8, v23);
      CTSConnectionHandler::SetServerRedirectionInfo(
        *((CTSConnectionHandler **)v7 + 36),
        *((_DWORD *)a2 + 1),
        v180,
        0,
        0,
        1);
      goto LABEL_336;
    }
    if ( (unsigned int)(v22 - 11) <= 0x7F )
      goto LABEL_43;
LABEL_336:
    CoreFSM::Disconnect(*((CoreFSM **)v7 + 31), 0);
    *v179 = 1;
    goto LABEL_18;
  }
  v24 = (unsigned __int8 *)a2 + v4;
  if ( (*(_WORD *)a2 & 0x200) != 0 )
  {
    v25 = *((_DWORD *)a2 + 2);
    v26 = (unsigned __int8 *)a2 + 12;
    if ( (v25 & 1) != 0 )
    {
      if ( !(unsigned int)CheckReadNBytes((unsigned __int8 *)a2 + 12, v24, 4u, L"can not read TARGET_NET_ADDRESSsize") )
      {
        v12 = -1626322452;
LABEL_13:
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v18 = RdpX_GetActivityIdPrefix(v11, v10, v13, v14);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 220, &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids, v18);
        }
        CCO::DropLinkImmediate(v7, 0xD06u);
LABEL_18:
        v19 = hMem;
        if ( !hMem )
          goto LABEL_20;
        goto LABEL_19;
      }
      v27 = *(unsigned int *)v26;
      v28 = (char *)a2 + 16;
      if ( !(unsigned int)CheckReadNBytes((unsigned __int8 *)a2 + 16, v24, v27, L"can not read TARGET_NET_ADDRESS") )
      {
        v12 = -1626322452;
LABEL_12:
        v7 = (CCO *)this;
        goto LABEL_13;
      }
      v26 = (unsigned __int8 *)a2 + v27 + 16;
    }
    else
    {
      v28 = 0;
      LODWORD(v27) = 0;
    }
    if ( (v25 & 2) != 0 )
    {
      if ( !(unsigned int)CheckReadNBytes(v26, v24, 4u, L"can not read LOAD_BALANCE_INFOsize")
        || (v29 = *(_DWORD *)v26,
            v30 = v26 + 4,
            !(unsigned int)CheckReadNBytes(v30, v24, v29, L"can not read LOAD_BALANCE_INFO")) )
      {
        v12 = -1626322447;
        goto LABEL_12;
      }
    }
    else
    {
      v30 = 0;
      v29 = 0;
    }
    if ( (unsigned int)(v27 - 1) > 0x7F )
    {
      v7 = (CCO *)this;
      Size = 0;
      (*(void (__fastcall **)(CTSConnectionHandler *, const char *, size_t *))(*(_QWORD *)this[50] + 128LL))(
        this[50],
        "ServerName",
        &Size);
      CTSConnectionHandler::SetServerRedirectionInfo(
        this[36],
        *((_DWORD *)a2 + 1),
        (const unsigned __int16 *)Size,
        v30,
        v29,
        1);
    }
    else
    {
      memcpy_0(v180, v28, (unsigned int)v27);
      v7 = (CCO *)this;
      CTSConnectionHandler::SetServerRedirectionInfo(this[36], *((_DWORD *)a2 + 1), v180, 0, 0, 1);
    }
    goto LABEL_336;
  }
  if ( (*(_WORD *)a2 & 0x400) == 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v149 = RdpX_GetActivityIdPrefix(256, v10, v13, v14);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 219, &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids, v149);
    }
    goto LABEL_336;
  }
  v31 = *((_DWORD *)a2 + 2);
  v32 = (unsigned __int8 *)a2 + 12;
  v156 = v31;
  if ( (v31 & 1) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes((unsigned __int8 *)a2 + 12, v24, 4u, L"can not read TARGET_NET_ADDRESSsize")
      || (v33 = *(unsigned int *)v32,
          v174 = v33,
          v160 = (unsigned __int16 *)((char *)a2 + 16),
          !(unsigned int)CheckReadNBytes((unsigned __int8 *)a2 + 16, v24, v33, L"can not read TARGET_NET_ADDRESS")) )
    {
      v12 = -1626322387;
      goto LABEL_12;
    }
    if ( (v33 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322386;
      goto LABEL_12;
    }
    v32 = (unsigned __int8 *)a2 + v33 + 16;
  }
  else
  {
    v160 = 0;
    LODWORD(v174) = 0;
  }
  if ( (v31 & 2) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v32, v24, 4u, L"can not read LOAD_BALANCE_INFOsize")
      || (v34 = *(unsigned int *)v32,
          *(_QWORD *)v175 = v34,
          v176 = v32 + 4,
          !(unsigned int)CheckReadNBytes(v32 + 4, v24, v34, L"can not read LOAD_BALANCE_INFO")) )
    {
      v12 = -1626322381;
      goto LABEL_12;
    }
    v32 += v34 + 4;
  }
  else
  {
    v176 = 0;
    v175[0] = 0;
  }
  if ( (v31 & 4) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v32, v24, 4u, L"can not read LB_USERNAMEsize")
      || (v35 = *(unsigned int *)v32,
          v36 = (__int64)(v32 + 4),
          Size = v35,
          Src = v32 + 4,
          !(unsigned int)CheckReadNBytes(v32 + 4, v24, v35, L"can not read LB_USERNAME")) )
    {
      v12 = -1626322376;
      goto LABEL_12;
    }
    if ( (v35 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322375;
      goto LABEL_12;
    }
    v32 += v35 + 4;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v37 = RdpX_GetActivityIdPrefix(v11, v10, v13, v14);
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        190,
        (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
        v37,
        v36);
    }
  }
  else
  {
    Src = 0;
    Size = 0;
  }
  if ( (v31 & 8) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v32, v24, 4u, L"can not read LB_DOMAINsize")
      || (v38 = *(unsigned int *)v32,
          v39 = (__int64)(v32 + 4),
          v164 = v38,
          v165 = v32 + 4,
          !(unsigned int)CheckReadNBytes(v32 + 4, v24, v38, L"can not read LB_DOMAIN")) )
    {
      v12 = -1626322368;
      goto LABEL_12;
    }
    if ( (v38 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322367;
      goto LABEL_12;
    }
    v32 += v38 + 4;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v40 = RdpX_GetActivityIdPrefix(v11, v10, v13, v14);
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        191,
        (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
        v40,
        v39);
    }
  }
  else
  {
    v165 = 0;
    LODWORD(v164) = 0;
  }
  if ( (v31 & 0x10) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v32, v24, 4u, L"can not read LB_PASSWORDsize")
      || (v41 = *(unsigned int *)v32,
          v162 = v41,
          v161 = v32 + 4,
          !(unsigned int)CheckReadNBytes(v32 + 4, v24, v41, L"can not read LB_PASSWORD")) )
    {
      v12 = -1626322360;
      goto LABEL_12;
    }
    if ( (v41 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322359;
      goto LABEL_12;
    }
    v32 += v41 + 4;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v42 = RdpX_GetActivityIdPrefix(v11, v10, v13, v14);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 192, &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids, v42);
    }
  }
  else
  {
    v161 = 0;
    v162 = 0;
  }
  if ( (v31 & 0x100) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v32, v24, 4u, L"can not read TARGET_FQDNsize")
      || (v43 = *(unsigned int *)v32,
          v44 = (__int64)(v32 + 4),
          v170 = v43,
          v171 = v32 + 4,
          !(unsigned int)CheckReadNBytes(v32 + 4, v24, v43, L"can not read TARGET_FQDN")) )
    {
      v12 = -1626322352;
      goto LABEL_12;
    }
    if ( (v43 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322351;
      goto LABEL_12;
    }
    v32 += v43 + 4;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v45 = RdpX_GetActivityIdPrefix(v11, v10, v13, v14);
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        193,
        (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
        v45,
        v44);
    }
  }
  else
  {
    v171 = 0;
    LODWORD(v170) = 0;
  }
  if ( (v31 & 0x200) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v32, v24, 4u, L"can not read TARGET_NETBIOS_NAMEsize")
      || (v46 = *(unsigned int *)v32,
          v47 = (__int64)(v32 + 4),
          v172 = v46,
          v173 = v32 + 4,
          !(unsigned int)CheckReadNBytes(v32 + 4, v24, v46, L"can not read TARGET_NETBIOS_NAME")) )
    {
      v12 = -1626322344;
      goto LABEL_12;
    }
    if ( (v46 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322343;
      goto LABEL_12;
    }
    v32 += v46 + 4;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v48 = RdpX_GetActivityIdPrefix(v11, v10, v13, v14);
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        194,
        (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
        v48,
        v47);
    }
  }
  else
  {
    v173 = 0;
    LODWORD(v172) = 0;
  }
  if ( (v31 & 0x1000) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v32, v24, 4u, L"can not read LB_CLIENT_TSV_URLsize")
      || (v49 = *(unsigned int *)v32,
          v50 = v32 + 4,
          !(unsigned int)CheckReadNBytes(v32 + 4, v24, v49, L"can not read LB_CLIENT_TSV_URL")) )
    {
      v12 = -1626322328;
      goto LABEL_12;
    }
    if ( (v49 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322327;
      goto LABEL_12;
    }
    v32 += v49 + 4;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v51 = RdpX_GetActivityIdPrefix(v11, v10, v13, v14);
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        195,
        (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
        v51,
        (__int64)v50);
    }
  }
  else
  {
    v50 = 0;
    LODWORD(v49) = 0;
  }
  v12 = CCO::internalVerifyLBInfo((CCO *)this, (v31 >> 13) & 1, v50, v49);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = RdpX_GetActivityIdPrefix(v52, v10, v13, v14);
      v16 = 196;
      v17 = "internalVerifyLBInfo";
      goto LABEL_10;
    }
LABEL_11:
    v11 = 520093696;
    if ( (v12 & 0x1F000000) != 0x1F000000 )
      goto LABEL_18;
    goto LABEL_12;
  }
  if ( (v31 & 0x8000) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v32, v24, 4u, L"can not read LB_REDIRECTION_GUIDsize")
      || (v53 = *(unsigned int *)v32,
          v167 = v53,
          v166 = v32 + 4,
          !(unsigned int)CheckReadNBytes(v32 + 4, v24, v53, L"can not read LB_REDIRECTION_GUID")) )
    {
      v12 = -1626322315;
      goto LABEL_12;
    }
    if ( (v53 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322314;
      goto LABEL_12;
    }
    v32 += v53 + 4;
  }
  else
  {
    v166 = 0;
    LODWORD(v167) = 0;
  }
  if ( (v31 & 0x10000) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v32, v24, 4u, L"can not read LB_TARGET_CERTIFICATEsize")
      || (v54 = *(unsigned int *)v32,
          v169 = v54,
          v168 = v32 + 4,
          !(unsigned int)CheckReadNBytes(v32 + 4, v24, v54, L"can not read LB_TARGET_CERTIFICATE")) )
    {
      v12 = -1626322308;
      goto LABEL_12;
    }
    if ( (v54 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322307;
      goto LABEL_12;
    }
    v32 += v54 + 4;
  }
  else
  {
    v168 = 0;
    LODWORD(v169) = 0;
  }
  LODWORD(uBytes) = 0;
  if ( (v31 & 0x800) == 0 )
  {
    v79 = 0;
    goto LABEL_208;
  }
  if ( !(unsigned int)CheckReadNBytes(v32, v24, 4u, L"TARGET_NET_ADDRESSES - wrong size") )
  {
    v12 = -1626322288;
    goto LABEL_12;
  }
  v55 = (unsigned int *)(v32 + 4);
  if ( !(unsigned int)CheckReadNBytes(
                        v32 + 4,
                        v24,
                        *(unsigned int *)v32,
                        L"TARGET_NET_ADDRESSES - wrong total bytes size") )
  {
    v12 = -1626322278;
    goto LABEL_12;
  }
  if ( !(unsigned int)CheckReadNBytes(
                        v32 + 4,
                        v24,
                        4u,
                        L"TARGET_NET_ADDRESSES - wrong size while getting number of addresses") )
  {
    v12 = -1626322272;
    goto LABEL_12;
  }
  v56 = *v55;
  v154 = v56;
  if ( (unsigned int)v56 > 0x19 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v57 = RdpX_GetActivityIdPrefix(v11, v10, v13, v14);
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids, v57, v56);
    }
    return (unsigned int)-2147467259;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v58 = RdpX_GetActivityIdPrefix(v11, v10, v13, v14);
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids, v58, v56);
  }
  hMem = LocalAlloc(0x40u, 8 * v56);
  if ( hMem )
  {
    v158 = LocalAlloc(0x40u, 4 * v56);
    v67 = v158;
    if ( !v158 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v68 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v64, v65, v66);
        v69 = 200;
        v70 = "pServerIpAddressLengths";
LABEL_191:
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v69,
          (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
          v68,
          (__int64)v70);
        goto LABEL_192;
      }
      goto LABEL_192;
    }
    v71 = (unsigned __int8 *)(v55 + 1);
    v72 = 0;
    if ( v154 )
    {
      while ( (unsigned int)CheckReadNBytes(v71, v24, 4u, L"can not read TARGET_NET_ADDRESS_IPV6V4_LIST Addressessize") )
      {
        v67[v72] = *(_DWORD *)v71;
        *((_QWORD *)hMem + v72) = v71 + 4;
        if ( !(unsigned int)CheckReadNBytes(
                              v71 + 4,
                              v24,
                              (unsigned int)v67[v72],
                              L"can not read TARGET_NET_ADDRESS_IPV6V4_LIST Addresses") )
          break;
        v73 = (unsigned int)v67[v72];
        v74 = *((_QWORD *)hMem + v72);
        if ( *(_BYTE *)((unsigned int)(v73 - 1) + v74) || *(_BYTE *)((unsigned int)(v73 - 2) + v74) )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v84 = RdpX_GetActivityIdPrefix(v11, v73, v13, v14);
            v85 = 201;
LABEL_216:
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v85, &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids, v84);
          }
LABEL_217:
          v12 = -2147467259;
          goto LABEL_193;
        }
        v75 = (unsigned int)v73;
        v178 = v73;
        v76 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          RdpX_GetActivityIdPrefix(v11, v73, (unsigned int)v73, v14);
          WPP_SF_DdS(*((_QWORD *)WPP_GLOBAL_Control + 2), v72, v74);
          v76 = WPP_GLOBAL_Control;
          v75 = v178;
        }
        v67 = v158;
        v77 = *((unsigned int *)v158 + v72);
        v78 = (unsigned int)(v77 + uBytes);
        if ( (unsigned int)v78 < (unsigned int)uBytes || (unsigned int)v78 < (unsigned int)v77 )
        {
          if ( v76 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v76[7] & 1) != 0 && *((_BYTE *)v76 + 25) >= 2u )
          {
            v84 = RdpX_GetActivityIdPrefix(v78, v77, v75, (unsigned int)uBytes);
            v85 = 203;
            goto LABEL_216;
          }
          goto LABEL_217;
        }
        LODWORD(uBytes) = v77 + uBytes;
        v71 += v75 + 4;
        v72 = (unsigned int)(v72 + 1);
        if ( (unsigned int)v72 >= v154 )
        {
          v31 = v156;
          goto LABEL_207;
        }
      }
      v12 = -1626322240;
      goto LABEL_12;
    }
LABEL_207:
    v79 = v154;
LABEL_208:
    v156 = v31 & 0x80;
    v80 = v156 == 0;
    if ( (_DWORD)Size )
    {
      v81 = Size;
      v82 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)Size + 2LL);
      v83 = v82;
      if ( v82 )
      {
        memcpy_0(v82, Src, v81);
        if ( (v31 & 0x20) != 0 )
          CTSConnectionHandler::SetRedirectionUserName(this[36], v83);
        else
          v12 = (*(__int64 (__fastcall **)(CTSConnectionHandler *, const char *, unsigned __int16 *, _QWORD))(*(_QWORD *)this[50] + 56LL))(
                  this[50],
                  "UserName",
                  v83,
                  0);
        LocalFree(v83);
        if ( v12 < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = RdpX_GetActivityIdPrefix(v86, v10, v13, v14);
            v16 = 204;
            v17 = "Set property for username";
            goto LABEL_10;
          }
          goto LABEL_11;
        }
      }
    }
    if ( (_DWORD)v164 )
    {
      v87 = v164;
      v88 = LocalAlloc(0x40u, (unsigned int)v164 + 2LL);
      v89 = v88;
      if ( v88 )
      {
        memcpy_0(v88, v165, v87);
        v12 = (*(__int64 (__fastcall **)(CTSConnectionHandler *, const char *, void *, _QWORD))(*(_QWORD *)this[50]
                                                                                              + 56LL))(
                this[50],
                "Domain",
                v89,
                0);
        LocalFree(v89);
        if ( v12 < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = RdpX_GetActivityIdPrefix(v90, v10, v13, v14);
            v16 = 205;
            v17 = "Set property for domain";
            goto LABEL_10;
          }
          goto LABEL_11;
        }
      }
    }
    if ( (_DWORD)v162 )
    {
      v91 = (unsigned int)v162;
      v92 = (unsigned int)v162 + 2LL;
      if ( v92 <= 0x800 )
      {
        v93 = LocalAlloc(0x40u, v92);
        v94 = v93;
        if ( (v31 & 0x4000) != 0 )
        {
          if ( v93 )
          {
            memcpy_0(v93, v161, (unsigned int)v91);
            v7 = (CCO *)this;
            v12 = (*(__int64 (__fastcall **)(CTSConnectionHandler *, const char *, void *, _QWORD))(*(_QWORD *)this[50]
                                                                                                  + 56LL))(
                    this[50],
                    "PKEncryptedPassword",
                    v94,
                    0);
            LocalFree(v94);
            if ( v12 < 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v15 = RdpX_GetActivityIdPrefix(v95, v10, v13, v14);
                v16 = 206;
                v17 = "Set property for PK-encrypted Password";
                goto LABEL_10;
              }
              goto LABEL_11;
            }
            goto LABEL_264;
          }
        }
        else if ( v93 )
        {
          memcpy_0(v93, v161, v91);
          v12 = (*(__int64 (__fastcall **)(CTSConnectionHandler *, const char *, void *, _QWORD))(*(_QWORD *)this[50]
                                                                                                + 64LL))(
                  this[50],
                  "Password",
                  v94,
                  0);
          v96 = v161;
          do
          {
            *v96++ = 0;
            --v91;
          }
          while ( v91 );
          v97 = v94;
          v98 = (unsigned int)(v162 + 2);
          if ( (_DWORD)v162 != -2 )
          {
            do
            {
              *v97++ = 0;
              --v98;
            }
            while ( v98 );
          }
          LocalFree(v94);
          if ( v12 < 0 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v15 = RdpX_GetActivityIdPrefix(v99, v10, v13, v14);
              v16 = 207;
              v17 = "Set property for Password";
              goto LABEL_10;
            }
            goto LABEL_11;
          }
          if ( (_DWORD)Size )
            (*(void (__fastcall **)(CTSConnectionHandler *, const char *, __int64))(*(_QWORD *)this[50] + 32LL))(
              this[50],
              "AutoLogon",
              1);
          v155 = (v31 >> 6) & 1;
          v12 = (*(__int64 (__fastcall **)(CTSConnectionHandler *, const char *, _QWORD))(*(_QWORD *)this[50] + 32LL))(
                  this[50],
                  "PasswordContainsSCardPin",
                  v155);
          if ( v12 < 0 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v15 = RdpX_GetActivityIdPrefix(v100, v10, v13, v14);
              v16 = 208;
              v17 = "Failed to set TS_PROP_CORE_PASSWORD_IS_SC_PIN!";
              goto LABEL_10;
            }
            goto LABEL_11;
          }
          v7 = (CCO *)this;
LABEL_270:
          v102 = v166;
          if ( v166 )
          {
            if ( (_DWORD)v167 )
            {
              v103 = v167;
              v104 = LocalAlloc(0x40u, (unsigned int)v167 + 2LL);
              v105 = v104;
              if ( v104 )
              {
                memcpy_0(v104, v102, v103);
                v12 = (*(__int64 (__fastcall **)(_QWORD, const char *, void *, _QWORD))(**((_QWORD **)v7 + 50) + 56LL))(
                        *((_QWORD *)v7 + 50),
                        "RedirectionGuid",
                        v105,
                        0);
                LocalFree(v105);
                if ( v12 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v15 = RdpX_GetActivityIdPrefix(v106, v10, v13, v14);
                    v16 = 210;
                    v17 = "Failed to set TS_PROP_REDIRECTION_GUID!";
                    goto LABEL_10;
                  }
                  goto LABEL_11;
                }
              }
            }
          }
          v107 = v168;
          if ( v168 )
          {
            if ( (_DWORD)v169 )
            {
              v108 = v169;
              v109 = LocalAlloc(0x40u, (unsigned int)v169 + 2LL);
              v110 = v109;
              if ( v109 )
              {
                memcpy_0(v109, v107, v108);
                v12 = (*(__int64 (__fastcall **)(_QWORD, const char *, void *, _QWORD))(**((_QWORD **)v7 + 50) + 56LL))(
                        *((_QWORD *)v7 + 50),
                        "TargetCertificate",
                        v110,
                        0);
                LocalFree(v110);
                if ( v12 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v15 = RdpX_GetActivityIdPrefix(v111, v10, v13, v14);
                    v16 = 211;
                    v17 = "Failed to set TS_PROP_REDIRECTION_TARGET_CERTIFICATE!";
                    goto LABEL_10;
                  }
                  goto LABEL_11;
                }
              }
            }
          }
          v12 = (*(__int64 (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)v7 + 50) + 32LL))(
                  *((_QWORD *)v7 + 50),
                  "RedirectionUseSCardLogon",
                  v155);
          if ( v12 < 0 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v15 = RdpX_GetActivityIdPrefix(v112, v10, v13, v14);
              v16 = 212;
              v17 = "Failed to set TS_PROP_REDIRECTION_USE_SCARD_LOGON!";
              goto LABEL_10;
            }
            goto LABEL_11;
          }
          if ( (_DWORD)v170 )
          {
            v113 = v170;
            v114 = LocalAlloc(0x40u, (unsigned int)v170 + 2LL);
            v115 = v114;
            if ( v114 )
            {
              memcpy_0(v114, v171, v113);
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v120 = RdpX_GetActivityIdPrefix(v117, v116, v118, v119);
                WPP_SF_DS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  213,
                  (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
                  v120,
                  (__int64)v115);
              }
              v12 = (*(__int64 (__fastcall **)(_QWORD, const char *, void *, _QWORD))(**((_QWORD **)v7 + 50) + 56LL))(
                      *((_QWORD *)v7 + 50),
                      "ServerFqdn",
                      v115,
                      0);
              LocalFree(v115);
              if ( v12 < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = RdpX_GetActivityIdPrefix(v121, v10, v13, v14);
                  v16 = 214;
                  v17 = "Set property for server FQDN";
                  goto LABEL_10;
                }
                goto LABEL_11;
              }
            }
          }
          if ( (_DWORD)v172 )
          {
            v122 = v172;
            v123 = LocalAlloc(0x40u, (unsigned int)v172 + 2LL);
            v124 = v123;
            if ( v123 )
            {
              memcpy_0(v123, v173, v122);
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v129 = RdpX_GetActivityIdPrefix(v126, v125, v127, v128);
                WPP_SF_DS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  215,
                  (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
                  v129,
                  (__int64)v124);
              }
              v12 = (*(__int64 (__fastcall **)(_QWORD, const char *, void *, _QWORD))(**((_QWORD **)v7 + 50) + 56LL))(
                      *((_QWORD *)v7 + 50),
                      "ServerNetBiosName",
                      v124,
                      0);
              LocalFree(v124);
              if ( v12 < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v15 = RdpX_GetActivityIdPrefix(v130, v10, v13, v14);
                  v16 = 216;
                  v17 = "Set property for server NetBios name";
                  goto LABEL_10;
                }
                goto LABEL_11;
              }
            }
          }
          if ( hMem && v79 )
          {
            v131 = (char *)LocalAlloc(0x40u, (unsigned int)uBytes);
            v136 = v131;
            if ( !v131 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v68 = RdpX_GetActivityIdPrefix(v133, v132, v134, v135);
                v69 = 217;
                v70 = "pAlignedServerIpAddresses";
                goto LABEL_191;
              }
LABEL_192:
              v12 = -2147024882;
LABEL_193:
              v19 = hMem;
LABEL_19:
              LocalFree(v19);
LABEL_20:
              if ( v158 )
                LocalFree(v158);
              return (unsigned int)v12;
            }
            v137 = 0;
            v157 = v131;
            v138 = (unsigned int *)v158;
            v139 = (const void **)hMem;
            do
            {
              memcpy_0(v136, v139[v137], v138[v137]);
              v141 = v138[v137];
              v137 = (unsigned int)(v137 + 1);
              v136 += v141;
            }
            while ( (unsigned int)v137 < v79 );
            v7 = (CCO *)this;
            v142 = v157;
            v12 = CTSConnectionHandler::SetServerAddressesToConnect(this[36], (unsigned __int16 *)v157, v140, v79);
            if ( v12 < 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v147 = RdpX_GetActivityIdPrefix(v144, v143, v145, v146);
                LODWORD(v150) = v12;
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  218,
                  (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
                  v147,
                  (__int64)"_spConnectionHandler->SetServerAddressesToConnect failed",
                  v150);
              }
              LocalFree(v142);
              goto LABEL_11;
            }
          }
          if ( (unsigned int)(v174 - 1) > 0x7F )
          {
            v148 = *((_QWORD *)v7 + 50);
            v160 = 0;
            (*(void (__fastcall **)(__int64, const char *, unsigned __int16 **))(*(_QWORD *)v148 + 128LL))(
              v148,
              "ServerName",
              &v160);
            CTSConnectionHandler::SetServerRedirectionInfo(
              *((CTSConnectionHandler **)v7 + 36),
              *((_DWORD *)v177 + 1),
              v160,
              v176,
              v175[0],
              v80);
          }
          else
          {
            memcpy_0(v180, v160, (unsigned int)v174);
            CTSConnectionHandler::SetServerRedirectionInfo(
              *((CTSConnectionHandler **)v7 + 36),
              *((_DWORD *)v177 + 1),
              v180,
              0,
              0,
              v80);
          }
          if ( v156 )
            goto LABEL_18;
          goto LABEL_336;
        }
      }
    }
    v7 = (CCO *)this;
LABEL_264:
    v12 = (*(__int64 (__fastcall **)(_QWORD, const char *, unsigned int *))(**((_QWORD **)v7 + 50) + 120LL))(
            *((_QWORD *)v7 + 50),
            "PasswordContainsSCardPin",
            &v155);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = RdpX_GetActivityIdPrefix(v101, v10, v13, v14);
        v16 = 209;
        v17 = "Failed to get TS_PROP_CORE_PASSWORD_IS_SC_PIN!";
        goto LABEL_10;
      }
      goto LABEL_11;
    }
    goto LABEL_270;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v63 = RdpX_GetActivityIdPrefix(v60, v59, v61, v62);
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      199,
      (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
      v63,
      (__int64)"pServerIpAddresses");
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x1801803dc  push    rbp
0x1801803de  push    rbx
0x1801803df  push    rsi
0x1801803e0  push    rdi
0x1801803e1  push    r12
0x1801803e3  push    r13
0x1801803e5  push    r14
0x1801803e7  push    r15
0x1801803e9  lea     rbp, [rsp-0A8h]
0x1801803f1  sub     rsp, 1A8h
0x1801803f8  mov     rax, cs:__security_cookie
0x1801803ff  xor     rax, rsp
0x180180402  mov     [rbp+0E0h+var_50], rax
0x180180409  movzx   esi, word ptr [rdx+2]
0x18018040d  mov     edi, r8d
0x180180410  mov     [rbp+0E0h+var_D8], r9
0x180180414  mov     r13, rdx
0x180180417  mov     [rbp+0E0h+var_E8], rdx
0x18018041b  mov     r12, rcx
0x18018041e  mov     [rsp+1E0h+var_1B0], rcx
0x180180423  mov     [rsp+1E0h+hMem], 0
0x18018042c  mov     [rsp+1E0h+var_180], 0
0x180180435  mov     [rsp+1E0h+var_194], 0
0x18018043d  mov     rax, cs:WPP_GLOBAL_Control
0x180180444  lea     r14, WPP_GLOBAL_Control
0x18018044b  lea     r15, WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids
0x180180452  cmp     rax, r14
0x180180455  jz      short loc_180180483
0x180180457  test    byte ptr [rax+1Ch], 1
0x18018045b  jz      short loc_180180483
0x18018045d  cmp     byte ptr [rax+19h], 4
0x180180461  jb      short loc_180180483
0x180180463  call    RdpX_GetActivityIdPrefix
0x180180468  mov     rcx, cs:WPP_GLOBAL_Control
0x18018046f  mov     edx, 0BAh
0x180180474  mov     r9d, eax
0x180180477  mov     r8, r15
0x18018047a  mov     rcx, [rcx+10h]
0x18018047e  call    WPP_SF_d
0x180180483  mov     rcx, [r12+190h]
0x18018048b  lea     r8, [rsp+1E0h+uBytes]
0x180180490  mov     dword ptr [rsp+1E0h+uBytes], 1
0x180180498  lea     rdx, aEnableserverre; "EnableServerRedirectionPduProcessing"
0x18018049f  mov     rax, [rcx]
0x1801804a2  mov     rax, [rax+78h]
0x1801804a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801804ab  mov     ebx, eax
0x1801804ad  test    eax, eax
0x1801804af  jns     loc_1801805AA
0x1801804b5  mov     rax, cs:WPP_GLOBAL_Control
0x1801804bc  cmp     rax, r14
0x1801804bf  jz      short loc_180180500
0x1801804c1  mov     r14b, 8
0x1801804c4  test    [rax+1Ch], r14b
0x1801804c8  jz      short loc_180180500
0x1801804ca  cmp     byte ptr [rax+19h], 2
0x1801804ce  jb      short loc_180180500
0x1801804d0  call    RdpX_GetActivityIdPrefix
0x1801804d5  mov     edx, 0BBh
0x1801804da  lea     rcx, aFailedToGetTsP_0; "Failed to get TS_PROP_CORE_ENABLE_SERVE"...
0x1801804e1  mov     r8, r15
0x1801804e4  mov     dword ptr [rsp+1E0h+var_1B8], ebx
0x1801804e8  mov     r9d, eax
0x1801804eb  mov     qword ptr [rsp+1E0h+var_1C0], rcx
0x1801804f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1801804f7  mov     rcx, [rcx+10h]
0x1801804fb  call    WPP_SF_DsD
0x180180500  lea     rsi, WPP_GLOBAL_Control
0x180180507  mov     ecx, 1F000000h
0x18018050c  mov     eax, ebx
0x18018050e  and     eax, ecx
0x180180510  cmp     eax, ecx
0x180180512  jnz     short loc_180180562
0x180180514  mov     r12, [rsp+1E0h+var_1B0]
0x180180519  mov     rax, cs:WPP_GLOBAL_Control
0x180180520  cmp     rax, rsi
0x180180523  jz      short loc_180180555
0x180180525  test    byte ptr [rax+1Ch], 1
0x180180529  jz      short loc_180180555
0x18018052b  cmp     byte ptr [rax+19h], 2
0x18018052f  jb      short loc_180180555
0x180180531  call    RdpX_GetActivityIdPrefix
0x180180536  mov     rcx, cs:WPP_GLOBAL_Control
0x18018053d  lea     r8, WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids
0x180180544  mov     edx, 0DCh
0x180180549  mov     r9d, eax
0x18018054c  mov     rcx, [rcx+10h]
0x180180550  call    WPP_SF_d
0x180180555  mov     edx, 0D06h; unsigned int
0x18018055a  mov     rcx, r12; this
0x18018055d  call    ?DropLinkImmediate@CCO@@UEAAJK@Z; CCO::DropLinkImmediate(ulong)
0x180180562  mov     rcx, [rsp+1E0h+hMem]; hMem
0x180180567  test    rcx, rcx
0x18018056a  jz      short loc_180180572
0x18018056c  call    cs:__imp_LocalFree
0x180180572  mov     rax, [rsp+1E0h+var_180]
0x180180577  test    rax, rax
0x18018057a  jz      short loc_180180585
0x18018057c  mov     rcx, rax; hMem
0x18018057f  call    cs:__imp_LocalFree
0x180180585  mov     eax, ebx
0x180180587  mov     rcx, [rbp+0E0h+var_50]
0x18018058e  xor     rcx, rsp; StackCookie
0x180180591  call    __security_check_cookie
0x180180596  add     rsp, 1A8h
0x18018059d  pop     r15
0x18018059f  pop     r14
0x1801805a1  pop     r13
0x1801805a3  pop     r12
0x1801805a5  pop     rdi
0x1801805a6  pop     rsi
0x1801805a7  pop     rbx
0x1801805a8  pop     rbp
0x1801805a9  retn
0x1801805aa  cmp     dword ptr [rsp+1E0h+uBytes], 0
0x1801805af  jnz     short loc_1801805FA
0x1801805b1  mov     rax, cs:WPP_GLOBAL_Control
0x1801805b8  cmp     rax, r14
0x1801805bb  jz      short loc_1801805E9
0x1801805bd  test    byte ptr [rax+1Ch], 1
0x1801805c1  jz      short loc_1801805E9
0x1801805c3  cmp     byte ptr [rax+19h], 2
0x1801805c7  jb      short loc_1801805E9
0x1801805c9  call    RdpX_GetActivityIdPrefix
0x1801805ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1801805d5  mov     edx, 0BCh
0x1801805da  mov     r9d, eax
0x1801805dd  mov     r8, r15
0x1801805e0  mov     rcx, [rcx+10h]
0x1801805e4  call    WPP_SF_d
0x1801805e9  mov     ebx, 9F1249BFh
0x1801805ee  lea     rsi, WPP_GLOBAL_Control
0x1801805f5  jmp     loc_180180519
0x1801805fa  mov     rcx, [r12+118h]
0x180180602  test    rcx, rcx
0x180180605  jz      short loc_180180631
0x180180607  mov     rax, [rcx]
0x18018060a  mov     rax, [rax+18h]
0x18018060e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180180613  test    eax, eax
0x180180615  jz      short loc_180180631
0x180180617  mov     rcx, [r12+118h]
0x18018061f  mov     r8d, edi
0x180180622  mov     rdx, r13
0x180180625  mov     rax, [rcx]
0x180180628  mov     rax, [rax+70h]
0x18018062c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180180631  movzx   eax, word ptr [r13+2]
0x180180636  cmp     edi, eax
0x180180638  jnb     short loc_18018066A
0x18018063a  mov     rax, cs:WPP_GLOBAL_Control
0x180180641  cmp     rax, r14
0x180180644  jz      short loc_180180663
0x180180646  test    byte ptr [rax+1Ch], 1
0x18018064a  jz      short loc_180180663
0x18018064c  cmp     byte ptr [rax+19h], 1
0x180180650  jb      short loc_180180663
0x180180652  mov     rcx, [rax+10h]
0x180180656  mov     edx, 0BDh
0x18018065b  mov     r8, r15
0x18018065e  call    WPP_SF_
0x180180663  mov     ebx, 9F1049CDh
0x180180668  jmp     short loc_1801805EE
0x18018066a  xor     edi, edi
0x18018066c  mov     ecx, 100h
0x180180671  mov     [rsp+1E0h+var_188], rdi
0x180180676  test    [r13+0], cx
0x18018067b  jz      short loc_1801806D6
0x18018067d  lea     rcx, [rax-0Ah]
0x180180681  cmp     rcx, 80h
0x180180688  jnb     short loc_180180698
0x18018068a  lea     eax, [rcx-1]
0x18018068d  cmp     eax, 7Fh
0x180180690  ja      loc_180181D72
0x180180696  jmp     short loc_18018069D
0x180180698  mov     ecx, 80h
0x18018069d  mov     r8d, ecx; Size
0x1801806a0  lea     rdx, [r13+8]; Src
0x1801806a4  lea     rcx, [rbp+0E0h+var_D0]; void *
0x1801806a8  call    memcpy_0
0x1801806ad  mov     edx, [r13+4]; unsigned int
0x1801806b1  lea     r8, [rbp+0E0h+var_D0]; unsigned __int16 *
0x1801806b5  mov     rcx, [r12+120h]; this
0x1801806bd  xor     r9d, r9d; unsigned __int8 *
0x1801806c0  mov     dword ptr [rsp+1E0h+var_1B8], 1; int
0x1801806c8  mov     dword ptr [rsp+1E0h+var_1C0], edi; unsigned int
0x1801806cc  call    ?SetServerRedirectionInfo@CTSConnectionHandler@@QEAAJIPEBGPEAEIH@Z; CTSConnectionHandler::SetServerRedirectionInfo(uint,ushort const *,uchar *,uint,int)
0x1801806d1  jmp     loc_180181D72
0x1801806d6  add     rsi, r13
0x1801806d9  mov     eax, 200h
0x1801806de  test    [r13+0], ax
0x1801806e3  jz      loc_180180844
0x1801806e9  mov     r15d, [r13+8]
0x1801806ed  lea     rdi, [r13+0Ch]
0x1801806f1  test    r15b, 1
0x1801806f5  jz      short loc_180180757
0x1801806f7  lea     r9, aCanNotReadTarg_6; "can not read TARGET_NET_ADDRESSsize"
0x1801806fe  mov     r8d, 4; unsigned __int64
0x180180704  mov     rdx, rsi; unsigned __int8 *
0x180180707  mov     rcx, rdi; unsigned __int8 *
0x18018070a  call    ?CheckReadNBytes@@YAHPEAE0_KPEBG@Z; CheckReadNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18018070f  test    eax, eax
0x180180711  jnz     short loc_18018071D
0x180180713  mov     ebx, 9F1049ECh
0x180180718  jmp     loc_1801805EE
0x18018071d  mov     r14d, [rdi]
0x180180720  lea     r12, [rdi+4]
0x180180724  mov     r8d, r14d; unsigned __int64
0x180180727  lea     r9, aCanNotReadTarg_4; "can not read TARGET_NET_ADDRESS"
0x18018072e  mov     rcx, r12; unsigned __int8 *
0x180180731  mov     rdx, rsi; unsigned __int8 *
0x180180734  call    ?CheckReadNBytes@@YAHPEAE0_KPEBG@Z; CheckReadNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x180180739  test    eax, eax
0x18018073b  jnz     short loc_18018074E
0x18018073d  mov     ebx, 9F1049ECh
0x180180742  lea     rsi, WPP_GLOBAL_Control
0x180180749  jmp     loc_180180514
0x18018074e  add     rdi, 4
0x180180752  add     rdi, r14
0x180180755  jmp     short loc_18018075D
0x180180757  xor     r12d, r12d
0x18018075a  xor     r14d, r14d
0x18018075d  test    r15b, 2
0x180180761  jz      short loc_1801807A8
0x180180763  lea     r9, aCanNotReadLoad_0; "can not read LOAD_BALANCE_INFOsize"
0x18018076a  mov     r8d, 4; unsigned __int64
0x180180770  mov     rdx, rsi; unsigned __int8 *
0x180180773  mov     rcx, rdi; unsigned __int8 *
0x180180776  call    ?CheckReadNBytes@@YAHPEAE0_KPEBG@Z; CheckReadNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18018077b  test    eax, eax
0x18018077d  jnz     short loc_180180786
0x18018077f  mov     ebx, 9F1049F1h
0x180180784  jmp     short loc_180180742
0x180180786  mov     r15d, [rdi]
0x180180789  lea     r9, aCanNotReadLoad; "can not read LOAD_BALANCE_INFO"
0x180180790  add     rdi, 4
0x180180794  mov     r8d, r15d; unsigned __int64
0x180180797  mov     rcx, rdi; unsigned __int8 *
0x18018079a  mov     rdx, rsi; unsigned __int8 *
0x18018079d  call    ?CheckReadNBytes@@YAHPEAE0_KPEBG@Z; CheckReadNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x1801807a2  test    eax, eax
0x1801807a4  jnz     short loc_1801807AD
0x1801807a6  jmp     short loc_18018077F
0x1801807a8  xor     edi, edi
0x1801807aa  xor     r15d, r15d
0x1801807ad  lea     eax, [r14-1]
0x1801807b1  cmp     eax, 7Fh
0x1801807b4  ja      short loc_1801807FC
0x1801807b6  mov     r8d, r14d; Size
0x1801807b9  lea     rcx, [rbp+0E0h+var_D0]; void *
0x1801807bd  mov     rdx, r12; Src
0x1801807c0  call    memcpy_0
0x1801807c5  mov     r12, [rsp+1E0h+var_1B0]
0x1801807ca  lea     r8, [rbp+0E0h+var_D0]; unsigned __int16 *
0x1801807ce  mov     dword ptr [rsp+1E0h+var_1B8], 1; int
0x1801807d6  xor     r9d, r9d; unsigned __int8 *
0x1801807d9  mov     dword ptr [rsp+1E0h+var_1C0], 0; unsigned int
0x1801807e1  mov     edx, [r13+4]; unsigned int
0x1801807e5  mov     rcx, [r12+120h]; this
0x1801807ed  call    ?SetServerRedirectionInfo@CTSConnectionHandler@@QEAAJIPEBGPEAEIH@Z; CTSConnectionHandler::SetServerRedirectionInfo(uint,ushort const *,uchar *,uint,int)
0x1801807f2  mov     rdi, [rsp+1E0h+var_188]
0x1801807f7  jmp     loc_180181D72
0x1801807fc  mov     r12, [rsp+1E0h+var_1B0]
0x180180801  lea     r8, [rsp+1E0h+Size]
0x180180806  mov     [rsp+1E0h+Size], 0
0x18018080f  lea     rdx, aServername; "ServerName"
0x180180816  mov     rcx, [r12+190h]
0x18018081e  mov     rax, [rcx]
0x180180821  mov     rax, [rax+80h]
0x180180828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018082d  mov     r8, [rsp+1E0h+Size]
0x180180832  mov     r9, rdi
0x180180835  mov     dword ptr [rsp+1E0h+var_1B8], 1
0x18018083d  mov     dword ptr [rsp+1E0h+var_1C0], r15d
0x180180842  jmp     short loc_1801807E1
0x180180844  mov     eax, 400h
0x180180849  test    [r13+0], ax
0x18018084e  jz      loc_180181D3A
0x180180854  mov     r12d, [r13+8]
0x180180858  lea     rdi, [r13+0Ch]
0x18018085c  mov     [rsp+1E0h+var_190], r12d
0x180180861  test    r12b, 1
0x180180865  jz      short loc_1801808D9
0x180180867  lea     r9, aCanNotReadTarg_6; "can not read TARGET_NET_ADDRESSsize"
0x18018086e  mov     r8d, 4; unsigned __int64
0x180180874  mov     rdx, rsi; unsigned __int8 *
0x180180877  mov     rcx, rdi; unsigned __int8 *
0x18018087a  call    ?CheckReadNBytes@@YAHPEAE0_KPEBG@Z; CheckReadNBytes(uchar *,uchar *,unsigned __int64,ushort const *)
0x18018087f  test    eax, eax
0x180180881  jnz     short loc_18018088D
0x180180883  mov     ebx, 9F104A2Dh
0x180180888  jmp     loc_180180742
0x18018088d  mov     ebx, [rdi]
0x18018088f  lea     r14, [rdi+4]
0x180180893  mov     r8d, ebx; unsigned __int64
0x180180896  mov     [rbp+0E0h+var_100], rbx
0x18018089a  mov     rcx, r14; unsigned __int8 *
0x18018089d  mov     [rsp+1E0h+var_170], r14
0x1801808a2  lea     r9, aCanNotReadTarg_4; "can not read TARGET_NET_ADDRESS"
0x1801808a9  mov     rdx, rsi; unsigned __int8 *
  ... truncated ...
```
