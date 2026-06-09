# GetRGBLookupEntry(x,x,x)

- ea: `0x1000dce2`
- end: `0x1000dd10`
- name: `_GetRGBLookupEntry@12`
- size: `46`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1000dd16`
- `0x1000de78`
- `0x1000e4ba`
- `0x1000e701`

## callees

- `0x1000dce2`

## pseudocode

```c
char __fastcall GetRGBLookupEntry(int a1, int a2, __int16 a3)
{
  bool v3; // cc

  if ( a3 < 0 )
  {
    v3 = a3 <= a2;
  }
  else
  {
    v3 = a3 <= a2;
    if ( a3 < a2 )
      return *(_BYTE *)(a3 + a1);
  }
  if ( v3 )
    return *(_BYTE *)a1;
  else
    return *(_BYTE *)(a1 + a2 - 1);
}

```

## disassembly

```asm
0x1000dce2  mov     edi, edi
0x1000dce4  push    ebp
0x1000dce5  mov     ebp, esp
0x1000dce7  movsx   eax, [ebp+arg_0]
0x1000dceb  push    esi
0x1000dcec  push    edi
0x1000dced  xor     edi, edi
0x1000dcef  cmp     di, [ebp+arg_0]
0x1000dcf3  pop     edi
0x1000dcf4  pop     esi
0x1000dcf5  jg      short loc_1000DD00
0x1000dcf7  cmp     eax, edx
0x1000dcf9  jge     short loc_1000DD02
0x1000dcfb  mov     al, [eax+ecx]
0x1000dcfe  jmp     short loc_1000DD0C
0x1000dd00  cmp     eax, edx
0x1000dd02  jle     short loc_1000DD0A
0x1000dd04  mov     al, [ecx+edx-1]
0x1000dd08  jmp     short loc_1000DD0C
0x1000dd0a  mov     al, [ecx]
0x1000dd0c  pop     ebp
0x1000dd0d  retn    4
```
