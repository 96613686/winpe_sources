# CWin32Modem::GetModemInfo(CTapi32Api &,ulong,MethodContext *,CInstance *,ushort const *)

- ea: `0x18003dd50`
- end: `0x18003e40f`
- name: `?GetModemInfo@CWin32Modem@@AEAAHAEAVCTapi32Api@@KPEAVMethodContext@@PEAVCInstance@@PEBG@Z`
- size: `1727`
- prototype: `__int64 __fastcall(CWin32Modem *__hidden this, struct CTapi32Api *, unsigned int, struct MethodContext *, struct CInstance *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800e6fb0`
- `0x1800e7060`
- `0x1800e7680`

## callees

- `0x180008d20`
- `0x18000a360`
- `0x18000a970`
- `0x18000a9f0`
- `0x18000ab4c`
- `0x18000bc90`
- `0x18000cac0`
- `0x180014c58`
- `0x180015c80`
- `0x18001f954`
- `0x18003d7b0`
- `0x18003dd50`
- `0x180044170`
- `0x180075e88`
- `0x18007eefc`
- `0x1800e6218`
- `0x1800e641c`
- `0x1800e7110`
- `0x1800e7b18`
- `0x1800fc980`

## import_xrefs

- `msvcrt!iswdigit` at `0x18003df23`
- `msvcrt!iswdigit` at `0x18003df23`
- `msvcrt!_wtol` at `0x18003df43`
- `msvcrt!_wtol` at `0x18003df43`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003dde4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003dde4`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18003de6b`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18003de77`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18003de83`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18003de8f`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18003de6b`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18003de77`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18003de83`
- `framedynos!??0CHString@@QEAA@XZ` at `0x18003de8f`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x18003e042`
- `framedynos!?CompareNoCase@CHString@@QEBAHPEBG@Z` at `0x18003e042`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003df3a`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003e1e6`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003df3a`
- `framedynos!??BCHString@@QEBAPEBGXZ` at `0x18003e1e6`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18003e068`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18003e13e`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18003e068`
- `framedynos!?SetDWORD@CInstance@@QEAA_NPEBGK@Z` at `0x18003e13e`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18003e087`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18003e15d`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18003e17c`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18003e087`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18003e15d`
- `framedynos!?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z` at `0x18003e17c`
- `framedynos!?CreateNewInstance@Provider@@IEAAPEAVCInstance@@PEAVMethodContext@@@Z` at `0x18003e0f7`
- `framedynos!?CreateNewInstance@Provider@@IEAAPEAVCInstance@@PEAVMethodContext@@@Z` at `0x18003e0f7`
- `framedynos!?Commit@CInstance@@QEAAJXZ` at `0x18003e223`
- `framedynos!?Commit@CInstance@@QEAAJXZ` at `0x18003e223`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x18003deee`
- `framedynos!??4CHString@@QEAAAEBV0@AEBV0@@Z` at `0x18003deee`
- `framedynos!?Mid@CHString@@QEBA?AV1@H@Z` at `0x18003dedf`
- `framedynos!?Mid@CHString@@QEBA?AV1@H@Z` at `0x18003dedf`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x18003df07`
- `framedynos!?GetLength@CHString@@QEBAHXZ` at `0x18003df07`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x18003df74`
- `framedynos!?Format@CHString@@QEAAXPEBGZZ` at `0x18003df74`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18003dda1`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18003dfc5`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18003dfd3`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18003dda1`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18003dfc5`
- `framedynos!??0CRegistry@@QEAA@XZ` at `0x18003dfd3`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e0a4`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e0af`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e232`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e23d`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e29d`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e2a8`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e310`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e402`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e0a4`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e0af`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e232`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e23d`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e29d`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e2a8`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e310`
- `framedynos!??1CRegistry@@QEAA@XZ` at `0x18003e402`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18003dfed`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18003e010`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18003dfed`
- `framedynos!?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z` at `0x18003e010`
- `framedynos!??0CHPtrArray@@QEAA@XZ` at `0x18003ddb7`
- `framedynos!??0CHPtrArray@@QEAA@XZ` at `0x18003ddc6`
- `framedynos!??0CHPtrArray@@QEAA@XZ` at `0x18003ddb7`
- `framedynos!??0CHPtrArray@@QEAA@XZ` at `0x18003ddc6`
- `framedynos!??1CHPtrArray@@QEAA@XZ` at `0x18003e389`
- `framedynos!??1CHPtrArray@@QEAA@XZ` at `0x18003e389`
- `framedynos!?GetSize@CHPtrArray@@QEBAHXZ` at `0x18003de29`
- `framedynos!?GetSize@CHPtrArray@@QEBAHXZ` at `0x18003de29`
- `framedynos!?GetAt@CHPtrArray@@QEBAPEAXH@Z` at `0x18003de39`
- `framedynos!?GetAt@CHPtrArray@@QEBAPEAXH@Z` at `0x18003de39`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x18003e3a6`
- `framedynos!?Release@CInstance@@QEAAJXZ` at `0x18003e3a6`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18003e1f9`
- `framedynos!?SetCharSplat@CInstance@@QEAA_NPEBG0@Z` at `0x18003e1f9`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18003df51`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18003e1ca`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18003df51`
- `framedynos!?IsEmpty@CHString@@QEBAHXZ` at `0x18003e1ca`
- `framedynos!?Find@CHString@@QEBAHG@Z` at `0x18003decc`
- `framedynos!?Find@CHString@@QEBAHG@Z` at `0x18003decc`
- `framedynos!??ACHString@@QEBAGH@Z` at `0x18003df1a`
- `framedynos!??ACHString@@QEBAGH@Z` at `0x18003df1a`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003def9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e0bb`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e0c7`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e0d3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e0df`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e249`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e255`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e261`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e26d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e2b4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e2c0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e2cc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e2d8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e347`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e353`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e35f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e36b`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003def9`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e0bb`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e0c7`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e0d3`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e0df`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e249`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e255`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e261`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e26d`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e2b4`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e2c0`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e2cc`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e2d8`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e347`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e353`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e35f`
- `framedynos!??1CHString@@QEAA@XZ` at `0x18003e36b`
- `CFGMGR32!CM_Open_DevNode_Key_Ex` at `0x18003dfb3`
- `CFGMGR32!CM_Open_DevNode_Key_Ex` at `0x18003dfb3`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
_BOOL8 __fastcall CWin32Modem::GetModemInfo(
        CWin32Modem *this,
        struct CTapi32Api *a2,
        char a3,
        struct MethodContext *a4,
        struct CInstance *a5,
        const unsigned __int16 *a6)
{
  unsigned int v7; // r12d
  struct CInstance *NewInstance; // rdi
  HRESULT v9; // esi
  int v10; // r14d
  __int64 Next; // rbx
  volatile signed __int32 *v12; // rax
  const unsigned __int16 *v13; // rdx
  int v14; // eax
  __int64 v15; // rax
  unsigned int i; // r15d
  wint_t v17; // ax
  char v18; // r15
  const wchar_t *v19; // rax
  __int64 v20; // r8
  CInstance *v21; // rax
  CInstance *v22; // rax
  CWin32Modem *v23; // rcx
  struct CRegistry *v24; // r9
  CInstance *v25; // rax
  CInstance *v26; // rax
  CInstance *v27; // rax
  CWin32Modem *v28; // rcx
  CWin32Modem *v29; // rcx
  CInstance *v30; // rbx
  const unsigned __int16 *v31; // rax
  CInstance *v32; // rax
  struct CInstance *v34; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v35[8]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v36[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v37[8]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v38[8]; // [rsp+60h] [rbp-A0h] BYREF
  volatile signed __int32 *v39; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v40; // [rsp+70h] [rbp-90h]
  int v41; // [rsp+74h] [rbp-8Ch] BYREF
  int v42; // [rsp+78h] [rbp-88h]
  HKEY phkDevice; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v44[24]; // [rsp+88h] [rbp-78h] BYREF
  CWin32Modem *v45; // [rsp+A0h] [rbp-60h]
  _BYTE v46[8]; // [rsp+A8h] [rbp-58h] BYREF
  const unsigned __int16 *v47; // [rsp+B0h] [rbp-50h]
  struct MethodContext *v48; // [rsp+B8h] [rbp-48h]
  struct CTapi32Api *v49; // [rsp+C0h] [rbp-40h]
  _BYTE v50[24]; // [rsp+C8h] [rbp-38h] BYREF
  int v51; // [rsp+E0h] [rbp-20h]
  GUID pclsid; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v53[608]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v54[608]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v55[608]; // [rsp+5C0h] [rbp+4C0h] BYREF

  v48 = a4;
  v49 = a2;
  v45 = this;
  v47 = a6;
  CRegistry::CRegistry((CRegistry *)v55);
  v7 = 0;
  NewInstance = 0;
  v34 = 0;
  CHPtrArray::CHPtrArray((CHPtrArray *)v50);
  v51 = 0;
  CHPtrArray::CHPtrArray((CHPtrArray *)v44);
  v39 = 0;
  pclsid = 0;
  v9 = CLSIDFromString(L"{4D36E96D-E325-11CE-BFC1-08002BE10318}", &pclsid);
  if ( !v9
    && (unsigned int)CConfigManager::GetDeviceListFilterByClass(
                       (CConfigManager *)v50,
                       (struct CDeviceCollection *)v44,
                       &pclsid,
                       0,
                       0) )
  {
    v10 = 0;
    v40 = 0;
    Next = 0;
    v41 = 0;
    if ( CHPtrArray::GetSize((CHPtrArray *)v44) )
    {
      v12 = (volatile signed __int32 *)CHPtrArray::GetAt((CHPtrArray *)v44, 0);
      Next = (__int64)v12;
      if ( v12 )
        _InterlockedIncrement(v12 + 2);
    }
    v42 = a3 & 1;
    while ( 1 )
    {
      v39 = (volatile signed __int32 *)Next;
      if ( !Next )
      {
        if ( !v42 || v10 )
        {
          _com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>::~_com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>(&v39);
          CDeviceCollection::~CDeviceCollection((CDeviceCollection *)v44);
          CConfigManager::~CConfigManager((CConfigManager *)v50);
          _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v34);
          CRegistry::~CRegistry((CRegistry *)v55);
          return v9 >= 0;
        }
        goto LABEL_42;
      }
      CHString::CHString((CHString *)v38);
      CHString::CHString((CHString *)v37);
      CHString::CHString((CHString *)v36);
      CHString::CHString((CHString *)v35);
      CConfigMgrDevice::GetDeviceID((CConfigMgrDevice *)Next, (struct CHString *)v36);
      CConfigMgrDevice::GetRegStringProperty((CConfigMgrDevice *)Next, v13, (struct CHString *)v37);
      CConfigMgrDevice::GetStringProperty((CConfigMgrDevice *)Next, 0xAu, (struct CHString *)v38);
      v14 = CHString::Find((CHString *)v38, 0x5Cu);
      v15 = CHString::Mid(v38, v46, (unsigned int)(v14 + 1));
      CHString::operator=(v35, v15);
      CHString::~CHString((CHString *)v46);
      for ( i = 0; (signed int)i < CHString::GetLength((CHString *)v35); ++i )
      {
        v17 = CHString::operator[](v35, i);
        if ( !iswdigit(v17) )
        {
          v18 = 0;
          goto LABEL_14;
        }
      }
      v18 = 1;
      v19 = (const wchar_t *)CHString::operator unsigned short const *(v35);
      v7 = _wtol(v19);
LABEL_14:
      if ( CHString::IsEmpty((CHString *)v36) )
      {
        v20 = v40++;
        CHString::Format((CHString *)v36, L"Modem%d", v20);
      }
      phkDevice = 0;
      if ( CM_Open_DevNode_Key_Ex(*(_DWORD *)(Next + 68), 0x20019u, 0, 0, &phkDevice, 1u, 0) )
      {
        CHString::~CHString((CHString *)v35);
        CHString::~CHString((CHString *)v36);
        CHString::~CHString((CHString *)v37);
        CHString::~CHString((CHString *)v38);
        CRefPtrLite::Release((CRefPtrLite *)Next);
        TRefPtr<CConfigMgrDevice>::Empty(v44);
        CHPtrArray::~CHPtrArray((CHPtrArray *)v44);
        CConfigManager::~CConfigManager((CConfigManager *)v50);
        if ( NewInstance )
          CInstance::Release(NewInstance);
        goto LABEL_43;
      }
      CRegistry::CRegistry((CRegistry *)v53);
      CRegistry::CRegistry((CRegistry *)v54);
      if ( CRegistry::Open((CRegistry *)v53, phkDevice, 0, 0x20019u)
        || CRegistry::Open((CRegistry *)v54, phkDevice, L"Settings", 0x20019u) )
      {
        CRegistry::~CRegistry((CRegistry *)v54);
        CRegistry::~CRegistry((CRegistry *)v53);
        CHString::~CHString((CHString *)v35);
        CHString::~CHString((CHString *)v36);
        CHString::~CHString((CHString *)v37);
        CHString::~CHString((CHString *)v38);
        goto LABEL_42;
      }
      if ( (a3 & 1) != 0 )
        break;
      NewInstance = Provider::CreateNewInstance(v45, v48);
      _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v34);
      v34 = NewInstance;
      if ( NewInstance )
      {
        v10 = 1;
        if ( v18 )
        {
          v25 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v34);
          CInstance::SetDWORD(v25, L"Index", v7);
        }
        v26 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v34);
        CInstance::SetCHString(v26, L"IndexEx", (const struct CHString *)v35);
        v27 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v34);
        CInstance::SetCHString(v27, L"DeviceID", (const struct CHString *)v36);
