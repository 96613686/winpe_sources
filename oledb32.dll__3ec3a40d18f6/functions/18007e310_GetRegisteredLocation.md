# GetRegisteredLocation

- ea: `0x18007e310`
- end: `0x18007e424`
- name: `GetRegisteredLocation`
- size: `276`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007e42c`

## callees

- `0x18003fdf4`
- `0x18007e310`
- `0x18007e700`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsA` at `0x18007e3c7`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x18007e3c7`
- `ADVAPI32!RegOpenKeyExA` at `0x18007e362`
- `ADVAPI32!RegOpenKeyExA` at `0x18007e362`
- `ADVAPI32!RegQueryValueExA` at `0x18007e3a5`
- `ADVAPI32!RegQueryValueExA` at `0x18007e3a5`
- `ADVAPI32!RegCloseKey` at `0x18007e3f7`
- `ADVAPI32!RegCloseKey` at `0x18007e3f7`

## string_xrefs

- `0x18007e35b`: `CLSID\{ADB880A6-D8FF-11CF-9377-00AA003B7A11}\InprocServer32`

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
0x18007e310  mov     [rsp-8+arg_8], rbx
0x18007e315  mov     [rsp-8+arg_10], rdi
0x18007e31a  push    rbp
0x18007e31b  lea     rbp, [rsp-60h]
0x18007e320  sub     rsp, 160h
0x18007e327  mov     rax, cs:__security_cookie
0x18007e32e  xor     rax, rsp
0x18007e331  mov     [rbp+60h+var_10], rax
0x18007e335  mov     rdi, rcx
0x18007e338  mov     [rsp+160h+hKey], 0
0x18007e341  lea     rax, [rsp+160h+hKey]
0x18007e346  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18007e34d  mov     r9d, 20019h; samDesired
0x18007e353  mov     [rsp+160h+phkResult], rax; phkResult
0x18007e358  xor     r8d, r8d; ulOptions
0x18007e35b  lea     rdx, aClsidAdb880a6D; "CLSID\\{ADB880A6-D8FF-11CF-9377-00AA003"...
0x18007e362  call    cs:__imp_RegOpenKeyExA
0x18007e368  test    eax, eax
0x18007e36a  jnz     loc_18007E401
0x18007e370  mov     rcx, [rsp+160h+hKey]; hKey
0x18007e375  lea     rax, [rsp+160h+cbData]
0x18007e37a  mov     [rsp+160h+lpcbData], rax; lpcbData
0x18007e37f  lea     r9, [rsp+160h+Type]; lpType
0x18007e384  lea     rax, [rsp+160h+Data]
0x18007e389  mov     [rsp+160h+cbData], 104h
0x18007e391  xor     r8d, r8d; lpReserved
0x18007e394  mov     [rsp+160h+phkResult], rax; lpData
0x18007e399  xor     edx, edx; lpValueName
0x18007e39b  mov     [rsp+160h+Type], 1
0x18007e3a3  xor     ebx, ebx
0x18007e3a5  call    cs:__imp_RegQueryValueExA
0x18007e3ab  test    eax, eax
0x18007e3ad  jnz     short loc_18007E3F2
0x18007e3af  cmp     [rsp+160h+Type], 2
0x18007e3b4  mov     [rbp+60h+var_1D], bl
0x18007e3b7  jnz     short loc_18007E3D9
0x18007e3b9  mov     r8d, 104h; nSize
0x18007e3bf  lea     rcx, [rsp+160h+Data]; lpSrc
0x18007e3c4  mov     rdx, rdi; lpDst
0x18007e3c7  call    cs:__imp_ExpandEnvironmentStringsA
0x18007e3cd  dec     eax
0x18007e3cf  cmp     eax, 103h
0x18007e3d4  setbe   bl
0x18007e3d7  jmp     short loc_18007E3F2
0x18007e3d9  lea     r8, [rsp+160h+Data]; char *
0x18007e3de  mov     edx, 104h; unsigned __int64
0x18007e3e3  mov     rcx, rdi; char *
0x18007e3e6  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18007e3eb  mov     ebx, eax
0x18007e3ed  not     ebx
0x18007e3ef  shr     ebx, 1Fh
0x18007e3f2  mov     rcx, [rsp+160h+hKey]; hKey
0x18007e3f7  call    cs:__imp_RegCloseKey
0x18007e3fd  mov     eax, ebx
0x18007e3ff  jmp     short loc_18007E403
0x18007e401  xor     eax, eax
0x18007e403  mov     rcx, [rbp+60h+var_10]
0x18007e407  xor     rcx, rsp; StackCookie
0x18007e40a  call    __security_check_cookie
0x18007e40f  lea     r11, [rsp+160h+var_s0]
0x18007e417  mov     rbx, [r11+18h]
0x18007e41b  mov     rdi, [r11+20h]
0x18007e41f  mov     rsp, r11
0x18007e422  pop     rbp
0x18007e423  retn
```
