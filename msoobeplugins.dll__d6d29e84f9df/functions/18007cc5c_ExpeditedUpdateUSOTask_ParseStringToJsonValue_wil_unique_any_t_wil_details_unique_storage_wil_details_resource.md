# ExpeditedUpdateUSOTask::_ParseStringToJsonValue(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::com_ptr_t<Windows::Data::Json::IJsonValue,wil::err_returncode_policy> &)

- ea: `0x18007cc5c`
- end: `0x18007ce3f`
- name: `?_ParseStringToJsonValue@ExpeditedUpdateUSOTask@@AEAAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$com_ptr_t@UIJsonValue@Json@Data@Windows@@Uerr_returncode_policy@wil@@@3@@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18007b510`

## callees

- `0x180003470`
- `0x180008544`
- `0x18001ad08`
- `0x1800418d8`
- `0x180042068`
- `0x180043c58`
- `0x18007cc5c`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007ccaa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18007ccaa`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007cd0c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18007cd0c`
- `OLEAUT32!__imp_SysStringLen` at `0x18007cc9b`
- `OLEAUT32!__imp_SysStringLen` at `0x18007cc9b`

## string_xrefs

- `0x18007cced`: `Windows.Data.Json.JsonObject`
- `0x18007ccbd`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007cd1f`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`
- `0x18007cdee`: `shell\oobe\machine\plugins\adapters\com\expeditedupdateusotasks.cpp`

## pseudocode

```c
__int64 __fastcall ExpeditedUpdateUSOTask::_ParseStringToJsonValue(__int64 a1, BSTR *a2, __int64 *a3)
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
        (void *)0x345,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
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
        v11 = 848;
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
      v11 = 844;
    }
    else
    {
      v11 = 841;
    }
    v14 = (unsigned int)v10;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
      (const char *)v14,
      v16);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v18);
    goto LABEL_16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x342,
    (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\com\\expeditedupdateusotasks.cpp",
    (const char *)(unsigned int)v6,
    v16);
LABEL_17:
  Windows::Internal::String::~String((Windows::Internal::String *)&string);
  return v7;
}

```

## disassembly

