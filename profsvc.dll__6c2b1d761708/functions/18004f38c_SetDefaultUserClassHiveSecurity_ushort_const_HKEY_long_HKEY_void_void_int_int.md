# SetDefaultUserClassHiveSecurity_(ushort const *,HKEY__ *,long (*)(HKEY__ *,void *,void *,int,int))

- ea: `0x18004f38c`
- end: `0x18004f55e`
- name: `?SetDefaultUserClassHiveSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z`
- size: `466`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY hKey, __int64 (__fastcall *)(HKEY handle, PSECURITY_DESCRIPTOR pSecurityDescriptor, void *a3))`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016150`
- `0x1800358a0`

## callees

- `0x180029804`
- `0x180041618`
- `0x180041678`
- `0x18004f38c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f400`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004f400`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f42f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f51b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f42f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004f51b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f4d6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f4d6`

## string_xrefs

- `0x18004f43b`: `Local Settings\MuiCache`

## pseudocode

```c
__int64 __fastcall SetDefaultUserClassHiveSecurity_(
        const unsigned __int16 *a1,
        HKEY hKey,
        __int64 (__fastcall *a3)(HKEY handle, PSECURITY_DESCRIPTOR pSecurityDescriptor, void *a3))
{
  signed int v6; // ebx
  LSTATUS v7; // eax
  bool v8; // sf
  unsigned __int64 v9; // rdi
  LSTATUS v10; // eax
  int v11; // r8d
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-19h]
  int v14; // [rsp+58h] [rbp-11h]
  int v15; // [rsp+5Ch] [rbp-Dh]
  const wchar_t *v16; // [rsp+60h] [rbp-9h]
  int v17; // [rsp+68h] [rbp-1h]
  int v18; // [rsp+6Ch] [rbp+3h]
  const wchar_t *v19; // [rsp+70h] [rbp+7h]
  int v20; // [rsp+78h] [rbp+Fh]
  int v21; // [rsp+7Ch] [rbp+13h]
  const wchar_t *v22; // [rsp+80h] [rbp+17h]
  int v23; // [rsp+88h] [rbp+1Fh]
  int v24; // [rsp+8Ch] [rbp+23h]
  const wchar_t *v25; // [rsp+90h] [rbp+27h]
  int v26; // [rsp+98h] [rbp+2Fh]
  int v27; // [rsp+9Ch] [rbp+33h]
  HKEY hKeya; // [rsp+E8h] [rbp+7Fh] BYREF

  v6 = SetHiveLpacSecurity_(a1, hKey, 1, (int (*)(HKEY, void *, void *, int, int))a3);
  if ( v6 >= 0 )
  {
    hKeya = 0;
    if ( a3 != ApplySecurityToRegistryKey_ )
    {
      v7 = RegOpenKeyExW(hKey, L"Local Settings", 0, 0x60019u, &hKeya);
      v8 = v7 < 0;
      if ( v7 > 0 )
        v8 = 1;
      if ( !v8 )
      {
        SetUserHiveSecurity_(a1, hKeya, (int (*)(HKEY, void *, void *, int, int))a3);
        RegCloseKey(hKeya);
      }
    }
    v15 = 1;
    v16 = L"Local Settings\\MuiCache";
    v19 = L"Local Settings\\Software";
    v22 = L"Local Settings\\Software\\Microsoft";
    v17 = 1;
    v18 = 1;
    v21 = 1;
    v24 = 1;
    v26 = 1;
    v27 = 1;
    v9 = 0;
    v25 = L"Local Settings\\Software\\Microsoft\\Windows";
    lpSubKey = L"Local Settings";
    v14 = 0;
    v20 = 0;
    v23 = 0;
    do
    {
      v10 = RegCreateKeyExW(hKey, (&lpSubKey)[2 * v9], 0, 0, 0, 0x60019u, 0, &hKeya, 0);
      v6 = v10;
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
      if ( v6 >= 0 )
      {
        v11 = *(&v14 + 4 * v9);
        if ( *(&v15 + 4 * v9) )
          SetHiveLpacSecurity_(a1, hKeya, v11, (int (*)(HKEY, void *, void *, int, int))a3);
        else
          SetHiveAppContainerSecurity_(a1, hKeya, v11, (int (*)(HKEY, void *, void *, int, int))a3);
        RegCloseKey(hKeya);
      }
      ++v9;
    }
    while ( v9 < 5 );
    if ( v6 == -2147024894 )
      return 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004f38c  mov     [rsp-8+arg_0], rbx
0x18004f391  mov     [rsp-8+arg_8], rsi
0x18004f396  push    rbp
0x18004f397  push    rdi
0x18004f398  push    r12
0x18004f39a  push    r14
0x18004f39c  push    r15
0x18004f39e  lea     rbp, [rsp-37h]
0x18004f3a3  sub     rsp, 0A0h
0x18004f3aa  mov     r14, r8
0x18004f3ad  mov     r9, r8; int (*)(HKEY, void *, void *, int, int)
0x18004f3b0  mov     edi, 1
0x18004f3b5  mov     r12, rdx
0x18004f3b8  mov     r8d, edi; int
0x18004f3bb  mov     r15, rcx
0x18004f3be  call    ?SetHiveLpacSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveLpacSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18004f3c3  mov     ebx, eax
0x18004f3c5  test    eax, eax
0x18004f3c7  js      loc_18004F53F
0x18004f3cd  lea     rax, ?ApplySecurityToRegistryKey_@@YAJPEAUHKEY__@@PEAX1HH@Z; ApplySecurityToRegistryKey_(HKEY__ *,void *,void *,int,int)
0x18004f3d4  mov     [rbp+57h+hKey], 0
0x18004f3dc  lea     rbx, aLocalSettings; "Local Settings"
0x18004f3e3  cmp     r14, rax
0x18004f3e6  jz      short loc_18004F43B
0x18004f3e8  lea     rax, [rbp+57h+hKey]
0x18004f3ec  mov     r9d, 60019h; samDesired
0x18004f3f2  xor     r8d, r8d; ulOptions
0x18004f3f5  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18004f3fa  mov     rdx, rbx; lpSubKey
0x18004f3fd  mov     rcx, r12; hKey
0x18004f400  call    cs:__imp_RegOpenKeyExW
0x18004f407  nop     dword ptr [rax+rax+00h]
0x18004f40c  test    eax, eax
0x18004f40e  jle     short loc_18004F41A
0x18004f410  movzx   eax, ax
0x18004f413  or      eax, 80070000h
0x18004f418  test    eax, eax
0x18004f41a  js      short loc_18004F43B
0x18004f41c  mov     rdx, [rbp+57h+hKey]; HKEY
0x18004f420  mov     r8, r14; int (*)(HKEY, void *, void *, int, int)
0x18004f423  mov     rcx, r15; unsigned __int16 *
0x18004f426  call    ?SetUserHiveSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z; SetUserHiveSecurity_(ushort const *,HKEY__ *,long (*)(HKEY__ *,void *,void *,int,int))
0x18004f42b  mov     rcx, [rbp+57h+hKey]; hKey
0x18004f42f  call    cs:__imp_RegCloseKey
0x18004f436  nop     dword ptr [rax+rax+00h]
0x18004f43b  lea     rax, aLocalSettingsM; "Local Settings\\MuiCache"
0x18004f442  mov     [rbp+57h+var_64], edi
0x18004f445  mov     [rbp+57h+var_60], rax
0x18004f449  lea     rax, aLocalSettingsS_0; "Local Settings\\Software"
0x18004f450  mov     [rbp+57h+var_50], rax
0x18004f454  lea     rax, aLocalSettingsS; "Local Settings\\Software\\Microsoft"
0x18004f45b  mov     [rbp+57h+var_40], rax
0x18004f45f  lea     rax, aLocalSettingsS_1; "Local Settings\\Software\\Microsoft\\Wi"...
0x18004f466  mov     [rbp+57h+var_58], edi
0x18004f469  mov     [rbp+57h+var_54], edi
0x18004f46c  mov     [rbp+57h+var_44], edi
0x18004f46f  mov     [rbp+57h+var_34], edi
0x18004f472  mov     [rbp+57h+var_28], edi
0x18004f475  mov     [rbp+57h+var_24], edi
0x18004f478  xor     edi, edi
0x18004f47a  mov     [rbp+57h+var_30], rax
0x18004f47e  mov     [rbp+57h+lpSubKey], rbx
0x18004f482  mov     [rbp+57h+var_68], 0
0x18004f489  mov     [rbp+57h+var_48], 0
0x18004f490  mov     [rbp+57h+var_38], 0
0x18004f497  mov     [rsp+0C0h+lpdwDisposition], 0; lpdwDisposition
0x18004f4a0  lea     rax, [rbp+57h+hKey]
0x18004f4a4  mov     [rsp+0C0h+var_88], rax; phkResult
0x18004f4a9  mov     rsi, rdi
0x18004f4ac  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004f4b5  add     rsi, rsi
0x18004f4b8  mov     [rsp+0C0h+samDesired], 60019h; samDesired
0x18004f4c0  xor     r9d, r9d; lpClass
0x18004f4c3  xor     r8d, r8d; Reserved
0x18004f4c6  mov     dword ptr [rsp+0C0h+phkResult], 0; dwOptions
0x18004f4ce  mov     rcx, r12; hKey
0x18004f4d1  mov     rdx, [rbp+rsi*8+57h+lpSubKey]; lpSubKey
0x18004f4d6  call    cs:__imp_RegCreateKeyExW
0x18004f4dd  nop     dword ptr [rax+rax+00h]
0x18004f4e2  mov     ebx, eax
0x18004f4e4  test    eax, eax
0x18004f4e6  jle     short loc_18004F4F1
0x18004f4e8  movzx   ebx, ax
0x18004f4eb  or      ebx, 80070000h
0x18004f4f1  test    ebx, ebx
0x18004f4f3  js      short loc_18004F527
0x18004f4f5  cmp     [rbp+rsi*8+57h+var_64], 0
0x18004f4fa  mov     r9, r14; int (*)(HKEY, void *, void *, int, int)
0x18004f4fd  mov     r8d, [rbp+rsi*8+57h+var_68]; int
0x18004f502  mov     rcx, r15; unsigned __int16 *
0x18004f505  mov     rdx, [rbp+57h+hKey]; HKEY
0x18004f509  jz      short loc_18004F512
0x18004f50b  call    ?SetHiveLpacSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveLpacSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18004f510  jmp     short loc_18004F517
0x18004f512  call    ?SetHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveAppContainerSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18004f517  mov     rcx, [rbp+57h+hKey]; hKey
0x18004f51b  call    cs:__imp_RegCloseKey
0x18004f522  nop     dword ptr [rax+rax+00h]
0x18004f527  inc     rdi
0x18004f52a  cmp     rdi, 5
0x18004f52e  jb      loc_18004F497
0x18004f534  xor     eax, eax
0x18004f536  cmp     ebx, 80070002h
0x18004f53c  cmovz   ebx, eax
0x18004f53f  lea     r11, [rsp+0C0h+var_20]
0x18004f547  mov     eax, ebx
0x18004f549  mov     rbx, [r11+30h]
0x18004f54d  mov     rsi, [r11+38h]
0x18004f551  mov     rsp, r11
0x18004f554  pop     r15
0x18004f556  pop     r14
0x18004f558  pop     r12
0x18004f55a  pop     rdi
0x18004f55b  pop     rbp
0x18004f55c  retn
```
