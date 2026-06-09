# Microsoft::RdpNano::RawUdpRdpTransportFilter::OnDataReceived(std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::InBuffer> const &)

- ea: `0x18011c740`
- end: `0x18011d9a7`
- name: `?OnDataReceived@RawUdpRdpTransportFilter@RdpNano@Microsoft@@UEAAXAEBV?$shared_ptr@VInBuffer@IAsyncTransport@Dct@Basix@Microsoft@@@std@@@Z`
- size: `4711`
- prototype: ``
- caller_count: `0`
- callee_count: `45`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180010a60`
- `0x180015bb8`
- `0x1800185f4`
- `0x180018674`
- `0x1800187a8`
- `0x180018d1c`
- `0x180018ea4`
- `0x18001902c`
- `0x18001ab4c`
- `0x18001ba50`
- `0x180028820`
- `0x1800325fc`
- `0x18003302c`
- `0x1800334a8`
- `0x18003c308`
- `0x18004569c`
- `0x1800bb210`
- `0x1800de7c0`
- `0x1800ea630`
- `0x18011667c`
- `0x1801168d4`
- `0x1801169b8`
- `0x180116a74`
- `0x180117980`
- `0x180118a9c`
- `0x180118eb0`
- `0x1801192b0`
- `0x18011b254`
- `0x18011c740`
- `0x18011dc0c`
- `0x180120420`
- `0x180120f3c`
- `0x180121f5c`
- `0x1801abb34`
- `0x1801b0ab4`
- `0x1801b3cbc`
- `0x1801b3e10`
- `0x1802e2464`
- `0x1802eb7a4`
- `0x18032f050`
- `0x18032f0b0`
- `0x1803449f0`
- `0x180375c40`
- `0x180376720`

## string_xrefs

- `0x18011cae6`: `Microsoft::Basix::Dct.RawUdpRdpFilter.WriteCallback`
- `0x18011d476`: `Microsoft::Basix::Dct.RawUdpRdpFilter.SecurityCookieHash`
- `0x18011cd63`: `First data packet arrived. UDP handshake has completed.`
- `0x18011d531`: `RawUdpFilter FIN packet received and the security hash matches.`
- `0x18011d5ac`: `RawUdpFilter FIN packet received, but security hash does not match. Ignoring this condition and continuing processing this packet.`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall Microsoft::RdpNano::RawUdpRdpTransportFilter::OnDataReceived(
        __int64 a1,
        Microsoft::Basix::Dct::IAsyncTransport::InBuffer **a2)
{
  struct Microsoft::Basix::Instrumentation::ActivityManager *v4; // rax
  __int64 v5; // r9
  unsigned __int8 *v6; // rsi
  unsigned __int64 v7; // r15
  __int64 v8; // r12
  __int64 v9; // rbx
  __int64 v10; // rax
  Microsoft::RdpNano::RawUdpRdpTransportFilter *v11; // r13
  int v12; // r9d
  volatile signed __int32 *v13; // rdi
  __int64 v14; // rax
  volatile signed __int32 *v15; // rdi
  struct Microsoft::Basix::Instrumentation::ActivityManager *v16; // rax
  __int64 result; // rax
  volatile signed __int32 *v18; // rcx
  struct Microsoft::Basix::Instrumentation::ActivityManager *v19; // rax
  unsigned __int64 v20; // r12
  int v21; // r9d
  volatile signed __int32 *v22; // rdi
  volatile signed __int32 *v23; // rsi
  volatile signed __int32 *v24; // rsi
  __int64 v25; // xmm0_8
  __int64 v26; // rdx
  __int64 v27; // rdx
  int v28; // r9d
  volatile signed __int32 *v29; // rsi
  volatile signed __int32 *v30; // rsi
  __int64 v31; // rax
  volatile signed __int32 *v32; // rsi
  unsigned __int64 v33; // r15
  unsigned __int64 v34; // r13
  Microsoft::Basix::Containers::FlexIBuffer *v35; // rax
  Microsoft::Basix::Containers::FlexIBuffer *v36; // rsi
  unsigned __int64 v37; // r8
  char v38; // dl
  char *v39; // rax
  char v40; // r12
  Microsoft::Basix::Dct::IAsyncTransport::InBuffer *v41; // rcx
  __int64 v42; // rax
  __int64 SubBuffer; // rsi
  __int64 v44; // rax
  _BYTE *v45; // rcx
  char v46; // si
  __int64 v47; // rax
  volatile signed __int32 *v48; // rdi
  struct Microsoft::Basix::Instrumentation::ActivityManager *v49; // rax
  Microsoft::Basix::Containers::FlexIBuffer *v50; // rax
  Microsoft::Basix::Containers::FlexIBuffer *v51; // rsi
  unsigned __int64 v52; // r8
  char v53; // dl
  unsigned __int8 *v54; // rax
  int v55; // r12d
  __int64 v56; // rax
  Microsoft::Basix::Containers::FlexIBuffer *v57; // rax
  Microsoft::Basix::Containers::FlexIBuffer *v58; // rsi
  unsigned __int64 v59; // r8
  char v60; // dl
  char *v61; // rax
  char v62; // r15
  __int64 v63; // rax
  __int128 *v64; // rax
  int v65; // eax
  volatile signed __int32 *v66; // rsi
  int v67; // esi
  int v68; // r9d
  volatile signed __int32 *v69; // rdi
  __int64 v70; // rdx
  int v71; // r9d
  volatile signed __int32 *v72; // rdi
  struct Microsoft::Basix::Instrumentation::ActivityManager *v73; // rax
  __int64 v74; // rax
  unsigned __int64 v75; // rdi
  volatile signed __int32 *v76; // rdi
  struct Microsoft::Basix::Instrumentation::ActivityManager *v77; // rax
  int v78; // r9d
  volatile signed __int32 *v79; // rbx
  char *v80; // [rsp+20h] [rbp-148h]
  char *v81; // [rsp+20h] [rbp-148h]
  __int64 v82; // [rsp+38h] [rbp-130h] BYREF
  __int128 v83; // [rsp+40h] [rbp-128h] BYREF
  __int128 v84; // [rsp+50h] [rbp-118h]
  char v85; // [rsp+60h] [rbp-108h]
  __int128 *v86; // [rsp+68h] [rbp-100h]
  __int128 *v87; // [rsp+78h] [rbp-F0h]
  _BYTE v88[56]; // [rsp+80h] [rbp-E8h] BYREF
  _BYTE *v89; // [rsp+B8h] [rbp-B0h]
  __int128 Buf1; // [rsp+C0h] [rbp-A8h] BYREF
  __int128 v91; // [rsp+D0h] [rbp-98h]
  _OWORD Buf2[2]; // [rsp+E0h] [rbp-88h] BYREF
  _OWORD v93[2]; // [rsp+100h] [rbp-68h] BYREF
  _BYTE v94[16]; // [rsp+120h] [rbp-48h] BYREF

  try
  {
    v4 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
    LOBYTE(v5) = 1;
    Microsoft::Basix::Instrumentation::ActivityManager::SetActivityId(v4, v94, a1 + 464, v5);
    v6 = *(unsigned __int8 **)(std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2) + 16);
    v7 = *(_QWORD *)(std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2) + 40);
    *((_QWORD *)Microsoft::Basix::Dct::IAsyncTransport::InBuffer::Descriptor(*a2) + 14) = v7;
    v8 = *(_QWORD *)(std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2) + 40);
    LODWORD(v9) = 8;
    if ( *(_QWORD *)(std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2) + 40) <= 8u )
      v9 = *(_QWORD *)(std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2) + 40);
    v10 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2);
    Microsoft::Basix::Instrumentation::TraceManager::Hexdump<Microsoft::Basix::TraceDebug,unsigned __int64>(
      (unsigned int)"UDPRDPFLTR",
      *(_QWORD *)(v10 + 16),
      v9,
      (unsigned int)"Receive (raw) size: %d, data : ",
      v8);
    v11 = (Microsoft::RdpNano::RawUdpRdpTransportFilter *)(a1 - 1096);
    v82 = a1 - 1096;
    if ( v7 <= *(unsigned int *)(a1 - 1096 + 1204) )
    {
      Buf2[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(Buf2);
      if ( *(_QWORD *)&Buf2[0] && *(_BYTE *)(*(_QWORD *)&Buf2[0] + 128LL) )
      {
        Buf1 = 0;
        v91 = 0;
        std::string::_Construct<1,char const *>(
          &Buf1,
          "UDP raw data received: length must be greater than where the syn byte is\n    %s(%d): %s()",
          (const char *)0x59,
          v12,
          v81);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)Buf2,
          (unsigned int)"RDPNANO",
          (unsigned int)&Buf1,
          (unsigned int)"C:\\__w\\1\\s\\rdnanolib\\rdnano\\RawUdpRdpTransportFilter.cpp",
          246,
          (__int64)"Microsoft::RdpNano::RawUdpRdpTransportFilter::OnDataReceived");
        std::string::_Tidy_deallocate(&Buf1);
      }
      v13 = (volatile signed __int32 *)*((_QWORD *)&Buf2[0] + 1);
      if ( *((_QWORD *)&Buf2[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&Buf2[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
LABEL_32:
      v19 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
      return (*(__int64 (__fastcall **)(struct Microsoft::Basix::Instrumentation::ActivityManager *, __int128 *, _BYTE *))(*(_QWORD *)v19 + 32LL))(
               v19,
               &Buf1,
               v94);
    }
    if ( *(_DWORD *)(a1 + 88) )
    {
      if ( *(_DWORD *)(a1 + 88) == 1 )
      {
        if ( (int)Microsoft::RdpNano::RawUdpRdpTransportFilter::OnSynAckReceived(
                    (Microsoft::RdpNano::RawUdpRdpTransportFilter *)(a1 - 1096),
                    v6,
                    v7) >= 0 )
        {
          _mm_lfence();
          (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 288) + 8LL))(*(_QWORD *)(a1 + 288), 0);
          *(_DWORD *)(a1 + 88) = 3;
          Buf1 = 0;
          *(_QWORD *)&v91 = 0;
          memset(v93, 0, sizeof(v93));
          std::string::_Construct<1,char const *>(v93, "Microsoft::Basix::Dct.RawUdpRdpFilter.WriteCallback", 51);
          _mm_lfence();
          Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(a1 - 1056, &Buf1, v93);
          std::string::_Tidy_deallocate(v93);
          if ( *(_QWORD *)((*(_QWORD *)(v91 + 8)
                          & ((unsigned __int128)-(__int128)(unsigned __int64)(*(_QWORD *)(v91 + 8) + 17LL) >> 64))
                         + 0x18)
            || *(_QWORD *)v91 )
          {
            boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::weak_ptr<Microsoft::Basix::Dct::IAsyncTransport::WriteCompletionCallback>>(
              v91,
              Buf2);
            _mm_lfence();
            *(_QWORD *)(a1 + 248) = *(_QWORD *)&Buf2[0];
            v18 = *(volatile signed __int32 **)(a1 + 256);
            *(_QWORD *)(a1 + 256) = *((_QWORD *)&Buf2[0] + 1);
            if ( v18 )
            {
              if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
            }
          }
          _mm_lfence();
          Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnOpened(
            (Microsoft::Basix::Dct::DCTBaseChannelImplNoProp *)(a1 - 1096),
            0,
            0);
          boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&Buf1);
        }
        goto LABEL_32;
      }
    }
    else if ( *(_BYTE *)(a1 + 84) )
    {
      if ( (int)Microsoft::RdpNano::RawUdpRdpTransportFilter::OnSynReceived(
                  (Microsoft::RdpNano::RawUdpRdpTransportFilter *)(a1 - 1096),
                  v6,
                  v7) >= 0 )
      {
        _mm_lfence();
        *(_DWORD *)(a1 + 88) = 2;
        v14 = Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::ITimerCallback>(
                a1 + *(int *)(*(_QWORD *)(a1 - 1088) + 4LL) - 1088LL,
                &Buf1);
        _mm_lfence();
        Buf2[0] = 0;
        if ( *(_QWORD *)(v14 + 8) )
        {
          _mm_lfence();
          Buf2[0] = *(_OWORD *)v14;
          _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&Buf2[0] + 1) + 12LL));
        }
        v82 = *(unsigned int *)(a1 + 76);
        Microsoft::Basix::Timer::Setup(a1 + 280, &v82, Buf2);
        _mm_lfence();
        v15 = (volatile signed __int32 *)*((_QWORD *)&Buf1 + 1);
        if ( *((_QWORD *)&Buf1 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&Buf1 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
            if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
          }
        }
        Microsoft::RdpNano::RawUdpRdpTransportFilter::SendSynAckPacket(v11);
      }
      v16 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
      return (*(__int64 (__fastcall **)(struct Microsoft::Basix::Instrumentation::ActivityManager *, __int128 *, _BYTE *))(*(_QWORD *)v16 + 32LL))(
               v16,
               &Buf1,
               v94);
    }
    v20 = v6[*(unsigned int *)(a1 + 108)];
    if ( (v20 & 1) != 0 )
    {
      Buf2[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(Buf2);
      if ( *(_QWORD *)&Buf2[0] && *(_BYTE *)(*(_QWORD *)&Buf2[0] + 128LL) )
      {
        Buf1 = 0;
        v91 = 0;
        std::string::_Construct<1,char const *>(
          &Buf1,
          "UDP handshake retransmission packet received. Ignoring the duplicate packet: length = %d, flag=%d",
          97,
          v21);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int,int>(
          (unsigned int)Buf2,
          (unsigned int)"RDPNANO",
          (unsigned int)&Buf1,
          v7,
          v20);
        std::string::_Tidy_deallocate(&Buf1);
      }
      v22 = (volatile signed __int32 *)*((_QWORD *)&Buf2[0] + 1);
      if ( *((_QWORD *)&Buf2[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&Buf2[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
          if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
        }
      }
      goto LABEL_32;
    }
    if ( *((_DWORD *)v11 + 296) == 2 )
    {
      v93[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v93);
      if ( *(_QWORD *)&v93[0] && *(_BYTE *)(*(_QWORD *)&v93[0] + 128LL) )
      {
        Buf1 = 0;
        v91 = 0;
        std::string::_Construct<1,char const *>(&Buf1, "First data packet arrived. UDP handshake has completed.", 55);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
          v93,
          "RDPNANO",
          &Buf1);
        std::string::_Tidy_deallocate(&Buf1);
      }
      v23 = (volatile signed __int32 *)*((_QWORD *)&v93[0] + 1);
      if ( *((_QWORD *)&v93[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v93[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
          if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
        }
      }
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 288) + 8LL))(*(_QWORD *)(a1 + 288), 0);
      *(_DWORD *)(a1 + 88) = 3;
      Buf2[0] = 0;
      Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::RdpNano::RawUdpRdpTransportFilter>(
        a1 + *(int *)(*(_QWORD *)(a1 - 1088) + 4LL) - 1088LL,
        Buf2);
      v24 = (volatile signed __int32 *)*((_QWORD *)&Buf2[0] + 1);
      if ( *((_QWORD *)&Buf2[0] + 1) )
      {
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&Buf2[0] + 1) + 8LL));
        v24 = (volatile signed __int32 *)*((_QWORD *)&Buf2[0] + 1);
      }
      v25 = *(_QWORD *)&Buf2[0];
      v93[0] = Buf2[0];
      v87 = 0;
      if ( (unsigned __int8)std::_Test_callable<_lambda_052e919cc0e5399df76dff3972c0cac1_>(v93) )
      {
        *(_QWORD *)&v83 = &std::_Func_impl_no_alloc<_lambda_fcaa066874a2c745404df506353875eb_,void,>::`vftable';
        *((_QWORD *)&v83 + 1) = v25;
        *(_QWORD *)&v84 = v24;
        v93[0] = 0;
        v87 = &v83;
        v24 = 0;
      }
      v26 = Microsoft::Basix::Instrumentation::ActivityFunction<void>(v88, &v83);
      std::thread::_Start<std::function<void (void)>,>(&Buf1, v26);
      std::thread::join((std::thread *)&Buf1);
      if ( DWORD2(Buf1) )
        terminate();
      if ( v89 )
      {
        LOBYTE(v27) = v89 != v88;
        (*(void (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v89 + 32LL))(v89, v27);
        v89 = 0;
      }
      if ( v24 )
      {
        if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
          if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
        }
      }
      v93[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v93);
      if ( *(_QWORD *)&v93[0] && *(_BYTE *)(*(_QWORD *)&v93[0] + 128LL) )
      {
        Buf1 = 0;
        v91 = 0;
        std::string::_Construct<1,char const *>(
          &Buf1,
          "Proessing first UDP data packet received: length = %d, flag=%d",
          62,
          v28);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int,int>(
          (unsigned int)v93,
          (unsigned int)"RDPNANO",
          (unsigned int)&Buf1,
          v7,
          v20);
        std::string::_Tidy_deallocate(&Buf1);
      }
      v29 = (volatile signed __int32 *)*((_QWORD *)&v93[0] + 1);
      if ( *((_QWORD *)&v93[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v93[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
          if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
        }
      }
      v30 = (volatile signed __int32 *)*((_QWORD *)&Buf2[0] + 1);
      if ( *((_QWORD *)&Buf2[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&Buf2[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
          if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
        }
      }
    }
    v31 = Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::ITimerCallback>(
            a1 + *(int *)(*(_QWORD *)(a1 - 1088) + 4LL) - 1088LL,
            &Buf1);
    Buf2[0] = 0;
    if ( *(_QWORD *)(v31 + 8) )
    {
      Buf2[0] = *(_OWORD *)v31;
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&Buf2[0] + 1) + 12LL));
    }
    *(_QWORD *)&v93[0] = (unsigned __int64)*(unsigned int *)(a1 + 68) >> 2;
    Microsoft::Basix::Timer::Setup(a1 + 280, v93, Buf2);
    v32 = (volatile signed __int32 *)*((_QWORD *)&Buf1 + 1);
    if ( *((_QWORD *)&Buf1 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&Buf1 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
        if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
      }
    }
    *(_QWORD *)(a1 + 96) = *(_QWORD *)std::chrono::steady_clock::now(v93) / 1000000LL;
    v33 = v20;
    v34 = v20 >> 5;
    v35 = (Microsoft::Basix::Containers::FlexIBuffer *)std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2);
    v36 = v35;
    v37 = *((_QWORD *)v35 + 3);
    v38 = v37 >= *((_QWORD *)v35 + 4) || v37 < *((_QWORD *)v35 + 2);
    Microsoft::Basix::Containers::FlexIBuffer::OverflowCheck(
      v35,
      v38,
      v37 - *((_DWORD *)v35 + 4),
      1,
      "C:\\__w\\1\\s\\src\\libbasix\\publicinc\\libbasix/containers/flexibuffer.h",
      0x26Du);
    v39 = (char *)*((_QWORD *)v36 + 3);
    v40 = *v39;
    *((_QWORD *)v36 + 3) = v39 + 1;
    v41 = *a2;
    if ( v34 >= *(unsigned int *)(a1 + 108) )
    {
      v45 = *(_BYTE **)(std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(v41) + 16);
      v45[*(_DWORD *)(a1 + 108) - 1 + 1] = v40;
      *v45 = v33;
    }
    else
    {
      v42 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(v41);
      _mm_lfence();
      SubBuffer = Microsoft::Basix::Containers::FlexIBuffer::GetSubBuffer(v42, &v83, v34);
      v44 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2);
      _mm_lfence();
      Microsoft::Basix::Containers::FlexIBuffer::operator=(v44, SubBuffer);
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v83);
    }
    v46 = *(_BYTE *)(a1 + 4 * ((v33 >> 1) & 0xF) + 180);
    *(_BYTE *)Microsoft::Basix::Dct::IAsyncTransport::InBuffer::Descriptor(*a2) = v46;
    if ( v46 == 106 )
    {
      v47 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2);
      if ( *(_QWORD *)(v47 + 32) - *(_QWORD *)(v47 + 24) < 0x2Au )
      {
        Buf2[0] = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(Buf2);
        if ( *(_QWORD *)&Buf2[0] && *(_BYTE *)(*(_QWORD *)&Buf2[0] + 128LL) )
        {
          Buf1 = 0;
          v91 = 0;
          std::string::_Construct<1,char const *>(
            &Buf1,
            "UDPFinPacket length of buffer is less than expected for Fin payload, ignoring this packet!",
            90);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
            Buf2,
            "RDPNANO",
            &Buf1);
          std::string::_Tidy_deallocate(&Buf1);
        }
        v48 = (volatile signed __int32 *)*((_QWORD *)&Buf2[0] + 1);
        if ( *((_QWORD *)&Buf2[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&Buf2[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
            if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
          }
        }
LABEL_94:
        v49 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
        return (*(__int64 (__fastcall **)(struct Microsoft::Basix::Instrumentation::ActivityManager *, __int128 *, _BYTE *))(*(_QWORD *)v49 + 32LL))(
                 v49,
                 &Buf1,
                 v94);
      }
      v50 = (Microsoft::Basix::Containers::FlexIBuffer *)std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2);
      v51 = v50;
      v52 = *((_QWORD *)v50 + 3);
      v53 = v52 >= *((_QWORD *)v50 + 4) || v52 < *((_QWORD *)v50 + 2);
      Microsoft::Basix::Containers::FlexIBuffer::OverflowCheck(
        v50,
        v53,
        v52 - *((_DWORD *)v50 + 4),
        1,
        "C:\\__w\\1\\s\\src\\libbasix\\publicinc\\libbasix/containers/flexibuffer.h",
        0x26Du);
      v54 = (unsigned __int8 *)*((_QWORD *)v51 + 3);
      v55 = *v54;
      *((_QWORD *)v51 + 3) = v54 + 1;
      *(_QWORD *)&v93[0] = 0;
      v56 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2);
      Microsoft::Basix::Containers::FlexIBuffer::Extract<unsigned __int64>(v56, v93);
      v57 = (Microsoft::Basix::Containers::FlexIBuffer *)std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2);
      v58 = v57;
      v59 = *((_QWORD *)v57 + 3);
      if ( v59 >= *((_QWORD *)v57 + 4) || (v60 = 0, v59 < *((_QWORD *)v57 + 2)) )
        v60 = 1;
      Microsoft::Basix::Containers::FlexIBuffer::OverflowCheck(
        v57,
        v60,
        v59 - *((_DWORD *)v57 + 4),
        1,
        "C:\\__w\\1\\s\\src\\libbasix\\publicinc\\libbasix/containers/flexibuffer.h",
        0x26Du);
      v61 = (char *)*((_QWORD *)v58 + 3);
      v62 = *v61;
      *((_QWORD *)v58 + 3) = v61 + 1;
      Buf1 = 0;
      v91 = 0;
      v63 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2);
      Microsoft::Basix::Containers::FlexIBuffer::Extract<RdpNanoSecurityCookieHash>(v63, &Buf1);
      if ( v62 == 1 )
      {
        v83 = 0;
        v84 = 0;
        std::string::_Construct<1,char const *>(&v83, "Microsoft::Basix::Dct.RawUdpRdpFilter.SecurityCookieHash", 56);
        v85 = 46;
        v64 = &v83;
        if ( *((_QWORD *)&v84 + 1) > 0xFu )
          v64 = (__int128 *)v83;
        v86 = v64;
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<Microsoft::RdpNano::SecurityCookieHash>(
          a1 - 136,
          Buf2,
          &v83);
        std::string::_Tidy_deallocate(&v83);
        v65 = memcmp(&Buf1, Buf2, 0x20u);
        Buf2[0] = 0;
        if ( v65 )
        {
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(Buf2);
          if ( *(_QWORD *)&Buf2[0] && *(_BYTE *)(*(_QWORD *)&Buf2[0] + 128LL) )
          {
            Buf1 = 0;
            v91 = 0;
            std::string::_Construct<1,char const *>(
              &Buf1,
              "RawUdpFilter FIN packet received, but security hash does not match. Ignoring this condition and continuing"
              " processing this packet.",
              130);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
              Buf2,
              "RDPNANO",
              &Buf1);
            std::string::_Tidy_deallocate(&Buf1);
          }
        }
        else
        {
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(Buf2);
          if ( *(_QWORD *)&Buf2[0] && *(_BYTE *)(*(_QWORD *)&Buf2[0] + 128LL) )
          {
            Buf1 = 0;
            v91 = 0;
            std::string::_Construct<1,char const *>(
              &Buf1,
              "RawUdpFilter FIN packet received and the security hash matches.",
              63);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
              Buf2,
              "RDPNANO",
              &Buf1);
            std::string::_Tidy_deallocate(&Buf1);
          }
        }
        v66 = (volatile signed __int32 *)*((_QWORD *)&Buf2[0] + 1);
        if ( *((_QWORD *)&Buf2[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&Buf2[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
            if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
          }
        }
      }
      v67 = v93[0];
      Buf2[0] = 0;
      if ( *(_QWORD *)&v93[0] != *(_QWORD *)(a1 + 112) )
      {
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(Buf2);
        if ( *(_QWORD *)&Buf2[0] && *(_BYTE *)(*(_QWORD *)&Buf2[0] + 128LL) )
        {
          Buf1 = 0;
          v91 = 0;
          std::string::_Construct<1,char const *>(
            &Buf1,
            "RawUdpFilter FIN packet received, but magicWord is incorrect. Dropping the packet: magicWord=0x%llx, FIN flag=%d",
            112,
            v68);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned __int64,int>(
            (unsigned int)Buf2,
            (unsigned int)"RDPNANO",
            (unsigned int)&Buf1,
            v67,
            v62);
          std::string::_Tidy_deallocate(&Buf1);
        }
        v69 = (volatile signed __int32 *)*((_QWORD *)&Buf2[0] + 1);
        if ( *((_QWORD *)&Buf2[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&Buf2[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
            if ( _InterlockedExchangeAdd(v69 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
          }
        }
        goto LABEL_94;
      }
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(Buf2);
      if ( *(_QWORD *)&Buf2[0] && *(_BYTE *)(*(_QWORD *)&Buf2[0] + 128LL) )
      {
        Buf1 = 0;
        v91 = 0;
        std::string::_Construct<1,char const *>(
          &Buf1,
          "RawUdpFilter FIN packet received - version = %d, FIN flag=%d",
          60,
          v71);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int,int>(
          (unsigned int)Buf2,
          (unsigned int)"RDPNANO",
          (unsigned int)&Buf1,
          v55,
          v62);
        std::string::_Tidy_deallocate(&Buf1);
      }
      v72 = (volatile signed __int32 *)*((_QWORD *)&Buf2[0] + 1);
      if ( *((_QWORD *)&Buf2[0] + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&Buf2[0] + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v72)(v72);
          if ( !_InterlockedDecrement(v72 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v72 + 8LL))(v72);
        }
      }
      LOBYTE(v70) = v62;
      Microsoft::RdpNano::RawUdpRdpTransportFilter::OnFinPacketReceived(v82, v70);
      v73 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
      result = (*(__int64 (__fastcall **)(struct Microsoft::Basix::Instrumentation::ActivityManager *, __int128 *, _BYTE *))(*(_QWORD *)v73 + 32LL))(
                 v73,
                 &Buf1,
                 v94);
    }
    else
    {
      if ( v46 == 104 )
      {
        v74 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2);
        v75 = *(_QWORD *)(v74 + 32) - *(_QWORD *)(v74 + 24);
        if ( v75 < 0x3E8 )
        {
          Buf2[0] = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(Buf2);
          if ( *(_QWORD *)&Buf2[0] && *(_BYTE *)(*(_QWORD *)&Buf2[0] + 128LL) )
          {
            Buf1 = 0;
            v91 = 0;
            std::string::_Construct<1,char const *>(&Buf1, "URCPDummyPacket packet received: length = %d", 44);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,int>(
              Buf2,
              "RDPNANO",
              &Buf1,
              (unsigned int)v75);
            std::string::_Tidy_deallocate(&Buf1);
          }
          v76 = (volatile signed __int32 *)*((_QWORD *)&Buf2[0] + 1);
          if ( *((_QWORD *)&Buf2[0] + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&Buf2[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v76)(v76);
              if ( _InterlockedExchangeAdd(v76 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v76 + 8LL))(v76);
            }
          }
        }
      }
      Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnDataReceived(v82, a2);
      v77 = Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager();
      result = (*(__int64 (__fastcall **)(struct Microsoft::Basix::Instrumentation::ActivityManager *, __int128 *, _BYTE *))(*(_QWORD *)v77 + 32LL))(
                 v77,
                 &Buf1,
                 v94);
    }
  }
  catch ( ... )
  {
    Buf2[0] = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(Buf2);
    result = *(_QWORD *)&Buf2[0];
    if ( *(_QWORD *)&Buf2[0] && *(_BYTE *)(*(_QWORD *)&Buf2[0] + 128LL) )
    {
      Buf1 = 0;
      v91 = 0u;
      std::string::_Construct<1,char const *>(
        &Buf1,
        "RawUdpRdpTransportFilter - Dropping a packet due to an exception in decoding.\n    %s(%d): %s()",
        (const char *)0x5E,
        v78,
        v80);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
        (unsigned int)Buf2,
        (unsigned int)"RDPNANO",
        (unsigned int)&Buf1,
        (unsigned int)"C:\\__w\\1\\s\\rdnanolib\\rdnano\\RawUdpRdpTransportFilter.cpp",
        207,
        (__int64)"Microsoft::RdpNano::RawUdpRdpTransportFilter::OnDataReceived");
      result = std::string::_Tidy_deallocate(&Buf1);
    }
    v79 = (volatile signed __int32 *)*((_QWORD *)&Buf2[0] + 1);
    if ( *((_QWORD *)&Buf2[0] + 1) )
    {
      result = (unsigned int)_InterlockedExchangeAdd(
                               (volatile signed __int32 *)(*((_QWORD *)&Buf2[0] + 1) + 8LL),
                               0xFFFFFFFF);
      if ( (_DWORD)result == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v79)(v79);
        result = (unsigned int)_InterlockedExchangeAdd(v79 + 3, 0xFFFFFFFF);
        if ( (_DWORD)result == 1 )
          return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v79 + 8LL))(v79);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18011c740  mov     [rsp+arg_10], rbx
