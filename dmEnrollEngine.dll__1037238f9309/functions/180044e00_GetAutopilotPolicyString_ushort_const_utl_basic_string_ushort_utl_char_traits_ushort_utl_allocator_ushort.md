# GetAutopilotPolicyString(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)

- ea: `0x180044e00`
- end: `0x1800450b6`
- name: `?GetAutopilotPolicyString@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z`
- size: `694`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
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
- `0x180044e00`
- `0x18004c364`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044f73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180044f73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045052`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180045052`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044f62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044f62`

## string_xrefs

- `0x180044e43`: `EnterpriseDeviceManagement.Service.AutoPilot.AutoPilotServer`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall GetAutopilotPolicyString(__int64 a1, __int64 a2)
{
  int v3; // eax
  unsigned int v4; // ebx
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
  int v17; // [rsp+20h] [rbp-88h] BYREF
  __int64 v18; // [rsp+28h] [rbp-80h] BYREF
  HSTRING string; // [rsp+30h] [rbp-78h] BYREF
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-70h] BYREF
  __int64 v21; // [rsp+40h] [rbp-68h] BYREF
  HSTRING_HEADER v22; // [rsp+48h] [rbp-60h] BYREF
  __int64 v23; // [rsp+60h] [rbp-48h]
  _BYTE v24[32]; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v21 = a1;
  LOBYTE(v17) = 0;
  v23 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v22,
    L"EnterpriseDeviceManagement.Service.AutoPilot.AutoPilotServer",
    0x3Du,
    0x3Cu);
  v18 = 0;
  v3 = Windows::Foundation::ActivateInstance<EnterpriseDeviceManagement::Service::AutoPilot::IAutoPilotUtil>(v23, &v18);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v20 = 0;
    string = 0;
    v6 = v18;
    v7 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v18 + 56LL);
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v20);
    v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v24, &v21);
    v9 = v7(v6, *(_QWORD *)(v8 + 24), &v20);
    v12 = v9;
    if ( v9 >= 0 )
    {
      v13 = string;
      if ( string )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v21);
        WindowsDeleteString(v13);
        if ( !(_BYTE)v21 )
          SetLastError(HIDWORD(v21));
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
            (void *)0xC27,
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
          (void *)0xC26,
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
        (void *)0xC25,
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
      (void *)0xC20,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\utils.cpp",
      (const char *)(unsigned int)v3,
      v17);
    v23 = 0;
    wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(&v18);
    return v4;
  }
}

```

## disassembly

