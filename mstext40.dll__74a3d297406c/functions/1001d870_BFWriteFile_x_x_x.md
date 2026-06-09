# BFWriteFile(x,x,x)

- ea: `0x1001d870`
- end: `0x1001d998`
- name: `_BFWriteFile@12`
- size: `296`
- prototype: `int __stdcall(int, void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x10025e40`
- `0x10028bb0`

## callees

- `0x1001d870`
- `0x1001da60`
- `0x1002ba60`

## pseudocode

```c
int __stdcall BFWriteFile(int a1, char *Src, size_t Size)
{
  int result; // eax
  void *v4; // ecx
  _BYTE *v5; // edx
  size_t v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // eax
  int v9; // ecx
  bool v10; // zf
  int v11; // eax
  int v12; // eax

  if ( !Size )
    return 0;
  v4 = *(void **)(a1 + 8);
  v5 = *(_BYTE **)(a1 + 4);
  v6 = (size_t)&v5[*(_DWORD *)a1 - (_DWORD)v4];
  if ( Size <= v6 )
  {
    memcpy(v4, Src, Size);
    *(_DWORD *)(a1 + 8) += Size;
    v7 = *(_DWORD *)(a1 + 8);
    if ( *(_DWORD *)(a1 + 56) < v7 )
      *(_DWORD *)(a1 + 56) = v7;
    *(_DWORD *)(a1 + 80) = 1;
    return 0;
  }
  if ( Size <= *(_DWORD *)(a1 + 52) + v5 - (_BYTE *)v4 )
  {
    memcpy(v4, Src, Size);
    *(_DWORD *)(a1 + 8) += Size;
LABEL_17:
    v9 = *(_DWORD *)(a1 + 72);
    v10 = v9 + *(_DWORD *)a1 == *(_DWORD *)(a1 + 76);
    v11 = *(_DWORD *)(a1 + 8);
    *(_DWORD *)(a1 + 80) = 1;
    *(_DWORD *)(a1 + 64) = 0;
    if ( v10 )
    {
      v12 = v11 - *(_DWORD *)(a1 + 4);
      *(_DWORD *)a1 = v12;
      *(_DWORD *)(a1 + 76) = v9 + v12;
    }
    else
    {
      *(_DWORD *)a1 = v11 - *(_DWORD *)(a1 + 4);
    }
    return 0;
  }
  if ( *(_DWORD *)(a1 + 80) != 1 )
  {
    *(_DWORD *)(a1 + 72) += (_BYTE *)v4 - v5;
    memcpy(v5, Src, Size);
    *(_DWORD *)(a1 + 8) = Size + *(_DWORD *)(a1 + 4);
    goto LABEL_17;
  }
  memcpy(v4, Src, v6);
  *(_DWORD *)(a1 + 8) += v6;
  v8 = *(_DWORD *)(a1 + 8);
  if ( *(_DWORD *)(a1 + 56) < v8 )
    *(_DWORD *)(a1 + 56) = v8;
  result = WriteFileBlock(a1);
  if ( result >= 0 )
  {
    if ( Size - v6 > *(_DWORD *)(a1 + 52) )
      return -5;
    memcpy(*(void **)(a1 + 4), &Src[v6], Size - v6);
    *(_DWORD *)(a1 + 8) = *(_DWORD *)(a1 + 4) + Size - v6;
    goto LABEL_17;
  }
  return result;
}

```

## disassembly

