# ListView::GetSelectedItemIndex(int *)

- ea: `0x18001327c`
- end: `0x180013303`
- name: `?GetSelectedItemIndex@ListView@@QEBAJPEAH@Z`
- size: `135`
- prototype: `__int64 __fastcall(HWND *this, unsigned int *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d9a0`
- `0x18000dc0c`
- `0x18000e6b0`
- `0x18001330c`
- `0x180013458`
- `0x180016fa8`
- `0x180017260`

## callees

- `0x18001327c`

## import_xrefs

- `USER32!SendMessageW` at `0x1800132ab`
- `USER32!SendMessageW` at `0x1800132c4`
- `USER32!SendMessageW` at `0x1800132e4`
- `USER32!SendMessageW` at `0x1800132ab`
- `USER32!SendMessageW` at `0x1800132c4`
- `USER32!SendMessageW` at `0x1800132e4`

## pseudocode

```c
__int64 __fastcall ListView::GetSelectedItemIndex(HWND *this, unsigned int *a2)
{
  HWND v5; // rcx
  unsigned int v6; // ebx
  int v7; // ebp

  if ( !a2 )
    return 2147942487LL;
  v5 = *this;
  *a2 = -1;
  if ( (int)SendMessageW(v5, 0x1032u, 0, 0) >= 1 )
  {
    v6 = 0;
    v7 = SendMessageW(*this, 0x1004u, 0, 0);
    if ( v7 > 0 )
    {
      while ( (SendMessageW(*this, 0x102Cu, v6, 2) & 2) == 0 )
      {
        if ( (int)++v6 >= v7 )
          return 0;
      }
      *a2 = v6;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001327c  push    rbx
0x18001327e  push    rbp
0x18001327f  push    rsi
0x180013280  push    rdi
0x180013281  sub     rsp, 28h
0x180013285  mov     rdi, rdx
0x180013288  mov     rsi, rcx
0x18001328b  test    rdx, rdx
0x18001328e  jnz     short loc_180013297
0x180013290  mov     eax, 80070057h
0x180013295  jmp     short loc_1800132FA
0x180013297  mov     rcx, [rcx]; hWnd
0x18001329a  xor     r9d, r9d; lParam
0x18001329d  mov     dword ptr [rdx], 0FFFFFFFFh
0x1800132a3  xor     r8d, r8d; wParam
0x1800132a6  mov     edx, 1032h; Msg
0x1800132ab  call    cs:__imp_SendMessageW
0x1800132b1  cmp     eax, 1
0x1800132b4  jl      short loc_1800132F8
0x1800132b6  mov     rcx, [rsi]; hWnd
0x1800132b9  xor     r9d, r9d; lParam
0x1800132bc  xor     r8d, r8d; wParam
0x1800132bf  mov     edx, 1004h; Msg
0x1800132c4  call    cs:__imp_SendMessageW
0x1800132ca  xor     ebx, ebx
0x1800132cc  mov     rbp, rax
0x1800132cf  test    eax, eax
0x1800132d1  jle     short loc_1800132F8
0x1800132d3  mov     rcx, [rsi]; hWnd
0x1800132d6  mov     edx, 102Ch; Msg
0x1800132db  mov     r8d, ebx; wParam
0x1800132de  mov     r9d, 2; lParam
0x1800132e4  call    cs:__imp_SendMessageW
0x1800132ea  test    al, 2
0x1800132ec  jnz     short loc_1800132F6
0x1800132ee  inc     ebx
0x1800132f0  cmp     ebx, ebp
0x1800132f2  jl      short loc_1800132D3
0x1800132f4  jmp     short loc_1800132F8
0x1800132f6  mov     [rdi], ebx
0x1800132f8  xor     eax, eax
0x1800132fa  add     rsp, 28h
0x1800132fe  pop     rdi
0x1800132ff  pop     rsi
0x180013300  pop     rbp
0x180013301  pop     rbx
0x180013302  retn
```
