# PrepareSelfRegKey

- ea: `0x18000e05c`
- end: `0x18000e20b`
- name: `PrepareSelfRegKey`
- size: `431`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000eaf8`
- `0x180031050`

## callees

- `0x180005944`
- `0x18000e05c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e0c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e1c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e0c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000e1c2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000e14d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18000e14d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e178`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e194`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e1ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e178`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e194`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e1ec`
- `ADVAPI32!RegCreateKeyW` at `0x18000e16a`
- `ADVAPI32!RegCreateKeyW` at `0x18000e16a`

## string_xrefs

- `0x18000e072`: `SelfReg\CLSID`
- `0x18000e1b4`: `SOFTWARE\Wow6432Node\Microsoft\COM3`
- `0x18000e085`: `SOFTWARE\Microsoft\COM3`
- `0x18000e0dd`: `hKeyCOM3`
- `0x18000e10b`: `com\complus\src\comcat\catsrvut\catsrvut.cpp`

## pseudocode

```c
__int64 __fastcall PrepareSelfRegKey(int a1)
{
  int v2; // esi
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  __int64 i; // rdi
  const WCHAR *v6; // rdx
  LSTATUS v7; // eax
  LPCWSTR lpSubKey[3]; // [rsp+30h] [rbp-50h]
  int v10; // [rsp+48h] [rbp-38h] BYREF
  __int16 v11; // [rsp+4Ch] [rbp-34h]
  int v12; // [rsp+50h] [rbp-30h]
  const unsigned __int16 *v13; // [rsp+58h] [rbp-28h]
  __int64 v14; // [rsp+60h] [rbp-20h]
  __int64 v15; // [rsp+68h] [rbp-18h]
  int v16; // [rsp+70h] [rbp-10h]
  int v17; // [rsp+74h] [rbp-Ch]
  HKEY hKey; // [rsp+B8h] [rbp+38h] BYREF
  HKEY v19; // [rsp+C0h] [rbp+40h] BYREF

  hKey = 0;
  lpSubKey[0] = L"SelfReg\\CLSID";
  lpSubKey[1] = L"SelfReg\\Interface";
  lpSubKey[2] = L"SelfReg\\TypeLib";
  v2 = 0;
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\COM3", 0, 0x2001Fu, &hKey);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( !v4 )
  {
    while ( 1 )
    {
      if ( !hKey )
      {
        v10 = 0;
        v11 = 21;
        v12 = -1073605930;
        v13 = L"hKeyCOM3";
        v14 = 0;
        v15 = 0;
        v17 = 1;
        v16 = 1;
        CError::WriteToLog((CError *)&v10, L"com\\complus\\src\\comcat\\catsrvut\\catsrvut.cpp", 0x2B1u, L"hKeyCOM3");
      }
      if ( a1 )
        RegDeleteTreeW(hKey, L"SelfReg");
      for ( i = 0; i != 3; ++i )
      {
        v6 = lpSubKey[i];
        v19 = 0;
        if ( !RegCreateKeyW(hKey, v6, &v19) )
          RegCloseKey(v19);
      }
      if ( v2 )
        break;
      if ( hKey )
        RegCloseKey(hKey);
      hKey = 0;
      v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Wow6432Node\\Microsoft\\COM3", 0, 0x2001Fu, &hKey);
      v4 = v7;
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      if ( v4 )
        break;
      v2 = 1;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x18000e05c  mov     [rsp-28h+arg_0], rbx
0x18000e061  push    rbp
0x18000e062  push    rsi
0x18000e063  push    rdi
0x18000e064  push    r13
0x18000e066  push    r14
0x18000e068  mov     rbp, rsp
0x18000e06b  sub     rsp, 80h
0x18000e072  lea     rax, aSelfregClsid; "SelfReg\\CLSID"
0x18000e079  mov     [rbp+hKey], 0
0x18000e081  mov     [rbp+lpSubKey], rax
0x18000e085  lea     rdx, aSoftwareMicros_10; "SOFTWARE\\Microsoft\\COM3"
0x18000e08c  lea     rax, aSelfregInterfa; "SelfReg\\Interface"
0x18000e093  mov     r14d, ecx
0x18000e096  mov     [rbp+var_48], rax
0x18000e09a  mov     r9d, 2001Fh; samDesired
0x18000e0a0  lea     rax, aSelfregTypelib; "SelfReg\\TypeLib"
0x18000e0a7  xor     r8d, r8d; ulOptions
0x18000e0aa  mov     [rbp+var_40], rax
0x18000e0ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e0b5  lea     rax, [rbp+hKey]
0x18000e0b9  xor     esi, esi
0x18000e0bb  mov     [rsp+80h+phkResult], rax; phkResult
0x18000e0c0  call    cs:__imp_RegOpenKeyExW
0x18000e0c6  mov     ebx, eax
0x18000e0c8  test    eax, eax
0x18000e0ca  jle     short loc_18000E0D5
0x18000e0cc  movzx   ebx, ax
0x18000e0cf  or      ebx, 80070000h
0x18000e0d5  test    ebx, ebx
0x18000e0d7  jnz     loc_18000E1E3
0x18000e0dd  lea     r13, aHkeycom3; "hKeyCOM3"
0x18000e0e4  cmp     [rbp+hKey], 0
0x18000e0e9  jnz     short loc_18000E13D
0x18000e0eb  mov     eax, 15h
0x18000e0f0  mov     [rbp+var_38], 0
0x18000e0f7  mov     r9, r13; unsigned __int16 *
0x18000e0fa  mov     [rbp+var_34], ax
0x18000e0fe  mov     r8d, 2B1h; unsigned int
0x18000e104  mov     [rbp+var_30], 0C00212D6h
0x18000e10b  lea     rdx, aComComplusSrcC_1; "com\\complus\\src\\comcat\\catsrvut\\ca"...
0x18000e112  mov     [rbp+var_28], r13
0x18000e116  lea     rcx, [rbp+var_38]; this
0x18000e11a  mov     [rbp+var_20], 0
0x18000e122  mov     [rbp+var_18], 0
0x18000e12a  mov     [rbp+var_C], 1
0x18000e131  mov     [rbp+var_10], 1
0x18000e138  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000e13d  test    r14d, r14d
0x18000e140  jz      short loc_18000E153
0x18000e142  mov     rcx, [rbp+hKey]; hKey
0x18000e146  lea     rdx, aSelfreg; "SelfReg"
0x18000e14d  call    cs:__imp_RegDeleteTreeW
0x18000e153  xor     edi, edi
0x18000e155  mov     rdx, [rbp+rdi*8+lpSubKey]; lpSubKey
0x18000e15a  lea     r8, [rbp+arg_10]; phkResult
0x18000e15e  mov     rcx, [rbp+hKey]; hKey
0x18000e162  mov     [rbp+arg_10], 0
0x18000e16a  call    cs:__imp_RegCreateKeyW
0x18000e170  test    eax, eax
0x18000e172  jnz     short loc_18000E17E
0x18000e174  mov     rcx, [rbp+arg_10]; hKey
0x18000e178  call    cs:__imp_RegCloseKey
0x18000e17e  inc     rdi
0x18000e181  cmp     rdi, 3
0x18000e185  jnz     short loc_18000E155
0x18000e187  test    esi, esi
0x18000e189  jnz     short loc_18000E1E3
0x18000e18b  mov     rcx, [rbp+hKey]; hKey
0x18000e18f  test    rcx, rcx
0x18000e192  jz      short loc_18000E19A
0x18000e194  call    cs:__imp_RegCloseKey
0x18000e19a  lea     rax, [rbp+hKey]
0x18000e19e  mov     [rbp+hKey], 0
0x18000e1a6  mov     r9d, 2001Fh; samDesired
0x18000e1ac  mov     [rsp+80h+phkResult], rax; phkResult
0x18000e1b1  xor     r8d, r8d; ulOptions
0x18000e1b4  lea     rdx, aSoftwareWow643; "SOFTWARE\\Wow6432Node\\Microsoft\\COM3"
0x18000e1bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e1c2  call    cs:__imp_RegOpenKeyExW
0x18000e1c8  mov     ebx, eax
0x18000e1ca  test    eax, eax
0x18000e1cc  jle     short loc_18000E1D7
0x18000e1ce  movzx   ebx, ax
0x18000e1d1  or      ebx, 80070000h
0x18000e1d7  test    ebx, ebx
0x18000e1d9  jnz     short loc_18000E1E3
0x18000e1db  lea     esi, [rbx+1]
0x18000e1de  jmp     loc_18000E0E4
0x18000e1e3  mov     rcx, [rbp+hKey]; hKey
0x18000e1e7  test    rcx, rcx
0x18000e1ea  jz      short loc_18000E1F2
0x18000e1ec  call    cs:__imp_RegCloseKey
0x18000e1f2  mov     eax, ebx
0x18000e1f4  mov     rbx, [rsp+80h+arg_0]
0x18000e1fc  add     rsp, 80h
0x18000e203  pop     r14
0x18000e205  pop     r13
0x18000e207  pop     rdi
0x18000e208  pop     rsi
0x18000e209  pop     rbp
0x18000e20a  retn
```
