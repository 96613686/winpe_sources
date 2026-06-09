# COleScript::LogTelemetryOnScriptStateStarted(void)

- ea: `0x18007cce0`
- end: `0x18007cf1f`
- name: `?LogTelemetryOnScriptStateStarted@COleScript@@QEAAXXZ`
- size: `575`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180052880`

## callees

- `0x1800010c0`
- `0x180001240`
- `0x18004e110`
- `0x180052a8c`
- `0x18007cce0`
- `0x18007fa70`
- `0x18008ac10`
- `0x18008af00`
- `0x18008b5c0`
- `0x18008bcd0`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007cdbb`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007ce9b`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007cdbb`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007ce9b`

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
      if ( (unsigned int)dword_1800B5D60 > 5 && (unsigned __int8)tlgKeywordOn() )
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
          (unsigned int)byte_1800AB7EB,
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
    else if ( (unsigned int)dword_1800B5D60 > 5 && (unsigned __int8)tlgKeywordOn() )
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
        (unsigned int)&byte_1800AB89F,
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
0x18007cce0  push    rbp
0x18007cce2  push    rbx
0x18007cce3  push    rdi
0x18007cce4  lea     rbp, [rsp-47h]
0x18007cce9  sub     rsp, 0A0h
0x18007ccf0  cmp     cs:?s_fAlreadyLoggedTelemetryOnScriptStateStarted@COleScript@@0HA, 0; int COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted
0x18007ccf7  mov     rdi, rcx
0x18007ccfa  jnz     loc_18007CF13
0x18007cd00  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging> `wil::Feature<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::GetImpl(void)'::`2'::impl
0x18007cd07  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VBScript_Enhanced_Logging>::__private_IsEnabled(void)
0x18007cd0c  test    al, al
0x18007cd0e  mov     eax, cs:dword_1800B5D60
0x18007cd14  jz      loc_18007CE2D
0x18007cd1a  cmp     eax, 5
0x18007cd1d  jbe     loc_18007CEF6
0x18007cd23  call    _tlgKeywordOn
0x18007cd28  test    al, al
0x18007cd2a  jz      loc_18007CEF6
0x18007cd30  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007cd37  mov     rbx, rcx
0x18007cd3a  cmp     dword ptr [rcx+1B68h], 0
0x18007cd41  jnz     short loc_18007CD4F
0x18007cd43  call    ?IdentifyCurrentProcessTreeEnhanced@RegistryBasedThrottle@@AEAAXXZ; RegistryBasedThrottle::IdentifyCurrentProcessTreeEnhanced(void)
0x18007cd48  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007cd4f  mov     rax, [rbx+1B50h]
0x18007cd56  mov     [rbp+57h+arg_10], rax
0x18007cd5a  call    ?GetCurrentCallStack@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentCallStack(void)
0x18007cd5f  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007cd66  mov     [rbp+57h+arg_18], rax
0x18007cd6a  call    ?GetCurrentProcessTree@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessTree(void)
0x18007cd6f  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007cd76  mov     [rbp+57h+var_40], rax
0x18007cd7a  call    ?GetCurrentProcessName@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessName(void)
0x18007cd7f  mov     rcx, gs:58h
0x18007cd88  mov     edx, cs:_tls_index
0x18007cd8e  mov     [rbp+57h+var_38], rax
0x18007cd92  mov     rax, [rdi+0C0h]
0x18007cd99  mov     [rbp+57h+var_30], rax
0x18007cd9d  mov     eax, 10h
0x18007cda2  add     rax, [rcx+rdx*8]
0x18007cda6  mov     ecx, 10000003h
0x18007cdab  mov     [rbp+57h+var_20], rax
0x18007cdaf  mov     [rbp+57h+var_28], 2000000h
0x18007cdb7  mov     byte ptr [rbp+57h+arg_8], 1
0x18007cdbb  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18007cdc2  nop     dword ptr [rax+rax+00h]
0x18007cdc7  mov     [rbp+57h+var_18], rax
0x18007cdcb  lea     rdx, byte_1800AB7EB
0x18007cdd2  lea     rax, [rbp+57h+arg_10]
0x18007cdd6  mov     [rsp+0B0h+var_50], rax
0x18007cddb  lea     rax, [rbp+57h+arg_18]
0x18007cddf  mov     [rsp+0B0h+var_58], rax
0x18007cde4  lea     rax, [rbp+57h+var_40]
0x18007cde8  mov     [rsp+0B0h+var_60], rax
0x18007cded  lea     rax, [rbp+57h+var_38]
0x18007cdf1  mov     [rsp+0B0h+var_68], rax
0x18007cdf6  lea     rax, [rbp+57h+var_30]
0x18007cdfa  mov     [rsp+0B0h+var_70], rax
0x18007cdff  lea     rax, [rbp+57h+var_28]
0x18007ce03  mov     [rsp+0B0h+var_78], rax
0x18007ce08  lea     rax, [rbp+57h+arg_8]
0x18007ce0c  mov     [rsp+0B0h+var_80], rax
0x18007ce11  lea     rax, [rbp+57h+var_20]
0x18007ce15  mov     [rsp+0B0h+var_88], rax
0x18007ce1a  lea     rax, [rbp+57h+var_18]
0x18007ce1e  mov     [rsp+0B0h+var_90], rax
0x18007ce23  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@D@@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@D@@666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18007ce28  jmp     loc_18007CEF6
0x18007ce2d  cmp     eax, 5
0x18007ce30  jbe     loc_18007CEF6
0x18007ce36  call    _tlgKeywordOn
0x18007ce3b  test    al, al
0x18007ce3d  jz      loc_18007CEF6
0x18007ce43  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007ce4a  call    ?GetCurrentProcessTree@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessTree(void)
0x18007ce4f  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007ce56  mov     [rbp+57h+arg_8], rax
0x18007ce5a  call    ?GetCurrentProcessName@RegistryBasedThrottle@@QEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessName(void)
0x18007ce5f  mov     rcx, gs:58h
0x18007ce68  mov     edx, cs:_tls_index
0x18007ce6e  mov     [rbp+57h+arg_18], rax
0x18007ce72  mov     rax, [rdi+0C0h]
0x18007ce79  mov     [rbp+57h+var_18], rax
0x18007ce7d  mov     eax, 10h
0x18007ce82  add     rax, [rcx+rdx*8]
0x18007ce86  mov     ecx, 10000003h
0x18007ce8b  mov     [rbp+57h+var_28], rax
0x18007ce8f  mov     [rbp+57h+var_20], 2000000h
0x18007ce97  mov     byte ptr [rbp+57h+arg_10], 1
0x18007ce9b  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18007cea2  nop     dword ptr [rax+rax+00h]
0x18007cea7  mov     [rbp+57h+var_30], rax
0x18007ceab  lea     rdx, byte_1800AB89F
0x18007ceb2  lea     rax, [rbp+57h+arg_8]
0x18007ceb6  mov     [rsp+0B0h+var_60], rax
0x18007cebb  lea     rax, [rbp+57h+arg_18]
0x18007cebf  mov     [rsp+0B0h+var_68], rax
0x18007cec4  lea     rax, [rbp+57h+var_18]
0x18007cec8  mov     [rsp+0B0h+var_70], rax
0x18007cecd  lea     rax, [rbp+57h+var_20]
0x18007ced1  mov     [rsp+0B0h+var_78], rax
0x18007ced6  lea     rax, [rbp+57h+arg_10]
0x18007ceda  mov     [rsp+0B0h+var_80], rax
0x18007cedf  lea     rax, [rbp+57h+var_28]
0x18007cee3  mov     [rsp+0B0h+var_88], rax
0x18007cee8  lea     rax, [rbp+57h+var_30]
0x18007ceec  mov     [rsp+0B0h+var_90], rax
0x18007cef1  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@D@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@D@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18007cef6  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007cefd  lea     rdx, aJscriptsetscri; "JScriptSetScriptStateStarted"
0x18007cf04  call    ?WriteLoggingLocalTickCount@RegistryBasedThrottle@@QEAAJPEBD@Z; RegistryBasedThrottle::WriteLoggingLocalTickCount(char const *)
0x18007cf09  mov     cs:?s_fAlreadyLoggedTelemetryOnScriptStateStarted@COleScript@@0HA, 1; int COleScript::s_fAlreadyLoggedTelemetryOnScriptStateStarted
0x18007cf13  add     rsp, 0A0h
0x18007cf1a  pop     rdi
0x18007cf1b  pop     rbx
0x18007cf1c  pop     rbp
0x18007cf1d  retn
```
