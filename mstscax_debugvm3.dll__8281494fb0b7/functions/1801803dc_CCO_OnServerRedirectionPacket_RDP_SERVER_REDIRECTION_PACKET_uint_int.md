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
  int v14; // eax
  int v15; // edx
  const char *v16; // rcx
  unsigned int v17; // eax
  HLOCAL v18; // rcx
  unsigned int v20; // eax
  __int64 v21; // rax
  unsigned int v22; // ecx
  unsigned __int8 *v23; // rsi
  int v24; // r15d
  unsigned __int8 *v25; // rdi
  unsigned __int64 v26; // r14
  char *v27; // r12
  unsigned int v28; // r15d
  unsigned __int8 *v29; // rdi
  unsigned int v30; // r12d
  unsigned __int8 *v31; // rdi
  size_t v32; // rbx
  unsigned __int64 v33; // rbx
  size_t v34; // r15
  __int64 v35; // rbx
  int v36; // eax
  size_t v37; // rbx
  __int64 v38; // r15
  int v39; // eax
  size_t v40; // rbx
  unsigned int v41; // eax
  size_t v42; // rbx
  __int64 v43; // r15
  int v44; // eax
  size_t v45; // rbx
  __int64 v46; // r15
  int v47; // eax
  unsigned __int64 v48; // rbx
  unsigned __int8 *v49; // r15
  int v50; // eax
  __int64 v51; // rcx
  size_t v52; // r15
  size_t v53; // r15
  unsigned int *v54; // r15
  __int64 v55; // rdi
  unsigned int v56; // eax
  unsigned int v57; // eax
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // r8
  int v61; // eax
  __int64 v62; // rdx
  __int64 v63; // r8
  _DWORD *v64; // rdi
  int v65; // eax
  int v66; // edx
  const char *v67; // rcx
  unsigned __int8 *v68; // r15
  __int64 v69; // r13
  __int64 v70; // rdx
  __int64 v71; // rdi
  __int64 v72; // r8
  HKEY v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rcx
  unsigned int v76; // r15d
  BOOL v77; // r13d
  unsigned int v78; // esi
  unsigned __int16 *v79; // rax
  unsigned __int16 *v80; // rdi
  unsigned int v81; // eax
  __int64 v82; // rdx
  __int64 v83; // rcx
  unsigned int v84; // ebx
  HLOCAL v85; // rax
  void *v86; // rdi
  __int64 v87; // rcx
  size_t v88; // rdi
  SIZE_T v89; // rdx
  HLOCAL v90; // rax
  void *v91; // rsi
  __int64 v92; // rcx
  _BYTE *v93; // rax
  _BYTE *v94; // rax
  __int64 v95; // rcx
  __int64 v96; // rcx
  __int64 v97; // rcx
  __int64 v98; // rcx
  void *v99; // rsi
  unsigned int v100; // ebx
  HLOCAL v101; // rax
  void *v102; // rdi
  __int64 v103; // rcx
  void *v104; // rsi
  unsigned int v105; // ebx
  HLOCAL v106; // rax
  void *v107; // rdi
  __int64 v108; // rcx
  __int64 v109; // rcx
  unsigned int v110; // esi
  HLOCAL v111; // rax
  void *v112; // rdi
  __int64 v113; // rdx
  __int64 v114; // rcx
  __int64 v115; // r8
  int v116; // eax
  __int64 v117; // rcx
  unsigned int v118; // esi
  HLOCAL v119; // rax
  void *v120; // rdi
  __int64 v121; // rdx
  __int64 v122; // rcx
  __int64 v123; // r8
  int v124; // eax
  __int64 v125; // rcx
  char *v126; // rax
  __int64 v127; // rdx
  __int64 v128; // rcx
  __int64 v129; // r8
  char *v130; // rdi
  __int64 v131; // rsi
  unsigned int *v132; // r12
  const void **v133; // r14
  unsigned int v134; // r8d
  __int64 v135; // rax
  HLOCAL v136; // rdi
  __int64 v137; // rdx
  __int64 v138; // rcx
  __int64 v139; // r8
  int v140; // eax
  __int64 v141; // rcx
  unsigned int v142; // eax
  SIZE_T uBytes; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h]
  unsigned int v146; // [rsp+48h] [rbp-B8h]
  unsigned int v147; // [rsp+4Ch] [rbp-B4h] BYREF
  int v148; // [rsp+50h] [rbp-B0h]
  HLOCAL v149; // [rsp+58h] [rbp-A8h]
  HLOCAL v150; // [rsp+60h] [rbp-A0h]
  size_t Size; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v152; // [rsp+70h] [rbp-90h] BYREF
  void *v153; // [rsp+78h] [rbp-88h]
  size_t v154; // [rsp+80h] [rbp-80h]
  void *Src; // [rsp+88h] [rbp-78h]
  size_t v156; // [rsp+90h] [rbp-70h]
  void *v157; // [rsp+98h] [rbp-68h]
  void *v158; // [rsp+A0h] [rbp-60h]
  size_t v159; // [rsp+A8h] [rbp-58h]
  void *v160; // [rsp+B0h] [rbp-50h]
  size_t v161; // [rsp+B8h] [rbp-48h]
  size_t v162; // [rsp+C0h] [rbp-40h]
  void *v163; // [rsp+C8h] [rbp-38h]
  size_t v164; // [rsp+D0h] [rbp-30h]
  void *v165; // [rsp+D8h] [rbp-28h]
  size_t v166; // [rsp+E0h] [rbp-20h]
  unsigned int v167[2]; // [rsp+E8h] [rbp-18h]
  unsigned __int8 *v168; // [rsp+F0h] [rbp-10h]
  struct RDP_SERVER_REDIRECTION_PACKET *v169; // [rsp+F8h] [rbp-8h]
  __int64 v170; // [rsp+100h] [rbp+0h]
  int *v171; // [rsp+108h] [rbp+8h]
  unsigned __int16 v172[64]; // [rsp+110h] [rbp+10h] BYREF

  v4 = *((unsigned __int16 *)a2 + 1);
  v5 = a3;
  v171 = a4;
  v169 = a2;
  v7 = (CCO *)this;
  hMem = 0;
  v150 = 0;
  v147 = 0;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(this, a2, a3);
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
      v14 = RdpX_GetActivityIdPrefix(v11, v10, v13);
      v15 = 187;
      v16 = "Failed to get TS_PROP_CORE_ENABLE_SERVER_REDIRECTION_PDU_PROCESSING!";
