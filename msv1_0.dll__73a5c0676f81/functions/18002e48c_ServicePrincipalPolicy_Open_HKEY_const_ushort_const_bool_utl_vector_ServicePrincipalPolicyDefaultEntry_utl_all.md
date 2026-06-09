# ServicePrincipalPolicy::Open(HKEY__ * const,ushort const *,bool,utl::vector<ServicePrincipalPolicyDefaultEntry,utl::allocator<ServicePrincipalPolicyDefaultEntry>> &)

- ea: `0x18002e48c`
- end: `0x18002e56f`
- name: `?Open@ServicePrincipalPolicy@@SA?AV?$unique_ptr@VServicePrincipalPolicy@@U?$default_delete@VServicePrincipalPolicy@@@utl@@@utl@@QEAUHKEY__@@PEBG_NAEAV?$vector@VServicePrincipalPolicyDefaultEntry@@V?$allocator@VServicePrincipalPolicyDefaultEntry@@@utl@@@3@@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001f240`

## callees

- `0x18002049c`
- `0x18002e48c`
- `0x18002e578`
- `0x18002e5a8`
- `0x180030510`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e4c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e4c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e4f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e4f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall ServicePrincipalPolicy::Open(__int64 *a1, HKEY a2, const WCHAR *a3, __int64 a4, HKEY hKey)
{
  LSTATUS v6; // eax
  signed int v7; // ecx
  HKEY v8; // rdi
  void *v9; // rax
  __int64 v10; // rax
  __int64 v12; // [rsp+38h] [rbp-8h] BYREF

  hKey = 0;
  v6 = RegOpenKeyExW(a2, a3, 0, 0x20019u, &hKey);
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0xC0070000;
  else
    v7 = v6;
  if ( v7 >= 0 || v6 == 2 )
  {
    v8 = 0;
    if ( hKey )
    {
      v8 = hKey;
      hKey = 0;
    }
    v9 = operator new(0x28u);
    v10 = ServicePrincipalPolicy::ServicePrincipalPolicy(v9, v8);
    v12 = v10;
    if ( v10 )
    {
      v12 = 0;
      *a1 = v10;
    }
    else
    {
      *a1 = 0;
    }
    utl::unique_ptr<ServicePrincipalPolicy,utl::default_delete<ServicePrincipalPolicy>>::~unique_ptr<ServicePrincipalPolicy,utl::default_delete<ServicePrincipalPolicy>>(&v12);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  else
  {
    *a1 = 0;
    if ( hKey )
      RegCloseKey(hKey);
  }
  return a1;
}

```

## disassembly

```asm
0x18002e48c  mov     [rsp-8+arg_0], rbx
0x18002e491  mov     [rsp-8+arg_8], rdi
0x18002e496  push    rbp
0x18002e497  mov     rbp, rsp
0x18002e49a  sub     rsp, 40h
0x18002e49e  mov     rax, r8
0x18002e4a1  mov     r10, rdx
0x18002e4a4  mov     rbx, rcx
0x18002e4a7  mov     [rbp+hKey], 0
0x18002e4af  lea     rcx, [rbp+hKey]
0x18002e4b3  mov     [rsp+40h+phkResult], rcx; phkResult
0x18002e4b8  mov     r9d, 20019h; samDesired
0x18002e4be  xor     r8d, r8d; ulOptions
0x18002e4c1  mov     rdx, rax; lpSubKey
0x18002e4c4  mov     rcx, r10; hKey
0x18002e4c7  call    cs:__imp_RegOpenKeyExW
0x18002e4cd  test    eax, eax
0x18002e4cf  jg      short loc_18002E4D5
0x18002e4d1  mov     ecx, eax
0x18002e4d3  jmp     short loc_18002E4DE
0x18002e4d5  movzx   ecx, ax
0x18002e4d8  or      ecx, 0C0070000h
0x18002e4de  test    ecx, ecx
0x18002e4e0  jns     short loc_18002E500
0x18002e4e2  cmp     eax, 2
0x18002e4e5  jz      short loc_18002E500
0x18002e4e7  mov     qword ptr [rbx], 0
0x18002e4ee  mov     rcx, [rbp+hKey]; hKey
0x18002e4f2  test    rcx, rcx
0x18002e4f5  jz      short loc_18002E55C
0x18002e4f7  call    cs:__imp_RegCloseKey
0x18002e4fd  nop
0x18002e4fe  jmp     short loc_18002E55C
0x18002e500  xor     edi, edi
0x18002e502  mov     rax, [rbp+hKey]
0x18002e506  test    rax, rax
0x18002e509  jz      short loc_18002E516
0x18002e50b  mov     rdi, rax
0x18002e50e  mov     [rbp+hKey], 0
0x18002e516  mov     ecx, 28h ; '('; Size
0x18002e51b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e520  mov     [rbp+var_8], rax
0x18002e524  mov     rdx, rdi
0x18002e527  mov     rcx, rax
0x18002e52a  call    ??0ServicePrincipalPolicy@@AEAA@PEAUHKEY__@@_NAEAV?$vector@VServicePrincipalPolicyDefaultEntry@@V?$allocator@VServicePrincipalPolicyDefaultEntry@@@utl@@@utl@@@Z; ServicePrincipalPolicy::ServicePrincipalPolicy(HKEY__ *,bool,utl::vector<ServicePrincipalPolicyDefaultEntry,utl::allocator<ServicePrincipalPolicyDefaultEntry>> &)
0x18002e52f  nop
0x18002e530  mov     [rbp+var_8], rax
0x18002e534  lea     rcx, [rbp+var_8]
0x18002e538  test    rax, rax
0x18002e53b  jnz     short loc_18002E542
0x18002e53d  mov     [rbx], rax
0x18002e540  jmp     short loc_18002E54D
0x18002e542  mov     [rbp+var_8], 0
0x18002e54a  mov     [rbx], rax
0x18002e54d  call    ??1?$unique_ptr@VServicePrincipalPolicy@@U?$default_delete@VServicePrincipalPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<ServicePrincipalPolicy,utl::default_delete<ServicePrincipalPolicy>>::~unique_ptr<ServicePrincipalPolicy,utl::default_delete<ServicePrincipalPolicy>>(void)
0x18002e552  nop
0x18002e553  lea     rcx, [rbp+hKey]
0x18002e557  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002e55c  mov     rax, rbx
0x18002e55f  mov     rbx, [rsp+40h+arg_0]
0x18002e564  mov     rdi, [rsp+40h+arg_8]
0x18002e569  add     rsp, 40h
0x18002e56d  pop     rbp
0x18002e56e  retn
```
