# BFCreateFile(x,x,x)

- ea: `0x1001d4b0`
- end: `0x1001d548`
- name: `_BFCreateFile@12`
- size: `152`
- prototype: `int __stdcall(LPCWSTR lpFileName, int, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1001ede0`
- `0x10025e40`

## callees

- `0x1000b070`
- `0x1000b200`
- `0x1000b3f0`
- `0x1001d4b0`
- `0x1001d9a0`

## pseudocode

```c
int __stdcall BFCreateFile(LPCWSTR lpFileName, __int16 a2, int *a3)
{
  int v3; // eax
  int v4; // esi
  int v6; // edi
  int v7; // eax

  v3 = MemAllocate(0x54u);
  v4 = v3;
  if ( !v3 )
    return -6;
  if ( (a2 & 0x100) != 0 )
    *(_DWORD *)(v3 + 12) = 1;
  v6 = OSCreateFile(lpFileName, v3);
  if ( v6 )
  {
    MemFree(v4);
    return v6;
  }
  else
  {
    v7 = MemAllocate(0xFDE8u);
    if ( v7 )
    {
      *(_DWORD *)(v4 + 4) = v7;
      *(_DWORD *)(v4 + 8) = v7;
      *(_DWORD *)(v4 + 52) = 65000;
      *(_DWORD *)(v4 + 72) = 0;
      *(_DWORD *)(v4 + 68) = 0;
      *(_DWORD *)v4 = 0;
      *a3 = v4;
      return 0;
    }
    else
    {
      DOSCloseFile(*(HANDLE *)(v4 + 20));
      MemFree(v4);
      return -6;
    }
  }
}

```

## disassembly

```asm
0x1001d4b0  push    esi
0x1001d4b1  push    54h ; 'T'; Size
0x1001d4b3  call    _MemAllocate@4; MemAllocate(x)
0x1001d4b8  mov     esi, eax
0x1001d4ba  test    esi, esi
0x1001d4bc  jnz     short loc_1001D4C5
0x1001d4be  lea     eax, [esi-6]
0x1001d4c1  pop     esi
0x1001d4c2  retn    0Ch
0x1001d4c5  test    [esp+4+arg_4], 100h
0x1001d4cd  jz      short loc_1001D4D6
0x1001d4cf  mov     dword ptr [esi+0Ch], 1
0x1001d4d6  push    edi
0x1001d4d7  push    esi; int
0x1001d4d8  push    [esp+0Ch+lpFileName]; lpFileName
0x1001d4dc  call    OSCreateFile
0x1001d4e1  mov     edi, eax
0x1001d4e3  test    edi, edi
0x1001d4e5  jz      short loc_1001D4F4
0x1001d4e7  push    esi
0x1001d4e8  call    _MemFree@4; MemFree(x)
0x1001d4ed  mov     eax, edi
0x1001d4ef  pop     edi
0x1001d4f0  pop     esi
0x1001d4f1  retn    0Ch
0x1001d4f4  push    0FDE8h; Size
0x1001d4f9  call    _MemAllocate@4; MemAllocate(x)
0x1001d4fe  test    eax, eax
0x1001d500  jnz     short loc_1001D51A
0x1001d502  push    dword ptr [esi+14h]; hObject
0x1001d505  call    _DOSCloseFile@4; DOSCloseFile(x)
0x1001d50a  push    esi
0x1001d50b  call    _MemFree@4; MemFree(x)
0x1001d510  pop     edi
0x1001d511  mov     eax, 0FFFFFFFAh
0x1001d516  pop     esi
0x1001d517  retn    0Ch
0x1001d51a  mov     [esi+4], eax
0x1001d51d  mov     [esi+8], eax
0x1001d520  mov     eax, [esp+8+arg_8]
0x1001d524  mov     dword ptr [esi+34h], 0FDE8h
0x1001d52b  mov     dword ptr [esi+48h], 0
0x1001d532  mov     dword ptr [esi+44h], 0
0x1001d539  mov     dword ptr [esi], 0
0x1001d53f  mov     [eax], esi
0x1001d541  xor     eax, eax
0x1001d543  pop     edi
0x1001d544  pop     esi
0x1001d545  retn    0Ch
```
