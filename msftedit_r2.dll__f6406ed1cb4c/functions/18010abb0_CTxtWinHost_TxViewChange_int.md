# CTxtWinHost::TxViewChange(int)

- ea: `0x18010abb0`
- end: `0x18010ac04`
- name: `?TxViewChange@CTxtWinHost@@UEAAXH@Z`
- size: `84`
- prototype: `void __fastcall(CTxtWinHost *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18010abb0`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetParent` at `0x18010abe7`
- `ext-ms-win-ntuser-window-l1-1-0!GetParent` at `0x18010abe7`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x18010abd0`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x18010abf6`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x18010abd0`
- `ext-ms-win-ntuser-draw-l1-1-0!UpdateWindow` at `0x18010abf6`

## pseudocode

```c
void __fastcall CTxtWinHost::TxViewChange(HWND *this, int a2)
{
  HWND Parent; // rax

  if ( (*((_DWORD *)this + 23) & 0x200) != 0 && a2 )
  {
    if ( ((_BYTE)this[11] & 0x20) != 0 )
    {
      Parent = GetParent(this[4]);
      UpdateWindow(Parent);
    }
    UpdateWindow(this[4]);
  }
}

```

## disassembly

```asm
0x18010abb0  push    rbx
0x18010abb2  sub     rsp, 20h
0x18010abb6  test    dword ptr [rcx+5Ch], 200h
0x18010abbd  mov     rbx, rcx
0x18010abc0  jz      short loc_18010ABDC
0x18010abc2  test    edx, edx
0x18010abc4  jz      short loc_18010ABDC
0x18010abc6  test    byte ptr [rcx+58h], 20h
0x18010abca  jnz     short loc_18010ABE3
0x18010abcc  mov     rcx, [rbx+20h]; hWnd
0x18010abd0  call    cs:__imp_UpdateWindow
0x18010abd7  nop     dword ptr [rax+rax+00h]
0x18010abdc  add     rsp, 20h
0x18010abe0  pop     rbx
0x18010abe1  retn
0x18010abe3  mov     rcx, [rcx+20h]; hWnd
0x18010abe7  call    cs:__imp_GetParent
0x18010abee  nop     dword ptr [rax+rax+00h]
0x18010abf3  mov     rcx, rax; hWnd
0x18010abf6  call    cs:__imp_UpdateWindow
0x18010abfd  nop     dword ptr [rax+rax+00h]
0x18010ac02  jmp     short loc_18010ABCC
```
