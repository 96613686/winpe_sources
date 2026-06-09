# ListView_InstallChecks

- ea: `0x1800465c4`
- end: `0x18004675c`
- name: `ListView_InstallChecks`
- size: `408`
- prototype: `int __fastcall(HWND hWnd, HINSTANCE hInstance)`
- caller_count: `6`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800176f8`
- `0x18001abbc`
- `0x180027d50`
- `0x18002fb40`
- `0x18003154c`
- `0x180032a04`

## callees

- `0x1800395ec`
- `0x180039780`
- `0x1800465c4`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x180046716`
- `api-ms-win-core-atoms-l1-1-0!GlobalAddAtomW` at `0x180046716`
- `GDI32!DeleteObject` at `0x180046658`
- `GDI32!DeleteObject` at `0x18004668c`
- `GDI32!DeleteObject` at `0x1800466b6`
- `GDI32!DeleteObject` at `0x1800466e8`
- `GDI32!DeleteObject` at `0x180046658`
- `GDI32!DeleteObject` at `0x18004668c`
- `GDI32!DeleteObject` at `0x1800466b6`
- `GDI32!DeleteObject` at `0x1800466e8`
- `USER32!LoadIconW` at `0x18004663c`
- `USER32!LoadIconW` at `0x180046670`
- `USER32!LoadIconW` at `0x18004669a`
- `USER32!LoadIconW` at `0x1800466cc`
- `USER32!LoadIconW` at `0x18004663c`
- `USER32!LoadIconW` at `0x180046670`
- `USER32!LoadIconW` at `0x18004669a`
- `USER32!LoadIconW` at `0x1800466cc`
- `USER32!GetWindowLongW` at `0x180046600`
- `USER32!GetWindowLongW` at `0x180046600`
- `USER32!SetPropW` at `0x180046749`
- `USER32!SetPropW` at `0x180046749`
- `USER32!SetWindowLongPtrW` at `0x180046736`
- `USER32!SetWindowLongPtrW` at `0x180046736`
- `USER32!SendMessageW` at `0x1800466ff`
- `USER32!SendMessageW` at `0x1800466ff`
- `USER32!GetSystemMetrics` at `0x180046615`
- `USER32!GetSystemMetrics` at `0x180046622`
- `USER32!GetSystemMetrics` at `0x180046615`
- `USER32!GetSystemMetrics` at `0x180046622`
- `USER32!GetWindowLongPtrW` at `0x1800465dc`
- `USER32!GetWindowLongPtrW` at `0x1800465dc`

## pseudocode

```c
int __fastcall ListView_InstallChecks(HWND hWnd, HINSTANCE hInstance)
{
  const WCHAR *v4; // rax
  int v5; // r14d
  int SystemMetrics; // ebx
  int v7; // eax
  UINT v8; // r8d
  int v9; // r9d
  struct _IMAGELIST *v10; // rbx
  HICON IconW; // rax
  int v12; // edx
  HICON v13; // rsi
  HICON v14; // rax
  int v15; // edx
  HICON v16; // rsi
  HICON v17; // rax
  int v18; // edx
  HICON v19; // rsi
  HICON v20; // rax
  int v21; // edx
  HICON v22; // rsi
  void *v23; // rax
  int v25; // [rsp+20h] [rbp-48h]

  if ( (__int64 (__fastcall *)(HWND, UINT, WPARAM))GetWindowLongPtrW(hWnd, -4) == LvxcbProc )
  {
    LODWORD(v4) = 1;
  }
  else
  {
    v5 = GetWindowLongW(hWnd, -20) & 0x400000;
    SystemMetrics = GetSystemMetrics(50);
    v7 = GetSystemMetrics(49);
    v10 = ImageList_Create(v7, SystemMetrics, v8, v9, v25);
    IconW = LoadIconW(hInstance, (LPCWSTR)0x33);
    v13 = IconW;
    if ( IconW )
    {
      ImageList_ReplaceIcon(v10, v12, IconW);
      DeleteObject(v13);
    }
    v14 = LoadIconW(hInstance, (LPCWSTR)(v5 != 0 ? 62LL : 50LL));
    v16 = v14;
    if ( v14 )
    {
      ImageList_ReplaceIcon(v10, v15, v14);
      DeleteObject(v16);
    }
    v17 = LoadIconW(hInstance, (LPCWSTR)0x3C);
    v19 = v17;
    if ( v17 )
    {
      ImageList_ReplaceIcon(v10, v18, v17);
      DeleteObject(v19);
    }
    v20 = LoadIconW(hInstance, (LPCWSTR)(v5 != 0 ? 63LL : 61LL));
    v22 = v20;
    if ( v20 )
    {
      ImageList_ReplaceIcon(v10, v21, v20);
      DeleteObject(v22);
    }
    SendMessageW(hWnd, 0x1003u, 2u, (LPARAM)v10);
    if ( lpString || (v4 = (const WCHAR *)GlobalAddAtomW(L"RASLVXCB"), lpString = v4, (_WORD)v4) )
    {
      v23 = (void *)SetWindowLongPtrW(hWnd, -4, (LONG_PTR)LvxcbProc);
      LODWORD(v4) = SetPropW(hWnd, lpString, v23);
    }
  }
  return (int)v4;
}

```

## disassembly

