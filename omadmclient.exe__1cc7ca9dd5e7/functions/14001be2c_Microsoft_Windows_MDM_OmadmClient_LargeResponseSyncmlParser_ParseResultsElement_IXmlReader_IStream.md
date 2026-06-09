# Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::ParseResultsElement(IXmlReader *,IStream *)

- ea: `0x14001be2c`
- end: `0x14001ccef`
- name: `?ParseResultsElement@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEAUIXmlReader@@PEAUIStream@@@Z`
- size: `3779`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *__hidden this, struct IXmlReader *, struct IStream *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001cff0`

## callees

- `0x140003450`
- `0x14000b0f4`
- `0x140019d40`
- `0x14001a84c`
- `0x14001adb8`
- `0x14001b308`
- `0x14001be2c`
- `0x14001d5b0`
- `0x14001d758`
- `0x140069010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001c0c2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001c171`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001c190`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001c1af`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001c0c2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001c171`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001c190`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001c1af`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x14001c367`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x14001c367`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::ParseResultsElement(
        Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *this,
        struct IXmlReader *a2,
        struct IStream *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // eax
  unsigned int v10; // edx
  struct IXmlWriter *v11; // rbx
  struct IXmlWriter *v12; // rdi
  int v13; // eax
  unsigned int v14; // esi
  unsigned int v15; // eax
  struct IStream *v16; // r15
  int IsLessThanMax; // eax
  int v18; // edx
  struct IStream *v19; // rsi
  int v20; // eax
  unsigned int v21; // r14d
  unsigned int v22; // edx
  int v23; // eax
  int v24; // eax
  int v25; // eax
  unsigned int v26; // edx
  unsigned int v27; // edx
  __int64 v28; // rdx
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  HRESULT v34; // eax
  int v35; // eax
  unsigned int v36; // r12d
  __int64 v37; // rdx
  int v38; // eax
  int v39; // eax
  unsigned int v40; // eax
  int v41; // eax
  int v42; // eax
  int v43; // [rsp+20h] [rbp-79h]
  int v44; // [rsp+20h] [rbp-79h]
  __int64 v45; // [rsp+40h] [rbp-59h] BYREF
  int v46; // [rsp+48h] [rbp-51h] BYREF
  int v47; // [rsp+4Ch] [rbp-4Dh] BYREF
  int v48; // [rsp+50h] [rbp-49h]
  int v49; // [rsp+54h] [rbp-45h]
  __int64 v50; // [rsp+58h] [rbp-41h] BYREF
  IStream *pstm; // [rsp+60h] [rbp-39h] BYREF
  struct IStream *v52; // [rsp+68h] [rbp-31h] BYREF
  struct IXmlWriter *v53; // [rsp+70h] [rbp-29h] BYREF
  struct IStream *v54; // [rsp+78h] [rbp-21h]
  int v55; // [rsp+80h] [rbp-19h] BYREF
  int v56; // [rsp+84h] [rbp-15h] BYREF
  struct IXmlWriter *v57; // [rsp+88h] [rbp-11h] BYREF
  ULARGE_INTEGER pui; // [rsp+90h] [rbp-9h] BYREF
  struct IXmlWriter *v59[2]; // [rsp+98h] [rbp-1h] BYREF
  char v60[16]; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v54 = a3;
  v46 = 0;
  pui.QuadPart = 0;
  *(_QWORD *)((char *)this + 44) = 0;
  *((_DWORD *)this + 13) = 0;
  pstm = 0;
  v53 = 0;
  v6 = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreateTempWriterAndStream(&pstm, &v53);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x532,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v6,
      v43);
    if ( v53 )
      ((void (__fastcall *)(struct IXmlWriter *))v53->lpVtbl->Release)(v53);
    if ( pstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
    return v7;
  }
  v52 = 0;
  v57 = 0;
  v9 = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreateTempWriterAndStream(&v52, &v57);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x538,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v9,
      v43);
    if ( v57 )
      ((void (__fastcall *)(struct IXmlWriter *))v57->lpVtbl->Release)(v57);
    if ( v52 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v52 + 16LL))(v52);
    if ( v53 )
      ((void (__fastcall *)(struct IXmlWriter *))v53->lpVtbl->Release)(v53);
    if ( pstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
    return v7;
  }
  v11 = v53;
  v59[0] = v53;
  v12 = v57;
  v59[1] = v57;
  v13 = WriteNodeShallowMultiple(v59, v10, a2);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53C,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v13,
      v43);
    if ( v12 )
      ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
    if ( v52 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v52 + 16LL))(v52);
    if ( v11 )
      ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
    if ( pstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
    return v14;
  }
  v15 = *((_DWORD *)this + 9);
  if ( v15 < 0xA )
  {
    *((_DWORD *)this + 9) = -1;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x540,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)0x80070216LL,
      v43);
    if ( v12 )
      ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
    if ( v52 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v52 + 16LL))(v52);
    if ( v11 )
      ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
    if ( pstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
    return 2147942934LL;
  }
  *((_DWORD *)this + 9) = v15 - 10;
  v49 = 0;
  v16 = pstm;
  IsLessThanMax = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::IsLessThanMax(this, a3, pstm, 0);
  *((_DWORD *)this + 14) = IsLessThanMax;
  if ( !IsLessThanMax )
    *((_DWORD *)this + 13) = 1;
  v18 = 0;
  v47 = 0;
  v19 = v52;
  while ( 1 )
  {
    if ( !v18 && ((unsigned int (__fastcall *)(struct IXmlReader *, int *))a2->lpVtbl->Read)(a2, &v46) )
    {
LABEL_72:
      v45 = 0;
      v35 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v16 + 40LL))(v16, 0, 0, 0);
      v36 = v35;
      v37 = 0;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5C1,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
          (const char *)(unsigned int)v35,
          v43);
        if ( v12 )
          ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
        if ( v19 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v11 )
          ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
        if ( v16 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
        return v36;
      }
      v50 = 0xFFFFFFFFLL;
      if ( !v49 )
      {
        v21 = -2102788095;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5E7,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
          (const char *)0x82AA0001LL,
          v43);
        if ( v12 )
          ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
        if ( v19 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v11 )
          ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
        if ( v16 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
        return v21;
      }
      if ( *((_DWORD *)this + 13) && !v47 )
      {
        v45 = 0xFFFFFFFFLL;
        v43 = 0;
        v38 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, _QWORD))(*(_QWORD *)v16 + 56LL))(
                v16,
                *((_QWORD *)this + 2),
                0xFFFFFFFFLL,
                0);
        v36 = v38;
        v37 = 0;
        if ( v38 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5CC,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
            (const char *)(unsigned int)v38,
            0);
          if ( v12 )
            ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
          if ( v19 )
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
          if ( v11 )
            ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
          if ( v16 )
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
          return v36;
        }
        goto LABEL_154;
      }
      if ( !*((_DWORD *)this + 12) && !*((_DWORD *)this + 14) )
      {
LABEL_154:
        if ( !v47 )
          goto LABEL_175;
        v41 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v19 + 40LL))(
                v19,
                0,
                0,
                0);
        v21 = v41;
        if ( v41 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5DF,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
            (const char *)(unsigned int)v41,
            v43);
          if ( v12 )
            ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
          if ( v19 )
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
          if ( v11 )
            ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
          if ( v16 )
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
          return v21;
        }
        v42 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, _QWORD))(*(_QWORD *)v19 + 56LL))(
                v19,
                *((_QWORD *)this + 2),
                v50,
                0);
        v36 = v42;
        if ( v42 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5E2,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
            (const char *)(unsigned int)v42,
            0);
          if ( v12 )
            ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
          if ( v19 )
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
          if ( v11 )
            ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
          if ( v16 )
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
        }
        else
        {
LABEL_175:
          if ( v12 )
            ((void (__fastcall *)(struct IXmlWriter *, __int64))v12->lpVtbl->Release)(v12, v37);
          if ( v19 )
            (*(void (__fastcall **)(struct IStream *, __int64))(*(_QWORD *)v19 + 16LL))(v19, v37);
          if ( v11 )
            ((void (__fastcall *)(struct IXmlWriter *, __int64))v11->lpVtbl->Release)(v11, v37);
          if ( v16 )
            (*(void (__fastcall **)(struct IStream *, __int64))(*(_QWORD *)v16 + 16LL))(v16, v37);
        }
        return v36;
      }
      v45 = 0xFFFFFFFFLL;
      v43 = 0;
      v39 = (*(__int64 (__fastcall **)(struct IStream *, struct IStream *, __int64, _QWORD))(*(_QWORD *)v16 + 56LL))(
              v16,
              v54,
              0xFFFFFFFFLL,
              0);
      v36 = v39;
      v37 = 0;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5D5,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
          (const char *)(unsigned int)v39,
          0);
        if ( v12 )
          ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
        if ( v19 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v11 )
          ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
        if ( v16 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
        return v36;
      }
      v40 = *((_DWORD *)this + 9);
      if ( v40 + 10 >= v40 )
      {
        *((_DWORD *)this + 9) = v40 + 10;
        v36 = 0;
        goto LABEL_154;
      }
      *((_DWORD *)this + 9) = -1;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D9,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
        (const char *)0x80070216LL,
        0);
      if ( v12 )
        ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
      if ( v19 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v11 )
        ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
      if ( v16 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
      return 2147942934LL;
    }
    v18 = 0;
    v48 = 0;
    v50 = 0;
    v56 = 0;
    if ( v46 != 1 )
    {
      if ( v46 == 15 )
      {
        v45 = 0;
        v55 = 0;
        v20 = ((__int64 (__fastcall *)(struct IXmlReader *, __int64 *, int *))a2->lpVtbl->GetLocalName)(a2, &v45, &v55);
        v21 = v20;
        if ( v20 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x598,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
            (const char *)(unsigned int)v20,
            v43);
          if ( v12 )
            ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
          if ( v19 )
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
          if ( v11 )
            ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
          if ( v16 )
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
          return v21;
        }
        if ( !(unsigned int)_o__wcsicmp(L"Results", v45) )
        {
          v23 = WriteNodeShallowMultiple(v59, v22, a2);
          v21 = v23;
          if ( v23 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x59D,
              (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
              (const char *)(unsigned int)v23,
              v43);
            if ( v12 )
              ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
            if ( v19 )
              (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
            if ( v11 )
              ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
            if ( v16 )
              (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
            return v21;
          }
          if ( !*((_DWORD *)this + 14) && !*((_DWORD *)this + 13) )
          {
            strcpy(v60, "</Results>");
            v24 = (*(__int64 (__fastcall **)(_QWORD, char *, __int64))(**((_QWORD **)this + 2) + 32LL))(
                    *((_QWORD *)this + 2),
                    v60,
                    10);
            v21 = v24;
            if ( v24 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x5AA,
                (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
                (const char *)(unsigned int)v24,
                v43);
              if ( v12 )
                ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
              if ( v19 )
                (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
              if ( v11 )
                ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
              if ( v16 )
                (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
              return v21;
            }
          }
          v49 = 1;
          goto LABEL_69;
        }
        goto LABEL_70;
      }
      goto LABEL_71;
    }
    v25 = ((__int64 (__fastcall *)(struct IXmlReader *, __int64 *, int *))a2->lpVtbl->GetLocalName)(a2, &v50, &v56);
    v21 = v25;
    if ( v25 < 0 )
      break;
    if ( !(unsigned int)_o__wcsicmp(L"CmdId", v50)
      || !(unsigned int)_o__wcsicmp(L"MsgRef", v50)
      || !(unsigned int)_o__wcsicmp(L"CmdRef", v50) )
    {
      v31 = WriteNodeMultiple(v59, v26, a2);
      v21 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x564,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
          (const char *)(unsigned int)v31,
          v43);
        if ( v12 )
          ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
        if ( v19 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v11 )
          ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
        if ( v16 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
        return v21;
      }
      v32 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a2->lpVtbl->GetNodeType)(a2, &v46);
      v21 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x569,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
          (const char *)(unsigned int)v32,
          v43);
        if ( v12 )
          ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
        if ( v19 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v11 )
          ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
        if ( v16 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
        return v21;
      }
      v48 = 1;
      v33 = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::IsLessThanMax(this, v54, v16, 0);
      *((_DWORD *)this + 14) = v33;
      if ( !v33 )
        *((_DWORD *)this + 13) = 1;
      v34 = IStream_Size(v16, &pui);
      v21 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x574,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
          (const char *)(unsigned int)v34,
          v43);
        if ( v12 )
          ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
        if ( v19 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v11 )
          ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
        if ( v16 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
        return v21;
      }
