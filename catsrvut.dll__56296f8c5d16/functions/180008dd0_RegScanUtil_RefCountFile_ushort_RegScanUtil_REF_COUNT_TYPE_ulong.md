# RegScanUtil::RefCountFile(ushort *,RegScanUtil::REF_COUNT_TYPE,ulong)

- ea: `0x180008dd0`
- end: `0x180009033`
- name: `?RefCountFile@RegScanUtil@@CAJPEAGW4REF_COUNT_TYPE@1@K@Z`
- size: `611`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004fdbc`
- `0x180050154`

## callees

- `0x180005944`
- `0x180008dd0`
- `0x180055880`
- `0x180055940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e7b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008ed4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180008ed4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008fc0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008fc0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008fde`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008fde`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008f5a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180008f5a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009012`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009012`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180009003`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180009003`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180008e34`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180008e71`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180008e34`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180008e71`

## string_xrefs

- `0x180008ea7`: `SOFTWARE\Microsoft\Windows\CurrentVersion\SharedDlls`
- `0x180008f02`: `hkeySharedDlls`
- `0x180008f15`: `com\complus\src\comcat\regscan\regscanutil.cpp`

## pseudocode

```c
__int64 __fastcall RegScanUtil::RefCountFile(const WCHAR *a1, int a2, unsigned int a3)
{
  WCHAR *v6; // rdi
  DWORD LongPathNameW; // eax
  DWORD v8; // r8d
  unsigned __int64 v9; // rdx
  __int64 v10; // rax
  void *v11; // rsp
  signed int LastError; // eax
  bool v13; // zf
  LSTATUS v14; // eax
  bool v15; // zf
  HKEY v16; // rcx
  int v17; // ebx
  LSTATUS v18; // eax
  int v19; // eax
  unsigned int v20; // eax
  LSTATUS v21; // eax
  bool v22; // zf
  WCHAR szLongPath[4]; // [rsp+50h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+8h] BYREF
  DWORD Type; // [rsp+60h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+64h] [rbp+14h] BYREF
  int v28; // [rsp+68h] [rbp+18h] BYREF
  __int16 v29; // [rsp+6Ch] [rbp+1Ch]
  int v30; // [rsp+70h] [rbp+20h]
  const unsigned __int16 *v31; // [rsp+78h] [rbp+28h]
  __int64 v32; // [rsp+80h] [rbp+30h]
  __int64 v33; // [rsp+88h] [rbp+38h]
  int v34; // [rsp+90h] [rbp+40h]
  int v35; // [rsp+94h] [rbp+44h]

  hKey = 0;
  cbData = 4;
  *(_DWORD *)szLongPath = 0;
  Type = 0;
  if ( !a1 || a2 >= 4 )
    return 0;
  v6 = 0;
  LongPathNameW = GetLongPathNameW(a1, 0, 0);
  v8 = LongPathNameW;
  if ( !LongPathNameW )
    goto LABEL_9;
  v9 = 2LL * (LongPathNameW + 1);
  v10 = v9 + 15;
  if ( v9 + 15 < v9 )
    v10 = 0xFFFFFFFFFFFFFF0LL;
  v11 = alloca(v10 & 0xFFFFFFFFFFFFFFF0uLL);
  v6 = szLongPath;
  if ( !GetLongPathNameW(a1, szLongPath, v8) )
  {
LABEL_9:
    LastError = GetLastError();
    v13 = LastError == 0;
    if ( LastError > 0 )
      v13 = 0;
    if ( !v13 )
      goto LABEL_39;
  }
  v14 = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SharedDlls",
          0,
          0,
          0,
          0x2001Bu,
          0,
          &hKey,
          0);
  v15 = v14 == 0;
  if ( v14 > 0 )
    v15 = 0;
  if ( !v15 )
    goto LABEL_39;
  v16 = hKey;
  v17 = 1;
  if ( !hKey )
  {
    v28 = 0;
    v32 = 0;
    v33 = 0;
    v29 = 21;
    v30 = -1073605930;
    v31 = L"hkeySharedDlls";
    v35 = 1;
    v34 = 1;
    CError::WriteToLog((CError *)&v28, L"com\\complus\\src\\comcat\\regscan\\regscanutil.cpp", 0x8Cu, L"hkeySharedDlls");
    v16 = hKey;
  }
  v18 = RegQueryValueExW(v16, v6, 0, &Type, (LPBYTE)szLongPath, &cbData);
  if ( (v18 & 0xFFFFFFFD) != 0 )
    goto LABEL_39;
  if ( !a2 )
  {
    v19 = *(_DWORD *)szLongPath + 1;
    goto LABEL_27;
  }
  if ( a2 == 1 || a2 == 2 )
  {
    v13 = v18 == 0;
    v19 = *(_DWORD *)szLongPath;
    if ( !v13 || !*(_DWORD *)szLongPath )
    {
      v17 = 0;
      goto LABEL_28;
    }
    v19 = *(_DWORD *)szLongPath - 1;
    goto LABEL_27;
  }
  if ( a2 != 3 )
    goto LABEL_39;
  v19 = *(_DWORD *)szLongPath;
  if ( *(_DWORD *)szLongPath < a3 )
  {
    v19 = a3;
LABEL_27:
    *(_DWORD *)szLongPath = v19;
  }
LABEL_28:
  Type = 4;
  cbData = 4;
  if ( !v17 )
  {
LABEL_36:
    if ( !v19 && a2 == 2 )
      DeleteFileW(v6);
    goto LABEL_39;
  }
  if ( v19 )
  {
    v21 = RegSetValueExW(hKey, v6, 0, 4u, (const BYTE *)szLongPath, 4u);
    v22 = v21 == 0;
    if ( v21 <= 0 )
      goto LABEL_34;
    v20 = (unsigned __int16)v21 | 0x80070000;
  }
  else
  {
    RegDeleteValueW(hKey, v6);
    v20 = 0;
  }
  v22 = v20 == 0;
LABEL_34:
  if ( v22 )
  {
    v19 = *(_DWORD *)szLongPath;
    goto LABEL_36;
  }
LABEL_39:
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180008dd0  push    rbp
0x180008dd2  push    rbx
0x180008dd3  push    rsi
0x180008dd4  push    rdi
0x180008dd5  push    r12
0x180008dd7  push    r14
0x180008dd9  sub     rsp, 0A8h
0x180008de0  lea     rbp, [rsp+50h]
0x180008de5  mov     rax, cs:__security_cookie
0x180008dec  xor     rax, rbp
0x180008def  mov     [rbp+80h+var_38], rax
0x180008df3  mov     [rbp+80h+hKey], 0
0x180008dfb  mov     r12d, 4
0x180008e01  mov     [rbp+80h+cbData], r12d
0x180008e05  mov     r14d, r8d
0x180008e08  mov     dword ptr [rbp+80h+szLongPath], 0
0x180008e0f  mov     esi, edx
0x180008e11  mov     [rbp+80h+Type], 0
0x180008e18  mov     rbx, rcx
0x180008e1b  test    rcx, rcx
0x180008e1e  jz      loc_180009018
0x180008e24  cmp     edx, r12d
0x180008e27  jge     loc_180009018
0x180008e2d  xor     edi, edi
0x180008e2f  xor     r8d, r8d; cchBuffer
0x180008e32  xor     edx, edx; lpszLongPath
0x180008e34  call    cs:__imp_GetLongPathNameW
0x180008e3a  mov     r8d, eax
0x180008e3d  test    eax, eax
0x180008e3f  jz      short loc_180008E7B
0x180008e41  lea     edx, [rax+1]
0x180008e44  add     rdx, rdx
0x180008e47  lea     rax, [rdx+0Fh]
0x180008e4b  cmp     rax, rdx
0x180008e4e  ja      short loc_180008E5A
0x180008e50  mov     rax, 0FFFFFFFFFFFFFF0h
0x180008e5a  and     rax, 0FFFFFFFFFFFFFFF0h
0x180008e5e  call    _alloca_probe
0x180008e63  sub     rsp, rax
0x180008e66  mov     rcx, rbx; lpszShortPath
0x180008e69  lea     rdi, [rsp+0D0h+szLongPath]
0x180008e6e  mov     rdx, rdi; lpszLongPath
0x180008e71  call    cs:__imp_GetLongPathNameW
0x180008e77  test    eax, eax
0x180008e79  jnz     short loc_180008E95
0x180008e7b  call    cs:__imp_GetLastError
0x180008e81  test    eax, eax
0x180008e83  jle     short loc_180008E8F
0x180008e85  movzx   eax, ax
0x180008e88  or      eax, 80070000h
0x180008e8d  test    eax, eax
0x180008e8f  jnz     loc_180009009
0x180008e95  mov     [rsp+0D0h+lpdwDisposition], 0; lpdwDisposition
0x180008e9e  lea     rax, [rbp+80h+hKey]
0x180008ea2  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180008ea7  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180008eae  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180008eb7  xor     r9d, r9d; lpClass
0x180008eba  mov     [rsp+0D0h+samDesired], 2001Bh; samDesired
0x180008ec2  xor     r8d, r8d; Reserved
0x180008ec5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180008ecc  mov     [rsp+0D0h+dwOptions], 0; dwOptions
0x180008ed4  call    cs:__imp_RegCreateKeyExW
0x180008eda  test    eax, eax
0x180008edc  jle     short loc_180008EE8
0x180008ede  movzx   eax, ax
0x180008ee1  or      eax, 80070000h
0x180008ee6  test    eax, eax
0x180008ee8  jnz     loc_180009009
0x180008eee  mov     rcx, [rbp+80h+hKey]
0x180008ef2  mov     ebx, 1
0x180008ef7  test    rcx, rcx
0x180008efa  jnz     short loc_180008F3E
0x180008efc  lea     eax, [rbx+14h]
0x180008eff  mov     [rbp+80h+var_68], ecx
0x180008f02  lea     r9, aHkeyshareddlls; "hkeySharedDlls"
0x180008f09  mov     [rbp+80h+var_50], rcx
0x180008f0d  mov     [rbp+80h+var_48], rcx
0x180008f11  lea     r8d, [rax+77h]; unsigned int
0x180008f15  lea     rdx, aComComplusSrcC_2; "com\\complus\\src\\comcat\\regscan\\reg"...
0x180008f1c  mov     [rbp+80h+var_64], ax
0x180008f20  lea     rcx, [rbp+80h+var_68]; this
0x180008f24  mov     [rbp+80h+var_60], 0C00212D6h
0x180008f2b  mov     [rbp+80h+var_58], r9
0x180008f2f  mov     [rbp+80h+var_3C], ebx
0x180008f32  mov     [rbp+80h+var_40], ebx
0x180008f35  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x180008f3a  mov     rcx, [rbp+80h+hKey]; hKey
0x180008f3e  lea     rax, [rbp+80h+cbData]
0x180008f42  xor     r8d, r8d; lpReserved
0x180008f45  mov     qword ptr [rsp+0D0h+samDesired], rax; lpcbData
0x180008f4a  lea     r9, [rbp+80h+Type]; lpType
0x180008f4e  lea     rax, [rbp+80h+szLongPath]
0x180008f52  mov     rdx, rdi; lpValueName
0x180008f55  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x180008f5a  call    cs:__imp_RegQueryValueExW
0x180008f60  test    eax, 0FFFFFFFDh
0x180008f65  jnz     loc_180009009
0x180008f6b  mov     edx, esi
0x180008f6d  test    esi, esi
0x180008f6f  jz      short loc_180008FA1
0x180008f71  sub     edx, ebx
0x180008f73  jz      short loc_180008F8E
0x180008f75  sub     edx, ebx
0x180008f77  jz      short loc_180008F8E
0x180008f79  cmp     edx, ebx
0x180008f7b  jnz     loc_180009009
0x180008f81  mov     eax, dword ptr [rbp+80h+szLongPath]
0x180008f84  cmp     eax, r14d
0x180008f87  jnb     short loc_180008FA9
0x180008f89  mov     eax, r14d
0x180008f8c  jmp     short loc_180008FA6
0x180008f8e  test    eax, eax
0x180008f90  mov     eax, dword ptr [rbp+80h+szLongPath]
0x180008f93  jnz     short loc_180008F99
0x180008f95  test    eax, eax
0x180008f97  jnz     short loc_180008F9D
0x180008f99  xor     ebx, ebx
0x180008f9b  jmp     short loc_180008FA9
0x180008f9d  dec     eax
0x180008f9f  jmp     short loc_180008FA6
0x180008fa1  mov     eax, dword ptr [rbp+80h+szLongPath]
0x180008fa4  add     eax, ebx
0x180008fa6  mov     dword ptr [rbp+80h+szLongPath], eax
0x180008fa9  mov     [rbp+80h+Type], r12d
0x180008fad  mov     [rbp+80h+cbData], r12d
0x180008fb1  test    ebx, ebx
0x180008fb3  jz      short loc_180008FF7
0x180008fb5  mov     rcx, [rbp+80h+hKey]; hKey
0x180008fb9  mov     rdx, rdi; lpValueName
0x180008fbc  test    eax, eax
0x180008fbe  jnz     short loc_180008FCA
0x180008fc0  call    cs:__imp_RegDeleteValueW
0x180008fc6  xor     eax, eax
0x180008fc8  jmp     short loc_180008FF0
0x180008fca  lea     rax, [rbp+80h+szLongPath]
0x180008fce  mov     [rsp+0D0h+samDesired], r12d; cbData
0x180008fd3  mov     r9d, r12d; dwType
0x180008fd6  mov     qword ptr [rsp+0D0h+dwOptions], rax; lpData
0x180008fdb  xor     r8d, r8d; Reserved
0x180008fde  call    cs:__imp_RegSetValueExW
0x180008fe4  test    eax, eax
0x180008fe6  jle     short loc_180008FF2
0x180008fe8  movzx   eax, ax
0x180008feb  or      eax, 80070000h
0x180008ff0  test    eax, eax
0x180008ff2  jnz     short loc_180009009
0x180008ff4  mov     eax, dword ptr [rbp+80h+szLongPath]
0x180008ff7  test    eax, eax
0x180008ff9  jnz     short loc_180009009
0x180008ffb  cmp     esi, 2
0x180008ffe  jnz     short loc_180009009
0x180009000  mov     rcx, rdi; lpFileName
0x180009003  call    cs:__imp_DeleteFileW
0x180009009  mov     rcx, [rbp+80h+hKey]; hKey
0x18000900d  test    rcx, rcx
0x180009010  jz      short loc_180009018
0x180009012  call    cs:__imp_RegCloseKey
0x180009018  xor     eax, eax
0x18000901a  mov     rcx, [rbp+80h+var_38]
0x18000901e  xor     rcx, rbp; StackCookie
0x180009021  call    __security_check_cookie
0x180009026  lea     rsp, [rbp+58h]
0x18000902a  pop     r14
0x18000902c  pop     r12
0x18000902e  pop     rdi
0x18000902f  pop     rsi
0x180009030  pop     rbx
0x180009031  pop     rbp
0x180009032  retn
```
