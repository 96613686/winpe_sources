# DBOpenXF

- ea: `0x1001a8d0`
- end: `0x1001a92f`
- name: `DBOpenXF`
- size: `95`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1001a8d0`
- `0x1002580a`

## pseudocode

```c
int __stdcall DBOpenXF(int a1, int a2, __int16 a3)
{
  int v3; // eax
  int v4; // ecx
  int result; // eax
  int *v6; // eax

  v3 = MemAllocate(16);
  v4 = v3;
  if ( !v3 )
    return -2;
  *(_DWORD *)(v3 + 4) = a1;
  *(_DWORD *)(v3 + 8) = a2;
  *(_WORD *)(v3 + 12) = a3;
  if ( *(_DWORD *)(dword_1003A9BC + 72) )
  {
    v6 = (int *)dword_1003A9B8;
    dword_1003A9B8 = v4;
    *v6 = v4;
    return 0;
  }
  else
  {
    *(_DWORD *)(dword_1003A9BC + 72) = v3;
    result = 0;
    dword_1003A9B8 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x1001a8d0  mov     edi, edi
0x1001a8d2  push    ebp
0x1001a8d3  mov     ebp, esp
0x1001a8d5  mov     ecx, 10h
0x1001a8da  call    _MemAllocate@4; MemAllocate(x)
0x1001a8df  mov     ecx, eax
0x1001a8e1  test    ecx, ecx
0x1001a8e3  jnz     short loc_1001A8EE
0x1001a8e5  mov     eax, 0FFFFFFFEh
0x1001a8ea  pop     ebp
0x1001a8eb  retn    0Ch
0x1001a8ee  mov     eax, [ebp+arg_0]
0x1001a8f1  mov     [ecx+4], eax
0x1001a8f4  mov     eax, [ebp+arg_4]
0x1001a8f7  mov     [ecx+8], eax
0x1001a8fa  mov     ax, [ebp+arg_8]
0x1001a8fe  mov     [ecx+0Ch], ax
0x1001a902  mov     eax, dword_1003A9BC
0x1001a907  cmp     dword ptr [eax+48h], 0
0x1001a90b  jnz     short loc_1001A91C
0x1001a90d  mov     [eax+48h], ecx
0x1001a910  xor     eax, eax
0x1001a912  mov     dword_1003A9B8, ecx
0x1001a918  pop     ebp
0x1001a919  retn    0Ch
0x1001a91c  mov     eax, dword_1003A9B8
0x1001a921  mov     dword_1003A9B8, ecx
0x1001a927  mov     [eax], ecx
0x1001a929  xor     eax, eax
0x1001a92b  pop     ebp
0x1001a92c  retn    0Ch
```
