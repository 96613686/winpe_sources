# CompressEnd(x)

- ea: `0x1000fdf3`
- end: `0x1000fe1b`
- name: `_CompressEnd@4`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100093a0`
- `0x1000f001`
- `0x1000fbcc`

## callees

- `0x10004a67`
- `0x1000fdf3`

## pseudocode

```c
int __thiscall CompressEnd(int this)
{
  int result; // eax

  if ( !*(_BYTE *)(this + 4) )
    return -100;
  UnwindCompressBegin(*(HLOCAL *)(this + 8));
  result = 0;
  *(_DWORD *)(this + 88) = 0;
  *(_DWORD *)(this + 64) = 0;
  *(_DWORD *)(this + 60) = 0;
  *(_BYTE *)(this + 4) = 0;
  return result;
}

```

## disassembly

```asm
0x1000fdf3  mov     edi, edi
0x1000fdf5  push    esi
0x1000fdf6  mov     esi, ecx
0x1000fdf8  cmp     byte ptr [esi+4], 0
0x1000fdfc  jnz     short loc_1000FE03
0x1000fdfe  push    0FFFFFF9Ch
0x1000fe00  pop     eax
0x1000fe01  pop     esi
0x1000fe02  retn
0x1000fe03  mov     ecx, [esi+8]; hMem
0x1000fe06  call    _UnwindCompressBegin@4; UnwindCompressBegin(x)
0x1000fe0b  xor     eax, eax
0x1000fe0d  mov     [esi+58h], eax
0x1000fe10  mov     [esi+40h], eax
0x1000fe13  mov     [esi+3Ch], eax
0x1000fe16  mov     [esi+4], al
0x1000fe19  pop     esi
0x1000fe1a  retn
```
