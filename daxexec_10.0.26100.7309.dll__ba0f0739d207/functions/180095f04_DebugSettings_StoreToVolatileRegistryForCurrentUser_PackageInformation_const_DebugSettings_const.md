# DebugSettings::StoreToVolatileRegistryForCurrentUser(PackageInformation const &,DebugSettings const &)

- ea: `0x180095f04`
- end: `0x1800960ba`
- name: `?StoreToVolatileRegistryForCurrentUser@DebugSettings@@SAXAEBVPackageInformation@@AEBV1@@Z`
- size: `438`
- prototype: `static void(const struct PackageInformation *, const struct DebugSettings *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180096460`

## callees

- `0x1800053a0`
- `0x180011820`
- `0x1800118c0`
- `0x180013100`
- `0x180095790`
- `0x180095f04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180096051`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180096051`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180095fea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096034`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180095fea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180096034`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180095f95`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180095f95`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall DebugSettings::StoreToVolatileRegistryForCurrentUser(
        const struct PackageInformation *a1,
        const struct DebugSettings *a2)
{
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  const BYTE *v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-29h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-29h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-29h]
  HKEY hKey; // [rsp+50h] [rbp+7h] BYREF
  int v12; // [rsp+58h] [rbp+Fh]
  HKEY *p_hKey; // [rsp+60h] [rbp+17h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp+1Fh] BYREF
  char v15; // [rsp+70h] [rbp+27h]
  LPCWSTR lpSubKey[4]; // [rsp+78h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v12 = 0;
  GetDebugKeyPathForPackage(lpSubKey);
  hKey = 0;
  v12 = 1;
  p_hKey = &hKey;
  phkResult = 0;
  v15 = 1;
  v3 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v3 = lpSubKey[0];
  v4 = RegCreateKeyExW(HKEY_CURRENT_USER, v3, 0, 0, 1u, 0x2011Fu, 0, &phkResult, 0);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x30,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
      (const char *)v4,
      dwOptions);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  std::wstring::~wstring(lpSubKey);
  v5 = (const BYTE *)a2;
  if ( *((_QWORD *)a2 + 3) > 7u )
    v5 = *(const BYTE **)a2;
  v6 = RegSetValueExW(hKey, 0, 0, 1u, v5, 2 * *((_DWORD *)a2 + 4));
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
      (const char *)v6,
      dwOptionsa);
  if ( *((_BYTE *)a2 + 56) )
  {
    v7 = RegSetValueExW(
           hKey,
           L"DebuggerEnvironment",
           0,
           7u,
           *((const BYTE **)a2 + 4),
           2 * ((__int64)(*((_QWORD *)a2 + 5) - *((_QWORD *)a2 + 4)) >> 1));
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
        (const char *)v7,
        dwOptionsb);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180095f04  mov     [rsp-8+arg_10], rbx
0x180095f09  push    rbp
0x180095f0a  lea     rbp, [rsp-57h]
0x180095f0f  sub     rsp, 0A0h
0x180095f16  mov     rax, cs:__security_cookie
0x180095f1d  xor     rax, rsp
0x180095f20  mov     [rbp+57h+var_8], rax
0x180095f24  mov     rbx, rdx
0x180095f27  and     [rbp+57h+var_48], 0
0x180095f2b  mov     rdx, rcx
0x180095f2e  lea     rcx, [rbp+57h+lpSubKey]; void *
0x180095f32  call    ?GetDebugKeyPathForPackage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVPackageInformation@@@Z; GetDebugKeyPathForPackage(PackageInformation const &)
0x180095f37  nop
0x180095f38  and     [rbp+57h+hKey], 0
0x180095f3d  mov     [rbp+57h+var_48], 1
0x180095f44  lea     rax, [rbp+57h+hKey]
0x180095f48  mov     [rbp+57h+var_40], rax
0x180095f4c  and     [rbp+57h+var_38], 0
0x180095f51  mov     [rbp+57h+var_30], 1
0x180095f55  lea     rdx, [rbp+57h+lpSubKey]
0x180095f59  cmp     [rbp+57h+var_10], 7
0x180095f5e  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180095f63  and     [rsp+0A0h+var_60], 0
0x180095f69  lea     rax, [rbp+57h+var_38]
0x180095f6d  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180095f72  and     [rsp+0A0h+var_70], 0
0x180095f78  mov     [rsp+0A0h+samDesired], 2011Fh; samDesired
0x180095f80  mov     [rsp+0A0h+dwOptions], 1; unsigned int
0x180095f88  xor     r9d, r9d; lpClass
0x180095f8b  xor     r8d, r8d; Reserved
0x180095f8e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180095f95  call    cs:__imp_RegCreateKeyExW
0x180095f9c  nop     dword ptr [rax+rax+00h]
0x180095fa1  mov     rcx, [rbp+5Fh]; this
0x180095fa5  test    eax, eax
0x180095fa7  jnz     loc_180096090
0x180095fad  lea     rcx, [rbp+57h+var_40]
0x180095fb1  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180095fb6  nop
0x180095fb7  lea     rcx, [rbp+57h+lpSubKey]; void *
0x180095fbb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180095fc0  mov     eax, [rbx+10h]
0x180095fc3  add     eax, eax
0x180095fc5  mov     rcx, rbx
0x180095fc8  cmp     qword ptr [rbx+18h], 7
0x180095fcd  jbe     short loc_180095FD2
0x180095fcf  mov     rcx, [rbx]
0x180095fd2  mov     [rsp+0A0h+samDesired], eax; cbData
0x180095fd6  mov     qword ptr [rsp+0A0h+dwOptions], rcx; unsigned int
0x180095fdb  mov     r9d, 1; dwType
0x180095fe1  xor     r8d, r8d; Reserved
0x180095fe4  xor     edx, edx; lpValueName
0x180095fe6  mov     rcx, [rbp+57h+hKey]; hKey
0x180095fea  call    cs:__imp_RegSetValueExW
0x180095ff1  nop     dword ptr [rax+rax+00h]
0x180095ff6  mov     rcx, [rbp+5Fh]; this
0x180095ffa  test    eax, eax
0x180095ffc  jnz     loc_1800960A5
0x180096002  cmp     [rbx+38h], al
0x180096005  jz      short loc_180096048
0x180096007  mov     rcx, [rbx+20h]
0x18009600b  mov     rax, [rbx+28h]
0x18009600f  sub     rax, rcx
0x180096012  sar     rax, 1
0x180096015  add     eax, eax
0x180096017  mov     [rsp+0A0h+samDesired], eax; cbData
0x18009601b  mov     qword ptr [rsp+0A0h+dwOptions], rcx; unsigned int
0x180096020  mov     r9d, 7; dwType
0x180096026  xor     r8d, r8d; Reserved
0x180096029  lea     rdx, aDebuggerenviro; "DebuggerEnvironment"
0x180096030  mov     rcx, [rbp+57h+hKey]; hKey
0x180096034  call    cs:__imp_RegSetValueExW
0x18009603b  nop     dword ptr [rax+rax+00h]
0x180096040  mov     rcx, [rbp+5Fh]; this
0x180096044  test    eax, eax
0x180096046  jnz     short loc_18009607B
0x180096048  mov     rcx, [rbp+57h+hKey]; hKey
0x18009604c  test    rcx, rcx
0x18009604f  jz      short loc_18009605D
0x180096051  call    cs:__imp_RegCloseKey
0x180096058  nop     dword ptr [rax+rax+00h]
0x18009605d  mov     rcx, [rbp+57h+var_8]
0x180096061  xor     rcx, rsp; StackCookie
0x180096064  call    __security_check_cookie
0x180096069  mov     rbx, [rsp+0A0h+arg_10]
0x180096071  add     rsp, 0A0h
0x180096078  pop     rbp
0x180096079  retn
0x18009607b  mov     r9d, eax; char *
0x18009607e  lea     r8, aOnecoreBaseApp_68; "onecore\\base\\appmodel\\execmodel\\des"...
0x180096085  mov     edx, 7Ch ; '|'; void *
0x18009608a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180096090  mov     r9d, eax; char *
0x180096093  lea     r8, aOnecoreBaseApp_68; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009609a  mov     edx, 30h ; '0'; void *
0x18009609f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800960a5  mov     r9d, eax; char *
0x1800960a8  lea     r8, aOnecoreBaseApp_68; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800960af  mov     edx, 76h ; 'v'; void *
0x1800960b4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