LABEL_10:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
        v14,
        (__int64)v16,
        v12);
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
      v20 = RdpX_GetActivityIdPrefix(v11, v10, v13);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 188, &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids, v20);
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
  v21 = *((unsigned __int16 *)a2 + 1);
  if ( v5 < (unsigned int)v21 )
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
  v149 = 0;
  if ( (*(_WORD *)a2 & 0x100) != 0 )
  {
    v22 = v21 - 10;
    if ( (unsigned __int64)(v21 - 10) >= 0x80 )
    {
      v22 = 128;
LABEL_43:
      memcpy_0(v172, (char *)a2 + 8, v22);
      CTSConnectionHandler::SetServerRedirectionInfo(
        *((CTSConnectionHandler **)v7 + 36),
        *((_DWORD *)a2 + 1),
        v172,
        0,
        0,
        1);
      goto LABEL_336;
    }
    if ( (unsigned int)(v21 - 11) <= 0x7F )
      goto LABEL_43;
LABEL_336:
    CoreFSM::Disconnect(*((CoreFSM **)v7 + 31), 0);
    *v171 = 1;
    goto LABEL_18;
  }
  v23 = (unsigned __int8 *)a2 + v4;
  if ( (*(_WORD *)a2 & 0x200) != 0 )
  {
    v24 = *((_DWORD *)a2 + 2);
    v25 = (unsigned __int8 *)a2 + 12;
    if ( (v24 & 1) != 0 )
    {
      if ( !(unsigned int)CheckReadNBytes((unsigned __int8 *)a2 + 12, v23, 4u, L"can not read TARGET_NET_ADDRESSsize") )
      {
        v12 = -1626322452;
LABEL_13:
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v17 = RdpX_GetActivityIdPrefix(v11, v10, v13);
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 220, &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids, v17);
        }
        CCO::DropLinkImmediate(v7, 0xD06u);
LABEL_18:
        v18 = hMem;
        if ( !hMem )
          goto LABEL_20;
        goto LABEL_19;
      }
      v26 = *(unsigned int *)v25;
      v27 = (char *)a2 + 16;
      if ( !(unsigned int)CheckReadNBytes((unsigned __int8 *)a2 + 16, v23, v26, L"can not read TARGET_NET_ADDRESS") )
      {
        v12 = -1626322452;
LABEL_12:
        v7 = (CCO *)this;
        goto LABEL_13;
      }
      v25 = (unsigned __int8 *)a2 + v26 + 16;
    }
    else
    {
      v27 = 0;
      LODWORD(v26) = 0;
    }
    if ( (v24 & 2) != 0 )
    {
      if ( !(unsigned int)CheckReadNBytes(v25, v23, 4u, L"can not read LOAD_BALANCE_INFOsize")
        || (v28 = *(_DWORD *)v25,
            v29 = v25 + 4,
            !(unsigned int)CheckReadNBytes(v29, v23, v28, L"can not read LOAD_BALANCE_INFO")) )
      {
        v12 = -1626322447;
        goto LABEL_12;
      }
    }
    else
    {
      v29 = 0;
      v28 = 0;
    }
    if ( (unsigned int)(v26 - 1) > 0x7F )
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
        v29,
        v28,
        1);
    }
    else
    {
      memcpy_0(v172, v27, (unsigned int)v26);
      v7 = (CCO *)this;
      CTSConnectionHandler::SetServerRedirectionInfo(this[36], *((_DWORD *)a2 + 1), v172, 0, 0, 1);
    }
    goto LABEL_336;
  }
  if ( (*(_WORD *)a2 & 0x400) == 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v142 = RdpX_GetActivityIdPrefix(256, v10, v13);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 219, &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids, v142);
    }
    goto LABEL_336;
  }
  v30 = *((_DWORD *)a2 + 2);
  v31 = (unsigned __int8 *)a2 + 12;
  v148 = v30;
  if ( (v30 & 1) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes((unsigned __int8 *)a2 + 12, v23, 4u, L"can not read TARGET_NET_ADDRESSsize")
      || (v32 = *(unsigned int *)v31,
          v166 = v32,
          v152 = (unsigned __int16 *)((char *)a2 + 16),
          !(unsigned int)CheckReadNBytes((unsigned __int8 *)a2 + 16, v23, v32, L"can not read TARGET_NET_ADDRESS")) )
    {
      v12 = -1626322387;
      goto LABEL_12;
    }
    if ( (v32 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322386;
      goto LABEL_12;
    }
    v31 = (unsigned __int8 *)a2 + v32 + 16;
  }
  else
  {
    v152 = 0;
    LODWORD(v166) = 0;
  }
  if ( (v30 & 2) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v31, v23, 4u, L"can not read LOAD_BALANCE_INFOsize")
      || (v33 = *(unsigned int *)v31,
          *(_QWORD *)v167 = v33,
          v168 = v31 + 4,
          !(unsigned int)CheckReadNBytes(v31 + 4, v23, v33, L"can not read LOAD_BALANCE_INFO")) )
    {
      v12 = -1626322381;
      goto LABEL_12;
    }
    v31 += v33 + 4;
  }
  else
  {
    v168 = 0;
    v167[0] = 0;
  }
  if ( (v30 & 4) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v31, v23, 4u, L"can not read LB_USERNAMEsize")
      || (v34 = *(unsigned int *)v31,
          v35 = (__int64)(v31 + 4),
          Size = v34,
          Src = v31 + 4,
          !(unsigned int)CheckReadNBytes(v31 + 4, v23, v34, L"can not read LB_USERNAME")) )
    {
      v12 = -1626322376;
      goto LABEL_12;
    }
    if ( (v34 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322375;
      goto LABEL_12;
    }
    v31 += v34 + 4;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v36 = RdpX_GetActivityIdPrefix(v11, v10, v13);
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        190,
        (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
        v36,
        v35);
    }
  }
  else
  {
    Src = 0;
    Size = 0;
  }
  if ( (v30 & 8) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v31, v23, 4u, L"can not read LB_DOMAINsize")
      || (v37 = *(unsigned int *)v31,
          v38 = (__int64)(v31 + 4),
          v156 = v37,
          v157 = v31 + 4,
          !(unsigned int)CheckReadNBytes(v31 + 4, v23, v37, L"can not read LB_DOMAIN")) )
    {
      v12 = -1626322368;
      goto LABEL_12;
    }
    if ( (v37 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322367;
      goto LABEL_12;
    }
    v31 += v37 + 4;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v39 = RdpX_GetActivityIdPrefix(v11, v10, v13);
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        191,
        (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
        v39,
        v38);
    }
  }
  else
  {
    v157 = 0;
    LODWORD(v156) = 0;
  }
  if ( (v30 & 0x10) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v31, v23, 4u, L"can not read LB_PASSWORDsize")
      || (v40 = *(unsigned int *)v31,
          v154 = v40,
          v153 = v31 + 4,
          !(unsigned int)CheckReadNBytes(v31 + 4, v23, v40, L"can not read LB_PASSWORD")) )
    {
      v12 = -1626322360;
      goto LABEL_12;
    }
    if ( (v40 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322359;
      goto LABEL_12;
    }
    v31 += v40 + 4;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v41 = RdpX_GetActivityIdPrefix(v11, v10, v13);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 192, &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids, v41);
    }
  }
  else
  {
    v153 = 0;
    v154 = 0;
  }
  if ( (v30 & 0x100) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v31, v23, 4u, L"can not read TARGET_FQDNsize")
      || (v42 = *(unsigned int *)v31,
          v43 = (__int64)(v31 + 4),
          v162 = v42,
          v163 = v31 + 4,
          !(unsigned int)CheckReadNBytes(v31 + 4, v23, v42, L"can not read TARGET_FQDN")) )
    {
      v12 = -1626322352;
      goto LABEL_12;
    }
    if ( (v42 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322351;
      goto LABEL_12;
    }
    v31 += v42 + 4;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v44 = RdpX_GetActivityIdPrefix(v11, v10, v13);
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        193,
        (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
        v44,
        v43);
    }
  }
  else
  {
    v163 = 0;
    LODWORD(v162) = 0;
  }
  if ( (v30 & 0x200) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v31, v23, 4u, L"can not read TARGET_NETBIOS_NAMEsize")
      || (v45 = *(unsigned int *)v31,
          v46 = (__int64)(v31 + 4),
          v164 = v45,
          v165 = v31 + 4,
          !(unsigned int)CheckReadNBytes(v31 + 4, v23, v45, L"can not read TARGET_NETBIOS_NAME")) )
    {
      v12 = -1626322344;
      goto LABEL_12;
    }
    if ( (v45 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322343;
      goto LABEL_12;
    }
    v31 += v45 + 4;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v47 = RdpX_GetActivityIdPrefix(v11, v10, v13);
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        194,
        (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
        v47,
        v46);
    }
  }
  else
  {
    v165 = 0;
    LODWORD(v164) = 0;
  }
  if ( (v30 & 0x1000) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v31, v23, 4u, L"can not read LB_CLIENT_TSV_URLsize")
      || (v48 = *(unsigned int *)v31,
          v49 = v31 + 4,
          !(unsigned int)CheckReadNBytes(v31 + 4, v23, v48, L"can not read LB_CLIENT_TSV_URL")) )
    {
      v12 = -1626322328;
      goto LABEL_12;
    }
    if ( (v48 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322327;
      goto LABEL_12;
    }
    v31 += v48 + 4;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v50 = RdpX_GetActivityIdPrefix(v11, v10, v13);
      WPP_SF_DS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        195,
        (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
        v50,
        (__int64)v49);
    }
  }
  else
  {
    v49 = 0;
    LODWORD(v48) = 0;
  }
  v12 = CCO::internalVerifyLBInfo((CCO *)this, (v30 >> 13) & 1, v49, v48);
  if ( v12 < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpX_GetActivityIdPrefix(v51, v10, v13);
      v15 = 196;
      v16 = "internalVerifyLBInfo";
      goto LABEL_10;
    }
