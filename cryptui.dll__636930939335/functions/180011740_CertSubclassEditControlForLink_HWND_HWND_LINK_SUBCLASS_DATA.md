# CertSubclassEditControlForLink(HWND__ *,HWND__ *,_LINK_SUBCLASS_DATA *)

- ea: `0x180011740`
- end: `0x180011858`
- name: `?CertSubclassEditControlForLink@@YAXPEAUHWND__@@0PEAU_LINK_SUBCLASS_DATA@@@Z`
- size: `280`
- prototype: `void(HWND, HWND, struct _LINK_SUBCLASS_DATA *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000f2b0`

## callees

- `0x180011740`
- `0x180012b18`
- `0x18003e582`
- `0x18003e5c0`

## import_xrefs

- `USER32!GetWindowLongPtrA` at `0x180011807`
- `USER32!GetWindowLongPtrA` at `0x180011807`
- `USER32!SetWindowLongPtrA` at `0x18001181c`
- `USER32!SetWindowLongPtrA` at `0x180011831`
- `USER32!SetWindowLongPtrA` at `0x18001181c`
- `USER32!SetWindowLongPtrA` at `0x180011831`
- `USER32!SendMessageW` at `0x1800117cf`
- `USER32!SendMessageW` at `0x1800117f2`
- `USER32!SendMessageW` at `0x1800117cf`
- `USER32!SendMessageW` at `0x1800117f2`

## pseudocode

```c
void __fastcall CertSubclassEditControlForLink(HWND a1, HWND a2, struct _LINK_SUBCLASS_DATA *a3)
{
  HWND Window; // rax
  HWND v6; // rcx
  __int64 v7; // [rsp+20h] [rbp-A8h]
  __int64 v8; // [rsp+28h] [rbp-A0h]
  __int64 v9; // [rsp+30h] [rbp-98h]
  __int64 v10; // [rsp+38h] [rbp-90h]
  __int64 v11; // [rsp+48h] [rbp-80h]
  LPARAM v12[3]; // [rsp+60h] [rbp-68h] BYREF
  LPARAM lParam[7]; // [rsp+78h] [rbp-50h] BYREF

  Window = IsolationAwareCreateWindowExW(
             (__int64)a1,
             (__int64)a2,
             (__int64)a3,
             0x80000001,
             v7,
             v8,
             v9,
             v10,
             a1,
             v11,
             HinstDll);
  *((_QWORD *)a3 + 3) = Window;
  if ( Window )
  {
    memset_0(v12, 0, 0x48u);
    lParam[2] = (LPARAM)HinstDll;
    LODWORD(v12[0]) = 72;
    v12[1] = (LPARAM)a2;
    v12[2] = 1;
    SendMessageW(a2, 0xB2u, 0, (LPARAM)lParam);
    v6 = (HWND)*((_QWORD *)a3 + 3);
    lParam[3] = *((_QWORD *)a3 + 4);
    SendMessageW(v6, 0x432u, 0, (LPARAM)v12);
  }
  *((_DWORD *)a3 + 10) = 0;
  *((_QWORD *)a3 + 1) = GetWindowLongPtrA(a2, -4);
  SetWindowLongPtrA(a2, -21, (LONG_PTR)a3);
  SetWindowLongPtrA(a2, -4, (LONG_PTR)LinkSubclassProc);
}

```

## disassembly

```asm
0x180011740  mov     [rsp+arg_18], rbx
0x180011745  push    rdi
0x180011746  sub     rsp, 0C0h
0x18001174d  mov     rax, cs:__security_cookie
0x180011754  xor     rax, rsp
0x180011757  mov     [rsp+0C8h+var_18], rax
0x18001175f  mov     rax, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * HinstDll
0x180011766  mov     r9d, 80000001h
0x18001176c  mov     [rsp+0C8h+var_78], rax
0x180011771  mov     rbx, r8
0x180011774  mov     [rsp+0C8h+var_88], rcx
0x180011779  mov     rdi, rdx
0x18001177c  call    IsolationAwareCreateWindowExW
0x180011781  mov     [rbx+18h], rax
0x180011785  test    rax, rax
0x180011788  jz      short loc_1800117F8
0x18001178a  xor     edx, edx; Val
0x18001178c  lea     rcx, [rsp+0C8h+var_68]; void *
0x180011791  lea     r8d, [rdx+48h]; Size
0x180011795  call    memset_0
0x18001179a  mov     rax, cs:?HinstDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * HinstDll
0x1800117a1  lea     r9, [rsp+0C8h+lParam]; lParam
0x1800117a6  xor     r8d, r8d; wParam
0x1800117a9  mov     [rsp+0C8h+var_40], rax
0x1800117b1  mov     edx, 0B2h; Msg
0x1800117b6  mov     dword ptr [rsp+0C8h+var_68], 48h ; 'H'
0x1800117be  mov     rcx, rdi; hWnd
0x1800117c1  mov     [rsp+0C8h+var_60], rdi
0x1800117c6  mov     [rsp+0C8h+var_58], 1
0x1800117cf  call    cs:__imp_SendMessageW
0x1800117d5  mov     rax, [rbx+20h]
0x1800117d9  lea     r9, [rsp+0C8h+var_68]; lParam
0x1800117de  mov     rcx, [rbx+18h]; hWnd
0x1800117e2  xor     r8d, r8d; wParam
0x1800117e5  mov     edx, 432h; Msg
0x1800117ea  mov     [rsp+0C8h+var_38], rax
0x1800117f2  call    cs:__imp_SendMessageW
0x1800117f8  mov     edx, 0FFFFFFFCh; nIndex
0x1800117fd  mov     dword ptr [rbx+28h], 0
0x180011804  mov     rcx, rdi; hWnd
0x180011807  call    cs:__imp_GetWindowLongPtrA
0x18001180d  mov     r8, rbx; dwNewLong
0x180011810  mov     edx, 0FFFFFFEBh; nIndex
0x180011815  mov     rcx, rdi; hWnd
0x180011818  mov     [rbx+8], rax
0x18001181c  call    cs:__imp_SetWindowLongPtrA
0x180011822  lea     r8, ?LinkSubclassProc@@YA_JPEAUHWND__@@I_K_J@Z; dwNewLong
0x180011829  mov     edx, 0FFFFFFFCh; nIndex
0x18001182e  mov     rcx, rdi; hWnd
0x180011831  call    cs:__imp_SetWindowLongPtrA
0x180011837  mov     rcx, [rsp+0C8h+var_18]
0x18001183f  xor     rcx, rsp; StackCookie
0x180011842  call    __security_check_cookie
0x180011847  mov     rbx, [rsp+0C8h+arg_18]
0x18001184f  add     rsp, 0C0h
0x180011856  pop     rdi
0x180011857  retn
```
