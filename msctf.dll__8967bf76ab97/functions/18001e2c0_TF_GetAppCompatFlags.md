# TF_GetAppCompatFlags

- ea: `0x18001e2c0`
- end: `0x18001e557`
- name: `TF_GetAppCompatFlags`
- size: `663`
- prototype: `__int64(void)`
- caller_count: `17`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013a70`
- `0x180018714`
- `0x18001e640`
- `0x18001e650`
- `0x18001ee40`
- `0x18001f750`
- `0x180024b2c`
- `0x1800381f0`
- `0x18003a5fc`
- `0x18008a980`
- `0x1800a35d4`
- `0x1800aa398`
- `0x1800b5ad8`
- `0x1800e496c`
- `0x1800e57bc`
- `0x1800e5dac`
- `0x1800e6f00`

## callees

- `0x18001e2c0`
- `0x180106a60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e3a4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e3a4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e341`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e341`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e503`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001e503`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e4ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e4ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e523`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e523`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001e3d2`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001e3d2`

## string_xrefs

- `0x18001e3ec`: `SOFTWARE\Microsoft\CTF\Compatibility\`
- `0x18001e4d6`: `Compatibility`

## pseudocode

```c
__int64 TF_GetAppCompatFlags()
{
  unsigned int v0; // esi
  int v1; // ebx
  int v2; // ebx
  __int64 *Value; // rax
  __int64 v4; // rcx
  unsigned int v5; // eax
  __int64 v7; // rbx
  LPWSTR v8; // r9
  __int64 v9; // r8
  const unsigned __int16 *v10; // rdx
  __int64 v11; // rax
  WCHAR *v12; // r10
  __int64 v13; // r11
  WCHAR *v14; // rcx
  WCHAR *v15; // rax
  WCHAR *v16; // rdx
  WCHAR *v17; // rcx
  HKEY v18; // rdi
  BYTE Data[4]; // [rsp+30h] [rbp-668h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-664h] BYREF
  DWORD Type; // [rsp+38h] [rbp-660h] BYREF
  LPWSTR FilePart; // [rsp+40h] [rbp-658h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-650h] BYREF
  WCHAR SubKey[260]; // [rsp+50h] [rbp-648h] BYREF
  WCHAR Filename[264]; // [rsp+260h] [rbp-438h] BYREF
  WCHAR Buffer[264]; // [rsp+470h] [rbp-228h] BYREF

  v0 = g_dwAppCompatibility;
  if ( (NtCurrentPeb()->AppCompatFlags.QuadPart & 0x200000000LL) != 0 )
  {
    v0 = g_dwAppCompatibility | 0x28000;
    g_dwAppCompatibility |= 0x28000u;
  }
  if ( dword_180140C7C )
    goto LABEL_4;
  v7 = 260;
  dword_180140C7C = 1;
  if ( !GetModuleFileNameW(0, Filename, 0x104u) )
    goto LABEL_4;
  FilePart = 0;
  GetFullPathNameW(Filename, 0x104u, Buffer, &FilePart);
  v8 = FilePart;
  if ( !FilePart )
    goto LABEL_4;
  v9 = 2147483646;
  v10 = L"SOFTWARE\\Microsoft\\CTF\\Compatibility\\";
  v11 = 2147483646;
  v12 = SubKey;
  v13 = 260;
  do
  {
    if ( !v11 )
      break;
    if ( !*v10 )
      break;
    *v12++ = *v10++;
    --v11;
    --v13;
  }
  while ( v13 );
  v14 = v12 - 1;
  if ( v13 )
    v14 = v12;
  *v14 = 0;
  v15 = SubKey;
  while ( *v15 )
  {
    ++v15;
    if ( !--v7 )
      goto LABEL_30;
  }
  v16 = Filename - v7 + 3;
  do
  {
    if ( !v9 )
      break;
    if ( !*v8 )
      break;
    *v16++ = *v8++;
    --v9;
    --v7;
  }
  while ( v7 );
  v17 = v16 - 1;
  if ( v7 )
    v17 = v16;
  *v17 = 0;
LABEL_30:
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
LABEL_4:
    v1 = dword_180140C78;
  }
  else
  {
    v18 = hKey;
    *(_DWORD *)Data = 0;
    Type = 0;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"Compatibility", 0, &Type, Data, &cbData) )
    {
      v1 = dword_180140C78;
    }
    else
    {
      v1 = *(_DWORD *)Data;
      dword_180140C78 = *(_DWORD *)Data;
    }
    if ( v18 )
      RegCloseKey(v18);
  }
  v2 = v0 | v1;
  if ( g_dwTLSIndex == -1 || (Value = (__int64 *)TlsGetValue(g_dwTLSIndex)) == 0 )
  {
    v5 = 0;
  }
  else
  {
    v4 = *Value;
    v5 = 0;
    if ( v4 )
    {
      v5 = *(_DWORD *)(v4 + 3112);
      if ( *(_BYTE *)(v4 + 3072) )
        v5 |= 0x8000u;
    }
  }
  return v2 | v5;
}

