# Microsoft::RdpNano::RdpSideTransport::OnClosed(void)

- ea: `0x1800e5ab0`
- end: `0x1800e609c`
- name: `?OnClosed@RdpSideTransport@RdpNano@Microsoft@@MEAAXXZ`
- size: `1516`
- prototype: `void __fastcall(Microsoft::RdpNano::RdpSideTransport *__hidden this)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x1800111fc`
- `0x180015bb8`
- `0x180018ea4`
- `0x18001902c`
- `0x18001ab4c`
- `0x18002a8ec`
- `0x18004569c`
- `0x1800de5b4`
- `0x1800e3d30`
- `0x1800e4cd4`
- `0x1800e5ab0`
- `0x180115aac`
- `0x180311d5c`
- `0x180311d64`
- `0x180311dbc`
- `0x180311e54`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x1800e5c26`: `C:\__w\1\s\rdnanolib\rdnano\RdpSideTransport.cpp`
- `0x1800e5dc7`: `C:\__w\1\s\rdnanolib\rdnano\RdpSideTransport.cpp`
- `0x1800e5cbf`: `Microsoft::RdpNano::RdpSideTransport::OnClosed`
- `0x1800e5db3`: `Microsoft::RdpNano::RdpSideTransport::OnClosed`
- `0x1800e5cae`: `RdpSideTransport::OnClosed - last exception: 0x%x, %s\n    %s(%d): %s()`
- `0x1800e5ec2`: `RdpSideTransport::OnClosed - no error reported`
- `0x1800e5da2`: `RdpSideTransport::OnClosed - m_fNetworkDisconnect is false, setting NL_DISCONNECT_LOCAL disconnect reason.\n    %s(%d): %s()`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall Microsoft::RdpNano::RdpSideTransport::OnClosed(Microsoft::RdpNano::RdpSideTransport *this)
{
  char *v2; // r15
  __int64 v3; // rax
  volatile signed __int32 *v4; // rsi
  __int64 *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // r12
  volatile signed __int32 *v8; // rdi
  volatile signed __int32 *v9; // rbx
  __int64 v10; // rdx
  const void *v11; // rax
  unsigned int DctChannelExceptionCode; // r15d
  const char *v13; // r9
  __int128 *v14; // rbx
  volatile signed __int32 *v15; // rbx
  int v16; // r9d
  volatile signed __int32 *v17; // rbx
  unsigned int v18; // r12d
  unsigned int v19; // eax
  Microsoft::RdpNano::IceRestartAgent *v20; // rcx
  __int64 v21; // rdx
  signed __int32 v22; // eax
  signed __int32 v23; // ett
  __int128 v24; // rcx
  const char *v25; // [rsp+20h] [rbp-79h]
  int v26; // [rsp+28h] [rbp-71h]
  const char *v27; // [rsp+30h] [rbp-69h]
  __int128 v28; // [rsp+40h] [rbp-59h] BYREF
  __int128 v29; // [rsp+50h] [rbp-49h]
  __int64 v30; // [rsp+60h] [rbp-39h]
  __int128 v31; // [rsp+68h] [rbp-31h]
  __int128 v32; // [rsp+78h] [rbp-21h]
  __int128 v33; // [rsp+88h] [rbp-11h] BYREF
  __int128 v34; // [rsp+98h] [rbp-1h] BYREF
  __int128 v35; // [rsp+A8h] [rbp+Fh] BYREF
  __m128i si128; // [rsp+B8h] [rbp+1Fh]

  v32 = 0;
  v31 = 0;
  v2 = (char *)this + 248;
  if ( Mtx_lock((Microsoft::RdpNano::RdpSideTransport *)((char *)this + 248)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v2 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v2 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v3 = *((_QWORD *)this + 20);
  if ( v3 )
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
  v30 = *((_QWORD *)this + 19);
  *(_QWORD *)&v31 = v30;
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 20);
  *((_QWORD *)&v31 + 1) = v4;
  v5 = (__int64 *)((char *)this + 88);
  v6 = *((_QWORD *)this + 12);
  if ( v6 )
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
  v7 = *v5;
  *(_QWORD *)&v32 = *v5;
  v8 = (volatile signed __int32 *)*((_QWORD *)this + 12);
  *((_QWORD *)&v32 + 1) = v8;
  v34 = 0;
  std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(v5, &v34);
  v9 = (volatile signed __int32 *)*((_QWORD *)&v34 + 1);
  if ( *((_QWORD *)&v34 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v34 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  Mtx_unlock((_Mtx_t)v2);
  v34 = 0;
  __ExceptionPtrCreate(&v34);
  v35 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v35) = 0;
  if ( v7 )
  {
    v11 = (const void *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v7 + 32LL))(v7, &v33);
    __ExceptionPtrAssign(&v34, v11);
    __ExceptionPtrDestroy(&v33);
  }
  if ( !(unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                           &v34,
                           v10) )
  {
    DctChannelExceptionCode = 0;
    goto LABEL_40;
  }
  v33 = 0;
  __ExceptionPtrCopy(&v33, &v34);
  DctChannelExceptionCode = Microsoft::RdpNano::RdpSideTransport::GetDctChannelExceptionCode(
                              (char *)this - 8,
                              0,
                              &v33,
                              &v35);
  if ( !DctChannelExceptionCode )
  {
LABEL_40:
    v33 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v33);
    if ( (_QWORD)v33 && *(_BYTE *)(v33 + 128) )
    {
      v28 = 0;
      v29 = 0;
      std::string::_Construct<1,char const *>(&v28, "RdpSideTransport::OnClosed - no error reported", 46);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
        &v33,
        "RDPNANO",
        &v28);
      std::string::_Tidy_deallocate(&v28);
    }
    v15 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
    if ( *((_QWORD *)&v33 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          goto LABEL_23;
      }
    }
    goto LABEL_24;
  }
  v33 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v33);
  if ( (_QWORD)v33 && *(_BYTE *)(v33 + 128) )
  {
    v14 = &v35;
    if ( si128.m128i_i64[1] > 0xFuLL )
      v14 = (__int128 *)v35;
    v28 = 0;
    v29 = 0;
    std::string::_Construct<1,char const *>(
      &v28,
      "RdpSideTransport::OnClosed - last exception: 0x%x, %s\n    %s(%d): %s()",
      70,
      v13,
      v25,
      v26,
      v27);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,long,char const *,char const *,int,char const *>(
      (unsigned int)&v33,
      (unsigned int)"RDPNANO",
      (unsigned int)&v28,
      DctChannelExceptionCode,
      (__int64)v14,
      (__int64)"C:\\__w\\1\\s\\rdnanolib\\rdnano\\RdpSideTransport.cpp",
      9,
      (__int64)"Microsoft::RdpNano::RdpSideTransport::OnClosed");
    std::string::_Tidy_deallocate(&v28);
  }
  v15 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
  if ( *((_QWORD *)&v33 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
LABEL_23:
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
LABEL_24:
  std::string::_Tidy_deallocate(&v35);
  __ExceptionPtrDestroy(&v34);
  if ( !*((_BYTE *)this + 328) )
  {
    v34 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v34);
    if ( (_QWORD)v34 && *(_BYTE *)(v34 + 128) )
    {
      v28 = 0;
      v29 = 0;
      std::string::_Construct<1,char const *>(
        &v28,
        "RdpSideTransport::OnClosed - m_fNetworkDisconnect is false, setting NL_DISCONNECT_LOCAL disconnect reason.\n"
        "    %s(%d): %s()",
        (const char *)0x7B,
        v16,
        v25);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
        (unsigned int)&v34,
        (unsigned int)"RDPNANO",
        (unsigned int)&v28,
        (unsigned int)"C:\\__w\\1\\s\\rdnanolib\\rdnano\\RdpSideTransport.cpp",
        21,
        (__int64)"Microsoft::RdpNano::RdpSideTransport::OnClosed");
      std::string::_Tidy_deallocate(&v28);
    }
    v17 = (volatile signed __int32 *)*((_QWORD *)&v34 + 1);
    if ( *((_QWORD *)&v34 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v34 + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( !_InterlockedDecrement(v17 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    DctChannelExceptionCode = 1;
  }
  v18 = 0;
  if ( v30 )
  {
    v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 24LL))(v30);
    v18 = Microsoft::RdpNano::RdpSideTransport::ConvertSmilesLinkTypeToNanoLinkType((char *)this - 8, v19);
  }
  v20 = (Microsoft::RdpNano::IceRestartAgent *)*((_QWORD *)this + 7);
  if ( v20 )
    Microsoft::RdpNano::IceRestartAgent::CloseAndJoin(v20);
  v33 = 0;
  v21 = *((_QWORD *)this + 10);
  if ( v21 )
  {
    v22 = *(_DWORD *)(v21 + 8);
    while ( v22 )
    {
      v23 = v22;
      v22 = _InterlockedCompareExchange((volatile signed __int32 *)(v21 + 8), v22 + 1, v22);
      if ( v23 == v22 )
      {
        *(_QWORD *)&v24 = *((_QWORD *)this + 9);
        *(_QWORD *)&v33 = v24;
        *((_QWORD *)&v24 + 1) = *((_QWORD *)this + 10);
        *((_QWORD *)&v33 + 1) = *((_QWORD *)&v24 + 1);
        goto LABEL_50;
      }
    }
  }
  v24 = v33;
LABEL_50:
  if ( (_QWORD)v24 )
    (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v24 + 8LL))(v24, DctChannelExceptionCode, v18);
  if ( *((_QWORD *)&v24 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL)) )
    {
      (***((void (__fastcall ****)(_QWORD))&v24 + 1))(*((_QWORD *)&v24 + 1));
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 12LL)) )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v24 + 1) + 8LL))(*((_QWORD *)&v24 + 1));
    }
  }
  if ( v4 )
  {
    if ( !_InterlockedDecrement(v4 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( !_InterlockedDecrement(v4 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  if ( v8 && !_InterlockedDecrement(v8 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
    if ( !_InterlockedDecrement(v8 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
  }
}

```

