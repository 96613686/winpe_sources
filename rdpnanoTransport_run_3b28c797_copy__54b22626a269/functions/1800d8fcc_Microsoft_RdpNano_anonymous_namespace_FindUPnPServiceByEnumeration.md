# Microsoft::RdpNano::_anonymous_namespace_::FindUPnPServiceByEnumeration

- ea: `0x1800d8fcc`
- end: `0x1800d96db`
- name: `Microsoft::RdpNano::_anonymous_namespace_::FindUPnPServiceByEnumeration`
- size: `1807`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800d88b8`

## callees

- `0x18000d9c0`
- `0x18000da90`
- `0x1800109a0`
- `0x180010a60`
- `0x180015bb8`
- `0x180017344`
- `0x180017518`
- `0x180018ea4`
- `0x18001902c`
- `0x180024700`
- `0x180027b84`
- `0x18002a8ec`
- `0x18002fec0`
- `0x1800377b4`
- `0x18004569c`
- `0x1800d2cd4`
- `0x1800d2db4`
- `0x1800d32c8`
- `0x1800d4284`
- `0x1800d5574`
- `0x1800d8fcc`
- `0x1802e9b68`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## string_xrefs

- `0x1800d941b`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d94f3`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d9524`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d9588`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d9615`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d968d`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d959a`: `Failed to get services list from device`
- `0x1800d9627`: `Failed to get services count`
- `0x1800d969f`: `Device has no services`
- `0x1800d942d`: `Failed to get service enumerator`
- `0x1800d91d4`: `Service enumeration found UPnP service %s`
- `0x1800d930f`: `Using enumerated service %s`
- `0x1800d94df`: `Microsoft::RdpNano::`anonymous-namespace'::FindUPnPServiceByEnumeration`
- `0x1800d94cd`: `Service enumeration found no matching service\n    %s(%d): %s()`
- `0x1800d9539`: `UPnP service enumeration cound not find `

## pseudocode

