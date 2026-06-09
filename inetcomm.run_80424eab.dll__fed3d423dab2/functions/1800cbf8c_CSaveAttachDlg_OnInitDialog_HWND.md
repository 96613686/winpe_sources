# CSaveAttachDlg::OnInitDialog(HWND__ *)

- ea: `0x1800cbf8c`
- end: `0x1800cc2df`
- name: `?OnInitDialog@CSaveAttachDlg@@AEAAJPEAUHWND__@@@Z`
- size: `851`
- prototype: `int(CSaveAttachDlg *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800cbc1c`

## callees

- `0x18008e390`
- `0x18008ea70`
- `0x18008ece0`
- `0x1800cba14`
- `0x1800cbb54`
- `0x1800cbf8c`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!CenterDialog` at `0x1800cc00b`
- `MSOERT2!CenterDialog` at `0x1800cc00b`
- `SHLWAPI!SHAutoComplete` at `0x1800cc03a`
- `SHLWAPI!SHAutoComplete` at `0x1800cc03a`
- `USER32!SendMessageA` at `0x1800cc0b3`
- `USER32!SendMessageA` at `0x1800cc132`
- `USER32!SendMessageA` at `0x1800cc25e`
- `USER32!SendMessageA` at `0x1800cc276`
- `USER32!SendMessageA` at `0x1800cc2a7`
- `USER32!SendMessageA` at `0x1800cc0b3`
- `USER32!SendMessageA` at `0x1800cc132`
- `USER32!SendMessageA` at `0x1800cc25e`
- `USER32!SendMessageA` at `0x1800cc276`
- `USER32!SendMessageA` at `0x1800cc2a7`
- `USER32!GetDlgItem` at `0x1800cc019`
- `USER32!GetDlgItem` at `0x1800cc074`
- `USER32!GetDlgItem` at `0x1800cc019`
- `USER32!GetDlgItem` at `0x1800cc074`
- `USER32!SendMessageW` at `0x1800cc066`
- `USER32!SendMessageW` at `0x1800cc1f0`
- `USER32!SendMessageW` at `0x1800cc066`
- `USER32!SendMessageW` at `0x1800cc1f0`
- `USER32!SetFocus` at `0x1800cc2b1`
- `USER32!SetFocus` at `0x1800cc2b1`
- `USER32!GetClientRect` at `0x1800cc247`
- `USER32!GetClientRect` at `0x1800cc247`
- `USER32!GetSystemMetrics` at `0x1800cc0fb`
- `USER32!GetSystemMetrics` at `0x1800cc108`
- `USER32!GetSystemMetrics` at `0x1800cc0fb`
- `USER32!GetSystemMetrics` at `0x1800cc108`

## string_xrefs

- `0x1800cc1a7`: `ImageList_ReplaceIcon`

## pseudocode

```c
__int64 __fastcall CSaveAttachDlg::OnInitDialog(CSaveAttachDlg *this, HWND a2)
{
  HWND DlgItem; // rax
  LPARAM *v6; // r9
  HWND v7; // rax
  __int64 v8; // rcx
  int v9; // edi
  int SystemMetrics; // ebx
  int v11; // eax
  HIMAGELIST v12; // r15
  __int64 i; // rdi
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(HIMAGELIST, __int64, __int64); // rax
  __int64 v16; // r14
  int v17; // eax
  HWND v18; // rcx
  HWND v19; // rcx
  int v20; // [rsp+20h] [rbp-E0h]
  int cInitial; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  LPARAM v24[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v25; // [rsp+58h] [rbp-A8h]
  __int128 v26; // [rsp+68h] [rbp-98h]
  __int64 v27; // [rsp+78h] [rbp-88h]
  int v28; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v29[32]; // [rsp+84h] [rbp-7Ch] BYREF
  int v30; // [rsp+A4h] [rbp-5Ch]
  __int64 v31; // [rsp+A8h] [rbp-58h]
  LPARAM v32; // [rsp+E0h] [rbp-20h] BYREF
  int v33; // [rsp+ECh] [rbp-14h]
  int v34; // [rsp+F0h] [rbp-10h]
  struct tagRECT Rect; // [rsp+140h] [rbp+40h] BYREF
  LPARAM lParam[66]; // [rsp+150h] [rbp+50h] BYREF

  cInitial = 0;
  v22 = 0;
  v23 = 0;
  memset_0(&v28, 0, 0x58u);
  *((_QWORD *)this + 2) = a2;
  *(_OWORD *)v24 = 0;
  v27 = 0;
  v25 = 0;
  v26 = 0;
  Rect = 0;
  CenterDialog(a2);
  DlgItem = GetDlgItem(a2, 702);
  *((_QWORD *)this + 4) = DlgItem;
  if ( !DlgItem )
    return 2147500037LL;
  SHAutoComplete(DlgItem, 1u);
  v6 = (LPARAM *)((char *)this + 40);
  if ( this == (CSaveAttachDlg *)-40LL )
  {
    HrGetLastOpenFileDirectoryW(260, lParam);
    v6 = lParam;
  }
  SendMessageW(*((HWND *)this + 4), 0xCu, 0, (LPARAM)v6);
  v7 = GetDlgItem(a2, 701);
  *((_QWORD *)this + 3) = v7;
  *(_OWORD *)v24 = 0;
  LODWORD(v24[1]) = 0;
  v27 = 0;
  LODWORD(v24[0]) = 6;
  v25 = 0;
  v26 = 0;
  SendMessageA(v7, 0x101Bu, 0, (LPARAM)v24);
  memset_0(v29, 0, 0x54u);
  v8 = *((_QWORD *)this + 1);
  v28 = 7;
  if ( !(*(unsigned int (__fastcall **)(__int64, int *, __int64 *))(*(_QWORD *)v8 + 384LL))(v8, &cInitial, &v22) )
  {
    v9 = cInitial;
    SystemMetrics = GetSystemMetrics(50);
    v11 = GetSystemMetrics(49);
    v12 = ImageList_Create(v11, SystemMetrics, 0, v9, v20);
    SendMessageA(*((HWND *)this + 3), 0x1003u, 1u, (LPARAM)v12);
    for ( i = 0; (unsigned int)i < cInitial; i = (unsigned int)(i + 1) )
    {
      if ( !(unsigned int)HrAttachDataFromBodyPart(
                            *((_QWORD *)this + 1),
                            *(_QWORD *)(v22 + 8 * i),
                            &v23,
                            *((unsigned int *)this + 140)) )
      {
        v14 = v23;
        if ( *((_DWORD *)this + 140) || !v23 || *(_DWORD *)(v23 + 1592) )
        {
          *(_QWORD *)&v29[20] = v23 + 520;
          v15 = (__int64 (__fastcall *)(HIMAGELIST, __int64, __int64))qword_1800F2358;
          v16 = *(_QWORD *)(v23 + 1560);
          if ( qword_1800F2358 == -1 )
          {
            GetProcFromComCtl32(&qword_1800F2358, "ImageList_ReplaceIcon");
            v15 = (__int64 (__fastcall *)(HIMAGELIST, __int64, __int64))qword_1800F2358;
          }
          if ( v15 )
            v17 = v15(v12, 0xFFFFFFFFLL, v16);
          else
            v17 = -1;
          v18 = (HWND)*((_QWORD *)this + 3);
          v30 = v17;
          v31 = v14;
          if ( SendMessageW(v18, 0x104Du, 0, (LPARAM)&v28) == -1 )
          {
            HrFreeAttachData(v14);
            v23 = 0;
          }
        }
      }
    }
    if ( v22 )
    {
      ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
      v22 = 0;
    }
  }
  GetClientRect(*((HWND *)this + 3), &Rect);
  SendMessageA(*((HWND *)this + 3), 0x101Eu, 0, LOWORD(Rect.right));
  SendMessageA(*((HWND *)this + 3), 0x1036u, 0, 32);
  memset_0(&v32, 0, 0x58u);
  v19 = (HWND)*((_QWORD *)this + 3);
  v34 = 2;
  v33 = 2;
  SendMessageA(v19, 0x102Bu, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&v32);
  SetFocus(*((HWND *)this + 3));
  return 0;
}

```

## disassembly

```asm
0x1800cbf8c  mov     [rsp-8+arg_10], rbx
0x1800cbf91  push    rbp
0x1800cbf92  push    rsi
0x1800cbf93  push    rdi
0x1800cbf94  push    r14
0x1800cbf96  push    r15
0x1800cbf98  lea     rbp, [rsp-270h]
0x1800cbfa0  sub     rsp, 370h
0x1800cbfa7  mov     rax, cs:__security_cookie
0x1800cbfae  xor     rax, rsp
0x1800cbfb1  mov     [rbp+290h+var_30], rax
0x1800cbfb8  mov     rbx, rdx
0x1800cbfbb  mov     [rsp+390h+cInitial], 0
0x1800cbfc3  xor     edx, edx; Val
0x1800cbfc5  mov     [rsp+390h+var_358], 0
0x1800cbfce  mov     rsi, rcx
0x1800cbfd1  mov     [rsp+390h+var_350], 0
0x1800cbfda  lea     rcx, [rbp+290h+var_310]; void *
0x1800cbfde  lea     r8d, [rdx+58h]; Size
0x1800cbfe2  call    memset_0
0x1800cbfe7  xorps   xmm0, xmm0
0x1800cbfea  mov     [rsi+10h], rbx
0x1800cbfee  xor     eax, eax
0x1800cbff0  mov     rcx, rbx
0x1800cbff3  movups  xmmword ptr [rsp+390h+var_348], xmm0
0x1800cbff8  mov     [rsp+390h+var_318], rax
0x1800cbffd  movups  [rsp+390h+var_338], xmm0
0x1800cc002  movups  [rsp+390h+var_328], xmm0
0x1800cc007  movups  xmmword ptr [rbp+290h+Rect.left], xmm0
0x1800cc00b  call    cs:__imp_CenterDialog
0x1800cc011  mov     edx, 2BEh; nIDDlgItem
0x1800cc016  mov     rcx, rbx; hDlg
0x1800cc019  call    cs:__imp_GetDlgItem
0x1800cc01f  mov     [rsi+20h], rax
0x1800cc023  test    rax, rax
0x1800cc026  jnz     short loc_1800CC032
0x1800cc028  mov     eax, 80004005h
0x1800cc02d  jmp     loc_1800CC2B9
0x1800cc032  mov     edx, 1; dwFlags
0x1800cc037  mov     rcx, rax; hwndEdit
0x1800cc03a  call    cs:__imp_SHAutoComplete
0x1800cc040  lea     r9, [rsi+28h]
0x1800cc044  test    r9, r9
0x1800cc047  jnz     short loc_1800CC05B
0x1800cc049  lea     rdx, [rbp+290h+lParam]
0x1800cc04d  mov     ecx, 104h
0x1800cc052  call    HrGetLastOpenFileDirectoryW
0x1800cc057  lea     r9, [rbp+290h+lParam]; lParam
0x1800cc05b  mov     rcx, [rsi+20h]; hWnd
0x1800cc05f  xor     r8d, r8d; wParam
0x1800cc062  lea     edx, [r8+0Ch]; Msg
0x1800cc066  call    cs:__imp_SendMessageW
0x1800cc06c  mov     edx, 2BDh; nIDDlgItem
0x1800cc071  mov     rcx, rbx; hDlg
0x1800cc074  call    cs:__imp_GetDlgItem
0x1800cc07a  xorps   xmm0, xmm0
0x1800cc07d  lea     r9, [rsp+390h+var_348]; lParam
0x1800cc082  xor     ecx, ecx
0x1800cc084  mov     [rsi+18h], rax
0x1800cc088  movups  xmmword ptr [rsp+390h+var_348], xmm0
0x1800cc08d  mov     dword ptr [rsp+390h+var_348+8], ecx
0x1800cc091  xor     r8d, r8d; wParam
0x1800cc094  mov     [rsp+390h+var_318], rcx
0x1800cc099  mov     edx, 101Bh; Msg
0x1800cc09e  mov     rcx, rax; hWnd
0x1800cc0a1  mov     dword ptr [rsp+390h+var_348], 6
0x1800cc0a9  movups  [rsp+390h+var_338], xmm0
0x1800cc0ae  movups  [rsp+390h+var_328], xmm0
0x1800cc0b3  call    cs:__imp_SendMessageA
0x1800cc0b9  xor     edx, edx; Val
0x1800cc0bb  lea     rcx, [rbp+290h+var_310+4]; void *
0x1800cc0bf  lea     r8d, [rdx+54h]; Size
0x1800cc0c3  call    memset_0
0x1800cc0c8  mov     rcx, [rsi+8]
0x1800cc0cc  lea     r8, [rsp+390h+var_358]
0x1800cc0d1  mov     dword ptr [rbp+290h+var_310], 7
0x1800cc0d8  lea     rdx, [rsp+390h+cInitial]
0x1800cc0dd  mov     rax, [rcx]
0x1800cc0e0  mov     rax, [rax+180h]
0x1800cc0e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc0ec  test    eax, eax
0x1800cc0ee  jnz     loc_1800CC23F
0x1800cc0f4  mov     edi, [rsp+390h+cInitial]
0x1800cc0f8  lea     ecx, [rax+32h]; nIndex
0x1800cc0fb  call    cs:__imp_GetSystemMetrics
0x1800cc101  mov     ecx, 31h ; '1'; nIndex
0x1800cc106  mov     ebx, eax
0x1800cc108  call    cs:__imp_GetSystemMetrics
0x1800cc10e  mov     r9d, edi; cInitial
0x1800cc111  xor     r8d, r8d; flags
0x1800cc114  mov     ecx, eax; cx
0x1800cc116  mov     edx, ebx; cy
0x1800cc118  call    ImageList_Create
0x1800cc11d  mov     rcx, [rsi+18h]; hWnd
0x1800cc121  mov     r9, rax; lParam
0x1800cc124  mov     edx, 1003h; Msg
0x1800cc129  mov     r8d, 1; wParam
0x1800cc12f  mov     r15, rax
0x1800cc132  call    cs:__imp_SendMessageA
0x1800cc138  xor     edi, edi
0x1800cc13a  cmp     [rsp+390h+cInitial], edi
0x1800cc13e  jbe     loc_1800CC219
0x1800cc144  mov     rdx, [rsp+390h+var_358]
0x1800cc149  lea     r8, [rsp+390h+var_350]
0x1800cc14e  mov     r9d, [rsi+230h]
0x1800cc155  mov     rcx, [rsi+8]
0x1800cc159  mov     rdx, [rdx+rdi*8]
0x1800cc15d  call    HrAttachDataFromBodyPart
0x1800cc162  test    eax, eax
0x1800cc164  jnz     loc_1800CC20D
0x1800cc16a  mov     rbx, [rsp+390h+var_350]
0x1800cc16f  cmp     [rsi+230h], eax
0x1800cc175  jnz     short loc_1800CC188
0x1800cc177  test    rbx, rbx
0x1800cc17a  jz      short loc_1800CC188
0x1800cc17c  cmp     [rbx+638h], eax
0x1800cc182  jz      loc_1800CC20D
0x1800cc188  lea     rax, [rbx+208h]
0x1800cc18f  mov     [rbp+290h+var_2F8], rax
0x1800cc193  mov     rax, cs:qword_1800F2358
0x1800cc19a  mov     r14, [rbx+618h]
0x1800cc1a1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800cc1a5  jnz     short loc_1800CC1C1
0x1800cc1a7  lea     rdx, aImagelistRepla; "ImageList_ReplaceIcon"
0x1800cc1ae  lea     rcx, qword_1800F2358
0x1800cc1b5  call    _GetProcFromComCtl32
0x1800cc1ba  mov     rax, cs:qword_1800F2358
0x1800cc1c1  test    rax, rax
0x1800cc1c4  jz      short loc_1800CC1D6
0x1800cc1c6  mov     r8, r14
0x1800cc1c9  or      edx, 0FFFFFFFFh
0x1800cc1cc  mov     rcx, r15
0x1800cc1cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc1d4  jmp     short loc_1800CC1D9
0x1800cc1d6  or      eax, 0FFFFFFFFh
0x1800cc1d9  mov     rcx, [rsi+18h]; hWnd
0x1800cc1dd  lea     r9, [rbp+290h+var_310]; lParam
0x1800cc1e1  xor     r8d, r8d; wParam
0x1800cc1e4  mov     [rbp+290h+var_2EC], eax
0x1800cc1e7  mov     edx, 104Dh; Msg
0x1800cc1ec  mov     [rbp+290h+var_2E8], rbx
0x1800cc1f0  call    cs:__imp_SendMessageW
0x1800cc1f6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800cc1fa  jnz     short loc_1800CC20D
0x1800cc1fc  mov     rcx, rbx
0x1800cc1ff  call    HrFreeAttachData
0x1800cc204  mov     [rsp+390h+var_350], 0
0x1800cc20d  inc     edi
0x1800cc20f  cmp     edi, [rsp+390h+cInitial]
0x1800cc213  jb      loc_1800CC144
0x1800cc219  mov     rdx, [rsp+390h+var_358]
0x1800cc21e  test    rdx, rdx
0x1800cc221  jz      short loc_1800CC23F
0x1800cc223  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800cc22a  mov     rax, [rcx]
0x1800cc22d  mov     rax, [rax+28h]
0x1800cc231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cc236  mov     [rsp+390h+var_358], 0
0x1800cc23f  mov     rcx, [rsi+18h]; hWnd
0x1800cc243  lea     rdx, [rbp+290h+Rect]; lpRect
0x1800cc247  call    cs:__imp_GetClientRect
0x1800cc24d  movzx   r9d, word ptr [rbp+290h+Rect.right]; lParam
0x1800cc252  xor     r8d, r8d; wParam
0x1800cc255  mov     rcx, [rsi+18h]; hWnd
0x1800cc259  mov     edx, 101Eh; Msg
0x1800cc25e  call    cs:__imp_SendMessageA
0x1800cc264  mov     rcx, [rsi+18h]; hWnd
0x1800cc268  mov     r9d, 20h ; ' '; lParam
0x1800cc26e  xor     r8d, r8d; wParam
0x1800cc271  mov     edx, 1036h; Msg
0x1800cc276  call    cs:__imp_SendMessageA
0x1800cc27c  xor     edx, edx; Val
0x1800cc27e  lea     rcx, [rbp+290h+var_2B0]; void *
0x1800cc282  lea     r8d, [rdx+58h]; Size
0x1800cc286  call    memset_0
0x1800cc28b  mov     rcx, [rsi+18h]; hWnd
0x1800cc28f  lea     r9, [rbp+290h+var_2B0]; lParam
0x1800cc293  mov     eax, 2
0x1800cc298  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x1800cc29c  mov     edx, 102Bh; Msg
0x1800cc2a1  mov     [rbp+290h+var_2A0], eax
0x1800cc2a4  mov     [rbp+290h+var_2A4], eax
0x1800cc2a7  call    cs:__imp_SendMessageA
0x1800cc2ad  mov     rcx, [rsi+18h]; hWnd
0x1800cc2b1  call    cs:__imp_SetFocus
0x1800cc2b7  xor     eax, eax
0x1800cc2b9  mov     rcx, [rbp+290h+var_30]
0x1800cc2c0  xor     rcx, rsp; StackCookie
0x1800cc2c3  call    __security_check_cookie
0x1800cc2c8  mov     rbx, [rsp+390h+arg_10]
0x1800cc2d0  add     rsp, 370h
0x1800cc2d7  pop     r15
0x1800cc2d9  pop     r14
0x1800cc2db  pop     rdi
0x1800cc2dc  pop     rsi
0x1800cc2dd  pop     rbp
0x1800cc2de  retn
```
