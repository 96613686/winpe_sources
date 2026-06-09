# Microsoft::RdpNano::RawUdpRdpTransportFilter::OnNetworkInactivityTimerFired(std::chrono::duration<__int64,std::ratio<1,1000>>)

- ea: `0x18011e680`
- end: `0x18011ffaa`
- name: `?OnNetworkInactivityTimerFired@RawUdpRdpTransportFilter@RdpNano@Microsoft@@IEAAXV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@@Z`
- size: `6442`
- prototype: ``
- caller_count: `1`
- callee_count: `44`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180122130`

## callees

- `0x18000d9c0`
- `0x18000da90`
- `0x180015bb8`
- `0x180017380`
- `0x180017494`
- `0x1800187a8`
- `0x180018b94`
- `0x180018ea4`
- `0x18001902c`
- `0x1800191b4`
- `0x18001955c`
- `0x18001a768`
- `0x18001ab4c`
- `0x18001bed4`
- `0x18001dad8`
- `0x18001db78`
- `0x18001f814`
- `0x18001f860`
- `0x18001f8d4`
- `0x18001f970`
- `0x180024760`
- `0x180028820`
- `0x18002a8ec`
- `0x18003302c`
- `0x1800334a8`
- `0x1800386d0`
- `0x18003c308`
- `0x1801170a8`
- `0x1801171b8`
- `0x1801187ac`
- `0x1801195b8`
- `0x180119f84`
- `0x18011abb0`
- `0x18011e680`
- `0x1801b0ab4`
- `0x1801b3b70`
- `0x1802e2464`
- `0x1802ea40c`
- `0x180311d5c`
- `0x180311dbc`
- `0x180311e54`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x18011f471`: `Microsoft::Basix::Dct.Smiles.LinkPoolSize`
- `0x18011f883`: `numSmilesLinks`
- `0x18011edbe`: `Microsoft::Basix::Dct.NetworkExceptionRead`
- `0x18011ee8d`: `Microsoft::Basix::Dct.NetworkExceptionWrite`
- `0x18011fe8c`: `Network inactivity timer - Close reason is already set, not reporting network drop.`

## pseudocode

