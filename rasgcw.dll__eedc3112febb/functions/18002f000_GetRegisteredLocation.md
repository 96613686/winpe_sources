# GetRegisteredLocation

- ea: `0x18002f000`
- end: `0x18002f114`
- name: `GetRegisteredLocation`
- size: `276`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002f11c`

## callees

- `0x1800176ec`
- `0x18002f000`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f0e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f0e7`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x18002f0b7`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x18002f0b7`
- `KERNEL32!RegOpenKeyExA` at `0x18002f052`
- `KERNEL32!RegOpenKeyExA` at `0x18002f052`
- `KERNEL32!RegQueryValueExA` at `0x18002f095`
- `KERNEL32!RegQueryValueExA` at `0x18002f095`

## string_xrefs

- `0x18002f04b`: `CLSID\{ADB880A6-D8FF-11CF-9377-00AA003B7A11}\InprocServer32`

## pseudocode

```c
_BOOL8 __fastcall GetRegisteredLocation(char *a1)
{
  BOOL v2; // ebx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[272]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  if ( RegOpenKeyExA(
         HKEY_CLASSES_ROOT,
         "CLSID\\{ADB880A6-D8FF-11CF-9377-00AA003B7A11}\\InprocServer32",
         0,
         0x20019u,
         &hKey) )
  {
    return 0;
  }
  cbData = 260;
  Type = 1;
  v2 = 0;
  if ( !RegQueryValueExA(hKey, 0, 0, &Type, Data, &cbData) )
  {
    Data[259] = 0;
    if ( Type == 2 )
      LOBYTE(v2) = ExpandEnvironmentStringsA((LPCSTR)Data, a1, 0x104u) - 1 <= 0x103;
    else
      v2 = (int)StringCchCopyA(a1, 0x104u, (const char *)Data) >= 0;
  }
  RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x18002f000  mov     [rsp-8+arg_8], rbx
0x18002f005  mov     [rsp-8+arg_10], rdi
0x18002f00a  push    rbp
0x18002f00b  lea     rbp, [rsp-60h]
0x18002f010  sub     rsp, 160h
0x18002f017  mov     rax, cs:__security_cookie
0x18002f01e  xor     rax, rsp
0x18002f021  mov     [rbp+60h+var_10], rax
0x18002f025  mov     rdi, rcx
0x18002f028  mov     [rsp+160h+hKey], 0
0x18002f031  lea     rax, [rsp+160h+hKey]
0x18002f036  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18002f03d  mov     r9d, 20019h; samDesired
0x18002f043  mov     [rsp+160h+phkResult], rax; phkResult
0x18002f048  xor     r8d, r8d; ulOptions
0x18002f04b  lea     rdx, aClsidAdb880a6D; "CLSID\\{ADB880A6-D8FF-11CF-9377-00AA003"...
0x18002f052  call    cs:__imp_RegOpenKeyExA
0x18002f058  test    eax, eax
0x18002f05a  jnz     loc_18002F0F1
0x18002f060  mov     rcx, [rsp+160h+hKey]; hKey
0x18002f065  lea     rax, [rsp+160h+cbData]
0x18002f06a  mov     [rsp+160h+lpcbData], rax; lpcbData
0x18002f06f  lea     r9, [rsp+160h+Type]; lpType
0x18002f074  lea     rax, [rsp+160h+Data]
0x18002f079  mov     [rsp+160h+cbData], 104h
0x18002f081  xor     r8d, r8d; lpReserved
0x18002f084  mov     [rsp+160h+phkResult], rax; lpData
0x18002f089  xor     edx, edx; lpValueName
0x18002f08b  mov     [rsp+160h+Type], 1
0x18002f093  xor     ebx, ebx
0x18002f095  call    cs:__imp_RegQueryValueExA
0x18002f09b  test    eax, eax
0x18002f09d  jnz     short loc_18002F0E2
0x18002f09f  cmp     [rsp+160h+Type], 2
0x18002f0a4  mov     [rbp+60h+var_1D], bl
0x18002f0a7  jnz     short loc_18002F0C9
0x18002f0a9  mov     r8d, 104h; nSize
0x18002f0af  lea     rcx, [rsp+160h+Data]; lpSrc
0x18002f0b4  mov     rdx, rdi; lpDst
0x18002f0b7  call    cs:__imp_ExpandEnvironmentStringsA
0x18002f0bd  dec     eax
0x18002f0bf  cmp     eax, 103h
0x18002f0c4  setbe   bl
0x18002f0c7  jmp     short loc_18002F0E2
0x18002f0c9  lea     r8, [rsp+160h+Data]; char *
0x18002f0ce  mov     edx, 104h; unsigned __int64
0x18002f0d3  mov     rcx, rdi; char *
0x18002f0d6  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18002f0db  mov     ebx, eax
0x18002f0dd  not     ebx
0x18002f0df  shr     ebx, 1Fh
0x18002f0e2  mov     rcx, [rsp+160h+hKey]; hKey
0x18002f0e7  call    cs:__imp_RegCloseKey
0x18002f0ed  mov     eax, ebx
0x18002f0ef  jmp     short loc_18002F0F3
0x18002f0f1  xor     eax, eax
0x18002f0f3  mov     rcx, [rbp+60h+var_10]
0x18002f0f7  xor     rcx, rsp; StackCookie
0x18002f0fa  call    __security_check_cookie
0x18002f0ff  lea     r11, [rsp+160h+var_s0]
0x18002f107  mov     rbx, [r11+18h]
0x18002f10b  mov     rdi, [r11+20h]
0x18002f10f  mov     rsp, r11
0x18002f112  pop     rbp
0x18002f113  retn
```
