# DwGetInstalledProtocolsEx

- ea: `0x18005ed04`
- end: `0x18005eed1`
- name: `DwGetInstalledProtocolsEx`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000fba0`

## callees

- `0x18005ed04`
- `0x18005f8ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ed5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005edbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ee0d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ed5b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005edbc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005ee0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ed73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ee83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005eea5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ed73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005ee83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005eea5`

## string_xrefs

- `0x18005edae`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`

## pseudocode

```c
__int64 __fastcall DwGetInstalledProtocolsEx(int a1, int a2, int a3)
{
  unsigned int v3; // ebx
  unsigned int i; // edi
  unsigned int j; // edi
  const WCHAR *v8; // rdx
  HKEY v9; // rsi
  int v10; // eax
  int v11; // eax
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  int v14; // [rsp+78h] [rbp+38h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  v14 = a2;
  v3 = 0;
  hKey = 0;
  for ( i = 0; i < 2; ++i )
  {
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)qword_1800EE5C0[3 * (int)i + 1], 0, 0x2000000u, &hKey) )
    {
      v3 |= LODWORD(qword_1800EE5C0[3 * (int)i]);
      RegCloseKey(hKey);
    }
  }
  if ( (a1 || a3) && v3 )
  {
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
           0,
           0x2000000u,
           &hKey) )
    {
      return 0;
    }
    else
    {
      for ( j = 0; j < 2; ++j )
      {
        if ( (v3 & qword_1800EE5C0[3 * (int)j]) != 0 )
        {
          v8 = (const WCHAR *)qword_1800EE5C0[3 * (int)j + 2];
          phkResult = 0;
          if ( !RegOpenKeyExW(hKey, v8, 0, 0x2000000u, &phkResult) )
          {
            v9 = phkResult;
            v14 = 0;
            if ( !a3 || (v10 = RegQueryDword(phkResult, L"EnableIn", &v14), v10 != 2) && (v10 || !v14) )
            {
              if ( !a1 || (v11 = RegQueryDword(v9, L"EnableRoute", &v14), v11 != 2) && (v11 || !v14) )
                v3 &= ~LODWORD(qword_1800EE5C0[3 * (int)j]);
            }
            RegCloseKey(phkResult);
          }
        }
      }
      RegCloseKey(hKey);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18005ed04  mov     [rsp-28h+arg_0], rbx
0x18005ed09  mov     [rsp-28h+arg_10], rsi
0x18005ed0e  mov     [rsp-28h+arg_8], edx
0x18005ed12  push    rbp
0x18005ed13  push    rdi
0x18005ed14  push    r12
0x18005ed16  push    r14
0x18005ed18  push    r15
0x18005ed1a  mov     rbp, rsp
0x18005ed1d  sub     rsp, 40h
0x18005ed21  xor     ebx, ebx
0x18005ed23  lea     r14, qword_1800EE5C0
0x18005ed2a  mov     [rbp+hKey], rbx
0x18005ed2e  xor     edi, edi
0x18005ed30  mov     r15d, r8d
0x18005ed33  mov     r12d, ecx
0x18005ed36  movsxd  rax, edi
0x18005ed39  mov     r9d, 2000000h; samDesired
0x18005ed3f  xor     r8d, r8d; ulOptions
0x18005ed42  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005ed49  lea     rsi, [rax+rax*2]
0x18005ed4d  mov     rdx, [r14+rsi*8+8]; lpSubKey
0x18005ed52  lea     rax, [rbp+hKey]
0x18005ed56  mov     [rsp+40h+phkResult], rax; phkResult
0x18005ed5b  call    cs:__imp_RegOpenKeyExW
0x18005ed62  nop     dword ptr [rax+rax+00h]
0x18005ed67  test    eax, eax
0x18005ed69  jnz     short loc_18005ED7F
0x18005ed6b  or      ebx, [r14+rsi*8]
0x18005ed6f  mov     rcx, [rbp+hKey]; hKey
0x18005ed73  call    cs:__imp_RegCloseKey
0x18005ed7a  nop     dword ptr [rax+rax+00h]
0x18005ed7f  inc     edi
0x18005ed81  cmp     edi, 2
0x18005ed84  jb      short loc_18005ED36
0x18005ed86  test    r12d, r12d
0x18005ed89  jnz     short loc_18005ED94
0x18005ed8b  test    r15d, r15d
0x18005ed8e  jz      loc_18005EEB5
0x18005ed94  test    ebx, ebx
0x18005ed96  jz      loc_18005EEB5
0x18005ed9c  lea     rax, [rbp+hKey]
0x18005eda0  mov     r9d, 2000000h; samDesired
0x18005eda6  xor     r8d, r8d; ulOptions
0x18005eda9  mov     [rsp+40h+phkResult], rax; phkResult
0x18005edae  lea     rdx, aSystemCurrentc_30; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18005edb5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005edbc  call    cs:__imp_RegOpenKeyExW
0x18005edc3  nop     dword ptr [rax+rax+00h]
0x18005edc8  test    eax, eax
0x18005edca  jnz     loc_18005EEB3
0x18005edd0  xor     edi, edi
0x18005edd2  lea     rcx, qword_1800EE5C0
0x18005edd9  movsxd  rax, edi
0x18005eddc  lea     r14, [rax+rax*2]
0x18005ede0  test    [rcx+r14*8], ebx
0x18005ede4  jz      loc_18005EE96
0x18005edea  mov     rdx, [rcx+r14*8+10h]; lpSubKey
0x18005edef  lea     rax, [rbp+var_10]
0x18005edf3  mov     rcx, [rbp+hKey]; hKey
0x18005edf7  mov     r9d, 2000000h; samDesired
0x18005edfd  xor     r8d, r8d; ulOptions
0x18005ee00  mov     [rsp+40h+phkResult], rax; phkResult
0x18005ee05  mov     [rbp+var_10], 0
0x18005ee0d  call    cs:__imp_RegOpenKeyExW
0x18005ee14  nop     dword ptr [rax+rax+00h]
0x18005ee19  test    eax, eax
0x18005ee1b  jnz     short loc_18005EE8F
0x18005ee1d  mov     rsi, [rbp+var_10]
0x18005ee21  mov     [rbp+arg_8], eax
0x18005ee24  test    r15d, r15d
0x18005ee27  jz      short loc_18005EE4A
0x18005ee29  lea     r8, [rbp+arg_8]
0x18005ee2d  mov     rcx, rsi
0x18005ee30  lea     rdx, aEnablein; "EnableIn"
0x18005ee37  call    RegQueryDword
0x18005ee3c  cmp     eax, 2
0x18005ee3f  jz      short loc_18005EE7F
0x18005ee41  test    eax, eax
0x18005ee43  jnz     short loc_18005EE4A
0x18005ee45  cmp     [rbp+arg_8], eax
0x18005ee48  jnz     short loc_18005EE7F
0x18005ee4a  test    r12d, r12d
0x18005ee4d  jz      short loc_18005EE70
0x18005ee4f  lea     r8, [rbp+arg_8]
0x18005ee53  mov     rcx, rsi
0x18005ee56  lea     rdx, aEnableroute; "EnableRoute"
0x18005ee5d  call    RegQueryDword
0x18005ee62  cmp     eax, 2
0x18005ee65  jz      short loc_18005EE7F
0x18005ee67  test    eax, eax
0x18005ee69  jnz     short loc_18005EE70
0x18005ee6b  cmp     [rbp+arg_8], eax
0x18005ee6e  jnz     short loc_18005EE7F
0x18005ee70  lea     rax, qword_1800EE5C0
0x18005ee77  mov     eax, [rax+r14*8]
0x18005ee7b  not     eax
0x18005ee7d  and     ebx, eax
0x18005ee7f  mov     rcx, [rbp+var_10]; hKey
0x18005ee83  call    cs:__imp_RegCloseKey
0x18005ee8a  nop     dword ptr [rax+rax+00h]
0x18005ee8f  lea     rcx, qword_1800EE5C0
0x18005ee96  inc     edi
0x18005ee98  cmp     edi, 2
0x18005ee9b  jb      loc_18005EDD9
0x18005eea1  mov     rcx, [rbp+hKey]; hKey
0x18005eea5  call    cs:__imp_RegCloseKey
0x18005eeac  nop     dword ptr [rax+rax+00h]
0x18005eeb1  jmp     short loc_18005EEB5
0x18005eeb3  xor     ebx, ebx
0x18005eeb5  lea     r11, [rsp+40h+var_s0]
0x18005eeba  mov     eax, ebx
0x18005eebc  mov     rbx, [r11+30h]
0x18005eec0  mov     rsi, [r11+40h]
0x18005eec4  mov     rsp, r11
0x18005eec7  pop     r15
0x18005eec9  pop     r14
0x18005eecb  pop     r12
0x18005eecd  pop     rdi
0x18005eece  pop     rbp
0x18005eecf  retn
```
