# RegistryConfig::AddCommandSetting(ushort const *,ushort const *,ushort const *,ushort const *,ulong,uchar const *,unsigned __int64)

- ea: `0x18000aa94`
- end: `0x18000ac51`
- name: `?AddCommandSetting@RegistryConfig@@QEAAXPEBG000KPEBE_K@Z`
- size: `445`
- prototype: `void __fastcall(HKEY *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, LPCWSTR lpValueName, DWORD dwType, BYTE *lpData, unsigned __int64 cbData)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008670`

## callees

- `0x180007800`
- `0x18000899c`
- `0x18000aa94`
- `0x18000ac58`
- `0x18000c600`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000abcb`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000abcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab19`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ab2c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abf0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ab24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000abf0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ab5d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ab5d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000abb2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000abb2`

## string_xrefs

- `0x18000ac15`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000ac2a`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000ac3c`: `admin\prov\launch\lib\registryconfig.cpp`

## pseudocode

```c
void __fastcall RegistryConfig::AddCommandSetting(
        HKEY *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        LPCWSTR lpValueName,
        DWORD dwType,
        BYTE *lpData,
        unsigned __int64 cbData)
{
  const WCHAR *v9; // rdx
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-59h]
  unsigned int phkResulta; // [rsp+20h] [rbp-59h]
  HKEY hKey; // [rsp+50h] [rbp-29h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+58h] [rbp-21h] BYREF
  unsigned __int64 v16; // [rsp+70h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+3Fh]

  RegistryConfig::AppendStrings(this, lpSubKey, 7);
  hKey = 0;
  v9 = (const WCHAR *)lpSubKey;
  if ( v16 >= 8 )
    v9 = lpSubKey[0];
  v10 = RegOpenKeyExW(*this, v9, 0, 0xF003Fu, &hKey);
  if ( v10 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x83,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v10,
      phkResult);
  if ( cbData > 0xFFFFFFFF )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      cbData > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
      phkResult);
  v11 = RegSetValueExW(hKey, lpValueName, 0, dwType, lpData, cbData);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x8B,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v11,
      phkResulta);
  if ( v16 >= 8 )
    operator delete((void *)lpSubKey[0]);
  v16 = 7;
  lpSubKey[2] = 0;
  LOWORD(lpSubKey[0]) = 0;
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18000aa94  push    rbp
0x18000aa96  push    rbx
0x18000aa97  push    rsi
0x18000aa98  push    rdi
0x18000aa99  push    r14
0x18000aa9b  push    r15
0x18000aa9d  lea     rbp, [rsp-0Fh]
0x18000aaa2  sub     rsp, 88h
0x18000aaa9  mov     rax, cs:__security_cookie
0x18000aab0  xor     rax, rsp
0x18000aab3  mov     [rbp+37h+var_38], rax
0x18000aab7  mov     rax, r9
0x18000aaba  mov     rsi, rcx
0x18000aabd  mov     r14, [rbp+37h+lpValueName]
0x18000aac1  mov     r15, [rbp+37h+lpData]
0x18000aac5  mov     [rbp+37h+hKey], 0
0x18000aacd  lea     r9, [rcx+8]
0x18000aad1  cmp     qword ptr [r9+18h], 8
0x18000aad6  jb      short loc_18000AADB
0x18000aad8  mov     r9, [r9]
0x18000aadb  mov     [rsp+0B0h+var_68], rax
0x18000aae0  lea     rax, asc_180010164; "\\"
0x18000aae7  mov     [rsp+0B0h+var_70], rax
0x18000aaec  mov     [rsp+0B0h+var_78], r8
0x18000aaf1  mov     [rsp+0B0h+var_80], rax
0x18000aaf6  mov     qword ptr [rsp+0B0h+cbData], rdx
0x18000aafb  mov     [rsp+0B0h+phkResult], rax
0x18000ab00  mov     r8d, 7
0x18000ab06  lea     rdx, [rbp+37h+lpSubKey]
0x18000ab0a  call    ?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ; RegistryConfig::AppendStrings(int,...)
0x18000ab0f  nop
0x18000ab10  mov     rdi, [rbp+37h+hKey]
0x18000ab14  test    rdi, rdi
0x18000ab17  jz      short loc_18000AB32
0x18000ab19  call    cs:__imp_GetLastError
0x18000ab1f  mov     ebx, eax
0x18000ab21  mov     rcx, rdi; hKey
0x18000ab24  call    cs:__imp_RegCloseKey
0x18000ab2a  mov     ecx, ebx; dwErrCode
0x18000ab2c  call    cs:__imp_SetLastError
0x18000ab32  mov     [rbp+37h+hKey], 0
0x18000ab3a  lea     rdx, [rbp+37h+lpSubKey]
0x18000ab3e  cmp     [rbp+37h+var_40], 8
0x18000ab43  cmovnb  rdx, [rbp+37h+lpSubKey]; lpSubKey
0x18000ab48  lea     rax, [rbp+37h+hKey]
0x18000ab4c  mov     [rsp+0B0h+phkResult], rax; int
0x18000ab51  mov     r9d, 0F003Fh; samDesired
0x18000ab57  xor     r8d, r8d; ulOptions
0x18000ab5a  mov     rcx, [rsi]; hKey
0x18000ab5d  call    cs:__imp_RegOpenKeyExW
0x18000ab63  mov     rcx, [rbp+3Fh]; this
0x18000ab67  test    eax, eax
0x18000ab69  jnz     loc_18000AC27
0x18000ab6f  mov     edx, 0FFFFFFFFh
0x18000ab74  mov     rax, qword ptr [rbp+37h+arg_38]
0x18000ab78  cmp     rax, rdx
0x18000ab7b  mov     ecx, eax
0x18000ab7d  jbe     short loc_18000AB81
0x18000ab7f  mov     ecx, edx
0x18000ab81  cmp     rdx, rax
0x18000ab84  sbb     r9d, r9d
0x18000ab87  and     r9d, 80070216h; char *
0x18000ab8e  mov     r10, [rbp+3Fh]
0x18000ab92  cmp     rax, rdx
0x18000ab95  ja      loc_18000AC3C
0x18000ab9b  mov     [rsp+0B0h+cbData], ecx; cbData
0x18000ab9f  mov     [rsp+0B0h+phkResult], r15; unsigned int
0x18000aba4  mov     r9d, [rbp+37h+dwType]; dwType
0x18000aba8  xor     r8d, r8d; Reserved
0x18000abab  mov     rdx, r14; lpValueName
0x18000abae  mov     rcx, [rbp+37h+hKey]; hKey
0x18000abb2  call    cs:__imp_RegSetValueExW
0x18000abb8  mov     rcx, [rbp+3Fh]; this
0x18000abbc  test    eax, eax
0x18000abbe  jnz     short loc_18000AC12
0x18000abc0  cmp     [rbp+37h+var_40], 8
0x18000abc5  jb      short loc_18000ABD1
0x18000abc7  mov     rcx, [rbp+37h+lpSubKey]
0x18000abcb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000abd1  mov     [rbp+37h+var_40], 7
0x18000abd9  mov     [rbp+37h+var_48], 0
0x18000abe1  xor     eax, eax
0x18000abe3  mov     word ptr [rbp+37h+lpSubKey], ax
0x18000abe7  mov     rcx, [rbp+37h+hKey]; hKey
0x18000abeb  test    rcx, rcx
0x18000abee  jz      short loc_18000ABF6
0x18000abf0  call    cs:__imp_RegCloseKey
0x18000abf6  mov     rcx, [rbp+37h+var_38]
0x18000abfa  xor     rcx, rsp; StackCookie
0x18000abfd  call    __security_check_cookie
0x18000ac02  add     rsp, 88h
0x18000ac09  pop     r15
0x18000ac0b  pop     r14
0x18000ac0d  pop     rdi
0x18000ac0e  pop     rsi
0x18000ac0f  pop     rbx
0x18000ac10  pop     rbp
0x18000ac11  retn
0x18000ac12  mov     r9d, eax; char *
0x18000ac15  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000ac1c  mov     edx, 8Bh; void *
0x18000ac21  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000ac27  mov     r9d, eax; char *
0x18000ac2a  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000ac31  mov     edx, 83h; void *
0x18000ac36  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000ac3c  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000ac43  mov     edx, 86h; void *
0x18000ac48  mov     rcx, r10; this
0x18000ac4b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
