# GetRegisteredLocation

- ea: `0x18003e22c`
- end: `0x18003e340`
- name: `GetRegisteredLocation`
- size: `276`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003e348`

## callees

- `0x1800129d0`
- `0x18003e22c`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003e27e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003e27e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003e2c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18003e2c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e313`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e313`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x18003e2e3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x18003e2e3`

## string_xrefs

- `0x18003e277`: `CLSID\{ADB880A6-D8FF-11CF-9377-00AA003B7A11}\InprocServer32`

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
0x18003e22c  mov     [rsp-8+arg_8], rbx
0x18003e231  mov     [rsp-8+arg_10], rdi
0x18003e236  push    rbp
0x18003e237  lea     rbp, [rsp-60h]
0x18003e23c  sub     rsp, 160h
0x18003e243  mov     rax, cs:__security_cookie
0x18003e24a  xor     rax, rsp
0x18003e24d  mov     [rbp+60h+var_10], rax
0x18003e251  mov     rdi, rcx
0x18003e254  mov     [rsp+160h+hKey], 0
0x18003e25d  lea     rax, [rsp+160h+hKey]
0x18003e262  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18003e269  mov     r9d, 20019h; samDesired
0x18003e26f  mov     [rsp+160h+phkResult], rax; phkResult
0x18003e274  xor     r8d, r8d; ulOptions
0x18003e277  lea     rdx, aClsidAdb880a6D; "CLSID\\{ADB880A6-D8FF-11CF-9377-00AA003"...
0x18003e27e  call    cs:__imp_RegOpenKeyExA
0x18003e284  test    eax, eax
0x18003e286  jnz     loc_18003E31D
0x18003e28c  mov     rcx, [rsp+160h+hKey]; hKey
0x18003e291  lea     rax, [rsp+160h+cbData]
0x18003e296  mov     [rsp+160h+lpcbData], rax; lpcbData
0x18003e29b  lea     r9, [rsp+160h+Type]; lpType
0x18003e2a0  lea     rax, [rsp+160h+Data]
0x18003e2a5  mov     [rsp+160h+cbData], 104h
0x18003e2ad  xor     r8d, r8d; lpReserved
0x18003e2b0  mov     [rsp+160h+phkResult], rax; lpData
0x18003e2b5  xor     edx, edx; lpValueName
0x18003e2b7  mov     [rsp+160h+Type], 1
0x18003e2bf  xor     ebx, ebx
0x18003e2c1  call    cs:__imp_RegQueryValueExA
0x18003e2c7  test    eax, eax
0x18003e2c9  jnz     short loc_18003E30E
0x18003e2cb  cmp     [rsp+160h+Type], 2
0x18003e2d0  mov     [rbp+60h+var_1D], bl
0x18003e2d3  jnz     short loc_18003E2F5
0x18003e2d5  mov     r8d, 104h; nSize
0x18003e2db  lea     rcx, [rsp+160h+Data]; lpSrc
0x18003e2e0  mov     rdx, rdi; lpDst
0x18003e2e3  call    cs:__imp_ExpandEnvironmentStringsA
0x18003e2e9  dec     eax
0x18003e2eb  cmp     eax, 103h
0x18003e2f0  setbe   bl
0x18003e2f3  jmp     short loc_18003E30E
0x18003e2f5  lea     r8, [rsp+160h+Data]; char *
0x18003e2fa  mov     edx, 104h; unsigned __int64
0x18003e2ff  mov     rcx, rdi; char *
0x18003e302  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18003e307  mov     ebx, eax
0x18003e309  not     ebx
0x18003e30b  shr     ebx, 1Fh
0x18003e30e  mov     rcx, [rsp+160h+hKey]; hKey
0x18003e313  call    cs:__imp_RegCloseKey
0x18003e319  mov     eax, ebx
0x18003e31b  jmp     short loc_18003E31F
0x18003e31d  xor     eax, eax
0x18003e31f  mov     rcx, [rbp+60h+var_10]
0x18003e323  xor     rcx, rsp; StackCookie
0x18003e326  call    __security_check_cookie
0x18003e32b  lea     r11, [rsp+160h+var_s0]
0x18003e333  mov     rbx, [r11+18h]
0x18003e337  mov     rdi, [r11+20h]
0x18003e33b  mov     rsp, r11
0x18003e33e  pop     rbp
0x18003e33f  retn
```
