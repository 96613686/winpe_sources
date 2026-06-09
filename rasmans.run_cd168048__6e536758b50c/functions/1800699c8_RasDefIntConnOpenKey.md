# RasDefIntConnOpenKey

- ea: `0x1800699c8`
- end: `0x180069bd7`
- name: `RasDefIntConnOpenKey`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180069be0`

## callees

- `0x180001fd0`
- `0x18005c5d4`
- `0x1800699c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069a60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180069a60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069b9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069bb3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069b9e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180069bb3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180069ad2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180069b31`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180069b83`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180069ad2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180069b31`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180069b83`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x180069a20`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineA` at `0x180069a20`

## pseudocode

```c
__int64 __fastcall RasDefIntConnOpenKey(__int64 a1, int a2, int a3, HKEY *a4)
{
  int v7; // eax
  __int64 v9; // rcx
  const char *CommandLineA; // rax
  unsigned int v11; // ebx
  int v12; // edi
  LSTATUS v13; // eax
  HKEY hKey; // [rsp+50h] [rbp-10h] BYREF
  HKEY v15; // [rsp+58h] [rbp-8h] BYREF
  DWORD dwDisposition; // [rsp+80h] [rbp+20h] BYREF

  dwDisposition = 0;
  hKey = 0;
  v15 = 0;
  v7 = IsConsumerPlatform();
  if ( a2 )
  {
    if ( !v7 )
      return 87;
    v9 = -2147483646;
    goto LABEL_11;
  }
  CommandLineA = GetCommandLineA();
  if ( !CommandLineA || !strstr_0(CommandLineA, "-k netsvcs") )
  {
    v9 = -2147483647;
LABEL_11:
    v12 = 0;
    hKey = (HKEY)v9;
    goto LABEL_12;
  }
  v11 = RegOpenKeyExW(HKEY_CURRENT_USER, 0, 0, 0xF003Fu, &hKey);
  if ( !v11 )
  {
    v9 = (__int64)hKey;
    v12 = 1;
LABEL_12:
    v13 = RegCreateKeyExW(
            (HKEY)v9,
            L"Software\\Microsoft\\RAS AutoDial",
            0,
            0,
            0,
            a3 != 0 ? 131101 : 131103,
            0,
            &v15,
            &dwDisposition);
    v11 = v13;
    if ( !v13
      || a3
      && v13 == 5
      && (v11 = RegCreateKeyExW(hKey, L"Software\\Microsoft\\RAS AutoDial", 0, 0, 0, 0x20019u, 0, &v15, &dwDisposition)) == 0 )
    {
      v11 = RegCreateKeyExW(v15, L"Default", 0, 0, 0, a3 != 0 ? 131097 : 131103, 0, a4, &dwDisposition);
    }
    goto LABEL_17;
  }
  v12 = 0;
LABEL_17:
  if ( hKey && v12 )
    RegCloseKey(hKey);
  if ( v15 )
    RegCloseKey(v15);
  return v11;
}

```

## disassembly

