# CUserProfileManager::InitializeRedirectionLinks(void)

- ea: `0x18004aeec`
- end: `0x18004b175`
- name: `?InitializeRedirectionLinks@CUserProfileManager@@AEAAJXZ`
- size: `649`
- prototype: `__int64 __fastcall(CUserProfileManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039094`

## callees

- `0x18000e1a0`
- `0x1800130d0`
- `0x180013770`
- `0x180022130`
- `0x180031060`
- `0x18003bc70`
- `0x18004aeec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004af7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004afe6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004af7d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004afe6`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18004b0c9`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x18004b0c9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b0ab`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004b0ab`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004b04a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004b04a`

## string_xrefs

- `0x18004af9d`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x18004affd`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`
- `0x18004b0fd`: `onecore\ds\security\gina\profile\profsvc\profmgr.cpp`

## pseudocode

```c
__int64 __fastcall CUserProfileManager::InitializeRedirectionLinks(CUserProfileManager *this)
{
  unsigned int v1; // eax
  unsigned int v2; // ebx
  unsigned int v3; // eax
  DWORD i; // ebx
  unsigned int v5; // eax
  __int64 v6; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY v11; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKeyDest; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwDisposition; // [rsp+6Ch] [rbp-94h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  memset(lpSubKey, 0, 24);
  if ( (int)Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::Initialize(
              lpSubKey,
              -2147483646,
              L"System\\CurrentControlSet\\Control\\ProfileList",
              L"RedirectionKey") < 0 )
    goto LABEL_19;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 0x20019u, &hKey);
  if ( v1 == 2 )
  {
LABEL_18:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_19:
    v2 = 0;
    goto LABEL_20;
  }
  if ( !v1 )
  {
    v11 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v11,
      0);
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
           0,
           0xF003Fu,
           &v11);
    if ( v3 )
    {
      v2 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0xEA,
             (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
             (const char *)v3,
             phkResulta);
LABEL_15:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v11);
      goto LABEL_16;
    }
    for ( i = 0; ; ++i )
    {
      Name[0] = 0;
      cchName = 260;
      if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
        break;
      dwDisposition = 0;
      hKeyDest = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKeyDest,
        0);
      v5 = RegCreateKeyExW(v11, Name, 0, 0, 1u, 0xF003Fu, 0, &hKeyDest, &dwDisposition);
      if ( v5 )
      {
        v6 = 250;
        goto LABEL_14;
      }
      v5 = RegCopyTreeW(hKey, Name, hKeyDest);
      if ( v5 )
      {
        v6 = 253;
LABEL_14:
        v2 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v6,
               (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
               (const char *)v5,
               phkResultb);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeyDest);
        goto LABEL_15;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeyDest);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v11);
    goto LABEL_18;
  }
  v2 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0xE7,
         (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\profmgr.cpp",
         (const char *)v1,
         phkResult);
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_20:
  Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<unsigned short>>::_Free(lpSubKey);
  return v2;
}

```

## disassembly

