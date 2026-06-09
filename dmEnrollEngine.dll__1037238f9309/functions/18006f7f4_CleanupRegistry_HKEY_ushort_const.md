# CleanupRegistry(HKEY__ *,ushort const *)

- ea: `0x18006f7f4`
- end: `0x18006f9d8`
- name: `?CleanupRegistry@@YAJPEAUHKEY__@@PEBG@Z`
- size: `484`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18006c5d0`
- `0x18006e640`

## callees

- `0x1800071c0`
- `0x18006f7f4`
- `0x18006f9e0`
- `0x18006fc08`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18006f8de`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18006f8de`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006f946`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006f946`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006f8ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006f8ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f99a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006f99a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18006f976`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18006f976`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CleanupRegistry(HKEY hKey, LPCWSTR lpSubKey)
{
  unsigned int v4; // edi
  signed int AllSubKeys; // ebx
  const WCHAR **v6; // rsi
  const WCHAR **v7; // r14
  const WCHAR *v8; // r15
  LSTATUS v9; // eax
  LSTATUS v10; // eax
  unsigned int v11; // ecx
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  const WCHAR **v15; // [rsp+60h] [rbp-20h] BYREF
  __int64 v16; // [rsp+68h] [rbp-18h]
  const WCHAR ***v17; // [rsp+70h] [rbp-10h]
  unsigned int v18; // [rsp+78h] [rbp-8h]
  char v19; // [rsp+7Ch] [rbp-4h]
  DWORD cSubKeys; // [rsp+D0h] [rbp+50h] BYREF
  HKEY hKeya; // [rsp+D8h] [rbp+58h] BYREF

  v15 = 0;
  v16 = 0;
  v4 = 0;
  wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v15);
  v18 = 0;
  v17 = &v15;
  v19 = 1;
  AllSubKeys = RegistryGetAllSubKeys(hKey);
  if ( v19 )
    v17[1] = (const WCHAR **)v18;
  if ( AllSubKeys == -2147024894 )
  {
    AllSubKeys = 0;
  }
  else if ( AllSubKeys >= 0 )
  {
    v6 = v15;
    v7 = &v15[v16];
    while ( v6 != v7 )
    {
      v8 = *v6;
      hKeya = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKeya,
        0);
      v9 = RegOpenKeyExW(hKey, v8, 0, 0x10009u, &hKeya);
      AllSubKeys = v9;
      if ( v9 > 0 )
        AllSubKeys = (unsigned __int16)v9 | 0x80070000;
      if ( AllSubKeys < 0 )
        goto LABEL_23;
      v10 = RegDeleteTreeW(hKeya, lpSubKey);
      v11 = v10;
      if ( v10 > 0 )
        v11 = (unsigned __int16)v10 | 0x80070000;
      if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147024894 )
        v4 = v11;
      cSubKeys = 0;
      v12 = RegQueryInfoKeyW(hKeya, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
      AllSubKeys = v12;
      if ( v12 > 0 )
        AllSubKeys = (unsigned __int16)v12 | 0x80070000;
      if ( AllSubKeys < 0 )
        goto LABEL_23;
      if ( !cSubKeys )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hKeya,
          0);
        v13 = RegDeleteKeyW(hKey, v8);
        AllSubKeys = v13;
        if ( v13 > 0 )
          AllSubKeys = (unsigned __int16)v13 | 0x80070000;
        if ( AllSubKeys < 0 )
LABEL_23:
          v4 = AllSubKeys;
      }
      if ( hKeya )
        RegCloseKey(hKeya);
      ++v6;
    }
  }
  else
  {
    v4 = AllSubKeys;
  }
  if ( !v4 )
    v4 = AllSubKeys;
  wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::reset(&v15);
  return v4;
}

```

## disassembly

