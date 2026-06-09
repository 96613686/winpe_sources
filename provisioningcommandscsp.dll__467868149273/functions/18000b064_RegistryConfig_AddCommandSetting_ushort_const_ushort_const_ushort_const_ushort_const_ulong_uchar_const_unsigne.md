# RegistryConfig::AddCommandSetting(ushort const *,ushort const *,ushort const *,ushort const *,ulong,uchar const *,unsigned __int64)

- ea: `0x18000b064`
- end: `0x18000b24c`
- name: `?AddCommandSetting@RegistryConfig@@QEAAXPEBG000KPEBE_K@Z`
- size: `488`
- prototype: `void __fastcall(RegistryConfig *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, LPCWSTR lpValueName, DWORD dwType, BYTE *lpData, DWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180008a70`

## callees

- `0x180007b84`
- `0x180008da4`
- `0x18000b064`
- `0x18000b254`
- `0x18000ccc0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000b1b9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000b1b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b108`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b108`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b0fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b1e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b0fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b1e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b13f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b13f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b19a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000b19a`

## string_xrefs

- `0x18000b210`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000b225`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000b237`: `admin\prov\launch\lib\registryconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18000b064  push    rbp
0x18000b066  push    rbx
0x18000b067  push    rsi
0x18000b068  push    rdi
0x18000b069  push    r14
0x18000b06b  push    r15
0x18000b06d  lea     rbp, [rsp-0Fh]
0x18000b072  sub     rsp, 88h
0x18000b079  mov     rax, cs:__security_cookie
0x18000b080  xor     rax, rsp
0x18000b083  mov     [rbp+37h+var_38], rax
0x18000b087  mov     rax, r9
0x18000b08a  mov     rsi, rcx
0x18000b08d  mov     r14, [rbp+37h+lpValueName]
0x18000b091  mov     r15, [rbp+37h+lpData]
0x18000b095  mov     [rbp+37h+hKey], 0
0x18000b09d  lea     r9, [rcx+8]
0x18000b0a1  cmp     qword ptr [r9+18h], 8
0x18000b0a6  jb      short loc_18000B0AB
0x18000b0a8  mov     r9, [r9]
0x18000b0ab  mov     [rsp+0B0h+var_68], rax
0x18000b0b0  lea     rax, asc_180010164; "\\"
0x18000b0b7  mov     [rsp+0B0h+var_70], rax
0x18000b0bc  mov     [rsp+0B0h+var_78], r8
0x18000b0c1  mov     [rsp+0B0h+var_80], rax
0x18000b0c6  mov     qword ptr [rsp+0B0h+cbData], rdx
0x18000b0cb  mov     [rsp+0B0h+phkResult], rax
0x18000b0d0  mov     r8d, 7
0x18000b0d6  lea     rdx, [rbp+37h+lpSubKey]
0x18000b0da  call    ?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ; RegistryConfig::AppendStrings(int,...)
0x18000b0df  nop
0x18000b0e0  mov     rdi, [rbp+37h+hKey]
0x18000b0e4  test    rdi, rdi
0x18000b0e7  jz      short loc_18000B114
0x18000b0e9  call    cs:__imp_GetLastError
0x18000b0f0  nop     dword ptr [rax+rax+00h]
0x18000b0f5  mov     ebx, eax
0x18000b0f7  mov     rcx, rdi; hKey
0x18000b0fa  call    cs:__imp_RegCloseKey
0x18000b101  nop     dword ptr [rax+rax+00h]
0x18000b106  mov     ecx, ebx; dwErrCode
0x18000b108  call    cs:__imp_SetLastError
0x18000b10f  nop     dword ptr [rax+rax+00h]
0x18000b114  mov     [rbp+37h+hKey], 0
0x18000b11c  lea     rdx, [rbp+37h+lpSubKey]
0x18000b120  cmp     [rbp+37h+var_40], 8
0x18000b125  cmovnb  rdx, [rbp+37h+lpSubKey]; lpSubKey
0x18000b12a  lea     rax, [rbp+37h+hKey]
0x18000b12e  mov     [rsp+0B0h+phkResult], rax; int
0x18000b133  mov     r9d, 0F003Fh; samDesired
0x18000b139  xor     r8d, r8d; ulOptions
0x18000b13c  mov     rcx, [rsi]; hKey
0x18000b13f  call    cs:__imp_RegOpenKeyExW
0x18000b146  nop     dword ptr [rax+rax+00h]
0x18000b14b  mov     rcx, [rbp+3Fh]; this
0x18000b14f  test    eax, eax
0x18000b151  jnz     loc_18000B222
0x18000b157  mov     edx, 0FFFFFFFFh
0x18000b15c  mov     rax, qword ptr [rbp+37h+arg_38]
0x18000b160  cmp     rax, rdx
0x18000b163  mov     ecx, eax
0x18000b165  jbe     short loc_18000B169
0x18000b167  mov     ecx, edx
0x18000b169  cmp     rdx, rax
0x18000b16c  sbb     r9d, r9d
0x18000b16f  and     r9d, 80070216h; char *
0x18000b176  mov     r10, [rbp+3Fh]
0x18000b17a  cmp     rax, rdx
0x18000b17d  ja      loc_18000B237
0x18000b183  mov     [rsp+0B0h+cbData], ecx; cbData
0x18000b187  mov     [rsp+0B0h+phkResult], r15; unsigned int
0x18000b18c  mov     r9d, [rbp+37h+dwType]; dwType
0x18000b190  xor     r8d, r8d; Reserved
0x18000b193  mov     rdx, r14; lpValueName
0x18000b196  mov     rcx, [rbp+37h+hKey]; hKey
0x18000b19a  call    cs:__imp_RegSetValueExW
0x18000b1a1  nop     dword ptr [rax+rax+00h]
0x18000b1a6  mov     rcx, [rbp+3Fh]; this
0x18000b1aa  test    eax, eax
0x18000b1ac  jnz     short loc_18000B20D
0x18000b1ae  cmp     [rbp+37h+var_40], 8
0x18000b1b3  jb      short loc_18000B1C5
0x18000b1b5  mov     rcx, [rbp+37h+lpSubKey]
0x18000b1b9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000b1c0  nop     dword ptr [rax+rax+00h]
0x18000b1c5  mov     [rbp+37h+var_40], 7
0x18000b1cd  mov     [rbp+37h+var_48], 0
0x18000b1d5  xor     eax, eax
0x18000b1d7  mov     word ptr [rbp+37h+lpSubKey], ax
0x18000b1db  mov     rcx, [rbp+37h+hKey]; hKey
0x18000b1df  test    rcx, rcx
0x18000b1e2  jz      short loc_18000B1F0
0x18000b1e4  call    cs:__imp_RegCloseKey
0x18000b1eb  nop     dword ptr [rax+rax+00h]
0x18000b1f0  mov     rcx, [rbp+37h+var_38]
0x18000b1f4  xor     rcx, rsp; StackCookie
0x18000b1f7  call    __security_check_cookie
0x18000b1fc  add     rsp, 88h
0x18000b203  pop     r15
0x18000b205  pop     r14
0x18000b207  pop     rdi
0x18000b208  pop     rsi
0x18000b209  pop     rbx
0x18000b20a  pop     rbp
0x18000b20b  retn
0x18000b20d  mov     r9d, eax; char *
0x18000b210  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000b217  mov     edx, 8Bh; void *
0x18000b21c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000b222  mov     r9d, eax; char *
0x18000b225  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000b22c  mov     edx, 83h; void *
0x18000b231  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000b237  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000b23e  mov     edx, 86h; void *
0x18000b243  mov     rcx, r10; this
0x18000b246  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
