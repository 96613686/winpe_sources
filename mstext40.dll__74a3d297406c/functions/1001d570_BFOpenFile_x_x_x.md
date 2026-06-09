# BFOpenFile(x,x,x)

- ea: `0x1001d570`
- end: `0x1001d692`
- name: `_BFOpenFile@12`
- size: `290`
- prototype: `int __stdcall(LPCWSTR lpFileName, int, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1001ff80`
- `0x10026190`

## callees

- `0x1000b070`
- `0x1000b200`
- `0x1000b3f0`
- `0x1000b470`
- `0x1000b830`
- `0x1000b9b0`
- `0x1000ba90`
- `0x1001d570`

## pseudocode

```c
int __stdcall BFOpenFile(LPCWSTR lpFileName, __int16 a2, _DWORD *a3)
{
  int v3; // eax
  _DWORD *v4; // esi
  bool v6; // zf
  HANDLE *v7; // edi
  int v8; // eax
  int v9; // ebx
  int v10; // eax

  v3 = MemAllocate(0x54u);
  v4 = (_DWORD *)v3;
  if ( !v3 )
    return -6;
  DOSFileDateTime(lpFileName, 2, v3 + 28, v3 + 32, v3 + 36, v3 + 40, v3 + 44, v3 + 48);
  if ( (a2 & 0x100) != 0 )
    v4[3] = 1;
  v6 = v4[3] == 0;
  v4[4] = (unsigned __int8)a2;
  if ( !v6 )
  {
    v9 = -4;
LABEL_19:
    MemFree(v4);
    return v9;
  }
  v7 = (HANDLE *)(v4 + 5);
  v8 = DOSOpenFile(lpFileName, (unsigned __int8)a2, (int)(v4 + 5));
  if ( v8 )
  {
    if ( v8 == -4 )
      v9 = -1;
    else
      v9 = v8 == -2 ? -4 : (v8 != -3) - 3;
    if ( v9 )
      goto LABEL_19;
  }
  v10 = MemAllocate(0xFDE8u);
  if ( v10 )
  {
    v6 = v4[3] == 0;
    v4[1] = v10;
    v4[13] = 65000;
    v4[18] = 0;
    v4[17] = 0;
    *v4 = 0;
    v4[2] = v10;
    if ( v6 )
    {
      DOSSetFilePosition(*v7, 2u, 0);
      DOSGetFilePosition(*v7, v4 + 19);
      DOSSetFilePosition(*v7, 0, 0);
    }
    *a3 = v4;
    return 0;
  }
  else
  {
    DOSCloseFile(*v7);
    MemFree(v4);
    return -6;
  }
}

```

## disassembly