LABEL_11:
    v11 = 520093696;
    if ( (v12 & 0x1F000000) != 0x1F000000 )
      goto LABEL_18;
    goto LABEL_12;
  }
  if ( (v30 & 0x8000) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v31, v23, 4u, L"can not read LB_REDIRECTION_GUIDsize")
      || (v52 = *(unsigned int *)v31,
          v159 = v52,
          v158 = v31 + 4,
          !(unsigned int)CheckReadNBytes(v31 + 4, v23, v52, L"can not read LB_REDIRECTION_GUID")) )
    {
      v12 = -1626322315;
      goto LABEL_12;
    }
    if ( (v52 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322314;
      goto LABEL_12;
    }
    v31 += v52 + 4;
  }
  else
  {
    v158 = 0;
    LODWORD(v159) = 0;
  }
  if ( (v30 & 0x10000) != 0 )
  {
    if ( !(unsigned int)CheckReadNBytes(v31, v23, 4u, L"can not read LB_TARGET_CERTIFICATEsize")
      || (v53 = *(unsigned int *)v31,
          v161 = v53,
          v160 = v31 + 4,
          !(unsigned int)CheckReadNBytes(v31 + 4, v23, v53, L"can not read LB_TARGET_CERTIFICATE")) )
    {
      v12 = -1626322308;
      goto LABEL_12;
    }
    if ( (v53 & 1) != 0 )
    {
      TRACE_ABORT_FROM_MACRO_FN((wchar_t *)L"Bad string size, expecting widechar string size here");
      v12 = -1626322307;
      goto LABEL_12;
    }
    v31 += v53 + 4;
  }
  else
  {
    v160 = 0;
    LODWORD(v161) = 0;
  }
  LODWORD(uBytes) = 0;
  if ( (v30 & 0x800) == 0 )
  {
    v76 = 0;
    goto LABEL_208;
  }
  if ( !(unsigned int)CheckReadNBytes(v31, v23, 4u, L"TARGET_NET_ADDRESSES - wrong size") )
  {
    v12 = -1626322288;
    goto LABEL_12;
  }
  v54 = (unsigned int *)(v31 + 4);
  if ( !(unsigned int)CheckReadNBytes(
                        v31 + 4,
                        v23,
                        *(unsigned int *)v31,
                        L"TARGET_NET_ADDRESSES - wrong total bytes size") )
  {
    v12 = -1626322278;
    goto LABEL_12;
  }
  if ( !(unsigned int)CheckReadNBytes(
                        v31 + 4,
                        v23,
                        4u,
                        L"TARGET_NET_ADDRESSES - wrong size while getting number of addresses") )
  {
    v12 = -1626322272;
    goto LABEL_12;
  }
  v55 = *v54;
  v146 = v55;
  if ( (unsigned int)v55 > 0x19 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v56 = RdpX_GetActivityIdPrefix(v11, v10, v13);
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids, v56, v55);
    }
    return (unsigned int)-2147467259;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v57 = RdpX_GetActivityIdPrefix(v11, v10, v13);
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids, v57, v55);
  }
  hMem = LocalAlloc(0x40u, 8 * v55);
  if ( hMem )
  {
    v150 = LocalAlloc(0x40u, 4 * v55);
    v64 = v150;
    if ( !v150 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v65 = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v62, v63);
        v66 = 200;
        v67 = "pServerIpAddressLengths";
LABEL_191:
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v66,
          (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
          v65,
          (__int64)v67);
        goto LABEL_192;
      }
      goto LABEL_192;
    }
    v68 = (unsigned __int8 *)(v54 + 1);
    v69 = 0;
    if ( v146 )
    {
      while ( (unsigned int)CheckReadNBytes(v68, v23, 4u, L"can not read TARGET_NET_ADDRESS_IPV6V4_LIST Addressessize") )
      {
        v64[v69] = *(_DWORD *)v68;
        *((_QWORD *)hMem + v69) = v68 + 4;
        if ( !(unsigned int)CheckReadNBytes(
                              v68 + 4,
                              v23,
                              (unsigned int)v64[v69],
                              L"can not read TARGET_NET_ADDRESS_IPV6V4_LIST Addresses") )
          break;
        v70 = (unsigned int)v64[v69];
        v71 = *((_QWORD *)hMem + v69);
        if ( *(_BYTE *)((unsigned int)(v70 - 1) + v71) || *(_BYTE *)((unsigned int)(v70 - 2) + v71) )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v81 = RdpX_GetActivityIdPrefix(v11, v70, v13);
            v82 = 201;
LABEL_216:
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v82, &WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids, v81);
          }
