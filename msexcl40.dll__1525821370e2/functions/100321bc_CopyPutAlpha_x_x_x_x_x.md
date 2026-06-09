# CopyPutAlpha(x,x,x,x,x)

- ea: `0x100321bc`
- end: `0x1003226e`
- name: `_CopyPutAlpha@20`
- size: `178`
- prototype: `int __fastcall(int, int, int, char *, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1002c918`
- `0x1002cee0`
- `0x1002db68`

## callees

- `0x1002ec67`
- `0x10031f11`
- `0x10031fd9`
- `0x10032050`
- `0x100321bc`

## pseudocode

```c
int __fastcall CopyPutAlpha(int a1, int a2, int a3, char *a4, unsigned int a5)
{
  unsigned int v5; // edi
  char *i; // eax
  int CopyBufferNode; // eax
  _DWORD *v9; // esi
  _DWORD *v10; // ecx
  int v11; // eax

  v5 = a5 >> 1;
  for ( i = &a4[2 * (a5 >> 1) - 2]; i >= a4 && *(_WORD *)i == 32; i -= 2 )
    --v5;
  if ( !v5 )
  {
    CopyPutBlank(a3);
    return 0;
  }
  CopyBufferNode = AllocateCopyBufferNode();
  v9 = (_DWORD *)CopyBufferNode;
  if ( !CopyBufferNode )
    return -1011;
  *(_BYTE *)(CopyBufferNode + 4) = *(_BYTE *)(a2 + 28);
  *(_WORD *)(CopyBufferNode + 8) = 1040;
  *(_DWORD *)(CopyBufferNode + 12) = a3;
  v10 = *(_DWORD **)(*(_DWORD *)(*(_DWORD *)(a1 + 4) + 4) + 12);
  if ( !v10[3] )
    v10 = (_DWORD *)v10[2];
  v11 = TextStoragePut(v10[4], a4, v5, 1);
  v9[6] = v11;
  if ( v11 == -1 )
  {
    *v9 = dword_1003AE78;
    dword_1003AE78 = v9;
    return -1011;
  }
  AddCopyCell(a1, v9);
  return 0;
}

```

## disassembly

```asm
0x100321bc  mov     edi, edi
0x100321be  push    ebp
0x100321bf  mov     ebp, esp
0x100321c1  push    ecx
0x100321c2  push    ecx
0x100321c3  push    ebx
0x100321c4  mov     ebx, [ebp+arg_4]
0x100321c7  push    edi
0x100321c8  mov     edi, [ebp+arg_8]
0x100321cb  shr     edi, 1
0x100321cd  lea     eax, [ebx-2]
0x100321d0  mov     [ebp+var_8], edx
0x100321d3  mov     [ebp+var_4], ecx
0x100321d6  lea     eax, [eax+edi*2]
0x100321d9  jmp     short loc_100321E5
0x100321db  cmp     word ptr [eax], 20h ; ' '
0x100321df  jnz     short loc_100321E9
0x100321e1  dec     edi
0x100321e2  sub     eax, 2
0x100321e5  cmp     eax, ebx
0x100321e7  jnb     short loc_100321DB
0x100321e9  test    edi, edi
0x100321eb  jnz     short loc_100321F9
0x100321ed  push    [ebp+arg_0]
0x100321f0  call    _CopyPutBlank@12; CopyPutBlank(x,x,x)
0x100321f5  xor     eax, eax
0x100321f7  jmp     short loc_10032268
0x100321f9  push    esi
0x100321fa  call    AllocateCopyBufferNode
0x100321ff  mov     esi, eax
0x10032201  test    esi, esi
0x10032203  jz      short loc_10032254
0x10032205  mov     eax, [ebp+var_8]
0x10032208  mov     al, [eax+1Ch]
0x1003220b  mov     [esi+4], al
0x1003220e  mov     eax, 410h
0x10032213  mov     [esi+8], ax
0x10032217  mov     eax, [ebp+arg_0]
0x1003221a  mov     [esi+0Ch], eax
0x1003221d  mov     eax, [ebp+var_4]
0x10032220  mov     eax, [eax+4]
0x10032223  mov     eax, [eax+4]
0x10032226  mov     ecx, [eax+0Ch]
0x10032229  cmp     dword ptr [ecx+0Ch], 0
0x1003222d  jnz     short loc_10032232
0x1003222f  mov     ecx, [ecx+8]
0x10032232  mov     ecx, [ecx+10h]
0x10032235  mov     edx, ebx
0x10032237  push    1
0x10032239  push    edi
0x1003223a  call    _TextStoragePut@16; TextStoragePut(x,x,x,x)
0x1003223f  mov     [esi+18h], eax
0x10032242  cmp     eax, 0FFFFFFFFh
0x10032245  jnz     short loc_1003225B
0x10032247  mov     eax, dword_1003AE78
0x1003224c  mov     [esi], eax
0x1003224e  mov     dword_1003AE78, esi
0x10032254  mov     eax, 0FFFFFC0Dh
0x10032259  jmp     short loc_10032267
0x1003225b  mov     ecx, [ebp+var_4]
0x1003225e  mov     edx, esi
0x10032260  call    AddCopyCell
0x10032265  xor     eax, eax
0x10032267  pop     esi
0x10032268  pop     edi
0x10032269  pop     ebx
0x1003226a  leave
0x1003226b  retn    0Ch
```
