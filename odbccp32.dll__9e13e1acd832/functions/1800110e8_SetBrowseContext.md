# SetBrowseContext

- ea: `0x1800110e8`
- end: `0x18001155b`
- name: `SetBrowseContext`
- size: `1139`
- prototype: `__int64 __fastcall(HWND hDlg, __int64, __int64, __int64, __int16 *, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000c440`
- `0x180010668`
- `0x180010dc0`

## callees

- `0x18000fed0`
- `0x180010140`
- `0x18001085c`
- `0x1800110d0`
- `0x1800110e8`
- `0x180014aae`
- `0x180014ae0`
- `0x180015010`

## import_xrefs

- `USER32!SetWindowLongPtrA` at `0x1800112b8`
- `USER32!SetWindowLongPtrA` at `0x1800112b8`
- `USER32!GetWindowLongPtrA` at `0x1800111c2`
- `USER32!GetWindowLongPtrA` at `0x1800111c2`
- `USER32!SendMessageA` at `0x1800112e9`
- `USER32!SendMessageA` at `0x18001148e`
- `USER32!SendMessageA` at `0x1800112e9`
- `USER32!SendMessageA` at `0x18001148e`
- `USER32!LoadCursorA` at `0x180011151`
- `USER32!LoadCursorA` at `0x180011151`
- `USER32!SetCursor` at `0x18001115a`
- `USER32!SetCursor` at `0x18001123c`
- `USER32!SetCursor` at `0x180011527`
- `USER32!SetCursor` at `0x18001115a`
- `USER32!SetCursor` at `0x18001123c`
- `USER32!SetCursor` at `0x180011527`
- `USER32!SendMessageW` at `0x180011381`
- `USER32!SendMessageW` at `0x180011399`
- `USER32!SendMessageW` at `0x1800113fd`
- `USER32!SendMessageW` at `0x18001146c`
- `USER32!SendMessageW` at `0x1800114b1`
- `USER32!SendMessageW` at `0x1800114c6`
- `USER32!SendMessageW` at `0x18001151b`
- `USER32!SendMessageW` at `0x180011381`
- `USER32!SendMessageW` at `0x180011399`
- `USER32!SendMessageW` at `0x1800113fd`
- `USER32!SendMessageW` at `0x18001146c`
- `USER32!SendMessageW` at `0x1800114b1`
- `USER32!SendMessageW` at `0x1800114c6`
- `USER32!SendMessageW` at `0x18001151b`
- `USER32!GetDlgItem` at `0x18001117e`
- `USER32!GetDlgItem` at `0x180011454`
- `USER32!GetDlgItem` at `0x18001147a`
- `USER32!GetDlgItem` at `0x18001117e`
- `USER32!GetDlgItem` at `0x180011454`
- `USER32!GetDlgItem` at `0x18001147a`
- `SHELL32!SHGetFileInfoA` at `0x1800112d5`
- `SHELL32!SHGetFileInfoA` at `0x1800112d5`
- `SHELL32!SHGetMalloc` at `0x18001118c`
- `SHELL32!SHGetMalloc` at `0x18001118c`
- `SHELL32!SHGetDesktopFolder` at `0x1800111a7`
- `SHELL32!SHGetDesktopFolder` at `0x1800111a7`

## pseudocode

