# GetAppCompatFlags(void)

- ea: `0x18000c244`
- end: `0x18000c447`
- name: `?GetAppCompatFlags@@YAKXZ`
- size: `515`
- prototype: `unsigned int(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000be40`
- `0x18000beb0`

## callees

- `0x18000c244`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c292`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000c292`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c3f0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000c3f0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c3a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c3a7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c40c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c40c`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000c2ba`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18000c2ba`

## string_xrefs

- `0x18000c2d4`: `SOFTWARE\Microsoft\CTF\Compatibility\`
- `0x18000c3da`: `Compatibility`

## pseudocode

```c
__int64 GetAppCompatFlags(void)
{
  LPWSTR v0; // r9
  __int64 v1; // r10
  const unsigned __int16 *v2; // r8
  __int64 v3; // rcx
  WCHAR *v4; // rax
  __int64 v5; // rdx
  bool v6; // zf
  WCHAR *v7; // rcx
  __int64 v8; // rdx
  WCHAR *v9; // rax
  __int64 v10; // r8
  WCHAR *v11; // rax
  __int64 v12; // rbx
  WCHAR *v13; // rcx
  HKEY v14; // rdi
  unsigned int v15; // ebx
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR FilePart; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR Buffer[264]; // [rsp+470h] [rbp+370h] BYREF

  if ( dword_180141190 )
    return (unsigned int)dword_180141194;
  dword_180141190 = 1;
  if ( !GetModuleFileNameW(0, Filename, 0x104u) )
    return (unsigned int)dword_180141194;
  FilePart = 0;
  GetFullPathNameW(Filename, 0x104u, Buffer, &FilePart);
  v0 = FilePart;
  if ( !FilePart )
    return (unsigned int)dword_180141194;
  v1 = 2147483646;
  v2 = L"SOFTWARE\\Microsoft\\CTF\\Compatibility\\";
  v3 = 2147483646;
  v4 = SubKey;
  v5 = 260;
  do
  {
    if ( !v3 )
      break;
    if ( !*v2 )
      break;
    *v4++ = *v2++;
    --v3;
    --v5;
  }
  while ( v5 );
  v6 = v5 == 0;
  v7 = v4 - 1;
  v8 = 260;
  if ( !v6 )
    v7 = v4;
  v9 = SubKey;
  *v7 = 0;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v8;
  }
  while ( v8 );
  v10 = (260 - v8) & -(__int64)(v8 != 0);
  if ( v8 )
  {
    v11 = &SubKey[v10];
    v12 = 260 - v10;
    if ( 260 != v10 )
    {
      do
      {
        if ( !v1 )
          break;
        if ( !*v0 )
          break;
        *v11++ = *v0++;
        --v1;
        --v12;
      }
      while ( v12 );
    }
    v13 = v11 - 1;
    if ( v12 )
      v13 = v11;
    *v13 = 0;
  }
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
    return (unsigned int)dword_180141194;
  }
  else
  {
    v14 = hKey;
    *(_DWORD *)Data = 0;
    Type = 0;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"Compatibility", 0, &Type, Data, &cbData) )
    {
      v15 = dword_180141194;
    }
    else
    {
      v15 = *(_DWORD *)Data;
      dword_180141194 = *(_DWORD *)Data;
    }
    if ( v14 )
      RegCloseKey(v14);
  }
  return v15;
}

