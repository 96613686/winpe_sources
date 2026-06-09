# SetPasswd

- ea: `0x18000f384`
- end: `0x18000f643`
- name: `SetPasswd`
- size: `703`
- prototype: `int __fastcall(HKEY, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e5f4`

## callees

- `0x18000e2e0`
- `0x18000f384`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x18000f4c2`
- `msvcrt!_snwprintf_s` at `0x18000f4c2`
- `msvcrt!wcscpy_s` at `0x18000f60c`
- `msvcrt!wcscpy_s` at `0x18000f60c`
- `msvcrt!wcsncpy_s` at `0x18000f439`
- `msvcrt!wcsncpy_s` at `0x18000f439`
- `KERNEL32!GlobalFree` at `0x18000f5b5`
- `KERNEL32!GlobalFree` at `0x18000f5b5`
- `KERNEL32!GlobalAlloc` at `0x18000f476`
- `KERNEL32!GlobalAlloc` at `0x18000f476`
- `ADVAPI32!RegSetValueExW` at `0x18000f595`
- `ADVAPI32!RegSetValueExW` at `0x18000f595`
- `ADVAPI32!RegDeleteValueW` at `0x18000f558`
- `ADVAPI32!RegDeleteValueW` at `0x18000f558`
- `ADVAPI32!RegCloseKey` at `0x18000f5a6`
- `ADVAPI32!RegCloseKey` at `0x18000f5a6`
- `ADVAPI32!RegQueryValueExW` at `0x18000f536`
- `ADVAPI32!RegQueryValueExW` at `0x18000f536`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f4e9`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f4e9`

## pseudocode

```c
int __fastcall SetPasswd(HKEY a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rbx
  const wchar_t *v6; // r8
  DWORD v7; // r8d
  BYTE *v8; // r9
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r14
  unsigned int v12; // r15d
  wchar_t *v13; // rax
  wchar_t *v14; // rsi
  LSTATUS v15; // r14d
  const wchar_t *p_fOAEP; // r8
  DWORD *phkResult; // [rsp+20h] [rbp-E0h]
  PBYTE *lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h]
  HKEY hKey; // [rsp+48h] [rbp-B8h]
  struct _INFORMATIONCARD_CRYPTO_HANDLE Destination[21]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v26; // [rsp+256h] [rbp+156h]
  __int16 fOAEP; // [rsp+260h] [rbp+160h] BYREF
  BOOL fOAEP_2; // [rsp+262h] [rbp+162h] BYREF

  v23 = a2;
  hKey = a1;
  v22 = 0;
  LOWORD(Destination[0].type) = 0;
  memset_0((char *)&Destination[0].type + 2, 0, 0x206u);
  cbData = 0;
  Type = 0;
  fOAEP = 0;
  memset_0(&fOAEP_2, 0, 0x206u);
  v5 = *(_QWORD *)(a3 + 8);
  v26 = 0;
  if ( !*(_DWORD *)(a3 + 76) )
  {
    v6 = *(const wchar_t **)(v5 + 8);
    if ( v6 )
    {
      if ( !*(_QWORD *)v5 )
      {
        wcsncpy_s((wchar_t *)Destination, 0x104u, v6, 0x103u);
        cbData = 2;
LABEL_17:
        if ( *(_DWORD *)(a3 + 76) || !*(_QWORD *)(v5 + 8) || *(_QWORD *)v5 )
        {
          Decrypt(Destination, (BOOL)&fOAEP, v7, v8, phkResult, lpcbData);
          p_fOAEP = (const wchar_t *)&fOAEP;
        }
        else
        {
          p_fOAEP = (const wchar_t *)Destination;
        }
        LODWORD(v13) = wcscpy_s((wchar_t *)(v5 + 536), 0x104u, p_fOAEP);
        return (int)v13;
      }
    }
  }
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( *(_WORD *)(a2 + 2 * v10) );
  v11 = (unsigned int)(v10 + 8);
  v12 = v10 + 8;
  v13 = (wchar_t *)GlobalAlloc(0x40u, 2 * v11);
  v14 = v13;
  if ( v13 )
  {
    memset_0(v13, 0, 2 * v11);
    lpcbData = (PBYTE *)L"\\Auth";
    _snwprintf_s(v14, v12, (unsigned int)(v11 - 1), L"%s%s", v23);
    v15 = RegOpenKeyExW(hKey, v14, 0, 0xF003Fu, &v22);
    if ( !v15 )
    {
      cbData = 520;
      v15 = RegQueryValueExW(v22, L"Password", 0, &Type, (LPBYTE)Destination, &cbData);
      if ( !v15 && Type == 1 )
      {
        RegDeleteValueW(v22, L"Password");
        do
          ++v9;
        while ( *((_WORD *)&Destination[0].type + v9) );
        RegSetValueExW(v22, L"Password", 0, 3u, (const BYTE *)Destination, v9 + 1);
      }
      RegCloseKey(v22);
    }
    LODWORD(v13) = (unsigned int)GlobalFree(v14);
    if ( !v15 && cbData > 1 )
      goto LABEL_17;
  }
  return (int)v13;
}

