# SendVBScriptToastNotificationForMshtml

- ea: `0x1808f5300`
- end: `0x1808f5cde`
- name: `SendVBScriptToastNotificationForMshtml`
- size: `2526`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800145c4`

## callees

- `0x1804e4c1c`
- `0x1807e84a8`
- `0x1808f3b00`
- `0x1808f5300`
- `0x1808f5e10`
- `0x1810f65c0`
- `0x181100f20`
- `0x181104010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1808f5446`
- `msvcrt!wcsrchr` at `0x1808f5446`
- `KERNEL32!GetCurrentProcessId` at `0x1808f5373`
- `KERNEL32!GetCurrentProcessId` at `0x1808f5373`
- `KERNEL32!ProcessIdToSessionId` at `0x1808f5386`
- `KERNEL32!ProcessIdToSessionId` at `0x1808f5386`
- `KERNEL32!InitOnceExecuteOnce` at `0x1808f5347`
- `KERNEL32!InitOnceExecuteOnce` at `0x1808f5347`
- `KERNEL32!CompareStringW` at `0x1808f555e`
- `KERNEL32!CompareStringW` at `0x1808f56f7`
- `KERNEL32!CompareStringW` at `0x1808f555e`
- `KERNEL32!CompareStringW` at `0x1808f56f7`
- `KERNEL32!GetModuleFileNameW` at `0x1808f540c`
- `KERNEL32!GetModuleFileNameW` at `0x1808f540c`
- `KERNEL32!GetLastError` at `0x1808f541c`
- `KERNEL32!GetLastError` at `0x1808f541c`
- `USER32!GetProcessWindowStation` at `0x1808f53a5`
- `USER32!GetProcessWindowStation` at `0x1808f53a5`
- `USER32!GetUserObjectInformationW` at `0x1808f53e2`
- `USER32!GetUserObjectInformationW` at `0x1808f53e2`
- `SHELL32!SHGetFolderPathW` at `0x1808f5601`
- `SHELL32!SHGetFolderPathW` at `0x1808f5601`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808f5668`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808f5760`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808f5845`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808f5948`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808f5a03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808f5668`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808f5760`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808f5845`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808f5948`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808f5a03`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1808f568c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1808f5a27`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1808f568c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1808f5a27`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1808f5862`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1808f5862`

## string_xrefs

- `0x1808f583e`: `Windows.Data.Xml.Dom.XmlDocument`
- `0x1808f57cc`: `<toast activationType='protocol' launch='https://techcommunity.microsoft.com/blog/windows-itpro-blog/vbscript-deprecation-timelines-and-next-steps/4148301'><visual><binding template='ToastGeneric'><text>VBScript Usage Detected</text><text>VBScript will be removed and may not be supported in future versions of Windows. Go to Event Viewer > VBScriptDeprecationEvent for more details.</text></binding></visual><actions><action content='Learn More' activationType='protocol' arguments='https://techcomm`

## pseudocode

