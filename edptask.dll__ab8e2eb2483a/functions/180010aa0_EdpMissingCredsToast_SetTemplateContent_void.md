# EdpMissingCredsToast::SetTemplateContent(void)

- ea: `0x180010aa0`
- end: `0x180010c53`
- name: `?SetTemplateContent@EdpMissingCredsToast@@UEAAJXZ`
- size: `435`
- prototype: `__int64 __fastcall(EdpMissingCredsToast *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x180007254`
- `0x180010aa0`
- `0x180013410`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010af1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010bc0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010af1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010bc0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010ad8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010ba7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010ad8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010ba7`

## string_xrefs

- `0x180010b10`: `ds\security\efs\edptask\toast\edptoast.cpp`
- `0x180010b56`: `ds\security\efs\edptask\toast\edptoast.cpp`
- `0x180010be2`: `ds\security\efs\edptask\toast\edptoast.cpp`
- `0x180010ad1`: `Windows.Data.Xml.Dom.XmlDocument`
- `0x180010ba0`: `<toast launch="MissingCreds"><visual><binding template="ToastGeneric"><text id="1"></text><text id="2"></text></binding></visual><actions><action arguments="MissingCreds.Ignore" id="1"/><action arguments="MissingCreds.LearnMore" id="2"/></actions></toast>`

## pseudocode

```c
__int64 __fastcall EdpMissingCredsToast::SetTemplateContent(EdpMissingCredsToast *this)
{
  __int64 *v1; // rdi
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 (__fastcall *v8)(__int64, HSTRING); // rdi
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // [rsp+20h] [rbp-30h] BYREF
  HSTRING string; // [rsp+28h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  v1 = (__int64 *)((char *)this + 8);
  if ( WindowsCreateStringReference(L"Windows.Data.Xml.Dom.XmlDocument", 0x20u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>(
         (__int64)string,
         v1);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DD,
      (int)"ds\\security\\efs\\edptask\\toast\\edptoast.cpp",
      (const char *)(unsigned int)v2);
    return v3;
  }
  v12 = 0;
  v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))*v1)(
         *v1,
         &GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637,
         &v12);
  v3 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E0,
      (int)"ds\\security\\efs\\edptask\\toast\\edptoast.cpp",
      (const char *)(unsigned int)v5);
    v6 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return v3;
  }
  v7 = v12;
  v8 = *(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v12 + 48LL);
  if ( WindowsCreateStringReference(
         L"<toast launch=\"MissingCreds\"><visual><binding template=\"ToastGeneric\"><text id=\"1\"></text><text id=\"2\">"
          "</text></binding></visual><actions><action arguments=\"MissingCreds.Ignore\" id=\"1\"/><action arguments=\"Mis"
          "singCreds.LearnMore\" id=\"2\"/></actions></toast>",
         0xFFu,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v9 = v8(v7, string);
  v3 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E1,
      (int)"ds\\security\\efs\\edptask\\toast\\edptoast.cpp",
      (const char *)(unsigned int)v9);
    v10 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return v3;
  }
  v11 = v12;
  if ( v12 )
  {
    v12 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return 0;
}

