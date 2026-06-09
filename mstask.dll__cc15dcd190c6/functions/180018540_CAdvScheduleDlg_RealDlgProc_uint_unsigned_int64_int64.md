# CAdvScheduleDlg::RealDlgProc(uint,unsigned __int64,__int64)

- ea: `0x180018540`
- end: `0x1800185d1`
- name: `?RealDlgProc@CAdvScheduleDlg@@MEAA_JI_K_J@Z`
- size: `145`
- prototype: `__int64(CAdvScheduleDlg *__hidden this, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180018540`
- `0x180018780`
- `0x180018a14`
- `0x18001923c`

## import_xrefs

- `USER32!SetWindowLongPtrW` at `0x1800185c1`
- `USER32!SetWindowLongPtrW` at `0x1800185c1`
- `USER32!WinHelpW` at `0x18001859b`
- `USER32!WinHelpW` at `0x18001859b`

## string_xrefs

- `0x18001858d`: `%windir%\help\mstask.hlp`

## pseudocode

```c
__int64 __fastcall CAdvScheduleDlg::RealDlgProc(HWND *this, int a2, HWND a3, __int64 a4)
{
  int v5; // edx
  unsigned __int64 v6; // rdx
  int v7; // edx
  int v8; // edx
  __int64 v9; // rdx
  UINT v11; // r8d
  HWND v12; // rcx

  v5 = a2 - 2;
  if ( !v5 )
  {
    SetWindowLongPtrW(this[1], 16, 0);
    return 1;
  }
  v6 = (unsigned int)(v5 - 24);
  if ( !(_DWORD)v6 )
  {
    CAdvScheduleDlg::_OnSetIniChange((CAdvScheduleDlg *)this, v6, (__int64)a3);
    return 1;
  }
  v7 = v6 - 57;
  if ( !v7 )
  {
    v12 = *(HWND *)(a4 + 16);
    v11 = 12;
    goto LABEL_11;
  }
  v8 = v7 - 40;
  if ( !v8 )
  {
    v11 = 10;
    v12 = a3;
LABEL_11:
    WinHelpW(v12, szMstaskHelp, v11, (ULONG_PTR)&s_aAdvancedDlgHelpIds);
    return 1;
  }
  v9 = (unsigned int)(v8 - 149);
  if ( !(_DWORD)v9 )
    return CAdvScheduleDlg::_OnInitDialog((CAdvScheduleDlg *)this, v9);
  if ( (_DWORD)v9 == 1 )
    return CAdvScheduleDlg::_OnCommand(this, (unsigned __int16)a3, a3);
  return 0;
}

```

## disassembly

```asm
0x180018540  sub     rsp, 28h
0x180018544  mov     r10, r9
0x180018547  mov     rax, r8
0x18001854a  sub     edx, 2
0x18001854d  jz      short loc_1800185B6
0x18001854f  sub     edx, 18h; unsigned __int64
0x180018552  jz      short loc_1800185AF
0x180018554  sub     edx, 39h ; '9'
0x180018557  jz      short loc_1800185A3
0x180018559  sub     edx, 28h ; '('
0x18001855c  jz      short loc_180018584
0x18001855e  sub     edx, 95h; __int64
0x180018564  jz      short loc_18001857B
0x180018566  cmp     edx, 1
0x180018569  jz      short loc_18001856F
0x18001856b  xor     eax, eax
0x18001856d  jmp     short loc_1800185CC
0x18001856f  movzx   edx, ax; int
0x180018572  add     rsp, 28h
0x180018576  jmp     ?_OnCommand@CAdvScheduleDlg@@AEAA_JHPEAUHWND__@@I@Z; CAdvScheduleDlg::_OnCommand(int,HWND__ *,uint)
0x18001857b  add     rsp, 28h
0x18001857f  jmp     ?_OnInitDialog@CAdvScheduleDlg@@AEAA_J_J@Z; CAdvScheduleDlg::_OnInitDialog(__int64)
0x180018584  mov     r8d, 0Ah; uCommand
0x18001858a  mov     rcx, rax; hWndMain
0x18001858d  lea     rdx, szMstaskHelp; "%windir%\\help\\mstask.hlp"
0x180018594  lea     r9, ?s_aAdvancedDlgHelpIds@@3PAKA; dwData
0x18001859b  call    cs:__imp_WinHelpW
0x1800185a1  jmp     short loc_1800185C7
0x1800185a3  mov     rcx, [r10+10h]; this
0x1800185a7  mov     r8d, 0Ch; __int64
0x1800185ad  jmp     short loc_18001858D
0x1800185af  call    ?_OnSetIniChange@CAdvScheduleDlg@@AEAA_J_K_J@Z; CAdvScheduleDlg::_OnSetIniChange(unsigned __int64,__int64)
0x1800185b4  jmp     short loc_1800185C7
0x1800185b6  mov     rcx, [rcx+8]; hWnd
0x1800185ba  xor     r8d, r8d; dwNewLong
0x1800185bd  lea     edx, [r8+10h]; nIndex
0x1800185c1  call    cs:__imp_SetWindowLongPtrW
0x1800185c7  mov     eax, 1
0x1800185cc  add     rsp, 28h
0x1800185d0  retn
```
