# SetUserName

- ea: `0x18000fb1c`
- end: `0x18000fe3e`
- name: `SetUserName`
- size: `802`
- prototype: `int __fastcall(HKEY, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e5f4`

## callees

- `0x1800016c8`
- `0x18000e2e0`
- `0x18000fb1c`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x18000fc02`
- `msvcrt!_snwprintf_s` at `0x18000fc02`
- `msvcrt!wcscpy_s` at `0x18000fd4d`
- `msvcrt!wcscpy_s` at `0x18000fd4d`
- `KERNEL32!GlobalFree` at `0x18000fd15`
- `KERNEL32!GlobalFree` at `0x18000fd15`
- `KERNEL32!GlobalAlloc` at `0x18000fbbb`
- `KERNEL32!GlobalAlloc` at `0x18000fbbb`
- `ADVAPI32!RegSetValueExW` at `0x18000fcf5`
- `ADVAPI32!RegSetValueExW` at `0x18000fcf5`
- `ADVAPI32!RegDeleteValueW` at `0x18000fcb4`
- `ADVAPI32!RegDeleteValueW` at `0x18000fcb4`
- `ADVAPI32!RegCloseKey` at `0x18000fd06`
- `ADVAPI32!RegCloseKey` at `0x18000fdf8`
- `ADVAPI32!RegCloseKey` at `0x18000fd06`
- `ADVAPI32!RegCloseKey` at `0x18000fdf8`
- `ADVAPI32!RegQueryValueExW` at `0x18000fc78`
- `ADVAPI32!RegQueryValueExW` at `0x18000fde5`
- `ADVAPI32!RegQueryValueExW` at `0x18000fc78`
- `ADVAPI32!RegQueryValueExW` at `0x18000fde5`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fc2c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fda1`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fc2c`
- `ADVAPI32!RegOpenKeyExW` at `0x18000fda1`

## pseudocode

```c
int __fastcall SetUserName(HKEY a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r13
  __int64 v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rbx
  unsigned int v8; // r14d
  wchar_t *v9; // rax
  wchar_t *v10; // rsi
  HKEY v11; // r14
  LSTATUS v12; // ebx
  unsigned __int64 v13; // rcx
  DWORD v14; // r8d
  BYTE *v15; // r9
  const wchar_t *p_fOAEP; // r8
  unsigned __int64 v17; // rcx
  DWORD *phkResult; // [rsp+20h] [rbp-E0h]
  PBYTE *lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v22; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h]
  struct _INFORMATIONCARD_CRYPTO_HANDLE Data[22]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 fOAEP; // [rsp+260h] [rbp+160h] BYREF
  BOOL fOAEP_2; // [rsp+262h] [rbp+162h] BYREF

  v3 = *(_QWORD *)(a3 + 8);
  hKey = a1;
  v22 = 0;
  LOWORD(Data[0].type) = 0;
  memset_0((char *)&Data[0].type + 2, 0, 0x206u);
  cbData = 0;
  Type = 0;
  fOAEP = 0;
  memset_0(&fOAEP_2, 0, 0x206u);
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)(a2 + 2 * v6) );
  v7 = (unsigned int)(v6 + 8);
  v8 = v6 + 8;
  v9 = (wchar_t *)GlobalAlloc(0x40u, 2 * v7);
  v10 = v9;
  if ( v9 )
  {
    memset_0(v9, 0, 2 * v7);
    lpcbData = (PBYTE *)L"\\Auth";
    _snwprintf_s(v10, v8, (unsigned int)(v7 - 1), L"%s%s", a2);
    v11 = hKey;
    v12 = RegOpenKeyExW(hKey, v10, 0, 0xF003Fu, &v22);
    if ( !v12 )
    {
      cbData = 518;
      v12 = RegQueryValueExW(v22, L"User", 0, &Type, (LPBYTE)Data, &cbData);
      if ( !v12 && Type == 1 )
      {
        v13 = cbData & 0xFFFFFFFE;
        if ( v13 >= 0x208 )
          goto LABEL_23;
        *(_WORD *)((char *)&Data[0].type + v13) = 0;
        RegDeleteValueW(v22, L"User");
        do
          ++v5;
        while ( *((_WORD *)&Data[0].type + v5) );
        RegSetValueExW(v22, L"User", 0, 3u, (const BYTE *)Data, 2 * v5 + 2);
      }
      RegCloseKey(v22);
    }
    GlobalFree(v10);
    if ( !v12 && cbData > 1 )
    {
      Decrypt(Data, (BOOL)&fOAEP, v14, v15, phkResult, lpcbData);
      p_fOAEP = (const wchar_t *)&fOAEP;
LABEL_15:
      LODWORD(v9) = wcscpy_s((wchar_t *)(v3 + 16), 0x104u, p_fOAEP);
      return (int)v9;
    }
    LODWORD(v9) = RegOpenKeyExW(v11, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon", 0, 0x20019u, &v22);
    if ( !(_DWORD)v9 )
    {
      LOWORD(Data[0].type) = 0;
      cbData = 518;
      v12 = RegQueryValueExW(v22, L"DefaultUserName", 0, 0, (LPBYTE)Data, &cbData);
      LODWORD(v9) = RegCloseKey(v22);
    }
    if ( !v12 && cbData > 1 )
    {
      v17 = cbData & 0xFFFFFFFE;
      if ( v17 < 0x208 )
      {
        *(_WORD *)((char *)&Data[0].type + v17) = 0;
        p_fOAEP = (const wchar_t *)Data;
        goto LABEL_15;
      }
LABEL_23:
      _report_rangecheckfailure();
    }
  }
  return (int)v9;
}

