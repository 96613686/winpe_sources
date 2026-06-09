# CopyBufferPutText(x,x,x,x)

- ea: `0x100167e0`
- end: `0x1001689a`
- name: `_CopyBufferPutText@16`
- size: `186`
- prototype: `int __stdcall(int, int, void *Src, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x10015cb0`

## callees

- `0x1000b070`
- `0x100167e0`
- `0x10016a10`
- `0x1002ba60`

## pseudocode

```c
int __stdcall CopyBufferPutText(int a1, int a2, const unsigned __int16 *Src, int a4)
{
  unsigned int v4; // esi
  _DWORD *v5; // eax
  _DWORD *v6; // edi
  _DWORD *v8; // ecx
  _DWORD *v9; // eax

  v4 = wcslen(Src);
  RemoveCopyItem(a1, a2);
  v5 = (_DWORD *)MemAllocate(0x220u);
  v6 = v5;
  if ( !v5 )
    return -1011;
  v5[1] = *(_DWORD *)(a2 + 24);
  v5[5] = a4;
  v5[2] = 10;
  v5[6] = v4;
  memcpy(v5 + 7, Src, 2 * v4);
  *((_WORD *)v6 + v4 + 14) = 0;
  v8 = 0;
  v9 = *(_DWORD **)(a1 + 68);
  if ( !v9 )
    goto LABEL_8;
  do
  {
    if ( v9[1] > v6[1] )
      break;
    v8 = v9;
    v9 = (_DWORD *)*v9;
  }
  while ( v9 );
  if ( v8 )
  {
    *v8 = v6;
    *v6 = v9;
    return 0;
  }
  else
  {
LABEL_8:
    *(_DWORD *)(a1 + 68) = v6;
    *v6 = v9;
    return 0;
  }
}

```

## disassembly

```asm
0x100167e0  push    ebx
0x100167e1  push    esi
0x100167e2  mov     esi, [esp+8+Src]
0x100167e6  push    edi
0x100167e7  lea     ecx, [esi+2]
0x100167ea  lea     ebx, [ebx+0]
0x100167f0  mov     ax, [esi]
0x100167f3  add     esi, 2
0x100167f6  test    ax, ax
0x100167f9  jnz     short loc_100167F0
0x100167fb  push    [esp+0Ch+arg_4]
0x100167ff  mov     ebx, [esp+10h+arg_0]
0x10016803  sub     esi, ecx
0x10016805  push    ebx
0x10016806  sar     esi, 1
0x10016808  call    RemoveCopyItem
0x1001680d  push    220h; Size
0x10016812  call    _MemAllocate@4; MemAllocate(x)
0x10016817  mov     edi, eax
0x10016819  test    edi, edi
0x1001681b  jnz     short loc_10016828
0x1001681d  pop     edi
0x1001681e  pop     esi
0x1001681f  mov     eax, 0FFFFFC0Dh
0x10016824  pop     ebx
0x10016825  retn    10h
0x10016828  mov     eax, [esp+0Ch+arg_4]
0x1001682c  mov     eax, [eax+18h]
0x1001682f  mov     [edi+4], eax
0x10016832  mov     eax, [esp+0Ch+arg_C]
0x10016836  mov     [edi+14h], eax
0x10016839  lea     eax, [esi+esi]
0x1001683c  push    eax; Size
0x1001683d  push    [esp+10h+Src]; Src
0x10016841  lea     eax, [edi+1Ch]
0x10016844  mov     dword ptr [edi+8], 0Ah
0x1001684b  push    eax; void *
0x1001684c  mov     [edi+18h], esi
0x1001684f  call    _memcpy
0x10016854  xor     eax, eax
0x10016856  add     esp, 0Ch
0x10016859  mov     [edi+esi*2+1Ch], ax
0x1001685e  xor     ecx, ecx
0x10016860  mov     eax, [ebx+44h]
0x10016863  test    eax, eax
0x10016865  jz      short loc_1001688D
0x10016867  mov     edx, [edi+4]
0x1001686a  lea     ebx, [ebx+0]
0x10016870  cmp     [eax+4], edx
0x10016873  ja      short loc_1001687D
0x10016875  mov     ecx, eax
0x10016877  mov     eax, [eax]
0x10016879  test    eax, eax
0x1001687b  jnz     short loc_10016870
0x1001687d  test    ecx, ecx
0x1001687f  jz      short loc_1001688D
0x10016881  mov     [ecx], edi
0x10016883  mov     [edi], eax
0x10016885  xor     eax, eax
0x10016887  pop     edi
0x10016888  pop     esi
0x10016889  pop     ebx
0x1001688a  retn    10h
0x1001688d  mov     [ebx+44h], edi
0x10016890  mov     [edi], eax
0x10016892  xor     eax, eax
0x10016894  pop     edi
0x10016895  pop     esi
0x10016896  pop     ebx
0x10016897  retn    10h
```
