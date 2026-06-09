# CContainerWnd::OnSysCommand(uint,unsigned __int64,__int64)

- ea: `0x140017fe4`
- end: `0x14001914d`
- name: `?OnSysCommand@CContainerWnd@@QEAA_JI_K_J@Z`
- size: `4457`
- prototype: `__int64 __fastcall(CContainerWnd *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001d3e0`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000d078`
- `0x1400125e8`
- `0x140013d38`
- `0x14001524c`
- `0x140017fe4`
- `0x1400197d4`
- `0x140019ff8`
- `0x14001e454`
- `0x140028bf0`
- `0x14002a7d8`
- `0x14005d668`
- `0x14009e9ac`
- `0x14009ea34`
- `0x1400a3674`
- `0x1400a3eb0`
- `0x1400f9104`
- `0x1400f915c`
- `0x140111220`
- `0x140112010`

## import_xrefs

- `USER32!MoveWindow` at `0x1400188b1`
- `USER32!MoveWindow` at `0x1400188b1`
- `USER32!GetClientRect` at `0x1400183c5`
- `USER32!GetClientRect` at `0x1400183c5`
- `USER32!GetWindowRect` at `0x140018840`
- `USER32!GetWindowRect` at `0x140018840`
- `USER32!IsIconic` at `0x1400182ff`
- `USER32!IsIconic` at `0x1400182ff`
- `USER32!DefWindowProcW` at `0x1400181b0`
- `USER32!DefWindowProcW` at `0x1400190c2`
- `USER32!DefWindowProcW` at `0x1400181b0`
- `USER32!DefWindowProcW` at `0x1400190c2`
- `KERNEL32!GetLastError` at `0x1400183f6`
- `KERNEL32!GetLastError` at `0x140018871`
- `KERNEL32!GetLastError` at `0x1400188d6`
- `KERNEL32!GetLastError` at `0x1400183f6`
- `KERNEL32!GetLastError` at `0x140018871`
- `KERNEL32!GetLastError` at `0x1400188d6`
- `OLEAUT32!__imp_VariantClear` at `0x14001873e`
- `OLEAUT32!__imp_VariantClear` at `0x14001873e`

## pseudocode

```c
LRESULT __fastcall CContainerWnd::OnSysCommand(CContainerWnd *this, UINT a2, WPARAM a3, const unsigned __int16 *a4)
{
  unsigned int v4; // r14d
  int v6; // eax
  char *v9; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v11; // ebx
  unsigned int v12; // eax
  int v13; // edx
  int v14; // ebx
  unsigned int v15; // eax
  UINT v16; // edx
  unsigned int v18; // eax
  unsigned int v19; // eax
  PVOID *v20; // rcx
  unsigned int v21; // eax
  HWND v22; // rcx
  HWND v23; // rcx
  DWORD LastError; // eax
  __int64 v25; // rdi
  DWORD v26; // ebx
  unsigned int v27; // eax
  __int64 v28; // r8
  unsigned int v29; // eax
  CEtwEventProv *ProviderInstance; // rax
  unsigned int v31; // r14d
  unsigned int v32; // r14d
  unsigned int v33; // r14d
  unsigned int v34; // r14d
  unsigned int v35; // r14d
  unsigned int v36; // r14d
  __int64 v37; // r8
  __int64 v38; // rdx
  unsigned int v39; // eax
  __int64 v40; // rdx
  __int64 (__fastcall ***v41)(_QWORD, GUID *, UINT *); // r9
  int v42; // r14d
  unsigned int v43; // eax
  int v44; // edx
  int v45; // r14d
  unsigned int v46; // eax
  int v47; // edx
  const char *v48; // rcx
  __int64 v49; // rcx
  __int16 v50; // dx
  HWND v51; // rcx
  __int64 v52; // rdi
  unsigned int v53; // eax
  __int64 v54; // r8
  __int64 v55; // rdx
  int v56; // edx
  int v57; // ebx
  unsigned int v58; // eax
  __int64 v59; // rcx
  unsigned int v60; // eax
  HWND v61; // rdx
  unsigned int v62; // r14d
  unsigned int v63; // r14d
  unsigned int v64; // r14d
  unsigned int v65; // r14d
  unsigned int v66; // r14d
  unsigned int v67; // edx
  __int64 v68; // r8
  int v69; // r14d
  unsigned int v70; // eax
  __int64 (__fastcall ***v71)(_QWORD, GUID *, UINT *); // r9
  unsigned int v72; // r14d
  unsigned int v73; // r14d
  unsigned int v74; // r14d
  unsigned int v75; // r14d
  unsigned int v76; // r14d
  unsigned int v77; // r14d
  __int64 v78; // rcx
  __int16 v79; // dx
  __int64 (__fastcall ***v80)(_QWORD, GUID *, unsigned int *); // rcx
  int v81; // r14d
  unsigned int v82; // eax
  int v83; // r14d
  unsigned int v84; // eax
  int v85; // r14d
  unsigned int v86; // eax
  int v87; // edx
  const char *v88; // rcx
  __int64 (__fastcall ***v89)(_QWORD, GUID *, unsigned int *); // rcx
  int v90; // r14d
  unsigned int v91; // eax
  int v92; // r14d
  unsigned int v93; // eax
  __int64 v94; // rcx
  double v95; // xmm2_8
  int v96; // r9d
  double v97; // xmm1_8
  unsigned int v98; // r14d
  unsigned int v99; // r14d
  unsigned int v100; // r14d
  unsigned int v101; // r14d
  unsigned int v102; // r14d
  const unsigned __int16 *bRepaint; // [rsp+28h] [rbp-D8h]
  UINT Msg[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v105; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v106[2]; // [rsp+40h] [rbp-C0h] BYREF
  LPARAM lParam; // [rsp+48h] [rbp-B8h]
  VARIANTARG Rect; // [rsp+50h] [rbp-B0h] BYREF
  struct tagRECT v109; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v110[74]; // [rsp+80h] [rbp-80h] BYREF

  v4 = (unsigned __int16)a3;
  lParam = (LPARAM)a4;
  v6 = a3 & 0xFFF0;
  *(_QWORD *)&v109.left = a3;
  Msg[0] = a2;
  if ( v6 == 61488 )
  {
    v9 = (char *)this + 760;
    if ( (unsigned int)CContainerWnd::CanGoFullScreen(this) && !*(_DWORD *)(*(_QWORD *)v9 + 6260LL) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          136,
          &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
          CurrentThreadActivityIdPrefix);
      }
      v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 15) + 336LL))(
              *((_QWORD *)this + 15),
              0xFFFFFFFFLL);
      if ( v11 >= 0
        || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 0;
      }
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 137;
      goto LABEL_13;
    }
    if ( !*((_DWORD *)this + 480) || *(_DWORD *)(*(_QWORD *)v9 + 6260LL) )
    {
      v16 = a2;
    }
    else
    {
      v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 544LL))(*((_QWORD *)this + 16));
      if ( v14 >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v18 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 139, &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids, v18);
        }
        v11 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 15) + 336LL))(
                *((_QWORD *)this + 15),
                0xFFFFFFFFLL);
        if ( v11 >= 0
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return 0;
        }
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        v13 = 140;
LABEL_13:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
          v12,
          (__int64)"put_FullScreen failed!",
          v11);
        return 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          138,
          (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
          v15,
          (__int64)"SyncSessionDisplaySettings failed!",
          v14);
      }
      v16 = Msg[0];
    }
    return DefWindowProcW(*((HWND *)this + 1), v16, a3, lParam);
  }
  if ( v6 == 61472 )
  {
    if ( *((_DWORD *)this + 28) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids, v19);
      }
      CClientUtilsWin32::NotifyShellOfFullScreen(
        *((HWND *)this + 1),
        0,
        (struct ITaskbarList2 **)this + 229,
        (int *)this + 460);
    }
    goto LABEL_69;
  }
  if ( v6 != 61728 )
  {
    if ( v6 == 61536 )
    {
      ProviderInstance = CEtwEventProv::GetProviderInstance();
      CEtwEventProv::EtwCloseEventTrace(ProviderInstance, 4099);
    }
    goto LABEL_69;
  }
  if ( *((_DWORD *)this + 29) )
  {
    if ( !*(_DWORD *)(*((_QWORD *)this + 95) + 6260LL) && *((_DWORD *)this + 28) )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 15) + 336LL))(*((_QWORD *)this + 15), 0);
    *((_DWORD *)this + 29) = 0;
    goto LABEL_69;
  }
  if ( !*((_DWORD *)this + 28) || IsIconic(*((HWND *)this + 1)) )
  {
    if ( !*((_DWORD *)this + 28) )
      goto LABEL_69;
    v22 = (HWND)*((_QWORD *)this + 1);
    v105 = 0;
    v106[0] = 0;
    if ( (int)CClientUtilsWin32::MonitorTopLeftFromHwnd(v22, &v105, v106) < 0 )
      goto LABEL_69;
    v23 = (HWND)*((_QWORD *)this + 1);
    *(_OWORD *)&Rect.vt = 0;
    if ( GetClientRect(v23, (LPRECT)&Rect) )
    {
      if ( *(_DWORD *)&Rect.vt != v105 || Rect.decVal.Hi32 != v106[0] )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          v29 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 144, &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids, v29);
        }
        CContainerWnd::FullScreenCycle(this);
      }
      goto LABEL_69;
    }
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v25 = *((_QWORD *)this + 1);
      v26 = LastError;
      v27 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(bRepaint) = v26;
      WPP_SF_Dqd(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, v28, v27, v25);
      goto LABEL_69;
    }
  }
  else
  {
    v106[0] = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 15) + 336LL))(*((_QWORD *)this + 15), 0);
    if ( (v106[0] & 0x80000000) == 0 )
    {
LABEL_69:
      v20 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_70;
    }
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(bRepaint) = v106[0];
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        142,
        (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
        v21,
        (__int64)"put_FullScreen failed!");
      goto LABEL_69;
    }
  }
