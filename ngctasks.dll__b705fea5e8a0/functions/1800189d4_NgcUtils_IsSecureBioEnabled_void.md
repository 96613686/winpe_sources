# NgcUtils::IsSecureBioEnabled(void)

- ea: `0x1800189d4`
- end: `0x180018be3`
- name: `?IsSecureBioEnabled@NgcUtils@@YA_NXZ`
- size: `527`
- prototype: `bool __fastcall(NgcUtils *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800106ac`

## callees

- `0x1800012cc`
- `0x180006330`
- `0x18000ebc0`
- `0x180017868`
- `0x1800180d4`
- `0x180018944`
- `0x1800189d4`
- `0x18001a014`
- `0x18001aa20`
- `0x18001ab24`
- `0x18001db3c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180018b30`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180018b4c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180018b30`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180018b4c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018af1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018af1`
- `ntdll!NtQuerySystemInformation` at `0x180018a71`
- `ntdll!NtQuerySystemInformation` at `0x180018a71`
- `tbs!Tbsi_GetDeviceInfo` at `0x1800189fb`
- `tbs!Tbsi_GetDeviceInfo` at `0x1800189fb`

## string_xrefs

- `0x180018a0c`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x180018a82`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`
- `0x180018ab8`: `onecore\ds\security\ngc\utils\bio\lib\securebioutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
      (int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)(unsigned int)DeviceInfo);
  if ( DWORD1(v12) < 2 )
  {
    if ( (unsigned int)dword_180031038 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180031038,
        (__int64)byte_180029B13);
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
    if ( (unsigned int)dword_180031038 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180031038,
        (__int64)word_180029AEA);
    return 0;
  }
  v9[0] = 0;
  v4 = NgcUtils::CoInitializer::Initialize((NgcUtils::CoInitializer *)v9, v3);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x19D,
      (int)"onecore\\ds\\security\\ngc\\utils\\bio\\lib\\securebioutils.cpp",
      (const char *)(unsigned int)v4);
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
    if ( (unsigned int)dword_180031038 > 4 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180031038,
        (__int64)&byte_180029AB7);
    wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>((__int64 *)&v11);
    goto LABEL_15;
  }
  wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>((__int64 *)&v11);
  if ( v9[0] )
    CoUninitialize();
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
    return 1;
  if ( NgcUtils::IsSDEVTablePresent(v5) || NgcUtils::ExistsSecureFpRegKey(v7) )
    return (unsigned int)NgcUtils::SecureBioRegKeyState() != 0;
  if ( (unsigned int)dword_180031038 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180031038,
      (__int64)&byte_180029A8F);
  return 0;
}

```

## disassembly

