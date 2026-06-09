# Jot::CBackupSectionAsync::OnPoll(uint *)

- ea: `0x18082e860`
- end: `0x18082f45d`
- name: `?OnPoll@CBackupSectionAsync@Jot@@UEAAXPEAI@Z`
- size: `3069`
- prototype: `void __fastcall(Jot::CBackupSectionAsync *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `42`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180032260`
- `0x18005d070`
- `0x18006bb90`
- `0x180074020`
- `0x18007ca50`
- `0x18007cdf0`
- `0x180090190`
- `0x180090cb0`
- `0x180092e24`
- `0x18009342c`
- `0x180093480`
- `0x1800943d4`
- `0x180094630`
- `0x1800cb9f0`
- `0x18014da54`
- `0x18014eb00`
- `0x1801ac5c0`
- `0x1801ac8e0`
- `0x1801aca20`
- `0x1801ad930`
- `0x1801af210`
- `0x1801af2f8`
- `0x1801c4c50`
- `0x1801c5b50`
- `0x1801ee3ac`
- `0x1801efea0`
- `0x1802536c0`
- `0x1802ad2b0`
- `0x1802e2190`
- `0x1802e3f10`
- `0x1802e5170`
- `0x1802e5190`
- `0x1803881c4`
- `0x1804af7e8`
- `0x1806ca680`
- `0x18072ef78`
- `0x1807d927c`
- `0x1807d9364`
- `0x18082e860`
- `0x18082f460`
- `0x1808a2d04`
- `0x1808e0364`

## import_xrefs

- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18082ea3c`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x18082ea3c`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18082e913`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18082e9e7`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18082ea12`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18082ea47`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18082ebea`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18082e913`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18082e9e7`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18082ea12`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18082ea47`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x18082ebea`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18082e8da`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18082e9c5`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18082e8da`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18082e9c5`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18082eb98`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18082eb98`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18082e94d`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18082eb7b`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18082e94d`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18082eb7b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18082ef0b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18082f037`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18082f3dc`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18082ef0b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18082f037`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18082f3dc`

## pseudocode

```c
void __fastcall Jot::CBackupSectionAsync::OnPoll(Jot::CBackupSectionAsync *this, unsigned int *a2)
{
  void (__fastcall *v4)(Jot::CBackupSectionAsync *, __int128 *); // rbx
  __int64 v5; // rcx
  const void *v6; // rax
  void (__fastcall *v7)(Jot::CBackupSectionAsync *, __int128 *); // rbx
  const void *v8; // rax
  __int64 v9; // rdx
  void (__fastcall *v10)(Jot::CBackupSectionAsync *, __int64); // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  const void *v14; // rax
  bool v15; // al
  __int64 v16; // rcx
  __int64 v17; // rcx
  const void *v18; // rax
  const void *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // rsi
  void (__fastcall *v25)(__int64, __int64, _QWORD, __int64, char, _QWORD, _DWORD, _BYTE, _DWORD); // rdi
  __int64 v26; // rbx
  _QWORD *v27; // rax
  void (__fastcall *v28)(Jot::CBackupSectionAsync *, __int128 *); // rbx
  Jot::CReplicatorConnector *v29; // rcx
  const void *v30; // rax
  __int64 v31; // rax
  _QWORD *v32; // rsi
  unsigned __int64 v33; // rdx
  unsigned int v34; // r8d
  void (__fastcall ***v35)(_QWORD, GUID *, void **); // rcx
  void (__fastcall *v36)(_QWORD, GUID *, void **); // rax
  void (__fastcall *v37)(Jot::CBackupSectionAsync *, __int64); // rbx
  __int64 v38; // rax
  __int64 v39; // rax
  _QWORD *v40; // rax
  _QWORD *v41; // r12
  void (__fastcall *v42)(void *, GUID *, MsoCF::IPropertySet **); // rax
  __int64 v43; // rax
  __int64 v44; // rbx
  void (__fastcall *v45)(Jot::CBackupSectionAsync *, __int64); // rbx
  __int64 v46; // rax
  void *v47; // rdx
  void *v48; // rcx
  __int64 *v49; // rax
  __int64 v50; // r13
  void (__fastcall *v51)(Jot::CBackupSectionAsync *, __int128 *); // rdi
  void *v52; // rdx
  __int64 v53; // rax
  __int64 Filename; // rax
  unsigned __int8 v55; // dl
  Jot::VersionEditor *v56; // rcx
  const struct Jot::FileFormatDescriptor *FfdFromVersion; // rdi
  __int64 v58; // rax
  __int64 v59; // rax
  __int64 EnterpriseIdentity; // rax
  void *v61; // rax
  int v62; // r8d
  unsigned int v63; // esi
  __int64 v64; // rdi
  __int64 v65; // rax
  void *v66; // rsi
  __int64 v67; // rcx
  __int64 v68; // rax
  __int64 v69; // r8
  __int64 v70; // rax
  void (__fastcall *v71)(Jot::CBackupSectionAsync *, __int64); // rbx
  __int64 v72; // rax
  _BYTE v73[8]; // [rsp+60h] [rbp-148h] BYREF
  __int128 v74; // [rsp+68h] [rbp-140h] BYREF
  __int128 v75; // [rsp+78h] [rbp-130h] BYREF
  void *v76; // [rsp+88h] [rbp-120h] BYREF
  Jot::CBackupSectionAsync::CurrentSectionBackup *v77; // [rsp+90h] [rbp-118h] BYREF
  MsoCF::IPropertySet *v78; // [rsp+98h] [rbp-110h] BYREF
  int v79[2]; // [rsp+A0h] [rbp-108h] BYREF
  __int64 v80; // [rsp+B0h] [rbp-F8h] BYREF
  __int64 v81; // [rsp+B8h] [rbp-F0h] BYREF
  _QWORD v82[3]; // [rsp+C0h] [rbp-E8h] BYREF
  char v83; // [rsp+D8h] [rbp-D0h]
  __int16 v84; // [rsp+100h] [rbp-A8h]
  char v85; // [rsp+102h] [rbp-A6h]
  int v86; // [rsp+10Ch] [rbp-9Ch]
  __int64 v87; // [rsp+118h] [rbp-90h]
  _BYTE v88[32]; // [rsp+130h] [rbp-78h] BYREF
  _BYTE v89[32]; // [rsp+150h] [rbp-58h] BYREF

  *(_QWORD *)v79 = this;
  if ( *a2 == 10 )
  {
    v32 = (_QWORD *)((char *)this + 400);
    if ( !(unsigned __int8)Jot::CNodeRef<Jot::CSemNotebookTrait>::IsValid((char *)this + 400)
      || !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v32 + 168LL))(*v32) )
    {
      v71 = *(void (__fastcall **)(Jot::CBackupSectionAsync *, __int64))(*(_QWORD *)this + 96LL);
      Jot::ExceptionWithErrorCode::ExceptionWithErrorCode(v82, 17040982);
      v82[0] = &Jot::ErrBackupSection_SectionNotValid::`vftable';
      v72 = std::make_exception_ptr<Jot::ErrBackupSection_SectionNotValid>(&v74, v82);
      v71(this, v72);
      return;
    }
    v35 = (void (__fastcall ***)(_QWORD, GUID *, void **))*v32;
    v76 = 0;
    if ( v35 )
    {
      v36 = **v35;
      if ( (char *)v36 == (char *)MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface )
        MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(
          v35,
          &GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b,
          &v76);
      else
        v36(v35, &GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b, &v76);
    }
    if ( !v76 )
    {
      v37 = *(void (__fastcall **)(Jot::CBackupSectionAsync *, __int64))(*(_QWORD *)this + 96LL);
      v38 = Jot::ErrUnknownInternalError::ErrUnknownInternalError(v82, 17040983);
      v39 = std::make_exception_ptr<Jot::ErrUnknownInternalError>(&v74, v38);
      v37(this, v39);
LABEL_45:
      if ( v76 )
      {
        if ( *(__int64 (__fastcall **)(void *))(*(_QWORD *)v76 + 16LL) == MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::Release )
          MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::Release(v76);
        else
          (*(void (**)(void))(*(_QWORD *)v76 + 16LL))();
      }
      return;
    }
    v40 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x70, v33, v34);
    v41 = v40;
    *(_QWORD *)&v74 = v40;
    if ( v40 )
    {
      *v40 = 0;
      v40[1] = 0;
      v40[2] = 0;
      v40[3] = 0;
      v40[4] = 0;
      v40[5] = 0;
      v40[6] = 0;
      v40[7] = 0;
      *((_OWORD *)v40 + 4) = 0;
      v40[10] = 0;
      v40[11] = 7;
      *((_WORD *)v40 + 32) = 0;
      v40[12] = 0;
      *((_DWORD *)v40 + 26) = 0;
    }
    else
    {
      v41 = 0;
    }
    v77 = (Jot::CBackupSectionAsync::CurrentSectionBackup *)v41;
    *(_QWORD *)&v74 = v41;
    v78 = 0;
    if ( v76 )
    {
      v42 = **(void (__fastcall ***)(void *, GUID *, MsoCF::IPropertySet **))v76;
      if ( (char *)v42 == (char *)MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface )
        MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface(
          v76,
          &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75,
          &v78);
      else
        v42(v76, &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75, &v78);
    }
    MsoCF::IPropertySet::GetProperty(
      v78,
      (const struct MsoCF::PropertyInfo *)Jot::PropertySpace_Jot11::priCountOfDeepRevisionChanges,
      (struct MsoCF::CPropertyValue *)(v41 + 12));
    v81 = 0;
    v80 = 0;
    v43 = Jot::CNodeRef<Jot::CSemPageContentTrait>::CNodeRef<Jot::CSemPageContentTrait>(&v75, (char *)this + 400);
    Jot::CBackupSectionAsync::FindInProgressBackupFileForSection(this, v43, &v81);
    v44 = v81;
    if ( v81 )
    {
      v49 = (__int64 *)(*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v81 + 32LL))(v81, &v75, 0);
      v50 = *v49;
      *v49 = 0;
      v80 = v50;
      if ( (_QWORD)v75 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v75 + 8LL))(v75);
      if ( v50 )
      {
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(v41 + 7, v44);
        v53 = Jot::CNodeRef<Jot::CSemPageContentTrait>::CNodeRef<Jot::CSemPageContentTrait>(&v75, (char *)this + 400);
        Filename = Jot::SectionEditor::GetFilename(v89, v53);
        std::wstring::operator=(v41 + 8, Filename);
        std::wstring::~wstring(v89);
        Jot::RemoveInvalidFilenameCharacters(v41 + 8, 0);
        v73[0] = 0;
        if ( !(unsigned __int8)MsoCF::Properties::Raw<Jot::PropertySpace_Jot14::prtidPrimaryStorageIsCellStorage>::FGet(
                                 *v32,
                                 v73)
          || v73[0] != 1 )
        {
          sub_1800CB9F0((char *)this + 400);
        }
        Jot::CStoreOnJotStorageFactory::CStoreOnJotStorageFactory((Jot::CStoreOnJotStorageFactory *)v82);
        LOBYTE(v56) = v55;
        FfdFromVersion = Jot::VersionEditor::GetFfdFromVersion(v56, v55);
        MsoCF::CIPtr<Jot::IJotStorage_Core,Jot::IJotStorage_Core>::Assign(v82, v50);
        v82[1] = FfdFromVersion;
        v82[2] = FfdFromVersion;
        v83 = 1;
        v87 = 0;
        v84 = 256;
        v86 = 0;
        v85 = 1;
        v58 = Jot::CStoreOnJotStorageFactory::Create(v82, &v75);
        MsoCF::CIPtr<Jot::IServerStore,Jot::IServerStore>::operator=<Jot::IObjectSpaceStoreOnCellStorage,Jot::IObjectSpaceStoreOnCellStorage>(
          v41 + 3,
          v58);
        if ( (_QWORD)v75 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v75 + 8LL))(v75);
        v59 = Jot::CNodeRef<Jot::CSemPageContentTrait>::CNodeRef<Jot::CSemPageContentTrait>(&v75, (char *)this + 400);
        EnterpriseIdentity = Jot::EDP::GetEnterpriseIdentity(v89, v59);
        v61 = (void *)Jot::EDP::Identity::Identity(v88, EnterpriseIdentity);
        LOBYTE(v62) = 1;
        Jot::CreateNativeReplicator((int)v79, v41[3], v62, 0, 1, 0, 0, 0, 1, 0, v61);
        v63 = *((_DWORD *)this + 284);
        v64 = *(_QWORD *)v79;
        v65 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v79 + 24LL))(*(_QWORD *)v79);
        MsoCF::CIPtr<Jot::IXPSDocument,Jot::IXPSDocument>::CIPtr<Jot::IXPSDocument,Jot::IXPSDocument>(&v77, v65);
        Jot::CReplicatorConnector::Connect(v41, v76, &v77, v63);
        v66 = v76;
        if ( v76 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v76 + 8LL))(v76);
        v67 = v41[2];
        v41[2] = v66;
        MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(v67);
        v68 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v64 + 24LL))(v64);
        LOBYTE(v69) = 1;
        v70 = (*(__int64 (__fastcall **)(__int64, Jot::CBackupSectionAsync::CurrentSectionBackup **, __int64))(*(_QWORD *)v68 + 88LL))(
                v68,
                &v77,
                v69);
        Mso::TCntPtr<Mso::Async::IDispatchQueue>::operator=(v41 + 4, v70);
        if ( v77 )
          (*(void (__fastcall **)(Jot::CBackupSectionAsync::CurrentSectionBackup *))(*(_QWORD *)v77 + 16LL))(v77);
        *(_QWORD *)&v74 = 0;
        MsoCF::COwnerPtr<Jot::CBackupSectionAsync::CurrentSectionBackup,MsoCF::COwnerPtr_Delete_Auto<Jot::CBackupSectionAsync::CurrentSectionBackup>>::Attach(
          (char *)this + 1232,
          v41);
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(
          (char *)this + 376,
          *(_QWORD *)(*((_QWORD *)this + 154) + 32LL));
        *((_DWORD *)this + 96) = 11;
        *((_DWORD *)this + 97) = 11;
        *((_DWORD *)this + 93) = 3;
        if ( v64 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
        Jot::CStoreOnJotStorageFactory::~CStoreOnJotStorageFactory((Jot::CStoreOnJotStorageFactory *)v82);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 8LL))(v50);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        if ( v78 )
          (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v78 + 16LL))(v78);
        goto LABEL_45;
      }
      v51 = *(void (__fastcall **)(Jot::CBackupSectionAsync *, __int128 *))(*(_QWORD *)this + 96LL);
      Jot::ExceptionWithErrorCode::ExceptionWithErrorCode(v82, 17040985);
      v82[0] = &Jot::ErrBackupSection_CouldNotCreateStorage::`vftable';
      std::exception_ptr::_Copy_exception(&v75, v82, &TI3_AUErrBackupSection_CouldNotCreateStorage_Jot__);
      v82[0] = &Jot::ErrStorageUrl::`vftable';
      Jot::Exception::~Exception((Jot::Exception *)v82);
      v51(this, &v75);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      if ( v78 )
        (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v78 + 16LL))(v78);
      if ( v41 )
      {
        Jot::CBackupSectionAsync::CurrentSectionBackup::~CurrentSectionBackup((Jot::CBackupSectionAsync::CurrentSectionBackup *)v41);
        Mso::Memory::Free((Mso::Memory *)v41, v52);
      }
      v48 = v76;
      if ( !v76 )
        return;
      if ( *(__int64 (__fastcall **)(void *))(*(_QWORD *)v76 + 16LL) != MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::Release )
      {
        (*(void (**)(void))(*(_QWORD *)v76 + 16LL))();
        return;
      }
    }
    else
    {
      v45 = *(void (__fastcall **)(Jot::CBackupSectionAsync *, __int64))(*(_QWORD *)this + 96LL);
      Jot::ExceptionWithErrorCode::ExceptionWithErrorCode(v82, 17040984);
      v82[0] = &Jot::ErrBackupSection_SectionNotValid::`vftable';
      v46 = std::make_exception_ptr<Jot::ErrBackupSection_SectionNotValid>(&v75, v82);
      v45(this, v46);
      if ( v78 )
        (*(void (__fastcall **)(MsoCF::IPropertySet *))(*(_QWORD *)v78 + 16LL))(v78);
      if ( v41 )
      {
        Jot::CBackupSectionAsync::CurrentSectionBackup::~CurrentSectionBackup((Jot::CBackupSectionAsync::CurrentSectionBackup *)v41);
        Mso::Memory::Free((Mso::Memory *)v41, v47);
      }
      v48 = v76;
      if ( !v76 )
        return;
      if ( *(__int64 (__fastcall **)(void *))(*(_QWORD *)v76 + 16LL) != MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::Release )
      {
        (*(void (**)(void))(*(_QWORD *)v76 + 16LL))();
        return;
      }
    }
    MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::Release(v48);
    return;
  }
  if ( *a2 != 11 )
  {
    if ( *a2 != 12 )
    {
      if ( *a2 != 13 )
      {
        if ( *a2 == 14 )
        {
          v4 = *(void (__fastcall **)(Jot::CBackupSectionAsync *, __int128 *))(*(_QWORD *)this + 96LL);
          v74 = 0;
          __ExceptionPtrCreate(&v74);
          v4(this, &v74);
        }
        return;
      }
      v5 = *((_QWORD *)this + 154);
      if ( v5 && *(_QWORD *)(v5 + 32) )
      {
        v6 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 48) + 80LL))(*(_QWORD *)(v5 + 48));
        if ( __ExceptionPtrToBool(v6) )
        {
          v7 = *(void (__fastcall **)(Jot::CBackupSectionAsync *, __int128 *))(*(_QWORD *)this + 96LL);
          v8 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 154) + 48LL) + 80LL))(*(_QWORD *)(*((_QWORD *)this + 154) + 48LL));
          v74 = 0;
          __ExceptionPtrCopy(&v74, v8);
          v7(this, &v74);
        }
        *a2 = 14;
        return;
      }
      v9 = 17040988;
