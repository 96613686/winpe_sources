# TLSCertFilterCommand(_EAPTLS_CERT_FILTER_DIALOG *,ushort,ushort,HWND__ *,HWND__ *)

- ea: `0x18006caf4`
- end: `0x18006ceb9`
- name: `?TLSCertFilterCommand@@YAHPEAU_EAPTLS_CERT_FILTER_DIALOG@@GGPEAUHWND__@@1@Z`
- size: `965`
- prototype: `__int64 __fastcall(struct _EAPTLS_CERT_FILTER_DIALOG *, unsigned __int16, unsigned __int16, HWND, HWND)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800667bc`
- `0x18006d150`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180065c48`
- `0x180066320`
- `0x1800667bc`
- `0x1800669bc`
- `0x1800690f8`
- `0x18006a4a4`
- `0x18006caf4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cdee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006cdee`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetFocus` at `0x18006cd98`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetFocus` at `0x18006cd98`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006cd74`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006cd74`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18006cd8f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x18006cd8f`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x18006cdce`
- `ext-ms-win-ntuser-dialogbox-l1-1-1!DialogBoxParamW` at `0x18006cdce`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x18006cc4f`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x18006cc4f`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006cb68`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006cb8f`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006cbfc`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006cc65`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006ce5e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006cb68`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006cb8f`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006cbfc`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006cc65`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!IsDlgButtonChecked` at `0x18006ce5e`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_Destroy` at `0x18006cc43`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_Destroy` at `0x18006cc43`

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
0x18006caf4  mov     [rsp+arg_10], rbx
0x18006caf9  mov     [rsp+arg_18], rbp
0x18006cafe  mov     word ptr [rsp+arg_8], dx
0x18006cb03  push    rsi
0x18006cb04  push    rdi
0x18006cb05  push    r15
0x18006cb07  sub     rsp, 30h
0x18006cb0b  movzx   ebp, r8w
0x18006cb0f  mov     rsi, r9
0x18006cb12  mov     rbx, rcx
0x18006cb15  test    rcx, rcx
0x18006cb18  jz      loc_18006CEA4
0x18006cb1e  mov     r15d, 413h
0x18006cb24  mov     edx, ebp
0x18006cb26  cmp     ebp, r15d
0x18006cb29  ja      loc_18006CCD6
0x18006cb2f  jz      loc_18006CC5F
0x18006cb35  sub     edx, 1
0x18006cb38  jz      loc_18006CC3A
0x18006cb3e  sub     edx, 1
0x18006cb41  jz      loc_18006CC3F
0x18006cb47  sub     edx, 40Dh
0x18006cb4d  jz      loc_18006CBF4
0x18006cb53  sub     edx, 2
0x18006cb56  jz      short loc_18006CB87
0x18006cb58  cmp     edx, 1
0x18006cb5b  jnz     loc_18006CEA4
0x18006cb61  lea     edx, [r15-1]; nIDButton
0x18006cb65  mov     rcx, r9; hDlg
0x18006cb68  call    cs:__imp_IsDlgButtonChecked
0x18006cb6e  movzx   edx, word ptr [rbx+0A4h]
0x18006cb75  mov     r8d, 0FFF7h
0x18006cb7b  movzx   ecx, dx
0x18006cb7e  or      dx, 8
0x18006cb82  jmp     loc_18006CE78
0x18006cb87  mov     edx, 411h; nIDButton
0x18006cb8c  mov     rcx, rsi; hDlg
0x18006cb8f  call    cs:__imp_IsDlgButtonChecked
0x18006cb95  movzx   r8d, word ptr [rbx+0A4h]
0x18006cb9d  mov     r9d, 0FFEFh; unsigned __int16
0x18006cba3  movzx   ecx, r8w
0x18006cba7  mov     edi, 1
0x18006cbac  and     cx, r9w
0x18006cbb0  or      r8w, 10h
0x18006cbb5  cmp     eax, edi
0x18006cbb7  mov     edx, r15d; unsigned __int16
0x18006cbba  cmovnz  r8w, cx
0x18006cbbf  mov     rcx, rsi; HWND
0x18006cbc2  mov     [rbx+0A4h], r8w
0x18006cbca  mov     r8, rbx; struct _EAPTLS_CERT_FILTER_DIALOG *
0x18006cbcd  call    ?CheckDlgButtonAndSendComm@@YAXPEAUHWND__@@GPEAU_EAPTLS_CERT_FILTER_DIALOG@@G@Z; CheckDlgButtonAndSendComm(HWND__ *,ushort,_EAPTLS_CERT_FILTER_DIALOG *,ushort)
0x18006cbd2  mov     edx, 414h; unsigned __int16
0x18006cbd7  mov     r8, rbx; struct _EAPTLS_CERT_FILTER_DIALOG *
0x18006cbda  mov     rcx, rsi; HWND
0x18006cbdd  call    ?CheckDlgButtonAndSendComm@@YAXPEAUHWND__@@GPEAU_EAPTLS_CERT_FILTER_DIALOG@@G@Z; CheckDlgButtonAndSendComm(HWND__ *,ushort,_EAPTLS_CERT_FILTER_DIALOG *,ushort)
0x18006cbe2  mov     edx, 412h; unsigned __int16
0x18006cbe7  mov     r8, rbx; struct _EAPTLS_CERT_FILTER_DIALOG *
0x18006cbea  mov     rcx, rsi; HWND
0x18006cbed  call    ?CheckDlgButtonAndSendComm@@YAXPEAUHWND__@@GPEAU_EAPTLS_CERT_FILTER_DIALOG@@G@Z; CheckDlgButtonAndSendComm(HWND__ *,ushort,_EAPTLS_CERT_FILTER_DIALOG *,ushort)
0x18006cbf2  jmp     short loc_18006CC2B
0x18006cbf4  mov     edx, 40Fh; nIDButton
0x18006cbf9  mov     rcx, rsi; hDlg
0x18006cbfc  call    cs:__imp_IsDlgButtonChecked
0x18006cc02  movzx   edx, word ptr [rbx+0A4h]
0x18006cc09  mov     edi, 1
0x18006cc0e  movzx   ecx, dx
0x18006cc11  mov     r8d, 0FFFEh
0x18006cc17  and     cx, r8w
0x18006cc1b  or      dx, di
0x18006cc1e  cmp     eax, edi
0x18006cc20  cmovnz  dx, cx
0x18006cc24  mov     [rbx+0A4h], dx
0x18006cc2b  mov     rcx, rbx; struct _EAPTLS_CERT_FILTER_DIALOG *
0x18006cc2e  call    ?EnableFilterDialogControls@@YAXPEAU_EAPTLS_CERT_FILTER_DIALOG@@@Z; EnableFilterDialogControls(_EAPTLS_CERT_FILTER_DIALOG *)
0x18006cc33  mov     eax, edi
0x18006cc35  jmp     loc_18006CEA6
0x18006cc3a  call    ?CertTreeGetSelectedHashes@@YAKPEAU_EAPTLS_CERT_FILTER_DIALOG@@@Z; CertTreeGetSelectedHashes(_EAPTLS_CERT_FILTER_DIALOG *)
0x18006cc3f  mov     rcx, [rbx+30h]; himl
0x18006cc43  call    cs:__imp_ImageList_Destroy
0x18006cc49  mov     rdx, rbp; nResult
0x18006cc4c  mov     rcx, rsi; hDlg
0x18006cc4f  call    cs:__imp_EndDialog
0x18006cc55  mov     eax, 1
0x18006cc5a  jmp     loc_18006CEA6
0x18006cc5f  mov     edx, r15d; nIDButton
0x18006cc62  mov     rcx, rsi; hDlg
0x18006cc65  call    cs:__imp_IsDlgButtonChecked
0x18006cc6b  movzx   edx, word ptr [rbx+0A4h]
0x18006cc72  mov     ebp, 2
0x18006cc77  lea     edi, [rbp-1]
0x18006cc7a  cmp     eax, edi
0x18006cc7c  jnz     short loc_18006CCB9
0x18006cc7e  or      dx, bp
0x18006cc81  mov     [rbx+0A4h], dx
0x18006cc88  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cc8f  lea     rax, WPP_GLOBAL_Control
0x18006cc96  cmp     rcx, rax
0x18006cc99  jz      short loc_18006CCC8
0x18006cc9b  mov     rcx, [rcx+10h]
0x18006cc9f  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006cca6  mov     edx, 0C0h
0x18006ccab  call    WPP_SF_
0x18006ccb0  movzx   edx, word ptr [rbx+0A4h]
0x18006ccb7  jmp     short loc_18006CCC8
0x18006ccb9  mov     eax, 0FFFDh
0x18006ccbe  and     dx, ax
0x18006ccc1  mov     [rbx+0A4h], dx
0x18006ccc8  test    bpl, dl
0x18006cccb  jnz     loc_18006CC2B
0x18006ccd1  jmp     loc_18006CE94
0x18006ccd6  sub     edx, 414h
0x18006ccdc  jz      loc_18006CE56
0x18006cce2  mov     edi, 1
0x18006cce7  sub     edx, 3
0x18006ccea  jz      loc_18006CDA3
0x18006ccf0  sub     edx, edi
0x18006ccf2  jz      short loc_18006CD04
0x18006ccf4  sub     edx, edi
0x18006ccf6  jz      loc_18006CDA3
0x18006ccfc  cmp     edx, edi
0x18006ccfe  jnz     loc_18006CEA4
0x18006cd04  mov     eax, 0D8h
0x18006cd09  mov     [rsp+48h+arg_0], 0
0x18006cd12  mov     [rsp+48h+arg_8], 0
0x18006cd1a  lea     r8, [rsp+48h+arg_8]; int *
0x18006cd1f  mov     r15d, 418h
0x18006cd25  cmp     bp, r15w
0x18006cd29  lea     edx, [rax+8]
0x18006cd2c  cmovnz  eax, edx
0x18006cd2f  lea     rdx, [rsp+48h+arg_0]; struct _EAPTLS_EKU_NODE **
0x18006cd34  mov     rsi, [rax+rcx]
0x18006cd38  mov     rcx, rsi; hWnd
0x18006cd3b  call    ?GetSelectedEKUListItem@@YAXPEAUHWND__@@PEAPEAU_EAPTLS_EKU_NODE@@PEAH@Z; GetSelectedEKUListItem(HWND__ *,_EAPTLS_EKU_NODE * *,int *)
0x18006cd40  mov     rax, [rsp+48h+arg_0]
0x18006cd45  test    rax, rax
0x18006cd48  jz      loc_18006CC33
0x18006cd4e  cmp     bp, r15w
0x18006cd52  jnz     short loc_18006CD5D
0x18006cd54  mov     dword ptr [rax+24h], 0
0x18006cd5b  jmp     short loc_18006CD64
0x18006cd5d  mov     dword ptr [rax+28h], 0
0x18006cd64  movsxd  r8, [rsp+48h+arg_8]; wParam
0x18006cd69  xor     r9d, r9d; lParam
0x18006cd6c  mov     edx, 1008h; Msg
0x18006cd71  mov     rcx, rsi; hWnd
0x18006cd74  call    cs:__imp_SendMessageW
0x18006cd7a  mov     ecx, 0F0h
0x18006cd7f  cmp     bp, r15w
0x18006cd83  lea     eax, [rcx+10h]
0x18006cd86  cmovnz  ecx, eax
0x18006cd89  xor     edx, edx; bEnable
0x18006cd8b  mov     rcx, [rcx+rbx]; hWnd
0x18006cd8f  call    cs:__imp_EnableWindow
0x18006cd95  mov     rcx, rsi; hWnd
0x18006cd98  call    cs:__imp_SetFocus
0x18006cd9e  jmp     loc_18006CC33
0x18006cda3  xor     eax, eax
0x18006cda5  mov     [rsp+48h+dwInitParam], rbx; dwInitParam
0x18006cdaa  mov     ecx, 417h
0x18006cdaf  lea     r9, ?EKUListDialogProc@@YA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x18006cdb6  cmp     bp, cx
0x18006cdb9  mov     r8, rsi; hWndParent
0x18006cdbc  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18006cdc3  mov     edx, 74h ; 't'; lpTemplateName
0x18006cdc8  setz    al
0x18006cdcb  mov     [rbx+38h], eax
0x18006cdce  call    cs:__imp_DialogBoxParamW
0x18006cdd4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006cdd8  jnz     short loc_18006CE18
0x18006cdda  lea     rax, WPP_GLOBAL_Control
0x18006cde1  cmp     cs:WPP_GLOBAL_Control, rax
0x18006cde8  jz      loc_18006CC33
0x18006cdee  call    cs:__imp_GetLastError
0x18006cdf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18006cdfb  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006ce02  mov     edx, 0C1h
0x18006ce07  mov     r9d, eax
0x18006ce0a  mov     rcx, [rcx+10h]
0x18006ce0e  call    WPP_SF_d
0x18006ce13  jmp     loc_18006CC33
0x18006ce18  cmp     rax, rdi
0x18006ce1b  jnz     loc_18006CC33
0x18006ce21  cmp     qword ptr [rbx+78h], 0
0x18006ce26  jz      loc_18006CC33
0x18006ce2c  mov     eax, [rbx+38h]
0x18006ce2f  mov     rdx, [rbx+78h]; struct _EAPTLS_EKU_NODE *
0x18006ce33  neg     eax
0x18006ce35  sbb     rcx, rcx
0x18006ce38  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18006ce3c  mov     rcx, [rcx+rbx+0E0h]; hWnd
0x18006ce44  call    ?AddItemToListBox@@YAXPEAUHWND__@@PEAU_EAPTLS_EKU_NODE@@@Z; AddItemToListBox(HWND__ *,_EAPTLS_EKU_NODE *)
0x18006ce49  mov     qword ptr [rbx+78h], 0
0x18006ce51  jmp     loc_18006CC33
0x18006ce56  mov     edx, 414h; nIDButton
0x18006ce5b  mov     rcx, rsi; hDlg
0x18006ce5e  call    cs:__imp_IsDlgButtonChecked
0x18006ce64  movzx   edx, word ptr [rbx+0A4h]
0x18006ce6b  mov     r8d, 0FFFBh
0x18006ce71  movzx   ecx, dx
0x18006ce74  or      dx, 4
0x18006ce78  and     cx, r8w
0x18006ce7c  mov     edi, 1
0x18006ce81  cmp     eax, edi
0x18006ce83  cmovnz  dx, cx
0x18006ce87  mov     [rbx+0A4h], dx
0x18006ce8e  jz      loc_18006CC2B
0x18006ce94  mov     rdx, rbx; struct _EAPTLS_CERT_FILTER_DIALOG *
0x18006ce97  mov     rcx, rsi; HWND
0x18006ce9a  call    ?CheckIfLastUncheck@@YAXPEAUHWND__@@PEAU_EAPTLS_CERT_FILTER_DIALOG@@@Z; CheckIfLastUncheck(HWND__ *,_EAPTLS_CERT_FILTER_DIALOG *)
0x18006ce9f  jmp     loc_18006CC2B
0x18006cea4  xor     eax, eax
0x18006cea6  mov     rbx, [rsp+48h+arg_10]
0x18006ceab  mov     rbp, [rsp+48h+arg_18]
0x18006ceb0  add     rsp, 30h
0x18006ceb4  pop     r15
0x18006ceb6  pop     rdi
0x18006ceb7  pop     rsi
0x18006ceb8  retn
```
