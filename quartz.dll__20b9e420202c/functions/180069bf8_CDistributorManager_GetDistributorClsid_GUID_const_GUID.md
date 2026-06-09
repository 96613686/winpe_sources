# CDistributorManager::GetDistributorClsid(_GUID const &,_GUID *)

- ea: `0x180069bf8`
- end: `0x180069d8d`
- name: `?GetDistributorClsid@CDistributorManager@@IEAAJAEBU_GUID@@PEAU2@@Z`
- size: `405`
- prototype: `int(CDistributorManager *__hidden this, const struct _GUID *, struct _GUID *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800332bc`

## callees

- `0x180026920`
- `0x180038498`
- `0x1800384a4`
- `0x1800388a0`
- `0x180069bf8`

## import_xrefs

- `ADVAPI32!RegQueryValueW` at `0x180069cad`
- `ADVAPI32!RegQueryValueW` at `0x180069d18`
- `ADVAPI32!RegQueryValueW` at `0x180069cad`
- `ADVAPI32!RegQueryValueW` at `0x180069d18`
- `ADVAPI32!RegOpenKeyExW` at `0x180069c86`
- `ADVAPI32!RegOpenKeyExW` at `0x180069c86`
- `ADVAPI32!RegCloseKey` at `0x180069cf9`
- `ADVAPI32!RegCloseKey` at `0x180069d2b`
- `ADVAPI32!RegCloseKey` at `0x180069cf9`
- `ADVAPI32!RegCloseKey` at `0x180069d2b`
- `ole32!CLSIDFromString` at `0x180069d6e`
- `ole32!CLSIDFromString` at `0x180069d6e`
- `ole32!StringFromGUID2` at `0x180069c31`
- `ole32!StringFromGUID2` at `0x180069c31`

## pseudocode

```c
__int64 __fastcall CDistributorManager::GetDistributorClsid(
        CDistributorManager *this,
        const struct _GUID *a2,
        struct _GUID *a3)
{
  unsigned int v4; // ebx
  WCHAR *v5; // rax
  WCHAR *v6; // rdi
  __int64 result; // rax
  LSTATUS v8; // ebx
  HRESULT v9; // ebx
  LONG cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  OLECHAR sz[48]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[128]; // [rsp+A0h] [rbp-60h] BYREF

  if ( !StringFromGUID2(a2, sz, 48) )
    return 2147500034LL;
  StringCbPrintfW(SubKey, 0x100u, L"Interface\\%ls\\Distributor", sz);
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey) )
    return 2147500034LL;
  cbData = 0;
  if ( RegQueryValueW(hKey, 0, 0, &cbData) )
  {
    v4 = -2147467262;
LABEL_7:
    RegCloseKey(hKey);
    return v4;
  }
  v5 = (WCHAR *)operator new[](saturated_mul((unsigned __int64)cbData >> 1, 2u));
  v6 = v5;
  if ( !v5 )
  {
    v4 = -2147024882;
    goto LABEL_7;
  }
  v8 = RegQueryValueW(hKey, 0, v5, &cbData);
  RegCloseKey(hKey);
  if ( v8 )
  {
    operator delete(v6);
    return 2147500034LL;
  }
  v9 = CLSIDFromString(v6, a3);
  operator delete(v6);
  result = 0;
  if ( v9 < 0 )
    return (unsigned int)v9;
  return result;
}

```

## disassembly

