# GenerateSstpAttribute

- ea: `0x140018114`
- end: `0x140018167`
- name: `GenerateSstpAttribute`
- size: `83`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140018170`
- `0x1400182dc`
- `0x140018480`
- `0x14001855c`
- `0x1400185f8`

## callees

- `0x140005f40`
- `0x140018114`

## pseudocode

```c
char __fastcall GenerateSstpAttribute(
        char a1,
        const void *a2,
        unsigned __int16 a3,
        __int64 a4,
        unsigned __int16 a5,
        _WORD *a6)
{
  char v6; // r11
  __int16 v7; // bx

  v6 = 0;
  if ( a5 >= (unsigned __int64)a3 + 4 )
  {
    v7 = a3 + 4;
    *(_BYTE *)(a4 + 1) = a1;
    *(_BYTE *)a4 = 0;
    *(_WORD *)(a4 + 2) = __ROR2__(a3 + 4, 8);
    memmove((void *)(a4 + 4), a2, a3);
    v6 = 1;
    *a6 = v7;
  }
  return v6;
}

```

## disassembly

```asm
0x140018114  push    rbx
0x140018116  sub     rsp, 20h
0x14001811a  movzx   eax, [rsp+28h+arg_20]
0x14001811f  xor     r11b, r11b
0x140018122  movzx   ebx, r8w
0x140018126  mov     r8d, ebx; Size
0x140018129  lea     r10, [rbx+4]
0x14001812d  cmp     rax, r10
0x140018130  jb      short loc_14001815D
0x140018132  add     bx, 4
0x140018136  mov     [r9+1], cl
0x14001813a  movzx   eax, bx
0x14001813d  mov     [r9], r11b
0x140018140  ror     ax, 8
0x140018144  lea     rcx, [r9+4]; void *
0x140018148  mov     [r9+2], ax
0x14001814d  call    memmove
0x140018152  mov     rax, [rsp+28h+arg_28]
0x140018157  mov     r11b, 1
0x14001815a  mov     [rax], bx
0x14001815d  mov     al, r11b
0x140018160  add     rsp, 20h
0x140018164  pop     rbx
0x140018165  retn
```
