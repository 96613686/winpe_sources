# CopyRedirectedProfileListKeyForSid(HKEY__ *,ushort const *)

- ea: `0x180051554`
- end: `0x1800516ac`
- name: `?CopyRedirectedProfileListKeyForSid@@YAJPEAUHKEY__@@PEBG@Z`
- size: `344`
- prototype: `__int64 __fastcall(HKEY hKeySrc, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180041f2c`
- `0x180045750`

## callees

- `0x18000d030`
- `0x18000e1a0`
- `0x1800130d0`
- `0x180013770`
- `0x180030ad0`
- `0x180031060`
- `0x180051554`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18005164c`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18005164c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005160d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005160d`

## string_xrefs

- `0x1800515a8`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x180051624`: `onecore\ds\security\gina\profile\proflib\sid.cpp`
- `0x180051663`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  HKEY hKeyDest; // [rsp+90h] [rbp+20h] BYREF

  memset(lpSubKey, 0, 24);
  v3 = Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::InitializeFormat(
         lpSubKey,
         L"%s\\%s",
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
         a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    hKeyDest = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKeyDest,
      0);
    v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0, 1u, 0xF003Fu, 0, &hKeyDest, 0);
    if ( v5 )
    {
      v4 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x70,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
             (const char *)v5,
             dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeyDest);
    }
    else
    {
      v6 = RegCopyTreeW(hKeySrc, 0, hKeyDest);
      if ( v6 )
      {
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x72,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
               (const char *)v6,
               dwOptionsa);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeyDest);
      }
      else
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeyDest);
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
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
  return v4;
}

```

## disassembly

```asm
0x180051554  mov     [rsp-8+arg_0], rbx
0x180051559  mov     [rsp-8+arg_8], rdi
0x18005155e  push    rbp
0x18005155f  mov     rbp, rsp
0x180051562  sub     rsp, 70h
0x180051566  mov     rdi, rcx
0x180051569  mov     [rbp+lpSubKey], 0
0x180051571  mov     [rbp+var_18], 0
0x180051579  mov     [rbp+var_10], 0
0x180051581  mov     r9, rdx
0x180051584  lea     r8, aSoftwareMicros_34; "Software\\Microsoft\\Windows NT\\Curren"...
0x18005158b  lea     rdx, aSS_0; "%s\\%s"
0x180051592  lea     rcx, [rbp+lpSubKey]
0x180051596  call    ?InitializeFormat@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18005159b  mov     ebx, eax
0x18005159d  test    eax, eax
0x18005159f  jns     short loc_1800515BE
0x1800515a1  mov     rcx, [rbp+8]; this
0x1800515a5  mov     r9d, eax; char *
0x1800515a8  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800515af  mov     edx, 65h ; 'e'; void *
0x1800515b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800515b9  jmp     loc_18005168E
0x1800515be  mov     [rbp+hKeyDest], 0
0x1800515c6  xor     edx, edx
0x1800515c8  lea     rcx, [rbp+hKeyDest]
0x1800515cc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800515d1  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x1800515da  lea     rax, [rbp+hKeyDest]
0x1800515de  mov     [rsp+70h+phkResult], rax; phkResult
0x1800515e3  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800515ec  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x1800515f4  mov     [rsp+70h+dwOptions], 1; unsigned int
0x1800515fc  xor     r9d, r9d; lpClass
0x1800515ff  xor     r8d, r8d; Reserved
0x180051602  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x180051606  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005160d  call    cs:__imp_RegCreateKeyExW
0x180051614  nop     dword ptr [rax+rax+00h]
0x180051619  test    eax, eax
0x18005161b  jz      short loc_180051643
0x18005161d  mov     rcx, [rbp+8]; this
0x180051621  mov     r9d, eax; char *
0x180051624  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18005162b  mov     edx, 70h ; 'p'; void *
0x180051630  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180051635  mov     ebx, eax
0x180051637  lea     rcx, [rbp+hKeyDest]
0x18005163b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180051640  nop
0x180051641  jmp     short loc_18005168E
0x180051643  mov     r8, [rbp+hKeyDest]; hKeyDest
0x180051647  xor     edx, edx; lpSubKey
0x180051649  mov     rcx, rdi; hKeySrc
0x18005164c  call    cs:__imp_RegCopyTreeW
0x180051653  nop     dword ptr [rax+rax+00h]
0x180051658  test    eax, eax
0x18005165a  jz      short loc_180051682
0x18005165c  mov     rcx, [rbp+8]; this
0x180051660  mov     r9d, eax; char *
0x180051663  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18005166a  mov     edx, 72h ; 'r'; void *
0x18005166f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180051674  mov     ebx, eax
0x180051676  lea     rcx, [rbp+hKeyDest]
0x18005167a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005167f  nop
0x180051680  jmp     short loc_18005168E
0x180051682  lea     rcx, [rbp+hKeyDest]
0x180051686  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005168b  nop
0x18005168c  xor     ebx, ebx
0x18005168e  lea     rcx, [rbp+lpSubKey]
0x180051692  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x180051697  mov     eax, ebx
0x180051699  lea     r11, [rsp+70h+var_s0]
0x18005169e  mov     rbx, [r11+10h]
0x1800516a2  mov     rdi, [r11+18h]
0x1800516a6  mov     rsp, r11
0x1800516a9  pop     rbp
0x1800516aa  retn
```
