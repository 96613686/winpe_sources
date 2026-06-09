# ConciergeSettingUSBProvider::GetSettingsInString(ushort * *)

- ea: `0x1800add70`
- end: `0x1800adfac`
- name: `?GetSettingsInString@ConciergeSettingUSBProvider@@UEAAJPEAPEAG@Z`
- size: `572`
- prototype: `__int64 __fastcall(ConciergeSettingUSBProvider *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003470`
- `0x18000b358`
- `0x18001ad08`
- `0x18003e430`
- `0x18003e478`
- `0x18003e56c`
- `0x180040898`
- `0x1800418d8`
- `0x180043c58`
- `0x180048d38`
- `0x1800adbb0`
- `0x1800add70`
- `0x1800adfb4`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800adddf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800adddf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800addc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800addc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800adeef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800adeef`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800addf6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800addf6`

## string_xrefs

- `0x1800addbf`: `Windows.Storage.PathIO`
- `0x1800ade5e`: `Concierge.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=1
__int64 __fastcall ConciergeSettingUSBProvider::GetSettingsInString(
        ConciergeSettingUSBProvider *this,
        unsigned __int16 **a2)
{
  int ActivationFactory; // eax
  __int64 i; // rbx
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, PVOID, __int64 *); // r14
  __int64 v8; // rax
  char v9; // r8
  HSTRING_HEADER *v10; // rax
  __int64 v11; // rdi
  const wchar_t *StringRawBuffer; // rax
  __int64 v13; // rdx
  unsigned __int64 v14; // rcx
  size_t v15; // r9
  int v16; // eax
  __int64 v17; // [rsp+20h] [rbp-88h]
  int v18; // [rsp+20h] [rbp-88h]
  HSTRING v19; // [rsp+30h] [rbp-78h] BYREF
  __int64 v20; // [rsp+38h] [rbp-70h] BYREF
  __int64 v21; // [rsp+40h] [rbp-68h] BYREF
  _QWORD v22[3]; // [rsp+48h] [rbp-60h] BYREF
  HSTRING string; // [rsp+60h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  *a2 = 0;
  UsbDriveHelper::GetUsbDrives(v22);
  v21 = 0;
  if ( WindowsCreateStringReference(L"Windows.Storage.PathIO", 0x16u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_0f2f3758_8ec7_4381_922b_8f6c07d288f3, &v21);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x8A,
      (unsigned int)"shell\\oobe\\machine\\concierge\\lib\\conciergesettingusbprovider.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v17);
  for ( i = v22[0]; ; i += 32 )
  {
    if ( i == v22[1] )
    {
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v21);
      std::vector<std::wstring>::_Tidy(v22);
      return 2147943568LL;
    }
    v20 = 0;
    v6 = v21;
    v7 = *(int (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v21 + 48LL);
    v20 = 0;
    v8 = std::wstring::append(i, L"Concierge.json");
    v19 = (HSTRING)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v8);
    v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            (HSTRING_HEADER *)&string,
            (const WCHAR **)&v19,
            v9);
    if ( v7(v6, v10[1].Reserved.Reserved1, &v20) >= 0 )
      break;
LABEL_17:
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v20);
  }
  v19 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &v19,
    0);
  v11 = v20;
  if ( (int)WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(v20) < 0
    || (*(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v11 + 64LL))(v11, &v19) < 0 )
  {
    Windows::Internal::String::~String((Windows::Internal::String *)&v19);
    goto LABEL_17;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(v19, 0);
  v15 = -1;
  do
    ++v15;
  while ( StringRawBuffer[v15] );
  v16 = _AllocStringWorker<CTCoAllocPolicy>(v14, v13, StringRawBuffer, v15, v17, (void **)a2);
  if ( v16 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"shell\\oobe\\machine\\concierge\\lib\\conciergesettingusbprovider.cpp",
      (const char *)(unsigned int)v16,
      v18);
  Windows::Internal::String::~String((Windows::Internal::String *)&v19);
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v20);
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v21);
  std::vector<std::wstring>::_Tidy(v22);
  return 0;
}

```

