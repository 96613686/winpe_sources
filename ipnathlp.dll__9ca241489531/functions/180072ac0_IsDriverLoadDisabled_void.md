# IsDriverLoadDisabled(void)

- ea: `0x180072ac0`
- end: `0x180072bf7`
- name: `?IsDriverLoadDisabled@@YAEXZ`
- size: `311`
- prototype: `unsigned __int8(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180047810`
- `0x180069660`

## callees

- `0x18004e0c0`
- `0x180072ac0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180072bb2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180072bb2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072b88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180072b88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072bce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180072bce`

## string_xrefs

- `0x180072ae5`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
bool IsDriverLoadDisabled(void)
{
  bool v0; // bl
  BYTE Data[4]; // [rsp+30h] [rbp-69h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-65h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-61h] BYREF
  wchar_t ValueName[16]; // [rsp+40h] [rbp-59h] BYREF
  WCHAR SubKey[64]; // [rsp+60h] [rbp-39h] BYREF

  wcscpy(SubKey, L"System\\CurrentControlSet\\Services\\SharedAccess\\Parameters");
  v0 = 0;
  hKey = 0;
  wcscpy(ValueName, L"DileIpNat");
  cbData = 4;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey)
    && !RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData) )
  {
    v0 = *(_DWORD *)Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180072ac0  mov     [rsp-8+arg_0], rbx
0x180072ac5  mov     [rsp-8+arg_8], rsi
0x180072aca  push    rbp
0x180072acb  lea     rbp, [rsp-57h]
0x180072ad0  sub     rsp, 0F0h
0x180072ad7  mov     rax, cs:__security_cookie
0x180072ade  xor     rax, rsp
0x180072ae1  mov     [rbp+57h+var_10], rax
0x180072ae5  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x180072aec  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180072af0  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x180072af7  mov     esi, 1
0x180072afc  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x180072b02  mov     r9d, esi; samDesired
0x180072b05  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x180072b09  xor     r8d, r8d; ulOptions
0x180072b0c  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x180072b13  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180072b1a  movaps  [rbp+57h+var_70], xmm0
0x180072b1e  xor     bl, bl
0x180072b20  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x180072b27  movaps  [rbp+57h+var_80], xmm1
0x180072b2b  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x180072b32  movaps  [rbp+57h+var_50], xmm0
0x180072b36  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x180072b3d  movaps  [rbp+57h+var_60], xmm1
0x180072b41  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x180072b48  movaps  [rbp+57h+var_30], xmm0
0x180072b4c  movups  xmm0, xmmword ptr cs:aDisableipnat; "DisableIpNat"
0x180072b53  mov     [rbp+57h+var_20], eax
0x180072b56  lea     rax, [rbp+57h+hKey]
0x180072b5a  movaps  [rbp+57h+var_40], xmm1
0x180072b5e  movups  xmm1, xmmword ptr cs:aDisableipnat+0Ah; "leIpNat"
0x180072b65  mov     [rbp+57h+hKey], 0
0x180072b6d  movups  xmmword ptr [rbp+57h+ValueName], xmm0
0x180072b71  mov     [rbp+57h+cbData], 4
0x180072b78  movups  xmmword ptr [rbp+57h+ValueName+0Ah], xmm1
0x180072b7c  mov     dword ptr [rbp+57h+Data], 0
0x180072b83  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180072b88  call    cs:__imp_RegOpenKeyExW
0x180072b8e  test    eax, eax
0x180072b90  jnz     short loc_180072BC5
0x180072b92  mov     rcx, [rbp+57h+hKey]; hKey
0x180072b96  lea     rax, [rbp+57h+cbData]
0x180072b9a  mov     [rsp+0F0h+lpcbData], rax; lpcbData
0x180072b9f  lea     rdx, [rbp+57h+ValueName]; lpValueName
0x180072ba3  lea     rax, [rbp+57h+Data]
0x180072ba7  xor     r9d, r9d; lpType
0x180072baa  xor     r8d, r8d; lpReserved
0x180072bad  mov     [rsp+0F0h+phkResult], rax; lpData
0x180072bb2  call    cs:__imp_RegQueryValueExW
0x180072bb8  test    eax, eax
0x180072bba  jnz     short loc_180072BC5
0x180072bbc  cmp     dword ptr [rbp+57h+Data], eax
0x180072bbf  movzx   ebx, bl
0x180072bc2  cmovnz  ebx, esi
0x180072bc5  mov     rcx, [rbp+57h+hKey]; hKey
0x180072bc9  test    rcx, rcx
0x180072bcc  jz      short loc_180072BD4
0x180072bce  call    cs:__imp_RegCloseKey
0x180072bd4  mov     al, bl
0x180072bd6  mov     rcx, [rbp+57h+var_10]
0x180072bda  xor     rcx, rsp; StackCookie
0x180072bdd  call    __security_check_cookie
0x180072be2  lea     r11, [rsp+0F0h+var_s0]
0x180072bea  mov     rbx, [r11+10h]
0x180072bee  mov     rsi, [r11+18h]
0x180072bf2  mov     rsp, r11
0x180072bf5  pop     rbp
0x180072bf6  retn
```
