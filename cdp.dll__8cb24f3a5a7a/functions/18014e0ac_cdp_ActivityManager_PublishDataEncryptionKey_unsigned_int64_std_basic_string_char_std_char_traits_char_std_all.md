# cdp::ActivityManager::PublishDataEncryptionKey(unsigned __int64,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18014e0ac`
- end: `0x18014eb14`
- name: `?PublishDataEncryptionKey@ActivityManager@cdp@@AEAAX_KAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `2664`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, installer_update`

## callers

- `0x18014dac0`
- `0x18014de50`

## callees

- `0x180013da0`
- `0x1800175f8`
- `0x1800186b4`
- `0x180030190`
- `0x180067954`
- `0x18006a280`
- `0x18006b714`
- `0x18006b7cc`
- `0x18007120c`
- `0x180074b50`
- `0x18008e820`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800d6df4`
- `0x1800d8710`
- `0x1800e77f0`
- `0x18011b8bc`
- `0x18011b8fc`
- `0x180143248`
- `0x18014d240`
- `0x18014e0ac`
- `0x1801909cc`
- `0x1801f6fb0`
- `0x1801fc4d4`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e10b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e1ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e283`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e335`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e4c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e575`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e662`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e71f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e7ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e885`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e99f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e10b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e1ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e283`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e335`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e4c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e575`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e662`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e71f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e7ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e885`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18014e99f`

## string_xrefs