## disassembly

```asm
0x1800add70  mov     [rsp+arg_0], rbx
0x1800add75  mov     [rsp+arg_10], rsi
0x1800add7a  push    rdi
0x1800add7b  push    r14
0x1800add7d  push    r15
0x1800add7f  sub     rsp, 90h
0x1800add86  mov     rax, cs:__security_cookie
0x1800add8d  xor     rax, rsp
0x1800add90  mov     [rsp+0A8h+var_28], rax
0x1800add98  mov     rsi, rdx
0x1800add9b  xor     r15d, r15d
0x1800add9e  mov     [rdx], r15
0x1800adda1  lea     rcx, [rsp+0A8h+var_60]
0x1800adda6  call    ?GetUsbDrives@UsbDriveHelper@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ; UsbDriveHelper::GetUsbDrives(void)
0x1800addab  nop
0x1800addac  mov     [rsp+0A8h+var_68], r15
0x1800addb1  lea     r9, [rsp+0A8h+string]; string
0x1800addb6  lea     r8, [rsp+0A8h+hstringHeader]; hstringHeader
0x1800addbb  lea     edx, [r15+16h]; length
0x1800addbf  lea     rcx, ?RuntimeClass_Windows_Storage_PathIO@@3QBGB; "Windows.Storage.PathIO"
0x1800addc6  call    cs:__imp_WindowsCreateStringReference
0x1800addcc  test    eax, eax
0x1800addce  jns     short loc_1800ADDE5
0x1800addd0  xor     r9d, r9d; lpArguments
0x1800addd3  xor     r8d, r8d; nNumberOfArguments
0x1800addd6  lea     edx, [r15+1]; dwExceptionFlags
0x1800addda  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800adddf  call    cs:__imp_RaiseException
0x1800adde5  lea     r8, [rsp+0A8h+var_68]
0x1800addea  lea     rdx, _GUID_0f2f3758_8ec7_4381_922b_8f6c07d288f3
0x1800addf1  mov     rcx, [rsp+0A8h+string]
0x1800addf6  call    cs:__imp_RoGetActivationFactory
0x1800addfc  mov     rcx, [rsp+0A8h]; this
0x1800ade04  test    eax, eax
0x1800ade06  jns     short loc_1800ADE1C
0x1800ade08  mov     r9d, eax; char *
0x1800ade0b  lea     r8, aShellOobeMachi_34; "shell\\oobe\\machine\\concierge\\lib\\c"...
0x1800ade12  mov     edx, 8Ah; void *
0x1800ade17  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800ade1c  mov     rbx, [rsp+0A8h+var_60]
0x1800ade21  cmp     rbx, [rsp+0A8h+var_58]
0x1800ade26  jnz     short loc_1800ADE48
0x1800ade28  lea     rcx, [rsp+0A8h+var_68]
0x1800ade2d  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800ade32  nop
0x1800ade33  lea     rcx, [rsp+0A8h+var_60]
0x1800ade38  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800ade3d  nop
0x1800ade3e  mov     eax, 80070490h
0x1800ade43  jmp     loc_1800ADF82
0x1800ade48  mov     [rsp+0A8h+var_70], r15
0x1800ade4d  mov     rdi, [rsp+0A8h+var_68]
0x1800ade52  mov     rax, [rdi]
0x1800ade55  mov     r14, [rax+30h]
0x1800ade59  mov     [rsp+0A8h+var_70], r15
0x1800ade5e  lea     rdx, aConciergeJson; "Concierge.json"
0x1800ade65  mov     rcx, rbx
0x1800ade68  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800ade6d  mov     rcx, rax
0x1800ade70  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ade75  mov     [rsp+0A8h+var_78], rax
0x1800ade7a  lea     rdx, [rsp+0A8h+var_78]
0x1800ade7f  lea     rcx, [rsp+0A8h+string]
0x1800ade84  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800ade89  nop
0x1800ade8a  lea     r8, [rsp+0A8h+var_70]
0x1800ade8f  mov     rdx, [rax+18h]
0x1800ade93  mov     rcx, rdi
0x1800ade96  mov     rax, r14
0x1800ade99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ade9e  nop
0x1800ade9f  shr     eax, 1Fh
0x1800adea2  xor     al, 1
0x1800adea4  jz      loc_1800ADF6B
0x1800adeaa  mov     [rsp+0A8h+var_78], r15
0x1800adeaf  xor     edx, edx
0x1800adeb1  lea     rcx, [rsp+0A8h+var_78]
0x1800adeb6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x1800adebb  mov     rdi, [rsp+0A8h+var_70]
0x1800adec0  mov     rcx, rdi
0x1800adec3  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)
0x1800adec8  test    eax, eax
0x1800adeca  js      loc_1800ADF60
0x1800aded0  mov     rax, [rdi]
0x1800aded3  lea     rdx, [rsp+0A8h+var_78]
0x1800aded8  mov     rcx, rdi
0x1800adedb  mov     rax, [rax+40h]
0x1800adedf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adee4  test    eax, eax
0x1800adee6  js      short loc_1800ADF60
0x1800adee8  xor     edx, edx; length
0x1800adeea  mov     rcx, [rsp+0A8h+var_78]; string
0x1800adeef  call    cs:__imp_WindowsGetStringRawBuffer
0x1800adef5  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800adef9  inc     r9
0x1800adefc  cmp     [rax+r9*2], r15w
0x1800adf01  jnz     short loc_1800ADEF9
0x1800adf03  mov     [rsp+0A8h+var_80], rsi
0x1800adf08  mov     r8, rax
0x1800adf0b  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x1800adf10  mov     rcx, [rsp+0A8h]; this
0x1800adf18  test    eax, eax
0x1800adf1a  jns     short loc_1800ADF31
0x1800adf1c  mov     r9d, eax; char *
0x1800adf1f  lea     r8, aShellOobeMachi_34; "shell\\oobe\\machine\\concierge\\lib\\c"...
0x1800adf26  mov     edx, 93h; void *
0x1800adf2b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800adf31  lea     rcx, [rsp+0A8h+var_78]; this
0x1800adf36  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800adf3b  nop
0x1800adf3c  lea     rcx, [rsp+0A8h+var_70]
0x1800adf41  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800adf46  nop
0x1800adf47  lea     rcx, [rsp+0A8h+var_68]
0x1800adf4c  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800adf51  nop
0x1800adf52  lea     rcx, [rsp+0A8h+var_60]
0x1800adf57  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800adf5c  xor     eax, eax
0x1800adf5e  jmp     short loc_1800ADF82
0x1800adf60  lea     rcx, [rsp+0A8h+var_78]; this
0x1800adf65  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800adf6a  nop
0x1800adf6b  lea     rcx, [rsp+0A8h+var_70]
0x1800adf70  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x1800adf75  add     rbx, 20h ; ' '
0x1800adf79  jmp     loc_1800ADE21
0x1800adf7e  mov     eax, dword ptr [rsp+0A8h+var_78]
0x1800adf82  mov     rcx, [rsp+0A8h+var_28]
0x1800adf8a  xor     rcx, rsp; StackCookie
0x1800adf8d  call    __security_check_cookie
0x1800adf92  lea     r11, [rsp+0A8h+var_18]
0x1800adf9a  mov     rbx, [r11+20h]
0x1800adf9e  mov     rsi, [r11+30h]
0x1800adfa2  mov     rsp, r11
0x1800adfa5  pop     r15
0x1800adfa7  pop     r14
0x1800adfa9  pop     rdi
0x1800adfaa  retn
```
