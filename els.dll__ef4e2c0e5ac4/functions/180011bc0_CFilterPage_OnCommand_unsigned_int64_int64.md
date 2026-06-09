# CFilterPage::_OnCommand(unsigned __int64,__int64)

- ea: `0x180011bc0`
- end: `0x180011d71`
- name: `?_OnCommand@CFilterPage@@MEAAK_K_J@Z`
- size: `433`
- prototype: `unsigned int __fastcall(CFilterPage *__hidden this, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180011a7c`
- `0x180011bc0`
- `0x1800121ac`
- `0x180019224`
- `0x18001edf0`
- `0x180020c08`
- `0x180020ce4`
- `0x1800222d0`

## import_xrefs

- `USER32!SendMessageW` at `0x180011c50`
- `USER32!SendMessageW` at `0x180011c50`
- `USER32!GetDlgItem` at `0x180011c3c`
- `USER32!GetDlgItem` at `0x180011d01`
- `USER32!GetDlgItem` at `0x180011c3c`
- `USER32!GetDlgItem` at `0x180011d01`
- `USER32!GetWindowTextW` at `0x180011d15`
- `USER32!GetWindowTextW` at `0x180011d15`

## pseudocode

```c
__int64 __fastcall CFilterPage::_OnCommand(HWND *this, unsigned __int64 a2)
{
  int v2; // ebx
  unsigned __int64 v4; // rdx
  HWND v5; // rax
  LRESULT v6; // rax
  __int16 v7; // ax
  unsigned __int64 v8; // rdx
  HWND DlgItem; // rax
  WCHAR String[264]; // [rsp+20h] [rbp-228h] BYREF

  v2 = (unsigned __int16)a2;
  if ( (unsigned __int16)a2 > 0x7Bu )
  {
    if ( (unsigned __int16)a2 == 125 )
    {
      v8 = a2 >> 16;
      if ( (_WORD)v8 == 1 )
      {
        CPropSheetPage::_EnableApply((CPropSheetPage *)this, v8);
        DlgItem = GetDlgItem(this[2], 125);
        GetWindowTextW(DlgItem, String, 260);
        SetCategoryCombobox(this[2], (struct CSources *)(this[5] + 1196), String, 0);
        SetTypesCheckboxes(this[2], (struct CSources *)(this[5] + 1196), 0x1Fu);
      }
      return 0;
    }
    if ( (unsigned __int16)a2 == 127 )
    {
      v7 = 1;
    }
    else
    {
      if ( (unsigned __int16)a2 != 129 && (unsigned __int16)a2 != 131 && (unsigned __int16)a2 != 133 )
      {
        if ( (unsigned __int16)a2 == 134 )
        {
          CPropSheetPage::_EnableApply((CPropSheetPage *)this, a2);
          CFilterPage::_SetFromTo(this, 0, 0);
          CFilterPage::_SetFromTo(this, 1, 0);
          ClearFindOrFilterDlg(this[2], (struct CSources *)(this[5] + 1196));
        }
        return 0;
      }
      v7 = 768;
    }
    a2 >>= 16;
    if ( (_WORD)a2 != v7 )
      return 0;
LABEL_21:
    CPropSheetPage::_EnableApply((CPropSheetPage *)this, a2);
    return 0;
  }
  if ( (unsigned __int16)a2 == 123 )
    goto LABEL_21;
  if ( (unsigned __int16)a2 == 111 || (unsigned __int16)a2 == 115 )
  {
    v4 = a2 >> 16;
    if ( (_WORD)v4 == 1 )
    {
      CPropSheetPage::_EnableApply((CPropSheetPage *)this, v4);
      v5 = GetDlgItem(this[2], v2);
      v6 = SendMessageW(v5, 0x147u, 0, 0);
      CFilterPage::_EnableDateTime(this, v2 != 111, v6);
    }
  }
  else if ( (unsigned __int16)a2 == 119 || (unsigned __int16)a2 == 120 || (unsigned int)(unsigned __int16)a2 - 121 <= 1 )
  {
    goto LABEL_21;
  }
  return 0;
}

```

## disassembly

