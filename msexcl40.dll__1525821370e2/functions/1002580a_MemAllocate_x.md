# MemAllocate(x)

- ea: `0x1002580a`
- end: `0x10025980`
- name: `_MemAllocate@4`
- size: `374`
- prototype: `int __fastcall(signed int)`
- caller_count: `101`
- callee_count: `3`
- tags: ``

## callers

- `0x100066d0`
- `0x10006960`
- `0x10006bd0`
- `0x10007740`
- `0x10007a00`
- `0x10008210`
- `0x100082d0`
- `0x100088e0`
- `0x100092a0`
- `0x100094b0`
- `0x100098e0`
- `0x10009aa0`
- `0x1000a410`
- `0x1000a4d0`
- `0x1000a6a0`
- `0x1000ab50`
- `0x1000b350`
- `0x1000be60`
- `0x1000c030`
- `0x1000d030`
- `0x1000d590`
- `0x1000df70`
- `0x1000e590`
- `0x1000e600`
- `0x1000f040`
- `0x1000fdf0`
- `0x10010790`
- `0x10011280`
- `0x10011a70`
- `0x10012270`
- `0x10013490`
- `0x10014020`
- `0x10014c50`
- `0x10015090`
- `0x100158d0`
- `0x10015ed0`
- `0x10016680`
- `0x10016950`
- `0x10016f20`
- `0x10017110`
- `0x10017730`
- `0x10017790`
- `0x100181b0`
- `0x10018550`
- `0x10019d40`
- `0x1001a8d0`
- `0x1001a940`
- `0x1001aa40`
- `0x1001abf0`
- `0x1001b1e0`

## callees

- `0x100257b6`
- `0x1002580a`
- `0x10035f40`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1002587f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1002587f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x10025890`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x10025890`

## pseudocode

```c
int __fastcall MemAllocate(signed int a1)
{
  _DWORD *v1; // edx
  _DWORD *v3; // ebx
  unsigned int v4; // ecx
  int v5; // eax
  _DWORD *v6; // esi
  _DWORD *v7; // edi
  HGLOBAL v8; // eax
  HGLOBAL v9; // edi
  _DWORD *v10; // eax
  int v11; // ecx
  _DWORD *v12; // esi
  unsigned int v13; // esi
  size_t v14; // ecx
  char *v15; // ecx
  int v16; // [esp+Ch] [ebp-4h]

  if ( a1 < 0 )
    return 0;
  v1 = 0;
  if ( !a1 )
    return 0;
  if ( (unsigned int)a1 > 0x1FE8 )
    return AllocateFromGlobalHeap(a1);
  v3 = (_DWORD *)dword_1003AE64;
  v4 = a1 + 12;
  v5 = 12;
  if ( v4 > 0xC )
    v5 = v4;
  v6 = 0;
  v7 = 0;
  v16 = v5;
  if ( !dword_1003AE64 )
  {
LABEL_14:
    while ( 1 )
    {
      v8 = GlobalAlloc(0x2002u, 0x2004u);
      v9 = v8;
      if ( !v8 )
        return 0;
      v10 = GlobalLock(v8);
      if ( !v10 )
        return 0;
      v11 = dword_1003AE60;
      *v10 = v9;
      v10[1] = 0;
      v10[2] = v11;
      v10[3] = 0;
      if ( v11 )
        *(_DWORD *)(v11 + 12) = v10;
      dword_1003AE60 = (int)v10;
      v7 = v10 + 4;
      v10[5] = 8180;
      v1 = 0;
      v10[6] = 0;
      if ( v6 )
      {
        v6[2] = v7;
        v1 = v6;
      }
      else
      {
        dword_1003AE64 = (int)(v10 + 4);
      }
      if ( v10 != (_DWORD *)-16 )
      {
        v5 = v16;
        goto LABEL_28;
      }
    }
  }
  do
  {
    if ( v3[1] == v5 )
    {
      if ( v6 )
        v6[2] = v3[2];
      else
        dword_1003AE64 = v3[2];
      v12 = v3 + 3;
      memset(v3 + 3, 0, v5 - 12);
      *v3 = 2;
      return (int)v12;
    }
    if ( v3[1] > v5 && !v7 )
    {
      v7 = v3;
      v1 = v6;
    }
    v6 = v3;
    v3 = (_DWORD *)v3[2];
  }
  while ( v3 );
  if ( !v7 )
    goto LABEL_14;
LABEL_28:
  v13 = v7[1] - v5;
  if ( v13 < 0xC )
  {
    if ( v1 )
      v1[2] = v7[2];
    else
      dword_1003AE64 = v7[2];
    v14 = v5 - 12;
    goto LABEL_33;
  }
  if ( v7[1] > 0x1FF4u )
    return 0;
  v15 = (char *)v7 + v5;
  *((_DWORD *)v15 + 1) = v13;
  *((_DWORD *)v15 + 2) = v7[2];
  if ( v1 )
    v1[2] = v15;
  else
    dword_1003AE64 = (int)v7 + v5;
  v7[1] = v16;
  v14 = v16 - 12;
LABEL_33:
  v12 = v7 + 3;
  memset(v7 + 3, 0, v14);
  *v7 = 2;
  return (int)v12;
}

```

## disassembly

