# CIntlAdvancedDlg::_CopySettings_DlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180009870`
- end: `0x180009a0b`
- name: `?_CopySettings_DlgProc@CIntlAdvancedDlg@@AEAAHPEAUHWND__@@I_K_J@Z`
- size: `411`
- prototype: `__int64 __usercall@<rax>(CIntlAdvancedDlg *__hidden this@<rcx>, HWND@<rdx>, unsigned int@<r8d>, unsigned __int64@<r9>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18000a3c0`

## callees

- `0x1800096fc`
- `0x180009870`
- `0x180009a14`
- `0x180009ca0`
- `0x180012f38`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800099f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800099f6`
- `USER32!SetWindowLongPtrW` at `0x18000999c`
- `USER32!SetWindowLongPtrW` at `0x18000999c`
- `USER32!GetDlgItem` at `0x1800099bc`
- `USER32!GetDlgItem` at `0x1800099d8`
- `USER32!GetDlgItem` at `0x1800099bc`
- `USER32!GetDlgItem` at `0x1800099d8`
- `USER32!EndDialog` at `0x180009983`
- `USER32!EndDialog` at `0x180009983`
- `USER32!ShowWindow` at `0x1800099c7`
- `USER32!ShowWindow` at `0x1800099e3`
- `USER32!ShowWindow` at `0x1800099c7`
- `USER32!ShowWindow` at `0x1800099e3`
- `USER32!IsDlgButtonChecked` at `0x1800098e3`
- `USER32!IsDlgButtonChecked` at `0x180009931`
- `USER32!IsDlgButtonChecked` at `0x1800098e3`
- `USER32!IsDlgButtonChecked` at `0x180009931`

## pseudocode

```c
__int64 __fastcall CIntlAdvancedDlg::_CopySettings_DlgProc(
        CIntlAdvancedDlg *this,
        HWND a2,
        int a3,
        int a4,
        LONG_PTR dwNewLong)
{
  int v7; // r8d
  int v8; // r8d
  int v10; // ebx
  UINT v11; // eax
  BOOL v12; // r8d
  int v13; // ebx
  UINT v14; // eax
  int *v15; // r8
  BOOL v16; // r9d
  int v17; // ebx
  HWND DlgItem; // rax
  HWND v19; // rax
  void *v20; // rcx

  v7 = a3 - 2;
  if ( !v7 )
  {
    v20 = (void *)*((_QWORD *)this + 2);
    if ( v20 )
    {
      operator delete(v20);
      *((_QWORD *)this + 2) = 0;
    }
    return 1;
  }
  v8 = v7 - 270;
  if ( !v8 )
  {
    *(_QWORD *)((char *)this + 4) = 0;
    SetWindowLongPtrW(a2, 16, dwNewLong);
    Input_LoadAndInitFunctions();
    CIntlAdvancedDlg::_CopySettings_InitListView(this, a2);
    v17 = *(_DWORD *)this;
    DlgItem = GetDlgItem(a2, 1026);
    ShowWindow(DlgItem, v17);
    v13 = *((_DWORD *)this + 3);
LABEL_27:
    v19 = GetDlgItem(a2, 3040);
    ShowWindow(v19, v13);
    return 1;
  }
  if ( v8 != 1 )
    return 0;
  if ( (unsigned __int16)a4 == 1 )
  {
    CIntlAdvancedDlg::_CopySettings_ApplyChanges(this, a2);
    goto LABEL_25;
  }
  if ( (unsigned __int16)a4 == 2 )
  {
LABEL_25:
    EndDialog(a2, 1);
    return 1;
  }
  if ( (unsigned __int16)a4 != 1054 )
  {
    if ( (unsigned __int16)a4 == 1055 )
    {
      v10 = 0;
      if ( !HIWORD(a4) )
      {
        v11 = IsDlgButtonChecked(a2, 1055);
        v12 = v11 == 1;
        *((_DWORD *)this + 2) = v12;
        if ( *((_DWORD *)this + 1) || v11 == 1 && *((_DWORD *)this + 3) )
          v10 = 1;
        CIntlAdvancedDlg::_CopySettings_UpdateListView((CAccountListView **)this, a2, v12, v10);
      }
    }
    return 1;
  }
  v13 = 0;
  if ( !HIWORD(a4) )
  {
    v14 = IsDlgButtonChecked(a2, 1054);
    v15 = (int *)((char *)this + 8);
    *((_DWORD *)this + 1) = v14 == 1;
    v16 = v14 == 1 || *v15 && *((_DWORD *)this + 3);
    CIntlAdvancedDlg::_CopySettings_UpdateListView((CAccountListView **)this, a2, *v15, v16);
    if ( *((_DWORD *)this + 3) && !*((_DWORD *)this + 1) )
      v13 = 1;
    goto LABEL_27;
  }
  return 1;
}

