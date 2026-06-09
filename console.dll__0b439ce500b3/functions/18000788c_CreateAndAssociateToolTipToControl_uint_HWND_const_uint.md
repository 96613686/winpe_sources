# CreateAndAssociateToolTipToControl(uint,HWND__ * const,uint)

- ea: `0x18000788c`
- end: `0x180007992`
- name: `?CreateAndAssociateToolTipToControl@@YAXIQEAUHWND__@@I@Z`
- size: `262`
- prototype: `void __fastcall(unsigned int nIDDlgItem, HWND, UINT uID)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b5a0`
- `0x18000c7e4`
- `0x18000cea0`

## callees

- `0x1800015b0`
- `0x180002088`
- `0x18000788c`
- `0x180008748`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800078f7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800078f7`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180007962`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180007962`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180007931`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180007931`

## pseudocode

```c
void __fastcall CreateAndAssociateToolTipToControl(__int64 nIDDlgItem, HWND a2, __int64 uID, __int64 a4)
{
  UINT v4; // esi
  int v6; // ebp
  HWND Window; // rdi
  int v8; // [rsp+20h] [rbp-2B8h]
  int v9; // [rsp+28h] [rbp-2B0h]
  int v10; // [rsp+30h] [rbp-2A8h]
  int v11; // [rsp+38h] [rbp-2A0h]
  LPARAM lParam[10]; // [rsp+60h] [rbp-278h] BYREF
  WCHAR Buffer[256]; // [rsp+B0h] [rbp-228h] BYREF

  v4 = uID;
  v6 = nIDDlgItem;
  Window = IsolationAwareCreateWindowExW(nIDDlgItem, (__int64)a2, uID, a4, v8, v9, v10, v11, a2);
  if ( Window )
  {
    memset_0(Buffer, 0, sizeof(Buffer));
    if ( LoadStringW(ghInstance, v4, Buffer, 256) > 0 )
    {
      memset_0(lParam, 0, 0x48u);
      lParam[0] = 0x1100000048LL;
      lParam[1] = (LPARAM)a2;
      lParam[2] = (LPARAM)GetDlgItem(a2, v6);
      lParam[6] = (LPARAM)Buffer;
      SendMessageW(Window, 0x432u, 0, (LPARAM)lParam);
    }
  }
}

```

## disassembly

```asm
0x18000788c  mov     [rsp+arg_18], rbx
0x180007891  push    rbp
0x180007892  push    rsi
0x180007893  push    rdi
0x180007894  sub     rsp, 2C0h
0x18000789b  mov     rax, cs:__security_cookie
0x1800078a2  xor     rax, rsp
0x1800078a5  mov     [rsp+2D8h+var_28], rax
0x1800078ad  mov     esi, r8d
0x1800078b0  mov     [rsp+2D8h+var_298], rdx; HWND
0x1800078b5  mov     rbx, rdx
0x1800078b8  mov     ebp, ecx
0x1800078ba  call    IsolationAwareCreateWindowExW
0x1800078bf  mov     rdi, rax
0x1800078c2  test    rax, rax
0x1800078c5  jz      loc_18000796E
0x1800078cb  xor     edx, edx; Val
0x1800078cd  lea     rcx, [rsp+2D8h+Buffer]; void *
0x1800078d5  mov     r8d, 200h; Size
0x1800078db  call    memset_0
0x1800078e0  mov     rcx, cs:?ghInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x1800078e7  lea     r8, [rsp+2D8h+Buffer]; lpBuffer
0x1800078ef  mov     r9d, 100h; cchBufferMax
0x1800078f5  mov     edx, esi; uID
0x1800078f7  call    cs:__imp_LoadStringW
0x1800078fe  nop     dword ptr [rax+rax+00h]
0x180007903  test    eax, eax
0x180007905  jle     short loc_18000796E
0x180007907  mov     esi, 48h ; 'H'
0x18000790c  lea     rcx, [rsp+2D8h+lParam]; void *
0x180007911  mov     r8d, esi; Size
0x180007914  xor     edx, edx; Val
0x180007916  call    memset_0
0x18000791b  mov     edx, ebp; nIDDlgItem
0x18000791d  mov     dword ptr [rsp+2D8h+lParam], esi
0x180007921  mov     rcx, rbx; hDlg
0x180007924  mov     [rsp+2D8h+var_270], rbx
0x180007929  mov     dword ptr [rsp+2D8h+lParam+4], 11h
0x180007931  call    cs:__imp_GetDlgItem
0x180007938  nop     dword ptr [rax+rax+00h]
0x18000793d  mov     [rsp+2D8h+var_268], rax
0x180007942  lea     r9, [rsp+2D8h+lParam]; lParam
0x180007947  lea     rax, [rsp+2D8h+Buffer]
0x18000794f  xor     r8d, r8d; wParam
0x180007952  mov     edx, 432h; Msg
0x180007957  mov     [rsp+2D8h+var_248], rax
0x18000795f  mov     rcx, rdi; hWnd
0x180007962  call    cs:__imp_SendMessageW
0x180007969  nop     dword ptr [rax+rax+00h]
0x18000796e  mov     rcx, [rsp+2D8h+var_28]
0x180007976  xor     rcx, rsp; StackCookie
0x180007979  call    __security_check_cookie
0x18000797e  mov     rbx, [rsp+2D8h+arg_18]
0x180007986  add     rsp, 2C0h
0x18000798d  pop     rdi
0x18000798e  pop     rsi
0x18000798f  pop     rbp
0x180007990  retn
```
