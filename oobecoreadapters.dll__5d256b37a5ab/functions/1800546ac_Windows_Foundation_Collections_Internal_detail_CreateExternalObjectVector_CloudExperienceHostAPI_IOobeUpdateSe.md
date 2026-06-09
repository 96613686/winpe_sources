# Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<CloudExperienceHostAPI::IOobeUpdateSetting,Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeUpdateSetting *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeUpdateSetting *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeUpdateSetting *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeUpdateSetting *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeUpdateSetting *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeUpdateSetting *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeUpdateSetting *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeUpdateSetting *>> * *)

- ea: `0x1800546ac`
- end: `0x180054847`
- name: `??$CreateExternalObjectVector@UIOobeUpdateSetting@CloudExperienceHostAPI@@V?$Vector@PEAUIOobeUpdateSetting@CloudExperienceHostAPI@@U?$DefaultEqualityPredicate@PEAUIOobeUpdateSetting@CloudExperienceHostAPI@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIOobeUpdateSetting@CloudExperienceHostAPI@@@4567@U?$DefaultVectorOptions@PEAUIOobeUpdateSetting@CloudExperienceHostAPI@@@4567@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIOobeUpdateSetting@CloudExperienceHostAPI@@U?$DefaultEqualityPredicate@PEAUIOobeUpdateSetting@CloudExperienceHostAPI@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIOobeUpdateSetting@CloudExperienceHostAPI@@@4567@U?$DefaultVectorOptions@PEAUIOobeUpdateSetting@CloudExperienceHostAPI@@@4567@@1234@@Z`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800558e0`

## callees

- `0x180002b60`
- `0x18000683c`
- `0x180009100`
- `0x18000a4f8`
- `0x180036a74`
- `0x1800546ac`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800547c1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800547c1`

## string_xrefs

- `0x180054708`: `Windows.Foundation.Collections.IIterator`1<CloudExperienceHostAPI.IOobeUpdateSetting>`
- `0x1800546d4`: `Windows.Foundation.Collections.IVector`1<CloudExperienceHostAPI.IOobeUpdateSetting>`
- `0x1800546ee`: `Windows.Foundation.Collections.IVectorView`1<CloudExperienceHostAPI.IOobeUpdateSetting>`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<CloudExperienceHostAPI::IOobeUpdateSetting,Windows::Foundation::Collections::Internal::Vector<CloudExperienceHostAPI::IOobeUpdateSetting *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<CloudExperienceHostAPI::IOobeUpdateSetting *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<CloudExperienceHostAPI::IOobeUpdateSetting *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<CloudExperienceHostAPI::IOobeUpdateSetting *>>>(
        __int64 a1,
        _QWORD *a2)
{
  int ActivationFactory; // ebx
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v7; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v8; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v9[2]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v10[3]; // [rsp+40h] [rbp-C0h] BYREF
  GUID v11; // [rsp+58h] [rbp-A8h]
  GUID v12; // [rsp+68h] [rbp-98h]
  GUID v13; // [rsp+78h] [rbp-88h]
  GUID v14; // [rsp+88h] [rbp-78h]
  GUID v15; // [rsp+98h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v17; // [rsp+C8h] [rbp-38h]
  _BYTE v18[24]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v19; // [rsp+E8h] [rbp-18h]
  _BYTE v20[24]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v21; // [rsp+108h] [rbp+8h]
  _BYTE v22[24]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v23; // [rsp+128h] [rbp+28h]

  v9[0] = L"Windows.Foundation.Collections.IVector`1<CloudExperienceHostAPI.IOobeUpdateSetting>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v18, v9);
  v9[0] = L"Windows.Foundation.Collections.IVectorView`1<CloudExperienceHostAPI.IOobeUpdateSetting>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v20, v9);
  v9[0] = L"Windows.Foundation.Collections.IIterator`1<CloudExperienceHostAPI.IOobeUpdateSetting>";
  Microsoft::WRL::Wrappers::HStringReference::HStringReference(v22, v9);
  v10[0] = v19;
  v10[1] = v21;
  v10[2] = v23;
  v11 = GUID_7282c4e1_bcda_41d7_8e75_53726d5c228f;
  v12 = GUID_36569ad4_6032_5471_9f39_19af988cc7b2;
  v13 = GUID_0ed96c5c_dc7f_5b24_ad64_6034dc6852e9;
  v14 = GUID_8b420f77_1600_5e25_b6ac_d1c2454dbe88;
  v15 = GUID_b97674b4_c069_56fb_bc9a_98ec84ba4a78;
  v8 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.Collections.Detail.Vector",
    0x2Du,
    0x2Cu);
  ActivationFactory = RoGetActivationFactory(v17, &GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9, &v8);
  if ( ActivationFactory >= 0 )
  {
    v7 = 0;
    v4 = v8;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
    ActivationFactory =  Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}(v4, v10, &v7);
    if ( ActivationFactory >= 0 )
    {
      v5 = v7;
      v7 = 0;
      *a2 = v5;
      ActivationFactory = 0;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v8);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800546ac  mov     [rsp-8+arg_0], rbx
