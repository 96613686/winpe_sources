# RdpWin32RemoteAppPresenter::PresentWithSharedMemoryTexture(RdpXInterfaceRegion *,RdpXInterfaceRegion *)

- ea: `0x1800af830`
- end: `0x1800b02bf`
- name: `?PresentWithSharedMemoryTexture@RdpWin32RemoteAppPresenter@@UEAA?AW4_XResult32@@PEAURdpXInterfaceRegion@@0@Z`
- size: `2703`
- prototype: `__int64 __fastcall(__int64, struct RdpXInterfaceRegion *, struct RdpXInterfaceRegion *)`
- caller_count: `0`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800186a0`
- `0x1800186d0`
- `0x18001cdc0`
- `0x18001cde4`
- `0x18001f5d0`
- `0x180022978`
- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x180072548`
- `0x180082c10`
- `0x1800ae340`
- `0x1800af830`
- `0x1800e9b1c`
- `0x1800f7d90`
- `0x180240c24`
- `0x180270c44`
- `0x1802711cc`
- `0x1802fe378`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800afd61`
- `KERNEL32!SetLastError` at `0x1800aff0d`
- `KERNEL32!SetLastError` at `0x1800afd61`
- `KERNEL32!SetLastError` at `0x1800aff0d`
- `KERNEL32!GetLastError` at `0x1800afdda`
- `KERNEL32!GetLastError` at `0x1800afe0d`
- `KERNEL32!GetLastError` at `0x1800aff67`
- `KERNEL32!GetLastError` at `0x1800affc0`
- `KERNEL32!GetLastError` at `0x1800afdda`
- `KERNEL32!GetLastError` at `0x1800afe0d`
- `KERNEL32!GetLastError` at `0x1800aff67`
- `KERNEL32!GetLastError` at `0x1800affc0`
- `GDI32!DeleteObject` at `0x1800affb1`
- `GDI32!DeleteObject` at `0x1800b0282`
- `GDI32!DeleteObject` at `0x1800affb1`
- `GDI32!DeleteObject` at `0x1800b0282`
- `GDI32!DeleteDC` at `0x1800b0275`
- `GDI32!DeleteDC` at `0x1800b0275`
- `GDI32!SelectObject` at `0x1800b026b`
- `GDI32!SelectObject` at `0x1800b026b`
- `USER32!IsIconic` at `0x1800af954`
- `USER32!IsIconic` at `0x1800af954`
- `USER32!RedrawWindow` at `0x1800aff25`
- `USER32!RedrawWindow` at `0x1800aff25`
- `USER32!UpdateLayeredWindow` at `0x1800afda1`
- `USER32!UpdateLayeredWindow` at `0x1800afda1`

## string_xrefs

- `0x1800b01d3`: `PinCompositionTargetToWindow failed`
- `0x1800afd4b`: `GenerateUpdateLayeredWindowData failed`
- `0x1800afcf1`: `CopyRegion(DEFAULT) failed`
- `0x1800afc23`: `CopyRegion(REMOVE_ALPHA) failed`
- `0x1800afefb`: `CreateGDIRegion failed`
- `0x1800afdf6`: `RemoteAppPresenter UpdateLayeredWindow failed (windowId=0x%x, localWindowId=0x%x)`

## pseudocode

```c
__int64 __fastcall RdpWin32RemoteAppPresenter::PresentWithSharedMemoryTexture(
        __int64 a1,
        struct RdpXInterfaceRegion *a2,
        struct RdpXInterfaceRegion *a3)
{
  CTSCriticalSection *v3; // rbx
  signed int UpdateLayeredWindowData; // edi
  int v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v12; // ebx
  unsigned int v13; // eax
  int v14; // ebx
  unsigned int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  unsigned int v18; // eax
  HKEY v19; // rax
  unsigned int v20; // eax
  int v21; // edx
  const char *v22; // rcx
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rbx
  __int64 v28; // rdi
  int v29; // r13d
  signed int LastError; // eax
  unsigned int v31; // eax
  __int64 v32; // rdx
  int v33; // ebx
  unsigned int v34; // eax
  HRGN v35; // rbx
  BOOL v36; // r13d
  __int64 v37; // r13
  signed int v38; // eax
  int v39; // ebx
  unsigned int v40; // eax
  __int64 *v41; // rbx
  __int64 v42; // rdx
  __int64 v43; // rcx
  HRGN v44; // rdi
  __int64 v45; // rdi
  unsigned int v46; // eax
  int v47; // ebx
  unsigned int v48; // eax
  CTSCriticalSection *v49; // rbx
  HGDIOBJ v50; // rax
  HDC v51; // rcx
  HDC hdcSrc; // [rsp+20h] [rbp-79h]
  HDC hdcSrca; // [rsp+20h] [rbp-79h]
  POINT *pptSrc; // [rsp+28h] [rbp-71h]
  HRGN v56; // [rsp+50h] [rbp-49h] BYREF
  BOOL v57; // [rsp+58h] [rbp-41h]
  SIZE psize; // [rsp+60h] [rbp-39h] BYREF
  HDC hdc[2]; // [rsp+68h] [rbp-31h] BYREF
  BLENDFUNCTION pblend[2]; // [rsp+78h] [rbp-21h] BYREF
  __int64 v61; // [rsp+80h] [rbp-19h] BYREF
  HGDIOBJ h[2]; // [rsp+88h] [rbp-11h]
  __int64 v63; // [rsp+98h] [rbp-1h]
  CTSCriticalSection *v64; // [rsp+A0h] [rbp+7h]
  void (*v65)(__int64, const wchar_t *, ...); // [rsp+A8h] [rbp+Fh] BYREF
  int v66; // [rsp+B0h] [rbp+17h]
  int v67; // [rsp+B4h] [rbp+1Bh]

