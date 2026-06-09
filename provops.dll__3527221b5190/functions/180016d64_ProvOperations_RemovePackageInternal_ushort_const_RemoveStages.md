# ProvOperations::RemovePackageInternal(ushort const *,RemoveStages &)

- ea: `0x180016d64`
- end: `0x18001700f`
- name: `?RemovePackageInternal@ProvOperations@@AEAAJPEBGAEAW4RemoveStages@@@Z`
- size: `683`
- prototype: `__int64 __fastcall(ProvOperations *this, char *, enum RemoveStages *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180016840`
- `0x180017020`

## callees

- `0x18000a044`
- `0x18000e398`
- `0x18001434c`
- `0x180016d64`
- `0x18001b3a8`
- `0x1800210f0`
- `0x18002bddc`
- `0x18002cbf4`
- `0x18002d090`
- `0x18002d218`
- `0x180033ed0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180016df9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016f00`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016fc9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016df9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016f00`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016fc9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016e8c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180016e8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016f11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016fb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016f11`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016fb2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180016fa2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180016fa2`

## pseudocode

```c
__int64 __fastcall ProvOperations::RemovePackageInternal(ProvOperations *this, char *a2, enum RemoveStages *a3)
{
  char *v3; // rdi
  unsigned __int64 v4; // rsi
  unsigned __int64 v5; // r8
  wil *v6; // rcx
  char IsStateSeparationEnabled; // al
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  unsigned __int64 v10; // r8
  wil *v11; // rcx
  wil *v12; // rcx
  const WCHAR *v13; // rdx
  wil *v14; // rcx
  DWORD dwOptions; // [rsp+20h] [rbp-E8h]
  unsigned int v17; // [rsp+50h] [rbp-B8h]
  HKEY v18; // [rsp+58h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A8h] BYREF
  enum RemoveStages *v20; // [rsp+68h] [rbp-A0h]
  LPCWSTR lpSubKey[2]; // [rsp+70h] [rbp-98h] BYREF
  __int64 v22; // [rsp+80h] [rbp-88h]
  unsigned __int64 v23; // [rsp+88h] [rbp-80h]
  _BYTE v24[96]; // [rsp+90h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v3 = a2;
  v18 = (HKEY)a2;
  v20 = a3;
  v17 = 0;
  v23 = 7;
  v22 = 0;
  LOWORD(lpSubKey[0]) = 0;
  v4 = -1;
  if ( *(_WORD *)a2 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)&a2[2 * v5] );
  }
  else
  {
    v5 = 0;
  }
  try
  {
    std::wstring::assign(lpSubKey, a2, v5);
    PackageEnroller::PackageEnroller((PackageEnroller *)v24);
    if ( v23 >= 8 )
      operator delete((void *)lpSubKey[0]);
    v23 = 7;
    v22 = 0;
    LOWORD(lpSubKey[0]) = 0;
    PackageEnroller::Unenroll((PackageEnroller *)v24);
    PackageEnroller::~PackageEnroller((PackageEnroller *)v24);
  }
  catch ( ... )
  {
    *(_DWORD *)v20 |= 1u;
    v17 = wil::ResultFromCaughtException(v6);
    v4 = -1;
    v3 = (char *)v18;
  }
  try
  {
    hKey = 0;
    IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
    v8 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\PackageInfo";
    if ( !IsStateSeparationEnabled )
      v8 = L"SOFTWARE\\Microsoft\\Provisioning\\PackageInfo";
    v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v8, 0, 0, 0, 0xBu, 0, &hKey, 0);
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x13,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageinfo.cpp",
        (const char *)v9,
        dwOptions);
    v23 = 7;
    v22 = 0;
    LOWORD(lpSubKey[0]) = 0;
    if ( *(_WORD *)v3 )
    {
      v10 = -1;
      do
        ++v10;
      while ( *(_WORD *)&v3[2 * v10] );
    }
    else
    {
      v10 = 0;
    }
    std::wstring::assign(lpSubKey, v3, v10);
    PackageInfo::Remove(&hKey, lpSubKey);
    if ( v23 >= 8 )
      operator delete((void *)lpSubKey[0]);
    v11 = (wil *)hKey;
    if ( hKey )
      RegCloseKey(hKey);
  }
  catch ( ... )
  {
    *(_DWORD *)v20 |= 0x20u;
    v17 = wil::ResultFromCaughtException(v11);
    v4 = -1;
    v3 = (char *)v18;
  }
  try
  {
    hKey = (HKEY)v3;
    ProvOperations::ForEachCachedCrcRegistry__lambda_e2222a85c88cc1015c89bca6873be844___(&hKey);
  }
  catch ( ... )
  {
    *(_DWORD *)v20 |= 2u;
    v17 = wil::ResultFromCaughtException(v12);
    v4 = -1;
    v3 = (char *)v18;
  }
  try
  {
    v23 = 7;
    v22 = 0;
    LOWORD(lpSubKey[0]) = 0;
    if ( *(_WORD *)v3 )
    {
      do
        ++v4;
      while ( *(_WORD *)&v3[2 * v4] );
    }
    else
    {
      v4 = 0;
    }
    std::wstring::assign(lpSubKey, v3, v4);
    ProvResults::GetRootKey(&v18);
    v13 = (const WCHAR *)lpSubKey;
    if ( v23 >= 8 )
      v13 = lpSubKey[0];
    RegDeleteTreeW(v18, v13);
    v14 = (wil *)v18;
    if ( v18 )
      RegCloseKey(v18);
    if ( v23 >= 8 )
      operator delete((void *)lpSubKey[0]);
  }
  catch ( ... )
  {
    *(_DWORD *)v20 |= 0x10u;
    return (unsigned int)wil::ResultFromCaughtException(v14);
  }
  return v17;
}