```c
__int64 __fastcall SetBrowseContext(HWND hDlg, __int64 a2, __int64 a3, __int64 a4, __int16 *a5, int a6)
{
  HWND v6; // rdi
  HCURSOR CursorA; // rax
  HWND DlgItem; // r12
  unsigned int v9; // r14d
  CHAR *Buf2; // rsi
  __int16 *WindowLongPtrA; // rax
  void *v12; // rdx
  __int16 *v13; // r15
  __int16 *v14; // rcx
  __int16 v15; // ax
  __int16 *v16; // rdi
  __int16 *v17; // rax
  __int16 v18; // bx
  __int64 v19; // rax
  HCURSOR v20; // rbx
  __int16 *v21; // rcx
  LPARAM v22; // rax
  HWND v23; // rax
  WPARAM v24; // rbx
  HWND v25; // rax
  HCURSOR hCursor; // [rsp+48h] [rbp-B8h]
  IMalloc *ppMalloc; // [rsp+50h] [rbp-B0h] BYREF
  IShellFolder *ppshf; // [rsp+58h] [rbp-A8h] BYREF
  HWND v30; // [rsp+60h] [rbp-A0h] BYREF
  int v31[2]; // [rsp+68h] [rbp-98h] BYREF
  LPARAM v32[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+90h] [rbp-70h]
  __int64 v35; // [rsp+A0h] [rbp-60h]
  LPARAM lParam[12]; // [rsp+B0h] [rbp-50h] BYREF
  SHFILEINFOA psfi; // [rsp+110h] [rbp+10h] BYREF
  wchar_t v38[264]; // [rsp+280h] [rbp+180h] BYREF

  v6 = hDlg;
  v30 = hDlg;
  memset_0(lParam, 0, 0x58u);
  ppMalloc = 0;
  ppshf = 0;
  *(_QWORD *)v31 = 0;
  CursorA = LoadCursorA(0, (LPCSTR)0x7F02);
  hCursor = SetCursor(CursorA);
  memset_0(&psfi, 0, sizeof(psfi));
  DlgItem = GetDlgItem(v6, 1884);
  if ( SHGetMalloc(&ppMalloc) < 0 )
  {
    v9 = 1;
LABEL_34:
    v20 = hCursor;
    goto LABEL_43;
  }
  Buf2 = 0;
  if ( SHGetDesktopFolder(&ppshf) < 0 )
    goto LABEL_37;
  WindowLongPtrA = (__int16 *)GetWindowLongPtrA(v6, 16);
  v12 = 0;
  v13 = WindowLongPtrA;
  if ( !a6 )
  {
    v21 = WindowLongPtrA;
    goto LABEL_21;
  }
  if ( a6 == 1 )
  {
    LODWORD(v30) = 0;
    GetDisplayName((__int64)a5, 0, 0, 0, (int *)&v30);
    if ( ((unsigned int)v30 & 0x20000000) == 0 )
    {
      LODWORD(Buf2) = 2;
      goto LABEL_37;
    }
    v21 = a5;
LABEL_21:
    Buf2 = (CHAR *)ConcatPidls(v21, 0);
    if ( Buf2 )
    {
LABEL_22:
      if ( !v13 )
      {
LABEL_24:
        SetWindowLongPtrA(v6, 16, (LONG_PTR)Buf2);
        v22 = SHGetFileInfoA(Buf2, 0, &psfi, 0x168u, 0x4009u);
        SendMessageA(DlgItem, 0x1003u, 1u, v22);
        if ( a6 == 3
          || ((int (__fastcall *)(IShellFolder *, CHAR *, _QWORD, GUID *, int *))ppshf->lpVtbl->BindToObject)(
               ppshf,
               Buf2,
               0,
               &IID_IShellFolder,
               v31) >= 0 )
        {
          ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
          ppshf = 0;
          lParam[0] = 4;
          while ( (unsigned int)SendMessageW(DlgItem, 0x104Bu, 0, (LPARAM)lParam) )
          {
            if ( lParam[5] )
              ((void (__fastcall *)(IMalloc *))ppMalloc->lpVtbl->Free)(ppMalloc);
            ++HIDWORD(lParam[0]);
          }
          SendMessageW(DlgItem, 0x1009u, 0, 0);
          if ( a6 == 3 )
          {
            ((void (__fastcall *)(IMalloc *))ppMalloc->lpVtbl->Release)(ppMalloc);
            v9 = 0;
            goto LABEL_34;
          }
          v32[0] = 3;
          v32[1] = 5;
          v35 = 0;
          v33 = 0;
          v34 = 0;
          SendMessageW(DlgItem, 0x1061u, 0, (LPARAM)v32);
          EnumFolderObjects(DlgItem, *(__int64 *)v31, 0, 0, (__int64)ppMalloc, 2, Buf2);
          GetDisplayName((__int64)Buf2, v38, 0x105u, 0, 0);
          v23 = GetDlgItem(v6, 1887);
          v24 = SendMessageW(v23, 0x143u, 0, (LPARAM)v38);
          v25 = GetDlgItem(v6, 1887);
          SendMessageA(v25, 0x14Eu, v24, 0);
          LODWORD(Buf2) = 1;
        }
        else
        {
          LODWORD(Buf2) = 0;
        }
        goto LABEL_37;
      }
LABEL_23:
      ((void (__fastcall *)(IMalloc *, __int16 *))ppMalloc->lpVtbl->Free)(ppMalloc, v13);
      goto LABEL_24;
    }
    LODWORD(Buf2) = 0;
LABEL_37:
    v20 = hCursor;
    goto LABEL_38;
  }
  if ( a6 != 2 )
    goto LABEL_22;
  v14 = WindowLongPtrA;
  if ( WindowLongPtrA )
  {
    v15 = *WindowLongPtrA;
    v16 = 0;
    while ( v15 )
    {
      v17 = (__int16 *)PidlNext(v14, v12);
      v14 = v17;
      if ( !v17 )
        break;
      v15 = *v17;
      if ( v15 )
        v16 = v14;
    }
    if ( v16 )
    {
      v18 = *v16;
      *v16 = (__int16)v12;
      v19 = ConcatPidls(v13, v12);
      *v16 = v18;
      Buf2 = (CHAR *)v19;
      v6 = v30;
      goto LABEL_23;
    }
  }
  v20 = hCursor;
  SetCursor(hCursor);
LABEL_38:
  SendMessageW(DlgItem, 0x101Eu, 1u, 0xFFFF);
  SendMessageW(DlgItem, 0x1016u, 2u, 0);
  if ( ppshf )
    ((void (__fastcall *)(IShellFolder *))ppshf->lpVtbl->Release)(ppshf);
  if ( *(_QWORD *)v31 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 16LL))(*(_QWORD *)v31);
  ((void (__fastcall *)(IMalloc *))ppMalloc->lpVtbl->Release)(ppMalloc);
  SendMessageW(DlgItem, 0x1030u, 0, (LPARAM)ListViewCompare);
  v9 = (unsigned int)Buf2;
LABEL_43:
  SetCursor(v20);
  return v9;
}

```