```

## disassembly

```asm
0x18000f384  mov     [rsp-8+arg_18], rbx
0x18000f389  push    rbp
0x18000f38a  push    rsi
0x18000f38b  push    rdi
0x18000f38c  push    r12
0x18000f38e  push    r13
0x18000f390  push    r14
0x18000f392  push    r15
0x18000f394  lea     rbp, [rsp-380h]
0x18000f39c  sub     rsp, 480h
0x18000f3a3  mov     rax, cs:__security_cookie
0x18000f3aa  xor     rax, rsp
0x18000f3ad  mov     [rbp+3B0h+var_40], rax
0x18000f3b4  mov     r13, r8
0x18000f3b7  mov     [rsp+4B0h+var_470], rdx
0x18000f3bc  mov     rsi, rdx
0x18000f3bf  mov     [rsp+4B0h+hKey], rcx
0x18000f3c4  xor     r15d, r15d
0x18000f3c7  lea     rcx, [rsp+4B0h+var_45E]; void *
0x18000f3cc  mov     ebx, 206h
0x18000f3d1  mov     [rsp+4B0h+var_478], r15
0x18000f3d6  mov     r8d, ebx; Size
0x18000f3d9  mov     [rsp+4B0h+Destination], r15w
0x18000f3df  xor     edx, edx; Val
0x18000f3e1  call    memset_0
0x18000f3e6  mov     r8d, ebx; Size
0x18000f3e9  mov     [rsp+4B0h+cbData], r15d
0x18000f3ee  xor     edx, edx; Val
0x18000f3f0  mov     [rsp+4B0h+Type], r15d
0x18000f3f5  lea     rcx, [rbp+3B0h+fOAEP+2]; void *
0x18000f3fc  mov     word ptr [rbp+3B0h+fOAEP], r15w
0x18000f404  call    memset_0
0x18000f409  mov     edi, 104h
0x18000f40e  mov     rbx, [r13+8]
0x18000f412  mov     [rbp+3B0h+var_25A], r15w
0x18000f41a  cmp     [r13+4Ch], r15d
0x18000f41e  jnz     short loc_18000F452
0x18000f420  mov     r8, [rbx+8]; Source
0x18000f424  test    r8, r8
0x18000f427  jz      short loc_18000F452
0x18000f429  cmp     [rbx], r15
0x18000f42c  jnz     short loc_18000F452
0x18000f42e  lea     r9d, [rdi-1]; MaxCount
0x18000f432  mov     edx, edi; SizeInWords
0x18000f434  lea     rcx, [rsp+4B0h+Destination]; Destination
0x18000f439  call    cs:__imp_wcsncpy_s
0x18000f440  nop     dword ptr [rax+rax+00h]
0x18000f445  mov     [rsp+4B0h+cbData], 2
0x18000f44d  jmp     loc_18000F5D2
0x18000f452  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000f456  mov     rax, rdi
0x18000f459  inc     rax
0x18000f45c  cmp     [rsi+rax*2], r15w
0x18000f461  jnz     short loc_18000F459
0x18000f463  lea     r14d, [rax+8]
0x18000f467  mov     ecx, 40h ; '@'; uFlags
0x18000f46c  lea     r12, [r14+r14]
0x18000f470  mov     r15d, r14d
0x18000f473  mov     rdx, r12; dwBytes
0x18000f476  call    cs:__imp_GlobalAlloc
0x18000f47d  nop     dword ptr [rax+rax+00h]
0x18000f482  mov     rsi, rax
0x18000f485  test    rax, rax
0x18000f488  jz      loc_18000F618
0x18000f48e  mov     r8, r12; Size
0x18000f491  xor     edx, edx; Val
0x18000f493  mov     rcx, rax; void *
0x18000f496  call    memset_0
0x18000f49b  lea     rax, aAuth; "\\Auth"
0x18000f4a2  mov     edx, r15d; BufferCount
0x18000f4a5  mov     [rsp+4B0h+lpcbData], rax
0x18000f4aa  lea     r8d, [r14-1]; MaxCount
0x18000f4ae  mov     rax, [rsp+4B0h+var_470]
0x18000f4b3  lea     r9, aSS_0; "%s%s"
0x18000f4ba  mov     rcx, rsi; Buffer
0x18000f4bd  mov     [rsp+4B0h+phkResult], rax
0x18000f4c2  call    cs:__imp__snwprintf_s
0x18000f4c9  nop     dword ptr [rax+rax+00h]
0x18000f4ce  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000f4d3  lea     rax, [rsp+4B0h+var_478]
0x18000f4d8  mov     r9d, 0F003Fh; samDesired
0x18000f4de  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18000f4e3  xor     r8d, r8d; ulOptions
0x18000f4e6  mov     rdx, rsi; lpSubKey
0x18000f4e9  call    cs:__imp_RegOpenKeyExW
0x18000f4f0  nop     dword ptr [rax+rax+00h]
0x18000f4f5  xor     r15d, r15d
0x18000f4f8  mov     r14d, eax
0x18000f4fb  test    eax, eax
0x18000f4fd  jnz     loc_18000F5B2
0x18000f503  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000f508  lea     rax, [rsp+4B0h+cbData]
0x18000f50d  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x18000f512  lea     r12, aPassword; "Password"
0x18000f519  lea     rax, [rsp+4B0h+Destination]
0x18000f51e  mov     [rsp+4B0h+cbData], 208h
0x18000f526  lea     r9, [rsp+4B0h+Type]; lpType
0x18000f52b  mov     [rsp+4B0h+phkResult], rax; lpData
0x18000f530  xor     r8d, r8d; lpReserved
0x18000f533  mov     rdx, r12; lpValueName
0x18000f536  call    cs:__imp_RegQueryValueExW
0x18000f53d  nop     dword ptr [rax+rax+00h]
0x18000f542  mov     r14d, eax
0x18000f545  test    eax, eax
0x18000f547  jnz     short loc_18000F5A1
0x18000f549  cmp     [rsp+4B0h+Type], 1
0x18000f54e  jnz     short loc_18000F5A1
0x18000f550  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000f555  mov     rdx, r12; lpValueName
0x18000f558  call    cs:__imp_RegDeleteValueW
0x18000f55f  nop     dword ptr [rax+rax+00h]
0x18000f564  lea     rax, [rsp+4B0h+Destination]
0x18000f569  inc     rdi
0x18000f56c  cmp     [rax+rdi*2], r15w
0x18000f571  jnz     short loc_18000F569
0x18000f573  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000f578  lea     eax, [rdi+1]
0x18000f57b  mov     dword ptr [rsp+4B0h+lpcbData], eax; ppOutData
0x18000f57f  mov     r9d, 3; dwType
0x18000f585  lea     rax, [rsp+4B0h+Destination]
0x18000f58a  xor     r8d, r8d; Reserved
0x18000f58d  mov     rdx, r12; lpValueName
0x18000f590  mov     [rsp+4B0h+phkResult], rax; pcbOutData
0x18000f595  call    cs:__imp_RegSetValueExW
0x18000f59c  nop     dword ptr [rax+rax+00h]
0x18000f5a1  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000f5a6  call    cs:__imp_RegCloseKey
0x18000f5ad  nop     dword ptr [rax+rax+00h]
0x18000f5b2  mov     rcx, rsi; hMem
0x18000f5b5  call    cs:__imp_GlobalFree
0x18000f5bc  nop     dword ptr [rax+rax+00h]
0x18000f5c1  test    r14d, r14d
0x18000f5c4  jnz     short loc_18000F618
0x18000f5c6  cmp     [rsp+4B0h+cbData], 1
0x18000f5cb  jbe     short loc_18000F618
0x18000f5cd  mov     edi, 104h
0x18000f5d2  cmp     [r13+4Ch], r15d
0x18000f5d6  jnz     short loc_18000F5EA
0x18000f5d8  cmp     [rbx+8], r15
0x18000f5dc  jz      short loc_18000F5EA
0x18000f5de  cmp     [rbx], r15
0x18000f5e1  jnz     short loc_18000F5EA
0x18000f5e3  lea     r8, [rsp+4B0h+Destination]
0x18000f5e8  jmp     short loc_18000F602
0x18000f5ea  lea     rdx, [rbp+3B0h+fOAEP]; fOAEP
0x18000f5f1  lea     rcx, [rsp+4B0h+Destination]; hCrypto
0x18000f5f6  call    Decrypt
0x18000f5fb  lea     r8, [rbp+3B0h+fOAEP]; Source
0x18000f602  mov     rdx, rdi; SizeInWords
0x18000f605  lea     rcx, [rbx+218h]; Destination
0x18000f60c  call    cs:__imp_wcscpy_s
0x18000f613  nop     dword ptr [rax+rax+00h]
0x18000f618  mov     rcx, [rbp+3B0h+var_40]
0x18000f61f  xor     rcx, rsp; StackCookie
0x18000f622  call    __security_check_cookie
0x18000f627  mov     rbx, [rsp+4B0h+arg_18]
0x18000f62f  add     rsp, 480h
0x18000f636  pop     r15
0x18000f638  pop     r14
0x18000f63a  pop     r13
0x18000f63c  pop     r12
0x18000f63e  pop     rdi
0x18000f63f  pop     rsi
0x18000f640  pop     rbp
0x18000f641  retn
```
