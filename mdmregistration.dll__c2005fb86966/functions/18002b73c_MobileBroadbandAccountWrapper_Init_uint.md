# MobileBroadbandAccountWrapper::Init(uint *)

- ea: `0x18002b73c`
- end: `0x18002ba12`
- name: `?Init@MobileBroadbandAccountWrapper@@QEAAJPEAI@Z`
- size: `726`
- prototype: `__int64 __fastcall(MobileBroadbandAccountWrapper *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022e74`

## callees

- `0x1800026d0`
- `0x180021ef0`
- `0x18002b73c`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b874`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002b874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002b79e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002b79e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b855`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002b855`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b818`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b9b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b9c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b9db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b818`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b9b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b9c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b9db`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b7f3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b8ac`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b7f3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002b8ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall MobileBroadbandAccountWrapper::Init(MobileBroadbandAccountWrapper *this, unsigned int *a2)
{
  HSTRING v4; // rbx
  HRESULT ActivationFactory; // edi
  __int64 v6; // rsi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rdi
  __int64 v8; // rsi
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v14; // [rsp+20h] [rbp-60h] BYREF
  __int64 v15; // [rsp+28h] [rbp-58h] BYREF
  __int64 v16; // [rsp+30h] [rbp-50h] BYREF
  HSTRING v17; // [rsp+38h] [rbp-48h] BYREF
  HSTRING string; // [rsp+40h] [rbp-40h] BYREF
  HSTRING v19; // [rsp+48h] [rbp-38h]
  __int64 v20; // [rsp+50h] [rbp-30h]
  HSTRING v21; // [rsp+58h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-20h] BYREF

  v20 = 0;
  v17 = 0;
  v4 = 0;
  v19 = 0;
  v16 = 0;
  v15 = 0;
  v14 = 0;
  string = 0;
  ActivationFactory = WindowsCreateString(L"Windows.Networking.NetworkOperators.MobileBroadbandModem", 0x38u, &string);
  if ( ActivationFactory >= 0 )
  {
    v4 = string;
    v19 = string;
    WindowsDeleteString(0);
    ActivationFactory = RoGetActivationFactory(v4, &GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8, &v16);
    if ( ActivationFactory >= 0 )
    {
      v6 = v16;
      v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v16 + 48LL);
      WindowsDeleteString(v17);
      v17 = 0;
      ActivationFactory = v7(v6, &v17);
      if ( ActivationFactory >= 0 )
      {
        if ( WindowsCreateStringReference(L"Windows.Devices.Enumeration.DeviceInformation", 0x2Du, &hstringHeader, &v21) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        ActivationFactory = RoGetActivationFactory(v21, &GUID_c17f100e_3a46_4a78_8013_769dc9b97390, &v15);
        if ( ActivationFactory >= 0 )
        {
          ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v15 + 80LL))(
                                v15,
                                v17,
                                &v14);
          if ( ActivationFactory >= 0 )
          {
            v8 = v14;
            v9 = *(_QWORD *)this;
            if ( *(_QWORD *)this )
            {
              *(_QWORD *)this = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
            }
            ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(v8);
            if ( ActivationFactory >= 0 )
            {
              ActivationFactory = (*(__int64 (__fastcall **)(__int64, MobileBroadbandAccountWrapper *))(*(_QWORD *)v8 + 64LL))(
                                    v8,
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
  v10 = v14;
  if ( v14 )
  {
    v14 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( v4 )
    WindowsDeleteString(v4);
  WindowsDeleteString(v17);
  v17 = 0;
  WindowsDeleteString(0);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18002b73c  mov     [rsp-28h+arg_10], rbx
0x18002b741  mov     [rsp-28h+arg_18], rsi
0x18002b746  push    rbp
0x18002b747  push    rdi
0x18002b748  push    r12
0x18002b74a  push    r14
0x18002b74c  push    r15
0x18002b74e  mov     rbp, rsp
0x18002b751  sub     rsp, 80h
0x18002b758  mov     rax, cs:__security_cookie
0x18002b75f  xor     rax, rsp
0x18002b762  mov     [rbp+var_8], rax
0x18002b766  mov     r15, rdx
0x18002b769  mov     r14, rcx
0x18002b76c  xor     r12d, r12d
0x18002b76f  mov     [rbp+var_30], r12
0x18002b773  mov     [rbp+var_48], r12
0x18002b777  mov     ebx, r12d
0x18002b77a  mov     [rbp+var_38], rbx
0x18002b77e  mov     [rbp+var_50], r12
0x18002b782  mov     [rbp+var_58], r12
0x18002b786  mov     [rbp+var_60], r12
0x18002b78a  mov     [rbp+string], r12
0x18002b78e  lea     r8, [rbp+string]; string
0x18002b792  lea     edx, [r12+38h]; length
0x18002b797  lea     rcx, ?RuntimeClass_Windows_Networking_NetworkOperators_MobileBroadbandModem@@3QBGB; "Windows.Networking.NetworkOperators.Mob"...
0x18002b79e  call    cs:__imp_WindowsCreateString
0x18002b7a5  nop     dword ptr [rax+rax+00h]
0x18002b7aa  mov     edi, eax
0x18002b7ac  test    eax, eax
0x18002b7ae  js      loc_18002B962
0x18002b7b4  mov     rbx, [rbp+string]
0x18002b7b8  mov     [rbp+var_38], rbx
0x18002b7bc  xor     ecx, ecx; string
0x18002b7be  call    cs:__imp_WindowsDeleteString
0x18002b7c5  nop     dword ptr [rax+rax+00h]
0x18002b7ca  nop
0x18002b7cb  mov     rcx, [rbp+var_50]
0x18002b7cf  test    rcx, rcx
0x18002b7d2  jz      short loc_18002B7E5
0x18002b7d4  mov     [rbp+var_50], r12
0x18002b7d8  mov     rax, [rcx]
0x18002b7db  mov     rax, [rax+10h]
0x18002b7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7e4  nop
0x18002b7e5  lea     r8, [rbp+var_50]
0x18002b7e9  lea     rdx, _GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8
0x18002b7f0  mov     rcx, rbx
0x18002b7f3  call    cs:__imp_RoGetActivationFactory
0x18002b7fa  nop     dword ptr [rax+rax+00h]
0x18002b7ff  mov     edi, eax
0x18002b801  test    eax, eax
0x18002b803  js      loc_18002B962
0x18002b809  mov     rsi, [rbp+var_50]
0x18002b80d  mov     rax, [rsi]
0x18002b810  mov     rdi, [rax+30h]
0x18002b814  mov     rcx, [rbp+var_48]; string
0x18002b818  call    cs:__imp_WindowsDeleteString
0x18002b81f  nop     dword ptr [rax+rax+00h]
0x18002b824  mov     [rbp+var_48], r12
0x18002b828  lea     rdx, [rbp+var_48]
0x18002b82c  mov     rcx, rsi
0x18002b82f  mov     rax, rdi
0x18002b832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b837  mov     edi, eax
0x18002b839  test    eax, eax
0x18002b83b  js      loc_18002B962
0x18002b841  lea     r9, [rbp+var_28]; string
0x18002b845  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18002b849  mov     edx, 2Dh ; '-'; length
0x18002b84e  lea     rcx, ?RuntimeClass_Windows_Devices_Enumeration_DeviceInformation@@3QBGB; "Windows.Devices.Enumeration.DeviceInfor"...
0x18002b855  call    cs:__imp_WindowsCreateStringReference
0x18002b85c  nop     dword ptr [rax+rax+00h]
0x18002b861  test    eax, eax
0x18002b863  jns     short loc_18002B880
0x18002b865  xor     r9d, r9d; lpArguments
0x18002b868  xor     r8d, r8d; nNumberOfArguments
0x18002b86b  lea     edx, [r9+1]; dwExceptionFlags
0x18002b86f  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002b874  call    cs:__imp_RaiseException
0x18002b87b  nop     dword ptr [rax+rax+00h]
0x18002b880  mov     rdi, [rbp+var_28]
0x18002b884  mov     rcx, [rbp+var_58]
0x18002b888  test    rcx, rcx
0x18002b88b  jz      short loc_18002B89E
0x18002b88d  mov     [rbp+var_58], r12
0x18002b891  mov     rax, [rcx]
0x18002b894  mov     rax, [rax+10h]
0x18002b898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b89d  nop
0x18002b89e  lea     r8, [rbp+var_58]
0x18002b8a2  lea     rdx, _GUID_c17f100e_3a46_4a78_8013_769dc9b97390
0x18002b8a9  mov     rcx, rdi
0x18002b8ac  call    cs:__imp_RoGetActivationFactory
0x18002b8b3  nop     dword ptr [rax+rax+00h]
0x18002b8b8  mov     edi, eax
0x18002b8ba  test    eax, eax
0x18002b8bc  js      loc_18002B962
0x18002b8c2  mov     rdi, [rbp+var_58]
0x18002b8c6  mov     rax, [rdi]
0x18002b8c9  mov     rsi, [rax+50h]
0x18002b8cd  mov     rcx, [rbp+var_60]
0x18002b8d1  test    rcx, rcx
0x18002b8d4  jz      short loc_18002B8E7
0x18002b8d6  mov     [rbp+var_60], r12
0x18002b8da  mov     rdx, [rcx]
0x18002b8dd  mov     rax, [rdx+10h]
0x18002b8e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8e6  nop
0x18002b8e7  lea     r8, [rbp+var_60]
0x18002b8eb  mov     rdx, [rbp+var_48]
0x18002b8ef  mov     rcx, rdi
0x18002b8f2  mov     rax, rsi
0x18002b8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8fa  mov     edi, eax
0x18002b8fc  test    eax, eax
0x18002b8fe  js      short loc_18002B962
0x18002b900  mov     rsi, [rbp+var_60]
0x18002b904  mov     rcx, [r14]
0x18002b907  test    rcx, rcx
0x18002b90a  jz      short loc_18002B91C
0x18002b90c  mov     [r14], r12
0x18002b90f  mov     rax, [rcx]
0x18002b912  mov     rax, [rax+10h]
0x18002b916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b91b  nop
0x18002b91c  mov     rcx, rsi
0x18002b91f  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)
0x18002b924  mov     edi, eax
0x18002b926  test    eax, eax
0x18002b928  js      short loc_18002B962
0x18002b92a  mov     rax, [rsi]
0x18002b92d  mov     rdx, r14
0x18002b930  mov     rcx, rsi
0x18002b933  mov     rax, [rax+40h]
0x18002b937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b93c  mov     edi, eax
0x18002b93e  test    eax, eax
0x18002b940  js      short loc_18002B962
0x18002b942  mov     rcx, [r14]
0x18002b945  mov     rax, [rcx]
0x18002b948  lea     rdx, [r14+10h]
0x18002b94c  mov     rax, [rax+38h]
0x18002b950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b955  mov     edi, eax
0x18002b957  test    eax, eax
0x18002b959  js      short loc_18002B962
0x18002b95b  mov     eax, [r14+10h]
0x18002b95f  mov     [r15], eax
0x18002b962  mov     rcx, [rbp+var_60]
0x18002b966  test    rcx, rcx
0x18002b969  jz      short loc_18002B97C
0x18002b96b  mov     [rbp+var_60], r12
0x18002b96f  mov     rax, [rcx]
0x18002b972  mov     rax, [rax+10h]
0x18002b976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b97b  nop
0x18002b97c  mov     rcx, [rbp+var_58]
0x18002b980  test    rcx, rcx
0x18002b983  jz      short loc_18002B996
0x18002b985  mov     [rbp+var_58], r12
0x18002b989  mov     rax, [rcx]
0x18002b98c  mov     rax, [rax+10h]
0x18002b990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b995  nop
0x18002b996  mov     rcx, [rbp+var_50]
0x18002b99a  test    rcx, rcx
0x18002b99d  jz      short loc_18002B9B0
0x18002b99f  mov     [rbp+var_50], r12
0x18002b9a3  mov     rax, [rcx]
0x18002b9a6  mov     rax, [rax+10h]
0x18002b9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9af  nop
0x18002b9b0  test    rbx, rbx
0x18002b9b3  jz      short loc_18002B9C5
0x18002b9b5  mov     rcx, rbx; string
0x18002b9b8  call    cs:__imp_WindowsDeleteString
0x18002b9bf  nop     dword ptr [rax+rax+00h]
0x18002b9c4  nop
0x18002b9c5  mov     rcx, [rbp+var_48]; string
0x18002b9c9  call    cs:__imp_WindowsDeleteString
0x18002b9d0  nop     dword ptr [rax+rax+00h]
0x18002b9d5  mov     [rbp+var_48], r12
0x18002b9d9  xor     ecx, ecx; string
0x18002b9db  call    cs:__imp_WindowsDeleteString
0x18002b9e2  nop     dword ptr [rax+rax+00h]
0x18002b9e7  mov     eax, edi
0x18002b9e9  mov     rcx, [rbp+var_8]
0x18002b9ed  xor     rcx, rsp; StackCookie
0x18002b9f0  call    __security_check_cookie
0x18002b9f5  lea     r11, [rsp+80h+var_s0]
0x18002b9fd  mov     rbx, [r11+40h]
0x18002ba01  mov     rsi, [r11+48h]
0x18002ba05  mov     rsp, r11
0x18002ba08  pop     r15
0x18002ba0a  pop     r14
0x18002ba0c  pop     r12
0x18002ba0e  pop     rdi
0x18002ba0f  pop     rbp
0x18002ba10  retn
```
