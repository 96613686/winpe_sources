# ComboEx_GetEditBox

- ea: `0x180037db8`
- end: `0x180037ed0`
- name: `ComboEx_GetEditBox`
- size: `280`
- prototype: `__int64 __fastcall(DWORD_PTR dwRefData)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800371b0`
- `0x180037bdc`
- `0x180037fc0`
- `0x180038160`
- `0x1800393b0`
- `0x180039700`

## callees

- `0x180030800`
- `0x180037db8`

## import_xrefs

- `USER32!SendMessageW` at `0x180037ea0`
- `USER32!SendMessageW` at `0x180037eb9`
- `USER32!SendMessageW` at `0x180037ea0`
- `USER32!SendMessageW` at `0x180037eb9`
- `USER32!CreateWindowExW` at `0x180037e65`
- `USER32!CreateWindowExW` at `0x180037e65`
- `USER32!GetDlgCtrlID` at `0x180037df9`
- `USER32!GetDlgCtrlID` at `0x180037df9`

## pseudocode

```c
__int64 __fastcall ComboEx_GetEditBox(DWORD_PTR dwRefData)
{
  __int64 result; // rax
  int v3; // ebp
  DWORD v4; // edi
  int DlgCtrlID; // eax
  DWORD v6; // r9d
  HWND Window; // rax
  HWND v8; // rcx
  LRESULT v9; // rax

  result = *(_QWORD *)(dwRefData + 64);
  if ( !result )
  {
    v3 = *(_DWORD *)(dwRefData + 16);
    if ( (v3 & 3) != 2 )
      return 0;
    v4 = *(_DWORD *)(dwRefData + 32) & 0x7000;
    DlgCtrlID = GetDlgCtrlID(*(HWND *)dwRefData);
    v6 = (2 * (v3 & 0x40 | 0x2A000000)) | 0x400;
    if ( (v3 & 0x80) == 0 )
      v6 = 2 * (v3 & 0x40 | 0x2A000000);
    Window = CreateWindowExW(
               v4,
               L"EDIT",
               &c_szNULL,
               v6,
               0,
               0,
               0,
               0,
               *(HWND *)(dwRefData + 56),
               (HMENU)DlgCtrlID,
               g_hinst,
               0);
    *(_QWORD *)(dwRefData + 64) = Window;
    if ( Window && SetWindowSubclass(Window, EditSubclassProc, 0, dwRefData) )
    {
      v8 = *(HWND *)(dwRefData + 56);
      if ( v8 )
      {
        v9 = SendMessageW(v8, 0x31u, 0, 0);
        if ( v9 )
          SendMessageW(*(HWND *)(dwRefData + 64), 0x30u, v9, 0);
      }
      return *(_QWORD *)(dwRefData + 64);
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180037db8  push    rbx
0x180037dba  push    rbp
0x180037dbb  push    rsi
0x180037dbc  push    rdi
0x180037dbd  sub     rsp, 68h
0x180037dc1  mov     rax, [rcx+40h]
0x180037dc5  mov     rsi, rcx
0x180037dc8  test    rax, rax
0x180037dcb  jnz     loc_180037EC7
0x180037dd1  mov     ebp, [rcx+10h]
0x180037dd4  mov     eax, ebp
0x180037dd6  and     al, 3
0x180037dd8  cmp     al, 2
0x180037dda  jnz     loc_180037EC5
0x180037de0  mov     edi, [rcx+20h]
0x180037de3  mov     ebx, ebp
0x180037de5  mov     rcx, [rcx]; hWnd
0x180037de8  and     ebx, 40h
0x180037deb  or      ebx, 2A000000h
0x180037df1  and     edi, 7000h
0x180037df7  add     ebx, ebx
0x180037df9  call    cs:__imp_GetDlgCtrlID
0x180037dff  mov     [rsp+88h+lpParam], 0; lpParam
0x180037e08  lea     r8, c_szNULL; lpWindowName
0x180037e0f  movsxd  rdx, eax
0x180037e12  mov     r9d, ebx
0x180037e15  mov     rax, cs:g_hinst
0x180037e1c  bts     r9d, 0Ah
0x180037e21  mov     [rsp+88h+hInstance], rax; hInstance
0x180037e26  and     bpl, 80h
0x180037e2a  mov     rax, [rsi+38h]
0x180037e2e  mov     ecx, edi; dwExStyle
0x180037e30  mov     [rsp+88h+hMenu], rdx; hMenu
0x180037e35  cmovz   r9d, ebx; dwStyle
0x180037e39  mov     [rsp+88h+hWndParent], rax; hWndParent
0x180037e3e  lea     rdx, c_szEdit; "EDIT"
0x180037e45  mov     [rsp+88h+nHeight], 0; nHeight
0x180037e4d  mov     [rsp+88h+nWidth], 0; nWidth
0x180037e55  mov     [rsp+88h+Y], 0; Y
0x180037e5d  mov     [rsp+88h+X], 0; X
0x180037e65  call    cs:__imp_CreateWindowExW
0x180037e6b  mov     [rsi+40h], rax
0x180037e6f  test    rax, rax
0x180037e72  jz      short loc_180037EC5
0x180037e74  mov     r9, rsi; dwRefData
0x180037e77  lea     rdx, EditSubclassProc; pfnSubclass
0x180037e7e  xor     r8d, r8d; uIdSubclass
0x180037e81  mov     rcx, rax; hWnd
0x180037e84  call    SetWindowSubclass
0x180037e89  test    eax, eax
0x180037e8b  jz      short loc_180037EC5
0x180037e8d  mov     rcx, [rsi+38h]; hWnd
0x180037e91  test    rcx, rcx
0x180037e94  jz      short loc_180037EBF
0x180037e96  xor     r9d, r9d; lParam
0x180037e99  xor     r8d, r8d; wParam
0x180037e9c  lea     edx, [r9+31h]; Msg
0x180037ea0  call    cs:__imp_SendMessageW
0x180037ea6  test    rax, rax
0x180037ea9  jz      short loc_180037EBF
0x180037eab  mov     rcx, [rsi+40h]; hWnd
0x180037eaf  xor     r9d, r9d; lParam
0x180037eb2  mov     r8, rax; wParam
0x180037eb5  lea     edx, [r9+30h]; Msg
0x180037eb9  call    cs:__imp_SendMessageW
0x180037ebf  mov     rax, [rsi+40h]
0x180037ec3  jmp     short loc_180037EC7
0x180037ec5  xor     eax, eax
0x180037ec7  add     rsp, 68h
0x180037ecb  pop     rdi
0x180037ecc  pop     rsi
0x180037ecd  pop     rbp
0x180037ece  pop     rbx
0x180037ecf  retn
```