```

## disassembly

```asm
0x18000c244  push    rbp
0x18000c246  push    rbx
0x18000c247  push    rsi
0x18000c248  push    rdi
0x18000c249  lea     rbp, [rsp-598h]
0x18000c251  sub     rsp, 698h
0x18000c258  mov     rax, cs:__security_cookie
0x18000c25f  xor     rax, rsp
0x18000c262  mov     [rbp+5B0h+var_30], rax
0x18000c269  xor     esi, esi
0x18000c26b  cmp     cs:dword_180141190, esi
0x18000c271  jnz     loc_18000C42F
0x18000c277  mov     ebx, 104h
0x18000c27c  mov     cs:dword_180141190, 1
0x18000c286  mov     r8d, ebx; nSize
0x18000c289  lea     rdx, [rbp+5B0h+Filename]; lpFilename
0x18000c290  xor     ecx, ecx; hModule
0x18000c292  call    cs:__imp_GetModuleFileNameW
0x18000c298  test    eax, eax
0x18000c29a  jz      loc_18000C42F
0x18000c2a0  lea     r9, [rsp+6B0h+FilePart]; lpFilePart
0x18000c2a5  mov     [rsp+6B0h+FilePart], rsi
0x18000c2aa  lea     r8, [rbp+5B0h+Buffer]; lpBuffer
0x18000c2b1  mov     edx, ebx; nBufferLength
0x18000c2b3  lea     rcx, [rbp+5B0h+Filename]; lpFileName
0x18000c2ba  call    cs:__imp_GetFullPathNameW
0x18000c2c0  mov     r9, [rsp+6B0h+FilePart]
0x18000c2c5  test    r9, r9
0x18000c2c8  jz      loc_18000C42F
0x18000c2ce  mov     r10d, 7FFFFFFEh
0x18000c2d4  lea     r8, ?c_szAppCompat@@3QBGB; "SOFTWARE\\Microsoft\\CTF\\Compatibility"...
0x18000c2db  mov     ecx, r10d
0x18000c2de  lea     rax, [rsp+6B0h+SubKey]
0x18000c2e3  mov     edx, ebx
0x18000c2e5  test    rcx, rcx
0x18000c2e8  jz      short loc_18000C309
0x18000c2ea  movzx   r11d, word ptr [r8]
0x18000c2ee  test    r11w, r11w
0x18000c2f2  jz      short loc_18000C309
0x18000c2f4  mov     [rax], r11w
0x18000c2f8  add     r8, 2
0x18000c2fc  add     rax, 2
0x18000c300  dec     rcx
0x18000c303  sub     rdx, 1
0x18000c307  jnz     short loc_18000C2E5
0x18000c309  test    rdx, rdx
0x18000c30c  lea     rcx, [rax-2]
0x18000c310  mov     rdx, rbx
0x18000c313  cmovnz  rcx, rax
0x18000c317  lea     rax, [rsp+6B0h+SubKey]
0x18000c31c  mov     [rcx], si
0x18000c31f  cmp     [rax], si
0x18000c322  jz      short loc_18000C32E
0x18000c324  add     rax, 2
0x18000c328  sub     rdx, 1
0x18000c32c  jnz     short loc_18000C31F
0x18000c32e  mov     rcx, rbx
0x18000c331  mov     rax, rdx
0x18000c334  sub     rcx, rdx
0x18000c337  neg     rax
0x18000c33a  sbb     r8, r8
0x18000c33d  and     r8, rcx
0x18000c340  test    rdx, rdx
0x18000c343  jz      short loc_18000C383
0x18000c345  lea     rax, [rsp+6B0h+SubKey]
0x18000c34a  lea     rax, [rax+r8*2]
0x18000c34e  sub     rbx, r8
0x18000c351  jz      short loc_18000C375
0x18000c353  test    r10, r10
0x18000c356  jz      short loc_18000C375
0x18000c358  movzx   ecx, word ptr [r9]
0x18000c35c  test    cx, cx
0x18000c35f  jz      short loc_18000C375
0x18000c361  mov     [rax], cx
0x18000c364  add     r9, 2
0x18000c368  add     rax, 2
0x18000c36c  dec     r10
0x18000c36f  sub     rbx, 1
0x18000c373  jnz     short loc_18000C353
0x18000c375  test    rbx, rbx
0x18000c378  lea     rcx, [rax-2]
0x18000c37c  cmovnz  rcx, rax
0x18000c380  mov     [rcx], si
0x18000c383  lea     rax, [rsp+6B0h+hKey]
0x18000c388  mov     [rsp+6B0h+hKey], rsi
0x18000c38d  mov     r9d, 20019h; samDesired
0x18000c393  mov     [rsp+6B0h+phkResult], rax; phkResult
0x18000c398  xor     r8d, r8d; ulOptions
0x18000c39b  lea     rdx, [rsp+6B0h+SubKey]; lpSubKey
0x18000c3a0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c3a7  call    cs:__imp_RegOpenKeyExW
0x18000c3ad  test    eax, eax
0x18000c3af  jnz     loc_18000C437
0x18000c3b5  mov     rdi, [rsp+6B0h+hKey]
0x18000c3ba  lea     rax, [rsp+6B0h+cbData]
0x18000c3bf  mov     [rsp+6B0h+lpcbData], rax; lpcbData
0x18000c3c4  lea     r9, [rsp+6B0h+Type]; lpType
0x18000c3c9  lea     rax, [rsp+6B0h+Data]
0x18000c3ce  mov     dword ptr [rsp+6B0h+Data], esi
0x18000c3d2  xor     r8d, r8d; lpReserved
0x18000c3d5  mov     [rsp+6B0h+phkResult], rax; lpData
0x18000c3da  lea     rdx, ?c_szCompatibility@@3QBGB; "Compatibility"
0x18000c3e1  mov     [rsp+6B0h+Type], esi
0x18000c3e5  mov     rcx, rdi; hKey
0x18000c3e8  mov     [rsp+6B0h+cbData], 4
0x18000c3f0  call    cs:__imp_RegQueryValueExW
0x18000c3f6  test    eax, eax
0x18000c3f8  jnz     short loc_18000C43F
0x18000c3fa  mov     ebx, dword ptr [rsp+6B0h+Data]
0x18000c3fe  mov     cs:dword_180141194, ebx
0x18000c404  test    rdi, rdi
0x18000c407  jz      short loc_18000C412
0x18000c409  mov     rcx, rdi; hKey
0x18000c40c  call    cs:__imp_RegCloseKey
0x18000c412  mov     eax, ebx
0x18000c414  mov     rcx, [rbp+5B0h+var_30]
0x18000c41b  xor     rcx, rsp; StackCookie
0x18000c41e  call    __security_check_cookie
0x18000c423  add     rsp, 698h
0x18000c42a  pop     rdi
0x18000c42b  pop     rsi
0x18000c42c  pop     rbx
0x18000c42d  pop     rbp
0x18000c42e  retn
0x18000c42f  mov     eax, cs:dword_180141194
0x18000c435  jmp     short loc_18000C414
0x18000c437  mov     ebx, cs:dword_180141194
0x18000c43d  jmp     short loc_18000C412
0x18000c43f  mov     ebx, cs:dword_180141194
0x18000c445  jmp     short loc_18000C404
```