LABEL_217:
          v12 = -2147467259;
          goto LABEL_193;
        }
        v72 = (unsigned int)v70;
        v170 = v70;
        v73 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_DWORD)WPP_GLOBAL_Control[7] & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          RdpX_GetActivityIdPrefix(v11, v70, (unsigned int)v70);
          WPP_SF_DdS(*((_QWORD *)WPP_GLOBAL_Control + 2), v69, v71);
          v73 = WPP_GLOBAL_Control;
          v72 = v170;
        }
        v64 = v150;
        v74 = *((unsigned int *)v150 + v69);
        v75 = (unsigned int)(v74 + uBytes);
        if ( (unsigned int)v75 < (unsigned int)uBytes || (unsigned int)v75 < (unsigned int)v74 )
        {
          if ( v73 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v73[7] & 1) != 0 && *((_BYTE *)v73 + 25) >= 2u )
          {
            v81 = RdpX_GetActivityIdPrefix(v75, v74, v72);
            v82 = 203;
            goto LABEL_216;
          }
          goto LABEL_217;
        }
        LODWORD(uBytes) = v74 + uBytes;
        v68 += v72 + 4;
        v69 = (unsigned int)(v69 + 1);
        if ( (unsigned int)v69 >= v146 )
        {
          v30 = v148;
          goto LABEL_207;
        }
      }
      v12 = -1626322240;
      goto LABEL_12;
    }
