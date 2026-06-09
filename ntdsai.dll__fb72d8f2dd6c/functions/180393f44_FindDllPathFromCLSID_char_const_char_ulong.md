# FindDllPathFromCLSID(char const *,char *,ulong)

- ea: `0x180393f44`
- end: `0x1803940df`
- name: `?FindDllPathFromCLSID@@YAJPEBDPEADK@Z`
- size: `411`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey, BYTE *lpDst)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1803940e8`

## callees

- `0x18001e090`
- `0x180021aa3`
- `0x180393f44`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180393fc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180393fea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180394017`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180393fc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180393fea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180394017`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039409d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803940a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803940b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18039409d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803940a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1803940b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180394047`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180394047`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x18039408b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x18039408b`

## string_xrefs

- `0x180393f95`: `CLSID`

## pseudocode

```c
__int64 __fastcall FindDllPathFromCLSID(LPCSTR lpSubKey, BYTE *lpDst)
{
  unsigned int v4; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v10; // [rsp+48h] [rbp-B8h] BYREF
  CHAR Src[1024]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  phkResult = 0;
  v10 = 0;
  Type = 0;
  cbData = 0;
  if ( RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0x20019u, &hKey) )
    goto LABEL_9;
  if ( RegOpenKeyExA(hKey, lpSubKey, 0, 0x20019u, &phkResult) )
    goto LABEL_9;
  if ( RegOpenKeyExA(phkResult, "InProcServer32", 0, 0x20019u, &v10) )
    goto LABEL_9;
  cbData = 1024;
  if ( RegQueryValueExA(v10, 0, 0, &Type, lpDst, &cbData) )
    goto LABEL_9;
  v4 = 0;
  if ( Type != 1 )
  {
    if ( Type == 2 && cbData <= 0x400 )
    {
      memcpy_0(Src, lpDst, cbData);
      ExpandEnvironmentStringsA(Src, (LPSTR)lpDst, 0x400u);
      goto LABEL_10;
    }
LABEL_9:
    v4 = -2147467259;
  }
LABEL_10:
  RegCloseKey(hKey);
  RegCloseKey(phkResult);
  RegCloseKey(v10);
  return v4;
}

```

## disassembly

```asm
0x180393f44  mov     [rsp-8+arg_10], rbx
0x180393f49  mov     [rsp-8+arg_18], rdi
0x180393f4e  push    rbp
0x180393f4f  lea     rbp, [rsp-360h]
0x180393f57  sub     rsp, 460h
0x180393f5e  mov     rax, cs:__security_cookie
0x180393f65  xor     rax, rsp
0x180393f68  mov     [rbp+360h+var_10], rax
0x180393f6f  mov     rdi, rdx
0x180393f72  mov     [rsp+460h+hKey], 0
0x180393f7b  mov     rbx, rcx
0x180393f7e  mov     [rsp+460h+var_420], 0
0x180393f87  lea     rax, [rsp+460h+hKey]
0x180393f8c  mov     [rsp+460h+var_418], 0
0x180393f95  lea     rdx, aClsid; "CLSID"
0x180393f9c  mov     [rsp+460h+phkResult], rax; phkResult
0x180393fa1  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180393fa8  mov     [rsp+460h+Type], 0
0x180393fb0  mov     r9d, 20019h; samDesired
0x180393fb6  mov     [rsp+460h+cbData], 0
0x180393fbe  xor     r8d, r8d; ulOptions
0x180393fc1  call    cs:__imp_RegOpenKeyExA
0x180393fc7  test    eax, eax
0x180393fc9  jnz     loc_180394093
0x180393fcf  mov     rcx, [rsp+460h+hKey]; hKey
0x180393fd4  lea     rax, [rsp+460h+var_420]
0x180393fd9  mov     r9d, 20019h; samDesired
0x180393fdf  mov     [rsp+460h+phkResult], rax; phkResult
0x180393fe4  xor     r8d, r8d; ulOptions
0x180393fe7  mov     rdx, rbx; lpSubKey
0x180393fea  call    cs:__imp_RegOpenKeyExA
0x180393ff0  test    eax, eax
0x180393ff2  jnz     loc_180394093
0x180393ff8  mov     rcx, [rsp+460h+var_420]; hKey
0x180393ffd  lea     rax, [rsp+460h+var_418]
0x180394002  mov     r9d, 20019h; samDesired
0x180394008  mov     [rsp+460h+phkResult], rax; phkResult
0x18039400d  xor     r8d, r8d; ulOptions
0x180394010  lea     rdx, aInprocserver32; "InProcServer32"
0x180394017  call    cs:__imp_RegOpenKeyExA
0x18039401d  test    eax, eax
0x18039401f  jnz     short loc_180394093
0x180394021  mov     rcx, [rsp+460h+var_418]; hKey
0x180394026  lea     rax, [rsp+460h+cbData]
0x18039402b  mov     [rsp+460h+lpcbData], rax; lpcbData
0x180394030  lea     r9, [rsp+460h+Type]; lpType
0x180394035  xor     r8d, r8d; lpReserved
0x180394038  mov     [rsp+460h+phkResult], rdi; lpData
0x18039403d  xor     edx, edx; lpValueName
0x18039403f  mov     [rsp+460h+cbData], 400h
0x180394047  call    cs:__imp_RegQueryValueExA
0x18039404d  test    eax, eax
0x18039404f  jnz     short loc_180394093
0x180394051  mov     eax, [rsp+460h+Type]
0x180394055  xor     ebx, ebx
0x180394057  sub     eax, 1
0x18039405a  jz      short loc_180394098
0x18039405c  cmp     eax, 1
0x18039405f  jnz     short loc_180394093
0x180394061  cmp     [rsp+460h+cbData], 400h
0x180394069  ja      short loc_180394093
0x18039406b  mov     r8d, [rsp+460h+cbData]; Size
0x180394070  lea     rcx, [rsp+460h+Src]; void *
0x180394075  mov     rdx, rdi; Src
0x180394078  call    memcpy_0
0x18039407d  mov     r8d, 400h; nSize
0x180394083  lea     rcx, [rsp+460h+Src]; lpSrc
0x180394088  mov     rdx, rdi; lpDst
0x18039408b  call    cs:__imp_ExpandEnvironmentStringsA
0x180394091  jmp     short loc_180394098
0x180394093  mov     ebx, 80004005h
0x180394098  mov     rcx, [rsp+460h+hKey]; hKey
0x18039409d  call    cs:__imp_RegCloseKey
0x1803940a3  mov     rcx, [rsp+460h+var_420]; hKey
0x1803940a8  call    cs:__imp_RegCloseKey
0x1803940ae  mov     rcx, [rsp+460h+var_418]; hKey
0x1803940b3  call    cs:__imp_RegCloseKey
0x1803940b9  mov     eax, ebx
0x1803940bb  mov     rcx, [rbp+360h+var_10]
0x1803940c2  xor     rcx, rsp; StackCookie
0x1803940c5  call    __security_check_cookie
0x1803940ca  lea     r11, [rsp+460h+var_s0]
0x1803940d2  mov     rbx, [r11+20h]
0x1803940d6  mov     rdi, [r11+28h]
0x1803940da  mov     rsp, r11
0x1803940dd  pop     rbp
0x1803940de  retn
```
