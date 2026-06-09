# IERegEnumKeys

- ea: `0x180067b70`
- end: `0x180067e56`
- name: `IERegEnumKeys`
- size: `742`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18003f5c0`
- `0x180067b70`
- `0x180083c10`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067d0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067d0f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180067db3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180067db3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067e12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180067e12`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180067d59`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180067d59`

## pseudocode

```c
__int64 __fastcall IERegEnumKeys(
        unsigned int a1,
        __int64 (__fastcall *a2)(_QWORD, _QWORD, HKEY, WCHAR *, __int64),
        __int64 a3,
        int a4)
{
  __int64 v5; // r12
  int v7; // esi
  unsigned int v8; // r14d
  unsigned int v9; // ebx
  unsigned int v10; // edx
  int v11; // r10d
  int v12; // r9d
  __int64 v13; // rax
  unsigned int v14; // edx
  int v15; // r9d
  __int64 v16; // rax
  unsigned int i; // edi
  __int64 v18; // r15
  DWORD v19; // edx
  int v20; // eax
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cSubKeys; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  __int64 v24; // [rsp+70h] [rbp-90h]
  __int64 (__fastcall *v25)(_QWORD, _QWORD, HKEY, WCHAR *, __int64); // [rsp+78h] [rbp-88h]
  _DWORD v26[8]; // [rsp+80h] [rbp-80h]
  WCHAR Name[264]; // [rsp+A0h] [rbp-60h] BYREF

  v24 = a3;
  v25 = a2;
  v5 = a1;
  cSubKeys = 0;
  cchName = 0;
  hKey = 0;
  if ( a1 >= 0x55 )
    return 2147747588LL;
  if ( !a2 || (dword_1800E4BA4[10 * a1] & 0x280) == 0 )
    return 2147942487LL;
  v7 = 0;
  v8 = 0;
  IERegInit();
  v9 = 0;
  if ( (a4 & 0x10) != 0 )
  {
    v10 = 3;
    do
    {
      while ( 1 )
      {
        v11 = v10;
        if ( _bittest(&a4, v10) )
          break;
        v12 = dword_1800E4BA4[10 * v5];
        if ( (dword_18025DFD0[v10] & v12) != dword_18025DFD0[v10] )
          break;
        if ( !qword_18029A190[v10] )
          break;
        v13 = v9++;
        v26[v13] = v10;
        if ( (v12 & 0x200) == 0 || v10 != 3 )
          break;
        v26[v13] = 4;
        v10 = 2;
      }
      --v10;
    }
    while ( v11 > 0 );
  }
  else
  {
    v14 = 0;
    while ( 1 )
    {
      if ( !_bittest(&a4, v14) )
      {
        v15 = dword_1800E4BA4[10 * v5];
        if ( (dword_18025DFD0[v14] & v15) == dword_18025DFD0[v14] )
        {
          if ( qword_18029A190[v14] )
          {
            v16 = v9++;
            v26[v16] = v14;
            if ( (v15 & 0x200) != 0 && v14 == 3 )
              break;
          }
        }
      }
      if ( (int)++v14 > 3 )
        goto LABEL_24;
    }
    v26[v16] = 4;
  }
LABEL_24:
  for ( i = 0; i < v9; ++i )
  {
    if ( v7 )
      break;
    v18 = (int)v26[i];
    if ( !RegOpenKeyExW((HKEY)qword_18029A190[v18], (LPCWSTR)qword_1800E4B80[5 * v5], 0, 0x20019u, &hKey) )
    {
      if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0) )
      {
        for ( cchName = 260; ; cchName = 260 )
        {
          v19 = cSubKeys;
          if ( !cSubKeys )
            break;
          --cSubKeys;
          if ( RegEnumKeyExW(hKey, v19 - 1, Name, &cchName, 0, 0, 0, 0) )
            break;
          v20 = v25((unsigned int)v5, (unsigned int)v18, hKey, Name, v24);
          v8 = v20;
          if ( v20 == 263942 || v20 < 0 )
          {
            v7 = 1;
            cchName = 260;
            break;
          }
        }
      }
      RegCloseKey(hKey);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180067b70  mov     [rsp-8+arg_18], rbx
0x180067b75  push    rbp
0x180067b76  push    rsi
0x180067b77  push    rdi
0x180067b78  push    r12
0x180067b7a  push    r13
0x180067b7c  push    r14
0x180067b7e  push    r15
0x180067b80  lea     rbp, [rsp-1C0h]
0x180067b88  sub     rsp, 2C0h
0x180067b8f  mov     rax, cs:__security_cookie
0x180067b96  xor     rax, rsp
0x180067b99  mov     [rbp+1F0h+var_40], rax
0x180067ba0  xor     r15d, r15d
0x180067ba3  mov     [rsp+2F0h+var_280], r8
0x180067ba8  mov     [rsp+2F0h+var_278], rdx
0x180067bad  mov     edi, r9d
0x180067bb0  mov     r12d, ecx
0x180067bb3  mov     rax, rdx
0x180067bb6  mov     [rsp+2F0h+cSubKeys], r15d
0x180067bbb  mov     [rsp+2F0h+cchName], r15d
0x180067bc0  mov     [rsp+2F0h+hKey], r15
0x180067bc5  cmp     ecx, 55h ; 'U'
0x180067bc8  jb      short loc_180067BD4
0x180067bca  mov     eax, 80040704h
0x180067bcf  jmp     loc_180067E2C
0x180067bd4  test    rax, rax
0x180067bd7  jz      loc_180067E27
0x180067bdd  lea     r13, [r12+r12*4]
0x180067be1  lea     rax, __ImageBase
0x180067be8  test    ds:rva dword_1800E4BA4[rax+r13*8], 280h
0x180067bf4  jz      loc_180067E27
0x180067bfa  mov     esi, r15d
0x180067bfd  mov     r14d, r15d
0x180067c00  call    IERegInit
0x180067c05  mov     ebx, r15d
0x180067c08  test    dil, 10h
0x180067c0c  jz      short loc_180067C71
0x180067c0e  mov     edx, 3
0x180067c13  lea     r11, __ImageBase
0x180067c1a  bt      edi, edx
0x180067c1d  mov     r10d, edx
0x180067c20  jb      short loc_180067C68
0x180067c22  mov     r9d, ds:rva dword_1800E4BA4[r11+r13*8]
0x180067c2a  mov     eax, r9d
0x180067c2d  movsxd  r8, edx
0x180067c30  mov     ecx, ds:rva dword_18025DFD0[r11+r8*4]
0x180067c38  and     eax, ecx
0x180067c3a  cmp     eax, ecx
0x180067c3c  jnz     short loc_180067C68
0x180067c3e  cmp     rva qword_18029A190[r11+r8*8], r15
0x180067c46  jz      short loc_180067C68
0x180067c48  mov     eax, ebx
0x180067c4a  inc     ebx
0x180067c4c  mov     [rbp+rax*4+1F0h+var_270], edx
0x180067c50  bt      r9d, 9
0x180067c55  jnb     short loc_180067C68
0x180067c57  cmp     edx, 3
0x180067c5a  jnz     short loc_180067C68
0x180067c5c  mov     [rbp+rax*4+1F0h+var_270], 4
0x180067c64  dec     edx
0x180067c66  jmp     short loc_180067C1A
0x180067c68  dec     edx
0x180067c6a  test    r10d, r10d
0x180067c6d  jg      short loc_180067C1A
0x180067c6f  jmp     short loc_180067CCB
0x180067c71  mov     edx, r15d
0x180067c74  bt      edi, edx
0x180067c77  jb      short loc_180067CBA
0x180067c79  lea     r10, __ImageBase
0x180067c80  mov     r8d, edx
0x180067c83  mov     r9d, ds:rva dword_1800E4BA4[r10+r13*8]
0x180067c8b  mov     eax, r9d
0x180067c8e  mov     ecx, ds:rva dword_18025DFD0[r10+r8*4]
0x180067c96  and     eax, ecx
0x180067c98  cmp     eax, ecx
0x180067c9a  jnz     short loc_180067CBA
0x180067c9c  cmp     rva qword_18029A190[r10+r8*8], r15
0x180067ca4  jz      short loc_180067CBA
0x180067ca6  mov     eax, ebx
0x180067ca8  inc     ebx
0x180067caa  mov     [rbp+rax*4+1F0h+var_270], edx
0x180067cae  bt      r9d, 9
0x180067cb3  jnb     short loc_180067CBA
0x180067cb5  cmp     edx, 3
0x180067cb8  jz      short loc_180067CC3
0x180067cba  inc     edx
0x180067cbc  cmp     edx, 3
0x180067cbf  jle     short loc_180067C74
0x180067cc1  jmp     short loc_180067CCB
0x180067cc3  mov     [rbp+rax*4+1F0h+var_270], 4
0x180067ccb  mov     edi, r15d
0x180067cce  test    ebx, ebx
0x180067cd0  jz      loc_180067E22
0x180067cd6  test    esi, esi
0x180067cd8  jnz     loc_180067E22
0x180067cde  mov     eax, edi
0x180067ce0  mov     r9d, 20019h; samDesired
0x180067ce6  xor     r8d, r8d; ulOptions
0x180067ce9  movsxd  r15, [rbp+rax*4+1F0h+var_270]
0x180067cee  lea     rax, [rsp+2F0h+hKey]
0x180067cf3  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180067cf8  lea     rax, __ImageBase
0x180067cff  mov     rdx, ds:rva qword_1800E4B80[rax+r13*8]; lpSubKey
0x180067d07  mov     rcx, rva qword_18029A190[rax+r15*8]; hKey
0x180067d0f  call    cs:__imp_RegOpenKeyExW
0x180067d15  xor     ecx, ecx
0x180067d17  test    eax, eax
0x180067d19  jnz     loc_180067E18
0x180067d1f  mov     [rsp+2F0h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x180067d24  lea     rax, [rsp+2F0h+cSubKeys]
0x180067d29  mov     [rsp+2F0h+lpcbSecurityDescriptor], rcx; lpcbSecurityDescriptor
0x180067d2e  xor     r9d, r9d; lpReserved
0x180067d31  mov     [rsp+2F0h+lpcbMaxValueLen], rcx; lpcbMaxValueLen
0x180067d36  xor     r8d, r8d; lpcchClass
0x180067d39  mov     [rsp+2F0h+lpcbMaxValueNameLen], rcx; lpcbMaxValueNameLen
0x180067d3e  xor     edx, edx; lpClass
0x180067d40  mov     [rsp+2F0h+lpcValues], rcx; lpcValues
0x180067d45  mov     [rsp+2F0h+lpcbMaxClassLen], rcx; lpcbMaxClassLen
0x180067d4a  mov     [rsp+2F0h+lpcbMaxSubKeyLen], rcx; lpcbMaxSubKeyLen
0x180067d4f  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180067d54  mov     [rsp+2F0h+phkResult], rax; lpcSubKeys
0x180067d59  call    cs:__imp_RegQueryInfoKeyW
0x180067d5f  test    eax, eax
0x180067d61  jnz     loc_180067E0D
0x180067d67  mov     [rsp+2F0h+cchName], 104h
0x180067d6f  mov     edx, [rsp+2F0h+cSubKeys]
0x180067d73  test    edx, edx
0x180067d75  jz      loc_180067E0D
0x180067d7b  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180067d80  lea     r9, [rsp+2F0h+cchName]; lpcchName
0x180067d85  mov     [rsp+2F0h+lpcValues], 0; lpftLastWriteTime
0x180067d8e  lea     r8, [rbp+1F0h+Name]; lpName
0x180067d92  mov     [rsp+2F0h+lpcbMaxClassLen], 0; lpcchClass
0x180067d9b  dec     edx; dwIndex
0x180067d9d  mov     [rsp+2F0h+lpcbMaxSubKeyLen], 0; lpClass
0x180067da6  mov     [rsp+2F0h+phkResult], 0; lpReserved
0x180067daf  mov     [rsp+2F0h+cSubKeys], edx
0x180067db3  call    cs:__imp_RegEnumKeyExW
0x180067db9  test    eax, eax
0x180067dbb  jnz     short loc_180067E0D
0x180067dbd  mov     rax, [rsp+2F0h+var_280]
0x180067dc2  lea     r9, [rbp+1F0h+Name]
0x180067dc6  mov     r8, [rsp+2F0h+hKey]
0x180067dcb  mov     edx, r15d
0x180067dce  mov     [rsp+2F0h+phkResult], rax
0x180067dd3  mov     ecx, r12d
0x180067dd6  mov     rax, [rsp+2F0h+var_278]
0x180067ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067de0  mov     r14d, eax
0x180067de3  cmp     eax, 40706h
0x180067de8  jz      short loc_180067E00
0x180067dea  test    eax, eax
0x180067dec  js      short loc_180067E00
0x180067dee  mov     [rsp+2F0h+cchName], 104h
0x180067df6  test    esi, esi
0x180067df8  jz      loc_180067D6F
0x180067dfe  jmp     short loc_180067E0D
0x180067e00  mov     esi, 1
0x180067e05  mov     [rsp+2F0h+cchName], 104h
0x180067e0d  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180067e12  call    cs:__imp_RegCloseKey
0x180067e18  inc     edi
0x180067e1a  cmp     edi, ebx
0x180067e1c  jb      loc_180067CD6
0x180067e22  mov     eax, r14d
0x180067e25  jmp     short loc_180067E2C
0x180067e27  mov     eax, 80070057h
0x180067e2c  mov     rcx, [rbp+1F0h+var_40]
0x180067e33  xor     rcx, rsp; StackCookie
0x180067e36  call    __security_check_cookie
0x180067e3b  mov     rbx, [rsp+2F0h+arg_18]
0x180067e43  add     rsp, 2C0h
0x180067e4a  pop     r15
0x180067e4c  pop     r14
0x180067e4e  pop     r13
0x180067e50  pop     r12
0x180067e52  pop     rdi
0x180067e53  pop     rsi
0x180067e54  pop     rbp
0x180067e55  retn
```
