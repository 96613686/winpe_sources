# CGeneralPage::_UpdateAppNameAndIcon(ushort *,unsigned __int64,ushort * *)

- ea: `0x180012a04`
- end: `0x180012bb7`
- name: `?_UpdateAppNameAndIcon@CGeneralPage@@AEAAXPEAG_KPEAPEAG@Z`
- size: `435`
- prototype: `void __fastcall(CGeneralPage *__hidden this, unsigned __int16 *, unsigned __int64, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, installer_update`

## callers

- `0x1800116c0`
- `0x180012870`

## callees

- `0x180001840`
- `0x1800082f4`
- `0x180009018`
- `0x1800090e0`
- `0x180009f38`
- `0x18000cd0c`
- `0x18000d3f8`
- `0x18001140c`
- `0x180011568`
- `0x1800128c0`
- `0x18001296c`
- `0x180012a04`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180012b1d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180012b1d`
- `USER32!GetDlgItemTextW` at `0x180012ac6`
- `USER32!GetDlgItemTextW` at `0x180012ac6`
- `USER32!SetDlgItemTextW` at `0x180012b4e`
- `USER32!SetDlgItemTextW` at `0x180012b4e`

## pseudocode

```c
void __fastcall CGeneralPage::_UpdateAppNameAndIcon(
        CGeneralPage *this,
        unsigned __int16 *a2,
        unsigned __int64 a3,
        unsigned __int16 **a4)
{
  unsigned __int64 v8; // r8
  unsigned __int16 *v9; // rdi
  unsigned __int64 v10; // r8
  void *Block; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR String[264]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v13[264]; // [rsp+240h] [rbp+140h] BYREF

  memset_0(v13, 0, 0x20Au);
  Block = 0;
  CGeneralPage::_GetAppAndArgs(this, v13, v8, (unsigned __int16 **)&Block);
  v9 = (unsigned __int16 *)Block;
  if ( Block )
  {
    if ( IsLocalFilename((const unsigned __int16 *)this + 70) )
    {
      CGeneralPage::_ExpandAppName(this, v13, v10);
      *((_DWORD *)this + 174) |= 0x10u;
      CGeneralPage::_UpdateAppIcon(this, v13);
      GetDlgItemTextW(*((HWND *)this + 14), 1667, String, 261);
      StripLeadTrailSpace(String);
      DeleteQuotes(String);
      if ( !String[0] && IsLocalFilename(v13) )
      {
        StringCchCopyW(String, 0x105u, v13);
        DeleteQuotes(String);
        PathRemoveFileSpecW(String);
        if ( (unsigned int)HasSpacesW(String) )
          AddQuotes(String, 0x105u);
        SetDlgItemTextW(*((HWND *)this + 14), 1667, String);
      }
      *((_DWORD *)this + 174) |= 0x20u;
      CGeneralPage::_SetAppEdit(this, v13, v9);
    }
    if ( a2 )
      StringCchCopyW(a2, a3, v13);
    if ( a4 )
      *a4 = v9;
    else
      operator delete(v9);
  }
}

