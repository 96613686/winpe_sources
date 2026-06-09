# CAdvScheduleDlg::_OnCommand(int,HWND__ *,uint)

- ea: `0x180018780`
- end: `0x180018a0e`
- name: `?_OnCommand@CAdvScheduleDlg@@AEAA_JHPEAUHWND__@@I@Z`
- size: `654`
- prototype: `__int64 __fastcall(CAdvScheduleDlg *__hidden this, int, HWND, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018540`

## callees

- `0x180013404`
- `0x18001347c`
- `0x1800185d8`
- `0x180018780`
- `0x180018edc`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800187b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800187b3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001887e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001887e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180018862`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180018870`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180018862`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180018870`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018894`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180018894`
- `USER32!SendMessageW` at `0x180018850`
- `USER32!SendMessageW` at `0x1800188c4`
- `USER32!SendMessageW` at `0x1800188dc`
- `USER32!SendMessageW` at `0x180018910`
- `USER32!SendMessageW` at `0x180018985`
- `USER32!SendMessageW` at `0x180018850`
- `USER32!SendMessageW` at `0x1800188c4`
- `USER32!SendMessageW` at `0x1800188dc`
- `USER32!SendMessageW` at `0x180018910`
- `USER32!SendMessageW` at `0x180018985`
- `USER32!EnableWindow` at `0x18001891b`
- `USER32!EnableWindow` at `0x180018970`
- `USER32!EnableWindow` at `0x18001891b`
- `USER32!EnableWindow` at `0x180018970`
- `USER32!GetDlgItem` at `0x180018836`
- `USER32!GetDlgItem` at `0x1800188a3`
- `USER32!GetDlgItem` at `0x1800188ec`
- `USER32!GetDlgItem` at `0x18001895c`
- `USER32!GetDlgItem` at `0x180018836`
- `USER32!GetDlgItem` at `0x1800188a3`
- `USER32!GetDlgItem` at `0x1800188ec`
- `USER32!GetDlgItem` at `0x18001895c`
- `USER32!EndDialog` at `0x1800189e4`
- `USER32!EndDialog` at `0x1800189e4`
- `USER32!IsDlgButtonChecked` at `0x180018804`
- `USER32!IsDlgButtonChecked` at `0x1800189b2`
- `USER32!IsDlgButtonChecked` at `0x180018804`
- `USER32!IsDlgButtonChecked` at `0x1800189b2`

## pseudocode

