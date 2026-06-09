# CopyValue

- ea: `0x140003a58`
- end: `0x140003c3f`
- name: `CopyValue`
- size: `487`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, HKEY, LPCWSTR, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000329c`

## callees

- `0x140002a28`
- `0x140002b70`
- `0x140003a58`
- `0x14000c62c`
- `0x14000c9c0`
- `0x14000ccc4`
- `0x14000cd48`
- `0x14000daa4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003ad3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003b1c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003b56`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003ad3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003b1c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003b56`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140003bf8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140003bf8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140003b84`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140003b84`

## pseudocode

```c
__int64 __fastcall CopyValue(HKEY hKey, LPCWSTR lpValueName, HKEY a3, LPCWSTR a4, _DWORD *a5, __int64 a6)
{
  _DWORD *v10; // rdi
  unsigned int v11; // ebx
  const BYTE *v12; // r12
  __int64 v13; // rcx
  const WCHAR *ResString2FromModule; // r14
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  DWORD Type; // [rsp+30h] [rbp-18h] BYREF
  LPBYTE lpData[2]; // [rsp+38h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+48h] BYREF

  Type = 0;
  cbData = 0;
  if ( !hKey || !lpValueName || !a3 || !a4 || (v10 = a5) == 0 || !a6 )
  {
    v11 = 87;
    goto LABEL_24;
  }
  v11 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
  if ( v11 )
  {
LABEL_24:
    SaveErrorMessage(v11);
    return v11;
  }
  lpData[0] = (LPBYTE)AllocateMemory(cbData + 1);
  v12 = lpData[0];
  if ( !lpData[0] )
  {
    v11 = 14;
    goto LABEL_24;
  }
  v11 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData[0], &cbData);
  if ( v11 )
  {
    FreeMemory(lpData);
    goto LABEL_24;
  }
  if ( !*v10 && !RegQueryValueExW(a3, a4, 0, 0, 0, 0) )
  {
    ResString2FromModule = (const WCHAR *)GetResString2FromModule(v13, 203, 0);
    GetResString2FromModule(v15, 206, 1);
    if ( !lstrlenW(a4) )
      GetResString2FromModule(v16, 501, 2);
    SetReason2(2, L"%s\\%s", a6);
    GetReason();
    do
      v17 = Prompt(ResString2FromModule);
    while ( v17 > 3 );
    if ( v17 == 3 )
    {
      *v10 = 1;
    }
    else if ( v17 != 1 )
    {
      FreeMemory(lpData);
      v11 = 1223;
      goto LABEL_24;
    }
  }
  v11 = RegSetValueExW(a3, a4, 0, Type, v12, cbData);
  FreeMemory(lpData);
  return v11;
}

```

## disassembly

