# NetworkPropertyMaps::InternalGetNetworkDescription(_GUID const &,wchar_t * *)

- ea: `0x180013d70`
- end: `0x18001419f`
- name: `?InternalGetNetworkDescription@NetworkPropertyMaps@@AEBAXAEBU_GUID@@PEAPEA_W@Z`
- size: `1071`
- prototype: `void(NetworkPropertyMaps *__hidden this, const struct _GUID *, wchar_t **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180034940`

## callees

- `0x180013d70`
- `0x180014aa0`
- `0x180014d80`
- `0x180014e20`
- `0x180014fb0`
- `0x180015608`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800aba25`
- `0x1800baf04`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013e31`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180013e31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ef9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ef9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014026`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014026`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180013ee9`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180013ee9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013feb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013feb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014081`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014135`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014081`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014135`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013fc4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800140cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013fc4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800140cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014017`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014017`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013f5d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013f5d`

## string_xrefs

- `0x1800140dd`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x1800140f5`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x18001418d`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall NetworkPropertyMaps::InternalGetNetworkDescription(
        NetworkPropertyMaps *this,
        const struct _GUID *a2,
        HKEY *a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  BOOL v9; // ebx
  const char *v10; // r9
  HKEY v11; // r9
  struct _RTL_CRITICAL_SECTION *v12; // r15
  LPCWSTR *v13; // r9
  LSTATUS v14; // eax
  unsigned int v15; // ecx
  HKEY v16; // r12
  LSTATUS v17; // eax
  unsigned int v18; // r14d
  signed int v19; // ebx
  BYTE *v20; // rax
  wchar_t *v21; // rsi
  LSTATUS v22; // eax
  wchar_t *v23; // r9
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type[2]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  OLECHAR sz[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v30; // [rsp+60h] [rbp-A0h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  _BYTE v32[30]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[256]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v34[2064]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+AF8h] [rbp+9F8h]

  *a3 = 0;
  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&g_unidentifiedGuid.Data1;
  if ( !v6 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)g_unidentifiedGuid.Data4;
  if ( !v6 )
    goto LABEL_7;
  v7 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&g_identifyingGuid.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&g_identifyingGuid.Data1 )
    v7 = *(_QWORD *)a2->Data4 - *(_QWORD *)g_identifyingGuid.Data4;
  if ( !v7 )
  {
LABEL_7:
    v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&g_unidentifiedGuid.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&g_unidentifiedGuid.Data1 )
      v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)g_unidentifiedGuid.Data4;
    v9 = v8 != 0;
    memset_0(Buffer, 0, sizeof(Buffer));
    if ( !LoadStringW(g_moduleHandle, v9 + 204, Buffer, 256) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x51A,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
        v10);
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
      &hKey,
      Buffer);
    v11 = hKey;
    *a3 = hKey;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_87eca99fb86d3f2974af9b60843a1c5f_Traceguids, v11);
    return;
  }
  memset_0(v34, 0, 0x802u);
  if ( (unsigned int)GetPolicyData(a2, 2u, v34) == 1 )
  {
    *(_OWORD *)sz = 0;
    v30 = 0;
    v31 = 0;
    memset(v32, 0, sizeof(v32));
    StringFromGUID2(a2, sz, 39);
    v12 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 784);
    EnterCriticalSection(v12);
    hKey = 0;
    v13 = &qword_1801C7140;
    if ( (unsigned __int64)qword_1801C7158 > 7 )
      v13 = (LPCWSTR *)qword_1801C7140;
    StringCchPrintfW(Buffer, 0x78u, L"%s\\%s", v13, sz);
    v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, Buffer, 0, 0x20019u, &hKey);
    v15 = v14;
    if ( v14 > 0 )
      v15 = (unsigned __int16)v14 | 0x80070000;
    if ( v15 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x577,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
        v15 != 0 ? (const char *)0x8000FFFFLL : 0,
        phkResult);
    Type[0] = 0;
    v16 = hKey;
    *a3 = 0;
    cbData = 200;
    v17 = RegQueryValueExW(v16, L"Description", 0, Type, (LPBYTE)Buffer, &cbData);
    v18 = v17;
    if ( v17 > 0 )
      v18 = (unsigned __int16)v17 | 0x80070000;
    v19 = 0;
    if ( v18 != -2147024662 )
      v19 = v18;
    if ( v19 )
      goto LABEL_26;
    v20 = (BYTE *)CoTaskMemAlloc(cbData);
    v21 = (wchar_t *)v20;
    if ( !v20 )
    {
      v19 = -2147024882;
LABEL_26:
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x57A,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
          (const char *)(unsigned int)v19,
          phkResulta);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v12 )
        LeaveCriticalSection(v12);
      return;
    }
    if ( v18 == -2147024662 )
    {
      v22 = RegQueryValueExW(v16, L"Description", 0, Type, v20, &cbData);
      v19 = v22;
      if ( v22 > 0 )
        v19 = (unsigned __int16)v22 | 0x80070000;
      if ( v19 )
        goto LABEL_35;
    }
    else
    {
      memcpy_0(v20, Buffer, cbData);
      v19 = 0;
    }
    *a3 = (HKEY)v21;
    v21 = 0;
