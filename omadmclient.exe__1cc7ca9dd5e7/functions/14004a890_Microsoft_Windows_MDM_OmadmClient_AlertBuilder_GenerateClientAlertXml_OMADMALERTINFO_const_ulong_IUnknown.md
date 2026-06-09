# Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateClientAlertXml(OMADMALERTINFO const &,ulong,IUnknown *)

- ea: `0x14004a890`
- end: `0x14004b46e`
- name: `?GenerateClientAlertXml@AlertBuilder@OmadmClient@MDM@Windows@Microsoft@@UEAAJAEBUOMADMALERTINFO@@KPEAUIUnknown@@@Z`
- size: `3038`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::AlertBuilder *__hidden this, const struct OMADMALERTINFO *, unsigned int, struct IUnknown *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x14000d71c`
- `0x14000d778`
- `0x14000e610`
- `0x140013404`
- `0x14004a5fc`
- `0x14004a890`
- `0x140069010`

## import_xrefs

- `coredpus!__imp_GetElementName` at `0x14004aa6f`
- `coredpus!__imp_GetElementName` at `0x14004aade`
- `coredpus!__imp_GetElementName` at `0x14004ab55`
- `coredpus!__imp_GetElementName` at `0x14004abcb`
- `coredpus!__imp_GetElementName` at `0x14004ac47`
- `coredpus!__imp_GetElementName` at `0x14004acc6`
- `coredpus!__imp_GetElementName` at `0x14004ad37`
- `coredpus!__imp_GetElementName` at `0x14004ae03`
- `coredpus!__imp_GetElementName` at `0x14004ae74`
- `coredpus!__imp_GetElementName` at `0x14004af37`
- `coredpus!__imp_GetElementName` at `0x14004af4a`
- `coredpus!__imp_GetElementName` at `0x14004afec`
- `coredpus!__imp_GetElementName` at `0x14004b0e3`
- `coredpus!__imp_GetElementName` at `0x14004b1d7`
- `coredpus!__imp_GetElementName` at `0x14004b2a2`
- `coredpus!__imp_GetElementName` at `0x14004aa6f`
- `coredpus!__imp_GetElementName` at `0x14004aade`
- `coredpus!__imp_GetElementName` at `0x14004ab55`
- `coredpus!__imp_GetElementName` at `0x14004abcb`
- `coredpus!__imp_GetElementName` at `0x14004ac47`
- `coredpus!__imp_GetElementName` at `0x14004acc6`
- `coredpus!__imp_GetElementName` at `0x14004ad37`
- `coredpus!__imp_GetElementName` at `0x14004ae03`
- `coredpus!__imp_GetElementName` at `0x14004ae74`
- `coredpus!__imp_GetElementName` at `0x14004af37`
- `coredpus!__imp_GetElementName` at `0x14004af4a`
- `coredpus!__imp_GetElementName` at `0x14004afec`
- `coredpus!__imp_GetElementName` at `0x14004b0e3`
- `coredpus!__imp_GetElementName` at `0x14004b1d7`
- `coredpus!__imp_GetElementName` at `0x14004b2a2`
- `coredpus!__imp_GetDataTypeName` at `0x14004b0cf`
- `coredpus!__imp_GetDataTypeName` at `0x14004b0cf`
- `coredpus!__imp_AddSubnode` at `0x14004ab00`
- `coredpus!__imp_AddSubnode` at `0x14004ab70`
- `coredpus!__imp_AddSubnode` at `0x14004abea`
- `coredpus!__imp_AddSubnode` at `0x14004ad56`
- `coredpus!__imp_AddSubnode` at `0x14004ae93`
- `coredpus!__imp_AddSubnode` at `0x14004b00c`
- `coredpus!__imp_AddSubnode` at `0x14004b103`
- `coredpus!__imp_AddSubnode` at `0x14004b1f7`
- `coredpus!__imp_AddSubnode` at `0x14004b2c1`
- `coredpus!__imp_AddSubnode` at `0x14004ab00`
- `coredpus!__imp_AddSubnode` at `0x14004ab70`
- `coredpus!__imp_AddSubnode` at `0x14004abea`
- `coredpus!__imp_AddSubnode` at `0x14004ad56`
- `coredpus!__imp_AddSubnode` at `0x14004ae93`
- `coredpus!__imp_AddSubnode` at `0x14004b00c`
- `coredpus!__imp_AddSubnode` at `0x14004b103`
- `coredpus!__imp_AddSubnode` at `0x14004b1f7`
- `coredpus!__imp_AddSubnode` at `0x14004b2c1`
- `coredpus!__imp_GetMarkName` at `0x14004b1c3`
- `coredpus!__imp_GetMarkName` at `0x14004b1c3`
- `DMCmnUtils!InvStrCmpW` at `0x14004af6d`
- `DMCmnUtils!InvStrCmpW` at `0x14004af6d`

## string_xrefs

- `0x14004a8d5`: `GenerateClientAlertXml`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::AlertBuilder::GenerateClientAlertXml(
        Microsoft::Windows::MDM::OmadmClient::AlertBuilder *this,
        const struct OMADMALERTINFO *a2,
        int a3,
        struct IUnknown *a4)
{
  __int64 v7; // r8
  char v8; // al
  struct IXmlWriter *v9; // rcx
  unsigned int v10; // edi
  bool v11; // zf
  __int64 v12; // r9
  int v13; // eax
  struct IXmlWriter *v14; // rbx
  int v15; // eax
  bool v16; // zf
  __int64 ElementName; // rax
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  int v21; // edi
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rdi
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // eax
  __int64 v31; // rdi
  __int64 v32; // rax
  int v33; // eax
  int v34; // eax
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rdi
  __int64 v38; // rax
  int v39; // eax
  int v40; // eax
  int v41; // r14d
  __int64 v42; // r15
  __int64 v43; // r12
  const unsigned __int16 *v44; // rcx
  int v45; // eax
  __int64 v46; // rdi
  __int64 v47; // rax
  int v48; // eax
  int v49; // eax
  int DataTypeName; // edi
  __int64 v51; // rax
  int v52; // eax
  int v53; // eax
  int MarkName; // edi
  __int64 v55; // rax
  int v56; // eax
  int v57; // eax
  __int64 v58; // rdi
  __int64 v59; // rax
  int v60; // eax
  int v61; // eax
  int v62; // eax
  unsigned int v63; // eax
  __int64 v64; // rdx
  __int64 v65; // r8
  int v67; // [rsp+20h] [rbp-98h]
  int v68; // [rsp+20h] [rbp-98h]
  unsigned int v69; // [rsp+30h] [rbp-88h] BYREF
  struct IXmlWriter *v70; // [rsp+38h] [rbp-80h] BYREF
  _QWORD v71[3]; // [rsp+40h] [rbp-78h] BYREF
  int v72; // [rsp+58h] [rbp-60h]
  unsigned int *v73; // [rsp+60h] [rbp-58h]
  struct _EVENT_DATA_DESCRIPTOR v74; // [rsp+68h] [rbp-50h] BYREF
  struct IXmlWriter **v75; // [rsp+78h] [rbp-40h]
  __int64 v76; // [rsp+80h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v69 = 0;
  v71[0] = 0;
  v71[1] = "GenerateClientAlertXml";
  v71[2] = COmaDmLogger::GetLogger();
  v72 = 2;
  v73 = &v69;
  v8 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
  if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
  {
    LODWORD(v70) = 38;
    v75 = &v70;
    v76 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_OMADM_CLIENT_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)OmaDmClientFunctionEntryPointEvent,
      v7,
      2u,
      &v74);
    v8 = Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits;
  }
  v74.Ptr = (ULONGLONG)&v69;
  LOBYTE(v74.Size) = 1;
  v9 = (struct IXmlWriter *)(unsigned int)(*((_DWORD *)a2 + 1) - 1200);
  if ( (unsigned int)v9 <= 1 )
  {
    if ( *((_QWORD *)a2 + 3) )
    {
      LODWORD(v71[0]) = 3003;
      goto LABEL_6;
    }
  }
  else if ( !*((_QWORD *)a2 + 3) )
  {
    LODWORD(v71[0]) = 3002;
LABEL_6:
    v10 = -2147418113;
    HIDWORD(v71[0]) = -2147418113;
    v11 = (v8 & 8) == 0;
    goto LABEL_7;
  }
  v70 = 0;
  v13 = Microsoft::Windows::MDM::OmadmClient::AlertBuilder::CreateXmlWriterHelper(&v70);
  v10 = v13;
  v69 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19A,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
      (const char *)(unsigned int)v13,
      v67);
    v9 = v70;
    if ( v70 )
      ((void (__fastcall *)(struct IXmlWriter *))v70->lpVtbl->Release)(v70);
    v11 = (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) == 0;
LABEL_7:
    if ( !v11 )
    {
      v12 = v69;
LABEL_126:
      McTemplateU0qq_EventWriteTransfer(v9, OmaDmClientFunctionReturnValueEvent, 38, v12);
      goto LABEL_127;
    }
    goto LABEL_127;
  }
  v14 = v70;
  v15 = ((__int64 (__fastcall *)(struct IXmlWriter *, struct IUnknown *))v70->lpVtbl->SetOutput)(v70, a4);
  v10 = v15;
  v69 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
      (const char *)(unsigned int)v15,
      v67);
    if ( v14 )
      ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
LABEL_18:
    v16 = (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) == 0;
    goto LABEL_19;
  }
  ElementName = GetElementName(27);
  v18 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, __int64, _QWORD))v14->lpVtbl->WriteStartElement)(
          v14,
          0,
          ElementName,
          0);
  v10 = v18;
  v69 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
      (const char *)(unsigned int)v18,
      v67);
    if ( v14 )
      ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
    goto LABEL_18;
  }
  v19 = GetElementName(5);
  v20 = AddSubnode(v14, 0, v19, 1);
  v10 = v20;
  v69 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
      (const char *)(unsigned int)v20,
      a3);
    if ( v14 )
      ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
    goto LABEL_18;
  }
  v21 = *((_DWORD *)a2 + 1);
  v22 = GetElementName(21);
  v68 = v21;
  v23 = AddSubnode(v14, 0, v22, 1);
  v10 = v23;
  v69 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
      (const char *)(unsigned int)v23,
      v68);
    if ( v14 )
      ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
    goto LABEL_18;
  }
  v24 = *((_QWORD *)a2 + 5);
  if ( v24 )
  {
    v25 = GetElementName(24);
    v68 = v24;
    v26 = AddSubnode(v14, 0, v25, 2);
    v10 = v26;
    v69 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
        (const char *)(unsigned int)v26,
        v68);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      goto LABEL_18;
    }
  }
  if ( !*((_QWORD *)a2 + 3) )
    goto LABEL_115;
  v27 = GetElementName(22);
  v28 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, __int64, _QWORD))v14->lpVtbl->WriteStartElement)(
          v14,
          0,
          v27,
          0);
  v10 = v28;
  v69 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
      (const char *)(unsigned int)v28,
      v68);
    if ( v14 )
      ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
    goto LABEL_18;
  }
  if ( *((_QWORD *)a2 + 7) )
  {
    v29 = GetElementName(17);
    v30 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, __int64, _QWORD))v14->lpVtbl->WriteStartElement)(
            v14,
            0,
            v29,
            0);
    v10 = v30;
    v69 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C0,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
        (const char *)(unsigned int)v30,
        v68);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      goto LABEL_18;
    }
    v31 = *((_QWORD *)a2 + 7);
    v32 = GetElementName(10);
    v68 = v31;
    v33 = AddSubnode(v14, 0, v32, 2);
    v10 = v33;
    v69 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
        (const char *)(unsigned int)v33,
        v68);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      goto LABEL_18;
    }
    v34 = ((__int64 (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->WriteEndElement)(v14);
    v10 = v34;
    v69 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C8,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
        (const char *)(unsigned int)v34,
        v68);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      goto LABEL_18;
    }
  }
  if ( *((_QWORD *)a2 + 2) )
  {
    v35 = GetElementName(15);
    v36 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, __int64, _QWORD))v14->lpVtbl->WriteStartElement)(
            v14,
            0,
            v35,
            0);
    v10 = v36;
    v69 = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D1,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
        (const char *)(unsigned int)v36,
        v68);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      goto LABEL_18;
    }
    v37 = *((_QWORD *)a2 + 2);
    v38 = GetElementName(10);
    v68 = v37;
    v39 = AddSubnode(v14, 0, v38, 2);
    v10 = v39;
    v69 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D5,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
        (const char *)(unsigned int)v39,
        v68);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      goto LABEL_18;
    }
    v40 = ((__int64 (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->WriteEndElement)(v14);
    v10 = v40;
    v69 = v40;
    if ( v40 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D9,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
        (const char *)(unsigned int)v40,
        v68);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      goto LABEL_18;
    }
  }
  v41 = 0;
  v42 = GetElementName(23);
  v43 = GetElementName(72);
  v44 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
  if ( !v44 || !InvStrCmpW(v44, L"text/plain") )
  {
LABEL_80:
    if ( *((_DWORD *)a2 + 8) != 1 )
    {
      if ( !v41 )
      {
        v49 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, __int64, _QWORD))v14->lpVtbl->WriteStartElement)(
                v14,
                0,
                v42,
                0);
        v10 = v49;
        v69 = v49;
        if ( v49 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1F8,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
            (const char *)(unsigned int)v49,
            v68);
          if ( v14 )
            ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
          goto LABEL_74;
        }
        v41 = 1;
      }
      DataTypeName = GetDataTypeName(*((unsigned int *)a2 + 8));
      v51 = GetElementName(44);
      v68 = DataTypeName;
      v52 = AddSubnode(v14, v43, v51, 2);
      v10 = v52;
      v69 = v52;
      if ( v52 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x203,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
          (const char *)(unsigned int)v52,
          v68);
        if ( v14 )
          ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
        goto LABEL_74;
      }
    }
    if ( *((_DWORD *)a2 + 9) )
    {
      if ( !v41 )
      {
        v53 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, __int64, _QWORD))v14->lpVtbl->WriteStartElement)(
                v14,
                0,
                v42,
                0);
        v10 = v53;
        v69 = v53;
        if ( v53 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x20D,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
            (const char *)(unsigned int)v53,
            v68);
          if ( v14 )
            ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
          goto LABEL_74;
        }
        v41 = 1;
      }
      MarkName = GetMarkName(*((unsigned int *)a2 + 9));
      v55 = GetElementName(48);
      v68 = MarkName;
      v56 = AddSubnode(v14, v43, v55, 2);
      v10 = v56;
      v69 = v56;
      if ( v56 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x214,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
          (const char *)(unsigned int)v56,
          v68);
        if ( v14 )
          ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
        goto LABEL_74;
      }
    }
    if ( v41 )
    {
      v57 = ((__int64 (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->WriteEndElement)(v14);
      v10 = v57;
      v69 = v57;
      if ( v57 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21B,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
          (const char *)(unsigned int)v57,
          v68);
        if ( v14 )
          ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
        goto LABEL_74;
      }
    }
    v58 = *((_QWORD *)a2 + 3);
    v59 = GetElementName(21);
    v68 = v58;
    v60 = AddSubnode(v14, 0, v59, 2);
    v10 = v60;
    v69 = v60;
    if ( v60 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x220,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
        (const char *)(unsigned int)v60,
        v68);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      goto LABEL_74;
    }
    v61 = ((__int64 (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->WriteEndElement)(v14);
    v10 = v61;
    v69 = v61;
    if ( v61 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x224,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
        (const char *)(unsigned int)v61,
        v68);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      goto LABEL_74;
    }
LABEL_115:
    v62 = ((__int64 (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->WriteEndElement)(v14);
    v10 = v62;
    v69 = v62;
    if ( v62 >= 0 )
    {
      v63 = ((__int64 (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Flush)(v14);
      v10 = v63;
      v12 = v63;
      v69 = v63;
      if ( (v63 & 0x80000000) == 0 )
      {
        if ( v14 )
        {
          ((void (__fastcall *)(struct IXmlWriter *, __int64, __int64, _QWORD))v14->lpVtbl->Release)(v14, v64, v65, v63);
          v12 = v69;
        }
        if ( (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) != 0 )
          goto LABEL_126;
        goto LABEL_127;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22D,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
        (const char *)v63,
        v68);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x229,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
        (const char *)(unsigned int)v62,
        v68);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
    }
    goto LABEL_18;
  }
  v45 = ((__int64 (__fastcall *)(struct IXmlWriter *, _QWORD, __int64, _QWORD))v14->lpVtbl->WriteStartElement)(
          v14,
          0,
          v42,
          0);
  v10 = v45;
  v69 = v45;
  if ( v45 >= 0 )
  {
    v46 = *((_QWORD *)a2 + 1);
    v47 = GetElementName(57);
    v68 = v46;
    v48 = AddSubnode(v14, v43, v47, 2);
    v10 = v48;
    v69 = v48;
    if ( v48 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1EE,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
        (const char *)(unsigned int)v48,
        v68);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      goto LABEL_74;
    }
    v41 = 1;
    goto LABEL_80;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E7,
    (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\alertbuilder.cpp",
    (const char *)(unsigned int)v45,
    v68);
  if ( v14 )
    ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
LABEL_74:
  v16 = (Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits & 8) == 0;
LABEL_19:
  if ( !v16 )
  {
    v12 = v69;
    goto LABEL_126;
  }
LABEL_127:
  Microsoft::Windows::TelemetryInfo::~TelemetryInfo((Microsoft::Windows::TelemetryInfo *)v71);
  return v10;
}

```