```asm
0x140003a58  push    rbp
0x140003a5a  push    rbx
0x140003a5b  push    rsi
0x140003a5c  push    rdi
0x140003a5d  push    r12
0x140003a5f  push    r13
0x140003a61  push    r14
0x140003a63  push    r15
0x140003a65  mov     rbp, rsp
0x140003a68  sub     rsp, 48h
0x140003a6c  xor     r12d, r12d
0x140003a6f  mov     rsi, r9
0x140003a72  mov     [rbp+Type], r12d
0x140003a76  mov     r13, r8
0x140003a79  mov     [rbp+cbData], r12d
0x140003a7d  mov     r14, rdx
0x140003a80  mov     r15, rcx
0x140003a83  test    rcx, rcx
0x140003a86  jz      loc_140003C20
0x140003a8c  test    rdx, rdx
0x140003a8f  jz      loc_140003C20
0x140003a95  test    r8, r8
0x140003a98  jz      loc_140003C20
0x140003a9e  test    r9, r9
0x140003aa1  jz      loc_140003C20
0x140003aa7  mov     rdi, [rbp+arg_20]
0x140003aab  test    rdi, rdi
0x140003aae  jz      loc_140003C20
0x140003ab4  cmp     [rbp+arg_28], r12
0x140003ab8  jz      loc_140003C20
0x140003abe  lea     rax, [rbp+cbData]
0x140003ac2  xor     r8d, r8d; lpReserved
0x140003ac5  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140003aca  lea     r9, [rbp+Type]; lpType
0x140003ace  mov     [rsp+48h+lpData], r12; lpData
0x140003ad3  call    cs:__imp_RegQueryValueExW
0x140003ad9  mov     ebx, eax
0x140003adb  test    eax, eax
0x140003add  jnz     loc_140003C25
0x140003ae3  mov     ecx, [rbp+cbData]
0x140003ae6  inc     ecx; dwBytes
0x140003ae8  call    AllocateMemory
0x140003aed  mov     [rbp+var_10], rax
0x140003af1  mov     r12, rax
0x140003af4  test    rax, rax
0x140003af7  jnz     short loc_140003B01
0x140003af9  lea     ebx, [rax+0Eh]
0x140003afc  jmp     loc_140003C25
0x140003b01  lea     rax, [rbp+cbData]
0x140003b05  xor     r8d, r8d; lpReserved
0x140003b08  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140003b0d  lea     r9, [rbp+Type]; lpType
0x140003b11  mov     rdx, r14; lpValueName
0x140003b14  mov     [rsp+48h+lpData], r12; lpData
0x140003b19  mov     rcx, r15; hKey
0x140003b1c  call    cs:__imp_RegQueryValueExW
0x140003b22  mov     ebx, eax
0x140003b24  test    eax, eax
0x140003b26  jz      short loc_140003B36
0x140003b28  lea     rcx, [rbp+var_10]
0x140003b2c  call    FreeMemory
0x140003b31  jmp     loc_140003C25
0x140003b36  xor     ebx, ebx
0x140003b38  cmp     [rdi], ebx
0x140003b3a  jnz     loc_140003BDF
0x140003b40  mov     [rsp+48h+lpcbData], rbx; lpcbData
0x140003b45  xor     r9d, r9d; lpType
0x140003b48  xor     r8d, r8d; lpReserved
0x140003b4b  mov     [rsp+48h+lpData], rbx; lpData
0x140003b50  mov     rdx, rsi; lpValueName
0x140003b53  mov     rcx, r13; hKey
0x140003b56  call    cs:__imp_RegQueryValueExW
0x140003b5c  test    eax, eax
0x140003b5e  jnz     short loc_140003BDF
0x140003b60  xor     r8d, r8d
0x140003b63  mov     edx, 0CBh
0x140003b68  call    GetResString2FromModule
0x140003b6d  mov     edx, 0CEh
0x140003b72  lea     r8d, [rbx+1]
0x140003b76  mov     r14, rax
0x140003b79  call    GetResString2FromModule
0x140003b7e  mov     rcx, rsi; lpString
0x140003b81  mov     r15, rax
0x140003b84  call    cs:__imp_lstrlenW
0x140003b8a  test    eax, eax
0x140003b8c  jnz     short loc_140003B9E
0x140003b8e  mov     edx, 1F5h
0x140003b93  lea     r8d, [rbx+2]
0x140003b97  call    GetResString2FromModule
0x140003b9c  jmp     short loc_140003BA1
0x140003b9e  mov     rax, rsi
0x140003ba1  mov     r8, [rbp+arg_28]
0x140003ba5  lea     rdx, aSS; "%s\\%s"
0x140003bac  mov     r9, rax
0x140003baf  mov     ecx, 2
0x140003bb4  call    SetReason2
0x140003bb9  call    GetReason
0x140003bbe  mov     rbx, rax
0x140003bc1  mov     r9d, [rdi]
0x140003bc4  mov     r8, r15
0x140003bc7  mov     rdx, rbx
0x140003bca  mov     rcx, r14
0x140003bcd  call    Prompt
0x140003bd2  cmp     eax, 3
0x140003bd5  jg      short loc_140003BC1
0x140003bd7  jnz     short loc_140003C0B
0x140003bd9  mov     dword ptr [rdi], 1
0x140003bdf  mov     eax, [rbp+cbData]
0x140003be2  xor     r8d, r8d; Reserved
0x140003be5  mov     r9d, [rbp+Type]; dwType
0x140003be9  mov     rdx, rsi; lpValueName
0x140003bec  mov     dword ptr [rsp+48h+lpcbData], eax; cbData
0x140003bf0  mov     rcx, r13; hKey
0x140003bf3  mov     [rsp+48h+lpData], r12; lpData
0x140003bf8  call    cs:__imp_RegSetValueExW
0x140003bfe  lea     rcx, [rbp+var_10]
0x140003c02  mov     ebx, eax
0x140003c04  call    FreeMemory
0x140003c09  jmp     short loc_140003C2C
0x140003c0b  cmp     eax, 1
0x140003c0e  jz      short loc_140003BDF
0x140003c10  lea     rcx, [rbp+var_10]
0x140003c14  call    FreeMemory
0x140003c19  mov     ebx, 4C7h
0x140003c1e  jmp     short loc_140003C25
0x140003c20  mov     ebx, 57h ; 'W'
0x140003c25  mov     ecx, ebx
0x140003c27  call    SaveErrorMessage
0x140003c2c  mov     eax, ebx
0x140003c2e  add     rsp, 48h
0x140003c32  pop     r15
0x140003c34  pop     r14
0x140003c36  pop     r13
0x140003c38  pop     r12
0x140003c3a  pop     rdi
0x140003c3b  pop     rsi
0x140003c3c  pop     rbx
0x140003c3d  pop     rbp
0x140003c3e  retn
```