LABEL_207:
    v76 = v146;
LABEL_208:
    v148 = v30 & 0x80;
    v77 = v148 == 0;
    if ( (_DWORD)Size )
    {
      v78 = Size;
      v79 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)Size + 2LL);
      v80 = v79;
      if ( v79 )
      {
        memcpy_0(v79, Src, v78);
        if ( (v30 & 0x20) != 0 )
          CTSConnectionHandler::SetRedirectionUserName(this[36], v80);
        else
          v12 = (*(__int64 (__fastcall **)(CTSConnectionHandler *, const char *, unsigned __int16 *, _QWORD))(*(_QWORD *)this[50] + 56LL))(
                  this[50],
                  "UserName",
                  v80,
                  0);
        LocalFree(v80);
        if ( v12 < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = RdpX_GetActivityIdPrefix(v83, v10, v13);
            v15 = 204;
            v16 = "Set property for username";
            goto LABEL_10;
          }
          goto LABEL_11;
        }
      }
    }
    if ( (_DWORD)v156 )
    {
      v84 = v156;
      v85 = LocalAlloc(0x40u, (unsigned int)v156 + 2LL);
      v86 = v85;
      if ( v85 )
      {
        memcpy_0(v85, v157, v84);
        v12 = (*(__int64 (__fastcall **)(CTSConnectionHandler *, const char *, void *, _QWORD))(*(_QWORD *)this[50]
                                                                                              + 56LL))(
                this[50],
                "Domain",
                v86,
                0);
        LocalFree(v86);
        if ( v12 < 0 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v14 = RdpX_GetActivityIdPrefix(v87, v10, v13);
            v15 = 205;
            v16 = "Set property for domain";
            goto LABEL_10;
          }
          goto LABEL_11;
        }
      }
    }
    if ( (_DWORD)v154 )
    {
      v88 = (unsigned int)v154;
      v89 = (unsigned int)v154 + 2LL;
      if ( v89 <= 0x800 )
      {
        v90 = LocalAlloc(0x40u, v89);
        v91 = v90;
        if ( (v30 & 0x4000) != 0 )
        {
          if ( v90 )
          {
            memcpy_0(v90, v153, (unsigned int)v88);
            v7 = (CCO *)this;
            v12 = (*(__int64 (__fastcall **)(CTSConnectionHandler *, const char *, void *, _QWORD))(*(_QWORD *)this[50]
                                                                                                  + 56LL))(
                    this[50],
                    "PKEncryptedPassword",
                    v91,
                    0);
            LocalFree(v91);
            if ( v12 < 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v14 = RdpX_GetActivityIdPrefix(v92, v10, v13);
                v15 = 206;
                v16 = "Set property for PK-encrypted Password";
                goto LABEL_10;
              }
              goto LABEL_11;
            }
            goto LABEL_264;
          }
        }
        else if ( v90 )
        {
          memcpy_0(v90, v153, v88);
          v12 = (*(__int64 (__fastcall **)(CTSConnectionHandler *, const char *, void *, _QWORD))(*(_QWORD *)this[50]
                                                                                                + 64LL))(
                  this[50],
                  "Password",
                  v91,
                  0);
          v93 = v153;
          do
          {
            *v93++ = 0;
            --v88;
          }
          while ( v88 );
          v94 = v91;
          v95 = (unsigned int)(v154 + 2);
          if ( (_DWORD)v154 != -2 )
          {
            do
            {
              *v94++ = 0;
              --v95;
            }
            while ( v95 );
          }
          LocalFree(v91);
          if ( v12 < 0 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = RdpX_GetActivityIdPrefix(v96, v10, v13);
              v15 = 207;
              v16 = "Set property for Password";
              goto LABEL_10;
            }
            goto LABEL_11;
          }
          if ( (_DWORD)Size )
            (*(void (__fastcall **)(CTSConnectionHandler *, const char *, __int64))(*(_QWORD *)this[50] + 32LL))(
              this[50],
              "AutoLogon",
              1);
          v147 = (v30 >> 6) & 1;
          v12 = (*(__int64 (__fastcall **)(CTSConnectionHandler *, const char *, _QWORD))(*(_QWORD *)this[50] + 32LL))(
                  this[50],
                  "PasswordContainsSCardPin",
                  v147);
          if ( v12 < 0 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = RdpX_GetActivityIdPrefix(v97, v10, v13);
              v15 = 208;
              v16 = "Failed to set TS_PROP_CORE_PASSWORD_IS_SC_PIN!";
              goto LABEL_10;
            }
            goto LABEL_11;
          }
          v7 = (CCO *)this;