LABEL_30:
        if ( ((a3 & 4) != 0
           || (v10 = CWin32Modem::NTSpecificRegistryValues(v23, NewInstance, (struct CRegistry *)v53, v24)) != 0)
          && (a3 & 4) == 0 )
        {
          CWin32Modem::AssignCommonFields(v45, NewInstance, (struct CRegistry *)v53, (struct CRegistry *)v54);
          CWin32Modem::AssignCfgMgrFields(v28, NewInstance, (struct CConfigMgrDevice *)Next);
          if ( !CHString::IsEmpty((CHString *)v37) )
          {
            v30 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v34);
            v31 = (const unsigned __int16 *)CHString::operator unsigned short const *(v37);
            CInstance::SetCharSplat(v30, L"AttachedTo", v31);
          }
          CWin32Modem::GetFieldsFromTAPI(v29, v49, NewInstance);
        }
        goto LABEL_36;
      }
      v10 = 0;
LABEL_36:
      if ( (a3 & 2) != 0 )
      {
        if ( v10 )
        {
          v32 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v34);
          v9 = CInstance::Commit(v32);
        }
      }
      CRegistry::~CRegistry((CRegistry *)v54);
      CRegistry::~CRegistry((CRegistry *)v53);
      CHString::~CHString((CHString *)v35);
      CHString::~CHString((CHString *)v36);
      CHString::~CHString((CHString *)v37);
      CHString::~CHString((CHString *)v38);
