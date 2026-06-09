# IsUiccProvisioningEnabled

- ea: `0x18002aa6c`
- end: `0x18002ab39`
- name: `IsUiccProvisioningEnabled`
- size: `205`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18002a5e4`
- `0x18002a910`

## callees

- `0x18001b3a8`
- `0x18002aa6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002aaf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ab16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002aaf2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002ab16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002aa9c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002aa9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aadd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002aadd`

## string_xrefs

- `0x18002ab27`: `onecoreuap\admin\prov\lib\provagent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool IsUiccProvisioningEnabled()
{
  unsigned int v0; // eax
  bool v2; // bl
  unsigned int phkResult; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, gc_wszRegMultivariant, 0, 1u, &hKey) == 2
    || (Data = 0, cbData = 4, v0 = RegQueryValueExW(hKey, L"Enable", 0, 0, (LPBYTE)&Data, &cbData), v0 == 2) )
  {
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    if ( v0 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x53,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provagent.cpp",
        (const char *)v0,
        phkResult);
    v2 = Data != 0;
    if ( hKey )
      RegCloseKey(hKey);
    return v2;
  }
}

```

## disassembly

```asm
0x18002aa6c  push    rbx
0x18002aa6e  sub     rsp, 30h
0x18002aa72  mov     [rsp+38h+hKey], 0
0x18002aa7b  lea     rax, [rsp+38h+hKey]
0x18002aa80  mov     [rsp+38h+phkResult], rax; phkResult
0x18002aa85  mov     r9d, 1; samDesired
0x18002aa8b  xor     r8d, r8d; ulOptions
0x18002aa8e  mov     rdx, cs:?gc_wszRegMultivariant@@3PEBGEB; lpSubKey
0x18002aa95  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002aa9c  call    cs:__imp_RegOpenKeyExW
0x18002aaa2  cmp     eax, 2
0x18002aaa5  jz      short loc_18002AAE8
0x18002aaa7  mov     [rsp+38h+Data], 0
0x18002aaaf  mov     [rsp+38h+cbData], 4
0x18002aab7  lea     rax, [rsp+38h+cbData]
0x18002aabc  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18002aac1  lea     rax, [rsp+38h+Data]
0x18002aac6  mov     [rsp+38h+phkResult], rax; unsigned int
0x18002aacb  xor     r9d, r9d; lpType
0x18002aace  xor     r8d, r8d; lpReserved
0x18002aad1  lea     rdx, ?gc_wszEnable@@3QBGB; "Enable"
0x18002aad8  mov     rcx, [rsp+38h+hKey]; hKey
0x18002aadd  call    cs:__imp_RegQueryValueExW
0x18002aae3  cmp     eax, 2
0x18002aae6  jnz     short loc_18002AAFC
0x18002aae8  mov     rcx, [rsp+38h+hKey]; hKey
0x18002aaed  test    rcx, rcx
0x18002aaf0  jz      short loc_18002AAF8
0x18002aaf2  call    cs:__imp_RegCloseKey
0x18002aaf8  xor     al, al
0x18002aafa  jmp     short loc_18002AB1E
0x18002aafc  mov     rcx, [rsp+38h]; this
0x18002ab01  test    eax, eax
0x18002ab03  jnz     short loc_18002AB24
0x18002ab05  cmp     [rsp+38h+Data], eax
0x18002ab09  setnz   bl
0x18002ab0c  mov     rcx, [rsp+38h+hKey]; hKey
0x18002ab11  test    rcx, rcx
0x18002ab14  jz      short loc_18002AB1C
0x18002ab16  call    cs:__imp_RegCloseKey
0x18002ab1c  mov     al, bl
0x18002ab1e  add     rsp, 30h
0x18002ab22  pop     rbx
0x18002ab23  retn
0x18002ab24  mov     r9d, eax; char *
0x18002ab27  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\prov\\lib\\provagent"...
0x18002ab2e  mov     edx, 53h ; 'S'; void *
0x18002ab33  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