```

## disassembly

```asm
0x180016d64  mov     r11, rsp
0x180016d67  mov     [r11+8], rbx
0x180016d6b  mov     [r11+20h], rsi
0x180016d6f  push    rdi
0x180016d70  sub     rsp, 100h
0x180016d77  mov     rax, cs:__security_cookie
0x180016d7e  xor     rax, rsp
0x180016d81  mov     [rsp+108h+var_18], rax
0x180016d89  mov     rdi, rdx
0x180016d8c  mov     [rsp+108h+var_B0], rdx
0x180016d91  mov     [rsp+108h+var_A0], r8
0x180016d96  xor     ebx, ebx
0x180016d98  mov     [rsp+108h+var_B8], ebx
0x180016d9c  mov     qword ptr [r11-80h], 7
0x180016da4  mov     [r11-88h], rbx
0x180016dab  mov     word ptr [rsp+108h+lpSubKey], bx
0x180016db0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180016db4  cmp     [rdx], bx
0x180016db7  jnz     short loc_180016DBE
0x180016db9  mov     r8d, ebx
0x180016dbc  jmp     short loc_180016DCB
0x180016dbe  mov     r8, rsi
0x180016dc1  inc     r8
0x180016dc4  cmp     [rdx+r8*2], bx
0x180016dc9  jnz     short loc_180016DC1
0x180016dcb  lea     rcx, [rsp+108h+lpSubKey]; void *
0x180016dd0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180016dd5  nop
0x180016dd6  lea     rdx, [rsp+108h+lpSubKey]
0x180016ddb  lea     rcx, [rsp+108h+var_78]; this
0x180016de3  call    ??0PackageEnroller@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageEnroller::PackageEnroller(std::wstring const &)
0x180016de8  nop
0x180016de9  cmp     [rsp+108h+var_80], 8
0x180016df2  jb      short loc_180016DFF
0x180016df4  mov     rcx, [rsp+108h+lpSubKey]
0x180016df9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180016dff  mov     [rsp+108h+var_80], 7
0x180016e0b  mov     [rsp+108h+var_88], rbx
0x180016e13  mov     word ptr [rsp+108h+lpSubKey], bx
0x180016e18  lea     rcx, [rsp+108h+var_78]; this
0x180016e20  call    ?Unenroll@PackageEnroller@@QEAAXXZ; PackageEnroller::Unenroll(void)
0x180016e25  nop
0x180016e26  lea     rcx, [rsp+108h+var_78]; this
0x180016e2e  call    ??1PackageEnroller@@QEAA@XZ; PackageEnroller::~PackageEnroller(void)
0x180016e33  nop
0x180016e34  jmp     short loc_180016E41
0x180016e36  xor     ebx, ebx
0x180016e38  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180016e3c  mov     rdi, [rsp+108h+var_B0]
0x180016e41  mov     [rsp+108h+hKey], rbx
0x180016e46  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x180016e4b  lea     rcx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Provisioning\\Pack"...
0x180016e52  lea     rdx, aOsdataSoftware_8; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x180016e59  test    al, al
0x180016e5b  cmovz   rdx, rcx; lpSubKey
0x180016e5f  mov     [rsp+108h+lpdwDisposition], rbx; lpdwDisposition
0x180016e64  lea     rax, [rsp+108h+hKey]
0x180016e69  mov     [rsp+108h+phkResult], rax; phkResult
0x180016e6e  mov     [rsp+108h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180016e73  mov     [rsp+108h+samDesired], 0Bh; samDesired
0x180016e7b  mov     [rsp+108h+dwOptions], ebx; unsigned int
0x180016e7f  xor     r9d, r9d; lpClass
0x180016e82  xor     r8d, r8d; Reserved
0x180016e85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016e8c  call    cs:__imp_RegCreateKeyExW
0x180016e92  mov     rcx, [rsp+108h]; this
0x180016e9a  test    eax, eax
0x180016e9c  jnz     loc_180016FF9
0x180016ea2  mov     [rsp+108h+var_80], 7
0x180016eae  mov     [rsp+108h+var_88], rbx
0x180016eb6  mov     word ptr [rsp+108h+lpSubKey], bx
0x180016ebb  cmp     [rdi], bx
0x180016ebe  jnz     short loc_180016EC5
0x180016ec0  mov     r8, rbx
0x180016ec3  jmp     short loc_180016ED2
0x180016ec5  mov     r8, rsi
0x180016ec8  inc     r8
0x180016ecb  cmp     [rdi+r8*2], bx
0x180016ed0  jnz     short loc_180016EC8
0x180016ed2  mov     rdx, rdi; Src
0x180016ed5  lea     rcx, [rsp+108h+lpSubKey]; void *
0x180016eda  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180016edf  nop
0x180016ee0  lea     rdx, [rsp+108h+lpSubKey]
0x180016ee5  lea     rcx, [rsp+108h+hKey]
0x180016eea  call    ?Remove@PackageInfo@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PackageInfo::Remove(std::wstring const &)
0x180016eef  nop
0x180016ef0  cmp     [rsp+108h+var_80], 8
0x180016ef9  jb      short loc_180016F07
0x180016efb  mov     rcx, [rsp+108h+lpSubKey]
0x180016f00  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180016f06  nop
0x180016f07  mov     rcx, [rsp+108h+hKey]; hKey
0x180016f0c  test    rcx, rcx
0x180016f0f  jz      short loc_180016F18
0x180016f11  call    cs:__imp_RegCloseKey
0x180016f17  nop
0x180016f18  jmp     short loc_180016F25
0x180016f1a  xor     ebx, ebx
0x180016f1c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180016f20  mov     rdi, [rsp+108h+var_B0]
0x180016f25  mov     [rsp+108h+hKey], rdi
0x180016f2a  lea     rcx, [rsp+108h+hKey]
0x180016f2f  call    ProvOperations__ForEachCachedCrcRegistry__lambda_e2222a85c88cc1015c89bca6873be844___
0x180016f34  nop
0x180016f35  jmp     short loc_180016F42
0x180016f37  xor     ebx, ebx
0x180016f39  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180016f3d  mov     rdi, [rsp+108h+var_B0]
0x180016f42  mov     [rsp+108h+var_80], 7
0x180016f4e  mov     [rsp+108h+var_88], rbx
0x180016f56  mov     word ptr [rsp+108h+lpSubKey], bx
0x180016f5b  cmp     [rdi], bx
0x180016f5e  jnz     short loc_180016F65
0x180016f60  mov     rsi, rbx
0x180016f63  jmp     short loc_180016F6E
0x180016f65  inc     rsi
0x180016f68  cmp     [rdi+rsi*2], bx
0x180016f6c  jnz     short loc_180016F65
0x180016f6e  mov     r8, rsi
0x180016f71  mov     rdx, rdi; Src
0x180016f74  lea     rcx, [rsp+108h+lpSubKey]; void *
0x180016f79  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180016f7e  nop
0x180016f7f  lea     rcx, [rsp+108h+var_B0]; phkResult
0x180016f84  call    ?GetRootKey@ProvResults@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; ProvResults::GetRootKey(ulong)
0x180016f89  lea     rdx, [rsp+108h+lpSubKey]
0x180016f8e  cmp     [rsp+108h+var_80], 8
0x180016f97  cmovnb  rdx, [rsp+108h+lpSubKey]; lpSubKey
0x180016f9d  mov     rcx, [rsp+108h+var_B0]; hKey
0x180016fa2  call    cs:__imp_RegDeleteTreeW
0x180016fa8  mov     rcx, [rsp+108h+var_B0]; hKey
0x180016fad  test    rcx, rcx
0x180016fb0  jz      short loc_180016FB9
0x180016fb2  call    cs:__imp_RegCloseKey
0x180016fb8  nop
0x180016fb9  cmp     [rsp+108h+var_80], 8
0x180016fc2  jb      short loc_180016FD0
0x180016fc4  mov     rcx, [rsp+108h+lpSubKey]
0x180016fc9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180016fcf  nop
0x180016fd0  mov     eax, [rsp+108h+var_B8]
0x180016fd4  mov     rcx, [rsp+108h+var_18]
0x180016fdc  xor     rcx, rsp; StackCookie
0x180016fdf  call    __security_check_cookie
0x180016fe4  lea     r11, [rsp+108h+var_8]
0x180016fec  mov     rbx, [r11+10h]
0x180016ff0  mov     rsi, [r11+28h]
0x180016ff4  mov     rsp, r11
0x180016ff7  pop     rdi
0x180016ff8  retn
0x180016ff9  mov     r9d, eax; char *
0x180016ffc  lea     r8, aOnecoreuapAdmi_21; "onecoreuap\\admin\\prov\\lib\\packagein"...
0x180017003  mov     edx, 13h; void *
0x180017008  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
