# WebRuntimeDiagnostics::LCIEDiagnosticsSession::CreateIsoSession(void)

- ea: `0x1800689a4`
- end: `0x180068b78`
- name: `?CreateIsoSession@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@SAJXZ`
- size: `468`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800687a0`
- `0x180072c04`

## callees

- `0x180018b30`
- `0x18002652c`
- `0x18002b5a0`
- `0x180037b5c`
- `0x18006818c`
- `0x18006842c`
- `0x1800687ac`
- `0x1800689a4`
- `0x180068be8`
- `0x18006915c`
- `0x1800693a0`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x180068a6d`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x180068a6d`
- `iertutil!__imp_?IEConfiguration_SetBrowserAppProfile@@YAJPEBGKK@Z` at `0x180068a60`
- `iertutil!__imp_?IEConfiguration_SetBrowserAppProfile@@YAJPEBGKK@Z` at `0x180068a60`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180068b22`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180068b22`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180068ae5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180068ae5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068b49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068b49`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180068a8c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180068a8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WebRuntimeDiagnostics::LCIEDiagnosticsSession::CreateIsoSession(
        WebRuntimeDiagnostics::LCIEDiagnosticsSession *a1)
{
  WebRuntimeDiagnostics::LCIEDiagnosticsSession *v1; // rbx
  __int64 v2; // rax
  unsigned int TargetIsoProcessID; // ebx
  DWORD v4; // edi
  __int64 v5; // rdx
  WebRuntimeDiagnostics::LCIEDiagnosticsSession *v6; // rcx
  HANDLE v7; // rax
  WebRuntimeDiagnostics::LCIEDiagnosticsSession *v8; // rcx
  const char *v9; // r9
  unsigned int v10; // edx
  WebRuntimeDiagnostics::LCIEDiagnosticsSession *v11; // rcx
  const char *v12; // r9
  const char *v13; // r9
  _BYTE v15[64]; // [rsp+20h] [rbp-29h] BYREF
  _BYTE v16[64]; // [rsp+60h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  void *dwProcessId; // [rsp+B0h] [rbp+67h] BYREF
  WebRuntimeDiagnostics::LCIEDiagnosticsSession *v19; // [rsp+B8h] [rbp+6Fh]

  if ( !WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_instance )
  {
    v1 = (WebRuntimeDiagnostics::LCIEDiagnosticsSession *)operator new(0xF0u);
    v19 = v1;
    *(_BYTE *)v1 = 0;
    dwProcessId = &CritSec_TryExclusive;
    std::function<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> (wil::critical_section &)>::function<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> (wil::critical_section &)>(
      v15,
      &dwProcessId);
    dwProcessId = &CritSec_Exclusive;
    v2 = std::function<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> (wil::critical_section &)>::function<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> (wil::critical_section &)>(
           v16,
           &dwProcessId);
    ThreadSafeData<std::unordered_map<unsigned long,void *>,wil::critical_section,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>>::ThreadSafeData<std::unordered_map<unsigned long,void *>,wil::critical_section,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>>(
      (char *)v1 + 8,
      v2);
    WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_instance = v1;
  }
  LODWORD(dwProcessId) = 0;
  TargetIsoProcessID = WebRuntimeDiagnostics::LCIEDiagnosticsSession::GetTargetIsoProcessID(
                         a1,
                         (unsigned int *)&dwProcessId);
  if ( !TargetIsoProcessID )
  {
    v4 = (unsigned int)dwProcessId;
    if ( (_DWORD)dwProcessId )
    {
      if ( *(_BYTE *)WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_instance )
        goto LABEL_10;
      IEConfiguration_SetBrowserAppProfile(L"MicrosoftEdge", 8u, 0);
      LOBYTE(v5) = 1;
      IEConfiguration_SetBool(536870927, v5);
      TargetIsoProcessID = WebRuntimeDiagnostics::LCIEDiagnosticsSession::CreateEventAndSetSecurityAccess(v6);
      if ( !TargetIsoProcessID )
      {
        v7 = OpenProcess(0x100400u, 0, v4);
        if ( !v7 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x6C,
            (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticssession.cpp",
            v9);
        TargetIsoProcessID = WebRuntimeDiagnostics::LCIEDiagnosticsSession::SetProcessTrustedSID(v8, v7);
        if ( !TargetIsoProcessID )
        {
LABEL_10:
          if ( v4 != WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_isoProcessId )
          {
            WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_isoProcessId = v4;
            WebRuntimeDiagnostics::LCIEDiagnosticsSession::UninitializeIsoSession(WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_instance);
            WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_isoManagerInitializedEvent = CreateEventW(0, 0, 0, 0);
            if ( !WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_isoManagerInitializedEvent )
              wil::details::in1diag3::_FailFast_GetLastError(
                retaddr,
                (void *)0x7A,
                (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticssession.cpp",
                v12);
            TargetIsoProcessID = WebRuntimeDiagnostics::LCIEDiagnosticsSession::OpenDiagnosticsTargetScope(v11, v10);
            if ( !TargetIsoProcessID
              && WaitForSingleObject(
                   WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_isoManagerInitializedEvent,
                   0x2710u) )
            {
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x82,
                (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticssession.cpp",
                v13);
            }
            CloseHandle(WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_isoManagerInitializedEvent);
            WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_isoManagerInitializedEvent = 0;
          }
        }
      }
    }
    else
    {
      return (unsigned int)-2147023728;
    }
  }
  return TargetIsoProcessID;
}

```

## disassembly

```asm
0x1800689a4  mov     [rsp-8+arg_10], rbx
0x1800689a9  mov     [rsp-8+arg_18], rdi
0x1800689ae  push    rbp
0x1800689af  lea     rbp, [rsp-57h]
0x1800689b4  sub     rsp, 0A0h
0x1800689bb  cmp     cs:?s_instance@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@0PEAV12@EA, 0; WebRuntimeDiagnostics::LCIEDiagnosticsSession * WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_instance
0x1800689c3  jnz     short loc_180068A20
0x1800689c5  mov     ecx, 0F0h; Size
0x1800689ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800689cf  mov     rbx, rax
0x1800689d2  mov     [rbp+57h+arg_8], rax
0x1800689d6  mov     byte ptr [rax], 0
0x1800689d9  lea     rax, CritSec_TryExclusive
0x1800689e0  mov     [rbp+57h+dwProcessId], rax
0x1800689e4  lea     rdx, [rbp+57h+dwProcessId]
0x1800689e8  lea     rcx, [rbp+57h+var_80]
0x1800689ec  call    ??$?0P6A?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVcritical_section@1@@Z$0A@@?$function@$$A6A?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVcritical_section@2@@Z@std@@QEAA@$$QEAP6A?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVcritical_section@3@@Z@Z; std::function<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> (wil::critical_section &)>::function<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> (wil::critical_section &)>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> (*&&)(wil::critical_section &))
0x1800689f1  mov     r8, rax
0x1800689f4  lea     rax, CritSec_Exclusive
0x1800689fb  mov     [rbp+57h+dwProcessId], rax
0x1800689ff  lea     rdx, [rbp+57h+dwProcessId]
0x180068a03  lea     rcx, [rbp+57h+var_40]
0x180068a07  call    ??$?0P6A?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVcritical_section@1@@Z$0A@@?$function@$$A6A?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVcritical_section@2@@Z@std@@QEAA@$$QEAP6A?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVcritical_section@3@@Z@Z; std::function<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> (wil::critical_section &)>::function<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> (wil::critical_section &)>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> (*&&)(wil::critical_section &))
0x180068a0c  mov     rdx, rax
0x180068a0f  lea     rcx, [rbx+8]
0x180068a13  call    ??0?$ThreadSafeData@V?$unordered_map@KPEAXU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKPEAX@std@@@2@@std@@Vcritical_section@wil@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@4@@@IEAA@V?$function@$$A6A?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAVcritical_section@2@@Z@std@@0@Z; ThreadSafeData<std::unordered_map<ulong,void *>,wil::critical_section,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>>::ThreadSafeData<std::unordered_map<ulong,void *>,wil::critical_section,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>>(std::function<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> (wil::critical_section &)>,std::function<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> (wil::critical_section &)>)
0x180068a18  nop
0x180068a19  mov     cs:?s_instance@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@0PEAV12@EA, rbx; WebRuntimeDiagnostics::LCIEDiagnosticsSession * WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_instance
0x180068a20  mov     dword ptr [rbp+57h+dwProcessId], 0
0x180068a27  lea     rdx, [rbp+57h+dwProcessId]; unsigned int *
0x180068a2b  call    ?GetTargetIsoProcessID@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@AEAAJPEAK@Z; WebRuntimeDiagnostics::LCIEDiagnosticsSession::GetTargetIsoProcessID(ulong *)
0x180068a30  mov     ebx, eax
0x180068a32  test    eax, eax
0x180068a34  jnz     loc_180068B61
0x180068a3a  mov     edi, dword ptr [rbp+57h+dwProcessId]
0x180068a3d  test    edi, edi
0x180068a3f  jz      loc_180068B5C
0x180068a45  mov     rcx, cs:?s_instance@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@0PEAV12@EA; WebRuntimeDiagnostics::LCIEDiagnosticsSession * WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_instance
0x180068a4c  mov     dl, [rcx]
0x180068a4e  nop
0x180068a4f  test    dl, dl
0x180068a51  jnz     short loc_180068ABD
0x180068a53  xor     r8d, r8d
0x180068a56  lea     edx, [rax+8]
0x180068a59  lea     rcx, aMicrosoftedge; "MicrosoftEdge"
0x180068a60  call    cs:__imp_?IEConfiguration_SetBrowserAppProfile@@YAJPEBGKK@Z; IEConfiguration_SetBrowserAppProfile(ushort const *,ulong,ulong)
0x180068a66  mov     dl, 1
0x180068a68  mov     ecx, 2000000Fh
0x180068a6d  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x180068a73  call    ?CreateEventAndSetSecurityAccess@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@AEAAJXZ; WebRuntimeDiagnostics::LCIEDiagnosticsSession::CreateEventAndSetSecurityAccess(void)
0x180068a78  mov     ebx, eax
0x180068a7a  test    eax, eax
0x180068a7c  jnz     loc_180068B61
0x180068a82  mov     r8d, edi; dwProcessId
0x180068a85  xor     edx, edx; bInheritHandle
0x180068a87  mov     ecx, 100400h; dwDesiredAccess
0x180068a8c  call    cs:__imp_OpenProcess
0x180068a92  test    rax, rax
0x180068a95  jnz     short loc_180068AAB
0x180068a97  mov     rcx, [rbp+5Fh]; this
0x180068a9b  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180068aa2  lea     edx, [rbx+6Ch]; void *
0x180068aa5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180068aab  mov     rdx, rax; void *
0x180068aae  call    ?SetProcessTrustedSID@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@AEAAJPEAX@Z; WebRuntimeDiagnostics::LCIEDiagnosticsSession::SetProcessTrustedSID(void *)
0x180068ab3  mov     ebx, eax
0x180068ab5  test    eax, eax
0x180068ab7  jnz     loc_180068B61
0x180068abd  cmp     edi, cs:?s_isoProcessId@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@0KA; ulong WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_isoProcessId
0x180068ac3  jz      loc_180068B61
0x180068ac9  mov     cs:?s_isoProcessId@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@0KA, edi; ulong WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_isoProcessId
0x180068acf  mov     rcx, cs:?s_instance@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@0PEAV12@EA; this
0x180068ad6  call    ?UninitializeIsoSession@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@AEAAXXZ; WebRuntimeDiagnostics::LCIEDiagnosticsSession::UninitializeIsoSession(void)
0x180068adb  xor     r9d, r9d; lpName
0x180068ade  xor     r8d, r8d; bInitialState
0x180068ae1  xor     edx, edx; bManualReset
0x180068ae3  xor     ecx, ecx; lpEventAttributes
0x180068ae5  call    cs:__imp_CreateEventW
0x180068aeb  mov     cs:?s_isoManagerInitializedEvent@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@0PEAXEA, rax; void * WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_isoManagerInitializedEvent
0x180068af2  test    rax, rax
0x180068af5  jnz     short loc_180068B0B
0x180068af7  mov     rcx, [rbp+5Fh]; this
0x180068afb  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180068b02  lea     edx, [rax+7Ah]; void *
0x180068b05  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180068b0b  call    ?OpenDiagnosticsTargetScope@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@AEAAJK@Z; WebRuntimeDiagnostics::LCIEDiagnosticsSession::OpenDiagnosticsTargetScope(ulong)
0x180068b10  mov     ebx, eax
0x180068b12  test    eax, eax
0x180068b14  jnz     short loc_180068B42
0x180068b16  mov     edx, 2710h; dwMilliseconds
0x180068b1b  mov     rcx, cs:?s_isoManagerInitializedEvent@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@0PEAXEA; hHandle
0x180068b22  call    cs:__imp_WaitForSingleObject
0x180068b28  test    eax, eax
0x180068b2a  jz      short loc_180068B42
0x180068b2c  mov     rcx, [rbp+5Fh]; this
0x180068b30  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x180068b37  mov     edx, 82h; void *
0x180068b3c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180068b42  mov     rcx, cs:?s_isoManagerInitializedEvent@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@0PEAXEA; hObject
0x180068b49  call    cs:__imp_CloseHandle
0x180068b4f  mov     cs:?s_isoManagerInitializedEvent@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@0PEAXEA, 0; void * WebRuntimeDiagnostics::LCIEDiagnosticsSession::s_isoManagerInitializedEvent
0x180068b5a  jmp     short loc_180068B61
0x180068b5c  mov     ebx, 80070490h
0x180068b61  mov     eax, ebx
0x180068b63  lea     r11, [rsp+0A0h+var_s0]
0x180068b6b  mov     rbx, [r11+20h]
0x180068b6f  mov     rdi, [r11+28h]
0x180068b73  mov     rsp, r11
0x180068b76  pop     rbp
0x180068b77  retn
```
