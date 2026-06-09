# RecursiveDeleteKey

- ea: `0x140007cbc`
- end: `0x14000809c`
- name: `RecursiveDeleteKey`
- size: `992`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400073d4`
- `0x140007cbc`

## callees

- `0x140001bb2`
- `0x140002ce4`
- `0x140007cbc`
- `0x14000ce50`
- `0x14000d2d0`
- `0x14000d694`
- `0x14000e560`
- `0x14000e798`
- `0x14000f294`
- `0x14000f2c4`
- `0x14000f43c`
- `0x14000f8e8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007d36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140007d36`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140007eee`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140007eee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007da7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007dcb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007e35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007e78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007fe0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007da7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007dcb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007e35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007e78`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007fe0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140007dec`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140008007`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140007dec`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140008007`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140007d88`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140007d88`

## pseudocode

```c
__int64 __fastcall RecursiveDeleteKey(HKEY a1, const WCHAR *a2, int a3, __int64 a4)
{
  int v4; // r14d
  HKEY v7; // rsi
  unsigned int v8; // ebx
  _DWORD *v9; // r13
  WCHAR *v10; // rdi
  int v11; // esi
  DWORD v12; // r15d
  WCHAR *v13; // rax
  __int64 i; // rcx
  LSTATUS v15; // eax
  unsigned int v16; // edi
  int v17; // r15d
  unsigned int j; // esi
  __int64 Item; // rax
  __int64 v20; // rdx
  unsigned int v21; // eax
  DWORD v22; // eax
  __int64 ResString2FromModule; // rax
  FILE *v24; // rax
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-9h] BYREF
  DWORD cchName; // [rsp+6Ch] [rbp-5h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+7h] BYREF
  __int64 DynamicArray; // [rsp+80h] [rbp+Fh] BYREF
  LPVOID v31[8]; // [rsp+88h] [rbp+17h] BYREF
  HKEY v32; // [rsp+D8h] [rbp+67h]

  v32 = a1;
  v4 = 0;
  cchName = 0;
  hKey = 0;
  v7 = a1;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  if ( !a1 || !a2 || !a4 )
  {
    v8 = 87;
    goto LABEL_61;
  }
  v8 = RegOpenKeyExW(a1, a2, 0, *(_DWORD *)(a4 + 140) | 0xF003F, &hKey);
  if ( v8 )
  {
LABEL_61:
    v17 = a3;
    goto LABEL_62;
  }
  v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v8 )
  {
    a1 = hKey;
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    goto LABEL_61;
  }
  if ( !cSubKeys )
  {
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v8 = RegDeleteKeyExW(v7, a2, *(_DWORD *)(a4 + 140), 0);
    goto LABEL_61;
  }
  if ( cbMaxSubKeyLen )
  {
    if ( cbMaxSubKeyLen < 0x100 )
      cbMaxSubKeyLen *= 2;
  }
  else
  {
    cbMaxSubKeyLen = 256;
  }
  DynamicArray = CreateDynamicArray();
  v9 = (_DWORD *)DynamicArray;
  if ( !DynamicArray )
  {
    a1 = hKey;
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
LABEL_19:
    v8 = 14;
    goto LABEL_61;
  }
  ++cbMaxSubKeyLen;
  v31[0] = AllocateMemory(2 * cbMaxSubKeyLen + 4);
  v10 = (WCHAR *)v31[0];
  if ( !v31[0] )
  {
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    DestroyDynamicArray(&DynamicArray);
    goto LABEL_19;
  }
  v11 = 0;
  v12 = 0;
  if ( !cSubKeys )
    goto LABEL_30;
  while ( 1 )
  {
    cchName = cbMaxSubKeyLen;
    v13 = v10;
    for ( i = 2LL * cbMaxSubKeyLen; i; --i )
    {
      *(_BYTE *)v13 = 0;
      v13 = (WCHAR *)((char *)v13 + 1);
    }
    v15 = RegEnumKeyExW(hKey, v12, v10, &cchName, 0, 0, 0, 0);
    v4 = v15;
    if ( v15 )
    {
      if ( !v11 )
        v11 = v15;
      goto LABEL_34;
    }
    if ( (unsigned int)DynArrayAppendString(v9, v10) == -1 )
      break;
LABEL_34:
    if ( ++v12 >= cSubKeys )
      goto LABEL_30;
  }
  v11 = 14;
  v4 = 14;
