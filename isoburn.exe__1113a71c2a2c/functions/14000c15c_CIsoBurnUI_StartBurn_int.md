# CIsoBurnUI::_StartBurn(int)

- ea: `0x14000c15c`
- end: `0x14000c311`
- name: `?_StartBurn@CIsoBurnUI@@AEAAXH@Z`
- size: `437`
- prototype: `void __fastcall(CIsoBurnUI *__hidden this, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000af38`
- `0x14000b3c0`

## callees

- `0x140001fa0`
- `0x14000c15c`
- `0x140010010`

## import_xrefs

- `USER32!SendDlgItemMessageW` at `0x14000c1a2`
- `USER32!SendDlgItemMessageW` at `0x14000c1a2`
- `USER32!LoadStringW` at `0x14000c2bd`
- `USER32!LoadStringW` at `0x14000c2bd`
- `USER32!SendMessageW` at `0x14000c258`
- `USER32!SendMessageW` at `0x14000c258`
- `USER32!SetWindowTextW` at `0x14000c2da`
- `USER32!SetWindowTextW` at `0x14000c2da`
- `USER32!IsDlgButtonChecked` at `0x14000c1b4`
- `USER32!IsDlgButtonChecked` at `0x14000c1b4`
- `USER32!EnableWindow` at `0x14000c1d6`
- `USER32!EnableWindow` at `0x14000c1ed`
- `USER32!EnableWindow` at `0x14000c237`
- `USER32!EnableWindow` at `0x14000c1d6`
- `USER32!EnableWindow` at `0x14000c1ed`
- `USER32!EnableWindow` at `0x14000c237`
- `USER32!GetDlgItem` at `0x14000c1cb`
- `USER32!GetDlgItem` at `0x14000c1e2`
- `USER32!GetDlgItem` at `0x14000c22c`
- `USER32!GetDlgItem` at `0x14000c244`
- `USER32!GetDlgItem` at `0x14000c2cc`
- `USER32!GetDlgItem` at `0x14000c1cb`
- `USER32!GetDlgItem` at `0x14000c1e2`
- `USER32!GetDlgItem` at `0x14000c22c`
- `USER32!GetDlgItem` at `0x14000c244`
- `USER32!GetDlgItem` at `0x14000c2cc`
- `COMCTL32!__imp_DPA_GetPtr` at `0x14000c276`
- `COMCTL32!__imp_DPA_GetPtr` at `0x14000c276`

## pseudocode

