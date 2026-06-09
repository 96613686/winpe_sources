# SetCensusReturnCodeRegkey(ulong const &)

- ea: `0x140002c14`
- end: `0x140002cfa`
- name: `?SetCensusReturnCodeRegkey@@YAXAEBK@Z`
- size: `230`
- prototype: `void __fastcall(const unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140003610`

## callees

- `0x14000233f`
- `0x140002c14`
- `0x1400115f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002cdc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140002cdc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140002ca0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140002ca0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140002ccc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140002ccc`
- `dcntel!GetCensusRegistryLocation` at `0x140002c58`
- `dcntel!GetCensusRegistryLocation` at `0x140002c58`

## pseudocode

```c
void __fastcall SetCensusReturnCodeRegkey(const unsigned int *a1)
{
  int v1; // eax
  BYTE Data[8]; // [rsp+50h] [rbp-238h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-230h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-228h] BYREF

  v1 = *a1;
  hKey = 0;
  *(_DWORD *)Data = v1;
  memset_0(SubKey, 0, 0x20Au);
  if ( (int)GetCensusRegistryLocation(SubKey, 0x105u) >= 0
    && !RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0) )
  {
    RegSetValueExW(hKey, L"ReturnCode", 0, 4u, Data, 4u);
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x140002c14  sub     rsp, 288h
0x140002c1b  mov     rax, cs:__security_cookie
0x140002c22  xor     rax, rsp
0x140002c25  mov     [rsp+288h+var_18], rax
0x140002c2d  mov     eax, [rcx]
0x140002c2f  xor     edx, edx; Val
0x140002c31  lea     rcx, [rsp+288h+SubKey]; void *
0x140002c36  mov     [rsp+288h+hKey], 0
0x140002c3f  mov     r8d, 20Ah; Size
0x140002c45  mov     dword ptr [rsp+288h+Data], eax
0x140002c49  call    memset_0
0x140002c4e  mov     edx, 105h
0x140002c53  lea     rcx, [rsp+288h+SubKey]
0x140002c58  call    cs:__imp_?GetCensusRegistryLocation@@YAJPEAGK@Z; GetCensusRegistryLocation(ushort *,ulong)
0x140002c5e  test    eax, eax
0x140002c60  js      short loc_140002CD2
0x140002c62  mov     [rsp+288h+lpdwDisposition], 0; lpdwDisposition
0x140002c6b  lea     rax, [rsp+288h+hKey]
0x140002c70  mov     [rsp+288h+phkResult], rax; phkResult
0x140002c75  lea     rdx, [rsp+288h+SubKey]; lpSubKey
0x140002c7a  mov     [rsp+288h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140002c83  xor     r9d, r9d; lpClass
0x140002c86  mov     [rsp+288h+samDesired], 0F003Fh; samDesired
0x140002c8e  xor     r8d, r8d; Reserved
0x140002c91  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140002c98  mov     [rsp+288h+dwOptions], 0; dwOptions
0x140002ca0  call    cs:__imp_RegCreateKeyExW
0x140002ca6  test    eax, eax
0x140002ca8  jnz     short loc_140002CD2
0x140002caa  mov     rcx, [rsp+288h+hKey]; hKey
0x140002caf  lea     r9d, [rax+4]; dwType
0x140002cb3  lea     rax, [rsp+288h+Data]
0x140002cb8  mov     [rsp+288h+samDesired], r9d; cbData
0x140002cbd  xor     r8d, r8d; Reserved
0x140002cc0  mov     qword ptr [rsp+288h+dwOptions], rax; lpData
0x140002cc5  lea     rdx, ValueName; "ReturnCode"
0x140002ccc  call    cs:__imp_RegSetValueExW
0x140002cd2  mov     rcx, [rsp+288h+hKey]; hKey
0x140002cd7  test    rcx, rcx
0x140002cda  jz      short loc_140002CE2
0x140002cdc  call    cs:__imp_RegCloseKey
0x140002ce2  mov     rcx, [rsp+288h+var_18]
0x140002cea  xor     rcx, rsp; StackCookie
0x140002ced  call    __security_check_cookie
0x140002cf2  add     rsp, 288h
0x140002cf9  retn
```
