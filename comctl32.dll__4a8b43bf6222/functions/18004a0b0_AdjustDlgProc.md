# AdjustDlgProc

- ea: `0x18004a0b0`
- end: `0x18004a5ed`
- name: `AdjustDlgProc`
- size: `1341`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update`

## callees

- `0x1800115f0`
- `0x180019614`
- `0x180031540`
- `0x180035fe0`
- `0x18004a0b0`
- `0x18004a78c`
- `0x18004a824`
- `0x18004aa30`
- `0x18004b0c4`
- `0x18004b9a8`
- `0x18004bd1c`
- `0x18004c388`

## import_xrefs

- `USER32!GetDC` at `0x18004a56c`
- `USER32!GetDC` at `0x18004a56c`
- `USER32!ReleaseDC` at `0x18004a5b2`
- `USER32!ReleaseDC` at `0x18004a5b2`
- `USER32!SendMessageW` at `0x18004a26f`
- `USER32!SendMessageW` at `0x18004a288`
- `USER32!SendMessageW` at `0x18004a2ca`
- `USER32!SendMessageW` at `0x18004a40d`
- `USER32!SendMessageW` at `0x18004a422`
- `USER32!SendMessageW` at `0x18004a26f`
- `USER32!SendMessageW` at `0x18004a288`
- `USER32!SendMessageW` at `0x18004a2ca`
- `USER32!SendMessageW` at `0x18004a40d`
- `USER32!SendMessageW` at `0x18004a422`
- `USER32!GetDlgItem` at `0x18004a508`
- `USER32!GetDlgItem` at `0x18004a51d`
- `USER32!GetDlgItem` at `0x18004a532`
- `USER32!GetDlgItem` at `0x18004a560`
- `USER32!GetDlgItem` at `0x18004a508`
- `USER32!GetDlgItem` at `0x18004a51d`
- `USER32!GetDlgItem` at `0x18004a532`
- `USER32!GetDlgItem` at `0x18004a560`
- `USER32!ShowWindow` at `0x18004a4ed`
- `USER32!ShowWindow` at `0x18004a4ed`
- `USER32!SetWindowLongPtrW` at `0x18004a4c5`
- `USER32!SetWindowLongPtrW` at `0x18004a4c5`
- `USER32!SetFocus` at `0x18004a511`
- `USER32!SetFocus` at `0x18004a511`
- `USER32!SendDlgItemMessageW` at `0x18004a1aa`
- `USER32!SendDlgItemMessageW` at `0x18004a22c`
- `USER32!SendDlgItemMessageW` at `0x18004a46a`
- `USER32!SendDlgItemMessageW` at `0x18004a48d`
- `USER32!SendDlgItemMessageW` at `0x18004a1aa`
- `USER32!SendDlgItemMessageW` at `0x18004a22c`
- `USER32!SendDlgItemMessageW` at `0x18004a46a`
- `USER32!SendDlgItemMessageW` at `0x18004a48d`
- `USER32!InvalidateRect` at `0x18004a43f`
- `USER32!InvalidateRect` at `0x18004a43f`
- `USER32!GetWindowLongPtrW` at `0x18004a0e9`
- `USER32!GetWindowLongPtrW` at `0x18004a38d`
- `USER32!GetWindowLongPtrW` at `0x18004a3a2`
- `USER32!GetWindowLongPtrW` at `0x18004a0e9`
- `USER32!GetWindowLongPtrW` at `0x18004a38d`
- `USER32!GetWindowLongPtrW` at `0x18004a3a2`
- `USER32!UpdateWindow` at `0x18004a4f6`
- `USER32!UpdateWindow` at `0x18004a4f6`
- `USER32!EndDialog` at `0x18004a3d3`
- `USER32!EndDialog` at `0x18004a4df`
- `USER32!EndDialog` at `0x18004a3d3`
- `USER32!EndDialog` at `0x18004a4df`

## pseudocode

```c
INT_PTR __fastcall AdjustDlgProc(HWND a1, int a2, unsigned __int64 a3, HWND a4)
{
  LONG_PTR WindowLongPtrW; // r15
  unsigned int v10; // eax
  unsigned int v11; // edi
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // ecx
  int NearestInsert; // eax
  __int64 v16; // r8
  __int64 v17; // rdx
  LRESULT v18; // rax
  unsigned __int64 v19; // rbx
  int v20; // ecx
  WPARAM v21; // r8
  unsigned int v22; // ebx
  int v23; // r12d
  HWND *v24; // rcx
  HWND v25; // rbx
  LRESULT v26; // r14
  LONG_PTR v27; // rbx
  HWND v28; // rcx
  unsigned __int64 v29; // rbx
  int v30; // eax
  int v31; // esi
  unsigned int v32; // ebx
  int v33; // eax
  HWND v34; // rax
  HWND v35; // rax
  HWND v36; // rax
  int v37; // edx
  HWND DlgItem; // rdi
  HDC DC; // rbx
  int v40; // edx
  int lParam; // [rsp+20h] [rbp-40h]
  int v42; // [rsp+28h] [rbp-38h]
  WCHAR String[2]; // [rsp+30h] [rbp-30h] BYREF
  _DWORD v44[7]; // [rsp+34h] [rbp-2Ch] BYREF
  HWND v45; // [rsp+50h] [rbp-10h]

  WindowLongPtrW = GetWindowLongPtrW(a1, 16);
  switch ( a2 )
  {
    case 43:
      PaintAdjustLine(*(_QWORD *)(WindowLongPtrW + 8));
      return 1;
    case 44:
      v37 = *((_DWORD *)a4 + 1);
      if ( ((v37 - 201) & 0xFFFFFFFD) == 0 )
      {
        v44[0] = 0;
        DlgItem = GetDlgItem(a1, v37);
        wcscpy(String, L"W");
        DC = GetDC(DlgItem);
        MGetTextExtent(DC, String, 1, (__int64)v44);
        v40 = v44[0];
        if ( v44[0] < g_dyButtonHack + 2 )
          v40 = g_dyButtonHack + 2;
        *((_DWORD *)a4 + 4) = v40;
        ReleaseDC(DlgItem, DC);
      }
      return 1;
    case 272:
      SetWindowLongPtrW(a1, 16, (LONG_PTR)a4);
      if ( !(unsigned int)InitAdjustDlg(a1) )
        EndDialog(a1, 0);
      ShowWindow(a1, 5);
      UpdateWindow(a1);
      v34 = GetDlgItem(a1, 203);
      SetFocus(v34);
      v35 = GetDlgItem(a1, 203);
      MakeDragList(v35);
      v36 = GetDlgItem(a1, 201);
      MakeDragList(v36);
      return 0;
  }
  if ( a2 != 273 )
  {
    if ( a2 == uDragListMsg )
      return (int)HandleDragMsg(WindowLongPtrW, a1, a3, a4);
    return 0;
  }
  switch ( (unsigned __int16)a3 )
  {
    case 1u:
      v31 = 0;
      v32 = SendDlgItemMessageW(a1, 201, 0x188u, 0, 0);
      v33 = SendDlgItemMessageW(a1, 203, 0x188u, 0, 0);
      v42 = 1;
      v17 = 201;
      v16 = v32;
      if ( v33 != -1 )
        v31 = v33;
      lParam = v31;
      goto LABEL_43;
    case 2u:
      goto LABEL_34;
    case 0xC9u:
      v29 = a3 >> 16;
      v20 = (unsigned __int16)v29 - 2;
      if ( (unsigned __int16)v29 == 2 )
      {
        v21 = 1;
        goto LABEL_24;
      }
LABEL_36:
      if ( (unsigned int)(v20 - 2) <= 1 )
      {
        *(_OWORD *)&v44[1] = 0;
        v30 = SendMessageW(a4, 0x188u, 0, 0);
        if ( SendMessageW(a4, 0x198u, v30, (LPARAM)&v44[1]) != -1 )
          InvalidateRect(a4, (const RECT *)&v44[1], 0);
      }
      return 1;
    case 0xCAu:
      v24 = *(HWND **)(WindowLongPtrW + 8);
      v25 = *v24;
      memset(&v44[1], 0, 24);
      v45 = a1;
      v26 = CCSendNotify((__int64)v24, -705, (LPARAM)&v44[1]);
      v27 = GetWindowLongPtrW(v25, 0);
      v28 = *(HWND *)(v27 + 120);
      if ( v28 )
        *(_QWORD *)(GetWindowLongPtrW(v28, 16) + 8) = v27;
      *(_QWORD *)(WindowLongPtrW + 8) = v27;
      *(_DWORD *)(WindowLongPtrW + 16) = 0;
      if ( v26 != 2 && (unsigned int)InitAdjustDlg(a1) )
        return 1;
LABEL_34:
      EndDialog(a1, 1);
      return 1;
    case 0xCBu:
      v19 = a3 >> 16;
      if ( (unsigned __int16)v19 == 1 )
      {
        v22 = SendMessageW(a4, 0x188u, 0, 0);
        SendItemNotify(*(_QWORD *)(WindowLongPtrW + 8), v22, 4294966590LL);
        SafeEnableWindow(a1);
        v23 = (unsigned __int16)~((unsigned int)SendMessageW(a4, 0x199u, (int)v22, 0) >> 16) >> 15;
        SafeEnableWindow(a1);
        if ( v23 )
          GetNearestInsert(*(_QWORD *)(WindowLongPtrW + 8), v22 - 1, 0, 2);
        SafeEnableWindow(a1);
        if ( v23 )
          GetNearestInsert(
            *(_QWORD *)(WindowLongPtrW + 8),
            v22 + 2,
            *(unsigned int *)(*(_QWORD *)(WindowLongPtrW + 8) + 200LL),
            1);
        SafeEnableWindow(a1);
        return 1;
      }
      v20 = (unsigned __int16)v19 - 2;
      if ( (unsigned __int16)v19 == 2 )
      {
        v21 = 204;
LABEL_24:
        SendMessageW(a1, 0x111u, v21, 0);
        return 1;
      }
      goto LABEL_36;
    case 0xCCu:
      v18 = SendDlgItemMessageW(a1, 203, 0x188u, 0, 0);
      LBMoveButton(WindowLongPtrW, 203, v18, 201, 0, 0);
      break;
    case 0xCDu:
      CCSendNotify(*(_QWORD *)(WindowLongPtrW + 8), -709, 0);
      break;
    default:
      if ( (unsigned int)(unsigned __int16)a3 - 206 <= 1 )
      {
        v10 = SendDlgItemMessageW(a1, 203, 0x188u, 0, 0);
        v11 = v10;
        if ( a3 == 206 )
        {
          v12 = 0;
          v13 = 2;
          v14 = -1;
        }
        else
        {
          v12 = *(unsigned int *)(*(_QWORD *)(WindowLongPtrW + 8) + 200LL);
          v13 = 1;
          v14 = 2;
        }
        NearestInsert = GetNearestInsert(*(_QWORD *)(WindowLongPtrW + 8), v10 + v14, v12, v13);
        v42 = 0;
        v16 = v11;
        lParam = NearestInsert;
        v17 = 203;
LABEL_43:
        LBMoveButton(WindowLongPtrW, v17, v16, 203, lParam, v42);
        return 1;
      }
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18004a0b0  mov     [rsp-38h+arg_8], rbx
0x18004a0b5  push    rbp
0x18004a0b6  push    rsi
0x18004a0b7  push    rdi
0x18004a0b8  push    r12
0x18004a0ba  push    r13
0x18004a0bc  push    r14
0x18004a0be  push    r15
0x18004a0c0  mov     rbp, rsp
0x18004a0c3  sub     rsp, 60h
0x18004a0c7  mov     rax, cs:__security_cookie
0x18004a0ce  xor     rax, rsp
0x18004a0d1  mov     [rbp+var_8], rax
0x18004a0d5  mov     esi, edx
0x18004a0d7  mov     r12d, 10h
0x18004a0dd  mov     edx, r12d; nIndex
0x18004a0e0  mov     r14, r9
0x18004a0e3  mov     rbx, r8
0x18004a0e6  mov     rdi, rcx
0x18004a0e9  call    cs:__imp_GetWindowLongPtrW
0x18004a0ef  mov     r15, rax
0x18004a0f2  lea     r13d, [r12-0Fh]
0x18004a0f7  mov     eax, esi
0x18004a0f9  sub     eax, 2Bh ; '+'
0x18004a0fc  jz      loc_18004A5BA
0x18004a102  sub     eax, r13d
0x18004a105  jz      loc_18004A547
0x18004a10b  sub     eax, 0E4h
0x18004a110  jz      loc_18004A4BC
0x18004a116  cmp     eax, r13d
0x18004a119  jz      short loc_18004A13F
0x18004a11b  cmp     esi, cs:uDragListMsg
0x18004a121  jnz     loc_18004A540
0x18004a127  mov     r9, r14
0x18004a12a  mov     r8, rbx
0x18004a12d  mov     rdx, rdi
0x18004a130  mov     rcx, r15
0x18004a133  call    HandleDragMsg
0x18004a138  cdqe
0x18004a13a  jmp     loc_18004A5C9
0x18004a13f  movzx   ecx, bx
0x18004a142  sub     ecx, r13d
0x18004a145  jz      loc_18004A452
0x18004a14b  sub     ecx, r13d
0x18004a14e  jz      loc_18004A3CD
0x18004a154  sub     ecx, 0C7h
0x18004a15a  jz      loc_18004A3DE
0x18004a160  sub     ecx, r13d
0x18004a163  jz      loc_18004A35E
0x18004a169  sub     ecx, r13d
0x18004a16c  jz      loc_18004A249
0x18004a172  sub     ecx, r13d
0x18004a175  jz      loc_18004A210
0x18004a17b  sub     ecx, r13d
0x18004a17e  jz      short loc_18004A1FA
0x18004a180  sub     ecx, r13d
0x18004a183  jz      short loc_18004A18E
0x18004a185  cmp     ecx, r13d
0x18004a188  jnz     loc_18004A540
0x18004a18e  mov     r14d, 0CBh
0x18004a194  xor     esi, esi
0x18004a196  mov     edx, r14d; nIDDlgItem
0x18004a199  mov     [rsp+60h+lParam], rsi; lParam
0x18004a19e  xor     r9d, r9d; wParam
0x18004a1a1  mov     r8d, 188h; Msg
0x18004a1a7  mov     rcx, rdi; hDlg
0x18004a1aa  call    cs:__imp_SendDlgItemMessageW
0x18004a1b0  mov     r10, [r15+8]
0x18004a1b4  mov     rdi, rax
0x18004a1b7  cmp     rbx, 0CEh
0x18004a1be  jnz     short loc_18004A1CD
0x18004a1c0  mov     r8d, esi
0x18004a1c3  lea     r9d, [rsi+2]
0x18004a1c7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004a1cb  jmp     short loc_18004A1DC
0x18004a1cd  mov     r8d, [r10+0C8h]
0x18004a1d4  mov     r9d, r13d
0x18004a1d7  mov     ecx, 2
0x18004a1dc  lea     edx, [rax+rcx]
0x18004a1df  mov     rcx, r10
0x18004a1e2  call    GetNearestInsert
0x18004a1e7  mov     [rsp+60h+var_38], esi
0x18004a1eb  mov     r8d, edi
0x18004a1ee  mov     dword ptr [rsp+60h+lParam], eax
0x18004a1f2  mov     edx, r14d
0x18004a1f5  jmp     loc_18004A4AC
0x18004a1fa  mov     rcx, [r15+8]
0x18004a1fe  xor     r8d, r8d
0x18004a201  mov     edx, 0FFFFFD3Bh
0x18004a206  call    CCSendNotify
0x18004a20b  jmp     loc_18004A5C6
0x18004a210  xor     esi, esi
0x18004a212  mov     r14d, 0CBh
0x18004a218  mov     edx, r14d; nIDDlgItem
0x18004a21b  mov     [rsp+60h+lParam], rsi; lParam
0x18004a220  xor     r9d, r9d; wParam
0x18004a223  mov     r8d, 188h; Msg
0x18004a229  mov     rcx, rdi; hDlg
0x18004a22c  call    cs:__imp_SendDlgItemMessageW
0x18004a232  mov     [rsp+60h+var_38], esi
0x18004a236  lea     r9d, [r14-2]
0x18004a23a  mov     r8, rax
0x18004a23d  mov     dword ptr [rsp+60h+lParam], esi
0x18004a241  mov     edx, r14d
0x18004a244  jmp     loc_18004A4AF
0x18004a249  shr     rbx, 10h
0x18004a24d  movzx   ecx, bx
0x18004a250  sub     ecx, r13d
0x18004a253  jz      short loc_18004A27A
0x18004a255  sub     ecx, r13d
0x18004a258  jnz     loc_18004A3EA
0x18004a25e  mov     r8d, 0CCh; wParam
0x18004a264  mov     edx, 111h; Msg
0x18004a269  xor     r9d, r9d; lParam
0x18004a26c  mov     rcx, rdi; hWnd
0x18004a26f  call    cs:__imp_SendMessageW
0x18004a275  jmp     loc_18004A5C6
0x18004a27a  xor     r9d, r9d; lParam
0x18004a27d  xor     r8d, r8d; wParam
0x18004a280  mov     edx, 188h; Msg
0x18004a285  mov     rcx, r14; hWnd
0x18004a288  call    cs:__imp_SendMessageW
0x18004a28e  mov     rcx, [r15+8]
0x18004a292  mov     r8d, 0FFFFFD3Eh
0x18004a298  mov     edx, eax
0x18004a29a  mov     rbx, rax
0x18004a29d  call    SendItemNotify
0x18004a2a2  xor     esi, esi
0x18004a2a4  mov     r8, r14
0x18004a2a7  test    rax, rax
0x18004a2aa  mov     r9d, esi
0x18004a2ad  mov     edx, r13d
0x18004a2b0  mov     rcx, rdi; hWnd
0x18004a2b3  setnz   r9b
0x18004a2b7  call    SafeEnableWindow
0x18004a2bc  movsxd  r8, ebx; wParam
0x18004a2bf  xor     r9d, r9d; lParam
0x18004a2c2  mov     edx, 199h; Msg
0x18004a2c7  mov     rcx, r14; hWnd
0x18004a2ca  call    cs:__imp_SendMessageW
0x18004a2d0  shr     rax, 10h
0x18004a2d4  mov     r8, r14
0x18004a2d7  not     ax
0x18004a2da  mov     edx, 0CCh
0x18004a2df  movzx   r12d, ax
0x18004a2e3  mov     rcx, rdi; hWnd
0x18004a2e6  shr     r12d, 0Fh
0x18004a2ea  mov     r9d, r12d
0x18004a2ed  call    SafeEnableWindow
0x18004a2f2  test    r12d, r12d
0x18004a2f5  jz      short loc_18004A311
0x18004a2f7  mov     rcx, [r15+8]
0x18004a2fb  lea     edx, [rbx-1]
0x18004a2fe  lea     r9d, [rsi+2]
0x18004a302  xor     r8d, r8d
0x18004a305  call    GetNearestInsert
0x18004a30a  mov     r9d, r13d
0x18004a30d  test    eax, eax
0x18004a30f  jns     short loc_18004A314
0x18004a311  mov     r9d, esi
0x18004a314  mov     r8, r14
0x18004a317  mov     edx, 0CEh
0x18004a31c  mov     rcx, rdi; hWnd
0x18004a31f  call    SafeEnableWindow
0x18004a324  test    r12d, r12d
0x18004a327  jz      short loc_18004A346
0x18004a329  mov     rcx, [r15+8]
0x18004a32d  lea     edx, [rbx+2]
0x18004a330  mov     r9d, r13d
0x18004a333  mov     r8d, [rcx+0C8h]
0x18004a33a  call    GetNearestInsert
0x18004a33f  test    eax, eax
0x18004a341  js      short loc_18004A346
0x18004a343  mov     esi, r13d
0x18004a346  mov     r9d, esi
0x18004a349  mov     r8, r14
0x18004a34c  mov     edx, 0CFh
0x18004a351  mov     rcx, rdi; hWnd
0x18004a354  call    SafeEnableWindow
0x18004a359  jmp     loc_18004A5C6
0x18004a35e  mov     rcx, [r15+8]
0x18004a362  lea     r8, [rbp+var_2C+4]
0x18004a366  xorps   xmm0, xmm0
0x18004a369  xor     esi, esi
0x18004a36b  mov     edx, 0FFFFFD3Fh
0x18004a370  mov     rbx, [rcx]
0x18004a373  mov     qword ptr [rbp+var_2C+4], rsi
0x18004a377  movdqu  xmmword ptr [rbp+var_2C+0Ch], xmm0
0x18004a37c  mov     [rbp+var_10], rdi
0x18004a380  call    CCSendNotify
0x18004a385  xor     edx, edx; nIndex
0x18004a387  mov     rcx, rbx; hWnd
0x18004a38a  mov     r14, rax
0x18004a38d  call    cs:__imp_GetWindowLongPtrW
0x18004a393  mov     rbx, rax
0x18004a396  mov     rcx, [rax+78h]; hWnd
0x18004a39a  test    rcx, rcx
0x18004a39d  jz      short loc_18004A3AC
0x18004a39f  mov     edx, r12d; nIndex
0x18004a3a2  call    cs:__imp_GetWindowLongPtrW
0x18004a3a8  mov     [rax+8], rbx
0x18004a3ac  mov     [r15+8], rbx
0x18004a3b0  mov     [r15+10h], esi
0x18004a3b4  cmp     r14, 2
0x18004a3b8  jz      short loc_18004A3CD
0x18004a3ba  mov     rdx, r15
0x18004a3bd  mov     rcx, rdi; hWnd
0x18004a3c0  call    InitAdjustDlg
0x18004a3c5  test    eax, eax
0x18004a3c7  jnz     loc_18004A5C6
0x18004a3cd  mov     rdx, r13; nResult
0x18004a3d0  mov     rcx, rdi; hDlg
0x18004a3d3  call    cs:__imp_EndDialog
0x18004a3d9  jmp     loc_18004A5C6
0x18004a3de  shr     rbx, 10h
0x18004a3e2  movzx   ecx, bx
0x18004a3e5  sub     ecx, 2
0x18004a3e8  jz      short loc_18004A44A
0x18004a3ea  sub     ecx, 2
0x18004a3ed  jz      short loc_18004A3F8
0x18004a3ef  cmp     ecx, r13d
0x18004a3f2  jnz     loc_18004A5C6
0x18004a3f8  xorps   xmm0, xmm0
0x18004a3fb  xor     r9d, r9d; lParam
0x18004a3fe  xor     r8d, r8d; wParam
0x18004a401  mov     edx, 188h; Msg
0x18004a406  mov     rcx, r14; hWnd
0x18004a409  movups  xmmword ptr [rbp+var_2C+4], xmm0
0x18004a40d  call    cs:__imp_SendMessageW
0x18004a413  movsxd  r8, eax; wParam
0x18004a416  lea     r9, [rbp+var_2C+4]; lParam
0x18004a41a  mov     edx, 198h; Msg
0x18004a41f  mov     rcx, r14; hWnd
0x18004a422  call    cs:__imp_SendMessageW
0x18004a428  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004a42c  cmp     rax, rcx
0x18004a42f  jz      loc_18004A5C6
0x18004a435  xor     r8d, r8d; bErase
0x18004a438  lea     rdx, [rbp+var_2C+4]; lpRect
0x18004a43c  mov     rcx, r14; hWnd
0x18004a43f  call    cs:__imp_InvalidateRect
0x18004a445  jmp     loc_18004A5C6
0x18004a44a  mov     r8, r13
0x18004a44d  jmp     loc_18004A264
0x18004a452  xor     esi, esi
0x18004a454  xor     r9d, r9d; wParam
0x18004a457  mov     edx, 0C9h; nIDDlgItem
0x18004a45c  mov     [rsp+60h+lParam], rsi; lParam
0x18004a461  mov     r8d, 188h; Msg
0x18004a467  mov     rcx, rdi; hDlg
0x18004a46a  call    cs:__imp_SendDlgItemMessageW
0x18004a470  mov     r14d, 0CBh
0x18004a476  mov     [rsp+60h+lParam], rsi; lParam
0x18004a47b  mov     edx, r14d; nIDDlgItem
0x18004a47e  xor     r9d, r9d; wParam
0x18004a481  mov     r8d, 188h; Msg
0x18004a487  mov     rcx, rdi; hDlg
0x18004a48a  mov     rbx, rax
0x18004a48d  call    cs:__imp_SendDlgItemMessageW
0x18004a493  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004a497  mov     [rsp+60h+var_38], r13d
0x18004a49c  cmp     eax, ecx
0x18004a49e  lea     edx, [r14-2]
0x18004a4a2  mov     r8d, ebx
0x18004a4a5  cmovnz  esi, eax
0x18004a4a8  mov     dword ptr [rsp+60h+lParam], esi
0x18004a4ac  mov     r9d, r14d
0x18004a4af  mov     rcx, r15
0x18004a4b2  call    LBMoveButton
0x18004a4b7  jmp     loc_18004A5C6
0x18004a4bc  mov     r8, r14; dwNewLong
0x18004a4bf  mov     edx, r12d; nIndex
0x18004a4c2  mov     rcx, rdi; hWnd
0x18004a4c5  call    cs:__imp_SetWindowLongPtrW
0x18004a4cb  mov     rdx, r14
0x18004a4ce  mov     rcx, rdi; hWnd
0x18004a4d1  call    InitAdjustDlg
0x18004a4d6  test    eax, eax
0x18004a4d8  jnz     short loc_18004A4E5
0x18004a4da  xor     edx, edx; nResult
0x18004a4dc  mov     rcx, rdi; hDlg
0x18004a4df  call    cs:__imp_EndDialog
0x18004a4e5  mov     edx, 5; nCmdShow
0x18004a4ea  mov     rcx, rdi; hWnd
0x18004a4ed  call    cs:__imp_ShowWindow
0x18004a4f3  mov     rcx, rdi; hWnd
0x18004a4f6  call    cs:__imp_UpdateWindow
0x18004a4fc  mov     r14d, 0CBh
0x18004a502  mov     rcx, rdi; hDlg
0x18004a505  mov     edx, r14d; nIDDlgItem
0x18004a508  call    cs:__imp_GetDlgItem
0x18004a50e  mov     rcx, rax; hWnd
0x18004a511  call    cs:__imp_SetFocus
0x18004a517  mov     edx, r14d; nIDDlgItem
0x18004a51a  mov     rcx, rdi; hDlg
0x18004a51d  call    cs:__imp_GetDlgItem
0x18004a523  mov     rcx, rax; hLB
0x18004a526  call    MakeDragList
0x18004a52b  lea     edx, [r14-2]; nIDDlgItem
0x18004a52f  mov     rcx, rdi; hDlg
  ... truncated ...
```