```asm
0x18004aeec  mov     [rsp-8+arg_0], rbx
0x18004aef1  mov     [rsp-8+arg_8], rdi
0x18004aef6  push    rbp
0x18004aef7  lea     rbp, [rsp-1B0h]
0x18004aeff  sub     rsp, 2B0h
0x18004af06  mov     rax, cs:__security_cookie
0x18004af0d  xor     rax, rsp
0x18004af10  mov     [rbp+1B0h+var_10], rax
0x18004af17  xor     edi, edi
0x18004af19  lea     r9, aRedirectionkey; "RedirectionKey"
0x18004af20  mov     rbx, 0FFFFFFFF80000002h
0x18004af27  mov     [rsp+2B0h+lpSubKey], rdi
0x18004af2c  mov     rdx, rbx
0x18004af2f  mov     [rsp+2B0h+var_238], rdi
0x18004af34  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Pro"...
0x18004af3b  mov     [rbp+1B0h+var_230], rdi
0x18004af3f  lea     rcx, [rsp+2B0h+lpSubKey]
0x18004af44  call    ?Initialize@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEAUHKEY__@@PEBG1@Z; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::Initialize(HKEY__ *,ushort const *,ushort const *)
0x18004af49  test    eax, eax
0x18004af4b  js      loc_18004B142
0x18004af51  xor     edx, edx
0x18004af53  mov     [rsp+2B0h+hKey], rdi
0x18004af58  lea     rcx, [rsp+2B0h+hKey]
0x18004af5d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004af62  mov     rdx, [rsp+2B0h+lpSubKey]; lpSubKey
0x18004af67  lea     rax, [rsp+2B0h+hKey]
0x18004af6c  mov     r9d, 20019h; samDesired
0x18004af72  mov     [rsp+2B0h+phkResult], rax; unsigned int
0x18004af77  xor     r8d, r8d; ulOptions
0x18004af7a  mov     rcx, rbx; hKey
0x18004af7d  call    cs:__imp_RegOpenKeyExW
0x18004af84  nop     dword ptr [rax+rax+00h]
0x18004af89  cmp     eax, 2
0x18004af8c  jz      loc_18004B138
0x18004af92  test    eax, eax
0x18004af94  jz      short loc_18004AFB8
0x18004af96  mov     rcx, [rbp+1B8h]; this
0x18004af9d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004afa4  mov     r9d, eax; char *
0x18004afa7  mov     edx, 0E7h; void *
0x18004afac  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004afb1  mov     ebx, eax
0x18004afb3  jmp     loc_18004B122
0x18004afb8  xor     edx, edx
0x18004afba  mov     [rsp+2B0h+var_260], rdi
0x18004afbf  lea     rcx, [rsp+2B0h+var_260]
0x18004afc4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004afc9  lea     rax, [rsp+2B0h+var_260]
0x18004afce  mov     r9d, 0F003Fh; samDesired
0x18004afd4  xor     r8d, r8d; ulOptions
0x18004afd7  mov     [rsp+2B0h+phkResult], rax; unsigned int
0x18004afdc  lea     rdx, aSoftwareMicros_34; "Software\\Microsoft\\Windows NT\\Curren"...
0x18004afe3  mov     rcx, rbx; hKey
0x18004afe6  call    cs:__imp_RegOpenKeyExW
0x18004afed  nop     dword ptr [rax+rax+00h]
0x18004aff2  test    eax, eax
0x18004aff4  jz      short loc_18004B018
0x18004aff6  mov     rcx, [rbp+1B8h]; this
0x18004affd  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004b004  mov     r9d, eax; char *
0x18004b007  mov     edx, 0EAh; void *
0x18004b00c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004b011  mov     ebx, eax
0x18004b013  jmp     loc_18004B118
0x18004b018  mov     ebx, edi
0x18004b01a  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18004b01f  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x18004b024  mov     [rsp+2B0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18004b029  lea     r8, [rbp+1B0h+Name]; lpName
0x18004b02d  mov     [rsp+2B0h+lpcchClass], rdi; lpcchClass
0x18004b032  mov     edx, ebx; dwIndex
0x18004b034  mov     [rsp+2B0h+lpClass], rdi; lpClass
0x18004b039  mov     [rsp+2B0h+phkResult], rdi; lpReserved
0x18004b03e  mov     [rbp+1B0h+Name], di
0x18004b042  mov     [rsp+2B0h+cchName], 104h
0x18004b04a  call    cs:__imp_RegEnumKeyExW
0x18004b051  nop     dword ptr [rax+rax+00h]
0x18004b056  test    eax, eax
0x18004b058  jnz     loc_18004B12E
0x18004b05e  xor     edx, edx
0x18004b060  mov     [rsp+2B0h+dwDisposition], edi
0x18004b064  lea     rcx, [rsp+2B0h+hKeyDest]
0x18004b069  mov     [rsp+2B0h+hKeyDest], rdi
0x18004b06e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004b073  mov     rcx, [rsp+2B0h+var_260]; hKey
0x18004b078  lea     rax, [rsp+2B0h+dwDisposition]
0x18004b07d  mov     [rsp+2B0h+lpdwDisposition], rax; lpdwDisposition
0x18004b082  lea     rdx, [rbp+1B0h+Name]; lpSubKey
0x18004b086  lea     rax, [rsp+2B0h+hKeyDest]
0x18004b08b  xor     r9d, r9d; lpClass
0x18004b08e  mov     [rsp+2B0h+lpftLastWriteTime], rax; phkResult
0x18004b093  xor     r8d, r8d; Reserved
0x18004b096  mov     [rsp+2B0h+lpcchClass], rdi; lpSecurityAttributes
0x18004b09b  mov     dword ptr [rsp+2B0h+lpClass], 0F003Fh; samDesired
0x18004b0a3  mov     dword ptr [rsp+2B0h+phkResult], 1; unsigned int
0x18004b0ab  call    cs:__imp_RegCreateKeyExW
0x18004b0b2  nop     dword ptr [rax+rax+00h]
0x18004b0b7  test    eax, eax
0x18004b0b9  jnz     short loc_18004B0F1
0x18004b0bb  mov     r8, [rsp+2B0h+hKeyDest]; hKeyDest
0x18004b0c0  lea     rdx, [rbp+1B0h+Name]; lpSubKey
0x18004b0c4  mov     rcx, [rsp+2B0h+hKey]; hKeySrc
0x18004b0c9  call    cs:__imp_RegCopyTreeW
0x18004b0d0  nop     dword ptr [rax+rax+00h]
0x18004b0d5  test    eax, eax
0x18004b0d7  jnz     short loc_18004B0EA
0x18004b0d9  lea     rcx, [rsp+2B0h+hKeyDest]
0x18004b0de  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004b0e3  inc     ebx
0x18004b0e5  jmp     loc_18004B01A
0x18004b0ea  mov     edx, 0FDh
0x18004b0ef  jmp     short loc_18004B0F6
0x18004b0f1  mov     edx, 0FAh; void *
0x18004b0f6  mov     rcx, [rbp+1B8h]; this
0x18004b0fd  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x18004b104  mov     r9d, eax; char *
0x18004b107  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18004b10c  lea     rcx, [rsp+2B0h+hKeyDest]
0x18004b111  mov     ebx, eax
0x18004b113  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004b118  lea     rcx, [rsp+2B0h+var_260]
0x18004b11d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004b122  lea     rcx, [rsp+2B0h+hKey]
0x18004b127  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004b12c  jmp     short loc_18004B144
0x18004b12e  lea     rcx, [rsp+2B0h+var_260]
0x18004b133  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004b138  lea     rcx, [rsp+2B0h+hKey]
0x18004b13d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004b142  mov     ebx, edi
0x18004b144  lea     rcx, [rsp+2B0h+lpSubKey]
0x18004b149  call    ?_Free@?$NativeString@V?$ProcessHeapMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::ProcessHeapMemPolicy<ushort>>::_Free(void)
0x18004b14e  mov     eax, ebx
0x18004b150  mov     rcx, [rbp+1B0h+var_10]
0x18004b157  xor     rcx, rsp; StackCookie
0x18004b15a  call    __security_check_cookie
0x18004b15f  lea     r11, [rsp+2B0h+var_s0]
0x18004b167  mov     rbx, [r11+10h]
0x18004b16b  mov     rdi, [r11+18h]
0x18004b16f  mov     rsp, r11
0x18004b172  pop     rbp
0x18004b173  retn
```
