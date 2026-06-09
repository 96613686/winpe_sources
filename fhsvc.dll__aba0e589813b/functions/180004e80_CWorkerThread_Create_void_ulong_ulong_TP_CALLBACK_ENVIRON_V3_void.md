# CWorkerThread::Create(void *,ulong,ulong,_TP_CALLBACK_ENVIRON_V3 *,void *)

- ea: `0x180004e80`
- end: `0x1800062aa`
- name: `?Create@CWorkerThread@@QEAAJPEAXKKPEAU_TP_CALLBACK_ENVIRON_V3@@0@Z`
- size: `5162`
- prototype: `__int64 __fastcall(LPVOID *ppv, HANDLE hSourceHandle, int, int, struct _TP_CALLBACK_ENVIRON_V3 *pcbe, void *)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180003f00`
- `0x180007330`

## callees

- `0x180004e80`
- `0x180008b30`
- `0x18000a360`
- `0x18000b838`
- `0x18000bc2c`
- `0x18000ca14`
- `0x18000d840`
- `0x18000d970`
- `0x18000daf0`
- `0x180010158`
- `0x180010288`
- `0x1800107ac`
- `0x180010b08`
- `0x180010bac`
- `0x180010d28`
- `0x180011980`
- `0x180013010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x1800054dc`
- `ADVAPI32!SetThreadToken` at `0x1800056bf`
- `ADVAPI32!SetThreadToken` at `0x180005b63`
- `ADVAPI32!SetThreadToken` at `0x180005dbe`
- `ADVAPI32!SetThreadToken` at `0x180006101`
- `ADVAPI32!SetThreadToken` at `0x1800054dc`
- `ADVAPI32!SetThreadToken` at `0x1800056bf`
- `ADVAPI32!SetThreadToken` at `0x180005b63`
- `ADVAPI32!SetThreadToken` at `0x180005dbe`
- `ADVAPI32!SetThreadToken` at `0x180006101`
- `KERNEL32!GetCurrentProcess` at `0x180004f53`
- `KERNEL32!GetCurrentProcess` at `0x180004f5c`
- `KERNEL32!GetCurrentProcess` at `0x180004f53`
- `KERNEL32!GetCurrentProcess` at `0x180004f5c`
- `KERNEL32!GetLastError` at `0x180004f98`
- `KERNEL32!GetLastError` at `0x1800054ea`
- `KERNEL32!GetLastError` at `0x1800056cd`
- `KERNEL32!GetLastError` at `0x180005b71`
- `KERNEL32!GetLastError` at `0x180005dcc`
- `KERNEL32!GetLastError` at `0x180005f97`
- `KERNEL32!GetLastError` at `0x18000611d`
- `KERNEL32!GetLastError` at `0x180004f98`
- `KERNEL32!GetLastError` at `0x1800054ea`
- `KERNEL32!GetLastError` at `0x1800056cd`
- `KERNEL32!GetLastError` at `0x180005b71`
- `KERNEL32!GetLastError` at `0x180005dcc`
- `KERNEL32!GetLastError` at `0x180005f97`
- `KERNEL32!GetLastError` at `0x18000611d`
- `KERNEL32!DuplicateHandle` at `0x180004f8a`
- `KERNEL32!DuplicateHandle` at `0x180004f8a`
- `KERNEL32!CreateThreadpoolWork` at `0x180005f84`
- `KERNEL32!CreateThreadpoolWork` at `0x180005f84`
- `OLEAUT32!__imp_SysFreeString` at `0x180004fe4`
- `OLEAUT32!__imp_SysFreeString` at `0x180004ff0`
- `OLEAUT32!__imp_SysFreeString` at `0x180004ffc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000511e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000512a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005136`
- `OLEAUT32!__imp_SysFreeString` at `0x18000519e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800051aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800051b6`
- `OLEAUT32!__imp_SysFreeString` at `0x180005256`
- `OLEAUT32!__imp_SysFreeString` at `0x180005262`
- `OLEAUT32!__imp_SysFreeString` at `0x18000526e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000530b`
- `OLEAUT32!__imp_SysFreeString` at `0x180005317`
- `OLEAUT32!__imp_SysFreeString` at `0x180005323`
- `OLEAUT32!__imp_SysFreeString` at `0x18000538f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000539b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800053a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000540f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000541b`
- `OLEAUT32!__imp_SysFreeString` at `0x180005427`
- `OLEAUT32!__imp_SysFreeString` at `0x180005490`
- `OLEAUT32!__imp_SysFreeString` at `0x18000549c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800054a8`
- `OLEAUT32!__imp_SysFreeString` at `0x180005536`
- `OLEAUT32!__imp_SysFreeString` at `0x180005542`
- `OLEAUT32!__imp_SysFreeString` at `0x18000554e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800055c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800055cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800055d8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000567e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000568a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005696`
- `OLEAUT32!__imp_SysFreeString` at `0x180005719`
- `OLEAUT32!__imp_SysFreeString` at `0x180005725`
- `OLEAUT32!__imp_SysFreeString` at `0x180005731`
- `OLEAUT32!__imp_SysFreeString` at `0x1800057aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800057b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800057c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000583e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000584a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005856`
- `OLEAUT32!__imp_SysFreeString` at `0x1800058db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800058e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800058f3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800059db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800059e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800059f3`
- `OLEAUT32!__imp_SysFreeString` at `0x180005aec`
- `OLEAUT32!__imp_SysFreeString` at `0x180005af8`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b04`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b50`
- `OLEAUT32!__imp_SysFreeString` at `0x180005bbd`
- `OLEAUT32!__imp_SysFreeString` at `0x180005bc9`
- `OLEAUT32!__imp_SysFreeString` at `0x180005bd5`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c5e`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c76`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d02`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d0e`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e11`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e1d`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e29`
- `OLEAUT32!__imp_SysFreeString` at `0x180005eac`
- `OLEAUT32!__imp_SysFreeString` at `0x180005eb8`
- `OLEAUT32!__imp_SysFreeString` at `0x180005ec4`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f48`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f54`
- `OLEAUT32!__imp_SysFreeString` at `0x180005fdc`
- `OLEAUT32!__imp_SysFreeString` at `0x180005fe8`
- `OLEAUT32!__imp_SysFreeString` at `0x180005ff4`
- `OLEAUT32!__imp_SysFreeString` at `0x180006024`
- `OLEAUT32!__imp_SysFreeString` at `0x180006030`
- `OLEAUT32!__imp_SysFreeString` at `0x18000603c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800060ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800060b7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800060c3`
- `OLEAUT32!__imp_SysFreeString` at `0x180004fe4`
- `OLEAUT32!__imp_SysFreeString` at `0x180004ff0`
- `OLEAUT32!__imp_SysFreeString` at `0x180004ffc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000511e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000512a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005136`
- `OLEAUT32!__imp_SysFreeString` at `0x18000519e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800051aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800051b6`
- `OLEAUT32!__imp_SysFreeString` at `0x180005256`
- `OLEAUT32!__imp_SysFreeString` at `0x180005262`
- `OLEAUT32!__imp_SysFreeString` at `0x18000526e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000530b`
- `OLEAUT32!__imp_SysFreeString` at `0x180005317`
- `OLEAUT32!__imp_SysFreeString` at `0x180005323`
- `OLEAUT32!__imp_SysFreeString` at `0x18000538f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000539b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800053a7`
- `OLEAUT32!__imp_SysFreeString` at `0x18000540f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000541b`
- `OLEAUT32!__imp_SysFreeString` at `0x180005427`
- `OLEAUT32!__imp_SysFreeString` at `0x180005490`
- `OLEAUT32!__imp_SysFreeString` at `0x18000549c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800054a8`
- `OLEAUT32!__imp_SysFreeString` at `0x180005536`
- `OLEAUT32!__imp_SysFreeString` at `0x180005542`
- `OLEAUT32!__imp_SysFreeString` at `0x18000554e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800055c0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800055cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800055d8`
- `OLEAUT32!__imp_SysFreeString` at `0x18000567e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000568a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005696`
- `OLEAUT32!__imp_SysFreeString` at `0x180005719`
- `OLEAUT32!__imp_SysFreeString` at `0x180005725`
- `OLEAUT32!__imp_SysFreeString` at `0x180005731`
- `OLEAUT32!__imp_SysFreeString` at `0x1800057aa`
- `OLEAUT32!__imp_SysFreeString` at `0x1800057b6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800057c2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000583e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000584a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005856`
- `OLEAUT32!__imp_SysFreeString` at `0x1800058db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800058e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800058f3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800059db`
- `OLEAUT32!__imp_SysFreeString` at `0x1800059e7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800059f3`
- `OLEAUT32!__imp_SysFreeString` at `0x180005aec`
- `OLEAUT32!__imp_SysFreeString` at `0x180005af8`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b04`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180005b50`
- `OLEAUT32!__imp_SysFreeString` at `0x180005bbd`
- `OLEAUT32!__imp_SysFreeString` at `0x180005bc9`
- `OLEAUT32!__imp_SysFreeString` at `0x180005bd5`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c5e`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c76`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d02`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d0e`
- `OLEAUT32!__imp_SysFreeString` at `0x180005d1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e11`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e1d`
- `OLEAUT32!__imp_SysFreeString` at `0x180005e29`
- `OLEAUT32!__imp_SysFreeString` at `0x180005eac`
- `OLEAUT32!__imp_SysFreeString` at `0x180005eb8`
- `OLEAUT32!__imp_SysFreeString` at `0x180005ec4`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f3c`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f48`
- `OLEAUT32!__imp_SysFreeString` at `0x180005f54`
- `OLEAUT32!__imp_SysFreeString` at `0x180005fdc`
- `OLEAUT32!__imp_SysFreeString` at `0x180005fe8`
- `OLEAUT32!__imp_SysFreeString` at `0x180005ff4`
- `OLEAUT32!__imp_SysFreeString` at `0x180006024`
- `OLEAUT32!__imp_SysFreeString` at `0x180006030`
- `OLEAUT32!__imp_SysFreeString` at `0x18000603c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800060ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1800060b7`
- `OLEAUT32!__imp_SysFreeString` at `0x1800060c3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005898`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005e70`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005898`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180005e70`

## string_xrefs

- `0x180004ef2`: `ImpersonationToken`
- `0x180005203`: `Unexpected Configuration Manager error encountered`
- `0x180006264`: `SUCCEEDED(hr) || (hr >= FHSVC_E_NOT_CONFIGURED && hr <= FHSVC_E_FATAL_CONFIG_ERROR)`

## pseudocode

```c
__int64 __fastcall CWorkerThread::Create(
        LPVOID *ppv,
        HANDLE hSourceHandle,
        int a3,
        int a4,
        struct _TP_CALLBACK_ENVIRON_V3 *pcbe,
        void *a6)
{
  LPVOID *v7; // r15
  int v8; // r14d
  HANDLE CurrentProcess; // rbx
  HANDLE v11; // rax
  HANDLE *v12; // r12
  __int64 v13; // r8
  signed int LastError; // eax
  unsigned int v15; // ebx
  int UserConfiguration; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rcx
  PVOID *v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  signed int v24; // eax
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  signed int v28; // eax
  int v29; // eax
  int v30; // eax
  LPVOID *v31; // r15
  HRESULT Instance; // eax
  __int64 v33; // rdx
  __int64 v34; // rcx
  int v35; // edx
  int v36; // ecx
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rcx
  int v40; // edx
  int v41; // ecx
  int v42; // ecx
  signed int v43; // eax
  char *v44; // rsi
  int v45; // eax
  int v46; // eax
  __int64 v47; // rax
  __int64 v48; // rcx
  signed int v49; // eax
  LPVOID *v50; // rsi
  HRESULT v51; // eax
  LPVOID v52; // r8
  int v53; // eax
  PTP_WORK ThreadpoolWork; // rax
  signed int v55; // eax
  __int64 v56; // r8
  PVOID *v57; // rcx
  signed int v58; // eax
  const wchar_t *v59; // rcx
  unsigned int v60; // eax
  __int64 v61; // rax
  int v62; // eax
  BSTR v63; // [rsp+40h] [rbp-D8h] BYREF
  BSTR v64; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v65; // [rsp+50h] [rbp-C8h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-C0h] BYREF
  int v67; // [rsp+60h] [rbp-B8h]
  unsigned int v68; // [rsp+68h] [rbp-B0h] BYREF
  PVOID pv; // [rsp+70h] [rbp-A8h]
  LPVOID *v70; // [rsp+78h] [rbp-A0h]
  _DWORD v71[6]; // [rsp+88h] [rbp-90h] BYREF
  _BYTE v72[16]; // [rsp+A0h] [rbp-78h] BYREF
  _DWORD *v73; // [rsp+B0h] [rbp-68h]
  __int64 v74; // [rsp+B8h] [rbp-60h]
  __int64 *v75; // [rsp+C0h] [rbp-58h]
  __int64 v76; // [rsp+C8h] [rbp-50h]
  const wchar_t *v77; // [rsp+D0h] [rbp-48h]
  int v78; // [rsp+D8h] [rbp-40h]
  int v79; // [rsp+DCh] [rbp-3Ch]

  v7 = ppv;
  pv = ppv;
  v70 = ppv;
  v8 = -2147467259;
  v67 = -2147467259;
  if ( !hSourceHandle )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
        "ImpersonationToken");
    return 2147942487LL;
  }
  v68 = 0;
  v65 = 0;
  v64 = 0;
  v63 = 0;
  bstrString = 0;
  *((_DWORD *)ppv + 17) = a3;
  *((_DWORD *)ppv + 16) = a4;
  ppv[7] = a6;
  CurrentProcess = GetCurrentProcess();
  v11 = GetCurrentProcess();
  v12 = v7 + 4;
  if ( !DuplicateHandle(v11, hSourceHandle, CurrentProcess, v7 + 4, 0, 0, 2u) )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids, v15);
    SysFreeString(bstrString);
    SysFreeString(v63);
    SysFreeString(v64);
    if ( v65 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    goto LABEL_212;
  }
  if ( (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(FH_SERVICE_PROVIDER_GUID_Context, ConfigurationLoadStart, v13, 1, v71);
  UserConfiguration = LoadUserConfiguration(*v12, v7, (__int64)(v7 + 3), 0);
  v8 = UserConfiguration;
  v67 = UserConfiguration;
  if ( UserConfiguration < 0 && (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
  {
    v71[0] = UserConfiguration;
    v73 = v71;
    v74 = 4;
    v75 = &qword_1800159E8;
    v76 = 2;
    McGenEventWrite_EventWriteTransfer(FH_SERVICE_PROVIDER_GUID_Context, ConfigurationLoadStop, v19, 3, v72);
  }
  if ( v8 != -2147220735 )
  {
    if ( v8 == -2147220736 )
    {
      v15 = -2147219964;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
          2147747332LL);
      SysFreeString(bstrString);
      SysFreeString(v63);
      SysFreeString(v64);
      if ( v65 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
      goto LABEL_212;
    }
    v15 = v8;
    if ( v8 < 0 )
    {
      v21 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_ss(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            (unsigned int)&WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
            (unsigned int)"SUCCEEDED(hr)",
            (__int64)"Unexpected Configuration Manager error encountered");
          v21 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 1) != 0 )
          WPP_SF_d(v21[2], 15, &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids, (unsigned int)v8);
      }
      SysFreeString(bstrString);
      SysFreeString(v63);
      SysFreeString(v64);
      v20 = v65;
      if ( v65 )
        goto LABEL_24;
      goto LABEL_212;
    }
    v67 = -2147467259;
    if ( (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
      McTemplateU0dz_EventWriteTransfer(v18, v17, (unsigned int)v8, v7[3]);
    v22 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)*v7 + 80LL))(*v7, &v68);
    v8 = v22;
    v67 = v22;
    if ( v22 < 0 )
    {
      v15 = v22;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)&WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
          (unsigned int)v7[3],
          v22);
      SysFreeString(bstrString);
      SysFreeString(v63);
      SysFreeString(v64);
      if ( !v65 )
        goto LABEL_212;
      goto LABEL_89;
    }
    switch ( v68 )
    {
      case 0u:
        v15 = -2147219966;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            (unsigned int)&WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
            (unsigned int)v7[3],
            2);
        SysFreeString(bstrString);
        SysFreeString(v63);
        SysFreeString(v64);
        v23 = v65;
        if ( !v65 )
          goto LABEL_212;
        goto LABEL_97;
      case 1u:
        v15 = -2147219965;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            (unsigned int)&WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
            (unsigned int)v7[3],
            3);
        SysFreeString(bstrString);
        SysFreeString(v63);
        SysFreeString(v64);
        if ( !v65 )
          goto LABEL_212;
        goto LABEL_89;
      case 3u:
        v15 = -2147219963;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            (unsigned int)&WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
            (unsigned int)v7[3],
            5);
        SysFreeString(bstrString);
        SysFreeString(v63);
        SysFreeString(v64);
        v23 = v65;
        if ( !v65 )
          goto LABEL_212;
        goto LABEL_97;
    }
    v8 = -2147467259;
    v67 = -2147467259;
    if ( SetThreadToken(0, *v12) )
    {
      v25 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)*v7 + 160LL))(*v7);
      v15 = v25;
      if ( v25 >= 0 )
      {
        if ( (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(v26, ConfigurationSaveStart, v7[3]);
        v15 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)*v7 + 40LL))(*v7);
        if ( (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
          McTemplateU0z_EventWriteTransfer(v27, ConfigurationSaveStop, v7[3]);
        if ( (v15 & 0x80000000) == 0 )
        {
          if ( SetThreadToken(0, *v12) )
          {
            v29 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, BSTR *))(*(_QWORD *)*v7 + 192LL))(*v7, 0, &v64);
            v15 = v29;
            if ( v29 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  24,
                  &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
                  (unsigned int)v29);
              SysFreeString(bstrString);
              SysFreeString(v63);
              SysFreeString(v64);
              if ( v65 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
              goto LABEL_212;
            }
            v30 = (*(__int64 (__fastcall **)(LPVOID, __int64, BSTR *))(*(_QWORD *)*v7 + 192LL))(*v7, 1, &v63);
            v15 = v30;
            if ( v30 >= 0 )
            {
              v31 = v7 + 1;
              Instance = CoCreateInstance(&CLSID_FhCatalog, 0, 0x17u, &GUID_fa1e716f_0897_47d0_bb3c_51012844df49, v31);
              v15 = Instance;
              if ( Instance < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    26,
                    &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
                    (unsigned int)Instance);
                SysFreeString(bstrString);
                SysFreeString(v63);
                SysFreeString(v64);
                if ( v65 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                v7 = (LPVOID *)pv;
                goto LABEL_212;
              }
              if ( (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
                McTemplateU0zz_EventWriteTransfer(v34, v33, v64, v63);
              v8 = (*(__int64 (__fastcall **)(LPVOID, BSTR, BSTR, _QWORD))(*(_QWORD *)*v31 + 32LL))(*v31, v64, v63, 0);
              v67 = v8;
              v15 = v8;
              if ( (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
                McTemplateU0dzz_EventWriteTransfer(v36, v35, v8, (_DWORD)v64, (__int64)v63);
              if ( v8 == -2147220210 )
              {
                v37 = (*(__int64 (__fastcall **)(LPVOID, BSTR, BSTR))(*(_QWORD *)*v31 + 64LL))(*v31, v64, v63);
                v15 = v37;
                if ( v37 < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      27,
                      &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
                      (unsigned int)v37);
                  SysFreeString(bstrString);
                  SysFreeString(v63);
                  SysFreeString(v64);
                  if ( v65 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                  v7 = (LPVOID *)pv;
                  goto LABEL_212;
                }
                if ( (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
                  McTemplateU0zz_EventWriteTransfer(v39, v38, v64, v63);
                v8 = (*(__int64 (__fastcall **)(LPVOID, BSTR, BSTR, _QWORD))(*(_QWORD *)*v31 + 32LL))(*v31, v64, v63, 0);
                v67 = v8;
                v15 = v8;
                if ( (Microsoft_Windows_FileHistory_ServiceEnableBits & 1) != 0 )
                  McTemplateU0dzz_EventWriteTransfer(v41, v40, v8, (_DWORD)v64, (__int64)v63);
              }
              if ( v15 + 2147220219 <= 9 && (v42 = 917, _bittest(&v42, v15 + 2147220219)) || v15 == -2147219969 )
              {
                v15 = -2147219964;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_SSd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    28,
                    (unsigned int)&WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
                    (_DWORD)v64,
                    (__int64)v63,
                    4);
                SysFreeString(bstrString);
                SysFreeString(v63);
                SysFreeString(v64);
                if ( v65 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                v7 = (LPVOID *)pv;
                goto LABEL_212;
              }
              if ( (v15 & 0x80000000) != 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_SSd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    29,
                    (unsigned int)&WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
                    (_DWORD)v64,
                    (__int64)v63,
                    v15);
                SysFreeString(bstrString);
                SysFreeString(v63);
                SysFreeString(v64);
                if ( v65 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                v7 = (LPVOID *)pv;
                goto LABEL_212;
              }
              v8 = -2147467259;
              v67 = -2147467259;
              SysFreeString(v64);
              v64 = 0;
              SysFreeString(v63);
              v63 = 0;
              if ( !SetThreadToken(0, 0) )
              {
                v43 = GetLastError();
                v15 = v43;
                if ( v43 > 0 )
                  v15 = (unsigned __int16)v43 | 0x80070000;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    30,
                    &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
                    v15);
                SysFreeString(bstrString);
                SysFreeString(v63);
                SysFreeString(v64);
                if ( v65 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                v7 = (LPVOID *)pv;
                goto LABEL_212;
              }
              v44 = (char *)pv;
              v45 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)pv + 96LL))(*(_QWORD *)pv, &v65);
              v15 = v45;
              if ( v45 >= 0 )
              {
                v46 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR *))(*(_QWORD *)v65 + 24LL))(v65, 1, &bstrString);
                v15 = v46;
                if ( v46 < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      32,
                      &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
                      (unsigned int)v46);
                  SysFreeString(bstrString);
                  SysFreeString(v63);
                  SysFreeString(v64);
                  if ( v65 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                  v7 = (LPVOID *)pv;
                  goto LABEL_212;
                }
                v47 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                        v71,
                        bstrString);
                if ( !(unsigned int)CManagerThread::StartTargetVolumeTracking(v48, v47) )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids);
                  *((_DWORD *)v44 + 16) |= 1u;
                }
                if ( v65 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                  v65 = 0;
                }
              }
              else if ( v45 != -2147023728 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    31,
                    &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
                    (unsigned int)v45);
                SysFreeString(bstrString);
                SysFreeString(v63);
                SysFreeString(v64);
                if ( v65 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                v7 = (LPVOID *)pv;
                goto LABEL_212;
              }
              if ( !SetThreadToken(0, *v12) )
              {
                v49 = GetLastError();
                v15 = v49;
                if ( v49 > 0 )
                  v15 = (unsigned __int16)v49 | 0x80070000;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    34,
                    &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
                    v15);
                SysFreeString(bstrString);
                SysFreeString(v63);
                SysFreeString(v64);
                if ( v65 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                v7 = (LPVOID *)pv;
                goto LABEL_212;
              }
              v50 = (LPVOID *)(v44 + 16);
              v51 = CoCreateInstance(&CLSID_FhEngineBackup, 0, 0x17u, &GUID_e49f7e50_c070_11df_ac23_18a90531a85a, v50);
              v15 = v51;
              if ( v51 < 0 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    35,
                    &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
                    (unsigned int)v51);
                SysFreeString(bstrString);
                SysFreeString(v63);
                SysFreeString(v64);
                if ( v65 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                v7 = (LPVOID *)pv;
                goto LABEL_212;
              }
              v52 = *v31;
              v7 = (LPVOID *)pv;
              v53 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, LPVOID))(*(_QWORD *)*v50 + 24LL))(
                      *v50,
                      *(_QWORD *)pv,
                      v52);
              v15 = v53;
              if ( v53 >= 0 )
              {
                ThreadpoolWork = CreateThreadpoolWork(CWorkerThread::WorkCallback, v7, pcbe);
                v7[5] = ThreadpoolWork;
                if ( ThreadpoolWork )
                {
                  *((_DWORD *)v7 + 12) = 0;
                  SysFreeString(bstrString);
                  SysFreeString(v63);
                  SysFreeString(v64);
                  if ( !v65 )
                    goto LABEL_212;
                }
                else
                {
                  v55 = GetLastError();
                  v15 = v55;
                  if ( v55 > 0 )
                    v15 = (unsigned __int16)v55 | 0x80070000;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      37,
                      &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
                      v15);
                  SysFreeString(bstrString);
                  SysFreeString(v63);
                  SysFreeString(v64);
                  if ( !v65 )
                    goto LABEL_212;
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    36,
                    &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
                    (unsigned int)v53);
                SysFreeString(bstrString);
                SysFreeString(v63);
                SysFreeString(v64);
                if ( !v65 )
                  goto LABEL_212;
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  25,
                  &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
                  (unsigned int)v30);
              SysFreeString(bstrString);
              SysFreeString(v63);
              SysFreeString(v64);
              if ( !v65 )
                goto LABEL_212;
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
            goto LABEL_212;
          }
          v28 = GetLastError();
          v15 = v28;
          if ( v28 > 0 )
            v15 = (unsigned __int16)v28 | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids, v15);
          SysFreeString(bstrString);
          SysFreeString(v63);
          SysFreeString(v64);
          v23 = v65;
          if ( !v65 )
            goto LABEL_212;