```c
void __fastcall CIsoBurnUI::_StartBurn(CIsoBurnUI *this, int a2)
{
  LRESULT v4; // rbp
  BOOL v5; // r14d
  HWND DlgItem; // rax
  HWND v7; // rax
  int *v8; // rax
  HWND v9; // rax
  HWND v10; // rax
  __int64 v11; // rdi
  int (__fastcall *v12)(__int64, _QWORD, PVOID, BOOL, int, char *); // rbx
  PVOID Ptr; // rax
  HWND v14; // rax
  WCHAR Buffer[1024]; // [rsp+40h] [rbp-838h] BYREF

  v4 = SendDlgItemMessageW(*((HWND *)this + 1), 201, 0x147u, 0, 0);
  v5 = IsDlgButtonChecked(*((HWND *)this + 1), 207) == 1;
  DlgItem = GetDlgItem(*((HWND *)this + 1), 205);
  EnableWindow(DlgItem, 0);
  v7 = GetDlgItem(*((HWND *)this + 1), 207);
  EnableWindow(v7, 0);
  if ( *((_QWORD *)this + 20) )
  {
    v8 = (int *)*((_QWORD *)this + 19);
    if ( v8 )
    {
      if ( v4 >= 0 && v4 < *v8 )
      {
        v9 = GetDlgItem(*((HWND *)this + 1), 201);
        EnableWindow(v9, 0);
        v10 = GetDlgItem(*((HWND *)this + 1), 202);
        SendMessageW(v10, 0x402u, 0, 0);
        v11 = *((_QWORD *)this + 20);
        v12 = *(int (__fastcall **)(__int64, _QWORD, PVOID, BOOL, int, char *))(*(_QWORD *)v11 + 24LL);
        Ptr = DPA_GetPtr(*((HDPA *)this + 19), v4);
        if ( v12(v11, *((_QWORD *)this + 16), Ptr, v5, a2, (char *)this + 64) >= 0 )
        {
          LoadStringW(hInstance, 0x10Au, Buffer, 1024);
          v14 = GetDlgItem(*((HWND *)this + 1), 2);
          SetWindowTextW(v14, Buffer);
          *((_DWORD *)this + 46) = 1;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14000c15c  mov     [rsp+arg_10], rbx
0x14000c161  push    rbp
0x14000c162  push    rsi
0x14000c163  push    rdi
0x14000c164  push    r14
0x14000c166  push    r15
0x14000c168  sub     rsp, 850h
0x14000c16f  mov     rax, cs:__security_cookie
0x14000c176  xor     rax, rsp
0x14000c179  mov     [rsp+878h+var_38], rax
0x14000c181  mov     edi, 0C9h
0x14000c186  mov     [rsp+878h+lParam], 0; lParam
0x14000c18f  mov     r15d, edx
0x14000c192  mov     rsi, rcx
0x14000c195  mov     rcx, [rcx+8]; hDlg
0x14000c199  xor     r9d, r9d; wParam
0x14000c19c  mov     edx, edi; nIDDlgItem
0x14000c19e  lea     r8d, [rdi+7Eh]; Msg
0x14000c1a2  call    cs:__imp_SendDlgItemMessageW
0x14000c1a8  mov     rcx, [rsi+8]; hDlg
0x14000c1ac  lea     ebx, [rdi+6]
0x14000c1af  mov     edx, ebx; nIDButton
0x14000c1b1  mov     rbp, rax
0x14000c1b4  call    cs:__imp_IsDlgButtonChecked
0x14000c1ba  mov     rcx, [rsi+8]; hDlg
0x14000c1be  lea     edx, [rdi+4]; nIDDlgItem
0x14000c1c1  xor     r14d, r14d
0x14000c1c4  cmp     eax, 1
0x14000c1c7  setz    r14b
0x14000c1cb  call    cs:__imp_GetDlgItem
0x14000c1d1  mov     rcx, rax; hWnd
0x14000c1d4  xor     edx, edx; bEnable
0x14000c1d6  call    cs:__imp_EnableWindow
0x14000c1dc  mov     rcx, [rsi+8]; hDlg
0x14000c1e0  mov     edx, ebx; nIDDlgItem
0x14000c1e2  call    cs:__imp_GetDlgItem
0x14000c1e8  mov     rcx, rax; hWnd
0x14000c1eb  xor     edx, edx; bEnable
0x14000c1ed  call    cs:__imp_EnableWindow
0x14000c1f3  cmp     qword ptr [rsi+0A0h], 0
0x14000c1fb  jz      loc_14000C2EA
0x14000c201  mov     rax, [rsi+98h]
0x14000c208  test    rax, rax
0x14000c20b  jz      loc_14000C2EA
0x14000c211  test    rbp, rbp
0x14000c214  js      loc_14000C2EA
0x14000c21a  movsxd  rax, dword ptr [rax]
0x14000c21d  cmp     rbp, rax
0x14000c220  jge     loc_14000C2EA
0x14000c226  mov     rcx, [rsi+8]; hDlg
0x14000c22a  mov     edx, edi; nIDDlgItem
0x14000c22c  call    cs:__imp_GetDlgItem
0x14000c232  mov     rcx, rax; hWnd
0x14000c235  xor     edx, edx; bEnable
0x14000c237  call    cs:__imp_EnableWindow
0x14000c23d  mov     rcx, [rsi+8]; hDlg
0x14000c241  lea     edx, [rdi+1]; nIDDlgItem
0x14000c244  call    cs:__imp_GetDlgItem
0x14000c24a  xor     r9d, r9d; lParam
0x14000c24d  xor     r8d, r8d; wParam
0x14000c250  mov     rcx, rax; hWnd
0x14000c253  mov     edx, 402h; Msg
0x14000c258  call    cs:__imp_SendMessageW
0x14000c25e  mov     rdi, [rsi+0A0h]
0x14000c265  mov     rdx, rbp; i
0x14000c268  mov     rcx, [rsi+98h]; hdpa
0x14000c26f  mov     rax, [rdi]
0x14000c272  mov     rbx, [rax+18h]
0x14000c276  call    cs:__imp_DPA_GetPtr
0x14000c27c  lea     rdx, [rsi+40h]
0x14000c280  mov     r9d, r14d
0x14000c283  mov     [rsp+878h+var_850], rdx
0x14000c288  mov     r8, rax
0x14000c28b  mov     rdx, [rsi+80h]
0x14000c292  mov     rcx, rdi
0x14000c295  mov     rax, rbx
0x14000c298  mov     dword ptr [rsp+878h+lParam], r15d
0x14000c29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c2a2  test    eax, eax
0x14000c2a4  js      short loc_14000C2EA
0x14000c2a6  mov     rcx, cs:hInstance; hInstance
0x14000c2ad  lea     r8, [rsp+878h+Buffer]; lpBuffer
0x14000c2b2  mov     r9d, 400h; cchBufferMax
0x14000c2b8  mov     edx, 10Ah; uID
0x14000c2bd  call    cs:__imp_LoadStringW
0x14000c2c3  mov     rcx, [rsi+8]; hDlg
0x14000c2c7  mov     edx, 2; nIDDlgItem
0x14000c2cc  call    cs:__imp_GetDlgItem
0x14000c2d2  mov     rcx, rax; hWnd
0x14000c2d5  lea     rdx, [rsp+878h+Buffer]; lpString
0x14000c2da  call    cs:__imp_SetWindowTextW
0x14000c2e0  mov     dword ptr [rsi+0B8h], 1
0x14000c2ea  mov     rcx, [rsp+878h+var_38]
0x14000c2f2  xor     rcx, rsp; StackCookie
0x14000c2f5  call    __security_check_cookie
0x14000c2fa  mov     rbx, [rsp+878h+arg_10]
0x14000c302  add     rsp, 850h
0x14000c309  pop     r15
0x14000c30b  pop     r14
0x14000c30d  pop     rdi
0x14000c30e  pop     rsi
0x14000c30f  pop     rbp
0x14000c310  retn
```