```c
__int64 __fastcall CAdvScheduleDlg::_OnCommand(HWND *this, int a2, HWND a3)
{
  int v5; // ebx
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  int v9; // ebx
  UINT v11; // eax
  HWND v12; // rcx
  HWND v13; // rax
  LONG v14; // eax
  FILETIME *p_FileTime2; // rcx
  HWND v16; // rax
  HWND v17; // rdi
  BOOL v18; // edx
  int v19; // edx
  HWND v20; // rax
  HWND DlgItem; // rax
  HWND v22; // rsi
  UINT v23; // eax
  INT_PTR v24; // rdx
  FILETIME FileTime2; // [rsp+20h] [rbp-50h] BYREF
  struct _FILETIME FileTime; // [rsp+28h] [rbp-48h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-40h] BYREF
  struct _SYSTEMTIME v28; // [rsp+40h] [rbp-30h] BYREF
  LPARAM lParam[2]; // [rsp+50h] [rbp-20h] BYREF

  SystemTime = 0;
  GetSystemTime(&SystemTime);
  v5 = a2 - 1;
  if ( !v5 )
  {
    if ( (unsigned int)CAdvScheduleDlg::_OnOK((CAdvScheduleDlg *)this) != 1 )
      return 1;
    v24 = 1;
LABEL_28:
    EndDialog(this[1], v24);
    return 1;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    v24 = 0;
    goto LABEL_28;
  }
  v7 = v6 - 1772;
  if ( !v7 )
  {
    v23 = IsDlgButtonChecked(this[1], 1774);
    CAdvScheduleDlg::_EnableRepeatCtrls((CAdvScheduleDlg *)this, v23 == 1);
    return 1;
  }
  v8 = v7 - 6;
  if ( !v8 )
  {
    DlgItem = GetDlgItem(this[1], 1782);
    v22 = DlgItem;
    if ( DlgItem )
    {
      EnableWindow(DlgItem, 1);
      SendMessageW(v22, 0x1032u, 0, (LPARAM)(this + 3));
    }
    Spin_Disable(this[1], 1784);
    Spin_Disable(this[1], 1786);
    return 1;
  }
  v9 = v8 - 1;
  if ( v9 )
  {
    if ( v9 != 9 )
      return 0;
    v11 = IsDlgButtonChecked(this[1], 1790);
    v12 = this[1];
    if ( v11 == 1 )
    {
      FileTime2 = 0;
      FileTime = 0;
      *(_OWORD *)lParam = 0;
      v28 = SystemTime;
      v13 = GetDlgItem(v12, 1773);
      if ( v13 && !(unsigned int)SendMessageW(v13, 0x1001u, 0, (LPARAM)lParam) )
      {
        SystemTimeToFileTime((const SYSTEMTIME *)lParam, &FileTime);
        SystemTimeToFileTime(&SystemTime, &FileTime2);
        v14 = CompareFileTime(&FileTime, &FileTime2);
        p_FileTime2 = &FileTime2;
        if ( v14 > 0 )
          p_FileTime2 = &FileTime;
        FileTimeToSystemTime(p_FileTime2, &v28);
      }
      v16 = GetDlgItem(this[1], 1778);
      v17 = v16;
      if ( !v16 )
        return 1;
      SendMessageW(v16, 0x1002u, 0, (LPARAM)&v28);
      SendMessageW(v17, 0x1032u, 0, (LPARAM)&String);
      v18 = 1;
      goto LABEL_19;
    }
    v19 = 1778;
  }
  else
  {
    Spin_Enable(this[1], 1784, 1u);
    Spin_Enable(this[1], 1786, 0);
    v12 = this[1];
    v19 = 1782;
  }
  v20 = GetDlgItem(v12, v19);
  v17 = v20;
  if ( v20 )
  {
    SendMessageW(v20, 0x1032u, 0, (LPARAM)L" ");
    v18 = 0;
LABEL_19:
    EnableWindow(v17, v18);
  }
  return 1;
}

```

## disassembly

