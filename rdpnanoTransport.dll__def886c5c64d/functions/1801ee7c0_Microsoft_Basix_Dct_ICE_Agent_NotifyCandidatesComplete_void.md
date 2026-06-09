# Microsoft::Basix::Dct::ICE::Agent::NotifyCandidatesComplete(void)

- ea: `0x1801ee7c0`
- end: `0x1801eefec`
- name: `?NotifyCandidatesComplete@Agent@ICE@Dct@Basix@Microsoft@@AEAA_NXZ`
- size: `2092`
- prototype: `bool __fastcall(Microsoft::Basix::Dct::ICE::Agent *__hidden this)`
- caller_count: `0`
- callee_count: `30`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x18000e1c8`
- `0x18000e744`
- `0x180015bb8`
- `0x18001902c`
- `0x18001ab4c`
- `0x18002b3c8`
- `0x1800beedc`
- `0x1800bf3ac`
- `0x1800d4284`
- `0x180106a2c`
- `0x18013516c`
- `0x1801d8d58`
- `0x1801d9f6c`
- `0x1801da8c0`
- `0x1801dab7c`
- `0x1801e43e8`
- `0x1801ee7c0`
- `0x1802ebbac`
- `0x180311d64`
- `0x180311dbc`
- `0x180311e54`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x18032f140`
- `0x180375c40`

## string_xrefs

