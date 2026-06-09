# DAS::ProviderManagement::ProviderManager::OpenKeysStatic(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> *,ulong)

- ea: `0x1400128a0`
- end: `0x140012b52`
- name: `?OpenKeysStatic@ProviderManager@ProviderManagement@DAS@@CAJPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `690`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140012c08`

## callees

- `0x140006ce4`
- `0x140012704`
- `0x1400128a0`
- `0x140013754`
- `0x140013794`
- `0x1400138ac`
- `0x140014828`
- `0x1400149d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012983`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012a07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012a86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012aa6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012983`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012a07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012a86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140012aa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012975`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400129f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012a78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012a98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012975`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400129f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012a78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140012a98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400128e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012a1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400128e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012a1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400128fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012a2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400128fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140012a2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012923`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012a5a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012923`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140012a5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400128f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012a27`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400128f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140012a27`

## string_xrefs

- `0x140012ac8`: `failed to open provider path %ws with because it does not exist`
- `0x140012b0d`: `failed to open provider path %ws with read and set access`

## pseudocode

```c
__int64 __fastcall DAS::ProviderManagement::ProviderManager::OpenKeysStatic(__int64 a1)
{
  int i; // r15d
  HKEY *v3; // rsi
  HKEY v4; // r14
  DWORD LastError; // ebx
  LSTATUS v6; // eax
  __int64 v7; // rcx
  __int64 v8; // r8
  unsigned int v9; // ebx
  int v10; // eax
  unsigned int v11; // edi
  void *v12; // rbx
  HANDLE ProcessHeap; // rax
  WCHAR *v15; // rbx
  int v16; // eax
  unsigned int v17; // edi
  HANDLE v18; // rax
  HKEY v19; // r12
  DWORD v20; // edi
  unsigned int v21; // eax
  void *v22; // rdx
  unsigned int v23; // r8d
  unsigned int v24; // edi
  HANDLE v25; // rax
  HANDLE v26; // rax
  int phkResult; // [rsp+20h] [rbp-38h]
  unsigned int phkResulta; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID lpMem; // [rsp+70h] [rbp+18h] BYREF

  for ( i = 0; ; ++i )
  {
    if ( (unsigned __int64)i >= 2 )
      return 0;
    v3 = (HKEY *)(a1 + 8LL * i);
    v4 = *v3;
    if ( *v3 )
    {
      LastError = GetLastError();
      RegCloseKey(v4);
      SetLastError(LastError);
    }
    *v3 = 0;
    v6 = RegOpenKeyExW(
           (HKEY)*(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * i),
           (LPCWSTR)*(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * i + 1),
           0,
           0x20019u,
           (PHKEY)(a1 + 8LL * i));
    v9 = v6;
    if ( v6 == 5 )
      break;
    if ( v6 == 2 )
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
      if ( v6 > 0 )
        v9 = (unsigned __int16)v6 | 0x80070000;
      if ( (v9 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1CC,
          (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
          (const char *)v9,
          (int)"failed to open provider path %ws with read and set access",
          (const char *)*(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * i + 1));
        return v9;
      }
    }
LABEL_26:
    ;
  }
  lpMem = 0;
  v10 = DafConcatenateWithDelimiter(
          v7,
          *(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * i + 1),
          v8,
          &lpMem);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
      (const char *)(unsigned int)v10,
      phkResult);
    v12 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
    }
    return v11;
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v15 = (WCHAR *)lpMem;
  }
  else
  {
    v15 = (WCHAR *)lpMem;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids, lpMem);
  }
  v16 = DAS::ProviderManagement::ProviderManager::TakeKeyOwnership(v15);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BD,
      (unsigned int)"onecore\\base\\devices\\association\\libs\\providermanagement\\providermanagement.cpp",
      (const char *)(unsigned int)v16,
      phkResult);
    if ( v15 )
    {
      v18 = GetProcessHeap();
      HeapFree(v18, 0, v15);
    }
    return v17;
  }
  v19 = *v3;
  if ( *v3 )
  {
    v20 = GetLastError();
    RegCloseKey(v19);
    SetLastError(v20);
  }
  *v3 = 0;
  v21 = RegOpenKeyExW(
          (HKEY)*(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * i),
          (LPCWSTR)*(&DAS::ProviderManagement::c_providerRegistrationPaths + 3 * i + 1),
          0,
          0x20019u,
          v3);
  if ( !v21 )
  {
    if ( v15 )
    {
      v26 = GetProcessHeap();
      HeapFree(v26, 0, v15);
    }
    goto LABEL_26;
  }
  v24 = wil::details::in1diag3::Return_Win32(retaddr, v22, v23, (const char *)v21, phkResulta);
  if ( v15 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v15);
  }
  return v24;
}

