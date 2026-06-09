# EapPeapCMakeMessage(_PEAP_CONTROL_BLOCK *,_PPP_EAP_PACKET *,_PPP_EAP_PACKET *,ulong,_PPP_EAP_OUTPUT *,_PPP_EAP_INPUT *)

- ea: `0x180008b28`
- end: `0x18000c180`
- name: `?EapPeapCMakeMessage@@YAKPEAU_PEAP_CONTROL_BLOCK@@PEAU_PPP_EAP_PACKET@@1KPEAU_PPP_EAP_OUTPUT@@PEAU_PPP_EAP_INPUT@@@Z`
- size: `13912`
- prototype: `unsigned int __usercall@<eax>(struct _PEAP_CONTROL_BLOCK *@<rcx>, struct _PPP_EAP_PACKET *Src@<rdx>, struct _PPP_EAP_PACKET *@<r8>, unsigned int@<r9d>, struct _PPP_EAP_OUTPUT *, struct _PPP_EAP_INPUT *)`
- caller_count: `1`
- callee_count: `77`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180007270`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180007c60`
- `0x1800088e0`
- `0x180008b28`
- `0x180010cb4`
- `0x180017780`
- `0x18001ac80`
- `0x18001b488`
- `0x18001c680`
- `0x18001e300`
- `0x18001f020`
- `0x18001f404`
- `0x18001f78c`
- `0x18001fc9c`
- `0x180021168`
- `0x1800211a4`
- `0x180021fe0`
- `0x180022d18`
- `0x18002d2f4`
- `0x1800300c8`
- `0x180030240`
- `0x180030508`
- `0x180030c30`
- `0x180030e18`
- `0x180031194`
- `0x180031468`
- `0x18003149c`
- `0x18003205c`
- `0x180032370`
- `0x1800328ac`
- `0x180032a0c`
- `0x1800331c8`
- `0x180033354`
- `0x1800334d4`
- `0x180035680`
- `0x180036230`
- `0x18003623c`
- `0x180036254`
- `0x18004acb8`
- `0x18004cab8`
- `0x18004d0ac`
- `0x18004d2d8`
- `0x18004d4b8`
- `0x18004d878`
- `0x18004d9a4`
- `0x18004f508`
- `0x180051510`
- `0x180052dd0`
- `0x18005320c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c14b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c14b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800091a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009a6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a893`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000af11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800091a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180009a6e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000a893`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000af11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008c6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008c83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009074`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000913f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a872`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b104`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b111`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008c6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008c83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009074`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000913f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009a55`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a872`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ae15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b104`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000b111`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c13d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000c13d`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008c27`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180008c27`
- `eapputil!EapConvertHostToWireFormat16` at `0x18000994b`
- `eapputil!EapConvertHostToWireFormat16` at `0x180009d48`
- `eapputil!EapConvertHostToWireFormat16` at `0x18000a7e0`
- `eapputil!EapConvertHostToWireFormat16` at `0x18000a9a3`
- `eapputil!EapConvertHostToWireFormat16` at `0x18000beea`
- `eapputil!EapConvertHostToWireFormat16` at `0x18000994b`
- `eapputil!EapConvertHostToWireFormat16` at `0x180009d48`
- `eapputil!EapConvertHostToWireFormat16` at `0x18000a7e0`
- `eapputil!EapConvertHostToWireFormat16` at `0x18000a9a3`
- `eapputil!EapConvertHostToWireFormat16` at `0x18000beea`
- `eapputil!EapConvertWireToHostFormat32` at `0x180009f51`
- `eapputil!EapConvertWireToHostFormat32` at `0x180009f89`
- `eapputil!EapConvertWireToHostFormat32` at `0x180009f51`
- `eapputil!EapConvertWireToHostFormat32` at `0x180009f89`
- `eapputil!EapConvertWireToHostFormat16` at `0x180008d05`
- `eapputil!EapConvertWireToHostFormat16` at `0x180008d60`
- `eapputil!EapConvertWireToHostFormat16` at `0x180009016`
- `eapputil!EapConvertWireToHostFormat16` at `0x1800090f4`
- `eapputil!EapConvertWireToHostFormat16` at `0x1800093ab`
- `eapputil!EapConvertWireToHostFormat16` at `0x180009486`
- `eapputil!EapConvertWireToHostFormat16` at `0x180009c87`
- `eapputil!EapConvertWireToHostFormat16` at `0x180009dd6`
- `eapputil!EapConvertWireToHostFormat16` at `0x180009f0f`
- `eapputil!EapConvertWireToHostFormat16` at `0x18000a0c7`
- `eapputil!EapConvertWireToHostFormat16` at `0x18000a91a`
- `eapputil!EapConvertWireToHostFormat16` at `0x18000b4d5`
- `eapputil!EapConvertWireToHostFormat16` at `0x18000b512`
- `eapputil!EapConvertWireToHostFormat16` at `0x18000b86d`
- `eapputil!EapConvertWireToHostFormat16` at `0x18000b8c2`
- `eapputil!EapConvertWireToHostFormat16` at `0x18000b92e`
- `eapputil!EapConvertWireToHostFormat16` at `0x180008d05`
- `eapputil!EapConvertWireToHostFormat16` at `0x180008d60`
- `eapputil!EapConvertWireToHostFormat16` at `0x180009016`
- `eapputil!EapConvertWireToHostFormat16` at `0x1800090f4`
- `eapputil!EapConvertWireToHostFormat16` at `0x1800093ab`
- `eapputil!EapConvertWireToHostFormat16` at `0x180009486`
- `eapputil!EapConvertWireToHostFormat16` at `0x180009c87`
- `eapputil!EapConvertWireToHostFormat16` at `0x180009dd6`
- `eapputil!EapConvertWireToHostFormat16` at `0x180009f0f`
- `eapputil!EapConvertWireToHostFormat16` at `0x18000a0c7`
- `eapputil!EapConvertWireToHostFormat16` at `0x18000a91a`
- `eapputil!EapConvertWireToHostFormat16` at `0x18000b4d5`
- `eapputil!EapConvertWireToHostFormat16` at `0x18000b512`
- `eapputil!EapConvertWireToHostFormat16` at `0x18000b86d`
- `eapputil!EapConvertWireToHostFormat16` at `0x18000b8c2`
- `eapputil!EapConvertWireToHostFormat16` at `0x18000b92e`

## pseudocode

```c
__int64 __fastcall EapPeapCMakeMessage(
        struct _PEAP_CONTROL_BLOCK *a1,
        struct _PPP_EAP_PACKET *Src,
        struct _PPP_EAP_PACKET *a3,
        unsigned int a4,
        struct _PPP_EAP_OUTPUT *a5,
        struct _PPP_EAP_INPUT *a6)
{
  unsigned int v10; // eax
  struct _EAPTLS_CONTROL_BLOCK *v11; // rcx
  _DWORD *v12; // r13
  bool v14; // zf
  struct _PPP_EAP_PACKET *v15; // r14
  void *v16; // rcx
  DWORD LastError; // eax
  unsigned int updated; // ebx
  unsigned int v19; // r12d
  char Code; // al
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  struct _EAPTLS_CONTROL_BLOCK *v23; // rcx
  int v24; // ecx
  char v25; // al
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  struct _EAPTLS_CONTROL_BLOCK *v30; // rcx
  unsigned int v31; // r9d
  struct _PPP_EAP_PACKET *v32; // r15
  int v33; // r12d
  int v34; // eax
  unsigned int v35; // r12d
  unsigned __int16 v36; // ax
  void *v37; // rcx
  int v38; // eax
  _DWORD *v39; // rax
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  struct _EAPTLS_CONTROL_BLOCK *v42; // rcx
  __int64 v43; // rdx
  int v44; // edx
  __int64 v45; // rdx
  __int128 v46; // xmm1
  __int128 v47; // xmm0
  void *v48; // rax
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  GUID guidConnectionId; // xmm0
  struct _EAPTLS_CONTROL_BLOCK *v55; // rcx
  __int64 v56; // rdx
  BYTE v57; // r15
  struct _EAPTLS_CONTROL_BLOCK *v58; // rcx
  __int16 v59; // ax
  unsigned int PEAPTLVNAKMessage; // eax
  __int16 v61; // ax
  const void **v62; // r15
  unsigned int PEAPTLVStatusMessage; // eax
  unsigned __int8 *v64; // rdx
  unsigned int InvalidCryptoBindingResponse; // eax
  struct _EAPTLS_CONTROL_BLOCK *v66; // rcx
  __int64 v67; // rdx
  PPP_EAP_ACTION v68; // eax
  struct _EAPTLS_CONTROL_BLOCK *v69; // rcx
  __int64 v70; // rdx
  RAS_AUTH_ATTRIBUTE *pUserAttributes; // rax
  __int64 v72; // r9
  __int64 v73; // rdx
  BYTE Id; // al
  void *v75; // rcx
  _DWORD *v76; // rax
  _DWORD *v77; // rdx
  struct _EAPTLS_CONTROL_BLOCK *v78; // rcx
  __int64 v79; // rdx
  BYTE *v80; // rax
  struct _EAPTLS_CONTROL_BLOCK *v81; // rcx
  __int64 v82; // rdx
  DWORD dwAuthResultCode; // ecx
  DWORD v84; // r8d
  unsigned __int16 v85; // ax
  unsigned __int8 *Data; // rdx
  size_t v87; // r8
  unsigned int v88; // eax
  size_t v89; // r8
  __int64 v90; // rcx
  struct _EAPTLS_CONTROL_BLOCK *v91; // rcx
  __int64 v92; // rdx
  __int64 v93; // rdx
  __int64 v94; // rdx
  unsigned __int16 v95; // r12
  __int64 v96; // rdx
  char IsEnabled; // al
  BYTE *v98; // rcx
  int v99; // eax
  const char *v100; // r9
  unsigned int v101; // r8d
  unsigned int CapabilitesMethodPacket; // eax
  struct _EAPTLS_CONTROL_BLOCK *v103; // rcx
  __int16 v104; // ax
  __int64 v105; // rdx
  unsigned int v106; // r8d
  unsigned int v107; // r8d
  __int64 v108; // rax
  unsigned __int16 v109; // ax
  const void **v110; // r15
  unsigned __int8 *v111; // rdx
  unsigned int CryptoBindingTLV; // eax
  struct _EAPTLS_CONTROL_BLOCK *v113; // rcx
  __int64 v114; // rdx
  __int64 v115; // r9
  RAS_AUTH_ATTRIBUTE *v116; // rax
  __int64 v117; // rdx
  int v118; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v119; // rcx
  __int64 v120; // rax
  __int128 v121; // xmm0
  __int128 v122; // xmm1
  __int128 v123; // xmm0
  __int128 v124; // xmm1
  __int128 v125; // xmm0
  __int128 v126; // xmm1
  __int128 v127; // xmm0
  __int128 v128; // xmm1
  GUID v129; // xmm0
  __int64 v130; // rdx
  __int64 v131; // rdx
  int v132; // ecx
  DWORD fFlags; // eax
  WCHAR *pwszPassword; // rdx
  GUID v135; // xmm0
  __int64 v136; // rax
  unsigned int v137; // r15d
  void *v138; // rcx
  __int64 dwSizeOfUIContextData; // r9
  _DWORD *v140; // rax
  unsigned __int16 v141; // ax
  unsigned __int8 *v142; // rdx
  size_t v143; // r8
  unsigned int v144; // eax
  unsigned __int64 v145; // r8
  unsigned int v146; // eax
  struct _EAPTLS_CONTROL_BLOCK *v147; // rcx
  int v148; // edx
  __int64 v149; // r8
  unsigned int v150; // eax
  int v151; // eax
  __int64 v152; // rdx
  __int64 v153; // r8
  unsigned int v154; // edx
  __int64 v155; // r9
  struct _PEAP_CONN_PROPERTIES **v156; // rbx
  __int64 v157; // rcx
  struct _PEAP_ENTRY_CONN_PROPERTIES *v158; // r9
  unsigned int v159; // r15d
  unsigned int IdPrivacyAndPaddingBytesLen; // r12d
  __int64 v161; // r9
  int v162; // eax
  _DWORD *v163; // rax
  struct _PEAP_CONN_PROPERTIES *v164; // r15
  unsigned int *v165; // rdx
  struct _EAPTLS_CONTROL_BLOCK *v166; // rcx
  __int64 v167; // rdx
  __int64 v168; // rdx
  struct _PEAP_ENTRY_CONN_PROPERTIES *v169; // rcx
  size_t v170; // r8
  void *v171; // rdx
  struct _PEAP_ENTRY_CONN_PROPERTIES *v172; // rax
  int v173; // ebx
  __int64 v174; // r9
  __int64 v175; // rax
  struct _EAPTLS_CONTROL_BLOCK *v176; // rcx
  __int64 v177; // rdx
  struct _RAS_AUTH_ATTRIBUTE *v178; // rbx
  unsigned int v179; // eax
  RAS_AUTH_ATTRIBUTE *v180; // rax
  void *v181; // rcx
  unsigned int EAPTLVPacket; // eax
  struct _EAPTLS_CONTROL_BLOCK *v183; // rcx
  __int64 v184; // rax
  unsigned __int16 v185; // r15
  __int16 v186; // ax
  unsigned int v187; // r8d
  struct _EAPTLS_CONTROL_BLOCK *v188; // rcx
  __int64 v189; // rdx
  struct _EAPTLS_CONTROL_BLOCK *v190; // rcx
  const void **v191; // r15
  unsigned __int8 *v192; // rdx
  BYTE v193; // al
  __int64 v194; // rax
  struct _EAPTLS_CONTROL_BLOCK *v195; // rcx
  unsigned int v196; // edx
  struct _RAS_AUTH_ATTRIBUTE *v197; // rbx
  unsigned int v198; // eax
  DWORD v199; // eax
  struct _PPP_EAP_PACKET *v200; // [rsp+58h] [rbp-A8h]
  unsigned int v201; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int uBytes; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int16 uBytes_4; // [rsp+68h] [rbp-98h] BYREF
  struct _PEAP_ENTRY_CONN_PROPERTIES *v204; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v205; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL v206; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v208; // [rsp+90h] [rbp-70h]
  int v209; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v210; // [rsp+98h] [rbp-68h]
  int v211; // [rsp+9Ch] [rbp-64h]
  struct _PPP_EAP_PACKET *v212; // [rsp+A0h] [rbp-60h]
  void *Srca; // [rsp+A8h] [rbp-58h] BYREF
  struct _PEAP_ENTRY_CONN_PROPERTIES *v214; // [rsp+B0h] [rbp-50h] BYREF
  _PPP_EAP_INPUT v215; // [rsp+C0h] [rbp-40h] BYREF
  __int128 Buf2; // [rsp+160h] [rbp+60h] BYREF
  __int128 v217; // [rsp+170h] [rbp+70h]
  unsigned __int8 v218[28]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int8 v219[128]; // [rsp+1A0h] [rbp+A0h] BYREF

