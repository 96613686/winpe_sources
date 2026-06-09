# ODBCSendDlgItemMessage

- ea: `0x180013ec4`
- end: `0x180013ef8`
- name: `ODBCSendDlgItemMessage`
- size: `52`
- prototype: `LRESULT __fastcall(HWND, int, UINT, WPARAM, LPARAM)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180003570`
- `0x180004260`
- `0x180004718`
- `0x180004800`
- `0x180005c00`
- `0x18000b9c0`
- `0x18000c440`

## import_xrefs

- `USER32!SendMessageW` at `0x180013ef1`
- `USER32!GetDlgItem` at `0x180013ed4`
- `USER32!GetDlgItem` at `0x180013ed4`

## pseudocode

```c
LRESULT __fastcall ODBCSendDlgItemMessage(HWND a1, int a2, UINT a3, WPARAM a4, LPARAM a5)
{
  HWND DlgItem; // rax

  DlgItem = GetDlgItem(a1, a2);
  return SendMessageW(DlgItem, a3, a4, a5);
}

```

## disassembly

```asm
0x180013ec4  mov     [rsp+arg_0], rbx
0x180013ec9  push    rdi
0x180013eca  sub     rsp, 20h
0x180013ece  mov     rbx, r9
0x180013ed1  mov     edi, r8d
0x180013ed4  call    cs:__imp_GetDlgItem
0x180013eda  mov     r9, [rsp+28h+arg_20]
0x180013edf  mov     r8, rbx
0x180013ee2  mov     rcx, rax
0x180013ee5  mov     edx, edi
0x180013ee7  mov     rbx, [rsp+28h+arg_0]
0x180013eec  add     rsp, 20h
0x180013ef0  pop     rdi
0x180013ef1  jmp     cs:__imp_SendMessageW
```
