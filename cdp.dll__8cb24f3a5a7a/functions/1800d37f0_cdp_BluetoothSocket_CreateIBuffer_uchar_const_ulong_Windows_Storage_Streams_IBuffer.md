# cdp::BluetoothSocket::CreateIBuffer(uchar const *,ulong,Windows::Storage::Streams::IBuffer * *)

- ea: `0x1800d37f0`
- end: `0x1800d3c30`
- name: `?CreateIBuffer@BluetoothSocket@cdp@@AEAAJPEBEKPEAPEAUIBuffer@Streams@Storage@Windows@@@Z`
- size: `1088`
- prototype: `__int64 __fastcall(cdp::BluetoothSocket *__hidden this, const unsigned __int8 *, unsigned int, struct Windows::Storage::Streams::IBuffer **)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800d3210`
- `0x1802d8764`

## callees

- `0x18001ce80`
- `0x1800d37f0`
- `0x180114c58`
- `0x18016cecc`
- `0x1801f6fb0`
- `0x1801fcb36`
- `0x180354010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d388d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d39a8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d388d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800d39a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d3874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d398f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d3874`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800d398f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d39cf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d39cf`

## string_xrefs

- `0x1800d386d`: `Windows.Storage.Streams.InMemoryRandomAccessStream`
- `0x1800d3988`: `Windows.Storage.Streams.DataWriter`
- `0x1800d39f9`: `Failed to get DataWriterFactory`
- `0x1800d3a75`: `Failed to get DataWriter`
- `0x1800d3add`: `Failed to call DataWriter->WriteBytes`
- `0x1800d38c7`: `Failed to get InMemoryRandomAccessStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall cdp::BluetoothSocket::CreateIBuffer(
        cdp::BluetoothSocket *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        struct Windows::Storage::Streams::IBuffer **a4)
{
  int v7; // eax
  __int64 (__fastcall ***v8)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v9)(_QWORD, GUID *, __int64 *); // rdi
  int v10; // eax
  HSTRING v11; // rbx
  int ActivationFactory; // eax
  unsigned int v13; // esi
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, __int64 *); // rbx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // rax
  int v25; // [rsp+28h] [rbp-1D0h]
  __int64 v26; // [rsp+30h] [rbp-1C8h]
  __int64 v27; // [rsp+30h] [rbp-1C8h] BYREF
  int v28; // [rsp+38h] [rbp-1C0h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-1B8h] BYREF
  __int64 v30; // [rsp+48h] [rbp-1B0h] BYREF
  __int64 v31; // [rsp+50h] [rbp-1A8h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+58h] [rbp-1A0h] BYREF
  _BYTE v33[56]; // [rsp+90h] [rbp-168h] BYREF
  _BYTE v34[56]; // [rsp+C8h] [rbp-130h] BYREF
  _BYTE v35[56]; // [rsp+100h] [rbp-F8h] BYREF
  _BYTE v36[56]; // [rsp+138h] [rbp-C0h] BYREF
  _BYTE v37[56]; // [rsp+170h] [rbp-88h] BYREF
  HSTRING string; // [rsp+1A8h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+1B0h] [rbp-48h] BYREF

  if ( !a2 || !a3 || !a4 )
    return 2147942487LL;
  v29 = 0;
  v31 = 0;
  v30 = 0;
  v27 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Storage.Streams.InMemoryRandomAccessStream",
         0x32u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>>(
         string,
         &v29);
  try
  {
    v28 = v7;
    if ( v7 < 0 )
    {
      string = (HSTRING)".\\bluetoothsocket.cpp";
      LODWORD(hstringHeader.Reserved.Reserved1) = 307;
      cdp::MakeException<cdp::hresult_exception,>(
        pExceptionObject,
        &string,
        (unsigned int)v7,
        "Failed to get InMemoryRandomAccessStream");
      throw (cdp::hresult_exception *)pExceptionObject;
    }
    v8 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v29;
    v9 = **v29;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v31);
    v10 = v9(v8, &GUID_905a0fe6_bc53_11df_8c49_001e4fc686da, &v31);
    if ( v10 < 0 )
    {
      string = (HSTRING)".\\bluetoothsocket.cpp";
      LODWORD(hstringHeader.Reserved.Reserved1) = 308;
      cdp::MakeException<cdp::hresult_exception,>(v33, &string, (unsigned int)v10, "Failed to get IOutputStream");
      throw (cdp::hresult_exception *)v33;
    }
    if ( WindowsCreateStringReference(L"Windows.Storage.Streams.DataWriter", 0x22u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v11 = string;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
    ActivationFactory = RoGetActivationFactory(v11, &GUID_338c67c2_8b84_4c2b_9c50_7b8767847a1f, &v30);
    v13 = ActivationFactory;
    v28 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      string = (HSTRING)".\\bluetoothsocket.cpp";
      LODWORD(hstringHeader.Reserved.Reserved1) = 311;
      cdp::MakeException<cdp::hresult_exception,>(
        v34,
        &string,
        (unsigned int)ActivationFactory,
        "Failed to get DataWriterFactory");
      throw (cdp::hresult_exception *)v34;
    }
    v14 = v30;
    v15 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v30 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
    v16 = v15(v14, v31, &v27);
    if ( v16 < 0 )
    {
      string = (HSTRING)".\\bluetoothsocket.cpp";
      LODWORD(hstringHeader.Reserved.Reserved1) = 312;
      cdp::MakeException<cdp::hresult_exception,>(v35, &string, (unsigned int)v16, "Failed to get DataWriter");
      throw (cdp::hresult_exception *)v35;
    }
    v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int8 *))(*(_QWORD *)v27 + 96LL))(v27, a3, a2);
    if ( v17 < 0 )
    {
      string = (HSTRING)".\\bluetoothsocket.cpp";
      LODWORD(hstringHeader.Reserved.Reserved1) = 313;
      cdp::MakeException<cdp::hresult_exception,>(
        v36,
        &string,
        (unsigned int)v17,
        "Failed to call DataWriter->WriteBytes");
      throw (cdp::hresult_exception *)v36;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, struct Windows::Storage::Streams::IBuffer **))(*(_QWORD *)v27 + 248LL))(
            v27,
            a4);
    if ( v18 < 0 )
    {
      string = (HSTRING)".\\bluetoothsocket.cpp";
      LODWORD(hstringHeader.Reserved.Reserved1) = 314;
      cdp::MakeException<cdp::hresult_exception,>(v37, &string, (unsigned int)v18, "Failed to detach IBuffer");
      throw (cdp::hresult_exception *)v37;
    }
    v19 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v29;
    if ( v29 )
    {
      v29 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v22)[2])(v22);
    }
  }
  catch ( ... )
  {
    LODWORD(v24) = GetCurrentThreadId();
    v29 = v24;
    LODWORD(v27) = 316;
    cdp::CatchAllToHR<char const (&)[36],int,unsigned __int64>(
      &v28,
      "{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Couldn't cr"
      "eate an IBuffer from a raw buffer\"}",
      (unsigned int)".\\bluetoothsocket.cpp",
      (const char *)&v27,
      (const char *)&v29,
      v25,
      v26);
  }
  return v13;
}

