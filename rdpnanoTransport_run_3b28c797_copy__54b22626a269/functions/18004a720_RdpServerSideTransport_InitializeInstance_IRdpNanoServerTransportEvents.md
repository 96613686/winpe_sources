# RdpServerSideTransport::InitializeInstance(IRdpNanoServerTransportEvents *)

- ea: `0x18004a720`
- end: `0x18004ab56`
- name: `?InitializeInstance@RdpServerSideTransport@@UEAAJPEAUIRdpNanoServerTransportEvents@@@Z`
- size: `1078`
- prototype: `__int64 __fastcall(RdpServerSideTransport *__hidden this, struct IRdpNanoServerTransportEvents *)`
- caller_count: `0`
- callee_count: `15`
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
- `0x1800491b4`
- `0x180049224`
- `0x18004a720`
- `0x1800e3ed8`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x18004a9f6`: `Failed to create RdpSideTransport.\n    %s(%d): %s()`
- `0x18004a7a3`: `RdpServerSideTransport::InitializeInstance`
- `0x18004aa06`: `RdpServerSideTransport::InitializeInstance`
- `0x18004a7b7`: `C:\__w\1\s\rdpnanodll\RdpServerSideTransport.cpp`
- `0x18004aa1a`: `C:\__w\1\s\rdpnanodll\RdpServerSideTransport.cpp`
- `0x18004aac2`: `RdpServerSideTransport::InitializeInstance: hr=0x%x`

## pseudocode

```c
__int64 __fastcall RdpServerSideTransport::InitializeInstance(
        RdpServerSideTransport *this,
        struct IRdpNanoServerTransportEvents *a2)
{
  int v3; // r9d
  volatile signed __int32 *v4; // rdi
  __int64 *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rax
  volatile signed __int32 *v10; // rdi
  __int64 v11; // rax
  volatile signed __int32 *v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // rax
  volatile signed __int32 *v15; // rdi
  int v16; // r9d
  volatile signed __int32 *v17; // rdi
  volatile signed __int32 *v18; // rdi
  const char *v19; // [rsp+20h] [rbp-60h]
  __int128 v20; // [rsp+30h] [rbp-50h] BYREF
  __int128 v21; // [rsp+40h] [rbp-40h]
  __int128 v22; // [rsp+50h] [rbp-30h] BYREF
  __int128 v23; // [rsp+60h] [rbp-20h] BYREF

