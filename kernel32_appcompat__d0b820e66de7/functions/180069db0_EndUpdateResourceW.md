# EndUpdateResourceW

- ea: `0x180069db0`
- end: `0x18006a02e`
- name: `EndUpdateResourceW`
- size: `638`
- prototype: `BOOL __stdcall(HANDLE hUpdate, BOOL fDiscard)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180069da0`

## callees

- `0x18002f71c`
- `0x1800693bc`
- `0x180069ab4`
- `0x180069b50`
- `0x180069db0`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180069de9`
- `ntdll!RtlSetLastWin32Error` at `0x180069dfe`
- `ntdll!RtlSetLastWin32Error` at `0x180069ffb`
- `ntdll!RtlSetLastWin32Error` at `0x180069de9`
- `ntdll!RtlSetLastWin32Error` at `0x180069dfe`
- `ntdll!RtlSetLastWin32Error` at `0x180069ffb`
- `KERNELBASE!GlobalFree` at `0x180069e45`
- `KERNELBASE!GlobalFree` at `0x180069fc7`
- `KERNELBASE!GlobalFree` at `0x180069fed`
- `KERNELBASE!GlobalFree` at `0x180069e45`
- `KERNELBASE!GlobalFree` at `0x180069fc7`
- `KERNELBASE!GlobalFree` at `0x180069fed`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180069ef6`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180069f35`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180069ef6`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180069f35`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180069f95`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180069fa7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180069f95`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180069fa7`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180069f6e`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180069f6e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180069e14`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180069e30`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180069e75`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180069e14`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180069e30`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180069e75`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180069fb7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180069fde`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180069fb7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180069fde`

## pseudocode

```c
BOOL __stdcall EndUpdateResourceW(HANDLE hUpdate, BOOL fDiscard)
{
  ULONG v4; // ecx
  HGLOBAL *v6; // rax
  HGLOBAL *v7; // rsi
  ULONG LastErrorValue; // ebx
  ULONG v9; // edi
  const wchar_t *v10; // rax
  const WCHAR *v11; // r15
  HRESULT v12; // eax
  STRSAFE_LPWSTR v13; // rcx
  unsigned int v14; // ecx
  ULONG v15; // eax
  DWORD v16; // [rsp+28h] [rbp-D8h]
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF

  ppszDestEnd = 0;
  RtlSetLastWin32Error(0);
  if ( !hUpdate )
  {
    v4 = 87;
LABEL_3:
    RtlSetLastWin32Error(v4);
    return 0;
  }
  v6 = (HGLOBAL *)GlobalLock(hUpdate);
  v7 = v6;
  if ( !fDiscard )
  {
    if ( !v6 )
      return 0;
    v10 = (const wchar_t *)GlobalLock(v6[6]);
    v11 = v10;
    if ( !v10 )
    {
      v4 = 1359;
      goto LABEL_3;
    }
    v12 = StringCchCopyExW(pszDest, 0x104u, v10, &ppszDestEnd, 0, v16);
    if ( v12 < 0 )
    {
      LastErrorValue = (unsigned __int16)v12;
LABEL_29:
      v9 = LastErrorValue;
      goto LABEL_31;
    }
    v13 = ppszDestEnd;
    v9 = 0;
    do
      --v13;
    while ( *v13 != 92 && v13 >= pszDest );
    v13[1] = 0;
    if ( GetTempFileNameW(pszDest, L"RCX", 0, pszDest) )
      goto LABEL_24;
    if ( !UpdrGetTempPath(v14, pszDest) )
      wcscpy(pszDest, L".\\");
    if ( GetTempFileNameW(pszDest, L"RCX", 0, pszDest) )
    {
LABEL_24:
      v15 = WriteResFile(hUpdate, pszDest);
      LastErrorValue = v15;
      if ( v15 )
      {
        v9 = v15;
        DeleteFileW(pszDest);
        goto LABEL_31;
      }
      if ( !MoveFileExW(pszDest, v11, 3u) )
      {
        LastErrorValue = NtCurrentTeb()->LastErrorValue;
        if ( !LastErrorValue )
          LastErrorValue = 1359;
        DeleteFileW(pszDest);
        goto LABEL_29;
      }
    }
    else
    {
      LastErrorValue = NtCurrentTeb()->LastErrorValue;
    }
LABEL_31:
    GlobalUnlock(v7[6]);
    GlobalFree(v7[6]);
    goto LABEL_32;
  }
  if ( v6 )
  {
    if ( !GlobalLock(v6[6]) )
    {
      LastErrorValue = 0;
      v9 = 0;
LABEL_33:
      GlobalUnlock(hUpdate);
      goto LABEL_34;
    }
    GlobalFree(v7[6]);
    LastErrorValue = 0;
    v9 = 0;
LABEL_32:
    FreeData((struct _UPDATEDATA *)v7);
    goto LABEL_33;
  }
  LastErrorValue = 0;
  v9 = 0;
LABEL_34:
  GlobalFree(hUpdate);
  RtlSetLastWin32Error(v9);
  return LastErrorValue == 0;
}

