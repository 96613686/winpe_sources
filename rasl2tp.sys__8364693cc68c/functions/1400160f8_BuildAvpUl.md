# BuildAvpUl

- ea: `0x1400160f8`
- end: `0x140016139`
- name: `BuildAvpUl`
- size: `65`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1400162b0`
- `0x140016440`
- `0x140016840`
- `0x140016910`
- `0x140016990`
- `0x140016b60`
- `0x140016d00`

## callees

- `0x1400160f8`

## pseudocode

```c
__int64 __fastcall BuildAvpUl(__int16 a1, char a2, unsigned int a3, __int64 a4)
{
  __int16 v4; // ax

  *(_WORD *)(a4 + 2) = 0;
  *(_WORD *)(a4 + 4) = __ROR2__(a1, 8);
  *(_DWORD *)(a4 + 6) = _byteswap_ulong(a3);
  *(_WORD *)a4 = 10;
  v4 = 10;
  if ( a2 )
  {
    v4 = -32758;
    *(_WORD *)a4 = -32758;
  }
  *(_WORD *)a4 = __ROR2__(v4, 8);
  return 10;
}

```

## disassembly

```asm
0x1400160f8  ror     cx, 8
0x1400160fc  xor     eax, eax
0x1400160fe  mov     [r9+2], ax
0x140016103  mov     [r9+4], cx
0x140016108  lea     rcx, [r9+6]
0x14001610c  bswap   r8d
0x14001610f  mov     [rcx], r8d
0x140016112  sub     cx, r9w
0x140016116  add     cx, 4
0x14001611a  mov     [r9], cx
0x14001611e  movzx   eax, cx
0x140016121  test    dl, dl
0x140016123  jz      short loc_14001612D
0x140016125  or      ax, 8000h
0x140016129  mov     [r9], ax
0x14001612d  ror     ax, 8
0x140016131  mov     [r9], ax
0x140016135  movzx   eax, cx
0x140016138  retn
```
