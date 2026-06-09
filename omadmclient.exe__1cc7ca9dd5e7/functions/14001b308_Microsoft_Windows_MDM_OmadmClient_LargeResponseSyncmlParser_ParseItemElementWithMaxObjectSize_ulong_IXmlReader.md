# Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::ParseItemElementWithMaxObjectSize(ulong,IXmlReader *,IStream *,IStream *,IStream *,int *)

- ea: `0x14001b308`
- end: `0x14001be23`
- name: `?ParseItemElementWithMaxObjectSize@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@IEAAJKPEAUIXmlReader@@PEAUIStream@@11PEAH@Z`
- size: `2843`
- prototype: `int(Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *__hidden this, unsigned int, struct IXmlReader *, struct IStream *, struct IStream *, struct IStream *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001be2c`

## callees

- `0x14000b0f4`
- `0x140019d40`
- `0x14001a8ec`
- `0x14001b308`
- `0x14001d5b0`
- `0x14001d758`
- `0x140069010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001b546`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001b5b5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001b61a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001b635`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001b546`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001b5b5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001b61a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14001b635`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x14001ba0b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x14001ba9c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x14001bb30`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x14001ba0b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x14001ba9c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x14001bb30`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::ParseItemElementWithMaxObjectSize(
        Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *this,
        unsigned int a2,
        struct IXmlReader *a3,
        struct IStream *a4,
        struct IStream *a5,
        struct IStream *a6,
        int *a7)
{
  int v8; // eax
  unsigned int v9; // ebx
  int v11; // eax
  unsigned int v12; // edx
  struct IXmlWriter *v13; // rdi
  struct IXmlWriter *v14; // rsi
  int v15; // eax
  char v16; // r13
  struct IStream *v17; // rbx
  DWORD v18; // r15d
  int v19; // eax
  unsigned int v20; // edx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  unsigned int v24; // edx
  int v25; // eax
  struct IStream *v26; // r14
  int v27; // eax
  int v28; // eax
  HRESULT v29; // eax
  HRESULT v30; // eax
  struct IStream *v31; // r13
  HRESULT v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // [rsp+28h] [rbp-81h]
  char v37; // [rsp+58h] [rbp-51h]
  ULARGE_INTEGER v38; // [rsp+60h] [rbp-49h] BYREF
  struct IStream *v39; // [rsp+68h] [rbp-41h] BYREF
  ULARGE_INTEGER v40; // [rsp+70h] [rbp-39h] BYREF
  int v41; // [rsp+78h] [rbp-31h] BYREF
  int v42; // [rsp+7Ch] [rbp-2Dh] BYREF
  IStream *pstm; // [rsp+80h] [rbp-29h] BYREF
  ULARGE_INTEGER pui; // [rsp+88h] [rbp-21h] BYREF
  struct IXmlWriter *v45; // [rsp+90h] [rbp-19h] BYREF
  struct IXmlWriter *v46; // [rsp+98h] [rbp-11h] BYREF
  struct IXmlWriter *v47[9]; // [rsp+A0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+47h]

  pstm = 0;
  v45 = 0;
  v8 = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreateTempWriterAndStream(&pstm, &v45);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3FC,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v8,
      v36);
    if ( v45 )
      ((void (__fastcall *)(struct IXmlWriter *))v45->lpVtbl->Release)(v45);
    if ( pstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
    return v9;
  }
  v39 = 0;
  v46 = 0;
  v11 = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreateTempWriterAndStream(&v39, &v46);
  v9 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x401,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v11,
      v36);
    if ( v46 )
      ((void (__fastcall *)(struct IXmlWriter *))v46->lpVtbl->Release)(v46);
    if ( v39 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v39 + 16LL))(v39);
    if ( v45 )
      ((void (__fastcall *)(struct IXmlWriter *))v45->lpVtbl->Release)(v45);
    if ( pstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
    return v9;
  }
  v13 = v45;
  v47[0] = v45;
  v14 = v46;
  v47[1] = v46;
  v15 = WriteNodeShallowMultiple(v47, v12, a3);
  v9 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x405,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v15,
      v36);
    if ( v14 )
      ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
    if ( v39 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v39 + 16LL))(v39);
    if ( v13 )
      ((void (__fastcall *)(struct IXmlWriter *))v13->lpVtbl->Release)(v13);
    if ( pstm )
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)pstm + 16LL))(pstm);
    return v9;
  }
  v42 = 1;
  v37 = 1;
  v41 = 0;
  v16 = 1;
  v17 = pstm;
  do
  {
    v18 = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a3->lpVtbl->Read)(a3, &v41);
    if ( v18 )
      break;
    if ( v41 == 1 )
    {
      v38.QuadPart = 0;
      v40.LowPart = 0;
      v22 = ((__int64 (__fastcall *)(struct IXmlReader *, ULARGE_INTEGER *, ULARGE_INTEGER *))a3->lpVtbl->GetLocalName)(
              a3,
              &v38,
              &v40);
      v18 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x418,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
          (const char *)(unsigned int)v22,
          v36);
        if ( v14 )
          ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
        if ( v39 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v39 + 16LL))(v39);
        if ( v13 )
          ((void (__fastcall *)(struct IXmlWriter *))v13->lpVtbl->Release)(v13);
        if ( v17 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v17 + 16LL))(v17);
        return v18;
      }
      if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))_o__wcsicmp)(L"Data", (ULARGE_INTEGER)v38.QuadPart) )
      {
        if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))_o__wcsicmp)(
                              L"Source",
                              (ULARGE_INTEGER)v38.QuadPart)
          || !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))_o__wcsicmp)(L"Meta", (ULARGE_INTEGER)v38.QuadPart) )
        {
          v25 = WriteNodeMultiple(v47, v24, a3);
          v18 = v25;
          if ( v25 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x42C,
              (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
              (const char *)(unsigned int)v25,
              v36);
            if ( v14 )
              ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
            if ( v39 )
              (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v39 + 16LL))(v39);
            if ( v13 )
              ((void (__fastcall *)(struct IXmlWriter *))v13->lpVtbl->Release)(v13);
            if ( v17 )
              (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v17 + 16LL))(v17);
            return v18;
          }
        }
      }
      else
      {
        v23 = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::ParseDataElement(
                this,
                a2,
                a3,
                a4,
                a5,
                v13,
                v17,
                v14,
                &v42,
                a7);
        v18 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x427,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
            (const char *)(unsigned int)v23,
            v36);
          if ( v14 )
            ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
          if ( v39 )
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v39 + 16LL))(v39);
          if ( v13 )
            ((void (__fastcall *)(struct IXmlWriter *))v13->lpVtbl->Release)(v13);
          if ( v17 )
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v17 + 16LL))(v17);
          return v18;
        }
        v37 = 0;
      }
    }
    else if ( v41 == 15 )
    {
      v38.QuadPart = 0;
      v40.LowPart = v18;
      v19 = ((__int64 (__fastcall *)(struct IXmlReader *, ULARGE_INTEGER *, ULARGE_INTEGER *))a3->lpVtbl->GetLocalName)(
              a3,
              &v38,
              &v40);
      v18 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x438,
          (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
          (const char *)(unsigned int)v19,
          v36);
        if ( v14 )
          ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
        if ( v39 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v39 + 16LL))(v39);
        if ( v13 )
          ((void (__fastcall *)(struct IXmlWriter *))v13->lpVtbl->Release)(v13);
        if ( v17 )
          (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v17 + 16LL))(v17);
        return v18;
      }
      if ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, _QWORD))_o__wcsicmp)(L"Item", (ULARGE_INTEGER)v38.QuadPart) )
      {
        v21 = WriteNodeShallowMultiple(v47, v20, a3);
        v18 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x43E,
            (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
            (const char *)(unsigned int)v21,
            v36);
          if ( v14 )
            ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
          if ( v39 )
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v39 + 16LL))(v39);
          if ( v13 )
            ((void (__fastcall *)(struct IXmlWriter *))v13->lpVtbl->Release)(v13);
          if ( v17 )
            (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v17 + 16LL))(v17);
          return v18;
        }
        v16 = 0;
      }
    }
  }
  while ( v16 );
  v47[0] = 0;
  v26 = v39;
  if ( *a7 )
  {
    v27 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v39 + 40LL))(v39, 0, 0, 0);
    v18 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x454,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
        (const char *)(unsigned int)v27,
        v36);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      if ( v26 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v13 )
        ((void (__fastcall *)(struct IXmlWriter *))v13->lpVtbl->Release)(v13);
      if ( v17 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v17 + 16LL))(v17);
      return v18;
    }
    v38.LowPart = -1;
    v38.HighPart = (DWORD)v47[0];
    v36 = 0;
    v28 = (*(__int64 (__fastcall **)(struct IStream *, struct IStream *, ULARGE_INTEGER, _QWORD))(*(_QWORD *)v26 + 56LL))(
            v26,
            a6,
            v38,
            0);
    v18 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x457,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
        (const char *)(unsigned int)v28,
        0);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      if ( v26 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v13 )
        ((void (__fastcall *)(struct IXmlWriter *))v13->lpVtbl->Release)(v13);
      if ( v17 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v17 + 16LL))(v17);
      return v18;
    }
  }
  if ( v37 )
  {
    pui.QuadPart = 0;
    v29 = IStream_Size(v17, &pui);
    v18 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x461,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
        (const char *)(unsigned int)v29,
        v36);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      if ( v26 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v13 )
        ((void (__fastcall *)(struct IXmlWriter *))v13->lpVtbl->Release)(v13);
      if ( v17 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v17 + 16LL))(v17);
      return v18;
    }
    v38.QuadPart = 0;
    v30 = IStream_Size(a4, &v38);
    v18 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x465,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
        (const char *)(unsigned int)v30,
        v36);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      if ( v26 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v13 )
        ((void (__fastcall *)(struct IXmlWriter *))v13->lpVtbl->Release)(v13);
      if ( v17 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v17 + 16LL))(v17);
      return v18;
    }
    v40.QuadPart = 0;
    v31 = a5;
    v32 = IStream_Size(a5, &v40);
    v18 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x469,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
        (const char *)(unsigned int)v32,
        v36);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      if ( v26 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v13 )
        ((void (__fastcall *)(struct IXmlWriter *))v13->lpVtbl->Release)(v13);
      if ( v17 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v17 + 16LL))(v17);
      return v18;
    }
    v33 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v17 + 40LL))(v17, 0, 0, 0);
    v18 = v33;
    if ( v33 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46C,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
        (const char *)(unsigned int)v33,
        v36);
      if ( v14 )
        ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
      if ( v26 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v26 + 16LL))(v26);
      if ( v13 )
        ((void (__fastcall *)(struct IXmlWriter *))v13->lpVtbl->Release)(v13);
      if ( v17 )
        (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v17 + 16LL))(v17);
      return v18;
    }
    if ( pui.LowPart + v38.LowPart + v40.LowPart > *((_DWORD *)this + 9) || *a7 )
    {
      v31 = a6;
      *a7 = 1;
    }
  }
  else
  {
    v31 = a5;
  }
  if ( !v42 )
    goto LABEL_175;
  v34 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v17 + 40LL))(v17, 0, 0, 0);
  v18 = v34;
  if ( v34 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47A,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v34,
      v36);
    if ( v14 )
      ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
    if ( v26 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v26 + 16LL))(v26);
    if ( v13 )
      ((void (__fastcall *)(struct IXmlWriter *))v13->lpVtbl->Release)(v13);
    if ( v17 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v17 + 16LL))(v17);
    return v18;
  }
  pui.LowPart = -1;
  pui.HighPart = (DWORD)v47[0];
  v35 = (*(__int64 (__fastcall **)(struct IStream *, struct IStream *, ULARGE_INTEGER, _QWORD))(*(_QWORD *)v17 + 56LL))(
          v17,
          v31,
          pui,
          0);
  v18 = v35;
  if ( v35 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47D,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
      (const char *)(unsigned int)v35,
      0);
    if ( v14 )
      ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
    if ( v26 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v26 + 16LL))(v26);
    if ( v13 )
      ((void (__fastcall *)(struct IXmlWriter *))v13->lpVtbl->Release)(v13);
    if ( v17 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v17 + 16LL))(v17);
  }
  else
  {
LABEL_175:
    if ( v14 )
      ((void (__fastcall *)(struct IXmlWriter *))v14->lpVtbl->Release)(v14);
    if ( v26 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v26 + 16LL))(v26);
    if ( v13 )
      ((void (__fastcall *)(struct IXmlWriter *))v13->lpVtbl->Release)(v13);
    if ( v17 )
      (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return v18;
}

```

