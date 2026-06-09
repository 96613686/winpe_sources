# ComboEx_OnCreate

- ea: `0x180038160`
- end: `0x1800382c8`
- name: `ComboEx_OnCreate`
- size: `360`
- prototype: `__int64 __fastcall(HWND hWndParent)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800371b0`

## callees

- `0x1800184b8`
- `0x180030800`
- `0x180037db8`
- `0x180038160`
- `0x1800382d0`
- `0x180038c54`
- `0x180038ed4`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x18003817d`
- `KERNEL32!LocalAlloc` at `0x18003817d`
- `USER32!SetWindowLongW` at `0x1800381b0`
- `USER32!SetWindowLongW` at `0x1800381b0`
- `USER32!SetWindowLongPtrW` at `0x180038197`
- `USER32!SetWindowLongPtrW` at `0x180038197`
- `USER32!CreateWindowExW` at `0x180038241`
- `USER32!CreateWindowExW` at `0x180038241`

## string_xrefs

- `0x1800381f3`: `combobox`

## pseudocode

```c
__int64 __fastcall ComboEx_OnCreate(HWND hWndParent, __int64 a2)
{
  HLOCAL v4; // rax
  DWORD_PTR v5; // rbx
  int v6; // r9d
  DWORD v7; // r9d
  HWND Window; // rax

  v4 = LocalAlloc(0x40u, 0x98u);
  v5 = (DWORD_PTR)v4;
  if ( v4 )
  {
    SetWindowLongPtrW(hWndParent, 0, (LONG_PTR)v4);
    *(_DWORD *)(a2 + 48) &= 0xFF4F9FFF;
    SetWindowLongW(hWndParent, -16, *(_DWORD *)(a2 + 48));
    CIInitialize(v5, hWndParent, a2);
    v6 = *(_DWORD *)(a2 + 48);
    if ( (v6 & 3) == 1 )
      v7 = *(_DWORD *)(a2 + 48) & 0x40000202 | 0x16200411 | v6 & 0x60C0;
    else
      v7 = *(_DWORD *)(a2 + 48) & 0x40000202 | 0x16200411;
    Window = CreateWindowExW(
               *(_DWORD *)(a2 + 72) & 0x7000,
               L"combobox",
               *(LPCWSTR *)(a2 + 56),
               v7,
               0,
               0,
               *(_DWORD *)(a2 + 36),
               *(_DWORD *)(a2 + 32),
               hWndParent,
               *(HMENU *)(a2 + 16),
               *(HINSTANCE *)(a2 + 8),
               0);
    *(_QWORD *)(v5 + 56) = Window;
    if ( Window
      && SetWindowSubclass(Window, ComboSubclassProc, 0, v5)
      && (ComboEx_GetEditBox(v5) || (*(_DWORD *)(v5 + 16) & 3) != 2) )
    {
      ComboEx_OnSetFont(v5, 0, 0);
      *(_DWORD *)(v5 + 96) = 10;
      *(_QWORD *)(v5 + 104) = -1;
      ComboEx_OnWindowPosChanging(v5, 0);
      return 1;
    }
    ComboEx_OnDestroy(v5);
  }
  return 0;
}

