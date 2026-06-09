# ListView_CreateHeader

- ea: `0x180077698`
- end: `0x18007777b`
- name: `ListView_CreateHeader`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180078060`
- `0x180079ae0`

## callees

- `0x180077698`

## import_xrefs

- `USER32!SendMessageW` at `0x180077743`
- `USER32!SendMessageW` at `0x180077764`
- `USER32!SendMessageW` at `0x180077743`
- `USER32!SendMessageW` at `0x180077764`
- `USER32!CreateWindowExW` at `0x180077723`
- `USER32!CreateWindowExW` at `0x180077723`
- `USER32!GetWindowLongPtrW` at `0x1800776c1`
- `USER32!GetWindowLongPtrW` at `0x1800776c1`

## pseudocode

```c
__int64 __fastcall ListView_CreateHeader(__int64 a1)
{
  unsigned int v1; // edi
  HWND hWndParent; // rbx
  HINSTANCE hInstance; // rax
  int v5; // r9d
  HWND Window; // rax
  LPARAM v7; // r9

  v1 = *(_DWORD *)(a1 + 16);
  hWndParent = *(HWND *)a1;
  hInstance = (HINSTANCE)GetWindowLongPtrW(*(HWND *)a1, -6);
  v5 = (v1 >> 11) & 8 | 0x40000042;
  if ( (v1 & 0x8000) != 0 )
    v5 = (v1 >> 11) & 8 | 0x40000040;
  Window = CreateWindowExW(0, L"SysHeader32", 0, v5 | 0x80u, 0, 0, 0, 0, hWndParent, 0, hInstance, 0);
  *(_QWORD *)(a1 + 440) = Window;
  if ( Window )
  {
    SendMessageW(Window, 0x30u, *(_QWORD *)(a1 + 88), 0);
    v7 = *(_QWORD *)(a1 + 232);
    if ( v7 )
      SendMessageW(*(HWND *)(a1 + 440), 0x1208u, 0, v7);
  }
  return *(_QWORD *)(a1 + 440);
}

```

## disassembly

```asm
0x180077698  push    rbx
0x18007769a  push    rsi
0x18007769b  push    rdi
0x18007769c  push    r14
0x18007769e  sub     rsp, 68h
0x1800776a2  mov     edi, [rcx+10h]
0x1800776a5  mov     r14, rcx
0x1800776a8  mov     rbx, [rcx]
0x1800776ab  mov     esi, edi
0x1800776ad  shr     esi, 0Bh
0x1800776b0  mov     edx, 0FFFFFFFAh; nIndex
0x1800776b5  and     esi, 8
0x1800776b8  mov     rcx, rbx; hWnd
0x1800776bb  or      esi, 40000040h
0x1800776c1  call    cs:__imp_GetWindowLongPtrW
0x1800776c7  mov     [rsp+88h+lpParam], 0; lpParam
0x1800776d0  lea     rdx, c_szHeaderClass; "SysHeader32"
0x1800776d7  mov     [rsp+88h+hInstance], rax; hInstance
0x1800776dc  mov     r9d, esi
0x1800776df  mov     [rsp+88h+hMenu], 0; hMenu
0x1800776e8  or      r9d, 2
0x1800776ec  mov     [rsp+88h+hWndParent], rbx; hWndParent
0x1800776f1  bt      edi, 0Fh
0x1800776f5  mov     [rsp+88h+nHeight], 0; nHeight
0x1800776fd  cmovb   r9d, esi
0x180077701  mov     [rsp+88h+nWidth], 0; nWidth
0x180077709  bts     r9d, 7; dwStyle
0x18007770e  mov     [rsp+88h+Y], 0; Y
0x180077716  xor     r8d, r8d; lpWindowName
0x180077719  mov     [rsp+88h+X], 0; X
0x180077721  xor     ecx, ecx; dwExStyle
0x180077723  call    cs:__imp_CreateWindowExW
0x180077729  mov     [r14+1B8h], rax
0x180077730  test    rax, rax
0x180077733  jz      short loc_18007776A
0x180077735  mov     r8, [r14+58h]; wParam
0x180077739  xor     r9d, r9d; lParam
0x18007773c  mov     rcx, rax; hWnd
0x18007773f  lea     edx, [r9+30h]; Msg
0x180077743  call    cs:__imp_SendMessageW
0x180077749  mov     r9, [r14+0E8h]; lParam
0x180077750  test    r9, r9
0x180077753  jz      short loc_18007776A
0x180077755  mov     rcx, [r14+1B8h]; hWnd
0x18007775c  xor     r8d, r8d; wParam
0x18007775f  mov     edx, 1208h; Msg
0x180077764  call    cs:__imp_SendMessageW
0x18007776a  mov     rax, [r14+1B8h]
0x180077771  add     rsp, 68h
0x180077775  pop     r14
0x180077777  pop     rdi
0x180077778  pop     rsi
0x180077779  pop     rbx
0x18007777a  retn
```
