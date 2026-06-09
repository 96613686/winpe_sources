# QueryEnumKeys

- ea: `0x140005910`
- end: `0x140005c6f`
- name: `QueryEnumKeys`
- size: `863`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x140005910`
- `0x140005ef0`

## callees

- `0x140001bb2`
- `0x140001cc6`
- `0x140002ce4`
- `0x140005910`
- `0x140005c78`
- `0x1400064b0`
- `0x14000ce50`
- `0x14000d2d0`
- `0x14000ec2c`
- `0x14000ef5c`
- `0x14000f0c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140005bdd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140005bdd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140005acd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140005acd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005c0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140005c0c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140005a00`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140005a00`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140005a5c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x140005a5c`

## pseudocode

```c
__int64 __fastcall QueryEnumKeys(HKEY a1, _WORD *a2, __int64 a3, _DWORD *a4)
{
  unsigned int EnumValues; // ebx
  unsigned int v9; // eax
  __int64 v10; // rcx
  DWORD v11; // ecx
  void *v12; // r14
  int v13; // eax
  _WORD *v14; // r12
  DWORD i; // r15d
  int v16; // eax
  bool v17; // zf
  FILE *v18; // rax
  DWORD cSubKeys; // [rsp+60h] [rbp-9h] BYREF
  DWORD cchName; // [rsp+64h] [rbp-5h] BYREF
  DWORD v22; // [rsp+68h] [rbp-1h]
  HKEY hKey; // [rsp+70h] [rbp+7h] BYREF
  LPVOID Memory; // [rsp+78h] [rbp+Fh] BYREF
  LPVOID v25[8]; // [rsp+80h] [rbp+17h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+D0h] [rbp+67h] BYREF
  _WORD *v27; // [rsp+D8h] [rbp+6Fh]

  v27 = a2;
  cchName = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  hKey = 0;
  Memory = 0;
  v25[0] = 0;
  if ( !a1 || !a2 || !a3 || !a4 )
  {
    EnumValues = 87;
    goto LABEL_47;
  }
  if ( a4[1] != 1 )
  {
LABEL_9:
    if ( *(_DWORD *)(a3 + 112) == 1 && (a4[1] != 1 || !*(_QWORD *)(a3 + 96) && !*(_QWORD *)(a3 + 128)) )
      goto LABEL_14;
    goto LABEL_13;
  }
  if ( *(_DWORD *)(a3 + 112) == 1 )
  {
    if ( !*(_QWORD *)(a3 + 96) && !*(_QWORD *)(a3 + 128) )
      goto LABEL_14;
    goto LABEL_9;
  }
LABEL_13:
  EnumValues = QueryEnumValues(a1, (__int64)a2, a3, a4);
  if ( EnumValues )
    goto LABEL_49;
LABEL_14:
  v9 = RegQueryInfoKeyW(a1, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  EnumValues = v9;
  if ( v9 )
  {
    v10 = v9;
LABEL_48:
    SaveErrorMessage(v10);
    goto LABEL_49;
  }
  v11 = cbMaxSubKeyLen;
  if ( !cSubKeys || cbMaxSubKeyLen )
  {
    if ( cbMaxSubKeyLen < 0x100 )
      v11 = 2 * cbMaxSubKeyLen;
  }
  else
  {
    v11 = 256;
  }
  cbMaxSubKeyLen = v11 + 1;
  Memory = AllocateMemory(2 * (v11 + 1));
  v12 = Memory;
  if ( !Memory
    || (v13 = lstrlenW(a2), v22 = cbMaxSubKeyLen + 1 + v13, v25[0] = AllocateMemory(2 * v22), (v14 = v25[0]) == 0) )
  {
    EnumValues = 14;
LABEL_47:
    v10 = EnumValues;
    goto LABEL_48;
  }
  EnumValues = 0;
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = cbMaxSubKeyLen;
    memset_0(v12, 0, 2LL * cbMaxSubKeyLen);
    EnumValues = RegEnumKeyExW(a1, i, (LPWSTR)v12, &cchName, 0, 0, 0, 0);
    if ( !EnumValues )
    {
      a4[3] = 0;
      a4[1] = 1;
      if ( (*(_BYTE *)(a3 + 112) & 1) != 0 )
      {
        v16 = SearchData((LPCWSTR)v12);
        a4[1] = v16;
        if ( v16 )
        {
          a4[3] = 1;
        }
        else if ( !*(_DWORD *)(a3 + 32) && *(_DWORD *)(a3 + 112) == 1 )
        {
          continue;
        }
      }
      else if ( *(_DWORD *)(a3 + 112) || *(_QWORD *)(a3 + 96) )
      {
        a4[1] = 0;
      }
      StringCopyW(v14, v27, v22);
      StringConcatW(v14, L"\\", v22);
      StringConcatW(v14, v12, v22);
      v17 = a4[1] == 1;
      *a4 = 1;
      if ( v17 && !*(_QWORD *)(a3 + 96) && !*(_QWORD *)(a3 + 128) )
      {
        ++a4[4];
        a4[3] = 0;
        *a4 = 0;
        v18 = o___acrt_iob_func_0(1u);
        ShowMessageEx(v18, 1, 1, L"%s\n", v14);
      }
      if ( *(_DWORD *)(a3 + 32) != 1 )
        continue;
      if ( !RegOpenKeyExW(a1, (LPCWSTR)v12, 0, *(_DWORD *)(a3 + 140) | 0x20019, &hKey) )
      {
        EnumValues = QueryEnumKeys(hKey, v14, a3, a4);
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
        continue;
      }
    }
    EnumValues = 0;
  }
LABEL_49:
  FreeMemory(&Memory);
  FreeMemory(v25);
  return EnumValues;
}

