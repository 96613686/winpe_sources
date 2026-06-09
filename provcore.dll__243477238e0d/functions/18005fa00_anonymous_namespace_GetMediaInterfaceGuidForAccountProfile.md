# _anonymous_namespace_::GetMediaInterfaceGuidForAccountProfile

- ea: `0x18005fa00`
- end: `0x18005fdcd`
- name: `_anonymous_namespace_::GetMediaInterfaceGuidForAccountProfile`
- size: `973`
- prototype: `std::vector<_GUID> *__fastcall(std::vector<_GUID> *result, Windows::Networking::NetworkOperators::ProfileMediaType MediaType, const std::wstring *AccountId, const std::wstring *ProfileName)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005f564`

## callees

- `0x180002790`
- `0x18000af94`
- `0x18000b0a0`
- `0x18000b178`
- `0x18000b5d8`
- `0x18000fa6c`
- `0x180011844`
- `0x180011cfc`
- `0x180012748`
- `0x180012770`
- `0x18001a0d4`
- `0x180020b20`
- `0x180020cd8`
- `0x18005f248`
- `0x18005f2bc`
- `0x18005f510`
- `0x18005f810`
- `0x18005fa00`
- `0x18005fe50`
- `0x180060860`
- `0x18006372c`
- `0x18006393c`
- `0x180063b0c`
- `0x1800678c8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005fccd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005fccd`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
std::vector<_GUID> *__fastcall anonymous_namespace_::GetMediaInterfaceGuidForAccountProfile(
        std::vector<_GUID> *result,
        Windows::Networking::NetworkOperators::ProfileMediaType MediaType,
        const std::wstring *AccountId,
        const std::wstring *ProfileName)
{
  int Logger; // esi
  const wchar_t *v9; // rax
  __int64 v10; // r10
  const wchar_t *_a2; // r8
  std::vector<_GUID> *WwanInterfaceGuids; // rax
  void *Ptr; // r14
  _GUID *i; // rdi
  const wchar_t *v15; // rax
  _WCM_OPCODE v16; // r9d
  int CarrierSubscriberFromBlob; // eax
  const wchar_t *v18; // rax
  __int64 v19; // r10
  const wchar_t *v20; // r8
  const wchar_t *v21; // rax
  LPCWCH v22; // r8
  _GUID *Mylast; // rcx
  const wchar_t *v24; // rax
  __int64 v25; // r8
  std::shared_ptr<void> wcmHandle; // [rsp+38h] [rbp-C8h] BYREF
  std::vector<_GUID> *v28; // [rsp+48h] [rbp-B8h]
  std::wstring v29; // [rsp+50h] [rbp-B0h] BYREF
  std::vector<unsigned char> provisioningBlob; // [rsp+70h] [rbp-90h] BYREF
  std::vector<_GUID> interfaceGuids; // [rsp+88h] [rbp-78h] BYREF
  std::wstring provisionedCarrierId; // [rsp+A0h] [rbp-60h] BYREF
  std::wstring provisionedSubscriberId; // [rsp+C0h] [rbp-40h] BYREF
  std::wstring carrierId; // [rsp+E0h] [rbp-20h] BYREF

  v28 = result;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x12u, WPP_21d7a58b43bf3cd1c6756eedd6bc15da_Traceguids);
  }
  Logger = 0;
  MBAE::GetCarrierFromNetworkAccountId(&carrierId, AccountId);
  if ( !carrierId._Mypair._Myval2._Mysize )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x13u, WPP_21d7a58b43bf3cd1c6756eedd6bc15da_Traceguids);
    }
    Logger = -2147024883;
  }
  *(_OWORD *)&result->_Mypair._Myval2._Myfirst = 0;
  result->_Mypair._Myval2._Myend = 0;
  std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(result);
  if ( Logger >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&AccountId->_Mypair._Myval2);
      v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&carrierId._Mypair._Myval2);
      WPP_SF_SS(*(_QWORD *)(v10 + 16), 0x14u, WPP_21d7a58b43bf3cd1c6756eedd6bc15da_Traceguids, v9, _a2);
    }
    memset(&interfaceGuids, 0, sizeof(interfaceGuids));
    std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(&interfaceGuids);
    if ( MediaType )
    {
      if ( MediaType != ProfileMediaType_Wwan )
      {
LABEL_18:
        wcmHandle = 0;
        OpenWcmHandle(&wcmHandle);
        Ptr = wcmHandle._Ptr;
        if ( wcmHandle._Ptr )
        {
          for ( i = interfaceGuids._Mypair._Myval2._Myfirst; i != interfaceGuids._Mypair._Myval2._Mylast; ++i )
          {
            memset(&provisioningBlob, 0, sizeof(provisioningBlob));
            std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>((std::vector<_GUID> *)&provisioningBlob);
            v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&ProfileName->_Mypair._Myval2);
            std::wstring::wstring(&v29, v15);
            Logger = GetWcmParameter(Ptr, i, &v29, v16, &provisioningBlob);
            std::wstring::_Tidy_deallocate(&v29);
            if ( Logger < 0 || provisioningBlob._Mypair._Myval2._Myfirst == provisioningBlob._Mypair._Myval2._Mylast )
            {
              if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
              {
                v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&ProfileName->_Mypair._Myval2);
                WPP_SF__guid_Sd(*(_QWORD *)(v25 + 16), 0x15u, (const _GUID *)v25, i, v24, Logger);
              }
            }
            else
            {
              std::wstring::wstring(&provisionedCarrierId);
              std::wstring::wstring(&provisionedSubscriberId);
              CarrierSubscriberFromBlob = anonymous_namespace_::GetCarrierSubscriberFromBlob(
                                            &provisioningBlob,
                                            &provisionedCarrierId,
                                            &provisionedSubscriberId);
              Logger = CarrierSubscriberFromBlob;
              if ( CarrierSubscriberFromBlob >= 0 )
              {
                if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                  && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
                {
                  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&provisionedSubscriberId._Mypair._Myval2);
                  v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&provisionedCarrierId._Mypair._Myval2);
                  WPP_SF_SS(*(_QWORD *)(v19 + 16), 0x17u, WPP_21d7a58b43bf3cd1c6756eedd6bc15da_Traceguids, v18, v20);
                }
                std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&provisionedCarrierId._Mypair._Myval2);
                v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&carrierId._Mypair._Myval2);
                if ( CompareStringOrdinal(v21, -1, v22, -1, 1) == 2 )
                {
                  Mylast = result->_Mypair._Myval2._Mylast;
                  if ( Mylast == result->_Mypair._Myval2._Myend )
                  {
                    std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(result, result->_Mypair._Myval2._Mylast, i);
                  }
                  else
                  {
                    std::_Construct_in_place<_GUID,_GUID const &>(Mylast, i);
                    ++result->_Mypair._Myval2._Mylast;
                  }
                }
              }
              else if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                     && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
              {
                WPP_SF__guid_D(
                  WPP_GLOBAL_Control->Control.Logger,
                  0x16u,
                  WPP_21d7a58b43bf3cd1c6756eedd6bc15da_Traceguids,
                  i,
                  CarrierSubscriberFromBlob);
              }
              std::wstring::_Tidy_deallocate(&provisionedSubscriberId);
              std::wstring::_Tidy_deallocate(&provisionedCarrierId);
            }
            std::vector<unsigned char>::_Tidy((std::vector<char> *)&provisioningBlob);
          }
        }
        if ( wcmHandle._Rep )
          std::_Ref_count_base::_Decref(wcmHandle._Rep);
        std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::_Tidy(&interfaceGuids);
        goto LABEL_42;
      }
      WwanInterfaceGuids = GetWwanInterfaceGuids((std::vector<_GUID> *)&provisioningBlob);
    }
    else
    {
      WwanInterfaceGuids = GetWlanInterfaceGuids((std::vector<_GUID> *)&provisioningBlob);
    }
    std::vector<_GUID>::operator=(&interfaceGuids, WwanInterfaceGuids);
    std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>>::_Grp_t>>::_Tidy((std::vector<_GUID> *)&provisioningBlob);
    goto LABEL_18;
  }