0x1800546b1  mov     [rsp-8+arg_10], rdi
0x1800546b6  push    rbp
0x1800546b7  lea     rbp, [rsp-40h]
0x1800546bc  sub     rsp, 140h
0x1800546c3  mov     rax, cs:__security_cookie
0x1800546ca  xor     rax, rsp
0x1800546cd  mov     [rbp+40h+var_10], rax
0x1800546d1  mov     rdi, rdx
0x1800546d4  lea     rax, aWindowsFoundat_12; "Windows.Foundation.Collections.IVector`"...
0x1800546db  mov     [rsp+140h+var_110], rax
0x1800546e0  lea     rdx, [rsp+140h+var_110]
0x1800546e5  lea     rcx, [rbp+40h+var_70]
0x1800546e9  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800546ee  lea     rax, aWindowsFoundat_8; "Windows.Foundation.Collections.IVectorV"...
0x1800546f5  mov     [rsp+140h+var_110], rax
0x1800546fa  lea     rdx, [rsp+140h+var_110]
0x1800546ff  lea     rcx, [rbp+40h+var_50]
0x180054703  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180054708  lea     rax, aWindowsFoundat_1; "Windows.Foundation.Collections.IIterato"...
0x18005470f  mov     [rsp+140h+var_110], rax
0x180054714  lea     rdx, [rsp+140h+var_110]
0x180054719  lea     rcx, [rbp+40h+var_30]
0x18005471d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180054722  mov     rax, [rbp+40h+var_58]
0x180054726  mov     [rsp+140h+var_100], rax
0x18005472b  mov     rax, [rbp+40h+var_38]
0x18005472f  mov     [rsp+140h+var_F8], rax
0x180054734  mov     rax, [rbp+40h+var_18]
0x180054738  mov     [rsp+140h+var_F0], rax
0x18005473d  movups  xmm0, xmmword ptr cs:_GUID_7282c4e1_bcda_41d7_8e75_53726d5c228f.Data1
0x180054744  movdqu  [rsp+140h+var_E8], xmm0
0x18005474a  movups  xmm1, xmmword ptr cs:_GUID_36569ad4_6032_5471_9f39_19af988cc7b2.Data1
0x180054751  movdqu  [rsp+140h+var_D8], xmm1
0x180054757  movups  xmm0, xmmword ptr cs:_GUID_0ed96c5c_dc7f_5b24_ad64_6034dc6852e9.Data1
0x18005475e  movdqu  [rsp+140h+var_C8], xmm0
0x180054764  movups  xmm1, xmmword ptr cs:_GUID_8b420f77_1600_5e25_b6ac_d1c2454dbe88.Data1
0x18005476b  movdqu  [rbp+40h+var_B8], xmm1
0x180054770  movups  xmm0, xmmword ptr cs:_GUID_b97674b4_c069_56fb_bc9a_98ec84ba4a78.Data1
0x180054777  movdqu  [rbp+40h+var_A8], xmm0
0x18005477c  mov     [rsp+140h+var_118], 0
0x180054785  lea     rcx, [rsp+140h+var_118]
0x18005478a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005478f  mov     [rbp+40h+var_78], 0
0x180054797  mov     r9d, 2Ch ; ','; unsigned int
0x18005479d  lea     r8d, [r9+1]; unsigned int
0x1800547a1  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_Detail_Vector@@3QBGB; "Windows.Foundation.Collections.Detail.V"...
0x1800547a8  lea     rcx, [rbp+40h+hstringHeader]; hstringHeader
0x1800547ac  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800547b1  lea     r8, [rsp+140h+var_118]
0x1800547b6  lea     rdx, _GUID_08c77958_89bf_5cf8_a9cd_c72147b9b3a9
0x1800547bd  mov     rcx, [rbp+40h+var_78]
0x1800547c1  call    cs:__imp_RoGetActivationFactory
0x1800547c7  mov     ebx, eax
0x1800547c9  test    eax, eax
0x1800547cb  js      short loc_18005481A
0x1800547cd  mov     [rsp+140h+var_120], 0
0x1800547d6  mov     rbx, [rsp+140h+var_118]
0x1800547db  lea     rcx, [rsp+140h+var_120]
0x1800547e0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800547e5  lea     r8, [rsp+140h+var_120]
0x1800547ea  lea     rdx, [rsp+140h+var_100]
0x1800547ef  mov     rcx, rbx
0x1800547f2  call    ??_9IVectorStatics@Detail@Collections@Foundation@Windows@@$BPA@AA; [thunk]: Windows::Foundation::Collections::Detail::IVectorStatics::`vcall'{240,{flat}}
0x1800547f7  mov     ebx, eax
0x1800547f9  test    eax, eax
0x1800547fb  js      short loc_180054810
0x1800547fd  mov     rax, [rsp+140h+var_120]
0x180054802  mov     [rsp+140h+var_120], 0
0x18005480b  mov     [rdi], rax
0x18005480e  xor     ebx, ebx
0x180054810  lea     rcx, [rsp+140h+var_120]
0x180054815  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18005481a  lea     rcx, [rsp+140h+var_118]
0x18005481f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180054824  mov     eax, ebx
0x180054826  mov     rcx, [rbp+40h+var_10]
0x18005482a  xor     rcx, rsp; StackCookie
0x18005482d  call    __security_check_cookie
0x180054832  lea     r11, [rsp+140h+var_s0]
0x18005483a  mov     rbx, [r11+10h]
0x18005483e  mov     rdi, [r11+20h]
0x180054842  mov     rsp, r11
0x180054845  pop     rbp
0x180054846  retn
```
