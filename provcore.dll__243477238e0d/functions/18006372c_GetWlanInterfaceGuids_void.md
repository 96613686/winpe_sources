# GetWlanInterfaceGuids(void)

- ea: `0x18006372c`
- end: `0x180063934`
- name: `?GetWlanInterfaceGuids@@YA?AV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@XZ`
- size: `520`
- prototype: `std::vector<_GUID> *__fastcall(std::vector<_GUID> *result)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005fa00`

## callees

- `0x180002790`
- `0x18000b178`
- `0x180012748`
- `0x180012bc8`
- `0x18001bb3c`
- `0x1800633f0`
- `0x18006372c`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x1800637a7`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x1800637a7`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x18006381e`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x18006381e`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180063837`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
std::vector<_GUID> *__fastcall GetWlanInterfaceGuids(std::vector<_GUID> *result)
{
  signed int v2; // eax
  signed int v3; // edx
  void *v4; // rcx
  WWAN_INTERFACE_OBJECT *v5; // rax
  _WLAN_INTERFACE_INFO_LIST *v6; // rax
  int v7; // edx
  _WLAN_INTERFACE_INFO_LIST *v8; // rcx
  unsigned __int64 dwNumberOfItems; // rdx
  const std::_Value_init_tag *v10; // r8
  unsigned int v11; // r8d
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+28h] [rbp-58h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> v14; // [rsp+40h] [rbp-40h] BYREF
  std::vector<_GUID> *v15; // [rsp+58h] [rbp-28h]
  _WLAN_INTERFACE_INFO_LIST *pInterfaceList; // [rsp+60h] [rbp-20h] BYREF
  void *wlanHandle; // [rsp+68h] [rbp-18h] BYREF
  unsigned int dwVersion; // [rsp+70h] [rbp-10h] BYREF

  v15 = result;
  wlanHandle = 0;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xFu, WPP_d2d7dbc708d03403d4a3fe2bd494f1e4_Traceguids);
  }
  dwVersion = 0;
  v2 = WlanOpenHandle(2u, 0, &dwVersion, &wlanHandle);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  v4 = wlanHandle;
  if ( wlanHandle )
  {
    v5 = (WWAN_INTERFACE_OBJECT *)wlanHandle;
    v14.dismissed_ = 0;
  }
  else
  {
    v5 = 0;
    v14.dismissed_ = 1;
  }
  v14.fun_ = (void (__fastcall *)(void *))WlanCloseHandleWrapper;
  v14.p1_ = v5;
  v6 = 0;
  pInterfaceList = 0;
  if ( v3 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x10u, WPP_d2d7dbc708d03403d4a3fe2bd494f1e4_Traceguids);
      v4 = wlanHandle;
    }
    WlanEnumInterfaces(v4, 0, &pInterfaceList);
    v6 = pInterfaceList;
  }
  j.dismissed_ = v6 == 0;
  j.fun_ = (void (__fastcall *)(void *))WlanFreeMemory;
  j.p1_ = (WWAN_INTERFACE_OBJECT *const)v6;
  *(_OWORD *)&result->_Mypair._Myval2._Myfirst = 0;
  result->_Mypair._Myval2._Myend = 0;
  std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(result);
  if ( v7 >= 0 )
  {
    v8 = pInterfaceList;
    dwNumberOfItems = pInterfaceList->dwNumberOfItems;
    v10 = (const std::_Value_init_tag *)(result->_Mypair._Myval2._Mylast - result->_Mypair._Myval2._Myfirst);
    if ( dwNumberOfItems >= (unsigned __int64)v10 )
    {
      if ( dwNumberOfItems > (unsigned __int64)v10 )
      {
        if ( dwNumberOfItems <= result->_Mypair._Myval2._Myend - result->_Mypair._Myval2._Myfirst )
          result->_Mypair._Myval2._Mylast = std::_Uninitialized_value_construct_n<std::allocator<_GUID>>(
                                              result->_Mypair._Myval2._Mylast,
                                              dwNumberOfItems - (_QWORD)v10,
                                              (std::allocator<_GUID> *)result);
        else
          std::vector<_GUID>::_Resize_reallocate<std::_Value_init_tag>(result, dwNumberOfItems, v10);
        v8 = pInterfaceList;
      }
    }
    else
    {
      result->_Mypair._Myval2._Mylast = &result->_Mypair._Myval2._Myfirst[dwNumberOfItems];
    }
    v11 = 0;
    if ( v8->dwNumberOfItems )
    {
      do
      {
        result->_Mypair._Myval2._Myfirst[v11] = v8->InterfaceInfo[v11].InterfaceGuid;
        ++v11;
        v8 = pInterfaceList;
      }
      while ( v11 < pInterfaceList->dwNumberOfItems );
    }
  }
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&v14);
  return result;
}

```

