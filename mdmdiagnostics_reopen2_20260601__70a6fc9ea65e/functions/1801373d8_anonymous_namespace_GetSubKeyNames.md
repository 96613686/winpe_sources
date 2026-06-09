# _anonymous_namespace_::GetSubKeyNames

- ea: `0x1801373d8`
- end: `0x180137581`
- name: `_anonymous_namespace_::GetSubKeyNames`
- size: `425`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180135d94`
- `0x180137a54`
- `0x180137ea0`
- `0x180137fec`

## callees

- `0x180019080`
- `0x1800e68b0`
- `0x1800e7de8`
- `0x1800efd9c`
- `0x180105294`
- `0x180106b6c`
- `0x180106ee0`
- `0x180134e3c`
- `0x1801373d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18013748d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18013748d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801374f6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1801374f6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013742d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18013742d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall anonymous_namespace_::GetSubKeyNames(HKEY *a1, const WCHAR *a2, __int64 a3)
{
  HKEY v4; // rsi
  unsigned int v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // ebx
  DWORD i; // ebx
  __int64 v9; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v13; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v15[40]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+1E8h]

  v13 = 0;
  v4 = *a1;
  if ( a2 )
  {
    v13 = 0;
    v5 = RegOpenKeyExW(v4, a2, 0, 0x20019u, &v13);
    if ( v5 )
    {
      v6 = 31;
LABEL_7:
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v6,
             (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
             (const char *)v5,
             phkResult);
      goto LABEL_17;
    }
    v4 = v13;
  }
  cSubKeys = 0;
  std::vector<std::wstring>::clear(a3);
  v5 = RegQueryInfoKeyW(v4, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v5 )
  {
    v6 = 56;
    goto LABEL_7;
  }
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = 260;
    v5 = RegEnumKeyExW(v4, i, Name, &cchName, 0, 0, 0, 0);
    if ( v5 )
    {
      v6 = 60;
      goto LABEL_7;
    }
    std::wstring::wstring(v15, Name);
    v9 = *(_QWORD *)(a3 + 8);
    if ( v9 == *(_QWORD *)(a3 + 16) )
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a3, v9, v15);
    else
      std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(a3, v15);
    std::wstring::_Tidy_deallocate(v15);
  }
  v7 = 0;
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v13);
  return v7;
}

