# RegScan::CopyKeys(void)

- ea: `0x18004fed4`
- end: `0x18005014b`
- name: `?CopyKeys@RegScan@@QEAAJXZ`
- size: `631`
- prototype: `__int64 __fastcall(RegScan *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000eaf8`
- `0x18004fed4`

## callees

- `0x180005944`
- `0x18004fed4`
- `0x180050154`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005003a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005003a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800500ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800500ad`

## string_xrefs

- `0x18004ff1f`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x18004ff7f`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x18004ffdd`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x180050074`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x1800500dc`: `com\complus\src\comcat\regscan\regscan.cpp`
- `0x1800500bf`: `REG_CREATED_NEW_KEY == dwDisposition`

## pseudocode

```c
LSTATUS __fastcall RegScan::CopyKeys(RegScan *this)
{
  unsigned int i; // esi
  __int64 v3; // rdi
  const WCHAR *v4; // r14
  HKEY v5; // rcx
  LSTATUS result; // eax
  HKEY v7; // rax
  int v8; // [rsp+50h] [rbp-30h] BYREF
  __int16 v9; // [rsp+54h] [rbp-2Ch]
  int v10; // [rsp+58h] [rbp-28h]
  const unsigned __int16 *v11; // [rsp+60h] [rbp-20h]
  __int64 v12; // [rsp+68h] [rbp-18h]
  __int64 v13; // [rsp+70h] [rbp-10h]
  int v14; // [rsp+78h] [rbp-8h]
  int v15; // [rsp+7Ch] [rbp-4h]
  DWORD dwDisposition; // [rsp+C0h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+C8h] [rbp+48h] BYREF

  if ( !*((_QWORD *)this + 6) )
  {
    v8 = 0;
    v11 = L"m_hkeyDest";
    v9 = 21;
    v10 = -1073605930;
    v12 = 0;
    v13 = 0;
    v15 = 1;
    v14 = 1;
    CError::WriteToLog((CError *)&v8, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x1C7u, L"m_hkeyDest");
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_DWORD *)this + 2) )
      return RegScan::CopyValues(this);
    v3 = *(_QWORD *)(*(_QWORD *)this + 8LL * i);
    if ( !v3 )
    {
      v11 = L"pRegScan";
      v8 = 0;
      v9 = 21;
      v10 = -1073605930;
      v12 = 0;
      v13 = 0;
      v15 = 1;
      v14 = 1;
      CError::WriteToLog((CError *)&v8, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x1CFu, L"pRegScan");
    }
    if ( *(_DWORD *)(v3 + 72) )
      break;
