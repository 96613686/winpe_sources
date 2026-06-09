# Microsoft::Basix::Dct::SmilesV3::CheckToSuspendTimeoutLinks(void)

- ea: `0x18025e404`
- end: `0x18025f40e`
- name: `?CheckToSuspendTimeoutLinks@SmilesV3@Dct@Basix@Microsoft@@AEAAXXZ`
- size: `4106`
- prototype: `void __fastcall(Microsoft::Basix::Dct::SmilesV3 *__hidden this)`
- caller_count: `1`
- callee_count: `40`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18027dd10`

## callees

- `0x18000d9c0`
- `0x1800111fc`
- `0x180015bb8`
- `0x180017338`
- `0x180017380`
- `0x180018b94`
- `0x18001902c`
- `0x1800191b4`
- `0x18001ab4c`
- `0x18001ae64`
- `0x18001bbdc`
- `0x18001db78`
- `0x180024760`
- `0x180028100`
- `0x18002a8f4`
- `0x18003c308`
- `0x18004e1dc`
- `0x1800c3524`
- `0x1800c3bc8`
- `0x1800d621c`
- `0x18024774c`
- `0x180251b74`
- `0x180251c80`
- `0x180251ea8`
- `0x1802571d0`
- `0x18025e404`
- `0x18026c8c8`
- `0x1802741d0`
- `0x18027bd98`
- `0x18027c6e8`
- `0x18027e8d8`
- `0x18027f134`
- `0x18027f2f8`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## string_xrefs

- `0x18025e8bb`: `SmilesV3:  primary link(%d) hasn't received any packets in the last 4500ms, suspending it now and switch to a different link(%d)`
- `0x18025e931`: `SmilesV3:  primary link(%d) hasn't received any packets in the last 4500ms, suspending it now. But no link to switch to`
- `0x18025ea06`: `SmilesV3:  secondary link(%d) hasn't received any packets in the last 4500ms, suspending it now`
- `0x18025eaff`: `SmilesV3: Pending link-to-switch-to just suspended, calling MarkSwitchToNoLock to select a different link-to-switch-to`
- `0x18025eddf`: `SmilesV3:  all links are suspended due to timeout`
- `0x18025ef31`: `linkTopIndex`
- `0x18025f015`: `NumNonICELinksSuspendedInThisRound`
- `0x18025f0f9`: `NumLinksSuspendedInThisRound`
- `0x18025f18c`: `All Links suspended due to timeout`
- `0x18025f198`: `LinkSuspendAll`

## pseudocode