LABEL_69:
      if ( (v21 & 0x80000000) != 0 )
        goto LABEL_72;
LABEL_70:
      v18 = v48;
      goto LABEL_71;
    }
    if ( v47 )
    {
      v29 = ((__int64 (__fastcall *)(struct IXmlWriter *, struct IXmlReader *, _QWORD))v12->lpVtbl->WriteNode)(
              v12,
              a2,
              0);
      v21 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x586,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
          (const char *)(unsigned int)v29,
          v43);
        if ( v12 )
          ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
        if ( v19 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v11 )
          ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
        if ( v16 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
        return v21;
      }
    }
    else
    {
      v27 = *((_DWORD *)this + 10);
      if ( v27 )
      {
        v21 = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::ParseItemElementWithMaxObjectSize(
                this,
                v27,
                a2,
                v54,
                v16,
                v19,
                &v47);
        if ( (v21 & 0x80000000) != 0 )
        {
          v28 = 907;
          goto LABEL_52;
        }
      }
      else
      {
        v21 = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::ParseItemElementNoMaxObjectSize(
                this,
                a2,
                v54,
                v16,
                pui);
        if ( (v21 & 0x80000000) != 0 )
        {
          v28 = 896;
LABEL_52:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v28,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
            (const char *)v21,
            v43);
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x581,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
            (const char *)v21,
            v44);
          if ( v12 )
            ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
          if ( v19 )
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
          if ( v11 )
            ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
          if ( v16 )
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
          return v21;
        }
      }
    }
    v30 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a2->lpVtbl->GetNodeType)(a2, &v46);
    v21 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x58C,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
        (const char *)(unsigned int)v30,
        v43);
      if ( v12 )
        ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
      if ( v19 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
      if ( v11 )
        ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
      if ( v16 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
      return v21;
    }
    v18 = 1;
LABEL_71:
    if ( v49 )
      goto LABEL_72;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x55A,
    (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
    (const char *)(unsigned int)v25,
    v43);
  if ( v12 )
    ((void (__fastcall *)(struct IXmlWriter *))v12->lpVtbl->Release)(v12);
  if ( v19 )
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v11 )
    ((void (__fastcall *)(struct IXmlWriter *))v11->lpVtbl->Release)(v11);
  if ( v16 )
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 16LL))(v16);
  return v21;
}

