# RegistryConfig::Add(ushort const *,CommandSet const *)

- ea: `0x18000a640`
- end: `0x18000a7ef`
- name: `?Add@RegistryConfig@@QEAAXPEBGPEBUCommandSet@@@Z`
- size: `431`
- prototype: `void __fastcall(RegistryConfig *this, const unsigned __int16 *, const struct CommandSet *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006b10`

## callees

- `0x18000899c`
- `0x18000a640`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a765`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a775`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a785`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a765`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a775`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a785`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a691`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a6d3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a720`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a691`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a6d3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000a720`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a74e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000a74e`

## string_xrefs

- `0x18000a79e`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000a7b3`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000a7c8`: `admin\prov\launch\lib\registryconfig.cpp`
- `0x18000a7dd`: `admin\prov\launch\lib\registryconfig.cpp`

## pseudocode

```c
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
0x18000a640  mov     [rsp-18h+arg_8], rbx
0x18000a645  push    rbp
0x18000a646  push    rsi
0x18000a647  push    rdi
0x18000a648  mov     rbp, rsp
0x18000a64b  sub     rsp, 60h
0x18000a64f  mov     rbx, r8
0x18000a652  mov     rdi, rdx
0x18000a655  xor     esi, esi
0x18000a657  mov     [rbp+hKey], rsi
0x18000a65b  lea     rdx, [rcx+8]
0x18000a65f  cmp     qword ptr [rdx+18h], 8
0x18000a664  jb      short loc_18000A669
0x18000a666  mov     rdx, [rdx]; lpSubKey
0x18000a669  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x18000a66e  lea     rax, [rbp+hKey]
0x18000a672  mov     [rsp+60h+phkResult], rax; phkResult
0x18000a677  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000a67c  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18000a684  mov     [rsp+60h+dwOptions], esi; unsigned int
0x18000a688  xor     r9d, r9d; lpClass
0x18000a68b  xor     r8d, r8d; Reserved
0x18000a68e  mov     rcx, [rcx]; hKey
0x18000a691  call    cs:__imp_RegCreateKeyExW
0x18000a697  mov     rcx, [rbp+18h]; this
0x18000a69b  test    eax, eax
0x18000a69d  jnz     loc_18000A7B0
0x18000a6a3  mov     [rbp+arg_18], rsi
0x18000a6a7  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x18000a6ac  lea     rax, [rbp+arg_18]
0x18000a6b0  mov     [rsp+60h+phkResult], rax; phkResult
0x18000a6b5  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000a6ba  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18000a6c2  mov     [rsp+60h+dwOptions], esi; unsigned int
0x18000a6c6  xor     r9d, r9d; lpClass
0x18000a6c9  xor     r8d, r8d; Reserved
0x18000a6cc  mov     rdx, rdi; lpSubKey
0x18000a6cf  mov     rcx, [rbp+hKey]; hKey
0x18000a6d3  call    cs:__imp_RegCreateKeyExW
0x18000a6d9  mov     rcx, [rbp+18h]; this
0x18000a6dd  test    eax, eax
0x18000a6df  jnz     loc_18000A7C5
0x18000a6e5  mov     [rbp+arg_0], rsi
0x18000a6e9  lea     rdx, [rbx+18h]
0x18000a6ed  cmp     qword ptr [rdx+18h], 8
0x18000a6f2  jb      short loc_18000A6F7
0x18000a6f4  mov     rdx, [rdx]; lpSubKey
0x18000a6f7  mov     [rsp+60h+lpdwDisposition], rsi; lpdwDisposition
0x18000a6fc  lea     rax, [rbp+arg_0]
0x18000a700  mov     [rsp+60h+phkResult], rax; phkResult
0x18000a705  mov     [rsp+60h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x18000a70a  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18000a712  mov     [rsp+60h+dwOptions], esi; unsigned int
0x18000a716  xor     r9d, r9d; lpClass
0x18000a719  xor     r8d, r8d; Reserved
0x18000a71c  mov     rcx, [rbp+arg_18]; hKey
0x18000a720  call    cs:__imp_RegCreateKeyExW
0x18000a726  mov     rcx, [rbp+18h]; this
0x18000a72a  test    eax, eax
0x18000a72c  jnz     loc_18000A7DA
0x18000a732  lea     r9d, [rax+4]; dwType
0x18000a736  mov     [rsp+60h+samDesired], r9d; cbData
0x18000a73b  mov     qword ptr [rsp+60h+dwOptions], rbx; unsigned int
0x18000a740  xor     r8d, r8d; Reserved
0x18000a743  lea     rdx, Value; "altitude"
0x18000a74a  mov     rcx, [rbp+arg_0]; hKey
0x18000a74e  call    cs:__imp_RegSetValueExW
0x18000a754  mov     rcx, [rbp+18h]; this
0x18000a758  test    eax, eax
0x18000a75a  jnz     short loc_18000A79B
0x18000a75c  mov     rcx, [rbp+arg_0]; hKey
0x18000a760  test    rcx, rcx
0x18000a763  jz      short loc_18000A76C
0x18000a765  call    cs:__imp_RegCloseKey
0x18000a76b  nop
0x18000a76c  mov     rcx, [rbp+arg_18]; hKey
0x18000a770  test    rcx, rcx
0x18000a773  jz      short loc_18000A77C
0x18000a775  call    cs:__imp_RegCloseKey
0x18000a77b  nop
0x18000a77c  mov     rcx, [rbp+hKey]; hKey
0x18000a780  test    rcx, rcx
0x18000a783  jz      short loc_18000A78B
0x18000a785  call    cs:__imp_RegCloseKey
0x18000a78b  mov     rbx, [rsp+60h+arg_8]
0x18000a793  add     rsp, 60h
0x18000a797  pop     rdi
0x18000a798  pop     rsi
0x18000a799  pop     rbp
0x18000a79a  retn
0x18000a79b  mov     r9d, eax; char *
0x18000a79e  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000a7a5  mov     edx, 50h ; 'P'; void *
0x18000a7aa  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000a7b0  mov     r9d, eax; char *
0x18000a7b3  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000a7ba  mov     edx, 3Dh ; '='; void *
0x18000a7bf  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000a7c5  mov     r9d, eax; char *
0x18000a7c8  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000a7cf  mov     edx, 43h ; 'C'; void *
0x18000a7d4  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18000a7da  mov     r9d, eax; char *
0x18000a7dd  lea     r8, aAdminProvLaunc_0; "admin\\prov\\launch\\lib\\registryconfi"...
0x18000a7e4  mov     edx, 48h ; 'H'; void *
0x18000a7e9  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