## disassembly

```asm
0x1800110e8  mov     [rsp-8+arg_8], rbx
0x1800110ed  mov     [rsp-8+arg_10], rsi
0x1800110f2  push    rbp
0x1800110f3  push    rdi
0x1800110f4  push    r12
0x1800110f6  push    r14
0x1800110f8  push    r15
0x1800110fa  lea     rbp, [rsp-3A0h]
0x180011102  sub     rsp, 4A0h
0x180011109  mov     rax, cs:__security_cookie
0x180011110  xor     rax, rsp
0x180011113  mov     [rbp+3C0h+var_30], rax
0x18001111a  mov     rbx, [rbp+3C0h+arg_20]
0x180011121  xor     edx, edx; Val
0x180011123  mov     rdi, rcx
0x180011126  mov     [rsp+4C0h+var_460], rcx
0x18001112b  lea     rcx, [rbp+3C0h+lParam]; void *
0x18001112f  lea     r8d, [rdx+58h]; Size
0x180011133  call    memset_0
0x180011138  xor     r15d, r15d
0x18001113b  mov     edx, 7F02h; lpCursorName
0x180011140  xor     ecx, ecx; hInstance
0x180011142  mov     [rsp+4C0h+ppMalloc], r15
0x180011147  mov     [rsp+4C0h+ppshf], r15
0x18001114c  mov     qword ptr [rsp+4C0h+var_458], r15
0x180011151  call    cs:__imp_LoadCursorA
0x180011157  mov     rcx, rax; hCursor
0x18001115a  call    cs:__imp_SetCursor
0x180011160  xor     edx, edx; Val
0x180011162  lea     rcx, [rbp+3C0h+psfi]; void *
0x180011166  mov     r8d, 168h; Size
0x18001116c  mov     [rsp+4C0h+hCursor], rax
0x180011171  call    memset_0
0x180011176  mov     edx, 75Ch; nIDDlgItem
0x18001117b  mov     rcx, rdi; hDlg
0x18001117e  call    cs:__imp_GetDlgItem
0x180011184  lea     rcx, [rsp+4C0h+ppMalloc]; ppMalloc
0x180011189  mov     r12, rax
0x18001118c  call    cs:__imp_SHGetMalloc
0x180011192  test    eax, eax
0x180011194  jns     short loc_18001119F
0x180011196  lea     r14d, [r15+1]
0x18001119a  jmp     loc_1800113BC
0x18001119f  lea     rcx, [rsp+4C0h+ppshf]; ppshf
0x1800111a4  mov     esi, r15d
0x1800111a7  call    cs:__imp_SHGetDesktopFolder
0x1800111ad  mov     r14d, 1
0x1800111b3  test    eax, eax
0x1800111b5  js      loc_18001149B
0x1800111bb  lea     edx, [r14+0Fh]; nIndex
0x1800111bf  mov     rcx, rdi; hWnd
0x1800111c2  call    cs:__imp_GetWindowLongPtrA
0x1800111c8  mov     ecx, [rbp+3C0h+arg_28]
0x1800111ce  xor     edx, edx; void *
0x1800111d0  mov     r15, rax
0x1800111d3  test    ecx, ecx
0x1800111d5  jz      loc_18001127E
0x1800111db  sub     ecx, r14d
0x1800111de  jz      short loc_180011247
0x1800111e0  cmp     ecx, r14d
0x1800111e3  jnz     loc_180011294
0x1800111e9  mov     rcx, rax
0x1800111ec  test    rax, rax
0x1800111ef  jz      short loc_180011234
0x1800111f1  movzx   eax, word ptr [rax]
0x1800111f4  mov     edi, edx
0x1800111f6  test    ax, ax
0x1800111f9  jz      short loc_180011214
0x1800111fb  call    PidlNext
0x180011200  mov     rcx, rax
0x180011203  test    rax, rax
0x180011206  jz      short loc_180011214
0x180011208  movzx   eax, word ptr [rax]
0x18001120b  test    ax, ax
0x18001120e  cmovnz  rdi, rcx
0x180011212  jmp     short loc_1800111F6
0x180011214  test    rdi, rdi
0x180011217  jz      short loc_180011234
0x180011219  movzx   ebx, word ptr [rdi]
0x18001121c  mov     rcx, r15; Src
0x18001121f  mov     [rdi], dx
0x180011222  call    ConcatPidls
0x180011227  mov     [rdi], bx
0x18001122a  mov     rsi, rax
0x18001122d  mov     rdi, [rsp+4C0h+var_460]
0x180011232  jmp     short loc_180011299
0x180011234  mov     rbx, [rsp+4C0h+hCursor]
0x180011239  mov     rcx, rbx; hCursor
0x18001123c  call    cs:__imp_SetCursor
0x180011242  jmp     loc_1800114A0
0x180011247  lea     rax, [rsp+4C0h+var_460]
0x18001124c  mov     dword ptr [rsp+4C0h+var_460], edx
0x180011250  xor     r9d, r9d
0x180011253  mov     qword ptr [rsp+4C0h+uFlags], rax
0x180011258  xor     r8d, r8d
0x18001125b  mov     rcx, rbx
0x18001125e  call    GetDisplayName
0x180011263  test    dword ptr [rsp+4C0h+var_460], 20000000h
0x18001126b  jnz     short loc_180011277
0x18001126d  mov     esi, 2
0x180011272  jmp     loc_18001149B
0x180011277  xor     edx, edx
0x180011279  mov     rcx, rbx
0x18001127c  jmp     short loc_180011281
0x18001127e  mov     rcx, r15; Src
0x180011281  call    ConcatPidls
0x180011286  xor     edx, edx
0x180011288  mov     rsi, rax
0x18001128b  test    rax, rax
0x18001128e  jz      loc_180011499
0x180011294  test    r15, r15
0x180011297  jz      short loc_1800112AD
0x180011299  mov     rcx, [rsp+4C0h+ppMalloc]
0x18001129e  mov     rdx, r15
0x1800112a1  mov     rax, [rcx]
0x1800112a4  mov     rax, [rax+28h]
0x1800112a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112ad  mov     r8, rsi; dwNewLong
0x1800112b0  mov     edx, 10h; nIndex
0x1800112b5  mov     rcx, rdi; hWnd
0x1800112b8  call    cs:__imp_SetWindowLongPtrA
0x1800112be  mov     r9d, 168h; cbFileInfo
0x1800112c4  mov     [rsp+4C0h+uFlags], 4009h; uFlags
0x1800112cc  lea     r8, [rbp+3C0h+psfi]; psfi
0x1800112d0  xor     edx, edx; dwFileAttributes
0x1800112d2  mov     rcx, rsi; pszPath
0x1800112d5  call    cs:__imp_SHGetFileInfoA
0x1800112db  mov     r8, r14; wParam
0x1800112de  mov     edx, 1003h; Msg
0x1800112e3  mov     r9, rax; lParam
0x1800112e6  mov     rcx, r12; hWnd
0x1800112e9  call    cs:__imp_SendMessageA
0x1800112ef  cmp     [rbp+3C0h+arg_28], 3
0x1800112f6  jz      short loc_18001132F
0x1800112f8  mov     rcx, [rsp+4C0h+ppshf]
0x1800112fd  lea     rdx, [rsp+4C0h+var_458]
0x180011302  mov     qword ptr [rsp+4C0h+uFlags], rdx
0x180011307  lea     r9, IID_IShellFolder
0x18001130e  xor     r8d, r8d
0x180011311  mov     rdx, rsi
0x180011314  mov     rax, [rcx]
0x180011317  mov     rax, [rax+28h]
0x18001131b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011320  xor     r15d, r15d
0x180011323  test    eax, eax
0x180011325  jns     short loc_180011332
0x180011327  mov     esi, r15d
0x18001132a  jmp     loc_18001149B
0x18001132f  xor     r15d, r15d
0x180011332  mov     rcx, [rsp+4C0h+ppshf]
0x180011337  mov     rax, [rcx]
0x18001133a  mov     rax, [rax+10h]
0x18001133e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011343  mov     [rsp+4C0h+ppshf], r15
0x180011348  mov     ebx, 104Bh
0x18001134d  mov     [rbp+3C0h+lParam], 4
0x180011355  jmp     short loc_180011375
0x180011357  mov     rdx, [rbp+3C0h+var_3E8]
0x18001135b  test    rdx, rdx
0x18001135e  jz      short loc_180011371
0x180011360  mov     rcx, [rsp+4C0h+ppMalloc]
0x180011365  mov     rax, [rcx]
0x180011368  mov     rax, [rax+28h]
0x18001136c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011371  add     dword ptr [rbp+3C0h+lParam+4], r14d
0x180011375  lea     r9, [rbp+3C0h+lParam]; lParam
0x180011379  xor     r8d, r8d; wParam
0x18001137c  mov     edx, ebx; Msg
0x18001137e  mov     rcx, r12; hWnd
0x180011381  call    cs:__imp_SendMessageW
0x180011387  test    eax, eax
0x180011389  jnz     short loc_180011357
0x18001138b  xor     r9d, r9d; lParam
0x18001138e  xor     r8d, r8d; wParam
0x180011391  mov     edx, 1009h; Msg
0x180011396  mov     rcx, r12; hWnd
0x180011399  call    cs:__imp_SendMessageW
0x18001139f  cmp     [rbp+3C0h+arg_28], 3
0x1800113a6  jnz     short loc_1800113C6
0x1800113a8  mov     rcx, [rsp+4C0h+ppMalloc]
0x1800113ad  mov     rax, [rcx]
0x1800113b0  mov     rax, [rax+10h]
0x1800113b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113b9  mov     r14d, r15d
0x1800113bc  mov     rbx, [rsp+4C0h+hCursor]
0x1800113c1  jmp     loc_180011524
0x1800113c6  xorps   xmm0, xmm0
0x1800113c9  lea     r9, [rsp+4C0h+var_450]; lParam
0x1800113ce  movups  xmmword ptr [rsp+4C0h+var_450], xmm0
0x1800113d3  xor     eax, eax
0x1800113d5  mov     [rsp+4C0h+var_450], 3
0x1800113de  xor     r8d, r8d; wParam
0x1800113e1  mov     dword ptr [rsp+4C0h+var_450+8], 5
0x1800113e9  mov     edx, 1061h; Msg
0x1800113ee  mov     [rbp+3C0h+var_420], rax
0x1800113f2  mov     rcx, r12; hWnd
0x1800113f5  movups  [rbp+3C0h+var_440], xmm0
0x1800113f9  movups  [rbp+3C0h+var_430], xmm0
0x1800113fd  call    cs:__imp_SendMessageW
0x180011403  mov     rax, [rsp+4C0h+ppMalloc]
0x180011408  xor     r9d, r9d; int
0x18001140b  mov     rdx, qword ptr [rsp+4C0h+var_458]; int
0x180011410  xor     r8d, r8d; int
0x180011413  mov     [rsp+4C0h+Buf2], rsi; Buf2
0x180011418  mov     rcx, r12; int
0x18001141b  mov     [rsp+4C0h+var_498], 2; int
0x180011423  mov     qword ptr [rsp+4C0h+uFlags], rax; __int64
0x180011428  call    EnumFolderObjects
0x18001142d  xor     r9d, r9d
0x180011430  mov     qword ptr [rsp+4C0h+uFlags], r15
0x180011435  mov     r8d, 105h
0x18001143b  lea     rdx, [rbp+3C0h+var_240]
0x180011442  mov     rcx, rsi
0x180011445  call    GetDisplayName
0x18001144a  mov     esi, 75Fh
0x18001144f  mov     rcx, rdi; hDlg
0x180011452  mov     edx, esi; nIDDlgItem
0x180011454  call    cs:__imp_GetDlgItem
0x18001145a  lea     r9, [rbp+3C0h+var_240]; lParam
0x180011461  xor     r8d, r8d; wParam
0x180011464  mov     rcx, rax; hWnd
0x180011467  mov     edx, 143h; Msg
0x18001146c  call    cs:__imp_SendMessageW
0x180011472  mov     edx, esi; nIDDlgItem
0x180011474  mov     rcx, rdi; hDlg
0x180011477  mov     rbx, rax
0x18001147a  call    cs:__imp_GetDlgItem
0x180011480  xor     r9d, r9d; lParam
0x180011483  mov     r8, rbx; wParam
0x180011486  mov     rcx, rax; hWnd
0x180011489  mov     edx, 14Eh; Msg
0x18001148e  call    cs:__imp_SendMessageA
0x180011494  mov     esi, r14d
0x180011497  jmp     short loc_18001149B
0x180011499  mov     esi, edx
0x18001149b  mov     rbx, [rsp+4C0h+hCursor]
0x1800114a0  mov     r9d, 0FFFFh; lParam
0x1800114a6  mov     r8, r14; wParam
0x1800114a9  mov     edx, 101Eh; Msg
0x1800114ae  mov     rcx, r12; hWnd
0x1800114b1  call    cs:__imp_SendMessageW
0x1800114b7  xor     r9d, r9d; lParam
0x1800114ba  mov     edx, 1016h; Msg
0x1800114bf  mov     rcx, r12; hWnd
0x1800114c2  lea     r8d, [r9+2]; wParam
0x1800114c6  call    cs:__imp_SendMessageW
0x1800114cc  mov     rcx, [rsp+4C0h+ppshf]
0x1800114d1  test    rcx, rcx
0x1800114d4  jz      short loc_1800114E2
0x1800114d6  mov     rax, [rcx]
0x1800114d9  mov     rax, [rax+10h]
0x1800114dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114e2  mov     rcx, qword ptr [rsp+4C0h+var_458]
0x1800114e7  test    rcx, rcx
0x1800114ea  jz      short loc_1800114F8
0x1800114ec  mov     rax, [rcx]
0x1800114ef  mov     rax, [rax+10h]
0x1800114f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114f8  mov     rcx, [rsp+4C0h+ppMalloc]
0x1800114fd  mov     rax, [rcx]
0x180011500  mov     rax, [rax+10h]
0x180011504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011509  lea     r9, ListViewCompare; lParam
0x180011510  xor     r8d, r8d; wParam
0x180011513  mov     edx, 1030h; Msg
0x180011518  mov     rcx, r12; hWnd
0x18001151b  call    cs:__imp_SendMessageW
0x180011521  mov     r14d, esi
0x180011524  mov     rcx, rbx; hCursor
0x180011527  call    cs:__imp_SetCursor
0x18001152d  mov     eax, r14d
0x180011530  mov     rcx, [rbp+3C0h+var_30]
0x180011537  xor     rcx, rsp; StackCookie
0x18001153a  call    __security_check_cookie
0x18001153f  lea     r11, [rsp+4C0h+var_20]
0x180011547  mov     rbx, [r11+38h]
0x18001154b  mov     rsi, [r11+40h]
0x18001154f  mov     rsp, r11
0x180011552  pop     r15
0x180011554  pop     r14
0x180011556  pop     r12
0x180011558  pop     rdi
0x180011559  pop     rbp
0x18001155a  retn
```
