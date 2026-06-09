# CreateUpDownControl

- ea: `0x18002d220`
- end: `0x18002d2ed`
- name: `CreateUpDownControl`
- size: `205`
- prototype: `HWND __stdcall(DWORD dwStyle, int x, int y, int cx, int cy, HWND hParent, int nID, HINSTANCE hInst, HWND hBuddy, int nUpper, int nLower, int nPos)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180044574`
- `0x180066a3c`

## callees

- `0x18002d220`

## import_xrefs

- `USER32!SendMessageW` at `0x18002d29b`
- `USER32!SendMessageW` at `0x18002d2c4`
- `USER32!SendMessageW` at `0x18002d2de`
- `USER32!SendMessageW` at `0x18002d29b`
- `USER32!SendMessageW` at `0x18002d2c4`
- `USER32!SendMessageW` at `0x18002d2de`
- `USER32!CreateWindowExW` at `0x18002d27a`
- `USER32!CreateWindowExW` at `0x18002d27a`

## pseudocode

```c
HWND __stdcall CreateUpDownControl(
        DWORD dwStyle,
        int x,
        int y,
        int cx,
        int cy,
        HWND hParent,
        int nID,
        HINSTANCE hInst,
        HWND hBuddy,
        int nUpper,
        int nLower,
        int nPos)
{
  HWND Window; // rax
  HWND v13; // rbx

  Window = CreateWindowExW(0, L"msctls_updown32", 0, dwStyle, x, y, cx, cy, hParent, (HMENU)nID, hInst, 0);
  v13 = Window;
  if ( Window )
  {
    SendMessageW(Window, 0x469u, (WPARAM)hBuddy, 0);
    SendMessageW(v13, 0x465u, 0, (unsigned __int16)nUpper | ((unsigned __int16)nLower << 16));
    SendMessageW(v13, 0x467u, 0, (unsigned __int16)nPos);
  }
  return v13;
}

```

## disassembly

```asm
0x18002d220  mov     r11, rsp
0x18002d223  push    rbx
0x18002d224  sub     rsp, 60h
0x18002d228  mov     rax, [rsp+68h+hInst]
0x18002d230  movsxd  r10, [rsp+68h+nID]
0x18002d238  mov     qword ptr [r11-10h], 0
0x18002d240  mov     [r11-18h], rax
0x18002d244  mov     rax, [rsp+68h+hParent]
0x18002d24c  mov     [r11-20h], r10
0x18002d250  mov     [r11-28h], rax
0x18002d254  mov     eax, [rsp+68h+cy]
0x18002d25b  mov     [rsp+68h+nHeight], eax; nHeight
0x18002d25f  mov     [r11-38h], r9d
0x18002d263  mov     r9d, ecx; dwStyle
0x18002d266  mov     [r11-40h], r8d
0x18002d26a  xor     ecx, ecx; dwExStyle
0x18002d26c  mov     [rsp+68h+X], edx; X
0x18002d270  xor     r8d, r8d; lpWindowName
0x18002d273  lea     rdx, s_szUpdownClass; "msctls_updown32"
0x18002d27a  call    cs:__imp_CreateWindowExW
0x18002d280  mov     rbx, rax
0x18002d283  test    rax, rax
0x18002d286  jz      short loc_18002D2E4
0x18002d288  mov     r8, [rsp+68h+hBuddy]; wParam
0x18002d290  xor     r9d, r9d; lParam
0x18002d293  mov     edx, 469h; Msg
0x18002d298  mov     rcx, rax; hWnd
0x18002d29b  call    cs:__imp_SendMessageW
0x18002d2a1  movzx   edx, word ptr [rsp+68h+nLower]
0x18002d2a9  xor     r8d, r8d; wParam
0x18002d2ac  movzx   ecx, word ptr [rsp+68h+nUpper]
0x18002d2b4  shl     edx, 10h
0x18002d2b7  or      edx, ecx
0x18002d2b9  mov     rcx, rbx; hWnd
0x18002d2bc  movsxd  r9, edx; lParam
0x18002d2bf  mov     edx, 465h; Msg
0x18002d2c4  call    cs:__imp_SendMessageW
0x18002d2ca  movzx   r9d, word ptr [rsp+68h+nPos]; lParam
0x18002d2d3  xor     r8d, r8d; wParam
0x18002d2d6  mov     edx, 467h; Msg
0x18002d2db  mov     rcx, rbx; hWnd
0x18002d2de  call    cs:__imp_SendMessageW
0x18002d2e4  mov     rax, rbx
0x18002d2e7  add     rsp, 60h
0x18002d2eb  pop     rbx
0x18002d2ec  retn
```