  v3 = (CTSCriticalSection *)(a1 + 64);
  v64 = (CTSCriticalSection *)(a1 + 64);
  UpdateLayeredWindowData = 0;
  psize = 0;
  *(_QWORD *)&pblend[0].BlendOp = 0;
  v61 = 0;
  *(_OWORD *)hdc = 0;
  *(_OWORD *)h = 0;
  CTSCriticalSection::Lock((CTSCriticalSection *)(a1 + 64));
  if ( a2 )
  {
    if ( (*(unsigned int (__fastcall **)(struct RdpXInterfaceRegion *))(*(_QWORD *)a2 + 120LL))(a2) )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_DWORD)WPP_GLOBAL_Control[7] & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          &WPP_8078f27b9915346d8ab3175536312c32_Traceguids,
          CurrentThreadActivityIdPrefix);
      }
      goto LABEL_8;
    }
  }
  else if ( *(_DWORD *)(a1 + 184) )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
      goto LABEL_8;
    }
    v8 = *(_DWORD *)(a1 + 80);
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 24;
LABEL_7:
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_8078f27b9915346d8ab3175536312c32_Traceguids, v9, v8);
LABEL_8:
    UpdateLayeredWindowData = 1;
    goto LABEL_142;
  }
  if ( IsIconic(*(HWND *)(a1 + 200)) )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
      goto LABEL_8;
    }
    v8 = *(_DWORD *)(a1 + 80);
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 26;
    goto LABEL_7;
  }
  *(_DWORD *)(a1 + 184) = 0;
  if ( !*(_QWORD *)(a1 + 200) )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v12 = *(_DWORD *)(a1 + 80);
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_8078f27b9915346d8ab3175536312c32_Traceguids, v13, v12);
    }
    if ( (unsigned int)dword_1808B7630 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_1808B7630,
        &dword_180865094);
    goto LABEL_8;
  }
  if ( *(_DWORD *)(a1 + 172) || *(_DWORD *)(a1 + 180) )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v39 = *(_DWORD *)(a1 + 80);
      v40 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_8078f27b9915346d8ab3175536312c32_Traceguids, v40, v39);
    }
    if ( *(_DWORD *)(a1 + 176) )
    {
      v41 = (__int64 *)(a1 + 384);
      if ( !*(_QWORD *)(a1 + 384) )
      {
        if ( a2 )
        {
          v42 = *(_QWORD *)(a1 + 360);
          v56 = 0;
          v43 = v42 + 8 + *(int *)(*(_QWORD *)(v42 + 8) + 4LL);
          v44 = (HRGN)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 40LL))(v43);
          if ( !v44 )
          {
            if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
              && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v46 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                29,
                (unsigned int)&WPP_8078f27b9915346d8ab3175536312c32_Traceguids,
                v46,
                (__int64)"spPlatform",
                -2147467259);
            }
            UpdateLayeredWindowData = -2147467259;
            TCntPtr<ITSViewerRecorder>::SafeRelease(&v56);
            goto LABEL_137;
          }
          TCntPtr<ITSViewerRecorder>::SafeRelease(&v56);
          v56 = v44;
          TCntPtr<IPin>::SafeAddRef(&v56);
          v45 = (*(__int64 (__fastcall **)(HRGN))(*(_QWORD *)v44 + 64LL))(v44);
          if ( v45 != *v41 )
          {
            TCntPtr<ITSViewerRecorder>::SafeRelease((void *)(a1 + 384));
            *v41 = v45;
            TCntPtr<IPin>::SafeAddRef(a1 + 384);
          }
          TCntPtr<ITSViewerRecorder>::SafeRelease(&v56);
        }
      }
    }
    if ( *(_DWORD *)(a1 + 172)
      && (UpdateLayeredWindowData = RdpWin32RemoteAppPresenter::PresentSwapChain(
                                      (RdpWin32RemoteAppPresenter *)a1,
                                      a2,
                                      a3),
          UpdateLayeredWindowData < 0) )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control )
        goto LABEL_142;
      if ( ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_138;
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 30;
      v22 = "PresentSwapChain failed in RdpWin32RemoteAppPresenter::Present";
    }
    else
    {
      UpdateLayeredWindowData = RdpWin32RemoteAppPresenter::PinCompositionTargetToWindow((RdpWin32RemoteAppPresenter *)a1);
      if ( UpdateLayeredWindowData >= 0 )
        goto LABEL_142;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control )
        goto LABEL_142;
      if ( ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_138;
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 31;
      v22 = "PinCompositionTargetToWindow failed";
    }
