# ReadRegSpec

- ea: `0x100249dd`
- end: `0x10024c99`
- name: `ReadRegSpec`
- size: `700`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x10006bd0`

## callees

- `0x10006390`
- `0x10006400`
- `0x10018b80`
- `0x100249dd`
- `0x100331da`
- `0x1003325b`
- `0x10035510`
- `0x10035530`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10024c65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10024c88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10024c65`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x10024c88`

## pseudocode

```c
int __fastcall ReadRegSpec(int a1, int a2, _WORD *a3, int **a4)
{
  int v5; // eax
  int *v6; // esi
  int v7; // edx
  int v8; // edx
  int v9; // edx
  DWORD cbData; // [esp+Ch] [ebp-924h] BYREF
  BYTE v12; // [esp+13h] [ebp-91Dh] BYREF
  DWORD Type; // [esp+14h] [ebp-91Ch] BYREF
  HKEY hKey; // [esp+18h] [ebp-918h] BYREF
  BYTE v15[4]; // [esp+1Ch] [ebp-914h] BYREF
  WCHAR SubKey[128]; // [esp+20h] [ebp-910h] BYREF
  BYTE Data[2]; // [esp+120h] [ebp-810h] BYREF

  cbData = 128;
  if ( !*a3 )
    return 0;
  WCSCPY2(SubKey, a3, 0x80u);
  WCSCAT2(SubKey, L"\\Engines\\", 0x80u);
  WCSCAT2(SubKey, L"Excel", 0x80u);
  v5 = -2147483646;
  if ( a2 )
    v5 = a2;
  if ( JetRegOpenKeyW((HKEY)v5, SubKey, &hKey) )
    return 0;
  v6 = *a4;
  if ( !*a4 )
  {
LABEL_37:
    RegCloseKey(hKey);
    return 0;
  }
  while ( 1 )
  {
    switch ( *((_BYTE *)v6 + 4) )
    {
      case 0:
        cbData = 1025;
        if ( !JetRegQueryValueExW(hKey, (LPCWSTR)v6[2], 0, &Type, Data, &cbData) && (int)cbData > 0 && Type == 1 )
        {
          if ( 2 * cbData >= 0x804 )
LABEL_40:
            __report_rangecheckfailure();
          *(_WORD *)&Data[2 * cbData] = 0;
          WCSCPY2((_WORD *)v6[3], Data, v6[4]);
        }
        goto LABEL_36;
      case 1:
        cbData = 4;
        if ( !JetRegQueryValueExW(hKey, (LPCWSTR)v6[2], 0, &Type, v15, &cbData) && (int)cbData > 0 && Type == 4 )
          *(_DWORD *)v6[3] = *(_DWORD *)v15;
        goto LABEL_36;
      case 2:
        cbData = 1;
        if ( !JetRegQueryValueExW(hKey, (LPCWSTR)v6[2], 0, &Type, &v12, &cbData) && (int)cbData > 0 && Type == 3 )
          *(_DWORD *)v6[3] = v12 != 0;
        goto LABEL_36;
    }
    if ( *((_BYTE *)v6 + 4) == 3 )
    {
      cbData = 2052;
      if ( !JetRegQueryValueExW(hKey, (LPCWSTR)v6[2], 0, &Type, Data, &cbData) && (int)cbData > 0 && Type == 1 )
        break;
    }
LABEL_36:
    v6 = (int *)*v6;
    if ( !v6 )
      goto LABEL_37;
  }
  if ( 2 * cbData >= 0x804 )
    goto LABEL_40;
  *(_WORD *)&Data[2 * cbData] = 0;
  v7 = v6[5];
  if ( v7 && !WCSICMP(Data, v7) )
  {
    *(_DWORD *)v6[3] = 0;
    goto LABEL_36;
  }
  v8 = v6[6];
  if ( v8 && !WCSICMP(Data, v8) )
  {
    *(_DWORD *)v6[3] = 1;
    goto LABEL_36;
  }
  v9 = v6[7];
  if ( v9 && !WCSICMP(Data, v9) )
  {
    *(_DWORD *)v6[3] = 2;
    goto LABEL_36;
  }
  RegCloseKey(hKey);
  return *((unsigned __int8 *)v6 + 5);
}

