# Microsoft::IoT::ShellExtension::CAppManager::AddBackgroundTask(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180015be8`
- end: `0x180015cc7`
- name: `?AddBackgroundTask@CAppManager@ShellExtension@IoT@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `223`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011b30`

## callees

- `0x180010558`
- `0x180014f58`
- `0x180015be8`
- `0x180017ab8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180015ca2`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180015ca2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015c7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015c7d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015c42`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015c42`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::IoT::ShellExtension::CAppManager::AddBackgroundTask(__int64 a1)
{
  const WCHAR *v2; // rax
  unsigned int v3; // eax
  unsigned int v4; // r8d
  __int64 v5; // rdx
  const WCHAR *v6; // rax
  unsigned int v7; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  HKEY hKey; // [rsp+68h] [rbp+10h] BYREF

  hKey = 0;
  v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(qword_180026650);
  v3 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v2, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v3 )
  {
    v5 = 86;
  }
  else
  {
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    v3 = RegSetValueExW(hKey, v6, 0, 4u, 0, 0);
    if ( v3 )
    {
      v5 = 88;
    }
    else
    {
      v3 = RegFlushKey(hKey);
      if ( !v3 )
      {
        v7 = 0;
        goto LABEL_9;
      }
      v5 = 90;
    }
  }
  v7 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v5, v4, (const char *)v3, dwOptions);
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v7;
}

```

## disassembly

```asm
0x180015be8  push    rbx
0x180015bea  sub     rsp, 50h
0x180015bee  mov     rbx, rcx
0x180015bf1  mov     [rsp+58h+hKey], 0
0x180015bfa  lea     rcx, qword_180026650
0x180015c01  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015c06  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180015c0f  mov     rdx, rax; lpSubKey
0x180015c12  lea     rax, [rsp+58h+hKey]
0x180015c17  xor     r9d, r9d; lpClass
0x180015c1a  mov     [rsp+58h+phkResult], rax; phkResult
0x180015c1f  xor     r8d, r8d; Reserved
0x180015c22  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180015c2b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015c32  mov     [rsp+58h+samDesired], 20006h; samDesired
0x180015c3a  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180015c42  call    cs:__imp_RegCreateKeyExW
0x180015c48  test    eax, eax
0x180015c4a  jz      short loc_180015C53
0x180015c4c  mov     edx, 56h ; 'V'
0x180015c51  jmp     short loc_180015C8C
0x180015c53  mov     rcx, rbx
0x180015c56  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180015c5b  mov     rcx, [rsp+58h+hKey]; hKey
0x180015c60  mov     rdx, rax; lpValueName
0x180015c63  mov     [rsp+58h+samDesired], 0; cbData
0x180015c6b  mov     r9d, 4; dwType
0x180015c71  xor     r8d, r8d; Reserved
0x180015c74  mov     qword ptr [rsp+58h+dwOptions], 0; unsigned int
0x180015c7d  call    cs:__imp_RegSetValueExW
0x180015c83  test    eax, eax
0x180015c85  jz      short loc_180015C9D
0x180015c87  mov     edx, 58h ; 'X'; void *
0x180015c8c  mov     rcx, [rsp+58h]; this
0x180015c91  mov     r9d, eax; char *
0x180015c94  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180015c99  mov     ebx, eax
0x180015c9b  jmp     short loc_180015CB5
0x180015c9d  mov     rcx, [rsp+58h+hKey]; hKey
0x180015ca2  call    cs:__imp_RegFlushKey
0x180015ca8  test    eax, eax
0x180015caa  jz      short loc_180015CB3
0x180015cac  mov     edx, 5Ah ; 'Z'
0x180015cb1  jmp     short loc_180015C8C
0x180015cb3  xor     ebx, ebx
0x180015cb5  lea     rcx, [rsp+58h+hKey]
0x180015cba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180015cbf  mov     eax, ebx
0x180015cc1  add     rsp, 50h
0x180015cc5  pop     rbx
0x180015cc6  retn
```