```c
// Hidden C++ exception states: #wind=111
__int64 __fastcall Microsoft::RdpNano::RawUdpRdpTransportFilter::OnNetworkInactivityTimerFired(__int64 a1)
{
  int v2; // esi
  struct Microsoft::Basix::Instrumentation::ActivityManager *v3; // rax
  __int64 v4; // r9
  __int64 v5; // rdi
  _QWORD *v6; // rax
  volatile signed __int32 *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  __int128 *v10; // rdx
  __int64 v11; // rdi
  volatile signed __int32 *v12; // rbx
  unsigned int v13; // ebx
  volatile signed __int32 *v14; // rbx
  __int64 v15; // rax
  __int64 *v16; // rbx
  volatile signed __int32 *v17; // r12
  __int64 v18; // rdi
  __int64 Property; // rax
  char v20; // bl
  __int64 v21; // rax
  unsigned __int64 v22; // rdi
  unsigned __int64 v23; // rdi
  unsigned int v24; // edi
  __int64 v25; // rax
  const void *v26; // rax
  unsigned int v27; // ebx
  __int64 *v28; // rdi
  __int64 v29; // rbx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rbx
  __int64 v33; // rdx
  __int64 v34; // rbx
  char v35; // al
  __int64 *v36; // rax
  const char *v37; // r9
  __int64 v38; // rbx
  volatile signed __int32 *v39; // rbx
  __int64 v40; // rax
  const void *v41; // rax
  unsigned int v42; // ebx
  __int64 v43; // rax
  const void *v44; // rax
  volatile signed __int32 *v45; // rbx
  __int64 *v46; // rbx
  __int64 v47; // rax
  unsigned int v48; // r13d
  int v49; // esi
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int64 v53; // rdx
  _BYTE *v54; // rax
  int v55; // esi
  int v56; // esi
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rdx
  __int64 v60; // rdx
  int v61; // esi
  __int64 v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rdx
  __int64 v65; // rdx
  __int64 v66; // rax
  __int64 v67; // rdx
  __int64 v68; // rdx
  __int64 v69; // rdx
  __int64 v70; // rax
  __int64 v71; // rdx
  unsigned int v72; // esi
  __int64 v73; // rdx
  __int64 v74; // rdx
  volatile signed __int32 *v75; // rbx
  volatile signed __int32 *v76; // rbx
  struct Microsoft::Basix::Instrumentation::ActivityManager *v77; // rax
  char *v79; // [rsp+20h] [rbp-E0h]
  int Str; // [rsp+28h] [rbp-D8h]
  const char *v81; // [rsp+30h] [rbp-D0h]
  _BYTE v82[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v83; // [rsp+54h] [rbp-ACh]
  __int64 v84; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v85; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v86; // [rsp+68h] [rbp-98h] BYREF
  __int128 v87; // [rsp+78h] [rbp-88h]
  __int128 v88; // [rsp+88h] [rbp-78h] BYREF
  __int128 v89; // [rsp+98h] [rbp-68h]
  __int64 *v90; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v91; // [rsp+B0h] [rbp-50h]
  __int64 *v92; // [rsp+B8h] [rbp-48h]
  __int128 v93; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v94; // [rsp+D0h] [rbp-30h]
  _BYTE v95[32]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v96[2]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v97[2]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v98[32]; // [rsp+140h] [rbp+40h] BYREF
  _OWORD v99[2]; // [rsp+160h] [rbp+60h] BYREF
  _OWORD v100[2]; // [rsp+180h] [rbp+80h] BYREF
  _OWORD v101[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  _OWORD v102[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  _OWORD v103[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  _OWORD v104[2]; // [rsp+200h] [rbp+100h] BYREF
  _OWORD v105[2]; // [rsp+220h] [rbp+120h] BYREF
  _OWORD v106[2]; // [rsp+240h] [rbp+140h] BYREF
  _OWORD v107[2]; // [rsp+260h] [rbp+160h] BYREF
  _OWORD v108[2]; // [rsp+280h] [rbp+180h] BYREF
  _OWORD v109[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _OWORD v110[2]; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 v111[2]; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int128 v112; // [rsp+2F0h] [rbp+1F0h]
  __int64 v113[4]; // [rsp+300h] [rbp+200h] BYREF
  __int64 v114[4]; // [rsp+320h] [rbp+220h] BYREF
  __int64 v115[4]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE v116[32]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v117[32]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v118[32]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v119[32]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _BYTE v120[32]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _BYTE v121[32]; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v122[32]; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v123[32]; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v124[32]; // [rsp+460h] [rbp+360h] BYREF
  _BYTE v125[32]; // [rsp+480h] [rbp+380h] BYREF
  _BYTE v126[32]; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v127[32]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v128[32]; // [rsp+4E0h] [rbp+3E0h] BYREF
  _BYTE v129[32]; // [rsp+500h] [rbp+400h] BYREF
  _BYTE v130[32]; // [rsp+520h] [rbp+420h] BYREF
  _BYTE v131[32]; // [rsp+540h] [rbp+440h] BYREF
  _BYTE v132[32]; // [rsp+560h] [rbp+460h] BYREF
  _BYTE v133[32]; // [rsp+580h] [rbp+480h] BYREF
  _BYTE v134[176]; // [rsp+5A0h] [rbp+4A0h] BYREF
  int v135[4]; // [rsp+650h] [rbp+550h] BYREF
  __int128 v136; // [rsp+660h] [rbp+560h]
  int v137[4]; // [rsp+670h] [rbp+570h] BYREF
  __int128 v138; // [rsp+688h] [rbp+588h] BYREF
  __int128 v139; // [rsp+698h] [rbp+598h] BYREF
  __int64 v140; // [rsp+6A8h] [rbp+5A8h]
  unsigned __int64 v141; // [rsp+6B0h] [rbp+5B0h]
  _BYTE v142[16]; // [rsp+6B8h] [rbp+5B8h] BYREF

  v2 = 0;
  v83 = 0;
  v3 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
  LOBYTE(v4) = 1;
  Microsoft::Basix::Instrumentation::ActivityManager::SetActivityId(v3, v142, a1 + 1560, v4);
  v5 = *(_QWORD *)std::chrono::steady_clock::now(&v85) / 1000000LL;
  if ( v5 - (unsigned int)(*(_DWORD *)(a1 + 1164) - 2000) >= *(_QWORD *)(a1 + 1192) )
  {
    *(_OWORD *)v135 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v135);
    if ( *(_QWORD *)v135 && *(_BYTE *)(*(_QWORD *)v135 + 128LL) )
    {
      v13 = *(_DWORD *)(a1 + 1164);
      v86 = 0;
      v87 = 0;
      std::string::_Construct<1,char const *>(
        &v86,
        "The controller hasn't received any packets in the last %d ms due to network issues, shuting down now ...",
        104);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned long>(
        v135,
        "RDPNANO",
        &v86,
        v13);
      std::string::_Tidy_deallocate(&v86);
    }
    v14 = *(volatile signed __int32 **)&v135[2];
    if ( *(_QWORD *)&v135[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v135[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    v138 = 0;
    __ExceptionPtrCreate(&v138);
    LODWORD(v85) = 0;
    LOBYTE(v84) = 0;
    v91 = 0;
    v139 = 0;
    v15 = *(_QWORD *)(a1 + 1112);
    if ( v15 )
      _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
    v16 = *(__int64 **)(a1 + 1104);
    v92 = v16;
    *(_QWORD *)&v139 = v16;
    v17 = *(volatile signed __int32 **)(a1 + 1112);
    *((_QWORD *)&v139 + 1) = v17;
    if ( v16 )
    {
      v18 = *(_QWORD *)std::chrono::steady_clock::now(&v85) / 1000LL;
      v86 = 0;
      v87 = 0u;
      std::string::_Construct<1,char const *>(
        &v86,
        "The controller hasn't received any packets in the last 17000 ms",
        63);
      v91 = Microsoft::RdpNano::RawUdpRdpTransportFilter::DumpLastIOInfo(a1, &v86);
      v86 = 0;
      v87 = 0;
      std::string::_Construct<1,char const *>(&v86, "Microsoft::Basix::Dct.ICE.Turn.LackOfCap", 40);
      Property = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v16 + 5, v137, &v86);
      v82[0] = 0;
      v20 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<bool>(
              *(_QWORD *)(Property + 16),
              v82);
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v137);
      std::string::_Tidy_deallocate(&v86);
      v86 = 0;
      v87 = 0;
      std::string::_Construct<1,char const *>(&v86, "Microsoft::Basix::Dct.ICE.Turn.LackOfCapTime", 44);
      v21 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v92 + 5, v137, &v86);
      v85 = 0;
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::chrono::duration<__int64,std::ratio<1,1000000>>>(
        *(_QWORD *)(v21 + 16),
        &v90,
        &v85);
      v22 = (__int64)((unsigned __int128)((v18 - (__int64)v90) * (__int128)0x431BDE82D7B634DBLL) >> 64) >> 18;
      v23 = (v22 >> 63) + v22;
      v85 = v23;
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v137);
      std::string::_Tidy_deallocate(&v86);
      if ( v20 && (unsigned int)v23 < 0x4B0 )
      {
        LOBYTE(v84) = 1;
        v24 = 5;
        v88 = 0;
        v89 = 0;
        std::string::_Construct<1,char const *>(
          &v88,
          "C:\\__w\\1\\s\\rdnanolib\\rdnano\\RawUdpRdpTransportFilter.cpp",
          56);
        *(_OWORD *)v135 = 0;
        v136 = 0;
        std::string::_Construct<1,char const *>(v135, "Turn server 508 error", 21);
        v86 = 0;
        v87 = 0;
        std::string::_Construct<1,char const *>(&v86, "TurnServerLackOfCap", 19);
        v25 = Microsoft::Basix::Dct::DCTException::DCTException(
                (unsigned int)v134,
                0,
                (unsigned int)&v86,
                (unsigned int)v135,
                (__int64)&v88,
                1603);
        v26 = (const void *)std::make_exception_ptr<Microsoft::Basix::Dct::DCTException>(v137, v25);
        __ExceptionPtrAssign(&v138, v26);
        __ExceptionPtrDestroy(v137);
        std::string::_Tidy_deallocate(&v86);
        std::string::_Tidy_deallocate(v135);
        std::string::_Tidy_deallocate(&v88);
        *(_OWORD *)v135 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v135);
        if ( *(_QWORD *)v135 && *(_BYTE *)(*(_QWORD *)v135 + 128LL) )
        {
          v27 = *(_DWORD *)(a1 + 1164);
          v88 = 0;
          v89 = 0;
          std::string::_Construct<1,char const *>(
            &v88,
            "The UDP transport hasn't received any packets in the last %d ms due to turn server down. closing UDP now ...",
            108);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned long>(
            v135,
            "RDPNANO",
            &v88,
            v27);
          std::string::_Tidy_deallocate(&v88);
        }
      }
      else
      {
        v88 = 0;
        v89 = 0;
        std::string::_Construct<1,char const *>(&v88, "Microsoft::Basix::Dct.NetworkExceptionRead", 42);
        v28 = v92 + 5;
        v29 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v92 + 5, &v86, &v88);
        *(_OWORD *)v137 = 0;
        __ExceptionPtrCreate(v137);
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(
          *(_QWORD *)(v29 + 16),
          v135,
          v137);
        v2 = 196608;
        v83 = 196608;
        __ExceptionPtrAssign(&v138, v135);
        __ExceptionPtrDestroy(v135);
        __ExceptionPtrDestroy(v137);
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v86);
        std::string::_Tidy_deallocate(&v88);
        if ( !(unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                                 &v138,
                                 v30) )
        {
          v88 = 0;
          v89 = 0;
          std::string::_Construct<1,char const *>(&v88, "Microsoft::Basix::Dct.NetworkExceptionWrite", 43);
          v32 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v28, &v86, &v88);
          *(_OWORD *)v137 = 0;
          __ExceptionPtrCreate(v137);
          boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(
            *(_QWORD *)(v32 + 16),
            v135,
            v137);
          v2 = 983040;
          v83 = 983040;
          __ExceptionPtrAssign(&v138, v135);
          __ExceptionPtrDestroy(v135);
          __ExceptionPtrDestroy(v137);
          boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v86);
          std::string::_Tidy_deallocate(&v88);
        }
        if ( !(unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                                 &v138,
                                 v31) )
        {
          v88 = 0;
          v89 = 0;
          std::string::_Construct<1,char const *>(&v88, "Microsoft::Basix::Dct.LastException", 35);
          v34 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v28, &v86, &v88);
          *(_OWORD *)v137 = 0;
          __ExceptionPtrCreate(v137);
          boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::exception_ptr>(
            *(_QWORD *)(v34 + 16),
            v135,
            v137);
          v2 |= 0x300000u;
          v83 = v2;
          __ExceptionPtrAssign(&v138, v135);
          __ExceptionPtrDestroy(v135);
          __ExceptionPtrDestroy(v137);
          boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v86);
          std::string::_Tidy_deallocate(&v88);
        }
        v35 = std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                &v138,
                v33);
        *(_OWORD *)v135 = 0;
        if ( v35 )
        {
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v135);
          if ( *(_QWORD *)v135 && *(_BYTE *)(*(_QWORD *)v135 + 128LL) )
          {
            v36 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v95, &v138);
            v38 = (__int64)v36;
            if ( (unsigned __int64)v36[3] > 0xF )
              v38 = *v36;
            v88 = 0;
            v89 = 0;
            std::string::_Construct<1,char const *>(
              &v88,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v37,
              v79,
              Str,
              v81);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)v135,
              (unsigned int)"BASIX_NETWORK_DCT",
              (unsigned int)&v88,
              (unsigned int)"NetworkDown due to winsock layer exception",
              v38,
              (__int64)"C:\\__w\\1\\s\\rdnanolib\\rdnano\\RawUdpRdpTransportFilter.cpp",
              87,
              (__int64)"Microsoft::RdpNano::RawUdpRdpTransportFilter::OnNetworkInactivityTimerFired");
            std::string::_Tidy_deallocate(&v88);
            std::string::_Tidy_deallocate(v95);
          }
          v39 = *(volatile signed __int32 **)&v135[2];
          if ( *(_QWORD *)&v135[2] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v135[2] + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
              if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
            }
          }
          v24 = 9;
        }
        else
        {
          v24 = 3;
          v136 = 0;
          std::string::_Construct<1,char const *>(
            v135,
            "C:\\__w\\1\\s\\rdnanolib\\rdnano\\RawUdpRdpTransportFilter.cpp",
            56);
          v86 = 0;
          v87 = 0;
          std::string::_Construct<1,char const *>(
            &v86,
            "UDP Transport at transport layer not receiving any traffic in 17000 ms.",
            71);
          v88 = 0;
          v89 = 0;
          std::string::_Construct<1,char const *>(&v88, "NetworkDrop", 11);
          v40 = Microsoft::Basix::Dct::DCTException::DCTException(
                  (unsigned int)v134,
                  6,
                  (unsigned int)&v88,
                  (unsigned int)&v86,
                  (__int64)v135,
                  1632);
          v41 = (const void *)std::make_exception_ptr<Microsoft::Basix::Dct::DCTException>(v137, v40);
          __ExceptionPtrAssign(&v138, v41);
          __ExceptionPtrDestroy(v137);
          std::string::_Tidy_deallocate(&v88);
          std::string::_Tidy_deallocate(&v86);
          std::string::_Tidy_deallocate(v135);
        }
        *(_OWORD *)v135 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v135);
        if ( *(_QWORD *)v135 && *(_BYTE *)(*(_QWORD *)v135 + 128LL) )
        {
          v42 = *(_DWORD *)(a1 + 1164);
          v88 = 0;
          v89 = 0;
          std::string::_Construct<1,char const *>(
            &v88,
            "The UDP transport hasn't received any packets in the last %d ms due to network issues. closing UDP now ...",
            106);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned long>(
            v135,
            "RDPNANO",
            &v88,
            v42);
          std::string::_Tidy_deallocate(&v88);
        }
      }
    }
    else
    {
      v24 = 3;
      *(_OWORD *)v135 = 0;
      v136 = 0;
      std::string::_Construct<1,char const *>(
        v135,
        "C:\\__w\\1\\s\\rdnanolib\\rdnano\\RawUdpRdpTransportFilter.cpp",
        56);
      v86 = 0;
      v87 = 0;
      std::string::_Construct<1,char const *>(
        &v86,
        "UDP Transport at transport layer not receiving any traffic in 17000 ms.",
        71);
      v88 = 0;
      v89 = 0;
      std::string::_Construct<1,char const *>(&v88, "NetworkDrop", 11);
      v43 = Microsoft::Basix::Dct::DCTException::DCTException(
              (unsigned int)v134,
              6,
              (unsigned int)&v88,
              (unsigned int)&v86,
              (__int64)v135,
              1643);
      v44 = (const void *)std::make_exception_ptr<Microsoft::Basix::Dct::DCTException>(v137, v43);
      __ExceptionPtrAssign(&v138, v44);
      __ExceptionPtrDestroy(v137);
      std::string::_Tidy_deallocate(&v88);
      std::string::_Tidy_deallocate(&v86);
      std::string::_Tidy_deallocate(v135);
      *(_OWORD *)v135 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v135);
      if ( *(_QWORD *)v135 && *(_BYTE *)(*(_QWORD *)v135 + 128LL) )
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,char const *>(
          (int)v135,
          (int)"RD_CHECKPOINT",
          0,
          (int)"UDPTransport",
          "NetworkDrop",
          "UDP Transport at transport layer not receiving any traffic in 17000 ms, and no winsock info",
          (__int64)&Str1);
    }
    v45 = *(volatile signed __int32 **)&v135[2];
    if ( *(_QWORD *)&v135[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v135[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
        if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
      }
    }
    LODWORD(v90) = 0;
    if ( (unsigned __int8)std::_Atomic_storage<enum Microsoft::Basix::Pattern::IThreadedObject::State,4>::compare_exchange_strong(
                            a1 + 1400,
                            &v90,
                            v24) )
    {
      v46 = v92;
      v88 = 0;
      v89 = 0;
      std::string::_Construct<1,char const *>(&v88, "Microsoft::Basix::Dct.Smiles.LinkPoolSize", 41);
      v47 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v46 + 5, &v86, &v88);
      LODWORD(v90) = 0;
      v48 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<unsigned int>(
              *(_QWORD *)(v47 + 16),
              &v90);
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v86);
      std::string::_Tidy_deallocate(&v88);
      *(_OWORD *)v137 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v137);
      if ( *(_QWORD *)v137 && *(_BYTE *)(*(_QWORD *)v137 + 128LL) )
      {
        v92 = v111;
        if ( (_BYTE)v84 )
        {
          v93 = 0;
          v94 = 0;
          std::string::_Construct<1,char const *>(&v93, "true", 4);
          v49 = v2 | 1;
          v83 = v49;
          memset(v97, 0, sizeof(v97));
          std::string::_Construct<1,char const *>(v97, ":", 1);
          v49 |= 2u;
          v83 = v49;
          memset(v96, 0, sizeof(v96));
          std::string::_Construct<1,char const *>(v96, "\"", 1);
          v49 |= 4u;
          v83 = v49;
          memset(v110, 0, sizeof(v110));
          std::string::_Construct<1,char const *>(v110, "\"", 1);
          v49 |= 8u;
          v83 = v49;
          v50 = std::operator+<char>(v133, v110, "turnLackOfCapFlagged");
          v49 |= 0x10u;
          v83 = v49;
          LOBYTE(v51) = v82[0];
          std::string::string(v95, v51, v50, v96);
          v49 |= 0x20u;
          v83 = v49;
          LOBYTE(v52) = v82[0];
          std::string::string(v98, v52, v95, v97);
          v49 |= 0x40u;
          v83 = v49;
          LOBYTE(v53) = v82[0];
          std::string::string(v127, v53, v98, &v93);
          v54 = v127;
          v55 = v49 | 0x80;
        }
        else
        {
          memset(v109, 0, sizeof(v109));
          std::string::_Construct<1,char const *>(v109, "false", 5);
          v56 = v2 | 0x100;
          v83 = v56;
          memset(v108, 0, sizeof(v108));
          std::string::_Construct<1,char const *>(v108, ":", 1);
          v56 |= 0x200u;
          v83 = v56;
          memset(v107, 0, sizeof(v107));
          std::string::_Construct<1,char const *>(v107, "\"", 1);
          v56 |= 0x400u;
          v83 = v56;
          memset(v106, 0, sizeof(v106));
          std::string::_Construct<1,char const *>(v106, "\"", 1);
          v56 |= 0x800u;
          v83 = v56;
          v57 = std::operator+<char>(v132, v106, "turnLackOfCapFlagged");
          v56 |= 0x1000u;
          v83 = v56;
          LOBYTE(v58) = v82[0];
          std::string::string(v126, v58, v57, v107);
          v56 |= 0x2000u;
          v83 = v56;
          LOBYTE(v59) = v82[0];
          std::string::string(v125, v59, v126, v108);
          v56 |= 0x4000u;
          v83 = v56;
          LOBYTE(v60) = v82[0];
          std::string::string(v124, v60, v125, v109);
          v54 = v124;
          v55 = v56 | 0x8000;
        }
        v83 = v55;
        *(_OWORD *)v111 = *(_OWORD *)v54;
        v112 = *((_OWORD *)v54 + 1);
        *((_QWORD *)v54 + 2) = 0;
        *((_QWORD *)v54 + 3) = 15;
        *v54 = 0;
        v90 = v113;
        std::_Integral_to_string<char,unsigned int>(v128, v48);
        v61 = v55 | 0x400000;
        v83 = v61;
        memset(v105, 0, sizeof(v105));
        std::string::_Construct<1,char const *>(v105, ":", 1);
        memset(v104, 0, sizeof(v104));
        std::string::_Construct<1,char const *>(v104, "\"", 1);
        memset(v103, 0, sizeof(v103));
        std::string::_Construct<1,char const *>(v103, "\"", 1);
        v62 = std::operator+<char>(v131, v103, "numSmilesLinks");
        LOBYTE(v63) = v82[0];
        std::string::string(v123, v63, v62, v104);
        v61 |= 0x800000u;
        v83 = v61;
        LOBYTE(v64) = v82[0];
        std::string::string(v122, v64, v123, v105);
        v61 |= 0x1000000u;
        v83 = v61;
        LOBYTE(v65) = v82[0];
        std::string::string(v113, v65, v122, v128);
        v61 |= 0x2000000u;
        v83 = v61;
        *(_QWORD *)v135 = v114;
        std::_Integral_to_string<char,unsigned int>(v121, (unsigned int)v85);
        v61 |= 0x4000000u;
        v83 = v61;
        memset(v102, 0, sizeof(v102));
        std::string::_Construct<1,char const *>(v102, ":", 1);
        memset(v101, 0, sizeof(v101));
        std::string::_Construct<1,char const *>(v101, "\"", 1);
        memset(v100, 0, sizeof(v100));
        std::string::_Construct<1,char const *>(v100, "\"", 1);
        v66 = std::operator+<char>(v130, v100, "tsInSecAgoTurnLackOfCapFlagged");
        LOBYTE(v67) = v82[0];
        std::string::string(v120, v67, v66, v101);
        v61 |= 0x8000000u;
        v83 = v61;
        LOBYTE(v68) = v82[0];
        std::string::string(v119, v68, v120, v102);
        v61 |= 0x10000000u;
        v83 = v61;
        LOBYTE(v69) = v82[0];
        std::string::string(v114, v69, v119, v121);
        v61 |= 0x20000000u;
        v83 = v61;
        std::_Integral_to_string<char,int>(v118, v91);
        v61 |= 0x40000000u;
        v83 = v61;
        memset(v99, 0, sizeof(v99));
        std::string::_Construct<1,char const *>(v99, ":", 1);
        v86 = 0;
        v87 = 0;
        std::string::_Construct<1,char const *>(&v86, "\"", 1);
        v88 = 0;
        v89 = 0;
        std::string::_Construct<1,char const *>(&v88, "\"", 1);
        v70 = std::operator+<char>(v129, &v88, "diffFromLastWSReceivedTimeInMs");
        LOBYTE(v71) = v82[0];
        std::string::string(v117, v71, v70, &v86);
        v72 = v61 | 0x80000000;
        v83 = v72;
        LOBYTE(v73) = v82[0];
        std::string::string(v116, v73, v117, v99);
        LOBYTE(v74) = v82[0];
        std::string::string(v115, v74, v116, v118);
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string>(
          (int)v137,
          (int)"RD_CHECKPOINT",
          0,
          (int)"UDPTransport",
          "NetworkDrop",
          "UDP Transport at winsock layer not receiving any traffic in 17000 ms",
          (__int64)v115,
          (__int64)v114,
          (__int64)v113,
          (__int64)v111);
        std::string::_Tidy_deallocate(v116);
        std::string::_Tidy_deallocate(v117);
        std::string::_Tidy_deallocate(v129);
        std::string::_Tidy_deallocate(&v88);
        std::string::_Tidy_deallocate(&v86);
        std::string::_Tidy_deallocate(v99);
        std::string::_Tidy_deallocate(v118);
        std::string::_Tidy_deallocate(v119);
        std::string::_Tidy_deallocate(v120);
        std::string::_Tidy_deallocate(v130);
        std::string::_Tidy_deallocate(v100);
        std::string::_Tidy_deallocate(v101);
        std::string::_Tidy_deallocate(v102);
        std::string::_Tidy_deallocate(v121);
        std::string::_Tidy_deallocate(v122);
        std::string::_Tidy_deallocate(v123);
        std::string::_Tidy_deallocate(v131);
        std::string::_Tidy_deallocate(v103);
        std::string::_Tidy_deallocate(v104);
        std::string::_Tidy_deallocate(v105);
        std::string::_Tidy_deallocate(v128);
        if ( (v72 & 0x8000) != 0 )
        {
          LOWORD(v72) = v72 & 0x7FFF;
          std::string::_Tidy_deallocate(v124);
        }
        if ( (v72 & 0x4000) != 0 )
        {
          LOWORD(v72) = v72 & 0xBFFF;
          std::string::_Tidy_deallocate(v125);
        }
        if ( (v72 & 0x2000) != 0 )
        {
          LOWORD(v72) = v72 & 0xDFFF;
          std::string::_Tidy_deallocate(v126);
        }
        if ( (v72 & 0x1000) != 0 )
        {
          LOWORD(v72) = v72 & 0xEFFF;
          std::string::_Tidy_deallocate(v132);
        }
        if ( (v72 & 0x800) != 0 )
        {
          LOWORD(v72) = v72 & 0xF7FF;
          std::string::_Tidy_deallocate(v106);
        }
        if ( (v72 & 0x400) != 0 )
        {
          LOWORD(v72) = v72 & 0xFBFF;
          std::string::_Tidy_deallocate(v107);
        }
        if ( (v72 & 0x200) != 0 )
        {
          LOWORD(v72) = v72 & 0xFDFF;
          std::string::_Tidy_deallocate(v108);
        }
        if ( (v72 & 0x100) != 0 )
          std::string::_Tidy_deallocate(v109);
        if ( (v72 & 0x80u) != 0 )
        {
          LOBYTE(v72) = v72 & 0x7F;
          std::string::_Tidy_deallocate(v127);
        }
        if ( (v72 & 0x40) != 0 )
        {
          LOBYTE(v72) = v72 & 0xBF;
          std::string::_Tidy_deallocate(v98);
        }
        if ( (v72 & 0x20) != 0 )
        {
          LOBYTE(v72) = v72 & 0xDF;
          std::string::_Tidy_deallocate(v95);
        }
        if ( (v72 & 0x10) != 0 )
        {
          LOBYTE(v72) = v72 & 0xEF;
          std::string::_Tidy_deallocate(v133);
        }
        if ( (v72 & 8) != 0 )
        {
          LOBYTE(v72) = v72 & 0xF7;
          std::string::_Tidy_deallocate(v110);
        }
        if ( (v72 & 4) != 0 )
        {
          LOBYTE(v72) = v72 & 0xFB;
          std::string::_Tidy_deallocate(v96);
        }
        if ( (v72 & 2) != 0 )
        {
          LOBYTE(v72) = v72 & 0xFD;
          std::string::_Tidy_deallocate(v97);
        }
        if ( (v72 & 1) != 0 )
          std::string::_Tidy_deallocate(&v93);
      }
      v75 = *(volatile signed __int32 **)&v137[2];
      if ( *(_QWORD *)&v137[2] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v137[2] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v75)(v75);
          if ( _InterlockedExchangeAdd(v75 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v75 + 8LL))(v75);
        }
      }
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 120LL))(a1, &v138);
      Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnClosed(
        (Microsoft::Basix::Dct::DCTBaseChannelImplNoProp *)a1,
        0);
    }
    else
    {
      *(_OWORD *)v137 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v137);
      if ( *(_QWORD *)v137 && *(_BYTE *)(*(_QWORD *)v137 + 128LL) )
      {
        v93 = 0;
        v94 = 0;
        std::string::_Construct<1,char const *>(
          &v93,
          "Network inactivity timer - Close reason is already set, not reporting network drop.",
          83);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
          v137,
          "RDPNANO",
          &v93);
        std::string::_Tidy_deallocate(&v93);
      }
      v76 = *(volatile signed __int32 **)&v137[2];
      if ( *(_QWORD *)&v137[2] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v137[2] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
          if ( _InterlockedExchangeAdd(v76 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
        }
      }
    }
    if ( v17 )
    {
      if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    __ExceptionPtrDestroy(&v138);
  }
  else
  {
    v6 = (_QWORD *)Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::ITimerCallback>(
                     a1 + *(int *)(*(_QWORD *)(a1 + 8) + 4LL) + 8LL,
                     &v139);
    *(_OWORD *)v135 = 0;
    if ( v6[1] )
    {
      *(_QWORD *)v135 = *v6;
      *(_QWORD *)&v135[2] = v6[1];
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&v135[2] + 12LL));
    }
    v85 = (unsigned __int64)*(unsigned int *)(a1 + 1164) >> 2;
    Microsoft::Basix::Timer::Setup(a1 + 1376, &v85, v135);
    v7 = (volatile signed __int32 *)*((_QWORD *)&v139 + 1);
    if ( *((_QWORD *)&v139 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v139 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    v85 = v5 - *(_QWORD *)(a1 + 1192);
    v8 = Microsoft::Basix::ToString<__int64>(v98, &v85, 0, 6);
    v9 = std::operator+<char>(v95, "The controller hasn't received any packets in the last", v8);
    std::operator+<char>(&v139, v9, " ms, but it is not yet time to shut down.");
    std::string::_Tidy_deallocate(v95);
    std::string::_Tidy_deallocate(v98);
    v86 = 0;
    v87 = 0u;
    v10 = &v139;
    if ( v141 > 0xF )
      v10 = (__int128 *)v139;
    std::string::_Construct<2,char const *>(&v86, v10, v140);
    Microsoft::RdpNano::RawUdpRdpTransportFilter::DumpLastIOInfo(a1, &v86);
    *(_OWORD *)v135 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v135);
    if ( *(_QWORD *)v135 && *(_BYTE *)(*(_QWORD *)v135 + 128LL) )
    {
      _mm_lfence();
      v11 = v5 - *(_QWORD *)(a1 + 1192);
      v86 = 0;
      v87 = 0;
      std::string::_Construct<1,char const *>(&v86, "The controller hasn't received any packets in the last %d ms", 60);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,__int64>(
        v135,
        "RDPNANO",
        &v86,
        v11);
      std::string::_Tidy_deallocate(&v86);
    }
    v12 = *(volatile signed __int32 **)&v135[2];
    if ( *(_QWORD *)&v135[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v135[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    std::string::_Tidy_deallocate(&v139);
  }
  v77 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
  return (*(__int64 (__fastcall **)(struct Microsoft::Basix::Instrumentation::ActivityManager *, __int128 *, _BYTE *))(*(_QWORD *)v77 + 32LL))(
           v77,
           &v139,
           v142);
}

```

