# UserInsights::SetRegistryValue(HKEY__ *,ushort const *,ushort const *,ulong,uchar *,ulong)

- ea: `0x18027d4d8`
- end: `0x18027d64e`
- name: `?SetRegistryValue@UserInsights@@AEAA_NPEAUHKEY__@@PEBG1KPEAEK@Z`
- size: `374`
- prototype: `bool __fastcall(UserInsights *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int, BYTE *lpData, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18027d1b4`

## callees

- `0x18009aa7c`
- `0x1800caaa4`
- `0x1800cabe8`
- `0x18013ce80`
- `0x18027ca88`
- `0x18027ce8c`
- `0x18027d4d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18027d5f7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18027d5f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18027d60c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18027d60c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18027d5c8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18027d5c8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18027d565`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18027d565`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall UserInsights::SetRegistryValue(
        UserInsights *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        BYTE *lpData)
{
  bool v6; // bl
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  const WCHAR *v11; // rax
  HKEY phkResult; // [rsp+50h] [rbp-21h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-19h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-11h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+68h] [rbp-9h] BYREF
  _BYTE v17[32]; // [rsp+80h] [rbp+Fh] BYREF

  v6 = 0;
  phkResult = 0;
  hKey = 0;
  std::wstring::wstring(v17);
  InsightsRegistryPath(
    -2147483647,
    (unsigned int)L"Software\\Microsoft\\Input\\TypingInsights",
    *(_QWORD *)(v7 + 48),
    (unsigned int)&hKey,
    (__int64)v17);
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  SecurityDescriptor = 0;
  ConvertStringSecurityDescriptorToSecurityDescriptorW(
    L"D:(A;CIOI;KRKW;;;SY)(A;CIOI;KRKW;;;BU)(A;CIOI;KRKW;;;AU)(A;CIOI;KRKW;;;AC)",
    1u,
    &SecurityDescriptor,
    0);
  SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
  SecurityAttributes.bInheritHandle = 0;
  v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17, v8, v9, v10);
  if ( !RegCreateKeyExW(hKey, v11, 0, 0, 0, 0x20006u, &SecurityAttributes, &phkResult, 0) )
  {
    v6 = RegSetValueExW(phkResult, L"Insights", 0, 3u, lpData, 0x1Cu) == 0;
    RegCloseKey(phkResult);
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&SecurityDescriptor);
  std::wstring::_Tidy_deallocate(v17);
  return v6;
}

```

## disassembly

