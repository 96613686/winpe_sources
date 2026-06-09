# Microsoft::RdpNano::_anonymous_namespace_::FindUPnPService

- ea: `0x1800d88b8`
- end: `0x1800d8fcc`
- name: `Microsoft::RdpNano::_anonymous_namespace_::FindUPnPService`
- size: `1812`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800da0bc`
- `0x1803868e9`

## callees

- `0x18000d9c0`
- `0x18000da90`
- `0x180015bb8`
- `0x180018ea4`
- `0x18001902c`
- `0x180024700`
- `0x180027b84`
- `0x1800d32c8`
- `0x1800d3e4c`
- `0x1800d4284`
- `0x1800d6154`
- `0x1800d88b8`
- `0x1800d8fcc`
- `0x1800db4bc`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x1803304e0`
- `0x180330b40`
- `0x180375c40`

## string_xrefs

- `0x1800d8aa4`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d8e81`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d8f38`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d8e96`: `Failed to get services`
- `0x1800d8a90`: `Microsoft::RdpNano::`anonymous-namespace'::FindUPnPService`
- `0x1800d8bbe`: `Falling back to service enumeration search for %s`
- `0x1800d8f4d`: `Failed to get service item`
- `0x1800d8d75`: `Found UPnP service %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=30
_QWORD *__fastcall Microsoft::RdpNano::_anonymous_namespace_::FindUPnPService(
        _QWORD *a1,
        const char *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  _QWORD *v6; // r15
  int v7; // ebx
  const char *v8; // rdx
  _QWORD *v9; // rdi
  __int64 (__fastcall *v10)(_QWORD *, _QWORD, _QWORD *); // r13
  _QWORD *v11; // rcx
  _bstr_t::Data_t *v12; // rbx
  int v13; // edi
  __int64 v14; // r8
  int v15; // r9d
  volatile signed __int32 *v16; // r14
  _QWORD *v17; // rdx
  volatile signed __int32 *v18; // r14
  __int64 *UPnPServiceByEnumeration; // rax
  __int64 v20; // rdx
  _QWORD *v21; // rcx
  _QWORD *v22; // rcx
  __int128 *v23; // rdx
  volatile signed __int32 *v24; // r14
  Microsoft::Basix *v26; // rcx
  const struct std::error_category *v27; // rax
  Microsoft::Basix *v28; // rcx
  const struct std::error_category *v29; // rax
  __int64 *Description; // rax
  const char *v31; // r9
  __int64 v32; // rbx
  volatile signed __int32 *v33; // rbx
  const char *v34; // [rsp+20h] [rbp-238h]
  int v35; // [rsp+28h] [rbp-230h]
  const char *v36; // [rsp+30h] [rbp-228h]
  const char *v37; // [rsp+20h] [rbp-238h]
  int v38; // [rsp+28h] [rbp-230h]
  const char *v39; // [rsp+30h] [rbp-228h]
  _QWORD *v40; // [rsp+40h] [rbp-218h] BYREF
  _bstr_t::Data_t *v41; // [rsp+48h] [rbp-210h] BYREF
  __int128 v42; // [rsp+50h] [rbp-208h] BYREF
  __int64 v43; // [rsp+60h] [rbp-1F8h]
  __int64 v44; // [rsp+68h] [rbp-1F0h]
  int v45; // [rsp+70h] [rbp-1E8h]
  _QWORD v46[2]; // [rsp+78h] [rbp-1E0h] BYREF
  _OWORD v47[2]; // [rsp+88h] [rbp-1D0h] BYREF
  _QWORD *v48; // [rsp+A8h] [rbp-1B0h]
  const std::exception *v49; // [rsp+B0h] [rbp-1A8h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+C0h] [rbp-198h] BYREF
  _BYTE v51[144]; // [rsp+150h] [rbp-108h] BYREF
  __int128 v52; // [rsp+1E0h] [rbp-78h] BYREF
  __int128 v53; // [rsp+1F0h] [rbp-68h] BYREF
  __int128 v54; // [rsp+200h] [rbp-58h]
  _QWORD *v55; // [rsp+210h] [rbp-48h] BYREF

  v40 = a4;
  v6 = a1;
  v48 = a1;
  *a1 = 0;
  v45 = 1;
  v55 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD **))(*(_QWORD *)*a4 + 200LL))(*a4, &v55);
  if ( v7 < 0 )
  {
    _mm_lfence();
    std::string::string(v47, (const char *)&Str1);
    std::string::string(&v53, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
    std::string::string(&v42, "Failed to get services");
    v27 = Microsoft::Basix::WindowsCategory(v26);
    v52 = *(_OWORD *)std::error_code::error_code((std::error_code *)v46, v7, v27);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v52,
      (unsigned int)&v42,
      (unsigned int)&v53,
      240,
      (__int64)v47);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  v41 = 0;
  v8 = a2;
  if ( *((_QWORD *)a2 + 3) > 0xFu )
    v8 = *(const char **)a2;
  _bstr_t::_bstr_t((_bstr_t *)&v41, v8);
  v9 = v55;
  v10 = *(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD *))(*v55 + 72LL);
  v11 = (_QWORD *)*v6;
  *v6 = 0;
  if ( v11 )
    (*(void (__fastcall **)(_QWORD *))(*v11 + 16LL))(v11);
  v12 = v41;
  if ( !v41 )
  {
    v12 = (_bstr_t::Data_t *)operator new(0x18u);
    v41 = v12;
    if ( v12 )
    {
      *(_OWORD *)v12 = 0;
      *((_QWORD *)v12 + 2) = 0;
      *((_QWORD *)v12 + 1) = 0;
      *((_DWORD *)v12 + 4) = 1;
      *(_QWORD *)v12 = 0;
    }
    else
    {
      v12 = 0;
    }
    v41 = v12;
    if ( !v12 )
    {
      _com_issue_error(-2147024882);
      __debugbreak();
    }
  }
  v13 = v10(v9, *(_QWORD *)v12, v6);
  if ( v13 == -2147024809 )
  {
    v52 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v52);
    if ( (_QWORD)v52 && *(_BYTE *)(v52 + 128) )
    {
      v46[0] = &v42;
      v42 = 0;
      v43 = 0;
      v44 = 0;
      v14 = *((_QWORD *)a2 + 2);
      if ( *((_QWORD *)a2 + 3) > 0xFu )
        a2 = *(const char **)a2;
      std::string::_Construct<2,char const *>(&v42, a2, v14);
      v53 = 0;
      v54 = 0;
      std::string::_Construct<1,char const *>(
        &v53,
        "get_Item for %s return 0x%x\n    %s(%d): %s()",
        (const char *)0x2C,
        v15,
        v37,
        v38,
        v39);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,std::string,long,char const *,int,char const *>(
        (unsigned int)&v52,
        (unsigned int)"RDPNANO",
        (unsigned int)&v53,
        (unsigned int)&v42,
        144,
        (__int64)"C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp",
        249,
        (__int64)"Microsoft::RdpNano::`anonymous-namespace'::FindUPnPService");
      std::string::_Tidy_deallocate(&v53);
    }
    v16 = (volatile signed __int32 *)*((_QWORD *)&v52 + 1);
    if ( *((_QWORD *)&v52 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v52 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    v52 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v52);
    if ( (_QWORD)v52 && *(_BYTE *)(v52 + 128) )
    {
      v46[0] = &v42;
      v42 = 0;
      v43 = 0;
      v44 = 0;
      v17 = a3;
      if ( a3[3] > 0xFu )
        v17 = (_QWORD *)*a3;
      std::string::_Construct<2,char const *>(&v42, v17, a3[2]);
      v53 = 0;
      v54 = 0;
      std::string::_Construct<1,char const *>(
        &v53,
        "Falling back to service enumeration search for %s",
        (const char *)0x31);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(
        &v52,
        "RDPNANO",
        &v53,
        &v42);
      std::string::_Tidy_deallocate(&v53);
    }
    v18 = (volatile signed __int32 *)*((_QWORD *)&v52 + 1);
    if ( *((_QWORD *)&v52 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v52 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    UPnPServiceByEnumeration = Microsoft::RdpNano::_anonymous_namespace_::FindUPnPServiceByEnumeration(
                                 &v40,
                                 (__int64)a3,
                                 v40);
    v20 = *UPnPServiceByEnumeration;
    *UPnPServiceByEnumeration = 0;
    v21 = (_QWORD *)*v6;
    *v6 = v20;
    if ( v21 )
      (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
    if ( v40 )
      (*(void (__fastcall **)(_QWORD *))(*v40 + 16LL))(v40);
  }
  else
  {
    if ( v13 < 0 )
    {
      _mm_lfence();
      std::string::string(v47, (const char *)&Str1);
      std::string::string(&v53, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
      std::string::string(&v42, "Failed to get service item");
      v29 = Microsoft::Basix::WindowsCategory(v28);
      v52 = *(_OWORD *)std::error_code::error_code((std::error_code *)v46, v13, v29);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)v51,
        (unsigned int)&v52,
        (unsigned int)&v42,
        (unsigned int)&v53,
        261,
        (__int64)v47);
      throw (Microsoft::Basix::SystemException *)v51;
    }
    try
    {
      _mm_lfence();
      v22 = (_QWORD *)*v6;
      v40 = v22;
      if ( v22 )
        (*(void (__fastcall **)(_QWORD *))(*v22 + 8LL))(v22);
      Microsoft::RdpNano::_anonymous_namespace_::GetComString_wil::com_ptr_t_IUPnPService_wil::err_exception_policy__long____cdecl_IUPnPService::___wchar_t______(
        &v53,
        &v40,
         IUPnPService::`vcall'{72,{flat}});
      v52 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v52);
      if ( (_QWORD)v52 && *(_BYTE *)(v52 + 128) )
      {
        v46[0] = &v42;
        v42 = 0;
        v43 = 0;
        v44 = 0;
        v23 = &v53;
        if ( *((_QWORD *)&v54 + 1) > 0xFu )
          v23 = (__int128 *)v53;
        std::string::_Construct<2,char const *>(&v42, v23, v54);
        memset(v47, 0, sizeof(v47));
        std::string::_Construct<1,char const *>(v47, "Found UPnP service %s", (const char *)0x15);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(
          &v52,
          "RDPNANO",
          v47,
          &v42);
        std::string::_Tidy_deallocate(v47);
      }
      v24 = (volatile signed __int32 *)*((_QWORD *)&v52 + 1);
      if ( *((_QWORD *)&v52 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v52 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
          if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
        }
      }
      std::string::_Tidy_deallocate(&v53);
    }
    catch ( const std::exception *v49 )
    {
      v52 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v52);
      if ( (_QWORD)v52 && *(_BYTE *)(v52 + 128) )
      {
        Description = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v47, v49);
        v32 = (__int64)Description;
        if ( (unsigned __int64)Description[3] > 0xF )
          v32 = *Description;
        v53 = 0;
        v54 = 0u;
        std::string::_Construct<1,char const *>(
          &v53,
          "%s: %s\n Caught at:\n    %s(%d): %s()",
          (const char *)0x23,
          v31,
          v34,
          v35,
          v36);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
          (unsigned int)&v52,
          (unsigned int)"RDPNANO",
          (unsigned int)&v53,
          (unsigned int)"Failed to get UPNP service type (not fatal)",
          v32,
          (__int64)"C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp",
          16,
          (__int64)"Microsoft::RdpNano::`anonymous-namespace'::FindUPnPService");
        std::string::_Tidy_deallocate(&v53);
        std::string::_Tidy_deallocate(v47);
      }
      v33 = (volatile signed __int32 *)*((_QWORD *)&v52 + 1);
      if ( *((_QWORD *)&v52 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v52 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
          if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
        }
      }
      v12 = v41;
      v6 = v48;
    }
  }
  _bstr_t::Data_t::Release(v12);
  if ( v55 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))(*v55 + 16LL))(v55, *v55);
  return v6;
}