  v212 = a3;
  v210 = a4;
  memset_0(&v215, 0, sizeof(v215));
  v10 = *(_DWORD *)a1;
  v214 = 0;
  hMem = 0;
  v205 = 0;
  v209 = 0;
  v201 = a4;
  v208 = v10;
  v11 = WPP_GLOBAL_Control;
  v12 = (_DWORD *)((char *)a1 + 4);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      398,
      &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
      (unsigned int)*v12);
    v11 = WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v11 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)v11 + 2), 399, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
    return 87;
  }
  v14 = (*v12 & 0x1000CB) == 0;
  v15 = 0;
  v211 = 0;
  if ( v14 )
  {
    v16 = (void *)*((_QWORD *)a1 + 1);
    if ( v16 )
    {
      if ( !ImpersonateLoggedOnUser(v16) )
      {
        LastError = GetLastError();
        updated = LastError;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            400,
            &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
            LastError);
        goto LABEL_12;
      }
      v211 = 1;
    }
  }
  uBytes = 0;
  v19 = 0;
  if ( Src )
  {
    v15 = CopyEapPacket(Src);
    if ( !v15 )
    {
      updated = 8;
      a5->Action = EAPACTION_NoAction;
      goto LABEL_767;
    }
    v19 = (unsigned __int16)EapConvertWireToHostFormat16(Src->Length);
    uBytes = v19;
  }
  updated = 0;
  v200 = v212;
  if ( (unsigned int)IsInnFragmSuppState(v208) )
  {
    if ( (*((_BYTE *)a1 + 2900) & 1) != 0 )
    {
      v201 = *((_DWORD *)a1 + 715);
      v200 = (struct _PPP_EAP_PACKET *)*((_QWORD *)a1 + 356);
      if ( v15 )
      {
        if ( v15->Code == 1 && (unsigned __int16)EapConvertWireToHostFormat16(v15->Length) >= 6u && v15->Data[0] == 25 )
        {
          Code = v15[1].Code;
          if ( (Code & 0x40) != 0 && Code < 0 && v208 != 14 )
          {
            updated = UpdateCbByReassembly(a1);
            if ( updated )
              goto LABEL_767;
          }
        }
      }
    }
  }
  while ( 1 )
  {
    while ( 1 )
    {
      v21 = *(_DWORD *)a1;
      if ( *(int *)a1 <= 7 )
        break;
      v26 = v21 - 8;
      if ( !v26 )
      {
        usingCachedCredentials = 0;
        v195 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 524, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
          v195 = WPP_GLOBAL_Control;
        }
        if ( v15 )
        {
          if ( (unsigned __int8)(v15->Code - 3) <= 1u )
          {
            SetTLSFastReconnect(*((struct _EAPTLS_CONTROL_BLOCK **)a1 + 352), 0);
            if ( v15->Code == 4 )
            {
              v197 = RasEapAuthAttributeRemove(raatPeerId, *((struct _RAS_AUTH_ATTRIBUTE **)a1 + 345));
              RasAuthAttributeDestroy(*((HLOCAL *)a1 + 345));
              v14 = *((_DWORD *)a1 + 736) == 1;
              *((_QWORD *)a1 + 345) = v197;
              if ( v14 )
                *((_DWORD *)a1 + 656) = 1078067222;
              a5->dwAuthResultCode = *((_DWORD *)a1 + 656);
              FreeCachedCredentials(*((struct _EAPTLS_CONTROL_BLOCK **)a1 + 352));
              a5->Action = EAPACTION_Done;
              WritePeapAuthFailEvent(a1, *((_DWORD *)a1 + 656));
              v198 = RasAuthAttributeConcat(
                       *((struct _RAS_AUTH_ATTRIBUTE **)a1 + 344),
                       *((struct _RAS_AUTH_ATTRIBUTE **)a1 + 345),
                       (struct _RAS_AUTH_ATTRIBUTE **)a1 + 346);
              updated = v198;
              if ( v198 )
              {
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    525,
                    &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
                    v198);
              }
              else
              {
                a5->pUserAttributes = (RAS_AUTH_ATTRIBUTE *)*((_QWORD *)a1 + 346);
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 526, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
              updated = 1359;
              a5->dwAuthResultCode = 1359;
              FreeCachedCredentials(*((struct _EAPTLS_CONTROL_BLOCK **)a1 + 352));
              a5->Action = EAPACTION_Done;
            }
            v196 = *((_DWORD *)a1 + 656);
            goto LABEL_762;
          }
          if ( v195 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_d(*((_QWORD *)v195 + 2), 527, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v15->Code);
        }
        v196 = 1359;
LABEL_762:
        WritePeapAuthFailEvent(a1, v196);
        goto LABEL_98;
      }
      v27 = v26 - 1;
      if ( !v27 )
        goto LABEL_61;
      v28 = v27 - 1;
      if ( !v28 )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 494, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
          v30 = WPP_GLOBAL_Control;
        }
        if ( !a6 )
        {
          if ( v30 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            v94 = 495;
LABEL_283:
            WPP_SF_(*((_QWORD *)v30 + 2), v94, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
          }
LABEL_284:
          updated = 87;
          goto LABEL_98;
        }
        if ( !v15 && a6->pUserAttributes )
        {
          v181 = (void *)*((_QWORD *)a1 + 347);
          LODWORD(v204) = 0;
          if ( v181 )
          {
            RasAuthAttributeDestroy(v181);
            *((_QWORD *)a1 + 347) = 0;
          }
          updated = GetEAPResultTLVValue(a6->pUserAttributes, (int *)&v204, &v205);
          if ( !updated && (_DWORD)v204 == *((_DWORD *)a1 + 659) )
          {
            if ( (_DWORD)v204 )
            {
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 498, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
              updated = CreateEAPTLVPacket(a1, a6->pUserAttributes, v200, v201, v219, 0, 0);
              if ( updated )
                goto LABEL_209;
              if ( v205 == 1 )
              {
                if ( (*((_DWORD *)a1 + 1) & 0x20000) != 0 )
                  *((_DWORD *)a1 + 660) = 1;
                *(_DWORD *)a1 = 7;
                *((_DWORD *)a1 + 656) = 0;
                if ( *((_QWORD *)a1 + 349) )
                  SetSessionKeys((struct _RAS_AUTH_ATTRIBUTE **)a1 + 344, v219, 0);
              }
              else
              {
                *(_DWORD *)a1 = 8;
              }
              *((_DWORD *)a1 + 659) = 1;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 499, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
              if ( (unsigned int)HaveNonEmptySohTlv(a6->pUserAttributes, 1u) )
              {
                EAPTLVPacket = CreateEAPTLVPacket(a1, a6->pUserAttributes, v200, v201, 0, 1, 0);
                v32 = v200;
              }
              else
              {
                v183 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 500, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                  v183 = WPP_GLOBAL_Control;
                }
                v184 = *((_QWORD *)a1 + 326);
                if ( v184 && (*(_BYTE *)(v184 + 12) & 9) == 9 )
                {
                  if ( v183 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                    WPP_SF_(*((_QWORD *)v183 + 2), 501, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                  *((_DWORD *)a1 + 1) &= ~0x80000u;
                }
                v32 = v200;
                EAPTLVPacket = NakMsEapTlvRequest(v200, v201, *((_BYTE *)a1 + 16), a1);
              }
              updated = EAPTLVPacket;
              if ( EAPTLVPacket )
                goto LABEL_210;
              *(_DWORD *)a1 = (*((_DWORD *)a1 + 1) & 0x20000) != 0 ? 9 : 4;
            }
            *((_DWORD *)a1 + 656) = 0;
            a5->Action = EAPACTION_Send;
            goto LABEL_209;
          }
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_98;
          v43 = 497;
LABEL_109:
          WPP_SF_(*((_QWORD *)v42 + 2), v43, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
          goto LABEL_98;
        }
        if ( v30 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_122;
        v45 = 496;
LABEL_121:
        WPP_SF_(*((_QWORD *)v30 + 2), v45, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
        goto LABEL_122;
      }
      v29 = v28 - 4;
      if ( v29 )
      {
        if ( v29 != 1 )
          goto LABEL_592;
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 431, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
          v30 = WPP_GLOBAL_Control;
        }
        if ( v15 )
        {
          if ( v15->Code != 1 || v15->Id == *((_BYTE *)a1 + 16) )
            goto LABEL_602;
          if ( (unsigned __int16)EapConvertWireToHostFormat16(v15->Length) < 6u )
          {
            v30 = WPP_GLOBAL_Control;
LABEL_602:
            if ( v30 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              goto LABEL_122;
            v45 = 432;
            goto LABEL_121;
          }
        }
        if ( (unsigned __int16)EapConvertWireToHostFormat16(v15->Length) != 6 )
        {
          v91 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            v92 = 434;
            goto LABEL_268;
          }
          goto LABEL_131;
        }
        v32 = v200;
        *((_BYTE *)a1 + 16) = v15->Id;
        updated = GetNextFragment(a1, 0, v15, v200, v201, a5);
        if ( !updated )
          goto LABEL_81;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 433, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
        updated = 0;
LABEL_300:
        a5->Action = EAPACTION_NoAction;
        goto LABEL_81;
      }
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 435, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
        v30 = WPP_GLOBAL_Control;
      }
      if ( v15 )
      {
        if ( v15->Code != 1 || v15->Id == *((_BYTE *)a1 + 16) )
          goto LABEL_587;
        if ( (unsigned __int16)EapConvertWireToHostFormat16(v15->Length) < 6u )
        {
          v30 = WPP_GLOBAL_Control;
LABEL_587:
          if ( v30 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            v45 = 436;
            goto LABEL_121;
          }
LABEL_122:
          a5->Action = EAPACTION_NoAction;
          goto LABEL_98;
        }
      }
      v31 = v201;
      *((_BYTE *)a1 + 16) = v15->Id;
      updated = StoreTheNextFragment(a1, v15, v200, v31, 0, &v209, a5);
      if ( updated )
      {
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_122;
        v45 = 437;
        goto LABEL_121;
      }
      if ( !v209 )
        goto LABEL_116;
      LocalFree(v15);
      v15 = (struct _PPP_EAP_PACKET *)*((_QWORD *)a1 + 359);
    }
    if ( v21 == 7 )
    {
      usingCachedCredentials = 0;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 503, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      WritePeapAuthSuccessEvent(a1);
      if ( v15 && v15->Code == 3 )
      {
        if ( !a6 || !a6->fSuccessPacketReceived )
          goto LABEL_478;
      }
      else if ( !a6 || !a6->fSuccessPacketReceived )
      {
        if ( !v15 )
          goto LABEL_98;
        if ( v15->Code != 4 )
        {
          v113 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_98;
          v115 = v15->Code;
          v114 = 523;
          goto LABEL_347;
        }
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 522, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
        a5->dwAuthResultCode = 845;
        a5->Action = EAPACTION_Done;
        updated = 0;
        SetTLSFastReconnect(*((struct _EAPTLS_CONTROL_BLOCK **)a1 + 352), 0);
        WritePeapTraceLoggingEvent(a1, v15->Code, a5->dwAuthResultCode);
        goto LABEL_98;
      }
      v147 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
LABEL_479:
        v148 = *((_DWORD *)a1 + 650);
        if ( !v148 && !*((_DWORD *)a1 + 646) )
          goto LABEL_550;
        v204 = 0;
        Srca = 0;
        v206 = 0;
        uBytes = 16;
        if ( *((_DWORD *)a1 + 646) )
        {
          v149 = *((_QWORD *)a1 + 324);
          v150 = *(_DWORD *)(v149 + 4) + 16;
          if ( *(_DWORD *)(v149 + 4) >= 0xFFFFFFF0 )
          {
            uBytes = -1;
            if ( v147 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
LABEL_486:
              updated = 534;
              goto LABEL_98;
            }
            v151 = *(_DWORD *)(v149 + 4);
            v152 = 505;
LABEL_485:
            WPP_SF_ddD(
              *((_QWORD *)v147 + 2),
              v152,
              &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
              -1,
              v151,
              -2147024362);
            goto LABEL_486;
          }
        }
        else
        {
          v153 = *((_QWORD *)a1 + 326);
          v150 = *(_DWORD *)(v153 + 20) + 16;
          if ( *(_DWORD *)(v153 + 20) >= 0xFFFFFFF0 )
          {
            uBytes = -1;
            if ( v147 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              goto LABEL_486;
            v151 = *(_DWORD *)(v153 + 20);
            v152 = 506;
            goto LABEL_485;
          }
        }
        uBytes = v150;
        if ( v148 )
        {
          v154 = v150 + 15;
          if ( v150 + 15 < v150 )
          {
            uBytes = -1;
            if ( v147 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_dd(*((_QWORD *)v147 + 2), 507, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, -1, -2147024362);
            goto LABEL_486;
          }
          v155 = *((_QWORD *)a1 + 353);
          uBytes = v150 + 15;
          if ( v154 + *(_DWORD *)(v155 + 160) < v154 )
          {
            uBytes = -1;
            if ( v147 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              goto LABEL_486;
            v151 = *(_DWORD *)(v155 + 160);
            v152 = 508;
            goto LABEL_485;
          }
          uBytes = v154 + *(_DWORD *)(v155 + 160);
        }
        else
        {
          v156 = (struct _PEAP_CONN_PROPERTIES **)((char *)a1 + 2608);
          PeapGetFirstEntryConnProp(*((struct _PEAP_CONN_PROPERTIES **)a1 + 326), &v204);
          v158 = v204;
          if ( v204 )
          {
            if ( uBytes + *((_DWORD *)v204 + 1) < uBytes )
            {
              uBytes = -1;
              v147 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                goto LABEL_486;
              v151 = *((_DWORD *)v204 + 1);
              v152 = 509;
              goto LABEL_485;
            }
            uBytes += *((_DWORD *)v204 + 1);
LABEL_505:
            if ( *((_DWORD *)*v156 + 2) )
              v159 = *((_DWORD *)v158 + 1);
            else
              v159 = 0;
            IdPrivacyAndPaddingBytesLen = PeapGetIdPrivacyAndPaddingBytesLen(*v156, v158, v159);
            updated = ULongAdd(uBytes, 2u, &uBytes);
            if ( (updated & 0x80000000) != 0 )
            {
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                WPP_SF_dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  510,
                  &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
                  uBytes,
                  updated);
LABEL_511:
              updated = (unsigned __int16)updated;
LABEL_512:
              LocalFree(v206);
              goto LABEL_98;
            }
            if ( IdPrivacyAndPaddingBytesLen > 2 )
            {
              if ( AlignUnalignedString(
                     (unsigned __int16 *)((char *)v204 + v159),
                     IdPrivacyAndPaddingBytesLen,
                     (unsigned __int16 **)&v206) )
              {
                updated = GetLastError();
                v113 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  goto LABEL_98;
                v114 = 511;
                v115 = updated;
                goto LABEL_347;
              }
              v161 = -1;
              do
                ++v161;
              while ( *((_WORD *)v206 + v161) );
              IdPrivacyAndPaddingBytesLen = 2 * v161;
              if ( 2 * (_DWORD)v161 )
              {
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    512,
                    (unsigned int)&WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
                    (_DWORD)v206,
                    2 * v161);
                v162 = ULongAdd(uBytes, IdPrivacyAndPaddingBytesLen, &uBytes);
                LOWORD(updated) = v162;
                if ( v162 < 0 )
                {
                  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                    WPP_SF_ddD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      513,
                      &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
                      uBytes,
                      IdPrivacyAndPaddingBytesLen,
                      v162);
                  goto LABEL_511;
                }
              }
            }
            v163 = LocalAlloc(0x40u, uBytes);
            v164 = (struct _PEAP_CONN_PROPERTIES *)v163;
            if ( !v163 )
            {
LABEL_550:
              if ( *((_DWORD *)a1 + 655) )
              {
                updated = UpdateUserBlob(a1);
                if ( updated )
                  goto LABEL_98;
                a5->pUserData = (PBYTE)*((_QWORD *)a1 + 343);
                v174 = *(unsigned int *)(*((_QWORD *)a1 + 343) + 4LL);
                a5->dwSizeOfUserData = v174;
                a5->fSaveUserData = 1;
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    517,
                    &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
                    v174);
              }
              if ( !*((_DWORD *)a1 + 660) )
              {
                v175 = *((_QWORD *)a1 + 326);
                if ( !v175 || (*(_BYTE *)(v175 + 12) & 1) != 0 )
                {
                  updated = PeapCreateCookie(a1, (unsigned __int8 **)&hMem, &dword_1800A6200);
                  if ( updated )
                  {
                    v176 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                    {
LABEL_561:
                      SetTLSFastReconnect(*((struct _EAPTLS_CONTROL_BLOCK **)a1 + 352), 0);
                      v32 = v200;
                      a5->dwAuthResultCode = updated;
                      a5->Action = EAPACTION_Done;
                      *(_DWORD *)a1 = 6;
                      goto LABEL_86;
                    }
                    v177 = 518;
LABEL_560:
                    WPP_SF_(*((_QWORD *)v176 + 2), v177, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                    goto LABEL_561;
                  }
                  if ( (*((_DWORD *)a1 + 1) & 0x80000) == 0 )
                  {
                    *(_BYTE *)hMem = 0;
                    *((_BYTE *)hMem + 1) = 0;
                  }
                  updated = SetTLSSessionCookie(
                              *((struct _EAPTLS_CONTROL_BLOCK **)a1 + 352),
                              (unsigned __int8 *)hMem,
                              dword_1800A6200);
                  if ( updated )
                  {
                    v176 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                      goto LABEL_561;
                    v177 = 519;
                    goto LABEL_560;
                  }
                }
              }
              if ( (*(_BYTE *)(*((_QWORD *)a1 + 326) + 12LL) & 4) == 0 )
              {
                v178 = RasEapAuthAttributeRemove(raatPeerId, *((struct _RAS_AUTH_ATTRIBUTE **)a1 + 345));
                RasAuthAttributeDestroy(*((HLOCAL *)a1 + 345));
                *((_QWORD *)a1 + 345) = v178;
              }
              v179 = PeapExportInnerMethodType(a1);
              updated = v179;
              if ( v179 )
              {
                v113 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  goto LABEL_98;
                v114 = 520;
              }
              else
              {
                v179 = RasAuthAttributeConcat(
                         *((struct _RAS_AUTH_ATTRIBUTE **)a1 + 344),
                         *((struct _RAS_AUTH_ATTRIBUTE **)a1 + 345),
                         (struct _RAS_AUTH_ATTRIBUTE **)a1 + 346);
                updated = v179;
                if ( !v179 )
                {
                  v180 = (RAS_AUTH_ATTRIBUTE *)*((_QWORD *)a1 + 346);
                  *(_DWORD *)a1 = 6;
                  a5->pUserAttributes = v180;
                  a5->dwAuthResultCode = *((_DWORD *)a1 + 656);
                  a5->Action = EAPACTION_Done;
                  EapMethodWithTlsTelemetry::StoreAuthenticationSuccessStatus(
                    (EapMethodWithTlsTelemetry *)(*((_QWORD *)a1 + 352) + 884LL),
                    1);
                  EapMethodWithTlsTelemetry::TryWriteTelemetry(
                    (EapMethodWithTlsTelemetry *)(*((_QWORD *)a1 + 352) + 884LL),
                    "PEAP");
                  WritePeapTraceLoggingEvent(a1, v15->Code, *((_DWORD *)a1 + 656));
                  SQMPeapTime(a1);
                  goto LABEL_98;
                }
                v113 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  goto LABEL_98;
                v114 = 521;
              }
              goto LABEL_572;
            }
            *v163 = 1;
            v163[1] = uBytes;
            v163[2] = 1;
            v163[3] = *(_DWORD *)(*((_QWORD *)a1 + 326) + 12LL);
            if ( *((_DWORD *)a1 + 646) )
              v165 = (unsigned int *)*((_QWORD *)a1 + 324);
            else
              v165 = (unsigned int *)(*((_QWORD *)a1 + 326) + 16LL);
            memcpy_0(v163 + 4, v165, v165[1]);
            PeapGetFirstEntryConnProp(v164, &v204);
            if ( *((_DWORD *)a1 + 650) )
            {
              if ( !v204 )
              {
                v166 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                {
LABEL_534:
                  updated = 13;
                  goto LABEL_512;
                }
                v167 = 514;
LABEL_533:
                WPP_SF_(*((_QWORD *)v166 + 2), v167, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                goto LABEL_534;
              }
              *(_DWORD *)v204 = 1;
              *((_DWORD *)v204 + 2) = *(_DWORD *)(*((_QWORD *)a1 + 353) + 8LL);
              *((_DWORD *)v204 + 1) = *(_DWORD *)(*((_QWORD *)a1 + 353) + 160LL) + 15;
              v168 = *((_QWORD *)a1 + 353);
              v169 = (struct _PEAP_ENTRY_CONN_PROPERTIES *)((char *)v204 + 12);
              v170 = *(unsigned int *)(v168 + 160);
              v171 = *(void **)(v168 + 152);
            }
            else
            {
              PeapGetFirstEntryConnProp(
                *((struct _PEAP_CONN_PROPERTIES **)a1 + 326),
                (struct _PEAP_ENTRY_CONN_PROPERTIES **)&Srca);
              v171 = Srca;
              if ( !Srca )
              {
                v172 = 0;
                *((_DWORD *)v164 + 2) = 0;
                v204 = 0;
LABEL_543:
                if ( IdPrivacyAndPaddingBytesLen )
                {
                  if ( v172 )
                  {
                    memcpy_0((char *)v172 + *((unsigned int *)v172 + 1), v206, IdPrivacyAndPaddingBytesLen);
                  }
                  else
                  {
                    v173 = *((_DWORD *)v164 + 2);
                    *((_DWORD *)v164 + 2) = 1;
                    PeapGetFirstEntryConnProp(v164, &v204);
                    memcpy_0(v204, v206, IdPrivacyAndPaddingBytesLen);
                    *((_DWORD *)v164 + 2) = v173;
                    v204 = 0;
                  }
                  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                    WPP_SF_Sd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      516,
                      (unsigned int)&WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
                      (_DWORD)v206,
                      IdPrivacyAndPaddingBytesLen);
                }
                LocalFree(v206);
                LocalFree(*((HLOCAL *)a1 + 326));
                *((_QWORD *)a1 + 326) = v164;
                a5->fSaveConnectionData = 1;
                a5->pConnectionData = (PBYTE)v164;
                a5->dwSizeOfConnectionData = *((_DWORD *)v164 + 1);
                goto LABEL_550;
              }
              v169 = v204;
              if ( !v204 )
              {
                v166 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  goto LABEL_534;
                v167 = 515;
                goto LABEL_533;
              }
              v170 = *((unsigned int *)Srca + 1);
            }
            memcpy_0(v169, v171, v170);
            v172 = v204;
            goto LABEL_543;
          }
        }
        v156 = (struct _PEAP_CONN_PROPERTIES **)((char *)a1 + 2608);
        v157 = *((_QWORD *)a1 + 326);
        if ( *(_DWORD *)(v157 + 8) )
        {
          PeapGetFirstEntryConnProp((struct _PEAP_CONN_PROPERTIES *)v157, &v204);
        }
        else
        {
          *(_DWORD *)(v157 + 8) = 1;
          PeapGetFirstEntryConnProp(*v156, &v204);
          *((_DWORD *)*v156 + 2) = 0;
        }
        v158 = v204;
        goto LABEL_505;
      }
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 504, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
LABEL_478:
      v147 = WPP_GLOBAL_Control;
      goto LABEL_479;
    }
    if ( !v21 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 401, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      if ( v15 )
        v15->Data[0] = 13;
      v32 = v200;
      updated = EapTlsCMakeMessage(
                  *((struct _EAPTLS_CONTROL_BLOCK **)a1 + 352),
                  (struct _EAPTLS_PACKET *)v15,
                  (struct _EAPTLS_PACKET *)v200,
                  v201,
                  a5,
                  a6);
      if ( !updated )
      {
        if ( a5->Action == EAPACTION_NoAction )
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 402, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
          updated = 0;
          goto LABEL_81;
        }
        if ( v15 )
        {
          v146 = SaveOuterTLVs(v15, a1);
          updated = v146;
          if ( v146 )
          {
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 403, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v146);
            goto LABEL_81;
          }
        }
        v200->Data[0] = 25;
      }
      *(_DWORD *)a1 = 1;
      goto LABEL_86;
    }
    v22 = v21 - 1;
    if ( v22 )
    {
      v40 = v22 - 3;
      if ( v40 )
      {
        v41 = v40 - 1;
        if ( v41 )
        {
          if ( v41 == 1 )
          {
            usingCachedCredentials = 0;
            v42 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              goto LABEL_209;
            v43 = 502;
            goto LABEL_109;
          }
LABEL_592:
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 528, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
          WritePeapAuthFailEvent(a1, 0x54Fu);
LABEL_116:
          v32 = v200;
          goto LABEL_81;
        }
        v30 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 470, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
          v30 = WPP_GLOBAL_Control;
        }
        if ( !a6 )
        {
          if ( v30 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)v30 + 2), 471, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
          updated = 87;
          goto LABEL_116;
        }
        v44 = *((_DWORD *)a1 + 702);
        if ( v44 && !a6->fDataReceivedFromInteractiveUI )
        {
          if ( v30 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            v45 = 472;
            goto LABEL_121;
          }
          goto LABEL_122;
        }
        *(_QWORD *)&v215.isVpn = *(_QWORD *)&a6->isVpn;
        v46 = *(_OWORD *)&a6->pwszIdentity;
        *(_OWORD *)&v215.dwSizeInBytes = *(_OWORD *)&a6->dwSizeInBytes;
        v47 = *(_OWORD *)&a6->bInitialId;
        v215.pwszPassword = (WCHAR *)*((_QWORD *)&v46 + 1);
        v215.pwszIdentity = (WCHAR *)((char *)a1 + 1044);
        v48 = (void *)*((_QWORD *)a1 + 1);
        v49 = *(_OWORD *)&a6->fAuthenticationComplete;
        *(_OWORD *)&v215.bInitialId = v47;
        v50 = *(_OWORD *)&a6->fSuccessPacketReceived;
        *(_QWORD *)&v215.fAuthenticationComplete = v49;
        v215.hTokenImpersonateUser = v48;
        v51 = *(_OWORD *)&a6->dwSizeOfDataFromInteractiveUI;
        *(_OWORD *)&v215.fSuccessPacketReceived = v50;
        v52 = *(_OWORD *)&a6->dwSizeOfConnectionData;
        *(_OWORD *)&v215.dwSizeOfDataFromInteractiveUI = v51;
        v53 = *(_OWORD *)&a6->dwSizeOfUserData;
        *(_OWORD *)&v215.dwSizeOfConnectionData = v52;
        guidConnectionId = a6->guidConnectionId;
        *(_OWORD *)&v215.dwSizeOfUserData = v53;
        v215.guidConnectionId = guidConnectionId;
        if ( v15 && !v44 && (unsigned __int8)(v15->Code - 3) > 1u )
        {
          if ( (unsigned __int16)EapConvertWireToHostFormat16(v15->Length) >= 7u )
          {
            updated = PeapClientDecryptTunnelData(a1, v15, 2u, uBytes);
            if ( updated )
            {
              v55 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                goto LABEL_131;
              v56 = 473;
LABEL_130:
              WPP_SF_(*((_QWORD *)v55 + 2), v56, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
              goto LABEL_131;
            }
            if ( (unsigned int)IsEapTLVInsidePEAP(v15) )
            {
              v57 = *((_BYTE *)a1 + 16);
              uBytes_4 = 0;
              LODWORD(v206) = 0;
              v58 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 474, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                v58 = WPP_GLOBAL_Control;
              }
              if ( v15->Code == 1 )
              {
                *((_BYTE *)a1 + 16) = v15->Id;
                v58 = WPP_GLOBAL_Control;
              }
              if ( v15[2].Code != 33 )
              {
                updated = 722;
                goto LABEL_141;
              }
              v59 = EapConvertWireToHostFormat16(&v15[1].Length[1]);
              updated = CheckForUnsupportedMandatoryTLV((struct _EAP_TLV *)&v15[2].Id, v59 - 5, (int *)&v206, 1);
              if ( updated )
              {
                v58 = WPP_GLOBAL_Control;
LABEL_141:
                if ( v58 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_d(*((_QWORD *)v58 + 2), 475, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, updated);
                goto LABEL_131;
              }
              if ( (_DWORD)v206 )
              {
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 476, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                v32 = v200;
                CreatePEAPTLVNAKMessage(a1, v200, v201);
                a5->Action = EAPACTION_Send;
                goto LABEL_81;
              }
              if ( GetPEAPTLVStatusMessageValue(v15, &uBytes_4) )
              {
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 477, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                v32 = v200;
                PEAPTLVNAKMessage = CreatePEAPTLVNAKMessage(a1, v200, v201);
LABEL_151:
                v33 = 1;
                updated = PEAPTLVNAKMessage;
                if ( !PEAPTLVNAKMessage )
                  a5->Action = EAPACTION_Send;
                goto LABEL_82;
              }
              v15->Id = v57;
              v32 = v200;
              LODWORD(v204) = 0;
              LOWORD(uBytes) = 0;
              updated = VerifyInnerEapResults(
                          a1,
                          v15,
                          &v215,
                          a5,
                          v200,
                          &v201,
                          uBytes_4,
                          (unsigned __int16 *)&uBytes,
                          (int *)&v204);
              if ( updated )
                goto LABEL_81;
              v61 = uBytes;
              if ( uBytes_4 != (_WORD)uBytes )
              {
                if ( ChangePEAPTLVStatusMessageValue(v15, (int)v204) )
                {
                  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 478, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                  updated = 1359;
                  goto LABEL_81;
                }
                v61 = uBytes;
              }
              if ( v61 == 2 )
              {
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 479, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                updated = CreatePEAPTLVStatusMessage(a1, v200, v201, 0, 2u);
                if ( !updated )
                {
                  a5->Action = EAPACTION_Send;
                  *(_DWORD *)a1 = 8;
                  *((_DWORD *)a1 + 656) = a5->dwAuthResultCode;
                  goto LABEL_86;
                }
                goto LABEL_81;
              }
              v62 = (const void **)((char *)a1 + 2792);
              updated = GetTLV((struct _PPP_EAP_PACKET *)((char *)v15 + 6), 0xCu, (struct _EAP_TLV **)a1 + 349);
              if ( updated )
                goto LABEL_116;
              if ( (*(_BYTE *)(*((_QWORD *)a1 + 326) + 12LL) & 4) != 0 && !*v62 )
              {
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 480, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                v32 = v200;
                PEAPTLVStatusMessage = CreatePEAPTLVStatusMessage(a1, v200, v201, 0, 2u);
LABEL_171:
                updated = PEAPTLVStatusMessage;
                if ( !PEAPTLVStatusMessage )
                {
                  a5->Action = EAPACTION_Send;
                  *(_DWORD *)a1 = 8;
LABEL_173:
                  *((_DWORD *)a1 + 656) = 0;
                  goto LABEL_86;
                }
LABEL_81:
                v33 = 1;
                goto LABEL_82;
              }
              v64 = (unsigned __int8 *)*v62;
              if ( *v62 )
              {
                memset(v218, 0, sizeof(v218));
                Buf2 = 0;
                v217 = 0;
                updated = CreateCryptoBindingTLV(a1, v64 + 8, (struct _CRYPTO_BINDING_TLV *)&Buf2, 0, 1, 0);
                if ( updated )
                {
                  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      481,
                      &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
                      updated);
                  goto LABEL_116;
                }
                if ( memcmp_0(*v62, &Buf2, 0x3Cu) )
                {
                  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 482, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                  v32 = v200;
                  InvalidCryptoBindingResponse = CreateInvalidCryptoBindingResponse(a1, v200, v201);
                  updated = InvalidCryptoBindingResponse;
                  if ( InvalidCryptoBindingResponse )
                  {
                    v66 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                    {
                      v67 = 483;
                      goto LABEL_184;
                    }
                    goto LABEL_185;
                  }
                  v69 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  {
                    v70 = 484;
                    goto LABEL_188;
                  }
                  goto LABEL_189;
                }
              }
              if ( GetEAPTLVAttributes(v15, &a5->pUserAttributes) )
              {
                v55 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  goto LABEL_131;
                v56 = 485;
                goto LABEL_130;
              }
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 486, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
              pUserAttributes = a5->pUserAttributes;
              *v12 &= ~0x20000u;
              *((_QWORD *)a1 + 347) = pUserAttributes;
              *(_DWORD *)a1 = 10;
              updated = 0;
              a5->Action = EAPACTION_IndicateTLV;
              goto LABEL_98;
            }
            memcpy_0(v15->Data, *((const void **)a1 + 341), *((unsigned int *)a1 + 684));
            EapConvertHostToWireFormat16((unsigned __int16)(*((_WORD *)a1 + 1368) + 4), v15->Length);
          }
          v30 = WPP_GLOBAL_Control;
        }
        if ( a6->fDataReceivedFromInteractiveUI )
        {
          *((_DWORD *)a1 + 702) = 0;
          v30 = WPP_GLOBAL_Control;
        }
        v72 = v201;
        if ( v201 < 0xC8 )
        {
          if ( v30 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            v73 = 487;
            goto LABEL_204;
          }
          goto LABEL_205;
        }
        if ( v15 )
        {
          Id = v15->Id;
          ++*((_BYTE *)a1 + 2896);
          *((_BYTE *)a1 + 16) = Id;
          v15->Id = *((_BYTE *)a1 + 2896);
          if ( v15->Data[0] != *(_DWORD *)(*((_QWORD *)a1 + 353) + 8LL) )
            goto LABEL_208;
        }
        v32 = v200;
        updated = (*(__int64 (__fastcall **)(_QWORD, struct _PPP_EAP_PACKET *, struct _PPP_EAP_PACKET *, _QWORD, struct _PPP_EAP_OUTPUT *, _PPP_EAP_INPUT *))(*((_QWORD *)a1 + 353) + 120LL))(
                    *(_QWORD *)(*((_QWORD *)a1 + 353) + 128LL),
                    v15,
                    v200,
                    v201 - 200,
                    a5,
                    &v215);
        v200->Id = *((_BYTE *)a1 + 16);
        if ( updated )
          goto LABEL_81;
        if ( a5->fInvokeInteractiveUI )
        {
          v75 = (void *)*((_QWORD *)a1 + 350);
          if ( v75 )
          {
            LocalFree(v75);
            *((_QWORD *)a1 + 350) = 0;
          }
          v76 = LocalAlloc(0x40u, a5->dwSizeOfUIContextData + 12LL);
          *((_QWORD *)a1 + 350) = v76;
          v77 = v76;
          if ( !v76 )
          {
            v78 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
              v79 = 488;
              goto LABEL_218;
            }
            goto LABEL_219;
          }
          goto LABEL_220;
        }
        if ( a5->Action == EAPACTION_Done )
        {
          v81 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 489, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
            v81 = WPP_GLOBAL_Control;
          }
          if ( !*((_DWORD *)a1 + 659) )
          {
            if ( v81 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
              v82 = 490;
              goto LABEL_227;
            }
            goto LABEL_228;
          }
          *((_DWORD *)a1 + 659) = 0;
          *((_DWORD *)a1 + 656) = a5->dwAuthResultCode;
          if ( *((_WORD *)a1 + 1314) == 2 )
          {
            if ( !a5->dwAuthResultCode )
            {
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 491, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
              a5->dwAuthResultCode = 812;
              WritePeapTraceLoggingEvent(a1, v15->Code, 0x32Cu);
              goto LABEL_81;
            }
            goto LABEL_242;
          }
          dwAuthResultCode = a5->dwAuthResultCode;
          if ( (*(_BYTE *)(*((_QWORD *)a1 + 326) + 12LL) & 2) != 0 )
          {
            if ( !dwAuthResultCode )
              goto LABEL_238;
          }
          else
          {
            if ( dwAuthResultCode )
            {
              *((_WORD *)a1 + 1314) = 2;
              goto LABEL_240;
            }
LABEL_238:
            PeapSetTypeUserAttributes(a1, a5->pUserAttributes, 1);
            a5->pUserAttributes = 0;
          }
          *((_DWORD *)a1 + 656) = 0;
