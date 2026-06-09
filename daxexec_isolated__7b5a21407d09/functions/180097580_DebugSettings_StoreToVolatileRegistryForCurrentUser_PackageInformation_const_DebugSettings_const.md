# DebugSettings::StoreToVolatileRegistryForCurrentUser(PackageInformation const &,DebugSettings const &)

- ea: `0x180097580`
- end: `0x18009778c`
- name: `?StoreToVolatileRegistryForCurrentUser@DebugSettings@@SAXAEBVPackageInformation@@AEBV1@@Z`
- size: `524`
- prototype: `void __fastcall(const struct PackageInformation *, const struct DebugSettings *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180097d40`

## callees

- `0x180004f70`
- `0x180013510`
- `0x180014e74`
- `0x1800970f0`
- `0x180097580`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180097672`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180097672`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097653`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800976b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180097700`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800976b6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180097700`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180097664`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009771d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180097664`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009771d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180097626`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180097626`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DebugSettings::StoreToVolatileRegistryForCurrentUser(
        const struct PackageInformation *a1,
        const struct DebugSettings *a2)
{
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  HKEY v5; // r15
  HKEY *v6; // rsi
  HKEY v7; // r14
  DWORD LastError; // ebx
  const BYTE *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-49h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-49h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-49h]
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  int v16; // [rsp+58h] [rbp-11h]
  HKEY *p_hKey; // [rsp+60h] [rbp-9h]
  HKEY phkResult; // [rsp+68h] [rbp-1h] BYREF
  char v19; // [rsp+70h] [rbp+7h]
  LPCWSTR lpSubKey[4]; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  GetDebugKeyPathForPackage(lpSubKey, a1);
  hKey = 0;
  v16 = 1;
  p_hKey = &hKey;
  phkResult = 0;
  v19 = 1;
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
  if ( v19 )
  {
    v5 = phkResult;
    v6 = p_hKey;
    v7 = *p_hKey;
    if ( *p_hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v7);
      SetLastError(LastError);
    }
    *v6 = v5;
  }
  std::wstring::~wstring(lpSubKey);
  if ( *((_QWORD *)a2 + 3) <= 7u )
    v9 = (const BYTE *)a2;
  else
    v9 = *(const BYTE **)a2;
  v10 = RegSetValueExW(hKey, 0, 0, 1u, v9, 2 * *((_DWORD *)a2 + 4));
  if ( v10 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
      (const char *)v10,
      dwOptionsa);
  if ( *((_BYTE *)a2 + 56) )
  {
    v11 = RegSetValueExW(
            hKey,
            L"DebuggerEnvironment",
            0,
            7u,
            *((const BYTE **)a2 + 4),
            2 * ((__int64)(*((_QWORD *)a2 + 5) - *((_QWORD *)a2 + 4)) >> 1));
    if ( v11 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x7C,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\sharedlib\\debugsettings.cpp",
        (const char *)v11,
        dwOptionsb);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180097580  mov     [rsp-8+arg_10], rbx
0x180097585  push    rbp
0x180097586  push    rsi
0x180097587  push    rdi
0x180097588  push    r14
0x18009758a  push    r15
0x18009758c  lea     rbp, [rsp-37h]
0x180097591  sub     rsp, 0A0h
0x180097598  mov     rax, cs:__security_cookie
0x18009759f  xor     rax, rsp
0x1800975a2  mov     [rbp+57h+var_28], rax
0x1800975a6  mov     rdi, rdx
0x1800975a9  mov     [rbp+57h+var_68], 0
0x1800975b0  mov     rdx, rcx
0x1800975b3  lea     rcx, [rbp+57h+lpSubKey]
0x1800975b7  call    ?GetDebugKeyPathForPackage@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVPackageInformation@@@Z; GetDebugKeyPathForPackage(PackageInformation const &)
0x1800975bc  nop
0x1800975bd  mov     [rbp+57h+hKey], 0
0x1800975c5  mov     [rbp+57h+var_68], 1
0x1800975cc  lea     rax, [rbp+57h+hKey]
0x1800975d0  mov     [rbp+57h+var_60], rax
0x1800975d4  mov     [rbp+57h+var_58], 0
0x1800975dc  mov     [rbp+57h+var_50], 1
0x1800975e0  lea     rdx, [rbp+57h+lpSubKey]
0x1800975e4  cmp     [rbp+57h+var_30], 7
0x1800975e9  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800975ee  mov     [rsp+0C0h+lpdwDisposition], 0; lpdwDisposition
0x1800975f7  lea     rax, [rbp+57h+var_58]
0x1800975fb  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180097600  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180097609  mov     [rsp+0C0h+samDesired], 2011Fh; samDesired
0x180097611  mov     [rsp+0C0h+dwOptions], 1; unsigned int
0x180097619  xor     r9d, r9d; lpClass
0x18009761c  xor     r8d, r8d; Reserved
0x18009761f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180097626  call    cs:__imp_RegCreateKeyExW
0x18009762d  nop     dword ptr [rax+rax+00h]
0x180097632  mov     rcx, [rbp+5Fh]; this
0x180097636  test    eax, eax
0x180097638  jnz     loc_180097762
0x18009763e  cmp     [rbp+57h+var_50], al
0x180097641  jz      short loc_180097681
0x180097643  mov     r15, [rbp+57h+var_58]
0x180097647  mov     rsi, [rbp+57h+var_60]
0x18009764b  mov     r14, [rsi]
0x18009764e  test    r14, r14
0x180097651  jz      short loc_18009767E
0x180097653  call    cs:__imp_GetLastError
0x18009765a  nop     dword ptr [rax+rax+00h]
0x18009765f  mov     ebx, eax
0x180097661  mov     rcx, r14; hKey
0x180097664  call    cs:__imp_RegCloseKey
0x18009766b  nop     dword ptr [rax+rax+00h]
0x180097670  mov     ecx, ebx; dwErrCode
0x180097672  call    cs:__imp_SetLastError
0x180097679  nop     dword ptr [rax+rax+00h]
0x18009767e  mov     [rsi], r15
0x180097681  lea     rcx, [rbp+57h+lpSubKey]; void *
0x180097685  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009768a  mov     eax, [rdi+10h]
0x18009768d  add     eax, eax
0x18009768f  cmp     qword ptr [rdi+18h], 7
0x180097694  jbe     short loc_18009769B
0x180097696  mov     rcx, [rdi]
0x180097699  jmp     short loc_18009769E
0x18009769b  mov     rcx, rdi
0x18009769e  mov     [rsp+0C0h+samDesired], eax; cbData
0x1800976a2  mov     qword ptr [rsp+0C0h+dwOptions], rcx; unsigned int
0x1800976a7  mov     r9d, 1; dwType
0x1800976ad  xor     r8d, r8d; Reserved
0x1800976b0  xor     edx, edx; lpValueName
0x1800976b2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800976b6  call    cs:__imp_RegSetValueExW
0x1800976bd  nop     dword ptr [rax+rax+00h]
0x1800976c2  mov     rcx, [rbp+5Fh]; this
0x1800976c6  test    eax, eax
0x1800976c8  jnz     loc_180097777
0x1800976ce  cmp     [rdi+38h], al
0x1800976d1  jz      short loc_180097714
0x1800976d3  mov     rdx, [rdi+20h]
0x1800976d7  mov     rax, [rdi+28h]
0x1800976db  sub     rax, rdx
0x1800976de  sar     rax, 1
0x1800976e1  add     eax, eax
0x1800976e3  mov     [rsp+0C0h+samDesired], eax; cbData
0x1800976e7  mov     qword ptr [rsp+0C0h+dwOptions], rdx; unsigned int
0x1800976ec  mov     r9d, 7; dwType
0x1800976f2  xor     r8d, r8d; Reserved
0x1800976f5  lea     rdx, aDebuggerenviro; "DebuggerEnvironment"
0x1800976fc  mov     rcx, [rbp+57h+hKey]; hKey
0x180097700  call    cs:__imp_RegSetValueExW
0x180097707  nop     dword ptr [rax+rax+00h]
0x18009770c  mov     rcx, [rbp+5Fh]; this
0x180097710  test    eax, eax
0x180097712  jnz     short loc_18009774D
0x180097714  mov     rcx, [rbp+57h+hKey]; hKey
0x180097718  test    rcx, rcx
0x18009771b  jz      short loc_180097729
0x18009771d  call    cs:__imp_RegCloseKey
0x180097724  nop     dword ptr [rax+rax+00h]
0x180097729  mov     rcx, [rbp+57h+var_28]
0x18009772d  xor     rcx, rsp; StackCookie
0x180097730  call    __security_check_cookie
0x180097735  mov     rbx, [rsp+0C0h+arg_10]
0x18009773d  add     rsp, 0A0h
0x180097744  pop     r15
0x180097746  pop     r14
0x180097748  pop     rdi
0x180097749  pop     rsi
0x18009774a  pop     rbp
0x18009774b  retn
0x18009774d  mov     r9d, eax; char *
0x180097750  lea     r8, aOnecoreBaseApp_69; "onecore\\base\\appmodel\\execmodel\\des"...
0x180097757  mov     edx, 7Ch ; '|'; void *
0x18009775c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180097762  mov     r9d, eax; char *
0x180097765  lea     r8, aOnecoreBaseApp_69; "onecore\\base\\appmodel\\execmodel\\des"...
0x18009776c  mov     edx, 30h ; '0'; void *
0x180097771  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180097777  mov     r9d, eax; char *
0x18009777a  lea     r8, aOnecoreBaseApp_69; "onecore\\base\\appmodel\\execmodel\\des"...
0x180097781  mov     edx, 76h ; 'v'; void *
0x180097786  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
