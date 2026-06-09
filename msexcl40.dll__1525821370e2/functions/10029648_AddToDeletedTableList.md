# AddToDeletedTableList

- ea: `0x10029648`
- end: `0x100296ca`
- name: `AddToDeletedTableList`
- size: `130`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x10029730`
- `0x10029b60`

## callees

- `0x10006400`
- `0x10025775`
- `0x1002580a`
- `0x10029648`

## pseudocode

```c
int __fastcall AddToDeletedTableList(int a1, int a2)
{
  _WORD *v3; // ebx
  _DWORD *v4; // esi
  int result; // eax
  _DWORD *v6; // edi
  int v7; // esi
  _DWORD *v10; // [esp+14h] [ebp-4h]

  v3 = (_WORD *)(a2 + 104);
  v4 = *(_DWORD **)(a1 + 52);
  if ( !v4 )
  {
    v10 = (_DWORD *)(a1 + 52);
LABEL_7:
    result = MemAllocate(524);
    v6 = (_DWORD *)result;
    if ( result )
    {
      v7 = *(_DWORD *)(a2 + 100);
      *(_DWORD *)(result + 4) = *(_DWORD *)(a2 + 96);
      *(_DWORD *)(result + 8) = v7;
      WCSCPY2((_WORD *)(result + 12), v3, 0x100u);
      *v6 = *v10;
      result = a1;
      *(_DWORD *)(a1 + 52) = v6;
    }
    return result;
  }
  do
  {
    result = DBlstrcmpi((int)(v4 + 3), (int)v3);
    if ( !result )
      break;
    v4 = (_DWORD *)*v4;
  }
  while ( v4 );
  if ( !v4 )
  {
    v10 = (_DWORD *)(a1 + 52);
    goto LABEL_7;
  }
  return result;
}

```

## disassembly

```asm
0x10029648  mov     edi, edi
0x1002964a  push    ebp
0x1002964b  mov     ebp, esp
0x1002964d  sub     esp, 0Ch
0x10029650  push    ebx
0x10029651  push    esi
0x10029652  push    edi
0x10029653  mov     edi, ecx
0x10029655  mov     [ebp+var_8], edx
0x10029658  mov     [ebp+var_C], edi
0x1002965b  lea     ebx, [edx+68h]
0x1002965e  lea     eax, [edi+34h]
0x10029661  mov     esi, [eax]
0x10029663  test    esi, esi
0x10029665  jz      short loc_10029687
0x10029667  lea     ecx, [esi+0Ch]
0x1002966a  mov     edx, ebx
0x1002966c  call    _DBlstrcmpi@8; DBlstrcmpi(x,x)
0x10029671  test    eax, eax
0x10029673  jz      short loc_1002967B
0x10029675  mov     esi, [esi]
0x10029677  test    esi, esi
0x10029679  jnz     short loc_10029667
0x1002967b  test    esi, esi
0x1002967d  jnz     short loc_100296C5
0x1002967f  lea     esi, [edi+34h]
0x10029682  mov     [ebp+var_4], esi
0x10029685  jmp     short loc_1002968A
0x10029687  mov     [ebp+var_4], eax
0x1002968a  mov     ecx, 20Ch
0x1002968f  call    _MemAllocate@4; MemAllocate(x)
0x10029694  mov     edi, eax
0x10029696  test    edi, edi
0x10029698  jz      short loc_100296C5
0x1002969a  mov     esi, [ebp+var_8]
0x1002969d  mov     edx, ebx
0x1002969f  push    100h
0x100296a4  mov     ecx, [esi+60h]
0x100296a7  mov     esi, [esi+64h]
0x100296aa  mov     [edi+4], ecx
0x100296ad  lea     ecx, [edi+0Ch]
0x100296b0  mov     [edi+8], esi
0x100296b3  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100296b8  mov     ecx, [ebp+var_4]
0x100296bb  mov     eax, [ecx]
0x100296bd  mov     [edi], eax
0x100296bf  mov     eax, [ebp+var_C]
0x100296c2  mov     [eax+34h], edi
0x100296c5  pop     edi
0x100296c6  pop     esi
0x100296c7  pop     ebx
0x100296c8  leave
0x100296c9  retn
```
