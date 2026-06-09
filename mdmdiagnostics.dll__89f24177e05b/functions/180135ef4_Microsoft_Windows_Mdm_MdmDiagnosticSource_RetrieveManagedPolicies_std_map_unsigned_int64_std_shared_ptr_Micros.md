# Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveManagedPolicies(std::map<unsigned __int64,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::Policy>>>> &)

- ea: `0x180135ef4`
- end: `0x18013602c`
- name: `?RetrieveManagedPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAV?$map@_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@VPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@std@@@2@@std@@@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801306f0`

## callees

- `0x1800e4348`
- `0x1800e7c08`
- `0x1800ece5c`
- `0x180104108`
- `0x180104270`
- `0x180133ec4`
- `0x180135484`
- `0x180135ef4`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180135f14`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180135f14`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180135f47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180135f47`

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
0x180135ef4  mov     [rsp-18h+arg_0], rbx
0x180135ef9  mov     [rsp-18h+arg_10], rsi
0x180135efe  push    rbp
0x180135eff  push    rdi
0x180135f00  push    r14
0x180135f02  mov     rbp, rsp
0x180135f05  sub     rsp, 50h
0x180135f09  mov     r14, rcx
0x180135f0c  mov     [rbp+arg_8], 0
0x180135f14  call    cs:__imp_RtlIsStateSeparationEnabled
0x180135f1a  lea     rcx, aSoftwareMicros_18; "SOFTWARE\\Microsoft\\PolicyManager\\pro"...
0x180135f21  lea     rdx, aOsdataSoftware_3; "OSData\\SOFTWARE\\Microsoft\\PolicyMana"...
0x180135f28  test    al, al
0x180135f2a  cmovz   rdx, rcx; lpSubKey
0x180135f2e  lea     rax, [rbp+arg_8]
0x180135f32  mov     qword ptr [rsp+50h+phkResult], rax; int
0x180135f37  mov     r9d, 20019h; samDesired
0x180135f3d  xor     r8d, r8d; ulOptions
0x180135f40  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180135f47  call    cs:__imp_RegOpenKeyExW
0x180135f4d  test    eax, eax
0x180135f4f  jz      short loc_180135F70
0x180135f51  mov     rcx, [rbp+18h]; this
0x180135f55  mov     r9d, eax; char *
0x180135f58  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180135f5f  mov     edx, 23Eh; void *
0x180135f64  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180135f69  mov     ebx, eax
0x180135f6b  jmp     loc_18013600C
0x180135f70  lea     rcx, [rbp+var_20]
0x180135f74  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180135f79  nop
0x180135f7a  lea     r8, [rbp+var_20]
0x180135f7e  xor     edx, edx
0x180135f80  lea     rcx, [rbp+arg_8]
0x180135f84  call    _anonymous_namespace___GetSubKeyNames
0x180135f89  mov     ebx, eax
0x180135f8b  test    eax, eax
0x180135f8d  jns     short loc_180135FB3
0x180135f8f  mov     rcx, [rbp+18h]; this
0x180135f93  mov     r9d, eax; char *
0x180135f96  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180135f9d  mov     edx, 242h; void *
0x180135fa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180135fa7  nop
0x180135fa8  lea     rcx, [rbp+var_20]
0x180135fac  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180135fb1  jmp     short loc_18013600C
0x180135fb3  mov     rbx, [rbp+var_20]
0x180135fb7  mov     rsi, [rbp+var_18]
0x180135fbb  cmp     rbx, rsi
0x180135fbe  jz      short loc_180136001
0x180135fc0  mov     r8, r14
0x180135fc3  mov     rdx, rbx
0x180135fc6  lea     rcx, [rbp+arg_8]
0x180135fca  call    _anonymous_namespace___CollectManagedPoliciesForProvider
0x180135fcf  mov     edi, eax
0x180135fd1  test    eax, eax
0x180135fd3  js      short loc_180135FDB
0x180135fd5  add     rbx, 20h ; ' '
0x180135fd9  jmp     short loc_180135FBB
0x180135fdb  mov     rcx, [rbp+18h]; this
0x180135fdf  mov     r9d, edi; char *
0x180135fe2  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180135fe9  mov     edx, 247h; void *
0x180135fee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180135ff3  nop
0x180135ff4  lea     rcx, [rbp+var_20]
0x180135ff8  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180135ffd  mov     ebx, edi
0x180135fff  jmp     short loc_18013600C
0x180136001  lea     rcx, [rbp+var_20]
0x180136005  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18013600a  xor     ebx, ebx
0x18013600c  lea     rcx, [rbp+arg_8]
0x180136010  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180136015  mov     eax, ebx
0x180136017  lea     r11, [rsp+50h+var_s0]
0x18013601c  mov     rbx, [r11+20h]
0x180136020  mov     rsi, [r11+30h]
0x180136024  mov     rsp, r11
0x180136027  pop     r14
0x180136029  pop     rdi
0x18013602a  pop     rbp
0x18013602b  retn
```
