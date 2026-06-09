# StandbyMonitor::ProcessDhcpChange(void)

- ea: `0x18007ed24`
- end: `0x18007eed8`
- name: `?ProcessDhcpChange@StandbyMonitor@@YAXXZ`
- size: `436`
- prototype: `void __fastcall(StandbyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000eae0`

## callees

- `0x18000c090`
- `0x18000e190`
- `0x180020d20`
- `0x18007ed24`
- `0x18007eeec`
- `0x18007ef0c`
- `0x18007ef30`
- `0x18007eff0`
- `0x18009284c`
- `0x18011a8d8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007edc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007eded`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007edc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007eded`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18007eda6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryA` at `0x18007eda6`

## string_xrefs

- `0x18007ee43`: `onecore\net\netprofiles\service\src\standby\lib\standbymonitor.cpp`
- `0x18007edbd`: `DhcpGetDhcpServicedConnections`
- `0x18007ed9f`: `dhcpcsvc.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall StandbyMonitor::ProcessDhcpChange(StandbyMonitor *this)
{
  const char *v1; // r9
  HMODULE v2; // rsi
  HMODULE LibraryA; // rax
  HMODULE v4; // rbx
  const char *v5; // r9
  __int128 v6; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HMODULE v8; // [rsp+40h] [rbp+8h] BYREF
  FARPROC ProcAddress; // [rsp+48h] [rbp+10h] BYREF

  v6 = 0;
  StandbyMonitor::details::Singleton<StandbyMonitor::StandbyMonitor>::GetInstance(&v6);
  try
  {
    v2 = (HMODULE)v6;
    if ( !(_QWORD)v6 )
    {
LABEL_19:
      if ( *((_QWORD *)&v6 + 1) )
        std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v6 + 1));
      return;
    }
    if ( qword_1801BE0C8 && qword_1801BE0D0 )
    {
      std::function<unsigned long (unsigned long,wchar_t * * *,unsigned long *)>::operator=<unsigned long (*)(unsigned long,wchar_t * * *,unsigned long *),0>(
        v6 + 592,
        &qword_1801BE0C8);
      std::function<void (void * *)>::operator=<void (*)(void * *),0>(v2 + 164, &qword_1801BE0D0);
LABEL_18:
      v8 = v2;
      WcmCommon::ThreadPoolWorkQueue::SubmitWork__StandbyMonitor::ProcessDhcpChange_::_6_::_lambda_1___(v2 + 4, &v8);
      goto LABEL_19;
    }
    if ( !*(_BYTE *)(v6 + 584) )
    {
      LibraryA = LoadLibraryA("dhcpcsvc.dll");
      v4 = LibraryA;
      v8 = LibraryA;
      if ( LibraryA )
      {
        ProcAddress = GetProcAddress(LibraryA, "DhcpGetDhcpServicedConnections");
        std::function<unsigned long (unsigned long,wchar_t * * *,unsigned long *)>::operator=<unsigned long (*)(unsigned long,wchar_t * * *,unsigned long *),0>(
          v2 + 148,
          &ProcAddress);
        ProcAddress = GetProcAddress(v4, "DhcpFreeMem");
        std::function<void (void * *)>::operator=<void (*)(void * *),0>(v2 + 164, &ProcAddress);
        if ( *((_QWORD *)v2 + 81) && *((_QWORD *)v2 + 89) )
        {
          std::_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>::reset(v2 + 144);
          *((_QWORD *)v2 + 72) = v4;
          v8 = 0;
          *((_BYTE *)v2 + 584) = 1;
        }
        else
        {
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x3D8,
            (unsigned int)"onecore\\net\\netprofiles\\service\\src\\standby\\lib\\standbymonitor.cpp",
            v5);
          std::_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>::reset(v2 + 144);
          *((_QWORD *)v2 + 72) = 0;
          *((_BYTE *)v2 + 584) = 1;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v8);
      if ( !*((_BYTE *)v2 + 584) )
        std::_Throw_bad_optional_access();
    }
    if ( *((_QWORD *)v2 + 72) )
      goto LABEL_18;
    if ( *((_QWORD *)&v6 + 1) )
      std::_Ref_count_base::_Decref(*((std::_Ref_count_base **)&v6 + 1));
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x43E,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\standby\\lib\\standbymonitor.cpp",
      v1);
  }
}

```