LABEL_240:
          v84 = a5->dwAuthResultCode;
          if ( v84 )
            WritePeapTraceLoggingEvent(a1, v15->Code, v84);
LABEL_242:
          updated = CreatePEAPTLVStatusMessage(a1, v200, v201, 0, *((_WORD *)a1 + 1314));
          if ( !updated )
          {
            *(_DWORD *)a1 = (*((_WORD *)a1 + 1314) != 1) + 7;
            a5->Action = EAPACTION_Send;
            if ( !a5->dwAuthResultCode )
            {
              HandlePropertyFlags(a1, a5);
              goto LABEL_81;
            }
          }
          goto LABEL_210;
        }
        if ( a5->Action != EAPACTION_Send )
          goto LABEL_81;
        v85 = EapConvertWireToHostFormat16(v200->Length);
        if ( v85 < 5u )
        {
          v81 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            v82 = 493;
LABEL_227:
            WPP_SF_(*((_QWORD *)v81 + 2), v82, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
          }
LABEL_228:
          updated = 1359;
          goto LABEL_81;
        }
        Data = v200->Data;
        v87 = (unsigned int)v85 - 4;
        if ( *(_BYTE *)(*((_QWORD *)a1 + 352) + 849LL) )
          v88 = PeapEncryptTunnelDataLegacy(a1, Data, v87);
        else
          v88 = PeapEncryptTunnelDataModern(a1, Data, v87);
        updated = v88;
        if ( v88 )
          goto LABEL_81;
        v89 = *((unsigned int *)a1 + 684);
        if ( v89 <= (unsigned __int64)v201 - 6 )
        {
          memcpy_0(&v200[1].Id, *((const void **)a1 + 341), v89);
          v90 = (unsigned __int16)(*((_WORD *)a1 + 1368) + 6);
          v200->Data[0] = 25;
          v200[1].Code = 0;
          EapConvertHostToWireFormat16(v90, v200->Length);
LABEL_256:
          *((_BYTE *)a1 + 16) = v32->Id;
          goto LABEL_81;
        }
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            492,
            &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
            v201 - 6,
            v89);
