# NgcUtils::IsSecureBioEnabled(void)

- ea: `0x180022af0`
- end: `0x180022d00`
- name: `?IsSecureBioEnabled@NgcUtils@@YA_NXZ`
- size: `528`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001a52c`

## callees

- `0x1800012e8`
- `0x180004de0`
- `0x18001069c`
- `0x18001d6c8`
- `0x18002255c`
- `0x180022a64`
- `0x180022af0`
- `0x180022de0`
- `0x180022e94`
- `0x180022eb8`
- `0x180023c6c`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180022b8d`
- `ntdll!NtQuerySystemInformation` at `0x180022b8d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022c4f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022c6a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022c4f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022c6a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022c0c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180022c0c`
- `tbs!Tbsi_GetDeviceInfo` at `0x180022b17`
- `tbs!Tbsi_GetDeviceInfo` at `0x180022b17`

## string_xrefs

- `0x180022b28`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x180022b9e`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x180022bd4`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall NgcUtils::IsSecureBioEnabled(NgcUtils *this)
{
  int DeviceInfo; // eax
  NTSTATUS v2; // eax
  unsigned int v3; // edx
  int v4; // eax
  NgcUtils *v5; // rcx
  NgcUtils *v7; // rcx
  int ppv; // [rsp+20h] [rbp-50h]
  _BYTE v9[4]; // [rsp+30h] [rbp-40h] BYREF
  ULONG ReturnLength; // [rsp+34h] [rbp-3Ch] BYREF
  LPVOID v11; // [rsp+38h] [rbp-38h] BYREF
  __int128 v12; // [rsp+40h] [rbp-30h] BYREF
  __int128 SystemInformation; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v12 = 0;
  DeviceInfo = Tbsi_GetDeviceInfo(16, &v12);
  if ( DeviceInfo < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x17C,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)(unsigned int)DeviceInfo,
      ppv);
  if ( DWORD1(v12) < 2 )
  {
    if ( (unsigned int)dword_180037000 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_180037000,
        byte_18002F1B5,
        0,
        0);
    return 0;
  }
  SystemInformation = 0;
  ReturnLength = 0;
  v2 = NtQuerySystemInformation(SystemRegistryQuotaInformation|0x80, &SystemInformation, 0x10u, &ReturnLength);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0x18D,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)(unsigned int)v2,
      ppv);
  if ( (SystemInformation & 0x21) != 0x21 )
  {
    if ( (unsigned int)dword_180037000 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_180037000,
        &dword_18002F18C,
        0,
        0);
    return 0;
  }
  v9[0] = 0;
  v4 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)v9, v3);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19D,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)(unsigned int)v4,
      ppv);
LABEL_15:
    if ( v9[0] )
      CoUninitialize();
    return 0;
  }
  v11 = 0;
  if ( CoCreateInstance(
         &GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9,
         0,
         1u,
         &GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00,
         &v11) < 0 )
  {
    if ( (unsigned int)dword_180037000 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_180037000,
        byte_18002F159,
        0,
        0);
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v11);
    goto LABEL_15;
  }
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v11);
  if ( v9[0] )
    CoUninitialize();
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
    return 1;
  if ( NgcUtils::IsSDEVTablePresent(v5) || NgcUtils::ExistsSecureFpRegKey(v7) )
    return (unsigned int)NgcUtils::SecureBioRegKeyState() != 0;
  if ( (unsigned int)dword_180037000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180037000,
      byte_18002F131,
      0,
      0);
  return 0;
}

