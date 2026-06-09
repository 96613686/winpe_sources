# NetworkPropertyMaps::InternalGetTimeCreatedAndTimeConnected(_GUID const &,ulong *,ulong *,ulong *,ulong *)

- ea: `0x18000c198`
- end: `0x18000c545`
- name: `?InternalGetTimeCreatedAndTimeConnected@NetworkPropertyMaps@@AEBAXAEBU_GUID@@PEAK111@Z`
- size: `941`
- prototype: `void(NetworkPropertyMaps *__hidden this, const struct _GUID *, unsigned int *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c590`
- `0x180034940`

## callees

- `0x180009990`
- `0x18000c198`
- `0x18000c54c`
- `0x180013748`
- `0x180014d80`
- `0x180015608`
- `0x18001ffc8`
- `0x180020000`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800baf04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c21b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c21b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c3d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c3d5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c212`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000c212`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c2e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c35d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c2e6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c35d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c3c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c3c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c27e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c27e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000c312`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000c389`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000c4b5`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000c312`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000c389`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000c4b5`

## string_xrefs

- `0x18000c2da`: `DateCreated`
- `0x18000c41c`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x18000c434`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x18000c449`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x18000c4f0`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x18000c50f`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x18000c521`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x18000c533`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall NetworkPropertyMaps::InternalGetTimeCreatedAndTimeConnected(
        const SYSTEMTIME **this,
        const struct _GUID *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int *a6)
{
  struct _RTL_CRITICAL_SECTION *v10; // rbx
  LPCWSTR *v11; // r9
  LSTATUS v12; // eax
  unsigned int v13; // ecx
  int v14; // eax
  const char *v15; // r9
  int v16; // eax
  const char *v17; // r9
  struct _RTL_CRITICAL_SECTION *v18; // rcx
  const SYSTEMTIME *v19; // rbx
  __int64 v20; // rcx
  const char *v21; // r9
  unsigned int v22; // eax
  unsigned int v23; // ecx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME v30; // [rsp+48h] [rbp-B8h] BYREF
  _FILETIME FileTime; // [rsp+50h] [rbp-B0h] BYREF
  BYTE v32[16]; // [rsp+58h] [rbp-A8h] BYREF
  const SYSTEMTIME *v33; // [rsp+68h] [rbp-98h]
  BYTE Data[16]; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[120]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v10 = (struct _RTL_CRITICAL_SECTION *)(this + 98);
  if ( IsUnidentifiedOrIdentifyingNetwork(a2) )
  {
    hKey = 0;
    v30 = 0;
    wil::EnterCriticalSection(&v30, v10);
    std::_Tree<std::_Tmap_traits<_GUID,NetworkPropertyMaps::CONNECTED_PROFILE_INFO,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkPropertyMaps::CONNECTED_PROFILE_INFO>>,0>>::_Find_lower_bound<_GUID>(
      this + 105,
      v32,
      a2);
    v19 = v33;
    if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<_GUID,PENDING_CONNECTION_CATEGORY,std::less<_GUID>,std::allocator<std::pair<_GUID const,PENDING_CONNECTION_CATEGORY>>,0>>::_Lower_bound_duplicate<_GUID>(
                             v20,
                             v33,
                             a2)
      || v19 == this[105] )
    {
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x59A,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
        (const char *)0x8CA,
        phkResult);
    }
    if ( !SystemTimeToFileTime(v19 + 3, (LPFILETIME)&hKey) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x59D,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
        v21);
    v22 = (unsigned int)hKey;
    *a3 = (unsigned int)hKey;
    v23 = HIDWORD(hKey);
    *a4 = HIDWORD(hKey);
    *a5 = v22;
    *a6 = v23;
    v18 = (struct _RTL_CRITICAL_SECTION *)v30;
    if ( v30 )
      goto LABEL_19;
  }
  else
  {
    memset_0(sz, 0, 0x4Eu);
    StringFromGUID2(a2, sz, 39);
    EnterCriticalSection(v10);
    hKey = 0;
    v11 = &qword_1801C7140;
    if ( (unsigned __int64)qword_1801C7158 > 7 )
      v11 = (LPCWSTR *)qword_1801C7140;
    StringCchPrintfW(SubKey, 0x78u, L"%s\\%s", v11, sz);
    v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    if ( v13 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5AD,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
        v13 != 0 ? (const char *)0x8000FFFFLL : 0,
        phkResulta);
    cbData = 16;
    *(_OWORD *)Data = 0;
    v14 = RegQueryValueExW(hKey, L"DateCreated", 0, 0, Data, &cbData);
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5B3,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
        (const char *)(unsigned int)v14,
        phkResultb);
    FileTime = 0;
    if ( !SystemTimeToFileTime((const SYSTEMTIME *)Data, &FileTime) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x5B6,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
        v15);
    cbData = 16;
    *(_OWORD *)v32 = 0;
    v16 = RegQueryValueExW(hKey, L"DateLastConnected", 0, 0, v32, &cbData);
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5BB,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
        (const char *)(unsigned int)v16,
        phkResultc);
    v30 = 0;
    if ( !SystemTimeToFileTime((const SYSTEMTIME *)v32, &v30) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x5BE,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
        v17);
    *a3 = FileTime.dwLowDateTime;
    *a4 = FileTime.dwHighDateTime;
    *a5 = v30.dwLowDateTime;
    *a6 = v30.dwHighDateTime;
    if ( hKey )
      RegCloseKey(hKey);
    if ( v10 )
    {
      v18 = v10;
LABEL_19:
      LeaveCriticalSection(v18);
    }
  }
}

