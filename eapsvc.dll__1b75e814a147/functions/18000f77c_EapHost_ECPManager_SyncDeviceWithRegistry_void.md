# EapHost::ECPManager::SyncDeviceWithRegistry(void)

- ea: `0x18000f77c`
- end: `0x18001050f`
- name: `?SyncDeviceWithRegistry@ECPManager@EapHost@@AEAAXXZ`
- size: `3475`
- prototype: `void __fastcall(EapHost::ECPManager *__hidden this)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f184`

## callees

- `0x180001f60`
- `0x18000a5ac`
- `0x18000aafc`
- `0x18000ab70`
- `0x18000bbd8`
- `0x18000c150`
- `0x18000c1a8`
- `0x18000c39c`
- `0x18000c40c`
- `0x18000cc1c`
- `0x18000ce54`
- `0x18000d0f8`
- `0x18000d610`
- `0x18000eb88`
- `0x18000ecfc`
- `0x18000eda8`
- `0x18000efdc`
- `0x18000f77c`
- `0x180010f64`
- `0x180010fac`
- `0x180011cb0`
- `0x1800122b8`
- `0x180012968`
- `0x180012b30`
- `0x180012cf8`
- `0x1800133a8`
- `0x180014e74`
- `0x180017010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18000f7f0`
- `ntdll!EtwEventEnabled` at `0x18000f89a`
- `ntdll!EtwEventEnabled` at `0x18000f953`
- `ntdll!EtwEventEnabled` at `0x18000f9fc`
- `ntdll!EtwEventEnabled` at `0x18000fada`
- `ntdll!EtwEventEnabled` at `0x18000fc2a`
- `ntdll!EtwEventEnabled` at `0x18000fcfe`
- `ntdll!EtwEventEnabled` at `0x18000fdee`
- `ntdll!EtwEventEnabled` at `0x18000ff8a`
- `ntdll!EtwEventEnabled` at `0x180010071`
- `ntdll!EtwEventEnabled` at `0x18001023b`
- `ntdll!EtwEventEnabled` at `0x1800103a0`
- `ntdll!EtwEventEnabled` at `0x1800103fc`
- `ntdll!EtwEventEnabled` at `0x18001048c`
- `ntdll!EtwEventEnabled` at `0x18000f7f0`
- `ntdll!EtwEventEnabled` at `0x18000f89a`
- `ntdll!EtwEventEnabled` at `0x18000f953`
- `ntdll!EtwEventEnabled` at `0x18000f9fc`
- `ntdll!EtwEventEnabled` at `0x18000fada`
- `ntdll!EtwEventEnabled` at `0x18000fc2a`
- `ntdll!EtwEventEnabled` at `0x18000fcfe`
- `ntdll!EtwEventEnabled` at `0x18000fdee`
- `ntdll!EtwEventEnabled` at `0x18000ff8a`
- `ntdll!EtwEventEnabled` at `0x180010071`
- `ntdll!EtwEventEnabled` at `0x18001023b`
- `ntdll!EtwEventEnabled` at `0x1800103a0`
- `ntdll!EtwEventEnabled` at `0x1800103fc`
- `ntdll!EtwEventEnabled` at `0x18001048c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010331`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010331`

## string_xrefs

- `0x18000f875`: `SYSTEM\CurrentControlSet\Services\EapHost\ECP`
- `0x18000f804`: `Start to sync devices with ECP registry`
- `0x18000f95d`: `ECP bus enumerator exists. Should be deleted`
- `0x18000fc43`: `Found %Iu valid component keys:`
- `0x18000fdf8`: `Finding all the component devices`
- `0x180010496`: `Service shutdown detected while iterating through component devices`
- `0x18000ffa4`: `Device %S not in registry.  Delete it`
- `0x18001007b`: `Delete bad devices, if any`
- `0x1800103aa`: `Service shutdown detected while iterating through ECP keys`
- `0x180010251`: `Key %S does not have device. Create one.`
- `0x180010409`: `Unexpected result while opening ECP key. %u`

## pseudocode

```c
void __fastcall EapHost::ECPManager::SyncDeviceWithRegistry(EapHost::ECPManager *this)
{
  __int64 v2; // rdx
  __int64 v3; // r13
  int v4; // r8d
  int v5; // r9d
  __int64 v6; // rax
  unsigned int v7; // ebx
  int v8; // r8d
  int v9; // r9d
  __int64 v10; // rax
  int v11; // r8d
  int v12; // r9d
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // rax
  wchar_t *v16; // rbx
  wchar_t *v17; // rdi
  const wchar_t *v18; // r9
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rax
  wchar_t *v22; // r9
  wchar_t *v23; // r14
  wchar_t *i; // r15
  char v25; // al
  __int64 v26; // r8
  wchar_t *v27; // rsi
  int v28; // r9d
  __int64 v29; // rax
  wchar_t *v30; // r12
  unsigned int v31; // ebx
  __int64 v32; // r12
  wchar_t *v33; // r9
  int v34; // r8d
  int v35; // r9d
  __int64 v36; // rax
  wchar_t *v37; // r9
  EapHost::ECPManager *v38; // r14
  int v39; // r8d
  int v40; // r9d
  __int64 v41; // rax
  _QWORD *v42; // rax
  __int64 v43; // rcx
  _QWORD *v44; // rbx
  const wchar_t *v45; // r14
  wchar_t *j; // r15
  const wchar_t *v47; // rdx
  size_t v48; // r8
  const wchar_t *v49; // rcx
  const wchar_t *v50; // r9
  __int64 v51; // rcx
  int v52; // r8d
  int v53; // r9d
  __int64 v54; // rax
  __int64 **v55; // rcx
  __int64 k; // rax
  __int64 *m; // rcx
  int v58; // r8d
  int v59; // r9d
  __int64 v60; // rax
  unsigned __int64 v61; // rcx
  unsigned int v62; // ebx
  __int64 v63; // rdx
  unsigned int v64; // edx
  wchar_t *v65; // rbx
  char *v66; // r13
  const wchar_t *v67; // rdx
  unsigned __int64 v68; // r12
  unsigned __int64 v69; // r15
  _QWORD *v70; // r14
  const wchar_t *v71; // rcx
  size_t v72; // r8
  int v73; // eax
  const wchar_t *v74; // r9
  int v75; // r8d
  int v76; // r9d
  __int64 v77; // rax
  void *v78; // rcx
  wchar_t *v79; // r9
  _BYTE pExceptionObject[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v81; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v82; // [rsp+40h] [rbp-C0h]
  EapHost::ECPManager *v83; // [rsp+48h] [rbp-B8h]
  _QWORD v84[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v85; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v86; // [rsp+70h] [rbp-90h]
  wchar_t *S1[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v88; // [rsp+88h] [rbp-78h]
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  int v90; // [rsp+98h] [rbp-68h]
  _BYTE v91[16]; // [rsp+A0h] [rbp-60h] BYREF
  char *v92; // [rsp+B0h] [rbp-50h]
  int v93; // [rsp+B8h] [rbp-48h]
  int v94; // [rsp+BCh] [rbp-44h]
  char v95[2048]; // [rsp+C0h] [rbp-40h] BYREF

  v83 = this;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
  v3 = -1;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v95, 0x800u, "Start to sync devices with ECP registry") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v6 = -1;
    do
      ++v6;
    while ( v95[v6] );
    v92 = v95;
    v93 = v6 + 1;
    v94 = 0;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v4,
      v5,
      (__int64)v91);
  }
  v81 = 0;
  hKey = 0;
  v90 = 1;
  v7 = RegistryKey::Open(&hKey, v2, L"SYSTEM\\CurrentControlSet\\Services\\EapHost\\ECP", 9);
  if ( v7 != 1 )
  {
    if ( v7 )
    {
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent)
        && (int)StringCchPrintfA(v95, 0x800u, "Unexpected result while opening ECP key. %u", v7) >= 0
        && (byte_180020AC1 & 8) != 0 )
      {
        McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugErrorEvent, v95);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids, v7);
      SystemError::Throw<long>(&byte_180018CBC, 4317);
    }
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v95, 0x800u, "ECP key exists. Enumerating all subkeys") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v15 = -1;
      do
        ++v15;
      while ( v95[v15] );
      v92 = v95;
      v93 = v15 + 1;
      v94 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v13,
        v14,
        (__int64)v91);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
    *(_OWORD *)S1 = 0;
    v88 = 0;
    RegistryKey::SubKeys(&hKey, S1);
    v16 = S1[0];
    v17 = S1[1];
    while ( v16 != v17 )
    {
      if ( (unsigned __int8)EapHost::ECPManager::IsValidDeviceString(v16) )
      {
        v16 += 16;
      }
      else
      {
        if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugErrorEvent) )
        {
          v18 = v16;
          if ( *((_QWORD *)v16 + 3) > 7u )
            v18 = *(const wchar_t **)v16;
          if ( (int)StringCchPrintfA(v95, 0x800u, "Key %S is not valid", v18) >= 0 && (byte_180020AC1 & 8) != 0 )
          {
            v21 = -1;
            do
              ++v21;
            while ( v95[v21] );
            v92 = v95;
            v93 = v21 + 1;
            v94 = 0;
            McGenEventWrite_EtwEventWriteTransfer(
              (unsigned int)&eaphost_Context,
              (unsigned int)DebugErrorEvent,
              v19,
              v20,
              (__int64)v91);
          }
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          if ( *((_QWORD *)v16 + 3) <= 7u )
            v22 = v16;
          else
            v22 = *(wchar_t **)v16;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids, v22);
        }
        v23 = v16;
        for ( i = v16 + 16; i != v17; i += 16 )
        {
          if ( v23 != i )
          {
            if ( *((_QWORD *)v23 + 3) > 7u )
              operator delete(*(LPCVOID *)v23);
            *((_QWORD *)v23 + 2) = 0;
            *((_QWORD *)v23 + 3) = 7;
            *v23 = 0;
            *(_OWORD *)v23 = *(_OWORD *)i;
            *((_OWORD *)v23 + 1) = *((_OWORD *)i + 1);
            *((_QWORD *)i + 2) = 0;
            *((_QWORD *)i + 3) = 7;
            *i = 0;
          }
          v23 += 16;
        }
        v17 -= 16;
        if ( *((_QWORD *)v17 + 3) > 7u )
          operator delete(*(LPCVOID *)v17);
        *((_QWORD *)v17 + 2) = 0;
        *((_QWORD *)v17 + 3) = 7;
        *v17 = 0;
        S1[1] = v17;
      }
    }
    v25 = EtwEventEnabled(eaphost_Context, DebugInfoEvent);
    v27 = S1[0];
    if ( v25
      && (int)StringCchPrintfA(v95, 0x800u, "Found %Iu valid component keys:", ((char *)v17 - (char *)S1[0]) >> 5) >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v29 = -1;
      do
        ++v29;
      while ( v95[v29] );
      v92 = v95;
      v93 = v29 + 1;
      v94 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v26,
        v28,
        (__int64)v91);
    }
    v30 = v17;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v30 = v17;
    }
    else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_P(*((_QWORD *)WPP_GLOBAL_Control + 2), WPP_GLOBAL_Control, v26, ((char *)v17 - (char *)v27) >> 5);
    }
    else
    {
      v30 = v17;
    }
    v31 = 0;
    v32 = ((char *)v30 - (char *)v27) >> 5;
    if ( v32 )
    {
      do
      {
        if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
        {
          v33 = &v27[16 * v31];
          if ( *((_QWORD *)v33 + 3) > 7u )
            v33 = *(wchar_t **)v33;
          if ( (int)StringCchPrintfA(v95, 0x800u, "%S", v33) >= 0 && Microsoft_Windows_EapHostEnableBits < 0 )
          {
            v36 = -1;
            do
              ++v36;
            while ( v95[v36] );
            v92 = v95;
            v93 = v36 + 1;
            v94 = 0;
            McGenEventWrite_EtwEventWriteTransfer(
              (unsigned int)&eaphost_Context,
              (unsigned int)DebugInfoEvent,
              v34,
              v35,
              (__int64)v91);
          }
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v37 = &v27[16 * v31];
          if ( *((_QWORD *)v37 + 3) > 7u )
            v37 = *(wchar_t **)v37;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids, v37);
        }
        ++v31;
      }
      while ( v31 < (unsigned __int64)(((char *)v17 - (char *)v27) >> 5) );
    }
    v38 = v83;
    EapHost::ECPDeviceManager::CreateECPBusEnumerator((char *)v83 + 72, &v81);
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v95, 0x800u, "Finding all the component devices") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v41 = -1;
      do
        ++v41;
      while ( v95[v41] );
      v92 = v95;
      v93 = v41 + 1;
      v94 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v39,
        v40,
        (__int64)v91);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
    v84[0] = 0;
    v84[1] = 0;
    v42 = operator new(0x48u);
    *v42 = v42;
    v42[1] = v42;
    v42[2] = v42;
    *((_WORD *)v42 + 12) = 257;
    v84[0] = v42;
    v85 = 0;
    v86 = 0;
    EapHost::ECPDeviceManager::GetAllECPComponentDevices(v43, &v81, v84, &v85);
    v44 = *(_QWORD **)v84[0];
    while ( v44 != (_QWORD *)v84[0] )
    {
      if ( *(_BYTE *)v38 )
      {
        if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
          && (int)StringCchPrintfA(v95, 0x800u, "Service shutdown detected while iterating through component devices") >= 0
          && Microsoft_Windows_EapHostEnableBits < 0 )
        {
          McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v95);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
        throw (EapHost::ECPShutdownException *)pExceptionObject;
      }
      v45 = (const wchar_t *)(v44 + 4);
      for ( j = v27; j != v17; j += 16 )
      {
        v47 = (const wchar_t *)(v44 + 4);
        if ( v44[7] > 7u )
          v47 = *(const wchar_t **)v45;
        v48 = *((_QWORD *)j + 2);
        if ( *((_QWORD *)j + 3) <= 7u )
          v49 = j;
        else
          v49 = *(const wchar_t **)j;
        if ( v48 == v44[6] && (!v48 || !wmemcmp(v49, v47, v48)) )
          break;
      }
      if ( j == v17 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          if ( v44[7] <= 7u )
            v50 = (const wchar_t *)(v44 + 4);
          else
            v50 = *(const wchar_t **)v45;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids, v50);
        }
        if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
        {
          if ( v44[7] > 7u )
            v45 = *(const wchar_t **)v45;
          if ( (int)StringCchPrintfA(v95, 0x800u, "Device %S not in registry.  Delete it", v45) >= 0
            && Microsoft_Windows_EapHostEnableBits < 0 )
          {
            v54 = -1;
            do
              ++v54;
            while ( v95[v54] );
            v92 = v95;
            v93 = v54 + 1;
            v94 = 0;
            McGenEventWrite_EtwEventWriteTransfer(
              (unsigned int)&eaphost_Context,
              (unsigned int)DebugInfoEvent,
              v52,
              v53,
              (__int64)v91);
          }
        }
        EapHost::ECPDeviceManager::DeleteECPComponentDevice(v51, &v81, v44 + 8);
      }
      v55 = (__int64 **)v44[2];
      if ( *((_BYTE *)v55 + 25) )
      {
        for ( k = v44[1]; !*(_BYTE *)(k + 25) && v44 == *(_QWORD **)(k + 16); k = *(_QWORD *)(k + 8) )
          v44 = (_QWORD *)k;
        v44 = (_QWORD *)k;
      }
      else
      {
        v44 = (_QWORD *)v44[2];
        for ( m = *v55; !*((_BYTE *)m + 25); m = (__int64 *)*m )
          v44 = m;
      }
      v38 = v83;
    }
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v95, 0x800u, "Delete bad devices, if any") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      v60 = -1;
      do
        ++v60;
      while ( v95[v60] );
      v92 = v95;
      v93 = v60 + 1;
      v94 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v58,
        v59,
        (__int64)v91);
    }
    v61 = (unsigned __int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
      v61 = (unsigned __int64)WPP_GLOBAL_Control;
    }
    v62 = 0;
    v63 = v85;
    if ( (__int64)(*((_QWORD *)&v85 + 1) - v85) >> 3 )
    {
      do
      {
        EapHost::ECPDeviceManager::DeleteECPComponentDevice(v61, &v81, v63 + 8LL * v62++);
        v63 = v85;
        v61 = (__int64)(*((_QWORD *)&v85 + 1) - v85) >> 3;
      }
      while ( v62 < v61 );
      v61 = (unsigned __int64)WPP_GLOBAL_Control;
    }
    v64 = 0;
    v82 = 0;
    if ( !v32 )
    {
LABEL_187:
      std::vector<ATL::CComPtr<IUMBusPDO>>::~vector<ATL::CComPtr<IUMBusPDO>>(&v85);
      std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>,0>>::~_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>,0>>(v84);
      std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::~vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(S1);
      goto LABEL_188;
    }
    while ( 1 )
    {
      if ( *(_BYTE *)v38 )
      {
        if ( (_UNKNOWN **)v61 != &WPP_GLOBAL_Control && (*(_BYTE *)(v61 + 28) & 4) != 0 )
          WPP_SF_(*(_QWORD *)(v61 + 16), 46, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
        if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
          && (int)StringCchPrintfA(v95, 0x800u, "Service shutdown detected while iterating through ECP keys") >= 0
          && Microsoft_Windows_EapHostEnableBits < 0 )
        {
          McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, DebugInfoEvent, v95);
        }
        throw (EapHost::ECPShutdownException *)pExceptionObject;
      }
      v65 = &v27[16 * v64];
      std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>,0>>::_Find_lower_bound<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(
        v84,
        v91,
        v65);
      v66 = v92;
      if ( v92[25] )
      {
        v70 = v65 + 12;
      }
      else
      {
        v67 = (const wchar_t *)(v92 + 32);
        v68 = *((_QWORD *)v92 + 6);
        if ( *((_QWORD *)v92 + 7) > 7u )
          v67 = *(const wchar_t **)v67;
        v69 = *((_QWORD *)v65 + 2);
        v70 = v65 + 12;
        if ( *((_QWORD *)v65 + 3) <= 7u )
          v71 = v65;
        else
          v71 = *(const wchar_t **)v65;
        v72 = *((_QWORD *)v65 + 2);
        if ( v68 < v69 )
          v72 = *((_QWORD *)v92 + 6);
        v73 = wmemcmp(v71, v67, v72);
        if ( v73 )
        {
          if ( v73 >= 0 )
            goto LABEL_168;
        }
        else if ( v69 >= v68 )
        {
LABEL_168:
          if ( v66 != (char *)v84[0] )
            goto LABEL_169;
        }
      }
      if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent) )
      {
        v74 = v65;
        if ( *v70 > 7u )
          v74 = *(const wchar_t **)v65;
        if ( (int)StringCchPrintfA(v95, 0x800u, "Key %S does not have device. Create one.", v74) >= 0
          && Microsoft_Windows_EapHostEnableBits < 0 )
        {
          v77 = -1;
          do
            ++v77;
          while ( v95[v77] );
          v92 = v95;
          v93 = v77 + 1;
          v94 = 0;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&eaphost_Context,
            (unsigned int)DebugInfoEvent,
            v75,
            v76,
            (__int64)v91);
        }
      }
      v78 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v79 = &v27[16 * v82];
        if ( *((_QWORD *)v79 + 3) > 7u )
          v79 = *(wchar_t **)v79;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids, v79);
      }
      EapHost::ECPDeviceManager::CreateECPComponentDevice(v78, &v81, v65);
