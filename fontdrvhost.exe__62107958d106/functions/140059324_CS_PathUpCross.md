# CS_PathUpCross

- ea: `0x140059324`
- end: `0x140059356`
- name: `CS_PathUpCross`
- size: `50`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140059518`
- `0x140064ea4`

## callees

- `0x140059324`
- `0x1400595cc`
- `0x140059a48`
- `0x140059a78`

## pseudocode

```c
__int64 __fastcall CS_PathUpCross(__int64 a1)
{
  if ( *(_DWORD *)(CS_PathXtraCross(a1, 1) + 20) <= *(_DWORD *)(a1 + 20) )
    return CS_BackPathCross(a1);
  else
    return CS_ForwPathCross(a1);
}

```

## disassembly

```asm
0x140059324  push    rbx
0x140059326  sub     rsp, 20h
0x14005932a  mov     edx, 1
0x14005932f  mov     rbx, rcx
0x140059332  call    CS_PathXtraCross
0x140059337  mov     rcx, rbx
0x14005933a  mov     edx, [rax+14h]
0x14005933d  cmp     edx, [rbx+14h]
0x140059340  jle     short loc_14005934C
0x140059342  add     rsp, 20h
0x140059346  pop     rbx
0x140059347  jmp     CS_ForwPathCross
0x14005934c  add     rsp, 20h
0x140059350  pop     rbx
0x140059351  jmp     CS_BackPathCross
```