```

## disassembly

```asm
0x180022af0  push    rbp
0x180022af2  mov     rbp, rsp
0x180022af5  sub     rsp, 70h
0x180022af9  mov     rax, cs:__security_cookie
0x180022b00  xor     rax, rsp
0x180022b03  mov     [rbp+var_10], rax
0x180022b07  xorps   xmm0, xmm0
0x180022b0a  movups  [rbp+var_30], xmm0
0x180022b0e  lea     rdx, [rbp+var_30]
0x180022b12  mov     ecx, 10h
0x180022b17  call    cs:__imp_Tbsi_GetDeviceInfo
0x180022b1d  mov     rcx, [rbp+8]; this
0x180022b21  test    eax, eax
0x180022b23  jns     short loc_180022B39
0x180022b25  mov     r9d, eax; char *
0x180022b28  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180022b2f  mov     edx, 17Ch; void *
0x180022b34  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022b39  cmp     dword ptr [rbp+var_30+4], 2
0x180022b3d  jnb     short loc_180022B6C
0x180022b3f  mov     eax, cs:dword_180037000
0x180022b45  cmp     eax, 4
0x180022b48  jbe     loc_180022CEC
0x180022b4e  xor     r9d, r9d
0x180022b51  xor     r8d, r8d
0x180022b54  lea     rdx, byte_18002F1B5
0x180022b5b  lea     rcx, dword_180037000
0x180022b62  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180022b67  jmp     loc_180022CEC
0x180022b6c  xorps   xmm0, xmm0
0x180022b6f  movups  [rbp+SystemInformation], xmm0
0x180022b73  mov     [rbp+ReturnLength], 0
0x180022b7a  lea     r9, [rbp+ReturnLength]; ReturnLength
0x180022b7e  mov     r8d, 10h; SystemInformationLength
0x180022b84  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x180022b88  mov     ecx, 0A5h; SystemInformationClass
0x180022b8d  call    cs:__imp_NtQuerySystemInformation
0x180022b93  mov     rcx, [rbp+8]; this
0x180022b97  test    eax, eax
0x180022b99  jns     short loc_180022BAF
0x180022b9b  mov     r9d, eax; char *
0x180022b9e  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180022ba5  mov     edx, 18Dh; void *
0x180022baa  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180022baf  mov     al, byte ptr [rbp+SystemInformation]
0x180022bb2  and     al, 21h
0x180022bb4  cmp     al, 21h ; '!'
0x180022bb6  jnz     loc_180022CC8
0x180022bbc  mov     [rbp+var_40], 0
0x180022bc0  lea     rcx, [rbp+var_40]; this
0x180022bc4  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x180022bc9  mov     rcx, [rbp+8]; this
0x180022bcd  test    eax, eax
0x180022bcf  jns     short loc_180022BE7
0x180022bd1  mov     r9d, eax; char *
0x180022bd4  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180022bdb  mov     edx, 19Dh; void *
0x180022be0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022be5  jmp     short loc_180022C45
0x180022be7  mov     [rbp+var_38], 0
0x180022bef  lea     rax, [rbp+var_38]
0x180022bf3  mov     qword ptr [rsp+70h+ppv], rax; ppv
0x180022bf8  lea     r9, _GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00; riid
0x180022bff  xor     edx, edx; pUnkOuter
0x180022c01  lea     r8d, [rdx+1]; dwClsContext
0x180022c05  lea     rcx, _GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9; rclsid
0x180022c0c  call    cs:__imp_CoCreateInstance
0x180022c12  test    eax, eax
0x180022c14  jns     short loc_180022C5A
0x180022c16  mov     eax, cs:dword_180037000
0x180022c1c  cmp     eax, 4
0x180022c1f  jbe     short loc_180022C3B
0x180022c21  xor     r9d, r9d
0x180022c24  xor     r8d, r8d
0x180022c27  lea     rdx, byte_18002F159
0x180022c2e  lea     rcx, dword_180037000
0x180022c35  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180022c3a  nop
0x180022c3b  lea     rcx, [rbp+var_38]
0x180022c3f  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180022c44  nop
0x180022c45  cmp     [rbp+var_40], 0
0x180022c49  jz      loc_180022CEC
0x180022c4f  call    cs:__imp_CoUninitialize
0x180022c55  jmp     loc_180022CEC
0x180022c5a  lea     rcx, [rbp+var_38]
0x180022c5e  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180022c63  nop
0x180022c64  cmp     [rbp+var_40], 0
0x180022c68  jz      short loc_180022C70
0x180022c6a  call    cs:__imp_CoUninitialize
0x180022c70  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180022c77  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x180022c7c  test    al, al
0x180022c7e  jz      short loc_180022C84
0x180022c80  mov     al, 1
0x180022c82  jmp     short loc_180022CEE
0x180022c84  call    ?IsSDEVTablePresent@NgcUtils@@YA_NXZ; NgcUtils::IsSDEVTablePresent(void)
0x180022c89  test    al, al
0x180022c8b  jnz     short loc_180022CBC
0x180022c8d  call    ?ExistsSecureFpRegKey@NgcUtils@@YA_NXZ; NgcUtils::ExistsSecureFpRegKey(void)
0x180022c92  test    al, al
0x180022c94  jnz     short loc_180022CBC
0x180022c96  mov     eax, cs:dword_180037000
0x180022c9c  cmp     eax, 4
0x180022c9f  jbe     short loc_180022CEC
0x180022ca1  xor     r9d, r9d
0x180022ca4  xor     r8d, r8d
0x180022ca7  lea     rdx, byte_18002F131
0x180022cae  lea     rcx, dword_180037000
0x180022cb5  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180022cba  jmp     short loc_180022CEC
0x180022cbc  call    ?SecureBioRegKeyState@NgcUtils@@YA?AW4_NGC_ENABLED_STATE@@XZ; NgcUtils::SecureBioRegKeyState(void)
0x180022cc1  test    eax, eax
0x180022cc3  setnz   al
0x180022cc6  jmp     short loc_180022CEE
0x180022cc8  mov     eax, cs:dword_180037000
0x180022cce  cmp     eax, 4
0x180022cd1  jbe     short loc_180022CEC
0x180022cd3  xor     r9d, r9d
0x180022cd6  xor     r8d, r8d
0x180022cd9  lea     rdx, dword_18002F18C
0x180022ce0  lea     rcx, dword_180037000
0x180022ce7  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180022cec  xor     al, al
0x180022cee  mov     rcx, [rbp+var_10]
0x180022cf2  xor     rcx, rsp; StackCookie
0x180022cf5  call    __security_check_cookie
0x180022cfa  add     rsp, 70h
0x180022cfe  pop     rbp
0x180022cff  retn
```