LABEL_254:
        updated = 234;
        goto LABEL_81;
      }
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 438, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
        v30 = WPP_GLOBAL_Control;
      }
      if ( *((_DWORD *)a1 + 702) )
      {
        if ( v15 )
          goto LABEL_270;
        goto LABEL_280;
      }
      if ( !v15 )
        goto LABEL_280;
      if ( v15->Code != 4 )
      {
        if ( (unsigned __int16)EapConvertWireToHostFormat16(v15->Length) >= 7u )
        {
          updated = PeapClientDecryptTunnelData(a1, v15, 2u, v19);
          if ( updated )
          {
            v91 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
              v92 = 439;
              goto LABEL_268;
            }
            goto LABEL_131;
          }
          v30 = WPP_GLOBAL_Control;
LABEL_270:
          if ( v15->Code != 1 )
          {
            if ( v30 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              goto LABEL_208;
            v93 = 441;
            goto LABEL_273;
          }
          if ( !*((_DWORD *)a1 + 702) )
          {
            v95 = EapConvertWireToHostFormat16(v15->Length);
            if ( (unsigned int)IsCapabilitiesPacket(a1, v15, 0) )
            {
              LOBYTE(v96) = 3;
              _scrt_stub_for_acrt_uninitialize_critical(
                `wil::Feature<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::GetImpl'::`2'::impl,
                v96);
              IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Eaphost_TVS_Fixes>::GetImpl'::`2'::impl);
              v98 = &v15[3].Length[1];
              if ( IsEnabled )
              {
                v99 = EapConvertWireToHostFormat32(v98);
                if ( (*((_BYTE *)a1 + 2900) & 1) != 0 && (v99 & 1) == 0 )
                {
                  v30 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                    goto LABEL_208;
                  v93 = 442;
LABEL_273:
                  WPP_SF_(*((_QWORD *)v30 + 2), v93, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                  goto LABEL_208;
                }
              }
              else
              {
                v99 = EapConvertWireToHostFormat32(v98);
              }
              *((_DWORD *)a1 + 725) = v99;
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              {
                v100 = "Capable";
                if ( (v99 & 1) == 0 )
                  v100 = "Not Capable";
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  443,
                  &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
                  v100);
              }
              v32 = v200;
              v101 = v201;
              *((_BYTE *)a1 + 16) = v15->Id;
              CapabilitesMethodPacket = CreateCapabilitesMethodPacket(a1, v200, v101, 0);
              updated = CapabilitesMethodPacket;
              if ( CapabilitesMethodPacket )
              {
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    444,
                    &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
                    CapabilitesMethodPacket);
                goto LABEL_300;
              }
LABEL_317:
              a5->Action = EAPACTION_Send;
              goto LABEL_81;
            }
            if ( (unsigned int)IsMsEapTlvPacket(v15, v95) )
            {
              v32 = v200;
              updated = HandleMsEapTlvRequest(v15, v95, v200, v201, a1, a5, 0);
              goto LABEL_81;
            }
            if ( (unsigned int)IsEapTLVInsidePEAP(v15) )
            {
              uBytes_4 = 0;
              LODWORD(v204) = 0;
              v103 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 445, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                v103 = WPP_GLOBAL_Control;
              }
              if ( v15[2].Code != 33 )
              {
                updated = 722;
LABEL_310:
                if ( v103 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  goto LABEL_131;
                v105 = 446;
LABEL_312:
                WPP_SF_d(*((_QWORD *)v103 + 2), v105, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, updated);
                goto LABEL_131;
              }
              v104 = EapConvertWireToHostFormat16(&v15[1].Length[1]);
              updated = CheckForUnsupportedMandatoryTLV((struct _EAP_TLV *)&v15[2].Id, v104 - 5, (int *)&v204, 1);
              if ( updated )
              {
                v103 = WPP_GLOBAL_Control;
                goto LABEL_310;
              }
              if ( (_DWORD)v204 )
              {
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 447, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                v32 = v200;
                v106 = v201;
                *((_BYTE *)a1 + 16) = v15->Id;
                CreatePEAPTLVNAKMessage(a1, v200, v106);
                goto LABEL_317;
              }
              if ( GetPEAPTLVStatusMessageValue(v15, &uBytes_4) )
              {
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 448, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                v32 = v200;
                v107 = v201;
                *((_BYTE *)a1 + 16) = v15->Id;
                PEAPTLVNAKMessage = CreatePEAPTLVNAKMessage(a1, v200, v107);
                goto LABEL_151;
              }
              v108 = *((_QWORD *)a1 + 326);
              *((_DWORD *)a1 + 659) = 1;
              if ( (*(_BYTE *)(v108 + 12) & 2) != 0 )
              {
LABEL_328:
                v109 = uBytes_4;
              }
              else
              {
                v109 = uBytes_4;
                if ( uBytes_4 == 1 )
                {
                  uBytes_4 = 2;
                  if ( ChangePEAPTLVStatusMessageValue(v15, 0) )
                  {
                    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                      WPP_SF_(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        449,
                        &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                    updated = 1359;
                    goto LABEL_98;
                  }
                  goto LABEL_328;
                }
              }
              if ( v109 == 2 )
              {
                if ( *((_DWORD *)a1 + 735) == 1 )
                {
                  *((_DWORD *)a1 + 735) = 0;
                  *((_DWORD *)a1 + 736) = 1;
                }
              }
              else if ( v109 == 1 )
              {
                v110 = (const void **)((char *)a1 + 2792);
                updated = GetTLV((struct _PPP_EAP_PACKET *)((char *)v15 + 6), 0xCu, (struct _EAP_TLV **)a1 + 349);
                if ( updated )
                  goto LABEL_98;
                if ( (*(_BYTE *)(*((_QWORD *)a1 + 326) + 12LL) & 4) != 0 && !*v110 )
                {
                  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 450, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                  v32 = v200;
                  PEAPTLVStatusMessage = CreatePEAPTLVStatusMessage(a1, v200, v201, 0, 2u);
                  goto LABEL_171;
                }
                v111 = (unsigned __int8 *)*v110;
                if ( *v110 )
                {
                  memset(v218, 0, sizeof(v218));
                  Buf2 = 0;
                  v217 = 0;
                  CryptoBindingTLV = CreateCryptoBindingTLV(a1, v111 + 8, (struct _CRYPTO_BINDING_TLV *)&Buf2, 0, 1, 0);
                  updated = CryptoBindingTLV;
                  if ( CryptoBindingTLV )
                  {
                    v113 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                      goto LABEL_98;
                    v114 = 451;
                    goto LABEL_346;
                  }
                  if ( memcmp_0(*v110, &Buf2, 0x3Cu) )
                  {
                    v32 = v200;
                    InvalidCryptoBindingResponse = CreateInvalidCryptoBindingResponse(a1, v200, v201);
                    updated = InvalidCryptoBindingResponse;
                    if ( InvalidCryptoBindingResponse )
                    {
                      v66 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                      {
                        v67 = 452;
                        goto LABEL_184;
                      }
LABEL_185:
                      v68 = EAPACTION_NoAction;
                    }
                    else
                    {
                      v69 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                      {
                        v70 = 453;
                        goto LABEL_188;
                      }
LABEL_189:
                      v68 = EAPACTION_Send;
                    }
                    a5->Action = v68;
                    *(_DWORD *)a1 = 8;
                    a5->dwAuthResultCode = 823;
                    *((_DWORD *)a1 + 656) = 823;
                    goto LABEL_81;
                  }
                }
              }
              updated = GetEAPTLVAttributes(v15, &a5->pUserAttributes);
              if ( updated )
              {
                v91 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                {
                  v92 = 454;
                  goto LABEL_268;
                }
                goto LABEL_131;
              }
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 455, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
              v116 = a5->pUserAttributes;
              *((_DWORD *)a1 + 1) &= ~0x20000u;
              *((_QWORD *)a1 + 347) = v116;
              *(_DWORD *)a1 = 10;
              *((_BYTE *)a1 + 16) = v15->Id;
              a5->Action = EAPACTION_IndicateTLV;
LABEL_98:
              v32 = v200;
              goto LABEL_81;
            }
            if ( (*((_DWORD *)a1 + 1) & 0x80) != 0
              || (v117 = *((_QWORD *)a1 + 353)) == 0
              || v95 >= 7u && *(_DWORD *)(v117 + 8) != v15[1].Id )
            {
              LOBYTE(v118) = 0;
              if ( (*((_DWORD *)a1 + 1) & 0x80) != 0 || (v33 = 0, !*((_QWORD *)a1 + 353)) )
                v33 = 1;
              v119 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 456, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                v119 = WPP_GLOBAL_Control;
              }
              if ( !*((_QWORD *)a1 + 353) && v119 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              {
                WPP_SF_(*((_QWORD *)v119 + 2), 457, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                v119 = WPP_GLOBAL_Control;
              }
              if ( !v33 )
              {
                v120 = *((_QWORD *)a1 + 353);
                v118 = *(_DWORD *)(v120 + 8);
                if ( v119 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_dd(
                    *((_QWORD *)v119 + 2),
                    458,
                    &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
                    v15[1].Id,
                    *(_DWORD *)(v120 + 8));
                *((_DWORD *)a1 + 735) = 1;
              }
              v32 = v200;
              updated = CreateNakResponse(v200, v201, v15->Id, a1, v118);
              if ( !updated )
                a5->Action = EAPACTION_Send;
              goto LABEL_82;
            }
            v30 = WPP_GLOBAL_Control;
          }
LABEL_280:
          if ( !a6 )
          {
            if ( v30 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
              v94 = 459;
              goto LABEL_283;
            }
            goto LABEL_284;
          }
          v121 = *(_OWORD *)&a6->dwSizeInBytes;
          v122 = *(_OWORD *)&a6->pwszIdentity;
          *(_QWORD *)&v215.isVpn = *(_QWORD *)&a6->isVpn;
          *(_OWORD *)&v215.dwSizeInBytes = v121;
          v123 = *(_OWORD *)&a6->bInitialId;
          v215.pwszPassword = (WCHAR *)*((_QWORD *)&v122 + 1);
          v215.pwszIdentity = (WCHAR *)((char *)a1 + 1044);
          v124 = *(_OWORD *)&a6->fAuthenticationComplete;
          *(_OWORD *)&v215.bInitialId = v123;
          v125 = *(_OWORD *)&a6->fSuccessPacketReceived;
          *(_OWORD *)&v215.fAuthenticationComplete = v124;
          v126 = *(_OWORD *)&a6->dwSizeOfDataFromInteractiveUI;
          *(_OWORD *)&v215.fSuccessPacketReceived = v125;
          v127 = *(_OWORD *)&a6->dwSizeOfConnectionData;
          *(_OWORD *)&v215.dwSizeOfDataFromInteractiveUI = v126;
          v128 = *(_OWORD *)&a6->dwSizeOfUserData;
          *(_OWORD *)&v215.dwSizeOfConnectionData = v127;
          v129 = a6->guidConnectionId;
          *(_OWORD *)&v215.dwSizeOfUserData = v128;
          v215.guidConnectionId = v129;
          if ( !*((_DWORD *)a1 + 702) )
          {
            updated = PeapGetFirstEntryConnProp(*((struct _PEAP_CONN_PROPERTIES **)a1 + 326), &v214);
            if ( updated )
            {
              v113 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                goto LABEL_98;
              v114 = 460;
              v115 = updated;
              goto LABEL_347;
            }
            v130 = *((_QWORD *)a1 + 343);
            if ( !*(_DWORD *)(v130 + 36) || *(_DWORD *)(v130 + 4) < 0x38u || (v131 = v130 + 40) == 0 || !v214 )
            {
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 462, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
              updated = 13;
              goto LABEL_98;
            }
            v215.pConnectionData = (PBYTE)v214 + 12;
            v215.hTokenImpersonateUser = (HANDLE)*((_QWORD *)a1 + 1);
            v132 = *((_DWORD *)a1 + 1);
            v215.dwSizeOfConnectionData = *((_DWORD *)v214 + 1) - 15;
            fFlags = v215.fFlags;
            if ( (v132 & 2) != 0 )
              fFlags = v215.fFlags | 1;
            if ( (v132 & 4) != 0 )
              fFlags |= 2u;
            if ( (v132 & 8) != 0 )
              fFlags |= 4u;
            if ( (v132 & 0x10) != 0 )
              fFlags |= 8u;
            if ( (v132 & 0x20) != 0 )
              fFlags |= 0x10u;
            if ( (v132 & 0x40) != 0 )
              fFlags |= 0x20u;
            if ( *((char *)a1 + 4) < 0 )
              fFlags |= 0x40u;
            if ( (*((_DWORD *)a1 + 1) & 0x100) != 0 )
              fFlags |= 0x80u;
            if ( (*((_DWORD *)a1 + 1) & 0x40000) != 0 )
              fFlags |= 0x200000u;
            v215.fFlags = fFlags | 0x100;
            if ( *(_DWORD *)(v131 + 12) )
            {
              pwszPassword = (WCHAR *)(v131 + 530);
            }
            else
            {
              if ( *(_DWORD *)(v131 + 8) && *(_DWORD *)(v131 + 4) )
              {
                v215.pUserData = (PBYTE)(v131 + 16);
                v215.dwSizeOfUserData = *(_DWORD *)(v131 + 4) - 19;
              }
              else
              {
                v215.pUserData = 0;
                v215.dwSizeOfUserData = 0;
              }
              pwszPassword = v215.pwszPassword;
            }
            v135 = *(GUID *)((char *)a1 + 2920);
            v215.bInitialId = 0;
            v14 = *((_WORD *)a1 + 1035) == 0;
            v215.guidConnectionId = v135;
            if ( !v14 )
              pwszPassword = (WCHAR *)((char *)a1 + 2070);
            v136 = *((_QWORD *)a1 + 353);
            v215.pwszPassword = pwszPassword;
            updated = (*(__int64 (__fastcall **)(__int64, _PPP_EAP_INPUT *))(v136 + 104))(v136 + 128, &v215);
            RasEapSetRetryFlag(a1);
            v30 = WPP_GLOBAL_Control;
          }
          if ( !updated )
          {
            if ( *((_DWORD *)a1 + 702) )
            {
              *((_DWORD *)a1 + 702) = 0;
              v30 = WPP_GLOBAL_Control;
            }
            v137 = *((_DWORD *)a1 + 684) + 4;
            if ( v137 > uBytes )
            {
              updated = 8;
              if ( v30 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                WPP_SF_dd(*((_QWORD *)v30 + 2), 463, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, uBytes, v137);
              MicrosoftTelemetryAssertTriggeredNoArgs();
              goto LABEL_98;
            }
            if ( v15 )
            {
              memcpy_0(v15->Data, *((const void **)a1 + 341), *((unsigned int *)a1 + 684));
              EapConvertHostToWireFormat16((unsigned __int16)v137, v15->Length);
              v30 = WPP_GLOBAL_Control;
            }
            v72 = v201;
            if ( v201 <= 0xC8 )
            {
              if ( v30 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              {
                v73 = 464;
LABEL_204:
                WPP_SF_dd(*((_QWORD *)v30 + 2), v73, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v72, 200);
              }
LABEL_205:
              updated = 234;
              goto LABEL_98;
            }
            v32 = v200;
            updated = (*(__int64 (__fastcall **)(_QWORD, struct _PPP_EAP_PACKET *, struct _PPP_EAP_PACKET *, _QWORD, struct _PPP_EAP_OUTPUT *, _PPP_EAP_INPUT *))(*((_QWORD *)a1 + 353) + 120LL))(
                        *(_QWORD *)(*((_QWORD *)a1 + 353) + 128LL),
                        v15,
                        v200,
                        v201 - 200,
                        a5,
                        &v215);
            if ( updated )
            {
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                WPP_SF_dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  468,
                  &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
                  *(unsigned int *)(*((_QWORD *)a1 + 353) + 8LL),
                  updated);
              goto LABEL_81;
            }
            if ( a5->fInvokeInteractiveUI )
            {
              v138 = (void *)*((_QWORD *)a1 + 350);
              if ( v138 )
              {
                LocalFree(v138);
                *((_QWORD *)a1 + 350) = 0;
              }
              dwSizeOfUIContextData = a5->dwSizeOfUIContextData;
              if ( (int)dwSizeOfUIContextData + 12 < (unsigned int)dwSizeOfUIContextData )
              {
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_dd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    465,
                    &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
                    dwSizeOfUIContextData,
                    -2147024362);
                updated = 534;
                goto LABEL_81;
              }
              v140 = LocalAlloc(0x40u, (unsigned int)(dwSizeOfUIContextData + 12));
              *((_QWORD *)a1 + 350) = v140;
              v77 = v140;
              if ( !v140 )
              {
                v78 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                {
                  v79 = 466;
LABEL_218:
                  WPP_SF_(*((_QWORD *)v78 + 2), v79, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                }
LABEL_219:
                updated = 14;
                goto LABEL_81;
              }
LABEL_220:
              *v77 = *(_DWORD *)(*((_QWORD *)a1 + 353) + 8LL);
              *(_DWORD *)(*((_QWORD *)a1 + 350) + 4LL) = a5->dwSizeOfUIContextData;
              memcpy_0((void *)(*((_QWORD *)a1 + 350) + 8LL), a5->pUIContextData, a5->dwSizeOfUIContextData);
              v80 = (BYTE *)*((_QWORD *)a1 + 350);
              a5->dwSizeOfUIContextData += 12;
              a5->pUIContextData = v80;
              *((_DWORD *)a1 + 702) = 1;
              goto LABEL_210;
            }
            if ( (unsigned int)(a5->Action - 3) > 3 )
              goto LABEL_81;
            v141 = EapConvertWireToHostFormat16(v200->Length);
            v142 = v200->Data;
            v143 = (unsigned int)v141 - 4;
            v144 = *(_BYTE *)(*((_QWORD *)a1 + 352) + 849LL)
                 ? PeapEncryptTunnelDataLegacy(a1, v142, v143)
                 : PeapEncryptTunnelDataModern(a1, v142, v143);
            updated = v144;
            if ( v144 )
              goto LABEL_81;
            v145 = *((unsigned int *)a1 + 684);
            if ( v145 <= (unsigned __int64)v201 - 6 )
            {
              v200->Data[0] = 25;
              v200[1].Code = 0;
              memcpy_0(&v200[1].Id, *((const void **)a1 + 341), *((unsigned int *)a1 + 684));
              EapConvertHostToWireFormat16((unsigned __int16)(*((_WORD *)a1 + 1368) + 6), v200->Length);
              *((_BYTE *)a1 + 2896) = v200->Id;
              *((_BYTE *)a1 + 16) = v200->Id;
              *(_DWORD *)a1 = 5;
              goto LABEL_86;
            }
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                467,
                &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
                v201,
                v145 + 6);
            goto LABEL_254;
          }
          if ( v30 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_dd(
              *((_QWORD *)v30 + 2),
              469,
              &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
              *(unsigned int *)(*((_QWORD *)a1 + 353) + 8LL),
              updated);
          a5->dwAuthResultCode = updated;
          a5->Action = EAPACTION_Done;
          *(_DWORD *)a1 = 6;
LABEL_278:
          SetTLSFastReconnect(*((struct _EAPTLS_CONTROL_BLOCK **)a1 + 352), 0);
          goto LABEL_98;
        }
        v30 = WPP_GLOBAL_Control;
        if ( v15->Code != 4 )
          goto LABEL_270;
      }
      if ( v30 != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)v30 + 2), 440, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      a5->Action = EAPACTION_Done;
      a5->dwAuthResultCode = 812;
      goto LABEL_278;
    }
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 404, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
    if ( v15 && (unsigned __int8)(v15->Code - 1) <= 1u )
      v15->Data[0] = 13;
    updated = EapTlsCMakeMessage(
                *((struct _EAPTLS_CONTROL_BLOCK **)a1 + 352),
                (struct _EAPTLS_PACKET *)v15,
                (struct _EAPTLS_PACKET *)v200,
                v201,
                a5,
                a6);
    if ( updated )
      goto LABEL_116;
    if ( a5->fInvokeInteractiveUI )
    {
      v37 = (void *)*((_QWORD *)a1 + 350);
      uBytes = 0;
      if ( v37 )
      {
        LocalFree(v37);
        *((_QWORD *)a1 + 350) = 0;
      }
      v38 = ULongAdd(a5->dwSizeOfUIContextData, 0xCu, &uBytes);
      if ( v38 >= 0 )
      {
        v39 = LocalAlloc(0x40u, uBytes);
        *((_QWORD *)a1 + 350) = v39;
        if ( v39 )
        {
          *v39 = 13;
          *(_DWORD *)(*((_QWORD *)a1 + 350) + 4LL) = a5->dwSizeOfUIContextData;
          memcpy_0((void *)(*((_QWORD *)a1 + 350) + 8LL), a5->pUIContextData, a5->dwSizeOfUIContextData);
          a5->pUIContextData = (PBYTE)*((_QWORD *)a1 + 350);
          a5->dwSizeOfUIContextData = uBytes;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 406, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
          updated = 14;
        }
      }
      else
      {
        updated = (unsigned __int16)v38;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            405,
            &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
            a5->dwSizeOfUIContextData,
            v38);
      }
      goto LABEL_98;
    }
    if ( a5->Action != EAPACTION_Done )
    {
      v32 = v200;
      v200->Data[0] = 25;
      goto LABEL_81;
    }
    if ( a5->dwAuthResultCode )
      goto LABEL_116;
    v23 = (struct _EAPTLS_CONTROL_BLOCK *)*((_QWORD *)a1 + 352);
    if ( (*((_DWORD *)v23 + 1) & 0x2000) == 0 )
      SetCachedCredentials(v23);
    *((_QWORD *)a1 + 344) = a5->pUserAttributes;
    a5->pUserAttributes = 0;
    updated = PeapGetTunnelProperties(a1);
    if ( updated )
      goto LABEL_116;
    dword_1800A5D88 = GetTLSSessionCookie(
                        *((struct _EAPTLS_CONTROL_BLOCK **)a1 + 352),
                        (unsigned __int8 **)&hMem,
                        &dword_1800A6200,
                        &dword_1800A5D84);
    if ( dword_1800A5D88 || !dword_1800A6200 )
    {
      v24 = 0;
    }
    else
    {
      dword_1800A5D80 = PeapCheckCookie(a1, (struct _PEAP_COOKIE *)hMem, dword_1800A6200);
      v24 = *((_DWORD *)hMem + 259);
    }
    *((_DWORD *)a1 + 725) = v24;
    a5->Action = EAPACTION_NoAction;
    if ( a5->fSaveConnectionData )
    {
      if ( !ConnPropGetV1Struct(
              (struct _EAPTLS_CONN_PROPERTIES *)a5->pConnectionData,
              (struct _EAPTLS_CONN_PROPERTIES_V1 **)a1 + 324) )
        *((_DWORD *)a1 + 646) = 1;
      a5->fSaveConnectionData = 0;
      a5->pConnectionData = 0;
      a5->dwSizeOfConnectionData = 0;
    }
    if ( a5->fSaveUserData )
    {
      *((_DWORD *)a1 + 654) = 1;
      a5->pUserData = 0;
      a5->dwSizeOfUserData = 0;
    }
