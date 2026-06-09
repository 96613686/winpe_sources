# RemoveAClassName(wchar_t const *)

- ea: `0x1800205fc`
- end: `0x18002082e`
- name: `?RemoveAClassName@@YAJPEB_W@Z`
- size: `562`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180020304`

## callees

- `0x180014130`
- `0x1800205fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020759`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180020759`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020734`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180020734`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180020772`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002077c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180020772`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002077c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020741`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020741`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800206bb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800207c0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800206bb`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800207c0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020652`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800206f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020652`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800206f3`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002066a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800207e3`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18002066a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1800207e3`

## pseudocode

```c
LSTATUS __fastcall RemoveAClassName(WCHAR *lpSubKey)
{
  LSTATUS v2; // edi
  HKEY v3; // rcx
  WCHAR *v4; // rdx
  LSTATUS v5; // ebx
  DWORD v6; // esi
  LSTATUS result; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[528]; // [rsp+280h] [rbp+180h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v2 = RegOpenKeyExW(HKEY_CLASSES_ROOT, 0, 0, 0x2001Fu, &hKey);
  if ( v2 )
    return 0;
  v3 = hKey;
  v4 = lpSubKey;
LABEL_3:
  v5 = RegDeleteKeyW(v3, v4);
LABEL_4:
  v6 = 0;
  while ( 1 )
  {
    cchName = 260;
    ftLastWriteTime = 0;
    result = RegEnumKeyExW(hKey, v6, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
    if ( result )
      break;
    phkResult = 0;
    ++v6;
    v2 = RegOpenKeyExW(HKEY_CLASSES_ROOT, Name, 0, 0x2001Fu, &phkResult);
    if ( !v2 )
    {
      Type = 0;
      cchName = 520;
      v2 = RegQueryValueExW(phkResult, 0, 0, &Type, Data, &cchName);
      RegCloseKey(phkResult);
      if ( v2 || (unsigned int)_o__wcsicmp(Data) )
      {
        v2 = 0;
      }
      else
      {
        if ( v5 )
          RegDeleteValueW(phkResult, 0);
        else
          v5 = RegDeleteValueW(phkResult, 0);
        cchName = 260;
        if ( RegEnumKeyExW(phkResult, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) == 259 )
        {
          v3 = hKey;
          v4 = Name;
          if ( !v5 )
            goto LABEL_3;
          RegDeleteKeyW(hKey, Name);
          goto LABEL_4;
        }
      }
    }
  }
  if ( result == 259 )
    result = v2;
  if ( !result )
    return v5;
  return result;
}

```

## disassembly

