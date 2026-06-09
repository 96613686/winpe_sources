# RegSetDefValue

- ea: `0x180010da0`
- end: `0x180010fb7`
- name: `RegSetDefValue`
- size: `535`
- prototype: `__int64 __fastcall(LPCSTR lpSubKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010fc0`

## callees

- `0x1800014f0`
- `0x180010da0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f85`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f85`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180010f78`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExA` at `0x180010f78`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180010f21`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExA` at `0x180010f21`

## pseudocode

```c
LSTATUS __fastcall RegSetDefValue(LPCSTR lpSubKey, _BYTE *a2, const CHAR *a3, const BYTE *a4)
{
  _BYTE *v6; // rbx
  __int64 v7; // r11
  _BYTE *v8; // r8
  __int64 v9; // rax
  __int64 v10; // r10
  _BYTE *v11; // rax
  __int64 v12; // rcx
  _BYTE *v13; // rax
  __int64 v14; // r8
  const char *v15; // r10
  bool v16; // zf
  __int64 v17; // rax
  _BYTE *v18; // r8
  _BYTE *v19; // rax
  __int64 v20; // rcx
  _BYTE *v21; // rax
  __int64 v22; // r8
  _BYTE *v23; // rcx
  __int64 v24; // rdx
  _BYTE *v25; // rax
  LSTATUS result; // eax
  const BYTE *v27; // rax
  __int64 v28; // rcx
  LSTATUS v29; // ebx
  HKEY hKey; // [rsp+50h] [rbp-438h] BYREF
  _BYTE v31[1024]; // [rsp+60h] [rbp-428h] BYREF

  hKey = 0;
  v6 = a2;
  if ( a2 )
  {
    v7 = 2147483646;
    v8 = v31;
    v9 = 2147483646;
    v10 = 1024;
    do
    {
      if ( !v9 )
        break;
      if ( !*lpSubKey )
        break;
      *v8++ = *lpSubKey++;
      --v9;
      --v10;
    }
    while ( v10 );
    v11 = v8 - 1;
    v12 = 1024;
    if ( v10 )
      v11 = v8;
    *v11 = 0;
    v13 = v31;
    do
    {
      if ( !*v13 )
        break;
      ++v13;
      --v12;
    }
    while ( v12 );
    v14 = 1024 - v12;
    if ( v12 )
    {
      v15 = "\\";
      v16 = v14 == 1024;
      v17 = 2147483646;
      v18 = &v31[v14];
      if ( !v16 )
      {
        do
        {
          if ( !v17 )
            break;
          if ( !*v15 )
            break;
          *v18++ = *v15++;
          --v17;
          --v12;
        }
        while ( v12 );
      }
      v19 = v18 - 1;
      if ( v12 )
        v19 = v18;
      *v19 = 0;
    }
    v20 = 1024;
    v21 = v31;
    do
    {
      if ( !*v21 )
        break;
      ++v21;
      --v20;
    }
    while ( v20 );
    v22 = 1024 - v20;
    if ( v20 )
    {
      v23 = &v31[v22];
      v24 = 1024 - v22;
      if ( 1024 != v22 )
      {
        do
        {
          if ( !v7 )
            break;
          if ( !*v6 )
            break;
          *v23++ = *v6++;
          --v7;
          --v24;
        }
        while ( v24 );
      }
      v25 = v23 - 1;
      if ( v24 )
        v25 = v23;
      *v25 = 0;
    }
    lpSubKey = v31;
  }
  result = RegCreateKeyExA(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  if ( !result )
  {
    if ( !a4 )
      return 14;
    v27 = a4;
    v28 = 0x7FFFFFFF;
    do
    {
      if ( !*v27 )
        break;
      ++v27;
      --v28;
    }
    while ( v28 );
    if ( v28 )
    {
      v29 = RegSetValueExA(hKey, a3, 0, 1u, a4, 0x7FFFFFFF - v28 + 1);
      RegCloseKey(hKey);
      return v29;
    }
    else
    {
      return 14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010da0  mov     [rsp+arg_8], rbx
0x180010da5  push    rbp
0x180010da6  push    rsi
0x180010da7  push    rdi
0x180010da8  sub     rsp, 470h
0x180010daf  mov     rax, cs:__security_cookie
0x180010db6  xor     rax, rsp
0x180010db9  mov     [rsp+488h+var_28], rax
0x180010dc1  xor     ebp, ebp
0x180010dc3  mov     rdi, r9
0x180010dc6  mov     [rsp+488h+hKey], rbp
0x180010dcb  mov     rsi, r8
0x180010dce  mov     rbx, rdx
0x180010dd1  test    rdx, rdx
0x180010dd4  jz      loc_180010EF1
0x180010dda  mov     r11d, 7FFFFFFEh
0x180010de0  lea     r8, [rsp+488h+var_428]
0x180010de5  mov     edx, 400h
0x180010dea  mov     eax, r11d
0x180010ded  mov     r10d, edx
0x180010df0  test    rax, rax
0x180010df3  jz      short loc_180010E10
0x180010df5  movzx   r9d, byte ptr [rcx]
0x180010df9  test    r9b, r9b
0x180010dfc  jz      short loc_180010E10
0x180010dfe  mov     [r8], r9b
0x180010e01  inc     rcx
0x180010e04  inc     r8
0x180010e07  dec     rax
0x180010e0a  sub     r10, 1
0x180010e0e  jnz     short loc_180010DF0
0x180010e10  test    r10, r10
0x180010e13  lea     rax, [r8-1]
0x180010e17  mov     rcx, rdx
0x180010e1a  cmovnz  rax, r8
0x180010e1e  mov     [rax], bpl
0x180010e21  lea     rax, [rsp+488h+var_428]
0x180010e26  cmp     [rax], bpl
0x180010e29  jz      short loc_180010E34
0x180010e2b  inc     rax
0x180010e2e  sub     rcx, 1
0x180010e32  jnz     short loc_180010E26
0x180010e34  mov     r8, rdx
0x180010e37  sub     r8, rcx
0x180010e3a  test    rcx, rcx
0x180010e3d  cmovz   r8, rbp
0x180010e41  jz      short loc_180010E8E
0x180010e43  mov     rcx, rdx
0x180010e46  lea     r10, asc_18001B190; "\\"
0x180010e4d  sub     rcx, r8
0x180010e50  mov     rax, r11
0x180010e53  lea     r8, [rsp+r8+488h+var_428]
0x180010e58  jz      short loc_180010E80
0x180010e5a  nop     word ptr [rax+rax+00h]
0x180010e60  test    rax, rax
0x180010e63  jz      short loc_180010E80
0x180010e65  movzx   r9d, byte ptr [r10]
0x180010e69  test    r9b, r9b
0x180010e6c  jz      short loc_180010E80
0x180010e6e  mov     [r8], r9b
0x180010e71  inc     r10
0x180010e74  inc     r8
0x180010e77  dec     rax
0x180010e7a  sub     rcx, 1
0x180010e7e  jnz     short loc_180010E60
0x180010e80  test    rcx, rcx
0x180010e83  lea     rax, [r8-1]
0x180010e87  cmovnz  rax, r8
0x180010e8b  mov     [rax], bpl
0x180010e8e  mov     rcx, rdx
0x180010e91  lea     rax, [rsp+488h+var_428]
0x180010e96  cmp     [rax], bpl
0x180010e99  jz      short loc_180010EA4
0x180010e9b  inc     rax
0x180010e9e  sub     rcx, 1
0x180010ea2  jnz     short loc_180010E96
0x180010ea4  mov     r8, rdx
0x180010ea7  sub     r8, rcx
0x180010eaa  test    rcx, rcx
0x180010ead  cmovz   r8, rbp
0x180010eb1  jz      short loc_180010EEC
0x180010eb3  lea     rcx, [rsp+488h+var_428]
0x180010eb8  lea     rcx, [rcx+r8]
0x180010ebc  sub     rdx, r8
0x180010ebf  jz      short loc_180010EDE
0x180010ec1  test    r11, r11
0x180010ec4  jz      short loc_180010EDE
0x180010ec6  movzx   eax, byte ptr [rbx]
0x180010ec9  test    al, al
0x180010ecb  jz      short loc_180010EDE
0x180010ecd  mov     [rcx], al
0x180010ecf  inc     rbx
0x180010ed2  inc     rcx
0x180010ed5  dec     r11
0x180010ed8  sub     rdx, 1
0x180010edc  jnz     short loc_180010EC1
0x180010ede  test    rdx, rdx
0x180010ee1  lea     rax, [rcx-1]
0x180010ee5  cmovnz  rax, rcx
0x180010ee9  mov     [rax], bpl
0x180010eec  lea     rcx, [rsp+488h+var_428]
0x180010ef1  mov     [rsp+488h+lpdwDisposition], rbp; lpdwDisposition
0x180010ef6  lea     rax, [rsp+488h+hKey]
0x180010efb  mov     [rsp+488h+phkResult], rax; phkResult
0x180010f00  mov     rdx, rcx; lpSubKey
0x180010f03  mov     [rsp+488h+lpSecurityAttributes], rbp; lpSecurityAttributes
0x180010f08  xor     r9d, r9d; lpClass
0x180010f0b  mov     [rsp+488h+samDesired], 0F003Fh; samDesired
0x180010f13  xor     r8d, r8d; Reserved
0x180010f16  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180010f1d  mov     [rsp+488h+dwOptions], ebp; dwOptions
0x180010f21  call    cs:__imp_RegCreateKeyExA
0x180010f27  test    eax, eax
0x180010f29  jnz     short loc_180010F94
0x180010f2b  test    rdi, rdi
0x180010f2e  jz      short loc_180010F8F
0x180010f30  mov     r8d, 7FFFFFFFh
0x180010f36  mov     rax, rdi
0x180010f39  mov     ecx, r8d
0x180010f3c  nop     dword ptr [rax+00h]
0x180010f40  cmp     [rax], bpl
0x180010f43  jz      short loc_180010F4E
0x180010f45  inc     rax
0x180010f48  sub     rcx, 1
0x180010f4c  jnz     short loc_180010F40
0x180010f4e  sub     r8, rcx
0x180010f51  test    rcx, rcx
0x180010f54  cmovz   r8, rbp
0x180010f58  jz      short loc_180010F8F
0x180010f5a  mov     rcx, [rsp+488h+hKey]; hKey
0x180010f5f  lea     eax, [r8+1]
0x180010f63  mov     [rsp+488h+samDesired], eax; cbData
0x180010f67  mov     r9d, 1; dwType
0x180010f6d  xor     r8d, r8d; Reserved
0x180010f70  mov     qword ptr [rsp+488h+dwOptions], rdi; lpData
0x180010f75  mov     rdx, rsi; lpValueName
0x180010f78  call    cs:__imp_RegSetValueExA
0x180010f7e  mov     rcx, [rsp+488h+hKey]; hKey
0x180010f83  mov     ebx, eax
0x180010f85  call    cs:__imp_RegCloseKey
0x180010f8b  mov     eax, ebx
0x180010f8d  jmp     short loc_180010F94
0x180010f8f  mov     eax, 0Eh
0x180010f94  mov     rcx, [rsp+488h+var_28]
0x180010f9c  xor     rcx, rsp; StackCookie
0x180010f9f  call    __security_check_cookie
0x180010fa4  mov     rbx, [rsp+488h+arg_8]
0x180010fac  add     rsp, 470h
0x180010fb3  pop     rdi
0x180010fb4  pop     rsi
0x180010fb5  pop     rbp
0x180010fb6  retn
```