- `0x1801ee839`: `NotifyCandidatesComplete() called`
- `0x1801ee9f1`: `NotifyCandidatesComplete: add server reflexive %s`
- `0x1801eeb94`: `NotifyCandidatesComplete: add turn %s`
- `0x1801eec9f`: `NotifyCandidatesComplete: add non server reflexive %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
char __fastcall Microsoft::Basix::Dct::ICE::Agent::NotifyCandidatesComplete(Microsoft::Basix::Dct::ICE::Agent *this)
{
  char v2; // r12
  volatile signed __int32 *v3; // rbx
  _QWORD *v4; // r15
  _QWORD *v5; // rax
  _QWORD *v6; // rsi
  _QWORD *v7; // r13
  _QWORD *v8; // rax
  __int64 v9; // rdi
  volatile signed __int32 *v10; // rdi
  _QWORD *v11; // rdx
  __int64 v12; // rax
  _QWORD *v13; // r13
  _QWORD *i; // rsi
  int v15; // eax
  _QWORD *v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rdi
  volatile signed __int32 *v19; // rdi
  _QWORD *v20; // rax
  __int64 v21; // rdi
  volatile signed __int32 *v22; // rdi
  _QWORD *v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rsi
  __int64 v26; // rdi
  volatile signed __int32 *v27; // rdx
  signed __int32 v28; // eax
  signed __int32 v29; // ett
  unsigned __int128 v30; // kr10_16
  __int64 v31; // rax
  void *v32; // rdx
  __int64 (__fastcall *v33)(_QWORD, __int128 *, char *, __int64, __int128 *); // rbx
  __int64 v34; // rax
  char v35; // bl
  unsigned __int64 v36; // rsi
  unsigned __int64 v37; // rdi
  __int64 v39; // [rsp+30h] [rbp-99h] BYREF
  _QWORD v40[3]; // [rsp+38h] [rbp-91h] BYREF
  __int128 v41; // [rsp+50h] [rbp-79h]
  void *v42[2]; // [rsp+60h] [rbp-69h] BYREF
  __int128 v43; // [rsp+70h] [rbp-59h]
  char *v44; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v45[32]; // [rsp+88h] [rbp-41h] BYREF
  unsigned __int128 v46; // [rsp+A8h] [rbp-21h] BYREF
  __int128 v47; // [rsp+B8h] [rbp-11h] BYREF
  __int128 v48; // [rsp+C8h] [rbp-1h] BYREF
  __int64 v49; // [rsp+D8h] [rbp+Fh]
  __int128 v50; // [rsp+E0h] [rbp+17h] BYREF

  v2 = 0;
  LODWORD(v39) = 0;
  v46 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v46);
  if ( (_QWORD)v46 && *(_BYTE *)(v46 + 128) )
  {
    *(_OWORD *)v42 = 0;
    v43 = 0;
    std::string::_Construct<1,char const *>(v42, "NotifyCandidatesComplete() called", 33);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
      &v46,
      "BASIX_DCT",
      v42);
    std::string::_Tidy_deallocate(v42);
  }
  v3 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
  if ( *((_QWORD *)&v46 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  v48 = 0;
  v49 = 0;
  v50 = 0;
  __ExceptionPtrCreate(&v50);
  v44 = (char *)this + 240;
  if ( Mtx_lock((Microsoft::Basix::Dct::ICE::Agent *)((char *)this + 240)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)this + 79) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 79) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v4 = (_QWORD *)((char *)this + 944);
  if ( &v48 != (__int128 *)((char *)this + 944) )
    std::vector<std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>>::_Assign_counted_range<std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext> *>(
      &v48,
      *v4,
      (__int64)(*((_QWORD *)this + 119) - *((_QWORD *)this + 118)) >> 4);
  std::swap<std::exception_ptr,0>((char *)this + 456, &v50);
  v46 = 0;
  v5 = operator new(0x40u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  *(_QWORD *)&v46 = v5;
  v7 = (_QWORD *)*((_QWORD *)&v48 + 1);
  v6 = (_QWORD *)v48;
  if ( (_QWORD)v48 != *((_QWORD *)&v48 + 1) )
  {
    do
    {
      if ( *(_DWORD *)(*v6 + 228LL) == 1 )
      {
        v8 = (_QWORD *)std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::find(
                         &v46,
                         &v39,
                         *v6 + 32LL);
        if ( *v8 == (_QWORD)v46 )
        {
          v47 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v47);
          if ( (_QWORD)v47 && *(_BYTE *)(v47 + 128) )
          {
            v40[0] = v45;
            v9 = Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(v45, *v6, 0, 6);
            *(_OWORD *)&v40[1] = 0;
            v41 = 0;
            std::string::_Construct<1,char const *>(
              &v40[1],
              "NotifyCandidatesComplete: add server reflexive %s",
              (const char *)0x31);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(
              &v47,
              "BASIX_DCT",
              &v40[1],
              v9);
            std::string::_Tidy_deallocate(&v40[1]);
          }
          v10 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
          if ( *((_QWORD *)&v47 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
              if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
            }
          }
          v11 = (_QWORD *)*((_QWORD *)this + 122);
          if ( v11 == *((_QWORD **)this + 123) )
          {
            std::vector<std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger> const &>(
              (char *)this + 968,
              v11,
              v6);
          }
          else
          {
            *v11 = 0;
            v11[1] = 0;
            v12 = v6[1];
            if ( v12 )
              _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
            *v11 = *v6;
            v11[1] = v6[1];
            *((_QWORD *)this + 122) += 16LL;
          }
          std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Emplace<std::string const &>(
            &v46,
            v42,
            *v6 + 32LL);
        }
      }
      v6 += 2;
    }
    while ( v6 != v7 );
    v13 = (_QWORD *)*((_QWORD *)&v48 + 1);
    for ( i = (_QWORD *)v48; i != v13; i += 2 )
    {
      v15 = *(_DWORD *)(*i + 228LL);
      if ( v15 == 3 )
      {
        v16 = (_QWORD *)*((_QWORD *)this + 122);
        if ( v16 == *((_QWORD **)this + 123) )
        {
          std::vector<std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger> const &>(
            (char *)this + 968,
            v16,
            i);
        }
        else
        {
          *v16 = 0;
          v16[1] = 0;
          v17 = i[1];
          if ( v17 )
            _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
          *v16 = *i;
          v16[1] = i[1];
          *((_QWORD *)this + 122) += 16LL;
        }
        v47 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v47);
        if ( (_QWORD)v47 && *(_BYTE *)(v47 + 128) )
        {
          v40[0] = v45;
          v18 = Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(v45, *i, 0, 6);
          *(_OWORD *)&v40[1] = 0;
          v41 = 0;
          std::string::_Construct<1,char const *>(&v40[1], "NotifyCandidatesComplete: add turn %s", (const char *)0x25);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(
            &v47,
            "BASIX_DCT",
            &v40[1],
            v18);
          std::string::_Tidy_deallocate(&v40[1]);
        }
        v19 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
        if ( *((_QWORD *)&v47 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
            if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
          }
        }
      }
      else if ( v15 != 1 )
      {
        v20 = (_QWORD *)std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::find(
                          &v46,
                          &v39,
                          *i + 32LL);
        if ( *v20 == (_QWORD)v46 )
        {
          v47 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v47);
          if ( (_QWORD)v47 && *(_BYTE *)(v47 + 128) )
          {
            v40[0] = v45;
            v21 = Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(v45, *i, 0, 6);
            *(_OWORD *)&v40[1] = 0;
            v41 = 0;
            std::string::_Construct<1,char const *>(
              &v40[1],
              "NotifyCandidatesComplete: add non server reflexive %s",
              (const char *)0x35);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(
              &v47,
              "BASIX_DCT",
              &v40[1],
              v21);
            std::string::_Tidy_deallocate(&v40[1]);
          }
          v22 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
          if ( *((_QWORD *)&v47 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v47 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
              if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
            }
          }
          v23 = (_QWORD *)*((_QWORD *)this + 122);
          if ( v23 == *((_QWORD **)this + 123) )
          {
            std::vector<std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger> const &>(
              (char *)this + 968,
              v23,
              i);
          }
          else
          {
            *v23 = 0;
            v23[1] = 0;
            v24 = i[1];
            if ( v24 )
              _InterlockedIncrement((volatile signed __int32 *)(v24 + 8));
            *v23 = *i;
            v23[1] = i[1];
            *((_QWORD *)this + 122) += 16LL;
          }
          std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Emplace<std::string const &>(
            &v46,
            v42,
            *i + 32LL);
        }
      }
    }
  }
  v25 = *((_QWORD *)this + 119);
  v26 = *v4;
  if ( *v4 != v25 )
  {
    do
    {
      std::shared_ptr<Microsoft::Basix::Instrumentation::DelayedTraceManager::SessionDelayTraceCircularBuffer>::`scalar deleting destructor'(
        v26,
        0);
      v26 += 16;
    }
    while ( v26 != v25 );
    *((_QWORD *)this + 119) = *((_QWORD *)this + 118);
  }
  *(_QWORD *)&v47 = Microsoft::Basix::Dct::ICE::Agent::KeepCandidatesAlive;
  *((_QWORD *)&v47 + 1) = 4294967288LL;
  Microsoft::Basix::Dct::ICE::Agent::ScheduleTaskNoLock<bool (Microsoft::Basix::Dct::ICE::Agent::*)(void)>(
    this,
    &v47,
    5000000000LL);
  std::_Tree_val<std::_Tree_simple_types<std::string>>::_Erase_head<std::allocator<std::_Tree_node<std::string,void *>>>(
    &v46,
    &v46);
  Mtx_unlock((Microsoft::Basix::Dct::ICE::Agent *)((char *)this + 240));
  v46 = 0;
  v27 = (volatile signed __int32 *)*((_QWORD *)this + 113);
  if ( v27 )
  {
    v28 = *((_DWORD *)v27 + 2);
    while ( v28 )
    {
      v29 = v28;
      v28 = _InterlockedCompareExchange(v27 + 2, v28 + 1, v28);
      if ( v29 == v28 )
      {
        v36 = *((_QWORD *)this + 112);
        *(_QWORD *)&v46 = v36;
        v37 = *((_QWORD *)this + 113);
        *((_QWORD *)&v46 + 1) = v37;
        v30 = __PAIR128__(v37, v36);
        goto LABEL_67;
      }
    }
  }
  v30 = v46;
