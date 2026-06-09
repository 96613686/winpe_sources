# GetVdcFilePathRank

- ea: `0x18002323c`
- end: `0x18002341f`
- name: `GetVdcFilePathRank`
- size: `483`
- prototype: `__int64 __fastcall(wchar_t *String1, int *, __int64, wchar_t *, _DWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180025100`

## callees

- `0x180008f24`
- `0x180008fd4`
- `0x180022f8c`
- `0x180022fe8`
- `0x18002323c`
- `0x18002c01e`
- `0x18002c050`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800232ff`
- `msvcrt!_wcsicmp` at `0x180023367`
- `msvcrt!_wcsicmp` at `0x1800233cb`
- `msvcrt!_wcsicmp` at `0x1800232ff`
- `msvcrt!_wcsicmp` at `0x180023367`
- `msvcrt!_wcsicmp` at `0x1800233cb`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800233ba`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800233ba`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x180023383`
- `api-ms-win-core-file-l1-1-0!GetLogicalDriveStringsW` at `0x180023383`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002338d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002338d`

## pseudocode

```c
__int64 __fastcall GetVdcFilePathRank(wchar_t *String1, int *a2, __int64 a3, wchar_t *a4, _DWORD *a5)
{
  int v8; // edi
  unsigned int DitFolder; // ebx
  HRESULT v10; // eax
  int v11; // edi
  wchar_t *i; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  wchar_t pszDest[264]; // [rsp+20h] [rbp-E0h] BYREF

  memset_0(pszDest, 0, 0x20Au);
  *a5 = -1;
  *a2 = -1;
  v8 = 0;
  *a4 = 0;
  DitFolder = GetDitFolder((LPBYTE)pszDest);
  if ( !DitFolder )
  {
    v10 = StringCchCatW(pszDest, 0x105u, L"\\");
    if ( v10 < 0 )
      return (unsigned __int16)v10;
    v10 = StringCchCopyW(a4, 0x105u, pszDest);
    if ( v10 < 0 )
      return (unsigned __int16)v10;
    *a5 = 1;
    v8 = 1;
    if ( !_wcsicmp(String1, pszDest) )
    {
      *a2 = 1;
      return DitFolder;
    }
  }
  DitFolder = GetNtdsFolder(pszDest);
  if ( !DitFolder )
  {
    v10 = StringCchCatW(pszDest, 0x105u, L"\\");
    if ( v10 >= 0 )
    {
      if ( v8 )
        goto LABEL_12;
      v10 = StringCchCopyW(a4, 0x105u, pszDest);
      if ( v10 >= 0 )
      {
        *a5 = 2;
LABEL_12:
        if ( !_wcsicmp(String1, pszDest) )
        {
          *a2 = 2;
          return DitFolder;
        }
        goto LABEL_14;
      }
    }
    return (unsigned __int16)v10;
  }
LABEL_14:
  if ( GetLogicalDriveStringsW(0x105u, pszDest) )
  {
    v11 = 3;
    for ( i = pszDest; ; i += v14 + 1 )
    {
      v13 = -1;
      do
        ++v13;
      while ( i[v13] );
      if ( !v13 )
        break;
      if ( GetDriveTypeW(i) == 2 )
      {
        if ( !_wcsicmp(String1, i) )
        {
          *a2 = v11;
          return 0;
        }
        ++v11;
      }
      v14 = -1;
      do
        ++v14;
      while ( i[v14] );
    }
    return 0;
  }
  else
  {
    return GetLastError();
  }
}

