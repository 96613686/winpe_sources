# BFRemoveFileSpace(x,x,x)

- ea: `0x100264c2`
- end: `0x100265b8`
- name: `_BFRemoveFileSpace@12`
- size: `246`
- prototype: `int __fastcall(_DWORD *, int, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x10013f50`
- `0x10016fc0`
- `0x10017790`

## callees

- `0x10025bee`
- `0x10025d54`
- `0x10025df5`
- `0x100264c2`
- `0x100366a8`

## pseudocode

```c
int __fastcall BFRemoveFileSpace(_DWORD *a1, int a2, int a3)
{
  int v5; // edx
  int v6; // ecx
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int result; // eax
  int v11; // ebx

  v5 = a1[21];
  if ( a2 >= v5 )
  {
    v6 = v5 + *a1;
    if ( a2 <= v6 - 1 )
    {
      v7 = a1[22];
      if ( v6 == v7 )
      {
        memmove((void *)(a2 + a1[1] - v5), (const void *)(a2 + a1[1] - v5 + a3), v7 - a2 - a3);
        a1[22] -= a3;
        *a1 -= a3;
        a1[23] = 1;
LABEL_16:
        a1[19] = 0;
        return 0;
      }
    }
  }
  v8 = a1[22];
  if ( v8 == a2 )
  {
    v9 = v8 - a3;
    a1[22] = v9;
    a1[20] = v9;
    a1[21] = v9;
    *a1 = 0;
    goto LABEL_16;
  }
  if ( a1[23] != 1 || (result = WriteFileBlock(a1), result >= 0) )
  {
    a1[18] = 0;
    v11 = a2 + a3;
    while ( 1 )
    {
      a1[20] = v11;
      OSSetFilePosition(a1, 0, v11);
      result = ReadFileBlock(a1);
      if ( result < 0 )
        break;
      a1[21] = v11 - a3;
      result = WriteFileBlock(a1);
      if ( result < 0 )
        break;
      v11 += a1[16];
      if ( v11 >= a1[22] )
      {
        a1[20] = a2;
        OSSetFilePosition(a1, 0, a2);
        result = ReadFileBlock(a1);
        if ( result < 0 )
          return result;
        a1[22] -= a3;
        a1[18] = 1;
        goto LABEL_16;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x100264c2  mov     edi, edi
0x100264c4  push    ebp
0x100264c5  mov     ebp, esp
0x100264c7  push    ebx
0x100264c8  push    esi
0x100264c9  push    edi
0x100264ca  mov     edi, ecx
0x100264cc  mov     esi, edx
0x100264ce  mov     edx, [edi+54h]
0x100264d1  cmp     esi, edx
0x100264d3  jl      short loc_10026514
0x100264d5  mov     ecx, [edi]
0x100264d7  add     ecx, edx
0x100264d9  lea     eax, [ecx-1]
0x100264dc  cmp     esi, eax
0x100264de  jg      short loc_10026514
0x100264e0  mov     eax, [edi+58h]
0x100264e3  cmp     ecx, eax
0x100264e5  jnz     short loc_10026514
0x100264e7  mov     ecx, [edi+4]
0x100264ea  sub     eax, esi
0x100264ec  sub     ecx, edx
0x100264ee  add     ecx, esi
0x100264f0  mov     esi, [ebp+arg_0]
0x100264f3  sub     eax, esi
0x100264f5  push    eax; Size
0x100264f6  lea     eax, [ecx+esi]
0x100264f9  push    eax; Src
0x100264fa  push    ecx; void *
0x100264fb  call    _memmove
0x10026500  sub     [edi+58h], esi
0x10026503  add     esp, 0Ch
0x10026506  sub     [edi], esi
0x10026508  mov     dword ptr [edi+5Ch], 1
0x1002650f  jmp     loc_100265A8
0x10026514  mov     eax, [edi+58h]
0x10026517  cmp     eax, esi
0x10026519  jnz     short loc_1002652F
0x1002651b  sub     eax, [ebp+arg_0]
0x1002651e  mov     [edi+58h], eax
0x10026521  mov     [edi+50h], eax
0x10026524  mov     [edi+54h], eax
0x10026527  mov     dword ptr [edi], 0
0x1002652d  jmp     short loc_100265A8
0x1002652f  cmp     dword ptr [edi+5Ch], 1
0x10026533  jnz     short loc_10026540
0x10026535  mov     ecx, edi
0x10026537  call    WriteFileBlock
0x1002653c  test    eax, eax
0x1002653e  js      short loc_100265B1
0x10026540  mov     ebx, [ebp+arg_0]
0x10026543  mov     dword ptr [edi+48h], 0
0x1002654a  add     ebx, esi
0x1002654c  jmp     short loc_10026569
0x1002654e  mov     eax, ebx
0x10026550  mov     ecx, edi
0x10026552  sub     eax, [ebp+arg_0]
0x10026555  mov     [edi+54h], eax
0x10026558  call    WriteFileBlock
0x1002655d  test    eax, eax
0x1002655f  js      short loc_100265B1
0x10026561  add     ebx, [edi+40h]
0x10026564  cmp     ebx, [edi+58h]
0x10026567  jge     short loc_10026583
0x10026569  push    ebx
0x1002656a  xor     edx, edx
0x1002656c  mov     [edi+50h], ebx
0x1002656f  mov     ecx, edi
0x10026571  call    OSSetFilePosition
0x10026576  mov     ecx, edi
0x10026578  call    ReadFileBlock
0x1002657d  test    eax, eax
0x1002657f  jns     short loc_1002654E
0x10026581  jmp     short loc_100265B1
0x10026583  push    esi
0x10026584  xor     edx, edx
0x10026586  mov     [edi+50h], esi
0x10026589  mov     ecx, edi
0x1002658b  call    OSSetFilePosition
0x10026590  mov     ecx, edi
0x10026592  call    ReadFileBlock
0x10026597  test    eax, eax
0x10026599  js      short loc_100265B1
0x1002659b  mov     eax, [ebp+arg_0]
0x1002659e  sub     [edi+58h], eax
0x100265a1  mov     dword ptr [edi+48h], 1
0x100265a8  mov     dword ptr [edi+4Ch], 0
0x100265af  xor     eax, eax
0x100265b1  pop     edi
0x100265b2  pop     esi
0x100265b3  pop     ebx
0x100265b4  pop     ebp
0x100265b5  retn    4
```