LABEL_40:
      Next = TRefPtr<CConfigMgrDevice>::GetNext(v44, &v41);
      _com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>::~_com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>(&v39);
      v7 = 0;
    }
    _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator=(&v34, a5);
    if ( CHString::CompareNoCase((CHString *)v36, v47) )
    {
      CRegistry::~CRegistry((CRegistry *)v54);
      CRegistry::~CRegistry((CRegistry *)v53);
      CHString::~CHString((CHString *)v35);
      CHString::~CHString((CHString *)v36);
      CHString::~CHString((CHString *)v37);
      CHString::~CHString((CHString *)v38);
      NewInstance = v34;
      goto LABEL_40;
    }
    if ( v18 )
    {
      v21 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v34);
      CInstance::SetDWORD(v21, L"Index", v7);
    }
    v22 = (CInstance *)_com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(&v34);
    CInstance::SetCHString(v22, L"IndexEx", (const struct CHString *)v35);
    v10 = 1;
    NewInstance = v34;
    goto LABEL_30;
  }
LABEL_42:
  _com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>::~_com_ptr_t<_com_IIID<CIRQDescriptor,&__s_GUID const _GUID_cb0e0537_d375_11d2_b35e_00104bc97924>>(&v39);
  CDeviceCollection::~CDeviceCollection((CDeviceCollection *)v44);
  CConfigManager::~CConfigManager((CConfigManager *)v50);
  _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(&v34);
