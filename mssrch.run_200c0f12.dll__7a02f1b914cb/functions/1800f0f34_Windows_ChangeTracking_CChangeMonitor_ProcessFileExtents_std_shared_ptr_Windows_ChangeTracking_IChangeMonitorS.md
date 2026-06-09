# Windows::ChangeTracking::CChangeMonitor::_ProcessFileExtents(std::shared_ptr<Windows::ChangeTracking::IChangeMonitorStore> const &,Windows::ChangeTracking::SChangeRoot const &,wchar_t const *,Windows::ChangeTracking::SWalkRecord &)

- ea: `0x1800f0f34`
- end: `0x1800f1a33`
- name: `?_ProcessFileExtents@CChangeMonitor@ChangeTracking@Windows@@AEAAXAEBV?$shared_ptr@UIChangeMonitorStore@ChangeTracking@Windows@@@std@@AEBUSChangeRoot@23@PEB_WAEAUSWalkRecord@23@@Z`
- size: `2815`
- prototype: `__int64 __usercall@<rax>(Windows::ChangeTracking::CChangeMonitor *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180091d40`

## callees

- `0x180012120`
- `0x18001b470`
- `0x180022710`
- `0x18005e788`
- `0x18006f8cc`
- `0x180092e8c`
- `0x180093708`
- `0x1800a3a38`
- `0x1800a718c`
- `0x1800b869c`
- `0x1800e1320`
- `0x1800f0ef0`
- `0x1800f0f34`
- `0x1800f1a3c`
- `0x1800f1b04`
- `0x1800f1b3c`
- `0x1800f1cb0`
- `0x1800f1d64`
- `0x1800f1e0c`
- `0x1800f1f58`
- `0x1800f20dc`
- `0x1800f2138`
- `0x180100de0`
- `0x18010338c`
- `0x18010ff58`
- `0x180123e88`
- `0x1801244c0`
- `0x18012540e`
- `0x180150684`
- `0x180150af0`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f134a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f134a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f13b7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f13b7`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800f14cd`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800f14cd`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800f1450`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800f1450`

## string_xrefs

- `0x1800f118c`: `Range Tracking: Dropping hashes for: %s (Removed:%s  JournalTracked:%s)`
- `0x1800f14a8`: `fCanAccessFile ? S_OK : HRESULT_FROM_WIN32(ERROR_OPEN_FAILED)`
- `0x1800f1469`: `fCanAccessFile ? S_OK : ResultFromLastError()`
- `0x1800f14e6`: `fCanAccessFile ? S_OK : ResultFromLastError()`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall Windows::ChangeTracking::CChangeMonitor::_ProcessFileExtents(
        Windows::ChangeTracking::CChangeMonitor *this,
        _QWORD *a2,
        _BYTE *a3,
        __int64 a4,
        __int64 a5)
{
  char v6; // cl
  __int64 v7; // rax
  __int64 v8; // rdx
  char v9; // r12
  int v10; // edi
  union _LARGE_INTEGER v11; // rax
  _QWORD *v12; // r15
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  _QWORD *v17; // r9
  __int64 v18; // rax
  _QWORD *v19; // r8
  _QWORD *v20; // rdx
  __int64 v21; // r8
  const wchar_t *v22; // rcx
  void *FileWrapper; // r12
  int Error; // edi
  const struct Windows::ChangeTracking::SChangeRoot *v25; // r12
  const WCHAR *v26; // rcx
  int v27; // eax
  HANDLE v28; // rdi
  char v29; // di
  int v30; // eax
  bool v31; // di
  char v32; // di
  int v33; // eax
  unsigned int v34; // eax
  unsigned __int64 QuadPart; // rcx
  char v36; // di
  _QWORD *v37; // rdx
  _QWORD *v38; // rdx
  unsigned int v39; // eax
  __int64 v40; // rdx
  const wchar_t *v41; // r9
  const wchar_t *v42; // r8
  _QWORD *v43; // rbx
  __int64 *v44; // rcx
  __int64 v45; // rax
  _QWORD *i; // rax
  _QWORD *v47; // rbx
  union _LARGE_INTEGER v48; // rdx
  __int64 v49; // rcx
  _QWORD *j; // rbx
  char v51; // [rsp+40h] [rbp-C0h]
  char v52; // [rsp+41h] [rbp-BFh] BYREF
  char v53; // [rsp+42h] [rbp-BEh]
  HANDLE hDevice; // [rsp+48h] [rbp-B8h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-B0h] BYREF
  union _LARGE_INTEGER v56; // [rsp+58h] [rbp-A8h] BYREF
  union _LARGE_INTEGER v57; // [rsp+60h] [rbp-A0h]
  union _LARGE_INTEGER v58; // [rsp+68h] [rbp-98h]
  _QWORD *v59; // [rsp+70h] [rbp-90h]
  __int64 InBuffer; // [rsp+78h] [rbp-88h] BYREF
  __int16 v61; // [rsp+80h] [rbp-80h] BYREF
  char v62; // [rsp+82h] [rbp-7Eh]
  _QWORD *v63; // [rsp+88h] [rbp-78h]
  DWORD BytesReturned[4]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v65; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v66; // [rsp+A8h] [rbp-58h]
  __int64 v67; // [rsp+B0h] [rbp-50h]
  __int64 v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+C0h] [rbp-40h]
  _BYTE v70[24]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v71[88]; // [rsp+E0h] [rbp-20h] BYREF
  char v72; // [rsp+138h] [rbp+38h]
  __int64 v73; // [rsp+140h] [rbp+40h]
  unsigned __int8 v74; // [rsp+148h] [rbp+48h]
  __int64 v75; // [rsp+168h] [rbp+68h]
  int v76; // [rsp+170h] [rbp+70h]
  _BYTE v77[88]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v78; // [rsp+248h] [rbp+148h]
  __int64 v79; // [rsp+250h] [rbp+150h]
  unsigned __int8 v80; // [rsp+258h] [rbp+158h]
  __int64 v81; // [rsp+278h] [rbp+178h]
  unsigned int v82; // [rsp+280h] [rbp+180h]
  LPCWSTR lpFileName[3]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int64 v84; // [rsp+318h] [rbp+218h]
  _QWORD v85[7]; // [rsp+320h] [rbp+220h] BYREF
  _QWORD *v86; // [rsp+358h] [rbp+258h]
  _QWORD v87[7]; // [rsp+360h] [rbp+260h] BYREF
  _QWORD *v88; // [rsp+398h] [rbp+298h]
  _QWORD v89[8]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _QWORD pv[2]; // [rsp+3E0h] [rbp+2E0h] BYREF
  __m128i si128; // [rsp+3F0h] [rbp+2F0h]
  int v92; // [rsp+400h] [rbp+300h]
  __int64 v93; // [rsp+408h] [rbp+308h]
  __int128 v94; // [rsp+410h] [rbp+310h]
  __int128 v95; // [rsp+420h] [rbp+320h]
  __int64 v96; // [rsp+430h] [rbp+330h]
  int v97; // [rsp+438h] [rbp+338h]
  int v98; // [rsp+43Ch] [rbp+33Ch]
  int v99; // [rsp+440h] [rbp+340h]
  __int64 v100; // [rsp+448h] [rbp+348h]
  __int128 v101; // [rsp+450h] [rbp+350h]
  __int128 v102; // [rsp+460h] [rbp+360h]
  __int64 v103; // [rsp+4D0h] [rbp+3D0h]
  __int16 v104; // [rsp+4D8h] [rbp+3D8h]
  _BYTE OutBuffer[24]; // [rsp+4F0h] [rbp+3F0h] BYREF
  __int64 v106; // [rsp+508h] [rbp+408h]

  InBuffer = a4;
  hDevice = a3;
  v59 = a2;
  v6 = a3[36];
  if ( (v6 & 6) == 0 )
    return;
  if ( (v6 & 0x20) != 0 )
  {
    Windows::ChangeTracking::CChangeMonitor::_SignalChange(this, (struct Windows::ChangeTracking::SChangeRoot *)a3);
    return;
  }
  if ( (v6 & 2) == 0 || (*(_BYTE *)a5 & 8) == 0 )
  {
    v53 = 0;
LABEL_12:
    v51 = 0;
    goto LABEL_13;
  }
  v53 = 1;
  v7 = *(_QWORD *)(a5 + 224);
  v8 = *(_QWORD *)(a5 + 216);
  if ( v8 != v7 && (unsigned __int64)((v7 - v8) >> 4) <= 1 && *(__int64 *)(*(_QWORD *)(a5 + 224) - 16LL) <= 0 )
    goto LABEL_12;
  v51 = 1;
LABEL_13:
  if ( !*(_BYTE *)(a5 + 4) || (v9 = 1, *(_DWORD *)(a5 + 56)) )
    v9 = 0;
  v10 = *(_DWORD *)(a5 + 56) & 0x2107;
  v11.QuadPart = 0;
  FileSize.QuadPart = 0;
  if ( !v9 && !v10 || (v6 & 4) == 0 )
    goto LABEL_113;
  Windows::ChangeTracking::SChangeRecordValue::SChangeRecordValue((Windows::ChangeTracking::SChangeRecordValue *)v77);
  Windows::ChangeTracking::SChangeRecordValue::SChangeRecordValue((Windows::ChangeTracking::SChangeRecordValue *)v71);
  *(_QWORD *)BytesReturned = (char *)this + 24;
  CSRWLock::AcquireExclusive((Windows::ChangeTracking::CChangeMonitor *)((char *)this + 24));
  v12 = (_QWORD *)(a5 + 120);
  v13 = (_QWORD *)(a5 + 120);
  if ( *(_QWORD *)(a5 + 144) > 7u )
    v13 = (_QWORD *)*v12;
  v61 = *(_WORD *)hDevice | 0x4000;
  v62 = 1;
  v63 = v13;
  Windows::ChangeTracking::CStoreTransaction::CStoreTransaction(&v56, v59);
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int16 *, _QWORD))(*(_QWORD *)*v59 + 40LL))(*v59, &v61, 0) )
  {
    if ( v9 || v51 )
    {
      v62 = 2;
      Windows::ChangeTracking::SChangeRecordValue::SChangeRecordValue((Windows::ChangeTracking::SChangeRecordValue *)pv);
      LOBYTE(v97) = 4;
      (*(void (__fastcall **)(_QWORD, __int16 *, _QWORD *))(*(_QWORD *)*v59 + 72LL))(*v59, &v61, pv);
      if ( *(_QWORD *)(a5 + 144) <= 7u )
        v19 = (_QWORD *)(a5 + 120);
      else
        v19 = (_QWORD *)*v12;
      Windows::ChangeTracking::CChangeMonitor::_LogMessage(
        this,
        L"Range Tracking: Dropping hashes for: %s (Removed:%s  JournalTracked:%s)",
        v19);
      Windows::ChangeTracking::SChangeRecordValue::~SChangeRecordValue((Windows::ChangeTracking::SChangeRecordValue *)pv);
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, _QWORD, _BYTE *))(*(_QWORD *)*v59 + 48LL))(*v59, 0, v77);
      v17 = (_QWORD *)(a5 + 120);
      if ( *(_QWORD *)(a5 + 144) > 7u )
        v17 = (_QWORD *)*v12;
      LOBYTE(v15) = v78;
      v18 = Windows::ChangeTracking::Logging::ExtentKindLog(v15, v14, v16, v17);
      Windows::ChangeTracking::CChangeMonitor::_LogMessage(
        this,
        L"Range Tracking: Found hashes for (extentKind: %s): %s",
        v18);
    }
  }
  Windows::ChangeTracking::CStoreTransaction::Commit((Windows::ChangeTracking::CStoreTransaction *)&v56);
  Windows::ChangeTracking::CStoreTransaction::~CStoreTransaction((Windows::ChangeTracking::CStoreTransaction *)&v56);
  Microsoft::WRL::Wrappers::Details::SyncLockExclusive::~SyncLockExclusive((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)BytesReturned);
  if ( v10 && !v9 && !v51 )
  {
    v65 = 0;
    v66 = 0;
    v67 = 0;
    v68 = 0;
    v69 = 3;
    std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(v70);
    std::wstring::wstring(lpFileName, InBuffer);
    if ( *(_QWORD *)(a5 + 144) <= 7u )
      v20 = (_QWORD *)(a5 + 120);
    else
      v20 = (_QWORD *)*v12;
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)v20 + v21) );
    std::wstring::_Append<wchar_t>(lpFileName);
    v52 = 1;
    pv[0] = &COplockProvider::`vftable';
    pv[1] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v100 = 0;
    v103 = 0;
    v104 = 0;
    v101 = 0;
    v102 = 0;
    v92 = 3;
    v93 = 0;
    v94 = 0;
    v95 = 0;
    v96 = 0;
    v98 = 1;
    v99 = 72;
    v97 = 1;
    v89[0] = &std::_Func_impl_no_alloc<_lambda_f95aa8065ccec292900f2d8ee65d83de_,void,>::`vftable';
    v89[1] = &v52;
    v89[7] = v89;
    v22 = (const wchar_t *)lpFileName;
    if ( v84 > 7 )
      v22 = lpFileName[0];
    FileWrapper = NtCreateFileWrapper(v22);
    if ( FileWrapper != (void *)-1LL || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      Error = COplockProvider::RequestOplockOnHandle(pv, FileWrapper);
      CloseHandle(FileWrapper);
    }
    std::function<unsigned long (PolicyParameters)>::~function<unsigned long (PolicyParameters)>(v89);
    v25 = (const struct Windows::ChangeTracking::SChangeRoot *)hDevice;
    Windows::ChangeTracking::CChangeMonitor::_ThrowIfFastFail(
      this,
      (const struct Windows::ChangeTracking::SChangeRoot *)hDevice,
      Error,
      L"hrRequestOplock");
    if ( Error < 0 )
    {
LABEL_101:
      if ( v51 || !v67 )
      {
        v72 = 4;
      }
      else if ( !v69 && !v80 )
      {
LABEL_111:
        COplockProvider::~COplockProvider((COplockProvider *)pv);
        ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)lpFileName);
        Windows::ChangeTracking::DiffContext::~DiffContext((Windows::ChangeTracking::DiffContext *)&v65);
        goto LABEL_112;
      }
      if ( !*((_BYTE *)v25 + 192) )
      {
        hDevice = (char *)this + 24;
        CSRWLock::AcquireExclusive((Windows::ChangeTracking::CChangeMonitor *)((char *)this + 24));
        if ( *(_QWORD *)(a5 + 144) > 7u )
          v12 = (_QWORD *)*v12;
        v61 = *(_WORD *)v25 | 0x4000;
        v62 = 2;
        v63 = v12;
        v43 = v59;
        Windows::ChangeTracking::CStoreTransaction::CStoreTransaction(&v56, v59);
        (*(void (__fastcall **)(_QWORD, __int16 *, _BYTE *))(*(_QWORD *)*v43 + 72LL))(*v43, &v61, v71);
        Windows::ChangeTracking::CStoreTransaction::Commit((Windows::ChangeTracking::CStoreTransaction *)&v56);
        Windows::ChangeTracking::CStoreTransaction::~CStoreTransaction((Windows::ChangeTracking::CStoreTransaction *)&v56);
        Microsoft::WRL::Wrappers::Details::SyncLockExclusive::~SyncLockExclusive((Microsoft::WRL::Wrappers::Details::SyncLockExclusive *)&hDevice);
      }
      goto LABEL_111;
    }
    v26 = (const WCHAR *)lpFileName;
    if ( v84 > 7 )
      v26 = lpFileName[0];
    hDevice = CreateFileW(v26, 0x80000000, 5u, 0, 3u, 0x80u, 0);
    if ( (char *)hDevice - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      v27 = ResultFromLastError();
    else
      v27 = 0;
    Windows::ChangeTracking::CChangeMonitor::_ThrowIfFastFail(this, v25, v27, L"hFile ? S_OK : ResultFromLastError()");
    v28 = hDevice;
    if ( (char *)hDevice - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      goto LABEL_100;
    memset_0(OutBuffer, 0, 0x248u);
    LODWORD(InBuffer) = 131074;
    BytesReturned[0] = 0;
    if ( DeviceIoControl(v28, 0x900EBu, &InBuffer, 4u, OutBuffer, 0x248u, BytesReturned, 0) )
    {
      v29 = 1;
      v30 = 0;
    }
    else
    {
      v29 = 0;
      v30 = ResultFromLastError();
    }
    if ( (Windows::ChangeTracking::CChangeMonitor::_ThrowIfFastFail(
            this,
            v25,
            v30,
            L"fCanAccessFile ? S_OK : ResultFromLastError()"),
          !v29)
      || (v31 = v106 == *(_QWORD *)(a5 + 16),
          Windows::ChangeTracking::CChangeMonitor::_ThrowIfFastFail(
            this,
            v25,
            v106 != *(_QWORD *)(a5 + 16) ? 0x8007006E : 0,
            L"fCanAccessFile ? S_OK : HRESULT_FROM_WIN32(ERROR_OPEN_FAILED)"),
          !v31)
      || (!GetFileSizeEx(hDevice, &FileSize) ? (v32 = 0, v33 = ResultFromLastError()) : (v32 = 1, v33 = 0),
          Windows::ChangeTracking::CChangeMonitor::_ThrowIfFastFail(
            this,
            v25,
            v33,
            L"fCanAccessFile ? S_OK : ResultFromLastError()"),
          !v32) )
    {
LABEL_100:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hDevice);
      goto LABEL_101;
    }
    if ( v53 && *(_QWORD *)(*(_QWORD *)(a5 + 224) - 8LL) <= FileSize.QuadPart )
    {
      v51 = 1;
      goto LABEL_100;
    }
    v34 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 18) + 8LL))(*((_QWORD *)this + 18));
    QuadPart = FileSize.QuadPart;
    if ( FileSize.QuadPart >= v34 )
    {
      v36 = 0;
      if ( v78 != 3 )
        goto LABEL_71;
    }
    else
    {
      v36 = 1;
      if ( v78 != 2 )
        goto LABEL_68;
    }
    v66 = v81;
    v65 = v82;
    *(_QWORD *)(a5 + 264) = v79;
    if ( v36 )
    {
LABEL_68:
      v85[0] = &std::_Func_impl_no_alloc<_lambda_e4d42c4e6fc1bf0d7be81e77d21b7150_,bool,unsigned __int64,unsigned __int64 *,unsigned char *>::`vftable';
      v85[1] = &hDevice;
      v85[2] = this;
      v85[3] = v25;
      v85[4] = &v52;
      v86 = v85;
      Windows::ChangeTracking::CalculateDiffFromSingleHash(QuadPart, v85, &v65);
      if ( v86 )
      {
        v37 = v85;
        LOBYTE(v37) = v86 != v85;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v86 + 32LL))(v86, v37);
      }
      v72 = 2;
      goto LABEL_74;
    }