```asm
0x18007cc5c  mov     [rsp-8+arg_0], rbx
0x18007cc61  mov     [rsp-8+arg_18], rdi
0x18007cc66  push    rbp
0x18007cc67  mov     rbp, rsp
0x18007cc6a  sub     rsp, 80h
0x18007cc71  mov     rax, cs:__security_cookie
0x18007cc78  xor     rax, rsp
0x18007cc7b  mov     [rbp+var_10], rax
0x18007cc7f  mov     rdi, r8
0x18007cc82  mov     rbx, rdx
0x18007cc85  mov     [rbp+string], 0
0x18007cc8d  xor     edx, edx
0x18007cc8f  lea     rcx, [rbp+string]
0x18007cc93  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18007cc98  mov     rcx, [rbx]; pbstr
0x18007cc9b  call    cs:__imp_SysStringLen
0x18007cca1  lea     r8, [rbp+string]; string
0x18007cca5  mov     edx, eax; length
0x18007cca7  mov     rcx, [rbx]; sourceString
0x18007ccaa  call    cs:__imp_WindowsCreateString
0x18007ccb0  mov     ebx, eax
0x18007ccb2  test    eax, eax
0x18007ccb4  jns     short loc_18007CCD3
0x18007ccb6  mov     rcx, [rbp+8]; this
0x18007ccba  mov     r9d, eax; char *
0x18007ccbd  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007ccc4  mov     edx, 342h; void *
0x18007ccc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ccce  jmp     loc_18007CE13
0x18007ccd3  mov     [rbp+var_40], 0
0x18007ccdb  mov     [rbp+var_18], 0
0x18007cce3  mov     r9d, 1Ch; unsigned int
0x18007cce9  lea     r8d, [r9+1]; unsigned int
0x18007cced  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18007ccf4  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18007ccf8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007ccfd  lea     r8, [rbp+var_40]
0x18007cd01  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18007cd08  mov     rcx, [rbp+var_18]
0x18007cd0c  call    cs:__imp_RoGetActivationFactory
0x18007cd12  mov     ebx, eax
0x18007cd14  test    eax, eax
0x18007cd16  jns     short loc_18007CD35
0x18007cd18  mov     rcx, [rbp+8]; this
0x18007cd1c  mov     r9d, eax; char *
0x18007cd1f  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007cd26  mov     edx, 345h; void *
0x18007cd2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cd30  jmp     loc_18007CE09
0x18007cd35  mov     [rbp+var_48], 0
0x18007cd3d  mov     [rbp+var_50], 0
0x18007cd41  mov     rcx, [rbp+var_40]
0x18007cd45  mov     rax, [rcx]
0x18007cd48  mov     [rbp+var_48], 0
0x18007cd50  lea     r9, [rbp+var_50]
0x18007cd54  lea     r8, [rbp+var_48]
0x18007cd58  mov     rdx, [rbp+string]
0x18007cd5c  mov     rax, [rax+38h]
0x18007cd60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cd65  mov     ebx, eax
0x18007cd67  test    eax, eax
0x18007cd69  jns     short loc_18007CD72
0x18007cd6b  mov     edx, 349h
0x18007cd70  jmp     short loc_18007CDBB
0x18007cd72  cmp     [rbp+var_50], 0
0x18007cd76  jz      short loc_18007CDE1
0x18007cd78  mov     rbx, [rbp+var_48]
0x18007cd7c  mov     rcx, [rdi]
0x18007cd7f  mov     qword ptr [rdi], 0
0x18007cd86  test    rcx, rcx
0x18007cd89  jz      short loc_18007CD98
0x18007cd8b  mov     rax, [rcx]
0x18007cd8e  mov     rax, [rax+10h]
0x18007cd92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cd97  nop
0x18007cd98  mov     rax, [rbx]
0x18007cd9b  mov     r8, rdi
0x18007cd9e  lea     rdx, _GUID_a3219ecb_f0b3_4dcd_beee_19d48cd3ed1e
0x18007cda5  mov     rcx, rbx
0x18007cda8  mov     rax, [rax]
0x18007cdab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cdb0  mov     ebx, eax
0x18007cdb2  test    eax, eax
0x18007cdb4  jns     short loc_18007CDC0
0x18007cdb6  mov     edx, 34Ch
0x18007cdbb  mov     r9d, eax
0x18007cdbe  jmp     short loc_18007CDEE
0x18007cdc0  lea     rcx, [rbp+var_48]
0x18007cdc4  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007cdc9  nop
0x18007cdca  lea     rcx, [rbp+var_40]
0x18007cdce  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007cdd3  nop
0x18007cdd4  lea     rcx, [rbp+string]; this
0x18007cdd8  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18007cddd  xor     eax, eax
0x18007cddf  jmp     short loc_18007CE1E
0x18007cde1  mov     ebx, 80070057h
0x18007cde6  mov     r9d, ebx; char *
0x18007cde9  mov     edx, 350h; void *
0x18007cdee  lea     r8, aShellOobeMachi_25; "shell\\oobe\\machine\\plugins\\adapters"...
0x18007cdf5  mov     rcx, [rbp+8]; this
0x18007cdf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cdfe  nop
0x18007cdff  lea     rcx, [rbp+var_48]
0x18007ce03  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007ce08  nop
0x18007ce09  lea     rcx, [rbp+var_40]
0x18007ce0d  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18007ce12  nop
0x18007ce13  lea     rcx, [rbp+string]; this
0x18007ce17  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18007ce1c  mov     eax, ebx
0x18007ce1e  mov     rcx, [rbp+var_10]
0x18007ce22  xor     rcx, rsp; StackCookie
0x18007ce25  call    __security_check_cookie
0x18007ce2a  lea     r11, [rsp+80h+var_s0]
0x18007ce32  mov     rbx, [r11+10h]
0x18007ce36  mov     rdi, [r11+28h]
0x18007ce3a  mov     rsp, r11
0x18007ce3d  pop     rbp
0x18007ce3e  retn
```