```

## disassembly

```asm
0x18001e2c0  push    rbx
0x18001e2c2  sub     rsp, 690h
0x18001e2c9  mov     rax, cs:__security_cookie
0x18001e2d0  xor     rax, rsp
0x18001e2d3  mov     [rsp+698h+var_18], rax
0x18001e2db  mov     rax, gs:60h
0x18001e2e4  mov     rcx, 200000000h
0x18001e2ee  mov     [rsp+698h+arg_0], rsi
0x18001e2f6  mov     esi, cs:?g_dwAppCompatibility@@3KA; ulong g_dwAppCompatibility
0x18001e2fc  test    [rax+2C8h], rcx
0x18001e303  jnz     loc_18001E52E
0x18001e309  cmp     cs:dword_180140C7C, 0
0x18001e310  mov     [rsp+698h+arg_8], rdi
0x18001e318  jz      short loc_18001E388
0x18001e31a  mov     ebx, cs:dword_180140C78
0x18001e320  mov     ecx, cs:?g_dwTLSIndex@@3KA; dwTlsIndex
0x18001e326  or      ebx, esi
0x18001e328  mov     rdi, [rsp+698h+arg_8]
0x18001e330  mov     rsi, [rsp+698h+arg_0]
0x18001e338  cmp     ecx, 0FFFFFFFFh
0x18001e33b  jz      loc_18001E550
0x18001e341  call    cs:__imp_TlsGetValue
0x18001e347  test    rax, rax
0x18001e34a  jz      loc_18001E550
0x18001e350  mov     rcx, [rax]
0x18001e353  xor     eax, eax
0x18001e355  test    rcx, rcx
0x18001e358  jz      short loc_18001E36D
0x18001e35a  cmp     byte ptr [rcx+0C00h], 0
0x18001e361  mov     eax, [rcx+0C28h]
0x18001e367  jnz     loc_18001E547
0x18001e36d  or      eax, ebx
0x18001e36f  mov     rcx, [rsp+698h+var_18]
0x18001e377  xor     rcx, rsp; StackCookie
0x18001e37a  call    __security_check_cookie
0x18001e37f  add     rsp, 690h
0x18001e386  pop     rbx
0x18001e387  retn
0x18001e388  mov     ebx, 104h
0x18001e38d  mov     cs:dword_180140C7C, 1
0x18001e397  mov     r8d, ebx; nSize
0x18001e39a  lea     rdx, [rsp+698h+Filename]; lpFilename
0x18001e3a2  xor     ecx, ecx; hModule
0x18001e3a4  call    cs:__imp_GetModuleFileNameW
0x18001e3aa  test    eax, eax
0x18001e3ac  jz      loc_18001E31A
0x18001e3b2  lea     r9, [rsp+698h+FilePart]; lpFilePart
0x18001e3b7  mov     [rsp+698h+FilePart], 0
0x18001e3c0  lea     r8, [rsp+698h+Buffer]; lpBuffer
0x18001e3c8  mov     edx, ebx; nBufferLength
0x18001e3ca  lea     rcx, [rsp+698h+Filename]; lpFileName
0x18001e3d2  call    cs:__imp_GetFullPathNameW
0x18001e3d8  mov     r9, [rsp+698h+FilePart]
0x18001e3dd  test    r9, r9
0x18001e3e0  jz      loc_18001E31A
0x18001e3e6  mov     r8d, 7FFFFFFEh
0x18001e3ec  lea     rdx, ?c_szAppCompat@@3QBGB; "SOFTWARE\\Microsoft\\CTF\\Compatibility"...
0x18001e3f3  mov     eax, r8d
0x18001e3f6  lea     r10, [rsp+698h+SubKey]
0x18001e3fb  mov     r11d, ebx
0x18001e3fe  xchg    ax, ax
0x18001e400  test    rax, rax
0x18001e403  jz      short loc_18001E422
0x18001e405  movzx   ecx, word ptr [rdx]
0x18001e408  test    cx, cx
0x18001e40b  jz      short loc_18001E422
0x18001e40d  mov     [r10], cx
0x18001e411  add     rdx, 2
0x18001e415  add     r10, 2
0x18001e419  dec     rax
0x18001e41c  sub     r11, 1
0x18001e420  jnz     short loc_18001E400
0x18001e422  test    r11, r11
0x18001e425  lea     rcx, [r10-2]
0x18001e429  cmovnz  rcx, r10
0x18001e42d  xor     eax, eax
0x18001e42f  mov     [rcx], ax
0x18001e432  lea     rax, [rsp+698h+SubKey]
0x18001e437  cmp     word ptr [rax], 0
0x18001e43b  jz      short loc_18001E449
0x18001e43d  add     rax, 2
0x18001e441  sub     rbx, 1
0x18001e445  jnz     short loc_18001E437
0x18001e447  jmp     short loc_18001E492
0x18001e449  lea     rax, [rbx+rbx]
0x18001e44d  lea     rdx, [rsp+698h+var_440]
0x18001e455  sub     rdx, rax
0x18001e458  test    rbx, rbx
0x18001e45b  jz      short loc_18001E482
0x18001e45d  nop     dword ptr [rax]
0x18001e460  test    r8, r8
0x18001e463  jz      short loc_18001E482
0x18001e465  movzx   eax, word ptr [r9]
0x18001e469  test    ax, ax
0x18001e46c  jz      short loc_18001E482
0x18001e46e  mov     [rdx], ax
0x18001e471  add     r9, 2
0x18001e475  add     rdx, 2
0x18001e479  dec     r8
0x18001e47c  sub     rbx, 1
0x18001e480  jnz     short loc_18001E460
0x18001e482  test    rbx, rbx
0x18001e485  lea     rcx, [rdx-2]
0x18001e489  cmovnz  rcx, rdx
0x18001e48d  xor     eax, eax
0x18001e48f  mov     [rcx], ax
0x18001e492  lea     rax, [rsp+698h+hKey]
0x18001e497  mov     [rsp+698h+hKey], 0
0x18001e4a0  mov     r9d, 20019h; samDesired
0x18001e4a6  mov     [rsp+698h+phkResult], rax; phkResult
0x18001e4ab  xor     r8d, r8d; ulOptions
0x18001e4ae  lea     rdx, [rsp+698h+SubKey]; lpSubKey
0x18001e4b3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e4ba  call    cs:__imp_RegOpenKeyExW
0x18001e4c0  test    eax, eax
0x18001e4c2  jnz     loc_18001E31A
0x18001e4c8  mov     rdi, [rsp+698h+hKey]
0x18001e4cd  lea     r9, [rsp+698h+Type]; lpType
0x18001e4d2  mov     dword ptr [rsp+698h+Data], eax
0x18001e4d6  lea     rdx, ?c_szCompatibility@@3QBGB; "Compatibility"
0x18001e4dd  mov     [rsp+698h+Type], eax
0x18001e4e1  xor     r8d, r8d; lpReserved
0x18001e4e4  lea     rax, [rsp+698h+cbData]
0x18001e4e9  mov     [rsp+698h+cbData], 4
0x18001e4f1  mov     [rsp+698h+lpcbData], rax; lpcbData
0x18001e4f6  mov     rcx, rdi; hKey
0x18001e4f9  lea     rax, [rsp+698h+Data]
0x18001e4fe  mov     [rsp+698h+phkResult], rax; lpData
0x18001e503  call    cs:__imp_RegQueryValueExW
0x18001e509  test    eax, eax
0x18001e50b  jnz     short loc_18001E53F
0x18001e50d  mov     ebx, dword ptr [rsp+698h+Data]
0x18001e511  mov     cs:dword_180140C78, ebx
0x18001e517  test    rdi, rdi
0x18001e51a  jz      loc_18001E320
0x18001e520  mov     rcx, rdi; hKey
0x18001e523  call    cs:__imp_RegCloseKey
0x18001e529  jmp     loc_18001E320
0x18001e52e  or      esi, 28000h
0x18001e534  mov     cs:?g_dwAppCompatibility@@3KA, esi; ulong g_dwAppCompatibility
0x18001e53a  jmp     loc_18001E309
0x18001e53f  mov     ebx, cs:dword_180140C78
0x18001e545  jmp     short loc_18001E517
0x18001e547  bts     eax, 0Fh
0x18001e54b  jmp     loc_18001E36D
0x18001e550  xor     eax, eax
0x18001e552  jmp     loc_18001E36D
```