  *(_QWORD *)&v22 = a2;
  if ( a2 )
  {
    v6 = (__int64 *)wil::com_weak_query<IVirtualChannelCallbacks * &>(&v23, &v22);
    v7 = *v6;
    *v6 = 0;
    v8 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = v7;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    if ( (_QWORD)v23 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v23 + 16LL))(v23);
    v9 = std::make_shared<RdpServerSideTransport::RdpSideTransportCallbacks,RdpServerSideTransport &>(&v23, this);
    std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=((char *)this + 48, v9);
    v10 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
    if ( *((_QWORD *)&v23 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v23 + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( !_InterlockedDecrement(v10 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    v11 = std::make_shared<RdpServerSideTransportReadProcessor,std::shared_ptr<RdpServerSideTransport::RdpSideTransportCallbacks> &>(
            &v23,
            (char *)this + 48);
    std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=((char *)this + 64, v11);
    v12 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
    if ( *((_QWORD *)&v23 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v23 + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( !_InterlockedDecrement(v12 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
    v22 = 0;
    v23 = 0;
    v13 = *((_QWORD *)this + 7);
    if ( v13 )
    {
      *(_QWORD *)&v23 = *((_QWORD *)this + 6);
      *((_QWORD *)&v23 + 1) = v13;
      _InterlockedIncrement((volatile signed __int32 *)(v13 + 12));
    }
    v14 = CreateRdpSideTransport(&v20, &v23, &v22);
    std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=((char *)this + 32, v14);
    v15 = (volatile signed __int32 *)*((_QWORD *)&v20 + 1);
    if ( *((_QWORD *)&v20 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v20 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    v23 = 0;
    if ( *((_QWORD *)this + 4) )
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v23);
      if ( (_QWORD)v23 && *(_BYTE *)(v23 + 128) )
      {
        v20 = 0;
        v21 = 0;
        std::string::_Construct<1,char const *>(&v20, "RdpServerSideTransport::InitializeInstance: hr=0x%x", 51);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,long>(
          &v23,
          "RDPNANO",
          &v20,
          0);
        std::string::_Tidy_deallocate(&v20);
      }
      v18 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
      if ( *((_QWORD *)&v23 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v23 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
      return 0;
    }
    else
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v23);
      if ( (_QWORD)v23 && *(_BYTE *)(v23 + 128) )
      {
        v20 = 0;
        v21 = 0;
        std::string::_Construct<1,char const *>(
          &v20,
          "Failed to create RdpSideTransport.\n    %s(%d): %s()",
          (const char *)0x33,
          v16,
          v19);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)&v23,
          (unsigned int)"RDPNANO",
          (unsigned int)&v20,
          (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\RdpServerSideTransport.cpp",
          71,
          (__int64)"RdpServerSideTransport::InitializeInstance");
        std::string::_Tidy_deallocate(&v20);
      }
      v17 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
      if ( *((_QWORD *)&v23 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v23 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
          if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        }
      }
      (*(void (__fastcall **)(RdpServerSideTransport *))(*(_QWORD *)this + 32LL))(this);
      return 2147500037LL;
    }
  }
  else
  {
    v23 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v23);
    if ( (_QWORD)v23 && *(_BYTE *)(v23 + 128) )
    {
      v20 = 0;
      v21 = 0;
      std::string::_Construct<1,char const *>(
        &v20,
        "Invalid pointer callbacks.\n    %s(%d): %s()",
        (const char *)0x2B,
        v3,
        v19);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
        (unsigned int)&v23,
        (unsigned int)"RDPNANO",
        (unsigned int)&v20,
        (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\RdpServerSideTransport.cpp",
        55,
        (__int64)"RdpServerSideTransport::InitializeInstance");
      std::string::_Tidy_deallocate(&v20);
    }
    v4 = (volatile signed __int32 *)*((_QWORD *)&v23 + 1);
    if ( *((_QWORD *)&v23 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v23 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
    (*(void (__fastcall **)(RdpServerSideTransport *))(*(_QWORD *)this + 32LL))(this);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18004a720  mov     [rsp-18h+arg_10], rbx
0x18004a725  mov     [rsp-18h+arg_18], rsi
0x18004a72a  push    rbp
0x18004a72b  push    rdi
0x18004a72c  push    r14
0x18004a72e  mov     rbp, rsp
0x18004a731  mov     eax, 80h
0x18004a736  call    _alloca_probe
0x18004a73b  sub     rsp, rax
0x18004a73e  mov     rax, cs:__security_cookie
0x18004a745  xor     rax, rsp
0x18004a748  mov     [rbp+var_10], rax
0x18004a74c  mov     rsi, rcx
0x18004a74f  mov     qword ptr [rbp+var_30], rdx
0x18004a753  test    rdx, rdx
0x18004a756  jnz     loc_18004A836
0x18004a75c  xorps   xmm0, xmm0
0x18004a75f  movups  [rbp+var_20], xmm0
0x18004a763  lea     rcx, [rbp+var_20]
0x18004a767  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x18004a76c  mov     rax, qword ptr [rbp+var_20]
0x18004a770  test    rax, rax
0x18004a773  jz      short loc_18004A7DB
0x18004a775  cmp     byte ptr [rax+80h], 0
0x18004a77c  jz      short loc_18004A7DB
0x18004a77e  xorps   xmm0, xmm0
0x18004a781  movups  [rbp+var_50], xmm0
0x18004a785  xorps   xmm1, xmm1
0x18004a788  movdqu  [rbp+var_40], xmm1
0x18004a78d  mov     r8d, 2Bh ; '+'
0x18004a793  lea     rdx, aInvalidPointer_0; "Invalid pointer callbacks.\n    %s(%d):"...
0x18004a79a  lea     rcx, [rbp+var_50]
0x18004a79e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18004a7a3  lea     rax, aRdpserversidet_8; "RdpServerSideTransport::InitializeInsta"...
0x18004a7aa  mov     [rsp+80h+var_58], rax
0x18004a7af  mov     dword ptr [rsp+80h+var_60], 37h ; '7'
0x18004a7b7  lea     r9, aCW1SRdpnanodll_2; "C:\\__w\\1\\s\\rdpnanodll\\RdpServerSid"...
0x18004a7be  lea     r8, [rbp+var_50]
0x18004a7c2  lea     rdx, aRdpnano; "RDPNANO"
0x18004a7c9  lea     rcx, [rbp+var_20]
0x18004a7cd  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,char const *,int,char const *)
0x18004a7d2  lea     rcx, [rbp+var_50]
0x18004a7d6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004a7db  mov     rdi, qword ptr [rbp+var_20+8]
0x18004a7df  test    rdi, rdi
0x18004a7e2  jz      short loc_18004A81C
0x18004a7e4  or      ebx, 0FFFFFFFFh
0x18004a7e7  mov     eax, ebx
0x18004a7e9  lock xadd [rdi+8], eax
0x18004a7ee  add     eax, ebx
0x18004a7f0  jnz     short loc_18004A81C
0x18004a7f2  mov     rax, [rdi]
0x18004a7f5  mov     rcx, rdi
0x18004a7f8  mov     rax, [rax]
0x18004a7fb  call    cs:__guard_dispatch_icall_fptr
0x18004a801  mov     eax, ebx
0x18004a803  lock xadd [rdi+0Ch], eax
0x18004a808  add     eax, ebx
0x18004a80a  jnz     short loc_18004A81C
0x18004a80c  mov     rax, [rdi]
0x18004a80f  mov     rcx, rdi
0x18004a812  mov     rax, [rax+8]
0x18004a816  call    cs:__guard_dispatch_icall_fptr
0x18004a81c  mov     rax, [rsi]
0x18004a81f  mov     rcx, rsi
0x18004a822  mov     rax, [rax+20h]
0x18004a826  call    cs:__guard_dispatch_icall_fptr
0x18004a82c  mov     eax, 80070057h
0x18004a831  jmp     loc_18004AB32
0x18004a836  lea     rdx, [rbp+var_30]
0x18004a83a  lea     rcx, [rbp+var_20]
0x18004a83e  call    ??$com_weak_query@AEAPEAUIVirtualChannelCallbacks@@@wil@@YA?AV?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@0@AEAPEAUIVirtualChannelCallbacks@@@Z; wil::com_weak_query<IVirtualChannelCallbacks * &>(IVirtualChannelCallbacks * &)
0x18004a843  mov     rdx, [rax]
0x18004a846  mov     qword ptr [rax], 0
0x18004a84d  mov     rcx, [rsi+18h]
0x18004a851  mov     [rsi+18h], rdx
0x18004a855  test    rcx, rcx
0x18004a858  jz      short loc_18004A868
0x18004a85a  mov     rax, [rcx]
0x18004a85d  mov     rax, [rax+10h]
0x18004a861  call    cs:__guard_dispatch_icall_fptr
0x18004a867  nop
0x18004a868  mov     rcx, qword ptr [rbp+var_20]
0x18004a86c  test    rcx, rcx
0x18004a86f  jz      short loc_18004A87F
0x18004a871  mov     rax, [rcx]
0x18004a874  mov     rax, [rax+10h]
0x18004a878  call    cs:__guard_dispatch_icall_fptr
0x18004a87e  nop
0x18004a87f  lea     r14, [rsi+30h]
0x18004a883  mov     rdx, rsi
0x18004a886  lea     rcx, [rbp+var_20]
0x18004a88a  call    ??$make_shared@VRdpSideTransportCallbacks@RdpServerSideTransport@@AEAV2@@std@@YA?AV?$shared_ptr@VRdpSideTransportCallbacks@RdpServerSideTransport@@@0@AEAVRdpServerSideTransport@@@Z; std::make_shared<RdpServerSideTransport::RdpSideTransportCallbacks,RdpServerSideTransport &>(RdpServerSideTransport &)
0x18004a88f  mov     rdx, rax
0x18004a892  mov     rcx, r14
0x18004a895  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x18004a89a  or      ebx, 0FFFFFFFFh
0x18004a89d  mov     rdi, qword ptr [rbp+var_20+8]
0x18004a8a1  test    rdi, rdi
0x18004a8a4  jz      short loc_18004A8DB
0x18004a8a6  mov     eax, ebx
0x18004a8a8  lock xadd [rdi+8], eax
0x18004a8ad  add     eax, ebx
0x18004a8af  jnz     short loc_18004A8DB
0x18004a8b1  mov     rax, [rdi]
0x18004a8b4  mov     rcx, rdi
0x18004a8b7  mov     rax, [rax]
0x18004a8ba  call    cs:__guard_dispatch_icall_fptr
0x18004a8c0  mov     eax, ebx
0x18004a8c2  lock xadd [rdi+0Ch], eax
0x18004a8c7  add     eax, ebx
0x18004a8c9  jnz     short loc_18004A8DB
0x18004a8cb  mov     rax, [rdi]
0x18004a8ce  mov     rcx, rdi
0x18004a8d1  mov     rax, [rax+8]
0x18004a8d5  call    cs:__guard_dispatch_icall_fptr
0x18004a8db  mov     rdx, r14
0x18004a8de  lea     rcx, [rbp+var_20]
0x18004a8e2  call    ??$make_shared@VRdpServerSideTransportReadProcessor@@AEAV?$shared_ptr@VRdpSideTransportCallbacks@RdpServerSideTransport@@@std@@@std@@YA?AV?$shared_ptr@VRdpServerSideTransportReadProcessor@@@0@AEAV?$shared_ptr@VRdpSideTransportCallbacks@RdpServerSideTransport@@@0@@Z; std::make_shared<RdpServerSideTransportReadProcessor,std::shared_ptr<RdpServerSideTransport::RdpSideTransportCallbacks> &>(std::shared_ptr<RdpServerSideTransport::RdpSideTransportCallbacks> &)
0x18004a8e7  mov     rdx, rax
0x18004a8ea  lea     rcx, [rsi+40h]
0x18004a8ee  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x18004a8f3  mov     rdi, qword ptr [rbp+var_20+8]
0x18004a8f7  test    rdi, rdi
0x18004a8fa  jz      short loc_18004A931
0x18004a8fc  mov     eax, ebx
0x18004a8fe  lock xadd [rdi+8], eax
0x18004a903  add     eax, ebx
0x18004a905  jnz     short loc_18004A931
0x18004a907  mov     rax, [rdi]
0x18004a90a  mov     rcx, rdi
0x18004a90d  mov     rax, [rax]
0x18004a910  call    cs:__guard_dispatch_icall_fptr
0x18004a916  mov     eax, ebx
0x18004a918  lock xadd [rdi+0Ch], eax
0x18004a91d  add     eax, ebx
0x18004a91f  jnz     short loc_18004A931
0x18004a921  mov     rax, [rdi]
0x18004a924  mov     rcx, rdi
0x18004a927  mov     rax, [rax+8]
0x18004a92b  call    cs:__guard_dispatch_icall_fptr
0x18004a931  xorps   xmm0, xmm0
0x18004a934  movdqu  [rbp+var_30], xmm0
0x18004a939  xorps   xmm1, xmm1
0x18004a93c  movdqu  [rbp+var_20], xmm1
0x18004a941  mov     rcx, [r14+8]
0x18004a945  test    rcx, rcx
0x18004a948  jz      short loc_18004A959
0x18004a94a  mov     rax, [r14]
0x18004a94d  mov     qword ptr [rbp+var_20], rax
0x18004a951  mov     qword ptr [rbp+var_20+8], rcx
0x18004a955  lock inc dword ptr [rcx+0Ch]
0x18004a959  lea     r8, [rbp+var_30]
0x18004a95d  lea     rdx, [rbp+var_20]
0x18004a961  lea     rcx, [rbp+var_50]
0x18004a965  call    ?CreateRdpSideTransport@@YA?AV?$shared_ptr@VIRdpSideTransport@@@std@@V?$weak_ptr@VIRdpSideTransportCallbacks@@@2@V?$weak_ptr@VIRdpSideTransportInstrumentationCallbacks@@@2@@Z; CreateRdpSideTransport(std::weak_ptr<IRdpSideTransportCallbacks>,std::weak_ptr<IRdpSideTransportInstrumentationCallbacks>)
0x18004a96a  mov     rdx, rax
0x18004a96d  lea     rcx, [rsi+20h]
0x18004a971  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x18004a976  mov     rdi, qword ptr [rbp+var_50+8]
0x18004a97a  test    rdi, rdi
0x18004a97d  jz      short loc_18004A9B4
0x18004a97f  mov     eax, ebx
0x18004a981  lock xadd [rdi+8], eax
0x18004a986  add     eax, ebx
0x18004a988  jnz     short loc_18004A9B4
0x18004a98a  mov     rax, [rdi]
0x18004a98d  mov     rcx, rdi
0x18004a990  mov     rax, [rax]
0x18004a993  call    cs:__guard_dispatch_icall_fptr
0x18004a999  mov     eax, ebx
0x18004a99b  lock xadd [rdi+0Ch], eax
0x18004a9a0  add     eax, ebx
0x18004a9a2  jnz     short loc_18004A9B4
0x18004a9a4  mov     rax, [rdi]
0x18004a9a7  mov     rcx, rdi
0x18004a9aa  mov     rax, [rax+8]
0x18004a9ae  call    cs:__guard_dispatch_icall_fptr
0x18004a9b4  xorps   xmm0, xmm0
0x18004a9b7  lea     rcx, [rbp+var_20]
0x18004a9bb  movups  [rbp+var_20], xmm0
0x18004a9bf  cmp     qword ptr [rsi+20h], 0
0x18004a9c4  jnz     loc_18004AA96
0x18004a9ca  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x18004a9cf  mov     rax, qword ptr [rbp+var_20]
0x18004a9d3  test    rax, rax
0x18004a9d6  jz      short loc_18004AA3E
0x18004a9d8  cmp     byte ptr [rax+80h], 0
0x18004a9df  jz      short loc_18004AA3E
0x18004a9e1  xorps   xmm0, xmm0
0x18004a9e4  movups  [rbp+var_50], xmm0
0x18004a9e8  xorps   xmm1, xmm1
0x18004a9eb  movdqu  [rbp+var_40], xmm1
0x18004a9f0  mov     r8d, 33h ; '3'
0x18004a9f6  lea     rdx, aFailedToCreate_6; "Failed to create RdpSideTransport.\n   "...
0x18004a9fd  lea     rcx, [rbp+var_50]
0x18004aa01  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18004aa06  lea     rax, aRdpserversidet_8; "RdpServerSideTransport::InitializeInsta"...
0x18004aa0d  mov     [rsp+80h+var_58], rax
0x18004aa12  mov     dword ptr [rsp+80h+var_60], 47h ; 'G'
0x18004aa1a  lea     r9, aCW1SRdpnanodll_2; "C:\\__w\\1\\s\\rdpnanodll\\RdpServerSid"...
0x18004aa21  lea     r8, [rbp+var_50]
0x18004aa25  lea     rdx, aRdpnano; "RDPNANO"
0x18004aa2c  lea     rcx, [rbp+var_20]
0x18004aa30  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,char const *,int,char const *)
0x18004aa35  lea     rcx, [rbp+var_50]
0x18004aa39  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004aa3e  mov     rdi, qword ptr [rbp+var_20+8]
0x18004aa42  test    rdi, rdi
0x18004aa45  jz      short loc_18004AA7C
0x18004aa47  mov     eax, ebx
0x18004aa49  lock xadd [rdi+8], eax
0x18004aa4e  add     eax, ebx
0x18004aa50  jnz     short loc_18004AA7C
0x18004aa52  mov     rax, [rdi]
0x18004aa55  mov     rcx, rdi
0x18004aa58  mov     rax, [rax]
0x18004aa5b  call    cs:__guard_dispatch_icall_fptr
0x18004aa61  mov     eax, ebx
0x18004aa63  lock xadd [rdi+0Ch], eax
0x18004aa68  add     eax, ebx
0x18004aa6a  jnz     short loc_18004AA7C
0x18004aa6c  mov     rax, [rdi]
0x18004aa6f  mov     rcx, rdi
0x18004aa72  mov     rax, [rax+8]
0x18004aa76  call    cs:__guard_dispatch_icall_fptr
0x18004aa7c  mov     rax, [rsi]
0x18004aa7f  mov     rcx, rsi
0x18004aa82  mov     rax, [rax+20h]
0x18004aa86  call    cs:__guard_dispatch_icall_fptr
0x18004aa8c  mov     eax, 80004005h
0x18004aa91  jmp     loc_18004AB32
0x18004aa96  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18004aa9b  mov     rax, qword ptr [rbp+var_20]
0x18004aa9f  test    rax, rax
0x18004aaa2  jz      short loc_18004AAF2
0x18004aaa4  cmp     byte ptr [rax+80h], 0
0x18004aaab  jz      short loc_18004AAF2
0x18004aaad  xorps   xmm0, xmm0
0x18004aab0  movups  [rbp+var_50], xmm0
0x18004aab4  xorps   xmm1, xmm1
0x18004aab7  movdqu  [rbp+var_40], xmm1
0x18004aabc  mov     r8d, 33h ; '3'
0x18004aac2  lea     rdx, aRdpserversidet_12; "RdpServerSideTransport::InitializeInsta"...
0x18004aac9  lea     rcx, [rbp+var_50]
0x18004aacd  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18004aad2  xor     r9d, r9d
0x18004aad5  lea     r8, [rbp+var_50]
0x18004aad9  lea     rdx, aRdpnano; "RDPNANO"
0x18004aae0  lea     rcx, [rbp+var_20]
0x18004aae4  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@J@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@J@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,long>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,long)
0x18004aae9  lea     rcx, [rbp+var_50]
0x18004aaed  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18004aaf2  mov     rdi, qword ptr [rbp+var_20+8]
0x18004aaf6  test    rdi, rdi
0x18004aaf9  jz      short loc_18004AB30
0x18004aafb  mov     eax, ebx
0x18004aafd  lock xadd [rdi+8], eax
0x18004ab02  add     eax, ebx
0x18004ab04  jnz     short loc_18004AB30
0x18004ab06  mov     rax, [rdi]
0x18004ab09  mov     rcx, rdi
0x18004ab0c  mov     rax, [rax]
0x18004ab0f  call    cs:__guard_dispatch_icall_fptr
0x18004ab15  mov     eax, ebx
0x18004ab17  lock xadd [rdi+0Ch], eax
0x18004ab1c  add     eax, ebx
0x18004ab1e  jnz     short loc_18004AB30
0x18004ab20  mov     rax, [rdi]
0x18004ab23  mov     rcx, rdi
0x18004ab26  mov     rax, [rax+8]
0x18004ab2a  call    cs:__guard_dispatch_icall_fptr
0x18004ab30  xor     eax, eax
0x18004ab32  mov     rcx, [rbp+var_10]
0x18004ab36  xor     rcx, rsp; StackCookie
0x18004ab39  call    __security_check_cookie
0x18004ab3e  lea     r11, [rsp+80h+var_s0]
0x18004ab46  mov     rbx, [r11+30h]
0x18004ab4a  mov     rsi, [r11+38h]
0x18004ab4e  mov     rsp, r11
0x18004ab51  pop     r14
0x18004ab53  pop     rdi
0x18004ab54  pop     rbp
0x18004ab55  retn
```