```

## disassembly

```asm
0x180009870  push    rbx
0x180009872  push    rbp
0x180009873  push    rsi
0x180009874  push    rdi
0x180009875  sub     rsp, 28h
0x180009879  mov     rsi, rdx
0x18000987c  mov     rdi, rcx
0x18000987f  mov     ebp, 1
0x180009884  sub     r8d, 2
0x180009888  jz      loc_1800099EB
0x18000988e  sub     r8d, 10Eh
0x180009895  jz      loc_18000998B
0x18000989b  cmp     r8d, ebp
0x18000989e  jz      short loc_1800098A7
0x1800098a0  xor     eax, eax
0x1800098a2  jmp     loc_180009A02
0x1800098a7  movzx   ecx, r9w
0x1800098ab  sub     ecx, ebp
0x1800098ad  jz      loc_180009975
0x1800098b3  sub     ecx, ebp
0x1800098b5  jz      loc_18000997D
0x1800098bb  sub     ecx, 41Ch
0x1800098c1  jz      short loc_180009919
0x1800098c3  cmp     ecx, ebp
0x1800098c5  jnz     loc_180009A00
0x1800098cb  shr     r9, 10h
0x1800098cf  xor     ebx, ebx
0x1800098d1  test    r9w, r9w
0x1800098d5  jnz     loc_180009A00
0x1800098db  mov     edx, 41Fh; nIDButton
0x1800098e0  mov     rcx, rsi; hDlg
0x1800098e3  call    cs:__imp_IsDlgButtonChecked
0x1800098e9  cmp     eax, ebp
0x1800098eb  mov     r8d, ebx
0x1800098ee  setz    r8b; int
0x1800098f2  mov     [rdi+8], r8d
0x1800098f6  cmp     [rdi+4], ebx
0x1800098f9  jnz     short loc_180009904
0x1800098fb  cmp     eax, ebp
0x1800098fd  jnz     short loc_180009906
0x1800098ff  cmp     [rdi+0Ch], ebx
0x180009902  jz      short loc_180009906
0x180009904  mov     ebx, ebp
0x180009906  mov     r9d, ebx; int
0x180009909  mov     rdx, rsi; HWND
0x18000990c  mov     rcx, rdi; this
0x18000990f  call    ?_CopySettings_UpdateListView@CIntlAdvancedDlg@@AEAAXPEAUHWND__@@HH@Z; CIntlAdvancedDlg::_CopySettings_UpdateListView(HWND__ *,int,int)
0x180009914  jmp     loc_180009A00
0x180009919  shr     r9, 10h
0x18000991d  xor     ebx, ebx
0x18000991f  test    r9w, r9w
0x180009923  jnz     loc_180009A00
0x180009929  mov     edx, 41Eh; nIDButton
0x18000992e  mov     rcx, rsi; hDlg
0x180009931  call    cs:__imp_IsDlgButtonChecked
0x180009937  cmp     eax, ebp
0x180009939  lea     r8, [rdi+8]
0x18000993d  mov     eax, ebx
0x18000993f  setz    al
0x180009942  mov     [rdi+4], eax
0x180009945  jz      short loc_180009956
0x180009947  cmp     [r8], ebx
0x18000994a  jz      short loc_180009951
0x18000994c  cmp     [rdi+0Ch], ebx
0x18000994f  jnz     short loc_180009956
0x180009951  mov     r9d, ebx
0x180009954  jmp     short loc_180009959
0x180009956  mov     r9d, ebp; int
0x180009959  mov     r8d, [r8]; int
0x18000995c  mov     rdx, rsi; HWND
0x18000995f  mov     rcx, rdi; this
0x180009962  call    ?_CopySettings_UpdateListView@CIntlAdvancedDlg@@AEAAXPEAUHWND__@@HH@Z; CIntlAdvancedDlg::_CopySettings_UpdateListView(HWND__ *,int,int)
0x180009967  cmp     [rdi+0Ch], ebx
0x18000996a  jz      short loc_1800099D0
0x18000996c  cmp     [rdi+4], ebx
0x18000996f  jnz     short loc_1800099D0
0x180009971  mov     ebx, ebp
0x180009973  jmp     short loc_1800099D0
0x180009975  mov     rcx, rdi; this
0x180009978  call    ?_CopySettings_ApplyChanges@CIntlAdvancedDlg@@AEAAXPEAUHWND__@@@Z; CIntlAdvancedDlg::_CopySettings_ApplyChanges(HWND__ *)
0x18000997d  mov     rdx, rbp; nResult
0x180009980  mov     rcx, rsi; hDlg
0x180009983  call    cs:__imp_EndDialog
0x180009989  jmp     short loc_180009A00
0x18000998b  mov     r8, [rsp+48h+dwNewLong]; dwNewLong
0x180009990  xor     ebx, ebx
0x180009992  mov     [rcx+4], rbx
0x180009996  mov     rcx, rsi; hWnd
0x180009999  lea     edx, [rbx+10h]; nIndex
0x18000999c  call    cs:__imp_SetWindowLongPtrW
0x1800099a2  call    ?Input_LoadAndInitFunctions@@YAHXZ; Input_LoadAndInitFunctions(void)
0x1800099a7  mov     rdx, rsi; HWND
0x1800099aa  mov     rcx, rdi; this
0x1800099ad  call    ?_CopySettings_InitListView@CIntlAdvancedDlg@@AEAAHPEAUHWND__@@@Z; CIntlAdvancedDlg::_CopySettings_InitListView(HWND__ *)
0x1800099b2  mov     ebx, [rdi]
0x1800099b4  mov     edx, 402h; nIDDlgItem
0x1800099b9  mov     rcx, rsi; hDlg
0x1800099bc  call    cs:__imp_GetDlgItem
0x1800099c2  mov     rcx, rax; hWnd
0x1800099c5  mov     edx, ebx; nCmdShow
0x1800099c7  call    cs:__imp_ShowWindow
0x1800099cd  mov     ebx, [rdi+0Ch]
0x1800099d0  mov     edx, 0BE0h; nIDDlgItem
0x1800099d5  mov     rcx, rsi; hDlg
0x1800099d8  call    cs:__imp_GetDlgItem
0x1800099de  mov     rcx, rax; hWnd
0x1800099e1  mov     edx, ebx; nCmdShow
0x1800099e3  call    cs:__imp_ShowWindow
0x1800099e9  jmp     short loc_180009A00
0x1800099eb  mov     rcx, [rcx+10h]
0x1800099ef  xor     ebx, ebx
0x1800099f1  test    rcx, rcx
0x1800099f4  jz      short loc_180009A00
0x1800099f6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800099fc  mov     [rdi+10h], rbx
0x180009a00  mov     eax, ebp
0x180009a02  add     rsp, 28h
0x180009a06  pop     rdi
0x180009a07  pop     rsi
0x180009a08  pop     rbp
0x180009a09  pop     rbx
0x180009a0a  retn
```