```asm
0x18027d4d8  mov     [rsp-8+arg_8], rbx
0x18027d4dd  mov     [rsp-8+arg_10], rdi
0x18027d4e2  push    rbp
0x18027d4e3  lea     rbp, [rsp-3Fh]
0x18027d4e8  sub     rsp, 0B0h
0x18027d4ef  mov     rax, cs:__security_cookie
0x18027d4f6  xor     rax, rsp
0x18027d4f9  mov     [rbp+3Fh+var_10], rax
0x18027d4fd  mov     r8, rcx
0x18027d500  mov     rdi, [rbp+3Fh+lpData]
0x18027d504  xor     bl, bl
0x18027d506  mov     [rbp+3Fh+var_60], 0
0x18027d50e  mov     [rbp+3Fh+hKey], 0
0x18027d516  lea     rcx, [rbp+3Fh+var_30]
0x18027d51a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18027d51f  lea     rcx, [rbp+3Fh+var_30]
0x18027d523  mov     qword ptr [rsp+0B0h+dwOptions], rcx
0x18027d528  lea     r9, [rbp+3Fh+hKey]
0x18027d52c  mov     r8, [r8+30h]
0x18027d530  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Input\\TypingInsig"...
0x18027d537  mov     rcx, 0FFFFFFFF80000001h
0x18027d53e  call    InsightsRegistryPath
0x18027d543  xorps   xmm0, xmm0
0x18027d546  xor     eax, eax
0x18027d548  movups  xmmword ptr [rbp+3Fh+SecurityAttributes.nLength], xmm0
0x18027d54c  mov     qword ptr [rbp+3Fh+SecurityAttributes.bInheritHandle], rax
0x18027d550  mov     [rbp+3Fh+SecurityDescriptor], rax
0x18027d554  xor     r9d, r9d; SecurityDescriptorSize
0x18027d557  lea     r8, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x18027d55b  lea     edx, [rax+1]; StringSDRevision
0x18027d55e  lea     rcx, StringSecurityDescriptor; "D:(A;CIOI;KRKW;;;SY)(A;CIOI;KRKW;;;BU)("...
0x18027d565  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18027d56c  nop     dword ptr [rax+rax+00h]
0x18027d571  mov     [rbp+3Fh+SecurityAttributes.nLength], 18h
0x18027d578  mov     rax, [rbp+3Fh+SecurityDescriptor]
0x18027d57c  mov     [rbp+3Fh+SecurityAttributes.lpSecurityDescriptor], rax
0x18027d580  mov     [rbp+3Fh+SecurityAttributes.bInheritHandle], 0
0x18027d587  lea     rcx, [rbp+3Fh+var_30]
0x18027d58b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18027d590  mov     rdx, rax; lpSubKey
0x18027d593  mov     [rsp+0B0h+lpdwDisposition], 0; lpdwDisposition
0x18027d59c  lea     rax, [rbp+3Fh+var_60]
0x18027d5a0  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18027d5a5  lea     rax, [rbp+3Fh+SecurityAttributes]
0x18027d5a9  mov     [rsp+0B0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18027d5ae  mov     [rsp+0B0h+samDesired], 20006h; samDesired
0x18027d5b6  mov     [rsp+0B0h+dwOptions], 0; dwOptions
0x18027d5be  xor     r9d, r9d; lpClass
0x18027d5c1  xor     r8d, r8d; Reserved
0x18027d5c4  mov     rcx, [rbp+3Fh+hKey]; hKey
0x18027d5c8  call    cs:__imp_RegCreateKeyExW
0x18027d5cf  nop     dword ptr [rax+rax+00h]
0x18027d5d4  test    eax, eax
0x18027d5d6  jnz     short loc_18027D618
0x18027d5d8  mov     [rsp+0B0h+samDesired], 1Ch; cbData
0x18027d5e0  mov     qword ptr [rsp+0B0h+dwOptions], rdi; lpData
0x18027d5e5  lea     r9d, [rax+3]; dwType
0x18027d5e9  xor     r8d, r8d; Reserved
0x18027d5ec  lea     rdx, aInsights; "Insights"
0x18027d5f3  mov     rcx, [rbp+3Fh+var_60]; hKey
0x18027d5f7  call    cs:__imp_RegSetValueExW
0x18027d5fe  nop     dword ptr [rax+rax+00h]
0x18027d603  test    eax, eax
0x18027d605  setz    bl
0x18027d608  mov     rcx, [rbp+3Fh+var_60]; hKey
0x18027d60c  call    cs:__imp_RegCloseKey
0x18027d613  nop     dword ptr [rax+rax+00h]
0x18027d618  lea     rcx, [rbp+3Fh+SecurityDescriptor]
0x18027d61c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18027d621  lea     rcx, [rbp+3Fh+var_30]
0x18027d625  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18027d62a  mov     al, bl
0x18027d62c  mov     rcx, [rbp+3Fh+var_10]
0x18027d630  xor     rcx, rsp; StackCookie
0x18027d633  call    __security_check_cookie
0x18027d638  lea     r11, [rsp+0B0h+var_s0]
0x18027d640  mov     rbx, [r11+18h]
0x18027d644  mov     rdi, [r11+20h]
0x18027d648  mov     rsp, r11
0x18027d64b  pop     rbp
0x18027d64c  retn
```
