# RdpWin32RemoteAppPresenter::GenerateUpdateLayeredWindowData(tagUPDATE_LAYERED_WINDOW_DATA *)

- ea: `0x1800ae340`
- end: `0x1800af821`
- name: `?GenerateUpdateLayeredWindowData@RdpWin32RemoteAppPresenter@@IEAAJPEAUtagUPDATE_LAYERED_WINDOW_DATA@@@Z`
- size: `5345`
- prototype: `__int64 __fastcall(RdpWin32RemoteAppPresenter *__hidden this, struct tagUPDATE_LAYERED_WINDOW_DATA *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800af830`

## callees

- `0x180039c98`
- `0x180039ce4`
- `0x1800ae340`
- `0x1800dafe4`
- `0x180270884`
- `0x180273220`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetVersionExW` at `0x1800af5fd`
- `KERNEL32!GetVersionExW` at `0x1800af5fd`
- `KERNEL32!SetLastError` at `0x1800af32c`
- `KERNEL32!SetLastError` at `0x1800af32c`
- `KERNEL32!GetLastError` at `0x1800af3c4`
- `KERNEL32!GetLastError` at `0x1800af3c4`
- `GDI32!SetWorldTransform` at `0x1800aeeb2`
- `GDI32!SetWorldTransform` at `0x1800af44d`
- `GDI32!SetWorldTransform` at `0x1800aeeb2`
- `GDI32!SetWorldTransform` at `0x1800af44d`
- `GDI32!SelectObject` at `0x1800aeaa0`
- `GDI32!SelectObject` at `0x1800aeaa0`
- `GDI32!CreateCompatibleDC` at `0x1800ae9b5`
- `GDI32!CreateCompatibleDC` at `0x1800ae9b5`
- `GDI32!GetWorldTransform` at `0x1800aeea4`
- `GDI32!GetWorldTransform` at `0x1800aeea4`
- `GDI32!CreateDIBSection` at `0x1800aea45`
- `GDI32!CreateDIBSection` at `0x1800aea45`
- `GDI32!SetGraphicsMode` at `0x1800aee96`
- `GDI32!SetGraphicsMode` at `0x1800af45c`
- `GDI32!SetGraphicsMode` at `0x1800aee96`
- `GDI32!SetGraphicsMode` at `0x1800af45c`
- `USER32!GetWindowRect` at `0x1800ae568`
- `USER32!GetWindowRect` at `0x1800ae568`
- `USER32!ReleaseDC` at `0x1800af7fc`
- `USER32!ReleaseDC` at `0x1800af7fc`
- `USER32!GetDC` at `0x1800ae947`
- `USER32!GetDC` at `0x1800ae947`
- `ADVAPI32!EventWriteTransfer` at `0x1800ae550`
- `ADVAPI32!EventWriteTransfer` at `0x1800ae756`
- `ADVAPI32!EventWriteTransfer` at `0x1800ae93a`
- `ADVAPI32!EventWriteTransfer` at `0x1800af066`
- `ADVAPI32!EventWriteTransfer` at `0x1800af17a`
- `ADVAPI32!EventWriteTransfer` at `0x1800af324`
- `ADVAPI32!EventWriteTransfer` at `0x1800af59c`
- `ADVAPI32!EventWriteTransfer` at `0x1800af7bd`
- `ADVAPI32!EventWriteTransfer` at `0x1800ae550`
- `ADVAPI32!EventWriteTransfer` at `0x1800ae756`
- `ADVAPI32!EventWriteTransfer` at `0x1800ae93a`
- `ADVAPI32!EventWriteTransfer` at `0x1800af066`
- `ADVAPI32!EventWriteTransfer` at `0x1800af17a`
- `ADVAPI32!EventWriteTransfer` at `0x1800af324`
- `ADVAPI32!EventWriteTransfer` at `0x1800af59c`
- `ADVAPI32!EventWriteTransfer` at `0x1800af7bd`
- `MSIMG32!AlphaBlend` at `0x1800af36b`
- `MSIMG32!AlphaBlend` at `0x1800af36b`

## string_xrefs

- `0x1800ae480`: `RemoteAppPresenter ignoring present for layered window - no GDI texture created yet (windowId=0x%x).`

## pseudocode

```c
__int64 __fastcall RdpWin32RemoteAppPresenter::GenerateUpdateLayeredWindowData(
        RdpWin32RemoteAppPresenter *this,
        struct tagUPDATE_LAYERED_WINDOW_DATA *a2)
{
  HDC v4; // r12
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v6; // edi
  int v7; // edi
  unsigned int v8; // eax
  __int64 v9; // rcx
  HWND v10; // rcx
  unsigned int v11; // eax
  int v12; // r15d
  int v13; // r13d
  volatile signed __int32 *v14; // rcx
  __int64 v15; // rax
  int IsMarginBlendingRequired; // eax
  int v17; // edi
  int v18; // ecx
  HDC DC; // rax
  unsigned int v20; // eax
  int v21; // edx
  const char *v22; // rcx
  HDC CompatibleDC; // rax
  HBITMAP DIBSection; // rax
  __int64 v25; // rsi
  unsigned int *v26; // r9
  unsigned int v27; // r12d
  int *v28; // r10
  int i; // r8d
  unsigned int j; // edi
  __int64 v31; // rcx
  unsigned int k; // edx
  __int64 v33; // rcx
  _DWORD *v34; // rdi
  int m; // r8d
  int v36; // edi
  __int64 v37; // rcx
  _DWORD *v38; // rdi
  int n; // edx
  __int64 v40; // rcx
  _DWORD *v41; // rdi
  int v42; // r12d
  int v43; // ebx
  int v44; // edi
  int v45; // esi
  unsigned int v46; // eax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rcx
  int v50; // eax
  float v51; // xmm1_4
  unsigned int v52; // esi
  unsigned int v53; // edi
  float v54; // xmm2_4
  float v55; // xmm3_4
  float v56; // xmm1_4
  float v57; // xmm3_4
  unsigned int v58; // eax
  float v59; // xmm1_4
  int v60; // r12d
  __int64 v61; // r12
  __int64 v62; // rcx
  signed int LastError; // eax
  unsigned int v64; // eax
  __int64 v65; // rcx
  ULONG UserDataCount[2]; // [rsp+28h] [rbp-E0h]
  ULONG UserDataCounta[2]; // [rsp+28h] [rbp-E0h]
  PEVENT_DATA_DESCRIPTOR UserData; // [rsp+30h] [rbp-D8h]
  PEVENT_DATA_DESCRIPTOR UserDataa; // [rsp+30h] [rbp-D8h]
  __int64 xoriginSrc; // [rsp+38h] [rbp-D0h]
  __int64 xoriginSrca; // [rsp+38h] [rbp-D0h]
  __int64 yoriginSrc; // [rsp+40h] [rbp-C8h]
  __int64 yoriginSrca; // [rsp+40h] [rbp-C8h]
  __int64 wSrc; // [rsp+48h] [rbp-C0h]
  __int64 wSrca; // [rsp+48h] [rbp-C0h]
  __int64 hSrc; // [rsp+50h] [rbp-B8h]
  __int64 hSrca; // [rsp+50h] [rbp-B8h]
  __int64 ftn; // [rsp+58h] [rbp-B0h]
  unsigned int v80; // [rsp+88h] [rbp-80h] BYREF
  int v81; // [rsp+8Ch] [rbp-7Ch] BYREF
  unsigned int v82; // [rsp+90h] [rbp-78h] BYREF
  unsigned int v83; // [rsp+94h] [rbp-74h] BYREF
  unsigned int v84; // [rsp+98h] [rbp-70h] BYREF
  unsigned int v85; // [rsp+9Ch] [rbp-6Ch] BYREF
  int v86; // [rsp+A0h] [rbp-68h] BYREF
  int yoriginDest; // [rsp+A4h] [rbp-64h] BYREF
  int v88; // [rsp+A8h] [rbp-60h] BYREF
  int v89; // [rsp+ACh] [rbp-5Ch] BYREF
  void (*v90)(__int64, const wchar_t *, ...); // [rsp+B0h] [rbp-58h] BYREF
  EVENT_DESCRIPTOR v91; // [rsp+B8h] [rbp-50h] BYREF
  EVENT_DESCRIPTOR v92; // [rsp+C8h] [rbp-40h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+D8h] [rbp-30h] BYREF
  struct tagRECT Rect; // [rsp+E8h] [rbp-20h] BYREF
  XFORM v95; // [rsp+F8h] [rbp-10h] BYREF
  _XFORM xf; // [rsp+110h] [rbp+8h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+128h] [rbp+20h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v98; // [rsp+248h] [rbp+140h] BYREF
  char *v99; // [rsp+258h] [rbp+150h]
  int v100; // [rsp+260h] [rbp+158h]
  int v101; // [rsp+264h] [rbp+15Ch]
  _DWORD *v102; // [rsp+268h] [rbp+160h]
  __int64 v103; // [rsp+270h] [rbp+168h]
  struct tagRECT *p_Rect; // [rsp+278h] [rbp+170h]
  __int64 v105; // [rsp+280h] [rbp+178h]
  unsigned int *v106; // [rsp+288h] [rbp+180h]
  __int64 v107; // [rsp+290h] [rbp+188h]
  int *v108; // [rsp+298h] [rbp+190h]
  __int64 v109; // [rsp+2A0h] [rbp+198h]
  _DWORD *v110; // [rsp+2A8h] [rbp+1A0h]
  __int64 v111; // [rsp+2B0h] [rbp+1A8h]
  unsigned int *p_yoriginDest; // [rsp+2B8h] [rbp+1B0h]
  __int64 v113; // [rsp+2C0h] [rbp+1B8h]
  unsigned int *v114; // [rsp+2C8h] [rbp+1C0h]
  __int64 v115; // [rsp+2D0h] [rbp+1C8h]
  int *v116; // [rsp+2D8h] [rbp+1D0h]
  __int64 v117; // [rsp+2E0h] [rbp+1D8h]
  struct tagRECT *v118; // [rsp+2E8h] [rbp+1E0h]
  __int64 v119; // [rsp+2F0h] [rbp+1E8h]
  _BYTE v120[48]; // [rsp+2F8h] [rbp+1F0h] BYREF

