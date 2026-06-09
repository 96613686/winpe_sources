# CopyBufferAppendLongText(x,x,x,x)

- ea: `0x10016150`
- end: `0x100161c6`
- name: `_CopyBufferAppendLongText@16`
- size: `118`
- prototype: `int __stdcall(int, int, void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10015cb0`

## callees

- `0x1000b310`
- `0x10016150`
- `0x1002ba60`

## pseudocode

```c
int __stdcall CopyBufferAppendLongText(int a1, int a2, void *Src, size_t Size)
{
  int **v4; // esi
  size_t v5; // edi
  int v6; // ecx
  int *v8; // eax
  int *v9; // eax
  size_t v10; // edi

  v4 = *(int ***)(a1 + 68);
  if ( v4 )
  {
    while ( v4[1] != *(int **)(a2 + 24) )
    {
      v4 = (int **)*v4;
      if ( !v4 )
        goto LABEL_4;
    }
  }
  else
  {
LABEL_4:
    v4 = 0;
  }
  v5 = Size + 2 * (_DWORD)v4[6];
  v6 = MemReAllocate(v4[7], v5 + 2);
  if ( !v6 )
    return -1011;
  v8 = v4[6];
  v4[7] = (int *)v6;
  memcpy((void *)(v6 + 2 * (_DWORD)v8), Src, Size);
  v9 = v4[7];
  v10 = v5 >> 1;
  v4[6] = (int *)v10;
  *((_WORD *)v9 + v10) = 0;
  return 0;
}

```

## disassembly

```asm
0x10016150  push    ebx
0x10016151  push    esi
0x10016152  mov     esi, [esp+8+arg_0]
0x10016156  push    edi
0x10016157  mov     esi, [esi+44h]
0x1001615a  test    esi, esi
0x1001615c  jz      short loc_10016170
0x1001615e  mov     eax, [esp+0Ch+arg_4]
0x10016162  mov     eax, [eax+18h]
0x10016165  cmp     [esi+4], eax
0x10016168  jz      short loc_10016172
0x1001616a  mov     esi, [esi]
0x1001616c  test    esi, esi
0x1001616e  jnz     short loc_10016165
0x10016170  xor     esi, esi
0x10016172  mov     eax, [esi+18h]
0x10016175  mov     ebx, [esp+0Ch+Size]
0x10016179  lea     edi, [ebx+eax*2]
0x1001617c  lea     eax, [edi+2]
0x1001617f  push    eax; Size
0x10016180  push    dword ptr [esi+1Ch]; Src
0x10016183  call    _MemReAllocate@8; MemReAllocate(x,x)
0x10016188  mov     ecx, eax
0x1001618a  test    ecx, ecx
0x1001618c  jnz     short loc_10016199
0x1001618e  pop     edi
0x1001618f  pop     esi
0x10016190  mov     eax, 0FFFFFC0Dh
0x10016195  pop     ebx
0x10016196  retn    10h
0x10016199  mov     eax, [esi+18h]
0x1001619c  push    ebx; Size
0x1001619d  push    [esp+10h+Src]; Src
0x100161a1  mov     [esi+1Ch], ecx
0x100161a4  lea     eax, [ecx+eax*2]
0x100161a7  push    eax; void *
0x100161a8  call    _memcpy
0x100161ad  mov     eax, [esi+1Ch]
0x100161b0  add     esp, 0Ch
0x100161b3  shr     edi, 1
0x100161b5  xor     ecx, ecx
0x100161b7  mov     [esi+18h], edi
0x100161ba  mov     [eax+edi*2], cx
0x100161be  xor     eax, eax
0x100161c0  pop     edi
0x100161c1  pop     esi
0x100161c2  pop     ebx
0x100161c3  retn    10h
```