```c
// Hidden C++ exception states: #wind=37
_QWORD *__fastcall Microsoft::RdpNano::_anonymous_namespace_::FindUPnPServiceByEnumeration(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3)
{
  int v5; // ebx
  int v6; // ebx
  __int64 v7; // rax
  int v8; // ebx
  __int64 v9; // r8
  int v10; // edi
  __int64 v11; // rbx
  unsigned int (__fastcall *v12)(__int64, __int64, _QWORD *); // r14
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // r8
  _QWORD *v17; // rdx
  volatile signed __int32 *v18; // rbx
  _QWORD *v19; // rdx
  volatile signed __int32 *v20; // rbx
  Microsoft::Basix *v22; // rcx
  const struct std::error_category *v23; // rax
  Microsoft::Basix::Instrumentation::EventBase *v24; // rax
  const char *v25; // r8
  int v26; // r9d
  __int64 v27; // rax
  Microsoft::Basix *v28; // rcx
  const struct std::error_category *v29; // rax
  Microsoft::Basix *v30; // rcx
  const struct std::error_category *v31; // rax
  const char *v32; // [rsp+20h] [rbp-E0h]
  char v33; // [rsp+30h] [rbp-D0h]
  __int128 v34; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v35; // [rsp+48h] [rbp-B8h]
  __int128 v36; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v37; // [rsp+68h] [rbp-98h]
  __int64 v38; // [rsp+70h] [rbp-90h]
  int v39; // [rsp+78h] [rbp-88h]
  _QWORD v40[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v42[2]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v43; // [rsp+130h] [rbp+30h] BYREF
  __int64 *v44; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v45[2]; // [rsp+148h] [rbp+48h] BYREF
  __int64 v46; // [rsp+158h] [rbp+58h] BYREF
  _QWORD v47[2]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v48; // [rsp+170h] [rbp+70h]
  unsigned __int64 v49; // [rsp+178h] [rbp+78h]
  int v50; // [rsp+180h] [rbp+80h] BYREF

  v40[1] = a1;
  v39 = 1;
  v44 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*a3 + 200LL))(*a3, &v44);
  if ( v5 < 0 )
  {
    _mm_lfence();
    std::string::string(&v34, (const char *)&Str1);
    std::string::string(&v36, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
    std::string::string(v47, "Failed to get services list from device");
    v29 = Microsoft::Basix::WindowsCategory(v28);
    v43 = *(_OWORD *)std::error_code::error_code((std::error_code *)v45, v5, v29);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v43,
      (unsigned int)v47,
      (unsigned int)&v36,
      200,
      (__int64)&v34);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  v6 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v44 + 56))(v44, &v50);
  if ( v6 < 0 )
  {
    _mm_lfence();
    std::string::string(&v34, (const char *)&Str1);
    std::string::string(&v36, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
    std::string::string(v47, "Failed to get services count");
    v31 = Microsoft::Basix::WindowsCategory(v30);
    v43 = *(_OWORD *)std::error_code::error_code((std::error_code *)v45, v6, v31);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v43,
      (unsigned int)v47,
      (unsigned int)&v36,
      203,
      (__int64)&v34);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  if ( v50 <= 0 )
  {
    std::string::string(&v34, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
    std::string::string(&v36, "Device has no services");
    Microsoft::Basix::Exception::Exception(pExceptionObject, &v36, &v34, 204);
    throw (Microsoft::Basix::Exception *)pExceptionObject;
  }
  v42[0] = 0;
  v7 = *v44;
  v42[0] = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *))(v7 + 64))(v44, v42);
  if ( v8 < 0 )
  {
    _mm_lfence();
    std::string::string(&v34, (const char *)&Str1);
    std::string::string(&v36, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
    std::string::string(v47, "Failed to get service enumerator");
    v23 = Microsoft::Basix::WindowsCategory(v22);
    v43 = *(_OWORD *)std::error_code::error_code((std::error_code *)v45, v8, v23);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v43,
      (unsigned int)v47,
      (unsigned int)&v36,
      207,
      (__int64)&v34);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  v46 = 0;
  LOBYTE(v9) = v33;
  wil::com_ptr_t<IEnumUnknown,wil::err_exception_policy>::com_ptr_t<IEnumUnknown,wil::err_exception_policy>(
    &v46,
    v42[0],
    v9);
  v10 = 3;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 40LL))(v46);
  while ( 1 )
  {
    v11 = v46;
    v12 = *(unsigned int (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v46 + 24LL);
    v13 = v42[0];
    v42[0] = 0;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    if ( v12(v11, 1, v42) )
    {
      std::exception_ptr::__autoclassinit2((std::exception_ptr *)v45, 0x10u);
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v45);
      if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(v45) )
      {
        v24 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(v45);
        if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v24) )
        {
          std::string::string(&v34, "Service enumeration found no matching service\n    %s(%d): %s()", v25, v26, v32);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
            (unsigned int)v45,
            (unsigned int)"TEREDO",
            (unsigned int)&v34,
            (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp",
            225,
            (__int64)"Microsoft::RdpNano::`anonymous-namespace'::FindUPnPServiceByEnumeration");
          boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(&v34);
        }
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v45);
      std::string::string(&v34, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
      v27 = std::operator+<char>(&v36, "UPnP service enumeration cound not find ", a2);
      Microsoft::Basix::Exception::Exception(pExceptionObject, v27, &v34, 226);
      throw (Microsoft::Basix::Exception *)pExceptionObject;
    }
    *a1 = 0;
    LOBYTE(v14) = v33;
    wil::com_ptr_t<IUPnPService,wil::err_exception_policy>::com_ptr_t<IUPnPService,wil::err_exception_policy>(
      a1,
      v42[0],
      v14);
    v10 |= 5u;
    v39 = v10;
    v15 = *a1;
    v40[0] = v15;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    Microsoft::RdpNano::_anonymous_namespace_::GetComString_wil::com_ptr_t_IUPnPService_wil::err_exception_policy__long____cdecl_IUPnPService::___wchar_t______(
      v47,
      v40,
       IUPnPService::`vcall'{72,{flat}});
    v43 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v43);
    if ( (_QWORD)v43 && *(_BYTE *)(v43 + 128) )
    {
      v45[0] = &v36;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      v17 = v47;
      if ( v49 > 0xF )
        v17 = (_QWORD *)v47[0];
      std::string::_Construct<2,char const *>(&v36, v17, v48);
      v34 = 0;
      v35 = 0;
      std::string::_Construct<1,char const *>(&v34, "Service enumeration found UPnP service %s", (const char *)0x29);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(
        &v43,
        "RDPNANO",
        &v34,
        &v36);
      std::string::_Tidy_deallocate(&v34);
    }
    v18 = (volatile signed __int32 *)*((_QWORD *)&v43 + 1);
    if ( *((_QWORD *)&v43 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v43 + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( !_InterlockedDecrement(v18 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    LOBYTE(v16) = v33;
    if ( (unsigned __int8)boost::algorithm::starts_with<std::string,std::string,boost::algorithm::is_equal>(
                            v47,
                            a2,
                            v16) )
      break;
    std::string::_Tidy_deallocate(v47);
    if ( (v10 & 1) != 0 )
    {
      v10 &= ~1u;
      if ( *a1 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
    }
  }
  v43 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v43);
  if ( (_QWORD)v43 && *(_BYTE *)(v43 + 128) )
  {
    v45[0] = &v36;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v19 = v47;
    if ( v49 > 0xF )
      v19 = (_QWORD *)v47[0];
    std::string::_Construct<2,char const *>(&v36, v19, v48);
    v34 = 0;
    v35 = 0;
    std::string::_Construct<1,char const *>(&v34, "Using enumerated service %s", (const char *)0x1B);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(
      &v43,
      "TEREDO",
      &v34,
      &v36);
    std::string::_Tidy_deallocate(&v34);
  }
  v20 = (volatile signed __int32 *)*((_QWORD *)&v43 + 1);
  if ( *((_QWORD *)&v43 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v43 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  std::string::_Tidy_deallocate(v47);
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  if ( v42[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v42[0] + 16LL))(v42[0]);
  if ( v44 )
    (*(void (__fastcall **)(__int64 *))(*v44 + 16))(v44);
  return a1;
}

```

## disassembly

```asm
0x1800d8fcc  mov     [rsp-8+arg_18], rbx
0x1800d8fd1  push    rbp
0x1800d8fd2  push    rsi
0x1800d8fd3  push    rdi
0x1800d8fd4  push    r12
0x1800d8fd6  push    r13
0x1800d8fd8  push    r14
0x1800d8fda  push    r15
0x1800d8fdc  lea     rbp, [rsp-90h]
0x1800d8fe4  mov     eax, 190h
0x1800d8fe9  call    _alloca_probe
0x1800d8fee  sub     rsp, rax
0x1800d8ff1  mov     rax, cs:__security_cookie
0x1800d8ff8  xor     rax, rsp
0x1800d8ffb  mov     [rbp+0C0h+var_38], rax
0x1800d9002  mov     r15, rdx
0x1800d9005  mov     rsi, rcx
0x1800d9008  mov     [rbp+0C0h+var_138], rcx
0x1800d900c  mov     [rsp+1C0h+var_148], 1
0x1800d9014  xor     r12d, r12d
0x1800d9017  mov     [rbp+0C0h+var_80], r12
0x1800d901b  mov     rcx, [r8]
0x1800d901e  mov     rax, [rcx]
0x1800d9021  mov     [rbp+0C0h+var_80], r12
0x1800d9025  lea     rdx, [rbp+0C0h+var_80]
0x1800d9029  mov     rax, [rax+0C8h]
0x1800d9030  call    cs:__guard_dispatch_icall_fptr
0x1800d9036  mov     ebx, eax
0x1800d9038  test    eax, eax
0x1800d903a  js      loc_1800D9573
0x1800d9040  mov     rcx, [rbp+0C0h+var_80]
0x1800d9044  mov     rax, [rcx]
0x1800d9047  lea     rdx, [rbp+0C0h+var_40]
0x1800d904e  mov     rax, [rax+38h]
0x1800d9052  call    cs:__guard_dispatch_icall_fptr
0x1800d9058  mov     ebx, eax
0x1800d905a  test    eax, eax
0x1800d905c  js      loc_1800D9600
0x1800d9062  cmp     [rbp+0C0h+var_40], r12d
0x1800d9069  jle     loc_1800D968D
0x1800d906f  mov     [rbp+0C0h+var_A0], r12
0x1800d9073  mov     rcx, [rbp+0C0h+var_80]
0x1800d9077  mov     rax, [rcx]
0x1800d907a  mov     [rbp+0C0h+var_A0], r12
0x1800d907e  lea     rdx, [rbp+0C0h+var_A0]
0x1800d9082  mov     rax, [rax+40h]
0x1800d9086  call    cs:__guard_dispatch_icall_fptr
0x1800d908c  mov     ebx, eax
0x1800d908e  test    eax, eax
0x1800d9090  js      loc_1800D9406
0x1800d9096  mov     [rbp+0C0h+var_68], r12
0x1800d909a  mov     r8b, [rsp+1C0h+var_190]
0x1800d909f  mov     rdx, [rbp+0C0h+var_A0]
0x1800d90a3  lea     rcx, [rbp+0C0h+var_68]
0x1800d90a7  call    ??$?0UIUnknown@@@?$com_ptr_t@UIEnumUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIUnknown@@U?$integral_constant@D$0A@@wistd@@@Z; wil::com_ptr_t<IEnumUnknown,wil::err_exception_policy>::com_ptr_t<IEnumUnknown,wil::err_exception_policy>(IUnknown *,wistd::integral_constant<char,0>)
0x1800d90ac  lea     edi, [r12+3]
0x1800d90b1  mov     rcx, [rbp+0C0h+var_68]
0x1800d90b5  mov     rax, [rcx]
0x1800d90b8  mov     rax, [rax+28h]
0x1800d90bc  call    cs:__guard_dispatch_icall_fptr
0x1800d90c2  or      r13d, 0FFFFFFFFh
0x1800d90c6  mov     rbx, [rbp+0C0h+var_68]
0x1800d90ca  mov     rax, [rbx]
0x1800d90cd  mov     r14, [rax+18h]
0x1800d90d1  mov     rcx, [rbp+0C0h+var_A0]
0x1800d90d5  mov     [rbp+0C0h+var_A0], r12
0x1800d90d9  test    rcx, rcx
0x1800d90dc  jz      short loc_1800D90EC
0x1800d90de  mov     rax, [rcx]
0x1800d90e1  mov     rax, [rax+10h]
0x1800d90e5  call    cs:__guard_dispatch_icall_fptr
0x1800d90eb  nop
0x1800d90ec  xor     r9d, r9d
0x1800d90ef  lea     r8, [rbp+0C0h+var_A0]
0x1800d90f3  lea     edx, [r9+1]
0x1800d90f7  mov     rcx, rbx
0x1800d90fa  mov     rax, r14
0x1800d90fd  call    cs:__guard_dispatch_icall_fptr
0x1800d9103  test    eax, eax
0x1800d9105  jnz     loc_1800D9493
0x1800d910b  xor     eax, eax
0x1800d910d  mov     [rsi], rax
0x1800d9110  mov     r8b, [rsp+1C0h+var_190]
0x1800d9115  mov     rdx, [rbp+0C0h+var_A0]
0x1800d9119  mov     rcx, rsi
0x1800d911c  call    ??$?0UIUnknown@@@?$com_ptr_t@UIUPnPService@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIUnknown@@U?$integral_constant@D$0A@@wistd@@@Z; wil::com_ptr_t<IUPnPService,wil::err_exception_policy>::com_ptr_t<IUPnPService,wil::err_exception_policy>(IUnknown *,wistd::integral_constant<char,0>)
0x1800d9121  or      edi, 4
0x1800d9124  or      edi, 1
0x1800d9127  mov     [rsp+1C0h+var_148], edi
0x1800d912b  mov     rcx, [rsi]
0x1800d912e  mov     [rbp+0C0h+var_140], rcx
0x1800d9132  test    rcx, rcx
0x1800d9135  jz      short loc_1800D9145
0x1800d9137  mov     rax, [rcx]
0x1800d913a  mov     rax, [rax+8]
0x1800d913e  call    cs:__guard_dispatch_icall_fptr
0x1800d9144  nop
0x1800d9145  lea     r8, ??_9IUPnPService@@$BEI@AA; [thunk]: IUPnPService::`vcall'{72,{flat}}
0x1800d914c  lea     rdx, [rbp+0C0h+var_140]
0x1800d9150  lea     rcx, [rbp+0C0h+var_60]
0x1800d9154  call    Microsoft__RdpNano___anonymous_namespace___GetComString_wil__com_ptr_t_IUPnPService_wil__err_exception_policy__long____cdecl_IUPnPService_____wchar_t______
0x1800d9159  nop
0x1800d915a  xorps   xmm0, xmm0
0x1800d915d  movups  [rbp+0C0h+var_90], xmm0
0x1800d9161  lea     rcx, [rbp+0C0h+var_90]
0x1800d9165  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800d916a  nop
0x1800d916b  mov     rax, qword ptr [rbp+0C0h+var_90]
0x1800d916f  test    rax, rax
0x1800d9172  jz      loc_1800D920C
0x1800d9178  cmp     [rax+80h], r12b
0x1800d917f  jz      loc_1800D920C
0x1800d9185  lea     rax, [rsp+1C0h+var_168]
0x1800d918a  mov     [rbp+0C0h+var_78], rax
0x1800d918e  xorps   xmm0, xmm0
0x1800d9191  movups  [rsp+1C0h+var_168], xmm0
0x1800d9196  mov     [rsp+1C0h+var_158], r12
0x1800d919b  mov     [rsp+1C0h+var_150], r12
0x1800d91a0  lea     rdx, [rbp+0C0h+var_60]
0x1800d91a4  cmp     [rbp+0C0h+var_48], 0Fh
0x1800d91a9  cmova   rdx, [rbp+0C0h+var_60]
0x1800d91ae  mov     r8, [rbp+0C0h+var_50]
0x1800d91b2  lea     rcx, [rsp+1C0h+var_168]
0x1800d91b7  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800d91bc  nop
0x1800d91bd  xorps   xmm0, xmm0
0x1800d91c0  movups  [rsp+1C0h+var_188], xmm0
0x1800d91c5  xorps   xmm1, xmm1
0x1800d91c8  movdqu  [rsp+1C0h+var_178], xmm1
0x1800d91ce  mov     r8d, 29h ; ')'
0x1800d91d4  lea     rdx, aServiceEnumera; "Service enumeration found UPnP service "...
0x1800d91db  lea     rcx, [rsp+1C0h+var_188]
0x1800d91e0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d91e5  nop
0x1800d91e6  lea     r9, [rsp+1C0h+var_168]
0x1800d91eb  lea     r8, [rsp+1C0h+var_188]
0x1800d91f0  lea     rdx, aRdpnano; "RDPNANO"
0x1800d91f7  lea     rcx, [rbp+0C0h+var_90]
0x1800d91fb  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@V65@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,std::string)
0x1800d9200  nop
0x1800d9201  lea     rcx, [rsp+1C0h+var_188]
0x1800d9206  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d920b  nop
0x1800d920c  mov     rbx, qword ptr [rbp+0C0h+var_90+8]
0x1800d9210  test    rbx, rbx
0x1800d9213  jz      short loc_1800D924E
0x1800d9215  mov     eax, r13d
0x1800d9218  lock xadd [rbx+8], eax
0x1800d921d  add     eax, r13d
0x1800d9220  jnz     short loc_1800D924E
0x1800d9222  mov     rax, [rbx]
0x1800d9225  mov     rcx, rbx
0x1800d9228  mov     rax, [rax]
0x1800d922b  call    cs:__guard_dispatch_icall_fptr
0x1800d9231  mov     eax, r13d
0x1800d9234  lock xadd [rbx+0Ch], eax
0x1800d9239  add     eax, r13d
0x1800d923c  jnz     short loc_1800D924E
0x1800d923e  mov     rax, [rbx]
0x1800d9241  mov     rcx, rbx
0x1800d9244  mov     rax, [rax+8]
0x1800d9248  call    cs:__guard_dispatch_icall_fptr
0x1800d924e  mov     r8b, [rsp+1C0h+var_190]
0x1800d9253  mov     rdx, r15
0x1800d9256  lea     rcx, [rbp+0C0h+var_60]
0x1800d925a  call    ??$starts_with@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@Uis_equal@algorithm@boost@@@algorithm@boost@@YA_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0Uis_equal@01@@Z; boost::algorithm::starts_with<std::string,std::string,boost::algorithm::is_equal>(std::string const &,std::string const &,boost::algorithm::is_equal)
0x1800d925f  test    al, al
0x1800d9261  jnz     short loc_1800D9295
0x1800d9263  lea     rcx, [rbp+0C0h+var_60]
0x1800d9267  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d926c  nop
0x1800d926d  test    dil, 1
0x1800d9271  jz      loc_1800D90C6
0x1800d9277  and     edi, 0FFFFFFFEh
0x1800d927a  mov     rcx, [rsi]
0x1800d927d  test    rcx, rcx
0x1800d9280  jz      short loc_1800D9290
0x1800d9282  mov     rax, [rcx]
0x1800d9285  mov     rax, [rax+10h]
0x1800d9289  call    cs:__guard_dispatch_icall_fptr
0x1800d928f  nop
0x1800d9290  jmp     loc_1800D90C6
0x1800d9295  xorps   xmm0, xmm0
0x1800d9298  movups  [rbp+0C0h+var_90], xmm0
0x1800d929c  lea     rcx, [rbp+0C0h+var_90]
0x1800d92a0  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800d92a5  nop
0x1800d92a6  mov     rax, qword ptr [rbp+0C0h+var_90]
0x1800d92aa  test    rax, rax
0x1800d92ad  jz      loc_1800D9347
0x1800d92b3  cmp     [rax+80h], r12b
0x1800d92ba  jz      loc_1800D9347
0x1800d92c0  lea     rax, [rsp+1C0h+var_168]
0x1800d92c5  mov     [rbp+0C0h+var_78], rax
0x1800d92c9  xorps   xmm0, xmm0
0x1800d92cc  movups  [rsp+1C0h+var_168], xmm0
0x1800d92d1  mov     [rsp+1C0h+var_158], r12
0x1800d92d6  mov     [rsp+1C0h+var_150], r12
0x1800d92db  lea     rdx, [rbp+0C0h+var_60]
0x1800d92df  cmp     [rbp+0C0h+var_48], 0Fh
0x1800d92e4  cmova   rdx, [rbp+0C0h+var_60]
0x1800d92e9  mov     r8, [rbp+0C0h+var_50]
0x1800d92ed  lea     rcx, [rsp+1C0h+var_168]
0x1800d92f2  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800d92f7  nop
0x1800d92f8  xorps   xmm0, xmm0
0x1800d92fb  movups  [rsp+1C0h+var_188], xmm0
0x1800d9300  xorps   xmm1, xmm1
0x1800d9303  movdqu  [rsp+1C0h+var_178], xmm1
0x1800d9309  mov     r8d, 1Bh
0x1800d930f  lea     rdx, aUsingEnumerate; "Using enumerated service %s"
0x1800d9316  lea     rcx, [rsp+1C0h+var_188]
0x1800d931b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d9320  nop
0x1800d9321  lea     r9, [rsp+1C0h+var_168]
0x1800d9326  lea     r8, [rsp+1C0h+var_188]
0x1800d932b  lea     rdx, aTeredo; "TEREDO"
0x1800d9332  lea     rcx, [rbp+0C0h+var_90]
0x1800d9336  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@V65@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,std::string)
0x1800d933b  nop
0x1800d933c  lea     rcx, [rsp+1C0h+var_188]
0x1800d9341  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d9346  nop
0x1800d9347  mov     rbx, qword ptr [rbp+0C0h+var_90+8]
0x1800d934b  test    rbx, rbx
0x1800d934e  jz      short loc_1800D938A
0x1800d9350  mov     eax, r13d
0x1800d9353  lock xadd [rbx+8], eax
0x1800d9358  add     eax, r13d
0x1800d935b  jnz     short loc_1800D938A
0x1800d935d  mov     rax, [rbx]
0x1800d9360  mov     rcx, rbx
0x1800d9363  mov     rax, [rax]
0x1800d9366  call    cs:__guard_dispatch_icall_fptr
0x1800d936c  mov     eax, r13d
0x1800d936f  lock xadd [rbx+0Ch], eax
0x1800d9374  add     eax, r13d
0x1800d9377  jnz     short loc_1800D938A
0x1800d9379  mov     rax, [rbx]
0x1800d937c  mov     rcx, rbx
0x1800d937f  mov     rax, [rax+8]
0x1800d9383  call    cs:__guard_dispatch_icall_fptr
0x1800d9389  nop
0x1800d938a  lea     rcx, [rbp+0C0h+var_60]
0x1800d938e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d9393  nop
0x1800d9394  mov     rcx, [rbp+0C0h+var_68]
0x1800d9398  test    rcx, rcx
0x1800d939b  jz      short loc_1800D93AB
0x1800d939d  mov     rax, [rcx]
0x1800d93a0  mov     rax, [rax+10h]
0x1800d93a4  call    cs:__guard_dispatch_icall_fptr
0x1800d93aa  nop
0x1800d93ab  mov     rcx, [rbp+0C0h+var_A0]
0x1800d93af  test    rcx, rcx
0x1800d93b2  jz      short loc_1800D93C2
0x1800d93b4  mov     rax, [rcx]
0x1800d93b7  mov     rax, [rax+10h]
0x1800d93bb  call    cs:__guard_dispatch_icall_fptr
0x1800d93c1  nop
0x1800d93c2  mov     rcx, [rbp+0C0h+var_80]
0x1800d93c6  test    rcx, rcx
0x1800d93c9  jz      short loc_1800D93D9
0x1800d93cb  mov     rdx, [rcx]
0x1800d93ce  mov     rax, [rdx+10h]
0x1800d93d2  call    cs:__guard_dispatch_icall_fptr
0x1800d93d8  nop
0x1800d93d9  mov     rax, rsi
0x1800d93dc  mov     rcx, [rbp+0C0h+var_38]
0x1800d93e3  xor     rcx, rsp; StackCookie
0x1800d93e6  call    __security_check_cookie
0x1800d93eb  mov     rbx, [rsp+1C0h+arg_18]
0x1800d93f3  add     rsp, 190h
0x1800d93fa  pop     r15
0x1800d93fc  pop     r14
0x1800d93fe  pop     r13
0x1800d9400  pop     r12
0x1800d9402  pop     rdi
0x1800d9403  pop     rsi
0x1800d9404  pop     rbp
0x1800d9405  retn
0x1800d9406  lfence
0x1800d9409  lea     rdx, Str1
0x1800d9410  lea     rcx, [rsp+1C0h+var_188]
0x1800d9415  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d941a  nop
0x1800d941b  lea     rdx, aCW1SRdpnanodll_13; "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpma"...
0x1800d9422  lea     rcx, [rsp+1C0h+var_168]
0x1800d9427  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d942c  nop
0x1800d942d  lea     rdx, aFailedToGetSer_1; "Failed to get service enumerator"
0x1800d9434  lea     rcx, [rbp+0C0h+var_60]
0x1800d9438  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d943d  nop
0x1800d943e  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x1800d9443  mov     r8, rax; struct std::error_category *
0x1800d9446  mov     edx, ebx; int
0x1800d9448  lea     rcx, [rbp+0C0h+var_78]; this
0x1800d944c  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x1800d9451  movups  xmm0, xmmword ptr [rax]
  ... truncated ...
```
