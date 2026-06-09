# WriteLoginOpts

- ea: `0x18000f7b0`
- end: `0x18000f9e7`
- name: `WriteLoginOpts`
- size: `567`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000be24`
- `0x18000fc20`

## callees

- `0x18000f7b0`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000f834`
- `msvcrt!wcscat_s` at `0x18000f834`
- `msvcrt!wcscpy_s` at `0x18000f81e`
- `msvcrt!wcscpy_s` at `0x18000f88b`
- `msvcrt!wcscpy_s` at `0x18000f81e`
- `msvcrt!wcscpy_s` at `0x18000f88b`
- `ADVAPI32!RegCreateKeyExW` at `0x18000f870`
- `ADVAPI32!RegCreateKeyExW` at `0x18000f870`
- `ADVAPI32!RegSetValueExW` at `0x18000f93c`
- `ADVAPI32!RegSetValueExW` at `0x18000f975`
- `ADVAPI32!RegSetValueExW` at `0x18000f997`
- `ADVAPI32!RegSetValueExW` at `0x18000f9b9`
- `ADVAPI32!RegSetValueExW` at `0x18000f93c`
- `ADVAPI32!RegSetValueExW` at `0x18000f975`
- `ADVAPI32!RegSetValueExW` at `0x18000f997`
- `ADVAPI32!RegSetValueExW` at `0x18000f9b9`
- `ADVAPI32!RegCloseKey` at `0x18000f9c4`
- `ADVAPI32!RegCloseKey` at `0x18000f9c4`

## pseudocode

```c
LSTATUS __fastcall WriteLoginOpts(HKEY hKey, wchar_t *Source, __int64 a3)
{
  LSTATUS result; // eax
  __int64 v7; // rbx
  int v8; // r8d
  int i; // r9d
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  unsigned __int16 v13; // cx
  __int64 v14; // rax
  HKEY hKeya; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[526]; // [rsp+62h] [rbp-9Eh] BYREF
  wchar_t Destination[264]; // [rsp+270h] [rbp+170h] BYREF
  wchar_t v20[264]; // [rsp+480h] [rbp+380h] BYREF

  hKeya = 0;
  dwDisposition = 0;
  *(_WORD *)Data = 0;
  memset_0(v18, 0, 0x206u);
  Destination[259] = 0;
  wcscpy_s(Destination, 0x104u, Source);
  wcscat_s(Destination, 0x104u, L"\\Auth");
  result = RegCreateKeyExW(hKey, Destination, 0, 0, 0, 0xF003Fu, 0, &hKeya, &dwDisposition);
  if ( !result )
  {
    wcscpy_s(v20, 0x104u, (const wchar_t *)(a3 + 16));
    v7 = -1;
    v8 = 259;
    for ( i = 0; ; ++i )
    {
      v10 = -1;
      do
        ++v10;
      while ( v20[v10] );
      v11 = 259;
      if ( (int)v10 < 259 )
        v11 = v10;
      if ( i >= v11 )
        break;
      v12 = i;
      v13 = v20[i] + 128;
      if ( v13 > 0xFFu )
        v13 = v20[i] - 127;
      *(_WORD *)&Data[2 * v12] = v13;
    }
    v14 = -1;
    if ( (int)v10 < 259 )
      v8 = v10;
    *(_WORD *)&Data[2 * v8] = 0;
    do
      ++v14;
    while ( *(_WORD *)&Data[2 * v14] );
    RegSetValueExW(hKeya, L"User", 0, 3u, Data, 2 * v14 + 2);
    do
      ++v7;
    while ( *(_WORD *)(a3 + 1064 + 2 * v7) );
    RegSetValueExW(hKeya, L"PCNFSDServer", 0, 1u, (const BYTE *)(a3 + 1064), 2 * v7 + 2);
    RegSetValueExW(hKeya, L"NISDomain", 0, 1u, 0, 0);
    RegSetValueExW(hKeya, L"NISServer", 0, 1u, 0, 0);
    return RegCloseKey(hKeya);
  }
  return result;
}

```

## disassembly

