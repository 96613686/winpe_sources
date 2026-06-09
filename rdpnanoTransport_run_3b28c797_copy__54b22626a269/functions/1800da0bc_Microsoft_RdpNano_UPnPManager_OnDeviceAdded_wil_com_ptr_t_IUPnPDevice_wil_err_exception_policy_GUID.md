# Microsoft::RdpNano::UPnPManager::OnDeviceAdded(wil::com_ptr_t<IUPnPDevice,wil::err_exception_policy>,_GUID)

- ea: `0x1800da0bc`
- end: `0x1800daf7b`
- name: `?OnDeviceAdded@UPnPManager@RdpNano@Microsoft@@AEAAXV?$com_ptr_t@UIUPnPDevice@@Uerr_exception_policy@wil@@@wil@@U_GUID@@@Z`
- size: `3775`
- prototype: ``
- caller_count: `2`
- callee_count: `38`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d7610`
- `0x1800d76f0`

## callees

- `0x18000d9c0`
- `0x18000da90`
- `0x180015bb8`
- `0x180018d1c`
- `0x18001902c`
- `0x1800191b4`
- `0x18001ab4c`
- `0x18001b890`
- `0x18001bbdc`
- `0x18002a8ec`
- `0x180045eb4`
- `0x1800d2ea0`
- `0x1800d32c8`
- `0x1800d38d0`
- `0x1800d3af0`
- `0x1800d3c5c`
- `0x1800d4284`
- `0x1800d4444`
- `0x1800d47d8`
- `0x1800d5d68`
- `0x1800d6154`
- `0x1800d6410`
- `0x1800d7998`
- `0x1800d7cd0`
- `0x1800d88b8`
- `0x1800d9c80`
- `0x1800da0bc`
- `0x1800dc750`
- `0x180249064`
- `0x180249184`
- `0x180249198`
- `0x1802497c8`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x180330b40`
- `0x180375c40`
- `0x180376720`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800dabae`
- `OLEAUT32!__imp_VariantInit` at `0x1800dabbd`
- `OLEAUT32!__imp_VariantInit` at `0x1800dabcc`
- `OLEAUT32!__imp_VariantInit` at `0x1800dabae`
- `OLEAUT32!__imp_VariantInit` at `0x1800dabbd`
- `OLEAUT32!__imp_VariantInit` at `0x1800dabcc`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800dabdd`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x1800dabdd`

## string_xrefs

- `0x1800da3f4`: `Device %s already exists in database. Ignoring.`
- `0x1800da929`: `Attempting fall-back UPnP device enumeration...`
- `0x1800daa56`: `Successfully found IGD device. Looking for IGD NAT Service`
- `0x1800dad40`: `Successfully found IGD NAT service. UDN=%s, interface=%s, externalAddress=%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=59 #try_helpers=1
__int64 __fastcall Microsoft::RdpNano::UPnPManager::OnDeviceAdded(__int64 a1, _QWORD *a2, _OWORD *a3)
{
  _OWORD *v3; // r15
  _QWORD *v4; // rsi
  __int64 v5; // r13
  __int64 v6; // rdi
  __int64 result; // rax
  volatile signed __int32 *v8; // r14
  signed __int32 v9; // eax
  bool v10; // zf
  volatile signed __int32 *v11; // r14
  signed __int32 v12; // eax
  __int64 v13; // rdi
  volatile signed __int32 *v14; // r14
  volatile signed __int32 *v15; // r14
  __int64 v16; // rdi
  int v17; // r14d
  const void *v18; // r9
  volatile signed __int32 *v19; // r14
  __int64 v20; // rcx
  __int64 v21; // r14
  __int128 *v22; // rcx
  char *v23; // rcx
  char *v24; // r10
  __int64 *v25; // r14
  __int64 *v26; // r11
  __int64 *v27; // r11
  __int64 *v28; // rdx
  __int64 *v29; // rax
  signed __int64 v30; // r10
  __int128 *v31; // rdx
  const char *v32; // r9
  volatile signed __int32 *v33; // r14
  volatile signed __int32 *v34; // r14
  __int64 v35; // rcx
  __int64 *UPnPDeviveByEnumeration; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  volatile signed __int32 *v39; // r14
  __int64 *UPnPService; // rax
  __int64 v41; // rcx
  const char *v42; // rdx
  __int64 v43; // rax
  __int64 v44; // r14
  _QWORD *v45; // rdx
  const char *v46; // r9
  volatile signed __int32 *v47; // r14
  void *v48; // rax
  __int64 v49; // rax
  __int64 v50; // rdx
  volatile signed __int32 *v51; // r14
  volatile signed __int32 *v52; // r14
  __int64 v53; // rax
  __int64 v54; // rax
  volatile signed __int32 *v55; // rbx
  __int64 v56; // rax
  __int64 v57; // rax
  volatile signed __int32 *v58; // rbx
  __int64 *v59; // rax
  __int64 v60; // rdx
  __int64 v61; // rcx
  const char *v62; // [rsp+20h] [rbp-328h]
  __int128 v63; // [rsp+40h] [rbp-308h] BYREF
  __int128 v64; // [rsp+50h] [rbp-2F8h]
  __int128 v65; // [rsp+60h] [rbp-2E8h] BYREF
  __m128i v66; // [rsp+70h] [rbp-2D8h]
  _QWORD *v67; // [rsp+80h] [rbp-2C8h]
  __int64 v68; // [rsp+88h] [rbp-2C0h]
  __int128 v69; // [rsp+90h] [rbp-2B8h] BYREF
  __int128 v70; // [rsp+A0h] [rbp-2A8h] BYREF
  __int64 v71; // [rsp+B0h] [rbp-298h]
  __int64 v72; // [rsp+B8h] [rbp-290h]
  const std::exception *v73; // [rsp+C0h] [rbp-288h] BYREF
  const std::exception *v74; // [rsp+C8h] [rbp-280h] BYREF
  char v75[8]; // [rsp+D8h] [rbp-270h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-268h] BYREF
  VARIANTARG v77; // [rsp+F8h] [rbp-250h] BYREF
  VARIANTARG v78; // [rsp+110h] [rbp-238h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+128h] [rbp-220h] BYREF
  _BYTE v80[144]; // [rsp+140h] [rbp-208h] BYREF
  __int128 v81; // [rsp+1D0h] [rbp-178h] BYREF
  __int128 v82; // [rsp+1E0h] [rbp-168h] BYREF
  char *v83[2]; // [rsp+1F0h] [rbp-158h] BYREF
  __int128 v84; // [rsp+200h] [rbp-148h]
  __int128 v85; // [rsp+210h] [rbp-138h] BYREF
  __m128i si128; // [rsp+220h] [rbp-128h]
  __int128 v87; // [rsp+230h] [rbp-118h] BYREF
  _QWORD v88[4]; // [rsp+240h] [rbp-108h] BYREF
  _BYTE v89[32]; // [rsp+260h] [rbp-E8h] BYREF
  _BYTE v90[144]; // [rsp+280h] [rbp-C8h] BYREF

  v3 = a3;
  v4 = a2;
  v5 = a1;
  v68 = a1;
  v67 = a2;
  *(_QWORD *)&v87 = a3;
  v6 = *a2;
  if ( *a2 )
  {
    if ( !memcmp(a3, &GUID_NULL, 0x10u) )
    {
      v81 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v81);
      result = v81;
      if ( (_QWORD)v81 && *(_BYTE *)(v81 + 128) )
      {
        v63 = 0;
        v64 = 0;
        std::string::_Construct<1,char const *>(&v63, "Found UPnP device for unspecified interface. Ignoring", 53);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(
          &v81,
          "RDPNANO",
          &v63);
        result = std::string::_Tidy_deallocate(&v63);
      }
      v11 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
      if ( *((_QWORD *)&v81 + 1) )
      {
        v12 = _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF);
        v10 = v12 == 1;
        result = (unsigned int)(v12 - 1);
        if ( v10 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
          result = (unsigned int)_InterlockedDecrement(v11 + 3);
          if ( !(_DWORD)result )
            result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        }
      }
      if ( *v4 )
        return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 16LL))(*v4);
    }
    else
    {
      *(_QWORD *)&v82 = v6;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
      Microsoft::RdpNano::_anonymous_namespace_::GetComString_wil::com_ptr_t_IUPnPService_wil::err_exception_policy__long____cdecl_IUPnPService::___wchar_t______(
        v88,
        &v82,
         IUPnPDevice::`vcall'{96,{flat}});
      v69 = 0;
      Microsoft::RdpNano::UPnPManager::FindDeviceForUdn(v5, &v69, v88);
      if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(&v69) )
      {
        v87 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v87);
        if ( (_QWORD)v87 && *(_BYTE *)(v87 + 128) )
        {
          *(_QWORD *)&v81 = v89;
          v13 = Microsoft::Basix::ToString<std::string>(v89, v88, 0, 6);
          v63 = 0;
          v64 = 0;
          std::string::_Construct<1,char const *>(
            &v63,
            "Device %s already exists in database. Ignoring.",
            (const char *)0x2F);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(
            &v87,
            "RDPNANO",
            &v63,
            v13);
          std::string::_Tidy_deallocate(&v63);
        }
        v14 = (volatile signed __int32 *)*((_QWORD *)&v87 + 1);
        if ( *((_QWORD *)&v87 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v87 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
            if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
          }
        }
        v15 = (volatile signed __int32 *)*((_QWORD *)&v69 + 1);
        if ( *((_QWORD *)&v69 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v69 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
            if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
          }
        }
        result = std::string::_Tidy_deallocate(v88);
        if ( *v4 )
          return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 16LL))(*v4);
      }
      else
      {
        v82 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v82);
        if ( (_QWORD)v82 && *(_BYTE *)(v82 + 128) )
        {
          v16 = v69;
          *(_QWORD *)&v81 = &v65;
          v17 = Microsoft::Basix::ToString<std::string>(&v65, v88, 0, 6);
          v63 = 0;
          v64 = 0;
          std::string::_Construct<1,char const *>(
            &v63,
            "Found device %s (0x%p) for guid %s",
            (const char *)0x22,
            v18,
            v62);
          *(_OWORD *)v83 = *v3;
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,std::string,Microsoft::RdpNano::UPnPManager::Device *,_GUID>(
            (unsigned int)&v82,
            (unsigned int)"RDPNANO",
            (unsigned int)&v63,
            v17,
            v16,
            (__int64)v83);
          std::string::_Tidy_deallocate(&v63);
        }
        v19 = (volatile signed __int32 *)*((_QWORD *)&v82 + 1);
        if ( *((_QWORD *)&v82 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v82 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
            if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
          }
        }
        try
        {
          v85 = 0;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOBYTE(v85) = 0;
          v20 = *v4;
          *(_QWORD *)&v82 = v20;
          if ( v20 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
          v21 = Microsoft::RdpNano::_anonymous_namespace_::GetComString_wil::com_ptr_t_IUPnPService_wil::err_exception_policy__long____cdecl_IUPnPService::___wchar_t______(
                  &v65,
                  &v82,
                   IUPnPDevice::`vcall'{112,{flat}});
          if ( &v85 != (__int128 *)v21 )
          {
            std::string::_Tidy_deallocate(&v85);
            v85 = *(_OWORD *)v21;
            si128 = *(__m128i *)(v21 + 16);
            *(_QWORD *)(v21 + 16) = 0;
            *(_QWORD *)(v21 + 24) = 15;
            *(_BYTE *)v21 = 0;
          }
          std::string::_Tidy_deallocate(&v65);
        }
        catch ( const std::exception *v73 )
        {
          v81 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v81);
          if ( (_QWORD)v81 && *(_BYTE *)(v81 + 128) )
          {
            v53 = Microsoft::Basix::Exception::CreateDescription(&v63, v73);
            v54 = std::operator+<char>(&v65, "Failed to get UPnP device type : ", v53);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(
              &v81,
              "RDPNANO",
              v54);
            std::string::_Tidy_deallocate(&v65);
            std::string::_Tidy_deallocate(&v63);
          }
          v55 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
          if ( *((_QWORD *)&v81 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v55)(v55);
              if ( _InterlockedExchangeAdd(v55 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v55 + 8LL))(v55);
            }
          }
          v5 = v68;
          v4 = v67;
          v3 = (_OWORD *)v87;
        }
        v22 = &v85;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v22 = (__int128 *)v85;
        v23 = (char *)v22 + si128.m128i_i64[0];
        v24 = (char *)&v85;
        if ( si128.m128i_i64[1] > 0xFuLL )
          v24 = (char *)v85;
        v25 = &qword_18053D300;
        v26 = &qword_18053D300;
        if ( (unsigned __int64)qword_18053D318 > 0xF )
          v26 = (__int64 *)qword_18053D300;
        v27 = (__int64 *)((char *)v26 + qword_18053D310);
        v28 = &qword_18053D300;
        if ( (unsigned __int64)qword_18053D318 > 0xF )
          v28 = (__int64 *)qword_18053D300;
        v29 = v28;
        if ( v24 == v23 )
        {
LABEL_63:
          if ( v29 != v27 )
          {
LABEL_64:
            *(_OWORD *)v83 = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v83);
            if ( v83[0] && v83[0][128] )
            {
              *(_QWORD *)&v81 = &v70;
              v70 = 0;
              v71 = 0;
              v72 = 0;
              v31 = &v85;
              if ( si128.m128i_i64[1] > 0xFuLL )
                v31 = (__int128 *)v85;
              std::string::_Construct<2,char const *>(&v70, v31, si128.m128i_i64[0]);
              *(_QWORD *)&v82 = &v63;
              v63 = 0;
              v64 = 0u;
              if ( (unsigned __int64)qword_18053D318 > 0xF )
                v25 = (__int64 *)qword_18053D300;
              std::string::_Construct<2,char const *>(&v63, v25, qword_18053D310);
              v65 = 0;
              v66 = 0;
              std::string::_Construct<1,char const *>(
                &v65,
                "Device expected was '%s', returned was '%s'",
                (const char *)0x2B,
                v32);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string,std::string>(
                (unsigned int)v83,
                (unsigned int)"RDPNANO",
                (unsigned int)&v65,
                (unsigned int)&v63,
                (__int64)&v70);
              std::string::_Tidy_deallocate(&v65);
            }
            v33 = (volatile signed __int32 *)v83[1];
            if ( v83[1] )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v83[1] + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
                if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
              }
            }
            *(_OWORD *)v83 = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v83);
            if ( v83[0] && v83[0][128] )
            {
              v65 = 0;
              v66 = 0;
              std::string::_Construct<1,char const *>(&v65, "Attempting fall-back UPnP device enumeration...", 47);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
                v83,
                "RDPNANO",
                &v65);
              std::string::_Tidy_deallocate(&v65);
            }
            v34 = (volatile signed __int32 *)v83[1];
            if ( v83[1] )
            {
              if ( !_InterlockedDecrement((volatile signed __int32 *)v83[1] + 2) )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
                if ( !_InterlockedDecrement(v34 + 3) )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
              }
            }
            v35 = *v4;
            *(_QWORD *)&v82 = v35;
            if ( v35 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
            UPnPDeviveByEnumeration = (__int64 *)Microsoft::RdpNano::_anonymous_namespace_::FindUPnPDeviveByEnumeration(
                                                   &v81,
                                                   &v82);
            v37 = *UPnPDeviveByEnumeration;
            *UPnPDeviveByEnumeration = 0;
            v38 = *v4;
            *v4 = v37;
            if ( v38 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
            if ( (_QWORD)v81 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v81 + 16LL))(v81);
          }
        }
        else
        {
          v30 = v24 - (char *)v28;
          while ( v29 != v27 )
          {
            if ( *((_BYTE *)v29 + v30) != *(_BYTE *)v29 )
              goto LABEL_64;
            v29 = (__int64 *)((char *)v29 + 1);
            if ( (char *)v29 + v30 == v23 )
              goto LABEL_63;
          }
        }
        *(_OWORD *)v83 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v83);
        if ( v83[0] && v83[0][128] )
        {
          v65 = 0;
          v66 = 0;
          std::string::_Construct<1,char const *>(
            &v65,
            "Successfully found IGD device. Looking for IGD NAT Service",
            58);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,>(
            v83,
            "RDPNANO",
            &v65);
          std::string::_Tidy_deallocate(&v65);
        }
        v39 = (volatile signed __int32 *)v83[1];
        if ( v83[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v83[1] + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
            if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
          }
        }
        Microsoft::Basix::Dct::SocketAddress::SocketAddress((Microsoft::Basix::Dct::SocketAddress *)v90);
        try
        {
          *(_QWORD *)&v82 = 0;
          UPnPService = (__int64 *)Microsoft::RdpNano::_anonymous_namespace_::FindUPnPService(
                                     &v81,
                                     qword_18053D340,
                                     qword_18053D320,
                                     v4);
          v41 = *UPnPService;
          *UPnPService = 0;
          *(_QWORD *)&v82 = v41;
          if ( (_QWORD)v81 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v81 + 16LL))(v81);
        }
        catch ( const std::exception *v74 )
        {
          *(_OWORD *)v83 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v83);
          if ( v83[0] && v83[0][128] )
          {
            v56 = Microsoft::Basix::Exception::CreateDescription(&v63, v74);
            v57 = std::operator+<char>(&v65, "Failed to get NAT service.Tring NATPPP service instead : ", v56);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(
              v83,
              "RDPNANO",
              v57);
            std::string::_Tidy_deallocate(&v65);
            std::string::_Tidy_deallocate(&v63);
          }
          v58 = (volatile signed __int32 *)v83[1];
          if ( v83[1] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v83[1] + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
              if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
            }
          }
          v59 = (__int64 *)Microsoft::RdpNano::_anonymous_namespace_::FindUPnPService(
                             &v81,
                             qword_18053D380,
                             qword_18053D2C0,
                             v67);
          v60 = *v59;
          *v59 = 0;
          v61 = v82;
          *(_QWORD *)&v82 = v60;
          if ( v61 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
          if ( (_QWORD)v81 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v81 + 16LL))(v81);
          v5 = v68;
          v4 = v67;
          v3 = (_OWORD *)v87;
        }
        *(_OWORD *)v83 = 0;
        v84 = 0;
        std::string::_Construct<1,char const *>(v83, "GetExternalIPAddress", 20);
        v42 = (const char *)v83;
        if ( *((_QWORD *)&v84 + 1) > 0xFu )
          v42 = v83[0];
        _bstr_t::_bstr_t((_bstr_t *)v75, v42);
        VariantInit(&pvarg);
        VariantInit(&v77);
        VariantInit(&v78);
        pvarg.llVal = (LONGLONG)SafeArrayCreateVector(0xCu, 0, 0);
        if ( !pvarg.llVal )
        {
          std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
          throw (std::bad_alloc *)pExceptionObject;
        }
        pvarg.vt = 8204;
        std::string::_Tidy_deallocate(v83);
        Microsoft::RdpNano::_anonymous_namespace_::UPnPAction_std::basic_string_char_std::char_traits_char__std::allocator_char_____::InvokeSync(
          v75,
          v89,
          &v82);
        Microsoft::RdpNano::_anonymous_namespace_::UPnPAction_void_::_UPnPAction_void_(v75);
        v65 = 0;
        v66 = _mm_load_si128((const __m128i *)&_xmm);
        LOBYTE(v65) = 0;
        v43 = Microsoft::Basix::Dct::SocketTools::FromNumericString(v80, v89, &v65, 1);
        Microsoft::Basix::Dct::SocketAddress::operator=(v90, v43);
        std::string::_Tidy_deallocate(&v65);
        *(_OWORD *)v83 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v83);
        if ( v83[0] && v83[0][128] )
        {
          v44 = Microsoft::Basix::Dct::SocketAddress::SocketAddress(
                  (Microsoft::Basix::Dct::SocketAddress *)v80,
                  (const struct Microsoft::Basix::Dct::SocketAddress *)v90);
          *(_QWORD *)&v81 = &v63;
          v63 = 0;
          v64 = 0u;
          v45 = v88;
          if ( v88[3] > 0xFu )
            v45 = (_QWORD *)v88[0];
          std::string::_Construct<2,char const *>(&v63, v45, v88[2]);
          v65 = 0;
          v66 = 0;
          std::string::_Construct<1,char const *>(
            &v65,
            "Successfully found IGD NAT service. UDN=%s, interface=%s, externalAddress=%s",
            (const char *)0x4C,
            v46,
            v62);
          v81 = *v3;
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string,_GUID,Microsoft::Basix::Dct::SocketAddress>(
            (unsigned int)v83,
            (unsigned int)"RDPNANO",
            (unsigned int)&v65,
            (unsigned int)&v63,
            (__int64)&v81,
            v44);
          std::string::_Tidy_deallocate(&v65);
        }
        v47 = (volatile signed __int32 *)v83[1];
        if ( v83[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v83[1] + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
            if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
          }
        }
        v48 = operator new(0xC0u);
        *(_QWORD *)&v81 = v48;
        if ( v48 )
          v49 = Microsoft::RdpNano::UPnPManager::Device::Device(
                  (_DWORD)v48,
                  (unsigned int)v88,
                  (_DWORD)v3,
                  (unsigned int)v90,
                  (__int64)&v82);
        else
          v49 = 0;
        v50 = std::shared_ptr<Microsoft::RdpNano::UPnPManager::Device>::shared_ptr<Microsoft::RdpNano::UPnPManager::Device>(
                v83,
                v49);
        Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>>>::insert(
          v5 + 40,
          v50);
        v51 = (volatile signed __int32 *)v83[1];
        if ( v83[1] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v83[1] + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v51)(v51);
            if ( _InterlockedExchangeAdd(v51 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
          }
        }
        std::string::_Tidy_deallocate(v89);
        if ( (_QWORD)v82 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v82 + 16LL))(v82);
        std::string::_Tidy_deallocate(&v85);
        v52 = (volatile signed __int32 *)*((_QWORD *)&v69 + 1);
        if ( *((_QWORD *)&v69 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v69 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
            if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
          }
        }
        result = std::string::_Tidy_deallocate(v88);
        if ( *v4 )
          return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 16LL))(*v4);
      }
    }
  }
  else
  {
    v81 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v81);
    result = v81;
    if ( (_QWORD)v81 && *(_BYTE *)(v81 + 128) )
    {
      v63 = 0;
      v64 = 0;
      std::string::_Construct<1,char const *>(
        &v63,
        "Found UPnP device for interface %s but device pointer is null. Ignoring.",
        (const char *)0x48);
      *(_OWORD *)v83 = *v3;
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,Microsoft::Basix::Guid>(
        &v81,
        "RDPNANO",
        &v63,
        v83);
      result = std::string::_Tidy_deallocate(&v63);
    }
    v8 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
    if ( *((_QWORD *)&v81 + 1) )
    {
      v9 = _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF);
      v10 = v9 == 1;
      result = (unsigned int)(v9 - 1);
      if ( v10 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        result = (unsigned int)_InterlockedDecrement(v8 + 3);
        if ( !(_DWORD)result )
          result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    if ( *v4 )
      return (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 16LL))(*v4);
  }
  return result;
}

