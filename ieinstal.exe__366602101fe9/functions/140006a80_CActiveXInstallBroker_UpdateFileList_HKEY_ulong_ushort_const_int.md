# CActiveXInstallBroker::UpdateFileList(HKEY__ *,ulong,ushort const * *,int *)

- ea: `0x140006a80`
- end: `0x140006d95`
- name: `?UpdateFileList@CActiveXInstallBroker@@AEAAJPEAUHKEY__@@KPEAPEBGPEAH@Z`
- size: `789`
- prototype: `int(CActiveXInstallBroker *__hidden this, HKEY, unsigned int, const unsigned __int16 **, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1400061e4`

## callees

- `0x140001af3`
- `0x140006a80`
- `0x1400109c0`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x140006beb`
- `ADVAPI32!RegDeleteValueW` at `0x140006beb`
- `ADVAPI32!RegSetValueExW` at `0x140006c6d`
- `ADVAPI32!RegSetValueExW` at `0x140006cfb`
- `ADVAPI32!RegSetValueExW` at `0x140006c6d`
- `ADVAPI32!RegSetValueExW` at `0x140006cfb`
- `ADVAPI32!RegCloseKey` at `0x140006d10`
- `ADVAPI32!RegCloseKey` at `0x140006d45`
- `ADVAPI32!RegCloseKey` at `0x140006d5b`
- `ADVAPI32!RegCloseKey` at `0x140006d10`
- `ADVAPI32!RegCloseKey` at `0x140006d45`
- `ADVAPI32!RegCloseKey` at `0x140006d5b`
- `ADVAPI32!RegEnumValueW` at `0x140006c23`
- `ADVAPI32!RegEnumValueW` at `0x140006c23`
- `ADVAPI32!RegCreateKeyW` at `0x140006b15`
- `ADVAPI32!RegCreateKeyW` at `0x140006b6a`
- `ADVAPI32!RegCreateKeyW` at `0x140006cbe`
- `ADVAPI32!RegCreateKeyW` at `0x140006b15`
- `ADVAPI32!RegCreateKeyW` at `0x140006b6a`
- `ADVAPI32!RegCreateKeyW` at `0x140006cbe`
- `ADVAPI32!RegOpenKeyExW` at `0x140006af1`
- `ADVAPI32!RegOpenKeyExW` at `0x140006b46`
- `ADVAPI32!RegOpenKeyExW` at `0x140006af1`
- `ADVAPI32!RegOpenKeyExW` at `0x140006b46`
- `KERNEL32!GetFileAttributesW` at `0x140006bce`
- `KERNEL32!GetFileAttributesW` at `0x140006bce`
- `msvcrt!wcsrchr` at `0x140006c91`
- `msvcrt!wcsrchr` at `0x140006c91`

## pseudocode

```c
__int64 __fastcall CActiveXInstallBroker::UpdateFileList(
        CActiveXInstallBroker *this,
        HKEY a2,
        unsigned int a3,
        const unsigned __int16 **a4,
        int *a5)
{
  LSTATUS KeyW; // eax
  bool v9; // cc
  HKEY v10; // rbx
  unsigned int v11; // edi
  DWORD v12; // edx
  int v13; // esi
  HKEY v14; // rcx
  __int64 i; // rbx
  const WCHAR *v16; // rdx
  wchar_t *v17; // rax
  const WCHAR *v18; // rax
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName[2]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR FileName; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v25[526]; // [rsp+62h] [rbp-9Eh] BYREF

  hKey = 0;
  phkResult = 0;
  if ( RegOpenKeyExW(a2, L"Files", 0, 0x2001Fu, &hKey)
    && a3
    && (KeyW = RegCreateKeyW(a2, L"Files", &hKey), v9 = KeyW <= 0, KeyW)
    || RegOpenKeyExW(a2, L"FilesFlags", 0, 0xF003Fu, &phkResult)
    && a3
    && (KeyW = RegCreateKeyW(a2, L"FilesFlags", &phkResult), v9 = KeyW <= 0, KeyW) )
  {
LABEL_25:
    if ( v9 )
      v11 = KeyW;
    else
      v11 = (unsigned __int16)KeyW | 0x80070000;
  }
  else
  {
    v10 = hKey;
    v11 = 0;
    if ( hKey )
    {
      Type = 1;
      FileName = 0;
      cchValueName[0] = 260;
      memset_0(v25, 0, 0x206u);
      v12 = 0;
      v13 = 1;
      v14 = v10;
      while ( !RegEnumValueW(v14, v12, &FileName, cchValueName, 0, &Type, 0, 0) )
      {
        cchValueName[0] = 260;
        if ( GetFileAttributesW(&FileName) == -1 )
        {
          v13 = 0;
          RegDeleteValueW(hKey, &FileName);
        }
        v14 = hKey;
        v12 = v13++;
      }
    }
    for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
    {
      v16 = a4[i];
      if ( v16 )
      {
        KeyW = RegSetValueExW(hKey, v16, 0, 1u, (const BYTE *)&Data, 1u);
        v9 = KeyW <= 0;
        if ( KeyW )
          goto LABEL_25;
        if ( a5 )
        {
          v17 = wcsrchr(a4[i], 0x5Cu);
          if ( v17 )
            v18 = v17 + 1;
          else
            v18 = a4[i];
          *(_QWORD *)cchValueName = 0;
          KeyW = RegCreateKeyW(phkResult, v18, (PHKEY)cchValueName);
          v9 = KeyW <= 0;
          if ( KeyW )
            goto LABEL_25;
          Type = a5[i];
          KeyW = RegSetValueExW(*(HKEY *)cchValueName, L"RedirectToHKCU", 0, 4u, (const BYTE *)&Type, 4u);
          v9 = KeyW <= 0;
          if ( KeyW )
            goto LABEL_25;
          RegCloseKey(*(HKEY *)cchValueName);
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v11;
}

```

## disassembly

```asm
0x140006a80  mov     [rsp-8+arg_0], rbx
0x140006a85  mov     [rsp-8+arg_10], rsi
0x140006a8a  push    rbp
0x140006a8b  push    rdi
0x140006a8c  push    r12
0x140006a8e  push    r14
0x140006a90  push    r15
0x140006a92  lea     rbp, [rsp-180h]
0x140006a9a  sub     rsp, 280h
0x140006aa1  mov     rax, cs:__security_cookie
0x140006aa8  xor     rax, rsp
0x140006aab  mov     [rbp+1A0h+var_30], rax
0x140006ab2  mov     r12, [rbp+1A0h+arg_20]
0x140006ab9  lea     rax, [rsp+2A0h+hKey]
0x140006abe  mov     rbx, rdx
0x140006ac1  mov     [rsp+2A0h+hKey], 0
0x140006aca  mov     r15, r9
0x140006acd  mov     [rsp+2A0h+var_248], 0
0x140006ad6  mov     r14d, r8d
0x140006ad9  mov     [rsp+2A0h+phkResult], rax; phkResult
0x140006ade  mov     rcx, rbx; hKey
0x140006ae1  lea     rdx, aFiles; "Files"
0x140006ae8  mov     r9d, 2001Fh; samDesired
0x140006aee  xor     r8d, r8d; ulOptions
0x140006af1  call    cs:__imp_RegOpenKeyExW
0x140006af8  nop     dword ptr [rax+rax+00h]
0x140006afd  test    eax, eax
0x140006aff  jz      short loc_140006B29
0x140006b01  test    r14d, r14d
0x140006b04  jz      short loc_140006B29
0x140006b06  lea     r8, [rsp+2A0h+hKey]; phkResult
0x140006b0b  mov     rcx, rbx; hKey
0x140006b0e  lea     rdx, aFiles; "Files"
0x140006b15  call    cs:__imp_RegCreateKeyW
0x140006b1c  nop     dword ptr [rax+rax+00h]
0x140006b21  test    eax, eax
0x140006b23  jnz     loc_140006D29
0x140006b29  lea     rax, [rsp+2A0h+var_248]
0x140006b2e  mov     r9d, 0F003Fh; samDesired
0x140006b34  xor     r8d, r8d; ulOptions
0x140006b37  mov     [rsp+2A0h+phkResult], rax; phkResult
0x140006b3c  lea     rdx, aFilesflags; "FilesFlags"
0x140006b43  mov     rcx, rbx; hKey
0x140006b46  call    cs:__imp_RegOpenKeyExW
0x140006b4d  nop     dword ptr [rax+rax+00h]
0x140006b52  test    eax, eax
0x140006b54  jz      short loc_140006B7E
0x140006b56  test    r14d, r14d
0x140006b59  jz      short loc_140006B7E
0x140006b5b  lea     r8, [rsp+2A0h+var_248]; phkResult
0x140006b60  mov     rcx, rbx; hKey
0x140006b63  lea     rdx, aFilesflags; "FilesFlags"
0x140006b6a  call    cs:__imp_RegCreateKeyW
0x140006b71  nop     dword ptr [rax+rax+00h]
0x140006b76  test    eax, eax
0x140006b78  jnz     loc_140006D29
0x140006b7e  mov     rbx, [rsp+2A0h+hKey]
0x140006b83  xor     edi, edi
0x140006b85  test    rbx, rbx
0x140006b88  jz      loc_140006C33
0x140006b8e  xor     eax, eax
0x140006b90  mov     [rsp+2A0h+Type], 1
0x140006b98  xor     edx, edx; Val
0x140006b9a  mov     [rsp+2A0h+FileName], ax
0x140006b9f  mov     r8d, 206h; Size
0x140006ba5  mov     [rsp+2A0h+cchValueName], 104h
0x140006bad  lea     rcx, [rsp+2A0h+var_23E]; void *
0x140006bb2  call    memset_0
0x140006bb7  xor     edx, edx
0x140006bb9  lea     esi, [rdi+1]
0x140006bbc  mov     rcx, rbx
0x140006bbf  jmp     short loc_140006C00
0x140006bc1  lea     rcx, [rsp+2A0h+FileName]; lpFileName
0x140006bc6  mov     [rsp+2A0h+cchValueName], 104h
0x140006bce  call    cs:__imp_GetFileAttributesW
0x140006bd5  nop     dword ptr [rax+rax+00h]
0x140006bda  cmp     eax, 0FFFFFFFFh
0x140006bdd  jnz     short loc_140006BF7
0x140006bdf  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140006be4  lea     rdx, [rsp+2A0h+FileName]; lpValueName
0x140006be9  xor     esi, esi
0x140006beb  call    cs:__imp_RegDeleteValueW
0x140006bf2  nop     dword ptr [rax+rax+00h]
0x140006bf7  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140006bfc  mov     edx, esi; dwIndex
0x140006bfe  inc     esi
0x140006c00  mov     [rsp+2A0h+lpcbData], rdi; lpcbData
0x140006c05  lea     rax, [rsp+2A0h+Type]
0x140006c0a  mov     [rsp+2A0h+lpData], rdi; lpData
0x140006c0f  lea     r9, [rsp+2A0h+cchValueName]; lpcchValueName
0x140006c14  mov     [rsp+2A0h+lpType], rax; lpType
0x140006c19  lea     r8, [rsp+2A0h+FileName]; lpValueName
0x140006c1e  mov     [rsp+2A0h+phkResult], rdi; lpReserved
0x140006c23  call    cs:__imp_RegEnumValueW
0x140006c2a  nop     dword ptr [rax+rax+00h]
0x140006c2f  test    eax, eax
0x140006c31  jz      short loc_140006BC1
0x140006c33  xor     ebx, ebx
0x140006c35  test    r14d, r14d
0x140006c38  jz      loc_140006D38
0x140006c3e  mov     rdx, [r15+rbx*8]; lpValueName
0x140006c42  test    rdx, rdx
0x140006c45  jz      loc_140006D1C
0x140006c4b  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140006c50  lea     rax, Data
0x140006c57  mov     dword ptr [rsp+2A0h+lpType], 1; cbData
0x140006c5f  mov     r9d, 1; dwType
0x140006c65  xor     r8d, r8d; Reserved
0x140006c68  mov     [rsp+2A0h+phkResult], rax; lpData
0x140006c6d  call    cs:__imp_RegSetValueExW
0x140006c74  nop     dword ptr [rax+rax+00h]
0x140006c79  test    eax, eax
0x140006c7b  jnz     loc_140006D29
0x140006c81  test    r12, r12
0x140006c84  jz      loc_140006D1C
0x140006c8a  mov     rcx, [r15+rbx*8]; Str
0x140006c8e  lea     edx, [rax+5Ch]; Ch
0x140006c91  call    cs:__imp_wcsrchr
0x140006c98  nop     dword ptr [rax+rax+00h]
0x140006c9d  test    rax, rax
0x140006ca0  jz      short loc_140006CA8
0x140006ca2  add     rax, 2
0x140006ca6  jmp     short loc_140006CAC
0x140006ca8  mov     rax, [r15+rbx*8]
0x140006cac  mov     rcx, [rsp+2A0h+var_248]; hKey
0x140006cb1  lea     r8, [rsp+2A0h+cchValueName]; phkResult
0x140006cb6  mov     rdx, rax; lpSubKey
0x140006cb9  mov     qword ptr [rsp+2A0h+cchValueName], rdi
0x140006cbe  call    cs:__imp_RegCreateKeyW
0x140006cc5  nop     dword ptr [rax+rax+00h]
0x140006cca  test    eax, eax
0x140006ccc  jnz     short loc_140006D29
0x140006cce  mov     eax, [r12+rbx*4]
0x140006cd2  lea     rdx, aRedirecttohkcu; "RedirectToHKCU"
0x140006cd9  mov     ecx, 4
0x140006cde  mov     [rsp+2A0h+Type], eax
0x140006ce2  mov     dword ptr [rsp+2A0h+lpType], ecx; cbData
0x140006ce6  lea     rax, [rsp+2A0h+Type]
0x140006ceb  mov     r9d, ecx; dwType
0x140006cee  mov     [rsp+2A0h+phkResult], rax; lpData
0x140006cf3  mov     rcx, qword ptr [rsp+2A0h+cchValueName]; hKey
0x140006cf8  xor     r8d, r8d; Reserved
0x140006cfb  call    cs:__imp_RegSetValueExW
0x140006d02  nop     dword ptr [rax+rax+00h]
0x140006d07  test    eax, eax
0x140006d09  jnz     short loc_140006D29
0x140006d0b  mov     rcx, qword ptr [rsp+2A0h+cchValueName]; hKey
0x140006d10  call    cs:__imp_RegCloseKey
0x140006d17  nop     dword ptr [rax+rax+00h]
0x140006d1c  inc     ebx
0x140006d1e  cmp     ebx, r14d
0x140006d21  jb      loc_140006C3E
0x140006d27  jmp     short loc_140006D38
0x140006d29  jg      short loc_140006D2F
0x140006d2b  mov     edi, eax
0x140006d2d  jmp     short loc_140006D38
0x140006d2f  movzx   edi, ax
0x140006d32  or      edi, 80070000h
0x140006d38  mov     rbx, [rsp+2A0h+hKey]
0x140006d3d  test    rbx, rbx
0x140006d40  jz      short loc_140006D51
0x140006d42  mov     rcx, rbx; hKey
0x140006d45  call    cs:__imp_RegCloseKey
0x140006d4c  nop     dword ptr [rax+rax+00h]
0x140006d51  mov     rcx, [rsp+2A0h+var_248]; hKey
0x140006d56  test    rcx, rcx
0x140006d59  jz      short loc_140006D67
0x140006d5b  call    cs:__imp_RegCloseKey
0x140006d62  nop     dword ptr [rax+rax+00h]
0x140006d67  mov     eax, edi
0x140006d69  mov     rcx, [rbp+1A0h+var_30]
0x140006d70  xor     rcx, rsp; StackCookie
0x140006d73  call    __security_check_cookie
0x140006d78  lea     r11, [rsp+2A0h+var_20]
0x140006d80  mov     rbx, [r11+30h]
0x140006d84  mov     rsi, [r11+40h]
0x140006d88  mov     rsp, r11
0x140006d8b  pop     r15
0x140006d8d  pop     r14
0x140006d8f  pop     r12
0x140006d91  pop     rdi
0x140006d92  pop     rbp
0x140006d93  retn
```
