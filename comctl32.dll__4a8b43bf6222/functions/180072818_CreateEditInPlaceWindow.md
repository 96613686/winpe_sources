# CreateEditInPlaceWindow

- ea: `0x180072818`
- end: `0x1800728f5`
- name: `CreateEditInPlaceWindow`
- size: `221`
- prototype: `__int64 __usercall@<rax>(HWND hWndParent@<rcx>, LPCWSTR lpWindowName@<rdx>, WPARAM wParam)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18006864c`
- `0x1800736d4`

## callees

- `0x180072818`

## import_xrefs

- `USER32!GetWindowLongW` at `0x180072835`
- `USER32!GetWindowLongW` at `0x180072835`
- `USER32!SendMessageW` at `0x1800728b0`
- `USER32!SendMessageW` at `0x1800728c4`
- `USER32!SendMessageW` at `0x1800728dc`
- `USER32!SendMessageW` at `0x1800728b0`
- `USER32!SendMessageW` at `0x1800728c4`
- `USER32!SendMessageW` at `0x1800728dc`
- `USER32!CreateWindowExW` at `0x180072893`
- `USER32!CreateWindowExW` at `0x180072893`

## pseudocode

```c
HWND __fastcall CreateEditInPlaceWindow(HWND hWndParent, LPCWSTR lpWindowName, __int64 a3, DWORD a4, WPARAM wParam)
{
  __int16 WindowLongW; // ax
  HWND Window; // rax
  HWND v10; // rbx

  WindowLongW = GetWindowLongW(hWndParent, -20);
  Window = CreateWindowExW(WindowLongW & 0x2000, L"EDIT", lpWindowName, a4, 0, 0, 0x4000, 20, hWndParent, 0, g_hinst, 0);
  v10 = Window;
  if ( Window )
  {
    SendMessageW(Window, 0xC5u, 0x103u, 0);
    SendMessageW(v10, 0xB1u, 0, 0);
    SendMessageW(v10, 0x30u, wParam, 0);
  }
  return v10;
}

```

## disassembly

```asm
0x180072818  mov     [rsp+arg_0], rbx
0x18007281d  mov     [rsp+arg_8], rsi
0x180072822  push    rdi
0x180072823  sub     rsp, 60h
0x180072827  mov     rdi, rdx
0x18007282a  mov     esi, r9d
0x18007282d  mov     edx, 0FFFFFFECh; nIndex
0x180072832  mov     rbx, rcx
0x180072835  call    cs:__imp_GetWindowLongW
0x18007283b  mov     [rsp+68h+lpParam], 0; lpParam
0x180072844  lea     rdx, aEdit; "EDIT"
0x18007284b  mov     ecx, eax
0x18007284d  mov     r9d, esi; dwStyle
0x180072850  mov     rax, cs:g_hinst
0x180072857  and     ecx, 2000h; dwExStyle
0x18007285d  mov     [rsp+68h+hInstance], rax; hInstance
0x180072862  mov     r8, rdi; lpWindowName
0x180072865  mov     [rsp+68h+hMenu], 0; hMenu
0x18007286e  mov     [rsp+68h+hWndParent], rbx; hWndParent
0x180072873  mov     [rsp+68h+nHeight], 14h; nHeight
0x18007287b  mov     [rsp+68h+nWidth], 4000h; nWidth
0x180072883  mov     [rsp+68h+Y], 0; Y
0x18007288b  mov     [rsp+68h+X], 0; X
0x180072893  call    cs:__imp_CreateWindowExW
0x180072899  mov     rbx, rax
0x18007289c  test    rax, rax
0x18007289f  jz      short loc_1800728E2
0x1800728a1  mov     edx, 0C5h; Msg
0x1800728a6  xor     r9d, r9d; lParam
0x1800728a9  mov     rcx, rax; hWnd
0x1800728ac  lea     r8d, [rdx+3Eh]; wParam
0x1800728b0  call    cs:__imp_SendMessageW
0x1800728b6  xor     r9d, r9d; lParam
0x1800728b9  xor     r8d, r8d; wParam
0x1800728bc  mov     edx, 0B1h; Msg
0x1800728c1  mov     rcx, rbx; hWnd
0x1800728c4  call    cs:__imp_SendMessageW
0x1800728ca  mov     r8, [rsp+68h+wParam]; wParam
0x1800728d2  xor     r9d, r9d; lParam
0x1800728d5  mov     rcx, rbx; hWnd
0x1800728d8  lea     edx, [r9+30h]; Msg
0x1800728dc  call    cs:__imp_SendMessageW
0x1800728e2  mov     rsi, [rsp+68h+arg_8]
0x1800728e7  mov     rax, rbx
0x1800728ea  mov     rbx, [rsp+68h+arg_0]
0x1800728ef  add     rsp, 60h
0x1800728f3  pop     rdi
0x1800728f4  retn
```