```

## disassembly

```asm
0x1400128a0  mov     [rsp+arg_0], rbx
0x1400128a5  mov     [rsp+arg_18], rsi
0x1400128aa  mov     [rsp+arg_8], edx
0x1400128ae  push    rdi
0x1400128af  push    r12
0x1400128b1  push    r13
0x1400128b3  push    r14
0x1400128b5  push    r15
0x1400128b7  sub     rsp, 30h
0x1400128bb  mov     r13, rcx
0x1400128be  xor     r15d, r15d
0x1400128c1  lea     r12, ?c_providerRegistrationPaths@ProviderManagement@DAS@@3PAU_PROVIDER_REGISTRATION_PATH@12@A; DAS::ProviderManagement::_PROVIDER_REGISTRATION_PATH near * DAS::ProviderManagement::c_providerRegistrationPaths
0x1400128c8  movsxd  rdi, r15d
0x1400128cb  cmp     rdi, 2
0x1400128cf  jnb     loc_140012B31
0x1400128d5  lea     rsi, ds:0[rdi*8]
0x1400128dd  add     rsi, r13
0x1400128e0  mov     r14, [rsi]
0x1400128e3  test    r14, r14
0x1400128e6  jz      short loc_140012901
0x1400128e8  call    cs:__imp_GetLastError
0x1400128ee  mov     ebx, eax
0x1400128f0  mov     rcx, r14; hKey
0x1400128f3  call    cs:__imp_RegCloseKey
0x1400128f9  mov     ecx, ebx; dwErrCode
0x1400128fb  call    cs:__imp_SetLastError
0x140012901  mov     qword ptr [rsi], 0
0x140012908  lea     r14, [rdi+rdi*2]
0x14001290c  mov     [rsp+58h+phkResult], rsi; int
0x140012911  mov     r9d, 20019h; samDesired
0x140012917  xor     r8d, r8d; ulOptions
0x14001291a  mov     rdx, [r12+r14*8+8]; lpSubKey
0x14001291f  mov     rcx, [r12+r14*8]; hKey
0x140012923  call    cs:__imp_RegOpenKeyExW
0x140012929  mov     ebx, eax
0x14001292b  cmp     eax, 5
0x14001292e  jnz     loc_140012AB4
0x140012934  mov     [rsp+58h+lpMem], 0
0x14001293d  lea     r9, [rsp+58h+lpMem]
0x140012942  mov     rdx, [r12+r14*8+8]
0x140012947  call    DafConcatenateWithDelimiter
0x14001294c  mov     edi, eax
0x14001294e  test    eax, eax
0x140012950  jns     short loc_140012990
0x140012952  mov     rcx, [rsp+58h]; this
0x140012957  mov     r9d, eax; char *
0x14001295a  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x140012961  mov     edx, 1BBh; void *
0x140012966  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001296b  mov     rbx, [rsp+58h+lpMem]
0x140012970  test    rbx, rbx
0x140012973  jz      short loc_140012989
0x140012975  call    cs:__imp_GetProcessHeap
0x14001297b  mov     rcx, rax; hHeap
0x14001297e  mov     r8, rbx; lpMem
0x140012981  xor     edx, edx; dwFlags
0x140012983  call    cs:__imp_HeapFree
0x140012989  mov     eax, edi
0x14001298b  jmp     loc_140012B39
0x140012990  lea     rax, WPP_GLOBAL_Control
0x140012997  mov     rcx, cs:WPP_GLOBAL_Control
0x14001299e  cmp     rcx, rax
0x1400129a1  jz      short loc_1400129C8
0x1400129a3  cmp     byte ptr [rcx+19h], 4
0x1400129a7  jb      short loc_1400129C8
0x1400129a9  mov     edx, 1Dh
0x1400129ae  mov     rbx, [rsp+58h+lpMem]
0x1400129b3  mov     r9, rbx
0x1400129b6  lea     r8, WPP_c259ffd365a33e780ba81409624fcc4e_Traceguids
0x1400129bd  mov     rcx, [rcx+10h]
0x1400129c1  call    WPP_SF_S
0x1400129c6  jmp     short loc_1400129CD
0x1400129c8  mov     rbx, [rsp+58h+lpMem]
0x1400129cd  mov     rcx, rbx; char *
0x1400129d0  call    ?TakeKeyOwnership@ProviderManager@ProviderManagement@DAS@@CAJPEAG@Z; DAS::ProviderManagement::ProviderManager::TakeKeyOwnership(ushort *)
0x1400129d5  mov     edi, eax
0x1400129d7  test    eax, eax
0x1400129d9  jns     short loc_140012A14
0x1400129db  mov     rcx, [rsp+58h]; this
0x1400129e0  mov     r9d, eax; char *
0x1400129e3  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x1400129ea  mov     edx, 1BDh; void *
0x1400129ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400129f4  test    rbx, rbx
0x1400129f7  jz      short loc_140012A0D
0x1400129f9  call    cs:__imp_GetProcessHeap
0x1400129ff  mov     rcx, rax; hHeap
0x140012a02  mov     r8, rbx; lpMem
0x140012a05  xor     edx, edx; dwFlags
0x140012a07  call    cs:__imp_HeapFree
0x140012a0d  mov     eax, edi
0x140012a0f  jmp     loc_140012B39
0x140012a14  mov     r12, [rsi]
0x140012a17  test    r12, r12
0x140012a1a  jz      short loc_140012A35
0x140012a1c  call    cs:__imp_GetLastError
0x140012a22  mov     edi, eax
0x140012a24  mov     rcx, r12; hKey
0x140012a27  call    cs:__imp_RegCloseKey
0x140012a2d  mov     ecx, edi; dwErrCode
0x140012a2f  call    cs:__imp_SetLastError
0x140012a35  mov     qword ptr [rsi], 0
0x140012a3c  mov     [rsp+58h+phkResult], rsi; unsigned int
0x140012a41  mov     r9d, 20019h; samDesired
0x140012a47  xor     r8d, r8d; ulOptions
0x140012a4a  lea     r12, ?c_providerRegistrationPaths@ProviderManagement@DAS@@3PAU_PROVIDER_REGISTRATION_PATH@12@A; DAS::ProviderManagement::_PROVIDER_REGISTRATION_PATH near * DAS::ProviderManagement::c_providerRegistrationPaths
0x140012a51  mov     rdx, [r12+r14*8+8]; lpSubKey
0x140012a56  mov     rcx, [r12+r14*8]; hKey
0x140012a5a  call    cs:__imp_RegOpenKeyExW
0x140012a60  test    eax, eax
0x140012a62  jz      short loc_140012A93
0x140012a64  mov     rcx, [rsp+58h]; this
0x140012a69  mov     r9d, eax; char *
0x140012a6c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140012a71  mov     edi, eax
0x140012a73  test    rbx, rbx
0x140012a76  jz      short loc_140012A8C
0x140012a78  call    cs:__imp_GetProcessHeap
0x140012a7e  mov     rcx, rax; hHeap
0x140012a81  mov     r8, rbx; lpMem
0x140012a84  xor     edx, edx; dwFlags
0x140012a86  call    cs:__imp_HeapFree
0x140012a8c  mov     eax, edi
0x140012a8e  jmp     loc_140012B39
0x140012a93  test    rbx, rbx
0x140012a96  jz      short loc_140012AAC
0x140012a98  call    cs:__imp_GetProcessHeap
0x140012a9e  mov     rcx, rax; hHeap
0x140012aa1  mov     r8, rbx; lpMem
0x140012aa4  xor     edx, edx; dwFlags
0x140012aa6  call    cs:__imp_HeapFree
0x140012aac  inc     r15d
0x140012aaf  jmp     loc_1400128C8
0x140012ab4  cmp     eax, 2
0x140012ab7  jnz     short loc_140012AED
0x140012ab9  mov     rcx, [rsp+58h]; this
0x140012abe  mov     rax, [r12+r14*8+8]
0x140012ac3  mov     [rsp+58h+var_30], rax; char *
0x140012ac8  lea     rax, aFailedToOpenPr_0; "failed to open provider path %ws with b"...
0x140012acf  mov     [rsp+58h+phkResult], rax; unsigned int
0x140012ad4  mov     r9d, 2; char *
0x140012ada  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x140012ae1  mov     edx, 1C3h; void *
0x140012ae6  call    ?Log_Win32Msg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x140012aeb  jmp     short loc_140012AAC
0x140012aed  test    eax, eax
0x140012aef  jle     short loc_140012AFA
0x140012af1  movzx   ebx, ax
0x140012af4  or      ebx, 80070000h
0x140012afa  test    ebx, ebx
0x140012afc  jns     short loc_140012AAC
0x140012afe  mov     rcx, [rsp+58h]; this
0x140012b03  mov     rdx, [r12+r14*8+8]
0x140012b08  mov     [rsp+58h+var_30], rdx; char *
0x140012b0d  lea     rax, aFailedToOpenPr; "failed to open provider path %ws with r"...
0x140012b14  mov     [rsp+58h+phkResult], rax; int
0x140012b19  mov     r9d, ebx; char *
0x140012b1c  lea     r8, aOnecoreBaseDev_0; "onecore\\base\\devices\\association\\li"...
0x140012b23  mov     edx, 1CCh; void *
0x140012b28  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x140012b2d  mov     eax, ebx
0x140012b2f  jmp     short loc_140012B39
0x140012b31  xor     eax, eax
0x140012b33  jmp     short loc_140012B39
0x140012b35  mov     eax, [rsp+58h+arg_8]
0x140012b39  mov     rbx, [rsp+58h+arg_0]
0x140012b3e  mov     rsi, [rsp+58h+arg_18]
0x140012b43  add     rsp, 30h
0x140012b47  pop     r15
0x140012b49  pop     r14
0x140012b4b  pop     r13
0x140012b4d  pop     r12
0x140012b4f  pop     rdi
0x140012b50  retn
```
