# BFWriteFile(x,x,x)

- ea: `0x1002611f`
- end: `0x1002622d`
- name: `_BFWriteFile@12`
- size: `270`
- prototype: `int __fastcall(int, char *, unsigned int Size)`
- caller_count: `19`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1000bfc0`
- `0x1000c030`
- `0x1000c670`
- `0x1000c9f0`
- `0x1000ca90`
- `0x1000d030`
- `0x1000d760`
- `0x10013d10`
- `0x10014020`
- `0x10014320`
- `0x10014c50`
- `0x10015090`
- `0x10015ed0`
- `0x10016240`
- `0x100163d0`
- `0x10016680`
- `0x10016950`
- `0x10016b00`
- `0x1001b770`

## callees

- `0x10025df5`
- `0x1002611f`
- `0x1003669c`

## pseudocode

```c
int __fastcall BFWriteFile(int a1, char *a2, unsigned int Size)
{
  unsigned int v3; // edi
  char *v6; // edx
  size_t v7; // ecx
  unsigned int v8; // eax
  unsigned int v9; // ecx
  size_t v10; // eax
  int result; // eax
  unsigned int v12; // ecx
  int v13; // edx
  size_t v14; // [esp+10h] [ebp-4h]

  v3 = Size;
  if ( !Size )
    return 0;
  v6 = *(char **)(a1 + 8);
  v7 = *(_DWORD *)a1 + *(_DWORD *)(a1 + 4) - (_DWORD)v6;
  v14 = v7;
  if ( Size <= v7 )
  {
    memcpy(v6, a2, Size);
    v8 = Size + *(_DWORD *)(a1 + 8);
    *(_DWORD *)(a1 + 8) = v8;
    if ( *(_DWORD *)(a1 + 68) < v8 )
      *(_DWORD *)(a1 + 68) = v8;
    *(_DWORD *)(a1 + 92) = 1;
    return 0;
  }
  if ( Size <= *(_DWORD *)(a1 + 4) + *(_DWORD *)(a1 + 64) - (int)v6 )
  {
    memcpy(v6, a2, Size);
    *(_DWORD *)(a1 + 8) += Size;
    v9 = *(_DWORD *)(a1 + 8);
LABEL_17:
    v12 = v9 - *(_DWORD *)(a1 + 4);
    *(_DWORD *)(a1 + 76) = 0;
    *(_DWORD *)(a1 + 92) = 1;
    v13 = *(_DWORD *)(a1 + 84);
    if ( v13 + *(_DWORD *)a1 == *(_DWORD *)(a1 + 88) )
      *(_DWORD *)(a1 + 88) = v12 + v13;
    *(_DWORD *)a1 = v12;
    return 0;
  }
  if ( *(_DWORD *)(a1 + 92) != 1 )
  {
    *(_DWORD *)(a1 + 84) += &v6[-*(_DWORD *)(a1 + 4)];
    memcpy(*(void **)(a1 + 4), a2, Size);
LABEL_16:
    v9 = v3 + *(_DWORD *)(a1 + 4);
    *(_DWORD *)(a1 + 8) = v9;
    goto LABEL_17;
  }
  memcpy(v6, a2, v7);
  v10 = v14 + *(_DWORD *)(a1 + 8);
  *(_DWORD *)(a1 + 8) = v10;
  if ( *(_DWORD *)(a1 + 68) < v10 )
    *(_DWORD *)(a1 + 68) = v10;
  result = WriteFileBlock(a1);
  if ( result >= 0 )
  {
    if ( Size - v14 > *(_DWORD *)(a1 + 64) )
      return -5;
    memcpy(*(void **)(a1 + 4), &a2[v14], Size - v14);
    v3 = Size - v14;
    goto LABEL_16;
  }
  return result;
}

