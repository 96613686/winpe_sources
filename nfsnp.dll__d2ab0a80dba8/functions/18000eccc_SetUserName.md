# SetUserName

- ea: `0x18000eccc`
- end: `0x18000efa5`
- name: `SetUserName`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d9b0`

## callees

- `0x1800016c8`
- `0x18000d6e4`
- `0x18000eccc`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x18000edac`
- `msvcrt!_snwprintf_s` at `0x18000edac`
- `msvcrt!wcscpy_s` at `0x18000eecd`
- `msvcrt!wcscpy_s` at `0x18000eecd`
- `KERNEL32!GlobalFree` at `0x18000ee9b`
- `KERNEL32!GlobalFree` at `0x18000ee9b`
- `KERNEL32!GlobalAlloc` at `0x18000ed6b`
- `KERNEL32!GlobalAlloc` at `0x18000ed6b`
- `ADVAPI32!RegSetValueExW` at `0x18000ee87`
- `ADVAPI32!RegSetValueExW` at `0x18000ee87`
- `ADVAPI32!RegDeleteValueW` at `0x18000ee4c`
- `ADVAPI32!RegDeleteValueW` at `0x18000ee4c`
- `ADVAPI32!RegCloseKey` at `0x18000ee92`
- `ADVAPI32!RegCloseKey` at `0x18000ef65`
- `ADVAPI32!RegCloseKey` at `0x18000ee92`
- `ADVAPI32!RegCloseKey` at `0x18000ef65`
- `ADVAPI32!RegQueryValueExW` at `0x18000ee16`
- `ADVAPI32!RegQueryValueExW` at `0x18000ef58`
- `ADVAPI32!RegQueryValueExW` at `0x18000ee16`
- `ADVAPI32!RegQueryValueExW` at `0x18000ef58`
- `ADVAPI32!RegOpenKeyExW` at `0x18000edd0`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ef1a`
- `ADVAPI32!RegOpenKeyExW` at `0x18000edd0`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ef1a`

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
0x18000eccc  mov     [rsp-8+arg_18], rbx
0x18000ecd1  push    rbp
0x18000ecd2  push    rsi
0x18000ecd3  push    rdi
0x18000ecd4  push    r12
0x18000ecd6  push    r13
0x18000ecd8  push    r14
0x18000ecda  push    r15
0x18000ecdc  lea     rbp, [rsp-380h]
0x18000ece4  sub     rsp, 480h
0x18000eceb  mov     rax, cs:__security_cookie
0x18000ecf2  xor     rax, rsp
0x18000ecf5  mov     [rbp+3B0h+var_40], rax
0x18000ecfc  mov     r13, [r8+8]
0x18000ed00  mov     r12, rdx
0x18000ed03  mov     [rsp+4B0h+hKey], rcx
0x18000ed08  xor     esi, esi
0x18000ed0a  mov     edi, 206h
0x18000ed0f  mov     [rsp+4B0h+var_478], rsi
0x18000ed14  mov     r8d, edi; Size
0x18000ed17  mov     word ptr [rsp+4B0h+Data], si
0x18000ed1c  xor     edx, edx; Val
0x18000ed1e  lea     rcx, [rsp+4B0h+var_45E]; void *
0x18000ed23  call    memset_0
0x18000ed28  mov     r8d, edi; Size
0x18000ed2b  mov     [rsp+4B0h+cbData], esi
0x18000ed2f  xor     edx, edx; Val
0x18000ed31  mov     [rsp+4B0h+Type], esi
0x18000ed35  lea     rcx, [rbp+3B0h+fOAEP+2]; void *
0x18000ed3c  mov     word ptr [rbp+3B0h+fOAEP], si
0x18000ed43  call    memset_0
0x18000ed48  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000ed4c  mov     rax, rdi
0x18000ed4f  inc     rax
0x18000ed52  cmp     [r12+rax*2], si
0x18000ed57  jnz     short loc_18000ED4F
0x18000ed59  lea     ebx, [rax+8]
0x18000ed5c  mov     ecx, 40h ; '@'; uFlags
0x18000ed61  lea     r15, [rbx+rbx]
0x18000ed65  mov     r14d, ebx
0x18000ed68  mov     rdx, r15; dwBytes
0x18000ed6b  call    cs:__imp_GlobalAlloc
0x18000ed71  mov     rsi, rax
0x18000ed74  test    rax, rax
0x18000ed77  jz      loc_18000EED3
0x18000ed7d  mov     r8, r15; Size
0x18000ed80  xor     edx, edx; Val
0x18000ed82  mov     rcx, rax; void *
0x18000ed85  call    memset_0
0x18000ed8a  lea     rax, aAuth; "\\Auth"
0x18000ed91  mov     edx, r14d; BufferCount
0x18000ed94  mov     [rsp+4B0h+lpcbData], rax
0x18000ed99  lea     r8d, [rbx-1]; MaxCount
0x18000ed9d  lea     r9, aSS_0; "%s%s"
0x18000eda4  mov     [rsp+4B0h+phkResult], r12
0x18000eda9  mov     rcx, rsi; Buffer
0x18000edac  call    cs:__imp__snwprintf_s
0x18000edb2  mov     r14, [rsp+4B0h+hKey]
0x18000edb7  lea     rax, [rsp+4B0h+var_478]
0x18000edbc  mov     rcx, r14; hKey
0x18000edbf  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18000edc4  mov     r9d, 0F003Fh; samDesired
0x18000edca  xor     r8d, r8d; ulOptions
0x18000edcd  mov     rdx, rsi; lpSubKey
0x18000edd0  call    cs:__imp_RegOpenKeyExW
0x18000edd6  xor     r15d, r15d
0x18000edd9  mov     ebx, eax
0x18000eddb  test    eax, eax
0x18000eddd  jnz     loc_18000EE98
0x18000ede3  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000ede8  lea     rax, [rsp+4B0h+cbData]
0x18000eded  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x18000edf2  lea     r12, aUser; "User"
0x18000edf9  lea     rax, [rsp+4B0h+Data]
0x18000edfe  mov     [rsp+4B0h+cbData], 206h
0x18000ee06  lea     r9, [rsp+4B0h+Type]; lpType
0x18000ee0b  mov     [rsp+4B0h+phkResult], rax; lpData
0x18000ee10  xor     r8d, r8d; lpReserved
0x18000ee13  mov     rdx, r12; lpValueName
0x18000ee16  call    cs:__imp_RegQueryValueExW
0x18000ee1c  mov     ebx, eax
0x18000ee1e  test    eax, eax
0x18000ee20  jnz     short loc_18000EE8D
0x18000ee22  cmp     [rsp+4B0h+Type], 1
0x18000ee27  jnz     short loc_18000EE8D
0x18000ee29  mov     ecx, [rsp+4B0h+cbData]
0x18000ee2d  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000ee31  cmp     rcx, 208h
0x18000ee38  jnb     loc_18000EF9F
0x18000ee3e  mov     word ptr [rsp+rcx+4B0h+Data], r15w
0x18000ee44  mov     rdx, r12; lpValueName
0x18000ee47  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000ee4c  call    cs:__imp_RegDeleteValueW
0x18000ee52  lea     rax, [rsp+4B0h+Data]
0x18000ee57  inc     rdi
0x18000ee5a  cmp     [rax+rdi*2], r15w
0x18000ee5f  jnz     short loc_18000EE57
0x18000ee61  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000ee66  lea     eax, ds:2[rdi*2]
0x18000ee6d  mov     dword ptr [rsp+4B0h+lpcbData], eax; ppOutData
0x18000ee71  mov     r9d, 3; dwType
0x18000ee77  lea     rax, [rsp+4B0h+Data]
0x18000ee7c  xor     r8d, r8d; Reserved
0x18000ee7f  mov     rdx, r12; lpValueName
0x18000ee82  mov     [rsp+4B0h+phkResult], rax; pcbOutData
0x18000ee87  call    cs:__imp_RegSetValueExW
0x18000ee8d  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000ee92  call    cs:__imp_RegCloseKey
0x18000ee98  mov     rcx, rsi; hMem
0x18000ee9b  call    cs:__imp_GlobalFree
0x18000eea1  test    ebx, ebx
0x18000eea3  jnz     short loc_18000EEFD
0x18000eea5  cmp     [rsp+4B0h+cbData], 1
0x18000eeaa  jbe     short loc_18000EEFD
0x18000eeac  lea     rdx, [rbp+3B0h+fOAEP]; fOAEP
0x18000eeb3  lea     rcx, [rsp+4B0h+Data]; hCrypto
0x18000eeb8  call    Decrypt
0x18000eebd  lea     r8, [rbp+3B0h+fOAEP]; Source
0x18000eec4  lea     rcx, [r13+10h]; Destination
0x18000eec8  mov     edx, 104h; SizeInWords
0x18000eecd  call    cs:__imp_wcscpy_s
0x18000eed3  mov     rcx, [rbp+3B0h+var_40]
0x18000eeda  xor     rcx, rsp; StackCookie
0x18000eedd  call    __security_check_cookie
0x18000eee2  mov     rbx, [rsp+4B0h+arg_18]
0x18000eeea  add     rsp, 480h
0x18000eef1  pop     r15
0x18000eef3  pop     r14
0x18000eef5  pop     r13
0x18000eef7  pop     r12
0x18000eef9  pop     rdi
0x18000eefa  pop     rsi
0x18000eefb  pop     rbp
0x18000eefc  retn
0x18000eefd  lea     rax, [rsp+4B0h+var_478]
0x18000ef02  mov     r9d, 20019h; samDesired
0x18000ef08  xor     r8d, r8d; ulOptions
0x18000ef0b  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18000ef10  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18000ef17  mov     rcx, r14; hKey
0x18000ef1a  call    cs:__imp_RegOpenKeyExW
0x18000ef20  test    eax, eax
0x18000ef22  jnz     short loc_18000EF6B
0x18000ef24  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000ef29  lea     rax, [rsp+4B0h+cbData]
0x18000ef2e  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x18000ef33  lea     rdx, aDefaultusernam; "DefaultUserName"
0x18000ef3a  lea     rax, [rsp+4B0h+Data]
0x18000ef3f  mov     word ptr [rsp+4B0h+Data], r15w
0x18000ef45  xor     r9d, r9d; lpType
0x18000ef48  mov     [rsp+4B0h+phkResult], rax; lpData
0x18000ef4d  xor     r8d, r8d; lpReserved
0x18000ef50  mov     [rsp+4B0h+cbData], 206h
0x18000ef58  call    cs:__imp_RegQueryValueExW
0x18000ef5e  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000ef63  mov     ebx, eax
0x18000ef65  call    cs:__imp_RegCloseKey
0x18000ef6b  test    ebx, ebx
0x18000ef6d  jnz     loc_18000EED3
0x18000ef73  cmp     [rsp+4B0h+cbData], 1
0x18000ef78  jbe     loc_18000EED3
0x18000ef7e  mov     ecx, [rsp+4B0h+cbData]
0x18000ef82  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18000ef86  cmp     rcx, 208h
0x18000ef8d  jnb     short loc_18000EF9F
0x18000ef8f  mov     word ptr [rsp+rcx+4B0h+Data], r15w
0x18000ef95  lea     r8, [rsp+4B0h+Data]
0x18000ef9a  jmp     loc_18000EEC4
0x18000ef9f  call    __report_rangecheckfailure
```