```

## disassembly

```asm
0x14001be2c  mov     [rsp-8+arg_18], rbx
0x14001be31  push    rbp
0x14001be32  push    rsi
0x14001be33  push    rdi
0x14001be34  push    r12
0x14001be36  push    r13
0x14001be38  push    r14
0x14001be3a  push    r15
0x14001be3c  lea     rbp, [rsp-27h]
0x14001be41  sub     rsp, 0C0h
0x14001be48  mov     rax, cs:__security_cookie
0x14001be4f  xor     rax, rsp
0x14001be52  mov     [rbp+57h+var_38], rax
0x14001be56  mov     r14, r8
0x14001be59  mov     [rbp+57h+var_78], r8
0x14001be5d  mov     r12, rdx
0x14001be60  mov     r13, rcx
0x14001be63  xor     r15d, r15d
0x14001be66  mov     [rbp+57h+var_A8], r15d
0x14001be6a  mov     qword ptr [rbp+57h+pui], r15
0x14001be6e  mov     [rcx+2Ch], r15
0x14001be72  mov     [rcx+34h], r15d
0x14001be76  mov     [rbp+57h+pstm], r15
0x14001be7a  mov     [rbp+57h+var_80], r15
0x14001be7e  lea     rdx, [rbp+57h+var_80]; struct IXmlWriter **
0x14001be82  lea     rcx, [rbp+57h+pstm]; struct IStream **
0x14001be86  call    ?CreateTempWriterAndStream@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@KAJPEAPEAUIStream@@PEAPEAUIXmlWriter@@@Z; Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreateTempWriterAndStream(IStream * *,IXmlWriter * *)
0x14001be8b  mov     ebx, eax
0x14001be8d  test    eax, eax
0x14001be8f  jns     short loc_14001BEDD
0x14001be91  mov     rcx, [rbp+5Fh]; this
0x14001be95  mov     r9d, eax; char *
0x14001be98  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001be9f  mov     edx, 532h; void *
0x14001bea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001bea9  nop
0x14001beaa  mov     rcx, [rbp+57h+var_80]
0x14001beae  test    rcx, rcx
0x14001beb1  jz      short loc_14001BEC0
0x14001beb3  mov     rax, [rcx]
0x14001beb6  mov     rax, [rax+10h]
0x14001beba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bebf  nop
0x14001bec0  mov     rcx, [rbp+57h+pstm]
0x14001bec4  test    rcx, rcx
0x14001bec7  jz      short loc_14001BED6
0x14001bec9  mov     rax, [rcx]
0x14001becc  mov     rax, [rax+10h]
0x14001bed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bed5  nop
0x14001bed6  mov     eax, ebx
0x14001bed8  jmp     loc_14001CCC7
0x14001bedd  mov     [rbp+57h+var_88], r15
0x14001bee1  mov     [rbp+57h+var_68], r15
0x14001bee5  lea     rdx, [rbp+57h+var_68]; struct IXmlWriter **
0x14001bee9  lea     rcx, [rbp+57h+var_88]; struct IStream **
0x14001beed  call    ?CreateTempWriterAndStream@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@KAJPEAPEAUIStream@@PEAPEAUIXmlWriter@@@Z; Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreateTempWriterAndStream(IStream * *,IXmlWriter * *)
0x14001bef2  mov     ebx, eax
0x14001bef4  test    eax, eax
0x14001bef6  jns     short loc_14001BF6E
0x14001bef8  mov     rcx, [rbp+5Fh]; this
0x14001befc  mov     r9d, eax; char *
0x14001beff  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001bf06  mov     edx, 538h; void *
0x14001bf0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001bf10  nop
0x14001bf11  mov     rcx, [rbp+57h+var_68]
0x14001bf15  test    rcx, rcx
0x14001bf18  jz      short loc_14001BF27
0x14001bf1a  mov     rax, [rcx]
0x14001bf1d  mov     rax, [rax+10h]
0x14001bf21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bf26  nop
0x14001bf27  mov     rcx, [rbp+57h+var_88]
0x14001bf2b  test    rcx, rcx
0x14001bf2e  jz      short loc_14001BF3D
0x14001bf30  mov     rax, [rcx]
0x14001bf33  mov     rax, [rax+10h]
0x14001bf37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bf3c  nop
0x14001bf3d  mov     rcx, [rbp+57h+var_80]
0x14001bf41  test    rcx, rcx
0x14001bf44  jz      short loc_14001BF53
0x14001bf46  mov     rax, [rcx]
0x14001bf49  mov     rax, [rax+10h]
0x14001bf4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bf52  nop
0x14001bf53  mov     rcx, [rbp+57h+pstm]
0x14001bf57  test    rcx, rcx
0x14001bf5a  jz      short loc_14001BF69
0x14001bf5c  mov     rax, [rcx]
0x14001bf5f  mov     rax, [rax+10h]
0x14001bf63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bf68  nop
0x14001bf69  jmp     loc_14001BED6
0x14001bf6e  mov     rbx, [rbp+57h+var_80]
0x14001bf72  mov     [rbp+57h+var_58], rbx
0x14001bf76  mov     rdi, [rbp+57h+var_68]
0x14001bf7a  mov     [rbp+57h+var_50], rdi
0x14001bf7e  mov     r8, r12; struct IXmlReader *
0x14001bf81  lea     rcx, [rbp+57h+var_58]; struct IXmlWriter **
0x14001bf85  call    ?WriteNodeShallowMultiple@@YAJPEAPEAUIXmlWriter@@KPEAUIXmlReader@@@Z; WriteNodeShallowMultiple(IXmlWriter * *,ulong,IXmlReader *)
0x14001bf8a  mov     esi, eax
0x14001bf8c  test    eax, eax
0x14001bf8e  jns     short loc_14001C006
0x14001bf90  mov     rcx, [rbp+5Fh]; this
0x14001bf94  mov     r9d, eax; char *
0x14001bf97  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001bf9e  mov     edx, 53Ch; void *
0x14001bfa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001bfa8  nop
0x14001bfa9  test    rdi, rdi
0x14001bfac  jz      short loc_14001BFBE
0x14001bfae  mov     rax, [rdi]
0x14001bfb1  mov     rcx, rdi
0x14001bfb4  mov     rax, [rax+10h]
0x14001bfb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bfbd  nop
0x14001bfbe  mov     rcx, [rbp+57h+var_88]
0x14001bfc2  test    rcx, rcx
0x14001bfc5  jz      short loc_14001BFD4
0x14001bfc7  mov     rax, [rcx]
0x14001bfca  mov     rax, [rax+10h]
0x14001bfce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bfd3  nop
0x14001bfd4  test    rbx, rbx
0x14001bfd7  jz      short loc_14001BFE9
0x14001bfd9  mov     rax, [rbx]
0x14001bfdc  mov     rcx, rbx
0x14001bfdf  mov     rax, [rax+10h]
0x14001bfe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bfe8  nop
0x14001bfe9  mov     rcx, [rbp+57h+pstm]
0x14001bfed  test    rcx, rcx
0x14001bff0  jz      short loc_14001BFFF
0x14001bff2  mov     rax, [rcx]
0x14001bff5  mov     rax, [rax+10h]
0x14001bff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bffe  nop
0x14001bfff  mov     eax, esi
0x14001c001  jmp     loc_14001CCC7
0x14001c006  mov     eax, [r13+24h]
0x14001c00a  cmp     eax, 0Ah
0x14001c00d  jb      loc_14001CC48
0x14001c013  add     eax, 0FFFFFFF6h
0x14001c016  mov     [r13+24h], eax
0x14001c01a  mov     [rbp+57h+var_9C], r15d
0x14001c01e  xor     r9d, r9d; unsigned int
0x14001c021  mov     r15, [rbp+57h+pstm]
0x14001c025  mov     r8, r15; struct IStream *
0x14001c028  mov     rdx, r14; struct IStream *
0x14001c02b  mov     rcx, r13; this
0x14001c02e  call    ?IsLessThanMax@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@IEAAHPEAUIStream@@0K@Z; Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::IsLessThanMax(IStream *,IStream *,ulong)
0x14001c033  mov     [r13+38h], eax
0x14001c037  test    eax, eax
0x14001c039  jnz     short loc_14001C043
0x14001c03b  mov     dword ptr [r13+34h], 1
0x14001c043  xor     edx, edx
0x14001c045  mov     [rbp+57h+var_A4], edx
0x14001c048  mov     rsi, [rbp+57h+var_88]
0x14001c04c  test    edx, edx
0x14001c04e  jnz     short loc_14001C06C
0x14001c050  mov     rax, [r12]
0x14001c054  lea     rdx, [rbp+57h+var_A8]
0x14001c058  mov     rcx, r12
0x14001c05b  mov     rax, [rax+30h]
0x14001c05f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c064  test    eax, eax
0x14001c066  jnz     loc_14001C390
0x14001c06c  xor     edx, edx
0x14001c06e  mov     [rbp+57h+var_A0], edx
0x14001c071  mov     [rbp+57h+var_98], rdx
0x14001c075  mov     [rbp+57h+var_6C], edx
0x14001c078  mov     ecx, [rbp+57h+var_A8]
0x14001c07b  sub     ecx, 1
0x14001c07e  jz      loc_14001C143
0x14001c084  cmp     ecx, 0Eh
0x14001c087  jnz     loc_14001C386
0x14001c08d  mov     [rbp+57h+var_B0], rdx
0x14001c091  mov     [rbp+57h+var_70], edx
0x14001c094  mov     rax, [r12]
0x14001c098  lea     r8, [rbp+57h+var_70]
0x14001c09c  lea     rdx, [rbp+57h+var_B0]
0x14001c0a0  mov     rcx, r12
0x14001c0a3  mov     rax, [rax+70h]
0x14001c0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c0ac  mov     r14d, eax
0x14001c0af  test    eax, eax
0x14001c0b1  js      loc_14001C51A
0x14001c0b7  mov     rdx, [rbp+57h+var_B0]
0x14001c0bb  lea     rcx, aResults; "Results"
0x14001c0c2  call    cs:__imp__o__wcsicmp
0x14001c0c9  nop     dword ptr [rax+rax+00h]
0x14001c0ce  test    eax, eax
0x14001c0d0  jnz     loc_14001C383
0x14001c0d6  mov     r8, r12; struct IXmlReader *
0x14001c0d9  lea     rcx, [rbp+57h+var_58]; struct IXmlWriter **
0x14001c0dd  call    ?WriteNodeShallowMultiple@@YAJPEAPEAUIXmlWriter@@KPEAUIXmlReader@@@Z; WriteNodeShallowMultiple(IXmlWriter * *,ulong,IXmlReader *)
0x14001c0e2  mov     r14d, eax
0x14001c0e5  test    eax, eax
0x14001c0e7  js      loc_14001C4A8
0x14001c0ed  cmp     dword ptr [r13+38h], 0
0x14001c0f2  jnz     short loc_14001C137
0x14001c0f4  cmp     dword ptr [r13+34h], 0
0x14001c0f9  jnz     short loc_14001C137
0x14001c0fb  movsd   xmm0, qword ptr cs:aResults_0; "</Results>"
0x14001c103  movsd   qword ptr [rbp+57h+var_48], xmm0
0x14001c108  mov     eax, dword ptr cs:aResults_0+7; "ts>"
0x14001c10e  mov     dword ptr [rbp+57h+var_48+7], eax
0x14001c111  mov     rcx, [r13+10h]
0x14001c115  mov     rax, [rcx]
0x14001c118  xor     r9d, r9d
0x14001c11b  lea     r8d, [r9+0Ah]
0x14001c11f  lea     rdx, [rbp+57h+var_48]
0x14001c123  mov     rax, [rax+20h]
0x14001c127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c12c  mov     r14d, eax
0x14001c12f  test    eax, eax
0x14001c131  js      loc_14001C436
0x14001c137  mov     [rbp+57h+var_9C], 1
0x14001c13e  jmp     loc_14001C37E
0x14001c143  mov     rax, [r12]
0x14001c147  lea     r8, [rbp+57h+var_6C]
0x14001c14b  lea     rdx, [rbp+57h+var_98]
0x14001c14f  mov     rcx, r12
0x14001c152  mov     rax, [rax+70h]
0x14001c156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c15b  mov     r14d, eax
0x14001c15e  test    eax, eax
0x14001c160  js      loc_14001CBD6
0x14001c166  mov     rdx, [rbp+57h+var_98]
0x14001c16a  lea     rcx, aCmdid; "CmdId"
0x14001c171  call    cs:__imp__o__wcsicmp
0x14001c178  nop     dword ptr [rax+rax+00h]
0x14001c17d  test    eax, eax
0x14001c17f  jz      loc_14001C302
0x14001c185  mov     rdx, [rbp+57h+var_98]
0x14001c189  lea     rcx, aMsgref; "MsgRef"
0x14001c190  call    cs:__imp__o__wcsicmp
0x14001c197  nop     dword ptr [rax+rax+00h]
0x14001c19c  test    eax, eax
0x14001c19e  jz      loc_14001C302
0x14001c1a4  mov     rdx, [rbp+57h+var_98]
0x14001c1a8  lea     rcx, aCmdref; "CmdRef"
0x14001c1af  call    cs:__imp__o__wcsicmp
0x14001c1b6  nop     dword ptr [rax+rax+00h]
0x14001c1bb  test    eax, eax
0x14001c1bd  jz      loc_14001C302
0x14001c1c3  cmp     [rbp+57h+var_A4], 0
0x14001c1c7  jnz     loc_14001C2B6
0x14001c1cd  mov     edx, [r13+28h]; unsigned int
0x14001c1d1  mov     rcx, r13; this
0x14001c1d4  test    edx, edx
0x14001c1d6  jnz     short loc_14001C202
0x14001c1d8  mov     rax, qword ptr [rbp+57h+pui]
0x14001c1dc  mov     qword ptr [rsp+0F0h+var_D0], rax; union _ULARGE_INTEGER
0x14001c1e1  mov     r9, r15; struct IStream *
0x14001c1e4  mov     r8, [rbp+57h+var_78]; struct IStream *
0x14001c1e8  mov     rdx, r12; struct IXmlReader *
0x14001c1eb  call    ?ParseItemElementNoMaxObjectSize@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEAUIXmlReader@@PEAUIStream@@1T_ULARGE_INTEGER@@@Z; Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::ParseItemElementNoMaxObjectSize(IXmlReader *,IStream *,IStream *,_ULARGE_INTEGER)
0x14001c1f0  mov     r14d, eax
0x14001c1f3  test    eax, eax
0x14001c1f5  jns     loc_14001C2D9
0x14001c1fb  mov     edx, 380h
0x14001c200  jmp     short loc_14001C231
0x14001c202  lea     rax, [rbp+57h+var_A4]
0x14001c206  mov     [rsp+0F0h+var_C0], rax; int *
0x14001c20b  mov     [rsp+0F0h+var_C8], rsi; struct IStream *
0x14001c210  mov     qword ptr [rsp+0F0h+var_D0], r15; int
0x14001c215  mov     r9, [rbp+57h+var_78]; struct IStream *
0x14001c219  mov     r8, r12; struct IXmlReader *
0x14001c21c  call    ?ParseItemElementWithMaxObjectSize@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@IEAAJKPEAUIXmlReader@@PEAUIStream@@11PEAH@Z; Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::ParseItemElementWithMaxObjectSize(ulong,IXmlReader *,IStream *,IStream *,IStream *,int *)
0x14001c221  mov     r14d, eax
0x14001c224  test    eax, eax
0x14001c226  jns     loc_14001C2D9
0x14001c22c  mov     edx, 38Bh; void *
0x14001c231  mov     r9d, r14d; char *
0x14001c234  mov     rcx, [rbp+5Fh]; this
0x14001c238  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001c23f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001c244  mov     rcx, [rbp+5Fh]; this
0x14001c248  mov     r9d, r14d; char *
0x14001c24b  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001c252  mov     edx, 581h; void *
0x14001c257  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001c25c  nop
0x14001c25d  test    rdi, rdi
0x14001c260  jz      short loc_14001C272
0x14001c262  mov     rax, [rdi]
0x14001c265  mov     rcx, rdi
0x14001c268  mov     rax, [rax+10h]
0x14001c26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c271  nop
0x14001c272  test    rsi, rsi
0x14001c275  jz      short loc_14001C287
0x14001c277  mov     rax, [rsi]
0x14001c27a  mov     rcx, rsi
0x14001c27d  mov     rax, [rax+10h]
0x14001c281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c286  nop
  ... truncated ...
```
