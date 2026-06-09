# cdp::DeserializeJsonToValueSet(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x18030b224`
- end: `0x18030bedb`
- name: `?DeserializeJsonToValueSet@cdp@@YA?BV?$shared_ptr@UValueSet@ConnectedDevices@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z`
- size: `3255`
- prototype: ``
- caller_count: `2`
- callee_count: `37`
- tags: `registry_config`

## callers

- `0x1801f2c9c`
- `0x1801f31c0`

## callees

- `0x180003c74`
- `0x18000b724`
- `0x18000f554`
- `0x180030190`
- `0x18003a060`
- `0x18005ba50`
- `0x1800952e0`
- `0x180095428`
- `0x1800954b4`
- `0x1800a11bc`
- `0x180143248`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x1801fd910`
- `0x1801fdc00`
- `0x1801fe1f0`
- `0x1801fe270`
- `0x1801fea90`
- `0x1801fec60`
- `0x1801fedc0`
- `0x1801ff120`
- `0x1801ff2f0`
- `0x1801ffa70`
- `0x1801ffb50`
- `0x180200aa0`
- `0x180200c20`
- `0x180200c50`
- `0x180202760`
- `0x180241c94`
- `0x180241cc0`
- `0x180241dbc`
- `0x1802a12b0`
- `0x18030b078`
- `0x18030b15c`
- `0x18030b224`
- `0x18030bee4`
- `0x18030bfc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030b2e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030b489`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030b5df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030b6d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030b87a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030bbe1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030b2e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030b489`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030b5df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030b6d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030b87a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18030bbe1`

## string_xrefs

- `0x18030b315`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18030b4ba`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18030b610`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18030b705`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18030b8ab`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`
- `0x18030bc12`: `{"hr":"0x%08x","file":"%s","line":%d,"thread":"%zu"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall cdp::DeserializeJsonToValueSet(_QWORD *a1)
{
  int v2; // ecx
  __int64 v3; // r9
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rax
  const char *v7; // r15
  const char *v8; // r12
  __int64 v9; // rax
  unsigned int v10; // eax
  int v11; // ebx
  int v12; // eax
  int v13; // ecx
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rax
  int v18; // r13d
  __int64 v19; // rax
  unsigned int v20; // eax
  char v21; // r14
  unsigned int v22; // esi
  __int64 v23; // rax
  unsigned int v24; // eax
  int v25; // eax
  int v26; // ecx
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // rax
  int v32; // ecx
  int v33; // ecx
  int v34; // ecx
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  int v38; // ecx
  __int64 v39; // r9
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // rax
  __int64 v43; // rbx
  Json::Value *v44; // rax
  bool v45; // al
  bool *v46; // rdx
  __int64 v47; // rbx
  __int64 v48; // rax
  __int64 v49; // rax
  Json::Value *v50; // rax
  __int64 v51; // rbx
  __int64 v52; // rax
  __int64 v53; // rcx
  __int64 *v54; // rdx
  __int64 v55; // rbx
  Json::Value *v56; // rax
  __int64 v57; // rbx
  Json::Value *v58; // rax
  double v59; // xmm0_8
  double *v60; // rdx
  Json::Value *v61; // rax
  __int64 v62; // rbx
  Json::Value *v63; // rax
  __int64 i; // r14
  __int64 v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rbx
  _QWORD *v68; // r8
  _QWORD *v69; // rdx
  int v70; // ecx
  __int64 v71; // r9
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rcx
  __int64 v77; // rax
  __int64 v78; // rbx
  Json::Value *v79; // rax
  __int64 v80; // rax
  __int64 *v81; // rdx
  bool v82; // bl
  __int64 v83; // rbx
  _QWORD *v84; // rax
  double v85; // xmm0_8
  unsigned __int64 v86; // rax
  char *v87; // rdx
  __int64 v88; // rbx
  unsigned __int64 v90; // rax
  _BYTE v91[32]; // [rsp+0h] [rbp-518h] BYREF
  char v92; // [rsp+30h] [rbp-4E8h]
  int v93; // [rsp+34h] [rbp-4E4h] BYREF
  bool v94[4]; // [rsp+38h] [rbp-4E0h] BYREF
  int v95; // [rsp+3Ch] [rbp-4DCh] BYREF
  const char *CurrentThreadId; // [rsp+40h] [rbp-4D8h] BYREF
  _DWORD v97[3]; // [rsp+48h] [rbp-4D0h] BYREF
  int v98; // [rsp+54h] [rbp-4C4h]
  _BYTE v99[40]; // [rsp+58h] [rbp-4C0h] BYREF
  int v100; // [rsp+80h] [rbp-498h]
  __int64 v101; // [rsp+88h] [rbp-490h] BYREF
  const char *v102; // [rsp+90h] [rbp-488h]
  _BYTE v103[24]; // [rsp+98h] [rbp-480h] BYREF
  _QWORD *v104; // [rsp+B0h] [rbp-468h]
  const char *v105; // [rsp+B8h] [rbp-460h] BYREF
  const char *v106; // [rsp+C0h] [rbp-458h]
  _BYTE v107[40]; // [rsp+D0h] [rbp-448h] BYREF
  char v108[16]; // [rsp+F8h] [rbp-420h] BYREF
  char v109[16]; // [rsp+108h] [rbp-410h] BYREF
  char v110[16]; // [rsp+118h] [rbp-400h] BYREF
  char v111[16]; // [rsp+128h] [rbp-3F0h] BYREF
  char v112[16]; // [rsp+138h] [rbp-3E0h] BYREF
  char v113[16]; // [rsp+148h] [rbp-3D0h] BYREF
  char v114[16]; // [rsp+158h] [rbp-3C0h] BYREF
  char v115[16]; // [rsp+168h] [rbp-3B0h] BYREF
  char v116[16]; // [rsp+178h] [rbp-3A0h] BYREF
  char v117[16]; // [rsp+188h] [rbp-390h] BYREF
  char v118[16]; // [rsp+198h] [rbp-380h] BYREF
  char v119[16]; // [rsp+1A8h] [rbp-370h] BYREF
  char v120[16]; // [rsp+1B8h] [rbp-360h] BYREF
  char v121[16]; // [rsp+1C8h] [rbp-350h] BYREF
  char v122[16]; // [rsp+1D8h] [rbp-340h] BYREF
  char v123[16]; // [rsp+1E8h] [rbp-330h] BYREF
  char v124; // [rsp+1F8h] [rbp-320h] BYREF
  char v125[16]; // [rsp+208h] [rbp-310h] BYREF
  char v126; // [rsp+218h] [rbp-300h] BYREF
  char v127[16]; // [rsp+228h] [rbp-2F0h] BYREF
  char v128[16]; // [rsp+238h] [rbp-2E0h] BYREF
  char v129[16]; // [rsp+248h] [rbp-2D0h] BYREF
  _BYTE v130[40]; // [rsp+258h] [rbp-2C0h] BYREF
  _BYTE v131[56]; // [rsp+280h] [rbp-298h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+2B8h] [rbp-260h] BYREF
  _BYTE v133[56]; // [rsp+2F0h] [rbp-228h] BYREF
  _BYTE v134[56]; // [rsp+360h] [rbp-1B8h] BYREF
  _BYTE v135[56]; // [rsp+398h] [rbp-180h] BYREF
  unsigned __int64 v136; // [rsp+3D0h] [rbp-148h] BYREF
  _DWORD v137[6]; // [rsp+3D8h] [rbp-140h] BYREF
  _BYTE v138[32]; // [rsp+3F0h] [rbp-128h] BYREF
  _BYTE v139[192]; // [rsp+410h] [rbp-108h] BYREF

  v104 = a1;
  Json::Value::Value(v107, 0);
  Json::Reader::Reader((Json::Reader *)v139);
  std::make_shared<ConnectedDevices::ValueSet,>(a1);
  v100 = 1;
  if ( !(unsigned __int8)Json::Reader::parse((Json::Reader *)v139) )
  {
    v136 = (unsigned __int64)"..\\valuesethelpers.cpp";
    v137[0] = 110;
    v93 = -2089418750;
    CurrentThreadId = (const char *)GetCurrentThreadId();
    Log<long &,char const * &,int &,unsigned __int64>(
      v2,
      (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
      (unsigned int)&v93,
      (unsigned int)&v136,
      (__int64)v137,
      (__int64)&CurrentThreadId);
    v3 = cdp::ExceptionStackFromSourceLocationInfo(v103, &v136);
    v6 = cdp::ErrorCodeToString(2205548546LL, v4, v5, v3);
    ConnectedDevices::Exception::Exception(pExceptionObject, 2205548546LL, v6);
    throw (ConnectedDevices::Exception *)pExceptionObject;
  }
  Json::Value::getMemberNames(v107, &v105);
  v7 = v105;
  v8 = v106;
  v102 = v106;
  while ( 1 )
  {
    CurrentThreadId = v7;
    if ( v7 == v8 )
      break;
    cdp::ToWstring(v138, v7);
    v9 = Json::Value::Value(v130, 0);
    Json::Value::get(v107, v99, v7, v9);
    Json::Value::~Value((Json::Value *)v130);
    v10 = Json::Value::type(v99);
    v11 = cdp::JsonValueTypeToDataValueType(v10);
    *(_DWORD *)(*(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                             *a1,
                             v127,
                             v138)
              + 64LL) = v11;
    v12 = Json::Value::type(v99);
    switch ( v12 )
    {
      case 1:
        if ( Json::Value::asLargestInt((Json::Value *)v99) < 0 )
        {
          v88 = Json::Value::asLargestInt((Json::Value *)v99);
          *(_QWORD *)(*(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                                   *a1,
                                   v103,
                                   v138)
                    + 88LL) = v88;
          break;
        }
        *(_DWORD *)(*(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                                 *a1,
                                 v125,
                                 v138)
                  + 64LL) = 7;
        v86 = Json::Value::asUInt64((Json::Value *)v99);
        v87 = &v126;
LABEL_67:
        *(_QWORD *)(*(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                                 *a1,
                                 v87,
                                 v138)
                  + 96LL) = v86;
        break;
      case 2:
        v86 = Json::Value::asUInt64((Json::Value *)v99);
        v87 = &v124;
        goto LABEL_67;
      case 3:
        v85 = Json::Value::asDouble((Json::Value *)v99);
        *(double *)(*(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                                 *a1,
                                 v123,
                                 v138)
                  + 112LL) = v85;
        break;
      case 4:
        v83 = Json::Value::asString(v99, &v136);
        v84 = (_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                          *a1,
                          v122,
                          v138);
        std::string::operator=(*v84 + 216LL, v83);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v136);
        break;
      case 5:
        v82 = Json::Value::asBool((Json::Value *)v99);
        *(_BYTE *)(*(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                                *a1,
                                v121,
                                v138)
                 + 122LL) = v82;
        break;
      case 6:
        v18 = 0;
        v98 = 0;
        if ( Json::Value::size((Json::Value *)v99) )
        {
          v19 = Json::Value::operator[](v99, 0);
          v20 = Json::Value::type(v19);
          v18 = cdp::JsonValueTypeToDataValueArrayType(v20);
          v98 = v18;
          *(_DWORD *)(*(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                                   *a1,
                                   v128,
                                   v138)
                    + 64LL) = v18;
        }
        v21 = 0;
        v92 = 0;
        v22 = 0;
LABEL_16:
        v93 = v22;
        if ( v22 >= Json::Value::size((Json::Value *)v99) )
        {
          v8 = v102;
          break;
        }
        v23 = Json::Value::operator[](v99, v22);
        v24 = Json::Value::type(v23);
        v25 = cdp::JsonValueTypeToDataValueArrayType(v24);
        if ( ((unsigned int)(v18 - 25) > 1 || (unsigned int)(v25 - 25) > 1) && v18 != v25 )
        {
          v136 = (unsigned __int64)"..\\valuesethelpers.cpp";
          v137[0] = 183;
          v93 = -2089418750;
          CurrentThreadId = (const char *)GetCurrentThreadId();
          Log<long &,char const * &,int &,unsigned __int64>(
            v26,
            (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
            (unsigned int)&v93,
            (unsigned int)&v136,
            (__int64)v137,
            (__int64)&CurrentThreadId);
          v27 = cdp::ExceptionStackFromSourceLocationInfo(v103, &v136);
          v30 = cdp::ErrorCodeToString(2205548546LL, v28, v29, v27);
          ConnectedDevices::Exception::Exception(v133, 2205548546LL, v30);
          throw (ConnectedDevices::Exception *)v133;
        }
        v31 = Json::Value::operator[](v99, v22);
        v32 = Json::Value::type(v31);
        if ( !v32 )
        {
LABEL_28:
          CurrentThreadId = "..\\valuesethelpers.cpp";
          v97[0] = 190;
          v95 = -2089418750;
          v136 = GetCurrentThreadId();
          Log<long &,char const * &,int &,unsigned __int64>(
            v38,
            (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
            (unsigned int)&v95,
            (unsigned int)&CurrentThreadId,
            (__int64)v97,
            (__int64)&v136);
          v39 = cdp::ExceptionStackFromSourceLocationInfo(v103, &CurrentThreadId);
          v42 = cdp::ErrorCodeToString(2205548546LL, v40, v41, v39);
          ConnectedDevices::Exception::Exception(v135, 2205548546LL, v42);
          throw (ConnectedDevices::Exception *)v135;
        }
        v33 = v32 - 1;
        if ( v33 )
        {
          v34 = v33 - 1;
          if ( v34 )
          {
            v35 = v34 - 1;
            if ( v35 )
            {
              v36 = v35 - 1;
              if ( v36 )
              {
                v37 = v36 - 1;
                if ( v37 )
                {
                  if ( (unsigned int)(v37 - 1) <= 1 )
                    goto LABEL_28;
                }
                else
                {
                  v43 = *(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                                     *a1,
                                     v129,
                                     v138);
                  v44 = (Json::Value *)Json::Value::operator[](v99, v22);
                  v45 = Json::Value::asBool(v44);
                  v94[0] = v45;
                  v46 = *(bool **)(v43 + 496);
                  if ( v46 == *(bool **)(v43 + 504) )
                  {
                    std::vector<unsigned char>::_Emplace_reallocate<unsigned char &>(v43 + 488, v46, v94);
                  }
                  else
                  {
                    *v46 = v45;
                    ++*(_QWORD *)(v43 + 496);
                  }
                }
              }
              else
              {
                v47 = *(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                                   *a1,
                                   v108,
                                   v138);
                v48 = Json::Value::operator[](v99, v22);
                v49 = Json::Value::asString(v48, &v136);
                std::vector<std::string>::_Emplace_one_at_back<std::string>(v47 + 704, v49);
                std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v136);
              }
              goto LABEL_60;
            }
          }
          else if ( v21 )
          {
            v97[2] = 0;
            v101 = 0;
            try
            {
              v50 = (Json::Value *)Json::Value::operator[](v99, v22);
              v51 = Json::Value::asLargestInt(v50);
              v101 = v51;
            }
            catch ( ... )
            {
              LODWORD(v90) = GetCurrentThreadId();
              v136 = v90;
              v95 = 229;
              cdp::CatchAllToHR<char const (&)[29],int,unsigned __int64>(
                (unsigned int)v91 + 80,
                (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\""
                              ",\"text\":\"Failed to parse uint64 value as int64\"}",
                (unsigned int)"..\\valuesethelpers.cpp",
                (unsigned int)v91 + 60,
                (__int64)&v136);
            }
            v52 = std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                    *a1,
                    v109,
                    v138);
            v53 = *(_QWORD *)v52 + 368LL;
            v54 = *(__int64 **)(*(_QWORD *)v52 + 376LL);
            if ( v54 == *(__int64 **)(*(_QWORD *)v52 + 384LL) )
            {
              std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(v53, v54, &v101);
            }
            else
            {
              *v54 = v51;
              *(_QWORD *)(v53 + 8) += 8LL;
            }
          }
          else
          {
            v55 = *(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                               *a1,
                               v110,
                               v138);
            v56 = (Json::Value *)Json::Value::operator[](v99, v22);
            v136 = Json::Value::asUInt64(v56);
            std::vector<unsigned __int64>::_Emplace_one_at_back<unsigned __int64>(v55 + 392, &v136);
          }
          v57 = *(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                             *a1,
                             v111,
                             v138);
          v58 = (Json::Value *)Json::Value::operator[](v99, v22);
          v59 = Json::Value::asDouble(v58);
          v136 = *(_QWORD *)&v59;
          v60 = *(double **)(v57 + 448);
          if ( v60 == *(double **)(v57 + 456) )
          {
            std::vector<cdp::SendQueueItem *>::_Emplace_reallocate<cdp::SendQueueItem * &>(v57 + 440, v60, &v136);
          }
          else
          {
            *v60 = v59;
            *(_QWORD *)(v57 + 448) = v60 + 1;
          }
        }
        else if ( v21 || (v61 = (Json::Value *)Json::Value::operator[](v99, v22), Json::Value::asLargestInt(v61) < 0) )
        {
          *(_DWORD *)(*(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                                   *a1,
                                   v114,
                                   v138)
                    + 64LL) = 25;
          if ( !v21 )
          {
            for ( i = 0; ; i = (unsigned int)(i + 1) )
            {
              v65 = std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                      *a1,
                      v115,
                      v138);
              v66 = *a1;
              if ( (unsigned int)i >= (unsigned __int64)((__int64)(*(_QWORD *)(*(_QWORD *)v65 + 400LL)
                                                                 - *(_QWORD *)(*(_QWORD *)v65 + 392LL)) >> 3) )
                break;
              if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                                                        v66,
                                                        v116,
                                                        v138)
                                         + 392LL)
                             + 8 * i) > 0x7FFFFFFFFFFFFFFFuLL )
              {
                CurrentThreadId = "..\\valuesethelpers.cpp";
                v97[0] = 206;
                v95 = -2089418750;
                v136 = GetCurrentThreadId();
                Log<long &,char const * &,int &,unsigned __int64>(
                  v70,
                  (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
                  (unsigned int)&v95,
                  (unsigned int)&CurrentThreadId,
                  (__int64)v97,
                  (__int64)&v136);
                v71 = cdp::ExceptionStackFromSourceLocationInfo(v103, &CurrentThreadId);
                v74 = cdp::ErrorCodeToString(2205548546LL, v72, v73, v71);
                ConnectedDevices::Exception::Exception(v134, 2205548546LL, v74);
                throw (ConnectedDevices::Exception *)v134;
              }
              v67 = *(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                                 *a1,
                                 v117,
                                 v138);
              v68 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                                                        *a1,
                                                        v118,
                                                        v138)
                                         + 392LL)
                             + 8 * i);
              v69 = *(_QWORD **)(v67 + 376);
              if ( v69 == *(_QWORD **)(v67 + 384) )
              {
                std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(v67 + 368, v69, v68);
              }
              else
              {
                *v69 = *v68;
                *(_QWORD *)(v67 + 376) += 8LL;
              }
            }
            v75 = std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                    v66,
                    v119,
                    v138);
            v76 = *(_QWORD *)v75;
            v77 = *(_QWORD *)(*(_QWORD *)v75 + 392LL);
            if ( v77 != *(_QWORD *)(v76 + 400) )
              *(_QWORD *)(v76 + 400) = v77;
          }
          v78 = *(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                             *a1,
                             v120,
                             v138);
          v79 = (Json::Value *)Json::Value::operator[](v99, v22);
          v80 = Json::Value::asLargestInt(v79);
          v136 = v80;
          v81 = *(__int64 **)(v78 + 376);
          if ( v81 == *(__int64 **)(v78 + 384) )
          {
            std::vector<unsigned __int64>::_Emplace_reallocate<unsigned __int64 const &>(v78 + 368, v81, &v136);
          }
          else
          {
            *v81 = v80;
            *(_QWORD *)(v78 + 376) += 8LL;
          }
          v21 = 1;
          v92 = 1;
        }
        else
        {
          *(_DWORD *)(*(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                                   *a1,
                                   v112,
                                   v138)
                    + 64LL) = 26;
          v62 = *(_QWORD *)std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(
                             *a1,
                             v113,
                             v138);
          v63 = (Json::Value *)Json::Value::operator[](v99, v22);
          v136 = Json::Value::asUInt64(v63);
          std::vector<unsigned __int64>::_Emplace_one_at_back<unsigned __int64>(v62 + 392, &v136);
        }
LABEL_60:
        ++v22;
        goto LABEL_16;
      case 7:
        v136 = (unsigned __int64)"..\\valuesethelpers.cpp";
        v137[0] = 261;
        v93 = -2089418750;
        CurrentThreadId = (const char *)GetCurrentThreadId();
        Log<long &,char const * &,int &,unsigned __int64>(
          v13,
          (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\"}",
          (unsigned int)&v93,
          (unsigned int)&v136,
          (__int64)v137,
          (__int64)&CurrentThreadId);
        v14 = cdp::ExceptionStackFromSourceLocationInfo(v103, &v136);
        v17 = cdp::ErrorCodeToString(2205548546LL, v15, v16, v14);
        ConnectedDevices::Exception::Exception(v131, 2205548546LL, v17);
        throw (ConnectedDevices::Exception *)v131;
    }
    Json::Value::~Value((Json::Value *)v99);
    std::wstring::_Tidy_deallocate(v138);
    v7 += 32;
  }
  std::vector<std::string>::_Tidy(&v105);
  Json::Reader::~Reader((Json::Reader *)v139);
  Json::Value::~Value((Json::Value *)v107);
  return a1;
}

```

