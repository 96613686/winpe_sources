# XBytes::SetBytes(__int64)

- ea: `0x18001b3b0`
- end: `0x18001b524`
- name: `?SetBytes@XBytes@@QEAAX_J@Z`
- size: `372`
- prototype: `void __fastcall(XBytes *__hidden this, __int64)`
- caller_count: `12`
- callee_count: `4`
- tags: ``

## callers

- `0x180006848`
- `0x180006a38`
- `0x180006c54`
- `0x1800177fc`
- `0x180017b7c`
- `0x1800180a8`
- `0x1800191e8`
- `0x1800196b0`
- `0x18001add0`
- `0x18001b120`
- `0x18001b1e0`
- `0x18001b26c`

## callees

- `0x180001510`
- `0x18001aeb4`
- `0x18001b014`
- `0x18001b3b0`

## import_xrefs

- `USER32!EnableWindow` at `0x18001b48f`
- `USER32!EnableWindow` at `0x18001b4ee`
- `USER32!EnableWindow` at `0x18001b506`
- `USER32!EnableWindow` at `0x18001b48f`
- `USER32!EnableWindow` at `0x18001b4ee`
- `USER32!EnableWindow` at `0x18001b506`
- `USER32!SendMessageW` at `0x18001b460`
- `USER32!SendMessageW` at `0x18001b4c2`
- `USER32!SendMessageW` at `0x18001b460`
- `USER32!SendMessageW` at `0x18001b4c2`
- `USER32!SetDlgItemTextW` at `0x18001b472`
- `USER32!SetDlgItemTextW` at `0x18001b4d6`
- `USER32!SetDlgItemTextW` at `0x18001b472`
- `USER32!SetDlgItemTextW` at `0x18001b4d6`
- `USER32!GetDlgItem` at `0x18001b44c`
- `USER32!GetDlgItem` at `0x18001b47f`
- `USER32!GetDlgItem` at `0x18001b49c`
- `USER32!GetDlgItem` at `0x18001b4ad`
- `USER32!GetDlgItem` at `0x18001b4e3`
- `USER32!GetDlgItem` at `0x18001b4fb`
- `USER32!GetDlgItem` at `0x18001b44c`
- `USER32!GetDlgItem` at `0x18001b47f`
- `USER32!GetDlgItem` at `0x18001b49c`
- `USER32!GetDlgItem` at `0x18001b4ad`
- `USER32!GetDlgItem` at `0x18001b4e3`
- `USER32!GetDlgItem` at `0x18001b4fb`

## pseudocode

```c
void __fastcall XBytes::SetBytes(XBytes *this, __int64 a2)
{
  __int64 v2; // r9
  __int64 v4; // rax
  unsigned int v5; // eax
  int v6; // eax
  WPARAM v7; // rbx
  HWND v8; // rax
  HWND v9; // rax
  HWND v10; // rax
  BOOL v11; // edx
  HWND DlgItem; // rax
  HWND v13; // rax
  unsigned int v14; // [rsp+20h] [rbp-38h] BYREF
  int v15; // [rsp+24h] [rbp-34h] BYREF
  WCHAR String[16]; // [rsp+28h] [rbp-30h] BYREF

  v2 = a2;
  if ( a2 != -1 )
  {
    v4 = 1024;
    if ( a2 >= 1024 )
      v4 = a2;
    v2 = v4;
  }
  if ( v2 > 0x6000000000000000LL )
    v2 = 0x6000000000000000LL;
  *(_QWORD *)this = v2;
  v15 = 0;
  if ( v2 == -1 )
  {
    DlgItem = GetDlgItem(*((HWND *)this + 1), *((_DWORD *)this + 5));
    SendMessageW(DlgItem, 0x14Eu, 0xFFFFFFFFFFFFFFFFuLL, 0);
    SetDlgItemTextW(*((HWND *)this + 1), *((_DWORD *)this + 4), &XBytes::m_szNoLimit);
    v13 = GetDlgItem(*((HWND *)this + 1), *((_DWORD *)this + 5));
    EnableWindow(v13, 0);
    v10 = GetDlgItem(*((HWND *)this + 1), *((_DWORD *)this + 4));
    v11 = 0;
  }
  else
  {
    v14 = 0;
    v5 = XBytes::BytesToParts(v2, &v14, &v15);
    XBytes::FormatForDisplay(String, 0x10u, v5, v14);
    v6 = v15;
    if ( !*(_QWORD *)this )
      v6 = 2;
    v7 = v6 - 1;
    v8 = GetDlgItem(*((HWND *)this + 1), *((_DWORD *)this + 5));
    SendMessageW(v8, 0x14Eu, v7, 0);
    SetDlgItemTextW(*((HWND *)this + 1), *((_DWORD *)this + 4), String);
    v9 = GetDlgItem(*((HWND *)this + 1), *((_DWORD *)this + 5));
    EnableWindow(v9, 1);
    v10 = GetDlgItem(*((HWND *)this + 1), *((_DWORD *)this + 4));
    v11 = 1;
  }
  EnableWindow(v10, v11);
}

```

## disassembly