LABEL_43:
  CRegistry::~CRegistry((CRegistry *)v55);
  return 0;
}

```

## disassembly

```asm
0x18003dd50  mov     [rsp-8+arg_10], rbx
0x18003dd55  push    rbp
0x18003dd56  push    rsi
0x18003dd57  push    rdi
0x18003dd58  push    r12
0x18003dd5a  push    r13
0x18003dd5c  push    r14
0x18003dd5e  push    r15
0x18003dd60  lea     rbp, [rsp-730h]
0x18003dd68  sub     rsp, 830h
0x18003dd6f  mov     rax, cs:__security_cookie
0x18003dd76  xor     rax, rsp
0x18003dd79  mov     [rbp+760h+var_40], rax
0x18003dd80  mov     [rbp+760h+var_7A8], r9
0x18003dd84  mov     r13d, r8d
0x18003dd87  mov     [rbp+760h+var_7A0], rdx
0x18003dd8b  mov     [rbp+760h+var_7C0], rcx
0x18003dd8f  mov     rax, [rbp+760h+arg_28]
0x18003dd96  mov     [rbp+760h+var_7B0], rax
0x18003dd9a  lea     rcx, [rbp+760h+var_2A0]
0x18003dda1  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x18003dda7  nop
0x18003dda8  xor     r12d, r12d
0x18003ddab  mov     edi, r12d
0x18003ddae  mov     [rsp+860h+var_820], r12
0x18003ddb3  lea     rcx, [rbp+760h+var_798]
0x18003ddb7  call    cs:__imp_??0CHPtrArray@@QEAA@XZ; CHPtrArray::CHPtrArray(void)
0x18003ddbd  nop
0x18003ddbe  mov     [rbp+760h+var_780], r12d
0x18003ddc2  lea     rcx, [rbp+760h+var_7D8]
0x18003ddc6  call    cs:__imp_??0CHPtrArray@@QEAA@XZ; CHPtrArray::CHPtrArray(void)
0x18003ddcc  nop
0x18003ddcd  mov     [rsp+860h+var_7F8], r12
0x18003ddd2  xorps   xmm0, xmm0
0x18003ddd5  movups  xmmword ptr [rbp+760h+pclsid.Data1], xmm0
0x18003ddd9  lea     rdx, [rbp+760h+pclsid]; pclsid
0x18003dddd  lea     rcx, sz; "{4D36E96D-E325-11CE-BFC1-08002BE10318}"
0x18003dde4  call    cs:__imp_CLSIDFromString
0x18003ddea  mov     esi, eax
0x18003ddec  test    eax, eax
0x18003ddee  jnz     loc_18003E2DF
0x18003ddf4  mov     dword ptr [rsp+860h+phkDevice], r12d; int
0x18003ddf9  xor     r9d, r9d; int
0x18003ddfc  lea     r8, [rbp+760h+pclsid]; struct _GUID *
0x18003de00  lea     rdx, [rbp+760h+var_7D8]; struct CDeviceCollection *
0x18003de04  lea     rcx, [rbp+760h+var_798]; this
0x18003de08  call    ?GetDeviceListFilterByClass@CConfigManager@@QEAAHAEAVCDeviceCollection@@PEBU_GUID@@HH@Z; CConfigManager::GetDeviceListFilterByClass(CDeviceCollection &,_GUID const *,int,int)
0x18003de0d  test    eax, eax
0x18003de0f  jz      loc_18003E2DF
0x18003de15  mov     r14d, r12d
0x18003de18  mov     [rsp+860h+var_7F0], r12d
0x18003de1d  mov     ebx, r12d
0x18003de20  mov     [rsp+860h+var_7EC], r12d
0x18003de25  lea     rcx, [rbp+760h+var_7D8]
0x18003de29  call    cs:__imp_?GetSize@CHPtrArray@@QEBAHXZ; CHPtrArray::GetSize(void)
0x18003de2f  test    eax, eax
0x18003de31  jz      short loc_18003DE4B
0x18003de33  xor     edx, edx
0x18003de35  lea     rcx, [rbp+760h+var_7D8]
0x18003de39  call    cs:__imp_?GetAt@CHPtrArray@@QEBAPEAXH@Z; CHPtrArray::GetAt(int)
0x18003de3f  mov     rbx, rax
0x18003de42  test    rax, rax
0x18003de45  jz      short loc_18003DE4B
0x18003de47  lock inc dword ptr [rax+8]
0x18003de4b  mov     ecx, r13d
0x18003de4e  and     ecx, 1
0x18003de51  mov     [rsp+860h+var_7E8], ecx
0x18003de55  mov     rax, rbx
0x18003de58  mov     [rsp+860h+var_7F8], rbx
0x18003de5d  test    rax, rax
0x18003de60  jz      loc_18003E3BC
0x18003de66  lea     rcx, [rsp+860h+var_800]
0x18003de6b  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18003de71  nop
0x18003de72  lea     rcx, [rsp+860h+var_808]
0x18003de77  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18003de7d  nop
0x18003de7e  lea     rcx, [rsp+860h+var_810]
0x18003de83  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18003de89  nop
0x18003de8a  lea     rcx, [rsp+860h+var_818]
0x18003de8f  call    cs:__imp_??0CHString@@QEAA@XZ; CHString::CHString(void)
0x18003de95  nop
0x18003de96  lea     rdx, [rsp+860h+var_810]; struct CHString *
0x18003de9b  mov     rcx, rbx; this
0x18003de9e  call    ?GetDeviceID@CConfigMgrDevice@@QEAAHAEAVCHString@@@Z; CConfigMgrDevice::GetDeviceID(CHString &)
0x18003dea3  lea     r8, [rsp+860h+var_808]; struct CHString *
0x18003dea8  mov     rcx, rbx; this
0x18003deab  call    ?GetRegStringProperty@CConfigMgrDevice@@QEAAHPEBGAEAVCHString@@@Z; CConfigMgrDevice::GetRegStringProperty(ushort const *,CHString &)
0x18003deb0  lea     r8, [rsp+860h+var_800]; struct CHString *
0x18003deb5  mov     edx, 0Ah; unsigned int
0x18003deba  mov     rcx, rbx; this
0x18003debd  call    ?GetStringProperty@CConfigMgrDevice@@QEAAHKAEAVCHString@@@Z; CConfigMgrDevice::GetStringProperty(ulong,CHString &)
0x18003dec2  mov     edx, 5Ch ; '\'
0x18003dec7  lea     rcx, [rsp+860h+var_800]
0x18003decc  call    cs:__imp_?Find@CHString@@QEBAHG@Z; CHString::Find(ushort)
0x18003ded2  lea     r8d, [rax+1]
0x18003ded6  lea     rdx, [rbp+760h+var_7B8]
0x18003deda  lea     rcx, [rsp+860h+var_800]
0x18003dedf  call    cs:__imp_?Mid@CHString@@QEBA?AV1@H@Z; CHString::Mid(int)
0x18003dee5  nop
0x18003dee6  mov     rdx, rax
0x18003dee9  lea     rcx, [rsp+860h+var_818]
0x18003deee  call    cs:__imp_??4CHString@@QEAAAEBV0@AEBV0@@Z; CHString::operator=(CHString const &)
0x18003def4  nop
0x18003def5  lea     rcx, [rbp+760h+var_7B8]
0x18003def9  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18003deff  mov     r15d, r12d
0x18003df02  lea     rcx, [rsp+860h+var_818]
0x18003df07  call    cs:__imp_?GetLength@CHString@@QEBAHXZ; CHString::GetLength(void)
0x18003df0d  lea     rcx, [rsp+860h+var_818]
0x18003df12  cmp     r15d, eax
0x18003df15  jge     short loc_18003DF37
0x18003df17  mov     edx, r15d
0x18003df1a  call    cs:__imp_??ACHString@@QEBAGH@Z; CHString::operator[](int)
0x18003df20  movzx   ecx, ax; C
0x18003df23  call    cs:__imp_iswdigit
0x18003df29  test    eax, eax
0x18003df2b  jz      short loc_18003DF32
0x18003df2d  inc     r15d
0x18003df30  jmp     short loc_18003DF02
0x18003df32  xor     r15b, r15b
0x18003df35  jmp     short loc_18003DF4C
0x18003df37  mov     r15b, 1
0x18003df3a  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18003df40  mov     rcx, rax; String
0x18003df43  call    cs:__imp__wtol
0x18003df49  mov     r12d, eax
0x18003df4c  lea     rcx, [rsp+860h+var_810]
0x18003df51  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x18003df57  test    eax, eax
0x18003df59  jz      short loc_18003DF7A
0x18003df5b  mov     eax, [rsp+860h+var_7F0]
0x18003df5f  mov     r8d, eax
0x18003df62  inc     eax
0x18003df64  mov     [rsp+860h+var_7F0], eax
0x18003df68  lea     rdx, aModemD; "Modem%d"
0x18003df6f  lea     rcx, [rsp+860h+var_810]
0x18003df74  call    cs:__imp_?Format@CHString@@QEAAXPEBGZZ; CHString::Format(ushort const *,...)
0x18003df7a  mov     [rbp+760h+var_7E0], 0
0x18003df82  test    rbx, rbx
0x18003df85  jz      loc_18003E3B1
0x18003df8b  mov     [rsp+860h+hMachine], 0; hMachine
0x18003df94  mov     [rsp+860h+ulFlags], 1; ulFlags
0x18003df9c  lea     rax, [rbp+760h+var_7E0]
0x18003dfa0  mov     [rsp+860h+phkDevice], rax; phkDevice
0x18003dfa5  xor     r9d, r9d; Disposition
0x18003dfa8  xor     r8d, r8d; ulHardwareProfile
0x18003dfab  mov     edx, 20019h; samDesired
0x18003dfb0  mov     ecx, [rbx+44h]; dnDevNode
0x18003dfb3  call    cs:__imp_CM_Open_DevNode_Key_Ex
0x18003dfb9  test    eax, eax
0x18003dfbb  jnz     loc_18003E342
0x18003dfc1  lea     rcx, [rbp+760h+var_760]
0x18003dfc5  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x18003dfcb  nop
0x18003dfcc  lea     rcx, [rbp+760h+var_500]
0x18003dfd3  call    cs:__imp_??0CRegistry@@QEAA@XZ; CRegistry::CRegistry(void)
0x18003dfd9  nop
0x18003dfda  mov     edi, 20019h
0x18003dfdf  mov     r9d, edi
0x18003dfe2  xor     r8d, r8d
0x18003dfe5  mov     rdx, [rbp+760h+var_7E0]
0x18003dfe9  lea     rcx, [rbp+760h+var_760]
0x18003dfed  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x18003dff3  test    eax, eax
0x18003dff5  jnz     loc_18003E296
0x18003dffb  mov     r9d, edi
0x18003dffe  lea     r8, aSettings; "Settings"
0x18003e005  mov     rdx, [rbp+760h+var_7E0]
0x18003e009  lea     rcx, [rbp+760h+var_500]
0x18003e010  call    cs:__imp_?Open@CRegistry@@QEAAJPEAUHKEY__@@PEBGK@Z; CRegistry::Open(HKEY__ *,ushort const *,ulong)
0x18003e016  test    eax, eax
0x18003e018  jnz     loc_18003E296
0x18003e01e  test    r13b, 1
0x18003e022  jz      loc_18003E0EF
0x18003e028  mov     rdx, [rbp+760h+arg_20]
0x18003e02f  lea     rcx, [rsp+860h+var_820]
0x18003e034  call    ??4?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEAAAEAV0@PEAVCInstance@@@Z; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator=(CInstance *)
0x18003e039  mov     rdx, [rbp+760h+var_7B0]
0x18003e03d  lea     rcx, [rsp+860h+var_810]
0x18003e042  call    cs:__imp_?CompareNoCase@CHString@@QEBAHPEBG@Z; CHString::CompareNoCase(ushort const *)
0x18003e048  test    eax, eax
0x18003e04a  jnz     short loc_18003E09D
0x18003e04c  test    r15b, r15b
0x18003e04f  jz      short loc_18003E06E
0x18003e051  lea     rcx, [rsp+860h+var_820]
0x18003e056  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x18003e05b  mov     r8d, r12d
0x18003e05e  lea     rdx, aIndex; "Index"
0x18003e065  mov     rcx, rax
0x18003e068  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18003e06e  lea     rcx, [rsp+860h+var_820]
0x18003e073  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x18003e078  lea     r8, [rsp+860h+var_818]
0x18003e07d  lea     rdx, aIndexex; "IndexEx"
0x18003e084  mov     rcx, rax
0x18003e087  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x18003e08d  mov     r14d, 1
0x18003e093  mov     rdi, [rsp+860h+var_820]
0x18003e098  jmp     loc_18003E182
0x18003e09d  lea     rcx, [rbp+760h+var_500]
0x18003e0a4  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18003e0aa  nop
0x18003e0ab  lea     rcx, [rbp+760h+var_760]
0x18003e0af  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18003e0b5  nop
0x18003e0b6  lea     rcx, [rsp+860h+var_818]
0x18003e0bb  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18003e0c1  nop
0x18003e0c2  lea     rcx, [rsp+860h+var_810]
0x18003e0c7  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18003e0cd  nop
0x18003e0ce  lea     rcx, [rsp+860h+var_808]
0x18003e0d3  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18003e0d9  nop
0x18003e0da  lea     rcx, [rsp+860h+var_800]
0x18003e0df  call    cs:__imp_??1CHString@@QEAA@XZ; CHString::~CHString(void)
0x18003e0e5  mov     rdi, [rsp+860h+var_820]
0x18003e0ea  jmp     loc_18003E273
0x18003e0ef  mov     rdx, [rbp+760h+var_7A8]
0x18003e0f3  mov     rcx, [rbp+760h+var_7C0]
0x18003e0f7  call    cs:__imp_?CreateNewInstance@Provider@@IEAAPEAVCInstance@@PEAVMethodContext@@@Z; Provider::CreateNewInstance(MethodContext *)
0x18003e0fd  mov     rdi, rax
0x18003e100  lea     rcx, [rsp+860h+var_820]
0x18003e105  call    ?_Release@?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::_Release(void)
0x18003e10a  mov     [rsp+860h+var_820], rdi
0x18003e10f  test    rdi, rdi
0x18003e112  jnz     short loc_18003E11C
0x18003e114  xor     r14d, r14d
0x18003e117  jmp     loc_18003E20B
0x18003e11c  mov     r14d, 1
0x18003e122  test    r15b, r15b
0x18003e125  jz      short loc_18003E144
0x18003e127  lea     rcx, [rsp+860h+var_820]
0x18003e12c  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x18003e131  mov     r8d, r12d
0x18003e134  lea     rdx, aIndex; "Index"
0x18003e13b  mov     rcx, rax
0x18003e13e  call    cs:__imp_?SetDWORD@CInstance@@QEAA_NPEBGK@Z; CInstance::SetDWORD(ushort const *,ulong)
0x18003e144  lea     rcx, [rsp+860h+var_820]
0x18003e149  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x18003e14e  lea     r8, [rsp+860h+var_818]
0x18003e153  lea     rdx, aIndexex; "IndexEx"
0x18003e15a  mov     rcx, rax
0x18003e15d  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x18003e163  lea     rcx, [rsp+860h+var_820]
0x18003e168  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x18003e16d  lea     r8, [rsp+860h+var_810]
0x18003e172  lea     rdx, aDeviceid; "DeviceID"
0x18003e179  mov     rcx, rax
0x18003e17c  call    cs:__imp_?SetCHString@CInstance@@QEAA_NPEBGAEBVCHString@@@Z; CInstance::SetCHString(ushort const *,CHString const &)
0x18003e182  mov     r15d, r13d
0x18003e185  and     r15d, 4
0x18003e189  jnz     short loc_18003E19E
0x18003e18b  lea     r8, [rbp+760h+var_760]; struct CRegistry *
0x18003e18f  mov     rdx, rdi; struct CInstance *
0x18003e192  call    ?NTSpecificRegistryValues@CWin32Modem@@AEAAHPEAVCInstance@@PEAVCRegistry@@1@Z; CWin32Modem::NTSpecificRegistryValues(CInstance *,CRegistry *,CRegistry *)
0x18003e197  mov     r14d, eax
0x18003e19a  test    eax, eax
0x18003e19c  jz      short loc_18003E20B
0x18003e19e  test    r15d, r15d
0x18003e1a1  jnz     short loc_18003E20B
0x18003e1a3  lea     r9, [rbp+760h+var_500]; struct CRegistry *
0x18003e1aa  lea     r8, [rbp+760h+var_760]; struct CRegistry *
0x18003e1ae  mov     rdx, rdi; struct CInstance *
0x18003e1b1  mov     rcx, [rbp+760h+var_7C0]; this
0x18003e1b5  call    ?AssignCommonFields@CWin32Modem@@AEAAHPEAVCInstance@@PEAVCRegistry@@1@Z; CWin32Modem::AssignCommonFields(CInstance *,CRegistry *,CRegistry *)
0x18003e1ba  mov     r8, rbx; struct CConfigMgrDevice *
0x18003e1bd  mov     rdx, rdi; struct CInstance *
0x18003e1c0  call    ?AssignCfgMgrFields@CWin32Modem@@AEAAHPEAVCInstance@@PEAVCConfigMgrDevice@@@Z; CWin32Modem::AssignCfgMgrFields(CInstance *,CConfigMgrDevice *)
0x18003e1c5  lea     rcx, [rsp+860h+var_808]
0x18003e1ca  call    cs:__imp_?IsEmpty@CHString@@QEBAHXZ; CHString::IsEmpty(void)
0x18003e1d0  test    eax, eax
0x18003e1d2  jnz     short loc_18003E1FF
0x18003e1d4  lea     rcx, [rsp+860h+var_820]
0x18003e1d9  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x18003e1de  mov     rbx, rax
0x18003e1e1  lea     rcx, [rsp+860h+var_808]
0x18003e1e6  call    cs:__imp_??BCHString@@QEBAPEBGXZ; CHString::operator ushort const *(void)
0x18003e1ec  mov     r8, rax
0x18003e1ef  lea     rdx, aAttachedto; "AttachedTo"
0x18003e1f6  mov     rcx, rbx
0x18003e1f9  call    cs:__imp_?SetCharSplat@CInstance@@QEAA_NPEBG0@Z; CInstance::SetCharSplat(ushort const *,ushort const *)
0x18003e1ff  mov     r8, rdi; struct CInstance *
0x18003e202  mov     rdx, [rbp+760h+var_7A0]; struct CTapi32Api *
0x18003e206  call    ?GetFieldsFromTAPI@CWin32Modem@@AEAAHAEAVCTapi32Api@@PEAVCInstance@@@Z; CWin32Modem::GetFieldsFromTAPI(CTapi32Api &,CInstance *)
0x18003e20b  test    r13b, 2
0x18003e20f  jz      short loc_18003E22B
0x18003e211  test    r14d, r14d
0x18003e214  jz      short loc_18003E22B
0x18003e216  lea     rcx, [rsp+860h+var_820]
0x18003e21b  call    ??C?$_com_ptr_t@V?$_com_IIID@VCInstance@@$1?_GUID_3402945e_d19a_11d2_b35e_00104bc97924@@3U__s_GUID@@B@@@@QEBAPEAVCInstance@@XZ; _com_ptr_t<_com_IIID<CInstance,&__s_GUID const _GUID_3402945e_d19a_11d2_b35e_00104bc97924>>::operator->(void)
0x18003e220  mov     rcx, rax
0x18003e223  call    cs:__imp_?Commit@CInstance@@QEAAJXZ; CInstance::Commit(void)
0x18003e229  mov     esi, eax
0x18003e22b  lea     rcx, [rbp+760h+var_500]
0x18003e232  call    cs:__imp_??1CRegistry@@QEAA@XZ; CRegistry::~CRegistry(void)
0x18003e238  nop
0x18003e239  lea     rcx, [rbp+760h+var_760]
  ... truncated ...
```
