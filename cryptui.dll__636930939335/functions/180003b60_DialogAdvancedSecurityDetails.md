# DialogAdvancedSecurityDetails

- ea: `0x180003b60`
- end: `0x180003cc8`
- name: `DialogAdvancedSecurityDetails`
- size: `360`
- prototype: `__int64 __fastcall(HWND hDlg)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180003b60`
- `0x180004dc4`
- `0x18003e582`
- `0x18003e5c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bf7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003bf7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003bdb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003bdb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180003c60`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180003c60`
- `USER32!SetWindowLongPtrW` at `0x180003bec`
- `USER32!SetWindowLongPtrW` at `0x180003bec`
- `USER32!EndDialog` at `0x180003bb0`
- `USER32!EndDialog` at `0x180003c09`
- `USER32!EndDialog` at `0x180003bb0`
- `USER32!EndDialog` at `0x180003c09`
- `USER32!SetWindowTextW` at `0x180003c3b`
- `USER32!SetWindowTextW` at `0x180003c7c`
- `USER32!SetWindowTextW` at `0x180003c9f`
- `USER32!SetWindowTextW` at `0x180003c3b`
- `USER32!SetWindowTextW` at `0x180003c7c`
- `USER32!SetWindowTextW` at `0x180003c9f`
- `USER32!GetDlgItem` at `0x180003c2b`
- `USER32!GetDlgItem` at `0x180003c6e`
- `USER32!GetDlgItem` at `0x180003c93`
- `USER32!GetDlgItem` at `0x180003c2b`
- `USER32!GetDlgItem` at `0x180003c6e`
- `USER32!GetDlgItem` at `0x180003c93`

## pseudocode

```c
__int64 __fastcall DialogAdvancedSecurityDetails(HWND hDlg, int a2, unsigned __int16 a3, LONG_PTR a4)
{
  int v6; // edx
  __int64 v8; // rcx
  HWND DlgItem; // rax
  HWND v10; // rax
  const WCHAR *v11; // rdi
  HWND v12; // rax
  WCHAR Buffer; // [rsp+20h] [rbp-218h] BYREF
  _BYTE v14[510]; // [rsp+22h] [rbp-216h] BYREF

  v6 = a2 - 272;
  if ( v6 )
  {
    if ( v6 == 1 && (a3 == 1 || a3 == 2) )
    {
      EndDialog(hDlg, a3);
      return 1;
    }
  }
  else
  {
    Buffer = 0;
    memset_0(v14, 0, sizeof(v14));
    SetLastError(0);
    if ( SetWindowLongPtrW(hDlg, -21, a4) || !GetLastError() )
    {
      InitializeDetailGlobals(v8);
      if ( g_szDetailApplicationPath )
      {
        DlgItem = GetDlgItem(hDlg, 1051);
        SetWindowTextW(DlgItem, (LPCWSTR)g_szDetailApplicationPath);
      }
      LoadStringW(g_hInstProtectUI, 3396 - (*(_DWORD *)(a4 + 40) != 0), &Buffer, 256);
      v10 = GetDlgItem(hDlg, 1052);
      SetWindowTextW(v10, &Buffer);
      v11 = *(const WCHAR **)(a4 + 16);
      if ( v11 )
      {
        v12 = GetDlgItem(hDlg, 1050);
        SetWindowTextW(v12, v11);
      }
    }
    else
    {
      EndDialog(hDlg, 2);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003b60  mov     [rsp+arg_8], rbx
0x180003b65  push    rdi
0x180003b66  sub     rsp, 230h
0x180003b6d  mov     rax, cs:__security_cookie
0x180003b74  xor     rax, rsp
0x180003b77  mov     [rsp+238h+var_18], rax
0x180003b7f  mov     rdi, r9
0x180003b82  mov     rbx, rcx
0x180003b85  sub     edx, 110h
0x180003b8b  jz      short loc_180003BC0
0x180003b8d  cmp     edx, 1
0x180003b90  jnz     loc_180003CA5
0x180003b96  movzx   ecx, r8w
0x180003b9a  mov     edx, ecx
0x180003b9c  sub     edx, 1
0x180003b9f  jz      short loc_180003BAA
0x180003ba1  cmp     edx, 1
0x180003ba4  jnz     loc_180003CA5
0x180003baa  mov     rdx, rcx; nResult
0x180003bad  mov     rcx, rbx; hDlg
0x180003bb0  call    cs:__imp_EndDialog
0x180003bb6  mov     eax, 1
0x180003bbb  jmp     loc_180003CA7
0x180003bc0  xor     eax, eax
0x180003bc2  lea     rcx, [rsp+238h+var_216]; void *
0x180003bc7  xor     edx, edx; Val
0x180003bc9  mov     [rsp+238h+Buffer], ax
0x180003bce  mov     r8d, 1FEh; Size
0x180003bd4  call    memset_0
0x180003bd9  xor     ecx, ecx; dwErrCode
0x180003bdb  call    cs:__imp_SetLastError
0x180003be1  mov     r8, rdi; dwNewLong
0x180003be4  mov     edx, 0FFFFFFEBh; nIndex
0x180003be9  mov     rcx, rbx; hWnd
0x180003bec  call    cs:__imp_SetWindowLongPtrW
0x180003bf2  test    rax, rax
0x180003bf5  jnz     short loc_180003C14
0x180003bf7  call    cs:__imp_GetLastError
0x180003bfd  test    eax, eax
0x180003bff  jz      short loc_180003C14
0x180003c01  mov     edx, 2; nResult
0x180003c06  mov     rcx, rbx; hDlg
0x180003c09  call    cs:__imp_EndDialog
0x180003c0f  jmp     loc_180003CA5
0x180003c14  call    InitializeDetailGlobals
0x180003c19  cmp     cs:g_szDetailApplicationPath, 0
0x180003c21  jz      short loc_180003C41
0x180003c23  mov     edx, 41Bh; nIDDlgItem
0x180003c28  mov     rcx, rbx; hDlg
0x180003c2b  call    cs:__imp_GetDlgItem
0x180003c31  mov     rdx, cs:g_szDetailApplicationPath; lpString
0x180003c38  mov     rcx, rax; hWnd
0x180003c3b  call    cs:__imp_SetWindowTextW
0x180003c41  mov     eax, [rdi+28h]
0x180003c44  lea     r8, [rsp+238h+Buffer]; lpBuffer
0x180003c49  mov     rcx, cs:g_hInstProtectUI; hInstance
0x180003c50  neg     eax
0x180003c52  mov     r9d, 100h; cchBufferMax
0x180003c58  sbb     edx, edx
0x180003c5a  add     edx, 0D44h; uID
0x180003c60  call    cs:__imp_LoadStringW
0x180003c66  mov     edx, 41Ch; nIDDlgItem
0x180003c6b  mov     rcx, rbx; hDlg
0x180003c6e  call    cs:__imp_GetDlgItem
0x180003c74  mov     rcx, rax; hWnd
0x180003c77  lea     rdx, [rsp+238h+Buffer]; lpString
0x180003c7c  call    cs:__imp_SetWindowTextW
0x180003c82  mov     rdi, [rdi+10h]
0x180003c86  test    rdi, rdi
0x180003c89  jz      short loc_180003CA5
0x180003c8b  mov     edx, 41Ah; nIDDlgItem
0x180003c90  mov     rcx, rbx; hDlg
0x180003c93  call    cs:__imp_GetDlgItem
0x180003c99  mov     rcx, rax; hWnd
0x180003c9c  mov     rdx, rdi; lpString
0x180003c9f  call    cs:__imp_SetWindowTextW
0x180003ca5  xor     eax, eax
0x180003ca7  mov     rcx, [rsp+238h+var_18]
0x180003caf  xor     rcx, rsp; StackCookie
0x180003cb2  call    __security_check_cookie
0x180003cb7  mov     rbx, [rsp+238h+arg_8]
0x180003cbf  add     rsp, 230h
0x180003cc6  pop     rdi
0x180003cc7  retn
```