```asm
0x1800699c8  mov     [rsp-18h+arg_8], rbx
0x1800699cd  mov     [rsp-18h+arg_10], rsi
0x1800699d2  mov     [rsp-18h+dwDisposition], ecx
0x1800699d6  push    rbp
0x1800699d7  push    rdi
0x1800699d8  push    r14
0x1800699da  mov     rbp, rsp
0x1800699dd  sub     rsp, 60h
0x1800699e1  mov     r14, r9
0x1800699e4  mov     [rbp+dwDisposition], 0
0x1800699eb  mov     esi, r8d
0x1800699ee  mov     [rbp+hKey], 0
0x1800699f6  mov     ebx, edx
0x1800699f8  mov     [rbp+var_8], 0
0x180069a00  call    IsConsumerPlatform
0x180069a05  test    ebx, ebx
0x180069a07  jz      short loc_180069A20
0x180069a09  test    eax, eax
0x180069a0b  jnz     short loc_180069A17
0x180069a0d  mov     eax, 57h ; 'W'
0x180069a12  jmp     loc_180069BC1
0x180069a17  mov     rcx, 0FFFFFFFF80000002h
0x180069a1e  jmp     short loc_180069A89
0x180069a20  call    cs:__imp_GetCommandLineA
0x180069a27  nop     dword ptr [rax+rax+00h]
0x180069a2c  test    rax, rax
0x180069a2f  jz      short loc_180069A82
0x180069a31  lea     rdx, aKNetsvcs; "-k netsvcs"
0x180069a38  mov     rcx, rax; Str
0x180069a3b  call    strstr_0
0x180069a40  test    rax, rax
0x180069a43  jz      short loc_180069A82
0x180069a45  lea     rax, [rbp+hKey]
0x180069a49  mov     r9d, 0F003Fh; samDesired
0x180069a4f  xor     r8d, r8d; ulOptions
0x180069a52  mov     [rsp+60h+phkResult], rax; phkResult
0x180069a57  xor     edx, edx; lpSubKey
0x180069a59  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180069a60  call    cs:__imp_RegOpenKeyExW
0x180069a67  nop     dword ptr [rax+rax+00h]
0x180069a6c  mov     ebx, eax
0x180069a6e  test    eax, eax
0x180069a70  jnz     short loc_180069A7B
0x180069a72  mov     rcx, [rbp+hKey]
0x180069a76  lea     edi, [rax+1]
0x180069a79  jmp     short loc_180069A8F
0x180069a7b  xor     edi, edi
0x180069a7d  jmp     loc_180069B91
0x180069a82  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180069a89  xor     edi, edi
0x180069a8b  mov     [rbp+hKey], rcx
0x180069a8f  mov     eax, esi
0x180069a91  neg     eax
0x180069a93  lea     rax, [rbp+dwDisposition]
0x180069a97  sbb     edx, edx
0x180069a99  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180069a9e  and     edx, 0FFFFFFFEh
0x180069aa1  lea     rax, [rbp+var_8]
0x180069aa5  mov     [rsp+60h+var_28], rax; phkResult
0x180069aaa  add     edx, 2001Fh
0x180069ab0  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180069ab9  xor     r9d, r9d; lpClass
0x180069abc  mov     [rsp+60h+samDesired], edx; samDesired
0x180069ac0  xor     r8d, r8d; Reserved
0x180069ac3  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\RAS AutoDial"
0x180069aca  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x180069ad2  call    cs:__imp_RegCreateKeyExW
0x180069ad9  nop     dword ptr [rax+rax+00h]
0x180069ade  mov     ebx, eax
0x180069ae0  test    eax, eax
0x180069ae2  jz      short loc_180069B43
0x180069ae4  test    esi, esi
0x180069ae6  jz      loc_180069B91
0x180069aec  cmp     eax, 5
0x180069aef  jnz     loc_180069B91
0x180069af5  mov     rcx, [rbp+hKey]; hKey
0x180069af9  lea     rax, [rbp+dwDisposition]
0x180069afd  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180069b02  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\RAS AutoDial"
0x180069b09  lea     rax, [rbp+var_8]
0x180069b0d  xor     r9d, r9d; lpClass
0x180069b10  mov     [rsp+60h+var_28], rax; phkResult
0x180069b15  xor     r8d, r8d; Reserved
0x180069b18  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180069b21  mov     [rsp+60h+samDesired], 20019h; samDesired
0x180069b29  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x180069b31  call    cs:__imp_RegCreateKeyExW
0x180069b38  nop     dword ptr [rax+rax+00h]
0x180069b3d  mov     ebx, eax
0x180069b3f  test    eax, eax
0x180069b41  jnz     short loc_180069B91
0x180069b43  neg     esi
0x180069b45  lea     rcx, [rbp+dwDisposition]
0x180069b49  mov     [rsp+60h+lpdwDisposition], rcx; lpdwDisposition
0x180069b4e  lea     rdx, aDefault; "Default"
0x180069b55  mov     rcx, [rbp+var_8]; hKey
0x180069b59  sbb     eax, eax
0x180069b5b  mov     [rsp+60h+var_28], r14; phkResult
0x180069b60  and     eax, 0FFFFFFFAh
0x180069b63  add     eax, 2001Fh
0x180069b68  mov     [rsp+60h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180069b71  mov     [rsp+60h+samDesired], eax; samDesired
0x180069b75  xor     r9d, r9d; lpClass
0x180069b78  xor     r8d, r8d; Reserved
0x180069b7b  mov     dword ptr [rsp+60h+phkResult], 0; dwOptions
0x180069b83  call    cs:__imp_RegCreateKeyExW
0x180069b8a  nop     dword ptr [rax+rax+00h]
0x180069b8f  mov     ebx, eax
0x180069b91  mov     rcx, [rbp+hKey]; hKey
0x180069b95  test    rcx, rcx
0x180069b98  jz      short loc_180069BAA
0x180069b9a  test    edi, edi
0x180069b9c  jz      short loc_180069BAA
0x180069b9e  call    cs:__imp_RegCloseKey
0x180069ba5  nop     dword ptr [rax+rax+00h]
0x180069baa  mov     rcx, [rbp+var_8]; hKey
0x180069bae  test    rcx, rcx
0x180069bb1  jz      short loc_180069BBF
0x180069bb3  call    cs:__imp_RegCloseKey
0x180069bba  nop     dword ptr [rax+rax+00h]
0x180069bbf  mov     eax, ebx
0x180069bc1  lea     r11, [rsp+60h+var_s0]
0x180069bc6  mov     rbx, [r11+28h]
0x180069bca  mov     rsi, [r11+30h]
0x180069bce  mov     rsp, r11
0x180069bd1  pop     r14
0x180069bd3  pop     rdi
0x180069bd4  pop     rbp
0x180069bd5  retn
```