## disassembly

```asm
0x18011e680  mov     rax, rsp
0x18011e683  mov     [rax+10h], rbx
0x18011e687  mov     [rax+18h], rsi
0x18011e68b  mov     [rax+20h], rdi
0x18011e68f  push    rbp
0x18011e690  push    r12
0x18011e692  push    r13
0x18011e694  push    r14
0x18011e696  push    r15
0x18011e698  lea     rbp, [rax-5F8h]
0x18011e69f  mov     eax, 6D0h
0x18011e6a4  call    _alloca_probe
0x18011e6a9  sub     rsp, rax
0x18011e6ac  mov     rax, cs:__security_cookie
0x18011e6b3  xor     rax, rsp
0x18011e6b6  mov     [rbp+5F0h+var_28], rax
0x18011e6bd  mov     r15, rcx
0x18011e6c0  xor     r12d, r12d
0x18011e6c3  mov     esi, r12d
0x18011e6c6  mov     [rsp+6F0h+var_69C], r12d
0x18011e6cb  call    ?GlobalManager@ActivityManager@Instrumentation@Basix@Microsoft@@SAAEAV1234@XZ; Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager(void)
0x18011e6d0  lea     r8, [r15+618h]
0x18011e6d7  mov     r9b, 1
0x18011e6da  lea     rdx, [rbp+5F0h+var_38]
0x18011e6e1  mov     rcx, rax
0x18011e6e4  call    ?SetActivityId@ActivityManager@Instrumentation@Basix@Microsoft@@QEAA?AUGuid@34@AEBU534@_N@Z; Microsoft::Basix::Instrumentation::ActivityManager::SetActivityId(Microsoft::Basix::Guid const &,bool)
0x18011e6e9  nop
0x18011e6ea  lea     rcx, [rsp+6F0h+var_690]
0x18011e6ef  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18011e6f4  mov     rcx, [rax]
0x18011e6f7  mov     rax, 431BDE82D7B634DBh
0x18011e701  imul    rcx
0x18011e704  mov     rdi, rdx
0x18011e707  sar     rdi, 12h
0x18011e70b  mov     rax, rdi
0x18011e70e  shr     rax, 3Fh
0x18011e712  add     rdi, rax
0x18011e715  mov     ecx, [r15+48Ch]
0x18011e71c  sub     ecx, 7D0h
0x18011e722  mov     rax, rdi
0x18011e725  sub     rax, rcx
0x18011e728  cmp     rax, [r15+4A8h]
0x18011e72f  jge     loc_18011E975
0x18011e735  mov     rax, [r15+8]
0x18011e739  movsxd  rcx, dword ptr [rax+4]
0x18011e73d  add     rcx, 8
0x18011e741  add     rcx, r15
0x18011e744  lea     rdx, [rbp+5F0h+var_58]
0x18011e74b  call    ??$GetSharedPtr@VITimerCallback@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$shared_ptr@VITimerCallback@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::ITimerCallback>(void)
0x18011e750  nop
0x18011e751  xorps   xmm0, xmm0
0x18011e754  movdqu  xmmword ptr [rbp+5F0h+var_A0], xmm0
0x18011e75c  cmp     [rax+8], r12
0x18011e760  jz      short loc_18011E77B
0x18011e762  mov     rcx, [rax]
0x18011e765  mov     qword ptr [rbp+5F0h+var_A0], rcx
0x18011e76c  mov     rax, [rax+8]
0x18011e770  mov     qword ptr [rbp+5F0h+var_A0+8], rax
0x18011e777  lock inc dword ptr [rax+0Ch]
0x18011e77b  mov     eax, [r15+48Ch]
0x18011e782  shr     rax, 2
0x18011e786  mov     qword ptr [rsp+6F0h+var_690], rax
0x18011e78b  lea     rcx, [r15+560h]
0x18011e792  lea     r8, [rbp+5F0h+var_A0]
0x18011e799  lea     rdx, [rsp+6F0h+var_690]
0x18011e79e  call    ?Setup@Timer@Basix@Microsoft@@QEAAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@V?$weak_ptr@VITimerCallback@Basix@Microsoft@@@6@@Z; Microsoft::Basix::Timer::Setup(std::chrono::duration<__int64,std::ratio<1,1000>> const &,std::weak_ptr<Microsoft::Basix::ITimerCallback>)
0x18011e7a3  nop
0x18011e7a4  or      r14d, 0FFFFFFFFh
0x18011e7a8  mov     rbx, qword ptr [rbp+5F0h+var_58+8]
0x18011e7af  test    rbx, rbx
0x18011e7b2  jz      short loc_18011E7ED
0x18011e7b4  mov     eax, r14d
0x18011e7b7  lock xadd [rbx+8], eax
0x18011e7bc  add     eax, r14d
0x18011e7bf  jnz     short loc_18011E7ED
0x18011e7c1  mov     rax, [rbx]
0x18011e7c4  mov     rcx, rbx
0x18011e7c7  mov     rax, [rax]
0x18011e7ca  call    cs:__guard_dispatch_icall_fptr
0x18011e7d0  mov     eax, r14d
0x18011e7d3  lock xadd [rbx+0Ch], eax
0x18011e7d8  add     eax, r14d
0x18011e7db  jnz     short loc_18011E7ED
0x18011e7dd  mov     rax, [rbx]
0x18011e7e0  mov     rcx, rbx
0x18011e7e3  mov     rax, [rax+8]
0x18011e7e7  call    cs:__guard_dispatch_icall_fptr
0x18011e7ed  mov     rax, rdi
0x18011e7f0  sub     rax, [r15+4A8h]
0x18011e7f7  mov     qword ptr [rsp+6F0h+var_690], rax
0x18011e7fc  mov     r9d, 6
0x18011e802  xor     r8d, r8d
0x18011e805  lea     rdx, [rsp+6F0h+var_690]
0x18011e80a  lea     rcx, [rbp+5F0h+var_5B0]
0x18011e80e  call    ??$ToString@_J@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEB_JHH@Z; Microsoft::Basix::ToString<__int64>(__int64 const &,int,int)
0x18011e813  nop
0x18011e814  mov     r8, rax
0x18011e817  lea     rdx, aTheControllerH_2; "The controller hasn't received any pack"...
0x18011e81e  lea     rcx, [rbp+5F0h+var_610]
0x18011e822  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18011e827  nop
0x18011e828  lea     r8, aMsButItIsNotYe; " ms, but it is not yet time to shut dow"...
0x18011e82f  mov     rdx, rax
0x18011e832  lea     rcx, [rbp+5F0h+var_58]
0x18011e839  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18011e83e  nop
0x18011e83f  lea     rcx, [rbp+5F0h+var_610]
0x18011e843  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18011e848  nop
0x18011e849  lea     rcx, [rbp+5F0h+var_5B0]
0x18011e84d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18011e852  xorps   xmm0, xmm0
0x18011e855  movups  [rsp+6F0h+var_690+8], xmm0
0x18011e85a  mov     qword ptr [rsp+6F0h+var_680+8], r12
0x18011e85f  mov     [rbp+5F0h+var_670], r12
0x18011e863  lea     rdx, [rbp+5F0h+var_58]
0x18011e86a  cmp     [rbp+5F0h+var_40], 0Fh
0x18011e872  cmova   rdx, qword ptr [rbp+5F0h+var_58]
0x18011e87a  mov     r8, [rbp+5F0h+var_48]
0x18011e881  lea     rcx, [rsp+6F0h+var_690+8]
0x18011e886  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x18011e88b  lea     rdx, [rsp+6F0h+var_690+8]
0x18011e890  mov     rcx, r15
0x18011e893  call    ?DumpLastIOInfo@RawUdpRdpTransportFilter@RdpNano@Microsoft@@IEAAHV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::RdpNano::RawUdpRdpTransportFilter::DumpLastIOInfo(std::string)
0x18011e898  xorps   xmm0, xmm0
0x18011e89b  movups  xmmword ptr [rbp+5F0h+var_A0], xmm0
0x18011e8a2  lea     rcx, [rbp+5F0h+var_A0]
0x18011e8a9  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x18011e8ae  nop
0x18011e8af  mov     rax, qword ptr [rbp+5F0h+var_A0]
0x18011e8b6  test    rax, rax
0x18011e8b9  jz      short loc_18011E91E
0x18011e8bb  cmp     [rax+80h], r12b
0x18011e8c2  jz      short loc_18011E91E
0x18011e8c4  lfence
0x18011e8c7  sub     rdi, [r15+4A8h]
0x18011e8ce  xorps   xmm0, xmm0
0x18011e8d1  movups  [rsp+6F0h+var_690+8], xmm0
0x18011e8d6  xorps   xmm1, xmm1
0x18011e8d9  movdqu  [rsp+6F0h+var_680+8], xmm1
0x18011e8df  mov     r8d, 3Ch ; '<'
0x18011e8e5  lea     rdx, aTheControllerH_3; "The controller hasn't received any pack"...
0x18011e8ec  lea     rcx, [rsp+6F0h+var_690+8]
0x18011e8f1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18011e8f6  nop
0x18011e8f7  mov     r9, rdi
0x18011e8fa  lea     r8, [rsp+6F0h+var_690+8]
0x18011e8ff  lea     rdx, aRdpnano; "RDPNANO"
0x18011e906  lea     rcx, [rbp+5F0h+var_A0]
0x18011e90d  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@_J@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@_J@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,__int64>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,__int64)
0x18011e912  nop
0x18011e913  lea     rcx, [rsp+6F0h+var_690+8]
0x18011e918  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18011e91d  nop
0x18011e91e  mov     rbx, qword ptr [rbp+5F0h+var_A0+8]
0x18011e925  test    rbx, rbx
0x18011e928  jz      short loc_18011E964
0x18011e92a  mov     eax, r14d
0x18011e92d  lock xadd [rbx+8], eax
0x18011e932  add     eax, r14d
0x18011e935  jnz     short loc_18011E964
0x18011e937  mov     rax, [rbx]
0x18011e93a  mov     rcx, rbx
0x18011e93d  mov     rax, [rax]
0x18011e940  call    cs:__guard_dispatch_icall_fptr
0x18011e946  mov     eax, r14d
0x18011e949  lock xadd [rbx+0Ch], eax
0x18011e94e  add     eax, r14d
0x18011e951  jnz     short loc_18011E964
0x18011e953  mov     rax, [rbx]
0x18011e956  mov     rcx, rbx
0x18011e959  mov     rax, [rax+8]
0x18011e95d  call    cs:__guard_dispatch_icall_fptr
0x18011e963  nop
0x18011e964  lea     rcx, [rbp+5F0h+var_58]
0x18011e96b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18011e970  jmp     loc_18011FF53
0x18011e975  xorps   xmm0, xmm0
0x18011e978  movups  xmmword ptr [rbp+5F0h+var_A0], xmm0
0x18011e97f  lea     rcx, [rbp+5F0h+var_A0]
0x18011e986  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x18011e98b  nop
0x18011e98c  lea     r13, aRdpnano; "RDPNANO"
0x18011e993  mov     rax, qword ptr [rbp+5F0h+var_A0]
0x18011e99a  test    rax, rax
0x18011e99d  jz      short loc_18011E9FB
0x18011e99f  cmp     [rax+80h], r12b
0x18011e9a6  jz      short loc_18011E9FB
0x18011e9a8  mov     ebx, [r15+48Ch]
0x18011e9af  xorps   xmm0, xmm0
0x18011e9b2  movups  [rsp+6F0h+var_690+8], xmm0
0x18011e9b7  xorps   xmm1, xmm1
0x18011e9ba  movdqu  [rsp+6F0h+var_680+8], xmm1
0x18011e9c0  mov     r8d, 68h ; 'h'
0x18011e9c6  lea     rdx, aTheControllerH_1; "The controller hasn't received any pack"...
0x18011e9cd  lea     rcx, [rsp+6F0h+var_690+8]
0x18011e9d2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18011e9d7  nop
0x18011e9d8  mov     r9d, ebx
0x18011e9db  lea     r8, [rsp+6F0h+var_690+8]
0x18011e9e0  mov     rdx, r13
0x18011e9e3  lea     rcx, [rbp+5F0h+var_A0]
0x18011e9ea  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@K@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@K@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,ulong>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,ulong)
0x18011e9ef  nop
0x18011e9f0  lea     rcx, [rsp+6F0h+var_690+8]
0x18011e9f5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18011e9fa  nop
0x18011e9fb  or      r14d, 0FFFFFFFFh
0x18011e9ff  mov     rbx, qword ptr [rbp+5F0h+var_A0+8]
0x18011ea06  test    rbx, rbx
0x18011ea09  jz      short loc_18011EA44
0x18011ea0b  mov     eax, r14d
0x18011ea0e  lock xadd [rbx+8], eax
0x18011ea13  add     eax, r14d
0x18011ea16  jnz     short loc_18011EA44
0x18011ea18  mov     rax, [rbx]
0x18011ea1b  mov     rcx, rbx
0x18011ea1e  mov     rax, [rax]
0x18011ea21  call    cs:__guard_dispatch_icall_fptr
0x18011ea27  mov     eax, r14d
0x18011ea2a  lock xadd [rbx+0Ch], eax
0x18011ea2f  add     eax, r14d
0x18011ea32  jnz     short loc_18011EA44
0x18011ea34  mov     rax, [rbx]
0x18011ea37  mov     rcx, rbx
0x18011ea3a  mov     rax, [rax+8]
0x18011ea3e  call    cs:__guard_dispatch_icall_fptr
0x18011ea44  xorps   xmm1, xmm1
0x18011ea47  movdqu  [rbp+5F0h+var_68], xmm1
0x18011ea4f  lea     rcx, [rbp+5F0h+var_68]; void *
0x18011ea56  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18011ea5b  nop
0x18011ea5c  mov     dword ptr [rsp+6F0h+var_690], r12d
0x18011ea61  mov     byte ptr [rsp+6F0h+var_698], r12b
0x18011ea66  mov     [rbp+5F0h+var_640], r12d
0x18011ea6a  xorps   xmm0, xmm0
0x18011ea6d  movups  [rbp+5F0h+var_58], xmm0
0x18011ea74  mov     rax, [r15+458h]
0x18011ea7b  test    rax, rax
0x18011ea7e  jz      short loc_18011EA84
0x18011ea80  lock inc dword ptr [rax+8]
0x18011ea84  mov     rbx, [r15+450h]
0x18011ea8b  mov     [rbp+5F0h+var_638], rbx
0x18011ea8f  mov     qword ptr [rbp+5F0h+var_58], rbx
0x18011ea96  mov     r12, [r15+458h]
0x18011ea9d  mov     qword ptr [rbp+5F0h+var_58+8], r12
0x18011eaa4  test    rbx, rbx
0x18011eaa7  jz      loc_18011F28F
0x18011eaad  lea     rcx, [rsp+6F0h+var_690]
0x18011eab2  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18011eab7  mov     rcx, [rax]
0x18011eaba  mov     rax, 20C49BA5E353F7CFh
0x18011eac4  imul    rcx
0x18011eac7  mov     rdi, rdx
0x18011eaca  sar     rdi, 7
0x18011eace  mov     rax, rdi
0x18011ead1  shr     rax, 3Fh
0x18011ead5  add     rdi, rax
0x18011ead8  xorps   xmm0, xmm0
0x18011eadb  movups  [rsp+6F0h+var_690+8], xmm0
0x18011eae0  mov     qword ptr [rsp+6F0h+var_680+8], 0
0x18011eae9  mov     [rbp+5F0h+var_670], 0
0x18011eaf1  mov     r8d, 3Fh ; '?'
0x18011eaf7  lea     rdx, aTheControllerH; "The controller hasn't received any pack"...
0x18011eafe  lea     rcx, [rsp+6F0h+var_690+8]
0x18011eb03  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18011eb08  lea     rdx, [rsp+6F0h+var_690+8]
0x18011eb0d  mov     rcx, r15
0x18011eb10  call    ?DumpLastIOInfo@RawUdpRdpTransportFilter@RdpNano@Microsoft@@IEAAHV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::RdpNano::RawUdpRdpTransportFilter::DumpLastIOInfo(std::string)
0x18011eb15  mov     [rbp+5F0h+var_640], eax
0x18011eb18  xorps   xmm0, xmm0
0x18011eb1b  movups  [rsp+6F0h+var_690+8], xmm0
0x18011eb20  xorps   xmm1, xmm1
0x18011eb23  movdqu  [rsp+6F0h+var_680+8], xmm1
0x18011eb29  mov     r8d, 28h ; '('
0x18011eb2f  lea     rdx, aMicrosoftBasix_145; "Microsoft::Basix::Dct.ICE.Turn.LackOfCa"...
0x18011eb36  lea     rcx, [rsp+6F0h+var_690+8]
0x18011eb3b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18011eb40  nop
0x18011eb41  lea     r8, [rsp+6F0h+var_690+8]
0x18011eb46  lea     rdx, [rbp+5F0h+var_80]
0x18011eb4d  lea     rcx, [rbx+28h]
0x18011eb51  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x18011eb56  nop
0x18011eb57  mov     [rsp+6F0h+var_6A0], 0
0x18011eb5c  lea     rdx, [rsp+6F0h+var_6A0]
0x18011eb61  mov     rcx, [rax+10h]
0x18011eb65  call    ??$get_value@_N@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA_NAEB_N@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<bool>(bool const &)
0x18011eb6a  mov     bl, al
0x18011eb6c  lea     rcx, [rbp+5F0h+var_80]
0x18011eb73  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x18011eb78  nop
0x18011eb79  lea     rcx, [rsp+6F0h+var_690+8]
0x18011eb7e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18011eb83  xorps   xmm0, xmm0
0x18011eb86  movups  [rsp+6F0h+var_690+8], xmm0
0x18011eb8b  xorps   xmm1, xmm1
0x18011eb8e  movdqu  [rsp+6F0h+var_680+8], xmm1
0x18011eb94  mov     r8d, 2Ch ; ','
0x18011eb9a  lea     rdx, aMicrosoftBasix_65; "Microsoft::Basix::Dct.ICE.Turn.LackOfCa"...
  ... truncated ...
```
