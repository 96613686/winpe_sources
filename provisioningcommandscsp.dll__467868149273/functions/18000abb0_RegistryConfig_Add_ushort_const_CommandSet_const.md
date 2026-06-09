# RegistryConfig::Add(ushort const *,CommandSet const *)

- ea: `0x18000abb0`
- end: `0x18000ad8a`
- name: `?Add@RegistryConfig@@QEAAXPEBGPEBUCommandSet@@@Z`
- size: `474`
- prototype: `void(RegistryConfig *__hidden this, const unsigned __int16 *, const struct CommandSet *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006e40`

## callees

- `0x180008da4`
- `0x18000abb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aced`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ad03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ad19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aced`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ad03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ad19`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ac01`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ac49`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ac9c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ac01`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ac49`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ac9c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000acd0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000acd0`

## string_xrefs

- `0x18000ad39`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000ad4e`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000ad63`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000ad78`: `admin\prov\launch\lib\registryconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall RegistryConfig::Add(RegistryConfig *this, const unsigned __int16 *a2, const struct CommandSet *a3)
{
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  unsigned int v7; // eax
  const WCHAR *v8; // rdx
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-40h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-40h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-40h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-40h]
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HKEY v17; // [rsp+80h] [rbp+20h] BYREF
  HKEY phkResult; // [rsp+98h] [rbp+38h] BYREF

  hKey = 0;
  v5 = (const WCHAR *)((char *)this + 8);
  if ( *((_QWORD *)this + 4) >= 8u )
    v5 = *(const WCHAR **)v5;
  v6 = RegCreateKeyExW(*(HKEY *)this, v5, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( v6 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x3D,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v6,
      dwOptions);
  phkResult = 0;
  v7 = RegCreateKeyExW(hKey, a2, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
  if ( v7 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x43,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v7,
      dwOptionsa);
  v17 = 0;
  v8 = (const WCHAR *)((char *)a3 + 24);
  if ( *((_QWORD *)a3 + 6) >= 8u )
    v8 = *(const WCHAR **)v8;
  v9 = RegCreateKeyExW(phkResult, v8, 0, 0, 0, 0xF003Fu, 0, &v17, 0);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x48,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v9,
      dwOptionsb);
  v10 = RegSetValueExW(v17, L"altitude", 0, 4u, (const BYTE *)a3, 4u);
  if ( v10 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x50,
      (unsigned int)"admin\\prov\\launch\\lib\\registryconfig.cpp",
      (const char *)v10,
      dwOptionsc);
  if ( v17 )
    RegCloseKey(v17);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18000abb0  mov     [rsp-18h+arg_8], rbx
0x18000abb5  push    rbp
0x18000abb6  push    rsi
0x18000abb7  push    rdi
0x18000abb8  mov     rbp, rsp
0x18000abbb  sub     rsp, 60h
0x18000abbf  mov     rbx, r8
0x18000abc2  mov     rdi, rdx
0x18000abc5  xor     esi, esi
0x18000abc7  mov     [rbp+hKey], rsi
0x18000abcb  lea     rdx, [rcx+8]
0x18000abcf  cmp     qword ptr [rdx+18h], 8
0x18000abd4  jb      short loc_18000ABD9
0x18000abd6  mov     rdx, [rdx]; lpSubKey
0x18000abd9  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x18000abde  lea     rax, [rbp+hKey]
0x18000abe2  mov     [rsp+60h+phkResult], rax; phkResult
0x18000abe7  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000abec  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18000abf4  mov     [rsp+60h+dwOptions], esi; unsigned int
0x18000abf8  xor     r9d, r9d; lpClass
0x18000abfb  xor     r8d, r8d; Reserved
0x18000abfe  mov     rcx, [rcx]; hKey
0x18000ac01  call    cs:__imp_RegCreateKeyExW
0x18000ac08  nop     dword ptr [rax+rax+00h]
0x18000ac0d  mov     rcx, [rbp+18h]; this
0x18000ac11  test    eax, eax
0x18000ac13  jnz     loc_18000AD4B
0x18000ac19  mov     [rbp+arg_18], rsi
0x18000ac1d  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x18000ac22  lea     rax, [rbp+arg_18]
0x18000ac26  mov     [rsp+60h+phkResult], rax; phkResult
0x18000ac2b  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000ac30  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18000ac38  mov     [rsp+60h+dwOptions], esi; unsigned int
0x18000ac3c  xor     r9d, r9d; lpClass
0x18000ac3f  xor     r8d, r8d; Reserved
0x18000ac42  mov     rdx, rdi; lpSubKey
0x18000ac45  mov     rcx, [rbp+hKey]; hKey
0x18000ac49  call    cs:__imp_RegCreateKeyExW
0x18000ac50  nop     dword ptr [rax+rax+00h]
0x18000ac55  mov     rcx, [rbp+18h]; this
0x18000ac59  test    eax, eax
0x18000ac5b  jnz     loc_18000AD60
0x18000ac61  mov     [rbp+arg_0], rsi
0x18000ac65  lea     rdx, [rbx+18h]
0x18000ac69  cmp     qword ptr [rdx+18h], 8
0x18000ac6e  jb      short loc_18000AC73
0x18000ac70  mov     rdx, [rdx]; lpSubKey
0x18000ac73  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x18000ac78  lea     rax, [rbp+arg_0]
0x18000ac7c  mov     [rsp+60h+phkResult], rax; phkResult
0x18000ac81  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000ac86  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18000ac8e  mov     [rsp+60h+dwOptions], esi; unsigned int
0x18000ac92  xor     r9d, r9d; lpClass
0x18000ac95  xor     r8d, r8d; Reserved
0x18000ac98  mov     rcx, [rbp+arg_18]; hKey
0x18000ac9c  call    cs:__imp_RegCreateKeyExW
0x18000aca3  nop     dword ptr [rax+rax+00h]
0x18000aca8  mov     rcx, [rbp+18h]; this
0x18000acac  test    eax, eax
0x18000acae  jnz     loc_18000AD75
0x18000acb4  lea     r9d, [rax+4]; dwType
0x18000acb8  mov     [rsp+60h+samDesired], r9d; cbData
0x18000acbd  mov     qword ptr [rsp+60h+dwOptions], rbx; unsigned int
0x18000acc2  xor     r8d, r8d; Reserved
0x18000acc5  lea     rdx, Value; "altitude"
0x18000accc  mov     rcx, [rbp+arg_0]; hKey
0x18000acd0  call    cs:__imp_RegSetValueExW
0x18000acd7  nop     dword ptr [rax+rax+00h]
0x18000acdc  mov     rcx, [rbp+18h]; this
0x18000ace0  test    eax, eax
0x18000ace2  jnz     short loc_18000AD36
0x18000ace4  mov     rcx, [rbp+arg_0]; hKey
0x18000ace8  test    rcx, rcx
0x18000aceb  jz      short loc_18000ACFA
0x18000aced  call    cs:__imp_RegCloseKey
0x18000acf4  nop     dword ptr [rax+rax+00h]
0x18000acf9  nop
0x18000acfa  mov     rcx, [rbp+arg_18]; hKey
0x18000acfe  test    rcx, rcx
0x18000ad01  jz      short loc_18000AD10
0x18000ad03  call    cs:__imp_RegCloseKey
0x18000ad0a  nop     dword ptr [rax+rax+00h]
0x18000ad0f  nop
0x18000ad10  mov     rcx, [rbp+hKey]; hKey
0x18000ad14  test    rcx, rcx
0x18000ad17  jz      short loc_18000AD25
0x18000ad19  call    cs:__imp_RegCloseKey
0x18000ad20  nop     dword ptr [rax+rax+00h]
0x18000ad25  mov     rbx, [rsp+60h+arg_8]
0x18000ad2d  add     rsp, 60h
0x18000ad31  pop     rdi
0x18000ad32  pop     rsi
0x18000ad33  pop     rbp
0x18000ad34  retn
0x18000ad36  mov     r9d, eax; char *
0x18000ad39  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000ad40  mov     edx, 50h ; 'P'; void *
0x18000ad45  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000ad4b  mov     r9d, eax; char *
0x18000ad4e  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000ad55  mov     edx, 3Dh ; '='; void *
0x18000ad5a  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000ad60  mov     r9d, eax; char *
0x18000ad63  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000ad6a  mov     edx, 43h ; 'C'; void *
0x18000ad6f  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000ad75  mov     r9d, eax; char *
0x18000ad78  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000ad7f  mov     edx, 48h ; 'H'; void *
0x18000ad84  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