## disassembly

```asm
0x14004a890  mov     [rsp+arg_0], rbx
0x14004a895  push    rsi
0x14004a896  push    rdi
0x14004a897  push    r12
0x14004a899  push    r14
0x14004a89b  push    r15
0x14004a89d  sub     rsp, 90h
0x14004a8a4  mov     rax, cs:__security_cookie
0x14004a8ab  xor     rax, rsp
0x14004a8ae  mov     [rsp+0B8h+var_30], rax
0x14004a8b6  mov     r14, r9
0x14004a8b9  mov     r15d, r8d
0x14004a8bc  mov     rsi, rdx
0x14004a8bf  mov     [rsp+0B8h+var_88], 0
0x14004a8c7  call    ?GetLogger@COmaDmLogger@@SAPEAV1@XZ; COmaDmLogger::GetLogger(void)
0x14004a8cc  mov     [rsp+0B8h+var_78], 0
0x14004a8d5  lea     rcx, aGenerateclient_0; "GenerateClientAlertXml"
0x14004a8dc  mov     [rsp+0B8h+var_70], rcx
0x14004a8e1  mov     [rsp+0B8h+var_68], rax
0x14004a8e6  mov     ecx, 2
0x14004a8eb  mov     [rsp+0B8h+var_60], ecx
0x14004a8ef  lea     rax, [rsp+0B8h+var_88]
0x14004a8f4  mov     [rsp+0B8h+var_58], rax
0x14004a8f9  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x14004a8ff  lea     ebx, [rcx+24h]
0x14004a902  mov     r12b, 8
0x14004a905  test    r12b, al
0x14004a908  jz      short loc_14004A94A
0x14004a90a  mov     dword ptr [rsp+0B8h+var_80], ebx
0x14004a90e  lea     rax, [rsp+0B8h+var_80]
0x14004a913  mov     [rsp+0B8h+var_40], rax
0x14004a918  mov     [rsp+0B8h+var_38], 4
0x14004a924  lea     rax, [rsp+0B8h+var_50]
0x14004a929  mov     qword ptr [rsp+0B8h+var_98], rax; int
0x14004a92e  mov     r9d, ecx
0x14004a931  lea     rdx, OmaDmClientFunctionEntryPointEvent
0x14004a938  lea     rcx, WP_OMADM_CLIENT_PROVIDER_Context
0x14004a93f  call    McGenEventWrite_EventWriteTransfer
0x14004a944  mov     eax, cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits
0x14004a94a  lea     rcx, [rsp+0B8h+var_88]
0x14004a94f  mov     qword ptr [rsp+0B8h+var_50], rcx
0x14004a954  mov     [rsp+0B8h+var_48], 1
0x14004a959  mov     ecx, [rsi+4]
0x14004a95c  sub     ecx, 4B0h
0x14004a962  cmp     ecx, 1
0x14004a965  jbe     short loc_14004A995
0x14004a967  cmp     qword ptr [rsi+18h], 0
0x14004a96c  jnz     short loc_14004A9A6
0x14004a96e  mov     dword ptr [rsp+0B8h+var_78], 0BBAh
0x14004a976  mov     edi, 8000FFFFh
0x14004a97b  mov     dword ptr [rsp+0B8h+var_78+4], edi
0x14004a97f  test    r12b, al
0x14004a982  jz      loc_14004B439
0x14004a988  mov     r9d, [rsp+0B8h+var_88]
0x14004a98d  mov     r8d, ebx
0x14004a990  jmp     loc_14004B42C
0x14004a995  cmp     qword ptr [rsi+18h], 0
0x14004a99a  jz      short loc_14004A9A6
0x14004a99c  mov     dword ptr [rsp+0B8h+var_78], 0BBBh
0x14004a9a4  jmp     short loc_14004A976
0x14004a9a6  mov     [rsp+0B8h+var_80], 0
0x14004a9af  lea     rcx, [rsp+0B8h+var_80]; struct IXmlWriter **
0x14004a9b4  call    ?CreateXmlWriterHelper@AlertBuilder@OmadmClient@MDM@Windows@Microsoft@@KAJPEAPEAUIXmlWriter@@@Z; Microsoft::Windows::MDM::OmadmClient::AlertBuilder::CreateXmlWriterHelper(IXmlWriter * *)
0x14004a9b9  mov     edi, eax
0x14004a9bb  mov     [rsp+0B8h+var_88], eax
0x14004a9bf  test    eax, eax
0x14004a9c1  jns     short loc_14004AA00
0x14004a9c3  mov     rcx, [rsp+0B8h]; this
0x14004a9cb  mov     r9d, eax; char *
0x14004a9ce  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004a9d5  mov     edx, 19Ah; void *
0x14004a9da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004a9df  nop
0x14004a9e0  mov     rcx, [rsp+0B8h+var_80]
0x14004a9e5  test    rcx, rcx
0x14004a9e8  jz      short loc_14004A9F7
0x14004a9ea  mov     rax, [rcx]
0x14004a9ed  mov     rax, [rax+10h]
0x14004a9f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a9f6  nop
0x14004a9f7  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, r12b
0x14004a9fe  jmp     short loc_14004A982
0x14004aa00  mov     rbx, [rsp+0B8h+var_80]
0x14004aa05  mov     rax, [rbx]
0x14004aa08  mov     rdx, r14
0x14004aa0b  mov     rcx, rbx
0x14004aa0e  mov     rax, [rax+18h]
0x14004aa12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004aa17  mov     edi, eax
0x14004aa19  mov     [rsp+0B8h+var_88], eax
0x14004aa1d  test    eax, eax
0x14004aa1f  jns     short loc_14004AA6A
0x14004aa21  mov     rcx, [rsp+0B8h]; this
0x14004aa29  mov     r9d, eax; char *
0x14004aa2c  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004aa33  mov     edx, 19Dh; void *
0x14004aa38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004aa3d  nop
0x14004aa3e  test    rbx, rbx
0x14004aa41  jz      short loc_14004AA53
0x14004aa43  mov     rax, [rbx]
0x14004aa46  mov     rcx, rbx
0x14004aa49  mov     rax, [rax+10h]
0x14004aa4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004aa52  nop
0x14004aa53  test    byte ptr cs:Microsoft_WindowsPhone_OmaDm_Client_ProviderEnableBits, r12b
0x14004aa5a  jz      loc_14004B439
0x14004aa60  mov     r9d, [rsp+0B8h+var_88]
0x14004aa65  jmp     loc_14004B426
0x14004aa6a  mov     ecx, 1Bh
0x14004aa6f  call    cs:__imp_GetElementName
0x14004aa76  nop     dword ptr [rax+rax+00h]
0x14004aa7b  mov     rcx, [rbx]
0x14004aa7e  mov     r10, [rcx+0D8h]
0x14004aa85  xor     r9d, r9d
0x14004aa88  mov     r8, rax
0x14004aa8b  xor     edx, edx
0x14004aa8d  mov     rcx, rbx
0x14004aa90  mov     rax, r10
0x14004aa93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004aa98  mov     edi, eax
0x14004aa9a  mov     [rsp+0B8h+var_88], eax
0x14004aa9e  test    eax, eax
0x14004aaa0  jns     short loc_14004AAD9
0x14004aaa2  mov     rcx, [rsp+0B8h]; this
0x14004aaaa  mov     r9d, eax; char *
0x14004aaad  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004aab4  mov     edx, 1A2h; void *
0x14004aab9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004aabe  nop
0x14004aabf  test    rbx, rbx
0x14004aac2  jz      short loc_14004AAD4
0x14004aac4  mov     rax, [rbx]
0x14004aac7  mov     rcx, rbx
0x14004aaca  mov     rax, [rax+10h]
0x14004aace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004aad3  nop
0x14004aad4  jmp     loc_14004AA53
0x14004aad9  mov     ecx, 5
0x14004aade  call    cs:__imp_GetElementName
0x14004aae5  nop     dword ptr [rax+rax+00h]
0x14004aaea  mov     [rsp+0B8h+var_98], r15d; int
0x14004aaef  mov     r14d, 1
0x14004aaf5  mov     r9d, r14d
0x14004aaf8  mov     r8, rax
0x14004aafb  xor     edx, edx
0x14004aafd  mov     rcx, rbx
0x14004ab00  call    cs:__imp_AddSubnode
0x14004ab07  nop     dword ptr [rax+rax+00h]
0x14004ab0c  mov     edi, eax
0x14004ab0e  mov     [rsp+0B8h+var_88], eax
0x14004ab12  test    eax, eax
0x14004ab14  jns     short loc_14004AB4D
0x14004ab16  mov     rcx, [rsp+0B8h]; this
0x14004ab1e  mov     r9d, eax; char *
0x14004ab21  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004ab28  mov     edx, 1A6h; void *
0x14004ab2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004ab32  nop
0x14004ab33  test    rbx, rbx
0x14004ab36  jz      short loc_14004AB48
0x14004ab38  mov     rax, [rbx]
0x14004ab3b  mov     rcx, rbx
0x14004ab3e  mov     rax, [rax+10h]
0x14004ab42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ab47  nop
0x14004ab48  jmp     loc_14004AA53
0x14004ab4d  mov     edi, [rsi+4]
0x14004ab50  mov     ecx, 15h
0x14004ab55  call    cs:__imp_GetElementName
0x14004ab5c  nop     dword ptr [rax+rax+00h]
0x14004ab61  mov     [rsp+0B8h+var_98], edi; int
0x14004ab65  mov     r9d, r14d
0x14004ab68  mov     r8, rax
0x14004ab6b  xor     edx, edx
0x14004ab6d  mov     rcx, rbx
0x14004ab70  call    cs:__imp_AddSubnode
0x14004ab77  nop     dword ptr [rax+rax+00h]
0x14004ab7c  mov     edi, eax
0x14004ab7e  mov     [rsp+0B8h+var_88], eax
0x14004ab82  test    eax, eax
0x14004ab84  jns     short loc_14004ABBD
0x14004ab86  mov     rcx, [rsp+0B8h]; this
0x14004ab8e  mov     r9d, eax; char *
0x14004ab91  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004ab98  mov     edx, 1AAh; void *
0x14004ab9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004aba2  nop
0x14004aba3  test    rbx, rbx
0x14004aba6  jz      short loc_14004ABB8
0x14004aba8  mov     rax, [rbx]
0x14004abab  mov     rcx, rbx
0x14004abae  mov     rax, [rax+10h]
0x14004abb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004abb7  nop
0x14004abb8  jmp     loc_14004AA53
0x14004abbd  mov     rdi, [rsi+28h]
0x14004abc1  test    rdi, rdi
0x14004abc4  jz      short loc_14004AC37
0x14004abc6  mov     ecx, 18h
0x14004abcb  call    cs:__imp_GetElementName
0x14004abd2  nop     dword ptr [rax+rax+00h]
0x14004abd7  mov     qword ptr [rsp+0B8h+var_98], rdi; int
0x14004abdc  mov     r9d, 2
0x14004abe2  mov     r8, rax
0x14004abe5  xor     edx, edx
0x14004abe7  mov     rcx, rbx
0x14004abea  call    cs:__imp_AddSubnode
0x14004abf1  nop     dword ptr [rax+rax+00h]
0x14004abf6  mov     edi, eax
0x14004abf8  mov     [rsp+0B8h+var_88], eax
0x14004abfc  test    eax, eax
0x14004abfe  jns     short loc_14004AC37
0x14004ac00  mov     rcx, [rsp+0B8h]; this
0x14004ac08  mov     r9d, eax; char *
0x14004ac0b  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004ac12  mov     edx, 1B0h; void *
0x14004ac17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004ac1c  nop
0x14004ac1d  test    rbx, rbx
0x14004ac20  jz      short loc_14004AC32
0x14004ac22  mov     rax, [rbx]
0x14004ac25  mov     rcx, rbx
0x14004ac28  mov     rax, [rax+10h]
0x14004ac2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ac31  nop
0x14004ac32  jmp     loc_14004AA53
0x14004ac37  cmp     qword ptr [rsi+18h], 0
0x14004ac3c  jz      loc_14004B361
0x14004ac42  mov     ecx, 16h
0x14004ac47  call    cs:__imp_GetElementName
0x14004ac4e  nop     dword ptr [rax+rax+00h]
0x14004ac53  mov     rcx, [rbx]
0x14004ac56  mov     r10, [rcx+0D8h]
0x14004ac5d  xor     r9d, r9d
0x14004ac60  mov     r8, rax
0x14004ac63  xor     edx, edx
0x14004ac65  mov     rcx, rbx
0x14004ac68  mov     rax, r10
0x14004ac6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ac70  mov     edi, eax
0x14004ac72  mov     [rsp+0B8h+var_88], eax
0x14004ac76  test    eax, eax
0x14004ac78  jns     short loc_14004ACB1
0x14004ac7a  mov     rcx, [rsp+0B8h]; this
0x14004ac82  mov     r9d, eax; char *
0x14004ac85  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004ac8c  mov     edx, 1B8h; void *
0x14004ac91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004ac96  nop
0x14004ac97  test    rbx, rbx
0x14004ac9a  jz      short loc_14004ACAC
0x14004ac9c  mov     rax, [rbx]
0x14004ac9f  mov     rcx, rbx
0x14004aca2  mov     rax, [rax+10h]
0x14004aca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004acab  nop
0x14004acac  jmp     loc_14004AA53
0x14004acb1  mov     r14d, 0Ah
0x14004acb7  cmp     qword ptr [rsi+38h], 0
0x14004acbc  jz      loc_14004ADF3
0x14004acc2  lea     ecx, [r14+7]
0x14004acc6  call    cs:__imp_GetElementName
0x14004accd  nop     dword ptr [rax+rax+00h]
0x14004acd2  mov     rcx, [rbx]
0x14004acd5  mov     r10, [rcx+0D8h]
0x14004acdc  xor     r9d, r9d
0x14004acdf  mov     r8, rax
0x14004ace2  xor     edx, edx
0x14004ace4  mov     rcx, rbx
0x14004ace7  mov     rax, r10
0x14004acea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004acef  mov     edi, eax
0x14004acf1  mov     [rsp+0B8h+var_88], eax
0x14004acf5  test    eax, eax
0x14004acf7  jns     short loc_14004AD30
0x14004acf9  mov     rcx, [rsp+0B8h]; this
0x14004ad01  mov     r9d, eax; char *
0x14004ad04  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14004ad0b  mov     edx, 1C0h; void *
0x14004ad10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004ad15  nop
0x14004ad16  test    rbx, rbx
0x14004ad19  jz      short loc_14004AD2B
0x14004ad1b  mov     rax, [rbx]
0x14004ad1e  mov     rcx, rbx
0x14004ad21  mov     rax, [rax+10h]
0x14004ad25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004ad2a  nop
0x14004ad2b  jmp     loc_14004AA53
0x14004ad30  mov     rdi, [rsi+38h]
0x14004ad34  mov     ecx, r14d
0x14004ad37  call    cs:__imp_GetElementName
0x14004ad3e  nop     dword ptr [rax+rax+00h]
0x14004ad43  mov     qword ptr [rsp+0B8h+var_98], rdi; int
0x14004ad48  mov     r9d, 2
0x14004ad4e  mov     r8, rax
0x14004ad51  xor     edx, edx
0x14004ad53  mov     rcx, rbx
0x14004ad56  call    cs:__imp_AddSubnode
  ... truncated ...
```