LABEL_13:
      v10 = *(void (__fastcall **)(Jot::CBackupSectionAsync *, __int64))(*(_QWORD *)this + 96LL);
      v11 = Jot::ErrUnknownInternalError::ErrUnknownInternalError(v82, v9);
      v12 = std::make_exception_ptr<Jot::ErrUnknownInternalError>(&v74, v11);
      v10(this, v12);
      return;
    }
    v13 = *((_QWORD *)this + 154);
    if ( !v13 || !*(_QWORD *)(v13 + 32) )
    {
      v9 = 17040987;
      goto LABEL_13;
    }
    v75 = 0;
    __ExceptionPtrCreate(&v75);
    v14 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 154) + 32LL) + 80LL))(*(_QWORD *)(*((_QWORD *)this + 154) + 32LL));
    v15 = __ExceptionPtrToBool(v14);
    v16 = *((_QWORD *)this + 154);
    if ( v15 )
    {
      v17 = *(_QWORD *)(v16 + 32);
    }
    else
    {
      v18 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v16 + 40) + 80LL))(*(_QWORD *)(v16 + 40));
      if ( !__ExceptionPtrToBool(v18) )
      {
LABEL_21:
        if ( __ExceptionPtrToBool(&v75) )
        {
          v28 = *(void (__fastcall **)(Jot::CBackupSectionAsync *, __int128 *))(*(_QWORD *)this + 96LL);
          v74 = 0;
          __ExceptionPtrCopy(&v74, &v75);
          v28(this, &v74);
        }
        else if ( !(unsigned __int8)Mso::AB::Optimized::TriggeredFeatureGate::operator bool(&qword_18154BEE0, v20, v21)
               || (unsigned __int8)Mso::AB::Optimized::TriggeredFeatureGate::operator bool(&qword_18154BEF0, v22, v23) )
        {
          v24 = *(_QWORD *)(*((_QWORD *)this + 154) + 56LL);
          v25 = *(void (__fastcall **)(__int64, __int64, _QWORD, __int64, char, _QWORD, _DWORD, _BYTE, _DWORD))(*(_QWORD *)v24 + 160LL);
          v26 = *(_QWORD *)Jot::CWzInBuffer::operator MsoCF::String<MsoCF::WzTraits>((char *)this + 776, &v74);
          v27 = (_QWORD *)Jot::CWzInBuffer::operator MsoCF::String<MsoCF::WzTraits>((char *)this + 416, v79);
          v25(v24, *((_QWORD *)this + 154) + 48LL, *v27, v26, 1, 0, 0, 0, 0);
          MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(
            (char *)this + 376,
            *(_QWORD *)(*((_QWORD *)this + 154) + 48LL));
          *((_DWORD *)this + 96) = 13;
          *((_DWORD *)this + 97) = 13;
          *((_DWORD *)this + 93) = 3;
        }
        else
        {
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _BYTE, char, _BYTE))(**(_QWORD **)(*((_QWORD *)this + 154) + 56LL)
                                                                                             + 312LL))(
            *(_QWORD *)(*((_QWORD *)this + 154) + 56LL),
            0,
            0,
            0,
            0,
            0,
            1,
            0);
          *a2 = 14;
        }
        __ExceptionPtrDestroy(&v75);
        return;
      }
      v17 = *(_QWORD *)(*((_QWORD *)this + 154) + 40LL);
    }
    v19 = (const void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 80LL))(v17);
    __ExceptionPtrAssign(&v75, v19);
    goto LABEL_21;
  }
  v29 = (Jot::CReplicatorConnector *)*((_QWORD *)this + 154);
  if ( !v29 || !*((_QWORD *)v29 + 4) )
  {
    v9 = 17040986;
    goto LABEL_13;
  }
  Jot::CReplicatorConnector::Disconnect(v29);
  v30 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 154) + 32LL) + 80LL))(*(_QWORD *)(*((_QWORD *)this + 154) + 32LL));
  if ( __ExceptionPtrToBool(v30) )
  {
    *a2 = 12;
  }
  else
  {
    v31 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 154) + 24LL)
                                                                       + 160LL))(
            *(_QWORD *)(*((_QWORD *)this + 154) + 24LL),
            &v80,
            0,
            0);
    Mso::TCntPtr<Mso::Async::IDispatchQueue>::operator=(*((_QWORD *)this + 154) + 40LL, v31);
    if ( v80 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v80 + 16LL))(v80);
    MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(
      (char *)this + 376,
      *(_QWORD *)(*((_QWORD *)this + 154) + 40LL));
    *((_DWORD *)this + 96) = 12;
    *((_DWORD *)this + 97) = 12;
    *((_DWORD *)this + 93) = 3;
  }
}

