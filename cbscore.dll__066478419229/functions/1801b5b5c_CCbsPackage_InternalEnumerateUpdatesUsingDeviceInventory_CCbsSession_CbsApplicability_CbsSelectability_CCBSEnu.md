# CCbsPackage::InternalEnumerateUpdatesUsingDeviceInventory(CCbsSession *,_CbsApplicability,_CbsSelectability,CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong> *,bool *)

- ea: `0x1801b5b5c`
- end: `0x1801b6686`
- name: `?InternalEnumerateUpdatesUsingDeviceInventory@CCbsPackage@@AEAAJPEAVCCbsSession@@W4_CbsApplicability@@W4_CbsSelectability@@PEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@PEA_N@Z`
- size: `2858`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801a6c00`

## callees

- `0x18000c70c`
- `0x180010cc0`
- `0x1800133a4`
- `0x1800138b8`
- `0x18001d7f8`
- `0x180023f30`
- `0x18002573c`
- `0x18002c34c`
- `0x18002cae4`
- `0x180068404`
- `0x180093c4c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x180128510`
- `0x1801a5494`
- `0x1801a8b68`
- `0x1801b5b5c`
- `0x1801d7de0`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b60bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b619a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b6424`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b665f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b60bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b619a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b6424`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b665f`

## string_xrefs

- `0x1801b634d`: `Failed to get internal update, package: {}, update: {}`
- `0x1801b6601`: `Failed getting update CbsUpdatePropertyName property`
- `0x1801b61f2`: `Failed to create an instance of the update for public use.`
- `0x1801b62c0`: `Failed to get current state on package: {}, update: {}`
- `0x1801b6593`: `Failed to get the Parent package for the update`
- `0x1801b5be2`: `Failed to allocate update enumerator.`
- `0x1801b5ca0`: `Failed to enumerate updates using DeviceInventory.xml`
- `0x1801b5da7`: `Failed to enumerate updates using DeviceInventory.xml`

## pseudocode

