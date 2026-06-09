# COleScript::LogTelemetryOnCloneMultithreading(void)

- ea: `0x18007b250`
- end: `0x18007b37d`
- name: `?LogTelemetryOnCloneMultithreading@COleScript@@QEAAXXZ`
- size: `301`
- prototype: `void __fastcall(COleScript *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180077820`

## callees

- `0x180001008`
- `0x180051d1c`
- `0x18007b250`
- `0x180089b4c`
- `0x180089ca4`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18007b292`
- `KERNEL32!GetTickCount64` at `0x18007b292`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007b306`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18007b306`

## string_xrefs

- `0x18007b278`: `JScriptCloneMultithread`
- `0x18007b35f`: `JScriptCloneMultithread`

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
            (unsigned int)byte_1800A99AD,
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
0x18007b250  push    rbx
0x18007b252  push    rsi
0x18007b253  push    rdi
0x18007b254  sub     rsp, 60h
0x18007b258  cmp     cs:?s_fAlreadyLoggedTelemetryOnCloneMultithreading@COleScript@@0HA, 0; int COleScript::s_fAlreadyLoggedTelemetryOnCloneMultithreading
0x18007b25f  mov     rsi, rcx
0x18007b262  jnz     loc_18007B375
0x18007b268  mov     rdi, cs:g_pTraceLoggingClient
0x18007b26f  cmp     dword ptr [rdi+130h], 0
0x18007b276  jnz     short loc_18007B28B
0x18007b278  lea     rdx, aJscriptclonemu; "JScriptCloneMultithread"
0x18007b27f  mov     rcx, rdi; this
0x18007b282  call    ?ReadLoggedLocalTickCountFromRegistry@RegistryBasedThrottle@@AEAAJPEBD@Z; RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(char const *)
0x18007b287  test    eax, eax
0x18007b289  js      short loc_18007B2A5
0x18007b28b  mov     rbx, [rdi+128h]
0x18007b292  call    cs:__imp_GetTickCount64
0x18007b298  sub     rax, rbx
0x18007b29b  cmp     rax, [rdi+18h]
0x18007b29f  jbe     loc_18007B375
0x18007b2a5  mov     eax, cs:dword_1800B3D60
0x18007b2ab  cmp     eax, 5
0x18007b2ae  jbe     loc_18007B358
0x18007b2b4  call    _tlgKeywordOn
0x18007b2b9  test    al, al
0x18007b2bb  jz      loc_18007B358
0x18007b2c1  mov     rax, [rsi+0C0h]
0x18007b2c8  mov     edx, cs:_tls_index
0x18007b2ce  mov     [rsp+78h+arg_10], rax
0x18007b2d6  mov     rax, gs:58h
0x18007b2df  mov     ecx, 10h
0x18007b2e4  mov     [rsp+78h+arg_18], 2000000h
0x18007b2f0  mov     [rsp+78h+arg_8], 1
0x18007b2f8  add     rcx, [rax+rdx*8]
0x18007b2fc  mov     [rsp+78h+var_28], rcx
0x18007b301  mov     ecx, 10000003h
0x18007b306  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18007b30c  mov     [rsp+78h+var_20], rax
0x18007b311  lea     rdx, byte_1800A99AD
0x18007b318  lea     rax, [rsp+78h+arg_10]
0x18007b320  mov     [rsp+78h+var_38], rax
0x18007b325  lea     rax, [rsp+78h+arg_18]
0x18007b32d  mov     [rsp+78h+var_40], rax
0x18007b332  lea     rax, [rsp+78h+arg_8]
0x18007b33a  mov     [rsp+78h+var_48], rax
0x18007b33f  lea     rax, [rsp+78h+var_28]
0x18007b344  mov     [rsp+78h+var_50], rax
0x18007b349  lea     rax, [rsp+78h+var_20]
0x18007b34e  mov     [rsp+78h+var_58], rax
0x18007b353  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByRef<16> const &)
0x18007b358  mov     rcx, cs:g_pTraceLoggingClient; this
0x18007b35f  lea     rdx, aJscriptclonemu; "JScriptCloneMultithread"
0x18007b366  call    ?WriteLoggingLocalTickCount@RegistryBasedThrottle@@QEAAJPEBD@Z; RegistryBasedThrottle::WriteLoggingLocalTickCount(char const *)
0x18007b36b  mov     cs:?s_fAlreadyLoggedTelemetryOnCloneMultithreading@COleScript@@0HA, 1; int COleScript::s_fAlreadyLoggedTelemetryOnCloneMultithreading
0x18007b375  add     rsp, 60h
0x18007b379  pop     rdi
0x18007b37a  pop     rsi
0x18007b37b  pop     rbx
0x18007b37c  retn
```
