# CfEnumAppPolicy

- ea: `0x180003930`
- end: `0x180003b9f`
- name: `CfEnumAppPolicy`
- size: `623`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPBYTE lpData, LPBYTE, LPBYTE)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180003930`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000399b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000399b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003a16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003a74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003ad1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b2a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003a16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003a74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003ad1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b2a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800039cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800039cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003b7b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003b7b`

## string_xrefs

- `0x180003a5b`: `ImagePath`

## pseudocode

```c
__int64 __fastcall CfEnumAppPolicy(HKEY hKey, DWORD a2, WCHAR *a3, BYTE *a4, LPBYTE lpData, LPBYTE a6, LPBYTE a7)
{
  signed int v10; // ebx
  LSTATUS v11; // eax
  LSTATUS v12; // edi
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  LPBYTE v15; // r14
  LSTATUS v16; // eax
  LPBYTE v17; // r14
  LSTATUS v18; // eax
  LPBYTE v19; // r14
  LSTATUS v20; // eax
  HKEY phkResult; // [rsp+40h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+20h] BYREF
  DWORD cchName; // [rsp+88h] [rbp+38h] BYREF

  phkResult = 0;
  cchName = 65;
  *(_DWORD *)a4 = 0;
  if ( !hKey )
    return (unsigned int)-2147024637;
  v11 = RegEnumKeyExW(hKey, a2, a3, &cchName, 0, 0, 0, 0);
  v12 = v11;
  if ( !v11 )
  {
    cbData = 0;
    v13 = RegOpenKeyExW(hKey, a3, 0, 0x20019u, &phkResult);
    v10 = v13;
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
    if ( v10 < 0 )
      goto LABEL_36;
    cbData = 4;
    v14 = RegQueryValueExW(phkResult, L"Enabled", 0, 0, a4, &cbData);
    v10 = v14;
    if ( v14 == 2 )
    {
      *(_DWORD *)a4 = 0;
      v10 = 0;
    }
    else if ( v14 > 0 )
    {
      v10 = (unsigned __int16)v14 | 0x80070000;
    }
    if ( v10 < 0 )
      goto LABEL_36;
    v15 = lpData;
    if ( lpData )
    {
      cbData = 0x8000;
      v16 = RegQueryValueExW(phkResult, L"ImagePath", 0, 0, lpData, &cbData);
      v10 = v16;
      if ( v16 == 2 )
      {
        *(_WORD *)v15 = 0;
        v10 = 0;
      }
      else if ( v16 > 0 )
      {
        v10 = (unsigned __int16)v16 | 0x80070000;
      }
      if ( v10 < 0 )
        goto LABEL_36;
    }
    v17 = a6;
    if ( a6 )
    {
      cbData = 0x8000;
      v18 = RegQueryValueExW(phkResult, L"PackageName", 0, 0, a6, &cbData);
      v10 = v18;
      if ( v18 == 2 )
      {
        *(_WORD *)v17 = 0;
        v10 = 0;
      }
      else if ( v18 > 0 )
      {
        v10 = (unsigned __int16)v18 | 0x80070000;
      }
      if ( v10 < 0 )
        goto LABEL_36;
    }
    v19 = a7;
    if ( a7 )
    {
      cbData = 0x8000;
      v20 = RegQueryValueExW(phkResult, L"AppName", 0, 0, a7, &cbData);
      v10 = v20;
      if ( v20 == 2 )
      {
        *(_WORD *)v19 = 0;
        v10 = 0;
      }
      else if ( v20 > 0 )
      {
        v10 = (unsigned __int16)v20 | 0x80070000;
      }
      if ( v10 < 0 )
        goto LABEL_36;
    }
    goto LABEL_34;
  }
  if ( v11 == 234 )
  {
    v12 = 0;
LABEL_34:
    v10 = v12;
    goto LABEL_36;
  }
  if ( v11 <= 0 )
    goto LABEL_34;
  v10 = (unsigned __int16)v11 | 0x80070000;
LABEL_36:
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180003930  mov     [rsp-18h+arg_8], rbx
0x180003935  mov     [rsp-18h+arg_10], rsi
0x18000393a  push    rbp
0x18000393b  push    rdi
0x18000393c  push    r14
0x18000393e  mov     rbp, rsp
0x180003941  sub     rsp, 50h
0x180003945  mov     [rbp+phkResult], 0
0x18000394d  mov     r14, r9
0x180003950  mov     [rbp+cchName], 41h ; 'A'
0x180003957  mov     rsi, r8
0x18000395a  mov     dword ptr [r9], 0
0x180003961  mov     rbx, rcx
0x180003964  test    rcx, rcx
0x180003967  jnz     short loc_180003973
0x180003969  mov     ebx, 80070103h
0x18000396e  jmp     loc_180003B87
0x180003973  mov     [rsp+50h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18000397c  lea     r9, [rbp+cchName]; lpcchName
0x180003980  mov     [rsp+50h+lpcchClass], 0; lpcchClass
0x180003989  mov     [rsp+50h+lpClass], 0; lpClass
0x180003992  mov     [rsp+50h+lpReserved], 0; lpReserved
0x18000399b  call    cs:__imp_RegEnumKeyExW
0x1800039a2  nop     dword ptr [rax+rax+00h]
0x1800039a7  mov     edi, eax
0x1800039a9  test    eax, eax
0x1800039ab  jnz     loc_180003B56
0x1800039b1  mov     [rbp+cbData], eax
0x1800039b4  mov     r9d, 20019h; samDesired
0x1800039ba  lea     rax, [rbp+phkResult]
0x1800039be  xor     r8d, r8d; ulOptions
0x1800039c1  mov     rdx, rsi; lpSubKey
0x1800039c4  mov     [rsp+50h+lpReserved], rax; phkResult
0x1800039c9  mov     rcx, rbx; hKey
0x1800039cc  call    cs:__imp_RegOpenKeyExW
0x1800039d3  nop     dword ptr [rax+rax+00h]
0x1800039d8  mov     ebx, eax
0x1800039da  mov     esi, 80070000h
0x1800039df  test    eax, eax
0x1800039e1  jle     short loc_1800039E8
0x1800039e3  movzx   ebx, ax
0x1800039e6  or      ebx, esi
0x1800039e8  test    ebx, ebx
0x1800039ea  js      loc_180003B72
0x1800039f0  mov     rcx, [rbp+phkResult]; hKey
0x1800039f4  lea     rax, [rbp+cbData]
0x1800039f8  mov     [rsp+50h+lpClass], rax; lpcbData
0x1800039fd  lea     rdx, ValueName; "Enabled"
0x180003a04  xor     r9d, r9d; lpType
0x180003a07  mov     [rsp+50h+lpReserved], r14; lpData
0x180003a0c  xor     r8d, r8d; lpReserved
0x180003a0f  mov     [rbp+cbData], 4
0x180003a16  call    cs:__imp_RegQueryValueExW
0x180003a1d  nop     dword ptr [rax+rax+00h]
0x180003a22  mov     ebx, eax
0x180003a24  cmp     eax, 2
0x180003a27  jnz     short loc_180003A34
0x180003a29  mov     dword ptr [r14], 0
0x180003a30  xor     ebx, ebx
0x180003a32  jmp     short loc_180003A3D
0x180003a34  test    eax, eax
0x180003a36  jle     short loc_180003A3D
0x180003a38  movzx   ebx, ax
0x180003a3b  or      ebx, esi
0x180003a3d  test    ebx, ebx
0x180003a3f  js      loc_180003B72
0x180003a45  mov     r14, [rbp+lpData]
0x180003a49  test    r14, r14
0x180003a4c  jz      short loc_180003AA2
0x180003a4e  mov     rcx, [rbp+phkResult]; hKey
0x180003a52  lea     rax, [rbp+cbData]
0x180003a56  mov     [rsp+50h+lpClass], rax; lpcbData
0x180003a5b  lea     rdx, aImagepath; "ImagePath"
0x180003a62  xor     r9d, r9d; lpType
0x180003a65  mov     [rsp+50h+lpReserved], r14; lpData
0x180003a6a  xor     r8d, r8d; lpReserved
0x180003a6d  mov     [rbp+cbData], 8000h
0x180003a74  call    cs:__imp_RegQueryValueExW
0x180003a7b  nop     dword ptr [rax+rax+00h]
0x180003a80  mov     ebx, eax
0x180003a82  cmp     eax, 2
0x180003a85  jnz     short loc_180003A91
0x180003a87  xor     eax, eax
0x180003a89  mov     [r14], ax
0x180003a8d  xor     ebx, ebx
0x180003a8f  jmp     short loc_180003A9A
0x180003a91  test    eax, eax
0x180003a93  jle     short loc_180003A9A
0x180003a95  movzx   ebx, ax
0x180003a98  or      ebx, esi
0x180003a9a  test    ebx, ebx
0x180003a9c  js      loc_180003B72
0x180003aa2  mov     r14, [rbp+arg_28]
0x180003aa6  test    r14, r14
0x180003aa9  jz      short loc_180003AFB
0x180003aab  mov     rcx, [rbp+phkResult]; hKey
0x180003aaf  lea     rax, [rbp+cbData]
0x180003ab3  mov     [rsp+50h+lpClass], rax; lpcbData
0x180003ab8  lea     rdx, aPackagename; "PackageName"
0x180003abf  xor     r9d, r9d; lpType
0x180003ac2  mov     [rsp+50h+lpReserved], r14; lpData
0x180003ac7  xor     r8d, r8d; lpReserved
0x180003aca  mov     [rbp+cbData], 8000h
0x180003ad1  call    cs:__imp_RegQueryValueExW
0x180003ad8  nop     dword ptr [rax+rax+00h]
0x180003add  mov     ebx, eax
0x180003adf  cmp     eax, 2
0x180003ae2  jnz     short loc_180003AEE
0x180003ae4  xor     eax, eax
0x180003ae6  mov     [r14], ax
0x180003aea  xor     ebx, ebx
0x180003aec  jmp     short loc_180003AF7
0x180003aee  test    eax, eax
0x180003af0  jle     short loc_180003AF7
0x180003af2  movzx   ebx, ax
0x180003af5  or      ebx, esi
0x180003af7  test    ebx, ebx
0x180003af9  js      short loc_180003B72
0x180003afb  mov     r14, [rbp+arg_30]
0x180003aff  test    r14, r14
0x180003b02  jz      short loc_180003B65
0x180003b04  mov     rcx, [rbp+phkResult]; hKey
0x180003b08  lea     rax, [rbp+cbData]
0x180003b0c  mov     [rsp+50h+lpClass], rax; lpcbData
0x180003b11  lea     rdx, aAppname; "AppName"
0x180003b18  xor     r9d, r9d; lpType
0x180003b1b  mov     [rsp+50h+lpReserved], r14; lpData
0x180003b20  xor     r8d, r8d; lpReserved
0x180003b23  mov     [rbp+cbData], 8000h
0x180003b2a  call    cs:__imp_RegQueryValueExW
0x180003b31  nop     dword ptr [rax+rax+00h]
0x180003b36  mov     ebx, eax
0x180003b38  cmp     eax, 2
0x180003b3b  jnz     short loc_180003B47
0x180003b3d  xor     eax, eax
0x180003b3f  mov     [r14], ax
0x180003b43  xor     ebx, ebx
0x180003b45  jmp     short loc_180003B50
0x180003b47  test    eax, eax
0x180003b49  jle     short loc_180003B50
0x180003b4b  movzx   ebx, ax
0x180003b4e  or      ebx, esi
0x180003b50  test    ebx, ebx
0x180003b52  jns     short loc_180003B65
0x180003b54  jmp     short loc_180003B72
0x180003b56  cmp     eax, 0EAh
0x180003b5b  jnz     short loc_180003B61
0x180003b5d  xor     edi, edi
0x180003b5f  jmp     short loc_180003B65
0x180003b61  test    eax, eax
0x180003b63  jg      short loc_180003B69
0x180003b65  mov     ebx, edi
0x180003b67  jmp     short loc_180003B72
0x180003b69  movzx   ebx, ax
0x180003b6c  or      ebx, 80070000h
0x180003b72  mov     rcx, [rbp+phkResult]; hKey
0x180003b76  test    rcx, rcx
0x180003b79  jz      short loc_180003B87
0x180003b7b  call    cs:__imp_RegCloseKey
0x180003b82  nop     dword ptr [rax+rax+00h]
0x180003b87  lea     r11, [rsp+50h+var_s0]
0x180003b8c  mov     eax, ebx
0x180003b8e  mov     rbx, [r11+28h]
0x180003b92  mov     rsi, [r11+30h]
0x180003b96  mov     rsp, r11
0x180003b99  pop     r14
0x180003b9b  pop     rdi
0x180003b9c  pop     rbp
0x180003b9d  retn
```
