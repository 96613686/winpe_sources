# WriteSymLinksOpts

- ea: `0x180010d8c`
- end: `0x180010eaf`
- name: `WriteSymLinksOpts`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, registry_config`

## callers

- `0x180010bec`

## callees

- `0x180010d8c`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180010dfe`
- `ADVAPI32!RegCreateKeyExW` at `0x180010dfe`
- `ADVAPI32!RegSetValueExW` at `0x180010e33`
- `ADVAPI32!RegSetValueExW` at `0x180010e5d`
- `ADVAPI32!RegSetValueExW` at `0x180010e87`
- `ADVAPI32!RegSetValueExW` at `0x180010e33`
- `ADVAPI32!RegSetValueExW` at `0x180010e5d`
- `ADVAPI32!RegSetValueExW` at `0x180010e87`
- `ADVAPI32!RegCloseKey` at `0x180010e97`
- `ADVAPI32!RegCloseKey` at `0x180010e97`

## string_xrefs

- `0x180010e2c`: `SymLinks`
- `0x180010e4b`: `DeleteSymlinks`
- `0x180010e75`: `DisplayAllLinks`

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
0x180010d8c  mov     [rsp-8+arg_0], rbx
0x180010d91  push    rbp
0x180010d92  mov     rbp, rsp
0x180010d95  sub     rsp, 60h
0x180010d99  mov     eax, [r8+38h]
0x180010d9d  xor     ebx, ebx
0x180010d9f  shr     eax, 9
0x180010da2  mov     [rbp+hKey], rbx
0x180010da6  mov     [rbp+dwDisposition], ebx
0x180010da9  lea     r9d, [rbx+1]
0x180010dad  mov     [rbp+arg_10], ebx
0x180010db0  and     eax, r9d
0x180010db3  mov     [rbp+arg_18], ebx
0x180010db6  test    dword ptr [r8+38h], 1000h
0x180010dbe  mov     dword ptr [rbp+Data], eax
0x180010dc1  jz      short loc_180010DC7
0x180010dc3  mov     [rbp+arg_10], r9d
0x180010dc7  test    dword ptr [r8+38h], 800h
0x180010dcf  jz      short loc_180010DD5
0x180010dd1  mov     [rbp+arg_18], r9d
0x180010dd5  lea     rax, [rbp+dwDisposition]
0x180010dd9  xor     r9d, r9d; lpClass
0x180010ddc  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180010de1  xor     r8d, r8d; Reserved
0x180010de4  lea     rax, [rbp+hKey]
0x180010de8  mov     [rsp+60h+phkResult], rax; phkResult
0x180010ded  mov     [rsp+60h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x180010df2  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x180010dfa  mov     [rsp+60h+dwOptions], ebx; dwOptions
0x180010dfe  call    cs:__imp_RegCreateKeyExW
0x180010e05  nop     dword ptr [rax+rax+00h]
0x180010e0a  test    eax, eax
0x180010e0c  jnz     loc_180010EA3
0x180010e12  mov     rcx, [rbp+hKey]; hKey
0x180010e16  lea     ebx, [rax+4]
0x180010e19  lea     rax, [rbp+Data]
0x180010e1d  mov     [rsp+60h+samDesired], ebx; cbData
0x180010e21  mov     r9d, ebx; dwType
0x180010e24  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180010e29  xor     r8d, r8d; Reserved
0x180010e2c  lea     rdx, aSymlinks; "SymLinks"
0x180010e33  call    cs:__imp_RegSetValueExW
0x180010e3a  nop     dword ptr [rax+rax+00h]
0x180010e3f  mov     rcx, [rbp+hKey]; hKey
0x180010e43  lea     rax, [rbp+arg_10]
0x180010e47  mov     [rsp+60h+samDesired], ebx; cbData
0x180010e4b  lea     rdx, aDeletesymlinks; "DeleteSymlinks"
0x180010e52  mov     r9d, ebx; dwType
0x180010e55  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180010e5a  xor     r8d, r8d; Reserved
0x180010e5d  call    cs:__imp_RegSetValueExW
0x180010e64  nop     dword ptr [rax+rax+00h]
0x180010e69  mov     rcx, [rbp+hKey]; hKey
0x180010e6d  lea     rax, [rbp+arg_18]
0x180010e71  mov     [rsp+60h+samDesired], ebx; cbData
0x180010e75  lea     rdx, aDisplayalllink; "DisplayAllLinks"
0x180010e7c  mov     r9d, ebx; dwType
0x180010e7f  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180010e84  xor     r8d, r8d; Reserved
0x180010e87  call    cs:__imp_RegSetValueExW
0x180010e8e  nop     dword ptr [rax+rax+00h]
0x180010e93  mov     rcx, [rbp+hKey]; hKey
0x180010e97  call    cs:__imp_RegCloseKey
0x180010e9e  nop     dword ptr [rax+rax+00h]
0x180010ea3  mov     rbx, [rsp+60h+arg_0]
0x180010ea8  add     rsp, 60h
0x180010eac  pop     rbp
0x180010ead  retn
```
