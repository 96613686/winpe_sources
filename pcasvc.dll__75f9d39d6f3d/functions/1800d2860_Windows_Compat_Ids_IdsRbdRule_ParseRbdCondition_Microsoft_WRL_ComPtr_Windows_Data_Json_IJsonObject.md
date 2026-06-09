# Windows::Compat::Ids::IdsRbdRule::ParseRbdCondition(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>)

- ea: `0x1800d2860`
- end: `0x1800d2d43`
- name: `?ParseRbdCondition@IdsRbdRule@Ids@Compat@Windows@@UEAAKV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `1251`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180012920`
- `0x1800189e4`
- `0x18007a6e8`
- `0x180080a20`
- `0x18008cd3c`
- `0x180096f34`
- `0x1800bed5c`
- `0x1800c1ed4`
- `0x1800c7c7c`
- `0x1800d2860`
- `0x1800f1f10`
- `0x1800f7010`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800d29e1`
- `ntdll!RtlNtStatusToDosError` at `0x1800d29e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2994`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d29c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2a87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2ab3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2c19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2c89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2cba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2994`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d29c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2a87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2ab3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2c19`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2c89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d2cba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d290d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d2a27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d2cf7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d2d07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d290d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d2a27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d2cf7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800d2d07`

## string_xrefs