  *(_QWORD *)&v91.Id = 0;
  v4 = 0;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        (unsigned int)&WPP_8078f27b9915346d8ab3175536312c32_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"pUlwData");
    }
    v6 = -2147467261;
    goto LABEL_142;
  }
  if ( !*((_QWORD *)this + 18) )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v7 = *((_DWORD *)this + 20);
      v8 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_8078f27b9915346d8ab3175536312c32_Traceguids, v8, v7);
    }
    v9 = *((_QWORD *)this + 47);
    v6 = -2147019873;
    if ( v9 )
      (*(void (**)(__int64, const wchar_t *, ...))(*(_QWORD *)v9 + 224LL))(
        v9,
        L"RemoteAppPresenter ignoring present for layered window - no GDI texture created yet (windowId=0x%x).",
        0,
        *((unsigned int *)this + 20));
    goto LABEL_142;
  }
  if ( (unsigned int)dword_1808B7628 > 5 )
  {
    v81 = *((_DWORD *)this + 20);
    *(_QWORD *)&v120[40] = 4;
    *(_QWORD *)&v120[32] = &v81;
    *(_DWORD *)&EventDescriptor.Level = 261;
    *(_QWORD *)v120 = off_1808B7630;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    *(_DWORD *)&v120[8] = *(unsigned __int16 *)off_1808B7630;
    *(_QWORD *)&v120[16] = byte_18086513B;
    *(_DWORD *)&v120[12] = 2;
    *(_QWORD *)&v120[24] = 0x10000001DLL;
    v84 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(qword_1808B7648, &EventDescriptor, 0, 0, 3u, (PEVENT_DATA_DESCRIPTOR)v120);
  }
  v10 = (HWND)*((_QWORD *)this + 25);
  Rect = 0;
  if ( !GetWindowRect(v10, &Rect) )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        &WPP_8078f27b9915346d8ab3175536312c32_Traceguids,
        v11,
        -2147019873);
    }
    v6 = -2147019873;
    goto LABEL_142;
  }
  v12 = Rect.right - Rect.left;
  v13 = Rect.bottom - Rect.top;
  *((_DWORD *)a2 + 7) = 2;
  v14 = (volatile signed __int32 *)*((_QWORD *)a2 + 4);
  *(_DWORD *)&v91.Id = v12;
  *(_DWORD *)&v91.Level = v13;
  if ( *((volatile signed __int32 **)this + 18) != v14 )
  {
    if ( v14 )
    {
      *((_QWORD *)a2 + 4) = 0;
      if ( _InterlockedExchangeAdd(v14 + 4, 0xFFFFFFFF) == 1 )
      {
        _InterlockedIncrement(v14 + 4);
        (*(void (__fastcall **)(volatile signed __int32 *, __int64))(*(_QWORD *)v14 + 120LL))(v14, 1);
      }
    }
    v15 = *((_QWORD *)this + 18);
    *((_QWORD *)a2 + 4) = v15;
    if ( v15 )
      _InterlockedIncrement((volatile signed __int32 *)(v15 + 16));
  }
  *((_DWORD *)a2 + 6) = 33488896;
  *((_QWORD *)a2 + 2) = 0;
  *(_QWORD *)a2 = *(_QWORD *)&v91.Id;
  IsMarginBlendingRequired = RdpWin32RemoteAppPresenter::IsMarginBlendingRequired(this);
  v17 = IsMarginBlendingRequired;
  if ( *((float *)this + 57) == 1.0
    && *((float *)this + 58) == 1.0
    && !IsMarginBlendingRequired
    && !*((_DWORD *)this + 56) )
  {
    if ( (unsigned int)dword_1808B7628 > 5 )
    {
      v81 = *((_DWORD *)this + 20);
      *(_QWORD *)&v120[40] = 4;
      *(_QWORD *)&v120[32] = &v81;
      *(_DWORD *)&EventDescriptor.Level = 5;
      *(_QWORD *)v120 = off_1808B7630;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      *(_DWORD *)&v120[8] = *(unsigned __int16 *)off_1808B7630;
      *(_QWORD *)&v120[16] = &dword_180865164;
      *(_DWORD *)&v120[12] = 2;
      *(_QWORD *)&v120[24] = 0x10000002FLL;
      v84 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(qword_1808B7648, &EventDescriptor, 0, 0, 3u, (PEVENT_DATA_DESCRIPTOR)v120);
    }
    *((_QWORD *)a2 + 1) = *(_QWORD *)(*((_QWORD *)a2 + 4) + 80LL);
    goto LABEL_148;
  }
  memset(v120, 0, 44);
  *(_QWORD *)&EventDescriptor.Id = 0;
  memset(&xf, 0, sizeof(xf));
  memset(&v95, 0, sizeof(v95));
  if ( (unsigned int)dword_1808B7628 > 5 )
  {
    v18 = *((_DWORD *)this + 56);
    v84 = *((_DWORD *)this + 62);
    yoriginDest = *((_DWORD *)this + 60);
    v88 = *((_DWORD *)this + 61);
    v89 = *((_DWORD *)this + 59);
    v81 = v18;
    v83 = v18 != 0;
    v82 = *((_DWORD *)this + 20);
    v91.Keyword = 0;
    v116 = &v81;
    LODWORD(v90) = IsMarginBlendingRequired;
    v114 = &v84;
    p_yoriginDest = (unsigned int *)&yoriginDest;
    v110 = &v88;
    v108 = &v89;
    v106 = &v83;
    p_Rect = (struct tagRECT *)&v90;
    v102 = &v82;
    *(_DWORD *)&v91.Level = 5;
    v98.Ptr = (ULONGLONG)off_1808B7630;
    v117 = 4;
    v115 = 4;
    v113 = 4;
    v111 = 4;
    v109 = 4;
    v107 = 4;
    v105 = 4;
    v103 = 4;
    *(_DWORD *)&v91.Id = 184549376;
    v98.Size = *(unsigned __int16 *)off_1808B7630;
    v99 = (char *)&unk_1808650A8;
    v98.Reserved = 2;
    v100 = 135;
    v101 = 1;
    v80 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(qword_1808B7648, &v91, 0, 0, 0xAu, &v98);
  }
  DC = GetDC(*((HWND *)this + 25));
  *(_QWORD *)&v91.Id = DC;
  v4 = DC;
  if ( !DC )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    v21 = 48;
    v22 = "hdcWindow";
