# WindowsRemoteAppLib::CWinManager::DoZorder(void)

- ea: `0x1800acb6c`
- end: `0x1800ae091`
- name: `?DoZorder@CWinManager@WindowsRemoteAppLib@@QEAAJXZ`
- size: `5413`
- prototype: `__int64 __fastcall(WindowsRemoteAppLib::CWinManager *__hidden this)`
- caller_count: `3`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1802521c0`
- `0x180261b70`
- `0x18026368c`

## callees

- `0x180002224`
- `0x180002734`
- `0x18000281c`
- `0x180003e34`
- `0x180003f04`
- `0x180004004`
- `0x1800186a0`
- `0x1800186d0`
- `0x18001e170`
- `0x180039c98`
- `0x180039ce4`
- `0x180082910`
- `0x1800829d4`
- `0x180082ad8`
- `0x180082c10`
- `0x180092b3c`
- `0x18009f57c`
- `0x1800a561c`
- `0x1800aca08`
- `0x1800acb6c`
- `0x1800e9b1c`
- `0x180100a0c`
- `0x180262a94`
- `0x180262bbc`
- `0x180262d0c`
- `0x180262f74`
- `0x1802634b8`
- `0x180263644`
- `0x1802639e0`
- `0x180263ec4`
- `0x180688f3e`
- `0x180688fc0`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800acea4`
- `KERNEL32!GetLastError` at `0x1800add9a`
- `KERNEL32!GetLastError` at `0x1800adee9`
- `KERNEL32!GetLastError` at `0x1800acea4`
- `KERNEL32!GetLastError` at `0x1800add9a`
- `KERNEL32!GetLastError` at `0x1800adee9`
- `KERNEL32!GetCurrentThreadId` at `0x1800ad414`
- `KERNEL32!GetCurrentThreadId` at `0x1800ad51a`
- `KERNEL32!GetCurrentThreadId` at `0x1800ad414`
- `KERNEL32!GetCurrentThreadId` at `0x1800ad51a`
- `USER32!GetWindowLongPtrW` at `0x1800ad2a0`
- `USER32!GetWindowLongPtrW` at `0x1800ad2c0`
- `USER32!GetWindowLongPtrW` at `0x1800ad2d6`
- `USER32!GetWindowLongPtrW` at `0x1800ad713`
- `USER32!GetWindowLongPtrW` at `0x1800ad7cd`
- `USER32!GetWindowLongPtrW` at `0x1800ad829`
- `USER32!GetWindowLongPtrW` at `0x1800ad903`
- `USER32!GetWindowLongPtrW` at `0x1800adb85`
- `USER32!GetWindowLongPtrW` at `0x1800ad2a0`
- `USER32!GetWindowLongPtrW` at `0x1800ad2c0`
- `USER32!GetWindowLongPtrW` at `0x1800ad2d6`
- `USER32!GetWindowLongPtrW` at `0x1800ad713`
- `USER32!GetWindowLongPtrW` at `0x1800ad7cd`
- `USER32!GetWindowLongPtrW` at `0x1800ad829`
- `USER32!GetWindowLongPtrW` at `0x1800ad903`
- `USER32!GetWindowLongPtrW` at `0x1800adb85`
- `USER32!GetWindowThreadProcessId` at `0x1800ad40b`
- `USER32!GetWindowThreadProcessId` at `0x1800ad511`
- `USER32!GetWindowThreadProcessId` at `0x1800ad40b`
- `USER32!GetWindowThreadProcessId` at `0x1800ad511`
- `USER32!GetWindow` at `0x1800ad2e9`
- `USER32!GetWindow` at `0x1800ad67e`
- `USER32!GetWindow` at `0x1800ad2e9`
- `USER32!GetWindow` at `0x1800ad67e`
- `USER32!IsIconic` at `0x1800ad451`
- `USER32!IsIconic` at `0x1800ad451`
- `USER32!BeginDeferWindowPos` at `0x1800ace8e`
- `USER32!BeginDeferWindowPos` at `0x1800ace8e`
- `USER32!GetGUIThreadInfo` at `0x1800ada6a`
- `USER32!GetGUIThreadInfo` at `0x1800ada6a`
- `USER32!DeferWindowPos` at `0x1800add0d`
- `USER32!DeferWindowPos` at `0x1800add0d`
- `USER32!EndDeferWindowPos` at `0x1800add8c`
- `USER32!EndDeferWindowPos` at `0x1800add8c`
- `USER32!IsWindowVisible` at `0x1800acf19`
- `USER32!IsWindowVisible` at `0x1800ad1eb`
- `USER32!IsWindowVisible` at `0x1800acf19`
- `USER32!IsWindowVisible` at `0x1800ad1eb`
- `USER32!GetForegroundWindow` at `0x1800ad400`
- `USER32!GetForegroundWindow` at `0x1800ad506`
- `USER32!GetForegroundWindow` at `0x1800ad400`
- `USER32!GetForegroundWindow` at `0x1800ad506`

## string_xrefs

- `0x1800ad9b8`: `Remove SWP_NOOWNERZORDER on window`

## pseudocode