```c
// Hidden C++ exception states: #wind=59
void __fastcall Microsoft::Basix::Dct::SmilesV3::CheckToSuspendTimeoutLinks(
        Microsoft::Basix::Dct::SmilesV3 *this,
        __int64 a2)
{
  __m128i v3; // xmm6
  unsigned __int64 v4; // rsi
  int v5; // r12d
  unsigned int v6; // r14d
  unsigned int v7; // r13d
  struct _Mtx_internal_imp_t *v8; // rbx
  _QWORD *v9; // rdi
  __int64 v10; // rcx
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rax
  struct Microsoft::Basix::Dct::OperationOnLinkId *v15; // rdx
  __int64 v16; // rcx
  volatile signed __int32 *v17; // rdi
  char *v18; // r14
  __int64 v19; // r13
  __int64 v20; // rax
  __int64 v21; // rsi
  volatile signed __int32 *v22; // r12
  __int16 v23; // di
  __int64 v24; // rax
  volatile signed __int32 *v25; // rdi
  int v26; // r9d
  int v27; // edi
  int v28; // esi
  unsigned int v29; // edi
  volatile signed __int32 *v30; // rdi
  unsigned int v31; // edi
  volatile signed __int32 *v32; // rdi
  volatile signed __int32 *v33; // rdi
  __int64 v34; // rax
  volatile signed __int32 *v35; // rdi
  const struct Microsoft::Basix::Dct::OperationOnLinkId *v36; // rbx
  struct Microsoft::Basix::Dct::OperationOnLinkId *v37; // rdi
  volatile signed __int32 *v38; // rdi
  volatile signed __int32 *v39; // rbx
  unsigned int v40; // r14d
  volatile signed __int32 *v41; // rsi
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rdx
  __int64 v49; // rdx
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int64 v53; // rdx
  volatile signed __int32 *v54; // rsi
  int v55; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v56; // [rsp+58h] [rbp-A8h]
  __int128 v57; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v58; // [rsp+70h] [rbp-90h]
  int v59; // [rsp+80h] [rbp-80h]
  unsigned int v60; // [rsp+84h] [rbp-7Ch]
  struct Microsoft::Basix::Dct::OperationOnLinkId *v61; // [rsp+88h] [rbp-78h] BYREF
  __m128i v62; // [rsp+90h] [rbp-70h] BYREF
  __m128i v63; // [rsp+B0h] [rbp-50h] BYREF
  __int64 *v64; // [rsp+C0h] [rbp-40h]
  _OWORD v65[2]; // [rsp+C8h] [rbp-38h] BYREF
  char v66[8]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v67; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v68; // [rsp+100h] [rbp+0h]
  __int16 v69; // [rsp+108h] [rbp+8h]
  char v70; // [rsp+10Ah] [rbp+Ah]
  __int64 v71; // [rsp+110h] [rbp+10h]
  _OWORD v72[2]; // [rsp+118h] [rbp+18h] BYREF
  _OWORD v73[2]; // [rsp+138h] [rbp+38h] BYREF
  _OWORD v74[2]; // [rsp+158h] [rbp+58h] BYREF
  _OWORD v75[2]; // [rsp+178h] [rbp+78h] BYREF
  _OWORD v76[2]; // [rsp+198h] [rbp+98h] BYREF
  __int64 v77[4]; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v78[4]; // [rsp+1D8h] [rbp+D8h] BYREF
  __int64 v79[4]; // [rsp+1F8h] [rbp+F8h] BYREF
  _BYTE v80[32]; // [rsp+218h] [rbp+118h] BYREF
  _BYTE v81[32]; // [rsp+238h] [rbp+138h] BYREF
  _BYTE v82[32]; // [rsp+258h] [rbp+158h] BYREF
  _BYTE v83[32]; // [rsp+278h] [rbp+178h] BYREF
  _BYTE v84[32]; // [rsp+298h] [rbp+198h] BYREF
  _BYTE v85[32]; // [rsp+2B8h] [rbp+1B8h] BYREF
  _BYTE v86[32]; // [rsp+2D8h] [rbp+1D8h] BYREF
  _BYTE v87[32]; // [rsp+2F8h] [rbp+1F8h] BYREF
  _BYTE v88[32]; // [rsp+318h] [rbp+218h] BYREF
  _BYTE v89[32]; // [rsp+338h] [rbp+238h] BYREF
  _BYTE v90[32]; // [rsp+358h] [rbp+258h] BYREF
  __int128 v91; // [rsp+378h] [rbp+278h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+388h] [rbp+288h] BYREF
  int v93[4]; // [rsp+3A8h] [rbp+2A8h] BYREF
  __int128 v94; // [rsp+3B8h] [rbp+2B8h] BYREF
  __int128 v95; // [rsp+3C8h] [rbp+2C8h]
  struct Microsoft::Basix::Dct::OperationOnLinkId *v96[2]; // [rsp+3D8h] [rbp+2D8h] BYREF
  struct Microsoft::Basix::Dct::OperationOnLinkId *v97; // [rsp+3E8h] [rbp+2E8h]

  *(_OWORD *)v96 = 0;
  v97 = 0;
  v3 = 0;
  v63 = 0;
  v94 = 0;
  v95 = 0;
  v62 = 0;
  LOBYTE(a2) = 1;
  Microsoft::Basix::Dct::OperationOnLinkId::OperationOnLinkId(&v94, a2, 0, &v62);
  v4 = *(_QWORD *)std::chrono::steady_clock::now(&v61) / 1000000LL - *((_QWORD *)this + 376);
  v5 = 0;
  v6 = 0;
  v7 = 0;
  v8 = (Microsoft::Basix::Dct::SmilesV3 *)((char *)this + 1832);
  v64 = (__int64 *)((char *)this + 1832);
  if ( Mtx_lock((Microsoft::Basix::Dct::SmilesV3 *)((char *)this + 1832)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)this + 477) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 477) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v91 = 0;
  Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
    &v91,
    (char *)this + 1528);
  v62 = 0;
  while ( (_QWORD)v91 )
  {
    v9 = (_QWORD *)*((_QWORD *)&v91 + 1);
    v10 = **((_QWORD **)&v91 + 1);
    if ( v4 <= *(_QWORD *)(**((_QWORD **)&v91 + 1) + 336LL) + 4500LL || !*(_BYTE *)(v10 + 352) || *(_DWORD *)(v10 + 280) )
    {
      if ( !*(_DWORD *)(v10 + 280) )
        ++v5;
    }
    else
    {
      v11 = v7 + 1;
      if ( *(_DWORD *)(v10 + 80) != 9 )
        v11 = v7;
      v7 = v11;
      ++v6;
      Microsoft::Basix::Dct::LinkDataV3::SetInSuspend((Microsoft::Basix::Dct::LinkDataV3 *)v10);
      Microsoft::Basix::Dct::SmilesV3::Summary::UpdateLinkStatus((char *)this + 2056, *(unsigned int *)(*v9 + 80LL), 0);
      memset(pExceptionObject, 0, sizeof(pExceptionObject));
      v14 = v9[1];
      if ( v14 )
        _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
      *(_QWORD *)v93 = *v9;
      *(_QWORD *)&v93[2] = v9[1];
      LOBYTE(v13) = 4;
      LOBYTE(v12) = 1;
      Microsoft::Basix::Dct::OperationOnLinkId::OperationOnLinkId(pExceptionObject, v12, v13, v93);
      v15 = v96[1];
      if ( v96[1] == v97 )
      {
        std::vector<Microsoft::Basix::Dct::OperationOnLinkId>::_Emplace_reallocate<Microsoft::Basix::Dct::OperationOnLinkId const &>(
          v96,
          v96[1],
          pExceptionObject);
      }
      else
      {
        *(_BYTE *)v96[1] = pExceptionObject[0];
        *(_DWORD *)((char *)v15 + 2) = *(_DWORD *)((char *)pExceptionObject + 2);
        *((_QWORD *)v15 + 1) = 0;
        *((_QWORD *)v15 + 2) = 0;
        v16 = *(_QWORD *)&pExceptionObject[1];
        if ( *(_QWORD *)&pExceptionObject[1] )
          _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)&pExceptionObject[1] + 8LL));
        *((_QWORD *)v15 + 1) = *((_QWORD *)&pExceptionObject[0] + 1);
        *((_QWORD *)v15 + 2) = v16;
        *((_WORD *)v15 + 12) = WORD4(pExceptionObject[1]);
        v96[1] = (struct Microsoft::Basix::Dct::OperationOnLinkId *)((char *)v96[1] + 32);
      }
      std::deque<Microsoft::Basix::Dct::OperationOnLinkId>::_Emplace_back_internal<Microsoft::Basix::Dct::OperationOnLinkId const &>(
        (char *)this + 3120,
        pExceptionObject);
      v17 = *(volatile signed __int32 **)&pExceptionObject[1];
      if ( *(_QWORD *)&pExceptionObject[1]
        && _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&pExceptionObject[1] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
    Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(&v91);
  }
  v56 = v7;
  v60 = v6;
  v59 = v5;
  v61 = v96[1];
  if ( v96[0] == v96[1] )
  {
    v19 = 0;
  }
  else
  {
    v18 = (char *)v96[0] + 2;
    v19 = v63.m128i_i64[0];
    do
    {
      v62 = 0;
      v20 = *(_QWORD *)(v18 + 14);
      if ( v20 )
        _InterlockedIncrement((volatile signed __int32 *)(v20 + 8));
      v21 = *(_QWORD *)(v18 + 6);
      *(_QWORD *)v93 = v21;
      v62.m128i_i64[0] = v21;
      v22 = *(volatile signed __int32 **)(v18 + 14);
      v62.m128i_i64[1] = (__int64)v22;
      if ( (unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                              &v62,
                              *((_QWORD *)this + 228)) )
      {
        LOWORD(v55) = 0;
        v23 = std::_Atomic_reinterpret_as<short,unsigned short>(&v55);
        *(_WORD *)(*(__int64 (__fastcall **)(char *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((char *)this + 3088) = v23;
        v66[0] = 6;
        v67 = 0;
        v68 = 0;
        v69 = 0;
        v70 = 0;
        v71 = 0;
        v91 = 0;
        v24 = Microsoft::Basix::Dct::SmilesV3::MarkSwitchToNoLock(this, v65, v66, &v91);
        std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(&v63, v24);
        v25 = (volatile signed __int32 *)*((_QWORD *)&v65[0] + 1);
        if ( *((_QWORD *)&v65[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v65[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
            if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
          }
        }
        LOBYTE(v94) = *(v18 - 2);
        *(_DWORD *)((char *)&v94 + 2) = *(_DWORD *)v18;
        std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=((char *)&v94 + 8, v18 + 6);
        WORD4(v95) = *((_WORD *)v18 + 11);
        v19 = v63.m128i_i64[0];
        v91 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v91);
        if ( v19 )
        {
          if ( (_QWORD)v91 && *(_BYTE *)(v91 + 128) )
          {
            v27 = *(_DWORD *)(v19 + 152);
            v28 = *(_DWORD *)(v21 + 152);
            v57 = 0;
            v58 = 0;
            std::string::_Construct<1,char const *>(
              &v57,
              "SmilesV3:  primary link(%d) hasn't received any packets in the last 4500ms, suspending it now and switch t"
              "o a different link(%d)",
              128,
              v26);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned int>(
              (unsigned int)&v91,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v57,
              v28,
              v27);
            std::string::_Tidy_deallocate(&v57);
            v21 = *(_QWORD *)v93;
          }
        }
        else if ( (_QWORD)v91 && *(_BYTE *)(v91 + 128) )
        {
          v29 = *(_DWORD *)(v21 + 152);
          v57 = 0;
          v58 = 0;
          std::string::_Construct<1,char const *>(
            &v57,
            "SmilesV3:  primary link(%d) hasn't received any packets in the last 4500ms, suspending it now. But no link to switch to",
            119);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int>(
            &v91,
            "BASIX_DCT",
            &v57,
            v29);
          std::string::_Tidy_deallocate(&v57);
        }
        v30 = (volatile signed __int32 *)*((_QWORD *)&v91 + 1);
        if ( *((_QWORD *)&v91 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v91 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
            if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
          }
        }
        std::vector<short>::_Tidy(&v67);
      }
      else
      {
        v91 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v91);
        if ( (_QWORD)v91 && *(_BYTE *)(v91 + 128) )
        {
          v31 = *(_DWORD *)(v21 + 152);
          v57 = 0;
          v58 = 0;
          std::string::_Construct<1,char const *>(
            &v57,
            "SmilesV3:  secondary link(%d) hasn't received any packets in the last 4500ms, suspending it now",
            95);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int>(
            &v91,
            "BASIX_DCT",
            &v57,
            v31);
          std::string::_Tidy_deallocate(&v57);
        }
        v32 = (volatile signed __int32 *)*((_QWORD *)&v91 + 1);
        if ( *((_QWORD *)&v91 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v91 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
            if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
          }
        }
      }
      if ( !v19 )
      {
        LOWORD(v55) = *(_WORD *)(v21 + 152);
        if ( (unsigned __int8)std::_Atomic_storage<unsigned short,2>::compare_exchange_strong(
                                (char *)this + 3088,
                                &v55,
                                0,
                                5) )
        {
          v91 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v91);
          if ( (_QWORD)v91 && *(_BYTE *)(v91 + 128) )
          {
            v57 = 0;
            v58 = 0;
            std::string::_Construct<1,char const *>(
              &v57,
              "SmilesV3: Pending link-to-switch-to just suspended, calling MarkSwitchToNoLock to select a different link-to-switch-to",
              118);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
              &v91,
              "BASIX_DCT",
              &v57);
            std::string::_Tidy_deallocate(&v57);
          }
          v33 = (volatile signed __int32 *)*((_QWORD *)&v91 + 1);
          if ( *((_QWORD *)&v91 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v91 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
              if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
            }
          }
          v91 = 0;
          v34 = Microsoft::Basix::Dct::SmilesV3::MarkSwitchToNoLock(this, pExceptionObject, (char *)this + 3056, &v91);
          std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(&v63, v34);
          v35 = (volatile signed __int32 *)*((_QWORD *)&pExceptionObject[0] + 1);
          if ( *((_QWORD *)&pExceptionObject[0] + 1) )
          {
            if ( _InterlockedExchangeAdd(
                   (volatile signed __int32 *)(*((_QWORD *)&pExceptionObject[0] + 1) + 8LL),
                   0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
              if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
            }
          }
          LOBYTE(v94) = *(v18 - 2);
          *(_DWORD *)((char *)&v94 + 2) = *(_DWORD *)v18;
          std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=((char *)&v94 + 8, v18 + 6);
          WORD4(v95) = *((_WORD *)v18 + 11);
          v19 = v63.m128i_i64[0];
        }
      }
      if ( v22 )
      {
        if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
          if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
        }
      }
      v18 += 32;
    }
    while ( v18 - 2 != (char *)v61 );
    v3 = _mm_load_si128(&v63);
    v8 = (Microsoft::Basix::Dct::SmilesV3 *)((char *)this + 1832);
    v5 = v59;
  }
  Mtx_unlock(v8);
  v36 = v96[0];
  v37 = v96[1];
  while ( v36 != v37 )
  {
    Microsoft::Basix::Dct::SmilesV3::ProcessLinkOperation(this, v36);
    v36 = (const struct Microsoft::Basix::Dct::OperationOnLinkId *)((char *)v36 + 32);
  }
  v38 = (volatile signed __int32 *)_mm_srli_si128(v3, 8).m128i_u64[0];
  v39 = (volatile signed __int32 *)v95;
  if ( v19 )
  {
    LOBYTE(pExceptionObject[0]) = v94;
    *(_DWORD *)((char *)pExceptionObject + 2) = *(_DWORD *)((char *)&v94 + 2);
    *(_OWORD *)((char *)pExceptionObject + 8) = 0;
    LOBYTE(v19) = 0;
    if ( (_QWORD)v95 )
      _InterlockedIncrement((volatile signed __int32 *)(v95 + 8));
    *((_QWORD *)&pExceptionObject[0] + 1) = *((_QWORD *)&v94 + 1);
    *(_QWORD *)&pExceptionObject[1] = v39;
    WORD4(pExceptionObject[1]) = WORD4(v95);
    v62 = 0;
    if ( v38 )
      _InterlockedIncrement(v38 + 2);
    v62 = v3;
    Microsoft::Basix::Dct::SmilesV3::SendMarkSwitch(this, &v62, pExceptionObject);
  }
  if ( !v5 )
  {
    v40 = v60;
    if ( v60 )
    {
      v91 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v91);
      if ( (_QWORD)v91 && *(_BYTE *)(v91 + 128) != (_BYTE)v19 )
      {
        v57 = 0;
        v58 = 0;
        std::string::_Construct<1,char const *>(&v57, "SmilesV3:  all links are suspended due to timeout", 49);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(
          &v91,
          "BASIX_DCT",
          &v57);
        std::string::_Tidy_deallocate(&v57);
      }
      v41 = (volatile signed __int32 *)*((_QWORD *)&v91 + 1);
      if ( *((_QWORD *)&v91 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v91 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
          if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
        }
      }
      *(_OWORD *)v93 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v93);
      if ( *(_QWORD *)v93 && *(_BYTE *)(*(_QWORD *)v93 + 128LL) != (_BYTE)v19 )
      {
        *(_QWORD *)&v91 = v77;
        std::_Integral_to_string<char,unsigned int>(v88, *((unsigned int *)this + 380));
        memset(v75, 0, sizeof(v75));
        std::string::_Construct<1,char const *>(v75, ":", 1);
        memset(v74, 0, sizeof(v74));
        std::string::_Construct<1,char const *>(v74, "\"", 1);
        memset(v76, 0, sizeof(v76));
        std::string::_Construct<1,char const *>(v76, "\"", 1);
        v42 = std::operator+<char>(v66, v76, "linkTopIndex");
        LOBYTE(v43) = v55;
        std::string::string(v87, v43, v42, v74);
        LOBYTE(v44) = v55;
        std::string::string(v86, v44, v87, v75);
        LOBYTE(v45) = v55;
        std::string::string(v77, v45, v86, v88);
        v64 = v78;
        std::_Integral_to_string<char,unsigned int>(v85, v56);
        memset(v73, 0, sizeof(v73));
        std::string::_Construct<1,char const *>(v73, ":", 1);
        memset(v72, 0, sizeof(v72));
        std::string::_Construct<1,char const *>(v72, "\"", 1);
        memset(&v62, 0, 32);
        std::string::_Construct<1,char const *>(&v62, "\"", 1);
        v46 = std::operator+<char>(v90, &v62, "NumNonICELinksSuspendedInThisRound");
        LOBYTE(v47) = v55;
        std::string::string(v84, v47, v46, v72);
        LOBYTE(v48) = v55;
        std::string::string(v83, v48, v84, v73);
        LOBYTE(v49) = v55;
        std::string::string(v78, v49, v83, v85);
        std::_Integral_to_string<char,unsigned int>(v82, v40);
        memset(v65, 0, sizeof(v65));
        std::string::_Construct<1,char const *>(v65, ":", 1);
        memset(pExceptionObject, 0, sizeof(pExceptionObject));
        std::string::_Construct<1,char const *>(pExceptionObject, "\"", 1);
        v57 = 0;
        v58 = 0;
        std::string::_Construct<1,char const *>(&v57, "\"", 1);
        v50 = std::operator+<char>(v89, &v57, "NumLinksSuspendedInThisRound");
        LOBYTE(v51) = v55;
        std::string::string(v81, v51, v50, pExceptionObject);
        LOBYTE(v52) = v55;
        std::string::string(v80, v52, v81, v65);
        LOBYTE(v53) = v55;
        std::string::string(v79, v53, v80, v82);
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string>(
          (int)v93,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "LinkSuspendAll",
          "All Links suspended due to timeout",
          (__int64)v79,
          (__int64)v78,
          (__int64)v77);
        std::string::_Tidy_deallocate(v80);
        std::string::_Tidy_deallocate(v81);
        std::string::_Tidy_deallocate(v89);
        std::string::_Tidy_deallocate(&v57);
        std::string::_Tidy_deallocate(pExceptionObject);
        std::string::_Tidy_deallocate(v65);
        std::string::_Tidy_deallocate(v82);
        std::string::_Tidy_deallocate(v83);
        std::string::_Tidy_deallocate(v84);
        std::string::_Tidy_deallocate(v90);
        std::string::_Tidy_deallocate(&v62);
        std::string::_Tidy_deallocate(v72);
        std::string::_Tidy_deallocate(v73);
        std::string::_Tidy_deallocate(v85);
        std::string::_Tidy_deallocate(v86);
        std::string::_Tidy_deallocate(v87);
        std::string::_Tidy_deallocate(v66);
        std::string::_Tidy_deallocate(v76);
        std::string::_Tidy_deallocate(v74);
        std::string::_Tidy_deallocate(v75);
        std::string::_Tidy_deallocate(v88);
      }
      v54 = *(volatile signed __int32 **)&v93[2];
      if ( *(_QWORD *)&v93[2] )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v93[2] + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
          if ( !_InterlockedDecrement(v54 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
        }
      }
    }
  }
  if ( v39 )
  {
    if ( !_InterlockedDecrement(v39 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
      if ( !_InterlockedDecrement(v39 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
    }
  }
  if ( v38 )
  {
    if ( !_InterlockedDecrement(v38 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
      if ( !_InterlockedDecrement(v38 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
    }
  }
  std::vector<Microsoft::Basix::Dct::OperationOnLinkId>::_Tidy(v96);
}

```