LABEL_42:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v21,
      (unsigned int)&WPP_8078f27b9915346d8ab3175536312c32_Traceguids,
      v20,
      (__int64)v22);
LABEL_43:
    v6 = -2147467261;
LABEL_142:
    if ( (unsigned int)dword_1808B7628 > 3 )
    {
      v86 = *((_DWORD *)this + 20);
      Rect.left = v6;
      p_Rect = &Rect;
      v105 = 4;
      v102 = &v86;
      *(_DWORD *)&v92.Level = 515;
      v98.Ptr = (ULONGLONG)off_1808B7630;
      v103 = 4;
      *(_DWORD *)&v92.Id = 184549376;
      v92.Keyword = 0;
      v98.Size = *(unsigned __int16 *)off_1808B7630;
      v99 = byte_180864F31;
      v98.Reserved = 2;
      v100 = 37;
      v101 = 1;
      v85 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(qword_1808B7648, &v92, 0, 0, 4u, &v98);
    }
    if ( v6 != -2147019873 )
    {
      v65 = *((_QWORD *)this + 47);
      if ( v65 )
        (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v65 + 232LL))(
          v65,
          L"RemoteAppPresenter GenerateULWData failed",
          v6,
          0,
          0);
    }
    goto LABEL_154;
  }
  CompatibleDC = CreateCompatibleDC(DC);
  *((_QWORD *)a2 + 1) = CompatibleDC;
  if ( !CompatibleDC )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    v21 = 49;
    v22 = "pUlwData->hdcSrc";
    goto LABEL_42;
  }
  *(_DWORD *)v120 = 40;
  *(_DWORD *)&v120[4] = v12;
  *(_DWORD *)&v120[8] = v13;
  *(_QWORD *)&v120[12] = 2097153;
  *(_DWORD *)&v120[20] = 4 * v12 * v13;
  DIBSection = CreateDIBSection(CompatibleDC, (const BITMAPINFO *)v120, 0, (void **)&EventDescriptor, 0, 0);
  *((_QWORD *)a2 + 5) = DIBSection;
  if ( !DIBSection )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_43;
    }
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    v21 = 50;
    v22 = "pUlwData->hBitmap";
    goto LABEL_42;
  }
  v25 = *(_QWORD *)&EventDescriptor.Id;
  *((_QWORD *)a2 + 6) = SelectObject(*((HDC *)a2 + 1), DIBSection);
  if ( v17 )
  {
    v26 = (unsigned int *)((char *)this + 248);
    v27 = *((_DWORD *)this + 59);
    v28 = (int *)((char *)this + 244);
    v80 = *((_DWORD *)this + 60);
    *(_QWORD *)&Rect.left = (char *)this + 248;
    if ( v27 + v80 > v12 || *v28 + *v26 > v13 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control || ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) == 0 )
      {
        *(_QWORD *)&Rect.left = (char *)this + 248;
      }
      else if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v43 = *v28;
        v44 = *((_DWORD *)this + 62);
        v45 = *((_DWORD *)this + 20);
        *(_QWORD *)&Rect.left = (char *)this + 248;
        v46 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DDDDDDdd(*((_QWORD *)WPP_GLOBAL_Control + 2), v47, v48, v46, v45, v27, v80, v43, v44, v12, v13);
      }
      v49 = *((_QWORD *)this + 47);
      v6 = -2147019873;
      if ( v49 )
      {
        LODWORD(hSrc) = v13;
        LODWORD(wSrc) = v12;
        LODWORD(yoriginSrc) = **(_DWORD **)&Rect.left;
        LODWORD(xoriginSrc) = *((_DWORD *)this + 61);
        LODWORD(UserData) = *((_DWORD *)this + 60);
        UserDataCount[0] = *((_DWORD *)this + 59);
        (*(void (**)(__int64, const wchar_t *, ...))(*(_QWORD *)v49 + 224LL))(
          v49,
          L"RemoteAppPresenter ignoring present for layered window - invalid window dimensions (windowId=0x%x, leftResizeM"
           "argin=%u, rightResizeMargin=%u, topResizeMargin=%u, bottomResizeMargin=%u, cx=%d, cy=%d)",
          0,
          *((unsigned int *)this + 20),
          *(_QWORD *)UserDataCount,
          UserData,
          xoriginSrc,
          yoriginSrc,
          wSrc,
          hSrc);
      }
      goto LABEL_141;
    }
    if ( v13 > 0 )
    {
      for ( i = 0; i < v13; ++i )
      {
        for ( j = 0; j < v27; v27 = *((_DWORD *)this + 59) )
        {
          v31 = (int)(4 * j++);
          *(_DWORD *)(v31 + v25 + 4 * v12 * i) = 0x1000000;
        }
      }
    }
    for ( k = 0; k < *v26; ++k )
    {
      if ( v12 > 0 )
      {
        v33 = v12;
        v34 = (_DWORD *)(v25 + (int)(4 * k * v12));
        while ( v33 )
        {
          *v34++ = 0x1000000;
          --v33;
        }
      }
    }
    for ( m = 0; m < v13; ++m )
    {
      v36 = v12 - *((_DWORD *)this + 60);
      if ( v36 < v12 )
      {
        v37 = *((int *)this + 60);
        v38 = (_DWORD *)(v25 + 4 * m * v12 + 4 * v36);
        while ( v37 )
        {
          *v38++ = 0x1000000;
          --v37;
        }
      }
    }
    for ( n = v13 - *v28; n < v13; ++n )
    {
      if ( v12 > 0 )
      {
        v40 = v12;
        v41 = (_DWORD *)(v25 + 4 * n * v12);
        while ( v40 )
        {
          *v41++ = 0x1000000;
          --v40;
        }
      }
    }
    v42 = *((_DWORD *)this + 59);
    v12 = v12 - *((_DWORD *)this + 60) - v42;
    v13 = v13 - *v28 - *v26;
    yoriginDest = *v28;
  }
  else
  {
    v42 = 0;
    yoriginDest = 0;
  }
  v50 = *((_DWORD *)this + 56);
  v84 = v42;
  if ( v50 )
  {
    if ( v50 == 90 )
    {
      v95.eM11 = 0.0;
      v95.eM22 = 0.0;
      v95.eDy = 0.0;
      v95.eDx = (float)v12;
      v95.eM21 = (float)((float)v12 * -1.0) / (float)v13;
      v51 = *((float *)this + 57);
      v95.eM12 = (float)v13 / (float)v12;
      if ( v51 == 1.0 && *((float *)this + 58) == 1.0 )
      {
        v52 = v13;
        v53 = v12;
LABEL_107:
        SetGraphicsMode(*((HDC *)a2 + 1), 2);
        GetWorldTransform(*((HDC *)a2 + 1), &xf);
        SetWorldTransform(*((HDC *)a2 + 1), &v95);
        goto LABEL_117;
      }
      v54 = (float)v12 / v51;
      v52 = (int)(float)((float)v13 / *((float *)this + 58));
    }
    else
    {
      if ( v50 == 180 )
      {
        v55 = *((float *)this + 57);
        v95.eDx = (float)v12;
        v95.eDy = (float)v13;
        *(__m128i *)&v95.eM11 = _mm_load_si128((const __m128i *)&_xmm_bf8000000000000000000000bf800000);
        if ( v55 == 1.0 && *((float *)this + 58) == 1.0 )
        {
          v52 = v12;
          v53 = v13;
          goto LABEL_107;
        }
        v54 = (float)v13 / *((float *)this + 58);
        v56 = (float)v12 / v55;
      }
      else
      {
        if ( v50 != 270 )
        {
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v58 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              52,
              &WPP_8078f27b9915346d8ab3175536312c32_Traceguids,
              v58,
              -2147024809);
          }
          v6 = -2147024809;
          goto LABEL_141;
        }
        v57 = *((float *)this + 57);
        v95.eM11 = 0.0;
        *(_QWORD *)&v95.eM22 = 0;
        v95.eDy = (float)v13;
        v95.eM12 = (float)((float)v13 * -1.0) / (float)v12;
        v95.eM21 = (float)v12 / (float)v13;
        if ( v57 == 1.0 && *((float *)this + 58) == 1.0 )
        {
          v52 = v13;
          v53 = v12;
          goto LABEL_107;
        }
        v56 = (float)v13 / *((float *)this + 58);
        v54 = (float)v12 / v57;
      }
      v52 = (int)v56;
    }
    v53 = (int)v54;
    goto LABEL_107;
  }
  v59 = *((float *)this + 57);
  if ( v59 == 1.0 && *((float *)this + 58) == 1.0 )
  {
    v52 = v12;
    v53 = v13;
  }
  else
  {
    v52 = (int)(float)((float)v12 / v59);
    v53 = (int)(float)((float)v13 / *((float *)this + 58));
  }
