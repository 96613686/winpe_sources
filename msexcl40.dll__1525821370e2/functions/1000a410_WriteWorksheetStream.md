# WriteWorksheetStream

- ea: `0x1000a410`
- end: `0x1000a4c0`
- name: `WriteWorksheetStream`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1000a6a0`

## callees

- `0x1000a410`
- `0x1002580a`
- `0x1003669c`

## pseudocode

```c
int __fastcall WriteWorksheetStream(int a1, __int16 *a2, int a3)
{
  __int16 *v3; // esi
  unsigned int v4; // edx
  __int16 v5; // cx
  size_t v6; // edi
  _WORD *v7; // eax
  _WORD *v8; // ebx
  _DWORD *v9; // ecx
  unsigned int v11; // [esp+Ch] [ebp-10h]
  __int16 v13; // [esp+14h] [ebp-8h]
  __int16 v14; // [esp+18h] [ebp-4h]

  v3 = a2;
  v4 = (unsigned int)a2 + a3;
  v11 = v4;
  while ( 1 )
  {
    v14 = *v3;
    v5 = v3[1];
    v13 = v5;
    v6 = v5;
    if ( *v3 != 523 )
      break;
LABEL_10:
    if ( v14 != 10 )
    {
      v3 = (__int16 *)((char *)v3 + v6 + 4);
      if ( (unsigned int)v3 < v4 )
        continue;
    }
    return 0;
  }
  v7 = (_WORD *)MemAllocate(v5 + 11);
  v8 = v7;
  if ( v7 )
  {
    v7[2] = v14;
    v7[3] = v13;
    memcpy(v7 + 4, v3 + 2, v6);
    v9 = *(_DWORD **)(a1 + 4);
    if ( v9 )
    {
      while ( *v9 )
        v9 = (_DWORD *)*v9;
      *v9 = v8;
    }
    else
    {
      *(_DWORD *)(a1 + 4) = v8;
    }
    v4 = v11;
    goto LABEL_10;
  }
  return -2;
}

```

## disassembly

```asm
0x1000a410  mov     edi, edi
0x1000a412  push    ebp
0x1000a413  mov     ebp, esp
0x1000a415  sub     esp, 10h
0x1000a418  push    ebx
0x1000a419  push    esi
0x1000a41a  mov     esi, edx
0x1000a41c  mov     [ebp+var_C], ecx
0x1000a41f  mov     edx, [ebp+arg_0]
0x1000a422  mov     ebx, 20Bh
0x1000a427  add     edx, esi
0x1000a429  push    edi
0x1000a42a  mov     [ebp+var_10], edx
0x1000a42d  nop     dword ptr [eax]
0x1000a430  movzx   eax, word ptr [esi]
0x1000a433  mov     ecx, eax
0x1000a435  mov     [ebp+var_4], ecx
0x1000a438  movzx   ecx, word ptr [esi+2]
0x1000a43c  mov     [ebp+var_8], ecx
0x1000a43f  movsx   edi, cx
0x1000a442  cmp     ax, bx
0x1000a445  jz      short loc_1000A497
0x1000a447  lea     ecx, [edi+0Bh]
0x1000a44a  call    _MemAllocate@4; MemAllocate(x)
0x1000a44f  mov     ebx, eax
0x1000a451  test    ebx, ebx
0x1000a453  jz      short loc_1000A4B2
0x1000a455  mov     eax, [ebp+var_4]
0x1000a458  lea     ecx, [ebx+8]
0x1000a45b  mov     [ebx+4], ax
0x1000a45f  mov     eax, [ebp+var_8]
0x1000a462  mov     [ebx+6], ax
0x1000a466  lea     eax, [esi+4]
0x1000a469  push    edi; Size
0x1000a46a  push    eax; Src
0x1000a46b  push    ecx; void *
0x1000a46c  call    _memcpy
0x1000a471  mov     edx, [ebp+var_C]
0x1000a474  add     esp, 0Ch
0x1000a477  mov     ecx, [edx+4]
0x1000a47a  test    ecx, ecx
0x1000a47c  jnz     short loc_1000A483
0x1000a47e  mov     [edx+4], ebx
0x1000a481  jmp     short loc_1000A48F
0x1000a483  mov     eax, [ecx]
0x1000a485  test    eax, eax
0x1000a487  jz      short loc_1000A48D
0x1000a489  mov     ecx, eax
0x1000a48b  jmp     short loc_1000A483
0x1000a48d  mov     [ecx], ebx
0x1000a48f  mov     edx, [ebp+var_10]
0x1000a492  mov     ebx, 20Bh
0x1000a497  cmp     word ptr [ebp+var_4], 0Ah
0x1000a49c  jz      short loc_1000A4A7
0x1000a49e  add     esi, 4
0x1000a4a1  add     esi, edi
0x1000a4a3  cmp     esi, edx
0x1000a4a5  jb      short loc_1000A430
0x1000a4a7  pop     edi
0x1000a4a8  pop     esi
0x1000a4a9  xor     eax, eax
0x1000a4ab  pop     ebx
0x1000a4ac  mov     esp, ebp
0x1000a4ae  pop     ebp
0x1000a4af  retn    4
0x1000a4b2  pop     edi
0x1000a4b3  pop     esi
0x1000a4b4  mov     eax, 0FFFFFFFEh
0x1000a4b9  pop     ebx
0x1000a4ba  mov     esp, ebp
0x1000a4bc  pop     ebp
0x1000a4bd  retn    4
```
