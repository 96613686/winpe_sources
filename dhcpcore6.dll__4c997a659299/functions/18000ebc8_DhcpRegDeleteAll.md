# DhcpRegDeleteAll

- ea: `0x18000ebc8`
- end: `0x18000ed10`
- name: `DhcpRegDeleteAll`
- size: `328`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e950`

## callees

- `0x18000ebc8`
- `0x180019ad0`
- `0x18001a3ee`
- `0x180033900`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000ec34`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000ec34`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000ec90`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000ec90`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000eccd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000eccd`

## pseudocode

```c
__int64 __fastcall DhcpRegDeleteAll(HKEY hKey)
{
  DWORD v2; // ebx
  unsigned int v3; // esi
  DWORD i; // edi
  DWORD cValues; // [rsp+60h] [rbp-108h] BYREF
  DWORD cchValueName[3]; // [rsp+64h] [rbp-104h] BYREF
  WCHAR ValueName[104]; // [rsp+70h] [rbp-F8h] BYREF

  cValues = 0;
  cchValueName[0] = 0;
  v2 = 0;
  v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
  for ( i = 0; v2 < cValues; ++v2 )
  {
    cchValueName[0] = 100;
    memset_0(ValueName, 0, 0xC8u);
    v3 = RegEnumValueW(hKey, i, ValueName, cchValueName, 0, 0, 0, 0);
    if ( v3 )
    {
      if ( (xmmword_1800423E0 & 0x10) != 0 )
        WPP_SF_(1028, 90, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids);
      ++i;
    }
    else
    {
      RegDeleteValueW(hKey, ValueName);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000ebc8  mov     [rsp+arg_8], rbx
0x18000ebcd  mov     [rsp+arg_10], rbp
0x18000ebd2  push    rsi
0x18000ebd3  push    rdi
0x18000ebd4  push    r14
0x18000ebd6  sub     rsp, 150h
0x18000ebdd  mov     rax, cs:__security_cookie
0x18000ebe4  xor     rax, rsp
0x18000ebe7  mov     [rsp+168h+var_28], rax
0x18000ebef  xor     r14d, r14d
0x18000ebf2  lea     rax, [rsp+168h+cValues]
0x18000ebf7  mov     [rsp+168h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18000ebfc  xor     r9d, r9d; lpReserved
0x18000ebff  mov     [rsp+168h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18000ec04  xor     r8d, r8d; lpcchClass
0x18000ec07  mov     [rsp+168h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18000ec0c  xor     edx, edx; lpClass
0x18000ec0e  mov     [rsp+168h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18000ec13  mov     rbp, rcx
0x18000ec16  mov     [rsp+168h+lpcValues], rax; lpcValues
0x18000ec1b  mov     [rsp+168h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18000ec20  mov     [rsp+168h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x18000ec25  mov     [rsp+168h+lpcSubKeys], r14; lpcSubKeys
0x18000ec2a  mov     [rsp+168h+cValues], r14d
0x18000ec2f  mov     [rsp+168h+cchValueName], r14d
0x18000ec34  call    cs:__imp_RegQueryInfoKeyW
0x18000ec3b  nop     dword ptr [rax+rax+00h]
0x18000ec40  mov     ebx, r14d
0x18000ec43  mov     esi, eax
0x18000ec45  mov     edi, r14d
0x18000ec48  cmp     [rsp+168h+cValues], r14d
0x18000ec4d  jbe     loc_18000ECE5
0x18000ec53  xor     edx, edx; Val
0x18000ec55  mov     [rsp+168h+cchValueName], 64h ; 'd'
0x18000ec5d  mov     r8d, 0C8h; Size
0x18000ec63  lea     rcx, [rsp+168h+ValueName]; void *
0x18000ec68  call    memset_0
0x18000ec6d  mov     [rsp+168h+lpcValues], r14; lpcbData
0x18000ec72  lea     r9, [rsp+168h+cchValueName]; lpcchValueName
0x18000ec77  mov     [rsp+168h+lpcbMaxClassLen], r14; lpData
0x18000ec7c  lea     r8, [rsp+168h+ValueName]; lpValueName
0x18000ec81  mov     [rsp+168h+lpcbMaxSubKeyLen], r14; lpType
0x18000ec86  mov     edx, edi; dwIndex
0x18000ec88  mov     rcx, rbp; hKey
0x18000ec8b  mov     [rsp+168h+lpcSubKeys], r14; lpReserved
0x18000ec90  call    cs:__imp_RegEnumValueW
0x18000ec97  nop     dword ptr [rax+rax+00h]
0x18000ec9c  mov     esi, eax
0x18000ec9e  test    eax, eax
0x18000eca0  jz      short loc_18000ECC5
0x18000eca2  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000eca9  jz      short loc_18000ECC1
0x18000ecab  mov     edx, 5Ah ; 'Z'
0x18000ecb0  lea     r8, WPP_80912ccc52483efd9cc4ca3c8a600041_Traceguids
0x18000ecb7  mov     ecx, 404h
0x18000ecbc  call    WPP_SF_
0x18000ecc1  inc     edi
0x18000ecc3  jmp     short loc_18000ECD9
0x18000ecc5  lea     rdx, [rsp+168h+ValueName]; lpValueName
0x18000ecca  mov     rcx, rbp; hKey
0x18000eccd  call    cs:__imp_RegDeleteValueW
0x18000ecd4  nop     dword ptr [rax+rax+00h]
0x18000ecd9  inc     ebx
0x18000ecdb  cmp     ebx, [rsp+168h+cValues]
0x18000ecdf  jb      loc_18000EC53
0x18000ece5  mov     eax, esi
0x18000ece7  mov     rcx, [rsp+168h+var_28]
0x18000ecef  xor     rcx, rsp; StackCookie
0x18000ecf2  call    __security_check_cookie
0x18000ecf7  lea     r11, [rsp+168h+var_18]
0x18000ecff  mov     rbx, [r11+28h]
0x18000ed03  mov     rbp, [r11+30h]
0x18000ed07  mov     rsp, r11
0x18000ed0a  pop     r14
0x18000ed0c  pop     rdi
0x18000ed0d  pop     rsi
0x18000ed0e  retn
```