LABEL_117:
  if ( v52 > *((_DWORD *)this + 52) )
  {
    if ( (unsigned int)dword_1808B7628 > 3 )
    {
      v80 = *((_DWORD *)this + 52);
      LODWORD(v90) = *((_DWORD *)this + 20);
      *(_QWORD *)&Rect.right = 0;
      v106 = &v80;
      v82 = v52;
      p_Rect = (struct tagRECT *)&v82;
      v102 = &v90;
      Rect.top = 3;
      v98.Ptr = (ULONGLONG)off_1808B7630;
      v107 = 4;
      v105 = 4;
      v103 = 4;
      Rect.left = 184549376;
      v98.Size = *(unsigned __int16 *)off_1808B7630;
      v99 = (char *)word_180864F62;
      v98.Reserved = 2;
      v100 = 78;
      v101 = 1;
      v83 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(qword_1808B7648, (PCEVENT_DESCRIPTOR)&Rect, 0, 0, 5u, &v98);
    }
    v52 = *((_DWORD *)this + 52);
  }
  if ( v53 > *((_DWORD *)this + 53) )
  {
    if ( (unsigned int)dword_1808B7628 > 3 )
    {
      v80 = *((_DWORD *)this + 53);
      LODWORD(v90) = *((_DWORD *)this + 20);
      *(_QWORD *)&Rect.right = 0;
      v106 = &v80;
      v82 = v53;
      p_Rect = (struct tagRECT *)&v82;
      v102 = &v90;
      Rect.top = 3;
      v98.Ptr = (ULONGLONG)off_1808B7630;
      v107 = 4;
      v105 = 4;
      v103 = 4;
      Rect.left = 184549376;
      v98.Size = *(unsigned __int16 *)off_1808B7630;
      v99 = (char *)&dword_180864FBC;
      v98.Reserved = 2;
      v100 = 81;
      v101 = 1;
      v83 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(qword_1808B7648, (PCEVENT_DESCRIPTOR)&Rect, 0, 0, 5u, &v98);
    }
    v53 = *((_DWORD *)this + 53);
  }
  if ( (unsigned int)dword_1808B7628 > 5 )
  {
    v80 = *((_DWORD *)this + 53);
    v82 = *((_DWORD *)this + 52);
    v86 = *((_DWORD *)this + 20);
    v118 = (struct tagRECT *)&v80;
    v116 = (int *)&v82;
    v114 = (unsigned int *)&v90;
    p_yoriginDest = &v83;
    v110 = &v89;
    v108 = &v88;
    v106 = (unsigned int *)&v81;
    p_Rect = (struct tagRECT *)&v85;
    v102 = &v86;
    *(_DWORD *)&v92.Level = 5;
    v98.Ptr = (ULONGLONG)off_1808B7630;
    v81 = yoriginDest;
    v92.Keyword = 0;
    LODWORD(v90) = v53;
    v83 = v52;
    v89 = v13;
    v88 = v12;
    v85 = v42;
    v119 = 4;
    v117 = 4;
    v115 = 4;
    v113 = 4;
    v111 = 4;
    v109 = 4;
    v107 = 4;
    v105 = 4;
    v103 = 4;
    *(_DWORD *)&v92.Id = 184549376;
    v98.Size = *(unsigned __int16 *)off_1808B7630;
    v99 = byte_180865019;
    v98.Reserved = 2;
    v100 = 131;
    v101 = 1;
    Rect.left = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(qword_1808B7648, &v92, 0, 0, 0xBu, &v98);
  }
  SetLastError(0);
  v81 = AlphaBlend(
          *((HDC *)a2 + 1),
          v42,
          yoriginDest,
          v12,
          v13,
          *(HDC *)(*((_QWORD *)a2 + 4) + 80LL),
          0,
          0,
          v52,
          v53,
          *(BLENDFUNCTION *)((char *)a2 + 24));
  v60 = v81;
  if ( !v81 )
  {
    v61 = *((_QWORD *)this + 47);
    if ( v61 )
    {
      v62 = *((_QWORD *)this + 18);
      v90 = *(void (**)(__int64, const wchar_t *, ...))(*(_QWORD *)v61 + 240LL);
      Rect.left = *(_DWORD *)(v62 + 28);
      v86 = *(_DWORD *)(v62 + 24);
      v85 = *((_DWORD *)a2 + 5);
      v80 = *((_DWORD *)a2 + 4);
      v82 = *((_DWORD *)this + 20);
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LODWORD(ftn) = v85;
      LODWORD(hSrca) = v80;
      LODWORD(wSrca) = v13;
      LODWORD(yoriginSrca) = v12;
      LODWORD(xoriginSrca) = yoriginDest;
      LODWORD(UserDataa) = v84;
      UserDataCounta[0] = v82;
      v90(
        v61,
        L"RemoteAppPresenter AlphaBlend failed (windowId=0x%x, destX=%d, destY=%d, destWidth=%l, destHeight=%l, sourceX=%l"
         ", sourceY=%l, sourceWidth=%l, sourceHeight=%l, textureWidth=%u, textureHeight=%u)",
        (unsigned int)LastError,
        0,
        *(_QWORD *)UserDataCounta,
        UserDataa,
        xoriginSrca,
        yoriginSrca,
        wSrca,
        hSrca,
        ftn,
        v52,
        v53,
        v86,
        Rect.left);
      v60 = v81;
    }
    else
    {
      v60 = 0;
    }
  }
  if ( *((_DWORD *)this + 56) )
  {
    SetWorldTransform(*((HDC *)a2 + 1), &xf);
    SetGraphicsMode(*((HDC *)a2 + 1), 1);
  }
  if ( !v60 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v64 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        &WPP_8078f27b9915346d8ab3175536312c32_Traceguids,
        v64,
        -2147467259);
    }
    v6 = -2147467259;