```

## disassembly

```asm
0x180012a04  push    rbp
0x180012a06  push    rbx
0x180012a07  push    rsi
0x180012a08  push    rdi
0x180012a09  push    r12
0x180012a0b  push    r14
0x180012a0d  push    r15
0x180012a0f  lea     rbp, [rsp-360h]
0x180012a17  sub     rsp, 460h
0x180012a1e  mov     rax, cs:__security_cookie
0x180012a25  xor     rax, rsp
0x180012a28  mov     [rbp+390h+var_40], rax
0x180012a2f  mov     r15, r8
0x180012a32  mov     r14, rdx
0x180012a35  mov     rbx, rcx
0x180012a38  xor     edx, edx; Val
0x180012a3a  mov     r8d, 20Ah; Size
0x180012a40  lea     rcx, [rbp+390h+var_250]; void *
0x180012a47  mov     rsi, r9
0x180012a4a  call    memset_0
0x180012a4f  xor     r12d, r12d
0x180012a52  lea     r9, [rsp+490h+Block]; unsigned __int16 **
0x180012a57  lea     rdx, [rbp+390h+var_250]; unsigned __int16 *
0x180012a5e  mov     [rsp+490h+Block], r12
0x180012a63  mov     rcx, rbx; this
0x180012a66  call    ?_GetAppAndArgs@CGeneralPage@@AEAAXPEAG_KPEAPEAG@Z; CGeneralPage::_GetAppAndArgs(ushort *,unsigned __int64,ushort * *)
0x180012a6b  mov     rdi, [rsp+490h+Block]
0x180012a70  test    rdi, rdi
0x180012a73  jz      loc_180012B96
0x180012a79  lea     rcx, [rbx+8Ch]; unsigned __int16 *
0x180012a80  call    ?IsLocalFilename@@YAHPEBG@Z; IsLocalFilename(ushort const *)
0x180012a85  test    eax, eax
0x180012a87  jz      loc_180012B6D
0x180012a8d  lea     rdx, [rbp+390h+var_250]; unsigned __int16 *
0x180012a94  mov     rcx, rbx; this
0x180012a97  call    ?_ExpandAppName@CGeneralPage@@AEAAXPEAG_K@Z; CGeneralPage::_ExpandAppName(ushort *,unsigned __int64)
0x180012a9c  or      dword ptr [rbx+2B8h], 10h
0x180012aa3  lea     rdx, [rbp+390h+var_250]; unsigned __int16 *
0x180012aaa  mov     rcx, rbx; this
0x180012aad  call    ?_UpdateAppIcon@CGeneralPage@@AEAAXPEBG@Z; CGeneralPage::_UpdateAppIcon(ushort const *)
0x180012ab2  mov     rcx, [rbx+70h]; hDlg
0x180012ab6  lea     r8, [rsp+490h+String]; lpString
0x180012abb  mov     r9d, 105h; cchMax
0x180012ac1  mov     edx, 683h; nIDDlgItem
0x180012ac6  call    cs:__imp_GetDlgItemTextW
0x180012acc  lea     rcx, [rsp+490h+String]; unsigned __int16 *
0x180012ad1  call    ?StripLeadTrailSpace@@YAXPEAG@Z; StripLeadTrailSpace(ushort *)
0x180012ad6  lea     rcx, [rsp+490h+String]; unsigned __int16 *
0x180012adb  call    ?DeleteQuotes@@YAXPEAG@Z; DeleteQuotes(ushort *)
0x180012ae0  cmp     [rsp+490h+String], r12w
0x180012ae6  jnz     short loc_180012B54
0x180012ae8  lea     rcx, [rbp+390h+var_250]; unsigned __int16 *
0x180012aef  call    ?IsLocalFilename@@YAHPEBG@Z; IsLocalFilename(ushort const *)
0x180012af4  test    eax, eax
0x180012af6  jz      short loc_180012B54
0x180012af8  lea     r8, [rbp+390h+var_250]; unsigned __int16 *
0x180012aff  mov     edx, 105h; unsigned __int64
0x180012b04  lea     rcx, [rsp+490h+String]; unsigned __int16 *
0x180012b09  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012b0e  lea     rcx, [rsp+490h+String]; unsigned __int16 *
0x180012b13  call    ?DeleteQuotes@@YAXPEAG@Z; DeleteQuotes(ushort *)
0x180012b18  lea     rcx, [rsp+490h+String]; pszPath
0x180012b1d  call    cs:__imp_PathRemoveFileSpecW
0x180012b23  lea     rcx, [rsp+490h+String]; unsigned __int16 *
0x180012b28  call    ?HasSpacesW@@YAHPEBG@Z; HasSpacesW(ushort const *)
0x180012b2d  test    eax, eax
0x180012b2f  jz      short loc_180012B40
0x180012b31  mov     edx, 105h; unsigned int
0x180012b36  lea     rcx, [rsp+490h+String]; Src
0x180012b3b  call    ?AddQuotes@@YAXPEAGK@Z; AddQuotes(ushort *,ulong)
0x180012b40  mov     rcx, [rbx+70h]; hDlg
0x180012b44  lea     r8, [rsp+490h+String]; lpString
0x180012b49  mov     edx, 683h; nIDDlgItem
0x180012b4e  call    cs:__imp_SetDlgItemTextW
0x180012b54  or      dword ptr [rbx+2B8h], 20h
0x180012b5b  lea     rdx, [rbp+390h+var_250]; unsigned __int16 *
0x180012b62  mov     r8, rdi; unsigned __int16 *
0x180012b65  mov     rcx, rbx; this
0x180012b68  call    ?_SetAppEdit@CGeneralPage@@AEAAXPEBG0@Z; CGeneralPage::_SetAppEdit(ushort const *,ushort const *)
0x180012b6d  test    r14, r14
0x180012b70  jz      short loc_180012B84
0x180012b72  lea     r8, [rbp+390h+var_250]; unsigned __int16 *
0x180012b79  mov     rdx, r15; unsigned __int64
0x180012b7c  mov     rcx, r14; unsigned __int16 *
0x180012b7f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180012b84  test    rsi, rsi
0x180012b87  jz      short loc_180012B8E
0x180012b89  mov     [rsi], rdi
0x180012b8c  jmp     short loc_180012B96
0x180012b8e  mov     rcx, rdi; Block
0x180012b91  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012b96  mov     rcx, [rbp+390h+var_40]
0x180012b9d  xor     rcx, rsp; StackCookie
0x180012ba0  call    __security_check_cookie
0x180012ba5  add     rsp, 460h
0x180012bac  pop     r15
0x180012bae  pop     r14
0x180012bb0  pop     r12
0x180012bb2  pop     rdi
0x180012bb3  pop     rsi
0x180012bb4  pop     rbx
0x180012bb5  pop     rbp
0x180012bb6  retn
```