0x18011c745  mov     [rsp+arg_18], rsi
0x18011c74a  push    rdi
0x18011c74b  push    r12
0x18011c74d  push    r13
0x18011c74f  push    r14
0x18011c751  push    r15
0x18011c753  mov     eax, 140h
0x18011c758  call    _alloca_probe
0x18011c75d  sub     rsp, rax
0x18011c760  mov     rax, cs:__security_cookie
0x18011c767  xor     rax, rsp
0x18011c76a  mov     [rsp+168h+var_38], rax
0x18011c772  mov     r14, rdx
0x18011c775  mov     rdi, rcx
0x18011c778  call    ?GlobalManager@ActivityManager@Instrumentation@Basix@Microsoft@@SAAEAV1234@XZ; Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager(void)
0x18011c77d  lea     r8, [rdi+1D0h]
0x18011c784  mov     r9b, 1
0x18011c787  lea     rdx, [rsp+168h+var_48]
0x18011c78f  mov     rcx, rax
0x18011c792  call    ?SetActivityId@ActivityManager@Instrumentation@Basix@Microsoft@@QEAA?AUGuid@34@AEBU534@_N@Z; Microsoft::Basix::Instrumentation::ActivityManager::SetActivityId(Microsoft::Basix::Guid const &,bool)
0x18011c797  nop
0x18011c798  mov     rcx, [r14]
0x18011c79b  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18011c7a0  mov     rsi, [rax+10h]
0x18011c7a4  mov     rcx, [r14]
0x18011c7a7  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18011c7ac  mov     r15, [rax+28h]
0x18011c7b0  mov     rcx, [r14]; this
0x18011c7b3  call    ?Descriptor@InBuffer@IAsyncTransport@Dct@Basix@Microsoft@@QEAAAEAVInDescriptor@2345@XZ; Microsoft::Basix::Dct::IAsyncTransport::InBuffer::Descriptor(void)
0x18011c7b8  mov     [rax+70h], r15
0x18011c7bc  mov     rcx, [r14]
0x18011c7bf  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18011c7c4  mov     r12, [rax+28h]
0x18011c7c8  mov     rcx, [r14]
0x18011c7cb  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18011c7d0  mov     ebx, 8
0x18011c7d5  cmp     [rax+28h], rbx
0x18011c7d9  ja      short loc_18011C7E7
0x18011c7db  mov     rcx, [r14]
0x18011c7de  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18011c7e3  mov     rbx, [rax+28h]
0x18011c7e7  mov     rcx, [r14]
0x18011c7ea  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18011c7ef  mov     [rsp+168h+var_148], r12
0x18011c7f4  lea     r9, aReceiveRawSize; "Receive (raw) size: %d, data : "
0x18011c7fb  mov     r8, rbx
0x18011c7fe  mov     rdx, [rax+10h]
0x18011c802  lea     rcx, aUdprdpfltr; "UDPRDPFLTR"
0x18011c809  call    ??$Hexdump@VTraceDebug@Basix@Microsoft@@_K@TraceManager@Instrumentation@Basix@Microsoft@@SAXPEBDPEBX_K02@Z; Microsoft::Basix::Instrumentation::TraceManager::Hexdump<Microsoft::Basix::TraceDebug,unsigned __int64>(char const *,void const *,unsigned __int64,char const *,unsigned __int64)
0x18011c80e  lea     r13, [rdi-448h]
0x18011c815  mov     [rsp+168h+var_130], r13
0x18011c81a  mov     eax, [r13+4B4h]
0x18011c821  cmp     r15, rax
0x18011c824  ja      loc_18011C949
0x18011c82a  xorps   xmm0, xmm0
0x18011c82d  movups  [rsp+168h+Buf2], xmm0
0x18011c835  lea     rcx, [rsp+168h+Buf2]
0x18011c83d  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x18011c842  nop
0x18011c843  mov     rax, qword ptr [rsp+168h+Buf2]
0x18011c84b  test    rax, rax
0x18011c84e  jz      loc_18011C8D5
0x18011c854  cmp     byte ptr [rax+80h], 0
0x18011c85b  jz      short loc_18011C8D5
0x18011c85d  xorps   xmm0, xmm0
0x18011c860  movups  [rsp+168h+Buf1], xmm0
0x18011c868  xorps   xmm1, xmm1
0x18011c86b  movdqu  [rsp+168h+var_98], xmm1
0x18011c874  mov     r8d, 59h ; 'Y'
0x18011c87a  lea     rdx, aUdpRawDataRece; "UDP raw data received: length must be g"...
0x18011c881  lea     rcx, [rsp+168h+Buf1]
0x18011c889  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18011c88e  nop
0x18011c88f  lea     rax, aMicrosoftRdpna_12; "Microsoft::RdpNano::RawUdpRdpTransportF"...
0x18011c896  mov     [rsp+168h+var_140], rax
0x18011c89b  mov     dword ptr [rsp+168h+var_148], 1F6h
0x18011c8a3  lea     r9, aCW1SRdnanolibR_2; "C:\\__w\\1\\s\\rdnanolib\\rdnano\\RawUd"...
0x18011c8aa  lea     r8, [rsp+168h+Buf1]
0x18011c8b2  lea     rdx, aRdpnano; "RDPNANO"
0x18011c8b9  lea     rcx, [rsp+168h+Buf2]
0x18011c8c1  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,char const *,int,char const *)
0x18011c8c6  nop
0x18011c8c7  lea     rcx, [rsp+168h+Buf1]
0x18011c8cf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18011c8d4  nop
0x18011c8d5  mov     rdi, qword ptr [rsp+168h+Buf2+8]
0x18011c8dd  test    rdi, rdi
0x18011c8e0  jz      short loc_18011C91B
0x18011c8e2  or      ebx, 0FFFFFFFFh
0x18011c8e5  mov     eax, ebx
0x18011c8e7  lock xadd [rdi+8], eax
0x18011c8ec  add     eax, ebx
0x18011c8ee  jnz     short loc_18011C91B
0x18011c8f0  mov     rax, [rdi]
0x18011c8f3  mov     rcx, rdi
0x18011c8f6  mov     rax, [rax]
0x18011c8f9  call    cs:__guard_dispatch_icall_fptr
0x18011c8ff  mov     eax, ebx
0x18011c901  lock xadd [rdi+0Ch], eax
0x18011c906  add     eax, ebx
0x18011c908  jnz     short loc_18011C91B
0x18011c90a  mov     rax, [rdi]
0x18011c90d  mov     rcx, rdi
0x18011c910  mov     rax, [rax+8]
0x18011c914  call    cs:__guard_dispatch_icall_fptr
0x18011c91a  nop
0x18011c91b  call    ?GlobalManager@ActivityManager@Instrumentation@Basix@Microsoft@@SAAEAV1234@XZ; Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager(void)
0x18011c920  mov     r9, rax
0x18011c923  mov     rcx, [rax]
0x18011c926  mov     rax, [rcx+20h]
0x18011c92a  lea     r8, [rsp+168h+var_48]
0x18011c932  lea     rdx, [rsp+168h+Buf1]
0x18011c93a  mov     rcx, r9
0x18011c93d  call    cs:__guard_dispatch_icall_fptr
0x18011c943  nop
0x18011c944  jmp     loc_18011D973
0x18011c949  xor     r12d, r12d
0x18011c94c  cmp     [rdi+58h], r12d
0x18011c950  jnz     loc_18011CA79
0x18011c956  cmp     [rdi+54h], r12b
0x18011c95a  jz      loc_18011CBEE
0x18011c960  mov     r8, r15; unsigned __int64
0x18011c963  mov     rdx, rsi; unsigned __int8 *
0x18011c966  mov     rcx, r13; this
0x18011c969  call    ?OnSynReceived@RawUdpRdpTransportFilter@RdpNano@Microsoft@@IEAAJPEAE_K@Z; Microsoft::RdpNano::RawUdpRdpTransportFilter::OnSynReceived(uchar *,unsigned __int64)
0x18011c96e  test    eax, eax
0x18011c970  js      loc_18011CA4B
0x18011c976  lfence
0x18011c979  mov     dword ptr [rdi+58h], 2
0x18011c980  mov     rax, [rdi-440h]
0x18011c987  movsxd  rcx, dword ptr [rax+4]
0x18011c98b  add     rcx, 0FFFFFFFFFFFFFBC0h
0x18011c992  add     rcx, rdi
0x18011c995  lea     rdx, [rsp+168h+Buf1]
0x18011c99d  call    ??$GetSharedPtr@VITimerCallback@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$shared_ptr@VITimerCallback@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::ITimerCallback>(void)
0x18011c9a2  mov     rdx, rax
0x18011c9a5  lfence
0x18011c9a8  xorps   xmm0, xmm0
0x18011c9ab  movdqu  [rsp+168h+Buf2], xmm0
0x18011c9b4  cmp     [rax+8], r12
0x18011c9b8  jz      short loc_18011C9D8
0x18011c9ba  lfence
0x18011c9bd  mov     rax, [rax]
0x18011c9c0  mov     qword ptr [rsp+168h+Buf2], rax
0x18011c9c8  mov     rax, [rdx+8]
0x18011c9cc  mov     qword ptr [rsp+168h+Buf2+8], rax
0x18011c9d4  lock inc dword ptr [rax+0Ch]
0x18011c9d8  mov     eax, [rdi+4Ch]
0x18011c9db  mov     [rsp+168h+var_130], rax
0x18011c9e0  lea     r8, [rsp+168h+Buf2]
0x18011c9e8  lea     rdx, [rsp+168h+var_130]
0x18011c9ed  lea     rcx, [rdi+118h]
0x18011c9f4  call    ?Setup@Timer@Basix@Microsoft@@QEAAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@V?$weak_ptr@VITimerCallback@Basix@Microsoft@@@6@@Z; Microsoft::Basix::Timer::Setup(std::chrono::duration<__int64,std::ratio<1,1000>> const &,std::weak_ptr<Microsoft::Basix::ITimerCallback>)
0x18011c9f9  nop
0x18011c9fa  lfence
0x18011c9fd  mov     rdi, qword ptr [rsp+168h+Buf1+8]
0x18011ca05  test    rdi, rdi
0x18011ca08  jz      short loc_18011CA42
0x18011ca0a  or      ebx, 0FFFFFFFFh
0x18011ca0d  mov     eax, ebx
0x18011ca0f  lock xadd [rdi+8], eax
0x18011ca14  add     eax, ebx
0x18011ca16  jnz     short loc_18011CA42
0x18011ca18  mov     rax, [rdi]
0x18011ca1b  mov     rcx, rdi
0x18011ca1e  mov     rax, [rax]
0x18011ca21  call    cs:__guard_dispatch_icall_fptr
0x18011ca27  mov     eax, ebx
0x18011ca29  lock xadd [rdi+0Ch], eax
0x18011ca2e  add     eax, ebx
0x18011ca30  jnz     short loc_18011CA42
0x18011ca32  mov     rax, [rdi]
0x18011ca35  mov     rcx, rdi
0x18011ca38  mov     rax, [rax+8]
0x18011ca3c  call    cs:__guard_dispatch_icall_fptr
0x18011ca42  mov     rcx, r13; this
0x18011ca45  call    ?SendSynAckPacket@RawUdpRdpTransportFilter@RdpNano@Microsoft@@IEAAXXZ; Microsoft::RdpNano::RawUdpRdpTransportFilter::SendSynAckPacket(void)
0x18011ca4a  nop
0x18011ca4b  call    ?GlobalManager@ActivityManager@Instrumentation@Basix@Microsoft@@SAAEAV1234@XZ; Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager(void)
0x18011ca50  mov     r9, rax
0x18011ca53  mov     rcx, [rax]
0x18011ca56  mov     rax, [rcx+20h]
0x18011ca5a  lea     r8, [rsp+168h+var_48]
0x18011ca62  lea     rdx, [rsp+168h+Buf1]
0x18011ca6a  mov     rcx, r9
0x18011ca6d  call    cs:__guard_dispatch_icall_fptr
0x18011ca73  nop
0x18011ca74  jmp     loc_18011D973
0x18011ca79  cmp     dword ptr [rdi+58h], 1
0x18011ca7d  jnz     loc_18011CBEE
0x18011ca83  mov     r8, r15; unsigned __int64
0x18011ca86  mov     rdx, rsi; unsigned __int8 *
0x18011ca89  mov     rcx, r13; this
0x18011ca8c  call    ?OnSynAckReceived@RawUdpRdpTransportFilter@RdpNano@Microsoft@@IEAAJPEAE_K@Z; Microsoft::RdpNano::RawUdpRdpTransportFilter::OnSynAckReceived(uchar *,unsigned __int64)
0x18011ca91  test    eax, eax
0x18011ca93  js      loc_18011CBC0
0x18011ca99  lfence
0x18011ca9c  mov     rcx, [rdi+120h]
0x18011caa3  mov     rax, [rcx]
0x18011caa6  xor     edx, edx
0x18011caa8  mov     rax, [rax+8]
0x18011caac  call    cs:__guard_dispatch_icall_fptr
0x18011cab2  mov     dword ptr [rdi+58h], 3
0x18011cab9  xorps   xmm0, xmm0
0x18011cabc  xor     eax, eax
0x18011cabe  movups  [rsp+168h+Buf1], xmm0
0x18011cac6  mov     qword ptr [rsp+168h+var_98], rax
0x18011cace  movups  [rsp+168h+var_68], xmm0
0x18011cad6  xorps   xmm1, xmm1
0x18011cad9  movdqu  [rsp+168h+var_58], xmm1
0x18011cae2  lea     r8d, [rax+33h]
0x18011cae6  lea     rdx, aMicrosoftBasix_437; "Microsoft::Basix::Dct.RawUdpRdpFilter.W"...
0x18011caed  lea     rcx, [rsp+168h+var_68]
0x18011caf5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18011cafa  nop
0x18011cafb  lfence
0x18011cafe  lea     r8, [rsp+168h+var_68]
0x18011cb06  lea     rdx, [rsp+168h+Buf1]
0x18011cb0e  lea     rcx, [rdi-420h]
0x18011cb15  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x18011cb1a  nop
0x18011cb1b  lea     rcx, [rsp+168h+var_68]
0x18011cb23  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18011cb28  mov     rcx, qword ptr [rsp+168h+var_98]
0x18011cb30  mov     r8, [rcx+8]
0x18011cb34  lea     rax, [r8+11h]
0x18011cb38  neg     rax
0x18011cb3b  sbb     rdx, rdx
0x18011cb3e  and     rdx, r8
0x18011cb41  cmp     [rdx+18h], r12
0x18011cb45  jnz     short loc_18011CB4C
0x18011cb47  cmp     [rcx], r12
0x18011cb4a  jz      short loc_18011CBA1
0x18011cb4c  lea     rdx, [rsp+168h+Buf2]
0x18011cb54  call    ??$get_value@V?$weak_ptr@VWriteCompletionCallback@IAsyncTransport@Dct@Basix@Microsoft@@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$weak_ptr@VWriteCompletionCallback@IAsyncTransport@Dct@Basix@Microsoft@@@std@@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::weak_ptr<Microsoft::Basix::Dct::IAsyncTransport::WriteCompletionCallback>>(void)
0x18011cb59  lfence
0x18011cb5c  mov     rax, qword ptr [rsp+168h+Buf2]
0x18011cb64  mov     [rdi+0F8h], rax
0x18011cb6b  mov     rcx, [rdi+100h]
0x18011cb72  mov     rax, qword ptr [rsp+168h+Buf2+8]
0x18011cb7a  mov     [rdi+100h], rax
0x18011cb81  test    rcx, rcx
0x18011cb84  jz      short loc_18011CBA1
0x18011cb86  or      ebx, 0FFFFFFFFh
0x18011cb89  mov     eax, ebx
0x18011cb8b  lock xadd [rcx+0Ch], eax
0x18011cb90  add     eax, ebx
0x18011cb92  jnz     short loc_18011CBA1
0x18011cb94  mov     rax, [rcx]
0x18011cb97  mov     rax, [rax+8]
0x18011cb9b  call    cs:__guard_dispatch_icall_fptr
0x18011cba1  lfence
0x18011cba4  xor     r8d, r8d; bool
0x18011cba7  xor     edx, edx; bool
0x18011cba9  mov     rcx, r13; this
0x18011cbac  call    ?FireOnOpened@DCTBaseChannelImplNoProp@Dct@Basix@Microsoft@@MEAAX_N0@Z; Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnOpened(bool,bool)
0x18011cbb1  nop
0x18011cbb2  lea     rcx, [rsp+168h+Buf1]
0x18011cbba  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x18011cbbf  nop
0x18011cbc0  call    ?GlobalManager@ActivityManager@Instrumentation@Basix@Microsoft@@SAAEAV1234@XZ; Microsoft::Basix::Instrumentation::ActivityManager::GlobalManager(void)
0x18011cbc5  mov     r9, rax
0x18011cbc8  mov     rcx, [rax]
0x18011cbcb  mov     rax, [rcx+20h]
0x18011cbcf  lea     r8, [rsp+168h+var_48]
0x18011cbd7  lea     rdx, [rsp+168h+Buf1]
0x18011cbdf  mov     rcx, r9
0x18011cbe2  call    cs:__guard_dispatch_icall_fptr
0x18011cbe8  nop
0x18011cbe9  jmp     loc_18011D973
0x18011cbee  mov     eax, [rdi+6Ch]
0x18011cbf1  movzx   r12d, byte ptr [rax+rsi]
0x18011cbf6  test    r12b, 1
0x18011cbfa  jz      loc_18011CD08
0x18011cc00  xorps   xmm0, xmm0
0x18011cc03  movups  [rsp+168h+Buf2], xmm0
0x18011cc0b  lea     rcx, [rsp+168h+Buf2]
0x18011cc13  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18011cc18  nop
0x18011cc19  mov     rax, qword ptr [rsp+168h+Buf2]
0x18011cc21  test    rax, rax
0x18011cc24  jz      short loc_18011CC94
0x18011cc26  cmp     byte ptr [rax+80h], 0
0x18011cc2d  jz      short loc_18011CC94
0x18011cc2f  xorps   xmm0, xmm0
0x18011cc32  movups  [rsp+168h+Buf1], xmm0
0x18011cc3a  xorps   xmm1, xmm1
0x18011cc3d  movdqu  [rsp+168h+var_98], xmm1
0x18011cc46  mov     r8d, 61h ; 'a'
0x18011cc4c  lea     rdx, aUdpHandshakeRe_1; "UDP handshake retransmission packet rec"...
0x18011cc53  lea     rcx, [rsp+168h+Buf1]
0x18011cc5b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18011cc60  nop
0x18011cc61  mov     dword ptr [rsp+168h+var_148], r12d
0x18011cc66  mov     r9d, r15d
0x18011cc69  lea     r8, [rsp+168h+Buf1]
0x18011cc71  lea     rdx, aRdpnano; "RDPNANO"
0x18011cc78  lea     rcx, [rsp+168h+Buf2]
0x18011cc80  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@HH@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@HH@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int,int>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,int,int)
  ... truncated ...
```