## disassembly

```asm
0x18025e404  mov     rax, rsp
0x18025e407  mov     [rax+10h], rbx
0x18025e40b  mov     [rax+18h], rsi
0x18025e40f  mov     [rax+20h], rdi
0x18025e413  push    rbp
0x18025e414  push    r12
0x18025e416  push    r13
0x18025e418  push    r14
0x18025e41a  push    r15
0x18025e41c  lea     rbp, [rax-338h]
0x18025e423  mov     eax, 410h
0x18025e428  call    _alloca_probe
0x18025e42d  sub     rsp, rax
0x18025e430  movaps  [rsp+430h+var_38+8], xmm6
0x18025e438  mov     rax, cs:__security_cookie
0x18025e43f  xor     rax, rsp
0x18025e442  mov     [rbp+330h+var_40], rax
0x18025e449  mov     r15, rcx
0x18025e44c  xor     edi, edi
0x18025e44e  xorps   xmm0, xmm0
0x18025e451  xorps   xmm1, xmm1
0x18025e454  movdqu  xmmword ptr [rbp+330h+var_58], xmm1
0x18025e45c  mov     [rbp+330h+var_48], rdi
0x18025e463  xorps   xmm6, xmm6
0x18025e466  movdqa  [rbp+330h+var_380], xmm6
0x18025e46b  movups  [rbp+330h+var_78], xmm0
0x18025e472  movups  [rbp+330h+var_68], xmm0
0x18025e479  movdqu  [rbp+330h+var_3A0], xmm0
0x18025e47e  lea     r9, [rbp+330h+var_3A0]
0x18025e482  xor     r8d, r8d
0x18025e485  mov     dl, 1
0x18025e487  lea     rcx, [rbp+330h+var_78]
0x18025e48e  call    ??0OperationOnLinkId@Dct@Basix@Microsoft@@QEAA@W4Direction@LinkData@123@W4Mode@0123@V?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Dct::OperationOnLinkId::OperationOnLinkId(Microsoft::Basix::Dct::LinkData::Direction,Microsoft::Basix::Dct::OperationOnLinkId::Mode,std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>)
0x18025e493  nop
0x18025e494  lea     rcx, [rbp+330h+var_3A8]
0x18025e498  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18025e49d  mov     rcx, [rax]
0x18025e4a0  mov     rax, 431BDE82D7B634DBh
0x18025e4aa  imul    rcx
0x18025e4ad  mov     rsi, rdx
0x18025e4b0  sar     rsi, 12h
0x18025e4b4  mov     rax, rsi
0x18025e4b7  shr     rax, 3Fh
0x18025e4bb  add     rsi, rax
0x18025e4be  sub     rsi, [r15+0BC0h]
0x18025e4c5  mov     r12d, edi
0x18025e4c8  mov     r14d, edi
0x18025e4cb  mov     r13d, edi
0x18025e4ce  lea     rbx, [r15+728h]
0x18025e4d5  mov     [rbp+330h+var_370], rbx
0x18025e4d9  mov     rcx, rbx; _Mtx_t
0x18025e4dc  call    _Mtx_lock
0x18025e4e1  test    eax, eax
0x18025e4e3  jnz     loc_18025F3F1
0x18025e4e9  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18025e4f0  jz      loc_18025F3FC
0x18025e4f6  xorps   xmm0, xmm0
0x18025e4f9  movups  [rbp+330h+var_B8], xmm0
0x18025e500  lea     rdx, [r15+5F8h]
0x18025e507  lea     rcx, [rbp+330h+var_B8]
0x18025e50e  call    ??0iterator@?$IterationSafeStore@V?$shared_ptr@VTransport@FailoverBridge@Dct@Basix@Microsoft@@@std@@U?$equal_to@V?$shared_ptr@VTransport@FailoverBridge@Dct@Basix@Microsoft@@@std@@@2@@Containers@Basix@Microsoft@@QEAA@PEBV1234@@Z; Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>> const *)
0x18025e513  nop
0x18025e514  xorps   xmm1, xmm1
0x18025e517  movdqu  [rbp+330h+var_3A0], xmm1
0x18025e51c  mov     rcx, qword ptr [rbp+330h+var_B8]
0x18025e523  test    rcx, rcx
0x18025e526  jz      loc_18025E6DF
0x18025e52c  mov     rdi, qword ptr [rbp+330h+var_B8+8]
0x18025e533  mov     rcx, [rdi]; this
0x18025e536  mov     rax, [rcx+150h]
0x18025e53d  add     rax, 1194h
0x18025e543  cmp     rsi, rax
0x18025e546  jbe     loc_18025E6C1
0x18025e54c  xor     eax, eax
0x18025e54e  cmp     [rcx+160h], al
0x18025e554  jz      loc_18025E6C1
0x18025e55a  cmp     [rcx+118h], eax
0x18025e560  jnz     loc_18025E6C1
0x18025e566  lea     eax, [r13+1]
0x18025e56a  cmp     dword ptr [rcx+50h], 9
0x18025e56e  cmovnz  eax, r13d
0x18025e572  mov     r13d, eax
0x18025e575  inc     r14d
0x18025e578  call    ?SetInSuspend@LinkDataV3@Dct@Basix@Microsoft@@QEAAXXZ; Microsoft::Basix::Dct::LinkDataV3::SetInSuspend(void)
0x18025e57d  mov     rdx, [rdi]
0x18025e580  lea     rcx, [r15+808h]
0x18025e587  xor     r8d, r8d
0x18025e58a  mov     edx, [rdx+50h]
0x18025e58d  call    ?UpdateLinkStatus@Summary@SmilesV3@Dct@Basix@Microsoft@@QEAAXW4LinkType@ISmiles@345@_N@Z; Microsoft::Basix::Dct::SmilesV3::Summary::UpdateLinkStatus(Microsoft::Basix::Dct::ISmiles::LinkType,bool)
0x18025e592  xorps   xmm0, xmm0
0x18025e595  movups  [rbp+330h+pExceptionObject], xmm0
0x18025e59c  movups  [rbp+330h+var_98], xmm0
0x18025e5a3  mov     rax, [rdi+8]
0x18025e5a7  test    rax, rax
0x18025e5aa  jz      short loc_18025E5B0
0x18025e5ac  lock inc dword ptr [rax+8]
0x18025e5b0  mov     rax, [rdi]
0x18025e5b3  mov     qword ptr [rbp+330h+var_88], rax
0x18025e5ba  mov     rax, [rdi+8]
0x18025e5be  mov     qword ptr [rbp+330h+var_88+8], rax
0x18025e5c5  lea     r9, [rbp+330h+var_88]
0x18025e5cc  mov     r8b, 4
0x18025e5cf  mov     dl, 1
0x18025e5d1  lea     rcx, [rbp+330h+pExceptionObject]
0x18025e5d8  call    ??0OperationOnLinkId@Dct@Basix@Microsoft@@QEAA@W4Direction@LinkData@123@W4Mode@0123@V?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Dct::OperationOnLinkId::OperationOnLinkId(Microsoft::Basix::Dct::LinkData::Direction,Microsoft::Basix::Dct::OperationOnLinkId::Mode,std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>)
0x18025e5dd  nop
0x18025e5de  mov     rdx, [rbp+330h+var_58+8]
0x18025e5e5  cmp     rdx, [rbp+330h+var_48]
0x18025e5ec  jz      short loc_18025E651
0x18025e5ee  mov     al, byte ptr [rbp+330h+pExceptionObject]
0x18025e5f4  mov     [rdx], al
0x18025e5f6  movzx   eax, word ptr [rbp+330h+pExceptionObject+2]
0x18025e5fd  mov     [rdx+2], ax
0x18025e601  movzx   eax, word ptr [rbp+330h+pExceptionObject+4]
0x18025e608  mov     [rdx+4], ax
0x18025e60c  xor     eax, eax
0x18025e60e  mov     [rdx+8], rax
0x18025e612  mov     [rdx+10h], rax
0x18025e616  mov     rcx, qword ptr [rbp+330h+var_98]
0x18025e61d  test    rcx, rcx
0x18025e620  jz      short loc_18025E626
0x18025e622  lock inc dword ptr [rcx+8]
0x18025e626  mov     rax, qword ptr [rbp+330h+pExceptionObject+8]
0x18025e62d  mov     [rdx+8], rax
0x18025e631  mov     [rdx+10h], rcx
0x18025e635  mov     al, byte ptr [rbp+330h+var_98+8]
0x18025e63b  mov     [rdx+18h], al
0x18025e63e  mov     al, byte ptr [rbp+330h+var_98+9]
0x18025e644  mov     [rdx+19h], al
0x18025e647  add     [rbp+330h+var_58+8], 20h ; ' '
0x18025e64f  jmp     short loc_18025E664
0x18025e651  lea     r8, [rbp+330h+pExceptionObject]
0x18025e658  lea     rcx, [rbp+330h+var_58]
0x18025e65f  call    ??$_Emplace_reallocate@AEBVOperationOnLinkId@Dct@Basix@Microsoft@@@?$vector@VOperationOnLinkId@Dct@Basix@Microsoft@@V?$allocator@VOperationOnLinkId@Dct@Basix@Microsoft@@@std@@@std@@AEAAPEAVOperationOnLinkId@Dct@Basix@Microsoft@@QEAV2345@AEBV2345@@Z; std::vector<Microsoft::Basix::Dct::OperationOnLinkId>::_Emplace_reallocate<Microsoft::Basix::Dct::OperationOnLinkId const &>(Microsoft::Basix::Dct::OperationOnLinkId * const,Microsoft::Basix::Dct::OperationOnLinkId const &)
0x18025e664  lea     rcx, [r15+0C30h]
0x18025e66b  lea     rdx, [rbp+330h+pExceptionObject]
0x18025e672  call    ??$_Emplace_back_internal@AEBVOperationOnLinkId@Dct@Basix@Microsoft@@@?$deque@VOperationOnLinkId@Dct@Basix@Microsoft@@V?$allocator@VOperationOnLinkId@Dct@Basix@Microsoft@@@std@@@std@@AEAAXAEBVOperationOnLinkId@Dct@Basix@Microsoft@@@Z; std::deque<Microsoft::Basix::Dct::OperationOnLinkId>::_Emplace_back_internal<Microsoft::Basix::Dct::OperationOnLinkId const &>(Microsoft::Basix::Dct::OperationOnLinkId const &)
0x18025e677  nop
0x18025e678  mov     rdi, qword ptr [rbp+330h+var_98]
0x18025e67f  test    rdi, rdi
0x18025e682  jz      short loc_18025E6BD
0x18025e684  or      eax, 0FFFFFFFFh
0x18025e687  lock xadd [rdi+8], eax
0x18025e68c  cmp     eax, 1
0x18025e68f  jnz     short loc_18025E6BD
0x18025e691  mov     rax, [rdi]
0x18025e694  mov     rcx, rdi
0x18025e697  mov     rax, [rax]
0x18025e69a  call    cs:__guard_dispatch_icall_fptr
0x18025e6a0  or      eax, 0FFFFFFFFh
0x18025e6a3  lock xadd [rdi+0Ch], eax
0x18025e6a8  cmp     eax, 1
0x18025e6ab  jnz     short loc_18025E6BD
0x18025e6ad  mov     rax, [rdi]
0x18025e6b0  mov     rcx, rdi
0x18025e6b3  mov     rax, [rax+8]
0x18025e6b7  call    cs:__guard_dispatch_icall_fptr
0x18025e6bd  xor     edi, edi
0x18025e6bf  jmp     short loc_18025E6CE
0x18025e6c1  xor     edi, edi
0x18025e6c3  cmp     [rcx+118h], edi
0x18025e6c9  jnz     short loc_18025E6CE
0x18025e6cb  inc     r12d
0x18025e6ce  lea     rcx, [rbp+330h+var_B8]
0x18025e6d5  call    ??Eiterator@?$IterationSafeStore@V?$weak_ptr@VIActivityListener@Instrumentation@Basix@Microsoft@@@std@@U?$owner_equals@V?$weak_ptr@VIActivityListener@Instrumentation@Basix@Microsoft@@@std@@@Algorithm@Basix@Microsoft@@@Containers@Basix@Microsoft@@QEAAAEAV01234@XZ; Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(void)
0x18025e6da  jmp     loc_18025E51C
0x18025e6df  mov     dword ptr [rsp+430h+var_3D8], r13d
0x18025e6e4  mov     [rbp+330h+var_3AC], r14d
0x18025e6e8  mov     [rbp+330h+var_3B0], r12d
0x18025e6ec  test    rcx, rcx
0x18025e6ef  jz      short loc_18025E70A
0x18025e6f1  add     rcx, 50h ; 'P'
0x18025e6f5  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18025e6fa  or      ecx, 0FFFFFFFFh
0x18025e6fd  lock xadd [rax], ecx
0x18025e701  cmp     ecx, 0FFFFFFFFh
0x18025e704  jz      loc_18025F3CA
0x18025e70a  mov     rax, [rbp+330h+var_58+8]
0x18025e711  mov     [rbp+330h+var_3A8], rax
0x18025e715  mov     r14, [rbp+330h+var_58]
0x18025e71c  cmp     r14, rax
0x18025e71f  jz      loc_18025ECA6
0x18025e725  add     r14, 2
0x18025e729  mov     r13, qword ptr [rbp+330h+var_380]
0x18025e72d  xorps   xmm0, xmm0
0x18025e730  movups  [rbp+330h+var_3A0], xmm0
0x18025e734  mov     rax, [r14+0Eh]
0x18025e738  test    rax, rax
0x18025e73b  jz      short loc_18025E741
0x18025e73d  lock inc dword ptr [rax+8]
0x18025e741  mov     rsi, [r14+6]
0x18025e745  mov     qword ptr [rbp+330h+var_88], rsi
0x18025e74c  mov     qword ptr [rbp+330h+var_3A0], rsi
0x18025e750  mov     r12, [r14+0Eh]
0x18025e754  mov     qword ptr [rbp+330h+var_3A0+8], r12
0x18025e758  mov     rdx, [r15+720h]
0x18025e75f  lea     rcx, [rbp+330h+var_3A0]
0x18025e763  call    ??$?8U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@detail@multi_index@boost@@YA_NAEBV?$bidir_node_iterator@U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@012@0@Z; boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &,boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &)
0x18025e768  test    al, al
0x18025e76a  jz      loc_18025E9BD
0x18025e770  mov     word ptr [rsp+430h+var_3E0], di
0x18025e775  lea     rcx, [rsp+430h+var_3E0]
0x18025e77a  call    ??$_Atomic_reinterpret_as@FG@std@@YAFAEBG@Z; std::_Atomic_reinterpret_as<short,ushort>(ushort const &)
0x18025e77f  movzx   edi, ax
0x18025e782  lea     rcx, [r15+0C10h]
0x18025e789  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18025e78e  xchg    di, [rax]
0x18025e791  mov     [rbp+330h+var_348], 6
0x18025e795  xorps   xmm0, xmm0
0x18025e798  movdqu  [rbp+330h+var_340], xmm0
0x18025e79d  xor     ebx, ebx
0x18025e79f  mov     [rbp+330h+var_330], rbx
0x18025e7a3  mov     [rbp+330h+var_328], bx
0x18025e7a7  mov     [rbp+330h+var_326], bl
0x18025e7aa  mov     [rbp+330h+var_320], rbx
0x18025e7ae  movdqu  [rbp+330h+var_B8], xmm0
0x18025e7b6  lea     r9, [rbp+330h+var_B8]
0x18025e7bd  lea     r8, [rbp+330h+var_348]
0x18025e7c1  lea     rdx, [rbp+330h+var_368]
0x18025e7c5  mov     rcx, r15
0x18025e7c8  call    ?MarkSwitchToNoLock@SmilesV3@Dct@Basix@Microsoft@@AEAA?AV?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@AEBUSwitchInfo@1234@V56@@Z; Microsoft::Basix::Dct::SmilesV3::MarkSwitchToNoLock(Microsoft::Basix::Dct::SmilesV3::SwitchInfo const &,std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>)
0x18025e7cd  mov     rdx, rax
0x18025e7d0  lea     rcx, [rbp+330h+var_380]
0x18025e7d4  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x18025e7d9  mov     rdi, qword ptr [rbp+330h+var_368+8]
0x18025e7dd  test    rdi, rdi
0x18025e7e0  jz      short loc_18025E81F
0x18025e7e2  or      r13d, 0FFFFFFFFh
0x18025e7e6  mov     eax, r13d
0x18025e7e9  lock xadd [rdi+8], eax
0x18025e7ee  add     eax, r13d
0x18025e7f1  jnz     short loc_18025E81F
0x18025e7f3  mov     rax, [rdi]
0x18025e7f6  mov     rcx, rdi
0x18025e7f9  mov     rax, [rax]
0x18025e7fc  call    cs:__guard_dispatch_icall_fptr
0x18025e802  mov     eax, r13d
0x18025e805  lock xadd [rdi+0Ch], eax
0x18025e80a  add     eax, r13d
0x18025e80d  jnz     short loc_18025E81F
0x18025e80f  mov     rax, [rdi]
0x18025e812  mov     rcx, rdi
0x18025e815  mov     rax, [rax+8]
0x18025e819  call    cs:__guard_dispatch_icall_fptr
0x18025e81f  mov     al, [r14-2]
0x18025e823  mov     byte ptr [rbp+330h+var_78], al
0x18025e829  movzx   eax, word ptr [r14]
0x18025e82d  mov     word ptr [rbp+330h+var_78+2], ax
0x18025e834  movzx   eax, word ptr [r14+2]
0x18025e839  mov     word ptr [rbp+330h+var_78+4], ax
0x18025e840  lea     rdx, [r14+6]
0x18025e844  lea     rcx, [rbp+330h+var_78+8]
0x18025e84b  call    ??4?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext> const &)
0x18025e850  mov     al, [r14+16h]
0x18025e854  mov     byte ptr [rbp+330h+var_68+8], al
0x18025e85a  mov     al, [r14+17h]
0x18025e85e  mov     byte ptr [rbp+330h+var_68+9], al
0x18025e864  mov     r13, qword ptr [rbp+330h+var_380]
0x18025e868  xorps   xmm0, xmm0
0x18025e86b  lea     rcx, [rbp+330h+var_B8]
0x18025e872  movups  [rbp+330h+var_B8], xmm0
0x18025e879  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18025e87e  test    r13, r13
0x18025e881  jz      short loc_18025E900
0x18025e883  mov     rax, qword ptr [rbp+330h+var_B8]
0x18025e88a  test    rax, rax
0x18025e88d  jz      short loc_18025E8FE
0x18025e88f  cmp     [rax+80h], bl
0x18025e895  jz      short loc_18025E8FE
0x18025e897  mov     edi, [r13+98h]
0x18025e89e  mov     esi, [rsi+98h]
0x18025e8a4  xorps   xmm0, xmm0
0x18025e8a7  movups  [rsp+430h+var_3D8+8], xmm0
0x18025e8ac  xorps   xmm1, xmm1
0x18025e8af  movdqu  xmmword ptr [rsp+430h+var_3C8+8], xmm1
0x18025e8b5  mov     r8d, 80h
0x18025e8bb  lea     rdx, aSmilesv3Primar; "SmilesV3:  primary link(%d) hasn't rece"...
0x18025e8c2  lea     rcx, [rsp+430h+var_3D8+8]
0x18025e8c7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025e8cc  nop
0x18025e8cd  mov     dword ptr [rsp+430h+var_410], edi
0x18025e8d1  mov     r9d, esi
0x18025e8d4  lea     r8, [rsp+430h+var_3D8+8]
0x18025e8d9  lea     rdx, aBasixDct; "BASIX_DCT"
0x18025e8e0  lea     rcx, [rbp+330h+var_B8]
0x18025e8e7  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@II@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@II@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,uint,uint>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,uint,uint)
0x18025e8ec  nop
0x18025e8ed  lea     rcx, [rsp+430h+var_3D8+8]
0x18025e8f2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18025e8f7  mov     rsi, qword ptr [rbp+330h+var_88]
0x18025e8fe  jmp     short loc_18025E96A
0x18025e900  mov     rax, qword ptr [rbp+330h+var_B8]
0x18025e907  test    rax, rax
0x18025e90a  jz      short loc_18025E96A
0x18025e90c  cmp     [rax+80h], bl
0x18025e912  jz      short loc_18025E96A
0x18025e914  mov     edi, [rsi+98h]
0x18025e91a  xorps   xmm0, xmm0
0x18025e91d  movups  [rsp+430h+var_3D8+8], xmm0
0x18025e922  xorps   xmm1, xmm1
  ... truncated ...
```
