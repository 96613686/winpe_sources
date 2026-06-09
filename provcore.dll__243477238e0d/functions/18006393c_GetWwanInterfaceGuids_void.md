# GetWwanInterfaceGuids(void)

- ea: `0x18006393c`
- end: `0x180063b05`
- name: `?GetWwanInterfaceGuids@@YA?AV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@XZ`
- size: `457`
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
- `0x18005f248`
- `0x18005f2bc`
- `0x18006393c`

## import_xrefs

- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180063a2f`
- `ext-ms-win-wwan-wwapi-l1-1-1!WwanEnumerateInterfaces` at `0x180063a2f`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800639b7`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanOpenHandle` at `0x1800639b7`
- `ext-ms-win-wwan-wwapi-l1-1-0!WwanFreeMemory` at `0x180063a48`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
std::vector<_GUID> *__fastcall GetWwanInterfaceGuids(std::vector<_GUID> *result)
{
  int v2; // eax
  signed int v3; // edx
  void *v4; // r9
  WWAN_INTERFACE_OBJECT *v5; // rax
  WWAN_INTERFACE_OBJECT *v6; // rax
  int v7; // edx
  unsigned int v8; // edi
  WWAN_INTERFACE_INFO_LIST *i; // rdx
  const _GUID *p_InterfaceGuid; // rdx
  _GUID *Mylast; // rcx
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+28h] [rbp-58h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> v14; // [rsp+40h] [rbp-40h] BYREF
  std::vector<_GUID> *v15; // [rsp+58h] [rbp-28h]
  WWAN_INTERFACE_INFO_LIST *pInterfaceList; // [rsp+60h] [rbp-20h] BYREF
  void *wwanHandle; // [rsp+68h] [rbp-18h] BYREF
  unsigned int dwVersion; // [rsp+70h] [rbp-10h] BYREF

  v15 = result;
  wwanHandle = 0;
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x11u, WPP_d2d7dbc708d03403d4a3fe2bd494f1e4_Traceguids);
  }
  dwVersion = 0;
  v2 = WwanOpenHandle(1, 0, &dwVersion, &wwanHandle);
  v3 = v2;
  if ( v2 > 0 )
    v3 = (unsigned __int16)v2 | 0x80070000;
  v4 = wwanHandle;
  if ( wwanHandle )
  {
    v5 = (WWAN_INTERFACE_OBJECT *)wwanHandle;
    v14.dismissed_ = 0;
  }
  else
  {
    v5 = 0;
    v14.dismissed_ = 1;
  }
  v14.fun_ = (void (__fastcall *)(void *))anonymous_namespace_::WwanCloseHandleWrapper;
  v14.p1_ = v5;
  v6 = 0;
  pInterfaceList = 0;
  if ( v3 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0x12u, WPP_d2d7dbc708d03403d4a3fe2bd494f1e4_Traceguids);
      v4 = wwanHandle;
    }
    WwanEnumerateInterfaces(v4, 0, &pInterfaceList);
    v6 = (WWAN_INTERFACE_OBJECT *)pInterfaceList;
  }
  j.dismissed_ = v6 == 0;
  j.fun_ = (void (__fastcall *)(void *))WwanFreeMemory;
  j.p1_ = v6;
  *(_OWORD *)&result->_Mypair._Myval2._Myfirst = 0;
  result->_Mypair._Myval2._Myend = 0;
  std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(result);
  if ( v7 >= 0 )
  {
    v8 = 0;
    for ( i = pInterfaceList; v8 < pInterfaceList->dwNumberOfItems; i = pInterfaceList )
    {
      p_InterfaceGuid = &i->pInterfaceInfo[v8].InterfaceGuid;
      Mylast = result->_Mypair._Myval2._Mylast;
      if ( Mylast == result->_Mypair._Myval2._Myend )
      {
        std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(result, result->_Mypair._Myval2._Mylast, p_InterfaceGuid);
      }
      else
      {
        std::_Construct_in_place<_GUID,_GUID const &>(Mylast, p_InterfaceGuid);
        ++result->_Mypair._Myval2._Mylast;
      }
      ++v8;
    }
  }
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&v14);
  return result;
}

```

## disassembly