```asm
0x180044e00  mov     r11, rsp
0x180044e03  mov     [r11+18h], rbx
0x180044e07  push    rsi
0x180044e08  push    rdi
0x180044e09  push    r14
0x180044e0b  sub     rsp, 90h
0x180044e12  mov     rax, cs:__security_cookie
0x180044e19  xor     rax, rsp
0x180044e1c  mov     [rsp+0A8h+var_20], rax
0x180044e24  mov     rsi, rdx
0x180044e27  mov     [r11-68h], rcx
0x180044e2b  xor     r14d, r14d
0x180044e2e  mov     byte ptr [rsp+0A8h+var_88], r14b; int
0x180044e33  mov     [r11-80h], r14
0x180044e37  mov     [r11-48h], r14
0x180044e3b  lea     r9d, [r14+3Ch]; unsigned int
0x180044e3f  lea     r8d, [r14+3Dh]; unsigned int
0x180044e43  lea     rdx, ?RuntimeClass_EnterpriseDeviceManagement_Service_AutoPilot_AutoPilotServer@@3QBGB; "EnterpriseDeviceManagement.Service.Auto"...
0x180044e4a  lea     rcx, [r11-60h]; hstringHeader
0x180044e4e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180044e53  nop
0x180044e54  mov     rcx, [rsp+0A8h+var_80]
0x180044e59  mov     [rsp+0A8h+var_80], r14
0x180044e5e  test    rcx, rcx
0x180044e61  jz      short loc_180044E70
0x180044e63  mov     rax, [rcx]
0x180044e66  mov     rax, [rax+10h]
0x180044e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044e6f  nop
0x180044e70  lea     rdx, [rsp+0A8h+var_80]
0x180044e75  mov     rcx, [rsp+0A8h+var_48]
0x180044e7a  call    ??$ActivateInstance@UIAutoPilotUtil@AutoPilot@Service@EnterpriseDeviceManagement@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIAutoPilotUtil@AutoPilot@Service@EnterpriseDeviceManagement@@@Z; Windows::Foundation::ActivateInstance<EnterpriseDeviceManagement::Service::AutoPilot::IAutoPilotUtil>(HSTRING__ *,EnterpriseDeviceManagement::Service::AutoPilot::IAutoPilotUtil * *)
0x180044e7f  mov     ebx, eax
0x180044e81  test    eax, eax
0x180044e83  jns     short loc_180044EB8
0x180044e85  mov     rcx, [rsp+0A8h]; this
0x180044e8d  mov     r9d, eax; char *
0x180044e90  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180044e97  mov     edx, 0C20h; void *
0x180044e9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044ea1  nop
0x180044ea2  mov     [rsp+0A8h+var_48], r14
0x180044ea7  lea     rcx, [rsp+0A8h+var_80]
0x180044eac  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180044eb1  mov     eax, ebx
0x180044eb3  jmp     loc_180045091
0x180044eb8  mov     [rsp+0A8h+var_70], r14
0x180044ebd  mov     [rsp+0A8h+string], r14
0x180044ec2  mov     rdi, [rsp+0A8h+var_80]
0x180044ec7  mov     rax, [rdi]
0x180044eca  mov     rbx, [rax+38h]
0x180044ece  lea     rcx, [rsp+0A8h+var_70]
0x180044ed3  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180044ed8  lea     rdx, [rsp+0A8h+var_68]
0x180044edd  lea     rcx, [rsp+0A8h+var_40]
0x180044ee2  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180044ee7  nop
0x180044ee8  lea     r8, [rsp+0A8h+var_70]
0x180044eed  mov     rdx, [rax+18h]
0x180044ef1  mov     rcx, rdi
0x180044ef4  mov     rax, rbx
0x180044ef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044efc  mov     ebx, eax
0x180044efe  test    eax, eax
0x180044f00  jns     short loc_180044F4B
0x180044f02  mov     rcx, [rsp+0A8h]; this
0x180044f0a  mov     r9d, eax; char *
0x180044f0d  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180044f14  mov     edx, 0C25h; void *
0x180044f19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044f1e  nop
0x180044f1f  lea     rcx, [rsp+0A8h+string]; this
0x180044f24  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180044f29  nop
0x180044f2a  lea     rcx, [rsp+0A8h+var_70]
0x180044f2f  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180044f34  nop
0x180044f35  mov     [rsp+0A8h+var_48], r14
0x180044f3a  lea     rcx, [rsp+0A8h+var_80]
0x180044f3f  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180044f44  mov     eax, ebx
0x180044f46  jmp     loc_180045091
0x180044f4b  mov     rbx, [rsp+0A8h+string]
0x180044f50  test    rbx, rbx
0x180044f53  jz      short loc_180044F79
0x180044f55  lea     rcx, [rsp+0A8h+var_68]; this
0x180044f5a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180044f5f  mov     rcx, rbx; string
0x180044f62  call    cs:__imp_WindowsDeleteString
0x180044f68  cmp     [rsp+0A8h+var_68], r14b
0x180044f6d  jnz     short loc_180044F79
0x180044f6f  mov     ecx, [rsp+0A8h+dwErrCode]; dwErrCode
0x180044f73  call    cs:__imp_SetLastError
0x180044f79  mov     [rsp+0A8h+string], r14
0x180044f7e  mov     rdi, [rsp+0A8h+var_70]
0x180044f83  lea     r9, [rsp+0A8h+var_88]
0x180044f88  mov     rcx, rdi
0x180044f8b  call    ??$WaitForCompletion@PEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@@details@wil@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@KPEA_N@Z; wil::details::WaitForCompletion<Windows::Foundation::IAsyncOperation<HSTRING__ *> *>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,ulong,bool *)
0x180044f90  mov     ebx, eax
0x180044f92  test    eax, eax
0x180044f94  js      short loc_180044FAC
0x180044f96  mov     rax, [rdi]
0x180044f99  lea     rdx, [rsp+0A8h+string]
0x180044f9e  mov     rcx, rdi
0x180044fa1  mov     rax, [rax+40h]
0x180044fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044faa  mov     ebx, eax
0x180044fac  test    ebx, ebx
0x180044fae  jns     short loc_180044FF9
0x180044fb0  mov     rcx, [rsp+0A8h]; this
0x180044fb8  mov     r9d, ebx; char *
0x180044fbb  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180044fc2  mov     edx, 0C26h; void *
0x180044fc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044fcc  nop
0x180044fcd  lea     rcx, [rsp+0A8h+string]; this
0x180044fd2  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180044fd7  nop
0x180044fd8  lea     rcx, [rsp+0A8h+var_70]
0x180044fdd  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180044fe2  nop
0x180044fe3  mov     [rsp+0A8h+var_48], r14
0x180044fe8  lea     rcx, [rsp+0A8h+var_80]
0x180044fed  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180044ff2  mov     eax, ebx
0x180044ff4  jmp     loc_180045091
0x180044ff9  cmp     byte ptr [rsp+0A8h+var_88], r14b
0x180044ffe  jz      short loc_18004504B
0x180045000  mov     rcx, [rsp+0A8h]; this
0x180045008  mov     ebx, 800705B4h
0x18004500d  mov     r9d, ebx; char *
0x180045010  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180045017  mov     edx, 0C27h; void *
0x18004501c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045021  nop
0x180045022  lea     rcx, [rsp+0A8h+string]; this
0x180045027  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18004502c  nop
0x18004502d  lea     rcx, [rsp+0A8h+var_70]
0x180045032  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180045037  nop
0x180045038  mov     [rsp+0A8h+var_48], r14
0x18004503d  lea     rcx, [rsp+0A8h+var_80]
0x180045042  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180045047  mov     eax, ebx
0x180045049  jmp     short loc_180045091
0x18004504b  xor     edx, edx; length
0x18004504d  mov     rcx, [rsp+0A8h+string]; string
0x180045052  call    cs:__imp_WindowsGetStringRawBuffer
0x180045058  mov     rdx, rax
0x18004505b  mov     rcx, rsi
0x18004505e  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180045063  nop
0x180045064  lea     rcx, [rsp+0A8h+string]; this
0x180045069  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18004506e  nop
0x18004506f  lea     rcx, [rsp+0A8h+var_70]
0x180045074  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x180045079  nop
0x18004507a  mov     [rsp+0A8h+var_48], r14
0x18004507f  lea     rcx, [rsp+0A8h+var_80]
0x180045084  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180045089  xor     eax, eax
0x18004508b  jmp     short loc_180045091
0x18004508d  mov     eax, dword ptr [rsp+0A8h+var_80]
0x180045091  mov     rcx, [rsp+0A8h+var_20]
0x180045099  xor     rcx, rsp; StackCookie
0x18004509c  call    __security_check_cookie
0x1800450a1  mov     rbx, [rsp+0A8h+arg_10]
0x1800450a9  add     rsp, 90h
0x1800450b0  pop     r14
0x1800450b2  pop     rdi
0x1800450b3  pop     rsi
0x1800450b4  retn
```
