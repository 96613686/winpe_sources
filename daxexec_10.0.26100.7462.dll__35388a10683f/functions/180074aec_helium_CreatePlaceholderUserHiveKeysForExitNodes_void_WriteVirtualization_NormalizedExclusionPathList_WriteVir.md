# helium::CreatePlaceholderUserHiveKeysForExitNodes(void *,WriteVirtualization::NormalizedExclusionPathList<WriteVirtualization::RegistryPath> const &)

- ea: `0x180074aec`
- end: `0x180074d67`
- name: `?CreatePlaceholderUserHiveKeysForExitNodes@helium@@YAXPEAXAEBV?$NormalizedExclusionPathList@VRegistryPath@WriteVirtualization@@@WriteVirtualization@@@Z`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config`

## callers

- `0x18006fabc`

## callees

- `0x1800053a0`
- `0x180011820`
- `0x180013100`
- `0x180074aec`
- `0x180076510`
- `0x1800766e4`
- `0x180096668`
- `0x1800967b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180074b9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180074c92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180074b9a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180074c92`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180074b79`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180074c71`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180074b79`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180074c71`

## string_xrefs

- `0x180074cfb`: `onecore\base\appmodel\execmodel\desktopappx\lib\hivepath.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall helium::CreatePlaceholderUserHiveKeysForExitNodes(__int64 a1, __int64 ***a2)
{
  unsigned __int16 v3; // dx
  __int64 **v4; // rdi
  __int64 *v5; // rbx
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  __int64 **v8; // rax
  __int64 i; // rax
  __int64 *j; // rcx
  const char *v11; // rsi
  unsigned __int16 v12; // r14
  __int64 *v13; // rdi
  __int64 *v14; // rbx
  const WCHAR *v15; // rdx
  unsigned int v16; // eax
  __int64 **v17; // rax
  __int64 *k; // rax
  __int64 *m; // rcx
  DWORD dwOptions; // [rsp+20h] [rbp-39h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-39h]
  HKEY hKey; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v23[16]; // [rsp+58h] [rbp-1h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  LoggedonUserImpersonation::Impersonate(v23, a1);
  v4 = *a2;
  v5 = **a2;
  while ( v5 != (__int64 *)v4 )
  {
    v6 = (const WCHAR *)(v5 + 4);
    hKey = 0;
    if ( (unsigned __int64)v5[7] > 7 )
      v6 = *(const WCHAR **)v6;
    v7 = RegCreateKeyExW(HKEY_CURRENT_USER, v6, 0, 0, 0, 4u, 0, &hKey, 0);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x88,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumdescription.cpp",
        (const char *)v7,
        dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    v8 = (__int64 **)v5[2];
    if ( *((_BYTE *)v8 + 25) )
    {
      for ( i = v5[1]; !*(_BYTE *)(i + 25) && v5 == *(__int64 **)(i + 16); i = *(_QWORD *)(i + 8) )
        v5 = (__int64 *)i;
      v5 = (__int64 *)i;
    }
    else
    {
      v5 = (__int64 *)v5[2];
      for ( j = *v8; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v5 = j;
    }
  }
  v11 = (const char *)&unk_1800DB840;
  do
  {
    v12 = *(_WORD *)v11;
    if ( helium::IsSupportedWowArchitecture((helium *)*(unsigned __int16 *)v11, v3) )
    {
      v13 = (__int64 *)*a2;
      v14 = **a2;
      while ( v14 != v13 )
      {
        helium::TranslateHkcuRelativePathToSupportedWowArchitecture(lpSubKey, v14 + 4, v12);
        hKey = 0;
        v15 = (const WCHAR *)lpSubKey;
        if ( lpSubKey[3] > (LPCWSTR)7 )
          v15 = lpSubKey[0];
        v16 = RegCreateKeyExW(HKEY_CURRENT_USER, v15, 0, 0, 0, 4u, 0, &hKey, 0);
        if ( v16 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x94,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\heliumdescription.cpp",
            (const char *)v16,
            dwOptionsa);
        if ( hKey )
          RegCloseKey(hKey);
        std::wstring::~wstring(lpSubKey);
        v17 = (__int64 **)v14[2];
        if ( *((_BYTE *)v17 + 25) )
        {
          for ( k = (__int64 *)v14[1]; !*((_BYTE *)k + 25) && v14 == (__int64 *)k[2]; k = (__int64 *)k[1] )
            v14 = k;
          v14 = k;
        }
        else
        {
          v14 = (__int64 *)v14[2];
          for ( m = *v17; !*((_BYTE *)m + 25); m = (__int64 *)*m )
            v14 = m;
        }
      }
    }
    v11 += 2;
  }
  while ( v11 != "onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\hivepath.cpp" );
  ImpersonationReverter::~ImpersonationReverter((ImpersonationReverter *)v23);
}

```

## disassembly

```asm
0x180074aec  mov     [rsp-8+arg_8], rbx
0x180074af1  mov     [rsp-8+arg_10], rsi
0x180074af6  push    rbp
0x180074af7  push    rdi
0x180074af8  push    r12
0x180074afa  push    r14
0x180074afc  push    r15
0x180074afe  lea     rbp, [rsp-37h]
0x180074b03  sub     rsp, 90h
0x180074b0a  mov     rax, cs:__security_cookie
0x180074b11  xor     rax, rsp
0x180074b14  mov     [rbp+57h+var_28], rax
0x180074b18  mov     r15, rdx
0x180074b1b  mov     rdx, rcx
0x180074b1e  lea     rcx, [rbp+57h+var_58]
0x180074b22  call    ?Impersonate@LoggedonUserImpersonation@@SA?AU1@PEAX@Z
0x180074b27  nop
0x180074b28  mov     rdi, [r15]
0x180074b2b  mov     rbx, [rdi]
0x180074b2e  xor     r12d, r12d
0x180074b31  cmp     rbx, rdi
0x180074b34  jz      loc_180074BF5
0x180074b3a  lea     rdx, [rbx+20h]
0x180074b3e  mov     [rbp+57h+hKey], r12
0x180074b42  cmp     qword ptr [rdx+18h], 7
0x180074b47  jbe     short loc_180074B4C
0x180074b49  mov     rdx, [rdx]; lpSubKey
0x180074b4c  mov     [rsp+0B0h+lpdwDisposition], r12; lpdwDisposition
0x180074b51  lea     rax, [rbp+57h+hKey]
0x180074b55  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180074b5a  mov     [rsp+0B0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180074b5f  mov     [rsp+0B0h+samDesired], 4; samDesired
0x180074b67  mov     [rsp+0B0h+dwOptions], r12d; unsigned int
0x180074b6c  xor     r9d, r9d; lpClass
0x180074b6f  xor     r8d, r8d; Reserved
0x180074b72  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180074b79  call    cs:__imp_RegCreateKeyExW
0x180074b80  nop     dword ptr [rax+rax+00h]
0x180074b85  mov     rcx, [rbp+5Fh]; this
0x180074b89  test    eax, eax
0x180074b8b  jnz     loc_180074D3D
0x180074b91  mov     rcx, [rbp+57h+hKey]; hKey
0x180074b95  test    rcx, rcx
0x180074b98  jz      short loc_180074BA6
0x180074b9a  call    cs:__imp_RegCloseKey
0x180074ba1  nop     dword ptr [rax+rax+00h]
0x180074ba6  mov     rax, [rbx+10h]
0x180074baa  cmp     [rax+19h], r12b
0x180074bae  jz      short loc_180074BD1
0x180074bb0  mov     rax, [rbx+8]
0x180074bb4  jmp     short loc_180074BC3
0x180074bb6  cmp     rbx, [rax+10h]
0x180074bba  jnz     short loc_180074BC9
0x180074bbc  mov     rbx, rax
0x180074bbf  mov     rax, [rax+8]
0x180074bc3  cmp     [rax+19h], r12b
0x180074bc7  jz      short loc_180074BB6
0x180074bc9  mov     rbx, rax
0x180074bcc  jmp     loc_180074B31
0x180074bd1  mov     rbx, rax
0x180074bd4  mov     rcx, [rax]
0x180074bd7  cmp     [rcx+19h], r12b
0x180074bdb  jnz     loc_180074B31
0x180074be1  mov     rbx, rcx
0x180074be4  mov     rax, [rcx]
0x180074be7  mov     rcx, rax
0x180074bea  cmp     [rax+19h], r12b
0x180074bee  jz      short loc_180074BE1
0x180074bf0  jmp     loc_180074B31
0x180074bf5  lea     rsi, unk_1800DB840
0x180074bfc  movzx   r14d, word ptr [rsi]
0x180074c00  movzx   ecx, r14w; this
0x180074c04  call    ?IsSupportedWowArchitecture@helium@@YA_NG@Z
0x180074c09  test    al, al
0x180074c0b  jz      loc_180074CF7
0x180074c11  mov     rdi, [r15]
0x180074c14  mov     rbx, [rdi]
0x180074c17  cmp     rbx, rdi
0x180074c1a  jz      loc_180074CF7
0x180074c20  lea     rdx, [rbx+20h]
0x180074c24  movzx   r8d, r14w
0x180074c28  lea     rcx, [rbp+57h+lpSubKey]
0x180074c2c  call    ?TranslateHkcuRelativePathToSupportedWowArchitecture@helium@@YA?AVRegistryPath@WriteVirtualization@@AEBV23@G@Z
0x180074c31  nop
0x180074c32  mov     [rbp+57h+hKey], r12
0x180074c36  lea     rdx, [rbp+57h+lpSubKey]
0x180074c3a  cmp     [rbp+57h+var_30], 7
0x180074c3f  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180074c44  mov     [rsp+0B0h+lpdwDisposition], r12; lpdwDisposition
0x180074c49  lea     rax, [rbp+57h+hKey]
0x180074c4d  mov     [rsp+0B0h+phkResult], rax; phkResult
0x180074c52  mov     [rsp+0B0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180074c57  mov     [rsp+0B0h+samDesired], 4; samDesired
0x180074c5f  mov     [rsp+0B0h+dwOptions], r12d; unsigned int
0x180074c64  xor     r9d, r9d; lpClass
0x180074c67  xor     r8d, r8d; Reserved
0x180074c6a  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180074c71  call    cs:__imp_RegCreateKeyExW
0x180074c78  nop     dword ptr [rax+rax+00h]
0x180074c7d  mov     rcx, [rbp+5Fh]; this
0x180074c81  test    eax, eax
0x180074c83  jnz     loc_180074D52
0x180074c89  mov     rcx, [rbp+57h+hKey]; hKey
0x180074c8d  test    rcx, rcx
0x180074c90  jz      short loc_180074C9F
0x180074c92  call    cs:__imp_RegCloseKey
0x180074c99  nop     dword ptr [rax+rax+00h]
0x180074c9e  nop
0x180074c9f  lea     rcx, [rbp+57h+lpSubKey]; void *
0x180074ca3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x180074ca8  mov     rax, [rbx+10h]
0x180074cac  cmp     [rax+19h], r12b
0x180074cb0  jz      short loc_180074CD3
0x180074cb2  mov     rax, [rbx+8]
0x180074cb6  jmp     short loc_180074CC5
0x180074cb8  cmp     rbx, [rax+10h]
0x180074cbc  jnz     short loc_180074CCB
0x180074cbe  mov     rbx, rax
0x180074cc1  mov     rax, [rax+8]
0x180074cc5  cmp     [rax+19h], r12b
0x180074cc9  jz      short loc_180074CB8
0x180074ccb  mov     rbx, rax
0x180074cce  jmp     loc_180074C17
0x180074cd3  mov     rbx, rax
0x180074cd6  mov     rcx, [rax]
0x180074cd9  cmp     [rcx+19h], r12b
0x180074cdd  jnz     loc_180074C17
0x180074ce3  mov     rbx, rcx
0x180074ce6  mov     rax, [rcx]
0x180074ce9  mov     rcx, rax
0x180074cec  cmp     [rax+19h], r12b
0x180074cf0  jz      short loc_180074CE3
0x180074cf2  jmp     loc_180074C17
0x180074cf7  add     rsi, 2
0x180074cfb  lea     rax, aOnecoreBaseApp_39
0x180074d02  cmp     rsi, rax
0x180074d05  jnz     loc_180074BFC
0x180074d0b  lea     rcx, [rbp+57h+var_58]; this
0x180074d0f  call    ??1ImpersonationReverter@@QEAA@XZ
0x180074d14  mov     rcx, [rbp+57h+var_28]
0x180074d18  xor     rcx, rsp; StackCookie
0x180074d1b  call    __security_check_cookie
0x180074d20  lea     r11, [rsp+0B0h+var_20]
0x180074d28  mov     rbx, [r11+38h]
0x180074d2c  mov     rsi, [r11+40h]
0x180074d30  mov     rsp, r11
0x180074d33  pop     r15
0x180074d35  pop     r14
0x180074d37  pop     r12
0x180074d39  pop     rdi
0x180074d3a  pop     rbp
0x180074d3b  retn
0x180074d3d  mov     r9d, eax; char *
0x180074d40  lea     r8, aOnecoreBaseApp_10
0x180074d47  mov     edx, 88h; void *
0x180074d4c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z
0x180074d52  mov     r9d, eax; char *
0x180074d55  lea     r8, aOnecoreBaseApp_10
0x180074d5c  mov     edx, 94h; void *
0x180074d61  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z
```
