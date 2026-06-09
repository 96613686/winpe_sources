# CVDecompressSetPalette(x,x,x)

- ea: `0x1000552a`
- end: `0x10005592`
- name: `_CVDecompressSetPalette@12`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10010148`
- `0x100101f2`

## callees

- `0x10005491`
- `0x1000552a`
- `0x10013599`

## pseudocode

```c
int __thiscall CVDecompressSetPalette(_DWORD *this, int a2)
{
  _DWORD *v2; // ebx
  _BYTE *v3; // edi
  unsigned int i; // ebx

  v2 = this;
  v3 = (_BYTE *)this[13];
  if ( a2 )
  {
    for ( i = 0; i < 0x400; ++i )
      *v3++ = FindNearestRGB(dword_10002368[(unsigned __int8)RgbLookup[i]]);
    v2 = this;
  }
  else
  {
    memmove(v3, RgbLookup, 0x400u);
  }
  v2[12] = 1024;
  return 0;
}

```

## disassembly

```asm
0x1000552a  mov     edi, edi
0x1000552c  push    ebp
0x1000552d  mov     ebp, esp
0x1000552f  push    ecx
0x10005530  push    ecx
0x10005531  cmp     [ebp+arg_0], 0
0x10005535  push    ebx
0x10005536  mov     ebx, ecx
0x10005538  mov     [ebp+var_4], edx
0x1000553b  push    edi
0x1000553c  mov     [ebp+var_8], ebx
0x1000553f  mov     edi, [ebx+34h]
0x10005542  jz      short loc_10005570
0x10005544  xor     ebx, ebx
0x10005546  movzx   eax, ds:_RgbLookup[ebx]
0x1000554d  mov     edx, [ebp+arg_0]
0x10005550  mov     ecx, [ebp+var_4]
0x10005553  push    ds:dword_10002368[eax*4]
0x1000555a  call    _FindNearestRGB@12; FindNearestRGB(x,x,x)
0x1000555f  mov     [edi], al
0x10005561  inc     edi
0x10005562  inc     ebx
0x10005563  cmp     ebx, 400h
0x10005569  jb      short loc_10005546
0x1000556b  mov     ebx, [ebp+var_8]
0x1000556e  jmp     short loc_10005583
0x10005570  push    400h; Size
0x10005575  push    offset _RgbLookup; Src
0x1000557a  push    edi; void *
0x1000557b  call    _memmove
0x10005580  add     esp, 0Ch
0x10005583  pop     edi
0x10005584  mov     dword ptr [ebx+30h], 400h
0x1000558b  xor     eax, eax
0x1000558d  pop     ebx
0x1000558e  leave
0x1000558f  retn    4
```
