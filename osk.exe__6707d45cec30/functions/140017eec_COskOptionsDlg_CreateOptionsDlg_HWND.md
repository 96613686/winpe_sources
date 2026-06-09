# COskOptionsDlg::CreateOptionsDlg(HWND__ *)

- ea: `0x140017eec`
- end: `0x140017f8c`
- name: `?CreateOptionsDlg@COskOptionsDlg@@SAPEAUHWND__@@PEAU2@@Z`
- size: `160`
- prototype: `HWND __fastcall(HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140016a5c`

## callees

- `0x1400020d8`
- `0x140017ec4`
- `0x140017eec`
- `0x1400182a4`
- `0x14001bf88`

## import_xrefs

- `USER32!SetForegroundWindow` at `0x140017f78`
- `USER32!SetForegroundWindow` at `0x140017f78`

## pseudocode

```c
HWND __fastcall COskOptionsDlg::CreateOptionsDlg(HWND a1)
{
  HWND HWND; // rbx
  COskOptionsDlg *v3; // rax
  __int64 v4; // rcx
  unsigned int v5; // edx

  if ( COskOptionsDlg::s_pCOskOptionsDlgSingleton )
  {
    HWND = COskOptionsDlg::GetHWND();
    SetForegroundWindow(HWND);
  }
  else
  {
    HWND = 0;
    v3 = (COskOptionsDlg *)operator new(0x10u);
    if ( v3 )
    {
      *(_QWORD *)v3 = 0;
      *((_QWORD *)v3 + 1) = 0;
      COskOptionsDlg::s_pCOskOptionsDlgSingleton = v3;
      HWND = SHFusionCreateDialogParam(
               v4,
               (const WCHAR *)0x1388,
               a1,
               (INT_PTR (__stdcall *)(HWND, UINT, WPARAM, LPARAM))COskOptionsDlg::OptionsDlgProc,
               (LPARAM)v3);
      if ( !HWND )
      {
        if ( COskOptionsDlg::s_pCOskOptionsDlgSingleton )
          COskOptionsDlg::`scalar deleting destructor'(COskOptionsDlg::s_pCOskOptionsDlgSingleton, v5);
        COskOptionsDlg::s_pCOskOptionsDlgSingleton = 0;
      }
    }
    else
    {
      COskOptionsDlg::s_pCOskOptionsDlgSingleton = 0;
    }
  }
  return HWND;
}

```

## disassembly

```asm
0x140017eec  mov     [rsp+arg_0], rbx
0x140017ef1  push    rdi
0x140017ef2  sub     rsp, 30h
0x140017ef6  cmp     cs:?s_pCOskOptionsDlgSingleton@COskOptionsDlg@@0PEAV1@EA, 0; COskOptionsDlg * COskOptionsDlg::s_pCOskOptionsDlgSingleton
0x140017efe  mov     rdi, rcx
0x140017f01  jnz     short loc_140017F6D
0x140017f03  xor     ebx, ebx
0x140017f05  lea     ecx, [rbx+10h]; Size
0x140017f08  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140017f0d  mov     [rsp+38h+arg_8], rax
0x140017f12  test    rax, rax
0x140017f15  jz      short loc_140017F64
0x140017f17  lea     r9, ?OptionsDlgProc@COskOptionsDlg@@SA_JPEAUHWND__@@I_K_J@Z; COskOptionsDlg::OptionsDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x140017f1e  mov     [rax], rbx
0x140017f21  mov     r8, rdi
0x140017f24  mov     [rax+8], rbx
0x140017f28  mov     edx, 1388h
0x140017f2d  mov     cs:?s_pCOskOptionsDlgSingleton@COskOptionsDlg@@0PEAV1@EA, rax; COskOptionsDlg * COskOptionsDlg::s_pCOskOptionsDlgSingleton
0x140017f34  mov     [rsp+38h+var_18], rax
0x140017f39  call    SHFusionCreateDialogParam
0x140017f3e  mov     rbx, rax
0x140017f41  test    rax, rax
0x140017f44  jnz     short loc_140017F7E
0x140017f46  mov     rcx, cs:?s_pCOskOptionsDlgSingleton@COskOptionsDlg@@0PEAV1@EA; this
0x140017f4d  test    rcx, rcx
0x140017f50  jz      short loc_140017F57
0x140017f52  call    ??_GCOskOptionsDlg@@AEAAPEAXI@Z; COskOptionsDlg::`scalar deleting destructor'(uint)
0x140017f57  mov     cs:?s_pCOskOptionsDlgSingleton@COskOptionsDlg@@0PEAV1@EA, 0; COskOptionsDlg * COskOptionsDlg::s_pCOskOptionsDlgSingleton
0x140017f62  jmp     short loc_140017F7E
0x140017f64  mov     cs:?s_pCOskOptionsDlgSingleton@COskOptionsDlg@@0PEAV1@EA, rbx; COskOptionsDlg * COskOptionsDlg::s_pCOskOptionsDlgSingleton
0x140017f6b  jmp     short loc_140017F7E
0x140017f6d  call    ?GetHWND@COskOptionsDlg@@SAPEAUHWND__@@XZ; COskOptionsDlg::GetHWND(void)
0x140017f72  mov     rcx, rax; hWnd
0x140017f75  mov     rbx, rax
0x140017f78  call    cs:__imp_SetForegroundWindow
0x140017f7e  mov     rax, rbx
0x140017f81  mov     rbx, [rsp+38h+arg_0]
0x140017f86  add     rsp, 30h
0x140017f8a  pop     rdi
0x140017f8b  retn
```
