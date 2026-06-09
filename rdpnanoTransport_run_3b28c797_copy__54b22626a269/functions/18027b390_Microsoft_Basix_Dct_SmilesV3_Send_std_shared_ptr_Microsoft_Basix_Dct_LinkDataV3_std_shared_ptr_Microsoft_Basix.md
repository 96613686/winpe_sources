# Microsoft::Basix::Dct::SmilesV3::Send(std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>,std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::OutBuffer>,uchar,ushort,ushort,ushort,Microsoft::Basix::Dct::OperationOnLinkId)

- ea: `0x18027b390`
- end: `0x18027bd95`
- name: `?Send@SmilesV3@Dct@Basix@Microsoft@@AEAAXV?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@V?$shared_ptr@VOutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@@6@EGGGVOperationOnLinkId@234@@Z`
- size: `2565`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `broker_com_uri`

## callers

- `0x18025fc34`
- `0x180261ba0`
- `0x18027bd98`

## callees

- `0x180008f80`
- `0x18000d9c0`
- `0x180015bb8`
- `0x1800189b8`
- `0x180018d1c`
- `0x1800328a0`
- `0x180105b78`
- `0x1801acb74`
- `0x180230ff4`
- `0x18024cb04`
- `0x18024cc90`
- `0x18024d1a4`
- `0x18024d330`
- `0x18024d4bc`
- `0x18024e254`
- `0x18027b390`
- `0x18027f518`
- `0x18027f5c0`
- `0x18027f690`
- `0x1802ec708`
- `0x1802ed49c`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x18027b650`: `SmilesV3::Send() CLOCK_OFFSET: linkId=%d, clockOffsetInMs=%d`
- `0x18027b765`: `SmilesV3::Send() SYNCEX: linkId=%d, cntSendsInLastNMs=%d, delay=%d, m_lastSentInMs=%d`
- `0x18027b8b6`: `SmilesV3::Send() INFORM_PEER_SWITCHINFO_EX: linkId=%d, reason=%d, contextCnt=%d`
- `0x18027ba9d`: `SmilesV3::Send() INFORM_PEER_PRIMARY_LINKID_EX: linkId=%d, informPeerLinkId=%d`
- `0x18027bb84`: `SmilesV3::Send() INFORM_PEER_PRIMARY_EPOCH_EX: linkId=%d, switchEpoch=%d`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Microsoft::Basix::Dct::SmilesV3::Send(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        char a4,
        __int16 a5,
        __int16 a6,
        __int16 a7,
        __int64 a8)
{
  __int64 result; // rax
  char v13; // r12
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rdx
  double v17; // xmm6_8
  __int64 v18; // rdi
  __int16 v19; // r15
  unsigned __int8 v20; // bl
  char v21; // di
  __int16 v22; // ax
  Microsoft::Basix::Dct::IAsyncTransport::OutBuffer **v23; // r12
  struct Microsoft::Basix::Containers::FlexOBuffer *v24; // rax
  __int64 v25; // rax
  char v26; // di
  int v27; // r9d
  int v28; // ebx
  volatile signed __int32 *v29; // rbx
  int v30; // r9d
  __int64 v31; // rbx
  volatile signed __int32 *v32; // rbx
  __int64 v33; // r12
  __int64 v34; // rbx
  int v35; // r9d
  char v36; // di
  int v37; // ebx
  volatile signed __int32 *v38; // rbx
  __int64 v39; // rbx
  char v40; // di
  int v41; // r9d
  __int16 v42; // bx
  int v43; // r9d
  volatile signed __int32 *v44; // rbx
  int v45; // r9d
  __int16 v46; // bx
  volatile signed __int32 *v47; // rbx
  int v48; // r9d
  char v49; // di
  int v50; // ebx
  volatile signed __int32 *v51; // rbx
  volatile signed __int32 *v52; // rbx
  volatile signed __int32 *v53; // rbx
  volatile signed __int32 *v54; // rbx
  volatile signed __int32 *v55; // rbx
  volatile signed __int32 *v56; // rbx
  int v57; // [rsp+20h] [rbp-C9h]
  int v58; // [rsp+28h] [rbp-C1h]
  __int16 v59; // [rsp+40h] [rbp-A9h] BYREF
  _WORD v60[3]; // [rsp+42h] [rbp-A7h] BYREF
  __int128 v61; // [rsp+48h] [rbp-A1h] BYREF
  __int128 v62; // [rsp+58h] [rbp-91h]
  int v63; // [rsp+68h] [rbp-81h]
  Microsoft::Basix::Dct::IAsyncTransport::OutBuffer **v64; // [rsp+70h] [rbp-79h]
  char v65; // [rsp+78h] [rbp-71h]
  __int64 v66; // [rsp+80h] [rbp-69h]
  _QWORD *v67; // [rsp+88h] [rbp-61h]
  __int64 v68; // [rsp+90h] [rbp-59h]
  __int64 v69; // [rsp+98h] [rbp-51h]
  __int128 v70; // [rsp+A0h] [rbp-49h] BYREF
  _OWORD v71[2]; // [rsp+B8h] [rbp-31h] BYREF

  v64 = (Microsoft::Basix::Dct::IAsyncTransport::OutBuffer **)a3;
  v67 = a2;
  v69 = a3;
  v66 = a8;
  v68 = a8;
  result = std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(a2, 0);
  v13 = 0;
  if ( (_BYTE)result
    || (v14 = *a2,
        result = std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                   *a2 + 104LL,
                   0),
        (_BYTE)result) )
  {
    v55 = (volatile signed __int32 *)a2[1];
    if ( v55 )
    {
      result = (unsigned int)_InterlockedDecrement(v55 + 2);
      if ( !(_DWORD)result )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v55)(v55);
        result = (unsigned int)_InterlockedDecrement(v55 + 3);
        if ( !(_DWORD)result )
          result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v55 + 8LL))(v55);
      }
    }
    v56 = *(volatile signed __int32 **)(a3 + 8);
    if ( v56 )
    {
      result = (unsigned int)_InterlockedDecrement(v56 + 2);
      if ( !(_DWORD)result )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
        result = (unsigned int)_InterlockedDecrement(v56 + 3);
        if ( !(_DWORD)result )
          result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
      }
    }
    v54 = *(volatile signed __int32 **)(a8 + 16);
  }
  else
  {
    v60[0] = *(_WORD *)(v14 + 152);
    LOWORD(v63) = 0;
    if ( (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::num(*(_QWORD *)(a1 + 2896)) )
    {
      v13 = 1;
      v63 = (int)Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(a1 + 2896));
    }
    v15 = *a2;
    if ( (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(*a2 + 192LL)) )
      v17 = Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v15 + 192));
    else
      v17 = DOUBLE_1000_0;
    v18 = 5;
    v19 = 0;
    v20 = 0;
    v65 = a4 & 0x80;
    if ( a4 < 0 )
    {
      v21 = 2;
      if ( (a4 & 8) != 0 )
      {
        v19 = 1;
        v21 = 8;
        if ( v13 )
        {
          v19 = 3;
          v21 = 10;
        }
      }
      if ( (a4 & 2) != 0
        && *(_WORD *)(*(__int64 (__fastcall **)(__int64, __int64, _QWORD))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(
                       a1 + 3088,
                       v16,
                       0) )
      {
        v21 += 2 * ((__int64)(unsigned int)(*(_DWORD *)(a1 + 3072) - *(_DWORD *)(a1 + 3064)) >> 1) + 2;
        v19 |= 4u;
      }
      v20 = v21 + 3;
      if ( (a4 & 0x10) == 0 )
        v20 = v21;
      v22 = v19 | 0x30;
      if ( (a4 & 0x10) == 0 )
        v22 = v19;
      v19 = v22;
      if ( !*(_BYTE *)(a1 + 3177) && *(_BYTE *)v66 )
      {
        v20 += 3;
        v19 = v22 | 8;
      }
      v18 = v20 + 6LL;
    }
    memset(v71, 0, sizeof(v71));
    v23 = v64;
    v24 = Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(*v64);
    v25 = Microsoft::Basix::Containers::FlexOBuffer::Begin(v24, &v70);
    Microsoft::Basix::Containers::FlexOBuffer::Iterator::ReserveBlob(v25, v71, v18);
    LOBYTE(v59) = a4;
    Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<unsigned char>(v71, &v59);
    v59 = a5;
    Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<enum Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(
      v71,
      &v59);
    v59 = a6;
    Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<enum Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(
      v71,
      &v59);
    LOBYTE(v18) = 0;
    if ( v65 )
    {
      LOBYTE(v59) = v20;
      Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<unsigned char>(v71, &v59);
      v59 = v19;
      Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<enum Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(
        v71,
        &v59);
      if ( (v19 & 2) != 0 )
      {
        v26 = v63;
        v59 = v63;
        Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<enum Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(
          v71,
          &v59);
        v70 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v70);
        if ( (_QWORD)v70 && *(_BYTE *)(v70 + 128) )
        {
          v28 = *(_DWORD *)(*a2 + 152LL);
          v61 = 0;
          v62 = 0;
          std::string::_Construct<1,char const *>(
            &v61,
            "SmilesV3::Send() CLOCK_OFFSET: linkId=%d, clockOffsetInMs=%d",
            60,
            v27);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,short>(
            (unsigned int)&v70,
            (unsigned int)"BASIX_DCT",
            (unsigned int)&v61,
            v28,
            v26);
          std::string::_Tidy_deallocate(&v61);
        }
        v29 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
        LOBYTE(v18) = 0;
        if ( *((_QWORD *)&v70 + 1) )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v70 + 1) + 8LL)) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
            if ( !_InterlockedDecrement(v29 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
          }
        }
      }
      if ( (v19 & 1) != 0 )
      {
        v59 = a7;
        Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<enum Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(
          v71,
          &v59);
        v59 = (int)v17;
        Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<enum Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(
          v71,
          &v59);
        Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<enum Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(
          v71,
          v60);
        v70 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v70);
        if ( (_QWORD)v70 && *(_BYTE *)(v70 + 128) )
        {
          v31 = *(_QWORD *)(a1 + 2880);
          LODWORD(v18) = *(_DWORD *)(*a2 + 152LL);
          v61 = 0;
          v62 = 0;
          std::string::_Construct<1,char const *>(
            &v61,
            "SmilesV3::Send() SYNCEX: linkId=%d, cntSendsInLastNMs=%d, delay=%d, m_lastSentInMs=%d",
            85,
            v30,
            v57,
            v58);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,unsigned short,short,unsigned __int64>(
            (unsigned int)&v70,
            (unsigned int)"BASIX_DCT",
            (unsigned int)&v61,
            v18,
            a7,
            (int)v17,
            v31);
          std::string::_Tidy_deallocate(&v61);
          LOBYTE(v18) = 0;
        }
        v32 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
        if ( *((_QWORD *)&v70 + 1) )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v70 + 1) + 8LL)) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
            if ( !_InterlockedDecrement(v32 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
          }
        }
      }
      if ( (v19 & 4) != 0 )
      {
        LOBYTE(v59) = *(_BYTE *)(a1 + 3056);
        Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<unsigned char>(v71, &v59);
        v33 = (__int64)(unsigned int)(*(_DWORD *)(a1 + 3072) - *(_DWORD *)(a1 + 3064)) >> 1;
        LOBYTE(v59) = v33;
        Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<unsigned char>(v71, &v59);
        if ( (_BYTE)v33 )
        {
          v34 = 0;
          v18 = (unsigned __int8)v33;
          do
          {
            v60[0] = *(_WORD *)(v34 + *(_QWORD *)(a1 + 3064));
            Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<enum Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(
              v71,
              v60);
            v34 += 2;
            --v18;
          }
          while ( v18 );
        }
        v70 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v70);
        if ( (_QWORD)v70 && *(_BYTE *)(v70 + 128) != (_BYTE)v18 )
        {
          v36 = *(_BYTE *)(a1 + 3056);
          v37 = *(_DWORD *)(*a2 + 152LL);
          v61 = 0;
          v62 = 0;
          std::string::_Construct<1,char const *>(
            &v61,
            "SmilesV3::Send() INFORM_PEER_SWITCHINFO_EX: linkId=%d, reason=%d, contextCnt=%d",
            79,
            v35,
            v57);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,enum Microsoft::Basix::Dct::SmilesV3::SwitchReasonCode,unsigned char>(
            (unsigned int)&v70,
            (unsigned int)"BASIX_DCT",
            (unsigned int)&v61,
            v37,
            v36,
            v33);
          std::string::_Tidy_deallocate(&v61);
          LOBYTE(v18) = 0;
        }
        v38 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
        if ( *((_QWORD *)&v70 + 1) )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v70 + 1) + 8LL)) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
            if ( !_InterlockedDecrement(v38 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
          }
        }
        v23 = v64;
      }
      if ( (v19 & 8) != 0 )
      {
        v39 = v66;
        v40 = *(_BYTE *)v66;
        LOBYTE(v59) = *(_BYTE *)v66;
        Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<unsigned char>(v71, &v59);
        v60[0] = *(_WORD *)(v39 + 4);
        Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<enum Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(
          v71,
          v60);
        v70 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v70);
        if ( (_QWORD)v70 && *(_BYTE *)(v70 + 128) )
        {
          v42 = *(_WORD *)(v39 + 2);
          v61 = 0;
          v62 = 0;
          std::string::_Construct<1,char const *>(
            &v61,
            "SmilesV3::Send() INFORM_PEER_OPERATION_EX: operationMode=%d, operationId=%d",
            75,
            v41);
          LOBYTE(v43) = v40;
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned char,unsigned short>(
            (unsigned int)&v70,
            (unsigned int)"BASIX_DCT",
            (unsigned int)&v61,
            v43,
            v42);
          std::string::_Tidy_deallocate(&v61);
        }
        v44 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
        LOBYTE(v18) = 0;
        if ( *((_QWORD *)&v70 + 1) )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v70 + 1) + 8LL)) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
            if ( !_InterlockedDecrement(v44 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
          }
        }
      }
      if ( (v19 & 0x10) != 0 )
      {
        v60[0] = *(_WORD *)(*a2 + 240LL);
        Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<enum Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(
          v71,
          v60);
        v70 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v70);
        if ( (_QWORD)v70 && *(_BYTE *)(v70 + 128) != (_BYTE)v18 )
        {
          v46 = *(_WORD *)(*a2 + 240LL);
          LODWORD(v18) = *(_DWORD *)(*a2 + 152LL);
          v61 = 0;
          v62 = 0;
          std::string::_Construct<1,char const *>(
            &v61,
            "SmilesV3::Send() INFORM_PEER_PRIMARY_LINKID_EX: linkId=%d, informPeerLinkId=%d",
            78,
            v45);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,unsigned short>(
            (unsigned int)&v70,
            (unsigned int)"BASIX_DCT",
            (unsigned int)&v61,
            v18,
            v46);
          std::string::_Tidy_deallocate(&v61);
          LOBYTE(v18) = 0;
        }
        v47 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
        if ( *((_QWORD *)&v70 + 1) )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v70 + 1) + 8LL)) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
            if ( !_InterlockedDecrement(v47 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
          }
        }
      }
      if ( (v19 & 0x20) != 0 )
      {
        LOBYTE(v59) = *(_BYTE *)(a1 + 3090);
        Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<unsigned char>(v71, &v59);
        v70 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v70);
        if ( (_QWORD)v70 && *(_BYTE *)(v70 + 128) != (_BYTE)v18 )
        {
          v49 = *(_BYTE *)(a1 + 3090);
          v50 = *(_DWORD *)(*a2 + 152LL);
          v61 = 0;
          v62 = 0;
          std::string::_Construct<1,char const *>(
            &v61,
            "SmilesV3::Send() INFORM_PEER_PRIMARY_EPOCH_EX: linkId=%d, switchEpoch=%d",
            72,
            v48);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,unsigned char>(
            (unsigned int)&v70,
            (unsigned int)"BASIX_DCT",
            (unsigned int)&v61,
            v50,
            v49);
          std::string::_Tidy_deallocate(&v61);
        }
        v51 = (volatile signed __int32 *)*((_QWORD *)&v70 + 1);
        if ( *((_QWORD *)&v70 + 1) )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v70 + 1) + 8LL)) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v51)(v51);
            if ( !_InterlockedDecrement(v51 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v51 + 8LL))(v51);
          }
        }
      }
    }
    Microsoft::Basix::Dct::LogSendUserData(v23, *(unsigned int *)(*a2 + 152LL));
    Microsoft::Basix::Dct::IAsyncTransport::QueueWrite(*(_QWORD *)(*a2 + 104LL), v23);
    v52 = (volatile signed __int32 *)a2[1];
    if ( v52 )
    {
      if ( _InterlockedExchangeAdd(v52 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
        if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
      }
    }
    v53 = (volatile signed __int32 *)v23[1];
    if ( v53 )
    {
      if ( _InterlockedExchangeAdd(v53 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
        if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
      }
    }
    result = v66;
    v54 = *(volatile signed __int32 **)(v66 + 16);
  }
  if ( v54 )
  {
    result = (unsigned int)_InterlockedDecrement(v54 + 2);
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
      result = (unsigned int)_InterlockedDecrement(v54 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18027b390  mov     [rsp-8+arg_18], rbx
0x18027b395  push    rbp
0x18027b396  push    rsi
0x18027b397  push    rdi
0x18027b398  push    r12
0x18027b39a  push    r13
0x18027b39c  push    r14
0x18027b39e  push    r15
0x18027b3a0  lea     rbp, [rsp-7]
0x18027b3a5  mov     eax, 0F0h
0x18027b3aa  call    _alloca_probe
0x18027b3af  sub     rsp, rax
0x18027b3b2  movaps  [rsp+120h+var_40], xmm6
0x18027b3ba  mov     rax, cs:__security_cookie
0x18027b3c1  xor     rax, rsp
0x18027b3c4  mov     [rbp+37h+var_48], rax
0x18027b3c8  mov     sil, r9b
0x18027b3cb  mov     rdi, r8
0x18027b3ce  mov     [rbp+37h+var_B0], r8
0x18027b3d2  mov     r14, rdx
0x18027b3d5  mov     r13, rcx
0x18027b3d8  mov     [rbp+37h+var_98], rdx
0x18027b3dc  mov     [rbp+37h+var_88], r8
0x18027b3e0  mov     r15, [rbp+37h+arg_38]
0x18027b3e4  mov     [rbp+37h+var_A0], r15
0x18027b3e8  mov     [rbp+37h+var_90], r15
0x18027b3ec  xor     edx, edx
0x18027b3ee  mov     rcx, r14
0x18027b3f1  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x18027b3f6  xor     r12d, r12d
0x18027b3f9  test    al, al
0x18027b3fb  jnz     loc_18027BCAA
0x18027b401  mov     rbx, [r14]
0x18027b404  lea     rcx, [rbx+68h]
0x18027b408  xor     edx, edx
0x18027b40a  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x18027b40f  test    al, al
0x18027b411  jnz     loc_18027BCAA
0x18027b417  movzx   eax, word ptr [rbx+98h]
0x18027b41e  mov     [rsp+120h+var_DE], ax
0x18027b423  mov     word ptr [rsp+120h+var_B8], r12w
0x18027b429  mov     rcx, [r13+0B50h]
0x18027b430  call    ?num@?$SlidingStats@N$0BE@$00$00@Algorithm@Basix@Microsoft@@QEAAHXZ; Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::num(void)
0x18027b435  test    eax, eax
0x18027b437  jz      short loc_18027B450
0x18027b439  mov     r12b, 1
0x18027b43c  mov     rcx, [r13+0B50h]
0x18027b443  call    ?nmin@?$SlidingStats@N$0BE@$00$00@Algorithm@Basix@Microsoft@@QEAANXZ; Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(void)
0x18027b448  cvttsd2si eax, xmm0
0x18027b44c  mov     [rsp+120h+var_B8], eax
0x18027b450  mov     rbx, [r14]
0x18027b453  mov     rcx, [rbx+0C0h]
0x18027b45a  call    ?num@?$SlidingStats@N$04$00$00@Algorithm@Basix@Microsoft@@QEAAHXZ; Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(void)
0x18027b45f  xor     r8d, r8d
0x18027b462  test    eax, eax
0x18027b464  jz      short loc_18027B47A
0x18027b466  mov     rcx, [rbx+0C0h]
0x18027b46d  call    ?nmin@?$SlidingStats@N$0BE@$00$00@Algorithm@Basix@Microsoft@@QEAANXZ; Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(void)
0x18027b472  movaps  xmm6, xmm0
0x18027b475  xor     r8d, r8d
0x18027b478  jmp     short loc_18027B482
0x18027b47a  movsd   xmm6, cs:__real@408f400000000000
0x18027b482  mov     edi, 5
0x18027b487  movzx   r15d, r8w
0x18027b48b  mov     bl, r8b
0x18027b48e  mov     al, sil
0x18027b491  and     al, 80h
0x18027b493  mov     [rbp+37h+var_A8], al
0x18027b496  jz      loc_18027B544
0x18027b49c  mov     dil, 2
0x18027b49f  mov     ebx, 3
0x18027b4a4  test    sil, 8
0x18027b4a8  jz      short loc_18027B4BD
0x18027b4aa  lea     r15d, [rbx-2]
0x18027b4ae  mov     dil, 8
0x18027b4b1  test    r12b, r12b
0x18027b4b4  jz      short loc_18027B4BD
0x18027b4b6  movzx   r15d, bx
0x18027b4ba  mov     dil, 0Ah
0x18027b4bd  test    sil, 2
0x18027b4c1  jz      short loc_18027B4F8
0x18027b4c3  lea     rcx, [r13+0C10h]
0x18027b4ca  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18027b4cf  movzx   ecx, word ptr [rax]
0x18027b4d2  nop
0x18027b4d3  xor     r8d, r8d
0x18027b4d6  test    cx, cx
0x18027b4d9  jz      short loc_18027B4F8
0x18027b4db  mov     eax, [r13+0C00h]
0x18027b4e2  sub     eax, [r13+0BF8h]
0x18027b4e9  sar     rax, 1
0x18027b4ec  add     al, al
0x18027b4ee  add     al, 2
0x18027b4f0  add     dil, al
0x18027b4f3  or      r15w, 4
0x18027b4f8  lea     eax, [rbx+rdi]
0x18027b4fb  movzx   ebx, al
0x18027b4fe  movzx   eax, dil
0x18027b502  test    sil, 10h
0x18027b506  cmovz   ebx, eax
0x18027b509  mov     dl, bl
0x18027b50b  movzx   eax, r15w
0x18027b50f  or      ax, 30h
0x18027b513  test    sil, 10h
0x18027b517  cmovz   ax, r15w
0x18027b51c  movzx   r15d, ax
0x18027b520  cmp     [r13+0C69h], r8b
0x18027b527  jnz     short loc_18027B53D
0x18027b529  mov     rcx, [rbp+37h+var_A0]
0x18027b52d  cmp     [rcx], r8b
0x18027b530  jz      short loc_18027B53D
0x18027b532  lea     ebx, [rdx+3]
0x18027b535  or      ax, 8
0x18027b539  movzx   r15d, ax
0x18027b53d  movzx   edi, bl
0x18027b540  add     rdi, 6
0x18027b544  xorps   xmm0, xmm0
0x18027b547  movups  [rbp+37h+var_68], xmm0
0x18027b54b  movups  [rbp+37h+var_58], xmm0
0x18027b54f  mov     r12, [rbp+37h+var_B0]
0x18027b553  mov     rcx, [r12]; this
0x18027b557  call    ?FlexO@OutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@QEAAAEAVFlexOBuffer@Containers@45@XZ; Microsoft::Basix::Dct::IAsyncTransport::OutBuffer::FlexO(void)
0x18027b55c  lea     rdx, [rbp+37h+var_80]
0x18027b560  mov     rcx, rax
0x18027b563  call    ?Begin@FlexOBuffer@Containers@Basix@Microsoft@@QEBA?AVIterator@1234@XZ; Microsoft::Basix::Containers::FlexOBuffer::Begin(void)
0x18027b568  mov     r8, rdi
0x18027b56b  lea     rdx, [rbp+37h+var_68]
0x18027b56f  mov     rcx, rax
0x18027b572  call    ?ReserveBlob@Iterator@FlexOBuffer@Containers@Basix@Microsoft@@QEAA?AVInserter@2345@_K@Z; Microsoft::Basix::Containers::FlexOBuffer::Iterator::ReserveBlob(unsigned __int64)
0x18027b577  mov     byte ptr [rsp+120h+var_E0], sil
0x18027b57c  lea     rdx, [rsp+120h+var_E0]
0x18027b581  lea     rcx, [rbp+37h+var_68]
0x18027b585  call    ??$Inject@E@Inserter@FlexOBuffer@Containers@Basix@Microsoft@@QEAAPEBXAEBE@Z; Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<uchar>(uchar const &)
0x18027b58a  movzx   eax, [rbp+37h+arg_20]
0x18027b58e  mov     [rsp+120h+var_E0], ax
0x18027b593  lea     rdx, [rsp+120h+var_E0]
0x18027b598  lea     rcx, [rbp+37h+var_68]
0x18027b59c  call    ??$Inject@W4Attribute@STUNMessage@ICE@Dct@Basix@Microsoft@@@Inserter@FlexOBuffer@Containers@Basix@Microsoft@@QEAAPEBXAEBW4Attribute@STUNMessage@ICE@Dct@34@@Z; Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(Microsoft::Basix::Dct::ICE::STUNMessage::Attribute const &)
0x18027b5a1  movzx   eax, [rbp+37h+arg_28]
0x18027b5a5  mov     [rsp+120h+var_E0], ax
0x18027b5aa  lea     rdx, [rsp+120h+var_E0]
0x18027b5af  lea     rcx, [rbp+37h+var_68]
0x18027b5b3  call    ??$Inject@W4Attribute@STUNMessage@ICE@Dct@Basix@Microsoft@@@Inserter@FlexOBuffer@Containers@Basix@Microsoft@@QEAAPEBXAEBW4Attribute@STUNMessage@ICE@Dct@34@@Z; Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(Microsoft::Basix::Dct::ICE::STUNMessage::Attribute const &)
0x18027b5b8  or      esi, 0FFFFFFFFh
0x18027b5bb  xor     edi, edi
0x18027b5bd  cmp     [rbp+37h+var_A8], dil
0x18027b5c1  jz      loc_18027BBFD
0x18027b5c7  mov     byte ptr [rsp+120h+var_E0], bl
0x18027b5cb  lea     rdx, [rsp+120h+var_E0]
0x18027b5d0  lea     rcx, [rbp+37h+var_68]
0x18027b5d4  call    ??$Inject@E@Inserter@FlexOBuffer@Containers@Basix@Microsoft@@QEAAPEBXAEBE@Z; Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<uchar>(uchar const &)
0x18027b5d9  mov     [rsp+120h+var_E0], r15w
0x18027b5df  lea     rdx, [rsp+120h+var_E0]
0x18027b5e4  lea     rcx, [rbp+37h+var_68]
0x18027b5e8  call    ??$Inject@W4Attribute@STUNMessage@ICE@Dct@Basix@Microsoft@@@Inserter@FlexOBuffer@Containers@Basix@Microsoft@@QEAAPEBXAEBW4Attribute@STUNMessage@ICE@Dct@34@@Z; Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(Microsoft::Basix::Dct::ICE::STUNMessage::Attribute const &)
0x18027b5ed  test    r15b, 2
0x18027b5f1  jz      loc_18027B6CB
0x18027b5f7  mov     edi, [rsp+120h+var_B8]
0x18027b5fb  mov     [rsp+120h+var_E0], di
0x18027b600  lea     rdx, [rsp+120h+var_E0]
0x18027b605  lea     rcx, [rbp+37h+var_68]
0x18027b609  call    ??$Inject@W4Attribute@STUNMessage@ICE@Dct@Basix@Microsoft@@@Inserter@FlexOBuffer@Containers@Basix@Microsoft@@QEAAPEBXAEBW4Attribute@STUNMessage@ICE@Dct@34@@Z; Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(Microsoft::Basix::Dct::ICE::STUNMessage::Attribute const &)
0x18027b60e  xorps   xmm0, xmm0
0x18027b611  movups  [rbp+37h+var_80], xmm0
0x18027b615  lea     rcx, [rbp+37h+var_80]
0x18027b619  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18027b61e  nop
0x18027b61f  mov     rax, qword ptr [rbp+37h+var_80]
0x18027b623  xor     ecx, ecx
0x18027b625  test    rax, rax
0x18027b628  jz      short loc_18027B68B
0x18027b62a  cmp     [rax+80h], cl
0x18027b630  jz      short loc_18027B68B
0x18027b632  mov     rax, [r14]
0x18027b635  mov     ebx, [rax+98h]
0x18027b63b  xorps   xmm0, xmm0
0x18027b63e  movups  [rsp+120h+var_D8], xmm0
0x18027b643  xorps   xmm1, xmm1
0x18027b646  movdqu  [rsp+120h+var_C8], xmm1
0x18027b64c  lea     r8d, [rsi+3Dh]
0x18027b650  lea     rdx, aSmilesv3SendCl; "SmilesV3::Send() CLOCK_OFFSET: linkId=%"...
0x18027b657  lea     rcx, [rsp+120h+var_D8]
0x18027b65c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027b661  nop
0x18027b662  mov     [rsp+120h+var_100], di
0x18027b667  mov     r9d, ebx
0x18027b66a  lea     r8, [rsp+120h+var_D8]
0x18027b66f  lea     rdx, aBasixDct; "BASIX_DCT"
0x18027b676  lea     rcx, [rbp+37h+var_80]
0x18027b67a  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@IF@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@IF@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,uint,short>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,uint,short)
0x18027b67f  nop
0x18027b680  lea     rcx, [rsp+120h+var_D8]
0x18027b685  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027b68a  nop
0x18027b68b  mov     rbx, qword ptr [rbp+37h+var_80+8]
0x18027b68f  xor     edi, edi
0x18027b691  test    rbx, rbx
0x18027b694  jz      short loc_18027B6CB
0x18027b696  mov     eax, esi
0x18027b698  lock xadd [rbx+8], eax
0x18027b69d  add     eax, esi
0x18027b69f  jnz     short loc_18027B6CB
0x18027b6a1  mov     rax, [rbx]
0x18027b6a4  mov     rcx, rbx
0x18027b6a7  mov     rax, [rax]
0x18027b6aa  call    cs:__guard_dispatch_icall_fptr
0x18027b6b0  mov     eax, esi
0x18027b6b2  lock xadd [rbx+0Ch], eax
0x18027b6b7  add     eax, esi
0x18027b6b9  jnz     short loc_18027B6CB
0x18027b6bb  mov     rax, [rbx]
0x18027b6be  mov     rcx, rbx
0x18027b6c1  mov     rax, [rax+8]
0x18027b6c5  call    cs:__guard_dispatch_icall_fptr
0x18027b6cb  test    r15b, 1
0x18027b6cf  jz      loc_18027B7F1
0x18027b6d5  movzx   eax, [rbp+37h+arg_30]
0x18027b6d9  mov     [rsp+120h+var_E0], ax
0x18027b6de  lea     rdx, [rsp+120h+var_E0]
0x18027b6e3  lea     rcx, [rbp+37h+var_68]
0x18027b6e7  call    ??$Inject@W4Attribute@STUNMessage@ICE@Dct@Basix@Microsoft@@@Inserter@FlexOBuffer@Containers@Basix@Microsoft@@QEAAPEBXAEBW4Attribute@STUNMessage@ICE@Dct@34@@Z; Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(Microsoft::Basix::Dct::ICE::STUNMessage::Attribute const &)
0x18027b6ec  cvttsd2si eax, xmm6
0x18027b6f0  mov     [rsp+120h+var_E0], ax
0x18027b6f5  lea     rdx, [rsp+120h+var_E0]
0x18027b6fa  lea     rcx, [rbp+37h+var_68]
0x18027b6fe  call    ??$Inject@W4Attribute@STUNMessage@ICE@Dct@Basix@Microsoft@@@Inserter@FlexOBuffer@Containers@Basix@Microsoft@@QEAAPEBXAEBW4Attribute@STUNMessage@ICE@Dct@34@@Z; Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(Microsoft::Basix::Dct::ICE::STUNMessage::Attribute const &)
0x18027b703  movzx   eax, [rsp+120h+var_DE]
0x18027b708  mov     [rsp+120h+var_DE], ax
0x18027b70d  lea     rdx, [rsp+120h+var_DE]
0x18027b712  lea     rcx, [rbp+37h+var_68]
0x18027b716  call    ??$Inject@W4Attribute@STUNMessage@ICE@Dct@Basix@Microsoft@@@Inserter@FlexOBuffer@Containers@Basix@Microsoft@@QEAAPEBXAEBW4Attribute@STUNMessage@ICE@Dct@34@@Z; Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<Microsoft::Basix::Dct::ICE::STUNMessage::Attribute>(Microsoft::Basix::Dct::ICE::STUNMessage::Attribute const &)
0x18027b71b  xorps   xmm0, xmm0
0x18027b71e  movups  [rbp+37h+var_80], xmm0
0x18027b722  lea     rcx, [rbp+37h+var_80]
0x18027b726  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18027b72b  nop
0x18027b72c  mov     rax, qword ptr [rbp+37h+var_80]
0x18027b730  test    rax, rax
0x18027b733  jz      short loc_18027B7B3
0x18027b735  cmp     [rax+80h], dil
0x18027b73c  jz      short loc_18027B7B3
0x18027b73e  mov     rbx, [r13+0B40h]
0x18027b745  mov     rax, [r14]
0x18027b748  mov     edi, [rax+98h]
0x18027b74e  xorps   xmm0, xmm0
0x18027b751  movups  [rsp+120h+var_D8], xmm0
0x18027b756  xorps   xmm1, xmm1
0x18027b759  movdqu  [rsp+120h+var_C8], xmm1
0x18027b75f  mov     r8d, 55h ; 'U'
0x18027b765  lea     rdx, aSmilesv3SendSy; "SmilesV3::Send() SYNCEX: linkId=%d, cnt"...
0x18027b76c  lea     rcx, [rsp+120h+var_D8]
0x18027b771  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027b776  nop
0x18027b777  mov     [rsp+120h+var_F0], rbx
0x18027b77c  cvttsd2si eax, xmm6
0x18027b780  mov     [rsp+120h+var_F8], ax
0x18027b785  movzx   eax, [rbp+37h+arg_30]
0x18027b789  mov     [rsp+120h+var_100], ax
0x18027b78e  mov     r9d, edi
0x18027b791  lea     r8, [rsp+120h+var_D8]
0x18027b796  lea     rdx, aBasixDct; "BASIX_DCT"
0x18027b79d  lea     rcx, [rbp+37h+var_80]
0x18027b7a1  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@IGF_K@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@IGF_K@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,uint,ushort,short,unsigned __int64>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,uint,ushort,short,unsigned __int64)
0x18027b7a6  nop
0x18027b7a7  lea     rcx, [rsp+120h+var_D8]
0x18027b7ac  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027b7b1  xor     edi, edi
0x18027b7b3  mov     rbx, qword ptr [rbp+37h+var_80+8]
0x18027b7b7  test    rbx, rbx
0x18027b7ba  jz      short loc_18027B7F1
0x18027b7bc  mov     eax, esi
0x18027b7be  lock xadd [rbx+8], eax
0x18027b7c3  add     eax, esi
0x18027b7c5  jnz     short loc_18027B7F1
0x18027b7c7  mov     rax, [rbx]
0x18027b7ca  mov     rcx, rbx
0x18027b7cd  mov     rax, [rax]
0x18027b7d0  call    cs:__guard_dispatch_icall_fptr
0x18027b7d6  mov     eax, esi
0x18027b7d8  lock xadd [rbx+0Ch], eax
0x18027b7dd  add     eax, esi
0x18027b7df  jnz     short loc_18027B7F1
0x18027b7e1  mov     rax, [rbx]
0x18027b7e4  mov     rcx, rbx
0x18027b7e7  mov     rax, [rax+8]
0x18027b7eb  call    cs:__guard_dispatch_icall_fptr
0x18027b7f1  test    r15b, 4
0x18027b7f5  jz      loc_18027B939
0x18027b7fb  mov     al, [r13+0BF0h]
0x18027b802  mov     byte ptr [rsp+120h+var_E0], al
0x18027b806  lea     rdx, [rsp+120h+var_E0]
0x18027b80b  lea     rcx, [rbp+37h+var_68]
0x18027b80f  call    ??$Inject@E@Inserter@FlexOBuffer@Containers@Basix@Microsoft@@QEAAPEBXAEBE@Z; Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<uchar>(uchar const &)
0x18027b814  mov     r12d, [r13+0C00h]
0x18027b81b  sub     r12d, [r13+0BF8h]
0x18027b822  sar     r12, 1
0x18027b825  mov     byte ptr [rsp+120h+var_E0], r12b
0x18027b82a  lea     rdx, [rsp+120h+var_E0]
0x18027b82f  lea     rcx, [rbp+37h+var_68]
0x18027b833  call    ??$Inject@E@Inserter@FlexOBuffer@Containers@Basix@Microsoft@@QEAAPEBXAEBE@Z; Microsoft::Basix::Containers::FlexOBuffer::Inserter::Inject<uchar>(uchar const &)
  ... truncated ...
```