## disassembly

```asm
0x1800e5ab0  mov     rax, rsp
0x1800e5ab3  mov     [rax+10h], rbx
0x1800e5ab7  mov     [rax+18h], rsi
0x1800e5abb  mov     [rax+20h], rdi
0x1800e5abf  push    rbp
0x1800e5ac0  push    r12
0x1800e5ac2  push    r13
0x1800e5ac4  push    r14
0x1800e5ac6  push    r15
0x1800e5ac8  lea     rbp, [rax-5Fh]
0x1800e5acc  mov     eax, 0D0h
0x1800e5ad1  call    _alloca_probe
0x1800e5ad6  sub     rsp, rax
0x1800e5ad9  mov     rax, cs:__security_cookie
0x1800e5ae0  xor     rax, rsp
0x1800e5ae3  mov     [rbp+57h+var_28], rax
0x1800e5ae7  mov     r14, rcx
0x1800e5aea  xorps   xmm1, xmm1
0x1800e5aed  movdqu  [rbp+57h+var_78], xmm1
0x1800e5af2  movdqu  [rbp+57h+var_88], xmm1
0x1800e5af7  lea     r15, [rcx+0F8h]
0x1800e5afe  mov     rcx, r15; _Mtx_t
0x1800e5b01  call    _Mtx_lock
0x1800e5b06  xor     r13d, r13d
0x1800e5b09  test    eax, eax
0x1800e5b0b  jnz     loc_1800E6091
0x1800e5b11  cmp     dword ptr [r15+4Ch], 7FFFFFFFh
0x1800e5b19  jz      loc_1800E607E
0x1800e5b1f  mov     rax, [r14+0A0h]
0x1800e5b26  test    rax, rax
0x1800e5b29  jz      short loc_1800E5B2F
0x1800e5b2b  lock inc dword ptr [rax+8]
0x1800e5b2f  mov     rax, [r14+98h]
0x1800e5b36  mov     [rbp+57h+var_90], rax
0x1800e5b3a  mov     qword ptr [rbp+57h+var_88], rax
0x1800e5b3e  mov     rsi, [r14+0A0h]
0x1800e5b45  mov     qword ptr [rbp+57h+var_88+8], rsi
0x1800e5b49  lea     rcx, [r14+58h]
0x1800e5b4d  mov     rax, [rcx+8]
0x1800e5b51  test    rax, rax
0x1800e5b54  jz      short loc_1800E5B5A
0x1800e5b56  lock inc dword ptr [rax+8]
0x1800e5b5a  mov     r12, [rcx]
0x1800e5b5d  mov     qword ptr [rbp+57h+var_78], r12
0x1800e5b61  mov     rdi, [rcx+8]
0x1800e5b65  mov     qword ptr [rbp+57h+var_78+8], rdi
0x1800e5b69  xorps   xmm0, xmm0
0x1800e5b6c  movdqu  [rbp+57h+var_58], xmm0
0x1800e5b71  lea     rdx, [rbp+57h+var_58]
0x1800e5b75  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x1800e5b7a  mov     rbx, qword ptr [rbp+57h+var_58+8]
0x1800e5b7e  test    rbx, rbx
0x1800e5b81  jz      short loc_1800E5BBC
0x1800e5b83  or      eax, 0FFFFFFFFh
0x1800e5b86  lock xadd [rbx+8], eax
0x1800e5b8b  cmp     eax, 1
0x1800e5b8e  jnz     short loc_1800E5BBC
0x1800e5b90  mov     rax, [rbx]
0x1800e5b93  mov     rcx, rbx
0x1800e5b96  mov     rax, [rax]
0x1800e5b99  call    cs:__guard_dispatch_icall_fptr
0x1800e5b9f  or      eax, 0FFFFFFFFh
0x1800e5ba2  lock xadd [rbx+0Ch], eax
0x1800e5ba7  cmp     eax, 1
0x1800e5baa  jnz     short loc_1800E5BBC
0x1800e5bac  mov     rax, [rbx]
0x1800e5baf  mov     rcx, rbx
0x1800e5bb2  mov     rax, [rax+8]
0x1800e5bb6  call    cs:__guard_dispatch_icall_fptr
0x1800e5bbc  mov     rcx, r15; _Mtx_t
0x1800e5bbf  call    _Mtx_unlock
0x1800e5bc4  xorps   xmm1, xmm1
0x1800e5bc7  movdqu  [rbp+57h+var_58], xmm1
0x1800e5bcc  lea     rcx, [rbp+57h+var_58]; void *
0x1800e5bd0  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800e5bd5  nop
0x1800e5bd6  xorps   xmm0, xmm0
0x1800e5bd9  movups  [rbp+57h+var_48], xmm0
0x1800e5bdd  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800e5be5  movdqu  [rbp+57h+var_38], xmm1
0x1800e5bea  mov     byte ptr [rbp+57h+var_48], r13b
0x1800e5bee  test    r12, r12
0x1800e5bf1  jz      short loc_1800E5C1D
0x1800e5bf3  mov     rax, [r12]
0x1800e5bf7  lea     rdx, [rbp+57h+var_68]
0x1800e5bfb  mov     rcx, r12
0x1800e5bfe  mov     rax, [rax+20h]
0x1800e5c02  call    cs:__guard_dispatch_icall_fptr
0x1800e5c08  mov     rdx, rax; void *
0x1800e5c0b  lea     rcx, [rbp+57h+var_58]; void *
0x1800e5c0f  call    ?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1800e5c14  lea     rcx, [rbp+57h+var_68]; void *
0x1800e5c18  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800e5c1d  lea     rcx, [rbp+57h+var_58]
0x1800e5c21  call    ??B?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(void)
0x1800e5c26  lea     r12, aCW1SRdnanolibR; "C:\\__w\\1\\s\\rdnanolib\\rdnano\\RdpSi"...
0x1800e5c2d  test    al, al
0x1800e5c2f  jz      loc_1800E5E87
0x1800e5c35  xorps   xmm0, xmm0
0x1800e5c38  movdqu  [rbp+57h+var_68], xmm0
0x1800e5c3d  lea     rdx, [rbp+57h+var_58]; void *
0x1800e5c41  lea     rcx, [rbp+57h+var_68]; void *
0x1800e5c45  call    ?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800e5c4a  lea     rcx, [r14-8]
0x1800e5c4e  lea     r9, [rbp+57h+var_48]
0x1800e5c52  lea     r8, [rbp+57h+var_68]
0x1800e5c56  xor     edx, edx
0x1800e5c58  call    ?GetDctChannelExceptionCode@RdpSideTransport@RdpNano@Microsoft@@IEAAJ_NVexception_ptr@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::RdpNano::RdpSideTransport::GetDctChannelExceptionCode(bool,std::exception_ptr,std::string &)
0x1800e5c5d  mov     r15d, eax
0x1800e5c60  test    eax, eax
0x1800e5c62  jz      loc_1800E5E8A
0x1800e5c68  xorps   xmm0, xmm0
0x1800e5c6b  movups  [rbp+57h+var_68], xmm0
0x1800e5c6f  lea     rcx, [rbp+57h+var_68]
0x1800e5c73  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x1800e5c78  nop
0x1800e5c79  mov     rax, qword ptr [rbp+57h+var_68]
0x1800e5c7d  test    rax, rax
0x1800e5c80  jz      short loc_1800E5CFF
0x1800e5c82  cmp     [rax+80h], r13b
0x1800e5c89  jz      short loc_1800E5CFF
0x1800e5c8b  lea     rbx, [rbp+57h+var_48]
0x1800e5c8f  cmp     qword ptr [rbp+57h+var_38+8], 0Fh
0x1800e5c94  cmova   rbx, qword ptr [rbp+57h+var_48]
0x1800e5c99  xorps   xmm0, xmm0
0x1800e5c9c  movups  [rbp+57h+var_B0], xmm0
0x1800e5ca0  xorps   xmm1, xmm1
0x1800e5ca3  movdqu  [rbp+57h+var_A0], xmm1
0x1800e5ca8  mov     r8d, 46h ; 'F'
0x1800e5cae  lea     rdx, aRdpsidetranspo_19; "RdpSideTransport::OnClosed - last excep"...
0x1800e5cb5  lea     rcx, [rbp+57h+var_B0]
0x1800e5cb9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800e5cbe  nop
0x1800e5cbf  lea     rax, aMicrosoftRdpna_19; "Microsoft::RdpNano::RdpSideTransport::O"...
0x1800e5cc6  mov     [rsp+0F0h+var_B8], rax
0x1800e5ccb  mov     dword ptr [rsp+0F0h+var_C0], 609h
0x1800e5cd3  mov     qword ptr [rsp+0F0h+var_C8], r12
0x1800e5cd8  mov     [rsp+0F0h+var_D0], rbx
0x1800e5cdd  mov     r9d, r15d
0x1800e5ce0  lea     r8, [rbp+57h+var_B0]
0x1800e5ce4  lea     rdx, aRdpnano; "RDPNANO"
0x1800e5ceb  lea     rcx, [rbp+57h+var_68]
0x1800e5cef  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@JPEBDPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@J11H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,long,char const *,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,long,char const *,char const *,int,char const *)
0x1800e5cf4  nop
0x1800e5cf5  lea     rcx, [rbp+57h+var_B0]
0x1800e5cf9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e5cfe  nop
0x1800e5cff  mov     rbx, qword ptr [rbp+57h+var_68+8]
0x1800e5d03  test    rbx, rbx
0x1800e5d06  jz      short loc_1800E5D45
0x1800e5d08  or      r12d, 0FFFFFFFFh
0x1800e5d0c  mov     eax, r12d
0x1800e5d0f  lock xadd [rbx+8], eax
0x1800e5d14  add     eax, r12d
0x1800e5d17  jnz     short loc_1800E5D45
0x1800e5d19  mov     rax, [rbx]
0x1800e5d1c  mov     rcx, rbx
0x1800e5d1f  mov     rax, [rax]
0x1800e5d22  call    cs:__guard_dispatch_icall_fptr
0x1800e5d28  mov     eax, r12d
0x1800e5d2b  lock xadd [rbx+0Ch], eax
0x1800e5d30  add     eax, r12d
0x1800e5d33  jnz     short loc_1800E5D45
0x1800e5d35  mov     rax, [rbx]
0x1800e5d38  mov     rcx, rbx
0x1800e5d3b  mov     rax, [rax+8]
0x1800e5d3f  call    cs:__guard_dispatch_icall_fptr
0x1800e5d45  or      r12d, 0FFFFFFFFh
0x1800e5d49  lea     rcx, [rbp+57h+var_48]
0x1800e5d4d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e5d52  nop
0x1800e5d53  lea     rcx, [rbp+57h+var_58]; void *
0x1800e5d57  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800e5d5c  cmp     byte ptr [r14+148h], 0
0x1800e5d64  jnz     loc_1800E5E35
0x1800e5d6a  xorps   xmm0, xmm0
0x1800e5d6d  movups  [rbp+57h+var_58], xmm0
0x1800e5d71  lea     rcx, [rbp+57h+var_58]
0x1800e5d75  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x1800e5d7a  nop
0x1800e5d7b  mov     rax, qword ptr [rbp+57h+var_58]
0x1800e5d7f  test    rax, rax
0x1800e5d82  jz      short loc_1800E5DED
0x1800e5d84  cmp     byte ptr [rax+80h], 0
0x1800e5d8b  jz      short loc_1800E5DED
0x1800e5d8d  xorps   xmm0, xmm0
0x1800e5d90  movups  [rbp+57h+var_B0], xmm0
0x1800e5d94  xorps   xmm1, xmm1
0x1800e5d97  movdqu  [rbp+57h+var_A0], xmm1
0x1800e5d9c  mov     r8d, 7Bh ; '{'
0x1800e5da2  lea     rdx, aRdpsidetranspo_16; "RdpSideTransport::OnClosed - m_fNetwork"...
0x1800e5da9  lea     rcx, [rbp+57h+var_B0]
0x1800e5dad  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800e5db2  nop
0x1800e5db3  lea     rax, aMicrosoftRdpna_19; "Microsoft::RdpNano::RdpSideTransport::O"...
0x1800e5dba  mov     qword ptr [rsp+0F0h+var_C8], rax
0x1800e5dbf  mov     dword ptr [rsp+0F0h+var_D0], 615h
0x1800e5dc7  lea     r9, aCW1SRdnanolibR; "C:\\__w\\1\\s\\rdnanolib\\rdnano\\RdpSi"...
0x1800e5dce  lea     r8, [rbp+57h+var_B0]
0x1800e5dd2  lea     rdx, aRdpnano; "RDPNANO"
0x1800e5dd9  lea     rcx, [rbp+57h+var_58]
0x1800e5ddd  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,char const *,int,char const *)
0x1800e5de2  nop
0x1800e5de3  lea     rcx, [rbp+57h+var_B0]
0x1800e5de7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e5dec  nop
0x1800e5ded  mov     rbx, qword ptr [rbp+57h+var_58+8]
0x1800e5df1  test    rbx, rbx
0x1800e5df4  jz      short loc_1800E5E2F
0x1800e5df6  mov     eax, r12d
0x1800e5df9  lock xadd [rbx+8], eax
0x1800e5dfe  add     eax, r12d
0x1800e5e01  jnz     short loc_1800E5E2F
0x1800e5e03  mov     rax, [rbx]
0x1800e5e06  mov     rcx, rbx
0x1800e5e09  mov     rax, [rax]
0x1800e5e0c  call    cs:__guard_dispatch_icall_fptr
0x1800e5e12  mov     eax, r12d
0x1800e5e15  lock xadd [rbx+0Ch], eax
0x1800e5e1a  add     eax, r12d
0x1800e5e1d  jnz     short loc_1800E5E2F
0x1800e5e1f  mov     rax, [rbx]
0x1800e5e22  mov     rcx, rbx
0x1800e5e25  mov     rax, [rax+8]
0x1800e5e29  call    cs:__guard_dispatch_icall_fptr
0x1800e5e2f  mov     r15d, 1
0x1800e5e35  xor     r12d, r12d
0x1800e5e38  mov     rcx, [rbp+57h+var_90]
0x1800e5e3c  test    rcx, rcx
0x1800e5e3f  jz      short loc_1800E5E5C
0x1800e5e41  mov     rax, [rcx]
0x1800e5e44  mov     rax, [rax+18h]
0x1800e5e48  call    cs:__guard_dispatch_icall_fptr
0x1800e5e4e  mov     edx, eax
0x1800e5e50  lea     rcx, [r14-8]
0x1800e5e54  call    ?ConvertSmilesLinkTypeToNanoLinkType@RdpSideTransport@RdpNano@Microsoft@@IEAAIW4LinkType@ISmiles@Dct@Basix@3@@Z; Microsoft::RdpNano::RdpSideTransport::ConvertSmilesLinkTypeToNanoLinkType(Microsoft::Basix::Dct::ISmiles::LinkType)
0x1800e5e59  mov     r12d, eax
0x1800e5e5c  mov     rcx, [r14+38h]; this
0x1800e5e60  test    rcx, rcx
0x1800e5e63  jz      short loc_1800E5E6A
0x1800e5e65  call    ?CloseAndJoin@IceRestartAgent@RdpNano@Microsoft@@QEAAXXZ; Microsoft::RdpNano::IceRestartAgent::CloseAndJoin(void)
0x1800e5e6a  xorps   xmm1, xmm1
0x1800e5e6d  movdqu  [rbp+57h+var_68], xmm1
0x1800e5e72  mov     rdx, [r14+50h]
0x1800e5e76  test    rdx, rdx
0x1800e5e79  jz      loc_1800E5F5B
0x1800e5e7f  mov     eax, [rdx+8]
0x1800e5e82  jmp     loc_1800E5F57
0x1800e5e87  mov     r15d, r13d
0x1800e5e8a  xorps   xmm0, xmm0
0x1800e5e8d  movups  [rbp+57h+var_68], xmm0
0x1800e5e91  lea     rcx, [rbp+57h+var_68]
0x1800e5e95  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800e5e9a  nop
0x1800e5e9b  mov     rax, qword ptr [rbp+57h+var_68]
0x1800e5e9f  test    rax, rax
0x1800e5ea2  jz      short loc_1800E5EF2
0x1800e5ea4  cmp     [rax+80h], r13b
0x1800e5eab  jz      short loc_1800E5EF2
0x1800e5ead  xorps   xmm0, xmm0
0x1800e5eb0  movups  [rbp+57h+var_B0], xmm0
0x1800e5eb4  xorps   xmm1, xmm1
0x1800e5eb7  movdqu  [rbp+57h+var_A0], xmm1
0x1800e5ebc  mov     r8d, 2Eh ; '.'
0x1800e5ec2  lea     rdx, aRdpsidetranspo_2; "RdpSideTransport::OnClosed - no error r"...
0x1800e5ec9  lea     rcx, [rbp+57h+var_B0]
0x1800e5ecd  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800e5ed2  nop
0x1800e5ed3  lea     r8, [rbp+57h+var_B0]
0x1800e5ed7  lea     rdx, aRdpnano; "RDPNANO"
0x1800e5ede  lea     rcx, [rbp+57h+var_68]
0x1800e5ee2  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x1800e5ee7  nop
0x1800e5ee8  lea     rcx, [rbp+57h+var_B0]
0x1800e5eec  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800e5ef1  nop
0x1800e5ef2  mov     rbx, qword ptr [rbp+57h+var_68+8]
0x1800e5ef6  test    rbx, rbx
0x1800e5ef9  jz      loc_1800E5D45
0x1800e5eff  or      r12d, 0FFFFFFFFh
0x1800e5f03  mov     eax, r12d
0x1800e5f06  lock xadd [rbx+8], eax
0x1800e5f0b  add     eax, r12d
0x1800e5f0e  jnz     loc_1800E5D49
0x1800e5f14  mov     rax, [rbx]
0x1800e5f17  mov     rcx, rbx
0x1800e5f1a  mov     rax, [rax]
0x1800e5f1d  call    cs:__guard_dispatch_icall_fptr
0x1800e5f23  mov     eax, r12d
0x1800e5f26  lock xadd [rbx+0Ch], eax
0x1800e5f2b  add     eax, r12d
0x1800e5f2e  jnz     loc_1800E5D49
0x1800e5f34  mov     rax, [rbx]
0x1800e5f37  mov     rcx, rbx
0x1800e5f3a  mov     rax, [rax+8]
0x1800e5f3e  call    cs:__guard_dispatch_icall_fptr
0x1800e5f44  jmp     loc_1800E5D49
0x1800e5f49  lea     ecx, [rax+1]
0x1800e5f4c  lock cmpxchg [rdx+8], ecx
0x1800e5f51  jz      loc_1800E6069
  ... truncated ...
```