LABEL_61:
    if ( *(_DWORD *)a1 != 1 )
      break;
    if ( (*((_BYTE *)a1 + 2900) & 1) == 0 )
      break;
    v201 = *((_DWORD *)a1 + 715);
    v200 = (struct _PPP_EAP_PACKET *)*((_QWORD *)a1 + 356);
    v25 = v15[1].Code;
    if ( (v25 & 0x40) == 0 || v25 >= 0 )
      break;
    updated = UpdateCbByReassembly(a1);
    if ( updated )
      goto LABEL_767;
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 407, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
  if ( !v15 || (unsigned __int16)EapConvertWireToHostFormat16(v15->Length) < 7u )
  {
    a5->Action = EAPACTION_NoAction;
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      goto LABEL_98;
    v43 = 430;
    goto LABEL_109;
  }
  updated = PeapClientDecryptTunnelData(a1, v15, 2u, v19);
  if ( updated )
  {
    v91 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      v92 = 408;
      goto LABEL_268;
    }
LABEL_131:
    updated = 0;
    goto LABEL_122;
  }
  v15->Data[0] = 25;
  v185 = EapConvertWireToHostFormat16(v15->Length);
  if ( (unsigned int)IsMsEapTlvPacket(v15, v185) )
  {
    updated = HandleMsEapTlvRequest(v15, v185, v200, v201, a1, a5, 1);
    goto LABEL_98;
  }
  if ( (unsigned int)IsEapTLVInsidePEAP(v15) )
  {
    v14 = v15[2].Code == 33;
    LODWORD(v204) = 0;
    if ( !v14 )
    {
      updated = 722;
      goto LABEL_665;
    }
    v186 = EapConvertWireToHostFormat16(&v15[1].Length[1]);
    updated = CheckForUnsupportedMandatoryTLV((struct _EAP_TLV *)&v15[2].Id, v186 - 5, (int *)&v204, 1);
    if ( updated )
    {
LABEL_665:
      v103 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_131;
      v105 = 409;
      goto LABEL_312;
    }
    if ( (_DWORD)v204 )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 410, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      v32 = v200;
      v187 = v201;
      *((_BYTE *)a1 + 16) = v15->Id;
      CreatePEAPTLVNAKMessage(a1, v200, v187);
      *(_DWORD *)a1 = 9;
      updated = 0;
      goto LABEL_317;
    }
    *((_BYTE *)a1 + 16) = v15->Id;
    updated = GetPEAPTLVStatusMessageValue(v15, &v205);
    if ( updated )
    {
      v91 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_131;
      v92 = 411;
      goto LABEL_268;
    }
    if ( v205 == 2 )
    {
      v32 = v200;
      CreatePEAPTLVStatusMessage(a1, v200, v201, 0, 2u);
      *(_DWORD *)a1 = 8;
      goto LABEL_317;
    }
    if ( (*((_DWORD *)a1 + 1) & 0x400) != 0 )
    {
      if ( (*(_BYTE *)(*((_QWORD *)a1 + 343) + 8LL) & 8) != 0 )
      {
        v188 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v189 = 412;
          goto LABEL_680;
        }
LABEL_695:
        v32 = v200;
        updated = CreatePEAPTLVStatusMessage(a1, v200, v201, 0, 2u);
        if ( !updated )
        {
          a5->Action = EAPACTION_Send;
          *(_DWORD *)a1 = 9;
          goto LABEL_173;
        }
        goto LABEL_81;
      }
      updated = dword_1800A5D88;
      if ( dword_1800A5D88 )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 413, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
        a5->dwAuthResultCode = updated;
        *(_DWORD *)a1 = 6;
        a5->Action = EAPACTION_Done;
        goto LABEL_98;
      }
      if ( dword_1800A5D84 )
      {
        if ( dword_1800A6200 )
        {
          v190 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 414, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
            v190 = WPP_GLOBAL_Control;
          }
          if ( !dword_1800A5D80 )
          {
            v191 = (const void **)((char *)a1 + 2792);
            updated = GetTLV((struct _PPP_EAP_PACKET *)((char *)v15 + 6), 0xCu, (struct _EAP_TLV **)a1 + 349);
            if ( updated )
              goto LABEL_98;
            if ( (*(_BYTE *)(*((_QWORD *)a1 + 326) + 12LL) & 4) != 0 && !*v191 )
            {
              if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 415, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
              goto LABEL_695;
            }
            v192 = (unsigned __int8 *)*v191;
            *((_DWORD *)a1 + 660) = 1;
            if ( v192 )
            {
              memset(v218, 0, sizeof(v218));
              Buf2 = 0;
              v217 = 0;
              CryptoBindingTLV = CreateCryptoBindingTLV(a1, v192 + 8, (struct _CRYPTO_BINDING_TLV *)&Buf2, 0, 1, 0);
              updated = CryptoBindingTLV;
              if ( CryptoBindingTLV )
              {
                v113 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  goto LABEL_98;
                v114 = 416;
LABEL_346:
                v115 = CryptoBindingTLV;
LABEL_347:
                WPP_SF_d(*((_QWORD *)v113 + 2), v114, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v115);
                goto LABEL_98;
              }
              if ( memcmp_0(*v191, &Buf2, 0x3Cu) )
              {
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 417, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                v32 = v200;
                InvalidCryptoBindingResponse = CreateInvalidCryptoBindingResponse(a1, v200, v201);
                updated = InvalidCryptoBindingResponse;
                if ( InvalidCryptoBindingResponse )
                {
                  v66 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                  {
                    v67 = 418;
LABEL_184:
                    WPP_SF_d(
                      *((_QWORD *)v66 + 2),
                      v67,
                      &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
                      InvalidCryptoBindingResponse);
                  }
                  goto LABEL_185;
                }
                v69 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                {
                  v70 = 419;
LABEL_188:
                  WPP_SF_(*((_QWORD *)v69 + 2), v70, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
                }
                goto LABEL_189;
              }
            }
            updated = GetEAPTLVAttributes(v15, &a5->pUserAttributes);
            if ( updated )
            {
              v91 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                goto LABEL_131;
              v92 = 420;
LABEL_268:
              WPP_SF_(*((_QWORD *)v91 + 2), v92, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
              goto LABEL_131;
            }
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 421, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
            a5->Action = EAPACTION_IndicateTLV;
            *((_DWORD *)a1 + 1) |= 0x20000u;
            *(_DWORD *)a1 = 10;
            *((_DWORD *)a1 + 656) = a5->dwAuthResultCode;
            *((_DWORD *)a1 + 659) = 1;
            *((_QWORD *)a1 + 347) = a5->pUserAttributes;
            v179 = SavePEAPUserCreds(a1, a5);
            v113 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
              goto LABEL_98;
            v114 = 422;
LABEL_572:
            v115 = v179;
            goto LABEL_347;
          }
          if ( v190 == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_695;
          WPP_SF_d(
            *((_QWORD *)v190 + 2),
            423,
            &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids,
            (unsigned int)dword_1800A5D80);
        }
        else
        {
          v188 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            goto LABEL_695;
          v189 = 424;
LABEL_680:
          WPP_SF_(*((_QWORD *)v188 + 2), v189, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
        }
      }
    }
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 425, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
    goto LABEL_695;
  }
  if ( v185 >= 7u && v15[1].Id == 1 )
  {
    v32 = v200;
    updated = CreateIdentityResponse(v200, v201, v15->Id, a1);
    if ( updated )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 426, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
    }
    else
    {
      a5->Action = EAPACTION_Send;
      v193 = v200->Id;
      *(_DWORD *)a1 = 4;
      *((_BYTE *)a1 + 16) = v193;
      getDefaultCapIfBypassNegot((unsigned int *)a1 + 725);
    }
    goto LABEL_81;
  }
  if ( *(_DWORD *)a1 == 1 )
  {
    v194 = *((_QWORD *)a1 + 352);
    if ( *(_DWORD *)v194 == 4 && !*(_BYTE *)(v194 + 849) )
    {
      if ( v201 < 5 )
      {
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 427, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v201);
        updated = -2147319786;
        goto LABEL_98;
      }
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 428, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      v32 = v200;
      v200->Id = v15->Id;
      v200->Code = 2;
      EapConvertHostToWireFormat16(6, v200->Length);
      *(_WORD *)v200->Data = 25;
      a5->Action = EAPACTION_Send;
      goto LABEL_256;
    }
  }
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 429, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
  updated = 0;
