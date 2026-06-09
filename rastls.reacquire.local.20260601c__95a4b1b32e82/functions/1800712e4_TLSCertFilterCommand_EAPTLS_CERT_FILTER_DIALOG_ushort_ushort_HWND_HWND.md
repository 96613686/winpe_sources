# TLSCertFilterCommand(_EAPTLS_CERT_FILTER_DIALOG *,ushort,ushort,HWND__ *,HWND__ *)

- ea: `0x1800712e4`
- end: `0x1800716f2`
- name: `?TLSCertFilterCommand@@YAHPEAU_EAPTLS_CERT_FILTER_DIALOG@@GGPEAUHWND__@@1@Z`
- size: `1038`
- prototype: `__int64 __fastcall(struct _EAPTLS_CERT_FILTER_DIALOG *, unsigned __int16, unsigned __int16, HWND, HWND)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18006a578`
- `0x1800719d0`

## callees

- `0x180005010`
- `0x180007d00`
- `0x1800698e0`
- `0x18006a078`
- `0x18006a578`
- `0x18006a7a4`
- `0x18006d3b0`
- `0x18006e94c`
- `0x1800712e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007161a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007161a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetFocus` at `0x1800715b8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetFocus` at `0x1800715b8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180071588`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180071588`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x1800715a9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x1800715a9`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x1800715f4`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x1800715f4`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x180071457`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x180071457`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x180071358`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x180071385`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x1800713f8`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x180071473`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x180071690`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x180071358`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x180071385`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x1800713f8`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x180071473`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x180071690`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_Destroy` at `0x180071445`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_Destroy` at `0x180071445`

## pseudocode