```

## disassembly

```asm
0x140005910  mov     [rsp-8+arg_10], rbx
0x140005915  mov     [rsp-8+arg_8], rdx
0x14000591a  push    rbp
0x14000591b  push    rsi
0x14000591c  push    rdi
0x14000591d  push    r12
0x14000591f  push    r13
0x140005921  push    r14
0x140005923  push    r15
0x140005925  lea     rbp, [rsp-27h]
0x14000592a  sub     rsp, 90h
0x140005931  xor     r12d, r12d
0x140005934  mov     rsi, r9
0x140005937  mov     [rbp+57h+cchName], r12d
0x14000593b  mov     rdi, r8
0x14000593e  mov     [rbp+57h+cSubKeys], r12d
0x140005942  mov     r15, rdx
0x140005945  mov     [rbp+57h+cbMaxSubKeyLen], r12d
0x140005949  mov     r13, rcx
0x14000594c  mov     [rbp+57h+hKey], r12
0x140005950  mov     [rbp+57h+var_48], r12
0x140005954  mov     [rbp+57h+var_40], r12
0x140005958  test    rcx, rcx
0x14000595b  jz      loc_140005C33
0x140005961  test    rdx, rdx
0x140005964  jz      loc_140005C33
0x14000596a  test    r8, r8
0x14000596d  jz      loc_140005C33
0x140005973  test    r9, r9
0x140005976  jz      loc_140005C33
0x14000597c  cmp     dword ptr [r9+4], 1
0x140005981  jnz     short loc_140005999
0x140005983  cmp     dword ptr [r8+70h], 1
0x140005988  jnz     short loc_1400059B6
0x14000598a  cmp     [r8+60h], r12
0x14000598e  jnz     short loc_140005999
0x140005990  cmp     [r8+80h], r12
0x140005997  jz      short loc_1400059C5
0x140005999  cmp     dword ptr [r8+70h], 1
0x14000599e  jnz     short loc_1400059B6
0x1400059a0  cmp     dword ptr [r9+4], 1
0x1400059a5  jnz     short loc_1400059C5
0x1400059a7  cmp     [r8+60h], r12
0x1400059ab  jnz     short loc_1400059B6
0x1400059ad  cmp     [r8+80h], r12
0x1400059b4  jz      short loc_1400059C5
0x1400059b6  call    QueryEnumValues
0x1400059bb  mov     ebx, eax
0x1400059bd  test    eax, eax
0x1400059bf  jnz     loc_140005C3F
0x1400059c5  mov     [rsp+0C0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1400059ca  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1400059ce  mov     [rsp+0C0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x1400059d3  xor     r9d, r9d; lpReserved
0x1400059d6  mov     [rsp+0C0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x1400059db  xor     r8d, r8d; lpcchClass
0x1400059de  mov     [rsp+0C0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x1400059e3  xor     edx, edx; lpClass
0x1400059e5  mov     [rsp+0C0h+lpcValues], r12; lpcValues
0x1400059ea  mov     rcx, r13; hKey
0x1400059ed  mov     [rsp+0C0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x1400059f2  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1400059f7  lea     rax, [rbp+57h+cSubKeys]
0x1400059fb  mov     [rsp+0C0h+lpcSubKeys], rax; lpcSubKeys
0x140005a00  call    cs:__imp_RegQueryInfoKeyW
0x140005a07  nop     dword ptr [rax+rax+00h]
0x140005a0c  mov     ebx, eax
0x140005a0e  test    eax, eax
0x140005a10  jz      short loc_140005A19
0x140005a12  mov     ecx, eax
0x140005a14  jmp     loc_140005C3A
0x140005a19  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x140005a1c  cmp     [rbp+57h+cSubKeys], r12d
0x140005a20  jz      short loc_140005A2D
0x140005a22  test    ecx, ecx
0x140005a24  jnz     short loc_140005A2D
0x140005a26  mov     ecx, 100h
0x140005a2b  jmp     short loc_140005A37
0x140005a2d  cmp     ecx, 100h
0x140005a33  jnb     short loc_140005A37
0x140005a35  add     ecx, ecx
0x140005a37  inc     ecx
0x140005a39  mov     [rbp+57h+cbMaxSubKeyLen], ecx
0x140005a3c  add     ecx, ecx; dwBytes
0x140005a3e  call    AllocateMemory
0x140005a43  mov     [rbp+57h+var_48], rax
0x140005a47  mov     r14, rax
0x140005a4a  test    rax, rax
0x140005a4d  jnz     short loc_140005A59
0x140005a4f  mov     ebx, 0Eh
0x140005a54  jmp     loc_140005C38
0x140005a59  mov     rcx, r15; lpString
0x140005a5c  call    cs:__imp_lstrlenW
0x140005a63  nop     dword ptr [rax+rax+00h]
0x140005a68  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x140005a6b  inc     ecx
0x140005a6d  add     eax, ecx
0x140005a6f  mov     [rbp+57h+var_58], eax
0x140005a72  lea     ecx, [rax+rax]; dwBytes
0x140005a75  call    AllocateMemory
0x140005a7a  mov     [rbp+57h+var_40], rax
0x140005a7e  mov     r12, rax
0x140005a81  test    rax, rax
0x140005a84  jz      short loc_140005A4F
0x140005a86  xor     ebx, ebx
0x140005a88  xor     r15d, r15d
0x140005a8b  cmp     [rbp+57h+cSubKeys], ebx
0x140005a8e  jbe     loc_140005C3F
0x140005a94  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x140005a97  xor     edx, edx; Val
0x140005a99  mov     r8d, eax
0x140005a9c  mov     [rbp+57h+cchName], eax
0x140005a9f  add     r8, r8; Size
0x140005aa2  mov     rcx, r14; void *
0x140005aa5  call    memset_0
0x140005aaa  xor     eax, eax
0x140005aac  lea     r9, [rbp+57h+cchName]; lpcchName
0x140005ab0  mov     [rsp+0C0h+lpcValues], rax; lpftLastWriteTime
0x140005ab5  mov     r8, r14; lpName
0x140005ab8  mov     [rsp+0C0h+lpcbMaxClassLen], rax; lpcchClass
0x140005abd  mov     edx, r15d; dwIndex
0x140005ac0  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpClass
0x140005ac5  mov     rcx, r13; hKey
0x140005ac8  mov     [rsp+0C0h+lpcSubKeys], rax; lpReserved
0x140005acd  call    cs:__imp_RegEnumKeyExW
0x140005ad4  nop     dword ptr [rax+rax+00h]
0x140005ad9  xor     ecx, ecx
0x140005adb  mov     ebx, eax
0x140005add  test    eax, eax
0x140005adf  jnz     loc_140005C22
0x140005ae5  lea     eax, [rbx+1]
0x140005ae8  mov     [rsi+0Ch], ecx
0x140005aeb  mov     [rsi+4], eax
0x140005aee  test    [rdi+70h], al
0x140005af1  jz      short loc_140005B2A
0x140005af3  mov     r8d, [rbp+57h+cchName]
0x140005af7  mov     r9, rdi
0x140005afa  add     r8d, r8d
0x140005afd  mov     edx, eax
0x140005aff  mov     rcx, r14; lpString
0x140005b02  call    SearchData
0x140005b07  xor     ecx, ecx
0x140005b09  mov     [rsi+4], eax
0x140005b0c  test    eax, eax
0x140005b0e  jnz     short loc_140005B21
0x140005b10  cmp     [rdi+20h], ecx
0x140005b13  jnz     short loc_140005B38
0x140005b15  cmp     dword ptr [rdi+70h], 1
0x140005b19  jz      loc_140005C24
0x140005b1f  jmp     short loc_140005B38
0x140005b21  mov     dword ptr [rsi+0Ch], 1
0x140005b28  jmp     short loc_140005B38
0x140005b2a  cmp     [rdi+70h], ecx
0x140005b2d  jnz     short loc_140005B35
0x140005b2f  cmp     [rdi+60h], rcx
0x140005b33  jz      short loc_140005B38
0x140005b35  mov     [rsi+4], ecx
0x140005b38  mov     r8d, [rbp+57h+var_58]
0x140005b3c  mov     rcx, r12
0x140005b3f  mov     rdx, [rbp+57h+arg_8]
0x140005b43  call    StringCopyW
0x140005b48  mov     r8d, [rbp+57h+var_58]
0x140005b4c  lea     rdx, asc_14001181C; "\\"
0x140005b53  mov     rcx, r12
0x140005b56  call    StringConcatW
0x140005b5b  mov     r8d, [rbp+57h+var_58]
0x140005b5f  mov     rdx, r14
0x140005b62  mov     rcx, r12
0x140005b65  call    StringConcatW
0x140005b6a  cmp     dword ptr [rsi+4], 1
0x140005b6e  mov     dword ptr [rsi], 1
0x140005b74  jnz     short loc_140005BB7
0x140005b76  xor     ecx, ecx
0x140005b78  cmp     [rdi+60h], rcx
0x140005b7c  jnz     short loc_140005BB7
0x140005b7e  cmp     [rdi+80h], rcx
0x140005b85  jnz     short loc_140005BB7
0x140005b87  inc     dword ptr [rsi+10h]
0x140005b8a  mov     [rsi+0Ch], ecx
0x140005b8d  mov     [rsi], ecx
0x140005b8f  mov     ecx, 1; Ix
0x140005b94  call    _o___acrt_iob_func_0
0x140005b99  mov     rcx, rax
0x140005b9c  mov     [rsp+0C0h+lpcSubKeys], r12
0x140005ba1  mov     eax, 1
0x140005ba6  lea     r9, aS_5; "%s\n"
0x140005bad  mov     r8d, eax
0x140005bb0  mov     edx, eax
0x140005bb2  call    ShowMessageEx
0x140005bb7  cmp     dword ptr [rdi+20h], 1
0x140005bbb  jnz     short loc_140005C24
0x140005bbd  mov     r9d, [rdi+8Ch]
0x140005bc4  lea     rax, [rbp+57h+hKey]
0x140005bc8  or      r9d, 20019h; samDesired
0x140005bcf  mov     [rsp+0C0h+lpcSubKeys], rax; phkResult
0x140005bd4  xor     r8d, r8d; ulOptions
0x140005bd7  mov     rdx, r14; lpSubKey
0x140005bda  mov     rcx, r13; hKey
0x140005bdd  call    cs:__imp_RegOpenKeyExW
0x140005be4  nop     dword ptr [rax+rax+00h]
0x140005be9  xor     ecx, ecx
0x140005beb  test    eax, eax
0x140005bed  jnz     short loc_140005C22
0x140005bef  mov     rcx, [rbp+57h+hKey]
0x140005bf3  mov     r9, rsi
0x140005bf6  mov     r8, rdi
0x140005bf9  mov     rdx, r12
0x140005bfc  call    QueryEnumKeys
0x140005c01  mov     rcx, [rbp+57h+hKey]; hKey
0x140005c05  mov     ebx, eax
0x140005c07  test    rcx, rcx
0x140005c0a  jz      short loc_140005C24
0x140005c0c  call    cs:__imp_RegCloseKey
0x140005c13  nop     dword ptr [rax+rax+00h]
0x140005c18  mov     [rbp+57h+hKey], 0
0x140005c20  jmp     short loc_140005C24
0x140005c22  mov     ebx, ecx
0x140005c24  inc     r15d
0x140005c27  cmp     r15d, [rbp+57h+cSubKeys]
0x140005c2b  jb      loc_140005A94
0x140005c31  jmp     short loc_140005C3F
0x140005c33  mov     ebx, 57h ; 'W'
0x140005c38  mov     ecx, ebx
0x140005c3a  call    SaveErrorMessage
0x140005c3f  lea     rcx, [rbp+57h+var_48]
0x140005c43  call    FreeMemory
0x140005c48  lea     rcx, [rbp+57h+var_40]
0x140005c4c  call    FreeMemory
0x140005c51  mov     eax, ebx
0x140005c53  mov     rbx, [rsp+0C0h+arg_10]
0x140005c5b  add     rsp, 90h
0x140005c62  pop     r15
0x140005c64  pop     r14
0x140005c66  pop     r13
0x140005c68  pop     r12
0x140005c6a  pop     rdi
0x140005c6b  pop     rsi
0x140005c6c  pop     rbp
0x140005c6d  retn
```
