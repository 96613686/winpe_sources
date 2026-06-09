# CreativeFramework::Triggers::OnCommonTriggerEvent(CreativeFramework::Triggers::TriggerType)

- ea: `0x1400478ac`
- end: `0x140047a36`
- name: `?OnCommonTriggerEvent@Triggers@CreativeFramework@@YAJW4TriggerType@12@@Z`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001aff0`

## callees

- `0x1400478ac`
- `0x140047f0c`
- `0x14007bf4c`
- `0x14009ac68`
- `0x14010e160`
- `0x140138d84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140047968`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140047968`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140047900`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140047900`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140047a09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140047a09`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140047993`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x140047993`

## string_xrefs

- `0x1400478f2`: `Software\Microsoft\Windows\CurrentVersion\ContentDeliveryManager\CommonTriggerRegistrations\UserIdle\Show`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CreativeFramework::Triggers::OnCommonTriggerEvent()
{
  HKEY *v0; // rax
  HRESULT v1; // eax
  unsigned int v2; // ebx
  int v4; // eax
  int phkResult; // [rsp+20h] [rbp-19h]
  DWORD cValues; // [rsp+60h] [rbp+27h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+2Fh] BYREF
  GUID pclsid; // [rsp+70h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  hKey = 0;
  cValues = 0;
  v0 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\ContentDeliveryManager\\CommonTriggerRegistrations\\UserIdle\\Show",
          0,
          0x20019u,
          v0)
    && !RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0)
    && cValues )
  {
    pclsid = 0;
    v1 = CLSIDFromString(L"{518fffa3-5b1c-4904-a637-82b7f763777e}", &pclsid);
    v2 = v1;
    if ( v1 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecoreuap\\shell\\contentdeliverymanager\\utils\\lib\\contentdeliverymanagertriggers\\contentdeli"
                      "verymanagertriggers.cpp",
        (const char *)(unsigned int)v1,
        phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v2;
    }
    v4 = CreativeFramework::Triggers::TriggerProcessRule(&pclsid);
    v2 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecoreuap\\shell\\contentdeliverymanager\\utils\\lib\\contentdeliverymanagertriggers\\contentdeli"
                      "verymanagertriggers.cpp",
        (const char *)(unsigned int)v4,
        phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v2;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1400478ac  mov     [rsp-8+arg_0], rbx
0x1400478b1  push    rbp
0x1400478b2  lea     rbp, [rsp-57h]
0x1400478b7  sub     rsp, 90h
0x1400478be  mov     rax, cs:__security_cookie
0x1400478c5  xor     rax, rsp
0x1400478c8  mov     [rbp+57h+var_10], rax
0x1400478cc  mov     [rbp+57h+hKey], 0
0x1400478d4  mov     [rbp+57h+cValues], 0
0x1400478db  lea     rcx, [rbp+57h+hKey]
0x1400478df  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1400478e4  mov     [rsp+90h+phkResult], rax; phkResult
0x1400478e9  mov     r9d, 20019h; samDesired
0x1400478ef  xor     r8d, r8d; ulOptions
0x1400478f2  lea     rdx, ?c_regKeyUserIdleShowRegistrations@ContentDeliveryManagerSettings@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400478f9  mov     rcx, 0FFFFFFFF80000001h; hKey
0x140047900  call    cs:__imp_RegOpenKeyExW
0x140047907  nop     dword ptr [rax+rax+00h]
0x14004790c  test    eax, eax
0x14004790e  jnz     loc_140047A00
0x140047914  mov     [rsp+90h+lpftLastWriteTime], 0; lpftLastWriteTime
0x14004791d  mov     [rsp+90h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x140047926  mov     [rsp+90h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x14004792f  mov     [rsp+90h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x140047938  lea     rax, [rbp+57h+cValues]
0x14004793c  mov     [rsp+90h+lpcValues], rax; lpcValues
0x140047941  mov     [rsp+90h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x14004794a  mov     [rsp+90h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x140047953  mov     [rsp+90h+phkResult], 0; int
0x14004795c  xor     r9d, r9d; lpReserved
0x14004795f  xor     r8d, r8d; lpcchClass
0x140047962  xor     edx, edx; lpClass
0x140047964  mov     rcx, [rbp+57h+hKey]; hKey
0x140047968  call    cs:__imp_RegQueryInfoKeyW
0x14004796f  nop     dword ptr [rax+rax+00h]
0x140047974  test    eax, eax
0x140047976  jnz     loc_140047A00
0x14004797c  cmp     [rbp+57h+cValues], eax
0x14004797f  jbe     short loc_140047A00
0x140047981  xorps   xmm0, xmm0
0x140047984  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x140047988  lea     rdx, [rbp+57h+pclsid]; pclsid
0x14004798c  lea     rcx, ?c_userIdleTriggerRuleId@ContentDeliveryManagerSettings@CreativeFramework@@3QBGB; "{518fffa3-5b1c-4904-a637-82b7f763777e}"
0x140047993  call    cs:__imp_CLSIDFromString
0x14004799a  nop     dword ptr [rax+rax+00h]
0x14004799f  mov     ebx, eax
0x1400479a1  test    eax, eax
0x1400479a3  jns     short loc_1400479CC
0x1400479a5  mov     rcx, [rbp+5Fh]; this
0x1400479a9  mov     r9d, eax; char *
0x1400479ac  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\contentdeliverymanag"...
0x1400479b3  mov     edx, 3Fh ; '?'; void *
0x1400479b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400479bd  nop
0x1400479be  lea     rcx, [rbp+57h+hKey]
0x1400479c2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400479c7  nop
0x1400479c8  mov     eax, ebx
0x1400479ca  jmp     short loc_140047A18
0x1400479cc  lea     rcx, [rbp+57h+pclsid]
0x1400479d0  call    ?TriggerProcessRule@Triggers@CreativeFramework@@YAJAEBU_GUID@@W4RuleType@12@@Z; CreativeFramework::Triggers::TriggerProcessRule(_GUID const &,CreativeFramework::Triggers::RuleType)
0x1400479d5  mov     ebx, eax
0x1400479d7  test    eax, eax
0x1400479d9  jns     short loc_140047A00
0x1400479db  mov     rcx, [rbp+5Fh]; this
0x1400479df  mov     r9d, eax; char *
0x1400479e2  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\contentdeliverymanag"...
0x1400479e9  mov     edx, 40h ; '@'; void *
0x1400479ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400479f3  nop
0x1400479f4  lea     rcx, [rbp+57h+hKey]
0x1400479f8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400479fd  nop
0x1400479fe  jmp     short loc_1400479C8
0x140047a00  mov     rcx, [rbp+57h+hKey]; hKey
0x140047a04  test    rcx, rcx
0x140047a07  jz      short loc_140047A16
0x140047a09  call    cs:__imp_RegCloseKey
0x140047a10  nop     dword ptr [rax+rax+00h]
0x140047a15  nop
0x140047a16  xor     eax, eax
0x140047a18  mov     rcx, [rbp+57h+var_10]
0x140047a1c  xor     rcx, rsp; StackCookie
0x140047a1f  call    __security_check_cookie
0x140047a24  mov     rbx, [rsp+90h+arg_0]
0x140047a2c  add     rsp, 90h
0x140047a33  pop     rbp
0x140047a34  retn
```
