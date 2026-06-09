# COleScript::LogTelemetryOnScriptStateStarted(void)

- ea: `0x18007b4b8`
- end: `0x18007b6ea`
- name: `?LogTelemetryOnScriptStateStarted@COleScript@@QEAAXXZ`
- size: `562`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180051b10`

## callees

- `0x1800010c0`
- `0x180001240`
- `0x18004d480`
- `0x180051d1c`
- `0x18007b4b8`
- `0x18007e100`
- `0x180088d70`
- `0x180089030`
- `0x180089640`
- `0x180089ca4`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007b593`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007b66d`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007b593`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007b66d`

## pseudocode

```c
void __fastcall COleScript::LogTelemetryOnScriptStateStarted(COleScript *this)
{
  RegistryBasedThrottle *v2; // rcx
  RegistryBasedThrottle *v3; // rbx
  char *CurrentProcessName; // rax
  _QWORD *ThreadLocalStoragePointer; // rcx
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  char *v9; // rax
  _QWORD *v10; // rcx
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  char *CurrentProcessTree; // [rsp+70h] [rbp+17h] BYREF
  char *v15; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 CLSID; // [rsp+80h] [rbp+27h] BYREF
  __int64 v17; // [rsp+88h] [rbp+2Fh] BYREF
  __int64 v18; // [rsp+90h] [rbp+37h] BYREF
  _QWORD v19[3]; // [rsp+98h] [rbp+3Fh] BYREF
  char *v20; // [rsp+C8h] [rbp+6Fh] BYREF
  __int64 v21; // [rsp+D0h] [rbp+77h] BYREF
  char *v22; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( !COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned int)dword_1800B3D60 > 5 && (unsigned __int8)tlgKeywordOn() )
      {
        v2 = g_pTraceLoggingClient;
        v3 = g_pTraceLoggingClient;
        if ( !*((_DWORD *)g_pTraceLoggingClient + 1754) )
        {
          RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(g_pTraceLoggingClient);
          v2 = g_pTraceLoggingClient;
        }
        v21 = *((_QWORD *)v3 + 874);
        v22 = RegistryBasedThrottle::GetCurrentCallStack(v2);
        CurrentProcessTree = RegistryBasedThrottle::GetCurrentProcessTree(g_pTraceLoggingClient);
        CurrentProcessName = RegistryBasedThrottle::GetCurrentProcessName(g_pTraceLoggingClient);
        ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
        v15 = CurrentProcessName;
        CLSID = *((_QWORD *)this + 24);
        v18 = ThreadLocalStoragePointer[tls_index] + 16LL;
        v17 = 0x2000000;
        LOBYTE(v20) = 1;
        v19[0] = IEConfiguration_GetCLSID(268435459);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v6,
          (unsigned int)byte_1800A97F3,
          v7,
          v8,
          (__int64)v19,
          (__int64)&v18,
          (__int64)&v20,
          (__int64)&v17,
          (__int64)&CLSID,
          (__int64)&v15,
          (__int64)&CurrentProcessTree,
          (__int64)&v22,
          (__int64)&v21);
      }
    }
    else if ( (unsigned int)dword_1800B3D60 > 5 && (unsigned __int8)tlgKeywordOn() )
    {
      v20 = RegistryBasedThrottle::GetCurrentProcessTree(g_pTraceLoggingClient);
      v9 = RegistryBasedThrottle::GetCurrentProcessName(g_pTraceLoggingClient);
      v10 = NtCurrentTeb()->ThreadLocalStoragePointer;
      v22 = v9;
      v19[0] = *((_QWORD *)this + 24);
      v17 = v10[tls_index] + 16LL;
      v18 = 0x2000000;
      LOBYTE(v21) = 1;
      CLSID = IEConfiguration_GetCLSID(268435459);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v11,
        (unsigned int)&byte_1800A98A7,
        v12,
        v13,
        (__int64)&CLSID,
        (__int64)&v17,
        (__int64)&v21,
        (__int64)&v18,
        (__int64)v19,
        (__int64)&v22,
        (__int64)&v20);
    }
    RegistryBasedThrottle::WriteLoggingLocalTickCount(g_pTraceLoggingClient, "JScriptSetScriptStateStarted");
    COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted = 1;
  }
}