```c
signed int SendVBScriptToastNotificationForMshtml()
{
  DWORD CurrentProcessId; // eax
  HWINSTA ProcessWindowStation; // rax
  signed int result; // eax
  wchar_t *v3; // rax
  WCHAR *v4; // rdi
  WCHAR *v5; // r10
  WCHAR *v6; // r14
  WCHAR v7; // r8
  const WCHAR *v8; // r9
  unsigned __int64 v9; // rbx
  int v10; // r15d
  WCHAR v11; // dx
  unsigned __int16 v12; // cx
  int v13; // esi
  WCHAR v14; // r8
  const WCHAR *v15; // r9
  WCHAR v16; // dx
  unsigned __int16 v17; // cx
  int v18; // eax
  wchar_t *v19; // rdi
  HRESULT v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  int ActivationFactory; // esi
  unsigned int v24; // r8d
  _QWORD *v25; // rcx
  int v26; // eax
  _QWORD *v27; // rsi
  unsigned __int64 v28; // rdx
  __int64 v29; // r14
  HRESULT v30; // eax
  int v31; // edx
  unsigned int v32; // r8d
  int v33; // edi
  __int64 v34; // rcx
  void (*v35)(void); // rax
  _QWORD *v36; // rcx
  __int64 v37; // rcx
  _QWORD *v38; // rcx
  HRESULT v39; // eax
  int v40; // edx
  unsigned int v41; // r8d
  int v42; // eax
  __int64 (__fastcall ***v43)(_QWORD, GUID *, _QWORD **); // rcx
  void (*v44)(void); // rax
  __int64 v45; // rcx
  int v46; // edx
  unsigned int v47; // r8d
  _QWORD *v48; // rcx
  __int64 (__fastcall ***v49)(_QWORD, GUID *, _QWORD **); // rcx
  _QWORD *v50; // rdi
  __int64 v51; // rsi
  HRESULT v52; // eax
  int v53; // edx
  unsigned int v54; // r8d
  int v55; // ebx
  _QWORD *v56; // rcx
  __int64 (__fastcall ***v57)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v58; // rcx
  _QWORD *v59; // rcx
  HRESULT v60; // eax
  int v61; // edx
  unsigned int v62; // r8d
  int v63; // eax
  __int64 v64; // rcx
  _QWORD *v65; // rcx
  __int64 (__fastcall ***v66)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v67; // rcx
  _QWORD *v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rcx
  _QWORD *v71; // rcx
  __int64 (__fastcall ***v72)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v73; // rcx
  int v74; // eax
  __int64 v75; // rcx
  __int64 v76; // rcx
  _QWORD *v77; // rcx
  __int64 (__fastcall ***v78)(_QWORD, GUID *, _QWORD **); // rcx
  __int64 v79; // rcx
  _QWORD *v80; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v81; // [rsp+38h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v82)(_QWORD, GUID *, _QWORD **); // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v83; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v84; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v85; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pSessionId; // [rsp+60h] [rbp-A0h] BYREF
  DWORD nLengthNeeded; // [rsp+64h] [rbp-9Ch] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-98h] BYREF
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  __int64 pvInfo; // [rsp+88h] [rbp-78h] BYREF
  int v91; // [rsp+90h] [rbp-70h]
  WCHAR Filename[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v93[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR pszPath[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR sourceString[2048]; // [rsp+6D0h] [rbp+5D0h] BYREF

  InitOnceExecuteOnce(&stru_1815C53B0, InitOnceVersionInfo, 0, 0);
  if ( (unsigned __int8)(byte_1815C545A - 2) <= 1u )
    return 1;
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    return 1;
  if ( !pSessionId )
    return 1;
  ProcessWindowStation = GetProcessWindowStation();
  if ( !ProcessWindowStation )
    return 1;
  nLengthNeeded = 0;
  pvInfo = 0;
  v91 = 0;
  if ( !GetUserObjectInformationW(ProcessWindowStation, 1, &pvInfo, 0xCu, &nLengthNeeded) || (v91 & 1) == 0 )
    return 1;
  if ( !GetModuleFileNameW(0, Filename, 0x104u) )
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  v3 = wcsrchr(Filename, 0x5Cu);
  if ( v3 )
  {
    v4 = v3 + 1;
    if ( v3 == (wchar_t *)-2LL )
      return 1;
    v5 = v3 + 1;
    v6 = v3 + 1;
  }
  else
  {
    v6 = Filename;
    v4 = Filename;
    v5 = Filename;
  }
  v7 = *v6;
  v8 = L"mshta.exe";
  v9 = -1;
  v10 = 0x7FFFFFFF;
  while ( v7 )
  {
    v11 = *v8;
    if ( v7 == *v8 )
      goto LABEL_22;
    v12 = v11 - 65;
    if ( (unsigned __int16)(v7 - 65) > 0x19u )
    {
      if ( v12 > 0x19u )
        goto LABEL_29;
    }
    else
    {
      v7 += 32;
      if ( v12 > 0x19u )
        goto LABEL_21;
    }
    v11 += 32;
LABEL_21:
    if ( v7 != v11 )
    {
LABEL_29:
      if ( ((v7 | v11) & 0xFF80) != 0 )
      {
        v18 = CompareStringW(0, 0x31001u, v5, -1, v8, -1);
        if ( v18 <= 0 )
          v13 = 0x7FFFFFFF;
        else
          v13 = v18 - 2;
      }
      else if ( v7 <= v11 )
      {
        v13 = -1;
      }
      else
      {
        v13 = 1;
      }
      goto LABEL_24;
    }
LABEL_22:
    v7 = v5[1];
    ++v5;
    ++v8;
  }
  v13 = -(*v8 != 0);
LABEL_24:
  v14 = *v6;
  v15 = L"iexplore.exe";
  if ( !*v6 )
  {
LABEL_40:
    v10 = -(*v15 != 0);
    goto LABEL_41;
  }
  while ( 1 )
  {
    v16 = *v15;
    if ( v14 != *v15 )
      break;
LABEL_39:
    v14 = v4[1];
    ++v4;
    ++v15;
    if ( !v14 )
      goto LABEL_40;
  }
  v17 = v16 - 65;
  if ( (unsigned __int16)(v14 - 65) > 0x19u )
  {
    if ( v17 > 0x19u )
      goto LABEL_54;
  }
  else
  {
    v14 += 32;
    if ( v17 > 0x19u )
      goto LABEL_38;
  }
  v16 += 32;
LABEL_38:
  if ( v14 == v16 )
    goto LABEL_39;
LABEL_54:
  if ( ((v14 | v16) & 0xFF80) != 0 )
  {
    v26 = CompareStringW(0, 0x31001u, v4, -1, v15, -1);
    if ( v26 > 0 )
      v10 = v26 - 2;
  }
  else
  {
    v10 = -1;
    if ( v14 > v16 )
      v10 = 1;
  }
LABEL_41:
  if ( v13 && v10 || !(unsigned __int8)ShouldShowToastThrottled(v6) )
    return 1;
  v19 = L"Microsoft.MSHTA";
  if ( v13 )
    v19 = (wchar_t *)L"Microsoft.InternetExplorer";
  if ( SHGetFolderPathW(0, 2, 0, 0, pszPath) >= 0 && (int)StringCchPrintfW(v93, 0x104u, L"%s.lnk", v6) >= 0 )
    CreateShortcutForExe((__int64)pszPath, (__int64)v93, (__int64)Filename, v19);
  v80 = 0;
  string = 0;
  v20 = WindowsCreateStringReference(
          L"Windows.UI.Notifications.ToastNotificationManager",
          0x31u,
          &hstringHeader,
          &string);
  if ( v20 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4, &v80);
  if ( ActivationFactory >= 0 )
  {
    v27 = v80;
    v28 = -1;
    v81 = 0;
    v29 = *v80;
    string = 0;
    do
      ++v28;
    while ( v19[v28] );
    if ( v28 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v28, v24);
      __debugbreak();
    }
    if ( (int)v28 + 1 < (unsigned int)v28 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v28, v24);
      JUMPOUT(0x1808F5CDDLL);
    }
    v30 = WindowsCreateStringReference(v19, v28, &hstringHeader, &string);
    if ( v30 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v30, v31, v32);
      __debugbreak();
    }
    v33 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v29 + 56))(v27, string, &v81);
    if ( v33 < 0 )
    {
      v34 = v81;
      if ( !v81 )
        goto LABEL_69;
      v81 = 0;
      v35 = *(void (**)(void))(*(_QWORD *)v34 + 16LL);
      goto LABEL_68;
    }
    v33 = StringCchPrintfW(
            sourceString,
            0x800u,
            L"<toast activationType='protocol' launch='https://techcommunity.microsoft.com/blog/windows-itpro-blog/vbscrip"
             "t-deprecation-timelines-and-next-steps/4148301'><visual><binding template='ToastGeneric'><text>VBScript Usa"
             "ge Detected</text><text>VBScript will be removed and may not be supported in future versions of Windows. Go"
             " to Event Viewer > VBScriptDeprecationEvent for more details.</text></binding></visual><actions><action con"
             "tent='Learn More' activationType='protocol' arguments='https://techcommunity.microsoft.com/blog/windows-itp"
             "ro-blog/vbscript-deprecation-timelines-and-next-steps/4148301' /><action content='Dismiss' activationType='"
             "system' arguments='dismiss' /></actions></toast>");
    if ( v33 < 0 )
    {
      v37 = v81;
      if ( v81 )
      {
        v81 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
      v38 = v80;
      if ( v80 )
      {
        v80 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v38 + 16LL))(v38);
        return v33;
      }
      return v33;
    }
    v82 = 0;
    string = 0;
    v39 = WindowsCreateStringReference(L"Windows.Data.Xml.Dom.XmlDocument", 0x20u, &hstringHeader, &string);
    if ( v39 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v39, v40, v41);
      __debugbreak();
    }
    v42 = RoActivateInstance(string, &v82);
    v43 = v82;
    v33 = v42;
    if ( v42 < 0 )
    {
      if ( !v82 )
      {
LABEL_82:
        v45 = v81;
        if ( !v81 )
        {
LABEL_69:
          v36 = v80;
          if ( v80 )
          {
            v80 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v36 + 16LL))(v36);
          }
          return v33;
        }
        v81 = 0;
        v35 = *(void (**)(void))(*(_QWORD *)v45 + 16LL);
LABEL_68:
        v35();
        goto LABEL_69;
      }
      v82 = 0;
      v44 = (void (*)(void))(*v43)[2];
LABEL_81:
      v44();
      goto LABEL_82;
    }
    v83 = 0;
    v33 = (**v82)(v82, &GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637, &v83);
    if ( v33 < 0 )
    {
      v48 = v83;
      if ( v83 )
      {
        v83 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v48 + 16LL))(v48);
      }
      v49 = v82;
      if ( !v82 )
        goto LABEL_82;
      v82 = 0;
      v44 = (void (*)(void))(*v49)[2];
      goto LABEL_81;
    }
    do
      ++v9;
    while ( sourceString[v9] );
    if ( v9 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v46, v47);
      __debugbreak();
    }
    if ( (int)v9 + 1 < (unsigned int)v9 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v46, v47);
      __debugbreak();
    }
    v50 = v83;
    v51 = *v83;
    v52 = WindowsCreateStringReference(sourceString, v9, &hstringHeader, &string);
    if ( v52 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v52, v53, v54);
      __debugbreak();
    }
    v55 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING))(v51 + 48))(v50, string);
    if ( v55 < 0 )
    {
      v56 = v83;
      if ( v83 )
      {
        v83 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v56 + 16LL))(v56);
      }
      v57 = v82;
      if ( v82 )
      {
        v82 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v57)[2])(v57);
      }
      v58 = v81;
      if ( v81 )
      {
        v81 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
      }
      v59 = v80;
      if ( v80 )
      {
        v80 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v59 + 16LL))(v59);
      }
      return v55;
    }
    v84 = 0;
    string = 0;
    v60 = WindowsCreateStringReference(L"Windows.UI.Notifications.ToastNotification", 0x2Au, &hstringHeader, &string);
    if ( v60 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v60, v61, v62);
      __debugbreak();
    }
    v63 = RoGetActivationFactory(string, &GUID_04124b20_82c6_4229_b109_fd9ed4662b53, &v84);
    v64 = v84;
    v55 = v63;
    if ( v63 >= 0 )
    {
      v85 = 0;
      v55 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v84 + 48LL))(v84, v82, &v85);
      if ( v55 >= 0 )
      {
        v74 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v81 + 48LL))(v81, v85);
        v75 = v85;
        v55 = v74;
        if ( v85 )
        {
          v85 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
        }
        v76 = v84;
        if ( v84 )
        {
          v84 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
        }
        v77 = v83;
        if ( v83 )
        {
          v83 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v77 + 16LL))(v77);
        }
        v78 = v82;
        if ( v82 )
        {
          v82 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v78)[2])(v78);
        }
        v79 = v81;
        if ( v81 )
        {
          v81 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
        }
        v68 = v80;
        if ( !v80 )
          return v55;
      }
      else
      {
        v69 = v85;
        if ( v85 )
        {
          v85 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
        }
        v70 = v84;
        if ( v84 )
        {
          v84 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
        }
        v71 = v83;
        if ( v83 )
        {
          v83 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v71 + 16LL))(v71);
        }
        v72 = v82;
        if ( v82 )
        {
          v82 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v72)[2])(v72);
        }
        v73 = v81;
        if ( v81 )
        {
          v81 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
        }
        v68 = v80;
        if ( !v80 )
          return v55;
      }
    }
    else
    {
      if ( v84 )
      {
        v84 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      }
      v65 = v83;
      if ( v83 )
      {
        v83 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v65 + 16LL))(v65);
      }
      v66 = v82;
      if ( v82 )
      {
        v82 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v66)[2])(v66);
      }
      v67 = v81;
      if ( v81 )
      {
        v81 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
      }
      v68 = v80;
      if ( !v80 )
        return v55;
    }
    v80 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v68 + 16LL))(v68);
    return v55;
  }
  v25 = v80;
  if ( v80 )
  {
    v80 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v25 + 16LL))(v25);
  }
  return ActivationFactory;
}

```

