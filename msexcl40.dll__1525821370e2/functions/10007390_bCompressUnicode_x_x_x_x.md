# bCompressUnicode(x,x,x,x)

- ea: `0x10007390`
- end: `0x100073d1`
- name: `_bCompressUnicode@16`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1000d030`

## callees

- `0x10007390`

## pseudocode

```c
int __thiscall bCompressUnicode(_WORD *this, _BYTE *a2, _DWORD *a3)
{
  _BYTE *v3; // edx
  char v5; // al

  v3 = (char *)this + 1;
  if ( !*this )
    return 1;
  while ( !*v3 )
  {
    v5 = *(_BYTE *)this;
    v3 += 2;
    --*a3;
    ++this;
    *a2++ = v5;
    if ( !*this )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x10007390  mov     edi, edi
0x10007392  push    ebp
0x10007393  mov     ebp, esp
0x10007395  cmp     word ptr [ecx], 0
0x10007399  lea     edx, [ecx+1]
0x1000739c  push    esi
0x1000739d  mov     esi, [ebp+arg_0]
0x100073a0  push    edi
0x100073a1  jz      short loc_100073BE
0x100073a3  mov     edi, [ebp+arg_4]
0x100073a6  cmp     byte ptr [edx], 0
0x100073a9  jnz     short loc_100073C9
0x100073ab  mov     al, [ecx]
0x100073ad  add     edx, 2
0x100073b0  dec     dword ptr [edi]
0x100073b2  add     ecx, 2
0x100073b5  mov     [esi], al
0x100073b7  inc     esi
0x100073b8  cmp     word ptr [ecx], 0
0x100073bc  jnz     short loc_100073A6
0x100073be  pop     edi
0x100073bf  mov     eax, 1
0x100073c4  pop     esi
0x100073c5  pop     ebp
0x100073c6  retn    8
0x100073c9  pop     edi
0x100073ca  xor     eax, eax
0x100073cc  pop     esi
0x100073cd  pop     ebp
0x100073ce  retn    8
```