```c
__int64 __fastcall TLSCertFilterCommand(
        struct _EAPTLS_CERT_FILTER_DIALOG *a1,
        __int16 a2,
        unsigned __int16 a3,
        HWND a4)
{
  INT_PTR v4; // rbp
  UINT v7; // eax
  __int16 v8; // r8
  __int16 v9; // cx
  __int16 v10; // dx
  UINT v11; // eax
  __int16 v12; // r8
  __int16 v13; // cx
  __int16 v14; // r8
  unsigned __int16 v15; // r9
  unsigned __int16 v16; // r9
  UINT v17; // eax
  __int16 v18; // dx
  __int16 v19; // cx
  __int16 v20; // dx
  UINT v22; // eax
  __int16 v23; // dx
  __int16 v24; // dx
  __int64 v25; // rax
  HWND v26; // rsi
  __int64 v27; // rcx
  HINSTANCE v28; // rcx
  INT_PTR v29; // rax
  DWORD LastError; // eax
  __int16 v31; // cx
  struct _EAPTLS_EKU_NODE *v33; // [rsp+50h] [rbp+8h] BYREF
  int v34; // [rsp+58h] [rbp+10h] BYREF

  LOWORD(v34) = a2;
  v4 = a3;
  if ( a1 )
  {
    if ( a3 <= 0x413u )
    {
      switch ( a3 )
      {
        case 0x413u:
          v22 = IsDlgButtonChecked(a4, 1043);
          v23 = *((_WORD *)a1 + 82);
          if ( v22 == 1 )
          {
            v24 = v23 | 2;
            *((_WORD *)a1 + 82) = v24;
            if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 192, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
              v24 = *((_WORD *)a1 + 82);
            }
          }
          else
          {
            v24 = v23 & 0xFFFD;
            *((_WORD *)a1 + 82) = v24;
          }
          if ( (v24 & 2) != 0 )
            goto LABEL_16;
LABEL_50:
          CheckIfLastUncheck(a4, a1);
LABEL_16:
          EnableFilterDialogControls(a1);
          return 1;
        case 1u:
          CertTreeGetSelectedHashes(a1);
          break;
        case 2u:
          break;
        case 0x40Fu:
          v17 = IsDlgButtonChecked(a4, 1039);
          v18 = *((_WORD *)a1 + 82);
          v19 = v18 & 0xFFFE;
          v20 = v18 | 1;
          if ( v17 != 1 )
            v20 = v19;
          *((_WORD *)a1 + 82) = v20;
          goto LABEL_16;
        case 0x411u:
          v11 = IsDlgButtonChecked(a4, 1041);
          v12 = *((_WORD *)a1 + 82);
          v13 = v12 & 0xFFEF;
          v14 = v12 | 0x10;
          if ( v11 != 1 )
            v14 = v13;
          *((_WORD *)a1 + 82) = v14;
          CheckDlgButtonAndSendComm(a4, 0x413u, a1, 0xFFEFu);
          CheckDlgButtonAndSendComm(a4, 0x414u, a1, v15);
          CheckDlgButtonAndSendComm(a4, 0x412u, a1, v16);
          goto LABEL_16;
        case 0x412u:
          v7 = IsDlgButtonChecked(a4, 1042);
          v8 = -9;
          v9 = *((_WORD *)a1 + 82);
          v10 = v9 | 8;
          goto LABEL_47;
        default:
          return 0;
      }
      ImageList_Destroy(*((HIMAGELIST *)a1 + 6));
      EndDialog(a4, v4);
      return 1;
    }
    switch ( a3 )
    {
      case 0x414u:
        v7 = IsDlgButtonChecked(a4, 1044);
        v8 = -5;
        v9 = *((_WORD *)a1 + 82);
        v10 = v9 | 4;
LABEL_47:
        v31 = v8 & v9;
        if ( v7 != 1 )
          v10 = v31;
        *((_WORD *)a1 + 82) = v10;
        if ( v7 == 1 )
          goto LABEL_16;
        goto LABEL_50;
      case 0x417u:
        goto LABEL_40;
      case 0x418u:
LABEL_31:
        v25 = 216;
        v33 = 0;
        v34 = 0;
        if ( a3 != 1048 )
          v25 = 224;
        v26 = *(HWND *)((char *)a1 + v25);
        GetSelectedEKUListItem(v26, &v33, &v34);
        if ( v33 )
        {
          if ( (_WORD)v4 == 1048 )
            *((_DWORD *)v33 + 9) = 0;
          else
            *((_DWORD *)v33 + 10) = 0;
          SendMessageW(v26, 0x1008u, v34, 0);
          v27 = 240;
          if ( (_WORD)v4 != 1048 )
            v27 = 256;
          EnableWindow(*(HWND *)((char *)a1 + v27), 0);
          SetFocus(v26);
        }
        return 1;
      case 0x419u:
LABEL_40:
        v28 = g_hInstance;
        *((_DWORD *)a1 + 14) = a3 == 1047;
        v29 = DialogBoxParamW(v28, (LPCWSTR)0x74, a4, EKUListDialogProc, (LPARAM)a1);
        if ( v29 == -1 )
        {
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            LastError = GetLastError();
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              193,
              &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids,
              LastError);
          }
        }
        else if ( v29 == 1 && *((_QWORD *)a1 + 15) )
        {
          AddItemToListBox(
            *(HWND *)((char *)a1 + (-(__int64)(*((_DWORD *)a1 + 14) != 0) & 0xFFFFFFFFFFFFFFF8uLL) + 224),
            *((struct _EAPTLS_EKU_NODE **)a1 + 15));
          *((_QWORD *)a1 + 15) = 0;
        }
        return 1;
      case 0x41Au:
        goto LABEL_31;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800712e4  mov     [rsp+arg_10], rbx
0x1800712e9  mov     [rsp+arg_18], rbp
0x1800712ee  mov     word ptr [rsp+arg_8], dx
0x1800712f3  push    rsi
0x1800712f4  push    rdi
0x1800712f5  push    r15
0x1800712f7  sub     rsp, 30h
0x1800712fb  movzx   ebp, r8w
0x1800712ff  mov     rsi, r9
0x180071302  mov     rbx, rcx
0x180071305  test    rcx, rcx
0x180071308  jz      loc_1800716DC
0x18007130e  mov     r15d, 413h
0x180071314  mov     edx, ebp
0x180071316  cmp     ebp, r15d
0x180071319  ja      loc_1800714EA
0x18007131f  jz      loc_18007146D
0x180071325  sub     edx, 1
0x180071328  jz      loc_18007143C
0x18007132e  sub     edx, 1
0x180071331  jz      loc_180071441
0x180071337  sub     edx, 40Dh
0x18007133d  jz      loc_1800713F0
0x180071343  sub     edx, 2
0x180071346  jz      short loc_18007137D
0x180071348  cmp     edx, 1
0x18007134b  jnz     loc_1800716DC
0x180071351  lea     edx, [r15-1]; nIDButton
0x180071355  mov     rcx, r9; hDlg
0x180071358  call    cs:__imp_IsDlgButtonChecked
0x18007135f  nop     dword ptr [rax+rax+00h]
0x180071364  movzx   edx, word ptr [rbx+0A4h]
0x18007136b  mov     r8d, 0FFF7h
0x180071371  movzx   ecx, dx
0x180071374  or      dx, 8
0x180071378  jmp     loc_1800716B0
0x18007137d  mov     edx, 411h; nIDButton
0x180071382  mov     rcx, rsi; hDlg
0x180071385  call    cs:__imp_IsDlgButtonChecked
0x18007138c  nop     dword ptr [rax+rax+00h]
0x180071391  movzx   r8d, word ptr [rbx+0A4h]
0x180071399  mov     r9d, 0FFEFh; unsigned __int16
0x18007139f  movzx   ecx, r8w
0x1800713a3  mov     edi, 1
0x1800713a8  and     cx, r9w
0x1800713ac  or      r8w, 10h
0x1800713b1  cmp     eax, edi
0x1800713b3  mov     edx, r15d; unsigned __int16
0x1800713b6  cmovnz  r8w, cx
0x1800713bb  mov     rcx, rsi; HWND
0x1800713be  mov     [rbx+0A4h], r8w
0x1800713c6  mov     r8, rbx; struct _EAPTLS_CERT_FILTER_DIALOG *
0x1800713c9  call    ?CheckDlgButtonAndSendComm@@YAXPEAUHWND__@@GPEAU_EAPTLS_CERT_FILTER_DIALOG@@G@Z; CheckDlgButtonAndSendComm(HWND__ *,ushort,_EAPTLS_CERT_FILTER_DIALOG *,ushort)
0x1800713ce  mov     edx, 414h; unsigned __int16
0x1800713d3  mov     r8, rbx; struct _EAPTLS_CERT_FILTER_DIALOG *
0x1800713d6  mov     rcx, rsi; HWND
0x1800713d9  call    ?CheckDlgButtonAndSendComm@@YAXPEAUHWND__@@GPEAU_EAPTLS_CERT_FILTER_DIALOG@@G@Z; CheckDlgButtonAndSendComm(HWND__ *,ushort,_EAPTLS_CERT_FILTER_DIALOG *,ushort)
0x1800713de  mov     edx, 412h; unsigned __int16
0x1800713e3  mov     r8, rbx; struct _EAPTLS_CERT_FILTER_DIALOG *
0x1800713e6  mov     rcx, rsi; HWND
0x1800713e9  call    ?CheckDlgButtonAndSendComm@@YAXPEAUHWND__@@GPEAU_EAPTLS_CERT_FILTER_DIALOG@@G@Z; CheckDlgButtonAndSendComm(HWND__ *,ushort,_EAPTLS_CERT_FILTER_DIALOG *,ushort)
0x1800713ee  jmp     short loc_18007142D
0x1800713f0  mov     edx, 40Fh; nIDButton
0x1800713f5  mov     rcx, rsi; hDlg
0x1800713f8  call    cs:__imp_IsDlgButtonChecked
0x1800713ff  nop     dword ptr [rax+rax+00h]
0x180071404  movzx   edx, word ptr [rbx+0A4h]
0x18007140b  mov     edi, 1
0x180071410  movzx   ecx, dx
0x180071413  mov     r8d, 0FFFEh
0x180071419  and     cx, r8w
0x18007141d  or      dx, di
0x180071420  cmp     eax, edi
0x180071422  cmovnz  dx, cx
0x180071426  mov     [rbx+0A4h], dx
0x18007142d  mov     rcx, rbx; struct _EAPTLS_CERT_FILTER_DIALOG *
0x180071430  call    ?EnableFilterDialogControls@@YAXPEAU_EAPTLS_CERT_FILTER_DIALOG@@@Z; EnableFilterDialogControls(_EAPTLS_CERT_FILTER_DIALOG *)
0x180071435  mov     eax, edi
0x180071437  jmp     loc_1800716DE
0x18007143c  call    ?CertTreeGetSelectedHashes@@YAKPEAU_EAPTLS_CERT_FILTER_DIALOG@@@Z; CertTreeGetSelectedHashes(_EAPTLS_CERT_FILTER_DIALOG *)
0x180071441  mov     rcx, [rbx+30h]; himl
0x180071445  call    cs:__imp_ImageList_Destroy
0x18007144c  nop     dword ptr [rax+rax+00h]
0x180071451  mov     rdx, rbp; nResult
0x180071454  mov     rcx, rsi; hDlg
0x180071457  call    cs:__imp_EndDialog
0x18007145e  nop     dword ptr [rax+rax+00h]
0x180071463  mov     eax, 1
0x180071468  jmp     loc_1800716DE
0x18007146d  mov     edx, r15d; nIDButton
0x180071470  mov     rcx, rsi; hDlg
0x180071473  call    cs:__imp_IsDlgButtonChecked
0x18007147a  nop     dword ptr [rax+rax+00h]
0x18007147f  movzx   edx, word ptr [rbx+0A4h]
0x180071486  mov     ebp, 2
0x18007148b  lea     edi, [rbp-1]
0x18007148e  cmp     eax, edi
0x180071490  jnz     short loc_1800714CD
0x180071492  or      dx, bp
0x180071495  mov     [rbx+0A4h], dx
0x18007149c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800714a3  lea     rax, WPP_GLOBAL_Control
0x1800714aa  cmp     rcx, rax
0x1800714ad  jz      short loc_1800714DC
0x1800714af  mov     rcx, [rcx+10h]
0x1800714b3  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x1800714ba  mov     edx, 0C0h
0x1800714bf  call    WPP_SF_
0x1800714c4  movzx   edx, word ptr [rbx+0A4h]
0x1800714cb  jmp     short loc_1800714DC
0x1800714cd  mov     eax, 0FFFDh
0x1800714d2  and     dx, ax
0x1800714d5  mov     [rbx+0A4h], dx
0x1800714dc  test    bpl, dl
0x1800714df  jnz     loc_18007142D
0x1800714e5  jmp     loc_1800716CC
0x1800714ea  sub     edx, 414h
0x1800714f0  jz      loc_180071688
0x1800714f6  mov     edi, 1
0x1800714fb  sub     edx, 3
0x1800714fe  jz      loc_1800715C9
0x180071504  sub     edx, edi
0x180071506  jz      short loc_180071518
0x180071508  sub     edx, edi
0x18007150a  jz      loc_1800715C9
0x180071510  cmp     edx, edi
0x180071512  jnz     loc_1800716DC
0x180071518  mov     eax, 0D8h
0x18007151d  mov     [rsp+48h+arg_0], 0
0x180071526  mov     [rsp+48h+arg_8], 0
0x18007152e  lea     r8, [rsp+48h+arg_8]; int *
0x180071533  mov     r15d, 418h
0x180071539  cmp     bp, r15w
0x18007153d  lea     edx, [rax+8]
0x180071540  cmovnz  eax, edx
0x180071543  lea     rdx, [rsp+48h+arg_0]; struct _EAPTLS_EKU_NODE **
0x180071548  mov     rsi, [rax+rcx]
0x18007154c  mov     rcx, rsi; hWnd
0x18007154f  call    ?GetSelectedEKUListItem@@YAXPEAUHWND__@@PEAPEAU_EAPTLS_EKU_NODE@@PEAH@Z; GetSelectedEKUListItem(HWND__ *,_EAPTLS_EKU_NODE * *,int *)
0x180071554  mov     rax, [rsp+48h+arg_0]
0x180071559  test    rax, rax
0x18007155c  jz      loc_180071435
0x180071562  cmp     bp, r15w
0x180071566  jnz     short loc_180071571
0x180071568  mov     dword ptr [rax+24h], 0
0x18007156f  jmp     short loc_180071578
0x180071571  mov     dword ptr [rax+28h], 0
0x180071578  movsxd  r8, [rsp+48h+arg_8]; wParam
0x18007157d  xor     r9d, r9d; lParam
0x180071580  mov     edx, 1008h; Msg
0x180071585  mov     rcx, rsi; hWnd
0x180071588  call    cs:__imp_SendMessageW
0x18007158f  nop     dword ptr [rax+rax+00h]
0x180071594  mov     ecx, 0F0h
0x180071599  cmp     bp, r15w
0x18007159d  lea     eax, [rcx+10h]
0x1800715a0  cmovnz  ecx, eax
0x1800715a3  xor     edx, edx; bEnable
0x1800715a5  mov     rcx, [rcx+rbx]; hWnd
0x1800715a9  call    cs:__imp_EnableWindow
0x1800715b0  nop     dword ptr [rax+rax+00h]
0x1800715b5  mov     rcx, rsi; hWnd
0x1800715b8  call    cs:__imp_SetFocus
0x1800715bf  nop     dword ptr [rax+rax+00h]
0x1800715c4  jmp     loc_180071435
0x1800715c9  xor     eax, eax
0x1800715cb  mov     [rsp+48h+dwInitParam], rbx; dwInitParam
0x1800715d0  mov     ecx, 417h
0x1800715d5  lea     r9, ?EKUListDialogProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x1800715dc  cmp     bp, cx
0x1800715df  mov     r8, rsi; hWndParent
0x1800715e2  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800715e9  mov     edx, 74h ; 't'; lpTemplateName
0x1800715ee  setz    al
0x1800715f1  mov     [rbx+38h], eax
0x1800715f4  call    cs:__imp_DialogBoxParamW
0x1800715fb  nop     dword ptr [rax+rax+00h]
0x180071600  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180071604  jnz     short loc_18007164A
0x180071606  lea     rax, WPP_GLOBAL_Control
0x18007160d  cmp     cs:WPP_GLOBAL_Control, rax
0x180071614  jz      loc_180071435
0x18007161a  call    cs:__imp_GetLastError
0x180071621  nop     dword ptr [rax+rax+00h]
0x180071626  mov     rcx, cs:WPP_GLOBAL_Control
0x18007162d  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x180071634  mov     edx, 0C1h
0x180071639  mov     r9d, eax
0x18007163c  mov     rcx, [rcx+10h]
0x180071640  call    WPP_SF_d
0x180071645  jmp     loc_180071435
0x18007164a  cmp     rax, rdi
0x18007164d  jnz     loc_180071435
0x180071653  cmp     qword ptr [rbx+78h], 0
0x180071658  jz      loc_180071435
0x18007165e  mov     eax, [rbx+38h]
0x180071661  mov     rdx, [rbx+78h]; struct _EAPTLS_EKU_NODE *
0x180071665  neg     eax
0x180071667  sbb     rcx, rcx
0x18007166a  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18007166e  mov     rcx, [rcx+rbx+0E0h]; hWnd
0x180071676  call    ?AddItemToListBox@@YAXPEAUHWND__@@PEAU_EAPTLS_EKU_NODE@@@Z; AddItemToListBox(HWND__ *,_EAPTLS_EKU_NODE *)
0x18007167b  mov     qword ptr [rbx+78h], 0
0x180071683  jmp     loc_180071435
0x180071688  mov     edx, 414h; nIDButton
0x18007168d  mov     rcx, rsi; hDlg
0x180071690  call    cs:__imp_IsDlgButtonChecked
0x180071697  nop     dword ptr [rax+rax+00h]
0x18007169c  movzx   edx, word ptr [rbx+0A4h]
0x1800716a3  mov     r8d, 0FFFBh
0x1800716a9  movzx   ecx, dx
0x1800716ac  or      dx, 4
0x1800716b0  and     cx, r8w
0x1800716b4  mov     edi, 1
0x1800716b9  cmp     eax, edi
0x1800716bb  cmovnz  dx, cx
0x1800716bf  mov     [rbx+0A4h], dx
0x1800716c6  jz      loc_18007142D
0x1800716cc  mov     rdx, rbx; struct _EAPTLS_CERT_FILTER_DIALOG *
0x1800716cf  mov     rcx, rsi; HWND
0x1800716d2  call    ?CheckIfLastUncheck@@YAXPEAUHWND__@@PEAU_EAPTLS_CERT_FILTER_DIALOG@@@Z; CheckIfLastUncheck(HWND__ *,_EAPTLS_CERT_FILTER_DIALOG *)
0x1800716d7  jmp     loc_18007142D
0x1800716dc  xor     eax, eax
0x1800716de  mov     rbx, [rsp+48h+arg_10]
0x1800716e3  mov     rbp, [rsp+48h+arg_18]
0x1800716e8  add     rsp, 30h
0x1800716ec  pop     r15
0x1800716ee  pop     rdi
0x1800716ef  pop     rsi
0x1800716f0  retn
```
