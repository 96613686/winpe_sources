# ListView::SetSelectedItemIndex(int)

- ea: `0x180013738`
- end: `0x1800137ba`
- name: `?SetSelectedItemIndex@ListView@@QEAAJH@Z`
- size: `130`
- prototype: `__int64 __fastcall(HWND *this, int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d338`
- `0x18000f074`
- `0x18000f9c0`
- `0x1800173f8`

## callees

- `0x180013738`
- `0x1800184ce`

## import_xrefs

- `USER32!SendMessageW` at `0x18001376e`
- `USER32!SendMessageW` at `0x1800137a1`
- `USER32!SendMessageW` at `0x18001376e`
- `USER32!SendMessageW` at `0x1800137a1`
- `USER32!SetFocus` at `0x18001375a`
- `USER32!SetFocus` at `0x18001375a`

## pseudocode

```c
__int64 __fastcall ListView::SetSelectedItemIndex(HWND *this, int a2)
{
  WPARAM v2; // rbx
  HWND v5; // rcx
  LPARAM lParam; // [rsp+20h] [rbp-68h] BYREF
  int v7; // [rsp+2Ch] [rbp-5Ch]
  int v8; // [rsp+30h] [rbp-58h]

  v2 = a2;
  if ( a2 == -1 )
    return 2147942487LL;
  SetFocus(*this);
  SendMessageW(*this, 0x1013u, v2, 0);
  memset_0(&lParam, 0, 0x58u);
  v5 = *this;
  v8 = 3;
  v7 = 3;
  SendMessageW(v5, 0x102Bu, v2, (LPARAM)&lParam);
  return 0;
}

```

## disassembly

```asm
0x180013738  mov     [rsp+arg_0], rbx
0x18001373d  push    rdi
0x18001373e  sub     rsp, 80h
0x180013745  movsxd  rbx, edx
0x180013748  mov     rdi, rcx
0x18001374b  cmp     ebx, 0FFFFFFFFh
0x18001374e  jnz     short loc_180013757
0x180013750  mov     eax, 80070057h
0x180013755  jmp     short loc_1800137A9
0x180013757  mov     rcx, [rcx]; hWnd
0x18001375a  call    cs:__imp_SetFocus
0x180013760  mov     rcx, [rdi]; hWnd
0x180013763  xor     r9d, r9d; lParam
0x180013766  mov     r8, rbx; wParam
0x180013769  mov     edx, 1013h; Msg
0x18001376e  call    cs:__imp_SendMessageW
0x180013774  xor     edx, edx; Val
0x180013776  lea     rcx, [rsp+88h+lParam]; void *
0x18001377b  lea     r8d, [rdx+58h]; Size
0x18001377f  call    memset_0
0x180013784  mov     rcx, [rdi]; hWnd
0x180013787  lea     r9, [rsp+88h+lParam]; lParam
0x18001378c  mov     eax, 3
0x180013791  mov     r8, rbx; wParam
0x180013794  mov     edx, 102Bh; Msg
0x180013799  mov     [rsp+88h+var_58], eax
0x18001379d  mov     [rsp+88h+var_5C], eax
0x1800137a1  call    cs:__imp_SendMessageW
0x1800137a7  xor     eax, eax
0x1800137a9  mov     rbx, [rsp+88h+arg_0]
0x1800137b1  add     rsp, 80h
0x1800137b8  pop     rdi
0x1800137b9  retn
```