LABEL_136:
    LODWORD(pptSrc) = UpdateLayeredWindowData;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v21,
      (unsigned int)&WPP_8078f27b9915346d8ab3175536312c32_Traceguids,
      v20,
      (__int64)v22,
      pptSrc);
LABEL_137:
    v19 = WPP_GLOBAL_Control;
LABEL_138:
    if ( v19 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v19[7] & 0x40) != 0 && *((_BYTE *)v19 + 25) >= 2u )
    {
      v47 = *(_DWORD *)(a1 + 80);
      v48 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, &WPP_8078f27b9915346d8ab3175536312c32_Traceguids, v48, v47);
    }
    goto LABEL_142;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v14 = *(_DWORD *)(a1 + 80);
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_8078f27b9915346d8ab3175536312c32_Traceguids, v15, v14);
    v3 = (CTSCriticalSection *)(a1 + 64);
  }
  if ( (unsigned int)RdpWin32RemoteAppPresenter::IsWindowLayered((RdpWin32RemoteAppPresenter *)a1)
    && *(_DWORD *)(a1 + 176) )
  {
    v16 = *(_QWORD *)(a1 + 160);
    if ( v16 )
    {
      if ( *(_QWORD *)(a1 + 144) )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 32LL))(v16);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 160) + 40LL))(*(_QWORD *)(a1 + 160));
        if ( a2 )
        {
          v17 = *(_QWORD *)(a1 + 144);
          v65 = 0;
          v66 = *(_DWORD *)(v17 + 24);
          v67 = *(_DWORD *)(v17 + 28);
          v18 = (*(__int64 (__fastcall **)(struct RdpXInterfaceRegion *, void (**)(__int64, const wchar_t *, ...)))(*(_QWORD *)a2 + 56LL))(
                  a2,
                  &v65);
          UpdateLayeredWindowData = MapXResultToHR(v18);
          if ( UpdateLayeredWindowData < 0 )
          {
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control )
              goto LABEL_142;
            if ( ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_138;
            v20 = RdpWppGetCurrentThreadActivityIdPrefix();
            v21 = 33;
            v22 = "IntersectRect DirtyRegion with texureRect failed";
            goto LABEL_136;
          }
          if ( a3 )
          {
            v23 = (*(__int64 (__fastcall **)(struct RdpXInterfaceRegion *, struct RdpXInterfaceRegion *))(*(_QWORD *)a3 + 64LL))(
                    a3,
                    a2);
            UpdateLayeredWindowData = MapXResultToHR(v23);
            if ( UpdateLayeredWindowData < 0 )
            {
              v19 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control )
                goto LABEL_142;
              if ( ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_138;
              v20 = RdpWppGetCurrentThreadActivityIdPrefix();
              v21 = 34;
              v22 = "IntersectRegion OpaqueRegion with DirtyRegion failed";
              goto LABEL_136;
            }
            HIDWORD(pptSrc) = HIDWORD(a3);
            v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 160) + 64LL))(
                    *(_QWORD *)(a1 + 160),
                    *(_QWORD *)(a1 + 144),
                    1);
            UpdateLayeredWindowData = MapXResultToHR(v24);
            if ( UpdateLayeredWindowData < 0 )
            {
              v19 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control )
                goto LABEL_142;
              if ( ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_138;
              v20 = RdpWppGetCurrentThreadActivityIdPrefix();
              v21 = 35;
              v22 = "CopyRegion(REMOVE_ALPHA) failed";
              goto LABEL_136;
            }
            v25 = (*(__int64 (__fastcall **)(struct RdpXInterfaceRegion *, struct RdpXInterfaceRegion *))(*(_QWORD *)a2 + 80LL))(
                    a2,
                    a3);
            UpdateLayeredWindowData = MapXResultToHR(v25);
            if ( UpdateLayeredWindowData < 0 )
            {
              v19 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control )
                goto LABEL_142;
              if ( ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                goto LABEL_138;
              v20 = RdpWppGetCurrentThreadActivityIdPrefix();
              v21 = 36;
              v22 = "Subtract opaque region from DirtyRegion failed";
              goto LABEL_136;
            }
          }
          v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, struct RdpXInterfaceRegion *))(**(_QWORD **)(a1 + 160) + 64LL))(
                  *(_QWORD *)(a1 + 160),
                  *(_QWORD *)(a1 + 144),
                  0,
                  0,
                  0,
                  a2);
          UpdateLayeredWindowData = MapXResultToHR(v26);
          if ( UpdateLayeredWindowData < 0 )
          {
            v19 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control )
              goto LABEL_142;
            if ( ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              goto LABEL_138;
            v20 = RdpWppGetCurrentThreadActivityIdPrefix();
            v21 = 37;
            v22 = "CopyRegion(DEFAULT) failed";
            goto LABEL_136;
          }
        }
      }
    }
    UpdateLayeredWindowData = RdpWin32RemoteAppPresenter::GenerateUpdateLayeredWindowData(
                                (RdpWin32RemoteAppPresenter *)a1,
                                (struct tagUPDATE_LAYERED_WINDOW_DATA *)&psize);
    if ( UpdateLayeredWindowData == -2147019873 )
    {
      UpdateLayeredWindowData = 0;
      goto LABEL_142;
    }
    if ( UpdateLayeredWindowData < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control )
        goto LABEL_142;
      if ( ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_138;
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 38;
      v22 = "GenerateUpdateLayeredWindowData failed";
      goto LABEL_136;
    }
    CTSCriticalSection::UnLock(v3);
    SetLastError(0);
    if ( UpdateLayeredWindow(
           *(HWND *)(a1 + 200),
           0,
           0,
           &psize,
           hdc[0],
           (POINT *)&hdc[1],
           0,
           pblend,
           *(_DWORD *)&pblend[1]) )
    {
      goto LABEL_142;
    }
    v27 = *(_QWORD *)(a1 + 376);
    if ( v27 )
    {
      v28 = *(_QWORD *)(a1 + 200);
      v29 = *(_DWORD *)(a1 + 80);
      v56 = *(HRGN *)(*(_QWORD *)v27 + 240LL);
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LODWORD(hdcSrca) = v29;
      ((void (*)(__int64, const wchar_t *, ...))v56)(
        v27,
        L"RemoteAppPresenter UpdateLayeredWindow failed (windowId=0x%x, localWindowId=0x%x)",
        (unsigned int)LastError,
        0,
        hdcSrca,
        v28);
    }
    UpdateLayeredWindowData = GetLastError();
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_80:
      if ( UpdateLayeredWindowData > 0 )
        UpdateLayeredWindowData = (unsigned __int16)UpdateLayeredWindowData | 0x80070000;
      if ( UpdateLayeredWindowData >= 0 )
        UpdateLayeredWindowData = -2147467259;
      goto LABEL_138;
    }
    v31 = RdpWppGetCurrentThreadActivityIdPrefix();
    v32 = 39;
