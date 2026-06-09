# CompressBegin(x,x,x)

- ea: `0x1000fbcc`
- end: `0x1000fc91`
- name: `_CompressBegin@12`
- size: `197`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x100093a0`
- `0x1000fc97`

## callees

- `0x10004695`
- `0x1000f82f`
- `0x1000fa28`
- `0x1000fbcc`
- `0x1000fdf3`

## pseudocode

```c
int __fastcall CompressBegin(int a1, __int16 *a2, int a3)
{
  int result; // eax
  __int16 v6; // cx
  int v7; // esi
  unsigned int v8; // esi
  bool v9; // zf
  int v10; // eax
  HLOCAL v11; // eax
  __int16 v12; // [esp-8h] [ebp-14h]

  result = CompressQuery(a3);
  if ( !result )
  {
    if ( !a1 )
      return -2;
    if ( *(_BYTE *)(a1 + 4) )
      CompressEnd(a1);
    v6 = 0;
    v7 = a2[2] * a2[7];
    *(_DWORD *)(a1 + 28) = -2;
    v8 = ((unsigned int)(v7 + 31) >> 3) & 0x1FFFFFFC;
    v9 = *(_BYTE *)(a1 + 5) == 0;
    *(_DWORD *)(a1 + 24) = v8;
    if ( !v9 )
      v6 = 4;
    v12 = CompressFlags & 0xFFFB | v6;
    v10 = DecompressedDibType(a2);
    v11 = CVCompressBegin(a2[2], a2[4], -v8, v10, (int)(a2 + 16), a1 + 44, a1 + 80, v12);
    *(_DWORD *)(a1 + 8) = v11;
    if ( !v11 )
      return -3;
    *(_DWORD *)(a1 + 16) = *((_DWORD *)a2 + 1);
    *(_DWORD *)(a1 + 20) = *((_DWORD *)a2 + 2);
    result = 0;
    *(_BYTE *)(a1 + 4) = 1;
  }
  return result;
}

```

## disassembly

```asm
0x1000fbcc  mov     edi, edi
0x1000fbce  push    ebp
0x1000fbcf  mov     ebp, esp
0x1000fbd1  push    ecx
0x1000fbd2  push    ebx
0x1000fbd3  push    edi
0x1000fbd4  push    [ebp+arg_0]
0x1000fbd7  mov     ebx, edx
0x1000fbd9  mov     edi, ecx
0x1000fbdb  call    _CompressQuery@12; CompressQuery(x,x,x)
0x1000fbe0  test    eax, eax
0x1000fbe2  jnz     loc_1000FC8B
0x1000fbe8  test    edi, edi
0x1000fbea  jnz     short loc_1000FBF4
0x1000fbec  push    0FFFFFFFEh
0x1000fbee  pop     eax
0x1000fbef  jmp     loc_1000FC8B
0x1000fbf4  cmp     byte ptr [edi+4], 0
0x1000fbf8  jz      short loc_1000FC01
0x1000fbfa  mov     ecx, edi
0x1000fbfc  call    _CompressEnd@4; CompressEnd(x)
0x1000fc01  movsx   eax, word ptr [ebx+4]
0x1000fc05  xor     ecx, ecx
0x1000fc07  push    esi
0x1000fc08  movsx   esi, word ptr [ebx+0Eh]
0x1000fc0c  mov     edx, 0FFFBh
0x1000fc11  imul    esi, eax
0x1000fc14  push    4
0x1000fc16  pop     eax
0x1000fc17  mov     dword ptr [edi+1Ch], 0FFFFFFFEh
0x1000fc1e  add     esi, 1Fh
0x1000fc21  shr     esi, 3
0x1000fc24  and     esi, 1FFFFFFCh
0x1000fc2a  cmp     [edi+5], cl
0x1000fc2d  mov     [edi+18h], esi
0x1000fc30  cmovnz  ecx, eax
0x1000fc33  mov     ax, _CompressFlags
0x1000fc39  and     ax, dx
0x1000fc3c  or      cx, ax
0x1000fc3f  lea     eax, [edi+50h]
0x1000fc42  mov     word ptr [ebp+var_4], cx
0x1000fc46  mov     ecx, ebx
0x1000fc48  push    [ebp+var_4]
0x1000fc4b  push    eax
0x1000fc4c  lea     eax, [edi+2Ch]
0x1000fc4f  push    eax
0x1000fc50  lea     eax, [ebx+20h]
0x1000fc53  push    eax
0x1000fc54  call    _DecompressedDibType@4; DecompressedDibType(x)
0x1000fc59  mov     dx, [ebx+8]
0x1000fc5d  neg     esi
0x1000fc5f  mov     cx, [ebx+4]
0x1000fc63  push    eax
0x1000fc64  push    esi
0x1000fc65  call    _CVCompressBegin@32; CVCompressBegin(x,x,x,x,x,x,x,x)
0x1000fc6a  mov     [edi+8], eax
0x1000fc6d  pop     esi
0x1000fc6e  test    eax, eax
0x1000fc70  jnz     short loc_1000FC79
0x1000fc72  push    0FFFFFFFDh
0x1000fc74  jmp     loc_1000FBEE
0x1000fc79  mov     eax, [ebx+4]
0x1000fc7c  mov     [edi+10h], eax
0x1000fc7f  mov     eax, [ebx+8]
0x1000fc82  mov     [edi+14h], eax
0x1000fc85  xor     eax, eax
0x1000fc87  mov     byte ptr [edi+4], 1
0x1000fc8b  pop     edi
0x1000fc8c  pop     ebx
0x1000fc8d  leave
0x1000fc8e  retn    4
```