```

## disassembly

```asm
0x18082e860  mov     [rsp+arg_10], rbx
0x18082e865  mov     [rsp+arg_18], rsi
0x18082e86a  push    rdi
0x18082e86b  push    r12
0x18082e86d  push    r13
0x18082e86f  push    r14
0x18082e871  push    r15
0x18082e873  sub     rsp, 180h
0x18082e87a  mov     rax, cs:__security_cookie
0x18082e881  xor     rax, rsp
0x18082e884  mov     [rsp+1A8h+var_38], rax
0x18082e88c  mov     rdi, rdx
0x18082e88f  mov     r15, rcx
0x18082e892  mov     qword ptr [rsp+1A8h+var_108], rcx
0x18082e89a  mov     ecx, [rdx]
0x18082e89c  sub     ecx, 0Ah
0x18082e89f  jz      loc_18082ECA0
0x18082e8a5  sub     ecx, 1
0x18082e8a8  jz      loc_18082EBAD
0x18082e8ae  sub     ecx, 1
0x18082e8b1  jz      loc_18082E99A
0x18082e8b7  sub     ecx, 1
0x18082e8ba  jz      short loc_18082E8EA
0x18082e8bc  cmp     ecx, 1
0x18082e8bf  jnz     loc_18082F430
0x18082e8c5  mov     rax, [r15]
0x18082e8c8  mov     rbx, [rax+60h]
0x18082e8cc  xorps   xmm0, xmm0
0x18082e8cf  movdqu  [rsp+1A8h+var_140], xmm0
0x18082e8d5  lea     rcx, [rsp+1A8h+var_140]
0x18082e8da  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18082e8e0  lea     rdx, [rsp+1A8h+var_140]
0x18082e8e5  jmp     loc_18082F424
0x18082e8ea  mov     rcx, [r15+4D0h]
0x18082e8f1  xor     r14d, r14d
0x18082e8f4  test    rcx, rcx
0x18082e8f7  jz      short loc_18082E96F
0x18082e8f9  cmp     [rcx+20h], r14
0x18082e8fd  jz      short loc_18082E96F
0x18082e8ff  mov     rcx, [rcx+30h]
0x18082e903  mov     rax, [rcx]
0x18082e906  mov     rax, [rax+50h]
0x18082e90a  call    cs:__guard_dispatch_icall_fptr
0x18082e910  mov     rcx, rax
0x18082e913  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18082e919  test    al, al
0x18082e91b  jz      short loc_18082E964
0x18082e91d  mov     rax, [r15]
0x18082e920  mov     rbx, [rax+60h]
0x18082e924  mov     rax, [r15+4D0h]
0x18082e92b  mov     rcx, [rax+30h]
0x18082e92f  mov     rax, [rcx]
0x18082e932  mov     rax, [rax+50h]
0x18082e936  call    cs:__guard_dispatch_icall_fptr
0x18082e93c  xorps   xmm0, xmm0
0x18082e93f  movdqu  [rsp+1A8h+var_140], xmm0
0x18082e945  mov     rdx, rax
0x18082e948  lea     rcx, [rsp+1A8h+var_140]
0x18082e94d  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18082e953  lea     rdx, [rsp+1A8h+var_140]
0x18082e958  mov     rcx, r15
0x18082e95b  mov     rax, rbx
0x18082e95e  call    cs:__guard_dispatch_icall_fptr
0x18082e964  mov     dword ptr [rdi], 0Eh
0x18082e96a  jmp     loc_18082F430
0x18082e96f  mov     edx, 104065Ch
0x18082e974  mov     rax, [r15]
0x18082e977  mov     rbx, [rax+60h]
0x18082e97b  lea     rcx, [rsp+1A8h+var_E8]
0x18082e983  call    ??0ErrUnknownInternalError@Jot@@QEAA@VExceptionTag@1@@Z; Jot::ErrUnknownInternalError::ErrUnknownInternalError(Jot::ExceptionTag)
0x18082e988  mov     rdx, rax
0x18082e98b  lea     rcx, [rsp+1A8h+var_140]
0x18082e990  call    ??$make_exception_ptr@UErrUnknownInternalError@Jot@@@std@@YA?AVexception_ptr@0@UErrUnknownInternalError@Jot@@@Z; std::make_exception_ptr<Jot::ErrUnknownInternalError>(Jot::ErrUnknownInternalError)
0x18082e995  jmp     loc_18082F421
0x18082e99a  mov     rax, [r15+4D0h]
0x18082e9a1  xor     r14d, r14d
0x18082e9a4  test    rax, rax
0x18082e9a7  jz      loc_18082EBA3
0x18082e9ad  cmp     [rax+20h], r14
0x18082e9b1  jz      loc_18082EBA3
0x18082e9b7  xorps   xmm0, xmm0
0x18082e9ba  movdqu  [rsp+1A8h+var_130], xmm0
0x18082e9c0  lea     rcx, [rsp+1A8h+var_130]
0x18082e9c5  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18082e9cb  nop
0x18082e9cc  mov     rax, [r15+4D0h]
0x18082e9d3  mov     rcx, [rax+20h]
0x18082e9d7  mov     rax, [rcx]
0x18082e9da  mov     rax, [rax+50h]
0x18082e9de  call    cs:__guard_dispatch_icall_fptr
0x18082e9e4  mov     rcx, rax
0x18082e9e7  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18082e9ed  mov     rcx, [r15+4D0h]
0x18082e9f4  test    al, al
0x18082e9f6  jz      short loc_18082E9FE
0x18082e9f8  mov     rcx, [rcx+20h]
0x18082e9fc  jmp     short loc_18082EA27
0x18082e9fe  mov     rcx, [rcx+28h]
0x18082ea02  mov     rax, [rcx]
0x18082ea05  mov     rax, [rax+50h]
0x18082ea09  call    cs:__guard_dispatch_icall_fptr
0x18082ea0f  mov     rcx, rax
0x18082ea12  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18082ea18  test    al, al
0x18082ea1a  jz      short loc_18082EA42
0x18082ea1c  mov     rax, [r15+4D0h]
0x18082ea23  mov     rcx, [rax+28h]
0x18082ea27  mov     rax, [rcx]
0x18082ea2a  mov     rax, [rax+50h]
0x18082ea2e  call    cs:__guard_dispatch_icall_fptr
0x18082ea34  mov     rdx, rax
0x18082ea37  lea     rcx, [rsp+1A8h+var_130]
0x18082ea3c  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18082ea42  lea     rcx, [rsp+1A8h+var_130]
0x18082ea47  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18082ea4d  test    al, al
0x18082ea4f  jnz     loc_18082EB61
0x18082ea55  lea     rcx, qword_18154BEE0
0x18082ea5c  call    ??BTriggeredFeatureGate@Optimized@AB@Mso@@QEGBA_NXZ; Mso::AB::Optimized::TriggeredFeatureGate::operator bool(void)
0x18082ea61  test    al, al
0x18082ea63  jz      short loc_18082EAB7
0x18082ea65  lea     rcx, qword_18154BEF0
0x18082ea6c  call    ??BTriggeredFeatureGate@Optimized@AB@Mso@@QEGBA_NXZ; Mso::AB::Optimized::TriggeredFeatureGate::operator bool(void)
0x18082ea71  test    al, al
0x18082ea73  jnz     short loc_18082EAB7
0x18082ea75  mov     rax, [r15+4D0h]
0x18082ea7c  mov     rcx, [rax+38h]
0x18082ea80  mov     rax, [rcx]
0x18082ea83  mov     byte ptr [rsp+1A8h+var_170], r14b
0x18082ea88  mov     byte ptr [rsp+1A8h+var_178], 1
0x18082ea8d  mov     byte ptr [rsp+1A8h+var_180], r14b
0x18082ea92  mov     qword ptr [rsp+1A8h+var_188], r14
0x18082ea97  xor     r9d, r9d
0x18082ea9a  xor     r8d, r8d
0x18082ea9d  xor     edx, edx
0x18082ea9f  mov     rax, [rax+138h]
0x18082eaa6  call    cs:__guard_dispatch_icall_fptr
0x18082eaac  mov     dword ptr [rdi], 0Eh
0x18082eab2  jmp     loc_18082EB93
0x18082eab7  mov     rax, [r15+4D0h]
0x18082eabe  mov     rsi, [rax+38h]
0x18082eac2  mov     rax, [rsi]
0x18082eac5  mov     rdi, [rax+0A0h]
0x18082eacc  lea     rcx, [r15+308h]
0x18082ead3  lea     rdx, [rsp+1A8h+var_140]
0x18082ead8  call    ??BCWzInBuffer@Jot@@QEBA?AV?$String@UWzTraits@MsoCF@@@MsoCF@@XZ; Jot::CWzInBuffer::operator MsoCF::String<MsoCF::WzTraits>(void)
0x18082eadd  mov     rbx, [rax]
0x18082eae0  lea     rcx, [r15+1A0h]
0x18082eae7  lea     rdx, [rsp+1A8h+var_108]
0x18082eaef  call    ??BCWzInBuffer@Jot@@QEBA?AV?$String@UWzTraits@MsoCF@@@MsoCF@@XZ; Jot::CWzInBuffer::operator MsoCF::String<MsoCF::WzTraits>(void)
0x18082eaf4  mov     rdx, [r15+4D0h]
0x18082eafb  add     rdx, 30h ; '0'
0x18082eaff  mov     dword ptr [rsp+1A8h+var_168], r14d
0x18082eb04  mov     byte ptr [rsp+1A8h+var_170], r14b
0x18082eb09  mov     [rsp+1A8h+var_178], r14d
0x18082eb0e  mov     qword ptr [rsp+1A8h+var_180], r14
0x18082eb13  mov     [rsp+1A8h+var_188], 1
0x18082eb18  mov     r9, rbx
0x18082eb1b  mov     r8, [rax]
0x18082eb1e  mov     rcx, rsi
0x18082eb21  mov     rax, rdi
0x18082eb24  call    cs:__guard_dispatch_icall_fptr
0x18082eb2a  mov     rax, [r15+4D0h]
0x18082eb31  lea     rcx, [r15+178h]
0x18082eb38  mov     rdx, [rax+30h]
0x18082eb3c  call    ?Assign@?$CIPtr@UICellStorage@CsiCell@@U12@@MsoCF@@QEAAXPEAUICellStorage@CsiCell@@@Z; MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(CsiCell::ICellStorage *)
0x18082eb41  mov     eax, 0Dh
0x18082eb46  mov     [r15+180h], eax
0x18082eb4d  mov     [r15+184h], eax
0x18082eb54  mov     dword ptr [r15+174h], 3
0x18082eb5f  jmp     short loc_18082EB93
0x18082eb61  mov     rax, [r15]
0x18082eb64  mov     rbx, [rax+60h]
0x18082eb68  xorps   xmm0, xmm0
0x18082eb6b  movdqu  [rsp+1A8h+var_140], xmm0
0x18082eb71  lea     rdx, [rsp+1A8h+var_130]
0x18082eb76  lea     rcx, [rsp+1A8h+var_140]
0x18082eb7b  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18082eb81  lea     rdx, [rsp+1A8h+var_140]
0x18082eb86  mov     rcx, r15
0x18082eb89  mov     rax, rbx
0x18082eb8c  call    cs:__guard_dispatch_icall_fptr
0x18082eb92  nop
0x18082eb93  lea     rcx, [rsp+1A8h+var_130]
0x18082eb98  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18082eb9e  jmp     loc_18082F430
0x18082eba3  mov     edx, 104065Bh
0x18082eba8  jmp     loc_18082E974
0x18082ebad  mov     rcx, [r15+4D0h]; this
0x18082ebb4  xor     r14d, r14d
0x18082ebb7  test    rcx, rcx
0x18082ebba  jz      loc_18082EC96
0x18082ebc0  cmp     [rcx+20h], r14
0x18082ebc4  jz      loc_18082EC96
0x18082ebca  call    ?Disconnect@CReplicatorConnector@Jot@@QEAAXXZ; Jot::CReplicatorConnector::Disconnect(void)
0x18082ebcf  mov     rax, [r15+4D0h]
0x18082ebd6  mov     rcx, [rax+20h]
0x18082ebda  mov     rax, [rcx]
0x18082ebdd  mov     rax, [rax+50h]
0x18082ebe1  call    cs:__guard_dispatch_icall_fptr
0x18082ebe7  mov     rcx, rax
0x18082ebea  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x18082ebf0  test    al, al
0x18082ebf2  jnz     loc_18082EC8B
0x18082ebf8  mov     rax, [r15+4D0h]
0x18082ebff  mov     rcx, [rax+18h]
0x18082ec03  mov     rax, [rcx]
0x18082ec06  xor     r9d, r9d
0x18082ec09  xor     r8d, r8d
0x18082ec0c  lea     rdx, [rsp+1A8h+var_F8]
0x18082ec14  mov     rax, [rax+0A0h]
0x18082ec1b  call    cs:__guard_dispatch_icall_fptr
0x18082ec21  mov     rcx, [r15+4D0h]
0x18082ec28  add     rcx, 28h ; '('
0x18082ec2c  mov     rdx, rax
0x18082ec2f  call    ??4?$TCntPtr@VIDispatchQueue@Async@Mso@@@Mso@@QEAAAEAV01@$$QEAV01@@Z; Mso::TCntPtr<Mso::Async::IDispatchQueue>::operator=(Mso::TCntPtr<Mso::Async::IDispatchQueue> &&)
0x18082ec34  mov     rcx, [rsp+1A8h+var_F8]
0x18082ec3c  test    rcx, rcx
0x18082ec3f  jz      short loc_18082EC4E
0x18082ec41  mov     rax, [rcx]
0x18082ec44  mov     rax, [rax+10h]
0x18082ec48  call    cs:__guard_dispatch_icall_fptr
0x18082ec4e  mov     rdx, [r15+4D0h]
0x18082ec55  lea     rcx, [r15+178h]
0x18082ec5c  mov     rdx, [rdx+28h]
0x18082ec60  call    ?Assign@?$CIPtr@UICellStorage@CsiCell@@U12@@MsoCF@@QEAAXPEAUICellStorage@CsiCell@@@Z; MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(CsiCell::ICellStorage *)
0x18082ec65  mov     dword ptr [r15+180h], 0Ch
0x18082ec70  mov     dword ptr [r15+184h], 0Ch
0x18082ec7b  mov     dword ptr [r15+174h], 3
0x18082ec86  jmp     loc_18082F430
0x18082ec8b  mov     dword ptr [rdi], 0Ch
0x18082ec91  jmp     loc_18082F430
0x18082ec96  mov     edx, 104065Ah
0x18082ec9b  jmp     loc_18082E974
0x18082eca0  lea     rsi, [r15+190h]
0x18082eca7  mov     rcx, rsi
0x18082ecaa  call    ?IsValid@?$CNodeRef@VCSemNotebookTrait@Jot@@@Jot@@QEBA_NXZ; Jot::CNodeRef<Jot::CSemNotebookTrait>::IsValid(void)
0x18082ecaf  xor     r14d, r14d
0x18082ecb2  test    al, al
0x18082ecb4  jz      loc_18082F3E7
0x18082ecba  mov     rcx, [rsi]
0x18082ecbd  mov     rax, [rcx]
0x18082ecc0  mov     rax, [rax+0A8h]
0x18082ecc7  call    cs:__guard_dispatch_icall_fptr
0x18082eccd  test    al, al
0x18082eccf  jz      loc_18082F3E7
0x18082ecd5  mov     rcx, [rsi]
0x18082ecd8  mov     [rsp+1A8h+var_120], r14
0x18082ece0  test    rcx, rcx
0x18082ece3  jz      short loc_18082ED14
0x18082ece5  mov     rax, [rcx]
0x18082ece8  mov     rax, [rax]
0x18082eceb  lea     rdx, ?QueryInterface@?$CJotComObject@VCGraphSpaceNode@Jot@@VCAllocatorOnNew@MsoCF@@@MsoCF@@UEAAJAEBU_GUID@@PEAPEAX@Z; MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(_GUID const &,void * *)
0x18082ecf2  lea     r8, [rsp+1A8h+var_120]
0x18082ecfa  cmp     rax, rdx
0x18082ecfd  lea     rdx, _GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b
0x18082ed04  jnz     short loc_18082ED0D
0x18082ed06  call    ?QueryInterface@?$CJotComObject@VCGraphSpaceNode@Jot@@VCAllocatorOnNew@MsoCF@@@MsoCF@@UEAAJAEBU_GUID@@PEAPEAX@Z; MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(_GUID const &,void * *)
0x18082ed0b  jmp     short loc_18082ED14
0x18082ed0d  call    cs:__guard_dispatch_icall_fptr
0x18082ed13  nop
0x18082ed14  cmp     [rsp+1A8h+var_120], r14
0x18082ed1c  jnz     short loc_18082ED90
0x18082ed1e  mov     rax, [r15]
0x18082ed21  mov     rbx, [rax+60h]
0x18082ed25  mov     edx, 1040657h
0x18082ed2a  lea     rcx, [rsp+1A8h+var_E8]
0x18082ed32  call    ??0ErrUnknownInternalError@Jot@@QEAA@VExceptionTag@1@@Z; Jot::ErrUnknownInternalError::ErrUnknownInternalError(Jot::ExceptionTag)
0x18082ed37  mov     rdx, rax
0x18082ed3a  lea     rcx, [rsp+1A8h+var_140]
0x18082ed3f  call    ??$make_exception_ptr@UErrUnknownInternalError@Jot@@@std@@YA?AVexception_ptr@0@UErrUnknownInternalError@Jot@@@Z; std::make_exception_ptr<Jot::ErrUnknownInternalError>(Jot::ErrUnknownInternalError)
0x18082ed44  mov     rdx, rax
0x18082ed47  mov     rcx, r15
0x18082ed4a  mov     rax, rbx
0x18082ed4d  call    cs:__guard_dispatch_icall_fptr
0x18082ed53  nop
0x18082ed54  mov     rcx, [rsp+1A8h+var_120]; void *
0x18082ed5c  test    rcx, rcx
0x18082ed5f  jz      loc_18082F430
0x18082ed65  mov     rax, [rcx]
0x18082ed68  mov     rdx, [rax+10h]
0x18082ed6c  lea     rax, ?Release@?$CJotComObject@VCGraphSpaceNode@Jot@@VCAllocatorOnNew@MsoCF@@@MsoCF@@UEAAKXZ; MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::Release(void)
0x18082ed73  cmp     rdx, rax
0x18082ed76  jnz     short loc_18082ED82
0x18082ed78  call    ?Release@?$CJotComObject@VCGraphSpaceNode@Jot@@VCAllocatorOnNew@MsoCF@@@MsoCF@@UEAAKXZ; MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::Release(void)
0x18082ed7d  jmp     loc_18082F430
0x18082ed82  mov     rax, rdx
0x18082ed85  call    cs:__guard_dispatch_icall_fptr
0x18082ed8b  jmp     loc_18082F430
0x18082ed90  mov     ecx, 70h ; 'p'; this
0x18082ed95  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18082ed9a  mov     r12, rax
0x18082ed9d  mov     qword ptr [rsp+1A8h+var_140], rax
0x18082eda2  test    rax, rax
0x18082eda5  jz      short loc_18082EDE8
0x18082eda7  mov     [rax], r14
0x18082edaa  mov     [rax+8], r14
0x18082edae  mov     [rax+10h], r14
0x18082edb2  mov     [rax+18h], r14
0x18082edb6  mov     [rax+20h], r14
  ... truncated ...
```
