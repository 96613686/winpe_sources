# CopyValue

- ea: `0x140003c24`
- end: `0x140003e2e`
- name: `CopyValue`
- size: `522`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpValueName, HKEY, LPCWSTR, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400033d8`

## callees

- `0x140002b6c`
- `0x140002ce4`
- `0x140003c24`
- `0x14000ce50`
- `0x14000d2d0`
- `0x14000d610`
- `0x14000d694`
- `0x14000e600`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003c9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003cee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003d2e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003c9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003cee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003d2e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140003de0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140003de0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140003d66`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140003d66`

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
0x140003c24  push    rbp
0x140003c26  push    rbx
0x140003c27  push    rsi
0x140003c28  push    rdi
0x140003c29  push    r12
0x140003c2b  push    r13
0x140003c2d  push    r14
0x140003c2f  push    r15
0x140003c31  mov     rbp, rsp
0x140003c34  sub     rsp, 48h
0x140003c38  xor     r12d, r12d
0x140003c3b  mov     rsi, r9
0x140003c3e  mov     [rbp+Type], r12d
0x140003c42  mov     r13, r8
0x140003c45  mov     [rbp+cbData], r12d
0x140003c49  mov     r14, rdx
0x140003c4c  mov     r15, rcx
0x140003c4f  test    rcx, rcx
0x140003c52  jz      loc_140003E0E
0x140003c58  test    rdx, rdx
0x140003c5b  jz      loc_140003E0E
0x140003c61  test    r8, r8
0x140003c64  jz      loc_140003E0E
0x140003c6a  test    r9, r9
0x140003c6d  jz      loc_140003E0E
0x140003c73  mov     rdi, [rbp+arg_20]
0x140003c77  test    rdi, rdi
0x140003c7a  jz      loc_140003E0E
0x140003c80  cmp     [rbp+arg_28], r12
0x140003c84  jz      loc_140003E0E
0x140003c8a  lea     rax, [rbp+cbData]
0x140003c8e  xor     r8d, r8d; lpReserved
0x140003c91  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140003c96  lea     r9, [rbp+Type]; lpType
0x140003c9a  mov     [rsp+48h+lpData], r12; lpData
0x140003c9f  call    cs:__imp_RegQueryValueExW
0x140003ca6  nop     dword ptr [rax+rax+00h]
0x140003cab  mov     ebx, eax
0x140003cad  test    eax, eax
0x140003caf  jnz     loc_140003E13
0x140003cb5  mov     ecx, [rbp+cbData]
0x140003cb8  inc     ecx; dwBytes
0x140003cba  call    AllocateMemory
0x140003cbf  mov     [rbp+var_10], rax
0x140003cc3  mov     r12, rax
0x140003cc6  test    rax, rax
0x140003cc9  jnz     short loc_140003CD3
0x140003ccb  lea     ebx, [rax+0Eh]
0x140003cce  jmp     loc_140003E13
0x140003cd3  lea     rax, [rbp+cbData]
0x140003cd7  xor     r8d, r8d; lpReserved
0x140003cda  mov     [rsp+48h+lpcbData], rax; lpcbData
0x140003cdf  lea     r9, [rbp+Type]; lpType
0x140003ce3  mov     rdx, r14; lpValueName
0x140003ce6  mov     [rsp+48h+lpData], r12; lpData
0x140003ceb  mov     rcx, r15; hKey
0x140003cee  call    cs:__imp_RegQueryValueExW
0x140003cf5  nop     dword ptr [rax+rax+00h]
0x140003cfa  mov     ebx, eax
0x140003cfc  test    eax, eax
0x140003cfe  jz      short loc_140003D0E
0x140003d00  lea     rcx, [rbp+var_10]
0x140003d04  call    FreeMemory
0x140003d09  jmp     loc_140003E13
0x140003d0e  xor     ebx, ebx
0x140003d10  cmp     [rdi], ebx
0x140003d12  jnz     loc_140003DC7
0x140003d18  mov     [rsp+48h+lpcbData], rbx; lpcbData
0x140003d1d  xor     r9d, r9d; lpType
0x140003d20  xor     r8d, r8d; lpReserved
0x140003d23  mov     [rsp+48h+lpData], rbx; lpData
0x140003d28  mov     rdx, rsi; lpValueName
0x140003d2b  mov     rcx, r13; hKey
0x140003d2e  call    cs:__imp_RegQueryValueExW
0x140003d35  nop     dword ptr [rax+rax+00h]
0x140003d3a  test    eax, eax
0x140003d3c  jnz     loc_140003DC7
0x140003d42  xor     r8d, r8d
0x140003d45  mov     edx, 0CBh
0x140003d4a  call    GetResString2FromModule
0x140003d4f  mov     edx, 0CEh
0x140003d54  lea     r8d, [rbx+1]
0x140003d58  mov     r14, rax
0x140003d5b  call    GetResString2FromModule
0x140003d60  mov     rcx, rsi; lpString
0x140003d63  mov     r15, rax
0x140003d66  call    cs:__imp_lstrlenW
0x140003d6d  nop     dword ptr [rax+rax+00h]
0x140003d72  test    eax, eax
0x140003d74  jnz     short loc_140003D86
0x140003d76  mov     edx, 1F5h
0x140003d7b  lea     r8d, [rbx+2]
0x140003d7f  call    GetResString2FromModule
0x140003d84  jmp     short loc_140003D89
0x140003d86  mov     rax, rsi
0x140003d89  mov     r8, [rbp+arg_28]
0x140003d8d  lea     rdx, aSS; "%s\\%s"
0x140003d94  mov     r9, rax
0x140003d97  mov     ecx, 2
0x140003d9c  call    SetReason2
0x140003da1  call    GetReason
0x140003da6  mov     rbx, rax
0x140003da9  mov     r9d, [rdi]
0x140003dac  mov     r8, r15
0x140003daf  mov     rdx, rbx
0x140003db2  mov     rcx, r14
0x140003db5  call    Prompt
0x140003dba  cmp     eax, 3
0x140003dbd  jg      short loc_140003DA9
0x140003dbf  jnz     short loc_140003DF9
0x140003dc1  mov     dword ptr [rdi], 1
0x140003dc7  mov     eax, [rbp+cbData]
0x140003dca  xor     r8d, r8d; Reserved
0x140003dcd  mov     r9d, [rbp+Type]; dwType
0x140003dd1  mov     rdx, rsi; lpValueName
0x140003dd4  mov     dword ptr [rsp+48h+lpcbData], eax; cbData
0x140003dd8  mov     rcx, r13; hKey
0x140003ddb  mov     [rsp+48h+lpData], r12; lpData
0x140003de0  call    cs:__imp_RegSetValueExW
0x140003de7  nop     dword ptr [rax+rax+00h]
0x140003dec  lea     rcx, [rbp+var_10]
0x140003df0  mov     ebx, eax
0x140003df2  call    FreeMemory
0x140003df7  jmp     short loc_140003E1A
0x140003df9  cmp     eax, 1
0x140003dfc  jz      short loc_140003DC7
0x140003dfe  lea     rcx, [rbp+var_10]
0x140003e02  call    FreeMemory
0x140003e07  mov     ebx, 4C7h
0x140003e0c  jmp     short loc_140003E13
0x140003e0e  mov     ebx, 57h ; 'W'
0x140003e13  mov     ecx, ebx
0x140003e15  call    SaveErrorMessage
0x140003e1a  mov     eax, ebx
0x140003e1c  add     rsp, 48h
0x140003e20  pop     r15
0x140003e22  pop     r14
0x140003e24  pop     r13
0x140003e26  pop     r12
0x140003e28  pop     rdi
0x140003e29  pop     rsi
0x140003e2a  pop     rbx
0x140003e2b  pop     rbp
0x140003e2c  retn
```