```

## disassembly

```asm
0x180038160  mov     [rsp+arg_0], rbx
0x180038165  mov     [rsp+arg_8], rsi
0x18003816a  push    rdi
0x18003816b  sub     rsp, 60h
0x18003816f  mov     rdi, rdx
0x180038172  mov     rsi, rcx
0x180038175  mov     edx, 98h; uBytes
0x18003817a  lea     ecx, [rdx-58h]; uFlags
0x18003817d  call    cs:__imp_LocalAlloc
0x180038183  mov     rbx, rax
0x180038186  test    rax, rax
0x180038189  jz      loc_1800382B6
0x18003818f  mov     r8, rax; dwNewLong
0x180038192  xor     edx, edx; nIndex
0x180038194  mov     rcx, rsi; hWnd
0x180038197  call    cs:__imp_SetWindowLongPtrW
0x18003819d  and     dword ptr [rdi+30h], 0FF4F9FFFh
0x1800381a4  mov     edx, 0FFFFFFF0h; nIndex
0x1800381a9  mov     r8d, [rdi+30h]; dwNewLong
0x1800381ad  mov     rcx, rsi; hWnd
0x1800381b0  call    cs:__imp_SetWindowLongW
0x1800381b6  mov     r8, rdi
0x1800381b9  mov     rdx, rsi
0x1800381bc  mov     rcx, rbx
0x1800381bf  call    CIInitialize
0x1800381c4  mov     r9d, [rdi+30h]
0x1800381c8  mov     ecx, r9d
0x1800381cb  and     ecx, 40000202h
0x1800381d1  mov     eax, r9d
0x1800381d4  or      ecx, 16200411h
0x1800381da  and     al, 3
0x1800381dc  cmp     al, 1
0x1800381de  jnz     short loc_1800381EC
0x1800381e0  and     r9d, 60C0h
0x1800381e7  or      r9d, ecx
0x1800381ea  jmp     short loc_1800381EF
0x1800381ec  mov     r9d, ecx; dwStyle
0x1800381ef  mov     rax, [rdi+8]
0x1800381f3  lea     rdx, c_szComboBox; "combobox"
0x1800381fa  mov     ecx, [rdi+48h]
0x1800381fd  mov     r8, [rdi+38h]; lpWindowName
0x180038201  and     ecx, 7000h; dwExStyle
0x180038207  mov     [rsp+68h+lpParam], 0; lpParam
0x180038210  mov     [rsp+68h+hInstance], rax; hInstance
0x180038215  mov     rax, [rdi+10h]
0x180038219  mov     [rsp+68h+hMenu], rax; hMenu
0x18003821e  mov     eax, [rdi+20h]
0x180038221  mov     [rsp+68h+hWndParent], rsi; hWndParent
0x180038226  mov     [rsp+68h+nHeight], eax; nHeight
0x18003822a  mov     eax, [rdi+24h]
0x18003822d  mov     [rsp+68h+nWidth], eax; nWidth
0x180038231  mov     [rsp+68h+Y], 0; Y
0x180038239  mov     [rsp+68h+X], 0; X
0x180038241  call    cs:__imp_CreateWindowExW
0x180038247  mov     [rbx+38h], rax
0x18003824b  test    rax, rax
0x18003824e  jz      short loc_1800382AE
0x180038250  mov     r9, rbx; dwRefData
0x180038253  lea     rdx, ComboSubclassProc; pfnSubclass
0x18003825a  xor     r8d, r8d; uIdSubclass
0x18003825d  mov     rcx, rax; hWnd
0x180038260  call    SetWindowSubclass
0x180038265  test    eax, eax
0x180038267  jz      short loc_1800382AE
0x180038269  mov     rcx, rbx; dwRefData
0x18003826c  call    ComboEx_GetEditBox
0x180038271  test    rax, rax
0x180038274  jnz     short loc_180038281
0x180038276  mov     ecx, [rbx+10h]
0x180038279  and     cl, 3
0x18003827c  cmp     cl, 2
0x18003827f  jz      short loc_1800382AE
0x180038281  xor     r8d, r8d
0x180038284  xor     edx, edx
0x180038286  mov     rcx, rbx
0x180038289  call    ComboEx_OnSetFont
0x18003828e  xor     edx, edx
0x180038290  mov     dword ptr [rbx+60h], 0Ah
0x180038297  mov     rcx, rbx
0x18003829a  mov     qword ptr [rbx+68h], 0FFFFFFFFFFFFFFFFh
0x1800382a2  call    ComboEx_OnWindowPosChanging
0x1800382a7  mov     eax, 1
0x1800382ac  jmp     short loc_1800382B8
0x1800382ae  mov     rcx, rbx
0x1800382b1  call    ComboEx_OnDestroy
0x1800382b6  xor     eax, eax
0x1800382b8  mov     rbx, [rsp+68h+arg_0]
0x1800382bd  mov     rsi, [rsp+68h+arg_8]
0x1800382c2  add     rsp, 60h
0x1800382c6  pop     rdi
0x1800382c7  retn
```
