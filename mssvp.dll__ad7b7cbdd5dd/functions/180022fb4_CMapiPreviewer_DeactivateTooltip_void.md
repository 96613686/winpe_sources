# CMapiPreviewer::DeactivateTooltip(void)

- ea: `0x180022fb4`
- end: `0x180023000`
- name: `?DeactivateTooltip@CMapiPreviewer@@AEAAXXZ`
- size: `76`
- prototype: `void __fastcall(CMapiPreviewer *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180024320`
- `0x180025a90`
- `0x180025fd0`
- `0x1800272b0`

## callees

- `0x180022fb4`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180022ff4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180022ff4`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180022fd7`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180022fd7`

## pseudocode

```c
void __fastcall CMapiPreviewer::DeactivateTooltip(struct tagRECT *this)
{
  HWND v2; // rcx

  this[76].right = 0;
  *(_QWORD *)&this[76].left = 0;
  SetRectEmpty(this + 12);
  v2 = *(HWND *)&this[11].right;
  if ( v2 )
    SendMessageW(v2, 0x401u, 0, 0);
}

```

## disassembly

```asm
0x180022fb4  push    rbx
0x180022fb6  sub     rsp, 20h
0x180022fba  mov     dword ptr [rcx+4C8h], 0
0x180022fc4  xor     eax, eax
0x180022fc6  mov     [rcx+4C0h], rax
0x180022fcd  mov     rbx, rcx
0x180022fd0  add     rcx, 0C0h; lprc
0x180022fd7  call    cs:__imp_SetRectEmpty
0x180022fdd  mov     rcx, [rbx+0B8h]; hWnd
0x180022fe4  test    rcx, rcx
0x180022fe7  jz      short loc_180022FFA
0x180022fe9  xor     r9d, r9d; lParam
0x180022fec  xor     r8d, r8d; wParam
0x180022fef  mov     edx, 401h; Msg
0x180022ff4  call    cs:__imp_SendMessageW
0x180022ffa  add     rsp, 20h
0x180022ffe  pop     rbx
0x180022fff  retn
```
