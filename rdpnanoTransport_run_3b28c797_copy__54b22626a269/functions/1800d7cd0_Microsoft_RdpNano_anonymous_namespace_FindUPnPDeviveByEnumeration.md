# Microsoft::RdpNano::_anonymous_namespace_::FindUPnPDeviveByEnumeration

- ea: `0x1800d7cd0`
- end: `0x1800d88b7`
- name: `Microsoft::RdpNano::_anonymous_namespace_::FindUPnPDeviveByEnumeration`
- size: `3047`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800da0bc`

## callees

- `0x18000d9c0`
- `0x18000da90`
- `0x180015bb8`
- `0x180017518`
- `0x18001902c`
- `0x18001ab4c`
- `0x180024700`
- `0x180027b84`
- `0x1800d2cd4`
- `0x1800d2d44`
- `0x1800d32c8`
- `0x1800d4284`
- `0x1800d54f0`
- `0x1800d7cd0`
- `0x1802e9b68`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032fa70`
- `0x180330b40`
- `0x180375c40`

## string_xrefs

- `0x1800d858d`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d8621`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d86b9`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d8738`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d8786`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d87ed`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d886b`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d7dbd`: `Discovered device is already root device`

## pseudocode

```c
// Hidden C++ exception states: #wind=48
__int64 **__fastcall Microsoft::RdpNano::_anonymous_namespace_::FindUPnPDeviveByEnumeration(__int64 **a1, _QWORD *a2)
{
  int v4; // r12d
  _QWORD *v5; // rcx
  __int64 v6; // r8
  volatile signed __int32 *v7; // rbx
  __int64 v8; // rcx
  __int64 *v9; // rbx
  volatile signed __int32 *v10; // rbx
  __int64 *v11; // rdx
  __int64 *v12; // rdx
  __int64 *v13; // r14
  _QWORD *v14; // rdx
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // ebx
  int v18; // ebx
  __int64 v19; // rax
  int v20; // ebx
  __int64 v21; // r8
  __int64 v22; // rbx
  unsigned int (__fastcall *v23)(__int64, __int64, __int64 *); // r13
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rbx
  __int128 *v27; // rcx
  char *v28; // rcx
  char *v29; // r8
  __int128 *v30; // r9
  __int128 *v31; // r9
  __int128 *v32; // rdx
  __int128 *v33; // rax
  signed __int64 v34; // r8
  __int128 *v35; // rdx
  volatile signed __int32 *v36; // rbx
  __int64 v37; // rbx
  __int64 (__fastcall *v38)(__int64, __int64 **); // r14
  __int64 *v39; // rcx
  int v40; // ebx
  __int128 *v41; // rdx
  volatile signed __int32 *v42; // rbx
  __int64 *v43; // rbx
  _QWORD *v44; // rcx
  Microsoft::Basix *v46; // rcx
  const struct std::error_category *v47; // rax
  Microsoft::Basix *v48; // rcx
  const struct std::error_category *v49; // rax
  Microsoft::Basix *v50; // rcx
  const struct std::error_category *v51; // rax
  __int64 v52; // rax
  Microsoft::Basix *v53; // rcx
  const struct std::error_category *v54; // rax
  char v55; // [rsp+30h] [rbp-D0h]
  __int128 v56; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v57; // [rsp+48h] [rbp-B8h]
  _OWORD v58[2]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v59; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v60[32]; // [rsp+80h] [rbp-80h] BYREF
  __int64 **v61; // [rsp+A0h] [rbp-60h]
  _QWORD *v62; // [rsp+A8h] [rbp-58h]
  _BYTE pExceptionObject[144]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v64; // [rsp+140h] [rbp+40h] BYREF
  __int64 v65; // [rsp+150h] [rbp+50h] BYREF
  _QWORD *v66; // [rsp+158h] [rbp+58h] BYREF
  int v67; // [rsp+160h] [rbp+60h] BYREF
  __int64 *v68; // [rsp+168h] [rbp+68h] BYREF
  __int128 v69; // [rsp+170h] [rbp+70h] BYREF
  __int128 v70; // [rsp+180h] [rbp+80h]
  __int128 v71; // [rsp+190h] [rbp+90h] BYREF
  __int64 v72; // [rsp+1A0h] [rbp+A0h]
  __int64 v73; // [rsp+1A8h] [rbp+A8h]
  _OWORD v74[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v75; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v76; // [rsp+1E0h] [rbp+E0h]
  _OWORD v77[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  _OWORD v78[2]; // [rsp+210h] [rbp+110h] BYREF
  __int64 v79; // [rsp+230h] [rbp+130h] BYREF

  v61 = a1;
  v62 = a2;
  *a1 = 0;
  v4 = 1;
  v5 = (_QWORD *)*a2;
  v59 = v5;
  if ( v5 )
    (*(void (__fastcall **)(_QWORD *))(*v5 + 8LL))(v5);
  Microsoft::RdpNano::_anonymous_namespace_::GetComString_wil::com_ptr_t_IUPnPService_wil::err_exception_policy__long____cdecl_IUPnPService::___wchar_t______(
    &v69,
    &v59,
     IUPnPDevice::`vcall'{112,{flat}});
  if ( !(_QWORD)v70 )
  {
    std::string::string(v58, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
    std::string::string(&v56, "UPnP device type must not be empty!");
    Microsoft::Basix::Exception::Exception(pExceptionObject, &v56, v58, 140);
    throw (Microsoft::Basix::Exception *)pExceptionObject;
  }
  LOBYTE(v6) = v55;
  if ( (unsigned __int8)boost::algorithm::starts_with<std::string,char const *,boost::algorithm::is_equal>(
                          &v69,
                          &off_1803F0CB0,
                          v6) )
  {
    v64 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v64);
    if ( (_QWORD)v64 && *(_BYTE *)(v64 + 128) )
    {
      v56 = 0;
      v57 = 0;
      std::string::_Construct<1,char const *>(&v56, "Discovered device is already root device", 40);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
        &v64,
        "RDPNANO",
        &v56);
      std::string::_Tidy_deallocate(&v56);
    }
    v7 = (volatile signed __int32 *)*((_QWORD *)&v64 + 1);
    if ( *((_QWORD *)&v64 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v64 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    v8 = *a2;
    v9 = *a1;
    *a1 = (__int64 *)*a2;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
    if ( v9 )
      (*(void (__fastcall **)(__int64 *))(*v9 + 16))(v9);
  }
  else
  {
    v74[0] = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v74);
    if ( *(_QWORD *)&v74[0] && *(_BYTE *)(*(_QWORD *)&v74[0] + 128LL) )
    {
      *(_QWORD *)&v64 = &v71;
      v71 = 0;
      v72 = 0;
      v73 = 0;
      v35 = &v69;
      if ( *((_QWORD *)&v70 + 1) > 0xFu )
        v35 = (__int128 *)v69;
      std::string::_Construct<2,char const *>(&v71, v35, v70);
      v56 = 0;
      v57 = 0;
      std::string::_Construct<1,char const *>(
        &v56,
        "Discovered device (%s) is not root device. Getting root device",
        (const char *)0x3E);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(
        v74,
        "RDPNANO",
        &v56,
        &v71);
      std::string::_Tidy_deallocate(&v56);
    }
    v36 = (volatile signed __int32 *)*((_QWORD *)&v74[0] + 1);
    if ( *((_QWORD *)&v74[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v74[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
        if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
      }
    }
    v37 = *a2;
    v38 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)*a2 + 64LL);
    v39 = *a1;
    *a1 = 0;
    if ( v39 )
      (*(void (__fastcall **)(__int64 *))(*v39 + 16))(v39);
    v40 = v38(v37, a1);
    if ( v40 < 0 )
    {
      _mm_lfence();
      std::string::string(v58, (const char *)&Str1);
      std::string::string(&v56, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
      std::string::string(v74, "Failed to get root device");
      v49 = Microsoft::Basix::WindowsCategory(v48);
      v71 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v64, v40, v49);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)&v71,
        (unsigned int)v74,
        (unsigned int)&v56,
        153,
        (__int64)v58);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
  }
  v64 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v64);
  if ( (_QWORD)v64 && *(_BYTE *)(v64 + 128) )
  {
    v56 = 0;
    v57 = 0;
    std::string::_Construct<1,char const *>(&v56, "Walking device tree...", 22);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(&v64, "RDPNANO", &v56);
    std::string::_Tidy_deallocate(&v56);
  }
  v10 = (volatile signed __int32 *)*((_QWORD *)&v64 + 1);
  if ( *((_QWORD *)&v64 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v64 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  memset(v77, 0, sizeof(v77));
  v11 = &qword_18053D3A0;
  if ( (unsigned __int64)qword_18053D3B8 > 0xF )
    v11 = (__int64 *)qword_18053D3A0;
  std::string::_Construct<2,char const *>(v77, v11, qword_18053D3B0);
  memset(v78, 0, sizeof(v78));
  v12 = &qword_18053D300;
  if ( (unsigned __int64)qword_18053D318 > 0xF )
    v12 = (__int64 *)qword_18053D300;
  std::string::_Construct<2,char const *>(v78, v12, qword_18053D310);
  v13 = (__int64 *)v77;
  do
  {
    v75 = 0;
    v76 = 0;
    v14 = v13;
    if ( (unsigned __int64)v13[3] > 0xF )
      v14 = (_QWORD *)*v13;
    std::string::_Construct<2,char const *>(&v75, v14, v13[2]);
    v68 = 0;
    v15 = *a1;
    v16 = **a1;
    v68 = 0;
    v17 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v16 + 88))(v15, &v68);
    if ( v17 < 0 )
    {
      _mm_lfence();
      std::string::string(v60, (const char *)&Str1);
      std::string::string(v58, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
      std::string::string(&v56, "Failed to get device children");
      v51 = Microsoft::Basix::WindowsCategory(v50);
      v71 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v64, v17, v51);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)&v71,
        (unsigned int)&v56,
        (unsigned int)v58,
        162,
        (__int64)v60);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
    v67 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v68 + 56))(v68, &v67);
    if ( v18 < 0 )
    {
      _mm_lfence();
      std::string::string(v60, (const char *)&Str1);
      std::string::string(v58, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
      std::string::string(&v56, "Failed to get child list length");
      v47 = Microsoft::Basix::WindowsCategory(v46);
      v71 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v64, v18, v47);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)&v71,
        (unsigned int)&v56,
        (unsigned int)v58,
        165,
        (__int64)v60);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
    if ( v67 <= 0 )
    {
      std::string::string(v60, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
      std::string::string(v58, "No children found");
      Microsoft::Basix::Exception::Exception(pExceptionObject, v58, v60, 166);
      throw (Microsoft::Basix::Exception *)pExceptionObject;
    }
    v65 = 0;
    v19 = *v68;
    v65 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v19 + 64))(v68, &v65);
    if ( v20 < 0 )
    {
      _mm_lfence();
      std::string::string(v58, (const char *)&Str1);
      std::string::string(&v56, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
      std::string::string(v60, "Failed to det child enumeration");
      v54 = Microsoft::Basix::WindowsCategory(v53);
      v71 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v64, v20, v54);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)&v71,
        (unsigned int)v60,
        (unsigned int)&v56,
        169,
        (__int64)v58);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
    *(_QWORD *)&v74[0] = 0;
    LOBYTE(v21) = v55;
    wil::com_ptr_t<IEnumUnknown,wil::err_exception_policy>::com_ptr_t<IEnumUnknown,wil::err_exception_policy>(
      v74,
      v65,
      v21);
    v4 |= 2u;
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v74[0] + 40LL))(*(_QWORD *)&v74[0]);
    while ( 1 )
    {
      v22 = *(_QWORD *)&v74[0];
      v23 = *(unsigned int (__fastcall **)(__int64, __int64, __int64 *))(**(_QWORD **)&v74[0] + 24LL);
      v24 = v65;
      v65 = 0;
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      if ( v23(v22, 1, &v65) )
      {
        std::string::string(v58, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
        v52 = std::operator+<char>(v60, "Failed to find child with type ", &v75);
        Microsoft::Basix::Exception::Exception(pExceptionObject, v52, v58, 188);
        throw (Microsoft::Basix::Exception *)pExceptionObject;
      }
      v66 = 0;
      LOBYTE(v25) = v55;
      wil::com_ptr_t<IUPnPDevice,wil::err_exception_policy>::com_ptr_t<IUPnPDevice,wil::err_exception_policy>(
        &v66,
        v65,
        v25);
      v4 |= 4u;
      *(_QWORD *)&v64 = v66;
      if ( v66 )
        (*(void (__fastcall **)(_QWORD *))(*v66 + 8LL))(v66);
      v26 = Microsoft::RdpNano::_anonymous_namespace_::GetComString_wil::com_ptr_t_IUPnPService_wil::err_exception_policy__long____cdecl_IUPnPService::___wchar_t______(
              v58,
              &v64,
               IUPnPDevice::`vcall'{112,{flat}});
      if ( &v69 != (__int128 *)v26 )
      {
        std::string::_Tidy_deallocate(&v69);
        v69 = *(_OWORD *)v26;
        v70 = *(_OWORD *)(v26 + 16);
        *(_QWORD *)(v26 + 16) = 0;
        *(_QWORD *)(v26 + 24) = 15;
        *(_BYTE *)v26 = 0;
      }
      std::string::_Tidy_deallocate(v58);
      v27 = &v69;
      if ( *((_QWORD *)&v70 + 1) > 0xFu )
        v27 = (__int128 *)v69;
      v28 = (char *)v27 + v70;
      v29 = (char *)&v69;
      if ( *((_QWORD *)&v70 + 1) > 0xFu )
        v29 = (char *)v69;
      v30 = &v75;
      if ( *((_QWORD *)&v76 + 1) > 0xFu )
        v30 = (__int128 *)v75;
      v31 = (__int128 *)((char *)v30 + v76);
      v32 = &v75;
      if ( *((_QWORD *)&v76 + 1) > 0xFu )
        v32 = (__int128 *)v75;
      v33 = v32;
      if ( v29 != v28 )
        break;
LABEL_55:
      if ( v33 == v31 )
        goto LABEL_72;
LABEL_56:
      if ( v66 )
        (*(void (__fastcall **)(_QWORD *))(*v66 + 16LL))(v66);
    }
    v34 = v29 - (char *)v32;
    while ( v33 != v31 )
    {
      if ( *((_BYTE *)v33 + v34) != *(_BYTE *)v33 )
        goto LABEL_56;
      v33 = (__int128 *)((char *)v33 + 1);
      if ( (char *)v33 + v34 == v28 )
        goto LABEL_55;
    }
LABEL_72:
    v71 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v71);
    if ( (_QWORD)v71 && *(_BYTE *)(v71 + 128) )
    {
      *(_QWORD *)&v64 = &v56;
      v56 = 0;
      v57 = 0u;
      v41 = &v69;
      if ( *((_QWORD *)&v70 + 1) > 0xFu )
        v41 = (__int128 *)v69;
      std::string::_Construct<2,char const *>(&v56, v41, v70);
      memset(v58, 0, sizeof(v58));
      std::string::_Construct<1,char const *>(v58, "Device enumeration found %s!", (const char *)0x1C);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(
        &v71,
        "RDPNANO",
        v58,
        &v56);
      std::string::_Tidy_deallocate(v58);
    }
    v42 = (volatile signed __int32 *)*((_QWORD *)&v71 + 1);
    if ( *((_QWORD *)&v71 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v71 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
        if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
      }
    }
    v43 = *a1;
    v44 = v66;
    *a1 = v66;
    if ( v44 )
    {
      (*(void (__fastcall **)(_QWORD *))(*v44 + 8LL))(v44);
      v44 = v66;
    }
    if ( v43 )
    {
      (*(void (__fastcall **)(__int64 *))(*v43 + 16))(v43);
      v44 = v66;
    }
    if ( v44 )
      (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
    if ( *(_QWORD *)&v74[0] )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v74[0] + 16LL))(*(_QWORD *)&v74[0]);
    if ( v65 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
    if ( v68 )
      (*(void (__fastcall **)(__int64 *))(*v68 + 16))(v68);
    std::string::_Tidy_deallocate(&v75);
    v13 += 4;
  }
  while ( v13 != &v79 );
  `eh vector destructor iterator'(
    v77,
    0x20u,
    2u,
    boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>);
  std::string::_Tidy_deallocate(&v69);
  if ( *a2 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
  return a1;
}

```

## disassembly

```asm
0x1800d7cd0  mov     [rsp-8+arg_10], rbx
0x1800d7cd5  push    rbp
0x1800d7cd6  push    rsi
0x1800d7cd7  push    rdi
0x1800d7cd8  push    r12
0x1800d7cda  push    r13
0x1800d7cdc  push    r14
0x1800d7cde  push    r15
0x1800d7ce0  lea     rbp, [rsp-140h]
0x1800d7ce8  mov     eax, 240h
0x1800d7ced  call    _alloca_probe
0x1800d7cf2  sub     rsp, rax
0x1800d7cf5  mov     rax, cs:__security_cookie
0x1800d7cfc  xor     rax, rsp
0x1800d7cff  mov     [rbp+170h+var_40], rax
0x1800d7d06  mov     r15, rdx
0x1800d7d09  mov     rsi, rcx
0x1800d7d0c  mov     [rbp+170h+var_1D0], rcx
0x1800d7d10  mov     [rbp+170h+var_1C8], rdx
0x1800d7d14  xor     r13d, r13d
0x1800d7d17  mov     [rsp+270h+var_23C], r13d
0x1800d7d1c  mov     [rcx], r13
0x1800d7d1f  lea     r12d, [r13+1]
0x1800d7d23  mov     [rsp+270h+var_23C], r12d
0x1800d7d28  mov     rcx, [rdx]
0x1800d7d2b  mov     [rsp+270h+var_1F8], rcx
0x1800d7d30  test    rcx, rcx
0x1800d7d33  jz      short loc_1800D7D43
0x1800d7d35  mov     rax, [rcx]
0x1800d7d38  mov     rax, [rax+8]
0x1800d7d3c  call    cs:__guard_dispatch_icall_fptr
0x1800d7d42  nop
0x1800d7d43  lea     r8, ??_9IUPnPDevice@@$BHA@AA; [thunk]: IUPnPDevice::`vcall'{112,{flat}}
0x1800d7d4a  lea     rdx, [rsp+270h+var_1F8]
0x1800d7d4f  lea     rcx, [rbp+170h+var_100]
0x1800d7d53  call    Microsoft__RdpNano___anonymous_namespace___GetComString_wil__com_ptr_t_IUPnPService_wil__err_exception_policy__long____cdecl_IUPnPService_____wchar_t______
0x1800d7d58  nop
0x1800d7d59  cmp     qword ptr [rbp+170h+var_F0], r13
0x1800d7d60  jz      loc_1800D8738
0x1800d7d66  mov     r8b, [rsp+270h+var_240]
0x1800d7d6b  lea     rdx, off_1803F0CB0; "urn:schemas-upnp-org:device:InternetGat"...
0x1800d7d72  lea     rcx, [rbp+170h+var_100]
0x1800d7d76  call    ??$starts_with@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDUis_equal@algorithm@boost@@@algorithm@boost@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBQEBDUis_equal@01@@Z; boost::algorithm::starts_with<std::string,char const *,boost::algorithm::is_equal>(std::string const &,char const * const &,boost::algorithm::is_equal)
0x1800d7d7b  xorps   xmm0, xmm0
0x1800d7d7e  test    al, al
0x1800d7d80  jz      loc_1800D8203
0x1800d7d86  movups  [rbp+170h+var_130], xmm0
0x1800d7d8a  lea     rcx, [rbp+170h+var_130]
0x1800d7d8e  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800d7d93  nop
0x1800d7d94  mov     rax, qword ptr [rbp+170h+var_130]
0x1800d7d98  test    rax, rax
0x1800d7d9b  jz      short loc_1800D7DF0
0x1800d7d9d  cmp     [rax+80h], r13b
0x1800d7da4  jz      short loc_1800D7DF0
0x1800d7da6  xorps   xmm0, xmm0
0x1800d7da9  movups  [rsp+270h+var_238], xmm0
0x1800d7dae  xorps   xmm1, xmm1
0x1800d7db1  movdqu  [rsp+270h+var_228], xmm1
0x1800d7db7  mov     r8d, 28h ; '('
0x1800d7dbd  lea     rdx, aDiscoveredDevi_0; "Discovered device is already root devic"...
0x1800d7dc4  lea     rcx, [rsp+270h+var_238]
0x1800d7dc9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d7dce  nop
0x1800d7dcf  lea     r8, [rsp+270h+var_238]
0x1800d7dd4  lea     rdx, aRdpnano; "RDPNANO"
0x1800d7ddb  lea     rcx, [rbp+170h+var_130]
0x1800d7ddf  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x1800d7de4  nop
0x1800d7de5  lea     rcx, [rsp+270h+var_238]
0x1800d7dea  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d7def  nop
0x1800d7df0  or      edi, 0FFFFFFFFh
0x1800d7df3  mov     rbx, qword ptr [rbp+170h+var_130+8]
0x1800d7df7  test    rbx, rbx
0x1800d7dfa  jz      short loc_1800D7E31
0x1800d7dfc  mov     eax, edi
0x1800d7dfe  lock xadd [rbx+8], eax
0x1800d7e03  add     eax, edi
0x1800d7e05  jnz     short loc_1800D7E31
0x1800d7e07  mov     rax, [rbx]
0x1800d7e0a  mov     rcx, rbx
0x1800d7e0d  mov     rax, [rax]
0x1800d7e10  call    cs:__guard_dispatch_icall_fptr
0x1800d7e16  mov     eax, edi
0x1800d7e18  lock xadd [rbx+0Ch], eax
0x1800d7e1d  add     eax, edi
0x1800d7e1f  jnz     short loc_1800D7E31
0x1800d7e21  mov     rax, [rbx]
0x1800d7e24  mov     rcx, rbx
0x1800d7e27  mov     rax, [rax+8]
0x1800d7e2b  call    cs:__guard_dispatch_icall_fptr
0x1800d7e31  mov     rcx, [r15]
0x1800d7e34  mov     rbx, [rsi]
0x1800d7e37  mov     [rsi], rcx
0x1800d7e3a  test    rcx, rcx
0x1800d7e3d  jz      short loc_1800D7E4C
0x1800d7e3f  mov     rax, [rcx]
0x1800d7e42  mov     rax, [rax+8]
0x1800d7e46  call    cs:__guard_dispatch_icall_fptr
0x1800d7e4c  test    rbx, rbx
0x1800d7e4f  jz      short loc_1800D7E62
0x1800d7e51  mov     rax, [rbx]
0x1800d7e54  mov     rcx, rbx
0x1800d7e57  mov     rax, [rax+10h]
0x1800d7e5b  call    cs:__guard_dispatch_icall_fptr
0x1800d7e61  nop
0x1800d7e62  xorps   xmm0, xmm0
0x1800d7e65  movups  [rbp+170h+var_130], xmm0
0x1800d7e69  lea     rcx, [rbp+170h+var_130]
0x1800d7e6d  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800d7e72  nop
0x1800d7e73  mov     rax, qword ptr [rbp+170h+var_130]
0x1800d7e77  test    rax, rax
0x1800d7e7a  jz      short loc_1800D7ECF
0x1800d7e7c  cmp     [rax+80h], r13b
0x1800d7e83  jz      short loc_1800D7ECF
0x1800d7e85  xorps   xmm0, xmm0
0x1800d7e88  movups  [rsp+270h+var_238], xmm0
0x1800d7e8d  xorps   xmm1, xmm1
0x1800d7e90  movdqu  [rsp+270h+var_228], xmm1
0x1800d7e96  mov     r8d, 16h
0x1800d7e9c  lea     rdx, aWalkingDeviceT; "Walking device tree..."
0x1800d7ea3  lea     rcx, [rsp+270h+var_238]
0x1800d7ea8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d7ead  nop
0x1800d7eae  lea     r8, [rsp+270h+var_238]
0x1800d7eb3  lea     rdx, aRdpnano; "RDPNANO"
0x1800d7eba  lea     rcx, [rbp+170h+var_130]
0x1800d7ebe  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x1800d7ec3  nop
0x1800d7ec4  lea     rcx, [rsp+270h+var_238]
0x1800d7ec9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d7ece  nop
0x1800d7ecf  mov     rbx, qword ptr [rbp+170h+var_130+8]
0x1800d7ed3  test    rbx, rbx
0x1800d7ed6  jz      short loc_1800D7F0D
0x1800d7ed8  mov     eax, edi
0x1800d7eda  lock xadd [rbx+8], eax
0x1800d7edf  add     eax, edi
0x1800d7ee1  jnz     short loc_1800D7F0D
0x1800d7ee3  mov     rax, [rbx]
0x1800d7ee6  mov     rcx, rbx
0x1800d7ee9  mov     rax, [rax]
0x1800d7eec  call    cs:__guard_dispatch_icall_fptr
0x1800d7ef2  mov     eax, edi
0x1800d7ef4  lock xadd [rbx+0Ch], eax
0x1800d7ef9  add     eax, edi
0x1800d7efb  jnz     short loc_1800D7F0D
0x1800d7efd  mov     rax, [rbx]
0x1800d7f00  mov     rcx, rbx
0x1800d7f03  mov     rax, [rax+8]
0x1800d7f07  call    cs:__guard_dispatch_icall_fptr
0x1800d7f0d  xorps   xmm0, xmm0
0x1800d7f10  movups  [rbp+170h+var_80], xmm0
0x1800d7f17  xorps   xmm1, xmm1
0x1800d7f1a  movdqa  [rbp+170h+var_70], xmm1
0x1800d7f22  lea     rdx, qword_18053D3A0
0x1800d7f29  cmp     cs:qword_18053D3B8, 0Fh
0x1800d7f31  cmova   rdx, cs:qword_18053D3A0
0x1800d7f39  mov     r8, cs:qword_18053D3B0
0x1800d7f40  lea     rcx, [rbp+170h+var_80]
0x1800d7f47  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800d7f4c  nop
0x1800d7f4d  xorps   xmm0, xmm0
0x1800d7f50  movups  [rbp+170h+var_60], xmm0
0x1800d7f57  xorps   xmm1, xmm1
0x1800d7f5a  movdqa  [rbp+170h+var_50], xmm1
0x1800d7f62  lea     rdx, qword_18053D300
0x1800d7f69  cmp     cs:qword_18053D318, 0Fh
0x1800d7f71  cmova   rdx, cs:qword_18053D300
0x1800d7f79  mov     r8, cs:qword_18053D310
0x1800d7f80  lea     rcx, [rbp+170h+var_60]
0x1800d7f87  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800d7f8c  nop
0x1800d7f8d  lea     r14, [rbp+170h+var_80]
0x1800d7f94  xorps   xmm0, xmm0
0x1800d7f97  movups  [rbp+170h+var_A0], xmm0
0x1800d7f9e  xorps   xmm1, xmm1
0x1800d7fa1  movdqu  [rbp+170h+var_90], xmm1
0x1800d7fa9  mov     rdx, r14
0x1800d7fac  cmp     qword ptr [r14+18h], 0Fh
0x1800d7fb1  jbe     short loc_1800D7FB6
0x1800d7fb3  mov     rdx, [r14]
0x1800d7fb6  mov     r8, [r14+10h]
0x1800d7fba  lea     rcx, [rbp+170h+var_A0]
0x1800d7fc1  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800d7fc6  nop
0x1800d7fc7  mov     [rbp+170h+var_108], r13
0x1800d7fcb  mov     rcx, [rsi]
0x1800d7fce  mov     rax, [rcx]
0x1800d7fd1  mov     [rbp+170h+var_108], r13
0x1800d7fd5  lea     rdx, [rbp+170h+var_108]
0x1800d7fd9  mov     rax, [rax+58h]
0x1800d7fdd  call    cs:__guard_dispatch_icall_fptr
0x1800d7fe3  mov     ebx, eax
0x1800d7fe5  test    eax, eax
0x1800d7fe7  js      loc_1800D86A5
0x1800d7fed  mov     [rbp+170h+var_110], r13d
0x1800d7ff1  mov     rcx, [rbp+170h+var_108]
0x1800d7ff5  mov     rax, [rcx]
0x1800d7ff8  lea     rdx, [rbp+170h+var_110]
0x1800d7ffc  mov     rax, [rax+38h]
0x1800d8000  call    cs:__guard_dispatch_icall_fptr
0x1800d8006  mov     ebx, eax
0x1800d8008  test    eax, eax
0x1800d800a  js      loc_1800D8579
0x1800d8010  cmp     [rbp+170h+var_110], r13d
0x1800d8014  jle     loc_1800D886B
0x1800d801a  mov     [rbp+170h+var_120], r13
0x1800d801e  mov     rcx, [rbp+170h+var_108]
0x1800d8022  mov     rax, [rcx]
0x1800d8025  mov     [rbp+170h+var_120], r13
0x1800d8029  lea     rdx, [rbp+170h+var_120]
0x1800d802d  mov     rax, [rax+40h]
0x1800d8031  call    cs:__guard_dispatch_icall_fptr
0x1800d8037  mov     ebx, eax
0x1800d8039  test    eax, eax
0x1800d803b  js      loc_1800D87D8
0x1800d8041  mov     qword ptr [rbp+170h+var_C0], r13
0x1800d8048  mov     r8b, [rsp+270h+var_240]
0x1800d804d  mov     rdx, [rbp+170h+var_120]
0x1800d8051  lea     rcx, [rbp+170h+var_C0]
0x1800d8058  call    ??$?0UIUnknown@@@?$com_ptr_t@UIEnumUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIUnknown@@U?$integral_constant@D$0A@@wistd@@@Z; wil::com_ptr_t<IEnumUnknown,wil::err_exception_policy>::com_ptr_t<IEnumUnknown,wil::err_exception_policy>(IUnknown *,wistd::integral_constant<char,0>)
0x1800d805d  or      r12d, 2
0x1800d8061  mov     [rsp+270h+var_23C], r12d
0x1800d8066  mov     rcx, qword ptr [rbp+170h+var_C0]
0x1800d806d  mov     rax, [rcx]
0x1800d8070  mov     rax, [rax+28h]
0x1800d8074  call    cs:__guard_dispatch_icall_fptr
0x1800d807a  mov     rbx, qword ptr [rbp+170h+var_C0]
0x1800d8081  mov     rax, [rbx]
0x1800d8084  mov     r13, [rax+18h]
0x1800d8088  mov     rcx, [rbp+170h+var_120]
0x1800d808c  mov     [rbp+170h+var_120], 0
0x1800d8094  test    rcx, rcx
0x1800d8097  jz      short loc_1800D80A7
0x1800d8099  mov     rax, [rcx]
0x1800d809c  mov     rax, [rax+10h]
0x1800d80a0  call    cs:__guard_dispatch_icall_fptr
0x1800d80a6  nop
0x1800d80a7  xor     r9d, r9d
0x1800d80aa  lea     r8, [rbp+170h+var_120]
0x1800d80ae  lea     edx, [r9+1]
0x1800d80b2  mov     rcx, rbx
0x1800d80b5  mov     rax, r13
0x1800d80b8  call    cs:__guard_dispatch_icall_fptr
0x1800d80be  xor     r13d, r13d
0x1800d80c1  test    eax, eax
0x1800d80c3  jnz     loc_1800D8786
0x1800d80c9  mov     [rbp+170h+var_118], r13
0x1800d80cd  mov     r8b, [rsp+270h+var_240]
0x1800d80d2  mov     rdx, [rbp+170h+var_120]
0x1800d80d6  lea     rcx, [rbp+170h+var_118]
0x1800d80da  call    ??$?0UIUnknown@@@?$com_ptr_t@UIUPnPDevice@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIUnknown@@U?$integral_constant@D$0A@@wistd@@@Z; wil::com_ptr_t<IUPnPDevice,wil::err_exception_policy>::com_ptr_t<IUPnPDevice,wil::err_exception_policy>(IUnknown *,wistd::integral_constant<char,0>)
0x1800d80df  or      r12d, 4
0x1800d80e3  mov     [rsp+270h+var_23C], r12d
0x1800d80e8  mov     rcx, [rbp+170h+var_118]
0x1800d80ec  mov     qword ptr [rbp+170h+var_130], rcx
0x1800d80f0  test    rcx, rcx
0x1800d80f3  jz      short loc_1800D8103
0x1800d80f5  mov     rax, [rcx]
0x1800d80f8  mov     rax, [rax+8]
0x1800d80fc  call    cs:__guard_dispatch_icall_fptr
0x1800d8102  nop
0x1800d8103  lea     r8, ??_9IUPnPDevice@@$BHA@AA; [thunk]: IUPnPDevice::`vcall'{112,{flat}}
0x1800d810a  lea     rdx, [rbp+170h+var_130]
0x1800d810e  lea     rcx, [rsp+270h+var_218]
0x1800d8113  call    Microsoft__RdpNano___anonymous_namespace___GetComString_wil__com_ptr_t_IUPnPService_wil__err_exception_policy__long____cdecl_IUPnPService_____wchar_t______
0x1800d8118  mov     rbx, rax
0x1800d811b  lea     rax, [rbp+170h+var_100]
0x1800d811f  cmp     rax, rbx
0x1800d8122  jz      short loc_1800D814E
0x1800d8124  lea     rcx, [rbp+170h+var_100]
0x1800d8128  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d812d  movups  xmm0, xmmword ptr [rbx]
0x1800d8130  movups  [rbp+170h+var_100], xmm0
0x1800d8134  movups  xmm1, xmmword ptr [rbx+10h]
0x1800d8138  movups  [rbp+170h+var_F0], xmm1
0x1800d813f  mov     [rbx+10h], r13
0x1800d8143  mov     qword ptr [rbx+18h], 0Fh
0x1800d814b  mov     [rbx], r13b
0x1800d814e  lea     rcx, [rsp+270h+var_218]
0x1800d8153  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d8158  lea     rcx, [rbp+170h+var_100]
0x1800d815c  cmp     qword ptr [rbp+170h+var_F0+8], 0Fh
0x1800d8164  cmova   rcx, qword ptr [rbp+170h+var_100]
0x1800d8169  add     rcx, qword ptr [rbp+170h+var_F0]
0x1800d8170  lea     r8, [rbp+170h+var_100]
0x1800d8174  cmp     qword ptr [rbp+170h+var_F0+8], 0Fh
0x1800d817c  cmova   r8, qword ptr [rbp+170h+var_100]
0x1800d8181  lea     r9, [rbp+170h+var_A0]
0x1800d8188  cmp     qword ptr [rbp+170h+var_90+8], 0Fh
0x1800d8190  cmova   r9, qword ptr [rbp+170h+var_A0]
0x1800d8198  add     r9, qword ptr [rbp+170h+var_90]
0x1800d819f  lea     rdx, [rbp+170h+var_A0]
0x1800d81a6  cmp     qword ptr [rbp+170h+var_90+8], 0Fh
0x1800d81ae  cmova   rdx, qword ptr [rbp+170h+var_A0]
0x1800d81b6  mov     rax, rdx
0x1800d81b9  cmp     r8, rcx
  ... truncated ...
```
