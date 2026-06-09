# BitLockerToast::SetTemplateContent(void)

- ea: `0x180010720`
- end: `0x1800108d3`
- name: `?SetTemplateContent@BitLockerToast@@UEAAJXZ`
- size: `435`
- prototype: `__int64 __fastcall(BitLockerToast *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800056c4`
- `0x180007254`
- `0x180010720`
- `0x180013410`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010771`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010840`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010771`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180010840`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180010827`

## string_xrefs

- `0x180010790`: `ds\security\efs\edptask\toast\edptoast.cpp`
- `0x1800107d6`: `ds\security\efs\edptask\toast\edptoast.cpp`
- `0x180010862`: `ds\security\efs\edptask\toast\edptoast.cpp`
- `0x180010751`: `Windows.Data.Xml.Dom.XmlDocument`
- `0x180010820`: `<toast><visual><binding template="ToastGeneric"><text id="1"></text><text id="2"></text></binding></visual></toast>`

## pseudocode

```c
__int64 __fastcall BitLockerToast::SetTemplateContent(BitLockerToast *this)
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
      (void *)0x6C2,
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
      (void *)0x6C5,
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
         L"<toast><visual><binding template=\"ToastGeneric\"><text id=\"1\"></text><text id=\"2\"></text></binding></visual></toast>",
         0x73u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v9 = v8(v7, string);
  v3 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C6,
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
0x180010720  mov     [rsp-8+arg_8], rbx
0x180010725  mov     [rsp-8+arg_10], rdi
0x18001072a  push    rbp
0x18001072b  mov     rbp, rsp
0x18001072e  sub     rsp, 50h
0x180010732  mov     rax, cs:__security_cookie
0x180010739  xor     rax, rsp
0x18001073c  mov     [rbp+var_8], rax
0x180010740  lea     rdi, [rcx+8]
0x180010744  lea     r9, [rbp+string]; string
0x180010748  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001074c  mov     edx, 20h ; ' '; length
0x180010751  lea     rcx, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x180010758  call    cs:__imp_WindowsCreateStringReference
0x18001075e  test    eax, eax
0x180010760  jns     short loc_180010777
0x180010762  xor     r9d, r9d; lpArguments
0x180010765  xor     r8d, r8d; nNumberOfArguments
0x180010768  lea     edx, [r9+1]; dwExceptionFlags
0x18001076c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180010771  call    cs:__imp_RaiseException
0x180010777  mov     rdx, rdi
0x18001077a  mov     rcx, [rbp+string]
0x18001077e  call    ??$ActivateInstance@V?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>)
0x180010783  mov     ebx, eax
0x180010785  test    eax, eax
0x180010787  jns     short loc_1800107A8
0x180010789  mov     rcx, [rbp+8]; this
0x18001078d  mov     r9d, eax; char *
0x180010790  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x180010797  mov     edx, 6C2h; void *
0x18001079c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800107a1  mov     eax, ebx
0x1800107a3  jmp     loc_1800108B7
0x1800107a8  mov     [rbp+var_30], 0
0x1800107b0  mov     rcx, [rdi]
0x1800107b3  mov     rax, [rcx]
0x1800107b6  lea     r8, [rbp+var_30]
0x1800107ba  lea     rdx, _GUID_6cd0e74e_ee65_4489_9ebf_ca43e87ba637
0x1800107c1  mov     rax, [rax]
0x1800107c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107c9  mov     ebx, eax
0x1800107cb  test    eax, eax
0x1800107cd  jns     short loc_180010808
0x1800107cf  mov     rcx, [rbp+8]; this
0x1800107d3  mov     r9d, eax; char *
0x1800107d6  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x1800107dd  mov     edx, 6C5h; void *
0x1800107e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800107e7  nop
0x1800107e8  mov     rcx, [rbp+var_30]
0x1800107ec  test    rcx, rcx
0x1800107ef  jz      short loc_180010806
0x1800107f1  mov     [rbp+var_30], 0
0x1800107f9  mov     rax, [rcx]
0x1800107fc  mov     rax, [rax+10h]
0x180010800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010805  nop
0x180010806  jmp     short loc_1800107A1
0x180010808  mov     rbx, [rbp+var_30]
0x18001080c  mov     rax, [rbx]
0x18001080f  mov     rdi, [rax+30h]
0x180010813  lea     r9, [rbp+string]; string
0x180010817  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001081b  mov     edx, 73h ; 's'; length
0x180010820  lea     rcx, aToastVisualBin_1; "<toast><visual><binding template=\"Toas"...
0x180010827  call    cs:__imp_WindowsCreateStringReference
0x18001082d  test    eax, eax
0x18001082f  jns     short loc_180010846
0x180010831  xor     r9d, r9d; lpArguments
0x180010834  xor     r8d, r8d; nNumberOfArguments
0x180010837  lea     edx, [r9+1]; dwExceptionFlags
0x18001083b  mov     ecx, 0C000000Dh; dwExceptionCode
0x180010840  call    cs:__imp_RaiseException
0x180010846  mov     rdx, [rbp+string]
0x18001084a  mov     rcx, rbx
0x18001084d  mov     rax, rdi
0x180010850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010855  mov     ebx, eax
0x180010857  test    eax, eax
0x180010859  jns     short loc_180010897
0x18001085b  mov     rcx, [rbp+8]; this
0x18001085f  mov     r9d, eax; char *
0x180010862  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x180010869  mov     edx, 6C6h; void *
0x18001086e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010873  nop
0x180010874  mov     rcx, [rbp+var_30]
0x180010878  test    rcx, rcx
0x18001087b  jz      short loc_180010892
0x18001087d  mov     [rbp+var_30], 0
0x180010885  mov     rax, [rcx]
0x180010888  mov     rax, [rax+10h]
0x18001088c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010891  nop
0x180010892  jmp     loc_1800107A1
0x180010897  mov     rcx, [rbp+var_30]
0x18001089b  test    rcx, rcx
0x18001089e  jz      short loc_1800108B5
0x1800108a0  mov     [rbp+var_30], 0
0x1800108a8  mov     rax, [rcx]
0x1800108ab  mov     rax, [rax+10h]
0x1800108af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108b4  nop
0x1800108b5  xor     eax, eax
0x1800108b7  mov     rcx, [rbp+var_8]
0x1800108bb  xor     rcx, rsp; StackCookie
0x1800108be  call    __security_check_cookie
0x1800108c3  mov     rbx, [rsp+50h+arg_8]
0x1800108c8  mov     rdi, [rsp+50h+arg_10]
0x1800108cd  add     rsp, 50h
0x1800108d1  pop     rbp
0x1800108d2  retn
```
