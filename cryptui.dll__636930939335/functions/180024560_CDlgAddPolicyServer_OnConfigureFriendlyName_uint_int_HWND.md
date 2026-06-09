# CDlgAddPolicyServer::OnConfigureFriendlyName(uint,int,HWND__ *)

- ea: `0x180024560`
- end: `0x180024673`
- name: `?OnConfigureFriendlyName@CDlgAddPolicyServer@@AEAAXIHPEAUHWND__@@@Z`
- size: `275`
- prototype: `void __fastcall(CDlgAddPolicyServer *__hidden this, unsigned int, int, HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180025fe0`

## callees

- `0x180014440`
- `0x180023358`
- `0x180023dd0`
- `0x180024560`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024601`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024601`
- `USER32!GetActiveWindow` at `0x1800245bf`
- `USER32!GetActiveWindow` at `0x1800245bf`
- `USER32!SetWindowTextW` at `0x1800245f7`
- `USER32!SetWindowTextW` at `0x1800245f7`
- `USER32!EnableWindow` at `0x180024631`
- `USER32!EnableWindow` at `0x18002464e`
- `USER32!EnableWindow` at `0x180024631`
- `USER32!EnableWindow` at `0x18002464e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CDlgAddPolicyServer::OnConfigureFriendlyName(
        CDlgAddPolicyServer *this,
        __int64 a2,
        __int64 a3,
        HWND a4)
{
  __int64 v5; // rax
  HWND ActiveWindow; // rax
  HWND *DlgItem; // rax
  __int64 v8; // rax
  HWND *v9; // rax
  HWND *v10; // rax
  _QWORD v11[7]; // [rsp+20h] [rbp-60h] BYREF
  int v12; // [rsp+58h] [rbp-28h]
  __int64 v13; // [rsp+68h] [rbp-18h]
  __int64 v14; // [rsp+70h] [rbp-10h]
  HWND v15; // [rsp+A8h] [rbp+28h] BYREF

  v15 = a4;
  v5 = *((_QWORD *)this + 8);
  v11[1] = 0;
  v11[5] = 0;
  v11[6] = 0;
  v12 = 0;
  v11[0] = &CDlgConfigureFriendlyName::`vftable';
  v13 = 0;
  v14 = v5;
  ActiveWindow = GetActiveWindow();
  if ( ATL::CDialogImpl<CDlgConfigureFriendlyName,ATL::CWindow>::DoModal((__int64)v11, ActiveWindow) == 1 )
  {
    DlgItem = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, &v15, 1008);
    SetWindowTextW(*DlgItem, &Src);
    LocalFree(*((HLOCAL *)this + 8));
    v8 = v13;
    v13 = 0;
    *((_QWORD *)this + 8) = v8;
    v9 = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, &v15, 1006);
    EnableWindow(*v9, 1);
    v10 = (HWND *)ATL::CWindow::GetDlgItem((char *)this + 8, &v15, 1);
    EnableWindow(*v10, 0);
  }
  CDlgConfigureFriendlyName::~CDlgConfigureFriendlyName((CDlgConfigureFriendlyName *)v11);
}

```

## disassembly

```asm
0x180024560  mov     [rsp-8+arg_8], rbx
0x180024565  mov     [rsp-8+arg_10], rdi
0x18002456a  mov     [rsp-8+arg_18], r9
0x18002456f  push    rbp
0x180024570  mov     rbp, rsp
0x180024573  sub     rsp, 80h
0x18002457a  mov     rdi, rcx
0x18002457d  mov     rax, [rcx+40h]
0x180024581  mov     [rbp+var_58], 0
0x180024589  lea     rcx, [rbp+var_50]
0x18002458d  mov     [rbp+arg_0], rcx
0x180024591  mov     [rbp+var_38], 0
0x180024599  mov     [rbp+var_30], 0
0x1800245a1  mov     [rbp+var_28], 0
0x1800245a8  lea     rcx, ??_7CDlgConfigureFriendlyName@@6B@; const CDlgConfigureFriendlyName::`vftable'
0x1800245af  mov     [rbp+var_60], rcx
0x1800245b3  mov     [rbp+var_18], 0
0x1800245bb  mov     [rbp+var_10], rax
0x1800245bf  call    cs:__imp_GetActiveWindow
0x1800245c5  mov     rdx, rax
0x1800245c8  lea     rcx, [rbp+var_60]
0x1800245cc  call    ?DoModal@?$CDialogImpl@VCDlgConfigureFriendlyName@@VCWindow@ATL@@@ATL@@QEAA_JPEAUHWND__@@_J@Z; ATL::CDialogImpl<CDlgConfigureFriendlyName,ATL::CWindow>::DoModal(HWND__ *,__int64)
0x1800245d1  cmp     rax, 1
0x1800245d5  jnz     short loc_180024655
0x1800245d7  lea     rbx, [rdi+8]
0x1800245db  mov     r8d, 3F0h
0x1800245e1  lea     rdx, [rbp+arg_18]
0x1800245e5  mov     rcx, rbx
0x1800245e8  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x1800245ed  lea     rdx, Src; lpString
0x1800245f4  mov     rcx, [rax]; hWnd
0x1800245f7  call    cs:__imp_SetWindowTextW
0x1800245fd  mov     rcx, [rdi+40h]; hMem
0x180024601  call    cs:__imp_LocalFree
0x180024607  mov     rax, [rbp+var_18]
0x18002460b  mov     [rbp+var_18], 0
0x180024613  mov     [rdi+40h], rax
0x180024617  mov     r8d, 3EEh
0x18002461d  lea     rdx, [rbp+arg_18]
0x180024621  mov     rcx, rbx
0x180024624  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180024629  mov     edx, 1; bEnable
0x18002462e  mov     rcx, [rax]; hWnd
0x180024631  call    cs:__imp_EnableWindow
0x180024637  mov     r8d, 1
0x18002463d  lea     rdx, [rbp+arg_18]
0x180024641  mov     rcx, rbx
0x180024644  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x180024649  xor     edx, edx; bEnable
0x18002464b  mov     rcx, [rax]; hWnd
0x18002464e  call    cs:__imp_EnableWindow
0x180024654  nop
0x180024655  lea     rcx, [rbp+var_60]; this
0x180024659  call    ??1CDlgConfigureFriendlyName@@UEAA@XZ; CDlgConfigureFriendlyName::~CDlgConfigureFriendlyName(void)
0x18002465e  lea     r11, [rsp+80h+var_s0]
0x180024666  mov     rbx, [r11+18h]
0x18002466a  mov     rdi, [r11+20h]
0x18002466e  mov     rsp, r11
0x180024671  pop     rbp
0x180024672  retn
```