LABEL_35:
    if ( v21 )
      CoTaskMemFree(v21);
    goto LABEL_26;
  }
  *(_QWORD *)Type = 0;
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
    Type,
    v34);
  v23 = *(wchar_t **)Type;
  *(_QWORD *)Type = 0;
  *a3 = (HKEY)v23;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_87eca99fb86d3f2974af9b60843a1c5f_Traceguids, v23);
    if ( *(_QWORD *)Type )
      CoTaskMemFree(*(LPVOID *)Type);
  }
}

```

## disassembly

```asm
0x180013d70  mov     [rsp-8+arg_18], rbx
0x180013d75  push    rbp
0x180013d76  push    rsi
0x180013d77  push    rdi
0x180013d78  push    r12
0x180013d7a  push    r13
0x180013d7c  push    r14
0x180013d7e  push    r15
0x180013d80  lea     rbp, [rsp-9C0h]
0x180013d88  sub     rsp, 0AC0h
0x180013d8f  mov     rax, cs:__security_cookie
0x180013d96  xor     rax, rsp
0x180013d99  mov     [rbp+9F0h+var_40], rax
0x180013da0  mov     rdi, r8
0x180013da3  mov     rbx, rdx
0x180013da6  mov     r15, rcx
0x180013da9  xor     r13d, r13d
0x180013dac  mov     [r8], r13
0x180013daf  mov     rax, [rdx]
0x180013db2  mov     r8, qword ptr cs:?g_unidentifiedGuid@@3U_GUID@@A.Data1; _GUID g_unidentifiedGuid ...
0x180013db9  mov     rdx, qword ptr cs:?g_unidentifiedGuid@@3U_GUID@@A.Data4; _GUID g_unidentifiedGuid ...
0x180013dc0  sub     rax, r8
0x180013dc3  jnz     short loc_180013DCC
0x180013dc5  mov     rax, [rbx+8]
0x180013dc9  sub     rax, rdx
0x180013dcc  test    rax, rax
0x180013dcf  jz      short loc_180013DF1
0x180013dd1  mov     rax, [rbx]
0x180013dd4  sub     rax, qword ptr cs:?g_identifyingGuid@@3U_GUID@@A.Data1; _GUID g_identifyingGuid ...
0x180013ddb  jnz     short loc_180013DE8
0x180013ddd  mov     rax, [rbx+8]
0x180013de1  sub     rax, qword ptr cs:?g_identifyingGuid@@3U_GUID@@A.Data4; _GUID g_identifyingGuid ...
0x180013de8  test    rax, rax
0x180013deb  jnz     loc_180013E90
0x180013df1  mov     rax, [rbx]
0x180013df4  sub     rax, r8
0x180013df7  jnz     short loc_180013E00
0x180013df9  mov     rax, [rbx+8]
0x180013dfd  sub     rax, rdx
0x180013e00  mov     ebx, r13d
0x180013e03  test    rax, rax
0x180013e06  setnz   bl
0x180013e09  xor     edx, edx; Val
0x180013e0b  mov     r8d, 200h; Size
0x180013e11  lea     rcx, [rbp+9F0h+Buffer]; void *
0x180013e15  call    memset_0
0x180013e1a  mov     r9d, 100h; cchBufferMax
0x180013e20  lea     r8, [rbp+9F0h+Buffer]; lpBuffer
0x180013e24  lea     edx, [rbx+0CCh]; uID
0x180013e2a  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; hInstance
0x180013e31  call    cs:__imp_LoadStringW
0x180013e37  test    eax, eax
0x180013e39  jz      loc_180014186
0x180013e3f  lea     rdx, [rbp+9F0h+Buffer]
0x180013e43  lea     rcx, [rsp+0AF0h+hKey]
0x180013e48  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x180013e4d  mov     r9, [rsp+0AF0h+hKey]
0x180013e52  mov     [rdi], r9
0x180013e55  lea     rax, WPP_GLOBAL_Control
0x180013e5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e63  cmp     rcx, rax
0x180013e66  jz      loc_18001402C
0x180013e6c  test    byte ptr [rcx+1Ch], 8
0x180013e70  jz      loc_18001402C
0x180013e76  mov     edx, 16h
0x180013e7b  lea     r8, WPP_87eca99fb86d3f2974af9b60843a1c5f_Traceguids
0x180013e82  mov     rcx, [rcx+10h]
0x180013e86  call    WPP_SF_S
0x180013e8b  jmp     loc_18001402C
0x180013e90  xor     edx, edx; Val
0x180013e92  mov     r8d, 802h; Size
0x180013e98  lea     rcx, [rbp+9F0h+var_850]; void *
0x180013e9f  call    memset_0
0x180013ea4  lea     r8, [rbp+9F0h+var_850]
0x180013eab  mov     edx, 2; unsigned int
0x180013eb0  mov     rcx, rbx; Buf1
0x180013eb3  call    ?GetPolicyData@@YAJPEBU_GUID@@KZZ; GetPolicyData(_GUID const *,ulong,...)
0x180013eb8  cmp     eax, 1
0x180013ebb  jnz     loc_180014140
0x180013ec1  xorps   xmm0, xmm0
0x180013ec4  movups  xmmword ptr [rsp+0AF0h+sz], xmm0
0x180013ec9  movups  [rsp+0AF0h+var_A90], xmm0
0x180013ece  movups  [rsp+0AF0h+var_A80], xmm0
0x180013ed3  movups  xmmword ptr [rbp+9F0h+var_A70], xmm0
0x180013ed7  movups  xmmword ptr [rbp+9F0h+var_A70+0Eh], xmm0
0x180013edb  mov     r8d, 27h ; '''; cchMax
0x180013ee1  lea     rdx, [rsp+0AF0h+sz]; lpsz
0x180013ee6  mov     rcx, rbx; rguid
0x180013ee9  call    cs:__imp_StringFromGUID2
0x180013eef  add     r15, 310h
0x180013ef6  mov     rcx, r15; lpCriticalSection
0x180013ef9  call    cs:__imp_EnterCriticalSection
0x180013eff  mov     [rsp+0AF0h+var_AC0], r15
0x180013f04  mov     [rsp+0AF0h+hKey], r13
0x180013f09  lea     r9, qword_1801C7140
0x180013f10  cmp     cs:qword_1801C7158, 7
0x180013f18  cmova   r9, cs:qword_1801C7140
0x180013f20  lea     rax, [rsp+0AF0h+sz]
0x180013f25  mov     [rsp+0AF0h+phkResult], rax
0x180013f2a  lea     r8, aSS; "%s\\%s"
0x180013f31  mov     edx, 78h ; 'x'; unsigned __int64
0x180013f36  lea     rcx, [rbp+9F0h+Buffer]; wchar_t *
0x180013f3a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180013f3f  lea     rax, [rsp+0AF0h+hKey]
0x180013f44  mov     [rsp+0AF0h+phkResult], rax; int
0x180013f49  mov     r9d, 20019h; samDesired
0x180013f4f  xor     r8d, r8d; ulOptions
0x180013f52  lea     rdx, [rbp+9F0h+Buffer]; lpSubKey
0x180013f56  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013f5d  call    cs:__imp_RegOpenKeyExW
0x180013f63  mov     ecx, eax
0x180013f65  test    eax, eax
0x180013f67  jg      loc_18001408C
0x180013f6d  mov     eax, ecx
0x180013f6f  neg     eax
0x180013f71  sbb     r9d, r9d
0x180013f74  and     r9d, 8000FFFFh; char *
0x180013f7b  mov     rax, [rbp+9F8h]
0x180013f82  test    ecx, ecx
0x180013f84  jnz     loc_1800140DD
0x180013f8a  mov     [rsp+0AF0h+Type], r13d
0x180013f8f  mov     r12, [rsp+0AF0h+hKey]
0x180013f94  mov     [rdi], r13
0x180013f97  mov     [rsp+0AF0h+cbData], 0C8h
0x180013f9f  lea     rax, [rsp+0AF0h+cbData]
0x180013fa4  mov     [rsp+0AF0h+lpcbData], rax; lpcbData
0x180013fa9  lea     rax, [rbp+9F0h+Buffer]
0x180013fad  mov     [rsp+0AF0h+phkResult], rax; int
0x180013fb2  lea     r9, [rsp+0AF0h+Type]; lpType
0x180013fb7  xor     r8d, r8d; lpReserved
0x180013fba  lea     rdx, aDescription; "Description"
0x180013fc1  mov     rcx, r12; hKey
0x180013fc4  call    cs:__imp_RegQueryValueExW
0x180013fca  mov     r14d, eax
0x180013fcd  test    eax, eax
0x180013fcf  jg      loc_18001409A
0x180013fd5  mov     ebx, r13d
0x180013fd8  cmp     r14d, 800700EAh
0x180013fdf  cmovnz  ebx, r14d
0x180013fe3  test    ebx, ebx
0x180013fe5  jnz     short loc_180013FFE
0x180013fe7  mov     ecx, [rsp+0AF0h+cbData]; cb
0x180013feb  call    cs:__imp_CoTaskMemAlloc
0x180013ff1  mov     rsi, rax
0x180013ff4  test    rax, rax
0x180013ff7  jnz     short loc_180014056
0x180013ff9  mov     ebx, 8007000Eh
0x180013ffe  mov     rcx, [rbp+9F8h]; this
0x180014005  test    ebx, ebx
0x180014007  js      loc_1800140F2
0x18001400d  mov     rcx, [rsp+0AF0h+hKey]; hKey
0x180014012  test    rcx, rcx
0x180014015  jz      short loc_18001401E
0x180014017  call    cs:__imp_RegCloseKey
0x18001401d  nop
0x18001401e  test    r15, r15
0x180014021  jz      short loc_18001402C
0x180014023  mov     rcx, r15; lpCriticalSection
0x180014026  call    cs:__imp_LeaveCriticalSection
0x18001402c  mov     rcx, [rbp+9F0h+var_40]
0x180014033  xor     rcx, rsp; StackCookie
0x180014036  call    __security_check_cookie
0x18001403b  mov     rbx, [rsp+0AF0h+arg_18]
0x180014043  add     rsp, 0AC0h
0x18001404a  pop     r15
0x18001404c  pop     r14
0x18001404e  pop     r13
0x180014050  pop     r12
0x180014052  pop     rdi
0x180014053  pop     rsi
0x180014054  pop     rbp
0x180014055  retn
0x180014056  cmp     r14d, 800700EAh
0x18001405d  jz      short loc_1800140AA
0x18001405f  mov     r8d, [rsp+0AF0h+cbData]; Size
0x180014064  lea     rdx, [rbp+9F0h+Buffer]; Src
0x180014068  mov     rcx, rsi; void *
0x18001406b  call    memcpy_0
0x180014070  mov     ebx, r13d
0x180014073  mov     [rdi], rsi
0x180014076  mov     rsi, r13
0x180014079  test    rsi, rsi
0x18001407c  jz      short loc_180013FFE
0x18001407e  mov     rcx, rsi; pv
0x180014081  call    cs:__imp_CoTaskMemFree
0x180014087  jmp     loc_180013FFE
0x18001408c  movzx   ecx, ax
0x18001408f  or      ecx, 80070000h
0x180014095  jmp     loc_180013F6D
0x18001409a  movzx   r14d, ax
0x18001409e  or      r14d, 80070000h
0x1800140a5  jmp     loc_180013FD5
0x1800140aa  lea     rax, [rsp+0AF0h+cbData]
0x1800140af  mov     [rsp+0AF0h+lpcbData], rax; lpcbData
0x1800140b4  mov     [rsp+0AF0h+phkResult], rsi; lpData
0x1800140b9  lea     r9, [rsp+0AF0h+Type]; lpType
0x1800140be  xor     r8d, r8d; lpReserved
0x1800140c1  lea     rdx, aDescription; "Description"
0x1800140c8  mov     rcx, r12; hKey
0x1800140cb  call    cs:__imp_RegQueryValueExW
0x1800140d1  mov     ebx, eax
0x1800140d3  test    eax, eax
0x1800140d5  jg      short loc_180014107
0x1800140d7  test    ebx, ebx
0x1800140d9  jnz     short loc_180014079
0x1800140db  jmp     short loc_180014073
0x1800140dd  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x1800140e4  mov     edx, 577h; void *
0x1800140e9  mov     rcx, rax; this
0x1800140ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800140f2  mov     r9d, ebx; char *
0x1800140f5  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x1800140fc  mov     edx, 57Ah; void *
0x180014101  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180014107  movzx   ebx, ax
0x18001410a  or      ebx, 80070000h
0x180014110  jmp     short loc_1800140D7
0x180014112  mov     edx, 17h
0x180014117  lea     r8, WPP_87eca99fb86d3f2974af9b60843a1c5f_Traceguids
0x18001411e  mov     rcx, [rcx+10h]
0x180014122  call    WPP_SF_S
0x180014127  mov     rcx, qword ptr [rsp+0AF0h+Type]; pv
0x18001412c  test    rcx, rcx
0x18001412f  jz      loc_18001402C
0x180014135  call    cs:__imp_CoTaskMemFree
0x18001413b  jmp     loc_18001402C
0x180014140  mov     qword ptr [rsp+0AF0h+Type], r13
0x180014145  lea     rdx, [rbp+9F0h+var_850]
0x18001414c  lea     rcx, [rsp+0AF0h+Type]
0x180014151  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x180014156  mov     r9, qword ptr [rsp+0AF0h+Type]
0x18001415b  mov     qword ptr [rsp+0AF0h+Type], r13
0x180014160  mov     [rdi], r9
0x180014163  lea     rax, WPP_GLOBAL_Control
0x18001416a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014171  cmp     rcx, rax
0x180014174  jz      loc_18001402C
0x18001417a  test    byte ptr [rcx+1Ch], 8
0x18001417e  jz      loc_18001402C
0x180014184  jmp     short loc_180014112
0x180014186  mov     rcx, [rbp+9F8h]; this
0x18001418d  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x180014194  mov     edx, 51Ah; void *
0x180014199  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
