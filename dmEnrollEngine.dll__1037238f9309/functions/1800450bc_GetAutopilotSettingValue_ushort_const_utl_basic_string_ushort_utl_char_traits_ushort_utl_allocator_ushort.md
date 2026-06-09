# GetAutopilotSettingValue(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x1800450bc`
- end: `0x1800453ae`
- name: `?GetAutopilotSettingValue@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `754`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800141d0`

## callees

- `0x18000d810`
- `0x18000e508`
- `0x180011938`
- `0x18002e1a0`
- `0x18003392c`
- `0x1800339ac`
- `0x1800375ec`
- `0x18003c41c`
- `0x18003c968`
- `0x1800432d4`
- `0x1800450bc`
- `0x18004c2ec`
- `0x18004c364`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045272`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180045272`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045351`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045261`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045261`

## string_xrefs

- `0x18004513e`: `EnterpriseDeviceManagement.Service.AutoPilot.AutoPilotServer`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall GetAutopilotSettingValue(__int64 a1, __int64 a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, _QWORD); // rbx
  __int64 v8; // rax
  int v9; // eax
  DWORD v10; // edx
  int v11; // r8d
  unsigned int v12; // ebx
  HSTRING v13; // rbx
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // rdi
  int v15; // ebx
  PCWSTR StringRawBuffer; // rax
  int v17; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v18; // [rsp+28h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+30h] [rbp-98h] BYREF
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-90h] BYREF
  DWORD dwErrCode[2]; // [rsp+40h] [rbp-88h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-78h] BYREF
  __int64 v23; // [rsp+68h] [rbp-60h]
  _BYTE v24[32]; // [rsp+70h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  *(_QWORD *)dwErrCode = L"CloudAssignedDeviceAssociationTag";
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v17) = 0;
    v23 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"EnterpriseDeviceManagement.Service.AutoPilot.AutoPilotServer",
      0x3Du,
      0x3Cu);
    v18 = 0;
    v4 = Windows::Foundation::ActivateInstance<EnterpriseDeviceManagement::Service::AutoPilot::IAutoPilotUtil>(
           v23,
           &v18);
    v5 = v4;
    if ( v4 >= 0 )
    {
      v20 = 0;
      string = 0;
      v6 = v18;
      v7 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v18 + 336LL);
      Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v20);
      v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v24, dwErrCode);
      v9 = v7(v6, *(_QWORD *)(v8 + 24), &v20);
      v12 = v9;
      if ( v9 >= 0 )
      {
        v13 = string;
        if ( string )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)dwErrCode);
          WindowsDeleteString(v13);
          if ( !LOBYTE(dwErrCode[0]) )
            SetLastError(dwErrCode[1]);
        }
        string = 0;
        v14 = v20;
        v15 = wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(v20, v10, v11, &v17);
        if ( v15 >= 0 )
          v15 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), HSTRING *))(*v14)[8])(
                  v14,
                  &string);
        if ( v15 >= 0 )
        {
          if ( (_BYTE)v17 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xC43,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\utils.cpp",
              (const char *)0x800705B4LL,
              v17);
            Windows::Internal::String::~String(&string);
            Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v20);
            v23 = 0;
            wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v18);
            return 2147943860LL;
          }
          else
          {
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
              a2,
              StringRawBuffer);
            Windows::Internal::String::~String(&string);
            Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v20);
            v23 = 0;
            wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v18);
            return 0;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC41,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\utils.cpp",
            (const char *)(unsigned int)v15,
            v17);
          Windows::Internal::String::~String(&string);
          Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v20);
          v23 = 0;
          wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v18);
          return (unsigned int)v15;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC3F,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\utils.cpp",
          (const char *)(unsigned int)v9,
          v17);
        Windows::Internal::String::~String(&string);
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v20);
        v23 = 0;
        wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v18);
        return v12;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC38,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\utils.cpp",
        (const char *)(unsigned int)v4,
        v17);
      v23 = 0;
      wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v18);
      return v5;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC31,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\utils.cpp",
      (const char *)0x80004001LL,
      v17);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x1800450bc  push    rbx
0x1800450be  push    rsi
0x1800450bf  push    rdi
0x1800450c0  push    r14
0x1800450c2  sub     rsp, 0A8h
0x1800450c9  mov     rax, cs:__security_cookie
0x1800450d0  xor     rax, rsp
0x1800450d3  mov     [rsp+0C8h+var_38], rax
0x1800450db  mov     rsi, rdx
0x1800450de  lea     rax, aCloudassignedd; "CloudAssignedDeviceAssociationTag"
0x1800450e5  mov     qword ptr [rsp+0C8h+dwErrCode], rax
0x1800450ea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1800450f1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1800450f6  xor     r14d, r14d
0x1800450f9  test    al, al
0x1800450fb  jnz     short loc_180045125
0x1800450fd  mov     rcx, [rsp+0C8h]; this
0x180045105  mov     ebx, 80004001h
0x18004510a  mov     r9d, ebx; char *
0x18004510d  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180045114  mov     edx, 0C31h; void *
0x180045119  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004511e  mov     eax, ebx
0x180045120  jmp     loc_180045390
0x180045125  mov     byte ptr [rsp+0C8h+var_A8], r14b; int
0x18004512a  mov     [rsp+0C8h+var_A0], r14
0x18004512f  mov     [rsp+0C8h+var_60], r14
0x180045134  mov     r9d, 3Ch ; '<'; unsigned int
0x18004513a  lea     r8d, [r9+1]; unsigned int
0x18004513e  lea     rdx, ?RuntimeClass_EnterpriseDeviceManagement_Service_AutoPilot_AutoPilotServer@@3QBGB; "EnterpriseDeviceManagement.Service.Auto"...
0x180045145  lea     rcx, [rsp+0C8h+hstringHeader]; hstringHeader
0x18004514a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004514f  nop
0x180045150  mov     rcx, [rsp+0C8h+var_A0]
0x180045155  mov     [rsp+0C8h+var_A0], r14
0x18004515a  test    rcx, rcx
0x18004515d  jz      short loc_18004516C
0x18004515f  mov     rax, [rcx]
0x180045162  mov     rax, [rax+10h]
0x180045166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004516b  nop
0x18004516c  lea     rdx, [rsp+0C8h+var_A0]
0x180045171  mov     rcx, [rsp+0C8h+var_60]
0x180045176  call    ??$ActivateInstance@UIAutoPilotUtil@AutoPilot@Service@EnterpriseDeviceManagement@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIAutoPilotUtil@AutoPilot@Service@EnterpriseDeviceManagement@@@Z; Windows::Foundation::ActivateInstance<EnterpriseDeviceManagement::Service::AutoPilot::IAutoPilotUtil>(HSTRING__ *,EnterpriseDeviceManagement::Service::AutoPilot::IAutoPilotUtil * *)
0x18004517b  mov     ebx, eax
0x18004517d  test    eax, eax
0x18004517f  jns     short loc_1800451B4
0x180045181  mov     rcx, [rsp+0C8h]; this
0x180045189  mov     r9d, eax; char *
0x18004518c  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180045193  mov     edx, 0C38h; void *
0x180045198  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004519d  nop
0x18004519e  mov     [rsp+0C8h+var_60], r14
0x1800451a3  lea     rcx, [rsp+0C8h+var_A0]
0x1800451a8  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x1800451ad  mov     eax, ebx
0x1800451af  jmp     loc_180045390
0x1800451b4  mov     [rsp+0C8h+var_90], r14
0x1800451b9  mov     [rsp+0C8h+string], r14
0x1800451be  mov     rdi, [rsp+0C8h+var_A0]
0x1800451c3  mov     rax, [rdi]
0x1800451c6  mov     rbx, [rax+150h]
0x1800451cd  lea     rcx, [rsp+0C8h+var_90]
0x1800451d2  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x1800451d7  lea     rdx, [rsp+0C8h+dwErrCode]
0x1800451dc  lea     rcx, [rsp+0C8h+var_58]
0x1800451e1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800451e6  nop
0x1800451e7  lea     r8, [rsp+0C8h+var_90]
0x1800451ec  mov     rdx, [rax+18h]
0x1800451f0  mov     rcx, rdi
0x1800451f3  mov     rax, rbx
0x1800451f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800451fb  mov     ebx, eax
0x1800451fd  test    eax, eax
0x1800451ff  jns     short loc_18004524A
0x180045201  mov     rcx, [rsp+0C8h]; this
0x180045209  mov     r9d, eax; char *
0x18004520c  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180045213  mov     edx, 0C3Fh; void *
0x180045218  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004521d  nop
0x18004521e  lea     rcx, [rsp+0C8h+string]; this
0x180045223  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180045228  nop
0x180045229  lea     rcx, [rsp+0C8h+var_90]
0x18004522e  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180045233  nop
0x180045234  mov     [rsp+0C8h+var_60], r14
0x180045239  lea     rcx, [rsp+0C8h+var_A0]
0x18004523e  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180045243  mov     eax, ebx
0x180045245  jmp     loc_180045390
0x18004524a  mov     rbx, [rsp+0C8h+string]
0x18004524f  test    rbx, rbx
0x180045252  jz      short loc_180045278
0x180045254  lea     rcx, [rsp+0C8h+dwErrCode]; this
0x180045259  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18004525e  mov     rcx, rbx; string
0x180045261  call    cs:__imp_WindowsDeleteString
0x180045267  cmp     byte ptr [rsp+0C8h+dwErrCode], r14b
0x18004526c  jnz     short loc_180045278
0x18004526e  mov     ecx, [rsp+0C8h+dwErrCode+4]; dwErrCode
0x180045272  call    cs:__imp_SetLastError
0x180045278  mov     [rsp+0C8h+string], r14
0x18004527d  mov     rdi, [rsp+0C8h+var_90]
0x180045282  lea     r9, [rsp+0C8h+var_A8]
0x180045287  mov     rcx, rdi
0x18004528a  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x18004528f  mov     ebx, eax
0x180045291  test    eax, eax
0x180045293  js      short loc_1800452AB
0x180045295  mov     rax, [rdi]
0x180045298  lea     rdx, [rsp+0C8h+string]
0x18004529d  mov     rcx, rdi
0x1800452a0  mov     rax, [rax+40h]
0x1800452a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800452a9  mov     ebx, eax
0x1800452ab  test    ebx, ebx
0x1800452ad  jns     short loc_1800452F8
0x1800452af  mov     rcx, [rsp+0C8h]; this
0x1800452b7  mov     r9d, ebx; char *
0x1800452ba  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800452c1  mov     edx, 0C41h; void *
0x1800452c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800452cb  nop
0x1800452cc  lea     rcx, [rsp+0C8h+string]; this
0x1800452d1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800452d6  nop
0x1800452d7  lea     rcx, [rsp+0C8h+var_90]
0x1800452dc  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x1800452e1  nop
0x1800452e2  mov     [rsp+0C8h+var_60], r14
0x1800452e7  lea     rcx, [rsp+0C8h+var_A0]
0x1800452ec  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x1800452f1  mov     eax, ebx
0x1800452f3  jmp     loc_180045390
0x1800452f8  cmp     byte ptr [rsp+0C8h+var_A8], r14b
0x1800452fd  jz      short loc_18004534A
0x1800452ff  mov     rcx, [rsp+0C8h]; this
0x180045307  mov     ebx, 800705B4h
0x18004530c  mov     r9d, ebx; char *
0x18004530f  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180045316  mov     edx, 0C43h; void *
0x18004531b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045320  nop
0x180045321  lea     rcx, [rsp+0C8h+string]; this
0x180045326  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18004532b  nop
0x18004532c  lea     rcx, [rsp+0C8h+var_90]
0x180045331  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180045336  nop
0x180045337  mov     [rsp+0C8h+var_60], r14
0x18004533c  lea     rcx, [rsp+0C8h+var_A0]
0x180045341  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180045346  mov     eax, ebx
0x180045348  jmp     short loc_180045390
0x18004534a  xor     edx, edx; length
0x18004534c  mov     rcx, [rsp+0C8h+string]; string
0x180045351  call    cs:__imp_WindowsGetStringRawBuffer
0x180045357  mov     rdx, rax
0x18004535a  mov     rcx, rsi
0x18004535d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180045362  nop
0x180045363  lea     rcx, [rsp+0C8h+string]; this
0x180045368  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18004536d  nop
0x18004536e  lea     rcx, [rsp+0C8h+var_90]
0x180045373  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180045378  nop
0x180045379  mov     [rsp+0C8h+var_60], r14
0x18004537e  lea     rcx, [rsp+0C8h+var_A0]
0x180045383  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180045388  xor     eax, eax
0x18004538a  jmp     short loc_180045390
0x18004538c  mov     eax, dword ptr [rsp+0C8h+var_A0]
0x180045390  mov     rcx, [rsp+0C8h+var_38]
0x180045398  xor     rcx, rsp; StackCookie
0x18004539b  call    __security_check_cookie
0x1800453a0  add     rsp, 0A8h
0x1800453a7  pop     r14
0x1800453a9  pop     rdi
0x1800453aa  pop     rsi
0x1800453ab  pop     rbx
0x1800453ac  retn
```
