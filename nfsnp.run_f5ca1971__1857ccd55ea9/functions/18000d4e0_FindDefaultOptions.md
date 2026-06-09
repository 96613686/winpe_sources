# FindDefaultOptions

- ea: `0x18000d4e0`
- end: `0x18000d57c`
- name: `FindDefaultOptions`
- size: `156`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000c738`

## callees

- `0x18000d4e0`
- `0x18000da44`
- `0x180012e70`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000d54f`
- `ADVAPI32!RegCloseKey` at `0x18000d54f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000d538`
- `ADVAPI32!RegOpenKeyExW` at `0x18000d538`

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
0x18000d4e0  push    rbx
0x18000d4e2  sub     rsp, 260h
0x18000d4e9  mov     rax, cs:__security_cookie
0x18000d4f0  xor     rax, rsp
0x18000d4f3  mov     [rsp+268h+var_18], rax
0x18000d4fb  mov     rbx, rcx
0x18000d4fe  mov     [rsp+268h+hKey], 0
0x18000d507  mov     r8, rcx
0x18000d50a  lea     r9, [rsp+268h+SubKey]
0x18000d50f  xor     ecx, ecx
0x18000d511  lea     rdx, aDefault; "Default"
0x18000d518  call    DaBuildRegistryPath
0x18000d51d  lea     rax, [rsp+268h+hKey]
0x18000d522  mov     r9d, 20019h; samDesired
0x18000d528  xor     r8d, r8d; ulOptions
0x18000d52b  mov     [rsp+268h+phkResult], rax; phkResult
0x18000d530  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x18000d535  mov     rcx, rbx; hKey
0x18000d538  call    cs:__imp_RegOpenKeyExW
0x18000d53f  nop     dword ptr [rax+rax+00h]
0x18000d544  mov     ebx, eax
0x18000d546  test    eax, eax
0x18000d548  jnz     short loc_18000D55B
0x18000d54a  mov     rcx, [rsp+268h+hKey]; hKey
0x18000d54f  call    cs:__imp_RegCloseKey
0x18000d556  nop     dword ptr [rax+rax+00h]
0x18000d55b  xor     eax, eax
0x18000d55d  test    ebx, ebx
0x18000d55f  setz    al
0x18000d562  mov     rcx, [rsp+268h+var_18]
0x18000d56a  xor     rcx, rsp; StackCookie
0x18000d56d  call    __security_check_cookie
0x18000d572  add     rsp, 260h
0x18000d579  pop     rbx
0x18000d57a  retn
```
