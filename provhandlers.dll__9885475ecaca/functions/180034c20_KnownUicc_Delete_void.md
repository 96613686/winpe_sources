# KnownUicc::Delete(void)

- ea: `0x180034c20`
- end: `0x180034f26`
- name: `?Delete@KnownUicc@@QEBAXXZ`
- size: `774`
- prototype: `void __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800308d0`

## callees

- `0x180002a98`
- `0x180007f48`
- `0x180012390`
- `0x180012d80`
- `0x18002b17c`
- `0x180032624`
- `0x180034c20`
- `0x180035c34`
- `0x18003b9a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034e93`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034e93`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180034ccf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180034ddd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180034e62`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180034ccf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180034ddd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180034e62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034c73`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034c73`
- `ntdll!RtlGetPersistedStateLocation` at `0x180034d29`
- `ntdll!RtlGetPersistedStateLocation` at `0x180034d29`

## string_xrefs

- `0x180034e1b`: `IMSISpecific\`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall KnownUicc::Delete(LPCWSTR lpSubKey)
{
  LPCWSTR v1; // r15
  LPCWSTR v2; // rsi
  unsigned int v3; // eax
  _QWORD *v4; // r14
  const WCHAR *v5; // rdx
  const char *v6; // r9
  const WCHAR *v7; // rdx
  unsigned int v8; // eax
  int PersistedStateLocation; // eax
  const char *v10; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-498h]
  HKEY hKey; // [rsp+48h] [rbp-470h] BYREF
  LPCWSTR v13; // [rsp+50h] [rbp-468h]
  int v14[132]; // [rsp+60h] [rbp-458h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+0h]

  v1 = lpSubKey;
  v13 = lpSubKey;
  v2 = lpSubKey;
  hKey = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, gc_wszRegUicc, 0, 0x10009u, &hKey);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x10B,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
      (const char *)v3,
      phkResult);
  v4 = v1 + 12;
  if ( *((_QWORD *)v1 + 3) < 8u )
    v5 = v1;
  else
    v5 = *(const WCHAR **)v1;
  try
  {
    UndoForUicc(hKey, v5);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
      v6);
    v4 = v1 + 12;
    v1 = v13;
    v2 = v13;
  }
  try
  {
    if ( *v4 < 8u )
      v7 = v2;
    else
      v7 = *(const WCHAR **)v1;
    v8 = RegDeleteTreeW(hKey, v7);
    if ( v8 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x115,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        (const char *)v8,
        phkResult);
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"CellularMVSettings",
                               0,
                               L"Software\\Microsoft\\Cellular\\MVSettings\\",
                               0);
    if ( PersistedStateLocation >= 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x125,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
        (const char *)0x8000FFFFLL,
        (int)v14);
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x123,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
      (const char *)(unsigned int)PersistedStateLocation,
      (int)v14);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\knownuicc.cpp",
      v10);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x180034c20  push    rbx
0x180034c22  push    rsi
0x180034c23  push    r14
0x180034c25  push    r15
0x180034c27  sub     rsp, 498h
0x180034c2e  mov     rax, cs:__security_cookie
0x180034c35  xor     rax, rsp
0x180034c38  mov     [rsp+4B8h+var_38], rax
0x180034c40  mov     r15, rcx
0x180034c43  mov     [rsp+4B8h+var_468], rcx
0x180034c48  mov     rsi, rcx
0x180034c4b  xor     ebx, ebx
0x180034c4d  mov     [rsp+4B8h+hKey], rbx
0x180034c52  lea     rax, [rsp+4B8h+hKey]
0x180034c57  mov     [rsp+4B8h+phkResult], rax; unsigned int
0x180034c5c  mov     r9d, 10009h; samDesired
0x180034c62  xor     r8d, r8d; ulOptions
0x180034c65  mov     rdx, cs:?gc_wszRegUicc@@3PEBGEB; lpSubKey
0x180034c6c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034c73  call    cs:__imp_RegOpenKeyExW
0x180034c79  mov     rcx, [rsp+4B8h]; this
0x180034c81  test    eax, eax
0x180034c83  jnz     loc_180034EB7
0x180034c89  lea     r14, [r15+18h]
0x180034c8d  mov     [rsp+4B8h+var_478], r14
0x180034c92  cmp     qword ptr [r14], 8
0x180034c96  jb      short loc_180034C9D
0x180034c98  mov     rdx, [r15]
0x180034c9b  jmp     short loc_180034CA0
0x180034c9d  mov     rdx, r15; lpSubKey
0x180034ca0  mov     rcx, [rsp+4B8h+hKey]; hKey
0x180034ca5  call    UndoForUicc
0x180034caa  nop
0x180034cab  jmp     short loc_180034CBC
0x180034cad  xor     ebx, ebx
0x180034caf  mov     r14, [rsp+4B8h+var_478]
0x180034cb4  mov     r15, [rsp+4B8h+var_468]
0x180034cb9  mov     rsi, r15
0x180034cbc  cmp     qword ptr [r14], 8
0x180034cc0  jb      short loc_180034CC7
0x180034cc2  mov     rdx, [r15]
0x180034cc5  jmp     short loc_180034CCA
0x180034cc7  mov     rdx, rsi; lpSubKey
0x180034cca  mov     rcx, [rsp+4B8h+hKey]; hKey
0x180034ccf  call    cs:__imp_RegDeleteTreeW
0x180034cd5  mov     rcx, [rsp+4B8h]; this
0x180034cdd  test    eax, eax
0x180034cdf  jz      short loc_180034CF6
0x180034ce1  mov     r9d, eax; char *
0x180034ce4  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180034ceb  mov     edx, 115h; void *
0x180034cf0  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180034cf5  nop
0x180034cf6  mov     dword ptr [rsp+4B8h+var_478], ebx
0x180034cfa  lea     rax, [rsp+4B8h+var_478]
0x180034cff  mov     [rsp+4B8h+var_488], rax
0x180034d04  mov     dword ptr [rsp+4B8h+var_490], 208h
0x180034d0c  lea     rax, [rsp+4B8h+var_458]
0x180034d11  mov     [rsp+4B8h+phkResult], rax; int
0x180034d16  xor     r9d, r9d
0x180034d19  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Cellular\\MVSettin"...
0x180034d20  xor     edx, edx
0x180034d22  lea     rcx, aCellularmvsett; "CellularMVSettings"
0x180034d29  call    cs:__imp_RtlGetPersistedStateLocation
0x180034d2f  mov     rcx, [rsp+4B8h]; this
0x180034d37  test    eax, eax
0x180034d39  js      loc_180034ECC
0x180034d3f  mov     edx, dword ptr [rsp+4B8h+var_478]
0x180034d43  cmp     edx, 2
0x180034d46  setb    al
0x180034d49  mov     rcx, [rsp+4B8h]; this
0x180034d51  test    al, al
0x180034d53  jnz     loc_180034EE0
0x180034d59  lea     eax, [rdx-1]
0x180034d5c  shr     eax, 1
0x180034d5e  mov     edx, eax
0x180034d60  mov     dword ptr [rsp+4B8h+var_478], eax
0x180034d64  dec     eax
0x180034d66  cmp     word ptr [rsp+rax*2+4B8h+var_458], 5Ch ; '\'
0x180034d6c  jnz     short loc_180034D89
0x180034d6e  lea     eax, [rdx-1]
0x180034d71  mov     dword ptr [rsp+4B8h+var_478], eax
0x180034d75  add     rax, rax
0x180034d78  cmp     rax, 208h
0x180034d7e  jnb     loc_180034EF7
0x180034d84  mov     word ptr [rsp+rax+4B8h+var_458], bx
0x180034d89  cmp     qword ptr [r14], 8
0x180034d8d  jb      short loc_180034D94
0x180034d8f  mov     rax, [r15]
0x180034d92  jmp     short loc_180034D97
0x180034d94  mov     rax, rsi
0x180034d97  mov     [rsp+4B8h+phkResult], rax; int
0x180034d9c  lea     r9, [rsp+4B8h+var_458]
0x180034da1  lea     r8, aSIccidspecific; "%s\\ICCIDSpecific\\%s"
0x180034da8  mov     r14d, 104h
0x180034dae  mov     edx, r14d; unsigned __int64
0x180034db1  lea     rcx, [rsp+4B8h+SubKey]; unsigned __int16 *
0x180034db9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034dbe  mov     rcx, [rsp+4B8h]; this
0x180034dc6  test    eax, eax
0x180034dc8  js      loc_180034EFD
0x180034dce  lea     rdx, [rsp+4B8h+SubKey]; lpSubKey
0x180034dd6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034ddd  call    cs:__imp_RegDeleteTreeW
0x180034de3  mov     rcx, [rsp+4B8h]; this
0x180034deb  test    eax, eax
0x180034ded  jz      short loc_180034E03
0x180034def  mov     r9d, eax; char *
0x180034df2  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180034df9  mov     edx, 12Eh; void *
0x180034dfe  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180034e03  mov     rax, [rsi+20h]
0x180034e07  test    rax, rax
0x180034e0a  jz      short loc_180034E89
0x180034e0c  cmp     qword ptr [rax+18h], 8
0x180034e11  jb      short loc_180034E16
0x180034e13  mov     rax, [rax]
0x180034e16  mov     [rsp+4B8h+var_490], rax
0x180034e1b  lea     rax, aImsispecific; "IMSISpecific\\"
0x180034e22  mov     [rsp+4B8h+phkResult], rax; int
0x180034e27  lea     r9, [rsp+4B8h+var_458]
0x180034e2c  lea     r8, aSSS; "%s\\%s%s"
0x180034e33  mov     rdx, r14; unsigned __int64
0x180034e36  lea     rcx, [rsp+4B8h+SubKey]; unsigned __int16 *
0x180034e3e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180034e43  mov     rcx, [rsp+4B8h]; this
0x180034e4b  test    eax, eax
0x180034e4d  js      loc_180034F10
0x180034e53  lea     rdx, [rsp+4B8h+SubKey]; lpSubKey
0x180034e5b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034e62  call    cs:__imp_RegDeleteTreeW
0x180034e68  mov     rcx, [rsp+4B8h]; this
0x180034e70  test    eax, eax
0x180034e72  jz      short loc_180034E89
0x180034e74  mov     r9d, eax; char *
0x180034e77  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180034e7e  mov     edx, 132h; void *
0x180034e83  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180034e88  nop
0x180034e89  mov     rcx, [rsp+4B8h+hKey]; hKey
0x180034e8e  test    rcx, rcx
0x180034e91  jz      short loc_180034E99
0x180034e93  call    cs:__imp_RegCloseKey
0x180034e99  mov     rcx, [rsp+4B8h+var_38]
0x180034ea1  xor     rcx, rsp; StackCookie
0x180034ea4  call    __security_check_cookie
0x180034ea9  add     rsp, 498h
0x180034eb0  pop     r15
0x180034eb2  pop     r14
0x180034eb4  pop     rsi
0x180034eb5  pop     rbx
0x180034eb6  retn
0x180034eb7  mov     r9d, eax; char *
0x180034eba  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180034ec1  mov     edx, 10Bh; void *
0x180034ec6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180034ecc  mov     r9d, eax; char *
0x180034ecf  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180034ed6  mov     edx, 123h; void *
0x180034edb  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180034ee0  mov     r9d, 8000FFFFh; char *
0x180034ee6  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180034eed  mov     edx, 125h; void *
0x180034ef2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034ef7  call    __report_rangecheckfailure
0x180034efd  mov     r9d, eax; char *
0x180034f00  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180034f07  lea     edx, [r14+29h]; void *
0x180034f0b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180034f10  mov     r9d, eax; char *
0x180034f13  lea     r8, aOnecoreuapAdmi_15; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180034f1a  mov     edx, 131h; void *
0x180034f1f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