```

## disassembly

```asm
0x18007b4b8  push    rbp
0x18007b4ba  push    rbx
0x18007b4bb  push    rdi
0x18007b4bc  lea     rbp, [rsp-47h]
0x18007b4c1  sub     rsp, 0A0h
0x18007b4c8  cmp     cs:?s_fAlreadyLoggedTelemetryOnScriptStateStarted@COleScript@@0HA, 0; int COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted
0x18007b4cf  mov     rdi, rcx
0x18007b4d2  jnz     loc_18007B6DF
0x18007b4d8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging> `wil::Feature<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetImpl(void)'::`2'::impl
0x18007b4df  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(void)
0x18007b4e4  test    al, al
0x18007b4e6  mov     eax, cs:dword_1800B3D60
0x18007b4ec  jz      loc_18007B5FF
0x18007b4f2  cmp     eax, 5
0x18007b4f5  jbe     loc_18007B6C2
0x18007b4fb  call    _tlgKeywordOn
0x18007b500  test    al, al
0x18007b502  jz      loc_18007B6C2
0x18007b508  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007b50f  mov     rbx, rcx
0x18007b512  cmp     dword ptr [rcx+1B68h], 0
0x18007b519  jnz     short loc_18007B527
0x18007b51b  call    ?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)
0x18007b520  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007b527  mov     rax, [rbx+1B50h]
0x18007b52e  mov     [rbp+57h+arg_10], rax
0x18007b532  call    ?GetCurrentCallStack@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentCallStack(void)
0x18007b537  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007b53e  mov     [rbp+57h+arg_18], rax
0x18007b542  call    ?GetCurrentProcessTree@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessTree(void)
0x18007b547  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007b54e  mov     [rbp+57h+var_40], rax
0x18007b552  call    ?GetCurrentProcessName@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessName(void)
0x18007b557  mov     rcx, gs:58h
0x18007b560  mov     edx, cs:_tls_index
0x18007b566  mov     [rbp+57h+var_38], rax
0x18007b56a  mov     rax, [rdi+0C0h]
0x18007b571  mov     [rbp+57h+var_30], rax
0x18007b575  mov     eax, 10h
0x18007b57a  add     rax, [rcx+rdx*8]
0x18007b57e  mov     ecx, 10000003h
0x18007b583  mov     [rbp+57h+var_20], rax
0x18007b587  mov     [rbp+57h+var_28], 2000000h
0x18007b58f  mov     byte ptr [rbp+57h+arg_8], 1
0x18007b593  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18007b599  mov     [rbp+57h+var_18], rax
0x18007b59d  lea     rdx, byte_1800A97F3
0x18007b5a4  lea     rax, [rbp+57h+arg_10]
0x18007b5a8  mov     [rsp+0B0h+var_50], rax
0x18007b5ad  lea     rax, [rbp+57h+arg_18]
0x18007b5b1  mov     [rsp+0B0h+var_58], rax
0x18007b5b6  lea     rax, [rbp+57h+var_40]
0x18007b5ba  mov     [rsp+0B0h+var_60], rax
0x18007b5bf  lea     rax, [rbp+57h+var_38]
0x18007b5c3  mov     [rsp+0B0h+var_68], rax
0x18007b5c8  lea     rax, [rbp+57h+var_30]
0x18007b5cc  mov     [rsp+0B0h+var_70], rax
0x18007b5d1  lea     rax, [rbp+57h+var_28]
0x18007b5d5  mov     [rsp+0B0h+var_78], rax
0x18007b5da  lea     rax, [rbp+57h+arg_8]
0x18007b5de  mov     [rsp+0B0h+var_80], rax
0x18007b5e3  lea     rax, [rbp+57h+var_20]
0x18007b5e7  mov     [rsp+0B0h+var_88], rax
0x18007b5ec  lea     rax, [rbp+57h+var_18]
0x18007b5f0  mov     [rsp+0B0h+var_90], rax
0x18007b5f5  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@D@@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@D@@666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18007b5fa  jmp     loc_18007B6C2
0x18007b5ff  cmp     eax, 5
0x18007b602  jbe     loc_18007B6C2
0x18007b608  call    _tlgKeywordOn
0x18007b60d  test    al, al
0x18007b60f  jz      loc_18007B6C2
0x18007b615  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007b61c  call    ?GetCurrentProcessTree@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessTree(void)
0x18007b621  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007b628  mov     [rbp+57h+arg_8], rax
0x18007b62c  call    ?GetCurrentProcessName@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessName(void)
0x18007b631  mov     rcx, gs:58h
0x18007b63a  mov     edx, cs:_tls_index
0x18007b640  mov     [rbp+57h+arg_18], rax
0x18007b644  mov     rax, [rdi+0C0h]
0x18007b64b  mov     [rbp+57h+var_18], rax
0x18007b64f  mov     eax, 10h
0x18007b654  add     rax, [rcx+rdx*8]
0x18007b658  mov     ecx, 10000003h
0x18007b65d  mov     [rbp+57h+var_28], rax
0x18007b661  mov     [rbp+57h+var_20], 2000000h
0x18007b669  mov     byte ptr [rbp+57h+arg_10], 1
0x18007b66d  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18007b673  mov     [rbp+57h+var_30], rax
0x18007b677  lea     rdx, byte_1800A98A7
0x18007b67e  lea     rax, [rbp+57h+arg_8]
0x18007b682  mov     [rsp+0B0h+var_60], rax
0x18007b687  lea     rax, [rbp+57h+arg_18]
0x18007b68b  mov     [rsp+0B0h+var_68], rax
0x18007b690  lea     rax, [rbp+57h+var_18]
0x18007b694  mov     [rsp+0B0h+var_70], rax
0x18007b699  lea     rax, [rbp+57h+var_20]
0x18007b69d  mov     [rsp+0B0h+var_78], rax
0x18007b6a2  lea     rax, [rbp+57h+arg_10]
0x18007b6a6  mov     [rsp+0B0h+var_80], rax
0x18007b6ab  lea     rax, [rbp+57h+var_28]
0x18007b6af  mov     [rsp+0B0h+var_88], rax
0x18007b6b4  lea     rax, [rbp+57h+var_30]
0x18007b6b8  mov     [rsp+0B0h+var_90], rax
0x18007b6bd  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@D@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@D@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18007b6c2  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007b6c9  lea     rdx, aJscriptsetscri; "JScriptSetScriptStateStarted"
0x18007b6d0  call    ?WriteLoggingLocalTickCount@RegistryBasedThrottle@@QEAAJPEBD@Z; RegistryBasedThrottle::WriteLoggingLocalTickCount(char const *)
0x18007b6d5  mov     cs:?s_fAlreadyLoggedTelemetryOnScriptStateStarted@COleScript@@0HA, 1; int COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted
0x18007b6df  add     rsp, 0A0h
0x18007b6e6  pop     rdi
0x18007b6e7  pop     rbx
0x18007b6e8  pop     rbp
0x18007b6e9  retn
```