```asm
0x18001b3b0  mov     [rsp+arg_8], rbx
0x18001b3b5  push    rdi
0x18001b3b6  sub     rsp, 50h
0x18001b3ba  mov     rax, cs:__security_cookie
0x18001b3c1  xor     rax, rsp
0x18001b3c4  mov     [rsp+58h+var_10], rax
0x18001b3c9  mov     r9, rdx
0x18001b3cc  mov     rdi, rcx
0x18001b3cf  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001b3d3  jz      short loc_18001B3E4
0x18001b3d5  mov     eax, 400h
0x18001b3da  cmp     rdx, rax
0x18001b3dd  cmovge  rax, rdx
0x18001b3e1  mov     r9, rax
0x18001b3e4  mov     rax, 6000000000000000h
0x18001b3ee  cmp     r9, rax
0x18001b3f1  cmovg   r9, rax
0x18001b3f5  xor     ebx, ebx
0x18001b3f7  mov     [rcx], r9
0x18001b3fa  mov     [rsp+58h+var_34], ebx
0x18001b3fe  cmp     r9, 0FFFFFFFFFFFFFFFFh
0x18001b402  jz      loc_18001B4A6
0x18001b408  lea     r8, [rsp+58h+var_34]; int *
0x18001b40d  mov     [rsp+58h+var_38], ebx
0x18001b411  lea     rdx, [rsp+58h+var_38]; unsigned int *
0x18001b416  mov     rcx, r9; __int64
0x18001b419  call    ?BytesToParts@XBytes@@SAK_JPEAKPEAH@Z; XBytes::BytesToParts(__int64,ulong *,int *)
0x18001b41e  mov     r9d, [rsp+58h+var_38]; unsigned int
0x18001b423  lea     edx, [rbx+10h]; unsigned int
0x18001b426  mov     r8d, eax; unsigned int
0x18001b429  lea     rcx, [rsp+58h+String]; unsigned __int16 *
0x18001b42e  call    ?FormatForDisplay@XBytes@@CAXPEAGIKK@Z; XBytes::FormatForDisplay(ushort *,uint,ulong,ulong)
0x18001b433  cmp     [rdi], rbx
0x18001b436  lea     ecx, [rbx+2]
0x18001b439  mov     eax, [rsp+58h+var_34]
0x18001b43d  mov     edx, [rdi+14h]; nIDDlgItem
0x18001b440  cmovz   eax, ecx
0x18001b443  mov     rcx, [rdi+8]; hDlg
0x18001b447  dec     eax
0x18001b449  movsxd  rbx, eax
0x18001b44c  call    cs:__imp_GetDlgItem
0x18001b452  xor     r9d, r9d; lParam
0x18001b455  mov     r8, rbx; wParam
0x18001b458  mov     rcx, rax; hWnd
0x18001b45b  mov     edx, 14Eh; Msg
0x18001b460  call    cs:__imp_SendMessageW
0x18001b466  mov     edx, [rdi+10h]; nIDDlgItem
0x18001b469  lea     r8, [rsp+58h+String]; lpString
0x18001b46e  mov     rcx, [rdi+8]; hDlg
0x18001b472  call    cs:__imp_SetDlgItemTextW
0x18001b478  mov     edx, [rdi+14h]; nIDDlgItem
0x18001b47b  mov     rcx, [rdi+8]; hDlg
0x18001b47f  call    cs:__imp_GetDlgItem
0x18001b485  mov     ebx, 1
0x18001b48a  mov     rcx, rax; hWnd
0x18001b48d  mov     edx, ebx; bEnable
0x18001b48f  call    cs:__imp_EnableWindow
0x18001b495  mov     edx, [rdi+10h]; nIDDlgItem
0x18001b498  mov     rcx, [rdi+8]; hDlg
0x18001b49c  call    cs:__imp_GetDlgItem
0x18001b4a2  mov     edx, ebx
0x18001b4a4  jmp     short loc_18001B503
0x18001b4a6  mov     edx, [rcx+14h]; nIDDlgItem
0x18001b4a9  mov     rcx, [rcx+8]; hDlg
0x18001b4ad  call    cs:__imp_GetDlgItem
0x18001b4b3  xor     r9d, r9d; lParam
0x18001b4b6  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x18001b4ba  mov     rcx, rax; hWnd
0x18001b4bd  mov     edx, 14Eh; Msg
0x18001b4c2  call    cs:__imp_SendMessageW
0x18001b4c8  mov     edx, [rdi+10h]; nIDDlgItem
0x18001b4cb  lea     r8, ?m_szNoLimit@XBytes@@0PAGA; lpString
0x18001b4d2  mov     rcx, [rdi+8]; hDlg
0x18001b4d6  call    cs:__imp_SetDlgItemTextW
0x18001b4dc  mov     edx, [rdi+14h]; nIDDlgItem
0x18001b4df  mov     rcx, [rdi+8]; hDlg
0x18001b4e3  call    cs:__imp_GetDlgItem
0x18001b4e9  mov     rcx, rax; hWnd
0x18001b4ec  xor     edx, edx; bEnable
0x18001b4ee  call    cs:__imp_EnableWindow
0x18001b4f4  mov     edx, [rdi+10h]; nIDDlgItem
0x18001b4f7  mov     rcx, [rdi+8]; hDlg
0x18001b4fb  call    cs:__imp_GetDlgItem
0x18001b501  xor     edx, edx; bEnable
0x18001b503  mov     rcx, rax; hWnd
0x18001b506  call    cs:__imp_EnableWindow
0x18001b50c  mov     rcx, [rsp+58h+var_10]
0x18001b511  xor     rcx, rsp; StackCookie
0x18001b514  call    __security_check_cookie
0x18001b519  mov     rbx, [rsp+58h+arg_8]
0x18001b51e  add     rsp, 50h
0x18001b522  pop     rdi
0x18001b523  retn
```