## disassembly

```asm
0x18030b224  mov     r11, rsp
0x18030b227  mov     [r11+18h], rbx
0x18030b22b  mov     [r11+20h], rsi
0x18030b22f  push    rdi
0x18030b230  push    r12
0x18030b232  push    r13
0x18030b234  push    r14
0x18030b236  push    r15
0x18030b238  sub     rsp, 4F0h
0x18030b23f  movaps  xmmword ptr [r11-38h], xmm6
0x18030b244  mov     rax, cs:__security_cookie
0x18030b24b  xor     rax, rsp
0x18030b24e  mov     [rsp+518h+var_48], rax
0x18030b256  mov     rbx, rdx
0x18030b259  mov     rdi, rcx
0x18030b25c  mov     [r11-468h], rcx
0x18030b263  mov     [rsp+518h+var_498], 0
0x18030b26e  xor     edx, edx
0x18030b270  lea     rcx, [r11-448h]
0x18030b277  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x18030b27c  nop
0x18030b27d  lea     rcx, [rsp+518h+var_108]; this
0x18030b285  call    ??0Reader@Json@@QEAA@XZ; Json::Reader::Reader(void)
0x18030b28a  nop
0x18030b28b  mov     rcx, rdi
0x18030b28e  call    ??$make_shared@UValueSet@ConnectedDevices@@$$V@std@@YA?AV?$shared_ptr@UValueSet@ConnectedDevices@@@0@XZ; std::make_shared<ConnectedDevices::ValueSet,>(void)
0x18030b293  mov     [rsp+518h+var_498], 1
0x18030b29e  mov     r9b, 1
0x18030b2a1  lea     r8, [rsp+518h+var_448]
0x18030b2a9  mov     rdx, rbx
0x18030b2ac  lea     rcx, [rsp+518h+var_108]
0x18030b2b4  call    ?parse@Reader@Json@@QEAA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAVValue@2@_N@Z; Json::Reader::parse(std::string const &,Json::Value &,bool)
0x18030b2b9  test    al, al
0x18030b2bb  jnz     loc_18030B367
0x18030b2c1  lea     rax, aValuesethelper; "..\\valuesethelpers.cpp"
0x18030b2c8  mov     [rsp+518h+var_148], rax
0x18030b2d0  mov     [rsp+518h+var_140], 6Eh ; 'n'
0x18030b2db  mov     ebx, 83760002h
0x18030b2e0  mov     [rsp+518h+var_4E4], ebx
0x18030b2e4  call    cs:__imp_GetCurrentThreadId
0x18030b2ea  mov     eax, eax
0x18030b2ec  mov     [rsp+518h+var_4D8], rax
0x18030b2f1  lea     rax, [rsp+518h+var_4D8]
0x18030b2f6  mov     [rsp+518h+var_4F0], rax
0x18030b2fb  lea     rax, [rsp+518h+var_140]
0x18030b303  mov     [rsp+518h+var_4F8], rax
0x18030b308  lea     r9, [rsp+518h+var_148]
0x18030b310  lea     r8, [rsp+518h+var_4E4]
0x18030b315  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18030b31c  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18030b321  lea     rdx, [rsp+518h+var_148]
0x18030b329  lea     rcx, [rsp+518h+var_480]
0x18030b331  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18030b336  mov     r9, rax
0x18030b339  mov     ecx, ebx
0x18030b33b  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18030b340  mov     r8, rax
0x18030b343  mov     edx, ebx
0x18030b345  lea     rcx, [rsp+518h+pExceptionObject]
0x18030b34d  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18030b352  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18030b359  lea     rcx, [rsp+518h+pExceptionObject]; pExceptionObject
0x18030b361  call    _CxxThrowException_0
0x18030b367  lea     rdx, [rsp+518h+var_460]
0x18030b36f  lea     rcx, [rsp+518h+var_448]
0x18030b377  call    ?getMemberNames@Value@Json@@QEBA?AV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@XZ; Json::Value::getMemberNames(void)
0x18030b37c  nop
0x18030b37d  mov     r15, [rsp+518h+var_460]
0x18030b385  mov     r12, [rsp+518h+var_458]
0x18030b38d  mov     [rsp+518h+var_488], r12
0x18030b395  mov     [rsp+518h+var_4D8], r15
0x18030b39a  cmp     r15, r12
0x18030b39d  jz      loc_18030BE7C
0x18030b3a3  mov     rdx, r15
0x18030b3a6  lea     rcx, [rsp+518h+var_128]
0x18030b3ae  call    ?ToWstring@cdp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@@Z; cdp::ToWstring(std::string const &)
0x18030b3b3  nop
0x18030b3b4  xor     edx, edx
0x18030b3b6  lea     rcx, [rsp+518h+var_2C0]
0x18030b3be  call    ??0Value@Json@@QEAA@W4ValueType@1@@Z; Json::Value::Value(Json::ValueType)
0x18030b3c3  nop
0x18030b3c4  mov     r9, rax
0x18030b3c7  mov     r8, r15
0x18030b3ca  lea     rdx, [rsp+518h+var_4C0]
0x18030b3cf  lea     rcx, [rsp+518h+var_448]
0x18030b3d7  call    ?get@Value@Json@@QEBA?AV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV12@@Z; Json::Value::get(std::string const &,Json::Value const &)
0x18030b3dc  nop
0x18030b3dd  lea     rcx, [rsp+518h+var_2C0]; this
0x18030b3e5  call    ??1Value@Json@@QEAA@XZ; Json::Value::~Value(void)
0x18030b3ea  lea     rcx, [rsp+518h+var_4C0]
0x18030b3ef  call    ?type@Value@Json@@QEBA?AW4ValueType@2@XZ; Json::Value::type(void)
0x18030b3f4  mov     ecx, eax
0x18030b3f6  call    cdp__JsonValueTypeToDataValueType
0x18030b3fb  mov     ebx, eax
0x18030b3fd  lea     r8, [rsp+518h+var_128]
0x18030b405  lea     rdx, [rsp+518h+var_2F0]
0x18030b40d  mov     rcx, [rdi]
0x18030b410  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UDataVariant@ConnectedDevices@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UDataVariant@ConnectedDevices@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UDataVariant@ConnectedDevices@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18030b415  mov     rcx, [rax]
0x18030b418  mov     [rcx+40h], ebx
0x18030b41b  lea     rcx, [rsp+518h+var_4C0]
0x18030b420  call    ?type@Value@Json@@QEBA?AW4ValueType@2@XZ; Json::Value::type(void)
0x18030b425  mov     ecx, eax
0x18030b427  sub     ecx, 1
0x18030b42a  jz      loc_18030BDC6
0x18030b430  sub     ecx, 1
0x18030b433  jz      loc_18030BDB2
0x18030b439  sub     ecx, 1
0x18030b43c  jz      loc_18030BD80
0x18030b442  sub     ecx, 1
0x18030b445  jz      loc_18030BD2E
0x18030b44b  sub     ecx, 1
0x18030b44e  jz      loc_18030BCFF
0x18030b454  sub     ecx, 1
0x18030b457  jz      loc_18030B50C
0x18030b45d  cmp     ecx, 1
0x18030b460  jnz     loc_18030BE5B
0x18030b466  lea     rax, aValuesethelper; "..\\valuesethelpers.cpp"
0x18030b46d  mov     [rsp+518h+var_148], rax
0x18030b475  mov     [rsp+518h+var_140], 105h
0x18030b480  mov     ebx, 83760002h
0x18030b485  mov     [rsp+518h+var_4E4], ebx
0x18030b489  call    cs:__imp_GetCurrentThreadId
0x18030b48f  mov     eax, eax
0x18030b491  mov     [rsp+518h+var_4D8], rax
0x18030b496  lea     rax, [rsp+518h+var_4D8]
0x18030b49b  mov     [rsp+518h+var_4F0], rax
0x18030b4a0  lea     rax, [rsp+518h+var_140]
0x18030b4a8  mov     [rsp+518h+var_4F8], rax
0x18030b4ad  lea     r9, [rsp+518h+var_148]
0x18030b4b5  lea     r8, [rsp+518h+var_4E4]
0x18030b4ba  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18030b4c1  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18030b4c6  lea     rdx, [rsp+518h+var_148]
0x18030b4ce  lea     rcx, [rsp+518h+var_480]
0x18030b4d6  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18030b4db  mov     r9, rax
0x18030b4de  mov     ecx, ebx
0x18030b4e0  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18030b4e5  mov     r8, rax
0x18030b4e8  mov     edx, ebx
0x18030b4ea  lea     rcx, [rsp+518h+var_298]
0x18030b4f2  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18030b4f7  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18030b4fe  lea     rcx, [rsp+518h+var_298]; pExceptionObject
0x18030b506  call    _CxxThrowException_0
0x18030b50c  xor     r13d, r13d
0x18030b50f  mov     [rsp+518h+var_4C4], r13d
0x18030b514  lea     rcx, [rsp+518h+var_4C0]; this
0x18030b519  call    ?size@Value@Json@@QEBAIXZ; Json::Value::size(void)
0x18030b51e  test    eax, eax
0x18030b520  jz      short loc_18030B563
0x18030b522  xor     edx, edx
0x18030b524  lea     rcx, [rsp+518h+var_4C0]
0x18030b529  call    ??AValue@Json@@QEBAAEBV01@H@Z; Json::Value::operator[](int)
0x18030b52e  mov     rcx, rax
0x18030b531  call    ?type@Value@Json@@QEBA?AW4ValueType@2@XZ; Json::Value::type(void)
0x18030b536  mov     ecx, eax
0x18030b538  call    cdp__JsonValueTypeToDataValueArrayType
0x18030b53d  mov     r13d, eax
0x18030b540  mov     [rsp+518h+var_4C4], eax
0x18030b544  lea     r8, [rsp+518h+var_128]
0x18030b54c  lea     rdx, [rsp+518h+var_2E0]
0x18030b554  mov     rcx, [rdi]
0x18030b557  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UDataVariant@ConnectedDevices@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UDataVariant@ConnectedDevices@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UDataVariant@ConnectedDevices@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18030b55c  mov     rcx, [rax]
0x18030b55f  mov     [rcx+40h], r13d
0x18030b563  xor     r14b, r14b
0x18030b566  mov     [rsp+518h+var_4E8], r14b
0x18030b56b  xor     esi, esi
0x18030b56d  mov     [rsp+518h+var_4E4], esi
0x18030b571  lea     rcx, [rsp+518h+var_4C0]; this
0x18030b576  call    ?size@Value@Json@@QEBAIXZ; Json::Value::size(void)
0x18030b57b  cmp     esi, eax
0x18030b57d  jnb     loc_18030BE53
0x18030b583  mov     edx, esi
0x18030b585  lea     rcx, [rsp+518h+var_4C0]
0x18030b58a  call    ??AValue@Json@@QEBAAEBV01@I@Z; Json::Value::operator[](uint)
0x18030b58f  mov     rcx, rax
0x18030b592  call    ?type@Value@Json@@QEBA?AW4ValueType@2@XZ; Json::Value::type(void)
0x18030b597  mov     ecx, eax
0x18030b599  call    cdp__JsonValueTypeToDataValueArrayType
0x18030b59e  lea     ecx, [r13-19h]
0x18030b5a2  cmp     ecx, 1
0x18030b5a5  ja      short loc_18030B5B3
0x18030b5a7  lea     ecx, [rax-19h]
0x18030b5aa  cmp     ecx, 1
0x18030b5ad  jbe     loc_18030B662
0x18030b5b3  cmp     r13d, eax
0x18030b5b6  jz      loc_18030B662
0x18030b5bc  lea     rax, aValuesethelper; "..\\valuesethelpers.cpp"
0x18030b5c3  mov     [rsp+518h+var_148], rax
0x18030b5cb  mov     [rsp+518h+var_140], 0B7h
0x18030b5d6  mov     ebx, 83760002h
0x18030b5db  mov     [rsp+518h+var_4E4], ebx
0x18030b5df  call    cs:__imp_GetCurrentThreadId
0x18030b5e5  mov     eax, eax
0x18030b5e7  mov     [rsp+518h+var_4D8], rax
0x18030b5ec  lea     rax, [rsp+518h+var_4D8]
0x18030b5f1  mov     [rsp+518h+var_4F0], rax
0x18030b5f6  lea     rax, [rsp+518h+var_140]
0x18030b5fe  mov     [rsp+518h+var_4F8], rax
0x18030b603  lea     r9, [rsp+518h+var_148]
0x18030b60b  lea     r8, [rsp+518h+var_4E4]
0x18030b610  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18030b617  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18030b61c  lea     rdx, [rsp+518h+var_148]
0x18030b624  lea     rcx, [rsp+518h+var_480]
0x18030b62c  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18030b631  mov     r9, rax
0x18030b634  mov     ecx, ebx
0x18030b636  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18030b63b  mov     r8, rax
0x18030b63e  mov     edx, ebx
0x18030b640  lea     rcx, [rsp+518h+var_228]
0x18030b648  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18030b64d  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18030b654  lea     rcx, [rsp+518h+var_228]; pExceptionObject
0x18030b65c  call    _CxxThrowException_0
0x18030b662  mov     edx, esi
0x18030b664  lea     rcx, [rsp+518h+var_4C0]
0x18030b669  call    ??AValue@Json@@QEBAAEBV01@I@Z; Json::Value::operator[](uint)
0x18030b66e  mov     rcx, rax
0x18030b671  call    ?type@Value@Json@@QEBA?AW4ValueType@2@XZ; Json::Value::type(void)
0x18030b676  mov     ecx, eax
0x18030b678  test    eax, eax
0x18030b67a  jz      short loc_18030B6B7
0x18030b67c  sub     ecx, 1
0x18030b67f  jz      loc_18030BA22
0x18030b685  sub     ecx, 1
0x18030b688  jz      loc_18030B815
0x18030b68e  sub     ecx, 1
0x18030b691  jz      loc_18030B9AD
0x18030b697  sub     ecx, 1
0x18030b69a  jz      loc_18030B7BB
0x18030b6a0  sub     ecx, 1
0x18030b6a3  jz      loc_18030B754
0x18030b6a9  sub     ecx, 1
0x18030b6ac  jz      short loc_18030B6B7
0x18030b6ae  cmp     ecx, 1
0x18030b6b1  jnz     loc_18030BCF8
0x18030b6b7  lea     rax, aValuesethelper; "..\\valuesethelpers.cpp"
0x18030b6be  mov     [rsp+518h+var_4D8], rax
0x18030b6c3  mov     [rsp+518h+var_4D0], 0BEh
0x18030b6cb  mov     ebx, 83760002h
0x18030b6d0  mov     [rsp+518h+var_4DC], ebx
0x18030b6d4  call    cs:__imp_GetCurrentThreadId
0x18030b6da  mov     eax, eax
0x18030b6dc  mov     [rsp+518h+var_148], rax
0x18030b6e4  lea     rax, [rsp+518h+var_148]
0x18030b6ec  mov     [rsp+518h+var_4F0], rax
0x18030b6f1  lea     rax, [rsp+518h+var_4D0]
0x18030b6f6  mov     [rsp+518h+var_4F8], rax
0x18030b6fb  lea     r9, [rsp+518h+var_4D8]
0x18030b700  lea     r8, [rsp+518h+var_4DC]
0x18030b705  lea     rdx, aHr0x08xFileSLi_40; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x18030b70c  call    ??$Log@AEAJAEAPEBDAEAH_K@@YAXW4CDPLogLevel@@PEBDAEAJAEAPEBDAEAH$$QEA_K@Z; Log<long &,char const * &,int &,unsigned __int64>(CDPLogLevel,char const *,long &,char const * &,int &,unsigned __int64 &&)
0x18030b711  lea     rdx, [rsp+518h+var_4D8]
0x18030b716  lea     rcx, [rsp+518h+var_480]
0x18030b71e  call    ?ExceptionStackFromSourceLocationInfo@cdp@@YA?AV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@AEBUCDPSourceLocationInfo@1@@Z; cdp::ExceptionStackFromSourceLocationInfo(cdp::CDPSourceLocationInfo const &)
0x18030b723  mov     r9, rax
0x18030b726  mov     ecx, ebx
0x18030b728  call    ?ErrorCodeToString@cdp@@YAPEBDW4ErrorCode@ConnectedDevices@@@Z; cdp::ErrorCodeToString(ConnectedDevices::ErrorCode)
0x18030b72d  mov     r8, rax
0x18030b730  mov     edx, ebx
0x18030b732  lea     rcx, [rsp+518h+var_180]
0x18030b73a  call    ??0Exception@ConnectedDevices@@QEAA@W4ErrorCode@1@PEBD$$QEAV?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@@Z; ConnectedDevices::Exception::Exception(ConnectedDevices::ErrorCode,char const *,std::vector<ConnectedDevices::Exception::StackFrame> &&)
0x18030b73f  lea     rdx, _TI3?AVException@ConnectedDevices@@; pThrowInfo
0x18030b746  lea     rcx, [rsp+518h+var_180]; pExceptionObject
0x18030b74e  call    _CxxThrowException_0
0x18030b754  lea     r8, [rsp+518h+var_128]
0x18030b75c  lea     rdx, [rsp+518h+var_2D0]
0x18030b764  mov     rcx, [rdi]
0x18030b767  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UDataVariant@ConnectedDevices@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UDataVariant@ConnectedDevices@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UDataVariant@ConnectedDevices@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18030b76c  mov     rbx, [rax]
0x18030b76f  mov     edx, esi
0x18030b771  lea     rcx, [rsp+518h+var_4C0]
0x18030b776  call    ??AValue@Json@@QEBAAEBV01@I@Z; Json::Value::operator[](uint)
0x18030b77b  mov     rcx, rax; this
0x18030b77e  call    ?asBool@Value@Json@@QEBA_NXZ; Json::Value::asBool(void)
0x18030b783  mov     [rsp+518h+var_4E0], al
0x18030b787  mov     rdx, [rbx+1F0h]
0x18030b78e  cmp     rdx, [rbx+1F8h]
0x18030b795  jz      short loc_18030B7A5
0x18030b797  mov     [rdx], al
0x18030b799  inc     qword ptr [rbx+1F0h]
0x18030b7a0  jmp     loc_18030BCF8
0x18030b7a5  lea     r8, [rsp+518h+var_4E0]
0x18030b7aa  lea     rcx, [rbx+1E8h]
0x18030b7b1  call    ??$_Emplace_reallocate@AEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAPEAEQEAEAEAE@Z; std::vector<uchar>::_Emplace_reallocate<uchar &>(uchar * const,uchar &)
0x18030b7b6  jmp     loc_18030BCF8
0x18030b7bb  lea     r8, [rsp+518h+var_128]
0x18030b7c3  lea     rdx, [rsp+518h+var_420]
0x18030b7cb  mov     rcx, [rdi]
0x18030b7ce  call    ??$_Try_emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UDataVariant@ConnectedDevices@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UDataVariant@ConnectedDevices@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UDataVariant@ConnectedDevices@@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,ConnectedDevices::DataVariant>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18030b7d3  mov     rbx, [rax]
0x18030b7d6  mov     edx, esi
0x18030b7d8  lea     rcx, [rsp+518h+var_4C0]
0x18030b7dd  call    ??AValue@Json@@QEBAAEBV01@I@Z; Json::Value::operator[](uint)
0x18030b7e2  lea     rdx, [rsp+518h+var_148]
  ... truncated ...
```