## disassembly

```asm
0x14001b308  mov     rax, rsp
0x14001b30b  mov     [rax+18h], rbx
0x14001b30f  mov     [rax+20h], r9
0x14001b313  mov     [rax+10h], edx
0x14001b316  mov     [rax+8], rcx
0x14001b31a  push    rbp
0x14001b31b  push    rsi
0x14001b31c  push    rdi
0x14001b31d  push    r12
0x14001b31f  push    r13
0x14001b321  push    r14
0x14001b323  push    r15
0x14001b325  lea     rbp, [rax-47h]
0x14001b329  sub     rsp, 0B0h
0x14001b330  mov     r14, r8
0x14001b333  xor     r15d, r15d
0x14001b336  mov     [rbp+3Fh+pstm], r15
0x14001b33a  mov     [rbp+3Fh+var_58], r15
0x14001b33e  lea     rdx, [rbp+3Fh+var_58]; struct IXmlWriter **
0x14001b342  lea     rcx, [rbp+3Fh+pstm]; struct IStream **
0x14001b346  call    ?CreateTempWriterAndStream@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@KAJPEAPEAUIStream@@PEAPEAUIXmlWriter@@@Z; Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreateTempWriterAndStream(IStream * *,IXmlWriter * *)
0x14001b34b  mov     ebx, eax
0x14001b34d  test    eax, eax
0x14001b34f  jns     short loc_14001B39D
0x14001b351  mov     rcx, [rbp+47h]; this
0x14001b355  mov     r9d, eax; char *
0x14001b358  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001b35f  mov     edx, 3FCh; void *
0x14001b364  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001b369  nop
0x14001b36a  mov     rcx, [rbp+3Fh+var_58]
0x14001b36e  test    rcx, rcx
0x14001b371  jz      short loc_14001B380
0x14001b373  mov     rax, [rcx]
0x14001b376  mov     rax, [rax+10h]
0x14001b37a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b37f  nop
0x14001b380  mov     rcx, [rbp+3Fh+pstm]
0x14001b384  test    rcx, rcx
0x14001b387  jz      short loc_14001B396
0x14001b389  mov     rax, [rcx]
0x14001b38c  mov     rax, [rax+10h]
0x14001b390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b395  nop
0x14001b396  mov     eax, ebx
0x14001b398  jmp     loc_14001BE07
0x14001b39d  mov     [rbp+3Fh+var_80], r15
0x14001b3a1  mov     [rbp+3Fh+var_50], r15
0x14001b3a5  lea     rdx, [rbp+3Fh+var_50]; struct IXmlWriter **
0x14001b3a9  lea     rcx, [rbp+3Fh+var_80]; struct IStream **
0x14001b3ad  call    ?CreateTempWriterAndStream@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@KAJPEAPEAUIStream@@PEAPEAUIXmlWriter@@@Z; Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::CreateTempWriterAndStream(IStream * *,IXmlWriter * *)
0x14001b3b2  mov     ebx, eax
0x14001b3b4  test    eax, eax
0x14001b3b6  jns     short loc_14001B42E
0x14001b3b8  mov     rcx, [rbp+47h]; this
0x14001b3bc  mov     r9d, eax; char *
0x14001b3bf  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001b3c6  mov     edx, 401h; void *
0x14001b3cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001b3d0  nop
0x14001b3d1  mov     rcx, [rbp+3Fh+var_50]
0x14001b3d5  test    rcx, rcx
0x14001b3d8  jz      short loc_14001B3E7
0x14001b3da  mov     rax, [rcx]
0x14001b3dd  mov     rax, [rax+10h]
0x14001b3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b3e6  nop
0x14001b3e7  mov     rcx, [rbp+3Fh+var_80]
0x14001b3eb  test    rcx, rcx
0x14001b3ee  jz      short loc_14001B3FD
0x14001b3f0  mov     rax, [rcx]
0x14001b3f3  mov     rax, [rax+10h]
0x14001b3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b3fc  nop
0x14001b3fd  mov     rcx, [rbp+3Fh+var_58]
0x14001b401  test    rcx, rcx
0x14001b404  jz      short loc_14001B413
0x14001b406  mov     rax, [rcx]
0x14001b409  mov     rax, [rax+10h]
0x14001b40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b412  nop
0x14001b413  mov     rcx, [rbp+3Fh+pstm]
0x14001b417  test    rcx, rcx
0x14001b41a  jz      short loc_14001B429
0x14001b41c  mov     rax, [rcx]
0x14001b41f  mov     rax, [rax+10h]
0x14001b423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b428  nop
0x14001b429  jmp     loc_14001B396
0x14001b42e  mov     rdi, [rbp+3Fh+var_58]
0x14001b432  mov     [rbp+3Fh+var_48], rdi
0x14001b436  mov     rsi, [rbp+3Fh+var_50]
0x14001b43a  mov     [rbp+3Fh+var_40], rsi
0x14001b43e  mov     r8, r14; struct IXmlReader *
0x14001b441  lea     rcx, [rbp+3Fh+var_48]; struct IXmlWriter **
0x14001b445  call    ?WriteNodeShallowMultiple@@YAJPEAPEAUIXmlWriter@@KPEAUIXmlReader@@@Z; WriteNodeShallowMultiple(IXmlWriter * *,ulong,IXmlReader *)
0x14001b44a  mov     ebx, eax
0x14001b44c  test    eax, eax
0x14001b44e  jns     short loc_14001B4C4
0x14001b450  mov     rcx, [rbp+47h]; this
0x14001b454  mov     r9d, eax; char *
0x14001b457  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001b45e  mov     edx, 405h; void *
0x14001b463  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001b468  nop
0x14001b469  test    rsi, rsi
0x14001b46c  jz      short loc_14001B47E
0x14001b46e  mov     rax, [rsi]
0x14001b471  mov     rcx, rsi
0x14001b474  mov     rax, [rax+10h]
0x14001b478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b47d  nop
0x14001b47e  mov     rcx, [rbp+3Fh+var_80]
0x14001b482  test    rcx, rcx
0x14001b485  jz      short loc_14001B494
0x14001b487  mov     rax, [rcx]
0x14001b48a  mov     rax, [rax+10h]
0x14001b48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b493  nop
0x14001b494  test    rdi, rdi
0x14001b497  jz      short loc_14001B4A9
0x14001b499  mov     rax, [rdi]
0x14001b49c  mov     rcx, rdi
0x14001b49f  mov     rax, [rax+10h]
0x14001b4a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b4a8  nop
0x14001b4a9  mov     rcx, [rbp+3Fh+pstm]
0x14001b4ad  test    rcx, rcx
0x14001b4b0  jz      short loc_14001B4BF
0x14001b4b2  mov     rax, [rcx]
0x14001b4b5  mov     rax, [rax+10h]
0x14001b4b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b4be  nop
0x14001b4bf  jmp     loc_14001B396
0x14001b4c4  mov     [rbp+3Fh+var_6C], 1
0x14001b4cb  mov     [rbp+3Fh+var_90], 1
0x14001b4cf  mov     [rbp+3Fh+var_70], r15d
0x14001b4d3  mov     r13b, 1
0x14001b4d6  mov     r12, [rbp+3Fh+arg_30]
0x14001b4da  mov     rbx, [rbp+3Fh+pstm]
0x14001b4de  mov     rax, [r14]
0x14001b4e1  lea     rdx, [rbp+3Fh+var_70]
0x14001b4e5  mov     rcx, r14
0x14001b4e8  mov     rax, [rax+30h]
0x14001b4ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b4f1  mov     r15d, eax
0x14001b4f4  test    eax, eax
0x14001b4f6  jnz     loc_14001B665
0x14001b4fc  mov     eax, [rbp+3Fh+var_70]
0x14001b4ff  sub     eax, 1
0x14001b502  jz      short loc_14001B579
0x14001b504  cmp     eax, 0Eh
0x14001b507  jnz     loc_14001B65C
0x14001b50d  mov     qword ptr [rbp+3Fh+var_88], 0
0x14001b515  mov     dword ptr [rbp+3Fh+var_78], r15d
0x14001b519  mov     rax, [r14]
0x14001b51c  lea     r8, [rbp+3Fh+var_78]
0x14001b520  lea     rdx, [rbp+3Fh+var_88]
0x14001b524  mov     rcx, r14
0x14001b527  mov     rax, [rax+70h]
0x14001b52b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b530  mov     r15d, eax
0x14001b533  test    eax, eax
0x14001b535  js      loc_14001B784
0x14001b53b  mov     rdx, qword ptr [rbp+3Fh+var_88]
0x14001b53f  lea     rcx, aItem; "Item"
0x14001b546  call    cs:__imp__o__wcsicmp
0x14001b54d  nop     dword ptr [rax+rax+00h]
0x14001b552  test    eax, eax
0x14001b554  jnz     loc_14001B65C
0x14001b55a  mov     r8, r14; struct IXmlReader *
0x14001b55d  lea     rcx, [rbp+3Fh+var_48]; struct IXmlWriter **
0x14001b561  call    ?WriteNodeShallowMultiple@@YAJPEAPEAUIXmlWriter@@KPEAUIXmlReader@@@Z; WriteNodeShallowMultiple(IXmlWriter * *,ulong,IXmlReader *)
0x14001b566  mov     r15d, eax
0x14001b569  test    eax, eax
0x14001b56b  js      loc_14001B711
0x14001b571  xor     r13b, r13b
0x14001b574  jmp     loc_14001B65C
0x14001b579  mov     qword ptr [rbp+3Fh+var_88], 0
0x14001b581  mov     dword ptr [rbp+3Fh+var_78], 0
0x14001b588  mov     rax, [r14]
0x14001b58b  lea     r8, [rbp+3Fh+var_78]
0x14001b58f  lea     rdx, [rbp+3Fh+var_88]
0x14001b593  mov     rcx, r14
0x14001b596  mov     rax, [rax+70h]
0x14001b59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b59f  mov     r15d, eax
0x14001b5a2  test    eax, eax
0x14001b5a4  js      loc_14001B8DD
0x14001b5aa  mov     rdx, qword ptr [rbp+3Fh+var_88]
0x14001b5ae  lea     rcx, aData; "Data"
0x14001b5b5  call    cs:__imp__o__wcsicmp
0x14001b5bc  nop     dword ptr [rax+rax+00h]
0x14001b5c1  test    eax, eax
0x14001b5c3  jnz     short loc_14001B60F
0x14001b5c5  mov     [rsp+48h], r12; int *
0x14001b5ca  lea     rax, [rbp+3Fh+var_6C]
0x14001b5ce  mov     [rsp+0E0h+var_A0], rax; int *
0x14001b5d3  mov     [rsp+0E0h+var_A8], rsi; struct IXmlWriter *
0x14001b5d8  mov     [rsp+0E0h+var_B0], rbx; struct IStream *
0x14001b5dd  mov     [rsp+0E0h+var_B8], rdi; struct IXmlWriter *
0x14001b5e2  mov     rax, [rbp+3Fh+arg_20]
0x14001b5e6  mov     [rsp+0E0h+var_C0], rax; int
0x14001b5eb  mov     r9, [rbp+3Fh+arg_18]; struct IStream *
0x14001b5ef  mov     r8, r14; struct IXmlReader *
0x14001b5f2  mov     edx, [rbp+3Fh+arg_8]; unsigned int
0x14001b5f5  mov     rcx, [rbp+3Fh+arg_0]; this
0x14001b5f9  call    ?ParseDataElement@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@IEAAJKPEAUIXmlReader@@PEAUIStream@@1PEAUIXmlWriter@@12PEAH3@Z; Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::ParseDataElement(ulong,IXmlReader *,IStream *,IStream *,IXmlWriter *,IStream *,IXmlWriter *,int *,int *)
0x14001b5fe  mov     r15d, eax
0x14001b601  test    eax, eax
0x14001b603  js      loc_14001B7F7
0x14001b609  mov     [rbp+3Fh+var_90], 0
0x14001b60d  jmp     short loc_14001B65C
0x14001b60f  mov     rdx, qword ptr [rbp+3Fh+var_88]
0x14001b613  lea     rcx, aSource; "Source"
0x14001b61a  call    cs:__imp__o__wcsicmp
0x14001b621  nop     dword ptr [rax+rax+00h]
0x14001b626  test    eax, eax
0x14001b628  jz      short loc_14001B645
0x14001b62a  mov     rdx, qword ptr [rbp+3Fh+var_88]
0x14001b62e  lea     rcx, aMeta; "Meta"
0x14001b635  call    cs:__imp__o__wcsicmp
0x14001b63c  nop     dword ptr [rax+rax+00h]
0x14001b641  test    eax, eax
0x14001b643  jnz     short loc_14001B65C
0x14001b645  mov     r8, r14; struct IXmlReader *
0x14001b648  lea     rcx, [rbp+3Fh+var_48]; struct IXmlWriter **
0x14001b64c  call    ?WriteNodeMultiple@@YAJPEAPEAUIXmlWriter@@KPEAUIXmlReader@@@Z; WriteNodeMultiple(IXmlWriter * *,ulong,IXmlReader *)
0x14001b651  mov     r15d, eax
0x14001b654  test    eax, eax
0x14001b656  js      loc_14001B86A
0x14001b65c  test    r13b, r13b
0x14001b65f  jnz     loc_14001B4DE
0x14001b665  xor     eax, eax
0x14001b667  mov     [rbp+3Fh+var_48], rax
0x14001b66b  mov     r14, [rbp+3Fh+var_80]
0x14001b66f  xor     r13d, r13d
0x14001b672  cmp     [r12], r13d
0x14001b676  jz      loc_14001B9F6
0x14001b67c  mov     edx, r13d
0x14001b67f  mov     rax, [r14]
0x14001b682  xor     r9d, r9d
0x14001b685  xor     r8d, r8d
0x14001b688  mov     rcx, r14
0x14001b68b  mov     rax, [rax+28h]
0x14001b68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b694  mov     r15d, eax
0x14001b697  test    eax, eax
0x14001b699  jns     loc_14001B950
0x14001b69f  mov     rcx, [rbp+47h]; this
0x14001b6a3  mov     r9d, eax; char *
0x14001b6a6  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001b6ad  mov     edx, 454h; void *
0x14001b6b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001b6b7  nop
0x14001b6b8  test    rsi, rsi
0x14001b6bb  jz      short loc_14001B6CD
0x14001b6bd  mov     rax, [rsi]
0x14001b6c0  mov     rcx, rsi
0x14001b6c3  mov     rax, [rax+10h]
0x14001b6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b6cc  nop
0x14001b6cd  test    r14, r14
0x14001b6d0  jz      short loc_14001B6E2
0x14001b6d2  mov     rax, [r14]
0x14001b6d5  mov     rcx, r14
0x14001b6d8  mov     rax, [rax+10h]
0x14001b6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b6e1  nop
0x14001b6e2  test    rdi, rdi
0x14001b6e5  jz      short loc_14001B6F7
0x14001b6e7  mov     rax, [rdi]
0x14001b6ea  mov     rcx, rdi
0x14001b6ed  mov     rax, [rax+10h]
0x14001b6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b6f6  nop
0x14001b6f7  test    rbx, rbx
0x14001b6fa  jz      short loc_14001B70C
0x14001b6fc  mov     rax, [rbx]
0x14001b6ff  mov     rcx, rbx
0x14001b702  mov     rax, [rax+10h]
0x14001b706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b70b  nop
0x14001b70c  jmp     loc_14001BE04
0x14001b711  mov     rcx, [rbp+47h]; this
0x14001b715  mov     r9d, r15d; char *
0x14001b718  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001b71f  mov     edx, 43Eh; void *
0x14001b724  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001b729  nop
0x14001b72a  test    rsi, rsi
0x14001b72d  jz      short loc_14001B73F
0x14001b72f  mov     rax, [rsi]
0x14001b732  mov     rcx, rsi
0x14001b735  mov     rax, [rax+10h]
0x14001b739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b73e  nop
0x14001b73f  mov     rcx, [rbp+3Fh+var_80]
0x14001b743  test    rcx, rcx
0x14001b746  jz      short loc_14001B755
  ... truncated ...
```