LABEL_42:
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0x18u, WPP_21d7a58b43bf3cd1c6756eedd6bc15da_Traceguids, Logger);
  }
  std::wstring::_Tidy_deallocate(&carrierId);
  return result;
}

```

## disassembly

```asm
0x18005fa00  mov     [rsp-8+arg_8], rbx
0x18005fa05  push    rbp
0x18005fa06  push    rsi
0x18005fa07  push    rdi
0x18005fa08  push    r12
0x18005fa0a  push    r13
0x18005fa0c  push    r14
0x18005fa0e  push    r15
0x18005fa10  lea     rbp, [rsp-10h]
0x18005fa15  sub     rsp, 110h
0x18005fa1c  mov     rax, cs:__security_cookie
0x18005fa23  xor     rax, rsp
0x18005fa26  mov     [rbp+40h+var_40], rax
0x18005fa2a  mov     r15, ProfileName
0x18005fa2d  mov     r14, AccountId
0x18005fa30  mov     edi, MediaType
0x18005fa32  mov     rbx, rcx
0x18005fa35  mov     [rsp+140h+var_F8], rcx
0x18005fa3a  mov     [rsp+140h+var_110], 0
0x18005fa42  lea     r12, WPP_GLOBAL_Control; __annotation("TMF:",
0x18005fa49  lea     r13, WPP_21d7a58b43bf3cd1c6756eedd6bc15da_Traceguids
0x18005fa50  mov     rcx, cs:WPP_GLOBAL_Control
0x18005fa57  cmp     rcx, r12
0x18005fa5a  jz      short loc_18005FA73
0x18005fa5c  test    byte ptr [rcx+1Ch], 10h
0x18005fa60  jz      short loc_18005FA73
0x18005fa62  mov     MediaType, 12h; id
0x18005fa67  mov     AccountId, r13; TraceGuid
0x18005fa6a  mov     rcx, [rcx+10h]; Logger
0x18005fa6e  call    WPP_SF_
0x18005fa73  xor     esi, esi
0x18005fa75  mov     rdx, r14; MbaeNetworkAccountId
0x18005fa78  lea     rcx, [rbp+40h+carrierId]; result
0x18005fa7c  call    ?GetCarrierFromNetworkAccountId@MBAE@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; MBAE::GetCarrierFromNetworkAccountId(std::wstring const &)
0x18005fa81  nop
0x18005fa82  cmp     [rbp+40h+carrierId._Mypair._Myval2._Mysize], rsi
0x18005fa86  jnz     short loc_18005FAAE
0x18005fa88  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18005fa8f  cmp     rcx, r12
0x18005fa92  jz      short loc_18005FAA9
0x18005fa94  test    byte ptr [rcx+1Ch], 2
0x18005fa98  jz      short loc_18005FAA9
0x18005fa9a  lea     MediaType, [rsi+13h]; id
0x18005fa9d  mov     AccountId, r13; TraceGuid
0x18005faa0  mov     rcx, [rcx+10h]; Logger
0x18005faa4  call    WPP_SF_
0x18005faa9  mov     esi, 8007000Dh
0x18005faae  xorps   xmm0, xmm0
0x18005fab1  xor     eax, eax
0x18005fab3  movups  xmmword ptr [rbx], xmm0
0x18005fab6  mov     [rbx+10h], rax
0x18005faba  mov     rcx, rbx; this
0x18005fabd  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x18005fac2  mov     [rsp+140h+var_110], 1
0x18005faca  test    esi, esi
0x18005facc  js      loc_18005FD72
0x18005fad2  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18005fad9  cmp     r10, r12
0x18005fadc  jz      short loc_18005FB12
0x18005fade  test    byte ptr [r10+1Ch], 10h
0x18005fae3  jz      short loc_18005FB12
0x18005fae5  mov     rcx, r14; this
0x18005fae8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005faed  mov     AccountId, rax
0x18005faf0  lea     rcx, [rbp+40h+carrierId]; this
0x18005faf4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005faf9  mov     ProfileName, rax; _a1
0x18005fafc  mov     MediaType, 14h; id
0x18005fb01  mov     [rsp+140h+_a2], AccountId; _a2
0x18005fb06  mov     AccountId, r13; TraceGuid
0x18005fb09  mov     rcx, [r10+10h]; Logger
0x18005fb0d  call    WPP_SF_SS
0x18005fb12  xorps   xmm0, xmm0
0x18005fb15  xor     eax, eax
0x18005fb17  movups  xmmword ptr [rbp+40h+interfaceGuids._Mypair._Myval2._Myfirst], xmm0
0x18005fb1b  mov     [rbp+40h+interfaceGuids._Mypair._Myval2._Myend], rax
0x18005fb1f  lea     rcx, [rbp+40h+interfaceGuids]; this
0x18005fb23  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x18005fb28  nop
0x18005fb29  test    edi, edi
0x18005fb2b  jz      short loc_18005FB3E
0x18005fb2d  cmp     edi, 1
0x18005fb30  jnz     short loc_18005FB5E
0x18005fb32  lea     rcx, [rsp+140h+provisioningBlob]; result
0x18005fb37  call    ?GetWwanInterfaceGuids@@YA?AV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@XZ; GetWwanInterfaceGuids(void)
0x18005fb3c  jmp     short loc_18005FB48
0x18005fb3e  lea     rcx, [rsp+140h+provisioningBlob]; result
0x18005fb43  call    ?GetWlanInterfaceGuids@@YA?AV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@XZ; GetWlanInterfaceGuids(void)
0x18005fb48  mov     rdx, rax; _Right
0x18005fb4b  lea     rcx, [rbp+40h+interfaceGuids]; this
0x18005fb4f  call    ??4?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<_GUID>::operator=(std::vector<_GUID> &&)
0x18005fb54  lea     rcx, [rsp+140h+provisioningBlob]; this
0x18005fb59  call    ?_Tidy@?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@AEAAXXZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::_Tidy(void)
0x18005fb5e  xorps   xmm0, xmm0
0x18005fb61  movups  xmmword ptr [rsp+140h+wcmHandle._Ptr], xmm0
0x18005fb66  lea     rcx, [rsp+140h+wcmHandle]; result
0x18005fb6b  call    ?OpenWcmHandle@@YA?AV?$shared_ptr@X@std@@XZ; OpenWcmHandle(void)
0x18005fb70  nop
0x18005fb71  mov     r14, [rsp+140h+wcmHandle._Ptr]
0x18005fb76  test    r14, r14
0x18005fb79  jz      loc_18005FD59
0x18005fb7f  mov     rdi, [rbp+40h+interfaceGuids._Mypair._Myval2._Myfirst]
0x18005fb83  jmp     loc_18005FD4F
0x18005fb88  xorps   xmm0, xmm0
0x18005fb8b  xor     eax, eax
0x18005fb8d  movups  xmmword ptr [rsp+140h+provisioningBlob._Mypair._Myval2._Myfirst], xmm0
0x18005fb92  mov     [rbp+40h+provisioningBlob._Mypair._Myval2._Myend], rax
0x18005fb96  lea     rcx, [rsp+140h+provisioningBlob]; this
0x18005fb9b  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x18005fba0  nop
0x18005fba1  mov     rcx, r15; this
0x18005fba4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005fba9  mov     rdx, rax; _Ptr
0x18005fbac  lea     rcx, [rsp+140h+var_F0]; this
0x18005fbb1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005fbb6  nop
0x18005fbb7  lea     rax, [rsp+140h+provisioningBlob]
0x18005fbbc  mov     [rsp+140h+_a2], rax; WcmHandle
0x18005fbc1  lea     AccountId, [rsp+140h+var_F0]; ProfileName
0x18005fbc6  mov     rdx, rdi; InterfaceGuid
0x18005fbc9  mov     rcx, r14; WcmHandle
0x18005fbcc  call    ?GetWcmParameter@@YAJPEAXAEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4_WCM_OPCODE@@AEAV?$vector@EV?$allocator@E@std@@@3@@Z; GetWcmParameter(void *,_GUID const &,std::wstring const &,_WCM_OPCODE,std::vector<uchar> &)
0x18005fbd1  mov     esi, eax
0x18005fbd3  lea     rcx, [rsp+140h+var_F0]; this
0x18005fbd8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005fbdd  test    esi, esi
0x18005fbdf  js      loc_18005FD0B
0x18005fbe5  mov     rax, [rsp+140h+provisioningBlob._Mypair._Myval2._Mylast]
0x18005fbea  cmp     [rsp+140h+provisioningBlob._Mypair._Myval2._Myfirst], rax
0x18005fbef  jz      loc_18005FD0B
0x18005fbf5  lea     rcx, [rbp+40h+provisionedCarrierId]; this
0x18005fbf9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005fbfe  nop
0x18005fbff  lea     rcx, [rbp+40h+provisionedSubscriberId]; this
0x18005fc03  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005fc08  nop
0x18005fc09  lea     AccountId, [rbp+40h+provisionedSubscriberId]; SubscriberId
0x18005fc0d  lea     rdx, [rbp+40h+provisionedCarrierId]; CarrierId
0x18005fc11  lea     rcx, [rsp+140h+provisioningBlob]; Blob
0x18005fc16  call    _anonymous_namespace___GetCarrierSubscriberFromBlob
0x18005fc1b  mov     esi, eax
0x18005fc1d  test    eax, eax
0x18005fc1f  jns     short loc_18005FC64
0x18005fc21  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18005fc28  cmp     rcx, r12
0x18005fc2b  jz      short loc_18005FC4C
0x18005fc2d  test    byte ptr [rcx+1Ch], 10h
0x18005fc31  jz      short loc_18005FC4C
0x18005fc33  mov     MediaType, 16h; id
0x18005fc38  mov     dword ptr [rsp+140h+_a2], eax; _a2
0x18005fc3c  mov     ProfileName, rdi; _a1
0x18005fc3f  mov     AccountId, r13; TraceGuid
0x18005fc42  mov     rcx, [rcx+10h]; Logger
0x18005fc46  call    WPP_SF__guid_D
0x18005fc4b  nop
0x18005fc4c  lea     rcx, [rbp+40h+provisionedSubscriberId]; this
0x18005fc50  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005fc55  nop
0x18005fc56  lea     rcx, [rbp+40h+provisionedCarrierId]; this
0x18005fc5a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005fc5f  jmp     loc_18005FD41
0x18005fc64  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18005fc6b  cmp     r10, r12
0x18005fc6e  jz      short loc_18005FCA5
0x18005fc70  test    byte ptr [r10+1Ch], 10h
0x18005fc75  jz      short loc_18005FCA5
0x18005fc77  lea     rcx, [rbp+40h+provisionedSubscriberId]; this
0x18005fc7b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005fc80  mov     AccountId, rax
0x18005fc83  lea     rcx, [rbp+40h+provisionedCarrierId]; this
0x18005fc87  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005fc8c  mov     ProfileName, rax; _a1
0x18005fc8f  mov     MediaType, 17h; id
0x18005fc94  mov     [rsp+140h+_a2], AccountId; _a2
0x18005fc99  mov     AccountId, r13; TraceGuid
0x18005fc9c  mov     rcx, [r10+10h]; Logger
0x18005fca0  call    WPP_SF_SS
0x18005fca5  lea     rcx, [rbp+40h+provisionedCarrierId]; this
0x18005fca9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005fcae  mov     AccountId, rax
0x18005fcb1  lea     rcx, [rbp+40h+carrierId]; this
0x18005fcb5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005fcba  mov     rcx, rax; lpString1
0x18005fcbd  mov     dword ptr [rsp+140h+_a2], 1; bIgnoreCase
0x18005fcc5  or      eax, 0FFFFFFFFh
0x18005fcc8  mov     r9d, eax; cchCount2
0x18005fccb  mov     MediaType, eax; cchCount1
0x18005fccd  call    cs:__imp_CompareStringOrdinal
0x18005fcd3  cmp     eax, 2
0x18005fcd6  jnz     loc_18005FC4C
0x18005fcdc  mov     rcx, [rbx+8]; _Obj
0x18005fce0  cmp     rcx, [rbx+10h]
0x18005fce4  jz      short loc_18005FCF8
0x18005fce6  mov     rdx, rdi; <_Args_0>
0x18005fce9  call    ??$_Construct_in_place@U_GUID@@AEBU1@@std@@YAXAEAU_GUID@@AEBU1@@Z; std::_Construct_in_place<_GUID,_GUID const &>(_GUID &,_GUID const &)
0x18005fcee  add     qword ptr [rbx+8], 10h
0x18005fcf3  jmp     loc_18005FC4C
0x18005fcf8  mov     AccountId, rdi; <_Val_0>
0x18005fcfb  mov     rdx, rcx; _Whereptr
0x18005fcfe  mov     rcx, rbx; this
0x18005fd01  call    ??$_Emplace_reallocate@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEBU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(_GUID * const,_GUID const &)
0x18005fd06  jmp     loc_18005FC4C
0x18005fd0b  mov     AccountId, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18005fd12  cmp     AccountId, r12
0x18005fd15  jz      short loc_18005FD41
0x18005fd17  test    byte ptr [AccountId+1Ch], 8
0x18005fd1c  jz      short loc_18005FD41
0x18005fd1e  mov     rcx, r15; this
0x18005fd21  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005fd26  mov     MediaType, 15h; id
0x18005fd2b  mov     [rsp+140h+Logger], esi; Logger
0x18005fd2f  mov     [rsp+140h+_a2], rax; _a3
0x18005fd34  mov     ProfileName, rdi; _a2
0x18005fd37  mov     rcx, [AccountId+10h]; Logger
0x18005fd3b  call    WPP_SF__guid_Sd
0x18005fd40  nop
0x18005fd41  lea     rcx, [rsp+140h+provisioningBlob]; this
0x18005fd46  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18005fd4b  add     rdi, 10h
0x18005fd4f  cmp     rdi, [rbp+40h+interfaceGuids._Mypair._Myval2._Mylast]
0x18005fd53  jnz     loc_18005FB88
0x18005fd59  mov     rcx, [rsp+140h+wcmHandle._Rep]; this
0x18005fd5e  test    rcx, rcx
0x18005fd61  jz      short loc_18005FD69
0x18005fd63  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005fd68  nop
0x18005fd69  lea     rcx, [rbp+40h+interfaceGuids]; this
0x18005fd6d  call    ?_Tidy@?$vector@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@V?$allocator@U_Grp_t@?$_Tgt_state_t@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@@std@@@3@@std@@AEAAXXZ; std::vector<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t,std::allocator<std::_Tgt_state_t<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>>::_Grp_t>>::_Tidy(void)
0x18005fd72  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18005fd79  cmp     rcx, r12
0x18005fd7c  jz      short loc_18005FD99
0x18005fd7e  test    byte ptr [rcx+1Ch], 10h
0x18005fd82  jz      short loc_18005FD99
0x18005fd84  mov     MediaType, 18h; id
0x18005fd89  mov     r9d, esi; _a1
0x18005fd8c  mov     AccountId, r13; TraceGuid
0x18005fd8f  mov     rcx, [rcx+10h]; Logger
0x18005fd93  call    WPP_SF_d
0x18005fd98  nop
0x18005fd99  lea     rcx, [rbp+40h+carrierId]; this
0x18005fd9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005fda2  mov     rax, rbx
0x18005fda5  mov     rcx, [rbp+40h+var_40]
0x18005fda9  xor     rcx, rsp; StackCookie
0x18005fdac  call    __security_check_cookie
0x18005fdb1  mov     rbx, [rsp+140h+arg_8]
0x18005fdb9  add     rsp, 110h
0x18005fdc0  pop     r15
0x18005fdc2  pop     r14
0x18005fdc4  pop     r13
0x18005fdc6  pop     r12
0x18005fdc8  pop     rdi
0x18005fdc9  pop     rsi
0x18005fdca  pop     rbp
0x18005fdcb  retn
```
