# BuildAvpAch

- ea: `0x140016084`
- end: `0x1400160ef`
- name: `BuildAvpAch`
- size: `107`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140016440`
- `0x140016ae0`
- `0x140016b60`
- `0x140016d00`

## callees

- `0x140004900`
- `0x140016084`

## pseudocode

```c
__int64 __fastcall BuildAvpAch(
        __int16 a1,
        __int16 a2,
        char a3,
        const void *a4,
        unsigned __int16 a5,
        unsigned __int16 *a6)
{
  __int16 v7; // di
  unsigned __int16 v8; // di
  __int16 v9; // ax

  a6[1] = __ROR2__(a2, 8);
  v7 = (_WORD)a6 + 6;
  a6[2] = __ROR2__(a1, 8);
  if ( a5 )
  {
    memmove(a6 + 3, a4, a5);
    v7 += a5;
  }
  v8 = v7 - (_WORD)a6;
  *a6 = v8;
  v9 = v8;
  if ( a3 )
  {
    v9 = v8 | 0x8000;
    *a6 = v8 | 0x8000;
  }
  *a6 = __ROR2__(v9, 8);
  return v8;
}

```

## disassembly

```asm
0x140016084  push    rbx
0x140016086  push    rbp
0x140016087  push    rsi
0x140016088  push    rdi
0x140016089  sub     rsp, 28h
0x14001608d  mov     rsi, [rsp+48h+arg_28]
0x140016092  mov     bpl, r8b
0x140016095  movzx   eax, [rsp+48h+arg_20]
0x14001609a  ror     dx, 8
0x14001609e  ror     cx, 8
0x1400160a2  mov     [rsi+2], dx
0x1400160a6  lea     rdi, [rsi+6]
0x1400160aa  mov     [rsi+4], cx
0x1400160ae  test    ax, ax
0x1400160b1  jz      short loc_1400160C6
0x1400160b3  mov     r8d, eax; Size
0x1400160b6  mov     rdx, r9; Src
0x1400160b9  mov     rcx, rdi; void *
0x1400160bc  mov     ebx, eax
0x1400160be  call    memmove
0x1400160c3  add     rdi, rbx
0x1400160c6  sub     di, si
0x1400160c9  mov     [rsi], di
0x1400160cc  movzx   eax, di
0x1400160cf  test    bpl, bpl
0x1400160d2  jz      short loc_1400160DB
0x1400160d4  or      ax, 8000h
0x1400160d8  mov     [rsi], ax
0x1400160db  ror     ax, 8
0x1400160df  mov     [rsi], ax
0x1400160e2  movzx   eax, di
0x1400160e5  add     rsp, 28h
0x1400160e9  pop     rdi
0x1400160ea  pop     rsi
0x1400160eb  pop     rbp
0x1400160ec  pop     rbx
0x1400160ed  retn
```