```asm
0x18000f7b0  push    rbp
0x18000f7b2  push    rbx
0x18000f7b3  push    rsi
0x18000f7b4  push    rdi
0x18000f7b5  push    r14
0x18000f7b7  lea     rbp, [rsp-5A0h]
0x18000f7bf  sub     rsp, 6A0h
0x18000f7c6  mov     rax, cs:__security_cookie
0x18000f7cd  xor     rax, rsp
0x18000f7d0  mov     [rbp+5C0h+var_30], rax
0x18000f7d7  xor     r14d, r14d
0x18000f7da  mov     rsi, r8
0x18000f7dd  mov     rbx, rdx
0x18000f7e0  mov     [rsp+6C0h+hKey], r14
0x18000f7e5  mov     rdi, rcx
0x18000f7e8  mov     [rsp+6C0h+dwDisposition], r14d
0x18000f7ed  xor     edx, edx; Val
0x18000f7ef  mov     word ptr [rsp+6C0h+Data], r14w
0x18000f7f5  mov     r8d, 206h; Size
0x18000f7fb  lea     rcx, [rsp+6C0h+var_65E]; void *
0x18000f800  call    memset_0
0x18000f805  mov     r8, rbx; Source
0x18000f808  mov     [rbp+5C0h+var_24A], r14w
0x18000f810  mov     ebx, 104h
0x18000f815  lea     rcx, [rbp+5C0h+Destination]; Destination
0x18000f81c  mov     edx, ebx; SizeInWords
0x18000f81e  call    cs:__imp_wcscpy_s
0x18000f824  lea     r8, aAuth; "\\Auth"
0x18000f82b  mov     edx, ebx; SizeInWords
0x18000f82d  lea     rcx, [rbp+5C0h+Destination]; Destination
0x18000f834  call    cs:__imp_wcscat_s
0x18000f83a  lea     rax, [rsp+6C0h+dwDisposition]
0x18000f83f  xor     r9d, r9d; lpClass
0x18000f842  mov     [rsp+6C0h+lpdwDisposition], rax; lpdwDisposition
0x18000f847  lea     rdx, [rbp+5C0h+Destination]; lpSubKey
0x18000f84e  lea     rax, [rsp+6C0h+hKey]
0x18000f853  xor     r8d, r8d; Reserved
0x18000f856  mov     [rsp+6C0h+phkResult], rax; phkResult
0x18000f85b  mov     rcx, rdi; hKey
0x18000f85e  mov     [rsp+6C0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000f863  mov     [rsp+6C0h+samDesired], 0F003Fh; samDesired
0x18000f86b  mov     [rsp+6C0h+dwOptions], r14d; dwOptions
0x18000f870  call    cs:__imp_RegCreateKeyExW
0x18000f876  test    eax, eax
0x18000f878  jnz     loc_18000F9CA
0x18000f87e  lea     r8, [rsi+10h]; Source
0x18000f882  mov     edx, ebx; SizeInWords
0x18000f884  lea     rcx, [rbp+5C0h+var_240]; Destination
0x18000f88b  call    cs:__imp_wcscpy_s
0x18000f891  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000f895  mov     r8d, 103h
0x18000f89b  mov     r9d, r14d
0x18000f89e  lea     edi, [rbx+2]
0x18000f8a1  lea     r10d, [r8-4]
0x18000f8a5  lea     rax, [rbp+5C0h+var_240]
0x18000f8ac  mov     rcx, rbx
0x18000f8af  inc     rcx
0x18000f8b2  cmp     [rax+rcx*2], r14w
0x18000f8b7  jnz     short loc_18000F8AF
0x18000f8b9  cmp     ecx, r8d
0x18000f8bc  mov     eax, r8d
0x18000f8bf  cmovl   eax, ecx
0x18000f8c2  cmp     r9d, eax
0x18000f8c5  jge     short loc_18000F8F0
0x18000f8c7  movsxd  rdx, r9d
0x18000f8ca  mov     ecx, 80h
0x18000f8cf  add     cx, [rbp+rdx*2+5C0h+var_240]
0x18000f8d7  movzx   eax, cx
0x18000f8da  sub     ax, r10w
0x18000f8de  cmp     cx, r10w
0x18000f8e2  cmova   cx, ax
0x18000f8e6  add     r9d, edi
0x18000f8e9  mov     word ptr [rsp+rdx*2+6C0h+Data], cx
0x18000f8ee  jmp     short loc_18000F8A5
0x18000f8f0  cmp     ecx, r8d
0x18000f8f3  mov     rax, rbx
0x18000f8f6  cmovl   r8d, ecx
0x18000f8fa  movsxd  rcx, r8d
0x18000f8fd  mov     word ptr [rsp+rcx*2+6C0h+Data], r14w
0x18000f903  lea     rcx, [rsp+6C0h+Data]
0x18000f908  inc     rax
0x18000f90b  cmp     [rcx+rax*2], r14w
0x18000f910  jnz     short loc_18000F908
0x18000f912  mov     rcx, [rsp+6C0h+hKey]; hKey
0x18000f917  lea     eax, ds:2[rax*2]
0x18000f91e  mov     [rsp+6C0h+samDesired], eax; cbData
0x18000f922  lea     rdx, aUser; "User"
0x18000f929  lea     rax, [rsp+6C0h+Data]
0x18000f92e  mov     r9d, 3; dwType
0x18000f934  xor     r8d, r8d; Reserved
0x18000f937  mov     qword ptr [rsp+6C0h+dwOptions], rax; lpData
0x18000f93c  call    cs:__imp_RegSetValueExW
0x18000f942  lea     rcx, [rsi+428h]
0x18000f949  inc     rbx
0x18000f94c  cmp     [rcx+rbx*2], r14w
0x18000f951  jnz     short loc_18000F949
0x18000f953  lea     eax, ds:2[rbx*2]
0x18000f95a  mov     r9d, edi; dwType
0x18000f95d  mov     [rsp+6C0h+samDesired], eax; cbData
0x18000f961  lea     rdx, aPcnfsdserver; "PCNFSDServer"
0x18000f968  mov     qword ptr [rsp+6C0h+dwOptions], rcx; lpData
0x18000f96d  xor     r8d, r8d; Reserved
0x18000f970  mov     rcx, [rsp+6C0h+hKey]; hKey
0x18000f975  call    cs:__imp_RegSetValueExW
0x18000f97b  mov     rcx, [rsp+6C0h+hKey]; hKey
0x18000f980  lea     rdx, aNisdomain; "NISDomain"
0x18000f987  mov     r9d, edi; dwType
0x18000f98a  mov     [rsp+6C0h+samDesired], r14d; cbData
0x18000f98f  xor     r8d, r8d; Reserved
0x18000f992  mov     qword ptr [rsp+6C0h+dwOptions], r14; lpData
0x18000f997  call    cs:__imp_RegSetValueExW
0x18000f99d  mov     rcx, [rsp+6C0h+hKey]; hKey
0x18000f9a2  lea     rdx, aNisserver; "NISServer"
0x18000f9a9  mov     r9d, edi; dwType
0x18000f9ac  mov     [rsp+6C0h+samDesired], r14d; cbData
0x18000f9b1  xor     r8d, r8d; Reserved
0x18000f9b4  mov     qword ptr [rsp+6C0h+dwOptions], r14; lpData
0x18000f9b9  call    cs:__imp_RegSetValueExW
0x18000f9bf  mov     rcx, [rsp+6C0h+hKey]; hKey
0x18000f9c4  call    cs:__imp_RegCloseKey
0x18000f9ca  mov     rcx, [rbp+5C0h+var_30]
0x18000f9d1  xor     rcx, rsp; StackCookie
0x18000f9d4  call    __security_check_cookie
0x18000f9d9  add     rsp, 6A0h
0x18000f9e0  pop     r14
0x18000f9e2  pop     rdi
0x18000f9e3  pop     rsi
0x18000f9e4  pop     rbx
0x18000f9e5  pop     rbp
0x18000f9e6  retn
```