LABEL_97:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v23);
          goto LABEL_212;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            22,
            (unsigned int)&WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
            (unsigned int)v7[3],
            v15);
        SysFreeString(bstrString);
        SysFreeString(v63);
        SysFreeString(v64);
        if ( !v65 )
          goto LABEL_212;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
            (unsigned int)v25);
        SysFreeString(bstrString);
        SysFreeString(v63);
        SysFreeString(v64);
        if ( !v65 )
          goto LABEL_212;
      }
    }
    else
    {
      v24 = GetLastError();
      v15 = v24;
      if ( v24 > 0 )
        v15 = (unsigned __int16)v24 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids, v15);
      SysFreeString(bstrString);
      SysFreeString(v63);
      SysFreeString(v64);
      if ( !v65 )
        goto LABEL_212;
    }
LABEL_89:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    goto LABEL_212;
  }
  v15 = -2147219967;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids, 2147747329LL);
  SysFreeString(bstrString);
  SysFreeString(v63);
  SysFreeString(v64);
  v20 = v65;
  if ( v65 )
LABEL_24:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v20);
LABEL_212:
  if ( SetThreadToken(0, 0) )
  {
LABEL_218:
    v57 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_219;
  }
  v57 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v58 = GetLastError();
    if ( v58 > 0 )
      v58 = (unsigned __int16)v58 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
      (unsigned int)v58);
    goto LABEL_218;
  }