```

## disassembly

```asm
0x180010aa0  mov     [rsp-8+arg_8], rbx
0x180010aa5  mov     [rsp-8+arg_10], rdi
0x180010aaa  push    rbp
0x180010aab  mov     rbp, rsp
0x180010aae  sub     rsp, 50h
0x180010ab2  mov     rax, cs:__security_cookie
0x180010ab9  xor     rax, rsp
0x180010abc  mov     [rbp+var_8], rax
0x180010ac0  lea     rdi, [rcx+8]
0x180010ac4  lea     r9, [rbp+string]; string
0x180010ac8  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180010acc  mov     edx, 20h ; ' '; length
0x180010ad1  lea     rcx, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x180010ad8  call    cs:__imp_WindowsCreateStringReference
0x180010ade  test    eax, eax
0x180010ae0  jns     short loc_180010AF7
0x180010ae2  xor     r9d, r9d; lpArguments
0x180010ae5  xor     r8d, r8d; nNumberOfArguments
0x180010ae8  lea     edx, [r9+1]; dwExceptionFlags
0x180010aec  mov     ecx, 0C000000Dh; dwExceptionCode
0x180010af1  call    cs:__imp_RaiseException
0x180010af7  mov     rdx, rdi
0x180010afa  mov     rcx, [rbp+string]
0x180010afe  call    ??$ActivateInstance@V?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>)
0x180010b03  mov     ebx, eax
0x180010b05  test    eax, eax
0x180010b07  jns     short loc_180010B28
0x180010b09  mov     rcx, [rbp+8]; this
0x180010b0d  mov     r9d, eax; char *
0x180010b10  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x180010b17  mov     edx, 3DDh; void *
0x180010b1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b21  mov     eax, ebx
0x180010b23  jmp     loc_180010C37
0x180010b28  mov     [rbp+var_30], 0
0x180010b30  mov     rcx, [rdi]
0x180010b33  mov     rax, [rcx]
0x180010b36  lea     r8, [rbp+var_30]
0x180010b3a  lea     rdx, _GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637
0x180010b41  mov     rax, [rax]
0x180010b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b49  mov     ebx, eax
0x180010b4b  test    eax, eax
0x180010b4d  jns     short loc_180010B88
0x180010b4f  mov     rcx, [rbp+8]; this
0x180010b53  mov     r9d, eax; char *
0x180010b56  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x180010b5d  mov     edx, 3E0h; void *
0x180010b62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010b67  nop
0x180010b68  mov     rcx, [rbp+var_30]
0x180010b6c  test    rcx, rcx
0x180010b6f  jz      short loc_180010B86
0x180010b71  mov     [rbp+var_30], 0
0x180010b79  mov     rax, [rcx]
0x180010b7c  mov     rax, [rax+10h]
0x180010b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b85  nop
0x180010b86  jmp     short loc_180010B21
0x180010b88  mov     rbx, [rbp+var_30]
0x180010b8c  mov     rax, [rbx]
0x180010b8f  mov     rdi, [rax+30h]
0x180010b93  lea     r9, [rbp+string]; string
0x180010b97  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180010b9b  mov     edx, 0FFh; length
0x180010ba0  lea     rcx, aToastLaunchMis; "<toast launch=\"MissingCreds\"><visual>"...
0x180010ba7  call    cs:__imp_WindowsCreateStringReference
0x180010bad  test    eax, eax
0x180010baf  jns     short loc_180010BC6
0x180010bb1  xor     r9d, r9d; lpArguments
0x180010bb4  xor     r8d, r8d; nNumberOfArguments
0x180010bb7  lea     edx, [r9+1]; dwExceptionFlags
0x180010bbb  mov     ecx, 0C000000Dh; dwExceptionCode
0x180010bc0  call    cs:__imp_RaiseException
0x180010bc6  mov     rdx, [rbp+string]
0x180010bca  mov     rcx, rbx
0x180010bcd  mov     rax, rdi
0x180010bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bd5  mov     ebx, eax
0x180010bd7  test    eax, eax
0x180010bd9  jns     short loc_180010C17
0x180010bdb  mov     rcx, [rbp+8]; this
0x180010bdf  mov     r9d, eax; char *
0x180010be2  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x180010be9  mov     edx, 3E1h; void *
0x180010bee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010bf3  nop
0x180010bf4  mov     rcx, [rbp+var_30]
0x180010bf8  test    rcx, rcx
0x180010bfb  jz      short loc_180010C12
0x180010bfd  mov     [rbp+var_30], 0
0x180010c05  mov     rax, [rcx]
0x180010c08  mov     rax, [rax+10h]
0x180010c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c11  nop
0x180010c12  jmp     loc_180010B21
0x180010c17  mov     rcx, [rbp+var_30]
0x180010c1b  test    rcx, rcx
0x180010c1e  jz      short loc_180010C35
0x180010c20  mov     [rbp+var_30], 0
0x180010c28  mov     rax, [rcx]
0x180010c2b  mov     rax, [rax+10h]
0x180010c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c34  nop
0x180010c35  xor     eax, eax
0x180010c37  mov     rcx, [rbp+var_8]
0x180010c3b  xor     rcx, rsp; StackCookie
0x180010c3e  call    __security_check_cookie
0x180010c43  mov     rbx, [rsp+50h+arg_8]
0x180010c48  mov     rdi, [rsp+50h+arg_10]
0x180010c4d  add     rsp, 50h
0x180010c51  pop     rbp
0x180010c52  retn
```
