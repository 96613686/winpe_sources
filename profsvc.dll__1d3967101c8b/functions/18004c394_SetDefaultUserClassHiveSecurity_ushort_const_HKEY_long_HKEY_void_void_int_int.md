# SetDefaultUserClassHiveSecurity_(ushort const *,HKEY__ *,long (*)(HKEY__ *,void *,void *,int,int))

- ea: `0x18004c394`
- end: `0x18004c54d`
- name: `?SetDefaultUserClassHiveSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z`
- size: `441`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY hKey, int (*)(HKEY, void *, void *, int, int))`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011200`
- `0x1800350cc`

## callees

- `0x180027910`
- `0x18003fe18`
- `0x18003fe74`
- `0x18004c394`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c408`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c408`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c431`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c511`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c431`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c511`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004c4d2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004c4d2`

## string_xrefs

- `0x18004c437`: `Local Settings\MuiCache`

## pseudocode

```c
__int64 __fastcall SetDefaultUserClassHiveSecurity_(
        const unsigned __int16 *a1,
        HKEY hKey,
        __int64 (__fastcall *a3)(HKEY handle, PSECURITY_DESCRIPTOR pSecurityDescriptor, void *))
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
0x18004c394  mov     [rsp-8+arg_0], rbx
0x18004c399  mov     [rsp-8+arg_8], rsi
0x18004c39e  push    rbp
0x18004c39f  push    rdi
0x18004c3a0  push    r12
0x18004c3a2  push    r14
0x18004c3a4  push    r15
0x18004c3a6  lea     rbp, [rsp-37h]
0x18004c3ab  sub     rsp, 0A0h
0x18004c3b2  mov     r14, r8
0x18004c3b5  mov     r9, r8; int (*)(HKEY, void *, void *, int, int)
0x18004c3b8  mov     edi, 1
0x18004c3bd  mov     r12, rdx
0x18004c3c0  mov     r8d, edi; int
0x18004c3c3  mov     r15, rcx
0x18004c3c6  call    ?SetHiveLpacSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveLpacSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18004c3cb  mov     ebx, eax
0x18004c3cd  test    eax, eax
0x18004c3cf  js      loc_18004C52F
0x18004c3d5  lea     rax, ?ApplySecurityToRegistryKey_@@YAJPEAUHKEY__@@PEAX1HH@Z; ApplySecurityToRegistryKey_(HKEY__ *,void *,void *,int,int)
0x18004c3dc  mov     [rbp+57h+hKey], 0
0x18004c3e4  lea     rbx, aLocalSettings; "Local Settings"
0x18004c3eb  cmp     r14, rax
0x18004c3ee  jz      short loc_18004C437
0x18004c3f0  lea     rax, [rbp+57h+hKey]
0x18004c3f4  mov     r9d, 60019h; samDesired
0x18004c3fa  xor     r8d, r8d; ulOptions
0x18004c3fd  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18004c402  mov     rdx, rbx; lpSubKey
0x18004c405  mov     rcx, r12; hKey
0x18004c408  call    cs:__imp_RegOpenKeyExW
0x18004c40e  test    eax, eax
0x18004c410  jle     short loc_18004C41C
0x18004c412  movzx   eax, ax
0x18004c415  or      eax, 80070000h
0x18004c41a  test    eax, eax
0x18004c41c  js      short loc_18004C437
0x18004c41e  mov     rdx, [rbp+57h+hKey]; HKEY
0x18004c422  mov     r8, r14; int (*)(HKEY, void *, void *, int, int)
0x18004c425  mov     rcx, r15; unsigned __int16 *
0x18004c428  call    ?SetUserHiveSecurity_@@YAJPEBGPEAUHKEY__@@P6AJ1PEAX2HH@Z@Z; SetUserHiveSecurity_(ushort const *,HKEY__ *,long (*)(HKEY__ *,void *,void *,int,int))
0x18004c42d  mov     rcx, [rbp+57h+hKey]; hKey
0x18004c431  call    cs:__imp_RegCloseKey
0x18004c437  lea     rax, aLocalSettingsM; "Local Settings\\MuiCache"
0x18004c43e  mov     [rbp+57h+var_64], edi
0x18004c441  mov     [rbp+57h+var_60], rax
0x18004c445  lea     rax, aLocalSettingsS_0; "Local Settings\\Software"
0x18004c44c  mov     [rbp+57h+var_50], rax
0x18004c450  lea     rax, aLocalSettingsS; "Local Settings\\Software\\Microsoft"
0x18004c457  mov     [rbp+57h+var_40], rax
0x18004c45b  lea     rax, aLocalSettingsS_1; "Local Settings\\Software\\Microsoft\\Wi"...
0x18004c462  mov     [rbp+57h+var_58], edi
0x18004c465  mov     [rbp+57h+var_54], edi
0x18004c468  mov     [rbp+57h+var_44], edi
0x18004c46b  mov     [rbp+57h+var_34], edi
0x18004c46e  mov     [rbp+57h+var_28], edi
0x18004c471  mov     [rbp+57h+var_24], edi
0x18004c474  xor     edi, edi
0x18004c476  mov     [rbp+57h+var_30], rax
0x18004c47a  mov     [rbp+57h+lpSubKey], rbx
0x18004c47e  mov     [rbp+57h+var_68], 0
0x18004c485  mov     [rbp+57h+var_48], 0
0x18004c48c  mov     [rbp+57h+var_38], 0
0x18004c493  mov     [rsp+0C0h+lpdwDisposition], 0; lpdwDisposition
0x18004c49c  lea     rax, [rbp+57h+hKey]
0x18004c4a0  mov     [rsp+0C0h+var_88], rax; phkResult
0x18004c4a5  mov     rsi, rdi
0x18004c4a8  mov     [rsp+0C0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004c4b1  add     rsi, rsi
0x18004c4b4  mov     [rsp+0C0h+samDesired], 60019h; samDesired
0x18004c4bc  xor     r9d, r9d; lpClass
0x18004c4bf  xor     r8d, r8d; Reserved
0x18004c4c2  mov     dword ptr [rsp+0C0h+phkResult], 0; dwOptions
0x18004c4ca  mov     rcx, r12; hKey
0x18004c4cd  mov     rdx, [rbp+rsi*8+57h+lpSubKey]; lpSubKey
0x18004c4d2  call    cs:__imp_RegCreateKeyExW
0x18004c4d8  mov     ebx, eax
0x18004c4da  test    eax, eax
0x18004c4dc  jle     short loc_18004C4E7
0x18004c4de  movzx   ebx, ax
0x18004c4e1  or      ebx, 80070000h
0x18004c4e7  test    ebx, ebx
0x18004c4e9  js      short loc_18004C517
0x18004c4eb  cmp     [rbp+rsi*8+57h+var_64], 0
0x18004c4f0  mov     r9, r14; int (*)(HKEY, void *, void *, int, int)
0x18004c4f3  mov     r8d, [rbp+rsi*8+57h+var_68]; int
0x18004c4f8  mov     rcx, r15; unsigned __int16 *
0x18004c4fb  mov     rdx, [rbp+57h+hKey]; HKEY
0x18004c4ff  jz      short loc_18004C508
0x18004c501  call    ?SetHiveLpacSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveLpacSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18004c506  jmp     short loc_18004C50D
0x18004c508  call    ?SetHiveAppContainerSecurity_@@YAJPEBGPEAUHKEY__@@HP6AJ1PEAX2HH@Z@Z; SetHiveAppContainerSecurity_(ushort const *,HKEY__ *,int,long (*)(HKEY__ *,void *,void *,int,int))
0x18004c50d  mov     rcx, [rbp+57h+hKey]; hKey
0x18004c511  call    cs:__imp_RegCloseKey
0x18004c517  inc     rdi
0x18004c51a  cmp     rdi, 5
0x18004c51e  jb      loc_18004C493
0x18004c524  xor     eax, eax
0x18004c526  cmp     ebx, 80070002h
0x18004c52c  cmovz   ebx, eax
0x18004c52f  lea     r11, [rsp+0C0h+var_20]
0x18004c537  mov     eax, ebx
0x18004c539  mov     rbx, [r11+30h]
0x18004c53d  mov     rsi, [r11+38h]
0x18004c541  mov     rsp, r11
0x18004c544  pop     r15
0x18004c546  pop     r14
0x18004c548  pop     r12
0x18004c54a  pop     rdi
0x18004c54b  pop     rbp
0x18004c54c  retn
```
