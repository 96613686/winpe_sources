# EdpAadReauthToast::SetTemplateContent(void)

- ea: `0x1800108e0`
- end: `0x180010a93`
- name: `?SetTemplateContent@EdpAadReauthToast@@UEAAJXZ`
- size: `435`
- prototype: `__int64 __fastcall(EdpAadReauthToast *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x180007254`
- `0x1800108e0`
- `0x180013410`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010931`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010a00`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010931`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010a00`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010918`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800109e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010918`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800109e7`

## string_xrefs

- `0x180010950`: `ds\security\efs\edptask\toast\edptoast.cpp`
- `0x180010996`: `ds\security\efs\edptask\toast\edptoast.cpp`
- `0x180010a22`: `ds\security\efs\edptask\toast\edptoast.cpp`
- `0x180010911`: `Windows.Data.Xml.Dom.XmlDocument`
- `0x1800109e0`: `<toast launch="ReAuth"><visual><binding template="ToastGeneric"><text id="1"></text><text id="2"></text></binding></visual></toast>`

## pseudocode

```c
__int64 __fastcall EdpAadReauthToast::SetTemplateContent(EdpAadReauthToast *this)
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
      (void *)0x2F5,
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
      (void *)0x2F8,
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
         L"<toast launch=\"ReAuth\"><visual><binding template=\"ToastGeneric\"><text id=\"1\"></text><text id=\"2\"></text"
          "></binding></visual></toast>",
         0x83u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v9 = v8(v7, string);
  v3 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F9,
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
0x1800108e0  mov     [rsp-8+arg_8], rbx
0x1800108e5  mov     [rsp-8+arg_10], rdi
0x1800108ea  push    rbp
0x1800108eb  mov     rbp, rsp
0x1800108ee  sub     rsp, 50h
0x1800108f2  mov     rax, cs:__security_cookie
0x1800108f9  xor     rax, rsp
0x1800108fc  mov     [rbp+var_8], rax
0x180010900  lea     rdi, [rcx+8]
0x180010904  lea     r9, [rbp+string]; string
0x180010908  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001090c  mov     edx, 20h ; ' '; length
0x180010911  lea     rcx, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x180010918  call    cs:__imp_WindowsCreateStringReference
0x18001091e  test    eax, eax
0x180010920  jns     short loc_180010937
0x180010922  xor     r9d, r9d; lpArguments
0x180010925  xor     r8d, r8d; nNumberOfArguments
0x180010928  lea     edx, [r9+1]; dwExceptionFlags
0x18001092c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180010931  call    cs:__imp_RaiseException
0x180010937  mov     rdx, rdi
0x18001093a  mov     rcx, [rbp+string]
0x18001093e  call    ??$ActivateInstance@V?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>)
0x180010943  mov     ebx, eax
0x180010945  test    eax, eax
0x180010947  jns     short loc_180010968
0x180010949  mov     rcx, [rbp+8]; this
0x18001094d  mov     r9d, eax; char *
0x180010950  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x180010957  mov     edx, 2F5h; void *
0x18001095c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010961  mov     eax, ebx
0x180010963  jmp     loc_180010A77
0x180010968  mov     [rbp+var_30], 0
0x180010970  mov     rcx, [rdi]
0x180010973  mov     rax, [rcx]
0x180010976  lea     r8, [rbp+var_30]
0x18001097a  lea     rdx, _GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637
0x180010981  mov     rax, [rax]
0x180010984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010989  mov     ebx, eax
0x18001098b  test    eax, eax
0x18001098d  jns     short loc_1800109C8
0x18001098f  mov     rcx, [rbp+8]; this
0x180010993  mov     r9d, eax; char *
0x180010996  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x18001099d  mov     edx, 2F8h; void *
0x1800109a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800109a7  nop
0x1800109a8  mov     rcx, [rbp+var_30]
0x1800109ac  test    rcx, rcx
0x1800109af  jz      short loc_1800109C6
0x1800109b1  mov     [rbp+var_30], 0
0x1800109b9  mov     rax, [rcx]
0x1800109bc  mov     rax, [rax+10h]
0x1800109c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109c5  nop
0x1800109c6  jmp     short loc_180010961
0x1800109c8  mov     rbx, [rbp+var_30]
0x1800109cc  mov     rax, [rbx]
0x1800109cf  mov     rdi, [rax+30h]
0x1800109d3  lea     r9, [rbp+string]; string
0x1800109d7  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800109db  mov     edx, 83h; length
0x1800109e0  lea     rcx, aToastLaunchRea; "<toast launch=\"ReAuth\"><visual><bindi"...
0x1800109e7  call    cs:__imp_WindowsCreateStringReference
0x1800109ed  test    eax, eax
0x1800109ef  jns     short loc_180010A06
0x1800109f1  xor     r9d, r9d; lpArguments
0x1800109f4  xor     r8d, r8d; nNumberOfArguments
0x1800109f7  lea     edx, [r9+1]; dwExceptionFlags
0x1800109fb  mov     ecx, 0C000000Dh; dwExceptionCode
0x180010a00  call    cs:__imp_RaiseException
0x180010a06  mov     rdx, [rbp+string]
0x180010a0a  mov     rcx, rbx
0x180010a0d  mov     rax, rdi
0x180010a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a15  mov     ebx, eax
0x180010a17  test    eax, eax
0x180010a19  jns     short loc_180010A57
0x180010a1b  mov     rcx, [rbp+8]; this
0x180010a1f  mov     r9d, eax; char *
0x180010a22  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x180010a29  mov     edx, 2F9h; void *
0x180010a2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010a33  nop
0x180010a34  mov     rcx, [rbp+var_30]
0x180010a38  test    rcx, rcx
0x180010a3b  jz      short loc_180010A52
0x180010a3d  mov     [rbp+var_30], 0
0x180010a45  mov     rax, [rcx]
0x180010a48  mov     rax, [rax+10h]
0x180010a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a51  nop
0x180010a52  jmp     loc_180010961
0x180010a57  mov     rcx, [rbp+var_30]
0x180010a5b  test    rcx, rcx
0x180010a5e  jz      short loc_180010A75
0x180010a60  mov     [rbp+var_30], 0
0x180010a68  mov     rax, [rcx]
0x180010a6b  mov     rax, [rax+10h]
0x180010a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a74  nop
0x180010a75  xor     eax, eax
0x180010a77  mov     rcx, [rbp+var_8]
0x180010a7b  xor     rcx, rsp; StackCookie
0x180010a7e  call    __security_check_cookie
0x180010a83  mov     rbx, [rsp+50h+arg_8]
0x180010a88  mov     rdi, [rsp+50h+arg_10]
0x180010a8d  add     rsp, 50h
0x180010a91  pop     rbp
0x180010a92  retn
```
