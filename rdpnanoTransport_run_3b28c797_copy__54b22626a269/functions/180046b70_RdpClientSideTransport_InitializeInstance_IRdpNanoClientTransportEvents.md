# RdpClientSideTransport::InitializeInstance(IRdpNanoClientTransportEvents *)

- ea: `0x180046b70`
- end: `0x180046f4e`
- name: `?InitializeInstance@RdpClientSideTransport@@UEAAJPEAUIRdpNanoClientTransportEvents@@@Z`
- size: `990`
- prototype: `__int64 __fastcall(RdpClientSideTransport *__hidden this, struct IRdpNanoClientTransportEvents *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x1800111fc`
- `0x180015bb8`
- `0x180018ea4`
- `0x18001902c`
- `0x18001b010`
- `0x18004569c`
- `0x180045a60`
- `0x180045da4`
- `0x180046b70`
- `0x1800e3ed8`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x180046bf3`: `RdpClientSideTransport::InitializeInstance`
- `0x180046dfe`: `RdpClientSideTransport::InitializeInstance`
- `0x180046c07`: `C:\__w\1\s\rdpnanodll\RdpClientSideTransport.cpp`
- `0x180046e12`: `C:\__w\1\s\rdpnanodll\RdpClientSideTransport.cpp`
- `0x180046dee`: `Failed to create RdpSideTransport.\n    %s(%d): %s()`
- `0x180046eba`: `RdpClientSideTransport::InitializeInstance: hr=0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RdpClientSideTransport::InitializeInstance(
        RdpClientSideTransport *this,
        struct IRdpNanoClientTransportEvents *a2)
{
  int v3; // r9d
  volatile signed __int32 *v4; // rdi
  __int64 *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rax
  volatile signed __int32 *v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rax
  volatile signed __int32 *v13; // rdi
  int v14; // r9d
  volatile signed __int32 *v15; // rdi
  volatile signed __int32 *v16; // rdi
  const char *v17; // [rsp+20h] [rbp-60h]
  __int128 v18; // [rsp+30h] [rbp-50h] BYREF
  __int128 v19; // [rsp+40h] [rbp-40h]
  __int128 v20; // [rsp+50h] [rbp-30h] BYREF
  __int128 v21; // [rsp+60h] [rbp-20h] BYREF