```asm
0x1001d870  push    edi
0x1001d871  mov     edi, [esp+4+Size]
0x1001d875  test    edi, edi
0x1001d877  jnz     short loc_1001D87F
0x1001d879  xor     eax, eax
0x1001d87b  pop     edi
0x1001d87c  retn    0Ch
0x1001d87f  push    ebx
0x1001d880  push    esi
0x1001d881  mov     esi, [esp+0Ch+arg_0]
0x1001d885  mov     ebx, [esi]
0x1001d887  mov     ecx, [esi+8]
0x1001d88a  sub     ebx, ecx
0x1001d88c  mov     edx, [esi+4]
0x1001d88f  add     ebx, edx
0x1001d891  cmp     edi, ebx
0x1001d893  ja      short loc_1001D8C0
0x1001d895  push    edi; Size
0x1001d896  push    [esp+10h+Src]; Src
0x1001d89a  push    ecx; void *
0x1001d89b  call    _memcpy
0x1001d8a0  add     [esi+8], edi
0x1001d8a3  add     esp, 0Ch
0x1001d8a6  mov     eax, [esi+8]
0x1001d8a9  cmp     [esi+38h], eax
0x1001d8ac  jnb     short loc_1001D8B1
0x1001d8ae  mov     [esi+38h], eax
0x1001d8b1  mov     dword ptr [esi+50h], 1
0x1001d8b8  xor     eax, eax
0x1001d8ba  pop     esi
0x1001d8bb  pop     ebx
0x1001d8bc  pop     edi
0x1001d8bd  retn    0Ch
0x1001d8c0  mov     eax, edx
0x1001d8c2  sub     eax, ecx
0x1001d8c4  add     eax, [esi+34h]
0x1001d8c7  push    ebp
0x1001d8c8  cmp     edi, eax
0x1001d8ca  ja      short loc_1001D8DF
0x1001d8cc  push    edi; Size
0x1001d8cd  push    [esp+14h+Src]; Src
0x1001d8d1  push    ecx; void *
0x1001d8d2  call    _memcpy
0x1001d8d7  add     esp, 0Ch
0x1001d8da  add     [esi+8], edi
0x1001d8dd  jmp     short loc_1001D95A
0x1001d8df  cmp     dword ptr [esi+50h], 1
0x1001d8e3  jnz     short loc_1001D93F
0x1001d8e5  mov     ebp, [esp+10h+Src]
0x1001d8e9  push    ebx; Size
0x1001d8ea  push    ebp; Src
0x1001d8eb  push    ecx; void *
0x1001d8ec  call    _memcpy
0x1001d8f1  add     [esi+8], ebx
0x1001d8f4  add     esp, 0Ch
0x1001d8f7  mov     eax, [esi+8]
0x1001d8fa  cmp     [esi+38h], eax
0x1001d8fd  jnb     short loc_1001D902
0x1001d8ff  mov     [esi+38h], eax
0x1001d902  push    esi
0x1001d903  call    WriteFileBlock
0x1001d908  test    eax, eax
0x1001d90a  js      loc_1001D991
0x1001d910  mov     eax, edi
0x1001d912  sub     eax, ebx
0x1001d914  cmp     eax, [esi+34h]
0x1001d917  ja      short loc_1001D933
0x1001d919  push    eax; Size
0x1001d91a  lea     eax, [ebx+ebp]
0x1001d91d  push    eax; Src
0x1001d91e  push    dword ptr [esi+4]; void *
0x1001d921  call    _memcpy
0x1001d926  sub     edi, ebx
0x1001d928  add     esp, 0Ch
0x1001d92b  add     edi, [esi+4]
0x1001d92e  mov     [esi+8], edi
0x1001d931  jmp     short loc_1001D95A
0x1001d933  pop     ebp
0x1001d934  pop     esi
0x1001d935  pop     ebx
0x1001d936  mov     eax, 0FFFFFFFBh
0x1001d93b  pop     edi
0x1001d93c  retn    0Ch
0x1001d93f  push    edi; Size
0x1001d940  push    [esp+14h+Src]; Src
0x1001d944  sub     ecx, edx
0x1001d946  add     [esi+48h], ecx
0x1001d949  push    edx; void *
0x1001d94a  call    _memcpy
0x1001d94f  mov     eax, [esi+4]
0x1001d952  add     esp, 0Ch
0x1001d955  add     eax, edi
0x1001d957  mov     [esi+8], eax
0x1001d95a  mov     eax, [esi]
0x1001d95c  mov     ecx, [esi+48h]
0x1001d95f  add     eax, ecx
0x1001d961  cmp     eax, [esi+4Ch]
0x1001d964  mov     eax, [esi+8]
0x1001d967  mov     dword ptr [esi+50h], 1
0x1001d96e  mov     dword ptr [esi+40h], 0
0x1001d975  jnz     short loc_1001D98A
0x1001d977  sub     eax, [esi+4]
0x1001d97a  mov     [esi], eax
0x1001d97c  add     eax, ecx
0x1001d97e  pop     ebp
0x1001d97f  mov     [esi+4Ch], eax
0x1001d982  xor     eax, eax
0x1001d984  pop     esi
0x1001d985  pop     ebx
0x1001d986  pop     edi
0x1001d987  retn    0Ch
0x1001d98a  sub     eax, [esi+4]
0x1001d98d  mov     [esi], eax
0x1001d98f  xor     eax, eax
0x1001d991  pop     ebp
0x1001d992  pop     esi
0x1001d993  pop     ebx
0x1001d994  pop     edi
0x1001d995  retn    0Ch
```