```asm
0x18006f7f4  mov     [rsp-38h+arg_0], rbx
0x18006f7f9  push    rbp
0x18006f7fa  push    rsi
0x18006f7fb  push    rdi
0x18006f7fc  push    r12
0x18006f7fe  push    r13
0x18006f800  push    r14
0x18006f802  push    r15
0x18006f804  mov     rbp, rsp
0x18006f807  sub     rsp, 80h
0x18006f80e  mov     r12, rcx
0x18006f811  mov     [rbp+var_20], 0
0x18006f819  lea     rcx, [rbp+var_20]
0x18006f81d  mov     [rbp+var_18], 0
0x18006f825  mov     r13, rdx
0x18006f828  xor     edi, edi
0x18006f82a  call    ?reset@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18006f82f  lea     rax, [rbp+var_20]
0x18006f833  mov     [rbp+var_8], edi
0x18006f836  lea     r8, [rbp+var_20]
0x18006f83a  mov     [rbp+var_10], rax
0x18006f83e  lea     rdx, [rbp+var_8]
0x18006f842  mov     [rbp+var_4], 1
0x18006f846  mov     rcx, r12; hKey
0x18006f849  call    RegistryGetAllSubKeys
0x18006f84e  mov     ebx, eax
0x18006f850  cmp     [rbp+var_4], dil
0x18006f854  jz      short loc_18006F861
0x18006f856  mov     rax, [rbp+var_10]
0x18006f85a  mov     ecx, [rbp+var_8]
0x18006f85d  mov     [rax+8], rcx
0x18006f861  cmp     ebx, 80070002h
0x18006f867  jnz     short loc_18006F870
0x18006f869  xor     ebx, ebx
0x18006f86b  jmp     loc_18006F9AD
0x18006f870  test    ebx, ebx
0x18006f872  jns     short loc_18006F87B
0x18006f874  mov     edi, ebx
0x18006f876  jmp     loc_18006F9AD
0x18006f87b  mov     rsi, [rbp+var_20]
0x18006f87f  mov     rax, [rbp+var_18]
0x18006f883  lea     r14, [rsi+rax*8]
0x18006f887  jmp     loc_18006F9A4
0x18006f88c  mov     r15, [rsi]
0x18006f88f  lea     rcx, [rbp+hKey]
0x18006f893  xor     edx, edx
0x18006f895  mov     [rbp+hKey], 0
0x18006f89d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18006f8a2  lea     rax, [rbp+hKey]
0x18006f8a6  mov     r9d, 10009h; samDesired
0x18006f8ac  xor     r8d, r8d; ulOptions
0x18006f8af  mov     [rsp+80h+phkResult], rax; phkResult
0x18006f8b4  mov     rdx, r15; lpSubKey
0x18006f8b7  mov     rcx, r12; hKey
0x18006f8ba  call    cs:__imp_RegOpenKeyExW
0x18006f8c0  mov     ebx, eax
0x18006f8c2  test    eax, eax
0x18006f8c4  jle     short loc_18006F8CF
0x18006f8c6  movzx   ebx, ax
0x18006f8c9  or      ebx, 80070000h
0x18006f8cf  test    ebx, ebx
0x18006f8d1  js      loc_18006F98F
0x18006f8d7  mov     rcx, [rbp+hKey]; hKey
0x18006f8db  mov     rdx, r13; lpSubKey
0x18006f8de  call    cs:__imp_RegDeleteTreeW
0x18006f8e4  xor     edx, edx; lpClass
0x18006f8e6  mov     ecx, eax
0x18006f8e8  test    eax, eax
0x18006f8ea  jle     short loc_18006F8F5
0x18006f8ec  movzx   ecx, ax
0x18006f8ef  or      ecx, 80070000h
0x18006f8f5  mov     r8d, 80000000h
0x18006f8fb  lea     eax, [rcx+r8]
0x18006f8ff  test    r8d, eax
0x18006f902  jnz     short loc_18006F90D
0x18006f904  cmp     ecx, 80070002h
0x18006f90a  cmovnz  edi, ecx
0x18006f90d  mov     rcx, [rbp+hKey]; hKey
0x18006f911  lea     rax, [rbp+cSubKeys]
0x18006f915  mov     [rsp+80h+lpftLastWriteTime], rdx; lpftLastWriteTime
0x18006f91a  xor     r9d, r9d; lpReserved
0x18006f91d  mov     [rsp+80h+lpcbSecurityDescriptor], rdx; lpcbSecurityDescriptor
0x18006f922  xor     r8d, r8d; lpcchClass
0x18006f925  mov     [rsp+80h+lpcbMaxValueLen], rdx; lpcbMaxValueLen
0x18006f92a  mov     [rsp+80h+lpcbMaxValueNameLen], rdx; lpcbMaxValueNameLen
0x18006f92f  mov     [rsp+80h+lpcValues], rdx; lpcValues
0x18006f934  mov     [rsp+80h+lpcbMaxClassLen], rdx; lpcbMaxClassLen
0x18006f939  mov     [rsp+80h+lpcbMaxSubKeyLen], rdx; lpcbMaxSubKeyLen
0x18006f93e  mov     [rsp+80h+phkResult], rax; lpcSubKeys
0x18006f943  mov     [rbp+cSubKeys], edx
0x18006f946  call    cs:__imp_RegQueryInfoKeyW
0x18006f94c  mov     ebx, eax
0x18006f94e  test    eax, eax
0x18006f950  jle     short loc_18006F95B
0x18006f952  movzx   ebx, ax
0x18006f955  or      ebx, 80070000h
0x18006f95b  test    ebx, ebx
0x18006f95d  js      short loc_18006F98F
0x18006f95f  cmp     [rbp+cSubKeys], 0
0x18006f963  jnz     short loc_18006F991
0x18006f965  xor     edx, edx
0x18006f967  lea     rcx, [rbp+hKey]
0x18006f96b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18006f970  mov     rdx, r15; lpSubKey
0x18006f973  mov     rcx, r12; hKey
0x18006f976  call    cs:__imp_RegDeleteKeyW
0x18006f97c  mov     ebx, eax
0x18006f97e  test    eax, eax
0x18006f980  jle     short loc_18006F98B
0x18006f982  movzx   ebx, ax
0x18006f985  or      ebx, 80070000h
0x18006f98b  test    ebx, ebx
0x18006f98d  jns     short loc_18006F991
0x18006f98f  mov     edi, ebx
0x18006f991  mov     rcx, [rbp+hKey]; hKey
0x18006f995  test    rcx, rcx
0x18006f998  jz      short loc_18006F9A0
0x18006f99a  call    cs:__imp_RegCloseKey
0x18006f9a0  add     rsi, 8
0x18006f9a4  cmp     rsi, r14
0x18006f9a7  jnz     loc_18006F88C
0x18006f9ad  test    edi, edi
0x18006f9af  lea     rcx, [rbp+var_20]
0x18006f9b3  cmovz   edi, ebx
0x18006f9b6  call    ?reset@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::reset(void)
0x18006f9bb  mov     rbx, [rsp+80h+arg_0]
0x18006f9c3  mov     eax, edi
0x18006f9c5  add     rsp, 80h
0x18006f9cc  pop     r15
0x18006f9ce  pop     r14
0x18006f9d0  pop     r13
0x18006f9d2  pop     r12
0x18006f9d4  pop     rdi
0x18006f9d5  pop     rsi
0x18006f9d6  pop     rbp
0x18006f9d7  retn
```