LABEL_208:
  a5->Action = EAPACTION_NoAction;
LABEL_209:
  v32 = v200;
LABEL_210:
  v33 = 1;
LABEL_82:
  if ( *(_DWORD *)a1 == 4 && v33 && *((_DWORD *)a1 + 735) == 1 )
    *((_DWORD *)a1 + 735) = 0;
LABEL_86:
  v34 = IsInnFragmSuppState(v208);
  v35 = v210;
  if ( (v34 || v201 > v210) && (*((_BYTE *)a1 + 2900) & 1) != 0 && (unsigned int)(a5->Action - 3) <= 3 )
  {
    v36 = EapConvertWireToHostFormat16(v32->Length);
    if ( (unsigned int)v36 > *((_DWORD *)a1 + 726) )
    {
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 529, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
      updated = 0;
      a5->Action = EAPACTION_NoAction;
    }
    else if ( v36 <= v35 )
    {
      memcpy_0(v212, v32, v36);
    }
    else
    {
      updated = UpdateCBbyFragment(a1, v32, v212, v35);
    }
  }
LABEL_767:
  if ( v211 )
  {
    if ( !RevertToSelf() )
    {
      v199 = GetLastError();
      updated = v199;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 530, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids, v199);
    }
  }
LABEL_12:
  if ( hMem )
    LocalFree(hMem);
  if ( v15 && !v209 )
    LocalFree(v15);
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 531, &WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids);
  return updated;
}

