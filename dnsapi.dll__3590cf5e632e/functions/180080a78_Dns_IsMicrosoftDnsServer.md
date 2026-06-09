# Dns_IsMicrosoftDnsServer

- ea: `0x180080a78`
- end: `0x180080af2`
- name: `Dns_IsMicrosoftDnsServer`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006d40`
- `0x180062990`

## callees

- `0x180080a78`
- `0x18008b5f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080ace`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180080ace`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080ab5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180080ab5`

## string_xrefs

- `0x180080aa7`: `System\CurrentControlSet\Services\DNS`

## pseudocode

```c
__int64 Dns_IsMicrosoftDnsServer()
{
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\DNS", 0, 1u, &hKey) )
    return 0;
  RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x180080a78  sub     rsp, 48h
0x180080a7c  mov     rax, cs:__security_cookie
0x180080a83  xor     rax, rsp
0x180080a86  mov     [rsp+48h+var_10], rax
0x180080a8b  lea     rax, [rsp+48h+hKey]
0x180080a90  mov     [rsp+48h+hKey], 0
0x180080a99  mov     r9d, 1; samDesired
0x180080a9f  mov     [rsp+48h+phkResult], rax; phkResult
0x180080aa4  xor     r8d, r8d; ulOptions
0x180080aa7  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\DN"...
0x180080aae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180080ab5  call    cs:__imp_RegOpenKeyExW
0x180080abc  nop     dword ptr [rax+rax+00h]
0x180080ac1  test    eax, eax
0x180080ac3  jz      short loc_180080AC9
0x180080ac5  xor     eax, eax
0x180080ac7  jmp     short loc_180080ADF
0x180080ac9  mov     rcx, [rsp+48h+hKey]; hKey
0x180080ace  call    cs:__imp_RegCloseKey
0x180080ad5  nop     dword ptr [rax+rax+00h]
0x180080ada  mov     eax, 1
0x180080adf  mov     rcx, [rsp+48h+var_10]
0x180080ae4  xor     rcx, rsp; StackCookie
0x180080ae7  call    __security_check_cookie
0x180080aec  add     rsp, 48h
0x180080af0  retn
```
