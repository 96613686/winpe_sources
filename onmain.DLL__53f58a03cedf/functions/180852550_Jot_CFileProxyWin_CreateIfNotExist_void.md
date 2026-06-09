# Jot::CFileProxyWin::CreateIfNotExist(void)

- ea: `0x180852550`
- end: `0x180853055`
- name: `?CreateIfNotExist@CFileProxyWin@Jot@@UEAA_NXZ`
- size: `2821`
- prototype: `bool __fastcall(Jot::CFileProxyWin *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config`

## callees

- `0x18002e7a8`
- `0x18002fa9c`
- `0x18006eaec`
- `0x1801ad1c4`
- `0x1801adc90`
- `0x1801ae484`
- `0x1801af940`
- `0x1802de718`
- `0x1802e2190`
- `0x1802e50d0`
- `0x1802e5170`
- `0x1802e5190`
- `0x18032e4fc`
- `0x180445818`
- `0x1807a5aa0`
- `0x180852550`
- `0x180914fe0`

## import_xrefs

- `MSO!__imp_?MsoHrDrmStgCreateStorageEx@@YAJKPEB_WKKKPEAUtagSTGOPTIONS@@PEAXAEBU_GUID@@PEAUIMsoDrmDocument@@PEAUIStorage@@PEAPEAXAEBUOperationContext@Drm@Mso@@@Z` at `0x180852bfb`
- `MSO!__imp_?MsoHrDrmStgCreateStorageEx@@YAJKPEB_WKKKPEAUtagSTGOPTIONS@@PEAXAEBU_GUID@@PEAUIMsoDrmDocument@@PEAUIStorage@@PEAPEAXAEBUOperationContext@Drm@Mso@@@Z` at `0x180852bfb`
- `MSO!__imp_?CreateMetadataParser@Xml@Clp@Mso@@YA?AV?$TCntPtr@UIMetadataParser@Xml@Clp@Mso@@@3@AEAUIStream@@@Z` at `0x180852953`
- `MSO!__imp_?CreateMetadataParser@Xml@Clp@Mso@@YA?AV?$TCntPtr@UIMetadataParser@Xml@Clp@Mso@@@3@AEAUIStream@@@Z` at `0x180852e34`
- `MSO!__imp_?CreateMetadataParser@Xml@Clp@Mso@@YA?AV?$TCntPtr@UIMetadataParser@Xml@Clp@Mso@@@3@AEAUIStream@@@Z` at `0x180852953`
- `MSO!__imp_?CreateMetadataParser@Xml@Clp@Mso@@YA?AV?$TCntPtr@UIMetadataParser@Xml@Clp@Mso@@@3@AEAUIStream@@@Z` at `0x180852e34`
- `MSO!__imp_?CreateOperationContext@Drm@Mso@@YA?AUOperationContext@12@XZ` at `0x180852b81`
- `MSO!__imp_?CreateOperationContext@Drm@Mso@@YA?AUOperationContext@12@XZ` at `0x180852b81`
- `MSO!__imp_?MsoHrCreateEncryptedStream@@YAJKPEAUIStorage@@PEAUISession@Crypto@Mso@@PEAPEAUIStream@@@Z` at `0x180852ecd`
- `MSO!__imp_?MsoHrCreateEncryptedStream@@YAJKPEAUIStorage@@PEAUISession@Crypto@Mso@@PEAPEAUIStream@@@Z` at `0x180852ecd`
- `Mso20Win32Client!__imp_?MsoStgCreateStorageEx@@YAJPEB_WKKKPEAUtagSTGOPTIONS@@PEAXAEBU_GUID@@PEAPEAX@Z` at `0x180852710`
- `Mso20Win32Client!__imp_?MsoStgCreateStorageEx@@YAJPEB_WKKKPEAUtagSTGOPTIONS@@PEAXAEBU_GUID@@PEAPEAX@Z` at `0x180852710`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180852625`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180852625`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18085282f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1808528c2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18085296a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18085282f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1808528c2`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18085296a`

## string_xrefs

- `0x1808525ca`: `CreateLocalFile`
- `0x180852a68`: `LabeledFileCreated`
- `0x180852f28`: `LabeledFileCreated`
- `0x180853005`: `FileAlreadyExists`
- `0x180852a1f`: `CreateUnencryptedPackageStreamFailed`
- `0x180852868`: `CreateTransformInfoStorageFailed`
- `0x1808527d6`: `CreateDataSpacesStorageFailed`
- `0x180852ee0`: `CreateEncryptedStreamFailed`
- `0x18085298c`: `WriteLabelInfoFailed`
- `0x180852e71`: `WriteLabelInfoFailed`
- `0x1808528fb`: `CreateLabelInfoStreamFailed`
- `0x180852de2`: `CreateLabelInfoStreamFailed`
- `0x180852740`: `CreateFileFailed`
- `0x180852c23`: `CreateFileFailed`
- `0x180852d57`: `OpenTransformInfoStorageFailed`
- `0x180852cc3`: `OpenDataSpacesStorageFailed`

## pseudocode

