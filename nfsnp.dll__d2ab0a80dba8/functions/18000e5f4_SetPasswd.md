# SetPasswd

- ea: `0x18000e5f4`
- end: `0x18000e876`
- name: `SetPasswd`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d9b0`

## callees

- `0x18000d6e4`
- `0x18000e5f4`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!_snwprintf_s` at `0x18000e726`
- `msvcrt!_snwprintf_s` at `0x18000e726`
- `msvcrt!wcscpy_s` at `0x18000e846`
- `msvcrt!wcscpy_s` at `0x18000e846`
- `msvcrt!wcsncpy_s` at `0x18000e6a9`
- `msvcrt!wcsncpy_s` at `0x18000e6a9`
- `KERNEL32!GlobalFree` at `0x18000e7f5`
- `KERNEL32!GlobalFree` at `0x18000e7f5`
- `KERNEL32!GlobalAlloc` at `0x18000e6e0`
- `KERNEL32!GlobalAlloc` at `0x18000e6e0`
- `ADVAPI32!RegSetValueExW` at `0x18000e7e1`
- `ADVAPI32!RegSetValueExW` at `0x18000e7e1`
- `ADVAPI32!RegDeleteValueW` at `0x18000e7aa`
- `ADVAPI32!RegDeleteValueW` at `0x18000e7aa`
- `ADVAPI32!RegCloseKey` at `0x18000e7ec`
- `ADVAPI32!RegCloseKey` at `0x18000e7ec`
- `ADVAPI32!RegQueryValueExW` at `0x18000e78e`
- `ADVAPI32!RegQueryValueExW` at `0x18000e78e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e747`
- `ADVAPI32!RegOpenKeyExW` at `0x18000e747`

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
0x18000e5f4  mov     [rsp-8+arg_18], rbx
0x18000e5f9  push    rbp
0x18000e5fa  push    rsi
0x18000e5fb  push    rdi
0x18000e5fc  push    r12
0x18000e5fe  push    r13
0x18000e600  push    r14
0x18000e602  push    r15
0x18000e604  lea     rbp, [rsp-380h]
0x18000e60c  sub     rsp, 480h
0x18000e613  mov     rax, cs:__security_cookie
0x18000e61a  xor     rax, rsp
0x18000e61d  mov     [rbp+3B0h+var_40], rax
0x18000e624  mov     r13, r8
0x18000e627  mov     [rsp+4B0h+var_470], rdx
0x18000e62c  mov     rsi, rdx
0x18000e62f  mov     [rsp+4B0h+hKey], rcx
0x18000e634  xor     r15d, r15d
0x18000e637  lea     rcx, [rsp+4B0h+var_45E]; void *
0x18000e63c  mov     ebx, 206h
0x18000e641  mov     [rsp+4B0h+var_478], r15
0x18000e646  mov     r8d, ebx; Size
0x18000e649  mov     [rsp+4B0h+Destination], r15w
0x18000e64f  xor     edx, edx; Val
0x18000e651  call    memset_0
0x18000e656  mov     r8d, ebx; Size
0x18000e659  mov     [rsp+4B0h+cbData], r15d
0x18000e65e  xor     edx, edx; Val
0x18000e660  mov     [rsp+4B0h+Type], r15d
0x18000e665  lea     rcx, [rbp+3B0h+fOAEP+2]; void *
0x18000e66c  mov     word ptr [rbp+3B0h+fOAEP], r15w
0x18000e674  call    memset_0
0x18000e679  mov     edi, 104h
0x18000e67e  mov     rbx, [r13+8]
0x18000e682  mov     [rbp+3B0h+var_25A], r15w
0x18000e68a  cmp     [r13+4Ch], r15d
0x18000e68e  jnz     short loc_18000E6BC
0x18000e690  mov     r8, [rbx+8]; Source
0x18000e694  test    r8, r8
0x18000e697  jz      short loc_18000E6BC
0x18000e699  cmp     [rbx], r15
0x18000e69c  jnz     short loc_18000E6BC
0x18000e69e  lea     r9d, [rdi-1]; MaxCount
0x18000e6a2  mov     edx, edi; SizeInWords
0x18000e6a4  lea     rcx, [rsp+4B0h+Destination]; Destination
0x18000e6a9  call    cs:__imp_wcsncpy_s
0x18000e6af  mov     [rsp+4B0h+cbData], 2
0x18000e6b7  jmp     loc_18000E80C
0x18000e6bc  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000e6c0  mov     rax, rdi
0x18000e6c3  inc     rax
0x18000e6c6  cmp     [rsi+rax*2], r15w
0x18000e6cb  jnz     short loc_18000E6C3
0x18000e6cd  lea     r14d, [rax+8]
0x18000e6d1  mov     ecx, 40h ; '@'; uFlags
0x18000e6d6  lea     r12, [r14+r14]
0x18000e6da  mov     r15d, r14d
0x18000e6dd  mov     rdx, r12; dwBytes
0x18000e6e0  call    cs:__imp_GlobalAlloc
0x18000e6e6  mov     rsi, rax
0x18000e6e9  test    rax, rax
0x18000e6ec  jz      loc_18000E84C
0x18000e6f2  mov     r8, r12; Size
0x18000e6f5  xor     edx, edx; Val
0x18000e6f7  mov     rcx, rax; void *
0x18000e6fa  call    memset_0
0x18000e6ff  lea     rax, aAuth; "\\Auth"
0x18000e706  mov     edx, r15d; BufferCount
0x18000e709  mov     [rsp+4B0h+lpcbData], rax
0x18000e70e  lea     r8d, [r14-1]; MaxCount
0x18000e712  mov     rax, [rsp+4B0h+var_470]
0x18000e717  lea     r9, aSS_0; "%s%s"
0x18000e71e  mov     rcx, rsi; Buffer
0x18000e721  mov     [rsp+4B0h+phkResult], rax
0x18000e726  call    cs:__imp__snwprintf_s
0x18000e72c  mov     rcx, [rsp+4B0h+hKey]; hKey
0x18000e731  lea     rax, [rsp+4B0h+var_478]
0x18000e736  mov     r9d, 0F003Fh; samDesired
0x18000e73c  mov     [rsp+4B0h+phkResult], rax; phkResult
0x18000e741  xor     r8d, r8d; ulOptions
0x18000e744  mov     rdx, rsi; lpSubKey
0x18000e747  call    cs:__imp_RegOpenKeyExW
0x18000e74d  xor     r15d, r15d
0x18000e750  mov     r14d, eax
0x18000e753  test    eax, eax
0x18000e755  jnz     loc_18000E7F2
0x18000e75b  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000e760  lea     rax, [rsp+4B0h+cbData]
0x18000e765  mov     [rsp+4B0h+lpcbData], rax; lpcbData
0x18000e76a  lea     r12, aPassword; "Password"
0x18000e771  lea     rax, [rsp+4B0h+Destination]
0x18000e776  mov     [rsp+4B0h+cbData], 208h
0x18000e77e  lea     r9, [rsp+4B0h+Type]; lpType
0x18000e783  mov     [rsp+4B0h+phkResult], rax; lpData
0x18000e788  xor     r8d, r8d; lpReserved
0x18000e78b  mov     rdx, r12; lpValueName
0x18000e78e  call    cs:__imp_RegQueryValueExW
0x18000e794  mov     r14d, eax
0x18000e797  test    eax, eax
0x18000e799  jnz     short loc_18000E7E7
0x18000e79b  cmp     [rsp+4B0h+Type], 1
0x18000e7a0  jnz     short loc_18000E7E7
0x18000e7a2  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000e7a7  mov     rdx, r12; lpValueName
0x18000e7aa  call    cs:__imp_RegDeleteValueW
0x18000e7b0  lea     rax, [rsp+4B0h+Destination]
0x18000e7b5  inc     rdi
0x18000e7b8  cmp     [rax+rdi*2], r15w
0x18000e7bd  jnz     short loc_18000E7B5
0x18000e7bf  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000e7c4  lea     eax, [rdi+1]
0x18000e7c7  mov     dword ptr [rsp+4B0h+lpcbData], eax; ppOutData
0x18000e7cb  mov     r9d, 3; dwType
0x18000e7d1  lea     rax, [rsp+4B0h+Destination]
0x18000e7d6  xor     r8d, r8d; Reserved
0x18000e7d9  mov     rdx, r12; lpValueName
0x18000e7dc  mov     [rsp+4B0h+phkResult], rax; pcbOutData
0x18000e7e1  call    cs:__imp_RegSetValueExW
0x18000e7e7  mov     rcx, [rsp+4B0h+var_478]; hKey
0x18000e7ec  call    cs:__imp_RegCloseKey
0x18000e7f2  mov     rcx, rsi; hMem
0x18000e7f5  call    cs:__imp_GlobalFree
0x18000e7fb  test    r14d, r14d
0x18000e7fe  jnz     short loc_18000E84C
0x18000e800  cmp     [rsp+4B0h+cbData], 1
0x18000e805  jbe     short loc_18000E84C
0x18000e807  mov     edi, 104h
0x18000e80c  cmp     [r13+4Ch], r15d
0x18000e810  jnz     short loc_18000E824
0x18000e812  cmp     [rbx+8], r15
0x18000e816  jz      short loc_18000E824
0x18000e818  cmp     [rbx], r15
0x18000e81b  jnz     short loc_18000E824
0x18000e81d  lea     r8, [rsp+4B0h+Destination]
0x18000e822  jmp     short loc_18000E83C
0x18000e824  lea     rdx, [rbp+3B0h+fOAEP]; fOAEP
0x18000e82b  lea     rcx, [rsp+4B0h+Destination]; hCrypto
0x18000e830  call    Decrypt
0x18000e835  lea     r8, [rbp+3B0h+fOAEP]; Source
0x18000e83c  mov     rdx, rdi; SizeInWords
0x18000e83f  lea     rcx, [rbx+218h]; Destination
0x18000e846  call    cs:__imp_wcscpy_s
0x18000e84c  mov     rcx, [rbp+3B0h+var_40]
0x18000e853  xor     rcx, rsp; StackCookie
0x18000e856  call    __security_check_cookie
0x18000e85b  mov     rbx, [rsp+4B0h+arg_18]
0x18000e863  add     rsp, 480h
0x18000e86a  pop     r15
0x18000e86c  pop     r14
0x18000e86e  pop     r13
0x18000e870  pop     r12
0x18000e872  pop     rdi
0x18000e873  pop     rsi
0x18000e874  pop     rbp
0x18000e875  retn
```
