# write_multi_char_0

- ea: `0x180045130`
- end: `0x180045182`
- name: `write_multi_char_0`
- size: `82`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180045280`
- `0x180045e80`
- `0x1800472a0`

## callees

- `0x18001e648`
- `0x180045130`

## pseudocode

```c
void __fastcall write_multi_char_0(wchar_t a1, int a2, _DWORD *a3)
{
  int v4; // edi

  if ( a2 > 0 )
  {
    v4 = a2;
    while ( putwch_nolock(a1) != 0xFFFF )
    {
      if ( ++*a3 != -1 && --v4 > 0 )
        continue;
      return;
    }
    *a3 = -1;
  }
}

```

## disassembly

```asm
0x180045130  test    edx, edx
0x180045132  jle     short locret_180045181
0x180045134  mov     [rsp+arg_0], rbx
0x180045139  mov     [rsp+arg_8], rsi
0x18004513e  push    rdi
0x18004513f  sub     rsp, 20h
0x180045143  mov     rbx, r8
0x180045146  mov     edi, edx
0x180045148  movzx   esi, cx
0x18004514b  movzx   ecx, si; Character
0x18004514e  call    _putwch_nolock
0x180045153  mov     ecx, 0FFFFh
0x180045158  cmp     ax, cx
0x18004515b  jz      short loc_18004516C
0x18004515d  inc     dword ptr [rbx]
0x18004515f  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180045162  jz      short loc_180045172
0x180045164  dec     edi
0x180045166  test    edi, edi
0x180045168  jg      short loc_18004514B
0x18004516a  jmp     short loc_180045172
0x18004516c  mov     dword ptr [rbx], 0FFFFFFFFh
0x180045172  mov     rbx, [rsp+28h+arg_0]
0x180045177  mov     rsi, [rsp+28h+arg_8]
0x18004517c  add     rsp, 20h
0x180045180  pop     rdi
0x180045181  retn
```