```asm
0x18006393c  mov     [rsp-8+arg_8], rbx
0x180063941  mov     [rsp-8+arg_10], rdi
0x180063946  push    rbp
0x180063947  mov     rbp, rsp
0x18006394a  sub     rsp, 80h
0x180063951  mov     rax, cs:__security_cookie
0x180063958  xor     rax, rsp
0x18006395b  mov     [rbp+var_8], rax
0x18006395f  mov     rbx, rcx
0x180063962  mov     [rbp+var_28], rcx
0x180063966  mov     [rbp+var_60], 0
0x18006396d  mov     [rbp+wwanHandle], 0
0x180063975  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x18006397c  mov     rcx, cs:WPP_GLOBAL_Control
0x180063983  cmp     rcx, rdi
0x180063986  jz      short loc_1800639A3
0x180063988  test    byte ptr [rcx+1Ch], 10h
0x18006398c  jz      short loc_1800639A3
0x18006398e  mov     edx, 11h; id
0x180063993  lea     r8, WPP_d2d7dbc708d03403d4a3fe2bd494f1e4_Traceguids; TraceGuid
0x18006399a  mov     rcx, [rcx+10h]; Logger
0x18006399e  call    WPP_SF_
0x1800639a3  mov     [rbp+dwVersion], 0
0x1800639aa  lea     r9, [rbp+wwanHandle]
0x1800639ae  lea     r8, [rbp+dwVersion]
0x1800639b2  xor     edx, edx
0x1800639b4  lea     ecx, [rdx+1]
0x1800639b7  call    cs:__imp_WwanOpenHandle
0x1800639bd  mov     edx, eax
0x1800639bf  test    eax, eax
0x1800639c1  jle     short loc_1800639CC
0x1800639c3  movzx   edx, ax
0x1800639c6  or      edx, 80070000h
0x1800639cc  mov     r9, [rbp+wwanHandle]
0x1800639d0  test    r9, r9
0x1800639d3  jz      short loc_1800639DE
0x1800639d5  mov     rax, r9
0x1800639d8  mov     [rbp+var_40.dismissed_], 0
0x1800639dc  jmp     short loc_1800639E4
0x1800639de  xor     eax, eax
0x1800639e0  mov     [rbp+var_40.dismissed_], 1
0x1800639e4  lea     rcx, _anonymous_namespace___WwanCloseHandleWrapper
0x1800639eb  mov     [rbp+var_40.fun_], rcx
0x1800639ef  mov     [rbp+var_40.p1_], rax
0x1800639f3  xor     eax, eax
0x1800639f5  mov     [rbp+pInterfaceList], rax
0x1800639f9  test    edx, edx
0x1800639fb  js      short loc_180063A48
0x1800639fd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180063a04  cmp     rcx, rdi
0x180063a07  jz      short loc_180063A26
0x180063a09  test    byte ptr [rcx+1Ch], 10h
0x180063a0d  jz      short loc_180063A26
0x180063a0f  lea     edx, [rax+12h]; id
0x180063a12  lea     r8, WPP_d2d7dbc708d03403d4a3fe2bd494f1e4_Traceguids; TraceGuid
0x180063a19  mov     rcx, [rcx+10h]; Logger
0x180063a1d  call    WPP_SF_
0x180063a22  mov     r9, [rbp+wwanHandle]
0x180063a26  lea     r8, [rbp+pInterfaceList]
0x180063a2a  xor     edx, edx
0x180063a2c  mov     rcx, r9
0x180063a2f  call    cs:__imp_WwanEnumerateInterfaces
0x180063a35  mov     edx, eax
0x180063a37  test    eax, eax
0x180063a39  jle     short loc_180063A44
0x180063a3b  movzx   edx, ax
0x180063a3e  or      edx, 80070000h
0x180063a44  mov     rax, [rbp+pInterfaceList]
0x180063a48  mov     rcx, cs:__imp_WwanFreeMemory
0x180063a4f  test    rax, rax
0x180063a52  jz      short loc_180063A5A
0x180063a54  mov     [rbp+j.dismissed_], 0
0x180063a58  jmp     short loc_180063A5E
0x180063a5a  mov     [rbp+j.dismissed_], 1
0x180063a5e  mov     [rbp+j.fun_], rcx
0x180063a62  mov     [rbp+j.p1_], rax
0x180063a66  xorps   xmm0, xmm0
0x180063a69  xor     eax, eax
0x180063a6b  movups  xmmword ptr [rbx], xmm0
0x180063a6e  mov     [rbx+10h], rax
0x180063a72  mov     rcx, rbx; this
0x180063a75  call    ??0?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDocument@Xml@WcmCommon@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>::vector<std::pair<std::wstring,std::shared_ptr<WcmCommon::Xml::Document>>>(void)
0x180063a7a  mov     [rbp+var_60], 1
0x180063a81  test    edx, edx
0x180063a83  js      short loc_180063ACD
0x180063a85  xor     edi, edi
0x180063a87  mov     rdx, [rbp+pInterfaceList]
0x180063a8b  cmp     [rdx], edi
0x180063a8d  jbe     short loc_180063ACD
0x180063a8f  mov     eax, edi
0x180063a91  imul    rcx, rax, 24Ch
0x180063a98  add     rcx, 4
0x180063a9c  add     rdx, rcx; <_Args_0>
0x180063a9f  mov     rcx, [rbx+8]; _Obj
0x180063aa3  cmp     rcx, [rbx+10h]
0x180063aa7  jz      short loc_180063AB5
0x180063aa9  call    ??$_Construct_in_place@U_GUID@@AEBU1@@std@@YAXAEAU_GUID@@AEBU1@@Z; std::_Construct_in_place<_GUID,_GUID const &>(_GUID &,_GUID const &)
0x180063aae  add     qword ptr [rbx+8], 10h
0x180063ab3  jmp     short loc_180063AC3
0x180063ab5  mov     r8, rdx; <_Val_0>
0x180063ab8  mov     rdx, rcx; _Whereptr
0x180063abb  mov     rcx, rbx; this
0x180063abe  call    ??$_Emplace_reallocate@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEBU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(_GUID * const,_GUID const &)
0x180063ac3  inc     edi
0x180063ac5  mov     rdx, [rbp+pInterfaceList]
0x180063ac9  cmp     edi, [rdx]
0x180063acb  jb      short loc_180063A8F
0x180063acd  lea     rcx, [rbp+j]; j
0x180063ad1  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x180063ad6  nop
0x180063ad7  lea     rcx, [rbp+var_40]; j
0x180063adb  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x180063ae0  mov     rax, rbx
0x180063ae3  mov     rcx, [rbp+var_8]
0x180063ae7  xor     rcx, rsp; StackCookie
0x180063aea  call    __security_check_cookie
0x180063aef  lea     r11, [rsp+80h+var_s0]
0x180063af7  mov     rbx, [r11+18h]
0x180063afb  mov     rdi, [r11+20h]
0x180063aff  mov     rsp, r11
0x180063b02  pop     rbp
0x180063b03  retn
```
