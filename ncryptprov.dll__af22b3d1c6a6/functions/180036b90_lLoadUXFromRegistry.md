# lLoadUXFromRegistry

- ea: `0x180036b90`
- end: `0x180036d33`
- name: `lLoadUXFromRegistry`
- size: `419`
- prototype: `__int64 __fastcall(HMODULE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005ed0c`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x180036b90`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180036cbb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180036cbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036ccc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036bf8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036bf8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036d03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036d03`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036c3b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036c98`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036c3b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180036c98`

## string_xrefs

- `0x180036bc6`: `onecore\ds\security\cryptoapi\ncrypt\storage\prompt.c`

## pseudocode

```c
__int64 __fastcall lLoadUXFromRegistry(HMODULE *a1)
{
  BYTE *v1; // rdi
  __int64 v3; // r9
  unsigned int v4; // ebx
  __int64 v5; // rcx
  HMODULE Library; // rax
  signed int LastError; // eax
  DWORD cbData; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  hKey = 0;
  cbData = 0;
  if ( !a1 )
  {
    v3 = 69;
    v4 = -2146893785;
    v5 = 2148073511LL;
LABEL_3:
    DebugTraceError(v5, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\prompt.c", v3);
    goto LABEL_18;
  }
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Control\\Cryptography\\Providers\\Microsoft Software Key Storage Provider\\Properties",
         0,
         0x20019u,
         &hKey) )
  {
    v3 = 84;
LABEL_6:
    v4 = -2146893794;
    v5 = 2148073502LL;
    goto LABEL_3;
  }
  if ( RegQueryValueExW(hKey, L"UXImage", 0, 0, 0, &cbData) )
  {
    v3 = 97;
    goto LABEL_6;
  }
  v1 = (BYTE *)SafeAllocaAllocateFromHeap(cbData);
  if ( !v1 )
  {
    v4 = -2146893810;
    v3 = 105;
    v5 = 2148073486LL;
    goto LABEL_3;
  }
  if ( RegQueryValueExW(hKey, L"UXImage", 0, 0, v1, &cbData) )
  {
    v3 = 118;
    goto LABEL_6;
  }
  Library = LoadLibraryExW((LPCWSTR)v1, 0, 0);
  if ( !Library )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v3 = 127;
    v5 = v4;
    goto LABEL_3;
  }
  *a1 = Library;
  v4 = 0;
LABEL_18:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v1 )
    MSCryptFree(v1);
  return v4;
}

```

## disassembly

