# VpnWizDialogProc

- ea: `0x180026010`
- end: `0x18002620a`
- name: `VpnWizDialogProc`
- size: `506`
- prototype: `__int64 __fastcall(HWND hDlg)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18002049c`
- `0x180020810`
- `0x180024c4c`
- `0x180025f54`
- `0x180026010`
- `0x1800262cc`
- `0x18002c598`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x180026110`
- `USER32!SetWindowLongPtrW` at `0x18002619a`
- `USER32!SetWindowLongPtrW` at `0x180026110`
- `USER32!SetWindowLongPtrW` at `0x18002619a`
- `USER32!PostMessageW` at `0x180026130`
- `USER32!PostMessageW` at `0x180026130`
- `USER32!ShowWindow` at `0x1800260bd`
- `USER32!ShowWindow` at `0x1800260bd`
- `USER32!IsDlgButtonChecked` at `0x18002615f`
- `USER32!IsDlgButtonChecked` at `0x18002615f`
- `USER32!GetDlgItem` at `0x1800260b2`
- `USER32!GetDlgItem` at `0x1800261ce`
- `USER32!GetDlgItem` at `0x1800260b2`
- `USER32!GetDlgItem` at `0x1800261ce`
- `USER32!SendMessageW` at `0x1800261e7`
- `USER32!SendMessageW` at `0x1800261e7`
- `USER32!GetParent` at `0x180026119`
- `USER32!GetParent` at `0x180026119`
- `USER32!GetWindowLongPtrW` at `0x1800260f5`
- `USER32!GetWindowLongPtrW` at `0x1800260f5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180026066`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180026066`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180026093`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002609c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180026093`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002609c`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180026083`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180026083`

## string_xrefs

- `0x180026077`: `sharedaccess`

## pseudocode

```c
__int64 __fastcall VpnWizDialogProc(HWND hDlg, int a2, __int64 a3, __int64 a4)
{
  int v9; // esi
  int v10; // esi
  SC_HANDLE v11; // rax
  SC_HANDLE v12; // rsi
  int v13; // ebp
  SC_HANDLE v14; // rax
  HWND v15; // rax
  HWND Parent; // rax
  int v17; // esi
  HWND DlgItem; // rax

  if ( (unsigned int)RasSrvMessageFilter(hDlg) )
    return 1;
  v9 = a2 - 78;
  if ( !v9 )
  {
    switch ( *(_DWORD *)(a4 + 16) )
    {
      case 0xFFFFFF35:
        VpnWizCancelEdit(hDlg);
        SetWindowLongPtrW(hDlg, 0, 0);
        break;
      case 0xFFFFFF37:
        v17 = IsServerOS();
        RasSrvGetDatabaseHandle(hDlg);
        IsDlgButtonChecked(hDlg, 7053);
        UserTabSaveEncryption(hDlg, v17 != 0);
        break;
      case 0xFFFFFF38:
        if ( !GetWindowLongPtrW(hDlg, -21) )
        {
          VpnWizInitializeDialog(hDlg);
          SetWindowLongPtrW(hDlg, -21, 1);
        }
        Parent = GetParent(hDlg);
        PostMessageW(Parent, 0x470u, 0, 3);
        break;
    }
LABEL_20:
    RasSrvGetDatabaseHandle(hDlg);
    if ( (unsigned __int64)(a3 - 7053) <= 1 )
    {
      DlgItem = GetDlgItem(hDlg, 7053);
      if ( DlgItem )
        SendMessageW(DlgItem, 0xF0u, 0, 0);
    }
    return 0;
  }
  v10 = v9 - 194;
  if ( !v10 )
  {
    v11 = OpenSCManagerW(0, 0, 0x20000u);
    v12 = v11;
    if ( !v11 )
      goto LABEL_11;
    v13 = 0;
    v14 = OpenServiceW(v11, L"sharedaccess", 1u);
    if ( v14 )
    {
      v13 = 1;
      CloseServiceHandle(v14);
    }
    CloseServiceHandle(v12);
    if ( !v13 )
    {
LABEL_11:
      v15 = GetDlgItem(hDlg, 7062);
      ShowWindow(v15, 0);
    }
    return 0;
  }
  if ( v10 == 1 )
    goto LABEL_20;
  return 0;
}

