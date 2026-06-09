# COskMessageDlg::CreateMessageDlg(HWND__ *)

- ea: `0x14001b0e0`
- end: `0x14001b188`
- name: `?CreateMessageDlg@COskMessageDlg@@SAPEAUHWND__@@PEAU2@@Z`
- size: `168`
- prototype: `HWND __fastcall(HWND)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140016a5c`

## callees

- `0x1400020d8`
- `0x14001b0e0`
- `0x14001b190`
- `0x14001bf88`

## import_xrefs

- `USER32!ShowWindow` at `0x14001b13e`
- `USER32!ShowWindow` at `0x14001b13e`
- `USER32!SetForegroundWindow` at `0x14001b174`
- `USER32!SetForegroundWindow` at `0x14001b174`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001b14d`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001b14d`

## pseudocode

```c
HWND __fastcall COskMessageDlg::CreateMessageDlg(HWND a1)
{
  HWND HWND; // rbx
  struct COskMessageDlg *v3; // rax
  __int64 v4; // rcx
  HWND DialogParam; // rax

  if ( COskMessageDlg::s_pCOskMessageDlgSingleton )
  {
    HWND = COskMessageDlg::GetHWND();
    SetForegroundWindow(HWND);
  }
  else
  {
    HWND = 0;
    v3 = (struct COskMessageDlg *)operator new(8u);
    if ( v3 )
    {
      *(_QWORD *)v3 = 0;
      COskMessageDlg::s_pCOskMessageDlgSingleton = v3;
      DialogParam = SHFusionCreateDialogParam(
                      v4,
                      (const WCHAR *)0x138A,
                      a1,
                      (INT_PTR (__stdcall *)(HWND, UINT, WPARAM, LPARAM))COskMessageDlg::MessageDlgProc,
                      (LPARAM)v3);
      HWND = DialogParam;
      if ( DialogParam )
      {
        ShowWindow(DialogParam, 1);
      }
      else
      {
        operator delete(COskMessageDlg::s_pCOskMessageDlgSingleton);
        COskMessageDlg::s_pCOskMessageDlgSingleton = 0;
      }
    }
    else
    {
      COskMessageDlg::s_pCOskMessageDlgSingleton = 0;
    }
  }
  return HWND;
}

```

## disassembly

```asm
0x14001b0e0  mov     [rsp+arg_0], rbx
0x14001b0e5  push    rdi
0x14001b0e6  sub     rsp, 30h
0x14001b0ea  cmp     cs:?s_pCOskMessageDlgSingleton@COskMessageDlg@@0PEAV1@EA, 0; COskMessageDlg * COskMessageDlg::s_pCOskMessageDlgSingleton
0x14001b0f2  mov     rdi, rcx
0x14001b0f5  jnz     short loc_14001B169
0x14001b0f7  xor     ebx, ebx
0x14001b0f9  lea     ecx, [rbx+8]; Size
0x14001b0fc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001b101  mov     [rsp+38h+arg_8], rax
0x14001b106  test    rax, rax
0x14001b109  jz      short loc_14001B160
0x14001b10b  lea     r9, ?MessageDlgProc@COskMessageDlg@@SA_JPEAUHWND__@@I_K_J@Z; COskMessageDlg::MessageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x14001b112  mov     [rax], rbx
0x14001b115  mov     r8, rdi
0x14001b118  mov     cs:?s_pCOskMessageDlgSingleton@COskMessageDlg@@0PEAV1@EA, rax; COskMessageDlg * COskMessageDlg::s_pCOskMessageDlgSingleton
0x14001b11f  mov     edx, 138Ah
0x14001b124  mov     [rsp+38h+var_18], rax
0x14001b129  call    SHFusionCreateDialogParam
0x14001b12e  mov     rbx, rax
0x14001b131  test    rax, rax
0x14001b134  jz      short loc_14001B146
0x14001b136  mov     edx, 1; nCmdShow
0x14001b13b  mov     rcx, rax; hWnd
0x14001b13e  call    cs:__imp_ShowWindow
0x14001b144  jmp     short loc_14001B17A
0x14001b146  mov     rcx, cs:?s_pCOskMessageDlgSingleton@COskMessageDlg@@0PEAV1@EA; COskMessageDlg * COskMessageDlg::s_pCOskMessageDlgSingleton
0x14001b14d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14001b153  mov     cs:?s_pCOskMessageDlgSingleton@COskMessageDlg@@0PEAV1@EA, 0; COskMessageDlg * COskMessageDlg::s_pCOskMessageDlgSingleton
0x14001b15e  jmp     short loc_14001B17A
0x14001b160  mov     cs:?s_pCOskMessageDlgSingleton@COskMessageDlg@@0PEAV1@EA, rbx; COskMessageDlg * COskMessageDlg::s_pCOskMessageDlgSingleton
0x14001b167  jmp     short loc_14001B17A
0x14001b169  call    ?GetHWND@COskMessageDlg@@SAPEAUHWND__@@XZ; COskMessageDlg::GetHWND(void)
0x14001b16e  mov     rcx, rax; hWnd
0x14001b171  mov     rbx, rax
0x14001b174  call    cs:__imp_SetForegroundWindow
0x14001b17a  mov     rax, rbx
0x14001b17d  mov     rbx, [rsp+38h+arg_0]
0x14001b182  add     rsp, 30h
0x14001b186  pop     rdi
0x14001b187  retn
```
