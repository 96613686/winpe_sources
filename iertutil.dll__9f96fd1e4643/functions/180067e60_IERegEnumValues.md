# IERegEnumValues

- ea: `0x180067e60`
- end: `0x18006811b`
- name: `IERegEnumValues`
- size: `699`
- prototype: `__int64 __fastcall(int, int, int, int, REGSAM samDesired)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x18003f5c0`
- `0x180067e60`
- `0x180083c10`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067fd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180067fd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800680d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800680d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006801f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18006801f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180068079`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180068079`

## pseudocode

```c
__int64 __fastcall IERegEnumValues(
        unsigned int a1,
        __int64 (__fastcall *a2)(_QWORD, _QWORD, HKEY, WCHAR *, __int64),
        __int64 a3,
        int a4,
        REGSAM samDesired)
{
  __int64 v7; // r15
  int v8; // esi
  unsigned int v9; // r14d
  unsigned int v10; // edx
  unsigned int v11; // ebx
  int v12; // r9d
  __int64 v13; // rax
  signed int i; // r8d
  __int64 v15; // rax
  unsigned int v16; // r13d
  unsigned int j; // edi
  __int64 v18; // r12
  DWORD v19; // edx
  int v20; // eax
  DWORD cchValueName; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cValues; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v23; // [rsp+68h] [rbp-98h]
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+78h] [rbp-88h]
  __int64 (__fastcall *v26)(_QWORD, _QWORD, HKEY, WCHAR *, __int64); // [rsp+80h] [rbp-80h]
  _DWORD v27[6]; // [rsp+88h] [rbp-78h]
  WCHAR ValueName[264]; // [rsp+A0h] [rbp-60h] BYREF

  v25 = a3;
  v26 = a2;
  v23 = a1;
  hKey = 0;
  cchValueName = 0;
  cValues = 0;
  if ( a1 >= 0x55 )
    return 2147747588LL;
  v7 = 5LL * a1;
  if ( (dword_1800E4BA4[10 * a1] & 0x100) == 0 || !a2 )
    return 2147942487LL;
  v8 = 0;
  v9 = 0;
  IERegInit();
  v10 = 3;
  v11 = 0;
  if ( (a4 & 0x10) != 0 )
  {
    do
    {
      v12 = v10;
      if ( !_bittest(&a4, v10)
        && (dword_18025DFD0[v10] & dword_1800E4BA4[2 * v7]) == dword_18025DFD0[v10]
        && qword_18029A190[v10] )
      {
        v13 = v11++;
        v27[v13] = v10;
      }
      --v10;
    }
    while ( v12 > 0 );
  }
  else
  {
    for ( i = 0; i <= 3; ++i )
    {
      if ( !_bittest(&a4, i)
        && (dword_18025DFD0[i] & dword_1800E4BA4[2 * v7]) == dword_18025DFD0[i]
        && qword_18029A190[i] )
      {
        v15 = v11++;
        v27[v15] = i;
      }
    }
  }
  v16 = v23;
  for ( j = 0; j < v11; ++j )
  {
    if ( v8 )
      break;
    v18 = (int)v27[j];
    if ( !RegOpenKeyExW((HKEY)qword_18029A190[v18], (LPCWSTR)qword_1800E4B80[v7], 0, samDesired, &hKey) )
    {
      if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0) )
      {
        for ( cchValueName = 260; ; cchValueName = 260 )
        {
          v19 = cValues;
          if ( !cValues )
            break;
          --cValues;
          if ( RegEnumValueW(hKey, v19 - 1, ValueName, &cchValueName, 0, 0, 0, 0) )
            break;
          v20 = v26(v16, (unsigned int)v18, hKey, ValueName, v25);
          v9 = v20;
          if ( v20 == 263942 || v20 < 0 )
          {
            v8 = 1;
            cchValueName = 260;
            break;
          }
        }
      }
      RegCloseKey(hKey);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180067e60  mov     [rsp-8+arg_18], rbx
0x180067e65  push    rbp
0x180067e66  push    rsi
0x180067e67  push    rdi
0x180067e68  push    r12
0x180067e6a  push    r13
0x180067e6c  push    r14
0x180067e6e  push    r15
0x180067e70  lea     rbp, [rsp-1C0h]
0x180067e78  sub     rsp, 2C0h
0x180067e7f  mov     rax, cs:__security_cookie
0x180067e86  xor     rax, rsp
0x180067e89  mov     [rbp+1F0h+var_40], rax
0x180067e90  xor     r12d, r12d
0x180067e93  mov     r13d, ecx
0x180067e96  mov     [rsp+2F0h+var_278], r8
0x180067e9b  mov     edi, r9d
0x180067e9e  mov     [rbp+1F0h+var_270], rdx
0x180067ea2  mov     [rsp+2F0h+var_288], r13d
0x180067ea7  mov     [rsp+2F0h+hKey], r12
0x180067eac  mov     [rsp+2F0h+cchValueName], r12d
0x180067eb1  mov     [rsp+2F0h+cValues], r12d
0x180067eb6  cmp     ecx, 55h ; 'U'
0x180067eb9  jb      short loc_180067EC5
0x180067ebb  mov     eax, 80040704h
0x180067ec0  jmp     loc_1800680F1
0x180067ec5  lea     r15, ds:0[r13*4]
0x180067ecd  add     r15, r13
0x180067ed0  lea     rax, __ImageBase
0x180067ed7  test    ds:rva dword_1800E4BA4[rax+r15*8], 100h
0x180067ee3  jz      loc_1800680EC
0x180067ee9  test    rdx, rdx
0x180067eec  jz      loc_1800680EC
0x180067ef2  mov     esi, r12d
0x180067ef5  mov     r14d, r12d
0x180067ef8  call    IERegInit
0x180067efd  lea     r13, __ImageBase
0x180067f04  mov     edx, 3
0x180067f09  mov     ebx, r12d
0x180067f0c  test    dil, 10h
0x180067f10  jz      short loc_180067F4E
0x180067f12  bt      edi, edx
0x180067f15  mov     r9d, edx
0x180067f18  jb      short loc_180067F45
0x180067f1a  mov     eax, ds:rva dword_1800E4BA4[r13+r15*8]
0x180067f22  movsxd  r8, edx
0x180067f25  mov     ecx, ds:rva dword_18025DFD0[r13+r8*4]
0x180067f2d  and     eax, ecx
0x180067f2f  cmp     eax, ecx
0x180067f31  jnz     short loc_180067F45
0x180067f33  cmp     rva qword_18029A190[r13+r8*8], r12
0x180067f3b  jz      short loc_180067F45
0x180067f3d  mov     eax, ebx
0x180067f3f  inc     ebx
0x180067f41  mov     [rbp+rax*4+1F0h+var_268], edx
0x180067f45  dec     edx
0x180067f47  test    r9d, r9d
0x180067f4a  jg      short loc_180067F12
0x180067f4c  jmp     short loc_180067F8B
0x180067f4e  mov     r8d, r12d
0x180067f51  bt      edi, r8d
0x180067f55  jb      short loc_180067F83
0x180067f57  mov     eax, ds:rva dword_1800E4BA4[r13+r15*8]
0x180067f5f  mov     r9d, r8d
0x180067f62  mov     ecx, ds:rva dword_18025DFD0[r13+r9*4]
0x180067f6a  and     eax, ecx
0x180067f6c  cmp     eax, ecx
0x180067f6e  jnz     short loc_180067F83
0x180067f70  cmp     rva qword_18029A190[r13+r9*8], r12
0x180067f78  jz      short loc_180067F83
0x180067f7a  mov     eax, ebx
0x180067f7c  inc     ebx
0x180067f7e  mov     [rbp+rax*4+1F0h+var_268], r8d
0x180067f83  inc     r8d
0x180067f86  cmp     r8d, edx
0x180067f89  jle     short loc_180067F51
0x180067f8b  mov     r13d, [rsp+2F0h+var_288]
0x180067f90  mov     edi, r12d
0x180067f93  test    ebx, ebx
0x180067f95  jz      loc_1800680E7
0x180067f9b  test    esi, esi
0x180067f9d  jnz     loc_1800680E7
0x180067fa3  mov     r9d, [rbp+1F0h+samDesired]; samDesired
0x180067faa  xor     r8d, r8d; ulOptions
0x180067fad  mov     eax, edi
0x180067faf  movsxd  r12, [rbp+rax*4+1F0h+var_268]
0x180067fb4  lea     rax, [rsp+2F0h+hKey]
0x180067fb9  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180067fbe  lea     rax, __ImageBase
0x180067fc5  mov     rdx, ds:rva qword_1800E4B80[rax+r15*8]; lpSubKey
0x180067fcd  mov     rcx, rva qword_18029A190[rax+r12*8]; hKey
0x180067fd5  call    cs:__imp_RegOpenKeyExW
0x180067fdb  xor     ecx, ecx
0x180067fdd  test    eax, eax
0x180067fdf  jnz     loc_1800680DD
0x180067fe5  mov     [rsp+2F0h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x180067fea  lea     rax, [rsp+2F0h+cValues]
0x180067fef  mov     [rsp+2F0h+lpcbSecurityDescriptor], rcx; lpcbSecurityDescriptor
0x180067ff4  xor     r9d, r9d; lpReserved
0x180067ff7  mov     [rsp+2F0h+lpcbMaxValueLen], rcx; lpcbMaxValueLen
0x180067ffc  xor     r8d, r8d; lpcchClass
0x180067fff  mov     [rsp+2F0h+lpcbMaxValueNameLen], rcx; lpcbMaxValueNameLen
0x180068004  xor     edx, edx; lpClass
0x180068006  mov     [rsp+2F0h+lpcValues], rax; lpcValues
0x18006800b  mov     [rsp+2F0h+lpcbMaxClassLen], rcx; lpcbMaxClassLen
0x180068010  mov     [rsp+2F0h+lpcbMaxSubKeyLen], rcx; lpcbMaxSubKeyLen
0x180068015  mov     [rsp+2F0h+phkResult], rcx; lpcSubKeys
0x18006801a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18006801f  call    cs:__imp_RegQueryInfoKeyW
0x180068025  test    eax, eax
0x180068027  jnz     loc_1800680D2
0x18006802d  mov     [rsp+2F0h+cchValueName], 104h
0x180068035  mov     edx, [rsp+2F0h+cValues]
0x180068039  test    edx, edx
0x18006803b  jz      loc_1800680D2
0x180068041  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180068046  lea     r9, [rsp+2F0h+cchValueName]; lpcchValueName
0x18006804b  mov     [rsp+2F0h+lpcValues], 0; lpcbData
0x180068054  lea     r8, [rbp+1F0h+ValueName]; lpValueName
0x180068058  mov     [rsp+2F0h+lpcbMaxClassLen], 0; lpData
0x180068061  dec     edx; dwIndex
0x180068063  mov     [rsp+2F0h+lpcbMaxSubKeyLen], 0; lpType
0x18006806c  mov     [rsp+2F0h+phkResult], 0; lpReserved
0x180068075  mov     [rsp+2F0h+cValues], edx
0x180068079  call    cs:__imp_RegEnumValueW
0x18006807f  test    eax, eax
0x180068081  jnz     short loc_1800680D2
0x180068083  mov     rax, [rsp+2F0h+var_278]
0x180068088  lea     r9, [rbp+1F0h+ValueName]
0x18006808c  mov     r8, [rsp+2F0h+hKey]
0x180068091  mov     edx, r12d
0x180068094  mov     [rsp+2F0h+phkResult], rax
0x180068099  mov     ecx, r13d
0x18006809c  mov     rax, [rbp+1F0h+var_270]
0x1800680a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800680a5  mov     r14d, eax
0x1800680a8  cmp     eax, 40706h
0x1800680ad  jz      short loc_1800680C5
0x1800680af  test    eax, eax
0x1800680b1  js      short loc_1800680C5
0x1800680b3  mov     [rsp+2F0h+cchValueName], 104h
0x1800680bb  test    esi, esi
0x1800680bd  jz      loc_180068035
0x1800680c3  jmp     short loc_1800680D2
0x1800680c5  mov     esi, 1
0x1800680ca  mov     [rsp+2F0h+cchValueName], 104h
0x1800680d2  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800680d7  call    cs:__imp_RegCloseKey
0x1800680dd  inc     edi
0x1800680df  cmp     edi, ebx
0x1800680e1  jb      loc_180067F9B
0x1800680e7  mov     eax, r14d
0x1800680ea  jmp     short loc_1800680F1
0x1800680ec  mov     eax, 80070057h
0x1800680f1  mov     rcx, [rbp+1F0h+var_40]
0x1800680f8  xor     rcx, rsp; StackCookie
0x1800680fb  call    __security_check_cookie
0x180068100  mov     rbx, [rsp+2F0h+arg_18]
0x180068108  add     rsp, 2C0h
0x18006810f  pop     r15
0x180068111  pop     r14
0x180068113  pop     r13
0x180068115  pop     r12
0x180068117  pop     rdi
0x180068118  pop     rsi
0x180068119  pop     rbp
0x18006811a  retn
```
