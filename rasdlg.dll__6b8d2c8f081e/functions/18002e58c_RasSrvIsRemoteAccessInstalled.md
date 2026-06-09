# RasSrvIsRemoteAccessInstalled

- ea: `0x18002e58c`
- end: `0x18002e64d`
- name: `RasSrvIsRemoteAccessInstalled`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18002de30`

## callees

- `0x18002e58c`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e617`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002e617`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e626`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002e626`

## string_xrefs

- `0x18002e5b4`: `SYSTEM\CurrentControlSet\Services\RemoteAccess`

## pseudocode

```c
__int64 RasSrvIsRemoteAccessInstalled()
{
  HKEY hKey; // [rsp+30h] [rbp-88h] BYREF
  _OWORD v2[4]; // [rsp+40h] [rbp-78h] BYREF
  _OWORD v3[2]; // [rsp+80h] [rbp-38h]

  v2[1] = *(_OWORD *)L"urrentControlSet\\Services\\RemoteAccess";
  v2[0] = *(_OWORD *)L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess";
  v2[3] = *(_OWORD *)L"\\Services\\RemoteAccess";
  hKey = 0;
  v2[2] = *(_OWORD *)L"ntrolSet\\Services\\RemoteAccess";
  v3[0] = *(_OWORD *)L"s\\RemoteAccess";
  *(_OWORD *)((char *)v3 + 14) = *(_OWORD *)L"eAccess";
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v2, 0, 0x20019u, &hKey) )
    return 0;
  RegCloseKey(hKey);
  return 1;
}

```

## disassembly

```asm
0x18002e58c  mov     r11, rsp
0x18002e58f  sub     rsp, 0B8h
0x18002e596  mov     rax, cs:__security_cookie
0x18002e59d  xor     rax, rsp
0x18002e5a0  mov     [rsp+0B8h+var_18], rax
0x18002e5a8  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+10h; "urrentControlSet\\Services\\RemoteAcces"...
0x18002e5af  lea     rax, [rsp+0B8h+hKey]
0x18002e5b4  movaps  xmm0, xmmword ptr cs:aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18002e5bb  lea     rdx, [r11-78h]; lpSubKey
0x18002e5bf  movaps  [rsp+0B8h+var_68], xmm1
0x18002e5c4  mov     r9d, 20019h; samDesired
0x18002e5ca  movaps  xmm1, xmmword ptr cs:aSystemCurrentc+30h; "\\Services\\RemoteAccess"
0x18002e5d1  xor     r8d, r8d; ulOptions
0x18002e5d4  movaps  [rsp+0B8h+var_78], xmm0
0x18002e5d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002e5e0  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+20h; "ntrolSet\\Services\\RemoteAccess"
0x18002e5e7  movaps  [rsp+0B8h+var_48], xmm1
0x18002e5ec  movups  xmm1, xmmword ptr cs:aSystemCurrentc+4Eh; "eAccess"
0x18002e5f3  mov     [rsp+0B8h+hKey], 0
0x18002e5fc  movaps  [rsp+0B8h+var_58], xmm0
0x18002e601  movaps  xmm0, xmmword ptr cs:aSystemCurrentc+40h; "s\\RemoteAccess"
0x18002e608  movaps  xmmword ptr [r11-38h], xmm0
0x18002e60d  movups  xmmword ptr [r11-2Ah], xmm1
0x18002e612  mov     [rsp+0B8h+phkResult], rax; phkResult
0x18002e617  call    cs:__imp_RegOpenKeyExW
0x18002e61d  test    eax, eax
0x18002e61f  jnz     short loc_18002E633
0x18002e621  mov     rcx, [rsp+0B8h+hKey]; hKey
0x18002e626  call    cs:__imp_RegCloseKey
0x18002e62c  mov     eax, 1
0x18002e631  jmp     short loc_18002E635
0x18002e633  xor     eax, eax
0x18002e635  mov     rcx, [rsp+0B8h+var_18]
0x18002e63d  xor     rcx, rsp; StackCookie
0x18002e640  call    __security_check_cookie
0x18002e645  add     rsp, 0B8h
0x18002e64c  retn
```