```

## disassembly

```asm
0x100249dd  mov     edi, edi
0x100249df  push    ebp
0x100249e0  mov     ebp, esp
0x100249e2  and     esp, 0FFFFFFF8h
0x100249e5  sub     esp, 924h
0x100249eb  mov     eax, ___security_cookie
0x100249f0  xor     eax, esp
0x100249f2  mov     [esp+924h+var_4], eax
0x100249f9  push    ebx
0x100249fa  push    esi
0x100249fb  mov     esi, [ebp+arg_4]
0x100249fe  xor     ebx, ebx
0x10024a00  push    edi
0x10024a01  mov     edi, edx
0x10024a03  mov     eax, 80h
0x10024a08  mov     edx, [ebp+arg_0]
0x10024a0b  mov     [esp+930h+cbData], eax
0x10024a0f  cmp     [edx], bx
0x10024a12  jz      loc_10024C6B
0x10024a18  push    eax
0x10024a19  lea     ecx, [esp+934h+SubKey]
0x10024a1d  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10024a22  push    80h
0x10024a27  mov     edx, offset aEngines; "\\Engines\\"
0x10024a2c  lea     ecx, [esp+934h+SubKey]
0x10024a30  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10024a35  push    80h
0x10024a3a  mov     edx, offset aExcel; "Excel"
0x10024a3f  lea     ecx, [esp+934h+SubKey]
0x10024a43  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10024a48  lea     eax, [esp+930h+hKey]
0x10024a4c  test    edi, edi
0x10024a4e  push    eax; phkResult
0x10024a4f  lea     eax, [esp+934h+SubKey]
0x10024a53  push    eax; lpSubKey
0x10024a54  mov     eax, 80000002h
0x10024a59  cmovnz  eax, edi
0x10024a5c  push    eax; hKey
0x10024a5d  call    _JetRegOpenKeyW@12; JetRegOpenKeyW(x,x,x)
0x10024a62  test    eax, eax
0x10024a64  jnz     loc_10024C6B
0x10024a6a  mov     esi, [esi]
0x10024a6c  test    esi, esi
0x10024a6e  jz      loc_10024C61
0x10024a74  xor     edi, edi
0x10024a76  inc     edi
0x10024a77  movzx   eax, byte ptr [esi+4]
0x10024a7b  sub     eax, ebx
0x10024a7d  jz      loc_10024BF9
0x10024a83  sub     eax, 1
0x10024a86  jz      loc_10024BB9
0x10024a8c  sub     eax, 1
0x10024a8f  jz      loc_10024B69
0x10024a95  sub     eax, 1
0x10024a98  jnz     loc_10024C57
0x10024a9e  lea     eax, [esp+930h+cbData]
0x10024aa2  mov     [esp+930h+cbData], 804h
0x10024aaa  push    eax; lpcbData
0x10024aab  lea     eax, [esp+934h+Data]
0x10024ab2  push    eax; lpData
0x10024ab3  lea     eax, [esp+938h+Type]
0x10024ab7  push    eax; lpType
0x10024ab8  push    ebx; lpReserved
0x10024ab9  push    dword ptr [esi+8]; lpValueName
0x10024abc  push    [esp+944h+hKey]; hKey
0x10024ac0  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x10024ac5  test    eax, eax
0x10024ac7  jnz     loc_10024C57
0x10024acd  mov     eax, [esp+930h+cbData]
0x10024ad1  test    eax, eax
0x10024ad3  jle     loc_10024C57
0x10024ad9  cmp     [esp+930h+Type], edi
0x10024add  jnz     loc_10024C57
0x10024ae3  add     eax, eax
0x10024ae5  cmp     eax, 804h
0x10024aea  jnb     loc_10024C94
0x10024af0  xor     ecx, ecx
0x10024af2  mov     word ptr [esp+eax+930h+Data], cx
0x10024afa  mov     edx, [esi+14h]
0x10024afd  test    edx, edx
0x10024aff  jz      short loc_10024B1B
0x10024b01  lea     ecx, [esp+930h+Data]
0x10024b08  call    _WCSICMP@8; WCSICMP(x,x)
0x10024b0d  test    eax, eax
0x10024b0f  jnz     short loc_10024B1B
0x10024b11  mov     eax, [esi+0Ch]
0x10024b14  mov     [eax], ebx
0x10024b16  jmp     loc_10024C57
0x10024b1b  mov     edx, [esi+18h]
0x10024b1e  test    edx, edx
0x10024b20  jz      short loc_10024B3C
0x10024b22  lea     ecx, [esp+930h+Data]
0x10024b29  call    _WCSICMP@8; WCSICMP(x,x)
0x10024b2e  test    eax, eax
0x10024b30  jnz     short loc_10024B3C
0x10024b32  mov     eax, [esi+0Ch]
0x10024b35  mov     [eax], edi
0x10024b37  jmp     loc_10024C57
0x10024b3c  mov     edx, [esi+1Ch]
0x10024b3f  test    edx, edx
0x10024b41  jz      loc_10024C84
0x10024b47  lea     ecx, [esp+930h+Data]
0x10024b4e  call    _WCSICMP@8; WCSICMP(x,x)
0x10024b53  test    eax, eax
0x10024b55  jnz     loc_10024C84
0x10024b5b  mov     eax, [esi+0Ch]
0x10024b5e  mov     dword ptr [eax], 2
0x10024b64  jmp     loc_10024C57
0x10024b69  lea     eax, [esp+930h+cbData]
0x10024b6d  mov     [esp+930h+cbData], edi
0x10024b71  push    eax; lpcbData
0x10024b72  lea     eax, [esp+934h+var_91D]
0x10024b76  push    eax; lpData
0x10024b77  lea     eax, [esp+938h+Type]
0x10024b7b  push    eax; lpType
0x10024b7c  push    ebx; lpReserved
0x10024b7d  push    dword ptr [esi+8]; lpValueName
0x10024b80  push    [esp+944h+hKey]; hKey
0x10024b84  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x10024b89  test    eax, eax
0x10024b8b  jnz     loc_10024C57
0x10024b91  cmp     [esp+930h+cbData], ebx
0x10024b95  jle     loc_10024C57
0x10024b9b  cmp     [esp+930h+Type], 3
0x10024ba0  jnz     loc_10024C57
0x10024ba6  mov     eax, [esi+0Ch]
0x10024ba9  xor     ecx, ecx
0x10024bab  cmp     [esp+930h+var_91D], cl
0x10024baf  setnz   cl
0x10024bb2  mov     [eax], ecx
0x10024bb4  jmp     loc_10024C57
0x10024bb9  lea     eax, [esp+930h+cbData]
0x10024bbd  mov     [esp+930h+cbData], 4
0x10024bc5  push    eax; lpcbData
0x10024bc6  lea     eax, [esp+934h+var_914]
0x10024bca  push    eax; lpData
0x10024bcb  lea     eax, [esp+938h+Type]
0x10024bcf  push    eax; lpType
0x10024bd0  push    ebx; lpReserved
0x10024bd1  push    dword ptr [esi+8]; lpValueName
0x10024bd4  push    [esp+944h+hKey]; hKey
0x10024bd8  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x10024bdd  test    eax, eax
0x10024bdf  jnz     short loc_10024C57
0x10024be1  cmp     [esp+930h+cbData], ebx
0x10024be5  jle     short loc_10024C57
0x10024be7  cmp     [esp+930h+Type], 4
0x10024bec  jnz     short loc_10024C57
0x10024bee  mov     ecx, [esi+0Ch]
0x10024bf1  mov     eax, dword ptr [esp+930h+var_914]
0x10024bf5  mov     [ecx], eax
0x10024bf7  jmp     short loc_10024C57
0x10024bf9  lea     eax, [esp+930h+cbData]
0x10024bfd  mov     [esp+930h+cbData], 401h
0x10024c05  push    eax; lpcbData
0x10024c06  lea     eax, [esp+934h+Data]
0x10024c0d  push    eax; lpData
0x10024c0e  lea     eax, [esp+938h+Type]
0x10024c12  push    eax; lpType
0x10024c13  push    ebx; lpReserved
0x10024c14  push    dword ptr [esi+8]; lpValueName
0x10024c17  push    [esp+944h+hKey]; hKey
0x10024c1b  call    _JetRegQueryValueExW@24; JetRegQueryValueExW(x,x,x,x,x,x)
0x10024c20  test    eax, eax
0x10024c22  jnz     short loc_10024C57
0x10024c24  mov     eax, [esp+930h+cbData]
0x10024c28  test    eax, eax
0x10024c2a  jle     short loc_10024C57
0x10024c2c  cmp     [esp+930h+Type], edi
0x10024c30  jnz     short loc_10024C57
0x10024c32  add     eax, eax
0x10024c34  cmp     eax, 804h
0x10024c39  jnb     short loc_10024C94
0x10024c3b  xor     ecx, ecx
0x10024c3d  lea     edx, [esp+930h+Data]
0x10024c44  mov     word ptr [esp+eax+930h+Data], cx
0x10024c4c  push    dword ptr [esi+10h]
0x10024c4f  mov     ecx, [esi+0Ch]
0x10024c52  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10024c57  mov     esi, [esi]
0x10024c59  test    esi, esi
0x10024c5b  jnz     loc_10024A77
0x10024c61  push    [esp+930h+hKey]; hKey
0x10024c65  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10024c6b  xor     eax, eax
0x10024c6d  mov     ecx, [esp+930h+var_4]
0x10024c74  pop     edi
0x10024c75  pop     esi
0x10024c76  pop     ebx
0x10024c77  xor     ecx, esp; StackCookie
0x10024c79  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10024c7e  mov     esp, ebp
0x10024c80  pop     ebp
0x10024c81  retn    8
0x10024c84  push    [esp+930h+hKey]; hKey
0x10024c88  call    ds:__imp__RegCloseKey@4; RegCloseKey(x)
0x10024c8e  movzx   eax, byte ptr [esi+5]
0x10024c92  jmp     short loc_10024C6D
0x10024c94  call    ___report_rangecheckfailure
```