```asm
0x180036b90  mov     [rsp+arg_10], rbx
0x180036b95  push    rdi
0x180036b96  sub     rsp, 30h
0x180036b9a  xor     edi, edi
0x180036b9c  mov     [rsp+38h+hKey], 0
0x180036ba5  mov     [rsp+38h+cbData], edi
0x180036ba9  mov     rbx, rcx
0x180036bac  test    rcx, rcx
0x180036baf  jnz     short loc_180036BD7
0x180036bb1  lea     r9d, [rcx+45h]
0x180036bb5  mov     ebx, 80090027h
0x180036bba  mov     ecx, 80090027h
0x180036bbf  lea     rdx, aStatus; "Status"
0x180036bc6  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180036bcd  call    DebugTraceError
0x180036bd2  jmp     loc_180036CF9
0x180036bd7  lea     rax, [rsp+38h+hKey]
0x180036bdc  mov     r9d, 20019h; samDesired
0x180036be2  xor     r8d, r8d; ulOptions
0x180036be5  mov     [rsp+38h+phkResult], rax; phkResult
0x180036bea  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Cry"...
0x180036bf1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180036bf8  call    cs:__imp_RegOpenKeyExW
0x180036bff  nop     dword ptr [rax+rax+00h]
0x180036c04  test    eax, eax
0x180036c06  jz      short loc_180036C1A
0x180036c08  mov     r9d, 54h ; 'T'
0x180036c0e  mov     ebx, 8009001Eh
0x180036c13  mov     ecx, 8009001Eh
0x180036c18  jmp     short loc_180036BBF
0x180036c1a  mov     rcx, [rsp+38h+hKey]; hKey
0x180036c1f  lea     rax, [rsp+38h+cbData]
0x180036c24  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180036c29  lea     rdx, aUximage; "UXImage"
0x180036c30  xor     r9d, r9d; lpType
0x180036c33  mov     [rsp+38h+phkResult], rdi; lpData
0x180036c38  xor     r8d, r8d; lpReserved
0x180036c3b  call    cs:__imp_RegQueryValueExW
0x180036c42  nop     dword ptr [rax+rax+00h]
0x180036c47  test    eax, eax
0x180036c49  jz      short loc_180036C53
0x180036c4b  mov     r9d, 61h ; 'a'
0x180036c51  jmp     short loc_180036C0E
0x180036c53  mov     ecx, [rsp+38h+cbData]
0x180036c57  call    SafeAllocaAllocateFromHeap
0x180036c5c  mov     rdi, rax
0x180036c5f  test    rax, rax
0x180036c62  jnz     short loc_180036C77
0x180036c64  mov     ebx, 8009000Eh
0x180036c69  lea     r9d, [rax+69h]
0x180036c6d  mov     ecx, 8009000Eh
0x180036c72  jmp     loc_180036BBF
0x180036c77  mov     rcx, [rsp+38h+hKey]; hKey
0x180036c7c  lea     rax, [rsp+38h+cbData]
0x180036c81  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180036c86  lea     rdx, aUximage; "UXImage"
0x180036c8d  xor     r9d, r9d; lpType
0x180036c90  mov     [rsp+38h+phkResult], rdi; lpData
0x180036c95  xor     r8d, r8d; lpReserved
0x180036c98  call    cs:__imp_RegQueryValueExW
0x180036c9f  nop     dword ptr [rax+rax+00h]
0x180036ca4  test    eax, eax
0x180036ca6  jz      short loc_180036CB3
0x180036ca8  mov     r9d, 76h ; 'v'
0x180036cae  jmp     loc_180036C0E
0x180036cb3  xor     r8d, r8d; dwFlags
0x180036cb6  xor     edx, edx; hFile
0x180036cb8  mov     rcx, rdi; lpLibFileName
0x180036cbb  call    cs:__imp_LoadLibraryExW
0x180036cc2  nop     dword ptr [rax+rax+00h]
0x180036cc7  test    rax, rax
0x180036cca  jnz     short loc_180036CF4
0x180036ccc  call    cs:__imp_GetLastError
0x180036cd3  nop     dword ptr [rax+rax+00h]
0x180036cd8  mov     ebx, eax
0x180036cda  test    eax, eax
0x180036cdc  jle     short loc_180036CE7
0x180036cde  movzx   ebx, ax
0x180036ce1  or      ebx, 80070000h
0x180036ce7  mov     r9d, 7Fh
0x180036ced  mov     ecx, ebx
0x180036cef  jmp     loc_180036BBF
0x180036cf4  mov     [rbx], rax
0x180036cf7  xor     ebx, ebx
0x180036cf9  mov     rcx, [rsp+38h+hKey]; hKey
0x180036cfe  test    rcx, rcx
0x180036d01  jz      short loc_180036D18
0x180036d03  call    cs:__imp_RegCloseKey
0x180036d0a  nop     dword ptr [rax+rax+00h]
0x180036d0f  mov     [rsp+38h+hKey], 0
0x180036d18  test    rdi, rdi
0x180036d1b  jz      short loc_180036D25
0x180036d1d  mov     rcx, rdi
0x180036d20  call    MSCryptFree
0x180036d25  mov     eax, ebx
0x180036d27  mov     rbx, [rsp+38h+arg_10]
0x180036d2c  add     rsp, 30h
0x180036d30  pop     rdi
0x180036d31  retn
```
