# CMVEngine::RetrieveSettingsGroupsToUpdateFromRegistry(__MIDL___MIDL_itf_mvengine_0000_0000_0001,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18001e83c`
- end: `0x18001eaab`
- name: `?RetrieveSettingsGroupsToUpdateFromRegistry@CMVEngine@@CAJW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `623`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180018698`

## callees

- `0x1800098dc`
- `0x180009900`
- `0x18000b030`
- `0x18000f56c`
- `0x180013de0`
- `0x18001e83c`
- `0x180021c5c`
- `0x180043750`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001e882`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ea5f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001e882`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001ea5f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e904`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e904`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001e990`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001e990`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e919`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e952`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ea78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e919`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e952`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ea78`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMVEngine::RetrieveSettingsGroupsToUpdateFromRegistry(unsigned int a1, __int64 *a2)
{
  __int64 v4; // r14
  __int64 i; // rsi
  int DeviceUpdateSettingsGroupRegKey; // eax
  unsigned int v7; // esi
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int v11; // edi
  DWORD v12; // r14d
  unsigned __int64 v13; // r8
  char v14; // al
  __int64 v15; // rcx
  __int64 v16; // rsi
  void **v17; // rdx
  const char *v18; // r9
  int phkResult; // [rsp+20h] [rbp-498h]
  unsigned int phkResulta; // [rsp+20h] [rbp-498h]
  DWORD cchValueName; // [rsp+40h] [rbp-478h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-470h] BYREF
  void *v23[3]; // [rsp+50h] [rbp-468h] BYREF
  unsigned __int64 v24; // [rsp+68h] [rbp-450h]
  WCHAR ValueName[264]; // [rsp+70h] [rbp-448h] BYREF
  WCHAR SubKey[264]; // [rsp+280h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+0h]

  v4 = a2[1];
  for ( i = *a2; i != v4; i += 32 )
  {
    if ( *(_QWORD *)(i + 24) >= 8u )
      operator delete(*(void **)i);
    *(_QWORD *)(i + 24) = 7;
    *(_QWORD *)(i + 16) = 0;
    *(_WORD *)i = 0;
  }
  a2[1] = *a2;
  DeviceUpdateSettingsGroupRegKey = GetDeviceUpdateSettingsGroupRegKey(a1);
  v7 = DeviceUpdateSettingsGroupRegKey;
  if ( DeviceUpdateSettingsGroupRegKey < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD9,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
      (const char *)(unsigned int)DeviceUpdateSettingsGroupRegKey,
      phkResult);
    return v7;
  }
  hKey = 0;
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  if ( v9 == 2 )
    goto LABEL_9;
  if ( !v9 )
  {
    v12 = 0;
    while ( 1 )
    {
      cchValueName = 260;
      v9 = RegEnumValueW(hKey, v12, ValueName, &cchValueName, 0, 0, 0, 0);
      if ( v9 == 259 )
        break;
      if ( v9 )
      {
        v10 = 3052;
        goto LABEL_14;
      }
      v24 = 7;
      v23[2] = 0;
      LOWORD(v23[0]) = 0;
      if ( ValueName[0] )
      {
        v13 = -1;
        do
          ++v13;
        while ( ValueName[v13] );
      }
      else
      {
        v13 = 0;
      }
      try
      {
        std::wstring::assign(v23, (char *)ValueName, v13);
        if ( (unsigned __int64)v23 >= a2[1] || (v14 = 1, *a2 > (unsigned __int64)v23) )
          v14 = 0;
        v15 = a2[2];
        if ( v14 )
        {
          v16 = *a2;
          if ( a2[1] == v15 )
            std::vector<std::wstring>::_Reserve(a2);
          v17 = (void **)(*a2 + (((unsigned __int64)v23 - v16) & 0xFFFFFFFFFFFFFFE0uLL));
        }
        else
        {
          if ( a2[1] == v15 )
            std::vector<std::wstring>::_Reserve(a2);
          v17 = v23;
        }
        std::wstring::wstring((_QWORD *)a2[1], v17);
        a2[1] += 32;
        if ( v24 >= 8 )
          operator delete(v23[0]);
        ++v12;
      }
      catch ( ... )
      {
        cchValueName = wil::details::in1diag3::Return_CaughtException(
                         retaddr,
                         (void *)0xBF2,
                         (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
                         v18);
        if ( hKey )
          RegCloseKey(hKey);
        return cchValueName;
      }
    }
LABEL_9:
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  v10 = 3040;
LABEL_14:
  v11 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)v10,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\engine\\src\\provisionengine.cpp",
          (const char *)v9,
          phkResulta);
  if ( hKey )
    RegCloseKey(hKey);
  return v11;
}

```

