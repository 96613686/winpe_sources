# Microsoft::Basix::Dct::WinsockDCTChannelContext::InternalQueueWrite(std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::OutBuffer> const &)

- ea: `0x180150730`
- end: `0x1801510c2`
- name: `?InternalQueueWrite@WinsockDCTChannelContext@Dct@Basix@Microsoft@@MEAAXAEBV?$shared_ptr@VOutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@@std@@@Z`
- size: `2450`
- prototype: ``
- caller_count: `0`
- callee_count: `36`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x1800111fc`
- `0x180015bb8`
- `0x180017380`
- `0x180017518`
- `0x180018b94`
- `0x18001902c`
- `0x18001979c`
- `0x18001ab4c`
- `0x180024760`
- `0x1800334a8`
- `0x18003c308`
- `0x18003da74`
- `0x18003f0f4`
- `0x18004e1dc`
- `0x1800bb210`
- `0x1800d34ac`
- `0x1801195b8`
- `0x180119f84`
- `0x18014d5f4`
- `0x18014e4f8`
- `0x18014e658`
- `0x18014fae0`
- `0x180150730`
- `0x1801acb74`
- `0x1801ad72c`
- `0x1801b3b70`
- `0x1802ea40c`
- `0x1802ed54c`
- `0x1802ee5e0`
- `0x1802ee648`
- `0x1802ee6dc`
- `0x180311e54`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x1801508f0`: `OnWritableThread`
- `0x1801507ff`: `Ignoring QueueWrite - socket closed.`
- `0x180150947`: `WinsockDCTChannelContext::InternalQueueWrite`
- `0x180150a66`: `no dummy packet from winsock WriteComplete in the last 14 seconds: local: `
- `0x180150ac0`: `DummyPacketWriteIncomplete`
- `0x180150cf0`: `WinsockDCT WritePostDummyFailed`
- `0x180150cfc`: `WritePostDummyFailed`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
void __fastcall Microsoft::Basix::Dct::WinsockDCTChannelContext::InternalQueueWrite(
        __int64 a1,
        Microsoft::Basix::Dct::IAsyncTransport::OutBuffer **a2)
{
  __int64 v4; // rax
  volatile signed __int32 *v5; // rsi
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rbx
  Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **DelayedTraceRecord; // r15
  int i; // ebx
  char *Buffer; // rax
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rdx
  volatile signed __int32 *v30; // rbx
  __int64 v31; // rax
  __int64 *v32; // rax
  __int64 v33; // rdx
  void (__fastcall ***v34)(_QWORD, __int64); // rcx
  void (__fastcall ***v35)(_QWORD, __int64); // rcx
  __int64 v36; // rax
  __int64 PeerAddress; // rax
  __int64 v38; // rax
  volatile signed __int32 *v39; // rbx
  volatile signed __int32 *v40; // rbx
  Microsoft::Basix::Containers::FlexOBuffer *v41; // rax
  __int64 v42; // rax
  char v43; // [rsp+40h] [rbp-C0h]
  int v44; // [rsp+44h] [rbp-BCh] BYREF
  int v45; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v46; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v47[2]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v48[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v49[2]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v50[2]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v51[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v52[32]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v53[4]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v54[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v55[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v56[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v57[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v58[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v59[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v60[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v61[32]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v62[32]; // [rsp+240h] [rbp+140h] BYREF
  char v63; // [rsp+260h] [rbp+160h] BYREF
  __int64 v64; // [rsp+310h] [rbp+210h] BYREF
  size_t BufferCount[2]; // [rsp+318h] [rbp+218h] BYREF
  __int128 v66; // [rsp+328h] [rbp+228h]
  __int128 v67; // [rsp+338h] [rbp+238h] BYREF
  __int128 v68; // [rsp+348h] [rbp+248h]
  int v69[4]; // [rsp+358h] [rbp+258h] BYREF
  __int128 v70; // [rsp+368h] [rbp+268h]

  v64 = 0;
  v46 = 0;
  v4 = *(_QWORD *)(a1 + 3984);
  if ( v4 )
    _InterlockedAdd((volatile signed __int32 *)(v4 + 8), 1u);
  *(_QWORD *)&v46 = *(_QWORD *)(a1 + 3976);
  v5 = *(volatile signed __int32 **)(a1 + 3984);
  *((_QWORD *)&v46 + 1) = v5;
  if ( !(_QWORD)v46 )
  {
    *(_OWORD *)BufferCount = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(BufferCount);
    if ( BufferCount[0] && *(_BYTE *)(BufferCount[0] + 128) )
    {
      v67 = 0;
      v68 = 0;
      std::string::_Construct<1,char const *>(&v67, "Ignoring QueueWrite - socket closed.", 36);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
        BufferCount,
        "NANO_DCT",
        &v67);
      std::string::_Tidy_deallocate(&v67);
    }
    v6 = (volatile signed __int32 *)BufferCount[1];
    if ( BufferCount[1] )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(BufferCount[1] + 8)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        if ( !_InterlockedDecrement(v6 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
    }
    goto LABEL_51;
  }
  if ( *(_BYTE *)(a1 + 4096)
    && *(_BYTE *)(a1 + 4097)
    && *(_BYTE *)std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2) == 104 )
  {
    if ( *(_BYTE *)std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2) == 104 )
    {
      v10 = *(_QWORD *)Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager(v8, v7, v9);
      v67 = 0;
      v68 = 0;
      std::string::_Construct<1,char const *>(&v67, "OnWritableThread", 16);
      DelayedTraceRecord = (Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **)Microsoft::Basix::Instrumentation::DelayedTraceManager::GetDelayedTraceRecord(v10, &v67, 0);
      std::string::_Tidy_deallocate(&v67);
      if ( *DelayedTraceRecord )
      {
        BufferCount[0] = 0;
        for ( i = 0; i < 2; ++i )
        {
          Buffer = Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::GetBuffer(
                     *DelayedTraceRecord,
                     BufferCount);
          v14 = snprintf(Buffer, BufferCount[0], "WinsockDCTChannelContext::InternalQueueWrite");
          if ( v14 < BufferCount[0] )
            break;
          BufferCount[0] = v14;
        }
        Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::Finalize(
          *DelayedTraceRecord,
          4,
          "BASIX_DCT");
      }
    }
    ++*(_QWORD *)(a1 + 4104);
    v15 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::ITimerCallback>(
            a1 + *(int *)(*(_QWORD *)(a1 + 8) + 4LL) + 8LL,
            &v67);
    BufferCount[0] = 14000;
    Microsoft::Basix::Timer::Setup(a1 + 4128, BufferCount, v15);
    v16 = *(_QWORD *)std::chrono::steady_clock::now(BufferCount) / 1000LL;
    if ( *(_QWORD *)(a1 + 4120) + 14500000LL < *(_QWORD *)(a1 + 4112) )
    {
      v67 = 0;
      memset(v47, 0, sizeof(v47));
      std::string::_Construct<1,char const *>(v47, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp", 54);
      v17 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a1 + 104LL))(a1, v59);
      v18 = std::operator+<char>(
              v58,
              "no dummy packet from winsock WriteComplete in the last 14 seconds: local: ",
              a1 + 104);
      v19 = std::operator+<char>(v57, v18, ", channelClassName=");
      LOBYTE(v20) = v43;
      std::string::string(v52, v20, v19, v17);
      *(_OWORD *)v69 = 0;
      v70 = 0;
      std::string::_Construct<1,char const *>(v69, "DummyPacketWriteIncomplete", 26);
      v21 = Microsoft::Basix::Dct::DCTException::DCTException(
              (unsigned int)&v63,
              2,
              (unsigned int)v69,
              (unsigned int)v52,
              (__int64)v47,
              291);
      std::make_exception_ptr<Microsoft::Basix::Dct::DCTException>(&v67, v21);
      std::string::_Tidy_deallocate(v69);
      std::string::_Tidy_deallocate(v52);
      std::string::_Tidy_deallocate(v57);
      std::string::_Tidy_deallocate(v58);
      std::string::_Tidy_deallocate(v59);
      std::string::_Tidy_deallocate(v47);
      *(_OWORD *)v69 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v69);
      if ( *(_QWORD *)v69 && *(_BYTE *)(*(_QWORD *)v69 + 128LL) )
      {
        memset(v51, 0, sizeof(v51));
        std::string::_Construct<1,char const *>(v51, "\"", 1);
        v22 = (_QWORD *)Microsoft::Basix::Exception::CreateDescription(v62, &v67);
        v23 = v22;
        if ( v22[3] > 0xFu )
          v23 = (_QWORD *)*v22;
        memset(v50, 0, sizeof(v50));
        std::string::_Construct<1,char const *>(v50, "\"", 1);
        memset(v49, 0, sizeof(v49));
        std::string::_Construct<1,char const *>(v49, ":", 1);
        memset(v48, 0, sizeof(v48));
        std::string::_Construct<1,char const *>(v48, "\"", 1);
        *(_OWORD *)BufferCount = 0;
        v66 = 0;
        std::string::_Construct<1,char const *>(BufferCount, "\"", 1);
        v24 = std::operator+<char>(v61, BufferCount, "exception");
        LOBYTE(v25) = v43;
        std::string::string(v56, v25, v24, v48);
        LOBYTE(v26) = v43;
        std::string::string(v55, v26, v56, v49);
        LOBYTE(v27) = v43;
        std::string::string(v54, v27, v55, v50);
        v28 = std::operator+<char>(v60, v54, v23);
        LOBYTE(v29) = v43;
        std::string::string(v53, v29, v28, v51);
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
          (int)v69,
          (int)"RD_CHECKPOINT",
          0,
          (int)"WinsockDCT",
          "WritePostDummyFailed",
          "WinsockDCT WritePostDummyFailed",
          (__int64)v53);
        std::string::_Tidy_deallocate(v60);
        std::string::_Tidy_deallocate(v54);
        std::string::_Tidy_deallocate(v55);
        std::string::_Tidy_deallocate(v56);
        std::string::_Tidy_deallocate(v61);
        std::string::_Tidy_deallocate(BufferCount);
        std::string::_Tidy_deallocate(v48);
        std::string::_Tidy_deallocate(v49);
        std::string::_Tidy_deallocate(v50);
        std::string::_Tidy_deallocate(v62);
        std::string::_Tidy_deallocate(v51);
      }
      v30 = *(volatile signed __int32 **)&v69[2];
      if ( *(_QWORD *)&v69[2] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v69[2] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
          if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
        }
      }
      *(_BYTE *)(a1 + 4097) = 0;
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 120LL))(a1, &v67);
      Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnClosed(
        (Microsoft::Basix::Dct::DCTBaseChannelImplNoProp *)a1,
        1);
      __ExceptionPtrDestroy(&v67);
      goto LABEL_51;
    }
    *(_QWORD *)(a1 + 4112) = v16;
  }
  v31 = Microsoft::Basix::Containers::ObjectCache<Microsoft::Basix::Dct::WinsockDCTIORequest>::Acquire(a1 + 4168);
  if ( v31 )
  {
    v35 = (void (__fastcall ***)(_QWORD, __int64))v64;
    v64 = v31;
    if ( v35 )
      (**v35)(v35, 1);
  }
  else
  {
    v44 = 2;
    v32 = (__int64 *)std::make_unique<Microsoft::Basix::Dct::WinsockDCTIORequest,std::shared_ptr<Microsoft::Basix::WinUtils::WinSockObj> &,enum Microsoft::Basix::Dct::WinsockDCTIORequest::Type const &,0>(
                       BufferCount,
                       &v46,
                       &v44);
    v33 = *v32;
    *v32 = 0;
    v34 = (void (__fastcall ***)(_QWORD, __int64))v64;
    v64 = v33;
    if ( v34 )
      (**v34)(v34, 1);
    if ( BufferCount[0] )
      (**(void (__fastcall ***)(size_t, __int64))BufferCount[0])(BufferCount[0], 1);
    v5 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
  }
  std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(v64 + 88, a2);
  v36 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2);
  PeerAddress = Microsoft::Basix::Dct::IAsyncTransport::IODescriptor::GetPeerAddress(v36, v69);
  v38 = std::dynamic_pointer_cast<Microsoft::Basix::Dct::SockaddrStorage,Microsoft::Basix::Dct::EndpointAddress>(
          &v67,
          PeerAddress);
  std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(v64 + 128, v38);
  v39 = (volatile signed __int32 *)*((_QWORD *)&v67 + 1);
  if ( *((_QWORD *)&v67 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v67 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
      if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
    }
  }
  v40 = *(volatile signed __int32 **)&v69[2];
  if ( *(_QWORD *)&v69[2] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v69[2] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
      if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
    }
  }
  if ( *(_BYTE *)(a1 + 1536) )
  {
    v44 = *(unsigned __int16 *)(std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2) + 12);
    v41 = Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(*a2);
    v45 = Microsoft::Basix::Containers::FlexOBuffer::Size(v41);
    LODWORD(BufferCount[0]) = *(unsigned __int16 *)(std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2)
                                                  + 2);
    Microsoft::Basix::Instrumentation::SocketDataSent::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
      a1 + 1664,
      a1 + 1544,
      (unsigned int)BufferCount,
      (unsigned int)&v45,
      (__int64)&v44);
  }
  v42 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*a2);
  *(_BYTE *)(v64 + 276) = *(_BYTE *)(v42 + 129);
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 160LL))(a1, &v64);
LABEL_51:
  if ( v5 )
  {
    if ( !_InterlockedDecrement(v5 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( !_InterlockedDecrement(v5 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  if ( v64 )
    (**(void (__fastcall ***)(__int64, __int64))v64)(v64, 1);
}

```

## disassembly

```asm
0x180150730  mov     [rsp-8+arg_10], rbx
0x180150735  mov     [rsp-8+arg_18], rsi
0x18015073a  push    rbp
0x18015073b  push    rdi
0x18015073c  push    r13
0x18015073e  push    r14
0x180150740  push    r15
0x180150742  lea     rbp, [rsp-280h]
0x18015074a  mov     eax, 380h
0x18015074f  call    _alloca_probe
0x180150754  sub     rsp, rax
0x180150757  mov     rax, cs:__security_cookie
0x18015075e  xor     rax, rsp
0x180150761  mov     [rbp+2A0h+var_28], rax
0x180150768  mov     r14, rdx
0x18015076b  mov     rdi, rcx
0x18015076e  mov     [rbp+2A0h+var_90], 0
0x180150779  xorps   xmm0, xmm0
0x18015077c  movups  [rsp+3A0h+var_350], xmm0
0x180150781  mov     rax, [rcx+0F90h]
0x180150788  mov     r15d, 1
0x18015078e  test    rax, rax
0x180150791  jz      short loc_180150798
0x180150793  lock add [rax+8], r15d
0x180150798  mov     rax, [rcx+0F88h]
0x18015079f  mov     qword ptr [rsp+3A0h+var_350], rax
0x1801507a4  mov     rsi, [rcx+0F90h]
0x1801507ab  mov     qword ptr [rsp+3A0h+var_350+8], rsi
0x1801507b0  or      r13d, 0FFFFFFFFh
0x1801507b4  test    rax, rax
0x1801507b7  jnz     loc_180150891
0x1801507bd  movups  xmmword ptr [rbp+2A0h+BufferCount], xmm0
0x1801507c4  lea     rcx, [rbp+2A0h+BufferCount]
0x1801507cb  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1801507d0  nop
0x1801507d1  mov     rax, [rbp+2A0h+BufferCount]
0x1801507d8  test    rax, rax
0x1801507db  jz      short loc_18015083B
0x1801507dd  cmp     byte ptr [rax+80h], 0
0x1801507e4  jz      short loc_18015083B
0x1801507e6  xorps   xmm0, xmm0
0x1801507e9  movups  [rbp+2A0h+var_68], xmm0
0x1801507f0  xorps   xmm1, xmm1
0x1801507f3  movdqu  [rbp+2A0h+var_58], xmm1
0x1801507fb  lea     r8d, [r13+25h]
0x1801507ff  lea     rdx, aIgnoringQueuew; "Ignoring QueueWrite - socket closed."
0x180150806  lea     rcx, [rbp+2A0h+var_68]
0x18015080d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180150812  nop
0x180150813  lea     r8, [rbp+2A0h+var_68]
0x18015081a  lea     rdx, aNanoDct; "NANO_DCT"
0x180150821  lea     rcx, [rbp+2A0h+BufferCount]
0x180150828  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x18015082d  nop
0x18015082e  lea     rcx, [rbp+2A0h+var_68]
0x180150835  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18015083a  nop
0x18015083b  mov     rbx, [rbp+2A0h+BufferCount+8]
0x180150842  test    rbx, rbx
0x180150845  jz      loc_18015103D
0x18015084b  mov     eax, r13d
0x18015084e  lock xadd [rbx+8], eax
0x180150853  add     eax, r13d
0x180150856  jnz     loc_18015103D
0x18015085c  mov     rax, [rbx]
0x18015085f  mov     rcx, rbx
0x180150862  mov     rax, [rax]
0x180150865  call    cs:__guard_dispatch_icall_fptr
0x18015086b  mov     eax, r13d
0x18015086e  lock xadd [rbx+0Ch], eax
0x180150873  add     eax, r13d
0x180150876  jnz     loc_18015103D
0x18015087c  mov     rax, [rbx]
0x18015087f  mov     rcx, rbx
0x180150882  mov     rax, [rax+8]
0x180150886  call    cs:__guard_dispatch_icall_fptr
0x18015088c  jmp     loc_18015103D
0x180150891  cmp     byte ptr [rcx+1000h], 0
0x180150898  jz      loc_180150E2A
0x18015089e  cmp     byte ptr [rcx+1001h], 0
0x1801508a5  jz      loc_180150E2A
0x1801508ab  mov     rcx, [rdx]
0x1801508ae  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x1801508b3  cmp     byte ptr [rax], 68h ; 'h'
0x1801508b6  jnz     loc_180150E2A
0x1801508bc  mov     rcx, [r14]
0x1801508bf  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x1801508c4  cmp     byte ptr [rax], 68h ; 'h'
0x1801508c7  jnz     loc_180150991
0x1801508cd  call    ?s_delayedTraceManager@TraceManager@Instrumentation@Basix@Microsoft@@SAAEAV?$shared_ptr@VDelayedTraceManager@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager(void)
0x1801508d2  mov     rbx, [rax]
0x1801508d5  xorps   xmm0, xmm0
0x1801508d8  movups  [rbp+2A0h+var_68], xmm0
0x1801508df  xorps   xmm1, xmm1
0x1801508e2  movdqu  [rbp+2A0h+var_58], xmm1
0x1801508ea  mov     r8d, 10h
0x1801508f0  lea     rdx, aOnwritablethre_0; "OnWritableThread"
0x1801508f7  lea     rcx, [rbp+2A0h+var_68]
0x1801508fe  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180150903  nop
0x180150904  xor     r8d, r8d
0x180150907  lea     rdx, [rbp+2A0h+var_68]
0x18015090e  mov     rcx, rbx
0x180150911  call    ?GetDelayedTraceRecord@DelayedTraceManager@Instrumentation@Basix@Microsoft@@QEAAAEAV?$shared_ptr@VDelayedTraceRecord@DelayedTraceManager@Instrumentation@Basix@Microsoft@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@6@_N@Z; Microsoft::Basix::Instrumentation::DelayedTraceManager::GetDelayedTraceRecord(std::string const &,bool)
0x180150916  mov     r15, rax
0x180150919  lea     rcx, [rbp+2A0h+var_68]
0x180150920  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180150925  cmp     qword ptr [r15], 0
0x180150929  jz      short loc_18015098B
0x18015092b  mov     [rbp+2A0h+BufferCount], 0
0x180150936  xor     ebx, ebx
0x180150938  lea     rdx, [rbp+2A0h+BufferCount]; unsigned __int64 *
0x18015093f  mov     rcx, [r15]; this
0x180150942  call    ?GetBuffer@DelayedTraceRecord@DelayedTraceManager@Instrumentation@Basix@Microsoft@@QEAAPEADAEA_K@Z; Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::GetBuffer(unsigned __int64 &)
0x180150947  lea     r8, aWinsockdctchan_6; "WinsockDCTChannelContext::InternalQueue"...
0x18015094e  mov     rdx, [rbp+2A0h+BufferCount]; BufferCount
0x180150955  mov     rcx, rax; Buffer
0x180150958  call    snprintf
0x18015095d  movsxd  rcx, eax
0x180150960  cmp     rcx, [rbp+2A0h+BufferCount]
0x180150967  jb      short loc_180150977
0x180150969  mov     [rbp+2A0h+BufferCount], rcx
0x180150970  inc     ebx
0x180150972  cmp     ebx, 2
0x180150975  jl      short loc_180150938
0x180150977  lea     r8, aBasixDct; "BASIX_DCT"
0x18015097e  mov     edx, 4
0x180150983  mov     rcx, [r15]
0x180150986  call    ?Finalize@DelayedTraceRecord@DelayedTraceManager@Instrumentation@Basix@Microsoft@@QEAAXW4Level@RecordDescriptor@345@PEBD@Z; Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::Finalize(Microsoft::Basix::Instrumentation::RecordDescriptor::Level,char const *)
0x18015098b  mov     r15d, 1
0x180150991  add     [rdi+1008h], r15
0x180150998  mov     rax, [rdi+8]
0x18015099c  movsxd  rcx, dword ptr [rax+4]
0x1801509a0  add     rcx, 8
0x1801509a4  add     rcx, rdi
0x1801509a7  lea     rdx, [rbp+2A0h+var_68]
0x1801509ae  call    ??$GetWeakPtr@VITimerCallback@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$weak_ptr@VITimerCallback@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::ITimerCallback>(void)
0x1801509b3  mov     [rbp+2A0h+BufferCount], 36B0h
0x1801509be  lea     rcx, [rdi+1020h]
0x1801509c5  mov     r8, rax
0x1801509c8  lea     rdx, [rbp+2A0h+BufferCount]
0x1801509cf  call    ?Setup@Timer@Basix@Microsoft@@QEAAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@V?$weak_ptr@VITimerCallback@Basix@Microsoft@@@6@@Z; Microsoft::Basix::Timer::Setup(std::chrono::duration<__int64,std::ratio<1,1000>> const &,std::weak_ptr<Microsoft::Basix::ITimerCallback>)
0x1801509d4  lea     rcx, [rbp+2A0h+BufferCount]
0x1801509db  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1801509e0  mov     rcx, [rax]
0x1801509e3  mov     rax, 20C49BA5E353F7CFh
0x1801509ed  imul    rcx
0x1801509f0  sar     rdx, 7
0x1801509f4  mov     rax, rdx
0x1801509f7  shr     rax, 3Fh
0x1801509fb  add     rdx, rax
0x1801509fe  mov     rax, [rdi+1018h]
0x180150a05  add     rax, 0DD40A0h
0x180150a0b  cmp     rax, [rdi+1010h]
0x180150a12  jge     loc_180150E23
0x180150a18  xorps   xmm0, xmm0
0x180150a1b  movups  [rbp+2A0h+var_68], xmm0
0x180150a22  movups  [rsp+3A0h+var_340], xmm0
0x180150a27  xorps   xmm1, xmm1
0x180150a2a  movdqu  [rsp+3A0h+var_330], xmm1
0x180150a30  mov     r8d, 36h ; '6'
0x180150a36  lea     rdx, aCW1SSrcLibbasi_63; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180150a3d  lea     rcx, [rsp+3A0h+var_340]
0x180150a42  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180150a47  nop
0x180150a48  mov     rax, [rdi]
0x180150a4b  lea     rdx, [rbp+2A0h+var_1C0]
0x180150a52  mov     rcx, rdi
0x180150a55  mov     rax, [rax+68h]
0x180150a59  call    cs:__guard_dispatch_icall_fptr
0x180150a5f  mov     rbx, rax
0x180150a62  lea     r8, [rdi+68h]
0x180150a66  lea     rdx, aNoDummyPacketF; "no dummy packet from winsock WriteCompl"...
0x180150a6d  lea     rcx, [rbp+2A0h+var_1E0]
0x180150a74  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x180150a79  nop
0x180150a7a  lea     r8, aChannelclassna_0; ", channelClassName="
0x180150a81  mov     rdx, rax
0x180150a84  lea     rcx, [rbp+2A0h+var_200]
0x180150a8b  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180150a90  nop
0x180150a91  mov     r9, rbx
0x180150a94  mov     r8, rax
0x180150a97  mov     dl, [rsp+3A0h+var_360]
0x180150a9b  lea     rcx, [rbp+2A0h+var_2A0]
0x180150a9f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180150aa4  nop
0x180150aa5  xorps   xmm0, xmm0
0x180150aa8  movups  xmmword ptr [rbp+2A0h+var_48], xmm0
0x180150aaf  xorps   xmm1, xmm1
0x180150ab2  movdqu  [rbp+2A0h+var_38], xmm1
0x180150aba  mov     r8d, 1Ah
0x180150ac0  lea     rdx, aDummypacketwri; "DummyPacketWriteIncomplete"
0x180150ac7  lea     rcx, [rbp+2A0h+var_48]
0x180150ace  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180150ad3  nop
0x180150ad4  mov     dword ptr [rsp+3A0h+Str], 123h
0x180150adc  lea     rax, [rsp+3A0h+var_340]
0x180150ae1  mov     [rsp+3A0h+var_380], rax
0x180150ae6  lea     r9, [rbp+2A0h+var_2A0]
0x180150aea  lea     r8, [rbp+2A0h+var_48]
0x180150af1  mov     edx, 2
0x180150af6  lea     rcx, [rbp+2A0h+var_140]
0x180150afd  call    ??0DCTException@Dct@Basix@Microsoft@@QEAA@W4ErrorCode@0123@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@11I@Z; Microsoft::Basix::Dct::DCTException::DCTException(Microsoft::Basix::Dct::DCTException::ErrorCode,std::string const &,std::string const &,std::string const &,uint)
0x180150b02  mov     rdx, rax
0x180150b05  lea     rcx, [rbp+2A0h+var_68]
0x180150b0c  call    ??$make_exception_ptr@VDCTException@Dct@Basix@Microsoft@@@std@@YA?AVexception_ptr@0@VDCTException@Dct@Basix@Microsoft@@@Z; std::make_exception_ptr<Microsoft::Basix::Dct::DCTException>(Microsoft::Basix::Dct::DCTException)
0x180150b11  nop
0x180150b12  lea     rcx, [rbp+2A0h+var_48]
0x180150b19  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180150b1e  nop
0x180150b1f  lea     rcx, [rbp+2A0h+var_2A0]
0x180150b23  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180150b28  nop
0x180150b29  lea     rcx, [rbp+2A0h+var_200]
0x180150b30  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180150b35  nop
0x180150b36  lea     rcx, [rbp+2A0h+var_1E0]
0x180150b3d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180150b42  nop
0x180150b43  lea     rcx, [rbp+2A0h+var_1C0]
0x180150b4a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180150b4f  nop
0x180150b50  lea     rcx, [rsp+3A0h+var_340]
0x180150b55  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180150b5a  xorps   xmm0, xmm0
0x180150b5d  movups  xmmword ptr [rbp+2A0h+var_48], xmm0
0x180150b64  lea     rcx, [rbp+2A0h+var_48]
0x180150b6b  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x180150b70  nop
0x180150b71  mov     rax, qword ptr [rbp+2A0h+var_48]
0x180150b78  test    rax, rax
0x180150b7b  jz      loc_180150DA3
0x180150b81  cmp     byte ptr [rax+80h], 0
0x180150b88  jz      loc_180150DA3
0x180150b8e  xorps   xmm0, xmm0
0x180150b91  movups  [rbp+2A0h+var_2C0], xmm0
0x180150b95  xorps   xmm1, xmm1
0x180150b98  movdqu  [rbp+2A0h+var_2B0], xmm1
0x180150b9d  mov     r8, r15
0x180150ba0  lea     r14, asc_1803D71C8; "\""
0x180150ba7  mov     rdx, r14
0x180150baa  lea     rcx, [rbp+2A0h+var_2C0]
0x180150bae  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180150bb3  nop
0x180150bb4  lea     rdx, [rbp+2A0h+var_68]
0x180150bbb  lea     rcx, [rbp+2A0h+var_160]
0x180150bc2  call    ?CreateDescription@Exception@Basix@Microsoft@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVexception_ptr@5@@Z; Microsoft::Basix::Exception::CreateDescription(std::exception_ptr const &)
0x180150bc7  mov     rbx, rax
0x180150bca  cmp     qword ptr [rax+18h], 0Fh
0x180150bcf  jbe     short loc_180150BD4
0x180150bd1  mov     rbx, [rax]
0x180150bd4  xorps   xmm0, xmm0
0x180150bd7  movups  [rbp+2A0h+var_2E0], xmm0
0x180150bdb  xorps   xmm1, xmm1
0x180150bde  movdqu  [rbp+2A0h+var_2D0], xmm1
0x180150be3  mov     r8, r15
0x180150be6  mov     rdx, r14
0x180150be9  lea     rcx, [rbp+2A0h+var_2E0]
0x180150bed  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180150bf2  nop
0x180150bf3  xorps   xmm0, xmm0
0x180150bf6  movups  [rbp+2A0h+var_300], xmm0
0x180150bfa  xorps   xmm1, xmm1
0x180150bfd  movdqu  [rbp+2A0h+var_2F0], xmm1
0x180150c02  mov     r8, r15
0x180150c05  lea     rdx, asc_1803D71C4; ":"
0x180150c0c  lea     rcx, [rbp+2A0h+var_300]
0x180150c10  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180150c15  nop
0x180150c16  xorps   xmm0, xmm0
0x180150c19  movups  [rbp+2A0h+var_320], xmm0
0x180150c1d  xorps   xmm1, xmm1
0x180150c20  movdqu  [rbp+2A0h+var_310], xmm1
0x180150c25  mov     r8, r15
0x180150c28  mov     rdx, r14
0x180150c2b  lea     rcx, [rbp+2A0h+var_320]
0x180150c2f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180150c34  nop
0x180150c35  xorps   xmm0, xmm0
0x180150c38  movups  xmmword ptr [rbp+2A0h+BufferCount], xmm0
0x180150c3f  xorps   xmm1, xmm1
0x180150c42  movdqu  [rbp+2A0h+var_78], xmm1
0x180150c4a  mov     r8, r15
0x180150c4d  mov     rdx, r14
0x180150c50  lea     rcx, [rbp+2A0h+BufferCount]
0x180150c57  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180150c5c  nop
0x180150c5d  lea     r8, aException; "exception"
0x180150c64  lea     rdx, [rbp+2A0h+BufferCount]
0x180150c6b  lea     rcx, [rbp+2A0h+var_180]
0x180150c72  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180150c77  nop
0x180150c78  lea     r9, [rbp+2A0h+var_320]
0x180150c7c  mov     r8, rax
0x180150c7f  mov     dl, [rsp+3A0h+var_360]
0x180150c83  lea     rcx, [rbp+2A0h+var_220]
0x180150c8a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x180150c8f  nop
0x180150c90  lea     r9, [rbp+2A0h+var_300]
  ... truncated ...
```