```c
__int64 __fastcall WindowsRemoteAppLib::CWinManager::DoZorder(WindowsRemoteAppLib::CWinManager *this)
{
  __int64 v2; // rbx
  __int64 v3; // rsi
  struct WindowsRemoteAppLib::CRailUi *v4; // rdi
  __int64 v5; // rcx
  signed int LocalZOrder; // r15d
  int v7; // r8d
  int v8; // r9d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v10; // edx
  const char *v11; // rcx
  int RailUi; // eax
  unsigned int v13; // eax
  int v14; // r8d
  int v15; // r9d
  HDWP v16; // r14
  unsigned int v17; // eax
  __int64 v18; // rdx
  unsigned __int8 v19; // dl
  int v20; // eax
  __int64 v21; // r14
  int v22; // eax
  int v23; // r8d
  int v24; // r9d
  struct WindowsRemoteAppLib::CRailUi *v25; // r14
  int v26; // r8d
  int v27; // r9d
  unsigned int v28; // eax
  char *v29; // rdx
  const char *v30; // rax
  int v31; // eax
  HWND v32; // r14
  int v33; // r8d
  int v34; // r9d
  unsigned int v35; // eax
  LONG_PTR WindowLongPtrW; // r14
  HWND Window; // rax
  HWND v38; // rdx
  const char *v39; // rcx
  int v40; // r8d
  int v41; // r9d
  HWND ForegroundWindow; // rax
  DWORD WindowThreadProcessId; // r14d
  DWORD CurrentThreadId; // eax
  int v45; // r8d
  int v46; // r9d
  HWND v47; // rax
  DWORD v48; // r14d
  DWORD v49; // eax
  int v50; // r8d
  int v51; // r9d
  int v52; // ecx
  int v53; // r8d
  int v54; // r9d
  WindowsRemoteAppLib::CWinManager *v55; // rcx
  unsigned int v56; // r8d
  HWND PrevVisibleWindow; // rax
  unsigned int v58; // r8d
  int v59; // r9d
  HWND v60; // r14
  int v61; // r14d
  unsigned __int64 v62; // rax
  BOOL v63; // r14d
  WindowsRemoteAppLib::CWinManager *v64; // rcx
  HWND v65; // r14
  const char *v66; // rax
  __int16 *v67; // rdx
  HWND v68; // rax
  __int64 AppIdForRailWindow; // rax
  bool v70; // r14
  unsigned int v71; // r8d
  int v72; // r9d
  BOOL GUIThreadInfo; // eax
  WindowsRemoteAppLib::CWinManager *v74; // rcx
  HWND v75; // rax
  HWND v76; // r14
  int *v77; // rdx
  const char *v78; // rax
  __int64 v79; // r14
  HWND v80; // r14
  int v81; // r8d
  int v82; // r9d
  int v83; // r14d
  unsigned int v84; // eax
  int v85; // r8d
  int v86; // r9d
  int v87; // ebx
  unsigned int v88; // eax
  int v90[2]; // [rsp+28h] [rbp-D8h]
  int v91; // [rsp+70h] [rbp-90h] BYREF
  int v92; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int8 v93; // [rsp+78h] [rbp-88h]
  const char *v94; // [rsp+80h] [rbp-80h] BYREF
  int v95; // [rsp+88h] [rbp-78h]
  __int64 v96; // [rsp+90h] [rbp-70h] BYREF
  HWND hWnd; // [rsp+98h] [rbp-68h]
  const char *v98; // [rsp+A0h] [rbp-60h] BYREF
  UINT uFlags; // [rsp+A8h] [rbp-58h] BYREF
  BOOL v100; // [rsp+ACh] [rbp-54h]
  HDWP hWinPosInfo; // [rsp+B0h] [rbp-50h] BYREF
  HWND v102; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v103; // [rsp+C0h] [rbp-40h]
  int v104; // [rsp+C8h] [rbp-38h]
  HWND hWndInsertAfter; // [rsp+D0h] [rbp-30h]
  int v106; // [rsp+D8h] [rbp-28h]
  const char *v107; // [rsp+E0h] [rbp-20h] BYREF
  HWND v108; // [rsp+E8h] [rbp-18h] BYREF
  LONG_PTR v109; // [rsp+F0h] [rbp-10h]
  int v110; // [rsp+F8h] [rbp-8h]
  int v111; // [rsp+FCh] [rbp-4h] BYREF
  __int64 v112; // [rsp+100h] [rbp+0h] BYREF
  int v113; // [rsp+108h] [rbp+8h]
  HWND v114; // [rsp+110h] [rbp+10h] BYREF
  int v115; // [rsp+11Ch] [rbp+1Ch]
  struct WindowsRemoteAppLib::CRailUi *v116; // [rsp+130h] [rbp+30h] BYREF
  __int64 v117; // [rsp+138h] [rbp+38h] BYREF
  int v118; // [rsp+140h] [rbp+40h] BYREF
  int v119; // [rsp+144h] [rbp+44h] BYREF
  int v120; // [rsp+148h] [rbp+48h] BYREF
  int v121; // [rsp+14Ch] [rbp+4Ch] BYREF
  int v122; // [rsp+150h] [rbp+50h] BYREF
  int v123; // [rsp+154h] [rbp+54h] BYREF
  int v124; // [rsp+158h] [rbp+58h] BYREF
  struct WindowsRemoteAppLib::CRailUi *v125; // [rsp+160h] [rbp+60h] BYREF
  int v126; // [rsp+168h] [rbp+68h] BYREF
  int v127; // [rsp+16Ch] [rbp+6Ch] BYREF
  __m128i si128; // [rsp+170h] [rbp+70h] BYREF
  __int64 v129; // [rsp+180h] [rbp+80h]
  _DWORD v130[4]; // [rsp+188h] [rbp+88h] BYREF
  HWND v131; // [rsp+198h] [rbp+98h] BYREF
  int v132; // [rsp+1A4h] [rbp+A4h]
  HWND v133; // [rsp+1A8h] [rbp+A8h] BYREF
  int v134; // [rsp+1B4h] [rbp+B4h]
  _BYTE v135[40]; // [rsp+1B8h] [rbp+B8h] BYREF
  struct tagGUITHREADINFO pgui; // [rsp+1E0h] [rbp+E0h] BYREF

  v2 = 0;
  v106 = 0;
  v112 = 0;
  v3 = 0;
  v117 = 0;
  TCntPtr<IPin>::SafeAddRef(&v112);
  v4 = 0;
  v125 = 0;
  v129 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  if ( (unsigned int)dword_1808B7630 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1808B7630,
      &dword_1808645BC);
  if ( !(unsigned int)WindowsRemoteAppLib::CWinManager::CheckZOrder(this) )
  {
    LocalZOrder = 1;
    goto LABEL_215;
  }
  LocalZOrder = WindowsRemoteAppLib::CWinManager::GetLocalZOrder(v5, &si128);
  if ( LocalZOrder < 0
    && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      (unsigned int)WPP_5f7999f72f073c88df0000a8d4f05f34_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)"GetLocalZOrder failed",
      LocalZOrder);
  }
  v10 = *((_DWORD *)this + 630);
  v11 = "DoZorder";
  if ( v10 == -1 )
  {
    if ( (unsigned int)dword_1808B5850 > 4 )
    {
      v92 = *((_DWORD *)this + 630);
      v98 = "Found active window in Z-order";
      hWinPosInfo = "DoZorder";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)"DoZorder",
        (unsigned int)byte_1808645E1,
        v7,
        v8,
        (__int64)&v98,
        (__int64)&hWinPosInfo,
        (__int64)&v92);
    }
    v95 = 1;
  }
  else
  {
    v95 = 0;
    if ( v10 )
    {
      v7 = *((unsigned __int8 *)this + 2512);
      if ( *((_BYTE *)this + 2512) )
      {
        LODWORD(v11) = 0;
        while ( *((_DWORD *)this + (unsigned int)v11 + 372) != v10 )
        {
          LODWORD(v11) = (_DWORD)v11 + 1;
          if ( (int)v11 >= v7 )
            goto LABEL_27;
        }
        LODWORD(v114) = v10;
        v115 = 1;
        RailUi = WindowsRemoteAppLib::CRailUiManager::FindRailUi(
                   this,
                   (const struct WindowsRemoteAppLib::CRailUiId *)&v114,
                   &v125);
        v4 = v125;
        LocalZOrder = RailUi;
        if ( RailUi >= 0 )
        {
          if ( IsWindowVisible(*((HWND *)v125 + 6)) )
          {
            if ( (unsigned int)dword_1808B5850 > 4 )
            {
              v92 = *((_DWORD *)this + 630);
              hWinPosInfo = "DoZorder";
              v98 = "Found active window in Z-order";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                (_DWORD)v11,
                (unsigned int)byte_180864619,
                v7,
                v8,
                (__int64)&v98,
                (__int64)&hWinPosInfo,
                (__int64)&v92);
            }
            v95 = 1;
            goto LABEL_30;
          }
        }
        else
        {
          v11 = (const char *)&WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v13 = RdpWppGetCurrentThreadActivityIdPrefix();
            v90[0] = LocalZOrder;
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              33,
              (unsigned int)WPP_5f7999f72f073c88df0000a8d4f05f34_Traceguids,
              v13,
              (__int64)"FindRailUi failed",
              *(_QWORD *)v90);
          }
        }
        if ( (unsigned int)dword_1808B5850 > 3 )
        {
          v92 = *((_DWORD *)this + 630);
          hWinPosInfo = "Found active window in Z-order, but it is invisible or suppressed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1808B5850,
            (unsigned int)word_1808644F2,
            v7,
            v8,
            (__int64)&hWinPosInfo,
            (__int64)&v92);
        }
LABEL_27:
        v95 = 0;
      }
    }
    if ( (unsigned int)dword_1808B5850 > 3 )
    {
      v92 = *((_DWORD *)this + 630);
      hWinPosInfo = "Unable to find active window in Z-order";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1808B5850,
        (unsigned int)qword_180864520,
        v7,
        v8,
        (__int64)&hWinPosInfo,
        (__int64)&v92);
    }
  }
LABEL_30:
  if ( (unsigned int)dword_1808B5850 > 4 )
  {
    v92 = *((unsigned __int8 *)this + 2512);
    v98 = "Beginning Z-order processing of windows";
    hWinPosInfo = "DoZorder";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)v11,
      (unsigned int)&word_18086454E,
      v7,
      v8,
      (__int64)&v98,
      (__int64)&hWinPosInfo,
      (__int64)&v92);
  }
  hWinPosInfo = BeginDeferWindowPos(*((unsigned __int8 *)this + 2512));
  v16 = hWinPosInfo;
  if ( !hWinPosInfo )
  {
    LocalZOrder = GetLastError();
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_38;
    }
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 34;
    goto LABEL_37;
  }
  hWndInsertAfter = 0;
  v19 = 0;
  v104 = 0;
  v110 = 0;
  v113 = 0;
  v93 = 0;
  if ( !*((_BYTE *)this + 2512) )
  {
LABEL_182:
    if ( EndDeferWindowPos(v16) )
    {
      if ( v2 )
      {
        if ( (unsigned int)dword_1808B5850 > 5 )
        {
          v111 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 48LL))(v2);
          v114 = (HWND)"Restoring server activation for window";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1808B5850,
            (unsigned int)&byte_180863FBF,
            v85,
            v86,
            (__int64)&v114,
            (__int64)&v111);
        }
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v2 + 80LL))(v2, 0);
      }
      v87 = WindowsRemoteAppLib::CWinManager::VerifyZOrder(this);
      if ( v87 < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v88 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_5f7999f72f073c88df0000a8d4f05f34_Traceguids, v88, v87);
      }
      goto LABEL_215;
    }
    LocalZOrder = GetLastError();
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_38:
      if ( LocalZOrder > 0 )
        LocalZOrder = (unsigned __int16)LocalZOrder | 0x80070000;
      if ( LocalZOrder >= 0 )
        LocalZOrder = -2147467259;
      goto LABEL_215;
    }
    v17 = RdpWppGetCurrentThreadActivityIdPrefix();
    v18 = 37;
LABEL_37:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      WPP_5f7999f72f073c88df0000a8d4f05f34_Traceguids,
      v17,
      LocalZOrder);
    goto LABEL_38;
  }
  while ( 1 )
  {
    v20 = *((_DWORD *)this + 629);
    v116 = 0;
    v96 = 0;
    if ( v20 && *((_DWORD *)this + v19 + 372) == v20 )
    {
      v104 = 1;
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        v92 = *((_DWORD *)this + v19 + 372);
        v98 = "DoZorder";
        v108 = (HWND)"Found marker window in Z-order";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v19,
          (unsigned int)qword_180864468,
          v14,
          v15,
          (__int64)&v108,
          (__int64)&v98,
          (__int64)&v92);
      }
      goto LABEL_178;
    }
    v21 = v19 + 372LL;
    v130[3] = 1;
    v103 = v21;
    v130[0] = *((_DWORD *)this + v21);
    v22 = WindowsRemoteAppLib::CRailUiManager::FindRailUi(
            this,
            (const struct WindowsRemoteAppLib::CRailUiId *)v130,
            &v116);
    if ( v22 < 0 )
    {
      if ( (unsigned int)dword_1808B5850 > 3 )
      {
        v92 = v22;
        uFlags = *((_DWORD *)this + v21);
        v98 = "Missing proxy window for window in Z-order list";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          dword_1808B5850,
          (unsigned int)byte_18086449B,
          v23,
          v24,
          (__int64)&v98,
          (__int64)&uFlags,
          (__int64)&v92);
      }
      goto LABEL_178;
    }
    v25 = v116;
    LocalZOrder = (*(__int64 (__fastcall **)(struct WindowsRemoteAppLib::CRailUi *, __int64 *))(*(_QWORD *)v116 + 32LL))(
                    v116,
                    &v96);
    if ( LocalZOrder < 0
      && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v28 = RdpWppGetCurrentThreadActivityIdPrefix();
      v90[0] = LocalZOrder;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        (unsigned int)WPP_5f7999f72f073c88df0000a8d4f05f34_Traceguids,
        v28,
        (__int64)"GetWindowInterface failed unexpectedly",
        *(_QWORD *)v90);
    }
    if ( !v96 )
    {
      if ( (unsigned int)dword_1808B5850 <= 3 )
        goto LABEL_178;
      v29 = byte_1808644C9;
      v92 = *((_DWORD *)this + v103);
      v30 = "GetWindowInterface returned null for window in Z-order list";
      goto LABEL_63;
    }
    v31 = *((_DWORD *)this + 630);
    v26 = v110;
    v32 = (HWND)*((_QWORD *)v25 + 6);
    hWnd = v32;
    if ( *((_DWORD *)this + v103) == v31 )
      v26 = 1;
    v110 = v26;
    if ( v32 )
      break;
    if ( (unsigned int)dword_1808B5850 > 3 )
    {
      v29 = byte_180864339;
      v92 = *((_DWORD *)this + v103);
      v30 = "hWnd is NULL for RAIL window";
LABEL_63:
      v98 = v30;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1808B5850,
        (_DWORD)v29,
        v26,
        v27,
        (__int64)&v98,
        (__int64)&v92);
    }
LABEL_178:
    if ( v96 != v3 )
    {
      TCntPtr<ITSViewerRecorder>::SafeRelease(&v117);
      v3 = v96;
      v117 = v96;
      TCntPtr<IPin>::SafeAddRef(&v117);
    }
LABEL_180:
    TCntPtr<ITSViewerRecorder>::SafeRelease(&v96);
    TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v116);
    v19 = v93 + 1;
    v93 = v19;
    if ( v19 >= *((_BYTE *)this + 2512) )
    {
      v16 = hWinPosInfo;
      goto LABEL_182;
    }
  }
  if ( !IsWindowVisible(v32) )
  {
    if ( (unsigned int)dword_1808B5850 > 5 )
    {
      v126 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v96 + 40LL))(v96);
      v98 = *(const char **)WindowsRemoteAppLib::CWinManager::GetWindowTitleForRailWindow(&v114, v96);
      v124 = (int)v32;
      v123 = *((_DWORD *)this + v103);
      v108 = (HWND)"Skipping invisible window";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v98,
        (unsigned int)word_180864362,
        v33,
        v34,
        (__int64)&v108,
        (__int64)&v123,
        (__int64)&v124,
        (__int64)&v98,
        (__int64)&v126);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v114);
    }
    goto LABEL_180;
  }
  v35 = GetWindowLongPtrW(v32, -20) & 8;
  v98 = (const char *)v35;
  v100 = v35 != 0;
  WindowLongPtrW = GetWindowLongPtrW(v32, -16);
  v108 = (HWND)WindowLongPtrW;
  v109 = GetWindowLongPtrW(hWnd, -20);
  Window = GetWindow(hWnd, 3u);
  v38 = Window;
  v114 = Window;
  if ( (unsigned int)dword_1808B5850 > 5 )
  {
    v91 = (int)Window;
    v92 = v109;
    LODWORD(v102) = v100;
    uFlags = WindowLongPtrW;
    v122 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v96 + 40LL))(v96);
    v39 = *(const char **)WindowsRemoteAppLib::CWinManager::GetWindowTitleForRailWindow(v135, v96);
    v120 = (int)hWnd;
    v107 = v39;
    v121 = *((_DWORD *)this + v103);
    v94 = "Evaluating window";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v39,
      (unsigned int)&byte_1808643AF,
      v40,
      v41,
      (__int64)&v94,
      (__int64)&v121,
      (__int64)&v120,
      (__int64)&v107,
      (__int64)&v122,
      (__int64)&v91,
      (__int64)&v102,
      (__int64)&uFlags,
      (__int64)&v92);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v135);
  }
  if ( !v113 && !v104 && !v95 )
  {
    if ( *((_DWORD *)this + 629) )
    {
      ForegroundWindow = GetForegroundWindow();
      WindowThreadProcessId = GetWindowThreadProcessId(ForegroundWindow, 0);
      CurrentThreadId = GetCurrentThreadId();
      if ( (!CurrentThreadId || CurrentThreadId != WindowThreadProcessId)
        && !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v96 + 40LL))(v96)
        && (v109 & 0x8000000) == 0
        && !IsIconic(hWnd)
        && (v109 & 0x80u) == 0LL )
      {
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          LODWORD(v102) = (_DWORD)v108;
          v91 = v109;
          v92 = *((_DWORD *)this + v103);
          v94 = "DoZorder";
          v107 = "Immediately setting foreground";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v109,
            (unsigned int)byte_180864425,
            v45,
            v46,
            (__int64)&v107,
            (__int64)&v94,
            (__int64)&v92,
            (__int64)&v102,
            (__int64)&v91);
        }
        v113 = 1;
        goto LABEL_190;
      }
    }
  }
  if ( !v93 && (*(unsigned int (__fastcall **)(__int64, HWND))(*(_QWORD *)v96 + 56LL))(v96, v38) )
  {
    v47 = GetForegroundWindow();
    v48 = GetWindowThreadProcessId(v47, 0);
    v49 = GetCurrentThreadId();
    if ( (!v49 || v49 != v48)
      && !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v96 + 40LL))(v96)
      && (v109 & 0x8000000) == 0
      && ((*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v96 + 72LL))(v96) || (v109 & 0x80u) == 0LL) )
    {
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        LODWORD(v102) = (_DWORD)v108;
        v91 = v109;
        v92 = *((_DWORD *)this + v103);
        v94 = "DoZorder";
        v107 = "Immediately setting foreground for this first-show window";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v109,
          (unsigned int)qword_180864288,
          v50,
          v51,
          (__int64)&v107,
          (__int64)&v94,
          (__int64)&v92,
          (__int64)&v102,
          (__int64)&v91);
      }
      goto LABEL_190;
    }
    if ( (unsigned int)dword_1808B5850 > 5 )
    {
      v119 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v96 + 72LL))(v96);
      v118 = v109;
      v127 = (int)v108;
      v111 = *((_DWORD *)this + v103);
      v94 = "Not setting foreground for this first-show window";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v52,
        (unsigned int)byte_1808642CB,
        v53,
        v54,
        (__int64)&v94,
        (__int64)&v111,
        (__int64)&v127,
        (__int64)&v118,
        (__int64)&v119);
    }
  }
  uFlags = 787;
  v92 = 0;
  v108 = GetWindow(hWnd, 6u);
  PrevVisibleWindow = WindowsRemoteAppLib::CWinManager::FindPrevVisibleWindow(v55, hWnd, v56);
  v60 = PrevVisibleWindow;
  v102 = PrevVisibleWindow;
  if ( (unsigned int)dword_1808B5850 > 5 )
  {
    v91 = (int)PrevVisibleWindow;
    v94 = "Previous Visible Window";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1808B5850,
      (unsigned int)&dword_180864314,
      v58,
      v59,
      (__int64)&v94,
      (__int64)&v91);
  }
  if ( !v60 )
    goto LABEL_111;
  if ( v3 )
  {
    v61 = *((_DWORD *)this + v103);
    if ( v61 != (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v3 + 40LL))(v3) )
    {
      v60 = v102;
      goto LABEL_106;
    }
LABEL_111:
    v63 = v100;
    goto LABEL_112;
  }
LABEL_106:
  v62 = GetWindowLongPtrW(v60, -20);
  v63 = v100;
  if ( v100 == ((v62 >> 3) & 1) )
  {
    v131 = v102;
    v132 = 3;
    if ( (int)WindowsRemoteAppLib::CRailUiManager::FindRailUi(
                this,
                (const struct WindowsRemoteAppLib::CRailUiId *)&v131,
                0) < 0 )
    {
      v64 = (WindowsRemoteAppLib::CWinManager *)v102;
      v65 = v102;
      hWndInsertAfter = v102;
      v100 = 1;
      if ( (unsigned int)dword_1808B5850 <= 5 )
        goto LABEL_120;
      v91 = (int)v102;
      v66 = "Under local window";
      v67 = (__int16 *)&byte_1808641CF;
      goto LABEL_110;
    }
  }
LABEL_112:
  v64 = (WindowsRemoteAppLib::CWinManager *)hWndInsertAfter;
  v100 = 0;
  if ( hWndInsertAfter )
  {
    if ( v63 == (((unsigned __int64)GetWindowLongPtrW(hWndInsertAfter, -20) >> 3) & 1) )
    {
      v65 = hWndInsertAfter;
      if ( (GetWindowLongPtrW(hWndInsertAfter, -16) & 0x20000000) == 0 || (unsigned int)dword_1808B5850 <= 5 )
        goto LABEL_120;
      v91 = (int)v65;
      v66 = "Under minimized window";
      v67 = &word_18086421E;
LABEL_110:
      v94 = v66;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1808B5850,
        (_DWORD)v67,
        v58,
        v59,
        (__int64)&v94,
        (__int64)&v91);
      goto LABEL_120;
    }
    v65 = 0;
    hWndInsertAfter = 0;
    if ( (unsigned int)dword_1808B5850 > 5 )
    {
      v94 = "Placing under HWND_TOP";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_1808B5850,
        (unsigned int)&byte_1808641FF,
        0,
        v59,
        (__int64)&v94);
    }
  }
  else
  {
    v65 = 0;
  }
LABEL_120:
  if ( (!*((_DWORD *)this + 629) || !v104) && !v110 )
  {
    if ( v4 )
    {
      if ( WindowsRemoteAppLib::CWinManager::IsWindowUnderWindow(v64, v65, *((HWND *)v4 + 6)) )
      {
        v68 = WindowsRemoteAppLib::CWinManager::FindPrevVisibleWindow(v64, *((HWND *)v4 + 6), v58);
        LODWORD(v64) = dword_1808B5850;
        v65 = v68;
        hWndInsertAfter = v68;
        if ( (unsigned int)dword_1808B5850 > 4 )
        {
          v91 = (int)v68;
          v94 = "DoZorder";
          v107 = "Bumping above active window";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            dword_1808B5850,
            (unsigned int)&word_18086424E,
            v58,
            v59,
            (__int64)&v107,
            (__int64)&v94,
            (__int64)&v91);
        }
      }
    }
  }
  if ( v65 )
  {
    if ( (GetWindowLongPtrW(v65, -20) & 8) != 0 )
    {
      if ( !v98 )
      {
        LODWORD(v64) = 0;
        hWndInsertAfter = 0;
      }
    }
    else if ( !v98 )
    {
      goto LABEL_148;
    }
  }
  else if ( v98 )
  {
    hWndInsertAfter = HWND_MESSAGE|0x2LL;
  }
  if ( !v108 || hWnd == v108 )
  {
    v70 = 1;
    if ( *((_BYTE *)this + 1472) )
    {
      v106 |= 1u;
      AppIdForRailWindow = WindowsRemoteAppLib::CWinManager::GetAppIdForRailWindow(v135, v96);
      if ( !(unsigned __int8)utl::operator==<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(
                               AppIdForRailWindow,
                               L"Microsoft.Windows.ControlPanel") )
        v70 = 0;
    }
    if ( (v106 & 1) != 0 )
    {
      v106 &= ~1u;
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v135);
    }
    if ( v70 )
    {
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        v91 = (int)hWnd;
        v94 = "DoZorder";
        v107 = "Remove SWP_NOOWNERZORDER on window";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)v64,
          (unsigned int)&dword_18086413C,
          v58,
          v59,
          (__int64)&v107,
          (__int64)&v94,
          (__int64)&v91);
      }
      uFlags = 275;
    }
    else if ( (unsigned int)dword_1808B5850 > 5 )
    {
      v91 = (int)hWnd;
      v94 = "SWP_NOOWNERZORDER suppression skipped for window";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1808B5850,
        (unsigned int)byte_180864171,
        v58,
        v59,
        (__int64)&v94,
        (__int64)&v91);
    }
  }
LABEL_148:
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v96 + 72LL))(v96) )
  {
    memset_0(&pgui, 0, sizeof(pgui));
    pgui.cbSize = 72;
    GUIThreadInfo = GetGUIThreadInfo(0, &pgui);
    LODWORD(v74) = (_DWORD)hWnd;
    if ( GUIThreadInfo && pgui.hwndActive && hWnd == pgui.hwndActive )
      goto LABEL_171;
    if ( v100 )
    {
      v75 = WindowsRemoteAppLib::CWinManager::FindPrevVisibleWindow((WindowsRemoteAppLib::CWinManager *)hWnd, v114, v71);
      v76 = v75;
      if ( *((_DWORD *)this + 629)
        || v75
        && !WindowsRemoteAppLib::CWinManager::IsTooltipWindow(v74, v75)
        && (v133 = v76,
            v134 = 3,
            (int)WindowsRemoteAppLib::CRailUiManager::FindRailUi(
                   this,
                   (const struct WindowsRemoteAppLib::CRailUiId *)&v133,
                   0) < 0) )
      {
        if ( v104 )
        {
          if ( (unsigned int)dword_1808B5850 > 5 )
          {
            v91 = (int)v76;
            v114 = (HWND)"Previous Visible Window";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1808B5850,
              (unsigned int)byte_1808640BB,
              v71,
              v72,
              (__int64)&v114,
              (__int64)&v91);
          }
          goto LABEL_177;
        }
        if ( (unsigned int)dword_1808B5850 <= 4 )
        {
LABEL_190:
          if ( (v109 & 0x8000000) == 0 )
          {
            v83 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v96 + 72LL))(v96);
            if ( v83 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v96 + 80LL))(v96, 1);
            if ( (unsigned int)dword_1808B5850 > 4 )
            {
              v91 = (int)hWnd;
              v114 = (HWND)"DoZorder";
              v94 = "SetWindowToForeground";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                dword_1808B5850,
                (unsigned int)&byte_180864087,
                v81,
                v82,
                (__int64)&v94,
                (__int64)&v114,
                (__int64)&v91);
            }
            WindowsRemoteAppLib::CWinManager::SetWindowToForeground(this, hWnd);
            if ( v83 )
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v96 + 80LL))(v96, 0);
          }
LABEL_177:
          hWndInsertAfter = hWnd;
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v96 + 64LL))(v96, 0);
          goto LABEL_178;
        }
        v77 = &dword_18086419C;
        v91 = *((_DWORD *)this + v103);
        v114 = (HWND)"DoZorder";
        v78 = "Marker window not seen yet; setting window to foreground";
LABEL_189:
        v94 = v78;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)v74,
          (_DWORD)v77,
          v71,
          v72,
          (__int64)&v94,
          (__int64)&v114,
          (__int64)&v91);
        goto LABEL_190;
      }
    }
    else
    {
      if ( !v93 || (GetWindowLongPtrW(hWnd, -20) & 8) != 0 )
      {
        if ( (unsigned int)dword_1808B5850 <= 4 )
          goto LABEL_190;
        v77 = (int *)byte_18086400D;
        v91 = *((_DWORD *)this + v103);
        v114 = (HWND)"DoZorder";
        v78 = "Setting window to foreground";
        goto LABEL_189;
      }
      v79 = v103;
      if ( (unsigned int)dword_1808B5850 > 4 )
      {
        v91 = *((_DWORD *)this + v103);
        v114 = (HWND)"DoZorder";
        v94 = "Activating window";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)v74,
          (unsigned int)qword_1808640E0,
          v71,
          v72,
          (__int64)&v94,
          (__int64)&v114,
          (__int64)&v91);
      }
      uFlags &= ~0x10u;
      v92 = 1;
      if ( v96 != v2 )
      {
        TCntPtr<ITSViewerRecorder>::SafeRelease(&v112);
        v2 = v96;
        v112 = v96;
        TCntPtr<IPin>::SafeAddRef(&v112);
      }
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 80LL))(v2, 1);
      if ( (unsigned int)dword_1808B5850 > 5 )
      {
        v91 = *((_DWORD *)this + v79);
        v114 = (HWND)"Suppressing server activation because window should be active as per z-order";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1808B5850,
          (unsigned int)byte_180864113,
          v71,
          v72,
          (__int64)&v114,
          (__int64)&v91);
      }
    }
  }
  LODWORD(v74) = (_DWORD)hWnd;
LABEL_171:
  if ( v104 )
    goto LABEL_177;
  v80 = hWndInsertAfter;
  if ( hWndInsertAfter == v102 && !v92 )
    goto LABEL_177;
  if ( (unsigned int)dword_1808B5850 > 4 )
  {
    v91 = (int)hWndInsertAfter;
    v114 = (HWND)"DoZorder";
    LODWORD(v102) = (_DWORD)v74;
    v94 = "Positioning window with DeferWindowPos";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)v74,
      (unsigned int)qword_180864040,
      v71,
      v72,
      (__int64)&v94,
      (__int64)&v114,
      (__int64)&v102,
      (__int64)&v91);
  }
  hWinPosInfo = DeferWindowPos(hWinPosInfo, hWnd, v80, 0, 0, 0, 0, uFlags);
  if ( hWinPosInfo )
    goto LABEL_177;
  LocalZOrder = GetLastError();
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v84 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      36,
      WPP_5f7999f72f073c88df0000a8d4f05f34_Traceguids,
      v84,
      LocalZOrder);
  }
  if ( LocalZOrder > 0 )
    LocalZOrder = (unsigned __int16)LocalZOrder | 0x80070000;
  if ( LocalZOrder >= 0 )
    LocalZOrder = -2147467259;
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v96);
  TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v116);
LABEL_215:
  if ( (unsigned int)dword_1808B7630 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1808B7630,
      qword_180863FE8);
  utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(&si128);
  TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v125);
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v112);
  TCntPtr<ITSViewerRecorder>::SafeRelease(&v117);
  return (unsigned int)LocalZOrder;
}

```

