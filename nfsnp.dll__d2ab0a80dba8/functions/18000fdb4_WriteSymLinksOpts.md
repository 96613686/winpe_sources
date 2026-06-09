# WriteSymLinksOpts

- ea: `0x18000fdb4`
- end: `0x18000feb4`
- name: `WriteSymLinksOpts`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config`

## callers

- `0x18000fc20`

## callees

- `0x18000fdb4`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18000fe26`
- `ADVAPI32!RegCreateKeyExW` at `0x18000fe26`
- `ADVAPI32!RegSetValueExW` at `0x18000fe51`
- `ADVAPI32!RegSetValueExW` at `0x18000fe75`
- `ADVAPI32!RegSetValueExW` at `0x18000fe99`
- `ADVAPI32!RegSetValueExW` at `0x18000fe51`
- `ADVAPI32!RegSetValueExW` at `0x18000fe75`
- `ADVAPI32!RegSetValueExW` at `0x18000fe99`
- `ADVAPI32!RegCloseKey` at `0x18000fea3`
- `ADVAPI32!RegCloseKey` at `0x18000fea3`

## string_xrefs

- `0x18000fe4a`: `SymLinks`
- `0x18000fe63`: `DeleteSymlinks`
- `0x18000fe87`: `DisplayAllLinks`

## pseudocode

```c
LSTATUS __fastcall WriteSymLinksOpts(HKEY a1, const WCHAR *a2, __int64 a3)
{
  int v3; // eax
  bool v4; // zf
  LSTATUS result; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-10h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-Ch] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  BOOL v9; // [rsp+80h] [rbp+20h] BYREF
  BOOL v10; // [rsp+88h] [rbp+28h] BYREF

  v3 = *(_DWORD *)(a3 + 56) >> 9;
  hKey = 0;
  dwDisposition = 0;
  v10 = 0;
  v4 = (*(_DWORD *)(a3 + 56) & 0x1000) == 0;
  *(_DWORD *)Data = v3 & 1;
  v9 = !v4;
  v10 = (*(_DWORD *)(a3 + 56) & 0x800) != 0;
  result = RegCreateKeyExW(a1, a2, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
  if ( !result )
  {
    RegSetValueExW(hKey, L"SymLinks", 0, 4u, Data, 4u);
    RegSetValueExW(hKey, L"DeleteSymlinks", 0, 4u, (const BYTE *)&v9, 4u);
    RegSetValueExW(hKey, L"DisplayAllLinks", 0, 4u, (const BYTE *)&v10, 4u);
    return RegCloseKey(hKey);
  }
  return result;
}

```

## disassembly

```asm
0x18000fdb4  mov     [rsp-8+arg_0], rbx
0x18000fdb9  push    rbp
0x18000fdba  mov     rbp, rsp
0x18000fdbd  sub     rsp, 60h
0x18000fdc1  mov     eax, [r8+38h]
0x18000fdc5  xor     ebx, ebx
0x18000fdc7  shr     eax, 9
0x18000fdca  mov     [rbp+hKey], rbx
0x18000fdce  mov     [rbp+dwDisposition], ebx
0x18000fdd1  lea     r9d, [rbx+1]
0x18000fdd5  mov     [rbp+arg_10], ebx
0x18000fdd8  and     eax, r9d
0x18000fddb  mov     [rbp+arg_18], ebx
0x18000fdde  test    dword ptr [r8+38h], 1000h
0x18000fde6  mov     dword ptr [rbp+Data], eax
0x18000fde9  jz      short loc_18000FDEF
0x18000fdeb  mov     [rbp+arg_10], r9d
0x18000fdef  test    dword ptr [r8+38h], 800h
0x18000fdf7  jz      short loc_18000FDFD
0x18000fdf9  mov     [rbp+arg_18], r9d
0x18000fdfd  lea     rax, [rbp+dwDisposition]
0x18000fe01  xor     r9d, r9d; lpClass
0x18000fe04  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x18000fe09  xor     r8d, r8d; Reserved
0x18000fe0c  lea     rax, [rbp+hKey]
0x18000fe10  mov     [rsp+60h+phkResult], rax; phkResult
0x18000fe15  mov     [rsp+60h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18000fe1a  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x18000fe22  mov     [rsp+60h+dwOptions], ebx; dwOptions
0x18000fe26  call    cs:__imp_RegCreateKeyExW
0x18000fe2c  test    eax, eax
0x18000fe2e  jnz     short loc_18000FEA9
0x18000fe30  mov     rcx, [rbp+hKey]; hKey
0x18000fe34  lea     ebx, [rax+4]
0x18000fe37  lea     rax, [rbp+Data]
0x18000fe3b  mov     [rsp+60h+samDesired], ebx; cbData
0x18000fe3f  mov     r9d, ebx; dwType
0x18000fe42  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18000fe47  xor     r8d, r8d; Reserved
0x18000fe4a  lea     rdx, aSymlinks; "SymLinks"
0x18000fe51  call    cs:__imp_RegSetValueExW
0x18000fe57  mov     rcx, [rbp+hKey]; hKey
0x18000fe5b  lea     rax, [rbp+arg_10]
0x18000fe5f  mov     [rsp+60h+samDesired], ebx; cbData
0x18000fe63  lea     rdx, aDeletesymlinks; "DeleteSymlinks"
0x18000fe6a  mov     r9d, ebx; dwType
0x18000fe6d  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18000fe72  xor     r8d, r8d; Reserved
0x18000fe75  call    cs:__imp_RegSetValueExW
0x18000fe7b  mov     rcx, [rbp+hKey]; hKey
0x18000fe7f  lea     rax, [rbp+arg_18]
0x18000fe83  mov     [rsp+60h+samDesired], ebx; cbData
0x18000fe87  lea     rdx, aDisplayalllink; "DisplayAllLinks"
0x18000fe8e  mov     r9d, ebx; dwType
0x18000fe91  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x18000fe96  xor     r8d, r8d; Reserved
0x18000fe99  call    cs:__imp_RegSetValueExW
0x18000fe9f  mov     rcx, [rbp+hKey]; hKey
0x18000fea3  call    cs:__imp_RegCloseKey
0x18000fea9  mov     rbx, [rsp+60h+arg_0]
0x18000feae  add     rsp, 60h
0x18000feb2  pop     rbp
0x18000feb3  retn
```