LABEL_219:
  if ( (v15 & 0x80000000) != 0 )
  {
    if ( v15 == -2147219968 )
      goto LABEL_233;
    if ( v15 + 2147219967 > 2 )
    {
      if ( (Microsoft_Windows_FileHistory_CoreEnableBits & 2) != 0 )
      {
        v59 = (const wchar_t *)v7[3];
        v60 = v15;
        if ( v8 != -2147467259 )
          v60 = v8;
        v68 = v60;
        v71[0] = v15;
        v73 = v71;
        v74 = 4;
        v75 = (__int64 *)&v68;
        v76 = 4;
        if ( v59 )
        {
          v61 = -1;
          do
            ++v61;
          while ( v59[v61] );
          v62 = 2 * v61 + 2;
        }
        else
        {
          v62 = 10;
          v59 = L"NULL";
        }
        v77 = v59;
        v78 = v62;
        v79 = 0;
        McGenEventWrite_EventWriteTransfer(FH_CORE_PROVIDER_GUID_Context, CycleFailure_Initialization, v56, 4, v72);
        v57 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v15 + 2147219967 > 3 )
      {
LABEL_233:
        if ( v57 != &WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 4) != 0 )
          WPP_SF_s(
            v57[2],
            40,
            &WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids,
            "SUCCEEDED(hr) || (hr >= FHSVC_E_NOT_CONFIGURED && hr <= FHSVC_E_FATAL_CONFIG_ERROR)");
      }
    }
  }
  return v15;
}