```

## disassembly

```asm
0x1800da0bc  mov     [rsp+arg_18], rbx
0x1800da0c1  push    rsi
0x1800da0c2  push    rdi
0x1800da0c3  push    r13
0x1800da0c5  push    r14
0x1800da0c7  push    r15
0x1800da0c9  mov     eax, 320h
0x1800da0ce  call    _alloca_probe
0x1800da0d3  sub     rsp, rax
0x1800da0d6  mov     rax, cs:__security_cookie
0x1800da0dd  xor     rax, rsp
0x1800da0e0  mov     [rsp+348h+var_38], rax
0x1800da0e8  mov     r15, r8
0x1800da0eb  mov     rsi, rdx
0x1800da0ee  mov     r13, rcx
0x1800da0f1  mov     [rsp+348h+var_2C0], rcx
0x1800da0f9  mov     [rsp+348h+var_2C8], rdx
0x1800da101  mov     qword ptr [rsp+348h+var_118], r8
0x1800da109  mov     rdi, [rdx]
0x1800da10c  xor     ebx, ebx
0x1800da10e  test    rdi, rdi
0x1800da111  jnz     loc_1800DA209
0x1800da117  xorps   xmm0, xmm0
0x1800da11a  movups  [rsp+348h+var_178], xmm0
0x1800da122  lea     rcx, [rsp+348h+var_178]
0x1800da12a  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x1800da12f  nop
0x1800da130  mov     rax, qword ptr [rsp+348h+var_178]
0x1800da138  test    rax, rax
0x1800da13b  jz      short loc_1800DA1A6
0x1800da13d  cmp     [rax+80h], bl
0x1800da143  jz      short loc_1800DA1A6
0x1800da145  xorps   xmm0, xmm0
0x1800da148  movups  [rsp+348h+var_308], xmm0
0x1800da14d  xorps   xmm1, xmm1
0x1800da150  movdqu  [rsp+348h+var_2F8], xmm1
0x1800da156  lea     r8d, [rdi+48h]
0x1800da15a  lea     rdx, aFoundUpnpDevic; "Found UPnP device for interface %s but "...
0x1800da161  lea     rcx, [rsp+348h+var_308]
0x1800da166  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800da16b  nop
0x1800da16c  movups  xmm0, xmmword ptr [r15]
0x1800da170  movdqu  xmmword ptr [rsp+348h+var_158], xmm0
0x1800da179  lea     r9, [rsp+348h+var_158]
0x1800da181  lea     r8, [rsp+348h+var_308]
0x1800da186  lea     rdx, aRdpnano; "RDPNANO"
0x1800da18d  lea     rcx, [rsp+348h+var_178]
0x1800da195  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@UGuid@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@UGuid@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,Microsoft::Basix::Guid>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &,Microsoft::Basix::Guid)
0x1800da19a  nop
0x1800da19b  lea     rcx, [rsp+348h+var_308]
0x1800da1a0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800da1a5  nop
0x1800da1a6  mov     r14, qword ptr [rsp+348h+var_178+8]
0x1800da1ae  test    r14, r14
0x1800da1b1  jz      short loc_1800DA1EE
0x1800da1b3  or      edi, 0FFFFFFFFh
0x1800da1b6  mov     eax, edi
0x1800da1b8  lock xadd [r14+8], eax
0x1800da1be  add     eax, edi
0x1800da1c0  jnz     short loc_1800DA1EE
0x1800da1c2  mov     rax, [r14]
0x1800da1c5  mov     rcx, r14
0x1800da1c8  mov     rax, [rax]
0x1800da1cb  call    cs:__guard_dispatch_icall_fptr
0x1800da1d1  mov     eax, edi
0x1800da1d3  lock xadd [r14+0Ch], eax
0x1800da1d9  add     eax, edi
0x1800da1db  jnz     short loc_1800DA1EE
0x1800da1dd  mov     rax, [r14]
0x1800da1e0  mov     rcx, r14
0x1800da1e3  mov     rax, [rax+8]
0x1800da1e7  call    cs:__guard_dispatch_icall_fptr
0x1800da1ed  nop
0x1800da1ee  mov     rcx, [rsi]
0x1800da1f1  test    rcx, rcx
0x1800da1f4  jz      short loc_1800DA204
0x1800da1f6  mov     rax, [rcx]
0x1800da1f9  mov     rax, [rax+10h]
0x1800da1fd  call    cs:__guard_dispatch_icall_fptr
0x1800da203  nop
0x1800da204  jmp     loc_1800DAF30
0x1800da209  mov     r8d, 10h; Size
0x1800da20f  lea     rdx, GUID_NULL; Buf2
0x1800da216  mov     rcx, r15; Buf1
0x1800da219  call    memcmp
0x1800da21e  test    eax, eax
0x1800da220  jnz     loc_1800DA305
0x1800da226  xorps   xmm0, xmm0
0x1800da229  movups  [rsp+348h+var_178], xmm0
0x1800da231  lea     rcx, [rsp+348h+var_178]
0x1800da239  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x1800da23e  nop
0x1800da23f  mov     rax, qword ptr [rsp+348h+var_178]
0x1800da247  test    rax, rax
0x1800da24a  jz      short loc_1800DA2A2
0x1800da24c  cmp     [rax+80h], bl
0x1800da252  jz      short loc_1800DA2A2
0x1800da254  xorps   xmm0, xmm0
0x1800da257  movups  [rsp+348h+var_308], xmm0
0x1800da25c  xorps   xmm1, xmm1
0x1800da25f  movdqu  [rsp+348h+var_2F8], xmm1
0x1800da265  mov     r8d, 35h ; '5'
0x1800da26b  lea     rdx, aFoundUpnpDevic_0; "Found UPnP device for unspecified inter"...
0x1800da272  lea     rcx, [rsp+348h+var_308]
0x1800da277  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800da27c  nop
0x1800da27d  lea     r8, [rsp+348h+var_308]
0x1800da282  lea     rdx, aRdpnano; "RDPNANO"
0x1800da289  lea     rcx, [rsp+348h+var_178]
0x1800da291  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &)
0x1800da296  nop
0x1800da297  lea     rcx, [rsp+348h+var_308]
0x1800da29c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800da2a1  nop
0x1800da2a2  mov     r14, qword ptr [rsp+348h+var_178+8]
0x1800da2aa  test    r14, r14
0x1800da2ad  jz      short loc_1800DA2EA
0x1800da2af  or      edi, 0FFFFFFFFh
0x1800da2b2  mov     eax, edi
0x1800da2b4  lock xadd [r14+8], eax
0x1800da2ba  add     eax, edi
0x1800da2bc  jnz     short loc_1800DA2EA
0x1800da2be  mov     rax, [r14]
0x1800da2c1  mov     rcx, r14
0x1800da2c4  mov     rax, [rax]
0x1800da2c7  call    cs:__guard_dispatch_icall_fptr
0x1800da2cd  mov     eax, edi
0x1800da2cf  lock xadd [r14+0Ch], eax
0x1800da2d5  add     eax, edi
0x1800da2d7  jnz     short loc_1800DA2EA
0x1800da2d9  mov     rax, [r14]
0x1800da2dc  mov     rcx, r14
0x1800da2df  mov     rax, [rax+8]
0x1800da2e3  call    cs:__guard_dispatch_icall_fptr
0x1800da2e9  nop
0x1800da2ea  mov     rcx, [rsi]
0x1800da2ed  test    rcx, rcx
0x1800da2f0  jz      short loc_1800DA300
0x1800da2f2  mov     rax, [rcx]
0x1800da2f5  mov     rax, [rax+10h]
0x1800da2f9  call    cs:__guard_dispatch_icall_fptr
0x1800da2ff  nop
0x1800da300  jmp     loc_1800DAF30
0x1800da305  mov     qword ptr [rsp+348h+var_168], rdi
0x1800da30d  mov     rax, [rdi]
0x1800da310  mov     rcx, rdi
0x1800da313  mov     rax, [rax+8]
0x1800da317  call    cs:__guard_dispatch_icall_fptr
0x1800da31d  nop
0x1800da31e  lea     r8, ??_9IUPnPDevice@@$BGA@AA; [thunk]: IUPnPDevice::`vcall'{96,{flat}}
0x1800da325  lea     rdx, [rsp+348h+var_168]
0x1800da32d  lea     rcx, [rsp+348h+var_108]
0x1800da335  call    Microsoft__RdpNano___anonymous_namespace___GetComString_wil__com_ptr_t_IUPnPService_wil__err_exception_policy__long____cdecl_IUPnPService_____wchar_t______
0x1800da33a  nop
0x1800da33b  xorps   xmm0, xmm0
0x1800da33e  movups  [rsp+348h+var_2B8], xmm0
0x1800da346  lea     r8, [rsp+348h+var_108]
0x1800da34e  lea     rdx, [rsp+348h+var_2B8]
0x1800da356  mov     rcx, r13
0x1800da359  call    ?FindDeviceForUdn@UPnPManager@RdpNano@Microsoft@@QEAA?AV?$shared_ptr@VDevice@UPnPManager@RdpNano@Microsoft@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::RdpNano::UPnPManager::FindDeviceForUdn(std::string const &)
0x1800da35e  nop
0x1800da35f  xor     edx, edx
0x1800da361  lea     rcx, [rsp+348h+var_2B8]
0x1800da369  call    ??B?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(void)
0x1800da36e  xorps   xmm0, xmm0
0x1800da371  test    al, al
0x1800da373  jz      loc_1800DA4E4
0x1800da379  movups  [rsp+348h+var_118], xmm0
0x1800da381  lea     rcx, [rsp+348h+var_118]
0x1800da389  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800da38e  nop
0x1800da38f  mov     rax, qword ptr [rsp+348h+var_118]
0x1800da397  test    rax, rax
0x1800da39a  jz      loc_1800DA42E
0x1800da3a0  cmp     [rax+80h], bl
0x1800da3a6  jz      loc_1800DA42E
0x1800da3ac  lea     rax, [rsp+348h+var_E8]
0x1800da3b4  mov     qword ptr [rsp+348h+var_178], rax
0x1800da3bc  mov     r9d, 6
0x1800da3c2  xor     r8d, r8d
0x1800da3c5  lea     rdx, [rsp+348h+var_108]
0x1800da3cd  lea     rcx, [rsp+348h+var_E8]
0x1800da3d5  call    ??$ToString@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@HH@Z; Microsoft::Basix::ToString<std::string>(std::string const &,int,int)
0x1800da3da  mov     rdi, rax
0x1800da3dd  xorps   xmm0, xmm0
0x1800da3e0  movups  [rsp+348h+var_308], xmm0
0x1800da3e5  xorps   xmm1, xmm1
0x1800da3e8  movdqu  [rsp+348h+var_2F8], xmm1
0x1800da3ee  mov     r8d, 2Fh ; '/'
0x1800da3f4  lea     rdx, aDeviceSAlready; "Device %s already exists in database. I"...
0x1800da3fb  lea     rcx, [rsp+348h+var_308]
0x1800da400  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800da405  nop
0x1800da406  mov     r9, rdi
0x1800da409  lea     r8, [rsp+348h+var_308]
0x1800da40e  lea     rdx, aRdpnano; "RDPNANO"
0x1800da415  lea     rcx, [rsp+348h+var_118]
0x1800da41d  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@V65@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,std::string)
0x1800da422  nop
0x1800da423  lea     rcx, [rsp+348h+var_308]
0x1800da428  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800da42d  nop
0x1800da42e  mov     r14, qword ptr [rsp+348h+var_118+8]
0x1800da436  or      edi, 0FFFFFFFFh
0x1800da439  test    r14, r14
0x1800da43c  jz      short loc_1800DA476
0x1800da43e  mov     eax, edi
0x1800da440  lock xadd [r14+8], eax
0x1800da446  add     eax, edi
0x1800da448  jnz     short loc_1800DA476
0x1800da44a  mov     rax, [r14]
0x1800da44d  mov     rcx, r14
0x1800da450  mov     rax, [rax]
0x1800da453  call    cs:__guard_dispatch_icall_fptr
0x1800da459  mov     eax, edi
0x1800da45b  lock xadd [r14+0Ch], eax
0x1800da461  add     eax, edi
0x1800da463  jnz     short loc_1800DA476
0x1800da465  mov     rax, [r14]
0x1800da468  mov     rcx, r14
0x1800da46b  mov     rax, [rax+8]
0x1800da46f  call    cs:__guard_dispatch_icall_fptr
0x1800da475  nop
0x1800da476  mov     r14, qword ptr [rsp+348h+var_2B8+8]
0x1800da47e  test    r14, r14
0x1800da481  jz      short loc_1800DA4BB
0x1800da483  mov     eax, edi
0x1800da485  lock xadd [r14+8], eax
0x1800da48b  add     eax, edi
0x1800da48d  jnz     short loc_1800DA4BB
0x1800da48f  mov     rax, [r14]
0x1800da492  mov     rcx, r14
0x1800da495  mov     rax, [rax]
0x1800da498  call    cs:__guard_dispatch_icall_fptr
0x1800da49e  mov     eax, edi
0x1800da4a0  lock xadd [r14+0Ch], eax
0x1800da4a6  add     eax, edi
0x1800da4a8  jnz     short loc_1800DA4BB
0x1800da4aa  mov     rax, [r14]
0x1800da4ad  mov     rcx, r14
0x1800da4b0  mov     rax, [rax+8]
0x1800da4b4  call    cs:__guard_dispatch_icall_fptr
0x1800da4ba  nop
0x1800da4bb  lea     rcx, [rsp+348h+var_108]
0x1800da4c3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800da4c8  nop
0x1800da4c9  mov     rcx, [rsi]
0x1800da4cc  test    rcx, rcx
0x1800da4cf  jz      short loc_1800DA4DF
0x1800da4d1  mov     rax, [rcx]
0x1800da4d4  mov     rax, [rax+10h]
0x1800da4d8  call    cs:__guard_dispatch_icall_fptr
0x1800da4de  nop
0x1800da4df  jmp     loc_1800DAF30
0x1800da4e4  movups  [rsp+348h+var_168], xmm0
0x1800da4ec  lea     rcx, [rsp+348h+var_168]
0x1800da4f4  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x1800da4f9  nop
0x1800da4fa  mov     rax, qword ptr [rsp+348h+var_168]
0x1800da502  test    rax, rax
0x1800da505  jz      loc_1800DA5BA
0x1800da50b  cmp     [rax+80h], bl
0x1800da511  jz      loc_1800DA5BA
0x1800da517  mov     rdi, qword ptr [rsp+348h+var_2B8]
0x1800da51f  lea     rax, [rsp+348h+var_2E8]
0x1800da524  mov     qword ptr [rsp+348h+var_178], rax
0x1800da52c  mov     r9d, 6
0x1800da532  xor     r8d, r8d
0x1800da535  lea     rdx, [rsp+348h+var_108]
0x1800da53d  lea     rcx, [rsp+348h+var_2E8]
0x1800da542  call    ??$ToString@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@HH@Z; Microsoft::Basix::ToString<std::string>(std::string const &,int,int)
0x1800da547  mov     r14, rax
0x1800da54a  xorps   xmm0, xmm0
0x1800da54d  movups  [rsp+348h+var_308], xmm0
0x1800da552  xorps   xmm1, xmm1
0x1800da555  movdqu  [rsp+348h+var_2F8], xmm1
0x1800da55b  mov     r8d, 22h ; '"'
0x1800da561  lea     rdx, aFoundDeviceS0x; "Found device %s (0x%p) for guid %s"
0x1800da568  lea     rcx, [rsp+348h+var_308]
0x1800da56d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800da572  nop
0x1800da573  movups  xmm0, xmmword ptr [r15]
0x1800da577  movdqu  xmmword ptr [rsp+348h+var_158], xmm0
0x1800da580  lea     rax, [rsp+348h+var_158]
0x1800da588  mov     [rsp+348h+var_320], rax
0x1800da58d  mov     [rsp+348h+var_328], rdi
0x1800da592  mov     r9, r14
0x1800da595  lea     r8, [rsp+348h+var_308]
0x1800da59a  lea     rdx, aRdpnano; "RDPNANO"
0x1800da5a1  lea     rcx, [rsp+348h+var_168]
0x1800da5a9  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAVDevice@UPnPManager@RdpNano@3@U_GUID@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@V65@PEAVDevice@UPnPManager@RdpNano@3@U_GUID@@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,std::string,Microsoft::RdpNano::UPnPManager::Device *,_GUID>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,std::string,Microsoft::RdpNano::UPnPManager::Device *,_GUID)
0x1800da5ae  nop
0x1800da5af  lea     rcx, [rsp+348h+var_308]
0x1800da5b4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800da5b9  nop
0x1800da5ba  mov     r14, qword ptr [rsp+348h+var_168+8]
0x1800da5c2  or      edi, 0FFFFFFFFh
0x1800da5c5  test    r14, r14
0x1800da5c8  jz      short loc_1800DA601
0x1800da5ca  mov     eax, edi
  ... truncated ...
```