```c
bool __fastcall Jot::CFileProxyWin::CreateIfNotExist(Jot::CFileProxyWin *this)
{
  struct Mso::Telemetry::IActivityParenter *v2; // rax
  __int64 v3; // rdi
  _QWORD *v4; // rax
  char v5; // di
  bool v6; // al
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // edi
  _QWORD *v10; // rax
  __int64 v11; // rax
  int v12; // edi
  _QWORD *v13; // rax
  __int64 v14; // rcx
  int v15; // edi
  _QWORD *v16; // rax
  __int64 v17; // rcx
  int v18; // edi
  _QWORD *v19; // rax
  struct Mso::Telemetry::IActivityParenter *v20; // rcx
  _QWORD *v21; // rax
  __int64 v22; // rax
  int v23; // edi
  _QWORD *v24; // rax
  unsigned int FileOrDirectory; // edi
  struct IStream *v26; // rcx
  struct Mso::Telemetry::IActivityParenter *v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  Jot *v31; // rax
  bool v32; // r9
  const struct Mso::Drm::OperationContext *OperationContext; // rdi
  struct IMsoDrmDocument *v34; // r14
  __int64 v35; // rax
  int Storage; // edi
  _QWORD *v37; // rax
  __int64 v38; // rax
  int v39; // edi
  _QWORD *v40; // rax
  __int64 v41; // rax
  int v42; // edi
  _QWORD *v43; // rax
  __int64 v44; // rax
  int v45; // edi
  _QWORD *v46; // rax
  __int64 v47; // rax
  _QWORD *v48; // rax
  int v49; // edi
  _QWORD *v50; // rax
  struct Mso::Telemetry::IActivityParenter *v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v55; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v56; // [rsp+70h] [rbp-98h] BYREF
  struct Mso::Telemetry::IActivityParenter *v57; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v58[8]; // [rsp+80h] [rbp-88h] BYREF
  struct IStream *v59; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v60[2]; // [rsp+90h] [rbp-78h] BYREF
  __int64 v61; // [rsp+A0h] [rbp-68h] BYREF
  char v62[8]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v63[440]; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD v64[3]; // [rsp+268h] [rbp+160h] BYREF
  unsigned __int64 v65; // [rsp+280h] [rbp+178h]
  _BYTE v66[80]; // [rsp+288h] [rbp+180h] BYREF

  v2 = Mso::Telemetry::Activity::UseThreadCurrentParenter();
  v3 = (__int64)v2;
  v57 = v2;
  if ( v2 )
    (*(void (__fastcall **)(struct Mso::Telemetry::IActivityParenter *))(*(_QWORD *)v2 + 8LL))(v2);
  v58[1] = 0;
  v4 = (_QWORD *)Mso::Telemetry::EventFlags::EventFlags(&v59, 4);
  v60[0] = &off_1811FB7C0;
  v60[1] = "CreateLocalFile";
  Jot::Logging::Activity::Activity((unsigned int)v62, (unsigned int)v60, 0, *v4, (__int64)v58, v3);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v5 = 0;
  if ( byte_181549DC8 < 0 )
    v6 = Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_181549DC8);
  else
    v6 = byte_181549DC8 != 0;
  if ( v6 )
    v5 = (*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD, __int64))(*(_QWORD *)this + 80LL))(this, 0, 600000000);
  if ( *((_QWORD *)this + 60) || v5 )
  {
    Jot::Logging::Activity::Succeed<Mso::StringLiterals::StringLiteral<char>,>(v62, "FileAlreadyExists");
    std::_Optional_destruct_base<Office::System::Result,0>::~_Optional_destruct_base<Office::System::Result,0>(v63);
    std::unique_ptr<Jot::Logging::Activity::Impl>::~unique_ptr<Jot::Logging::Activity::Impl>(v62);
    return 0;
  }
  (*(void (__fastcall **)(Jot::CFileProxyWin *, __int64 *))(*(_QWORD *)this + 232LL))(this, &v61);
  if ( v61 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v61 + 24LL))(v61);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 48LL))(v7);
  }
  if ( *((_QWORD *)this + 57) )
  {
    OperationContext = (const struct Mso::Drm::OperationContext *)Mso::Drm::CreateOperationContext(v66);
    v34 = (struct IMsoDrmDocument *)*((_QWORD *)this + 57);
    v35 = (*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD *, _QWORD))(*(_QWORD *)this + 112LL))(this, v64, 0);
    if ( *(_QWORD *)(v35 + 24) > 7u )
      v35 = *(_QWORD *)v35;
    Storage = MsoHrDrmStgCreateStorageEx(
                0x10000000u,
                (const wchar_t *)v35,
                0x1012u,
                5u,
                0,
                0,
                0,
                &IID_IStorage,
                v34,
                0,
                (void **)this + 60,
                OperationContext);
    std::wstring::~wstring(v64);
    Mso::Drm::OperationContext::~OperationContext((Mso::Drm::OperationContext *)v66);
    if ( Storage < 0 )
    {
      Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>((Jot::Logging::Activity *)v62);
      v37 = (_QWORD *)(*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD *, _QWORD))(*(_QWORD *)this + 112LL))(
                        this,
                        v64,
                        0);
      if ( v37[3] > 7u )
        v37 = (_QWORD *)*v37;
      Jot::ThrowHRESULTWithFilenameTag((unsigned int)Storage, v37, 505427419);
    }
    v55 = 0;
    v56 = 0;
    v60[0] = 0;
    v38 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->((char *)this + 480);
    v39 = (*(__int64 (__fastcall **)(__int64, const wchar_t near *const *, _QWORD, __int64, _QWORD, _DWORD, __int64 *))(*(_QWORD *)v38 + 48LL))(
            v38,
            &c_wzDataSpacesStg,
            0,
            18,
            0,
            0,
            &v55);
    if ( v39 < 0 )
    {
      Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>((Jot::Logging::Activity *)v62);
      v40 = (_QWORD *)(*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD *, _QWORD))(*(_QWORD *)this + 112LL))(
                        this,
                        v64,
                        0);
      if ( v40[3] > 7u )
        v40 = (_QWORD *)*v40;
      Jot::ThrowHRESULTWithFilenameTag((unsigned int)v39, v40, 504643977);
    }
    v41 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v55);
    v42 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, __int64, _QWORD, _DWORD, __int64 *))(*(_QWORD *)v41 + 48LL))(
            v41,
            L"TransformInfo",
            0,
            18,
            0,
            0,
            &v56);
    if ( v42 < 0 )
    {
      Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>((Jot::Logging::Activity *)v62);
      v43 = (_QWORD *)(*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD *, _QWORD))(*(_QWORD *)this + 112LL))(
                        this,
                        v64,
                        0);
      if ( v43[3] > 7u )
        v43 = (_QWORD *)*v43;
      Jot::ThrowHRESULTWithFilenameTag((unsigned int)v42, v43, 504643976);
    }
    v44 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v56);
    v45 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, _DWORD, _QWORD *))(*(_QWORD *)v44 + 24LL))(
            v44,
            L"LabelInfo",
            4114,
            0,
            0,
            v60);
    if ( v45 < 0 )
    {
      Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>((Jot::Logging::Activity *)v62);
      v46 = (_QWORD *)(*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD *, _QWORD))(*(_QWORD *)this + 112LL))(
                        this,
                        v64,
                        0);
      if ( v46[3] > 7u )
        v46 = (_QWORD *)*v46;
      Jot::ThrowHRESULTWithFilenameTag((unsigned int)v45, v46, 505172755);
    }
    Mso::Clp::Xml::CreateMetadataParser(&v57, v60[0]);
    v47 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(&v57);
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v47 + 48LL))(v47, *((_QWORD *)this + 59)) )
    {
      Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>((Jot::Logging::Activity *)v62);
      v48 = (_QWORD *)(*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD *, _QWORD))(*(_QWORD *)this + 112LL))(
                        this,
                        v64,
                        0);
      if ( v48[3] > 7u )
        v48 = (_QWORD *)*v48;
      Jot::ThrowHRESULTWithFilenameTag(2147500037LL, v48, 505172754);
    }
    v59 = 0;
    v49 = MsoHrCreateEncryptedStream(0, *((struct IStorage **)this + 60), 0, &v59);
    if ( v49 < 0 )
    {
      Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>((Jot::Logging::Activity *)v62);
      v50 = (_QWORD *)(*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD *, _QWORD))(*(_QWORD *)this + 112LL))(
                        this,
                        v64,
                        0);
      if ( v50[3] > 7u )
        v50 = (_QWORD *)*v50;
      Jot::ThrowHRESULTWithFilenameTag((unsigned int)v49, v50, 505427418);
    }
    FileOrDirectory = 0;
    Jot::Logging::Activity::Succeed<Mso::StringLiterals::StringLiteral<char>,>(v62, "LabeledFileCreated");
    if ( v59 )
      ((void (__fastcall *)(struct IStream *))v59->lpVtbl->Release)(v59);
    v51 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(struct Mso::Telemetry::IActivityParenter *))(*(_QWORD *)v51 + 8LL))(v51);
    }
    v52 = v60[0];
    if ( v60[0] )
    {
      v60[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    }
    v53 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
    }
    v30 = v55;
    if ( !v55 )
      goto LABEL_104;
    v55 = 0;
LABEL_103:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    goto LABEL_104;
  }
  if ( *((_BYTE *)this + 448) )
  {
    v8 = (*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD *, _QWORD))(*(_QWORD *)this + 112LL))(this, v64, 0);
    if ( *(_QWORD *)(v8 + 24) > 7u )
      v8 = *(_QWORD *)v8;
    v9 = MsoStgCreateStorageEx((const wchar_t *)v8, 0x1012u, 5u, 0, 0, 0, &IID_IStorage, (void **)this + 60);
    if ( v65 > 7 )
      std::_Deallocate<16>(v64[0], 2 * v65 + 2);
    if ( v9 < 0 )
    {
      Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>((Jot::Logging::Activity *)v62);
      v10 = (_QWORD *)(*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD *, _QWORD))(*(_QWORD *)this + 112LL))(
                        this,
                        v64,
                        0);
      if ( v10[3] > 7u )
        v10 = (_QWORD *)*v10;
      Jot::ThrowHRESULTWithFilenameTag((unsigned int)v9, v10, 504653386);
    }
    v60[0] = 0;
    v56 = 0;
    v55 = 0;
    v11 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->((char *)this + 480);
    v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t near *const *, __int64, _QWORD, _DWORD, _QWORD *))(*(_QWORD *)v11 + 40LL))(
            v11,
            &c_wzDataSpacesStg,
            4114,
            0,
            0,
            v60);
    if ( v12 < 0 )
    {
      Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>((Jot::Logging::Activity *)v62);
      v13 = (_QWORD *)(*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD *, _QWORD))(*(_QWORD *)this + 112LL))(
                        this,
                        v64,
                        0);
      if ( v13[3] > 7u )
        v13 = (_QWORD *)*v13;
      Jot::ThrowHRESULTWithFilenameTag((unsigned int)v12, v13, 504653385);
    }
    v14 = v60[0];
    if ( !v60[0] )
      CrashWithRecovery(0x1E3C3840u, 0);
    v15 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, _DWORD, __int64 *))(*(_QWORD *)v14 + 40LL))(
            v14,
            L"TransformInfo",
            4114,
            0,
            0,
            &v56);
    if ( v15 < 0 )
    {
      Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>((Jot::Logging::Activity *)v62);
      v16 = (_QWORD *)(*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD *, _QWORD))(*(_QWORD *)this + 112LL))(
                        this,
                        v64,
                        0);
      if ( v16[3] > 7u )
        v16 = (_QWORD *)*v16;
      Jot::ThrowHRESULTWithFilenameTag((unsigned int)v15, v16, 504653384);
    }
    v17 = v56;
    if ( !v56 )
      CrashWithRecovery(0x1E3C3840u, 0);
    v18 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, _DWORD, __int64 *))(*(_QWORD *)v17 + 24LL))(
            v17,
            L"LabelInfo",
            4114,
            0,
            0,
            &v55);
    if ( v18 < 0 )
    {
      Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>((Jot::Logging::Activity *)v62);
      v19 = (_QWORD *)(*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD *, _QWORD))(*(_QWORD *)this + 112LL))(
                        this,
                        v64,
                        0);
      if ( v19[3] > 7u )
        v19 = (_QWORD *)*v19;
      Jot::ThrowHRESULTWithFilenameTag((unsigned int)v18, v19, 505427417);
    }
    Mso::Clp::Xml::CreateMetadataParser(&v57, v55);
    v20 = v57;
    if ( !v57 )
      CrashWithRecovery(0x1E3C3840u, 0);
    if ( !(*(unsigned __int8 (__fastcall **)(struct Mso::Telemetry::IActivityParenter *, _QWORD))(*(_QWORD *)v20 + 48LL))(
            v20,
            *((_QWORD *)this + 59)) )
    {
      Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>((Jot::Logging::Activity *)v62);
      v21 = (_QWORD *)(*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD *, _QWORD))(*(_QWORD *)this + 112LL))(
                        this,
                        v64,
                        0);
      if ( v21[3] > 7u )
        v21 = (_QWORD *)*v21;
      Jot::ThrowHRESULTWithFilenameTag(2147500037LL, v21, 505427416);
    }
    v59 = 0;
    v22 = Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->((char *)this + 480);
    v23 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, _QWORD, _DWORD, struct IStream **))(*(_QWORD *)v22 + 24LL))(
            v22,
            L"UnencryptedPackage",
            4114,
            0,
            0,
            &v59);
    if ( v23 < 0 )
    {
      Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>((Jot::Logging::Activity *)v62);
      v24 = (_QWORD *)(*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD *, _QWORD))(*(_QWORD *)this + 112LL))(
                        this,
                        v64,
                        0);
      if ( v24[3] > 7u )
        v24 = (_QWORD *)*v24;
      Jot::ThrowHRESULTWithFilenameTag((unsigned int)v23, v24, 505427415);
    }
    FileOrDirectory = 0;
    Jot::Logging::Activity::Succeed<Mso::StringLiterals::StringLiteral<char>,>(v62, "LabeledFileCreated");
    v26 = v59;
    if ( v59 )
    {
      v59 = 0;
      ((void (__fastcall *)(struct IStream *))v26->lpVtbl->Release)(v26);
    }
    v27 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(struct Mso::Telemetry::IActivityParenter *))(*(_QWORD *)v27 + 8LL))(v27);
    }
    v28 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    v29 = v56;
    if ( v56 )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v60[0];
    if ( !v60[0] )
      goto LABEL_104;
    v60[0] = 0;
    goto LABEL_103;
  }
  Jot::Logging::Activity::Succeed<Mso::StringLiterals::StringLiteral<char>,>(v62, "NonLabeledFile");
  v31 = (Jot *)(*(__int64 (__fastcall **)(Jot::CFileProxyWin *, _QWORD *, _QWORD))(*(_QWORD *)this + 112LL))(
                 this,
                 v64,
                 0);
  if ( *((_QWORD *)v31 + 3) > 7u )
    v31 = *(Jot **)v31;
  FileOrDirectory = Jot::CreateFileOrDirectory(v31, 0, 0, v32);
  std::wstring::~wstring(v64);
  if ( FileOrDirectory )
  {
    if ( FileOrDirectory != 183 && FileOrDirectory != 80 )
      Jot::CFileProxyBase::ThrowError(this, FileOrDirectory);
    goto LABEL_105;
  }
LABEL_104:
  (*(void (__fastcall **)(Jot::CFileProxyWin *, _QWORD))(*(_QWORD *)this + 440LL))(this, 0);
LABEL_105:
  if ( v61 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
  std::_Optional_destruct_base<Office::System::Result,0>::~_Optional_destruct_base<Office::System::Result,0>(v63);
  std::unique_ptr<Jot::Logging::Activity::Impl>::~unique_ptr<Jot::Logging::Activity::Impl>(v62);
  return FileOrDirectory == 0;
}

```