## disassembly

```asm
0x1808f5300  push    rbp
0x1808f5302  push    rbx
0x1808f5303  push    rsi
0x1808f5304  push    rdi
0x1808f5305  push    r12
0x1808f5307  push    r13
0x1808f5309  push    r14
0x1808f530b  push    r15
0x1808f530d  lea     rbp, [rsp-15E8h]
0x1808f5315  mov     eax, 16E8h
0x1808f531a  call    _alloca_probe
0x1808f531f  sub     rsp, rax
0x1808f5322  mov     rax, cs:__security_cookie
0x1808f5329  xor     rax, rsp
0x1808f532c  mov     [rbp+1620h+var_50], rax
0x1808f5333  xor     r9d, r9d; Context
0x1808f5336  lea     rdx, ?InitOnceVersionInfo@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1808f533d  xor     r8d, r8d; Parameter
0x1808f5340  lea     rcx, stru_1815C53B0; InitOnce
0x1808f5347  call    cs:__imp_InitOnceExecuteOnce
0x1808f534e  nop     dword ptr [rax+rax+00h]
0x1808f5353  movzx   eax, cs:byte_1815C545A
0x1808f535a  mov     r13d, 1
0x1808f5360  sub     al, 2
0x1808f5362  cmp     al, r13b
0x1808f5365  jbe     loc_1808F5C63
0x1808f536b  xor     r12d, r12d
0x1808f536e  mov     [rsp+1720h+pSessionId], r12d
0x1808f5373  call    cs:__imp_GetCurrentProcessId
0x1808f537a  nop     dword ptr [rax+rax+00h]
0x1808f537f  mov     ecx, eax; dwProcessId
0x1808f5381  lea     rdx, [rsp+1720h+pSessionId]; pSessionId
0x1808f5386  call    cs:__imp_ProcessIdToSessionId
0x1808f538d  nop     dword ptr [rax+rax+00h]
0x1808f5392  test    eax, eax
0x1808f5394  jz      loc_1808F5C63
0x1808f539a  cmp     [rsp+1720h+pSessionId], r12d
0x1808f539f  jz      loc_1808F5C63
0x1808f53a5  call    cs:__imp_GetProcessWindowStation
0x1808f53ac  nop     dword ptr [rax+rax+00h]
0x1808f53b1  test    rax, rax
0x1808f53b4  jz      loc_1808F5C63
0x1808f53ba  xor     ecx, ecx
0x1808f53bc  mov     [rsp+1720h+nLengthNeeded], r12d
0x1808f53c1  mov     [rbp+1620h+pvInfo], rcx
0x1808f53c5  lea     r8, [rbp+1620h+pvInfo]; pvInfo
0x1808f53c9  mov     [rbp+1620h+var_1690], ecx
0x1808f53cc  mov     r9d, 0Ch; nLength
0x1808f53d2  lea     rcx, [rsp+1720h+nLengthNeeded]
0x1808f53d7  mov     edx, r13d; nIndex
0x1808f53da  mov     [rsp+1720h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x1808f53df  mov     rcx, rax; hObj
0x1808f53e2  call    cs:__imp_GetUserObjectInformationW
0x1808f53e9  nop     dword ptr [rax+rax+00h]
0x1808f53ee  test    eax, eax
0x1808f53f0  jz      loc_1808F5C63
0x1808f53f6  test    byte ptr [rbp+1620h+var_1690], r13b
0x1808f53fa  jz      loc_1808F5C63
0x1808f5400  mov     r8d, 104h; nSize
0x1808f5406  lea     rdx, [rbp+1620h+Filename]; lpFilename
0x1808f540a  xor     ecx, ecx; hModule
0x1808f540c  call    cs:__imp_GetModuleFileNameW
0x1808f5413  nop     dword ptr [rax+rax+00h]
0x1808f5418  test    eax, eax
0x1808f541a  jnz     short loc_1808F543D
0x1808f541c  call    cs:__imp_GetLastError
0x1808f5423  nop     dword ptr [rax+rax+00h]
0x1808f5428  test    eax, eax
0x1808f542a  jle     loc_1808F5C66
0x1808f5430  movzx   eax, ax
0x1808f5433  or      eax, 80070000h
0x1808f5438  jmp     loc_1808F5C66
0x1808f543d  mov     edx, 5Ch ; '\'; Ch
0x1808f5442  lea     rcx, [rbp+1620h+Filename]; Str
0x1808f5446  call    cs:__imp_wcsrchr
0x1808f544d  nop     dword ptr [rax+rax+00h]
0x1808f5452  test    rax, rax
0x1808f5455  jz      short loc_1808F546C
0x1808f5457  lea     rdi, [rax+2]
0x1808f545b  test    rdi, rdi
0x1808f545e  jz      loc_1808F5C63
0x1808f5464  mov     r10, rdi
0x1808f5467  mov     r14, rdi
0x1808f546a  jmp     short loc_1808F5476
0x1808f546c  lea     r14, [rbp+1620h+Filename]
0x1808f5470  mov     rdi, r14
0x1808f5473  mov     r10, r14
0x1808f5476  movzx   r8d, word ptr [r14]
0x1808f547a  lea     r9, aMshtaExe; "mshta.exe"
0x1808f5481  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1808f5488  mov     r15d, 7FFFFFFFh
0x1808f548e  test    r8w, r8w
0x1808f5492  jz      short loc_1808F54DB
0x1808f5494  movzx   edx, word ptr [r9]
0x1808f5498  cmp     r8w, dx
0x1808f549c  jz      short loc_1808F54C8
0x1808f549e  lea     eax, [r8-41h]
0x1808f54a2  lea     ecx, [rdx-41h]
0x1808f54a5  cmp     ax, 19h
0x1808f54a9  ja      short loc_1808F54B8
0x1808f54ab  add     r8w, 20h ; ' '
0x1808f54b0  cmp     cx, 19h
0x1808f54b4  ja      short loc_1808F54C2
0x1808f54b6  jmp     short loc_1808F54BE
0x1808f54b8  cmp     cx, 19h
0x1808f54bc  ja      short loc_1808F5528
0x1808f54be  add     dx, 20h ; ' '
0x1808f54c2  cmp     r8w, dx
0x1808f54c6  jnz     short loc_1808F5528
0x1808f54c8  movzx   r8d, word ptr [r10+2]
0x1808f54cd  add     r10, 2
0x1808f54d1  add     r9, 2
0x1808f54d5  test    r8w, r8w
0x1808f54d9  jnz     short loc_1808F5494
0x1808f54db  movzx   eax, word ptr [r9]
0x1808f54df  neg     ax
0x1808f54e2  sbb     esi, esi
0x1808f54e4  movzx   r8d, word ptr [r14]
0x1808f54e8  lea     r9, aIexploreExe; "iexplore.exe"
0x1808f54ef  test    r8w, r8w
0x1808f54f3  jz      loc_1808F55AD
0x1808f54f9  nop     dword ptr [rax+00000000h]
0x1808f5500  movzx   edx, word ptr [r9]
0x1808f5504  cmp     r8w, dx
0x1808f5508  jz      loc_1808F5596
0x1808f550e  lea     eax, [r8-41h]
0x1808f5512  lea     ecx, [rdx-41h]
0x1808f5515  cmp     ax, 19h
0x1808f5519  ja      short loc_1808F557E
0x1808f551b  add     r8w, 20h ; ' '
0x1808f5520  cmp     cx, 19h
0x1808f5524  ja      short loc_1808F558C
0x1808f5526  jmp     short loc_1808F5588
0x1808f5528  movzx   ecx, dx
0x1808f552b  movzx   eax, r8w
0x1808f552f  or      ecx, eax
0x1808f5531  test    ecx, 0FFFFFF80h
0x1808f5537  jnz     short loc_1808F5548
0x1808f5539  cmp     r8w, dx
0x1808f553d  jbe     short loc_1808F5544
0x1808f553f  mov     esi, r13d
0x1808f5542  jmp     short loc_1808F54E4
0x1808f5544  mov     esi, ebx
0x1808f5546  jmp     short loc_1808F54E4
0x1808f5548  mov     [rsp+1720h+cchCount2], ebx; cchCount2
0x1808f554c  mov     r8, r10; lpString1
0x1808f554f  mov     [rsp+1720h+lpnLengthNeeded], r9; lpString2
0x1808f5554  mov     edx, 31001h; dwCmpFlags
0x1808f5559  mov     r9d, ebx; cchCount1
0x1808f555c  xor     ecx, ecx; Locale
0x1808f555e  call    cs:__imp_CompareStringW
0x1808f5565  nop     dword ptr [rax+rax+00h]
0x1808f556a  test    eax, eax
0x1808f556c  jle     short loc_1808F5576
0x1808f556e  lea     esi, [rax-2]
0x1808f5571  jmp     loc_1808F54E4
0x1808f5576  mov     esi, r15d
0x1808f5579  jmp     loc_1808F54E4
0x1808f557e  cmp     cx, 19h
0x1808f5582  ja      loc_1808F56C0
0x1808f5588  add     dx, 20h ; ' '
0x1808f558c  cmp     r8w, dx
0x1808f5590  jnz     loc_1808F56C0
0x1808f5596  movzx   r8d, word ptr [rdi+2]
0x1808f559b  add     rdi, 2
0x1808f559f  add     r9, 2
0x1808f55a3  test    r8w, r8w
0x1808f55a7  jnz     loc_1808F5500
0x1808f55ad  movzx   eax, word ptr [r9]
0x1808f55b1  neg     ax
0x1808f55b4  sbb     r15d, r15d
0x1808f55b7  test    esi, esi
0x1808f55b9  jz      short loc_1808F55C4
0x1808f55bb  test    r15d, r15d
0x1808f55be  jnz     loc_1808F5C63
0x1808f55c4  mov     rcx, r14
0x1808f55c7  call    ShouldShowToastThrottled
0x1808f55cc  test    al, al
0x1808f55ce  jz      loc_1808F5C63
0x1808f55d4  lea     rax, aMicrosoftInter_1; "Microsoft.InternetExplorer"
0x1808f55db  test    esi, esi
0x1808f55dd  lea     rdi, aMicrosoftMshta; "Microsoft.MSHTA"
0x1808f55e4  mov     edx, 2; csidl
0x1808f55e9  cmovnz  rdi, rax
0x1808f55ed  lea     rax, [rbp+1620h+pszPath]
0x1808f55f4  xor     r9d, r9d; dwFlags
0x1808f55f7  mov     [rsp+1720h+lpnLengthNeeded], rax; pszPath
0x1808f55fc  xor     r8d, r8d; hToken
0x1808f55ff  xor     ecx, ecx; hwnd
0x1808f5601  call    cs:__imp_SHGetFolderPathW
0x1808f5608  nop     dword ptr [rax+rax+00h]
0x1808f560d  test    eax, eax
0x1808f560f  js      short loc_1808F564A
0x1808f5611  mov     r9, r14
0x1808f5614  lea     r8, aSLnk; "%s.lnk"
0x1808f561b  mov     edx, 104h; unsigned __int64
0x1808f5620  lea     rcx, [rbp+1620h+var_1470]; unsigned __int16 *
0x1808f5627  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1808f562c  test    eax, eax
0x1808f562e  js      short loc_1808F564A
0x1808f5630  mov     r9, rdi
0x1808f5633  lea     r8, [rbp+1620h+Filename]
0x1808f5637  lea     rdx, [rbp+1620h+var_1470]
0x1808f563e  lea     rcx, [rbp+1620h+pszPath]
0x1808f5645  call    CreateShortcutForExe
0x1808f564a  lea     r9, [rbp+1620h+string]; string
0x1808f564e  mov     [rsp+1720h+var_16F0], r12
0x1808f5653  lea     r8, [rsp+1720h+hstringHeader]; hstringHeader
0x1808f5658  mov     [rbp+1620h+string], r12
0x1808f565c  mov     edx, 31h ; '1'; length
0x1808f5661  lea     rcx, ?RuntimeClass_Windows_UI_Notifications_ToastNotificationManager@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x1808f5668  call    cs:__imp_WindowsCreateStringReference
0x1808f566f  nop     dword ptr [rax+rax+00h]
0x1808f5674  test    eax, eax
0x1808f5676  js      loc_1808F5C95
0x1808f567c  mov     rcx, [rbp+1620h+string]
0x1808f5680  lea     r8, [rsp+1720h+var_16F0]
0x1808f5685  lea     rdx, _GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4
0x1808f568c  call    cs:__imp_RoGetActivationFactory
0x1808f5693  nop     dword ptr [rax+rax+00h]
0x1808f5698  mov     esi, eax
0x1808f569a  test    eax, eax
0x1808f569c  jns     short loc_1808F5714
0x1808f569e  mov     rcx, [rsp+1720h+var_16F0]
0x1808f56a3  test    rcx, rcx
0x1808f56a6  jz      short loc_1808F56B9
0x1808f56a8  mov     [rsp+1720h+var_16F0], r12
0x1808f56ad  mov     rdx, [rcx]
0x1808f56b0  mov     rax, [rdx+10h]
0x1808f56b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808f56b9  mov     eax, esi
0x1808f56bb  jmp     loc_1808F5C66
0x1808f56c0  movzx   ecx, dx
0x1808f56c3  movzx   eax, r8w
0x1808f56c7  or      ecx, eax
0x1808f56c9  test    ecx, 0FFFFFF80h
0x1808f56cf  jnz     short loc_1808F56E1
0x1808f56d1  cmp     r8w, dx
0x1808f56d5  mov     r15d, ebx
0x1808f56d8  cmova   r15d, r13d
0x1808f56dc  jmp     loc_1808F55B7
0x1808f56e1  mov     [rsp+1720h+cchCount2], ebx; cchCount2
0x1808f56e5  mov     r8, rdi; lpString1
0x1808f56e8  mov     [rsp+1720h+lpnLengthNeeded], r9; lpString2
0x1808f56ed  mov     edx, 31001h; dwCmpFlags
0x1808f56f2  mov     r9d, ebx; cchCount1
0x1808f56f5  xor     ecx, ecx; Locale
0x1808f56f7  call    cs:__imp_CompareStringW
0x1808f56fe  nop     dword ptr [rax+rax+00h]
0x1808f5703  test    eax, eax
0x1808f5705  jle     loc_1808F55B7
0x1808f570b  lea     r15d, [rax-2]
0x1808f570f  jmp     loc_1808F55B7
0x1808f5714  mov     rsi, [rsp+1720h+var_16F0]
0x1808f5719  mov     rdx, rbx
0x1808f571c  mov     [rsp+1720h+var_16E8], r12
0x1808f5721  mov     r14, [rsi]
0x1808f5724  mov     [rbp+1620h+string], r12
0x1808f5728  nop     dword ptr [rax+rax+00000000h]
0x1808f5730  inc     rdx; int
0x1808f5733  cmp     [rdi+rdx*2], r12w
0x1808f5738  jnz     short loc_1808F5730
0x1808f573a  mov     r15d, 0FFFFFFFFh
0x1808f5740  cmp     rdx, r15
0x1808f5743  ja      loc_1808F5C8A
0x1808f5749  lea     eax, [rdx+1]
0x1808f574c  cmp     eax, edx
0x1808f574e  jb      loc_1808F5CD3
0x1808f5754  lea     r9, [rbp+1620h+string]; string
0x1808f5758  mov     rcx, rdi; sourceString
0x1808f575b  lea     r8, [rsp+1720h+hstringHeader]; hstringHeader
0x1808f5760  call    cs:__imp_WindowsCreateStringReference
0x1808f5767  nop     dword ptr [rax+rax+00h]
0x1808f576c  test    eax, eax
0x1808f576e  js      loc_1808F5C9D
0x1808f5774  mov     rdx, [rbp+1620h+string]
0x1808f5778  lea     r8, [rsp+1720h+var_16E8]
0x1808f577d  mov     rax, [r14+38h]
0x1808f5781  mov     rcx, rsi
0x1808f5784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808f5789  mov     edi, eax
0x1808f578b  test    eax, eax
0x1808f578d  jns     short loc_1808F57CC
0x1808f578f  mov     rcx, [rsp+1720h+var_16E8]
0x1808f5794  test    rcx, rcx
0x1808f5797  jz      short loc_1808F57AA
0x1808f5799  mov     [rsp+1720h+var_16E8], r12
0x1808f579e  mov     rdx, [rcx]
0x1808f57a1  mov     rax, [rdx+10h]
0x1808f57a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808f57aa  mov     rcx, [rsp+1720h+var_16F0]
0x1808f57af  test    rcx, rcx
0x1808f57b2  jz      short loc_1808F57C5
0x1808f57b4  mov     [rsp+1720h+var_16F0], r12
0x1808f57b9  mov     rax, [rcx]
0x1808f57bc  mov     rax, [rax+10h]
0x1808f57c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808f57c5  mov     eax, edi
0x1808f57c7  jmp     loc_1808F5C66
0x1808f57cc  lea     r8, aToastActivatio; "<toast activationType='protocol' launch"...
  ... truncated ...
```