LABEL_71:
    v87[0] = &std::_Func_impl_no_alloc<_lambda_e4d42c4e6fc1bf0d7be81e77d21b7150_,bool,unsigned __int64,unsigned __int64 *,unsigned char *>::`vftable';
    v87[1] = &hDevice;
    v87[2] = this;
    v87[3] = v25;
    v87[4] = &v52;
    v88 = v87;
    Windows::ChangeTracking::CalculateDiffFromMultipleHashes(QuadPart);
    if ( v88 )
    {
      v38 = v87;
      LOBYTE(v38) = v88 != v87;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v88 + 32LL))(v88, v38);
    }
    v72 = 3;
LABEL_74:
    if ( v67 )
    {
      v75 = v67;
      v76 = v68;
      v73 = *(_QWORD *)(a5 + 16);
      if ( v69 )
      {
        if ( v69 != 1 )
        {
          if ( v69 == 2 )
          {
            v74 = v80 + 1;
            v39 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 18) + 16LL))(*((_QWORD *)this + 18));
            if ( v74 >= v39 )
              v72 = 1;
          }
          else if ( v69 == 3 )
          {
            v74 = v80;
          }
          goto LABEL_85;
        }
        std::vector<Windows::ChangeTracking::SUnchangedRange>::operator=(a5 + 240, v70);
      }
      else
      {
        v56.QuadPart = 0;
        v57 = FileSize;
        v58.QuadPart = 0;
        std::vector<Windows::ChangeTracking::SUnchangedRange>::push_back(a5 + 240, &v56);
      }
      v74 = 0;
    }
LABEL_85:
    if ( *(_QWORD *)(a5 + 144) <= 7u )
      v40 = a5 + 120;
    else
      v40 = *v12;
    v41 = L"Single";
    if ( !v36 )
      v41 = L"Multiple";
    if ( v69 )
    {
      switch ( v69 )
      {
        case 1:
          v42 = L"PartiallyChanged";
          break;
        case 2:
          v42 = L"FullyChanged";
          break;
        case 3:
          v42 = L"Unknown";
          break;
        default:
          v42 = (const wchar_t *)&cchOriginalDestLength;
          break;
      }
    }
    else
    {
      v42 = L"Identical";
    }
    Windows::ChangeTracking::CChangeMonitor::_LogMessage(
      this,
      L"Range Tracking: Hashes calculated (ChangeKind: %s, Kind: %s): %s",
      v42,
      v41,
      v40);
    goto LABEL_100;
  }
LABEL_112:
  Windows::ChangeTracking::SChangeRecordValue::~SChangeRecordValue((Windows::ChangeTracking::SChangeRecordValue *)v71);
  Windows::ChangeTracking::SChangeRecordValue::~SChangeRecordValue((Windows::ChangeTracking::SChangeRecordValue *)v77);
  v11 = FileSize;
LABEL_113:
  if ( v51 || v53 && *(_QWORD *)(a5 + 240) == *(_QWORD *)(a5 + 248) )
  {
    v44 = *(__int64 **)(a5 + 216);
    if ( v44 != *(__int64 **)(a5 + 224) )
    {
      v45 = *v44;
      if ( *v44 > 0 )
      {
        v56.QuadPart = 0;
        v57.QuadPart = v45;
        v58.QuadPart = 0;
        std::vector<Windows::ChangeTracking::SUnchangedRange>::push_back(a5 + 240, &v56);
      }
      for ( i = *(_QWORD **)(a5 + 216); ; i = v47 )
      {
        v47 = i + 2;
        if ( i + 2 == *(_QWORD **)(a5 + 224) )
          break;
        v56.QuadPart = *i + i[1];
        v57.QuadPart = *v47 - v56.QuadPart;
        v58 = v56;
        std::vector<Windows::ChangeTracking::SUnchangedRange>::push_back(a5 + 240, &v56);
      }
      v11 = FileSize;
    }
    if ( !v11.QuadPart )
    {
      v11.QuadPart = 0x7FFFFFFFFFFFFFFFLL;
      FileSize.QuadPart = 0x7FFFFFFFFFFFFFFFLL;
    }
    v48.QuadPart = 0;
    v49 = *(_QWORD *)(a5 + 224);
    if ( *(_QWORD *)(a5 + 216) != v49 )
      v48.QuadPart = *(_QWORD *)(v49 - 8) + *(_QWORD *)(v49 - 16);
    if ( v48.QuadPart < (unsigned __int64)v11.QuadPart )
    {
      v56 = v48;
      v57.QuadPart = v11.QuadPart - v48.QuadPart;
      v58 = v48;
      std::vector<Windows::ChangeTracking::SUnchangedRange>::push_back(a5 + 240, &v56);
    }
  }
  *(_DWORD *)a5 = *(_DWORD *)a5 & 0xFFFFFFF7 | (*(_QWORD *)(a5 + 248) != *(_QWORD *)(a5 + 240) ? 8 : 0);
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 18) + 24LL))(*((_QWORD *)this + 18))
    && (*(_BYTE *)a5 & 8) != 0 )
  {
    Windows::ChangeTracking::CChangeMonitor::_LogMessage(this, L"UR for: %s");
    for ( j = *(_QWORD **)(a5 + 240); j != *(_QWORD **)(a5 + 248); j += 3 )
      Windows::ChangeTracking::CChangeMonitor::_LogMessage(
        this,
        L"UR: Offset: %I64d   Size: %I64d   NewOffset: %I64d",
        *j,
        j[1],
        j[2]);
  }
}

```

