# BuildAvpUs

- ea: `0x140016140`
- end: `0x140016184`
- name: `BuildAvpUs`
- size: `68`
- prototype: ``
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x140016190`
- `0x140016280`
- `0x1400162b0`
- `0x1400163b0`
- `0x140016440`
- `0x140016840`
- `0x140016910`
- `0x140016990`
- `0x140016ae0`
- `0x140016b60`
- `0x140016d00`
- `0x140016e80`
- `0x140016f70`

## callees

- `0x140016140`

## pseudocode

```c
__int64 __fastcall BuildAvpUs(__int16 a1, char a2, __int16 a3, _WORD *a4)
{
  __int16 v4; // ax

  a4[1] = 0;
  a4[2] = __ROR2__(a1, 8);
  a4[3] = __ROR2__(a3, 8);
  *a4 = 8;
  v4 = 8;
  if ( a2 )
  {
    v4 = -32760;
    *a4 = -32760;
  }
  *a4 = __ROR2__(v4, 8);
  return 8;
}

```

## disassembly

```asm
0x140016140  ror     cx, 8
0x140016144  xor     eax, eax
0x140016146  mov     [r9+2], ax
0x14001614b  mov     [r9+4], cx
0x140016150  lea     rcx, [r9+6]
0x140016154  ror     r8w, 8
0x140016159  mov     [rcx], r8w
0x14001615d  sub     cx, r9w
0x140016161  add     cx, 2
0x140016165  mov     [r9], cx
0x140016169  movzx   eax, cx
0x14001616c  test    dl, dl
0x14001616e  jz      short loc_140016178
0x140016170  or      ax, 8000h
0x140016174  mov     [r9], ax
0x140016178  ror     ax, 8
0x14001617c  mov     [r9], ax
0x140016180  movzx   eax, cx
0x140016183  retn
```