## disassembly

```asm
0x18007ed24  mov     rax, rsp
0x18007ed27  mov     [rax+18h], rbx
0x18007ed2b  mov     [rax+20h], rsi
0x18007ed2f  push    rdi
0x18007ed30  sub     rsp, 30h
0x18007ed34  xorps   xmm0, xmm0
0x18007ed37  movups  xmmword ptr [rax-18h], xmm0
0x18007ed3b  lea     rcx, [rax-18h]
0x18007ed3f  call    ?GetInstance@?$Singleton@VStandbyMonitor@1@@details@StandbyMonitor@@SA?AV?$shared_ptr@VStandbyMonitor@1@@std@@XZ; StandbyMonitor::details::Singleton<StandbyMonitor::StandbyMonitor>::GetInstance(void)
0x18007ed44  nop
0x18007ed45  mov     rsi, [rsp+38h+var_18]
0x18007ed4a  test    rsi, rsi
0x18007ed4d  jz      loc_18007EEB6
0x18007ed53  cmp     cs:qword_1801BE0C8, 0
0x18007ed5b  jz      short loc_18007ED92
0x18007ed5d  cmp     cs:qword_1801BE0D0, 0
0x18007ed65  jz      short loc_18007ED92
0x18007ed67  lea     rcx, [rsi+250h]
0x18007ed6e  lea     rdx, qword_1801BE0C8
0x18007ed75  call    ??$?4P6AKKPEAPEAPEA_WPEAK@Z$0A@@?$function@$$A6AKKPEAPEAPEA_WPEAK@Z@std@@QEAAAEAV01@$$QEAP6AKKPEAPEAPEA_WPEAK@Z@Z; std::function<ulong (ulong,wchar_t * * *,ulong *)>::operator=<ulong (*)(ulong,wchar_t * * *,ulong *),0>(ulong (*&&)(ulong,wchar_t * * *,ulong *))
0x18007ed7a  lea     rcx, [rsi+290h]
0x18007ed81  lea     rdx, qword_1801BE0D0
0x18007ed88  call    ??$?4P6AXPEAPEAX@Z$0A@@?$function@$$A6AXPEAPEAX@Z@std@@QEAAAEAV01@$$QEAP6AXPEAPEAX@Z@Z; std::function<void (void * *)>::operator=<void (*)(void * *),0>(void (*&&)(void * *))
0x18007ed8d  jmp     loc_18007EEA2
0x18007ed92  cmp     byte ptr [rsi+248h], 0
0x18007ed99  jnz     loc_18007EE86
0x18007ed9f  lea     rcx, LibFileName; "dhcpcsvc.dll"
0x18007eda6  call    cs:__imp_LoadLibraryA
0x18007edac  mov     rbx, rax
0x18007edaf  mov     [rsp+38h+arg_0], rax
0x18007edb4  test    rax, rax
0x18007edb7  jz      loc_18007EE6E
0x18007edbd  lea     rdx, aDhcpgetdhcpser; "DhcpGetDhcpServicedConnections"
0x18007edc4  mov     rcx, rax; hModule
0x18007edc7  call    cs:__imp_GetProcAddress
0x18007edcd  mov     [rsp+38h+arg_8], rax
0x18007edd2  lea     rcx, [rsi+250h]
0x18007edd9  lea     rdx, [rsp+38h+arg_8]
0x18007edde  call    ??$?4P6AKKPEAPEAPEA_WPEAK@Z$0A@@?$function@$$A6AKKPEAPEAPEA_WPEAK@Z@std@@QEAAAEAV01@$$QEAP6AKKPEAPEAPEA_WPEAK@Z@Z; std::function<ulong (ulong,wchar_t * * *,ulong *)>::operator=<ulong (*)(ulong,wchar_t * * *,ulong *),0>(ulong (*&&)(ulong,wchar_t * * *,ulong *))
0x18007ede3  lea     rdx, aDhcpfreemem; "DhcpFreeMem"
0x18007edea  mov     rcx, rbx; hModule
0x18007eded  call    cs:__imp_GetProcAddress
0x18007edf3  mov     [rsp+38h+arg_8], rax
0x18007edf8  lea     rcx, [rsi+290h]
0x18007edff  lea     rdx, [rsp+38h+arg_8]
0x18007ee04  call    ??$?4P6AXPEAPEAX@Z$0A@@?$function@$$A6AXPEAPEAX@Z@std@@QEAAAEAV01@$$QEAP6AXPEAPEAX@Z@Z; std::function<void (void * *)>::operator=<void (*)(void * *),0>(void (*&&)(void * *))
0x18007ee09  cmp     qword ptr [rsi+288h], 0
0x18007ee11  jz      short loc_18007EE3E
0x18007ee13  cmp     qword ptr [rsi+2C8h], 0
0x18007ee1b  jz      short loc_18007EE3E
0x18007ee1d  lea     rdi, [rsi+240h]
0x18007ee24  mov     rcx, rdi
0x18007ee27  call    ?reset@?$_Optional_destruct_base@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@std@@QEAAXXZ; std::_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>::reset(void)
0x18007ee2c  mov     [rdi], rbx
0x18007ee2f  mov     [rsp+38h+arg_0], 0
0x18007ee38  mov     byte ptr [rdi+8], 1
0x18007ee3c  jmp     short loc_18007EE6E
0x18007ee3e  mov     rcx, [rsp+38h]; this
0x18007ee43  lea     r8, aOnecoreNetNetp_10; "onecore\\net\\netprofiles\\service\\src"...
0x18007ee4a  mov     edx, 3D8h; void *
0x18007ee4f  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18007ee54  lea     rbx, [rsi+240h]
0x18007ee5b  mov     rcx, rbx
0x18007ee5e  call    ?reset@?$_Optional_destruct_base@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@std@@QEAAXXZ; std::_Optional_destruct_base<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>,0>::reset(void)
0x18007ee63  mov     qword ptr [rbx], 0
0x18007ee6a  mov     byte ptr [rbx+8], 1
0x18007ee6e  lea     rcx, [rsp+38h+arg_0]
0x18007ee73  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18007ee78  cmp     byte ptr [rsi+248h], 0
0x18007ee7f  jnz     short loc_18007EE86
0x18007ee81  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x18007ee86  cmp     qword ptr [rsi+240h], 0
0x18007ee8e  jnz     short loc_18007EEA2
0x18007ee90  mov     rcx, [rsp+38h+var_10]; this
0x18007ee95  test    rcx, rcx
0x18007ee98  jz      short loc_18007EEA0
0x18007ee9a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007ee9f  nop
0x18007eea0  jmp     short loc_18007EEC8
0x18007eea2  mov     [rsp+38h+arg_0], rsi
0x18007eea7  lea     rcx, [rsi+10h]
0x18007eeab  lea     rdx, [rsp+38h+arg_0]
0x18007eeb0  call    WcmCommon__ThreadPoolWorkQueue__SubmitWork__StandbyMonitor__ProcessDhcpChange____6____lambda_1___
0x18007eeb5  nop
0x18007eeb6  mov     rcx, [rsp+38h+var_10]; this
0x18007eebb  test    rcx, rcx
0x18007eebe  jz      short loc_18007EEC6
0x18007eec0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007eec5  nop
0x18007eec6  jmp     short $+2
0x18007eec8  mov     rbx, [rsp+38h+arg_10]
0x18007eecd  mov     rsi, [rsp+38h+arg_18]
0x18007eed2  add     rsp, 30h
0x18007eed6  pop     rdi
0x18007eed7  retn
```