```asm
0x1800205fc  mov     [rsp-8+arg_8], rbx
0x180020601  mov     [rsp-8+arg_10], rsi
0x180020606  push    rbp
0x180020607  push    rdi
0x180020608  push    r14
0x18002060a  lea     rbp, [rsp-3A0h]
0x180020612  sub     rsp, 4A0h
0x180020619  mov     rax, cs:__security_cookie
0x180020620  xor     rax, rsp
0x180020623  mov     [rbp+3B0h+var_20], rax
0x18002062a  mov     r14, rcx
0x18002062d  mov     [rsp+4B0h+hKey], 0FFFFFFFFFFFFFFFFh
0x180020636  lea     rax, [rsp+4B0h+hKey]
0x18002063b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180020642  mov     r9d, 2001Fh; samDesired
0x180020648  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18002064d  xor     r8d, r8d; ulOptions
0x180020650  xor     edx, edx; lpSubKey
0x180020652  call    cs:__imp_RegOpenKeyExW
0x180020658  mov     edi, eax
0x18002065a  test    eax, eax
0x18002065c  jnz     loc_180020803
0x180020662  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180020667  mov     rdx, r14; lpSubKey
0x18002066a  call    cs:__imp_RegDeleteKeyW
0x180020670  mov     ebx, eax
0x180020672  xor     esi, esi
0x180020674  mov     rcx, [rsp+4B0h+hKey]; hKey
0x180020679  lea     rax, [rsp+4B0h+ftLastWriteTime]
0x18002067e  mov     [rsp+4B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180020683  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x180020688  mov     [rsp+4B0h+lpcchClass], 0; lpcchClass
0x180020691  lea     r8, [rsp+4B0h+Name]; lpName
0x180020696  mov     [rsp+4B0h+lpClass], 0; lpClass
0x18002069f  mov     edx, esi; dwIndex
0x1800206a1  mov     [rsp+4B0h+phkResult], 0; lpReserved
0x1800206aa  mov     [rsp+4B0h+cchName], 104h
0x1800206b2  mov     qword ptr [rsp+4B0h+ftLastWriteTime.dwLowDateTime], 0
0x1800206bb  call    cs:__imp_RegEnumKeyExW
0x1800206c1  test    eax, eax
0x1800206c3  jnz     loc_1800207F5
0x1800206c9  lea     rax, [rsp+4B0h+var_468]
0x1800206ce  mov     [rsp+4B0h+var_468], 0
0x1800206d7  mov     r9d, 2001Fh; samDesired
0x1800206dd  mov     [rsp+4B0h+phkResult], rax; phkResult
0x1800206e2  xor     r8d, r8d; ulOptions
0x1800206e5  lea     rdx, [rsp+4B0h+Name]; lpSubKey
0x1800206ea  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800206f1  inc     esi
0x1800206f3  call    cs:__imp_RegOpenKeyExW
0x1800206f9  mov     edi, eax
0x1800206fb  test    eax, eax
0x1800206fd  jnz     loc_180020674
0x180020703  mov     rcx, [rsp+4B0h+var_468]; hKey
0x180020708  lea     r9, [rsp+4B0h+Type]; lpType
0x18002070d  mov     [rsp+4B0h+Type], eax
0x180020711  xor     r8d, r8d; lpReserved
0x180020714  lea     rax, [rsp+4B0h+cchName]
0x180020719  mov     [rsp+4B0h+cchName], 208h
0x180020721  mov     [rsp+4B0h+lpClass], rax; lpcbData
0x180020726  xor     edx, edx; lpValueName
0x180020728  lea     rax, [rbp+3B0h+Data]
0x18002072f  mov     [rsp+4B0h+phkResult], rax; lpData
0x180020734  call    cs:__imp_RegQueryValueExW
0x18002073a  mov     rcx, [rsp+4B0h+var_468]; hKey
0x18002073f  mov     edi, eax
0x180020741  call    cs:__imp_RegCloseKey
0x180020747  test    edi, edi
0x180020749  jnz     loc_1800207EE
0x18002074f  mov     rdx, r14
0x180020752  lea     rcx, [rbp+3B0h+Data]
0x180020759  call    cs:__imp__o__wcsicmp
0x18002075f  test    eax, eax
0x180020761  jnz     loc_1800207EE
0x180020767  mov     rcx, [rsp+4B0h+var_468]; hKey
0x18002076c  xor     edx, edx; lpValueName
0x18002076e  test    ebx, ebx
0x180020770  jnz     short loc_18002077C
0x180020772  call    cs:__imp_RegDeleteValueW
0x180020778  mov     ebx, eax
0x18002077a  jmp     short loc_180020782
0x18002077c  call    cs:__imp_RegDeleteValueW
0x180020782  mov     rcx, [rsp+4B0h+var_468]; hKey
0x180020787  lea     rax, [rsp+4B0h+ftLastWriteTime]
0x18002078c  mov     [rsp+4B0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180020791  lea     r9, [rsp+4B0h+cchName]; lpcchName
0x180020796  mov     [rsp+4B0h+lpcchClass], 0; lpcchClass
0x18002079f  lea     r8, [rsp+4B0h+Name]; lpName
0x1800207a4  mov     [rsp+4B0h+lpClass], 0; lpClass
0x1800207ad  xor     edx, edx; dwIndex
0x1800207af  mov     [rsp+4B0h+phkResult], 0; lpReserved
0x1800207b8  mov     [rsp+4B0h+cchName], 104h
0x1800207c0  call    cs:__imp_RegEnumKeyExW
0x1800207c6  cmp     eax, 103h
0x1800207cb  jnz     loc_180020674
0x1800207d1  mov     rcx, [rsp+4B0h+hKey]; hKey
0x1800207d6  lea     rdx, [rsp+4B0h+Name]; lpSubKey
0x1800207db  test    ebx, ebx
0x1800207dd  jz      loc_18002066A
0x1800207e3  call    cs:__imp_RegDeleteKeyW
0x1800207e9  jmp     loc_180020672
0x1800207ee  xor     edi, edi
0x1800207f0  jmp     loc_180020674
0x1800207f5  cmp     eax, 103h
0x1800207fa  cmovz   eax, edi
0x1800207fd  test    eax, eax
0x1800207ff  jz      short loc_180020805
0x180020801  jmp     short loc_180020807
0x180020803  xor     ebx, ebx
0x180020805  mov     eax, ebx
0x180020807  mov     rcx, [rbp+3B0h+var_20]
0x18002080e  xor     rcx, rsp; StackCookie
0x180020811  call    __security_check_cookie
0x180020816  lea     r11, [rsp+4B0h+var_10]
0x18002081e  mov     rbx, [r11+28h]
0x180020822  mov     rsi, [r11+30h]
0x180020826  mov     rsp, r11
0x180020829  pop     r14
0x18002082b  pop     rdi
0x18002082c  pop     rbp
0x18002082d  retn
```
