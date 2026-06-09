# SetVersion3AndLocking2

- ea: `0x18000f278`
- end: `0x18000f467`
- name: `SetVersion3AndLocking2`
- size: `495`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t *Source)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000be24`

## callees

- `0x18000f278`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000f2fd`
- `msvcrt!wcscat_s` at `0x18000f2fd`
- `msvcrt!wcsncpy_s` at `0x18000f2e6`
- `msvcrt!wcsncpy_s` at `0x18000f2e6`
- `ADVAPI32!RegCloseKey` at `0x18000f3c6`
- `ADVAPI32!RegCloseKey` at `0x18000f3c6`
- `ADVAPI32!RegQueryValueExW` at `0x18000f35b`
- `ADVAPI32!RegQueryValueExW` at `0x18000f38b`
- `ADVAPI32!RegQueryValueExW` at `0x18000f3bb`
- `ADVAPI32!RegQueryValueExW` at `0x18000f35b`
- `ADVAPI32!RegQueryValueExW` at `0x18000f38b`
- `ADVAPI32!RegQueryValueExW` at `0x18000f3bb`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f31e`
- `ADVAPI32!RegOpenKeyExW` at `0x18000f31e`

## string_xrefs

- `0x18000f2ec`: `\Mount`
- `0x18000f3a0`: `EUCMount`

## pseudocode

```c
__int64 __fastcall SetVersion3AndLocking2(HKEY hKey, wchar_t *Source, __int64 a3)
{
  int v5; // eax
  unsigned int v6; // eax
  __int64 result; // rax
  int v8; // ecx
  int v9; // edx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  BYTE v12[4]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE v13[4]; // [rsp+3Ch] [rbp-C4h] BYREF
  HKEY hKeya; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t Destination[264]; // [rsp+50h] [rbp-B0h] BYREF

  *(_DWORD *)Data = 1;
  *(_DWORD *)v12 = 1;
  cbData = 0;
  *(_DWORD *)v13 = 0;
  hKeya = 0;
  Destination[259] = 0;
  wcsncpy_s(Destination, 0x104u, Source, 0x103u);
  wcscat_s(Destination, 0x104u, L"\\Mount");
  if ( !RegOpenKeyExW(hKey, Destination, 0, 0x20019u, &hKeya) )
  {
    cbData = 4;
    RegQueryValueExW(hKeya, L"Locking", 0, 0, Data, &cbData);
    cbData = 4;
    RegQueryValueExW(hKeya, L"Version3", 0, 0, v12, &cbData);
    cbData = 4;
    RegQueryValueExW(hKeya, L"EUCMount", 0, 0, v13, &cbData);
    RegCloseKey(hKeya);
  }
  v5 = *(_DWORD *)(a3 + 56);
  if ( *(_DWORD *)Data )
    v6 = v5 | 1;
  else
    v6 = v5 & 0xFFFFFFFE;
  if ( *(_DWORD *)v12 )
    result = v6 | 4;
  else
    result = v6 & 0xFFFFFFFB;
  v8 = *(_DWORD *)v13;
  *(_DWORD *)(a3 + 56) = result;
  if ( !v8 )
  {
    result = (unsigned int)result & 0xFFF01FBF;
    goto LABEL_22;
  }
  v9 = 0x2000;
  if ( v8 == 0x2000 )
    goto LABEL_11;
  if ( v8 == 64 )
  {
    result = (unsigned int)result | 0x40;
    goto LABEL_22;
  }
  v9 = 0x4000;
  if ( v8 == 0x4000
    || (v9 = 0x8000, v8 == 0x8000)
    || (v9 = 0x10000, v8 == 0x10000)
    || (v9 = 0x20000, v8 == 0x20000)
    || (v9 = 0x40000, v8 == 0x40000)
    || (v9 = 0x80000, v8 == 0x80000) )
  {
LABEL_11:
    result = v9 | (unsigned int)result;
LABEL_22:
    *(_DWORD *)(a3 + 56) = result;
  }
  return result;
}

