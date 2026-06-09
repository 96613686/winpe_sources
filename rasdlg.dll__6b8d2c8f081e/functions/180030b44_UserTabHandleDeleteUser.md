# UserTabHandleDeleteUser

- ea: `0x180030b44`
- end: `0x180030d56`
- name: `UserTabHandleDeleteUser`
- size: `530`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18003039c`

## callees

- `0x18000f380`
- `0x18002e918`
- `0x180030748`
- `0x180030b44`
- `0x1800348f0`
- `0x1800349c4`
- `0x180034f6c`
- `0x180035530`
- `0x1800356a4`
- `0x1800356c4`
- `0x18003c4ec`
- `0x18004d110`

## import_xrefs

- `USER32!MessageBoxW` at `0x180030cbe`
- `USER32!MessageBoxW` at `0x180030cbe`
- `USER32!SendMessageW` at `0x180030d0a`
- `USER32!SendMessageW` at `0x180030d0a`
- `USER32!GetDlgItem` at `0x180030cee`
- `USER32!GetDlgItem` at `0x180030cee`

## string_xrefs

- `0x180030c90`: `UserTabHandleDeleteUser: StringCchPrintfExW failed. hr = 0x%x`

## pseudocode

```c
__int64 __fastcall UserTabHandleDeleteUser(HWND hWnd, unsigned int a2)
{
  unsigned int UserHandle; // edi
  HWND v5; // rcx
  __int64 result; // rax
  __int64 v7; // rcx
  __int64 StringPcch; // rax
  const wchar_t *pszFormat; // rdi
  const WCHAR *v10; // r15
  __int64 v11; // rcx
  wchar_t *v12; // rax
  HRESULT v13; // eax
  unsigned __int16 v14; // di
  HWND DlgItem; // rax
  HWND v16; // rdi
  int v17; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v18; // [rsp+48h] [rbp-B8h]
  __int64 v19; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v20; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t v21[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[512]; // [rsp+270h] [rbp+170h] BYREF

  v20 = 0;
  v18 = 0;
  v19 = 0;
  v17 = 257;
  RasSrvGetDatabaseHandle(hWnd);
  UserHandle = usrGetUserHandle(0, a2, &v19);
  if ( UserHandle )
    goto LABEL_2;
  result = usrGetName(v19, &v20);
  if ( !(_DWORD)result )
  {
    result = usrGetFullName(v7, v21, 257, &v17);
    if ( !(_DWORD)result )
    {
      v17 = 0;
      StringPcch = PszLoadStringPcch(hInstance);
      v17 = 0;
      pszFormat = (const wchar_t *)StringPcch;
      v10 = (const WCHAR *)PszLoadStringPcch(hInstance);
      v11 = -1;
      do
        ++v11;
      while ( v21[v11] );
      if ( v11 )
        v12 = v21;
      else
        v12 = v20;
      v13 = StringCchPrintfExW(pszDest, 0x200u, 0, 0, 0x100u, pszFormat, v12);
      v14 = v13;
      if ( v13 >= 0 )
      {
        if ( MessageBoxW(hWnd, pszDest, v10, 0x34u) != 7 )
        {
          UserHandle = usrDeleteUser(v18, a2);
          v5 = hWnd;
          if ( UserHandle )
            goto LABEL_3;
          DlgItem = GetDlgItem(hWnd, 7043);
          v16 = DlgItem;
          if ( DlgItem )
          {
            if ( !(unsigned int)SendMessageW(DlgItem, 0x1009u, 0, 0) )
            {
              UserHandle = 7324;
LABEL_2:
              v5 = hWnd;
LABEL_3:
              ErrDisplayError(v5);
              return UserHandle;
            }
            UserTabFillUserList(v16, v18);
          }
        }
        return 0;
      }
      else
      {
        DbgOutputTrace("UserTabHandleDeleteUser: StringCchPrintfExW failed. hr = 0x%x", v13);
        return v14;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180030b44  mov     [rsp-8+arg_10], rbx
0x180030b49  push    rbp
0x180030b4a  push    rdi
0x180030b4b  push    r12
0x180030b4d  push    r14
0x180030b4f  push    r15
0x180030b51  lea     rbp, [rsp-580h]
0x180030b59  sub     rsp, 680h
0x180030b60  mov     rax, cs:__security_cookie
0x180030b67  xor     rax, rsp
0x180030b6a  mov     [rbp+5A0h+var_30], rax
0x180030b71  xor     r12d, r12d
0x180030b74  lea     r8, [rsp+6A0h+var_658]
0x180030b79  mov     r14d, edx
0x180030b7c  mov     [rsp+6A0h+var_648], r12
0x180030b81  mov     r15d, 101h
0x180030b87  mov     [rsp+6A0h+var_658], r12
0x180030b8c  mov     rbx, rcx
0x180030b8f  mov     [rsp+6A0h+var_650], r12
0x180030b94  lea     edx, [r12+2]
0x180030b99  mov     [rsp+6A0h+var_660], r15d
0x180030b9e  call    RasSrvGetDatabaseHandle
0x180030ba3  mov     rcx, [rsp+6A0h+var_658]
0x180030ba8  lea     r8, [rsp+6A0h+var_650]
0x180030bad  mov     edx, r14d
0x180030bb0  call    usrGetUserHandle
0x180030bb5  mov     edi, eax
0x180030bb7  test    eax, eax
0x180030bb9  jz      short loc_180030BD5
0x180030bbb  mov     edx, 1CA3h
0x180030bc0  mov     rcx, rbx; hWnd
0x180030bc3  mov     r8d, 1C8Ch
0x180030bc9  call    ErrDisplayError
0x180030bce  mov     eax, edi
0x180030bd0  jmp     loc_180030D2F
0x180030bd5  mov     rcx, [rsp+6A0h+var_650]
0x180030bda  lea     rdx, [rsp+6A0h+var_648]
0x180030bdf  call    usrGetName
0x180030be4  test    eax, eax
0x180030be6  jnz     loc_180030D2F
0x180030bec  lea     r9, [rsp+6A0h+var_660]
0x180030bf1  mov     r8d, r15d
0x180030bf4  lea     rdx, [rsp+6A0h+var_640]
0x180030bf9  call    usrGetFullName
0x180030bfe  test    eax, eax
0x180030c00  jnz     loc_180030D2F
0x180030c06  mov     rcx, cs:hInstance; hModule
0x180030c0d  lea     r8, [rsp+6A0h+var_660]
0x180030c12  mov     edx, 1CBAh
0x180030c17  mov     [rsp+6A0h+var_660], r12d
0x180030c1c  call    PszLoadStringPcch
0x180030c21  mov     rcx, cs:hInstance; hModule
0x180030c28  lea     r8, [rsp+6A0h+var_660]
0x180030c2d  mov     edx, 1CB9h
0x180030c32  mov     [rsp+6A0h+var_660], r12d
0x180030c37  mov     rdi, rax
0x180030c3a  call    PszLoadStringPcch
0x180030c3f  mov     r15, rax
0x180030c42  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180030c46  lea     rax, [rsp+6A0h+var_640]
0x180030c4b  inc     rcx
0x180030c4e  cmp     [rax+rcx*2], r12w
0x180030c53  jnz     short loc_180030C4B
0x180030c55  xor     r9d, r9d; pcchRemaining
0x180030c58  xor     r8d, r8d; ppszDestEnd
0x180030c5b  test    rcx, rcx
0x180030c5e  mov     edx, 200h; cchDest
0x180030c63  lea     rcx, [rbp+5A0h+pszDest]; pszDest
0x180030c6a  jz      short loc_180030CA4
0x180030c6c  lea     rax, [rsp+6A0h+var_640]
0x180030c71  mov     [rsp+6A0h+var_670], rax
0x180030c76  mov     [rsp+6A0h+pszFormat], rdi; pszFormat
0x180030c7b  mov     [rsp+6A0h+dwFlags], 100h; dwFlags
0x180030c83  call    StringCchPrintfExW
0x180030c88  mov     edi, eax
0x180030c8a  test    eax, eax
0x180030c8c  jns     short loc_180030CAB
0x180030c8e  mov     edx, eax
0x180030c90  lea     rcx, aUsertabhandled; "UserTabHandleDeleteUser: StringCchPrint"...
0x180030c97  call    DbgOutputTrace
0x180030c9c  movzx   eax, di
0x180030c9f  jmp     loc_180030D2F
0x180030ca4  mov     rax, [rsp+6A0h+var_648]
0x180030ca9  jmp     short loc_180030C71
0x180030cab  mov     r9d, 34h ; '4'; uType
0x180030cb1  lea     rdx, [rbp+5A0h+pszDest]; lpText
0x180030cb8  mov     r8, r15; lpCaption
0x180030cbb  mov     rcx, rbx; hWnd
0x180030cbe  call    cs:__imp_MessageBoxW
0x180030cc4  cmp     eax, 7
0x180030cc7  jz      short loc_180030D2D
0x180030cc9  mov     rcx, [rsp+6A0h+var_658]
0x180030cce  mov     edx, r14d
0x180030cd1  call    usrDeleteUser
0x180030cd6  mov     edi, eax
0x180030cd8  mov     rcx, rbx; hDlg
0x180030cdb  test    eax, eax
0x180030cdd  jz      short loc_180030CE9
0x180030cdf  mov     edx, 1CB7h
0x180030ce4  jmp     loc_180030BC3
0x180030ce9  mov     edx, 1B83h; nIDDlgItem
0x180030cee  call    cs:__imp_GetDlgItem
0x180030cf4  mov     rdi, rax
0x180030cf7  test    rax, rax
0x180030cfa  jz      short loc_180030D2D
0x180030cfc  xor     r9d, r9d; lParam
0x180030cff  xor     r8d, r8d; wParam
0x180030d02  mov     edx, 1009h; Msg
0x180030d07  mov     rcx, rax; hWnd
0x180030d0a  call    cs:__imp_SendMessageW
0x180030d10  test    eax, eax
0x180030d12  jnz     short loc_180030D20
0x180030d14  mov     edi, 1C9Ch
0x180030d19  mov     edx, edi
0x180030d1b  jmp     loc_180030BC0
0x180030d20  mov     rdx, [rsp+6A0h+var_658]
0x180030d25  mov     rcx, rdi; hWnd
0x180030d28  call    UserTabFillUserList
0x180030d2d  xor     eax, eax
0x180030d2f  mov     rcx, [rbp+5A0h+var_30]
0x180030d36  xor     rcx, rsp; StackCookie
0x180030d39  call    __security_check_cookie
0x180030d3e  mov     rbx, [rsp+6A0h+arg_10]
0x180030d46  add     rsp, 680h
0x180030d4d  pop     r15
0x180030d4f  pop     r14
0x180030d51  pop     r12
0x180030d53  pop     rdi
0x180030d54  pop     rbp
0x180030d55  retn
```