```asm
0x1800465c4  push    rbx
0x1800465c6  push    rbp
0x1800465c7  push    rsi
0x1800465c8  push    rdi
0x1800465c9  push    r12
0x1800465cb  push    r14
0x1800465cd  sub     rsp, 38h
0x1800465d1  mov     rbp, rdx
0x1800465d4  mov     rdi, rcx
0x1800465d7  mov     edx, 0FFFFFFFCh; nIndex
0x1800465dc  call    cs:__imp_GetWindowLongPtrW
0x1800465e2  lea     r12, LvxcbProc
0x1800465e9  cmp     rax, r12
0x1800465ec  jnz     short loc_1800465F8
0x1800465ee  mov     eax, 1
0x1800465f3  jmp     loc_18004674F
0x1800465f8  mov     edx, 0FFFFFFECh; nIndex
0x1800465fd  mov     rcx, rdi; hWnd
0x180046600  call    cs:__imp_GetWindowLongW
0x180046606  mov     r14d, eax
0x180046609  mov     ecx, 32h ; '2'; nIndex
0x18004660e  and     r14d, 400000h
0x180046615  call    cs:__imp_GetSystemMetrics
0x18004661b  mov     ecx, 31h ; '1'; nIndex
0x180046620  mov     ebx, eax
0x180046622  call    cs:__imp_GetSystemMetrics
0x180046628  mov     ecx, eax; cx
0x18004662a  mov     edx, ebx; cy
0x18004662c  call    ImageList_Create
0x180046631  mov     edx, 33h ; '3'; lpIconName
0x180046636  mov     rcx, rbp; hInstance
0x180046639  mov     rbx, rax
0x18004663c  call    cs:__imp_LoadIconW
0x180046642  mov     rsi, rax
0x180046645  test    rax, rax
0x180046648  jz      short loc_18004665E
0x18004664a  mov     r8, rax; hicon
0x18004664d  mov     rcx, rbx; himl
0x180046650  call    ImageList_ReplaceIcon
0x180046655  mov     rcx, rsi; ho
0x180046658  call    cs:__imp_DeleteObject
0x18004665e  mov     eax, r14d
0x180046661  mov     rcx, rbp; hInstance
0x180046664  neg     eax
0x180046666  sbb     rdx, rdx
0x180046669  and     edx, 0Ch
0x18004666c  add     rdx, 32h ; '2'; lpIconName
0x180046670  call    cs:__imp_LoadIconW
0x180046676  mov     rsi, rax
0x180046679  test    rax, rax
0x18004667c  jz      short loc_180046692
0x18004667e  mov     r8, rax; hicon
0x180046681  mov     rcx, rbx; himl
0x180046684  call    ImageList_ReplaceIcon
0x180046689  mov     rcx, rsi; ho
0x18004668c  call    cs:__imp_DeleteObject
0x180046692  mov     edx, 3Ch ; '<'; lpIconName
0x180046697  mov     rcx, rbp; hInstance
0x18004669a  call    cs:__imp_LoadIconW
0x1800466a0  mov     rsi, rax
0x1800466a3  test    rax, rax
0x1800466a6  jz      short loc_1800466BC
0x1800466a8  mov     r8, rax; hicon
0x1800466ab  mov     rcx, rbx; himl
0x1800466ae  call    ImageList_ReplaceIcon
0x1800466b3  mov     rcx, rsi; ho
0x1800466b6  call    cs:__imp_DeleteObject
0x1800466bc  neg     r14d
0x1800466bf  mov     rcx, rbp; hInstance
0x1800466c2  sbb     rdx, rdx
0x1800466c5  and     edx, 2
0x1800466c8  add     rdx, 3Dh ; '='; lpIconName
0x1800466cc  call    cs:__imp_LoadIconW
0x1800466d2  mov     rsi, rax
0x1800466d5  test    rax, rax
0x1800466d8  jz      short loc_1800466EE
0x1800466da  mov     r8, rax; hicon
0x1800466dd  mov     rcx, rbx; himl
0x1800466e0  call    ImageList_ReplaceIcon
0x1800466e5  mov     rcx, rsi; ho
0x1800466e8  call    cs:__imp_DeleteObject
0x1800466ee  mov     r9, rbx; lParam
0x1800466f1  mov     edx, 1003h; Msg
0x1800466f6  mov     r8d, 2; wParam
0x1800466fc  mov     rcx, rdi; hWnd
0x1800466ff  call    cs:__imp_SendMessageW
0x180046705  cmp     cs:lpString, 0
0x18004670d  jnz     short loc_18004672B
0x18004670f  lea     rcx, aRaslvxcb; "RASLVXCB"
0x180046716  call    cs:__imp_GlobalAddAtomW
0x18004671c  movzx   eax, ax
0x18004671f  mov     cs:lpString, rax
0x180046726  test    rax, rax
0x180046729  jz      short loc_18004674F
0x18004672b  mov     r8, r12; dwNewLong
0x18004672e  mov     edx, 0FFFFFFFCh; nIndex
0x180046733  mov     rcx, rdi; hWnd
0x180046736  call    cs:__imp_SetWindowLongPtrW
0x18004673c  mov     rdx, cs:lpString; lpString
0x180046743  mov     rcx, rdi; hWnd
0x180046746  mov     r8, rax; hData
0x180046749  call    cs:__imp_SetPropW
0x18004674f  add     rsp, 38h
0x180046753  pop     r14
0x180046755  pop     r12
0x180046757  pop     rdi
0x180046758  pop     rsi
0x180046759  pop     rbp
0x18004675a  pop     rbx
0x18004675b  retn
```
