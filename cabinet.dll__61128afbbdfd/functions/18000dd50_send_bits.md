# send_bits

- ea: `0x18000dd50`
- end: `0x18000de34`
- name: `send_bits`
- size: `228`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cd6c`
- `0x18000d5f0`
- `0x18000db18`
- `0x18000dbc8`

## callees

- `0x18000dd50`

## pseudocode

```c
__int64 __fastcall send_bits(__int64 a1, int a2, int a3)
{
  int v3; // r10d
  __int64 result; // rax
  __int16 v6; // r9
  unsigned int v8; // r8d
  __int64 v9; // rdx
  int v10; // r8d

  v3 = *(_DWORD *)(a1 + 72);
  result = a1;
  v6 = *(_WORD *)(a1 + 68) | ((_WORD)a2 << v3);
  *(_WORD *)(a1 + 68) = v6;
  if ( v3 <= 16 - a3 )
  {
    *(_DWORD *)(a1 + 72) = v3 + a3;
    return result;
  }
  v8 = *(_DWORD *)(a1 + 28);
  v9 = *(unsigned __int16 *)(a1 + 24);
  if ( (unsigned int)v9 >= v8 - 2 )
  {
    if ( (unsigned int)v9 < v8 )
    {
      *(_BYTE *)(v9 + *(_QWORD *)(a1 + 8)) = v6;
      LOWORD(v9) = ++*(_WORD *)(a1 + 24);
    }
    else
    {
      *(_DWORD *)(a1 + 64) = 1;
    }
    if ( (unsigned int)(unsigned __int16)v9 >= *(_DWORD *)(a1 + 28) )
    {
      *(_DWORD *)(a1 + 64) = 1;
      goto LABEL_6;
    }
    *(_BYTE *)((unsigned __int16)v9 + *(_QWORD *)(a1 + 8)) = *(_BYTE *)(a1 + 69);
  }
  else
  {
    *(_BYTE *)(v9 + *(_QWORD *)(a1 + 8)) = v6;
    *(_BYTE *)((unsigned __int16)++*(_WORD *)(a1 + 24) + *(_QWORD *)(a1 + 8)) = *(_BYTE *)(a1 + 69);
  }
  ++*(_WORD *)(a1 + 24);
LABEL_6:
  v10 = *(_DWORD *)(a1 + 72) + a3 - 16;
  *(_WORD *)(a1 + 68) = a2 >> (16 - *(_BYTE *)(a1 + 72));
  *(_DWORD *)(a1 + 72) = v10;
  return result;
}

```

## disassembly

```asm
0x18000dd50  mov     [rsp+arg_0], rbx
0x18000dd55  mov     [rsp+arg_8], rdi
0x18000dd5a  mov     r10d, [rcx+48h]
0x18000dd5e  mov     rax, rcx
0x18000dd61  mov     ecx, r10d
0x18000dd64  movzx   r9d, dx
0x18000dd68  shl     r9w, cl
0x18000dd6c  mov     ebx, 10h
0x18000dd71  mov     ecx, ebx
0x18000dd73  mov     edi, r8d
0x18000dd76  or      r9w, [rax+44h]
0x18000dd7b  sub     ecx, r8d
0x18000dd7e  mov     [rax+44h], r9w
0x18000dd83  mov     r11d, edx
0x18000dd86  cmp     r10d, ecx
0x18000dd89  jg      short loc_18000DD9D
0x18000dd8b  lea     ecx, [r10+r8]
0x18000dd8f  mov     [rax+48h], ecx
0x18000dd92  mov     rbx, [rsp+arg_0]
0x18000dd97  mov     rdi, [rsp+arg_8]
0x18000dd9c  retn
0x18000dd9d  mov     r8d, [rax+1Ch]
0x18000dda1  movzx   edx, word ptr [rax+18h]
0x18000dda5  lea     ecx, [r8-2]
0x18000dda9  cmp     edx, ecx
0x18000ddab  jnb     short loc_18000DDF3
0x18000ddad  mov     rcx, [rax+8]
0x18000ddb1  mov     [rdx+rcx], r9b
0x18000ddb5  inc     word ptr [rax+18h]
0x18000ddb9  movzx   r8d, word ptr [rax+18h]
0x18000ddbe  mov     rdx, [rax+8]
0x18000ddc2  movzx   ecx, byte ptr [rax+45h]
0x18000ddc6  mov     [r8+rdx], cl
0x18000ddca  inc     word ptr [rax+18h]
0x18000ddce  sub     ebx, [rax+48h]
0x18000ddd1  lea     r8d, [rdi-10h]
0x18000ddd5  add     r8d, [rax+48h]
0x18000ddd9  movzx   ecx, bl
0x18000dddc  sar     r11d, cl
0x18000dddf  mov     [rax+44h], r11w
0x18000dde4  mov     [rax+48h], r8d
0x18000dde8  mov     rbx, [rsp+arg_0]
0x18000dded  mov     rdi, [rsp+arg_8]
0x18000ddf2  retn
0x18000ddf3  cmp     edx, r8d
0x18000ddf6  jb      short loc_18000DE01
0x18000ddf8  mov     dword ptr [rax+40h], 1
0x18000ddff  jmp     short loc_18000DE11
0x18000de01  mov     rcx, [rax+8]
0x18000de05  mov     [rdx+rcx], r9b
0x18000de09  inc     word ptr [rax+18h]
0x18000de0d  movzx   edx, word ptr [rax+18h]
0x18000de11  movzx   ecx, dx
0x18000de14  cmp     ecx, [rax+1Ch]
0x18000de17  jb      short loc_18000DE22
0x18000de19  mov     dword ptr [rax+40h], 1
0x18000de20  jmp     short loc_18000DDCE
0x18000de22  mov     r8, [rax+8]
0x18000de26  movzx   r9d, dx
0x18000de2a  movzx   edx, byte ptr [rax+45h]
0x18000de2e  mov     [r9+r8], dl
0x18000de32  jmp     short loc_18000DDCA
```
