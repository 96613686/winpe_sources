# helium::CreatePlaceholderUserHiveKeysForExitNodes(void *,WriteVirtualization::NormalizedExclusionPathList<WriteVirtualization::RegistryPath> const &)

- ea: `0x180076258`
- end: `0x1800764d3`
- name: `?CreatePlaceholderUserHiveKeysForExitNodes@helium@@YAXPEAXAEBV?$NormalizedExclusionPathList@VRegistryPath@WriteVirtualization@@@WriteVirtualization@@@Z`
- size: `635`
- prototype: `void __fastcall(__int64, __int64 ***)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config`

## callers

- `0x18007161c`

## callees

- `0x180004f70`
- `0x180013510`
- `0x180014e74`
- `0x180076258`
- `0x180077d44`
- `0x180077ec4`
- `0x180097fb8`
- `0x18009815c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076306`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800763fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180076306`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800763fe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800762e5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800763dd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800762e5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800763dd`

## string_xrefs

- `0x180076467`: `onecore\base\appmodel\execmodel\desktopappx\lib\hivepath.cpp`

## pseudocode

```c
void __fastcall helium::CreatePlaceholderUserHiveKeysForExitNodes(__int64 a1, __int64 ***a2)
{
  unsigned __int16 v3; // dx
  __int64 **v4; // rdi
  __int64 *v5; // rbx
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  __int64 **v8; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  const char *v11; // rsi
  unsigned __int16 v12; // r14
  __int64 *v13; // rdi
  __int64 *v14; // rbx
  const WCHAR *v15; // rdx
  unsigned int v16; // eax
  __int64 **v17; // rcx
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
  v11 = (const char *)&qword_1800DCC28;
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
0x180076258  mov     [rsp-8+arg_8], rbx
0x18007625d  mov     [rsp-8+arg_10], rsi
0x180076262  push    rbp
0x180076263  push    rdi
0x180076264  push    r12
0x180076266  push    r14
0x180076268  push    r15
0x18007626a  lea     rbp, [rsp-37h]
0x18007626f  sub     rsp, 90h
0x180076276  mov     rax, cs:__security_cookie
0x18007627d  xor     rax, rsp
0x180076280  mov     [rbp+57h+var_28], rax
0x180076284  mov     r15, rdx
0x180076287  mov     rdx, rcx
0x18007628a  lea     rcx, [rbp+57h+var_58]
0x18007628e  call    ?Impersonate@LoggedonUserImpersonation@@SA?AU1@PEAX@Z; LoggedonUserImpersonation::Impersonate(void *)
0x180076293  nop
0x180076294  mov     rdi, [r15]
0x180076297  mov     rbx, [rdi]
0x18007629a  xor     r12d, r12d
0x18007629d  cmp     rbx, rdi
0x1800762a0  jz      loc_180076361
0x1800762a6  lea     rdx, [rbx+20h]
0x1800762aa  mov     [rbp+57h+hKey], r12
0x1800762ae  cmp     qword ptr [rdx+18h], 7
0x1800762b3  jbe     short loc_1800762B8
0x1800762b5  mov     rdx, [rdx]; lpSubKey
0x1800762b8  mov     [rsp+0B0h+lpdwDisposition], r12; lpdwDisposition
0x1800762bd  lea     rax, [rbp+57h+hKey]
0x1800762c1  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800762c6  mov     [rsp+0B0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800762cb  mov     [rsp+0B0h+samDesired], 4; samDesired
0x1800762d3  mov     [rsp+0B0h+dwOptions], r12d; unsigned int
0x1800762d8  xor     r9d, r9d; lpClass
0x1800762db  xor     r8d, r8d; Reserved
0x1800762de  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800762e5  call    cs:__imp_RegCreateKeyExW
0x1800762ec  nop     dword ptr [rax+rax+00h]
0x1800762f1  mov     rcx, [rbp+5Fh]; this
0x1800762f5  test    eax, eax
0x1800762f7  jnz     loc_1800764A9
0x1800762fd  mov     rcx, [rbp+57h+hKey]; hKey
0x180076301  test    rcx, rcx
0x180076304  jz      short loc_180076312
0x180076306  call    cs:__imp_RegCloseKey
0x18007630d  nop     dword ptr [rax+rax+00h]
0x180076312  mov     rcx, [rbx+10h]
0x180076316  cmp     [rcx+19h], r12b
0x18007631a  jz      short loc_18007633D
0x18007631c  mov     rax, [rbx+8]
0x180076320  jmp     short loc_18007632F
0x180076322  cmp     rbx, [rax+10h]
0x180076326  jnz     short loc_180076335
0x180076328  mov     rbx, rax
0x18007632b  mov     rax, [rax+8]
0x18007632f  cmp     [rax+19h], r12b
0x180076333  jz      short loc_180076322
0x180076335  mov     rbx, rax
0x180076338  jmp     loc_18007629D
0x18007633d  mov     rbx, rcx
0x180076340  mov     rcx, [rcx]
0x180076343  cmp     [rcx+19h], r12b
0x180076347  jnz     loc_18007629D
0x18007634d  mov     rbx, rcx
0x180076350  mov     rax, [rcx]
0x180076353  mov     rcx, rax
0x180076356  cmp     [rax+19h], r12b
0x18007635a  jz      short loc_18007634D
0x18007635c  jmp     loc_18007629D
0x180076361  lea     rsi, qword_1800DCC28
0x180076368  movzx   r14d, word ptr [rsi]
0x18007636c  movzx   ecx, r14w; this
0x180076370  call    ?IsSupportedWowArchitecture@helium@@YA_NG@Z; helium::IsSupportedWowArchitecture(ushort)
0x180076375  test    al, al
0x180076377  jz      loc_180076463
0x18007637d  mov     rdi, [r15]
0x180076380  mov     rbx, [rdi]
0x180076383  cmp     rbx, rdi
0x180076386  jz      loc_180076463
0x18007638c  lea     rdx, [rbx+20h]
0x180076390  movzx   r8d, r14w
0x180076394  lea     rcx, [rbp+57h+lpSubKey]
0x180076398  call    ?TranslateHkcuRelativePathToSupportedWowArchitecture@helium@@YA?AVRegistryPath@WriteVirtualization@@AEBV23@G@Z; helium::TranslateHkcuRelativePathToSupportedWowArchitecture(WriteVirtualization::RegistryPath const &,ushort)
0x18007639d  nop
0x18007639e  mov     [rbp+57h+hKey], r12
0x1800763a2  lea     rdx, [rbp+57h+lpSubKey]
0x1800763a6  cmp     [rbp+57h+var_30], 7
0x1800763ab  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x1800763b0  mov     [rsp+0B0h+lpdwDisposition], r12; lpdwDisposition
0x1800763b5  lea     rax, [rbp+57h+hKey]
0x1800763b9  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800763be  mov     [rsp+0B0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800763c3  mov     [rsp+0B0h+samDesired], 4; samDesired
0x1800763cb  mov     [rsp+0B0h+dwOptions], r12d; unsigned int
0x1800763d0  xor     r9d, r9d; lpClass
0x1800763d3  xor     r8d, r8d; Reserved
0x1800763d6  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800763dd  call    cs:__imp_RegCreateKeyExW
0x1800763e4  nop     dword ptr [rax+rax+00h]
0x1800763e9  mov     rcx, [rbp+5Fh]; this
0x1800763ed  test    eax, eax
0x1800763ef  jnz     loc_1800764BE
0x1800763f5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800763f9  test    rcx, rcx
0x1800763fc  jz      short loc_18007640B
0x1800763fe  call    cs:__imp_RegCloseKey
0x180076405  nop     dword ptr [rax+rax+00h]
0x18007640a  nop
0x18007640b  lea     rcx, [rbp+57h+lpSubKey]; void *
0x18007640f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180076414  mov     rcx, [rbx+10h]
0x180076418  cmp     [rcx+19h], r12b
0x18007641c  jz      short loc_18007643F
0x18007641e  mov     rax, [rbx+8]
0x180076422  jmp     short loc_180076431
0x180076424  cmp     rbx, [rax+10h]
0x180076428  jnz     short loc_180076437
0x18007642a  mov     rbx, rax
0x18007642d  mov     rax, [rax+8]
0x180076431  cmp     [rax+19h], r12b
0x180076435  jz      short loc_180076424
0x180076437  mov     rbx, rax
0x18007643a  jmp     loc_180076383
0x18007643f  mov     rbx, rcx
0x180076442  mov     rcx, [rcx]
0x180076445  cmp     [rcx+19h], r12b
0x180076449  jnz     loc_180076383
0x18007644f  mov     rbx, rcx
0x180076452  mov     rax, [rcx]
0x180076455  mov     rcx, rax
0x180076458  cmp     [rax+19h], r12b
0x18007645c  jz      short loc_18007644F
0x18007645e  jmp     loc_180076383
0x180076463  add     rsi, 2
0x180076467  lea     rax, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007646e  cmp     rsi, rax
0x180076471  jnz     loc_180076368
0x180076477  lea     rcx, [rbp+57h+var_58]; this
0x18007647b  call    ??1ImpersonationReverter@@QEAA@XZ; ImpersonationReverter::~ImpersonationReverter(void)
0x180076480  mov     rcx, [rbp+57h+var_28]
0x180076484  xor     rcx, rsp; StackCookie
0x180076487  call    __security_check_cookie
0x18007648c  lea     r11, [rsp+0B0h+var_20]
0x180076494  mov     rbx, [r11+38h]
0x180076498  mov     rsi, [r11+40h]
0x18007649c  mov     rsp, r11
0x18007649f  pop     r15
0x1800764a1  pop     r14
0x1800764a3  pop     r12
0x1800764a5  pop     rdi
0x1800764a6  pop     rbp
0x1800764a7  retn
0x1800764a9  mov     r9d, eax; char *
0x1800764ac  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800764b3  mov     edx, 88h; void *
0x1800764b8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800764be  mov     r9d, eax; char *
0x1800764c1  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800764c8  mov     edx, 94h; void *
0x1800764cd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