```asm
0x180018780  mov     [rsp-18h+arg_8], rbx
0x180018785  mov     [rsp-18h+arg_10], rsi
0x18001878a  push    rbp
0x18001878b  push    rdi
0x18001878c  push    r14
0x18001878e  mov     rbp, rsp
0x180018791  sub     rsp, 70h
0x180018795  mov     rax, cs:__security_cookie
0x18001879c  xor     rax, rsp
0x18001879f  mov     [rbp+var_10], rax
0x1800187a3  mov     rdi, rcx
0x1800187a6  xorps   xmm0, xmm0
0x1800187a9  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800187ad  mov     ebx, edx
0x1800187af  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800187b3  call    cs:__imp_GetSystemTime
0x1800187b9  mov     r14d, 1
0x1800187bf  sub     ebx, r14d
0x1800187c2  jz      loc_1800189D0
0x1800187c8  sub     ebx, r14d
0x1800187cb  jz      loc_1800189CC
0x1800187d1  sub     ebx, 6ECh
0x1800187d7  jz      loc_1800189A9
0x1800187dd  sub     ebx, 6
0x1800187e0  jz      loc_180018953
0x1800187e6  sub     ebx, r14d
0x1800187e9  jz      loc_180018926
0x1800187ef  cmp     ebx, 9
0x1800187f2  jz      short loc_1800187FB
0x1800187f4  xor     eax, eax
0x1800187f6  jmp     loc_1800189ED
0x1800187fb  mov     rcx, [rdi+8]; hDlg
0x1800187ff  mov     edx, 6FEh; nIDButton
0x180018804  call    cs:__imp_IsDlgButtonChecked
0x18001880a  mov     rcx, [rdi+8]; hDlg
0x18001880e  cmp     eax, r14d
0x180018811  jnz     loc_1800188E7
0x180018817  movaps  xmm1, xmmword ptr [rbp+SystemTime.wYear]
0x18001881b  xor     ebx, ebx
0x18001881d  xorps   xmm0, xmm0
0x180018820  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rbx
0x180018824  mov     edx, 6EDh; nIDDlgItem
0x180018829  mov     qword ptr [rbp+FileTime.dwLowDateTime], rbx
0x18001882d  movups  xmmword ptr [rbp+lParam], xmm0
0x180018831  movdqa  xmmword ptr [rbp+var_30.wYear], xmm1
0x180018836  call    cs:__imp_GetDlgItem
0x18001883c  test    rax, rax
0x18001883f  jz      short loc_18001889A
0x180018841  lea     r9, [rbp+lParam]; lParam
0x180018845  xor     r8d, r8d; wParam
0x180018848  mov     edx, 1001h; Msg
0x18001884d  mov     rcx, rax; hWnd
0x180018850  call    cs:__imp_SendMessageW
0x180018856  test    eax, eax
0x180018858  jnz     short loc_18001889A
0x18001885a  lea     rdx, [rbp+FileTime]; lpFileTime
0x18001885e  lea     rcx, [rbp+lParam]; lpSystemTime
0x180018862  call    cs:__imp_SystemTimeToFileTime
0x180018868  lea     rdx, [rbp+FileTime2]; lpFileTime
0x18001886c  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180018870  call    cs:__imp_SystemTimeToFileTime
0x180018876  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18001887a  lea     rcx, [rbp+FileTime]; lpFileTime1
0x18001887e  call    cs:__imp_CompareFileTime
0x180018884  lea     rdx, [rbp+var_30]; lpSystemTime
0x180018888  lea     rcx, [rbp+FileTime2]
0x18001888c  test    eax, eax
0x18001888e  jle     short loc_180018894
0x180018890  lea     rcx, [rbp+FileTime]; lpFileTime
0x180018894  call    cs:__imp_FileTimeToSystemTime
0x18001889a  mov     rcx, [rdi+8]; hDlg
0x18001889e  mov     edx, 6F2h; nIDDlgItem
0x1800188a3  call    cs:__imp_GetDlgItem
0x1800188a9  mov     rdi, rax
0x1800188ac  test    rax, rax
0x1800188af  jz      loc_1800189EA
0x1800188b5  lea     r9, [rbp+var_30]; lParam
0x1800188b9  xor     r8d, r8d; wParam
0x1800188bc  mov     edx, 1002h; Msg
0x1800188c1  mov     rcx, rax; hWnd
0x1800188c4  call    cs:__imp_SendMessageW
0x1800188ca  lea     r9, String; lParam
0x1800188d1  xor     r8d, r8d; wParam
0x1800188d4  mov     edx, 1032h; Msg
0x1800188d9  mov     rcx, rdi; hWnd
0x1800188dc  call    cs:__imp_SendMessageW
0x1800188e2  mov     edx, r14d
0x1800188e5  jmp     short loc_180018918
0x1800188e7  mov     edx, 6F2h; nIDDlgItem
0x1800188ec  call    cs:__imp_GetDlgItem
0x1800188f2  mov     rdi, rax
0x1800188f5  test    rax, rax
0x1800188f8  jz      loc_1800189EA
0x1800188fe  lea     r9, lParam; " "
0x180018905  xor     r8d, r8d; wParam
0x180018908  mov     edx, 1032h; Msg
0x18001890d  mov     rcx, rax; hWnd
0x180018910  call    cs:__imp_SendMessageW
0x180018916  xor     edx, edx; bEnable
0x180018918  mov     rcx, rdi; hWnd
0x18001891b  call    cs:__imp_EnableWindow
0x180018921  jmp     loc_1800189EA
0x180018926  mov     rcx, [rdi+8]; hDlg
0x18001892a  mov     r8d, r14d; unsigned __int16
0x18001892d  mov     edx, 6F8h; nIDDlgItem
0x180018932  call    ?Spin_Enable@@YAXPEAUHWND__@@HG@Z; Spin_Enable(HWND__ *,int,ushort)
0x180018937  mov     rcx, [rdi+8]; hDlg
0x18001893b  xor     r8d, r8d; unsigned __int16
0x18001893e  mov     edx, 6FAh; nIDDlgItem
0x180018943  call    ?Spin_Enable@@YAXPEAUHWND__@@HG@Z; Spin_Enable(HWND__ *,int,ushort)
0x180018948  mov     rcx, [rdi+8]
0x18001894c  mov     edx, 6F6h
0x180018951  jmp     short loc_1800188EC
0x180018953  mov     rcx, [rdi+8]; hDlg
0x180018957  mov     edx, 6F6h; nIDDlgItem
0x18001895c  call    cs:__imp_GetDlgItem
0x180018962  mov     rsi, rax
0x180018965  test    rax, rax
0x180018968  jz      short loc_18001898B
0x18001896a  mov     edx, r14d; bEnable
0x18001896d  mov     rcx, rax; hWnd
0x180018970  call    cs:__imp_EnableWindow
0x180018976  lea     r9, [rdi+18h]; lParam
0x18001897a  xor     r8d, r8d; wParam
0x18001897d  mov     edx, 1032h; Msg
0x180018982  mov     rcx, rsi; hWnd
0x180018985  call    cs:__imp_SendMessageW
0x18001898b  mov     rcx, [rdi+8]; hDlg
0x18001898f  mov     edx, 6F8h; nIDDlgItem
0x180018994  call    ?Spin_Disable@@YAXPEAUHWND__@@H@Z; Spin_Disable(HWND__ *,int)
0x180018999  mov     rcx, [rdi+8]; hDlg
0x18001899d  mov     edx, 6FAh; nIDDlgItem
0x1800189a2  call    ?Spin_Disable@@YAXPEAUHWND__@@H@Z; Spin_Disable(HWND__ *,int)
0x1800189a7  jmp     short loc_1800189EA
0x1800189a9  mov     rcx, [rdi+8]; hDlg
0x1800189ad  mov     edx, 6EEh; nIDButton
0x1800189b2  call    cs:__imp_IsDlgButtonChecked
0x1800189b8  xor     ebx, ebx
0x1800189ba  mov     rcx, rdi; this
0x1800189bd  cmp     eax, r14d
0x1800189c0  setz    bl
0x1800189c3  mov     edx, ebx; int
0x1800189c5  call    ?_EnableRepeatCtrls@CAdvScheduleDlg@@AEAAXH@Z; CAdvScheduleDlg::_EnableRepeatCtrls(int)
0x1800189ca  jmp     short loc_1800189EA
0x1800189cc  xor     edx, edx
0x1800189ce  jmp     short loc_1800189E0
0x1800189d0  mov     rcx, rdi; this
0x1800189d3  call    ?_OnOK@CAdvScheduleDlg@@AEAAHXZ; CAdvScheduleDlg::_OnOK(void)
0x1800189d8  cmp     eax, r14d
0x1800189db  jnz     short loc_1800189EA
0x1800189dd  mov     rdx, r14; nResult
0x1800189e0  mov     rcx, [rdi+8]; hDlg
0x1800189e4  call    cs:__imp_EndDialog
0x1800189ea  mov     rax, r14
0x1800189ed  mov     rcx, [rbp+var_10]
0x1800189f1  xor     rcx, rsp; StackCookie
0x1800189f4  call    __security_check_cookie
0x1800189f9  lea     r11, [rsp+70h+var_s0]
0x1800189fe  mov     rbx, [r11+28h]
0x180018a02  mov     rsi, [r11+30h]
0x180018a06  mov     rsp, r11
0x180018a09  pop     r14
0x180018a0b  pop     rdi
0x180018a0c  pop     rbp
0x180018a0d  retn
```
