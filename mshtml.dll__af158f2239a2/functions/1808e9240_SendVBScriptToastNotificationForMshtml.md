# SendVBScriptToastNotificationForMshtml

- ea: `0x1808e9240`
- end: `0x1808e9bab`
- name: `SendVBScriptToastNotificationForMshtml`
- size: `2411`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802ce520`

## callees

- `0x18028ecdc`
- `0x1808d1d30`
- `0x1808e7d90`
- `0x1808e9240`
- `0x1808e9ce0`
- `0x1810c2d60`
- `0x1810cd6c0`
- `0x1810d1010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1808e935c`
- `msvcrt!wcsrchr` at `0x1808e935c`
- `KERNEL32!GetCurrentProcessId` at `0x1808e92ad`
- `KERNEL32!GetCurrentProcessId` at `0x1808e92ad`
- `KERNEL32!ProcessIdToSessionId` at `0x1808e92ba`
- `KERNEL32!ProcessIdToSessionId` at `0x1808e92ba`
- `KERNEL32!InitOnceExecuteOnce` at `0x1808e9287`
- `KERNEL32!InitOnceExecuteOnce` at `0x1808e9287`
- `KERNEL32!CompareStringW` at `0x1808e946e`
- `KERNEL32!CompareStringW` at `0x1808e95ef`
- `KERNEL32!CompareStringW` at `0x1808e946e`
- `KERNEL32!CompareStringW` at `0x1808e95ef`
- `KERNEL32!GetModuleFileNameW` at `0x1808e932e`
- `KERNEL32!GetModuleFileNameW` at `0x1808e932e`
- `KERNEL32!GetLastError` at `0x1808e9338`
- `KERNEL32!GetLastError` at `0x1808e9338`
- `USER32!GetProcessWindowStation` at `0x1808e92d3`
- `USER32!GetProcessWindowStation` at `0x1808e92d3`
- `USER32!GetUserObjectInformationW` at `0x1808e930a`
- `USER32!GetUserObjectInformationW` at `0x1808e930a`
- `SHELL32!SHGetFolderPathW` at `0x1808e950b`
- `SHELL32!SHGetFolderPathW` at `0x1808e950b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808e956c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808e9650`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808e972f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808e9828`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808e98dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808e956c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808e9650`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808e972f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808e9828`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1808e98dd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1808e958a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1808e98fb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1808e958a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1808e98fb`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1808e9746`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1808e9746`

## string_xrefs

- `0x1808e9728`: `Windows.Data.Xml.Dom.XmlDocument`
- `0x1808e96b6`: `<toast activationType='protocol' launch='https://techcommunity.microsoft.com/blog/windows-itpro-blog/vbscript-deprecation-timelines-and-next-steps/4148301'><visual><binding template='ToastGeneric'><text>VBScript Usage Detected</text><text>VBScript will be removed and may not be supported in future versions of Windows. Go to Event Viewer > VBScriptDeprecationEvent for more details.</text></binding></visual><actions><action content='Learn More' activationType='protocol' arguments='https://techcomm`

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

  InitOnceExecuteOnce(&stru_181592340, InitOnceVersionInfo, 0, 0);
  if ( (unsigned __int8)(byte_18159233A - 2) <= 1u )
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
      JUMPOUT(0x1808E9BAALL);
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
0x1808e9240  push    rbp
0x1808e9242  push    rbx
0x1808e9243  push    rsi
0x1808e9244  push    rdi
0x1808e9245  push    r12
0x1808e9247  push    r13
0x1808e9249  push    r14
0x1808e924b  push    r15
0x1808e924d  lea     rbp, [rsp-15E8h]
0x1808e9255  mov     eax, 16E8h
0x1808e925a  call    _alloca_probe
0x1808e925f  sub     rsp, rax
0x1808e9262  mov     rax, cs:__security_cookie
0x1808e9269  xor     rax, rsp
0x1808e926c  mov     [rbp+1620h+var_50], rax
0x1808e9273  xor     r9d, r9d; Context
0x1808e9276  lea     rdx, ?InitOnceVersionInfo@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1808e927d  xor     r8d, r8d; Parameter
0x1808e9280  lea     rcx, stru_181592340; InitOnce
0x1808e9287  call    cs:__imp_InitOnceExecuteOnce
0x1808e928d  movzx   eax, cs:byte_18159233A
0x1808e9294  mov     r13d, 1
0x1808e929a  sub     al, 2
0x1808e929c  cmp     al, r13b
0x1808e929f  jbe     loc_1808E9B31
0x1808e92a5  xor     r12d, r12d
0x1808e92a8  mov     [rsp+1720h+pSessionId], r12d
0x1808e92ad  call    cs:__imp_GetCurrentProcessId
0x1808e92b3  mov     ecx, eax; dwProcessId
0x1808e92b5  lea     rdx, [rsp+1720h+pSessionId]; pSessionId
0x1808e92ba  call    cs:__imp_ProcessIdToSessionId
0x1808e92c0  test    eax, eax
0x1808e92c2  jz      loc_1808E9B31
0x1808e92c8  cmp     [rsp+1720h+pSessionId], r12d
0x1808e92cd  jz      loc_1808E9B31
0x1808e92d3  call    cs:__imp_GetProcessWindowStation
0x1808e92d9  test    rax, rax
0x1808e92dc  jz      loc_1808E9B31
0x1808e92e2  xor     ecx, ecx
0x1808e92e4  mov     [rsp+1720h+nLengthNeeded], r12d
0x1808e92e9  mov     [rbp+1620h+pvInfo], rcx
0x1808e92ed  lea     r8, [rbp+1620h+pvInfo]; pvInfo
0x1808e92f1  mov     [rbp+1620h+var_1690], ecx
0x1808e92f4  mov     r9d, 0Ch; nLength
0x1808e92fa  lea     rcx, [rsp+1720h+nLengthNeeded]
0x1808e92ff  mov     edx, r13d; nIndex
0x1808e9302  mov     [rsp+1720h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x1808e9307  mov     rcx, rax; hObj
0x1808e930a  call    cs:__imp_GetUserObjectInformationW
0x1808e9310  test    eax, eax
0x1808e9312  jz      loc_1808E9B31
0x1808e9318  test    byte ptr [rbp+1620h+var_1690], r13b
0x1808e931c  jz      loc_1808E9B31
0x1808e9322  mov     r8d, 104h; nSize
0x1808e9328  lea     rdx, [rbp+1620h+Filename]; lpFilename
0x1808e932c  xor     ecx, ecx; hModule
0x1808e932e  call    cs:__imp_GetModuleFileNameW
0x1808e9334  test    eax, eax
0x1808e9336  jnz     short loc_1808E9353
0x1808e9338  call    cs:__imp_GetLastError
0x1808e933e  test    eax, eax
0x1808e9340  jle     loc_1808E9B34
0x1808e9346  movzx   eax, ax
0x1808e9349  or      eax, 80070000h
0x1808e934e  jmp     loc_1808E9B34
0x1808e9353  mov     edx, 5Ch ; '\'; Ch
0x1808e9358  lea     rcx, [rbp+1620h+Filename]; Str
0x1808e935c  call    cs:__imp_wcsrchr
0x1808e9362  test    rax, rax
0x1808e9365  jz      short loc_1808E937C
0x1808e9367  lea     rdi, [rax+2]
0x1808e936b  test    rdi, rdi
0x1808e936e  jz      loc_1808E9B31
0x1808e9374  mov     r10, rdi
0x1808e9377  mov     r14, rdi
0x1808e937a  jmp     short loc_1808E9386
0x1808e937c  lea     r14, [rbp+1620h+Filename]
0x1808e9380  mov     rdi, r14
0x1808e9383  mov     r10, r14
0x1808e9386  movzx   r8d, word ptr [r14]
0x1808e938a  lea     r9, aMshtaExe; "mshta.exe"
0x1808e9391  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1808e9398  mov     r15d, 7FFFFFFFh
0x1808e939e  test    r8w, r8w
0x1808e93a2  jz      short loc_1808E93EB
0x1808e93a4  movzx   edx, word ptr [r9]
0x1808e93a8  cmp     r8w, dx
0x1808e93ac  jz      short loc_1808E93D8
0x1808e93ae  lea     eax, [r8-41h]
0x1808e93b2  lea     ecx, [rdx-41h]
0x1808e93b5  cmp     ax, 19h
0x1808e93b9  ja      short loc_1808E93C8
0x1808e93bb  add     r8w, 20h ; ' '
0x1808e93c0  cmp     cx, 19h
0x1808e93c4  ja      short loc_1808E93D2
0x1808e93c6  jmp     short loc_1808E93CE
0x1808e93c8  cmp     cx, 19h
0x1808e93cc  ja      short loc_1808E9438
0x1808e93ce  add     dx, 20h ; ' '
0x1808e93d2  cmp     r8w, dx
0x1808e93d6  jnz     short loc_1808E9438
0x1808e93d8  movzx   r8d, word ptr [r10+2]
0x1808e93dd  add     r10, 2
0x1808e93e1  add     r9, 2
0x1808e93e5  test    r8w, r8w
0x1808e93e9  jnz     short loc_1808E93A4
0x1808e93eb  movzx   eax, word ptr [r9]
0x1808e93ef  neg     ax
0x1808e93f2  sbb     esi, esi
0x1808e93f4  movzx   r8d, word ptr [r14]
0x1808e93f8  lea     r9, aIexploreExe; "iexplore.exe"
0x1808e93ff  test    r8w, r8w
0x1808e9403  jz      loc_1808E94B7
0x1808e9409  nop     dword ptr [rax+00000000h]
0x1808e9410  movzx   edx, word ptr [r9]
0x1808e9414  cmp     r8w, dx
0x1808e9418  jz      loc_1808E94A0
0x1808e941e  lea     eax, [r8-41h]
0x1808e9422  lea     ecx, [rdx-41h]
0x1808e9425  cmp     ax, 19h
0x1808e9429  ja      short loc_1808E9488
0x1808e942b  add     r8w, 20h ; ' '
0x1808e9430  cmp     cx, 19h
0x1808e9434  ja      short loc_1808E9496
0x1808e9436  jmp     short loc_1808E9492
0x1808e9438  movzx   ecx, dx
0x1808e943b  movzx   eax, r8w
0x1808e943f  or      ecx, eax
0x1808e9441  test    ecx, 0FFFFFF80h
0x1808e9447  jnz     short loc_1808E9458
0x1808e9449  cmp     r8w, dx
0x1808e944d  jbe     short loc_1808E9454
0x1808e944f  mov     esi, r13d
0x1808e9452  jmp     short loc_1808E93F4
0x1808e9454  mov     esi, ebx
0x1808e9456  jmp     short loc_1808E93F4
0x1808e9458  mov     [rsp+1720h+cchCount2], ebx; cchCount2
0x1808e945c  mov     r8, r10; lpString1
0x1808e945f  mov     [rsp+1720h+lpnLengthNeeded], r9; lpString2
0x1808e9464  mov     edx, 31001h; dwCmpFlags
0x1808e9469  mov     r9d, ebx; cchCount1
0x1808e946c  xor     ecx, ecx; Locale
0x1808e946e  call    cs:__imp_CompareStringW
0x1808e9474  test    eax, eax
0x1808e9476  jle     short loc_1808E9480
0x1808e9478  lea     esi, [rax-2]
0x1808e947b  jmp     loc_1808E93F4
0x1808e9480  mov     esi, r15d
0x1808e9483  jmp     loc_1808E93F4
0x1808e9488  cmp     cx, 19h
0x1808e948c  ja      loc_1808E95B8
0x1808e9492  add     dx, 20h ; ' '
0x1808e9496  cmp     r8w, dx
0x1808e949a  jnz     loc_1808E95B8
0x1808e94a0  movzx   r8d, word ptr [rdi+2]
0x1808e94a5  add     rdi, 2
0x1808e94a9  add     r9, 2
0x1808e94ad  test    r8w, r8w
0x1808e94b1  jnz     loc_1808E9410
0x1808e94b7  movzx   eax, word ptr [r9]
0x1808e94bb  neg     ax
0x1808e94be  sbb     r15d, r15d
0x1808e94c1  test    esi, esi
0x1808e94c3  jz      short loc_1808E94CE
0x1808e94c5  test    r15d, r15d
0x1808e94c8  jnz     loc_1808E9B31
0x1808e94ce  mov     rcx, r14
0x1808e94d1  call    ShouldShowToastThrottled
0x1808e94d6  test    al, al
0x1808e94d8  jz      loc_1808E9B31
0x1808e94de  lea     rax, aMicrosoftInter_1; "Microsoft.InternetExplorer"
0x1808e94e5  test    esi, esi
0x1808e94e7  lea     rdi, aMicrosoftMshta; "Microsoft.MSHTA"
0x1808e94ee  mov     edx, 2; csidl
0x1808e94f3  cmovnz  rdi, rax
0x1808e94f7  lea     rax, [rbp+1620h+pszPath]
0x1808e94fe  xor     r9d, r9d; dwFlags
0x1808e9501  mov     [rsp+1720h+lpnLengthNeeded], rax; pszPath
0x1808e9506  xor     r8d, r8d; hToken
0x1808e9509  xor     ecx, ecx; hwnd
0x1808e950b  call    cs:__imp_SHGetFolderPathW
0x1808e9511  test    eax, eax
0x1808e9513  js      short loc_1808E954E
0x1808e9515  mov     r9, r14
0x1808e9518  lea     r8, aSLnk; "%s.lnk"
0x1808e951f  mov     edx, 104h; unsigned __int64
0x1808e9524  lea     rcx, [rbp+1620h+var_1470]; unsigned __int16 *
0x1808e952b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1808e9530  test    eax, eax
0x1808e9532  js      short loc_1808E954E
0x1808e9534  mov     r9, rdi
0x1808e9537  lea     r8, [rbp+1620h+Filename]
0x1808e953b  lea     rdx, [rbp+1620h+var_1470]
0x1808e9542  lea     rcx, [rbp+1620h+pszPath]
0x1808e9549  call    CreateShortcutForExe
0x1808e954e  lea     r9, [rbp+1620h+string]; string
0x1808e9552  mov     [rsp+1720h+var_16F0], r12
0x1808e9557  lea     r8, [rsp+1720h+hstringHeader]; hstringHeader
0x1808e955c  mov     [rbp+1620h+string], r12
0x1808e9560  mov     edx, 31h ; '1'; length
0x1808e9565  lea     rcx, ?RuntimeClass_Windows_UI_Notifications_ToastNotificationManager@@3QBGB; "Windows.UI.Notifications.ToastNotificat"...
0x1808e956c  call    cs:__imp_WindowsCreateStringReference
0x1808e9572  test    eax, eax
0x1808e9574  js      loc_1808E9B62
0x1808e957a  mov     rcx, [rbp+1620h+string]
0x1808e957e  lea     r8, [rsp+1720h+var_16F0]
0x1808e9583  lea     rdx, _GUID_50ac103f_d235_4598_bbef_98fe4d1a3ad4
0x1808e958a  call    cs:__imp_RoGetActivationFactory
0x1808e9590  mov     esi, eax
0x1808e9592  test    eax, eax
0x1808e9594  jns     short loc_1808E9606
0x1808e9596  mov     rcx, [rsp+1720h+var_16F0]
0x1808e959b  test    rcx, rcx
0x1808e959e  jz      short loc_1808E95B1
0x1808e95a0  mov     [rsp+1720h+var_16F0], r12
0x1808e95a5  mov     rdx, [rcx]
0x1808e95a8  mov     rax, [rdx+10h]
0x1808e95ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808e95b1  mov     eax, esi
0x1808e95b3  jmp     loc_1808E9B34
0x1808e95b8  movzx   ecx, dx
0x1808e95bb  movzx   eax, r8w
0x1808e95bf  or      ecx, eax
0x1808e95c1  test    ecx, 0FFFFFF80h
0x1808e95c7  jnz     short loc_1808E95D9
0x1808e95c9  cmp     r8w, dx
0x1808e95cd  mov     r15d, ebx
0x1808e95d0  cmova   r15d, r13d
0x1808e95d4  jmp     loc_1808E94C1
0x1808e95d9  mov     [rsp+1720h+cchCount2], ebx; cchCount2
0x1808e95dd  mov     r8, rdi; lpString1
0x1808e95e0  mov     [rsp+1720h+lpnLengthNeeded], r9; lpString2
0x1808e95e5  mov     edx, 31001h; dwCmpFlags
0x1808e95ea  mov     r9d, ebx; cchCount1
0x1808e95ed  xor     ecx, ecx; Locale
0x1808e95ef  call    cs:__imp_CompareStringW
0x1808e95f5  test    eax, eax
0x1808e95f7  jle     loc_1808E94C1
0x1808e95fd  lea     r15d, [rax-2]
0x1808e9601  jmp     loc_1808E94C1
0x1808e9606  mov     rsi, [rsp+1720h+var_16F0]
0x1808e960b  mov     rdx, rbx
0x1808e960e  mov     [rsp+1720h+var_16E8], r12
0x1808e9613  mov     r14, [rsi]
0x1808e9616  mov     [rbp+1620h+string], r12
0x1808e961a  nop     word ptr [rax+rax+00h]
0x1808e9620  inc     rdx; int
0x1808e9623  cmp     [rdi+rdx*2], r12w
0x1808e9628  jnz     short loc_1808E9620
0x1808e962a  mov     r15d, 0FFFFFFFFh
0x1808e9630  cmp     rdx, r15
0x1808e9633  ja      loc_1808E9B57
0x1808e9639  lea     eax, [rdx+1]
0x1808e963c  cmp     eax, edx
0x1808e963e  jb      loc_1808E9BA0
0x1808e9644  lea     r9, [rbp+1620h+string]; string
0x1808e9648  mov     rcx, rdi; sourceString
0x1808e964b  lea     r8, [rsp+1720h+hstringHeader]; hstringHeader
0x1808e9650  call    cs:__imp_WindowsCreateStringReference
0x1808e9656  test    eax, eax
0x1808e9658  js      loc_1808E9B6A
0x1808e965e  mov     rdx, [rbp+1620h+string]
0x1808e9662  lea     r8, [rsp+1720h+var_16E8]
0x1808e9667  mov     rax, [r14+38h]
0x1808e966b  mov     rcx, rsi
0x1808e966e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808e9673  mov     edi, eax
0x1808e9675  test    eax, eax
0x1808e9677  jns     short loc_1808E96B6
0x1808e9679  mov     rcx, [rsp+1720h+var_16E8]
0x1808e967e  test    rcx, rcx
0x1808e9681  jz      short loc_1808E9694
0x1808e9683  mov     [rsp+1720h+var_16E8], r12
0x1808e9688  mov     rdx, [rcx]
0x1808e968b  mov     rax, [rdx+10h]
0x1808e968f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808e9694  mov     rcx, [rsp+1720h+var_16F0]
0x1808e9699  test    rcx, rcx
0x1808e969c  jz      short loc_1808E96AF
0x1808e969e  mov     [rsp+1720h+var_16F0], r12
0x1808e96a3  mov     rax, [rcx]
0x1808e96a6  mov     rax, [rax+10h]
0x1808e96aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808e96af  mov     eax, edi
0x1808e96b1  jmp     loc_1808E9B34
0x1808e96b6  lea     r8, aToastActivatio; "<toast activationType='protocol' launch"...
0x1808e96bd  mov     edx, 800h; unsigned __int64
0x1808e96c2  lea     rcx, [rbp+1620h+sourceString]; unsigned __int16 *
0x1808e96c9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1808e96ce  mov     edi, eax
0x1808e96d0  test    eax, eax
0x1808e96d2  jns     short loc_1808E9711
0x1808e96d4  mov     rcx, [rsp+1720h+var_16E8]
0x1808e96d9  test    rcx, rcx
0x1808e96dc  jz      short loc_1808E96EF
0x1808e96de  mov     [rsp+1720h+var_16E8], r12
0x1808e96e3  mov     rdx, [rcx]
0x1808e96e6  mov     rax, [rdx+10h]
0x1808e96ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808e96ef  mov     rcx, [rsp+1720h+var_16F0]
  ... truncated ...
```
