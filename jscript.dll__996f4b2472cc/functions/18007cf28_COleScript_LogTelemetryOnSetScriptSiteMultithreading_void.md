# COleScript::LogTelemetryOnSetScriptSiteMultithreading(void)

- ea: `0x18007cf28`
- end: `0x18007d062`
- name: `?LogTelemetryOnSetScriptSiteMultithreading@COleScript@@QEAAXXZ`
- size: `314`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800525d0`

## callees

- `0x180001008`
- `0x180052a8c`
- `0x18007cf28`
- `0x18008bb4c`
- `0x18008bcd0`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18007cf6a`
- `KERNEL32!GetTickCount64` at `0x18007cf6a`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007cfe4`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007cfe4`

## string_xrefs

- `0x18007cf50`: `JScriptSetScriptSiteMultithread`

## pseudocode

```c
void __fastcall COleScript::LogTelemetryOnSetScriptSiteMultithreading(COleScript *this)
{
  RegistryBasedThrottle *v2; // rdi
  __int64 v3; // rbx
  _QWORD *ThreadLocalStoragePointer; // rax
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // [rsp+50h] [rbp-28h] BYREF
  __int64 v9[4]; // [rsp+58h] [rbp-20h] BYREF
  char v10; // [rsp+88h] [rbp+10h] BYREF
  __int64 v11; // [rsp+90h] [rbp+18h] BYREF
  __int64 v12; // [rsp+98h] [rbp+20h] BYREF

  if ( !COleScript::s_fAlreadyLoggedTelemetryOnSetScriptSiteMultithreading )
  {
    if ( (v2 = g_pTraceLoggingClient, !*((_DWORD *)g_pTraceLoggingClient + 76))
      && (int)RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(
                (BYTE *)g_pTraceLoggingClient,
                "JScriptSetScriptSiteMultithread") < 0
      || (v3 = *((_QWORD *)v2 + 37), GetTickCount64() - v3 > *((_QWORD *)v2 + 3)) )
    {
      if ( (unsigned int)dword_1800B5D60 > 5 )
      {
        if ( (unsigned __int8)tlgKeywordOn() )
        {
          v11 = *((_QWORD *)this + 24);
          ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
          v12 = 0x2000000;
          v10 = 1;
          v8 = ThreadLocalStoragePointer[tls_index] + 16LL;
          v9[0] = IEConfiguration_GetCLSID(268435459);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(
            v5,
            (unsigned int)byte_1800AB771,
            v6,
            v7,
            (__int64)v9,
            (__int64)&v8,
            (__int64)&v10,
            (__int64)&v12,
            (__int64)&v11);
        }
      }
      RegistryBasedThrottle::WriteLoggingLocalTickCount(g_pTraceLoggingClient, "JScriptSetScriptStateStarted");
      COleScript::s_fAlreadyLoggedTelemetryOnSetScriptSiteMultithreading = 1;
    }
  }
}

```

## disassembly

```asm
0x18007cf28  push    rbx
0x18007cf2a  push    rsi
0x18007cf2b  push    rdi
0x18007cf2c  sub     rsp, 60h
0x18007cf30  cmp     cs:?s_fAlreadyLoggedTelemetryOnSetScriptSiteMultithreading@COleScript@@0HA, 0; int COleScript::s_fAlreadyLoggedTelemetryOnSetScriptSiteMultithreading
0x18007cf37  mov     rsi, rcx
0x18007cf3a  jnz     loc_18007D059
0x18007cf40  mov     rdi, cs:g_pTraceLoggingClient
0x18007cf47  cmp     dword ptr [rdi+130h], 0
0x18007cf4e  jnz     short loc_18007CF63
0x18007cf50  lea     rdx, aJscriptsetscri_0; "JScriptSetScriptSiteMultithread"
0x18007cf57  mov     rcx, rdi; this
0x18007cf5a  call    ?ReadLoggedLocalTickCountFromRegistry@RegistryBasedThrottle@@AEAAJPEBD@Z; RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(char const *)
0x18007cf5f  test    eax, eax
0x18007cf61  js      short loc_18007CF83
0x18007cf63  mov     rbx, [rdi+128h]
0x18007cf6a  call    cs:__imp_GetTickCount64
0x18007cf71  nop     dword ptr [rax+rax+00h]
0x18007cf76  sub     rax, rbx
0x18007cf79  cmp     rax, [rdi+18h]
0x18007cf7d  jbe     loc_18007D059
0x18007cf83  mov     eax, cs:dword_1800B5D60
0x18007cf89  cmp     eax, 5
0x18007cf8c  jbe     loc_18007D03C
0x18007cf92  call    _tlgKeywordOn
0x18007cf97  test    al, al
0x18007cf99  jz      loc_18007D03C
0x18007cf9f  mov     rax, [rsi+0C0h]
0x18007cfa6  mov     edx, cs:_tls_index
0x18007cfac  mov     [rsp+78h+arg_10], rax
0x18007cfb4  mov     rax, gs:58h
0x18007cfbd  mov     ecx, 10h
0x18007cfc2  mov     [rsp+78h+arg_18], 2000000h
0x18007cfce  mov     [rsp+78h+arg_8], 1
0x18007cfd6  add     rcx, [rax+rdx*8]
0x18007cfda  mov     [rsp+78h+var_28], rcx
0x18007cfdf  mov     ecx, 10000003h
0x18007cfe4  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18007cfeb  nop     dword ptr [rax+rax+00h]
0x18007cff0  mov     [rsp+78h+var_20], rax
0x18007cff5  lea     rdx, byte_1800AB771
0x18007cffc  lea     rax, [rsp+78h+arg_10]
0x18007d004  mov     [rsp+78h+var_38], rax
0x18007d009  lea     rax, [rsp+78h+arg_18]
0x18007d011  mov     [rsp+78h+var_40], rax
0x18007d016  lea     rax, [rsp+78h+arg_8]
0x18007d01e  mov     [rsp+78h+var_48], rax
0x18007d023  lea     rax, [rsp+78h+var_28]
0x18007d028  mov     [rsp+78h+var_50], rax
0x18007d02d  lea     rax, [rsp+78h+var_20]
0x18007d032  mov     [rsp+78h+var_58], rax
0x18007d037  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x18007d03c  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007d043  lea     rdx, aJscriptsetscri; "JScriptSetScriptStateStarted"
0x18007d04a  call    ?WriteLoggingLocalTickCount@RegistryBasedThrottle@@QEAAJPEBD@Z; RegistryBasedThrottle::WriteLoggingLocalTickCount(char const *)
0x18007d04f  mov     cs:?s_fAlreadyLoggedTelemetryOnSetScriptSiteMultithreading@COleScript@@0HA, 1; int COleScript::s_fAlreadyLoggedTelemetryOnSetScriptSiteMultithreading
0x18007d059  add     rsp, 60h
0x18007d05d  pop     rdi
0x18007d05e  pop     rsi
0x18007d05f  pop     rbx
0x18007d060  retn
```