- `0x18014e13a`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18014e1dc`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18014e2b2`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18014e364`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18014e436`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18014e4f0`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18014e5a4`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18014e691`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18014e74e`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18014e7fd`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18014e8b4`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18014e9ce`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall cdp::ActivityManager::PublishDataEncryptionKey(_BYTE *a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v3; // rsi
  int v6; // ecx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rax
  int v11; // ecx
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // rax
  int v16; // ebx
  DWORD v17; // eax
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rax
  int v22; // ebx
  DWORD v23; // eax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rax
  int v28; // ebx
  DWORD v29; // eax
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rax
  int v34; // ebx
  DWORD v35; // eax
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rax
  int v40; // ebx
  DWORD v41; // eax
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rax
  std::_Ref_count_base *v46; // rdi
  __int64 (__fastcall *v47)(std::_Ref_count_base *, _QWORD *); // rbx
  __int64 v48; // rax
  _QWORD *v49; // rdx
  int v50; // ebx
  DWORD v51; // eax
  __int64 v52; // rax
  __int64 v53; // rdx
  __int64 v54; // r8
  __int64 v55; // rax
  __int64 v56; // rdx
  int v57; // ebx
  DWORD v58; // eax
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // rax
  __int64 v63; // rdx
  int v64; // ebx
  DWORD v65; // eax
  __int64 v66; // rax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 v69; // rax
  int v70; // ebx
  DWORD v71; // eax
  __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // rax
  int v76; // ecx
  __int64 v77; // rax
  __int64 v78; // rdx
  __int64 v79; // r8
  __int64 v80; // rax
  const struct shared::ActivityData *v81; // rax
  int v82; // [rsp+30h] [rbp-D0h] BYREF
  __int64 CurrentThreadId; // [rsp+38h] [rbp-C8h] BYREF
  std::_Ref_count_base *v84[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v86[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v87; // [rsp+98h] [rbp-68h] BYREF
  std::_Ref_count_base *v88; // [rsp+A0h] [rbp-60h]
  _BYTE v89[24]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v90[6]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v91[528]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v92[528]; // [rsp+300h] [rbp+200h] BYREF
  const char *v93; // [rsp+510h] [rbp+410h] BYREF
  std::_Ref_count_base *v94; // [rsp+518h] [rbp+418h] BYREF
  _BYTE v95[11]; // [rsp+525h] [rbp+425h] BYREF

  v3 = a3;
  if ( !a2 )
  {
    v93 = "..\\activitymanager.cpp";
    LODWORD(v94) = 2936;
    v82 = -2147024809;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v6,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v82,
      (unsigned int)&v93,
      (__int64)&v94,
      (__int64)&CurrentThreadId);
    v7 = cdp::ExceptionStackFromSourceLocationInfo(v90, &v93);
    v10 = cdp::ErrorCodeToString(2147942487LL, v8, v9, v7);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147942487LL, v10);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  if ( !a3[2] )
  {
    v93 = "..\\activitymanager.cpp";
    LODWORD(v94) = 2937;
    v82 = -2147024809;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v11,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v82,
      (unsigned int)&v93,
      (__int64)&v94,
      (__int64)&CurrentThreadId);
    v12 = cdp::ExceptionStackFromSourceLocationInfo(v90, &v93);
    v15 = cdp::ErrorCodeToString(2147942487LL, v13, v14, v12);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147942487LL, v15);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  *(_OWORD *)v84 = 0;
  v93 = 0;
  v94 = (std::_Ref_count_base *)v84;
  v16 = CDPCreateActivityInternal(0, &v93);
  cdp::detail::address_of<ICDPActivity>::~address_of<ICDPActivity>(&v93);
  if ( v16 < 0 )
  {
    v93 = "..\\activitymanager.cpp";
    LODWORD(v94) = 2940;
    v82 = v16;
    v17 = GetCurrentThreadId();
    CurrentThreadId = v17;
    Log<long &,char const * &,int &,unsigned __int64>(
      v17,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v82,
      (unsigned int)&v93,
      (__int64)&v94,
      (__int64)&CurrentThreadId);
    v18 = cdp::ExceptionStackFromSourceLocationInfo(v90, &v93);
    v21 = cdp::ErrorCodeToString((unsigned int)v16, v19, v20, v18);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v16, v21);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v22 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v84[0] + 56LL))(v84[0], 15);
  if ( v22 < 0 )
  {
    v93 = "..\\activitymanager.cpp";
    LODWORD(v94) = 2941;
    v82 = v22;
    v23 = GetCurrentThreadId();
    CurrentThreadId = v23;
    Log<long &,char const * &,int &,unsigned __int64>(
      v23,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v82,
      (unsigned int)&v93,
      (__int64)&v94,
      (__int64)&CurrentThreadId);
    v24 = cdp::ExceptionStackFromSourceLocationInfo(v90, &v93);
    v27 = cdp::ErrorCodeToString((unsigned int)v22, v25, v26, v24);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v22, v27);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  *(_OWORD *)v86 = 0;
  v93 = 0;
  v94 = (std::_Ref_count_base *)v86;
  v28 = CDPCreateCrossPlatformAppId(&v93);
  cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(&v93);
  if ( v28 < 0 )
  {
    v93 = "..\\activitymanager.cpp";
    LODWORD(v94) = 2947;
    v82 = v28;
    v29 = GetCurrentThreadId();
    CurrentThreadId = v29;
    Log<long &,char const * &,int &,unsigned __int64>(
      v29,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v82,
      (unsigned int)&v93,
      (__int64)&v94,
      (__int64)&CurrentThreadId);
    v30 = cdp::ExceptionStackFromSourceLocationInfo(v90, &v93);
    v33 = cdp::ErrorCodeToString((unsigned int)v28, v31, v32, v30);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v28, v33);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v34 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, const char *, const char *))(*(_QWORD *)v86[0] + 32LL))(
          v86[0],
          "alternateId",
          "dek.encrypted.settings");
  if ( v34 < 0 )
  {
    v93 = "..\\activitymanager.cpp";
    LODWORD(v94) = 2948;
    v82 = v34;
    v35 = GetCurrentThreadId();
    CurrentThreadId = v35;
    Log<long &,char const * &,int &,unsigned __int64>(
      v35,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v82,
      (unsigned int)&v93,
      (__int64)&v94,
      (__int64)&CurrentThreadId);
    v36 = cdp::ExceptionStackFromSourceLocationInfo(v90, &v93);
    v39 = cdp::ErrorCodeToString((unsigned int)v34, v37, v38, v36);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v34, v39);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v40 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, std::_Ref_count_base *))(*(_QWORD *)v84[0] + 216LL))(
          v84[0],
          v86[0]);
  if ( v40 < 0 )
  {
    v93 = "..\\activitymanager.cpp";
    LODWORD(v94) = 2949;
    v82 = v40;
    v41 = GetCurrentThreadId();
    CurrentThreadId = v41;
    Log<long &,char const * &,int &,unsigned __int64>(
      v41,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v82,
      (unsigned int)&v93,
      (__int64)&v94,
      (__int64)&CurrentThreadId);
    v42 = cdp::ExceptionStackFromSourceLocationInfo(v90, &v93);
    v45 = cdp::ErrorCodeToString((unsigned int)v40, v43, v44, v42);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v40, v45);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v46 = v84[0];
  v47 = *(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD *))(*(_QWORD *)v84[0] + 72LL);
  v48 = std::_UIntegral_to_buff<char,unsigned __int64>(v95, a2);
  std::string::string(v90, v48, v95);
  v49 = v90;
  if ( v90[3] > 0xFu )
    v49 = (_QWORD *)v90[0];
  v50 = v47(v46, v49);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v90);
  if ( v50 < 0 )
  {
    v93 = "..\\activitymanager.cpp";
    LODWORD(v94) = 2950;
    v82 = v50;
    v51 = GetCurrentThreadId();
    CurrentThreadId = v51;
    Log<long &,char const * &,int &,unsigned __int64>(
      v51,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v82,
      (unsigned int)&v93,
      (__int64)&v94,
      (__int64)&CurrentThreadId);
    v52 = cdp::ExceptionStackFromSourceLocationInfo(v90, &v93);
    v55 = cdp::ErrorCodeToString((unsigned int)v50, v53, v54, v52);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v50, v55);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  if ( v3[3] > 0xFu )
    v3 = (_QWORD *)*v3;
  v57 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD *))(*(_QWORD *)v84[0] + 144LL))(v84[0], v3);
  if ( v57 < 0 )
  {
    v93 = "..\\activitymanager.cpp";
    LODWORD(v94) = 2951;
    v82 = v57;
    v58 = GetCurrentThreadId();
    CurrentThreadId = v58;
    Log<long &,char const * &,int &,unsigned __int64>(
      v58,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v82,
      (unsigned int)&v93,
      (__int64)&v94,
      (__int64)&CurrentThreadId);
    v59 = cdp::ExceptionStackFromSourceLocationInfo(v90, &v93);
    v62 = cdp::ErrorCodeToString((unsigned int)v57, v60, v61, v59);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v57, v62);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  LOBYTE(v56) = 1;
  v64 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v84[0] + 104LL))(v84[0], v56);
  if ( v64 < 0 )
  {
    v93 = "..\\activitymanager.cpp";
    LODWORD(v94) = 2952;
    v82 = v64;
    v65 = GetCurrentThreadId();
    CurrentThreadId = v65;
    Log<long &,char const * &,int &,unsigned __int64>(
      v65,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v82,
      (unsigned int)&v93,
      (__int64)&v94,
      (__int64)&CurrentThreadId);
    v66 = cdp::ExceptionStackFromSourceLocationInfo(v90, &v93);
    v69 = cdp::ErrorCodeToString((unsigned int)v64, v67, v68, v66);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v64, v69);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  LOBYTE(v63) = a1[544];
  v70 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int64))(*(_QWORD *)v84[0] + 184LL))(v84[0], v63);
  if ( v70 < 0 )
  {
    v93 = "..\\activitymanager.cpp";
    LODWORD(v94) = 2957;
    v82 = v70;
    v71 = GetCurrentThreadId();
    CurrentThreadId = v71;
    Log<long &,char const * &,int &,unsigned __int64>(
      v71,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v82,
      (unsigned int)&v93,
      (__int64)&v94,
      (__int64)&CurrentThreadId);
    v72 = cdp::ExceptionStackFromSourceLocationInfo(v90, &v93);
    v75 = cdp::ErrorCodeToString((unsigned int)v70, v73, v74, v72);
    ConnectedDevices::Exception::Exception(pExceptionObject, (unsigned int)v70, v75);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  if ( a1[544] )
  {
    cdp::ActivityManager::GetDatabaseConnectionLease(a1, v90);
    ActivityFeedClient::MetadataManager::MetadataManager(
      (ActivityFeedClient::MetadataManager *)&v93,
      (const struct ActivityFeedClient::ConnectionLease *)v90);
    ActivityFeedClient::MetadataManager::AddUpdateMetadata(
      (ActivityFeedClient::MetadataManager *)&v93,
      "PendingFirstDEKUpload",
      "false");
    ActivityFeedClient::ConnectionLease::RestoreConnectionToPool((ActivityFeedClient::ConnectionLease *)v90);
    if ( v94 )
      std::_Ref_count_base::_Decref(v94);
    ActivityFeedClient::ConnectionLease::~ConnectionLease((ActivityFeedClient::ConnectionLease *)v90);
  }
  cdp::query_interface<cdp::ICDPInternalActivityBase,ICDPActivity>(&v87, v84);
  if ( !v87 )
  {
    v93 = "..\\activitymanager.cpp";
    LODWORD(v94) = 2971;
    v82 = -2147467262;
    CurrentThreadId = GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v76,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v82,
      (unsigned int)&v93,
      (__int64)&v94,
      (__int64)&CurrentThreadId);
    v77 = cdp::ExceptionStackFromSourceLocationInfo(v90, &v93);
    v80 = cdp::ErrorCodeToString(2147500034LL, v78, v79, v77);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2147500034LL, v80);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  v81 = (const struct shared::ActivityData *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v87 + 24LL))(v87);
  shared::ActivityData::ActivityData((shared::ActivityData *)v92, v81);
  shared::ActivityData::ActivityData((shared::ActivityData *)v91, (const struct shared::ActivityData *)v92);
  v93 = v91;
  v94 = (std::_Ref_count_base *)v92;
  std::vector<shared::ActivityData>::vector<shared::ActivityData>(v89, &v93);
  `eh vector destructor iterator'(v91, 0x210u, 1u, (void (*)(void *))shared::ActivityData::~ActivityData);
  (*(void (__fastcall **)(_BYTE *, _BYTE *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v89, 0, 0, 0);
  std::vector<shared::ActivityData>::_Tidy(v89);
  shared::ActivityData::~ActivityData((shared::ActivityData *)v92);
  if ( v88 )
    std::_Ref_count_base::_Decref(v88);
  if ( v86[1] )
    std::_Ref_count_base::_Decref(v86[1]);
  if ( v84[1] )
    std::_Ref_count_base::_Decref(v84[1]);
}

```

## disassembly

```asm
0x18014e0ac  mov     [rsp-8+arg_18], rbx
0x18014e0b1  push    rbp
0x18014e0b2  push    rsi
0x18014e0b3  push    rdi
0x18014e0b4  push    r14
0x18014e0b6  push    r15
0x18014e0b8  lea     rbp, [rsp-440h]
0x18014e0c0  sub     rsp, 540h
0x18014e0c7  mov     rax, cs:__security_cookie
0x18014e0ce  xor     rax, rsp
0x18014e0d1  mov     [rbp+460h+var_30], rax
0x18014e0d8  mov     rsi, r8
0x18014e0db  mov     r15, rdx
0x18014e0de  mov     r14, rcx
0x18014e0e1  test    rdx, rdx
0x18014e0e4  jnz     loc_18014E181
0x18014e0ea  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x18014e0f1  mov     [rbp+460h+var_50], rax
0x18014e0f8  mov     dword ptr [rbp+460h+var_48], 0B78h
0x18014e102  mov     ebx, 80070057h
0x18014e107  mov     [rsp+560h+var_530], ebx
0x18014e10b  call    cs:__imp_GetCurrentThreadId
0x18014e111  mov     eax, eax
0x18014e113  mov     [rsp+560h+var_528], rax
0x18014e118  lea     rax, [rsp+560h+var_528]
0x18014e11d  mov     [rsp+560h+var_538], rax
0x18014e122  lea     rax, [rbp+460h+var_48]
0x18014e129  mov     [rsp+560h+var_540], rax
0x18014e12e  lea     r9, [rbp+460h+var_50]
0x18014e135  lea     r8, [rsp+560h+var_530]
0x18014e13a  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18014e141  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18014e146  lea     rdx, [rbp+460h+var_50]
0x18014e14d  lea     rcx, [rbp+460h+var_4A0]
0x18014e151  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18014e156  mov     r9, rax
0x18014e159  mov     ecx, ebx
0x18014e15b  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18014e160  mov     r8, rax
0x18014e163  mov     edx, ebx
0x18014e165  lea     rcx, [rsp+560h+pExceptionObject]
0x18014e16a  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18014e16f  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18014e176  lea     rcx, [rsp+560h+pExceptionObject]; pExceptionObject
0x18014e17b  call    _CxxThrowException_0
0x18014e181  cmp     qword ptr [r8+10h], 0
0x18014e186  jnz     loc_18014E223
0x18014e18c  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x18014e193  mov     [rbp+460h+var_50], rax
0x18014e19a  mov     dword ptr [rbp+460h+var_48], 0B79h
0x18014e1a4  mov     ebx, 80070057h
0x18014e1a9  mov     [rsp+560h+var_530], ebx
0x18014e1ad  call    cs:__imp_GetCurrentThreadId
0x18014e1b3  mov     eax, eax
0x18014e1b5  mov     [rsp+560h+var_528], rax
0x18014e1ba  lea     rax, [rsp+560h+var_528]
0x18014e1bf  mov     [rsp+560h+var_538], rax
0x18014e1c4  lea     rax, [rbp+460h+var_48]
0x18014e1cb  mov     [rsp+560h+var_540], rax
0x18014e1d0  lea     r9, [rbp+460h+var_50]
0x18014e1d7  lea     r8, [rsp+560h+var_530]
0x18014e1dc  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18014e1e3  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18014e1e8  lea     rdx, [rbp+460h+var_50]
0x18014e1ef  lea     rcx, [rbp+460h+var_4A0]
0x18014e1f3  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18014e1f8  mov     r9, rax
0x18014e1fb  mov     ecx, ebx
0x18014e1fd  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18014e202  mov     r8, rax
0x18014e205  mov     edx, ebx
0x18014e207  lea     rcx, [rsp+560h+pExceptionObject]
0x18014e20c  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18014e211  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18014e218  lea     rcx, [rsp+560h+pExceptionObject]; pExceptionObject
0x18014e21d  call    _CxxThrowException_0
0x18014e223  xorps   xmm0, xmm0
0x18014e226  movdqu  xmmword ptr [rsp+560h+var_520], xmm0
0x18014e22c  mov     [rbp+460h+var_50], 0
0x18014e237  lea     rax, [rsp+560h+var_520]
0x18014e23c  mov     [rbp+460h+var_48], rax
0x18014e243  lea     rdx, [rbp+460h+var_50]
0x18014e24a  xor     ecx, ecx
0x18014e24c  call    CDPCreateActivityInternal
0x18014e251  mov     ebx, eax
0x18014e253  lea     rcx, [rbp+460h+var_50]
0x18014e25a  call    ??1?$address_of@VICDPActivity@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPActivity>::~address_of<ICDPActivity>(void)
0x18014e25f  test    ebx, ebx
0x18014e261  jns     loc_18014E2F9
0x18014e267  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x18014e26e  mov     [rbp+460h+var_50], rax
0x18014e275  mov     dword ptr [rbp+460h+var_48], 0B7Ch
0x18014e27f  mov     [rsp+560h+var_530], ebx
0x18014e283  call    cs:__imp_GetCurrentThreadId
0x18014e289  mov     ecx, eax
0x18014e28b  mov     [rsp+560h+var_528], rcx
0x18014e290  lea     rax, [rsp+560h+var_528]
0x18014e295  mov     [rsp+560h+var_538], rax
0x18014e29a  lea     rax, [rbp+460h+var_48]
0x18014e2a1  mov     [rsp+560h+var_540], rax
0x18014e2a6  lea     r9, [rbp+460h+var_50]
0x18014e2ad  lea     r8, [rsp+560h+var_530]
0x18014e2b2  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18014e2b9  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18014e2be  lea     rdx, [rbp+460h+var_50]
0x18014e2c5  lea     rcx, [rbp+460h+var_4A0]
0x18014e2c9  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18014e2ce  mov     r9, rax
0x18014e2d1  mov     ecx, ebx
0x18014e2d3  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18014e2d8  mov     r8, rax
0x18014e2db  mov     edx, ebx
0x18014e2dd  lea     rcx, [rsp+560h+pExceptionObject]
0x18014e2e2  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18014e2e7  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18014e2ee  lea     rcx, [rsp+560h+pExceptionObject]; pExceptionObject
0x18014e2f3  call    _CxxThrowException_0
0x18014e2f9  mov     rcx, [rsp+560h+var_520]
0x18014e2fe  mov     rax, [rcx]
0x18014e301  mov     edx, 0Fh
0x18014e306  mov     rax, [rax+38h]
0x18014e30a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e30f  mov     ebx, eax
0x18014e311  test    eax, eax
0x18014e313  jns     loc_18014E3AB
0x18014e319  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x18014e320  mov     [rbp+460h+var_50], rax
0x18014e327  mov     dword ptr [rbp+460h+var_48], 0B7Dh
0x18014e331  mov     [rsp+560h+var_530], ebx
0x18014e335  call    cs:__imp_GetCurrentThreadId
0x18014e33b  mov     ecx, eax
0x18014e33d  mov     [rsp+560h+var_528], rcx
0x18014e342  lea     rax, [rsp+560h+var_528]
0x18014e347  mov     [rsp+560h+var_538], rax
0x18014e34c  lea     rax, [rbp+460h+var_48]
0x18014e353  mov     [rsp+560h+var_540], rax
0x18014e358  lea     r9, [rbp+460h+var_50]
0x18014e35f  lea     r8, [rsp+560h+var_530]
0x18014e364  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18014e36b  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18014e370  lea     rdx, [rbp+460h+var_50]
0x18014e377  lea     rcx, [rbp+460h+var_4A0]
0x18014e37b  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18014e380  mov     r9, rax
0x18014e383  mov     ecx, ebx
0x18014e385  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18014e38a  mov     r8, rax
0x18014e38d  mov     edx, ebx
0x18014e38f  lea     rcx, [rsp+560h+pExceptionObject]
0x18014e394  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18014e399  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18014e3a0  lea     rcx, [rsp+560h+pExceptionObject]; pExceptionObject
0x18014e3a5  call    _CxxThrowException_0
0x18014e3ab  xorps   xmm0, xmm0
0x18014e3ae  movdqu  xmmword ptr [rbp+460h+var_4D8], xmm0
0x18014e3b3  mov     [rbp+460h+var_50], 0
0x18014e3be  lea     rax, [rbp+460h+var_4D8]
0x18014e3c2  mov     [rbp+460h+var_48], rax
0x18014e3c9  lea     rcx, [rbp+460h+var_50]
0x18014e3d0  call    CDPCreateCrossPlatformAppId
0x18014e3d5  mov     ebx, eax
0x18014e3d7  lea     rcx, [rbp+460h+var_50]
0x18014e3de  call    ??1?$address_of@VICDPCrossPlatformAppId@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPCrossPlatformAppId>::~address_of<ICDPCrossPlatformAppId>(void)
0x18014e3e3  test    ebx, ebx
0x18014e3e5  jns     loc_18014E47D
0x18014e3eb  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x18014e3f2  mov     [rbp+460h+var_50], rax
0x18014e3f9  mov     dword ptr [rbp+460h+var_48], 0B83h
0x18014e403  mov     [rsp+560h+var_530], ebx
0x18014e407  call    cs:__imp_GetCurrentThreadId
0x18014e40d  mov     ecx, eax
0x18014e40f  mov     [rsp+560h+var_528], rcx
0x18014e414  lea     rax, [rsp+560h+var_528]
0x18014e419  mov     [rsp+560h+var_538], rax
0x18014e41e  lea     rax, [rbp+460h+var_48]
0x18014e425  mov     [rsp+560h+var_540], rax
0x18014e42a  lea     r9, [rbp+460h+var_50]
0x18014e431  lea     r8, [rsp+560h+var_530]
0x18014e436  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18014e43d  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18014e442  lea     rdx, [rbp+460h+var_50]
0x18014e449  lea     rcx, [rbp+460h+var_4A0]
0x18014e44d  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18014e452  mov     r9, rax
0x18014e455  mov     ecx, ebx
0x18014e457  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18014e45c  mov     r8, rax
0x18014e45f  mov     edx, ebx
0x18014e461  lea     rcx, [rsp+560h+pExceptionObject]
0x18014e466  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18014e46b  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18014e472  lea     rcx, [rsp+560h+pExceptionObject]; pExceptionObject
0x18014e477  call    _CxxThrowException_0
0x18014e47d  mov     rcx, [rbp+460h+var_4D8]
0x18014e481  mov     rax, [rcx]
0x18014e484  lea     r8, aDekEncryptedSe_0; "dek.encrypted.settings"
0x18014e48b  lea     rdx, aAlternateid; "alternateId"
0x18014e492  mov     rax, [rax+20h]
0x18014e496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e49b  mov     ebx, eax
0x18014e49d  test    eax, eax
0x18014e49f  jns     loc_18014E537
0x18014e4a5  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x18014e4ac  mov     [rbp+460h+var_50], rax
0x18014e4b3  mov     dword ptr [rbp+460h+var_48], 0B84h
0x18014e4bd  mov     [rsp+560h+var_530], ebx
0x18014e4c1  call    cs:__imp_GetCurrentThreadId
0x18014e4c7  mov     ecx, eax
0x18014e4c9  mov     [rsp+560h+var_528], rcx
0x18014e4ce  lea     rax, [rsp+560h+var_528]
0x18014e4d3  mov     [rsp+560h+var_538], rax
0x18014e4d8  lea     rax, [rbp+460h+var_48]
0x18014e4df  mov     [rsp+560h+var_540], rax
0x18014e4e4  lea     r9, [rbp+460h+var_50]
0x18014e4eb  lea     r8, [rsp+560h+var_530]
0x18014e4f0  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18014e4f7  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18014e4fc  lea     rdx, [rbp+460h+var_50]
0x18014e503  lea     rcx, [rbp+460h+var_4A0]
0x18014e507  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18014e50c  mov     r9, rax
0x18014e50f  mov     ecx, ebx
0x18014e511  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18014e516  mov     r8, rax
0x18014e519  mov     edx, ebx
0x18014e51b  lea     rcx, [rsp+560h+pExceptionObject]
0x18014e520  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18014e525  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18014e52c  lea     rcx, [rsp+560h+pExceptionObject]; pExceptionObject
0x18014e531  call    _CxxThrowException_0
0x18014e537  mov     rcx, [rsp+560h+var_520]
0x18014e53c  mov     rax, [rcx]
0x18014e53f  mov     rdx, [rbp+460h+var_4D8]
0x18014e543  mov     rax, [rax+0D8h]
0x18014e54a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e54f  mov     ebx, eax
0x18014e551  test    eax, eax
0x18014e553  jns     loc_18014E5EB
0x18014e559  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x18014e560  mov     [rbp+460h+var_50], rax
0x18014e567  mov     dword ptr [rbp+460h+var_48], 0B85h
0x18014e571  mov     [rsp+560h+var_530], ebx
0x18014e575  call    cs:__imp_GetCurrentThreadId
0x18014e57b  mov     ecx, eax
0x18014e57d  mov     [rsp+560h+var_528], rcx
0x18014e582  lea     rax, [rsp+560h+var_528]
0x18014e587  mov     [rsp+560h+var_538], rax
0x18014e58c  lea     rax, [rbp+460h+var_48]
0x18014e593  mov     [rsp+560h+var_540], rax
0x18014e598  lea     r9, [rbp+460h+var_50]
0x18014e59f  lea     r8, [rsp+560h+var_530]
0x18014e5a4  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18014e5ab  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18014e5b0  lea     rdx, [rbp+460h+var_50]
0x18014e5b7  lea     rcx, [rbp+460h+var_4A0]
0x18014e5bb  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18014e5c0  mov     r9, rax
0x18014e5c3  mov     ecx, ebx
0x18014e5c5  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18014e5ca  mov     r8, rax
0x18014e5cd  mov     edx, ebx
0x18014e5cf  lea     rcx, [rsp+560h+pExceptionObject]
0x18014e5d4  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18014e5d9  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18014e5e0  lea     rcx, [rsp+560h+pExceptionObject]; pExceptionObject
0x18014e5e5  call    _CxxThrowException_0
0x18014e5eb  mov     rdi, [rsp+560h+var_520]
0x18014e5f0  mov     rax, [rdi]
0x18014e5f3  mov     rbx, [rax+48h]
0x18014e5f7  mov     rdx, r15
0x18014e5fa  lea     rcx, [rbp+460h+var_3B]
0x18014e601  call    ??$_UIntegral_to_buff@D_K@std@@YAPEADPEAD_K@Z; std::_UIntegral_to_buff<char,unsigned __int64>(char *,unsigned __int64)
0x18014e606  lea     r8, [rbp+460h+var_3B]
0x18014e60d  mov     rdx, rax
0x18014e610  lea     rcx, [rbp+460h+var_4A0]
0x18014e614  call    ??$?0PEAD$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEAD0AEBV?$allocator@D@1@@Z; std::string::string(char *,char *,std::allocator<char> const &)
0x18014e619  nop
0x18014e61a  lea     rdx, [rbp+460h+var_4A0]
0x18014e61e  cmp     [rbp+460h+var_488], 0Fh
0x18014e623  cmova   rdx, [rbp+460h+var_4A0]
0x18014e628  mov     rcx, rdi
0x18014e62b  mov     rax, rbx
0x18014e62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e633  mov     ebx, eax
0x18014e635  lea     rcx, [rbp+460h+var_4A0]; void *
0x18014e639  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18014e63e  test    ebx, ebx
0x18014e640  jns     loc_18014E6D8
0x18014e646  lea     rax, aActivitymanage_1; "..\\activitymanager.cpp"
0x18014e64d  mov     [rbp+460h+var_50], rax
0x18014e654  mov     dword ptr [rbp+460h+var_48], 0B86h
0x18014e65e  mov     [rsp+560h+var_530], ebx
0x18014e662  call    cs:__imp_GetCurrentThreadId
0x18014e668  mov     ecx, eax
0x18014e66a  mov     [rsp+560h+var_528], rcx
0x18014e66f  lea     rax, [rsp+560h+var_528]
0x18014e674  mov     [rsp+560h+var_538], rax
0x18014e679  lea     rax, [rbp+460h+var_48]
0x18014e680  mov     [rsp+560h+var_540], rax
0x18014e685  lea     r9, [rbp+460h+var_50]
  ... truncated ...
```