  *(_QWORD *)&v20 = a2;
  if ( a2 )
  {
    v6 = (__int64 *)wil::com_weak_query<IVirtualChannelCallbacks * &>(&v21, &v20);
    v7 = *v6;
    *v6 = 0;
    v8 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v7;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    if ( (_QWORD)v21 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v21 + 16LL))(v21);
    v9 = std::make_shared<RdpClientSideTransport::RdpSideTransportCallbacks,RdpClientSideTransport &>(&v21, this);
    std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=((char *)this + 48, v9);
    v10 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
    if ( *((_QWORD *)&v21 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    v20 = 0;
    v21 = 0;
    v11 = *((_QWORD *)this + 7);
    if ( v11 )
    {
      *(_QWORD *)&v21 = *((_QWORD *)this + 6);
      *((_QWORD *)&v21 + 1) = v11;
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 12));
    }
    v12 = CreateRdpSideTransport(&v18, &v21, &v20);
    std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=((char *)this + 32, v12);
    v13 = (volatile signed __int32 *)*((_QWORD *)&v18 + 1);
    if ( *((_QWORD *)&v18 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v18 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    v21 = 0;
    if ( *((_QWORD *)this + 4) )
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v21);
      if ( (_QWORD)v21 && *(_BYTE *)(v21 + 128) )
      {
        v18 = 0;
        v19 = 0;
        std::string::_Construct<1,char const *>(&v18, "RdpClientSideTransport::InitializeInstance: hr=0x%x", 51);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,long>(
          &v21,
          "RDPNANO",
          &v18,
          0);
        std::string::_Tidy_deallocate(&v18);
      }
      v16 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
      if ( *((_QWORD *)&v21 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        }
      }
      return 0;
    }
    else
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v21);
      if ( (_QWORD)v21 && *(_BYTE *)(v21 + 128) )
      {
        v18 = 0;
        v19 = 0;
        std::string::_Construct<1,char const *>(
          &v18,
          "Failed to create RdpSideTransport.\n    %s(%d): %s()",
          (const char *)0x33,
          v14,
          v17);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)&v21,
          (unsigned int)"RDPNANO",
          (unsigned int)&v18,
          (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\RdpClientSideTransport.cpp",
          66,
          (__int64)"RdpClientSideTransport::InitializeInstance");
        std::string::_Tidy_deallocate(&v18);
      }
      v15 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
      if ( *((_QWORD *)&v21 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      (*(void (__fastcall **)(RdpClientSideTransport *))(*(_QWORD *)this + 40LL))(this);
      return 2147500037LL;
    }
  }
  else
  {
    v21 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v21);
    if ( (_QWORD)v21 && *(_BYTE *)(v21 + 128) )
    {
      v18 = 0;
      v19 = 0;
      std::string::_Construct<1,char const *>(
        &v18,
        "Invalid pointer callbacks.\n    %s(%d): %s()",
        (const char *)0x2B,
        v3,
        v17);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
        (unsigned int)&v21,
        (unsigned int)"RDPNANO",
        (unsigned int)&v18,
        (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\RdpClientSideTransport.cpp",
        52,
        (__int64)"RdpClientSideTransport::InitializeInstance");
      std::string::_Tidy_deallocate(&v18);
    }
    v4 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
    if ( *((_QWORD *)&v21 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
    (*(void (__fastcall **)(RdpClientSideTransport *))(*(_QWORD *)this + 40LL))(this);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180046b70  mov     [rsp-18h+arg_10], rbx
0x180046b75  mov     [rsp-18h+arg_18], rsi
0x180046b7a  push    rbp
0x180046b7b  push    rdi
0x180046b7c  push    r14
0x180046b7e  mov     rbp, rsp
0x180046b81  mov     eax, 80h
0x180046b86  call    _alloca_probe
0x180046b8b  sub     rsp, rax
0x180046b8e  mov     rax, cs:__security_cookie
0x180046b95  xor     rax, rsp
0x180046b98  mov     [rbp+var_10], rax
0x180046b9c  mov     rsi, rcx
0x180046b9f  mov     qword ptr [rbp+var_30], rdx
0x180046ba3  test    rdx, rdx
0x180046ba6  jnz     loc_180046C86
0x180046bac  xorps   xmm0, xmm0
0x180046baf  movups  [rbp+var_20], xmm0
0x180046bb3  lea     rcx, [rbp+var_20]
0x180046bb7  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x180046bbc  mov     rax, qword ptr [rbp+var_20]
0x180046bc0  test    rax, rax
0x180046bc3  jz      short loc_180046C2B
0x180046bc5  cmp     byte ptr [rax+80h], 0
0x180046bcc  jz      short loc_180046C2B
0x180046bce  xorps   xmm0, xmm0
0x180046bd1  movups  [rbp+var_50], xmm0
0x180046bd5  xorps   xmm1, xmm1
0x180046bd8  movdqu  [rbp+var_40], xmm1
0x180046bdd  mov     r8d, 2Bh ; '+'
0x180046be3  lea     rdx, aInvalidPointer_0; "Invalid pointer callbacks.\n    %s(%d):"...
0x180046bea  lea     rcx, [rbp+var_50]
0x180046bee  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180046bf3  lea     rax, aRdpclientsidet_7; "RdpClientSideTransport::InitializeInsta"...
0x180046bfa  mov     [rsp+80h+var_58], rax
0x180046bff  mov     dword ptr [rsp+80h+var_60], 34h ; '4'
0x180046c07  lea     r9, aCW1SRdpnanodll_14; "C:\\__w\\1\\s\\rdpnanodll\\RdpClientSid"...
0x180046c0e  lea     r8, [rbp+var_50]
0x180046c12  lea     rdx, aRdpnano; "RDPNANO"
0x180046c19  lea     rcx, [rbp+var_20]
0x180046c1d  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,char const *,int,char const *)
0x180046c22  lea     rcx, [rbp+var_50]
0x180046c26  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180046c2b  mov     rdi, qword ptr [rbp+var_20+8]
0x180046c2f  test    rdi, rdi
0x180046c32  jz      short loc_180046C6C
0x180046c34  or      ebx, 0FFFFFFFFh
0x180046c37  mov     eax, ebx
0x180046c39  lock xadd [rdi+8], eax
0x180046c3e  add     eax, ebx
0x180046c40  jnz     short loc_180046C6C
0x180046c42  mov     rax, [rdi]
0x180046c45  mov     rcx, rdi
0x180046c48  mov     rax, [rax]
0x180046c4b  call    cs:__guard_dispatch_icall_fptr
0x180046c51  mov     eax, ebx
0x180046c53  lock xadd [rdi+0Ch], eax
0x180046c58  add     eax, ebx
0x180046c5a  jnz     short loc_180046C6C
0x180046c5c  mov     rax, [rdi]
0x180046c5f  mov     rcx, rdi
0x180046c62  mov     rax, [rax+8]
0x180046c66  call    cs:__guard_dispatch_icall_fptr
0x180046c6c  mov     rax, [rsi]
0x180046c6f  mov     rcx, rsi
0x180046c72  mov     rax, [rax+28h]
0x180046c76  call    cs:__guard_dispatch_icall_fptr
0x180046c7c  mov     eax, 80070057h
0x180046c81  jmp     loc_180046F2A
0x180046c86  lea     rdx, [rbp+var_30]
0x180046c8a  lea     rcx, [rbp+var_20]
0x180046c8e  call    ??$com_weak_query@AEAPEAUIVirtualChannelCallbacks@@@wil@@YA?AV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@0@AEAPEAUIVirtualChannelCallbacks@@@Z; wil::com_weak_query<IVirtualChannelCallbacks * &>(IVirtualChannelCallbacks * &)
0x180046c93  mov     rdx, [rax]
0x180046c96  mov     qword ptr [rax], 0
0x180046c9d  mov     rcx, [rsi+18h]
0x180046ca1  mov     [rsi+18h], rdx
0x180046ca5  test    rcx, rcx
0x180046ca8  jz      short loc_180046CB8
0x180046caa  mov     rax, [rcx]
0x180046cad  mov     rax, [rax+10h]
0x180046cb1  call    cs:__guard_dispatch_icall_fptr
0x180046cb7  nop
0x180046cb8  mov     rcx, qword ptr [rbp+var_20]
0x180046cbc  test    rcx, rcx
0x180046cbf  jz      short loc_180046CCF
0x180046cc1  mov     rax, [rcx]
0x180046cc4  mov     rax, [rax+10h]
0x180046cc8  call    cs:__guard_dispatch_icall_fptr
0x180046cce  nop
0x180046ccf  mov     rdx, rsi
0x180046cd2  lea     rcx, [rbp+var_20]
0x180046cd6  call    ??$make_shared@VRdpSideTransportCallbacks@RdpClientSideTransport@@AEAV2@@std@@YA?AV?$shared_ptr@VRdpSideTransportCallbacks@RdpClientSideTransport@@@0@AEAVRdpClientSideTransport@@@Z; std::make_shared<RdpClientSideTransport::RdpSideTransportCallbacks,RdpClientSideTransport &>(RdpClientSideTransport &)
0x180046cdb  mov     rdx, rax
0x180046cde  lea     rcx, [rsi+30h]
0x180046ce2  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x180046ce7  or      ebx, 0FFFFFFFFh
0x180046cea  mov     rdi, qword ptr [rbp+var_20+8]
0x180046cee  test    rdi, rdi
0x180046cf1  jz      short loc_180046D28
0x180046cf3  mov     eax, ebx
0x180046cf5  lock xadd [rdi+8], eax
0x180046cfa  add     eax, ebx
0x180046cfc  jnz     short loc_180046D28
0x180046cfe  mov     rax, [rdi]
0x180046d01  mov     rcx, rdi
0x180046d04  mov     rax, [rax]
0x180046d07  call    cs:__guard_dispatch_icall_fptr
0x180046d0d  mov     eax, ebx
0x180046d0f  lock xadd [rdi+0Ch], eax
0x180046d14  add     eax, ebx
0x180046d16  jnz     short loc_180046D28
0x180046d18  mov     rax, [rdi]
0x180046d1b  mov     rcx, rdi
0x180046d1e  mov     rax, [rax+8]
0x180046d22  call    cs:__guard_dispatch_icall_fptr
0x180046d28  xorps   xmm0, xmm0
0x180046d2b  movdqu  [rbp+var_30], xmm0
0x180046d30  xorps   xmm1, xmm1
0x180046d33  movdqu  [rbp+var_20], xmm1
0x180046d38  mov     rcx, [rsi+38h]
0x180046d3c  test    rcx, rcx
0x180046d3f  jz      short loc_180046D51
0x180046d41  mov     rax, [rsi+30h]
0x180046d45  mov     qword ptr [rbp+var_20], rax
0x180046d49  mov     qword ptr [rbp+var_20+8], rcx
0x180046d4d  lock inc dword ptr [rcx+0Ch]
0x180046d51  lea     r8, [rbp+var_30]
0x180046d55  lea     rdx, [rbp+var_20]
0x180046d59  lea     rcx, [rbp+var_50]
0x180046d5d  call    ?CreateRdpSideTransport@@YA?AV?$shared_ptr@VIRdpSideTransport@@@std@@V?$weak_ptr@VIRdpSideTransportCallbacks@@@2@V?$weak_ptr@VIRdpSideTransportInstrumentationCallbacks@@@2@@Z; CreateRdpSideTransport(std::weak_ptr<IRdpSideTransportCallbacks>,std::weak_ptr<IRdpSideTransportInstrumentationCallbacks>)
0x180046d62  mov     rdx, rax
0x180046d65  lea     rcx, [rsi+20h]
0x180046d69  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x180046d6e  mov     rdi, qword ptr [rbp+var_50+8]
0x180046d72  test    rdi, rdi
0x180046d75  jz      short loc_180046DAC
0x180046d77  mov     eax, ebx
0x180046d79  lock xadd [rdi+8], eax
0x180046d7e  add     eax, ebx
0x180046d80  jnz     short loc_180046DAC
0x180046d82  mov     rax, [rdi]
0x180046d85  mov     rcx, rdi
0x180046d88  mov     rax, [rax]
0x180046d8b  call    cs:__guard_dispatch_icall_fptr
0x180046d91  mov     eax, ebx
0x180046d93  lock xadd [rdi+0Ch], eax
0x180046d98  add     eax, ebx
0x180046d9a  jnz     short loc_180046DAC
0x180046d9c  mov     rax, [rdi]
0x180046d9f  mov     rcx, rdi
0x180046da2  mov     rax, [rax+8]
0x180046da6  call    cs:__guard_dispatch_icall_fptr
0x180046dac  xorps   xmm0, xmm0
0x180046daf  lea     rcx, [rbp+var_20]
0x180046db3  movups  [rbp+var_20], xmm0
0x180046db7  cmp     qword ptr [rsi+20h], 0
0x180046dbc  jnz     loc_180046E8E
0x180046dc2  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x180046dc7  mov     rax, qword ptr [rbp+var_20]
0x180046dcb  test    rax, rax
0x180046dce  jz      short loc_180046E36
0x180046dd0  cmp     byte ptr [rax+80h], 0
0x180046dd7  jz      short loc_180046E36
0x180046dd9  xorps   xmm0, xmm0
0x180046ddc  movups  [rbp+var_50], xmm0
0x180046de0  xorps   xmm1, xmm1
0x180046de3  movdqu  [rbp+var_40], xmm1
0x180046de8  mov     r8d, 33h ; '3'
0x180046dee  lea     rdx, aFailedToCreate_6; "Failed to create RdpSideTransport.\n   "...
0x180046df5  lea     rcx, [rbp+var_50]
0x180046df9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180046dfe  lea     rax, aRdpclientsidet_7; "RdpClientSideTransport::InitializeInsta"...
0x180046e05  mov     [rsp+80h+var_58], rax
0x180046e0a  mov     dword ptr [rsp+80h+var_60], 42h ; 'B'
0x180046e12  lea     r9, aCW1SRdpnanodll_14; "C:\\__w\\1\\s\\rdpnanodll\\RdpClientSid"...
0x180046e19  lea     r8, [rbp+var_50]
0x180046e1d  lea     rdx, aRdpnano; "RDPNANO"
0x180046e24  lea     rcx, [rbp+var_20]
0x180046e28  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,char const *,int,char const *)
0x180046e2d  lea     rcx, [rbp+var_50]
0x180046e31  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180046e36  mov     rdi, qword ptr [rbp+var_20+8]
0x180046e3a  test    rdi, rdi
0x180046e3d  jz      short loc_180046E74
0x180046e3f  mov     eax, ebx
0x180046e41  lock xadd [rdi+8], eax
0x180046e46  add     eax, ebx
0x180046e48  jnz     short loc_180046E74
0x180046e4a  mov     rax, [rdi]
0x180046e4d  mov     rcx, rdi
0x180046e50  mov     rax, [rax]
0x180046e53  call    cs:__guard_dispatch_icall_fptr
0x180046e59  mov     eax, ebx
0x180046e5b  lock xadd [rdi+0Ch], eax
0x180046e60  add     eax, ebx
0x180046e62  jnz     short loc_180046E74
0x180046e64  mov     rax, [rdi]
0x180046e67  mov     rcx, rdi
0x180046e6a  mov     rax, [rax+8]
0x180046e6e  call    cs:__guard_dispatch_icall_fptr
0x180046e74  mov     rax, [rsi]
0x180046e77  mov     rcx, rsi
0x180046e7a  mov     rax, [rax+28h]
0x180046e7e  call    cs:__guard_dispatch_icall_fptr
0x180046e84  mov     eax, 80004005h
0x180046e89  jmp     loc_180046F2A
0x180046e8e  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180046e93  mov     rax, qword ptr [rbp+var_20]
0x180046e97  test    rax, rax
0x180046e9a  jz      short loc_180046EEA
0x180046e9c  cmp     byte ptr [rax+80h], 0
0x180046ea3  jz      short loc_180046EEA
0x180046ea5  xorps   xmm0, xmm0
0x180046ea8  movups  [rbp+var_50], xmm0
0x180046eac  xorps   xmm1, xmm1
0x180046eaf  movdqu  [rbp+var_40], xmm1
0x180046eb4  mov     r8d, 33h ; '3'
0x180046eba  lea     rdx, aRdpclientsidet_2; "RdpClientSideTransport::InitializeInsta"...
0x180046ec1  lea     rcx, [rbp+var_50]
0x180046ec5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180046eca  xor     r9d, r9d
0x180046ecd  lea     r8, [rbp+var_50]
0x180046ed1  lea     rdx, aRdpnano; "RDPNANO"
0x180046ed8  lea     rcx, [rbp+var_20]
0x180046edc  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@J@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@J@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,long>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,long)
0x180046ee1  lea     rcx, [rbp+var_50]
0x180046ee5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180046eea  mov     rdi, qword ptr [rbp+var_20+8]
0x180046eee  test    rdi, rdi
0x180046ef1  jz      short loc_180046F28
0x180046ef3  mov     eax, ebx
0x180046ef5  lock xadd [rdi+8], eax
0x180046efa  add     eax, ebx
0x180046efc  jnz     short loc_180046F28
0x180046efe  mov     rax, [rdi]
0x180046f01  mov     rcx, rdi
0x180046f04  mov     rax, [rax]
0x180046f07  call    cs:__guard_dispatch_icall_fptr
0x180046f0d  mov     eax, ebx
0x180046f0f  lock xadd [rdi+0Ch], eax
0x180046f14  add     eax, ebx
0x180046f16  jnz     short loc_180046F28
0x180046f18  mov     rax, [rdi]
0x180046f1b  mov     rcx, rdi
0x180046f1e  mov     rax, [rax+8]
0x180046f22  call    cs:__guard_dispatch_icall_fptr
0x180046f28  xor     eax, eax
0x180046f2a  mov     rcx, [rbp+var_10]
0x180046f2e  xor     rcx, rsp; StackCookie
0x180046f31  call    __security_check_cookie
0x180046f36  lea     r11, [rsp+80h+var_s0]
0x180046f3e  mov     rbx, [r11+30h]
0x180046f42  mov     rsi, [r11+38h]
0x180046f46  mov     rsp, r11
0x180046f49  pop     r14
0x180046f4b  pop     rdi
0x180046f4c  pop     rbp
0x180046f4d  retn
```
