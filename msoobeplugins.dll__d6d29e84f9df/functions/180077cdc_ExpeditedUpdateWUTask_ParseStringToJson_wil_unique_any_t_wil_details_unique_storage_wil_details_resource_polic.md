# ExpeditedUpdateWUTask::_ParseStringToJson(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::com_ptr_t<Windows::Data::Json::IJsonValue,wil::err_exception_policy> &)

- ea: `0x180077cdc`
- end: `0x180077ebf`
- name: `?_ParseStringToJson@ExpeditedUpdateWUTask@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$com_ptr_t@UIJsonValue@Json@Data@Windows@@Uerr_exception_policy@wil@@@3@@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800765c8`

## callees

- `0x180003470`
- `0x180008544`
- `0x18001ad08`
- `0x1800418d8`
- `0x180042068`
- `0x180043c58`
- `0x180077cdc`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180077d2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180077d2a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180077d8c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180077d8c`
- `OLEAUT32!__imp_SysStringLen` at `0x180077d1b`
- `OLEAUT32!__imp_SysStringLen` at `0x180077d1b`

## string_xrefs

- `0x180077d6d`: `Windows.Data.Json.JsonObject`
- `0x180077d3d`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180077d9f`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`
- `0x180077e6e`: `shell\oobe\machine\plugins\adapters\com\expeditedupdatewutasks.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ExpeditedUpdateWUTask::_ParseStringToJson(__int64 a1, BSTR *a2, __int64 *a3)
{
  UINT v5; // eax
  HRESULT v6; // eax
  unsigned int v7; // ebx
  int ActivationFactory; // eax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rdx
  __int64 (__fastcall ***v12)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v13; // rcx
  __int64 v14; // r9
  int v16; // [rsp+20h] [rbp-60h]
  char v17[8]; // [rsp+30h] [rbp-50h] BYREF
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-48h] BYREF
  __int64 *v19; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string; // [rsp+48h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v22; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  string = 0;
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
    &string,
    0);
  v5 = SysStringLen(*a2);
  v6 = WindowsCreateString(*a2, v5, &string);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v19 = 0;
    v22 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    ActivationFactory = RoGetActivationFactory(v22, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v19);
    v7 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4A5,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v16);
LABEL_16:
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v19);
      goto LABEL_17;
    }
    v18 = 0;
    v17[0] = 0;
    v9 = *v19;
    v18 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), char *))(v9 + 56))(
            v19,
            string,
            &v18,
            v17);
    v7 = v10;
    if ( v10 >= 0 )
    {
      if ( !v17[0] )
      {
        v7 = -2147024809;
        v14 = 2147942487LL;
        v11 = 1200;
        goto LABEL_15;
      }
      v12 = v18;
      v13 = *a3;
      *a3 = 0;
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      v10 = (**v12)(v12, &GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e, a3);
      v7 = v10;
      if ( v10 >= 0 )
      {
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v18);
        wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v19);
        Windows::Internal::String::~String((Windows::Internal::String *)&string);
        return 0;
      }
      v11 = 1196;
    }
    else
    {
      v11 = 1193;
    }
    v14 = (unsigned int)v10;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
      (const char *)v14,
      v16);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v18);
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4A2,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdatewutasks.cpp",
    (const char *)(unsigned int)v6,
    v16);
LABEL_17:
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  return v7;
}

