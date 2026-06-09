# CWizard::GetOfferRATicketString(HWND__ *)

- ea: `0x14003175c`
- end: `0x14003190f`
- name: `?GetOfferRATicketString@CWizard@@AEAAJPEAUHWND__@@@Z`
- size: `435`
- prototype: `int(CWizard *__hidden this, HWND)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140031adc`
- `0x140032bf0`

## callees

- `0x140028edc`
- `0x14002c0a4`
- `0x14003175c`
- `0x140034ce4`

## import_xrefs

- `KERNEL32!CreateThread` at `0x140031867`
- `KERNEL32!CreateThread` at `0x140031867`
- `KERNEL32!CloseHandle` at `0x1400318e5`
- `KERNEL32!CloseHandle` at `0x1400318e5`
- `USER32!SendMessageW` at `0x1400317ef`
- `USER32!SendMessageW` at `0x1400318d4`
- `USER32!SendMessageW` at `0x1400317ef`
- `USER32!SendMessageW` at `0x1400318d4`
- `USER32!ShowWindow` at `0x140031814`
- `USER32!ShowWindow` at `0x14003183c`
- `USER32!ShowWindow` at `0x140031814`
- `USER32!ShowWindow` at `0x14003183c`
- `USER32!GetDlgItem` at `0x14003176d`
- `USER32!GetDlgItem` at `0x140031803`
- `USER32!GetDlgItem` at `0x140031828`
- `USER32!GetDlgItem` at `0x14003176d`
- `USER32!GetDlgItem` at `0x140031803`
- `USER32!GetDlgItem` at `0x140031828`
- `USER32!SetWindowLongPtrW` at `0x1400318fa`
- `USER32!SetWindowLongPtrW` at `0x1400318fa`
- `USER32!EnableWindow` at `0x14003177e`
- `USER32!EnableWindow` at `0x14003177e`
- `USER32!GetParent` at `0x1400317d2`
- `USER32!GetParent` at `0x1400317d2`
- `OLEAUT32!__imp_SysFreeString` at `0x14003179d`
- `OLEAUT32!__imp_SysFreeString` at `0x14003179d`

## pseudocode

```c
__int64 __fastcall CWizard::GetOfferRATicketString(CWizard *this, HWND a2)
{
  HWND DlgItem; // rax
  CEventLogger *v4; // r8
  OLECHAR *v5; // rcx
  HWND Parent; // rax
  HWND v7; // rax
  HWND v8; // rax
  HANDLE Thread; // rax
  CEventLogger *v10; // rcx

  DlgItem = GetDlgItem(a2, 1054);
  EnableWindow(DlgItem, 0);
  v4 = _AtlModule;
  v5 = (OLECHAR *)*((_QWORD *)_AtlModule + 80);
  if ( v5 )
  {
    SysFreeString(v5);
    v4 = _AtlModule;
    *((_QWORD *)_AtlModule + 80) = 0;
  }
  GetDlgItemTextAsBSTR(a2, 1054, (unsigned __int16 **)v4 + 80);
  Parent = GetParent(a2);
  SendMessageW(Parent, 0x470u, 0, 16);
  v7 = GetDlgItem(a2, 1056);
  ShowWindow(v7, 0);
  v8 = GetDlgItem(a2, 1057);
  ShowWindow(v8, 5);
  Thread = CreateThread(0, 0, GetOfferRAStringThreadFunc, a2, 0, 0);
  if ( Thread )
  {
    CloseHandle(Thread);
  }
  else
  {
    CEventLogger::LogError(
      v10,
      &Critical_Error,
      L"base\\diagnosis\\ra\\ui\\wizard.cpp",
      0x6A8u,
      L"CWizard::GetOfferRATicketString",
      0);
    ShowErrorMessage(0x213u, 0x28Au, a2, 0, (unsigned __int16 *)0xFFFE, 0);
    SendMessageW(a2, 0x471u, 5u, 0);
  }
  SetWindowLongPtrW(a2, 0, -1);
  return 0;
}

```

## disassembly

