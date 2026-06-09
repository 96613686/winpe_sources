# CServiceCallback::GetCommercialId(ushort * *)

- ea: `0x18000ce20`
- end: `0x18000cf4f`
- name: `?GetCommercialId@CServiceCallback@@EEBAJPEAPEAG@Z`
- size: `303`
- prototype: `__int64 __fastcall(CServiceCallback *this, unsigned __int16 **, __int64, const char *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001ba0`
- `0x18000296c`
- `0x180005964`
- `0x1800080fc`
- `0x18000ce20`
- `0x18000d020`
- `0x18000d28c`

## string_xrefs

- `0x18000cf0a`: `onecore\enduser\deliveryoptimization\servicecallback\servicecallback.cpp`

## pseudocode

```c
__int64 __fastcall CServiceCallback::GetCommercialId(
        CServiceCallback *this,
        unsigned __int16 **a2,
        __int64 a3,
        const char *a4)
{
  bool v5; // zf
  unsigned int v6; // edx
  int PersistedLocation; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  unsigned __int16 *v11; // r9
  int v12; // edi
  unsigned int v13; // edx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned __int16 *v17; // r9
  int v19; // [rsp+20h] [rbp-248h]
  unsigned __int16 *v20; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int16 v21[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v5 = `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::AlreadyRetrieved == 0;
  *a2 = 0;
  if ( v5 )
  {
    memset_0(v21, 0, 0x208u);
    PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(
                          v21,
                          v6,
                          L"DataCollectionGroupPolicy",
                          L"Software\\Policies\\Microsoft\\Windows\\DataCollection",
                          v19);
    v11 = v21;
    v12 = PersistedLocation;
    if ( PersistedLocation < 0 )
      v11 = L"Software\\Policies\\Microsoft\\Windows\\DataCollection";
    Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(v9, v8, v10, v11);
    if ( !`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId )
    {
      Windows::Compat::Shared::Registry::GetPersistedLocation(
        v21,
        v13,
        L"Diagnostics_AllowTelemetry",
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\DataCollection",
        v19);
      v17 = v21;
      if ( v12 < 0 )
        v17 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\DataCollection";
      Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(v15, v14, v16, v17);
    }
    `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::AlreadyRetrieved = 1;
  }
  if ( !`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId )
    return 2147943568LL;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v20,
    (char *)&`Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId'::`2'::CommercialId,
    0xFFFFFFFFFFFFFFFFuLL,
    a4);
  if ( v20 )
  {
    *a2 = v20;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E,
      (unsigned int)"onecore\\enduser\\deliveryoptimization\\servicecallback\\servicecallback.cpp",
      (const char *)0x8007000ELL,
      v19);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18000ce20  mov     [rsp+arg_0], rbx
0x18000ce25  mov     [rsp+arg_10], rsi
0x18000ce2a  push    rdi
0x18000ce2b  sub     rsp, 260h
0x18000ce32  mov     rax, cs:__security_cookie
0x18000ce39  xor     rax, rsp
0x18000ce3c  mov     [rsp+268h+var_18], rax
0x18000ce44  xor     esi, esi
0x18000ce46  mov     rbx, rdx
0x18000ce49  cmp     cs:?AlreadyRetrieved@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4_NA, sil; bool `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::AlreadyRetrieved
0x18000ce50  mov     [rdx], rsi
0x18000ce53  jnz     short loc_18000CED3
0x18000ce55  xor     edx, edx; Val
0x18000ce57  lea     rcx, [rsp+268h+var_228]; void *
0x18000ce5c  mov     r8d, 208h; Size
0x18000ce62  call    memset_0
0x18000ce67  lea     r9, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18000ce6e  lea     r8, aDatacollection; "DataCollectionGroupPolicy"
0x18000ce75  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18000ce7a  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x18000ce7f  lea     r9, [rsp+268h+var_228]
0x18000ce84  mov     edi, eax
0x18000ce86  test    eax, eax
0x18000ce88  jns     short loc_18000CE91
0x18000ce8a  lea     r9, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18000ce91  call    ?ReadString@?$RegistryKeyWrapper@$0?HPPPPPPO@@Shared@Compat@Windows@@SAJPEAG_KPEBG22@Z; Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *)
0x18000ce96  cmp     cs:?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA, si; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x18000ce9d  jnz     short loc_18000CECC
0x18000ce9f  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000cea6  lea     r8, aDiagnosticsAll; "Diagnostics_AllowTelemetry"
0x18000cead  lea     rcx, [rsp+268h+var_228]; unsigned __int16 *
0x18000ceb2  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x18000ceb7  lea     r9, [rsp+268h+var_228]
0x18000cebc  test    edi, edi
0x18000cebe  jns     short loc_18000CEC7
0x18000cec0  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000cec7  call    ?ReadString@?$RegistryKeyWrapper@$0?HPPPPPPO@@Shared@Compat@Windows@@SAJPEAG_KPEBG22@Z; Windows::Compat::Shared::RegistryKeyWrapper<-2147483646>::ReadString(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *)
0x18000cecc  mov     cs:?AlreadyRetrieved@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4_NA, 1; bool `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::AlreadyRetrieved
0x18000ced3  cmp     cs:?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA, si; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x18000ceda  jnz     short loc_18000CEE3
0x18000cedc  mov     eax, 80070490h
0x18000cee1  jmp     short loc_18000CF2A
0x18000cee3  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000cee7  lea     rdx, ?CommercialId@?1??GetCommercialId@TelemetryProvider@Telemetry@Shared@Compat@Windows@@SAPEBGXZ@4PAGA; ushort near * `Windows::Compat::Shared::Telemetry::TelemetryProvider::GetCommercialId(void)'::`2'::CommercialId
0x18000ceee  lea     rcx, [rsp+268h+var_238]
0x18000cef3  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000cef8  mov     rax, [rsp+268h+var_238]
0x18000cefd  test    rax, rax
0x18000cf00  jnz     short loc_18000CF25
0x18000cf02  mov     rcx, [rsp+268h]; this
0x18000cf0a  lea     r8, aOnecoreEnduser; "onecore\\enduser\\deliveryoptimization"...
0x18000cf11  mov     ebx, 8007000Eh
0x18000cf16  lea     edx, [rax+6Eh]; void *
0x18000cf19  mov     r9d, ebx; char *
0x18000cf1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cf21  mov     eax, ebx
0x18000cf23  jmp     short loc_18000CF2A
0x18000cf25  mov     [rbx], rax
0x18000cf28  xor     eax, eax
0x18000cf2a  mov     rcx, [rsp+268h+var_18]
0x18000cf32  xor     rcx, rsp; StackCookie
0x18000cf35  call    __security_check_cookie
0x18000cf3a  lea     r11, [rsp+268h+var_8]
0x18000cf42  mov     rbx, [r11+10h]
0x18000cf46  mov     rsi, [r11+20h]
0x18000cf4a  mov     rsp, r11
0x18000cf4d  pop     rdi
0x18000cf4e  retn
```
