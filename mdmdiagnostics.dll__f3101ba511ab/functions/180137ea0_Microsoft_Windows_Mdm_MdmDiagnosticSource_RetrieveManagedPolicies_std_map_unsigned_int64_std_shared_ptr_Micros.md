# Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveManagedPolicies(std::map<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>> &)

- ea: `0x180137ea0`
- end: `0x180137fe5`
- name: `?RetrieveManagedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAV?$map@_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@2@@std@@@Z`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801324f4`

## callees

- `0x1800e4408`
- `0x1800e7de8`
- `0x1800ed46c`
- `0x180105294`
- `0x180105480`
- `0x180135d94`
- `0x1801373d8`
- `0x180137ea0`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180137ec0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180137ec0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180137ef9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180137ef9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveManagedPolicies(__int64 a1)
{
  char IsStateSeparationEnabled; // al
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  int SubKeyNames; // eax
  __int64 v7; // rbx
  __int64 v8; // rsi
  int v9; // eax
  unsigned int v10; // edi
  unsigned int phkResult; // [rsp+20h] [rbp-30h]
  _QWORD v13[4]; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  HKEY v15; // [rsp+78h] [rbp+28h] BYREF

  v15 = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v3 = L"OSData\\SOFTWARE\\Microsoft\\PolicyManager\\providers";
  if ( !IsStateSeparationEnabled )
    v3 = L"SOFTWARE\\Microsoft\\PolicyManager\\providers";
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &v15);
  if ( v4 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x23E,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
           (const char *)v4,
           phkResult);
  }
  else
  {
    std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v13);
    SubKeyNames = anonymous_namespace_::GetSubKeyNames(&v15, 0, (__int64)v13);
    v5 = SubKeyNames;
    if ( SubKeyNames >= 0 )
    {
      v7 = v13[0];
      v8 = v13[1];
      while ( v7 != v8 )
      {
        v9 = anonymous_namespace_::CollectManagedPoliciesForProvider(&v15, v7, a1);
        v10 = v9;
        if ( v9 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x247,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
            (const char *)(unsigned int)v9,
            phkResult);
          std::vector<std::wstring>::_Tidy(v13);
          v5 = v10;
          goto LABEL_13;
        }
        v7 += 32;
      }
      std::vector<std::wstring>::_Tidy(v13);
      v5 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x242,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
        (const char *)(unsigned int)SubKeyNames,
        phkResult);
      std::vector<std::wstring>::_Tidy(v13);
    }
  }
LABEL_13:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v15);
  return v5;
}

```

## disassembly

```asm
0x180137ea0  mov     [rsp-18h+arg_0], rbx
0x180137ea5  mov     [rsp-18h+arg_10], rsi
0x180137eaa  push    rbp
0x180137eab  push    rdi
0x180137eac  push    r14
0x180137eae  mov     rbp, rsp
0x180137eb1  sub     rsp, 50h
0x180137eb5  mov     r14, rcx
0x180137eb8  mov     [rbp+arg_8], 0
0x180137ec0  call    cs:__imp_RtlIsStateSeparationEnabled
0x180137ec7  nop     dword ptr [rax+rax+00h]
0x180137ecc  lea     rcx, aSoftwareMicros_18; "SOFTWARE\\Microsoft\\PolicyManager\\pro"...
0x180137ed3  lea     rdx, aOsdataSoftware_3; "OSData\\SOFTWARE\\Microsoft\\PolicyMana"...
0x180137eda  test    al, al
0x180137edc  cmovz   rdx, rcx; lpSubKey
0x180137ee0  lea     rax, [rbp+arg_8]
0x180137ee4  mov     qword ptr [rsp+50h+phkResult], rax; int
0x180137ee9  mov     r9d, 20019h; samDesired
0x180137eef  xor     r8d, r8d; ulOptions
0x180137ef2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180137ef9  call    cs:__imp_RegOpenKeyExW
0x180137f00  nop     dword ptr [rax+rax+00h]
0x180137f05  test    eax, eax
0x180137f07  jz      short loc_180137F28
0x180137f09  mov     rcx, [rbp+18h]; this
0x180137f0d  mov     r9d, eax; char *
0x180137f10  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137f17  mov     edx, 23Eh; void *
0x180137f1c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180137f21  mov     ebx, eax
0x180137f23  jmp     loc_180137FC4
0x180137f28  lea     rcx, [rbp+var_20]
0x180137f2c  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180137f31  nop
0x180137f32  lea     r8, [rbp+var_20]
0x180137f36  xor     edx, edx
0x180137f38  lea     rcx, [rbp+arg_8]
0x180137f3c  call    _anonymous_namespace___GetSubKeyNames
0x180137f41  mov     ebx, eax
0x180137f43  test    eax, eax
0x180137f45  jns     short loc_180137F6B
0x180137f47  mov     rcx, [rbp+18h]; this
0x180137f4b  mov     r9d, eax; char *
0x180137f4e  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137f55  mov     edx, 242h; void *
0x180137f5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137f5f  nop
0x180137f60  lea     rcx, [rbp+var_20]
0x180137f64  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180137f69  jmp     short loc_180137FC4
0x180137f6b  mov     rbx, [rbp+var_20]
0x180137f6f  mov     rsi, [rbp+var_18]
0x180137f73  cmp     rbx, rsi
0x180137f76  jz      short loc_180137FB9
0x180137f78  mov     r8, r14
0x180137f7b  mov     rdx, rbx
0x180137f7e  lea     rcx, [rbp+arg_8]
0x180137f82  call    _anonymous_namespace___CollectManagedPoliciesForProvider
0x180137f87  mov     edi, eax
0x180137f89  test    eax, eax
0x180137f8b  js      short loc_180137F93
0x180137f8d  add     rbx, 20h ; ' '
0x180137f91  jmp     short loc_180137F73
0x180137f93  mov     rcx, [rbp+18h]; this
0x180137f97  mov     r9d, edi; char *
0x180137f9a  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180137fa1  mov     edx, 247h; void *
0x180137fa6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137fab  nop
0x180137fac  lea     rcx, [rbp+var_20]
0x180137fb0  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180137fb5  mov     ebx, edi
0x180137fb7  jmp     short loc_180137FC4
0x180137fb9  lea     rcx, [rbp+var_20]
0x180137fbd  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180137fc2  xor     ebx, ebx
0x180137fc4  lea     rcx, [rbp+arg_8]
0x180137fc8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180137fcd  mov     eax, ebx
0x180137fcf  lea     r11, [rsp+50h+var_s0]
0x180137fd4  mov     rbx, [r11+20h]
0x180137fd8  mov     rsi, [r11+30h]
0x180137fdc  mov     rsp, r11
0x180137fdf  pop     r14
0x180137fe1  pop     rdi
0x180137fe2  pop     rbp
0x180137fe3  retn
```
