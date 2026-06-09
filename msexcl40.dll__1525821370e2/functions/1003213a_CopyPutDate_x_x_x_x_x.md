# CopyPutDate(x,x,x,x,x)

- ea: `0x1003213a`
- end: `0x100321b6`
- name: `_CopyPutDate@20`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1002c918`
- `0x1002cee0`

## callees

- `0x100320e5`
- `0x1003213a`

## pseudocode

```c
int __userpurge CopyPutDate@<eax>(int a1@<ecx>, double a2@<xmm3>, int a3)
{
  int v3; // eax
  int v4; // eax

  v3 = *(_DWORD *)(*(_DWORD *)(*(_DWORD *)(a1 + 4) + 4) + 12);
  if ( *(_DWORD *)(v3 + 28) == 1 )
  {
    a2 = a2 - 1462.0;
  }
  else if ( a2 >= 1.0 && a2 <= 60.0 )
  {
    a2 = a2 - 1.0;
  }
  if ( a2 < 0.0 || a2 >= 65381.0 && *(int *)(v3 + 4) < 8 )
    return -5017;
  v4 = PutDouble(a3);
  if ( !v4 )
    return -1011;
  *(_WORD *)(v4 + 8) |= 0x40u;
  return 0;
}

```

## disassembly

```asm
0x1003213a  mov     edi, edi
0x1003213c  push    ebp
0x1003213d  mov     ebp, esp
0x1003213f  mov     eax, [ecx+4]
0x10032142  mov     eax, [eax+4]
0x10032145  mov     eax, [eax+0Ch]
0x10032148  cmp     dword ptr [eax+1Ch], 1
0x1003214c  jnz     short loc_10032158
0x1003214e  subsd   xmm3, ds:__real@4096d80000000000
0x10032156  jmp     short loc_10032178
0x10032158  movsd   xmm1, ds:__real@3ff0000000000000
0x10032160  comisd  xmm3, xmm1
0x10032164  jb      short loc_10032178
0x10032166  movsd   xmm0, ds:__real@404e000000000000
0x1003216e  comisd  xmm0, xmm3
0x10032172  jb      short loc_10032178
0x10032174  subsd   xmm3, xmm1
0x10032178  xorps   xmm0, xmm0
0x1003217b  comisd  xmm0, xmm3
0x1003217f  ja      short loc_100321AD
0x10032181  comisd  xmm3, ds:__real@40efeca000000000
0x10032189  jb      short loc_10032191
0x1003218b  cmp     dword ptr [eax+4], 8
0x1003218f  jl      short loc_100321AD
0x10032191  push    [ebp+arg_0]
0x10032194  call    PutDouble
0x10032199  test    eax, eax
0x1003219b  jnz     short loc_100321A4
0x1003219d  mov     eax, 0FFFFFC0Dh
0x100321a2  jmp     short loc_100321B2
0x100321a4  or      word ptr [eax+8], 40h
0x100321a9  xor     eax, eax
0x100321ab  jmp     short loc_100321B2
0x100321ad  mov     eax, 0FFFFEC67h
0x100321b2  pop     ebp
0x100321b3  retn    4
```
