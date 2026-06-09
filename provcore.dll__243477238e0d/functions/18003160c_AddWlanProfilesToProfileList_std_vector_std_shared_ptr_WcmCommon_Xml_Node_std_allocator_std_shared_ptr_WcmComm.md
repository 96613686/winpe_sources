# AddWlanProfilesToProfileList(std::vector<std::shared_ptr<WcmCommon::Xml::Node>,std::allocator<std::shared_ptr<WcmCommon::Xml::Node>>> const &,std::vector<Profile,std::allocator<Profile>> &)

- ea: `0x18003160c`
- end: `0x180031967`
- name: `?AddWlanProfilesToProfileList@@YAJAEBV?$vector@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@2@@std@@AEAV?$vector@UProfile@@V?$allocator@UProfile@@@std@@@2@@Z`
- size: `859`
- prototype: `HRESULT __fastcall(const std::vector<std::shared_ptr<WcmCommon::Xml::Node>> *wlanNodes, std::vector<Profile> *profileList)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032790`

## callees

- `0x180002790`
- `0x18000846c`
- `0x18000af94`
- `0x180011844`
- `0x180011cfc`
- `0x180012618`
- `0x180012748`
- `0x180012770`
- `0x180012bc8`
- `0x18001c07c`
- `0x180031104`
- `0x180031148`
- `0x18003136c`
- `0x18003160c`
- `0x180031c40`
- `0x180031d6c`

## import_xrefs

- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x18003165a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanOpenHandle` at `0x18003165a`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x1800316e2`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanEnumInterfaces` at `0x1800316e2`
- `ext-ms-win-networking-wlanapi-l1-1-0!WlanFreeMemory` at `0x180031739`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall AddWlanProfilesToProfileList(
        const std::vector<std::shared_ptr<WcmCommon::Xml::Node>> *wlanNodes,
        std::vector<Profile> *profileList)
{
  unsigned int v4; // r14d
  DWORD v5; // eax
  const _EVENT_DESCRIPTOR *v6; // rdx
  int v7; // ebx
  _MCGEN_TRACE_CONTEXT *v8; // rcx
  DWORD v9; // eax
  std::shared_ptr<WcmCommon::Xml::Node> *Myfirst; // rsi
  std::shared_ptr<WcmCommon::Xml::Node> *Mylast; // r12
  unsigned __int64 *v12; // rdx
  int v13; // r8d
  unsigned int _a3; // r13d
  _WLAN_INTERFACE_INFO_LIST *v15; // rdx
  const wchar_t *v16; // rax
  __int64 v17; // r8
  const _GUID *Logger; // r10
  unsigned __int64 v19; // rbx
  std::wstring *v20; // rax
  Profile *v21; // rax
  Profile *v22; // rcx
  const _GUID *p_InterfaceGuid; // [rsp+30h] [rbp-D0h]
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> j; // [rsp+38h] [rbp-C8h] BYREF
  ScopeGuardImpl1<void (__cdecl*)(void *),WWAN_INTERFACE_OBJECT *> v26; // [rsp+50h] [rbp-B0h] BYREF
  std::wstring Path; // [rsp+68h] [rbp-98h] BYREF
  std::wstring v28; // [rsp+90h] [rbp-70h] BYREF
  Profile v29; // [rsp+B0h] [rbp-50h] BYREF
  _WLAN_INTERFACE_INFO_LIST *pInterfaceList; // [rsp+100h] [rbp+0h] BYREF
  void *hWlan; // [rsp+108h] [rbp+8h] BYREF
  unsigned int dwVersion; // [rsp+110h] [rbp+10h] BYREF
  std::wstring priorityStr; // [rsp+118h] [rbp+18h] BYREF
  std::wstring profileName; // [rsp+138h] [rbp+38h] BYREF

  v4 = 0;
  dwVersion = 0;
  hWlan = 0;
  pInterfaceList = 0;
  v5 = WlanOpenHandle(2u, 0, &dwVersion, &hWlan);
  v7 = v5;
  if ( v5 )
  {
    v8 = (_MCGEN_TRACE_CONTEXT *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xAu, WPP_67753f1af5ac3da253a8cc69796da9da_Traceguids, v5);
    }
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    if ( (Microsoft_Windows_NetworkProvisioningEnableBits[0] & 0x400) != 0 )
      McTemplateU0qd_EtwEventWriteTransfer(v8, v6, 1u, v7);
  }
  else
  {
    v26.dismissed_ = 0;
    v26.fun_ = (void (__fastcall *)(void *))WlanCloseHandleWrapper;
    v26.p1_ = (WWAN_INTERFACE_OBJECT *const)hWlan;
    v9 = WlanEnumInterfaces(hWlan, 0, &pInterfaceList);
    v7 = v9;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xBu, WPP_67753f1af5ac3da253a8cc69796da9da_Traceguids, v9);
      }
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      j.dismissed_ = 0;
      j.fun_ = (void (__fastcall *)(void *))WlanFreeMemory;
      j.p1_ = (WWAN_INTERFACE_OBJECT *const)pInterfaceList;
      if ( pInterfaceList->dwNumberOfItems )
      {
        Myfirst = wlanNodes->_Mypair._Myval2._Myfirst;
        Mylast = wlanNodes->_Mypair._Myval2._Mylast;
        if ( wlanNodes->_Mypair._Myval2._Myfirst != Mylast )
        {
          do
          {
            std::wstring::wstring(&Path, L"./wlan:name");
            WcmCommon::Xml::ExtractText<std::shared_ptr<WcmCommon::Xml::Node>>(&profileName, Myfirst, &Path);
            std::wstring::_Tidy_deallocate(&Path);
            std::wstring::wstring(&v28, L"@Priority");
            WcmCommon::Xml::ExtractText<std::shared_ptr<WcmCommon::Xml::Node>>(&priorityStr, Myfirst, &v28);
            std::wstring::_Tidy_deallocate(&v28);
            if ( priorityStr._Mypair._Myval2._Mysize )
              _a3 = std::stoul(&priorityStr, v12, v13);
            else
              _a3 = 10;
            v15 = pInterfaceList;
            if ( pInterfaceList->dwNumberOfItems )
            {
              do
              {
                p_InterfaceGuid = &v15->InterfaceInfo[v4].InterfaceGuid;
                if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
                  && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
                {
                  v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&profileName._Mypair._Myval2);
                  WPP_SF_Sd_guid_(*(_QWORD *)(v17 + 16), 0xDu, (const _GUID *)v17, v16, _a3, Logger);
                }
                v19 = 0x8E38E38E38E38E39uLL
                    * (((char *)profileList->_Mypair._Myval2._Mylast - (char *)profileList->_Mypair._Myval2._Myfirst) >> 3);
                std::wstring::wstring(&Path, &profileName);
                Profile::Profile(&v29, MediaTypeWlan, v20, p_InterfaceGuid, _a3, v19);
                v22 = profileList->_Mypair._Myval2._Mylast;
                if ( v22 == profileList->_Mypair._Myval2._Myend )
                {
                  std::vector<Profile>::_Emplace_reallocate<Profile>(
                    profileList,
                    profileList->_Mypair._Myval2._Mylast,
                    v21);
                }
                else
                {
                  std::_Construct_in_place<Profile,Profile>(v22, v21);
                  ++profileList->_Mypair._Myval2._Mylast;
                }
                std::wstring::_Tidy_deallocate(&v29.Name);
                ++v4;
                v15 = pInterfaceList;
              }
              while ( v4 < pInterfaceList->dwNumberOfItems );
            }
            std::wstring::_Tidy_deallocate(&priorityStr);
            std::wstring::_Tidy_deallocate(&profileName);
            ++Myfirst;
            v4 = 0;
          }
          while ( Myfirst != Mylast );
        }
        ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
        v7 = 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control->ReserveSpace[28] & 2) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->Control.Logger, 0xCu, WPP_67753f1af5ac3da253a8cc69796da9da_Traceguids);
        }
        ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&j);
        v7 = -2147024841;
      }
    }
    ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(&v26);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003160c  mov     [rsp-8+arg_10], rbx
0x180031611  push    rbp
0x180031612  push    rsi
0x180031613  push    rdi
0x180031614  push    r12
0x180031616  push    r13
0x180031618  push    r14
0x18003161a  push    r15
0x18003161c  lea     rbp, [rsp-60h]
0x180031621  sub     rsp, 160h
0x180031628  mov     rax, cs:__security_cookie
0x18003162f  xor     rax, rsp
0x180031632  mov     [rbp+90h+var_38], rax
0x180031636  mov     r15, profileList
0x180031639  mov     rdi, wlanNodes
0x18003163c  xor     r14d, r14d
0x18003163f  mov     [rbp+90h+dwVersion], r14d
0x180031643  mov     [rbp+90h+hWlan], r14
0x180031647  mov     [rbp+90h+pInterfaceList], r14
0x18003164b  lea     r9, [rbp+90h+hWlan]; phClientHandle
0x18003164f  lea     r8, [rbp+90h+dwVersion]; pdwNegotiatedVersion
0x180031653  xor     edx, edx; pReserved
0x180031655  lea     esi, [profileList+2]
0x180031658  mov     ecx, esi; dwClientVersion
0x18003165a  call    cs:__imp_WlanOpenHandle
0x180031660  mov     ebx, eax
0x180031662  test    eax, eax
0x180031664  jz      short loc_1800316C2
0x180031666  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003166d  mov     wlanNodes, cs:WPP_GLOBAL_Control
0x180031674  cmp     wlanNodes, rdi
0x180031677  jz      short loc_180031695
0x180031679  test    [wlanNodes+1Ch], sil
0x18003167d  jz      short loc_180031695
0x18003167f  lea     edx, [rsi+8]; id
0x180031682  mov     r9d, eax; _a1
0x180031685  lea     r8, WPP_67753f1af5ac3da253a8cc69796da9da_Traceguids; TraceGuid
0x18003168c  mov     wlanNodes, [wlanNodes+10h]; Logger
0x180031690  call    WPP_SF_d
0x180031695  test    ebx, ebx
0x180031697  jle     short loc_1800316A2
0x180031699  movzx   ebx, bx
0x18003169c  or      ebx, 80070000h
0x1800316a2  test    byte ptr cs:Microsoft_Windows_NetworkProvisioningEnableBits+1, 4
0x1800316a9  jz      loc_18003193E
0x1800316af  mov     r9d, ebx; Descriptor
0x1800316b2  mov     r8d, 1; Context
0x1800316b8  call    McTemplateU0qd_EtwEventWriteTransfer
0x1800316bd  jmp     loc_18003193E
0x1800316c2  mov     wlanNodes, [rbp+90h+hWlan]; hClientHandle
0x1800316c6  mov     [rsp+190h+var_140.dismissed_], r14b
0x1800316cb  lea     rax, ?WlanCloseHandleWrapper@@YAKPEAX@Z; WlanCloseHandleWrapper(void *)
0x1800316d2  mov     [rsp+190h+var_140.fun_], rax
0x1800316d7  mov     [rsp+190h+var_140.p1_], wlanNodes
0x1800316dc  lea     r8, [rbp+90h+pInterfaceList]; ppInterfaceList
0x1800316e0  xor     edx, edx; pReserved
0x1800316e2  call    cs:__imp_WlanEnumInterfaces
0x1800316e8  mov     ebx, eax
0x1800316ea  test    eax, eax
0x1800316ec  jz      short loc_180031735
0x1800316ee  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x1800316f5  mov     wlanNodes, cs:WPP_GLOBAL_Control
0x1800316fc  cmp     wlanNodes, rdi
0x1800316ff  jz      short loc_18003171F
0x180031701  test    [wlanNodes+1Ch], sil
0x180031705  jz      short loc_18003171F
0x180031707  mov     edx, 0Bh; id
0x18003170c  mov     r9d, eax; _a1
0x18003170f  lea     r8, WPP_67753f1af5ac3da253a8cc69796da9da_Traceguids; TraceGuid
0x180031716  mov     wlanNodes, [wlanNodes+10h]; Logger
0x18003171a  call    WPP_SF_d
0x18003171f  test    ebx, ebx
0x180031721  jle     loc_180031934
0x180031727  movzx   ebx, bx
0x18003172a  or      ebx, 80070000h
0x180031730  jmp     loc_180031934
0x180031735  mov     wlanNodes, [rbp+90h+pInterfaceList]
0x180031739  mov     rax, cs:__imp_WlanFreeMemory
0x180031740  mov     [rsp+190h+j.dismissed_], r14b
0x180031745  mov     [rsp+190h+j.fun_], rax
0x18003174a  mov     [rsp+190h+j.p1_], wlanNodes
0x18003174f  cmp     [wlanNodes], r14d
0x180031752  jnz     short loc_180031797
0x180031754  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x18003175b  mov     wlanNodes, cs:WPP_GLOBAL_Control
0x180031762  cmp     wlanNodes, rdi
0x180031765  jz      short loc_180031783
0x180031767  test    [wlanNodes+1Ch], sil
0x18003176b  jz      short loc_180031783
0x18003176d  mov     edx, 0Ch; id
0x180031772  lea     r8, WPP_67753f1af5ac3da253a8cc69796da9da_Traceguids; TraceGuid
0x180031779  mov     wlanNodes, [wlanNodes+10h]; Logger
0x18003177d  call    WPP_SF_
0x180031782  nop
0x180031783  lea     wlanNodes, [rsp+190h+j]; j
0x180031788  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x18003178d  mov     ebx, 80070037h
0x180031792  jmp     loc_180031934
0x180031797  mov     rsi, [rdi]
0x18003179a  mov     r12, [rdi+8]
0x18003179e  cmp     rsi, r12
0x1800317a1  jz      loc_180031927
0x1800317a7  lea     rdi, WPP_GLOBAL_Control
0x1800317ae  lea     profileList, aWlanName; "./wlan:name"
0x1800317b5  lea     wlanNodes, [rsp+190h+Path]; this
0x1800317ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800317bf  nop
0x1800317c0  lea     r8, [rsp+190h+Path]; Path
0x1800317c5  mov     profileList, rsi; s
0x1800317c8  lea     wlanNodes, [rbp+90h+profileName]; result
0x1800317cc  call    ??$ExtractText@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@Xml@WcmCommon@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@3@AEBV23@@Z; WcmCommon::Xml::ExtractText<std::shared_ptr<WcmCommon::Xml::Node>>(std::shared_ptr<WcmCommon::Xml::Node> const &,std::wstring const &)
0x1800317d1  nop
0x1800317d2  lea     wlanNodes, [rsp+190h+Path]; this
0x1800317d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800317dc  lea     profileList, aPriority; "@Priority"
0x1800317e3  lea     wlanNodes, [rbp+90h+var_100]; this
0x1800317e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800317ec  nop
0x1800317ed  lea     r8, [rbp+90h+var_100]; Path
0x1800317f1  mov     profileList, rsi; s
0x1800317f4  lea     wlanNodes, [rbp+90h+priorityStr]; result
0x1800317f8  call    ??$ExtractText@V?$shared_ptr@VNode@Xml@WcmCommon@@@std@@@Xml@WcmCommon@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$shared_ptr@VNode@Xml@WcmCommon@@@3@AEBV23@@Z; WcmCommon::Xml::ExtractText<std::shared_ptr<WcmCommon::Xml::Node>>(std::shared_ptr<WcmCommon::Xml::Node> const &,std::wstring const &)
0x1800317fd  nop
0x1800317fe  lea     wlanNodes, [rbp+90h+var_100]; this
0x180031802  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031807  cmp     [rbp+90h+priorityStr._Mypair._Myval2._Mysize], r14
0x18003180b  jnz     short loc_180031815
0x18003180d  mov     r13d, 0Ah
0x180031813  jmp     short loc_180031821
0x180031815  lea     wlanNodes, [rbp+90h+priorityStr]; _Str
0x180031819  call    ?stoul@std@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoul(std::wstring const &,unsigned __int64 *,int)
0x18003181e  mov     r13d, eax
0x180031821  mov     profileList, [rbp+90h+pInterfaceList]
0x180031825  cmp     dword ptr [profileList], 0
0x180031828  jbe     loc_180031901
0x18003182e  mov     eax, r14d
0x180031831  imul    wlanNodes, rax, 214h
0x180031838  lea     r10, [profileList+8]
0x18003183c  add     r10, wlanNodes
0x18003183f  mov     [rsp+190h+var_160], r10
0x180031844  mov     r8, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18003184b  cmp     r8, rdi
0x18003184e  jz      short loc_18003187B
0x180031850  test    byte ptr [r8+1Ch], 10h
0x180031855  jz      short loc_18003187B
0x180031857  lea     wlanNodes, [rbp+90h+profileName]; this
0x18003185b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180031860  mov     r9, rax; _a2
0x180031863  mov     edx, 0Dh; id
0x180031868  mov     [rsp+190h+Logger], r10; Logger
0x18003186d  mov     [rsp+190h+_a3], r13d; _a3
0x180031872  mov     wlanNodes, [r8+10h]; Logger
0x180031876  call    WPP_SF_Sd_guid_
0x18003187b  mov     rbx, [r15+8]
0x18003187f  sub     rbx, [r15]
0x180031882  sar     rbx, 3
0x180031886  mov     rax, 8E38E38E38E38E39h
0x180031890  imul    rbx, rax
0x180031894  lea     profileList, [rbp+90h+profileName]; _Right
0x180031898  lea     wlanNodes, [rsp+190h+Path]; this
0x18003189d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800318a2  mov     [rsp+190h+Logger], rbx
0x1800318a7  mov     [rsp+190h+_a3], r13d
0x1800318ac  mov     r9, [rsp+190h+var_160]
0x1800318b1  mov     r8, rax
0x1800318b4  xor     edx, edx
0x1800318b6  lea     wlanNodes, [rbp+90h+var_E0]
0x1800318ba  call    ??0Profile@@QEAA@W4MediaType@0@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@I_K@Z; Profile::Profile(Profile::MediaType,std::wstring,_GUID const &,uint,unsigned __int64)
0x1800318bf  nop
0x1800318c0  mov     wlanNodes, [r15+8]; _Obj
0x1800318c4  cmp     wlanNodes, [r15+10h]
0x1800318c8  jz      short loc_1800318D9
0x1800318ca  mov     profileList, rax; <_Args_0>
0x1800318cd  call    ??$_Construct_in_place@UProfile@@U1@@std@@YAXAEAUProfile@@$$QEAU1@@Z; std::_Construct_in_place<Profile,Profile>(Profile &,Profile &&)
0x1800318d2  add     qword ptr [r15+8], 48h ; 'H'
0x1800318d7  jmp     short loc_1800318E8
0x1800318d9  mov     r8, rax; <_Val_0>
0x1800318dc  mov     profileList, wlanNodes; _Whereptr
0x1800318df  mov     wlanNodes, r15; this
0x1800318e2  call    ??$_Emplace_reallocate@UProfile@@@?$vector@UProfile@@V?$allocator@UProfile@@@std@@@std@@AEAAPEAUProfile@@QEAU2@$$QEAU2@@Z; std::vector<Profile>::_Emplace_reallocate<Profile>(Profile * const,Profile &&)
0x1800318e7  nop
0x1800318e8  lea     wlanNodes, [rbp+90h+var_D8]; this
0x1800318ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800318f1  inc     r14d
0x1800318f4  mov     profileList, [rbp+90h+pInterfaceList]
0x1800318f8  cmp     r14d, [profileList]
0x1800318fb  jb      loc_18003182E
0x180031901  lea     wlanNodes, [rbp+90h+priorityStr]; this
0x180031905  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003190a  nop
0x18003190b  lea     wlanNodes, [rbp+90h+profileName]; this
0x18003190f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180031914  add     rsi, 10h
0x180031918  cmp     rsi, r12
0x18003191b  mov     r14d, 0
0x180031921  jnz     loc_1800317AE
0x180031927  lea     wlanNodes, [rsp+190h+j]; j
0x18003192c  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x180031931  mov     ebx, r14d
0x180031934  lea     wlanNodes, [rsp+190h+var_140]; j
0x180031939  call    ??$SafeExecute@V?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl1@P6AXPEAX@ZPEAUWWAN_INTERFACE_OBJECT@@@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *>>(ScopeGuardImpl1<void (*)(void *),WWAN_INTERFACE_OBJECT *> &)
0x18003193e  mov     eax, ebx
0x180031940  mov     wlanNodes, [rbp+90h+var_38]
0x180031944  xor     wlanNodes, rsp; StackCookie
0x180031947  call    __security_check_cookie
0x18003194c  mov     rbx, [rsp+190h+arg_10]
0x180031954  add     rsp, 160h
0x18003195b  pop     r15
0x18003195d  pop     r14
0x18003195f  pop     r13
0x180031961  pop     r12
0x180031963  pop     rdi
0x180031964  pop     rsi
0x180031965  pop     rbp
0x180031966  retn
```
