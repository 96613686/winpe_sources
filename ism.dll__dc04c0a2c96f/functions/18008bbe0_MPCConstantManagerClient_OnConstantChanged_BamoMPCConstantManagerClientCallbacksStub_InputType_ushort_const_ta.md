# MPCConstantManagerClient::OnConstantChanged(BamoMPCConstantManagerClientCallbacksStub *,InputType,ushort const *,tagPROPVARIANT const &,tagPROPVARIANT const &)

- ea: `0x18008bbe0`
- end: `0x18008bdb5`
- name: `?OnConstantChanged@MPCConstantManagerClient@@QEAAJPEAVBamoMPCConstantManagerClientCallbacksStub@@W4InputType@@PEBGAEBUtagPROPVARIANT@@3@Z`
- size: `469`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801853f0`

## callees

- `0x18003b53c`
- `0x18004e910`
- `0x180069f90`
- `0x18008bbe0`
- `0x18008c934`
- `0x18008dcac`
- `0x1800fc5cc`
- `0x180174a84`
- `0x18017bb2c`
- `0x18017bd48`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008bd2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008bd2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008bd10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008bd10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008bd9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008bd9d`

## string_xrefs

- `0x18008bc3d`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008bc85`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008bce5`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`
- `0x18008bd73`: `onecoreuap\windows\moderncore\inputv2\inputhost\components\mpcmanager\lib\mpcconstantmanagerclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 MPCConstantManagerClient::OnConstantChanged(RTL_SRWLOCK *a1, __int64 a2, int a3, ...)
{
  int v5; // eax
  int v6; // eax
  struct Windows::Foundation::IPropertyValue *v7; // rax
  struct Windows::Foundation::IPropertyValue *v8; // rax
  const char *v9; // r9
  RTL_SRWLOCK *v10; // rsi
  int v11; // edi
  RTL_SRWLOCK *v12; // rbx
  __int64 v13; // rbx
  int v15; // [rsp+20h] [rbp-50h]
  int v16; // [rsp+20h] [rbp-50h]
  struct Windows::Foundation::IPropertyValue *v17; // [rsp+30h] [rbp-40h] BYREF
  struct Windows::Foundation::IPropertyValue *v18; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string[2]; // [rsp+40h] [rbp-30h] BYREF
  int v20[2]; // [rsp+50h] [rbp-20h] BYREF
  struct Windows::Foundation::IPropertyValue **v21; // [rsp+58h] [rbp-18h]
  struct Windows::Foundation::IPropertyValue *v22; // [rsp+60h] [rbp-10h] BYREF
  RTL_SRWLOCK *v23; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  __int64 v25; // [rsp+98h] [rbp+28h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+38h] BYREF
  va_list va; // [rsp+A8h] [rbp+38h]
  PROPVARIANT *propvarIn; // [rsp+B0h] [rbp+40h]
  PROPVARIANT *v29; // [rsp+B8h] [rbp+48h]
  va_list va1; // [rsp+C0h] [rbp+50h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v26 = va_arg(va1, _QWORD);
  propvarIn = va_arg(va1, PROPVARIANT *);
  v29 = va_arg(va1, PROPVARIANT *);
  v25 = a2;
  string[0] = 0;
  Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(string, (__int64 *)va);
  v17 = 0;
  v18 = 0;
  v5 = MPCConstantManagerClient::CreatePropertyValueFromPROPVARIANT(propvarIn, &v18);
  if ( v5 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
      (const char *)(unsigned int)v5,
      v15);
  v17 = 0;
  v6 = MPCConstantManagerClient::CreatePropertyValueFromPROPVARIANT(v29, &v17);
  if ( v6 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xE2,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
      (const char *)(unsigned int)v6,
      v15);
  v7 = v17;
  v17 = 0;
  *(_QWORD *)v20 = v7;
  v8 = v18;
  v18 = 0;
  v22 = v8;
  LODWORD(v25) = a3;
  Microsoft::WRL::Details::Make<Windows::Internal::Input::MPCManager::ConstantChangedEventArgs,enum Windows::Internal::Input::MPCManager::InputType,Microsoft::WRL::Wrappers::HString,Windows::Foundation::IPropertyValue *,Windows::Foundation::IPropertyValue *>(
    (unsigned int)&v23,
    (unsigned int)&v25,
    (unsigned int)string,
    (unsigned int)&v22,
    (__int64)v20);
  if ( !v23 )
    wil::details::in1diag3::_FailFast_NullAlloc(
      retaddr,
      (void *)0xEA,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
      v9);
  v10 = a1 + 15;
  v22 = (struct Windows::Foundation::IPropertyValue *)v23;
  v23 = a1;
  v11 = 0;
  v25 = 0;
  v12 = a1 + 16;
  AcquireSRWLockExclusive(v12);
  Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(&v25, v10);
  if ( v12 )
    ReleaseSRWLockExclusive(v12);
  v13 = v25;
  if ( v25 )
  {
    *(_QWORD *)v20 = &v23;
    v21 = &v22;
    v11 = Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_2994a7a20cb592567dc6818203d49b13_,Windows::Foundation::ITypedEventHandler<Windows::Internal::Input::MPCManager::MPCConstantManagerClient *,Windows::Internal::Input::MPCManager::ConstantChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
            v20,
            v25,
            v10);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v13);
  }
  if ( v11 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecoreuap\\windows\\moderncore\\inputv2\\inputhost\\components\\mpcmanager\\lib\\mpcconstantmanagerclient.cpp",
      (const char *)(unsigned int)v11,
      v16);
  wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&v17);
  wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(&v18);
  WindowsDeleteString(string[0]);
  return 0;
}