## disassembly

```asm
0x180852550  mov     rax, rsp
0x180852553  mov     [rax+10h], rbx
0x180852557  mov     [rax+18h], rsi
0x18085255b  mov     [rax+20h], rdi
0x18085255f  push    rbp
0x180852560  push    r14
0x180852562  push    r15
0x180852564  lea     rbp, [rax-1F8h]
0x18085256b  sub     rsp, 2E0h
0x180852572  mov     rax, cs:__security_cookie
0x180852579  xor     rax, rsp
0x18085257c  mov     [rbp+1F0h+var_20], rax
0x180852583  mov     rbx, rcx
0x180852586  call    ?UseThreadCurrentParenter@Activity@Telemetry@Mso@@SAAEAUIActivityParenter@23@XZ; Mso::Telemetry::Activity::UseThreadCurrentParenter(void)
0x18085258b  mov     rdi, rax
0x18085258e  mov     [rsp+2F0h+var_280], rax
0x180852593  xor     r15d, r15d
0x180852596  test    rax, rax
0x180852599  jz      short loc_1808525AC
0x18085259b  mov     rcx, [rax]
0x18085259e  mov     rax, [rcx+8]
0x1808525a2  mov     rcx, rdi
0x1808525a5  call    cs:__guard_dispatch_icall_fptr
0x1808525ab  nop
0x1808525ac  mov     [rsp+2F0h+var_277], r15b
0x1808525b1  mov     edx, 4
0x1808525b6  lea     rcx, [rbp+1F0h+var_270]
0x1808525ba  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::DataCategories)
0x1808525bf  lea     rcx, off_1811FB7C0
0x1808525c6  mov     [rbp+1F0h+var_268], rcx
0x1808525ca  lea     rcx, aCreatelocalfil; "CreateLocalFile"
0x1808525d1  mov     [rbp+1F0h+var_260], rcx
0x1808525d5  mov     [rsp+2F0h+var_2C8], rdi
0x1808525da  lea     rcx, [rsp+2F0h+var_278]
0x1808525df  mov     [rsp+2F0h+var_2D0], rcx
0x1808525e4  mov     r9, [rax]
0x1808525e7  xor     r8d, r8d
0x1808525ea  lea     rdx, [rbp+1F0h+var_268]
0x1808525ee  lea     rcx, [rbp+1F0h+var_250]
0x1808525f2  call    ??0Activity@Logging@Jot@@IEAA@AEBUEventName@Telemetry@Mso@@W4ActivityType@12@UEventFlags@45@$$QEAV?$optional@VEventExportability@Telemetry@Mso@@@std@@AEBUIActivityParenter@45@@Z; Jot::Logging::Activity::Activity(Mso::Telemetry::EventName const &,Jot::Logging::ActivityType,Mso::Telemetry::EventFlags,std::optional<Mso::Telemetry::EventExportability> &&,Mso::Telemetry::IActivityParenter const &)
0x1808525f7  test    rdi, rdi
0x1808525fa  jz      short loc_18085260C
0x1808525fc  mov     rax, [rdi]
0x1808525ff  mov     rcx, rdi
0x180852602  mov     rax, [rax+10h]
0x180852606  call    cs:__guard_dispatch_icall_fptr
0x18085260c  mov     dil, r15b
0x18085260f  mov     al, cs:byte_181549DC8
0x180852615  test    al, al
0x180852617  js      short loc_18085261E
0x180852619  setnz   al
0x18085261c  jmp     short loc_18085262B
0x18085261e  lea     rcx, byte_181549DC8
0x180852625  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x18085262b  test    al, al
0x18085262d  jz      short loc_18085264A
0x18085262f  mov     rax, [rbx]
0x180852632  xor     edx, edx
0x180852634  mov     r8d, 23C34600h
0x18085263a  mov     rcx, rbx
0x18085263d  mov     rax, [rax+50h]
0x180852641  call    cs:__guard_dispatch_icall_fptr
0x180852647  mov     dil, al
0x18085264a  lea     rsi, [rbx+1E0h]
0x180852651  cmp     [rsi], r15
0x180852654  jnz     loc_180853005
0x18085265a  test    dil, dil
0x18085265d  jnz     loc_180853005
0x180852663  mov     rax, [rbx]
0x180852666  lea     rdx, [rbp+1F0h+var_258]
0x18085266a  mov     rcx, rbx
0x18085266d  mov     rax, [rax+0E8h]
0x180852674  call    cs:__guard_dispatch_icall_fptr
0x18085267a  nop
0x18085267b  mov     rcx, [rbp+1F0h+var_258]
0x18085267f  test    rcx, rcx
0x180852682  jz      short loc_1808526A4
0x180852684  mov     rax, [rcx]
0x180852687  mov     rax, [rax+18h]
0x18085268b  call    cs:__guard_dispatch_icall_fptr
0x180852691  mov     rdx, rax
0x180852694  mov     rcx, [rax]
0x180852697  mov     rax, [rcx+30h]
0x18085269b  mov     rcx, rdx
0x18085269e  call    cs:__guard_dispatch_icall_fptr
0x1808526a4  cmp     [rbx+1C8h], r15
0x1808526ab  jnz     loc_180852B7A
0x1808526b1  cmp     [rbx+1C0h], r15b
0x1808526b8  jz      loc_180852AFD
0x1808526be  mov     rax, [rbx]
0x1808526c1  xor     r8d, r8d
0x1808526c4  lea     rdx, [rbp+1F0h+var_90]
0x1808526cb  mov     rcx, rbx
0x1808526ce  mov     rax, [rax+70h]
0x1808526d2  call    cs:__guard_dispatch_icall_fptr
0x1808526d8  cmp     qword ptr [rax+18h], 7
0x1808526dd  jbe     short loc_1808526E2
0x1808526df  mov     rax, [rax]
0x1808526e2  mov     [rsp+2F0h+var_2B8], rsi
0x1808526e7  lea     rcx, IID_IStorage
0x1808526ee  mov     [rsp+2F0h+var_2C0], rcx
0x1808526f3  mov     [rsp+2F0h+var_2C8], r15
0x1808526f8  mov     [rsp+2F0h+var_2D0], r15
0x1808526fd  xor     r9d, r9d
0x180852700  lea     r8d, [r9+5]
0x180852704  mov     r14d, 1012h
0x18085270a  mov     edx, r14d
0x18085270d  mov     rcx, rax
0x180852710  call    cs:__imp_?MsoStgCreateStorageEx@@YAJPEB_WKKKPEAUtagSTGOPTIONS@@PEAXAEBU_GUID@@PEAPEAX@Z; MsoStgCreateStorageEx(wchar_t const *,ulong,ulong,ulong,tagSTGOPTIONS *,void *,_GUID const &,void * *)
0x180852716  mov     edi, eax
0x180852718  mov     rdx, [rbp+1F0h+var_78]
0x18085271f  cmp     rdx, 7
0x180852723  jbe     short loc_180852739
0x180852725  lea     rdx, ds:2[rdx*2]
0x18085272d  mov     rcx, [rbp+1F0h+var_90]
0x180852734  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180852739  test    edi, edi
0x18085273b  jns     short loc_180852789
0x18085273d  mov     r8d, edi
0x180852740  lea     rdx, aCreatefilefail; "CreateFileFailed"
0x180852747  lea     rcx, [rbp+1F0h+var_250]; this
0x18085274b  call    ??$Fail@V?$StringLiteral@D@StringLiterals@Mso@@$$V@Activity@Logging@Jot@@QEAAXV?$StringLiteral@D@StringLiterals@Mso@@K@Z; Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>(Mso::StringLiterals::StringLiteral<char>,ulong)
0x180852750  mov     rax, [rbx]
0x180852753  xor     r8d, r8d
0x180852756  lea     rdx, [rbp+1F0h+var_90]
0x18085275d  mov     rcx, rbx
0x180852760  mov     rax, [rax+70h]
0x180852764  call    cs:__guard_dispatch_icall_fptr
0x18085276a  nop
0x18085276b  cmp     qword ptr [rax+18h], 7
0x180852770  jbe     short loc_180852775
0x180852772  mov     rax, [rax]
0x180852775  mov     r8d, 1E14664Ah
0x18085277b  mov     rdx, rax
0x18085277e  mov     ecx, edi
0x180852780  call    ?ThrowHRESULTWithFilenameTag@Jot@@YAXJV?$String@UWzTraits@MsoCF@@@MsoCF@@K@Z; Jot::ThrowHRESULTWithFilenameTag(long,MsoCF::String<MsoCF::WzTraits>,ulong)
0x180852786  jmp     short $+2
0x180852788  nop
0x180852789  mov     [rbp+1F0h+var_268], r15
0x18085278d  mov     [rsp+2F0h+var_288], r15
0x180852792  mov     [rsp+2F0h+var_290], r15
0x180852797  mov     rcx, rsi
0x18085279a  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x18085279f  mov     r10, rax
0x1808527a2  mov     rcx, [rax]
0x1808527a5  mov     rax, [rcx+28h]
0x1808527a9  lea     rcx, [rbp+1F0h+var_268]
0x1808527ad  mov     [rsp+2F0h+var_2C8], rcx
0x1808527b2  mov     dword ptr [rsp+2F0h+var_2D0], r15d
0x1808527b7  xor     r9d, r9d
0x1808527ba  mov     r8d, r14d
0x1808527bd  lea     rdx, ?c_wzDataSpacesStg@@3QB_WB; wchar_t const near * const c_wzDataSpacesStg
0x1808527c4  mov     rcx, r10
0x1808527c7  call    cs:__guard_dispatch_icall_fptr
0x1808527cd  mov     edi, eax
0x1808527cf  test    eax, eax
0x1808527d1  jns     short loc_18085281F
0x1808527d3  mov     r8d, eax
0x1808527d6  lea     rdx, aCreatedataspac; "CreateDataSpacesStorageFailed"
0x1808527dd  lea     rcx, [rbp+1F0h+var_250]; this
0x1808527e1  call    ??$Fail@V?$StringLiteral@D@StringLiterals@Mso@@$$V@Activity@Logging@Jot@@QEAAXV?$StringLiteral@D@StringLiterals@Mso@@K@Z; Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>(Mso::StringLiterals::StringLiteral<char>,ulong)
0x1808527e6  mov     rcx, [rbx]
0x1808527e9  mov     rax, [rcx+70h]
0x1808527ed  xor     r8d, r8d
0x1808527f0  lea     rdx, [rbp+1F0h+var_90]
0x1808527f7  mov     rcx, rbx
0x1808527fa  call    cs:__guard_dispatch_icall_fptr
0x180852800  nop
0x180852801  cmp     qword ptr [rax+18h], 7
0x180852806  jbe     short loc_18085280B
0x180852808  mov     rax, [rax]
0x18085280b  mov     r8d, 1E146649h
0x180852811  mov     rdx, rax
0x180852814  mov     ecx, edi
0x180852816  call    ?ThrowHRESULTWithFilenameTag@Jot@@YAXJV?$String@UWzTraits@MsoCF@@@MsoCF@@K@Z; Jot::ThrowHRESULTWithFilenameTag(long,MsoCF::String<MsoCF::WzTraits>,ulong)
0x18085281c  jmp     short $+2
0x18085281e  nop
0x18085281f  mov     rcx, [rbp+1F0h+var_268]
0x180852823  test    rcx, rcx
0x180852826  jnz     short loc_180852836
0x180852828  xor     edx, edx
0x18085282a  mov     ecx, 1E3C3840h
0x18085282f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180852835  nop
0x180852836  mov     rax, [rcx]
0x180852839  lea     rdx, [rsp+2F0h+var_288]
0x18085283e  mov     [rsp+2F0h+var_2C8], rdx
0x180852843  mov     dword ptr [rsp+2F0h+var_2D0], r15d
0x180852848  xor     r9d, r9d
0x18085284b  mov     r8d, r14d
0x18085284e  lea     rdx, ?c_wzTransformInfoStg@@3QB_WB; "TransformInfo"
0x180852855  mov     rax, [rax+28h]
0x180852859  call    cs:__guard_dispatch_icall_fptr
0x18085285f  mov     edi, eax
0x180852861  test    eax, eax
0x180852863  jns     short loc_1808528B1
0x180852865  mov     r8d, eax
0x180852868  lea     rdx, aCreatetransfor; "CreateTransformInfoStorageFailed"
0x18085286f  lea     rcx, [rbp+1F0h+var_250]; this
0x180852873  call    ??$Fail@V?$StringLiteral@D@StringLiterals@Mso@@$$V@Activity@Logging@Jot@@QEAAXV?$StringLiteral@D@StringLiterals@Mso@@K@Z; Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>(Mso::StringLiterals::StringLiteral<char>,ulong)
0x180852878  mov     rcx, [rbx]
0x18085287b  mov     rax, [rcx+70h]
0x18085287f  xor     r8d, r8d
0x180852882  lea     rdx, [rbp+1F0h+var_90]
0x180852889  mov     rcx, rbx
0x18085288c  call    cs:__guard_dispatch_icall_fptr
0x180852892  nop
0x180852893  cmp     qword ptr [rax+18h], 7
0x180852898  jbe     short loc_18085289D
0x18085289a  mov     rax, [rax]
0x18085289d  mov     r8d, 1E146648h
0x1808528a3  mov     rdx, rax
0x1808528a6  mov     ecx, edi
0x1808528a8  call    ?ThrowHRESULTWithFilenameTag@Jot@@YAXJV?$String@UWzTraits@MsoCF@@@MsoCF@@K@Z; Jot::ThrowHRESULTWithFilenameTag(long,MsoCF::String<MsoCF::WzTraits>,ulong)
0x1808528ae  jmp     short $+2
0x1808528b0  nop
0x1808528b1  mov     rcx, [rsp+2F0h+var_288]
0x1808528b6  test    rcx, rcx
0x1808528b9  jnz     short loc_1808528C9
0x1808528bb  xor     edx, edx
0x1808528bd  mov     ecx, 1E3C3840h
0x1808528c2  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1808528c8  nop
0x1808528c9  mov     rax, [rcx]
0x1808528cc  lea     rdx, [rsp+2F0h+var_290]
0x1808528d1  mov     [rsp+2F0h+var_2C8], rdx
0x1808528d6  mov     dword ptr [rsp+2F0h+var_2D0], r15d
0x1808528db  xor     r9d, r9d
0x1808528de  mov     r8d, r14d
0x1808528e1  lea     rdx, ?c_wzDRMLabelInfoStm@@3QB_WB; "LabelInfo"
0x1808528e8  mov     rax, [rax+18h]
0x1808528ec  call    cs:__guard_dispatch_icall_fptr
0x1808528f2  mov     edi, eax
0x1808528f4  test    eax, eax
0x1808528f6  jns     short loc_180852949
0x1808528f8  mov     r8d, eax
0x1808528fb  lea     rdx, aCreatelabelinf; "CreateLabelInfoStreamFailed"
0x180852902  lea     rcx, [rbp+1F0h+var_250]; this
0x180852906  call    ??$Fail@V?$StringLiteral@D@StringLiterals@Mso@@$$V@Activity@Logging@Jot@@QEAAXV?$StringLiteral@D@StringLiterals@Mso@@K@Z; Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>(Mso::StringLiterals::StringLiteral<char>,ulong)
0x18085290b  mov     rcx, [rbx]
0x18085290e  mov     rax, [rcx+70h]
0x180852912  xor     r8d, r8d
0x180852915  lea     rdx, [rbp+1F0h+var_90]
0x18085291c  mov     rcx, rbx
0x18085291f  call    cs:__guard_dispatch_icall_fptr
0x180852925  nop
0x180852926  cmp     qword ptr [rax+18h], 7
0x18085292b  jbe     short loc_180852930
0x18085292d  mov     rax, [rax]
0x180852930  mov     r8d, 1E2035D9h
0x180852936  mov     rdx, rax
0x180852939  mov     ecx, edi
0x18085293b  call    ?ThrowHRESULTWithFilenameTag@Jot@@YAXJV?$String@UWzTraits@MsoCF@@@MsoCF@@K@Z; Jot::ThrowHRESULTWithFilenameTag(long,MsoCF::String<MsoCF::WzTraits>,ulong)
0x180852941  jmp     short loc_180852948
0x180852948  nop
0x180852949  mov     rdx, [rsp+2F0h+var_290]
0x18085294e  lea     rcx, [rsp+2F0h+var_280]
0x180852953  call    cs:__imp_?CreateMetadataParser@Xml@Clp@Mso@@YA?AV?$TCntPtr@UIMetadataParser@Xml@Clp@Mso@@@3@AEAUIStream@@@Z; Mso::Clp::Xml::CreateMetadataParser(IStream &)
0x180852959  mov     rcx, [rsp+2F0h+var_280]
0x18085295e  test    rcx, rcx
0x180852961  jnz     short loc_180852971
0x180852963  xor     edx, edx
0x180852965  mov     ecx, 1E3C3840h
0x18085296a  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180852970  nop
0x180852971  mov     rax, [rcx]
0x180852974  mov     rdx, [rbx+1D8h]
0x18085297b  mov     rax, [rax+30h]
0x18085297f  call    cs:__guard_dispatch_icall_fptr
0x180852985  test    al, al
0x180852987  jnz     short loc_1808529D8
0x180852989  xor     r8d, r8d
0x18085298c  lea     rdx, aWritelabelinfo; "WriteLabelInfoFailed"
0x180852993  lea     rcx, [rbp+1F0h+var_250]; this
0x180852997  call    ??$Fail@V?$StringLiteral@D@StringLiterals@Mso@@$$V@Activity@Logging@Jot@@QEAAXV?$StringLiteral@D@StringLiterals@Mso@@K@Z; Jot::Logging::Activity::Fail<Mso::StringLiterals::StringLiteral<char>,>(Mso::StringLiterals::StringLiteral<char>,ulong)
0x18085299c  mov     rax, [rbx]
0x18085299f  xor     r8d, r8d
0x1808529a2  lea     rdx, [rbp+1F0h+var_90]
0x1808529a9  mov     rcx, rbx
0x1808529ac  mov     rax, [rax+70h]
0x1808529b0  call    cs:__guard_dispatch_icall_fptr
0x1808529b6  nop
0x1808529b7  cmp     qword ptr [rax+18h], 7
0x1808529bc  jbe     short loc_1808529C1
0x1808529be  mov     rax, [rax]
0x1808529c1  mov     r8d, 1E2035D8h
0x1808529c7  mov     rdx, rax
0x1808529ca  mov     ecx, 80004005h
0x1808529cf  call    ?ThrowHRESULTWithFilenameTag@Jot@@YAXJV?$String@UWzTraits@MsoCF@@@MsoCF@@K@Z; Jot::ThrowHRESULTWithFilenameTag(long,MsoCF::String<MsoCF::WzTraits>,ulong)
0x1808529d5  jmp     short $+2
0x1808529d7  nop
0x1808529d8  mov     [rbp+1F0h+var_270], r15
0x1808529dc  mov     rcx, rsi
0x1808529df  call    ??C?$TCntPtr@VCOneNoteOM@OMUtils@Jot@@@Mso@@QEBAPEAVCOneNoteOM@OMUtils@Jot@@XZ; Mso::TCntPtr<Jot::OMUtils::COneNoteOM>::operator->(void)
0x1808529e4  mov     r10, rax
0x1808529e7  mov     rcx, [rax]
0x1808529ea  mov     rax, [rcx+18h]
0x1808529ee  lea     rcx, [rbp+1F0h+var_270]
0x1808529f2  mov     [rsp+2F0h+var_2C8], rcx
0x1808529f7  mov     dword ptr [rsp+2F0h+var_2D0], r15d
  ... truncated ...
```
