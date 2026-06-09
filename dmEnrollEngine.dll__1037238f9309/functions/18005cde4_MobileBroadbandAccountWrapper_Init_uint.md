# MobileBroadbandAccountWrapper::Init(uint *)

- ea: `0x18005cde4`
- end: `0x18005d015`
- name: `?Init@MobileBroadbandAccountWrapper@@QEAAJPEAI@Z`
- size: `561`
- prototype: `__int64 __fastcall(MobileBroadbandAccountWrapper *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800141d0`

## callees

- `0x18002e1a0`
- `0x18003c41c`
- `0x18003c968`
- `0x180059b98`
- `0x18005cde4`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005cf02`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005cf02`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005ce8f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005cf23`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005ce8f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18005cf23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ce72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ceae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cfd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cfe9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ce72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ceae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cfd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cfe9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005ce58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005ce58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005cee9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005cee9`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall MobileBroadbandAccountWrapper::Init(MobileBroadbandAccountWrapper *this, unsigned int *a2)
{
  int ActivationFactory; // ebx
  HSTRING v5; // rbx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  HSTRING v8; // rbx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING, _QWORD); // rbx
  int (__fastcall ***v11)(_QWORD, GUID *, __int64 *); // rdi
  HRESULT v12; // edx
  __int64 v13; // r8
  HSTRING v15; // [rsp+20h] [rbp-60h] BYREF
  int (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-58h] BYREF
  __int64 v17; // [rsp+30h] [rbp-50h] BYREF
  __int64 v18; // [rsp+38h] [rbp-48h] BYREF
  HSTRING string; // [rsp+40h] [rbp-40h] BYREF
  HSTRING v20[2]; // [rsp+48h] [rbp-38h] BYREF
  HSTRING v21; // [rsp+58h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-20h] BYREF

  v20[1] = 0;
  v15 = 0;
  v20[0] = 0;
  v18 = 0;
  v17 = 0;
  v16 = 0;
  string = 0;
  ActivationFactory = WindowsCreateString(L"Windows.Networking.NetworkOperators.MobileBroadbandModem", 0x38u, &string);
  if ( ActivationFactory >= 0 )
  {
    v5 = string;
    v20[0] = string;
    WindowsDeleteString(0);
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v18);
    ActivationFactory = RoGetActivationFactory(v5, &GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8, &v18);
    if ( ActivationFactory >= 0 )
    {
      v6 = v18;
      v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v18 + 48LL);
      WindowsDeleteString(v15);
      v15 = 0;
      ActivationFactory = v7(v6, &v15);
      if ( ActivationFactory >= 0 )
      {
        if ( WindowsCreateStringReference(L"Windows.Devices.Enumeration.DeviceInformation", 0x2Du, &hstringHeader, &v21) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v8 = v21;
        Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v17);
        ActivationFactory = RoGetActivationFactory(v8, &GUID_c17f100e_3a46_4a78_8013_769dc9b97390, &v17);
        if ( ActivationFactory >= 0 )
        {
          v9 = v17;
          v10 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v17 + 80LL);
          Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v16);
          ActivationFactory = v10(v9, v15, &v16);
          if ( ActivationFactory >= 0 )
          {
            v11 = v16;
            Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(this);
            ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(
                                  v11,
                                  v12,
                                  v13);
            if ( ActivationFactory >= 0 )
            {
              ActivationFactory = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), MobileBroadbandAccountWrapper *))(*v11)[8])(
                                    v11,
                                    this);
              if ( ActivationFactory >= 0 )
              {
                ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)this + 56LL))(
                                      *(_QWORD *)this,
                                      (char *)this + 16);
                if ( ActivationFactory >= 0 )
                  *a2 = *((_DWORD *)this + 4);
              }
            }
          }
        }
      }
    }
  }
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v16);
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v17);
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v18);
  Windows::Internal::String::~String(v20);
  WindowsDeleteString(v15);
  v15 = 0;
  WindowsDeleteString(0);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18005cde4  mov     [rsp-18h+arg_10], rbx