LABEL_70:
  if ( v4 > 0xA4 )
  {
    v67 = 175;
    if ( v4 > 0xAF )
    {
      v98 = v4 - 176;
      if ( v98 )
      {
        v99 = v98 - 1;
        if ( v99 )
        {
          v100 = v99 - 1;
          if ( v100 )
          {
            v101 = v100 - 1;
            if ( v101 )
            {
              v102 = v101 - 1;
              if ( v102 )
              {
                if ( v102 != 1 )
                  goto LABEL_262;
                v67 = 500;
              }
              else
              {
                v67 = 450;
              }
            }
            else
            {
              v67 = 400;
            }
          }
          else
          {
            v67 = 350;
          }
          goto LABEL_170;
        }
        v95 = DOUBLE_139_6917;
        v96 = 44;
        v97 = DOUBLE_35_6895;
      }
      else
      {
        v95 = DOUBLE_N74_006;
        v96 = 57;
        v97 = DOUBLE_40_7143;
      }
    }
    else
    {
      if ( v4 != 175 )
      {
        v72 = v4 - 165;
        if ( !v72 )
          goto LABEL_170;
        v73 = v72 - 1;
        if ( !v73 )
        {
          v67 = 200;
          goto LABEL_170;
        }
        v74 = v73 - 1;
        if ( !v74 )
        {
          v67 = 250;
          goto LABEL_170;
        }
        v75 = v74 - 1;
        if ( !v75 )
        {
          v67 = 300;
          goto LABEL_170;
        }
        v76 = v75 - 1;
        if ( v76 )
        {
          v77 = v76 - 1;
          if ( v77 )
          {
            if ( v77 != 1 )
              goto LABEL_262;
            v78 = *((_QWORD *)this + 15);
            if ( !v78 )
              return 0;
            *(_QWORD *)Msg = 0;
            LOWORD(v105) = 0;
            if ( (*(int (__fastcall **)(__int64, UINT *))(*(_QWORD *)v78 + 312LL))(v78, Msg) >= 0
              && (*(int (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)Msg + 1024LL))(*(_QWORD *)Msg, &v105) >= 0 )
            {
              v79 = -1;
              if ( (_WORD)v105 == 0xFFFF )
                v79 = 0;
              LOWORD(v105) = v79;
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)Msg + 1016LL))(*(_QWORD *)Msg);
            }
            goto LABEL_143;
          }
          v80 = (__int64 (__fastcall ***)(_QWORD, GUID *, unsigned int *))*((_QWORD *)this + 15);
          *(_QWORD *)v106 = 0;
          v81 = (**v80)(v80, &IID_IMsRdpClientNonScriptable7, v106);
          if ( v81 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v82 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              167,
              (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
              v82,
              (__int64)"QueryInterface(IID_IMsRdpClientNonScriptable7) failed!",
              v81);
          }
          if ( !*(_QWORD *)v106 )
            return 0;
          *(_QWORD *)Msg = 0;
          v83 = (*(__int64 (__fastcall **)(_QWORD, UINT *))(**(_QWORD **)v106 + 552LL))(*(_QWORD *)v106, Msg);
          if ( v83 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v84 = RdpWppGetCurrentThreadActivityIdPrefix();
            LODWORD(bRepaint) = v83;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              168,
              (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
              v84,
              (__int64)"get_Clipboard failed!",
              bRepaint);
          }
          if ( !*(_QWORD *)Msg )
          {
LABEL_250:
            v59 = *(_QWORD *)v106;
            if ( !*(_QWORD *)v106 )
              return 0;
            *(_QWORD *)v106 = 0;
            goto LABEL_145;
          }
          v85 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)Msg + 48LL))(*(_QWORD *)Msg);
          if ( v85 >= 0
            || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_248:
            v94 = *(_QWORD *)Msg;
            if ( *(_QWORD *)Msg )
            {
              *(_QWORD *)Msg = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
            }
            goto LABEL_250;
          }
          v86 = RdpWppGetCurrentThreadActivityIdPrefix();
          v87 = 169;
          v88 = "SyncRemoteClipboardToLocalSession failed.";
        }
        else
        {
          v89 = (__int64 (__fastcall ***)(_QWORD, GUID *, unsigned int *))*((_QWORD *)this + 15);
          *(_QWORD *)v106 = 0;
          v90 = (**v89)(v89, &IID_IMsRdpClientNonScriptable7, v106);
          if ( v90 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v91 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              164,
              (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
              v91,
              (__int64)"QueryInterface(IID_IMsRdpClientNonScriptable7) failed!",
              v90);
          }
          if ( !*(_QWORD *)v106 )
            return 0;
          *(_QWORD *)Msg = 0;
          v92 = (*(__int64 (__fastcall **)(_QWORD, UINT *))(**(_QWORD **)v106 + 552LL))(*(_QWORD *)v106, Msg);
          if ( v92 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v93 = RdpWppGetCurrentThreadActivityIdPrefix();
            LODWORD(bRepaint) = v92;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              165,
              (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
              v93,
              (__int64)"get_Clipboard failed!",
              bRepaint);
          }
          if ( !*(_QWORD *)Msg )
            goto LABEL_250;
          v85 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)Msg + 32LL))(*(_QWORD *)Msg);
          if ( v85 >= 0
            || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_248;
          }
          v86 = RdpWppGetCurrentThreadActivityIdPrefix();
          v87 = 166;
          v88 = "SyncLocalClipboardToRemoteSession failed.";
        }
        LODWORD(bRepaint) = v85;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v87,
          (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
          v86,
          (__int64)v88,
          bRepaint);
        goto LABEL_248;
      }
      v95 = DOUBLE_2_3488;
      v96 = 42;
      v97 = DOUBLE_48_8534;
    }
    CContainerWnd::InjectLocation3D(this, v97, v95, v96);
    return 0;
  }
  if ( v4 == 164 )
  {
    v67 = 150;
    goto LABEL_170;
  }
  if ( v4 <= 0x9B )
  {
    if ( v4 == 155 )
    {
      v37 = *((_QWORD *)this + 16);
      if ( v37 )
      {
        v38 = 3;
        goto LABEL_83;
      }
      if ( v20 == &WPP_GLOBAL_Control || (*((_BYTE *)v20 + 28) & 1) == 0 || *((_BYTE *)v20 + 25) < 2u )
        return 0;
      v39 = RdpWppGetCurrentThreadActivityIdPrefix();
      v40 = 158;
      goto LABEL_118;
    }
    v31 = v4 - 109;
    if ( !v31 )
    {
      CAboutDlg::CAboutDlg(
        (CAboutDlg *)v110,
        *((HWND *)this + 1),
        *((HINSTANCE *)this + 13),
        *(_DWORD *)(*((_QWORD *)this + 12) + 1612LL),
        (const unsigned __int16 *)(*((_QWORD *)this + 12) + 1616LL));
      CDlgBase::DoModal((CDlgBase *)v110);
      v110[0] = &CAboutDlg::`vftable';
      CDlgBase::~CDlgBase((CDlgBase *)v110);
      return 0;
    }
    v32 = v31 - 3;
    if ( !v32 )
    {
      if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 && *((_BYTE *)v20 + 25) >= 4u )
      {
        v60 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids, v60);
      }
      v61 = (HWND)*((_QWORD *)this + 1);
      if ( v61 && *((_QWORD *)this + 12) )
        CSH::SH_DisplayClientHelp(
          (CSH *)*(unsigned int *)(*((_QWORD *)this + 95) + 6260LL),
          v61,
          L"mshelp://windows/?id=f55326fa-e629-423b-abba-b30f76cc61e6",
          a4,
          *(_DWORD *)(*((_QWORD *)this + 95) + 6260LL),
          bRepaint);
      return 0;
    }
    v33 = v32 - 33;
    if ( v33 )
    {
      v34 = v33 - 6;
      if ( v34 )
      {
        v35 = v34 - 1;
        if ( !v35 )
        {
          v37 = *((_QWORD *)this + 16);
          if ( v37 )
          {
            v38 = 1;
            goto LABEL_83;
          }
          if ( v20 == &WPP_GLOBAL_Control || (*((_BYTE *)v20 + 28) & 1) == 0 || *((_BYTE *)v20 + 25) < 2u )
            return 0;
          v39 = RdpWppGetCurrentThreadActivityIdPrefix();
          v40 = 155;
          goto LABEL_118;
        }
        v36 = v35 - 1;
        if ( !v36 )
        {
          v37 = *((_QWORD *)this + 16);
          if ( v37 )
          {
            v38 = 0;
            goto LABEL_83;
          }
          if ( v20 == &WPP_GLOBAL_Control || (*((_BYTE *)v20 + 28) & 1) == 0 || *((_BYTE *)v20 + 25) < 2u )
            return 0;
          v39 = RdpWppGetCurrentThreadActivityIdPrefix();
          v40 = 156;
LABEL_118:
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v40, &WPP_c53b5e828c42300d429425e15b0600ad_Traceguids, v39);
          return 0;
        }
        if ( v36 == 1 )
        {
          v37 = *((_QWORD *)this + 16);
          if ( v37 )
          {
            v38 = 4;
LABEL_83:
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 512LL))(v37, v38);
            return 0;
          }
          if ( v20 == &WPP_GLOBAL_Control || (*((_BYTE *)v20 + 28) & 1) == 0 || *((_BYTE *)v20 + 25) < 2u )
            return 0;
          v39 = RdpWppGetCurrentThreadActivityIdPrefix();
          v40 = 157;
          goto LABEL_118;
        }
LABEL_262:
        DefWindowProcW(*((HWND *)this + 1), Msg[0], *(WPARAM *)&v109.left, lParam);
        return 0;
      }
      v41 = (__int64 (__fastcall ***)(_QWORD, GUID *, UINT *))*((_QWORD *)this + 15);
      if ( !v41 )
      {
        if ( v20 == &WPP_GLOBAL_Control || (*((_BYTE *)v20 + 28) & 1) == 0 || *((_BYTE *)v20 + 25) < 2u )
          return 0;
        v39 = RdpWppGetCurrentThreadActivityIdPrefix();
        v40 = 154;
        goto LABEL_118;
      }
      *(_QWORD *)Msg = 0;
      v42 = (**v41)(v41, &IID_IMsRdpExtendedSettings, Msg);
      if ( v42 < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_143;
        }
        v43 = RdpWppGetCurrentThreadActivityIdPrefix();
        v44 = 152;
        goto LABEL_106;
      }
      memset(&Rect, 0, sizeof(Rect));
      Rect.iVal = -1;
      Rect.vt = 11;
      v45 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**(_QWORD **)Msg + 24LL))(
              *(_QWORD *)Msg,
              L"ShowSessionDiagnostics",
              &Rect);
      if ( v45 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v46 = RdpWppGetCurrentThreadActivityIdPrefix();
        v47 = 153;
        v48 = "put_Property(UTREG_UI_SHOWSESSIONDIAGNOSTICS) failed!";
LABEL_112:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v47,
          (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
          v46,
          (__int64)v48,
          v45);
        goto LABEL_113;
      }
      goto LABEL_113;
    }
    v49 = *((_QWORD *)this + 15);
    if ( !v49 )
      return 0;
    *(_QWORD *)Msg = 0;
    LOWORD(v105) = 0;
    if ( (*(int (__fastcall **)(__int64, UINT *))(*(_QWORD *)v49 + 312LL))(v49, Msg) < 0
      || (*(int (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)Msg + 840LL))(*(_QWORD *)Msg, &v105) < 0 )
    {
      goto LABEL_143;
    }
    v50 = -1;
    if ( (_WORD)v105 == 0xFFFF )
      v50 = 0;
    LOWORD(v105) = v50;
    if ( (*(int (__fastcall **)(_QWORD))(**(_QWORD **)Msg + 832LL))(*(_QWORD *)Msg) < 0 )
      goto LABEL_143;
    *(_DWORD *)(*((_QWORD *)this + 95) + 46160LL) = (_WORD)v105 != 0;
    if ( !(_WORD)v105 )
    {
      v51 = (HWND)*((_QWORD *)this + 1);
      v109 = 0;
      if ( GetWindowRect(v51, &v109) )
      {
        if ( MoveWindow(*((HWND *)this + 1), v109.left, v109.top, v109.right - v109.left, v109.bottom - v109.top, 1)
          || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_137;
        }
        GetLastError();
        v52 = *((_QWORD *)this + 1);
        v53 = RdpWppGetCurrentThreadActivityIdPrefix();
        v55 = 150;
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_137;
        }
        GetLastError();
        v52 = *((_QWORD *)this + 1);
        v53 = RdpWppGetCurrentThreadActivityIdPrefix();
        v55 = 149;
      }
      WPP_SF_Dqd(*((_QWORD *)WPP_GLOBAL_Control + 2), v55, v54, v53, v52);
    }
LABEL_137:
    v57 = CContainerWnd::ResizeAxHostWnd(this);
    if ( v57 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v58 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(bRepaint) = v57;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        151,
        (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
        v58,
        (__int64)"ResizeAxHostWnd failed",
        bRepaint);
    }
    RDWin32ClientTelemetry::TraceSmartSizingChange((RDWin32ClientTelemetry *)((_WORD)v105 != 0), v56);
    goto LABEL_143;
  }
  v62 = v4 - 156;
  if ( !v62 )
  {
    v71 = (__int64 (__fastcall ***)(_QWORD, GUID *, UINT *))*((_QWORD *)this + 15);
    if ( !v71 )
    {
      if ( v20 == &WPP_GLOBAL_Control || (*((_BYTE *)v20 + 28) & 1) == 0 || *((_BYTE *)v20 + 25) < 2u )
        return 0;
      v39 = RdpWppGetCurrentThreadActivityIdPrefix();
      v40 = 161;
      goto LABEL_118;
    }
    *(_QWORD *)Msg = 0;
    v42 = (**v71)(v71, &IID_IMsRdpExtendedSettings, Msg);
    if ( v42 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_143;
      }
      v43 = RdpWppGetCurrentThreadActivityIdPrefix();
      v44 = 159;
LABEL_106:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v44,
        (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
        v43,
        (__int64)"QueryInterface failed for IMsRdpExtendedSettings",
        v42);
LABEL_143:
      v59 = *(_QWORD *)Msg;
      if ( !*(_QWORD *)Msg )
        return 0;
      *(_QWORD *)Msg = 0;
LABEL_145:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
      return 0;
    }
    memset(&Rect, 0, sizeof(Rect));
    Rect.iVal = -1;
    Rect.vt = 11;
    v45 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**(_QWORD **)Msg + 24LL))(
            *(_QWORD *)Msg,
            L"ShowConnectionInformation",
            &Rect);
    if ( v45 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v46 = RdpWppGetCurrentThreadActivityIdPrefix();
      v47 = 160;
      v48 = "put_Property(UTREG_UI_SHOWCONNECTIONINFORMATION) failed!";
      goto LABEL_112;
    }
LABEL_113:
    VariantClear(&Rect);
    goto LABEL_143;
  }
  v63 = v62 - 1;
  if ( v63 )
  {
    v64 = v63 - 3;
    if ( v64 )
    {
      v65 = v64 - 1;
      if ( v65 )
      {
        v66 = v65 - 1;
        if ( v66 )
        {
          if ( v66 != 1 )
            goto LABEL_262;
          v67 = 125;
        }
        else
        {
          v67 = 100;
        }
      }
      else
      {
        v67 = 75;
      }
    }
    else
    {
      v67 = 50;
    }
LABEL_170:
    CContainerWnd::SetZoomLevel(this, v67);
    return 0;
  }
  v68 = *((_QWORD *)this + 15);
  if ( v68 )
  {
    v69 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v68 + 336LL))(*((_QWORD *)this + 15), 0xFFFFFFFFLL);
    if ( v69 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v70 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        162,
        (unsigned int)&WPP_c53b5e828c42300d429425e15b0600ad_Traceguids,
        v70,
        (__int64)"put_FullScreen(VARIANT_TRUE) failed!",
        v69);
    }
    return 0;
  }
  if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 && *((_BYTE *)v20 + 25) >= 2u )
  {
    v39 = RdpWppGetCurrentThreadActivityIdPrefix();
    v40 = 163;
    goto LABEL_118;
  }
  return 0;
}

```

## disassembly

```asm
0x140017fe4  push    rbp
0x140017fe6  push    rbx
0x140017fe7  push    rsi
0x140017fe8  push    rdi
0x140017fe9  push    r12
0x140017feb  push    r13
0x140017fed  push    r14
0x140017fef  push    r15
0x140017ff1  lea     rbp, [rsp-1E8h]
0x140017ff9  sub     rsp, 2E8h
0x140018000  mov     rax, cs:__security_cookie
0x140018007  xor     rax, rsp
0x14001800a  mov     [rbp+220h+var_50], rax
0x140018011  movzx   r14d, r8w
0x140018015  mov     rdi, r8
0x140018018  mov     eax, r14d
0x14001801b  mov     [rsp+320h+lParam], r9
0x140018020  and     eax, 0FFF0h
0x140018025  mov     qword ptr [rsp+320h+var_2B8.left], r8
0x14001802a  mov     [rsp+320h+Msg], edx
0x14001802e  mov     r12d, edx
0x140018031  mov     r15, rcx
0x140018034  cmp     eax, 0F030h
0x140018039  jnz     loc_14001825F
0x14001803f  lea     rbx, [rcx+2F8h]
0x140018046  call    ?CanGoFullScreen@CContainerWnd@@AEAAHXZ; CContainerWnd::CanGoFullScreen(void)
0x14001804b  xor     esi, esi
0x14001804d  test    eax, eax
0x14001804f  jz      loc_140018112
0x140018055  mov     rax, [rbx]
0x140018058  cmp     [rax+1874h], esi
0x14001805e  jnz     loc_140018112
0x140018064  mov     rax, cs:WPP_GLOBAL_Control
0x14001806b  lea     r12, WPP_GLOBAL_Control
0x140018072  cmp     rax, r12
0x140018075  jz      short loc_1400180AA
0x140018077  test    dword ptr [rax+1Ch], 100h
0x14001807e  jz      short loc_1400180AA
0x140018080  cmp     byte ptr [rax+19h], 4
0x140018084  jb      short loc_1400180AA
0x140018086  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001808b  mov     rcx, cs:WPP_GLOBAL_Control
0x140018092  lea     r8, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x140018099  mov     edx, 88h
0x14001809e  mov     r9d, eax
0x1400180a1  mov     rcx, [rcx+10h]
0x1400180a5  call    WPP_SF_d
0x1400180aa  mov     rcx, [r15+78h]
0x1400180ae  or      edx, 0FFFFFFFFh
0x1400180b1  mov     rax, [rcx]
0x1400180b4  mov     rax, [rax+150h]
0x1400180bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400180c0  mov     ebx, eax
0x1400180c2  test    eax, eax
0x1400180c4  jns     loc_140019128
0x1400180ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400180d1  cmp     rcx, r12
0x1400180d4  jz      loc_140019128
0x1400180da  test    byte ptr [rcx+1Ch], 8
0x1400180de  jz      loc_140019128
0x1400180e4  mov     r13b, 2
0x1400180e7  cmp     [rcx+19h], r13b
0x1400180eb  jb      loc_140019128
0x1400180f1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400180f6  mov     edx, 89h
0x1400180fb  mov     dword ptr [rsp+320h+bRepaint], ebx
0x1400180ff  lea     rcx, aPutFullscreenF; "put_FullScreen failed!"
0x140018106  lea     r8, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x14001810d  jmp     loc_140018B46
0x140018112  cmp     [r15+780h], esi
0x140018119  jz      loc_140018257
0x14001811f  mov     rax, [rbx]
0x140018122  cmp     [rax+1874h], esi
0x140018128  jnz     loc_140018257
0x14001812e  mov     rcx, [r15+80h]
0x140018135  mov     rax, [rcx]
0x140018138  mov     rax, [rax+220h]
0x14001813f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018144  mov     ebx, eax
0x140018146  test    eax, eax
0x140018148  jns     short loc_1400181BB
0x14001814a  mov     rcx, cs:WPP_GLOBAL_Control
0x140018151  lea     r12, WPP_GLOBAL_Control
0x140018158  cmp     rcx, r12
0x14001815b  jz      short loc_1400181A0
0x14001815d  test    byte ptr [rcx+1Ch], 8
0x140018161  jz      short loc_1400181A0
0x140018163  mov     r13b, 2
0x140018166  cmp     [rcx+19h], r13b
0x14001816a  jb      short loc_1400181A0
0x14001816c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140018171  lea     rcx, aSyncsessiondis; "SyncSessionDisplaySettings failed!"
0x140018178  mov     dword ptr [rsp+320h+bRepaint], ebx
0x14001817c  mov     qword ptr [rsp+320h+nHeight], rcx
0x140018181  lea     r8, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x140018188  mov     rcx, cs:WPP_GLOBAL_Control
0x14001818f  mov     edx, 8Ah
0x140018194  mov     r9d, eax
0x140018197  mov     rcx, [rcx+10h]
0x14001819b  call    WPP_SF_DsD
0x1400181a0  mov     edx, [rsp+320h+Msg]; Msg
0x1400181a4  mov     r9, [rsp+320h+lParam]; lParam
0x1400181a9  mov     r8, rdi; wParam
0x1400181ac  mov     rcx, [r15+8]; hWnd
0x1400181b0  call    cs:__imp_DefWindowProcW
0x1400181b6  jmp     loc_14001912A
0x1400181bb  mov     rax, cs:WPP_GLOBAL_Control
0x1400181c2  lea     r12, WPP_GLOBAL_Control
0x1400181c9  cmp     rax, r12
0x1400181cc  jz      short loc_140018201
0x1400181ce  test    dword ptr [rax+1Ch], 100h
0x1400181d5  jz      short loc_140018201
0x1400181d7  cmp     byte ptr [rax+19h], 4
0x1400181db  jb      short loc_140018201
0x1400181dd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400181e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400181e9  lea     r8, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x1400181f0  mov     edx, 8Bh
0x1400181f5  mov     r9d, eax
0x1400181f8  mov     rcx, [rcx+10h]
0x1400181fc  call    WPP_SF_d
0x140018201  mov     rcx, [r15+78h]
0x140018205  or      edx, 0FFFFFFFFh
0x140018208  mov     rax, [rcx]
0x14001820b  mov     rax, [rax+150h]
0x140018212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018217  mov     ebx, eax
0x140018219  test    eax, eax
0x14001821b  jns     loc_140019128
0x140018221  mov     rcx, cs:WPP_GLOBAL_Control
0x140018228  cmp     rcx, r12
0x14001822b  jz      loc_140019128
0x140018231  test    byte ptr [rcx+1Ch], 8
0x140018235  jz      loc_140019128
0x14001823b  mov     r13b, 2
0x14001823e  cmp     [rcx+19h], r13b
0x140018242  jb      loc_140019128
0x140018248  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001824d  mov     edx, 8Ch
0x140018252  jmp     loc_1400180FB
0x140018257  mov     edx, r12d
0x14001825a  jmp     loc_1400181A4
0x14001825f  xor     esi, esi
0x140018261  lea     r12, WPP_GLOBAL_Control
0x140018268  lea     rbx, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x14001826f  mov     dil, 8
0x140018272  mov     r13b, 2
0x140018275  cmp     eax, 0F020h
0x14001827a  jnz     short loc_1400182DE
0x14001827c  cmp     [rcx+70h], esi
0x14001827f  jz      loc_1400184DC
0x140018285  mov     rax, cs:WPP_GLOBAL_Control
0x14001828c  cmp     rax, r12
0x14001828f  jz      short loc_1400182C0
0x140018291  test    dword ptr [rax+1Ch], 100h
0x140018298  jz      short loc_1400182C0
0x14001829a  cmp     byte ptr [rax+19h], 5
0x14001829e  jb      short loc_1400182C0
0x1400182a0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400182a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400182ac  mov     edx, 8Dh
0x1400182b1  mov     r9d, eax
0x1400182b4  mov     r8, rbx
0x1400182b7  mov     rcx, [rcx+10h]
0x1400182bb  call    WPP_SF_d
0x1400182c0  mov     rcx, [r15+8]; HWND
0x1400182c4  lea     r9, [r15+730h]; int *
0x1400182cb  lea     r8, [r15+728h]; struct ITaskbarList2 **
0x1400182d2  xor     edx, edx; int
0x1400182d4  call    ?NotifyShellOfFullScreen@CClientUtilsWin32@@SAHPEAUHWND__@@HPEAPEAUITaskbarList2@@PEAH@Z; CClientUtilsWin32::NotifyShellOfFullScreen(HWND__ *,int,ITaskbarList2 * *,int *)
0x1400182d9  jmp     loc_1400184DC
0x1400182de  cmp     eax, 0F120h
0x1400182e3  jnz     loc_1400184C3
0x1400182e9  cmp     [rcx+74h], esi
0x1400182ec  jnz     loc_140018494
0x1400182f2  cmp     [rcx+70h], esi
0x1400182f5  jz      loc_140018387
0x1400182fb  mov     rcx, [rcx+8]; hWnd
0x1400182ff  call    cs:__imp_IsIconic
0x140018305  test    eax, eax
0x140018307  jnz     short loc_140018387
0x140018309  mov     rcx, [r15+78h]
0x14001830d  xor     edx, edx
0x14001830f  mov     rax, [rcx]
0x140018312  mov     rax, [rax+150h]
0x140018319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001831e  mov     [rsp+320h+var_2E0], eax
0x140018322  test    eax, eax
0x140018324  jns     loc_1400184DC
0x14001832a  mov     rcx, cs:WPP_GLOBAL_Control
0x140018331  cmp     rcx, r12
0x140018334  jz      loc_1400184E3
0x14001833a  test    [rcx+1Ch], dil
0x14001833e  jz      loc_1400184E3
0x140018344  cmp     [rcx+19h], r13b
0x140018348  jb      loc_1400184E3
0x14001834e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140018353  mov     ecx, [rsp+320h+var_2E0]
0x140018357  mov     edx, 8Eh
0x14001835c  mov     dword ptr [rsp+320h+bRepaint], ecx
0x140018360  mov     r9d, eax
0x140018363  lea     rcx, aPutFullscreenF; "put_FullScreen failed!"
0x14001836a  mov     r8, rbx
0x14001836d  mov     qword ptr [rsp+320h+nHeight], rcx
0x140018372  mov     rcx, cs:WPP_GLOBAL_Control
0x140018379  mov     rcx, [rcx+10h]
0x14001837d  call    WPP_SF_DsD
0x140018382  jmp     loc_1400184DC
0x140018387  cmp     [r15+70h], esi
0x14001838b  jz      loc_1400184DC
0x140018391  mov     rcx, [r15+8]; HWND
0x140018395  lea     r8, [rsp+320h+var_2E0]; unsigned int *
0x14001839a  lea     rdx, [rsp+320h+var_2E8]; unsigned int *
0x14001839f  mov     [rsp+320h+var_2E8], esi
0x1400183a3  mov     [rsp+320h+var_2E0], esi
0x1400183a7  call    ?MonitorTopLeftFromHwnd@CClientUtilsWin32@@SAJPEAUHWND__@@PEAI1@Z; CClientUtilsWin32::MonitorTopLeftFromHwnd(HWND__ *,uint *,uint *)
0x1400183ac  test    eax, eax
0x1400183ae  js      loc_1400184DC
0x1400183b4  mov     rcx, [r15+8]; hWnd
0x1400183b8  lea     rdx, [rsp+320h+Rect]; lpRect
0x1400183bd  xorps   xmm0, xmm0
0x1400183c0  movups  xmmword ptr [rsp+320h+Rect.left], xmm0
0x1400183c5  call    cs:__imp_GetClientRect
0x1400183cb  test    eax, eax
0x1400183cd  jnz     short loc_140018437
0x1400183cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400183d6  cmp     rcx, r12
0x1400183d9  jz      loc_1400184E3
0x1400183df  test    dword ptr [rcx+1Ch], 100h
0x1400183e6  jz      loc_1400184E3
0x1400183ec  cmp     [rcx+19h], r13b
0x1400183f0  jb      loc_1400184E3
0x1400183f6  call    cs:__imp_GetLastError
0x1400183fc  mov     rdi, [r15+8]
0x140018400  mov     ebx, eax
0x140018402  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140018407  mov     rcx, cs:WPP_GLOBAL_Control
0x14001840e  mov     edx, 8Fh
0x140018413  mov     dword ptr [rsp+320h+bRepaint], ebx
0x140018417  mov     r9d, eax
0x14001841a  mov     qword ptr [rsp+320h+nHeight], rdi
0x14001841f  mov     rcx, [rcx+10h]
0x140018423  call    WPP_SF_Dqd
0x140018428  lea     rbx, WPP_c53b5e828c42300d429425e15b0600ad_Traceguids
0x14001842f  mov     dil, 8
0x140018432  jmp     loc_1400184DC
0x140018437  mov     eax, [rsp+320h+var_2E8]
0x14001843b  cmp     [rsp+320h+Rect.left], eax
0x14001843f  jnz     short loc_14001844F
0x140018441  mov     eax, [rsp+320h+var_2E0]
0x140018445  cmp     [rsp+320h+Rect.top], eax
0x140018449  jz      loc_1400184DC
0x14001844f  mov     rax, cs:WPP_GLOBAL_Control
0x140018456  cmp     rax, r12
0x140018459  jz      short loc_14001848A
0x14001845b  test    dword ptr [rax+1Ch], 100h
0x140018462  jz      short loc_14001848A
0x140018464  cmp     byte ptr [rax+19h], 4
0x140018468  jb      short loc_14001848A
0x14001846a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14001846f  mov     rcx, cs:WPP_GLOBAL_Control
0x140018476  mov     edx, 90h
0x14001847b  mov     r9d, eax
0x14001847e  mov     r8, rbx
0x140018481  mov     rcx, [rcx+10h]
0x140018485  call    WPP_SF_d
0x14001848a  mov     rcx, r15; this
0x14001848d  call    ?FullScreenCycle@CContainerWnd@@QEAAXXZ; CContainerWnd::FullScreenCycle(void)
0x140018492  jmp     short loc_1400184DC
0x140018494  mov     rax, [rcx+2F8h]
0x14001849b  cmp     [rax+1874h], esi
0x1400184a1  jnz     short loc_1400184BD
0x1400184a3  cmp     [rcx+70h], esi
0x1400184a6  jz      short loc_1400184BD
0x1400184a8  mov     rcx, [rcx+78h]
0x1400184ac  xor     edx, edx
0x1400184ae  mov     rax, [rcx]
0x1400184b1  mov     rax, [rax+150h]
0x1400184b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400184bd  mov     [r15+74h], esi
0x1400184c1  jmp     short loc_1400184DC
0x1400184c3  cmp     eax, 0F060h
0x1400184c8  jnz     short loc_1400184DC
0x1400184ca  call    ?GetProviderInstance@CEtwEventProv@@SAAEAV1@XZ; CEtwEventProv::GetProviderInstance(void)
0x1400184cf  mov     edx, 1003h; int
0x1400184d4  mov     rcx, rax; this
0x1400184d7  call    ?EtwCloseEventTrace@CEtwEventProv@@QEAAJH@Z; CEtwEventProv::EtwCloseEventTrace(int)
0x1400184dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400184e3  mov     eax, 0A4h
0x1400184e8  cmp     r14d, eax
0x1400184eb  ja      loc_140018CAE
0x1400184f1  jz      loc_140018CA4
0x1400184f7  mov     eax, 9Bh
0x1400184fc  cmp     r14d, eax
0x1400184ff  ja      loc_140018A8B
0x140018505  jz      loc_140018A49
0x14001850b  sub     r14d, 6Dh ; 'm'
0x14001850f  jz      loc_1400189FF
0x140018515  sub     r14d, 3
0x140018519  jz      loc_140018995
  ... truncated ...
```
