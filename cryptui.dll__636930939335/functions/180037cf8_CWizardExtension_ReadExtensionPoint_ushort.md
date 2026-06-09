# CWizardExtension::_ReadExtensionPoint(ushort * *)

- ea: `0x180037cf8`
- end: `0x180037e08`
- name: `?_ReadExtensionPoint@CWizardExtension@@AEAAJPEAPEAG@Z`
- size: `272`
- prototype: `__int64 __fastcall(CWizardExtension *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180037ca4`

## callees

- `0x180037cf8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037d97`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037d97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037df3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037df3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037d82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037dcc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037d82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180037dcc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037d3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180037d3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037dea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180037dea`

## string_xrefs

- `0x180037d78`: `WizardExtension`
- `0x180037dc5`: `WizardExtension`

## pseudocode

```c
__int64 __fastcall CWizardExtension::_ReadExtensionPoint(CWizardExtension *this, BYTE **a2)
{
  BYTE *v2; // rdi
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  bool v6; // cc
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  int v9; // [rsp+54h] [rbp+24h]
  DWORD Type; // [rsp+58h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+30h] BYREF

  v9 = HIDWORD(this);
  v2 = 0;
  cbData = 0;
  *a2 = 0;
  hKey = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Cryptography\\UserInterface", 0, 0x101u, &hKey);
  v5 = v4;
  v6 = v4 <= 0;
  if ( v4 )
    goto LABEL_2;
  Type = 0;
  v4 = RegQueryValueExW(hKey, L"WizardExtension", 0, &Type, 0, &cbData);
  v5 = v4;
  v6 = v4 <= 0;
  if ( v4 )
    goto LABEL_2;
  v2 = (BYTE *)LocalAlloc(0x40u, 2LL * cbData);
  if ( !v2 )
  {
    v5 = -2147024882;
    goto LABEL_9;
  }
  v4 = RegQueryValueExW(hKey, L"WizardExtension", 0, &Type, v2, &cbData);
  v5 = v4;
  v6 = v4 <= 0;
  if ( v4 )
  {
LABEL_2:
    if ( !v6 )
      v5 = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    *a2 = v2;
    v2 = 0;
  }
LABEL_9:
  if ( hKey )
    RegCloseKey(hKey);
  LocalFree(v2);
  return v5;
}

```

## disassembly

```asm
0x180037cf8  mov     [rsp-18h+arg_18], rbx
0x180037cfd  mov     qword ptr [rsp-18h+cbData], rcx
0x180037d02  push    rbp
0x180037d03  push    rsi
0x180037d04  push    rdi
0x180037d05  mov     rbp, rsp
0x180037d08  sub     rsp, 30h
0x180037d0c  xor     edi, edi
0x180037d0e  mov     [rbp+cbData], 0
0x180037d15  mov     [rdx], rdi
0x180037d18  lea     rax, [rbp+hKey]
0x180037d1c  mov     rsi, rdx
0x180037d1f  mov     [rbp+hKey], rdi
0x180037d23  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Cryptography\\User"...
0x180037d2a  mov     [rsp+30h+phkResult], rax; phkResult
0x180037d2f  mov     r9d, 101h; samDesired
0x180037d35  xor     r8d, r8d; ulOptions
0x180037d38  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037d3f  call    cs:__imp_RegOpenKeyExW
0x180037d45  mov     ebx, eax
0x180037d47  test    eax, eax
0x180037d49  jz      short loc_180037D5F
0x180037d4b  jle     loc_180037DE1
0x180037d51  movzx   ebx, ax
0x180037d54  or      ebx, 80070000h
0x180037d5a  jmp     loc_180037DE1
0x180037d5f  mov     rcx, [rbp+hKey]; hKey
0x180037d63  lea     rax, [rbp+cbData]
0x180037d67  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180037d6c  lea     r9, [rbp+Type]; lpType
0x180037d70  xor     r8d, r8d; lpReserved
0x180037d73  mov     [rsp+30h+phkResult], rdi; lpData
0x180037d78  lea     rdx, aWizardextensio; "WizardExtension"
0x180037d7f  mov     [rbp+Type], edi
0x180037d82  call    cs:__imp_RegQueryValueExW
0x180037d88  mov     ebx, eax
0x180037d8a  test    eax, eax
0x180037d8c  jnz     short loc_180037D4B
0x180037d8e  mov     edx, [rbp+cbData]
0x180037d91  lea     ecx, [rax+40h]; uFlags
0x180037d94  add     rdx, rdx; uBytes
0x180037d97  call    cs:__imp_LocalAlloc
0x180037d9d  mov     rdi, rax
0x180037da0  test    rax, rax
0x180037da3  jnz     short loc_180037DAC
0x180037da5  mov     ebx, 8007000Eh
0x180037daa  jmp     short loc_180037DE1
0x180037dac  mov     rcx, [rbp+hKey]; hKey
0x180037db0  lea     rax, [rbp+cbData]
0x180037db4  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180037db9  lea     r9, [rbp+Type]; lpType
0x180037dbd  xor     r8d, r8d; lpReserved
0x180037dc0  mov     [rsp+30h+phkResult], rdi; lpData
0x180037dc5  lea     rdx, aWizardextensio; "WizardExtension"
0x180037dcc  call    cs:__imp_RegQueryValueExW
0x180037dd2  mov     ebx, eax
0x180037dd4  test    eax, eax
0x180037dd6  jnz     loc_180037D4B
0x180037ddc  mov     [rsi], rdi
0x180037ddf  xor     edi, edi
0x180037de1  mov     rcx, [rbp+hKey]; hKey
0x180037de5  test    rcx, rcx
0x180037de8  jz      short loc_180037DF0
0x180037dea  call    cs:__imp_RegCloseKey
0x180037df0  mov     rcx, rdi; hMem
0x180037df3  call    cs:__imp_LocalFree
0x180037df9  mov     eax, ebx
0x180037dfb  mov     rbx, [rsp+30h+arg_18]
0x180037e00  add     rsp, 30h
0x180037e04  pop     rdi
0x180037e05  pop     rsi
0x180037e06  pop     rbp
0x180037e07  retn
```