LABEL_21:
    ;
  }
  v4 = *(const WCHAR **)(v3 + 32);
  if ( !v4 )
  {
    v11 = L"lpSubKey";
    v9 = 21;
    v8 = 0;
    v10 = -1073605930;
    v12 = 0;
    v13 = 0;
    v15 = 1;
    v14 = 1;
    CError::WriteToLog((CError *)&v8, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x1D6u, L"lpSubKey");
  }
  v5 = (HKEY)*((_QWORD *)this + 6);
  hKey = 0;
  dwDisposition = 0;
  result = RegCreateKeyExW(v5, v4, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
  if ( !result )
  {
    v7 = hKey;
    if ( !hKey )
    {
      v8 = 0;
      v9 = 21;
      v10 = -1073605930;
      v11 = L"hkeySubKey";
      v12 = 0;
      v13 = 0;
      v15 = 1;
      v14 = 1;
      CError::WriteToLog((CError *)&v8, L"com\\complus\\src\\comcat\\regscan\\regscan.cpp", 0x1F0u, L"hkeySubKey");
      v7 = hKey;
    }
    if ( dwDisposition == 2 )
    {
      if ( v7 != HKEY_CLASSES_ROOT )
        RegCloseKey(v7);
      hKey = 0;
    }
    else
    {
      if ( dwDisposition != 1 )
      {
        v8 = 0;
        v9 = 21;
        v10 = -1073605930;
        v11 = L"REG_CREATED_NEW_KEY == dwDisposition";
        v12 = 0;
        v13 = 0;
        v15 = 1;
        v14 = 1;
        CError::WriteToLog(
          (CError *)&v8,
          L"com\\complus\\src\\comcat\\regscan\\regscan.cpp",
          0x202u,
          L"REG_CREATED_NEW_KEY == dwDisposition");
        v7 = hKey;
      }
      *(_QWORD *)(v3 + 48) = v7;
    }
    result = RegScan::CopyKeys((RegScan *)v3);
    if ( result )
      return result;
    goto LABEL_21;
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18004fed4  mov     [rsp-38h+arg_10], rbx
0x18004fed9  push    rbp
0x18004feda  push    rsi
0x18004fedb  push    rdi
0x18004fedc  push    r12
0x18004fede  push    r13
0x18004fee0  push    r14
0x18004fee2  push    r15
0x18004fee4  mov     rbp, rsp
0x18004fee7  sub     rsp, 80h
0x18004feee  mov     r14d, 15h
0x18004fef4  xor     r15d, r15d
0x18004fef7  mov     rbx, rcx
0x18004fefa  mov     r13d, 0C00212D6h
0x18004ff00  lea     r12d, [r14-14h]
0x18004ff04  cmp     [rcx+30h], r15
0x18004ff08  jnz     short loc_18004FF48
0x18004ff0a  lea     r9, aMHkeydest; "m_hkeyDest"
0x18004ff11  mov     [rbp+var_30], r15d
0x18004ff15  mov     r8d, 1C7h; unsigned int
0x18004ff1b  mov     [rbp+var_20], r9
0x18004ff1f  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x18004ff26  mov     [rbp+var_2C], r14w
0x18004ff2b  lea     rcx, [rbp+var_30]; this
0x18004ff2f  mov     [rbp+var_28], r13d
0x18004ff33  mov     [rbp+var_18], r15
0x18004ff37  mov     [rbp+var_10], r15
0x18004ff3b  mov     [rbp+var_4], r12d
0x18004ff3f  mov     [rbp+var_8], r12d
0x18004ff43  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18004ff48  mov     esi, r15d
0x18004ff4b  lea     r8, aLpsubkey; "lpSubKey"
0x18004ff52  lea     rdx, aPregscan; "pRegScan"
0x18004ff59  cmp     esi, [rbx+8]
0x18004ff5c  jnb     loc_180050128
0x18004ff62  mov     rax, [rbx]
0x18004ff65  mov     ecx, esi
0x18004ff67  mov     rdi, [rax+rcx*8]
0x18004ff6b  test    rdi, rdi
0x18004ff6e  jnz     short loc_18004FFB1
0x18004ff70  mov     [rbp+var_20], rdx
0x18004ff74  lea     rcx, [rbp+var_30]; this
0x18004ff78  mov     r9, rdx; unsigned __int16 *
0x18004ff7b  mov     [rbp+var_30], r15d
0x18004ff7f  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x18004ff86  mov     [rbp+var_2C], r14w
0x18004ff8b  mov     r8d, 1CFh; unsigned int
0x18004ff91  mov     [rbp+var_28], r13d
0x18004ff95  mov     [rbp+var_18], r15
0x18004ff99  mov     [rbp+var_10], r15
0x18004ff9d  mov     [rbp+var_4], r12d
0x18004ffa1  mov     [rbp+var_8], r12d
0x18004ffa5  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18004ffaa  lea     r8, aLpsubkey; "lpSubKey"
0x18004ffb1  cmp     [rdi+48h], r15d
0x18004ffb5  jz      loc_180050114
0x18004ffbb  mov     r14, [rdi+20h]
0x18004ffbf  test    r14, r14
0x18004ffc2  jnz     short loc_180050001
0x18004ffc4  lea     eax, [r14+15h]
0x18004ffc8  mov     [rbp+var_20], r8
0x18004ffcc  mov     r9, r8; unsigned __int16 *
0x18004ffcf  mov     [rbp+var_2C], ax
0x18004ffd3  mov     r8d, 1D6h; unsigned int
0x18004ffd9  mov     [rbp+var_30], r15d
0x18004ffdd  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x18004ffe4  mov     [rbp+var_28], r13d
0x18004ffe8  lea     rcx, [rbp+var_30]; this
0x18004ffec  mov     [rbp+var_18], r15
0x18004fff0  mov     [rbp+var_10], r15
0x18004fff4  mov     [rbp+var_4], r12d
0x18004fff8  mov     [rbp+var_8], r12d
0x18004fffc  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180050001  mov     rcx, [rbx+30h]; hKey
0x180050005  lea     rax, [rbp+dwDisposition]
0x180050009  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x18005000e  xor     r9d, r9d; lpClass
0x180050011  lea     rax, [rbp+hKey]
0x180050015  mov     [rbp+hKey], r15
0x180050019  mov     [rsp+80h+phkResult], rax; phkResult
0x18005001e  xor     r8d, r8d; Reserved
0x180050021  mov     [rsp+80h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180050026  mov     rdx, r14; lpSubKey
0x180050029  mov     [rsp+80h+samDesired], 2001Fh; samDesired
0x180050031  mov     [rsp+80h+dwOptions], r15d; dwOptions
0x180050036  mov     [rbp+dwDisposition], r15d
0x18005003a  call    cs:__imp_RegCreateKeyExW
0x180050040  test    eax, eax
0x180050042  jnz     loc_18005011C
0x180050048  mov     rax, [rbp+hKey]
0x18005004c  mov     r14d, 15h
0x180050052  test    rax, rax
0x180050055  jnz     short loc_18005009C
0x180050057  lea     rax, aHkeysubkey; "hkeySubKey"
0x18005005e  mov     [rbp+var_30], r15d
0x180050062  mov     r9, rax; unsigned __int16 *
0x180050065  mov     [rbp+var_2C], r14w
0x18005006a  mov     r8d, 1F0h; unsigned int
0x180050070  mov     [rbp+var_28], r13d
0x180050074  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x18005007b  mov     [rbp+var_20], rax
0x18005007f  lea     rcx, [rbp+var_30]; this
0x180050083  mov     [rbp+var_18], r15
0x180050087  mov     [rbp+var_10], r15
0x18005008b  mov     [rbp+var_4], r12d
0x18005008f  mov     [rbp+var_8], r12d
0x180050093  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180050098  mov     rax, [rbp+hKey]
0x18005009c  cmp     [rbp+dwDisposition], 2
0x1800500a0  jnz     short loc_1800500B9
0x1800500a2  cmp     rax, 0FFFFFFFF80000000h
0x1800500a8  jz      short loc_1800500B3
0x1800500aa  mov     rcx, rax; hKey
0x1800500ad  call    cs:__imp_RegCloseKey
0x1800500b3  mov     [rbp+hKey], r15
0x1800500b7  jmp     short loc_180050108
0x1800500b9  cmp     [rbp+dwDisposition], r12d
0x1800500bd  jz      short loc_180050104
0x1800500bf  lea     rax, aRegCreatedNewK; "REG_CREATED_NEW_KEY == dwDisposition"
0x1800500c6  mov     [rbp+var_30], r15d
0x1800500ca  mov     r9, rax; unsigned __int16 *
0x1800500cd  mov     [rbp+var_2C], r14w
0x1800500d2  mov     r8d, 202h; unsigned int
0x1800500d8  mov     [rbp+var_28], r13d
0x1800500dc  lea     rdx, aComComplusSrcC; "com\\complus\\src\\comcat\\regscan\\reg"...
0x1800500e3  mov     [rbp+var_20], rax
0x1800500e7  lea     rcx, [rbp+var_30]; this
0x1800500eb  mov     [rbp+var_18], r15
0x1800500ef  mov     [rbp+var_10], r15
0x1800500f3  mov     [rbp+var_4], r12d
0x1800500f7  mov     [rbp+var_8], r12d
0x1800500fb  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180050100  mov     rax, [rbp+hKey]
0x180050104  mov     [rdi+30h], rax
0x180050108  mov     rcx, rdi; this
0x18005010b  call    ?CopyKeys@RegScan@@QEAAJXZ; RegScan::CopyKeys(void)
0x180050110  test    eax, eax
0x180050112  jnz     short loc_180050130
0x180050114  add     esi, r12d
0x180050117  jmp     loc_18004FF4B
0x18005011c  jle     short loc_180050130
0x18005011e  movzx   eax, ax
0x180050121  or      eax, 80070000h
0x180050126  jmp     short loc_180050130
0x180050128  mov     rcx, rbx; this
0x18005012b  call    ?CopyValues@RegScan@@AEAAJXZ; RegScan::CopyValues(void)
0x180050130  mov     rbx, [rsp+80h+arg_10]
0x180050138  add     rsp, 80h
0x18005013f  pop     r15
0x180050141  pop     r14
0x180050143  pop     r13
0x180050145  pop     r12
0x180050147  pop     rdi
0x180050148  pop     rsi
0x180050149  pop     rbp
0x18005014a  retn
```
