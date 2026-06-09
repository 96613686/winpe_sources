# ExcelDeleteNote(x,x)

- ea: `0x100168a0`
- end: `0x1001693f`
- name: `_ExcelDeleteNote@8`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x10016680`
- `0x10029b60`

## callees

- `0x10012270`
- `0x10013f50`
- `0x100168a0`
- `0x10025ab7`

## pseudocode

```c
int __thiscall ExcelDeleteNote(int *this, int a2)
{
  int result; // eax
  _DWORD *v4; // eax
  int *v5; // esi
  int v6; // ebx
  int *v7; // ecx
  int *v8; // edx

  dword_1003A784 = a2;
  result = ExcelScanFile(this, dword_10038320, 0);
  if ( result >= 0 )
  {
    if ( !result )
      return 0;
    v4 = (_DWORD *)this[11];
    if ( *v4 == 1 )
      v4 = (_DWORD *)v4[11];
    v5 = (int *)v4[22];
    v6 = *(_DWORD *)(this[12] + 20);
    if ( v6 )
    {
      v7 = *(int **)(v6 + 4);
      v8 = 0;
      if ( v7 )
      {
        while ( 1 )
        {
          result = *v7;
          if ( v7 == v5 )
            break;
          v8 = v7;
          v7 = (int *)*v7;
          if ( !result )
            return result;
        }
        if ( !v8 )
        {
          *(_DWORD *)(v6 + 4) = result;
          MemFree(v7);
          return 0;
        }
        *v8 = result;
        MemFree(v7);
      }
      return 0;
    }
    return RemoveFileSpace(v4[23], 1);
  }
  return result;
}

```

## disassembly

```asm
0x100168a0  mov     edi, edi
0x100168a2  push    ebp
0x100168a3  mov     ebp, esp
0x100168a5  mov     eax, [ebp+arg_0]
0x100168a8  mov     edx, offset dword_10038320
0x100168ad  push    ebx
0x100168ae  push    esi
0x100168af  push    edi
0x100168b0  mov     word ptr dword_1003A784, ax
0x100168b6  mov     edi, ecx
0x100168b8  shr     eax, 10h
0x100168bb  push    0
0x100168bd  mov     word ptr dword_1003A784+2, ax
0x100168c3  call    _ExcelScanFile@12; ExcelScanFile(x,x,x)
0x100168c8  test    eax, eax
0x100168ca  js      short loc_10016938
0x100168cc  jz      short loc_10016923
0x100168ce  mov     eax, [edi+2Ch]
0x100168d1  cmp     dword ptr [eax], 1
0x100168d4  jnz     short loc_100168D9
0x100168d6  mov     eax, [eax+2Ch]
0x100168d9  mov     esi, [eax+58h]
0x100168dc  mov     ecx, [eax+5Ch]
0x100168df  mov     eax, [edi+30h]
0x100168e2  mov     ebx, [eax+14h]
0x100168e5  test    ebx, ebx
0x100168e7  jz      short loc_1001692C
0x100168e9  mov     ecx, [ebx+4]
0x100168ec  xor     edx, edx
0x100168ee  test    ecx, ecx
0x100168f0  jz      short loc_10016923
0x100168f2  mov     eax, [ecx]
0x100168f4  cmp     ecx, esi
0x100168f6  jz      short loc_10016907
0x100168f8  mov     edx, ecx
0x100168fa  mov     ecx, eax
0x100168fc  test    ecx, ecx
0x100168fe  jnz     short loc_100168F2
0x10016900  pop     edi
0x10016901  pop     esi
0x10016902  pop     ebx
0x10016903  pop     ebp
0x10016904  retn    4
0x10016907  test    edx, edx
0x10016909  jnz     short loc_1001691C
0x1001690b  mov     [ebx+4], eax
0x1001690e  call    _MemFree@4; MemFree(x)
0x10016913  xor     eax, eax
0x10016915  pop     edi
0x10016916  pop     esi
0x10016917  pop     ebx
0x10016918  pop     ebp
0x10016919  retn    4
0x1001691c  mov     [edx], eax
0x1001691e  call    _MemFree@4; MemFree(x)
0x10016923  xor     eax, eax
0x10016925  pop     edi
0x10016926  pop     esi
0x10016927  pop     ebx
0x10016928  pop     ebp
0x10016929  retn    4
0x1001692c  push    1
0x1001692e  push    ecx
0x1001692f  mov     edx, esi
0x10016931  mov     ecx, edi
0x10016933  call    RemoveFileSpace
0x10016938  pop     edi
0x10016939  pop     esi
0x1001693a  pop     ebx
0x1001693b  pop     ebp
0x1001693c  retn    4
```