```

## disassembly

```asm
0x18000c198  push    rbp
0x18000c19a  push    rbx
0x18000c19b  push    rsi
0x18000c19c  push    rdi
0x18000c19d  push    r12
0x18000c19f  push    r13
0x18000c1a1  push    r14
0x18000c1a3  push    r15
0x18000c1a5  lea     rbp, [rsp-0D8h]
0x18000c1ad  sub     rsp, 1D8h
0x18000c1b4  mov     rax, cs:__security_cookie
0x18000c1bb  xor     rax, rsp
0x18000c1be  mov     [rbp+110h+var_50], rax
0x18000c1c5  mov     r15, r9
0x18000c1c8  mov     r14, r8
0x18000c1cb  mov     rdi, rdx
0x18000c1ce  mov     rsi, rcx
0x18000c1d1  mov     r12, [rbp+110h+arg_20]
0x18000c1d8  mov     r13, [rbp+110h+arg_28]
0x18000c1df  lea     rbx, [rcx+310h]
0x18000c1e6  mov     rcx, rdx; struct _GUID *
0x18000c1e9  call    ?IsUnidentifiedOrIdentifyingNetwork@@YA_NAEBU_GUID@@@Z; IsUnidentifiedOrIdentifyingNetwork(_GUID const &)
0x18000c1ee  test    al, al
0x18000c1f0  jnz     loc_18000C45B
0x18000c1f6  xor     edx, edx; Val
0x18000c1f8  lea     r8d, [rdx+4Eh]; Size
0x18000c1fc  lea     rcx, [rbp+110h+sz]; void *
0x18000c200  call    memset_0
0x18000c205  mov     r8d, 27h ; '''; cchMax
0x18000c20b  lea     rdx, [rbp+110h+sz]; lpsz
0x18000c20f  mov     rcx, rdi; rguid
0x18000c212  call    cs:__imp_StringFromGUID2
0x18000c218  mov     rcx, rbx; lpCriticalSection
0x18000c21b  call    cs:__imp_EnterCriticalSection
0x18000c221  mov     [rsp+210h+var_1E0], rbx
0x18000c226  xor     edi, edi
0x18000c228  mov     [rsp+210h+hKey], rdi
0x18000c22d  lea     r9, qword_1801C7140
0x18000c234  cmp     cs:qword_1801C7158, 7
0x18000c23c  cmova   r9, cs:qword_1801C7140
0x18000c244  lea     rax, [rbp+110h+sz]
0x18000c248  mov     [rsp+210h+phkResult], rax
0x18000c24d  lea     r8, aSS; "%s\\%s"
0x18000c254  lea     edx, [rdi+78h]; unsigned __int64
0x18000c257  lea     rcx, [rbp+110h+SubKey]; wchar_t *
0x18000c25b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000c260  lea     rax, [rsp+210h+hKey]
0x18000c265  mov     [rsp+210h+phkResult], rax; int
0x18000c26a  mov     r9d, 20019h; samDesired
0x18000c270  xor     r8d, r8d; ulOptions
0x18000c273  lea     rdx, [rbp+110h+SubKey]; lpSubKey
0x18000c277  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c27e  call    cs:__imp_RegOpenKeyExW
0x18000c284  mov     ecx, eax
0x18000c286  mov     esi, 80070000h
0x18000c28b  test    eax, eax
0x18000c28d  jg      loc_18000C412
0x18000c293  mov     eax, ecx
0x18000c295  neg     eax
0x18000c297  sbb     r9d, r9d
0x18000c29a  and     r9d, 8000FFFFh; char *
0x18000c2a1  mov     rax, [rbp+118h]
0x18000c2a8  test    ecx, ecx
0x18000c2aa  jnz     loc_18000C41C
0x18000c2b0  mov     [rsp+210h+cbData], 10h
0x18000c2b8  xorps   xmm0, xmm0
0x18000c2bb  movups  xmmword ptr [rsp+210h+Data], xmm0
0x18000c2c0  lea     rax, [rsp+210h+cbData]
0x18000c2c5  mov     [rsp+210h+lpcbData], rax; lpcbData
0x18000c2ca  lea     rax, [rsp+210h+Data]
0x18000c2cf  mov     [rsp+210h+phkResult], rax; int
0x18000c2d4  xor     r9d, r9d; lpType
0x18000c2d7  xor     r8d, r8d; lpReserved
0x18000c2da  lea     rdx, ValueName; "DateCreated"
0x18000c2e1  mov     rcx, [rsp+210h+hKey]; hKey
0x18000c2e6  call    cs:__imp_RegQueryValueExW
0x18000c2ec  test    eax, eax
0x18000c2ee  jg      loc_18000C3FE
0x18000c2f4  mov     rcx, [rbp+118h]; this
0x18000c2fb  test    eax, eax
0x18000c2fd  js      loc_18000C431
0x18000c303  mov     qword ptr [rsp+210h+FileTime.dwLowDateTime], rdi
0x18000c308  lea     rdx, [rsp+210h+FileTime]; lpFileTime
0x18000c30d  lea     rcx, [rsp+210h+Data]; lpSystemTime
0x18000c312  call    cs:__imp_SystemTimeToFileTime
0x18000c318  mov     rcx, [rbp+118h]; this
0x18000c31f  test    eax, eax
0x18000c321  jz      loc_18000C521
0x18000c327  mov     [rsp+210h+cbData], 10h
0x18000c32f  xorps   xmm0, xmm0
0x18000c332  movups  xmmword ptr [rsp+210h+var_1B8], xmm0
0x18000c337  lea     rax, [rsp+210h+cbData]
0x18000c33c  mov     [rsp+210h+lpcbData], rax; lpcbData
0x18000c341  lea     rax, [rsp+210h+var_1B8]
0x18000c346  mov     [rsp+210h+phkResult], rax; int
0x18000c34b  xor     r9d, r9d; lpType
0x18000c34e  xor     r8d, r8d; lpReserved
0x18000c351  lea     rdx, aDatelastconnec; "DateLastConnected"
0x18000c358  mov     rcx, [rsp+210h+hKey]; hKey
0x18000c35d  call    cs:__imp_RegQueryValueExW
0x18000c363  test    eax, eax
0x18000c365  jg      loc_18000C408
0x18000c36b  mov     rcx, [rbp+118h]; this
0x18000c372  test    eax, eax
0x18000c374  js      loc_18000C446
0x18000c37a  mov     qword ptr [rsp+210h+var_1C8.dwLowDateTime], rdi
0x18000c37f  lea     rdx, [rsp+210h+var_1C8]; lpFileTime
0x18000c384  lea     rcx, [rsp+210h+var_1B8]; lpSystemTime
0x18000c389  call    cs:__imp_SystemTimeToFileTime
0x18000c38f  mov     rcx, [rbp+118h]; this
0x18000c396  test    eax, eax
0x18000c398  jz      loc_18000C533
0x18000c39e  mov     eax, [rsp+210h+FileTime.dwLowDateTime]
0x18000c3a2  mov     [r14], eax
0x18000c3a5  mov     eax, [rsp+210h+FileTime.dwHighDateTime]
0x18000c3a9  mov     [r15], eax
0x18000c3ac  mov     eax, [rsp+210h+var_1C8.dwLowDateTime]
0x18000c3b0  mov     [r12], eax
0x18000c3b4  mov     eax, [rsp+210h+var_1C8.dwHighDateTime]
0x18000c3b8  mov     [r13+0], eax
0x18000c3bc  mov     rcx, [rsp+210h+hKey]; hKey
0x18000c3c1  test    rcx, rcx
0x18000c3c4  jz      short loc_18000C3CD
0x18000c3c6  call    cs:__imp_RegCloseKey
0x18000c3cc  nop
0x18000c3cd  test    rbx, rbx
0x18000c3d0  jz      short loc_18000C3DB
0x18000c3d2  mov     rcx, rbx; lpCriticalSection
0x18000c3d5  call    cs:__imp_LeaveCriticalSection
0x18000c3db  mov     rcx, [rbp+110h+var_50]
0x18000c3e2  xor     rcx, rsp; StackCookie
0x18000c3e5  call    __security_check_cookie
0x18000c3ea  add     rsp, 1D8h
0x18000c3f1  pop     r15
0x18000c3f3  pop     r14
0x18000c3f5  pop     r13
0x18000c3f7  pop     r12
0x18000c3f9  pop     rdi
0x18000c3fa  pop     rsi
0x18000c3fb  pop     rbx
0x18000c3fc  pop     rbp
0x18000c3fd  retn
0x18000c3fe  movzx   eax, ax
0x18000c401  or      eax, esi
0x18000c403  jmp     loc_18000C2F4
0x18000c408  movzx   eax, ax
0x18000c40b  or      eax, esi
0x18000c40d  jmp     loc_18000C36B
0x18000c412  movzx   ecx, ax
0x18000c415  or      ecx, esi
0x18000c417  jmp     loc_18000C293
0x18000c41c  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x18000c423  mov     edx, 5ADh; void *
0x18000c428  mov     rcx, rax; this
0x18000c42b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c431  mov     r9d, eax; char *
0x18000c434  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x18000c43b  mov     edx, 5B3h; void *
0x18000c440  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c446  mov     r9d, eax; char *
0x18000c449  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x18000c450  mov     edx, 5BBh; void *
0x18000c455  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c45b  mov     [rsp+210h+hKey], 0
0x18000c464  mov     qword ptr [rsp+210h+var_1C8.dwLowDateTime], 0
0x18000c46d  mov     rdx, rbx
0x18000c470  lea     rcx, [rsp+210h+var_1C8]
0x18000c475  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18000c47a  nop
0x18000c47b  mov     r8, rdi
0x18000c47e  lea     rdx, [rsp+210h+var_1B8]
0x18000c483  lea     rcx, [rsi+348h]
0x18000c48a  call    ??$_Find_lower_bound@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UCONNECTED_PROFILE_INFO@NetworkPropertyMaps@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UCONNECTED_PROFILE_INFO@NetworkPropertyMaps@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UCONNECTED_PROFILE_INFO@NetworkPropertyMaps@@@std@@PEAX@std@@@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,NetworkPropertyMaps::CONNECTED_PROFILE_INFO,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkPropertyMaps::CONNECTED_PROFILE_INFO>>,0>>::_Find_lower_bound<_GUID>(_GUID const &)
0x18000c48f  mov     r8, rdi
0x18000c492  mov     rbx, [rsp+210h+var_1A8]
0x18000c497  mov     rdx, rbx
0x18000c49a  call    ??$_Lower_bound_duplicate@U_GUID@@@?$_Tree@V?$_Tmap_traits@U_GUID@@UPENDING_CONNECTION_CATEGORY@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UPENDING_CONNECTION_CATEGORY@@@std@@@4@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UPENDING_CONNECTION_CATEGORY@@@std@@PEAX@1@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,PENDING_CONNECTION_CATEGORY,std::less<_GUID>,std::allocator<std::pair<_GUID const,PENDING_CONNECTION_CATEGORY>>,0>>::_Lower_bound_duplicate<_GUID>(std::_Tree_node<std::pair<_GUID const,PENDING_CONNECTION_CATEGORY>,void *> * const,_GUID const &)
0x18000c49f  test    al, al
0x18000c4a1  jz      short loc_18000C502
0x18000c4a3  cmp     rbx, [rsi+348h]
0x18000c4aa  jz      short loc_18000C502
0x18000c4ac  lea     rcx, [rbx+30h]; lpSystemTime
0x18000c4b0  lea     rdx, [rsp+210h+hKey]; lpFileTime
0x18000c4b5  call    cs:__imp_SystemTimeToFileTime
0x18000c4bb  mov     rcx, [rbp+118h]; this
0x18000c4c2  test    eax, eax
0x18000c4c4  jz      short loc_18000C4F0
0x18000c4c6  mov     rax, [rsp+210h+hKey]
0x18000c4cb  mov     [r14], eax
0x18000c4ce  mov     ecx, dword ptr [rsp+210h+hKey+4]
0x18000c4d2  mov     [r15], ecx
0x18000c4d5  mov     [r12], eax
0x18000c4d9  mov     [r13+0], ecx
0x18000c4dd  mov     rcx, qword ptr [rsp+210h+var_1C8.dwLowDateTime]
0x18000c4e2  test    rcx, rcx
0x18000c4e5  jz      loc_18000C3DB
0x18000c4eb  jmp     loc_18000C3D5
0x18000c4f0  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x18000c4f7  mov     edx, 59Dh; void *
0x18000c4fc  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000c502  mov     rcx, [rbp+118h]; this
0x18000c509  mov     r9d, 8CAh; char *
0x18000c50f  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x18000c516  mov     edx, 59Ah; void *
0x18000c51b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000c521  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x18000c528  mov     edx, 5B6h; void *
0x18000c52d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000c533  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x18000c53a  mov     edx, 5BEh; void *
0x18000c53f  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