```

## disassembly

```asm
0x180077cdc  mov     [rsp-8+arg_0], rbx
0x180077ce1  mov     [rsp-8+arg_18], rdi
0x180077ce6  push    rbp
0x180077ce7  mov     rbp, rsp
0x180077cea  sub     rsp, 80h
0x180077cf1  mov     rax, cs:__security_cookie
0x180077cf8  xor     rax, rsp
0x180077cfb  mov     [rbp+var_10], rax
0x180077cff  mov     rdi, r8
0x180077d02  mov     rbx, rdx
0x180077d05  mov     [rbp+string], 0
0x180077d0d  xor     edx, edx
0x180077d0f  lea     rcx, [rbp+string]
0x180077d13  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x180077d18  mov     rcx, [rbx]; pbstr
0x180077d1b  call    cs:__imp_SysStringLen
0x180077d21  lea     r8, [rbp+string]; string
0x180077d25  mov     edx, eax; length
0x180077d27  mov     rcx, [rbx]; sourceString
0x180077d2a  call    cs:__imp_WindowsCreateString
0x180077d30  mov     ebx, eax
0x180077d32  test    eax, eax
0x180077d34  jns     short loc_180077D53
0x180077d36  mov     rcx, [rbp+8]; this
0x180077d3a  mov     r9d, eax; char *
0x180077d3d  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180077d44  mov     edx, 4A2h; void *
0x180077d49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077d4e  jmp     loc_180077E93
0x180077d53  mov     [rbp+var_40], 0
0x180077d5b  mov     [rbp+var_18], 0
0x180077d63  mov     r9d, 1Ch; unsigned int
0x180077d69  lea     r8d, [r9+1]; unsigned int
0x180077d6d  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180077d74  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180077d78  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180077d7d  lea     r8, [rbp+var_40]
0x180077d81  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x180077d88  mov     rcx, [rbp+var_18]
0x180077d8c  call    cs:__imp_RoGetActivationFactory
0x180077d92  mov     ebx, eax
0x180077d94  test    eax, eax
0x180077d96  jns     short loc_180077DB5
0x180077d98  mov     rcx, [rbp+8]; this
0x180077d9c  mov     r9d, eax; char *
0x180077d9f  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180077da6  mov     edx, 4A5h; void *
0x180077dab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077db0  jmp     loc_180077E89
0x180077db5  mov     [rbp+var_48], 0
0x180077dbd  mov     [rbp+var_50], 0
0x180077dc1  mov     rcx, [rbp+var_40]
0x180077dc5  mov     rax, [rcx]
0x180077dc8  mov     [rbp+var_48], 0
0x180077dd0  lea     r9, [rbp+var_50]
0x180077dd4  lea     r8, [rbp+var_48]
0x180077dd8  mov     rdx, [rbp+string]
0x180077ddc  mov     rax, [rax+38h]
0x180077de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077de5  mov     ebx, eax
0x180077de7  test    eax, eax
0x180077de9  jns     short loc_180077DF2
0x180077deb  mov     edx, 4A9h
0x180077df0  jmp     short loc_180077E3B
0x180077df2  cmp     [rbp+var_50], 0
0x180077df6  jz      short loc_180077E61
0x180077df8  mov     rbx, [rbp+var_48]
0x180077dfc  mov     rcx, [rdi]
0x180077dff  mov     qword ptr [rdi], 0
0x180077e06  test    rcx, rcx
0x180077e09  jz      short loc_180077E18
0x180077e0b  mov     rax, [rcx]
0x180077e0e  mov     rax, [rax+10h]
0x180077e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077e17  nop
0x180077e18  mov     rax, [rbx]
0x180077e1b  mov     r8, rdi
0x180077e1e  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x180077e25  mov     rcx, rbx
0x180077e28  mov     rax, [rax]
0x180077e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077e30  mov     ebx, eax
0x180077e32  test    eax, eax
0x180077e34  jns     short loc_180077E40
0x180077e36  mov     edx, 4ACh
0x180077e3b  mov     r9d, eax
0x180077e3e  jmp     short loc_180077E6E
0x180077e40  lea     rcx, [rbp+var_48]
0x180077e44  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180077e49  nop
0x180077e4a  lea     rcx, [rbp+var_40]
0x180077e4e  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180077e53  nop
0x180077e54  lea     rcx, [rbp+string]; this
0x180077e58  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180077e5d  xor     eax, eax
0x180077e5f  jmp     short loc_180077E9E
0x180077e61  mov     ebx, 80070057h
0x180077e66  mov     r9d, ebx; char *
0x180077e69  mov     edx, 4B0h; void *
0x180077e6e  lea     r8, aShellOobeMachi_0; "shell\\oobe\\machine\\plugins\\adapters"...
0x180077e75  mov     rcx, [rbp+8]; this
0x180077e79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077e7e  nop
0x180077e7f  lea     rcx, [rbp+var_48]
0x180077e83  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180077e88  nop
0x180077e89  lea     rcx, [rbp+var_40]
0x180077e8d  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180077e92  nop
0x180077e93  lea     rcx, [rbp+string]; this
0x180077e97  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180077e9c  mov     eax, ebx
0x180077e9e  mov     rcx, [rbp+var_10]
0x180077ea2  xor     rcx, rsp; StackCookie
0x180077ea5  call    __security_check_cookie
0x180077eaa  lea     r11, [rsp+80h+var_s0]
0x180077eb2  mov     rbx, [r11+10h]
0x180077eb6  mov     rdi, [r11+28h]
0x180077eba  mov     rsp, r11
0x180077ebd  pop     rbp
0x180077ebe  retn
```