LABEL_141:
    v4 = *(HDC *)&v91.Id;
    goto LABEL_142;
  }
  v4 = *(HDC *)&v91.Id;
LABEL_148:
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( GetVersionExW(&VersionInformation) && VersionInformation.dwBuildNumber >= 0x3FDE )
    *((_DWORD *)a2 + 7) |= 0x20u;
  if ( (unsigned int)dword_1808B7628 > 5 )
  {
    Rect.left = *((_DWORD *)this + 58);
    v86 = *((_DWORD *)this + 57);
    v85 = *((_DWORD *)this + 53);
    v80 = *((_DWORD *)this + 52);
    v82 = *((_DWORD *)a2 + 1);
    LODWORD(v90) = *(_DWORD *)a2;
    v83 = *((_DWORD *)a2 + 5);
    v89 = *((_DWORD *)a2 + 4);
    v88 = *((_DWORD *)this + 20);
    v118 = &Rect;
    v116 = &v86;
    v114 = &v85;
    p_yoriginDest = &v80;
    v110 = &v82;
    v108 = (int *)&v90;
    v106 = &v83;
    p_Rect = (struct tagRECT *)&v89;
    v102 = &v88;
    *(_DWORD *)&v92.Level = 517;
    v98.Ptr = (ULONGLONG)off_1808B7630;
    v92.Keyword = 0;
    v119 = 4;
    v117 = 4;
    v115 = 4;
    v113 = 4;
    v111 = 4;
    v109 = 4;
    v107 = 4;
    v105 = 4;
    v103 = 4;
    *(_DWORD *)&v92.Id = 184549376;
    v98.Size = *(unsigned __int16 *)off_1808B7630;
    v99 = byte_180864E99;
    v98.Reserved = 2;
    v100 = 140;
    v101 = 1;
    v81 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(qword_1808B7648, &v92, 0, 0, 0xBu, &v98);
  }
  v6 = 0;
