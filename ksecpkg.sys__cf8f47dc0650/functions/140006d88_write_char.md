# write_char

- ea: `0x140006d88`
- end: `0x140006dd1`
- name: `write_char`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140006308`
- `0x140006dd8`

## callees

- `0x140006d88`
- `0x140006e30`

## pseudocode

```c
int __fastcall write_char(char a1, FILE *a2, _DWORD *a3)
{
  int result; // eax

  result = a2->_flag;
  if ( (result & 0x40) == 0 || a2->_base )
  {
    if ( --a2->_cnt < 0 )
    {
      result = flsbuf_s(a1, a2);
    }
    else
    {
      *a2->_ptr++ = a1;
      result = (unsigned __int8)a1;
    }
    if ( result == -1 )
      *a3 = -1;
    else
      ++*a3;
  }
  else
  {
    ++*a3;
  }
  return result;
}

```

## disassembly

```asm
0x140006d88  push    rbx
0x140006d8a  sub     rsp, 20h
0x140006d8e  mov     eax, [rdx+18h]
0x140006d91  mov     rbx, r8
0x140006d94  test    al, 40h
0x140006d96  jz      short loc_140006DA4
0x140006d98  cmp     qword ptr [rdx+10h], 0
0x140006d9d  jnz     short loc_140006DA4
0x140006d9f  inc     dword ptr [r8]
0x140006da2  jmp     short loc_140006DCA
0x140006da4  sub     dword ptr [rdx+8], 1
0x140006da8  js      short loc_140006DB7
0x140006daa  mov     rax, [rdx]
0x140006dad  mov     [rax], cl
0x140006daf  inc     qword ptr [rdx]
0x140006db2  movzx   eax, cl
0x140006db5  jmp     short loc_140006DBF
0x140006db7  movsx   ecx, cl; int
0x140006dba  call    _flsbuf_s
0x140006dbf  cmp     eax, 0FFFFFFFFh
0x140006dc2  jnz     short loc_140006DC8
0x140006dc4  mov     [rbx], eax
0x140006dc6  jmp     short loc_140006DCA
0x140006dc8  inc     dword ptr [rbx]
0x140006dca  add     rsp, 20h
0x140006dce  pop     rbx
0x140006dcf  retn
```