LABEL_79:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v32,
      &WPP_8078f27b9915346d8ab3175536312c32_Traceguids,
      v31,
      UpdateLayeredWindowData);
    v19 = WPP_GLOBAL_Control;
    goto LABEL_80;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v33 = *(_DWORD *)(a1 + 80);
    v34 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_8078f27b9915346d8ab3175536312c32_Traceguids, v34, v33);
  }
  v35 = 0;
  v56 = 0;
  if ( a2 )
  {
    UpdateLayeredWindowData = RdpWinRegion::CreateGDIRegion(a2, 0, &v56);
    if ( UpdateLayeredWindowData < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control )
        goto LABEL_142;
      if ( ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_138;
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 41;
      v22 = "CreateGDIRegion failed";
      goto LABEL_136;
    }
    v35 = v56;
  }
  SetLastError(0);
  v57 = RedrawWindow(*(HWND *)(a1 + 200), 0, v35, 1u);
  v36 = v57;
  if ( !v57 )
  {
    v37 = *(_QWORD *)(a1 + 376);
    if ( v37 )
    {
      v65 = *(void (**)(__int64, const wchar_t *, ...))(*(_QWORD *)v37 + 240LL);
      v63 = *(_QWORD *)(a1 + 200);
      LODWORD(v56) = *(_DWORD *)(a1 + 80);
      v38 = GetLastError();
      if ( v38 > 0 )
        v38 = (unsigned __int16)v38 | 0x80070000;
      LODWORD(hdcSrc) = (_DWORD)v56;
      v65(
        v37,
        L"RemoteAppPresenter RedrawWindow failed (windowId=0x%x, localWindowId=0x%x)",
        (unsigned int)v38,
        0,
        hdcSrc,
        v63);
      v36 = v57;
    }
    else
    {
      v36 = 0;
    }
  }
  if ( v35 )
    DeleteObject(v35);
  if ( !v36 )
  {
    UpdateLayeredWindowData = GetLastError();
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_80;
    }
    v31 = RdpWppGetCurrentThreadActivityIdPrefix();
    v32 = 42;
    goto LABEL_79;
  }