```

## disassembly

```asm
0x1002611f  mov     edi, edi
0x10026121  push    ebp
0x10026122  mov     ebp, esp
0x10026124  push    ecx
0x10026125  push    ecx
0x10026126  push    ebx
0x10026127  push    esi
0x10026128  push    edi
0x10026129  mov     edi, [ebp+Size]
0x1002612c  mov     ebx, edx
0x1002612e  mov     esi, ecx
0x10026130  test    edi, edi
0x10026132  jz      loc_10026224
0x10026138  mov     ecx, [esi+4]
0x1002613b  mov     edx, [esi+8]
0x1002613e  sub     ecx, edx
0x10026140  add     ecx, [esi]
0x10026142  mov     [ebp+var_4], ecx
0x10026145  cmp     edi, ecx
0x10026147  ja      short loc_10026170
0x10026149  push    edi; Size
0x1002614a  push    ebx; Src
0x1002614b  push    edx; void *
0x1002614c  call    _memcpy
0x10026151  mov     eax, [esi+8]
0x10026154  add     esp, 0Ch
0x10026157  add     eax, edi
0x10026159  mov     [esi+8], eax
0x1002615c  cmp     [esi+44h], eax
0x1002615f  jnb     short loc_10026164
0x10026161  mov     [esi+44h], eax
0x10026164  mov     dword ptr [esi+5Ch], 1
0x1002616b  jmp     loc_10026224
0x10026170  mov     eax, [esi+40h]
0x10026173  sub     eax, edx
0x10026175  add     eax, [esi+4]
0x10026178  cmp     edi, eax
0x1002617a  ja      short loc_1002618F
0x1002617c  push    edi; Size
0x1002617d  push    ebx; Src
0x1002617e  push    edx; void *
0x1002617f  call    _memcpy
0x10026184  add     esp, 0Ch
0x10026187  add     [esi+8], edi
0x1002618a  mov     ecx, [esi+8]
0x1002618d  jmp     short loc_100261FA
0x1002618f  cmp     dword ptr [esi+5Ch], 1
0x10026193  jnz     short loc_100261DF
0x10026195  push    ecx; Size
0x10026196  push    ebx; Src
0x10026197  push    edx; void *
0x10026198  call    _memcpy
0x1002619d  mov     eax, [esi+8]
0x100261a0  add     esp, 0Ch
0x100261a3  add     eax, [ebp+var_4]
0x100261a6  mov     [esi+8], eax
0x100261a9  cmp     [esi+44h], eax
0x100261ac  jnb     short loc_100261B1
0x100261ae  mov     [esi+44h], eax
0x100261b1  mov     ecx, esi
0x100261b3  call    WriteFileBlock
0x100261b8  test    eax, eax
0x100261ba  js      short loc_10026226
0x100261bc  mov     ecx, [ebp+var_4]
0x100261bf  mov     eax, edi
0x100261c1  sub     eax, ecx
0x100261c3  cmp     eax, [esi+40h]
0x100261c6  ja      short loc_100261DA
0x100261c8  push    eax; Size
0x100261c9  lea     eax, [ecx+ebx]
0x100261cc  push    eax; Src
0x100261cd  push    dword ptr [esi+4]; void *
0x100261d0  call    _memcpy
0x100261d5  sub     edi, [ebp+var_4]
0x100261d8  jmp     short loc_100261EF
0x100261da  push    0FFFFFFFBh
0x100261dc  pop     eax
0x100261dd  jmp     short loc_10026226
0x100261df  sub     edx, [esi+4]
0x100261e2  add     [esi+54h], edx
0x100261e5  push    edi; Size
0x100261e6  push    ebx; Src
0x100261e7  push    dword ptr [esi+4]; void *
0x100261ea  call    _memcpy
0x100261ef  mov     ecx, [esi+4]
0x100261f2  add     esp, 0Ch
0x100261f5  add     ecx, edi
0x100261f7  mov     [esi+8], ecx
0x100261fa  sub     ecx, [esi+4]
0x100261fd  mov     eax, esi
0x100261ff  push    5Ch ; '\'
0x10026201  pop     edx
0x10026202  mov     dword ptr [esi+4Ch], 0
0x10026209  mov     dword ptr [edx+eax], 1
0x10026210  mov     eax, [esi]
0x10026212  mov     edx, [esi+54h]
0x10026215  add     eax, edx
0x10026217  cmp     eax, [esi+58h]
0x1002621a  jnz     short loc_10026222
0x1002621c  lea     eax, [ecx+edx]
0x1002621f  mov     [esi+58h], eax
0x10026222  mov     [esi], ecx
0x10026224  xor     eax, eax
0x10026226  pop     edi
0x10026227  pop     esi
0x10026228  pop     ebx
0x10026229  leave
0x1002622a  retn    4
```
