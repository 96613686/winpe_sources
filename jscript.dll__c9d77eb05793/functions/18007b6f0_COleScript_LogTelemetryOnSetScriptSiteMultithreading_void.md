# COleScript::LogTelemetryOnSetScriptSiteMultithreading(void)

- ea: `0x18007b6f0`
- end: `0x18007b81d`
- name: `?LogTelemetryOnSetScriptSiteMultithreading@COleScript@@QEAAXXZ`
- size: `301`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180051880`

## callees

- `0x180001008`
- `0x180051d1c`
- `0x18007b6f0`
- `0x180089b4c`
- `0x180089ca4`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18007b732`
- `KERNEL32!GetTickCount64` at `0x18007b732`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007b7a6`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007b7a6`

## string_xrefs

- `0x18007b718`: `JScriptSetScriptSiteMultithread`

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
      if ( (unsigned int)dword_1800B3D60 > 5 )
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
            (unsigned int)byte_1800A9779,
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
0x18007b6f0  push    rbx
0x18007b6f2  push    rsi
0x18007b6f3  push    rdi
0x18007b6f4  sub     rsp, 60h
0x18007b6f8  cmp     cs:?s_fAlreadyLoggedTelemetryOnSetScriptSiteMultithreading@COleScript@@0HA, 0; int COleScript::s_fAlreadyLoggedTelemetryOnSetScriptSiteMultithreading
0x18007b6ff  mov     rsi, rcx
0x18007b702  jnz     loc_18007B815
0x18007b708  mov     rdi, cs:g_pTraceLoggingClient
0x18007b70f  cmp     dword ptr [rdi+130h], 0
0x18007b716  jnz     short loc_18007B72B
0x18007b718  lea     rdx, aJscriptsetscri_0; "JScriptSetScriptSiteMultithread"
0x18007b71f  mov     rcx, rdi; this
0x18007b722  call    ?ReadLoggedLocalTickCountFromRegistry@RegistryBasedThrottle@@AEAAJPEBD@Z; RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(char const *)
0x18007b727  test    eax, eax
0x18007b729  js      short loc_18007B745
0x18007b72b  mov     rbx, [rdi+128h]
0x18007b732  call    cs:__imp_GetTickCount64
0x18007b738  sub     rax, rbx
0x18007b73b  cmp     rax, [rdi+18h]
0x18007b73f  jbe     loc_18007B815
0x18007b745  mov     eax, cs:dword_1800B3D60
0x18007b74b  cmp     eax, 5
0x18007b74e  jbe     loc_18007B7F8
0x18007b754  call    _tlgKeywordOn
0x18007b759  test    al, al
0x18007b75b  jz      loc_18007B7F8
0x18007b761  mov     rax, [rsi+0C0h]
0x18007b768  mov     edx, cs:_tls_index
0x18007b76e  mov     [rsp+78h+arg_10], rax
0x18007b776  mov     rax, gs:58h
0x18007b77f  mov     ecx, 10h
0x18007b784  mov     [rsp+78h+arg_18], 2000000h
0x18007b790  mov     [rsp+78h+arg_8], 1
0x18007b798  add     rcx, [rax+rdx*8]
0x18007b79c  mov     [rsp+78h+var_28], rcx
0x18007b7a1  mov     ecx, 10000003h
0x18007b7a6  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18007b7ac  mov     [rsp+78h+var_20], rax
0x18007b7b1  lea     rdx, byte_1800A9779
0x18007b7b8  lea     rax, [rsp+78h+arg_10]
0x18007b7c0  mov     [rsp+78h+var_38], rax
0x18007b7c5  lea     rax, [rsp+78h+arg_18]
0x18007b7cd  mov     [rsp+78h+var_40], rax
0x18007b7d2  lea     rax, [rsp+78h+arg_8]
0x18007b7da  mov     [rsp+78h+var_48], rax
0x18007b7df  lea     rax, [rsp+78h+var_28]
0x18007b7e4  mov     [rsp+78h+var_50], rax
0x18007b7e9  lea     rax, [rsp+78h+var_20]
0x18007b7ee  mov     [rsp+78h+var_58], rax
0x18007b7f3  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x18007b7f8  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007b7ff  lea     rdx, aJscriptsetscri; "JScriptSetScriptStateStarted"
0x18007b806  call    ?WriteLoggingLocalTickCount@RegistryBasedThrottle@@QEAAJPEBD@Z; RegistryBasedThrottle::WriteLoggingLocalTickCount(char const *)
0x18007b80b  mov     cs:?s_fAlreadyLoggedTelemetryOnSetScriptSiteMultithreading@COleScript@@0HA, 1; int COleScript::s_fAlreadyLoggedTelemetryOnSetScriptSiteMultithreading
0x18007b815  add     rsp, 60h
0x18007b819  pop     rdi
0x18007b81a  pop     rsi
0x18007b81b  pop     rbx
0x18007b81c  retn
```