LABEL_30:
  FreeMemory(v31);
  if ( *v9 == 9 )
    v16 = v9[1];
  else
    v16 = 0;
  if ( v4 == 14 || !v16 )
  {
    v17 = a3;
    v8 = v11;
  }
  else
  {
    v17 = a3;
    v8 = 0;
    cchName = 0;
    for ( j = 0; j < v16; ++j )
    {
      Item = _DynArrayGetItem(v9, j, 0);
      if ( Item && *(_DWORD *)(Item + 4) == 0x20000 )
        v20 = *(_QWORD *)(Item + 16);
      else
        v20 = 0;
      v21 = RecursiveDeleteKey(hKey, v20, (unsigned int)(a3 + 1), a4);
      if ( v21 )
      {
        if ( !v8 )
          v8 = v21;
        v22 = cchName;
      }
      else
      {
        v22 = ++cchName;
      }
    }
    if ( v22 )
    {
      if ( v16 == cSubKeys && v22 == v16 )
        v8 = 0;
      else
        v8 = -2147286527;
    }
  }
  DestroyDynamicArray(&DynamicArray);
  a1 = hKey;
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( !v8 )
    v8 = RegDeleteKeyExW(v32, a2, *(_DWORD *)(a4 + 140), 0);
LABEL_62:
  if ( !v17 )
  {
    if ( v8 )
    {
      if ( v8 == -2147286527 )
      {
        ResString2FromModule = GetResString2FromModule(a1, 141, 0);
        SetReason(ResString2FromModule);
      }
      else
      {
        SaveErrorMessage(v8);
      }
      v24 = o___acrt_iob_func_0(2u);
    }
    else
    {
      SaveErrorMessage(0);
      v24 = o___acrt_iob_func_0(1u);
    }
    ShowLastErrorEx(v24);
  }
  return v8;
}