```

## disassembly

```asm
0x180004e80  mov     [rsp+arg_10], rbx
0x180004e85  mov     [rsp+arg_18], rsi
0x180004e8a  push    rdi
0x180004e8b  push    r12
0x180004e8d  push    r13
0x180004e8f  push    r14
0x180004e91  push    r15
0x180004e93  sub     rsp, 0F0h
0x180004e9a  mov     rax, cs:__security_cookie
0x180004ea1  xor     rax, rsp
0x180004ea4  mov     [rsp+118h+var_38], rax
0x180004eac  mov     rdi, rdx
0x180004eaf  mov     r15, rcx
0x180004eb2  mov     [rsp+118h+pv], rcx
0x180004eb7  mov     [rsp+118h+var_A0], rcx
0x180004ebc  mov     r13, [rsp+118h+pcbe]
0x180004ec4  mov     r14d, 80004005h
0x180004eca  mov     [rsp+118h+var_B8], r14d
0x180004ecf  test    rdx, rdx
0x180004ed2  jnz     short loc_180004F13
0x180004ed4  lea     rdi, WPP_GLOBAL_Control
0x180004edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ee2  cmp     rcx, rdi
0x180004ee5  jz      short loc_180004F09
0x180004ee7  test    byte ptr [rcx+1Ch], 1
0x180004eeb  jz      short loc_180004F09
0x180004eed  mov     edx, 0Ah
0x180004ef2  lea     r9, aImpersonationt; "ImpersonationToken"
0x180004ef9  lea     r8, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x180004f00  mov     rcx, [rcx+10h]
0x180004f04  call    WPP_SF_s
0x180004f09  mov     eax, 80070057h
0x180004f0e  jmp     loc_18000627D
0x180004f13  mov     [rsp+118h+var_B0], 0
0x180004f1b  mov     [rsp+118h+var_C8], 0
0x180004f24  mov     [rsp+118h+var_D0], 0
0x180004f2d  mov     [rsp+118h+var_D8], 0
0x180004f36  mov     [rsp+118h+bstrString], 0
0x180004f3f  mov     [rcx+44h], r8d
0x180004f43  mov     [rcx+40h], r9d
0x180004f47  mov     rax, [rsp+118h+arg_28]
0x180004f4f  mov     [rcx+38h], rax
0x180004f53  call    cs:__imp_GetCurrentProcess
0x180004f59  mov     rbx, rax
0x180004f5c  call    cs:__imp_GetCurrentProcess
0x180004f62  lea     r12, [r15+20h]
0x180004f66  mov     [rsp+118h+dwOptions], 2; dwOptions
0x180004f6e  mov     [rsp+118h+bInheritHandle], 0; bInheritHandle
0x180004f76  mov     [rsp+118h+dwDesiredAccess], 0; dwDesiredAccess
0x180004f7e  mov     r9, r12; lpTargetHandle
0x180004f81  mov     r8, rbx; hTargetProcessHandle
0x180004f84  mov     rdx, rdi; hSourceHandle
0x180004f87  mov     rcx, rax; hSourceProcessHandle
0x180004f8a  call    cs:__imp_DuplicateHandle
0x180004f90  test    eax, eax
0x180004f92  jnz     loc_18000501F
0x180004f98  call    cs:__imp_GetLastError
0x180004f9e  mov     ebx, eax
0x180004fa0  test    eax, eax
0x180004fa2  jle     short loc_180004FAD
0x180004fa4  movzx   ebx, ax
0x180004fa7  or      ebx, 80070000h
0x180004fad  lea     rdi, WPP_GLOBAL_Control
0x180004fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180004fbb  cmp     rcx, rdi
0x180004fbe  jz      short loc_180004FDF
0x180004fc0  test    byte ptr [rcx+1Ch], 1
0x180004fc4  jz      short loc_180004FDF
0x180004fc6  mov     edx, 0Bh
0x180004fcb  mov     r9d, ebx
0x180004fce  lea     r8, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x180004fd5  mov     rcx, [rcx+10h]
0x180004fd9  call    WPP_SF_d
0x180004fde  nop
0x180004fdf  mov     rcx, [rsp+118h+bstrString]; bstrString
0x180004fe4  call    cs:__imp_SysFreeString
0x180004fea  nop
0x180004feb  mov     rcx, [rsp+118h+var_D8]; bstrString
0x180004ff0  call    cs:__imp_SysFreeString
0x180004ff6  nop
0x180004ff7  mov     rcx, [rsp+118h+var_D0]; bstrString
0x180004ffc  call    cs:__imp_SysFreeString
0x180005002  nop
0x180005003  mov     rcx, [rsp+118h+var_C8]
0x180005008  test    rcx, rcx
0x18000500b  jz      short loc_18000501A
0x18000500d  mov     rax, [rcx]
0x180005010  mov     rax, [rax+10h]
0x180005014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005019  nop
0x18000501a  jmp     loc_1800060FD
0x18000501f  test    cs:Microsoft_Windows_FileHistory_ServiceEnableBits, 1
0x180005026  jz      short loc_18000504E
0x180005028  lea     rax, [rsp+118h+var_90]
0x180005030  mov     qword ptr [rsp+118h+dwDesiredAccess], rax
0x180005035  mov     r9d, 1
0x18000503b  lea     rdx, ConfigurationLoadStart
0x180005042  lea     rcx, FH_SERVICE_PROVIDER_GUID_Context
0x180005049  call    McGenEventWrite_EventWriteTransfer
0x18000504e  xor     r9d, r9d
0x180005051  lea     r8, [r15+18h]
0x180005055  mov     rdx, r15; ppv
0x180005058  mov     rcx, [r12]; Token
0x18000505c  call    ?LoadUserConfiguration@@YAJPEAXAEAV?$CComPtr@UIFhConfigMgrPriv@@@ATL@@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@PEAH@Z; LoadUserConfiguration(void *,ATL::CComPtr<IFhConfigMgrPriv> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,int *)
0x180005061  mov     r14d, eax
0x180005064  mov     [rsp+118h+var_B8], eax
0x180005068  test    eax, eax
0x18000506a  jns     short loc_1800050D9
0x18000506c  test    cs:Microsoft_Windows_FileHistory_ServiceEnableBits, 1
0x180005073  jz      short loc_1800050D9
0x180005075  mov     [rsp+118h+var_90], eax
0x18000507c  lea     rax, [rsp+118h+var_90]
0x180005084  mov     [rsp+118h+var_68], rax
0x18000508c  mov     [rsp+118h+var_60], 4
0x180005098  lea     rcx, qword_1800159E8
0x18000509f  mov     [rsp+118h+var_58], rcx
0x1800050a7  mov     [rsp+118h+var_50], 2
0x1800050b3  lea     rax, [rsp+118h+var_78]
0x1800050bb  mov     qword ptr [rsp+118h+dwDesiredAccess], rax
0x1800050c0  mov     r9d, 3
0x1800050c6  lea     rdx, ConfigurationLoadStop
0x1800050cd  lea     rcx, FH_SERVICE_PROVIDER_GUID_Context
0x1800050d4  call    McGenEventWrite_EventWriteTransfer
0x1800050d9  cmp     r14d, 80040301h
0x1800050e0  jnz     short loc_180005159
0x1800050e2  mov     ebx, 80040601h
0x1800050e7  lea     rdi, WPP_GLOBAL_Control
0x1800050ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050f5  cmp     rcx, rdi
0x1800050f8  jz      short loc_180005119
0x1800050fa  test    byte ptr [rcx+1Ch], 1
0x1800050fe  jz      short loc_180005119
0x180005100  mov     edx, 0Ch
0x180005105  mov     r9d, ebx
0x180005108  lea     r8, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x18000510f  mov     rcx, [rcx+10h]
0x180005113  call    WPP_SF_d
0x180005118  nop
0x180005119  mov     rcx, [rsp+118h+bstrString]; bstrString
0x18000511e  call    cs:__imp_SysFreeString
0x180005124  nop
0x180005125  mov     rcx, [rsp+118h+var_D8]; bstrString
0x18000512a  call    cs:__imp_SysFreeString
0x180005130  nop
0x180005131  mov     rcx, [rsp+118h+var_D0]; bstrString
0x180005136  call    cs:__imp_SysFreeString
0x18000513c  nop
0x18000513d  mov     rcx, [rsp+118h+var_C8]
0x180005142  test    rcx, rcx
0x180005145  jz      short loc_180005154
0x180005147  mov     rax, [rcx]
0x18000514a  mov     rax, [rax+10h]
0x18000514e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005153  nop
0x180005154  jmp     loc_1800060FD
0x180005159  cmp     r14d, 80040300h
0x180005160  jnz     short loc_1800051D9
0x180005162  mov     ebx, 80040604h
0x180005167  lea     rdi, WPP_GLOBAL_Control
0x18000516e  mov     rcx, cs:WPP_GLOBAL_Control
0x180005175  cmp     rcx, rdi
0x180005178  jz      short loc_180005199
0x18000517a  test    byte ptr [rcx+1Ch], 1
0x18000517e  jz      short loc_180005199
0x180005180  mov     edx, 0Dh
0x180005185  mov     r9d, ebx
0x180005188  lea     r8, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x18000518f  mov     rcx, [rcx+10h]
0x180005193  call    WPP_SF_d
0x180005198  nop
0x180005199  mov     rcx, [rsp+118h+bstrString]; bstrString
0x18000519e  call    cs:__imp_SysFreeString
0x1800051a4  nop
0x1800051a5  mov     rcx, [rsp+118h+var_D8]; bstrString
0x1800051aa  call    cs:__imp_SysFreeString
0x1800051b0  nop
0x1800051b1  mov     rcx, [rsp+118h+var_D0]; bstrString
0x1800051b6  call    cs:__imp_SysFreeString
0x1800051bc  nop
0x1800051bd  mov     rcx, [rsp+118h+var_C8]
0x1800051c2  test    rcx, rcx
0x1800051c5  jz      short loc_1800051D4
0x1800051c7  mov     rax, [rcx]
0x1800051ca  mov     rax, [rax+10h]
0x1800051ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051d3  nop
0x1800051d4  jmp     loc_1800060FD
0x1800051d9  mov     ebx, r14d
0x1800051dc  test    r14d, r14d
0x1800051df  jns     loc_180005291
0x1800051e5  lea     rdi, WPP_GLOBAL_Control
0x1800051ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800051f3  cmp     rcx, rdi
0x1800051f6  jz      short loc_180005251
0x1800051f8  test    byte ptr [rcx+1Ch], 4
0x1800051fc  jz      short loc_18000522D
0x1800051fe  mov     edx, 0Eh
0x180005203  lea     rax, aUnexpectedConf; "Unexpected Configuration Manager error "...
0x18000520a  mov     qword ptr [rsp+118h+dwDesiredAccess], rax
0x18000520f  lea     r9, aSucceededHr; "SUCCEEDED(hr)"
0x180005216  lea     r8, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x18000521d  mov     rcx, [rcx+10h]
0x180005221  call    WPP_SF_ss
0x180005226  mov     rcx, cs:WPP_GLOBAL_Control
0x18000522d  cmp     rcx, rdi
0x180005230  jz      short loc_180005251
0x180005232  test    byte ptr [rcx+1Ch], 1
0x180005236  jz      short loc_180005251
0x180005238  mov     edx, 0Fh
0x18000523d  mov     r9d, r14d
0x180005240  lea     r8, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x180005247  mov     rcx, [rcx+10h]
0x18000524b  call    WPP_SF_d
0x180005250  nop
0x180005251  mov     rcx, [rsp+118h+bstrString]; bstrString
0x180005256  call    cs:__imp_SysFreeString
0x18000525c  nop
0x18000525d  mov     rcx, [rsp+118h+var_D8]; bstrString
0x180005262  call    cs:__imp_SysFreeString
0x180005268  nop
0x180005269  mov     rcx, [rsp+118h+var_D0]; bstrString
0x18000526e  call    cs:__imp_SysFreeString
0x180005274  nop
0x180005275  mov     rcx, [rsp+118h+var_C8]
0x18000527a  test    rcx, rcx
0x18000527d  jz      short loc_18000528C
0x18000527f  mov     rax, [rcx]
0x180005282  mov     rax, [rax+10h]
0x180005286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000528b  nop
0x18000528c  jmp     loc_1800060FD
0x180005291  mov     [rsp+118h+var_B8], 80004005h
0x180005299  test    cs:Microsoft_Windows_FileHistory_ServiceEnableBits, 1
0x1800052a0  jz      short loc_1800052AE
0x1800052a2  mov     r9, [r15+18h]
0x1800052a6  mov     r8d, ebx
0x1800052a9  call    McTemplateU0dz_EventWriteTransfer
0x1800052ae  mov     rcx, [r15]
0x1800052b1  mov     rax, [rcx]
0x1800052b4  lea     rdx, [rsp+118h+var_B0]
0x1800052b9  mov     rax, [rax+50h]
0x1800052bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052c2  mov     r14d, eax
0x1800052c5  mov     [rsp+118h+var_B8], eax
0x1800052c9  test    eax, eax
0x1800052cb  jns     short loc_180005346
0x1800052cd  mov     ebx, eax
0x1800052cf  lea     rdi, WPP_GLOBAL_Control
0x1800052d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800052dd  cmp     rcx, rdi
0x1800052e0  jz      short loc_180005306
0x1800052e2  test    byte ptr [rcx+1Ch], 1
0x1800052e6  jz      short loc_180005306
0x1800052e8  mov     edx, 10h
0x1800052ed  mov     [rsp+118h+dwDesiredAccess], eax
0x1800052f1  mov     r9, [r15+18h]
0x1800052f5  lea     r8, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x1800052fc  mov     rcx, [rcx+10h]
0x180005300  call    WPP_SF_Sd
0x180005305  nop
0x180005306  mov     rcx, [rsp+118h+bstrString]; bstrString
0x18000530b  call    cs:__imp_SysFreeString
0x180005311  nop
0x180005312  mov     rcx, [rsp+118h+var_D8]; bstrString
0x180005317  call    cs:__imp_SysFreeString
0x18000531d  nop
0x18000531e  mov     rcx, [rsp+118h+var_D0]; bstrString
0x180005323  call    cs:__imp_SysFreeString
0x180005329  nop
0x18000532a  mov     rcx, [rsp+118h+var_C8]
0x18000532f  test    rcx, rcx
0x180005332  jz      short loc_180005341
0x180005334  mov     rax, [rcx]
0x180005337  mov     rax, [rax+10h]
0x18000533b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005340  nop
0x180005341  jmp     loc_1800060FD
0x180005346  mov     eax, [rsp+118h+var_B0]
0x18000534a  test    eax, eax
0x18000534c  jnz     short loc_1800053CA
0x18000534e  mov     ebx, 80040602h
0x180005353  lea     rdi, WPP_GLOBAL_Control
0x18000535a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005361  cmp     rcx, rdi
0x180005364  jz      short loc_18000538A
0x180005366  test    byte ptr [rcx+1Ch], 1
0x18000536a  jz      short loc_18000538A
0x18000536c  mov     edx, 11h
0x180005371  mov     [rsp+118h+dwDesiredAccess], ebx
0x180005375  mov     r9, [r15+18h]
0x180005379  lea     r8, WPP_35d9bebdd7d63c9467c96b30e14d7688_Traceguids
0x180005380  mov     rcx, [rcx+10h]
0x180005384  call    WPP_SF_Sd
0x180005389  nop
0x18000538a  mov     rcx, [rsp+118h+bstrString]; bstrString
0x18000538f  call    cs:__imp_SysFreeString
0x180005395  nop
0x180005396  mov     rcx, [rsp+118h+var_D8]; bstrString
0x18000539b  call    cs:__imp_SysFreeString
0x1800053a1  nop
  ... truncated ...
```
