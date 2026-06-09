# ReadUntilEOF

- ea: `0x10008210`
- end: `0x100082ca`
- name: `ReadUntilEOF`
- size: `186`
- prototype: `int __fastcall(int, int, int *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x100082d0`
- `0x100094b0`

## callees

- `0x10008210`
- `0x1000dcc0`
- `0x1002580a`
- `0x10025ab7`
- `0x10025ed1`

## pseudocode

```c
int __fastcall ReadUntilEOF(int a1, int a2, int *a3, int *a4)
{
  int *v5; // eax
  _DWORD *v6; // esi
  int v7; // esi
  int v8; // edi
  int result; // eax
  int *v10; // eax
  int v11; // [esp+Ch] [ebp-Ch] BYREF
  int v12; // [esp+10h] [ebp-8h]
  int v13; // [esp+14h] [ebp-4h]

  v13 = a1;
  v5 = (int *)*a3;
  v6 = (_DWORD *)*a4;
  *a3 = *a4;
  *v5 = (int)v6;
  v7 = v12;
  while ( 1 )
  {
    if ( ExcelReadRecordHeader(a1, a2) )
      return 0;
    v8 = MemAllocate(*(__int16 *)(a2 + 2) + 11);
    if ( !v8 )
      break;
    *(_DWORD *)(v8 + 4) = *(_DWORD *)a2;
    v12 = BFReadFile(*(size_t **)(v13 + 20), (_BYTE *)(v8 + 8), *(__int16 *)(a2 + 2), &v11);
    if ( v12 )
    {
      MemFree(v8);
      result = dword_10001970[abs32(v12)];
      if ( result == -10 )
        result = -10;
      if ( result )
        return result;
    }
    else
    {
      v7 = v8;
    }
    a1 = v13;
    v10 = (int *)*a3;
    *a3 = v7;
    *v10 = v7;
    if ( *(_WORD *)a2 == 10 )
    {
      *a4 = v7;
      return 0;
    }
  }
  return -2;
}

```

## disassembly

```asm
0x10008210  mov     edi, edi
0x10008212  push    ebp
0x10008213  mov     ebp, esp
0x10008215  sub     esp, 0Ch
0x10008218  push    ebx
0x10008219  mov     ebx, edx
0x1000821b  mov     [ebp+var_4], ecx
0x1000821e  mov     edx, [ebp+arg_0]
0x10008221  push    esi
0x10008222  mov     esi, [ebp+arg_4]
0x10008225  push    edi
0x10008226  mov     eax, [edx]
0x10008228  mov     esi, [esi]
0x1000822a  mov     [edx], esi
0x1000822c  mov     [eax], esi
0x1000822e  mov     esi, [ebp+var_8]
0x10008231  mov     edx, ebx
0x10008233  call    _ExcelReadRecordHeader@8; ExcelReadRecordHeader(x,x)
0x10008238  test    eax, eax
0x1000823a  jnz     short loc_100082B1
0x1000823c  movsx   ecx, word ptr [ebx+2]
0x10008240  add     ecx, 0Bh
0x10008243  call    _MemAllocate@4; MemAllocate(x)
0x10008248  mov     edi, eax
0x1000824a  test    edi, edi
0x1000824c  jz      short loc_100082BC
0x1000824e  mov     ecx, [ebx]
0x10008250  lea     eax, [ebp+var_C]
0x10008253  mov     [edi+4], ecx
0x10008256  lea     edx, [edi+8]
0x10008259  movsx   ecx, word ptr [ebx+2]
0x1000825d  push    eax
0x1000825e  push    ecx
0x1000825f  mov     ecx, [ebp+var_4]
0x10008262  mov     ecx, [ecx+14h]
0x10008265  call    _BFReadFile@16; BFReadFile(x,x,x,x)
0x1000826a  mov     [ebp+var_8], eax
0x1000826d  test    eax, eax
0x1000826f  jz      short loc_10008298
0x10008271  mov     ecx, edi
0x10008273  call    _MemFree@4; MemFree(x)
0x10008278  mov     eax, [ebp+var_8]
0x1000827b  mov     ecx, 0FFFFFFF6h
0x10008280  cdq
0x10008281  xor     eax, edx
0x10008283  sub     eax, edx
0x10008285  mov     eax, ds:dword_10001970[eax*4]
0x1000828c  cmp     eax, 0FFFFFFF6h
0x1000828f  cmovz   eax, ecx
0x10008292  test    eax, eax
0x10008294  jnz     short loc_100082B3
0x10008296  jmp     short loc_1000829A
0x10008298  mov     esi, edi
0x1000829a  mov     edi, [ebp+arg_0]
0x1000829d  mov     ecx, [ebp+var_4]
0x100082a0  mov     eax, [edi]
0x100082a2  mov     [edi], esi
0x100082a4  mov     [eax], esi
0x100082a6  cmp     word ptr [ebx], 0Ah
0x100082aa  jnz     short loc_10008231
0x100082ac  mov     eax, [ebp+arg_4]
0x100082af  mov     [eax], esi
0x100082b1  xor     eax, eax
0x100082b3  pop     edi
0x100082b4  pop     esi
0x100082b5  pop     ebx
0x100082b6  mov     esp, ebp
0x100082b8  pop     ebp
0x100082b9  retn    8
0x100082bc  pop     edi
0x100082bd  pop     esi
0x100082be  mov     eax, 0FFFFFFFEh
0x100082c3  pop     ebx
0x100082c4  mov     esp, ebp
0x100082c6  pop     ebp
0x100082c7  retn    8
```