LABEL_154:
  if ( v4 )
    ReleaseDC(*((HWND *)this + 25), v4);
  return v6;
}

```

## disassembly

```asm
0x1800ae340  mov     r11, rsp
0x1800ae343  push    rbp
0x1800ae344  push    rdi
0x1800ae345  push    r12
0x1800ae347  push    r14
0x1800ae349  lea     rbp, [r11-278h]
0x1800ae350  sub     rsp, 358h
0x1800ae357  mov     rax, cs:__security_cookie
0x1800ae35e  xor     rax, rsp
0x1800ae361  mov     [rbp+270h+var_50], rax
0x1800ae368  mov     [r11+18h], rbx
0x1800ae36c  mov     r14, rcx
0x1800ae36f  mov     [r11-28h], rsi
0x1800ae373  lea     rcx, [rbp+270h+VersionInformation]; void *
0x1800ae377  mov     [r11-30h], r13
0x1800ae37b  mov     rbx, rdx
0x1800ae37e  mov     [r11-38h], r15
0x1800ae382  xor     edx, edx; Val
0x1800ae384  mov     r8d, 114h; Size
0x1800ae38a  movaps  xmmword ptr [r11-48h], xmm6
0x1800ae38f  mov     qword ptr [rbp+270h+var_2C0.Id], 0
0x1800ae397  xor     r12d, r12d
0x1800ae39a  call    memset_0
0x1800ae39f  lea     rsi, _TraceLoggingMetadataEnd
0x1800ae3a6  mov     edi, 1
0x1800ae3ab  lea     r15, _TraceLoggingMetadata
0x1800ae3b2  test    rbx, rbx
0x1800ae3b5  jnz     short loc_1800AE410
0x1800ae3b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae3be  lea     rax, WPP_GLOBAL_Control
0x1800ae3c5  cmp     rcx, rax
0x1800ae3c8  jz      short loc_1800AE406
0x1800ae3ca  test    byte ptr [rcx+1Ch], 8
0x1800ae3ce  jz      short loc_1800AE406
0x1800ae3d0  cmp     byte ptr [rcx+19h], 2
0x1800ae3d4  jb      short loc_1800AE406
0x1800ae3d6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ae3db  lea     rcx, aPulwdata; "pUlwData"
0x1800ae3e2  mov     edx, 2Dh ; '-'
0x1800ae3e7  mov     qword ptr [rsp+370h+UserDataCount], rcx
0x1800ae3ec  lea     r8, WPP_8078f27b9915346d8ab3175536312c32_Traceguids
0x1800ae3f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae3fa  mov     r9d, eax
0x1800ae3fd  mov     rcx, [rcx+10h]
0x1800ae401  call    WPP_SF_Ds
0x1800ae406  mov     edi, 80004003h
0x1800ae40b  jmp     loc_1800AF4CD
0x1800ae410  cmp     [r14+90h], r12
0x1800ae417  jnz     loc_1800AE49F
0x1800ae41d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae424  lea     rax, WPP_GLOBAL_Control
0x1800ae42b  cmp     rcx, rax
0x1800ae42e  jz      short loc_1800AE468
0x1800ae430  test    byte ptr [rcx+1Ch], 40h
0x1800ae434  jz      short loc_1800AE468
0x1800ae436  cmp     byte ptr [rcx+19h], 4
0x1800ae43a  jb      short loc_1800AE468
0x1800ae43c  mov     edi, [r14+50h]
0x1800ae440  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ae445  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae44c  lea     r8, WPP_8078f27b9915346d8ab3175536312c32_Traceguids
0x1800ae453  mov     edx, 2Eh ; '.'
0x1800ae458  mov     [rsp+370h+UserDataCount], edi
0x1800ae45c  mov     r9d, eax
0x1800ae45f  mov     rcx, [rcx+10h]
0x1800ae463  call    WPP_SF_Dd
0x1800ae468  mov     rcx, [r14+178h]
0x1800ae46f  mov     edi, 8007139Fh
0x1800ae474  test    rcx, rcx
0x1800ae477  jz      loc_1800AF4CD
0x1800ae47d  mov     rax, [rcx]
0x1800ae480  lea     rdx, aRemoteappprese_1; "RemoteAppPresenter ignoring present for"...
0x1800ae487  mov     r9d, [r14+50h]
0x1800ae48b  xor     r8d, r8d
0x1800ae48e  mov     rax, [rax+0E0h]
0x1800ae495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae49a  jmp     loc_1800AF4CD
0x1800ae49f  mov     eax, cs:dword_1808B7628
0x1800ae4a5  cmp     eax, 5
0x1800ae4a8  jbe     loc_1800AE556
0x1800ae4ae  mov     eax, [r14+50h]
0x1800ae4b2  lea     rdx, [rbp+270h+EventDescriptor]; EventDescriptor
0x1800ae4b6  mov     [rbp+270h+var_2EC], eax
0x1800ae4b9  xor     r9d, r9d; RelatedActivityId
0x1800ae4bc  lea     rax, [rbp+270h+var_2EC]
0x1800ae4c0  mov     [rbp+270h+var_58], 4
0x1800ae4cb  mov     [rbp+270h+var_60], rax
0x1800ae4d2  xor     r8d, r8d; ActivityId
0x1800ae4d5  movzx   eax, cs:word_180865131
0x1800ae4dc  mov     dword ptr [rbp+270h+EventDescriptor.Level], eax
0x1800ae4df  mov     rax, cs:off_1808B7630
0x1800ae4e6  mov     [rbp+270h+var_80.Ptr], rax
0x1800ae4ed  mov     dword ptr [rbp+270h+EventDescriptor.Id], 0B000000h
0x1800ae4f4  mov     [rbp+270h+EventDescriptor.Keyword], r12
0x1800ae4f8  movzx   eax, word ptr [rax]
0x1800ae4fb  mov     [rbp+270h+var_80.Size], eax
0x1800ae501  lea     rax, byte_18086513B
0x1800ae508  mov     qword ptr [rbp+270h+var_70], rax
0x1800ae50f  mov     rax, rsi
0x1800ae512  sub     eax, r15d
0x1800ae515  mov     dword ptr [rbp+270h+var_80.0Ch], 2
0x1800ae51f  mov     dword ptr [rbp+270h+var_70+8], 1Dh
0x1800ae529  mov     dword ptr [rbp+270h+var_70+0Ch], edi
0x1800ae52f  mov     [rbp+270h+var_2E0], eax
0x1800ae532  mov     eax, [rbp+270h+var_2E0]
0x1800ae535  mov     rcx, cs:qword_1808B7648; RegHandle
0x1800ae53c  lea     rax, [rbp+270h+var_80]
0x1800ae543  mov     [rsp+370h+UserData], rax; UserData
0x1800ae548  mov     [rsp+370h+UserDataCount], 3; UserDataCount
0x1800ae550  call    cs:__imp_EventWriteTransfer
0x1800ae556  mov     rcx, [r14+0C8h]; hWnd
0x1800ae55d  lea     rdx, [rbp+270h+Rect]; lpRect
0x1800ae561  xorps   xmm0, xmm0
0x1800ae564  movups  xmmword ptr [rbp+270h+Rect.left], xmm0
0x1800ae568  call    cs:__imp_GetWindowRect
0x1800ae56e  test    eax, eax
0x1800ae570  jnz     short loc_1800AE5C7
0x1800ae572  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae579  lea     rax, WPP_GLOBAL_Control
0x1800ae580  cmp     rcx, rax
0x1800ae583  jz      short loc_1800AE5BD
0x1800ae585  test    byte ptr [rcx+1Ch], 8
0x1800ae589  jz      short loc_1800AE5BD
0x1800ae58b  cmp     byte ptr [rcx+19h], 2
0x1800ae58f  jb      short loc_1800AE5BD
0x1800ae591  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800ae596  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae59d  lea     r8, WPP_8078f27b9915346d8ab3175536312c32_Traceguids
0x1800ae5a4  mov     edx, 2Fh ; '/'
0x1800ae5a9  mov     [rsp+370h+UserDataCount], 8007139Fh
0x1800ae5b1  mov     r9d, eax
0x1800ae5b4  mov     rcx, [rcx+10h]
0x1800ae5b8  call    WPP_SF_Dd
0x1800ae5bd  mov     edi, 8007139Fh
0x1800ae5c2  jmp     loc_1800AF4CD
0x1800ae5c7  mov     r15d, [rbp+270h+Rect.right]
0x1800ae5cb  sub     r15d, [rbp+270h+Rect.left]
0x1800ae5cf  mov     r13d, [rbp+270h+Rect.bottom]
0x1800ae5d3  sub     r13d, [rbp+270h+Rect.top]
0x1800ae5d7  mov     dword ptr [rbx+1Ch], 2
0x1800ae5de  mov     rcx, [rbx+20h]
0x1800ae5e2  mov     dword ptr [rbp+270h+var_2C0.Id], r15d
0x1800ae5e6  mov     dword ptr [rbp+270h+var_2C0.Level], r13d
0x1800ae5ea  cmp     [r14+90h], rcx
0x1800ae5f1  jz      short loc_1800AE630
0x1800ae5f3  test    rcx, rcx
0x1800ae5f6  jz      short loc_1800AE61C
0x1800ae5f8  mov     [rbx+20h], r12
0x1800ae5fc  mov     eax, 0FFFFFFFFh
0x1800ae601  lock xadd [rcx+10h], eax
0x1800ae606  cmp     eax, edi
0x1800ae608  jnz     short loc_1800AE61C
0x1800ae60a  lock inc dword ptr [rcx+10h]
0x1800ae60e  mov     rax, [rcx]
0x1800ae611  mov     edx, edi
0x1800ae613  mov     rax, [rax+78h]
0x1800ae617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae61c  mov     rax, [r14+90h]
0x1800ae623  mov     [rbx+20h], rax
0x1800ae627  test    rax, rax
0x1800ae62a  jz      short loc_1800AE630
0x1800ae62c  lock inc dword ptr [rax+10h]
0x1800ae630  xor     eax, eax
0x1800ae632  mov     dword ptr [rbx+18h], 1FF0000h
0x1800ae639  mov     [rbx+10h], rax
0x1800ae63d  mov     rcx, r14; this
0x1800ae640  mov     rax, qword ptr [rbp+270h+var_2C0.Id]
0x1800ae644  mov     [rbx], rax
0x1800ae647  call    ?IsMarginBlendingRequired@RdpWin32RemoteAppPresenter@@IEBAHXZ; RdpWin32RemoteAppPresenter::IsMarginBlendingRequired(void)
0x1800ae64c  movss   xmm0, dword ptr [r14+0E4h]
0x1800ae655  mov     edi, eax
0x1800ae657  movss   xmm6, cs:__real@3f800000
0x1800ae65f  ucomiss xmm0, xmm6
0x1800ae662  jp      loc_1800AE76D
0x1800ae668  jnz     loc_1800AE76D
0x1800ae66e  movss   xmm0, dword ptr [r14+0E8h]
0x1800ae677  ucomiss xmm0, xmm6
0x1800ae67a  jp      loc_1800AE76D
0x1800ae680  jnz     loc_1800AE76D
0x1800ae686  test    eax, eax
0x1800ae688  jnz     loc_1800AE76D
0x1800ae68e  cmp     [r14+0E0h], r12d
0x1800ae695  jnz     loc_1800AE76D
0x1800ae69b  mov     eax, cs:dword_1808B7628
0x1800ae6a1  cmp     eax, 5
0x1800ae6a4  jbe     loc_1800AE75C
0x1800ae6aa  mov     eax, [r14+50h]
0x1800ae6ae  lea     rcx, _TraceLoggingMetadata
0x1800ae6b5  mov     [rbp+270h+var_2EC], eax
0x1800ae6b8  lea     rdx, [rbp+270h+EventDescriptor]; EventDescriptor
0x1800ae6bc  lea     rax, [rbp+270h+var_2EC]
0x1800ae6c0  mov     [rbp+270h+var_58], 4
0x1800ae6cb  mov     [rbp+270h+var_60], rax
0x1800ae6d2  xor     r9d, r9d; RelatedActivityId
0x1800ae6d5  movzx   eax, cs:word_18086515A
0x1800ae6dc  xor     r8d, r8d; ActivityId
0x1800ae6df  mov     dword ptr [rbp+270h+EventDescriptor.Level], eax
0x1800ae6e2  mov     rax, cs:off_1808B7630
0x1800ae6e9  mov     [rbp+270h+var_80.Ptr], rax
0x1800ae6f0  mov     dword ptr [rbp+270h+EventDescriptor.Id], 0B000000h
0x1800ae6f7  mov     [rbp+270h+EventDescriptor.Keyword], r12
0x1800ae6fb  movzx   eax, word ptr [rax]
0x1800ae6fe  mov     [rbp+270h+var_80.Size], eax
0x1800ae704  lea     rax, dword_180865164
0x1800ae70b  mov     qword ptr [rbp+270h+var_70], rax
0x1800ae712  mov     rax, rsi
0x1800ae715  sub     eax, ecx
0x1800ae717  mov     dword ptr [rbp+270h+var_80.0Ch], 2
0x1800ae721  mov     dword ptr [rbp+270h+var_70+8], 2Fh ; '/'
0x1800ae72b  mov     dword ptr [rbp+270h+var_70+0Ch], 1
0x1800ae735  mov     [rbp+270h+var_2E0], eax
0x1800ae738  mov     eax, [rbp+270h+var_2E0]
0x1800ae73b  mov     rcx, cs:qword_1808B7648; RegHandle
0x1800ae742  lea     rax, [rbp+270h+var_80]
0x1800ae749  mov     [rsp+370h+UserData], rax; UserData
0x1800ae74e  mov     [rsp+370h+UserDataCount], 3; UserDataCount
0x1800ae756  call    cs:__imp_EventWriteTransfer
0x1800ae75c  mov     rax, [rbx+20h]
0x1800ae760  mov     rcx, [rax+50h]
0x1800ae764  mov     [rbx+8], rcx
0x1800ae768  jmp     loc_1800AF5F2
0x1800ae76d  xor     eax, eax
0x1800ae76f  xor     edx, edx
0x1800ae771  xorps   xmm0, xmm0
0x1800ae774  mov     [rbp+270h+var_60+4], rax
0x1800ae77b  mov     qword ptr [rbp+270h+xf.eDx], rax
0x1800ae77f  xorps   xmm1, xmm1
0x1800ae782  mov     qword ptr [rbp+270h+var_280.eDx], rax
0x1800ae786  mov     eax, cs:dword_1808B7628
0x1800ae78c  mov     dword ptr [rbp+270h+var_80.Ptr], edx
0x1800ae792  mov     qword ptr [rbp+270h+EventDescriptor.Id], rdx
0x1800ae796  movups  xmmword ptr [rbp+270h+var_80.Ptr+4], xmm0
0x1800ae79d  movups  [rbp+270h+var_70+4], xmm0
0x1800ae7a4  movups  xmmword ptr [rbp+270h+xf.eM11], xmm0
0x1800ae7a8  movups  xmmword ptr [rbp+270h+var_280.eM11], xmm1
0x1800ae7ac  cmp     eax, 5
0x1800ae7af  jbe     loc_1800AE940
0x1800ae7b5  mov     eax, [r14+0F8h]
0x1800ae7bc  mov     ecx, [r14+0E0h]
0x1800ae7c3  test    ecx, ecx
0x1800ae7c5  mov     [rbp+270h+var_2E0], eax
0x1800ae7c8  mov     eax, [r14+0F0h]
0x1800ae7cf  mov     [rbp+270h+yoriginDest], eax
0x1800ae7d2  mov     eax, [r14+0F4h]
0x1800ae7d9  mov     [rbp+270h+var_2D0], eax
0x1800ae7dc  mov     eax, [r14+0ECh]
0x1800ae7e3  mov     [rbp+270h+var_2CC], eax
0x1800ae7e6  mov     eax, edx
0x1800ae7e8  setnz   al
0x1800ae7eb  mov     [rbp+270h+var_2EC], ecx
0x1800ae7ee  mov     [rbp+270h+var_2E4], eax
0x1800ae7f1  lea     rcx, _TraceLoggingMetadata
0x1800ae7f8  mov     eax, [r14+50h]
0x1800ae7fc  xor     r9d, r9d; RelatedActivityId
0x1800ae7ff  mov     [rbp+270h+var_2E8], eax
0x1800ae802  xor     r8d, r8d; ActivityId
0x1800ae805  mov     [rbp+270h+var_2C0.Keyword], rdx
0x1800ae809  lea     rax, [rbp+270h+var_2EC]
0x1800ae80d  mov     [rbp+270h+var_A0], rax
0x1800ae814  lea     rdx, [rbp+270h+var_2C0]; EventDescriptor
0x1800ae818  mov     dword ptr [rbp+270h+var_2C8], edi
0x1800ae81b  lea     rax, [rbp+270h+var_2E0]
0x1800ae81f  mov     [rbp+270h+var_B0], rax
0x1800ae826  lea     rax, [rbp+270h+yoriginDest]
0x1800ae82a  mov     [rbp+270h+var_C0], rax
0x1800ae831  lea     rax, [rbp+270h+var_2D0]
0x1800ae835  mov     [rbp+270h+var_D0], rax
0x1800ae83c  lea     rax, [rbp+270h+var_2CC]
0x1800ae840  mov     [rbp+270h+var_E0], rax
0x1800ae847  lea     rax, [rbp+270h+var_2E4]
0x1800ae84b  mov     [rbp+270h+var_F0], rax
0x1800ae852  lea     rax, [rbp+270h+var_2C8]
0x1800ae856  mov     [rbp+270h+var_100], rax
0x1800ae85d  lea     rax, [rbp+270h+var_2E8]
0x1800ae861  mov     [rbp+270h+var_110], rax
0x1800ae868  movzx   eax, cs:word_18086509E
0x1800ae86f  mov     dword ptr [rbp+270h+var_2C0.Level], eax
0x1800ae872  mov     rax, cs:off_1808B7630
0x1800ae879  mov     [rbp+270h+var_130.Ptr], rax
0x1800ae880  mov     [rbp+270h+var_98], 4
0x1800ae88b  mov     [rbp+270h+var_A8], 4
0x1800ae896  mov     [rbp+270h+var_B8], 4
0x1800ae8a1  mov     [rbp+270h+var_C8], 4
0x1800ae8ac  mov     [rbp+270h+var_D8], 4
0x1800ae8b7  mov     [rbp+270h+var_E8], 4
0x1800ae8c2  mov     [rbp+270h+var_F8], 4
0x1800ae8cd  mov     [rbp+270h+var_108], 4
0x1800ae8d8  mov     dword ptr [rbp+270h+var_2C0.Id], 0B000000h
0x1800ae8df  movzx   eax, word ptr [rax]
0x1800ae8e2  mov     [rbp+270h+var_130.Size], eax
0x1800ae8e8  lea     rax, unk_1808650A8
0x1800ae8ef  mov     [rbp+270h+var_120], rax
0x1800ae8f6  mov     rax, rsi
0x1800ae8f9  sub     eax, ecx
0x1800ae8fb  mov     dword ptr [rbp+270h+var_130.0Ch], 2
0x1800ae905  mov     [rbp+270h+var_118], 87h
0x1800ae90f  mov     [rbp+270h+var_114], 1
0x1800ae919  mov     [rbp+270h+var_2F0], eax
0x1800ae91c  mov     eax, [rbp+270h+var_2F0]
0x1800ae91f  mov     rcx, cs:qword_1808B7648; RegHandle
  ... truncated ...
```