```

## disassembly

```asm
0x18008bbe0  mov     [rsp-18h+arg_0], rbx
0x18008bbe5  mov     [rsp-18h+arg_18], r9
0x18008bbea  mov     [rsp-18h+arg_8], rdx
0x18008bbef  push    rbp
0x18008bbf0  push    rsi
0x18008bbf1  push    rdi
0x18008bbf2  mov     rbp, rsp
0x18008bbf5  sub     rsp, 70h
0x18008bbf9  mov     edi, r8d
0x18008bbfc  mov     rbx, rcx
0x18008bbff  mov     [rbp+string], 0
0x18008bc07  lea     rdx, [rbp+arg_18]
0x18008bc0b  lea     rcx, [rbp+string]
0x18008bc0f  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18008bc14  nop
0x18008bc15  mov     [rbp+var_40], 0
0x18008bc1d  mov     [rbp+var_38], 0
0x18008bc25  lea     rdx, [rbp+var_38]; struct Windows::Foundation::IPropertyValue **
0x18008bc29  mov     rcx, [rbp+propvarIn]; propvarIn
0x18008bc2d  call    ?CreatePropertyValueFromPROPVARIANT@MPCConstantManagerClient@@CAJAEBUtagPROPVARIANT@@PEAPEAUIPropertyValue@Foundation@Windows@@@Z; MPCConstantManagerClient::CreatePropertyValueFromPROPVARIANT(tagPROPVARIANT const &,Windows::Foundation::IPropertyValue * *)
0x18008bc32  mov     rcx, [rbp+18h]; this
0x18008bc36  test    eax, eax
0x18008bc38  jns     short loc_18008BC4F
0x18008bc3a  mov     r9d, eax; char *
0x18008bc3d  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008bc44  mov     edx, 0E1h; void *
0x18008bc49  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008bc4f  mov     rcx, [rbp+var_40]
0x18008bc53  mov     [rbp+var_40], 0
0x18008bc5b  test    rcx, rcx
0x18008bc5e  jz      short loc_18008BC6D
0x18008bc60  mov     rax, [rcx]
0x18008bc63  mov     rax, [rax+10h]
0x18008bc67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bc6c  nop
0x18008bc6d  lea     rdx, [rbp+var_40]; struct Windows::Foundation::IPropertyValue **
0x18008bc71  mov     rcx, [rbp+arg_28]; propvarIn
0x18008bc75  call    ?CreatePropertyValueFromPROPVARIANT@MPCConstantManagerClient@@CAJAEBUtagPROPVARIANT@@PEAPEAUIPropertyValue@Foundation@Windows@@@Z; MPCConstantManagerClient::CreatePropertyValueFromPROPVARIANT(tagPROPVARIANT const &,Windows::Foundation::IPropertyValue * *)
0x18008bc7a  mov     rcx, [rbp+18h]; this
0x18008bc7e  test    eax, eax
0x18008bc80  jns     short loc_18008BC97
0x18008bc82  mov     r9d, eax; char *
0x18008bc85  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008bc8c  mov     edx, 0E2h; void *
0x18008bc91  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008bc97  mov     rax, [rbp+var_40]
0x18008bc9b  mov     [rbp+var_40], 0
0x18008bca3  mov     qword ptr [rbp+var_20], rax
0x18008bca7  mov     rax, [rbp+var_38]
0x18008bcab  mov     [rbp+var_38], 0
0x18008bcb3  mov     [rbp+var_10], rax
0x18008bcb7  mov     dword ptr [rbp+arg_8], edi
0x18008bcba  lea     rax, [rbp+var_20]
0x18008bcbe  mov     qword ptr [rsp+70h+var_50], rax; int
0x18008bcc3  lea     r9, [rbp+var_10]
0x18008bcc7  lea     r8, [rbp+string]
0x18008bccb  lea     rdx, [rbp+arg_8]
0x18008bccf  lea     rcx, [rbp+var_8]
0x18008bcd3  call    ??$Make@VConstantChangedEventArgs@MPCManager@Input@Internal@Windows@@W4InputType@2345@VHString@Wrappers@WRL@Microsoft@@PEAUIPropertyValue@Foundation@5@PEAUIPropertyValue@Foundation@5@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VConstantChangedEventArgs@MPCManager@Input@Internal@Windows@@@12@$$QEAW4InputType@MPCManager@Input@Internal@Windows@@$$QEAVHString@Wrappers@12@$$QEAPEAUIPropertyValue@Foundation@8@2@Z; Microsoft::WRL::Details::Make<Windows::Internal::Input::MPCManager::ConstantChangedEventArgs,Windows::Internal::Input::MPCManager::InputType,Microsoft::WRL::Wrappers::HString,Windows::Foundation::IPropertyValue *,Windows::Foundation::IPropertyValue *>(Windows::Internal::Input::MPCManager::InputType &&,Microsoft::WRL::Wrappers::HString &&,Windows::Foundation::IPropertyValue * &&,Windows::Foundation::IPropertyValue * &&)
0x18008bcd8  mov     rcx, [rbp+18h]; this
0x18008bcdc  mov     rax, [rbp+var_8]
0x18008bce0  test    rax, rax
0x18008bce3  jnz     short loc_18008BCF7
0x18008bce5  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008bcec  mov     edx, 0EAh; void *
0x18008bcf1  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x18008bcf7  lea     rsi, [rbx+78h]
0x18008bcfb  mov     [rbp+var_10], rax
0x18008bcff  mov     [rbp+var_8], rbx
0x18008bd03  xor     edi, edi
0x18008bd05  mov     [rbp+arg_8], rdi
0x18008bd09  lea     rbx, [rsi+8]
0x18008bd0d  mov     rcx, rbx; SRWLock
0x18008bd10  call    cs:__imp_AcquireSRWLockExclusive
0x18008bd16  mov     rdx, rsi
0x18008bd19  lea     rcx, [rbp+arg_8]
0x18008bd1d  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> const &)
0x18008bd22  test    rbx, rbx
0x18008bd25  jz      short loc_18008BD30
0x18008bd27  mov     rcx, rbx; SRWLock
0x18008bd2a  call    cs:__imp_ReleaseSRWLockExclusive
0x18008bd30  mov     rbx, [rbp+arg_8]
0x18008bd34  test    rbx, rbx
0x18008bd37  jz      short loc_18008BD68
0x18008bd39  lea     rax, [rbp+var_8]
0x18008bd3d  mov     qword ptr [rbp+var_20], rax
0x18008bd41  lea     rax, [rbp+var_10]
0x18008bd45  mov     [rbp+var_18], rax
0x18008bd49  mov     r8, rsi
0x18008bd4c  mov     rdx, rbx
0x18008bd4f  lea     rcx, [rbp+var_20]
0x18008bd53  call    ??$InvokeDelegates@V_lambda_2994a7a20cb592567dc6818203d49b13_@@U?$ITypedEventHandler@PEAVMPCConstantManagerClient@MPCManager@Input@Internal@Windows@@PEAVConstantChangedEventArgs@2345@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_2994a7a20cb592567dc6818203d49b13_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVMPCConstantManagerClient@MPCManager@Input@Internal@Windows@@PEAVConstantChangedEventArgs@2345@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_2994a7a20cb592567dc6818203d49b13_,Windows::Foundation::ITypedEventHandler<Windows::Internal::Input::MPCManager::MPCConstantManagerClient *,Windows::Internal::Input::MPCManager::ConstantChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_2994a7a20cb592567dc6818203d49b13_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::Input::MPCManager::MPCConstantManagerClient *,Windows::Internal::Input::MPCManager::ConstantChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x18008bd58  mov     edi, eax
0x18008bd5a  test    rbx, rbx
0x18008bd5d  jz      short loc_18008BD68
0x18008bd5f  mov     rcx, rbx
0x18008bd62  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18008bd67  nop
0x18008bd68  mov     rcx, [rbp+18h]; this
0x18008bd6c  test    edi, edi
0x18008bd6e  jns     short loc_18008BD85
0x18008bd70  mov     r9d, edi; char *
0x18008bd73  lea     r8, aOnecoreuapWind_166; "onecoreuap\\windows\\moderncore\\inputv"...
0x18008bd7a  mov     edx, 0ECh; void *
0x18008bd7f  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18008bd85  lea     rcx, [rbp+var_40]
0x18008bd89  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x18008bd8e  nop
0x18008bd8f  lea     rcx, [rbp+var_38]
0x18008bd93  call    ??1?$com_ptr_t@UIMPCInputProviderBase@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>::~com_ptr_t<IMPCInputProviderBase,wil::err_exception_policy>(void)
0x18008bd98  nop
0x18008bd99  mov     rcx, [rbp+string]; string
0x18008bd9d  call    cs:__imp_WindowsDeleteString
0x18008bda3  xor     eax, eax
0x18008bda5  mov     rbx, [rsp+70h+arg_0]
0x18008bdad  add     rsp, 70h
0x18008bdb1  pop     rdi
0x18008bdb2  pop     rsi
0x18008bdb3  pop     rbp
0x18008bdb4  retn
```