```

## disassembly

```asm
0x1800d88b8  push    rbx
0x1800d88ba  push    rsi
0x1800d88bb  push    rdi
0x1800d88bc  push    r12
0x1800d88be  push    r13
0x1800d88c0  push    r14
0x1800d88c2  push    r15
0x1800d88c4  mov     eax, 220h
0x1800d88c9  call    _alloca_probe
0x1800d88ce  sub     rsp, rax
0x1800d88d1  mov     rax, cs:__security_cookie
0x1800d88d8  xor     rax, rsp
0x1800d88db  mov     [rsp+258h+var_40], rax
0x1800d88e3  mov     [rsp+258h+var_218], r9
0x1800d88e8  mov     r12, r8
0x1800d88eb  mov     r14, rdx
0x1800d88ee  mov     r15, rcx
0x1800d88f1  mov     [rsp+258h+var_1B0], rcx
0x1800d88f9  xor     esi, esi
0x1800d88fb  mov     [rsp+258h+var_1E8], esi
0x1800d88ff  mov     [rcx], rsi
0x1800d8902  mov     [rsp+258h+var_1E8], 1
0x1800d890a  mov     [rsp+258h+var_48], rsi
0x1800d8912  mov     rcx, [r9]
0x1800d8915  mov     rax, [rcx]
0x1800d8918  mov     [rsp+258h+var_48], rsi
0x1800d8920  lea     rdx, [rsp+258h+var_48]
0x1800d8928  mov     rax, [rax+0C8h]
0x1800d892f  call    cs:__guard_dispatch_icall_fptr
0x1800d8935  mov     ebx, eax
0x1800d8937  test    eax, eax
0x1800d8939  js      loc_1800D8E69
0x1800d893f  mov     [rsp+258h+var_210], rsi
0x1800d8944  mov     rdx, r14
0x1800d8947  cmp     qword ptr [r14+18h], 0Fh
0x1800d894c  jbe     short loc_1800D8951
0x1800d894e  mov     rdx, [r14]; char *
0x1800d8951  lea     rcx, [rsp+258h+var_210]; this
0x1800d8956  call    ??0_bstr_t@@QEAA@PEBD@Z; _bstr_t::_bstr_t(char const *)
0x1800d895b  nop
0x1800d895c  mov     rdi, [rsp+258h+var_48]
0x1800d8964  mov     rax, [rdi]
0x1800d8967  mov     r13, [rax+48h]
0x1800d896b  mov     rcx, [r15]
0x1800d896e  mov     [r15], rsi
0x1800d8971  test    rcx, rcx
0x1800d8974  jz      short loc_1800D8984
0x1800d8976  mov     rax, [rcx]
0x1800d8979  mov     rax, [rax+10h]
0x1800d897d  call    cs:__guard_dispatch_icall_fptr
0x1800d8983  nop
0x1800d8984  mov     rbx, [rsp+258h+var_210]
0x1800d8989  test    rbx, rbx
0x1800d898c  jnz     short loc_1800D89D0
0x1800d898e  lea     ecx, [rbx+18h]; Size
0x1800d8991  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d8996  mov     rbx, rax
0x1800d8999  mov     [rsp+258h+var_210], rax
0x1800d899e  test    rax, rax
0x1800d89a1  jz      short loc_1800D89BF
0x1800d89a3  xorps   xmm0, xmm0
0x1800d89a6  xor     eax, eax
0x1800d89a8  movups  xmmword ptr [rbx], xmm0
0x1800d89ab  mov     [rbx+10h], rax
0x1800d89af  mov     [rbx+8], rsi
0x1800d89b3  mov     dword ptr [rbx+10h], 1
0x1800d89ba  mov     [rbx], rsi
0x1800d89bd  jmp     short loc_1800D89C2
0x1800d89bf  mov     rbx, rsi
0x1800d89c2  mov     [rsp+258h+var_210], rbx
0x1800d89c7  test    rbx, rbx
0x1800d89ca  jz      loc_1800D8F15
0x1800d89d0  mov     r8, r15
0x1800d89d3  mov     rdx, [rbx]
0x1800d89d6  mov     rcx, rdi
0x1800d89d9  mov     rax, r13
0x1800d89dc  call    cs:__guard_dispatch_icall_fptr
0x1800d89e2  mov     edi, eax
0x1800d89e4  cmp     eax, 80070057h
0x1800d89e9  jnz     loc_1800D8C98
0x1800d89ef  xorps   xmm0, xmm0
0x1800d89f2  movups  [rsp+258h+var_78], xmm0
0x1800d89fa  lea     rcx, [rsp+258h+var_78]
0x1800d8a02  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x1800d8a07  nop
0x1800d8a08  mov     rax, qword ptr [rsp+258h+var_78]
0x1800d8a10  test    rax, rax
0x1800d8a13  jz      loc_1800D8AE8
0x1800d8a19  cmp     [rax+80h], sil
0x1800d8a20  jz      loc_1800D8AE8
0x1800d8a26  lea     rax, [rsp+258h+var_208]
0x1800d8a2b  mov     [rsp+258h+var_1E0], rax
0x1800d8a30  xorps   xmm0, xmm0
0x1800d8a33  movups  [rsp+258h+var_208], xmm0
0x1800d8a38  mov     [rsp+258h+var_1F8], rsi
0x1800d8a3d  mov     [rsp+258h+var_1F0], rsi
0x1800d8a42  mov     r8, [r14+10h]
0x1800d8a46  cmp     qword ptr [r14+18h], 0Fh
0x1800d8a4b  jbe     short loc_1800D8A50
0x1800d8a4d  mov     r14, [r14]
0x1800d8a50  mov     rdx, r14
0x1800d8a53  lea     rcx, [rsp+258h+var_208]
0x1800d8a58  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800d8a5d  nop
0x1800d8a5e  xorps   xmm0, xmm0
0x1800d8a61  movups  [rsp+258h+var_68], xmm0
0x1800d8a69  xorps   xmm1, xmm1
0x1800d8a6c  movdqu  [rsp+258h+var_58], xmm1
0x1800d8a75  mov     r8d, 2Ch ; ','
0x1800d8a7b  lea     rdx, aGetItemForSRet; "get_Item for %s return 0x%x\n    %s(%d)"...
0x1800d8a82  lea     rcx, [rsp+258h+var_68]
0x1800d8a8a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8a8f  nop
0x1800d8a90  lea     rax, aMicrosoftRdpna_2; "Microsoft::RdpNano::`anonymous-namespac"...
0x1800d8a97  mov     [rsp+258h+var_220], rax
0x1800d8a9c  mov     dword ptr [rsp+258h+var_228], 0F9h
0x1800d8aa4  lea     rdx, aCW1SRdpnanodll_13; "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpma"...
0x1800d8aab  mov     [rsp+258h+var_230], rdx
0x1800d8ab0  mov     dword ptr [rsp+258h+var_238], 80070490h
0x1800d8ab8  lea     r9, [rsp+258h+var_208]
0x1800d8abd  lea     r8, [rsp+258h+var_68]
0x1800d8ac5  lea     rdx, aRdpnano; "RDPNANO"
0x1800d8acc  lea     rcx, [rsp+258h+var_78]
0x1800d8ad4  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@JPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@V65@J1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,std::string,long,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,std::string,long,char const *,int,char const *)
0x1800d8ad9  nop
0x1800d8ada  lea     rcx, [rsp+258h+var_68]
0x1800d8ae2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d8ae7  nop
0x1800d8ae8  mov     r14, qword ptr [rsp+258h+var_78+8]
0x1800d8af0  or      edi, 0FFFFFFFFh
0x1800d8af3  test    r14, r14
0x1800d8af6  jz      short loc_1800D8B2F
0x1800d8af8  mov     eax, edi
0x1800d8afa  lock xadd [r14+8], eax
0x1800d8b00  add     eax, edi
0x1800d8b02  jnz     short loc_1800D8B2F
0x1800d8b04  mov     rax, [r14]
0x1800d8b07  mov     rcx, r14
0x1800d8b0a  mov     rax, [rax]
0x1800d8b0d  call    cs:__guard_dispatch_icall_fptr
0x1800d8b13  mov     eax, edi
0x1800d8b15  lock xadd [r14+0Ch], eax
0x1800d8b1b  add     eax, edi
0x1800d8b1d  jnz     short loc_1800D8B2F
0x1800d8b1f  mov     rax, [r14]
0x1800d8b22  mov     rcx, r14
0x1800d8b25  mov     rax, [rax+8]
0x1800d8b29  call    cs:__guard_dispatch_icall_fptr
0x1800d8b2f  xorps   xmm0, xmm0
0x1800d8b32  movups  [rsp+258h+var_78], xmm0
0x1800d8b3a  lea     rcx, [rsp+258h+var_78]
0x1800d8b42  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800d8b47  nop
0x1800d8b48  mov     rax, qword ptr [rsp+258h+var_78]
0x1800d8b50  test    rax, rax
0x1800d8b53  jz      loc_1800D8C03
0x1800d8b59  cmp     [rax+80h], sil
0x1800d8b60  jz      loc_1800D8C03
0x1800d8b66  lea     rax, [rsp+258h+var_208]
0x1800d8b6b  mov     [rsp+258h+var_1E0], rax
0x1800d8b70  xorps   xmm0, xmm0
0x1800d8b73  movups  [rsp+258h+var_208], xmm0
0x1800d8b78  mov     [rsp+258h+var_1F8], rsi
0x1800d8b7d  mov     [rsp+258h+var_1F0], rsi
0x1800d8b82  mov     rdx, r12
0x1800d8b85  cmp     qword ptr [r12+18h], 0Fh
0x1800d8b8b  jbe     short loc_1800D8B91
0x1800d8b8d  mov     rdx, [r12]
0x1800d8b91  mov     r8, [r12+10h]
0x1800d8b96  lea     rcx, [rsp+258h+var_208]
0x1800d8b9b  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800d8ba0  nop
0x1800d8ba1  xorps   xmm0, xmm0
0x1800d8ba4  movups  [rsp+258h+var_68], xmm0
0x1800d8bac  xorps   xmm1, xmm1
0x1800d8baf  movdqu  [rsp+258h+var_58], xmm1
0x1800d8bb8  mov     r8d, 31h ; '1'
0x1800d8bbe  lea     rdx, aFallingBackToS; "Falling back to service enumeration sea"...
0x1800d8bc5  lea     rcx, [rsp+258h+var_68]
0x1800d8bcd  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8bd2  nop
0x1800d8bd3  lea     r9, [rsp+258h+var_208]
0x1800d8bd8  lea     r8, [rsp+258h+var_68]
0x1800d8be0  lea     rdx, aRdpnano; "RDPNANO"
0x1800d8be7  lea     rcx, [rsp+258h+var_78]
0x1800d8bef  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@V65@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,std::string)
0x1800d8bf4  nop
0x1800d8bf5  lea     rcx, [rsp+258h+var_68]
0x1800d8bfd  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d8c02  nop
0x1800d8c03  mov     r14, qword ptr [rsp+258h+var_78+8]
0x1800d8c0b  test    r14, r14
0x1800d8c0e  jz      short loc_1800D8C47
0x1800d8c10  mov     eax, edi
0x1800d8c12  lock xadd [r14+8], eax
0x1800d8c18  add     eax, edi
0x1800d8c1a  jnz     short loc_1800D8C47
0x1800d8c1c  mov     rax, [r14]
0x1800d8c1f  mov     rcx, r14
0x1800d8c22  mov     rax, [rax]
0x1800d8c25  call    cs:__guard_dispatch_icall_fptr
0x1800d8c2b  mov     eax, edi
0x1800d8c2d  lock xadd [r14+0Ch], eax
0x1800d8c33  add     eax, edi
0x1800d8c35  jnz     short loc_1800D8C47
0x1800d8c37  mov     rax, [r14]
0x1800d8c3a  mov     rcx, r14
0x1800d8c3d  mov     rax, [rax+8]
0x1800d8c41  call    cs:__guard_dispatch_icall_fptr
0x1800d8c47  mov     r8, [rsp+258h+var_218]
0x1800d8c4c  mov     rdx, r12
0x1800d8c4f  lea     rcx, [rsp+258h+var_218]
0x1800d8c54  call    Microsoft__RdpNano___anonymous_namespace___FindUPnPServiceByEnumeration
0x1800d8c59  mov     rdx, [rax]
0x1800d8c5c  mov     [rax], rsi
0x1800d8c5f  mov     rcx, [r15]
0x1800d8c62  mov     [r15], rdx
0x1800d8c65  test    rcx, rcx
0x1800d8c68  jz      short loc_1800D8C78
0x1800d8c6a  mov     rax, [rcx]
0x1800d8c6d  mov     rax, [rax+10h]
0x1800d8c71  call    cs:__guard_dispatch_icall_fptr
0x1800d8c77  nop
0x1800d8c78  mov     rcx, [rsp+258h+var_218]
0x1800d8c7d  test    rcx, rcx
0x1800d8c80  jz      loc_1800D8E10
0x1800d8c86  mov     rax, [rcx]
0x1800d8c89  mov     rax, [rax+10h]
0x1800d8c8d  call    cs:__guard_dispatch_icall_fptr
0x1800d8c93  jmp     loc_1800D8E10
0x1800d8c98  test    edi, edi
0x1800d8c9a  js      loc_1800D8F20
0x1800d8ca0  lfence
0x1800d8ca3  mov     rcx, [r15]
0x1800d8ca6  mov     [rsp+258h+var_218], rcx
0x1800d8cab  test    rcx, rcx
0x1800d8cae  jz      short loc_1800D8CBE
0x1800d8cb0  mov     rax, [rcx]
0x1800d8cb3  mov     rax, [rax+8]
0x1800d8cb7  call    cs:__guard_dispatch_icall_fptr
0x1800d8cbd  nop
0x1800d8cbe  lea     r8, ??_9IUPnPService@@$BEI@AA; [thunk]: IUPnPService::`vcall'{72,{flat}}
0x1800d8cc5  lea     rdx, [rsp+258h+var_218]
0x1800d8cca  lea     rcx, [rsp+258h+var_68]
0x1800d8cd2  call    Microsoft__RdpNano___anonymous_namespace___GetComString_wil__com_ptr_t_IUPnPService_wil__err_exception_policy__long____cdecl_IUPnPService_____wchar_t______
0x1800d8cd7  nop
0x1800d8cd8  xorps   xmm0, xmm0
0x1800d8cdb  movups  [rsp+258h+var_78], xmm0
0x1800d8ce3  lea     rcx, [rsp+258h+var_78]
0x1800d8ceb  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800d8cf0  nop
0x1800d8cf1  mov     rax, qword ptr [rsp+258h+var_78]
0x1800d8cf9  test    rax, rax
0x1800d8cfc  jz      loc_1800D8DBA
0x1800d8d02  cmp     [rax+80h], sil
0x1800d8d09  jz      loc_1800D8DBA
0x1800d8d0f  lea     rax, [rsp+258h+var_208]
0x1800d8d14  mov     [rsp+258h+var_1E0], rax
0x1800d8d19  xorps   xmm0, xmm0
0x1800d8d1c  movups  [rsp+258h+var_208], xmm0
0x1800d8d21  mov     [rsp+258h+var_1F8], rsi
0x1800d8d26  mov     [rsp+258h+var_1F0], rsi
0x1800d8d2b  lea     rdx, [rsp+258h+var_68]
0x1800d8d33  cmp     qword ptr [rsp+258h+var_58+8], 0Fh
0x1800d8d3c  cmova   rdx, qword ptr [rsp+258h+var_68]
0x1800d8d45  mov     r8, qword ptr [rsp+258h+var_58]
0x1800d8d4d  lea     rcx, [rsp+258h+var_208]
0x1800d8d52  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800d8d57  nop
0x1800d8d58  xorps   xmm0, xmm0
0x1800d8d5b  movups  [rsp+258h+var_1D0], xmm0
0x1800d8d63  xorps   xmm1, xmm1
0x1800d8d66  movdqu  [rsp+258h+var_1C0], xmm1
0x1800d8d6f  mov     r8d, 15h
0x1800d8d75  lea     rdx, aFoundUpnpServi; "Found UPnP service %s"
0x1800d8d7c  lea     rcx, [rsp+258h+var_1D0]
0x1800d8d84  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800d8d89  nop
0x1800d8d8a  lea     r9, [rsp+258h+var_208]
0x1800d8d8f  lea     r8, [rsp+258h+var_1D0]
0x1800d8d97  lea     rdx, aRdpnano; "RDPNANO"
0x1800d8d9e  lea     rcx, [rsp+258h+var_78]
0x1800d8da6  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@V65@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,std::string)
0x1800d8dab  nop
0x1800d8dac  lea     rcx, [rsp+258h+var_1D0]
0x1800d8db4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800d8db9  nop
0x1800d8dba  mov     r14, qword ptr [rsp+258h+var_78+8]
0x1800d8dc2  test    r14, r14
0x1800d8dc5  jz      short loc_1800D8E02
0x1800d8dc7  or      edi, 0FFFFFFFFh
0x1800d8dca  mov     eax, edi
0x1800d8dcc  lock xadd [r14+8], eax
0x1800d8dd2  add     eax, edi
0x1800d8dd4  jnz     short loc_1800D8E02
0x1800d8dd6  mov     rax, [r14]
0x1800d8dd9  mov     rcx, r14
0x1800d8ddc  mov     rax, [rax]
0x1800d8ddf  call    cs:__guard_dispatch_icall_fptr
0x1800d8de5  mov     eax, edi
  ... truncated ...
```