```c
__int64 __fastcall CCbsPackage::InternalEnumerateUpdatesUsingDeviceInventory(
        int a1,
        CCbsSession *a2,
        int a3,
        int a4,
        __int64 a5,
        _BYTE *a6)
{
  unsigned int v10; // ebx
  int v11; // edx
  char *v12; // rdx
  int v14; // eax
  struct LogAdapter::Logger *v15; // rcx
  int v16; // edx
  char *v17; // rcx
  CCbsUpdate *v18; // rbx
  int v19; // eax
  int PublicInstance; // esi
  struct LogAdapter::Logger *v21; // rcx
  int v22; // edx
  char *v23; // rcx
  unsigned __int64 v24; // r15
  __int64 v25; // r13
  __int64 v26; // rsi
  __int64 (__fastcall *v27)(__int64, __int64, __int64); // rdi
  __int64 InitPointer; // rax
  __int64 (__fastcall *v29)(__int64, __int64); // rdi
  __int64 v30; // rax
  __int64 v31; // rsi
  __int64 (__fastcall *v32)(__int64, __int64); // rdi
  __int64 v33; // rax
  struct CCbsPackage **v34; // rax
  struct ICbsUIHandler *v35; // r9
  CCbsIdentity *v36; // r14
  CCbsPackage **v37; // rsi
  CCbsPackage **v38; // rdi
  CCbsPackage *v39; // rdi
  struct CCbsUpdate **v40; // rax
  struct CCbsSession *v41; // rdx
  int InternalUpdate; // r14d
  CCbsPackage *v43; // rcx
  CCbsUpdate *v44; // rdi
  struct CCbsPublicUpdate **v45; // rax
  __int64 v46; // rdx
  int v47; // eax
  unsigned int v48; // edi
  int v49; // eax
  char *v50; // rcx
  char *v51; // rcx
  int v52; // edx
  const wchar_t *v53; // rdx
  int v54; // edx
  __int64 v55; // rdx
  const wchar_t *v56; // rdx
  int v57; // edx
  char *v58; // rcx
  int v59; // edx
  int v60; // edx
  int v61; // edx
  int v62; // edx
  int v63; // [rsp+20h] [rbp-E0h]
  int v64; // [rsp+20h] [rbp-E0h]
  int v65[2]; // [rsp+70h] [rbp-90h] BYREF
  CCbsUpdate *v66; // [rsp+78h] [rbp-88h] BYREF
  int v67[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v68; // [rsp+88h] [rbp-78h] BYREF
  int v69[2]; // [rsp+90h] [rbp-70h] BYREF
  int v70; // [rsp+98h] [rbp-68h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v72; // [rsp+A8h] [rbp-58h] BYREF
  struct ICbsIdentity *v73; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v74; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v75[24]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v76; // [rsp+D8h] [rbp-28h]
  CCbsPackage **v77; // [rsp+E8h] [rbp-18h]
  _BYTE v78[64]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  *(_QWORD *)v65 = a5;
  v66 = 0;
  CCbsInterfaceArray<CCbsPackage *>::CCbsInterfaceArray<CCbsPackage *>(v78);
  if ( !Windows::AutoComPtr<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>>::AllocateWithNew<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>,>(&v66) )
  {
    v10 = -2147024882;
    v70 = -2147024882;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to allocate update enumerator.");
      *(_QWORD *)v65 = &v70;
      LOBYTE(v11) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v11,
        3,
        (unsigned int)": {}",
        (__int64)v65);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x109,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
      (const char *)0x8007000ELL,
      v63);
    CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
    if ( v66 )
    {
      v12 = (char *)v66 + *(int *)(*((_QWORD *)v66 + 1) + 4LL);
      (*(void (__fastcall **)(char *))(*((_QWORD *)v12 + 1) + 16LL))(v12 + 8);
    }
    return v10;
  }
  CCbsInterfaceArray<CCbsPackage *>::CCbsInterfaceArray<CCbsPackage *>(v75);
  v14 = CCbsSession::ProcessDeviceInventoryXML(a2);
  v10 = v14;
  if ( v14 < 0 )
  {
    v15 = LogAdapter::g_Logger;
    *a6 = 1;
    v70 = v14;
    if ( v15 )
    {
      LogAdapter::Logger::LogNumObjects<>(v15, 0, 3, "Failed to enumerate updates using DeviceInventory.xml");
      *(_QWORD *)v65 = &v70;
      LOBYTE(v16) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v16,
        3,
        (unsigned int)": {}",
        (__int64)v65);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
      (const char *)v10,
      v63);
    CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v75);
    CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
    if ( v66 )
    {
      v17 = (char *)v66 + *(int *)(*((_QWORD *)v66 + 1) + 4LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v10;
  }
  v18 = v66;
  v19 = CCbsPackage::InternalEnumerateUpdate(
          a1,
          (_DWORD)a2,
          (unsigned int)v78,
          a3,
          a4,
          0,
          0,
          1,
          (__int64)v66,
          1,
          1,
          0,
          0);
  PublicInstance = v19;
  if ( v19 >= 0 )
  {
    v24 = 0;
    if ( !*((_QWORD *)v18 + 6) )
    {
LABEL_48:
      CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v75);
      CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
      v50 = (char *)v18 + *(int *)(*((_QWORD *)v18 + 1) + 4LL) + 8;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v50 + 16LL))(v50);
      return 0;
    }
    while ( 1 )
    {
      v25 = *(_QWORD *)(*((_QWORD *)v18 + 8) + 8 * v24);
      pv = 0;
      if ( v24 >= *((_QWORD *)v18 + 6) )
        __fastfail(8u);
      v26 = *(_QWORD *)(*((_QWORD *)v18 + 8) + 8 * v24);
      v27 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v26 + 24LL);
      InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&pv);
      PublicInstance = v27(v26, 1, InitPointer);
      if ( PublicInstance < 0 )
        break;
      v72 = 0;
      v29 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 32LL);
      v30 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v72);
      PublicInstance = v29(v25, v30);
      if ( PublicInstance < 0 )
      {
        v70 = PublicInstance;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to get the Parent package for the update");
          *(_QWORD *)v67 = &v70;
          LOBYTE(v61) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v61,
            3,
            (unsigned int)": {}",
            (__int64)v67);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12F,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
          (const char *)(unsigned int)PublicInstance,
          v64);
        goto LABEL_63;
      }
      v31 = v72;
      v73 = 0;
      v32 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v72 + 24LL);
      v33 = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v73);
      PublicInstance = v32(v31, v33);
      if ( PublicInstance < 0 )
      {
        v70 = PublicInstance;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get Parent package identity.");
          *(_QWORD *)v67 = &v70;
          LOBYTE(v60) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v60,
            3,
            (unsigned int)": {}",
            (__int64)v67);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x132,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
          (const char *)(unsigned int)PublicInstance,
          v64);
        goto LABEL_61;
      }
      v74 = 0;
      v34 = (struct CCbsPackage **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v74);
      PublicInstance = CCbsSession::ResolvePackage(a2, 0, 0, v35, v73, 1, v34, 0);
      if ( PublicInstance < 0 )
      {
        v70 = PublicInstance;
        if ( LogAdapter::g_Logger )
        {
          *(_QWORD *)v67 = GetFastCbsIdentityString(v73);
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            0,
            3,
            (unsigned int)"Failed to resolve package {}",
            (__int64)v67);
          *(_QWORD *)v69 = &v70;
          LOBYTE(v59) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v59,
            3,
            (unsigned int)": {}",
            (__int64)v69);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13E,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
          (const char *)(unsigned int)PublicInstance,
          v64);
LABEL_60:
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v74);
LABEL_61:
        if ( v73 )
        {
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v73 + 16LL))(v73);
          v73 = 0;
        }
LABEL_63:
        if ( v72 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
          v72 = 0;
        }
LABEL_95:
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v75);
        CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
        goto LABEL_16;
      }
      v36 = *(CCbsIdentity **)(v74 + 112);
      v68 = 0;
      v37 = v77;
      v38 = &v77[v76];
      if ( v77 != v38 )
      {
        while ( !(unsigned int)CCbsIdentity::IsFastEqual(v36, *((struct CCbsIdentity **)*v37 + 14)) )
        {
          if ( ++v37 == v38 )
            goto LABEL_39;
        }
        v39 = *v37;
        v66 = 0;
        v40 = (struct CCbsUpdate **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v66);
        InternalUpdate = CCbsPackage::GetInternalUpdate(v39, (const wchar_t *)pv, v40);
        if ( InternalUpdate < 0 )
        {
          v70 = InternalUpdate;
          if ( LogAdapter::g_Logger )
          {
            v56 = &qword_1802EB518;
            *(_QWORD *)v67 = pv;
            if ( *((_QWORD *)*v37 + 15) )
              v56 = (const wchar_t *)*((_QWORD *)*v37 + 15);
            *(_QWORD *)v69 = v56;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to get internal update, package: {}, update: {}",
              (__int64)v69,
              (__int64)v67);
            *(_QWORD *)v65 = &v70;
            LOBYTE(v57) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v57,
              3,
              (unsigned int)": {}",
              (__int64)v65);
          }
          v55 = 329;
          goto LABEL_75;
        }
        v43 = *v37;
        v70 = 4096;
        InternalUpdate = CCbsPackage::GetCurrentState(v43, v41, (enum CbsState *)&v70);
        if ( InternalUpdate < 0 )
        {
          v70 = InternalUpdate;
          if ( LogAdapter::g_Logger )
          {
            v53 = &qword_1802EB518;
            *(_QWORD *)v65 = pv;
            if ( *((_QWORD *)*v37 + 15) )
              v53 = (const wchar_t *)*((_QWORD *)*v37 + 15);
            *(_QWORD *)v69 = v53;
            LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
              (_DWORD)LogAdapter::g_Logger,
              0,
              3,
              (unsigned int)"Failed to get current state on package: {}, update: {}",
              (__int64)v69,
              (__int64)v65);
            *(_QWORD *)v67 = &v70;
            LOBYTE(v54) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v54,
              3,
              (unsigned int)": {}",
              (__int64)v67);
          }
          v55 = 333;
LABEL_75:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v55,
            (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
            (const char *)(unsigned int)InternalUpdate,
            v64);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v66);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v68);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v74);
          if ( v73 )
          {
            (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v73 + 16LL))(v73);
            v73 = 0;
          }
          if ( v72 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
            v72 = 0;
          }
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v75);
          CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
          v58 = (char *)v18 + *(int *)(*((_QWORD *)v18 + 1) + 4LL) + 8;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v58 + 16LL))(v58);
          return (unsigned int)InternalUpdate;
        }
        if ( v70 != 4096 )
          *((_DWORD *)v66 + 110) = v70;
        v44 = v66;
        v45 = (struct CCbsPublicUpdate **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v68);
        PublicInstance = CCbsUpdate::CreatePublicInstance(v44, a2, v45);
        if ( PublicInstance < 0 )
        {
          v70 = PublicInstance;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(
              LogAdapter::g_Logger,
              0,
              3,
              "Failed to create an instance of the update for public use.");
            *(_QWORD *)v65 = &v70;
            LOBYTE(v52) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v52,
              3,
              (unsigned int)": {}",
              (__int64)v65);
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x156,
            (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
            (const char *)(unsigned int)PublicInstance,
            v64);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v66);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v68);
          goto LABEL_60;
        }
        if ( v68 )
          v46 = *(int *)(*(_QWORD *)(v68 + 8) + 4LL) + v68 + 8;
        else
          v46 = 0;
        v47 = CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>::Add(*(_QWORD *)v65, v46);
        v48 = v47;
        if ( v47 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x158,
            (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
            (const char *)(unsigned int)v47,
            v64);
          Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v66);
          goto LABEL_50;
        }
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v66);
LABEL_39:
        if ( v68 )
          goto LABEL_41;
      }
      v49 = CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,unsigned long>::Add(*(_QWORD *)v65, v25);
      v48 = v49;
      if ( v49 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x163,
          (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
          (const char *)(unsigned int)v49,
          v64);
LABEL_50:
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v68);
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v74);
        if ( v73 )
        {
          (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v73 + 16LL))(v73);
          v73 = 0;
        }
        if ( v72 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
          v72 = 0;
        }
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v75);
        CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
        v51 = (char *)v18 + *(int *)(*((_QWORD *)v18 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v51 + 16LL))(v51);
        return v48;
      }
LABEL_41:
      Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v68);
      Windows::AutoComPtr<CCbsDriverDeployment>::Close(&v74);
      if ( v73 )
      {
        (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v73 + 16LL))(v73);
        v73 = 0;
      }
      if ( v72 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
        v72 = 0;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( ++v24 >= *((_QWORD *)v18 + 6) )
        goto LABEL_48;
    }
    v70 = PublicInstance;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        LogAdapter::g_Logger,
        0,
        3,
        "Failed getting update CbsUpdatePropertyName property");
      *(_QWORD *)v67 = &v70;
      LOBYTE(v62) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (_DWORD)LogAdapter::g_Logger,
        v62,
        3,
        (unsigned int)": {}",
        (__int64)v67);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
      (const char *)(unsigned int)PublicInstance,
      v64);
    goto LABEL_95;
  }
  v21 = LogAdapter::g_Logger;
  *a6 = 1;
  v70 = v19;
  if ( v21 )
  {
    LogAdapter::Logger::LogNumObjects<>(v21, 0, 3, "Failed to enumerate updates using DeviceInventory.xml");
    *(_QWORD *)v65 = &v70;
    LOBYTE(v22) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v22,
      3,
      (unsigned int)": {}",
      (__int64)v65);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x122,
    (unsigned int)"onecore\\base\\cbs\\core\\cbspackageinventory.cpp",
    (const char *)(unsigned int)PublicInstance,
    v64);
  CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v75);
  CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(v78);
  if ( v18 )
  {
LABEL_16:
    v23 = (char *)v18 + *(int *)(*((_QWORD *)v18 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 16LL))(v23);
  }
  return (unsigned int)PublicInstance;
}

```