```asm
0x1002580a  mov     edi, edi
0x1002580c  push    ebp
0x1002580d  mov     ebp, esp
0x1002580f  push    ecx
0x10025810  push    ebx
0x10025811  push    esi
0x10025812  push    edi
0x10025813  test    ecx, ecx
0x10025815  js      loc_10025979
0x1002581b  xor     edx, edx
0x1002581d  test    ecx, ecx
0x1002581f  jz      loc_10025979
0x10025825  cmp     ecx, 1FE8h
0x1002582b  jbe     short loc_10025837
0x1002582d  call    AllocateFromGlobalHeap
0x10025832  jmp     loc_1002597B
0x10025837  mov     ebx, dword_1003AE64
0x1002583d  add     ecx, 0Ch
0x10025840  push    0Ch
0x10025842  pop     eax
0x10025843  cmp     ecx, eax
0x10025845  cmova   eax, ecx
0x10025848  xor     esi, esi
0x1002584a  xor     edi, edi
0x1002584c  mov     [ebp+var_4], eax
0x1002584f  test    ebx, ebx
0x10025851  jz      short loc_10025873
0x10025853  cmp     [ebx+4], eax
0x10025856  jz      short loc_100258D6
0x10025858  jle     short loc_10025862
0x1002585a  test    edi, edi
0x1002585c  jnz     short loc_10025862
0x1002585e  mov     edi, ebx
0x10025860  mov     edx, esi
0x10025862  mov     esi, ebx
0x10025864  mov     ebx, [ebx+8]
0x10025867  test    ebx, ebx
0x10025869  jnz     short loc_10025853
0x1002586b  test    edi, edi
0x1002586d  jnz     loc_10025916
0x10025873  xor     ebx, ebx
0x10025875  push    2004h; dwBytes
0x1002587a  push    2002h; uFlags
0x1002587f  call    ds:__imp__GlobalAlloc@8; GlobalAlloc(x,x)
0x10025885  mov     edi, eax
0x10025887  test    edi, edi
0x10025889  jz      loc_10025979
0x1002588f  push    edi; hMem
0x10025890  call    ds:__imp__GlobalLock@4; GlobalLock(x)
0x10025896  test    eax, eax
0x10025898  jz      loc_10025979
0x1002589e  mov     ecx, dword_1003AE60
0x100258a4  mov     [eax], edi
0x100258a6  mov     [eax+4], ebx
0x100258a9  mov     [eax+8], ecx
0x100258ac  mov     [eax+0Ch], ebx
0x100258af  test    ecx, ecx
0x100258b1  jz      short loc_100258B6
0x100258b3  mov     [ecx+0Ch], eax
0x100258b6  mov     dword_1003AE60, eax
0x100258bb  lea     edi, [eax+10h]
0x100258be  mov     dword ptr [eax+14h], 1FF4h
0x100258c5  mov     edx, ebx
0x100258c7  mov     [eax+18h], ebx
0x100258ca  test    esi, esi
0x100258cc  jnz     short loc_10025904
0x100258ce  mov     dword_1003AE64, edi
0x100258d4  jmp     short loc_10025909
0x100258d6  mov     ecx, [ebx+8]
0x100258d9  test    esi, esi
0x100258db  jnz     short loc_100258E5
0x100258dd  mov     dword_1003AE64, ecx
0x100258e3  jmp     short loc_100258E8
0x100258e5  mov     [esi+8], ecx
0x100258e8  lea     ecx, [eax-0Ch]
0x100258eb  push    ecx; Size
0x100258ec  lea     esi, [ebx+0Ch]
0x100258ef  push    0; Val
0x100258f1  push    esi; void *
0x100258f2  call    _memset
0x100258f7  mov     dword ptr [ebx], 2
0x100258fd  add     esp, 0Ch
0x10025900  mov     eax, esi
0x10025902  jmp     short loc_1002597B
0x10025904  mov     [esi+8], edi
0x10025907  mov     edx, esi
0x10025909  test    edi, edi
0x1002590b  jz      loc_10025875
0x10025911  mov     eax, [ebp+var_4]
0x10025914  jmp     short loc_10025918
0x10025916  xor     ebx, ebx
0x10025918  mov     esi, [edi+4]
0x1002591b  sub     esi, eax
0x1002591d  cmp     esi, 0Ch
0x10025920  jnb     short loc_1002594A
0x10025922  mov     ecx, [edi+8]
0x10025925  test    edx, edx
0x10025927  jnz     short loc_10025931
0x10025929  mov     dword_1003AE64, ecx
0x1002592f  jmp     short loc_10025934
0x10025931  mov     [edx+8], ecx
0x10025934  lea     ecx, [eax-0Ch]
0x10025937  push    ecx; Size
0x10025938  lea     esi, [edi+0Ch]
0x1002593b  push    ebx; Val
0x1002593c  push    esi; void *
0x1002593d  call    _memset
0x10025942  mov     dword ptr [edi], 2
0x10025948  jmp     short loc_100258FD
0x1002594a  cmp     dword ptr [edi+4], 1FF4h
0x10025951  ja      short loc_10025979
0x10025953  lea     ecx, [edi+eax]
0x10025956  mov     [ecx+4], esi
0x10025959  mov     eax, [edi+8]
0x1002595c  mov     [ecx+8], eax
0x1002595f  test    edx, edx
0x10025961  jnz     short loc_1002596B
0x10025963  mov     dword_1003AE64, ecx
0x10025969  jmp     short loc_1002596E
0x1002596b  mov     [edx+8], ecx
0x1002596e  mov     ecx, [ebp+var_4]
0x10025971  mov     [edi+4], ecx
0x10025974  add     ecx, 0FFFFFFF4h
0x10025977  jmp     short loc_10025937
0x10025979  xor     eax, eax
0x1002597b  pop     edi
0x1002597c  pop     esi
0x1002597d  pop     ebx
0x1002597e  leave
0x1002597f  retn
```
