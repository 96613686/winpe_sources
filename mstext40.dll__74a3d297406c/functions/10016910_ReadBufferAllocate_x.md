# ReadBufferAllocate(x)

- ea: `0x10016910`
- end: `0x10016985`
- name: `_ReadBufferAllocate@4`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1000ed90`
- `0x10011060`

## callees

- `0x1000b070`
- `0x10016910`
- `0x1001f090`

## pseudocode

```c
int __stdcall ReadBufferAllocate(int a1)
{
  _DWORD *v1; // ebx
  _DWORD *v2; // edi
  _DWORD *v3; // esi
  _DWORD *v4; // eax

  v1 = 0;
  v2 = 0;
  v3 = *(_DWORD **)(*(_DWORD *)(a1 + 4) + 916);
  if ( v3 )
  {
    while ( 1 )
    {
      v4 = MemAllocate(*(&Size + v3[4]));
      if ( !v4 )
        break;
      v4[1] = v3[6];
      v4[2] = v3[4];
      *v4 = 0;
      if ( v2 )
        *v2 = v4;
      else
        v1 = v4;
      v3 = (_DWORD *)*v3;
      v2 = v4;
      if ( !v3 )
        goto LABEL_7;
    }
    TextDestroyDataList(v1);
    return -1011;
  }
  else
  {
LABEL_7:
    *(_DWORD *)(a1 + 72) = v1;
    return 0;
  }
}

```

## disassembly

```asm
0x10016910  push    ebx
0x10016911  push    ebp
0x10016912  mov     ebp, [esp+8+arg_0]
0x10016916  xor     ebx, ebx
0x10016918  push    esi
0x10016919  push    edi
0x1001691a  xor     edi, edi
0x1001691c  mov     eax, [ebp+4]
0x1001691f  mov     esi, [eax+394h]
0x10016925  test    esi, esi
0x10016927  jz      short loc_10016967
0x10016929  lea     esp, [esp+0]
0x10016930  mov     eax, [esi+10h]
0x10016933  push    Size[eax*4]; Size
0x1001693a  call    _MemAllocate@4; MemAllocate(x)
0x1001693f  test    eax, eax
0x10016941  jz      short loc_10016973
0x10016943  mov     ecx, [esi+18h]
0x10016946  mov     [eax+4], ecx
0x10016949  mov     ecx, [esi+10h]
0x1001694c  mov     [eax+8], ecx
0x1001694f  mov     dword ptr [eax], 0
0x10016955  test    edi, edi
0x10016957  jnz     short loc_1001695D
0x10016959  mov     ebx, eax
0x1001695b  jmp     short loc_1001695F
0x1001695d  mov     [edi], eax
0x1001695f  mov     esi, [esi]
0x10016961  mov     edi, eax
0x10016963  test    esi, esi
0x10016965  jnz     short loc_10016930
0x10016967  pop     edi
0x10016968  pop     esi
0x10016969  mov     [ebp+48h], ebx
0x1001696c  xor     eax, eax
0x1001696e  pop     ebp
0x1001696f  pop     ebx
0x10016970  retn    4
0x10016973  push    ebx
0x10016974  call    _TextDestroyDataList@4; TextDestroyDataList(x)
0x10016979  pop     edi
0x1001697a  pop     esi
0x1001697b  pop     ebp
0x1001697c  mov     eax, 0FFFFFC0Dh
0x10016981  pop     ebx
0x10016982  retn    4
```
