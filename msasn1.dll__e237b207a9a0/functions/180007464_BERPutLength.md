# _BERPutLength

- ea: `0x180007464`
- end: `0x1800074cb`
- name: `_BERPutLength`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007380`
- `0x180007e40`

## callees

- `0x180007464`

## pseudocode

```c
__int64 __fastcall BERPutLength(__int64 a1, unsigned int a2, unsigned int a3)
{
  _BYTE *v3; // r9
  __int64 result; // rax
  unsigned int v5; // r8d
  unsigned int v6; // r8d

  v3 = *(_BYTE **)(a1 + 40);
  if ( a3 > 1 )
  {
    result = a3 + 127;
    *v3 = a3 + 127;
    v3 = (_BYTE *)++*(_QWORD *)(a1 + 40);
  }
  v5 = a3 - 3;
  if ( !v5 )
    goto LABEL_8;
  v6 = v5 - 1;
  if ( !v6 )
  {
LABEL_7:
    *v3 = BYTE2(a2);
    v3 = (_BYTE *)++*(_QWORD *)(a1 + 40);
LABEL_8:
    result = a2 >> 8;
    *v3 = BYTE1(a2);
    v3 = (_BYTE *)++*(_QWORD *)(a1 + 40);
    goto LABEL_6;
  }
  if ( v6 == 1 )
  {
    *v3 = HIBYTE(a2);
    v3 = (_BYTE *)++*(_QWORD *)(a1 + 40);
    goto LABEL_7;
  }
LABEL_6:
  *v3 = a2;
  ++*(_QWORD *)(a1 + 40);
  return result;
}

```

## disassembly

```asm
0x180007464  mov     r9, [rcx+28h]
0x180007468  cmp     r8d, 1
0x18000746c  jbe     short loc_18000747D
0x18000746e  lea     eax, [r8+7Fh]
0x180007472  mov     [r9], al
0x180007475  inc     qword ptr [rcx+28h]
0x180007479  mov     r9, [rcx+28h]
0x18000747d  sub     r8d, 3
0x180007481  jz      short loc_1800074A7
0x180007483  sub     r8d, 1
0x180007487  jz      short loc_180007497
0x180007489  cmp     r8d, 1
0x18000748d  jz      short loc_1800074B9
0x18000748f  mov     [r9], dl
0x180007492  inc     qword ptr [rcx+28h]
0x180007496  retn
0x180007497  mov     eax, edx
0x180007499  shr     eax, 10h
0x18000749c  mov     [r9], al
0x18000749f  inc     qword ptr [rcx+28h]
0x1800074a3  mov     r9, [rcx+28h]
0x1800074a7  mov     eax, edx
0x1800074a9  shr     eax, 8
0x1800074ac  mov     [r9], al
0x1800074af  inc     qword ptr [rcx+28h]
0x1800074b3  mov     r9, [rcx+28h]
0x1800074b7  jmp     short loc_18000748F
0x1800074b9  mov     eax, edx
0x1800074bb  shr     eax, 18h
0x1800074be  mov     [r9], al
0x1800074c1  inc     qword ptr [rcx+28h]
0x1800074c5  mov     r9, [rcx+28h]
0x1800074c9  jmp     short loc_180007497
```