LABEL_67:
  if ( (_QWORD)v30 )
  {
    if ( *((_BYTE *)this + 5504) )
    {
      v39 = *((_QWORD *)&v48 + 1);
      v44 = (char *)v48;
      v31 = Microsoft::Basix::ListToString<boost::iterators::indirect_iterator<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::shared_ptr<Microsoft::Basix::Dct::ICE::Candidate>>>>,boost::use_default,boost::use_default,boost::use_default,boost::use_default>>(
              (unsigned int)v45,
              (unsigned int)&v44,
              (unsigned int)&v39,
              0,
              6);
      LODWORD(v42[0]) = 2;
      v32 = (void *)v31;
      if ( *(_QWORD *)(v31 + 24) > 0xFu )
        v32 = *(void **)v31;
      v42[1] = v32;
      *(_QWORD *)&v43 = *(_QWORD *)(v31 + 16);
      BYTE8(v43) = 0;
      v2 = 3;
      Microsoft::Basix::Instrumentation::ICEGatherCandidatesComplete::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
        (char *)this + 5632,
        (char *)this + 5512,
        v42);
    }
    if ( (v2 & 2) != 0 )
    {
      v2 &= ~2u;
      if ( BYTE8(v43) )
        operator delete(v42[1], (const struct std::nothrow_t *)v27);
    }
    if ( (v2 & 1) != 0 )
      std::string::_Tidy_deallocate(v45);
    v33 = *(__int64 (__fastcall **)(_QWORD, __int128 *, char *, __int64, __int128 *))(*(_QWORD *)v30 + 104LL);
    v40[0] = &v47;
    v47 = 0;
    __ExceptionPtrCopy(&v47, &v50);
    v34 = Microsoft::Basix::Containers::FlexIBuffer::ToString((char *)this + 648, v45);
    v35 = v33(v30, &v48, (char *)this + 616, v34, &v47);
    std::string::_Tidy_deallocate(v45);
  }
  else
  {
    v35 = 0;
  }
  if ( *((_QWORD *)&v30 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v30 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (***((void (__fastcall ****)(_QWORD))&v30 + 1))(*((_QWORD *)&v30 + 1));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v30 + 1) + 12LL), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v30 + 1) + 8LL))(*((_QWORD *)&v30 + 1));
    }
  }
  __ExceptionPtrDestroy(&v50);
  std::vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>>::_Tidy(&v48);
  return v35;
}

