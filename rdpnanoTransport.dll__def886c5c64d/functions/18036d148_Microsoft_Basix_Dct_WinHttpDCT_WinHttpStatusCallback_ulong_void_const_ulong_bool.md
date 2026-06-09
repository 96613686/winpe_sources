# Microsoft::Basix::Dct::WinHttpDCT::WinHttpStatusCallback(ulong,void * const,ulong,bool &)

- ea: `0x18036d148`
- end: `0x18036de05`
- name: `?WinHttpStatusCallback@WinHttpDCT@Dct@Basix@Microsoft@@IEAAXKQEAXKAEA_N@Z`
- size: `3261`
- prototype: `void __fastcall(HINTERNET **this, unsigned int, unsigned __int16 *, unsigned int, bool *)`
- caller_count: `1`
- callee_count: `29`
- tags: `broker_com_uri`

## callers

- `0x18036de10`

## callees

- `0x18000d9c0`
- `0x1800111fc`
- `0x180015bb8`
- `0x180018d1c`
- `0x180018ea4`
- `0x18001902c`
- `0x1800191b4`
- `0x18001ab4c`
- `0x18001bbdc`
- `0x1800454f0`
- `0x18004569c`
- `0x1800d3af0`
- `0x1800de3ec`
- `0x18011963c`
- `0x1802e9e58`
- `0x1802ea490`
- `0x180311e54`
- `0x18032f050`
- `0x18032f0b0`
- `0x180366b58`
- `0x180367194`
- `0x180369978`
- `0x18036aaf8`
- `0x18036ad88`
- `0x18036b240`
- `0x18036b720`
- `0x18036bb10`
- `0x18036d148`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18036d872`
- `KERNEL32!GetLastError` at `0x18036d872`
- `WINHTTP!WinHttpReceiveResponse` at `0x18036d7f0`
- `WINHTTP!WinHttpReceiveResponse` at `0x18036d7f0`

## string_xrefs

- `0x18036d770`: `Received http send request complete.`
- `0x18036d9b4`: `Write completed: %d`
- `0x18036db47`: `WINHTTP_CALLBACK_STATUS_WRITE_COMPLETE nothing was written\n    %s(%d): %s()`
- `0x18036dc58`: `Invalid StatusInformation in WINHTTP_CALLBACK_STATUS_READ_COMPLETE`
- `0x18036dd2d`: `Read complete (WinHttp) error - invalid StatusInformation\n    %s(%d): %s()`

## pseudocode

```c
// Hidden C++ exception states: #wind=111
void __fastcall Microsoft::Basix::Dct::WinHttpDCT::WinHttpStatusCallback(
        HINTERNET **this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        bool *a5)
{
  unsigned int v7; // edx
  unsigned int v8; // edx
  unsigned int v9; // edx
  unsigned int v10; // edx
  void (__fastcall *v11)(HINTERNET **, __int64); // rdi
  __int64 v12; // rbx
  Microsoft::Basix *v13; // rcx
  const struct std::error_category *v14; // rax
  unsigned int v15; // ecx
  __int64 v16; // rax
  __int64 v17; // rax
  const char *v18; // r9
  unsigned int v19; // ebx
  volatile signed __int32 *v20; // rdi
  volatile signed __int32 *v21; // rdi
  volatile signed __int32 *v22; // rdi
  volatile signed __int32 *v23; // rdi
  volatile signed __int32 *v24; // rdi
  volatile signed __int32 *v25; // rdi
  void (__fastcall *v26)(HINTERNET **, __int64); // rsi
  __int64 v27; // rdi
  Microsoft::Basix *v28; // rcx
  const struct std::error_category *v29; // rbx
  signed int LastError; // eax
  unsigned int v31; // ecx
  __int64 v32; // rax
  __int64 v33; // rax
  unsigned int v34; // r15d
  volatile signed __int32 *v35; // rdi
  __int64 v36; // rcx
  void (__fastcall ***v37)(_QWORD, __int64); // r8
  volatile signed __int32 *v38; // rsi
  int v39; // r9d
  volatile signed __int32 *v40; // rsi
  void (__fastcall *v41)(HINTERNET **, __int64); // rdi
  __int64 v42; // rbx
  Microsoft::Basix *v43; // rcx
  const struct std::error_category *v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  int v47; // r9d
  volatile signed __int32 *v48; // rdi
  enum _WINHTTP_WEB_SOCKET_BUFFER_TYPE v49; // r8d
  const char *v50; // [rsp+20h] [rbp-E0h]
  int v51; // [rsp+20h] [rbp-E0h]
  const char *v52; // [rsp+20h] [rbp-E0h]
  const char *v53; // [rsp+28h] [rbp-D8h]
  __int128 v54; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v55; // [rsp+50h] [rbp-B0h]
  __int128 v56; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v57; // [rsp+70h] [rbp-90h] BYREF
  __int128 v58; // [rsp+80h] [rbp-80h]
  _BYTE v59[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v60[144]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v61; // [rsp+140h] [rbp+40h] BYREF

  *a5 = 0;
  if ( a2 > 0x20000 )
  {
    switch ( a2 )
    {
      case 0x80000u:
        if ( this[146] )
        {
          if ( !a3 || a4 < 8 )
          {
            v41 = (void (__fastcall *)(HINTERNET **, __int64))(*this)[15];
            v42 = ((__int64 (__fastcall *)(HINTERNET **, _BYTE *))(*this)[13])(this, v59);
            v57 = 0;
            v58 = 0;
            std::string::_Construct<1,char const *>(
              &v57,
              "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp",
              50);
            v54 = 0;
            v55 = 0;
            std::string::_Construct<1,char const *>(
              &v54,
              "Invalid StatusInformation in WINHTTP_CALLBACK_STATUS_READ_COMPLETE",
              66);
            v44 = Microsoft::Basix::WindowsCategory(v43);
            LODWORD(v56) = -2147418113;
            *((_QWORD *)&v56 + 1) = v44;
            v45 = Microsoft::Basix::SystemException::SystemException(
                    (unsigned int)v60,
                    (unsigned int)&v56,
                    (unsigned int)&v54,
                    (unsigned int)&v57,
                    828,
                    v42);
            v46 = std::make_exception_ptr<Microsoft::Basix::SystemException>(&v61, v45);
            v41(this, v46);
            __ExceptionPtrDestroy(&v61);
            std::string::_Tidy_deallocate(&v54);
            std::string::_Tidy_deallocate(&v57);
            std::string::_Tidy_deallocate(v59);
            v61 = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v61);
            if ( (_QWORD)v61 && *(_BYTE *)(v61 + 128) )
            {
              v54 = 0;
              v55 = 0;
              std::string::_Construct<1,char const *>(
                &v54,
                "Read complete (WinHttp) error - invalid StatusInformation\n    %s(%d): %s()",
                (const char *)0x4A,
                v47,
                v52);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
                (unsigned int)&v61,
                (unsigned int)"NANO_DCT",
                (unsigned int)&v54,
                (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp",
                61,
                (__int64)"Microsoft::Basix::Dct::WinHttpDCT::WinHttpStatusCallback");
              std::string::_Tidy_deallocate(&v54);
            }
            v48 = (volatile signed __int32 *)*((_QWORD *)&v61 + 1);
            if ( *((_QWORD *)&v61 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v61 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
                if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
              }
            }
            Microsoft::Basix::Dct::WinHttpDCT::FireOnClosedInternal((Microsoft::Basix::Dct::WinHttpDCT *)this, 0);
          }
          v49 = *((_DWORD *)a3 + 1);
          if ( v49 == WINHTTP_WEB_SOCKET_CLOSE_BUFFER_TYPE )
            Microsoft::Basix::Dct::WinHttpDCT::OnWebSocketCloseFrameReceived((Microsoft::Basix::Dct::WinHttpDCT *)this);
          else
            Microsoft::Basix::Dct::WinHttpDCT::OnReadCompleted(
              (Microsoft::Basix::Dct::WinHttpDCT *)this,
              *(_DWORD *)a3,
              v49);
        }
        break;
      case 0x100000u:
        if ( a3 && a4 >= 8 )
          v34 = *(_DWORD *)a3;
        else
          v34 = 0;
        v61 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v61);
        if ( (_QWORD)v61 && *(_BYTE *)(v61 + 128) )
        {
          v54 = 0;
          v55 = 0;
          std::string::_Construct<1,char const *>(&v54, "Write completed: %d", 19);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned long>(
            &v61,
            "NANO_DCT",
            &v54,
            v34);
          std::string::_Tidy_deallocate(&v54);
        }
        v35 = (volatile signed __int32 *)*((_QWORD *)&v61 + 1);
        if ( *((_QWORD *)&v61 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v61 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
            if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
          }
        }
        v56 = 0;
        Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::Dct::WinHttpDCT>(
          (char *)this + *((int *)this[1] + 1) + 8,
          &v56);
        v23 = (volatile signed __int32 *)*((_QWORD *)&v56 + 1);
        if ( *((_QWORD *)&v56 + 1) )
          _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v56 + 1) + 8LL));
        *(_QWORD *)&v57 = v56;
        *((_QWORD *)&v57 + 1) = v23;
        LODWORD(v58) = v34;
        std::async__lambda_acb9d1c77feaae365d26d25cc1ef8aa6___(&v61, 1, &v57);
        v36 = v61;
        if ( (_QWORD)v61 && !_InterlockedDecrement((volatile signed __int32 *)(v61 + 8)) )
        {
          v37 = *(void (__fastcall ****)(_QWORD, __int64))(v36 + 200);
          if ( v37 )
            (**v37)(*(_QWORD *)(v36 + 200), v36);
          else
            (**(void (__fastcall ***)(__int64, __int64))v36)(v36, 1);
        }
        v38 = (volatile signed __int32 *)*((_QWORD *)&v57 + 1);
        if ( *((_QWORD *)&v57 + 1) )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v57 + 1) + 8LL)) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
            if ( !_InterlockedDecrement(v38 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
          }
        }
        if ( !v34 )
        {
          v61 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v61);
          if ( (_QWORD)v61 && *(_BYTE *)(v61 + 128) )
          {
            v54 = 0;
            v55 = 0;
            std::string::_Construct<1,char const *>(
              &v54,
              "WINHTTP_CALLBACK_STATUS_WRITE_COMPLETE nothing was written\n    %s(%d): %s()",
              (const char *)0x4B,
              v39,
              v50);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
              (unsigned int)&v61,
              (unsigned int)"NANO_DCT",
              (unsigned int)&v54,
              (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp",
              46,
              (__int64)"Microsoft::Basix::Dct::WinHttpDCT::WinHttpStatusCallback");
            std::string::_Tidy_deallocate(&v54);
          }
          v40 = (volatile signed __int32 *)*((_QWORD *)&v61 + 1);
          if ( *((_QWORD *)&v61 + 1) )
          {
            if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v61 + 1) + 8LL)) )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
              if ( !_InterlockedDecrement(v40 + 3) )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
            }
          }
        }
        if ( v23 )
        {
LABEL_41:
          if ( !_InterlockedDecrement(v23 + 2) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
            if ( !_InterlockedDecrement(v23 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
          }
          return;
        }
        break;
      case 0x200000u:
        if ( this[146] && a3 && a4 >= 0x18 )
        {
          Microsoft::Basix::Dct::WinHttpDCT::OnWebSocketError(
            (Microsoft::Basix::Dct::WinHttpDCT *)this,
            (const struct _WINHTTP_ASYNC_RESULT *)a3,
            *((enum _WINHTTP_WEB_SOCKET_OPERATION *)a3 + 4));
        }
        else if ( this[144] && a3 && a4 >= 0x10 )
        {
          Microsoft::Basix::Dct::WinHttpDCT::OnHttpRequestError(
            (Microsoft::Basix::Dct::WinHttpDCT *)this,
            (const struct _WINHTTP_ASYNC_RESULT *)a3);
        }
        break;
      case 0x400000u:
        v61 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v61);
        if ( (_QWORD)v61 && *(_BYTE *)(v61 + 128) )
        {
          v54 = 0;
          v55 = 0;
          std::string::_Construct<1,char const *>(&v54, "Received http send request complete.", 36);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,>(
            &v61,
            "NANO_DCT",
            &v54);
          std::string::_Tidy_deallocate(&v54);
        }
        v25 = (volatile signed __int32 *)*((_QWORD *)&v61 + 1);
        if ( *((_QWORD *)&v61 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v61 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
            if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
          }
        }
        if ( !WinHttpReceiveResponse(*this[144], 0) )
        {
          v26 = (void (__fastcall *)(HINTERNET **, __int64))(*this)[15];
          v27 = ((__int64 (__fastcall *)(HINTERNET **, _BYTE *))(*this)[13])(this, v59);
          v57 = 0;
          v58 = 0;
          std::string::_Construct<1,char const *>(&v57, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp", 50);
          v54 = 0;
          v55 = 0;
          std::string::_Construct<1,char const *>(&v54, "WinHttpReceiveResponse failed", 29);
          v29 = Microsoft::Basix::WindowsCategory(v28);
          LastError = GetLastError();
          v31 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v31 = LastError;
          LODWORD(v56) = v31;
          *((_QWORD *)&v56 + 1) = v29;
          v32 = Microsoft::Basix::SystemException::SystemException(
                  (unsigned int)v60,
                  (unsigned int)&v56,
                  (unsigned int)&v54,
                  (unsigned int)&v57,
                  777,
                  v27);
          v33 = std::make_exception_ptr<Microsoft::Basix::SystemException>(&v61, v32);
          v26(this, v33);
          __ExceptionPtrDestroy(&v61);
          std::string::_Tidy_deallocate(&v54);
          std::string::_Tidy_deallocate(&v57);
          std::string::_Tidy_deallocate(v59);
LABEL_69:
          Microsoft::Basix::Dct::WinHttpDCT::FireOnClosedInternal((Microsoft::Basix::Dct::WinHttpDCT *)this, 0);
          return;
        }
        break;
      case 0x2000000u:
        v56 = 0;
        std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(this + 146, &v56);
        v23 = (volatile signed __int32 *)*((_QWORD *)&v56 + 1);
        goto LABEL_40;
      default:
        return;
    }
    return;
  }
  if ( a2 == 0x20000 )
  {
    v61 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v61);
    if ( (_QWORD)v61 && *(_BYTE *)(v61 + 128) )
    {
      v54 = 0;
      v55 = 0;
      std::string::_Construct<1,char const *>(&v54, "Http response (for websocket) received.", 39);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
        &v61,
        "NANO_DCT",
        &v54);
      std::string::_Tidy_deallocate(&v54);
    }
    v24 = (volatile signed __int32 *)*((_QWORD *)&v61 + 1);
    if ( *((_QWORD *)&v61 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v61 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
        if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
    Microsoft::Basix::Dct::WinHttpDCT::OnHttpResponseReceived((Microsoft::Basix::Dct::WinHttpDCT *)this);
    return;
  }
  v7 = a2 - 1;
  if ( !v7 )
  {
    v61 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v61);
    if ( (_QWORD)v61 && *(_BYTE *)(v61 + 128) )
    {
      v54 = 0;
      v55 = 0;
      std::string::_Construct<1,char const *>(&v54, "WINHTTP_CALLBACK_STATUS_RESOLVING_NAME", 38);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,>(
        &v61,
        "NANO_DCT",
        &v54);
      std::string::_Tidy_deallocate(&v54);
    }
    goto LABEL_39;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    v61 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v61);
    if ( (_QWORD)v61 && *(_BYTE *)(v61 + 128) )
    {
      v54 = 0;
      v55 = 0;
      std::string::_Construct<1,char const *>(&v54, "WINHTTP_CALLBACK_STATUS_NAME_RESOLVED", 37);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,>(
        &v61,
        "NANO_DCT",
        &v54);
      std::string::_Tidy_deallocate(&v54);
    }
