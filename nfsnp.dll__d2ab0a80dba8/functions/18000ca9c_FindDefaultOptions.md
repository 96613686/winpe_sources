# FindDefaultOptions

- ea: `0x18000ca9c`
- end: `0x18000cb2b`
- name: `FindDefaultOptions`
- size: `143`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000be24`

## callees

- `0x18000ca9c`
- `0x18000cf74`
- `0x180011ba0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000cb05`
- `ADVAPI32!RegCloseKey` at `0x18000cb05`
- `ADVAPI32!RegOpenKeyExW` at `0x18000caf4`
- `ADVAPI32!RegOpenKeyExW` at `0x18000caf4`

## pseudocode

```c
_BOOL8 __fastcall FindDefaultOptions(HKEY hKey)
{
  LSTATUS v2; // ebx
  HKEY hKeya; // [rsp+30h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF

  hKeya = 0;
  DaBuildRegistryPath(0, L"Default", (__int64)hKey, SubKey);
  v2 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &hKeya);
  if ( !v2 )
    RegCloseKey(hKeya);
  return v2 == 0;
}

```

## disassembly

```asm
0x18000ca9c  push    rbx
0x18000ca9e  sub     rsp, 260h
0x18000caa5  mov     rax, cs:__security_cookie
0x18000caac  xor     rax, rsp
0x18000caaf  mov     [rsp+268h+var_18], rax
0x18000cab7  mov     rbx, rcx
0x18000caba  mov     [rsp+268h+hKey], 0
0x18000cac3  mov     r8, rcx
0x18000cac6  lea     r9, [rsp+268h+SubKey]
0x18000cacb  xor     ecx, ecx
0x18000cacd  lea     rdx, aDefault; "Default"
0x18000cad4  call    DaBuildRegistryPath
0x18000cad9  lea     rax, [rsp+268h+hKey]
0x18000cade  mov     r9d, 20019h; samDesired
0x18000cae4  xor     r8d, r8d; ulOptions
0x18000cae7  mov     [rsp+268h+phkResult], rax; phkResult
0x18000caec  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x18000caf1  mov     rcx, rbx; hKey
0x18000caf4  call    cs:__imp_RegOpenKeyExW
0x18000cafa  mov     ebx, eax
0x18000cafc  test    eax, eax
0x18000cafe  jnz     short loc_18000CB0B
0x18000cb00  mov     rcx, [rsp+268h+hKey]; hKey
0x18000cb05  call    cs:__imp_RegCloseKey
0x18000cb0b  xor     eax, eax
0x18000cb0d  test    ebx, ebx
0x18000cb0f  setz    al
0x18000cb12  mov     rcx, [rsp+268h+var_18]
0x18000cb1a  xor     rcx, rsp; StackCookie
0x18000cb1d  call    __security_check_cookie
0x18000cb22  add     rsp, 260h
0x18000cb29  pop     rbx
0x18000cb2a  retn
```
