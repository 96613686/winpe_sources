# DBOpenBoundSheet

- ea: `0x1001aa40`
- end: `0x1001aaca`
- name: `DBOpenBoundSheet`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1001aa40`
- `0x1002580a`

## pseudocode

```c
int __stdcall DBOpenBoundSheet(__int16 *a1, char a2, int a3)
{
  int v3; // eax
  int v4; // edi
  int result; // eax
  _WORD *v7; // edx
  int v8; // ecx
  __int16 v9; // ax
  int *v10; // eax

  v3 = MemAllocate(528);
  v4 = v3;
  if ( !v3 )
    return -2;
  v7 = (_WORD *)(v3 + 14);
  v8 = 0;
  while ( 1 )
  {
    v9 = *a1;
    *v7++ = *a1++;
    if ( !v9 )
      break;
    if ( ++v8 >= 255 )
    {
      *v7 = 0;
      break;
    }
  }
  *(_BYTE *)(v4 + 12) = a2 == 0;
  if ( *(_DWORD *)(dword_1003A9BC + 80) )
  {
    v10 = (int *)dword_1003A9C0;
    dword_1003A9C0 = v4;
    *v10 = v4;
    return 0;
  }
  else
  {
    *(_DWORD *)(dword_1003A9BC + 80) = v4;
    result = 0;
    dword_1003A9C0 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x1001aa40  mov     edi, edi
0x1001aa42  push    ebp
0x1001aa43  mov     ebp, esp
0x1001aa45  push    edi
0x1001aa46  mov     ecx, 210h
0x1001aa4b  call    _MemAllocate@4; MemAllocate(x)
0x1001aa50  mov     edi, eax
0x1001aa52  test    edi, edi
0x1001aa54  jnz     short loc_1001AA5E
0x1001aa56  lea     eax, [edi-2]
0x1001aa59  pop     edi
0x1001aa5a  pop     ebp
0x1001aa5b  retn    0Ch
0x1001aa5e  push    esi
0x1001aa5f  mov     esi, [ebp+arg_0]
0x1001aa62  lea     edx, [edi+0Eh]
0x1001aa65  xor     ecx, ecx
0x1001aa67  nop     word ptr [eax+eax+00000000h]
0x1001aa70  movzx   eax, word ptr [esi]
0x1001aa73  lea     edx, [edx+2]
0x1001aa76  mov     [edx-2], ax
0x1001aa7a  lea     esi, [esi+2]
0x1001aa7d  test    ax, ax
0x1001aa80  jz      short loc_1001AA90
0x1001aa82  inc     ecx
0x1001aa83  cmp     ecx, 0FFh
0x1001aa89  jl      short loc_1001AA70
0x1001aa8b  xor     eax, eax
0x1001aa8d  mov     [edx], ax
0x1001aa90  cmp     [ebp+arg_4], 0
0x1001aa94  pop     esi
0x1001aa95  setz    al
0x1001aa98  mov     [edi+0Ch], al
0x1001aa9b  mov     eax, dword_1003A9BC
0x1001aaa0  cmp     dword ptr [eax+50h], 0
0x1001aaa4  jnz     short loc_1001AAB6
0x1001aaa6  mov     [eax+50h], edi
0x1001aaa9  xor     eax, eax
0x1001aaab  mov     dword_1003A9C0, edi
0x1001aab1  pop     edi
0x1001aab2  pop     ebp
0x1001aab3  retn    0Ch
0x1001aab6  mov     eax, dword_1003A9C0
0x1001aabb  mov     dword_1003A9C0, edi
0x1001aac1  mov     [eax], edi
0x1001aac3  xor     eax, eax
0x1001aac5  pop     edi
0x1001aac6  pop     ebp
0x1001aac7  retn    0Ch
```