LABEL_169:
      v64 = v82 + 1;
      v82 = v64;
      if ( v64 >= (unsigned __int64)(((char *)v17 - (char *)v27) >> 5) )
        goto LABEL_187;
      v61 = (unsigned __int64)WPP_GLOBAL_Control;
      v38 = v83;
    }
  }
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v95, 0x800u, "The ECP key does not exist") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v95[v10] );
    v92 = v95;
    v93 = v10 + 1;
    v94 = 0;
    McGenEventWrite_EtwEventWriteTransfer(
      (unsigned int)&eaphost_Context,
      (unsigned int)DebugInfoEvent,
      v8,
      v9,
      (__int64)v91);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
  pExceptionObject[0] = 0;
  EapHost::ECPDeviceManager::GetECPBusEnumerator((char *)this + 72, &v81, pExceptionObject);
  if ( !pExceptionObject[0] )
  {
    if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
      && (int)StringCchPrintfA(v95, 0x800u, "ECP bus enumerator exists. Should be deleted") >= 0
      && Microsoft_Windows_EapHostEnableBits < 0 )
    {
      do
        ++v3;
      while ( v95[v3] );
      v92 = v95;
      v93 = v3 + 1;
      v94 = 0;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&eaphost_Context,
        (unsigned int)DebugInfoEvent,
        v11,
        v12,
        (__int64)v91);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids);
    EapHost::ECPDeviceManager::DeleteECPBusEnumerator((char *)this + 72, &v81);
  }