```asm
0x1001d570  push    esi
0x1001d571  push    54h ; 'T'; Size
0x1001d573  call    _MemAllocate@4; MemAllocate(x)
0x1001d578  mov     esi, eax
0x1001d57a  test    esi, esi
0x1001d57c  jnz     short loc_1001D585
0x1001d57e  lea     eax, [esi-6]
0x1001d581  pop     esi
0x1001d582  retn    0Ch
0x1001d585  push    ebx
0x1001d586  mov     ebx, [esp+8+lpFileName]
0x1001d58a  lea     eax, [esi+30h]
0x1001d58d  push    eax
0x1001d58e  lea     eax, [esi+2Ch]
0x1001d591  push    eax
0x1001d592  lea     eax, [esi+28h]
0x1001d595  push    eax
0x1001d596  lea     eax, [esi+24h]
0x1001d599  push    eax
0x1001d59a  lea     eax, [esi+20h]
0x1001d59d  push    eax
0x1001d59e  lea     eax, [esi+1Ch]
0x1001d5a1  push    eax
0x1001d5a2  push    2
0x1001d5a4  push    ebx
0x1001d5a5  call    _DOSFileDateTime@32; DOSFileDateTime(x,x,x,x,x,x,x,x)
0x1001d5aa  mov     eax, [esp+8+arg_4]
0x1001d5ae  test    eax, 100h
0x1001d5b3  jz      short loc_1001D5BC
0x1001d5b5  mov     dword ptr [esi+0Ch], 1
0x1001d5bc  cmp     dword ptr [esi+0Ch], 0
0x1001d5c0  movzx   eax, al
0x1001d5c3  push    edi
0x1001d5c4  mov     [esi+10h], eax
0x1001d5c7  jnz     loc_1001D67F
0x1001d5cd  lea     edi, [esi+14h]
0x1001d5d0  push    edi; int
0x1001d5d1  push    eax; int
0x1001d5d2  push    ebx; lpFileName
0x1001d5d3  call    _DOSOpenFile@12; DOSOpenFile(x,x,x)
0x1001d5d8  test    eax, eax
0x1001d5da  jz      short loc_1001D603
0x1001d5dc  cmp     eax, 0FFFFFFFCh
0x1001d5df  jnz     short loc_1001D5E6
0x1001d5e1  or      ebx, 0FFFFFFFFh
0x1001d5e4  jmp     short loc_1001D5FB
0x1001d5e6  cmp     eax, 0FFFFFFFEh
0x1001d5e9  jnz     short loc_1001D5F0
0x1001d5eb  lea     ebx, [eax-2]
0x1001d5ee  jmp     short loc_1001D5FB
0x1001d5f0  xor     ebx, ebx
0x1001d5f2  cmp     eax, 0FFFFFFFDh
0x1001d5f5  setnz   bl
0x1001d5f8  add     ebx, 0FFFFFFFDh
0x1001d5fb  test    ebx, ebx
0x1001d5fd  jnz     loc_1001D684
0x1001d603  push    0FDE8h; Size
0x1001d608  call    _MemAllocate@4; MemAllocate(x)
0x1001d60d  test    eax, eax
0x1001d60f  jnz     short loc_1001D629
0x1001d611  push    dword ptr [edi]; hObject
0x1001d613  call    _DOSCloseFile@4; DOSCloseFile(x)
0x1001d618  push    esi
0x1001d619  call    _MemFree@4; MemFree(x)
0x1001d61e  pop     edi
0x1001d61f  pop     ebx
0x1001d620  mov     eax, 0FFFFFFFAh
0x1001d625  pop     esi
0x1001d626  retn    0Ch
0x1001d629  cmp     dword ptr [esi+0Ch], 0
0x1001d62d  mov     [esi+4], eax
0x1001d630  mov     dword ptr [esi+34h], 0FDE8h
0x1001d637  mov     dword ptr [esi+48h], 0
0x1001d63e  mov     dword ptr [esi+44h], 0
0x1001d645  mov     dword ptr [esi], 0
0x1001d64b  mov     [esi+8], eax
0x1001d64e  jnz     short loc_1001D671
0x1001d650  push    0; lDistanceToMove
0x1001d652  push    2; dwMoveMethod
0x1001d654  push    dword ptr [edi]; hFile
0x1001d656  call    _DOSSetFilePosition@12; DOSSetFilePosition(x,x,x)
0x1001d65b  lea     eax, [esi+4Ch]
0x1001d65e  push    eax; int
0x1001d65f  push    dword ptr [edi]; hFile
0x1001d661  call    _DOSGetFilePosition@8; DOSGetFilePosition(x,x)
0x1001d666  push    0; lDistanceToMove
0x1001d668  push    0; dwMoveMethod
0x1001d66a  push    dword ptr [edi]; hFile
0x1001d66c  call    _DOSSetFilePosition@12; DOSSetFilePosition(x,x,x)
0x1001d671  mov     eax, [esp+0Ch+arg_8]
0x1001d675  pop     edi
0x1001d676  pop     ebx
0x1001d677  mov     [eax], esi
0x1001d679  xor     eax, eax
0x1001d67b  pop     esi
0x1001d67c  retn    0Ch
0x1001d67f  mov     ebx, 0FFFFFFFCh
0x1001d684  push    esi
0x1001d685  call    _MemFree@4; MemFree(x)
0x1001d68a  pop     edi
0x1001d68b  mov     eax, ebx
0x1001d68d  pop     ebx
0x1001d68e  pop     esi
0x1001d68f  retn    0Ch
```
