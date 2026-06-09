# MdmLogCollector::CollectDeviceLinkInfo(void)

- ea: `0x180109760`
- end: `0x180109bf3`
- name: `?CollectDeviceLinkInfo@MdmLogCollector@@AEAAJXZ`
- size: `1171`
- prototype: `__int64 __fastcall(MdmLogCollector *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010a670`

## callees

- `0x180019000`
- `0x180019fa0`
- `0x18001a0a0`
- `0x1800e66dc`
- `0x1800e7aa8`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x1801052e4`
- `0x180107eec`
- `0x1801089c0`
- `0x180109760`
- `0x18010e09c`
- `0x18010f704`
- `0x1801111ec`
- `0x180191010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180109af6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180109af6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180109930`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180109930`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180109874`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180109874`

## string_xrefs

- `0x1801097a2`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x1801097fe`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x1801098e3`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180109947`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x1801099c4`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180109a23`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180109aa0`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x180109b31`: `onecoreuap\admin\enterprisemgmt\mdmdiagnostics\dll\mdmlogcollector.cpp`
- `0x1801097ba`: `Collecting device link information.\n`
- `0x180109840`: `ModernDeployment.Autopilot.Core.DeviceLinkUtilities`

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
                    (void *)0x72D,
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
                  (void *)0x729,
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
                (void *)0x726,
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
              (void *)0x723,
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
            (void *)0x71F,
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
          (void *)0x71B,
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
        (void *)0x716,
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
      (void *)0x710,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\dll\\mdmlogcollector.cpp",
      (const char *)0x80004001LL,
      v22);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x180109760  mov     [rsp+arg_8], rbx
0x180109765  push    rdi
0x180109766  sub     rsp, 0C0h
0x18010976d  mov     rax, cs:__security_cookie
0x180109774  xor     rax, rsp
0x180109777  mov     [rsp+0C8h+var_10], rax
0x18010977f  mov     rdi, rcx
0x180109782  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180109789  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18010978e  test    al, al
0x180109790  jnz     short loc_1801097BA
0x180109792  mov     rcx, [rsp+0C8h]; this
0x18010979a  mov     ebx, 80004001h
0x18010979f  mov     r9d, ebx; char *
0x1801097a2  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801097a9  mov     edx, 710h; void *
0x1801097ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801097b3  mov     eax, ebx
0x1801097b5  jmp     loc_180109BD1
0x1801097ba  lea     rcx, aCollectingDevi; "Collecting device link information.\n"
0x1801097c1  call    wprintf
0x1801097c6  xorps   xmm0, xmm0
0x1801097c9  movups  [rsp+0C8h+var_70], xmm0
0x1801097ce  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801097d6  movdqu  xmmword ptr [rsp+0C8h+length], xmm1
0x1801097dc  xor     eax, eax
0x1801097de  mov     word ptr [rsp+0C8h+var_70], ax
0x1801097e3  lea     rdx, [rsp+0C8h+var_70]
0x1801097e8  call    ?GetTemporaryOutputPath@MdmLogCollector@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MdmLogCollector::GetTemporaryOutputPath(std::wstring &)
0x1801097ed  mov     ebx, eax
0x1801097ef  test    eax, eax
0x1801097f1  jns     short loc_180109821
0x1801097f3  mov     rcx, [rsp+0C8h]; this
0x1801097fb  mov     r9d, eax; char *
0x1801097fe  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180109805  mov     edx, 716h; void *
0x18010980a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010980f  nop
0x180109810  lea     rcx, [rsp+0C8h+var_70]
0x180109815  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010981a  mov     eax, ebx
0x18010981c  jmp     loc_180109BD1
0x180109821  mov     [rsp+0C8h+var_98], 0
0x18010982a  mov     [rsp+0C8h+var_18], 0
0x180109836  mov     r9d, 33h ; '3'; unsigned int
0x18010983c  lea     r8d, [r9+1]; unsigned int
0x180109840  lea     rdx, ?RuntimeClass_ModernDeployment_Autopilot_Core_DeviceLinkUtilities@@3QBGB; "ModernDeployment.Autopilot.Core.DeviceL"...
0x180109847  lea     rcx, [rsp+0C8h+hstringHeader]; hstringHeader
0x18010984f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180109854  nop
0x180109855  mov     [rsp+0C8h+var_98], 0
0x18010985e  mov     [rsp+0C8h+var_78], 0
0x180109867  lea     rdx, [rsp+0C8h+var_78]
0x18010986c  mov     rcx, [rsp+0C8h+var_18]
0x180109874  call    cs:__imp_RoActivateInstance
0x18010987a  mov     ebx, eax
0x18010987c  test    eax, eax
0x18010987e  js      short loc_1801098D4
0x180109880  mov     r8d, 10h; Size
0x180109886  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18010988d  lea     rcx, _GUID_e85766c2_3059_5cd5_a1e7_5e5a7b9bbb4d; Buf1
0x180109894  call    memcmp_0
0x180109899  mov     rcx, [rsp+0C8h+var_78]
0x18010989e  test    eax, eax
0x1801098a0  jnz     short loc_1801098A9
0x1801098a2  mov     [rsp+0C8h+var_98], rcx
0x1801098a7  jmp     short loc_1801098D4
0x1801098a9  mov     rax, [rcx]
0x1801098ac  lea     r8, [rsp+0C8h+var_98]
0x1801098b1  lea     rdx, _GUID_e85766c2_3059_5cd5_a1e7_5e5a7b9bbb4d
0x1801098b8  mov     rax, [rax]
0x1801098bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801098c0  mov     ebx, eax
0x1801098c2  mov     rcx, [rsp+0C8h+var_78]
0x1801098c7  mov     rax, [rcx]
0x1801098ca  mov     rax, [rax+10h]
0x1801098ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801098d3  nop
0x1801098d4  test    ebx, ebx
0x1801098d6  jns     short loc_180109911
0x1801098d8  mov     rcx, [rsp+0C8h]; this
0x1801098e0  mov     r9d, ebx; char *
0x1801098e3  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801098ea  mov     edx, 71Bh; void *
0x1801098ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801098f4  nop
0x1801098f5  lea     rcx, [rsp+0C8h+var_98]
0x1801098fa  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x1801098ff  nop
0x180109900  lea     rcx, [rsp+0C8h+var_70]
0x180109905  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18010990a  mov     eax, ebx
0x18010990c  jmp     loc_180109BD1
0x180109911  mov     [rsp+0C8h+string], 0
0x18010991a  lea     rcx, [rsp+0C8h+var_70]
0x18010991f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180109924  mov     rcx, rax; sourceString
0x180109927  lea     r8, [rsp+0C8h+string]; string
0x18010992c  mov     edx, [rsp+0C8h+length]; length
0x180109930  call    cs:__imp_WindowsCreateString
0x180109936  mov     ebx, eax
0x180109938  test    eax, eax
0x18010993a  jns     short loc_180109980
0x18010993c  mov     rcx, [rsp+0C8h]; this
0x180109944  mov     r9d, eax; char *
0x180109947  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x18010994e  mov     edx, 71Fh; void *
0x180109953  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109958  nop
0x180109959  lea     rcx, [rsp+0C8h+string]
0x18010995e  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180109963  nop
0x180109964  lea     rcx, [rsp+0C8h+var_98]
0x180109969  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x18010996e  nop
0x18010996f  lea     rcx, [rsp+0C8h+var_70]
0x180109974  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109979  mov     eax, ebx
0x18010997b  jmp     loc_180109BD1
0x180109980  mov     [rsp+0C8h+var_90], 0
0x180109989  mov     rcx, [rsp+0C8h+var_98]
0x18010998e  mov     rax, [rcx]
0x180109991  mov     [rsp+0C8h+var_90], 0
0x18010999a  lea     r9, [rsp+0C8h+var_90]
0x18010999f  mov     r8d, 1
0x1801099a5  mov     rdx, [rsp+0C8h+string]
0x1801099aa  mov     rax, [rax+30h]
0x1801099ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801099b3  mov     ebx, eax
0x1801099b5  test    eax, eax
0x1801099b7  jns     short loc_180109A08
0x1801099b9  mov     rcx, [rsp+0C8h]; this
0x1801099c1  mov     r9d, eax; char *
0x1801099c4  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801099cb  mov     edx, 723h; void *
0x1801099d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801099d5  nop
0x1801099d6  lea     rcx, [rsp+0C8h+var_90]
0x1801099db  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x1801099e0  nop
0x1801099e1  lea     rcx, [rsp+0C8h+string]
0x1801099e6  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x1801099eb  nop
0x1801099ec  lea     rcx, [rsp+0C8h+var_98]
0x1801099f1  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x1801099f6  nop
0x1801099f7  lea     rcx, [rsp+0C8h+var_70]
0x1801099fc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109a01  mov     eax, ebx
0x180109a03  jmp     loc_180109BD1
0x180109a08  mov     rcx, [rsp+0C8h+var_90]
0x180109a0d  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)
0x180109a12  mov     ebx, eax
0x180109a14  test    eax, eax
0x180109a16  jns     short loc_180109A67
0x180109a18  mov     rcx, [rsp+0C8h]; this
0x180109a20  mov     r9d, eax; char *
0x180109a23  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180109a2a  mov     edx, 726h; void *
0x180109a2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109a34  nop
0x180109a35  lea     rcx, [rsp+0C8h+var_90]
0x180109a3a  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x180109a3f  nop
0x180109a40  lea     rcx, [rsp+0C8h+string]
0x180109a45  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180109a4a  nop
0x180109a4b  lea     rcx, [rsp+0C8h+var_98]
0x180109a50  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x180109a55  nop
0x180109a56  lea     rcx, [rsp+0C8h+var_70]
0x180109a5b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109a60  mov     eax, ebx
0x180109a62  jmp     loc_180109BD1
0x180109a67  mov     [rsp+0C8h+var_80], 0
0x180109a70  mov     rcx, [rsp+0C8h+var_90]
0x180109a75  mov     rax, [rcx]
0x180109a78  mov     [rsp+0C8h+var_80], 0
0x180109a81  lea     rdx, [rsp+0C8h+var_80]
0x180109a86  mov     rax, [rax+40h]
0x180109a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109a8f  mov     ebx, eax
0x180109a91  test    eax, eax
0x180109a93  jns     short loc_180109AEF
0x180109a95  mov     rcx, [rsp+0C8h]; this
0x180109a9d  mov     r9d, eax; char *
0x180109aa0  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180109aa7  mov     edx, 729h; void *
0x180109aac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109ab1  nop
0x180109ab2  lea     rcx, [rsp+0C8h+var_80]
0x180109ab7  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180109abc  nop
0x180109abd  lea     rcx, [rsp+0C8h+var_90]
0x180109ac2  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x180109ac7  nop
0x180109ac8  lea     rcx, [rsp+0C8h+string]
0x180109acd  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180109ad2  nop
0x180109ad3  lea     rcx, [rsp+0C8h+var_98]
0x180109ad8  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x180109add  nop
0x180109ade  lea     rcx, [rsp+0C8h+var_70]
0x180109ae3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109ae8  mov     eax, ebx
0x180109aea  jmp     loc_180109BD1
0x180109aef  xor     edx, edx; length
0x180109af1  mov     rcx, [rsp+0C8h+var_80]; string
0x180109af6  call    cs:__imp_WindowsGetStringRawBuffer
0x180109afc  mov     rdx, rax
0x180109aff  lea     rcx, [rsp+0C8h+var_50]
0x180109b04  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180109b09  nop
0x180109b0a  lea     rcx, [rsp+0C8h+var_50]
0x180109b0f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180109b14  mov     rcx, rax
0x180109b17  lea     rdx, [rdi+20h]
0x180109b1b  call    ?AddEntry@MdmLogCollector@@CAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; MdmLogCollector::AddEntry(ushort const *,std::vector<std::wstring> &)
0x180109b20  mov     ebx, eax
0x180109b22  test    eax, eax
0x180109b24  jns     short loc_180109B88
0x180109b26  mov     rcx, [rsp+0C8h]; this
0x180109b2e  mov     r9d, eax; char *
0x180109b31  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180109b38  mov     edx, 72Dh; void *
0x180109b3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109b42  nop
0x180109b43  lea     rcx, [rsp+0C8h+var_50]
0x180109b48  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109b4d  nop
0x180109b4e  lea     rcx, [rsp+0C8h+var_80]
0x180109b53  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180109b58  nop
0x180109b59  lea     rcx, [rsp+0C8h+var_90]
0x180109b5e  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x180109b63  nop
0x180109b64  lea     rcx, [rsp+0C8h+string]
0x180109b69  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180109b6e  nop
0x180109b6f  lea     rcx, [rsp+0C8h+var_98]
0x180109b74  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x180109b79  nop
0x180109b7a  lea     rcx, [rsp+0C8h+var_70]
0x180109b7f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109b84  mov     eax, ebx
0x180109b86  jmp     short loc_180109BD1
0x180109b88  lea     rcx, [rsp+0C8h+var_50]
0x180109b8d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109b92  nop
0x180109b93  lea     rcx, [rsp+0C8h+var_80]
0x180109b98  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180109b9d  nop
0x180109b9e  lea     rcx, [rsp+0C8h+var_90]
0x180109ba3  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x180109ba8  nop
0x180109ba9  lea     rcx, [rsp+0C8h+string]
0x180109bae  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x180109bb3  nop
0x180109bb4  lea     rcx, [rsp+0C8h+var_98]
0x180109bb9  call    ??1?$com_ptr_t@UIConfigNode@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigNode,wil::err_returncode_policy>::~com_ptr_t<IConfigNode,wil::err_returncode_policy>(void)
0x180109bbe  nop
0x180109bbf  lea     rcx, [rsp+0C8h+var_70]
0x180109bc4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180109bc9  xor     eax, eax
0x180109bcb  jmp     short loc_180109BD1
0x180109bcd  mov     eax, dword ptr [rsp+0C8h+var_98]
0x180109bd1  mov     rcx, [rsp+0C8h+var_10]
0x180109bd9  xor     rcx, rsp; StackCookie
0x180109bdc  call    __security_check_cookie
0x180109be1  mov     rbx, [rsp+0C8h+arg_8]
0x180109be9  add     rsp, 0C0h
0x180109bf0  pop     rdi
0x180109bf1  retn
```
