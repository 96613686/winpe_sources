# BuildL2tpHeader

- ea: `0x14001c620`
- end: `0x14001c6c3`
- name: `BuildL2tpHeader`
- size: `163`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000fd0c`
- `0x1400175f0`
- `0x140017fa0`

## callees

- `0x14001c620`

## pseudocode

```c
__int64 __fastcall BuildL2tpHeader(_WORD *a1, char a2, char a3, _WORD *a4, _WORD *a5, _WORD *a6, __int16 a7)
{
  _WORD *v7; // rax
  __int64 result; // rax

  *a1 = 16386;
  v7 = a1 + 2;
  if ( a2 )
  {
    *a1 = -16382;
  }
  else if ( a3 )
  {
    *a1 = 24578;
  }
  if ( a4 )
  {
    *v7 = __ROR2__(*a4, 8);
    v7 = a1 + 3;
  }
  if ( a5 )
    *v7++ = __ROR2__(*a5, 8);
  if ( a6 )
  {
    *a1 |= 0x800u;
    *v7 = __ROR2__(*a6, 8);
    v7[1] = __ROR2__(a7, 8);
    LOWORD(v7) = (_WORD)v7 + 4;
  }
  *a1 = __ROR2__(*a1, 8);
  result = (unsigned __int16)((_WORD)v7 - (_WORD)a1);
  a1[1] = __ROR2__(result, 8);
  return result;
}

```

## disassembly

```asm
0x14001c620  mov     word ptr [rcx], 4002h
0x14001c625  mov     r10, rcx
0x14001c628  lea     rax, [rcx+4]
0x14001c62c  test    dl, dl
0x14001c62e  jnz     short loc_14001C68C
0x14001c630  test    r8b, r8b
0x14001c633  jnz     short loc_14001C693
0x14001c635  test    r9, r9
0x14001c638  jz      short loc_14001C649
0x14001c63a  movzx   ecx, word ptr [r9]
0x14001c63e  ror     cx, 8
0x14001c642  mov     [rax], cx
0x14001c645  add     rax, 2
0x14001c649  mov     rcx, [rsp+arg_20]
0x14001c64e  test    rcx, rcx
0x14001c651  jz      short loc_14001C661
0x14001c653  movzx   ecx, word ptr [rcx]
0x14001c656  ror     cx, 8
0x14001c65a  mov     [rax], cx
0x14001c65d  add     rax, 2
0x14001c661  mov     rcx, [rsp+arg_28]
0x14001c666  test    rcx, rcx
0x14001c669  jnz     short loc_14001C69A
0x14001c66b  movzx   ecx, word ptr [r10]
0x14001c66f  sub     ax, r10w
0x14001c673  ror     cx, 8
0x14001c677  mov     [r10], cx
0x14001c67b  movzx   eax, ax
0x14001c67e  movzx   ecx, ax
0x14001c681  ror     cx, 8
0x14001c685  mov     [r10+2], cx
0x14001c68a  retn
0x14001c68c  mov     word ptr [rcx], 0C002h
0x14001c691  jmp     short loc_14001C635
0x14001c693  mov     word ptr [rcx], 6002h
0x14001c698  jmp     short loc_14001C635
0x14001c69a  mov     edx, 800h
0x14001c69f  or      [r10], dx
0x14001c6a3  movzx   ecx, word ptr [rcx]
0x14001c6a6  ror     cx, 8
0x14001c6aa  mov     [rax], cx
0x14001c6ad  lea     rcx, [rax+2]
0x14001c6b1  movzx   eax, [rsp+arg_30]
0x14001c6b6  ror     ax, 8
0x14001c6ba  mov     [rcx], ax
0x14001c6bd  lea     rax, [rcx+2]
0x14001c6c1  jmp     short loc_14001C66B
```
