# MdmLogCollector::CollectDeviceLinkInfo(void)

- ea: `0x18010aafc`
- end: `0x18010afa1`
- name: `?CollectDeviceLinkInfo@MdmLogCollector@@AEAAJXZ`
- size: `1189`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010ba4c`

## callees

- `0x180019080`
- `0x18001a030`
- `0x18001a130`
- `0x1800e68b0`
- `0x1800e7c78`
- `0x1800ed46c`
- `0x1800ef8c4`
- `0x1800efd9c`
- `0x1801065d0`
- `0x1801091bc`
- `0x180109d50`
- `0x18010aafc`
- `0x18010f60c`
- `0x180110d34`
- `0x18011268c`
- `0x180193010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010ae9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18010ae9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18010acd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18010acd2`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18010ac10`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18010ac10`

## string_xrefs

- `0x18010ab3e`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010ab9a`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010ac85`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010acef`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010ad6c`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010adcb`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010ae48`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010aedf`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x18010ab56`: `Collecting device link information.\n`
- `0x18010abdc`: `ModernDeployment.Autopilot.Core.DeviceLinkUtilities`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall MdmLogCollector::CollectDeviceLinkInfo(MdmLogCollector *this)
{
  __int64 v3; // rcx
  int TemporaryOutputPath; // eax
  unsigned int v5; // ebx
  int v6; // ebx
  const WCHAR *v7; // rax
  HRESULT v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rax
  int v16; // eax
  unsigned int v17; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v19; // rax
  int v20; // eax
  unsigned int v21; // ebx
  int v22; // [rsp+20h] [rbp-A8h]
  __int64 *v23; // [rsp+30h] [rbp-98h] BYREF
  __int64 *v24; // [rsp+38h] [rbp-90h] BYREF
  HSTRING string; // [rsp+40h] [rbp-88h] BYREF
  HSTRING v26; // [rsp+48h] [rbp-80h] BYREF
  __int64 *v27; // [rsp+50h] [rbp-78h] BYREF
  __int128 v28; // [rsp+58h] [rbp-70h] BYREF
  UINT32 length[4]; // [rsp+68h] [rbp-60h]
  _BYTE v30[32]; // [rsp+78h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-30h] BYREF
  __int64 v32; // [rsp+B0h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    wprintf(L"Collecting device link information.\n");
    v28 = 0;
    *(__m128i *)length = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v28) = 0;
    TemporaryOutputPath = MdmLogCollector::GetTemporaryOutputPath(v3, &v28);
    v5 = TemporaryOutputPath;
    if ( TemporaryOutputPath >= 0 )
    {
      v32 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"ModernDeployment.Autopilot.Core.DeviceLinkUtilities",
        0x34u,
        0x33u);
      v23 = 0;
      v27 = 0;
      v6 = RoActivateInstance(v32, &v27);
      if ( v6 >= 0 )
      {
        if ( !memcmp_0(&GUID_e85766c2_3059_5cd5_a1e7_5e5a7b9bbb4d, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
        {
          v23 = v27;
        }
        else
        {
          v6 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64 **))*v27)(
                 v27,
                 &GUID_e85766c2_3059_5cd5_a1e7_5e5a7b9bbb4d,
                 &v23);
          (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
        }
      }
      if ( v6 >= 0 )
      {
        string = 0;
        v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v28);
        v8 = WindowsCreateString(v7, length[0], &string);
        v9 = v8;
        if ( v8 >= 0 )
        {
          v24 = 0;
          v10 = *v23;
          v24 = 0;
          v11 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, __int64 **))(v10 + 48))(v23, string, 1, &v24);
          v12 = v11;
          if ( v11 >= 0 )
          {
            v13 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(v24);
            v14 = v13;
            if ( v13 >= 0 )
            {
              v26 = 0;
              v15 = *v24;
              v26 = 0;
              v16 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v15 + 64))(v24, &v26);
              v17 = v16;
              if ( v16 >= 0 )
              {
                StringRawBuffer = WindowsGetStringRawBuffer(v26, 0);
                std::wstring::wstring(v30, StringRawBuffer);
                v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
                v20 = MdmLogCollector::AddEntry(v19, (char *)this + 32);
                v21 = v20;
                if ( v20 >= 0 )
                {
                  std::wstring::_Tidy_deallocate(v30);
                  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v26);
                  wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v24);
                  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                  wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v23);
                  std::wstring::_Tidy_deallocate(&v28);
                  return 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x704,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                    (const char *)(unsigned int)v20,
                    v22);
                  std::wstring::_Tidy_deallocate(v30);
                  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v26);
                  wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v24);
                  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                  wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v23);
                  std::wstring::_Tidy_deallocate(&v28);
                  return v21;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x700,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                  (const char *)(unsigned int)v16,
                  v22);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&v26);
                wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v24);
                wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
                wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v23);
                std::wstring::_Tidy_deallocate(&v28);
                return v17;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x6FD,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
                (const char *)(unsigned int)v13,
                v22);
              wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v24);
              wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
              wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v23);
              std::wstring::_Tidy_deallocate(&v28);
              return v14;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x6FA,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
              (const char *)(unsigned int)v11,
              v22);
            wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v24);
            wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
            wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v23);
            std::wstring::_Tidy_deallocate(&v28);
            return v12;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6F6,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
            (const char *)(unsigned int)v8,
            v22);
          wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
          wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v23);
          std::wstring::_Tidy_deallocate(&v28);
          return v9;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6F2,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
          (const char *)(unsigned int)v6,
          v22);
        wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(&v23);
        std::wstring::_Tidy_deallocate(&v28);
        return (unsigned int)v6;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6ED,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
        (const char *)(unsigned int)TemporaryOutputPath,
        v22);
      std::wstring::_Tidy_deallocate(&v28);
      return v5;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)0x80004001LL,
      v22);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x18010aafc  mov     [rsp+arg_8], rbx
0x18010ab01  push    rdi
0x18010ab02  sub     rsp, 0C0h
0x18010ab09  mov     rax, cs:__security_cookie
0x18010ab10  xor     rax, rsp
0x18010ab13  mov     [rsp+0C8h+var_10], rax
0x18010ab1b  mov     rdi, rcx
0x18010ab1e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18010ab25  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18010ab2a  test    al, al
0x18010ab2c  jnz     short loc_18010AB56
0x18010ab2e  mov     rcx, [rsp+0C8h]; this
0x18010ab36  mov     ebx, 80004001h
0x18010ab3b  mov     r9d, ebx; char *
0x18010ab3e  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010ab45  mov     edx, 6E7h; void *
0x18010ab4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ab4f  mov     eax, ebx
0x18010ab51  jmp     loc_18010AF7F
0x18010ab56  lea     rcx, aCollectingDevi; "Collecting device link information.\n"
0x18010ab5d  call    wprintf
0x18010ab62  xorps   xmm0, xmm0
0x18010ab65  movups  [rsp+0C8h+var_70], xmm0
0x18010ab6a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18010ab72  movdqu  xmmword ptr [rsp+0C8h+length], xmm1
0x18010ab78  xor     eax, eax
0x18010ab7a  mov     word ptr [rsp+0C8h+var_70], ax
0x18010ab7f  lea     rdx, [rsp+0C8h+var_70]
0x18010ab84  call    ?GetTemporaryOutputPath@MdmLogCollector@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetTemporaryOutputPath(std::wstring &)
0x18010ab89  mov     ebx, eax
0x18010ab8b  test    eax, eax
0x18010ab8d  jns     short loc_18010ABBD
0x18010ab8f  mov     rcx, [rsp+0C8h]; this
0x18010ab97  mov     r9d, eax; char *
0x18010ab9a  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010aba1  mov     edx, 6EDh; void *
0x18010aba6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010abab  nop
0x18010abac  lea     rcx, [rsp+0C8h+var_70]
0x18010abb1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010abb6  mov     eax, ebx
0x18010abb8  jmp     loc_18010AF7F
0x18010abbd  mov     [rsp+0C8h+var_98], 0
0x18010abc6  mov     [rsp+0C8h+var_18], 0
0x18010abd2  mov     r9d, 33h ; '3'; unsigned int
0x18010abd8  lea     r8d, [r9+1]; unsigned int
0x18010abdc  lea     rdx, ?RuntimeClass_ModernDeployment_Autopilot_Core_DeviceLinkUtilities@@3QBGB; "ModernDeployment.Autopilot.Core.DeviceL"...
0x18010abe3  lea     rcx, [rsp+0C8h+hstringHeader]; hstringHeader
0x18010abeb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18010abf0  nop
0x18010abf1  mov     [rsp+0C8h+var_98], 0
0x18010abfa  mov     [rsp+0C8h+var_78], 0
0x18010ac03  lea     rdx, [rsp+0C8h+var_78]
0x18010ac08  mov     rcx, [rsp+0C8h+var_18]
0x18010ac10  call    cs:__imp_RoActivateInstance
0x18010ac17  nop     dword ptr [rax+rax+00h]
0x18010ac1c  mov     ebx, eax
0x18010ac1e  test    eax, eax
0x18010ac20  js      short loc_18010AC76
0x18010ac22  mov     r8d, 10h; Size
0x18010ac28  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18010ac2f  lea     rcx, _GUID_e85766c2_3059_5cd5_a1e7_5e5a7b9bbb4d; Buf1
0x18010ac36  call    memcmp_0
0x18010ac3b  mov     rcx, [rsp+0C8h+var_78]
0x18010ac40  test    eax, eax
0x18010ac42  jnz     short loc_18010AC4B
0x18010ac44  mov     [rsp+0C8h+var_98], rcx
0x18010ac49  jmp     short loc_18010AC76
0x18010ac4b  mov     rax, [rcx]
0x18010ac4e  lea     r8, [rsp+0C8h+var_98]
0x18010ac53  lea     rdx, _GUID_e85766c2_3059_5cd5_a1e7_5e5a7b9bbb4d
0x18010ac5a  mov     rax, [rax]
0x18010ac5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ac62  mov     ebx, eax
0x18010ac64  mov     rcx, [rsp+0C8h+var_78]
0x18010ac69  mov     rax, [rcx]
0x18010ac6c  mov     rax, [rax+10h]
0x18010ac70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ac75  nop
0x18010ac76  test    ebx, ebx
0x18010ac78  jns     short loc_18010ACB3
0x18010ac7a  mov     rcx, [rsp+0C8h]; this
0x18010ac82  mov     r9d, ebx; char *
0x18010ac85  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010ac8c  mov     edx, 6F2h; void *
0x18010ac91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ac96  nop
0x18010ac97  lea     rcx, [rsp+0C8h+var_98]
0x18010ac9c  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010aca1  nop
0x18010aca2  lea     rcx, [rsp+0C8h+var_70]
0x18010aca7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010acac  mov     eax, ebx
0x18010acae  jmp     loc_18010AF7F
0x18010acb3  mov     [rsp+0C8h+string], 0
0x18010acbc  lea     rcx, [rsp+0C8h+var_70]
0x18010acc1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010acc6  mov     rcx, rax; sourceString
0x18010acc9  lea     r8, [rsp+0C8h+string]; string
0x18010acce  mov     edx, [rsp+0C8h+length]; length
0x18010acd2  call    cs:__imp_WindowsCreateString
0x18010acd9  nop     dword ptr [rax+rax+00h]
0x18010acde  mov     ebx, eax
0x18010ace0  test    eax, eax
0x18010ace2  jns     short loc_18010AD28
0x18010ace4  mov     rcx, [rsp+0C8h]; this
0x18010acec  mov     r9d, eax; char *
0x18010acef  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010acf6  mov     edx, 6F6h; void *
0x18010acfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ad00  nop
0x18010ad01  lea     rcx, [rsp+0C8h+string]
0x18010ad06  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18010ad0b  nop
0x18010ad0c  lea     rcx, [rsp+0C8h+var_98]
0x18010ad11  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010ad16  nop
0x18010ad17  lea     rcx, [rsp+0C8h+var_70]
0x18010ad1c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ad21  mov     eax, ebx
0x18010ad23  jmp     loc_18010AF7F
0x18010ad28  mov     [rsp+0C8h+var_90], 0
0x18010ad31  mov     rcx, [rsp+0C8h+var_98]
0x18010ad36  mov     rax, [rcx]
0x18010ad39  mov     [rsp+0C8h+var_90], 0
0x18010ad42  lea     r9, [rsp+0C8h+var_90]
0x18010ad47  mov     r8d, 1
0x18010ad4d  mov     rdx, [rsp+0C8h+string]
0x18010ad52  mov     rax, [rax+30h]
0x18010ad56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ad5b  mov     ebx, eax
0x18010ad5d  test    eax, eax
0x18010ad5f  jns     short loc_18010ADB0
0x18010ad61  mov     rcx, [rsp+0C8h]; this
0x18010ad69  mov     r9d, eax; char *
0x18010ad6c  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010ad73  mov     edx, 6FAh; void *
0x18010ad78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ad7d  nop
0x18010ad7e  lea     rcx, [rsp+0C8h+var_90]
0x18010ad83  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010ad88  nop
0x18010ad89  lea     rcx, [rsp+0C8h+string]
0x18010ad8e  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18010ad93  nop
0x18010ad94  lea     rcx, [rsp+0C8h+var_98]
0x18010ad99  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010ad9e  nop
0x18010ad9f  lea     rcx, [rsp+0C8h+var_70]
0x18010ada4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ada9  mov     eax, ebx
0x18010adab  jmp     loc_18010AF7F
0x18010adb0  mov     rcx, [rsp+0C8h+var_90]
0x18010adb5  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)
0x18010adba  mov     ebx, eax
0x18010adbc  test    eax, eax
0x18010adbe  jns     short loc_18010AE0F
0x18010adc0  mov     rcx, [rsp+0C8h]; this
0x18010adc8  mov     r9d, eax; char *
0x18010adcb  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010add2  mov     edx, 6FDh; void *
0x18010add7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010addc  nop
0x18010addd  lea     rcx, [rsp+0C8h+var_90]
0x18010ade2  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010ade7  nop
0x18010ade8  lea     rcx, [rsp+0C8h+string]
0x18010aded  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18010adf2  nop
0x18010adf3  lea     rcx, [rsp+0C8h+var_98]
0x18010adf8  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010adfd  nop
0x18010adfe  lea     rcx, [rsp+0C8h+var_70]
0x18010ae03  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ae08  mov     eax, ebx
0x18010ae0a  jmp     loc_18010AF7F
0x18010ae0f  mov     [rsp+0C8h+var_80], 0
0x18010ae18  mov     rcx, [rsp+0C8h+var_90]
0x18010ae1d  mov     rax, [rcx]
0x18010ae20  mov     [rsp+0C8h+var_80], 0
0x18010ae29  lea     rdx, [rsp+0C8h+var_80]
0x18010ae2e  mov     rax, [rax+40h]
0x18010ae32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010ae37  mov     ebx, eax
0x18010ae39  test    eax, eax
0x18010ae3b  jns     short loc_18010AE97
0x18010ae3d  mov     rcx, [rsp+0C8h]; this
0x18010ae45  mov     r9d, eax; char *
0x18010ae48  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010ae4f  mov     edx, 700h; void *
0x18010ae54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ae59  nop
0x18010ae5a  lea     rcx, [rsp+0C8h+var_80]
0x18010ae5f  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18010ae64  nop
0x18010ae65  lea     rcx, [rsp+0C8h+var_90]
0x18010ae6a  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010ae6f  nop
0x18010ae70  lea     rcx, [rsp+0C8h+string]
0x18010ae75  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18010ae7a  nop
0x18010ae7b  lea     rcx, [rsp+0C8h+var_98]
0x18010ae80  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010ae85  nop
0x18010ae86  lea     rcx, [rsp+0C8h+var_70]
0x18010ae8b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010ae90  mov     eax, ebx
0x18010ae92  jmp     loc_18010AF7F
0x18010ae97  xor     edx, edx; length
0x18010ae99  mov     rcx, [rsp+0C8h+var_80]; string
0x18010ae9e  call    cs:__imp_WindowsGetStringRawBuffer
0x18010aea5  nop     dword ptr [rax+rax+00h]
0x18010aeaa  mov     rdx, rax
0x18010aead  lea     rcx, [rsp+0C8h+var_50]
0x18010aeb2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010aeb7  nop
0x18010aeb8  lea     rcx, [rsp+0C8h+var_50]
0x18010aebd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010aec2  mov     rcx, rax
0x18010aec5  lea     rdx, [rdi+20h]
0x18010aec9  call    ?AddEntry@MdmLogCollector@@CAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmLogCollector::AddEntry(ushort const *,std::vector<std::wstring> &)
0x18010aece  mov     ebx, eax
0x18010aed0  test    eax, eax
0x18010aed2  jns     short loc_18010AF36
0x18010aed4  mov     rcx, [rsp+0C8h]; this
0x18010aedc  mov     r9d, eax; char *
0x18010aedf  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010aee6  mov     edx, 704h; void *
0x18010aeeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010aef0  nop
0x18010aef1  lea     rcx, [rsp+0C8h+var_50]
0x18010aef6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010aefb  nop
0x18010aefc  lea     rcx, [rsp+0C8h+var_80]
0x18010af01  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18010af06  nop
0x18010af07  lea     rcx, [rsp+0C8h+var_90]
0x18010af0c  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010af11  nop
0x18010af12  lea     rcx, [rsp+0C8h+string]
0x18010af17  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18010af1c  nop
0x18010af1d  lea     rcx, [rsp+0C8h+var_98]
0x18010af22  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010af27  nop
0x18010af28  lea     rcx, [rsp+0C8h+var_70]
0x18010af2d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010af32  mov     eax, ebx
0x18010af34  jmp     short loc_18010AF7F
0x18010af36  lea     rcx, [rsp+0C8h+var_50]
0x18010af3b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010af40  nop
0x18010af41  lea     rcx, [rsp+0C8h+var_80]
0x18010af46  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18010af4b  nop
0x18010af4c  lea     rcx, [rsp+0C8h+var_90]
0x18010af51  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010af56  nop
0x18010af57  lea     rcx, [rsp+0C8h+string]
0x18010af5c  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x18010af61  nop
0x18010af62  lea     rcx, [rsp+0C8h+var_98]
0x18010af67  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010af6c  nop
0x18010af6d  lea     rcx, [rsp+0C8h+var_70]
0x18010af72  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010af77  xor     eax, eax
0x18010af79  jmp     short loc_18010AF7F
0x18010af7b  mov     eax, dword ptr [rsp+0C8h+var_98]
0x18010af7f  mov     rcx, [rsp+0C8h+var_10]
0x18010af87  xor     rcx, rsp; StackCookie
0x18010af8a  call    __security_check_cookie
0x18010af8f  mov     rbx, [rsp+0C8h+arg_8]
0x18010af97  add     rsp, 0C0h
0x18010af9e  pop     rdi
0x18010af9f  retn
```
