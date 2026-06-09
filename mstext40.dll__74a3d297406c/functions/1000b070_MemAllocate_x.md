# MemAllocate(x)

- ea: `0x1000b070`
- end: `0x1000b1f8`
- name: `_MemAllocate@4`
- size: `392`
- prototype: `int __stdcall(size_t Size)`
- caller_count: `83`
- callee_count: `3`
- tags: ``

## callers

- `0x10009e50`
- `0x10009ea0`
- `0x10009f00`
- `0x10009f50`
- `0x10009fa0`
- `0x1000a3e0`
- `0x1000a8c0`
- `0x1000b310`
- `0x1000c150`
- `0x1000c370`
- `0x1000cbf0`
- `0x1000d1c0`
- `0x1000d2c0`
- `0x1000d7a0`
- `0x1000d8d0`
- `0x1000db20`
- `0x1000e3b0`
- `0x1000e950`
- `0x1000ed90`
- `0x10011870`
- `0x10011d90`
- `0x10013b30`
- `0x10013c80`
- `0x10013cd0`
- `0x10013d50`
- `0x10013de0`
- `0x10013e90`
- `0x10013ee0`
- `0x10013f40`
- `0x10013f90`
- `0x100161d0`
- `0x10016280`
- `0x10016300`
- `0x10016380`
- `0x10016400`
- `0x10016480`
- `0x10016500`
- `0x100165a0`
- `0x10016620`
- `0x100166e0`
- `0x10016760`
- `0x100167e0`
- `0x10016910`
- `0x100170e0`
- `0x100178b0`
- `0x10018200`
- `0x10018b90`
- `0x10019f20`
- `0x1001bff0`
- `0x1001c420`

## callees

