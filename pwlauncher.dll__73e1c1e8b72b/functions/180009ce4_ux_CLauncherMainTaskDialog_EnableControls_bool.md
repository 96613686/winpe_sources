# ux::CLauncherMainTaskDialog::EnableControls(bool)

- ea: `0x180009ce4`
- end: `0x180009d50`
- name: `?EnableControls@CLauncherMainTaskDialog@ux@@AEAAX_N@Z`
- size: `108`
- prototype: `void __fastcall(HWND *this, unsigned __int8)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180009a40`
- `0x18000a4e8`

## import_xrefs

- `USER32!SendMessageW` at `0x180009d09`
- `USER32!SendMessageW` at `0x180009d24`
- `USER32!SendMessageW` at `0x180009d09`
- `USER32!SendMessageW` at `0x180009d24`
- `USER32!SendMessageW` at `0x180009d49`

## pseudocode

```c
void __fastcall ux::CLauncherMainTaskDialog::EnableControls(HWND *this, unsigned __int8 a2)
{
  unsigned int v2; // ebx

  v2 = a2;
  SendMessageW(this[21], 0x470u, 0x67u, a2);
  SendMessageW(this[21], 0x470u, 0x66u, v2);
  SendMessageW(this[21], 0x46Fu, 0x65u, v2);
}

```

## disassembly

```asm
0x180009ce4  mov     [rsp+arg_0], rbx
0x180009ce9  push    rdi
0x180009cea  sub     rsp, 20h
0x180009cee  movzx   ebx, dl
0x180009cf1  mov     rdi, rcx
0x180009cf4  mov     rcx, [rcx+0A8h]; hWnd
0x180009cfb  mov     r9d, ebx; lParam
0x180009cfe  mov     edx, 470h; Msg
0x180009d03  mov     r8d, 67h ; 'g'; wParam
0x180009d09  call    cs:__imp_SendMessageW
0x180009d0f  mov     rcx, [rdi+0A8h]; hWnd
0x180009d16  mov     r9d, ebx; lParam
0x180009d19  mov     edx, 470h; Msg
0x180009d1e  mov     r8d, 66h ; 'f'; wParam
0x180009d24  call    cs:__imp_SendMessageW
0x180009d2a  mov     rcx, [rdi+0A8h]
0x180009d31  mov     r9d, ebx
0x180009d34  mov     edx, 46Fh
0x180009d39  mov     r8d, 65h ; 'e'
0x180009d3f  mov     rbx, [rsp+28h+arg_0]
0x180009d44  add     rsp, 20h
0x180009d48  pop     rdi
0x180009d49  jmp     cs:__imp_SendMessageW
```
