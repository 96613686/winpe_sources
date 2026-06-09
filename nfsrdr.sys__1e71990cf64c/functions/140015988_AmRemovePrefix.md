# AmRemovePrefix

- ea: `0x140015988`
- end: `0x1400159c3`
- name: `AmRemovePrefix`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400150f0`
- `0x140035384`

## callees

- `0x140015988`
- `0x14003adc0`

## pseudocode

```c
__int64 __fastcall AmRemovePrefix(__int64 a1, unsigned __int16 a2)
{
  unsigned __int16 v2; // ax

  if ( *(_WORD *)a1 <= a2 || *(_WORD *)(a1 + 2) <= a2 )
    return 3221225473LL;
  v2 = *(_WORD *)a1 - a2;
  *(_WORD *)a1 = v2;
  memmove(*(void **)(a1 + 8), (const void *)(*(_QWORD *)(a1 + 8) + a2), v2);
  return 0;
}

```

## disassembly

```asm
0x140015988  sub     rsp, 28h
0x14001598c  movzx   eax, word ptr [rcx]
0x14001598f  cmp     ax, dx
0x140015992  jbe     short loc_1400159B8
0x140015994  cmp     [rcx+2], dx
0x140015998  jbe     short loc_1400159B8
0x14001599a  sub     ax, dx
0x14001599d  movzx   edx, dx
0x1400159a0  movzx   r8d, ax; Size
0x1400159a4  mov     [rcx], r8w
0x1400159a8  mov     rcx, [rcx+8]; void *
0x1400159ac  add     rdx, rcx; Src
0x1400159af  call    memmove
0x1400159b4  xor     eax, eax
0x1400159b6  jmp     short loc_1400159BD
0x1400159b8  mov     eax, 0C0000001h
0x1400159bd  add     rsp, 28h
0x1400159c1  retn
```