```

## disassembly

```asm
0x180008b28  push    rbp
0x180008b2a  push    rbx
0x180008b2b  push    rsi
0x180008b2c  push    rdi
0x180008b2d  push    r12
0x180008b2f  push    r13
0x180008b31  push    r14
0x180008b33  push    r15
0x180008b35  lea     rbp, [rsp-138h]
0x180008b3d  sub     rsp, 238h
0x180008b44  mov     rax, cs:__security_cookie
0x180008b4b  xor     rax, rsp
0x180008b4e  mov     [rbp+170h+var_50], rax
0x180008b55  mov     rsi, [rbp+170h+arg_20]
0x180008b5c  mov     r14, r8
0x180008b5f  mov     r15, [rbp+170h+arg_28]
0x180008b66  mov     rbx, rdx
0x180008b69  mov     [rbp+170h+var_1D0], r8
0x180008b6d  mov     rdi, rcx
0x180008b70  xor     edx, edx; Val
0x180008b72  mov     [rbp+170h+var_1D8], r9d
0x180008b76  mov     r8d, 98h; Size
0x180008b7c  lea     rcx, [rbp+170h+var_1B0]; void *
0x180008b80  mov     r12d, r9d
0x180008b83  call    memset_0
0x180008b88  mov     eax, [rdi]
0x180008b8a  xor     edx, edx
0x180008b8c  mov     [rbp+170h+var_1C0], rdx
0x180008b90  mov     [rbp+170h+hMem], rdx
0x180008b94  mov     [rsp+270h+var_1F8], dx
0x180008b99  mov     [rbp+170h+var_1DC], edx
0x180008b9c  mov     [rsp+270h+var_210], r12d
0x180008ba1  mov     [rbp+170h+var_1E0], eax
0x180008ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bab  lea     r12, WPP_GLOBAL_Control
0x180008bb2  lea     r13, [rdi+4]
0x180008bb6  cmp     rcx, r12
0x180008bb9  jz      short loc_180008BDD
0x180008bbb  mov     r9d, [r13+0]
0x180008bbf  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180008bc6  mov     rcx, [rcx+10h]
0x180008bca  mov     edx, 18Eh
0x180008bcf  call    WPP_SF_d
0x180008bd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bdb  xor     edx, edx
0x180008bdd  test    r14, r14
0x180008be0  jnz     short loc_180008C06
0x180008be2  cmp     rcx, r12
0x180008be5  jz      short loc_180008BFC
0x180008be7  mov     rcx, [rcx+10h]
0x180008beb  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180008bf2  mov     edx, 18Fh
0x180008bf7  call    WPP_SF_
0x180008bfc  mov     eax, 57h ; 'W'
0x180008c01  jmp     loc_180008CAC
0x180008c06  test    dword ptr [r13+0], 1000CBh
0x180008c0e  mov     r14, rdx
0x180008c11  mov     [rbp+170h+var_1D4], edx
0x180008c14  jnz     loc_180008CD6
0x180008c1a  mov     rcx, [rdi+8]; hToken
0x180008c1e  test    rcx, rcx
0x180008c21  jz      loc_180008CD6
0x180008c27  call    cs:__imp_ImpersonateLoggedOnUser
0x180008c2d  xor     edx, edx
0x180008c2f  test    eax, eax
0x180008c31  jnz     loc_180008CCF
0x180008c37  call    cs:__imp_GetLastError
0x180008c3d  mov     ebx, eax
0x180008c3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c46  cmp     rcx, r12
0x180008c49  jz      short loc_180008C63
0x180008c4b  mov     rcx, [rcx+10h]
0x180008c4f  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180008c56  mov     edx, 190h
0x180008c5b  mov     r9d, eax
0x180008c5e  call    WPP_SF_d
0x180008c63  xor     r13d, r13d
0x180008c66  mov     rcx, [rbp+170h+hMem]; hMem
0x180008c6a  test    rcx, rcx
0x180008c6d  jz      short loc_180008C75
0x180008c6f  call    cs:__imp_LocalFree
0x180008c75  test    r14, r14
0x180008c78  jz      short loc_180008C89
0x180008c7a  cmp     [rbp+170h+var_1DC], r13d
0x180008c7e  jnz     short loc_180008C89
0x180008c80  mov     rcx, r14; hMem
0x180008c83  call    cs:__imp_LocalFree
0x180008c89  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c90  cmp     rcx, r12
0x180008c93  jz      short loc_180008CAA
0x180008c95  mov     rcx, [rcx+10h]
0x180008c99  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180008ca0  mov     edx, 213h
0x180008ca5  call    WPP_SF_
0x180008caa  mov     eax, ebx
0x180008cac  mov     rcx, [rbp+170h+var_50]
0x180008cb3  xor     rcx, rsp; StackCookie
0x180008cb6  call    __security_check_cookie
0x180008cbb  add     rsp, 238h
0x180008cc2  pop     r15
0x180008cc4  pop     r14
0x180008cc6  pop     r13
0x180008cc8  pop     r12
0x180008cca  pop     rdi
0x180008ccb  pop     rsi
0x180008ccc  pop     rbx
0x180008ccd  pop     rbp
0x180008cce  retn
0x180008ccf  mov     [rbp+170h+var_1D4], 1
0x180008cd6  mov     dword ptr [rsp+270h+uBytes], edx
0x180008cda  mov     r12d, edx
0x180008cdd  test    rbx, rbx
0x180008ce0  jz      short loc_180008D16
0x180008ce2  mov     rcx, rbx; Src
0x180008ce5  call    ?CopyEapPacket@@YAPEAU_PPP_EAP_PACKET@@PEAU1@@Z; CopyEapPacket(_PPP_EAP_PACKET *)
0x180008cea  mov     r14, rax
0x180008ced  test    rax, rax
0x180008cf0  jnz     short loc_180008D01
0x180008cf2  xor     r13d, r13d
0x180008cf5  lea     ebx, [rax+8]
0x180008cf8  mov     [rsi+4], r13d
0x180008cfc  jmp     loc_18000C12C
0x180008d01  lea     rcx, [rbx+2]
0x180008d05  call    cs:__imp_EapConvertWireToHostFormat16
0x180008d0b  movzx   r12d, ax
0x180008d0f  xor     edx, edx
0x180008d11  mov     dword ptr [rsp+270h+uBytes], r12d
0x180008d16  mov     rax, [rbp+170h+var_1D0]
0x180008d1a  mov     ebx, edx
0x180008d1c  mov     ecx, [rbp+170h+var_1E0]
0x180008d1f  mov     [rsp+270h+var_218], rax
0x180008d24  call    ?IsInnFragmSuppState@@YAHW4_PEAP_STATE@@@Z; IsInnFragmSuppState(_PEAP_STATE)
0x180008d29  xor     r9d, r9d
0x180008d2c  lea     edx, [r9+1]
0x180008d30  test    eax, eax
0x180008d32  jz      short loc_180008DA6
0x180008d34  test    [rdi+0B54h], dl
0x180008d3a  jz      short loc_180008DA6
0x180008d3c  mov     eax, [rdi+0B2Ch]
0x180008d42  mov     [rsp+270h+var_210], eax
0x180008d46  mov     rax, [rdi+0B20h]
0x180008d4d  mov     [rsp+270h+var_218], rax
0x180008d52  test    r14, r14
0x180008d55  jz      short loc_180008DA6
0x180008d57  cmp     [r14], dl
0x180008d5a  jnz     short loc_180008DA6
0x180008d5c  lea     rcx, [r14+2]
0x180008d60  call    cs:__imp_EapConvertWireToHostFormat16
0x180008d66  mov     ecx, 6
0x180008d6b  xor     r9d, r9d
0x180008d6e  cmp     ax, cx
0x180008d71  jb      short loc_180008DA1
0x180008d73  cmp     byte ptr [r14+4], 19h
0x180008d78  jnz     short loc_180008DA1
0x180008d7a  mov     al, [r14+5]
0x180008d7e  test    al, 40h
0x180008d80  jz      short loc_180008DA1
0x180008d82  test    al, al
0x180008d84  jns     short loc_180008DA1
0x180008d86  cmp     [rbp+170h+var_1E0], 0Eh
0x180008d8a  jz      short loc_180008DA1
0x180008d8c  mov     rcx, rdi; struct _PEAP_CONTROL_BLOCK *
0x180008d8f  call    ?UpdateCbByReassembly@@YAKPEAU_PEAP_CONTROL_BLOCK@@@Z; UpdateCbByReassembly(_PEAP_CONTROL_BLOCK *)
0x180008d94  xor     r9d, r9d
0x180008d97  mov     ebx, eax
0x180008d99  test    eax, eax
0x180008d9b  jnz     loc_18000C129
0x180008da1  mov     edx, 1
0x180008da6  mov     [rsp+270h+var_220], edx
0x180008daa  mov     ecx, [rdi]
0x180008dac  mov     eax, 7
0x180008db1  cmp     ecx, eax
0x180008db3  jg      loc_180008FA3
0x180008db9  jz      loc_18000AB53
0x180008dbf  test    ecx, ecx
0x180008dc1  jz      loc_18000AA70
0x180008dc7  sub     ecx, 1
0x180008dca  jnz     loc_18000922B
0x180008dd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180008dd7  lea     rax, WPP_GLOBAL_Control
0x180008dde  cmp     rcx, rax
0x180008de1  jz      short loc_180008DFD
0x180008de3  mov     rcx, [rcx+10h]
0x180008de7  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180008dee  mov     edx, 194h
0x180008df3  call    WPP_SF_
0x180008df8  mov     edx, 1
0x180008dfd  test    r14, r14
0x180008e00  jz      short loc_180008E10
0x180008e02  mov     al, [r14]
0x180008e05  sub     al, dl
0x180008e07  cmp     al, dl
0x180008e09  ja      short loc_180008E10
0x180008e0b  mov     byte ptr [r14+4], 0Dh
0x180008e10  mov     r9d, [rsp+270h+var_210]; unsigned int
0x180008e15  mov     rdx, r14; struct _EAPTLS_PACKET *
0x180008e18  mov     r8, [rsp+270h+var_218]; struct _EAPTLS_PACKET *
0x180008e1d  mov     rcx, [rdi+0B00h]; struct _EAPTLS_CONTROL_BLOCK *
0x180008e24  mov     [rsp+270h+var_248], r15; struct _PPP_EAP_INPUT *
0x180008e29  mov     [rsp+270h+var_250], rsi; struct _PPP_EAP_OUTPUT *
0x180008e2e  call    ?EapTlsCMakeMessage@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@PEAU_EAPTLS_PACKET@@1KPEAU_PPP_EAP_OUTPUT@@PEAU_PPP_EAP_INPUT@@@Z; EapTlsCMakeMessage(_EAPTLS_CONTROL_BLOCK *,_EAPTLS_PACKET *,_EAPTLS_PACKET *,ulong,_PPP_EAP_OUTPUT *,_PPP_EAP_INPUT *)
0x180008e33  mov     ebx, eax
0x180008e35  xor     eax, eax
0x180008e37  test    ebx, ebx
0x180008e39  jnz     loc_1800092D3
0x180008e3f  cmp     [rsi+18h], eax
0x180008e42  jnz     loc_18000912B
0x180008e48  cmp     dword ptr [rsi+4], 2
0x180008e4c  jnz     loc_180009089
0x180008e52  cmp     [rsi+8], eax
0x180008e55  jnz     loc_1800092D3
0x180008e5b  mov     rcx, [rdi+0B00h]; struct _EAPTLS_CONTROL_BLOCK *
0x180008e62  test    dword ptr [rcx+4], 2000h
0x180008e69  jnz     short loc_180008E70
0x180008e6b  call    ?SetCachedCredentials@@YAXPEAU_EAPTLS_CONTROL_BLOCK@@@Z; SetCachedCredentials(_EAPTLS_CONTROL_BLOCK *)
0x180008e70  mov     rax, [rsi+10h]
0x180008e74  mov     rcx, rdi; struct _PEAP_CONTROL_BLOCK *
0x180008e77  mov     [rdi+0AC0h], rax
0x180008e7e  mov     qword ptr [rsi+10h], 0
0x180008e86  call    ?PeapGetTunnelProperties@@YAKPEAU_PEAP_CONTROL_BLOCK@@@Z; PeapGetTunnelProperties(_PEAP_CONTROL_BLOCK *)
0x180008e8b  mov     ebx, eax
0x180008e8d  test    eax, eax
0x180008e8f  jnz     loc_1800092D3
0x180008e95  mov     rcx, [rdi+0B00h]; struct _EAPTLS_CONTROL_BLOCK *
0x180008e9c  lea     r9, dword_1800A5D84; int *
0x180008ea3  lea     r8, dword_1800A6200; unsigned int *
0x180008eaa  lea     rdx, [rbp+170h+hMem]; unsigned __int8 **
0x180008eae  call    ?GetTLSSessionCookie@@YAKPEAU_EAPTLS_CONTROL_BLOCK@@PEAPEAEPEAKPEAH@Z; GetTLSSessionCookie(_EAPTLS_CONTROL_BLOCK *,uchar * *,ulong *,int *)
0x180008eb3  xor     r9d, r9d
0x180008eb6  mov     cs:dword_1800A5D88, eax
0x180008ebc  test    eax, eax
0x180008ebe  jnz     short loc_180008EED
0x180008ec0  mov     r8d, cs:dword_1800A6200; unsigned int
0x180008ec7  test    r8d, r8d
0x180008eca  jz      short loc_180008EED
0x180008ecc  mov     rdx, [rbp+170h+hMem]; struct _PEAP_COOKIE *
0x180008ed0  mov     rcx, rdi; struct _PEAP_CONTROL_BLOCK *
0x180008ed3  call    ?PeapCheckCookie@@YAKPEAU_PEAP_CONTROL_BLOCK@@PEAU_PEAP_COOKIE@@K@Z; PeapCheckCookie(_PEAP_CONTROL_BLOCK *,_PEAP_COOKIE *,ulong)
0x180008ed8  mov     cs:dword_1800A5D80, eax
0x180008ede  xor     r9d, r9d
0x180008ee1  mov     rax, [rbp+170h+hMem]
0x180008ee5  mov     ecx, [rax+40Ch]
0x180008eeb  jmp     short loc_180008EF0
0x180008eed  mov     ecx, r9d
0x180008ef0  mov     [rdi+0B54h], ecx
0x180008ef6  mov     [rsi+4], r9d
0x180008efa  cmp     [rsi+2Ch], r9d
0x180008efe  jz      short loc_180008F2D
0x180008f00  mov     rcx, [rsi+30h]; struct _EAPTLS_CONN_PROPERTIES *
0x180008f04  lea     rdx, [rdi+0A20h]; struct _EAPTLS_CONN_PROPERTIES_V1 **
0x180008f0b  call    ?ConnPropGetV1Struct@@YAKPEAU_EAPTLS_CONN_PROPERTIES@@PEAPEAU_EAPTLS_CONN_PROPERTIES_V1@@@Z; ConnPropGetV1Struct(_EAPTLS_CONN_PROPERTIES *,_EAPTLS_CONN_PROPERTIES_V1 * *)
0x180008f10  xor     r9d, r9d
0x180008f13  test    eax, eax
0x180008f15  jnz     short loc_180008F21
0x180008f17  mov     dword ptr [rdi+0A18h], 1
0x180008f21  mov     [rsi+2Ch], r9d
0x180008f25  mov     [rsi+30h], r9
0x180008f29  mov     [rsi+38h], r9d
0x180008f2d  mov     edx, 1
0x180008f32  cmp     [rsi+3Ch], r9d
0x180008f36  jz      short loc_180008F46
0x180008f38  mov     [rdi+0A38h], edx
0x180008f3e  mov     [rsi+40h], r9
0x180008f42  mov     [rsi+48h], r9d
0x180008f46  cmp     [rdi], edx
0x180008f48  jnz     loc_18000B835
0x180008f4e  test    [rdi+0B54h], dl
0x180008f54  jz      loc_18000B835
0x180008f5a  mov     eax, [rdi+0B2Ch]
0x180008f60  mov     [rsp+270h+var_210], eax
0x180008f64  mov     rax, [rdi+0B20h]
0x180008f6b  mov     [rsp+270h+var_218], rax
0x180008f70  mov     al, [r14+5]
0x180008f74  test    al, 40h
0x180008f76  jz      loc_18000B835
0x180008f7c  test    al, al
0x180008f7e  jns     loc_18000B835
0x180008f84  mov     rcx, rdi; struct _PEAP_CONTROL_BLOCK *
0x180008f87  call    ?UpdateCbByReassembly@@YAKPEAU_PEAP_CONTROL_BLOCK@@@Z; UpdateCbByReassembly(_PEAP_CONTROL_BLOCK *)
0x180008f8c  xor     r9d, r9d
0x180008f8f  mov     ebx, eax
0x180008f91  test    eax, eax
0x180008f93  jnz     loc_18000C129
0x180008f99  mov     edx, 1
0x180008f9e  jmp     loc_180008DAA
0x180008fa3  sub     ecx, 8
0x180008fa6  jz      loc_18000BF5A
0x180008fac  sub     ecx, 1
0x180008faf  jz      short loc_180008F46
0x180008fb1  sub     ecx, 1
0x180008fb4  jz      loc_18000B598
0x180008fba  sub     ecx, 4
0x180008fbd  jnz     loc_18000B448
0x180008fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fca  lea     rax, WPP_GLOBAL_Control
0x180008fd1  cmp     rcx, rax
0x180008fd4  jz      short loc_180008FF7
0x180008fd6  mov     rcx, [rcx+10h]
0x180008fda  lea     r8, WPP_86dfd8e07fac39eb87041706834f74ed_Traceguids
0x180008fe1  mov     edx, 1B3h
  ... truncated ...
```
