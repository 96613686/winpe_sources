# Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedProcess(void)

- ea: `0x180152cc0`
- end: `0x180153461`
- name: `?ThreadedProcess@WinsockDCTChannelContext@Dct@Basix@Microsoft@@MEAA_NXZ`
- size: `1953`
- prototype: `bool __fastcall(Microsoft::Basix::Dct::WinsockDCTChannelContext *__hidden this)`
- caller_count: `0`
- callee_count: `23`
- tags: `broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017344`
- `0x180018ea4`
- `0x18001902c`
- `0x180024700`
- `0x180027bf8`
- `0x18002a8ec`
- `0x18003d8fc`
- `0x1800bb210`
- `0x18014d8e8`
- `0x18014daec`
- `0x18014e01c`
- `0x180151be4`
- `0x180152cc0`
- `0x180153ac0`
- `0x1801acb74`
- `0x1802e9b68`
- `0x1802ed54c`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180152df5`
- `KERNEL32!GetLastError` at `0x180152df5`

## string_xrefs

- `0x18015315f`: `Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedProcess`
- `0x18015314d`: `Channel %s(%p@%s): Read IO failed. Terminating IO thread.\n    %s(%d): %s()`
- `0x18015329b`: `Channel %s(%p@%s): Received normal shutdown by peer. Terminating IO thread.`
- `0x180152e50`: `GetQueuedCompletionStatus() incomplete write: error(%d), bytesTransfered(%d), expectedBytesTransfered=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=55
char __fastcall Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedProcess(HANDLE *this)
{
  Microsoft::Basix::Dct::WinsockDCTChannelContext *v2; // rdi
  char **v3; // rax
  char *v4; // rcx
  char *v5; // r8
  __int64 v6; // r12
  Microsoft::Basix::Containers::FlexOBuffer *v7; // rax
  __int64 v8; // rsi
  DWORD LastError; // r15d
  int v10; // r9d
  __int64 v11; // rbx
  volatile signed __int32 *v12; // rsi
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  const void *v16; // r9
  HANDLE *v17; // rbx
  HANDLE *v18; // r14
  volatile signed __int32 *v19; // rdi
  const void *v20; // r9
  HANDLE *v21; // rbx
  HANDLE *v22; // r14
  volatile signed __int32 *v23; // rsi
  const void *v24; // r9
  HANDLE *v25; // rbx
  HANDLE *v26; // r14
  volatile signed __int32 *v27; // rdi
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 *Description; // rax
  const char *v34; // r9
  __int64 v35; // rbx
  volatile signed __int32 *v36; // rbx
  __int64 *v37; // rax
  const char *v38; // r9
  __int64 v39; // rbx
  volatile signed __int32 *v40; // rbx
  __int64 *v41; // rax
  const char *v42; // r9
  __int64 v43; // rbx
  volatile signed __int32 *v44; // rbx
  const char *v45; // r9
  volatile signed __int32 *v46; // rbx
  _BYTE *v47; // rbp
  __int64 v48; // rax
  __int64 *v49; // rax
  const char *v50; // r9
  __int64 v51; // rbx
  volatile signed __int32 *v52; // rbx
  _BYTE *v53; // rbp
  __int64 v54; // rax
  __int64 *v55; // rax
  const char *v56; // r9
  __int64 v57; // rbx
  volatile signed __int32 *v58; // rbx
  _BYTE *v59; // rbp
  __int64 v60; // rax
  __int64 *v61; // rax
  const char *v62; // r9
  __int64 v63; // rbx
  volatile signed __int32 *v64; // rbx
  _BYTE *v65; // rbp
  const char *v66; // r9
  __int64 v67; // rax
  volatile signed __int32 *v68; // rbx
  _BYTE *v69; // rdx
  _BYTE *v70; // rdx
  _BYTE *v71; // rdx
  _BYTE *v72; // rdx
  const char *v73; // [rsp+20h] [rbp-178h]
  int v74; // [rsp+28h] [rbp-170h]
  const char *v75; // [rsp+30h] [rbp-168h]
  const char *v76; // [rsp+20h] [rbp-178h]
  int v77; // [rsp+28h] [rbp-170h]
  const char *v78; // [rsp+30h] [rbp-168h]
  const char *v79; // [rsp+20h] [rbp-178h]
  int v80; // [rsp+28h] [rbp-170h]
  const char *v81; // [rsp+30h] [rbp-168h]
  const char *v82; // [rsp+20h] [rbp-178h]
  int v83; // [rsp+28h] [rbp-170h]
  const char *v84; // [rsp+30h] [rbp-168h]
  const char *v85; // [rsp+20h] [rbp-178h]
  int v86; // [rsp+28h] [rbp-170h]
  const char *v87; // [rsp+30h] [rbp-168h]
  const char *v88; // [rsp+20h] [rbp-178h]
  int v89; // [rsp+28h] [rbp-170h]
  const char *v90; // [rsp+30h] [rbp-168h]
  const char *v91; // [rsp+20h] [rbp-178h]
  int v92; // [rsp+28h] [rbp-170h]
  const char *v93; // [rsp+30h] [rbp-168h]
  const char *v94; // [rsp+20h] [rbp-178h]
  int v95; // [rsp+28h] [rbp-170h]
  const char *v96; // [rsp+30h] [rbp-168h]
  _BYTE v97[32]; // [rsp+0h] [rbp-198h] BYREF
  const char *v98; // [rsp+20h] [rbp-178h]
  const char *v99; // [rsp+28h] [rbp-170h]
  __int64 v100; // [rsp+30h] [rbp-168h]
  const char *v101; // [rsp+38h] [rbp-160h]
  __int128 v102; // [rsp+50h] [rbp-148h] BYREF
  __int128 v103; // [rsp+60h] [rbp-138h]
  Microsoft::Basix::Dct::WinsockDCTChannelContext *v104; // [rsp+70h] [rbp-128h]
  HANDLE *v105; // [rsp+78h] [rbp-120h]
  _BYTE v106[32]; // [rsp+80h] [rbp-118h] BYREF
  const Microsoft::Basix::Exception *v107; // [rsp+A0h] [rbp-F8h] BYREF
  const std::exception *v108; // [rsp+A8h] [rbp-F0h] BYREF
  const boost::exception *v109; // [rsp+B0h] [rbp-E8h] BYREF
  const Microsoft::Basix::Exception *v110; // [rsp+B8h] [rbp-E0h] BYREF
  const std::exception *v111; // [rsp+C0h] [rbp-D8h] BYREF
  const boost::exception *v112; // [rsp+C8h] [rbp-D0h] BYREF
  _BYTE pExceptionObject[128]; // [rsp+D0h] [rbp-C8h] BYREF
  char *v114; // [rsp+150h] [rbp-48h] BYREF
  _OWORD v115[2]; // [rsp+158h] [rbp-40h] BYREF

  v114 = 0;
  v2 = (Microsoft::Basix::Dct::WinsockDCTChannelContext *)(this - 136);
  v105 = this - 136;
  v104 = (Microsoft::Basix::Dct::WinsockDCTChannelContext *)(this - 136);
  v3 = Microsoft::Basix::Dct::WinsockDCTChannelContext::WaitForIOCPRequestCompletion(this - 136, (char **)v115);
  v4 = *v3;
  *v3 = 0;
  v5 = v114;
  v114 = v4;
  if ( v5 )
  {
    (**(void (__fastcall ***)(char *, __int64))v5)(v5, 1);
    v4 = v114;
  }
  if ( *(_QWORD *)&v115[0] )
  {
    (***(void (__fastcall ****)(_QWORD, __int64))&v115[0])(*(_QWORD *)&v115[0], 1);
    v4 = v114;
  }
  if ( !v4 )
    return 1;
  if ( *((_DWORD *)v4 + 71) != 1 )
  {
    if ( *((_DWORD *)v4 + 71) != 2 )
    {
      if ( *((_DWORD *)v4 + 71) != 3 )
      {
        std::string::string(&v102, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp");
        std::string::string(v115, "Invalid request type received.");
        Microsoft::Basix::Exception::Exception(pExceptionObject, v115, &v102, 509);
        throw (Microsoft::Basix::Exception *)pExceptionObject;
      }
      goto LABEL_67;
    }
    v6 = *(_QWORD *)(std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*((_QWORD *)v4 + 11))
                   + 136);
    v7 = Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(*((Microsoft::Basix::Dct::IAsyncTransport::OutBuffer **)v114
                                                                  + 11));
    v8 = Microsoft::Basix::Containers::FlexOBuffer::Size(v7) - v6;
    if ( *((_QWORD *)v114 + 15) != v8 )
    {
      LastError = GetLastError();
      v115[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v115);
      if ( *(_QWORD *)&v115[0] && *(_BYTE *)(*(_QWORD *)&v115[0] + 128LL) )
      {
        v11 = *((_QWORD *)v114 + 15);
        v102 = 0;
        v103 = 0;
        std::string::_Construct<1,char const *>(
          &v102,
          "GetQueuedCompletionStatus() incomplete write: error(%d), bytesTransfered(%d), expectedBytesTransfered=%d",
          104,
          v10,
          (_DWORD)v98);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned long,unsigned __int64,unsigned __int64>(
          (unsigned int)v115,
          (unsigned int)"NANO_DCT",
          (unsigned int)&v102,
          LastError,
          v11,
          v8);
        std::string::_Tidy_deallocate(&v102);
      }
      v12 = (volatile signed __int32 *)*((_QWORD *)&v115[0] + 1);
      if ( *((_QWORD *)&v115[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v115[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
    }
    v13 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*((_QWORD *)v114 + 11));
    *(_QWORD *)(v13 + 136) = v6 + *((_QWORD *)v114 + 15);
    if ( !*((_BYTE *)this + 3008)
      || (Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(
            v2,
            (const struct std::exception_ptr *)(v114 + 104),
            0),
          !(unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                              v114 + 104,
                              v14)) )
    {
LABEL_20:
      (*((void (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTChannelContext *, char **))*v105 + 23))(v2, &v114);
LABEL_66:
      v4 = v114;
LABEL_67:
      if ( v4 )
        (**(void (__fastcall ***)(char *, __int64))v4)(v4, 1);
      return 1;
    }
    v29 = boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v114);
    v30 = std::exception_ptr::exception_ptr((std::exception_ptr *)v115, (const struct std::exception_ptr *)(v29 + 104));
    try
    {
      std::rethrow_exception(v30);
    }
    catch ( const Microsoft::Basix::Exception *v107 )
    {
      v115[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v115);
      if ( *(_QWORD *)&v115[0] && *(_BYTE *)(*(_QWORD *)&v115[0] + 128LL) )
      {
        Description = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v106, v107);
        v35 = (__int64)Description;
        if ( (unsigned __int64)Description[3] > 0xF )
          v35 = *Description;
        v102 = 0;
        v103 = 0u;
        std::string::_Construct<1,char const *>(
          &v102,
          "%s: %s\n Caught at:\n    %s(%d): %s()",
          (const char *)0x23,
          v34,
          v82,
          v83,
          v84);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
          (unsigned int)v115,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v102,
          (unsigned int)"Write IO failed with exception. treated as non-fatal, ignore and continue",
          v35,
          (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp",
          239,
          (__int64)"Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedProcess");
        std::string::_Tidy_deallocate(&v102);
        std::string::_Tidy_deallocate(v106);
      }
      v36 = (volatile signed __int32 *)*((_QWORD *)&v115[0] + 1);
      if ( *((_QWORD *)&v115[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v115[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
          if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
        }
      }
      v2 = v104;
      goto LABEL_20;
    }
    catch ( const std::exception *v108 )
    {
      v115[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v115);
      if ( *(_QWORD *)&v115[0] && *(_BYTE *)(*(_QWORD *)&v115[0] + 128LL) )
      {
        v37 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v106, v108);
        v39 = (__int64)v37;
        if ( (unsigned __int64)v37[3] > 0xF )
          v39 = *v37;
        v102 = 0;
        v103 = 0u;
        std::string::_Construct<1,char const *>(
          &v102,
          "%s: %s\n Caught at:\n    %s(%d): %s()",
          (const char *)0x23,
          v38,
          v79,
          v80,
          v81);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
          (unsigned int)v115,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v102,
          (unsigned int)"Write IO failed with exception. treated as non-fatal, ignore and continue",
          v39,
          (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp",
          239,
          (__int64)"Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedProcess");
        std::string::_Tidy_deallocate(&v102);
        std::string::_Tidy_deallocate(v106);
      }
      v40 = (volatile signed __int32 *)*((_QWORD *)&v115[0] + 1);
      if ( *((_QWORD *)&v115[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v115[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
          if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
        }
      }
      v2 = v104;
      goto LABEL_20;
    }
    catch ( const boost::exception *v109 )
    {
      v115[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v115);
      if ( *(_QWORD *)&v115[0] && *(_BYTE *)(*(_QWORD *)&v115[0] + 128LL) )
      {
        v41 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v106, v109);
        v43 = (__int64)v41;
        if ( (unsigned __int64)v41[3] > 0xF )
          v43 = *v41;
        v102 = 0;
        v103 = 0u;
        std::string::_Construct<1,char const *>(
          &v102,
          "%s: %s\n Caught at:\n    %s(%d): %s()",
          (const char *)0x23,
          v42,
          v76,
          v77,
          v78);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
          (unsigned int)v115,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v102,
          (unsigned int)"Write IO failed with exception. treated as non-fatal, ignore and continue",
          v43,
          (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp",
          239,
          (__int64)"Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedProcess");
        std::string::_Tidy_deallocate(&v102);
        std::string::_Tidy_deallocate(v106);
      }
      v44 = (volatile signed __int32 *)*((_QWORD *)&v115[0] + 1);
      if ( *((_QWORD *)&v115[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v115[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
          if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
        }
      }
      v2 = v104;
      goto LABEL_20;
    }
    catch ( ... )
    {
      v115[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v115);
      if ( *(_QWORD *)&v115[0] && *(_BYTE *)(*(_QWORD *)&v115[0] + 128LL) )
      {
        v102 = 0;
        v103 = 0u;
        std::string::_Construct<1,char const *>(
          &v102,
          "%s: %s\n Caught at:\n    %s(%d): %s()",
          (const char *)0x23,
          v45,
          v73,
          v74,
          v75);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
          (unsigned int)v115,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v102,
          (unsigned int)"Write IO failed with exception. treated as non-fatal, ignore and continue",
          (__int64)"due to unknown error",
          (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp",
          239,
          (__int64)"Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedProcess");
        std::string::_Tidy_deallocate(&v102);
      }
      v46 = (volatile signed __int32 *)*((_QWORD *)&v115[0] + 1);
      if ( *((_QWORD *)&v115[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v115[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
          if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
        }
      }
      v2 = v104;
      goto LABEL_20;
    }
LABEL_160:
    try
    {
      v31 = boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v114);
      v32 = std::exception_ptr::exception_ptr(
              (std::exception_ptr *)v115,
              (const struct std::exception_ptr *)(v31 + 104));
      std::rethrow_exception(v32);
      JUMPOUT(0x18015345FLL);
    }
    catch ( const Microsoft::Basix::Exception *v110 )
    {
      v69 = v97;
      v47 = v69;
      *(_OWORD *)(v69 + 344) = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v69 + 344);
      v48 = *((_QWORD *)v47 + 43);
      if ( v48 && *(_BYTE *)(v48 + 128) )
      {
        v49 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v47 + 128, *((_QWORD *)v47 + 23));
        v51 = (__int64)v49;
        if ( (unsigned __int64)v49[3] > 0xF )
          v51 = *v49;
        *((_OWORD *)v47 + 5) = 0;
        *((_QWORD *)v47 + 12) = 0;
        *((_QWORD *)v47 + 13) = 0;
        std::string::_Construct<1,char const *>(
          v47 + 80,
          "%s: %s\n Caught at:\n    %s(%d): %s()",
          (const char *)0x23,
          v50,
          v94,
          v95,
          v96);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
          (_DWORD)v47 + 344,
          (unsigned int)"BASIX_DCT",
          (_DWORD)v47 + 80,
          (unsigned int)"Read IO failed with exception. treated as non-fatal, ignore and continue",
          v51,
          (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp",
          191,
          (__int64)"Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedProcess");
        std::string::_Tidy_deallocate(v47 + 80);
        std::string::_Tidy_deallocate(v47 + 128);
      }
      v52 = (volatile signed __int32 *)*((_QWORD *)v47 + 44);
      if ( v52 )
      {
        if ( _InterlockedExchangeAdd(v52 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
          if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
        }
      }
      goto LABEL_24;
    }
    catch ( const std::exception *v111 )
    {
      v70 = v97;
      v53 = v70;
      *(_OWORD *)(v70 + 344) = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v70 + 344);
      v54 = *((_QWORD *)v53 + 43);
      if ( v54 && *(_BYTE *)(v54 + 128) )
      {
        v55 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v53 + 128, *((_QWORD *)v53 + 24));
        v57 = (__int64)v55;
        if ( (unsigned __int64)v55[3] > 0xF )
          v57 = *v55;
        *((_OWORD *)v53 + 5) = 0;
        *((_QWORD *)v53 + 12) = 0;
        *((_QWORD *)v53 + 13) = 0;
        std::string::_Construct<1,char const *>(
          v53 + 80,
          "%s: %s\n Caught at:\n    %s(%d): %s()",
          (const char *)0x23,
          v56,
          v91,
          v92,
          v93);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
          (_DWORD)v53 + 344,
          (unsigned int)"BASIX_DCT",
          (_DWORD)v53 + 80,
          (unsigned int)"Read IO failed with exception. treated as non-fatal, ignore and continue",
          v57,
          (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp",
          191,
          (__int64)"Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedProcess");
        std::string::_Tidy_deallocate(v53 + 80);
        std::string::_Tidy_deallocate(v53 + 128);
      }
      v58 = (volatile signed __int32 *)*((_QWORD *)v53 + 44);
      if ( v58 )
      {
        if ( _InterlockedExchangeAdd(v58 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
          if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
        }
      }
      goto LABEL_24;
    }
    catch ( const boost::exception *v112 )
    {
      v71 = v97;
      v59 = v71;
      *(_OWORD *)(v71 + 344) = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v71 + 344);
      v60 = *((_QWORD *)v59 + 43);
      if ( v60 && *(_BYTE *)(v60 + 128) )
      {
        v61 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v59 + 128, *((_QWORD *)v59 + 25));
        v63 = (__int64)v61;
        if ( (unsigned __int64)v61[3] > 0xF )
          v63 = *v61;
        *((_OWORD *)v59 + 5) = 0;
        *((_QWORD *)v59 + 12) = 0;
        *((_QWORD *)v59 + 13) = 0;
        std::string::_Construct<1,char const *>(
          v59 + 80,
          "%s: %s\n Caught at:\n    %s(%d): %s()",
          (const char *)0x23,
          v62,
          v88,
          v89,
          v90);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
          (_DWORD)v59 + 344,
          (unsigned int)"BASIX_DCT",
          (_DWORD)v59 + 80,
          (unsigned int)"Read IO failed with exception. treated as non-fatal, ignore and continue",
          v63,
          (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp",
          191,
          (__int64)"Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedProcess");
        std::string::_Tidy_deallocate(v59 + 80);
        std::string::_Tidy_deallocate(v59 + 128);
      }
      v64 = (volatile signed __int32 *)*((_QWORD *)v59 + 44);
      if ( v64 )
      {
        if ( _InterlockedExchangeAdd(v64 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v64)(v64);
          if ( _InterlockedExchangeAdd(v64 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v64 + 8LL))(v64);
        }
      }
      goto LABEL_24;
    }
    catch ( ... )
    {
      v72 = v97;
      v65 = v72;
      *(_OWORD *)(v72 + 344) = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v72 + 344);
      v67 = *((_QWORD *)v65 + 43);
      if ( v67 && *(_BYTE *)(v67 + 128) )
      {
        *((_OWORD *)v65 + 5) = 0;
        *((_QWORD *)v65 + 12) = 0;
        *((_QWORD *)v65 + 13) = 0;
        std::string::_Construct<1,char const *>(
          v65 + 80,
          "%s: %s\n Caught at:\n    %s(%d): %s()",
          (const char *)0x23,
          v66,
          v85,
          v86,
          v87);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
          (_DWORD)v65 + 344,
          (unsigned int)"BASIX_DCT",
          (_DWORD)v65 + 80,
          (unsigned int)"Read IO failed with exception. treated as non-fatal, ignore and continue",
          (__int64)"due to unknown error",
          (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp",
          191,
          (__int64)"Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedProcess");
        std::string::_Tidy_deallocate(v65 + 80);
      }
      v68 = (volatile signed __int32 *)*((_QWORD *)v65 + 44);
      if ( v68 )
      {
        if ( _InterlockedExchangeAdd(v68 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
          if ( _InterlockedExchangeAdd(v68 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
        }
      }
      goto LABEL_24;
    }
  }
  if ( *((_BYTE *)this + 3008) )
  {
    Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(
      v2,
      (const struct std::exception_ptr *)(v4 + 104),
      1);
    if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                            v114 + 104,
                            v15) )
      goto LABEL_160;
    if ( !*((_QWORD *)v114 + 15) )
    {
      v115[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v115);
      if ( *(_QWORD *)&v115[0] && *(_BYTE *)(*(_QWORD *)&v115[0] + 128LL) )
      {
        v17 = this - 123;
        if ( (unsigned __int64)*(this - 120) > 0xF )
          v17 = (HANDLE *)*v17;
        v18 = this - 107;
        if ( (unsigned __int64)v18[3] > 0xF )
          v18 = (HANDLE *)*v18;
        v102 = 0;
        v103 = 0;
        std::string::_Construct<1,char const *>(
          &v102,
          "Channel %s(%p@%s): Received normal shutdown by peer. ignore and continue.",
          (const char *)0x49,
          v16,
          v98);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,Microsoft::Basix::Dct::WinsockDCTChannelContext *,char const *>(
          (unsigned int)v115,
          (unsigned int)"NANO_DCT",
          (unsigned int)&v102,
          (_DWORD)v18,
          (__int64)v2,
          (__int64)v17);
        std::string::_Tidy_deallocate(&v102);
      }
      v19 = (volatile signed __int32 *)*((_QWORD *)&v115[0] + 1);
      if ( *((_QWORD *)&v115[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v115[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
          if ( !_InterlockedDecrement(v19 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        }
      }
LABEL_24:
      v4 = v114;
      goto LABEL_67;
    }
LABEL_65:
    (*(void (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTChannelContext *, char **, _QWORD))(*(_QWORD *)v2 + 176LL))(
      v2,
      &v114,
      0);
    goto LABEL_66;
  }
  if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                          v4 + 104,
                          (unsigned int)(*((_DWORD *)v4 + 71) - 1)) )
  {
    v115[0] = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v115);
    if ( *(_QWORD *)&v115[0] && *(_BYTE *)(*(_QWORD *)&v115[0] + 128LL) )
    {
      v21 = this - 123;
      if ( (unsigned __int64)*(this - 120) > 0xF )
        v21 = (HANDLE *)*v21;
      v22 = this - 107;
      if ( (unsigned __int64)v22[3] > 0xF )
        v22 = (HANDLE *)*v22;
      v102 = 0;
      v103 = 0;
      std::string::_Construct<1,char const *>(
        &v102,
        "Channel %s(%p@%s): Read IO failed. Terminating IO thread.\n    %s(%d): %s()",
        (const char *)0x4A,
        v20,
        v98,
        v99,
        v100,
        v101);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,Microsoft::Basix::Dct::WinsockDCTChannelContext *,char const *,char const *,int,char const *>(
        (unsigned int)v115,
        (unsigned int)"NANO_DCT",
        (unsigned int)&v102,
        (_DWORD)v22,
        (__int64)v2,
        (__int64)v21,
        (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp",
        204,
        (__int64)"Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedProcess");
      std::string::_Tidy_deallocate(&v102);
    }
    v23 = (volatile signed __int32 *)*((_QWORD *)&v115[0] + 1);
    if ( *((_QWORD *)&v115[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v115[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
    (*((void (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTChannelContext *, char *))*v105 + 15))(v2, v114 + 104);
  }
  else
  {
    if ( *((_QWORD *)v114 + 15) )
      goto LABEL_65;
    v115[0] = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v115);
    if ( *(_QWORD *)&v115[0] && *(_BYTE *)(*(_QWORD *)&v115[0] + 128LL) )
    {
      v25 = this - 123;
      if ( (unsigned __int64)*(this - 120) > 0xF )
        v25 = (HANDLE *)*v25;
      v26 = this - 107;
      if ( (unsigned __int64)v26[3] > 0xF )
        v26 = (HANDLE *)*v26;
      v102 = 0;
      v103 = 0;
      std::string::_Construct<1,char const *>(
        &v102,
        "Channel %s(%p@%s): Received normal shutdown by peer. Terminating IO thread.",
        (const char *)0x4B,
        v24,
        v98);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,Microsoft::Basix::Dct::WinsockDCTChannelContext *,char const *>(
        (unsigned int)v115,
        (unsigned int)"NANO_DCT",
        (unsigned int)&v102,
        (_DWORD)v26,
        (__int64)v2,
        (__int64)v25);
      std::string::_Tidy_deallocate(&v102);
    }
    v27 = (volatile signed __int32 *)*((_QWORD *)&v115[0] + 1);
    if ( *((_QWORD *)&v115[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v115[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
        if ( !_InterlockedDecrement(v27 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
      }
    }
  }
  if ( v114 )
    (**(void (__fastcall ***)(char *, __int64))v114)(v114, 1);
  return 0;
}

```

## disassembly

```asm
0x180152cc0  mov     [rsp+arg_8], rbx
0x180152cc5  mov     [rsp+arg_10], rsi
0x180152cca  mov     [rsp+arg_18], rdi
0x180152ccf  push    r12
0x180152cd1  push    r14
0x180152cd3  push    r15
0x180152cd5  mov     eax, 180h
0x180152cda  call    _alloca_probe
0x180152cdf  sub     rsp, rax
0x180152ce2  mov     rax, cs:__security_cookie
0x180152ce9  xor     rax, rsp
0x180152cec  mov     [rsp+198h+var_20], rax
0x180152cf4  mov     r14, rcx
0x180152cf7  mov     [rsp+198h+var_48], 0
0x180152d03  lea     rdi, [rcx-440h]
0x180152d0a  mov     [rsp+198h+var_120], rdi
0x180152d0f  mov     [rsp+198h+var_128], rdi
0x180152d14  lea     rdx, [rsp+198h+var_40]
0x180152d1c  mov     rcx, rdi
0x180152d1f  call    ?WaitForIOCPRequestCompletion@WinsockDCTChannelContext@Dct@Basix@Microsoft@@IEAA?AV?$unique_ptr@VWinsockDCTIORequest@Dct@Basix@Microsoft@@U?$default_delete@VWinsockDCTIORequest@Dct@Basix@Microsoft@@@std@@@std@@XZ; Microsoft::Basix::Dct::WinsockDCTChannelContext::WaitForIOCPRequestCompletion(void)
0x180152d24  mov     rcx, [rax]
0x180152d27  mov     qword ptr [rax], 0
0x180152d2e  mov     r8, [rsp+198h+var_48]
0x180152d36  mov     [rsp+198h+var_48], rcx
0x180152d3e  test    r8, r8
0x180152d41  jz      short loc_180152D5F
0x180152d43  mov     rax, [r8]
0x180152d46  mov     edx, 1
0x180152d4b  mov     rcx, r8
0x180152d4e  mov     rax, [rax]
0x180152d51  call    cs:__guard_dispatch_icall_fptr
0x180152d57  mov     rcx, [rsp+198h+var_48]
0x180152d5f  mov     r8, qword ptr [rsp+198h+var_40]
0x180152d67  test    r8, r8
0x180152d6a  jz      short loc_180152D88
0x180152d6c  mov     rcx, [r8]
0x180152d6f  mov     rax, [rcx]
0x180152d72  mov     edx, 1
0x180152d77  mov     rcx, r8
0x180152d7a  call    cs:__guard_dispatch_icall_fptr
0x180152d80  mov     rcx, [rsp+198h+var_48]
0x180152d88  test    rcx, rcx
0x180152d8b  jnz     short loc_180152D92
0x180152d8d  jmp     loc_180153386
0x180152d92  mov     edx, [rcx+11Ch]
0x180152d98  sub     edx, 1
0x180152d9b  jz      loc_180152F6A
0x180152da1  sub     edx, 1
0x180152da4  jz      short loc_180152DB4
0x180152da6  cmp     edx, 1
0x180152da9  jnz     loc_1801533B6
0x180152daf  jmp     loc_180153370
0x180152db4  mov     rcx, [rcx+58h]
0x180152db8  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x180152dbd  mov     r12, [rax+88h]
0x180152dc4  mov     rcx, [rsp+198h+var_48]
0x180152dcc  mov     rcx, [rcx+58h]; this
0x180152dd0  call    ?FlexO@OutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@QEAAAEAVFlexOBuffer@Containers@45@XZ; Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(void)
0x180152dd5  mov     rcx, rax; this
0x180152dd8  call    ?Size@FlexOBuffer@Containers@Basix@Microsoft@@QEBA_KXZ; Microsoft::Basix::Containers::FlexOBuffer::Size(void)
0x180152ddd  mov     rsi, rax
0x180152de0  sub     rsi, r12
0x180152de3  mov     rcx, [rsp+198h+var_48]
0x180152deb  cmp     [rcx+78h], rsi
0x180152def  jz      loc_180152ED9
0x180152df5  call    cs:__imp_GetLastError
0x180152dfb  mov     r15d, eax
0x180152dfe  xorps   xmm0, xmm0
0x180152e01  movups  [rsp+198h+var_40], xmm0
0x180152e09  lea     rcx, [rsp+198h+var_40]
0x180152e11  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180152e16  nop
0x180152e17  mov     rcx, qword ptr [rsp+198h+var_40]
0x180152e1f  test    rcx, rcx
0x180152e22  jz      short loc_180152E94
0x180152e24  cmp     byte ptr [rcx+80h], 0
0x180152e2b  jz      short loc_180152E94
0x180152e2d  mov     rax, [rsp+198h+var_48]
0x180152e35  mov     rbx, [rax+78h]
0x180152e39  xorps   xmm0, xmm0
0x180152e3c  movups  [rsp+198h+var_148], xmm0
0x180152e41  xorps   xmm1, xmm1
0x180152e44  movdqu  [rsp+198h+var_138], xmm1
0x180152e4a  mov     r8d, 68h ; 'h'
0x180152e50  lea     rdx, aGetqueuedcompl; "GetQueuedCompletionStatus() incomplete "...
0x180152e57  lea     rcx, [rsp+198h+var_148]
0x180152e5c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180152e61  nop
0x180152e62  mov     [rsp+198h+var_170], rsi
0x180152e67  mov     [rsp+198h+var_178], rbx
0x180152e6c  mov     r9d, r15d
0x180152e6f  lea     r8, [rsp+198h+var_148]
0x180152e74  lea     rdx, aNanoDct; "NANO_DCT"
0x180152e7b  lea     rcx, [rsp+198h+var_40]
0x180152e83  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@K_K_K@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@K_K3@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,ulong,unsigned __int64,unsigned __int64>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,ulong,unsigned __int64,unsigned __int64)
0x180152e88  nop
0x180152e89  lea     rcx, [rsp+198h+var_148]
0x180152e8e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180152e93  nop
0x180152e94  mov     rsi, qword ptr [rsp+198h+var_40+8]
0x180152e9c  test    rsi, rsi
0x180152e9f  jz      short loc_180152ED9
0x180152ea1  or      ebx, 0FFFFFFFFh
0x180152ea4  mov     eax, ebx
0x180152ea6  lock xadd [rsi+8], eax
0x180152eab  add     eax, ebx
0x180152ead  jnz     short loc_180152ED9
0x180152eaf  mov     rax, [rsi]
0x180152eb2  mov     rcx, rsi
0x180152eb5  mov     rax, [rax]
0x180152eb8  call    cs:__guard_dispatch_icall_fptr
0x180152ebe  mov     eax, ebx
0x180152ec0  lock xadd [rsi+0Ch], eax
0x180152ec5  add     eax, ebx
0x180152ec7  jnz     short loc_180152ED9
0x180152ec9  mov     rax, [rsi]
0x180152ecc  mov     rcx, rsi
0x180152ecf  mov     rax, [rax+8]
0x180152ed3  call    cs:__guard_dispatch_icall_fptr
0x180152ed9  mov     rcx, [rsp+198h+var_48]
0x180152ee1  mov     rcx, [rcx+58h]
0x180152ee5  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x180152eea  mov     rcx, [rsp+198h+var_48]
0x180152ef2  mov     rcx, [rcx+78h]
0x180152ef6  add     rcx, r12
0x180152ef9  mov     [rax+88h], rcx
0x180152f00  cmp     byte ptr [r14+0BC0h], 0
0x180152f08  jz      short loc_180152F41
0x180152f0a  mov     rdx, [rsp+198h+var_48]
0x180152f12  add     rdx, 68h ; 'h'; struct std::exception_ptr *
0x180152f16  xor     r8d, r8d; bool
0x180152f19  mov     rcx, rdi; this
0x180152f1c  call    ?SetNetworkException@WinsockDCTChannelContext@Dct@Basix@Microsoft@@IEAAXAEBVexception_ptr@std@@_N@Z; Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(std::exception_ptr const &,bool)
0x180152f21  mov     rcx, [rsp+198h+var_48]
0x180152f29  add     rcx, 68h ; 'h'
0x180152f2d  call    ??B?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(void)
0x180152f32  test    al, al
0x180152f34  jnz     loc_180153412
0x180152f3a  jmp     short loc_180152F41
0x180152f3c  mov     rdi, [rsp+198h+var_128]
0x180152f41  mov     rax, [rsp+198h+var_120]
0x180152f46  mov     rdx, [rax]
0x180152f49  mov     rax, [rdx+0B8h]
0x180152f50  lea     rdx, [rsp+198h+var_48]
0x180152f58  mov     rcx, rdi
0x180152f5b  call    cs:__guard_dispatch_icall_fptr
0x180152f61  jmp     loc_180153368
0x180152f66  jmp     short loc_180152F3C
0x180152f68  jmp     short loc_180152F3C
0x180152f6a  cmp     byte ptr [r14+0BC0h], 0
0x180152f72  jz      loc_1801530CC
0x180152f78  lea     rdx, [rcx+68h]; struct std::exception_ptr *
0x180152f7c  mov     r8b, 1; bool
0x180152f7f  mov     rcx, rdi; this
0x180152f82  call    ?SetNetworkException@WinsockDCTChannelContext@Dct@Basix@Microsoft@@IEAAXAEBVexception_ptr@std@@_N@Z; Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(std::exception_ptr const &,bool)
0x180152f87  mov     rcx, [rsp+198h+var_48]
0x180152f8f  add     rcx, 68h ; 'h'
0x180152f93  call    ??B?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(void)
0x180152f98  test    al, al
0x180152f9a  jnz     loc_180153439
0x180152fa0  jmp     short loc_180152FB3
0x180152fa2  mov     rcx, [rsp+198h+var_48]
0x180152faa  jmp     loc_180153370
0x180152faf  jmp     short loc_180152FA2
0x180152fb1  jmp     short loc_180152FA2
0x180152fb3  mov     rax, [rsp+198h+var_48]
0x180152fbb  cmp     qword ptr [rax+78h], 0
0x180152fc0  jnz     loc_180153347
0x180152fc6  xorps   xmm0, xmm0
0x180152fc9  movups  [rsp+198h+var_40], xmm0
0x180152fd1  lea     rcx, [rsp+198h+var_40]
0x180152fd9  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180152fde  nop
0x180152fdf  mov     rax, qword ptr [rsp+198h+var_40]
0x180152fe7  test    rax, rax
0x180152fea  jz      loc_180153076
0x180152ff0  cmp     byte ptr [rax+80h], 0
0x180152ff7  jz      short loc_180153076
0x180152ff9  lea     rbx, [r14-3D8h]
0x180153000  cmp     qword ptr [rbx+18h], 0Fh
0x180153005  jbe     short loc_18015300A
0x180153007  mov     rbx, [rbx]
0x18015300a  add     r14, 0FFFFFFFFFFFFFCA8h
0x180153011  cmp     qword ptr [r14+18h], 0Fh
0x180153016  jbe     short loc_18015301B
0x180153018  mov     r14, [r14]
0x18015301b  xorps   xmm0, xmm0
0x18015301e  movups  [rsp+198h+var_148], xmm0
0x180153023  xorps   xmm1, xmm1
0x180153026  movdqu  [rsp+198h+var_138], xmm1
0x18015302c  mov     r8d, 49h ; 'I'
0x180153032  lea     rdx, aChannelSPSRece_0; "Channel %s(%p@%s): Received normal shut"...
0x180153039  lea     rcx, [rsp+198h+var_148]
0x18015303e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180153043  nop
0x180153044  mov     [rsp+198h+var_170], rbx
0x180153049  mov     [rsp+198h+var_178], rdi
0x18015304e  mov     r9, r14
0x180153051  lea     r8, [rsp+198h+var_148]
0x180153056  lea     rdx, aNanoDct; "NANO_DCT"
0x18015305d  lea     rcx, [rsp+198h+var_40]
0x180153065  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEBDPEAVWinsockDCTChannelContext@Dct@23@PEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1PEAVWinsockDCTChannelContext@Dct@23@1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,Microsoft::Basix::Dct::WinsockDCTChannelContext *,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,char const *,Microsoft::Basix::Dct::WinsockDCTChannelContext *,char const *)
0x18015306a  nop
0x18015306b  lea     rcx, [rsp+198h+var_148]
0x180153070  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180153075  nop
0x180153076  mov     rdi, qword ptr [rsp+198h+var_40+8]
0x18015307e  test    rdi, rdi
0x180153081  jz      loc_180152FA2
0x180153087  or      ebx, 0FFFFFFFFh
0x18015308a  mov     eax, ebx
0x18015308c  lock xadd [rdi+8], eax
0x180153091  add     eax, ebx
0x180153093  jnz     loc_180152FA2
0x180153099  mov     rax, [rdi]
0x18015309c  mov     rcx, rdi
0x18015309f  mov     rax, [rax]
0x1801530a2  call    cs:__guard_dispatch_icall_fptr
0x1801530a8  mov     eax, ebx
0x1801530aa  lock xadd [rdi+0Ch], eax
0x1801530af  add     eax, ebx
0x1801530b1  jnz     loc_180152FA2
0x1801530b7  mov     rax, [rdi]
0x1801530ba  mov     rcx, rdi
0x1801530bd  mov     rax, [rax+8]
0x1801530c1  call    cs:__guard_dispatch_icall_fptr
0x1801530c7  jmp     loc_180152FA2
0x1801530cc  add     rcx, 68h ; 'h'
0x1801530d0  call    ??B?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(void)
0x1801530d5  test    al, al
0x1801530d7  jz      loc_18015321C
0x1801530dd  xorps   xmm0, xmm0
0x1801530e0  movups  [rsp+198h+var_40], xmm0
0x1801530e8  lea     rcx, [rsp+198h+var_40]
0x1801530f0  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x1801530f5  nop
0x1801530f6  mov     rax, qword ptr [rsp+198h+var_40]
0x1801530fe  test    rax, rax
0x180153101  jz      loc_1801531B1
0x180153107  cmp     byte ptr [rax+80h], 0
0x18015310e  jz      loc_1801531B1
0x180153114  lea     rbx, [r14-3D8h]
0x18015311b  cmp     qword ptr [rbx+18h], 0Fh
0x180153120  jbe     short loc_180153125
0x180153122  mov     rbx, [rbx]
0x180153125  add     r14, 0FFFFFFFFFFFFFCA8h
0x18015312c  cmp     qword ptr [r14+18h], 0Fh
0x180153131  jbe     short loc_180153136
0x180153133  mov     r14, [r14]
0x180153136  xorps   xmm0, xmm0
0x180153139  movups  [rsp+198h+var_148], xmm0
0x18015313e  xorps   xmm1, xmm1
0x180153141  movdqu  [rsp+198h+var_138], xmm1
0x180153147  mov     r8d, 4Ah ; 'J'
0x18015314d  lea     rdx, aChannelSPSRead; "Channel %s(%p@%s): Read IO failed. Term"...
0x180153154  lea     rcx, [rsp+198h+var_148]
0x180153159  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18015315e  nop
0x18015315f  lea     rax, aMicrosoftBasix_29; "Microsoft::Basix::Dct::WinsockDCTChanne"...
0x180153166  mov     [rsp+198h+var_158], rax
0x18015316b  mov     dword ptr [rsp+198h+var_160], 1CCh
0x180153173  lea     rax, aCW1SSrcLibbasi_63; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18015317a  mov     [rsp+198h+var_168], rax
0x18015317f  mov     [rsp+198h+var_170], rbx
0x180153184  mov     [rsp+198h+var_178], rdi
0x180153189  mov     r9, r14
0x18015318c  lea     r8, [rsp+198h+var_148]
0x180153191  lea     rdx, aNanoDct; "NANO_DCT"
0x180153198  lea     rcx, [rsp+198h+var_40]
0x1801531a0  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEBDPEAVWinsockDCTChannelContext@Dct@23@PEBDPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1PEAVWinsockDCTChannelContext@Dct@23@11H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,Microsoft::Basix::Dct::WinsockDCTChannelContext *,char const *,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,char const *,Microsoft::Basix::Dct::WinsockDCTChannelContext *,char const *,char const *,int,char const *)
0x1801531a5  nop
0x1801531a6  lea     rcx, [rsp+198h+var_148]
0x1801531ab  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801531b0  nop
0x1801531b1  mov     rsi, qword ptr [rsp+198h+var_40+8]
0x1801531b9  test    rsi, rsi
0x1801531bc  jz      short loc_1801531F6
0x1801531be  or      ebx, 0FFFFFFFFh
0x1801531c1  mov     eax, ebx
0x1801531c3  lock xadd [rsi+8], eax
0x1801531c8  add     eax, ebx
0x1801531ca  jnz     short loc_1801531F6
0x1801531cc  mov     rax, [rsi]
0x1801531cf  mov     rcx, rsi
0x1801531d2  mov     rax, [rax]
0x1801531d5  call    cs:__guard_dispatch_icall_fptr
0x1801531db  mov     eax, ebx
0x1801531dd  lock xadd [rsi+0Ch], eax
0x1801531e2  add     eax, ebx
0x1801531e4  jnz     short loc_1801531F6
0x1801531e6  mov     rax, [rsi]
0x1801531e9  mov     rcx, rsi
0x1801531ec  mov     rax, [rax+8]
0x1801531f0  call    cs:__guard_dispatch_icall_fptr
0x1801531f6  mov     rdx, [rsp+198h+var_48]
0x1801531fe  add     rdx, 68h ; 'h'
0x180153202  mov     rax, [rsp+198h+var_120]
0x180153207  mov     rcx, [rax]
0x18015320a  mov     rax, [rcx+78h]
0x18015320e  mov     rcx, rdi
  ... truncated ...
```