0x18005cde9  mov     [rsp-18h+arg_18], rsi
0x18005cdee  push    rbp
0x18005cdef  push    rdi
0x18005cdf0  push    r14
0x18005cdf2  mov     rbp, rsp
0x18005cdf5  sub     rsp, 80h
0x18005cdfc  mov     rax, cs:__security_cookie
0x18005ce03  xor     rax, rsp
0x18005ce06  mov     [rbp+var_8], rax
0x18005ce0a  mov     r14, rdx
0x18005ce0d  mov     rsi, rcx
0x18005ce10  mov     [rbp+var_30], 0
0x18005ce18  mov     [rbp+var_60], 0
0x18005ce20  mov     [rbp+var_38], 0
0x18005ce28  mov     [rbp+var_48], 0
0x18005ce30  mov     [rbp+var_50], 0
0x18005ce38  mov     [rbp+var_58], 0
0x18005ce40  mov     [rbp+string], 0
0x18005ce48  lea     r8, [rbp+string]; string
0x18005ce4c  mov     edx, 38h ; '8'; length
0x18005ce51  lea     rcx, ?RuntimeClass_Windows_Networking_NetworkOperators_MobileBroadbandModem@@3QBGB; "Windows.Networking.NetworkOperators.Mob"...
0x18005ce58  call    cs:__imp_WindowsCreateString
0x18005ce5e  mov     ebx, eax
0x18005ce60  test    eax, eax
0x18005ce62  js      loc_18005CFAD
0x18005ce68  mov     rbx, [rbp+string]
0x18005ce6c  mov     [rbp+var_38], rbx
0x18005ce70  xor     ecx, ecx; string
0x18005ce72  call    cs:__imp_WindowsDeleteString
0x18005ce78  lea     rcx, [rbp+var_48]
0x18005ce7c  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005ce81  lea     r8, [rbp+var_48]
0x18005ce85  lea     rdx, _GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8
0x18005ce8c  mov     rcx, rbx
0x18005ce8f  call    cs:__imp_RoGetActivationFactory
0x18005ce95  mov     ebx, eax
0x18005ce97  test    eax, eax
0x18005ce99  js      loc_18005CFAD
0x18005ce9f  mov     rdi, [rbp+var_48]
0x18005cea3  mov     rax, [rdi]
0x18005cea6  mov     rbx, [rax+30h]
0x18005ceaa  mov     rcx, [rbp+var_60]; string
0x18005ceae  call    cs:__imp_WindowsDeleteString
0x18005ceb4  mov     [rbp+var_60], 0
0x18005cebc  lea     rdx, [rbp+var_60]
0x18005cec0  mov     rcx, rdi
0x18005cec3  mov     rax, rbx
0x18005cec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cecb  mov     ebx, eax
0x18005cecd  test    eax, eax
0x18005cecf  js      loc_18005CFAD
0x18005ced5  lea     r9, [rbp+var_28]; string
0x18005ced9  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18005cedd  mov     edx, 2Dh ; '-'; length
0x18005cee2  lea     rcx, ?RuntimeClass_Windows_Devices_Enumeration_DeviceInformation@@3QBGB; "Windows.Devices.Enumeration.DeviceInfor"...
0x18005cee9  call    cs:__imp_WindowsCreateStringReference
0x18005ceef  test    eax, eax
0x18005cef1  jns     short loc_18005CF08
0x18005cef3  xor     r9d, r9d; lpArguments
0x18005cef6  xor     r8d, r8d; nNumberOfArguments
0x18005cef9  lea     edx, [r9+1]; dwExceptionFlags
0x18005cefd  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005cf02  call    cs:__imp_RaiseException
0x18005cf08  mov     rbx, [rbp+var_28]
0x18005cf0c  lea     rcx, [rbp+var_50]
0x18005cf10  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005cf15  lea     r8, [rbp+var_50]
0x18005cf19  lea     rdx, _GUID_c17f100e_3a46_4a78_8013_769dc9b97390
0x18005cf20  mov     rcx, rbx
0x18005cf23  call    cs:__imp_RoGetActivationFactory
0x18005cf29  mov     ebx, eax
0x18005cf2b  test    eax, eax
0x18005cf2d  js      short loc_18005CFAD
0x18005cf2f  mov     rdi, [rbp+var_50]
0x18005cf33  mov     rax, [rdi]
0x18005cf36  mov     rbx, [rax+50h]
0x18005cf3a  lea     rcx, [rbp+var_58]
0x18005cf3e  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005cf43  lea     r8, [rbp+var_58]
0x18005cf47  mov     rdx, [rbp+var_60]
0x18005cf4b  mov     rcx, rdi
0x18005cf4e  mov     rax, rbx
0x18005cf51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf56  mov     ebx, eax
0x18005cf58  test    eax, eax
0x18005cf5a  js      short loc_18005CFAD
0x18005cf5c  mov     rdi, [rbp+var_58]
0x18005cf60  mov     rcx, rsi
0x18005cf63  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005cf68  mov     rcx, rdi
0x18005cf6b  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)
0x18005cf70  mov     ebx, eax
0x18005cf72  test    eax, eax
0x18005cf74  js      short loc_18005CFAD
0x18005cf76  mov     rax, [rdi]
0x18005cf79  mov     rdx, rsi
0x18005cf7c  mov     rcx, rdi
0x18005cf7f  mov     rax, [rax+40h]
0x18005cf83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf88  mov     ebx, eax
0x18005cf8a  test    eax, eax
0x18005cf8c  js      short loc_18005CFAD
0x18005cf8e  mov     rcx, [rsi]
0x18005cf91  mov     rax, [rcx]
0x18005cf94  lea     rdx, [rsi+10h]
0x18005cf98  mov     rax, [rax+38h]
0x18005cf9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cfa1  mov     ebx, eax
0x18005cfa3  test    eax, eax
0x18005cfa5  js      short loc_18005CFAD
0x18005cfa7  mov     eax, [rsi+10h]
0x18005cfaa  mov     [r14], eax
0x18005cfad  lea     rcx, [rbp+var_58]
0x18005cfb1  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005cfb6  nop
0x18005cfb7  lea     rcx, [rbp+var_50]
0x18005cfbb  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005cfc0  nop
0x18005cfc1  lea     rcx, [rbp+var_48]
0x18005cfc5  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18005cfca  nop
0x18005cfcb  lea     rcx, [rbp+var_38]; this
0x18005cfcf  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18005cfd4  nop
0x18005cfd5  mov     rcx, [rbp+var_60]; string
0x18005cfd9  call    cs:__imp_WindowsDeleteString
0x18005cfdf  mov     [rbp+var_60], 0
0x18005cfe7  xor     ecx, ecx; string
0x18005cfe9  call    cs:__imp_WindowsDeleteString
0x18005cfef  mov     eax, ebx
0x18005cff1  mov     rcx, [rbp+var_8]
0x18005cff5  xor     rcx, rsp; StackCookie
0x18005cff8  call    __security_check_cookie
0x18005cffd  lea     r11, [rsp+80h+var_s0]
0x18005d005  mov     rbx, [r11+30h]
0x18005d009  mov     rsi, [r11+38h]
0x18005d00d  mov     rsp, r11
0x18005d010  pop     r14
0x18005d012  pop     rdi
0x18005d013  pop     rbp
0x18005d014  retn
```
