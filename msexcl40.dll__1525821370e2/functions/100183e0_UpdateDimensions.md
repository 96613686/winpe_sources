# UpdateDimensions

- ea: `0x100183e0`
- end: `0x10018426`
- name: `UpdateDimensions`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x10018430`
- `0x10018550`

## callees

- `0x100183e0`

## pseudocode

```c
int __thiscall UpdateDimensions(unsigned __int16 *this, int a2, int a3)
{
  unsigned __int16 v3; // di
  int result; // eax

  v3 = *this;
  if ( HIWORD(a2) < this[1] )
    this[1] = HIWORD(a2);
  result = a3;
  if ( HIWORD(a3) > this[3] )
    this[3] = HIWORD(a3);
  if ( (unsigned __int16)a2 < v3 )
    *this = a2;
  if ( (unsigned __int16)a3 > this[2] )
    this[2] = a3;
  return result;
}

```

## disassembly

```asm
0x100183e0  mov     edi, edi
0x100183e2  push    ebp
0x100183e3  mov     ebp, esp
0x100183e5  mov     edx, [ebp+arg_0]
0x100183e8  mov     eax, edx
0x100183ea  push    esi
0x100183eb  shr     eax, 10h
0x100183ee  push    edi
0x100183ef  movzx   edi, word ptr [ecx]
0x100183f2  cmp     ax, [ecx+2]
0x100183f6  jnb     short loc_100183FC
0x100183f8  mov     [ecx+2], ax
0x100183fc  mov     eax, [ebp+arg_4]
0x100183ff  mov     esi, eax
0x10018401  shr     esi, 10h
0x10018404  cmp     si, [ecx+6]
0x10018408  jbe     short loc_1001840E
0x1001840a  mov     [ecx+6], si
0x1001840e  cmp     dx, di
0x10018411  pop     edi
0x10018412  pop     esi
0x10018413  jnb     short loc_10018418
0x10018415  mov     [ecx], dx
0x10018418  cmp     ax, [ecx+4]
0x1001841c  jbe     short loc_10018422
0x1001841e  mov     [ecx+4], ax
0x10018422  pop     ebp
0x10018423  retn    8
```