## disassembly

```asm
0x18006372c  mov     [rsp-8+arg_8], rbx
0x180063731  mov     [rsp-8+arg_10], rsi
0x180063736  push    rbp
0x180063737  mov     rbp, rsp
0x18006373a  sub     rsp, 80h
0x180063741  mov     rax, cs:__security_cookie
0x180063748  xor     rax, rsp
0x18006374b  mov     [rbp+var_8], rax
0x18006374f  mov     rbx, rcx
0x180063752  mov     [rbp+var_28], rcx
0x180063756  mov     [rbp+var_60], 0
0x18006375d  mov     [rbp+wlanHandle], 0
0x180063765  lea     rsi, WPP_GLOBAL_Control; __annotation("TMF:",
0x18006376c  mov     rcx, cs:WPP_GLOBAL_Control
0x180063773  cmp     rcx, rsi
0x180063776  jz      short loc_180063793
0x180063778  test    byte ptr [rcx+1Ch], 10h
0x18006377c  jz      short loc_180063793
0x18006377e  mov     edx, 0Fh; id
0x180063783  lea     r8, WPP_d2d7dbc708d03403d4a3fe2bd494f1e4_Traceguids; TraceGuid
0x18006378a  mov     rcx, [rcx+10h]; Logger
0x18006378e  call    WPP_SF_
0x180063793  mov     [rbp+dwVersion], 0
0x18006379a  lea     r9, [rbp+wlanHandle]; phClientHandle
0x18006379e  lea     r8, [rbp+dwVersion]; pdwNegotiatedVersion
0x1800637a2  xor     edx, edx; pReserved
0x1800637a4  lea     ecx, [rdx+2]; dwClientVersion
0x1800637a7  call    cs:__imp_WlanOpenHandle
0x1800637ad  mov     edx, eax
0x1800637af  test    eax, eax
0x1800637b1  jle     short loc_1800637BC
0x1800637b3  movzx   edx, ax
0x1800637b6  or      edx, 80070000h
0x1800637bc  mov     rcx, [rbp+wlanHandle]
0x1800637c0  test    rcx, rcx
0x1800637c3  jz      short loc_1800637CE
0x1800637c5  mov     rax, rcx
0x1800637c8  mov     [rbp+var_40.dismissed_], 0
0x1800637cc  jmp     short loc_1800637D4
0x1800637ce  xor     eax, eax
0x1800637d0  mov     [rbp+var_40.dismissed_], 1
0x1800637d4  lea     r8, ?WlanCloseHandleWrapper@@YAKPEAX@Z; WlanCloseHandleWrapper(void *)
0x1800637db  mov     [rbp+var_40.fun_], r8
0x1800637df  mov     [rbp+var_40.p1_], rax
0x1800637e3  xor     eax, eax
0x1800637e5  mov     [rbp+pInterfaceList], rax
0x1800637e9  test    edx, edx
0x1800637eb  js      short loc_180063837
0x1800637ed  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800637f4  cmp     rax, rsi
0x1800637f7  jz      short loc_180063818
0x1800637f9  test    byte ptr [rax+1Ch], 10h
0x1800637fd  jz      short loc_180063818
0x1800637ff  mov     edx, 10h; id
0x180063804  lea     r8, WPP_d2d7dbc708d03403d4a3fe2bd494f1e4_Traceguids; TraceGuid
0x18006380b  mov     rcx, [rax+10h]; Logger
0x18006380f  call    WPP_SF_
0x180063814  mov     rcx, [rbp+wlanHandle]; hClientHandle
0x180063818  lea     r8, [rbp+pInterfaceList]; ppInterfaceList
0x18006381c  xor     edx, edx; pReserved
0x18006381e  call    cs:__imp_WlanEnumInterfaces
0x180063824  mov     edx, eax
0x180063826  test    eax, eax
0x180063828  jle     short loc_180063833
0x18006382a  movzx   edx, ax
0x18006382d  or      edx, 80070000h
0x180063833  mov     rax, [rbp+pInterfaceList]
0x180063837  mov     rcx, cs:__imp_WlanFreeMemory
0x18006383e  test    rax, rax
0x180063841  jz      short loc_180063849
0x180063843  mov     [rbp+j.dismissed_], 0
0x180063847  jmp     short loc_18006384D
0x180063849  mov     [rbp+j.dismissed_], 1
0x18006384d  mov     [rbp+j.fun_], rcx
0x180063851  mov     [rbp+j.p1_], rax
0x180063855  xorps   xmm0, xmm0
0x180063858  xor     eax, eax
0x18006385a  movups  xmmword ptr [rbx], xmm0
0x18006385d  mov     [rbx+10h], rax
0x180063861  mov     rcx, rbx; this
0x180063864  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x180063869  mov     [rbp+var_60], 1
0x180063870  test    edx, edx
0x180063872  js      loc_1800638FC
0x180063878  mov     rcx, [rbp+pInterfaceList]
0x18006387c  mov     edx, [rcx]; _Newsize
0x18006387e  mov     r8, [rbx+8]
0x180063882  sub     r8, [rbx]
0x180063885  sar     r8, 4; _Newsize
0x180063889  cmp     rdx, r8
0x18006388c  jnb     short loc_18006389B
0x18006388e  shl     rdx, 4
0x180063892  add     rdx, [rbx]
0x180063895  mov     [rbx+8], rdx
0x180063899  jmp     short loc_1800638CE
0x18006389b  jbe     short loc_1800638CE
0x18006389d  mov     rax, [rbx+10h]
0x1800638a1  sub     rax, [rbx]
0x1800638a4  sar     rax, 4
0x1800638a8  cmp     rdx, rax
0x1800638ab  jbe     short loc_1800638B7
0x1800638ad  mov     rcx, rbx; this
0x1800638b0  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<_GUID>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800638b5  jmp     short loc_1800638CA
0x1800638b7  sub     rdx, r8; _Count
0x1800638ba  mov     r8, rbx; _Al
0x1800638bd  mov     rcx, [rbx+8]; _First
0x1800638c1  call    ??$_Uninitialized_value_construct_n@V?$allocator@U_GUID@@@std@@@std@@YAPEAU_GUID@@PEAU1@_KAEAV?$allocator@U_GUID@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<_GUID>>(_GUID *,unsigned __int64,std::allocator<_GUID> &)
0x1800638c6  mov     [rbx+8], rax
0x1800638ca  mov     rcx, [rbp+pInterfaceList]
0x1800638ce  xor     r8d, r8d
0x1800638d1  cmp     [rcx], r8d
0x1800638d4  jbe     short loc_1800638FC
0x1800638d6  mov     edx, r8d
0x1800638d9  imul    rax, rdx, 214h
0x1800638e0  movups  xmm0, xmmword ptr [rax+rcx+8]
0x1800638e5  add     rdx, rdx
0x1800638e8  mov     rcx, [rbx]
0x1800638eb  movdqu  xmmword ptr [rcx+rdx*8], xmm0
0x1800638f0  inc     r8d
0x1800638f3  mov     rcx, [rbp+pInterfaceList]
0x1800638f7  cmp     r8d, [rcx]
0x1800638fa  jb      short loc_1800638D6
0x1800638fc  lea     rcx, [rbp+j]; j
0x180063900  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x180063905  nop
0x180063906  lea     rcx, [rbp+var_40]; j
0x18006390a  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x18006390f  mov     rax, rbx
0x180063912  mov     rcx, [rbp+var_8]
0x180063916  xor     rcx, rsp; StackCookie
0x180063919  call    __security_check_cookie
0x18006391e  lea     r11, [rsp+80h+var_s0]
0x180063926  mov     rbx, [r11+18h]
0x18006392a  mov     rsi, [r11+20h]
0x18006392e  mov     rsp, r11
0x180063931  pop     rbp
0x180063932  retn
```
