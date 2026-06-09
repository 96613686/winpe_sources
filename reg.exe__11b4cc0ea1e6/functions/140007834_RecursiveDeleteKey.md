# RecursiveDeleteKey

- ea: `0x140007834`
- end: `0x140007bd7`
- name: `RecursiveDeleteKey`
- size: `931`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, int, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140006f9c`
- `0x140007834`

## callees

- `0x140001bb2`
- `0x140002b70`
- `0x140007834`
- `0x14000c62c`
- `0x14000c9c0`
- `0x14000cd48`
- `0x14000da24`
- `0x14000dc24`
- `0x14000e604`
- `0x14000e634`
- `0x14000e7a4`
- `0x14000ec3c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400078ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400078ae`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140007a3c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x140007a3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007913`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007931`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000798f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400079cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007b28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007913`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007931`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000798f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400079cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007b28`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14000794c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140007b49`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x14000794c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140007b49`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400078fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1400078fa`

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
  __int64 v31[8]; // [rsp+88h] [rbp+17h] BYREF
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
0x140007834  mov     rax, rsp
0x140007837  mov     [rax+20h], rbx
0x14000783b  mov     [rax+18h], r8d
0x14000783f  mov     [rax+10h], rdx
0x140007843  mov     [rax+8], rcx
0x140007847  push    rbp
0x140007848  push    rsi
0x140007849  push    rdi
0x14000784a  push    r12
0x14000784c  push    r13
0x14000784e  push    r14
0x140007850  push    r15
0x140007852  lea     rbp, [rax-5Fh]
0x140007856  sub     rsp, 90h
0x14000785d  xor     r14d, r14d
0x140007860  mov     r12, r9
0x140007863  mov     [rbp+57h+cchName], r14d
0x140007867  mov     rdi, rdx
0x14000786a  mov     [rbp+57h+hKey], r14
0x14000786e  mov     rsi, rcx
0x140007871  mov     [rbp+57h+cSubKeys], r14d
0x140007875  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x140007879  test    rcx, rcx
0x14000787c  jz      loc_140007B53
0x140007882  test    rdx, rdx
0x140007885  jz      loc_140007B53
0x14000788b  test    r9, r9
0x14000788e  jz      loc_140007B53
0x140007894  mov     r9d, [r9+8Ch]
0x14000789b  lea     rax, [rbp+57h+hKey]
0x14000789f  or      r9d, 0F003Fh; samDesired
0x1400078a6  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1400078ab  xor     r8d, r8d; ulOptions
0x1400078ae  call    cs:__imp_RegOpenKeyExW
0x1400078b4  mov     ebx, eax
0x1400078b6  test    eax, eax
0x1400078b8  jnz     loc_140007B58
0x1400078be  mov     rcx, [rbp+57h+hKey]; hKey
0x1400078c2  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1400078c6  mov     [rsp+58h], r14; lpftLastWriteTime
0x1400078cb  xor     r9d, r9d; lpReserved
0x1400078ce  mov     [rsp+0C0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1400078d3  xor     r8d, r8d; lpcchClass
0x1400078d6  mov     [rsp+0C0h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1400078db  xor     edx, edx; lpClass
0x1400078dd  mov     [rsp+0C0h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1400078e2  mov     [rsp+0C0h+lpcValues], r14; lpcValues
0x1400078e7  mov     [rsp+0C0h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1400078ec  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1400078f1  lea     rax, [rbp+57h+cSubKeys]
0x1400078f5  mov     [rsp+0C0h+phkResult], rax; lpcSubKeys
0x1400078fa  call    cs:__imp_RegQueryInfoKeyW
0x140007900  mov     ebx, eax
0x140007902  test    eax, eax
0x140007904  jz      short loc_140007922
0x140007906  mov     rcx, [rbp+57h+hKey]; hKey
0x14000790a  test    rcx, rcx
0x14000790d  jz      loc_140007B58
0x140007913  call    cs:__imp_RegCloseKey
0x140007919  mov     [rbp+57h+hKey], r14
0x14000791d  jmp     loc_140007B58
0x140007922  cmp     [rbp+57h+cSubKeys], r14d
0x140007926  jnz     short loc_140007959
0x140007928  mov     rcx, [rbp+57h+hKey]; hKey
0x14000792c  test    rcx, rcx
0x14000792f  jz      short loc_14000793B
0x140007931  call    cs:__imp_RegCloseKey
0x140007937  mov     [rbp+57h+hKey], r14
0x14000793b  mov     r8d, [r12+8Ch]; samDesired
0x140007943  xor     r9d, r9d; Reserved
0x140007946  mov     rdx, rdi; lpSubKey
0x140007949  mov     rcx, rsi; hKey
0x14000794c  call    cs:__imp_RegDeleteKeyExW
0x140007952  mov     ebx, eax
0x140007954  jmp     loc_140007B58
0x140007959  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x14000795c  test    eax, eax
0x14000795e  jnz     short loc_140007969
0x140007960  mov     [rbp+57h+cbMaxSubKeyLen], 100h
0x140007967  jmp     short loc_140007975
0x140007969  cmp     eax, 100h
0x14000796e  jnb     short loc_140007975
0x140007970  add     eax, eax
0x140007972  mov     [rbp+57h+cbMaxSubKeyLen], eax
0x140007975  call    CreateDynamicArray
0x14000797a  mov     [rbp+57h+var_48], rax
0x14000797e  mov     r13, rax
0x140007981  test    rax, rax
0x140007984  jnz     short loc_1400079A3
0x140007986  mov     rcx, [rbp+57h+hKey]; hKey
0x14000798a  test    rcx, rcx
0x14000798d  jz      short loc_140007999
0x14000798f  call    cs:__imp_RegCloseKey
0x140007995  mov     [rbp+57h+hKey], r14
0x140007999  mov     ebx, 0Eh
0x14000799e  jmp     loc_140007B58
0x1400079a3  mov     ecx, [rbp+57h+cbMaxSubKeyLen]
0x1400079a6  inc     ecx
0x1400079a8  mov     [rbp+57h+cbMaxSubKeyLen], ecx
0x1400079ab  lea     ecx, ds:4[rcx*2]; dwBytes
0x1400079b2  call    AllocateMemory
0x1400079b7  mov     [rbp+57h+var_40], rax
0x1400079bb  mov     rdi, rax
0x1400079be  test    rax, rax
0x1400079c1  jnz     short loc_1400079E1
0x1400079c3  mov     rcx, [rbp+57h+hKey]; hKey
0x1400079c7  test    rcx, rcx
0x1400079ca  jz      short loc_1400079D6
0x1400079cc  call    cs:__imp_RegCloseKey
0x1400079d2  mov     [rbp+57h+hKey], r14
0x1400079d6  lea     rcx, [rbp+57h+var_48]
0x1400079da  call    DestroyDynamicArray
0x1400079df  jmp     short loc_140007999
0x1400079e1  xor     esi, esi
0x1400079e3  mov     r15d, r14d
0x1400079e6  lea     ebx, [rsi+0Eh]
0x1400079e9  cmp     [rbp+57h+cSubKeys], esi
0x1400079ec  jbe     short loc_140007A5E
0x1400079ee  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1400079f1  mov     ecx, eax
0x1400079f3  mov     [rbp+57h+cchName], eax
0x1400079f6  mov     rax, rdi
0x1400079f9  add     rcx, rcx
0x1400079fc  jz      short loc_140007A0A
0x1400079fe  mov     byte ptr [rax], 0
0x140007a01  inc     rax
0x140007a04  sub     rcx, 1
0x140007a08  jnz     short loc_1400079FE
0x140007a0a  mov     rcx, [rbp+57h+hKey]; hKey
0x140007a0e  lea     r9, [rbp+57h+cchName]; lpcchName
0x140007a12  mov     [rsp+0C0h+lpcValues], 0; lpftLastWriteTime
0x140007a1b  mov     r8, rdi; lpName
0x140007a1e  mov     [rsp+0C0h+lpcbMaxClassLen], 0; lpcchClass
0x140007a27  mov     edx, r15d; dwIndex
0x140007a2a  mov     [rsp+0C0h+lpcbMaxSubKeyLen], 0; lpClass
0x140007a33  mov     [rsp+0C0h+phkResult], 0; lpReserved
0x140007a3c  call    cs:__imp_RegEnumKeyExW
0x140007a42  mov     r14d, eax
0x140007a45  test    eax, eax
0x140007a47  jnz     short loc_140007A74
0x140007a49  mov     rdx, rdi
0x140007a4c  mov     rcx, r13
0x140007a4f  call    DynArrayAppendString
0x140007a54  cmp     eax, 0FFFFFFFFh
0x140007a57  jnz     short loc_140007A79
0x140007a59  mov     esi, ebx
0x140007a5b  mov     r14d, ebx
0x140007a5e  lea     rcx, [rbp+57h+var_40]
0x140007a62  call    FreeMemory
0x140007a67  cmp     dword ptr [r13+0], 9
0x140007a6c  jnz     short loc_140007A88
0x140007a6e  mov     edi, [r13+4]
0x140007a72  jmp     short loc_140007A8A
0x140007a74  test    esi, esi
0x140007a76  cmovz   esi, eax
0x140007a79  inc     r15d
0x140007a7c  cmp     r15d, [rbp+57h+cSubKeys]
0x140007a80  jb      loc_1400079EE
0x140007a86  jmp     short loc_140007A5E
0x140007a88  xor     edi, edi
0x140007a8a  cmp     r14d, ebx
0x140007a8d  jz      short loc_140007B0D
0x140007a8f  xor     r14d, r14d
0x140007a92  test    edi, edi
0x140007a94  jz      short loc_140007B10
0x140007a96  mov     r15d, [rbp+57h+arg_10]
0x140007a9a  mov     ebx, r14d
0x140007a9d  mov     [rbp+57h+cchName], r14d
0x140007aa1  mov     esi, r14d
0x140007aa4  xor     r8d, r8d
0x140007aa7  mov     edx, esi
0x140007aa9  mov     rcx, r13
0x140007aac  call    __DynArrayGetItem
0x140007ab1  test    rax, rax
0x140007ab4  jnz     short loc_140007ABA
0x140007ab6  xor     edx, edx
0x140007ab8  jmp     short loc_140007AC7
0x140007aba  cmp     dword ptr [rax+4], 20000h
0x140007ac1  jnz     short loc_140007AB6
0x140007ac3  mov     rdx, [rax+10h]
0x140007ac7  mov     rcx, [rbp+57h+hKey]
0x140007acb  lea     r8d, [r15+1]
0x140007acf  mov     r9, r12
0x140007ad2  call    RecursiveDeleteKey
0x140007ad7  test    eax, eax
0x140007ad9  jz      short loc_140007AE6
0x140007adb  test    ebx, ebx
0x140007add  jnz     short loc_140007AE1
0x140007adf  mov     ebx, eax
0x140007ae1  mov     eax, [rbp+57h+cchName]
0x140007ae4  jmp     short loc_140007AEE
0x140007ae6  mov     eax, [rbp+57h+cchName]
0x140007ae9  inc     eax
0x140007aeb  mov     [rbp+57h+cchName], eax
0x140007aee  inc     esi
0x140007af0  cmp     esi, edi
0x140007af2  jb      short loc_140007AA4
0x140007af4  test    eax, eax
0x140007af6  jz      short loc_140007B16
0x140007af8  cmp     edi, [rbp+57h+cSubKeys]
0x140007afb  jnz     short loc_140007B06
0x140007afd  cmp     eax, edi
0x140007aff  jnz     short loc_140007B06
0x140007b01  mov     ebx, r14d
0x140007b04  jmp     short loc_140007B16
0x140007b06  mov     ebx, 80030201h
0x140007b0b  jmp     short loc_140007B16
0x140007b0d  xor     r14d, r14d
0x140007b10  mov     r15d, [rbp+57h+arg_10]
0x140007b14  mov     ebx, esi
0x140007b16  lea     rcx, [rbp+57h+var_48]
0x140007b1a  call    DestroyDynamicArray
0x140007b1f  mov     rcx, [rbp+57h+hKey]; hKey
0x140007b23  test    rcx, rcx
0x140007b26  jz      short loc_140007B32
0x140007b28  call    cs:__imp_RegCloseKey
0x140007b2e  mov     [rbp+57h+hKey], r14
0x140007b32  test    ebx, ebx
0x140007b34  jnz     short loc_140007B5C
0x140007b36  mov     r8d, [r12+8Ch]; samDesired
0x140007b3e  xor     r9d, r9d; Reserved
0x140007b41  mov     rdx, [rbp+57h+lpSubKey]; lpSubKey
0x140007b45  mov     rcx, [rbp+57h+arg_0]; hKey
0x140007b49  call    cs:__imp_RegDeleteKeyExW
0x140007b4f  mov     ebx, eax
0x140007b51  jmp     short loc_140007B5C
0x140007b53  mov     ebx, 57h ; 'W'
0x140007b58  mov     r15d, [rbp+57h+arg_10]
0x140007b5c  test    r15d, r15d
0x140007b5f  jnz     short loc_140007BBA
0x140007b61  test    ebx, ebx
0x140007b63  jz      short loc_140007B9C
0x140007b65  cmp     ebx, 80030201h
0x140007b6b  jnz     short loc_140007B84
0x140007b6d  xor     r8d, r8d
0x140007b70  mov     edx, 8Dh
0x140007b75  call    GetResString2FromModule
0x140007b7a  mov     rcx, rax
0x140007b7d  call    SetReason
0x140007b82  jmp     short loc_140007B8B
0x140007b84  mov     ecx, ebx
0x140007b86  call    SaveErrorMessage
0x140007b8b  mov     ecx, 2; Ix
0x140007b90  call    _o___acrt_iob_func_0
0x140007b95  mov     edx, 20001h
0x140007b9a  jmp     short loc_140007BB2
0x140007b9c  xor     ecx, ecx
0x140007b9e  call    SaveErrorMessage
0x140007ba3  mov     ecx, 1; Ix
0x140007ba8  call    _o___acrt_iob_func_0
0x140007bad  mov     edx, 20000h
0x140007bb2  mov     rcx, rax
0x140007bb5  call    ShowLastErrorEx
0x140007bba  mov     eax, ebx
0x140007bbc  mov     rbx, [rsp+0C0h+arg_18]
0x140007bc4  add     rsp, 90h
0x140007bcb  pop     r15
0x140007bcd  pop     r14
0x140007bcf  pop     r13
0x140007bd1  pop     r12
0x140007bd3  pop     rdi
0x140007bd4  pop     rsi
0x140007bd5  pop     rbp
0x140007bd6  retn
```