LABEL_270:
          v99 = v158;
          if ( v158 )
          {
            if ( (_DWORD)v159 )
            {
              v100 = v159;
              v101 = LocalAlloc(0x40u, (unsigned int)v159 + 2LL);
              v102 = v101;
              if ( v101 )
              {
                memcpy_0(v101, v99, v100);
                v12 = (*(__int64 (__fastcall **)(_QWORD, const char *, void *, _QWORD))(**((_QWORD **)v7 + 50) + 56LL))(
                        *((_QWORD *)v7 + 50),
                        "RedirectionGuid",
                        v102,
                        0);
                LocalFree(v102);
                if ( v12 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v14 = RdpX_GetActivityIdPrefix(v103, v10, v13);
                    v15 = 210;
                    v16 = "Failed to set TS_PROP_REDIRECTION_GUID!";
                    goto LABEL_10;
                  }
                  goto LABEL_11;
                }
              }
            }
          }
          v104 = v160;
          if ( v160 )
          {
            if ( (_DWORD)v161 )
            {
              v105 = v161;
              v106 = LocalAlloc(0x40u, (unsigned int)v161 + 2LL);
              v107 = v106;
              if ( v106 )
              {
                memcpy_0(v106, v104, v105);
                v12 = (*(__int64 (__fastcall **)(_QWORD, const char *, void *, _QWORD))(**((_QWORD **)v7 + 50) + 56LL))(
                        *((_QWORD *)v7 + 50),
                        "TargetCertificate",
                        v107,
                        0);
                LocalFree(v107);
                if ( v12 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v14 = RdpX_GetActivityIdPrefix(v108, v10, v13);
                    v15 = 211;
                    v16 = "Failed to set TS_PROP_REDIRECTION_TARGET_CERTIFICATE!";
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
                  v147);
          if ( v12 < 0 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = RdpX_GetActivityIdPrefix(v109, v10, v13);
              v15 = 212;
              v16 = "Failed to set TS_PROP_REDIRECTION_USE_SCARD_LOGON!";
              goto LABEL_10;
            }
            goto LABEL_11;
          }
          if ( (_DWORD)v162 )
          {
            v110 = v162;
            v111 = LocalAlloc(0x40u, (unsigned int)v162 + 2LL);
            v112 = v111;
            if ( v111 )
            {
              memcpy_0(v111, v163, v110);
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v116 = RdpX_GetActivityIdPrefix(v114, v113, v115);
                WPP_SF_DS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  213,
                  (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
                  v116,
                  (__int64)v112);
              }
              v12 = (*(__int64 (__fastcall **)(_QWORD, const char *, void *, _QWORD))(**((_QWORD **)v7 + 50) + 56LL))(
                      *((_QWORD *)v7 + 50),
                      "ServerFqdn",
                      v112,
                      0);
              LocalFree(v112);
              if ( v12 < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v14 = RdpX_GetActivityIdPrefix(v117, v10, v13);
                  v15 = 214;
                  v16 = "Set property for server FQDN";
                  goto LABEL_10;
                }
                goto LABEL_11;
              }
            }
          }
          if ( (_DWORD)v164 )
          {
            v118 = v164;
            v119 = LocalAlloc(0x40u, (unsigned int)v164 + 2LL);
            v120 = v119;
            if ( v119 )
            {
              memcpy_0(v119, v165, v118);
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                v124 = RdpX_GetActivityIdPrefix(v122, v121, v123);
                WPP_SF_DS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  215,
                  (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
                  v124,
                  (__int64)v120);
              }
              v12 = (*(__int64 (__fastcall **)(_QWORD, const char *, void *, _QWORD))(**((_QWORD **)v7 + 50) + 56LL))(
                      *((_QWORD *)v7 + 50),
                      "ServerNetBiosName",
                      v120,
                      0);
              LocalFree(v120);
              if ( v12 < 0 )
              {
                if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                  && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v14 = RdpX_GetActivityIdPrefix(v125, v10, v13);
                  v15 = 216;
                  v16 = "Set property for server NetBios name";
                  goto LABEL_10;
                }
                goto LABEL_11;
              }
            }
          }
          if ( hMem && v76 )
          {
            v126 = (char *)LocalAlloc(0x40u, (unsigned int)uBytes);
            v130 = v126;
            if ( !v126 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v65 = RdpX_GetActivityIdPrefix(v128, v127, v129);
                v66 = 217;
                v67 = "pAlignedServerIpAddresses";
                goto LABEL_191;
              }
LABEL_192:
              v12 = -2147024882;
LABEL_193:
              v18 = hMem;
LABEL_19:
              LocalFree(v18);
LABEL_20:
              if ( v150 )
                LocalFree(v150);
              return (unsigned int)v12;
            }
            v131 = 0;
            v149 = v126;
            v132 = (unsigned int *)v150;
            v133 = (const void **)hMem;
            do
            {
              memcpy_0(v130, v133[v131], v132[v131]);
              v135 = v132[v131];
              v131 = (unsigned int)(v131 + 1);
              v130 += v135;
            }
            while ( (unsigned int)v131 < v76 );
            v7 = (CCO *)this;
            v136 = v149;
            v12 = CTSConnectionHandler::SetServerAddressesToConnect(this[36], (unsigned __int16 *)v149, v134, v76);
            if ( v12 < 0 )
            {
              if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
                && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v140 = RdpX_GetActivityIdPrefix(v138, v137, v139);
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  218,
                  (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
                  v140,
                  (__int64)"_spConnectionHandler->SetServerAddressesToConnect failed",
                  v12);
              }
              LocalFree(v136);
              goto LABEL_11;
            }
          }
          if ( (unsigned int)(v166 - 1) > 0x7F )
          {
            v141 = *((_QWORD *)v7 + 50);
            v152 = 0;
            (*(void (__fastcall **)(__int64, const char *, unsigned __int16 **))(*(_QWORD *)v141 + 128LL))(
              v141,
              "ServerName",
              &v152);
            CTSConnectionHandler::SetServerRedirectionInfo(
              *((CTSConnectionHandler **)v7 + 36),
              *((_DWORD *)v169 + 1),
              v152,
              v168,
              v167[0],
              v77);
          }
          else
          {
            memcpy_0(v172, v152, (unsigned int)v166);
            CTSConnectionHandler::SetServerRedirectionInfo(
              *((CTSConnectionHandler **)v7 + 36),
              *((_DWORD *)v169 + 1),
              v172,
              0,
              0,
              v77);
          }
          if ( v148 )
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
            &v147);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpX_GetActivityIdPrefix(v98, v10, v13);
        v15 = 209;
        v16 = "Failed to get TS_PROP_CORE_PASSWORD_IS_SC_PIN!";
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
    v61 = RdpX_GetActivityIdPrefix(v59, v58, v60);
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      199,
      (unsigned int)&WPP_08de16ab86e6334a0320b0a677ab2965_Traceguids,
      v61,
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
