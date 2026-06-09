# DAS::ProviderManagement::ProviderManager::OpenKeysStatic(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> *,ulong)

- ea: `0x180060c78`
- end: `0x180060eb8`
- name: `?OpenKeysStatic@ProviderManager@ProviderManagement@DAS@@CAJPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `576`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config`

## callers

- `0x18002f930`

## callees

- `0x1800074c0`
- `0x18001eae0`
- `0x180028810`
- `0x18002a948`
- `0x18003a3ec`
- `0x180049834`
- `0x1800609f8`
- `0x180060c78`
- `0x1800618b4`
- `0x180061b2c`
- `0x180061c68`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060cdd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060ddf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060cdd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060ddf`

## string_xrefs

- `0x180060e36`: `failed to open provider path %ws with because it does not exist`
- `0x180060e77`: `failed to open provider path %ws with read and set access`

## pseudocode

```c
__int64 __fastcall DAS::ProviderManagement::ProviderManager::OpenKeysStatic(__int64 a1)
{
  int i; // esi
  HKEY *v3; // r14
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  unsigned int v7; // ebx
  WCHAR *v9; // rbx
  int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  int phkResult; // [rsp+20h] [rbp-38h]
  unsigned int phkResulta; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPWSTR pObjectName; // [rsp+70h] [rbp+18h] BYREF

  for ( i = 0; (unsigned __int64)i < 2; ++i )
  {
    v3 = (HKEY *)(a1 + 8LL * i);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      v3,
      0);
    v4 = RegOpenKeyExW(
           (HKEY)*(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * i),
           (LPCWSTR)*(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * i + 1),
           0,
           0x20019u,
           v3);
    v5 = v4;
    if ( v4 == 5 )
    {
      pObjectName = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pObjectName,
        0);
      v6 = DafConcatenateWithDelimiter_3(
             L"MACHINE",
             (unsigned __int16 *)*(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * i + 1),
             L"\\");
      v7 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1BB,
          (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
          (const char *)(unsigned int)v6,
          phkResult);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pObjectName);
        return v7;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        v9 = pObjectName;
      }
      else
      {
        v9 = pObjectName;
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids, pObjectName);
      }
      v10 = DAS::ProviderManagement::ProviderManager::TakeKeyOwnership(v9);
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1BD,
          (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
          (const char *)(unsigned int)v10,
          phkResult);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pObjectName);
        return v11;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        v3,
        0);
      v12 = RegOpenKeyExW(
              (HKEY)*(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * i),
              (LPCWSTR)*(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * i + 1),
              0,
              0x20019u,
              v3);
      if ( v12 )
      {
        v13 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x1BF,
                (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
                (const char *)v12,
                phkResulta);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pObjectName);
        return v13;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pObjectName);
    }
    else if ( v4 == 2 )
    {
      wil::details::in1diag3::Log_Win32Msg(
        retaddr,
        (void *)0x1C3,
        (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
        (const char *)2,
        (unsigned int)"failed to open provider path %ws with because it does not exist",
        (const char *)*(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * i + 1));
    }
    else
    {
      if ( v4 > 0 )
        v5 = (unsigned __int16)v4 | 0x80070000;
      if ( (v5 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1CC,
          (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
          (const char *)v5,
          (int)"failed to open provider path %ws with read and set access",
          (const char *)*(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * i + 1));
        return v5;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180060c78  mov     [rsp+arg_0], rbx
0x180060c7d  mov     [rsp+arg_18], rsi
0x180060c82  mov     [rsp+arg_8], edx
0x180060c86  push    rdi
0x180060c87  push    r12
0x180060c89  push    r13
0x180060c8b  push    r14
0x180060c8d  push    r15
0x180060c8f  sub     rsp, 30h
0x180060c93  mov     r15, rcx
0x180060c96  xor     esi, esi
0x180060c98  lea     r13, ?c_providerRegistrationPaths@ProviderManagement@DAS@@3PAU_PROVIDER_REGISTRATION_PATH@12@A; DAS::ProviderManagement::_PROVIDER_REGISTRATION_PATH near * DAS::ProviderManagement::c_providerRegistrationPaths
0x180060c9f  lea     r12, aOnecoreBaseDev_4; "onecore\\base\\devices\\association\\li"...
0x180060ca6  movsxd  rbx, esi
0x180060ca9  cmp     rbx, 2
0x180060cad  jnb     loc_180060E97
0x180060cb3  lea     r14, [r15+rbx*8]
0x180060cb7  xor     edx, edx
0x180060cb9  mov     rcx, r14
0x180060cbc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180060cc1  lea     rdi, [rbx+rbx*2]
0x180060cc5  mov     [rsp+58h+phkResult], r14; int
0x180060cca  mov     r9d, 20019h; samDesired
0x180060cd0  xor     r8d, r8d; ulOptions
0x180060cd3  mov     rdx, [r13+rdi*8+8]; lpSubKey
0x180060cd8  mov     rcx, [r13+rdi*8+0]; hKey
0x180060cdd  call    cs:__imp_RegOpenKeyExW
0x180060ce3  mov     ebx, eax
0x180060ce5  cmp     eax, 5
0x180060ce8  jnz     loc_180060E22
0x180060cee  mov     [rsp+58h+pObjectName], 0
0x180060cf7  xor     edx, edx
0x180060cf9  lea     rcx, [rsp+58h+pObjectName]
0x180060cfe  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180060d03  lea     r9, [rsp+58h+pObjectName]
0x180060d08  lea     r8, asc_18008CA3C; "\\"
0x180060d0f  mov     rdx, [r13+rdi*8+8]; unsigned __int16 *
0x180060d14  lea     rcx, aMachine; "MACHINE"
0x180060d1b  call    DafConcatenateWithDelimiter_3
0x180060d20  mov     ebx, eax
0x180060d22  test    eax, eax
0x180060d24  jns     short loc_180060D4C
0x180060d26  mov     rcx, [rsp+58h]; this
0x180060d2b  mov     r9d, eax; char *
0x180060d2e  mov     r8, r12; unsigned int
0x180060d31  mov     edx, 1BBh; void *
0x180060d36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060d3b  lea     rcx, [rsp+58h+pObjectName]
0x180060d40  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180060d45  mov     eax, ebx
0x180060d47  jmp     loc_180060E9F
0x180060d4c  lea     rax, WPP_GLOBAL_Control
0x180060d53  mov     rcx, cs:WPP_GLOBAL_Control
0x180060d5a  cmp     rcx, rax
0x180060d5d  jz      short loc_180060D84
0x180060d5f  cmp     byte ptr [rcx+19h], 4
0x180060d63  jb      short loc_180060D84
0x180060d65  mov     edx, 1Dh
0x180060d6a  mov     rbx, [rsp+58h+pObjectName]
0x180060d6f  mov     r9, rbx
0x180060d72  lea     r8, WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids
0x180060d79  mov     rcx, [rcx+10h]
0x180060d7d  call    WPP_SF_S
0x180060d82  jmp     short loc_180060D89
0x180060d84  mov     rbx, [rsp+58h+pObjectName]
0x180060d89  mov     rcx, rbx; pObjectName
0x180060d8c  call    ?TakeKeyOwnership@ProviderManager@ProviderManagement@DAS@@CAJPEAG@Z; DAS::ProviderManagement::ProviderManager::TakeKeyOwnership(ushort *)
0x180060d91  mov     ebx, eax
0x180060d93  test    eax, eax
0x180060d95  jns     short loc_180060DBD
0x180060d97  mov     rcx, [rsp+58h]; this
0x180060d9c  mov     r9d, eax; char *
0x180060d9f  mov     r8, r12; unsigned int
0x180060da2  mov     edx, 1BDh; void *
0x180060da7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060dac  lea     rcx, [rsp+58h+pObjectName]
0x180060db1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180060db6  mov     eax, ebx
0x180060db8  jmp     loc_180060E9F
0x180060dbd  xor     edx, edx
0x180060dbf  mov     rcx, r14
0x180060dc2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180060dc7  mov     [rsp+58h+phkResult], r14; unsigned int
0x180060dcc  mov     r9d, 20019h; samDesired
0x180060dd2  xor     r8d, r8d; ulOptions
0x180060dd5  mov     rdx, [r13+rdi*8+8]; lpSubKey
0x180060dda  mov     rcx, [r13+rdi*8+0]; hKey
0x180060ddf  call    cs:__imp_RegOpenKeyExW
0x180060de5  test    eax, eax
0x180060de7  jz      short loc_180060E11
0x180060de9  mov     rcx, [rsp+58h]; this
0x180060dee  mov     r9d, eax; char *
0x180060df1  mov     r8, r12; unsigned int
0x180060df4  mov     edx, 1BFh; void *
0x180060df9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180060dfe  mov     ebx, eax
0x180060e00  lea     rcx, [rsp+58h+pObjectName]
0x180060e05  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180060e0a  mov     eax, ebx
0x180060e0c  jmp     loc_180060E9F
0x180060e11  lea     rcx, [rsp+58h+pObjectName]
0x180060e16  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180060e1b  inc     esi
0x180060e1d  jmp     loc_180060CA6
0x180060e22  cmp     eax, 2
0x180060e25  jnz     short loc_180060E57
0x180060e27  mov     rcx, [rsp+58h]; this
0x180060e2c  mov     rax, [r13+rdi*8+8]
0x180060e31  mov     [rsp+58h+var_30], rax; char *
0x180060e36  lea     rax, aFailedToOpenPr_0; "failed to open provider path %ws with b"...
0x180060e3d  mov     [rsp+58h+phkResult], rax; unsigned int
0x180060e42  mov     r9d, 2; char *
0x180060e48  mov     r8, r12; unsigned int
0x180060e4b  mov     edx, 1C3h; void *
0x180060e50  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x180060e55  jmp     short loc_180060E1B
0x180060e57  test    eax, eax
0x180060e59  jle     short loc_180060E64
0x180060e5b  movzx   ebx, ax
0x180060e5e  or      ebx, 80070000h
0x180060e64  test    ebx, ebx
0x180060e66  jns     short loc_180060E1B
0x180060e68  mov     rcx, [rsp+58h]; this
0x180060e6d  mov     rdx, [r13+rdi*8+8]
0x180060e72  mov     [rsp+58h+var_30], rdx; char *
0x180060e77  lea     rax, aFailedToOpenPr; "failed to open provider path %ws with r"...
0x180060e7e  mov     [rsp+58h+phkResult], rax; int
0x180060e83  mov     r9d, ebx; char *
0x180060e86  mov     r8, r12; unsigned int
0x180060e89  mov     edx, 1CCh; void *
0x180060e8e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180060e93  mov     eax, ebx
0x180060e95  jmp     short loc_180060E9F
0x180060e97  xor     eax, eax
0x180060e99  jmp     short loc_180060E9F
0x180060e9b  mov     eax, [rsp+58h+arg_8]
0x180060e9f  mov     rbx, [rsp+58h+arg_0]
0x180060ea4  mov     rsi, [rsp+58h+arg_18]
0x180060ea9  add     rsp, 30h
0x180060ead  pop     r15
0x180060eaf  pop     r14
0x180060eb1  pop     r13
0x180060eb3  pop     r12
0x180060eb5  pop     rdi
0x180060eb6  retn
```