LABEL_39:
    v23 = (volatile signed __int32 *)*((_QWORD *)&v61 + 1);
LABEL_40:
    if ( !v23 )
      return;
    goto LABEL_41;
  }
  v9 = v8 - 2046;
  if ( v9 )
  {
    v10 = v9 - 14336;
    if ( v10 )
    {
      if ( v10 != 49152 )
        return;
      v11 = (void (__fastcall *)(HINTERNET **, __int64))(*this)[15];
      v12 = ((__int64 (__fastcall *)(HINTERNET **, _BYTE *))(*this)[13])(this, v59);
      v54 = 0;
      v55 = 0;
      std::string::_Construct<1,char const *>(&v54, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp", 50);
      v57 = 0;
      v58 = 0;
      std::string::_Construct<1,char const *>(&v57, "SSL error reported by WINHTTP_CALLBACK_STATUS_SECURE_FAILURE", 60);
      v14 = Microsoft::Basix::WindowsCategory(v13);
      v15 = *a3 | 0x80070000;
      if ( *(int *)a3 <= 0 )
        v15 = *(_DWORD *)a3;
      LODWORD(v56) = v15;
      *((_QWORD *)&v56 + 1) = v14;
      v16 = Microsoft::Basix::SystemException::SystemException(
              (unsigned int)v60,
              (unsigned int)&v56,
              (unsigned int)&v57,
              (unsigned int)&v54,
              866,
              v12);
      v17 = std::make_exception_ptr<Microsoft::Basix::SystemException>(&v61, v16);
      v11(this, v17);
      __ExceptionPtrDestroy(&v61);
      std::string::_Tidy_deallocate(&v57);
      std::string::_Tidy_deallocate(&v54);
      std::string::_Tidy_deallocate(v59);
      v61 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v61);
      if ( (_QWORD)v61 && *(_BYTE *)(v61 + 128) )
      {
        v19 = *a3 | 0x80070000;
        if ( *(int *)a3 <= 0 )
          v19 = *(_DWORD *)a3;
        v54 = 0;
        v55 = 0;
        std::string::_Construct<1,char const *>(&v54, "SSL (WinHttp) error: 0x%x\n    %s(%d): %s()", 42, v18, v51, v53);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,long,char const *,int,char const *>(
          (unsigned int)&v61,
          (unsigned int)"NANO_DCT",
          (unsigned int)&v54,
          v19,
          (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp",
          99,
          (__int64)"Microsoft::Basix::Dct::WinHttpDCT::WinHttpStatusCallback");
        std::string::_Tidy_deallocate(&v54);
      }
      v20 = (volatile signed __int32 *)*((_QWORD *)&v61 + 1);
      if ( *((_QWORD *)&v61 + 1)
        && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v61 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
      goto LABEL_69;
    }
    v61 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v61);
    if ( (_QWORD)v61 && *(_BYTE *)(v61 + 128) )
    {
      v54 = 0;
      v55 = 0;
      std::string::_Construct<1,char const *>(
        &v54,
        "WINHTTP_CALLBACK_STATUS_REDIRECT received. Undupported, ignored.",
        64);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(
        &v61,
        "NANO_DCT",
        &v54);
      std::string::_Tidy_deallocate(&v54);
    }
    goto LABEL_39;
  }
  Microsoft::Basix::Dct::WinHttpDCT::FireOnClosedInternal((Microsoft::Basix::Dct::WinHttpDCT *)this, 0);
  v56 = 0;
  std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(this + 142, &v56);
  v21 = (volatile signed __int32 *)*((_QWORD *)&v56 + 1);
  if ( *((_QWORD *)&v56 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v56 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  v56 = 0;
  std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(this + 140, &v56);
  v22 = (volatile signed __int32 *)*((_QWORD *)&v56 + 1);
  if ( *((_QWORD *)&v56 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v56 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( !_InterlockedDecrement(v22 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
  *a5 = 1;
}

```

## disassembly

```asm
0x18036d148  mov     [rsp-8+arg_8], rbx
0x18036d14d  mov     [rsp-8+arg_18], rsi
0x18036d152  push    rbp
0x18036d153  push    rdi
0x18036d154  push    r13
0x18036d156  push    r14
0x18036d158  push    r15
0x18036d15a  lea     rbp, [rsp-60h]
0x18036d15f  mov     eax, 160h
0x18036d164  call    _alloca_probe
0x18036d169  sub     rsp, rax
0x18036d16c  mov     rax, cs:__security_cookie
0x18036d173  xor     rax, rsp
0x18036d176  mov     [rbp+80h+var_30], rax
0x18036d17a  mov     rsi, r8
0x18036d17d  mov     r14, rcx
0x18036d180  mov     r15, [rbp+80h+arg_20]
0x18036d187  xor     r13d, r13d
0x18036d18a  mov     [r15], r13b
0x18036d18d  mov     eax, 20000h
0x18036d192  cmp     edx, eax
0x18036d194  ja      loc_18036D6DA
0x18036d19a  jz      loc_18036D61F
0x18036d1a0  sub     edx, 1
0x18036d1a3  jz      loc_18036D560
0x18036d1a9  sub     edx, 1
0x18036d1ac  jz      loc_18036D4F1
0x18036d1b2  sub     edx, 7FEh
0x18036d1b8  jz      loc_18036D42C
0x18036d1be  sub     edx, 3800h
0x18036d1c4  jz      loc_18036D3BA
0x18036d1ca  cmp     edx, 0C000h
0x18036d1d0  jnz     loc_18036DDDD
0x18036d1d6  mov     rax, [rcx]
0x18036d1d9  mov     rdi, [rax+78h]
0x18036d1dd  lea     rdx, [rbp+80h+var_F0]
0x18036d1e1  mov     rax, [rax+68h]
0x18036d1e5  call    cs:__guard_dispatch_icall_fptr
0x18036d1eb  mov     rbx, rax
0x18036d1ee  xorps   xmm0, xmm0
0x18036d1f1  movups  [rsp+180h+var_140], xmm0
0x18036d1f6  xorps   xmm1, xmm1
0x18036d1f9  movdqu  [rsp+180h+var_130], xmm1
0x18036d1ff  lea     r8d, [r13+32h]
0x18036d203  lea     r15, aCW1SSrcLibbasi_91; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18036d20a  mov     rdx, r15
0x18036d20d  lea     rcx, [rsp+180h+var_140]
0x18036d212  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18036d217  nop
0x18036d218  xorps   xmm0, xmm0
0x18036d21b  movups  [rsp+180h+var_110], xmm0
0x18036d220  xorps   xmm1, xmm1
0x18036d223  movdqu  [rbp+80h+var_100], xmm1
0x18036d228  lea     r8d, [r13+3Ch]
0x18036d22c  lea     rdx, aSslErrorReport; "SSL error reported by WINHTTP_CALLBACK_"...
0x18036d233  lea     rcx, [rsp+180h+var_110]
0x18036d238  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18036d23d  nop
0x18036d23e  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x18036d243  movzx   ecx, word ptr [rsi]
0x18036d246  or      ecx, 80070000h
0x18036d24c  cmp     [rsi], r13d
0x18036d24f  cmovle  ecx, [rsi]
0x18036d252  mov     dword ptr [rsp+180h+var_120], ecx
0x18036d256  mov     qword ptr [rsp+180h+var_120+8], rax
0x18036d25b  movaps  xmm0, [rsp+180h+var_120]
0x18036d260  movdqa  [rsp+180h+var_120], xmm0
0x18036d266  mov     [rsp+180h+var_158], rbx
0x18036d26b  mov     [rsp+180h+var_160], 362h
0x18036d274  lea     r9, [rsp+180h+var_140]
0x18036d279  lea     r8, [rsp+180h+var_110]
0x18036d27e  lea     rdx, [rsp+180h+var_120]
0x18036d283  lea     rcx, [rbp+80h+var_D0]
0x18036d287  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x18036d28c  mov     rdx, rax
0x18036d28f  lea     rcx, [rbp+80h+var_40]
0x18036d293  call    ??$make_exception_ptr@VSystemException@Basix@Microsoft@@@std@@YA?AVexception_ptr@0@VSystemException@Basix@Microsoft@@@Z; std::make_exception_ptr<Microsoft::Basix::SystemException>(Microsoft::Basix::SystemException)
0x18036d298  nop
0x18036d299  mov     rdx, rax
0x18036d29c  mov     rcx, r14
0x18036d29f  mov     rax, rdi
0x18036d2a2  call    cs:__guard_dispatch_icall_fptr
0x18036d2a8  nop
0x18036d2a9  lea     rcx, [rbp+80h+var_40]; void *
0x18036d2ad  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18036d2b2  nop
0x18036d2b3  lea     rcx, [rsp+180h+var_110]
0x18036d2b8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036d2bd  nop
0x18036d2be  lea     rcx, [rsp+180h+var_140]
0x18036d2c3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036d2c8  nop
0x18036d2c9  lea     rcx, [rbp+80h+var_F0]
0x18036d2cd  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036d2d2  xorps   xmm0, xmm0
0x18036d2d5  movups  [rbp+80h+var_40], xmm0
0x18036d2d9  lea     rcx, [rbp+80h+var_40]
0x18036d2dd  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x18036d2e2  nop
0x18036d2e3  mov     rax, qword ptr [rbp+80h+var_40]
0x18036d2e7  test    rax, rax
0x18036d2ea  jz      short loc_18036D368
0x18036d2ec  cmp     [rax+80h], r13b
0x18036d2f3  jz      short loc_18036D368
0x18036d2f5  movzx   ebx, word ptr [rsi]
0x18036d2f8  or      ebx, 80070000h
0x18036d2fe  cmp     [rsi], r13d
0x18036d301  cmovle  ebx, [rsi]
0x18036d304  xorps   xmm0, xmm0
0x18036d307  movups  [rsp+180h+var_140], xmm0
0x18036d30c  xorps   xmm1, xmm1
0x18036d30f  movdqu  [rsp+180h+var_130], xmm1
0x18036d315  lea     r8d, [r13+2Ah]
0x18036d319  lea     rdx, aSslWinhttpErro; "SSL (WinHttp) error: 0x%x\n    %s(%d): "...
0x18036d320  lea     rcx, [rsp+180h+var_140]
0x18036d325  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18036d32a  nop
0x18036d32b  lea     rax, aMicrosoftBasix_365; "Microsoft::Basix::Dct::WinHttpDCT::WinH"...
0x18036d332  mov     [rsp+180h+var_150], rax
0x18036d337  mov     dword ptr [rsp+180h+var_158], 363h
0x18036d33f  mov     [rsp+180h+var_160], r15
0x18036d344  mov     r9d, ebx
0x18036d347  lea     r8, [rsp+180h+var_140]
0x18036d34c  lea     rdx, aNanoDct; "NANO_DCT"
0x18036d353  lea     rcx, [rbp+80h+var_40]
0x18036d357  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@JPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@J1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,long,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,long,char const *,int,char const *)
0x18036d35c  nop
0x18036d35d  lea     rcx, [rsp+180h+var_140]
0x18036d362  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036d367  nop
0x18036d368  mov     rdi, qword ptr [rbp+80h+var_40+8]
0x18036d36c  test    rdi, rdi
0x18036d36f  jz      loc_18036D906
0x18036d375  or      ebx, 0FFFFFFFFh
0x18036d378  mov     eax, ebx
0x18036d37a  lock xadd [rdi+8], eax
0x18036d37f  add     eax, ebx
0x18036d381  jnz     loc_18036D906
0x18036d387  mov     rax, [rdi]
0x18036d38a  mov     rcx, rdi
0x18036d38d  mov     rax, [rax]
0x18036d390  call    cs:__guard_dispatch_icall_fptr
0x18036d396  mov     eax, ebx
0x18036d398  lock xadd [rdi+0Ch], eax
0x18036d39d  add     eax, ebx
0x18036d39f  jnz     loc_18036D906
0x18036d3a5  mov     rax, [rdi]
0x18036d3a8  mov     rcx, rdi
0x18036d3ab  mov     rax, [rax+8]
0x18036d3af  call    cs:__guard_dispatch_icall_fptr
0x18036d3b5  jmp     loc_18036D906
0x18036d3ba  xorps   xmm0, xmm0
0x18036d3bd  movups  [rbp+80h+var_40], xmm0
0x18036d3c1  lea     rcx, [rbp+80h+var_40]
0x18036d3c5  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x18036d3ca  nop
0x18036d3cb  mov     rax, qword ptr [rbp+80h+var_40]
0x18036d3cf  test    rax, rax
0x18036d3d2  jz      short loc_18036D427
0x18036d3d4  cmp     [rax+80h], r13b
0x18036d3db  jz      short loc_18036D427
0x18036d3dd  xorps   xmm0, xmm0
0x18036d3e0  movups  [rsp+180h+var_140], xmm0
0x18036d3e5  xorps   xmm1, xmm1
0x18036d3e8  movdqu  [rsp+180h+var_130], xmm1
0x18036d3ee  mov     r8d, 40h ; '@'
0x18036d3f4  lea     rdx, aWinhttpCallbac_1; "WINHTTP_CALLBACK_STATUS_REDIRECT receiv"...
0x18036d3fb  lea     rcx, [rsp+180h+var_140]
0x18036d400  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18036d405  nop
0x18036d406  lea     r8, [rsp+180h+var_140]
0x18036d40b  lea     rdx, aNanoDct; "NANO_DCT"
0x18036d412  lea     rcx, [rbp+80h+var_40]
0x18036d416  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &)
0x18036d41b  nop
0x18036d41c  lea     rcx, [rsp+180h+var_140]
0x18036d421  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036d426  nop
0x18036d427  jmp     loc_18036D5CD
0x18036d42c  xor     edx, edx; bool
0x18036d42e  call    ?FireOnClosedInternal@WinHttpDCT@Dct@Basix@Microsoft@@IEAAX_N@Z; Microsoft::Basix::Dct::WinHttpDCT::FireOnClosedInternal(bool)
0x18036d433  xorps   xmm0, xmm0
0x18036d436  movdqu  [rsp+180h+var_120], xmm0
0x18036d43c  lea     rcx, [r14+470h]
0x18036d443  lea     rdx, [rsp+180h+var_120]
0x18036d448  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x18036d44d  or      ebx, 0FFFFFFFFh
0x18036d450  mov     rdi, qword ptr [rsp+180h+var_120+8]
0x18036d455  test    rdi, rdi
0x18036d458  jz      short loc_18036D48F
0x18036d45a  mov     eax, ebx
0x18036d45c  lock xadd [rdi+8], eax
0x18036d461  add     eax, ebx
0x18036d463  jnz     short loc_18036D48F
0x18036d465  mov     rax, [rdi]
0x18036d468  mov     rcx, rdi
0x18036d46b  mov     rax, [rax]
0x18036d46e  call    cs:__guard_dispatch_icall_fptr
0x18036d474  mov     eax, ebx
0x18036d476  lock xadd [rdi+0Ch], eax
0x18036d47b  add     eax, ebx
0x18036d47d  jnz     short loc_18036D48F
0x18036d47f  mov     rax, [rdi]
0x18036d482  mov     rcx, rdi
0x18036d485  mov     rax, [rax+8]
0x18036d489  call    cs:__guard_dispatch_icall_fptr
0x18036d48f  xorps   xmm0, xmm0
0x18036d492  movdqu  [rsp+180h+var_120], xmm0
0x18036d498  lea     rcx, [r14+460h]
0x18036d49f  lea     rdx, [rsp+180h+var_120]
0x18036d4a4  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x18036d4a9  mov     rdi, qword ptr [rsp+180h+var_120+8]
0x18036d4ae  test    rdi, rdi
0x18036d4b1  jz      short loc_18036D4E8
0x18036d4b3  mov     eax, ebx
0x18036d4b5  lock xadd [rdi+8], eax
0x18036d4ba  add     eax, ebx
0x18036d4bc  jnz     short loc_18036D4E8
0x18036d4be  mov     rax, [rdi]
0x18036d4c1  mov     rcx, rdi
0x18036d4c4  mov     rax, [rax]
0x18036d4c7  call    cs:__guard_dispatch_icall_fptr
0x18036d4cd  mov     eax, ebx
0x18036d4cf  lock xadd [rdi+0Ch], eax
0x18036d4d4  add     eax, ebx
0x18036d4d6  jnz     short loc_18036D4E8
0x18036d4d8  mov     rax, [rdi]
0x18036d4db  mov     rcx, rdi
0x18036d4de  mov     rax, [rax+8]
0x18036d4e2  call    cs:__guard_dispatch_icall_fptr
0x18036d4e8  mov     byte ptr [r15], 1
0x18036d4ec  jmp     loc_18036DDDD
0x18036d4f1  xorps   xmm0, xmm0
0x18036d4f4  movups  [rbp+80h+var_40], xmm0
0x18036d4f8  lea     rcx, [rbp+80h+var_40]
0x18036d4fc  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18036d501  nop
0x18036d502  mov     rax, qword ptr [rbp+80h+var_40]
0x18036d506  test    rax, rax
0x18036d509  jz      short loc_18036D55E
0x18036d50b  cmp     [rax+80h], r13b
0x18036d512  jz      short loc_18036D55E
0x18036d514  xorps   xmm0, xmm0
0x18036d517  movups  [rsp+180h+var_140], xmm0
0x18036d51c  xorps   xmm1, xmm1
0x18036d51f  movdqu  [rsp+180h+var_130], xmm1
0x18036d525  mov     r8d, 25h ; '%'
0x18036d52b  lea     rdx, aWinhttpCallbac_2; "WINHTTP_CALLBACK_STATUS_NAME_RESOLVED"
0x18036d532  lea     rcx, [rsp+180h+var_140]
0x18036d537  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18036d53c  nop
0x18036d53d  lea     r8, [rsp+180h+var_140]
0x18036d542  lea     rdx, aNanoDct; "NANO_DCT"
0x18036d549  lea     rcx, [rbp+80h+var_40]
0x18036d54d  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &)
0x18036d552  nop
0x18036d553  lea     rcx, [rsp+180h+var_140]
0x18036d558  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036d55d  nop
0x18036d55e  jmp     short loc_18036D5CD
0x18036d560  xorps   xmm0, xmm0
0x18036d563  movups  [rbp+80h+var_40], xmm0
0x18036d567  lea     rcx, [rbp+80h+var_40]
0x18036d56b  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18036d570  nop
0x18036d571  mov     rax, qword ptr [rbp+80h+var_40]
0x18036d575  test    rax, rax
0x18036d578  jz      short loc_18036D5CD
0x18036d57a  cmp     [rax+80h], r13b
0x18036d581  jz      short loc_18036D5CD
0x18036d583  xorps   xmm0, xmm0
0x18036d586  movups  [rsp+180h+var_140], xmm0
0x18036d58b  xorps   xmm1, xmm1
0x18036d58e  movdqu  [rsp+180h+var_130], xmm1
0x18036d594  mov     r8d, 26h ; '&'
0x18036d59a  lea     rdx, aWinhttpCallbac; "WINHTTP_CALLBACK_STATUS_RESOLVING_NAME"
0x18036d5a1  lea     rcx, [rsp+180h+var_140]
0x18036d5a6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18036d5ab  nop
0x18036d5ac  lea     r8, [rsp+180h+var_140]
0x18036d5b1  lea     rdx, aNanoDct; "NANO_DCT"
0x18036d5b8  lea     rcx, [rbp+80h+var_40]
0x18036d5bc  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &)
0x18036d5c1  nop
0x18036d5c2  lea     rcx, [rsp+180h+var_140]
0x18036d5c7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18036d5cc  nop
0x18036d5cd  mov     rdi, qword ptr [rbp+80h+var_40+8]
0x18036d5d1  test    rdi, rdi
0x18036d5d4  jz      loc_18036DDDD
0x18036d5da  or      ebx, 0FFFFFFFFh
0x18036d5dd  mov     eax, ebx
0x18036d5df  lock xadd [rdi+8], eax
0x18036d5e4  add     eax, ebx
0x18036d5e6  jnz     loc_18036DDDD
0x18036d5ec  mov     rax, [rdi]
0x18036d5ef  mov     rcx, rdi
0x18036d5f2  mov     rax, [rax]
0x18036d5f5  call    cs:__guard_dispatch_icall_fptr
0x18036d5fb  mov     eax, ebx
  ... truncated ...
```
