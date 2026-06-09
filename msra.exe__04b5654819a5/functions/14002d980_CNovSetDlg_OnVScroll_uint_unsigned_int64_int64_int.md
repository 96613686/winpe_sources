# CNovSetDlg::OnVScroll(uint,unsigned __int64,__int64,int &)

- ea: `0x14002d980`
- end: `0x14002df53`
- name: `?OnVScroll@CNovSetDlg@@QEAA_JI_K_JAEAH@Z`
- size: `1491`
- prototype: `__int64 __fastcall(CNovSetDlg *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x140023d70`
- `0x14002d3f4`

## callees

- `0x140002463`
- `0x140007fc4`
- `0x14002d980`
- `0x140034ce4`
- `0x14004ad80`
- `0x14004ae40`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14002dc94`
- `KERNEL32!GetModuleHandleW` at `0x14002dcd5`
- `KERNEL32!GetModuleHandleW` at `0x14002dd21`
- `KERNEL32!GetModuleHandleW` at `0x14002dd8e`
- `KERNEL32!GetModuleHandleW` at `0x14002de17`
- `KERNEL32!GetModuleHandleW` at `0x14002de8e`
- `KERNEL32!GetModuleHandleW` at `0x14002dc94`
- `KERNEL32!GetModuleHandleW` at `0x14002dcd5`
- `KERNEL32!GetModuleHandleW` at `0x14002dd21`
- `KERNEL32!GetModuleHandleW` at `0x14002dd8e`
- `KERNEL32!GetModuleHandleW` at `0x14002de17`
- `KERNEL32!GetModuleHandleW` at `0x14002de8e`
- `KERNEL32!GetLastError` at `0x14002da5a`
- `KERNEL32!GetLastError` at `0x14002da6e`
- `KERNEL32!GetLastError` at `0x14002da5a`
- `KERNEL32!GetLastError` at `0x14002da6e`
- `USER32!SendMessageW` at `0x14002da9f`
- `USER32!SendMessageW` at `0x14002da9f`
- `USER32!LoadStringW` at `0x14002dcb1`
- `USER32!LoadStringW` at `0x14002dcf6`
- `USER32!LoadStringW` at `0x14002dd42`
- `USER32!LoadStringW` at `0x14002ddaf`
- `USER32!LoadStringW` at `0x14002de38`
- `USER32!LoadStringW` at `0x14002deaf`
- `USER32!LoadStringW` at `0x14002dcb1`
- `USER32!LoadStringW` at `0x14002dcf6`
- `USER32!LoadStringW` at `0x14002dd42`
- `USER32!LoadStringW` at `0x14002ddaf`
- `USER32!LoadStringW` at `0x14002de38`
- `USER32!LoadStringW` at `0x14002deaf`
- `USER32!GetDlgItem` at `0x14002da3e`
- `USER32!GetDlgItem` at `0x14002dedb`
- `USER32!GetDlgItem` at `0x14002df04`
- `USER32!GetDlgItem` at `0x14002da3e`
- `USER32!GetDlgItem` at `0x14002dedb`
- `USER32!GetDlgItem` at `0x14002df04`
- `USER32!ScrollWindow` at `0x14002dc08`
- `USER32!ScrollWindow` at `0x14002dc08`
- `USER32!GetScrollInfo` at `0x14002da29`
- `USER32!GetScrollInfo` at `0x14002dbd3`
- `USER32!GetScrollInfo` at `0x14002da29`
- `USER32!GetScrollInfo` at `0x14002dbd3`
- `USER32!SetScrollInfo` at `0x14002dbb9`
- `USER32!SetScrollInfo` at `0x14002dbb9`
- `USER32!UpdateWindow` at `0x14002dc18`
- `USER32!UpdateWindow` at `0x14002dc18`
- `USER32!SetWindowTextW` at `0x14002deef`
- `USER32!SetWindowTextW` at `0x14002df1a`
- `USER32!SetWindowTextW` at `0x14002deef`
- `USER32!SetWindowTextW` at `0x14002df1a`

## pseudocode

```c
__int64 __fastcall CNovSetDlg::OnVScroll(CNovSetDlg *this, __int64 a2, int a3, __int64 a4)
{
  HWND v6; // rcx
  HWND DlgItem; // rbx
  CEventLogger *v8; // rcx
  signed int LastError; // eax
  bool v10; // sf
  UINT v11; // r15d
  int v12; // eax
  CEventLogger *v13; // rcx
  int v14; // r14d
  int v15; // eax
  int v16; // eax
  unsigned int v17; // r9d
  int v18; // ecx
  HWND v19; // rcx
  int v20; // r14d
  int v21; // r14d
  HMODULE v22; // rax
  HMODULE v23; // rax
  HMODULE v24; // rax
  int v25; // eax
  int v26; // eax
  HMODULE ModuleHandleW; // rax
  int StringW; // eax
  int v29; // eax
  HMODULE v30; // rax
  int v31; // eax
  int v32; // eax
  HMODULE v33; // rax
  int v34; // eax
  HWND v35; // rax
  HWND v36; // rax
  unsigned int v38; // [rsp+28h] [rbp-D8h]
  SCROLLINFO v40; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[256]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v42[1024]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR String[1024]; // [rsp+A60h] [rbp+960h] BYREF

  memset_0(v42, 0, sizeof(v42));
  memset_0(String, 0, sizeof(String));
  memset_0(Buffer, 0, sizeof(Buffer));
  v6 = (HWND)*((_QWORD *)this + 1);
  v40.cbSize = 28;
  memset(&v40.nMin, 0, 20);
  v40.fMask = 23;
  GetScrollInfo(v6, 1, &v40);
  DlgItem = GetDlgItem(*((HWND *)this + 1), 1046);
  if ( (((unsigned __int64)DlgItem + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_6;
  if ( GetLastError() )
  {
    LastError = GetLastError();
    v10 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v10 = LastError < 0;
    }
    if ( !v10 )
    {
LABEL_6:
      v11 = 0;
      v12 = SendMessageW(DlgItem, 0x400u, 0, 0);
      v14 = v12;
      if ( a4 )
      {
        if ( !(_WORD)a3
          || (unsigned __int16)a3 == 1
          || (unsigned __int16)a3 == 2
          || (unsigned __int16)a3 == 3
          || (unsigned __int16)a3 == 5
          || (unsigned int)(unsigned __int16)a3 - 6 <= 1 )
        {
          if ( !v12 )
            goto LABEL_59;
          v15 = v12 - 1;
          if ( !v15 )
            goto LABEL_54;
          v16 = v15 - 1;
          if ( !v16 )
            goto LABEL_48;
          if ( v16 == 1 )
            goto LABEL_40;
          CEventLogger::LogError(
            v13,
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\ui\\novsettingsdialog.cpp",
            0x201u,
            L"CNovSetDlg::OnVScroll",
            0);
        }
LABEL_30:
        if ( v14 )
        {
          if ( v14 != 1 )
          {
            if ( v14 != 2 )
            {
              if ( v14 != 3 )
              {
                CEventLogger::LogError(
                  v13,
                  &Recoverable_Error,
                  L"base\\diagnosis\\ra\\ui\\novsettingsdialog.cpp",
                  0x245u,
                  L"CNovSetDlg::OnVScroll",
                  0);
                v20 = v14 - 1;
                if ( v20 )
                {
                  v21 = v20 - 1;
                  if ( v21 )
                  {
                    if ( v21 != 1 )
                      goto LABEL_37;
                    goto LABEL_41;
                  }
LABEL_49:
                  ModuleHandleW = GetModuleHandleW(0);
                  StringW = LoadStringW(ModuleHandleW, 0x240u, v42, 1024);
                  if ( StringW < 0 )
                  {
                    v38 = StringW;
                    v17 = 626;
                    goto LABEL_20;
                  }
                  v29 = StringCchCatW(String, 0x400u, v42);
                  if ( v29 < 0 )
                  {
                    v38 = v29;
                    v17 = 631;
                    goto LABEL_20;
                  }
                  memset_0(v42, 0, sizeof(v42));
                }
LABEL_55:
                v30 = GetModuleHandleW(0);
                v31 = LoadStringW(v30, 0x23Fu, v42, 1024);
                if ( v31 < 0 )
                {
                  v38 = v31;
                  v17 = 648;
                  goto LABEL_20;
                }
                v32 = StringCchCatW(String, 0x400u, v42);
                if ( v32 < 0 )
                {
                  v38 = v32;
                  v17 = 653;
                  goto LABEL_20;
                }
LABEL_37:
                if ( v11 )
                {
                  v22 = GetModuleHandleW(0);
                  if ( !LoadStringW(v22, v11, Buffer, 256) )
                  {
                    v17 = 688;
LABEL_43:
                    v38 = 0;
                    goto LABEL_20;
                  }
                  v35 = GetDlgItem(*((HWND *)this + 1), 1048);
                  SetWindowTextW(v35, Buffer);
                }
                v36 = GetDlgItem(*((HWND *)this + 1), 1045);
                SetWindowTextW(v36, String);
                return 0;
              }
LABEL_40:
              v11 = 559;
LABEL_41:
              v23 = GetModuleHandleW(0);
              if ( !LoadStringW(v23, 0x23Eu, String, 1024) )
              {
                v17 = 601;
                goto LABEL_43;
              }
              v24 = GetModuleHandleW(0);
              v25 = LoadStringW(v24, 0x2A9u, v42, 1024);
              if ( v25 < 0 )
              {
                v38 = v25;
                v17 = 610;
                goto LABEL_20;
              }
              v26 = StringCchCatW(String, 0x400u, v42);
              if ( v26 < 0 )
              {
                v38 = v26;
                v17 = 615;
                goto LABEL_20;
              }
              goto LABEL_49;
            }
LABEL_48:
            v11 = 569;
            goto LABEL_49;
          }
LABEL_54:
          v11 = 663;
          goto LABEL_55;
        }
LABEL_59:
        v11 = 706;
        v33 = GetModuleHandleW(0);
        v34 = LoadStringW(v33, 0x242u, String, 1024);
        if ( v34 < 0 )
        {
          v38 = v34;
          v17 = 666;
          goto LABEL_20;
        }
        goto LABEL_37;
      }
      dword_1400642A0 = v40.nPos;
      if ( (_WORD)a3 )
      {
        if ( (unsigned __int16)a3 != 1 )
        {
          if ( (unsigned __int16)a3 == 5 )
            v40.nPos = HIWORD(a3);
          goto LABEL_28;
        }
        v18 = v40.nPos + 1;
      }
      else
      {
        v18 = v40.nPos - 1;
      }
      v40.nPos = v18;
LABEL_28:
      v19 = (HWND)*((_QWORD *)this + 1);
      v40.fMask = 4;
      SetScrollInfo(v19, 1, &v40, 1);
      GetScrollInfo(*((HWND *)this + 1), 1, &v40);
      if ( v40.nPos != dword_1400642A0 )
      {
        ScrollWindow(*((HWND *)this + 1), 0, dword_140064234 * (dword_1400642A0 - v40.nPos), 0, 0);
        UpdateWindow(*((HWND *)this + 1));
      }
      goto LABEL_30;
    }
  }
  else
  {
    LastError = -2147467259;
  }
  v38 = LastError;
  v17 = 467;
LABEL_20:
  CEventLogger::LogError(
    v8,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\novsettingsdialog.cpp",
    v17,
    L"CNovSetDlg::OnVScroll",
    v38);
  return 0;
}

```

## disassembly

```asm
0x14002d980  mov     [rsp-8+arg_8], rbx
0x14002d985  push    rbp
0x14002d986  push    rsi
0x14002d987  push    rdi
0x14002d988  push    r12
0x14002d98a  push    r13
0x14002d98c  push    r14
0x14002d98e  push    r15
0x14002d990  lea     rbp, [rsp-1170h]
0x14002d998  mov     eax, 1270h
0x14002d99d  call    _alloca_probe
0x14002d9a2  sub     rsp, rax
0x14002d9a5  mov     rax, cs:__security_cookie
0x14002d9ac  xor     rax, rsp
0x14002d9af  mov     [rbp+11A0h+var_40], rax
0x14002d9b6  mov     r12, r8
0x14002d9b9  mov     [rsp+12A0h+var_1270], r9
0x14002d9be  mov     r13, rcx
0x14002d9c1  mov     ebx, 800h
0x14002d9c6  mov     r8d, ebx; Size
0x14002d9c9  lea     rcx, [rbp+11A0h+var_1040]; void *
0x14002d9d0  xor     edx, edx; Val
0x14002d9d2  call    memset_0
0x14002d9d7  mov     r8d, ebx; Size
0x14002d9da  lea     rcx, [rbp+11A0h+String]; void *
0x14002d9e1  xor     edx, edx; Val
0x14002d9e3  call    memset_0
0x14002d9e8  xor     edx, edx; Val
0x14002d9ea  lea     rcx, [rsp+12A0h+Buffer]; void *
0x14002d9ef  mov     r8d, 200h; Size
0x14002d9f5  call    memset_0
0x14002d9fa  mov     rcx, [r13+8]; hwnd
0x14002d9fe  lea     r8, [rsp+12A0h+var_1268]; lpsi
0x14002da03  xorps   xmm0, xmm0
0x14002da06  mov     [rsp+12A0h+var_1268.nTrackPos], 0
0x14002da0e  mov     edx, 1; nBar
0x14002da13  mov     [rsp+12A0h+var_1268.cbSize], 1Ch
0x14002da1b  movdqu  xmmword ptr [rsp+12A0h+var_1268.nMin], xmm0
0x14002da21  mov     [rsp+12A0h+var_1268.fMask], 17h
0x14002da29  call    cs:__imp_GetScrollInfo
0x14002da30  nop     dword ptr [rax+rax+00h]
0x14002da35  mov     rcx, [r13+8]; hDlg
0x14002da39  mov     edx, 416h; nIDDlgItem
0x14002da3e  call    cs:__imp_GetDlgItem
0x14002da45  nop     dword ptr [rax+rax+00h]
0x14002da4a  mov     rbx, rax
0x14002da4d  lea     rcx, [rax+1]
0x14002da51  test    rcx, 0FFFFFFFFFFFFFFFEh
0x14002da58  jnz     short loc_14002DA8E
0x14002da5a  call    cs:__imp_GetLastError
0x14002da61  nop     dword ptr [rax+rax+00h]
0x14002da66  test    eax, eax
0x14002da68  jz      loc_14002DB3C
0x14002da6e  call    cs:__imp_GetLastError
0x14002da75  nop     dword ptr [rax+rax+00h]
0x14002da7a  test    eax, eax
0x14002da7c  jle     short loc_14002DA88
0x14002da7e  movzx   eax, ax
0x14002da81  or      eax, 80070000h
0x14002da86  test    eax, eax
0x14002da88  js      loc_14002DB41
0x14002da8e  xor     r9d, r9d; lParam
0x14002da91  xor     r8d, r8d; wParam
0x14002da94  mov     edx, 400h; Msg
0x14002da99  mov     rcx, rbx; hWnd
0x14002da9c  xor     r15d, r15d
0x14002da9f  call    cs:__imp_SendMessageW
0x14002daa6  nop     dword ptr [rax+rax+00h]
0x14002daab  lea     rsi, aCnovsetdlgOnvs; "CNovSetDlg::OnVScroll"
0x14002dab2  mov     r14, rax
0x14002dab5  lea     rbx, aBaseDiagnosisR_17; "base\\diagnosis\\ra\\ui\\novsettingsdia"...
0x14002dabc  movzx   edx, r12w
0x14002dac0  lea     rdi, Recoverable_Error
0x14002dac7  cmp     [rsp+12A0h+var_1270], r15
0x14002dacc  jz      loc_14002DB6F
0x14002dad2  test    edx, edx
0x14002dad4  jz      short loc_14002DAF8
0x14002dad6  sub     edx, 1
0x14002dad9  jz      short loc_14002DAF8
0x14002dadb  sub     edx, 1
0x14002dade  jz      short loc_14002DAF8
0x14002dae0  sub     edx, 1
0x14002dae3  jz      short loc_14002DAF8
0x14002dae5  sub     edx, 2
0x14002dae8  jz      short loc_14002DAF8
0x14002daea  sub     edx, 1
0x14002daed  jz      short loc_14002DAF8
0x14002daef  cmp     edx, 1
0x14002daf2  jnz     loc_14002DC24
0x14002daf8  test    r14d, r14d
0x14002dafb  jz      loc_14002DE86
0x14002db01  sub     eax, 1
0x14002db04  jz      loc_14002DE0F
0x14002db0a  sub     eax, 1
0x14002db0d  jz      loc_14002DD86
0x14002db13  cmp     eax, 1
0x14002db16  jz      loc_14002DCCD
0x14002db1c  mov     [rsp+12A0h+var_1278], r15d; unsigned int
0x14002db21  mov     r9d, 201h; unsigned int
0x14002db27  mov     r8, rbx; unsigned __int16 *
0x14002db2a  mov     [rsp+12A0h+lpClipRect], rsi; unsigned __int16 *
0x14002db2f  mov     rdx, rdi; struct _EVENT_DESCRIPTOR *
0x14002db32  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002db37  jmp     loc_14002DC24
0x14002db3c  mov     eax, 80004005h
0x14002db41  mov     [rsp+12A0h+var_1278], eax; unsigned int
0x14002db45  lea     rsi, aCnovsetdlgOnvs; "CNovSetDlg::OnVScroll"
0x14002db4c  mov     r9d, 1D3h; unsigned int
0x14002db52  lea     r8, aBaseDiagnosisR_17; "base\\diagnosis\\ra\\ui\\novsettingsdia"...
0x14002db59  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002db60  mov     [rsp+12A0h+lpClipRect], rsi; unsigned __int16 *
0x14002db65  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002db6a  jmp     loc_14002DF26
0x14002db6f  mov     ecx, [rsp+12A0h+var_1268.nPos]
0x14002db73  mov     cs:dword_1400642A0, ecx
0x14002db79  test    edx, edx
0x14002db7b  jz      short loc_14002DB99
0x14002db7d  sub     edx, 1
0x14002db80  jz      short loc_14002DB95
0x14002db82  cmp     edx, 4
0x14002db85  jnz     short loc_14002DB9F
0x14002db87  shr     r12, 10h
0x14002db8b  movzx   eax, r12w
0x14002db8f  mov     [rsp+12A0h+var_1268.nPos], eax
0x14002db93  jmp     short loc_14002DB9F
0x14002db95  inc     ecx
0x14002db97  jmp     short loc_14002DB9B
0x14002db99  dec     ecx
0x14002db9b  mov     [rsp+12A0h+var_1268.nPos], ecx
0x14002db9f  mov     rcx, [r13+8]; hwnd
0x14002dba3  lea     r8, [rsp+12A0h+var_1268]; lpsi
0x14002dba8  mov     r9d, 1; redraw
0x14002dbae  mov     [rsp+12A0h+var_1268.fMask], 4
0x14002dbb6  mov     edx, r9d; nBar
0x14002dbb9  call    cs:__imp_SetScrollInfo
0x14002dbc0  nop     dword ptr [rax+rax+00h]
0x14002dbc5  mov     rcx, [r13+8]; hwnd
0x14002dbc9  lea     r8, [rsp+12A0h+var_1268]; lpsi
0x14002dbce  mov     edx, 1; nBar
0x14002dbd3  call    cs:__imp_GetScrollInfo
0x14002dbda  nop     dword ptr [rax+rax+00h]
0x14002dbdf  mov     r8d, cs:dword_1400642A0
0x14002dbe6  cmp     [rsp+12A0h+var_1268.nPos], r8d
0x14002dbeb  jz      short loc_14002DC24
0x14002dbed  sub     r8d, [rsp+12A0h+var_1268.nPos]
0x14002dbf2  xor     r9d, r9d; lpRect
0x14002dbf5  imul    r8d, cs:dword_140064234; YAmount
0x14002dbfd  xor     edx, edx; XAmount
0x14002dbff  mov     rcx, [r13+8]; hWnd
0x14002dc03  mov     [rsp+12A0h+lpClipRect], r15; lpClipRect
0x14002dc08  call    cs:__imp_ScrollWindow
0x14002dc0f  nop     dword ptr [rax+rax+00h]
0x14002dc14  mov     rcx, [r13+8]; hWnd
0x14002dc18  call    cs:__imp_UpdateWindow
0x14002dc1f  nop     dword ptr [rax+rax+00h]
0x14002dc24  mov     eax, r14d
0x14002dc27  test    r14d, r14d
0x14002dc2a  jz      loc_14002DE86
0x14002dc30  sub     eax, 1
0x14002dc33  jz      loc_14002DE0F
0x14002dc39  sub     eax, 1
0x14002dc3c  jz      loc_14002DD86
0x14002dc42  cmp     eax, 1
0x14002dc45  jz      loc_14002DCCD
0x14002dc4b  mov     [rsp+12A0h+var_1278], r15d; unsigned int
0x14002dc50  mov     r9d, 245h; unsigned int
0x14002dc56  mov     r8, rbx; unsigned __int16 *
0x14002dc59  mov     [rsp+12A0h+lpClipRect], rsi; unsigned __int16 *
0x14002dc5e  mov     rdx, rdi; struct _EVENT_DESCRIPTOR *
0x14002dc61  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002dc66  test    r14d, r14d
0x14002dc69  jz      loc_14002DE8C
0x14002dc6f  sub     r14d, 1
0x14002dc73  jz      loc_14002DE15
0x14002dc79  sub     r14d, 1
0x14002dc7d  jz      loc_14002DD8C
0x14002dc83  cmp     r14d, 1
0x14002dc87  jz      short loc_14002DCD3
0x14002dc89  test    r15d, r15d
0x14002dc8c  jz      loc_14002DEFB
0x14002dc92  xor     ecx, ecx; lpModuleName
0x14002dc94  call    cs:__imp_GetModuleHandleW
0x14002dc9b  nop     dword ptr [rax+rax+00h]
0x14002dca0  mov     r9d, 100h; cchBufferMax
0x14002dca6  lea     r8, [rsp+12A0h+Buffer]; lpBuffer
0x14002dcab  mov     rcx, rax; hInstance
0x14002dcae  mov     edx, r15d; uID
0x14002dcb1  call    cs:__imp_LoadStringW
0x14002dcb8  nop     dword ptr [rax+rax+00h]
0x14002dcbd  test    eax, eax
0x14002dcbf  jnz     loc_14002DED2
0x14002dcc5  mov     r9d, 2B0h
0x14002dccb  jmp     short loc_14002DD0C
0x14002dccd  mov     r15d, 22Fh
0x14002dcd3  xor     ecx, ecx; lpModuleName
0x14002dcd5  call    cs:__imp_GetModuleHandleW
0x14002dcdc  nop     dword ptr [rax+rax+00h]
0x14002dce1  mov     r9d, 400h; cchBufferMax
0x14002dce7  lea     r8, [rbp+11A0h+String]; lpBuffer
0x14002dcee  mov     rcx, rax; hInstance
0x14002dcf1  mov     edx, 23Eh; uID
0x14002dcf6  call    cs:__imp_LoadStringW
0x14002dcfd  nop     dword ptr [rax+rax+00h]
0x14002dd02  test    eax, eax
0x14002dd04  jnz     short loc_14002DD1F
0x14002dd06  mov     r9d, 259h
0x14002dd0c  mov     [rsp+12A0h+var_1278], 0
0x14002dd14  mov     r8, rbx
0x14002dd17  mov     rdx, rdi
0x14002dd1a  jmp     loc_14002DB60
0x14002dd1f  xor     ecx, ecx; lpModuleName
0x14002dd21  call    cs:__imp_GetModuleHandleW
0x14002dd28  nop     dword ptr [rax+rax+00h]
0x14002dd2d  mov     r9d, 400h; cchBufferMax
0x14002dd33  lea     r8, [rbp+11A0h+var_1040]; lpBuffer
0x14002dd3a  mov     rcx, rax; hInstance
0x14002dd3d  mov     edx, 2A9h; uID
0x14002dd42  call    cs:__imp_LoadStringW
0x14002dd49  nop     dword ptr [rax+rax+00h]
0x14002dd4e  test    eax, eax
0x14002dd50  jns     short loc_14002DD5E
0x14002dd52  mov     [rsp+12A0h+var_1278], eax
0x14002dd56  mov     r9d, 262h
0x14002dd5c  jmp     short loc_14002DD14
0x14002dd5e  lea     r8, [rbp+11A0h+var_1040]; unsigned __int16 *
0x14002dd65  mov     edx, 400h; unsigned __int64
0x14002dd6a  lea     rcx, [rbp+11A0h+String]; unsigned __int16 *
0x14002dd71  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14002dd76  test    eax, eax
0x14002dd78  jns     short loc_14002DD8C
0x14002dd7a  mov     [rsp+12A0h+var_1278], eax
0x14002dd7e  mov     r9d, 267h
0x14002dd84  jmp     short loc_14002DD14
0x14002dd86  mov     r15d, 239h
0x14002dd8c  xor     ecx, ecx; lpModuleName
0x14002dd8e  call    cs:__imp_GetModuleHandleW
0x14002dd95  nop     dword ptr [rax+rax+00h]
0x14002dd9a  mov     r9d, 400h; cchBufferMax
0x14002dda0  lea     r8, [rbp+11A0h+var_1040]; lpBuffer
0x14002dda7  mov     rcx, rax; hInstance
0x14002ddaa  mov     edx, 240h; uID
0x14002ddaf  call    cs:__imp_LoadStringW
0x14002ddb6  nop     dword ptr [rax+rax+00h]
0x14002ddbb  test    eax, eax
0x14002ddbd  jns     short loc_14002DDCE
0x14002ddbf  mov     [rsp+12A0h+var_1278], eax
0x14002ddc3  mov     r9d, 272h
0x14002ddc9  jmp     loc_14002DD14
0x14002ddce  lea     r8, [rbp+11A0h+var_1040]; unsigned __int16 *
0x14002ddd5  mov     edx, 400h; unsigned __int64
0x14002ddda  lea     rcx, [rbp+11A0h+String]; unsigned __int16 *
0x14002dde1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14002dde6  test    eax, eax
0x14002dde8  jns     short loc_14002DDF9
0x14002ddea  mov     [rsp+12A0h+var_1278], eax
0x14002ddee  mov     r9d, 277h
0x14002ddf4  jmp     loc_14002DD14
0x14002ddf9  xor     edx, edx; Val
0x14002ddfb  lea     rcx, [rbp+11A0h+var_1040]; void *
0x14002de02  mov     r8d, 800h; Size
0x14002de08  call    memset_0
0x14002de0d  jmp     short loc_14002DE15
0x14002de0f  mov     r15d, 297h
0x14002de15  xor     ecx, ecx; lpModuleName
0x14002de17  call    cs:__imp_GetModuleHandleW
0x14002de1e  nop     dword ptr [rax+rax+00h]
0x14002de23  mov     r9d, 400h; cchBufferMax
0x14002de29  lea     r8, [rbp+11A0h+var_1040]; lpBuffer
0x14002de30  mov     rcx, rax; hInstance
0x14002de33  mov     edx, 23Fh; uID
0x14002de38  call    cs:__imp_LoadStringW
0x14002de3f  nop     dword ptr [rax+rax+00h]
0x14002de44  test    eax, eax
0x14002de46  jns     short loc_14002DE57
0x14002de48  mov     [rsp+12A0h+var_1278], eax
0x14002de4c  mov     r9d, 288h
0x14002de52  jmp     loc_14002DD14
0x14002de57  lea     r8, [rbp+11A0h+var_1040]; unsigned __int16 *
0x14002de5e  mov     edx, 400h; unsigned __int64
0x14002de63  lea     rcx, [rbp+11A0h+String]; unsigned __int16 *
0x14002de6a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14002de6f  test    eax, eax
0x14002de71  jns     loc_14002DC89
0x14002de77  mov     [rsp+12A0h+var_1278], eax
0x14002de7b  mov     r9d, 28Dh
0x14002de81  jmp     loc_14002DD14
0x14002de86  mov     r15d, 2C2h
0x14002de8c  xor     ecx, ecx; lpModuleName
0x14002de8e  call    cs:__imp_GetModuleHandleW
0x14002de95  nop     dword ptr [rax+rax+00h]
0x14002de9a  mov     r9d, 400h; cchBufferMax
0x14002dea0  lea     r8, [rbp+11A0h+String]; lpBuffer
0x14002dea7  mov     rcx, rax; hInstance
0x14002deaa  mov     edx, 242h; uID
0x14002deaf  call    cs:__imp_LoadStringW
0x14002deb6  nop     dword ptr [rax+rax+00h]
0x14002debb  test    eax, eax
0x14002debd  jns     loc_14002DC89
0x14002dec3  mov     [rsp+12A0h+var_1278], eax
0x14002dec7  mov     r9d, 29Ah
  ... truncated ...
```
