# VpnWizDialogProc

- ea: `0x1800331a0`
- end: `0x18003339a`
- name: `VpnWizDialogProc`
- size: `506`
- prototype: `__int64 __fastcall(HWND hDlg)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18002e918`
- `0x18002ecd8`
- `0x180031dfc`
- `0x1800330e0`
- `0x1800331a0`
- `0x18003345c`
- `0x18003e608`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180033213`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180033213`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180033223`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003322c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180033223`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18003322c`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800331f6`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800331f6`
- `USER32!PostMessageW` at `0x1800332c0`
- `USER32!PostMessageW` at `0x1800332c0`
- `USER32!ShowWindow` at `0x18003324d`
- `USER32!ShowWindow` at `0x18003324d`
- `USER32!IsDlgButtonChecked` at `0x1800332ef`
- `USER32!IsDlgButtonChecked` at `0x1800332ef`
- `USER32!SetWindowLongPtrW` at `0x1800332a0`
- `USER32!SetWindowLongPtrW` at `0x18003332a`
- `USER32!SetWindowLongPtrW` at `0x1800332a0`
- `USER32!SetWindowLongPtrW` at `0x18003332a`
- `USER32!SendMessageW` at `0x180033377`
- `USER32!SendMessageW` at `0x180033377`
- `USER32!GetWindowLongPtrW` at `0x180033285`
- `USER32!GetWindowLongPtrW` at `0x180033285`
- `USER32!GetDlgItem` at `0x180033242`
- `USER32!GetDlgItem` at `0x18003335e`
- `USER32!GetDlgItem` at `0x180033242`
- `USER32!GetDlgItem` at `0x18003335e`
- `USER32!GetParent` at `0x1800332a9`
- `USER32!GetParent` at `0x1800332a9`

## string_xrefs

- `0x180033207`: `sharedaccess`

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
0x1800331a0  push    rbx
0x1800331a2  push    rbp
0x1800331a3  push    rsi
0x1800331a4  push    rdi
0x1800331a5  push    r14
0x1800331a7  sub     rsp, 30h
0x1800331ab  mov     rbp, r9
0x1800331ae  mov     r14, r8
0x1800331b1  mov     esi, edx
0x1800331b3  mov     rbx, rcx
0x1800331b6  call    RasSrvMessageFilter
0x1800331bb  test    eax, eax
0x1800331bd  jz      short loc_1800331C9
0x1800331bf  mov     eax, 1
0x1800331c4  jmp     loc_18003338F
0x1800331c9  mov     edi, 1
0x1800331ce  sub     esi, 4Eh ; 'N'
0x1800331d1  jz      loc_180033258
0x1800331d7  sub     esi, 0C2h
0x1800331dd  jz      short loc_1800331EC
0x1800331df  cmp     esi, edi
0x1800331e1  jz      loc_180033330
0x1800331e7  jmp     loc_18003338D
0x1800331ec  xor     edx, edx; lpDatabaseName
0x1800331ee  xor     ecx, ecx; lpMachineName
0x1800331f0  mov     r8d, 20000h; dwDesiredAccess
0x1800331f6  call    cs:__imp_OpenSCManagerW
0x1800331fc  mov     rsi, rax
0x1800331ff  test    rax, rax
0x180033202  jz      short loc_18003323A
0x180033204  mov     r8d, edi; dwDesiredAccess
0x180033207  lea     rdx, ServiceName; "sharedaccess"
0x18003320e  mov     rcx, rax; hSCManager
0x180033211  xor     ebp, ebp
0x180033213  call    cs:__imp_OpenServiceW
0x180033219  test    rax, rax
0x18003321c  jz      short loc_180033229
0x18003321e  mov     rcx, rax; hSCObject
0x180033221  mov     ebp, edi
0x180033223  call    cs:__imp_CloseServiceHandle
0x180033229  mov     rcx, rsi; hSCObject
0x18003322c  call    cs:__imp_CloseServiceHandle
0x180033232  test    ebp, ebp
0x180033234  jnz     loc_18003338D
0x18003323a  mov     edx, 1B96h; nIDDlgItem
0x18003323f  mov     rcx, rbx; hDlg
0x180033242  call    cs:__imp_GetDlgItem
0x180033248  mov     rcx, rax; hWnd
0x18003324b  xor     edx, edx; nCmdShow
0x18003324d  call    cs:__imp_ShowWindow
0x180033253  jmp     loc_18003338D
0x180033258  cmp     dword ptr [rbp+10h], 0FFFFFF35h
0x18003325f  jz      loc_18003331A
0x180033265  cmp     dword ptr [rbp+10h], 0FFFFFF37h
0x18003326c  jz      short loc_1800332C8
0x18003326e  cmp     dword ptr [rbp+10h], 0FFFFFF38h
0x180033275  jnz     loc_180033330
0x18003327b  mov     esi, 0FFFFFFEBh
0x180033280  mov     rcx, rbx; hWnd
0x180033283  mov     edx, esi; nIndex
0x180033285  call    cs:__imp_GetWindowLongPtrW
0x18003328b  test    rax, rax
0x18003328e  jnz     short loc_1800332A6
0x180033290  mov     rcx, rbx; hDlg
0x180033293  call    VpnWizInitializeDialog
0x180033298  mov     r8, rdi; dwNewLong
0x18003329b  mov     edx, esi; nIndex
0x18003329d  mov     rcx, rbx; hWnd
0x1800332a0  call    cs:__imp_SetWindowLongPtrW
0x1800332a6  mov     rcx, rbx; hWnd
0x1800332a9  call    cs:__imp_GetParent
0x1800332af  mov     r9d, 3; lParam
0x1800332b5  xor     r8d, r8d; wParam
0x1800332b8  mov     rcx, rax; hWnd
0x1800332bb  mov     edx, 470h; Msg
0x1800332c0  call    cs:__imp_PostMessageW
0x1800332c6  jmp     short loc_180033330
0x1800332c8  mov     [rsp+58h+var_38], 0
0x1800332d1  call    IsServerOS
0x1800332d6  lea     r8, [rsp+58h+var_38]
0x1800332db  mov     edx, edi
0x1800332dd  mov     rcx, rbx; hWnd
0x1800332e0  mov     esi, eax
0x1800332e2  call    RasSrvGetDatabaseHandle
0x1800332e7  mov     edx, 1B8Dh; nIDButton
0x1800332ec  mov     rcx, rbx; hDlg
0x1800332ef  call    cs:__imp_IsDlgButtonChecked
0x1800332f5  mov     rdx, [rsp+58h+var_38]
0x1800332fa  xor     ecx, ecx
0x1800332fc  test    eax, eax
0x1800332fe  setz    cl
0x180033301  test    rdx, rdx
0x180033304  jz      short loc_180033309
0x180033306  mov     [rdx+18h], ecx
0x180033309  xor     edx, edx
0x18003330b  mov     rcx, rbx
0x18003330e  test    esi, esi
0x180033310  setnz   dl
0x180033313  call    UserTabSaveEncryption
0x180033318  jmp     short loc_180033330
0x18003331a  mov     rcx, rbx; hWnd
0x18003331d  call    VpnWizCancelEdit
0x180033322  xor     r8d, r8d; dwNewLong
0x180033325  xor     edx, edx; nIndex
0x180033327  mov     rcx, rbx; hWnd
0x18003332a  call    cs:__imp_SetWindowLongPtrW
0x180033330  lea     r8, [rsp+58h+var_38]
0x180033335  mov     [rsp+58h+var_38], 0
0x18003333e  mov     edx, edi
0x180033340  mov     rcx, rbx; hWnd
0x180033343  call    RasSrvGetDatabaseHandle
0x180033348  lea     rax, [r14-1B8Dh]
0x18003334f  cmp     rax, rdi
0x180033352  ja      short loc_18003338D
0x180033354  mov     edx, 1B8Dh; nIDDlgItem
0x180033359  mov     rcx, rbx; hDlg
0x18003335c  xor     edi, edi
0x18003335e  call    cs:__imp_GetDlgItem
0x180033364  test    rax, rax
0x180033367  jz      short loc_180033380
0x180033369  xor     r9d, r9d; lParam
0x18003336c  xor     r8d, r8d; wParam
0x18003336f  mov     edx, 0F0h; Msg
0x180033374  mov     rcx, rax; hWnd
0x180033377  call    cs:__imp_SendMessageW
0x18003337d  mov     rdi, rax
0x180033380  mov     rcx, [rsp+58h+var_38]
0x180033385  test    rcx, rcx
0x180033388  jz      short loc_18003338D
0x18003338a  mov     [rcx+14h], edi
0x18003338d  xor     eax, eax
0x18003338f  add     rsp, 30h
0x180033393  pop     r14
0x180033395  pop     rdi
0x180033396  pop     rsi
0x180033397  pop     rbp
0x180033398  pop     rbx
0x180033399  retn
```