```

## disassembly

```asm
0x1800d37f0  mov     r11, rsp
0x1800d37f3  mov     [r11+8], rbx
0x1800d37f7  push    rsi
0x1800d37f8  push    rdi
0x1800d37f9  push    r12
0x1800d37fb  push    r14
0x1800d37fd  push    r15
0x1800d37ff  sub     rsp, 1D0h
0x1800d3806  mov     rax, cs:__security_cookie
0x1800d380d  xor     rax, rsp
0x1800d3810  mov     [rsp+1F8h+var_30], rax
0x1800d3818  mov     r14, r9
0x1800d381b  mov     r15d, r8d
0x1800d381e  mov     r12, rdx
0x1800d3821  test    rdx, rdx
0x1800d3824  jz      loc_1800D3C03
0x1800d382a  test    r8d, r8d
0x1800d382d  jz      loc_1800D3C03
0x1800d3833  test    r9, r9
0x1800d3836  jz      loc_1800D3C03
0x1800d383c  mov     [rsp+1F8h+var_1B8], 0
0x1800d3845  mov     [rsp+1F8h+var_1A8], 0
0x1800d384e  mov     [rsp+1F8h+var_1B0], 0
0x1800d3857  mov     [rsp+1F8h+var_1C8], 0
0x1800d3860  lea     r9, [r11-50h]; string
0x1800d3864  lea     r8, [r11-48h]; hstringHeader
0x1800d3868  mov     edx, 32h ; '2'; length
0x1800d386d  lea     rcx, ?RuntimeClass_Windows_Storage_Streams_InMemoryRandomAccessStream@@3QBGB; "Windows.Storage.Streams.InMemoryRandomA"...
0x1800d3874  call    cs:__imp_WindowsCreateStringReference
0x1800d387a  test    eax, eax
0x1800d387c  jns     short loc_1800D3893
0x1800d387e  xor     r9d, r9d; lpArguments
0x1800d3881  xor     r8d, r8d; nNumberOfArguments
0x1800d3884  lea     edx, [r9+1]; dwExceptionFlags
0x1800d3888  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800d388d  call    cs:__imp_RaiseException
0x1800d3893  lea     rdx, [rsp+1F8h+var_1B8]
0x1800d3898  mov     rcx, [rsp+1F8h+string]
0x1800d38a0  call    ??$ActivateInstance@V?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIRandomAccessStream@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IRandomAccessStream>>)
0x1800d38a5  mov     [rsp+1F8h+var_1C0], eax
0x1800d38a9  test    eax, eax
0x1800d38ab  jns     short loc_1800D38F5
0x1800d38ad  lea     rcx, aBluetoothsocke; ".\\bluetoothsocket.cpp"
0x1800d38b4  mov     [rsp+1F8h+string], rcx
0x1800d38bc  mov     dword ptr [rsp+1F8h+hstringHeader.Reserved], 133h
0x1800d38c7  lea     r9, aFailedToGetInm_0; "Failed to get InMemoryRandomAccessStrea"...
0x1800d38ce  mov     r8d, eax
0x1800d38d1  lea     rdx, [rsp+1F8h+string]
0x1800d38d9  lea     rcx, [rsp+1F8h+pExceptionObject]
0x1800d38de  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1800d38e3  lea     rdx, _TI4?AVhresult_exception@cdp@@; pThrowInfo
0x1800d38ea  lea     rcx, [rsp+1F8h+pExceptionObject]; pExceptionObject
0x1800d38ef  call    _CxxThrowException_0
0x1800d38f5  mov     rbx, [rsp+1F8h+var_1B8]
0x1800d38fa  mov     rax, [rbx]
0x1800d38fd  mov     rdi, [rax]
0x1800d3900  lea     rcx, [rsp+1F8h+var_1A8]
0x1800d3905  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800d390a  lea     r8, [rsp+1F8h+var_1A8]
0x1800d390f  lea     rdx, _GUID_905a0fe6_bc53_11df_8c49_001e4fc686da
0x1800d3916  mov     rcx, rbx
0x1800d3919  mov     rax, rdi
0x1800d391c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3921  nop
0x1800d3922  test    eax, eax
0x1800d3924  jns     short loc_1800D3973
0x1800d3926  lea     rcx, aBluetoothsocke; ".\\bluetoothsocket.cpp"
0x1800d392d  mov     [rsp+1F8h+string], rcx
0x1800d3935  mov     dword ptr [rsp+1F8h+hstringHeader.Reserved], 134h
0x1800d3940  lea     r9, aFailedToGetIou_0; "Failed to get IOutputStream"
0x1800d3947  mov     r8d, eax
0x1800d394a  lea     rdx, [rsp+1F8h+string]
0x1800d3952  lea     rcx, [rsp+1F8h+var_168]
0x1800d395a  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1800d395f  lea     rdx, _TI4?AVhresult_exception@cdp@@; pThrowInfo
0x1800d3966  lea     rcx, [rsp+1F8h+var_168]; pExceptionObject
0x1800d396e  call    _CxxThrowException_0
0x1800d3973  lea     r9, [rsp+1F8h+string]; string
0x1800d397b  lea     r8, [rsp+1F8h+hstringHeader]; hstringHeader
0x1800d3983  mov     edx, 22h ; '"'; length
0x1800d3988  lea     rcx, ?RuntimeClass_Windows_Storage_Streams_DataWriter@@3QBGB; "Windows.Storage.Streams.DataWriter"
0x1800d398f  call    cs:__imp_WindowsCreateStringReference
0x1800d3995  test    eax, eax
0x1800d3997  jns     short loc_1800D39AE
0x1800d3999  xor     r9d, r9d; lpArguments
0x1800d399c  xor     r8d, r8d; nNumberOfArguments
0x1800d399f  lea     edx, [r9+1]; dwExceptionFlags
0x1800d39a3  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800d39a8  call    cs:__imp_RaiseException
0x1800d39ae  mov     rbx, [rsp+1F8h+string]
0x1800d39b6  lea     rcx, [rsp+1F8h+var_1B0]
0x1800d39bb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800d39c0  lea     r8, [rsp+1F8h+var_1B0]
0x1800d39c5  lea     rdx, _GUID_338c67c2_8b84_4c2b_9c50_7b8767847a1f
0x1800d39cc  mov     rcx, rbx
0x1800d39cf  call    cs:__imp_RoGetActivationFactory
0x1800d39d5  mov     esi, eax
0x1800d39d7  mov     [rsp+1F8h+var_1C0], eax
0x1800d39db  test    eax, eax
0x1800d39dd  jns     short loc_1800D3A2C
0x1800d39df  lea     rcx, aBluetoothsocke; ".\\bluetoothsocket.cpp"
0x1800d39e6  mov     [rsp+1F8h+string], rcx
0x1800d39ee  mov     dword ptr [rsp+1F8h+hstringHeader.Reserved], 137h
0x1800d39f9  lea     r9, aFailedToGetDat_2; "Failed to get DataWriterFactory"
0x1800d3a00  mov     r8d, eax
0x1800d3a03  lea     rdx, [rsp+1F8h+string]
0x1800d3a0b  lea     rcx, [rsp+1F8h+var_130]
0x1800d3a13  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1800d3a18  lea     rdx, _TI4?AVhresult_exception@cdp@@; pThrowInfo
0x1800d3a1f  lea     rcx, [rsp+1F8h+var_130]; pExceptionObject
0x1800d3a27  call    _CxxThrowException_0
0x1800d3a2c  mov     rdi, [rsp+1F8h+var_1B0]
0x1800d3a31  mov     rax, [rdi]
0x1800d3a34  mov     rbx, [rax+30h]
0x1800d3a38  lea     rcx, [rsp+1F8h+var_1C8]
0x1800d3a3d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800d3a42  lea     r8, [rsp+1F8h+var_1C8]
0x1800d3a47  mov     rdx, [rsp+1F8h+var_1A8]
0x1800d3a4c  mov     rcx, rdi
0x1800d3a4f  mov     rax, rbx
0x1800d3a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3a57  test    eax, eax
0x1800d3a59  jns     short loc_1800D3AA8
0x1800d3a5b  lea     rcx, aBluetoothsocke; ".\\bluetoothsocket.cpp"
0x1800d3a62  mov     [rsp+1F8h+string], rcx
0x1800d3a6a  mov     dword ptr [rsp+1F8h+hstringHeader.Reserved], 138h
0x1800d3a75  lea     r9, aFailedToGetDat; "Failed to get DataWriter"
0x1800d3a7c  mov     r8d, eax
0x1800d3a7f  lea     rdx, [rsp+1F8h+string]
0x1800d3a87  lea     rcx, [rsp+1F8h+var_F8]
0x1800d3a8f  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1800d3a94  lea     rdx, _TI4?AVhresult_exception@cdp@@; pThrowInfo
0x1800d3a9b  lea     rcx, [rsp+1F8h+var_F8]; pExceptionObject
0x1800d3aa3  call    _CxxThrowException_0
0x1800d3aa8  mov     rcx, [rsp+1F8h+var_1C8]
0x1800d3aad  mov     rax, [rcx]
0x1800d3ab0  mov     r8, r12
0x1800d3ab3  mov     edx, r15d
0x1800d3ab6  mov     rax, [rax+60h]
0x1800d3aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3abf  test    eax, eax
0x1800d3ac1  jns     short loc_1800D3B10
0x1800d3ac3  lea     rcx, aBluetoothsocke; ".\\bluetoothsocket.cpp"
0x1800d3aca  mov     [rsp+1F8h+string], rcx
0x1800d3ad2  mov     dword ptr [rsp+1F8h+hstringHeader.Reserved], 139h
0x1800d3add  lea     r9, aFailedToCallDa_0; "Failed to call DataWriter->WriteBytes"
0x1800d3ae4  mov     r8d, eax
0x1800d3ae7  lea     rdx, [rsp+1F8h+string]
0x1800d3aef  lea     rcx, [rsp+1F8h+var_C0]
0x1800d3af7  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1800d3afc  lea     rdx, _TI4?AVhresult_exception@cdp@@; pThrowInfo
0x1800d3b03  lea     rcx, [rsp+1F8h+var_C0]; pExceptionObject
0x1800d3b0b  call    _CxxThrowException_0
0x1800d3b10  mov     rcx, [rsp+1F8h+var_1C8]
0x1800d3b15  mov     rax, [rcx]
0x1800d3b18  mov     rdx, r14
0x1800d3b1b  mov     rax, [rax+0F8h]
0x1800d3b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3b27  test    eax, eax
0x1800d3b29  jns     short loc_1800D3B79
0x1800d3b2b  lea     rcx, aBluetoothsocke; ".\\bluetoothsocket.cpp"
0x1800d3b32  mov     [rsp+1F8h+string], rcx
0x1800d3b3a  mov     dword ptr [rsp+1F8h+hstringHeader.Reserved], 13Ah
0x1800d3b45  lea     r9, aFailedToDetach_0; "Failed to detach IBuffer"
0x1800d3b4c  mov     r8d, eax
0x1800d3b4f  lea     rdx, [rsp+1F8h+string]
0x1800d3b57  lea     rcx, [rsp+1F8h+var_88]
0x1800d3b5f  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1800d3b64  lea     rdx, _TI4?AVhresult_exception@cdp@@; pThrowInfo
0x1800d3b6b  lea     rcx, [rsp+1F8h+var_88]; pExceptionObject
0x1800d3b73  call    _CxxThrowException_0
0x1800d3b79  mov     rcx, [rsp+1F8h+var_1C8]
0x1800d3b7e  test    rcx, rcx
0x1800d3b81  jz      short loc_1800D3B99
0x1800d3b83  mov     [rsp+1F8h+var_1C8], 0
0x1800d3b8c  mov     rax, [rcx]
0x1800d3b8f  mov     rax, [rax+10h]
0x1800d3b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3b98  nop
0x1800d3b99  mov     rcx, [rsp+1F8h+var_1B0]
0x1800d3b9e  test    rcx, rcx
0x1800d3ba1  jz      short loc_1800D3BB9
0x1800d3ba3  mov     [rsp+1F8h+var_1B0], 0
0x1800d3bac  mov     rax, [rcx]
0x1800d3baf  mov     rax, [rax+10h]
0x1800d3bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3bb8  nop
0x1800d3bb9  mov     rcx, [rsp+1F8h+var_1A8]
0x1800d3bbe  test    rcx, rcx
0x1800d3bc1  jz      short loc_1800D3BD9
0x1800d3bc3  mov     [rsp+1F8h+var_1A8], 0
0x1800d3bcc  mov     rax, [rcx]
0x1800d3bcf  mov     rax, [rax+10h]
0x1800d3bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3bd8  nop
0x1800d3bd9  mov     rcx, [rsp+1F8h+var_1B8]
0x1800d3bde  test    rcx, rcx
0x1800d3be1  jz      short loc_1800D3BF9
0x1800d3be3  mov     [rsp+1F8h+var_1B8], 0
0x1800d3bec  mov     rax, [rcx]
0x1800d3bef  mov     rax, [rax+10h]
0x1800d3bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d3bf8  nop
0x1800d3bf9  jmp     short loc_1800D3BFF
0x1800d3bfb  mov     esi, [rsp+1F8h+var_1C0]
0x1800d3bff  mov     eax, esi
0x1800d3c01  jmp     short loc_1800D3C08
0x1800d3c03  mov     eax, 80070057h
0x1800d3c08  mov     rcx, [rsp+1F8h+var_30]
0x1800d3c10  xor     rcx, rsp; StackCookie
0x1800d3c13  call    __security_check_cookie
0x1800d3c18  mov     rbx, [rsp+1F8h+arg_0]
0x1800d3c20  add     rsp, 1D0h
0x1800d3c27  pop     r15
0x1800d3c29  pop     r14
0x1800d3c2b  pop     r12
0x1800d3c2d  pop     rdi
0x1800d3c2e  pop     rsi
0x1800d3c2f  retn
```