## disassembly

```asm
0x1800acb6c  push    rbp
0x1800acb6e  push    rbx
0x1800acb6f  push    rsi
0x1800acb70  push    rdi
0x1800acb71  push    r12
0x1800acb73  push    r13
0x1800acb75  push    r14
0x1800acb77  push    r15
0x1800acb79  lea     rbp, [rsp-148h]
0x1800acb81  sub     rsp, 248h
0x1800acb88  mov     rax, cs:__security_cookie
0x1800acb8f  xor     rax, rsp
0x1800acb92  mov     [rbp+180h+var_50], rax
0x1800acb99  xor     r14d, r14d
0x1800acb9c  mov     r12, rcx
0x1800acb9f  mov     ebx, r14d
0x1800acba2  mov     [rbp+180h+var_1A8], r14d
0x1800acba6  lea     rcx, [rbp+180h+var_180]
0x1800acbaa  mov     [rbp+180h+var_180], rbx
0x1800acbae  mov     esi, r14d
0x1800acbb1  mov     [rbp+180h+var_148], r14
0x1800acbb5  call    ?SafeAddRef@?$TCntPtr@UIPin@@@@AEAAXXZ
0x1800acbba  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800acbc2  mov     edi, r14d
0x1800acbc5  mov     eax, cs:dword_1808B7630
0x1800acbcb  mov     [rbp+180h+var_120], r14
0x1800acbcf  mov     [rbp+180h+var_100], 0FFFFFFFFFFFFFFFFh
0x1800acbda  movdqu  [rbp+180h+var_110], xmm0
0x1800acbdf  cmp     eax, 5
0x1800acbe2  jbe     short loc_1800ACBF7
0x1800acbe4  lea     rdx, dword_1808645BC
0x1800acbeb  lea     rcx, dword_1808B7630
0x1800acbf2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z
0x1800acbf7  mov     rcx, r12; this
0x1800acbfa  call    ?CheckZOrder@CWinManager@WindowsRemoteAppLib@@IEAAHXZ
0x1800acbff  test    eax, eax
0x1800acc01  jnz     short loc_1800ACC0C
0x1800acc03  lea     r15d, [rax+1]
0x1800acc07  jmp     loc_1800AE029
0x1800acc0c  lea     rdx, [rbp+180h+var_110]
0x1800acc10  call    ?GetLocalZOrder@CWinManager@WindowsRemoteAppLib@@IEAAJAEAV?$vector@PEAUHWND__@@V?$allocator@PEAUHWND__@@@utl@@@utl@@@Z
0x1800acc15  lea     rcx, WPP_GLOBAL_Control
0x1800acc1c  mov     r15d, eax
0x1800acc1f  test    eax, eax
0x1800acc21  jns     short loc_1800ACC70
0x1800acc23  mov     rax, cs:WPP_GLOBAL_Control
0x1800acc2a  cmp     rax, rcx
0x1800acc2d  jz      short loc_1800ACC70
0x1800acc2f  test    byte ptr [rax+1Ch], 8
0x1800acc33  jz      short loc_1800ACC70
0x1800acc35  cmp     byte ptr [rax+19h], 2
0x1800acc39  jb      short loc_1800ACC70
0x1800acc3b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ
0x1800acc40  lea     rcx, aGetlocalzorder
0x1800acc47  mov     [rsp+280h+var_258], r15d
0x1800acc4c  mov     qword ptr [rsp+280h+y], rcx
0x1800acc51  lea     r8, WPP_5f7999f72f073c88df0000a8d4f05f34_Traceguids
0x1800acc58  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acc5f  mov     edx, 20h ; ' '
0x1800acc64  mov     r9d, eax
0x1800acc67  mov     rcx, [rcx+10h]
0x1800acc6b  call    WPP_SF_DsD
0x1800acc70  mov     edx, [r12+9D8h]
0x1800acc78  lea     rcx, aDozorder
0x1800acc7f  cmp     edx, 0FFFFFFFFh
0x1800acc82  jnz     short loc_1800ACCE1
0x1800acc84  mov     eax, cs:dword_1808B5850
0x1800acc8a  cmp     eax, 4
0x1800acc8d  jbe     short loc_1800ACCD2
0x1800acc8f  mov     eax, [r12+9D8h]
0x1800acc97  lea     rdx, byte_1808645E1
0x1800acc9e  mov     [rsp+280h+var_20C], eax
0x1800acca2  lea     rax, aFoundActiveWin
0x1800acca9  mov     [rbp+180h+var_1E0], rax
0x1800accad  lea     rax, [rsp+280h+var_20C]
0x1800accb2  mov     qword ptr [rsp+280h+cy], rax
0x1800accb7  lea     rax, [rbp+180h+hWinPosInfo]
0x1800accbb  mov     qword ptr [rsp+280h+var_258], rax
0x1800accc0  lea     rax, [rbp+180h+var_1E0]
0x1800accc4  mov     qword ptr [rsp+280h+y], rax
0x1800accc9  mov     [rbp+180h+hWinPosInfo], rcx
0x1800acccd  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z
0x1800accd2  mov     r13d, 1
0x1800accd8  mov     [rbp+180h+var_1F8], r13d
0x1800accdc  jmp     loc_1800ACE2F
0x1800acce1  mov     [rbp+180h+var_1F8], r14d
0x1800acce5  mov     r13d, 1
0x1800acceb  test    edx, edx
0x1800acced  jz      loc_1800ACDE7
0x1800accf3  movzx   r8d, byte ptr [r12+9D0h]
0x1800accfc  test    r8d, r8d
0x1800accff  jz      loc_1800ACDE7
0x1800acd05  mov     ecx, r14d
0x1800acd08  mov     eax, ecx
0x1800acd0a  cmp     [r12+rax*4+5D0h], edx
0x1800acd12  jz      short loc_1800ACD21
0x1800acd14  add     ecx, r13d
0x1800acd17  cmp     ecx, r8d
0x1800acd1a  jl      short loc_1800ACD08
0x1800acd1c  jmp     loc_1800ACDE3
0x1800acd21  mov     dword ptr [rbp+180h+var_170], edx
0x1800acd24  lea     r8, [rbp+180h+var_120]; struct WindowsRemoteAppLib::CRailUi **
0x1800acd28  lea     rdx, [rbp+180h+var_170]; struct WindowsRemoteAppLib::CRailUiId *
0x1800acd2c  mov     [rbp+180h+var_164], r13d
0x1800acd30  mov     rcx, r12; this
0x1800acd33  call    ?FindRailUi@CRailUiManager@WindowsRemoteAppLib@@QEAAJPEBVCRailUiId@2@PEAPEAVCRailUi@2@@Z
0x1800acd38  mov     rdi, [rbp+180h+var_120]
0x1800acd3c  mov     r15d, eax
0x1800acd3f  test    eax, eax
0x1800acd41  jns     loc_1800ACF15
0x1800acd47  mov     rax, cs:WPP_GLOBAL_Control
0x1800acd4e  lea     rcx, WPP_GLOBAL_Control
0x1800acd55  cmp     rax, rcx
0x1800acd58  jz      short loc_1800ACD9B
0x1800acd5a  test    byte ptr [rax+1Ch], 8
0x1800acd5e  jz      short loc_1800ACD9B
0x1800acd60  cmp     byte ptr [rax+19h], 2
0x1800acd64  jb      short loc_1800ACD9B
0x1800acd66  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ
0x1800acd6b  lea     rcx, aFindrailuiFail
0x1800acd72  mov     [rsp+280h+var_258], r15d
0x1800acd77  mov     qword ptr [rsp+280h+y], rcx
0x1800acd7c  lea     r8, WPP_5f7999f72f073c88df0000a8d4f05f34_Traceguids
0x1800acd83  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acd8a  mov     edx, 21h ; '!'
0x1800acd8f  mov     r9d, eax
0x1800acd92  mov     rcx, [rcx+10h]
0x1800acd96  call    WPP_SF_DsD
0x1800acd9b  mov     eax, cs:dword_1808B5850
0x1800acda1  cmp     eax, 3
0x1800acda4  jbe     short loc_1800ACDE3
0x1800acda6  mov     eax, [r12+9D8h]
0x1800acdae  lea     rdx, word_1808644F2
0x1800acdb5  mov     [rsp+280h+var_20C], eax
0x1800acdb9  lea     rcx, dword_1808B5850
0x1800acdc0  lea     rax, aFoundActiveWin_0
0x1800acdc7  mov     [rbp+180h+hWinPosInfo], rax
0x1800acdcb  lea     rax, [rsp+280h+var_20C]
0x1800acdd0  mov     qword ptr [rsp+280h+var_258], rax
0x1800acdd5  lea     rax, [rbp+180h+hWinPosInfo]
0x1800acdd9  mov     qword ptr [rsp+280h+y], rax
0x1800acdde  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z
0x1800acde3  mov     [rbp+180h+var_1F8], r14d
0x1800acde7  mov     eax, cs:dword_1808B5850
0x1800acded  cmp     eax, 3
0x1800acdf0  jbe     short loc_1800ACE2F
0x1800acdf2  mov     eax, [r12+9D8h]
0x1800acdfa  lea     rdx, qword_180864520
0x1800ace01  mov     [rsp+280h+var_20C], eax
0x1800ace05  lea     rcx, dword_1808B5850
0x1800ace0c  lea     rax, aUnableToFindAc
0x1800ace13  mov     [rbp+180h+hWinPosInfo], rax
0x1800ace17  lea     rax, [rsp+280h+var_20C]
0x1800ace1c  mov     qword ptr [rsp+280h+var_258], rax
0x1800ace21  lea     rax, [rbp+180h+hWinPosInfo]
0x1800ace25  mov     qword ptr [rsp+280h+y], rax
0x1800ace2a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z
0x1800ace2f  lea     r14, aDozorder
0x1800ace36  mov     eax, cs:dword_1808B5850
0x1800ace3c  cmp     eax, 4
0x1800ace3f  jbe     short loc_1800ACE85
0x1800ace41  movzx   eax, byte ptr [r12+9D0h]
0x1800ace4a  lea     rdx, word_18086454E
0x1800ace51  mov     [rsp+280h+var_20C], eax
0x1800ace55  lea     rax, aBeginningZOrde
0x1800ace5c  mov     [rbp+180h+var_1E0], rax
0x1800ace60  lea     rax, [rsp+280h+var_20C]
0x1800ace65  mov     qword ptr [rsp+280h+cy], rax
0x1800ace6a  lea     rax, [rbp+180h+hWinPosInfo]
0x1800ace6e  mov     qword ptr [rsp+280h+var_258], rax
0x1800ace73  lea     rax, [rbp+180h+var_1E0]
0x1800ace77  mov     qword ptr [rsp+280h+y], rax
0x1800ace7c  mov     [rbp+180h+hWinPosInfo], r14
0x1800ace80  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z
0x1800ace85  movzx   ecx, byte ptr [r12+9D0h]; nNumWindows
0x1800ace8e  call    cs:__imp_BeginDeferWindowPos
0x1800ace94  mov     [rbp+180h+hWinPosInfo], rax
0x1800ace98  mov     r14, rax
0x1800ace9b  test    rax, rax
0x1800ace9e  jnz     loc_1800ACF8E
0x1800acea4  call    cs:__imp_GetLastError
0x1800aceaa  mov     r15d, eax
0x1800acead  mov     rax, cs:WPP_GLOBAL_Control
0x1800aceb4  lea     rcx, WPP_GLOBAL_Control
0x1800acebb  cmp     rax, rcx
0x1800acebe  jz      short loc_1800ACEF4
0x1800acec0  test    byte ptr [rax+1Ch], 8
0x1800acec4  jz      short loc_1800ACEF4
0x1800acec6  cmp     byte ptr [rax+19h], 2
0x1800aceca  jb      short loc_1800ACEF4
0x1800acecc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ
0x1800aced1  lea     edx, [r14+22h]
0x1800aced5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800acedc  lea     r8, WPP_5f7999f72f073c88df0000a8d4f05f34_Traceguids
0x1800acee3  mov     r9d, eax
0x1800acee6  mov     [rsp+280h+y], r15d
0x1800aceeb  mov     rcx, [rcx+10h]
0x1800aceef  call    WPP_SF_Dd
0x1800acef4  test    r15d, r15d
0x1800acef7  jle     short loc_1800ACF04
0x1800acef9  movzx   r15d, r15w
0x1800acefd  or      r15d, 80070000h
0x1800acf04  test    r15d, r15d
0x1800acf07  mov     eax, 80004005h
0x1800acf0c  cmovns  r15d, eax
0x1800acf10  jmp     loc_1800AE029
0x1800acf15  mov     rcx, [rdi+30h]; hWnd
0x1800acf19  call    cs:__imp_IsWindowVisible
0x1800acf1f  test    eax, eax
0x1800acf21  jz      loc_1800ACD9B
0x1800acf27  mov     eax, cs:dword_1808B5850
0x1800acf2d  cmp     eax, 4
0x1800acf30  jbe     short loc_1800ACF7E
0x1800acf32  mov     eax, [r12+9D8h]
0x1800acf3a  lea     r14, aDozorder
0x1800acf41  mov     [rsp+280h+var_20C], eax
0x1800acf45  lea     rdx, byte_180864619
0x1800acf4c  lea     rax, aFoundActiveWin
0x1800acf53  mov     [rbp+180h+hWinPosInfo], r14
0x1800acf57  mov     [rbp+180h+var_1E0], rax
0x1800acf5b  lea     rax, [rsp+280h+var_20C]
0x1800acf60  mov     qword ptr [rsp+280h+cy], rax
0x1800acf65  lea     rax, [rbp+180h+hWinPosInfo]
0x1800acf69  mov     qword ptr [rsp+280h+var_258], rax
0x1800acf6e  lea     rax, [rbp+180h+var_1E0]
0x1800acf72  mov     qword ptr [rsp+280h+y], rax
0x1800acf77  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z
0x1800acf7c  jmp     short loc_1800ACF85
0x1800acf7e  lea     r14, aDozorder
0x1800acf85  mov     [rbp+180h+var_1F8], r13d
0x1800acf89  jmp     loc_1800ACE36
0x1800acf8e  xor     eax, eax
0x1800acf90  mov     [rbp+180h+hWndInsertAfter], rbx
0x1800acf94  xor     dl, dl
0x1800acf96  mov     [rbp+180h+var_1B8], ebx
0x1800acf99  mov     [rbp+180h+var_188], eax
0x1800acf9c  mov     [rbp+180h+var_178], eax
0x1800acf9f  mov     [rsp+280h+var_208], dl
0x1800acfa3  cmp     [r12+9D0h], al
0x1800acfab  jbe     loc_1800ADD89
0x1800acfb1  mov     eax, [r12+9D4h]
0x1800acfb9  mov     [rbp+180h+var_150], 0
0x1800acfc1  mov     [rbp+180h+var_1F0], 0
0x1800acfc9  test    eax, eax
0x1800acfcb  jz      short loc_1800AD03C
0x1800acfcd  movzx   ecx, dl
0x1800acfd0  cmp     [r12+rcx*4+5D0h], eax
0x1800acfd8  jnz     short loc_1800AD03C
0x1800acfda  mov     eax, cs:dword_1808B5850
0x1800acfe0  mov     [rbp+180h+var_1B8], r13d
0x1800acfe4  cmp     eax, 4
0x1800acfe7  jbe     loc_1800ADD3A
0x1800acfed  mov     eax, [r12+rcx*4+5D0h]
0x1800acff5  lea     rdx, qword_180864468
0x1800acffc  mov     [rsp+280h+var_20C], eax
0x1800ad000  lea     rax, aDozorder
0x1800ad007  mov     [rbp+180h+var_1E0], rax
0x1800ad00b  lea     rax, aFoundMarkerWin
0x1800ad012  mov     [rbp+180h+var_198], rax
0x1800ad016  lea     rax, [rsp+280h+var_20C]
0x1800ad01b  mov     qword ptr [rsp+280h+cy], rax
0x1800ad020  lea     rax, [rbp+180h+var_1E0]
0x1800ad024  mov     qword ptr [rsp+280h+var_258], rax
0x1800ad029  lea     rax, [rbp+180h+var_198]
0x1800ad02d  mov     qword ptr [rsp+280h+y], rax
0x1800ad032  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z
0x1800ad037  jmp     loc_1800ADD3A
0x1800ad03c  mov     eax, 174h
0x1800ad041  movzx   r14d, dl
0x1800ad045  add     r14, rax
0x1800ad048  mov     [rbp+180h+var_EC], r13d
0x1800ad04f  mov     cl, dl
0x1800ad051  mov     [rbp+180h+var_1C0], r14
0x1800ad055  lea     r8, [rbp+180h+var_150]; struct WindowsRemoteAppLib::CRailUi **
0x1800ad059  mov     rcx, r12; this
0x1800ad05c  lea     rdx, [rbp+180h+var_F8]; struct WindowsRemoteAppLib::CRailUiId *
0x1800ad063  mov     eax, [r12+r14*4]
0x1800ad067  mov     [rbp+180h+var_F8], eax
0x1800ad06d  call    ?FindRailUi@CRailUiManager@WindowsRemoteAppLib@@QEAAJPEBVCRailUiId@2@PEAPEAVCRailUi@2@@Z
0x1800ad072  test    eax, eax
0x1800ad074  jns     short loc_1800AD0C8
0x1800ad076  mov     ecx, cs:dword_1808B5850
0x1800ad07c  cmp     ecx, 3
0x1800ad07f  jbe     loc_1800ADD3A
0x1800ad085  mov     [rsp+280h+var_20C], eax
0x1800ad089  lea     rdx, byte_18086449B
0x1800ad090  mov     eax, [r12+r14*4]
0x1800ad094  mov     [rbp+180h+var_1D8], eax
0x1800ad097  lea     rax, aMissingProxyWi
0x1800ad09e  mov     [rbp+180h+var_1E0], rax
0x1800ad0a2  lea     rax, [rsp+280h+var_20C]
0x1800ad0a7  mov     qword ptr [rsp+280h+cy], rax
0x1800ad0ac  lea     rax, [rbp+180h+var_1D8]
0x1800ad0b0  mov     qword ptr [rsp+280h+var_258], rax
0x1800ad0b5  lea     rax, [rbp+180h+var_1E0]
0x1800ad0b9  mov     qword ptr [rsp+280h+y], rax
0x1800ad0be  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z
0x1800ad0c3  jmp     loc_1800ADD3A
0x1800ad0c8  mov     r14, [rbp+180h+var_150]
0x1800ad0cc  lea     rdx, [rbp+180h+var_1F0]
  ... truncated ...
```