## disassembly

```asm
0x18001e83c  mov     [rsp+arg_10], rbx
0x18001e841  mov     [rsp+arg_18], rsi
0x18001e846  push    rdi
0x18001e847  push    r14
0x18001e849  push    r15
0x18001e84b  sub     rsp, 4A0h
0x18001e852  mov     rax, cs:__security_cookie
0x18001e859  xor     rax, rsp
0x18001e85c  mov     [rsp+4B8h+var_28], rax
0x18001e864  mov     rdi, rdx
0x18001e867  mov     r15d, ecx
0x18001e86a  mov     r14, [rdx+8]
0x18001e86e  mov     rsi, [rdx]
0x18001e871  xor     ebx, ebx
0x18001e873  cmp     rsi, r14
0x18001e876  jz      short loc_18001E89D
0x18001e878  cmp     qword ptr [rsi+18h], 8
0x18001e87d  jb      short loc_18001E888
0x18001e87f  mov     rcx, [rsi]
0x18001e882  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001e888  mov     qword ptr [rsi+18h], 7
0x18001e890  mov     [rsi+10h], rbx
0x18001e894  mov     [rsi], bx
0x18001e897  add     rsi, 20h ; ' '
0x18001e89b  jmp     short loc_18001E873
0x18001e89d  mov     rax, [rdi]
0x18001e8a0  mov     [rdi+8], rax
0x18001e8a4  lea     rdx, [rsp+4B8h+SubKey]
0x18001e8ac  mov     ecx, r15d
0x18001e8af  call    ?GetDeviceUpdateSettingsGroupRegKey@@YAJW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@PEAGK@Z; GetDeviceUpdateSettingsGroupRegKey(__MIDL___MIDL_itf_mvengine_0000_0000_0001,ushort *,ulong)
0x18001e8b4  mov     esi, eax
0x18001e8b6  test    eax, eax
0x18001e8b8  jns     short loc_18001E8DD
0x18001e8ba  mov     rcx, [rsp+4B8h]; this
0x18001e8c2  mov     r9d, eax; char *
0x18001e8c5  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001e8cc  mov     edx, 0BD9h; void *
0x18001e8d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e8d6  mov     eax, esi
0x18001e8d8  jmp     loc_18001EA82
0x18001e8dd  mov     [rsp+4B8h+hKey], rbx
0x18001e8e2  lea     rax, [rsp+4B8h+hKey]
0x18001e8e7  mov     [rsp+4B8h+phkResult], rax; unsigned int
0x18001e8ec  mov     r9d, 20019h; samDesired
0x18001e8f2  xor     r8d, r8d; ulOptions
0x18001e8f5  lea     rdx, [rsp+4B8h+SubKey]; lpSubKey
0x18001e8fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e904  call    cs:__imp_RegOpenKeyExW
0x18001e90a  cmp     eax, 2
0x18001e90d  jnz     short loc_18001E926
0x18001e90f  mov     rcx, [rsp+4B8h+hKey]; hKey
0x18001e914  test    rcx, rcx
0x18001e917  jz      short loc_18001E91F
0x18001e919  call    cs:__imp_RegCloseKey
0x18001e91f  xor     eax, eax
0x18001e921  jmp     loc_18001EA82
0x18001e926  test    eax, eax
0x18001e928  jz      short loc_18001E95F
0x18001e92a  mov     edx, 0BE0h; void *
0x18001e92f  lea     r8, aOnecoreuapAdmi_18; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001e936  mov     r9d, eax; char *
0x18001e939  mov     rcx, [rsp+4B8h]; this
0x18001e941  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001e946  mov     edi, eax
0x18001e948  mov     rcx, [rsp+4B8h+hKey]; hKey
0x18001e94d  test    rcx, rcx
0x18001e950  jz      short loc_18001E958
0x18001e952  call    cs:__imp_RegCloseKey
0x18001e958  mov     eax, edi
0x18001e95a  jmp     loc_18001EA82
0x18001e95f  mov     r14d, ebx
0x18001e962  mov     [rsp+4B8h+cchValueName], 104h
0x18001e96a  mov     [rsp+4B8h+lpcbData], rbx; lpcbData
0x18001e96f  mov     [rsp+4B8h+lpData], rbx; lpData
0x18001e974  mov     [rsp+4B8h+lpType], rbx; lpType
0x18001e979  mov     [rsp+4B8h+phkResult], rbx; lpReserved
0x18001e97e  lea     r9, [rsp+4B8h+cchValueName]; lpcchValueName
0x18001e983  lea     r8, [rsp+4B8h+ValueName]; lpValueName
0x18001e988  mov     edx, r14d; dwIndex
0x18001e98b  mov     rcx, [rsp+4B8h+hKey]; hKey
0x18001e990  call    cs:__imp_RegEnumValueW
0x18001e996  cmp     eax, 103h
0x18001e99b  jz      loc_18001E90F
0x18001e9a1  test    eax, eax
0x18001e9a3  jz      short loc_18001E9AC
0x18001e9a5  mov     edx, 0BECh
0x18001e9aa  jmp     short loc_18001E92F
0x18001e9ac  mov     [rsp+4B8h+var_450], 7
0x18001e9b5  mov     [rsp+4B8h+var_458], rbx
0x18001e9ba  mov     word ptr [rsp+4B8h+var_468], bx
0x18001e9bf  cmp     [rsp+4B8h+ValueName], bx
0x18001e9c4  jnz     short loc_18001E9CB
0x18001e9c6  mov     r8, rbx
0x18001e9c9  jmp     short loc_18001E9DE
0x18001e9cb  lea     rax, [rsp+4B8h+ValueName]
0x18001e9d0  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001e9d4  inc     r8
0x18001e9d7  cmp     [rax+r8*2], bx
0x18001e9dc  jnz     short loc_18001E9D4
0x18001e9de  lea     rdx, [rsp+4B8h+ValueName]; Src
0x18001e9e3  lea     rcx, [rsp+4B8h+var_468]; void *
0x18001e9e8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001e9ed  nop
0x18001e9ee  lea     rax, [rsp+4B8h+var_468]
0x18001e9f3  cmp     rax, [rdi+8]
0x18001e9f7  jnb     short loc_18001EA05
0x18001e9f9  lea     rax, [rsp+4B8h+var_468]
0x18001e9fe  cmp     [rdi], rax
0x18001ea01  mov     al, 1
0x18001ea03  jbe     short loc_18001EA07
0x18001ea05  mov     al, bl
0x18001ea07  mov     rcx, [rdi+10h]
0x18001ea0b  test    al, al
0x18001ea0d  jz      short loc_18001EA31
0x18001ea0f  mov     rsi, [rdi]
0x18001ea12  cmp     [rdi+8], rcx
0x18001ea16  jnz     short loc_18001EA20
0x18001ea18  mov     rcx, rdi
0x18001ea1b  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x18001ea20  lea     rdx, [rsp+4B8h+var_468]
0x18001ea25  sub     rdx, rsi
0x18001ea28  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001ea2c  add     rdx, [rdi]
0x18001ea2f  jmp     short loc_18001EA44
0x18001ea31  cmp     [rdi+8], rcx
0x18001ea35  jnz     short loc_18001EA3F
0x18001ea37  mov     rcx, rdi
0x18001ea3a  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x18001ea3f  lea     rdx, [rsp+4B8h+var_468]
0x18001ea44  mov     rcx, [rdi+8]
0x18001ea48  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18001ea4d  add     qword ptr [rdi+8], 20h ; ' '
0x18001ea52  cmp     [rsp+4B8h+var_450], 8
0x18001ea58  jb      short loc_18001EA66
0x18001ea5a  mov     rcx, [rsp+4B8h+var_468]
0x18001ea5f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001ea65  nop
0x18001ea66  inc     r14d
0x18001ea69  jmp     loc_18001E962
0x18001ea6e  mov     rcx, [rsp+4B8h+hKey]; hKey
0x18001ea73  test    rcx, rcx
0x18001ea76  jz      short loc_18001EA7E
0x18001ea78  call    cs:__imp_RegCloseKey
0x18001ea7e  mov     eax, [rsp+4B8h+cchValueName]
0x18001ea82  mov     rcx, [rsp+4B8h+var_28]
0x18001ea8a  xor     rcx, rsp; StackCookie
0x18001ea8d  call    __security_check_cookie
0x18001ea92  lea     r11, [rsp+4B8h+var_18]
0x18001ea9a  mov     rbx, [r11+30h]
0x18001ea9e  mov     rsi, [r11+38h]
0x18001eaa2  mov     rsp, r11
0x18001eaa5  pop     r15
0x18001eaa7  pop     r14
0x18001eaa9  pop     rdi
0x18001eaaa  retn
```