```

## disassembly

```asm
0x18000f278  push    rbp
0x18000f27a  push    rbx
0x18000f27b  push    rdi
0x18000f27c  lea     rbp, [rsp-170h]
0x18000f284  sub     rsp, 270h
0x18000f28b  mov     rax, cs:__security_cookie
0x18000f292  xor     rax, rsp
0x18000f295  mov     [rbp+180h+var_20], rax
0x18000f29c  mov     r9d, 103h; MaxCount
0x18000f2a2  mov     dword ptr [rsp+280h+Data], 1
0x18000f2aa  mov     rdi, r8
0x18000f2ad  mov     dword ptr [rsp+280h+var_248], 1
0x18000f2b5  mov     rbx, rcx
0x18000f2b8  mov     [rsp+280h+cbData], 0
0x18000f2c0  xor     eax, eax
0x18000f2c2  mov     dword ptr [rsp+280h+var_244], 0
0x18000f2ca  mov     r8, rdx; Source
0x18000f2cd  mov     [rsp+280h+hKey], 0
0x18000f2d6  lea     edx, [r9+1]; SizeInWords
0x18000f2da  mov     [rbp+180h+var_2A], ax
0x18000f2e1  lea     rcx, [rsp+280h+Destination]; Destination
0x18000f2e6  call    cs:__imp_wcsncpy_s
0x18000f2ec  lea     r8, aMount; "\\Mount"
0x18000f2f3  mov     edx, 104h; SizeInWords
0x18000f2f8  lea     rcx, [rsp+280h+Destination]; Destination
0x18000f2fd  call    cs:__imp_wcscat_s
0x18000f303  lea     rax, [rsp+280h+hKey]
0x18000f308  mov     r9d, 20019h; samDesired
0x18000f30e  xor     r8d, r8d; ulOptions
0x18000f311  mov     [rsp+280h+phkResult], rax; phkResult
0x18000f316  lea     rdx, [rsp+280h+Destination]; lpSubKey
0x18000f31b  mov     rcx, rbx; hKey
0x18000f31e  call    cs:__imp_RegOpenKeyExW
0x18000f324  mov     ebx, 4
0x18000f329  test    eax, eax
0x18000f32b  jnz     loc_18000F3CC
0x18000f331  mov     rcx, [rsp+280h+hKey]; hKey
0x18000f336  lea     rax, [rsp+280h+cbData]
0x18000f33b  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18000f340  lea     rdx, aLocking; "Locking"
0x18000f347  lea     rax, [rsp+280h+Data]
0x18000f34c  mov     [rsp+280h+cbData], ebx
0x18000f350  xor     r9d, r9d; lpType
0x18000f353  mov     [rsp+280h+phkResult], rax; lpData
0x18000f358  xor     r8d, r8d; lpReserved
0x18000f35b  call    cs:__imp_RegQueryValueExW
0x18000f361  mov     rcx, [rsp+280h+hKey]; hKey
0x18000f366  lea     rax, [rsp+280h+cbData]
0x18000f36b  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18000f370  lea     rdx, aVersion3; "Version3"
0x18000f377  lea     rax, [rsp+280h+var_248]
0x18000f37c  mov     [rsp+280h+cbData], ebx
0x18000f380  xor     r9d, r9d; lpType
0x18000f383  mov     [rsp+280h+phkResult], rax; lpData
0x18000f388  xor     r8d, r8d; lpReserved
0x18000f38b  call    cs:__imp_RegQueryValueExW
0x18000f391  mov     rcx, [rsp+280h+hKey]; hKey
0x18000f396  lea     rax, [rsp+280h+cbData]
0x18000f39b  mov     [rsp+280h+lpcbData], rax; lpcbData
0x18000f3a0  lea     rdx, aEucmount; "EUCMount"
0x18000f3a7  lea     rax, [rsp+280h+var_244]
0x18000f3ac  mov     [rsp+280h+cbData], ebx
0x18000f3b0  xor     r9d, r9d; lpType
0x18000f3b3  mov     [rsp+280h+phkResult], rax; lpData
0x18000f3b8  xor     r8d, r8d; lpReserved
0x18000f3bb  call    cs:__imp_RegQueryValueExW
0x18000f3c1  mov     rcx, [rsp+280h+hKey]; hKey
0x18000f3c6  call    cs:__imp_RegCloseKey
0x18000f3cc  cmp     dword ptr [rsp+280h+Data], 0
0x18000f3d1  mov     eax, [rdi+38h]
0x18000f3d4  jz      short loc_18000F3DB
0x18000f3d6  or      eax, 1
0x18000f3d9  jmp     short loc_18000F3DE
0x18000f3db  and     eax, 0FFFFFFFEh
0x18000f3de  cmp     dword ptr [rsp+280h+var_248], 0
0x18000f3e3  jz      short loc_18000F3E9
0x18000f3e5  or      eax, ebx
0x18000f3e7  jmp     short loc_18000F3EC
0x18000f3e9  and     eax, 0FFFFFFFBh
0x18000f3ec  mov     ecx, dword ptr [rsp+280h+var_244]
0x18000f3f0  mov     [rdi+38h], eax
0x18000f3f3  test    ecx, ecx
0x18000f3f5  jz      short loc_18000F445
0x18000f3f7  mov     edx, 2000h
0x18000f3fc  cmp     ecx, edx
0x18000f3fe  jnz     short loc_18000F404
0x18000f400  or      eax, edx
0x18000f402  jmp     short loc_18000F44A
0x18000f404  cmp     ecx, 40h ; '@'
0x18000f407  jnz     short loc_18000F40D
0x18000f409  or      eax, ecx
0x18000f40b  jmp     short loc_18000F44A
0x18000f40d  mov     edx, 4000h
0x18000f412  cmp     ecx, edx
0x18000f414  jz      short loc_18000F400
0x18000f416  mov     edx, 8000h
0x18000f41b  cmp     ecx, edx
0x18000f41d  jz      short loc_18000F400
0x18000f41f  mov     edx, 10000h
0x18000f424  cmp     ecx, edx
0x18000f426  jz      short loc_18000F400
0x18000f428  mov     edx, 20000h
0x18000f42d  cmp     ecx, edx
0x18000f42f  jz      short loc_18000F400
0x18000f431  mov     edx, 40000h
0x18000f436  cmp     ecx, edx
0x18000f438  jz      short loc_18000F400
0x18000f43a  mov     edx, 80000h
0x18000f43f  cmp     ecx, edx
0x18000f441  jnz     short loc_18000F44D
0x18000f443  jmp     short loc_18000F400
0x18000f445  and     eax, 0FFF01FBFh
0x18000f44a  mov     [rdi+38h], eax
0x18000f44d  mov     rcx, [rbp+180h+var_20]
0x18000f454  xor     rcx, rsp; StackCookie
0x18000f457  call    __security_check_cookie
0x18000f45c  add     rsp, 270h
0x18000f463  pop     rdi
0x18000f464  pop     rbx
0x18000f465  pop     rbp
0x18000f466  retn
```
