# RealtimeProtection::DlpEngineUtils::CreateDlpCacheDirectories(void)

- ea: `0x1801a9a74`
- end: `0x1801aa77f`
- name: `?CreateDlpCacheDirectories@DlpEngineUtils@RealtimeProtection@@YAJXZ`
- size: `3339`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpEngineUtils *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18019d7f8`

## callees

- `0x180005c28`
- `0x18000a010`
- `0x180034420`
- `0x1800809d0`
- `0x18009351c`
- `0x1800b3710`
- `0x1800b8fcc`
- `0x18010474c`
- `0x180106620`
- `0x18010cb40`
- `0x18010ce3c`
- `0x1801458c0`
- `0x1801459c8`
- `0x1801a9a74`
- `0x1801b0464`

## import_xrefs

- `MpClient!MpFreeMemory` at `0x1801a9b35`
- `MpClient!MpFreeMemory` at `0x1801a9c25`
- `MpClient!MpFreeMemory` at `0x1801a9d0f`
- `MpClient!MpFreeMemory` at `0x1801a9fc1`
- `MpClient!MpFreeMemory` at `0x1801aa06e`
- `MpClient!MpFreeMemory` at `0x1801aa1db`
- `MpClient!MpFreeMemory` at `0x1801aa304`
- `MpClient!MpFreeMemory` at `0x1801aa43a`
- `MpClient!MpFreeMemory` at `0x1801aa611`
- `MpClient!MpFreeMemory` at `0x1801aa6df`
- `MpClient!MpFreeMemory` at `0x1801aa73b`
- `MpClient!MpFreeMemory` at `0x1801a9b35`
- `MpClient!MpFreeMemory` at `0x1801a9c25`
- `MpClient!MpFreeMemory` at `0x1801a9d0f`
- `MpClient!MpFreeMemory` at `0x1801a9fc1`
- `MpClient!MpFreeMemory` at `0x1801aa06e`
- `MpClient!MpFreeMemory` at `0x1801aa1db`
- `MpClient!MpFreeMemory` at `0x1801aa304`
- `MpClient!MpFreeMemory` at `0x1801aa43a`
- `MpClient!MpFreeMemory` at `0x1801aa611`
- `MpClient!MpFreeMemory` at `0x1801aa6df`
- `MpClient!MpFreeMemory` at `0x1801aa73b`
- `MpClient!MpConfigClose` at `0x1801a9c34`
- `MpClient!MpConfigClose` at `0x1801a9d1e`
- `MpClient!MpConfigClose` at `0x1801a9fd0`
- `MpClient!MpConfigClose` at `0x1801aa07d`
- `MpClient!MpConfigClose` at `0x1801aa1ea`
- `MpClient!MpConfigClose` at `0x1801aa313`
- `MpClient!MpConfigClose` at `0x1801aa449`
- `MpClient!MpConfigClose` at `0x1801aa620`
- `MpClient!MpConfigClose` at `0x1801aa6ee`
- `MpClient!MpConfigClose` at `0x1801aa74a`
- `MpClient!MpConfigClose` at `0x1801a9c34`
- `MpClient!MpConfigClose` at `0x1801a9d1e`
- `MpClient!MpConfigClose` at `0x1801a9fd0`
- `MpClient!MpConfigClose` at `0x1801aa07d`
- `MpClient!MpConfigClose` at `0x1801aa1ea`
- `MpClient!MpConfigClose` at `0x1801aa313`
- `MpClient!MpConfigClose` at `0x1801aa449`
- `MpClient!MpConfigClose` at `0x1801aa620`
- `MpClient!MpConfigClose` at `0x1801aa6ee`
- `MpClient!MpConfigClose` at `0x1801aa74a`
- `MpClient!MpConfigOpen` at `0x1801a9ade`
- `MpClient!MpConfigOpen` at `0x1801a9ade`
- `KERNEL32!GetLastError` at `0x1801aa54a`
- `KERNEL32!GetLastError` at `0x1801aa54a`

## string_xrefs

- `0x1801a9de2`: `Evidence directory creation failed error_`
- `0x1801a9e48`: `Directory Creation`
- `0x1801a9b3f`: `ProductAppDataPath`
- `0x1801a9b6a`: `DLPCache`
- `0x1801aa457`: `UserAgentApps`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpEngineUtils::CreateDlpCacheDirectories(
        RealtimeProtection::DlpEngineUtils *this)
{
  int v1; // eax
  unsigned int v2; // ebx
  int ValueString; // eax
  int v4; // eax
  const wchar_t *v5; // rdx
  const struct std::nothrow_t *v6; // rdx
  wchar_t *v7; // rbx
  int DirectoryIfNeeded; // eax
  unsigned int v9; // edi
  const struct std::nothrow_t *v10; // rdx
  int v12; // eax
  const wchar_t *v13; // rdx
  CommonUtil *v14; // rdi
  int v15; // eax
  unsigned int v16; // esi
  const struct std::nothrow_t *v17; // rdx
  int v18; // eax
  const wchar_t *v19; // rdx
  CommonUtil *v20; // rsi
  int v21; // eax
  unsigned int v22; // r15d
  LPCRITICAL_SECTION v23; // rdx
  void *v24; // r14
  int v25; // r9d
  int v26; // eax
  const wchar_t *v27; // rdx
  unsigned int v28; // r14d
  const struct std::nothrow_t *v29; // rdx
  int v30; // eax
  int v31; // eax
  const wchar_t *v32; // rdx
  CommonUtil *v33; // r15
  int v34; // eax
  unsigned int v35; // r12d
  const struct std::nothrow_t *v36; // rdx
  int v37; // eax
  const wchar_t *v38; // rdx
  CommonUtil *v39; // r12
  int v40; // eax
  unsigned int v41; // r13d
  const struct std::nothrow_t *v42; // rdx
  int v43; // eax
  const wchar_t *v44; // rdx
  CommonUtil *v45; // r13
  int v46; // eax
  const struct std::nothrow_t *v47; // rdx
  int v48; // eax
  const wchar_t *v49; // rdx
  CommonUtil *v50; // rcx
  int v51; // eax
  signed int LastError; // eax
  const struct std::nothrow_t *v53; // rdx
  const struct std::nothrow_t *v54; // rdx
  _BYTE v55[8]; // [rsp+B8h] [rbp-80h] BYREF
  __int64 v56; // [rsp+C0h] [rbp-78h] BYREF
  __int64 v57; // [rsp+C8h] [rbp-70h] BYREF
  __int64 v58; // [rsp+D0h] [rbp-68h] BYREF
  __int64 v59; // [rsp+D8h] [rbp-60h] BYREF
  __int64 v60; // [rsp+E0h] [rbp-58h] BYREF
  __int64 v61; // [rsp+E8h] [rbp-50h] BYREF
  __int64 v62; // [rsp+F0h] [rbp-48h] BYREF
  __int64 v63; // [rsp+F8h] [rbp-40h] BYREF
  __int64 v64; // [rsp+100h] [rbp-38h] BYREF
  wchar_t *v65; // [rsp+108h] [rbp-30h] BYREF
  __int64 v66; // [rsp+110h] [rbp-28h] BYREF
  wchar_t *v67; // [rsp+118h] [rbp-20h] BYREF
  CommonUtil *v68; // [rsp+120h] [rbp-18h] BYREF
  CommonUtil *v69; // [rsp+128h] [rbp-10h] BYREF
  CommonUtil *v70; // [rsp+130h] [rbp-8h] BYREF
  CommonUtil *v71; // [rsp+138h] [rbp+0h] BYREF
  CommonUtil *v72; // [rsp+140h] [rbp+8h] BYREF
  CommonUtil *v73; // [rsp+148h] [rbp+10h] BYREF
  CommonUtil *v74; // [rsp+150h] [rbp+18h] BYREF
  _OWORD v75[2]; // [rsp+158h] [rbp+20h] BYREF

  v66 = 0;
  v65 = 0;
  v67 = 0;
  v74 = 0;
  v73 = 0;
  v72 = 0;
  v71 = 0;
  v70 = 0;
  v69 = 0;
  v68 = 0;
  v1 = MpConfigOpen(L".", &v66);
  v2 = v1;
  if ( v1 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        188,
        (unsigned int)&WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)L".",
        v1);
LABEL_238:
    if ( v65 )
      MpFreeMemory(v65);
    if ( v66 )
      MpConfigClose();
    return v2;
  }
  ValueString = MpConfigGetValueString(v66, L"ProductAppDataPath", &v65);
  v2 = ValueString;
  if ( ValueString < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_SSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"ProductAppDataPath", ValueString);
    goto LABEL_238;
  }
  v4 = CommonUtil::NewSprintfW((CommonUtil *)&v67, (wchar_t **)L"%s\\%s", v65, L"DLPCache");
  v2 = v4;
  if ( v4 < 0 )
  {
    v6 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        190,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v4);
    if ( v67 )
      operator delete(v67, v6);
    goto LABEL_238;
  }
  v7 = v67;
  DirectoryIfNeeded = CommonUtil::UtilCreateDirectoryIfNeeded((CommonUtil *)v67, v5);
  v9 = DirectoryIfNeeded;
  if ( DirectoryIfNeeded < 0 )
  {
    v10 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        191,
        (unsigned int)&WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (_DWORD)v7,
        DirectoryIfNeeded);
LABEL_16:
    if ( v7 )
      operator delete(v7, v10);
    if ( v65 )
      MpFreeMemory(v65);
    if ( v66 )
      MpConfigClose();
    return v9;
  }
  v12 = CommonUtil::NewSprintfW((CommonUtil *)&v74, (wchar_t **)L"%s\\%s", v7, L"NetworkFilesMappingStubs");
  v9 = v12;
  if ( v12 < 0 )
  {
    v10 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        192,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v12);
    if ( v74 )
      operator delete(v74, v10);
    goto LABEL_16;
  }
  v14 = v74;
  v15 = CommonUtil::UtilCreateDirectoryIfNeeded(v74, v13);
  v16 = v15;
  if ( v15 < 0 )
  {
    v17 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        193,
        (unsigned int)&WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (_DWORD)v14,
        v15);
LABEL_33:
    if ( v14 )
      operator delete(v14, v17);
    if ( v7 )
      operator delete(v7, v17);
    if ( v65 )
      MpFreeMemory(v65);
    if ( v66 )
      MpConfigClose();
    return v16;
  }
  v18 = CommonUtil::NewSprintfW((CommonUtil *)&v73, (wchar_t **)L"%s\\%s", v7, L"FileEvidence");
  v16 = v18;
  if ( v18 < 0 )
  {
    v17 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        194,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v18);
    if ( v73 )
      operator delete(v73, v17);
    goto LABEL_33;
  }
  v20 = v73;
  v21 = CommonUtil::UtilCreateDirectoryIfNeeded(v73, v19);
  v22 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        195,
        (unsigned int)&WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (_DWORD)v20,
        v21);
    v67 = 0;
    CommonUtil::NewSprintfW(
      (CommonUtil *)&v67,
      (wchar_t **)L"%ls%#lx",
      L"Evidence directory creation failed error_",
      v22);
    v23 = g_pcsAsimovLock;
    v24 = v67;
    if ( g_pcsAsimovLock )
    {
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v75);
      if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
        && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
      {
        v57 = (__int64)L"Directory Creation";
        v56 = (__int64)v24;
        v64 = 0x2000000;
        LODWORD(v69) = *((_DWORD *)g_aAsimov + 18);
        LODWORD(v70) = *((_DWORD *)g_aAsimov + 17);
        LODWORD(v71) = *((_DWORD *)g_aAsimov + 16);
        LODWORD(v72) = *((unsigned __int8 *)g_aAsimov + 60);
        LODWORD(v73) = *((unsigned __int8 *)g_aAsimov + 59);
        LODWORD(v74) = *((unsigned __int8 *)g_aAsimov + 58);
        LODWORD(v68) = *((unsigned __int8 *)g_aAsimov + 57);
        LODWORD(v67) = *((unsigned __int8 *)g_aAsimov + 56);
        v58 = *((_QWORD *)g_aAsimov + 6);
        v59 = *((_QWORD *)g_aAsimov + 5);
        v60 = *((_QWORD *)g_aAsimov + 4);
        v61 = *((_QWORD *)g_aAsimov + 3);
        v62 = *((_QWORD *)g_aAsimov + 2);
        v63 = *((_QWORD *)g_aAsimov + 1);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
          v25,
          (int)&dword_1802C4424,
          (__int64)&v64,
          (__int64)&v63,
          (__int64)&v62,
          (__int64)&v61,
          (__int64)&v60,
          (__int64)&v59,
          (__int64)&v58,
          (__int64)&v67,
          (__int64)&v68,
          (__int64)&v74,
          (__int64)&v73,
          (__int64)&v72,
          (__int64)&v71,
          (__int64)&v70,
          (__int64)&v69,
          (__int64)&v57,
          (__int64)&v56);
      }
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v75);
    }
LABEL_57:
    if ( v24 )
      operator delete(v24, (const struct std::nothrow_t *)v23);
    if ( v20 )
      operator delete(v20, (const struct std::nothrow_t *)v23);
    if ( v14 )
      operator delete(v14, (const struct std::nothrow_t *)v23);
    if ( v7 )
      operator delete(v7, (const struct std::nothrow_t *)v23);
    if ( v65 )
      MpFreeMemory(v65);
    if ( v66 )
      MpConfigClose();
    return v22;
  }
  v26 = CommonUtil::NewSprintfW((CommonUtil *)&v72, (wchar_t **)L"%s\\%s", v7, L"SensitiveBuffer");
  v28 = v26;
  if ( v26 < 0 )
  {
    v29 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        196,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v26);
    if ( v72 )
      operator delete(v72, v29);
    if ( v20 )
      operator delete(v20, v29);
    if ( v14 )
      operator delete(v14, v29);
    if ( v7 )
      operator delete(v7, v29);
    if ( v65 )
      MpFreeMemory(v65);
    if ( v66 )
      MpConfigClose();
    return v28;
  }
  v24 = v72;
  v30 = CommonUtil::UtilCreateDirectoryIfNeeded(v72, v27);
  v22 = v30;
  if ( v30 < 0 )
  {
    v23 = (LPCRITICAL_SECTION)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        197,
        (unsigned int)&WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (_DWORD)v24,
        v30);
    goto LABEL_57;
  }
  v31 = CommonUtil::NewSprintfW((CommonUtil *)&v71, (wchar_t **)L"%s\\%s", v7, L"LLMContent");
  v22 = v31;
  if ( v31 < 0 )
  {
    v23 = (LPCRITICAL_SECTION)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        198,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v31);
    if ( v71 )
      operator delete(v71, (const struct std::nothrow_t *)v23);
    goto LABEL_57;
  }
  v33 = v71;
  v34 = CommonUtil::UtilCreateDirectoryIfNeeded(v71, v32);
  v35 = v34;
  if ( v34 < 0 )
  {
    v36 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        199,
        (unsigned int)&WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (_DWORD)v33,
        v34);
LABEL_101:
    if ( v33 )
      operator delete(v33, v36);
    if ( v24 )
      operator delete(v24, v36);
    if ( v20 )
      operator delete(v20, v36);
    if ( v14 )
      operator delete(v14, v36);
    if ( v7 )
      operator delete(v7, v36);
    if ( v65 )
      MpFreeMemory(v65);
    if ( v66 )
      MpConfigClose();
    return v35;
  }
  v37 = CommonUtil::NewSprintfW((CommonUtil *)&v70, (wchar_t **)L"%s\\%s", v7, L"PublishingLicenses");
  v35 = v37;
  if ( v37 < 0 )
  {
    v36 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        200,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v37);
    if ( v70 )
      operator delete(v70, v36);
    goto LABEL_101;
  }
  v39 = v70;
  v40 = CommonUtil::UtilCreateDirectoryIfNeeded(v70, v38);
  v41 = v40;
  if ( v40 < 0 )
  {
    v42 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        201,
        (unsigned int)&WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (_DWORD)v39,
        v40);
LABEL_126:
    if ( v39 )
      operator delete(v39, v42);
    if ( v33 )
      operator delete(v33, v42);
    if ( v24 )
      operator delete(v24, v42);
    if ( v20 )
      operator delete(v20, v42);
    if ( v14 )
      operator delete(v14, v42);
    if ( v7 )
      operator delete(v7, v42);
    if ( v65 )
      MpFreeMemory(v65);
    if ( v66 )
      MpConfigClose();
    return v41;
  }
  v43 = CommonUtil::NewSprintfW((CommonUtil *)&v69, (wchar_t **)L"%s\\%s", v7, L"RMSLabels");
  v41 = v43;
  if ( v43 < 0 )
  {
    v42 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        202,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v43);
    if ( v69 )
      operator delete(v69, v42);
    goto LABEL_126;
  }
  v45 = v69;
  v46 = CommonUtil::UtilCreateDirectoryIfNeeded(v69, v44);
  LODWORD(v67) = v46;
  if ( v46 < 0 )
  {
    v47 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        203,
        (unsigned int)&WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (_DWORD)v45,
        v46);
    goto LABEL_153;
  }
  v48 = CommonUtil::NewSprintfW((CommonUtil *)&v68, (wchar_t **)L"%s\\%s", v7, L"UserAgentApps");
  LODWORD(v67) = v48;
  if ( v48 < 0 )
  {
    v47 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        204,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v48);
    v50 = v68;
    if ( !v68 )
      goto LABEL_153;
    goto LABEL_177;
  }
  v51 = CommonUtil::UtilCreateDirectoryIfNeeded(v68, v49);
  LODWORD(v67) = v51;
  if ( v51 < 0 )
  {
    v47 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        205,
        (unsigned int)&WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (_DWORD)v68,
        v51);
    if ( !v68 )
      goto LABEL_153;
    v50 = v68;
LABEL_177:
    operator delete(v50, v47);
LABEL_153:
    if ( v45 )
      operator delete(v45, v47);
    if ( v39 )
      operator delete(v39, v47);
    if ( v33 )
      operator delete(v33, v47);
    if ( v24 )
      operator delete(v24, v47);
    if ( v20 )
      operator delete(v20, v47);
    if ( v14 )
      operator delete(v14, v47);
    if ( v7 )
      operator delete(v7, v47);
    if ( v65 )
      MpFreeMemory(v65);
    if ( v66 )
      MpConfigClose();
    return (unsigned int)v67;
  }
  v55[0] = 0;
  v75[0] = 0;
  LOWORD(v75[0]) = 0;
  v75[1] = _mm_load_si128((const __m128i *)&_xmm);
  if ( (unsigned __int8)RealtimeProtection::DlpUserAgentUtils::CreateUserAgentProcessNamesFileIfNeeded(v55, v75) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 207, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids, v55[0]);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v75);
    if ( v68 )
      operator delete(v68, v54);
    if ( v45 )
      operator delete(v45, v54);
    if ( v39 )
      operator delete(v39, v54);
    if ( v33 )
      operator delete(v33, v54);
    if ( v24 )
      operator delete(v24, v54);
    if ( v20 )
      operator delete(v20, v54);
    if ( v14 )
      operator delete(v14, v54);
    if ( v7 )
      operator delete(v7, v54);
    if ( v65 )
      MpFreeMemory(v65);
    if ( v66 )
      MpConfigClose();
    return 0;
  }
  else
  {
    LastError = GetLastError();
    LODWORD(v69) = LastError;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v69) = LastError;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        206,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)LastError);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v75);
    if ( v68 )
      operator delete(v68, v53);
    if ( v45 )
      operator delete(v45, v53);
    if ( v39 )
      operator delete(v39, v53);
    if ( v33 )
      operator delete(v33, v53);
    if ( v24 )
      operator delete(v24, v53);
    if ( v20 )
      operator delete(v20, v53);
    if ( v14 )
      operator delete(v14, v53);
    if ( v7 )
      operator delete(v7, v53);
    if ( v65 )
      MpFreeMemory(v65);
    if ( v66 )
      MpConfigClose();
    return (unsigned int)v69;
  }
}

```

