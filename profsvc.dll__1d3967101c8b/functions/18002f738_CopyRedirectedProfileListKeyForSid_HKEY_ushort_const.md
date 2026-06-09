# CopyRedirectedProfileListKeyForSid(HKEY__ *,ushort const *)

- ea: `0x18002f738`
- end: `0x18002f895`
- name: `?CopyRedirectedProfileListKeyForSid@@YAJPEAUHKEY__@@PEBG@Z`
- size: `349`
- prototype: `__int64 __fastcall(HKEY hKeySrc, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002b938`
- `0x180043c70`

## callees

- `0x180010f30`
- `0x1800111a0`
- `0x18001f060`
- `0x18002d2d8`
- `0x18002e648`
- `0x18002f738`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f81e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f85d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f86f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f81e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f85d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f86f`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18002f830`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18002f830`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f7f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002f7f1`

## string_xrefs

- `0x18002f78c`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18002f802`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x18002f841`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
__int64 __fastcall CopyRedirectedProfileListKeyForSid(HKEY hKeySrc, const unsigned __int16 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  unsigned int v5; // eax
  unsigned int v6; // eax
  DWORD dwOptions; // [rsp+20h] [rbp-50h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-50h]
  LPCWSTR lpSubKey[4]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]
  HKEY hKey; // [rsp+90h] [rbp+20h] BYREF

  memset(lpSubKey, 0, 24);
  v3 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%s\\%s",
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
         a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0, 1u, 0xF003Fu, 0, &hKey, 0);
    if ( v5 )
    {
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x70,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
             (const char *)v5,
             dwOptionsa);
      if ( hKey )
        RegCloseKey(hKey);
    }
    else
    {
      v6 = RegCopyTreeW(hKeySrc, 0, hKey);
      if ( v6 )
      {
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x72,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
               (const char *)v6,
               dwOptionsa);
        if ( hKey )
          RegCloseKey(hKey);
      }
      else
      {
        if ( hKey )
          RegCloseKey(hKey);
        v4 = 0;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
      (const char *)(unsigned int)v3,
      dwOptions);
  }
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free((__int64)lpSubKey);
  return v4;
}

```

## disassembly

```asm
0x18002f738  mov     [rsp-8+arg_0], rbx
0x18002f73d  mov     [rsp-8+arg_8], rdi
0x18002f742  push    rbp
0x18002f743  mov     rbp, rsp
0x18002f746  sub     rsp, 70h
0x18002f74a  mov     rdi, rcx
0x18002f74d  mov     [rbp+lpSubKey], 0
0x18002f755  mov     [rbp+var_18], 0
0x18002f75d  mov     [rbp+var_10], 0
0x18002f765  mov     r9, rdx
0x18002f768  lea     r8, aSoftwareMicros_34; "Software\\Microsoft\\Windows NT\\Curren"...
0x18002f76f  lea     rdx, aSS_0; "%s\\%s"
0x18002f776  lea     rcx, [rbp+lpSubKey]
0x18002f77a  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18002f77f  mov     ebx, eax
0x18002f781  test    eax, eax
0x18002f783  jns     short loc_18002F7A2
0x18002f785  mov     rcx, [rbp+8]; this
0x18002f789  mov     r9d, eax; char *
0x18002f78c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002f793  mov     edx, 65h ; 'e'; void *
0x18002f798  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f79d  jmp     loc_18002F878
0x18002f7a2  mov     [rbp+hKey], 0
0x18002f7aa  xor     edx, edx
0x18002f7ac  lea     rcx, [rbp+hKey]
0x18002f7b0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18002f7b5  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x18002f7be  lea     rax, [rbp+hKey]
0x18002f7c2  mov     [rsp+70h+phkResult], rax; phkResult
0x18002f7c7  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002f7d0  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x18002f7d8  mov     [rsp+70h+dwOptions], 1; unsigned int
0x18002f7e0  xor     r9d, r9d; lpClass
0x18002f7e3  xor     r8d, r8d; Reserved
0x18002f7e6  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x18002f7ea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002f7f1  call    cs:__imp_RegCreateKeyExW
0x18002f7f7  test    eax, eax
0x18002f7f9  jz      short loc_18002F827
0x18002f7fb  mov     rcx, [rbp+8]; this
0x18002f7ff  mov     r9d, eax; char *
0x18002f802  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002f809  mov     edx, 70h ; 'p'; void *
0x18002f80e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002f813  mov     ebx, eax
0x18002f815  mov     rcx, [rbp+hKey]; hKey
0x18002f819  test    rcx, rcx
0x18002f81c  jz      short loc_18002F825
0x18002f81e  call    cs:__imp_RegCloseKey
0x18002f824  nop
0x18002f825  jmp     short loc_18002F878
0x18002f827  mov     r8, [rbp+hKey]; hKeyDest
0x18002f82b  xor     edx, edx; lpSubKey
0x18002f82d  mov     rcx, rdi; hKeySrc
0x18002f830  call    cs:__imp_RegCopyTreeW
0x18002f836  test    eax, eax
0x18002f838  jz      short loc_18002F866
0x18002f83a  mov     rcx, [rbp+8]; this
0x18002f83e  mov     r9d, eax; char *
0x18002f841  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18002f848  mov     edx, 72h ; 'r'; void *
0x18002f84d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002f852  mov     ebx, eax
0x18002f854  mov     rcx, [rbp+hKey]; hKey
0x18002f858  test    rcx, rcx
0x18002f85b  jz      short loc_18002F864
0x18002f85d  call    cs:__imp_RegCloseKey
0x18002f863  nop
0x18002f864  jmp     short loc_18002F878
0x18002f866  mov     rcx, [rbp+hKey]; hKey
0x18002f86a  test    rcx, rcx
0x18002f86d  jz      short loc_18002F876
0x18002f86f  call    cs:__imp_RegCloseKey
0x18002f875  nop
0x18002f876  xor     ebx, ebx
0x18002f878  lea     rcx, [rbp+lpSubKey]
0x18002f87c  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18002f881  mov     eax, ebx
0x18002f883  lea     r11, [rsp+70h+var_s0]
0x18002f888  mov     rbx, [r11+10h]
0x18002f88c  mov     rdi, [r11+18h]
0x18002f890  mov     rsp, r11
0x18002f893  pop     rbp
0x18002f894  retn
```
