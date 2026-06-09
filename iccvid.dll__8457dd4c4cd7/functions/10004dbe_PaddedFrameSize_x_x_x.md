# PaddedFrameSize(x,x,x)

- ea: `0x10004dbe`
- end: `0x10004de1`
- name: `_PaddedFrameSize@12`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x10004de7`
- `0x10004e8d`

## callees

- `0x10004dbe`

## pseudocode

```c
int __fastcall PaddedFrameSize(int a1, int a2, int a3)
{
  if ( a3 )
    return (-a3 & (a3 + a1 + a2 - 1)) - a2;
  else
    return a1;
}

```

## disassembly

```asm
0x10004dbe  mov     edi, edi
0x10004dc0  push    ebp
0x10004dc1  mov     ebp, esp
0x10004dc3  push    esi
0x10004dc4  mov     esi, [ebp+arg_0]
0x10004dc7  test    esi, esi
0x10004dc9  jz      short loc_10004DDA
0x10004dcb  lea     eax, [edx-1]
0x10004dce  add     eax, ecx
0x10004dd0  add     eax, esi
0x10004dd2  neg     esi
0x10004dd4  and     eax, esi
0x10004dd6  sub     eax, edx
0x10004dd8  jmp     short loc_10004DDC
0x10004dda  mov     eax, ecx
0x10004ddc  pop     esi
0x10004ddd  pop     ebp
0x10004dde  retn    4
```