## disassembly

```asm
0x1801b5b5c  push    rbp
0x1801b5b5e  push    rbx
0x1801b5b5f  push    rsi
0x1801b5b60  push    rdi
0x1801b5b61  push    r12
0x1801b5b63  push    r13
0x1801b5b65  push    r14
0x1801b5b67  push    r15
0x1801b5b69  lea     rbp, [rsp-58h]
0x1801b5b6e  sub     rsp, 158h
0x1801b5b75  mov     rax, cs:__security_cookie
0x1801b5b7c  xor     rax, rsp
0x1801b5b7f  mov     [rbp+90h+var_50], rax
0x1801b5b83  mov     rax, [rbp+90h+arg_20]
0x1801b5b8a  mov     rsi, rcx
0x1801b5b8d  mov     rdi, [rbp+90h+arg_28]
0x1801b5b94  lea     rcx, [rbp+90h+var_90]
0x1801b5b98  xor     r13d, r13d
0x1801b5b9b  mov     qword ptr [rsp+190h+var_120], rax
0x1801b5ba0  mov     [rsp+190h+var_118], r13
0x1801b5ba5  mov     r15d, r9d
0x1801b5ba8  mov     r14d, r8d
0x1801b5bab  mov     r12, rdx
0x1801b5bae  call    ??0?$CCbsInterfaceArray@PEAVCCbsPackage@@@@QEAA@XZ; CCbsInterfaceArray<CCbsPackage *>::CCbsInterfaceArray<CCbsPackage *>(void)
0x1801b5bb3  lea     rcx, [rsp+190h+var_118]
0x1801b5bb8  call    ??$AllocateWithNew@V?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@$$V@?$AutoComPtr@V?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@@Windows@@QEAAPEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@XZ; Windows::AutoComPtr<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong>>::AllocateWithNew<CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong>,>(void)
0x1801b5bbd  test    rax, rax
0x1801b5bc0  jnz     loc_1801B5C6A
0x1801b5bc6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b5bcd  mov     ebx, 8007000Eh
0x1801b5bd2  mov     [rbp+90h+var_F8], ebx
0x1801b5bd5  test    rcx, rcx
0x1801b5bd8  jz      short loc_1801B5C19
0x1801b5bda  lea     edi, [rax+3]
0x1801b5bdd  xor     edx, edx
0x1801b5bdf  mov     r8d, edi
0x1801b5be2  lea     r9, aFailedToAlloca_14; "Failed to allocate update enumerator."
0x1801b5be9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b5bee  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b5bf5  lea     rax, [rbp+90h+var_F8]
0x1801b5bf9  mov     qword ptr [rsp+190h+var_120], rax
0x1801b5bfe  lea     r9, asc_1802EE7AC; ": {}"
0x1801b5c05  lea     rax, [rsp+190h+var_120]
0x1801b5c0a  mov     r8d, edi
0x1801b5c0d  mov     dl, 1
0x1801b5c0f  mov     [rsp+190h+var_170], rax; int
0x1801b5c14  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b5c19  mov     rcx, [rbp+98h]; this
0x1801b5c20  lea     r8, aOnecoreBaseCbs_75; "onecore\\base\\cbs\\core\\cbspackageinv"...
0x1801b5c27  mov     r9d, ebx; char *
0x1801b5c2a  mov     edx, 109h; void *
0x1801b5c2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b5c34  lea     rcx, [rbp+90h+var_90]
0x1801b5c38  call    ??1?$CCbsArrayBase@PEAVCCbsPackage@@V?$CCbsInterfaceArray@PEAVCCbsPackage@@@@@@MEAA@XZ; CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(void)
0x1801b5c3d  mov     rcx, [rsp+190h+var_118]
0x1801b5c42  test    rcx, rcx
0x1801b5c45  jz      short loc_1801B5C63
0x1801b5c47  mov     rdx, [rcx+8]
0x1801b5c4b  movsxd  rdx, dword ptr [rdx+4]
0x1801b5c4f  add     rdx, rcx
0x1801b5c52  mov     rcx, [rdx+8]
0x1801b5c56  mov     rax, [rcx+10h]
0x1801b5c5a  lea     rcx, [rdx+8]
0x1801b5c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5c63  mov     eax, ebx
0x1801b5c65  jmp     loc_1801B6107
0x1801b5c6a  lea     rcx, [rbp+90h+var_D0]
0x1801b5c6e  call    ??0?$CCbsInterfaceArray@PEAVCCbsPackage@@@@QEAA@XZ; CCbsInterfaceArray<CCbsPackage *>::CCbsInterfaceArray<CCbsPackage *>(void)
0x1801b5c73  lea     rdx, [rbp+90h+var_D0]
0x1801b5c77  mov     rcx, r12; this
0x1801b5c7a  call    ?ProcessDeviceInventoryXML@CCbsSession@@QEAAJPEAV?$CCbsInterfaceArray@PEAVCCbsPackage@@@@@Z; CCbsSession::ProcessDeviceInventoryXML(CCbsInterfaceArray<CCbsPackage *> *)
0x1801b5c7f  mov     ebx, eax
0x1801b5c81  test    eax, eax
0x1801b5c83  jns     loc_1801B5D32
0x1801b5c89  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b5c90  mov     byte ptr [rdi], 1
0x1801b5c93  mov     [rbp+90h+var_F8], eax
0x1801b5c96  test    rcx, rcx
0x1801b5c99  jz      short loc_1801B5CDC
0x1801b5c9b  mov     edi, 3
0x1801b5ca0  lea     r9, aFailedToEnumer_45; "Failed to enumerate updates using Devic"...
0x1801b5ca7  mov     r8d, edi
0x1801b5caa  xor     edx, edx
0x1801b5cac  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b5cb1  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b5cb8  lea     rax, [rbp+90h+var_F8]
0x1801b5cbc  mov     qword ptr [rsp+190h+var_120], rax
0x1801b5cc1  lea     r9, asc_1802EE7AC; ": {}"
0x1801b5cc8  lea     rax, [rsp+190h+var_120]
0x1801b5ccd  mov     r8d, edi
0x1801b5cd0  mov     dl, 1
0x1801b5cd2  mov     [rsp+190h+var_170], rax; int
0x1801b5cd7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b5cdc  mov     rcx, [rbp+98h]; this
0x1801b5ce3  lea     r8, aOnecoreBaseCbs_75; "onecore\\base\\cbs\\core\\cbspackageinv"...
0x1801b5cea  mov     r9d, ebx; char *
0x1801b5ced  mov     edx, 111h; void *
0x1801b5cf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b5cf7  lea     rcx, [rbp+90h+var_D0]
0x1801b5cfb  call    ??1?$CCbsArrayBase@PEAVCCbsPackage@@V?$CCbsInterfaceArray@PEAVCCbsPackage@@@@@@MEAA@XZ; CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(void)
0x1801b5d00  lea     rcx, [rbp+90h+var_90]
0x1801b5d04  call    ??1?$CCbsArrayBase@PEAVCCbsPackage@@V?$CCbsInterfaceArray@PEAVCCbsPackage@@@@@@MEAA@XZ; CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(void)
0x1801b5d09  mov     rax, [rsp+190h+var_118]
0x1801b5d0e  test    rax, rax
0x1801b5d11  jz      loc_1801B5C63
0x1801b5d17  mov     rcx, [rax+8]
0x1801b5d1b  add     rax, 8
0x1801b5d1f  movsxd  rcx, dword ptr [rcx+4]
0x1801b5d23  add     rcx, rax
0x1801b5d26  mov     rax, [rcx]
0x1801b5d29  mov     rax, [rax+10h]
0x1801b5d2d  jmp     loc_1801B5C5E
0x1801b5d32  mov     rbx, [rsp+190h+var_118]
0x1801b5d37  lea     r8, [rbp+90h+var_90]
0x1801b5d3b  mov     [rsp+190h+var_130], r13
0x1801b5d40  mov     r9d, r14d
0x1801b5d43  mov     [rsp+190h+var_138], r13
0x1801b5d48  mov     rdx, r12
0x1801b5d4b  mov     [rsp+190h+var_140], 1
0x1801b5d53  mov     rcx, rsi
0x1801b5d56  mov     [rsp+190h+var_148], 1
0x1801b5d5e  mov     [rsp+190h+var_150], rbx
0x1801b5d63  mov     [rsp+190h+var_158], 1
0x1801b5d6b  mov     [rsp+190h+var_160], r13
0x1801b5d70  mov     [rsp+190h+var_168], r13d
0x1801b5d75  mov     dword ptr [rsp+190h+var_170], r15d
0x1801b5d7a  call    ?InternalEnumerateUpdate@CCbsPackage@@AEAAJPEAVCCbsSession@@PEAV?$CCbsInterfaceArray@PEAVCCbsPackage@@@@W4_CbsApplicability@@W4_CbsSelectability@@HPEB_WHPEAV?$CCBSEnumInterfaceImpl@UIEnumCbsUpdate@@UICbsUpdate@@K@@HHPEAPEA_WPEAJ@Z; CCbsPackage::InternalEnumerateUpdate(CCbsSession *,CCbsInterfaceArray<CCbsPackage *> *,_CbsApplicability,_CbsSelectability,int,wchar_t const *,int,CCBSEnumInterfaceImpl<IEnumCbsUpdate,ICbsUpdate,ulong> *,int,int,wchar_t * *,long *)
0x1801b5d7f  xor     r14d, r14d
0x1801b5d82  mov     esi, eax
0x1801b5d84  test    eax, eax
0x1801b5d86  jns     loc_1801B5E32
0x1801b5d8c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b5d93  mov     byte ptr [rdi], 1
0x1801b5d96  mov     [rbp+90h+var_F8], eax
0x1801b5d99  test    rcx, rcx
0x1801b5d9c  jz      short loc_1801B5DDE
0x1801b5d9e  lea     edi, [r14+3]
0x1801b5da2  xor     edx, edx
0x1801b5da4  mov     r8d, edi
0x1801b5da7  lea     r9, aFailedToEnumer_45; "Failed to enumerate updates using Devic"...
0x1801b5dae  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801b5db3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801b5dba  lea     rax, [rbp+90h+var_F8]
0x1801b5dbe  mov     qword ptr [rsp+190h+var_120], rax
0x1801b5dc3  lea     r9, asc_1802EE7AC; ": {}"
0x1801b5dca  lea     rax, [rsp+190h+var_120]
0x1801b5dcf  mov     r8d, edi
0x1801b5dd2  mov     dl, 1
0x1801b5dd4  mov     [rsp+190h+var_170], rax; int
0x1801b5dd9  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801b5dde  mov     rcx, [rbp+98h]; this
0x1801b5de5  lea     r8, aOnecoreBaseCbs_75; "onecore\\base\\cbs\\core\\cbspackageinv"...
0x1801b5dec  mov     r9d, esi; char *
0x1801b5def  mov     edx, 122h; void *
0x1801b5df4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801b5df9  lea     rcx, [rbp+90h+var_D0]
0x1801b5dfd  call    ??1?$CCbsArrayBase@PEAVCCbsPackage@@V?$CCbsInterfaceArray@PEAVCCbsPackage@@@@@@MEAA@XZ; CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(void)
0x1801b5e02  lea     rcx, [rbp+90h+var_90]
0x1801b5e06  call    ??1?$CCbsArrayBase@PEAVCCbsPackage@@V?$CCbsInterfaceArray@PEAVCCbsPackage@@@@@@MEAA@XZ; CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>::~CCbsArrayBase<CCbsPackage *,CCbsInterfaceArray<CCbsPackage *>>(void)
0x1801b5e0b  test    rbx, rbx
0x1801b5e0e  jz      short loc_1801B5E2B
0x1801b5e10  mov     rax, [rbx+8]
0x1801b5e14  movsxd  rcx, dword ptr [rax+4]
0x1801b5e18  add     rcx, 8
0x1801b5e1c  add     rcx, rbx
0x1801b5e1f  mov     rax, [rcx]
0x1801b5e22  mov     rax, [rax+10h]
0x1801b5e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5e2b  mov     eax, esi
0x1801b5e2d  jmp     loc_1801B6107
0x1801b5e32  mov     r15, r14
0x1801b5e35  cmp     [rbx+30h], r14
0x1801b5e39  jbe     loc_1801B60D8
0x1801b5e3f  cmp     r14, [rbx+30h]
0x1801b5e43  jb      short loc_1801B5E4C
0x1801b5e45  mov     ecx, 8
0x1801b5e4a  int     29h; Win8: RtlFailFast(ecx)
0x1801b5e4c  mov     rax, [rbx+40h]
0x1801b5e50  mov     r13, [rax+r15*8]
0x1801b5e54  mov     [rbp+90h+pv], r14
0x1801b5e58  cmp     r15, [rbx+30h]
0x1801b5e5c  jb      short loc_1801B5E65
0x1801b5e5e  mov     ecx, 8
0x1801b5e63  int     29h; Win8: RtlFailFast(ecx)
0x1801b5e65  mov     rax, [rbx+40h]
0x1801b5e69  lea     rcx, [rbp+90h+pv]
0x1801b5e6d  mov     rsi, [rax+r15*8]
0x1801b5e71  mov     rax, [rsi]
0x1801b5e74  mov     rdi, [rax+18h]
0x1801b5e78  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801b5e7d  mov     r8, rax
0x1801b5e80  mov     edx, 1
0x1801b5e85  mov     rax, rdi
0x1801b5e88  mov     rcx, rsi
0x1801b5e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5e90  mov     esi, eax
0x1801b5e92  test    eax, eax
0x1801b5e94  js      loc_1801B65ED
0x1801b5e9a  mov     [rbp+90h+var_E8], r14
0x1801b5e9e  lea     rcx, [rbp+90h+var_E8]
0x1801b5ea2  mov     rax, [r13+0]
0x1801b5ea6  mov     rdi, [rax+20h]
0x1801b5eaa  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801b5eaf  mov     rdx, rax
0x1801b5eb2  mov     rcx, r13
0x1801b5eb5  mov     rax, rdi
0x1801b5eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5ebd  mov     esi, eax
0x1801b5ebf  test    eax, eax
0x1801b5ec1  js      loc_1801B657F
0x1801b5ec7  mov     rsi, [rbp+90h+var_E8]
0x1801b5ecb  lea     rcx, [rbp+90h+var_E0]
0x1801b5ecf  mov     [rbp+90h+var_E0], r14
0x1801b5ed3  mov     rax, [rsi]
0x1801b5ed6  mov     rdi, [rax+18h]
0x1801b5eda  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801b5edf  mov     rdx, rax
0x1801b5ee2  mov     rcx, rsi
0x1801b5ee5  mov     rax, rdi
0x1801b5ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5eed  mov     esi, eax
0x1801b5eef  test    eax, eax
0x1801b5ef1  js      loc_1801B6511
0x1801b5ef7  lea     rcx, [rbp+90h+var_D8]
0x1801b5efb  mov     [rbp+90h+var_D8], r14
0x1801b5eff  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801b5f04  mov     rcx, [rbp+90h+var_E0]
0x1801b5f08  xor     r8d, r8d; void *
0x1801b5f0b  mov     [rsp+190h+var_158], r14d; int
0x1801b5f10  xor     edx, edx; struct PerSessionPackageState *
0x1801b5f12  mov     [rsp+190h+var_160], rax; struct CCbsPackage **
0x1801b5f17  mov     [rsp+190h+var_168], 1; int
0x1801b5f1f  mov     [rsp+190h+var_170], rcx; int
0x1801b5f24  mov     rcx, r12; this
0x1801b5f27  call    ?ResolvePackage@CCbsSession@@QEAAJPEAUPerSessionPackageState@@PEAXPEAUICbsUIHandler@@PEAUICbsIdentity@@HPEAPEAVCCbsPackage@@H@Z; CCbsSession::ResolvePackage(PerSessionPackageState *,void *,ICbsUIHandler *,ICbsIdentity *,int,CCbsPackage * *,int)
0x1801b5f2c  mov     esi, eax
0x1801b5f2e  test    eax, eax
0x1801b5f30  js      loc_1801B6489
0x1801b5f36  mov     rax, [rbp+90h+var_D8]
0x1801b5f3a  mov     rcx, [rbp+90h+var_B8]
0x1801b5f3e  mov     r14, [rax+70h]
0x1801b5f42  mov     rax, [rbp+90h+var_A8]
0x1801b5f46  mov     [rbp+90h+var_108], 0
0x1801b5f4e  mov     rsi, rax
0x1801b5f51  lea     rdi, [rax+rcx*8]
0x1801b5f55  cmp     rax, rdi
0x1801b5f58  jz      loc_1801B6054
0x1801b5f5e  mov     rdx, [rsi]
0x1801b5f61  mov     rcx, r14; this
0x1801b5f64  mov     rdx, [rdx+70h]; struct CCbsIdentity *
0x1801b5f68  call    ?IsFastEqual@CCbsIdentity@@QEBAHPEAV1@@Z; CCbsIdentity::IsFastEqual(CCbsIdentity *)
0x1801b5f6d  test    eax, eax
0x1801b5f6f  jnz     short loc_1801B5F82
0x1801b5f71  add     rsi, 8
0x1801b5f75  cmp     rsi, rdi
0x1801b5f78  jnz     short loc_1801B5F5E
0x1801b5f7a  xor     r14d, r14d
0x1801b5f7d  jmp     loc_1801B604C
0x1801b5f82  mov     rdi, [rsi]
0x1801b5f85  lea     rcx, [rsp+190h+var_118]
0x1801b5f8a  mov     [rsp+190h+var_118], 0
0x1801b5f93  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801b5f98  mov     rdx, [rbp+90h+pv]; wchar_t *
0x1801b5f9c  mov     r8, rax; struct CCbsUpdate **
0x1801b5f9f  mov     rcx, rdi; this
0x1801b5fa2  call    ?GetInternalUpdate@CCbsPackage@@QEAAJPEB_WPEAPEAVCCbsUpdate@@@Z; CCbsPackage::GetInternalUpdate(wchar_t const *,CCbsUpdate * *)
0x1801b5fa7  xor     edi, edi
0x1801b5fa9  mov     r14d, eax
0x1801b5fac  test    eax, eax
0x1801b5fae  js      loc_1801B632E
0x1801b5fb4  mov     rcx, [rsi]; this
0x1801b5fb7  lea     r8, [rbp+90h+var_F8]; enum CbsState *
0x1801b5fbb  mov     [rbp+90h+var_F8], 1000h
0x1801b5fc2  call    ?GetCurrentState@CCbsPackage@@QEBAJPEAVCCbsSession@@PEAW4CbsState@@@Z; CCbsPackage::GetCurrentState(CCbsSession *,CbsState *)
0x1801b5fc7  mov     r14d, eax
0x1801b5fca  test    eax, eax
0x1801b5fcc  js      loc_1801B62A0
0x1801b5fd2  mov     ecx, [rbp+90h+var_F8]
0x1801b5fd5  cmp     ecx, 1000h
0x1801b5fdb  jz      short loc_1801B5FE8
0x1801b5fdd  mov     rax, [rsp+190h+var_118]
0x1801b5fe2  mov     [rax+1B8h], ecx
0x1801b5fe8  mov     rdi, [rsp+190h+var_118]
0x1801b5fed  lea     rcx, [rbp+90h+var_108]
0x1801b5ff1  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801b5ff6  mov     r8, rax; struct CCbsPublicUpdate **
0x1801b5ff9  mov     rdx, r12; struct CCbsSession *
0x1801b5ffc  mov     rcx, rdi; this
0x1801b5fff  call    ?CreatePublicInstance@CCbsUpdate@@QEAAJPEAVCCbsSession@@PEAPEAVCCbsPublicUpdate@@@Z; CCbsUpdate::CreatePublicInstance(CCbsSession *,CCbsPublicUpdate * *)
0x1801b6004  xor     r14d, r14d
0x1801b6007  mov     esi, eax
0x1801b6009  test    eax, eax
0x1801b600b  js      loc_1801B61DE
0x1801b6011  mov     rdx, [rbp+90h+var_108]
0x1801b6015  test    rdx, rdx
0x1801b6018  jnz     short loc_1801B601F
0x1801b601a  mov     edx, r14d
0x1801b601d  jmp     short loc_1801B602E
0x1801b601f  mov     rax, [rdx+8]
0x1801b6023  add     rdx, 8
  ... truncated ...
```
