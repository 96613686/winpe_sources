# CProxyDataObject::GetData(tagFORMATETC *,tagSTGMEDIUM *)

- ea: `0x1400481a0`
- end: `0x140048ca2`
- name: `?GetData@CProxyDataObject@@UEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `2818`
- prototype: `int(CProxyDataObject *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `0`
- callee_count: `16`
- tags: ``

## callees

- `0x140004b1c`
- `0x140004cf4`
- `0x1400056c4`
- `0x140005704`
- `0x140005750`
- `0x14000cae0`
- `0x140047460`
- `0x140047804`
- `0x140047f74`
- `0x1400480fc`
- `0x1400481a0`
- `0x140048e0c`
- `0x1400493c8`
- `0x140049880`
- `0x14004af48`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140048941`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x140048941`

## string_xrefs

- `0x140048351`: `CreateStream failed!`
- `0x140048688`: `CopyStgMedium failed!`
- `0x14004848d`: `CopyStgMedium failed.`

## pseudocode

```c
__int64 __fastcall CProxyDataObject::GetData(CProxyDataObject *this, struct tagFORMATETC *a2, struct tagSTGMEDIUM *a3)
{
  PVOID *v6; // rax
  int v7; // ebx
  int cfFormat; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  int Stream; // edi
  int v13; // ebx
  CClipFormatTypes *v14; // rcx
  LONG lindex; // ebx
  DWORD v16; // ebx
  unsigned int v17; // eax
  CProxyStreamManager *v18; // rcx
  unsigned int v19; // eax
  int v20; // edx
  const char *v21; // rcx
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  CProxyDataObject *v25; // rcx
  unsigned int v26; // eax
  unsigned int v27; // eax
  __int64 v28; // rax
  __int64 v29; // r12
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  int v34; // eax
  int v35; // ebx
  unsigned int v36; // eax
  int v37; // ebx
  unsigned int v38; // eax
  int v39; // ebx
  unsigned int v40; // eax
  int v41; // ebx
  unsigned int v42; // eax
  DWORD v43; // eax
  __int64 v44; // r8
  DWORD v45; // ebx
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // eax
  PVOID *v49; // rcx
  int v50; // ebx
  unsigned int v51; // eax
  int v52; // ebx
  unsigned int v53; // eax
  unsigned int v54; // eax
  DWORD tymed; // edi
  DWORD *v56; // rbx
  int v57; // r12d
  unsigned int v58; // eax
  __int64 v59; // rdx
  int v60; // edi
  unsigned int v61; // eax
  unsigned int v63; // eax
  struct IStream **v64; // [rsp+28h] [rbp-18h]
  HANDLE *lpHandles; // [rsp+30h] [rbp-10h] BYREF
  __int64 v66; // [rsp+38h] [rbp-8h] BYREF
  DWORD nCount; // [rsp+80h] [rbp+40h] BYREF
  unsigned int v68; // [rsp+98h] [rbp+58h] BYREF

  v66 = 0;
  lpHandles = 0;
  nCount = 0;
  v68 = 0;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v7 = *((_DWORD *)this + 43);
    cfFormat = a2->cfFormat;
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DdD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids,
      CurrentThreadActivityIdPrefix,
      cfFormat,
      v7);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v6 == &WPP_GLOBAL_Control || (*((_BYTE *)v6 + 28) & 1) == 0 || *((_BYTE *)v6 + 25) < 2u )
      goto LABEL_11;
    v10 = RdpWppGetCurrentThreadActivityIdPrefix();
    v11 = 43;
LABEL_10:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v10);
LABEL_11:
    Stream = -2147467261;
    goto LABEL_173;
  }
  v13 = a2->cfFormat;
  if ( v13 != CClipFormatTypes::FileContents(this) )
  {
    v24 = CClipFormatTypes::EnterpriseId(v14);
    v25 = (CProxyDataObject *)a2->cfFormat;
    if ( (_DWORD)v25 == v24 )
    {
      if ( *((_QWORD *)this + 11) )
      {
        Stream = CProxyDataObject::CopyStgMedium(v25, (const struct tagSTGMEDIUM *)((char *)this + 80), a3);
        if ( Stream >= 0 )
          goto LABEL_172;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_173;
        }
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 48;
LABEL_47:
        v21 = "CopyStgMedium failed.";
        goto LABEL_27;
      }
    }
    else
    {
      v26 = CClipFormatTypes::UploadToCloudId(v25);
      v25 = (CProxyDataObject *)a2->cfFormat;
      if ( (_DWORD)v25 == v26 )
      {
        if ( *((_QWORD *)this + 14) )
        {
          Stream = CProxyDataObject::CopyStgMedium(v25, (const struct tagSTGMEDIUM *)((char *)this + 104), a3);
          if ( Stream >= 0 )
            goto LABEL_172;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_173;
          }
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 49;
          goto LABEL_47;
        }
      }
      else
      {
        v27 = CClipFormatTypes::IncludeInHistoryId(v25);
        v25 = (CProxyDataObject *)a2->cfFormat;
        if ( (_DWORD)v25 == v27 && *((_QWORD *)this + 17) )
        {
          Stream = CProxyDataObject::CopyStgMedium(v25, (const struct tagSTGMEDIUM *)((char *)this + 128), a3);
          if ( Stream >= 0 )
            goto LABEL_172;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_173;
          }
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          v20 = 50;
          goto LABEL_47;
        }
      }
    }
    v28 = *((_QWORD *)this + 2);
    if ( !v28 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_11;
      }
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      v11 = 51;
      goto LABEL_10;
    }
    v29 = *(_QWORD *)(v28 + 96);
    if ( !v29 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v30 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v30);
      }
      Stream = -2147418113;
      goto LABEL_173;
    }
    if ( (_WORD)v25 == 15 && *((_QWORD *)this + 8) )
    {
      Stream = CProxyDataObject::CopyStgMedium(v25, (const struct tagSTGMEDIUM *)((char *)this + 56), a3);
      if ( Stream >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v31 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v31);
        }
        goto LABEL_173;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v32 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(v64) = Stream;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          54,
          (unsigned int)WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids,
          v32,
          (__int64)"CopyStgMedium failed!",
          v64,
          lpHandles,
          v66);
      }
    }
    Stream = (*(__int64 (__fastcall **)(__int64, HANDLE **, DWORD *))(*(_QWORD *)v29 + 24LL))(v29, &lpHandles, &nCount);
    if ( Stream < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 55;
        v21 = "GetFormatDataEvents failed!";
        goto LABEL_27;
      }
      goto LABEL_173;
    }
    Stream = CProxyDataObjectManager::AcquireDataObject(
               *((CProxyDataObjectManager **)this + 3),
               (CProxyDataObject *)((char *)this - 48),
               *((_DWORD *)this + 43));
    if ( Stream < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        v20 = 56;
        v21 = "AcquireDataObject failed";
        goto LABEL_27;
      }
      goto LABEL_173;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v33 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v33);
    }
    v34 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)v29 + 32LL))(
            v29,
            *((unsigned int *)this + 43),
            a2->cfFormat,
            &v68);
    Stream = v34;
    if ( v34 < 0 )
    {
      if ( (v34 & 0x1FFF0000) == 0x70000 && (_WORD)v34 == 1169 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v35 = a2->cfFormat;
          v36 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v36, v35);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v37 = a2->cfFormat;
        v38 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids,
          v38,
          v37,
          Stream);
      }
      if ( (int)CProxyDataObjectManager::ReleaseDataObject(
                  *((CProxyDataObjectManager **)this + 3),
                  *((_DWORD *)this + 43)) < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v39 = *((_DWORD *)this + 43);
        v40 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v40, v39);
      }
      goto LABEL_173;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v41 = a2->cfFormat;
      v42 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v42, v41);
    }
    v43 = WaitForMultipleObjects(nCount, lpHandles, 0, 0x493E0u);
    v45 = v43;
    if ( v43 )
    {
      if ( v43 >= nCount )
      {
        if ( v43 == 258 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v47 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v47);
          }
        }
        else if ( v43 != -1
               && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v48 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            64,
            WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids,
            v48,
            v45 - 128);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v46 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v46, v45);
      }
      LOBYTE(v44) = 7;
      (*(void (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v29 + 40LL))(v29, v68, v44, 11);
LABEL_135:
      Stream = -2147467259;
      goto LABEL_173;
    }
    v49 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v50 = a2->cfFormat;
      v51 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v51, v50);
      v49 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !*((_QWORD *)this + 5) )
    {
      if ( v49 != &WPP_GLOBAL_Control && (*((_BYTE *)v49 + 28) & 1) != 0 && *((_BYTE *)v49 + 25) >= 2u )
      {
        v52 = a2->cfFormat;
        v53 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v53, v52);
      }
      goto LABEL_135;
    }
    if ( v49 != &WPP_GLOBAL_Control && (*((_BYTE *)v49 + 28) & 1) != 0 && *((_BYTE *)v49 + 25) >= 5u )
    {
      v54 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v54);
      v49 = (PVOID *)WPP_GLOBAL_Control;
    }
    tymed = a2->tymed;
    v56 = (DWORD *)((char *)this + 32);
    v57 = *((_DWORD *)this + 8);
    if ( (tymed & v57) == tymed )
    {
LABEL_165:
      a3->tymed = *v56;
      a3->pUnkForRelease = (IUnknown *)*((_QWORD *)this + 6);
      a3->hBitmap = (HBITMAP)*((_QWORD *)this + 5);
      if ( a2->cfFormat == 15 )
      {
        v60 = CProxyDataObject::CopyStgMedium(
                (CProxyDataObject *)v49,
                (const struct tagSTGMEDIUM *)((char *)this + 32),
                (struct tagSTGMEDIUM *)((char *)this + 56));
        if ( v60 < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v61 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v61, v60);
        }
      }
      *(_OWORD *)v56 = 0;
      *((_QWORD *)this + 6) = 0;
      goto LABEL_172;
    }
    if ( a2->cfFormat == 3 )
    {
      if ( (tymed & 1) != 0 && v57 == 32 )
      {
        if ( v49 == &WPP_GLOBAL_Control || (*((_BYTE *)v49 + 28) & 1) == 0 || *((_BYTE *)v49 + 25) < 4u )
          goto LABEL_165;
        v58 = RdpWppGetCurrentThreadActivityIdPrefix();
        v59 = 68;
        goto LABEL_164;
      }
    }
    else if ( a2->cfFormat == 9 && (tymed & 1) != 0 && v57 == 16 )
    {
      if ( v49 == &WPP_GLOBAL_Control || (*((_BYTE *)v49 + 28) & 1) == 0 || *((_BYTE *)v49 + 25) < 4u )
        goto LABEL_165;
      v58 = RdpWppGetCurrentThreadActivityIdPrefix();
      v59 = 69;
LABEL_164:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v59, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v58);
      goto LABEL_165;
    }
    if ( v49 != &WPP_GLOBAL_Control && (*((_BYTE *)v49 + 28) & 1) != 0 && *((_BYTE *)v49 + 25) >= 2u )
    {
      v63 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids,
        v63,
        tymed,
        v57);
    }
    goto LABEL_39;
  }
  lindex = a2->lindex;
  if ( lindex < 0 )
  {
    if ( lindex != -1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v22, lindex);
      }
      Stream = -2147221400;
      goto LABEL_173;
    }
    a2->lindex = 0;
  }
  v16 = a2->tymed;
  if ( (v16 & 4) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v23, v16);
    }
LABEL_39:
    Stream = -2147221399;
    goto LABEL_173;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids, v17);
  }
  v18 = *(CProxyStreamManager **)(*((_QWORD *)this + 3) + 104LL);
  if ( !v18 )
  {
    Stream = -2147221398;
    goto LABEL_173;
  }
  Stream = CProxyStreamManager::CreateStream(
             v18,
             (CProxyDataObject *)((char *)this - 48),
             *((_DWORD *)this + 43),
             a2->lindex,
             *((_DWORD *)this + 44),
             &a3->pstm);
  if ( Stream >= 0 )
  {
    a3->tymed = 4;
    a3->pUnkForRelease = 0;
LABEL_172:
    Stream = 0;
    goto LABEL_173;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v19 = RdpWppGetCurrentThreadActivityIdPrefix();
    v20 = 46;
    v21 = "CreateStream failed!";
LABEL_27:
    LODWORD(v64) = Stream;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v20,
      (unsigned int)WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids,
      v19,
      (__int64)v21,
      v64);
  }
LABEL_173:
  TCntPtr<CRdpClipMainWnd>::SafeRelease(&v66);
  return (unsigned int)Stream;
}

```

## disassembly

```asm
0x1400481a0  mov     [rsp-38h+arg_8], rbx
0x1400481a5  push    rbp
0x1400481a6  push    rsi
0x1400481a7  push    rdi
0x1400481a8  push    r12
0x1400481aa  push    r13
0x1400481ac  push    r14
0x1400481ae  push    r15
0x1400481b0  mov     rbp, rsp
0x1400481b3  sub     rsp, 40h
0x1400481b7  xor     edi, edi
0x1400481b9  mov     r15, r8
0x1400481bc  mov     [rbp+var_8], rdi
0x1400481c0  mov     r14, rdx
0x1400481c3  mov     [rbp+lpHandles], rdi
0x1400481c7  mov     rsi, rcx
0x1400481ca  mov     [rbp+nCount], edi
0x1400481cd  mov     [rbp+arg_18], edi
0x1400481d0  mov     rax, cs:WPP_GLOBAL_Control
0x1400481d7  lea     r12, WPP_GLOBAL_Control
0x1400481de  cmp     rax, r12
0x1400481e1  jz      short loc_14004822D
0x1400481e3  test    byte ptr [rax+1Ch], 1
0x1400481e7  jz      short loc_14004822D
0x1400481e9  cmp     byte ptr [rax+19h], 5
0x1400481ed  jb      short loc_14004822D
0x1400481ef  mov     ebx, [rcx+0ACh]
0x1400481f5  movzx   edi, word ptr [rdx]
0x1400481f8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400481fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140048204  lea     r8, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids
0x14004820b  mov     edx, 2Ah ; '*'
0x140048210  mov     dword ptr [rsp+40h+var_18], ebx
0x140048214  mov     r9d, eax
0x140048217  mov     [rsp+40h+var_20], edi
0x14004821b  mov     rcx, [rcx+10h]
0x14004821f  call    WPP_SF_DdD
0x140048224  mov     rax, cs:WPP_GLOBAL_Control
0x14004822b  xor     edi, edi
0x14004822d  cmp     [rsi+18h], rdi
0x140048231  jnz     short loc_140048272
0x140048233  cmp     rax, r12
0x140048236  jz      short loc_140048268
0x140048238  test    byte ptr [rax+1Ch], 1
0x14004823c  jz      short loc_140048268
0x14004823e  cmp     byte ptr [rax+19h], 2
0x140048242  jb      short loc_140048268
0x140048244  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140048249  mov     edx, 2Bh ; '+'
0x14004824e  mov     rcx, cs:WPP_GLOBAL_Control
0x140048255  lea     r8, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids
0x14004825c  mov     r9d, eax
0x14004825f  mov     rcx, [rcx+10h]
0x140048263  call    WPP_SF_d
0x140048268  mov     edi, 80004003h
0x14004826d  jmp     loc_140048C30
0x140048272  movzx   ebx, word ptr [r14]
0x140048276  call    ?FileContents@CClipFormatTypes@@QEAAIXZ; CClipFormatTypes::FileContents(void)
0x14004827b  cmp     ebx, eax
0x14004827d  jnz     loc_140048432
0x140048283  mov     ebx, [r14+14h]
0x140048287  test    ebx, ebx
0x140048289  jns     short loc_140048298
0x14004828b  cmp     ebx, 0FFFFFFFFh
0x14004828e  jnz     loc_140048380
0x140048294  mov     [r14+14h], edi
0x140048298  mov     ebx, [r14+18h]
0x14004829c  test    bl, 4
0x14004829f  jz      loc_1400483E8
0x1400482a5  mov     rax, cs:WPP_GLOBAL_Control
0x1400482ac  cmp     rax, r12
0x1400482af  jz      short loc_1400482E1
0x1400482b1  test    byte ptr [rax+1Ch], 1
0x1400482b5  jz      short loc_1400482E1
0x1400482b7  cmp     byte ptr [rax+19h], 5
0x1400482bb  jb      short loc_1400482E1
0x1400482bd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400482c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400482c9  lea     r8, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids
0x1400482d0  mov     edx, 2Dh ; '-'
0x1400482d5  mov     r9d, eax
0x1400482d8  mov     rcx, [rcx+10h]
0x1400482dc  call    WPP_SF_d
0x1400482e1  mov     rax, [rsi+18h]
0x1400482e5  mov     rcx, [rax+68h]; this
0x1400482e9  test    rcx, rcx
0x1400482ec  jz      loc_1400483DE
0x1400482f2  mov     r9d, [r14+14h]; int
0x1400482f6  lea     rax, [r15+8]
0x1400482fa  mov     r8d, [rsi+0ACh]; unsigned int
0x140048301  lea     rdx, [rsi-30h]; struct CProxyDataObject *
0x140048305  mov     [rsp+40h+var_18], rax; struct IStream **
0x14004830a  mov     eax, [rsi+0B0h]
0x140048310  mov     [rsp+40h+var_20], eax; int
0x140048314  call    ?CreateStream@CProxyStreamManager@@QEAAJPEAVCProxyDataObject@@KJHPEAPEAUIStream@@@Z; CProxyStreamManager::CreateStream(CProxyDataObject *,ulong,long,int,IStream * *)
0x140048319  mov     edi, eax
0x14004831b  test    eax, eax
0x14004831d  jns     loc_1400483CA
0x140048323  mov     rax, cs:WPP_GLOBAL_Control
0x14004832a  cmp     rax, r12
0x14004832d  jz      loc_140048C30
0x140048333  test    byte ptr [rax+1Ch], 8
0x140048337  jz      loc_140048C30
0x14004833d  cmp     byte ptr [rax+19h], 2
0x140048341  jb      loc_140048C30
0x140048347  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004834c  mov     edx, 2Eh ; '.'
0x140048351  lea     rcx, aCreatestreamFa; "CreateStream failed!"
0x140048358  mov     dword ptr [rsp+40h+var_18], edi
0x14004835c  lea     r8, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids
0x140048363  mov     qword ptr [rsp+40h+var_20], rcx
0x140048368  mov     r9d, eax
0x14004836b  mov     rcx, cs:WPP_GLOBAL_Control
0x140048372  mov     rcx, [rcx+10h]
0x140048376  call    WPP_SF_DsD
0x14004837b  jmp     loc_140048C30
0x140048380  mov     rax, cs:WPP_GLOBAL_Control
0x140048387  cmp     rax, r12
0x14004838a  jz      short loc_1400483C0
0x14004838c  test    byte ptr [rax+1Ch], 1
0x140048390  jz      short loc_1400483C0
0x140048392  cmp     byte ptr [rax+19h], 2
0x140048396  jb      short loc_1400483C0
0x140048398  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004839d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400483a4  lea     r8, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids
0x1400483ab  mov     edx, 2Ch ; ','
0x1400483b0  mov     [rsp+40h+var_20], ebx
0x1400483b4  mov     r9d, eax
0x1400483b7  mov     rcx, [rcx+10h]
0x1400483bb  call    WPP_SF_Dd
0x1400483c0  mov     edi, 80040068h
0x1400483c5  jmp     loc_140048C30
0x1400483ca  mov     dword ptr [r15], 4
0x1400483d1  mov     qword ptr [r15+10h], 0
0x1400483d9  jmp     loc_140048C2E
0x1400483de  mov     edi, 8004006Ah
0x1400483e3  jmp     loc_140048C30
0x1400483e8  mov     rax, cs:WPP_GLOBAL_Control
0x1400483ef  cmp     rax, r12
0x1400483f2  jz      short loc_140048428
0x1400483f4  test    byte ptr [rax+1Ch], 1
0x1400483f8  jz      short loc_140048428
0x1400483fa  cmp     byte ptr [rax+19h], 2
0x1400483fe  jb      short loc_140048428
0x140048400  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140048405  mov     rcx, cs:WPP_GLOBAL_Control
0x14004840c  lea     r8, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids
0x140048413  mov     edx, 2Fh ; '/'
0x140048418  mov     [rsp+40h+var_20], ebx
0x14004841c  mov     r9d, eax
0x14004841f  mov     rcx, [rcx+10h]
0x140048423  call    WPP_SF_Dd
0x140048428  mov     edi, 80040069h
0x14004842d  jmp     loc_140048C30
0x140048432  call    ?EnterpriseId@CClipFormatTypes@@QEAAIXZ; CClipFormatTypes::EnterpriseId(void)
0x140048437  movzx   ecx, word ptr [r14]; this
0x14004843b  cmp     ecx, eax
0x14004843d  jnz     short loc_140048499
0x14004843f  cmp     [rsi+58h], rdi
0x140048443  jz      loc_140048558
0x140048449  lea     rdx, [rsi+50h]; struct tagSTGMEDIUM *
0x14004844d  mov     r8, r15; struct tagSTGMEDIUM *
0x140048450  call    ?CopyStgMedium@CProxyDataObject@@IEAAJPEBUtagSTGMEDIUM@@PEAU2@@Z; CProxyDataObject::CopyStgMedium(tagSTGMEDIUM const *,tagSTGMEDIUM *)
0x140048455  mov     edi, eax
0x140048457  test    eax, eax
0x140048459  jns     loc_140048C2E
0x14004845f  mov     rax, cs:WPP_GLOBAL_Control
0x140048466  cmp     rax, r12
0x140048469  jz      loc_140048C30
0x14004846f  test    byte ptr [rax+1Ch], 8
0x140048473  jz      loc_140048C30
0x140048479  cmp     byte ptr [rax+19h], 2
0x14004847d  jb      loc_140048C30
0x140048483  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140048488  mov     edx, 30h ; '0'
0x14004848d  lea     rcx, aCopystgmediumF; "CopyStgMedium failed."
0x140048494  jmp     loc_140048358
0x140048499  call    ?UploadToCloudId@CClipFormatTypes@@QEAAIXZ; CClipFormatTypes::UploadToCloudId(void)
0x14004849e  movzx   ecx, word ptr [r14]; this
0x1400484a2  cmp     ecx, eax
0x1400484a4  jnz     short loc_1400484F6
0x1400484a6  cmp     [rsi+70h], rdi
0x1400484aa  jz      loc_140048558
0x1400484b0  lea     rdx, [rsi+68h]; struct tagSTGMEDIUM *
0x1400484b4  mov     r8, r15; struct tagSTGMEDIUM *
0x1400484b7  call    ?CopyStgMedium@CProxyDataObject@@IEAAJPEBUtagSTGMEDIUM@@PEAU2@@Z; CProxyDataObject::CopyStgMedium(tagSTGMEDIUM const *,tagSTGMEDIUM *)
0x1400484bc  mov     edi, eax
0x1400484be  test    eax, eax
0x1400484c0  jns     loc_140048C2E
0x1400484c6  mov     rax, cs:WPP_GLOBAL_Control
0x1400484cd  cmp     rax, r12
0x1400484d0  jz      loc_140048C30
0x1400484d6  test    byte ptr [rax+1Ch], 8
0x1400484da  jz      loc_140048C30
0x1400484e0  cmp     byte ptr [rax+19h], 2
0x1400484e4  jb      loc_140048C30
0x1400484ea  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400484ef  mov     edx, 31h ; '1'
0x1400484f4  jmp     short loc_14004848D
0x1400484f6  call    ?IncludeInHistoryId@CClipFormatTypes@@QEAAIXZ; CClipFormatTypes::IncludeInHistoryId(void)
0x1400484fb  movzx   ecx, word ptr [r14]; this
0x1400484ff  cmp     ecx, eax
0x140048501  jnz     short loc_140048558
0x140048503  cmp     [rsi+88h], rdi
0x14004850a  jz      short loc_140048558
0x14004850c  lea     rdx, [rsi+80h]; struct tagSTGMEDIUM *
0x140048513  mov     r8, r15; struct tagSTGMEDIUM *
0x140048516  call    ?CopyStgMedium@CProxyDataObject@@IEAAJPEBUtagSTGMEDIUM@@PEAU2@@Z; CProxyDataObject::CopyStgMedium(tagSTGMEDIUM const *,tagSTGMEDIUM *)
0x14004851b  mov     edi, eax
0x14004851d  test    eax, eax
0x14004851f  jns     loc_140048C2E
0x140048525  mov     rax, cs:WPP_GLOBAL_Control
0x14004852c  cmp     rax, r12
0x14004852f  jz      loc_140048C30
0x140048535  test    byte ptr [rax+1Ch], 8
0x140048539  jz      loc_140048C30
0x14004853f  cmp     byte ptr [rax+19h], 2
0x140048543  jb      loc_140048C30
0x140048549  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004854e  mov     edx, 32h ; '2'
0x140048553  jmp     loc_14004848D
0x140048558  mov     rax, [rsi+10h]
0x14004855c  test    rax, rax
0x14004855f  jnz     short loc_140048594
0x140048561  mov     rax, cs:WPP_GLOBAL_Control
0x140048568  cmp     rax, r12
0x14004856b  jz      loc_140048268
0x140048571  test    byte ptr [rax+1Ch], 1
0x140048575  jz      loc_140048268
0x14004857b  cmp     byte ptr [rax+19h], 2
0x14004857f  jb      loc_140048268
0x140048585  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14004858a  mov     edx, 33h ; '3'
0x14004858f  jmp     loc_14004824E
0x140048594  mov     r12, [rax+60h]
0x140048598  test    r12, r12
0x14004859b  jnz     short loc_1400485EA
0x14004859d  mov     rax, cs:WPP_GLOBAL_Control
0x1400485a4  lea     rbx, WPP_GLOBAL_Control
0x1400485ab  cmp     rax, rbx
0x1400485ae  jz      short loc_1400485E0
0x1400485b0  test    byte ptr [rax+1Ch], 1
0x1400485b4  jz      short loc_1400485E0
0x1400485b6  cmp     byte ptr [rax+19h], 2
0x1400485ba  jb      short loc_1400485E0
0x1400485bc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400485c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400485c8  lea     edx, [r12+34h]
0x1400485cd  mov     r9d, eax
0x1400485d0  lea     r8, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids
0x1400485d7  mov     rcx, [rcx+10h]
0x1400485db  call    WPP_SF_d
0x1400485e0  mov     edi, 8000FFFFh
0x1400485e5  jmp     loc_140048C30
0x1400485ea  cmp     cx, 0Fh
0x1400485ee  jnz     loc_1400486B9
0x1400485f4  cmp     [rsi+40h], rdi
0x1400485f8  jz      loc_1400486B9
0x1400485fe  lea     rdx, [rsi+38h]; struct tagSTGMEDIUM *
0x140048602  mov     r8, r15; struct tagSTGMEDIUM *
0x140048605  call    ?CopyStgMedium@CProxyDataObject@@IEAAJPEBUtagSTGMEDIUM@@PEAU2@@Z; CProxyDataObject::CopyStgMedium(tagSTGMEDIUM const *,tagSTGMEDIUM *)
0x14004860a  mov     edi, eax
0x14004860c  test    eax, eax
0x14004860e  js      short loc_140048664
0x140048610  mov     rax, cs:WPP_GLOBAL_Control
0x140048617  lea     rbx, WPP_GLOBAL_Control
0x14004861e  cmp     rax, rbx
0x140048621  jz      loc_140048C30
0x140048627  test    byte ptr [rax+1Ch], 1
0x14004862b  jz      loc_140048C30
0x140048631  cmp     byte ptr [rax+19h], 5
0x140048635  jb      loc_140048C30
0x14004863b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140048640  mov     rcx, cs:WPP_GLOBAL_Control
0x140048647  lea     r8, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids
0x14004864e  mov     edx, 35h ; '5'
0x140048653  mov     r9d, eax
0x140048656  mov     rcx, [rcx+10h]
0x14004865a  call    WPP_SF_d
0x14004865f  jmp     loc_140048C30
0x140048664  mov     rax, cs:WPP_GLOBAL_Control
0x14004866b  lea     rbx, WPP_GLOBAL_Control
0x140048672  cmp     rax, rbx
0x140048675  jz      short loc_1400486C0
0x140048677  test    byte ptr [rax+1Ch], 8
0x14004867b  jz      short loc_1400486C0
0x14004867d  cmp     byte ptr [rax+19h], 2
0x140048681  jb      short loc_1400486C0
0x140048683  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140048688  lea     rcx, aCopystgmediumF_0; "CopyStgMedium failed!"
0x14004868f  mov     dword ptr [rsp+40h+var_18], edi
0x140048693  mov     qword ptr [rsp+40h+var_20], rcx
0x140048698  lea     r8, WPP_8b11c5d4348e3e2af8357e02f009926a_Traceguids
0x14004869f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400486a6  mov     edx, 36h ; '6'
0x1400486ab  mov     r9d, eax
0x1400486ae  mov     rcx, [rcx+10h]
0x1400486b2  call    WPP_SF_DsD
0x1400486b7  jmp     short loc_1400486C0
  ... truncated ...
```