LABEL_188:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v81 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v81 + 16LL))(v81);
}

```

## disassembly

```asm
0x18000f77c  push    rbp
0x18000f77e  push    rbx
0x18000f77f  push    rsi
0x18000f780  push    rdi
0x18000f781  push    r12
0x18000f783  push    r13
0x18000f785  push    r14
0x18000f787  push    r15
0x18000f789  lea     rbp, [rsp-7D8h]
0x18000f791  sub     rsp, 8D8h
0x18000f798  mov     rax, cs:__security_cookie
0x18000f79f  xor     rax, rsp
0x18000f7a2  mov     [rbp+810h+var_50], rax
0x18000f7a9  mov     r14, rcx
0x18000f7ac  mov     [rsp+910h+var_8C8], rcx
0x18000f7b1  lea     rdi, WPP_GLOBAL_Control
0x18000f7b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7bf  cmp     rcx, rdi
0x18000f7c2  jz      short loc_18000F7DF
0x18000f7c4  test    byte ptr [rcx+1Ch], 4
0x18000f7c8  jz      short loc_18000F7DF
0x18000f7ca  mov     edx, 23h ; '#'
0x18000f7cf  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x18000f7d6  mov     rcx, [rcx+10h]
0x18000f7da  call    WPP_SF_
0x18000f7df  lea     r12, DebugInfoEvent
0x18000f7e6  mov     rdx, r12
0x18000f7e9  mov     rcx, cs:eaphost_Context
0x18000f7f0  call    cs:__imp_EtwEventEnabled
0x18000f7f6  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000f7fa  mov     sil, 80h
0x18000f7fd  xor     r15d, r15d
0x18000f800  test    al, al
0x18000f802  jz      short loc_18000F85F
0x18000f804  lea     r8, aStartToSyncDev; "Start to sync devices with ECP registry"
0x18000f80b  mov     edx, 800h; unsigned __int64
0x18000f810  lea     rcx, [rbp+810h+var_850]; char *
0x18000f814  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000f819  test    eax, eax
0x18000f81b  js      short loc_18000F85F
0x18000f81d  test    cs:Microsoft_Windows_EapHostEnableBits, sil
0x18000f824  jz      short loc_18000F85F
0x18000f826  lea     rcx, [rbp+810h+var_850]
0x18000f82a  mov     rax, r13
0x18000f82d  inc     rax
0x18000f830  cmp     [rcx+rax], r15b
0x18000f834  jnz     short loc_18000F82D
0x18000f836  lea     rcx, [rbp+810h+var_850]
0x18000f83a  mov     [rbp+810h+var_860], rcx
0x18000f83e  inc     eax
0x18000f840  mov     [rbp+810h+var_858], eax
0x18000f843  mov     [rbp+810h+var_854], r15d
0x18000f847  lea     rax, [rbp+810h+var_870]
0x18000f84b  mov     [rsp+910h+var_8F0], rax
0x18000f850  mov     rdx, r12
0x18000f853  lea     rcx, eaphost_Context
0x18000f85a  call    McGenEventWrite_EtwEventWriteTransfer
0x18000f85f  mov     [rsp+910h+var_8D8], r15
0x18000f864  mov     [rbp+810h+hKey], r15
0x18000f868  mov     [rbp+810h+var_878], 1
0x18000f86f  mov     r9d, 9
0x18000f875  lea     r8, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\Ea"...
0x18000f87c  lea     rcx, [rbp+810h+hKey]
0x18000f880  call    ?Open@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK@Z; RegistryKey::Open(HKEY__ *,wchar_t const *,ulong)
0x18000f885  mov     ebx, eax
0x18000f887  mov     rcx, cs:eaphost_Context
0x18000f88e  cmp     eax, 1
0x18000f891  jnz     loc_18000F9F1
0x18000f897  mov     rdx, r12
0x18000f89a  call    cs:__imp_EtwEventEnabled
0x18000f8a0  test    al, al
0x18000f8a2  jz      short loc_18000F8FF
0x18000f8a4  lea     r8, aTheEcpKeyDoesN; "The ECP key does not exist"
0x18000f8ab  mov     edx, 800h; unsigned __int64
0x18000f8b0  lea     rcx, [rbp+810h+var_850]; char *
0x18000f8b4  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000f8b9  test    eax, eax
0x18000f8bb  js      short loc_18000F8FF
0x18000f8bd  test    cs:Microsoft_Windows_EapHostEnableBits, sil
0x18000f8c4  jz      short loc_18000F8FF
0x18000f8c6  lea     rcx, [rbp+810h+var_850]
0x18000f8ca  mov     rax, r13
0x18000f8cd  inc     rax
0x18000f8d0  cmp     [rcx+rax], r15b
0x18000f8d4  jnz     short loc_18000F8CD
0x18000f8d6  lea     rcx, [rbp+810h+var_850]
0x18000f8da  mov     [rbp+810h+var_860], rcx
0x18000f8de  inc     eax
0x18000f8e0  mov     [rbp+810h+var_858], eax
0x18000f8e3  mov     [rbp+810h+var_854], r15d
0x18000f8e7  lea     rax, [rbp+810h+var_870]
0x18000f8eb  mov     [rsp+910h+var_8F0], rax
0x18000f8f0  mov     rdx, r12
0x18000f8f3  lea     rcx, eaphost_Context
0x18000f8fa  call    McGenEventWrite_EtwEventWriteTransfer
0x18000f8ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f906  cmp     rcx, rdi
0x18000f909  jz      short loc_18000F926
0x18000f90b  test    byte ptr [rcx+1Ch], 4
0x18000f90f  jz      short loc_18000F926
0x18000f911  mov     edx, 24h ; '$'
0x18000f916  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x18000f91d  mov     rcx, [rcx+10h]
0x18000f921  call    WPP_SF_
0x18000f926  mov     [rsp+910h+pExceptionObject], r15b
0x18000f92b  lea     r8, [rsp+910h+pExceptionObject]
0x18000f930  lea     rdx, [rsp+910h+var_8D8]
0x18000f935  lea     rcx, [r14+48h]
0x18000f939  call    ?GetECPBusEnumerator@ECPDeviceManager@EapHost@@QEAAXAEAV?$CComPtr@UIUMBusPDO@@@ATL@@AEA_N@Z; EapHost::ECPDeviceManager::GetECPBusEnumerator(ATL::CComPtr<IUMBusPDO> &,bool &)
0x18000f93e  cmp     [rsp+910h+pExceptionObject], r15b
0x18000f943  jnz     loc_180010328
0x18000f949  mov     rdx, r12
0x18000f94c  mov     rcx, cs:eaphost_Context
0x18000f953  call    cs:__imp_EtwEventEnabled
0x18000f959  test    al, al
0x18000f95b  jz      short loc_18000F9B7
0x18000f95d  lea     r8, aEcpBusEnumerat; "ECP bus enumerator exists. Should be de"...
0x18000f964  mov     edx, 800h; unsigned __int64
0x18000f969  lea     rcx, [rbp+810h+var_850]; char *
0x18000f96d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000f972  test    eax, eax
0x18000f974  js      short loc_18000F9B7
0x18000f976  test    cs:Microsoft_Windows_EapHostEnableBits, sil
0x18000f97d  jz      short loc_18000F9B7
0x18000f97f  lea     rax, [rbp+810h+var_850]
0x18000f983  inc     r13
0x18000f986  cmp     [rax+r13], r15b
0x18000f98a  jnz     short loc_18000F983
0x18000f98c  lea     rax, [rbp+810h+var_850]
0x18000f990  mov     [rbp+810h+var_860], rax
0x18000f994  lea     eax, [r13+1]
0x18000f998  mov     [rbp+810h+var_858], eax
0x18000f99b  mov     [rbp+810h+var_854], r15d
0x18000f99f  lea     rax, [rbp+810h+var_870]
0x18000f9a3  mov     [rsp+910h+var_8F0], rax
0x18000f9a8  mov     rdx, r12
0x18000f9ab  lea     rcx, eaphost_Context
0x18000f9b2  call    McGenEventWrite_EtwEventWriteTransfer
0x18000f9b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f9be  cmp     rcx, rdi
0x18000f9c1  jz      short loc_18000F9DE
0x18000f9c3  test    byte ptr [rcx+1Ch], 4
0x18000f9c7  jz      short loc_18000F9DE
0x18000f9c9  mov     edx, 25h ; '%'
0x18000f9ce  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x18000f9d5  mov     rcx, [rcx+10h]
0x18000f9d9  call    WPP_SF_
0x18000f9de  lea     rdx, [rsp+910h+var_8D8]
0x18000f9e3  lea     rcx, [r14+48h]
0x18000f9e7  call    ?DeleteECPBusEnumerator@ECPDeviceManager@EapHost@@QEAAXAEAV?$CComPtr@UIUMBusPDO@@@ATL@@@Z; EapHost::ECPDeviceManager::DeleteECPBusEnumerator(ATL::CComPtr<IUMBusPDO> &)
0x18000f9ec  jmp     loc_180010328
0x18000f9f1  test    ebx, ebx
0x18000f9f3  jnz     loc_1800103F5
0x18000f9f9  mov     rdx, r12
0x18000f9fc  call    cs:__imp_EtwEventEnabled
0x18000fa02  test    al, al
0x18000fa04  jz      short loc_18000FA61
0x18000fa06  lea     r8, aEcpKeyExistsEn; "ECP key exists. Enumerating all subkeys"
0x18000fa0d  mov     edx, 800h; unsigned __int64
0x18000fa12  lea     rcx, [rbp+810h+var_850]; char *
0x18000fa16  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000fa1b  test    eax, eax
0x18000fa1d  js      short loc_18000FA61
0x18000fa1f  test    cs:Microsoft_Windows_EapHostEnableBits, sil
0x18000fa26  jz      short loc_18000FA61
0x18000fa28  lea     rcx, [rbp+810h+var_850]
0x18000fa2c  mov     rax, r13
0x18000fa2f  inc     rax
0x18000fa32  cmp     [rcx+rax], r15b
0x18000fa36  jnz     short loc_18000FA2F
0x18000fa38  lea     rcx, [rbp+810h+var_850]
0x18000fa3c  mov     [rbp+810h+var_860], rcx
0x18000fa40  inc     eax
0x18000fa42  mov     [rbp+810h+var_858], eax
0x18000fa45  mov     [rbp+810h+var_854], r15d
0x18000fa49  lea     rax, [rbp+810h+var_870]
0x18000fa4d  mov     [rsp+910h+var_8F0], rax
0x18000fa52  mov     rdx, r12
0x18000fa55  lea     rcx, eaphost_Context
0x18000fa5c  call    McGenEventWrite_EtwEventWriteTransfer
0x18000fa61  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa68  cmp     rcx, rdi
0x18000fa6b  jz      short loc_18000FA88
0x18000fa6d  test    byte ptr [rcx+1Ch], 4
0x18000fa71  jz      short loc_18000FA88
0x18000fa73  mov     edx, 26h ; '&'
0x18000fa78  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x18000fa7f  mov     rcx, [rcx+10h]
0x18000fa83  call    WPP_SF_
0x18000fa88  xorps   xmm0, xmm0
0x18000fa8b  movdqu  xmmword ptr [rsp+910h+S1], xmm0
0x18000fa91  mov     [rbp+810h+var_888], r15
0x18000fa95  lea     rdx, [rsp+910h+S1]
0x18000fa9a  lea     rcx, [rbp+810h+hKey]
0x18000fa9e  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18000faa3  mov     rbx, [rsp+910h+S1]
0x18000faa8  mov     rdi, [rbp+810h+S1+8]
0x18000faac  lea     rsi, WPP_GLOBAL_Control
0x18000fab3  cmp     rbx, rdi
0x18000fab6  jz      loc_18000FC20
0x18000fabc  mov     rcx, rbx
0x18000fabf  call    ?IsValidDeviceString@ECPManager@EapHost@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapHost::ECPManager::IsValidDeviceString(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18000fac4  test    al, al
0x18000fac6  jnz     loc_18000FC17
0x18000facc  lea     rdx, DebugErrorEvent
0x18000fad3  mov     rcx, cs:eaphost_Context
0x18000fada  call    cs:__imp_EtwEventEnabled
0x18000fae0  test    al, al
0x18000fae2  jz      short loc_18000FB50
0x18000fae4  mov     r9, rbx
0x18000fae7  cmp     qword ptr [rbx+18h], 7
0x18000faec  jbe     short loc_18000FAF1
0x18000faee  mov     r9, [rbx]
0x18000faf1  lea     r8, aKeySIsNotValid; "Key %S is not valid"
0x18000faf8  mov     edx, 800h; unsigned __int64
0x18000fafd  lea     rcx, [rbp+810h+var_850]; char *
0x18000fb01  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000fb06  test    eax, eax
0x18000fb08  js      short loc_18000FB50
0x18000fb0a  test    cs:byte_180020AC1, 8
0x18000fb11  jz      short loc_18000FB50
0x18000fb13  lea     rcx, [rbp+810h+var_850]
0x18000fb17  mov     rax, r13
0x18000fb1a  inc     rax
0x18000fb1d  cmp     [rcx+rax], r15b
0x18000fb21  jnz     short loc_18000FB1A
0x18000fb23  lea     rcx, [rbp+810h+var_850]
0x18000fb27  mov     [rbp+810h+var_860], rcx
0x18000fb2b  inc     eax
0x18000fb2d  mov     [rbp+810h+var_858], eax
0x18000fb30  mov     [rbp+810h+var_854], r15d
0x18000fb34  lea     rax, [rbp+810h+var_870]
0x18000fb38  mov     [rsp+910h+var_8F0], rax
0x18000fb3d  lea     rdx, DebugErrorEvent
0x18000fb44  lea     rcx, eaphost_Context
0x18000fb4b  call    McGenEventWrite_EtwEventWriteTransfer
0x18000fb50  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb57  cmp     rcx, rsi
0x18000fb5a  jz      short loc_18000FB86
0x18000fb5c  test    byte ptr [rcx+1Ch], 1
0x18000fb60  jz      short loc_18000FB86
0x18000fb62  cmp     qword ptr [rbx+18h], 7
0x18000fb67  jbe     short loc_18000FB6E
0x18000fb69  mov     r9, [rbx]
0x18000fb6c  jmp     short loc_18000FB71
0x18000fb6e  mov     r9, rbx
0x18000fb71  mov     edx, 27h ; '''
0x18000fb76  lea     r8, WPP_7b801e82f26e3453209b6da2f48854a6_Traceguids
0x18000fb7d  mov     rcx, [rcx+10h]
0x18000fb81  call    WPP_SF_S
0x18000fb86  mov     r14, rbx
0x18000fb89  lea     r15, [rbx+20h]
0x18000fb8d  jmp     short loc_18000FBE3
0x18000fb8f  cmp     r14, r15
0x18000fb92  jz      short loc_18000FBDB
0x18000fb94  cmp     qword ptr [r14+18h], 7
0x18000fb99  jbe     short loc_18000FBA3
0x18000fb9b  mov     rcx, [r14]; lpMem
0x18000fb9e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fba3  mov     qword ptr [r14+10h], 0
0x18000fbab  mov     qword ptr [r14+18h], 7
0x18000fbb3  xor     eax, eax
0x18000fbb5  mov     [r14], ax
0x18000fbb9  movups  xmm0, xmmword ptr [r15]
0x18000fbbd  movups  xmmword ptr [r14], xmm0
0x18000fbc1  movups  xmm1, xmmword ptr [r15+10h]
0x18000fbc6  movups  xmmword ptr [r14+10h], xmm1
0x18000fbcb  mov     [r15+10h], rax
0x18000fbcf  mov     qword ptr [r15+18h], 7
0x18000fbd7  mov     [r15], ax
0x18000fbdb  add     r14, 20h ; ' '
0x18000fbdf  add     r15, 20h ; ' '
0x18000fbe3  cmp     r15, rdi
0x18000fbe6  jnz     short loc_18000FB8F
0x18000fbe8  add     rdi, 0FFFFFFFFFFFFFFE0h
0x18000fbec  cmp     qword ptr [rdi+18h], 7
0x18000fbf1  jbe     short loc_18000FBFB
0x18000fbf3  mov     rcx, [rdi]; lpMem
0x18000fbf6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000fbfb  xor     r15d, r15d
0x18000fbfe  mov     [rdi+10h], r15
0x18000fc02  mov     qword ptr [rdi+18h], 7
0x18000fc0a  mov     [rdi], r15w
0x18000fc0e  mov     [rbp+810h+S1+8], rdi
0x18000fc12  jmp     loc_18000FAB3
0x18000fc17  add     rbx, 20h ; ' '
0x18000fc1b  jmp     loc_18000FAB3
0x18000fc20  mov     rdx, r12
0x18000fc23  mov     rcx, cs:eaphost_Context
0x18000fc2a  call    cs:__imp_EtwEventEnabled
0x18000fc30  test    al, al
0x18000fc32  mov     rsi, [rsp+910h+S1]
0x18000fc37  jz      short loc_18000FC9E
0x18000fc39  mov     r9, rdi
0x18000fc3c  sub     r9, rsi
0x18000fc3f  sar     r9, 5
0x18000fc43  lea     r8, aFoundIuValidCo; "Found %Iu valid component keys:"
0x18000fc4a  mov     edx, 800h; unsigned __int64
0x18000fc4f  lea     rcx, [rbp+810h+var_850]; char *
0x18000fc53  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
  ... truncated ...
```
