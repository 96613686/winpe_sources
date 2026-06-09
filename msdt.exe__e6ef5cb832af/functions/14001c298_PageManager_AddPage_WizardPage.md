# PageManager::AddPage(WizardPage *)

- ea: `0x14001c298`
- end: `0x14001c36a`
- name: `?AddPage@PageManager@@QEAAJPEAVWizardPage@@@Z`
- size: `210`
- prototype: `__int64 __fastcall(PageManager *__hidden this, struct WizardPage *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14001c890`

## callees

- `0x14001c298`
- `0x14001d22c`
- `0x140020420`

## import_xrefs

- `USER32!SendMessageW` at `0x14001c303`
- `USER32!SendMessageW` at `0x14001c303`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14001c2b1`
- `DUI70!?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x14001c2b1`
- `DUI70!??BTaskPage@DirectUI@@QEAAPEAU_PSP@@XZ` at `0x14001c2e8`
- `DUI70!??BTaskPage@DirectUI@@QEAAPEAU_PSP@@XZ` at `0x14001c2e8`
- `DUI70!?DUICreatePropertySheetPage@TaskPage@DirectUI@@QEAAJPEAUHINSTANCE__@@@Z` at `0x14001c2cb`
- `DUI70!?DUICreatePropertySheetPage@TaskPage@DirectUI@@QEAAJPEAUHINSTANCE__@@@Z` at `0x14001c2cb`

## pseudocode

```c
__int64 __fastcall PageManager::AddPage(PageManager *this, struct WizardPage *a2)
{
  HWND ParentHWND; // rax
  HINSTANCE v5; // rdx
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // r9d
  LPARAM v9; // rax

  ParentHWND = DirectUI::TaskPage::GetParentHWND(*((DirectUI::TaskPage **)this + 1));
  v5 = g_hInstance;
  *((_QWORD *)this + 3) = ParentHWND;
  v6 = DirectUI::TaskPage::DUICreatePropertySheetPage(a2, v5);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 377;
LABEL_7:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "PageManager::AddPage", v8, v6);
    return v7;
  }
  v9 = DirectUI::TaskPage::operator _PSP *(a2);
  if ( (unsigned int)SendMessageW(*((HWND *)this + 3), 0x467u, 0, v9) )
  {
    v6 = PageManager::SwitchToPage(this, a2);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 395;
      goto LABEL_7;
    }
  }
  else
  {
    v7 = -2147467259;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "PageManager::AddPage", 391, -2147467259);
  }
  return v7;
}

```

## disassembly

```asm
0x14001c298  mov     [rsp+arg_0], rbx
0x14001c29d  mov     [rsp+arg_8], rsi
0x14001c2a2  push    rdi
0x14001c2a3  sub     rsp, 30h
0x14001c2a7  mov     rdi, rcx
0x14001c2aa  mov     rsi, rdx
0x14001c2ad  mov     rcx, [rcx+8]
0x14001c2b1  call    cs:__imp_?GetParentHWND@TaskPage@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::TaskPage::GetParentHWND(void)
0x14001c2b8  nop     dword ptr [rax+rax+00h]
0x14001c2bd  mov     rdx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x14001c2c4  mov     rcx, rsi
0x14001c2c7  mov     [rdi+18h], rax
0x14001c2cb  call    cs:__imp_?DUICreatePropertySheetPage@TaskPage@DirectUI@@QEAAJPEAUHINSTANCE__@@@Z; DirectUI::TaskPage::DUICreatePropertySheetPage(HINSTANCE__ *)
0x14001c2d2  nop     dword ptr [rax+rax+00h]
0x14001c2d7  mov     ebx, eax
0x14001c2d9  test    eax, eax
0x14001c2db  jns     short loc_14001C2E5
0x14001c2dd  mov     r9d, 179h
0x14001c2e3  jmp     short loc_14001C33B
0x14001c2e5  mov     rcx, rsi
0x14001c2e8  call    cs:__imp_??BTaskPage@DirectUI@@QEAAPEAU_PSP@@XZ; DirectUI::TaskPage::operator _PSP *(void)
0x14001c2ef  nop     dword ptr [rax+rax+00h]
0x14001c2f4  mov     rcx, [rdi+18h]; hWnd
0x14001c2f8  xor     r8d, r8d; wParam
0x14001c2fb  mov     r9, rax; lParam
0x14001c2fe  mov     edx, 467h; Msg
0x14001c303  call    cs:__imp_SendMessageW
0x14001c30a  nop     dword ptr [rax+rax+00h]
0x14001c30f  test    eax, eax
0x14001c311  jnz     short loc_14001C324
0x14001c313  mov     ebx, 80004005h
0x14001c318  mov     r9d, 187h
0x14001c31e  mov     [rsp+38h+var_18], ebx
0x14001c322  jmp     short loc_14001C33F
0x14001c324  mov     rdx, rsi; struct WizardPage *
0x14001c327  mov     rcx, rdi; this
0x14001c32a  call    ?SwitchToPage@PageManager@@QEAAJPEAVWizardPage@@@Z; PageManager::SwitchToPage(WizardPage *)
0x14001c32f  mov     ebx, eax
0x14001c331  test    eax, eax
0x14001c333  jns     short loc_14001C357
0x14001c335  mov     r9d, 18Bh
0x14001c33b  mov     [rsp+38h+var_18], eax
0x14001c33f  lea     r8, aPagemanagerAdd; "PageManager::AddPage"
0x14001c346  mov     ecx, 1; Level
0x14001c34b  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14001c352  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14001c357  mov     rsi, [rsp+38h+arg_8]
0x14001c35c  mov     eax, ebx
0x14001c35e  mov     rbx, [rsp+38h+arg_0]
0x14001c363  add     rsp, 30h
0x14001c367  pop     rdi
0x14001c368  retn
```