```asm
0x1800189d4  push    rbp
0x1800189d6  mov     rbp, rsp
0x1800189d9  sub     rsp, 70h
0x1800189dd  mov     rax, cs:__security_cookie
0x1800189e4  xor     rax, rsp
0x1800189e7  mov     [rbp+var_10], rax
0x1800189eb  xorps   xmm0, xmm0
0x1800189ee  movups  [rbp+var_30], xmm0
0x1800189f2  lea     rdx, [rbp+var_30]
0x1800189f6  mov     ecx, 10h
0x1800189fb  call    cs:__imp_Tbsi_GetDeviceInfo
0x180018a01  mov     rcx, [rbp+8]; this
0x180018a05  test    eax, eax
0x180018a07  jns     short loc_180018A1D
0x180018a09  mov     r9d, eax; char *
0x180018a0c  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180018a13  mov     edx, 17Ch; void *
0x180018a18  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018a1d  cmp     dword ptr [rbp+var_30+4], 2
0x180018a21  jnb     short loc_180018A50
0x180018a23  mov     eax, cs:dword_180031038
0x180018a29  cmp     eax, 4
0x180018a2c  jbe     loc_180018BCF
0x180018a32  xor     r9d, r9d
0x180018a35  xor     r8d, r8d
0x180018a38  lea     rdx, byte_180029B13
0x180018a3f  lea     rcx, dword_180031038
0x180018a46  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180018a4b  jmp     loc_180018BCF
0x180018a50  xorps   xmm0, xmm0
0x180018a53  movups  [rbp+SystemInformation], xmm0
0x180018a57  mov     [rbp+ReturnLength], 0
0x180018a5e  lea     r9, [rbp+ReturnLength]; ReturnLength
0x180018a62  mov     r8d, 10h; SystemInformationLength
0x180018a68  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x180018a6c  mov     ecx, 0A5h; SystemInformationClass
0x180018a71  call    cs:__imp_NtQuerySystemInformation
0x180018a77  mov     rcx, [rbp+8]; this
0x180018a7b  test    eax, eax
0x180018a7d  jns     short loc_180018A93
0x180018a7f  mov     r9d, eax; char *
0x180018a82  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180018a89  mov     edx, 18Dh; void *
0x180018a8e  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x180018a93  mov     al, byte ptr [rbp+SystemInformation]
0x180018a96  and     al, 21h
0x180018a98  cmp     al, 21h ; '!'
0x180018a9a  jnz     loc_180018BAB
0x180018aa0  mov     [rbp+var_40], 0
0x180018aa4  lea     rcx, [rbp+var_40]; this
0x180018aa8  call    ?Initialize@CoInitializer@NgcUtils@@QEAAJK@Z; NgcUtils::CoInitializer::Initialize(ulong)
0x180018aad  mov     rcx, [rbp+8]; this
0x180018ab1  test    eax, eax
0x180018ab3  jns     short loc_180018ACC
0x180018ab5  mov     r9d, eax; char *
0x180018ab8  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\ngc\\utils\\bio"...
0x180018abf  mov     edx, 19Dh; void *
0x180018ac4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018ac9  nop
0x180018aca  jmp     short loc_180018B2A
0x180018acc  mov     [rbp+var_38], 0
0x180018ad4  lea     rax, [rbp+var_38]
0x180018ad8  mov     qword ptr [rsp+70h+ppv], rax; ppv
0x180018add  lea     r9, _GUID_1d14e48f_ff05_4652_af35_ad9f1aad8a00; riid
0x180018ae4  xor     edx, edx; pUnkOuter
0x180018ae6  lea     r8d, [rdx+1]; dwClsContext
0x180018aea  lea     rcx, _GUID_8aa829d6_e867_492a_8ab7_7363e4859ba9; rclsid
0x180018af1  call    cs:__imp_CoCreateInstance
0x180018af7  test    eax, eax
0x180018af9  jns     short loc_180018B3C
0x180018afb  mov     eax, cs:dword_180031038
0x180018b01  cmp     eax, 4
0x180018b04  jbe     short loc_180018B20
0x180018b06  xor     r9d, r9d
0x180018b09  xor     r8d, r8d
0x180018b0c  lea     rdx, byte_180029AB7
0x180018b13  lea     rcx, dword_180031038
0x180018b1a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180018b1f  nop
0x180018b20  lea     rcx, [rbp+var_38]
0x180018b24  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180018b29  nop
0x180018b2a  cmp     [rbp+var_40], 0
0x180018b2e  jz      short loc_180018B37
0x180018b30  call    cs:__imp_CoUninitialize
0x180018b36  nop
0x180018b37  jmp     loc_180018BCF
0x180018b3c  lea     rcx, [rbp+var_38]
0x180018b40  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180018b45  nop
0x180018b46  cmp     [rbp+var_40], 0
0x180018b4a  jz      short loc_180018B53
0x180018b4c  call    cs:__imp_CoUninitialize
0x180018b52  nop
0x180018b53  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180018b5a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x180018b5f  test    al, al
0x180018b61  jz      short loc_180018B67
0x180018b63  mov     al, 1
0x180018b65  jmp     short loc_180018BD1
0x180018b67  call    ?IsSDEVTablePresent@NgcUtils@@YA_NXZ; NgcUtils::IsSDEVTablePresent(void)
0x180018b6c  test    al, al
0x180018b6e  jnz     short loc_180018B9F
0x180018b70  call    ?ExistsSecureFpRegKey@NgcUtils@@YA_NXZ; NgcUtils::ExistsSecureFpRegKey(void)
0x180018b75  test    al, al
0x180018b77  jnz     short loc_180018B9F
0x180018b79  mov     eax, cs:dword_180031038
0x180018b7f  cmp     eax, 4
0x180018b82  jbe     short loc_180018BCF
0x180018b84  xor     r9d, r9d
0x180018b87  xor     r8d, r8d
0x180018b8a  lea     rdx, byte_180029A8F
0x180018b91  lea     rcx, dword_180031038
0x180018b98  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180018b9d  jmp     short loc_180018BCF
0x180018b9f  call    ?SecureBioRegKeyState@NgcUtils@@YA?AW4_NGC_ENABLED_STATE@@XZ; NgcUtils::SecureBioRegKeyState(void)
0x180018ba4  test    eax, eax
0x180018ba6  setnz   al
0x180018ba9  jmp     short loc_180018BD1
0x180018bab  mov     eax, cs:dword_180031038
0x180018bb1  cmp     eax, 4
0x180018bb4  jbe     short loc_180018BCF
0x180018bb6  xor     r9d, r9d
0x180018bb9  xor     r8d, r8d
0x180018bbc  lea     rdx, word_180029AEA
0x180018bc3  lea     rcx, dword_180031038
0x180018bca  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180018bcf  xor     al, al
0x180018bd1  mov     rcx, [rbp+var_10]
0x180018bd5  xor     rcx, rsp; StackCookie
0x180018bd8  call    __security_check_cookie
0x180018bdd  add     rsp, 70h
0x180018be1  pop     rbp
0x180018be2  retn
```
