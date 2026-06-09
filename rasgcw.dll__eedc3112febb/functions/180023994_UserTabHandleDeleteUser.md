# UserTabHandleDeleteUser

- ea: `0x180023994`
- end: `0x180023ba6`
- name: `UserTabHandleDeleteUser`
- size: `530`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18002326c`

## callees

- `0x18002049c`
- `0x180022da4`
- `0x1800235f8`
- `0x180023994`
- `0x180026710`
- `0x1800267dc`
- `0x180026d7c`
- `0x180027338`
- `0x18002749c`
- `0x1800274bc`
- `0x18002b970`
- `0x18002f3b0`

## import_xrefs

- `USER32!GetDlgItem` at `0x180023b3e`
- `USER32!GetDlgItem` at `0x180023b3e`
- `USER32!MessageBoxW` at `0x180023b0e`
- `USER32!MessageBoxW` at `0x180023b0e`
- `USER32!SendMessageW` at `0x180023b5a`
- `USER32!SendMessageW` at `0x180023b5a`

## string_xrefs

- `0x180023ae0`: `UserTabHandleDeleteUser: StringCchPrintfExW failed. hr = 0x%x`

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
            UserTabFillUserList(v16);
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
0x180023994  mov     [rsp-8+arg_10], rbx
0x180023999  push    rbp
0x18002399a  push    rdi
0x18002399b  push    r12
0x18002399d  push    r14
0x18002399f  push    r15
0x1800239a1  lea     rbp, [rsp-580h]
0x1800239a9  sub     rsp, 680h
0x1800239b0  mov     rax, cs:__security_cookie
0x1800239b7  xor     rax, rsp
0x1800239ba  mov     [rbp+5A0h+var_30], rax
0x1800239c1  xor     r12d, r12d
0x1800239c4  lea     r8, [rsp+6A0h+var_658]
0x1800239c9  mov     r14d, edx
0x1800239cc  mov     [rsp+6A0h+var_648], r12
0x1800239d1  mov     r15d, 101h
0x1800239d7  mov     [rsp+6A0h+var_658], r12
0x1800239dc  mov     rbx, rcx
0x1800239df  mov     [rsp+6A0h+var_650], r12
0x1800239e4  lea     edx, [r12+2]
0x1800239e9  mov     [rsp+6A0h+var_660], r15d
0x1800239ee  call    RasSrvGetDatabaseHandle
0x1800239f3  mov     rcx, [rsp+6A0h+var_658]
0x1800239f8  lea     r8, [rsp+6A0h+var_650]
0x1800239fd  mov     edx, r14d
0x180023a00  call    usrGetUserHandle
0x180023a05  mov     edi, eax
0x180023a07  test    eax, eax
0x180023a09  jz      short loc_180023A25
0x180023a0b  mov     edx, 1CA3h
0x180023a10  mov     rcx, rbx; hWnd
0x180023a13  mov     r8d, 1C8Ch
0x180023a19  call    ErrDisplayError
0x180023a1e  mov     eax, edi
0x180023a20  jmp     loc_180023B7F
0x180023a25  mov     rcx, [rsp+6A0h+var_650]
0x180023a2a  lea     rdx, [rsp+6A0h+var_648]
0x180023a2f  call    usrGetName
0x180023a34  test    eax, eax
0x180023a36  jnz     loc_180023B7F
0x180023a3c  lea     r9, [rsp+6A0h+var_660]
0x180023a41  mov     r8d, r15d
0x180023a44  lea     rdx, [rsp+6A0h+var_640]
0x180023a49  call    usrGetFullName
0x180023a4e  test    eax, eax
0x180023a50  jnz     loc_180023B7F
0x180023a56  mov     rcx, cs:hInstance; hModule
0x180023a5d  lea     r8, [rsp+6A0h+var_660]
0x180023a62  mov     edx, 1CBAh
0x180023a67  mov     [rsp+6A0h+var_660], r12d
0x180023a6c  call    PszLoadStringPcch
0x180023a71  mov     rcx, cs:hInstance; hModule
0x180023a78  lea     r8, [rsp+6A0h+var_660]
0x180023a7d  mov     edx, 1CB9h
0x180023a82  mov     [rsp+6A0h+var_660], r12d
0x180023a87  mov     rdi, rax
0x180023a8a  call    PszLoadStringPcch
0x180023a8f  mov     r15, rax
0x180023a92  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180023a96  lea     rax, [rsp+6A0h+var_640]
0x180023a9b  inc     rcx
0x180023a9e  cmp     [rax+rcx*2], r12w
0x180023aa3  jnz     short loc_180023A9B
0x180023aa5  xor     r9d, r9d; pcchRemaining
0x180023aa8  xor     r8d, r8d; ppszDestEnd
0x180023aab  test    rcx, rcx
0x180023aae  mov     edx, 200h; cchDest
0x180023ab3  lea     rcx, [rbp+5A0h+pszDest]; pszDest
0x180023aba  jz      short loc_180023AF4
0x180023abc  lea     rax, [rsp+6A0h+var_640]
0x180023ac1  mov     [rsp+6A0h+var_670], rax
0x180023ac6  mov     [rsp+6A0h+pszFormat], rdi; pszFormat
0x180023acb  mov     [rsp+6A0h+dwFlags], 100h; dwFlags
0x180023ad3  call    StringCchPrintfExW
0x180023ad8  mov     edi, eax
0x180023ada  test    eax, eax
0x180023adc  jns     short loc_180023AFB
0x180023ade  mov     edx, eax
0x180023ae0  lea     rcx, aUsertabhandled; "UserTabHandleDeleteUser: StringCchPrint"...
0x180023ae7  call    DbgOutputTrace
0x180023aec  movzx   eax, di
0x180023aef  jmp     loc_180023B7F
0x180023af4  mov     rax, [rsp+6A0h+var_648]
0x180023af9  jmp     short loc_180023AC1
0x180023afb  mov     r9d, 34h ; '4'; uType
0x180023b01  lea     rdx, [rbp+5A0h+pszDest]; lpText
0x180023b08  mov     r8, r15; lpCaption
0x180023b0b  mov     rcx, rbx; hWnd
0x180023b0e  call    cs:__imp_MessageBoxW
0x180023b14  cmp     eax, 7
0x180023b17  jz      short loc_180023B7D
0x180023b19  mov     rcx, [rsp+6A0h+var_658]
0x180023b1e  mov     edx, r14d
0x180023b21  call    usrDeleteUser
0x180023b26  mov     edi, eax
0x180023b28  mov     rcx, rbx; hDlg
0x180023b2b  test    eax, eax
0x180023b2d  jz      short loc_180023B39
0x180023b2f  mov     edx, 1CB7h
0x180023b34  jmp     loc_180023A13
0x180023b39  mov     edx, 1B83h; nIDDlgItem
0x180023b3e  call    cs:__imp_GetDlgItem
0x180023b44  mov     rdi, rax
0x180023b47  test    rax, rax
0x180023b4a  jz      short loc_180023B7D
0x180023b4c  xor     r9d, r9d; lParam
0x180023b4f  xor     r8d, r8d; wParam
0x180023b52  mov     edx, 1009h; Msg
0x180023b57  mov     rcx, rax; hWnd
0x180023b5a  call    cs:__imp_SendMessageW
0x180023b60  test    eax, eax
0x180023b62  jnz     short loc_180023B70
0x180023b64  mov     edi, 1C9Ch
0x180023b69  mov     edx, edi
0x180023b6b  jmp     loc_180023A10
0x180023b70  mov     rdx, [rsp+6A0h+var_658]
0x180023b75  mov     rcx, rdi; hWnd
0x180023b78  call    UserTabFillUserList
0x180023b7d  xor     eax, eax
0x180023b7f  mov     rcx, [rbp+5A0h+var_30]
0x180023b86  xor     rcx, rsp; StackCookie
0x180023b89  call    __security_check_cookie
0x180023b8e  mov     rbx, [rsp+6A0h+arg_10]
0x180023b96  add     rsp, 680h
0x180023b9d  pop     r15
0x180023b9f  pop     r14
0x180023ba1  pop     r12
0x180023ba3  pop     rdi
0x180023ba4  pop     rbp
0x180023ba5  retn
```
