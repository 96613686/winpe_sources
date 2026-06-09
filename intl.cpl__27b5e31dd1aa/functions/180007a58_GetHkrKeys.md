# GetHkrKeys

- ea: `0x180007a58`
- end: `0x180007ad5`
- name: `GetHkrKeys`
- size: `125`
- prototype: `__int64 __fastcall(HKEY hKey, HKEY, PHKEY phkResult, PHKEY, PHKEY)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007b70`
- `0x180007cec`

## callees

- `0x180007684`
- `0x18000793c`
- `0x180007a58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007a85`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180007a85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007abb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007ac4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007abb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007ac4`

## pseudocode

```c
__int64 __fastcall GetHkrKeys(HKEY hKey, HKEY a2, PHKEY phkResult, PHKEY a4, PHKEY a5)
{
  unsigned int CurrentControlSetKey; // ebx

  CurrentControlSetKey = RegOpenKeyExW(a2, L"Microsoft", 0, 0xF003Fu, phkResult);
  if ( !CurrentControlSetKey )
  {
    CurrentControlSetKey = GetCurrentControlSetKey(hKey, a4);
    if ( CurrentControlSetKey )
    {
LABEL_5:
      RegCloseKey(*phkResult);
      return CurrentControlSetKey;
    }
    CurrentControlSetKey = GetHardwareProfileKey(*a4, a5);
    if ( CurrentControlSetKey )
    {
      RegCloseKey(*a4);
      goto LABEL_5;
    }
  }
  return CurrentControlSetKey;
}

```

## disassembly

```asm
0x180007a58  push    rbx
0x180007a5a  push    rbp
0x180007a5b  push    rsi
0x180007a5c  push    rdi
0x180007a5d  sub     rsp, 38h
0x180007a61  mov     rax, rdx
0x180007a64  mov     [rsp+58h+phkResult], r8; phkResult
0x180007a69  mov     rdi, r9
0x180007a6c  lea     rdx, aMicrosoft; "Microsoft"
0x180007a73  mov     rsi, r8
0x180007a76  mov     rbp, rcx
0x180007a79  mov     rcx, rax; hKey
0x180007a7c  mov     r9d, 0F003Fh; samDesired
0x180007a82  xor     r8d, r8d; ulOptions
0x180007a85  call    cs:__imp_RegOpenKeyExW
0x180007a8b  mov     ebx, eax
0x180007a8d  test    eax, eax
0x180007a8f  jnz     short loc_180007ACA
0x180007a91  mov     rdx, rdi; phkResult
0x180007a94  mov     rcx, rbp; hKey
0x180007a97  call    GetCurrentControlSetKey
0x180007a9c  mov     ebx, eax
0x180007a9e  test    eax, eax
0x180007aa0  jnz     short loc_180007AC1
0x180007aa2  mov     rdx, [rsp+58h+arg_20]; phkResult
0x180007aaa  mov     rcx, [rdi]; hKey
0x180007aad  call    GetHardwareProfileKey
0x180007ab2  mov     ebx, eax
0x180007ab4  test    eax, eax
0x180007ab6  jz      short loc_180007ACA
0x180007ab8  mov     rcx, [rdi]; hKey
0x180007abb  call    cs:__imp_RegCloseKey
0x180007ac1  mov     rcx, [rsi]; hKey
0x180007ac4  call    cs:__imp_RegCloseKey
0x180007aca  mov     eax, ebx
0x180007acc  add     rsp, 38h
0x180007ad0  pop     rdi
0x180007ad1  pop     rsi
0x180007ad2  pop     rbp
0x180007ad3  pop     rbx
0x180007ad4  retn
```