```asm
0x180011bc0  mov     [rsp+arg_10], rbx
0x180011bc5  push    rdi
0x180011bc6  sub     rsp, 240h
0x180011bcd  mov     rax, cs:__security_cookie
0x180011bd4  xor     rax, rsp
0x180011bd7  mov     [rsp+248h+var_18], rax
0x180011bdf  movzx   ebx, dx
0x180011be2  mov     rdi, rcx
0x180011be5  cmp     ebx, 7Bh ; '{'
0x180011be8  ja      loc_180011C6E
0x180011bee  jz      short loc_180011C14
0x180011bf0  mov     ecx, ebx
0x180011bf2  sub     ecx, 6Fh ; 'o'
0x180011bf5  jz      short loc_180011C1C
0x180011bf7  sub     ecx, 4
0x180011bfa  jz      short loc_180011C1C
0x180011bfc  sub     ecx, 4
0x180011bff  jz      short loc_180011C14
0x180011c01  sub     ecx, 1
0x180011c04  jz      short loc_180011C14
0x180011c06  sub     ecx, 1
0x180011c09  jz      short loc_180011C14
0x180011c0b  cmp     ecx, 1
0x180011c0e  jnz     loc_180011D4E
0x180011c14  mov     rcx, rdi
0x180011c17  jmp     loc_180011CDE
0x180011c1c  shr     rdx, 10h; int
0x180011c20  mov     eax, 1
0x180011c25  cmp     dx, ax
0x180011c28  jnz     loc_180011D4E
0x180011c2e  mov     rcx, rdi; this
0x180011c31  call    ?_EnableApply@CPropSheetPage@@IEAAXH@Z; CPropSheetPage::_EnableApply(int)
0x180011c36  mov     rcx, [rdi+10h]; hDlg
0x180011c3a  mov     edx, ebx; nIDDlgItem
0x180011c3c  call    cs:__imp_GetDlgItem
0x180011c42  xor     r9d, r9d; lParam
0x180011c45  xor     r8d, r8d; wParam
0x180011c48  mov     rcx, rax; hWnd
0x180011c4b  mov     edx, 147h; Msg
0x180011c50  call    cs:__imp_SendMessageW
0x180011c56  xor     edx, edx
0x180011c58  mov     rcx, rdi
0x180011c5b  cmp     ebx, 6Fh ; 'o'
0x180011c5e  mov     r8, rax
0x180011c61  setnz   dl
0x180011c64  call    ?_EnableDateTime@CFilterPage@@AEAAXW4FROMTO@@H@Z; CFilterPage::_EnableDateTime(FROMTO,int)
0x180011c69  jmp     loc_180011D4E
0x180011c6e  sub     ebx, 7Dh ; '}'
0x180011c71  jz      short loc_180011CE5
0x180011c73  sub     ebx, 2
0x180011c76  jz      short loc_180011CD0
0x180011c78  sub     ebx, 2
0x180011c7b  jz      short loc_180011CC9
0x180011c7d  sub     ebx, 2
0x180011c80  jz      short loc_180011CC9
0x180011c82  sub     ebx, 2
0x180011c85  jz      short loc_180011CC9
0x180011c87  cmp     ebx, 1
0x180011c8a  jnz     loc_180011D4E
0x180011c90  call    ?_EnableApply@CPropSheetPage@@IEAAXH@Z; CPropSheetPage::_EnableApply(int)
0x180011c95  xor     r8d, r8d
0x180011c98  xor     edx, edx
0x180011c9a  mov     rcx, rdi
0x180011c9d  call    ?_SetFromTo@CFilterPage@@AEAAXW4FROMTO@@PEAU_SYSTEMTIME@@@Z; CFilterPage::_SetFromTo(FROMTO,_SYSTEMTIME *)
0x180011ca2  xor     r8d, r8d
0x180011ca5  mov     edx, ebx
0x180011ca7  mov     rcx, rdi
0x180011caa  call    ?_SetFromTo@CFilterPage@@AEAAXW4FROMTO@@PEAU_SYSTEMTIME@@@Z; CFilterPage::_SetFromTo(FROMTO,_SYSTEMTIME *)
0x180011caf  mov     rdx, [rdi+28h]
0x180011cb3  mov     ebx, 12B0h
0x180011cb8  mov     rcx, [rdi+10h]; HWND
0x180011cbc  add     rdx, rbx; struct CSources *
0x180011cbf  call    ?ClearFindOrFilterDlg@@YAXPEAUHWND__@@PEAVCSources@@@Z; ClearFindOrFilterDlg(HWND__ *,CSources *)
0x180011cc4  jmp     loc_180011D4E
0x180011cc9  mov     eax, 300h
0x180011cce  jmp     short loc_180011CD5
0x180011cd0  mov     eax, 1
0x180011cd5  shr     rdx, 10h; int
0x180011cd9  cmp     dx, ax
0x180011cdc  jnz     short loc_180011D4E
0x180011cde  call    ?_EnableApply@CPropSheetPage@@IEAAXH@Z; CPropSheetPage::_EnableApply(int)
0x180011ce3  jmp     short loc_180011D4E
0x180011ce5  shr     rdx, 10h; int
0x180011ce9  mov     eax, 1
0x180011cee  cmp     dx, ax
0x180011cf1  jnz     short loc_180011D4E
0x180011cf3  call    ?_EnableApply@CPropSheetPage@@IEAAXH@Z; CPropSheetPage::_EnableApply(int)
0x180011cf8  mov     rcx, [rdi+10h]; hDlg
0x180011cfc  mov     edx, 7Dh ; '}'; nIDDlgItem
0x180011d01  call    cs:__imp_GetDlgItem
0x180011d07  mov     r8d, 104h; nMaxCount
0x180011d0d  lea     rdx, [rsp+248h+String]; lpString
0x180011d12  mov     rcx, rax; hWnd
0x180011d15  call    cs:__imp_GetWindowTextW
0x180011d1b  mov     rdx, [rdi+28h]
0x180011d1f  lea     r8, [rsp+248h+String]; unsigned __int16 *
0x180011d24  mov     rcx, [rdi+10h]; HWND
0x180011d28  mov     ebx, 12B0h
0x180011d2d  add     rdx, rbx; struct CSources *
0x180011d30  xor     r9d, r9d; unsigned __int16
0x180011d33  call    ?SetCategoryCombobox@@YAXPEAUHWND__@@PEAVCSources@@PEBGG@Z; SetCategoryCombobox(HWND__ *,CSources *,ushort const *,ushort)
0x180011d38  mov     rdx, [rdi+28h]
0x180011d3c  mov     r8d, 1Fh; unsigned int
0x180011d42  mov     rcx, [rdi+10h]; hDlg
0x180011d46  add     rdx, rbx; this
0x180011d49  call    ?SetTypesCheckboxes@@YAXPEAUHWND__@@PEAVCSources@@K@Z; SetTypesCheckboxes(HWND__ *,CSources *,ulong)
0x180011d4e  xor     eax, eax
0x180011d50  mov     rcx, [rsp+248h+var_18]
0x180011d58  xor     rcx, rsp; StackCookie
0x180011d5b  call    __security_check_cookie
0x180011d60  mov     rbx, [rsp+248h+arg_10]
0x180011d68  add     rsp, 240h
0x180011d6f  pop     rdi
0x180011d70  retn
```
