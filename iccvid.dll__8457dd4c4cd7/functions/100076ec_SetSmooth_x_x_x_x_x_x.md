# SetSmooth(x,x,x,x,x,x)

- ea: `0x100076ec`
- end: `0x10007794`
- name: `_SetSmooth@24`
- size: `168`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x100077a0`
- `0x100079b0`
- `0x10007aa0`

## callees

- `0x10004100`
- `0x100076ec`

## pseudocode

```c
int __fastcall SetSmooth(unsigned int a1, int a2, int *a3, int a4, int a5, int *a6)
{
  int v6; // eax
  int v7; // ecx
  _DWORD *v8; // esi
  int v9; // eax
  int v10; // ecx
  unsigned int v11; // eax
  unsigned int v12; // eax
  int v13; // eax
  int v14; // ecx
  unsigned int v15; // eax
  unsigned int v16; // eax

  if ( a4 <= 0 || a5 <= 0 )
  {
    v6 = a4 + a5;
    v7 = 11;
  }
  else
  {
    v6 = 0;
    v7 = a4 + a5 + 11;
  }
  if ( !IsWriteRangeInBuffer(a1, (int)a3, a2, v6, v7) )
    return 0;
  v8 = (int *)((char *)a3 + a4);
  v9 = *a6;
  *a3 = *a6;
  *v8 = v9;
  v10 = a6[1];
  a3[2] = v10;
  v11 = *(int *)((char *)a3 + a4);
  v8[2] = v10;
  v12 = ((v10 & 0xFFFFFF00) << 8) | (unsigned __int16)(v11 >> 8);
  a3[1] = v12;
  v8[1] = v12;
  v13 = a6[2];
  *(int *)((char *)a3 + a5) = v13;
  *(_DWORD *)((char *)v8 + a5) = v13;
  v14 = a6[3];
  *(int *)((char *)a3 + a5 + 8) = v14;
  v15 = *(int *)((char *)a3 + a4 + a5);
  *(_DWORD *)((char *)v8 + a5 + 8) = v14;
  v16 = ((v14 & 0xFFFFFF00) << 8) | (unsigned __int16)(v15 >> 8);
  *(int *)((char *)a3 + a5 + 4) = v16;
  *(_DWORD *)((char *)v8 + a5 + 4) = v16;
  return 1;
}

```

## disassembly

```asm
0x100076ec  mov     edi, edi
0x100076ee  push    ebp
0x100076ef  mov     ebp, esp
0x100076f1  push    ecx
0x100076f2  push    ebx
0x100076f3  push    esi
0x100076f4  mov     esi, [ebp+arg_4]
0x100076f7  mov     [ebp+var_4], ecx
0x100076fa  push    edi
0x100076fb  mov     edi, [ebp+arg_8]
0x100076fe  test    esi, esi
0x10007700  jle     short loc_1000770F
0x10007702  test    edi, edi
0x10007704  jle     short loc_1000770F
0x10007706  lea     ecx, [edi+0Bh]
0x10007709  xor     eax, eax
0x1000770b  add     ecx, esi
0x1000770d  jmp     short loc_10007715
0x1000770f  push    0Bh
0x10007711  lea     eax, [esi+edi]
0x10007714  pop     ecx
0x10007715  mov     ebx, [ebp+arg_0]
0x10007718  push    ecx
0x10007719  mov     ecx, [ebp+var_4]
0x1000771c  push    eax
0x1000771d  push    edx
0x1000771e  mov     edx, ebx
0x10007720  call    _IsWriteRangeInBuffer@20; IsWriteRangeInBuffer(x,x,x,x,x)
0x10007725  test    eax, eax
0x10007727  jz      short loc_1000778B
0x10007729  mov     edx, [ebp+arg_C]
0x1000772c  add     esi, ebx
0x1000772e  mov     eax, [edx]
0x10007730  mov     [ebx], eax
0x10007732  mov     [esi], eax
0x10007734  mov     ecx, [edx+4]
0x10007737  mov     [ebx+8], ecx
0x1000773a  mov     eax, [esi]
0x1000773c  mov     [esi+8], ecx
0x1000773f  and     ecx, 0FFFFFF00h
0x10007745  shr     eax, 8
0x10007748  movzx   eax, ax
0x1000774b  shl     ecx, 8
0x1000774e  or      eax, ecx
0x10007750  mov     [ebx+4], eax
0x10007753  mov     [esi+4], eax
0x10007756  mov     eax, [edx+8]
0x10007759  mov     [ebx+edi], eax
0x1000775c  mov     [esi+edi], eax
0x1000775f  mov     ecx, [edx+0Ch]
0x10007762  mov     [ebx+edi+8], ecx
0x10007766  mov     eax, [esi+edi]
0x10007769  mov     [esi+edi+8], ecx
0x1000776d  and     ecx, 0FFFFFF00h
0x10007773  shr     eax, 8
0x10007776  movzx   eax, ax
0x10007779  shl     ecx, 8
0x1000777c  or      eax, ecx
0x1000777e  mov     [ebx+edi+4], eax
0x10007782  mov     [esi+edi+4], eax
0x10007786  xor     eax, eax
0x10007788  inc     eax
0x10007789  jmp     short loc_1000778D
0x1000778b  xor     eax, eax
0x1000778d  pop     edi
0x1000778e  pop     esi
0x1000778f  pop     ebx
0x10007790  leave
0x10007791  retn    10h
```
