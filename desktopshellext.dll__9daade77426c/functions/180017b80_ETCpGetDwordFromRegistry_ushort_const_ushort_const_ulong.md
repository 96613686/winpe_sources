# ETCpGetDwordFromRegistry(ushort const *,ushort const *,ulong &)

- ea: `0x180017b80`
- end: `0x180017c79`
- name: `?ETCpGetDwordFromRegistry@@YAJPEBG0AEAK@Z`
- size: `249`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, LPBYTE lpData)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800703b0`
- `0x180075218`

## callees

- `0x1800108cc`
- `0x180017988`
- `0x180017b80`
- `0x180017c80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017bf4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180017bf4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017c39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017c68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017c39`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017c68`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017bbe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017bbe`

## string_xrefs

- `0x180017c0d`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`
- `0x180017c4b`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`

## pseudocode

```c
__int64 __fastcall ETCpGetDwordFromRegistry(LPCWSTR lpSubKey, LPCWSTR lpValueName, LPBYTE lpData)
{
  HKEY *v6; // rax
  LSTATUS v7; // eax
  LSTATUS v8; // ebx
  __int64 v9; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  DWORD cbData; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  DWORD Type; // [rsp+88h] [rbp+40h] BYREF

  hKey[0] = 0;
  v6 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(hKey);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, v6);
  Type = 4;
  v8 = v7;
  cbData = 4;
  if ( v7 || (v8 = RegQueryValueExW(hKey[0], lpValueName, 0, &Type, lpData, &cbData)) != 0 )
  {
    if ( v8 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
        (const char *)(unsigned int)v8,
        phkResult);
    goto LABEL_13;
  }
  if ( Type != 4 )
  {
    v9 = 98;
LABEL_5:
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v9,
           (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
           (const char *)0xD,
           phkResult);
LABEL_13:
    if ( hKey[0] )
      RegCloseKey(hKey[0]);
    return (unsigned int)v8;
  }
  if ( cbData != 4 )
  {
    v9 = 102;
    goto LABEL_5;
  }
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return 0;
}

```

## disassembly

```asm
0x180017b80  push    rbp
0x180017b82  push    rbx
0x180017b83  push    rsi
0x180017b84  push    rdi
0x180017b85  mov     rbp, rsp
0x180017b88  sub     rsp, 48h
0x180017b8c  mov     rbx, rcx
0x180017b8f  mov     [rbp+hKey], 0
0x180017b97  lea     rcx, [rbp+hKey]
0x180017b9b  mov     rdi, r8
0x180017b9e  mov     rsi, rdx
0x180017ba1  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x180017ba6  mov     r9d, 1; samDesired
0x180017bac  mov     [rsp+48h+phkResult], rax; int
0x180017bb1  xor     r8d, r8d; ulOptions
0x180017bb4  mov     rdx, rbx; lpSubKey
0x180017bb7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017bbe  call    cs:__imp_RegOpenKeyExW
0x180017bc4  mov     [rbp+Type], 4
0x180017bcb  mov     ebx, eax
0x180017bcd  mov     [rbp+cbData], 4
0x180017bd4  test    eax, eax
0x180017bd6  jnz     short loc_180017C43
0x180017bd8  mov     rcx, [rbp+hKey]; hKey
0x180017bdc  lea     rax, [rbp+cbData]
0x180017be0  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180017be5  lea     r9, [rbp+Type]; lpType
0x180017be9  xor     r8d, r8d; lpReserved
0x180017bec  mov     [rsp+48h+phkResult], rdi; unsigned int
0x180017bf1  mov     rdx, rsi; lpValueName
0x180017bf4  call    cs:__imp_RegQueryValueExW
0x180017bfa  mov     ebx, eax
0x180017bfc  test    eax, eax
0x180017bfe  jnz     short loc_180017C43
0x180017c00  cmp     [rbp+Type], 4
0x180017c04  jz      short loc_180017C23
0x180017c06  lea     edx, [rax+62h]; void *
0x180017c09  mov     rcx, [rbp+20h]; this
0x180017c0d  lea     r8, aOnecoreInterna_15; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180017c14  mov     r9d, 0Dh; char *
0x180017c1a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180017c1f  mov     ebx, eax
0x180017c21  jmp     short loc_180017C5F
0x180017c23  cmp     [rbp+cbData], 4
0x180017c27  jz      short loc_180017C30
0x180017c29  mov     edx, 66h ; 'f'
0x180017c2e  jmp     short loc_180017C09
0x180017c30  mov     rcx, [rbp+hKey]; hKey
0x180017c34  test    rcx, rcx
0x180017c37  jz      short loc_180017C3F
0x180017c39  call    cs:__imp_RegCloseKey
0x180017c3f  xor     eax, eax
0x180017c41  jmp     short loc_180017C70
0x180017c43  test    ebx, ebx
0x180017c45  jns     short loc_180017C5F
0x180017c47  mov     rcx, [rbp+20h]; this
0x180017c4b  lea     r8, aOnecoreInterna_15; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180017c52  mov     r9d, ebx; char *
0x180017c55  mov     edx, 6Bh ; 'k'; void *
0x180017c5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c5f  mov     rcx, [rbp+hKey]; hKey
0x180017c63  test    rcx, rcx
0x180017c66  jz      short loc_180017C6E
0x180017c68  call    cs:__imp_RegCloseKey
0x180017c6e  mov     eax, ebx
0x180017c70  add     rsp, 48h
0x180017c74  pop     rdi
0x180017c75  pop     rsi
0x180017c76  pop     rbx
0x180017c77  pop     rbp
0x180017c78  retn
```