## disassembly

```asm
0x1800f0f34  push    rbp
0x1800f0f36  push    rbx
0x1800f0f37  push    rsi
0x1800f0f38  push    rdi
0x1800f0f39  push    r12
0x1800f0f3b  push    r13
0x1800f0f3d  push    r14
0x1800f0f3f  push    r15
0x1800f0f41  lea     rbp, [rsp-658h]
0x1800f0f49  sub     rsp, 758h
0x1800f0f50  mov     rax, cs:__security_cookie
0x1800f0f57  xor     rax, rsp
0x1800f0f5a  mov     [rbp+690h+var_50], rax
0x1800f0f61  mov     [rsp+790h+InBuffer], r9
0x1800f0f66  mov     rax, r8
0x1800f0f69  mov     [rsp+790h+hDevice], rax
0x1800f0f6e  mov     [rsp+790h+var_720], rdx
0x1800f0f73  mov     r13, rcx
0x1800f0f76  mov     r14, [rbp+690h+arg_20]
0x1800f0f7d  mov     cl, [r8+24h]
0x1800f0f81  test    cl, 6
0x1800f0f84  jz      short loc_1800F0F96
0x1800f0f86  test    cl, 20h
0x1800f0f89  jz      short loc_1800F0FB9
0x1800f0f8b  mov     rdx, rax; struct Windows::ChangeTracking::SChangeRoot *
0x1800f0f8e  mov     rcx, r13; this
0x1800f0f91  call    ?_SignalChange@CChangeMonitor@ChangeTracking@Windows@@AEAAXAEAUSChangeRoot@23@@Z; Windows::ChangeTracking::CChangeMonitor::_SignalChange(Windows::ChangeTracking::SChangeRoot &)
0x1800f0f96  mov     rcx, [rbp+690h+var_50]
0x1800f0f9d  xor     rcx, rsp; StackCookie
0x1800f0fa0  call    __security_check_cookie
0x1800f0fa5  add     rsp, 758h
0x1800f0fac  pop     r15
0x1800f0fae  pop     r14
0x1800f0fb0  pop     r13
0x1800f0fb2  pop     r12
0x1800f0fb4  pop     rdi
0x1800f0fb5  pop     rsi
0x1800f0fb6  pop     rbx
0x1800f0fb7  pop     rbp
0x1800f0fb8  retn
0x1800f0fb9  test    cl, 2
0x1800f0fbc  jz      short loc_1800F0FFF
0x1800f0fbe  test    byte ptr [r14], 8
0x1800f0fc2  jz      short loc_1800F0FFF
0x1800f0fc4  mov     [rsp+790h+var_74E], 1
0x1800f0fc9  mov     rax, [r14+0E0h]
0x1800f0fd0  mov     rdx, [r14+0D8h]
0x1800f0fd7  xor     esi, esi
0x1800f0fd9  cmp     rdx, rax
0x1800f0fdc  jz      short loc_1800F0FF8
0x1800f0fde  sub     rax, rdx
0x1800f0fe1  sar     rax, 4
0x1800f0fe5  cmp     rax, 1
0x1800f0fe9  ja      short loc_1800F0FF8
0x1800f0feb  mov     rax, [r14+0E0h]
0x1800f0ff2  cmp     [rax-10h], rsi
0x1800f0ff6  jle     short loc_1800F1006
0x1800f0ff8  mov     [rsp+790h+var_750], 1
0x1800f0ffd  jmp     short loc_1800F100B
0x1800f0fff  xor     esi, esi
0x1800f1001  mov     [rsp+790h+var_74E], sil
0x1800f1006  mov     [rsp+790h+var_750], sil
0x1800f100b  mov     edi, [r14+38h]
0x1800f100f  cmp     [r14+4], sil
0x1800f1013  jz      short loc_1800F101C
0x1800f1015  test    edi, edi
0x1800f1017  mov     r12b, 1
0x1800f101a  jz      short loc_1800F101F
0x1800f101c  mov     r12b, sil
0x1800f101f  and     edi, 2107h
0x1800f1025  mov     rax, rsi
0x1800f1028  mov     qword ptr [rsp+790h+FileSize], rax
0x1800f102d  test    r12b, r12b
0x1800f1030  jnz     short loc_1800F103A
0x1800f1032  test    edi, edi
0x1800f1034  jz      loc_1800F1897
0x1800f103a  test    cl, 4
0x1800f103d  jz      loc_1800F1897
0x1800f1043  lea     rcx, [rbp+690h+var_5A0]; this
0x1800f104a  call    ??0SChangeRecordValue@ChangeTracking@Windows@@QEAA@XZ; Windows::ChangeTracking::SChangeRecordValue::SChangeRecordValue(void)
0x1800f104f  nop
0x1800f1050  lea     rcx, [rbp+690h+var_6B0]; this
0x1800f1054  call    ??0SChangeRecordValue@ChangeTracking@Windows@@QEAA@XZ; Windows::ChangeTracking::SChangeRecordValue::SChangeRecordValue(void)
0x1800f1059  nop
0x1800f105a  lea     rbx, [r13+18h]
0x1800f105e  mov     qword ptr [rbp+690h+BytesReturned], rbx
0x1800f1062  mov     rcx, rbx; this
0x1800f1065  call    ?AcquireExclusive@CSRWLock@@QEAAXXZ; CSRWLock::AcquireExclusive(void)
0x1800f106a  nop
0x1800f106b  lea     r15, [r14+78h]
0x1800f106f  mov     rcx, r15
0x1800f1072  cmp     qword ptr [r15+18h], 7
0x1800f1077  jbe     short loc_1800F107C
0x1800f1079  mov     rcx, [r15]
0x1800f107c  mov     eax, 4000h
0x1800f1081  mov     rdx, [rsp+790h+hDevice]
0x1800f1086  or      ax, [rdx]
0x1800f1089  mov     [rbp+690h+var_710], ax
0x1800f108d  mov     [rbp+690h+var_70E], 1
0x1800f1091  mov     [rbp+690h+var_708], rcx
0x1800f1095  mov     rdx, [rsp+790h+var_720]
0x1800f109a  lea     rcx, [rsp+790h+var_738]
0x1800f109f  call    ??0CStoreTransaction@ChangeTracking@Windows@@QEAA@AEBV?$shared_ptr@UIChangeMonitorStore@ChangeTracking@Windows@@@std@@@Z; Windows::ChangeTracking::CStoreTransaction::CStoreTransaction(std::shared_ptr<Windows::ChangeTracking::IChangeMonitorStore> const &)
0x1800f10a4  nop
0x1800f10a5  mov     rax, [rsp+790h+var_720]
0x1800f10aa  mov     rcx, [rax]
0x1800f10ad  mov     rax, [rcx]
0x1800f10b0  xor     r8d, r8d
0x1800f10b3  lea     rdx, [rbp+690h+var_710]
0x1800f10b7  mov     rax, [rax+28h]
0x1800f10bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f10c0  test    al, al
0x1800f10c2  jz      loc_1800F11A8
0x1800f10c8  test    r12b, r12b
0x1800f10cb  jnz     short loc_1800F1120
0x1800f10cd  cmp     [rsp+790h+var_750], sil
0x1800f10d2  jnz     short loc_1800F1120
0x1800f10d4  mov     rax, [rsp+790h+var_720]
0x1800f10d9  mov     rcx, [rax]
0x1800f10dc  mov     rax, [rcx]
0x1800f10df  lea     r8, [rbp+690h+var_5A0]
0x1800f10e6  xor     edx, edx
0x1800f10e8  mov     rax, [rax+30h]
0x1800f10ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f10f1  mov     r9, r15
0x1800f10f4  cmp     qword ptr [r15+18h], 7
0x1800f10f9  jbe     short loc_1800F10FE
0x1800f10fb  mov     r9, [r15]
0x1800f10fe  mov     cl, [rbp+690h+var_548]
0x1800f1104  call    ?ExtentKindLog@Logging@ChangeTracking@Windows@@YAPEB_WW4ExtentKind@23@@Z; Windows::ChangeTracking::Logging::ExtentKindLog(Windows::ChangeTracking::ExtentKind)
0x1800f1109  mov     r8, rax
0x1800f110c  lea     rdx, aRangeTrackingF; "Range Tracking: Found hashes for (exten"...
0x1800f1113  mov     rcx, r13; this
0x1800f1116  call    ?_LogMessage@CChangeMonitor@ChangeTracking@Windows@@AEAAXPEB_WZZ; Windows::ChangeTracking::CChangeMonitor::_LogMessage(wchar_t const *,...)
0x1800f111b  jmp     loc_1800F11A8
0x1800f1120  mov     [rbp+690h+var_70E], 2
0x1800f1124  lea     rcx, [rbp+690h+pv]; this
0x1800f112b  call    ??0SChangeRecordValue@ChangeTracking@Windows@@QEAA@XZ; Windows::ChangeTracking::SChangeRecordValue::SChangeRecordValue(void)
0x1800f1130  nop
0x1800f1131  mov     byte ptr [rbp+690h+var_358], 4
0x1800f1138  mov     rax, [rsp+790h+var_720]
0x1800f113d  mov     rcx, [rax]
0x1800f1140  mov     rax, [rcx]
0x1800f1143  lea     r8, [rbp+690h+pv]
0x1800f114a  lea     rdx, [rbp+690h+var_710]
0x1800f114e  mov     rax, [rax+48h]
0x1800f1152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1157  lea     rcx, aFalse; "false"
0x1800f115e  lea     r9, aTrue; "true"
0x1800f1165  mov     rax, r9
0x1800f1168  cmp     [rsp+790h+var_750], sil
0x1800f116d  cmovz   rax, rcx
0x1800f1171  test    r12b, r12b
0x1800f1174  cmovz   r9, rcx
0x1800f1178  cmp     qword ptr [r15+18h], 7
0x1800f117d  jbe     short loc_1800F1184
0x1800f117f  mov     r8, [r15]
0x1800f1182  jmp     short loc_1800F1187
0x1800f1184  mov     r8, r15
0x1800f1187  mov     qword ptr [rsp+790h+dwCreationDisposition], rax
0x1800f118c  lea     rdx, aRangeTrackingD; "Range Tracking: Dropping hashes for: %s"...
0x1800f1193  mov     rcx, r13; this
0x1800f1196  call    ?_LogMessage@CChangeMonitor@ChangeTracking@Windows@@AEAAXPEB_WZZ; Windows::ChangeTracking::CChangeMonitor::_LogMessage(wchar_t const *,...)
0x1800f119b  nop
0x1800f119c  lea     rcx, [rbp+690h+pv]; this
0x1800f11a3  call    ??1SChangeRecordValue@ChangeTracking@Windows@@QEAA@XZ; Windows::ChangeTracking::SChangeRecordValue::~SChangeRecordValue(void)
0x1800f11a8  lea     rcx, [rsp+790h+var_738]; this
0x1800f11ad  call    ?Commit@CStoreTransaction@ChangeTracking@Windows@@QEAAXXZ; Windows::ChangeTracking::CStoreTransaction::Commit(void)
0x1800f11b2  nop
0x1800f11b3  lea     rcx, [rsp+790h+var_738]; this
0x1800f11b8  call    ??1CStoreTransaction@ChangeTracking@Windows@@QEAA@XZ; Windows::ChangeTracking::CStoreTransaction::~CStoreTransaction(void)
0x1800f11bd  nop
0x1800f11be  lea     rcx, [rbp+690h+BytesReturned]; this
0x1800f11c2  call    ??1SyncLockExclusive@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockExclusive::~SyncLockExclusive(void)
0x1800f11c7  test    edi, edi
0x1800f11c9  jz      loc_1800F187C
0x1800f11cf  test    r12b, r12b
0x1800f11d2  jnz     loc_1800F187C
0x1800f11d8  cmp     [rsp+790h+var_750], sil
0x1800f11dd  jnz     loc_1800F187C
0x1800f11e3  mov     [rbp+690h+var_6F0], rsi
0x1800f11e7  mov     [rbp+690h+var_6E8], rsi
0x1800f11eb  mov     [rbp+690h+var_6E0], rsi
0x1800f11ef  mov     [rbp+690h+var_6D8], rsi
0x1800f11f3  mov     edi, 3
0x1800f11f8  mov     [rbp+690h+var_6D0], edi
0x1800f11fb  lea     rcx, [rbp+690h+var_6C8]; void *
0x1800f11ff  call    ??0?$vector@Uunique_ptr_bytes_buffer@@V?$allocator@Uunique_ptr_bytes_buffer@@@std@@@std@@QEAA@XZ; std::vector<unique_ptr_bytes_buffer>::vector<unique_ptr_bytes_buffer>(void)
0x1800f1204  nop
0x1800f1205  mov     rdx, [rsp+790h+InBuffer]
0x1800f120a  lea     rcx, [rbp+690h+lpFileName]
0x1800f1211  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800f1216  nop
0x1800f1217  cmp     qword ptr [r15+18h], 7
0x1800f121c  jbe     short loc_1800F1223
0x1800f121e  mov     rdx, [r15]
0x1800f1221  jmp     short loc_1800F1226
0x1800f1223  mov     rdx, r15
0x1800f1226  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800f122a  inc     r8
0x1800f122d  cmp     [rdx+r8*2], si
0x1800f1232  jnz     short loc_1800F122A
0x1800f1234  lea     rcx, [rbp+690h+lpFileName]; Src
0x1800f123b  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x1800f1240  mov     [rsp+790h+var_74F], 1
0x1800f1245  lea     rax, ??_7COplockProvider@@6B@; const COplockProvider::`vftable'
0x1800f124c  mov     [rbp+690h+pv], rax
0x1800f1253  mov     [rbp+690h+var_3A8], rsi
0x1800f125a  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x1800f1262  movdqa  [rbp+690h+var_3A0], xmm0
0x1800f126a  mov     [rbp+690h+var_348], rsi
0x1800f1271  mov     [rbp+690h+var_2C0], rsi
0x1800f1278  mov     [rbp+690h+var_2B8], 0
0x1800f1281  xorps   xmm0, xmm0
0x1800f1284  movups  [rbp+690h+var_340], xmm0
0x1800f128b  movups  [rbp+690h+var_330], xmm0
0x1800f1292  mov     [rbp+690h+var_390], edi
0x1800f1298  mov     [rbp+690h+var_388], rsi
0x1800f129f  movdqa  [rbp+690h+var_380], xmm0
0x1800f12a7  xorps   xmm1, xmm1
0x1800f12aa  movdqa  [rbp+690h+var_370], xmm1
0x1800f12b2  mov     [rbp+690h+var_360], rsi
0x1800f12b9  mov     [rbp+690h+var_354], 1
0x1800f12c3  mov     [rbp+690h+var_350], 48h ; 'H'
0x1800f12cd  mov     [rbp+690h+var_358], 1
0x1800f12d7  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_f95aa8065ccec292900f2d8ee65d83de_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_f95aa8065ccec292900f2d8ee65d83de_,void,>::`vftable'
0x1800f12de  mov     [rbp+690h+var_3F0], rax
0x1800f12e5  lea     rax, [rsp+790h+var_74F]
0x1800f12ea  mov     [rbp+690h+var_3E8], rax
0x1800f12f1  lea     rax, [rbp+690h+var_3F0]
0x1800f12f8  mov     [rbp+690h+var_3B8], rax
0x1800f12ff  lea     rcx, [rbp+690h+lpFileName]
0x1800f1306  cmp     [rbp+690h+var_478], 7
0x1800f130e  cmova   rcx, [rbp+690h+lpFileName]; wchar_t *
0x1800f1316  call    ?NtCreateFileWrapper@@YAPEAXPEB_W@Z; NtCreateFileWrapper(wchar_t const *)
0x1800f131b  mov     r12, rax
0x1800f131e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800f1322  jnz     short loc_1800F132F
0x1800f1324  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800f1329  mov     edi, eax
0x1800f132b  test    eax, eax
0x1800f132d  js      short loc_1800F1351
0x1800f132f  lea     r8, [rbp+690h+var_3F0]
0x1800f1336  mov     rdx, r12; hSourceHandle
0x1800f1339  lea     rcx, [rbp+690h+pv]; pv
0x1800f1340  call    ?RequestOplockOnHandle@COplockProvider@@QEAAJPEAXAEBV?$function@$$A6AXXZ@std@@@Z; COplockProvider::RequestOplockOnHandle(void *,std::function<void (void)> const &)
0x1800f1345  mov     edi, eax
0x1800f1347  mov     rcx, r12; hObject
0x1800f134a  call    cs:__imp_CloseHandle
0x1800f1350  nop
0x1800f1351  lea     rcx, [rbp+690h+var_3F0]
0x1800f1358  call    ??1?$function@$$A6AKUPolicyParameters@@@Z@std@@QEAA@XZ; std::function<ulong (PolicyParameters)>::~function<ulong (PolicyParameters)>(void)
0x1800f135d  lea     r9, aHrrequestoploc; "hrRequestOplock"
0x1800f1364  mov     r8d, edi; int
0x1800f1367  mov     r12, [rsp+790h+hDevice]
0x1800f136c  mov     rdx, r12; struct Windows::ChangeTracking::SChangeRoot *
0x1800f136f  mov     rcx, r13; this
0x1800f1372  call    ?_ThrowIfFastFail@CChangeMonitor@ChangeTracking@Windows@@AEAAXAEBUSChangeRoot@23@JPEB_W@Z; Windows::ChangeTracking::CChangeMonitor::_ThrowIfFastFail(Windows::ChangeTracking::SChangeRoot const &,long,wchar_t const *)
0x1800f1377  test    edi, edi
0x1800f1379  js      loc_1800F17B1
0x1800f137f  lea     rcx, [rbp+690h+lpFileName]
0x1800f1386  cmp     [rbp+690h+var_478], 7
0x1800f138e  cmova   rcx, [rbp+690h+lpFileName]; lpFileName
0x1800f1396  mov     [rsp+790h+hTemplateFile], rsi; hTemplateFile
0x1800f139b  mov     [rsp+790h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800f13a3  mov     [rsp+790h+dwCreationDisposition], 3; dwCreationDisposition
0x1800f13ab  xor     r9d, r9d; lpSecurityAttributes
0x1800f13ae  mov     edx, 80000000h; dwDesiredAccess
0x1800f13b3  lea     r8d, [r9+5]; dwShareMode
0x1800f13b7  call    cs:__imp_CreateFileW
0x1800f13bd  mov     [rsp+790h+hDevice], rax
0x1800f13c2  dec     rax
0x1800f13c5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f13c9  ja      short loc_1800F13CF
0x1800f13cb  mov     eax, esi
0x1800f13cd  jmp     short loc_1800F13D4
0x1800f13cf  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800f13d4  lea     r9, aHfileSOkResult; "hFile ? S_OK : ResultFromLastError()"
0x1800f13db  mov     r8d, eax; int
0x1800f13de  mov     rdx, r12; struct Windows::ChangeTracking::SChangeRoot *
0x1800f13e1  mov     rcx, r13; this
0x1800f13e4  call    ?_ThrowIfFastFail@CChangeMonitor@ChangeTracking@Windows@@AEAAXAEBUSChangeRoot@23@JPEB_W@Z; Windows::ChangeTracking::CChangeMonitor::_ThrowIfFastFail(Windows::ChangeTracking::SChangeRoot const &,long,wchar_t const *)
0x1800f13e9  mov     rdi, [rsp+790h+hDevice]
0x1800f13ee  lea     rax, [rdi-1]
0x1800f13f2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f13f6  ja      loc_1800F17A7
0x1800f13fc  xor     edx, edx; Val
0x1800f13fe  mov     r8d, 248h; Size
0x1800f1404  lea     rcx, [rbp+690h+OutBuffer]; void *
0x1800f140b  call    memset_0
0x1800f1410  mov     dword ptr [rsp+790h+InBuffer], 20002h
0x1800f1418  mov     [rbp+690h+BytesReturned], esi
0x1800f141b  mov     [rsp+790h+lpOverlapped], rsi; lpOverlapped
0x1800f1420  lea     rax, [rbp+690h+BytesReturned]
0x1800f1424  mov     [rsp+790h+hTemplateFile], rax; lpBytesReturned
0x1800f1429  mov     [rsp+790h+dwFlagsAndAttributes], 248h; nOutBufferSize
0x1800f1431  lea     rax, [rbp+690h+OutBuffer]
0x1800f1438  mov     qword ptr [rsp+790h+dwCreationDisposition], rax; lpOutBuffer
0x1800f143d  mov     r9d, 4; nInBufferSize
0x1800f1443  lea     r8, [rsp+790h+InBuffer]; lpInBuffer
  ... truncated ...
```