```

## disassembly

```asm
0x18002323c  mov     [rsp-8+arg_10], rbx
0x180023241  push    rbp
0x180023242  push    rsi
0x180023243  push    rdi
0x180023244  push    r12
0x180023246  push    r13
0x180023248  push    r14
0x18002324a  push    r15
0x18002324c  lea     rbp, [rsp-140h]
0x180023254  sub     rsp, 240h
0x18002325b  mov     rax, cs:__security_cookie
0x180023262  xor     rax, rsp
0x180023265  mov     [rbp+170h+var_40], rax
0x18002326c  mov     r14, [rbp+170h+arg_20]
0x180023273  mov     rsi, rdx
0x180023276  mov     r12, rcx
0x180023279  xor     edx, edx; Val
0x18002327b  lea     rcx, [rsp+270h+pszDest]; void *
0x180023280  mov     r8d, 20Ah; Size
0x180023286  mov     r15, r9
0x180023289  call    memset_0
0x18002328e  mov     dword ptr [r14], 0FFFFFFFFh
0x180023295  lea     rcx, [rsp+270h+pszDest]; lpData
0x18002329a  xor     r13d, r13d
0x18002329d  mov     dword ptr [rsi], 0FFFFFFFFh
0x1800232a3  mov     edi, r13d
0x1800232a6  mov     [r15], r13w
0x1800232aa  call    GetDitFolder
0x1800232af  mov     ebx, eax
0x1800232b1  test    eax, eax
0x1800232b3  jnz     short loc_180023310
0x1800232b5  lea     r8, pszSrc; "\\"
0x1800232bc  mov     edx, 105h; cchDest
0x1800232c1  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800232c6  call    StringCchCatW
0x1800232cb  test    eax, eax
0x1800232cd  jns     short loc_1800232D7
0x1800232cf  movzx   ebx, ax
0x1800232d2  jmp     loc_1800233F3
0x1800232d7  lea     r8, [rsp+270h+pszDest]; pszSrc
0x1800232dc  mov     edx, 105h; cchDest
0x1800232e1  mov     rcx, r15; pszDest
0x1800232e4  call    StringCchCopyW
0x1800232e9  test    eax, eax
0x1800232eb  js      short loc_1800232CF
0x1800232ed  mov     eax, 1
0x1800232f2  lea     rdx, [rsp+270h+pszDest]; String2
0x1800232f7  mov     rcx, r12; String1
0x1800232fa  mov     [r14], eax
0x1800232fd  mov     edi, eax
0x1800232ff  call    cs:__imp__wcsicmp
0x180023305  test    eax, eax
0x180023307  jnz     short loc_180023310
0x180023309  mov     [rsi], edi
0x18002330b  jmp     loc_1800233F3
0x180023310  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180023315  call    GetNtdsFolder
0x18002331a  mov     ebx, eax
0x18002331c  test    eax, eax
0x18002331e  jnz     short loc_180023379
0x180023320  lea     r8, pszSrc; "\\"
0x180023327  mov     edx, 105h; cchDest
0x18002332c  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180023331  call    StringCchCatW
0x180023336  test    eax, eax
0x180023338  js      short loc_1800232CF
0x18002333a  test    edi, edi
0x18002333c  jnz     short loc_18002335F
0x18002333e  lea     r8, [rsp+270h+pszDest]; pszSrc
0x180023343  mov     edx, 105h; cchDest
0x180023348  mov     rcx, r15; pszDest
0x18002334b  call    StringCchCopyW
0x180023350  test    eax, eax
0x180023352  js      loc_1800232CF
0x180023358  mov     dword ptr [r14], 2
0x18002335f  lea     rdx, [rsp+270h+pszDest]; String2
0x180023364  mov     rcx, r12; String1
0x180023367  call    cs:__imp__wcsicmp
0x18002336d  test    eax, eax
0x18002336f  jnz     short loc_180023379
0x180023371  mov     dword ptr [rsi], 2
0x180023377  jmp     short loc_1800233F3
0x180023379  lea     rdx, [rsp+270h+pszDest]; lpBuffer
0x18002337e  mov     ecx, 105h; nBufferLength
0x180023383  call    cs:__imp_GetLogicalDriveStringsW
0x180023389  test    eax, eax
0x18002338b  jnz     short loc_180023397
0x18002338d  call    cs:__imp_GetLastError
0x180023393  mov     ebx, eax
0x180023395  jmp     short loc_1800233F3
0x180023397  mov     edi, 3
0x18002339c  lea     rbx, [rsp+270h+pszDest]
0x1800233a1  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800233a5  mov     rax, r14
0x1800233a8  inc     rax
0x1800233ab  cmp     [rbx+rax*2], r13w
0x1800233b0  jnz     short loc_1800233A8
0x1800233b2  test    rax, rax
0x1800233b5  jz      short loc_1800233F0
0x1800233b7  mov     rcx, rbx; lpRootPathName
0x1800233ba  call    cs:__imp_GetDriveTypeW
0x1800233c0  cmp     eax, 2
0x1800233c3  jnz     short loc_1800233D7
0x1800233c5  mov     rdx, rbx; String2
0x1800233c8  mov     rcx, r12; String1
0x1800233cb  call    cs:__imp__wcsicmp
0x1800233d1  test    eax, eax
0x1800233d3  jz      short loc_1800233EE
0x1800233d5  inc     edi
0x1800233d7  mov     rax, r14
0x1800233da  inc     rax
0x1800233dd  cmp     [rbx+rax*2], r13w
0x1800233e2  jnz     short loc_1800233DA
0x1800233e4  lea     rbx, [rbx+rax*2]
0x1800233e8  add     rbx, 2
0x1800233ec  jmp     short loc_1800233A5
0x1800233ee  mov     [rsi], edi
0x1800233f0  mov     ebx, r13d
0x1800233f3  mov     eax, ebx
0x1800233f5  mov     rcx, [rbp+170h+var_40]
0x1800233fc  xor     rcx, rsp; StackCookie
0x1800233ff  call    __security_check_cookie
0x180023404  mov     rbx, [rsp+270h+arg_10]
0x18002340c  add     rsp, 240h
0x180023413  pop     r15
0x180023415  pop     r14
0x180023417  pop     r13
0x180023419  pop     r12
0x18002341b  pop     rdi
0x18002341c  pop     rsi
0x18002341d  pop     rbp
0x18002341e  retn
```