```

## disassembly

```asm
0x140007cbc  mov     rax, rsp
0x140007cbf  mov     [rax+20h], rbx
0x140007cc3  mov     [rax+18h], r8d
0x140007cc7  mov     [rax+10h], rdx
0x140007ccb  mov     [rax+8], rcx
0x140007ccf  push    rbp
0x140007cd0  push    rsi
0x140007cd1  push    rdi
0x140007cd2  push    r12
0x140007cd4  push    r13
0x140007cd6  push    r14
0x140007cd8  push    r15
0x140007cda  lea     rbp, [rax-5Fh]
0x140007cde  sub     rsp, 90h
0x140007ce5  xor     r14d, r14d
0x140007ce8  mov     r12, r9
0x140007ceb  mov     [rbp+57h+cchName], r14d
0x140007cef  mov     rdi, rdx
0x140007cf2  mov     [rbp+57h+hKey], r14
0x140007cf6  mov     rsi, rcx
0x140007cf9  mov     [rbp+57h+cSubKeys], r14d
0x140007cfd  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x140007d01  test    rcx, rcx
0x140007d04  jz      loc_140008017
0x140007d0a  test    rdx, rdx
0x140007d0d  jz      loc_140008017
0x140007d13  test    r9, r9
0x140007d16  jz      loc_140008017
0x140007d1c  mov     r9d, [r9+8Ch]
0x140007d23  lea     rax, [rbp+57h+hKey]
0x140007d27  or      r9d, 0F003Fh; samDesired
0x140007d2e  mov     [rsp+0C0h+phkResult], rax; phkResult
0x140007d33  xor     r8d, r8d; ulOptions
0x140007d36  call    cs:__imp_RegOpenKeyExW
0x140007d3d  nop     dword ptr [rax+rax+00h]
0x140007d42  mov     ebx, eax
0x140007d44  test    eax, eax
0x140007d46  jnz     loc_14000801C
0x140007d4c  mov     rcx, [rbp+57h+hKey]; hKey
0x140007d50  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x140007d54  mov     [rsp+58h], r14; lpftLastWriteTime
0x140007d59  xor     r9d, r9d; lpReserved
0x140007d5c  mov     [rsp+0C0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x140007d61  xor     r8d, r8d; lpcchClass
0x140007d64  mov     [rsp+0C0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x140007d69  xor     edx, edx; lpClass
0x140007d6b  mov     [rsp+0C0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x140007d70  mov     [rsp+0C0h+lpcValues], r14; lpcValues
0x140007d75  mov     [rsp+0C0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x140007d7a  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x140007d7f  lea     rax, [rbp+57h+cSubKeys]
0x140007d83  mov     [rsp+0C0h+phkResult], rax; lpcSubKeys
0x140007d88  call    cs:__imp_RegQueryInfoKeyW
0x140007d8f  nop     dword ptr [rax+rax+00h]
0x140007d94  mov     ebx, eax
0x140007d96  test    eax, eax
0x140007d98  jz      short loc_140007DBC
0x140007d9a  mov     rcx, [rbp+57h+hKey]; hKey
0x140007d9e  test    rcx, rcx
0x140007da1  jz      loc_14000801C
0x140007da7  call    cs:__imp_RegCloseKey
0x140007dae  nop     dword ptr [rax+rax+00h]
0x140007db3  mov     [rbp+57h+hKey], r14
0x140007db7  jmp     loc_14000801C
0x140007dbc  cmp     [rbp+57h+cSubKeys], r14d
0x140007dc0  jnz     short loc_140007DFF
0x140007dc2  mov     rcx, [rbp+57h+hKey]; hKey
0x140007dc6  test    rcx, rcx
0x140007dc9  jz      short loc_140007DDB
0x140007dcb  call    cs:__imp_RegCloseKey
0x140007dd2  nop     dword ptr [rax+rax+00h]
0x140007dd7  mov     [rbp+57h+hKey], r14
0x140007ddb  mov     r8d, [r12+8Ch]; samDesired
0x140007de3  xor     r9d, r9d; Reserved
0x140007de6  mov     rdx, rdi; lpSubKey
0x140007de9  mov     rcx, rsi; hKey
0x140007dec  call    cs:__imp_RegDeleteKeyExW
0x140007df3  nop     dword ptr [rax+rax+00h]
0x140007df8  mov     ebx, eax
0x140007dfa  jmp     loc_14000801C
0x140007dff  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x140007e02  test    eax, eax
0x140007e04  jnz     short loc_140007E0F
0x140007e06  mov     [rbp+57h+cbMaxSubKeyLen], 100h
0x140007e0d  jmp     short loc_140007E1B
0x140007e0f  cmp     eax, 100h
0x140007e14  jnb     short loc_140007E1B
0x140007e16  add     eax, eax
0x140007e18  mov     [rbp+57h+cbMaxSubKeyLen], eax
0x140007e1b  call    CreateDynamicArray
0x140007e20  mov     [rbp+57h+var_48], rax
0x140007e24  mov     r13, rax
0x140007e27  test    rax, rax
0x140007e2a  jnz     short loc_140007E4F
0x140007e2c  mov     rcx, [rbp+57h+hKey]; hKey
0x140007e30  test    rcx, rcx
0x140007e33  jz      short loc_140007E45
0x140007e35  call    cs:__imp_RegCloseKey
0x140007e3c  nop     dword ptr [rax+rax+00h]
0x140007e41  mov     [rbp+57h+hKey], r14
0x140007e45  mov     ebx, 0Eh
0x140007e4a  jmp     loc_14000801C
0x140007e4f  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x140007e52  inc     ecx
0x140007e54  mov     [rbp+57h+cbMaxSubKeyLen], ecx
0x140007e57  lea     ecx, ds:4[rcx*2]; dwBytes
0x140007e5e  call    AllocateMemory
0x140007e63  mov     [rbp+57h+var_40], rax
0x140007e67  mov     rdi, rax
0x140007e6a  test    rax, rax
0x140007e6d  jnz     short loc_140007E93
0x140007e6f  mov     rcx, [rbp+57h+hKey]; hKey
0x140007e73  test    rcx, rcx
0x140007e76  jz      short loc_140007E88
0x140007e78  call    cs:__imp_RegCloseKey
0x140007e7f  nop     dword ptr [rax+rax+00h]
0x140007e84  mov     [rbp+57h+hKey], r14
0x140007e88  lea     rcx, [rbp+57h+var_48]
0x140007e8c  call    DestroyDynamicArray
0x140007e91  jmp     short loc_140007E45
0x140007e93  xor     esi, esi
0x140007e95  mov     r15d, r14d
0x140007e98  lea     ebx, [rsi+0Eh]
0x140007e9b  cmp     [rbp+57h+cSubKeys], esi
0x140007e9e  jbe     short loc_140007F16
0x140007ea0  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x140007ea3  mov     ecx, eax
0x140007ea5  mov     [rbp+57h+cchName], eax
0x140007ea8  mov     rax, rdi
0x140007eab  add     rcx, rcx
0x140007eae  jz      short loc_140007EBC
0x140007eb0  mov     byte ptr [rax], 0
0x140007eb3  inc     rax
0x140007eb6  sub     rcx, 1
0x140007eba  jnz     short loc_140007EB0
0x140007ebc  mov     rcx, [rbp+57h+hKey]; hKey
0x140007ec0  lea     r9, [rbp+57h+cchName]; lpcchName
0x140007ec4  mov     [rsp+0C0h+lpcValues], 0; lpftLastWriteTime
0x140007ecd  mov     r8, rdi; lpName
0x140007ed0  mov     [rsp+0C0h+lpcbMaxClassLen], 0; lpcchClass
0x140007ed9  mov     edx, r15d; dwIndex
0x140007edc  mov     [rsp+0C0h+lpcbMaxSubKeyLen], 0; lpClass
0x140007ee5  mov     [rsp+0C0h+phkResult], 0; lpReserved
0x140007eee  call    cs:__imp_RegEnumKeyExW
0x140007ef5  nop     dword ptr [rax+rax+00h]
0x140007efa  mov     r14d, eax
0x140007efd  test    eax, eax
0x140007eff  jnz     short loc_140007F2C
0x140007f01  mov     rdx, rdi
0x140007f04  mov     rcx, r13
0x140007f07  call    DynArrayAppendString
0x140007f0c  cmp     eax, 0FFFFFFFFh
0x140007f0f  jnz     short loc_140007F31
0x140007f11  mov     esi, ebx
0x140007f13  mov     r14d, ebx
0x140007f16  lea     rcx, [rbp+57h+var_40]
0x140007f1a  call    FreeMemory
0x140007f1f  cmp     dword ptr [r13+0], 9
0x140007f24  jnz     short loc_140007F40
0x140007f26  mov     edi, [r13+4]
0x140007f2a  jmp     short loc_140007F42
0x140007f2c  test    esi, esi
0x140007f2e  cmovz   esi, eax
0x140007f31  inc     r15d
0x140007f34  cmp     r15d, [rbp+57h+cSubKeys]
0x140007f38  jb      loc_140007EA0
0x140007f3e  jmp     short loc_140007F16
0x140007f40  xor     edi, edi
0x140007f42  cmp     r14d, ebx
0x140007f45  jz      short loc_140007FC5
0x140007f47  xor     r14d, r14d
0x140007f4a  test    edi, edi
0x140007f4c  jz      short loc_140007FC8
0x140007f4e  mov     r15d, [rbp+57h+arg_10]
0x140007f52  mov     ebx, r14d
0x140007f55  mov     [rbp+57h+cchName], r14d
0x140007f59  mov     esi, r14d
0x140007f5c  xor     r8d, r8d
0x140007f5f  mov     edx, esi
0x140007f61  mov     rcx, r13
0x140007f64  call    __DynArrayGetItem
0x140007f69  test    rax, rax
0x140007f6c  jnz     short loc_140007F72
0x140007f6e  xor     edx, edx
0x140007f70  jmp     short loc_140007F7F
0x140007f72  cmp     dword ptr [rax+4], 20000h
0x140007f79  jnz     short loc_140007F6E
0x140007f7b  mov     rdx, [rax+10h]
0x140007f7f  mov     rcx, [rbp+57h+hKey]
0x140007f83  lea     r8d, [r15+1]
0x140007f87  mov     r9, r12
0x140007f8a  call    RecursiveDeleteKey
0x140007f8f  test    eax, eax
0x140007f91  jz      short loc_140007F9E
0x140007f93  test    ebx, ebx
0x140007f95  jnz     short loc_140007F99
0x140007f97  mov     ebx, eax
0x140007f99  mov     eax, [rbp+57h+cchName]
0x140007f9c  jmp     short loc_140007FA6
0x140007f9e  mov     eax, [rbp+57h+cchName]
0x140007fa1  inc     eax
0x140007fa3  mov     [rbp+57h+cchName], eax
0x140007fa6  inc     esi
0x140007fa8  cmp     esi, edi
0x140007faa  jb      short loc_140007F5C
0x140007fac  test    eax, eax
0x140007fae  jz      short loc_140007FCE
0x140007fb0  cmp     edi, [rbp+57h+cSubKeys]
0x140007fb3  jnz     short loc_140007FBE
0x140007fb5  cmp     eax, edi
0x140007fb7  jnz     short loc_140007FBE
0x140007fb9  mov     ebx, r14d
0x140007fbc  jmp     short loc_140007FCE
0x140007fbe  mov     ebx, 80030201h
0x140007fc3  jmp     short loc_140007FCE
0x140007fc5  xor     r14d, r14d
0x140007fc8  mov     r15d, [rbp+57h+arg_10]
0x140007fcc  mov     ebx, esi
0x140007fce  lea     rcx, [rbp+57h+var_48]
0x140007fd2  call    DestroyDynamicArray
0x140007fd7  mov     rcx, [rbp+57h+hKey]; hKey
0x140007fdb  test    rcx, rcx
0x140007fde  jz      short loc_140007FF0
0x140007fe0  call    cs:__imp_RegCloseKey
0x140007fe7  nop     dword ptr [rax+rax+00h]
0x140007fec  mov     [rbp+57h+hKey], r14
0x140007ff0  test    ebx, ebx
0x140007ff2  jnz     short loc_140008020
0x140007ff4  mov     r8d, [r12+8Ch]; samDesired
0x140007ffc  xor     r9d, r9d; Reserved
0x140007fff  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140008003  mov     rcx, [rbp+57h+arg_0]; hKey
0x140008007  call    cs:__imp_RegDeleteKeyExW
0x14000800e  nop     dword ptr [rax+rax+00h]
0x140008013  mov     ebx, eax
0x140008015  jmp     short loc_140008020
0x140008017  mov     ebx, 57h ; 'W'
0x14000801c  mov     r15d, [rbp+57h+arg_10]
0x140008020  test    r15d, r15d
0x140008023  jnz     short loc_14000807E
0x140008025  test    ebx, ebx
0x140008027  jz      short loc_140008060
0x140008029  cmp     ebx, 80030201h
0x14000802f  jnz     short loc_140008048
0x140008031  xor     r8d, r8d
0x140008034  mov     edx, 8Dh
0x140008039  call    GetResString2FromModule
0x14000803e  mov     rcx, rax
0x140008041  call    SetReason
0x140008046  jmp     short loc_14000804F
0x140008048  mov     ecx, ebx
0x14000804a  call    SaveErrorMessage
0x14000804f  mov     ecx, 2; Ix
0x140008054  call    _o___acrt_iob_func_0
0x140008059  mov     edx, 20001h
0x14000805e  jmp     short loc_140008076
0x140008060  xor     ecx, ecx
0x140008062  call    SaveErrorMessage
0x140008067  mov     ecx, 1; Ix
0x14000806c  call    _o___acrt_iob_func_0
0x140008071  mov     edx, 20000h
0x140008076  mov     rcx, rax
0x140008079  call    ShowLastErrorEx
0x14000807e  mov     eax, ebx
0x140008080  mov     rbx, [rsp+0C0h+arg_18]
0x140008088  add     rsp, 90h
0x14000808f  pop     r15
0x140008091  pop     r14
0x140008093  pop     r13
0x140008095  pop     r12
0x140008097  pop     rdi
0x140008098  pop     rsi
0x140008099  pop     rbp
0x14000809a  retn
```