```

## disassembly

```asm
0x180026010  push    rbx
0x180026012  push    rbp
0x180026013  push    rsi
0x180026014  push    rdi
0x180026015  push    r14
0x180026017  sub     rsp, 30h
0x18002601b  mov     rbp, r9
0x18002601e  mov     r14, r8
0x180026021  mov     esi, edx
0x180026023  mov     rbx, rcx
0x180026026  call    RasSrvMessageFilter
0x18002602b  test    eax, eax
0x18002602d  jz      short loc_180026039
0x18002602f  mov     eax, 1
0x180026034  jmp     loc_1800261FF
0x180026039  mov     edi, 1
0x18002603e  sub     esi, 4Eh ; 'N'
0x180026041  jz      loc_1800260C8
0x180026047  sub     esi, 0C2h
0x18002604d  jz      short loc_18002605C
0x18002604f  cmp     esi, edi
0x180026051  jz      loc_1800261A0
0x180026057  jmp     loc_1800261FD
0x18002605c  xor     edx, edx; lpDatabaseName
0x18002605e  xor     ecx, ecx; lpMachineName
0x180026060  mov     r8d, 20000h; dwDesiredAccess
0x180026066  call    cs:__imp_OpenSCManagerW
0x18002606c  mov     rsi, rax
0x18002606f  test    rax, rax
0x180026072  jz      short loc_1800260AA
0x180026074  mov     r8d, edi; dwDesiredAccess
0x180026077  lea     rdx, ServiceName; "sharedaccess"
0x18002607e  mov     rcx, rax; hSCManager
0x180026081  xor     ebp, ebp
0x180026083  call    cs:__imp_OpenServiceW
0x180026089  test    rax, rax
0x18002608c  jz      short loc_180026099
0x18002608e  mov     rcx, rax; hSCObject
0x180026091  mov     ebp, edi
0x180026093  call    cs:__imp_CloseServiceHandle
0x180026099  mov     rcx, rsi; hSCObject
0x18002609c  call    cs:__imp_CloseServiceHandle
0x1800260a2  test    ebp, ebp
0x1800260a4  jnz     loc_1800261FD
0x1800260aa  mov     edx, 1B96h; nIDDlgItem
0x1800260af  mov     rcx, rbx; hDlg
0x1800260b2  call    cs:__imp_GetDlgItem
0x1800260b8  mov     rcx, rax; hWnd
0x1800260bb  xor     edx, edx; nCmdShow
0x1800260bd  call    cs:__imp_ShowWindow
0x1800260c3  jmp     loc_1800261FD
0x1800260c8  cmp     dword ptr [rbp+10h], 0FFFFFF35h
0x1800260cf  jz      loc_18002618A
0x1800260d5  cmp     dword ptr [rbp+10h], 0FFFFFF37h
0x1800260dc  jz      short loc_180026138
0x1800260de  cmp     dword ptr [rbp+10h], 0FFFFFF38h
0x1800260e5  jnz     loc_1800261A0
0x1800260eb  mov     esi, 0FFFFFFEBh
0x1800260f0  mov     rcx, rbx; hWnd
0x1800260f3  mov     edx, esi; nIndex
0x1800260f5  call    cs:__imp_GetWindowLongPtrW
0x1800260fb  test    rax, rax
0x1800260fe  jnz     short loc_180026116
0x180026100  mov     rcx, rbx; hDlg
0x180026103  call    VpnWizInitializeDialog
0x180026108  mov     r8, rdi; dwNewLong
0x18002610b  mov     edx, esi; nIndex
0x18002610d  mov     rcx, rbx; hWnd
0x180026110  call    cs:__imp_SetWindowLongPtrW
0x180026116  mov     rcx, rbx; hWnd
0x180026119  call    cs:__imp_GetParent
0x18002611f  mov     r9d, 3; lParam
0x180026125  xor     r8d, r8d; wParam
0x180026128  mov     rcx, rax; hWnd
0x18002612b  mov     edx, 470h; Msg
0x180026130  call    cs:__imp_PostMessageW
0x180026136  jmp     short loc_1800261A0
0x180026138  mov     [rsp+58h+var_38], 0
0x180026141  call    IsServerOS
0x180026146  lea     r8, [rsp+58h+var_38]
0x18002614b  mov     edx, edi
0x18002614d  mov     rcx, rbx; hWnd
0x180026150  mov     esi, eax
0x180026152  call    RasSrvGetDatabaseHandle
0x180026157  mov     edx, 1B8Dh; nIDButton
0x18002615c  mov     rcx, rbx; hDlg
0x18002615f  call    cs:__imp_IsDlgButtonChecked
0x180026165  mov     rdx, [rsp+58h+var_38]
0x18002616a  xor     ecx, ecx
0x18002616c  test    eax, eax
0x18002616e  setz    cl
0x180026171  test    rdx, rdx
0x180026174  jz      short loc_180026179
0x180026176  mov     [rdx+18h], ecx
0x180026179  xor     edx, edx
0x18002617b  mov     rcx, rbx
0x18002617e  test    esi, esi
0x180026180  setnz   dl
0x180026183  call    UserTabSaveEncryption
0x180026188  jmp     short loc_1800261A0
0x18002618a  mov     rcx, rbx; hWnd
0x18002618d  call    VpnWizCancelEdit
0x180026192  xor     r8d, r8d; dwNewLong
0x180026195  xor     edx, edx; nIndex
0x180026197  mov     rcx, rbx; hWnd
0x18002619a  call    cs:__imp_SetWindowLongPtrW
0x1800261a0  lea     r8, [rsp+58h+var_38]
0x1800261a5  mov     [rsp+58h+var_38], 0
0x1800261ae  mov     edx, edi
0x1800261b0  mov     rcx, rbx; hWnd
0x1800261b3  call    RasSrvGetDatabaseHandle
0x1800261b8  lea     rax, [r14-1B8Dh]
0x1800261bf  cmp     rax, rdi
0x1800261c2  ja      short loc_1800261FD
0x1800261c4  mov     edx, 1B8Dh; nIDDlgItem
0x1800261c9  mov     rcx, rbx; hDlg
0x1800261cc  xor     edi, edi
0x1800261ce  call    cs:__imp_GetDlgItem
0x1800261d4  test    rax, rax
0x1800261d7  jz      short loc_1800261F0
0x1800261d9  xor     r9d, r9d; lParam
0x1800261dc  xor     r8d, r8d; wParam
0x1800261df  mov     edx, 0F0h; Msg
0x1800261e4  mov     rcx, rax; hWnd
0x1800261e7  call    cs:__imp_SendMessageW
0x1800261ed  mov     rdi, rax
0x1800261f0  mov     rcx, [rsp+58h+var_38]
0x1800261f5  test    rcx, rcx
0x1800261f8  jz      short loc_1800261FD
0x1800261fa  mov     [rcx+14h], edi
0x1800261fd  xor     eax, eax
0x1800261ff  add     rsp, 30h
0x180026203  pop     r14
0x180026205  pop     rdi
0x180026206  pop     rsi
0x180026207  pop     rbp
0x180026208  pop     rbx
0x180026209  retn
```
