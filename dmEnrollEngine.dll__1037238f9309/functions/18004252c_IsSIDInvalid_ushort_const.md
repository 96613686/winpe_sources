# IsSIDInvalid(ushort const *)

- ea: `0x18004252c`
- end: `0x18004262e`
- name: `?IsSIDInvalid@@YAHPEBG@Z`
- size: `258`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001a9dc`
- `0x18006f0d0`

## callees

- `0x18001e770`
- `0x18004252c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004257d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800425c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004257d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800425c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800425e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800425f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042607`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042616`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800425e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800425f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042607`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180042616`

## pseudocode

```c
__int64 __fastcall IsSIDInvalid(LPCWSTR lpSubKey)
{
  LSTATUS v2; // ebx
  HKEY v3; // rcx
  LSTATUS v4; // ebx
  HKEY *p_hKey; // [rsp+30h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-18h] BYREF
  char v8; // [rsp+40h] [rbp-10h]
  HKEY hKey; // [rsp+68h] [rbp+18h] BYREF
  HKEY v10; // [rsp+70h] [rbp+20h] BYREF

  hKey = 0;
  p_hKey = &hKey;
  phkResult = 0;
  v8 = 1;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
         0,
         0x20019u,
         &phkResult);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  v3 = hKey;
  if ( !v2 )
  {
    v10 = 0;
    p_hKey = &v10;
    phkResult = 0;
    v8 = 1;
    v4 = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &phkResult);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v4 == 2 )
    {
      if ( v10 )
        RegCloseKey(v10);
      if ( hKey )
        RegCloseKey(hKey);
      return 1;
    }
    if ( v10 )
      RegCloseKey(v10);
    v3 = hKey;
  }
  if ( v3 )
    RegCloseKey(v3);
  return 0;
}

```

## disassembly

```asm
0x18004252c  mov     [rsp-8+arg_0], rbx
0x180042531  mov     [rsp-8+arg_18], rdi
0x180042536  push    rbp
0x180042537  mov     rbp, rsp
0x18004253a  sub     rsp, 50h
0x18004253e  lea     rax, [rbp+hKey]
0x180042542  mov     [rbp+hKey], 0
0x18004254a  mov     [rbp+var_20], rax
0x18004254e  lea     rdx, aSoftwareMicros_15; "Software\\Microsoft\\Windows NT\\Curren"...
0x180042555  lea     rax, [rbp+var_18]
0x180042559  mov     [rbp+var_18], 0
0x180042561  mov     rdi, rcx
0x180042564  mov     [rsp+50h+phkResult], rax; phkResult
0x180042569  mov     r9d, 20019h; samDesired
0x18004256f  mov     [rbp+var_10], 1
0x180042573  xor     r8d, r8d; ulOptions
0x180042576  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004257d  call    cs:__imp_RegOpenKeyExW
0x180042583  lea     rcx, [rbp+var_20]
0x180042587  mov     ebx, eax
0x180042589  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18004258e  mov     rcx, [rbp+hKey]; hKey
0x180042592  test    ebx, ebx
0x180042594  jnz     short loc_180042611
0x180042596  lea     rax, [rbp+arg_10]
0x18004259a  mov     [rbp+arg_10], 0
0x1800425a2  mov     [rbp+var_20], rax
0x1800425a6  mov     r9d, 20019h; samDesired
0x1800425ac  lea     rax, [rbp+var_18]
0x1800425b0  mov     [rbp+var_18], 0
0x1800425b8  xor     r8d, r8d; ulOptions
0x1800425bb  mov     [rsp+50h+phkResult], rax; phkResult
0x1800425c0  mov     rdx, rdi; lpSubKey
0x1800425c3  mov     [rbp+var_10], 1
0x1800425c7  call    cs:__imp_RegOpenKeyExW
0x1800425cd  lea     rcx, [rbp+var_20]
0x1800425d1  mov     ebx, eax
0x1800425d3  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800425d8  mov     rcx, [rbp+arg_10]; hKey
0x1800425dc  cmp     ebx, 2
0x1800425df  jnz     short loc_180042602
0x1800425e1  test    rcx, rcx
0x1800425e4  jz      short loc_1800425EC
0x1800425e6  call    cs:__imp_RegCloseKey
0x1800425ec  mov     rcx, [rbp+hKey]; hKey
0x1800425f0  test    rcx, rcx
0x1800425f3  jz      short loc_1800425FB
0x1800425f5  call    cs:__imp_RegCloseKey
0x1800425fb  mov     eax, 1
0x180042600  jmp     short loc_18004261E
0x180042602  test    rcx, rcx
0x180042605  jz      short loc_18004260D
0x180042607  call    cs:__imp_RegCloseKey
0x18004260d  mov     rcx, [rbp+hKey]; hKey
0x180042611  test    rcx, rcx
0x180042614  jz      short loc_18004261C
0x180042616  call    cs:__imp_RegCloseKey
0x18004261c  xor     eax, eax
0x18004261e  mov     rbx, [rsp+50h+arg_0]
0x180042623  mov     rdi, [rsp+50h+arg_18]
0x180042628  add     rsp, 50h
0x18004262c  pop     rbp
0x18004262d  retn
```
