# _BEREncOidNode

- ea: `0x1800076e0`
- end: `0x1800077a1`
- name: `_BEREncOidNode`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800074e0`
- `0x1800075e0`

## callees

- `0x1800076e0`

## pseudocode

```c
_BYTE *__fastcall BEREncOidNode(_BYTE *a1, unsigned int a2)
{
  _BYTE *result; // rax
  char v3; // r10
  char v4; // r8
  char v5; // r9
  char v6; // di

  result = a1 + 1;
  if ( a2 >= 0x80 )
  {
    v3 = a2 & 0x7F;
    v4 = (a2 >> 7) | 0x80;
    if ( a2 >= 0x4000 )
    {
      v5 = (a2 >> 14) | 0x80;
      if ( a2 >= 0x200000 )
      {
        v6 = (a2 >> 21) | 0x80;
        if ( a2 >= 0x10000000 )
        {
          *a1 = (a2 >> 28) | 0x80;
          *result = v6;
          a1[2] = v5;
          a1[3] = v4;
          a1[4] = v3;
          return a1 + 5;
        }
        else
        {
          *a1 = v6;
          *result = v5;
          a1[2] = v4;
          a1[3] = v3;
          return a1 + 4;
        }
      }
      else
      {
        *a1 = v5;
        *result = v4;
        a1[2] = v3;
        return a1 + 3;
      }
    }
    else
    {
      *a1 = v4;
      *result = v3;
      return a1 + 2;
    }
  }
  else
  {
    *a1 = a2;
  }
  return result;
}

```

## disassembly

```asm
0x1800076e0  sub     rsp, 8
0x1800076e4  lea     rax, [rcx+1]
0x1800076e8  cmp     edx, 80h
0x1800076ee  jnb     short loc_1800076F7
0x1800076f0  mov     [rcx], dl
0x1800076f2  add     rsp, 8
0x1800076f6  retn
0x1800076f7  mov     r8d, edx
0x1800076fa  movzx   r10d, dl
0x1800076fe  shr     r8d, 7
0x180007702  and     r10b, 7Fh
0x180007706  or      r8b, 80h
0x18000770a  cmp     edx, 4000h
0x180007710  jnb     short loc_180007720
0x180007712  mov     [rcx], r8b
0x180007715  mov     [rax], r10b
0x180007718  inc     rax
0x18000771b  add     rsp, 8
0x18000771f  retn
0x180007720  mov     r9d, edx
0x180007723  mov     [rsp+8+arg_0], rbx
0x180007728  shr     r9d, 0Eh
0x18000772c  or      r9b, 80h
0x180007730  cmp     edx, 200000h
0x180007736  jnb     short loc_18000774D
0x180007738  mov     [rcx], r9b
0x18000773b  mov     [rax], r8b
0x18000773e  mov     [rax+1], r10b
0x180007742  add     rax, 2
0x180007746  mov     rbx, [rsp+8+arg_0]
0x18000774b  jmp     short loc_1800076F2
0x18000774d  mov     [rsp+8+arg_8], rsi
0x180007752  mov     [rsp+8+var_8], rdi
0x180007756  mov     edi, edx
0x180007758  shr     edi, 15h
0x18000775b  or      dil, 80h
0x18000775f  cmp     edx, 10000000h
0x180007765  jnb     short loc_18000777B
0x180007767  mov     [rcx], dil
0x18000776a  mov     [rax], r9b
0x18000776d  mov     [rax+1], r8b
0x180007771  mov     [rax+2], r10b
0x180007775  add     rax, 3
0x180007779  jmp     short loc_180007796
0x18000777b  shr     edx, 1Ch
0x18000777e  or      dl, 80h
0x180007781  mov     [rcx], dl
0x180007783  mov     [rax], dil
0x180007786  mov     [rax+1], r9b
0x18000778a  mov     [rax+2], r8b
0x18000778e  mov     [rax+3], r10b
0x180007792  add     rax, 4
0x180007796  mov     rsi, [rsp+8+arg_8]
0x18000779b  mov     rdi, [rsp+8+var_8]
0x18000779f  jmp     short loc_180007746
```
