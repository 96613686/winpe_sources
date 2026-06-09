# Microsoft::Basix::Dct::SmilesV3::SendMarkSwitch(std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>,Microsoft::Basix::Dct::OperationOnLinkId)

- ea: `0x18027bd98`
- end: `0x18027c5dd`
- name: `?SendMarkSwitch@SmilesV3@Dct@Basix@Microsoft@@AEAAXV?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@VOperationOnLinkId@234@@Z`
- size: `2117`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180259d38`
- `0x18025e404`
- `0x18026da30`
- `0x18027dd10`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017338`
- `0x180018d1c`
- `0x18001902c`
- `0x1800191b4`
- `0x18001ab4c`
- `0x18001bbdc`
- `0x180024700`
- `0x180028100`
- `0x18002a8f4`
- `0x18003c308`
- `0x1800d621c`
- `0x18024d664`
- `0x180264a84`
- `0x18027b390`
- `0x18027bd98`
- `0x1802e9b68`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## string_xrefs

- `0x18027c580`: `SmilesV3::SendMarkSwitch: no linkIdSwitchingTo set`
- `0x18027be97`: `SmilesV3: MarkSwitching to a link with zero linkId!!`
- `0x18027bfa3`: `SmilesV3::SendMarkSwitch on informed new peer-side primary link(%d) with counter(%d), runningClockInMs(%d)`
- `0x18027c244`: `SmilesV3::SendMarkSwitch on new peer-side secondary link(%d) with counter(%d), runningClockInMs(%d)`
- `0x18027c449`: `SmilesV3::MarkSwitching for Peer: no suitable link to switch to, giveup `

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall Microsoft::Basix::Dct::SmilesV3::SendMarkSwitch(__int64 a1, _QWORD *a2, __int64 a3)
{
  const char *v6; // r15
  __int64 v7; // rax
  __int16 v8; // bx
  __int16 v9; // r14
  volatile signed __int32 *v10; // rbx
  char v11; // r12
  int v12; // r9d
  int v13; // ebx
  volatile signed __int32 *v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 result; // rax
  _QWORD *v21; // r15
  char v22; // r12
  int v23; // r9d
  int v24; // ebx
  volatile signed __int32 *v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rax
  volatile signed __int32 *v28; // rbx
  volatile signed __int32 *v29; // rbx
  volatile signed __int32 *v30; // rbx
  volatile signed __int32 *v31; // rbx
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  _OWORD v34[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v35; // [rsp+60h] [rbp-A0h]
  int v36; // [rsp+68h] [rbp-98h] BYREF
  __int128 v37; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v38[2]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v39; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  _BYTE pExceptionObject[128]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v42[2]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v43[24]; // [rsp+150h] [rbp+50h] BYREF
  char v44; // [rsp+168h] [rbp+68h]
  char v45; // [rsp+169h] [rbp+69h]
  __int128 v46; // [rsp+170h] [rbp+70h] BYREF
  __int128 v47; // [rsp+180h] [rbp+80h] BYREF
  __int128 v48; // [rsp+190h] [rbp+90h] BYREF

  v39 = a2;
  v40 = a3;
  if ( *a2 )
  {
    v6 = (const char *)(a1 + 3056);
    if ( !*(_WORD *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(a1 + 3088) )
    {
      std::string::string(v34, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\smilesv3.cpp");
      std::string::string(v38, "SmilesV3::SendMarkSwitch: no linkIdSwitchingTo set");
      Microsoft::Basix::Exception::Exception(pExceptionObject, v38, v34, 2788);
      throw (Microsoft::Basix::Exception *)pExceptionObject;
    }
    v7 = *a2;
    v8 = *(_WORD *)(*a2 + 242LL);
    v35 = v8;
    *(_WORD *)(v7 + 240) = v8;
    v9 = *(_QWORD *)std::chrono::steady_clock::now(&v36) / 1000000LL - *(_WORD *)(a1 + 3008);
    if ( !v8 )
    {
      v42[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v42);
      if ( *(_QWORD *)&v42[0] && *(_BYTE *)(*(_QWORD *)&v42[0] + 128LL) )
      {
        memset(v34, 0, sizeof(v34));
        std::string::_Construct<1,char const *>(v34, "SmilesV3: MarkSwitching to a link with zero linkId!!", 52);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(
          v42,
          "BASIX_DCT",
          v34);
        std::string::_Tidy_deallocate(v34);
      }
      v10 = (volatile signed __int32 *)*((_QWORD *)&v42[0] + 1);
      if ( *((_QWORD *)&v42[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v42[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
          if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        }
      }
    }
    v46 = 0;
    (*(void (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(*a2 + 104LL) + 80LL))(*(_QWORD *)(*a2 + 104LL), &v46);
    v36 = (unsigned __int16)_InterlockedIncrement16((volatile signed __int16 *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(a1 + 2944));
    v11 = boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
            a2,
            *(_QWORD *)(a1 + 1816))
        | 0x96;
    v42[0] = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v42);
    if ( *(_QWORD *)&v42[0] && *(_BYTE *)(*(_QWORD *)&v42[0] + 128LL) )
    {
      v13 = *(_DWORD *)(*a2 + 152LL);
      memset(v34, 0, sizeof(v34));
      std::string::_Construct<1,char const *>(
        v34,
        "SmilesV3::SendMarkSwitch on informed new peer-side primary link(%d) with counter(%d), runningClockInMs(%d)",
        106,
        v12,
        v32);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,unsigned short,unsigned short>(
        (unsigned int)v42,
        (unsigned int)"BASIX_DCT",
        (unsigned int)v34,
        v13,
        v36,
        v9);
      std::string::_Tidy_deallocate(v34);
    }
    v14 = (volatile signed __int32 *)*((_QWORD *)&v42[0] + 1);
    if ( *((_QWORD *)&v42[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v42[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    LOBYTE(v34[0]) = *(_BYTE *)a3;
    *(_DWORD *)((char *)v34 + 2) = *(_DWORD *)(a3 + 2);
    *(_OWORD *)((char *)v34 + 8) = 0;
    v15 = *(_QWORD *)(a3 + 16);
    if ( v15 )
      _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
    *(_OWORD *)((char *)v34 + 8) = *(_OWORD *)(a3 + 8);
    WORD4(v34[1]) = *(_WORD *)(a3 + 24);
    v47 = 0;
    if ( *((_QWORD *)&v46 + 1) )
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL));
    v47 = v46;
    *(_OWORD *)v43 = 0;
    v16 = a2[1];
    if ( v16 )
      _InterlockedIncrement((volatile signed __int32 *)(v16 + 8));
    *(_OWORD *)v43 = *(_OWORD *)a2;
    Microsoft::Basix::Dct::SmilesV3::Send(a1, v43, (__int64)&v47, v11, v36, v9, 0, (__int64)v34);
    *(_OWORD *)v43 = 0;
    v17 = a2[1];
    if ( v17 )
      _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
    *(_OWORD *)v43 = *(_OWORD *)a2;
    v18 = *(_QWORD *)(a1 + 1824);
    v42[0] = 0;
    v19 = *(_QWORD *)(v18 + 8);
    if ( v19 )
      _InterlockedIncrement((volatile signed __int32 *)(v19 + 8));
    v42[0] = *(_OWORD *)v18;
    Microsoft::Basix::Dct::SmilesV3::LogLinkSwitch(a1, (__int64 *)v34, v42, v43, v6, 1);
    std::string::_Tidy_deallocate(v34);
    v47 = 0;
    result = Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
               &v47,
               a1 + 1528);
    v34[0] = 0;
    while ( (_QWORD)v47 )
    {
      v21 = (_QWORD *)*((_QWORD *)&v47 + 1);
      if ( !(unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                               a2,
                               *((_QWORD *)&v47 + 1)) )
      {
        *(_WORD *)(*v21 + 240LL) = v35;
        v48 = 0;
        (*(void (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(*v21 + 104LL) + 80LL))(
          *(_QWORD *)(*v21 + 104LL),
          &v48);
        v22 = boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                v21,
                *(_QWORD *)(a1 + 1816))
            | 0x96;
        *(_OWORD *)v43 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v43);
        if ( *(_QWORD *)v43 && *(_BYTE *)(*(_QWORD *)v43 + 128LL) )
        {
          v24 = *(_DWORD *)(*v21 + 152LL);
          memset(v42, 0, sizeof(v42));
          std::string::_Construct<1,char const *>(
            v42,
            "SmilesV3::SendMarkSwitch on new peer-side secondary link(%d) with counter(%d), runningClockInMs(%d)",
            99,
            v23,
            v33);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,unsigned short,unsigned short>(
            (unsigned int)v43,
            (unsigned int)"BASIX_DCT",
            (unsigned int)v42,
            v24,
            v36,
            v9);
          std::string::_Tidy_deallocate(v42);
        }
        v25 = *(volatile signed __int32 **)&v43[8];
        if ( *(_QWORD *)&v43[8] )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v43[8] + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
            if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
          }
        }
        v43[0] = *(_BYTE *)a3;
        *(_DWORD *)&v43[2] = *(_DWORD *)(a3 + 2);
        *(_OWORD *)&v43[8] = 0;
        v26 = *(_QWORD *)(a3 + 16);
        if ( v26 )
          _InterlockedIncrement((volatile signed __int32 *)(v26 + 8));
        *(_QWORD *)&v43[8] = *(_QWORD *)(a3 + 8);
        *(_QWORD *)&v43[16] = *(_QWORD *)(a3 + 16);
        v44 = *(_BYTE *)(a3 + 24);
        v45 = *(_BYTE *)(a3 + 25);
        v38[0] = 0;
        if ( *((_QWORD *)&v48 + 1) )
          _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v48 + 1) + 8LL));
        v38[0] = v48;
        v37 = 0;
        v27 = v21[1];
        if ( v27 )
          _InterlockedIncrement((volatile signed __int32 *)(v27 + 8));
        v37 = *(_OWORD *)v21;
        Microsoft::Basix::Dct::SmilesV3::Send(a1, &v37, (__int64)v38, v22, v36, v9, 0, (__int64)v43);
        v28 = (volatile signed __int32 *)*((_QWORD *)&v48 + 1);
        if ( *((_QWORD *)&v48 + 1)
          && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v48 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
          if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
        }
      }
      result = Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(&v47);
    }
  }
  else
  {
    v46 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v46);
    result = v46;
    if ( (_QWORD)v46 && *(_BYTE *)(v46 + 128) )
    {
      memset(v34, 0, sizeof(v34));
      std::string::_Construct<1,char const *>(
        v34,
        "SmilesV3::MarkSwitching for Peer: no suitable link to switch to, giveup ",
        72);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
        &v46,
        "BASIX_DCT",
        v34);
      result = std::string::_Tidy_deallocate(v34);
    }
  }
  v29 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
  if ( *((_QWORD *)&v46 + 1) )
  {
    result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL));
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
      result = (unsigned int)_InterlockedDecrement(v29 + 3);
      if ( !(_DWORD)result )
        result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
    }
  }
  v30 = (volatile signed __int32 *)a2[1];
  if ( v30 )
  {
    result = (unsigned int)_InterlockedDecrement(v30 + 2);
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
      result = (unsigned int)_InterlockedDecrement(v30 + 3);
      if ( !(_DWORD)result )
        result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
    }
  }
  v31 = *(volatile signed __int32 **)(a3 + 16);
  if ( v31 )
  {
    result = (unsigned int)_InterlockedDecrement(v31 + 2);
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
      result = (unsigned int)_InterlockedDecrement(v31 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18027bd98  mov     [rsp-8+arg_18], rbx
0x18027bd9d  push    rbp
0x18027bd9e  push    rsi
0x18027bd9f  push    rdi
0x18027bda0  push    r12
0x18027bda2  push    r13
0x18027bda4  push    r14
0x18027bda6  push    r15
0x18027bda8  lea     rbp, [rsp-0B0h]
0x18027bdb0  mov     eax, 1B0h
0x18027bdb5  call    _alloca_probe
0x18027bdba  sub     rsp, rax
0x18027bdbd  mov     rax, cs:__security_cookie
0x18027bdc4  xor     rax, rsp
0x18027bdc7  mov     [rbp+0E0h+var_40], rax
0x18027bdce  mov     rdi, r8
0x18027bdd1  mov     rsi, rdx
0x18027bdd4  mov     r13, rcx
0x18027bdd7  mov     [rbp+0E0h+var_140], rdx
0x18027bddb  mov     [rbp+0E0h+var_138], r8
0x18027bddf  xor     ebx, ebx
0x18027bde1  or      r12d, 0FFFFFFFFh
0x18027bde5  cmp     [rdx], rbx
0x18027bde8  jz      loc_18027C410
0x18027bdee  lea     r15, [rcx+0BF0h]
0x18027bdf5  lea     rcx, [r15+20h]
0x18027bdf9  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18027bdfe  movzx   ecx, word ptr [rax]
0x18027be01  nop
0x18027be02  test    cx, cx
0x18027be05  jz      loc_18027C56E
0x18027be0b  mov     rax, [rsi]
0x18027be0e  movzx   ebx, word ptr [rax+0F2h]
0x18027be15  mov     [rsp+1E0h+var_180], bx
0x18027be1a  mov     [rax+0F0h], bx
0x18027be21  lea     rcx, [rsp+1E0h+var_178]
0x18027be26  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18027be2b  mov     rcx, [rax]
0x18027be2e  mov     rax, 431BDE82D7B634DBh
0x18027be38  imul    rcx
0x18027be3b  mov     r14, rdx
0x18027be3e  sar     r14, 12h
0x18027be42  mov     rax, r14
0x18027be45  shr     rax, 3Fh
0x18027be49  add     r14, rax
0x18027be4c  sub     r14w, [r13+0BC0h]
0x18027be54  test    bx, bx
0x18027be57  jnz     loc_18027BF0C
0x18027be5d  xorps   xmm0, xmm0
0x18027be60  movups  [rbp+0E0h+var_B0], xmm0
0x18027be64  lea     rcx, [rbp+0E0h+var_B0]
0x18027be68  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x18027be6d  nop
0x18027be6e  mov     rax, qword ptr [rbp+0E0h+var_B0]
0x18027be72  xor     ecx, ecx
0x18027be74  test    rax, rax
0x18027be77  jz      short loc_18027BECA
0x18027be79  cmp     [rax+80h], cl
0x18027be7f  jz      short loc_18027BECA
0x18027be81  xorps   xmm0, xmm0
0x18027be84  movups  [rsp+1E0h+var_1A0], xmm0
0x18027be89  xorps   xmm1, xmm1
0x18027be8c  movdqu  [rsp+1E0h+var_190], xmm1
0x18027be92  lea     r8d, [r12+35h]
0x18027be97  lea     rdx, aSmilesv3Marksw; "SmilesV3: MarkSwitching to a link with "...
0x18027be9e  lea     rcx, [rsp+1E0h+var_1A0]
0x18027bea3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027bea8  nop
0x18027bea9  lea     r8, [rsp+1E0h+var_1A0]
0x18027beae  lea     rdx, aBasixDct; "BASIX_DCT"
0x18027beb5  lea     rcx, [rbp+0E0h+var_B0]
0x18027beb9  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &)
0x18027bebe  nop
0x18027bebf  lea     rcx, [rsp+1E0h+var_1A0]
0x18027bec4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027bec9  nop
0x18027beca  mov     rbx, qword ptr [rbp+0E0h+var_B0+8]
0x18027bece  test    rbx, rbx
0x18027bed1  jz      short loc_18027BF0C
0x18027bed3  mov     eax, r12d
0x18027bed6  lock xadd [rbx+8], eax
0x18027bedb  add     eax, r12d
0x18027bede  jnz     short loc_18027BF0C
0x18027bee0  mov     rax, [rbx]
0x18027bee3  mov     rcx, rbx
0x18027bee6  mov     rax, [rax]
0x18027bee9  call    cs:__guard_dispatch_icall_fptr
0x18027beef  mov     eax, r12d
0x18027bef2  lock xadd [rbx+0Ch], eax
0x18027bef7  add     eax, r12d
0x18027befa  jnz     short loc_18027BF0C
0x18027befc  mov     rax, [rbx]
0x18027beff  mov     rcx, rbx
0x18027bf02  mov     rax, [rax+8]
0x18027bf06  call    cs:__guard_dispatch_icall_fptr
0x18027bf0c  xorps   xmm0, xmm0
0x18027bf0f  movups  [rbp+0E0h+var_70], xmm0
0x18027bf13  mov     rax, [rsi]
0x18027bf16  mov     rcx, [rax+68h]
0x18027bf1a  mov     rax, [rcx]
0x18027bf1d  lea     rdx, [rbp+0E0h+var_70]
0x18027bf21  mov     rax, [rax+50h]
0x18027bf25  call    cs:__guard_dispatch_icall_fptr
0x18027bf2b  nop
0x18027bf2c  lea     rcx, [r13+0B80h]
0x18027bf33  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18027bf38  mov     edx, 1
0x18027bf3d  mov     ecx, edx
0x18027bf3f  lock xadd [rax], cx
0x18027bf44  add     cx, dx
0x18027bf47  mov     [rsp+1E0h+var_178], ecx
0x18027bf4b  mov     rdx, [r13+718h]
0x18027bf52  mov     rcx, rsi
0x18027bf55  call    ??$?8U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@detail@multi_index@boost@@YA_NAEBV?$bidir_node_iterator@U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@012@0@Z; boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &,boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &)
0x18027bf5a  mov     r12b, al
0x18027bf5d  or      r12b, 96h
0x18027bf61  xorps   xmm0, xmm0
0x18027bf64  movups  [rbp+0E0h+var_B0], xmm0
0x18027bf68  lea     rcx, [rbp+0E0h+var_B0]
0x18027bf6c  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18027bf71  nop
0x18027bf72  mov     rax, qword ptr [rbp+0E0h+var_B0]
0x18027bf76  xor     ecx, ecx
0x18027bf78  test    rax, rax
0x18027bf7b  jz      short loc_18027BFE8
0x18027bf7d  cmp     [rax+80h], cl
0x18027bf83  jz      short loc_18027BFE8
0x18027bf85  mov     rax, [rsi]
0x18027bf88  mov     ebx, [rax+98h]
0x18027bf8e  xorps   xmm0, xmm0
0x18027bf91  movups  [rsp+1E0h+var_1A0], xmm0
0x18027bf96  xorps   xmm1, xmm1
0x18027bf99  movdqu  [rsp+1E0h+var_190], xmm1
0x18027bf9f  lea     r8d, [rcx+6Ah]
0x18027bfa3  lea     rdx, aSmilesv3Sendma; "SmilesV3::SendMarkSwitch on informed ne"...
0x18027bfaa  lea     rcx, [rsp+1E0h+var_1A0]
0x18027bfaf  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18027bfb4  nop
0x18027bfb5  mov     [rsp+1E0h+var_1B8], r14w
0x18027bfbb  mov     eax, [rsp+1E0h+var_178]
0x18027bfbf  mov     word ptr [rsp+1E0h+var_1C0], ax
0x18027bfc4  mov     r9d, ebx
0x18027bfc7  lea     r8, [rsp+1E0h+var_1A0]
0x18027bfcc  lea     rdx, aBasixDct; "BASIX_DCT"
0x18027bfd3  lea     rcx, [rbp+0E0h+var_B0]
0x18027bfd7  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@IGG@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@IGG@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,uint,ushort,ushort>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,uint,ushort,ushort)
0x18027bfdc  nop
0x18027bfdd  lea     rcx, [rsp+1E0h+var_1A0]
0x18027bfe2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027bfe7  nop
0x18027bfe8  mov     rbx, qword ptr [rbp+0E0h+var_B0+8]
0x18027bfec  test    rbx, rbx
0x18027bfef  jz      short loc_18027C02A
0x18027bff1  or      eax, 0FFFFFFFFh
0x18027bff4  lock xadd [rbx+8], eax
0x18027bff9  cmp     eax, 1
0x18027bffc  jnz     short loc_18027C02A
0x18027bffe  mov     rax, [rbx]
0x18027c001  mov     rcx, rbx
0x18027c004  mov     rax, [rax]
0x18027c007  call    cs:__guard_dispatch_icall_fptr
0x18027c00d  or      eax, 0FFFFFFFFh
0x18027c010  lock xadd [rbx+0Ch], eax
0x18027c015  cmp     eax, 1
0x18027c018  jnz     short loc_18027C02A
0x18027c01a  mov     rax, [rbx]
0x18027c01d  mov     rcx, rbx
0x18027c020  mov     rax, [rax+8]
0x18027c024  call    cs:__guard_dispatch_icall_fptr
0x18027c02a  mov     al, [rdi]
0x18027c02c  mov     byte ptr [rsp+1E0h+var_1A0], al
0x18027c030  movzx   eax, word ptr [rdi+2]
0x18027c034  mov     word ptr [rsp+1E0h+var_1A0+2], ax
0x18027c039  movzx   eax, word ptr [rdi+4]
0x18027c03d  mov     word ptr [rsp+1E0h+var_1A0+4], ax
0x18027c042  xorps   xmm0, xmm0
0x18027c045  movdqu  [rsp+1E0h+var_1A0+8], xmm0
0x18027c04b  mov     rax, [rdi+10h]
0x18027c04f  xor     ebx, ebx
0x18027c051  test    rax, rax
0x18027c054  jz      short loc_18027C05A
0x18027c056  lock inc dword ptr [rax+8]
0x18027c05a  mov     rax, [rdi+8]
0x18027c05e  mov     qword ptr [rsp+1E0h+var_1A0+8], rax
0x18027c063  mov     rax, [rdi+10h]
0x18027c067  mov     qword ptr [rsp+1E0h+var_190], rax
0x18027c06c  mov     al, [rdi+18h]
0x18027c06f  mov     byte ptr [rsp+1E0h+var_190+8], al
0x18027c073  mov     al, [rdi+19h]
0x18027c076  mov     byte ptr [rsp+1E0h+var_190+9], al
0x18027c07a  movdqa  [rbp+0E0h+var_60], xmm0
0x18027c082  mov     rax, qword ptr [rbp+0E0h+var_70+8]
0x18027c086  test    rax, rax
0x18027c089  jz      short loc_18027C08F
0x18027c08b  lock inc dword ptr [rax+8]
0x18027c08f  movaps  xmm0, [rbp+0E0h+var_70]
0x18027c093  movdqa  [rbp+0E0h+var_60], xmm0
0x18027c09b  xorps   xmm0, xmm0
0x18027c09e  movdqu  [rbp+0E0h+var_90], xmm0
0x18027c0a3  mov     rax, [rsi+8]
0x18027c0a7  test    rax, rax
0x18027c0aa  jz      short loc_18027C0B0
0x18027c0ac  lock inc dword ptr [rax+8]
0x18027c0b0  mov     rax, [rsi]
0x18027c0b3  mov     qword ptr [rbp+0E0h+var_90], rax
0x18027c0b7  mov     rax, [rsi+8]
0x18027c0bb  mov     qword ptr [rbp+0E0h+var_90+8], rax
0x18027c0bf  lea     rax, [rsp+1E0h+var_1A0]
0x18027c0c4  mov     [rsp+1E0h+var_1A8], rax
0x18027c0c9  mov     [rsp+1E0h+var_1B0], bx
0x18027c0ce  mov     [rsp+1E0h+var_1B8], r14w
0x18027c0d4  mov     eax, [rsp+1E0h+var_178]
0x18027c0d8  mov     word ptr [rsp+1E0h+var_1C0], ax
0x18027c0dd  mov     r9b, r12b
0x18027c0e0  lea     r8, [rbp+0E0h+var_60]
0x18027c0e7  lea     rdx, [rbp+0E0h+var_90]
0x18027c0eb  mov     rcx, r13
0x18027c0ee  call    ?Send@SmilesV3@Dct@Basix@Microsoft@@AEAAXV?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@V?$shared_ptr@VOutBuffer@IAsyncTransport@Dct@Basix@Microsoft@@@6@EGGGVOperationOnLinkId@234@@Z; Microsoft::Basix::Dct::SmilesV3::Send(std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>,std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::OutBuffer>,uchar,ushort,ushort,ushort,Microsoft::Basix::Dct::OperationOnLinkId)
0x18027c0f3  xorps   xmm0, xmm0
0x18027c0f6  movdqu  [rbp+0E0h+var_90], xmm0
0x18027c0fb  mov     rax, [rsi+8]
0x18027c0ff  test    rax, rax
0x18027c102  jz      short loc_18027C108
0x18027c104  lock inc dword ptr [rax+8]
0x18027c108  mov     rax, [rsi]
0x18027c10b  mov     qword ptr [rbp+0E0h+var_90], rax
0x18027c10f  mov     rax, [rsi+8]
0x18027c113  mov     qword ptr [rbp+0E0h+var_90+8], rax
0x18027c117  mov     rcx, [r13+720h]
0x18027c11e  movdqu  [rbp+0E0h+var_B0], xmm0
0x18027c123  mov     rax, [rcx+8]
0x18027c127  test    rax, rax
0x18027c12a  jz      short loc_18027C130
0x18027c12c  lock inc dword ptr [rax+8]
0x18027c130  mov     rax, [rcx]
0x18027c133  mov     qword ptr [rbp+0E0h+var_B0], rax
0x18027c137  mov     rax, [rcx+8]
0x18027c13b  mov     qword ptr [rbp+0E0h+var_B0+8], rax
0x18027c13f  mov     byte ptr [rsp+1E0h+var_1B8], 1
0x18027c144  mov     [rsp+1E0h+var_1C0], r15
0x18027c149  lea     r9, [rbp+0E0h+var_90]
0x18027c14d  lea     r8, [rbp+0E0h+var_B0]
0x18027c151  lea     rdx, [rsp+1E0h+var_1A0]
0x18027c156  mov     rcx, r13
0x18027c159  call    ?LogLinkSwitch@SmilesV3@Dct@Basix@Microsoft@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@6@0AEAUSwitchInfo@1234@W4Direction@LinkData@234@@Z; Microsoft::Basix::Dct::SmilesV3::LogLinkSwitch(std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>,std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>,Microsoft::Basix::Dct::SmilesV3::SwitchInfo &,Microsoft::Basix::Dct::LinkData::Direction)
0x18027c15e  lea     rcx, [rsp+1E0h+var_1A0]
0x18027c163  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18027c168  xorps   xmm0, xmm0
0x18027c16b  movups  [rbp+0E0h+var_60], xmm0
0x18027c172  lea     rdx, [r13+5F8h]
0x18027c179  lea     rcx, [rbp+0E0h+var_60]
0x18027c180  call    ??0iterator@?$IterationSafeStore@V?$shared_ptr@VTransport@FailoverBridge@Dct@Basix@Microsoft@@@std@@U?$equal_to@V?$shared_ptr@VTransport@FailoverBridge@Dct@Basix@Microsoft@@@std@@@2@@Containers@Basix@Microsoft@@QEAA@PEBV1234@@Z; Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>> const *)
0x18027c185  nop
0x18027c186  xorps   xmm1, xmm1
0x18027c189  movdqu  [rsp+1E0h+var_1A0], xmm1
0x18027c18f  mov     rcx, qword ptr [rbp+0E0h+var_60]
0x18027c196  test    rcx, rcx
0x18027c199  jz      loc_18027C3E6
0x18027c19f  mov     r15, qword ptr [rbp+0E0h+var_60+8]
0x18027c1a6  mov     rdx, r15
0x18027c1a9  mov     rcx, rsi
0x18027c1ac  call    ??$?8U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@detail@multi_index@boost@@YA_NAEBV?$bidir_node_iterator@U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@012@0@Z; boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &,boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &)
0x18027c1b1  test    al, al
0x18027c1b3  jnz     loc_18027C3D5
0x18027c1b9  mov     rax, [r15]
0x18027c1bc  movzx   ecx, [rsp+1E0h+var_180]
0x18027c1c1  mov     [rax+0F0h], cx
0x18027c1c8  xorps   xmm0, xmm0
0x18027c1cb  movups  [rbp+0E0h+var_50], xmm0
0x18027c1d2  mov     rax, [r15]
0x18027c1d5  mov     rcx, [rax+68h]
0x18027c1d9  mov     rax, [rcx]
0x18027c1dc  lea     rdx, [rbp+0E0h+var_50]
0x18027c1e3  mov     rax, [rax+50h]
0x18027c1e7  call    cs:__guard_dispatch_icall_fptr
0x18027c1ed  nop
0x18027c1ee  mov     rdx, [r13+718h]
0x18027c1f5  mov     rcx, r15
0x18027c1f8  call    ??$?8U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@detail@multi_index@boost@@YA_NAEBV?$bidir_node_iterator@U?$ordered_index_node@Unull_augment_policy@detail@multi_index@boost@@U?$index_node_base@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@std@@@2@@234@@detail@multi_index@boost@@@012@0@Z; boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &,boost::multi_index::detail::bidir_node_iterator<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>> const &)
0x18027c1fd  mov     r12b, al
0x18027c200  or      r12b, 96h
0x18027c204  xorps   xmm0, xmm0
0x18027c207  movups  [rbp+0E0h+var_90], xmm0
0x18027c20b  lea     rcx, [rbp+0E0h+var_90]
0x18027c20f  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18027c214  nop
0x18027c215  mov     rax, qword ptr [rbp+0E0h+var_90]
0x18027c219  test    rax, rax
0x18027c21c  jz      short loc_18027C286
0x18027c21e  cmp     [rax+80h], bl
0x18027c224  jz      short loc_18027C286
0x18027c226  mov     rax, [r15]
0x18027c229  mov     ebx, [rax+98h]
0x18027c22f  xorps   xmm0, xmm0
0x18027c232  movups  [rbp+0E0h+var_B0], xmm0
0x18027c236  xorps   xmm1, xmm1
0x18027c239  movdqu  [rbp+0E0h+var_A0], xmm1
0x18027c23e  mov     r8d, 63h ; 'c'
0x18027c244  lea     rdx, aSmilesv3Sendma_0; "SmilesV3::SendMarkSwitch on new peer-si"...
0x18027c24b  lea     rcx, [rbp+0E0h+var_B0]
  ... truncated ...
```
