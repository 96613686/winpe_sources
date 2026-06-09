# COleScript::LogTelemetryOnCloneMultithreading(void)

- ea: `0x18007ca60`
- end: `0x18007cb9a`
- name: `?LogTelemetryOnCloneMultithreading@COleScript@@QEAAXXZ`
- size: `314`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180078e20`

## callees

- `0x180001008`
- `0x180052a8c`
- `0x18007ca60`
- `0x18008bb4c`
- `0x18008bcd0`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18007caa2`
- `KERNEL32!GetTickCount64` at `0x18007caa2`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007cb1c`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007cb1c`

## string_xrefs

- `0x18007ca88`: `JScriptCloneMultithread`
- `0x18007cb7b`: `JScriptCloneMultithread`

## pseudocode

```c
void __fastcall COleScript::LogTelemetryOnCloneMultithreading(COleScript *this)
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

  if ( !COleScript::s_fAlreadyLoggedTelemetryOnCloneMultithreading )
  {
    if ( (v2 = g_pTraceLoggingClient, !*((_DWORD *)g_pTraceLoggingClient + 76))
      && (int)RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(
                (BYTE *)g_pTraceLoggingClient,
                "JScriptCloneMultithread") < 0
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
            (unsigned int)byte_1800AB9A5,
            v6,
            v7,
            (__int64)v9,
            (__int64)&v8,
            (__int64)&v10,
            (__int64)&v12,
            (__int64)&v11);
        }
      }
      RegistryBasedThrottle::WriteLoggingLocalTickCount(g_pTraceLoggingClient, "JScriptCloneMultithread");
      COleScript::s_fAlreadyLoggedTelemetryOnCloneMultithreading = 1;
    }
  }
}

```

## disassembly

```asm
0x18007ca60  push    rbx
0x18007ca62  push    rsi
0x18007ca63  push    rdi
0x18007ca64  sub     rsp, 60h
0x18007ca68  cmp     cs:?s_fAlreadyLoggedTelemetryOnCloneMultithreading@COleScript@@0HA, 0; int COleScript::s_fAlreadyLoggedTelemetryOnCloneMultithreading
0x18007ca6f  mov     rsi, rcx
0x18007ca72  jnz     loc_18007CB91
0x18007ca78  mov     rdi, cs:g_pTraceLoggingClient
0x18007ca7f  cmp     dword ptr [rdi+130h], 0
0x18007ca86  jnz     short loc_18007CA9B
0x18007ca88  lea     rdx, aJscriptclonemu; "JScriptCloneMultithread"
0x18007ca8f  mov     rcx, rdi; this
0x18007ca92  call    ?ReadLoggedLocalTickCountFromRegistry@RegistryBasedThrottle@@AEAAJPEBD@Z; RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(char const *)
0x18007ca97  test    eax, eax
0x18007ca99  js      short loc_18007CABB
0x18007ca9b  mov     rbx, [rdi+128h]
0x18007caa2  call    cs:__imp_GetTickCount64
0x18007caa9  nop     dword ptr [rax+rax+00h]
0x18007caae  sub     rax, rbx
0x18007cab1  cmp     rax, [rdi+18h]
0x18007cab5  jbe     loc_18007CB91
0x18007cabb  mov     eax, cs:dword_1800B5D60
0x18007cac1  cmp     eax, 5
0x18007cac4  jbe     loc_18007CB74
0x18007caca  call    _tlgKeywordOn
0x18007cacf  test    al, al
0x18007cad1  jz      loc_18007CB74
0x18007cad7  mov     rax, [rsi+0C0h]
0x18007cade  mov     edx, cs:_tls_index
0x18007cae4  mov     [rsp+78h+arg_10], rax
0x18007caec  mov     rax, gs:58h
0x18007caf5  mov     ecx, 10h
0x18007cafa  mov     [rsp+78h+arg_18], 2000000h
0x18007cb06  mov     [rsp+78h+arg_8], 1
0x18007cb0e  add     rcx, [rax+rdx*8]
0x18007cb12  mov     [rsp+78h+var_28], rcx
0x18007cb17  mov     ecx, 10000003h
0x18007cb1c  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18007cb23  nop     dword ptr [rax+rax+00h]
0x18007cb28  mov     [rsp+78h+var_20], rax
0x18007cb2d  lea     rdx, byte_1800AB9A5
0x18007cb34  lea     rax, [rsp+78h+arg_10]
0x18007cb3c  mov     [rsp+78h+var_38], rax
0x18007cb41  lea     rax, [rsp+78h+arg_18]
0x18007cb49  mov     [rsp+78h+var_40], rax
0x18007cb4e  lea     rax, [rsp+78h+arg_8]
0x18007cb56  mov     [rsp+78h+var_48], rax
0x18007cb5b  lea     rax, [rsp+78h+var_28]
0x18007cb60  mov     [rsp+78h+var_50], rax
0x18007cb65  lea     rax, [rsp+78h+var_20]
0x18007cb6a  mov     [rsp+78h+var_58], rax
0x18007cb6f  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x18007cb74  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007cb7b  lea     rdx, aJscriptclonemu; "JScriptCloneMultithread"
0x18007cb82  call    ?WriteLoggingLocalTickCount@RegistryBasedThrottle@@QEAAJPEBD@Z; RegistryBasedThrottle::WriteLoggingLocalTickCount(char const *)
0x18007cb87  mov     cs:?s_fAlreadyLoggedTelemetryOnCloneMultithreading@COleScript@@0HA, 1; int COleScript::s_fAlreadyLoggedTelemetryOnCloneMultithreading
0x18007cb91  add     rsp, 60h
0x18007cb95  pop     rdi
0x18007cb96  pop     rsi
0x18007cb97  pop     rbx
0x18007cb98  retn
```