LABEL_142:
  v49 = v64;
  if ( (unsigned int)CTSCriticalSection::IsLockedByCurrentThread(v64) )
    CTSCriticalSection::UnLock(v49);
  v50 = h[0];
  if ( h[0] )
  {
    v51 = hdc[0];
    if ( hdc[0] )
    {
      if ( h[1] )
      {
        SelectObject(hdc[0], h[1]);
        v51 = hdc[0];
      }
      DeleteDC(v51);
      v50 = h[0];
    }
    DeleteObject(v50);
  }
  RdpXSPtr<RdpWinGdiTexture2D>::SafeRelease(&v61);
  return MapHRToXResult((unsigned int)UpdateLayeredWindowData);
}

```

## disassembly

```asm
0x1800af830  mov     [rsp-8+arg_18], rbx
0x1800af835  push    rbp
0x1800af836  push    rsi
0x1800af837  push    rdi
0x1800af838  push    r12
0x1800af83a  push    r13
0x1800af83c  push    r14
0x1800af83e  push    r15
0x1800af840  lea     rbp, [rsp-27h]
0x1800af845  sub     rsp, 0C0h
0x1800af84c  mov     rax, cs:__security_cookie
0x1800af853  xor     rax, rsp
0x1800af856  mov     [rbp+57h+var_38], rax
0x1800af85a  lea     rbx, [rcx+40h]
0x1800af85e  xorps   xmm0, xmm0
0x1800af861  mov     rsi, rcx
0x1800af864  mov     [rbp+57h+var_50], rbx
0x1800af868  xor     edi, edi
0x1800af86a  xor     eax, eax
0x1800af86c  mov     rcx, rbx; this
0x1800af86f  mov     qword ptr [rbp+57h+psize.cx], rdi
0x1800af873  mov     r13, r8
0x1800af876  mov     qword ptr [rbp+57h+var_78.BlendOp], rax
0x1800af87a  mov     r12, rdx
0x1800af87d  mov     [rbp+57h+var_70], rdi
0x1800af881  movups  xmmword ptr [rbp+57h+hdc], xmm0
0x1800af885  movups  xmmword ptr [rbp+57h+h], xmm0
0x1800af889  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800af88e  test    r12, r12
0x1800af891  jnz     short loc_1800AF8F1
0x1800af893  cmp     [rsi+0B8h], edi
0x1800af899  jz      loc_1800AF94D
0x1800af89f  mov     rax, cs:WPP_GLOBAL_Control
0x1800af8a6  lea     r14, WPP_GLOBAL_Control
0x1800af8ad  cmp     rax, r14
0x1800af8b0  jz      short loc_1800AF8E7
0x1800af8b2  test    byte ptr [rax+1Ch], 40h
0x1800af8b6  jz      short loc_1800AF8E7
0x1800af8b8  cmp     byte ptr [rax+19h], 5
0x1800af8bc  jb      short loc_1800AF8E7
0x1800af8be  mov     ebx, [rsi+50h]
0x1800af8c1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800af8c6  lea     edx, [rdi+18h]
0x1800af8c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af8d0  lea     r8, WPP_8078f27b9915346d8ab3175536312c32_Traceguids
0x1800af8d7  mov     r9d, eax
0x1800af8da  mov     dword ptr [rsp+0F0h+hdcSrc], ebx
0x1800af8de  mov     rcx, [rcx+10h]
0x1800af8e2  call    WPP_SF_Dd
0x1800af8e7  mov     edi, 1
0x1800af8ec  jmp     loc_1800B0238
0x1800af8f1  mov     rax, [r12]
0x1800af8f5  mov     rcx, r12
0x1800af8f8  mov     rax, [rax+78h]
0x1800af8fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af901  test    eax, eax
0x1800af903  jz      short loc_1800AF94D
0x1800af905  mov     rax, cs:WPP_GLOBAL_Control
0x1800af90c  lea     r14, WPP_GLOBAL_Control
0x1800af913  cmp     rax, r14
0x1800af916  jz      short loc_1800AF8E7
0x1800af918  test    dword ptr [rax+1Ch], 100h
0x1800af91f  jz      short loc_1800AF8E7
0x1800af921  cmp     byte ptr [rax+19h], 5
0x1800af925  jb      short loc_1800AF8E7
0x1800af927  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800af92c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af933  lea     r8, WPP_8078f27b9915346d8ab3175536312c32_Traceguids
0x1800af93a  mov     edx, 19h
0x1800af93f  mov     r9d, eax
0x1800af942  mov     rcx, [rcx+10h]
0x1800af946  call    WPP_SF_d
0x1800af94b  jmp     short loc_1800AF8E7
0x1800af94d  mov     rcx, [rsi+0C8h]; hWnd
0x1800af954  call    cs:__imp_IsIconic
0x1800af95a  test    eax, eax
0x1800af95c  jz      short loc_1800AF99B
0x1800af95e  mov     rax, cs:WPP_GLOBAL_Control
0x1800af965  lea     r14, WPP_GLOBAL_Control
0x1800af96c  cmp     rax, r14
0x1800af96f  jz      loc_1800AF8E7
0x1800af975  test    byte ptr [rax+1Ch], 40h
0x1800af979  jz      loc_1800AF8E7
0x1800af97f  cmp     byte ptr [rax+19h], 5
0x1800af983  jb      loc_1800AF8E7
0x1800af989  mov     ebx, [rsi+50h]
0x1800af98c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800af991  mov     edx, 1Ah
0x1800af996  jmp     loc_1800AF8C9
0x1800af99b  mov     [rsi+0B8h], edi
0x1800af9a1  cmp     [rsi+0C8h], rdi
0x1800af9a8  jnz     short loc_1800AFA1B
0x1800af9aa  mov     rax, cs:WPP_GLOBAL_Control
0x1800af9b1  lea     r14, WPP_GLOBAL_Control
0x1800af9b8  cmp     rax, r14
0x1800af9bb  jz      short loc_1800AF9F4
0x1800af9bd  test    byte ptr [rax+1Ch], 40h
0x1800af9c1  jz      short loc_1800AF9F4
0x1800af9c3  cmp     byte ptr [rax+19h], 4
0x1800af9c7  jb      short loc_1800AF9F4
0x1800af9c9  mov     ebx, [rsi+50h]
0x1800af9cc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800af9d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800af9d8  lea     r8, WPP_8078f27b9915346d8ab3175536312c32_Traceguids
0x1800af9df  mov     edx, 1Bh
0x1800af9e4  mov     dword ptr [rsp+0F0h+hdcSrc], ebx
0x1800af9e8  mov     r9d, eax
0x1800af9eb  mov     rcx, [rcx+10h]
0x1800af9ef  call    WPP_SF_Dd
0x1800af9f4  mov     eax, cs:dword_1808B7630
0x1800af9fa  cmp     eax, 5
0x1800af9fd  jbe     loc_1800AF8E7
0x1800afa03  lea     rdx, dword_180865094
0x1800afa0a  lea     rcx, dword_1808B7630
0x1800afa11  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800afa16  jmp     loc_1800AF8E7
0x1800afa1b  cmp     [rsi+0ACh], edi
0x1800afa21  jnz     loc_1800AFFFA
0x1800afa27  cmp     [rsi+0B4h], edi
0x1800afa2d  jnz     loc_1800AFFFA
0x1800afa33  mov     rax, cs:WPP_GLOBAL_Control
0x1800afa3a  lea     r14, WPP_GLOBAL_Control
0x1800afa41  lea     r15, WPP_8078f27b9915346d8ab3175536312c32_Traceguids
0x1800afa48  cmp     rax, r14
0x1800afa4b  jz      short loc_1800AFA84
0x1800afa4d  test    byte ptr [rax+1Ch], 40h
0x1800afa51  jz      short loc_1800AFA84
0x1800afa53  cmp     byte ptr [rax+19h], 5
0x1800afa57  jb      short loc_1800AFA84
0x1800afa59  mov     ebx, [rsi+50h]
0x1800afa5c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800afa61  mov     rcx, cs:WPP_GLOBAL_Control
0x1800afa68  mov     edx, 20h ; ' '
0x1800afa6d  mov     r9d, eax
0x1800afa70  mov     dword ptr [rsp+0F0h+hdcSrc], ebx
0x1800afa74  mov     r8, r15
0x1800afa77  mov     rcx, [rcx+10h]
0x1800afa7b  call    WPP_SF_Dd
0x1800afa80  lea     rbx, [rsi+40h]
0x1800afa84  mov     rcx, rsi; this
0x1800afa87  call    ?IsWindowLayered@RdpWin32RemoteAppPresenter@@IEAAHXZ; RdpWin32RemoteAppPresenter::IsWindowLayered(void)
0x1800afa8c  test    eax, eax
0x1800afa8e  jz      loc_1800AFE71
0x1800afa94  cmp     [rsi+0B0h], edi
0x1800afa9a  jz      loc_1800AFE71
0x1800afaa0  mov     rcx, [rsi+0A0h]
0x1800afaa7  test    rcx, rcx
0x1800afaaa  jz      loc_1800AFCFD
0x1800afab0  cmp     [rsi+90h], rdi
0x1800afab7  jz      loc_1800AFCFD
0x1800afabd  mov     rax, [rcx]
0x1800afac0  mov     rax, [rax+20h]
0x1800afac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afac9  mov     rcx, [rsi+0A0h]
0x1800afad0  mov     rax, [rcx]
0x1800afad3  mov     rax, [rax+28h]
0x1800afad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afadc  test    r12, r12
0x1800afadf  jz      loc_1800AFCFD
0x1800afae5  mov     rcx, [rsi+90h]
0x1800afaec  lea     rdx, [rbp+57h+var_48]
0x1800afaf0  mov     [rbp+57h+var_48], rdi
0x1800afaf4  mov     eax, [rcx+18h]
0x1800afaf7  mov     [rbp+57h+var_40], eax
0x1800afafa  mov     eax, [rcx+1Ch]
0x1800afafd  mov     rcx, r12
0x1800afb00  mov     [rbp+57h+var_3C], eax
0x1800afb03  mov     rax, [r12]
0x1800afb07  mov     rax, [rax+38h]
0x1800afb0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afb10  mov     ecx, eax
0x1800afb12  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x1800afb17  mov     edi, eax
0x1800afb19  test    eax, eax
0x1800afb1b  jns     short loc_1800AFB57
0x1800afb1d  mov     rax, cs:WPP_GLOBAL_Control
0x1800afb24  cmp     rax, r14
0x1800afb27  jz      loc_1800B0238
0x1800afb2d  test    byte ptr [rax+1Ch], 8
0x1800afb31  jz      loc_1800B0200
0x1800afb37  cmp     byte ptr [rax+19h], 2
0x1800afb3b  jb      loc_1800B0200
0x1800afb41  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800afb46  mov     edx, 21h ; '!'
0x1800afb4b  lea     rcx, aIntersectrectD; "IntersectRect DirtyRegion with texureRe"...
0x1800afb52  jmp     loc_1800B01DA
0x1800afb57  test    r13, r13
0x1800afb5a  jz      loc_1800AFC89
0x1800afb60  mov     rax, [r13+0]
0x1800afb64  mov     rdx, r12
0x1800afb67  mov     rcx, r13
0x1800afb6a  mov     rax, [rax+40h]
0x1800afb6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afb73  mov     ecx, eax
0x1800afb75  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x1800afb7a  mov     edi, eax
0x1800afb7c  test    eax, eax
0x1800afb7e  jns     short loc_1800AFBBA
0x1800afb80  mov     rax, cs:WPP_GLOBAL_Control
0x1800afb87  cmp     rax, r14
0x1800afb8a  jz      loc_1800B0238
0x1800afb90  test    byte ptr [rax+1Ch], 8
0x1800afb94  jz      loc_1800B0200
0x1800afb9a  cmp     byte ptr [rax+19h], 2
0x1800afb9e  jb      loc_1800B0200
0x1800afba4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800afba9  mov     edx, 22h ; '"'
0x1800afbae  lea     rcx, aIntersectregio_0; "IntersectRegion OpaqueRegion with Dirty"...
0x1800afbb5  jmp     loc_1800B01DA
0x1800afbba  mov     rcx, [rsi+0A0h]
0x1800afbc1  xor     r9d, r9d
0x1800afbc4  mov     rdx, [rsi+90h]
0x1800afbcb  mov     [rsp+0F0h+pptSrc], r13
0x1800afbd0  mov     dword ptr [rsp+0F0h+hdcSrc], 0
0x1800afbd8  mov     rax, [rcx]
0x1800afbdb  lea     r8d, [r9+1]
0x1800afbdf  mov     rax, [rax+40h]
0x1800afbe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afbe8  mov     ecx, eax
0x1800afbea  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x1800afbef  mov     edi, eax
0x1800afbf1  test    eax, eax
0x1800afbf3  jns     short loc_1800AFC2F
0x1800afbf5  mov     rax, cs:WPP_GLOBAL_Control
0x1800afbfc  cmp     rax, r14
0x1800afbff  jz      loc_1800B0238
0x1800afc05  test    byte ptr [rax+1Ch], 8
0x1800afc09  jz      loc_1800B0200
0x1800afc0f  cmp     byte ptr [rax+19h], 2
0x1800afc13  jb      loc_1800B0200
0x1800afc19  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800afc1e  mov     edx, 23h ; '#'
0x1800afc23  lea     rcx, aCopyregionRemo; "CopyRegion(REMOVE_ALPHA) failed"
0x1800afc2a  jmp     loc_1800B01DA
0x1800afc2f  mov     rax, [r12]
0x1800afc33  mov     rdx, r13
0x1800afc36  mov     rcx, r12
0x1800afc39  mov     rax, [rax+50h]
0x1800afc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afc42  mov     ecx, eax
0x1800afc44  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x1800afc49  mov     edi, eax
0x1800afc4b  test    eax, eax
0x1800afc4d  jns     short loc_1800AFC89
0x1800afc4f  mov     rax, cs:WPP_GLOBAL_Control
0x1800afc56  cmp     rax, r14
0x1800afc59  jz      loc_1800B0238
0x1800afc5f  test    byte ptr [rax+1Ch], 8
0x1800afc63  jz      loc_1800B0200
0x1800afc69  cmp     byte ptr [rax+19h], 2
0x1800afc6d  jb      loc_1800B0200
0x1800afc73  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800afc78  mov     edx, 24h ; '$'
0x1800afc7d  lea     rcx, aSubtractOpaque; "Subtract opaque region from DirtyRegion"...
0x1800afc84  jmp     loc_1800B01DA
0x1800afc89  mov     rcx, [rsi+0A0h]
0x1800afc90  xor     r9d, r9d
0x1800afc93  mov     rdx, [rsi+90h]
0x1800afc9a  xor     r8d, r8d
0x1800afc9d  mov     [rsp+0F0h+pptSrc], r12
0x1800afca2  mov     dword ptr [rsp+0F0h+hdcSrc], 0
0x1800afcaa  mov     rax, [rcx]
0x1800afcad  mov     rax, [rax+40h]
0x1800afcb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afcb6  mov     ecx, eax
0x1800afcb8  call    ?MapXResultToHR@@YAJW4_XResult32@@@Z; MapXResultToHR(_XResult32)
0x1800afcbd  mov     edi, eax
0x1800afcbf  test    eax, eax
0x1800afcc1  jns     short loc_1800AFCFD
0x1800afcc3  mov     rax, cs:WPP_GLOBAL_Control
0x1800afcca  cmp     rax, r14
0x1800afccd  jz      loc_1800B0238
0x1800afcd3  test    byte ptr [rax+1Ch], 8
0x1800afcd7  jz      loc_1800B0200
0x1800afcdd  cmp     byte ptr [rax+19h], 2
0x1800afce1  jb      loc_1800B0200
0x1800afce7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800afcec  mov     edx, 25h ; '%'
0x1800afcf1  lea     rcx, aCopyregionDefa; "CopyRegion(DEFAULT) failed"
0x1800afcf8  jmp     loc_1800B01DA
0x1800afcfd  lea     rdx, [rbp+57h+psize]; struct tagUPDATE_LAYERED_WINDOW_DATA *
0x1800afd01  mov     rcx, rsi; this
0x1800afd04  call    ?GenerateUpdateLayeredWindowData@RdpWin32RemoteAppPresenter@@IEAAJPEAUtagUPDATE_LAYERED_WINDOW_DATA@@@Z; RdpWin32RemoteAppPresenter::GenerateUpdateLayeredWindowData(tagUPDATE_LAYERED_WINDOW_DATA *)
0x1800afd09  mov     edi, eax
0x1800afd0b  cmp     eax, 8007139Fh
0x1800afd10  jnz     short loc_1800AFD19
0x1800afd12  xor     edi, edi
0x1800afd14  jmp     loc_1800B0238
0x1800afd19  test    edi, edi
0x1800afd1b  jns     short loc_1800AFD57
0x1800afd1d  mov     rax, cs:WPP_GLOBAL_Control
0x1800afd24  cmp     rax, r14
0x1800afd27  jz      loc_1800B0238
0x1800afd2d  test    byte ptr [rax+1Ch], 8
0x1800afd31  jz      loc_1800B0200
0x1800afd37  cmp     byte ptr [rax+19h], 2
0x1800afd3b  jb      loc_1800B0200
0x1800afd41  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800afd46  mov     edx, 26h ; '&'
0x1800afd4b  lea     rcx, aGenerateupdate; "GenerateUpdateLayeredWindowData failed"
  ... truncated ...
```