- `0x1000aef0`
- `0x1000b070`
- `0x1002c490`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x1000b0f7`
- `KERNEL32!GlobalLock` at `0x1000b0f7`
- `KERNEL32!GlobalAlloc` at `0x1000b0ea`
- `KERNEL32!GlobalAlloc` at `0x1000b0d8`

## pseudocode

```c
_DWORD *__stdcall MemAllocate(int Size)
{
  _DWORD *v2; // ecx
  _DWORD *v3; // ebx
  int v4; // ebp
  _DWORD *v5; // esi
  _DWORD *v6; // edi
  int v7; // eax
  HGLOBAL v8; // eax
  HGLOBAL v9; // edi
  _DWORD *v10; // eax
  int v11; // ecx
  unsigned int v12; // eax

  if ( Size < 0 )
    return 0;
  v2 = 0;
  if ( !Size )
    return 0;
  if ( (unsigned int)Size > 0x1FE8 )
    return (_DWORD *)AllocateFromGlobalHeap(Size);
  v3 = (_DWORD *)dword_10040F6C;
  v4 = 12;
  if ( (unsigned int)(Size + 12) > 0xC )
    v4 = Size + 12;
  v5 = 0;
  v6 = 0;
  if ( dword_10040F6C )
  {
    do
    {
      v7 = v3[1];
      if ( v7 == v4 )
      {
        if ( v5 )
          v5[2] = v3[2];
        else
          dword_10040F6C = v3[2];
        memset(v3 + 3, 0, v4 - 12);
        *v3 = 2;
        return v3 + 3;
      }
      if ( v7 > v4 && !v6 )
      {
        v6 = v3;
        v2 = v5;
      }
      v5 = v3;
      v3 = (_DWORD *)v3[2];
    }
    while ( v3 );
    if ( !v6 )
      goto LABEL_15;
LABEL_27:
    v12 = v6[1] - v4;
    if ( v12 < 0xC )
    {
      if ( v2 )
        v2[2] = v6[2];
      else
        dword_10040F6C = v6[2];
LABEL_36:
      memset(v6 + 3, 0, v4 - 12);
      *v6 = 2;
      return v6 + 3;
    }
    if ( v6[1] <= 0x1FF4u )
    {
      *(_DWORD *)((char *)v6 + v4 + 4) = v12;
      *(_DWORD *)((char *)v6 + v4 + 8) = v6[2];
      if ( v2 )
        v2[2] = (char *)v6 + v4;
      else
        dword_10040F6C = (int)v6 + v4;
      v6[1] = v4;
      goto LABEL_36;
    }
  }
  else
  {
LABEL_15:
    while ( 1 )
    {
      v8 = GlobalAlloc(0x2002u, 0x2004u);
      v9 = v8;
      if ( !v8 )
        break;
      v10 = GlobalLock(v8);
      if ( !v10 )
        break;
      v11 = dword_10040F70;
      *v10 = v9;
      v10[1] = 0;
      v10[2] = v11;
      v10[3] = 0;
      if ( v11 )
        *(_DWORD *)(v11 + 12) = v10;
      v2 = 0;
      dword_10040F70 = (int)v10;
      v10[5] = 8180;
      v6 = v10 + 4;
      v10[6] = 0;
      if ( v5 )
      {
        v5[2] = v6;
        v2 = v5;
      }
      else
      {
        dword_10040F6C = (int)(v10 + 4);
      }
      if ( v10 != (_DWORD *)-16 )
        goto LABEL_27;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1000b070  mov     eax, [esp+Size]
0x1000b074  test    eax, eax
0x1000b076  jns     short loc_1000B07D
0x1000b078  xor     eax, eax
0x1000b07a  retn    4
0x1000b07d  xor     ecx, ecx
0x1000b07f  test    eax, eax
0x1000b081  jz      short loc_1000B078
0x1000b083  cmp     eax, 1FE8h
0x1000b088  jbe     short loc_1000B093
0x1000b08a  mov     [esp+Size], eax; Size
0x1000b08e  jmp     AllocateFromGlobalHeap
0x1000b093  push    ebx
0x1000b094  mov     ebx, dword_10040F6C
0x1000b09a  add     eax, 0Ch
0x1000b09d  push    ebp
0x1000b09e  mov     ebp, 0Ch
0x1000b0a3  cmp     eax, ebp
0x1000b0a5  push    esi
0x1000b0a6  cmova   ebp, eax
0x1000b0a9  xor     esi, esi
0x1000b0ab  push    edi
0x1000b0ac  xor     edi, edi
0x1000b0ae  test    ebx, ebx
0x1000b0b0  jz      short loc_1000B0D8
0x1000b0b2  mov     eax, [ebx+4]
0x1000b0b5  cmp     eax, ebp
0x1000b0b7  jz      loc_1000B149
0x1000b0bd  jle     short loc_1000B0C7
0x1000b0bf  test    edi, edi
0x1000b0c1  jnz     short loc_1000B0C7
0x1000b0c3  mov     edi, ebx
0x1000b0c5  mov     ecx, esi
0x1000b0c7  mov     esi, ebx
0x1000b0c9  mov     ebx, [ebx+8]
0x1000b0cc  test    ebx, ebx
0x1000b0ce  jnz     short loc_1000B0B2
0x1000b0d0  test    edi, edi
0x1000b0d2  jnz     loc_1000B188
0x1000b0d8  mov     ebx, ds:__imp__GlobalAlloc@8; GlobalAlloc(x,x)
0x1000b0de  mov     edi, edi
0x1000b0e0  push    2004h; dwBytes
0x1000b0e5  push    2002h; uFlags
0x1000b0ea  call    ebx ; GlobalAlloc(x,x); GlobalAlloc(x,x)
0x1000b0ec  mov     edi, eax
0x1000b0ee  test    edi, edi
0x1000b0f0  jz      loc_1000B1EF
0x1000b0f6  push    edi; hMem
0x1000b0f7  call    ds:__imp__GlobalLock@4; GlobalLock(x)
0x1000b0fd  test    eax, eax
0x1000b0ff  jz      loc_1000B1EF
0x1000b105  mov     ecx, dword_10040F70
0x1000b10b  mov     [eax], edi
0x1000b10d  mov     dword ptr [eax+4], 0
0x1000b114  mov     [eax+8], ecx
0x1000b117  mov     dword ptr [eax+0Ch], 0
0x1000b11e  test    ecx, ecx
0x1000b120  jz      short loc_1000B125
0x1000b122  mov     [ecx+0Ch], eax
0x1000b125  xor     ecx, ecx
0x1000b127  mov     dword_10040F70, eax
0x1000b12c  mov     dword ptr [eax+14h], 1FF4h
0x1000b133  lea     edi, [eax+10h]
0x1000b136  mov     dword ptr [eax+18h], 0
0x1000b13d  test    esi, esi
0x1000b13f  jnz     short loc_1000B17B
0x1000b141  mov     dword_10040F6C, edi
0x1000b147  jmp     short loc_1000B180
0x1000b149  mov     eax, [ebx+8]
0x1000b14c  test    esi, esi
0x1000b14e  jnz     short loc_1000B157
0x1000b150  mov     dword_10040F6C, eax
0x1000b155  jmp     short loc_1000B15A
0x1000b157  mov     [esi+8], eax
0x1000b15a  lea     ecx, [ebp-0Ch]
0x1000b15d  push    ecx; Size
0x1000b15e  lea     esi, [ebx+0Ch]
0x1000b161  push    0; Val
0x1000b163  push    esi; void *
0x1000b164  call    _memset
0x1000b169  add     esp, 0Ch
0x1000b16c  mov     dword ptr [ebx], 2
0x1000b172  mov     eax, esi
0x1000b174  pop     edi
0x1000b175  pop     esi
0x1000b176  pop     ebp
0x1000b177  pop     ebx
0x1000b178  retn    4
0x1000b17b  mov     [esi+8], edi
0x1000b17e  mov     ecx, esi
0x1000b180  test    edi, edi
0x1000b182  jz      loc_1000B0E0
0x1000b188  mov     edx, [edi+4]
0x1000b18b  mov     eax, edx
0x1000b18d  sub     eax, ebp
0x1000b18f  cmp     eax, 0Ch
0x1000b192  jnb     short loc_1000B1A7
0x1000b194  mov     eax, [edi+8]
0x1000b197  test    ecx, ecx
0x1000b199  jnz     short loc_1000B1A2
0x1000b19b  mov     dword_10040F6C, eax
0x1000b1a0  jmp     short loc_1000B1CE
0x1000b1a2  mov     [ecx+8], eax
0x1000b1a5  jmp     short loc_1000B1CE
0x1000b1a7  cmp     edx, 1FF4h
0x1000b1ad  ja      short loc_1000B1EF
0x1000b1af  mov     [edi+ebp+4], eax
0x1000b1b3  lea     edx, [edi+ebp]
0x1000b1b6  mov     eax, [edi+8]
0x1000b1b9  mov     [edx+8], eax
0x1000b1bc  test    ecx, ecx
0x1000b1be  jnz     short loc_1000B1C8
0x1000b1c0  mov     dword_10040F6C, edx
0x1000b1c6  jmp     short loc_1000B1CB
0x1000b1c8  mov     [ecx+8], edx
0x1000b1cb  mov     [edi+4], ebp
0x1000b1ce  lea     ecx, [ebp-0Ch]
0x1000b1d1  push    ecx; Size
0x1000b1d2  lea     esi, [edi+0Ch]
0x1000b1d5  push    0; Val
0x1000b1d7  push    esi; void *
0x1000b1d8  call    _memset
0x1000b1dd  add     esp, 0Ch
0x1000b1e0  mov     dword ptr [edi], 2
0x1000b1e6  mov     eax, esi
0x1000b1e8  pop     edi
0x1000b1e9  pop     esi
0x1000b1ea  pop     ebp
0x1000b1eb  pop     ebx
0x1000b1ec  retn    4
0x1000b1ef  pop     edi
0x1000b1f0  pop     esi
0x1000b1f1  pop     ebp
0x1000b1f2  xor     eax, eax
0x1000b1f4  pop     ebx
0x1000b1f5  retn    4
```