```

## disassembly

```asm
0x18000fb1c  mov     [rsp-8+arg_18], rbx
0x18000fb21  push    rbp
0x18000fb22  push    rsi
0x18000fb23  push    rdi
0x18000fb24  push    r12
0x18000fb26  push    r13
0x18000fb28  push    r14
0x18000fb2a  push    r15
0x18000fb2c  lea     rbp, [rsp-380h]
0x18000fb34  sub     rsp, 480h
0x18000fb3b  mov     rax, cs:__security_cookie
0x18000fb42  xor     rax, rsp
0x18000fb45  mov     [rbp+3B0h+var_40], rax
0x18000fb4c  mov     r13, [r8+8]
0x18000fb50  mov     r12, rdx
0x18000fb53  mov     [rsp+4B0h+hKey], rcx
0x18000fb58  xor     esi, esi
0x18000fb5a  mov     edi, 206h
0x18000fb5f  mov     [rsp+4B0h+var_478], rsi
0x18000fb64  mov     r8d, edi; Size
0x18000fb67  mov     word ptr [rsp+4B0h+Data], si
0x18000fb6c  xor     edx, edx; Val
0x18000fb6e  lea     rcx, [rsp+4B0h+var_45E]; void *
0x18000fb73  call    memset_0
0x18000fb78  mov     r8d, edi; Size
0x18000fb7b  mov     [rsp+4B0h+cbData], esi
0x18000fb7f  xor     edx, edx; Val
0x18000fb81  mov     [rsp+4B0h+Type], esi
0x18000fb85  lea     rcx, [rbp+3B0h+fOAEP+2]; void *
0x18000fb8c  mov     word ptr [rbp+3B0h+fOAEP], si
0x18000fb93  call    memset_0
0x18000fb98  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000fb9c  mov     rax, rdi
0x18000fb9f  inc     rax
0x18000fba2  cmp     [r12+rax*2], si
0x18000fba7  jnz     short loc_18000FB9F
0x18000fba9  lea     ebx, [rax+8]
0x18000fbac  mov     ecx, 40h ; '@'; uFlags
0x18000fbb1  lea     r15, [rbx+rbx]
0x18000fbb5  mov     r14d, ebx
0x18000fbb8  mov     rdx, r15; dwBytes
0x18000fbbb  call    cs:__imp_GlobalAlloc
0x18000fbc2  nop     dword ptr [rax+rax+00h]
0x18000fbc7  mov     rsi, rax
0x18000fbca  test    rax, rax
0x18000fbcd  jz      loc_18000FD59
0x18000fbd3  mov     r8, r15; Size
0x18000fbd6  xor     edx, edx; Val
0x18000fbd8  mov     rcx, rax; void *
0x18000fbdb  call    memset_0
0x18000fbe0  lea     rax, aAuth; "\\Auth"
0x18000fbe7  mov     edx, r14d; BufferCount
0x18000fbea  mov     [rsp+4B0h+lpcbData], rax
0x18000fbef  lea     r8d, [rbx-1]; MaxCount
0x18000fbf3  lea     r9, aSS_0; "%s%s"
0x18000fbfa  mov     [rsp+4B0h+phkResult], r12
0x18000fbff  mov     rcx, rsi; Buffer
0x18000fc02  call    cs:__imp__snwprintf_s
0x18000fc09  nop     dword ptr [rax+rax+00h]
0x18000fc0e  mov     r14, [rsp+4B0h+hKey]
0x18000fc13  lea     rax, [rsp+4B0h+var_478]
0x18000fc18  mov     rcx, r14; hKey
0x18000fc1b  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18000fc20  mov     r9d, 0F003Fh; samDesired
0x18000fc26  xor     r8d, r8d; ulOptions
0x18000fc29  mov     rdx, rsi; lpSubKey
0x18000fc2c  call    cs:__imp_RegOpenKeyExW
0x18000fc33  nop     dword ptr [rax+rax+00h]
0x18000fc38  xor     r15d, r15d
0x18000fc3b  mov     ebx, eax
0x18000fc3d  test    eax, eax
0x18000fc3f  jnz     loc_18000FD12
0x18000fc45  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000fc4a  lea     rax, [rsp+4B0h+cbData]
0x18000fc4f  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x18000fc54  lea     r12, aUser; "User"
0x18000fc5b  lea     rax, [rsp+4B0h+Data]
0x18000fc60  mov     [rsp+4B0h+cbData], 206h
0x18000fc68  lea     r9, [rsp+4B0h+Type]; lpType
0x18000fc6d  mov     [rsp+4B0h+phkResult], rax; lpData
0x18000fc72  xor     r8d, r8d; lpReserved
0x18000fc75  mov     rdx, r12; lpValueName
0x18000fc78  call    cs:__imp_RegQueryValueExW
0x18000fc7f  nop     dword ptr [rax+rax+00h]
0x18000fc84  mov     ebx, eax
0x18000fc86  test    eax, eax
0x18000fc88  jnz     short loc_18000FD01
0x18000fc8a  cmp     [rsp+4B0h+Type], 1
0x18000fc8f  jnz     short loc_18000FD01
0x18000fc91  mov     ecx, [rsp+4B0h+cbData]
0x18000fc95  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000fc99  cmp     rcx, 208h
0x18000fca0  jnb     loc_18000FE38
0x18000fca6  mov     word ptr [rsp+rcx+4B0h+Data], r15w
0x18000fcac  mov     rdx, r12; lpValueName
0x18000fcaf  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000fcb4  call    cs:__imp_RegDeleteValueW
0x18000fcbb  nop     dword ptr [rax+rax+00h]
0x18000fcc0  lea     rax, [rsp+4B0h+Data]
0x18000fcc5  inc     rdi
0x18000fcc8  cmp     [rax+rdi*2], r15w
0x18000fccd  jnz     short loc_18000FCC5
0x18000fccf  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000fcd4  lea     eax, ds:2[rdi*2]
0x18000fcdb  mov     dword ptr [rsp+4B0h+lpcbData], eax; ppOutData
0x18000fcdf  mov     r9d, 3; dwType
0x18000fce5  lea     rax, [rsp+4B0h+Data]
0x18000fcea  xor     r8d, r8d; Reserved
0x18000fced  mov     rdx, r12; lpValueName
0x18000fcf0  mov     [rsp+4B0h+phkResult], rax; pcbOutData
0x18000fcf5  call    cs:__imp_RegSetValueExW
0x18000fcfc  nop     dword ptr [rax+rax+00h]
0x18000fd01  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000fd06  call    cs:__imp_RegCloseKey
0x18000fd0d  nop     dword ptr [rax+rax+00h]
0x18000fd12  mov     rcx, rsi; hMem
0x18000fd15  call    cs:__imp_GlobalFree
0x18000fd1c  nop     dword ptr [rax+rax+00h]
0x18000fd21  test    ebx, ebx
0x18000fd23  jnz     short loc_18000FD84
0x18000fd25  cmp     [rsp+4B0h+cbData], 1
0x18000fd2a  jbe     short loc_18000FD84
0x18000fd2c  lea     rdx, [rbp+3B0h+fOAEP]; fOAEP
0x18000fd33  lea     rcx, [rsp+4B0h+Data]; hCrypto
0x18000fd38  call    Decrypt
0x18000fd3d  lea     r8, [rbp+3B0h+fOAEP]; Source
0x18000fd44  lea     rcx, [r13+10h]; Destination
0x18000fd48  mov     edx, 104h; SizeInWords
0x18000fd4d  call    cs:__imp_wcscpy_s
0x18000fd54  nop     dword ptr [rax+rax+00h]
0x18000fd59  mov     rcx, [rbp+3B0h+var_40]
0x18000fd60  xor     rcx, rsp; StackCookie
0x18000fd63  call    __security_check_cookie
0x18000fd68  mov     rbx, [rsp+4B0h+arg_18]
0x18000fd70  add     rsp, 480h
0x18000fd77  pop     r15
0x18000fd79  pop     r14
0x18000fd7b  pop     r13
0x18000fd7d  pop     r12
0x18000fd7f  pop     rdi
0x18000fd80  pop     rsi
0x18000fd81  pop     rbp
0x18000fd82  retn
0x18000fd84  lea     rax, [rsp+4B0h+var_478]
0x18000fd89  mov     r9d, 20019h; samDesired
0x18000fd8f  xor     r8d, r8d; ulOptions
0x18000fd92  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18000fd97  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000fd9e  mov     rcx, r14; hKey
0x18000fda1  call    cs:__imp_RegOpenKeyExW
0x18000fda8  nop     dword ptr [rax+rax+00h]
0x18000fdad  test    eax, eax
0x18000fdaf  jnz     short loc_18000FE04
0x18000fdb1  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000fdb6  lea     rax, [rsp+4B0h+cbData]
0x18000fdbb  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x18000fdc0  lea     rdx, aDefaultusernam; "DefaultUserName"
0x18000fdc7  lea     rax, [rsp+4B0h+Data]
0x18000fdcc  mov     word ptr [rsp+4B0h+Data], r15w
0x18000fdd2  xor     r9d, r9d; lpType
0x18000fdd5  mov     [rsp+4B0h+phkResult], rax; lpData
0x18000fdda  xor     r8d, r8d; lpReserved
0x18000fddd  mov     [rsp+4B0h+cbData], 206h
0x18000fde5  call    cs:__imp_RegQueryValueExW
0x18000fdec  nop     dword ptr [rax+rax+00h]
0x18000fdf1  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000fdf6  mov     ebx, eax
0x18000fdf8  call    cs:__imp_RegCloseKey
0x18000fdff  nop     dword ptr [rax+rax+00h]
0x18000fe04  test    ebx, ebx
0x18000fe06  jnz     loc_18000FD59
0x18000fe0c  cmp     [rsp+4B0h+cbData], 1
0x18000fe11  jbe     loc_18000FD59
0x18000fe17  mov     ecx, [rsp+4B0h+cbData]
0x18000fe1b  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000fe1f  cmp     rcx, 208h
0x18000fe26  jnb     short loc_18000FE38
0x18000fe28  mov     word ptr [rsp+rcx+4B0h+Data], r15w
0x18000fe2e  lea     r8, [rsp+4B0h+Data]
0x18000fe33  jmp     loc_18000FD44
0x18000fe38  call    __report_rangecheckfailure
```
