# TextGotoBookmark(x,x,x,x,x,x,x,x,x)

- ea: `0x1001f270`
- end: `0x1001f2f1`
- name: `_TextGotoBookmark@36`
- size: `129`
- prototype: `int __stdcall(int, LONG lDistanceToMove, int, int, int, __int128)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1000fe70`
- `0x100136b0`
- `0x1001e1e0`
- `0x1001f830`
- `0x10022400`

## callees

- `0x1001f270`
- `0x10021670`

## import_xrefs

- `KERNEL32!SetFilePointer` at `0x1001f283`
- `KERNEL32!SetFilePointer` at `0x1001f283`

## pseudocode

```c
int __stdcall TextGotoBookmark(int a1, LONG lDistanceToMove, int a3, int a4, int a5, __int128 a6)
{
  if ( SetFilePointer(*(HANDLE *)(a1 + 528), lDistanceToMove, 0, 0) == -1 )
    return -1022;
  *(_DWORD *)(a1 + 8848) = lDistanceToMove;
  *(_DWORD *)(a1 + 8852) = a3;
  *(_DWORD *)(a1 + 11996) = a4;
  *(_DWORD *)(a1 + 8760) = 0;
  *(_DWORD *)(a1 + 12000) = a5;
  if ( a5 )
    *(__m128i *)(a1 + 12004) = _mm_loadu_si128((const __m128i *)&a6);
  *(_DWORD *)(a1 + 11956) = 0;
  return TextGetNextRow(a1, 1);
}

```

## disassembly

```asm
0x1001f270  push    esi
0x1001f271  mov     esi, [esp+4+arg_0]
0x1001f275  push    0; dwMoveMethod
0x1001f277  push    0; lpDistanceToMoveHigh
0x1001f279  push    [esp+0Ch+lDistanceToMove]; lDistanceToMove
0x1001f27d  push    dword ptr [esi+210h]; hFile
0x1001f283  call    ds:__imp__SetFilePointer@16; SetFilePointer(x,x,x,x)
0x1001f289  cmp     eax, 0FFFFFFFFh
0x1001f28c  jnz     short loc_1001F297
0x1001f28e  mov     eax, 0FFFFFC02h
0x1001f293  pop     esi
0x1001f294  retn    24h ; '$'
0x1001f297  mov     eax, [esp+4+lDistanceToMove]
0x1001f29b  mov     [esi+2290h], eax
0x1001f2a1  mov     eax, [esp+4+arg_8]
0x1001f2a5  mov     [esi+2294h], eax
0x1001f2ab  mov     eax, [esp+4+arg_C]
0x1001f2af  mov     [esi+2EDCh], eax
0x1001f2b5  mov     eax, [esp+4+arg_10]
0x1001f2b9  mov     dword ptr [esi+2238h], 0
0x1001f2c3  mov     [esi+2EE0h], eax
0x1001f2c9  test    eax, eax
0x1001f2cb  jz      short loc_1001F2DB
0x1001f2cd  movdqu  xmm0, [esp+4+arg_14]
0x1001f2d3  movdqu  xmmword ptr [esi+2EE4h], xmm0
0x1001f2db  push    1
0x1001f2dd  push    esi
0x1001f2de  mov     dword ptr [esi+2EB4h], 0
0x1001f2e8  call    _TextGetNextRow@8; TextGetNextRow(x,x)
0x1001f2ed  pop     esi
0x1001f2ee  retn    24h ; '$'
```