```

## disassembly

```asm
0x180069db0  push    rbp
0x180069db2  push    rbx
0x180069db3  push    rsi
0x180069db4  push    rdi
0x180069db5  push    r14
0x180069db7  push    r15
0x180069db9  lea     rbp, [rsp-168h]
0x180069dc1  sub     rsp, 268h
0x180069dc8  mov     rax, cs:__security_cookie
0x180069dcf  xor     rax, rsp
0x180069dd2  mov     [rbp+190h+var_40], rax
0x180069dd9  mov     r14, rcx
0x180069ddc  mov     [rsp+290h+ppszDestEnd], 0
0x180069de5  xor     ecx, ecx; LastError
0x180069de7  mov     ebx, edx
0x180069de9  call    cs:__imp_RtlSetLastWin32Error
0x180069df0  nop     dword ptr [rax+rax+00h]
0x180069df5  test    r14, r14
0x180069df8  jnz     short loc_180069E11
0x180069dfa  lea     ecx, [r14+57h]; LastError
0x180069dfe  call    cs:__imp_RtlSetLastWin32Error
0x180069e05  nop     dword ptr [rax+rax+00h]
0x180069e0a  xor     eax, eax
0x180069e0c  jmp     loc_18006A00E
0x180069e11  mov     rcx, r14; hMem
0x180069e14  call    cs:__imp_GlobalLock
0x180069e1b  nop     dword ptr [rax+rax+00h]
0x180069e20  mov     rsi, rax
0x180069e23  test    ebx, ebx
0x180069e25  jz      short loc_180069E6C
0x180069e27  test    rax, rax
0x180069e2a  jz      short loc_180069E63
0x180069e2c  mov     rcx, [rax+30h]; hMem
0x180069e30  call    cs:__imp_GlobalLock
0x180069e37  nop     dword ptr [rax+rax+00h]
0x180069e3c  test    rax, rax
0x180069e3f  jz      short loc_180069E5A
0x180069e41  mov     rcx, [rsi+30h]; hMem
0x180069e45  call    cs:__imp_GlobalFree
0x180069e4c  nop     dword ptr [rax+rax+00h]
0x180069e51  xor     ebx, ebx
0x180069e53  xor     edi, edi
0x180069e55  jmp     loc_180069FD3
0x180069e5a  xor     ebx, ebx
0x180069e5c  xor     edi, edi
0x180069e5e  jmp     loc_180069FDB
0x180069e63  xor     ebx, ebx
0x180069e65  xor     edi, edi
0x180069e67  jmp     loc_180069FEA
0x180069e6c  test    rsi, rsi
0x180069e6f  jz      short loc_180069E0A
0x180069e71  mov     rcx, [rax+30h]; hMem
0x180069e75  call    cs:__imp_GlobalLock
0x180069e7c  nop     dword ptr [rax+rax+00h]
0x180069e81  mov     r15, rax
0x180069e84  test    rax, rax
0x180069e87  jnz     short loc_180069E93
0x180069e89  mov     ecx, 54Fh
0x180069e8e  jmp     loc_180069DFE
0x180069e93  lea     r9, [rsp+290h+ppszDestEnd]; ppszDestEnd
0x180069e98  mov     [rsp+290h+pcchRemaining], 0; pcchRemaining
0x180069ea1  mov     r8, r15; pszSrc
0x180069ea4  lea     rcx, [rsp+290h+pszDest]; pszDest
0x180069ea9  mov     edx, 104h; cchDest
0x180069eae  call    StringCchCopyExW
0x180069eb3  test    eax, eax
0x180069eb5  jns     short loc_180069EBF
0x180069eb7  movzx   ebx, ax
0x180069eba  jmp     loc_180069FA1
0x180069ebf  mov     rcx, [rsp+290h+ppszDestEnd]
0x180069ec4  xor     edi, edi
0x180069ec6  lea     ebx, [rdi+5Ch]
0x180069ec9  sub     rcx, 2
0x180069ecd  cmp     [rcx], bx
0x180069ed0  jz      short loc_180069EDC
0x180069ed2  lea     rax, [rsp+290h+pszDest]
0x180069ed7  cmp     rcx, rax
0x180069eda  jnb     short loc_180069EC9
0x180069edc  xor     eax, eax
0x180069ede  lea     r9, [rsp+290h+pszDest]; lpTempFileName
0x180069ee3  mov     [rcx+2], ax
0x180069ee7  lea     rdx, PrefixString; "RCX"
0x180069eee  lea     rcx, [rsp+290h+pszDest]; lpPathName
0x180069ef3  xor     r8d, r8d; uUnique
0x180069ef6  call    cs:__imp_GetTempFileNameW
0x180069efd  nop     dword ptr [rax+rax+00h]
0x180069f02  lea     rdx, [rsp+290h+pszDest]; unsigned __int16 *
0x180069f07  test    eax, eax
0x180069f09  jnz     short loc_180069F54
0x180069f0b  call    ?UpdrGetTempPath@@YAKKPEAG@Z; UpdrGetTempPath(ulong,ushort *)
0x180069f10  test    eax, eax
0x180069f12  jnz     short loc_180069F21
0x180069f14  mov     dword ptr [rsp+290h+pszDest], 5C002Eh
0x180069f1c  mov     [rsp+290h+var_24C], ax
0x180069f21  lea     r9, [rsp+290h+pszDest]; lpTempFileName
0x180069f26  xor     r8d, r8d; uUnique
0x180069f29  lea     rdx, PrefixString; "RCX"
0x180069f30  lea     rcx, [rsp+290h+pszDest]; lpPathName
0x180069f35  call    cs:__imp_GetTempFileNameW
0x180069f3c  nop     dword ptr [rax+rax+00h]
0x180069f41  test    eax, eax
0x180069f43  jnz     short loc_180069F4F
0x180069f45  mov     ebx, gs:68h
0x180069f4d  jmp     short loc_180069FB3
0x180069f4f  lea     rdx, [rsp+290h+pszDest]; lpFileName
0x180069f54  mov     rcx, r14; hMem
0x180069f57  call    ?WriteResFile@@YAJPEAXPEAG@Z; WriteResFile(void *,ushort *)
0x180069f5c  lea     rcx, [rsp+290h+pszDest]; lpFileName
0x180069f61  mov     ebx, eax
0x180069f63  test    eax, eax
0x180069f65  jnz     short loc_180069FA5
0x180069f67  lea     r8d, [rax+3]; dwFlags
0x180069f6b  mov     rdx, r15; lpNewFileName
0x180069f6e  call    cs:__imp_MoveFileExW
0x180069f75  nop     dword ptr [rax+rax+00h]
0x180069f7a  test    eax, eax
0x180069f7c  jnz     short loc_180069FB3
0x180069f7e  mov     ebx, gs:68h
0x180069f86  lea     rcx, [rsp+290h+pszDest]; lpFileName
0x180069f8b  test    ebx, ebx
0x180069f8d  mov     eax, 54Fh
0x180069f92  cmovz   ebx, eax
0x180069f95  call    cs:__imp_DeleteFileW
0x180069f9c  nop     dword ptr [rax+rax+00h]
0x180069fa1  mov     edi, ebx
0x180069fa3  jmp     short loc_180069FB3
0x180069fa5  mov     edi, eax
0x180069fa7  call    cs:__imp_DeleteFileW
0x180069fae  nop     dword ptr [rax+rax+00h]
0x180069fb3  mov     rcx, [rsi+30h]; hMem
0x180069fb7  call    cs:__imp_GlobalUnlock
0x180069fbe  nop     dword ptr [rax+rax+00h]
0x180069fc3  mov     rcx, [rsi+30h]; hMem
0x180069fc7  call    cs:__imp_GlobalFree
0x180069fce  nop     dword ptr [rax+rax+00h]
0x180069fd3  mov     rcx, rsi; struct _UPDATEDATA *
0x180069fd6  call    ?FreeData@@YAXPEAU_UPDATEDATA@@@Z; FreeData(_UPDATEDATA *)
0x180069fdb  mov     rcx, r14; hMem
0x180069fde  call    cs:__imp_GlobalUnlock
0x180069fe5  nop     dword ptr [rax+rax+00h]
0x180069fea  mov     rcx, r14; hMem
0x180069fed  call    cs:__imp_GlobalFree
0x180069ff4  nop     dword ptr [rax+rax+00h]
0x180069ff9  mov     ecx, edi; LastError
0x180069ffb  call    cs:__imp_RtlSetLastWin32Error
0x18006a002  nop     dword ptr [rax+rax+00h]
0x18006a007  xor     eax, eax
0x18006a009  test    ebx, ebx
0x18006a00b  setz    al
0x18006a00e  mov     rcx, [rbp+190h+var_40]
0x18006a015  xor     rcx, rsp; StackCookie
0x18006a018  call    __security_check_cookie
0x18006a01d  add     rsp, 268h
0x18006a024  pop     r15
0x18006a026  pop     r14
0x18006a028  pop     rdi
0x18006a029  pop     rsi
0x18006a02a  pop     rbx
0x18006a02b  pop     rbp
0x18006a02c  retn
```