## disassembly

```asm
0x1801a9a74  mov     rax, rsp
0x1801a9a77  mov     [rax+8], rbx
0x1801a9a7b  mov     [rax+10h], rsi
0x1801a9a7f  mov     [rax+18h], rdi
0x1801a9a83  push    rbp
0x1801a9a84  push    r12
0x1801a9a86  push    r13
0x1801a9a88  push    r14
0x1801a9a8a  push    r15
0x1801a9a8c  lea     rbp, [rax-78h]
0x1801a9a90  sub     rsp, 180h
0x1801a9a97  mov     rax, cs:__security_cookie
0x1801a9a9e  xor     rax, rsp
0x1801a9aa1  mov     [rbp+70h+var_30], rax
0x1801a9aa5  xor     r13d, r13d
0x1801a9aa8  lea     rdi, asc_18025D638; "."
0x1801a9aaf  mov     rcx, rdi
0x1801a9ab2  mov     [rbp+70h+var_98], r13
0x1801a9ab6  lea     rdx, [rbp+70h+var_98]
0x1801a9aba  mov     [rbp+70h+var_A0], r13
0x1801a9abe  mov     [rbp+70h+var_90], r13
0x1801a9ac2  mov     [rbp+70h+var_58], r13
0x1801a9ac6  mov     [rbp+70h+var_60], r13
0x1801a9aca  mov     [rbp+70h+var_68], r13
0x1801a9ace  mov     [rbp+70h+var_70], r13
0x1801a9ad2  mov     [rbp+70h+var_78], r13
0x1801a9ad6  mov     [rbp+70h+var_80], r13
0x1801a9ada  mov     [rbp+70h+var_88], r13
0x1801a9ade  call    cs:__imp_MpConfigOpen
0x1801a9ae4  mov     ebx, eax
0x1801a9ae6  test    eax, eax
0x1801a9ae8  jns     short loc_1801A9B2C
0x1801a9aea  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a9af1  lea     rdx, WPP_GLOBAL_Control
0x1801a9af8  cmp     rcx, rdx
0x1801a9afb  jz      loc_1801AA732
0x1801a9b01  test    byte ptr [rcx+1Ch], 1
0x1801a9b05  jz      loc_1801AA732
0x1801a9b0b  mov     rcx, [rcx+10h]
0x1801a9b0f  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x1801a9b16  mov     edx, 0BCh
0x1801a9b1b  mov     dword ptr [rsp+1A0h+var_180], eax
0x1801a9b1f  mov     r9, rdi
0x1801a9b22  call    WPP_SF_Sd
0x1801a9b27  jmp     loc_1801AA732
0x1801a9b2c  mov     rcx, [rbp+70h+var_A0]
0x1801a9b30  test    rcx, rcx
0x1801a9b33  jz      short loc_1801A9B3B
0x1801a9b35  call    cs:__imp_MpFreeMemory
0x1801a9b3b  mov     rcx, [rbp+70h+var_98]
0x1801a9b3f  lea     rsi, aProductappdata; "ProductAppDataPath"
0x1801a9b46  mov     rdx, rsi
0x1801a9b49  lea     r8, [rbp+70h+var_A0]
0x1801a9b4d  call    MpConfigGetValueString
0x1801a9b52  mov     ebx, eax
0x1801a9b54  test    eax, eax
0x1801a9b56  js      loc_1801AA6F8
0x1801a9b5c  mov     r8, [rbp+70h+var_A0]; wchar_t *
0x1801a9b60  lea     r12, aSS; "%s\\%s"
0x1801a9b67  mov     rdx, r12; wchar_t **
0x1801a9b6a  lea     r9, aDlpcache; "DLPCache"
0x1801a9b71  lea     rcx, [rbp+70h+var_90]; this
0x1801a9b75  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x1801a9b7a  mov     ebx, eax
0x1801a9b7c  test    eax, eax
0x1801a9b7e  jns     short loc_1801A9BC8
0x1801a9b80  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a9b87  lea     rdx, WPP_GLOBAL_Control
0x1801a9b8e  cmp     rcx, rdx
0x1801a9b91  jz      short loc_1801A9BB1
0x1801a9b93  test    byte ptr [rcx+1Ch], 1
0x1801a9b97  jz      short loc_1801A9BB1
0x1801a9b99  mov     rcx, [rcx+10h]
0x1801a9b9d  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x1801a9ba4  mov     edx, 0BEh
0x1801a9ba9  mov     r9d, eax
0x1801a9bac  call    WPP_SF_d
0x1801a9bb1  mov     rcx, [rbp+70h+var_90]; void *
0x1801a9bb5  test    rcx, rcx
0x1801a9bb8  jz      loc_1801AA732
0x1801a9bbe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801a9bc3  jmp     loc_1801AA732
0x1801a9bc8  mov     rbx, [rbp+70h+var_90]
0x1801a9bcc  mov     rcx, rbx; this
0x1801a9bcf  call    ?UtilCreateDirectoryIfNeeded@CommonUtil@@YAJPEB_W@Z; CommonUtil::UtilCreateDirectoryIfNeeded(wchar_t const *)
0x1801a9bd4  mov     edi, eax
0x1801a9bd6  test    eax, eax
0x1801a9bd8  jns     short loc_1801A9C41
0x1801a9bda  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a9be1  lea     rdx, WPP_GLOBAL_Control
0x1801a9be8  cmp     rcx, rdx
0x1801a9beb  jz      short loc_1801A9C0F
0x1801a9bed  test    byte ptr [rcx+1Ch], 1
0x1801a9bf1  jz      short loc_1801A9C0F
0x1801a9bf3  mov     rcx, [rcx+10h]
0x1801a9bf7  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x1801a9bfe  mov     edx, 0BFh
0x1801a9c03  mov     dword ptr [rsp+1A0h+var_180], eax
0x1801a9c07  mov     r9, rbx
0x1801a9c0a  call    WPP_SF_Sd
0x1801a9c0f  test    rbx, rbx
0x1801a9c12  jz      short loc_1801A9C1C
0x1801a9c14  mov     rcx, rbx; void *
0x1801a9c17  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801a9c1c  mov     rcx, [rbp+70h+var_A0]
0x1801a9c20  test    rcx, rcx
0x1801a9c23  jz      short loc_1801A9C2B
0x1801a9c25  call    cs:__imp_MpFreeMemory
0x1801a9c2b  mov     rcx, [rbp+70h+var_98]
0x1801a9c2f  test    rcx, rcx
0x1801a9c32  jz      short loc_1801A9C3A
0x1801a9c34  call    cs:__imp_MpConfigClose
0x1801a9c3a  mov     eax, edi
0x1801a9c3c  jmp     loc_1801AA752
0x1801a9c41  lea     r9, aNetworkfilesma; "NetworkFilesMappingStubs"
0x1801a9c48  mov     r8, rbx; wchar_t *
0x1801a9c4b  mov     rdx, r12; wchar_t **
0x1801a9c4e  lea     rcx, [rbp+70h+var_58]; this
0x1801a9c52  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x1801a9c57  mov     edi, eax
0x1801a9c59  test    eax, eax
0x1801a9c5b  jns     short loc_1801A9CA5
0x1801a9c5d  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a9c64  lea     rdx, WPP_GLOBAL_Control
0x1801a9c6b  cmp     rcx, rdx
0x1801a9c6e  jz      short loc_1801A9C8E
0x1801a9c70  test    byte ptr [rcx+1Ch], 1
0x1801a9c74  jz      short loc_1801A9C8E
0x1801a9c76  mov     rcx, [rcx+10h]
0x1801a9c7a  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x1801a9c81  mov     edx, 0C0h
0x1801a9c86  mov     r9d, eax
0x1801a9c89  call    WPP_SF_d
0x1801a9c8e  mov     rcx, [rbp+70h+var_58]; void *
0x1801a9c92  test    rcx, rcx
0x1801a9c95  jz      loc_1801A9C0F
0x1801a9c9b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801a9ca0  jmp     loc_1801A9C0F
0x1801a9ca5  mov     rdi, [rbp+70h+var_58]
0x1801a9ca9  mov     rcx, rdi; this
0x1801a9cac  call    ?UtilCreateDirectoryIfNeeded@CommonUtil@@YAJPEB_W@Z; CommonUtil::UtilCreateDirectoryIfNeeded(wchar_t const *)
0x1801a9cb1  mov     esi, eax
0x1801a9cb3  test    eax, eax
0x1801a9cb5  jns     short loc_1801A9D2B
0x1801a9cb7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a9cbe  lea     rdx, WPP_GLOBAL_Control
0x1801a9cc5  cmp     rcx, rdx
0x1801a9cc8  jz      short loc_1801A9CEC
0x1801a9cca  test    byte ptr [rcx+1Ch], 1
0x1801a9cce  jz      short loc_1801A9CEC
0x1801a9cd0  mov     rcx, [rcx+10h]
0x1801a9cd4  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x1801a9cdb  mov     edx, 0C1h
0x1801a9ce0  mov     dword ptr [rsp+1A0h+var_180], eax
0x1801a9ce4  mov     r9, rdi
0x1801a9ce7  call    WPP_SF_Sd
0x1801a9cec  test    rdi, rdi
0x1801a9cef  jz      short loc_1801A9CF9
0x1801a9cf1  mov     rcx, rdi; void *
0x1801a9cf4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801a9cf9  test    rbx, rbx
0x1801a9cfc  jz      short loc_1801A9D06
0x1801a9cfe  mov     rcx, rbx; void *
0x1801a9d01  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801a9d06  mov     rcx, [rbp+70h+var_A0]
0x1801a9d0a  test    rcx, rcx
0x1801a9d0d  jz      short loc_1801A9D15
0x1801a9d0f  call    cs:__imp_MpFreeMemory
0x1801a9d15  mov     rcx, [rbp+70h+var_98]
0x1801a9d19  test    rcx, rcx
0x1801a9d1c  jz      short loc_1801A9D24
0x1801a9d1e  call    cs:__imp_MpConfigClose
0x1801a9d24  mov     eax, esi
0x1801a9d26  jmp     loc_1801AA752
0x1801a9d2b  lea     r9, aFileevidence; "FileEvidence"
0x1801a9d32  mov     r8, rbx; wchar_t *
0x1801a9d35  mov     rdx, r12; wchar_t **
0x1801a9d38  lea     rcx, [rbp+70h+var_60]; this
0x1801a9d3c  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x1801a9d41  mov     esi, eax
0x1801a9d43  test    eax, eax
0x1801a9d45  jns     short loc_1801A9D8F
0x1801a9d47  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a9d4e  lea     rdx, WPP_GLOBAL_Control
0x1801a9d55  cmp     rcx, rdx
0x1801a9d58  jz      short loc_1801A9D78
0x1801a9d5a  test    byte ptr [rcx+1Ch], 1
0x1801a9d5e  jz      short loc_1801A9D78
0x1801a9d60  mov     rcx, [rcx+10h]
0x1801a9d64  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x1801a9d6b  mov     edx, 0C2h
0x1801a9d70  mov     r9d, eax
0x1801a9d73  call    WPP_SF_d
0x1801a9d78  mov     rcx, [rbp+70h+var_60]; void *
0x1801a9d7c  test    rcx, rcx
0x1801a9d7f  jz      loc_1801A9CEC
0x1801a9d85  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1801a9d8a  jmp     loc_1801A9CEC
0x1801a9d8f  mov     rsi, [rbp+70h+var_60]
0x1801a9d93  mov     rcx, rsi; this
0x1801a9d96  call    ?UtilCreateDirectoryIfNeeded@CommonUtil@@YAJPEB_W@Z; CommonUtil::UtilCreateDirectoryIfNeeded(wchar_t const *)
0x1801a9d9b  mov     r15d, eax
0x1801a9d9e  test    eax, eax
0x1801a9da0  jns     loc_1801A9FDE
0x1801a9da6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801a9dad  lea     rdx, WPP_GLOBAL_Control
0x1801a9db4  cmp     rcx, rdx
0x1801a9db7  jz      short loc_1801A9DDB
0x1801a9db9  test    byte ptr [rcx+1Ch], 1
0x1801a9dbd  jz      short loc_1801A9DDB
0x1801a9dbf  mov     rcx, [rcx+10h]
0x1801a9dc3  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x1801a9dca  mov     edx, 0C3h
0x1801a9dcf  mov     dword ptr [rsp+1A0h+var_180], eax
0x1801a9dd3  mov     r9, rsi
0x1801a9dd6  call    WPP_SF_Sd
0x1801a9ddb  mov     r9d, r15d
0x1801a9dde  mov     [rbp+70h+var_90], r13
0x1801a9de2  lea     r8, aEvidenceDirect; "Evidence directory creation failed erro"...
0x1801a9de9  lea     rdx, aLsLx; "%ls%#lx"
0x1801a9df0  lea     rcx, [rbp+70h+var_90]; this
0x1801a9df4  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x1801a9df9  mov     rdx, cs:?g_pcsAsimovLock@@3PEAVCMpCriticalSection@CommonUtil@@EA; CommonUtil::CMpCriticalSection * g_pcsAsimovLock
0x1801a9e00  mov     r14, [rbp+70h+var_90]
0x1801a9e04  test    rdx, rdx
0x1801a9e07  jz      loc_1801A9F84
0x1801a9e0d  lea     rcx, [rbp+70h+var_50]
0x1801a9e11  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1801a9e16  mov     r9, cs:g_hMpAsimovProvider
0x1801a9e1d  cmp     dword ptr [r9], 5
0x1801a9e21  jbe     loc_1801A9F7B
0x1801a9e27  mov     rdx, 400000000000h
0x1801a9e31  mov     rcx, r9
0x1801a9e34  call    _tlgKeywordOn
0x1801a9e39  test    al, al
0x1801a9e3b  jz      loc_1801A9F7B
0x1801a9e41  mov     rcx, cs:?g_aAsimov@@3PEAVCMpAsimov@@EA; CMpAsimov * g_aAsimov
0x1801a9e48  lea     rax, aDirectoryCreat; "Directory Creation"
0x1801a9e4f  mov     [rbp+70h+var_E0], rax
0x1801a9e53  lea     rdx, dword_1802C4424; int
0x1801a9e5a  mov     [rbp+70h+var_E8], r14
0x1801a9e5e  mov     [rbp+70h+var_A8], 2000000h
0x1801a9e66  mov     eax, [rcx+48h]
0x1801a9e69  mov     dword ptr [rbp+70h+var_80], eax
0x1801a9e6c  mov     eax, [rcx+44h]
0x1801a9e6f  mov     dword ptr [rbp+70h+var_78], eax
0x1801a9e72  mov     eax, [rcx+40h]
0x1801a9e75  mov     dword ptr [rbp+70h+var_70], eax
0x1801a9e78  movzx   eax, byte ptr [rcx+3Ch]
0x1801a9e7c  mov     dword ptr [rbp+70h+var_68], eax
0x1801a9e7f  movzx   eax, byte ptr [rcx+3Bh]
0x1801a9e83  mov     dword ptr [rbp+70h+var_60], eax
0x1801a9e86  movzx   eax, byte ptr [rcx+3Ah]
0x1801a9e8a  mov     dword ptr [rbp+70h+var_58], eax
0x1801a9e8d  movzx   eax, byte ptr [rcx+39h]
0x1801a9e91  mov     dword ptr [rbp+70h+var_88], eax
0x1801a9e94  movzx   eax, byte ptr [rcx+38h]
0x1801a9e98  mov     dword ptr [rbp+70h+var_90], eax
0x1801a9e9b  mov     rax, [rcx+30h]
0x1801a9e9f  mov     [rbp+70h+var_D8], rax
0x1801a9ea3  mov     rax, [rcx+28h]
0x1801a9ea7  mov     [rbp+70h+var_D0], rax
0x1801a9eab  mov     rax, [rcx+20h]
0x1801a9eaf  mov     [rbp+70h+var_C8], rax
0x1801a9eb3  mov     rax, [rcx+18h]
0x1801a9eb7  mov     [rbp+70h+var_C0], rax
0x1801a9ebb  mov     rax, [rcx+10h]
0x1801a9ebf  mov     [rbp+70h+var_B8], rax
0x1801a9ec3  mov     rax, [rcx+8]
0x1801a9ec7  mov     rcx, r9; int
0x1801a9eca  mov     [rbp+70h+var_B0], rax
0x1801a9ece  lea     rax, [rbp+70h+var_E8]
0x1801a9ed2  mov     [rsp+1A0h+var_100], rax; __int64
0x1801a9eda  lea     rax, [rbp+70h+var_E0]
0x1801a9ede  mov     [rsp+1A0h+var_108], rax; __int64
0x1801a9ee6  lea     rax, [rbp+70h+var_80]
0x1801a9eea  mov     [rsp+1A0h+var_110], rax; __int64
0x1801a9ef2  lea     rax, [rbp+70h+var_78]
0x1801a9ef6  mov     [rsp+1A0h+var_118], rax; __int64
0x1801a9efe  lea     rax, [rbp+70h+var_70]
0x1801a9f02  mov     [rsp+1A0h+var_120], rax; __int64
0x1801a9f0a  lea     rax, [rbp+70h+var_68]
0x1801a9f0e  mov     [rsp+1A0h+var_128], rax; __int64
0x1801a9f13  lea     rax, [rbp+70h+var_60]
0x1801a9f17  mov     [rsp+1A0h+var_130], rax; __int64
0x1801a9f1c  lea     rax, [rbp+70h+var_58]
0x1801a9f20  mov     [rsp+1A0h+var_138], rax; __int64
0x1801a9f25  lea     rax, [rbp+70h+var_88]
0x1801a9f29  mov     [rsp+1A0h+var_140], rax; __int64
0x1801a9f2e  lea     rax, [rbp+70h+var_90]
0x1801a9f32  mov     [rsp+1A0h+var_148], rax; __int64
0x1801a9f37  lea     rax, [rbp+70h+var_D8]
0x1801a9f3b  mov     [rsp+1A0h+var_150], rax; __int64
0x1801a9f40  lea     rax, [rbp+70h+var_D0]
0x1801a9f44  mov     [rsp+1A0h+var_158], rax; __int64
0x1801a9f49  lea     rax, [rbp+70h+var_C8]
0x1801a9f4d  mov     [rsp+1A0h+var_160], rax; __int64
0x1801a9f52  lea     rax, [rbp+70h+var_C0]
0x1801a9f56  mov     [rsp+1A0h+var_168], rax; __int64
0x1801a9f5b  lea     rax, [rbp+70h+var_B8]
  ... truncated ...
```