```

## disassembly

```asm
0x1801ee7c0  mov     rax, rsp
0x1801ee7c3  mov     [rax+10h], rbx
0x1801ee7c7  mov     [rax+18h], rsi
0x1801ee7cb  mov     [rax+20h], rdi
0x1801ee7cf  push    rbp
0x1801ee7d0  push    r12
0x1801ee7d2  push    r13
0x1801ee7d4  push    r14
0x1801ee7d6  push    r15
0x1801ee7d8  lea     rbp, [rax-5Fh]
0x1801ee7dc  mov     eax, 100h
0x1801ee7e1  call    _alloca_probe
0x1801ee7e6  sub     rsp, rax
0x1801ee7e9  mov     rax, cs:__security_cookie
0x1801ee7f0  xor     rax, rsp
0x1801ee7f3  mov     [rbp+57h+var_30], rax
0x1801ee7f7  mov     r14, rcx
0x1801ee7fa  xor     edi, edi
0x1801ee7fc  mov     r12d, edi
0x1801ee7ff  mov     dword ptr [rsp+120h+var_F0], edi
0x1801ee803  xorps   xmm0, xmm0
0x1801ee806  movups  [rbp+57h+var_78], xmm0
0x1801ee80a  lea     rcx, [rbp+57h+var_78]
0x1801ee80e  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1801ee813  nop
0x1801ee814  mov     rax, qword ptr [rbp+57h+var_78]
0x1801ee818  test    rax, rax
0x1801ee81b  jz      short loc_1801EE869
0x1801ee81d  cmp     [rax+80h], dil
0x1801ee824  jz      short loc_1801EE869
0x1801ee826  xorps   xmm0, xmm0
0x1801ee829  movups  xmmword ptr [rbp+57h+var_C0], xmm0
0x1801ee82d  xorps   xmm1, xmm1
0x1801ee830  movdqu  [rbp+57h+var_B0], xmm1
0x1801ee835  lea     r8d, [rdi+21h]
0x1801ee839  lea     rdx, aNotifycandidat_0; "NotifyCandidatesComplete() called"
0x1801ee840  lea     rcx, [rbp+57h+var_C0]
0x1801ee844  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801ee849  nop
0x1801ee84a  lea     r8, [rbp+57h+var_C0]
0x1801ee84e  lea     rdx, aBasixDct; "BASIX_DCT"
0x1801ee855  lea     rcx, [rbp+57h+var_78]
0x1801ee859  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x1801ee85e  nop
0x1801ee85f  lea     rcx, [rbp+57h+var_C0]
0x1801ee863  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801ee868  nop
0x1801ee869  or      esi, 0FFFFFFFFh
0x1801ee86c  mov     rbx, qword ptr [rbp+57h+var_78+8]
0x1801ee870  test    rbx, rbx
0x1801ee873  jz      short loc_1801EE8AA
0x1801ee875  mov     eax, esi
0x1801ee877  lock xadd [rbx+8], eax
0x1801ee87c  add     eax, esi
0x1801ee87e  jnz     short loc_1801EE8AA
0x1801ee880  mov     rax, [rbx]
0x1801ee883  mov     rcx, rbx
0x1801ee886  mov     rax, [rax]
0x1801ee889  call    cs:__guard_dispatch_icall_fptr
0x1801ee88f  mov     eax, esi
0x1801ee891  lock xadd [rbx+0Ch], eax
0x1801ee896  add     eax, esi
0x1801ee898  jnz     short loc_1801EE8AA
0x1801ee89a  mov     rax, [rbx]
0x1801ee89d  mov     rcx, rbx
0x1801ee8a0  mov     rax, [rax+8]
0x1801ee8a4  call    cs:__guard_dispatch_icall_fptr
0x1801ee8aa  xorps   xmm1, xmm1
0x1801ee8ad  movdqu  [rbp+57h+var_58], xmm1
0x1801ee8b2  mov     [rbp+57h+var_48], rdi
0x1801ee8b6  movdqu  [rbp+57h+var_40], xmm1
0x1801ee8bb  lea     rcx, [rbp+57h+var_40]; void *
0x1801ee8bf  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1801ee8c4  nop
0x1801ee8c5  lea     rbx, [r14+0F0h]
0x1801ee8cc  mov     [rbp+57h+var_A0], rbx
0x1801ee8d0  mov     rcx, rbx; _Mtx_t
0x1801ee8d3  call    _Mtx_lock
0x1801ee8d8  test    eax, eax
0x1801ee8da  jnz     loc_1801EEFE1
0x1801ee8e0  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1801ee8e7  jz      loc_1801EEFCF
0x1801ee8ed  lea     r15, [r14+3B0h]
0x1801ee8f4  lea     rax, [rbp+57h+var_58]
0x1801ee8f8  cmp     rax, r15
0x1801ee8fb  jz      short loc_1801EE914
0x1801ee8fd  mov     r8, [r15+8]
0x1801ee901  sub     r8, [r15]
0x1801ee904  sar     r8, 4
0x1801ee908  mov     rdx, [r15]
0x1801ee90b  lea     rcx, [rbp+57h+var_58]
0x1801ee90f  call    ??$_Assign_counted_range@PEAV?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@std@@@?$vector@V?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@std@@@2@@std@@AEAAXPEAV?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@1@_K@Z; std::vector<std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>>::_Assign_counted_range<std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext> *>(std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext> *,unsigned __int64)
0x1801ee914  lea     rcx, [r14+1C8h]
0x1801ee91b  lea     rdx, [rbp+57h+var_40]
0x1801ee91f  call    ??$swap@Vexception_ptr@std@@$0A@@std@@YAXAEAVexception_ptr@0@0@Z; std::swap<std::exception_ptr,0>(std::exception_ptr &,std::exception_ptr &)
0x1801ee924  xorps   xmm1, xmm1
0x1801ee927  movdqu  [rbp+57h+var_78], xmm1
0x1801ee92c  mov     ecx, 40h ; '@'; Size
0x1801ee931  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801ee936  mov     [rax], rax
0x1801ee939  mov     [rax+8], rax
0x1801ee93d  mov     [rax+10h], rax
0x1801ee941  mov     word ptr [rax+18h], 101h
0x1801ee947  mov     qword ptr [rbp+57h+var_78], rax
0x1801ee94b  mov     rsi, qword ptr [rbp+57h+var_58]
0x1801ee94f  mov     r13, qword ptr [rbp+57h+var_58+8]
0x1801ee953  cmp     rsi, r13
0x1801ee956  jz      loc_1801EED82
0x1801ee95c  mov     r8, [rsi]
0x1801ee95f  mov     eax, [r8+0E4h]
0x1801ee966  cmp     eax, 3
0x1801ee969  jz      loc_1801EEAC3
0x1801ee96f  cmp     eax, 1
0x1801ee972  jnz     loc_1801EEAC3
0x1801ee978  add     r8, 20h ; ' '
0x1801ee97c  lea     rdx, [rsp+120h+var_F0]
0x1801ee981  lea     rcx, [rbp+57h+var_78]
0x1801ee985  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::find(std::string const &)
0x1801ee98a  mov     rcx, qword ptr [rbp+57h+var_78]
0x1801ee98e  cmp     [rax], rcx
0x1801ee991  jnz     loc_1801EEAC3
0x1801ee997  xorps   xmm0, xmm0
0x1801ee99a  movups  [rbp+57h+var_68], xmm0
0x1801ee99e  lea     rcx, [rbp+57h+var_68]
0x1801ee9a2  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1801ee9a7  nop
0x1801ee9a8  mov     rax, qword ptr [rbp+57h+var_68]
0x1801ee9ac  test    rax, rax
0x1801ee9af  jz      short loc_1801EEA27
0x1801ee9b1  cmp     [rax+80h], dil
0x1801ee9b8  jz      short loc_1801EEA27
0x1801ee9ba  lea     rax, [rbp+57h+var_98]
0x1801ee9be  mov     qword ptr [rsp+120h+var_E8], rax
0x1801ee9c3  mov     r9d, 6
0x1801ee9c9  xor     r8d, r8d
0x1801ee9cc  mov     rdx, [rsi]
0x1801ee9cf  lea     rcx, [rbp+57h+var_98]
0x1801ee9d3  call    ??$ToString@VCandidate@ICE@Dct@Basix@Microsoft@@@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVCandidate@ICE@Dct@01@HH@Z; Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(Microsoft::Basix::Dct::ICE::Candidate const &,int,int)
0x1801ee9d8  mov     rdi, rax
0x1801ee9db  xorps   xmm0, xmm0
0x1801ee9de  movups  xmmword ptr [rsp+120h+var_E8+8], xmm0
0x1801ee9e3  xorps   xmm1, xmm1
0x1801ee9e6  movdqu  [rbp+57h+var_D0], xmm1
0x1801ee9eb  mov     r8d, 31h ; '1'
0x1801ee9f1  lea     rdx, aNotifycandidat_1; "NotifyCandidatesComplete: add server re"...
0x1801ee9f8  lea     rcx, [rsp+120h+var_E8+8]
0x1801ee9fd  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801eea02  nop
0x1801eea03  mov     r9, rdi
0x1801eea06  lea     r8, [rsp+120h+var_E8+8]
0x1801eea0b  lea     rdx, aBasixDct; "BASIX_DCT"
0x1801eea12  lea     rcx, [rbp+57h+var_68]
0x1801eea16  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@V65@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,std::string)
0x1801eea1b  nop
0x1801eea1c  lea     rcx, [rsp+120h+var_E8+8]
0x1801eea21  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801eea26  nop
0x1801eea27  mov     rdi, qword ptr [rbp+57h+var_68+8]
0x1801eea2b  test    rdi, rdi
0x1801eea2e  jz      short loc_1801EEA69
0x1801eea30  or      eax, 0FFFFFFFFh
0x1801eea33  lock xadd [rdi+8], eax
0x1801eea38  cmp     eax, 1
0x1801eea3b  jnz     short loc_1801EEA69
0x1801eea3d  mov     rax, [rdi]
0x1801eea40  mov     rcx, rdi
0x1801eea43  mov     rax, [rax]
0x1801eea46  call    cs:__guard_dispatch_icall_fptr
0x1801eea4c  or      eax, 0FFFFFFFFh
0x1801eea4f  lock xadd [rdi+0Ch], eax
0x1801eea54  cmp     eax, 1
0x1801eea57  jnz     short loc_1801EEA69
0x1801eea59  mov     rax, [rdi]
0x1801eea5c  mov     rcx, rdi
0x1801eea5f  mov     rax, [rax+8]
0x1801eea63  call    cs:__guard_dispatch_icall_fptr
0x1801eea69  lea     rcx, [r14+3C8h]
0x1801eea70  mov     rdx, [rcx+8]
0x1801eea74  cmp     rdx, [rcx+10h]
0x1801eea78  jz      short loc_1801EEAA5
0x1801eea7a  xor     edi, edi
0x1801eea7c  mov     [rdx], rdi
0x1801eea7f  mov     [rdx+8], rdi
0x1801eea83  mov     rax, [rsi+8]
0x1801eea87  test    rax, rax
0x1801eea8a  jz      short loc_1801EEA90
0x1801eea8c  lock inc dword ptr [rax+8]
0x1801eea90  mov     rax, [rsi]
0x1801eea93  mov     [rdx], rax
0x1801eea96  mov     rax, [rsi+8]
0x1801eea9a  mov     [rdx+8], rax
0x1801eea9e  add     qword ptr [rcx+8], 10h
0x1801eeaa3  jmp     short loc_1801EEAAF
0x1801eeaa5  mov     r8, rsi
0x1801eeaa8  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VWindowsETWEventLogger@Instrumentation@Basix@Microsoft@@@std@@@?$vector@V?$shared_ptr@VWindowsETWEventLogger@Instrumentation@Basix@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VWindowsETWEventLogger@Instrumentation@Basix@Microsoft@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VWindowsETWEventLogger@Instrumentation@Basix@Microsoft@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger> const &>(std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger> * const,std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger> const &)
0x1801eeaad  xor     edi, edi
0x1801eeaaf  mov     r8, [rsi]
0x1801eeab2  add     r8, 20h ; ' '
0x1801eeab6  lea     rdx, [rbp+57h+var_C0]
0x1801eeaba  lea     rcx, [rbp+57h+var_78]
0x1801eeabe  call    ??$_Emplace@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::_Emplace<std::string const &>(std::string const &)
0x1801eeac3  add     rsi, 10h
0x1801eeac7  cmp     rsi, r13
0x1801eeaca  jnz     loc_1801EE95C
0x1801eead0  mov     r13, qword ptr [rbp+57h+var_58+8]
0x1801eead4  mov     rsi, qword ptr [rbp+57h+var_58]
0x1801eead8  cmp     rsi, r13
0x1801eeadb  jz      loc_1801EED82
0x1801eeae1  jmp     short loc_1801EEAE5
0x1801eeae3  xor     edi, edi
0x1801eeae5  mov     r8, [rsi]
0x1801eeae8  mov     eax, [r8+0E4h]
0x1801eeaef  cmp     eax, 3
0x1801eeaf2  jnz     loc_1801EEC1D
0x1801eeaf8  lea     rcx, [r14+3C8h]
0x1801eeaff  mov     rdx, [rcx+8]
0x1801eeb03  cmp     rdx, [rcx+10h]
0x1801eeb07  jz      short loc_1801EEB32
0x1801eeb09  mov     [rdx], rdi
0x1801eeb0c  mov     [rdx+8], rdi
0x1801eeb10  mov     rax, [rsi+8]
0x1801eeb14  test    rax, rax
0x1801eeb17  jz      short loc_1801EEB1D
0x1801eeb19  lock inc dword ptr [rax+8]
0x1801eeb1d  mov     rax, [rsi]
0x1801eeb20  mov     [rdx], rax
0x1801eeb23  mov     rax, [rsi+8]
0x1801eeb27  mov     [rdx+8], rax
0x1801eeb2b  add     qword ptr [rcx+8], 10h
0x1801eeb30  jmp     short loc_1801EEB3A
0x1801eeb32  mov     r8, rsi
0x1801eeb35  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VWindowsETWEventLogger@Instrumentation@Basix@Microsoft@@@std@@@?$vector@V?$shared_ptr@VWindowsETWEventLogger@Instrumentation@Basix@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VWindowsETWEventLogger@Instrumentation@Basix@Microsoft@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@VWindowsETWEventLogger@Instrumentation@Basix@Microsoft@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger> const &>(std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger> * const,std::shared_ptr<Microsoft::Basix::Instrumentation::WindowsETWEventLogger> const &)
0x1801eeb3a  xorps   xmm0, xmm0
0x1801eeb3d  movups  [rbp+57h+var_68], xmm0
0x1801eeb41  lea     rcx, [rbp+57h+var_68]
0x1801eeb45  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1801eeb4a  nop
0x1801eeb4b  mov     rax, qword ptr [rbp+57h+var_68]
0x1801eeb4f  test    rax, rax
0x1801eeb52  jz      short loc_1801EEBCA
0x1801eeb54  cmp     [rax+80h], dil
0x1801eeb5b  jz      short loc_1801EEBCA
0x1801eeb5d  lea     rax, [rbp+57h+var_98]
0x1801eeb61  mov     qword ptr [rsp+120h+var_E8], rax
0x1801eeb66  mov     r9d, 6
0x1801eeb6c  xor     r8d, r8d
0x1801eeb6f  mov     rdx, [rsi]
0x1801eeb72  lea     rcx, [rbp+57h+var_98]
0x1801eeb76  call    ??$ToString@VCandidate@ICE@Dct@Basix@Microsoft@@@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBVCandidate@ICE@Dct@01@HH@Z; Microsoft::Basix::ToString<Microsoft::Basix::Dct::ICE::Candidate>(Microsoft::Basix::Dct::ICE::Candidate const &,int,int)
0x1801eeb7b  mov     rdi, rax
0x1801eeb7e  xorps   xmm0, xmm0
0x1801eeb81  movups  xmmword ptr [rsp+120h+var_E8+8], xmm0
0x1801eeb86  xorps   xmm1, xmm1
0x1801eeb89  movdqu  [rbp+57h+var_D0], xmm1
0x1801eeb8e  mov     r8d, 25h ; '%'
0x1801eeb94  lea     rdx, aNotifycandidat; "NotifyCandidatesComplete: add turn %s"
0x1801eeb9b  lea     rcx, [rsp+120h+var_E8+8]
0x1801eeba0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801eeba5  nop
0x1801eeba6  mov     r9, rdi
0x1801eeba9  lea     r8, [rsp+120h+var_E8+8]
0x1801eebae  lea     rdx, aBasixDct; "BASIX_DCT"
0x1801eebb5  lea     rcx, [rbp+57h+var_68]
0x1801eebb9  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@V65@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,std::string)
0x1801eebbe  nop
0x1801eebbf  lea     rcx, [rsp+120h+var_E8+8]
0x1801eebc4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801eebc9  nop
0x1801eebca  mov     rdi, qword ptr [rbp+57h+var_68+8]
0x1801eebce  test    rdi, rdi
0x1801eebd1  jz      loc_1801EED75
0x1801eebd7  or      eax, 0FFFFFFFFh
0x1801eebda  lock xadd [rdi+8], eax
0x1801eebdf  cmp     eax, 1
0x1801eebe2  jnz     loc_1801EED75
0x1801eebe8  mov     rax, [rdi]
0x1801eebeb  mov     rcx, rdi
0x1801eebee  mov     rax, [rax]
0x1801eebf1  call    cs:__guard_dispatch_icall_fptr
0x1801eebf7  or      eax, 0FFFFFFFFh
0x1801eebfa  lock xadd [rdi+0Ch], eax
0x1801eebff  cmp     eax, 1
0x1801eec02  jnz     loc_1801EED75
0x1801eec08  mov     rax, [rdi]
0x1801eec0b  mov     rcx, rdi
0x1801eec0e  mov     rax, [rax+8]
0x1801eec12  call    cs:__guard_dispatch_icall_fptr
0x1801eec18  jmp     loc_1801EED75
0x1801eec1d  cmp     eax, 1
0x1801eec20  jz      loc_1801EED75
0x1801eec26  add     r8, 20h ; ' '
0x1801eec2a  lea     rdx, [rsp+120h+var_F0]
0x1801eec2f  lea     rcx, [rbp+57h+var_78]
0x1801eec33  call    ?find@?$_Tree@V?$_Tset_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; std::_Tree<std::_Tset_traits<std::string,std::less<std::string>,std::allocator<std::string>,0>>::find(std::string const &)
0x1801eec38  mov     rcx, qword ptr [rbp+57h+var_78]
0x1801eec3c  cmp     [rax], rcx
0x1801eec3f  jnz     loc_1801EED75
0x1801eec45  xorps   xmm0, xmm0
0x1801eec48  movups  [rbp+57h+var_68], xmm0
0x1801eec4c  lea     rcx, [rbp+57h+var_68]
  ... truncated ...
```