```asm
0x180069bf8  mov     [rsp-8+arg_0], rbx
0x180069bfd  push    rbp
0x180069bfe  push    rsi
0x180069bff  push    rdi
0x180069c00  lea     rbp, [rsp-0B0h]
0x180069c08  sub     rsp, 1B0h
0x180069c0f  mov     rax, cs:__security_cookie
0x180069c16  xor     rax, rsp
0x180069c19  mov     [rbp+0C0h+var_20], rax
0x180069c20  mov     rsi, r8
0x180069c23  mov     rcx, rdx; rguid
0x180069c26  mov     r8d, 30h ; '0'; cchMax
0x180069c2c  lea     rdx, [rsp+1C0h+sz]; lpsz
0x180069c31  call    cs:__imp_StringFromGUID2
0x180069c38  nop     dword ptr [rax+rax+00h]
0x180069c3d  test    eax, eax
0x180069c3f  jz      loc_180069D43
0x180069c45  lea     r9, [rsp+1C0h+sz]
0x180069c4a  mov     edx, 100h; unsigned __int64
0x180069c4f  lea     r8, aInterfaceLsDis; "Interface\\%ls\\Distributor"
0x180069c56  lea     rcx, [rbp+0C0h+SubKey]; unsigned __int16 *
0x180069c5a  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180069c5f  lea     rax, [rsp+1C0h+hKey]
0x180069c64  mov     [rsp+1C0h+hKey], 0
0x180069c6d  mov     r9d, 20019h; samDesired
0x180069c73  mov     [rsp+1C0h+phkResult], rax; phkResult
0x180069c78  xor     r8d, r8d; ulOptions
0x180069c7b  lea     rdx, [rbp+0C0h+SubKey]; lpSubKey
0x180069c7f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180069c86  call    cs:__imp_RegOpenKeyExW
0x180069c8d  nop     dword ptr [rax+rax+00h]
0x180069c92  test    eax, eax
0x180069c94  jnz     loc_180069D43
0x180069c9a  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180069c9f  lea     r9, [rsp+1C0h+cbData]; lpcbData
0x180069ca4  xor     r8d, r8d; lpData
0x180069ca7  mov     [rsp+1C0h+cbData], eax
0x180069cab  xor     edx, edx; lpSubKey
0x180069cad  call    cs:__imp_RegQueryValueW
0x180069cb4  nop     dword ptr [rax+rax+00h]
0x180069cb9  test    eax, eax
0x180069cbb  jz      short loc_180069CC4
0x180069cbd  mov     ebx, 80004002h
0x180069cc2  jmp     short loc_180069CF4
0x180069cc4  movsxd  rcx, [rsp+1C0h+cbData]
0x180069cc9  mov     eax, 2
0x180069cce  shr     rcx, 1
0x180069cd1  mul     rcx
0x180069cd4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180069cdb  cmovb   rax, rcx
0x180069cdf  mov     rcx, rax; unsigned __int64
0x180069ce2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180069ce7  mov     rdi, rax
0x180069cea  test    rax, rax
0x180069ced  jnz     short loc_180069D09
0x180069cef  mov     ebx, 8007000Eh
0x180069cf4  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180069cf9  call    cs:__imp_RegCloseKey
0x180069d00  nop     dword ptr [rax+rax+00h]
0x180069d05  mov     eax, ebx
0x180069d07  jmp     short loc_180069D48
0x180069d09  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180069d0e  lea     r9, [rsp+1C0h+cbData]; lpcbData
0x180069d13  mov     r8, rdi; lpData
0x180069d16  xor     edx, edx; lpSubKey
0x180069d18  call    cs:__imp_RegQueryValueW
0x180069d1f  nop     dword ptr [rax+rax+00h]
0x180069d24  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180069d29  mov     ebx, eax
0x180069d2b  call    cs:__imp_RegCloseKey
0x180069d32  nop     dword ptr [rax+rax+00h]
0x180069d37  mov     rcx, rdi; lpsz
0x180069d3a  test    ebx, ebx
0x180069d3c  jz      short loc_180069D6B
0x180069d3e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180069d43  mov     eax, 80004002h
0x180069d48  mov     rcx, [rbp+0C0h+var_20]
0x180069d4f  xor     rcx, rsp; StackCookie
0x180069d52  call    __security_check_cookie
0x180069d57  mov     rbx, [rsp+1C0h+arg_0]
0x180069d5f  add     rsp, 1B0h
0x180069d66  pop     rdi
0x180069d67  pop     rsi
0x180069d68  pop     rbp
0x180069d69  retn
0x180069d6b  mov     rdx, rsi; pclsid
0x180069d6e  call    cs:__imp_CLSIDFromString
0x180069d75  nop     dword ptr [rax+rax+00h]
0x180069d7a  mov     rcx, rdi; Block
0x180069d7d  mov     ebx, eax
0x180069d7f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180069d84  xor     eax, eax
0x180069d86  test    ebx, ebx
0x180069d88  cmovs   eax, ebx
0x180069d8b  jmp     short loc_180069D48
```