```asm
0x14003175c  push    rbx
0x14003175e  sub     rsp, 30h
0x140031762  mov     rbx, rdx
0x140031765  mov     edx, 41Eh; nIDDlgItem
0x14003176a  mov     rcx, rbx; hDlg
0x14003176d  call    cs:__imp_GetDlgItem
0x140031774  nop     dword ptr [rax+rax+00h]
0x140031779  mov     rcx, rax; hWnd
0x14003177c  xor     edx, edx; bEnable
0x14003177e  call    cs:__imp_EnableWindow
0x140031785  nop     dword ptr [rax+rax+00h]
0x14003178a  mov     r8, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140031791  mov     rcx, [r8+280h]; bstrString
0x140031798  test    rcx, rcx
0x14003179b  jz      short loc_1400317BB
0x14003179d  call    cs:__imp_SysFreeString
0x1400317a4  nop     dword ptr [rax+rax+00h]
0x1400317a9  mov     r8, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400317b0  mov     qword ptr [r8+280h], 0
0x1400317bb  add     r8, 280h; unsigned __int16 **
0x1400317c2  mov     edx, 41Eh; int
0x1400317c7  mov     rcx, rbx; HWND
0x1400317ca  call    ?GetDlgItemTextAsBSTR@@YAJPEAUHWND__@@HPEAPEAG@Z; GetDlgItemTextAsBSTR(HWND__ *,int,ushort * *)
0x1400317cf  mov     rcx, rbx; hWnd
0x1400317d2  call    cs:__imp_GetParent
0x1400317d9  nop     dword ptr [rax+rax+00h]
0x1400317de  mov     r9d, 10h; lParam
0x1400317e4  xor     r8d, r8d; wParam
0x1400317e7  mov     rcx, rax; hWnd
0x1400317ea  mov     edx, 470h; Msg
0x1400317ef  call    cs:__imp_SendMessageW
0x1400317f6  nop     dword ptr [rax+rax+00h]
0x1400317fb  mov     edx, 420h; nIDDlgItem
0x140031800  mov     rcx, rbx; hDlg
0x140031803  call    cs:__imp_GetDlgItem
0x14003180a  nop     dword ptr [rax+rax+00h]
0x14003180f  mov     rcx, rax; hWnd
0x140031812  xor     edx, edx; nCmdShow
0x140031814  call    cs:__imp_ShowWindow
0x14003181b  nop     dword ptr [rax+rax+00h]
0x140031820  mov     edx, 421h; nIDDlgItem
0x140031825  mov     rcx, rbx; hDlg
0x140031828  call    cs:__imp_GetDlgItem
0x14003182f  nop     dword ptr [rax+rax+00h]
0x140031834  mov     rcx, rax; hWnd
0x140031837  mov     edx, 5; nCmdShow
0x14003183c  call    cs:__imp_ShowWindow
0x140031843  nop     dword ptr [rax+rax+00h]
0x140031848  mov     r9, rbx; lpParameter
0x14003184b  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x140031854  lea     r8, ?GetOfferRAStringThreadFunc@@YAKPEAX@Z; lpStartAddress
0x14003185b  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140031863  xor     edx, edx; dwStackSize
0x140031865  xor     ecx, ecx; lpThreadAttributes
0x140031867  call    cs:__imp_CreateThread
0x14003186e  nop     dword ptr [rax+rax+00h]
0x140031873  test    rax, rax
0x140031876  jnz     short loc_1400318E2
0x140031878  mov     dword ptr [rsp+38h+lpThreadId], eax; unsigned int
0x14003187c  lea     r8, aBaseDiagnosisR_12; "base\\diagnosis\\ra\\ui\\wizard.cpp"
0x140031883  lea     rax, aCwizardGetoffe; "CWizard::GetOfferRATicketString"
0x14003188a  mov     r9d, 6A8h; unsigned int
0x140031890  lea     rdx, Critical_Error; struct _EVENT_DESCRIPTOR *
0x140031897  mov     qword ptr [rsp+38h+dwCreationFlags], rax; unsigned __int16 *
0x14003189c  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400318a1  mov     edx, 28Ah; int
0x1400318a6  mov     dword ptr [rsp+38h+lpThreadId], 0; int
0x1400318ae  xor     r9d, r9d; int
0x1400318b1  mov     qword ptr [rsp+38h+dwCreationFlags], 0FFFEh; unsigned __int16 *
0x1400318ba  mov     r8, rbx; HWND
0x1400318bd  lea     ecx, [rdx-77h]; int
0x1400318c0  call    ?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z; ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)
0x1400318c5  xor     r9d, r9d; lParam
0x1400318c8  mov     edx, 471h; Msg
0x1400318cd  mov     rcx, rbx; hWnd
0x1400318d0  lea     r8d, [r9+5]; wParam
0x1400318d4  call    cs:__imp_SendMessageW
0x1400318db  nop     dword ptr [rax+rax+00h]
0x1400318e0  jmp     short loc_1400318F1
0x1400318e2  mov     rcx, rax; hObject
0x1400318e5  call    cs:__imp_CloseHandle
0x1400318ec  nop     dword ptr [rax+rax+00h]
0x1400318f1  or      r8, 0FFFFFFFFFFFFFFFFh; dwNewLong
0x1400318f5  xor     edx, edx; nIndex
0x1400318f7  mov     rcx, rbx; hWnd
0x1400318fa  call    cs:__imp_SetWindowLongPtrW
0x140031901  nop     dword ptr [rax+rax+00h]
0x140031906  xor     eax, eax
0x140031908  add     rsp, 30h
0x14003190c  pop     rbx
0x14003190d  retn
```
