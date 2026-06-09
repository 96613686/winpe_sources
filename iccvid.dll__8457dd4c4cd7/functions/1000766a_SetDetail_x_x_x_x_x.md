# SetDetail(x,x,x,x,x)

- ea: `0x1000766a`
- end: `0x100076e6`
- name: `_SetDetail@20`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x100077a0`
- `0x10007aa0`

## callees

- `0x10004100`
- `0x1000766a`

## pseudocode

```c
int __fastcall SetDetail(unsigned int a1, int a2, int a3, int a4, int a5)
{
  int v5; // eax
  int v6; // eax
  int v8; // [esp-4h] [ebp-10h]

  v5 = a4 + 5;
  if ( a4 <= 0 )
    v5 = 5;
  v8 = v5;
  v6 = 0;
  if ( a4 <= 0 )
    v6 = a4;
  if ( !IsWriteRangeInBuffer(a1, a3, a2, v6, v8) )
    return 0;
  if ( (a3 & 2) != 0 )
  {
    *(_WORD *)a3 = *(_WORD *)a5;
    *(_DWORD *)(a3 + 2) = *(_DWORD *)(a5 + 4);
    *(_WORD *)(a3 + a4) = *(_WORD *)(a5 + 8);
    *(_DWORD *)(a3 + a4 + 2) = *(_DWORD *)(a5 + 12);
  }
  else
  {
    *(_DWORD *)a3 = *(_DWORD *)a5;
    *(_WORD *)(a3 + 4) = *(_WORD *)(a5 + 6);
    *(_DWORD *)(a3 + a4) = *(_DWORD *)(a5 + 8);
    *(_WORD *)(a3 + a4 + 4) = *(_WORD *)(a5 + 14);
  }
  return 1;
}

```

## disassembly

```asm
0x1000766a  mov     edi, edi
0x1000766c  push    ebp
0x1000766d  mov     ebp, esp
0x1000766f  push    ebx
0x10007670  mov     ebx, [ebp+arg_0]
0x10007673  push    esi
0x10007674  mov     esi, [ebp+arg_4]
0x10007677  test    esi, esi
0x10007679  push    edi
0x1000767a  push    5
0x1000767c  pop     edi
0x1000767d  lea     eax, [esi+5]
0x10007680  cmovle  eax, edi
0x10007683  push    eax
0x10007684  xor     eax, eax
0x10007686  test    esi, esi
0x10007688  cmovle  eax, esi
0x1000768b  push    eax
0x1000768c  push    edx
0x1000768d  mov     edx, ebx
0x1000768f  call    _IsWriteRangeInBuffer@20; IsWriteRangeInBuffer(x,x,x,x,x)
0x10007694  test    eax, eax
0x10007696  jz      short loc_100076DD
0x10007698  mov     ecx, [ebp+arg_8]
0x1000769b  test    bl, 2
0x1000769e  jz      short loc_100076BD
0x100076a0  mov     ax, [ecx]
0x100076a3  mov     [ebx], ax
0x100076a6  mov     eax, [ecx+4]
0x100076a9  mov     [ebx+2], eax
0x100076ac  mov     ax, [ecx+8]
0x100076b0  mov     [ebx+esi], ax
0x100076b4  mov     eax, [ecx+0Ch]
0x100076b7  mov     [ebx+esi+2], eax
0x100076bb  jmp     short loc_100076D8
0x100076bd  mov     eax, [ecx]
0x100076bf  mov     [ebx], eax
0x100076c1  mov     ax, [ecx+6]
0x100076c5  mov     [ebx+4], ax
0x100076c9  mov     eax, [ecx+8]
0x100076cc  mov     [ebx+esi], eax
0x100076cf  mov     ax, [ecx+0Eh]
0x100076d3  mov     [ebx+esi+4], ax
0x100076d8  xor     eax, eax
0x100076da  inc     eax
0x100076db  jmp     short loc_100076DF
0x100076dd  xor     eax, eax
0x100076df  pop     edi
0x100076e0  pop     esi
0x100076e1  pop     ebx
0x100076e2  pop     ebp
0x100076e3  retn    0Ch
```