```

## disassembly

```asm
0x1801373d8  push    rbp
0x1801373da  push    rbx
0x1801373db  push    rsi
0x1801373dc  push    rdi
0x1801373dd  push    r14
0x1801373df  lea     rbp, [rsp-1C0h]
0x1801373e7  sub     rsp, 2C0h
0x1801373ee  mov     rax, cs:__security_cookie
0x1801373f5  xor     rax, rsp
0x1801373f8  mov     [rbp+1E0h+var_30], rax
0x1801373ff  mov     rdi, r8
0x180137402  xor     r14d, r14d
0x180137405  mov     [rsp+2E0h+var_278], r14
0x18013740a  mov     rsi, [rcx]
0x18013740d  test    rdx, rdx
0x180137410  jz      short loc_180137448
0x180137412  mov     [rsp+2E0h+var_278], r14
0x180137417  lea     rax, [rsp+2E0h+var_278]
0x18013741c  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180137421  mov     r9d, 20019h; samDesired
0x180137427  xor     r8d, r8d; ulOptions
0x18013742a  mov     rcx, rsi; hKey
0x18013742d  call    cs:__imp_RegOpenKeyExW
0x180137434  nop     dword ptr [rax+rax+00h]
0x180137439  test    eax, eax
0x18013743b  jz      short loc_180137443
0x18013743d  lea     edx, [r14+1Fh]
0x180137441  jmp     short loc_1801374A2
0x180137443  mov     rsi, [rsp+2E0h+var_278]
0x180137448  mov     [rsp+2E0h+cSubKeys], r14d
0x18013744d  mov     rcx, rdi
0x180137450  call    ?clear@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXXZ; std::vector<std::wstring>::clear(void)
0x180137455  mov     [rsp+2E0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18013745a  mov     [rsp+2E0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18013745f  mov     [rsp+2E0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180137464  mov     [rsp+2E0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x180137469  mov     [rsp+2E0h+lpcValues], r14; lpcValues
0x18013746e  mov     [rsp+2E0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180137473  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x180137478  lea     rax, [rsp+2E0h+cSubKeys]
0x18013747d  mov     [rsp+2E0h+phkResult], rax; unsigned int
0x180137482  xor     r9d, r9d; lpReserved
0x180137485  xor     r8d, r8d; lpcchClass
0x180137488  xor     edx, edx; lpClass
0x18013748a  mov     rcx, rsi; hKey
0x18013748d  call    cs:__imp_RegQueryInfoKeyW
0x180137494  nop     dword ptr [rax+rax+00h]
0x180137499  test    eax, eax
0x18013749b  jz      short loc_1801374BF
0x18013749d  mov     edx, 38h ; '8'; void *
0x1801374a2  mov     rcx, [rbp+1E8h]; this
0x1801374a9  mov     r9d, eax; char *
0x1801374ac  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x1801374b3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801374b8  mov     ebx, eax
0x1801374ba  jmp     loc_180137557
0x1801374bf  mov     ebx, r14d
0x1801374c2  cmp     ebx, [rsp+2E0h+cSubKeys]
0x1801374c6  jnb     loc_180137554
0x1801374cc  mov     [rsp+2E0h+cchName], 104h
0x1801374d4  mov     [rsp+2E0h+lpcValues], r14; lpftLastWriteTime
0x1801374d9  mov     [rsp+2E0h+lpcbMaxClassLen], r14; lpcchClass
0x1801374de  mov     [rsp+2E0h+lpcbMaxSubKeyLen], r14; lpClass
0x1801374e3  mov     [rsp+2E0h+phkResult], r14; lpReserved
0x1801374e8  lea     r9, [rsp+2E0h+cchName]; lpcchName
0x1801374ed  lea     r8, [rbp+1E0h+Name]; lpName
0x1801374f1  mov     edx, ebx; dwIndex
0x1801374f3  mov     rcx, rsi; hKey
0x1801374f6  call    cs:__imp_RegEnumKeyExW
0x1801374fd  nop     dword ptr [rax+rax+00h]
0x180137502  test    eax, eax
0x180137504  jnz     short loc_18013754A
0x180137506  lea     rdx, [rbp+1E0h+Name]
0x18013750a  lea     rcx, [rsp+2E0h+var_268]
0x18013750f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180137514  nop
0x180137515  mov     rdx, [rdi+8]
0x180137519  mov     rcx, rdi
0x18013751c  cmp     rdx, [rdi+10h]
0x180137520  jz      short loc_18013752E
0x180137522  lea     rdx, [rsp+2E0h+var_268]
0x180137527  call    ??$_Emplace_back_with_unused_capacity@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_back_with_unused_capacity<std::wstring>(std::wstring &&)
0x18013752c  jmp     short loc_180137539
0x18013752e  lea     r8, [rsp+2E0h+var_268]
0x180137533  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180137538  nop
0x180137539  lea     rcx, [rsp+2E0h+var_268]
0x18013753e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180137543  inc     ebx
0x180137545  jmp     loc_1801374C2
0x18013754a  mov     edx, 3Ch ; '<'
0x18013754f  jmp     loc_1801374A2
0x180137554  mov     ebx, r14d
0x180137557  lea     rcx, [rsp+2E0h+var_278]
0x18013755c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180137561  mov     eax, ebx
0x180137563  mov     rcx, [rbp+1E0h+var_30]
0x18013756a  xor     rcx, rsp; StackCookie
0x18013756d  call    __security_check_cookie
0x180137572  add     rsp, 2C0h
0x180137579  pop     r14
0x18013757b  pop     rdi
0x18013757c  pop     rsi
0x18013757d  pop     rbx
0x18013757e  pop     rbp
0x18013757f  retn
```