- `0x1800d295e`: `Windows::Compat::Ids::IdsRbdRule::ParseRbdCondition`
- `0x1800d29ac`: `Windows::Compat::Ids::IdsRbdRule::ParseRbdCondition`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::Compat::Ids::IdsRbdRule::ParseRbdCondition(__int64 a1, __int64 *a2)
{
  char *v4; // rsi
  signed int v5; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64, HSTRING *); // rbx
  const char *v8; // r9
  int v9; // r8d
  NTSTATUS v10; // eax
  NTSTATUS v11; // edi
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, __int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v15; // rdi
  int (__fastcall *v16)(__int64, __int64, __int64 *); // rbx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rdi
  unsigned __int16 (__fastcall *v21)(__int64, __int64, __int64 *); // rbx
  const char *v22; // r9
  int v23; // r8d
  __int64 (__fastcall *v24)(char *, __int64 *); // rbx
  __int64 v26; // [rsp+30h] [rbp-99h] BYREF
  HSTRING string; // [rsp+38h] [rbp-91h] BYREF
  __int64 v28; // [rsp+40h] [rbp-89h] BYREF
  HSTRING v29; // [rsp+48h] [rbp-81h] BYREF
  _QWORD v30[2]; // [rsp+50h] [rbp-79h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-69h] BYREF
  __int64 v32; // [rsp+78h] [rbp-51h]
  HSTRING_HEADER v33; // [rsp+80h] [rbp-49h] BYREF
  __int64 v34; // [rsp+98h] [rbp-31h]
  HSTRING_HEADER v35; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v36; // [rsp+B8h] [rbp-11h]
  HSTRING_HEADER v37; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v38; // [rsp+D8h] [rbp+Fh]

  v30[1] = a2;
  LODWORD(v28) = 0;
  string = 0;
  v29 = 0;
  v4 = (char *)operator new(0x60u, (const struct std::nothrow_t *)std::nothrow);
  v30[0] = v4;
  if ( v4 )
  {
    *(_QWORD *)v4 = &Windows::Compat::Ids::IdsRbdConditionItem::`vftable';
    *((_QWORD *)v4 + 6) = 7;
    *((_QWORD *)v4 + 5) = 0;
    *((_WORD *)v4 + 12) = 0;
    std::_Tree_comp<0,std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tree_comp<0,std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v4 + 80);
  }
  else
  {
    v4 = 0;
  }
  v30[0] = v4;
  if ( !v4 )
  {
    v5 = 8;
    goto LABEL_28;
  }
  v6 = *a2;
  v7 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)*a2 + 80LL);
  WindowsDeleteString(string);
  string = 0;
  v32 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ConditionId", 0xCu, 0xBu);
  v5 = v7(v6, v32, &string);
  if ( v5 < 0 )
  {
    v8 = "Failed to get the condition id [%x]";
    v9 = 534;
    goto LABEL_8;
  }
  WindowsGetStringRawBuffer(string, 0);
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsRbdRule::ParseRbdCondition",
    539,
    (unsigned int)"IdsRbdModel: Got condition id [%ws]");
  WindowsGetStringRawBuffer(string, 0);
  v10 = AslGuidFromString((GUID *)(v4 + 8));
  v11 = v10;
  if ( v10 < 0 )
  {
    v5 = RtlNtStatusToDosError(v10);
    if ( v5 == 317 )
      v5 = v11;
    if ( v5 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"Windows::Compat::Ids::IdsRbdRule::ParseRbdCondition",
        544,
        (unsigned int)"Failed to convert rule id to GUID [%d]");
      goto LABEL_28;
    }
  }
  v12 = *a2;
  v13 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)*a2 + 80LL);
  WindowsDeleteString(v29);
  v29 = 0;
  v32 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"DataSourceName", 0xFu, 0xEu);
  v5 = v13(v12, v32, &v29);
  if ( v5 < 0 )
  {
    v8 = "Failed to get the data source name [%x]";
    v9 = 552;
LABEL_8:
    AslLogCallPrintf(1, (unsigned int)"Windows::Compat::Ids::IdsRbdRule::ParseRbdCondition", v9, (_DWORD)v8);
    if ( (v5 & 0x1FFF0000) == 0x70000 )
      v5 = (unsigned __int16)v5;
    goto LABEL_28;
  }
  WindowsGetStringRawBuffer(v29, 0);
  AslLogCallPrintf(
    3,
    (unsigned int)"Windows::Compat::Ids::IdsRbdRule::ParseRbdCondition",
    557,
    (unsigned int)"IdsRbdModel: Got DataSourceName [%ws]");
  StringRawBuffer = WindowsGetStringRawBuffer(v29, 0);
  std::wstring::assign(v4 + 24, StringRawBuffer);
  v26 = 0;
  v15 = *a2;
  v16 = *(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)*a2 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v26);
  v32 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Parameters", 0xBu, 0xAu);
  if ( v16(v15, v32, &v26) < 0 )
  {
    v17 = *a2;
    v18 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)*a2 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v26);
    v34 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v33, L"Parameters", 0xBu, 0xAu);
    LODWORD(v28) = 1;
    v19 = v18(v17, v34, &v26);
    v20 = *a2;
    v21 = *(unsigned __int16 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)*a2 + 64LL);
    if ( (v19 & 0x1FFF0000) == 0x70000 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v26);
      v36 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v35, L"Parameters", 0xBu, 0xAu);
      LODWORD(v28) = 3;
      v5 = v21(v20, v36, &v26);
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v26);
      v38 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v37, L"Parameters", 0xBu, 0xAu);
      LODWORD(v28) = 5;
      v5 = ((__int64 (__fastcall *)(__int64, __int64, __int64 *))v21)(v20, v38, &v26);
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v5 )
  {
    WindowsGetStringRawBuffer(string, 0);
    v22 = "Failed to get the parameter object for condition id:[%ws] [%x]";
    v23 = 565;
  }
  else
  {
    v24 = **(__int64 (__fastcall ***)(char *, __int64 *))v4;
    v28 = v26;
    Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::InternalAddRef(&v28);
    v5 = v24(v4, &v28);
    if ( !v5 )
    {
      std::vector<Windows::Compat::Ids::IdsModel *>::push_back(a1 + 56, v30);
      WindowsGetStringRawBuffer(string, 0);
      AslLogCallPrintf(
        3,
        (unsigned int)"Windows::Compat::Ids::IdsRbdRule::ParseRbdCondition",
        578,
        (unsigned int)"Count of parameters parsed against ConditionId:%ws is %zu");
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v26);
      v5 = 0;
      goto LABEL_28;
    }
    WindowsGetStringRawBuffer(string, 0);
    v22 = "Failed to get parse parameters for condition id:[%ws] [%d]";
    v23 = 573;
  }
  AslLogCallPrintf(1, (unsigned int)"Windows::Compat::Ids::IdsRbdRule::ParseRbdCondition", v23, (_DWORD)v22);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(&v26);
LABEL_28:
  WindowsDeleteString(v29);
  v29 = 0;
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(a2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800d2860  mov     [rsp-8+arg_10], rbx
0x1800d2865  push    rbp
0x1800d2866  push    rsi
0x1800d2867  push    rdi
0x1800d2868  push    r12
0x1800d286a  push    r13
0x1800d286c  push    r14
0x1800d286e  push    r15
0x1800d2870  lea     rbp, [rsp-27h]
0x1800d2875  sub     rsp, 0F0h
0x1800d287c  mov     rax, cs:__security_cookie
0x1800d2883  xor     rax, rsp
0x1800d2886  mov     [rbp+57h+var_40], rax
0x1800d288a  mov     r15, rdx
0x1800d288d  mov     r13, rcx
0x1800d2890  mov     [rbp+57h+var_C8], rdx
0x1800d2894  xor     r12d, r12d
0x1800d2897  mov     dword ptr [rsp+120h+var_E0], r12d
0x1800d289c  mov     [rsp+120h+string], r12
0x1800d28a1  mov     [rsp+120h+var_D8], r12
0x1800d28a6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800d28ad  lea     ecx, [r12+60h]; unsigned __int64
0x1800d28b2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800d28b7  mov     rsi, rax
0x1800d28ba  mov     [rbp+57h+var_D0], rax
0x1800d28be  test    rax, rax
0x1800d28c1  jz      short loc_1800D28EA
0x1800d28c3  lea     rax, ??_7IdsRbdConditionItem@Ids@Compat@Windows@@6B@; const Windows::Compat::Ids::IdsRbdConditionItem::`vftable'
0x1800d28ca  mov     [rsi], rax
0x1800d28cd  mov     qword ptr [rsi+30h], 7
0x1800d28d5  mov     [rsi+28h], r12
0x1800d28d9  mov     [rsi+18h], r12w
0x1800d28de  lea     rcx, [rsi+50h]
0x1800d28e2  call    ??0?$_Tree_comp@$0A@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@AEBU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@1@@Z; std::_Tree_comp<0,std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Tree_comp<0,std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(std::less<std::wstring> const &,std::allocator<std::pair<std::wstring const,std::wstring>> const &)
0x1800d28e7  nop
0x1800d28e8  jmp     short loc_1800D28ED
0x1800d28ea  mov     rsi, r12
0x1800d28ed  mov     [rbp+57h+var_D0], rsi
0x1800d28f1  test    rsi, rsi
0x1800d28f4  jnz     short loc_1800D28FE
0x1800d28f6  lea     ebx, [rsi+8]
0x1800d28f9  jmp     loc_1800D2CF2
0x1800d28fe  mov     rdi, [r15]
0x1800d2901  mov     rax, [rdi]
0x1800d2904  mov     rbx, [rax+50h]
0x1800d2908  mov     rcx, [rsp+120h+string]; string
0x1800d290d  call    cs:__imp_WindowsDeleteString
0x1800d2913  mov     [rsp+120h+string], r12
0x1800d2918  mov     [rbp+57h+var_A8], r12
0x1800d291c  mov     r9d, 0Bh; unsigned int
0x1800d2922  lea     r8d, [r9+1]; unsigned int
0x1800d2926  lea     rdx, aConditionid; "ConditionId"
0x1800d292d  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800d2931  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d2936  nop
0x1800d2937  lea     r8, [rsp+120h+string]
0x1800d293c  mov     rdx, [rbp+57h+var_A8]
0x1800d2940  mov     rcx, rdi
0x1800d2943  mov     rax, rbx
0x1800d2946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d294b  mov     ebx, eax
0x1800d294d  test    eax, eax
0x1800d294f  jns     short loc_1800D298D
0x1800d2951  lea     r9, aFailedToGetThe_40; "Failed to get the condition id [%x]"
0x1800d2958  mov     r8d, 216h
0x1800d295e  lea     rdx, aWindowsCompatI_7; "Windows::Compat::Ids::IdsRbdRule::Parse"...
0x1800d2965  mov     dword ptr [rsp+120h+var_100], ebx
0x1800d2969  mov     ecx, 1
0x1800d296e  call    AslLogCallPrintf
0x1800d2973  mov     eax, ebx
0x1800d2975  and     eax, 1FFF0000h
0x1800d297a  cmp     eax, 70000h
0x1800d297f  jnz     loc_1800D2CF2
0x1800d2985  movzx   ebx, bx
0x1800d2988  jmp     loc_1800D2CF2
0x1800d298d  xor     edx, edx; length
0x1800d298f  mov     rcx, [rsp+120h+string]; string
0x1800d2994  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d299a  mov     [rsp+120h+var_100], rax
0x1800d299f  lea     r9, aIdsrbdmodelGot_0; "IdsRbdModel: Got condition id [%ws]"
0x1800d29a6  mov     r8d, 21Bh
0x1800d29ac  lea     r14, aWindowsCompatI_7; "Windows::Compat::Ids::IdsRbdRule::Parse"...
0x1800d29b3  mov     rdx, r14
0x1800d29b6  mov     ecx, 3
0x1800d29bb  call    AslLogCallPrintf
0x1800d29c0  xor     edx, edx; length
0x1800d29c2  mov     rcx, [rsp+120h+string]; string
0x1800d29c7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d29cd  lea     rcx, [rsi+8]; Guid
0x1800d29d1  mov     rdx, rax
0x1800d29d4  call    AslGuidFromString
0x1800d29d9  mov     edi, eax
0x1800d29db  test    eax, eax
0x1800d29dd  jns     short loc_1800D2A18
0x1800d29df  mov     ecx, eax; Status
0x1800d29e1  call    cs:__imp_RtlNtStatusToDosError
0x1800d29e7  mov     ebx, eax
0x1800d29e9  cmp     eax, 13Dh
0x1800d29ee  cmovz   ebx, edi
0x1800d29f1  test    ebx, ebx
0x1800d29f3  jz      short loc_1800D2A18
0x1800d29f5  mov     dword ptr [rsp+120h+var_100], ebx
0x1800d29f9  lea     r9, aFailedToConver_27; "Failed to convert rule id to GUID [%d]"
0x1800d2a00  mov     r8d, 220h
0x1800d2a06  mov     rdx, r14
0x1800d2a09  mov     ecx, 1
0x1800d2a0e  call    AslLogCallPrintf
0x1800d2a13  jmp     loc_1800D2CF2
0x1800d2a18  mov     rdi, [r15]
0x1800d2a1b  mov     rax, [rdi]
0x1800d2a1e  mov     rbx, [rax+50h]
0x1800d2a22  mov     rcx, [rsp+120h+var_D8]; string
0x1800d2a27  call    cs:__imp_WindowsDeleteString
0x1800d2a2d  mov     [rsp+120h+var_D8], r12
0x1800d2a32  mov     [rbp+57h+var_A8], r12
0x1800d2a36  mov     r9d, 0Eh; unsigned int
0x1800d2a3c  lea     r8d, [r9+1]; unsigned int
0x1800d2a40  lea     rdx, aDatasourcename; "DataSourceName"
0x1800d2a47  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800d2a4b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d2a50  nop
0x1800d2a51  lea     r8, [rsp+120h+var_D8]
0x1800d2a56  mov     rdx, [rbp+57h+var_A8]
0x1800d2a5a  mov     rcx, rdi
0x1800d2a5d  mov     rax, rbx
0x1800d2a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2a65  mov     ebx, eax
0x1800d2a67  test    eax, eax
0x1800d2a69  jns     short loc_1800D2A80
0x1800d2a6b  lea     r9, aFailedToGetThe_31; "Failed to get the data source name [%x]"
0x1800d2a72  mov     r8d, 228h
0x1800d2a78  mov     rdx, r14
0x1800d2a7b  jmp     loc_1800D2965
0x1800d2a80  xor     edx, edx; length
0x1800d2a82  mov     rcx, [rsp+120h+var_D8]; string
0x1800d2a87  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d2a8d  mov     [rsp+120h+var_100], rax
0x1800d2a92  lea     r9, aIdsrbdmodelGot_4; "IdsRbdModel: Got DataSourceName [%ws]"
0x1800d2a99  mov     r8d, 22Dh
0x1800d2a9f  mov     rdx, r14
0x1800d2aa2  mov     ecx, 3
0x1800d2aa7  call    AslLogCallPrintf
0x1800d2aac  xor     edx, edx; length
0x1800d2aae  mov     rcx, [rsp+120h+var_D8]; string
0x1800d2ab3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d2ab9  lea     rcx, [rsi+18h]
0x1800d2abd  mov     rdx, rax
0x1800d2ac0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800d2ac5  mov     [rsp+120h+var_F0], r12
0x1800d2aca  mov     rdi, [r15]
0x1800d2acd  mov     rax, [rdi]
0x1800d2ad0  mov     rbx, [rax+40h]
0x1800d2ad4  lea     rcx, [rsp+120h+var_F0]
0x1800d2ad9  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d2ade  mov     [rbp+57h+var_A8], r12
0x1800d2ae2  mov     r9d, 0Ah; unsigned int
0x1800d2ae8  lea     r8d, [r9+1]; unsigned int
0x1800d2aec  lea     rdx, aParameters; "Parameters"
0x1800d2af3  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800d2af7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d2afc  nop
0x1800d2afd  lea     r8, [rsp+120h+var_F0]
0x1800d2b02  mov     rdx, [rbp+57h+var_A8]
0x1800d2b06  mov     rcx, rdi
0x1800d2b09  mov     rax, rbx
0x1800d2b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2b11  test    eax, eax
0x1800d2b13  js      short loc_1800D2B1D
0x1800d2b15  mov     ebx, r12d
0x1800d2b18  jmp     loc_1800D2C0E
0x1800d2b1d  mov     rdi, [r15]
0x1800d2b20  mov     rax, [rdi]
0x1800d2b23  mov     rbx, [rax+40h]
0x1800d2b27  lea     rcx, [rsp+120h+var_F0]
0x1800d2b2c  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d2b31  mov     [rbp+57h+var_88], r12
0x1800d2b35  mov     r9d, 0Ah; unsigned int
0x1800d2b3b  lea     r8d, [r9+1]; unsigned int
0x1800d2b3f  lea     rdx, aParameters; "Parameters"
0x1800d2b46  lea     rcx, [rbp+57h+var_A0]; hstringHeader
0x1800d2b4a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d2b4f  nop
0x1800d2b50  mov     dword ptr [rsp+120h+var_E0], 1
0x1800d2b58  lea     r8, [rsp+120h+var_F0]
0x1800d2b5d  mov     rdx, [rbp+57h+var_88]
0x1800d2b61  mov     rcx, rdi
0x1800d2b64  mov     rax, rbx
0x1800d2b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2b6c  and     eax, 1FFF0000h
0x1800d2b71  mov     rdi, [r15]
0x1800d2b74  lea     rcx, [rsp+120h+var_F0]
0x1800d2b79  cmp     eax, 70000h
0x1800d2b7e  mov     rax, [rdi]
0x1800d2b81  mov     rbx, [rax+40h]
0x1800d2b85  jnz     short loc_1800D2BCC
0x1800d2b87  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d2b8c  mov     [rbp+57h+var_68], r12
0x1800d2b90  mov     r9d, 0Ah; unsigned int
0x1800d2b96  lea     r8d, [r9+1]; unsigned int
0x1800d2b9a  lea     rdx, aParameters; "Parameters"
0x1800d2ba1  lea     rcx, [rbp+57h+var_80]; hstringHeader
0x1800d2ba5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d2baa  nop
0x1800d2bab  mov     dword ptr [rsp+120h+var_E0], 3
0x1800d2bb3  lea     r8, [rsp+120h+var_F0]
0x1800d2bb8  mov     rdx, [rbp+57h+var_68]
0x1800d2bbc  mov     rcx, rdi
0x1800d2bbf  mov     rax, rbx
0x1800d2bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2bc7  movzx   ebx, ax
0x1800d2bca  jmp     short loc_1800D2C0E
0x1800d2bcc  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d2bd1  mov     [rbp+57h+var_48], r12
0x1800d2bd5  mov     r9d, 0Ah; unsigned int
0x1800d2bdb  lea     r8d, [r9+1]; unsigned int
0x1800d2bdf  lea     rdx, aParameters; "Parameters"
0x1800d2be6  lea     rcx, [rbp+57h+var_60]; hstringHeader
0x1800d2bea  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d2bef  nop
0x1800d2bf0  mov     dword ptr [rsp+120h+var_E0], 5
0x1800d2bf8  lea     r8, [rsp+120h+var_F0]
0x1800d2bfd  mov     rdx, [rbp+57h+var_48]
0x1800d2c01  mov     rcx, rdi
0x1800d2c04  mov     rax, rbx
0x1800d2c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2c0c  mov     ebx, eax
0x1800d2c0e  test    ebx, ebx
0x1800d2c10  jz      short loc_1800D2C52
0x1800d2c12  xor     edx, edx; length
0x1800d2c14  mov     rcx, [rsp+120h+string]; string
0x1800d2c19  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d2c1f  lea     r9, aFailedToGetThe_21; "Failed to get the parameter object for "...
0x1800d2c26  mov     r8d, 235h
0x1800d2c2c  mov     dword ptr [rsp+120h+var_F8], ebx
0x1800d2c30  mov     [rsp+120h+var_100], rax
0x1800d2c35  mov     rdx, r14
0x1800d2c38  mov     ecx, 1
0x1800d2c3d  call    AslLogCallPrintf
0x1800d2c42  nop
0x1800d2c43  lea     rcx, [rsp+120h+var_F0]
0x1800d2c48  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d2c4d  jmp     loc_1800D2CF2
0x1800d2c52  mov     rax, [rsi]
0x1800d2c55  mov     rbx, [rax]
0x1800d2c58  mov     rdx, [rsp+120h+var_F0]
0x1800d2c5d  mov     [rsp+120h+var_E0], rdx
0x1800d2c62  lea     rcx, [rsp+120h+var_E0]
0x1800d2c67  call    ?InternalAddRef@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::InternalAddRef(void)
0x1800d2c6c  lea     rdx, [rsp+120h+var_E0]
0x1800d2c71  mov     rcx, rsi
0x1800d2c74  mov     rax, rbx
0x1800d2c77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2c7c  mov     ebx, eax
0x1800d2c7e  test    eax, eax
0x1800d2c80  jz      short loc_1800D2C9E
0x1800d2c82  xor     edx, edx; length
0x1800d2c84  mov     rcx, [rsp+120h+string]; string
0x1800d2c89  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d2c8f  lea     r9, aFailedToGetPar; "Failed to get parse parameters for cond"...
0x1800d2c96  mov     r8d, 23Dh
0x1800d2c9c  jmp     short loc_1800D2C2C
0x1800d2c9e  lea     rcx, [r13+38h]
0x1800d2ca2  lea     rdx, [rbp+57h+var_D0]
0x1800d2ca6  call    ?push_back@?$vector@PEAVIdsModel@Ids@Compat@Windows@@V?$allocator@PEAVIdsModel@Ids@Compat@Windows@@@std@@@std@@QEAAXAEBQEAVIdsModel@Ids@Compat@Windows@@@Z; std::vector<Windows::Compat::Ids::IdsModel *>::push_back(Windows::Compat::Ids::IdsModel * const &)
0x1800d2cab  mov     rax, [rbp+57h+var_D0]
0x1800d2caf  mov     rbx, [rax+58h]
0x1800d2cb3  xor     edx, edx; length
0x1800d2cb5  mov     rcx, [rsp+120h+string]; string
0x1800d2cba  call    cs:__imp_WindowsGetStringRawBuffer
0x1800d2cc0  mov     [rsp+120h+var_F8], rbx
0x1800d2cc5  mov     [rsp+120h+var_100], rax
0x1800d2cca  lea     r9, aCountOfParamet; "Count of parameters parsed against Cond"...
0x1800d2cd1  mov     r8d, 242h
0x1800d2cd7  mov     rdx, r14
0x1800d2cda  mov     ecx, 3
0x1800d2cdf  call    AslLogCallPrintf
0x1800d2ce4  nop
0x1800d2ce5  lea     rcx, [rsp+120h+var_F0]
0x1800d2cea  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d2cef  mov     ebx, r12d
0x1800d2cf2  mov     rcx, [rsp+120h+var_D8]; string
0x1800d2cf7  call    cs:__imp_WindowsDeleteString
0x1800d2cfd  mov     [rsp+120h+var_D8], r12
0x1800d2d02  mov     rcx, [rsp+120h+string]; string
0x1800d2d07  call    cs:__imp_WindowsDeleteString
0x1800d2d0d  mov     [rsp+120h+string], r12
0x1800d2d12  mov     rcx, r15
0x1800d2d15  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVPackageUserInformation@Deployment@Management@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::Management::Deployment::PackageUserInformation *>>::InternalRelease(void)
0x1800d2d1a  mov     eax, ebx
0x1800d2d1c  mov     rcx, [rbp+57h+var_40]
0x1800d2d20  xor     rcx, rsp; StackCookie
0x1800d2d23  call    __security_check_cookie
0x1800d2d28  mov     rbx, [rsp+120h+arg_10]
0x1800d2d30  add     rsp, 0F0h
0x1800d2d37  pop     r15
0x1800d2d39  pop     r14
0x1800d2d3b  pop     r13
0x1800d2d3d  pop     r12
0x1800d2d3f  pop     rdi
0x1800d2d40  pop     rsi
  ... truncated ...
```
